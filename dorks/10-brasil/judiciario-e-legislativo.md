<div align="center">

[🏠 Hub](../../README.md) · [🇧🇷 Brasil](README.md) · [← Diários & Licitações](diarios-e-licitacoes.md) · [Próximo: Educação & Saúde →](educacao-e-saude.md)

# ⚖ Judiciário & Legislativo

*Tribunais (`*.jus.br`), casas legislativas (`*.leg.br`) e normas públicas.*

</div>

---

> [!CAUTION]
> Processos públicos podem conter dados pessoais sensíveis; muitos correm em segredo de justiça. Respeite LGPD e sigilo processual. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Judiciário (`*.jus.br`)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:jus.br filetype:pdf "acórdão"` | Acórdãos publicados | Google | 🟢 |
| `site:*.jus.br "jurisprudência"` | Jurisprudência de tribunais | Google | 🟢 |
| `site:stf.jus.br filetype:pdf` | Supremo Tribunal Federal | Google | 🟢 |
| `site:stj.jus.br "súmula"` | Súmulas do STJ | Google | 🟢 |
| `site:*.jus.br "diário da justiça" filetype:pdf` | Diário da Justiça | Google | 🟢 |
| `site:*.trf*.jus.br "sentença"` | Sentenças de TRFs | Google | 🟡 |

### Legislativo (`*.leg.br`)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:camara.leg.br filetype:pdf` | Câmara dos Deputados | Google | 🟢 |
| `site:senado.leg.br "projeto de lei"` | Projetos de lei no Senado | Google | 🟢 |
| `site:*.leg.br "ata da sessão"` | Atas de sessões legislativas | Google | 🟢 |
| `site:planalto.gov.br inurl:/ccivil_03/ "LEI"` | Legislação federal (Planalto) | Google | 🟢 |
| `site:*.al.*.leg.br` | Assembleias legislativas estaduais | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Yandex |
|---|---|---|
| `site:jus.br filetype:pdf "acórdão"` | `site:jus.br filetype:pdf "acórdão"` | `site:jus.br mime:pdf "acórdão"` |
| `site:camara.leg.br filetype:pdf` | `site:camara.leg.br filetype:pdf` | `site:camara.leg.br mime:pdf` |
| `site:planalto.gov.br inurl:/ccivil_03/` | `site:planalto.gov.br instreamset:url:/ccivil_03/` | `site:planalto.gov.br url:/ccivil_03/` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Documento judiciário por termo — 9 variações

```text
site:*.jus.br "acórdão" filetype:pdf
site:*.jus.br "sentença" filetype:pdf
site:*.jus.br "despacho" filetype:pdf
site:*.jus.br "jurisprudência" filetype:pdf
site:*.jus.br "súmula" filetype:pdf
site:*.jus.br "pauta de julgamento" filetype:pdf
site:*.jus.br "edital de intimação" filetype:pdf
site:*.jus.br "precatório" filetype:pdf
site:*.jus.br "recurso especial" filetype:pdf
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Domínios (2026-11):** judiciário usa `*.jus.br` (ex.: `stf.jus.br`, `tjsp.jus.br`); legislativo usa `*.leg.br` (`camara.leg.br`, `senado.leg.br`); legislação federal em `planalto.gov.br/ccivil_03`.
- **Segredo de justiça:** nunca contorne sigilo processual; processos restritos não são fonte aberta.
- Documentos judiciais podem conter dados pessoais sensíveis — minimize e respeite a LGPD e a resolução de privacidade do CNJ.

<div align="center">

[🏠 Hub](../../README.md) · [🇧🇷 Brasil](README.md) · [← Diários & Licitações](diarios-e-licitacoes.md) · [Próximo: Educação & Saúde →](educacao-e-saude.md)

</div>
