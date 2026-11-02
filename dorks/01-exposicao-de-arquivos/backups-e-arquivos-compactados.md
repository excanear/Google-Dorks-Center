<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Planilhas & CSV](planilhas-e-csv.md) · [Próximo: Dumps de Banco de Dados →](dumps-de-banco-de-dados.md)

# 💾 Backups & Arquivos Compactados

*Backups de site, código-fonte e sistemas esquecidos no webroot: `.zip`, `.tar.gz`, `.bak`, `.old`, `.7z`, `.rar`.*

</div>

---

> [!CAUTION]
> Backups costumam conter código-fonte, configuração e bancos inteiros. Localizar ≠ baixar: acessar o conteúdo sem autorização pode configurar crime (Lei 12.737/2012, CFAA). Em pentest, confirme o escopo por escrito. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Backups de site e webroot (diretórios abertos)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "backup.zip"` | Diretório aberto com backup.zip | Google, Bing | 🔴 |
| `intitle:"index of" "site.tar.gz"` | Backup compactado do site | Google, Bing | 🔴 |
| `intitle:"index of" "public_html.zip"` | Backup do webroot | Google, Bing | 🔴 |
| `intitle:"index of" "htdocs.zip"` | Backup de webroot Apache/Plesk | Google | 🔴 |
| `intitle:"index of" "backup" "parent directory"` | Pastas de backup genéricas | Google, Bing | 🟡 |
| `intitle:"index of" "/backups"` | Pasta /backups listável | Google | 🟡 |
| `intitle:"index of" "full_backup"` | Backups completos nomeados | Google | 🟡 |

### Backups gerados por plugins (CMS)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/wp-content/ai1wm-backups/` | All-in-One WP Migration | Google | 🔴 |
| `inurl:/wp-content/backups-dup-lite/` | Duplicator (WordPress) | Google | 🔴 |
| `inurl:/wp-content/uploads/backwpup` | BackWPup | Google | 🔴 |
| `intitle:"index of" "updraft"` | UpdraftPlus (WordPress) | Google | 🔴 |
| `inurl:/administrator/components/com_akeeba/backup/` | Akeeba (Joomla) | Google | 🔴 |
| `intitle:"index of" "akeeba" ext:jpa` | Arquivos .jpa do Akeeba | Google | 🔴 |

### Cópias de versão antiga e de editor

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `ext:bak inurl:config` | Cópias .bak de configuração | Google | 🔴 |
| `ext:old inurl:config` | Cópias .old de configuração | Google | 🔴 |
| `ext:orig inurl:index` | Arquivos .orig de merge/patch | Google | 🟡 |
| `ext:save inurl:php` | Cópias .save de editores | Google | 🟡 |
| `ext:swp intitle:"index of"` | Arquivos de swap do Vim listados | Google | 🟡 |
| `intitle:"index of" ".bak"` | Diretórios com arquivos .bak | Google, Bing | 🟡 |
| `intitle:"index of" ".old"` | Diretórios com arquivos .old | Google, Bing | 🟡 |

### Arquivos compactados em diretórios abertos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ext:rar` | Diretórios com .rar | Google | 🟡 |
| `intitle:"index of" ext:7z` | Diretórios com .7z | Google | 🟡 |
| `intitle:"index of" "backup" ext:tar.gz` | Tarballs em pastas de backup | Google | 🔴 |
| `intitle:"index of" "db" ext:gz` | Dumps compactados em /db | Google | 🔴 |
| `intitle:"index of" "release.zip"` | Pacotes de release/deploy | Google | 🟡 |
| `intitle:"index of" "dist.zip"` | Builds de front-end empacotados | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | Yandex |
|---|---|---|---|
| `intitle:"index of" "backup.zip"` | `intitle:"index of" "backup.zip"` | `intitle:"index of" "backup.zip"` | `title:"index of" "backup.zip"` |
| `ext:bak inurl:config` | `ext:bak inurl:config` | `filetype:bak inurl:config` | `mime:bak url:config` |
| `inurl:/wp-content/ai1wm-backups/` | `instreamset:url:wp-content/ai1wm-backups` | `inurl:wp-content/ai1wm-backups` | `url:wp-content/ai1wm-backups` |
| `intitle:"index of" ext:rar` | `intitle:"index of" ext:rar` | `intitle:"index of" filetype:rar` | `title:"index of" mime:rar` |
| `intitle:"index of" "updraft"` | `intitle:"index of" updraft` | `intitle:"index of" updraft` | `title:"index of" updraft` |

