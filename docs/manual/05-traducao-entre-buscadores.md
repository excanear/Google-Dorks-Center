<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [← Código & Arquivos](04-buscadores-de-codigo-e-arquivos.md) · [Próximo: Metodologia & OPSEC →](06-metodologia-recon-e-opsec.md)

# 🔁 Tradução entre Buscadores

*A matriz que quase nenhum repositório tem: o mesmo operador e o mesmo dork, lado a lado, em cada buscador.*

</div>

---

## 🧭 Matriz de operadores (web)

| Intenção | Google | Bing | DuckDuckGo | Yandex | Brave |
|---|---|---|---|---|---|
| Domínio | `site:` | `site:` | `site:` | `site:` / `domain:` | `site:` |
| Tipo de arquivo | `filetype:` | `filetype:`/`ext:` | `filetype:` | `mime:` | `filetype:` |
| Trecho de URL | `inurl:` | `instreamset:url:` | `inurl:` | `inurl:`/`url:` | — |
| Título | `intitle:` | `intitle:` | `intitle:` | `title:` | `intitle:` |
| Corpo | `intext:` | `inbody:` | `intext:` | — | `inbody:` |
| Frase exata | `"..."` | `"..."` | `"..."` | `"..."` | `"..."` |
| Exclusão | `-termo` | `-termo` | `-termo` | `~termo` *(não)* `-termo` | `-termo` |
| OU | `OR`/`\|` | `OR` | `OR` | `\|` | `OR` |
| Proximidade | `AROUND(n)` | `NEAR:n` | — | `/n` | — |
| Por IP | — | `ip:` | — | — | — |
| Reverse host | — | — | — | `rhost:` | — |

> **Regra prática:** o que o Bing chama `instreamset:url:` o Google chama `inurl:`; o que o Yandex chama `mime:` o Google chama `filetype:`.

## 🛰 Web → Infraestrutura

Alguns dorks web têm correspondente em buscadores de dispositivo:

| Intenção | Google (web) | Shodan | Censys | FOFA |
|---|---|---|---|---|
| Diretório aberto | `intitle:"index of /"` | `http.title:"Index of /"` | `web.endpoints.http.title:"Index of /"` | `title="Index of /"` |
| Painel por título | `intitle:"Grafana"` | `http.title:"Grafana"` | `web.endpoints.http.title:"Grafana"` | `title="Grafana"` |
| Produto/versão | `intext:"Server: nginx/1.18"` | `product:nginx version:1.18` | `host.services.software:(product="nginx")` | `app="nginx" && version="1.18"` |
| Por domínio no cert | — | `ssl.cert.subject.cn:alvo.com` | `...common_name:alvo.com` | `cert="alvo.com"` |

## 🐙 Web → Código

| Intenção | Google (web) | GitHub Code Search | Sourcegraph |
|---|---|---|---|
| Arquivo `.env` | `intitle:"index of" ".env"` | `path:.env` | `file:\.env$` |
| Chave privada | `ext:key "BEGIN RSA PRIVATE KEY"` | `/BEGIN RSA PRIVATE KEY/` | `content:"BEGIN RSA PRIVATE KEY"` |
| Config com senha | `ext:json "password"` | `path:*.json password` | `file:\.json$ password` |

## 🧪 30 dorks traduzidos lado a lado

> Formato: **intenção** → Google · Bing · DuckDuckGo · Yandex.

