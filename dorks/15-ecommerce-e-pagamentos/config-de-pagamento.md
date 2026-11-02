<div align="center">

[🏠 Hub](../../README.md) · [🛒 E-commerce & Pagamentos](README.md) · [← Pedidos & Clientes](pedidos-e-clientes.md)

# ⚙ Config de Pagamento

*Arquivos de configuração de plataforma e de módulo de pagamento em diretórios abertos — o container onde as chaves de gateway costumam estar.*

</div>

---

> [!CAUTION]
> Config de loja expõe DB, chaves de gateway e sal criptográfico. Identificar o arquivo exposto é recon; qualquer segredo dentro dele é incidente — reporte para rotação. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Arquivos de config de plataforma

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "app/etc/env.php"` | Config do Magento 2 (DB, crypt key) | Google | 🔴 |
| `intitle:"index of" "local.xml" "Magento"` | Config do Magento 1 (DB) | Google | 🔴 |
| `intitle:"index of" "parameters.php" "PrestaShop"` | Config do PrestaShop | Google | 🔴 |
| `intitle:"index of" "config.php" "OpenCart"` | Config do OpenCart | Google | 🔴 |
| `inurl:/admin/config.php "opencart"` | Config admin do OpenCart servido | Google | 🔴 |

### Pistas de config de pagamento

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:xml intext:"payment" intext:"merchant_id"` | Config de gateway com merchant id | Google | 🔴 |
| `intitle:"index of" intext:"payment.yml"` | Config de pagamento em YAML | Google | 🔴 |
| `filetype:json intext:"gateway" intext:"sandbox"` | Config de gateway (sandbox/prod) | Google | 🟡 |
| `intext:"paymentModuleConfig" ext:json` | Config de módulo de pagamento | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `intitle:"index of" "app/etc/env.php"` | `intitle:"index of" "app/etc/env.php"` | `"index of" "app/etc/env.php"` |
| `intitle:"index of" "local.xml" "Magento"` | `intitle:"index of" "local.xml" "Magento"` | `"index of" local.xml Magento` |
| `filetype:xml intext:"payment" intext:"merchant_id"` | `ext:xml "payment" "merchant_id"` | `filetype:xml payment merchant_id` |

> **Segredo dentro do arquivo:** a chave `sk_live_`/token de gateway, a `crypt.key` do Magento e a senha de DB são da [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md). Aqui tratamos o **arquivo de config da loja exposto**.

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Arquivo de config de loja em diretório aberto — 7 variações

```text
intitle:"index of" "env.php"
intitle:"index of" "parameters.php"
intitle:"index of" "settings.inc.php"
intitle:"index of" "config.inc.php"
intitle:"index of" "payment.yml"
intitle:"index of" "gateways.json"
intitle:"index of" "config.dist.php"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `app/etc/env.php` (Magento 2) e `local.xml` (Magento 1) contêm a **crypt key** que protege os tokens de pagamento salvos — vazá-los é crítico.
- `parameters.php` (PrestaShop) e `config.php` (OpenCart) guardam credencial de DB e cookie keys.
- Encontrar o **arquivo** é desta categoria; o **segredo** que ele contém é um achado para a [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md) — reporte para rotação imediata.
- Muitos resultados são exemplos de documentação; confira se há valores reais antes de reportar.

<div align="center">

[🏠 Hub](../../README.md) · [🛒 E-commerce & Pagamentos](README.md) · [← Pedidos & Clientes](pedidos-e-clientes.md)

</div>
