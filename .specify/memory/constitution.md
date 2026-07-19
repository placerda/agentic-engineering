# Constituição de engenharia

## I. Propósito e comportamento

O software deve expressar capacidades do domínio e entregar comportamento
observável. Frameworks, bancos, interfaces e provedores são mecanismos. Mudanças
começam por problema, usuário, resultado e critério de aceite.

## II. Dependências e fronteiras

Dependências apontam para políticas estáveis. Dados cruzam fronteiras por
contratos explícitos e mínimos. Limites acompanham mudança, ownership,
volatilidade e risco. Grafos de componentes permanecem acíclicos.

## III. Simplicidade e reversibilidade

Use o menor grau de distribuição e abstração que satisfaça requisitos medidos.
Prefira independência lógica antes de distribuição física e decisões
reversíveis enquanto o conhecimento for baixo.

## IV. Qualidade verificável

Regras objetivas viram testes, análise estática, políticas ou observação. Regras
de negócio devem ser testáveis sem infraestrutura real. Testes protegem
comportamento e contratos.

## V. Segurança e operação

Privilégio mínimo, segredos fora do código, entrada não confiável e recuperação
de falhas são requisitos de projeto. Código, dados, entrega, observabilidade e
operação devem permanecer alinhados.

## VI. Evidência

Trabalho não termina em código produzido. Critérios de aceite, validações,
documentação afetada, migração e riscos residuais precisam de evidência
reproduzível.

## Quando Spec Kit é obrigatório

Use o fluxo em `.specify/` se ocorrer qualquer condição de alto risco:

- mudança de autenticação, autorização, criptografia, privacidade ou limite de
  confiança;
- migração de dados com possibilidade de perda, corrupção ou indisponibilidade;
- contrato público incompatível sem estratégia de convivência.

Também use Spec Kit quando **duas ou mais** condições abaixo forem verdadeiras:

- alteração cruza três ou mais componentes ou unidades de implantação;
- exige nova fronteira, estilo arquitetural ou tecnologia operacional;
- afeta API, evento, esquema persistido ou integração externa;
- possui característica arquitetural mensurável como requisito principal;
- envolve mais de uma equipe ou entrega em várias etapas;
- permanece incerta após uma investigação curta;
- tem reversão cara ou exige migração coordenada.

Use trabalho direto por issue quando a mudança é local, reversível, cabe em um
componente, não altera contrato persistente ou público e possui critérios de
aceite verificáveis. Não crie especificação apenas por formalidade.

## Emendas

Mudanças nesta constituição exigem justificativa, impacto nos artefatos
existentes e plano de adoção. Regras que não podem ser verificadas devem ser
reescritas ou tratadas explicitamente como heurísticas.

**Versão:** 1.0.0  
**Ratificada em:** 2026-07-19

