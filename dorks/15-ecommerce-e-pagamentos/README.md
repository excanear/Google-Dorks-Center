<div align="center">

[🏠 Hub](../../README.md)

# 🛒 E-commerce & Pagamentos

*A plataforma de loja como alvo — admin de Magento/WooCommerce/PrestaShop, páginas de checkout e gateway, exportações de pedidos e configuração de pagamento exposta.*

</div>

---

> [!CAUTION]
> Pedidos e cadastros de clientes são dados pessoais (LGPD/GDPR); dados de cartão são regulados por PCI-DSS. Identificar exposição é recon; acessar dados de clientes ou testar fluxo de pagamento sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📂 Subcategorias

| # | Subcategoria | Conteúdo | Risco |
|---|---|---|---|
| 1 | [🏬 Plataformas de Loja](plataformas-de-loja.md) | Magento, WooCommerce, PrestaShop, OpenCart, VTEX | 🟡 |
| 2 | [💳 Checkout & Gateways](checkout-e-gateways.md) | Páginas de checkout, retornos de gateway, `/payment` | 🟡 |
| 3 | [📦 Pedidos & Clientes](pedidos-e-clientes.md) | Exportações de pedido, faturas, listas de cliente | 🔴 |
| 4 | [⚙ Config de Pagamento](config-de-pagamento.md) | Arquivos de config de módulo de pagamento | 🔴 |

## 🧭 Como usar esta categoria

1. **Plataforma** identifica o motor da loja e a versão — pivô para CVEs em [09 · Vulnerabilidades](../09-vulnerabilidades/README.md) (Magento é alvo clássico de "Magecart").
2. **Checkout/gateway** revela o fluxo de pagamento e integrações (PagSeguro, Mercado Pago, Stripe…).
3. **Pedidos/clientes** expostos são o pior cenário — dados pessoais e, às vezes, de pagamento. Reporte, não baixe.

## 🚧 Fronteira desta categoria

- **Chaves/tokens de gateway** (Stripe `sk_live_`, PayPal, PagSeguro) → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md). Aqui tratamos a **plataforma e o fluxo**, não a chave.
- **Dumps e exportações genéricas** (CSV/SQL) → [01 · Exposição de Arquivos](../01-exposicao-de-arquivos/README.md). Aqui, só quando é claramente **pedido/cliente de loja**.
- **Fingerprint genérico de CMS** (Magento skin/JS) já está em [04 · Tecnologias](../04-tecnologias/cms.md) — aqui ficam **admin, checkout e dados**.

## 🔗 Categorias relacionadas

- Chaves de gateway → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md)
- Fingerprint de CMS → [04 · Tecnologias](../04-tecnologias/cms.md)
- Dumps e backups → [01 · Exposição de Arquivos](../01-exposicao-de-arquivos/README.md)

<div align="center">

[🏠 Hub](../../README.md)

</div>
