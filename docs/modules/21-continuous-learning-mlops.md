# Módulo 21 — TITAN Continuous Learning & MLOps

**Versão:** 14.0.0  
**Status:** Engineering Baseline

## Objetivo
Governar o ciclo de vida de modelos, prompts, embeddings, regras e componentes de IA sem contaminar decisões aprovadas.

## Componentes
- dataset registry;
- feature store;
- model registry;
- prompt/template registry;
- evaluation service;
- drift detection;
- deployment controller;
- rollback;
- monitoramento pós-produção.

## Ciclo de promoção
```text
EXPERIMENTAL
  → VALIDATED
  → SECURITY_REVIEWED
  → ENGINEERING_APPROVED
  → SHADOW
  → LIMITED_RELEASE
  → PRODUCTION
  → RETIRED
```

## Regras de aprendizado
- aprendizado automático nunca altera regra mandatória em produção;
- novos modelos iniciam em shadow mode;
- modelos devem ser comparados com baseline;
- todo dataset possui origem, licença e classificação;
- drift crítico bloqueia decisões dependentes;
- rollback deve ser testado.

## Avaliações obrigatórias
- grounding;
- hallucination;
- adversarial prompts;
- segurança;
- regressão;
- viés;
- latência;
- qualidade por disciplina;
- comparação contra casos de referência.

## Critérios de aceite
- registry operacional;
- avaliação reproduzível;
- aprovação formal de versão;
- rollback validado;
- monitoramento de drift ativo;
- nenhuma mudança silenciosa em produção.
