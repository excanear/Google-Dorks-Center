<div align="center">

[🏠 Hub](../../README.md) · [🏛 Setores Regulados & Nichos](README.md) · [Próximo: Educação & EAD →](educacao-e-ead.md)

# 🏥 Saúde & Médico

*Servidores de imagem DICOM/PACS e portais de clínica expostos — identificar o sistema, nunca os dados de pacientes.*

</div>

---

> [!CAUTION]
> ⚠ **Dado de saúde é categoria especial (LGPD art. 11 / GDPR art. 9).** Os dorks abaixo identificam a **exposição do sistema/portal** — a existência pública é o achado a reportar. **Não** acesse imagens, exames ou prontuários de pacientes: isso é tratamento ilícito de dado sensível. Siga o [aviso legal completo](../../README.md#-aviso-de-uso-legal-e-ético).

## 📑 Nesta página

- [Curados](#-curados)
- [Traduções entre buscadores](#-traduções-entre-buscadores)
- [Expansão sistemática](#-expansão-sistemática)
- [Notas & falsos positivos](#-notas--falsos-positivos)

---

## 🎯 Curados

### Visualizadores e servidores PACS/DICOM

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `intitle:"Orthanc Explorer"` | Servidor DICOM Orthanc (web) | Google | 🔴 |
| `inurl:/dcm4chee-arc/ui2` | Interface dcm4chee-arc | Google | 🔴 |
| `intitle:"PacsOne Server"` | Servidor PACS PacsOne | Google | 🔴 |
| `inurl:/pacs intitle:"login"` | Portal PACS genérico | Google | 🔴 |
| `intitle:"DICOM" inurl:/viewer` | Visualizador DICOM web | Google | 🔴 |

### Portais de clínica e gestão

| Dork | Finalidade | Buscadores | Risco |
|---|---|---|---|
| `inurl:/login intext:"prontuário eletrônico"` | Portal de prontuário (login) | Google | 🔴 |
| `intitle:"OpenEMR" inurl:/interface` | Sistema OpenEMR | Google | 🔴 |
| `intitle:"OpenMRS"` | Plataforma OpenMRS | Google | 🔴 |
| `inurl:/clinic intitle:"login" intext:"agenda"` | Portal de agendamento clínico | Google | 🟡 |
| `intitle:"GNU Health"` | Sistema GNU Health | Google | 🔴 |

---

## 🔁 Traduções entre buscadores

| Google | Shodan | Censys |
|---|---|---|
| `intitle:"Orthanc Explorer"` | `http.title:"Orthanc Explorer"` | `services.http.response.html_title:"Orthanc Explorer"` |
| *(serviço DICOM)* | `port:104 "DICOM"` | `services.port:104` |
| *(serviço DICOM alt.)* | `port:11112 "DICOM"` | `services.port:11112` |
| `intitle:"OpenEMR"` | `http.title:"OpenEMR"` | `services.http.response.html_title:"OpenEMR"` |

> **Infraestrutura é o canal principal:** o protocolo DICOM roda em `104`, `11112` ou `2761`. No Shodan, `port:104 has_screenshot:false "DICOM"` localiza servidores. **Identificar** é o objetivo; conectar ao serviço e puxar estudos é acesso a dado sensível — não faça.

---

## 🧬 Expansão sistemática

> Cada bloco aplica **um padrão** a uma lista de variáveis com sentido técnico. Um dork por linha — copie a linha inteira.

<!-- expansao:inicio -->

> **Padrão:** Sistema PACS/DICOM por caminho (identificação, não acesso a dados) — 7 variações

```text
inurl:/orthanc
inurl:/osirix
inurl:/weasis
inurl:/ohif
inurl:/pacs/login
inurl:/wado
inurl:/dicom-web
```

<!-- expansao:fim -->

---

## 📝 Notas & falsos positivos

- Pesquisas públicas (Trend Micro, 2025) contaram **milhares** de servidores DICOM expostos mundialmente, a maioria **sem TLS** e sem validação de AE Title — o problema é real e sistêmico.
- O achado legítimo é **"existe um PACS/portal exposto"** — reporte ao responsável para contenção. O conteúdo (imagens, laudos) é dado sensível e está fora de escopo.
- `OpenEMR`/`OpenMRS`/`GNU Health` acumulam CVEs; a versão exposta liga a [09 · Vulnerabilidades](../09-vulnerabilidades/README.md).
- Dispositivo médico físico (bomba, monitor) é de [06 · IoT & ICS/SCADA](../06-iot-ics-scada/README.md); aqui é o **software/portal**.

<div align="center">

[🏠 Hub](../../README.md) · [🏛 Setores Regulados & Nichos](README.md) · [Próximo: Educação & EAD →](educacao-e-ead.md)

</div>
