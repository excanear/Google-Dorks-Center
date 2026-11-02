<div align="center">

[🏠 Hub](../../README.md)

# 🏢 Recon de Organização

*Mapear a superfície de uma organização autorizada: subdomínios, e-mails corporativos, documentos, presença em terceiros e stack de tecnologia/fornecedores.*

</div>

---

> [!CAUTION]
> Recon de organização é para **alvos autorizados** (pentest com escopo, bug bounty no programa, due diligence). Coleta passiva ≠ interação. Dados de pessoas aparecem **em agregado** (padrões corporativos), nunca para perseguir um indivíduo. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📂 Subcategorias

| # | Subcategoria | Conteúdo | Risco |
|---|---|---|---|
| 1 | [🌍 Subdomínios & Hosts](subdominios-e-hosts.md) | `site:*.alvo`, pivôs de host | 🟢 |
| 2 | [📧 E-mails & Pessoas](emails-e-pessoas.md) | Padrões de e-mail, diretórios (agregado) | 🟡 |
| 3 | [📑 Documentos & Metadados](documentos-e-metadados.md) | Documentos da org que vazam usuários/software | 🟡 |
| 4 | [🔗 Presença em Terceiros](presenca-em-terceiros.md) | Paste sites, repositórios, boards públicos | 🟡 |
| 5 | [🧩 Tecnologia & Fornecedores](tecnologia-e-fornecedores.md) | Stack, SaaS e fornecedores | 🟢 |

## 🧭 Como usar esta categoria

1. Comece pelos **subdomínios** para desenhar a superfície; depois cruze com infraestrutura e documentos.
2. Use Wayback/Common Crawl para enumerar URLs históricas de forma 100% passiva ([manual de código](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md)).
3. E-mails/pessoas são tratados como **padrão corporativo** (ex.: formato `nome.sobrenome@empresa`), não alvo individual.

## 🔗 Categorias relacionadas

- Fingerprint de produto/versão → [04 · Tecnologias](../04-tecnologias/README.md)
- Segredos e tokens da org → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md)
- SOCMINT (perfis em redes) → [08 · Pessoas & SOCMINT](../08-pessoas-e-socmint/README.md)

<div align="center">

[🏠 Hub](../../README.md)

</div>
