---
data: 2026-08-10
tags: [cyber, tryhackme, logs, soc-l1]
plataforma: TryHackMe
sala: Logs Fundamentals & Centralization
modulo: Cyber Security 101
---

# Logs Fundamentals

## THM: Logs Fundamentals & Centralization

### 1. O que são Logs e Sua Importância
- **Logs de Sistema**: Registros cronológicos de eventos gerados por sistemas operacionais, aplicativos e dispositivos de rede.
- **Importância Crítica**: Essenciais para a auditoria forense, conformidade e para a descoberta rápida de atividades maliciosas em um ambiente corporativo.

### 2. Tipos de Logs Comuns
- **Logs de Autenticação** ([[Authentication]]): Registram tentativas de login bem-sucedidas e falhas, essenciais para detectar ataques de força bruta.
- **Logs de Sistema** ([[Syslog]]): Mensagens geradas pelo kernel e serviços essenciais do sistema operacional.
- **Logs de Aplicação** ([[Application Logs]]): Eventos específicos gerados por softwares e aplicações web em execução.

### 3. Centralização e Armazenamento
- **Gerenciamento Centralizado**: Envio de logs de múltiplas fontes para um repositório seguro e unificado.
- **Prevenção de Tampering**: Evita que um invasor apague os logs locais após comprometer um host individual.

### 4. Localização de Logs no Linux
Locais comuns onde o Linux armazena logs:
- `/var/log/httpd`: contém logs de requisição/resposta HTTP e erros (equivalente a `/var/log/apache` em algumas distros)
- `/var/log/cron`: eventos relacionados a jobs do cron
- `/var/log/auth.log` e `/var/log/secure`: armazenam logs relacionados à autenticação
- `/var/log/kern`: armazena eventos relacionados ao kernel

**Exemplo de cron log:**
```
May 28 13:04:20 ebr crond[2843]: /usr/sbin/crond 4.4 dillon's cron daemon, started with loglevel notice
May 28 13:04:20 ebr crond[2843]: no timestamp found (user root job sys-hourly)
Jun 13 07:46:22 ebr crond[3592]: unable to exec /usr/sbin/sendmail: cron output for user root job sys-daily to /dev/null
```

### 5. Web Server Logs
É importante monitorar todas as requisições/respostas que entram e saem do web server, pra identificar qualquer tentativa de ataque web. No Linux, os locais comuns pra logs do Apache são `/var/log/apache` ou `/var/log/httpd`.

### 6. Exemplos de Comandos e Análise
```bash
# Visualizar logs de autenticação no Linux
cat /var/log/auth.log | grep "Failed password"

# Acompanhar logs em tempo real
tail -f /var/log/syslog
```

## O que fiz no lab
[Descreva aqui o que você configurou/analisou nas tasks práticas da sala — ex: quais logs você examinou, o que identificou nos Windows Event Logs e nos Web Server Access Logs, algum IOC que encontrou no exercício]

## Minha análise
[O que fez mais sentido pra você / o que ainda ficou nebuloso — ex: entendi bem a diferença entre os tipos de log, mas ainda quero praticar mais a diferença entre log rotation e retenção]

---

## Conexões com a Trilha SOC L1
- **Módulo Pai:** [[Cyber Security 101]]
- **Próxima Nota:** [[THM - SIEM Fundamentals]]
- **Conceitos Relacionados:** [[Authentication]], [[Syslog]], [[Application Logs]]