> Para buscadores de infraestrutura, backups expostos aparecem melhor por título de diretório — veja o [manual de infraestrutura](../../docs/manual/03-buscadores-de-infraestrutura.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Backup compactado por nome-base × extensão de arquivo — 214 variações

```text
intitle:"index of" "backup.rar"
intitle:"index of" "backup.7z"
intitle:"index of" "backup.tar"
intitle:"index of" "backup.gz"
intitle:"index of" "backup.tgz"
intitle:"index of" "backup.tar.gz"
intitle:"index of" "backup.bz2"
intitle:"index of" "backup.xz"
intitle:"index of" "backup.cab"
intitle:"index of" "bak.zip"
intitle:"index of" "bak.rar"
intitle:"index of" "bak.7z"
intitle:"index of" "bak.tar"
intitle:"index of" "bak.gz"
intitle:"index of" "bak.tgz"
intitle:"index of" "bak.tar.gz"
intitle:"index of" "bak.bz2"
intitle:"index of" "bak.xz"
intitle:"index of" "bak.cab"
intitle:"index of" "www.zip"
intitle:"index of" "www.rar"
intitle:"index of" "www.7z"
intitle:"index of" "www.tar"
intitle:"index of" "www.gz"
intitle:"index of" "www.tgz"
intitle:"index of" "www.tar.gz"
intitle:"index of" "www.bz2"
intitle:"index of" "www.xz"
intitle:"index of" "www.cab"
intitle:"index of" "web.zip"
intitle:"index of" "web.rar"
intitle:"index of" "web.7z"
intitle:"index of" "web.tar"
intitle:"index of" "web.gz"
intitle:"index of" "web.tgz"
intitle:"index of" "web.tar.gz"
intitle:"index of" "web.bz2"
intitle:"index of" "web.xz"
intitle:"index of" "web.cab"
intitle:"index of" "site.zip"
intitle:"index of" "site.rar"
intitle:"index of" "site.7z"
intitle:"index of" "site.tar"
intitle:"index of" "site.gz"
intitle:"index of" "site.tgz"
intitle:"index of" "site.bz2"
intitle:"index of" "site.xz"
intitle:"index of" "site.cab"
intitle:"index of" "website.zip"
intitle:"index of" "website.rar"
intitle:"index of" "website.7z"
intitle:"index of" "website.tar"
intitle:"index of" "website.gz"
intitle:"index of" "website.tgz"
intitle:"index of" "website.tar.gz"
intitle:"index of" "website.bz2"
intitle:"index of" "website.xz"
intitle:"index of" "website.cab"
intitle:"index of" "public_html.rar"
intitle:"index of" "public_html.7z"
intitle:"index of" "public_html.tar"
intitle:"index of" "public_html.gz"
intitle:"index of" "public_html.tgz"
intitle:"index of" "public_html.tar.gz"
intitle:"index of" "public_html.bz2"
intitle:"index of" "public_html.xz"
intitle:"index of" "public_html.cab"
intitle:"index of" "htdocs.rar"
intitle:"index of" "htdocs.7z"
intitle:"index of" "htdocs.tar"
intitle:"index of" "htdocs.gz"
intitle:"index of" "htdocs.tgz"
intitle:"index of" "htdocs.tar.gz"
intitle:"index of" "htdocs.bz2"
intitle:"index of" "htdocs.xz"
intitle:"index of" "htdocs.cab"
intitle:"index of" "httpdocs.zip"
intitle:"index of" "httpdocs.rar"
intitle:"index of" "httpdocs.7z"
intitle:"index of" "httpdocs.tar"
intitle:"index of" "httpdocs.gz"
intitle:"index of" "httpdocs.tgz"
intitle:"index of" "httpdocs.tar.gz"
intitle:"index of" "httpdocs.bz2"
intitle:"index of" "httpdocs.xz"
intitle:"index of" "httpdocs.cab"
intitle:"index of" "wwwroot.zip"
intitle:"index of" "wwwroot.rar"
intitle:"index of" "wwwroot.7z"
intitle:"index of" "wwwroot.tar"
intitle:"index of" "wwwroot.gz"
intitle:"index of" "wwwroot.tgz"
intitle:"index of" "wwwroot.tar.gz"
intitle:"index of" "wwwroot.bz2"
intitle:"index of" "wwwroot.xz"
intitle:"index of" "wwwroot.cab"
intitle:"index of" "app.zip"
intitle:"index of" "app.rar"
intitle:"index of" "app.7z"
intitle:"index of" "app.tar"
intitle:"index of" "app.gz"
intitle:"index of" "app.tgz"
intitle:"index of" "app.tar.gz"
intitle:"index of" "app.bz2"
intitle:"index of" "app.xz"
intitle:"index of" "app.cab"
intitle:"index of" "application.zip"
intitle:"index of" "application.rar"
intitle:"index of" "application.7z"
intitle:"index of" "application.tar"
intitle:"index of" "application.gz"
intitle:"index of" "application.tgz"
intitle:"index of" "application.tar.gz"
intitle:"index of" "application.bz2"
intitle:"index of" "application.xz"
intitle:"index of" "application.cab"
intitle:"index of" "source.zip"
intitle:"index of" "source.rar"
intitle:"index of" "source.7z"
intitle:"index of" "source.tar"
intitle:"index of" "source.gz"
intitle:"index of" "source.tgz"
intitle:"index of" "source.tar.gz"
intitle:"index of" "source.bz2"
intitle:"index of" "source.xz"
intitle:"index of" "source.cab"
intitle:"index of" "src.zip"
intitle:"index of" "src.rar"
intitle:"index of" "src.7z"
intitle:"index of" "src.tar"
intitle:"index of" "src.gz"
intitle:"index of" "src.tgz"
intitle:"index of" "src.tar.gz"
intitle:"index of" "src.bz2"
intitle:"index of" "src.xz"
intitle:"index of" "src.cab"
intitle:"index of" "release.rar"
intitle:"index of" "release.7z"
intitle:"index of" "release.tar"
intitle:"index of" "release.gz"
intitle:"index of" "release.tgz"
intitle:"index of" "release.tar.gz"
intitle:"index of" "release.bz2"
intitle:"index of" "release.xz"
intitle:"index of" "release.cab"
intitle:"index of" "dist.rar"
intitle:"index of" "dist.7z"
intitle:"index of" "dist.tar"
intitle:"index of" "dist.gz"
intitle:"index of" "dist.tgz"
intitle:"index of" "dist.tar.gz"
intitle:"index of" "dist.bz2"
intitle:"index of" "dist.xz"
intitle:"index of" "dist.cab"
intitle:"index of" "build.zip"
intitle:"index of" "build.rar"
intitle:"index of" "build.7z"
intitle:"index of" "build.tar"
intitle:"index of" "build.gz"
intitle:"index of" "build.tgz"
intitle:"index of" "build.tar.gz"
intitle:"index of" "build.bz2"
intitle:"index of" "build.xz"
intitle:"index of" "build.cab"
intitle:"index of" "full.zip"
intitle:"index of" "full.rar"
intitle:"index of" "full.7z"
intitle:"index of" "full.tar"
intitle:"index of" "full.gz"
intitle:"index of" "full.tgz"
intitle:"index of" "full.tar.gz"
intitle:"index of" "full.bz2"
intitle:"index of" "full.xz"
intitle:"index of" "full.cab"
intitle:"index of" "full_backup.zip"
intitle:"index of" "full_backup.rar"
intitle:"index of" "full_backup.7z"
intitle:"index of" "full_backup.tar"
intitle:"index of" "full_backup.gz"
intitle:"index of" "full_backup.tgz"
intitle:"index of" "full_backup.tar.gz"
intitle:"index of" "full_backup.bz2"
intitle:"index of" "full_backup.xz"
intitle:"index of" "full_backup.cab"
intitle:"index of" "db_backup.zip"
intitle:"index of" "db_backup.rar"
intitle:"index of" "db_backup.7z"
intitle:"index of" "db_backup.tar"
intitle:"index of" "db_backup.gz"
intitle:"index of" "db_backup.tgz"
intitle:"index of" "db_backup.tar.gz"
intitle:"index of" "db_backup.bz2"
intitle:"index of" "db_backup.xz"
intitle:"index of" "db_backup.cab"
intitle:"index of" "database.zip"
intitle:"index of" "database.rar"
intitle:"index of" "database.7z"
intitle:"index of" "database.tar"
intitle:"index of" "database.gz"
intitle:"index of" "database.tgz"
intitle:"index of" "database.tar.gz"
intitle:"index of" "database.bz2"
intitle:"index of" "database.xz"
intitle:"index of" "database.cab"
intitle:"index of" "home.zip"
intitle:"index of" "home.rar"
intitle:"index of" "home.7z"
intitle:"index of" "home.tar"
intitle:"index of" "home.gz"
intitle:"index of" "home.tgz"
intitle:"index of" "home.tar.gz"
intitle:"index of" "home.bz2"
intitle:"index of" "home.xz"
intitle:"index of" "home.cab"
```

> **Padrão:** Cópias de versão antiga por extensão de backup — 12 variações

```text
intitle:"index of" ext:bak
intitle:"index of" ext:old
intitle:"index of" ext:orig
intitle:"index of" ext:save
intitle:"index of" ext:sav
intitle:"index of" ext:tmp
intitle:"index of" ext:swp
intitle:"index of" ext:swo
intitle:"index of" ext:copy
intitle:"index of" ext:backup
intitle:"index of" ext:1
intitle:"index of" ext:~
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Repositórios de download legítimos** (releases de software) geram ruído em `.zip`/`.tar.gz`. Combine com `site:` do alvo ou com termos como `backup`/`public_html`.
- **`intitle:"index of"`** depende de *directory listing* habilitado. Muitos servidores retornam `403`/página customizada mesmo com o arquivo presente.
- Nomes de backup seguem **convenções previsíveis** (data, nome do domínio, nome do plugin) — é disso que a [Expansão](#-expansão-sistemática) tira proveito.
- Arquivos `.bak`/`.old`/`.php~` são servidos como **texto puro** quando o handler PHP não os processa, expondo o código-fonte.

<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Planilhas & CSV](planilhas-e-csv.md) · [Próximo: Dumps de Banco de Dados →](dumps-de-banco-de-dados.md)

</div>
