<div align="center">

[🏠 Hub](../../README.md)

# 🖧 Infraestrutura Web

*Interfaces e respostas da aplicação: painéis de login e administração, páginas de erro/debug, status pages, consoles de gerenciamento e versões expostas.*

</div>

---

> [!CAUTION]
> Encontrar um painel ou uma página de erro é passivo; **autenticar, explorar ou provocar erros** no alvo não é, e exige autorização (Lei 12.737/2012, CFAA). Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📂 Subcategorias

| # | Subcategoria | Conteúdo | Risco |
|---|---|---|---|
| 1 | [🔓 Painéis de Login](paineis-de-login.md) | Logins genéricos e por produto | 🟡 |
| 2 | [🛠 Painéis de Administração](paineis-de-administracao.md) | `/admin`, consoles, dashboards | 🟡–🔴 |
| 3 | [🐞 Erros & Debug](erros-e-debug.md) | Stack traces, `phpinfo()`, modo debug | 🟡–🔴 |
| 4 | [📈 Status & Info Pages](status-e-info-pages.md) | `server-status`, `/metrics`, `/actuator` | 🟡 |
| 5 | [🗂 Interfaces de Gerenciamento](interfaces-de-gerenciamento.md) | phpMyAdmin, Adminer, cPanel, Webmin | 🔴 |
| 6 | [🏷 Versões & Software Exposto](versoes-e-software-exposto.md) | Banners, `X-Powered-By`, versões | 🟡 |

## 🧭 Como usar esta categoria

1. Restrinja ao escopo autorizado com `site:alvo.com`.
2. Traduções para **Shodan/Censys/FOFA** aparecem em cada página — infra é onde esses buscadores brilham.
3. Para a sintaxe desses operadores, veja o [manual de infraestrutura](../../docs/manual/03-buscadores-de-infraestrutura.md).

## 🔗 Categorias relacionadas

- Diretórios abertos e `.git`/`.svn` → [01 · Diretórios Abertos](../01-exposicao-de-arquivos/diretorios-abertos.md)
- Fingerprint de CMS/framework/banco por produto → [04 · Tecnologias](../04-tecnologias/README.md)
- Erros que vazam **credenciais** → [02 · Senhas em Config & Código](../02-credenciais-e-segredos/senhas-em-configuracao-e-codigo.md)

<div align="center">

[🏠 Hub](../../README.md)

</div>
