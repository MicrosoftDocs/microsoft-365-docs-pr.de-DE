---
title: Health Insurance Portability and Accountability (HIPAA) & HITECH Acts
description: Microsoft bietet HIPAA (Health Insurance Portability & Accountability Act)-Verträge für Geschäftspartner (Business Associate Agreements, BAAs) an.
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
ms.openlocfilehash: 8a7a64532aeb7053572b78a6b05a757bf6d1b006
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44066458"
---
# <a name="health-insurance-portability-and-accountability-hipaa--hitech-acts"></a>Health Insurance Portability and Accountability (HIPAA) & HITECH Acts

## <a name="hipaa-and-the-hitech-act-overview"></a>HIPAA und der HITECH Act (Übersicht)

Der Health Insurance Portability and Accountability Act (HIPAA) ist ein US-Gesundheitsgesetz, das Anforderungen für die Nutzung, Offenlegung und Wahrung individuell identifizierbarer Gesundheitsinformationen festlegt. Sie gilt für erfasste Entitäten – Ärzte Büros, Krankenhäuser, Krankenversicherer und andere Gesundheitsunternehmen – mit Zugriff auf geschützte Integritätsinformationen von Patienten (Phi) sowie mit Geschäftspartnern wie Cloud Service und IT-Anbietern, die Phi in Ihrem Auftrag verarbeiten. (Die meisten betroffenen Entitäten führen selbst keine Funktionen wie Anspruchs- oder Datenverarbeitung aus, sondern verlassen sich dafür auf Geschäftspartner.)

Das Gesetz regelt die Nutzung und Verbreitung von PHI in vier allgemeinen Bereichen:

- Datenschutz, der die Vertraulichkeit der Patientendaten abdeckt.
- Sicherheit, die den Schutz von Informationen einschließlich physischer, technischer und administrativer Sicherheitsvorkehrungen betrifft.
- Bezeichner, welche die Informationstypen darstellen, die nicht freigegeben werden können, wenn sie für Forschungszwecke gesammelt wurden.
- Codes für die elektronische Übermittlung von Daten in mit dem Gesundheitswesen zusammenhängenden Transaktionen, einschließlich Berechtigungs- und Versicherungsansprüchen und Zahlungen.

Der Umfang von HIPAA wurde durch den Erlass des HITECH Act (Health Information Technology for Economic and Clinical Health) erweitert. Die Regeln von HIPAA und dem HITECH Act umfassen insgesamt:

- Die HIPAA-Datenschutzregel, die sich auf das Recht von Einzelpersonen zur Kontrolle der Verwendung ihrer persönlichen Daten konzentriert und die Vertraulichkeit von PHI abdeckt und deren Nutzung und Offenlegung einschränkt.
- Die HIPAA-Sicherheitsregel, mit der die Standards für administrative, technische und physische Sicherheitsmaßnahmen festgelegt werden, um elektronische PHI vor unbefugtem Zugriff, Nutzung und Offenlegung zu schützen. Er umfasst auch solche organisatorischen Anforderungen wie Verträge für Geschäftspartner (Business Associate Agreements, BAAs).

Die endgültige Richtlinie zur Benachrichtigung bei HITECH-Verletzungen (HITECH Breach Notification Final Rule), welche die Benachrichtigung von Einzelpersonen und Behörden erfordert, wenn eine Sicherheitsverletzung unsicherer PHI eintritt.

## <a name="microsoft-and-hipaa-and-the-hitech-act"></a>Microsoft und HIPAA sowie der HITECH Act

Die HIPAA-Bestimmungen erfordern, dass betroffene Unternehmen und deren Geschäftspartner – in diesem Fall Microsoft, wenn es Dienste einschließlich Clouddiensten für betroffene Unternehmen bereitstellt – Verträge abschließen, um sicherzustellen, dass diese Geschäftspartner PHI angemessen schützen. Diese Verträge oder Baas klären und begrenzen, wie der Geschäftspartner Phi verarbeiten kann, und legen jede Partei fest, welche Sicherheits-und Datenschutzbestimmungen in HIPAA und im HITECH Act dargelegt sind. Sobald eine Baa vorhanden ist, können Microsoft-Kunden – verdeckte Entitäten – ihre Dienste zum Verarbeiten und Speichern von Phi verwenden.

Derzeit gibt es keine offizielle Zertifizierung für HIPAA- oder HITECH Act-Compliance. Allerdings wurden für die im BAA abgedeckten Microsoft-Dienste Audits für die ISO/IEC 27001-Zertifizierung von Microsoft durch akkreditierte, unabhängige Prüfer durchgeführt.

