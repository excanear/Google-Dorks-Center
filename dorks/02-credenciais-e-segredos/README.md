<div align="center">

[🏠 Hub](../../README.md)

# 🔑 Credenciais & Segredos

*Segredos textuais indexados: variáveis de ambiente, tokens de API, senhas em configuração e código, autenticação básica e chaves embutidas no frontend.*

</div>

---

> [!CAUTION]
> Esta é a categoria de **maior risco** do repositório. Um segredo encontrado deve ser **reportado para rotação imediata**, nunca usado. Acessar sistemas com uma credencial achada — mesmo exposta publicamente — é acesso não autorizado (Lei 12.737/2012, CFAA, Computer Misuse Act). Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📂 Subcategorias

| # | Subcategoria | Conteúdo | Risco |
|---|---|---|---|
| 1 | [🌱 Variáveis de Ambiente (.env)](variaveis-de-ambiente-env.md) | `.env`, `.env.local`, `.env.production` | 🔴 |
| 2 | [🎟 Tokens de API](tokens-de-api.md) | Chaves por provedor (AWS, GCP, Stripe, Slack…) | 🔴 |
| 3 | [🔏 Senhas em Configuração e Código](senhas-em-configuracao-e-codigo.md) | `DB_PASSWORD`, connection strings, `password=` | 🔴 |
| 4 | [🚪 .htpasswd & Auth Básica](htpasswd-e-auth-basica.md) | `.htpasswd`, `.netrc`, `.pgpass`, `auth.json` | 🔴 |
| 5 | [🖥 Secrets em Frontend & JS](secrets-em-frontend-e-js.md) | Chaves em bundles, `firebaseConfig`, `apiKey:` | 🔴 |

## 🧭 Como usar esta categoria

1. Restrinja ao **escopo autorizado** com `site:alvo.com`.
2. Em código-fonte, o [GitHub Code Search](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md) costuma render mais que buscadores web — veja a coluna GitHub nas traduções.
3. Encontrou um segredo real? **Pare, não teste**, e acione divulgação responsável. Veja [Metodologia & OPSEC](../../docs/manual/06-metodologia-recon-e-opsec.md).

## 🔗 Categorias relacionadas

- Chaves privadas, certificados, keystores e service-account JSON → [01 · Chaves & Certificados](../01-exposicao-de-arquivos/chaves-e-certificados.md)
- Configs sem segredo (parâmetros, hosts) → [01 · Arquivos de Configuração](../01-exposicao-de-arquivos/arquivos-de-configuracao.md)
- Logs vazando tokens → [01 · Logs](../01-exposicao-de-arquivos/logs.md)

<div align="center">

[🏠 Hub](../../README.md)

</div>
