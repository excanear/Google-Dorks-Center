<div align="center">

[🏠 Hub](../../README.md) · [🧰 Tecnologias](README.md) · [← CMS](cms.md) · [Próximo: Servidores Web & App →](servidores-web-e-app.md)

# 🏗 Frameworks

*Fingerprint e artefatos de frameworks de aplicação — Laravel, Symfony, Django, Rails, Spring, Express, ASP.NET, Next.js.*

</div>

---

> [!CAUTION]
> Identificar o framework é recon. Explorar rotas de debug ou versões exige autorização. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### PHP (Laravel, Symfony)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/vendor/laravel` | Dependência Laravel exposta | Google | 🟡 |
| `intext:"Illuminate\\" "Stack trace"` | Stack trace de Laravel | Google | 🟡 |
| `inurl:/_ignition/health-check` | Ignition do Laravel (debug) | Google | 🔴 |
| `inurl:/app_dev.php` | Front controller de dev do Symfony | Google | 🔴 |
| `inurl:/bundles/ intext:"Symfony"` | Assets do Symfony | Google | 🟢 |

### Python / Ruby (Django, Flask, Rails)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/static/admin/css/base.css` | Fingerprint do Django admin | Google | 🟢 |
| `intext:"csrfmiddlewaretoken"` | Formulário Django | Google | 🟢 |
| `inurl:/rails/info/properties` | Info do Rails exposta | Google | 🔴 |
| `intext:"Ruby on Rails" "Routing Error"` | Erro de rota do Rails | Google | 🟡 |
| `inurl:/cable intext:"ActionCable"` | Endpoint ActionCable | Google | 🟢 |

### JVM / .NET / Node

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/error intext:"Whitelabel Error Page"` | Página de erro do Spring Boot | Google | 🟡 |
| `intext:"org.springframework" "Stack trace"` | Stack trace do Spring | Google | 🟡 |
| `inurl:.jsp intext:"javax.servlet"` | Aplicação JSP/Servlet | Google | 🟢 |
| `intext:"__VIEWSTATE" inurl:.aspx` | Fingerprint de Web Forms (ASP.NET) | Google | 🟢 |
| `inurl:/_next/static/ intext:"Next.js"` | Build do Next.js | Google | 🟢 |
| `intext:"Cannot GET /" "Express"` | Erro padrão do Express | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Shodan | FOFA |
|---|---|---|---|
| `inurl:/_ignition/health-check` | `instreamset:url:/_ignition/health-check` | `http.html:"/_ignition"` | `body="/_ignition"` |
| `inurl:/error intext:"Whitelabel Error Page"` | `inbody:"Whitelabel Error Page"` | `http.html:"Whitelabel Error Page"` | `body="Whitelabel Error Page"` |
| `inurl:/_next/static/ intext:"Next.js"` | `instreamset:url:/_next/static/` | `http.html:"/_next/static"` | `body="/_next/static"` |
| `intext:"Cannot GET /" "Express"` | `inbody:"Cannot GET /"` | `http.html:"Cannot GET /"` | `body="Cannot GET /"` |
| `inurl:/rails/info/properties` | `instreamset:url:/rails/info/properties` | `http.html:"/rails/info"` | `body="/rails/info/properties"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Rota/artefato de framework por URL — 22 variações

```text
inurl:/vendor/autoload.php
inurl:/vendor/composer/
inurl:/artisan
inurl:/storage/framework/
inurl:/config.php
inurl:/manage.py
inurl:/wsgi.py
inurl:/config/routes.rb
inurl:/public/assets/
inurl:/_next/static/chunks/
inurl:/node_modules/.package-lock.json
inurl:/actuator/mappings
inurl:/META-INF/MANIFEST.MF
inurl:/_profiler/latest
inurl:/rails/info/routes
inurl:/elmah.axd
inurl:/trace.axd
inurl:/.nuxt/
inurl:/__debug__/
inurl:/laravel-websockets
inurl:/telescope/requests
inurl:/horizon/dashboard
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `/_ignition`, `/app_dev.php` e `/rails/info/properties` são 🔴: rotas de debug que vazam config e às vezes permitem execução.
- Artefatos como `csrfmiddlewaretoken`, `__VIEWSTATE` e `/_next/static/` são fingerprints **benignos** (🟢) — servem para identificar a stack.
- Stack traces de framework também pertencem a [03 · Erros & Debug](../03-infraestrutura-web/erros-e-debug.md); aqui o foco é **identificar o framework**.
- Dependências em `/vendor/` ou `/node_modules/` indexadas revelam libs e versões — pivô de superfície.

<div align="center">

[🏠 Hub](../../README.md) · [🧰 Tecnologias](README.md) · [← CMS](cms.md) · [Próximo: Servidores Web & App →](servidores-web-e-app.md)

</div>
