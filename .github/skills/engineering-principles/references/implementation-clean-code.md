# Práticas de implementação e código limpo

Estas são práticas gerais resumidas, amplamente conhecidas na indústria. Não são
transcrições nem extrações do livro *Clean Code*.

## Clareza

- Use nomes que expressem intenção, unidade e domínio. Evite abreviações locais
  sem valor.
- Mantenha funções focadas em um resultado e no mesmo nível de abstração.
- Prefira fluxo explícito a efeitos colaterais ocultos.
- Reduza aninhamento com validações claras, decomposição e modelos adequados.
- Comentários explicam motivo, risco ou restrição. Não narram código confuso.

## Design

- Remova duplicação de conhecimento, não apenas texto semelhante.
- Encapsule invariantes perto dos dados e comportamentos que as mantêm.
- Não adicione parâmetros, flags ou abstrações para cenários hipotéticos.
- Torne estados inválidos difíceis de representar quando o custo for razoável.
- Preserve contratos pequenos e coesos. Evite objetos que conhecem detalhes de
  muitas camadas.

## Erros

- Falhe com contexto útil e no nível que pode tomar uma decisão.
- Não capture exceções amplas para retornar sucesso aparente.
- Preserve a causa original ao traduzir erros entre fronteiras.
- Mensagens não devem expor segredo, dado pessoal ou detalhe explorável.
- Modele recuperação e idempotência para efeitos repetíveis.

## Mudança segura

- Leia testes e chamadas antes de alterar uma interface.
- Faça a menor mudança completa e mantenha refatoração separada quando possível.
- Apague código morto em vez de comentar versões antigas.
- Use formatador, linter, análise estática e testes configurados pelo projeto.

