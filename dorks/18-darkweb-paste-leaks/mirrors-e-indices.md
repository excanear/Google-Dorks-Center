<div align="center">

[🏠 Hub](../../README.md) · [🕵 Dark Web, Paste & Leaks](README.md) · [← Monitoramento de Paste](paste-monitoring.md) · [Próximo: Indicadores de Vazamento →](indicadores-de-vazamento.md)

# 🔗 Mirrors & Índices

*Índices e buscadores clearnet de serviços .onion (Ahmia, dark.fail) e gateways Tor2web — para pesquisa de ameaças e para verificar se o seu domínio é citado em espelhos.*

</div>

---

> [!CAUTION]
> Pesquisar índices clearnet é legítimo para threat-intel; acessar ou operar serviços ilícitos não é. Use sempre ancorado no seu alvo autorizado e **não** interaja com conteúdo criminoso. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Buscadores/índices clearnet de .onion

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:ahmia.fi "{seu_dominio}"` | Seu domínio citado em índice Ahmia | Google | 🟡 |
| `site:dark.fail "{termo}"` | Índice de serviços (verificação) | Google | 🟡 |
| `site:onion.live "{termo}"` | Status/índice de serviços onion | Google | 🟡 |
| `site:tor.taxi "{termo}"` | Diretório de serviços (pesquisa) | Google | 🟢 |

### Gateways Tor2web e espelhos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:onion.ly "{seu_dominio}"` | Seu domínio em gateway onion.ly | Google | 🟡 |
| `inurl:onion.ws "{seu_dominio}"` | Espelho Tor2web onion.ws | Google | 🟡 |
| `intitle:"Tor2web" "{termo}"` | Página de gateway Tor2web | Google | 🟢 |
| `site:onion.sh "{seu_dominio}"` | Espelho onion.sh citando seu domínio | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `site:ahmia.fi "{seu_dominio}"` | `site:ahmia.fi "{seu_dominio}"` | `site:ahmia.fi {seu_dominio}` |
| `inurl:onion.ly "{seu_dominio}"` | `instreamset:url:onion.ly "{seu_dominio}"` | `inurl:onion.ly {seu_dominio}` |
| `site:dark.fail "{termo}"` | `site:dark.fail "{termo}"` | `site:dark.fail {termo}` |

> **OPSEC:** pesquisa de dark web exige higiene (rede isolada, sem login pessoal). Veja o [manual de metodologia & OPSEC](../../docs/manual/06-metodologia-recon-e-opsec.md). Acesso direto à rede Tor foge do escopo de dorking.

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Menção do seu domínio em índice/espelho onion (ancorado em {seu_dominio}) — 5 variações

```text
site:dark.fail "{seu_dominio}"
site:onion.live "{seu_dominio}"
site:tor.taxi "{seu_dominio}"
site:onion.ws "{seu_dominio}"
site:onion.ly "{seu_dominio}"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Índices clearnet (Ahmia, dark.fail) existem para **pesquisa**; eles próprios filtram conteúdo de abuso. Use-os para verificar menções ao seu domínio.
- Gateways Tor2web (`onion.ly`, `onion.ws`) às vezes indexam no Google — útil para descobrir que um serviço cita seu domínio, sem entrar na Tor.
- `{termo}` deve ser do seu interesse legítimo de defesa (seu domínio, sua marca); não use para localizar mercados ilícitos.
- Nada aqui envolve **acessar** conteúdo criminoso — apenas detectar menções ao seu alvo em índices públicos.

<div align="center">

[🏠 Hub](../../README.md) · [🕵 Dark Web, Paste & Leaks](README.md) · [← Monitoramento de Paste](paste-monitoring.md) · [Próximo: Indicadores de Vazamento →](indicadores-de-vazamento.md)

</div>
