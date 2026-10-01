# Módulo 17 — TITAN Observability & SRE

**Versão:** 14.0.0  
**Status:** Engineering Baseline

## Objetivo
Tornar o TITAN mensurável, diagnosticável e operável por equipes de engenharia e operações.

## Telemetria obrigatória
- logs estruturados em JSON;
- métricas Prometheus/OpenMetrics;
- traces OpenTelemetry;
- correlação por `trace_id`, `mission_id`, `project_id` e `decision_id`;
- dashboards operacionais e de qualidade;
- alertas acionáveis.

## SLI/SLO
| Serviço | SLI | SLO inicial |
|---|---|---|
| API | disponibilidade | ≥99,9% |
| Missões | conclusão sem falha técnica | ≥99% |
| Cálculos | reprodutibilidade | 100% dos críticos |
| Eventos | entrega persistida | ≥99,99% |
| QA | execução de gates | 100% das missões elegíveis |
| Knowledge Graph | latência p95 | definida por consulta |

## Métricas essenciais
```text
titan_missions_total
titan_missions_failed_total
titan_missions_blocked_total
titan_calculation_failures_total
titan_unsupported_claims_total
titan_normative_conflicts_total
titan_qa_failures_total
titan_event_lag
titan_backup_restore_status
titan_approval_queue_depth
titan_decision_confidence
```

## Alertas críticos
- perda de eventos;
- divergência entre fontes de verdade;
- aumento de alegações sem evidência;
- falha de backup;
- uso de norma expirada;
- cálculo não reproduzível;
- bypass de gate;
- deriva de modelo;
- falha de autorização.

## Error budget
O time pode consumir error budget somente em falhas operacionais não relacionadas à segurança, integridade de dados ou decisões críticas. Um incidente de segurança ou integridade suspende releases não essenciais.

## Critérios de aceite
- dashboards publicados;
- alertas testados;
- runbooks vinculados aos alertas;
- traces ponta a ponta disponíveis;
- SLOs medidos em staging e produção controlada.
