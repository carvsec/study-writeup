---
data: 2026-08-10
tags: [cyber, tryhackme, siem, soc-l1]
plataforma: TryHackMe
sala: SIEM Fundamentals
modulo: Cyber Security 101
---

# SIEM (Security Information and Event Management)

## THM: SIEM Fundamentals

### 1. O Conceito de SIEM
- **SIEM (Security Information and Event Management)**: Plataforma centralizada que combina gerenciamento de informações de segurança (SIM) e gerenciamento de eventos de segurança (SEM).
- **Propósito Principal**: Agregar, normalizar e correlacionar logs de toda a infraestrutura em tempo real para detecção de ameaças.

### 2. Coleta e Normalização de Dados
- **Coleta** ([[Collection]]): Agregação de dados de firewalls, endpoints, servidores e sistemas de rede através de agentes ou syslog.
- **Normalização** ([[Normalization]]): Padronização de diferentes formatos de logs brutos em um esquema coeso para facilitar a busca e a correlação.

#### Fontes de Log (Log Sources)
- **Host-Centric Log Sources**: eventos que ocorreram dentro ou relacionados ao host (Windows, Linux, servidores). Exemplos: usuário acessando um arquivo, tentativa de autenticação, execução de processo, adição/edição/remoção de chave de registro, execução de PowerShell.
- **Network-Centric Log Sources**: gerados quando hosts se comunicam entre si ou acessam a internet. Geradores: firewalls, IDS/IPS, roteadores. Exemplos: conexão SSH, arquivo acessado via FTP, tráfego web, acesso a recursos via VPN, compartilhamento de arquivo em rede.

#### Métodos de Log Ingestion
Cada solução SIEM tem sua própria forma de ingerir logs. Métodos comuns:
1. **Agent / Forwarder**: ferramenta leve instalada no endpoint (ex: forwarder do Splunk) configurada pra capturar e enviar logs importantes ao servidor SIEM.
2. **Syslog**: protocolo amplamente usado pra coletar dados de vários sistemas (web servers, bancos de dados etc.) e enviar em tempo real ao destino centralizado.
3. **Manual Upload**: algumas soluções (Splunk, ELK) permitem ingerir dados offline pra análise rápida.
4. **Port-Forwarding**: o SIEM pode ser configurado pra escutar uma porta específica, e os endpoints encaminham os dados pra essa porta.

### 3. Regras de Correlação e Alertas
- **Correlação de Eventos** ([[Correlation]]): Capacidade de cruzar múltiplos eventos aparentemente desconectados para identificar padrões complexos de ataque.
- **Geração de Alertas** ([[Alerting]]): Disparo automatizado de notificações para os analistas do [[SOC]] quando um comportamento suspeito é identificado.

### 4. Componentes Principais
- **Dashboard / Painel de Controle**: Visualização gráfica consolidada de métricas de segurança, incidentes e integridade dos agentes.
- **Motor de Busca e Consulta** ([[Querying]]): Ferramentas de linguagem de consulta para investigação forense rápida de logs históricos.

## O que fiz no lab
[Descreva o que você fez na task de Lab Work — ex: qual painel/query você explorou, que tipo de alerta ou evento você conseguiu correlacionar]

## Minha análise
[O que fez mais sentido / o que ainda é nebuloso — ex: entendi o fluxo coleta→normalização→correlação, mas ainda quero entender melhor como o SIEM prioriza alertas em alto volume sem gerar fadiga de alerta]

---

## Conexões com a Trilha SOC L1
- **Módulo Pai:** [[Cyber Security 101]]
- **Próxima Nota:** [[THM - Firewall Fundamentals]]
- **Conceitos Relacionados:** [[Collection]], [[Normalization]], [[Correlation]], [[SOC]]
