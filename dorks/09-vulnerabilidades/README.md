<div align="center">

[🏠 Hub](../../README.md)

# 🐛 Vulnerabilidades

*Dorks que **identificam sinais** de fragilidade — parâmetros suspeitos, mensagens de erro, endpoints e arquivos conhecidos. Recon de superfície, não exploração.*

</div>

---

> [!CAUTION]
> ## ⚖ Identificar ≠ explorar
>
> Os dorks aqui encontram **indícios** de que um alvo pode ter uma classe de vulnerabilidade. **Não há payloads nem passos de ataque** — isso está fora do escopo deste repositório.
>
> - Testar ou explorar uma vulnerabilidade sem **autorização escrita** (pentest com escopo, programa de bug bounty) é crime (Lei 12.737/2012, CFAA, Computer Misuse Act).
> - Encontrar um sinal é ponto de partida para **divulgação responsável**, não para ataque.
> - Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📂 Subcategorias

| # | Subcategoria | Conteúdo | Risco |
|---|---|---|---|
| 1 | [🔣 Parâmetros Suspeitos](parametros-suspeitos.md) | Parâmetros de URL associados a classes de bug | 🟡 |
| 2 | [⚠ Mensagens de Erro Reveladoras](mensagens-de-erro-reveladoras.md) | Erros de SQL/LFI/path que sinalizam fragilidade | 🟡 |
| 3 | [📁 Arquivos & Endpoints Conhecidos](arquivos-e-endpoints-conhecidos.md) | `.git`, `.DS_Store`, instaladores, endpoints de teste | 🔴 |
| 4 | [🧯 Exposições por Classe](exposicoes-por-classe.md) | Open redirect, SSRF-prone, upload, debug | 🟡 |

## 🧭 Como usar esta categoria

1. Os dorks dão o **sinal**; a confirmação exige análise manual dentro do escopo autorizado.
2. Muitos sinais são **falsos positivos** — parâmetro suspeito ≠ vulnerável. Trate como hipótese.
3. A exploração em si fica fora daqui: encontrou algo? Acione divulgação responsável.

## 🔗 Categorias relacionadas

- `.git`/`.svn` em listagem → [01 · Diretórios Abertos](../01-exposicao-de-arquivos/diretorios-abertos.md)
- Erros/stack traces de aplicação → [03 · Erros & Debug](../03-infraestrutura-web/erros-e-debug.md)
- Bancos expostos / erros SQL de serviço → [04 · Bancos de Dados](../04-tecnologias/bancos-de-dados.md)

<div align="center">

[🏠 Hub](../../README.md)

</div>
