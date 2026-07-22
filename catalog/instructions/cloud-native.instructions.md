---
applyTo: "**/Dockerfile,**/Dockerfile.*,**/docker-compose*.yml,**/docker-compose*.yaml,deploy/**,deployment/**,infra/**,k8s/**,helm/**,charts/**"
---

# Deployable applications and cloud-native services

These rules apply to services and deployment artifacts, not to every
library or script.

- Keep dependencies explicit and reproducible.
- Inject configuration per environment and keep secrets out of the code
  and the image.
- Treat databases, queues, caches, and external services as replaceable
  resources tied to configuration and contracts.
- Separate build, release, and run. The same artifact must move forward
  across environments.
- Prefer stateless processes; persist state in appropriate services.
- Expose the service through a port when applicable and scale through
  independent processes.
- Design for fast startup and shutdown, idempotency, and recovery after
  interruption.
- Reduce differences between development and production.
- Emit structured logs as an event stream for external collection.
- Run administrative tasks as versioned, auditable processes.

For deeper guidance, read
`.github/skills/engineering-principles/references/cloud-native-twelve-factor.md`.
