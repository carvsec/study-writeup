# REMnux: Getting Started

**Data:** 2026 | **Categoria:** Defensive Security Tooling

## O que aprendi
REMnux é uma distribuição Linux especializada em análise de malware, com ferramentas como Volatility 3, YARA, Wireshark, oledump e INetSim já integradas. Fornece um ambiente tipo sandbox pra dissecar software potencialmente malicioso sem colocar em risco a máquina principal, sendo muito usado durante incidentes de segurança reais, onde a precisão da análise é crítica. A sala cobriu três frentes: análise estática de documento Office malicioso, simulação de rede pra observar tentativas de conexão externa de forma segura, e análise de memória de um sistema infectado.

## Prática

**Análise de documento Office com oledump.py:**
```bash
oledump.py -h                          # ajuda / opções da ferramenta
oledump.py agenttesla.xlsm             # lista os streams do arquivo OLE2
oledump.py -s <numero_do_stream> -v agenttesla.xlsm   # decompacta e exibe a macro VBA de um stream específico
```
Identifiquei os streams marcados com `M`, que indicam presença de macro, e extraí o código VBA malicioso de dentro deles.

**Simulação de rede com INetSim:**
```bash
sudo nano /etc/inetsim/inetsim.conf
# alterei a linha: dns_default_ip 0.0.0.0 -> dns_default_ip <IP_DA_MAQUINA>
sudo inetsim                           # inicia o simulador de serviços de internet
```
Em outra máquina, baixei um payload apontando pro serviço simulado:
```bash
sudo wget https://<IP_DA_MAQUINA>/second_payload.zip --no-check-certificate
```
Parei o simulador com `Ctrl+C` e li o relatório gerado pra entender qual método de requisição (URL Method) o malware usou pra buscar o arquivo.

**Análise de memória com Volatility 3:**
```bash
vol3 -h                                              # ajuda da ferramenta
vol3 -f wcry.mem windows.pstree.PsTree               # árvore de processos por PID pai
vol3 -f wcry.mem windows.pslist.PsList               # lista de processos ativos no dump
vol3 -f wcry.mem windows.dlllist.DllList | grep "@WanaDecryptor@.exe"   # localiza o caminho do binário malicioso
vol3 -f wcry.mem windows.malfind.Malfind             # identifica processos com indício de código injetado
```
Também usei o utilitário `strings` pra extrair texto legível da amostra, incluindo strings em formato Unicode:
```bash
strings -e l arquivo_suspeito     # strings 16-bit little-endian
strings -e b arquivo_suspeito     # strings 16-bit big-endian
```

## Referência
https://tryhackme.com/room/remnuxgettingstarted
