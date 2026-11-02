<div align="center">

[🏠 Hub](../../README.md) · [🕵 Dark Web, Paste & Leaks](README.md) · [← Indicadores de Vazamento](indicadores-de-vazamento.md)

# 🔐 Consciência de Combolist

*Detectar se contas do SEU domínio aparecem em combos/listas publicadas — sem baixar, hospedar ou usar listas de terceiros.*

</div>

---

> [!CAUTION]
> **Linha vermelha:** aqui você só verifica se o **seu** domínio aparece em uma lista, para proteger seus usuários. Baixar, armazenar, descriptografar ou usar combolists com dados de outras pessoas é ilícito e fora de escopo. Todo dork é ancorado em `{seu_dominio}`. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Detecção do seu domínio em combos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:pastebin.com "@{seu_dominio}:"` | Formato `email@dom:senha` do seu domínio | Google | 🔴 |
| `"{seu_dominio}" intext:"email:pass"` | Seu domínio em lista rotulada email:pass | Google | 🔴 |
| `"@{seu_dominio}" intext:"combolist"` | Combolist mencionando seu domínio | Google | 🔴 |
| `"{seu_dominio}" intext:"user:pass" site:pastebin.com` | Par user:pass do seu domínio | Google | 🔴 |

### Monitoramento de breach do seu domínio

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `"{seu_dominio}" intext:"database leak"` | Menção a vazamento de base do seu domínio | Google | 🔴 |
| `"{seu_dominio}" intext:"breached" intext:"records"` | Relato de breach citando você | Google | 🟡 |
| `site:breachforums "{seu_dominio}"` | Seu domínio citado em fórum de breach | Google | 🔴 |
| `"{seu_dominio}" intext:"fullz" OR intext:"dump"` | Oferta citando seu domínio | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `site:pastebin.com "@{seu_dominio}:"` | `site:pastebin.com "@{seu_dominio}:"` | `site:pastebin.com @{seu_dominio}:` |
| `"{seu_dominio}" intext:"email:pass"` | `"{seu_dominio}" "email:pass"` | `{seu_dominio} "email:pass"` |
| `"@{seu_dominio}" intext:"combolist"` | `"@{seu_dominio}" "combolist"` | `@{seu_dominio} combolist` |

> **Faça isto da forma segura e legal:** HaveIBeenPwned (busca por domínio), Google Password Checkup e serviços corporativos de monitoramento fazem essa detecção sem você tocar em dados de terceiros. Veja o [manual de metodologia & OPSEC](../../docs/manual/06-metodologia-recon-e-opsec.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Seu domínio em lista rotulada (ancorado em {seu_dominio}) — 4 variações

```text
"{seu_dominio}" intext:"user:pass"
"{seu_dominio}" intext:"login:password"
"{seu_dominio}" intext:"combolist"
"{seu_dominio}" intext:"credential dump"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Nunca** remova o `{seu_dominio}` desses dorks. Sem ele, viram busca por combolists alheias — o que esta categoria proíbe.
- Detectar exposição → forçar reset de senha dos usuários afetados do **seu** domínio e habilitar MFA. Esse é o único uso legítimo.
- Fóruns de breach mudam de endereço constantemente; o valor é o **sinal** de que seu domínio é citado, não o acesso ao fórum.
- Possuir uma combolist de terceiros, mesmo "só para checar", pode configurar tratamento ilícito de dados — use serviços que fazem a verificação por você.

<div align="center">

[🏠 Hub](../../README.md) · [🕵 Dark Web, Paste & Leaks](README.md) · [← Indicadores de Vazamento](indicadores-de-vazamento.md)

</div>
