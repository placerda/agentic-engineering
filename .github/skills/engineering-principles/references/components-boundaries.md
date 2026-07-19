# Componentes e fronteiras

## Onde criar limites

- Desenhe limites por eixos de mudança, ownership, volatilidade, risco e
  características arquiteturais, não por moda ou organograma momentâneo.
- Agrupe o que muda pela mesma razão. Separe o que muda por razões diferentes.
- Considere quem publica, implanta e suporta o componente.
- Comece com independência lógica. Distribua fisicamente apenas quando escala,
  isolamento, implantação, conformidade ou ownership justificarem o custo.

## Coesão e acoplamento

- Avalie se os elementos do componente contribuem para uma finalidade comum.
- Meça dependências estáticas, temporais, de dados e operacionais.
- Mantenha o grafo de dependências entre componentes acíclico.
- Dependências síncronas criam acoplamento operacional em disponibilidade,
  latência e capacidade. Inclua esse custo na decisão.
- Elementos estáveis devem depender de abstrações úteis; abstrações sem usuários
  ou variação apenas escondem complexidade.

## Contratos de fronteira

- Dados que cruzam limites pertencem a contratos explícitos, mínimos e
  versionáveis.
- Não transporte objetos internos inteiros por conveniência.
- Defina semântica de erro, idempotência, tempo limite, compatibilidade e
  ownership.
- Uma fronteira parcial pode ser suficiente quando oferece isolamento de código
  e testes sem custo de processo ou rede.

## Heurísticas

- Prefira um monólito modular a serviços prematuros.
- Reuse deliberadamente. Compartilhar código também compartilha calendário de
  mudança e risco de regressão.
- Alinhe limites, dados e responsabilidade de equipe sempre que possível.
- Reavalie granularidade quando componentes mudam juntos, exigem coordenação
  frequente ou não podem ser operados de forma independente.

