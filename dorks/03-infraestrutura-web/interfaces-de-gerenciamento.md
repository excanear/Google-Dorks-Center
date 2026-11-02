<div align="center">

[🏠 Hub](../../README.md) · [🖧 Infraestrutura Web](README.md) · [← Status & Info Pages](status-e-info-pages.md) · [Próximo: Versões & Software Exposto →](versoes-e-software-exposto.md)

# 🗂 Interfaces de Gerenciamento

*Consoles de administração de banco, hospedagem e sistema — phpMyAdmin, Adminer, cPanel, Plesk, Webmin e afins.*

</div>

---

> [!CAUTION]
> Essas interfaces dão controle sobre bancos e servidores. Exposição é achado 🔴; **não tente autenticar** sem autorização. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Administração de banco de dados

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"phpMyAdmin" "Welcome to phpMyAdmin"` | phpMyAdmin exposto | Google, Bing | 🔴 |
| `inurl:/phpmyadmin/index.php` | Instância phpMyAdmin por URL | Google | 🔴 |
| `intitle:"Adminer" inurl:adminer.php` | Adminer (admin de banco) | Google | 🔴 |
| `intitle:"pgAdmin"` | pgAdmin exposto | Google | 🔴 |
| `intitle:"phpPgAdmin"` | phpPgAdmin exposto | Google | 🔴 |
| `intitle:"Mongo Express"` | UI web do MongoDB | Google | 🔴 |
| `intitle:"phpLiteAdmin"` | Admin de SQLite | Google | 🔴 |
| `intitle:"DBeaver"` inurl:/dbeaver | Console DBeaver web | Google | 🟡 |

### Painéis de hospedagem e sistema

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:2082 intitle:"cPanel"` | cPanel (porta padrão) | Google | 🟡 |
| `intitle:"Plesk Obsidian"` | Painel Plesk | Google | 🟡 |
| `intitle:"Webmin" inurl:/session_login.cgi` | Webmin | Google | 🔴 |
| `intitle:"Virtualmin"` | Virtualmin | Google | 🟡 |
| `intitle:"DirectAdmin" inurl:/CMD_LOGIN` | DirectAdmin | Google | 🟡 |
| `intitle:"ISPConfig"` | Painel ISPConfig | Google | 🟡 |
| `intitle:"CyberPanel"` | CyberPanel | Google | 🟡 |
| `intitle:"Proxmox Virtual Environment"` | Hypervisor Proxmox | Google | 🔴 |
| `intitle:"cockpit" inurl:9090` | Cockpit (gestão de Linux) | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Shodan | FOFA |
|---|---|---|---|
| `intitle:"phpMyAdmin" "Welcome to phpMyAdmin"` | `intitle:"phpMyAdmin"` | `http.title:"phpMyAdmin"` | `title="phpMyAdmin"` |
| `intitle:"Adminer" inurl:adminer.php` | `intitle:"Adminer"` | `http.html:"Adminer"` | `body="Adminer"` |
| `intitle:"Webmin" inurl:/session_login.cgi` | `intitle:"Webmin"` | `http.title:"Webmin" port:10000` | `title="Webmin"` |
| `intitle:"Proxmox Virtual Environment"` | `intitle:"Proxmox Virtual Environment"` | `http.title:"Proxmox Virtual Environment"` | `title="Proxmox Virtual Environment"` |
| `intitle:"Mongo Express"` | `intitle:"Mongo Express"` | `http.title:"Mongo Express"` | `title="Mongo Express"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Interface de gerenciamento por título — 6 variações

```text
intitle:"phpMyAdmin"
intitle:"Adminer"
intitle:"Webmin"
intitle:"cPanel"
intitle:"DirectAdmin"
intitle:"Cockpit"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- phpMyAdmin/Adminer/Webmin expostos à internet são 🔴 — alvos clássicos; apenas confirme a exposição e reporte.
- Painéis em **portas não-padrão** (cPanel 2082/2083, Webmin 10000, Proxmox 8006, Cockpit 9090) são melhor caçados por **Shodan/FOFA** com `port:`.
- A exposição de banco em si (serviço MongoDB/Elastic sem UI) fica em [04 · Bancos de Dados](../04-tecnologias/bancos-de-dados.md); aqui é a **interface web**.

<div align="center">

[🏠 Hub](../../README.md) · [🖧 Infraestrutura Web](README.md) · [← Status & Info Pages](status-e-info-pages.md) · [Próximo: Versões & Software Exposto →](versoes-e-software-exposto.md)

</div>
