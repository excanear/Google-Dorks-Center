<div align="center">

[🏠 Hub](../../README.md) · [🖧 Infraestrutura Web](README.md) · [← Interfaces de Gerenciamento](interfaces-de-gerenciamento.md)

# 🏷 Versões & Software Exposto

*Banners, cabeçalhos e páginas padrão que revelam produto e versão — base para avaliar superfície e correlacionar com CVEs.*

</div>

---

> [!CAUTION]
> Identificar versão é recon passivo. Testar exploits exige autorização e está fora do escopo deste repositório. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Páginas padrão e banners

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Apache2 Ubuntu Default Page"` | Apache recém-instalado | Google | 🟢 |
| `intitle:"Welcome to nginx!"` | Nginx sem configuração | Google | 🟢 |
| `intitle:"IIS Windows Server" "Internet Information Services"` | IIS padrão | Google | 🟢 |
| `intext:"Powered by" "v" inurl:/` | Rodapés com versão | Google | 🟡 |
| `intitle:"Index of" "Server at" "Apache/2"` | Versão do Apache no rodapé do listing | Google | 🟡 |

### Versão por produto

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"Powered by WordPress" inurl:/` | Rodapé WordPress | Google | 🟡 |
| `"Powered by vBulletin"` | Fórum vBulletin | Google | 🟡 |
| `intext:"Joomla! - Open Source Content Management"` | Fingerprint Joomla | Google | 🟡 |
| `intext:"This site is powered by Drupal"` | Fingerprint Drupal | Google | 🟡 |
| `intitle:"Dashboard" "Powered by Grafana v"` | Versão do Grafana | Google | 🟡 |
| `intext:"Server: Apache/2.4" intitle:"index of"` | Apache 2.4.x específico | Google | 🟡 |

### Cabeçalhos vazados em conteúdo

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"X-Powered-By: PHP/"` | Versão de PHP vazada em dump/debug | Google | 🟡 |
| `intext:"X-Powered-By: Express"` | Stack Node/Express | Google | 🟢 |
| `intext:"X-AspNet-Version"` | Versão do ASP.NET | Google | 🟡 |
| `intext:"Server: Microsoft-IIS/"` | Versão do IIS | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

> Versão/banner é o território natural de **Shodan/Censys/FOFA**.

| Google | Shodan | Censys | FOFA |
|---|---|---|---|
| `intitle:"Welcome to nginx!"` | `http.title:"Welcome to nginx!"` | `web.endpoints.http.title:"Welcome to nginx!"` | `title="Welcome to nginx!"` |
| `intext:"Server: Apache/2.4"` | `product:Apache version:2.4` | `host.services.software:(product="Apache")` | `header="Apache/2.4"` |
| `intext:"X-Powered-By: PHP/"` | `http.component:"PHP"` | `host.services.software:(product="PHP")` | `header="X-Powered-By: PHP"` |
| `intext:"Server: Microsoft-IIS/"` | `product:"Microsoft IIS httpd"` | `host.services.software:(product="IIS")` | `header="Microsoft-IIS"` |
| `"Powered by vBulletin"` | `http.html:"Powered by vBulletin"` | `web.endpoints.http.body:"vBulletin"` | `body="Powered by vBulletin"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Cabeçalho de versão vazado em conteúdo — 6 variações

```text
intext:"X-Powered-By: ASP.NET"
intext:"Server: Apache/2.2"
intext:"Server: Apache/2.4"
intext:"Server: nginx/1."
intext:"X-Generator: Drupal"
intext:"X-Drupal-Cache"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Páginas padrão (Apache/nginx/IIS) indicam servidor **recém-instalado ou abandonado** — 🟢, mas ótimo sinal de superfície esquecida.
- Banner de versão pode ser **falsificado** (`ServerTokens`, `server_tokens off`); confirme antes de concluir vulnerabilidade.
- A associação versão → CVE pertence a avaliação de vulnerabilidade; os dorks aqui **identificam**, não exploram.
- Para varredura de versão em escala, Shodan/Censys/FOFA superam os buscadores web — veja a tradução.

<div align="center">

[🏠 Hub](../../README.md) · [🖧 Infraestrutura Web](README.md) · [← Interfaces de Gerenciamento](interfaces-de-gerenciamento.md)

</div>
