# Relatório de Prontidão Técnica: Onboarding SecOps
**Disciplina:** Engenharia de Produto de Software (FGA0316) - 2026.1
**Aluno:** Sebastián Héctor Zuzunaga Rosado | **Matrícula:** 211006957

## 1. Configuração do Ambiente (Zero Trust & Isolamento)
Conforme as diretrizes de Soberania Técnica, as seguintes configurações foram aplicadas:
- [x] **Python 3.12:** Instalado e verificado.
- [x] **Poetry:** Configurado para criar `.venv` dentro do projeto (`virtualenvs.in-project true`).
- [x] **Determinismo:** Arquivos `pyproject.toml` e `poetry.lock` gerados com sucesso.

## 2. Logs de Auditoria e Qualidade (Security Gate)
Abaixo constam os resumos das execuções dos comandos de segurança:

### 2.1. Auditoria Estática (Bandit)
```
Code scanned:
        Total lines of code: 626071
        Total lines skipped (#nosec): 3

Run metrics:
        Total issues (by severity):
                Undefined: 0
                Low: 2765
                Medium: 156
                High: 28
        Total issues (by confidence):
                Undefined: 0
                Low: 16
                Medium: 112
                High: 2821
Files skipped (0):
```

*Comando: `poetry run bandit -r .`*

### 2.2. Verificação de Dependências (Safety)
```
+================================================================+

 REPORT 

  Safety v3.7.0 is scanning for
  Vulnerabilities...
  Scanning dependencies in your environment:

  -> /home/sebazac/Sebastian/EPS/Repos/EPS-
  Desafio01-SebastianZuzunaga/.venv/lib/python3.12/site-packages

  Using open-source vulnerability database
  Found and scanned 46 packages
  Timestamp 2026-03-30 20:01:10
  0 vulnerabilities reported
  0 vulnerabilities ignored
+================================================================+

 No known security vulnerabilities reported. 

+================================================================+
```

*Comando: `poetry run safety check`*

### 2.3. Qualidade e Conformidade (Ruff)
```

All checks passed!
```

*Comando: `poetry run ruff check .`*

## 3. Evidência de Integração Contínua (CI)
O pipeline automatizado foi executado com sucesso no GitHub Actions:
- **Link da Action de Sucesso:** https://github.com/sebazac332/EPS-Desafio01-SebastianZuzunaga/actions/runs/23769512047/job/69257351378

## 4. Declaração de Soberania Técnica (CISSP Domain 8)
Eu, Sebastián Héctor Zuzunaga Rosado, declaro que auditei manualmente as ferramentas e dependências deste projeto. Confirmo que o código gerado via IA (GitHub Copilot) passou pela minha revisão humana (*Human-in-the-loop*), garantindo que não há vazamento de segredos ou falhas lógicas críticas antes da migração para o ecossistema da PCDF.

---