Microsoft Enterprise Cloud-Dienste sind auch durch FedRAMP-Bewertungen abgedeckt. Microsoft Azure und Microsoft Azure Government haben eine „Provisional Authority to Operate“ vom FedRAMP Joint Authorization Board erhalten. Dynamics 365 U.S. Government erhielt eine „Agency Authority to Operate“ vom US Department of Housing and Urban Development (US-Ministerium für Wohnungsbau und städtische Entwicklung), ebenso wie Microsoft Office 365 U.S. Government vom US Department of Health and Human Services (US-Gesundheitsministerium).

Wenn Sie erfahren möchten, wie die Microsoft-Cloud Kunden dabei unterstützt, HIPAA und die HITECH-Anforderungen zu erfüllen, besuchen Sie die [Microsoft-Kundenreferenzen](https://customers.microsoft.com).

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft Cloud Services im Leistungsumfang

- [Azure und Azure Government](https://aka.ms/AzureCompliance)
- Cloud-App-Sicherheit
- Microsoft Health Bot Service
- Microsoft Stream
- Microsoft Professional Services: Premier und On-Premises für Azure, Dynamics 365, Intune und Medium Business- und Enterprise-Kunden von Microsoft 365 for Business
- [Dynamics 365 und Dynamics 365 U.S. Government](https://aka.ms/d365-compliance-list)
- Microsoft Flow-Clouddienst als eigenständiger Dienst oder in einem firmenspezifischen Office 365- oder Dynamics 365-Plan bzw. einer -Anwendungssuite enthalten
- Intune
- [Office 365, Office 365 U.S. Government, Office 365 U.S. Government Defense](https://go.microsoft.com/fwlink/p/?LinkID=2077751)
- PowerApps-Clouddienst als eigenständiger Dienst oder in einem firmenspezifischen Office 365- oder Dynamics 365-Plan oder einer -Anwendungssuite enthalten
- Power BI-Clouddienst entweder als eigenständiger Dienst oder als Bestandteil eines Plans oder einer Suite von Office 365 oder Dynamics 365 mit Branding
- Azure DevOps Services

## <a name="accelerate-your-deployment-of-hipaahitrust-solutions-on-azure"></a>Beschleunigen Sie die Bereitstellung von HIPAA/HITRUST-Lösungen auf Azure

Nutzen Sie die Vorteile der Cloud für Gesundheitsdatenlösungen mit der Azure-Blaupause für Sicherheit und Compliance – HIPAA/HITRUST-Gesundheitsdaten und AI. Diese Blaupause bietet Tools und Anleitungen, die Ihnen bei den ersten Schritten der Erstellung von HIPAA/HITRUST-Lösungen helfen.

[Beginnen Sie mit der Verwendung der Azure HIPAA/HITRUST-Blaupause](https://docs.microsoft.com/azure/governance/blueprints/samples/hipaa-hitrust/)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Kann meine Organisation einen Vertrag für Geschäftspartner (BAA) mit Microsoft eingehen?**

Microsoft bietet qualifizierten Unternehmen oder deren Lieferanten ein BAA, das zum Umfang gehörige Microsoft-Dienste abdeckt.

Für Microsoft-Clouddienste: Der [HIPAA-Vertrag für Geschäftspartner](https://aka.ms/BAA) wird standardmäßig über die Nutzungsbedingungen für Onlinedienste für alle Kunden zur Verfügung gestellt, die unter die HIPAA fallende Entitäten oder Geschäftspartner sind. Eine Liste der Clouddienste, die von diesem BAA abgedeckt werden, finden Sie auf dieser Website unter „Microsoft Cloud Services im Leistungsumfang“.

Für Microsoft Professional Services-Dienste: Der HIPAA-Vertrag für Geschäftspartner (BAA) ist für Microsoft Professional-Dienste im Leistungsumfang auf Anforderung bei Ihrem Vertreter für die Microsoft-Dienste verfügbar.

**Ist es mit einer Baa mit Microsoft sichergestellt, dass die Compliance meines Unternehmens mit dem HIPAA und dem HITECH Act übereinstimmt?**

Nein. Durch die Bereitstellung eines BAA hilft Microsoft, Ihre HIPAA-Compliance zu unterstützen, aber durch die Verwendung von Microsoft-Diensten allein wird diese nicht erreicht. Ihre Organisation ist dafür verantwortlich, sicherzustellen, dass Sie über ein adäquates Compliance-Programm und entsprechende interne Prozesse verfügen und dass Ihre besondere Verwendung von Microsoft-Diensten HIPAA und dem HITECH Act entspricht.

**Kann Microsoft die Baa meiner Organisation ändern?**

Microsoft kann den HIPAA BAA nicht ändern, da die Microsoft-Dienste für alle Kunden einheitlich sind und daher für alle Benutzer dieselben Verfahren ausgeführt werden müssen. Um jedoch die Baa für Microsofts HIPAA-regulierte Kunden und deren Dienste zu erstellen, arbeitete Microsoft mit einigen der führenden US Medical Schools und ihren HIPAA-Datenschutzrichtlinien sowie anderen öffentlichen und privaten HIPAA-bezogenen Entitäten zusammen.

**Wie kann ich Kopien der Berichte des Auditors erhalten?**

Das [Vertrauensstellungsportal](https://www.microsoft.com/trustcenter/STP/default.aspx) stellt unabhängig geprüfte Complianceberichte zur Verfügung. Sie können über das Portal Prüfberichte anfordern, sodass Ihre Prüfer die Ergebnisse der Clouddienste von Microsoft mit Ihren eigenen gesetzlichen und regulatorischen Anforderungen vergleichen können.

**Wie kann ich mehr über die Einhaltung von HIPAA und dem HITECH Act erfahren?**

Um Kunden bei dieser Aufgabe zu unterstützen, hat Microsoft die folgenden Leitfäden veröffentlicht:

- *HIPAA/HITECH Act-Implementierungsleitfaden* für [Azure](https://aka.ms/azurehipaaguidance) und für [Dynamics 365 und Office 365](https://go.microsoft.com/fwlink/?LinkID=257510). Verfasst für Datenschutz-, Sicherheits- und Compliance-Beauftragte sowie andere, die für die HIPAA- und HITECH Act-Implementierung verantwortlich sind. Es werden konkrete Schritte beschrieben, die Ihr Unternehmen zur Einhaltung der Compliance ausführen kann.
- [Praktischer Leitfaden zum Entwerfen von sicheren Gesundheitslösungen mit Microsoft Azure](https://aka.ms/azureindustrysecurity) hilft Ihnen, besser zu verstehen, was für die erfolgreiche, sichere Einführung eines Clouddiensts nötig ist.
- [Die Behandlung der HIPAA-Sicherheits- und Datenschutzanforderungen in der Microsoft-Cloud](https://smb.blob.core.windows.net/smbproduction/Content/Microsoft_Cloud_Healthcare_HIPAA_Security_Privacy.pdf) bietet einen kurzen Überblick über die Vorschriften. Außerdem wird eine detaillierte Analyse der Funktionsweise von Cloud-Diensten von Microsoft mit Methoden erstellt, die diesen Anforderungen entsprechen, sowie Anleitungen zum Erstellen von Compliance-fähigen Lösungen.

## <a name="use-microsoft-compliance-score-to-assess-your-risk"></a>Verwenden von Microsoft Compliancebewertungen zur Einschätzung des Risikos

[Microsoft Compliancebewertung](compliance-score.md) ist ein Preview-Feature im [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md), das Ihnen dabei hilft, den Compliance-Status Ihrer Organisation zu bestimmen und Maßnahmen zur Senkung von Risiken zu ergreifen. Verwenden Sie nach dem [Einrichten der Compliancebewertung](compliance-score-setup.md) die vorkonfigurierte [HIPAA Office 365-Vorlage](https://go.microsoft.com/fwlink/?linkid=2118005) und die [HIPAA Intune-Vorlage](https://go.microsoft.com/fwlink/?linkid=2118006) aus dem Dropdownmenü **Vorlage**, um Ihrer Organisation zu helfen, die Anforderungen dieser Verordnung zu erfüllen.

## <a name="resources"></a>Ressourcen

- [HIPAA Omnibus-Regel](https://aka.ms/HIPAA-omnibus) (Die endgültigen Bestimmungen ändernden HIPAA-Regeln)
- [Microsoft Common Controls Hub-Complianceframework](https://www.microsoft.com/trustcenter/common-controls-hub)
- [Nutzungsbedingungen für Microsoft-Onlinedienste](https://aka.ms/Online-Services-Terms)
- [Microsoft Government Cloud](https://go.microsoft.com/fwlink/p/?linkid=2087246)
- [Grundlegendes zur HIPAA-Compliance mit Azure](https://www.youtube.com/embed/6ptdye1LZ5k?autoplay=0)(19. Mai 2016)
- [Azure HIPAA-Implementierungsleitfaden](https://aka.ms/azure-hipaa-guide)
- [Compliance im Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)
