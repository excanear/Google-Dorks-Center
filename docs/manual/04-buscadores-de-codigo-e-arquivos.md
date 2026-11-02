<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [← Infraestrutura](03-buscadores-de-infraestrutura.md) · [Próximo: Tradução →](05-traducao-entre-buscadores.md)

# 💻 Manual — Buscadores de Código & Arquivos

*GitHub Code Search, GitLab, Sourcegraph, grep.app, PublicWWW, Wayback/CDX e Common Crawl. Verificado em 2026-11.*

</div>

---

> [!CAUTION]
> Segredos em repositórios públicos são o vazamento mais comum. Encontrar uma chave **não autoriza usá-la**: reporte ao dono para rotação. Em pentest, confirme o escopo. Veja [OPSEC](06-metodologia-recon-e-opsec.md).

## 📑 Nesta página

- [GitHub Code Search](#-github-code-search)
- [GitLab](#-gitlab)
- [Sourcegraph](#-sourcegraph)
- [grep.app](#-grepapp)
- [PublicWWW](#-publicwww)
- [Wayback Machine & CDX API](#-wayback-machine--cdx-api)
- [Common Crawl](#-common-crawl)

---

## 🐙 GitHub Code Search

A busca de código mais rica. Sintaxe de qualificadores `chave:valor`, com suporte a regex entre barras `/.../`.

| Qualificador | Função | Exemplo |
|---|---|---|
| `/regex/` | Expressão regular | `/AKIA[0-9A-Z]{16}/` |
| `path:` | Caminho/arquivo | `path:.env` |
| `language:` | Linguagem | `language:python` |
| `repo:` | Repositório específico | `repo:org/app` |
| `org:` / `user:` | Organização / usuário | `org:alvo` |
| `filename:` | Nome de arquivo | `filename:config.php` |
| `extension:` | Extensão | `extension:pem` |
| `symbol:` | Definição de símbolo | `symbol:connectDB` |
| `content:` | Conteúdo literal | `content:"BEGIN RSA PRIVATE KEY"` |
| `AND` `OR` `NOT` | Booleanos | `path:.env AND DB_PASSWORD` |

```dork
org:alvo path:.env (AWS_SECRET_ACCESS_KEY OR DB_PASSWORD)
```

> **Pegadinhas:** a busca indexa o **branch padrão** de repositórios públicos; exige login. Regex é **poderosíssimo** para padrões de segredo. Use `path:` em vez do antigo `filename:` quando quiser casar caminho completo.

## 🦊 GitLab

Busca por escopo (projetos, código, commits). Menos operadores que o GitHub.

| Recurso | Função |
|---|---|
| busca por projeto | restringe ao projeto/grupo |
| `filename:` | nome de arquivo (scope: blobs) |
| `path:` | caminho |
| `extension:` | extensão |

> A busca avançada (Elasticsearch) só está disponível em instâncias que a habilitam; em `gitlab.com`, varia por plano.

## 🔷 Sourcegraph

Busca de código multi-repo com filtros poderosos e regex. Útil para varrer OSS em massa.

| Filtro | Função |
|---|---|
| `repo:` | Regex de repositório |
| `file:` | Regex de caminho |
| `lang:` | Linguagem |
| `content:` | Conteúdo |
| `case:yes` | Sensível a maiúsculas |
| `type:symbol` | Busca símbolos |
| `patterntype:regexp` | Ativa regex |

```dork
repo:alvo file:\.env$ patterntype:regexp (SECRET|TOKEN|PASSWORD)
```

## 🔎 grep.app

Busca literal/regex em centenas de milhares de repositórios públicos, muito rápida. Sem login.

| Recurso | Função |
|---|---|
| texto literal | casa exato em qualquer repo público |
| regex (toggle) | ativa expressões regulares |
| filtro por linguagem/repo/path | refina resultados |

> Ótimo para medir **quão difundido** é um padrão (ex.: uma chave de API default de uma lib).

## 🌍 PublicWWW

Busca no **código-fonte HTML/JS** das páginas (não no texto visível). Acha quem usa um snippet, ID de analytics, chave pública ou biblioteca.

| Uso | Exemplo |
|---|---|
| ID de Analytics | `"UA-12345678"` |
| AdSense | `"pub-1234567890"` |
| snippet/lib | `"wp-content/plugins/plugin-x"` |
| chave pública de serviço | `"pk_live_"` |

> **Força:** pivô de **ownership** — descobrir todos os sites que compartilham um identificador. Plano gratuito limita resultados.

## 🏛 Wayback Machine & CDX API

Substitui o falecido `cache:`. Recupera versões históricas e **enumera URLs** já vistas de um domínio.

- **Interface:** `https://web.archive.org/web/*/alvo.com/*`
- **CDX API (enumeração de URLs):**
```dork
https://web.archive.org/cdx/search/cdx?url=alvo.com*&output=text&fl=original&collapse=urlkey
```

> **Força:** a CDX revela endpoints, parâmetros e arquivos **já removidos** do site atual — base para recon histórico. Veja também [Archive.today](https://archive.ph/).

## 🗺 Common Crawl

Corpus público de varreduras da web. Via **index API**, lista todas as URLs capturadas de um domínio.

```dork
https://index.commoncrawl.org/CC-MAIN-2024-latest-index?url=alvo.com*&output=json
```

> Escala de petabytes: ideal para enumeração massiva de URLs/subdomínios de forma 100% passiva, sem tocar no alvo.

<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [← Infraestrutura](03-buscadores-de-infraestrutura.md) · [Próximo: Tradução →](05-traducao-entre-buscadores.md)

</div>
