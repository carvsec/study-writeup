# Networking Concepts & Essentials — TryHackMe

**Data:** 20/07/2026 | **Categoria:** Networking Basics

## O que aprendi
Compreendi os fundamentos de redes, diferenciando o modelo teórico OSI (7 camadas) do modelo prático TCP/IP (4 camadas). Estudei o endereçamento físico (MAC Address na camada 2) e lógico (Endereço IP na camada 3), além de portas essenciais como HTTP (80), HTTPS (443) e SSH (22). Diferenciei a atuação de um Switch (conexão interna na LAN via MAC) e de um Roteador (comunicação entre redes distintas via IP).

## Prática
Utilizei comandos de diagnóstico e verificação de rede no terminal para testar conectividade, rotas e mapeamento de endereços:
```bash
ping 8.8.8.8
tracert tryhackme.com
ipconfig /all
arp -a
telnet 192.168.1.1 80
```

## Referência
https://tryhackme.com/room/networkingconcepts
https://tryhackme.com/room/networkingessentials
