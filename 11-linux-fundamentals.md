# Linux Fundamentals — TryHackMe

**Data:** 10/07/2026 | **Categoria:** Linux Basics

## O que aprendi
Compreendi o ambiente Linux, a interação com o sistema via linha de comando, navegação básica (pwd, ls, cd) e manipulação de arquivos (cat, head, tail). Aprofundei em permissões de sistema (rwx) e execução com sudo. Gerenciei processos (ps, top), serviços (systemctl), armazenamento (df, free) e automação (cron).

## Prática
Naveguei pelo sistema e listei arquivos essenciais:
```bash
whoami
ls -la
cat /etc/passwd
```

Realizei buscas de arquivos e verifiquei permissões:
```bash
find / -name flag.txt 2>/dev/null
grep -r "password" /var/log/
sudo cat /etc/shadow
```

Gerenciei serviços e verifiquei o status do sistema:
```bash
ps aux | grep apache2
systemctl status ssh
df -h
crontab -l
```

## Referência
Notas completas de estudo disponíveis sob consulta.
