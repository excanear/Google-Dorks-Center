<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [Próximo: Planilhas & CSV →](planilhas-e-csv.md)

# 📄 Documentos Office & PDF

*Documentos internos, confidenciais ou operacionais indexados por engano: relatórios, contratos, manuais, atas, apresentações e políticas.*

</div>

---

> [!CAUTION]
> Encontrar um documento indexado **não autoriza** baixá-lo, redistribuí-lo ou usá-lo. Em investigações e pentests, documente a URL, notifique o responsável (divulgação responsável) e respeite LGPD/GDPR. Veja o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

> Substitua `site:exemplo.com` pelo escopo **autorizado**. Sem `site:`, o dork faz busca ampla (pesquisa/estatística).

### Marcações de confidencialidade

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:pdf "confidencial" "uso interno"` | PDFs marcados como confidenciais (PT) | Google, Bing | 🔴 |
| `filetype:pdf "confidential" "internal use only"` | PDFs marcados como confidenciais (EN) | Google, Bing | 🔴 |
| `filetype:docx "strictly confidential"` | Documentos Word com marcação forte de sigilo | Google, Bing | 🔴 |
| `filetype:pdf "not for distribution" "proprietary"` | Material proprietário não-distribuível | Google, Bing | 🔴 |
| `filetype:pdf "for official use only"` | Documentos FOUO (governo/defesa EUA) | Google, Bing | 🔴 |
| `filetype:pdf "restrito" "não divulgar"` | Documentos restritos em português | Google | 🔴 |
| `filetype:pdf "draft" "do not distribute"` | Rascunhos que não deveriam circular | Google, Bing | 🟡 |
| `filetype:pptx "confidential" "board"` | Apresentações de conselho/diretoria | Google, Bing | 🔴 |
| `filetype:pdf "privileged and confidential" "attorney"` | Comunicações jurídicas privilegiadas | Google, Bing | 🔴 |
| `filetype:docx "sigiloso" "reservado"` | Documentos classificados (terminologia BR) | Google | 🔴 |
| `filetype:pdf "TLP:AMBER" OR "TLP:RED"` | Relatórios com Traffic Light Protocol restrito | Google, Bing | 🔴 |
| `filetype:pdf "company confidential" "do not copy"` | Documentos corporativos com proibição de cópia | Google, Bing | 🔴 |

### Documentos corporativos e operacionais

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:pdf "relatório interno"` | Relatórios internos em português | Google | 🟡 |
| `filetype:pdf "internal audit report"` | Relatórios de auditoria interna | Google, Bing | 🔴 |
| `filetype:pdf "penetration test report"` | Relatórios de pentest publicados por engano | Google, Bing | 🔴 |
| `filetype:pdf "vulnerability assessment" "findings"` | Avaliações de vulnerabilidade com achados | Google, Bing | 🔴 |
| `filetype:docx "ata de reunião"` | Atas de reunião internas | Google | 🟡 |
| `filetype:docx "meeting minutes" "action items"` | Atas de reunião (EN) | Google, Bing | 🟡 |
| `filetype:pdf "organograma"` | Organogramas (mapeamento de estrutura) | Google | 🟢 |
| `filetype:pdf "organizational chart"` | Organogramas (EN) | Google, Bing | 🟢 |
| `filetype:pdf "business continuity plan"` | Planos de continuidade de negócio | Google, Bing | 🟡 |
| `filetype:pdf "disaster recovery plan"` | Planos de recuperação de desastre (revelam infraestrutura) | Google, Bing | 🔴 |
| `filetype:pdf "incident response plan"` | Planos de resposta a incidentes | Google, Bing | 🟡 |
| `filetype:pdf "network diagram"` | Diagramas de rede em PDF | Google, Bing | 🔴 |
| `filetype:vsdx OR filetype:vsd "network"` | Diagramas Visio de rede | Google, Bing | 🔴 |
| `filetype:pdf "standard operating procedure"` | SOPs (procedimentos operacionais) | Google, Bing | 🟡 |
| `filetype:pdf "procedimento operacional padrão"` | POPs em português | Google | 🟡 |
| `filetype:docx "política de segurança da informação"` | PSI (revela controles e ferramentas) | Google | 🟡 |
| `filetype:pdf "information security policy" "password"` | Políticas de segurança que citam regras de senha | Google, Bing | 🟡 |
| `filetype:pdf "employee handbook"` | Manuais do colaborador | Google, Bing | 🟢 |
| `filetype:pdf "onboarding" "VPN" "credentials"` | Guias de onboarding com instruções de acesso | Google, Bing | 🔴 |
| `filetype:pdf "how to connect" "VPN" "username"` | Manuais de conexão VPN | Google, Bing | 🔴 |
| `filetype:docx "plano de negócios"` | Planos de negócio | Google | 🟡 |
| `filetype:pdf "due diligence report"` | Relatórios de due diligence | Google, Bing | 🔴 |
| `filetype:pdf "pricing" "internal" "discount"` | Tabelas de preço/desconto internas | Google, Bing | 🟡 |
| `filetype:pptx "roadmap" "confidential"` | Roadmaps de produto confidenciais | Google, Bing | 🔴 |
| `filetype:pptx "kickoff" "project"` | Apresentações de kickoff de projeto | Google, Bing | 🟢 |

