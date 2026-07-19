# Características, trade-offs e decisões

## Priorizar

- Extraia características do domínio, restrições e riscos, não de uma lista
  genérica.
- Escolha um conjunto pequeno de características importantes, como
  disponibilidade, segurança, modificabilidade, desempenho ou auditabilidade.
- Torne cada característica observável com cenário, estímulo, ambiente, resposta
  e medida.
- Distingua característica global de característica restrita a um fluxo ou
  componente.

## Analisar

- Toda melhoria tem custo ou efeito colateral. Declare o que foi sacrificado.
- Compare alternativas no contexto. Inclua complexidade cognitiva, operação,
  dados, entrega, custo e reversibilidade.
- Comece pelo menor grau de distribuição que atende às medidas.
- Métricas são sinais para investigação, não metas isoladas. Quando uma medida
  vira objetivo, ela pode perder valor diagnóstico.

## Registrar decisão

Use um ADR quando a decisão:

- altera uma fronteira, contrato, dado ou característica relevante;
- é cara de reverter;
- restringe alternativas futuras;
- afeta mais de um componente ou equipe;
- precisa de fiscalização automatizada.

Registre contexto, forças, alternativas, decisão, consequências, plano de
adoção e verificações de conformidade. Não reescreva ADR aceito para apagar o
histórico. Substitua-o por outro ADR.

## Fitness functions

Converta regras objetivas em verificações: testes de dependência, limites de
latência, compatibilidade de esquema, políticas, análise estática, testes de
resiliência ou alertas. Uma regra sem forma de inspeção tende a degradar.

