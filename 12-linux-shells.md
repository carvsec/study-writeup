# Linux Shells

**Data:** 15/07/2026 | **Categoria:** Command Line

## O que aprendi
A shell é a camada que interpreta os comandos digitados na CLI e os repassa pro sistema operacional, é o que dá o poder e a flexibilidade de fazer quase qualquer coisa sem depender da GUI. Existem vários tipos de shell bash, zsh, sh, etc., cada um com particularidades próprias; o comando `echo $SHELL` mostra qual está em uso na sessão atual. Bash é o padrão e mais usado na maioria das distros Linux.

Revisei também a navegação básica pwd, cd, ls e o uso do `grep` pra buscar padrões/palavras dentro de arquivos grandes, essencial pra depois, quando for analisar logs de verdade num SOC.

A parte principal foi escrever shell scripts: todo script bash começa com um shebang `#!/bin/bash`, que indica ao sistema qual interpretador usar. O arquivo precisa da extensão `.sh` e precisa de permissão de execução `chmod +x` antes de rodar.

## Prática
Vi qual shell estava em uso:
```bash
echo $SHELL
```

Naveguei e busquei conteúdo dentro de arquivos:
```bash
pwd
ls -la
grep "THM" arquivo_grande.txt
```

Criei e executei um script simples de autenticação recebe usuário, empresa e PIN, valida e libera acesso:
```bash
#!/bin/bash
echo "Enter your Username: "
read username
echo "Enter your Company name: "
read company
echo "Enter your PIN: "
read pin

if [ "$pin" == "1234" ]; then
  echo "Access Granted!"
else
  echo "Authentication Denied!!"
fi
```

Dei permissão de execução e rodei:
```bash
chmod +x locker_script.sh
./locker_script.sh
```

## Referência
https://tryhackme.com/room/linuxshells
