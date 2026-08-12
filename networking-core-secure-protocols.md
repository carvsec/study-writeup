# Networking Core & Secure Protocols

**Data:** 25/07/2026 | **Categoria:** Networking Basics

## O que aprendi
Estudei protocolos essenciais de infraestrutura como o DHCP atribuição automática de IPs e o DNS tradução de domínios para IPs. Analisei a camada de transporte comparando o TCP orientado à conexão, confiável, com 3-Way Handshake e controle por flags com o UDP focado em velocidade e baixa latência. Examinei a migração de protocolos legados em texto puro cleartext como FTP, HTTP, Telnet, POP3/IMAP para suas versões seguras SFTP, HTTPS, SSH, SMTPS, POP3S/IMAPS, compreendendo o funcionamento do TLS/SSL e da Cadeia de Confiança de Certificados Digitais.

## Prática
Realizei consultas de registros DNS e testes de conexão segura com inspeção de certificados via terminal:
```bash
nslookup instagram.com
dig instagram.com
openssl s_client -connect instagram.com:443
```

## Referência
https://tryhackme.com/room/networkingcoreprotocols
https://tryhackme.com/room/networkingsecureprotocols
