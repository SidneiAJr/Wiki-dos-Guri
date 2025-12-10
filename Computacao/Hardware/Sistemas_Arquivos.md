# Sistemas de Arquivos (EXT4, NTFS, BTRFS, XFS, FAT32, exFAT)

Um sistema de arquivos é a forma como o sistema operacional organiza e gerencia os dados dentro de um dispositivo de armazenamento.

## Principais Sistemas de Arquivos

| Sistema | Uso Principal | Suporte a Arquivos Grandes | Journaling | Recursos Especiais |
|---------|---------------|-----------------------------|------------|--------------------|
| **NTFS** | Windows | ✅ Sim | ✅ | Permissões avançadas, criptografia |
| **EXT4** | Linux (desktop/servidor) | ✅ Sim | ✅ | Estável e rápido |
| **BTRFS** | Linux (servidores / SO moderno) | ✅ Sim | ✅ | *Snapshots*, compressão, RAID |
| **XFS** | Linux (alta performance) | ✅ Sim | ✅ | Muito usado em servidores |
| **FAT32** | Pendrives antigos / BIOS | ❌ Máx. 4GB por arquivo | ❌ | Compatibilidade universal |
| **exFAT** | Pendrives modernos | ✅ Sim | ❌ | Compatível com Windows / Linux / Mac |

---

## Qual escolher?

| Situação | Melhor Sistema |
|----------|----------------|
| Windows instalado no PC | NTFS |
| Linux desktop comum | EXT4 |
| Servidor Linux moderno | BTRFS ou XFS |
| Pendrive universal | exFAT |
| BIOS/UEFI boot | FAT32 |

---

