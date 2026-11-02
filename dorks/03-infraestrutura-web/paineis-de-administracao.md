<div align="center">

[🏠 Hub](../../README.md) · [🖧 Infraestrutura Web](README.md) · [← Painéis de Login](paineis-de-login.md) · [Próximo: Erros & Debug →](erros-e-debug.md)

# 🛠 Painéis de Administração

*Consoles e dashboards administrativos expostos — do CMS ao painel de controle de servidor.*

</div>

---

> [!CAUTION]
> Painel administrativo exposto é achado sensível. Não tente acessar sem autorização. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Áreas administrativas por caminho

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/admin/login` | Login de área administrativa | Google | 🟡 |
| `inurl:/administrator/` | Admin do Joomla | Google | 🟡 |
| `inurl:/wp-admin/` | Admin do WordPress | Google | 🟡 |
| `inurl:/admin/dashboard` | Dashboard administrativo | Google | 🟡 |
| `inurl:/manager/html` | Tomcat Manager | Google | 🔴 |
| `inurl:/admin/config` | Configuração administrativa | Google | 🟡 |
| `inurl:/panel` intitle:"admin" | Painéis genéricos | Google | 🟡 |
| `inurl:/cpanel` | Acesso ao cPanel | Google | 🟡 |

### Consoles de aplicação e dados

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Django administration"` | Admin do Django | Google | 🔴 |
| `intitle:"Laravel Telescope"` | Debug/admin do Laravel | Google | 🔴 |
| `intitle:"Horizon" inurl:/horizon` | Laravel Horizon (filas) | Google | 🟡 |
| `intitle:"RabbitMQ Management"` | Console do RabbitMQ | Google | 🔴 |
| `intitle:"Kibana" inurl:/app/` | Console do Kibana | Google | 🟡 |
| `intitle:"Node-RED"` | Editor Node-RED exposto | Google | 🔴 |
| `intitle:"Jenkins" inurl:/manage` | Gerência do Jenkins | Google | 🔴 |
| `intitle:"MinIO Console"` | Console de storage MinIO | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Shodan | FOFA |
|---|---|---|---|
| `inurl:/manager/html` | `instreamset:url:/manager/html` | `http.title:"Apache Tomcat" http.html:"/manager"` | `body="/manager/html"` |
| `intitle:"Django administration"` | `intitle:"Django administration"` | `http.title:"Django administration"` | `title="Django administration"` |
| `intitle:"RabbitMQ Management"` | `intitle:"RabbitMQ Management"` | `http.title:"RabbitMQ Management"` | `title="RabbitMQ Management"` |
| `intitle:"Node-RED"` | `intitle:"Node-RED"` | `http.title:"Node-RED"` | `title="Node-RED"` |
| `intitle:"MinIO Console"` | `intitle:"MinIO Console"` | `http.title:"MinIO Console"` | `title="MinIO Console"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Caminho administrativo por URL — 14 variações

```text
inurl:/admin
inurl:/administrator
inurl:/wp-admin
inurl:/admin/index.php
inurl:/admincp
inurl:/backend
inurl:/manage
inurl:/management
inurl:/console
inurl:/admin/login.php
inurl:/adminpanel
inurl:/controlpanel
inurl:/webadmin
inurl:/siteadmin
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Documentação e demos usam `/admin`, `/wp-admin` como exemplo — combine com `site:` para achado real.
- `Tomcat Manager`, `Node-RED`, `RabbitMQ`, `MinIO` sem auth são 🔴 — frequentemente permitem ação direta; apenas confirme a exposição.
- phpMyAdmin/Adminer completos ficam em [🗂 Interfaces de Gerenciamento](interfaces-de-gerenciamento.md); aqui só o atalho.
- Consoles por produto são ótimos **fingerprints** — cruze com [04 · Tecnologias](../04-tecnologias/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [🖧 Infraestrutura Web](README.md) · [← Painéis de Login](paineis-de-login.md) · [Próximo: Erros & Debug →](erros-e-debug.md)

</div>
