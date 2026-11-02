<div align="center">

[🏠 Hub](../../README.md) · [🐛 Vulnerabilidades](README.md) · [← Arquivos & Endpoints Conhecidos](arquivos-e-endpoints-conhecidos.md)

# 🧯 Exposições por Classe

*Sinais de recon agrupados por classe de vulnerabilidade — open redirect, SSRF-prone, upload e debug. Sem payloads.*

</div>

---

> [!CAUTION]
> Sinal ≠ vulnerabilidade confirmada. **Não teste nem explore** sem autorização escrita. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Upload e manipulação de arquivo

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/upload intitle:"upload" site:alvo.com` | Formulários de upload | Google | 🟡 |
| `inurl:/fileupload OR inurl:/file-upload` | Endpoints de upload | Google | 🟡 |
| `intext:"Choose file to upload" site:alvo.com` | Páginas de upload genéricas | Google | 🟡 |
| `inurl:/uploads/ intitle:"index of"` | Pasta de uploads listável | Google | 🟡 |

### Debug e configuração aberta

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/debug=true` | Flag de debug na URL | Google | 🟡 |
| `inurl:/?test=1 OR inurl:/?debug=1` | Parâmetros de debug | Google | 🟡 |
| `intext:"display_errors" "On" inurl:php` | PHP exibindo erros | Google | 🟡 |
| `inurl:/.env inurl:/?` | `.env` acessível via parâmetro | Google | 🔴 |

### CORS, cabeçalhos e redirect

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:"redirect_uri=" inurl:oauth` | Redirect de OAuth (validação frouxa?) | Google | 🟡 |
| `inurl:"continue=" site:alvo.com` | Parâmetro de continuação | Google | 🟡 |
| `intext:"Access-Control-Allow-Origin: *"` | CORS permissivo em conteúdo | Google | 🟡 |
| `inurl:"/proxy?url="` | Proxy aberto (SSRF-prone) | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Shodan/FOFA |
|---|---|---|
| `inurl:/upload site:alvo.com` | `instreamset:url:/upload` | — |
| `inurl:"redirect_uri=" inurl:oauth` | `instreamset:url:"redirect_uri=" oauth` | — |
| `intext:"Access-Control-Allow-Origin: *"` | `inbody:"Access-Control-Allow-Origin: *"` | FOFA: `header="Access-Control-Allow-Origin: *"` |
| `inurl:"/proxy?url="` | `instreamset:url:"/proxy?url="` | — |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Endpoint de classe (upload/proxy/redirect) por URL — 10 variações

```text
inurl:/upload site:alvo.com
inurl:/fileupload site:alvo.com
inurl:/file-upload site:alvo.com
inurl:/import site:alvo.com
inurl:/proxy site:alvo.com
inurl:/fetch site:alvo.com
inurl:/redirect site:alvo.com
inurl:/forward site:alvo.com
inurl:/callback site:alvo.com
inurl:/oauth/authorize site:alvo.com
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- São **sinais de classe**: a presença de um formulário de upload ou de `redirect_uri=` não prova vulnerabilidade.
- `CORS *` pode ser intencional em APIs públicas — avalie o contexto.
- Nenhum payload aqui: confirmar exige teste manual **autorizado**; a exploração fica fora deste repositório.
- Proxies abertos (`/proxy?url=`) e `.env` acessível são 🔴 — reporte imediatamente.

<div align="center">

[🏠 Hub](../../README.md) · [🐛 Vulnerabilidades](README.md) · [← Arquivos & Endpoints Conhecidos](arquivos-e-endpoints-conhecidos.md)

</div>
