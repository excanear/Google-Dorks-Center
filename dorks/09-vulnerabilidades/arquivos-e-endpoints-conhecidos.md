<div align="center">

[🏠 Hub](../../README.md) · [🐛 Vulnerabilidades](README.md) · [← Mensagens de Erro](mensagens-de-erro-reveladoras.md) · [Próximo: Exposições por Classe →](exposicoes-por-classe.md)

# 📁 Arquivos & Endpoints Conhecidos

*Arquivos e endpoints que, quando expostos, indicam fragilidade — repositórios de versão, metadados de SO, instaladores e rotas de teste.*

</div>

---

> [!CAUTION]
> Localizar é passivo; baixar/reconstruir conteúdo ou acionar instaladores sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Repositórios de versão e metadados

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/.git/config intext:"[core]"` | Config de repositório Git exposto | Google | 🔴 |
| `inurl:/.git/HEAD` | HEAD de repositório Git | Google | 🔴 |
| `inurl:/.svn/entries` | Metadados SVN | Google | 🔴 |
| `inurl:/.DS_Store` | Metadados de diretório macOS | Google | 🟡 |
| `inurl:/.hg/ intext:"revlog"` | Repositório Mercurial | Google | 🟡 |
| `inurl:/WEB-INF/web.xml` | Descritor Java fora do protegido | Google | 🔴 |

### Instaladores e setup

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/install.php intitle:"installation"` | Instalador acessível | Google | 🔴 |
| `inurl:/setup.php intitle:"setup"` | Setup acessível | Google | 🔴 |
| `inurl:/wp-admin/install.php` | Instalador do WordPress | Google | 🔴 |
| `intitle:"Setup Wizard" inurl:install` | Assistente de instalação | Google | 🔴 |
| `inurl:/phpinfo.php` | phpinfo deixado no servidor | Google | 🔴 |

### Endpoints de teste e exemplo

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/test.php intext:"test"` | Páginas de teste | Google | 🟡 |
| `inurl:/examples/ intitle:"index of"` | Diretórios de exemplo | Google | 🟡 |
| `inurl:/phpunit/ inurl:eval-stdin.php` | Endpoint PHPUnit sensível | Google | 🔴 |
| `inurl:/console intitle:"Interactive"` | Console interativo exposto | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Shodan/FOFA |
|---|---|---|
| `inurl:/.git/config` | `instreamset:url:/.git/config` | FOFA: `body="[core]" && body="repositoryformatversion"` |
| `inurl:/.DS_Store` | `instreamset:url:/.DS_Store` | FOFA: `body=".DS_Store"` |
| `inurl:/phpinfo.php` | `instreamset:url:/phpinfo.php` | Shodan: `http.html:"phpinfo()"` |
| `inurl:/install.php` | `instreamset:url:/install.php` | — |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Arquivo/endpoint conhecido por URL — 14 variações

```text
inurl:/.git/config
inurl:/.git/index
inurl:/.svn/wc.db
inurl:/.hg/store
inurl:/.bzr/
inurl:/install.php
inurl:/setup.php
inurl:/test.php
inurl:/info.php
inurl:/.vscode/settings.json
inurl:/.idea/workspace.xml
inurl:/composer.json
inurl:/package.json
inurl:/.editorconfig
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `.git`/`.svn` expostos permitem **reconstruir o código** — 🔴; o dork localiza, a reconstrução/exploração exige escopo e fica fora daqui.
- Instaladores acessíveis podem permitir **takeover** da aplicação; apenas confirme a presença e reporte.
- `.git` em *directory listing* também em [01 · Diretórios Abertos](../01-exposicao-de-arquivos/diretorios-abertos.md); aqui o foco é o **endpoint específico** (`/.git/config`, `/.git/HEAD`).
- Muitos `test.php`/`examples` são inofensivos — trate como hipótese.

<div align="center">

[🏠 Hub](../../README.md) · [🐛 Vulnerabilidades](README.md) · [← Mensagens de Erro](mensagens-de-erro-reveladoras.md) · [Próximo: Exposições por Classe →](exposicoes-por-classe.md)

</div>
