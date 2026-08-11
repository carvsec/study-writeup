---
data: 2026-08-10
tags: [cyber, tryhackme, ids, soc-l1]
plataforma: TryHackMe
sala: IDS & IPS Fundamentals
modulo: Cyber Security 101
---

# IDS Fundamentals (Intrusion Detection System)

## THM: IDS & IPS Fundamentals

### 1. O que é um Sistema de Detecção de Intrusão
- **IDS (Intrusion Detection System)**: Ferramenta passiva projetada para monitorar o tráfego de rede ou eventos de host em busca de atividades maliciosas ou violações de políticas.
- **Visibilidade**: Foco em alertar a equipe de segurança sem interromper o fluxo de tráfego diretamente.

### 2. IDS vs. IPS (Detecção vs. Prevenção)
- **IDS**: Atua de forma passiva, gerando alertas e logs para investigação posterior.
- **IPS (Intrusion Prevention System)**: Atua de forma ativa, bloqueando ou mitigando o tráfego malicioso em tempo real ao identificá-lo.

### 3. Deployment Modes
IDS pode ser implantado das seguintes formas:
- **Host Intrusion Detection System (HIDS)**: soluções instaladas individualmente nos hosts, responsáveis por detectar ameaças associadas àquele host específico. Dão visibilidade detalhada da atividade do host, mas são difíceis de gerenciar em redes grandes (consomem recursos e exigem gerenciamento em cada host).
- **Network Intrusion Detection System (NIDS)**: soluções baseadas na rede, cruciais pra detectar atividades maliciosas em toda a rede, independente de host específico. Monitoram o tráfego de todos os hosts envolvidos e dão uma visão centralizada de todas as detecções da rede.

### 4. Métodos de Detecção (Detection Modes)
- **Signature-Based IDS** ([[Signature-based]]): cada ataque tem um padrão único (assinatura) preservado no banco de dados do IDS. Quanto mais forte o banco de assinaturas, mais eficiente a detecção de ameaças conhecidas — porém é incapaz de detectar ataques zero-day, já que eles não têm assinatura prévia salva.
- **Anomaly-Based IDS** ([[Anomaly-based]]): aprende primeiro o comportamento normal (baseline) da rede/sistema e detecta qualquer desvio dele. Consegue detectar zero-days por não depender de assinaturas — porém pode gerar muitos falsos positivos, já que comportamento legítimo incomum pode ser confundido com malicioso. Dá pra reduzir falsos positivos fazendo fine-tuning (definindo manualmente o que é comportamento normal).
- **Hybrid IDS**: combina os dois métodos pra aproveitar as forças de cada um — usa detecção por assinatura pra ameaças já conhecidas e detecção por anomalia quando encontra algo novo.

> Signature-based detecta ameaças rapidamente mas cobre só o que já é conhecido (bom pra superfície de ameaça pequena); anomaly-based e hybrid ajudam a detectar ameaças modernas zero-day, mas com maior overhead de processamento.

### 5. Snort — Ferramenta de IDS
Uma das soluções IDS open-source mais usadas, criada em 1998. Usa detecção baseada em assinatura e anomalia pra identificar ameaças conhecidas, definidas nos arquivos de regra do Snort. Vem com várias regras pré-instaladas, mas também é possível criar regras customizadas ou desabilitar regras que não sejam relevantes.

**Modos do Snort:**

| Modo | Descrição | Caso de uso |
|---|---|---|
| **Packet Sniffer Mode** | Lê e exibe pacotes de rede sem realizar análise sobre eles | Diagnosticar problemas de performance de rede |
| **Packet Logging Mode** | Detecta em tempo real e exibe alertas no console; permite logar o tráfego como arquivo PCAP pra análise posterior | Investigação forense de ataques de rede, root cause analysis |
| **NIDS Mode** | Modo principal — monitora tráfego em tempo real e aplica os arquivos de regra pra identificar padrões de ataque conhecidos, gerando alertas | Monitoramento proativo de rede/sistemas |

**Formato de uma regra Snort:**
```
alert icmp any any -> $HOME_NET any (msg:"Ping Detected"; sid:10001; rev:1;)
```
- `alert` → Action (o que fazer ao detectar)
- `icmp` → Protocol
- `any any` → Source IP / Source port
- `$HOME_NET any` → Destination IP / Destination port
- `msg` → mensagem do alerta (Rule metadata)
- `sid` → Signature ID (identificador único da regra)
- `rev` → Rule revision (versão da regra)

## O que fiz no lab
Iniciei a máquina do lab e explorei o diretório de configuração do Snort (`/etc/snort`), com os arquivos `snort.conf`, `snort.lua` (arquivo-chave de configuração), pasta `rules/` e outros.

Rodei o Snort em modo de detecção com o comando:
```bash
sudo snort -q -l /var/log/snort -i lo -A alert_fast -c /etc/snort/snort.lua
```
Ao pingar o loopback do host, o Snort gerou o alerta esperado:
```
[**] [1:1000001:1] "Loopback Ping Detected" [**] [Priority: 0] {ICMP} 127.0.0.1 -> 127.0.0.1
```
Isso confirmou que a regra estava funcionando corretamente.

Também rodei o Snort contra um arquivo PCAP (tráfego histórico) pra simular uma investigação forense:
```bash
sudo snort -q -l /var/log/snort -r Task.pcap -A alert_fast -c /etc/snort/snort.lua
```

## Minha análise
[O que fez mais sentido / o que ainda é nebuloso — ex: entendi a diferença IDS x IPS, mas a sintaxe de regra do Snort ainda não é automática pra mim]

---

## Conexões com a Trilha SOC L1
- **Módulo Pai:** [[Cyber Security 101]]
- **Próxima Nota:** [[THM - Vulnerability Management Overview]]
- **Conceitos Relacionados:** [[Signature-based]], [[Anomaly-based]], [[IDS]], [[IPS]]
