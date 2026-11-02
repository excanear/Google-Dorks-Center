<div align="center">

[🏠 Hub](../../README.md) · [🎨 Temáticos](README.md)

# 🎮 Games & Servidores

*Servidores de jogos e seus painéis — configs do Minecraft/FiveM/Rust, painéis Pterodactyl/Multicraft e arquivos de servidor em diretórios abertos.*

</div>

---

> [!CAUTION]
> Config de servidor de jogo pode conter senha de RCON e tokens. Identificar é recon; conectar-se ou administrar um servidor de terceiros sem autorização não é. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Configs de servidor em diretório aberto

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "server.properties"` | Config de servidor Minecraft | Google | 🟡 |
| `intitle:"index of" "ops.json"` | Operadores (admins) do Minecraft | Google | 🔴 |
| `intitle:"index of" "whitelist.json" "minecraft"` | Whitelist do servidor | Google | 🟡 |
| `intitle:"index of" "server.cfg" intext:"fivem"` | Config do FiveM (GTA RP) | Google | 🔴 |
| `intitle:"index of" "permissions.yml"` | Permissões de plugin (Bukkit/Spigot) | Google | 🟡 |

### Painéis de hospedagem de jogos

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Pterodactyl" inurl:/auth/login` | Painel Pterodactyl | Google | 🟡 |
| `intitle:"Multicraft" inurl:/login` | Painel Multicraft | Google | 🟡 |
| `intitle:"Pufferpanel"` | Painel PufferPanel | Google | 🟡 |
| `intitle:"TCAdmin"` | Painel TCAdmin de game hosting | Google | 🟡 |
| `inurl:/panel intext:"game server" inurl:/login` | Painel genérico de game server | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | Shodan | FOFA |
|---|---|---|
| `intitle:"index of" "server.properties"` | `http.html:"server.properties"` | `body="server.properties"` |
| `intitle:"Pterodactyl" inurl:/auth/login` | `http.title:"Pterodactyl"` | `title="Pterodactyl"` |
| `intitle:"Multicraft"` | `http.title:"Multicraft"` | `title="Multicraft"` |

> **Infraestrutura:** servidores de jogo têm portas características (Minecraft `25565`, FiveM `30120`, SA-MP `7777`); o Shodan por porta + produto localiza instâncias. Veja o [manual de infraestrutura](../../docs/manual/03-buscadores-de-infraestrutura.md).

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Config de servidor de jogo em diretório aberto — 7 variações

```text
intitle:"index of" "whitelist.json"
intitle:"index of" "banned-players.json"
intitle:"index of" "bukkit.yml"
intitle:"index of" "spigot.yml"
intitle:"index of" "paper.yml"
intitle:"index of" "eula.txt"
intitle:"index of" "server.cfg"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- `ops.json` (Minecraft) e `server.cfg` (FiveM) podem conter nomes de admin e, no FiveM, tokens de licença/esteiras — a senha de RCON vira achado para [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md).
- Painéis Pterodactyl/Multicraft expostos permitem gerenciar servidores inteiros — a existência é o achado; não tente logar.
- Muita config de jogo é de servidores de hobby; o interessante é a que vaza **credencial** ou expõe painel administrativo.
- Dispositivos/consoles físicos fogem do escopo; aqui é o **servidor de jogo** (software).

<div align="center">

[🏠 Hub](../../README.md) · [🎨 Temáticos](README.md)

</div>
