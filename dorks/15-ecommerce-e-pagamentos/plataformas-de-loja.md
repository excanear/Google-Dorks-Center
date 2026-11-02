<div align="center">

[🏠 Hub](../../README.md) · [🛒 E-commerce & Pagamentos](README.md) · [Próximo: Checkout & Gateways →](checkout-e-gateways.md)

# 🏬 Plataformas de Loja

*Painéis de administração e pontos de entrada de Magento, WooCommerce, PrestaShop, OpenCart, Shopify e VTEX.*

</div>

---

> [!CAUTION]
> Admin de loja e versão são recon; não tente autenticar nem explorar CVE sem autorização. Lojas processam pagamento — qualquer teste intrusivo exige escopo formal. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Magento / Adobe Commerce

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Magento Admin" inurl:/admin` | Login do admin Magento | Google | 🔴 |
| `inurl:/downloader intext:"Magento Connect Manager"` | Connect Manager (M1) | Google | 🔴 |
| `inurl:/magento_version` | Endpoint de versão do Magento | Google | 🟡 |
| `inurl:/rest/V1/ intext:"Magento"` | API REST do Magento 2 | Google | 🟡 |

### WooCommerce / PrestaShop

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/wp-content/plugins/woocommerce` | Loja WooCommerce (plugin) | Google | 🟢 |
| `intext:"Proudly powered by WooCommerce"` | Rodapé WooCommerce | Google | 🟢 |
| `intitle:"PrestaShop" inurl:/admin` | Admin do PrestaShop | Google | 🔴 |
| `inurl:/modules/ intext:"PrestaShop" inurl:/override` | Overrides do PrestaShop | Google | 🟡 |

### OpenCart / Shopify / VTEX

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"OpenCart" inurl:index.php?route=common/home` | Loja OpenCart | Google | 🟢 |
| `inurl:index.php?route=account/login "OpenCart"` | Login OpenCart | Google | 🟡 |
| `intext:"Powered by Shopify" intext:"myshopify.com"` | Loja Shopify | Google | 🟢 |
| `intext:"vtexcommercestable"` | Loja VTEX (BR) | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Shodan |
|---|---|---|
| `intitle:"Magento Admin" inurl:/admin` | `intitle:"Magento Admin"` | `http.title:"Magento Admin"` |
| `intitle:"PrestaShop" inurl:/admin` | `intitle:"PrestaShop"` | `http.html:"PrestaShop"` |
| `intext:"vtexcommercestable"` | `"vtexcommercestable"` | `http.html:"vtexcommercestable"` |
| `intext:"Powered by Shopify"` | `"Powered by Shopify"` | `http.html:"Shopify"` |

> **Infraestrutura:** Magento e PrestaShop têm `http.favicon.hash` e caminhos característicos; no FOFA, `app="Magento"` e `app="PrestaShop"`. Fingerprint genérico de CMS fica em [04 · Tecnologias](../04-tecnologias/cms.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Ponto de entrada de loja por caminho — 8 variações

```text
inurl:/customer/account/login
inurl:/sales/order/view
inurl:/index.php?route=account/login
inurl:/index.php?route=product/search
inurl:/catalogsearch/result
inurl:/rest/V1/products
inurl:/index.php?controller=authentication
inurl:/admin/index.php?route=common/dashboard
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Magento (M1 `/downloader`, M2 `/rest/V1/`) acumula CVEs críticos e é alvo de skimmers Magecart — a versão exposta é o gatilho para [09 · Vulnerabilidades](../09-vulnerabilidades/README.md).
- `Powered by WooCommerce/Shopify` é fingerprint benigno (quase toda loja pública tem) — o valor está no **admin** exposto ou em versão vulnerável.
- VTEX, Loja Integrada e Nuvemshop são comuns no e-commerce BR — cruze com [10 · Brasil](../10-brasil/README.md) quando o alvo for nacional.
- O fingerprint genérico (skin/JS do Magento) **não** se repete aqui — está em [04](../04-tecnologias/cms.md).

<div align="center">

[🏠 Hub](../../README.md) · [🛒 E-commerce & Pagamentos](README.md) · [Próximo: Checkout & Gateways →](checkout-e-gateways.md)

</div>
