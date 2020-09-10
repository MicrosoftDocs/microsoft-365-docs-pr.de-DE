---
title: NIST SP 800 – 171
description: Microsoft-Cloud-Dienste entsprechen den NIST-SP 800 – 171-Richtlinien, um kontrollierte nicht klassifizierte Informationen (CUI) in nicht föderalen Informationssystemen zu schützen.
keywords: Microsoft 365, Compliance, Angebote
localization_priority: None
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 757541aa86049106ad06f02419fee02033c6a0e3
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47417067"
---
# <a name="nist-sp-800171"></a>NIST SP 800 – 171

## <a name="about-nist-sp-800171"></a>Informationen zu NIST SP 800 – 171

Das US National Institute of Standards and Technology (NIST) fördert und unterhält Mess Standards und Richtlinien, die zum Schutz der Informations-und Informationssysteme von Bundesbehörden beitragen. Als Reaktion auf den Executive Order 13556 zum Verwalten von kontrollierten nicht klassifizierten Informationen (CUI) veröffentlicht er [NIST SP 800 – 171](https://csrc.nist.gov/publications/detail/sp/800-171/rev-1/final)und *schützt kontrollierte nicht klassifizierte Informationen in nicht föderalen Informationssystemen und Organisationen*. Cui ist definiert als Information – sowohl Digital als auch physisch – erstellt von einer Regierung (oder einer Entität in Ihrem Namen), die zwar nicht klassifiziert ist, noch vertraulich ist und Schutz erfordert.

NIST SP 800 – 171 wurde ursprünglich im Juni 2015 veröffentlicht und wurde seither als Reaktion auf die Entwicklung von Bedrohungen mehrmals aktualisiert. Sie enthält Richtlinien für die sichere Zugänglichkeit, Übertragung und Speicherung von Cui in nicht föderalen Informationssystemen und Organisationen. die Anforderungen fallen in vier Hauptkategorien:

- Steuerelemente und Prozesse für die Verwaltung und den Schutz
- Überwachung und Verwaltung von IT-Systemen
- Clear Practices and Procedures for End Users
- Implementierung technischer und physikalischer Sicherheitsmaßnahmen

## <a name="microsoft-and-nist-sp-800171"></a>Microsoft und NIST SP 800 – 171

Akkreditierte Drittanbieter-Assessment-Organisationen, Kratos Secureinfo und Coalfire, die mit Microsoft zusammenarbeiten, um zu bestätigen, dass die in-Scope-Cloud-Dienste die Kriterien in NIST SP 800 – 171 erfüllen, die *kontrollierte nicht klassifizierte Informationen (CUI) in nicht föderalen Informationssystemen und Organisationen schützen*, wenn Sie Cui verarbeiten. Die [Microsoft-Implementierung von FedRAMP](offering-fedramp.md) -Anforderungen stellt sicher, dass die Microsoft-bezogenen Cloud-Dienste die Anforderungen von NIST SP 800 – 171 erfüllen oder überschreiten, wenn Sie die vorhandenen Systeme und Vorgehensweisen verwenden.

NIST SP 800 – 171 Anforderungen sind eine Teilmenge von NIST SP 800-53, dem Standard, den FedRAMP verwendet. Anhang D von NIST SP 800 – 171 stellt eine direkte Zuordnung seiner Cui-Sicherheitsanforderungen zu den relevanten Sicherheitskontrollen in NIST SP 800-53 dar, für die die in-Scope-Cloud-Dienste bereits im Rahmen des FedRAMP-Programms geprüft und autorisiert wurden.

Jede Entität, die die US-Regierung Cui verarbeitet oder speichert – Forschungseinrichtungen, Beratungsunternehmen, Fertigungsunternehmen – muss den strengen Anforderungen von NIST SP 800 – 171 entsprechen. Diese Bestätigung bedeutet, dass Microsoft-basierte Cloud-Dienste Kunden bei der Bereitstellung von Cui-Arbeitsauslastungen mit der Gewissheit unterstützen können, dass Microsoft die vollständige Compliance vorsieht. Beispielsweise erfüllen alle DoD-Auftragnehmer, die "abgedeckte Verteidigungsinformationen" mit in-Scope-Microsoft Cloud-Diensten in ihren Informationssystemen verarbeiten, speichern oder übertragen, die DFARS-Klauseln des US-Verteidigungsministeriums, die die Einhaltung der Sicherheitsanforderungen von NIST SP 800 – 171 erfordern.

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft Cloud Services im Leistungsumfang

- [Azure-Regierung](https://aka.ms/AzureCompliance)
- [Dynamics 365 U.S. Government](https://aka.ms/d365-compliance-list)
- Intune
- [Office 365 US Government Community Cloud (gcc), Office 365 gcc High und DoD](https://aka.ms/o365-compliance-framework)

## <a name="audits-reports-and-certificates"></a>Audits, Berichte und Zertifikate

- [Azure Government Bescheinigung über die Einhaltung von NIST SP 800 – 171](https://aka.ms/Azure-NIST-800-171)

## <a name="how-to-implement"></a>Implementierung

- [Azure Blueprint-Beispiele](https://docs.microsoft.com/azure/governance/blueprints/samples/): erhalten Sie Unterstützung für die Implementierung von Arbeitsauslastungen, die NIST-basierten Steuerelementen entsprechen.

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Kann ich die Microsoft-Konformität mit NIST SP 800 – 171 für meine Organisation verwenden?**

Ja. Microsoft-Kunden können die überwachten Steuerelemente, die in den Berichten unabhängiger Drittanbieter-Assessment-Organisationen (3PAO) für FedRAMP-Standards beschrieben werden, als Teil ihrer eigenen FedRAMP-und NIST-Risikoanalyse-und Qualifizierungsmaßnahmen verwenden. Diese Berichte bestätigen die Effektivität der Steuerelemente, die von Microsoft in seinen in-Scope-Cloud-Diensten implementiert wurden. Kunden sind dafür verantwortlich sicherzustellen, dass Ihre Cui-Arbeitslasten den NIST-SP 800 – 171-Richtlinien entsprechen.

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a>Verwenden von Microsoft Compliancebewertungen zur Einschätzung des Risikos

[Microsoft Compliancebewertung](compliance-score.md) ist ein Preview-Feature im [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md), das Ihnen dabei hilft, den Compliance-Status Ihrer Organisation zu bestimmen und Maßnahmen zur Senkung von Risiken zu ergreifen. Nachdem Sie die [Kompatibilitätsbewertung eingerichtet](compliance-score-setup.md)haben, wählen Sie die vorkonfigurierte [NIST 800-171-Vorlage](https://go.microsoft.com/fwlink/?linkid=2117526) aus dem Dropdownmenü **Vorlage** aus, damit Ihre Organisation die Anforderungen für diese Verordnung erfüllt.

## <a name="resources"></a>Ressourcen

- [Microsoft DoD-Zertifizierung erfüllt NIST 800 – 171 Anforderungen](offering-DoD-DISA-L2-L4-L5.md)
- [NIST 800 – 171 Compliance beginnt mit der Cyber-Dokumentation](https://www.nist800171.com/)
- [FedRAMP-Autorisierungen für Microsoft Cloud Services](https://marketplace.fedramp.gov/index.html?status=Compliant&sort=productName#/products)
- [NIST 800-171 3,3 Audit und Verantwortlichkeit mit Office 365 gcc hoch](https://info.summit7systems.com/blog/nist-3.3-audit-and-accountability-with-office-365)
- [Microsoft und das NIST-Cyber-Framework](offering-nist-csf.md)
- [Microsoft Government Cloud](https://www.microsoft.com/enterprise/government)
- [Compliance im Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)
