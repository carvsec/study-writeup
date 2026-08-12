# Cryptography Basics & Public Key Cryptography 

**Data:** 03/08/2026 | **Categoria:** Cryptography

## O que aprendi

**Cryptography Basics** cobriu os termos fundamentais: plaintext, ciphertext, cipher e key. Vi a diferença entre criptografia simétrica uma única chave pra cifrar e decifrar — ex: DES, 3DES, AES e assimétrica par de chaves pública/privada — ex: RSA, Diffie-Hellman, ECC, além das operações matemáticas usadas por trás XOR e módulo.

**Public Key Cryptography Basics** aprofundou o porquê da criptografia assimétrica importar: ela não serve só pra confidencialidade, mas principalmente pra **autenticação**, **autenticidade**  e **integridade** — enquanto a simétrica foca quase só em confidencialidade. Isso é aplicado na prática em RSA, Diffie-Hellman, SSH, certificados SSL/TLS e PGP/GPG.

## Prática
Apliquei o conceito de criptografia assimétrica com GPG pra cifrar, decifrar e assinar arquivo:
```bash
gpg --import chave_publica.asc
gpg --encrypt --recipient usuario@email.com arquivo.txt
gpg --decrypt arquivo.txt.gpg
```
Também pratiquei a operação XOR aplicada como cifra simétrica simples C = P ⊕ K, e P = C ⊕ K pra recuperar o texto original e cálculo de módulo, que aparecem como base matemática de vários algoritmos assimétricos como RSA.

## Referência
- [Cryptography Basics — TryHackMe](https://tryhackme.com/room/cryptographybasics)
- [Public Key Cryptography Basics — TryHackMe](https://tryhackme.com/room/publickeycrypto)


