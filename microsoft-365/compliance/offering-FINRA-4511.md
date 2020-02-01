---
title: Financial Industry Regulatory Authority (FINRA) Rule 4511 (c) United States
description: Eine unabhängige Bewertungs Firma hat bestätigt, dass Azure und Office 365 Finanzunternehmen dabei helfen können, FINRA Regel 4511 Datensatzaufbewahrung und unveränderlichen Speicheranforderungen zu erfüllen.
keywords: Microsoft 365, Compliance, Angebote
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 9518fbdca5e7234e31979e4c88fe4499b65fc5f0
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602402"
---
# <a name="financial-industry-regulatory-authority-finra-rule-4511c-united-states"></a>Financial Industry Regulatory Authority (FINRA) Rule 4511 (c) United States

## <a name="about-finra-rule-4511"></a>Informationen zur FINRA-Regel 4511

Die [Financial Industry Regulatory Authority (FINRA)](https://www.finra.org/#/) ist die größte unabhängige Stelle zur Regulierung von Wertpapierfirmen mit Aufsicht über mehr als 4.500 Brokerfirmen in den Vereinigten Staaten. Es wurde vom US-Kongress autorisiert, "Amerikas Investoren zu schützen, indem Sie sicherstellen, dass die Broker-Händler-Branche fair und ehrlich agiert."

In 2011 hat die US-Sicherheits-und Exchange-Kommission (sec) die FINRA Annahme von SEC-Regeln für die Aufbewahrung von Büchern und Datensätzen auf elektronischen Speichermedien genehmigt. [FINRA Regel 4511 (c)](https://www.finra.org/sites/default/files/NoticeDocument/p123548.pdf) gibt an, dass "alle Bücher und Aufzeichnungen, die gemäß den FINRA-Regeln ausgeführt werden müssen, in einem Format und in einem Medium aufbewahrt werden, das mit der Regel" Sea (Securities Exchange Act) Rule 17a-4 "konform ist.

Außerdem erfordert FINRA Rule 4511 (c), dass Unternehmen für einen Zeitraum von mindestens sechs Jahren die Bücher und Datensätze aufbewahren, für die es keine festgelegten Aufbewahrungsfristen gemäß den geltenden FINRA-oder Sea-Regeln gibt. Wenn sich die Bücher und Datensätze auf ein Konto beziehen, ist der Aufbewahrungszeitraum für sechs Jahre nach dem Kontoabschluss beauftragt. Andernfalls beträgt der Aufbewahrungszeitraum sechs Jahre, nachdem solche Bücher und Datensätze erstellt wurden.

## <a name="microsoft-and-finra-rule-4511c"></a>Microsoft-und FINRA-Regel 4511 (c)

Kunden von Finanzdienstleistungen, die eine der am stärksten regulierten Branchen der Welt darstellen, unterliegen komplexen Bestimmungen wie der Beibehaltung von Finanztransaktionen und der damit verbundenen Kommunikation in einem nicht löschbaren und nicht veränderbaren Zustand. Unter Ihnen ist Regel 4511 der Financial Industry Regulatory Authority (FINRA), die strenge Anforderungen für regulierte Entitäten festlegt, die sich für die Aufbewahrung von Büchern und Aufzeichnungen auf elektronischen Speichermedien entscheiden. Gespeicherte Datensätze müssen manipulationssicher sein, sodass Sie erst nach Ablauf des festgelegten Aufbewahrungszeitraums geändert oder gelöscht werden können.

Microsoft Azure unveränderlicher BLOB-Speicher mit Richtlinien Sperre und Microsoft Office 365 mit Aufbewahrungs Sperre können Finanzinstituten dabei helfen, die unveränderlichen Speicheranforderungen von FINRA Rule 4511 (c) zu erfüllen.

## <a name="microsoft-azure"></a>Microsoft Azure

Um die Azure-Konformität mit FINRA Rule 4511 (c) zu evaluieren, behielt Microsoft eine unabhängige Bewertungs Firma, die sich auf die Verwaltung von Datensätzen und die Information Governance spezialisiert hat. Der resultierende Bericht [SEC 17a-4 (f) #a0 CFTC 1,31 (c-d) Compliance Assessment: Microsoft Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)umfasst die Azure-Konformität mit FINRA Rule 4511 (c), die die Format-und Medienanforderungen der SEC-Regel 17a-4 (f) aufweist.

Der Benutzer hat bestätigt, dass [Azure unveränderlicher BLOB-Speicher](https://docs.microsoft.com/azure/storage/blobs/storage-blob-immutable-storage) mit der Option für die Richtlinien Sperre, wenn zeitbasierte BLOBs in einem nicht löschbaren und nicht wiederbeschreibbaren (Worm)-Format aufbewahrt werden, den relevanten FINRA-Speicheranforderungen entspricht. Jedes BLOB (Record) wird vor der Änderung, Überschreibung oder Löschung geschützt, bis der erforderliche Aufbewahrungszeitraum abgelaufen ist und alle zugehörigen rechtlichen Aufbewahrungspflichten freigegeben wurden.

Software Anbieter und Partner mit vertraulichen Arbeitslasten können jetzt auf Azure unveränderlichen BLOB-Speicher als One-Stop-Shop-Cloud-Lösung für die Aufbewahrung von Datensätzen und den unveränderlichen Speicher setzen. Finanzinstitute können jetzt Ihre eigenen Anwendungen erstellen, indem Sie diese Funktionen nutzen und gleichzeitig kompatibel bleiben.

## <a name="microsoft-office-365"></a>Microsoft Office 365

Um Office 365 Compliance mit FINRA Rule 4511 (c) zu evaluieren, behielt Microsoft eine führende unabhängige Anwaltskanzlei, die sich auf regulatorische Probleme spezialisierte, Covington #a0 Burling, LLP. In dem resultierenden Bericht, der Archivierung in Microsoft Office 365, der Datenaufbewahrung und der Regel 17a-4-Konformität hat Covington festgestellt, dass [Office 365 mit der Aufbewahrungs Sperre](https://docs.microsoft.com/office365/securitycompliance/retention-policies#locking-a-retention-policy) Archivierungsfunktionen enthält, mit denen regulierte Kunden, einschließlich Broker-Dealern, Daten so speichern können, dass Sie die FINRA-Anforderungen für die Aufbewahrung von Datensätzen erfüllen.

Die Archivierung in Office 365 hilft bei der Beibehaltung einer Vielzahl von Daten, einschließlich e-Mail, Voicemail, freigegebene Dokumente, Sofortnachrichten und Daten von Drittanbietern. Die Archivierung in Office 365 ermöglicht es Kunden insbesondere, globale oder granulare Messaging-Aufbewahrungsrichtlinien festzulegen, um Daten für einen bestimmten Zeitraum und darüber hinaus in einem nicht wiederbeschreibbaren, nicht löschbaren Format zu speichern.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft-Clouddienste im Leistungsumfang

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Office 365](https://aka.ms/Office365ComplianceOfferings)

## <a name="audits-reports-and-certificates"></a>Prüfungen, Berichte und Zertifikate

### <a name="azure--finra-rule-4511c"></a>Azure #a0 FINRA Rule 4511 (c)

[SEC 17a-4 (f) #a0 CFTC 1,31 (c-d) Compliance Assessment of Azure Storage](https://servicetrust.microsoft.com/ViewPage/MSComplianceGuide?command=Download&downloadType=Document&downloadId=19b08fd4-d276-43e8-9461-715981d0ea20&docTab=4ce99610-c9c0-11e7-8c2c-f908a777fa4d_GRC_Assessment_Reports)

### <a name="office-365--finra-rule-4511c"></a>Office 365 #a0 FINRA Rule 4511 (c)

[Archivierung in Office 365, Datenaufbewahrung und sec-Regel 17a-4-Compliance](https://www.microsoft.com/microsoft-365/blog/2015/11/10/office-365-exchange-online-archiving-now-meets-sec-rule-17a-4-requirements/)

## <a name="how-to-implement"></a>Implementierung

- **Finanz dienstleistungsverordnung**: Compliance-Karte der wichtigsten US-regulatorischen Grundsätze für Cloud Computing und Microsoft Online Services. [Weitere Informationen](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=5b483567-00b0-4d86-96ae-ee887dadb61c&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)
- **Leitfaden für Risikobewertung und Compliance**: Erstellen Sie ein Governance-Modell für die Risikobewertung von Microsoft Cloud Services und die Benachrichtigung der Aufsichtsbehörden. [Weitere Informationen](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- **Anwendungsfälle in der Finanzbranche**: Verwenden Sie Fallübersichten, Lernprogramme und andere Ressourcen, um Azure-Lösungen für Finanzdienstleistungen zu entwickeln. [Weitere Informationen](https://docs.microsoft.com/azure/industry/financial/)

## <a name="resources"></a>Ressourcen

- [Microsoft Compliance-Programm für Finanzdienstleiter](https://download.microsoft.com/download/6/4/7/64707E3E-6D3E-45D0-8207-A0EA3201B4A6/Microsoft%20Cloud%20-%20Financial%20Services%20Compliance%20Program%20\(Print\).pdf)
- [Microsoft Clouddienste für Unternehmen und Finanzdienstleistungen](https://servicetrust.microsoft.com/viewpage/financialservicesoverview)
- [Finanzdienstleister-Compliance in Azure](https://azure.microsoft.com/resources/videos/azurecon-2015-financial-services-compliance-in-azure/)
- [Azure Financial Services Cloud Risikobewertungstool](https://servicetrust.microsoft.com/ViewPage/FFIECBlueprint?command=Download&downloadType=Document&downloadId=079a1973-711a-428f-9312-9ddd290cff7b&docTab=c726d5c0-2d1e-11e8-a485-57140ec19669_PaaS)
- [Microsoft Office 365-Aufbewahrungsrichtlinien](https://docs.microsoft.com/office365/securitycompliance/retention-policies)
- [Microsoft Financial Services Blog](https://techcommunity.microsoft.com/t5/Financial-Services-Blog/bg-p/FinancialServicesBlog)
- [Compliance im Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Hintergrundinformationen zum Angebot herunterladen

Benötigen Sie das Dokument mit Hintergrundwissen für dieses Angebot? Laden Sie die [PDF-Datei](https://download.microsoft.com/download/6/B/2/6B20520B-E264-4B58-9EE2-DD6C87D9E254/FINRA-Compliance.pdf) herunter.
