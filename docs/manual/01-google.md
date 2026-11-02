<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [← Construtor de Dorks](00-construtor-de-dorks.md) · [Próximo: Buscadores Web →](02-buscadores-web.md)

# 🔎 Manual — Google

*Todos os operadores de busca do Google, com status verificado, exemplo, pegadinha e equivalente em Bing/DuckDuckGo.*

</div>

---

> **Status verificado em 2026-11.** O Google muda operadores sem aviso e sem documentação oficial completa. Trate ⚠ e ❌ como "confirme antes de depender". Fontes no [rodapé](#-fontes).

## 📑 Nesta página

- [Legenda de status](#-legenda-de-status)
- [Operadores ativos](#-operadores-ativos)
- [Operadores instáveis](#-operadores-instáveis)
- [Operadores desativados](#-operadores-desativados)
- [Limites e pegadinhas](#-limites-e-pegadinhas)
- [Equivalências rápidas](#-equivalências-rápidas)
- [Fontes](#-fontes)

---

## 🏷 Legenda de status

| Símbolo | Significado |
|---|---|
| ✅ | Ativo e confiável |
| ⚠ | Funciona de forma inconsistente / não oficial |
| ❌ | Desativado — não use em dorks |

## ✅ Operadores ativos

| Operador | Status | Função | Exemplo |
|---|---|---|---|
| `site:` | ✅ | Restringe a um domínio ou TLD | `site:gov.br` |
| `filetype:` | ✅ | Tipo de arquivo (por MIME) | `filetype:pdf` |
| `ext:` | ✅ | Extensão (sinônimo prático de `filetype:`) | `ext:sql` |
| `intitle:` | ✅ | Termo no `<title>` | `intitle:"index of"` |
| `allintitle:` | ✅ | Todos os termos no título | `allintitle:admin login` |
| `inurl:` | ✅ | Termo na URL | `inurl:admin` |
| `allinurl:` | ✅ | Todos os termos na URL | `allinurl:login php` |
| `intext:` | ✅ | Termo no corpo da página | `intext:"senha"` |
| `allintext:` | ✅ | Todos os termos no corpo | `allintext:user password` |
| `"..."` | ✅ | Frase exata | `"strictly confidential"` |
| `-` | ✅ | Exclui termo | `error -changelog` |
| `OR` / `\|` | ✅ | OU lógico | `xls OR xlsx` |
| `( )` | ✅ | Agrupamento | `(sql OR dump)` |
| `*` | ✅ | Curinga de palavra inteira | `"user * admin"` |
| `before:` | ✅ | Antes da data (AAAA-MM-DD) | `before:2024-01-01` |
| `after:` | ✅ | Depois da data | `after:2023-01-01` |
| `AROUND(n)` | ⚠ | Proximidade entre termos | `admin AROUND(3) password` |

## ⚠ Operadores instáveis

| Operador | Status | Observação |
|---|---|---|
| `AROUND(n)` | ⚠ | Funciona, mas resultados variam entre sessões e regiões. Útil para proximidade, não confie no `n` exato. |
| `before:`/`after:` | ⚠→✅ | Introduzidos como "beta" em 2019; hoje confiáveis. Aceitam também só o ano (`after:2023`). |
| `daterange:` | ⚠ | Usa datas Julianas; quase sempre substituível por `before:`/`after:`. |
| `blogurl:` / `loc:` | ⚠ | Remanescentes de produtos antigos; comportamento irregular. |

## ❌ Operadores desativados

> **Não use em dorks.** Retornam resultados vazios ou enganosos. O validador do repositório rejeita dorks que os contenham.

| Operador | Situação |
|---|---|
| `cache:` | ❌ Removido (operador público aposentado). Use o [Wayback Machine](https://web.archive.org/) ou [Archive.today](https://archive.ph/). |
| `info:` | ❌ Descontinuado. |
| `link:` | ❌ Aposentado desde 2017. Use ferramentas de backlinks. |
| `related:` | ❌ Praticamente sem efeito hoje. |
| `inanchor:` / `allinanchor:` | ❌ Sem efeito confiável. |
| `phonebook:` | ❌ Removido há anos. |
| `+` (forçar termo) | ❌ Reatribuído ao Google+ em 2011; use `"aspas"` para forçar. |
| `~` (sinônimos) | ❌ Desativado; o Google já expande sinônimos sozinho. |
| `daterange:` (cru) | ⚠ Veja acima; prefira `before:`/`after:`. |

## 🧨 Limites e pegadinhas

- **32 palavras:** consultas acima de ~32 termos têm o excedente **silenciosamente ignorado**. Dorks longos precisam ser enxutos.
- **Stop words:** palavras muito comuns podem ser descartadas; force com aspas quando forem essenciais.
- **`filetype:` vs `ext:`:** equivalentes na prática; `filetype:` casa pelo tipo MIME, `ext:` pela extensão na URL. Para URLs com parâmetros (`?download=…`), nenhum dos dois enxerga o tipo real.
- **`site:` aceita curinga de subdomínio** (`site:*.alvo.com`), mas **não** curinga de caminho — use `inurl:` para caminho.
- **`intext:` não garante visibilidade:** o termo pode estar em HTML oculto ou metadados.
- **Personalização e região:** resultados variam por localização, idioma e histórico. Use janela anônima e, se possível, `gl=`/`hl=` via URL para padronizar.
- **Rate limit e CAPTCHA:** dorking intenso dispara o "unusual traffic". Veja [OPSEC](06-metodologia-recon-e-opsec.md).

## 🔁 Equivalências rápidas

| Google | Bing | DuckDuckGo |
|---|---|---|
| `filetype:pdf` | `filetype:pdf` / `ext:pdf` | `filetype:pdf` |
| `inurl:admin` | `instreamset:url:admin` | `inurl:admin` |
| `intitle:"x"` | `intitle:"x"` | `intitle:"x"` |
| `site:alvo.com` | `site:alvo.com` | `site:alvo.com` |
| `before:`/`after:` | *(sem equivalente direto)* | *(sem equivalente direto)* |

Matriz completa em [Tradução entre buscadores](05-traducao-entre-buscadores.md).

## 📚 Fontes

Status compilado em 2026-11 a partir de material público de referência de operadores de busca (cheat sheets mantidos pela comunidade e testes de operadores de 2026). Operadores marcados ⚠/❌ devem ser confirmados ao vivo antes de uso crítico, pois o Google não publica uma lista oficial completa.

<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [← Construtor de Dorks](00-construtor-de-dorks.md) · [Próximo: Buscadores Web →](02-buscadores-web.md)

</div>
