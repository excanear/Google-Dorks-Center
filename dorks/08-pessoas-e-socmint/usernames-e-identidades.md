<div align="center">

[🏠 Hub](../../README.md) · [👥 Pessoas & SOCMINT](README.md) · [← Perfis em Redes Sociais](perfis-em-redes-sociais.md) · [Próximo: Conteúdo Público & Posts →](conteudo-publico-e-posts.md)

# 🪪 Usernames & Identidades

*Correlacionar um mesmo username entre plataformas — técnica de pivô de identidade, aplicada só a investigações autorizadas.*

</div>

---

> [!CAUTION]
> Correlação de identidade é potente e sensível. Use com finalidade legítima e minimização (LGPD/GDPR); **jamais** para doxxing ou perseguição. Leia o [limite ético da categoria](README.md#-limite-ético-desta-categoria).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Mesmo username entre plataformas

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `"{username}" (site:github.com OR site:gitlab.com)` | Username em plataformas de código | Google | 🟡 |
| `"{username}" (site:reddit.com OR site:news.ycombinator.com)` | Username em comunidades | Google | 🟡 |
| `inurl:{username} (site:twitter.com OR site:instagram.com)` | Perfil por username na URL | Google | 🟡 |
| `"{username}" site:keybase.io` | Identidade verificada | Google | 🟢 |
| `intext:"{username}" site:pastebin.com` | Username em pastes | Google | 🟡 |

### Identidade via artefatos públicos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `"{username}" site:gravatar.com` | Gravatar associado | Google | 🟡 |
| `"{username}" (ext:asc OR "PGP")` | Chave PGP pública com identidade | Google | 🟢 |
| `"{username}" site:hackerone.com OR site:bugcrowd.com` | Perfil de pesquisador de segurança | Google | 🟢 |
| `"{username}" site:medium.com OR site:dev.to` | Autoria em blogs técnicos | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | GitHub Code Search |
|---|---|---|
| `"{username}" site:github.com` | `"{username}" site:github.com` | `user:{username}` |
| `inurl:{username} site:twitter.com` | `instreamset:url:{username} site:twitter.com` | — |
| `"{username}" site:pastebin.com` | `"{username}" site:pastebin.com` | — |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Correlação de username por plataforma (placeholder {username} = técnica) — 20 variações

```text
"{username}" site:github.com
"{username}" site:gitlab.com
"{username}" site:reddit.com
"{username}" site:medium.com
"{username}" site:dev.to
"{username}" site:hackerone.com
"{username}" site:bugcrowd.com
"{username}" site:stackoverflow.com
"{username}" site:behance.net
"{username}" site:dribbble.com
"{username}" site:twitch.tv
"{username}" site:producthunt.com
"{username}" site:devpost.com
"{username}" site:replit.com
"{username}" site:codepen.io
"{username}" site:kaggle.com
"{username}" site:last.fm
"{username}" site:goodreads.com
"{username}" site:steamcommunity.com
"{username}" site:discord.com/users
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `{username}` é um **placeholder de técnica** — a correlação só é legítima dentro de uma investigação autorizada.
- Usernames comuns geram muitos **homônimos**: correlação exige corroboração (foto, bio, datas), nunca conclusão por nome igual.
- Ferramentas dedicadas (Sherlock, Maigret, WhatsMyName) fazem isto em escala — estes dorks são o complemento manual.
- Minimização: colete só o que a finalidade exige.

<div align="center">

[🏠 Hub](../../README.md) · [👥 Pessoas & SOCMINT](README.md) · [← Perfis em Redes Sociais](perfis-em-redes-sociais.md) · [Próximo: Conteúdo Público & Posts →](conteudo-publico-e-posts.md)

</div>
