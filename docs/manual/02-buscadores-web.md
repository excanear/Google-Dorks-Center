<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [← Google](01-google.md) · [Próximo: Infraestrutura →](03-buscadores-de-infraestrutura.md)

# 🌐 Manual — Buscadores Web

*Operadores de Bing, DuckDuckGo, Yandex, Baidu, Brave, Startpage, Yahoo, Naver e Mojeek. Status verificado em 2026-11.*

</div>

---

Nenhum buscador replica 100% do Google. Esta página mostra **o que cada um suporta** para você escolher a ferramenta certa e traduzir dorks. A matriz lado a lado está em [Tradução entre buscadores](05-traducao-entre-buscadores.md).

## 📑 Nesta página

- [Bing](#-bing)
- [DuckDuckGo](#-duckduckgo)
- [Yandex](#-yandex)
- [Baidu](#-baidu)
- [Brave Search](#-brave-search)
- [Startpage](#-startpage)
- [Yahoo](#-yahoo)
- [Naver](#-naver)
- [Mojeek](#-mojeek)
- [Resumo comparativo](#-resumo-comparativo)

---

## 🅱 Bing

Documentação oficial da Microsoft cobre a maior parte. Diferenciais úteis: `ip:` e `instreamset:`.

| Operador | Status | Função |
|---|---|---|
| `site:` | ✅ | Restringe a domínio |
| `filetype:` / `ext:` | ✅ | Tipo/extensão de arquivo |
| `intitle:` | ✅ | Termo no título |
| `inbody:` | ✅ | Termo no corpo (equivale a `intext:`) |
| `inanchor:` | ✅ | Termo em texto-âncora |
| `ip:` | ✅ | Páginas hospedadas num IP | 
| `contains:` | ⚠ | Páginas com link para um tipo de arquivo |
| `instreamset:url:` | ⚠ | Filtra por trecho de URL (substitui `inurl:`) |
| `prefer:` | ⚠ | Dá peso a um termo |
| `language:` / `loc:` | ✅ | Idioma / país |
| `NEAR:n` | ⚠ | Proximidade (inconsistente) |

> **Pegadinha:** o Bing **não** tem `inurl:`; use `instreamset:url:trecho`. `intitle:` nem sempre aparece na doc oficial, mas funciona.

## 🦆 DuckDuckGo

Herda o índice do Bing, então aceita boa parte dos operadores do Bing, mas de forma **mais limitada e sem combinações complexas**.

| Operador | Status | Função |
|---|---|---|
| `site:` | ✅ | Domínio |
| `filetype:` | ✅ | Tipo de arquivo |
| `intitle:` | ✅ | Título |
| `inurl:` | ✅ | URL |
| `intext:` | ✅ | Corpo |
| `-` / `"..."` | ✅ | Exclusão / frase exata |
| `OR` | ⚠ | Suportado, mas frágil com muitos grupos |
| **bangs** `!g !gh` | ✅ | Redireciona a busca para outro site (`!gh` = GitHub) |

> **Força:** os **bangs** (`!`) são únicos — `!g dork` joga a mesma busca no Google, `!wayback url` no arquivo. Ótimo para pivotar rápido.

## 🇷🇺 Yandex

O mais poderoso **depois do Google** para dorking; vê conteúdo que outros não indexam.

| Operador | Status | Função |
|---|---|---|
| `site:` | ✅ | Domínio |
| `rhost:` | ✅ | Host na ordem reversa (`com.alvo.*`) |
| `url:` | ✅ | URL exata |
| `inurl:` | ✅ | Trecho de URL |
| `title:` | ✅ | Título (equivale a `intitle:`) |
| `mime:` | ✅ | Tipo de arquivo (`mime:pdf`) |
| `lang:` | ✅ | Idioma |
| `domain:` | ✅ | Domínio/TLD |
| `date:` | ✅ | Data |
| `/n` | ✅ | Proximidade entre palavras |
| `&&` / `\|` | ✅ | AND de frase / OR |

> **Força:** `mime:` + `rhost:` fazem varreduras de arquivo que o Google perde. Bom para imagens e conteúdo regional.

## 🇨🇳 Baidu

Foco no mercado chinês; operadores limitados e melhor para conteúdo em chinês.

| Operador | Status | Função |
|---|---|---|
| `site:` | ✅ | Domínio |
| `inurl:` | ✅ | URL |
| `intitle:` | ✅ | Título |
| `filetype:` | ✅ | Tipo de arquivo |
| `-` / `" "` | ✅ | Exclusão / frase |

> **Pegadinha:** resultados fora da China são irregulares; combinações booleanas complexas falham.

## 🦁 Brave Search

Índice próprio e independente. Operadores básicos, bons para fugir de personalização.

| Operador | Status | Função |
|---|---|---|
| `site:` | ✅ | Domínio |
| `filetype:` | ✅ | Tipo de arquivo |
| `intitle:` | ✅ | Título |
| `inbody:` | ⚠ | Corpo |
| `-` / `" "` | ✅ | Exclusão / frase |
| **goggles** | ✅ | Reordenam/filtram resultados por regras do usuário |

> **Força:** *Goggles* permitem lentes de busca customizadas — útil para focar em um setor ou excluir fontes.

## 🔒 Startpage

Resultados do Google **sem rastreamento**. Suporta os operadores do Google, com atraso de índice e sem personalização.

| Operador | Status | Função |
|---|---|---|
| `site:` `filetype:` `intitle:` `inurl:` `intext:` | ✅ | Como no Google |
| `before:`/`after:` | ⚠ | Nem sempre repassados |

> **Uso:** bom para repetir um dork do Google sem viés de histórico/IP.

## 🅰 Yahoo

Hoje servido pelo índice do Bing; trate como Bing com menos recursos.

| Operador | Status |
|---|---|
| `site:` `filetype:` `intitle:` `inurl:` | ✅ |
| `link:` | ❌ |

## 🇰🇷 Naver

Buscador líder na Coreia do Sul; essencial para conteúdo coreano.

| Operador | Status |
|---|---|
| `site:` | ✅ |
| `" "` (frase) | ✅ |
| `-` | ✅ |

> Operadores avançados são escassos; o valor está no **índice coreano** exclusivo.

## 🧭 Mojeek

Índice 100% próprio (sem Google/Bing). Operadores básicos, bom para resultados não enviesados.

| Operador | Status |
|---|---|
| `site:` | ✅ |
| `-` / `" "` | ✅ |
| `title:` | ⚠ |

## 📊 Resumo comparativo

| Recurso | Google | Bing | DDG | Yandex | Brave |
|---|---|---|---|---|---|
| `site:` | ✅ | ✅ | ✅ | ✅ | ✅ |
| `filetype:`/`mime:` | ✅ | ✅ | ✅ | ✅ | ✅ |
| `inurl:` | ✅ | `instreamset:url:` | ✅ | ✅ | ⚠ |
| `intitle:`/`title:` | ✅ | ✅ | ✅ | ✅ | ✅ |
| `intext:`/`inbody:` | ✅ | ✅ | ✅ | ✅ | ⚠ |
| por IP | ❌ | `ip:` | ❌ | ❌ | ❌ |
| proximidade | `AROUND(n)` | `NEAR:n` | ❌ | `/n` | ❌ |

<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [← Google](01-google.md) · [Próximo: Infraestrutura →](03-buscadores-de-infraestrutura.md)

</div>
