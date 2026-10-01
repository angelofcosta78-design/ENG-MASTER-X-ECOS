# Módulo 25 — TITAN Testing, Validation & Evidence

**Versão:** 14.0.0  
**Status:** Engineering Baseline

## Objetivo
Centralizar testes técnicos, de software, segurança, IA, resiliência e aceitação, produzindo um Acceptance Evidence Pack verificável.

## Pirâmide de testes
| Nível | Objetivo |
|---|---|
| Unit | funções, regras e cálculos |
| Contract | APIs, eventos e schemas |
| Dimensional | unidades e equações |
| Integration | sistemas internos e externos |
| Regression | estabilidade após mudanças |
| Adversarial | injection, bypass e dados maliciosos |
| Hallucination | claims sem evidência |
| Load | throughput e latência |
| Chaos | falhas e recuperação |
| Security | SAST, DAST, secrets e IAM |
| UAT | aceitação por usuários de engenharia |

## Evidence Pack
```yaml
acceptance_evidence_pack:
  release: "14.0.0-rc1"
  code_version: "git-sha"
  environment: staging
  datasets:
    - dataset_id: DATA-001
      hash: "sha256:..."
  suites:
    calculation: PASS
    normative: PASS
    qa: PASS
    security: PASS
    resilience: PASS
    performance: PASS
    ai: REVIEW_REQUIRED
    uat: PENDING
  approved_by: null
```

## Regras
- teste sem ambiente e versão não é evidência suficiente;
- falhas devem ser preservadas no pacote;
- testes críticos precisam de reexecução ou justificativa;
- resultados não podem ser editados manualmente;
- critérios de aceite devem existir antes da execução.

## Critérios de aceite
- nenhuma falha crítica aberta;
- cobertura de testes críticos aprovada;
- evidências assinadas;
- reprodutibilidade confirmada;
- UAT concluído;
- aprovação formal de release.
