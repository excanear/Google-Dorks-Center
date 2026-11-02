<div align="center">

[🏠 Hub](../../README.md) · [🐛 Vulnerabilidades](README.md) · [Próximo: Mensagens de Erro →](mensagens-de-erro-reveladoras.md)

# 🔣 Parâmetros Suspeitos

*Parâmetros de URL historicamente associados a classes de vulnerabilidade. São **sinais** para recon, não prova nem exploração.*

</div>

---

> [!CAUTION]
> Parâmetro suspeito ≠ vulnerável. **Não teste** sem autorização escrita. Aqui não há payloads. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Inclusão de arquivo / path (LFI/RFI-prone)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:"file=" ext:php` | Parâmetro de arquivo (possível LFI) | Google | 🟡 |
| `inurl:"page=" ext:php` | Parâmetro de página incluída | Google | 🟡 |
| `inurl:"include=" ext:php` | Parâmetro de include | Google | 🟡 |
| `inurl:"path=" site:alvo.com` | Parâmetro de caminho | Google | 🟡 |
| `inurl:"document=" ext:php` | Parâmetro de documento | Google | 🟡 |

### Redirecionamento (open redirect-prone)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:"redirect=" site:alvo.com` | Parâmetro de redirect | Google | 🟡 |
| `inurl:"url=http"` | Redirect com URL absoluta | Google | 🟡 |
| `inurl:"return=" OR inurl:"returnUrl="` | Retorno pós-login | Google | 🟡 |
| `inurl:"next=" inurl:login` | Destino após autenticação | Google | 🟡 |

### Injeção (SQLi/XSS-prone) e SSRF-prone

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:"id=" ext:php site:alvo.com` | Parâmetro numérico (possível SQLi) | Google | 🟡 |
| `inurl:"category=" ext:php` | Parâmetro de categoria | Google | 🟡 |
| `inurl:"search=" OR inurl:"q="` | Parâmetro de busca (possível XSS refletido) | Google | 🟡 |
| `inurl:"dest=" OR inurl:"uri="` | Parâmetro de destino (SSRF-prone) | Google | 🟡 |
| `inurl:"callback=" ext:php` | Callback JSONP (SSRF/XSS-prone) | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `inurl:"id=" ext:php` | `instreamset:url:"id=" ext:php` | `inurl:id= filetype:php` |
| `inurl:"redirect=" site:alvo.com` | `instreamset:url:"redirect="` | `inurl:redirect=` |
| `inurl:"file=" ext:php` | `instreamset:url:"file=" ext:php` | `inurl:file= filetype:php` |
| `inurl:"url=http"` | `instreamset:url:"url=http"` | `inurl:url=http` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Parâmetro associado a LFI/SQLi/path (sinal de recon) — 20 variações

```text
inurl:"id=" ext:php
inurl:"item=" ext:php
inurl:"cat=" ext:php
inurl:"path=" ext:php
inurl:"dir=" ext:php
inurl:"folder=" ext:php
inurl:"pg=" ext:php
inurl:"style=" ext:php
inurl:"template=" ext:php
inurl:"php_path=" ext:php
inurl:"doc=" ext:php
inurl:"view=" ext:php
inurl:"content=" ext:php
inurl:"layout=" ext:php
inurl:"mod=" ext:php
inurl:"conf=" ext:php
inurl:"lang=" ext:php
inurl:"detail=" ext:php
inurl:"read=" ext:php
inurl:"load=" ext:php
```

> **Padrão:** Parâmetro de redirecionamento (open redirect-prone) — 13 variações

```text
inurl:"url=" site:alvo.com
inurl:"return=" site:alvo.com
inurl:"returnUrl=" site:alvo.com
inurl:"next=" site:alvo.com
inurl:"dest=" site:alvo.com
inurl:"destination=" site:alvo.com
inurl:"goto=" site:alvo.com
inurl:"out=" site:alvo.com
inurl:"link=" site:alvo.com
inurl:"target=" site:alvo.com
inurl:"redir=" site:alvo.com
inurl:"u=" site:alvo.com
inurl:"r=" site:alvo.com
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Estes dorks mostram **onde olhar**, não que exista bug. A maioria dos parâmetros é perfeitamente segura.
- Não há payload aqui de propósito: a verificação é manual e **só dentro do escopo autorizado**.
- Combine com `site:alvo.com` para focar o recon; sem isso é pesquisa estatística.
- Nomes de parâmetro variam por idioma/framework — veja a [Expansão](#-expansão-sistemática).

<div align="center">

[🏠 Hub](../../README.md) · [🐛 Vulnerabilidades](README.md) · [Próximo: Mensagens de Erro →](mensagens-de-erro-reveladoras.md)

</div>
