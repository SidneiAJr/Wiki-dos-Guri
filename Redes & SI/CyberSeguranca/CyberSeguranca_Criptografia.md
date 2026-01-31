# 🔐 Criptografia

A **criptografia** é o processo de proteger dados através de técnicas matemáticas que tornam as informações ilegíveis para quem não possuir a chave correta.

É usada para:
- Garantir **confidencialidade**, **integridade** e **autenticidade** de informações.  
- Proteger dados em trânsito (como HTTPS) e em repouso (bancos de dados, backups, etc).

---

## 🧱 Tipos de Criptografia

### 1. Criptografia Simétrica (ex: AES)
- Usa **a mesma chave** para criptografar e descriptografar.
- Rápida e eficiente.
- Exemplo: **AES (Advanced Encryption Standard)** — usado em VPNs, Wi-Fi (WPA2) e arquivos zip protegidos.


# 🧮 Quadro Comparativo de Métodos de Criptografia

| Categoria | Algoritmo | Tipo de Chave | Reversível? | Tamanho de Chave Comum | Uso Típico |
|------------|------------|----------------|--------------|------------------------|-------------|
| **Simétrica** | **AES (Advanced Encryption Standard)** | Mesma chave | ✅ Sim | 128 / 192 / 256 bits | VPN, Wi-Fi, discos |
| **Simétrica** | **DES (Data Encryption Standard)** | Mesma chave | ✅ Sim | 56 bits | Legado (obsoleto) |
| **Simétrica** | **3DES (Triple DES)** | Mesma chave (3x) | ✅ Sim | 168 bits | Sistemas legados |
| **Simétrica** | **Blowfish** | Mesma chave | ✅ Sim | 32–448 bits | Substituto do DES |
| **Simétrica** | **Twofish** | Mesma chave | ✅ Sim | 128 / 256 bits | Criptografia geral |
| **Assimétrica** | **RSA (Rivest–Shamir–Adleman)** | Pública / Privada | ✅ Sim | 1024–4096 bits | HTTPS, assinaturas |
| **Assimétrica** | **ECC (Elliptic Curve Cryptography)** | Pública / Privada | ✅ Sim | 256 bits ≈ RSA 3072 | Mobile, IoT |
| **Assimétrica** | **DSA (Digital Signature Algorithm)** | Pública / Privada | ✅ Sim | 1024–3072 bits | Assinaturas digitais |
| **Hashing** | **MD5** | Sem chave | ❌ Não | 128 bits | Checksum (não seguro) |
| **Hashing** | **SHA-1** | Sem chave | ❌ Não | 160 bits | Antigo (não recomendado) |
| **Hashing** | **SHA-256 / SHA-512** | Sem chave | ❌ Não | 256 / 512 bits | Integridade, senhas |
| **Hashing** | **bcrypt / Argon2** | Sem chave | ❌ Não | Variável | Armazenamento seguro de senhas |
| **Híbrido** | **PGP / GPG (Pretty Good Privacy / GNU Privacy Guard)** | Combina simétrica + assimétrica | ✅ Sim | Variável | Criptografia de e-mails e arquivos |
| **Fluxo** | **RC4** | Mesma chave | ✅ Sim | Variável | SSL antigo (inseguro) |
