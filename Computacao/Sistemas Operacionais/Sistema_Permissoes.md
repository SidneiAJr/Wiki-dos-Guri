# 🔐 Sistema de Permissões em Sistemas Operacionais

Os sistemas operacionais (Linux e Windows) controlam **quem pode acessar, modificar ou executar** arquivos e recursos.

---

## 🐧 Permissões no Linux

Cada arquivo tem 3 tipos de permissões:

| Tipo | Descrição | Letra |
|:--|:--|:--|
| **Leitura** | Permite ver o conteúdo | r |
| **Escrita** | Permite modificar | w |
| **Execução** | Permite executar (programas/scripts) | x |

E 3 categorias de usuários:

| Categoria | Descrição |
|:--|:--|
| **Usuário (Owner)** | Dono do arquivo |
| **Grupo** | Usuários do mesmo grupo |
| **Outros** | Todos os demais |

**Exemplo:**
➡️ Dono pode ler, escrever e executar.  
➡️ Grupo pode ler e executar.  
➡️ Outros só podem ler.

**Comandos úteis:**
```bash
ls -l
chmod 755 arquivo.sh
chown usuario:grupo arquivo.txt
```

## 🪟 Permissões no Windows

Controladas por ACL (Access Control List).

Cada usuário ou grupo tem níveis de permissão:

Leitura

Gravação

Modificação

Controle total

Como configurar:

Botão direito → Propriedades → Segurança → Editar permissões


---


# ⚙️ Comparativo entre Linux e Windows

| Característica | Linux | Windows |
|:--|:--|:--|
| **Licença** | Livre (open source) | Proprietária |
| **Interface** | Várias (GNOME, KDE, XFCE) | Única e padronizada |
| **Segurança** | Alta, com permissões rígidas | Boa, mas mais vulnerável |
| **Uso de Recursos** | Leve | Mais pesado |
| **Terminal** | Ferramenta poderosa (bash, zsh) | Prompt e PowerShell |
| **Atualizações** | Controladas pelo usuário | Automáticas e centralizadas |
| **Instalação de Programas** | Repositórios (apt, yum) | Executáveis (.exe, .msi) |
| **Popularidade** | Servidores e Devs | Usuários domésticos e corporativos |

---

## 💡 Vantagens de cada um

**Linux:**
- Gratuito  
- Estável e seguro  
- Personalizável  
- Ideal pra servidores e desenvolvimento  

**Windows:**
- Interface amigável  
- Suporte amplo a jogos e softwares  
- Compatibilidade com hardware e drivers  

---

## 🧠 Curiosidade
O Android é baseado no **kernel Linux**.  
Muitos servidores web rodam Linux, enquanto estações corporativas usam Windows.

---

## ⚔️ Conclusão
> Linux é liberdade e controle.  
> Windows é praticidade e compatibilidade.


