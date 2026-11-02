<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [← Buscadores Web](02-buscadores-web.md) · [Próximo: Código & Arquivos →](04-buscadores-de-codigo-e-arquivos.md)

# 🛰 Manual — Buscadores de Infraestrutura

*Shodan, Censys, FOFA, ZoomEye, Netlas, Criminal IP, Hunter.how, BinaryEdge, Onyphe e LeakIX: buscam **dispositivos e serviços** expostos, não páginas web. Verificado em 2026-11.*

</div>

---

> [!CAUTION]
> Esses buscadores revelam serviços expostos na Internet. **Consultar o índice é passivo**; conectar, autenticar ou explorar o serviço exige autorização (Lei 12.737/2012, CFAA). Veja [OPSEC & legalidade](06-metodologia-recon-e-opsec.md).

## 📑 Nesta página

- [Shodan](#-shodan)
- [Censys](#-censys)
- [FOFA](#-fofa)
- [ZoomEye](#-zoomeye)
- [Netlas](#-netlas)
- [Criminal IP](#-criminal-ip)
- [Hunter.how](#-hunterhow)
- [BinaryEdge](#-binaryedge)
- [Onyphe](#-onyphe)
- [LeakIX](#-leakix)
- [Equivalências](#-equivalências)

---

## 🔦 Shodan

O buscador de dispositivos mais conhecido. Sintaxe `filtro:valor`, AND implícito por espaço.

| Filtro | Função | Exemplo |
|---|---|---|
| `port:` | Porta aberta | `port:3389` |
| `product:` | Produto/serviço | `product:nginx` |
| `http.title:` | Título da página HTTP | `http.title:"Index of /"` |
| `http.html:` | Conteúdo HTML | `http.html:"dashboard"` |
| `ssl.cert.subject.cn:` | CN do certificado | `ssl.cert.subject.cn:alvo.com` |
| `org:` | Organização | `org:"Example Ltd"` |
| `net:` | Faixa CIDR | `net:203.0.113.0/24` |
| `country:` / `city:` | Geografia | `country:BR` |
| `os:` | Sistema operacional | `os:"Windows"` |
| `vuln:` | CVE associado (plano pago) | `vuln:CVE-2021-44228` |
| `hostname:` | Hostname | `hostname:.alvo.com` |

```dork
http.title:"Index of /" country:BR port:80,443
```

> **Plano:** gratuito limita filtros (sem `vuln:`, sem exportação). Operadores combinam com espaço (AND); use `-filtro:` para excluir.

## 🛰 Censys

Migrou para a **Platform** com a linguagem **CenQL**. Campos hierárquicos sob `host.*` e `web.*`.

| Sintaxe | Função | Exemplo |
|---|---|---|
| `campo:valor` | Substring *case-insensitive* | `host.services.port:22` |
| `campo = "valor"` | Igualdade exata | `host.location.country = "Brazil"` |
| `>`, `<`, `>=`, `<=` | Faixas numéricas | `host.services.port > 1024` |
| `and` / `or` / `not` | Booleanos | `port:443 and not port:80` |
| `( )` aninhado | Mesma condição no mesmo serviço | `host.services:(port=22 and protocol="SSH")` |
| `host.services.software.product:` | Produto | `host.services.software.product:"GitLab"` |
| `host.services.tls.certificates.leaf_data.subject.common_name:` | CN TLS | — |

```dork
host.services.software.product:"GitLab" and host.location.country="Brazil"
```

> **Pegadinha:** sem aninhar com `( )`, duas condições de serviço podem casar em serviços **diferentes** do mesmo host. O **Query Converter** oficial migra campos legados (`services.*` → `host.services.*`). A API/SDK `censys` legada foi aposentada em favor de `censys-platform`.

## 🎯 FOFA

Buscador chinês potente; sintaxe `chave="valor"` com operadores lógicos simbólicos.

| Sintaxe | Função | Exemplo |
|---|---|---|
| `domain=` | Domínio | `domain="alvo.com"` |
| `host=` | Host | `host=".alvo.com"` |
| `title=` | Título HTTP | `title="Grafana"` |
| `body=` | Corpo HTML | `body="pleskLogin"` |
| `port=` | Porta | `port="6379"` |
| `protocol=` | Protocolo | `protocol="redis"` |
| `cert=` | Certificado | `cert="alvo.com"` |
| `&&` `\|\|` `!=` | AND / OR / diferente | `title="admin" && country="BR"` |

```dork
title="Grafana" && body="Welcome to Grafana" && country="BR"
```

## 🔭 ZoomEye

Buscador chinês de dispositivos e web. Sintaxe `chave:"valor"`.

| Filtro | Função |
|---|---|
| `app:` | Aplicação/produto |
| `ver:` | Versão |
| `port:` | Porta |
| `title:` | Título |
| `hostname:` | Hostname |
| `country:` / `city:` | Geografia |
| `ssl:` | Certificado SSL |

```dork
app:"Apache httpd" +version:"2.4.49" +country:"BR"
```

## 🌐 Netlas

Busca de ativos com sintaxe estilo Elasticsearch (campos com ponto).

| Campo | Função |
|---|---|
| `host:` | Host |
| `port:` | Porta |
| `http.title:` | Título |
| `certificate.subject.common_name:` | CN TLS |
| `A:` / `AND` / `OR` / `NOT` | Booleanos |

```dork
http.title:"index of" AND port:443
```

## 🚨 Criminal IP

Buscador de ativos com foco em risco/reputação.

| Filtro | Função |
|---|---|
| `product:` | Produto |
| `port:` | Porta |
| `title:` | Título |
| `ssl_subject:` | Certificado |
| `country:` | País |
| `tag:` | Etiquetas de risco (`tag: "malicious"`) |

## 🏹 Hunter.how

Buscador de ativos (não confundir com Hunter.io de e-mail). Sintaxe `chave="valor"`.

| Campo | Função |
|---|---|
| `domain=` | Domínio |
| `web.title=` | Título |
| `port=` | Porta |
| `protocol=` | Protocolo |
| `ip.country=` | País |

## 📡 BinaryEdge

Dados de varredura por `chave:"valor"`.

| Campo | Função |
|---|---|
| `ip:` | IP |
| `port:` | Porta |
| `country:` | País |
| `product:` | Produto |
| `http.title:` | Título |

## 🧅 Onyphe

Inteligência de ciberdefesa; categorias por "APIs" (`datascan`, `threatlist`).

| Campo | Função |
|---|---|
| `category:` | Tipo de dado (`datascan`) |
| `port:` | Porta |
| `product:` | Produto |
| `country:` | País |
| `organization:` | Organização |

## 💧 LeakIX

Foca em serviços **expostos e mal configurados** e indicadores de vazamento.

| Campo | Função |
|---|---|
| `+plugin:` | Tipo de exposição detectada |
| `+country:` | País |
| `+port:` | Porta |
| `+protocol:` | Protocolo |

> [!CAUTION]
> LeakIX pode listar bancos abertos e dados vazados. Posse/uso de dados vazados tem restrições legais severas — apenas confirme a exposição e reporte.

## 🔁 Equivalências

| Intenção | Shodan | Censys | FOFA |
|---|---|---|---|
| Porta aberta | `port:22` | `host.services.port:22` | `port="22"` |
| Título HTTP | `http.title:"x"` | `web.endpoints.http.title:"x"` | `title="x"` |
| Certificado p/ domínio | `ssl.cert.subject.cn:alvo.com` | `...common_name:alvo.com` | `cert="alvo.com"` |
| País | `country:BR` | `host.location.country="Brazil"` | `country="BR"` |
| Produto | `product:nginx` | `host.services.software.product:"nginx"` | `app="nginx"` |

<div align="center">

[🏠 Hub](../../README.md) · [📘 Manual](README.md) · [← Buscadores Web](02-buscadores-web.md) · [Próximo: Código & Arquivos →](04-buscadores-de-codigo-e-arquivos.md)

</div>
