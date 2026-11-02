<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Documentos Office & PDF](documentos-office-e-pdf.md) · [Próximo: Backups & Compactados →](backups-e-arquivos-compactados.md)

# 📊 Planilhas & CSV

*Planilhas e exportações tabulares: listas de usuários, inventários, contatos, senhas, financeiro, cadastros e exportações de sistemas.*

</div>

---

> [!CAUTION]
> Planilhas são a **principal fonte de vazamento acidental de dados pessoais**. Não baixe, não copie, não redistribua. Reporte ao controlador (LGPD art. 48) quando atuar profissionalmente. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Credenciais e acessos em planilhas

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:xlsx "username" "password"` | Planilhas com colunas de usuário e senha | Google, Bing | 🔴 |
| `filetype:xls "usuário" "senha"` | Planilhas legadas com usuário/senha (PT) | Google | 🔴 |
| `filetype:csv "email" "password"` | CSVs com e-mail e senha | Google, Bing | 🔴 |
| `filetype:xlsx "login" "senha" "sistema"` | Controle de acessos de sistemas | Google | 🔴 |
| `filetype:xlsx "password" "server" "IP"` | Inventário de servidores com senha | Google, Bing | 🔴 |
| `filetype:xlsx "admin" "password" "router"` | Planilhas com credenciais de rede | Google, Bing | 🔴 |
| `filetype:ods "senha" "acesso"` | Planilhas LibreOffice com acessos | Google | 🔴 |
| `filetype:csv "api_key"` | Exportações CSV contendo chaves de API | Google, Bing | 🔴 |
| `filetype:xlsx "wifi" "password" "SSID"` | Planilhas de redes Wi-Fi e senhas | Google, Bing | 🔴 |

### Dados pessoais (⚠ LGPD/GDPR)

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:xlsx "CPF" "RG" "data de nascimento"` | Cadastros com documentos pessoais ⚠ | Google | 🔴 |
| `filetype:csv "CPF" "nome" "telefone"` | Exportações de cadastro ⚠ | Google | 🔴 |
| `filetype:xls "nome completo" "CPF" "endereço"` | Listas cadastrais completas ⚠ | Google | 🔴 |
| `filetype:xlsx "lista de alunos" "matrícula"` | Listas de alunos ⚠ | Google | 🔴 |
| `filetype:xlsx "lista de presença" "CPF"` | Listas de presença com CPF ⚠ | Google | 🔴 |
| `filetype:xlsx "social security number" "DOB"` | Planilhas com SSN (EUA) ⚠ | Google, Bing | 🔴 |
| `filetype:csv "first_name" "last_name" "phone" "email"` | Exportações de CRM ⚠ | Google, Bing | 🔴 |
| `filetype:xlsx "patient" "diagnosis"` | Dados de saúde ⚠ categoria especial | Google, Bing | 🔴 |
| `filetype:xlsx "paciente" "prontuário"` | Dados de saúde (PT) ⚠ | Google | 🔴 |
| `filetype:xlsx "salário" "cargo" "admissão"` | Planilhas de RH ⚠ | Google | 🔴 |
| `filetype:xlsx "employee" "salary" "hire date"` | Planilhas de RH (EN) ⚠ | Google, Bing | 🔴 |
| `filetype:csv "IBAN" "BIC"` | Dados bancários (EU) ⚠ | Google, Bing | 🔴 |
| `filetype:xlsx "agência" "conta corrente" "CPF"` | Dados bancários (BR) ⚠ | Google | 🔴 |

