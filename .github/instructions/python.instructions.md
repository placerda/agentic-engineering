---
applyTo: "**/*.py,**/*.pyi"
---

# Python

- A configuração executável do repositório é a fonte de verdade. Respeite
  `pyproject.toml`, Ruff, o formatador, o verificador de tipos e os testes já
  adotados. Não substitua escolhas locais por preferências genéricas.
- Siga PEP 8 para legibilidade, nomes, imports, espaçamento e organização, salvo
  quando a configuração do projeto definir uma convenção compatível diferente.
- Aplique PEP 20 como critério de decisão: seja explícito, simples e legível;
  não esconda erros; diante de ambiguidade relevante, recuse-se a adivinhar.
- Siga PEP 257 em módulos, classes, funções e métodos públicos. Docstrings devem
  explicar comportamento, contrato, argumentos, retorno, efeitos colaterais,
  exceções e restrições quando essas informações forem úteis. Não repita a
  assinatura nem descreva o óbvio.
- Prefira tipos precisos, estruturas pequenas e interfaces explícitas. Evite
  `Any`, casts e exceções amplas sem justificativa.
- Isole relógio, aleatoriedade, sistema de arquivos, rede e provedores para que a
  lógica de negócio seja testável de forma determinística.
- Execute Ruff, formatador, verificação de tipos e testes conforme os comandos do
  repositório. Não introduza ferramentas novas apenas para satisfazer esta regra.

Para orientação detalhada, carregue a skill `python-development`.

