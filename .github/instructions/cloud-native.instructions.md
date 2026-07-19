---
applyTo: "**/Dockerfile,**/Dockerfile.*,**/docker-compose*.yml,**/docker-compose*.yaml,deploy/**,deployment/**,infra/**,k8s/**,helm/**,charts/**"
---

# Aplicações implantáveis e serviços cloud-native

Estas regras se aplicam a serviços e artefatos de implantação, não a toda
biblioteca ou script.

- Mantenha dependências explícitas e reproduzíveis.
- Injete configuração por ambiente e mantenha segredos fora do código e da
  imagem.
- Trate banco, fila, cache e serviços externos como recursos substituíveis por
  configuração e contratos.
- Separe build, release e execução. O mesmo artefato deve avançar entre
  ambientes.
- Prefira processos sem estado; persista estado em serviços apropriados.
- Exponha serviço por porta quando aplicável e dimensione por processos
  independentes.
- Projete inicialização e encerramento rápidos, idempotência e recuperação após
  interrupção.
- Reduza diferenças entre desenvolvimento e produção.
- Emita logs estruturados como fluxo de eventos para coleta externa.
- Execute tarefas administrativas como processos versionados e auditáveis.

Carregue a skill `cloud-native-service` para decisões de serviço, implantação ou
operação.

