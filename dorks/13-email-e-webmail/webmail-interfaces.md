<div align="center">

[🏠 Hub](../../README.md) · [📧 E-mail & Webmail](README.md) · [Próximo: Servidores de E-mail →](servidores-de-email.md)

# 🖥 Interfaces de Webmail

*Telas de login de OWA, Zimbra, Roundcube, Horde, RainLoop e afins — identificam o produto, a versão e o alvo.*

</div>

---

> [!CAUTION]
> A tela de login é recon; não tente autenticar sem autorização. A versão exposta pode indicar CVEs — reporte, não explore. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Microsoft (OWA / Exchange)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Outlook Web App"` | Login do OWA | Google, Bing | 🟡 |
| `inurl:/owa/auth/logon.aspx` | Página de logon do OWA | Google | 🟡 |
| `inurl:/owa/ intitle:"Outlook"` | Exchange OWA por caminho | Google | 🟡 |
| `intitle:"Exchange" inurl:/ecp/` | Exchange Control Panel | Google | 🔴 |

### Zimbra

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Zimbra Web Client"` | Login do Zimbra | Google | 🟡 |
| `inurl:/zimbra/ intitle:"Zimbra"` | Zimbra por caminho | Google | 🟡 |
| `intitle:"Zimbra Administration Console"` | Console admin do Zimbra | Google | 🔴 |
| `inurl:/zimbraAdmin/` | Admin Zimbra por caminho | Google | 🔴 |

### Open source (Roundcube / Horde / RainLoop / SquirrelMail)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Roundcube Webmail"` | Login do Roundcube | Google | 🟡 |
| `inurl:/roundcube/ intitle:"Welcome to Roundcube"` | Roundcube por caminho | Google | 🟡 |
| `intitle:"Horde :: Log in"` | Login do Horde | Google | 🟡 |
| `intitle:"RainLoop"` | Webmail RainLoop/SnappyMail | Google | 🟡 |
| `intitle:"SquirrelMail" inurl:/src/login.php` | Login do SquirrelMail | Google | 🟡 |
| `intitle:"AfterLogic" OR intext:"Powered by AfterLogic"` | Webmail AfterLogic | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Shodan |
|---|---|---|
| `intitle:"Outlook Web App"` | `intitle:"Outlook Web App"` | `http.title:"Outlook Web App"` |
| `intitle:"Zimbra Web Client"` | `intitle:"Zimbra Web Client"` | `http.title:"Zimbra Web Client"` |
| `intitle:"Roundcube Webmail"` | `intitle:"Roundcube Webmail"` | `http.title:"Roundcube Webmail"` |
| `intitle:"Horde :: Log in"` | `intitle:"Horde :: Log in"` | `http.html:"Horde"` |

> **Infraestrutura:** webmail é melhor enumerado no Shodan/Censys por `http.title`/`http.favicon.hash`. O favicon do Roundcube e do OWA tem hash estável — veja o [manual de infraestrutura](../../docs/manual/03-buscadores-de-infraestrutura.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Interface de webmail por caminho — 11 variações

```text
inurl:/roundcube/
inurl:/webmail/
inurl:/zimbra/
inurl:/horde/login.php
inurl:/squirrelmail/src/login.php
inurl:/rainloop/
inurl:/mail/
inurl:/exchange/
inurl:/iredadmin/login
inurl:/SOGo/
inurl:/afterlogic/
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- O `/ecp/` (Exchange Control Panel) e o `/zimbraAdmin/` são **administrativos** — risco maior que o webmail de usuário.
- Muitos provedores expõem webmail de propósito; o achado relevante é o webmail **corporativo interno** ou uma versão antiga vulnerável.
- A versão costuma aparecer no rodapé ou no `generator`/JS — cruze com [09 · Vulnerabilidades](../09-vulnerabilidades/README.md) para CVE conhecido.
- Login genérico sem marca de produto de e-mail é da [03 · Infra Web](../03-infraestrutura-web/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [📧 E-mail & Webmail](README.md) · [Próximo: Servidores de E-mail →](servidores-de-email.md)

</div>
