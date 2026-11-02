<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Logs](logs.md) · [Próximo: Chaves & Certificados →](chaves-e-certificados.md)

# ⚙ Arquivos de Configuração

*Arquivos de configuração expostos: `.ini`, `.conf`, `.yaml`, `.xml`, `.json` e configs de frameworks que revelam parâmetros de ambiente. Segredos em `.env` e chaves têm páginas próprias.*

</div>

---

> [!CAUTION]
> Configs revelam hosts internos, portas, versões e, por vezes, credenciais. Apenas localize e reporte. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético). Para `.env` e tokens, veja [Credenciais & Segredos](../02-credenciais-e-segredos/README.md).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Configuração de servidor web

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "httpd.conf"` | Configuração do Apache | Google | 🟡 |
| `intitle:"index of" "nginx.conf"` | Configuração do Nginx | Google | 🟡 |
| `intitle:"index of" ".htaccess"` | Regras do Apache (rewrite, auth) | Google | 🟡 |
| `intitle:"index of" "web.config"` | Configuração IIS/ASP.NET | Google | 🟡 |
| `ext:config "connectionStrings"` | web.config com strings de conexão | Google | 🔴 |

### Configuração de aplicação / framework

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `ext:yml inurl:config "database"` | YAML de config com bloco de banco | Google | 🟡 |
| `ext:yaml "secret_key_base"` | Config Rails com secret_key_base | Google | 🔴 |
| `ext:xml inurl:config "password"` | XML de configuração com senha | Google | 🔴 |
| `ext:json inurl:config "password"` | JSON de configuração com senha | Google | 🔴 |
| `ext:ini "[database]"` | Arquivos .ini com seção de banco | Google | 🟡 |
| `ext:conf "proxy_pass"` | Configs com upstreams internos | Google | 🟡 |
| `intitle:"index of" "application.properties"` | Config do Spring Boot | Google | 🔴 |
| `intitle:"index of" "settings.py"` | Config do Django | Google | 🔴 |
| `inurl:config.php.bak` | Config PHP em cópia de backup | Google | 🔴 |
| `intitle:"index of" "docker-compose.yml"` | Compose com serviços e variáveis | Google | 🟡 |
| `intitle:"index of" "Dockerfile"` | Dockerfile exposto | Google | 🟢 |

### Configuração de CI/CD e infraestrutura-como-código

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ".gitlab-ci.yml"` | Pipeline do GitLab CI | Google | 🟡 |
| `intitle:"index of" "Jenkinsfile"` | Pipeline do Jenkins | Google | 🟡 |
| `ext:tf "resource" "provider"` | Arquivos Terraform (infra exposta) | Google | 🟡 |
| `intitle:"index of" "terraform.tfstate"` | Estado do Terraform ⚠ segredos | Google | 🔴 |
| `ext:yaml "kind: Secret"` | Manifests Kubernetes de Secret | Google | 🔴 |
| `intitle:"index of" "ansible" "hosts"` | Inventário Ansible | Google | 🟡 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | Yandex |
|---|---|---|---|
| `intitle:"index of" "web.config"` | `intitle:"index of" "web.config"` | `intitle:"index of" web.config` | `title:"index of" "web.config"` |
| `ext:config "connectionStrings"` | `ext:config "connectionStrings"` | `filetype:config connectionStrings` | `mime:config "connectionStrings"` |
| `intitle:"index of" "application.properties"` | `intitle:"index of" application.properties` | `intitle:"index of" application.properties` | `title:"index of" application.properties` |
| `intitle:"index of" "terraform.tfstate"` | `intitle:"index of" terraform.tfstate` | `intitle:"index of" terraform.tfstate` | `title:"index of" terraform.tfstate` |
| `ext:yml inurl:config "database"` | `ext:yml inurl:config database` | `filetype:yml inurl:config database` | `mime:yml url:config database` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Configuração em diretórios abertos, por extensão — 11 variações

```text
intitle:"index of" ext:conf
intitle:"index of" ext:config
intitle:"index of" ext:cfg
intitle:"index of" ext:ini
intitle:"index of" ext:yml
intitle:"index of" ext:yaml
intitle:"index of" ext:xml
intitle:"index of" ext:json
intitle:"index of" ext:properties
intitle:"index of" ext:toml
intitle:"index of" ext:env
```

> **Padrão:** Arquivos de config por nome conhecido — 5 variações

```text
intitle:"index of" "config.php"
intitle:"index of" "wp-config.php"
intitle:"index of" "application.yml"
intitle:"index of" "config.json"
intitle:"index of" "appsettings.json"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Arquivos de exemplo** (`config.sample.yml`, `.env.example`) são intencionais e inofensivos — exclua com `-example -sample -dist -template`.
- **Documentação** de frameworks mostra trechos de config. Combine com `intitle:"index of"` ou `site:` para achar o arquivo real.
- `terraform.tfstate` e manifests `kind: Secret` são de **alto risco**: frequentemente contêm segredos em claro ou base64.
- `.htaccess`/`.htpasswd` podem ser servidos como texto quando o `AccessFileName` não está protegido — `.htpasswd` entra em [Credenciais & Segredos](../02-credenciais-e-segredos/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Logs](logs.md) · [Próximo: Chaves & Certificados →](chaves-e-certificados.md)

</div>
