# Hashing Basics 

**Data:** 03/08/2026 | **Categoria:** Cryptography

## O que aprendi
Hash é diferente de criptografia — não tem chave e não é reversível, serve pra integridade e verificação de senha, não pra confidencialidade. Qualquer mudança mínima no input muda o output inteiro (efeito avalanche). Aprendi por que senha em plaintext ou hash sem salt é perigoso (rainbow tables) e como salt + algoritmos como Bcrypt/Argon2 resolvem isso. Também vi a diferença entre quebrar hash (testar candidatos até bater, via Hashcat/John the Ripper) e decriptar (não se aplica a hash).

## Prática
Comparei dois arquivos de 1 bit de diferença e confirmei o efeito avalanche:
```bash
hexdump -C file1.txt
hexdump -C file2.txt
md5sum *.txt
sha1sum *.txt
sha256sum *.txt
```
Resultado: mesmo com só 1 bit de diferença no input, os três hashes saíram completamente diferentes entre os dois arquivos.

Também verifiquei integridade de arquivo comparando o SHA256 de uma ISO baixada com o hash assinado oficialmente:
```bash
sha256sum Fedora-Workstation-Live-x86_64-40-1.14.iso
```

## Referência
https://tryhackme.com/room/hashingbasics