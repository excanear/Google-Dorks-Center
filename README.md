<div align="center">

# 🎯 Google-Dorks-Center

**O repositório de dorks mais extenso e completo — multi-buscador, com arsenal pronto e manual para montar os seus.**

Google · Bing · DuckDuckGo · Yandex · Shodan · Censys · FOFA · GitHub · e mais

![Dorks](https://img.shields.io/badge/dorks-2966%2B-0a66c2?style=for-the-badge)
![Buscadores](https://img.shields.io/badge/buscadores-20%2B-success?style=for-the-badge)
![Categorias](https://img.shields.io/badge/categorias-19-blueviolet?style=for-the-badge)
![Idioma](https://img.shields.io/badge/idioma-PT--BR-green?style=for-the-badge)
![Foco](https://img.shields.io/badge/uso-ético%20%26%20legal-critical?style=for-the-badge)
![PRs](https://img.shields.io/badge/PRs-welcome-brightgreen?style=for-the-badge)

*Curadoria orientada a profissionais de OSINT, Pentest, Threat Intelligence, Bug Bounty, Red Team e Jornalismo Investigativo.*

</div>

---

> [!CAUTION]
> ## ⚖ Aviso de Uso Legal e Ético
>
> Este repositório é **exclusivamente educacional e profissional**. Os dorks listados servem para investigações **autorizadas, legítimas e proporcionais** — pentest com escopo contratado, bug bounty dentro do programa, threat intelligence, defesa cibernética, due diligence, jornalismo investigativo e pesquisa acadêmica.
>
> - **Localizar ≠ acessar.** Encontrar um recurso indexado **não autoriza** baixá-lo, acessá-lo, redistribuí-lo ou usá-lo. Fazer isso sem autorização pode configurar crime.
> - **É proibido** usar estes recursos para invasão não autorizada, stalking, assédio, doxxing, fraude, extorsão, vigilância ilegal ou qualquer violação de privacidade.
> - Respeite a legislação aplicável: **LGPD** (Brasil), **GDPR** (UE), **Marco Civil da Internet**, **Lei 12.737/2012** (crimes informáticos), **CFAA** (EUA) e **Computer Misuse Act** (Reino Unido), além dos **Termos de Serviço** de cada buscador.
> - **Dados vazados** (breaches, stealer logs, combolists) têm restrições legais severas de posse e uso. Consulte o jurídico.
> - Automação contra buscadores viola ToS e dispara bloqueios — use **APIs oficiais** quando precisar de volume.
> - Os mantenedores **não se responsabilizam** pelo uso indevido. A inclusão de um dork **não é incentivo** ao uso ilícito.

---

## 📑 Índice

<details open>
<summary><b>Navegação rápida</b></summary>

| Fundamentos | Manual | Categorias de Dorks | Operação |
|---|---|---|---|
| [Overview](#-overview) | [Construtor de Dorks](docs/manual/00-construtor-de-dorks.md) | [01 · Exposição de Arquivos](dorks/01-exposicao-de-arquivos/README.md) | [Cheat Sheet](#-cheat-sheet-google) |
| [Legenda](#-legenda) | [Google](docs/manual/01-google.md) | [02–19 · Mapa](#-mapa-de-categorias) | [Top Dorks](#-top-dorks) |
| [Contadores](#-contadores) | [Buscadores Web](docs/manual/02-buscadores-web.md) | [Mapa de Categorias](#-mapa-de-categorias) | [Contributing](#-contributing) |
| [Como usar](#-como-usar) | [Infraestrutura](docs/manual/03-buscadores-de-infraestrutura.md) · [Código](docs/manual/04-buscadores-de-codigo-e-arquivos.md) | | [Tradução](docs/manual/05-traducao-entre-buscadores.md) · [OPSEC](docs/manual/06-metodologia-recon-e-opsec.md) |

</details>

---

## 🌐 Overview

**Dorking** é o uso de operadores avançados de busca para encontrar, com precisão, informação que está publicamente indexada mas difícil de achar por busca comum. Este repositório é ao mesmo tempo:

- **Arsenal** — dorks prontos, curados e organizados por categoria, para copiar e colar.
- **Manual** — como montar seus próprios dorks para **qualquer** alvo, em **qualquer** buscador.

| Princípio | Como aplicamos |
|---|---|
| **Cobertura real + volume** | Dorks curados com finalidade clara **e** expansão sistemática por extensões, pastas, produtos e caminhos — cada variação com sentido técnico. |
| **Multi-buscador** | Cada dork pode ser traduzido para Bing, DuckDuckGo, Yandex, Shodan, Censys, FOFA, GitHub e outros. |
| **Sem duplicatas** | Cada dork aparece em **uma** categoria principal; um [validador](#-contadores) garante isso. |
| **Status verificado** | Operadores mortos (`cache:`, `info:`, `link:`) ficam só no manual, marcados ❌. |
| **Ética e legalidade** | Dorks sensíveis são sinalizados com 🔴/⚠; nada que mire pessoa física específica. |

---

## 🏷 Legenda

| Campo | Valores |
|---|---|
| **Risco** | 🟢 **Baixo** (recon/público) · 🟡 **Médio** (info sensível/infra) · 🔴 **Alto** (credenciais, dados pessoais, chaves) |
| **Buscadores** | `Google` · `Bing` · `DuckDuckGo` · `Yandex` · `Shodan` · `Censys` · `FOFA` · `GitHub` … |
| **Status de operador** | ✅ ativo · ⚠ instável/não-oficial · ❌ desativado |
| **Marcadores** | ⚠ especialmente sensível (privacidade/legal) · 🇧🇷 foco Brasil |

---

## 🔢 Contadores

| Métrica | Valor |
|---|---|
| **Dorks curados** | 1249 |
| **Dorks expandidos** | 1717 |
| **Total** | **2966** |
| **Categorias** | 19 (todas completas) |
| **Subcategorias** | 90+ |
| **Buscadores documentados** | 20+ |
| **Atualizado em** | 2026-11 |

> Cada dork é **distinto e útil** — a meta é o máximo de dorks reais e o máximo de categorias, sem padding. Regra de **zero duplicatas** e **sentido técnico** em cada variação, conferida por validador automático (dedupe global em todo o repositório).

---

## 🧭 Como usar

1. Vá à categoria do que você procura (comece por [Exposição de Arquivos](dorks/01-exposicao-de-arquivos/README.md)).
2. Copie um dork **curado** ou um bloco da **expansão sistemática**.
3. Restrinja ao escopo autorizado com `site:alvo.com`.
4. Precisa de outro buscador? Veja a [matriz de tradução](docs/manual/05-traducao-entre-buscadores.md).
5. Não sabe montar? Comece pelo [Construtor de Dorks](docs/manual/00-construtor-de-dorks.md).

---

## ⚡ Cheat Sheet (Google)

| Operador | Função | Exemplo |
|---|---|---|
| `site:` | Domínio/TLD | `site:gov.br` |
| `filetype:` / `ext:` | Tipo de arquivo | `filetype:pdf` |
| `intitle:` / `allintitle:` | Termo no título | `intitle:"index of"` |
| `inurl:` / `allinurl:` | Termo na URL | `inurl:admin` |
| `intext:` / `allintext:` | Termo no corpo | `intext:"senha"` |
| `"..."` | Frase exata | `"strictly confidential"` |
| `-` | Exclui termo | `-template` |
| `OR` / `\|` / `( )` | OU / agrupamento | `(sql OR dump)` |
| `*` | Curinga de palavra | `"user * admin"` |
| `before:` / `after:` | Data | `after:2024-01-01` |
| `cache:` `info:` `link:` `+` `~` | ❌ **desativados** | use o [Wayback](https://web.archive.org/) |

Cheat sheet completo e por buscador no [Manual](docs/manual/README.md).

---

## 🏆 Top Dorks

> Links para os dorks mais úteis (sem duplicar o conteúdo — cada um vive na sua categoria).

| # | Alvo | Onde |
|---|---|---|
| 1 | Diretórios abertos (`index of /`) | [Diretórios Abertos](dorks/01-exposicao-de-arquivos/diretorios-abertos.md) |
| 2 | Dumps SQL expostos | [Dumps de Banco](dorks/01-exposicao-de-arquivos/dumps-de-banco-de-dados.md) |
| 3 | Backups no webroot | [Backups & Compactados](dorks/01-exposicao-de-arquivos/backups-e-arquivos-compactados.md) |
| 4 | Chaves privadas e certificados | [Chaves & Certificados](dorks/01-exposicao-de-arquivos/chaves-e-certificados.md) |
| 5 | Planilhas com dados pessoais | [Planilhas & CSV](dorks/01-exposicao-de-arquivos/planilhas-e-csv.md) |
| 6 | Logs vazando tokens | [Logs](dorks/01-exposicao-de-arquivos/logs.md) |
| 7 | Configs com credenciais | [Arquivos de Configuração](dorks/01-exposicao-de-arquivos/arquivos-de-configuracao.md) |
| 8 | Documentos confidenciais | [Documentos & PDF](dorks/01-exposicao-de-arquivos/documentos-office-e-pdf.md) |
| 9 | Arquivos `.env` com segredos | [Variáveis de Ambiente](dorks/02-credenciais-e-segredos/variaveis-de-ambiente-env.md) |
| 10 | Tokens de API por provedor | [Tokens de API](dorks/02-credenciais-e-segredos/tokens-de-api.md) |
| 11 | Painéis de login e admin | [Painéis de Login](dorks/03-infraestrutura-web/paineis-de-login.md) |
| 12 | phpMyAdmin e consoles de banco | [Interfaces de Gerenciamento](dorks/03-infraestrutura-web/interfaces-de-gerenciamento.md) |
| 13 | Bancos de dados expostos | [Bancos de Dados](dorks/04-tecnologias/bancos-de-dados.md) |
| 14 | Buckets S3/Azure/GCP abertos | [AWS S3](dorks/05-cloud-e-storage/aws-s3.md) |
| 15 | Câmeras e dispositivos expostos | [Câmeras & DVR](dorks/06-iot-ics-scada/cameras-e-dvr.md) |
| 16 | Subdomínios de uma organização | [Subdomínios & Hosts](dorks/07-recon-de-organizacao/subdominios-e-hosts.md) |
| 17 | SOCMINT (perfis públicos, ético) | [Perfis em Redes Sociais](dorks/08-pessoas-e-socmint/perfis-em-redes-sociais.md) |
| 18 | `.git`/`.svn` e endpoints frágeis | [Arquivos & Endpoints Conhecidos](dorks/09-vulnerabilidades/arquivos-e-endpoints-conhecidos.md) |
| 19 | Transparência e dados públicos 🇧🇷 | [Governo & Transparência](dorks/10-brasil/governo-e-transparencia.md) |
| 20 | Seeds/carteiras de cripto expostas | [Cripto & Blockchain](dorks/11-tematicos/cripto-e-blockchain.md) |
| 21 | Swagger/OpenAPI e GraphQL expostos | [Documentação de API](dorks/12-apis-e-webhooks/documentacao-de-api.md) |
| 22 | Webhooks Slack/Discord vazados | [Webhooks](dorks/12-apis-e-webhooks/webhooks.md) |
| 23 | Webmail (OWA/Zimbra/Roundcube) | [Interfaces de Webmail](dorks/13-email-e-webmail/webmail-interfaces.md) |
| 24 | Portais SSL-VPN (Pulse/SonicWall…) | [Portais VPN](dorks/14-wifi-redes-vpn/portais-vpn.md) |
| 25 | Admin de loja (Magento/PrestaShop) | [Plataformas de Loja](dorks/15-ecommerce-e-pagamentos/plataformas-de-loja.md) |
| 26 | Rastreamento GPS/frota exposto | [Rastreamento & Frota](dorks/16-mapas-e-geoint/rastreamento-e-frota.md) |
| 27 | `google-services.json` e segredos mobile | [Strings & Segredos Mobile](dorks/17-mobile/strings-e-segredos-mobile.md) |
| 28 | Monitorar exposição do seu domínio (defensivo) | [Monitoramento de Paste](dorks/18-darkweb-paste-leaks/paste-monitoring.md) |
| 29 | PACS/DICOM e portais de saúde expostos | [Saúde & Médico](dorks/19-setores-e-nichos/saude-e-medico.md) |

---

## 🗺 Mapa de Categorias

| # | Categoria | Status |
|---|---|---|
| 01 | [Exposição de Arquivos](dorks/01-exposicao-de-arquivos/README.md) | ✅ Completa |
| 02 | [Credenciais & Segredos](dorks/02-credenciais-e-segredos/README.md) (`.env`, tokens, segredos) | ✅ Completa |
| 03 | [Infraestrutura Web](dorks/03-infraestrutura-web/README.md) (login, admin, erro/debug, versões) | ✅ Completa |
| 04 | [Tecnologias](dorks/04-tecnologias/README.md) (CMS, frameworks, servidores, bancos, CI/CD) | ✅ Completa |
| 05 | [Cloud & Storage](dorks/05-cloud-e-storage/README.md) (S3, Azure, GCP, Firebase) | ✅ Completa |
| 06 | [IoT & ICS/SCADA](dorks/06-iot-ics-scada/README.md) (câmeras, roteadores, impressoras, NAS) | ✅ Completa |
| 07 | [Recon de Organização](dorks/07-recon-de-organizacao/README.md) (subdomínios, e-mails, stack) | ✅ Completa |
| 08 | [Pessoas & SOCMINT](dorks/08-pessoas-e-socmint/README.md) (padrões amplos por rede) | ✅ Completa |
| 09 | [Vulnerabilidades](dorks/09-vulnerabilidades/README.md) (SQLi, LFI, open redirect, XSS) | ✅ Completa |
| 10 | [Brasil 🇧🇷](dorks/10-brasil/README.md) (gov.br, diários, licitações, transparência) | ✅ Completa |
| 11 | [Temáticos](dorks/11-tematicos/README.md) (jornalismo, cripto, acadêmico, vagas, games) | ✅ Completa |
| 12 | [APIs & Webhooks](dorks/12-apis-e-webhooks/README.md) (Swagger, GraphQL, chaves, webhooks) | ✅ Completa |
| 13 | [E-mail & Webmail](dorks/13-email-e-webmail/README.md) (OWA, Zimbra, MTA, mbox, relay) | ✅ Completa |
| 14 | [Wi-Fi, Redes & VPN](dorks/14-wifi-redes-vpn/README.md) (SSL-VPN, WLAN, NMS, PSK) | ✅ Completa |
| 15 | [E-commerce & Pagamentos](dorks/15-ecommerce-e-pagamentos/README.md) (Magento, checkout, pedidos) | ✅ Completa |
| 16 | [Mapas & GEOINT](dorks/16-mapas-e-geoint/README.md) (KML/GPX, GeoServer, rastreamento) | ✅ Completa |
| 17 | [Mobile](dorks/17-mobile/README.md) (APK/IPA, plist, segredos, backends) | ✅ Completa |
| 18 | [Dark Web, Paste & Leaks](dorks/18-darkweb-paste-leaks/README.md) (threat-intel **defensivo**) | ✅ Completa |
| 19 | [Setores & Nichos](dorks/19-setores-e-nichos/README.md) (saúde, educação, gov local, nichos) | ✅ Completa |

> **As 19 categorias estão completas** — 90+ subcategorias, cada dork distinto e útil (sem padding). A categoria 18 é **exclusivamente defensiva** (monitorar a exposição do próprio domínio). Próximos marcos possíveis: matriz de tradução completa entre todos os buscadores e uma versão em inglês.

---

## 📘 Manual

| Capítulo | Conteúdo |
|---|---|
| [🧱 Construtor de Dorks](docs/manual/00-construtor-de-dorks.md) | Monte dorks do zero |
| [🔎 Google](docs/manual/01-google.md) | Operadores, status 2026, pegadinhas |
| [🌐 Buscadores Web](docs/manual/02-buscadores-web.md) | Bing, DDG, Yandex, Baidu, Brave… |
| [🛰 Infraestrutura](docs/manual/03-buscadores-de-infraestrutura.md) | Shodan, Censys, FOFA, ZoomEye… |
| [💻 Código & Arquivos](docs/manual/04-buscadores-de-codigo-e-arquivos.md) | GitHub, Sourcegraph, Wayback… |
| [🔁 Tradução entre Buscadores](docs/manual/05-traducao-entre-buscadores.md) | Matriz + 30 dorks lado a lado |
| [🧭 Metodologia & OPSEC](docs/manual/06-metodologia-recon-e-opsec.md) | Recon, pivôs, evidência, legalidade |

---

## 🤝 Contributing

Contribuições são bem-vindas! Para manter a qualidade de **referência**:

1. **Um dork, uma categoria principal.** Verifique duplicatas antes de adicionar.
2. **Formato curado:** `` | `dork` | Finalidade | Buscadores | Risco | ``. Dork entre crases; escape `|` interno como `\|`.
3. **Expansão sistemática:** bloco ` ```text ` precedido de `> **Padrão:** …`, um dork por linha.
4. **Sem operadores mortos** (`cache:`, `info:`, `link:`, `+`, `~`) nos dorks.
5. **Nada que mire pessoa física específica**, facilite stalking, doxxing ou acesso não autorizado.
6. **Marque o risco** (🟢/🟡/🔴) e `⚠` quando houver dados pessoais.

```text
Título do PR:   [Categoria] Adiciona dorks de <assunto>
Descrição:      Finalidade · Buscadores · Risco · Fonte/raciocínio
```

---

<div align="center">

**🎯 Google-Dorks-Center** — *Encontre com precisão. Investigue com ética. Reporte com responsabilidade.*

<sub>A inclusão de um dork não é endosso ao uso indevido. Investigue dentro da lei e do escopo autorizado.</sub>

</div>
