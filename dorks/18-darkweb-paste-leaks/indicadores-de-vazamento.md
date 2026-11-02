<div align="center">

[🏠 Hub](../../README.md) · [🕵 Dark Web, Paste & Leaks](README.md) · [← Mirrors & Índices](mirrors-e-indices.md) · [Próximo: Consciência de Combolist →](combolist-awareness.md)

# 🚨 Indicadores de Vazamento

*Sinais, em superfícies públicas, de que dados ou segredos do SEU domínio vazaram — gists, boards, buckets e repositórios citando `{seu_dominio}`.*

</div>

---

> [!CAUTION]
> O objetivo é detectar a **sua própria** exposição para contê-la. Encontrar um segredo seu exposto obriga à rotação imediata; encontrar dados de terceiros não autoriza usá-los. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Segredos do seu domínio em superfícies de colaboração

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:gist.github.com "{seu_dominio}" intext:"password"` | Gist citando seu domínio + senha | Google | 🔴 |
| `site:trello.com "{seu_dominio}"` | Board público do Trello citando você | Google | 🔴 |
| `site:gitlab.com "{seu_dominio}" intext:"token"` | Snippet/repo GitLab com token seu | Google | 🔴 |
| `"{seu_dominio}" intext:"BEGIN RSA PRIVATE KEY"` | Chave privada do seu domínio exposta | Google | 🔴 |

### Seu domínio em buckets e índices

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:s3.amazonaws.com "{seu_dominio}"` | Objetos S3 citando seu domínio | Google | 🔴 |
| `site:blob.core.windows.net "{seu_dominio}"` | Blobs Azure com seu domínio | Google | 🔴 |
| `intitle:"index of" "{seu_dominio}" intext:"backup"` | Backup aberto citando seu domínio | Google | 🔴 |
| `"{seu_dominio}" ext:sql intext:"INSERT INTO"` | Dump SQL mencionando seu domínio | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `site:gist.github.com "{seu_dominio}" intext:"password"` | `site:gist.github.com "{seu_dominio}" "password"` | `site:gist.github.com {seu_dominio} password` |
| `site:trello.com "{seu_dominio}"` | `site:trello.com "{seu_dominio}"` | `site:trello.com {seu_dominio}` |
| `site:s3.amazonaws.com "{seu_dominio}"` | `site:s3.amazonaws.com "{seu_dominio}"` | `site:s3.amazonaws.com {seu_dominio}` |

> **Detalhe técnico do segredo** (formato de token, prefixo de chave) está em [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md); buckets em [05 · Cloud & Storage](../05-cloud-e-storage/README.md). Aqui, o foco é o **sinal de que é o SEU dado**.

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Seu domínio em superfície de colaboração/bucket (ancorado em {seu_dominio}) — 5 variações

```text
site:gist.github.com "{seu_dominio}"
site:gitlab.com "{seu_dominio}"
site:bitbucket.org "{seu_dominio}"
site:codepen.io "{seu_dominio}"
site:jsfiddle.net "{seu_dominio}"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Ancorar em `{seu_dominio}` é o que mantém isto defensivo: você procura a **sua** exposição, não a de outros.
- Trello/GitLab/Gist públicos são fontes recorrentes de vazamento acidental — monitore-os com regularidade.
- Ao confirmar segredo exposto: rotacione, invalide tokens, acione o provedor para remoção e registre o incidente.
- Dump SQL citando seu domínio é indicador forte de breach — acione resposta a incidentes; **não** baixe a base inteira de terceiros contida nele.

<div align="center">

[🏠 Hub](../../README.md) · [🕵 Dark Web, Paste & Leaks](README.md) · [← Mirrors & Índices](mirrors-e-indices.md) · [Próximo: Consciência de Combolist →](combolist-awareness.md)

</div>
