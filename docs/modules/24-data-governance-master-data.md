# Módulo 24 — TITAN Data Governance & Master Data

**Versão:** 14.0.0  
**Status:** Engineering Baseline

## Objetivo
Garantir que dados de ativos, projetos, requisitos, normas, fornecedores e documentos sejam identificáveis, consistentes, versionados e governados.

## Responsabilidades
- catálogo de dados;
- data ownership;
- qualidade e classificação;
- master data de ativos;
- resolução de duplicidade;
- data lineage;
- contratos de dados;
- retenção e descarte;
- reconciliação entre sistemas.

## Identidade canônica
```yaml
master_asset:
  asset_id: ASSET-001
  canonical_name: "Pump P-101"
  source_mappings:
    sap: MAT-001
    plm: PART-001
    eam: ASSET-001
    scada: TAG-P101
  owner: operations
  status: active
```

## Qualidade de dados
Dimensões mínimas:

- completude;
- validade;
- unicidade;
- consistência;
- atualidade;
- proveniência;
- conformidade de unidade.

## Regras
- nenhum sistema externo é fonte absoluta para todos os domínios;
- conflitos devem gerar reconciliação explícita;
- dado ausente não deve ser substituído silenciosamente;
- dados mestres têm proprietário;
- toda alteração relevante possui aprovação e histórico.

## Critérios de aceite
- catálogo publicado;
- owners definidos;
- regras de qualidade implementadas;
- duplicidades tratadas;
- lineage disponível;
- reconciliação testada.
