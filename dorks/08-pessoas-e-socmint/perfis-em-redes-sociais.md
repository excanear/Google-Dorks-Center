<div align="center">

[🏠 Hub](../../README.md) · [👥 Pessoas & SOCMINT](README.md) · [Próximo: Usernames & Identidades →](usernames-e-identidades.md)

# 🔎 Perfis em Redes Sociais

*Padrões para localizar perfis públicos por rede — como técnica ampla de enumeração, nunca para mirar um indivíduo.*

</div>

---

> [!CAUTION]
> Use só com finalidade legítima e autorizada (LGPD/GDPR). Os placeholders são genéricos; **não** adapte isto para perseguir uma pessoa. Leia o [limite ético da categoria](README.md#-limite-ético-desta-categoria).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Perfis por rede (padrão)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:linkedin.com/in "{cargo}" "{cidade}"` | Perfis profissionais por cargo/cidade | Google | 🟡 |
| `site:twitter.com "{termo}"` | Perfis/posts no X/Twitter | Google | 🟡 |
| `site:instagram.com "{termo}"` | Perfis no Instagram | Google | 🟡 |
| `site:facebook.com inurl:/people/ "{termo}"` | Diretório de pessoas do Facebook | Google | 🟡 |
| `site:github.com inurl:/ "{tecnologia}"` | Perfis de desenvolvedores por skill | Google | 🟢 |
| `site:about.me "{termo}"` | Páginas pessoais about.me | Google | 🟡 |
| `site:t.me "{termo}"` | Canais/perfis públicos no Telegram | Google | 🟡 |

### Diretórios e agregadores

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `(site:linktr.ee OR site:bio.link) "{termo}"` | Agregadores de links de bio | Google | 🟡 |
| `site:keybase.io "{termo}"` | Identidades verificadas Keybase | Google | 🟢 |
| `site:gravatar.com "{termo}"` | Perfis Gravatar por e-mail/username | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo (bang) |
|---|---|---|
| `site:linkedin.com/in "{cargo}"` | `site:linkedin.com/in "{cargo}"` | `!ddg site:linkedin.com/in {cargo}` |
| `site:twitter.com "{termo}"` | `site:twitter.com "{termo}"` | `!tw {termo}` |
| `site:instagram.com "{termo}"` | `site:instagram.com "{termo}"` | `site:instagram.com {termo}` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Enumeração de perfis por rede (placeholder {termo} = categoria ampla) — 18 variações

```text
site:linkedin.com/in "{termo}"
site:facebook.com "{termo}"
site:youtube.com "{termo}"
site:pinterest.com "{termo}"
site:tumblr.com "{termo}"
site:mastodon.social "{termo}"
site:bsky.app "{termo}"
site:vk.com "{termo}"
site:threads.net "{termo}"
site:flickr.com "{termo}"
site:ok.ru "{termo}"
site:xing.com "{termo}"
site:snapchat.com "{termo}"
site:kwai.com "{termo}"
site:linktr.ee "{termo}"
site:beacons.ai "{termo}"
site:gettr.com "{termo}"
site:truthsocial.com "{termo}"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Os placeholders `{cargo}`, `{cidade}`, `{termo}`, `{tecnologia}` representam **categorias amplas** de investigação, não uma pessoa.
- Muitas redes **bloqueiam indexação** de perfis; o buscador vê só o que está público e indexado.
- Para username OSINT em escala, Sherlock/Maigret (ver OSINT Ultimate Hub) complementam estes dorks.
- Minimize e documente a base legal: perfil público ainda é dado pessoal sob LGPD/GDPR.

<div align="center">

[🏠 Hub](../../README.md) · [👥 Pessoas & SOCMINT](README.md) · [Próximo: Usernames & Identidades →](usernames-e-identidades.md)

</div>
