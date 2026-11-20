# research-artifacts

<!-- project-family:start -->
> **Project family:** [AI Research Lab](https://github.com/alvarovillalbaa#ai-research-lab) · **Area:** Research artifacts
<!-- project-family:end -->

Last updated: 2026-11-10

Resolve, transfer, cache and verify research artifacts through existing storage backends.

**Status: planned.** This repository defines the independent product contract,
requirements and small reference examples. No resolver, storage service, package
or transfer engine is implemented.

## Independent use and target contract

A caller supplies an immutable artifact reference, expected SHA-256 and optional
byte length, an explicit operation/destination and backend policy. The intended
tool resolves or transfers bytes, verifies integrity, and returns an identified
receipt. A cache hit must be verified under the same policy as a download.

[Specification and acceptance](docs/specs/README.md) ·
[Reference example](examples/artifact-ref.json) ·
[Source lineage](docs/sources/lineage.json)

This product can serve an external trainer or application without Lab. It uses
existing local/object-storage implementations. Model-data retains dataset/split
semantics; model-architectures and trainers retain weight/state compatibility;
model-serving retains runtime loading; research-controller retains promotion.
Experiment-kit validates research records and references rather than remote bytes.

Generic provenance records bytes, source/backend identity, hashes and optional
parent references. Domain-specific lineage and release decisions stay with their
producers. This is not a mandatory shared schema or centralized registry service.

MIT covers authored documentation/examples. External artifacts retain their own
rights. The fixture reference is illustrative, not an implemented URI scheme.
Credentials, datasets and model weights remain outside Git.
