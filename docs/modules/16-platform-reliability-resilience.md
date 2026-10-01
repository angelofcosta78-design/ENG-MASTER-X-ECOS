# Módulo 16 — TITAN Platform Reliability & Resilience

**Versão:** 14.0.0  
**Status:** Engineering Baseline

## Objetivo
Garantir disponibilidade, recuperação, consistência e continuidade operacional do TITAN.

## Responsabilidades
- alta disponibilidade e failover;
- backup, restore e disaster recovery;
- RPO/RTO por criticidade;
- circuit breaker, retry e backpressure;
- checkpoints e replay de eventos;
- degradação controlada e fail-closed;
- chaos engineering;
- gestão de incidentes.

## Baseline
| Recurso | Requisito |
|---|---|
| Serviços stateless | mínimo de 3 réplicas em produção |
| Broker | mínimo de 3 nós, replicação ≥3 |
| Banco transacional | HA, PITR e restore testado |
| Artefatos emitidos | armazenamento versionado e imutável |
| RPO crítico | definido formalmente; referência inicial ≤15 min |
| RTO crítico | definido formalmente; validado em exercício |

## Estados de falha
```text
HEALTHY → DEGRADED → RECOVERING → RESTORED
                         └──────→ BLOCKED
```

Falhas em cálculo, evidência, aprovação ou persistência crítica devem bloquear publicação. Falhas não críticas podem usar modo degradado, sempre com alerta e registro.

## Recuperação
1. detectar incidente;
2. preservar estado e eventos;
3. interromper efeitos perigosos;
4. executar failover ou replay;
5. reconciliar fontes de verdade;
6. validar integridade;
7. reabrir operações;
8. registrar causa raiz e ação preventiva.

## Critérios de aceite
- restore real executado e documentado;
- failover validado;
- replay idempotente testado;
- nenhum evento crítico perdido;
- RPO/RTO medidos e aprovados;
- chaos tests sem bypass de governança.
