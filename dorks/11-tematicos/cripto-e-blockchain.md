<div align="center">

[🏠 Hub](../../README.md) · [🎨 Temáticos](README.md) · [← Jornalismo & Investigação](jornalismo-e-investigacao.md) · [Próximo: Acadêmico & Pesquisa →](academico-e-pesquisa.md)

# 🪙 Cripto & Blockchain

*Artefatos públicos de cripto — carteiras expostas, configs de exchange/nó, contratos e seed phrases vazadas.*

</div>

---

> [!CAUTION]
> Seed phrases e chaves privadas de cripto dão controle **irreversível** dos fundos. Encontrá-las **não autoriza** mover nada — isso é furto. Reporte ao dono. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Carteiras e seeds expostas

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:txt "mnemonic" "seed phrase"` | Seed phrases em texto | Google | 🔴 |
| `ext:json "privateKey" "address" intext:"0x"` | Keystore de carteira Ethereum | Google | 🔴 |
| `filetype:json "wallet" "encrypted"` | Arquivos de carteira | Google | 🔴 |
| `intitle:"index of" "wallet.dat"` | Carteira Bitcoin Core | Google | 🔴 |
| `ext:txt "12 word" OR "24 word" "recovery phrase"` | Frases de recuperação | Google | 🔴 |

### Nós, exchanges e configs

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"index of" "geth" "keystore"` | Keystore de nó Geth | Google | 🔴 |
| `ext:conf "rpcpassword" intext:"bitcoin"` | bitcoin.conf com RPC | Google | 🔴 |
| `inurl:8332 intext:"jsonrpc"` | RPC de nó Bitcoin exposto | Google | 🔴 |
| `inurl:8545 intext:"eth_" -github` | RPC JSON de nó Ethereum | Google | 🔴 |
| `filetype:env "WALLET_PRIVATE_KEY"` | Chave de carteira em `.env` | Google | 🔴 |

### Contratos e dados on-chain

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:etherscan.io "{contrato}"` | Contratos verificados (Etherscan) | Google | 🟢 |
| `ext:sol "pragma solidity"` | Código-fonte Solidity | Google | 🟢 |
| `site:github.com "pragma solidity" "{termo}"` | Contratos em repositórios | Google | 🟢 |

---

## 🔁 Traduções entre buscadores

| Google | GitHub Code Search | FOFA |
|---|---|---|
| `ext:json "privateKey" intext:"0x"` | `/\"privateKey\":\s*\"0x[0-9a-f]{64}\"/` | — |
| `inurl:8545 intext:"eth_"` | — | `port="8545" && body="eth_"` |
| `ext:sol "pragma solidity"` | `path:*.sol "pragma solidity"` | — |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Artefato de carteira em diretório aberto — 11 variações

```text
intitle:"index of" "keystore"
intitle:"index of" "UTC--"
intitle:"index of" "mnemonic.txt"
intitle:"index of" "seed.txt"
intitle:"index of" "privatekey.txt"
intitle:"index of" "electrum.dat"
intitle:"index of" "wallet.json"
intitle:"index of" "keystore.json"
intitle:"index of" "bitcoin.conf"
intitle:"index of" "metamask-vault"
intitle:"index of" "ledger-backup"
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Seed phrases/chaves privadas são 🔴 máximo: **jamais** use uma que encontrar — reporte para o dono mover os fundos.
- Código Solidity e endereços on-chain são **públicos por natureza** (🟢) — o risco está em chaves, não em contratos.
- Nós RPC expostos (8332/8545) permitem ações; apenas confirme a exposição.
- Chaves de carteira em arquivos também se cruzam com [02 · Credenciais & Segredos](../02-credenciais-e-segredos/README.md).

<div align="center">

[🏠 Hub](../../README.md) · [🎨 Temáticos](README.md) · [← Jornalismo & Investigação](jornalismo-e-investigacao.md) · [Próximo: Acadêmico & Pesquisa →](academico-e-pesquisa.md)

</div>
