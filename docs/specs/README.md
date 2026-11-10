# Artifact operations contract

Last updated: 2026-11-10

Status: planned; the example is a reference record, not a released wire schema.

## Inputs and outputs

An operation supplies an explicit immutable URI/revision or backend object identity,
expected content hash, optional length, destination, backend adapter and limits.
Authentication is configured separately and never embedded in public references.

Planned operations are resolve/materialize, verify, publish/transfer and cache
inspection. Each returns the requested source identity, observed hash/length,
destination or immutable published reference, outcome and measurement coverage.
Unknown source version, duration or cost remains unknown.

## Integrity and lifecycle requirements

- Fail on hash/length mismatch, incomplete writes, unsafe destinations or
  unsupported schemes. Do not return a partially materialized artifact as valid.
- Verify existing cached bytes, preserve immutable identities and isolate
  task-owned staging before promoting a verified result.
- Keep data and logs free of embedded credentials. Define overwrite/collision
  policy explicitly; never silently replace a different immutable object.
- Use existing local/object-store backends. Keep optional adapters independent.
- A verified byte hash does not establish data rights, model compatibility,
  trustworthy execution, evaluation quality or scientific correctness.

## First implementation and acceptance

- [ ] Select one local-file backend and explicit reference/receipt version.
- [ ] Verify a tiny known fixture, corrupt bytes, wrong length and missing input.
- [ ] Prove cache hit validation and partial-write/collision failure behavior.
- [ ] Demonstrate standalone materialization and consumption by another process.
- [ ] Add one explicitly selected object-store adapter only after the local path.

No database, GPU or provider account is required to read/use this specification.
A first runnable implementation needs its own environment and installed acceptance.
