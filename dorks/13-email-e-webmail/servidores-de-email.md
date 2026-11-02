<div align="center">

[🏠 Hub](../../README.md) · [📧 E-mail & Webmail](README.md) · [← Interfaces de Webmail](webmail-interfaces.md) · [Próximo: Listas & Arquivos →](listas-e-arquivos.md)

# 📮 Servidores de E-mail

*Painéis de administração de MTA (Postfix/iRedMail/Modoboa), interfaces de lista e banners SMTP/IMAP/POP3 — majoritariamente achados de infraestrutura.*

</div>

---

> [!CAUTION]
> Banner de servidor e painel de admin identificam o MTA e a versão. Isso é recon; não tente autenticar nem enviar e-mail por servidores de terceiros. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Painéis de administração de MTA

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Postfix Admin"` | Painel Postfix Admin | Google | 🔴 |
| `inurl:/postfixadmin/ intitle:"login"` | Postfix Admin por caminho | Google | 🔴 |
| `intitle:"iRedAdmin"` | Admin do iRedMail | Google | 🔴 |
| `intitle:"Modoboa"` | Painel Modoboa | Google | 🔴 |
| `intitle:"Mailu" inurl:/admin` | Admin do Mailu | Google | 🔴 |
| `intitle:"Mail-in-a-Box"` | Painel Mail-in-a-Box | Google | 🟡 |

### Listas e MTAs clássicos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/mailman/listinfo` | Interface de listas Mailman | Google | 🟢 |
| `intitle:"Mailman" inurl:/admin` | Admin de lista Mailman | Google | 🔴 |
| `inurl:2096 intitle:"webmail"` | Webmail cPanel (porta 2096) | Google | 🟡 |
| `intitle:"MailWizz"` | Plataforma de envio MailWizz | Google | 🟡 |
| `intitle:"Mautic"` | Automação de e-mail Mautic | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Shodan | Censys |
|---|---|---|
| `intitle:"Postfix Admin"` | `http.title:"Postfix Admin"` | `services.http.response.html_title:"Postfix Admin"` |
| `intitle:"iRedAdmin"` | `http.title:"iRedAdmin"` | `services.http.response.html_title:"iRedAdmin"` |
| *(banner SMTP)* | `port:25 product:"Postfix smtpd"` | `services.service_name:SMTP and services.banner:Postfix` |
| *(banner IMAP)* | `port:143 product:"Dovecot imapd"` | `services.service_name:IMAP and services.banner:Dovecot` |

> **Infraestrutura é o caminho principal aqui.** Portas e produtos: SMTP `25/465/587`, IMAP `143/993`, POP3 `110/995`. No FOFA, `protocol="smtp"` e `banner="220"`. Detalhes no [manual de infraestrutura](../../docs/manual/03-buscadores-de-infraestrutura.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Painel de administração de MTA por caminho — 8 variações

```text
inurl:/postfixadmin/login.php
inurl:/iredadmin/
inurl:/modoboa/
inurl:/mailu/admin
inurl:/poste/
inurl:/mailman/admin
inurl:/mautic/
inurl:/mailwizz/
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Painéis `Postfix Admin`, `iRedAdmin`, `Modoboa` e `Mailu /admin` gerenciam **todas as contas** do domínio — expô-los é crítico.
- O banner SMTP/IMAP revela o software e, muitas vezes, a versão exata — ótimo para casar com CVE, mas isso é infraestrutura: use Shodan/Censys, não o Google.
- `Mautic`/`MailWizz` são plataformas de **envio em massa**; expostas, podem permitir abuso de reputação de e-mail.
- Senha de SMTP em arquivo é da [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [📧 E-mail & Webmail](README.md) · [← Interfaces de Webmail](webmail-interfaces.md) · [Próximo: Listas & Arquivos →](listas-e-arquivos.md)

</div>
