<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Chaves & Certificados](chaves-e-certificados.md)

# 📂 Diretórios Abertos (Open Directory Listing)

*Listagens de diretório habilitadas que expõem o conteúdo bruto de pastas no servidor — a porta de entrada para a maioria dos achados desta categoria.*

</div>

---

> [!CAUTION]
> Um diretório listável pode expor backups, dumps, logs e chaves de uma só vez. Navegar na listagem é passivo; baixar arquivos sensíveis sem autorização não é. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Assinaturas de listagem por servidor

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of /"` | Listagem genérica (Apache/Nginx) | Google, Bing | 🟡 |
| `intitle:"index of /" "parent directory"` | Listagem clássica do Apache | Google | 🟡 |
| `intitle:"index of /" "last modified" "size"` | Listagem com colunas padrão | Google | 🟡 |
| `intitle:"index of /" "server at"` | Rodapé do mod_autoindex do Apache | Google | 🟡 |
| `"Directory listing for /" "Python"` | Listagem do http.server do Python | Google | 🟡 |
| `intitle:"Index of" "cgi-bin"` | Listagem expondo /cgi-bin | Google | 🟡 |

### Diretórios sensíveis por nome

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "/admin"` | Pasta administrativa listável | Google | 🟡 |
| `intitle:"index of" "/private"` | Pasta "private" exposta | Google | 🔴 |
| `intitle:"index of" "/backup"` | Pasta de backup | Google | 🔴 |
| `intitle:"index of" "/config"` | Pasta de configuração | Google | 🔴 |
| `intitle:"index of" "/db" OR "/database"` | Pasta de banco de dados | Google | 🔴 |
| `intitle:"index of" "/uploads"` | Pasta de uploads de usuários | Google | 🟡 |
| `intitle:"index of" "/.git"` | Repositório Git exposto | Google | 🔴 |
| `intitle:"index of" "/.svn"` | Repositório SVN exposto | Google | 🔴 |
| `intitle:"index of" "/secret" OR "/secrets"` | Pasta de segredos | Google | 🔴 |
| `intitle:"index of" "/credentials"` | Pasta de credenciais | Google | 🔴 |

### Mídia e dados pessoais em listagens

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "/docs" "confidential"` | Documentos confidenciais listados | Google | 🔴 |
| `intitle:"index of" "scans" OR "scanned"` | Documentos digitalizados ⚠ | Google | 🔴 |
| `intitle:"index of" "invoices"` | Faturas em pasta aberta | Google | 🟡 |
| `intitle:"index of" "contracts"` | Contratos em pasta aberta | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | Yandex |
|---|---|---|---|
| `intitle:"index of /"` | `intitle:"index of /"` | `intitle:"index of /"` | `title:"index of /"` |
| `intitle:"index of" "/.git"` | `intitle:"index of" "/.git"` | `intitle:"index of" "/.git"` | `title:"index of" "/.git"` |
| `"Directory listing for /" "Python"` | `"Directory listing for /" Python` | `"Directory listing for /" Python` | `"Directory listing for /" Python` |
| `intitle:"index of" "/backup"` | `intitle:"index of" "/backup"` | `intitle:"index of" "/backup"` | `title:"index of" "/backup"` |

