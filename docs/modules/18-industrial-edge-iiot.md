# Módulo 18 — TITAN Industrial Edge & IIoT

**Versão:** 14.0.0  
**Status:** Engineering Baseline

## Objetivo
Conectar o TITAN a equipamentos, sensores, SCADA, historiadores e redes industriais com segurança, baixa latência e operação resiliente offline.

## Protocolos
- OPC UA;
- MQTT com TLS;
- Kafka industrial;
- APIs de historiadores;
- conectores específicos de fabricantes somente quando aprovados.

## Arquitetura
```text
Sensor/PLC
  → Edge Gateway
  → Normalização e validação
  → Buffer local
  → Event Bus
  → TITAN Core
  → Digital Thread / Asset Intelligence
```

## Funções do Edge Gateway
- descoberta e mapeamento de tags;
- validação de faixa e qualidade;
- timestamp confiável;
- buffering offline;
- compressão e agregação;
- autenticação de dispositivo;
- sincronização após reconexão;
- execução de inferência aprovada localmente.

## Regras de segurança
- rede OT separada de IT;
- deny-by-default;
- nenhuma escrita em controle sem workflow autorizado;
- comandos operacionais críticos não são gerados autonomamente;
- dados inválidos são marcados, não corrigidos silenciosamente;
- cada tag possui origem, unidade, qualidade e timestamp.

## Critérios de aceite
- operação offline testada;
- perda e duplicidade de eventos tratadas;
- qualidade de dados monitorada;
- latência e throughput medidos;
- nenhum comando crítico liberado sem autorização humana apropriada.
