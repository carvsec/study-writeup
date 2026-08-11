Nmap: The Basics — TryHackMe
Data: 10/08/2026 | Categoria: Reconnaissance

O que aprendi

Estudei o Nmap como ferramenta essencial de mapeamento de rede e varredura de portas para auditorias de segurança. Diferenciei o Host Discovery (mapeamento de ativos vivos) do Port Scanning, entendendo tipos de varredura como SYN Scan (-sS), TCP Connect (-sT), UDP Scan (-sU) e a desativação de ping com -Pn. Explorei técnicas de detecção de versões (-sV), Sistema Operacional (-O), scripts de vulnerabilidade via NSE (-sC) e varreduras agressivas (-A), além de gerenciar intervalos de portas (-p), perfis de timing (-T0 a -T5) e exportação de resultados (-oN, -oX).

Prática

Executei comandos de varredura rápida de portas com detecção de versão e scans agressivos completos:

Bash
sudo nmap -sS -sV 10.10.10.10 -T4
sudo nmap -A -Pn -p- 10.10.10.10 -oN resultado_nmap.txt
Referência

Notas completas de estudo disponíveis sob consulta.