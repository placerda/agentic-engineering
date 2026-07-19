# Serviços cloud-native e Twelve-Factor

Use estas orientações em aplicações implantáveis e serviços. Não as imponha a
toda biblioteca, ferramenta local ou script.

## Doze fatores contextualizados

1. **Codebase:** uma base versionada por aplicação, com várias implantações.
2. **Dependências:** declare e isole dependências; não dependa do estado
   implícito da máquina.
3. **Configuração:** separe configuração por ambiente do código. Segredos ficam
   em mecanismo seguro, nunca no repositório.
4. **Serviços de apoio:** trate banco, fila, cache e APIs como recursos anexados
   e substituíveis por configuração.
5. **Build, release, run:** produza artefato imutável, combine-o com configuração
   em uma release identificável e execute sem reconstruir.
6. **Processos:** prefira processos sem estado e compartilhe estado por serviço
   apropriado.
7. **Port binding:** quando aplicável, o serviço exporta sua interface por uma
   porta e não depende de servidor externo acoplado.
8. **Concorrência:** escale por tipos e quantidades de processos, com trabalho
   particionável.
9. **Disposability:** inicialize e encerre rápido; trate interrupção, reentrega e
   recuperação.
10. **Paridade:** reduza diferenças de dependência, serviço e processo entre
    desenvolvimento e produção.
11. **Logs:** escreva eventos estruturados; roteamento, retenção e consulta são
    responsabilidades do ambiente.
12. **Administração:** execute migrações e tarefas pontuais com a mesma versão,
    configuração, controles e auditoria da aplicação.

## Complementos atuais

- Defina health checks que representem capacidade real de servir.
- Use privilégio mínimo, imagens pequenas, dependências verificadas e identidade
  de workload.
- Projete observabilidade para logs, métricas e traces correlacionados.
- Declare limites, pedidos de recurso, timeouts e comportamento de escala.
- Valide rollback ou roll-forward, migração e compatibilidade entre versões.

