# CyberChef: The Basics

**Data:** 2026 | **Categoria:** Defensive Security Tooling

## O que aprendi
CyberChef é uma ferramenta web desenvolvida pelo GCHQ, o "canivete suíço" pra manipulação e decodificação de dados, com tudo funcionando direto no navegador, sem instalação. A interface tem 4 áreas principais: Operations, biblioteca com todas as funções disponíveis, categorizadas e pesquisáveis, Recipe, onde você arrasta e organiza as operações na ordem que serão executadas, Input, onde entra o dado bruto, e Output, onde aparece o resultado após clicar em BAKE. As operações vão do simples, Base64, XOR, Morse, ao complexo, criptografia AES, decriptação RSA. O fluxo de raciocínio ensinado na sala é: definir o objetivo, colocar o dado no Input, selecionar as Operations certas, conferir o Output e repetir se o resultado não for o esperado.

## Prática
Como o CyberChef não usa terminal, o equivalente às "linhas de comando" são as operations encadeadas na Recipe. Apliquei as seguintes:

**URL Decode** — decodifiquei uma URL codificada:
```
Input:  https%3A%2F%2Ftryhackme.com%2Fr%2Froom%2Fcyberchefbasics
Recipe: URL Decode
Output: https://tryhackme.com/r/room/cyberchefbasics
```

**From UNIX Timestamp** — converti um timestamp Unix pra data legível:
```
Input:  1725151258
Recipe: From UNIX Timestamp (parâmetros padrão)
Output: data/hora correspondente
```

**From Base85** — decodifiquei uma string em Base85:
```
Input:  <+oue+DGm>Ap%u7
Recipe: From Base85 (parâmetros padrão)
Output: texto decodificado
```

**Extração de dados de um arquivo** — usei os extractors da categoria Extractors pra puxar IPs, URLs e emails de dentro de um arquivo de log/texto bruto, incluindo identificar um IP específico que começava e terminava com "10".

## Referência
https://tryhackme.com/room/cyberchefbasics
