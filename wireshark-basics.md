# Wireshark: The Basics 

**Data:** 30/07/2026 | **Categoria:** Network Analysis

## O que aprendi
Aprendi a utilizar o Wireshark como analisador de protocolos de rede para captura em tempo real e análise pós-incidente utilizando arquivos .pcap e .pcapng. Dominei a aplicação de Display Filters baseados em sintaxes de IP (ip.addr), portas e protocolos (icmp, http), combinados com operadores lógicos (and, or, not). Estudei recursos como o Follow Stream para reconstrução de sessões e o uso do painel estatístico (Protocol Hierarchy e Endpoints).

## Prática
Apliquei filtros de exibição avançados no Wireshark para isolar tráfego HTTP, resoluções de nomes e excluir tráfego local:
```
http.request.method == "GET" or http.request.method == "POST"
dns
ip.addr == 192.168.1.50 and not ip.src == 127.0.0.1
```

## Referência
https://tryhackme.com/room/wiresharkthebasics