### Inventário de TI e infraestrutura

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:xlsx "hostname" "IP address" "OS"` | Inventário de ativos de TI | Google, Bing | 🔴 |
| `filetype:xlsx "VLAN" "switch" "porta"` | Mapeamento de rede física | Google | 🔴 |
| `filetype:xlsx "asset tag" "serial number"` | Inventário patrimonial | Google, Bing | 🟡 |
| `filetype:csv "hostname" "mac address"` | Exportações de DHCP/NAC | Google, Bing | 🔴 |
| `filetype:xlsx "firewall rules" "source" "destination"` | Matrizes de regras de firewall | Google, Bing | 🔴 |
| `filetype:xlsx "license key" "software"` | Controle de licenças com chaves | Google, Bing | 🔴 |
| `filetype:xlsx "extension" "ramal" "telefone"` | Listas de ramais (engenharia social) | Google | 🟡 |
| `filetype:csv "domain" "registrar" "expiry"` | Portfólios de domínios | Google, Bing | 🟢 |

### Financeiro e comercial

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:xlsx "budget" "forecast" "confidential"` | Orçamentos e previsões confidenciais | Google, Bing | 🔴 |
| `filetype:xlsx "orçamento" "previsto" "realizado"` | Controle orçamentário | Google | 🟡 |
| `filetype:xlsx "invoice" "amount due"` | Faturas a receber | Google, Bing | 🟡 |
| `filetype:xlsx "fluxo de caixa"` | Fluxo de caixa | Google | 🟡 |
| `filetype:xlsx "customer list" "revenue"` | Carteira de clientes com receita | Google, Bing | 🔴 |
| `filetype:csv "order_id" "customer_email"` | Exportações de e-commerce ⚠ | Google, Bing | 🔴 |
| `filetype:xlsx "commission" "sales rep"` | Comissões de vendas | Google, Bing | 🟡 |
| `filetype:xlsx "tabela de preços" "custo"` | Tabelas de preço com custo interno | Google | 🟡 |

### Exportações de sistemas e Google Sheets

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `site:docs.google.com/spreadsheets "password"` | Google Sheets públicos citando senha | Google | 🔴 |
| `site:docs.google.com/spreadsheets "CPF"` | Google Sheets públicos com CPF ⚠ | Google | 🔴 |
| `site:docs.google.com/spreadsheets "confidential"` | Google Sheets confidenciais publicados | Google | 🔴 |
| `site:docs.google.com/spreadsheets "api key"` | Sheets com chaves de API | Google | 🔴 |
| `site:onedrive.live.com "xlsx" "senha"` | Planilhas compartilhadas no OneDrive | Google | 🔴 |
| `site:1drv.ms "xlsx"` | Links curtos do OneDrive para planilhas | Google | 🟡 |
| `site:dropbox.com/s "xlsx"` | Planilhas em links públicos do Dropbox | Google | 🟡 |
| `site:airtable.com/shr` | Views públicas compartilhadas do Airtable | Google | 🟡 |
| `filetype:csv "export" "users" "created_at"` | Exportações de tabela de usuários | Google, Bing | 🔴 |
| `filetype:csv inurl:export` | CSVs gerados por endpoints de exportação | Google | 🟡 |
| `filetype:xlsx inurl:report "generated"` | Relatórios gerados automaticamente | Google | 🟡 |
| `intitle:"index of" "xlsx" "backup"` | Diretórios abertos com planilhas de backup | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Bing | DuckDuckGo | Yandex |
|---|---|---|---|
| `filetype:xlsx "username" "password"` | `filetype:xlsx "username" "password"` | `filetype:xlsx username password` | `mime:xlsx "username" "password"` |
| `filetype:csv "email" "password"` | `filetype:csv "email" "password"` | `filetype:csv email password` | `mime:csv "email" "password"` |
| `filetype:xlsx "hostname" "IP address" "OS"` | `filetype:xlsx hostname "IP address"` | `filetype:xlsx hostname "IP address"` | `mime:xlsx hostname "IP address"` |
| `filetype:xlsx "firewall rules" "source" "destination"` | `filetype:xlsx "firewall rules"` | `filetype:xlsx "firewall rules"` | `mime:xlsx "firewall rules"` |
| `site:docs.google.com/spreadsheets "password"` | `site:docs.google.com "spreadsheets" password` | `site:docs.google.com spreadsheets password` | `site:docs.google.com password` |
| `filetype:xlsx "budget" "forecast" "confidential"` | `filetype:xlsx budget forecast confidential` | `filetype:xlsx budget forecast confidential` | `mime:xlsx budget forecast confidential` |
| `filetype:csv "first_name" "last_name" "phone" "email"` | `filetype:csv first_name last_name email` | `filetype:csv first_name last_name email` | `mime:csv first_name last_name email` |
| `filetype:xlsx "license key" "software"` | `filetype:xlsx "license key"` | `filetype:xlsx "license key"` | `mime:xlsx "license key"` |
| `site:airtable.com/shr` | `site:airtable.com inurl:shr` | `site:airtable.com shr` | `site:airtable.com inurl:shr` |
| `intitle:"index of" "xlsx" "backup"` | `intitle:"index of" xlsx backup` | `intitle:"index of" xlsx backup` | `title:"index of" xlsx backup` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Planilhas confidenciais, por extensão × termo de sigilo — 72 variações

