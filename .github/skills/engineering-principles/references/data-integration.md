# Dados e integração

## Dados

- Ownership de dados acompanha a capacidade responsável por sua semântica.
- Integração por banco compartilhado reduz autonomia e cria contratos ocultos.
- Escolha topologia de dados junto com os limites e a operação, não depois.
- Mudanças de esquema precisam de compatibilidade, migração, observação e
  recuperação.
- Minimize cópias, mas aceite duplicação controlada quando ela reduz acoplamento
  e possui regra clara de consistência.

## Comunicação

- Chamadas síncronas são simples de raciocinar localmente, mas acoplam
  disponibilidade, latência e capacidade.
- Mensagens assíncronas desacoplam tempo e podem melhorar resiliência, mas
  exigem idempotência, ordenação quando necessária, tratamento de duplicatas,
  rastreamento e operação.
- Defina tempo limite, repetição, backoff, circuit breaker e orçamento de
  latência no nível apropriado. Repetições sem limite amplificam falhas.
- Contratos devem ter semântica de erro e evolução compatível.

## Orquestração e coreografia

- Use orquestração quando um fluxo precisa de coordenação explícita, estado
  visível, compensação central ou auditoria de etapas.
- Use coreografia quando participantes podem reagir de forma independente e o
  acoplamento a um coordenador seria mais caro.
- Evite coreografia opaca com sequência de eventos implícita e difícil de
  observar.
- Para fluxos críticos, modele falhas parciais e compensações antes da
  implementação.

## Evidência

Teste contratos, compatibilidade, idempotência, falhas parciais, recuperação e
telemetria de correlação. Um diagrama feliz não prova operação segura.

