<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Arquivos de Configuração](arquivos-de-configuracao.md) · [Próximo: Diretórios Abertos →](diretorios-abertos.md)

# 🔐 Chaves & Certificados

*Chaves privadas, certificados e keystores expostos: `.pem`, `.key`, `.ppk`, `.pfx`, `.p12`, `.jks`, `id_rsa` e similares. Tokens de API ficam em [Credenciais & Segredos](../02-credenciais-e-segredos/README.md).*

</div>

---

> [!CAUTION]
> Uma chave privada exposta compromete servidores, TLS e assinaturas. Localizar é legítimo em escopo autorizado; **usar** a chave não é. Reporte imediatamente ao responsável pela rotação. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Chaves SSH

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "id_rsa"` | Chave privada SSH em diretório aberto | Google, Bing | 🔴 |
| `intitle:"index of" "id_ed25519"` | Chave privada SSH (Ed25519) | Google | 🔴 |
| `intitle:"index of" ".ssh" "authorized_keys"` | Pasta .ssh exposta | Google | 🔴 |
| `inurl:id_rsa -id_rsa.pub` | Chave privada (excluindo a pública) | Google | 🔴 |
| `ext:ppk "PuTTY-User-Key-File"` | Chaves privadas do PuTTY | Google | 🔴 |

### Chaves e certificados TLS

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `ext:key "BEGIN RSA PRIVATE KEY"` | Chaves privadas RSA em texto | Google | 🔴 |
| `ext:pem "BEGIN PRIVATE KEY"` | Chaves privadas PKCS#8 | Google | 🔴 |
| `ext:pem "BEGIN EC PRIVATE KEY"` | Chaves privadas de curva elíptica | Google | 🔴 |
| `intitle:"index of" ext:pfx` | Keystores PKCS#12 (.pfx) | Google | 🔴 |
| `intitle:"index of" ext:p12` | Keystores PKCS#12 (.p12) | Google | 🔴 |
| `intitle:"index of" "server.key"` | Chave TLS do servidor | Google | 🔴 |
| `intitle:"index of" "privkey.pem"` | Chave privada do Let's Encrypt | Google | 🔴 |

### Keystores de aplicação

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" ext:jks` | Java KeyStore exposto | Google | 🔴 |
| `intitle:"index of" ext:keystore` | Keystore Android/Java | Google | 🔴 |
| `intitle:"index of" "release.keystore"` | Keystore de assinatura Android | Google | 🔴 |
| `ext:pgp "BEGIN PGP PRIVATE KEY BLOCK"` | Chaves privadas PGP | Google | 🔴 |
| `ext:asc "BEGIN PGP PRIVATE KEY BLOCK"` | Chaves PGP em .asc | Google | 🔴 |

### Chaves de nuvem / serviço em arquivo

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `ext:json "private_key" "client_email" "googleapis"` | Service account do Google Cloud | Google | 🔴 |
| `ext:pem "BEGIN OPENSSH PRIVATE KEY"` | Chave OpenSSH em novo formato | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | Yandex |
|---|---|---|---|
| `intitle:"index of" "id_rsa"` | `intitle:"index of" "id_rsa"` | `intitle:"index of" id_rsa` | `title:"index of" "id_rsa"` |
| `ext:key "BEGIN RSA PRIVATE KEY"` | `ext:key "BEGIN RSA PRIVATE KEY"` | `filetype:key "BEGIN RSA PRIVATE KEY"` | `mime:key "BEGIN RSA PRIVATE KEY"` |
| `intitle:"index of" ext:pfx` | `intitle:"index of" ext:pfx` | `intitle:"index of" filetype:pfx` | `title:"index of" mime:pfx` |
| `ext:json "private_key" "client_email" "googleapis"` | `ext:json "private_key" "client_email"` | `filetype:json private_key client_email` | `mime:json "private_key" "client_email"` |

> Em código-fonte, chaves são melhor caçadas no [GitHub Code Search](../../docs/manual/04-buscadores-de-codigo-e-arquivos.md) com padrões como `"BEGIN RSA PRIVATE KEY"`.

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Chaves e certificados em diretórios abertos, por extensão — 8 variações

```text
intitle:"index of" ext:pem
intitle:"index of" ext:key
intitle:"index of" ext:ppk
intitle:"index of" ext:asc
intitle:"index of" ext:pgp
intitle:"index of" ext:crt
intitle:"index of" ext:cer
intitle:"index of" ext:der
```

> **Padrão:** Chaves/keystores por nome conhecido — 6 variações

```text
intitle:"index of" "id_dsa"
intitle:"index of" "id_ecdsa"
intitle:"index of" "private.key"
intitle:"index of" "client.key"
intitle:"index of" "debug.keystore"
intitle:"index of" "identity"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Chaves públicas** (`id_rsa.pub`, certificados `.crt`/`.cer`) não são sensíveis — a exclusão `-id_rsa.pub` evita confundir.
- Documentação e tutoriais mostram blocos `BEGIN ... PRIVATE KEY` como **exemplo**; o valor costuma ser `...` ou claramente falso. Verifique antes de reportar.
- Um achado real exige **resposta imediata**: rotação da chave/certificado e revogação, não só anotação.
- `.pfx`/`.p12`/`.jks` em geral são **protegidos por senha** — a exposição ainda é grave, mas o conteúdo não é imediatamente legível.

<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Arquivos de Configuração](arquivos-de-configuracao.md) · [Próximo: Diretórios Abertos →](diretorios-abertos.md)

</div>