```text
filetype:xls intext:"confidencial"
filetype:xls intext:"confidential"
filetype:xls intext:"uso interno"
filetype:xls intext:"internal use only"
filetype:xls intext:"não divulgar"
filetype:xls intext:"do not distribute"
filetype:xls intext:"strictly confidential"
filetype:xls intext:"proprietary"
filetype:xls intext:"restrito"
filetype:xls intext:"restricted"
filetype:xls intext:"sigiloso"
filetype:xls intext:"private and confidential"
filetype:xlsx intext:"confidencial"
filetype:xlsx intext:"confidential"
filetype:xlsx intext:"uso interno"
filetype:xlsx intext:"internal use only"
filetype:xlsx intext:"não divulgar"
filetype:xlsx intext:"do not distribute"
filetype:xlsx intext:"strictly confidential"
filetype:xlsx intext:"proprietary"
filetype:xlsx intext:"restrito"
filetype:xlsx intext:"restricted"
filetype:xlsx intext:"sigiloso"
filetype:xlsx intext:"private and confidential"
filetype:xlsm intext:"confidencial"
filetype:xlsm intext:"confidential"
filetype:xlsm intext:"uso interno"
filetype:xlsm intext:"internal use only"
filetype:xlsm intext:"não divulgar"
filetype:xlsm intext:"do not distribute"
filetype:xlsm intext:"strictly confidential"
filetype:xlsm intext:"proprietary"
filetype:xlsm intext:"restrito"
filetype:xlsm intext:"restricted"
filetype:xlsm intext:"sigiloso"
filetype:xlsm intext:"private and confidential"
filetype:csv intext:"confidencial"
filetype:csv intext:"confidential"
filetype:csv intext:"uso interno"
filetype:csv intext:"internal use only"
filetype:csv intext:"não divulgar"
filetype:csv intext:"do not distribute"
filetype:csv intext:"strictly confidential"
filetype:csv intext:"proprietary"
filetype:csv intext:"restrito"
filetype:csv intext:"restricted"
filetype:csv intext:"sigiloso"
filetype:csv intext:"private and confidential"
filetype:ods intext:"confidencial"
filetype:ods intext:"confidential"
filetype:ods intext:"uso interno"
filetype:ods intext:"internal use only"
filetype:ods intext:"não divulgar"
filetype:ods intext:"do not distribute"
filetype:ods intext:"strictly confidential"
filetype:ods intext:"proprietary"
filetype:ods intext:"restrito"
filetype:ods intext:"restricted"
filetype:ods intext:"sigiloso"
filetype:ods intext:"private and confidential"
filetype:tsv intext:"confidencial"
filetype:tsv intext:"confidential"
filetype:tsv intext:"uso interno"
filetype:tsv intext:"internal use only"
filetype:tsv intext:"não divulgar"
filetype:tsv intext:"do not distribute"
filetype:tsv intext:"strictly confidential"
filetype:tsv intext:"proprietary"
filetype:tsv intext:"restrito"
filetype:tsv intext:"restricted"
filetype:tsv intext:"sigiloso"
filetype:tsv intext:"private and confidential"
```

> **Padrão:** Planilhas em diretórios abertos, por extensão — 6 variações

```text
intitle:"index of" ext:xls
intitle:"index of" ext:xlsx
intitle:"index of" ext:xlsm
intitle:"index of" ext:csv
intitle:"index of" ext:ods
intitle:"index of" ext:tsv
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Templates de planilha** (modelos de controle de senhas, cursos de Excel) são o maior ruído. Exclua com `-template -modelo -tutorial -curso -exemplo`.
- **Google Sheets** só aparecem quando publicados ou com "qualquer pessoa com o link" e indexados. A ausência no Google **não** significa que o link não seja público.
- **CSV** raramente tem título — prefira termos de **cabeçalho de coluna** (`"first_name"`, `"created_at"`), que aparecem literalmente no conteúdo indexado.
- Planilhas `.xls` legadas costumam ter **abas ocultas**; o snippet do buscador mostra só a primeira.

<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [← Documentos Office & PDF](documentos-office-e-pdf.md) · [Próximo: Backups & Compactados →](backups-e-arquivos-compactados.md)

</div>
