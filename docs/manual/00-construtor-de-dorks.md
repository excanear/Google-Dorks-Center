<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [Próximo: Google →](01-google.md)

# 🧱 Construtor de Dorks

*Como montar um dork do zero para qualquer alvo: anatomia, lógica, precedência e um método passo a passo.*

</div>

---

Um **dork** é uma consulta de busca que usa **operadores avançados** para filtrar resultados por local, tipo de arquivo, texto, URL ou título. Dorking é a arte de transformar uma pergunta de investigação ("que documentos internos deste domínio estão indexados?") em uma consulta precisa.

## 📑 Nesta página

- [Anatomia de um dork](#-anatomia-de-um-dork)
- [Operadores booleanos e precedência](#-operadores-booleanos-e-precedência)
- [As 7 regras de ouro](#-as-7-regras-de-ouro)
- [Método passo a passo](#-método-passo-a-passo)
- [10 exemplos construídos do zero](#-10-exemplos-construídos-do-zero)

---

## 🔬 Anatomia de um dork

```dork
site:exemplo.com filetype:pdf intext:"confidencial" -template
```

| Parte | Papel |
|---|---|
| `site:exemplo.com` | **Operador de escopo** — restringe ao domínio |
| `filetype:pdf` | **Operador de tipo** — só PDFs |
| `intext:"confidencial"` | **Operador de conteúdo** — frase exata no corpo |
| `-template` | **Exclusão** — remove ruído |

Um dork combina três decisões: **onde** procurar (`site:`, `inurl:`), **o que** é o alvo (`filetype:`, `intitle:`, `intext:`) e **o que descartar** (`-termo`).

## 🔗 Operadores booleanos e precedência

| Operador | Efeito | Exemplo |
|---|---|---|
| espaço | AND implícito | `admin login` = admin **E** login |
| `OR` ou `\|` | OU lógico (maiúsculas) | `filetype:xls OR filetype:xlsx` |
| `-` | NÃO (exclui) | `erro -changelog` |
| `"..."` | frase exata | `"index of"` |
| `( )` | agrupamento | `(sql OR dump) site:alvo.com` |
| `*` | curinga de palavra | `"senha * padrão"` |

**Precedência:** o `OR` tem precedência sobre o AND implícito; na dúvida, **sempre agrupe com parênteses**:

```dork
site:alvo.com (filetype:sql OR filetype:dump) intext:"INSERT INTO"
```

Sem os parênteses, o buscador pode interpretar o escopo de forma inesperada.

## 📐 As 7 regras de ouro

1. **Uma pergunta por dork.** Se precisa de "E também", provavelmente são dois dorks.
2. **Comece largo, depois estreite.** Rode `site:alvo.com`, veja o volume, e vá adicionando filtros.
3. **Aspas mudam tudo.** `index of` ≠ `"index of"`. A segunda exige a frase literal.
4. **Maiúsculas só importam nos operadores.** `OR`/`AND` precisam ser maiúsculos; o resto do texto é *case-insensitive*.
5. **Menos de 32 palavras** (Google). Além disso, as palavras extras são ignoradas sem aviso.
6. **Exclua o ruído previsível** (`-template -sample -example -tutorial`).
7. **Valide o operador.** Operadores mortos (`cache:`, `info:`, `link:`) retornam resultados enganosos — veja o [Manual do Google](01-google.md).

## 🧭 Método passo a passo

1. **Defina o alvo e o selector.** Domínio? Tecnologia? Tipo de documento? Esse é o núcleo do dork.
2. **Escolha o operador de escopo.** `site:` para um alvo; sem escopo para pesquisa ampla.
3. **Escolha o operador de alvo.** Arquivo → `filetype:`; URL → `inurl:`; título → `intitle:`; texto → `intext:`.
4. **Adicione assinaturas de conteúdo.** Frases que *só* aparecem no que você procura (`"phpMyAdmin SQL Dump"`, `"BEGIN RSA PRIVATE KEY"`).
5. **Remova o ruído.** Rode, veja os falsos positivos, adicione exclusões.
6. **Traduza para outros buscadores** se precisar de cobertura — veja [Tradução entre buscadores](05-traducao-entre-buscadores.md).
7. **Documente.** Dork, data, buscador e resultado — a consulta é parte da evidência.

## 🧩 10 exemplos construídos do zero

**1. Documentos internos de um domínio**
> Pergunta: "que PDFs marcados como internos este domínio expõe?"
```dork
site:alvo.com filetype:pdf intext:"uso interno"
```

**2. Painel de login de um alvo**
> Começa largo (`site:`), estreita por URL típica de login.
```dork
site:alvo.com (inurl:login OR inurl:admin OR intitle:"login")
```

**3. Subdomínios de desenvolvimento**
```dork
site:*.alvo.com (inurl:dev OR inurl:staging OR inurl:test) -www
```

**4. Planilha com cabeçalhos de exportação de CRM**
> Mira termos que são literalmente nomes de coluna.
```dork
filetype:csv "first_name" "last_name" "email" site:alvo.com
```

**5. Diretório aberto do alvo**
```dork
site:alvo.com intitle:"index of" "parent directory"
```

**6. Tecnologia específica (ex.: Grafana)**
```dork
intitle:"Grafana" inurl:/login intext:"Welcome to Grafana"
```

**7. Erros que vazam caminho/stack**
```dork
site:alvo.com (intext:"Fatal error" OR intext:"Stack trace") -changelog
```

**8. Documento perdido via arquivo histórico**
> O operador `cache:` morreu; use o Wayback.
```dork
site:web.archive.org alvo.com filetype:pdf
```

**9. Presença em serviços de paste**
```dork
(site:pastebin.com OR site:ghostbin.com) "alvo.com"
```

**10. Combinação OR com agrupamento e escopo**
```dork
site:alvo.com (filetype:sql OR filetype:bak OR filetype:old) -sample
```

<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [Próximo: Google →](01-google.md)

</div>
