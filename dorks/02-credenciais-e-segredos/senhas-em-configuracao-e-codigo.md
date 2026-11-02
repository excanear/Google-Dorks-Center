<div align="center">

[🏠 Hub](../../README.md) · [🔑 Credenciais & Segredos](README.md) · [← Tokens de API](tokens-de-api.md) · [Próximo: .htpasswd & Auth Básica →](htpasswd-e-auth-basica.md)

# 🔏 Senhas em Configuração e Código

*Senhas e strings de conexão em claro dentro de arquivos de configuração, código-fonte e dumps de ambiente.*

</div>

---

> [!CAUTION]
> Senha em claro em config/código concede acesso direto a bancos e serviços. Reporte para rotação; não use. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Strings de conexão

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"jdbc:mysql://" "password"` | String JDBC MySQL com senha | Google | 🔴 |
| `intext:"jdbc:postgresql://" "password"` | String JDBC PostgreSQL | Google | 🔴 |
| `intext:"mongodb://" "@" -example` | URI MongoDB com credencial embutida | Google | 🔴 |
| `intext:"mysql://" "@" ext:env` | URL de conexão MySQL em `.env` | Google | 🔴 |
| `ext:config "connectionString" "Password="` | web.config com senha | Google | 🔴 |
| `intext:"Data Source=" "Password=" ext:config` | Connection string .NET | Google | 🔴 |
| `intext:"postgres://" "@" ext:yml` | URL Postgres em YAML | Google | 🔴 |

### Senhas em código-fonte

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `ext:php "define('DB_PASSWORD'"` | Constante de senha em PHP | Google | 🔴 |
| `ext:php "$password =" -example` | Variável de senha em PHP | Google | 🔴 |
| `ext:py "PASSWORD =" "DATABASES"` | settings.py do Django com senha | Google | 🔴 |
| `ext:rb "password:" "production"` | database.yml do Rails | Google | 🔴 |
| `ext:js "password:" "host:" "user:"` | Config de conexão em Node | Google | 🔴 |
| `intext:"password" ext:inc` | Includes PHP servidos como texto | Google | 🔴 |

### Dumps e configs genéricos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `ext:ini "password=" -sample` | `.ini` com senha | Google | 🔴 |
| `ext:yaml "password:" -example` | YAML com senha | Google | 🔴 |
| `ext:json "password" "username" -schema` | JSON de credenciais | Google | 🔴 |
| `ext:cfg "password"` | Arquivo `.cfg` com senha | Google | 🟡 |
| `intext:"SA_PASSWORD" ext:yml` | Senha do SQL Server em compose | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | GitHub Code Search |
|---|---|---|---|
| `intext:"jdbc:mysql://" "password"` | `"jdbc:mysql://" password` | `"jdbc:mysql://" password` | `content:jdbc:mysql:// password` |
| `ext:php "define('DB_PASSWORD'"` | `ext:php "define('DB_PASSWORD'"` | `filetype:php "DB_PASSWORD"` | `/define\('DB_PASSWORD'/ language:php` |
| `intext:"mongodb://" "@"` | `"mongodb://" "@"` | `"mongodb://" "@"` | `/mongodb:\/\/[^ ]+:[^ ]+@/` |
| `ext:config "connectionString" "Password="` | `ext:config connectionString "Password="` | `filetype:config connectionString` | `path:*.config connectionString Password=` |
| `ext:py "PASSWORD =" "DATABASES"` | `ext:py "PASSWORD =" DATABASES` | `filetype:py PASSWORD DATABASES` | `path:settings.py PASSWORD DATABASES` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Campo de senha/segredo × extensão de código/config — 120 variações