### Contratos, jurídico e RH

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:pdf "contrato de prestação de serviços" "CNPJ"` | Contratos de prestação de serviço | Google | 🟡 |
| `filetype:pdf "non-disclosure agreement" "signed"` | NDAs assinados | Google, Bing | 🔴 |
| `filetype:pdf "termo de confidencialidade"` | NDAs em português | Google | 🟡 |
| `filetype:pdf "master services agreement"` | MSAs corporativos | Google, Bing | 🟡 |
| `filetype:pdf "statement of work" "rate"` | SOWs com valores | Google, Bing | 🟡 |
| `filetype:pdf "folha de pagamento"` | Folhas de pagamento ⚠ dados pessoais | Google | 🔴 |
| `filetype:pdf "payroll" "salary" "employee id"` | Relatórios de folha (EN) ⚠ | Google, Bing | 🔴 |
| `filetype:docx "curriculum vitae" "CPF"` | Currículos com CPF ⚠ LGPD | Google | 🔴 |
| `filetype:pdf "avaliação de desempenho"` | Avaliações de desempenho ⚠ | Google | 🔴 |

### Técnicos e de TI

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `filetype:pdf "manual de instalação" "senha padrão"` | Manuais com senha padrão de equipamentos | Google | 🟡 |
| `filetype:pdf "default password" "admin" "manual"` | Manuais de dispositivos com credenciais padrão | Google, Bing | 🟡 |
| `filetype:pdf "as-built" "IP address"` | Documentação as-built com endereçamento IP | Google, Bing | 🔴 |
| `filetype:docx "IP address" "subnet" "gateway"` | Planilhas/documentos de endereçamento | Google, Bing | 🔴 |
| `filetype:pdf "runbook" "production"` | Runbooks de produção | Google, Bing | 🔴 |
| `filetype:pdf "architecture" "AWS" "VPC" "internal"` | Documentos de arquitetura cloud internos | Google, Bing | 🔴 |
| `filetype:docx "test plan" "UAT"` | Planos de teste/homologação | Google, Bing | 🟢 |
| `filetype:pdf "API documentation" "internal" "token"` | Documentação de API interna com tokens | Google, Bing | 🔴 |
| `filetype:rtf "password"` | Arquivos RTF que mencionam senha | Google, Bing | 🔴 |
| `filetype:odt "senha"` | Documentos LibreOffice com senha | Google | 🔴 |

### Por intitle / inurl

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/uploads/ filetype:pdf "confidential"` | PDFs confidenciais em pastas de upload de CMS | Google | 🔴 |
| `inurl:/wp-content/uploads/ filetype:docx` | Documentos Word em uploads do WordPress | Google | 🟡 |
| `inurl:/sites/default/files/ filetype:pdf "internal"` | Arquivos internos em uploads do Drupal | Google | 🟡 |
| `inurl:/_layouts/ filetype:docx` | Documentos expostos via SharePoint | Google | 🟡 |
| `inurl:/Shared%20Documents/ filetype:pdf` | Bibliotecas "Shared Documents" do SharePoint | Google | 🔴 |
| `inurl:/docs/ intitle:"index of" "pdf"` | Pastas de documentos com listagem aberta | Google | 🟡 |
| `intitle:"index of" "confidential" pdf` | Diretórios abertos com arquivos confidenciais | Google | 🔴 |
| `inurl:/intranet/ filetype:pdf` | PDFs de intranet indexados | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

