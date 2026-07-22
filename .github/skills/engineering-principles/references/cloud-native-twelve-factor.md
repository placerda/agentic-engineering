# Cloud-native services and Twelve-Factor

Use this guidance for deployable applications and services. Do not impose
it on every library, local tool, or script.

## The twelve factors, contextualized

1. **Codebase:** one codebase tracked in revision control, many deploys.
2. **Dependencies:** declare and isolate dependencies; do not rely on
   implicit machine state.
3. **Config:** keep per-environment configuration separate from code.
   Secrets live in a secure mechanism, never in the repository.
4. **Backing services:** treat databases, queues, caches, and APIs as
   attached resources, replaceable through configuration.
5. **Build, release, run:** produce an immutable artifact, combine it with
   configuration into an identifiable release, and run it without
   rebuilding.
6. **Processes:** prefer stateless processes and share state through the
   appropriate service.
7. **Port binding:** when applicable, the service exports its interface
   through a port and does not depend on an externally injected server.
8. **Concurrency:** scale out by process types and counts, with
   partitionable work.
9. **Disposability:** start up and shut down fast; handle interruption,
   redelivery, and recovery.
10. **Dev/prod parity:** reduce differences in dependencies, services, and
    processes between development and production.
11. **Logs:** write structured events; routing, retention, and querying are
    the environment's responsibility.
12. **Admin processes:** run migrations and one-off tasks with the same
    version, configuration, controls, and audit trail as the application.

## Current complements

These practices extend the original Twelve-Factor methodology with current
cloud-native operational and security guidance.

- Define health checks that represent real capacity to serve traffic.
- Use least privilege, small images, verified dependencies, and workload
  identity.
- Design observability for correlated logs, metrics, and traces.
- Declare limits, resource requests, timeouts, and scaling behavior.
- Validate rollback or roll-forward, migration, and cross-version
  compatibility.

## Conceptual references and further reading

The wording above is original, project-focused synthesis informed by:

- [The Twelve-Factor App](https://12factor.net/).
- Majors, Charity; Fong-Jones, Liz; Miranda, George.
  [*Observability Engineering*](https://www.oreilly.com/library/view/observability-engineering/9781492076438/).
  O'Reilly Media, 2022.
- Kubernetes documentation.
  ["Configure Liveness, Readiness and Startup Probes"](https://kubernetes.io/docs/tasks/configure-pod-container/configure-liveness-readiness-startup-probes/).
- Cloud Native Computing Foundation.
  ["Software Supply Chain Security Best Practices"](https://www.cncf.io/reports/software-supply-chain-security-best-practices/).
