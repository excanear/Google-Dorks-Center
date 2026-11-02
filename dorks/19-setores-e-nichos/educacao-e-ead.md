<div align="center">

[🏠 Hub](../../README.md) · [🏛 Setores Regulados & Nichos](README.md) · [← Saúde & Médico](saude-e-medico.md) · [Próximo: Governo Local & ONGs →](governo-local-e-ongs.md)

# 🎓 Educação & EAD

*Plataformas de ensino — Moodle, Canvas, Blackboard, Chamilo, Sakai — e portais acadêmicos expostos.*

</div>

---

> [!CAUTION]
> Plataformas educacionais guardam dados de alunos (muitas vezes menores de idade). Identificar o sistema é recon; acessar notas, cadastros ou turmas sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### LMS (Moodle / Canvas / Blackboard)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/login/index.php intext:"Moodle"` | Login do Moodle | Google | 🟡 |
| `inurl:/course/view.php?id= intext:"Moodle"` | Curso do Moodle indexado | Google | 🟢 |
| `inurl:/login/canvas intext:"Canvas"` | Login do Canvas LMS | Google | 🟡 |
| `site:instructure.com inurl:/login` | Instância Canvas hospedada | Google | 🟡 |
| `intitle:"Blackboard Learn"` | Plataforma Blackboard | Google | 🟡 |

### Outros LMS e portais acadêmicos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Chamilo" inurl:/index.php` | Plataforma Chamilo | Google | 🟡 |
| `intitle:"Sakai" inurl:/portal` | Plataforma Sakai | Google | 🟡 |
| `intitle:"Google Classroom" inurl:classroom.google.com` | Links de turma do Classroom | Google | 🟢 |
| `inurl:/student intitle:"portal" intext:"matrícula"` | Portal do aluno (BR) | Google | 🟡 |
| `intitle:"Open edX"` | Plataforma Open edX | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | Shodan |
|---|---|---|
| `inurl:/login/index.php intext:"Moodle"` | `instreamset:url:/login/index.php "Moodle"` | `http.html:"Moodle"` |
| `inurl:/login/canvas intext:"Canvas"` | `instreamset:url:/login/canvas "Canvas"` | `http.html:"instructure"` |
| `intitle:"Blackboard Learn"` | `intitle:"Blackboard Learn"` | `http.title:"Blackboard Learn"` |
| `intitle:"Chamilo"` | `intitle:"Chamilo"` | `http.title:"Chamilo"` |

> **Infraestrutura:** Moodle e Canvas têm favicons e cabeçalhos característicos; no FOFA, `app="Moodle"`. Produção acadêmica e `*.edu.br` ficam em [10 · Brasil](../10-brasil/educacao-e-saude.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Plataforma de ensino por título — 6 variações

```text
intitle:"Moodle"
intitle:"Canvas"
intitle:"Chamilo"
intitle:"Sakai"
intitle:"Totara"
intitle:"Brightspace"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Moodle/Canvas são frequentemente **públicos por missão** (universidades) — o achado relevante é a instância **desatualizada** (CVE) ou um portal interno exposto.
- A versão do Moodle aparece em `/lib/upgrade.txt` e no changelog — pivô para [09 · Vulnerabilidades](../09-vulnerabilidades/README.md).
- Dados de alunos podem envolver **menores** — sensibilidade elevada; pare no nível do sistema.
- `*.edu.br` e portais acadêmicos brasileiros específicos ficam em [10 · Brasil](../10-brasil/educacao-e-saude.md) para não duplicar.

<div align="center">

[🏠 Hub](../../README.md) · [🏛 Setores Regulados & Nichos](README.md) · [← Saúde & Médico](saude-e-medico.md) · [Próximo: Governo Local & ONGs →](governo-local-e-ongs.md)

</div>
