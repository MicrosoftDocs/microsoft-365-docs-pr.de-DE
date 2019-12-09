---
title: North American Electric Reliability Corporation (NERC)
description: Azure und Azure Government eignen sich für registrierte Entitäten, die bestimmte Workloads in der Cloud bereitstellen, die NERC-CIP-Standards unterworfen sind.
keywords: Microsoft 365, Compliance, Angebote
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: ceb87ace9d4ed832ea23ea7cddaf7e73ce0a17cb
ms.sourcegitcommit: eb0f255baff1f2856621cbc64a3f34a04be37be3
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39859359"
---
# <a name="north-american-electric-reliability-corporation-nerc"></a>North American Electric Reliability Corporation (NERC)

## <a name="about-the-nerc"></a>Informationen zu NERC

Die [North American Electric Reliability Corporation](https://www.nerc.com/) (NERC) ist eine Non-Profit-Aufsichtsbehörde, welche die Zuverlässigkeit des nordamerikanischen Hochleistungsstromnetzes sicherstellt. NERC unterliegt der Aufsicht der US Federal Energy Regulatory Commission (FERC) und der staatlichen Behörden in Kanada. 2006 hat FERC der NERC die Bezeichnung Electric Reliability Organization (ERO) gemäß dem Energy Policy Act von 2005 (US Public Law 109-58) verliehen. NERC entwickelt und erzwingt Zuverlässigkeitsstandards, die als NERC [CIP-Standards (Critical Infrastructure Protection)](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx) bekannt sind.

## <a name="microsoft-and-the-nerc-cip-standard"></a>Microsoft und der NERC CIP-Standard

Die North American Electric Reliability Corporation (NERC) ist eine Non-Profit-Aufsichtsbehörde, welche die Zuverlässigkeit des nordamerikanischen Hochleistungsstromnetzes sicherstellt. NERC unterliegt der Aufsicht der US Federal Energy Regulatory Commission (FERC) und der staatlichen Behörden in Kanada. 2006 hat FERC der NERC die Bezeichnung Electric Reliability Organization (ERO) gemäß dem Energy Policy Act von 2005 (US Public Law 109-58) verliehen. NERC entwickelt und erzwingt Zuverlässigkeitsstandards, die als NERC [CIP-Standards (Critical Infrastructure Protection)](https://www.nerc.com/pa/Stand/Pages/CIPStandards.aspx) bekannt sind.

Alle Eigentümer, Operatoren und Benutzer des Hochleistungsstromnetzes müssen [den NERC CIP-Standards entsprechen](https://www.nerc.com/pa/comp/Pages/default.aspx). Diese Entitäten müssen sich bei NERC registrieren. Cloud-Dienstanbieter und Drittanbieter unterliegen nicht den NERC CIP-Standards. Die CIP-Standards umfassen jedoch Ziele, die berücksichtigt werden sollten, wenn [registrierte Entitäten](https://www.nerc.com/pa/comp/Pages/Registration.aspx) Anbieter beim Betrieb des Großelektrosystems (Bulk Electric System, BES) nutzen. Microsoft-Kunden, die Großelektrosysteme betreiben, sind vollständig dafür verantwortlich, die Einhaltung der NERC CIP-Standards sicherzustellen. Weder Microsoft Azure noch Microsoft Azure Government stellt ein BES oder BES Cyber Asset dar.

Wie von NERC in den aktuellen [CIP-Standards](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf) und dem NERC-[Glossar](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf) angegeben, führen BES Cyber Assets Echtzeitfunktionen zur Überwachung oder Kontrolle des BES durch und würden den zuverlässigen Betrieb des BES innerhalb von 15 Minuten nach ihrer Beeinträchtigung stören. Zur ordnungsgemäßen Anpassung von BES Cyber Assets und Protected Cyber Assets an das Cloud Computing müssten bestehende Definitionen in den NERC CIP-Standards [überarbeitet werden](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx). Allerdings gibt es viele Workloads, die CIP-sensitive Daten betreffen und nicht unter die 15-Minuten-Regel fallen, einschließlich der umfassenden Kategorie der BES Cyber System Information (BCSI).

Azure und Azure Government eignen sich für registrierte Entitäten, die bestimmte Workloads bereitstellen, die NERC CIP-Standards unterworfen sind, einschließlich BCSI-Workloads. Microsoft stellt registrierten Entitäten, die an der Bereitstellung von NERC CIP-Complianceverpflichtungen unterliegenden Daten und Workloads in Azure oder Azure Government interessiert sind, die folgenden Dokumente zur Verfügung:

- [NERC CIP-Standards und Cloud Computing](https://aka.ms/AzureNERC) ist ein Whitepaper, in dem Complianceüberlegungen für NERC CIP-Anforderungen basierend auf etablierten Drittanbieterüberprüfungen behandelt werden, die für Cloud-Dienstanbieter wie FedRAMP gelten. Es behandelt Hintergrunduntersuchungen für Mitarbeiter in der Cloud und beantwortet häufige Fragen zur logischen Isolation und zur Mehrmandantenfähigkeit, die für registrierte Entitäten von Interesse sind. Außerdem werden Sicherheitsüberlegungen zur lokalen Bereitstellung im Vergleich zur Bereitstellung in der Cloud behandelt.
- [Cloudimplementierungsanleitung für NERC-Überprüfungen](https://aka.ms/AzureNERCGuide) ist ein Leitfaden, der die Zuordnung zwischen den Kontrollen der aktuellen NERC CIP-Standardanforderungen und den [NIST SP 800-53 Rev 4](https://nvd.nist.gov/800-53/Rev4)-Kontrollen enthält, welche die Basis für FedRAMP bilden. Er ist als technische Anleitung zur Unterstützung von registrierten Entitäten zur Einhaltung der NERC CIP-Complianceanforderungen für in der Cloud bereitgestellte Objekte konzipiert. Das Dokument enthält vorab ausgefüllte Berichte zu [Reliability Standard Audit Worksheets (RSAWs)](https://www.nerc.com/pa/comp/Pages/Reliability-Standard-Audit-Worksheets-\(RSAWs\).aspx), die erklären, wie Azure-Sicherheitskontrollen NERC CIP-Anforderungen entsprechen, und Anleitungen für registrierte Entitäten, um Azure Services zum Implementieren von Kontrollen zu verwenden, die sie besitzen.

Das NERC Unternehmen ERO [veröffentlichte](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx) eine Compliance Monitoring and Enforcement Program (CMEP)-[Praxisleitlinie](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf), welche die CMEP-Mitarbeiter des Unternehmens ERO beim Bewerten des Prozesses einer registrierten Entität zur Autorisierung des Zugriffs auf designierte BCSI-Speicherorte und aller von der registrierten Entität implementierten Zugriffskontrollen anleitet. Darüber hinaus hat NERC die Implementierungsdetails der Azure-Sicherheitskontrollen sowie FedRAMP-Überwachungsnachweise hinsichtlich der Standards NERC CIP-004-6 und CIP-011-2 überprüft, die für BCSI gelten. Basierend auf dem von ERO ausgegebenen Praxisleitfaden und den überprüften FedRAMP-Kontrollen, die sicherstellen sollen, dass registrierte Entitäten ihre Daten verschlüsseln, sind keine zusätzlichen Anleitungen oder Erläuterungen erforderlich, damit registrierte Entitäten BCSI und zugeordnete Workloads in der Cloud bereitstellen können. Allerdings sind registrierte Entitäten letztlich für die Compliance mit NERC CIP-Standards gemäß ihren eigenen Fakten und Gegebenheiten verantwortlich. Registrierte Entitäten sollten die [Cloudimplementierungsanleitung für NERC-Überprüfungen](https://aka.ms/AzureNERCGuide) zur Unterstützung bei der Dokumentation ihrer Prozesse und Nachweise für die Autorisierung des elektronischen Zugriffs auf BCSI-Speicherorte überprüfen, einschließlich der Verschlüsselungsschlüsselverwaltung, die für die BCSI-Verschlüsselung in Azure und Azure Government verwendet wird.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft Cloud Services im Leistungsumfang

- [Azure und Azure Government](https://aka.ms/AzureCompliance)

## <a name="audits-reports-and-certificates"></a>Prüfungen, Berichte und Zertifikate

Microsoft muss seine Clouddienste jedes Jahr rezertifizieren, um seine P-ATOs und ATOs zu behalten. Dazu muss Microsoft seine Sicherheitskontrollen laufend überwachen und bewerten sowie nachweisen, dass sie konform bleiben.

- [Microsoft Cloud Services-Autorisierungen](https://marketplace.fedramp.gov/?sort=productName&productNameSearch=azure#/product/azure-government)
- [FedRAMP-Prüfberichte für Microsoft](https://aka.ms/MicrosoftFedRAMPAuditDocuments)

## <a name="how-to-implement"></a>Implementierung

### <a name="nerc-cip-standards-and-cloud-computing"></a>NERC CIP-Standards und Cloud Computing

Bezieht sich auf die Compliance für registrierte Entitäten, welche die Cloudeinführung von NERC CIP-Standards unterliegenden Workloads in Betracht ziehen.

[Weitere Informationen](https://aka.ms/AzureNERC)

### <a name="cloud-implementation-guide-for-nerc-audits"></a>Cloudimplementierungsanleitung für NERC-Überprüfungen

Technische Anleitungen helfen registrierten Entitäten bei NERC-Überprüfungen von in Azure oder Azure Government bereitgestellten Objekten. 

[Weitere Informationen](https://aka.ms/AzureNERCGuide)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Wer ist für die Einhaltung der NERC CIP-Standards verantwortlich?**

Alle Eigentümer, Operatoren und Benutzer des Hochleistungsstromnetzes müssen [den NERC CIP-Standards entsprechen](https://www.nerc.com/pa/comp/Pages/default.aspx). Diese Entitäten müssen sich bei NERC registrieren. Cloud-Dienstanbieter und Drittanbieter unterliegen nicht den NERC CIP-Standards. Die CIP-Standards umfassen jedoch Ziele, die berücksichtigt werden sollten, wenn [registrierte Entitäten](https://www.nerc.com/pa/comp/Pages/Registration.aspx) Anbieter beim Betrieb des Großelektrosystems (Bulk Electric System, BES) nutzen. Microsoft-Kunden, die Großelektrosysteme betreiben, sind vollständig dafür verantwortlich, die Einhaltung der NERC CIP-Standards sicherzustellen. Weder Azure noch Azure Government stellt ein BES oder BES Cyber Asset dar.

Zur Einschätzung der Eignung von Azure und Azure Government für Daten und Workloads, die NERC CIP-Standards unterliegen, sollten registrierte Entitäten ihre eigenen Compliance Officer und NERC-Auditoren konsultieren. Sie sollten die [Cloudimplementierungsanleitung für NERC-Überprüfungen](https://aka.ms/AzureNERCGuide) lesen, um Hilfe bei der Dokumentation ihrer Prozesse und Nachweise für die in der Cloud bereitgestellten Objekte zu erhalten.

**Welche Workloads können registrierte Entitäten in Azure und Azure Government bereitstellen?**

Die NERC [CIP-Standards](https://www.nerc.com/pa/Stand/Reliability%20Standards%20Complete%20Set/RSCompleteSet.pdf) und das [Glossar](https://www.nerc.com/pa/Stand/Glossary%20of%20Terms/Glossary_of_Terms.pdf) besagen, dass BES Cyber Assets Echtzeitfunktionen zur Überwachung oder Kontrolle des BES durchführen und bei Beschädigung den zuverlässigen Betrieb des BES innerhalb von 15 Minuten stören würden. Zur ordnungsgemäßen Anpassung von BES Cyber Assets und Protected Cyber Assets an das Cloud Computing müssten bestehende Definitionen in den NERC CIP-Standards [überarbeitet werden](https://www.nerc.com/pa/Stand/Pages/Project%202016-02%20Modifications%20to%20CIP%20Standards.aspx). Allerdings gibt es viele Workloads, die CIP-sensitive Daten betreffen und nicht unter die 15-Minuten-Regel fallen, einschließlich der umfassenden Kategorie der BES Cyber System Information (BCSI).

Das NERC Unternehmen ERO [veröffentlichte](https://www.nerc.com/pa/comp/guidance/Pages/default.aspx) eine Compliance Monitoring and Enforcement Program (CMEP)-[Praxisleitlinie](https://www.nerc.com/pa/comp/guidance/CMEPPracticeGuidesDL/ERO%20Enterprise%20CMEP%20Practice%20Guide%20_%20BCSI%20-%20v0.2%20CLEAN.pdf), welche die CMEP-Mitarbeiter des Unternehmens ERO beim Bewerten des Prozesses einer registrierten Entität zur Autorisierung des Zugriffs auf designierte BCSI-Speicherorte und aller von der registrierten Entität implementierten Zugriffskontrollen anleitet. Darüber hinaus hat NERC die Implementierungsdetails der Azure-Sicherheitskontrollen sowie FedRAMP-Überwachungsnachweise hinsichtlich der Standards NERC CIP-004-6 und CIP-011-2 überprüft, die für BCSI gelten. Basierend auf dem von ERO ausgegebenen Praxisleitfaden und den überprüften FedRAMP-Kontrollen, die sicherstellen sollen, dass registrierte Entitäten ihre Daten verschlüsseln, sind keine zusätzlichen Anleitungen oder Erläuterungen erforderlich, damit registrierte Entitäten BCSI und zugeordnete Workloads in der Cloud bereitstellen können. Allerdings sind registrierte Entitäten letztlich für die Compliance mit NERC CIP-Standards gemäß ihren eigenen Fakten und Gegebenheiten verantwortlich.

## <a name="resources"></a>Ressourcen

- [NERC-Complianceleitfaden](https://www.nerc.com/pa/comp/guidance/)
- [NERC-Compliance und Durchsetzung](https://www.nerc.com/pa/comp/Pages/default.aspx)
- [NERC-Organisation und Zertifizierung](https://www.nerc.com/pa/comp/Pages/Registration.aspx)
- [Microsoft und FedRAMP](offering-fedramp.md)
- Microsoft und CSA STAR-[Nachweis](offering-csa-star-attestation.md) und -[Zertifizierung](offering-csa-star-certification.md)
- [Microsoft und SOC 2-Berichte](offering-soc.md)
- [Compliance im Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)
