<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Dumps de Banco de Dados](dumps-de-banco-de-dados.md) · [Próximo: Arquivos de Configuração →](arquivos-de-configuracao.md)

# 📜 Logs

*Arquivos de log expostos: acesso, erro, debug, aplicação e logs de ferramentas que vazam caminhos, IPs, tokens e, às vezes, credenciais.*

</div>

---

> [!CAUTION]
> Logs vazam caminhos internos, IPs, nomes de usuário, tokens de sessão e queries com dados pessoais. Trate como informação sensível e reporte ao responsável. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Logs genéricos em diretórios abertos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ext:log` | Diretórios abertos com .log | Google, Bing | 🟡 |
| `intitle:"index of" "logs"` | Pastas /logs listáveis | Google | 🟡 |
| `intitle:"index of" "error.log"` | Logs de erro | Google | 🟡 |
| `intitle:"index of" "access.log"` | Logs de acesso | Google | 🟡 |
| `intitle:"index of" "debug.log"` | Logs de debug | Google | 🟡 |

### Logs de aplicação e framework

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/wp-content/debug.log` | Debug log do WordPress | Google | 🔴 |
| `ext:log "laravel.log"` | Logs do Laravel (stack traces) | Google | 🔴 |
| `inurl:storage/logs "laravel.log"` | Pasta de logs do Laravel | Google | 🔴 |
| `ext:log "PHP Fatal error"` | Logs com erros fatais de PHP | Google | 🟡 |
| `ext:log "Stacktrace" "Exception"` | Stack traces de aplicação | Google | 🟡 |
| `ext:log "DEBUG" "SELECT * FROM"` | Logs de debug com queries SQL | Google | 🔴 |
| `inurl:/var/log/ intitle:"index of"` | Diretório /var/log exposto | Google | 🔴 |

### Logs que vazam segredos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `ext:log "password"` | Logs mencionando senha | Google | 🔴 |
| `ext:log "authorization: bearer"` | Tokens Bearer registrados em log | Google | 🔴 |
| `ext:log "api_key" OR "apikey"` | Chaves de API em log | Google | 🔴 |
| `ext:log "jdbc:mysql"` | Strings de conexão JDBC em log | Google | 🔴 |
| `ext:log "set-cookie" "session"` | Cookies de sessão registrados | Google | 🔴 |

### Logs de ferramentas

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "npm-debug.log"` | Log de erro do npm | Google | 🟡 |
| `intitle:"index of" "yarn-error.log"` | Log de erro do Yarn | Google | 🟡 |
| `intitle:"index of" "pip-log.txt"` | Log do pip | Google | 🟡 |
| `ext:log inurl:jenkins` | Logs de build do Jenkins | Google | 🟡 |
| `intitle:"index of" "catalina.out"` | Log do Apache Tomcat | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | Yandex |
|---|---|---|---|
| `intitle:"index of" ext:log` | `intitle:"index of" ext:log` | `intitle:"index of" filetype:log` | `title:"index of" mime:log` |
| `inurl:/wp-content/debug.log` | `instreamset:url:wp-content/debug.log` | `inurl:wp-content/debug.log` | `url:wp-content/debug.log` |
| `ext:log "api_key" OR "apikey"` | `ext:log (api_key OR apikey)` | `filetype:log api_key` | `mime:log "api_key"` |
| `inurl:storage/logs "laravel.log"` | `instreamset:url:storage/logs "laravel.log"` | `inurl:storage/logs laravel.log` | `url:storage/logs "laravel.log"` |
| `intitle:"index of" "catalina.out"` | `intitle:"index of" "catalina.out"` | `intitle:"index of" catalina.out` | `title:"index of" "catalina.out"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Logs em diretórios abertos, por extensão — 5 variações

```text
intitle:"index of" ext:log.1
intitle:"index of" ext:log.gz
intitle:"index of" ext:out
intitle:"index of" ext:err
intitle:"index of" ext:trace
```

> **Padrão:** Arquivos de log por nome conhecido — 4 variações

```text
intitle:"index of" "laravel.log"
intitle:"index of" "php_errors.log"
intitle:"index of" "production.log"
intitle:"index of" "app.log"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Changelogs** e "release logs" não são logs de runtime; filtre com `-changelog -release`.
- O conteúdo de um `.log` só é indexado quando servido como **texto** e **sem** `robots.txt`/headers bloqueando. Muitos achados são só o nome no listing.
- Logs rotacionados seguem padrão previsível (`access.log.1`, `error.log.2024-01-01`) — útil para a [Expansão](#-expansão-sistemática).
- Stack traces revelam **caminhos absolutos**, versões de framework e, às vezes, trechos de query — informação valiosa para pivôs, mesmo sem credenciais.

<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Dumps de Banco de Dados](dumps-de-banco-de-dados.md) · [Próximo: Arquivos de Configuração →](arquivos-de-configuracao.md)

</div>
