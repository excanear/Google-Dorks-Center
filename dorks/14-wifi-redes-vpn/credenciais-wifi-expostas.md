<div align="center">

[🏠 Hub](../../README.md) · [📡 Wi-Fi, Redes & VPN](README.md) · [← Wi-Fi & Controladoras](wifi-e-controladoras.md) · [Próximo: Monitoramento de Rede →](monitoramento-de-rede.md)

# 🔑 Credenciais Wi-Fi Expostas

*SSID e chave pré-compartilhada (PSK) em planilhas, arquivos de config e exports — o par "rede + senha" vazado em documentos públicos.*

</div>

---

> [!CAUTION]
> Senha de Wi-Fi é credencial. Encontrar um arquivo com SSID+PSK é recon; conectar-se a uma rede sem autorização é acesso não autorizado. Trate como comprometido e reporte. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Arquivos de configuração Wi-Fi

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "wpa_supplicant.conf"` | Config wpa_supplicant (PSK em claro) | Google | 🔴 |
| `filetype:conf intext:"psk=" intext:"ssid="` | PSK+SSID em arquivo de config | Google | 🔴 |
| `intitle:"index of" "hostapd.conf"` | Config de AP hostapd | Google | 🔴 |
| `ext:xml intext:"<keyMaterial>"` | Perfil Wi-Fi exportado do Windows | Google | 🔴 |
| `intext:"netsh wlan" intext:"key=clear"` | Export `netsh wlan` com chave | Google | 🔴 |

### SSID + senha em documentos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:xlsx intext:"SSID" intext:"senha"` | Planilha de redes e senhas (BR) | Google | 🔴 |
| `filetype:xlsx intext:"SSID" intext:"password"` | Planilha de redes e senhas | Google | 🔴 |
| `filetype:pdf intext:"WiFi password" intext:"SSID"` | PDF com credencial de Wi-Fi | Google | 🟡 |
| `intitle:"index of" intext:"wifi-passwords"` | Arquivo de senhas de Wi-Fi | Google | 🔴 |
| `filetype:txt intext:"WPA2" intext:"passphrase"` | Passphrase WPA2 em texto | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo |
|---|---|---|
| `filetype:conf intext:"psk=" intext:"ssid="` | `ext:conf "psk=" "ssid="` | `filetype:conf psk= ssid=` |
| `intitle:"index of" "wpa_supplicant.conf"` | `intitle:"index of" "wpa_supplicant.conf"` | `"index of" wpa_supplicant.conf` |
| `filetype:xlsx intext:"SSID" intext:"senha"` | `ext:xlsx "SSID" "senha"` | `filetype:xlsx SSID senha` |
| `ext:xml intext:"<keyMaterial>"` | `ext:xml "<keyMaterial>"` | `filetype:xml keyMaterial` |

> **Código-fonte:** `wpa_supplicant.conf` e perfis Wi-Fi commitados aparecem no GitHub Code Search (`filename:wpa_supplicant.conf psk`). Segredos genéricos ficam na [02](../02-credenciais-e-segredos/README.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Config de Wi-Fi em diretório aberto — 5 variações

```text
intitle:"index of" "wireless.conf"
intitle:"index of" "wifi.conf"
intitle:"index of" "interfaces.d"
intitle:"index of" "NetworkManager"
intitle:"index of" "wpa.conf"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `wpa_supplicant.conf` e `hostapd.conf` guardam a PSK **em claro** — achado de alto valor e alto risco.
- O perfil Wi-Fi do Windows (`<keyMaterial>`) e o `netsh wlan ... key=clear` expõem a senha exata da rede.
- Planilhas de "SSID + senha" são comuns em TI de pequenas empresas/escolas — por isso cruzam com [19 · Setores & Nichos](../19-setores-e-nichos/README.md) quando o alvo é um setor.
- Este é o único lugar da categoria com **credencial**; segredos que não são de Wi-Fi vão para a [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [📡 Wi-Fi, Redes & VPN](README.md) · [← Wi-Fi & Controladoras](wifi-e-controladoras.md) · [Próximo: Monitoramento de Rede →](monitoramento-de-rede.md)

</div>
