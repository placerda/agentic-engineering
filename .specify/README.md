# Fluxo mínimo de especificação

Este diretório oferece um fluxo leve inspirado em desenvolvimento orientado por
especificação. Ele não incorpora nem depende de uma distribuição de terceiros.

Use a regra objetiva em `memory/constitution.md`.

## Sequência

1. Copie `templates/spec-template.md` para
   `.specify/specs/NNN-nome-curto/spec.md`.
2. Resolva perguntas que alteram comportamento, dados, segurança ou contrato.
3. Copie `templates/plan-template.md` para `plan.md` no mesmo diretório.
4. Registre decisões arquiteturais significativas em `docs/adr/`.
5. Divida a entrega em tarefas pequenas, cada uma com condição de verificação.
6. Atualize especificação e plano quando uma decisão mudar. Não deixe o código
   ser a única fonte do novo comportamento.

Mantenha a especificação focada no quê e no porquê. O plano descreve como,
ordem, migração e validação.

