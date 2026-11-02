<div align="center">

[🏠 Hub](../../README.md) · [🇧🇷 Brasil](README.md)

# 🏢 Empresas & CNPJ

*Fontes públicas sobre pessoas jurídicas brasileiras — CNPJ, quadro societário, juntas comerciais e bases abertas de empresas.*

</div>

---

> [!CAUTION]
> Dados cadastrais de empresa são, em grande parte, públicos; dados de sócios pessoas físicas são pessoais sob a LGPD. Use para due diligence e recon legítimo de **organizações**, não para perfilar indivíduos. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### CNPJ e cadastro

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `"CNPJ" "{empresa}" filetype:pdf site:gov.br` | Documento oficial citando CNPJ da empresa | Google | 🟢 |
| `intext:"Comprovante de Inscrição" intext:"CNPJ" filetype:pdf` | Cartão CNPJ em pasta aberta | Google | 🟡 |
| `site:cnpj.biz "{empresa}"` | Ficha pública de CNPJ | Google | 🟢 |
| `site:econodata.com.br "{empresa}"` | Dados empresariais Econodata | Google | 🟢 |
| `site:consultasocio.com "{empresa}"` | Vínculos societários públicos | Google | 🟡 |

### Societário e contábil

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"Quadro de Sócios e Administradores" filetype:pdf` | QSA em documento público | Google | 🟡 |
| `"razão social" "CNPJ" filetype:xlsx` | Planilha de empresas | Google | 🟡 |
| `intext:"contrato social" "{empresa}" filetype:pdf` | Contrato social publicado | Google | 🟡 |
| `site:*.gov.br intext:"balanço patrimonial" filetype:pdf` | Balanço de estatal/entidade | Google | 🟢 |
| `intitle:"index of" intext:"faturamento" ext:xlsx` | Planilha de faturamento exposta | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `site:cnpj.biz "{empresa}"` | `site:cnpj.biz "{empresa}"` | `site:cnpj.biz {empresa}` |
| `"razão social" "CNPJ" filetype:xlsx` | `"razão social" "CNPJ" ext:xlsx` | `"razão social" CNPJ filetype:xlsx` |
| `intext:"contrato social" filetype:pdf` | `"contrato social" ext:pdf` | `"contrato social" filetype:pdf` |

> **Dados abertos oficiais:** a Receita Federal publica a base de CNPJ; portais como dados.gov.br têm datasets. Combine com [governo-e-transparencia](governo-e-transparencia.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Ficha pública de empresa por host (placeholder {empresa}) — 4 variações

```text
site:empresascnpj.com "{empresa}"
site:cnpja.com "{empresa}"
site:casadosdados.com.br "{empresa}"
site:informecadastral.com.br "{empresa}"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `{empresa}` é placeholder — preencha com a razão social/nome fantasia do alvo autorizado.
- Portais de consulta (cnpj.biz, Econodata) agregam dado público; o QSA mistura PJ e **pessoas físicas** — respeite a LGPD quanto aos sócios.
- Planilhas de faturamento/contábil expostas são achado de má configuração → cruze com [01 · Exposição de Arquivos](../01-exposicao-de-arquivos/README.md).
- Para licitações e contratos com empresas, veja [diarios-e-licitacoes](diarios-e-licitacoes.md).

<div align="center">

[🏠 Hub](../../README.md) · [🇧🇷 Brasil](README.md)

</div>
