# Logs Fundamentals & Centralization — 

**Data:** 09/08/2026 | **Categoria:** Defensive Security

## O que aprendi
Logs são a matéria-prima de qualquer investigação em SOC. Sem log centralizado, não tem como provar o que aconteceu nem correlacionar eventos entre fontes diferentes.

## Prática
Analisei logs em locais reais do Linux (`/var/log/auth.log`, `/var/log/cron`, `/var/log/httpd`) e pratiquei os comandos:
```bash
cat /var/log/auth.log | grep "Failed password"
tail -f /var/log/syslog
```
Também analisei Windows Event Logs e Web Server Access Logs pra identificar padrões de tentativa de acesso.

## Referência
https://tryhackme.com/room/logsfundamentals