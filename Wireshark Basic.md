---
data: 2026-08-10
tags: [cyber, tryhackme, firewall, soc-l1]
plataforma: TryHackMe
sala: Firewall Fundamentals
modulo: Cyber Security 101
---

# Firewall Fundamentals

## THM: Firewall Fundamentals

### 1. O Papel do Firewall na Rede
- **Firewall**: Sistema de segurança de rede que monitora e controla o tráfego de entrada e saída com base em regras de segurança preestabelecidas.
- **Barreira de Defesa**: Atua como a primeira linha de defesa lógica entre uma rede interna confiável e redes externas não confiáveis (como a Internet).

### 2. Stateless vs. Stateful Firewalls

**Stateless Firewall**
Opera nas camadas 3 e 4 do modelo OSI, filtrando dados baseado só em regras predeterminadas, sem levar em conta o estado das conexões anteriores. Cada pacote é comparado às regras independentemente de pertencer a uma conexão legítima já estabelecida. Isso permite processar pacotes rapidamente, mas impede aplicar políticas complexas baseadas no histórico da conexão — se o firewall nega alguns pacotes de uma fonte, ele "esquece" isso e trata pacotes futuros da mesma fonte como novos.

**Stateful Firewall**
Vai além de filtrar por regras fixas: rastreia conexões anteriores e as armazena numa tabela de estado. Opera nas camadas 3 e 4 também, mas com uma camada extra de segurança baseada no histórico da conexão. Se o firewall aceita alguns pacotes de uma fonte, ele registra isso na tabela de estado e permite automaticamente todos os pacotes futuros dessa conexão sem precisar inspecionar cada um — e da mesma forma nega os pacotes futuros de fontes já negadas.

**Proxy Firewall**
Resolve o problema dos anteriores (inabilidade de inspecionar o conteúdo do pacote). Atua como intermediário entre a rede privada e a internet, operando na camada 7. Inspeciona o conteúdo de todos os pacotes; requisições feitas por usuários da rede são encaminhadas pelo proxy, que mascara com seu próprio IP pra dar anonimato aos IPs internos. Permite políticas de content filtering pra permitir/negar tráfego com base no conteúdo.

**Next-Generation Firewall (NGFW)**
O tipo mais avançado, operando das camadas 3 a 7. Oferece deep packet inspection e funcionalidades que reforçam a segurança do tráfego. Tem sistema de prevenção de intrusão (bloqueia atividade maliciosa em tempo real) e análise heurística (analisa padrões de ataque e bloqueia instantaneamente antes de chegar na rede). NGFWs têm capacidade de decriptação SSL/TLS, inspecionando pacotes após decriptá-los e correlacionando os dados com feeds de threat intelligence.

### 3. Tipos de Filtragem e Arquitetura
- **Filtragem de Pacotes** ([[Packet Filtering]]): Inspeção básica nas camadas de rede e transporte (IP e portas).
- **Firewall de Próxima Geração** ([[NGFW]]): Integra inspeção profunda de pacotes ([[DPI]]), filtragem de aplicação e recursos avançados de ameaças.

## O que fiz no lab
[Descreva a prática com Windows Defender Firewall e Linux iptables — ex: que regra você criou/testou, qual porta/IP bloqueou ou liberou]

## Minha análise
[O que fez mais sentido / o que ainda é nebuloso — ex: entendi bem a diferença stateless x stateful, mas ainda quero praticar mais a sintaxe do iptables de cabeça]

---

## Conexões com a Trilha SOC L1
- **Módulo Pai:** [[Cyber Security 101]]
- **Próxima Nota:** [[THM - IDS & IPS Fundamentals]]
- **Conceitos Relacionados:** [[Packet Filtering]], [[NGFW]], [[DPI]]