```text
ext:php intext:"password"
ext:php intext:"passwd"
ext:php intext:"pwd"
ext:php intext:"db_password"
ext:php intext:"secret"
ext:php intext:"api_secret"
ext:php intext:"private_key"
ext:php intext:"client_secret"
ext:py intext:"password"
ext:py intext:"passwd"
ext:py intext:"pwd"
ext:py intext:"db_password"
ext:py intext:"secret"
ext:py intext:"api_secret"
ext:py intext:"private_key"
ext:py intext:"client_secret"
ext:rb intext:"password"
ext:rb intext:"passwd"
ext:rb intext:"pwd"
ext:rb intext:"db_password"
ext:rb intext:"secret"
ext:rb intext:"api_secret"
ext:rb intext:"private_key"
ext:rb intext:"client_secret"
ext:js intext:"password"
ext:js intext:"passwd"
ext:js intext:"pwd"
ext:js intext:"db_password"
ext:js intext:"secret"
ext:js intext:"api_secret"
ext:js intext:"private_key"
ext:js intext:"client_secret"
ext:ts intext:"password"
ext:ts intext:"passwd"
ext:ts intext:"pwd"
ext:ts intext:"db_password"
ext:ts intext:"secret"
ext:ts intext:"api_secret"
ext:ts intext:"private_key"
ext:ts intext:"client_secret"
ext:java intext:"password"
ext:java intext:"passwd"
ext:java intext:"pwd"
ext:java intext:"db_password"
ext:java intext:"secret"
ext:java intext:"api_secret"
ext:java intext:"private_key"
ext:java intext:"client_secret"
ext:yml intext:"password"
ext:yml intext:"passwd"
ext:yml intext:"pwd"
ext:yml intext:"db_password"
ext:yml intext:"secret"
ext:yml intext:"api_secret"
ext:yml intext:"private_key"
ext:yml intext:"client_secret"
ext:yaml intext:"password"
ext:yaml intext:"passwd"
ext:yaml intext:"pwd"
ext:yaml intext:"db_password"
ext:yaml intext:"secret"
ext:yaml intext:"api_secret"
ext:yaml intext:"private_key"
ext:yaml intext:"client_secret"
ext:ini intext:"password"
ext:ini intext:"passwd"
ext:ini intext:"pwd"
ext:ini intext:"db_password"
ext:ini intext:"secret"
ext:ini intext:"api_secret"
ext:ini intext:"private_key"
ext:ini intext:"client_secret"
ext:json intext:"password"
ext:json intext:"passwd"
ext:json intext:"pwd"
ext:json intext:"db_password"
ext:json intext:"secret"
ext:json intext:"api_secret"
ext:json intext:"private_key"
ext:json intext:"client_secret"
ext:xml intext:"password"
ext:xml intext:"passwd"
ext:xml intext:"pwd"
ext:xml intext:"db_password"
ext:xml intext:"secret"
ext:xml intext:"api_secret"
ext:xml intext:"private_key"
ext:xml intext:"client_secret"
ext:inc intext:"password"
ext:inc intext:"passwd"
ext:inc intext:"pwd"
ext:inc intext:"db_password"
ext:inc intext:"secret"
ext:inc intext:"api_secret"
ext:inc intext:"private_key"
ext:inc intext:"client_secret"
ext:cfg intext:"password"
ext:cfg intext:"passwd"
ext:cfg intext:"pwd"
ext:cfg intext:"db_password"
ext:cfg intext:"secret"
ext:cfg intext:"api_secret"
ext:cfg intext:"private_key"
ext:cfg intext:"client_secret"
ext:conf intext:"password"
ext:conf intext:"passwd"
ext:conf intext:"pwd"
ext:conf intext:"db_password"
ext:conf intext:"secret"
ext:conf intext:"api_secret"
ext:conf intext:"private_key"
ext:conf intext:"client_secret"
ext:properties intext:"password"
ext:properties intext:"passwd"
ext:properties intext:"pwd"
ext:properties intext:"db_password"
ext:properties intext:"secret"
ext:properties intext:"api_secret"
ext:properties intext:"private_key"
ext:properties intext:"client_secret"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Código de exemplo/boilerplate** usa `password = "your_password_here"`. A exclusão `-example -sample -your_` reduz o ruído.
- Strings de conexão com `@` podem ser **ilustrativas**; confirme que há host e credencial reais.
- `ext:inc` e `.php~`/`.php.bak` são servidos como texto quando o handler não processa — ver também [01 · Backups](../01-exposicao-de-arquivos/backups-e-arquivos-compactados.md).
- Em código-fonte, GitHub Code Search com regex casa o padrão credencial-no-código melhor que buscadores web.

<div align="center">

[🏠 Hub](../../README.md) · [🔑 Credenciais & Segredos](README.md) · [← Tokens de API](tokens-de-api.md) · [Próximo: .htpasswd & Auth Básica →](htpasswd-e-auth-basica.md)

</div>
