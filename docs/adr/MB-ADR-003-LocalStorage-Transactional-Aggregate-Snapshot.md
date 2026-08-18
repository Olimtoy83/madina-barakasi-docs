# MB-ADR-003 — LocalStorage Transactional Aggregate Snapshot

> **Architecture Decision Record for transactional persistence in the localStorage prototype**

---

## Document Information

| Field | Value |
| --- | --- |
| Document ID | MB-ADR-003 |
| Volume | II — Architecture |
| Title | LocalStorage Transactional Aggregate Snapshot |
| Version | 0.1.0 |
| Status | Draft |
| Classification | ADR |
| Language | English |
| Owner | Architecture |
| Created | 2026-08-18 |
| Last Updated | 2026-08-18 |

---

# 1. Context

Sale and Purchase completion currently calculate related CRM changes consistently in memory, but persistence uses multiple independent localStorage keys. A storage error can therefore leave persisted Products, Stock Movements, Transactions, and the completed Sale or Purchase in a partial durable state after reload.

This makes transactional history unreliable as a source for Reports and Analytics. In-memory domain calculation atomicity alone does not establish a durable transactional boundary.

# 2. Decision

The localStorage prototype will persist transactional CRM state in one versioned aggregate snapshot at:

```text
madina-crm:v2:transactional-state
```

The snapshot contains:

```text
{
  schemaVersion,
  revision,
  products,
  sales,
  purchases,
  stockMovements,
  transactions
}
```

The transactional slices are `products`, `sales`, `purchases`, `stockMovements`, and `transactions`. Clients and Tasks are outside this aggregate unless a future process requires their participation in Sale or Purchase completion atomicity.

The v2 snapshot is the authoritative persistence boundary for these transactional slices. A completion is successful only when domain calculation succeeds and the single aggregate persistence commit succeeds. The application and UI must not report completion as successful before that commit succeeds.

# 3. Atomicity Semantics

Completion must follow this sequence:

```text
calculate next aggregate
        -> serialize
        -> single localStorage write
        -> publish new in-memory state only after a successful write
```

If the write fails, completion is failed. The previous authoritative snapshot remains committed, no new completed lifecycle state is published, and partial cross-domain state is not treated as committed.

This provides prototype-level single-key atomic visibility. It is not a production database durability guarantee.

# 4. Error Handling and Recovery

Persistence errors must not be silently swallowed. Corruption or an unreadable authoritative v2 snapshot must not be silently replaced with empty arrays; it requires a controlled persistence or recovery error state.

The prototype does not introduce a journal, replay, rollback subsystem, or automatic reconstruction of conflicting historical data. A successful snapshot reloads as one complete committed aggregate. A failed snapshot write reloads the previous committed aggregate. Automatic invented recovery is prohibited.

# 5. Version and Revision

Every v2 snapshot contains `schemaVersion` and `revision`. The revision is a minimal snapshot version marker for the current prototype; this ADR does not define a complex optimistic-concurrency system.

# 6. Legacy v1 Compatibility

When no v2 snapshot exists, existing `madina-crm:v1:*` transactional keys may be read once as a legacy bootstrap source. Bootstrap reads serialized legacy values without automatic business-data normalization, repair, or recovery and must not invent resolutions for conflicting data.

After the first successful v2 transactional commit, the v2 snapshot becomes authoritative. The v1 transactional keys are no longer an authoritative source. This ADR does not require automatic deletion of v1 keys.

# 7. Duplicate Completion Protection

The application layer must prevent concurrent or in-flight duplicate completion of the same Sale or Purchase. Existing domain and reference-based deduplication remain additional safeguards. This ADR does not define distributed idempotency.

# 8. Scope and Supersession

This decision applies only to transactional persistence in the localStorage prototype. It does not define a production database schema, API, server transaction, journal protocol, event sourcing, outbox, distributed transaction, retry system, backup system, authentication, authorization, or complex concurrency control.

MB-ADR-003 must be superseded or revisited when the CRM moves to server or database persistence, where the appropriate durability, concurrency, retry, and recovery guarantees must be decided explicitly.

# 9. Consequences

- Transactional CRM persistence has one authoritative prototype boundary.
- Failed aggregate writes are visible as controlled persistence failures rather than successful completions.
- Reports and Analytics can consume only fully committed v2 transactional snapshots after implementation.
- The implementation requires aggregate storage, controlled read/write failure handling, and regression coverage for successful, failed, legacy-bootstrap, and duplicate-completion paths.
- Existing v1 data is preserved as a bootstrap source but is not automatically repaired.

# 10. Alternatives Considered

## Alternative A — Retain independent localStorage keys

Rejected because a multi-key write cannot provide the required durable cross-domain atomicity and may leave partial state after a storage failure.

## Alternative B — Single aggregate snapshot

Selected because a single localStorage write supplies the smallest controlled atomic-visibility boundary for the current prototype without designing a database or recovery subsystem.

## Alternative C — Multi-key journal or replay protocol

Rejected for the current prototype because it requires operation identifiers, commit stages, idempotent replay or rollback, and a recovery protocol beyond the approved scope.

# 11. Relationship to Existing Documentation

- MB-101 defines application data ownership and data boundaries.
- MB-CRM-004 requires cross-domain processes not to silently produce invalid partial state.
- MB-CRM-006 defines cross-domain data-contract integrity.
- MB-CRM-007 defines application service, data access, transaction management, and controlled error handling boundaries.
- MB-CRM-008 requires successful and failure transactional validation.

# 12. Status

This ADR is Draft and requires review before becoming Approved.

---

**Madina Barakasi Architecture Library**
