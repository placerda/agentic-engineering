---
name: cloud-native-service
description: Evaluates and implements deployable applications following contextualized cloud-native and Twelve-Factor practices. Use for services, containers, and deployment; do not use for libraries or scripts without service operation.
---

# Cloud-native service

Read
`../engineering-principles/references/cloud-native-twelve-factor.md` and,
when there is distributed communication,
`../engineering-principles/references/data-integration.md`.

1. Confirm the deployment unit, environments, and operating model.
2. Review dependencies, configuration, secrets, and attached services.
3. Ensure separation between build, release, and run.
4. Model state, scaling, interruption, idempotency, and administrative
   tasks.
5. Define logs, metrics, traces, health checks, and recovery.
6. Verify chain security, identity, and least privilege.

Document which factors do not apply and why. Do not distribute components
just to appear cloud-native.

