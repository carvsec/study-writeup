# CAPA: The Basics

**Data:** 2026 | **Categoria:** Defensive Security Tooling

## O que aprendi
CAPA, desenvolvido pela equipe FLARE/Mandiant, é uma ferramenta que identifica automaticamente as capacidades de um arquivo executável PE, ELF, .NET, shellcode, relatórios de sandbox, aplicando um conjunto de regras que descrevem comportamentos comuns de malware, sem precisar fazer engenharia reversa manual. Os resultados são organizados em referências ao MITRE ATT&CK, técnica de Obfuscated Files or Information T1027, e ao MBC Malware Behavior Catalog, agrupados por namespaces e capacidades específicas.

## Prática
Abri o PowerShell e naveguei até a pasta da ferramenta:
```powershell
cd C:\Users\Administrator\Desktop\capa
```
Rodei o CAPA contra a amostra de malware:
```powershell
capa.exe cryptbot.bin
```
Explorei os parâmetros de linha de comando da ferramenta:
```powershell
capa -h     # lista de parâmetros disponíveis
capa -v     # informação detalhada das capacidades
capa -vv    # informação muito detalhada
capa -j     # exporta o resultado em formato JSON
```
Como a análise completa demora, também li o resultado pré-processado direto no PowerShell:
```powershell
Get-Content .\cryptbot.txt
```
Analisei o resultado mapeado ao MITRE ATT&CK, identificando a técnica Obfuscated Files or Information T1027 e a sub-técnica Indicator Removal from Tools T1027.005, usadas quando o malware ofusca dados via base64 e XOR, e correlacionei com o namespace e a capability apontados no relatório do CAPA.

## Referência
https://tryhackme.com/room/capabasics
