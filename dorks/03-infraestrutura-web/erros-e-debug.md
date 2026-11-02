<div align="center">

[🏠 Hub](../../README.md) · [🖧 Infraestrutura Web](README.md) · [← Painéis de Administração](paineis-de-administracao.md) · [Próximo: Status & Info Pages →](status-e-info-pages.md)

# 🐞 Erros & Debug

*Páginas de erro, stack traces e modo debug que vazam caminhos, versões, queries e, às vezes, segredos.*

</div>

---

> [!CAUTION]
> Páginas de erro indexadas são passivas; **provocar erros** no alvo é interação e exige autorização. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Stack traces e exceções

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"Fatal error" "on line" intext:"Call Stack"` | Erro fatal do PHP com stack | Google | 🟡 |
| `intext:"Warning: mysqli" "on line"` | Aviso MySQLi vazando caminho | Google | 🟡 |
| `intext:"Whoops, looks like something went wrong"` | Tela de erro do Laravel | Google | 🔴 |
| `intext:"Traceback (most recent call last)"` | Stack trace de Python | Google | 🟡 |
| `intext:"Exception" "at " intext:".java:"` | Stack trace de Java | Google | 🟡 |
| `intext:"System.Web" "Stack Trace:"` | Erro de ASP.NET | Google | 🟡 |
| `intitle:"Runtime Error" "Server Error in"` | Erro de runtime ASP.NET | Google | 🟡 |

### Modo debug

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"DEBUG = True" "Django"` | Django com DEBUG ligado | Google | 🔴 |
| `intitle:"Werkzeug Debugger"` | Debugger interativo do Flask | Google | 🔴 |
| `intext:"APP_DEBUG" "true"` | Laravel em modo debug | Google | 🔴 |
| `inurl:/_profiler/ intitle:"Symfony Profiler"` | Profiler do Symfony exposto | Google | 🔴 |
| `intext:"Rails.env" "ActionController"` | Erro detalhado do Rails | Google | 🟡 |

### phpinfo e diagnósticos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"phpinfo()" "PHP Version"` | Saída de `phpinfo()` | Google, Bing | 🔴 |
| `ext:php intitle:"phpinfo()" "allow_url_fopen"` | phpinfo com diretivas | Google | 🔴 |
| `intext:"phpinfo()" "HTTP Request Headers"` | phpinfo com headers/env | Google | 🔴 |
| `intitle:"Test Page for the Apache"` | Página padrão do Apache | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Shodan | FOFA |
|---|---|---|---|
| `intitle:"phpinfo()" "PHP Version"` | `intitle:"phpinfo()" "PHP Version"` | `http.html:"phpinfo()"` | `body="phpinfo()"` |
| `intext:"Whoops, looks like something went wrong"` | `inbody:"Whoops, looks like something went wrong"` | `http.html:"Whoops, looks like"` | `body="Whoops, looks like"` |
| `intitle:"Werkzeug Debugger"` | `intitle:"Werkzeug Debugger"` | `http.title:"Werkzeug Debugger"` | `title="Werkzeug Debugger"` |
| `inurl:/_profiler/ intitle:"Symfony Profiler"` | `instreamset:url:/_profiler/` | `http.html:"Symfony Profiler"` | `body="Symfony Profiler"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Assinatura de erro/stack em conteúdo — 13 variações

```text
intext:"Fatal error"
intext:"Parse error"
intext:"Warning: include"
intext:"Warning: require"
intext:"Notice: Undefined"
intext:"Uncaught exception"
intext:"Call Stack"
intext:"stack trace"
intext:"Undefined index"
intext:"mysqli_fetch"
intext:"ORA-00933"
intext:"SQLSTATE"
intext:"Microsoft OLE DB Provider"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Fóruns e Q&A** (Stack Overflow etc.) contêm stack traces como exemplo — filtre com `-site:stackoverflow.com` ou foque no `site:` alvo.
- `DEBUG=True`/`APP_DEBUG=true`/Werkzeug/Symfony Profiler são 🔴: além de vazar dados, muitas vezes permitem execução.
- `phpinfo()` revela versão, módulos, caminhos e variáveis de ambiente — às vezes com segredos (cruze com [02](../02-credenciais-e-segredos/README.md)).
- Stack traces também vazam **versões** de framework → fingerprint para [04 · Tecnologias](../04-tecnologias/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [🖧 Infraestrutura Web](README.md) · [← Painéis de Administração](paineis-de-administracao.md) · [Próximo: Status & Info Pages →](status-e-info-pages.md)

</div>