> Em buscadores de infraestrutura, directory listings aparecem por título HTTP — por exemplo, no Shodan: `http.title:"Index of /"`. Veja o [manual de infraestrutura](../../docs/manual/03-buscadores-de-infraestrutura.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Listagem de diretório por pasta sensível — 17 variações

```text
intitle:"index of" "/conf"
intitle:"index of" "/secret"
intitle:"index of" "/secrets"
intitle:"index of" "/db"
intitle:"index of" "/database"
intitle:"index of" "/dump"
intitle:"index of" "/dumps"
intitle:"index of" "/upload"
intitle:"index of" "/files"
intitle:"index of" "/data"
intitle:"index of" "/tmp"
intitle:"index of" "/temp"
intitle:"index of" "/archive"
intitle:"index of" "/storage"
intitle:"index of" "/export"
intitle:"index of" "/internal"
intitle:"index of" "/restricted"
```

> **Padrão:** Listagem de diretório por pasta sensível × termo de confidencialidade — 59 variações

```text
intitle:"index of" "/docs" "confidencial"
intitle:"index of" "/docs" "uso interno"
intitle:"index of" "/docs" "internal use only"
intitle:"index of" "/docs" "não divulgar"
intitle:"index of" "/docs" "do not distribute"
intitle:"index of" "/docs" "strictly confidential"
intitle:"index of" "/docs" "proprietary"
intitle:"index of" "/docs" "restrito"
intitle:"index of" "/docs" "restricted"
intitle:"index of" "/docs" "sigiloso"
intitle:"index of" "/docs" "private and confidential"
intitle:"index of" "/documents" "confidencial"
intitle:"index of" "/documents" "confidential"
intitle:"index of" "/documents" "uso interno"
intitle:"index of" "/documents" "internal use only"
intitle:"index of" "/documents" "não divulgar"
intitle:"index of" "/documents" "do not distribute"
intitle:"index of" "/documents" "strictly confidential"
intitle:"index of" "/documents" "proprietary"
intitle:"index of" "/documents" "restrito"
intitle:"index of" "/documents" "restricted"
intitle:"index of" "/documents" "sigiloso"
intitle:"index of" "/documents" "private and confidential"
intitle:"index of" "/files" "confidencial"
intitle:"index of" "/files" "confidential"
intitle:"index of" "/files" "uso interno"
intitle:"index of" "/files" "internal use only"
intitle:"index of" "/files" "não divulgar"
intitle:"index of" "/files" "do not distribute"
intitle:"index of" "/files" "strictly confidential"
intitle:"index of" "/files" "proprietary"
intitle:"index of" "/files" "restrito"
intitle:"index of" "/files" "restricted"
intitle:"index of" "/files" "sigiloso"
intitle:"index of" "/files" "private and confidential"
intitle:"index of" "/data" "confidencial"
intitle:"index of" "/data" "confidential"
intitle:"index of" "/data" "uso interno"
intitle:"index of" "/data" "internal use only"
intitle:"index of" "/data" "não divulgar"
intitle:"index of" "/data" "do not distribute"
intitle:"index of" "/data" "strictly confidential"
intitle:"index of" "/data" "proprietary"
intitle:"index of" "/data" "restrito"
intitle:"index of" "/data" "restricted"
intitle:"index of" "/data" "sigiloso"
intitle:"index of" "/data" "private and confidential"
intitle:"index of" "/private" "confidencial"
intitle:"index of" "/private" "confidential"
intitle:"index of" "/private" "uso interno"
intitle:"index of" "/private" "internal use only"
intitle:"index of" "/private" "não divulgar"
intitle:"index of" "/private" "do not distribute"
intitle:"index of" "/private" "strictly confidential"
intitle:"index of" "/private" "proprietary"
intitle:"index of" "/private" "restrito"
intitle:"index of" "/private" "restricted"
intitle:"index of" "/private" "sigiloso"
intitle:"index of" "/private" "private and confidential"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Mirrors e repositórios públicos** (CRAN, APT, CDNs) são *index of* legítimos — o maior ruído desta página. Combine com um nome de pasta sensível ou com `site:` do alvo.
- O título varia por servidor: Apache usa `Index of /`, o `http.server` do Python usa `Directory listing for /`, IIS e Nginx diferem. Teste as variações.
- Uma listagem indexada pode já ter sido **desabilitada** — confirme o estado atual antes de reportar, e preserve a evidência pelo [Wayback Machine](https://web.archive.org/).
- `.git`/`.svn` em listagem permitem reconstruir o repositório inteiro; trate como alto risco e aponte para **Vulnerabilidades** (Fase 3) quando houver exploração associada.

<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Chaves & Certificados](chaves-e-certificados.md)

</div>
