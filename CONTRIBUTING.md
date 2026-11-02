# Contribuindo com o Google-Dorks-Center

Obrigado por contribuir! Este é um repositório **somente de documentação** (Markdown). Não envie scripts ou código executável.

## Regras

1. **Um dork, uma categoria principal.** Verifique duplicatas antes de adicionar — o repositório mantém **zero duplicatas**.
2. **Formato curado:** tabela `` | `dork` | Finalidade | Buscadores | Risco | ``. O dork vai entre crases; escape `|` interno como `\|`.
3. **Expansão sistemática:** bloco ` ```text ` precedido de `> **Padrão:** …`, um dork por linha, pronto para copiar.
4. **Sem operadores desativados** (`cache:`, `info:`, `link:`, `+`, `~` no Google) dentro de dorks — eles só aparecem no manual, marcados ❌.
5. **Limite do Google:** no máximo 32 palavras por dork; aspas balanceadas.
6. **Ética:** nada que mire uma pessoa física específica, facilite stalking, doxxing, fraude ou acesso não autorizado. Marque o risco (🟢/🟡/🔴) e `⚠` quando houver dados pessoais.
7. **Fontes oficiais** para status de operadores; registre a data de verificação.

## Formato do PR

```text
Título:      [Categoria] Adiciona dorks de <assunto>
Descrição:   Finalidade · Buscadores · Risco · Fonte/raciocínio
```

## Checklist

- [ ] Sem duplicatas
- [ ] Formato de tabela/bloco correto
- [ ] Risco marcado
- [ ] Sem operadores mortos nos dorks
- [ ] Respeita o aviso legal e ético do [README](README.md#-aviso-de-uso-legal-e-ético)
