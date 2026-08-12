# FlareVM: Arsenal of Tools

**Data:** 2026 | **Categoria:** Defensive Security Tooling

## O que aprendi
FlareVM é uma máquina virtual Windows criada pela equipe FLARE, reunindo ferramentas de engenharia reversa, análise de malware e forense num único ambiente. É usada em labs de malware, SOCs e resposta a incidentes, permitindo investigar um arquivo suspeito de forma segura, sem expor o sistema principal. A sala é majoritariamente baseada em ferramentas gráficas: PEStudio e CFF Explorer para análise estática de arquivos PE, x64dbg, debugger open-source pra binários x64/x32, Process Hacker, editor de memória e monitor de processos, FTK Imager, aquisição e análise forense de imagem de disco, HxD, editor hexadecimal, Process Explorer, visão detalhada da árvore de processos ativos, e Procmon, rastreamento de atividade do sistema em tempo real. A ferramenta com uso via linha de comando é o FLOSS, que extrai e desofusca strings de programas maliciosos.

## Prática
Abri o PowerShell na máquina FlareVM e naveguei até a pasta com a amostra:
```powershell
cd C:\Users\Administrator\Desktop\Sample
```
Rodei o FLOSS contra o executável suspeito, redirecionando o resultado pra um arquivo de texto:
```powershell
FLOSS.exe .\windows.exe > windows.txt
```
usei as ferramentas gráficas em conjunto:
- **PEStudio** pra abrir o arquivo e extrair o hash SHA256 e a contagem de funções do binário
- **CFF Explorer** pra gerar o hash MD5 e inspecionar o DOS Header do arquivo
- **Process Explorer** pra mapear a relação pai-filho dos processos ativos

## Referência
https://tryhackme.com/room/flarevmarsenaloftools
