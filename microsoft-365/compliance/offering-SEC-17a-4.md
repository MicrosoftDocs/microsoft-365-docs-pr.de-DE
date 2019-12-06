---
title: Securities and Exchange Commission (sec) Rule 17a-4 (f) Vereinigte Staaten
description: Eine unabhängige Bewertungs Firma hat bestätigt, dass Azure und Office 365 Finanzunternehmen bei der Erfüllung der SEC-Regel 17a-4 (f) Datensatzaufbewahrung und unveränderliche Speicheranforderungen unterstützen können.
keywords: Microsoft 365, Compliance, Angebote
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: 08ae4841f2523d5b5df576906bdf04e798d8e60f
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859515"
---
# <a name="securities-and-exchange-commission-sec-rule-17a-4f-united-states"></a>Securities and Exchange Commission (sec) Rule 17a-4 (f) Vereinigte Staaten

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft-und sec-Regel 17a-4 (f)

Die [US Securities and Exchange Commission (sec)](https://www.sec.gov/) ist eine unabhängige Agentur der US-Bundesregierung und des primären Aufsichtsrats und Regulators von US Securities Markets. Er übt Durchsetzungsbefugnisse auf Bundes Wertpapierrecht aus, schlägt neue Wertpapier Regelungen vor und überwacht die Marktregulierung der Wertpapier Industrie.

In der SEC werden strenge und explizite Anforderungen für regulierte Entitäten definiert, die sich für die Aufbewahrung von Büchern und Datensätzen auf elektronischen Speichermedien entscheiden. Sie hat [17 CFR 240.17 a-3](https://www.govinfo.gov/app/details/CFR-2012-title17-vol3/CFR-2012-title17-vol3-sec240-17a-3) und [17 CFR 240.17 a-4](https://www.ecfr.gov/cgi-bin/text-idx?mc=true&node=pt17.4.240&rgn=div5#se17.4.240_117a_64) zum Regulieren der Archivierung (einschließlich Aufbewahrungszeiträume) für Wertpapierbroker-Händler eingerichtet. Später [änderte](https://www.sec.gov/rules/interp/34-47806.htm) die SEC 17 CFR 240.17 a-4 Paragraph (f) mit zwei Interpretations Freigaben, um zu ermöglichen, dass Bücher und Aufzeichnungen auf elektronischen Speichermedien aufbewahrt werden, solange bestimmte Bedingungen erfüllt wurden.

Ein elektronisches Speichersystem erfüllt diese Bedingungen, wenn es die Änderung oder Löschung von Datensätzen für den erforderlichen Aufbewahrungszeitraum verhindert. Die Aufbewahrungszeiträume variieren je nach Datensatztypen von drei bis sechs Jahren, wobei die sofortige Barrierefreiheit für die ersten zwei Jahre beauftragt ist. Darüber hinaus muss für eine der Interpretations Versionen festgelegt werden, dass das Speichersystem Datensätze über den von der SEC festgelegten Aufbewahrungszeitraum hinaus aufbewahren kann, um Vorladungen, Rechtliche Aufbewahrungspflicht oder andere solche Anforderungen einzuhalten.

## <a name="microsoft-and-sec-rule-17a-4f"></a>Microsoft-und sec-Regel 17a-4 (f)

Kunden von Finanzdienstleistungen, die eine der am stärksten regulierten Branchen der Welt darstellen, unterliegen komplexen Bestimmungen wie der Beibehaltung von Finanztransaktionen und der damit verbundenen Kommunikation in einem nicht löschbaren und nicht veränderbaren Zustand. Zu den Bestimmungen gehört Regel 17a-4 (f) der US-Sicherheits-und Exchange-Kommission (sec), die strenge Anforderungen für regulierte Entitäten festlegt, die Bücher und Aufzeichnungen auf elektronischen Speichermedien speichern. Gespeicherte Datensätze müssen manipulationssicher sein, sodass Sie erst nach Ablauf des festgelegten Aufbewahrungszeitraums geändert oder gelöscht werden können.

Microsoft Azure unveränderlicher BLOB-Speicher mit Richtlinien Sperre und Microsoft Office 365 mit Aufbewahrungs Sperre können Finanzinstituten dabei helfen, die unveränderlichen Speicheranforderungen der SEC-Regel 17a-4 (f) zu erfüllen.

Zur Bewertung von Azure und Office 365 Compliance mit der SEC-Regel 17a-4 (f) behielt Microsoft eine unabhängige Bewertungs Firma, die sich auf die Verwaltung von Datensätzen und die Information Governance spezialisiert hat. Im Ergebnisbericht für:

- **Azure**: [SEC 17a-4 (f) Compliance Assessment: Microsoft Azure Speicher](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports), validierte der Benutzer, dass [Azure unveränderlicher BLOB-Speicher](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) mit der Richtlinien Sperroption, wenn zeitbasierte BLOBs in einem nicht löschbaren und nicht wiederbeschreibbaren (Worm)-Format aufbewahrt werden, die unveränderlichen Speicheranforderungen der SEC-Regel erfüllt. Jedes BLOB (Record) wird vor der Änderung, Überschreibung oder Löschung geschützt, bis der erforderliche Aufbewahrungszeitraum abgelaufen ist und alle zugehörigen rechtlichen Aufbewahrungspflichten freigegeben wurden. Software Anbieter und Partner mit vertraulichen Arbeitslasten können jetzt auf Azure unveränderlichen BLOB-Speicher als Onestop-Cloud-Lösung für die Aufbewahrung von Datensätzen und den unveränderlichen Speicher zurückgreifen. Finanzinstitute können jetzt Ihre eigenen Anwendungen erstellen, indem Sie diese Funktionen nutzen und gleichzeitig kompatibel bleiben.
- **Office 365**: [verwenden Sie Exchange Online zur Einhaltung von SEC 17a-4](https://docs.microsoft.com/office365/securitycompliance/use-exchange-online-to-comply-with-sec-rule-17a-4), der bestätigte [, dass Office 365 mit der Aufbewahrungs Sperre](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy) Archivierungsfunktionen enthält, mit denen regulierte Kunden, einschließlich Broker-Dealer, Daten so speichern können, dass Sie die Anforderungen der Datensatzaufbewahrung an die SEC erfüllen. Mithilfe von Aufbewahrungsrichtlinien in Office 365 erhalten Sie eine breite Palette von Daten, einschließlich e-Mail, Voicemail, freigegebene Dokumente, Sofortnachrichten und Daten von Drittanbietern. Die Archivierung in Office 365 ermöglicht es Kunden insbesondere, globale oder granulare Messaging-Aufbewahrungsrichtlinien festzulegen, um Daten für einen bestimmten Zeitraum und darüber hinaus in einem nicht wiederbeschreibbaren, nicht löschbaren Format zu speichern.

## <a name="microsoft-in-scope-cloud-services"></a>In-Scope-Cloud-Dienste von Microsoft

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9f756cce-b15d-45a9-94d7-6a583dee4401&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

## <a name="audits-reports-and-certificates"></a>Prüfungen, Berichte und Zertifikate

### <a name="azure--sec-rule-17"></a>Azure #a0 sec-Regel 17

[SEC 17a-4 (f) #a0 CFTC 1,31 (c-d) Compliance Assessment of Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--sec-rule-17"></a>Office 365 #a0 sec-Regel 17

[SEC 17a-4 (f) Compliance Assessment: Microsoft Security #a0 Compliance Center mit Exchange Online](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

## <a name="how-to-implement"></a>Implementierung

### <a name="financial-services-regulation"></a>Finanz dienstleistungsverordnung

Compliance-Map der wichtigsten US-regulatorischen Grundsätze für Cloud Computing und Microsoft Online Services. [Weitere Informationen](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

### <a name="risk-assessment--compliance-guide"></a>Risikobewertung #a0 Compliance-Leitfaden

Erstellen eines steuerungsmodells für die Risikobewertung von Microsoft-Cloud-Diensten und Regulierer-Benachrichtigungen. [Weitere Informationen](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

### <a name="financial-use-cases"></a>Finanz Anwendungsfälle

Verwenden Sie Groß-/Kleinschreibung, Lernprogramme und andere Ressourcen, um Azure-Lösungen für Finanzdienstleistungen zu erstellen. [Weitere Informationen](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>Ressourcen

- Archivierung in Microsoft Office 365, Datenaufbewahrung und Regel 17a-4
- [Compliance Microsoft Financial Services](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [Compliance-Programm Microsoft Business Cloud Services and Financial Services](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Finanzdienstleister-Compliance in Azure](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure Financial Services Cloud Risikobewertungstool](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Microsoft Office 365-Aufbewahrungsrichtlinien](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft Financial Services Blog](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Compliance im Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Hintergrundinformationen zum Angebot herunterladen

Benötigen Sie das Dokument mit Hintergrundwissen für dieses Angebot? Laden Sie die [PDF-Datei](https://download.microsoft.com/download/E/5/2/E52103E7-C1BB-4118-9725-4452FEA931D8/SEC17a-4(f)-Compliance.pdf) herunter.
