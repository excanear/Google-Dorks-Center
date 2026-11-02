<div align="center">

[🏠 Hub](../../README.md) · [🗺 Mapas & GEOINT](README.md) · [← Painéis de Mapa](paineis-de-mapa.md) · [Próximo: Mídia com Geolocalização →](imagens-com-geolocalizacao.md)

# 🚚 Rastreamento & Frota

*Plataformas de rastreamento GPS e dashboards de frota (Traccar, OpenGTS, GPSWOX) — localização, às vezes em tempo real, de veículos e pessoas.*

</div>

---

> [!CAUTION]
> Rastreamento revela localização de pessoas e bens em tempo real — dado sensível. Identificar um painel exposto é recon; observar ou seguir alvos não autorizados é vigilância ilícita. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Plataformas de rastreamento

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Traccar"` | Plataforma open source Traccar | Google | 🔴 |
| `inurl:/traccar inurl:login` | Login do Traccar | Google | 🔴 |
| `intitle:"OpenGTS"` | OpenGTS tracking | Google | 🔴 |
| `intitle:"GPSWOX"` | Plataforma GPSWOX | Google | 🔴 |
| `intitle:"GPS Tracking" inurl:login` | Painel genérico de rastreamento | Google | 🔴 |

### Dashboards de frota

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/fleet intitle:"dashboard"` | Dashboard de frota | Google | 🟡 |
| `intitle:"Fleet Management" inurl:login` | Gestão de frota | Google | 🟡 |
| `intext:"vehicle" intext:"latitude" inurl:/track` | Endpoint de rastreio de veículo | Google | 🔴 |
| `intitle:"Wialon"` | Plataforma de telemetria Wialon | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Shodan | FOFA |
|---|---|---|
| `intitle:"Traccar"` | `http.title:"Traccar"` | `title="Traccar"` |
| `intitle:"GPSWOX"` | `http.title:"GPSWOX"` | `title="GPSWOX"` |
| `intitle:"Wialon"` | `http.title:"Wialon"` | `title="Wialon"` |
| `intitle:"OpenGTS"` | `http.title:"OpenGTS"` | `title="OpenGTS"` |

> **Infraestrutura:** servidores de rastreamento costumam ouvir em portas de protocolo GPS (ex.: `5000-5200` no Traccar). Shodan por `http.title` e por porta localiza instâncias sem link indexado. Veja o [manual de infraestrutura](../../docs/manual/03-buscadores-de-infraestrutura.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Plataforma de rastreamento por título — 4 variações

```text
intitle:"GpsGate"
intitle:"Navixy"
intitle:"Ruptela"
intitle:"Flespi"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Esta é a subcategoria **mais sensível** do GEOINT: um painel aberto pode mostrar onde cada veículo (e motorista) está **agora**.
- Traccar/OpenGTS são auto-hospedados; muitos ficam expostos com credencial padrão — a existência já é o achado, não tente logar.
- "Fleet dashboard" às vezes é público de propósito (transporte público em tempo real) — confirme o contexto.
- Nunca use um painel para localizar ou seguir uma pessoa — isso é perseguição e crime, fora de qualquer escopo autorizado.

<div align="center">

[🏠 Hub](../../README.md) · [🗺 Mapas & GEOINT](README.md) · [← Painéis de Mapa](paineis-de-mapa.md) · [Próximo: Mídia com Geolocalização →](imagens-com-geolocalizacao.md)

</div>
