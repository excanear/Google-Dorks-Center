<div align="center">

[🏠 Hub](../../README.md) · [🖧 Infraestrutura Web](README.md) · [Próximo: Painéis de Administração →](paineis-de-administracao.md)

# 🔓 Painéis de Login

*Páginas de autenticação expostas — genéricas e por produto. O primeiro alvo de mapeamento de superfície.*

</div>

---

> [!CAUTION]
> Mapear um login é recon; **tentar autenticar, forçar ou enumerar usuários** exige autorização. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Logins genéricos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:login` | Páginas de login por URL | Google, Bing | 🟡 |
| `intitle:"login"` | Páginas de login por título | Google, Bing | 🟡 |
| `inurl:signin` | Páginas de sign-in | Google | 🟡 |
| `intitle:"please log in"` | Prompt de login | Google | 🟡 |
| `inurl:/auth/login` | Endpoint de autenticação | Google | 🟡 |
| `intitle:"Log In" inurl:admin` | Login administrativo | Google | 🟡 |
| `inurl:/user/login intitle:"Sign in"` | Login de usuário | Google | 🟡 |

### Login por produto / tecnologia

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:wp-login.php` | Login do WordPress | Google, Bing | 🟡 |
| `intitle:"Grafana" inurl:login` | Login do Grafana | Google | 🟡 |
| `intitle:"Kibana" inurl:login` | Login do Kibana | Google | 🟡 |
| `intitle:"Jenkins" inurl:login` | Login do Jenkins | Google | 🟡 |
| `intitle:"Gitlab" inurl:/users/sign_in` | Login do GitLab | Google | 🟡 |
| `intitle:"Portainer" inurl:/#/login` | Login do Portainer | Google | 🟡 |
| `intitle:"VMware Horizon"` | Portal VMware Horizon | Google | 🟡 |
| `intitle:"Fortinet" inurl:/remote/login` | Login SSL-VPN FortiGate | Google | 🔴 |
| `intitle:"GlobalProtect Portal"` | Portal Palo Alto GlobalProtect | Google | 🔴 |
| `intitle:"RD Web Access"` | Remote Desktop Web Access | Google | 🔴 |
| `intitle:"Outlook Web App" inurl:/owa` | Login do OWA (Exchange) | Google | 🟡 |
| `intitle:"Citrix" inurl:/vpn/index.html` | Login Citrix Gateway | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Shodan | FOFA |
|---|---|---|---|
| `inurl:login` | `instreamset:url:login` | `http.html:"login"` | `body="login"` |
| `inurl:wp-login.php` | `instreamset:url:wp-login.php` | `http.html:"/wp-login.php"` | `body="/wp-login.php"` |
| `intitle:"Grafana" inurl:login` | `intitle:"Grafana" inurl:login` | `http.title:"Grafana"` | `title="Grafana"` |
| `intitle:"GlobalProtect Portal"` | `intitle:"GlobalProtect Portal"` | `http.title:"GlobalProtect Portal"` | `title="GlobalProtect Portal"` |
| `intitle:"Fortinet" inurl:/remote/login` | `intitle:"Fortinet"` | `http.title:"Fortinet"` | `title="Fortinet"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Caminho de login por URL — 15 variações

```text
inurl:/login
inurl:/signin
inurl:/sign-in
inurl:/user/login
inurl:/users/sign_in
inurl:/account/login
inurl:/session/new
inurl:/accounts/login
inurl:/portal/login
inurl:/sso/login
inurl:/cas/login
inurl:/oauth/authorize
inurl:/login.aspx
inurl:/login.jsp
inurl:/login.php
```

> **Padrão:** Login por produto (título) — 17 variações

```text
intitle:"GitLab" inurl:login
intitle:"Portainer" inurl:login
intitle:"Nagios" inurl:login
intitle:"Zabbix" inurl:login
intitle:"Cacti" inurl:login
intitle:"PRTG" inurl:login
intitle:"Nextcloud" inurl:login
intitle:"ownCloud" inurl:login
intitle:"Jira" inurl:login
intitle:"Confluence" inurl:login
intitle:"SonarQube" inurl:login
intitle:"Rancher" inurl:login
intitle:"Harbor" inurl:login
intitle:"Keycloak" inurl:login
intitle:"Zimbra" inurl:login
intitle:"Roundcube" inurl:login
intitle:"phpMyAdmin" inurl:login
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `inurl:login`/`intitle:"login"` tem volume gigante — sempre combine com `site:` do alvo ou com um produto.
- Portais de **VPN/acesso remoto** (Fortinet, GlobalProtect, Citrix) são 🔴 por serem alvos de exploração conhecidos; mapear é recon, explorar exige escopo.
- Painéis por produto são melhor enumerados em **Shodan/FOFA** por `http.title:`/`title=` — veja a tradução.
- Páginas de login de produtos específicos também servem de **fingerprint** de tecnologia → cruze com [04 · Tecnologias](../04-tecnologias/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [🖧 Infraestrutura Web](README.md) · [Próximo: Painéis de Administração →](paineis-de-administracao.md)

</div>