> Equivalentes funcionais. Bing usa `filetype:`/`ext:`; DuckDuckGo herda boa parte do Bing; Yandex usa `mime:` e `title:`.

| Google | Bing | DuckDuckGo | Yandex |
|---|---|---|---|
| `filetype:pdf "confidencial" "uso interno"` | `filetype:pdf "confidencial" "uso interno"` | `filetype:pdf "confidencial" "uso interno"` | `mime:pdf "confidencial" "uso interno"` |
| `filetype:docx "strictly confidential"` | `ext:docx "strictly confidential"` | `filetype:docx "strictly confidential"` | `mime:docx "strictly confidential"` |
| `filetype:pdf "penetration test report"` | `filetype:pdf "penetration test report"` | `filetype:pdf "penetration test report"` | `mime:pdf "penetration test report"` |
| `filetype:pdf "network diagram"` | `filetype:pdf "network diagram"` | `filetype:pdf "network diagram"` | `mime:pdf "network diagram"` |
| `filetype:pdf "disaster recovery plan"` | `filetype:pdf "disaster recovery plan"` | `filetype:pdf "disaster recovery plan"` | `mime:pdf "disaster recovery plan"` |
| `filetype:pdf "how to connect" "VPN" "username"` | `filetype:pdf "how to connect" VPN username` | `filetype:pdf "how to connect" VPN username` | `mime:pdf "how to connect" VPN username` |
| `intitle:"index of" "confidential" pdf` | `intitle:"index of" confidential pdf` | `intitle:"index of" confidential pdf` | `title:"index of" confidential pdf` |
| `inurl:/wp-content/uploads/ filetype:docx` | `instreamset:url:wp-content/uploads ext:docx` | `inurl:wp-content/uploads filetype:docx` | `inurl:wp-content/uploads mime:docx` |
| `filetype:pptx "roadmap" "confidential"` | `filetype:pptx roadmap confidential` | `filetype:pptx roadmap confidential` | `mime:pptx roadmap confidential` |
| `filetype:pdf "TLP:AMBER" OR "TLP:RED"` | `filetype:pdf ("TLP:AMBER" OR "TLP:RED")` | `filetype:pdf "TLP:AMBER" OR "TLP:RED"` | `mime:pdf ("TLP:AMBER" \| "TLP:RED")` |

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Documentos marcados como confidenciais, por extensão × termo de sigilo — 96 variações

