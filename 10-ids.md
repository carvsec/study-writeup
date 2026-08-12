# IDS & IPS Fundamentals

**Data:** 10/08/2026 | **Categoria:** Security Solutions

## O que aprendi
IDS é passivo (detecta e alerta), IPS é ativo (bloqueia em tempo real). Métodos de detecção: signature-based (rápido, cego a zero-day), anomaly-based (detecta zero-day, mais falso positivo) e hybrid (combina os dois). Deployment em HIDS (por host) ou NIDS (rede toda, visão centralizada).

## Prática
Rodei Snort em modo NIDS pra detectar tráfego ICMP de loopback:
```bash
sudo snort -q -l /var/log/snort -i lo -A alert_fast -c /etc/snort/snort.lua
```
Resultado: alerta "Loopback Ping Detected" gerado corretamente, confirmando a regra funcionando. Também rodei o Snort contra um arquivo PCAP pra simular análise forense de tráfego histórico:
```bash
sudo snort -q -l /var/log/snort -r Task.pcap -A alert_fast -c /etc/snort/snort.lua
```

## Referência
https://tryhackme.com/room/idsfundamentals