<div align="center">

[🏠 Hub](../../README.md) · [🏢 Recon de Organização](README.md) · [← Subdomínios & Hosts](subdominios-e-hosts.md) · [Próximo: Documentos & Metadados →](documentos-e-metadados.md)

# 📧 E-mails & Pessoas

*Padrões de e-mail corporativo e diretórios de equipe — em agregado, para mapear a organização, nunca para perseguir um indivíduo.*

</div>

---

> [!CAUTION]
> Trate dados de pessoas com **minimização** (LGPD/GDPR): colete só o necessário ao escopo autorizado, em agregado. **Nada aqui serve para localizar ou assediar uma pessoa específica.** Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Padrão de e-mail corporativo

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"@alvo.com" -site:alvo.com` | E-mails do domínio citados fora do site | Google | 🟡 |
| `site:alvo.com intext:"@alvo.com"` | Formato de e-mail no próprio site | Google | 🟡 |
| `"@alvo.com" filetype:pdf` | E-mails em documentos públicos | Google | 🟡 |
| `"@alvo.com" (intext:"diretor" OR intext:"gerente")` | Papéis corporativos (agregado) | Google | 🟡 |
| `site:alvo.com inurl:contact OR inurl:equipe OR inurl:team` | Páginas de contato/equipe | Google | 🟢 |

### Diretórios e listas

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:alvo.com (intitle:"team" OR intitle:"nossa equipe")` | Página de equipe | Google | 🟢 |
| `site:alvo.com filetype:pdf "ramal" OR "extension"` | Listas de ramais em documentos | Google | 🟡 |
| `"@alvo.com" site:linkedin.com/company` | Página corporativa no LinkedIn | Google | 🟢 |
| `"works at alvo" OR "trabalha na alvo" site:linkedin.com/in` | Colaboradores (agregado, não indivíduo) | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `intext:"@alvo.com" -site:alvo.com` | `inbody:"@alvo.com" -site:alvo.com` | `"@alvo.com" -site:alvo.com` |
| `"@alvo.com" filetype:pdf` | `"@alvo.com" filetype:pdf` | `"@alvo.com" filetype:pdf` |
| `site:alvo.com inurl:team` | `site:alvo.com instreamset:url:team` | `site:alvo.com inurl:team` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->
<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- O objetivo é descobrir o **formato** de e-mail da organização (`nome.sobrenome@`, `inicialsobrenome@`) e o tamanho da superfície humana — não construir dossiê de indivíduo.
- Minimize: não armazene listas de pessoas além do necessário ao escopo; respeite LGPD/GDPR.
- Para engenharia social autorizada, o formato de e-mail basta; dados pessoais detalhados estão fora deste repositório.
- SOCMINT (perfis pessoais) tem seus próprios limites em [08 · Pessoas & SOCMINT](../08-pessoas-e-socmint/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [🏢 Recon de Organização](README.md) · [← Subdomínios & Hosts](subdominios-e-hosts.md) · [Próximo: Documentos & Metadados →](documentos-e-metadados.md)

</div>
