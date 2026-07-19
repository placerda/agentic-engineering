# Testes e fitness functions

## Testabilidade arquitetural

- Regras de negócio devem executar sem UI, rede, banco, relógio ou provedor
  reais.
- Injete efeitos externos por contratos pequenos. Use implementações reais em
  testes de integração focados.
- Controle tempo, aleatoriedade e concorrência para manter determinismo.
- Se um comportamento importante só pode ser testado por uma jornada completa,
  a arquitetura provavelmente esconde limites úteis.

## Estratégia

- Testes unitários protegem regras e decisões locais.
- Testes de contrato protegem fronteiras entre consumidores e provedores.
- Testes de integração protegem adaptadores e configuração real.
- Poucos testes ponta a ponta protegem jornadas críticas.
- Testes devem observar comportamento, não a forma interna de implementá-lo.
- Um defeito deve ganhar uma reprodução automatizada quando o custo for
  razoável.

## Fitness functions

Automatize regras que precisam permanecer verdadeiras, por exemplo:

- o domínio não importa infraestrutura;
- o grafo de componentes não contém ciclos;
- APIs e eventos preservam compatibilidade;
- latência, disponibilidade ou custo permanecem dentro do orçamento;
- imagens e dependências atendem políticas de segurança;
- migrações suportam convivência entre versões;
- telemetria contém os sinais necessários para operar.

Escolha o ponto de execução mais barato que ainda detecte a violação a tempo:
IDE, pre-commit, teste, CI, implantação ou monitoramento.

## Evidência de conclusão

Registre comando, escopo, resultado e limitações. Cobertura é um sinal, não uma
prova de qualidade. Uma tarefa está incompleta se o resultado esperado não puder
ser verificado.

