<div align="center">

[🏠 Hub](../../README.md) · [🔑 Credenciais & Segredos](README.md) · [← Senhas em Config & Código](senhas-em-configuracao-e-codigo.md) · [Próximo: Secrets em Frontend & JS →](secrets-em-frontend-e-js.md)

# 🚪 .htpasswd & Auth Básica

*Arquivos de autenticação expostos: `.htpasswd`, `.netrc`, `.pgpass`, `auth.json` e afins, que guardam usuários e hashes/senhas.*

</div>

---

> [!CAUTION]
> Hashes expostos permitem ataque offline; credenciais em `.netrc`/`.pgpass` costumam estar em **texto puro**. Reporte para rotação. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Apache htpasswd / htaccess

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ".htpasswd"` | `.htpasswd` em diretório listável | Google, Bing | 🔴 |
| `inurl:/.htpasswd -intitle:"index of"` | `.htpasswd` servido direto | Google | 🔴 |
| `ext:htpasswd` | Arquivos `.htpasswd` indexados | Google | 🔴 |
| `filetype:htpasswd intext:":$apr1$"` | Hashes MD5-crypt do Apache | Google | 🔴 |
| `inurl:.htaccess "AuthUserFile"` | `.htaccess` apontando o htpasswd | Google | 🟡 |

### Credenciais de ferramentas em texto

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ".netrc"` | `.netrc` (login FTP/HTTP em texto) | Google | 🔴 |
| `intitle:"index of" ".pgpass"` | Senhas PostgreSQL em texto | Google | 🔴 |
| `intitle:"index of" ".my.cnf"` | Config MySQL com `password=` | Google | 🔴 |
| `inurl:auth.json "http-basic"` | `auth.json` do Composer com credenciais | Google | 🔴 |
| `intitle:"index of" ".git-credentials"` | Credenciais Git em texto | Google | 🔴 |
| `inurl:.npmrc "_authToken"` | Token de registry npm | Google | 🔴 |
| `inurl:.dockercfg OR inurl:.docker/config.json` | Credenciais de registry Docker | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | GitHub Code Search |
|---|---|---|---|
| `intitle:"index of" ".htpasswd"` | `intitle:"index of" ".htpasswd"` | `intitle:"index of" .htpasswd` | `path:.htpasswd` |
| `inurl:.npmrc "_authToken"` | `instreamset:url:.npmrc "_authToken"` | `inurl:.npmrc _authToken` | `path:.npmrc _authToken` |
| `inurl:auth.json "http-basic"` | `instreamset:url:auth.json http-basic` | `inurl:auth.json http-basic` | `path:auth.json http-basic` |
| `intitle:"index of" ".git-credentials"` | `intitle:"index of" ".git-credentials"` | `intitle:"index of" .git-credentials` | `path:.git-credentials` |
| `intitle:"index of" ".pgpass"` | `intitle:"index of" ".pgpass"` | `intitle:"index of" .pgpass` | `path:.pgpass` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Arquivo de autenticação em diretório aberto — 4 variações

```text
intitle:"index of" ".npmrc"
intitle:"index of" ".pypirc"
intitle:"index of" "auth.json"
intitle:"index of" ".dockercfg"
```

> **Padrão:** Arquivo de autenticação servido direto — 9 variações

```text
inurl:.htpasswd -intitle:"index of"
inurl:.netrc -intitle:"index of"
inurl:.pgpass -intitle:"index of"
inurl:.my.cnf -intitle:"index of"
inurl:.git-credentials -intitle:"index of"
inurl:.npmrc -intitle:"index of"
inurl:.pypirc -intitle:"index of"
inurl:auth.json -intitle:"index of"
inurl:.dockercfg -intitle:"index of"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `.htpasswd` guarda **hashes** (`$apr1$`, `$2y$`), não senha em claro — mesmo assim é alto risco (ataque offline).
- `.netrc`, `.pgpass`, `.my.cnf` e `.git-credentials` costumam ter credencial em **texto puro**.
- Muitos servidores bloqueiam arquivos `dot` por padrão; parte dos achados será apenas o **nome** no listing.
- `.htaccess`/`AuthUserFile` revela o **caminho** do htpasswd — pivô para o arquivo real.

<div align="center">

[🏠 Hub](../../README.md) · [🔑 Credenciais & Segredos](README.md) · [← Senhas em Config & Código](senhas-em-configuracao-e-codigo.md) · [Próximo: Secrets em Frontend & JS →](secrets-em-frontend-e-js.md)

</div>
