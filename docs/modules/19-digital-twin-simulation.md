# Módulo 19 — TITAN Digital Twin & Simulation

**Versão:** 14.0.0  
**Status:** Engineering Baseline

## Objetivo
Representar e simular comportamento de ativos, sistemas e processos para apoiar análise, projeto, manutenção e cenários de mudança.

## Diferença para Digital Thread
- **Digital Thread:** rastreia objetos, eventos, decisões e ciclo de vida.
- **Digital Twin:** representa estados e comportamento físico ou operacional.

## Componentes
- modelo de ativo;
- modelo físico ou estatístico;
- dados de calibração;
- interface de simulação;
- cenários what-if;
- comparação modelo versus realidade;
- controle de versão do modelo.

## Contrato de modelo
```yaml
digital_twin:
  twin_id: TWIN-001
  asset_id: ASSET-001
  model_version: 1.0.0
  model_type: hybrid_physical_statistical
  calibration_dataset: DATA-001
  validity_range:
    temperature_c: [0, 120]
    flow_m3_h: [10, 500]
  validation:
    status: verified
    evidence_ids: [EVD-001]
```

## Regras
- simulação não substitui ensaio obrigatório;
- modelo fora da faixa de validade deve retornar `REVIEW_REQUIRED`;
- toda calibração gera nova versão;
- diferenças entre modelo e operação real alimentam investigação;
- resultados críticos exigem validação independente.

## Critérios de aceite
- modelo validado contra dados reais;
- faixa de validade documentada;
- erro de predição medido;
- cenários reproduzíveis;
- rollback de modelo disponível.
