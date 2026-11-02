<div align="center">

[🏠 Hub](../../README.md) · [🇧🇷 Brasil](README.md) · [← Governo & Transparência](governo-e-transparencia.md) · [Próximo: Judiciário & Legislativo →](judiciario-e-legislativo.md)

# 📰 Diários & Licitações

*Diário Oficial da União, diários estaduais/municipais, licitações e compras públicas.*

</div>

---

> [!CAUTION]
> Fontes públicas; respeite LGPD quanto a dados pessoais em publicações. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Diário Oficial

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:in.gov.br` | Imprensa Nacional / DOU | Google | 🟢 |
| `site:in.gov.br "nomeação"` | Nomeações no DOU | Google | 🟢 |
| `site:in.gov.br "portaria" filetype:pdf` | Portarias | Google | 🟢 |
| `inurl:diariooficial filetype:pdf` | Diários oficiais estaduais/municipais | Google | 🟢 |
| `inurl:dom site:*.gov.br "diário oficial"` | Diário Oficial do Município | Google | 🟢 |

### Licitações e compras

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:gov.br/compras` | Compras.gov.br (ex-ComprasNet) | Google | 🟢 |
| `inurl:comprasnet site:gov.br` | Sistema de compras federal | Google | 🟢 |
| `site:*.gov.br "edital de licitação" filetype:pdf` | Editais de licitação | Google | 🟢 |
| `site:*.gov.br "pregão eletrônico" filetype:pdf` | Pregões eletrônicos | Google | 🟢 |
| `site:*.gov.br "ata de registro de preços"` | Atas de registro de preços | Google | 🟢 |
| `site:*.gov.br "contrato" "CNPJ" filetype:pdf` | Contratos públicos | Google | 🟡 |
| `site:pncp.gov.br` | Portal Nacional de Contratações Públicas | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Yandex |
|---|---|---|
| `site:in.gov.br "portaria"` | `site:in.gov.br "portaria"` | `site:in.gov.br "portaria"` |
| `site:*.gov.br "edital de licitação" filetype:pdf` | `site:gov.br "edital de licitação" filetype:pdf` | `site:gov.br "edital de licitação" mime:pdf` |
| `site:gov.br/compras` | `site:gov.br inurl:compras` | `site:gov.br url:compras` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Documento de licitação/compras por termo — 11 variações

```text
site:*.gov.br "tomada de preços" filetype:pdf
site:*.gov.br "concorrência pública" filetype:pdf
site:*.gov.br "ata de registro de preços" filetype:pdf
site:*.gov.br "dispensa de licitação" filetype:pdf
site:*.gov.br "termo de referência" filetype:pdf
site:*.gov.br "contrato administrativo" filetype:pdf
site:*.gov.br "carta convite" filetype:pdf
site:*.gov.br "credenciamento" filetype:pdf
site:*.gov.br "chamamento público" filetype:pdf
site:*.gov.br "inexigibilidade" filetype:pdf
site:*.gov.br "pregão presencial" filetype:pdf
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Fontes oficiais (2026-11):** `in.gov.br` (DOU), `gov.br/compras` (Compras.gov.br, ex-ComprasNet), `pncp.gov.br` (PNCP). Diários municipais usam domínios próprios variados.
- Contratos públicos citam **CNPJ** (empresa, não pessoa física) — informação pública; CPF de pessoas em documentos deve ser tratado com cuidado (LGPD).
- Editais e atas são ótimos para due diligence e jornalismo de dados.

<div align="center">

[🏠 Hub](../../README.md) · [🇧🇷 Brasil](README.md) · [← Governo & Transparência](governo-e-transparencia.md) · [Próximo: Judiciário & Legislativo →](judiciario-e-legislativo.md)

</div>
