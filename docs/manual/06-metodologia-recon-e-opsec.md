<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [← Tradução](05-traducao-entre-buscadores.md)

# 🧭 Metodologia, Recon & OPSEC

*Como transformar dorks num fluxo de recon disciplinado, legal e seguro — e como não se expor no processo.*

</div>

---

## 📑 Nesta página

- [O fluxo de recon com dorks](#-o-fluxo-de-recon-com-dorks)
- [Pivôs: de um selector a outro](#-pivôs-de-um-selector-a-outro)
- [Documentação de evidência](#-documentação-de-evidência)
- [OPSEC do investigador](#-opsec-do-investigador)
- [Legalidade e ética](#-legalidade-e-ética)

---

## 🔄 O fluxo de recon com dorks

1. **Escopo.** Defina por escrito o que é alvo autorizado (domínios, faixas, apps). Fora disso = não toque.
2. **Footprinting passivo.** `site:alvo.com` + enumeração de subdomínios via Yandex/`rhost:`, Wayback CDX e Common Crawl.
3. **Mapeamento de superfície.** Diretórios abertos, tecnologias (`intitle:`, `inurl:`), painéis de login.
4. **Busca de exposição.** Arquivos, configs, segredos, backups — categoria [01 · Exposição de Arquivos](../../dorks/01-exposicao-de-arquivos/README.md) e [02 · Credenciais & Segredos](../../dorks/02-credenciais-e-segredos/README.md).
5. **Correlação multi-fonte.** Confirme achados em buscador de infraestrutura (Shodan/Censys) e código (GitHub).
6. **Validação.** Elimine falsos positivos; confirme que o achado é real e atual.
7. **Relato.** Documente e reporte por canal de divulgação responsável.

```dork
site:alvo.com                      → volume e tecnologias
site:*.alvo.com -www               → subdomínios
site:alvo.com intitle:"index of"   → diretórios abertos
site:alvo.com filetype:pdf "uso interno"  → exposição documental
```

## 🔀 Pivôs: de um selector a outro

| Você tem | Pivote para | Como |
|---|---|---|
| Domínio | Subdomínios | Yandex `rhost:`, Wayback CDX, Common Crawl |
| Domínio | IPs/serviços | Shodan `ssl.cert.subject.cn:`, Censys cert |
| ID de Analytics/AdSense | Outros sites do mesmo dono | PublicWWW |
| E-mail/username | Repositórios/código | GitHub `user:`/busca de e-mail em commits |
| Favicon/título | Painéis idênticos | Shodan `http.title:`, favicon hash |
| URL histórica | Parâmetros ocultos | Wayback CDX `fl=original` |

## 🧾 Documentação de evidência

Um dork é parte da prova. Para cada achado, registre:

- **Consulta exata** e **buscador** usado;
- **Data e hora** (fuso) da coleta;
- **URL** e **captura** (screenshot + snapshot no [Wayback](https://web.archive.org/));
- **Hash** do snapshot quando a política exigir integridade;
- **Classificação de risco** e se contém dados pessoais (LGPD/GDPR).

> Preserve **sem baixar o corpo** de material sensível quando a política assim exigir: a URL e o snapshot bastam para comprovar a exposição.

## 🛡 OPSEC do investigador

- **Não interaja com o alvo** na fase passiva. Dork consulta o índice do buscador, não o site do alvo — mas clicar no resultado **toca** o alvo. Saiba a diferença.
- **Conta e IP descartáveis** para buscadores que exigem login (Shodan, GitHub): nunca a conta pessoal/corporativa.
- **Rate limit & CAPTCHA:** buscas automatizadas disparam bloqueios. Respeite os ToS; para volume, use as **APIs oficiais** com chave, não scraping.
- **Vazamento reverso:** o que você pesquisa revela seu interesse. Em casos sensíveis, use rede e navegador isolados.
- **Nada de automação contra o Google** sem API — é violação de ToS e queima seu IP.
- **Separe coleta de análise:** colete o mínimo necessário; analise offline.

## ⚖ Legalidade e ética

- **Coleta passiva ≠ acesso.** Encontrar um arquivo indexado é diferente de baixá-lo, acessá-lo ou usá-lo. O segundo pode configurar acesso não autorizado (**Lei 12.737/2012**, **CFAA**, **Computer Misuse Act**).
- **Dados pessoais** estão sob **LGPD**/**GDPR** mesmo quando "públicos". Minimize, não redistribua, e tenha base legal.
- **Dados vazados** (breaches, stealer logs) têm restrições severas de posse — consulte o jurídico.
- **Escopo contratado** é obrigatório em pentest. Sem autorização escrita, pare.
- **Divulgação responsável:** encontrou exposição grave? Notifique o responsável de forma privada e dê prazo de correção.

> Releia o [aviso legal completo do Hub](../../README.md#-aviso-de-uso-legal-e-ético). A inclusão de um dork aqui **não é** incentivo ao uso indevido.

<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [← Tradução](05-traducao-entre-buscadores.md)

</div>
