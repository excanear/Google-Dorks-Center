<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Backups & Compactados](backups-e-arquivos-compactados.md) · [Próximo: Logs →](logs.md)

# 🗄 Dumps de Banco de Dados

*Exports SQL e dumps esquecidos no webroot: `.sql`, `.sql.gz`, `.dump`, `.bacpac`, e dumps gerados por ferramentas de administração.*

</div>

---

> [!CAUTION]
> Um dump de banco pode conter a base de dados **inteira**, incluindo hashes de senha e dados pessoais. Posse e uso podem ter restrições legais severas (LGPD, GDPR). Apenas localize e reporte; não baixe sem base legal. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Dumps SQL em diretórios abertos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ext:sql` | Diretórios abertos com arquivos .sql | Google, Bing | 🔴 |
| `intitle:"index of" "dump.sql"` | Dump SQL padrão | Google, Bing | 🔴 |
| `intitle:"index of" "backup.sql"` | Backup SQL nomeado | Google | 🔴 |
| `intitle:"index of" "database.sql"` | Export de banco | Google | 🔴 |
| `intitle:"index of" ext:sql "db"` | Dumps em pasta /db | Google | 🔴 |
| `intitle:"index of" "*.sql.gz"` | Dumps SQL compactados | Google | 🔴 |

### Assinaturas de conteúdo SQL

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `ext:sql "INSERT INTO" "VALUES"` | Dumps servidos como texto | Google | 🔴 |
| `ext:sql "CREATE TABLE" "users"` | Schema + tabela de usuários | Google | 🔴 |
| `ext:sql "DROP TABLE IF EXISTS"` | Cabeçalho típico de dump mysqldump | Google | 🟡 |
| `ext:sql "phpMyAdmin SQL Dump"` | Dumps exportados pelo phpMyAdmin | Google | 🔴 |
| `ext:sql "-- Server version"` | Cabeçalho de dump mysqldump | Google | 🟡 |
| `ext:sql "PostgreSQL database dump"` | Dumps do pg_dump | Google | 🔴 |

### Por ferramenta / plataforma

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/wp-content/ ext:sql` | Dumps dentro do WordPress | Google | 🔴 |
| `inurl:/backup/ ext:sql` | Dumps em pasta /backup | Google | 🔴 |
| `ext:bacpac` | Exports do Azure SQL / SQL Server | Google | 🔴 |
| `ext:mdf OR ext:ldf intitle:"index of"` | Arquivos de dados do SQL Server | Google | 🔴 |
| `ext:sqlite OR ext:db intitle:"index of"` | Bancos SQLite/embutidos listados | Google | 🔴 |
| `intitle:"index of" "adminer" ext:sql` | Exports feitos pelo Adminer | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | Yandex |
|---|---|---|---|
| `intitle:"index of" ext:sql` | `intitle:"index of" ext:sql` | `intitle:"index of" filetype:sql` | `title:"index of" mime:sql` |
| `ext:sql "INSERT INTO" "VALUES"` | `ext:sql "INSERT INTO"` | `filetype:sql "INSERT INTO"` | `mime:sql "INSERT INTO"` |
| `ext:sql "phpMyAdmin SQL Dump"` | `ext:sql "phpMyAdmin SQL Dump"` | `filetype:sql "phpMyAdmin SQL Dump"` | `mime:sql "phpMyAdmin SQL Dump"` |
| `ext:bacpac` | `ext:bacpac` | `filetype:bacpac` | `mime:bacpac` |
| `inurl:/backup/ ext:sql` | `instreamset:url:/backup/ ext:sql` | `inurl:backup filetype:sql` | `url:/backup/ mime:sql` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Dumps de banco em diretórios abertos, por extensão — 9 variações

```text
intitle:"index of" ext:sql.gz
intitle:"index of" ext:sql.zip
intitle:"index of" ext:dump
intitle:"index of" ext:bacpac
intitle:"index of" ext:mdf
intitle:"index of" ext:ldf
intitle:"index of" ext:sqlite
intitle:"index of" ext:sqlite3
intitle:"index of" ext:db
```

> **Padrão:** Dumps em pasta sensível × extensão — 27 variações

```text
inurl:/backup/ ext:sql.gz
inurl:/backup/ ext:dump
inurl:/backup/ ext:bacpac
inurl:/backups/ ext:sql
inurl:/backups/ ext:sql.gz
inurl:/backups/ ext:dump
inurl:/backups/ ext:bacpac
inurl:/db/ ext:sql
inurl:/db/ ext:sql.gz
inurl:/db/ ext:dump
inurl:/db/ ext:bacpac
inurl:/database/ ext:sql
inurl:/database/ ext:sql.gz
inurl:/database/ ext:dump
inurl:/database/ ext:bacpac
inurl:/dump/ ext:sql
inurl:/dump/ ext:sql.gz
inurl:/dump/ ext:dump
inurl:/dump/ ext:bacpac
inurl:/dumps/ ext:sql
inurl:/dumps/ ext:sql.gz
inurl:/dumps/ ext:dump
inurl:/dumps/ ext:bacpac
inurl:/sql/ ext:sql
inurl:/sql/ ext:sql.gz
inurl:/sql/ ext:dump
inurl:/sql/ ext:bacpac
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Tutoriais de SQL** e documentação usam `CREATE TABLE`/`INSERT INTO` como exemplo. Filtre por `site:` ou por extensão (`ext:sql`) para reduzir ruído.
- Dumps **compactados** (`.sql.gz`, `.sql.zip`) não têm o conteúdo indexado — só o nome do arquivo no listing. Mire o nome, não o conteúdo.
- Bancos **SQLite** (`.db`, `.sqlite`) às vezes são servidos como `application/octet-stream` e baixam direto; trate como achado de alto risco.
- Um dump localizado é uma **evidência** — registre URL, data e hash do snapshot (ex.: via Wayback) sem baixar o corpo, quando a política assim exigir.

<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Backups & Compactados](backups-e-arquivos-compactados.md) · [Próximo: Logs →](logs.md)

</div>
