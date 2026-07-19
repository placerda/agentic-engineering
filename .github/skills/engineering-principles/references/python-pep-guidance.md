# Python baseado em PEP 8, PEP 20 e PEP 257

## Fonte de verdade

`pyproject.toml` e as configurações de Ruff, formatador, verificador de tipos e
testes são executáveis e têm precedência sobre preferências genéricas. Não
introduza uma ferramenta se o projeto já tem outra equivalente.

## PEP 8

- Otimize para leitura consistente.
- Use nomes que expressem intenção e respeitem convenções da base.
- Organize imports e evite wildcard imports.
- Separe blocos lógicos sem criar fragmentação visual.
- Respeite o limite de linha configurado. Quando não houver configuração, use a
  recomendação oficial como ponto de partida.
- Consistência local importa, mas não perpetue uma violação que a automação do
  projeto rejeita.

## PEP 20

- Prefira explícito a implícito e simples a complicado.
- Legibilidade é requisito, não acabamento.
- Não deixe erros passarem silenciosamente sem decisão explícita.
- Diante de ambiguidade com impacto, não adivinhe.
- Se uma implementação é difícil de explicar, reduza ou registre a razão.

## PEP 257

- Documente módulos e APIs públicas.
- Docstrings resumem comportamento e contrato, não repetem assinatura.
- Inclua argumentos, retorno, efeitos colaterais, exceções e restrições quando
  forem relevantes ao uso correto.
- Use uma linha para casos simples; use resumo, linha em branco e detalhes para
  contratos maiores.
- Documente o comportamento público de classes e diferenças de extensão ou
  substituição.

## Verificação

Execute, conforme configurado no projeto:

1. Ruff ou linter equivalente.
2. Formatador em modo de verificação.
3. Verificador estático de tipos.
4. Testes específicos e depois o conjunto necessário.

