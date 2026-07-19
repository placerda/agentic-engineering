---
name: python-development
description: Orienta implementação e revisão Python alinhadas a PEP 8, PEP 20, PEP 257 e às ferramentas do repositório. Use ao alterar arquivos Python.
---

# Desenvolvimento Python

Leia `../engineering-principles/references/python-pep-guidance.md`. Depois:

1. Descubra versão do Python, gerenciador, `pyproject.toml` e comandos reais.
2. Preserve tipos, API pública e comportamento.
3. Aplique docstrings onde o contrato público precisa delas.
4. Isole efeitos externos e cubra regras com testes determinísticos.
5. Execute linter, formatador, tipos e testes já configurados.

Não imponha um limite de linha ou ferramenta diferente da configuração do
projeto. Não use `Any`, cast ou captura ampla para contornar um erro de projeto.

