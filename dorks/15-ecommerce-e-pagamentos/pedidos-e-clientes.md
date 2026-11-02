<div align="center">

[🏠 Hub](../../README.md) · [🛒 E-commerce & Pagamentos](README.md) · [← Checkout & Gateways](checkout-e-gateways.md) · [Próximo: Config de Pagamento →](config-de-pagamento.md)

# 📦 Pedidos & Clientes

*Exportações de pedidos, faturas e listas de clientes de lojas em diretórios abertos — dados pessoais e, às vezes, de pagamento.*

</div>

---

> [!CAUTION]
> Estes arquivos contêm **dados pessoais de clientes reais** (nome, endereço, telefone, às vezes pagamento). Confirmar a exposição é recon; abrir ou baixar é tratamento ilícito de dados sob a LGPD. Reporte imediatamente ao responsável. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Exportações de pedidos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" intext:"orders_export"` | Export de pedidos em diretório aberto | Google | 🔴 |
| `filetype:csv intext:"order_id" intext:"customer"` | CSV de pedidos com cliente | Google | 🔴 |
| `inurl:/var/export "Magento"` | Diretório de exportação do Magento | Google | 🔴 |
| `filetype:xlsx intext:"pedido" intext:"cliente" intext:"endereço"` | Planilha de pedidos (BR) | Google | 🔴 |

### Faturas e recibos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "invoices" ext:pdf` | Faturas em PDF em pasta aberta | Google | 🔴 |
| `inurl:/invoice intext:"order" filetype:pdf` | Fatura/recibo de pedido | Google | 🔴 |
| `intitle:"index of" intext:"nota-fiscal" ext:pdf` | Notas fiscais (BR) em pasta aberta | Google | 🔴 |

### Listas de clientes

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:csv intext:"email" intext:"telefone" intext:"cpf"` | Base de clientes (BR) | Google | 🔴 |
| `intitle:"index of" intext:"customers.csv"` | Export de clientes | Google | 🔴 |
| `filetype:sql intext:"INSERT INTO" intext:"customer_entity"` | Dump de clientes do Magento | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Yandex |
|---|---|---|
| `filetype:csv intext:"order_id" intext:"customer"` | `ext:csv "order_id" "customer"` | `mime:csv "order_id" "customer"` |
| `intitle:"index of" intext:"customers.csv"` | `intitle:"index of" "customers.csv"` | `title:"index of" "customers.csv"` |
| `intitle:"index of" "invoices" ext:pdf` | `intitle:"index of" "invoices" ext:pdf` | `title:"index of" "invoices" mime:pdf` |

> **Fronteira:** dumps genéricos de banco e backups ficam em [01 · Exposição de Arquivos](../01-exposicao-de-arquivos/README.md); aqui, só quando o conteúdo é claramente **pedido/cliente de loja**.

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Export de pedidos/clientes em diretório aberto — 7 variações

```text
intitle:"index of" intext:"pedidos.csv"
intitle:"index of" intext:"clientes.csv"
intitle:"index of" intext:"orders.csv"
intitle:"index of" intext:"sales_order.csv"
intitle:"index of" intext:"export_orders"
intitle:"index of" intext:"customer_list"
intitle:"index of" intext:"base-de-clientes"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Este é o conteúdo de **maior sensibilidade** da categoria. Trate todo achado como incidente de dados pessoais: registre a URL, **não** baixe, reporte.
- `customer_entity` (Magento) e `customers.csv` são padrões reais de export/dump — alto valor, alto risco.
- Notas fiscais e planilhas com CPF cruzam com [10 · Brasil](../10-brasil/README.md) (dados de documentos BR).
- Nunca publique, compartilhe ou armazene os dados encontrados — isso agrava a violação, não a corrige.

<div align="center">

[🏠 Hub](../../README.md) · [🛒 E-commerce & Pagamentos](README.md) · [← Checkout & Gateways](checkout-e-gateways.md) · [Próximo: Config de Pagamento →](config-de-pagamento.md)

</div>
