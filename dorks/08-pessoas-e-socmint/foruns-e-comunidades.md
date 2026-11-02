<div align="center">

[🏠 Hub](../../README.md) · [🧑 Pessoas & SOCMINT](README.md)

# 💬 Fóruns & Comunidades

*Técnica ampla de correlação de um **username** (não de um indivíduo nomeado) em fóruns, Q&A e comunidades — phpBB, Discourse, Disqus, Reddit e afins.*

</div>

---

> [!CAUTION]
> Esta página ensina a **técnica** de correlacionar um handle entre plataformas, com o placeholder `{username}`. Não a use para perseguir, expor ou perfilar uma pessoa específica — isso foge do escopo autorizado e pode ser crime. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Perfis e membros em fóruns

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:memberlist.php "{username}"` | Lista de membros phpBB/vBulletin | Google | 🟡 |
| `inurl:/u/ intitle:"profile" "{username}"` | Perfil em fórum Discourse | Google | 🟡 |
| `inurl:/members/ "{username}"` | Página de membro (vBulletin/XenForo) | Google | 🟡 |
| `inurl:/user/ "{username}" intext:"posts"` | Perfil com contagem de posts | Google | 🟡 |
| `site:disqus.com "{username}"` | Comentários via Disqus | Google | 🟡 |

### Q&A e comunidades técnicas

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `"{username}" (site:reddit.com OR site:quora.com)` | Handle em Reddit/Quora | Google | 🟡 |
| `"{username}" site:news.ycombinator.com` | Handle no Hacker News | Google | 🟢 |
| `"{username}" (site:superuser.com OR site:serverfault.com)` | Handle em Q&A técnico | Google | 🟢 |
| `inurl:/author/ "{username}"` | Páginas de autor (blogs/WordPress) | Google | 🟡 |
| `"@{username}" (site:t.me OR site:discord.com)` | Handle em Telegram/Discord | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `inurl:memberlist.php "{username}"` | `instreamset:url:memberlist.php "{username}"` | `inurl:memberlist.php {username}` |
| `site:disqus.com "{username}"` | `site:disqus.com "{username}"` | `site:disqus.com {username}` |
| `"{username}" site:news.ycombinator.com` | `"{username}" site:news.ycombinator.com` | `{username} site:news.ycombinator.com` |

> **Ferramentas dedicadas:** Sherlock, Maigret e WhatsMyName automatizam a correlação de username entre centenas de sites. Veja o [manual de metodologia & OPSEC](../../docs/manual/06-metodologia-recon-e-opsec.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Correlação de handle em fórum/comunidade (placeholder {username} = técnica) — 12 variações

```text
site:forums.he.net "{username}"
site:bitcointalk.org "{username}"
site:forum.xda-developers.com "{username}"
site:community.spiceworks.com "{username}"
site:community.cloudflare.com "{username}"
site:forum.unity.com "{username}"
site:discourse.org "{username}"
site:community.atlassian.com "{username}"
site:stackexchange.com "{username}"
site:answers.microsoft.com "{username}"
site:community.fortinet.com "{username}"
site:forums.docker.com "{username}"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `{username}` é **técnica**, não alvo: o objetivo é mostrar como um mesmo handle se espalha, não localizar uma pessoa real.
- `memberlist.php` e `/u/` revelam comunidades inteiras; muitos homônimos — valide contexto antes de qualquer conclusão.
- Correlação de username é **indício**, não prova de identidade: handles se repetem e são reusados por pessoas diferentes.
- Perfis em redes sociais estão em [perfis-em-redes-sociais](perfis-em-redes-sociais.md); aqui o foco é **fórum/comunidade**.

<div align="center">

[🏠 Hub](../../README.md) · [🧑 Pessoas & SOCMINT](README.md)

</div>
