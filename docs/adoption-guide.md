# Guia de adoção

Este modelo é um ponto de partida. Adote somente regras que possam ser
explicadas, mantidas e verificadas no repositório de destino.

## 1. Faça um inventário

Registre:

- propósito, usuários e capacidades do produto;
- linguagens, frameworks e runtimes;
- comandos reais de bootstrap, build, teste, lint e execução;
- estrutura de módulos e ownership;
- interfaces públicas, dados persistidos e unidades de implantação;
- CI, políticas de segurança e processo de release;
- documentação canônica e canais operacionais.

Execute os comandos antes de documentá-los. Não copie exemplos deste modelo como
se fossem comandos do projeto.

## 2. Adote o núcleo

Copie `AGENTS.md` e `.github/copilot-instructions.md`. Em seguida:

1. Substitua linguagem genérica por fatos estáveis do repositório.
2. Mantenha o arquivo sempre ativo curto.
3. Remova qualquer regra que contradiga a automação existente.
4. Acrescente os comandos validados e os caminhos mais importantes.
5. Não inclua segredos, URLs privadas com tokens ou dados pessoais.

## 3. Ative escopo real

Copie `python.instructions.md` apenas se houver Python. Confirme se o glob
`**/*.py,**/*.pyi` cobre o projeto.

Copie `cloud-native.instructions.md` somente se o repositório contiver serviços
implantáveis ou infraestrutura. Ajuste `applyTo` aos diretórios reais. Não use
`**/*.yaml` de forma ampla, pois isso aplicaria regras cloud-native a arquivos
sem relação com implantação.

Crie novas instruções com escopo somente quando:

- a regra se aplica a um conjunto identificável de arquivos;
- o glob é específico;
- a regra será usada com frequência;
- não existe uma configuração executável equivalente.

## 4. Escolha agentes

Comece com `implementation` e, se necessário, `architecture`. Adicione outros
perfis quando houver demanda recorrente e uma saída diferente.

Para cada perfil:

- mantenha nome funcional;
- escreva na descrição quando usar e quando não usar;
- conceda os menores aliases de ferramentas necessários;
- não configure MCPs ou segredos sem revisão de segurança;
- defina entrada, saída e handoff.

Muitos agentes aumentam roteamento, duplicação e manutenção. Poucos agentes
amplos aumentam contexto e mistura de responsabilidades. Adicione um agente
quando a especialização possui critérios, ferramentas ou artefatos próprios.

## 5. Escolha skills

Copie `engineering-principles` como biblioteca canônica. Remova referências sem
aplicação. Skills focadas devem apontar para a regra canônica, não duplicá-la.

Revise qualquer skill externa antes de instalar. Skills podem conter scripts e
instruções maliciosas. Não pré-aprove shell em `allowed-tools` sem confiança e
necessidade.

## 6. Configure issue e especificação

Adapte os templates de issue ao processo real. Aplique a regra de Spec Kit da
constituição:

- issue direta para mudança local e reversível;
- especificação para alto risco ou múltiplas condições estruturais.

Evite exigir especificação extensa para correções simples. Evite também usar uma
issue vaga para migração de dados, mudança de segurança ou contrato
incompatível.

## 7. Integre qualidade

Este repositório não fornece workflow executável porque não conhece a stack de
destino. No projeto consumidor, conecte fitness functions aos mecanismos já
adotados:

- formatter, linter e tipos;
- testes unitários, de contrato, integração e jornada;
- análise de dependências e ciclos;
- segurança de código, dependências e segredos;
- validação de schema e infraestrutura;
- métricas e políticas de implantação.

Cada gate precisa ter dono, tempo aceitável, mensagem acionável e processo para
exceção.

## 8. Faça um piloto

Escolha uma mudança real de baixo risco e observe:

- instruções descobertas corretamente;
- arquivos irrelevantes carregados;
- perguntas repetidas;
- ferramenta ou permissão ausente;
- qualidade dos handoffs;
- tempo até primeira mudança válida;
- retrabalho após revisão;
- evidência produzida.

Ajuste o modelo a partir desses sinais, não do volume de arquivos.

## Checklist

- [ ] Núcleo contém fatos estáveis e comandos verificados.
- [ ] Instruções com escopo têm globs específicos.
- [ ] Cada agente tem uso, não uso, ferramentas e saída.
- [ ] Skills têm uma fonte canônica por regra.
- [ ] Regra de Spec Kit foi adaptada ao risco do produto.
- [ ] Templates refletem o processo da equipe.
- [ ] CI executa regras objetivas importantes.
- [ ] Links, nomes e caminhos foram verificados.
- [ ] Proprietário e revisão periódica foram definidos.

