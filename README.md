# Agentic Engineering

Modelo reutilizável para orientar agentes de engenharia de software no GitHub e
no GitHub Copilot sem transformar cada solicitação em um manual extenso.

O repositório usa divulgação progressiva:

1. Um núcleo curto é aplicado a todo trabalho.
2. Instruções específicas entram apenas para arquivos compatíveis.
3. Agentes funcionais assumem papéis com ferramentas mínimas.
4. Skills carregam procedimentos e referências somente quando relevantes.
5. Documentação em `docs/` serve a pessoas e pode ser aberta quando uma skill ou
   instrução a indicar. Ela não é contexto automático.

Spec Kit, em `.specify/`, é acionado por uma regra objetiva para mudanças de
alto risco. Ele é um fluxo de trabalho, não uma camada de contexto.

## Início rápido

1. Leia [`AGENTS.md`](AGENTS.md) para conhecer o contrato operacional.
2. Escolha o agente pela tabela em [`docs/routing.md`](docs/routing.md).
3. Para uma mudança simples, trabalhe a partir de uma issue com critérios de
   aceite.
4. Para uma mudança ampla ou de alto risco, siga
   [`.specify/README.md`](.specify/README.md).
5. Antes de concluir, produza evidência reproduzível de que o comportamento
   esperado funciona.

## Mapa do repositório

| Caminho | Finalidade |
| --- | --- |
| `.github/copilot-instructions.md` | Núcleo conciso, sempre ativo |
| `.github/instructions/` | Regras ativadas por caminho |
| `.github/agents/` | Agentes funcionais e limites de atuação |
| `.github/skills/` | Índices e procedimentos carregados sob demanda |
| `.specify/` | Constituição e fluxo mínimo de especificação |
| `docs/` | Guia completo, adoção e roteamento |
| `docs/adr/` | Decisões arquiteturais do projeto consumidor |

## Adotar em outro repositório

Não copie tudo sem análise. Comece pelo núcleo, substitua comandos e caminhos
pelos que foram executados com sucesso no projeto, remova agentes sem uso e
ative somente as instruções compatíveis com a tecnologia presente. O roteiro
completo está em [`docs/adoption-guide.md`](docs/adoption-guide.md).

## Descoberta automática e referências comuns

O GitHub Copilot reconhece arquivos em locais e formatos específicos. Arquivos
como `.github/copilot-instructions.md`, `AGENTS.md`, perfis em
`.github/agents/`, instruções `*.instructions.md` e skills com `SKILL.md`
podem ser descobertos por superfícies compatíveis. Um Markdown comum em `docs/`
não é carregado automaticamente apenas por existir. Ele precisa ser anexado,
referenciado por uma instrução compatível ou aberto quando uma skill orientar
seu uso.

O suporte varia entre GitHub.com, Copilot CLI e IDEs. Consulte
[`docs/agentic-development-model.md`](docs/agentic-development-model.md#compatibilidade-entre-superficies)
antes de depender de um recurso específico.

## Direitos autorais e método de síntese

Os princípios deste modelo são formulações originais e concisas. Duas obras
locais autorizadas pelo usuário foram consultadas somente para síntese:
*Clean Architecture*, de Robert C. Martin, e *Fundamentals of Software
Architecture*, de Mark Richards e Neal Ford. Nenhuma passagem, figura, tabela,
exemplo ou estrutura de capítulo foi reproduzida.

As práticas de Clean Code aqui mencionadas são um resumo geral de práticas
amplamente conhecidas. Elas não foram extraídas nem citadas do livro
*Clean Code*. As fontes oficiais e referências bibliográficas estão em
[`sources.md`](.github/skills/engineering-principles/references/sources.md).

Este repositório não declara uma licença. Defina uma licença adequada antes de
redistribuir o modelo.
