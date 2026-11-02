<div align="center">

[🏠 Hub](../../README.md) · [🏛 Setores Regulados & Nichos](README.md) · [← Educação & EAD](educacao-e-ead.md) · [Próximo: Imobiliário & Automotivo →](imobiliario-e-automotivo.md)

# 🏛 Governo Local & ONGs

*Portais de transparência, ERPs municipais, sistemas de protocolo e plataformas de ONGs (CiviCRM) expostos — foco no sistema, não nos dados do cidadão.*

</div>

---

> [!CAUTION]
> Sistemas públicos e de ONGs guardam dados de cidadãos e doadores. Identificar o sistema exposto é recon; acessar dados pessoais não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Transparência e ERP municipal

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Portal da Transparência" -site:gov.br` | Portais de transparência (fora gov.br) | Google | 🟢 |
| `intitle:"1Doc" inurl:/login` | Sistema de protocolo 1Doc | Google | 🟡 |
| `intitle:"IPM Sistemas" inurl:/atende` | ERP municipal IPM/Atende | Google | 🟡 |
| `inurl:/e-sic intitle:"login"` | Sistema de acesso à informação (e-SIC) | Google | 🟡 |
| `intitle:"Governa" inurl:/portal` | ERP público Governa | Google | 🟡 |

### Sistemas de ONGs e conselhos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/civicrm/login` | Login do CiviCRM (ONGs) | Google | 🔴 |
| `intitle:"CiviCRM"` | Plataforma CiviCRM | Google | 🟡 |
| `inurl:/portal intext:"conselho" intext:"deliberação"` | Portal de conselho/colegiado | Google | 🟢 |
| `intitle:"index of" intext:"prestacao-de-contas"` | Prestação de contas em pasta aberta | Google | 🟡 |
| `intitle:"OpenCities" OR intext:"powered by OpenCities"` | CMS de governo OpenCities | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `intitle:"Portal da Transparência" -site:gov.br` | `intitle:"Portal da Transparência" -site:gov.br` | `intitle:"Portal da Transparência"` |
| `inurl:/civicrm/login` | `instreamset:url:/civicrm/login` | `inurl:civicrm/login` |
| `intitle:"1Doc" inurl:/login` | `intitle:"1Doc"` | `intitle:1Doc login` |
| `intitle:"CiviCRM"` | `intitle:"CiviCRM"` | `intitle:CiviCRM` |

> **Fronteira:** `*.gov.br` e sistemas públicos brasileiros específicos estão em [10 · Brasil](../10-brasil/README.md). Aqui, o **software do setor** de forma geral (incluindo internacional e municípios menores sob outros domínios).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Sistema de governo local/ONG por título — 6 variações

```text
intitle:"1Doc"
intitle:"IPM Sistemas"
intitle:"Governa"
intitle:"OpenCities"
intitle:"Betha Sistemas"
intitle:"Fiorilli"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Portais de transparência são **públicos por lei** — baixo risco; o interessante é o **módulo administrativo** exposto por engano.
- CiviCRM (ONGs) guarda doadores e beneficiários — o login exposto é o achado; não acesse os cadastros.
- ERPs municipais (`1Doc`, `IPM/Atende`, `Governa`) concentram protocolo, RH e finanças da prefeitura — alvo de alto valor; reporte exposição administrativa.
- Prefeituras `*.gov.br` ficam em [10 · Brasil](../10-brasil/README.md); aqui priorize o produto/sistema e o escopo internacional.

<div align="center">

[🏠 Hub](../../README.md) · [🏛 Setores Regulados & Nichos](README.md) · [← Educação & EAD](educacao-e-ead.md) · [Próximo: Imobiliário & Automotivo →](imobiliario-e-automotivo.md)

</div>
