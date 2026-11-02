<div align="center">

[🏠 Hub](../../README.md)

# 🕵 Dark Web, Paste & Leaks

*Threat-intelligence **defensivo**: monitorar se dados do SEU domínio (ou de um alvo que você está autorizado a proteger) apareceram em paste sites, índices e vazamentos — para reagir, não para coletar dados de terceiros.*

</div>

---

> [!CAUTION]
> **Esta categoria é exclusivamente defensiva.** Todos os dorks usam o placeholder `{seu_dominio}` e servem para descobrir a **exposição do seu próprio domínio** ou de um alvo que você tem autorização formal para proteger.
>
> - ❌ **Não** use nada aqui para baixar, compilar ou redistribuir dados pessoais, credenciais ou documentos de terceiros.
> - ⚖ Possuir ou usar bases de dados vazadas de outras pessoas tem restrições legais severas (LGPD, GDPR, Lei 12.737/2012). Detectar que **você** vazou é legítimo; aproveitar o vazamento de **outros** não é.
> - ✅ Ao encontrar exposição, o fluxo correto é **conter e reportar** (rotacionar segredos, acionar o responsável, pedir remoção).
>
> Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📂 Subcategorias

| # | Subcategoria | Conteúdo | Risco |
|---|---|---|---|
| 1 | [📋 Monitoramento de Paste](paste-monitoring.md) | Menções ao seu domínio em pastebin/paste.ee/rentry | 🟡 |
| 2 | [🔗 Mirrors & Índices](mirrors-e-indices.md) | Índices clearnet de .onion (pesquisa), Tor2web | 🟡 |
| 3 | [🚨 Indicadores de Vazamento](indicadores-de-vazamento.md) | Sinais de que o seu domínio/segredo vazou | 🔴 |
| 4 | [🔐 Consciência de Combolist](combolist-awareness.md) | Detectar seu domínio em combos — sem baixar listas | 🔴 |

## 🧭 Como usar esta categoria

1. Substitua `{seu_dominio}` pelo domínio que você administra ou está **autorizado** a proteger.
2. Rode o monitoramento periodicamente (é vigilância contínua, não busca única).
3. Ao achar exposição: **registre, contenha e reporte**. Nunca baixe a base de terceiros que acompanha o achado.

## 🚧 Fronteira desta categoria

- **Segredos do seu domínio em repositórios** → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md) para o detalhe técnico; aqui, só o **sinal de exposição**.
- **Paste/leak sites genéricos sem alvo** não entram: todo dork aqui é **ancorado no seu domínio**.
- **Recon de pessoas** → [08 · Pessoas & SOCMINT](../08-pessoas-e-socmint/README.md), que também proíbe mirar indivíduos.

## 🔗 Categorias relacionadas

- Segredos do seu domínio → [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md)
- Recon da sua organização → [07 · Recon de Organização](../07-recon-de-organizacao/README.md)
- Serviços de monitoramento (HaveIBeenPwned etc.) → [manual de metodologia](../../docs/manual/06-metodologia-recon-e-opsec.md)

<div align="center">

[🏠 Hub](../../README.md)

</div>
