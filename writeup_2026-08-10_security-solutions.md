# Security Solutions + Logs Fundamentals 

**Data:** 10/08/2026
**Categoria:** Defensive Security / Security Solutions

## O que aprendi
Hoje fechei o bloco de Security Solutions do Cyber 101: como logs se transformam em alertas úteis via SIEM, e as três camadas clássicas de defesa de rede — firewall (filtra tráfego), IDS (detecta comportamento suspeito) e scanner de vulnerabilidades (encontra falhas antes que sejam exploradas). Dá pra ver como as peças se conectam: sem log não tem SIEM, sem SIEM não tem alerta, sem alerta não tem triagem.

## Conceitos-chave

### Logs Fundamentals
- **Tipos de log**: eventos de sistema, aplicação e segurança/auditoria têm propósitos diferentes na investigação
- **Windows Event Logs**: estrutura de eventos do Windows (Event ID, Source, Level) usada pra rastrear ações no SO
- **Web server access logs**: cada requisição HTTP vira uma linha de log — IP, timestamp, método, status code — base pra identificar tentativas de exploração via endpoint

### Introduction to SIEM
- **Problema que o SIEM resolve**: logs existem em toneladas espalhadas por sistemas diferentes ("logs everywhere, answers nowhere") — o SIEM centraliza e correlaciona
- **Log sources e ingestion**: como diferentes fontes (firewall, servidores, endpoints) alimentam o SIEM
- **Processo de alerta**: da ingestão de log até a análise que vira um alerta acionável para o analista

### Firewall Fundamentals
- **Propósito**: controlar o que entra/sai da rede com base em regras
- **Tipos**: packet-filtering, stateful, next-gen (NGFW)
- **Regras**: lógica de permitir/bloquear por IP, porta, protocolo
- **Prática**: Windows Defender Firewall (GUI) e Linux iptables (linha de comando)

### IDS Fundamentals
- **Diferença de firewall**: IDS detecta e alerta, não bloqueia (isso seria IPS)
- **Tipos**: baseado em assinatura vs baseado em anomalia; NIDS (rede) vs HIDS (host)
- **Snort**: ferramenta prática de IDS, uso de regras pra detectar tráfego malicioso

### Vulnerability Scanner Overview
- **CVE**: identificador padronizado de uma vulnerabilidade conhecida
- **CVSS**: score que mede a severidade de uma CVE (0-10)
- **OpenVAS**: ferramenta open-source de scan de vulnerabilidades, usada no exercício prático

## Comando/ferramenta que usei
`iptables` — regras de firewall em Linux
`Snort` — engine de detecção baseada em regras
`OpenVAS` — scanner de vulnerabilidades, mapeamento de CVE/CVSS

## Dúvida ou ponto que ainda preciso reforçar
Quero praticar mais a leitura de uma regra Snort na prática (sintaxe ainda não é automática) e entender melhor como um SIEM prioriza alertas quando há volume alto (o que evita fadiga de alerta).