1. **PDFs internos** → `site:x filetype:pdf "uso interno"` · `site:x filetype:pdf "uso interno"` · `site:x filetype:pdf "uso interno"` · `site:x mime:pdf "uso interno"`
2. **Diretório aberto** → `intitle:"index of /"` · `intitle:"index of /"` · `intitle:"index of /"` · `title:"index of /"`
3. **Painel admin por URL** → `inurl:admin` · `instreamset:url:admin` · `inurl:admin` · `url:admin`
4. **Planilha com senha** → `filetype:xlsx "password"` · `ext:xlsx password` · `filetype:xlsx password` · `mime:xlsx "password"`
5. **Dump SQL** → `ext:sql "INSERT INTO"` · `ext:sql "INSERT INTO"` · `filetype:sql "INSERT INTO"` · `mime:sql "INSERT INTO"`
6. **Config web.config** → `ext:config "connectionStrings"` · `ext:config connectionStrings` · `filetype:config connectionStrings` · `mime:config "connectionStrings"`
7. **Login por título** → `intitle:"login"` · `intitle:"login"` · `intitle:"login"` · `title:"login"`
8. **Erro com stack** → `intext:"Stack trace"` · `inbody:"Stack trace"` · `intext:"Stack trace"` · `"Stack trace"`
9. **Subdomínio dev** → `site:*.x inurl:dev` · `site:x instreamset:url:dev` · `site:x inurl:dev` · `rhost:*.x.* url:dev`
10. **Arquivo .env** → `intitle:"index of" ".env"` · `intitle:"index of" ".env"` · `intitle:"index of" ".env"` · `title:"index of" ".env"`
11. **Log exposto** → `ext:log` · `ext:log` · `filetype:log` · `mime:log`
12. **Chave privada** → `ext:key "PRIVATE KEY"` · `ext:key "PRIVATE KEY"` · `filetype:key "PRIVATE KEY"` · `mime:key "PRIVATE KEY"`
13. **Backup zip** → `intitle:"index of" "backup.zip"` · idem · idem · `title:"index of" "backup.zip"`
14. **Git exposto** → `intitle:"index of" "/.git"` · idem · idem · `title:"index of" "/.git"`
15. **Documento confidencial** → `filetype:docx "confidential"` · `ext:docx confidential` · `filetype:docx confidential` · `mime:docx "confidential"`
16. **CSV de clientes** → `filetype:csv "email" "phone"` · `ext:csv email phone` · `filetype:csv email phone` · `mime:csv "email" "phone"`
17. **Terraform state** → `intitle:"index of" "terraform.tfstate"` · idem · idem · `title:"index of" "terraform.tfstate"`
18. **phpMyAdmin** → `intitle:"phpMyAdmin" inurl:index.php` · `intitle:"phpMyAdmin"` · `intitle:"phpMyAdmin"` · `title:"phpMyAdmin"`
19. **Câmera por título** → `intitle:"Live View" "AXIS"` · `intitle:"Live View" AXIS` · idem · `title:"Live View" AXIS`
20. **Documento gov** → `site:gov.br filetype:pdf` · `site:gov.br filetype:pdf` · idem · `site:gov.br mime:pdf`
21. **Pasta uploads** → `inurl:/wp-content/uploads/` · `instreamset:url:wp-content/uploads` · `inurl:wp-content/uploads` · `url:wp-content/uploads`
22. **Token em log** → `ext:log "bearer"` · `ext:log bearer` · `filetype:log bearer` · `mime:log "bearer"`
23. **Fatura PDF** → `filetype:pdf "invoice" "amount due"` · `ext:pdf invoice "amount due"` · idem · `mime:pdf invoice "amount due"`
24. **Sheet público** → `site:docs.google.com/spreadsheets` · `site:docs.google.com spreadsheets` · idem · `site:docs.google.com spreadsheets`
25. **Diretório /private** → `intitle:"index of" "/private"` · idem · idem · `title:"index of" "/private"`
26. **SOP/POP** → `filetype:pdf "standard operating procedure"` · `ext:pdf "standard operating procedure"` · idem · `mime:pdf "standard operating procedure"`
27. **Config .ini banco** → `ext:ini "[database]"` · `ext:ini "[database]"` · `filetype:ini "[database]"` · `mime:ini "[database]"`
28. **Keystore JKS** → `intitle:"index of" ext:jks` · `intitle:"index of" ext:jks` · `intitle:"index of" filetype:jks` · `title:"index of" mime:jks`
29. **Apresentação roadmap** → `filetype:pptx "roadmap" "confidential"` · `ext:pptx roadmap confidential` · idem · `mime:pptx roadmap confidential`
30. **Pasta de scans** → `intitle:"index of" "scans"` · idem · idem · `title:"index of" "scans"`

<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [← Código & Arquivos](04-buscadores-de-codigo-e-arquivos.md) · [Próximo: Metodologia & OPSEC →](06-metodologia-recon-e-opsec.md)

</div>
