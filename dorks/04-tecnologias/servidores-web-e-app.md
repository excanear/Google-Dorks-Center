<div align="center">

[🏠 Hub](../../README.md) · [🧰 Tecnologias](README.md) · [← Frameworks](frameworks.md) · [Próximo: Bancos de Dados →](bancos-de-dados.md)

# 🖥 Servidores Web & App

*Fingerprint de servidores web e de aplicação — Apache, Nginx, IIS, Tomcat, Jetty, JBoss/WildFly, WebLogic.*

</div>

---

> [!CAUTION]
> Identificar servidor/versão é passivo. Não explore sem autorização. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Servidores de aplicação Java

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Apache Tomcat" "If you're seeing this"` | Página padrão do Tomcat | Google | 🟡 |
| `intitle:"Apache Tomcat/" "Server Information"` | Versão do Tomcat | Google | 🟡 |
| `inurl:/examples/servlets/ "Tomcat"` | Servlets de exemplo do Tomcat | Google | 🔴 |
| `intitle:"Welcome to WildFly"` | Página padrão do WildFly/JBoss | Google | 🟡 |
| `intitle:"JBoss" inurl:/jbossws` | Serviços web do JBoss | Google | 🟡 |
| `intext:"Oracle WebLogic Server Administration Console"` | Console do WebLogic | Google | 🔴 |
| `intitle:"Jetty" intext:"Powered by Jetty"` | Servidor Jetty | Google | 🟢 |
| `intitle:"GlassFish Server" "Server Running"` | Página padrão do GlassFish | Google | 🟡 |

### Servidores web

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Test Page for the Apache HTTP Server"` | Apache recém-instalado (RHEL) | Google | 🟢 |
| `intitle:"Welcome to CentOS" "Apache"` | Apache padrão no CentOS | Google | 🟢 |
| `intitle:"HTTP Server Test Page" "Powered by"` | Página de teste de servidor | Google | 🟢 |
| `intext:"Microsoft-IIS" intitle:"index of"` | IIS com listing | Google | 🟡 |
| `intitle:"LiteSpeed" "Powered by LiteSpeed"` | Servidor LiteSpeed | Google | 🟢 |
| `intitle:"Caddy" "default"` | Página padrão do Caddy | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

> Servidor/versão é território natural de Shodan/Censys/FOFA.

| Google | Shodan | Censys | FOFA |
|---|---|---|---|
| `intitle:"Apache Tomcat" "If you're seeing this"` | `http.title:"Apache Tomcat"` | `web.endpoints.http.title:"Apache Tomcat"` | `title="Apache Tomcat"` |
| `intext:"Oracle WebLogic Server Administration Console"` | `http.html:"WebLogic Server Administration"` | `web.endpoints.http.body:"WebLogic"` | `body="WebLogic Server Administration Console"` |
| `intitle:"Welcome to WildFly"` | `http.title:"Welcome to WildFly"` | `web.endpoints.http.title:"WildFly"` | `title="Welcome to WildFly"` |
| `intitle:"LiteSpeed"` | `product:"LiteSpeed"` | `host.services.software:(product="LiteSpeed")` | `header="LiteSpeed"` |
| `intext:"Microsoft-IIS"` | `product:"Microsoft IIS httpd"` | `host.services.software:(product="IIS")` | `header="Microsoft-IIS"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Página padrão de servidor por título — 17 variações

```text
intitle:"Apache Tomcat"
intitle:"JBoss"
intitle:"GlassFish Server"
intitle:"Welcome to nginx on"
intitle:"Test Page for the Nginx"
intitle:"Apache2 Debian Default Page"
intitle:"IIS Windows"
intitle:"LiteSpeed"
intitle:"Jetty"
intitle:"Welcome to CentOS"
intitle:"Oracle HTTP Server"
intitle:"Lighttpd"
intitle:"Caddy"
intitle:"Gunicorn"
intitle:"Werkzeug"
intitle:"Apache Tomcat/9"
intitle:"Undertow"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Páginas padrão (Tomcat, WildFly, CentOS/Apache) indicam servidor **recém-instalado ou esquecido** — superfície interessante.
- `WebLogic Admin Console` e `servlets de exemplo` do Tomcat são 🔴: alvos clássicos de exploração; apenas confirme a exposição.
- Banner pode ser **ocultado** (`ServerTokens Prod`); ausência não prova ausência.
- Para varredura de versão em massa, use Shodan/Censys/FOFA (veja a tradução). Banners/versões em conteúdo web ficam também em [03 · Versões & Software Exposto](../03-infraestrutura-web/versoes-e-software-exposto.md).

<div align="center">

[🏠 Hub](../../README.md) · [🧰 Tecnologias](README.md) · [← Frameworks](frameworks.md) · [Próximo: Bancos de Dados →](bancos-de-dados.md)

</div>
