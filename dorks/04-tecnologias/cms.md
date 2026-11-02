<div align="center">

[🏠 Hub](../../README.md) · [🧰 Tecnologias](README.md) · [Próximo: Frameworks →](frameworks.md)

# 📰 CMS

*Fingerprint, caminhos e artefatos de versão de gerenciadores de conteúdo — WordPress, Joomla, Drupal, Magento e outros.*

</div>

---

> [!CAUTION]
> Fingerprint é passivo. Não explore versões identificadas sem autorização. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### WordPress

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/wp-content/plugins/` | Enumeração de plugins | Google | 🟡 |
| `inurl:/wp-content/themes/` | Enumeração de temas | Google | 🟡 |
| `inurl:/wp-json/wp/v2/users` | Enumeração de usuários via REST | Google | 🔴 |
| `inurl:readme.html "WordPress"` | readme com versão do WP | Google | 🟡 |
| `inurl:/wp-content/uploads/ -intitle:"index of"` | Diretório de uploads | Google | 🟡 |

### Joomla / Drupal / Magento

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/administrator/manifests/files/joomla.xml` | Versão do Joomla | Google | 🟡 |
| `inurl:/components/com_ intext:"Joomla"` | Componentes do Joomla | Google | 🟡 |
| `inurl:CHANGELOG.txt "Drupal"` | Versão do Drupal no changelog | Google | 🟡 |
| `inurl:/sites/default/files/ "Drupal"` | Arquivos do Drupal | Google | 🟡 |
| `inurl:/core/misc/drupal.js` | Fingerprint de Drupal | Google | 🟢 |
| `inurl:/skin/frontend/ "Magento"` | Skin do Magento | Google | 🟡 |
| `inurl:/js/mage/ "Magento"` | JS do Magento | Google | 🟢 |

### Outros CMS

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/typo3/ intext:"TYPO3"` | Backend do TYPO3 | Google | 🟡 |
| `inurl:/ghost/ intitle:"Ghost"` | Admin do Ghost | Google | 🟡 |
| `inurl:/sitecore/ intext:"Sitecore"` | CMS Sitecore | Google | 🟡 |
| `"powered by concrete5"` | CMS concrete5 | Google | 🟢 |
| `intext:"Powered by Craft CMS"` | Craft CMS | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Shodan | FOFA |
|---|---|---|---|
| `inurl:/wp-content/plugins/` | `instreamset:url:/wp-content/plugins/` | `http.html:"/wp-content/plugins/"` | `body="/wp-content/plugins/"` |
| `inurl:/administrator/manifests/files/joomla.xml` | `instreamset:url:joomla.xml` | `http.html:"joomla"` | `body="joomla"` |
| `inurl:/core/misc/drupal.js` | `instreamset:url:drupal.js` | `http.html:"Drupal"` | `body="Drupal"` |
| `inurl:/skin/frontend/ "Magento"` | `instreamset:url:/skin/frontend/` | `http.html:"Magento"` | `body="Magento"` |
| `inurl:/ghost/ intitle:"Ghost"` | `instreamset:url:/ghost/` | `http.title:"Ghost"` | `title="Ghost"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Caminho/artefato de CMS por URL — 26 variações

```text
inurl:/wp-includes/
inurl:/wp-json/
inurl:/xmlrpc.php
inurl:/administrator/index.php
inurl:/components/com_content/
inurl:/modules/mod_
inurl:/sites/all/modules/
inurl:/sites/all/themes/
inurl:/misc/drupal.js
inurl:/skin/frontend/default/
inurl:/js/varien/
inurl:/typo3conf/
inurl:/typo3temp/
inurl:/ghost/api/
inurl:/umbraco/
inurl:/sitecore/shell/
inurl:/bitrix/admin/
inurl:/concrete/index.php
inurl:/wp-content/mu-plugins/
inurl:/craft/web/
inurl:/contao/
inurl:/processwire/
inurl:/grav/user/
inurl:/october/backend
inurl:/sites/default/files/js/
inurl:/pub/static/frontend/
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `/wp-content/` e `/sites/default/files/` aparecem em **todo** site do CMS — use como fingerprint, combine com `site:` para alvo.
- A **enumeração de usuários** (`/wp-json/wp/v2/users`) é 🔴 por alimentar ataques de credencial; apenas confirme a exposição.
- Backups de plugin (UpdraftPlus etc.) ficam em [01 · Backups](../01-exposicao-de-arquivos/backups-e-arquivos-compactados.md); logins/admin em [03 · Infraestrutura Web](../03-infraestrutura-web/README.md).
- `readme.html`/`CHANGELOG.txt` revelam versão exata — pivô para avaliação de vulnerabilidade (fora do escopo deste repo).

<div align="center">

[🏠 Hub](../../README.md) · [🧰 Tecnologias](README.md) · [Próximo: Frameworks →](frameworks.md)

</div>
