<div align="center">

[🏠 Hub](../../README.md) · [🐛 Vulnerabilidades](README.md) · [← Parâmetros Suspeitos](parametros-suspeitos.md) · [Próximo: Arquivos & Endpoints Conhecidos →](arquivos-e-endpoints-conhecidos.md)

# ⚠ Mensagens de Erro Reveladoras

*Mensagens de erro indexadas que sinalizam fragilidade — SQL, inclusão de arquivo, path. São sinais de recon, não exploração.*

</div>

---

> [!CAUTION]
> Uma mensagem de erro indexada é passiva; **provocar erros** no alvo é interação e exige autorização. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Erros de SQL (SQLi-prone)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"You have an error in your SQL syntax"` | Erro de sintaxe MySQL exposto | Google | 🟡 |
| `intext:"Warning: mysql_fetch_array()"` | Erro MySQL clássico | Google | 🟡 |
| `intext:"Unclosed quotation mark after the character string"` | Erro SQL Server | Google | 🟡 |
| `intext:"supplied argument is not a valid MySQL"` | Resultado MySQL inválido | Google | 🟡 |
| `intext:"ORA-00933: SQL command not properly ended"` | Erro Oracle | Google | 🟡 |
| `intext:"PostgreSQL query failed"` | Erro PostgreSQL | Google | 🟡 |

### Erros de inclusão / path (LFI-prone)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"Warning: include("` | Falha de include PHP | Google | 🟡 |
| `intext:"failed to open stream: No such file"` | Caminho inválido em include | Google | 🟡 |
| `intext:"include_path" "Warning"` | Erro de include_path | Google | 🟡 |
| `intext:"java.io.FileNotFoundException" inurl:/` | Arquivo não encontrado em Java | Google | 🟡 |

### Outros erros reveladores

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intext:"Microsoft OLE DB Provider for ODBC Drivers error"` | Erro clássico ASP/ODBC | Google | 🟡 |
| `intext:"Fatal error: Uncaught" "Stack trace"` | Exceção PHP não tratada | Google | 🟡 |
| `intext:"Notice: Undefined index" inurl:php` | Aviso que revela variáveis | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Shodan/FOFA |
|---|---|---|
| `intext:"You have an error in your SQL syntax"` | `inbody:"You have an error in your SQL syntax"` | FOFA: `body="error in your SQL syntax"` |
| `intext:"Warning: include("` | `inbody:"Warning: include("` | FOFA: `body="Warning: include("` |
| `intext:"Microsoft OLE DB Provider for ODBC"` | `inbody:"Microsoft OLE DB Provider for ODBC"` | FOFA: `body="Microsoft OLE DB Provider"` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->
<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Fóruns e tutoriais** (Stack Overflow) citam essas mensagens como exemplo — filtre com `-site:stackoverflow.com` ou foque no `site:` alvo.
- Erro indexado indica que **já houve** falha visível, não que ainda exista — confirme o estado atual dentro do escopo.
- Erros de aplicação/debug mais amplos (Whoops, Werkzeug) estão em [03 · Erros & Debug](../03-infraestrutura-web/erros-e-debug.md); aqui o foco é o **sinal de classe de vulnerabilidade**.

<div align="center">

[🏠 Hub](../../README.md) · [🐛 Vulnerabilidades](README.md) · [← Parâmetros Suspeitos](parametros-suspeitos.md) · [Próximo: Arquivos & Endpoints Conhecidos →](arquivos-e-endpoints-conhecidos.md)

</div>
