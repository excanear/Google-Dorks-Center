<div align="center">

[🏠 Hub](../../README.md) · [🔌 APIs & Webhooks](README.md) · [← Webhooks](webhooks.md)

# 📦 Postman & Coleções

*Coleções, workspaces públicos e arquivos de environment do Postman/Insomnia — frequentemente carregando tokens e URLs internas.*

</div>

---

> [!CAUTION]
> Environments do Postman costumam guardar tokens e senhas em variáveis. Mapear coleções públicas é recon legítimo; usar credenciais encontradas nelas não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Coleções e workspaces públicos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:postman.com inurl:/collection` | Coleções públicas no Postman | Google | 🟡 |
| `site:documenter.getpostman.com` | Docs de coleção publicadas | Google | 🟡 |
| `site:www.postman.com "{empresa}"` | Workspace público de uma org | Google | 🟡 |
| `site:postman.com inurl:/workspace` | Workspaces públicos | Google | 🟡 |
| `inurl:/run.pstmn.io` | Botão "Run in Postman" com coleção | Google | 🟢 |

### Arquivos de coleção / environment exportados

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" intext:"postman_collection.json"` | Coleção exportada em diretório aberto | Google | 🟡 |
| `ext:json intext:"postman_collection"` | Arquivo de coleção Postman | Google | 🟡 |
| `ext:json intext:"_postman_variable_scope"` | Environment do Postman exportado | Google | 🔴 |
| `intext:"insomnia_export" ext:json` | Export do Insomnia | Google | 🔴 |
| `intitle:"index of" "environment.json" intext:"postman"` | Environment em pasta aberta | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `site:postman.com inurl:/collection` | `site:postman.com instreamset:url:/collection` | `site:postman.com inurl:collection` |
| `site:documenter.getpostman.com` | `site:documenter.getpostman.com` | `site:documenter.getpostman.com` |
| `ext:json intext:"postman_collection"` | `ext:json "postman_collection"` | `filetype:json postman_collection` |
| `ext:json intext:"_postman_variable_scope"` | `ext:json "_postman_variable_scope"` | `filetype:json _postman_variable_scope` |

> **Código-fonte:** coleções commitadas em repositórios aparecem no GitHub Code Search (`filename:*.postman_collection.json`) — veja o [manual de código](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Coleção/workspace por host (placeholder {empresa}) — 3 variações

```text
site:postman.com "{empresa}"
site:documenter.getpostman.com "{empresa}"
site:getpostman.com "{empresa}"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `{empresa}` é placeholder — preencha com o alvo autorizado da investigação.
- O achado de maior valor é o **environment** (`_postman_variable_scope`, `environment.json`): é ali que ficam tokens, `baseUrl` interno e senhas de teste.
- Coleções públicas no `postman.com` são, em geral, intencionais (devrel). O risco mora em environments exportados por engano para diretórios abertos.
- Insomnia exporta um JSON equivalente; o mesmo cuidado se aplica.

<div align="center">

[🏠 Hub](../../README.md) · [🔌 APIs & Webhooks](README.md) · [← Webhooks](webhooks.md)

</div>
