---
name: cloud-native-service
description: Avalia e implementa aplicações implantáveis segundo práticas cloud-native e Twelve-Factor contextualizadas. Use em serviços, containers e implantação; não use para bibliotecas ou scripts sem operação de serviço.
---

# Serviço cloud-native

Leia
`../engineering-principles/references/cloud-native-twelve-factor.md` e, quando
houver comunicação distribuída,
`../engineering-principles/references/data-integration.md`.

1. Confirme unidade de implantação, ambientes e modelo operacional.
2. Revise dependências, configuração, segredos e serviços anexados.
3. Garanta separação entre build, release e run.
4. Modele estado, escala, interrupção, idempotência e tarefas administrativas.
5. Defina logs, métricas, traces, health checks e recuperação.
6. Verifique segurança da cadeia, identidade e privilégio mínimo.

Documente quais fatores não se aplicam e por quê. Não distribua componentes
somente para parecer cloud-native.

