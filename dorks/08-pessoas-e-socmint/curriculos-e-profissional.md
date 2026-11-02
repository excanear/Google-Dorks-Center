<div align="center">

[🏠 Hub](../../README.md) · [👥 Pessoas & SOCMINT](README.md) · [← Conteúdo Público & Posts](conteudo-publico-e-posts.md)

# 📄 Currículos & Profissional

*Currículos e portfólios públicos — como padrão de busca (ex.: por cargo/skill), nunca para mirar uma pessoa específica.*

</div>

---

> [!CAUTION]
> Currículos contêm dados pessoais (às vezes CPF, endereço, telefone). Minimize e respeite LGPD/GDPR; **não** compile base de pessoas. Leia o [limite ético da categoria](README.md#-limite-ético-desta-categoria).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Currículos em documentos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:pdf (intitle:"curriculum vitae" OR intitle:"resume") "{cargo}"` | Currículos por cargo | Google | 🟡 |
| `filetype:pdf "currículo" "{habilidade}"` | Currículos em PT por skill | Google | 🟡 |
| `(filetype:doc OR filetype:docx) "resume" "{tecnologia}"` | Currículos por tecnologia | Google | 🟡 |
| `filetype:pdf "references available upon request"` | Currículos em inglês (frase típica) | Google | 🟢 |
| `filetype:pdf "objetivo profissional" "{área}"` | Currículos por área | Google | 🟡 |

### Portfólios e perfis profissionais

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:linkedin.com/in "{cargo}" "{tecnologia}"` | Perfis por cargo+skill (amplo) | Google | 🟡 |
| `(site:behance.net OR site:dribbble.com) "{especialidade}"` | Portfólios de design | Google | 🟢 |
| `site:github.io "portfolio" "{tecnologia}"` | Portfólios de dev em Pages | Google | 🟢 |
| `site:read.cv "{cargo}"` | Currículos em read.cv | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Yandex |
|---|---|---|
| `filetype:pdf intitle:"curriculum vitae" "{cargo}"` | `filetype:pdf intitle:"curriculum vitae" "{cargo}"` | `mime:pdf title:"curriculum vitae"` |
| `filetype:pdf "currículo" "{habilidade}"` | `filetype:pdf "currículo"` | `mime:pdf "currículo"` |
| `site:linkedin.com/in "{cargo}"` | `site:linkedin.com/in "{cargo}"` | `site:linkedin.com/in "{cargo}"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Portfólio/currículo por plataforma — 11 variações

```text
site:github.io "portfolio" "{área}"
site:behance.net "portfolio" "{área}"
site:dribbble.com "portfolio" "{área}"
site:read.cv "portfolio" "{área}"
site:carrd.co "portfolio" "{área}"
site:notion.site "portfolio" "{área}"
site:journoportfolio.com "portfolio" "{área}"
site:contra.com "portfolio" "{área}"
site:polywork.com "portfolio" "{área}"
site:gitconnected.com "portfolio" "{área}"
site:super.site "portfolio" "{área}"
```

> **Padrão:** Currículo por extensão de documento — 4 variações

```text
filetype:pdf intitle:"curriculum vitae" "{cargo}"
filetype:doc intitle:"curriculum vitae" "{cargo}"
filetype:docx intitle:"curriculum vitae" "{cargo}"
filetype:odt intitle:"curriculum vitae" "{cargo}"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Os placeholders `{cargo}`, `{tecnologia}`, `{habilidade}`, `{área}` definem uma **busca por perfil amplo** (ex.: recrutamento, pesquisa de mercado), não uma pessoa.
- Currículos com **CPF/endereço/telefone** são dados sensíveis — se achar, trate como [01 · Planilhas & CSV](../01-exposicao-de-arquivos/planilhas-e-csv.md) manda (⚠ LGPD): não redistribua.
- Modelos e cursos de currículo são o maior ruído — exclua com `-modelo -template -curso`.

<div align="center">

[🏠 Hub](../../README.md) · [👥 Pessoas & SOCMINT](README.md) · [← Conteúdo Público & Posts](conteudo-publico-e-posts.md)

</div>
