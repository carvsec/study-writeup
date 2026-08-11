---
data: 2026-08-10
tags: [cyber, tryhackme, vulnerability, openvas, soc-l1]
plataforma: TryHackMe
sala: Vulnerability Management Overview
modulo: Cyber Security 101
---

# Vulnerability Scanner Overview

## THM: Vulnerability Management Overview

### 1. O Papel dos Scanners de Vulnerabilidade
- **Scanner de Vulnerabilidades**: Ferramenta automatizada para auditar ativos de rede, servidores e aplicações em busca de falhas conhecidas, portas abertas e configurações incorretas.
- **Abordagem Proativa**: Permite identificar e corrigir brechas de segurança antes que atores maliciosos possam explorá-las.

### 2. Ferramentas de Vulnerability Scanning

Existem várias ferramentas pra scan automatizado de vulnerabilidades, cada uma com características próprias:

- **Nessus**: desenvolvido como projeto open-source em 1998, adquirido pela Tenable em 2005 e virou software proprietário. Tem opções extensas de scan e é muito usado por grandes empresas. Disponível em versão gratuita (recursos limitados) e paga (scans ilimitados, recursos avançados, suporte profissional). Precisa ser implantado e gerenciado on-premises.
- **Qualys**: desenvolvido em 1999 como solução de vulnerability management baseada em assinatura. Além do scan contínuo, oferece checagens de compliance e gestão de ativos, alertando automaticamente sobre vulnerabilidades encontradas no monitoramento contínuo. É uma plataforma cloud-based — sem custo extra de manter hardware físico.
- **Nexpose**: desenvolvido pela Rapid7 em 2005, solução por assinatura que descobre novos ativos na rede continuamente e roda scans de vulnerabilidade neles. Dá scores de risco de vulnerabilidade com base no valor do ativo e no impacto da falha. Também oferece checagens de compliance contra vários padrões. Suporta modo on-premises e híbrido (cloud + on-premises).

### 3. Ferramenta OpenVAS
- **OpenVAS** ([[Greenbone Security Assistant]]): Scanner de vulnerabilidades open-source robusto utilizado para varreduras completas de redes e sistemas.
- **Fases de Utilização**: Configuração de Alvos (Targets), Execução de Tarefas (Tasks) e Análise Detalhada de Relatórios de Resultados.

### 4. Avaliação de Severidade e Mitigação
- **Pontuação CVSS** ([[Common Vulnerability Scoring System]]): Métrica padronizada utilizada para classificar a gravidade das vulnerabilidades encontradas (Baixa, Média, Alta, Crítica).
- **Plano de Remediação**: Processo de priorização e correção das falhas com base no risco real apresentado ao negócio.

## O que fiz no lab
[Descreva o Practical Exercise — ex: qual alvo você escaneou no OpenVAS, quais CVEs apareceram, como priorizou pelo CVSS]

## Minha análise
[O que fez mais sentido / o que ainda é nebuloso — ex: entendi a diferença entre scanner (proativo) e IDS (reativo), mas ainda quero entender melhor como interpretar um relatório completo do OpenVAS na prática]

---

## Conexões com a Trilha SOC L1
- **Módulo Pai:** [[Cyber Security 101]]
- **Próxima Nota:** [[THM - Incident Response Basics]]
- **Conceitos Relacionados:** [[OpenVAS]], [[CVSS]], [[Vulnerability Management]]
