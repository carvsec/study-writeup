# Tcpdump: The Basics — TryHackMe

**Data:** 31/07/2026 | **Categoria:** Network Analysis

## O que aprendi
Explorei o tcpdump como ferramenta CLI nativa do Linux para captura rápida de pacotes, ideal para ambientes headless e servidores remotos. Compreendi parâmetros essenciais como -i (interface), -c (limite de pacotes), -w/-r (gravação e leitura de arquivos .pcap), além da desativação de resolução de nomes com -n e -nn. Estudei a aplicação de filtros BPF (Berkeley Packet Filter) para focar em IPs, portas e protocolos, bem como o controle de verbosidade (-v, -vv, -vvv) e inspeção de payloads em ASCII (-A) e Hexadecimal (-X).

## Prática
Capturei e filtrei pacotes diretamente na interface de rede via linha de comando:
```bash
sudo tcpdump -i eth0 -c 10 -nn
sudo tcpdump -i eth0 port 80 -w captura_web.pcap
tcpdump -r captura_web.pcap -A
sudo tcpdump -nn src 192.168.1.50 and dst port 22
```

## Referência
https://tryhackme.com/room/tcpdump
