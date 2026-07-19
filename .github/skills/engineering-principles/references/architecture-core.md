# Núcleo de arquitetura

## Propósito

- A organização do sistema deve revelar capacidades e linguagem do negócio,
  não apenas frameworks ou tipos técnicos.
- Arquitetura existe para manter opções importantes abertas e reduzir o custo
  total de mudar, operar e verificar o sistema.
- Não há estilo universalmente melhor. Toda escolha responde a contexto,
  restrições e trade-offs.

## Direção das dependências

- Dependências de código apontam para políticas estáveis e regras do domínio.
- Interface, persistência, transporte, framework e provedor são mecanismos
  substituíveis, não o centro do modelo.
- Modelos de ORM, HTTP, mensageria ou SDK não devem atravessar o núcleo. Converta
  para contratos mínimos na fronteira.
- O fluxo de execução pode sair do núcleo, mas a dependência de código continua
  apontando para dentro por meio de portas, callbacks ou interfaces.

## Decisões

- Separe política de mecanismo. A política descreve o que deve acontecer; o
  mecanismo descreve como um ambiente realiza isso.
- Prefira decisões reversíveis quando o conhecimento ainda é baixo.
- Adie detalhes sem bloquear aprendizado essencial.
- Justifique abstrações por estabilidade, variação concreta ou proteção de uma
  fronteira. Evite generalidade especulativa.
- Trate arquitetura como atividade contínua. Verifique se implementação, dados,
  entrega, observabilidade e operação ainda expressam a decisão.

## Perguntas de revisão

1. Que capacidade de negócio esta estrutura torna evidente?
2. O núcleo pode executar sem UI, rede, banco, relógio ou provedor real?
3. Qual detalhe teria maior custo de substituição hoje?
4. A dependência está orientada para a parte mais estável?
5. Que evidência mostra que a decisão funciona sob as restrições reais?

