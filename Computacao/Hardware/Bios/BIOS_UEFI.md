# BIOS vs UEFI

A BIOS/UEFI é o firmware responsável por inicializar o computador antes do sistema operacional.

---

## Diferença entre BIOS e UEFI

| Item | BIOS | UEFI |
|------|------|-------|
| Tecnologia | Antiga | Moderna |
| Suporte a discos | Até 2TB | Até 9.4 ZB |
| Interface | Texto | Gráfica (mouse) |
| Boot | Legacy (MBR) | Secure Boot / GPT |
| Velocidade | Mais lenta | Mais rápida |

---

## Principais Funções da UEFI/BIOS

- Definir ordem de boot
- Configurar CPU / RAM (XMP/DOCP)
- Monitoramento de hardware (temperatura, tensões)
- Ativar virtualização (Intel VT-x / AMD-V)
- Secure Boot / TPM (necessário no Windows 11)

---

## MBR x GPT

| Tipo | Limite de disco | Partições |
|------|------------------|------------|
| MBR | 2TB | 4 primárias |
| GPT | 9.4 ZB | 128 partições |

---

## Boas práticas

✅ Manter firmware atualizado  
✅ Desativar boot por DVD/USB quando não usado  
✅ Usar UEFI + GPT sempre que possível  
✅ Atenção ao Secure Boot ao instalar Linux

---

## Resumo

- BIOS → legado
- UEFI → moderno, seguro e rápido
- GPT → recomendado
