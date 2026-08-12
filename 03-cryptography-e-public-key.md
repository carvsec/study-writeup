# Cryptography Basics & Public Key Cryptography — TryHackMe

**Data:** 03/08/2026 | **Categoria:** Cryptography

## O que aprendi

**Cryptography Basics** cobriu os termos fundamentais: plaintext (dado legível), ciphertext (dado cifrado), cipher (algoritmo de conversão) e key (a informação secreta que o cipher usa). Vi a diferença entre criptografia simétrica (uma única chave pra cifrar e decifrar — ex: DES, 3DES, AES) e assimétrica (par de chaves pública/privada — ex: RSA, Diffie-Hellman, ECC), além das operações matemáticas usadas por trás (XOR e módulo).

**Public Key Cryptography Basics** aprofundou o porquê da criptografia assimétrica importar: ela não serve só pra confidencialidade, mas principalmente pra **autenticação** (confirmar identidade), **autenticidade** (confirmar que a mensagem realmente veio de quem diz ter enviado) e **integridade** (garantir que o dado não foi alterado) — enquanto a simétrica foca quase só em confidencialidade. Isso é aplicado na prática em RSA, Diffie-Hellman, SSH, certificados SSL/TLS e PGP/GPG.

## Prática
Apliquei o conceito de criptografia assimétrica com GPG (par de chaves pública/privada) pra cifrar, decifrar e assinar arquivo:
```bash
gpg --import chave_publica.asc
gpg --encrypt --recipient usuario@email.com arquivo.txt
gpg --decrypt arquivo.txt.gpg
```
Também pratiquei a operação XOR aplicada como cifra simétrica simples (C = P ⊕ K, e P = C ⊕ K pra recuperar o texto original) e cálculo de módulo, que aparecem como base matemática de vários algoritmos assimétricos como RSA.

## Referência
- [Cryptography Basics — TryHackMe](https://tryhackme.com/room/cryptographybasics)
- [Public Key Cryptography Basics — TryHackMe](https://tryhackme.com/room/publickeycrypto)

Notas completas de estudo disponíveis sob consulta.
