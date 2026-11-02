<div align="center">

[🏠 Hub](../../README.md) · [🇧🇷 Brasil](README.md) · [Próximo: Diários & Licitações →](diarios-e-licitacoes.md)

# 🏛 Governo & Transparência

*Portais do governo federal, estadual e municipal, transparência e dados abertos.*

</div>

---

> [!CAUTION]
> Fontes abertas por lei; dados pessoais seguem protegidos (LGPD). Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Governo federal (gov.br)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:gov.br filetype:pdf` | Documentos PDF do governo federal | Google | 🟢 |
| `site:gov.br filetype:xlsx` | Planilhas públicas | Google | 🟡 |
| `site:gov.br "relatório de gestão"` | Relatórios de gestão | Google | 🟢 |
| `site:gov.br inurl:/acesso-a-informacao` | Páginas da LAI | Google | 🟢 |
| `site:gov.br "ofício" filetype:pdf` | Ofícios publicados | Google | 🟢 |

### Transparência e dados abertos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:portaldatransparencia.gov.br` | Portal da Transparência federal | Google | 🟢 |
| `site:portaltransparencia.gov.br filetype:csv` | Dados em CSV | Google | 🟢 |
| `site:dados.gov.br filetype:csv` | Datasets abertos | Google | 🟢 |
| `inurl:transparencia site:gov.br filetype:csv` | Portais de transparência de órgãos | Google | 🟢 |
| `inurl:transparencia (site:*.gov.br) "servidores"` | Dados de pessoal (público) | Google | 🟡 |
| `site:*.gov.br "despesas" filetype:csv` | Despesas públicas | Google | 🟢 |

### Estados e municípios

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:*.sp.gov.br filetype:pdf` | Governo de São Paulo | Google | 🟢 |
| `site:*.rj.gov.br "edital"` | Editais do Rio de Janeiro | Google | 🟢 |
| `inurl:transparencia site:*.gov.br "remuneração"` | Remuneração de servidores (público) | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Yandex |
|---|---|---|
| `site:gov.br filetype:pdf` | `site:gov.br filetype:pdf` | `site:gov.br mime:pdf` |
| `site:dados.gov.br filetype:csv` | `site:dados.gov.br filetype:csv` | `site:dados.gov.br mime:csv` |
| `site:portaldatransparencia.gov.br` | `site:portaldatransparencia.gov.br` | `site:portaldatransparencia.gov.br` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Documento do governo federal por extensão — 8 variações

```text
site:gov.br filetype:csv
site:gov.br filetype:docx
site:gov.br filetype:odt
site:gov.br filetype:txt
site:gov.br filetype:rtf
site:gov.br filetype:pptx
site:gov.br filetype:xls
site:gov.br filetype:ods
```

> **Padrão:** Tema de transparência em domínio gov.br — 15 variações

```text
site:*.gov.br "relatório de gestão" filetype:pdf
site:*.gov.br "prestação de contas" filetype:pdf
site:*.gov.br "balanço" filetype:pdf
site:*.gov.br "despesas" filetype:pdf
site:*.gov.br "receitas" filetype:pdf
site:*.gov.br "convênio" filetype:pdf
site:*.gov.br "folha de pagamento" filetype:pdf
site:*.gov.br "diárias" filetype:pdf
site:*.gov.br "servidores" filetype:pdf
site:*.gov.br "nota de empenho" filetype:pdf
site:*.gov.br "ordem bancária" filetype:pdf
site:*.gov.br "suprimento de fundos" filetype:pdf
site:*.gov.br "portaria" filetype:pdf
site:*.gov.br "decreto" filetype:pdf
site:*.gov.br "lei orçamentária" filetype:pdf
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Domínios oficiais (2026-11):** `gov.br` (portal unificado), `portaldatransparencia.gov.br`, `dados.gov.br`. Estados usam `*.<uf>.gov.br`.
- Dados de remuneração/servidores são **públicos** por transparência, mas o uso deve respeitar finalidade e LGPD — não construa base para fins ilícitos.
- `transparencia` como subdomínio ou caminho varia por órgão; teste as duas formas.

<div align="center">

[🏠 Hub](../../README.md) · [🇧🇷 Brasil](README.md) · [Próximo: Diários & Licitações →](diarios-e-licitacoes.md)

</div>
