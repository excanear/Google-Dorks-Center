<div align="center">

[🏠 Hub](../../README.md) · [🛒 E-commerce & Pagamentos](README.md) · [← Plataformas de Loja](plataformas-de-loja.md) · [Próximo: Pedidos & Clientes →](pedidos-e-clientes.md)

# 💳 Checkout & Gateways

*Páginas de checkout, URLs de retorno de gateway e endpoints de integração de pagamento (PagSeguro, Mercado Pago, Stripe, PayPal).*

</div>

---

> [!CAUTION]
> Nunca envie dados reais nem teste transações num checkout de terceiros. Mapear o fluxo e as integrações é recon; qualquer teste de pagamento exige escopo e consentimento. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Páginas de checkout

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/checkout/onepage "Magento"` | Checkout one-page do Magento | Google | 🟡 |
| `inurl:/checkout/cart` | Carrinho/checkout indexado | Google | 🟢 |
| `inurl:/index.php?route=checkout/checkout` | Checkout do OpenCart | Google | 🟢 |
| `inurl:/order/payment intext:"total"` | Passo de pagamento do pedido | Google | 🟡 |

### Retornos e endpoints de gateway

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/payment/return` | URL de retorno de gateway | Google | 🟡 |
| `inurl:/notificacao intext:"pagseguro"` | Notification URL do PagSeguro | Google | 🟡 |
| `inurl:/mercadopago inurl:/notification` | Webhook do Mercado Pago | Google | 🟡 |
| `inurl:/stripe/webhook` | Endpoint de webhook do Stripe | Google | 🟡 |
| `inurl:/paypal/ipn` | Instant Payment Notification do PayPal | Google | 🟡 |

### Pistas de integração

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"data-pagseguro"` | Widget PagSeguro no frontend | Google | 🟢 |
| `intext:"MercadoPago.setPublishableKey"` | Chave pública do Mercado Pago no JS | Google | 🟡 |
| `intext:"Stripe.setPublishableKey"` | Chave pública (pk_) do Stripe no JS | Google | 🟡 |
| `inurl:/wc-api/ intext:"woocommerce"` | Endpoint de pagamento WooCommerce | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `inurl:/checkout/onepage "Magento"` | `instreamset:url:/checkout/onepage "Magento"` | `inurl:checkout/onepage Magento` |
| `inurl:/stripe/webhook` | `instreamset:url:/stripe/webhook` | `inurl:stripe/webhook` |
| `inurl:/paypal/ipn` | `instreamset:url:/paypal/ipn` | `inurl:paypal/ipn` |
| `intext:"MercadoPago.setPublishableKey"` | `"MercadoPago.setPublishableKey"` | `MercadoPago.setPublishableKey` |

> **Chaves no JS:** a **chave pública** (`pk_`, publishable) é projetada para ser visível e **não** é segredo; a **secreta** (`sk_live_`) nunca deveria aparecer e é da [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Retorno/webhook de gateway por caminho — 10 variações

```text
inurl:/payment/callback
inurl:/payment/notify
inurl:/pagseguro/retorno
inurl:/mercadopago/notification
inurl:/cielo/retorno
inurl:/pagarme/postback
inurl:/getnet/callback
inurl:/adyen/notification
inurl:/braintree/webhook
inurl:/pagbank/notificacao
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Endpoints de webhook/IPN (`/stripe/webhook`, `/paypal/ipn`, PagSeguro notification) indexados indicam o gateway em uso — recon útil, risco moderado.
- A **chave pública** no JS é esperada; a presença dela só confirma o gateway. A **chave secreta** no frontend é incidente — mande para a [02](../02-credenciais-e-segredos/README.md).
- Checkout indexado às vezes vaza carrinho/pedido via parâmetro de URL — não manipule; apenas registre.
- Integrações BR (PagSeguro, Mercado Pago, PagBank, Pix) são frequentes — cruze com [10 · Brasil](../10-brasil/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [🛒 E-commerce & Pagamentos](README.md) · [← Plataformas de Loja](plataformas-de-loja.md) · [Próximo: Pedidos & Clientes →](pedidos-e-clientes.md)

</div>