```text
filetype:pdf intext:"confidencial"
filetype:pdf intext:"confidential"
filetype:pdf intext:"uso interno"
filetype:pdf intext:"internal use only"
filetype:pdf intext:"não divulgar"
filetype:pdf intext:"do not distribute"
filetype:pdf intext:"strictly confidential"
filetype:pdf intext:"proprietary"
filetype:pdf intext:"restrito"
filetype:pdf intext:"restricted"
filetype:pdf intext:"sigiloso"
filetype:pdf intext:"private and confidential"
filetype:doc intext:"confidencial"
filetype:doc intext:"confidential"
filetype:doc intext:"uso interno"
filetype:doc intext:"internal use only"
filetype:doc intext:"não divulgar"
filetype:doc intext:"do not distribute"
filetype:doc intext:"strictly confidential"
filetype:doc intext:"proprietary"
filetype:doc intext:"restrito"
filetype:doc intext:"restricted"
filetype:doc intext:"sigiloso"
filetype:doc intext:"private and confidential"
filetype:docx intext:"confidencial"
filetype:docx intext:"confidential"
filetype:docx intext:"uso interno"
filetype:docx intext:"internal use only"
filetype:docx intext:"não divulgar"
filetype:docx intext:"do not distribute"
filetype:docx intext:"strictly confidential"
filetype:docx intext:"proprietary"
filetype:docx intext:"restrito"
filetype:docx intext:"restricted"
filetype:docx intext:"sigiloso"
filetype:docx intext:"private and confidential"
filetype:rtf intext:"confidencial"
filetype:rtf intext:"confidential"
filetype:rtf intext:"uso interno"
filetype:rtf intext:"internal use only"
filetype:rtf intext:"não divulgar"
filetype:rtf intext:"do not distribute"
filetype:rtf intext:"strictly confidential"
filetype:rtf intext:"proprietary"
filetype:rtf intext:"restrito"
filetype:rtf intext:"restricted"
filetype:rtf intext:"sigiloso"
filetype:rtf intext:"private and confidential"
filetype:odt intext:"confidencial"
filetype:odt intext:"confidential"
filetype:odt intext:"uso interno"
filetype:odt intext:"internal use only"
filetype:odt intext:"não divulgar"
filetype:odt intext:"do not distribute"
filetype:odt intext:"strictly confidential"
filetype:odt intext:"proprietary"
filetype:odt intext:"restrito"
filetype:odt intext:"restricted"
filetype:odt intext:"sigiloso"
filetype:odt intext:"private and confidential"
filetype:ppt intext:"confidencial"
filetype:ppt intext:"confidential"
filetype:ppt intext:"uso interno"
filetype:ppt intext:"internal use only"
filetype:ppt intext:"não divulgar"
filetype:ppt intext:"do not distribute"
filetype:ppt intext:"strictly confidential"
filetype:ppt intext:"proprietary"
filetype:ppt intext:"restrito"
filetype:ppt intext:"restricted"
filetype:ppt intext:"sigiloso"
filetype:ppt intext:"private and confidential"
filetype:pptx intext:"confidencial"
filetype:pptx intext:"confidential"
filetype:pptx intext:"uso interno"
filetype:pptx intext:"internal use only"
filetype:pptx intext:"não divulgar"
filetype:pptx intext:"do not distribute"
filetype:pptx intext:"strictly confidential"
filetype:pptx intext:"proprietary"
filetype:pptx intext:"restrito"
filetype:pptx intext:"restricted"
filetype:pptx intext:"sigiloso"
filetype:pptx intext:"private and confidential"
filetype:odp intext:"confidencial"
filetype:odp intext:"confidential"
filetype:odp intext:"uso interno"
filetype:odp intext:"internal use only"
filetype:odp intext:"não divulgar"
filetype:odp intext:"do not distribute"
filetype:odp intext:"strictly confidential"
filetype:odp intext:"proprietary"
filetype:odp intext:"restrito"
filetype:odp intext:"restricted"
filetype:odp intext:"sigiloso"
filetype:odp intext:"private and confidential"
```

> **Padrão:** Documentos em diretórios abertos, por extensão — 8 variações

```text
intitle:"index of" ext:pdf
intitle:"index of" ext:doc
intitle:"index of" ext:docx
intitle:"index of" ext:rtf
intitle:"index of" ext:odt
intitle:"index of" ext:ppt
intitle:"index of" ext:pptx
intitle:"index of" ext:odp
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- **Templates e modelos** ("modelo de contrato", "template") geram muitos falsos positivos — exclua com `-template -modelo -sample -exemplo`.
- **Cursos e apostilas** usam as palavras "confidencial" e "pentest report" como exemplo. Combine com `site:` para reduzir ruído.
- **`filetype:` vs `ext:`** — no Google são equivalentes; `filetype:` reconhece o tipo MIME e `ext:` a extensão da URL. Em URLs com parâmetros (`download.php?id=…`) o tipo real pode não aparecer em nenhum dos dois.
- Para documentos **removidos**, consulte o [Wayback Machine](https://web.archive.org/) — o operador `cache:` foi desativado (veja o [manual do Google](../../docs/manual/01-google.md)).

<div align="center">

[🏠 Hub](../../README.md) · [📂 Exposição de Arquivos](README.md) · [Próximo: Planilhas & CSV →](planilhas-e-csv.md)

</div>
