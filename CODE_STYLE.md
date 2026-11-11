# Code style and architecture

SDK Lattice is a bootstrap placeholder. No orchestration API or dependency
graph has been accepted. The guidelines below are proposals informed by the
existing Lattice repositories, not implemented contracts.

- Compose the networking, tunnel, DNS and policy layers through explicit
  boundaries; do not move their domain logic into the SDK by default.
- Define lifecycle, ownership, startup order, shutdown, cancellation,
  partial failure and compensation before exposing orchestration APIs.
- Expose typed configuration and errors. Check runtime capabilities and
  surface unsupported operations, missing privileges and driver failures.
- Design for injectable components and deterministic tests; supplement them
  with cross-platform integration tests using real OS resources where needed.
- Follow Rust formatting, public rustdoc, examples and CI feature gates.
  Record public contract decisions in ADRs under the repository workflow.

The flow-lattice contract and tunnel-lattice's pre-1.0 API are integration
risks. Prototype against them without treating either as a stable boundary.
