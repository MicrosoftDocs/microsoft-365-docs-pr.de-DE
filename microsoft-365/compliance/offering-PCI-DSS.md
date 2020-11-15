---
title: Payment Card Industry (PCI) Data Security Standard (DSS)
description: Azure, SharePoint Online und OneDrive for Business erfüllen die Payment Card Industry Data Security Standards der Stufe 1, Version 3.2.
keywords: Microsoft 365, Compliance, Angebote
localization_priority: Priority
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
ms.openlocfilehash: cb4d1a4c4632763506fd2d3b05431acb9233f744
ms.sourcegitcommit: d333d82fd5e4f3265e8b9372094e85875bee6fe5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49071963"
---
# <a name="payment-card-industry-pci-data-security-standard-dss"></a>Payment Card Industry (PCI) Data Security Standard (DSS)

## <a name="pci-dss-overview"></a>PCI DSS – Überblick

Der PCI-Datensicherheitsstandard (PCI DSS – Payment Card Industry Data Security Standards) ist ein globaler Informationssicherheitsstandard, der Betrug durch eine verstärkte Kontrolle von Kreditkartendaten verhindern soll. Unternehmen jeder Größe müssen die PCI DSS-Standards einhalten, wenn sie Zahlungskarten der fünf wichtigsten Kreditkartenmarken – Visa, MasterCard, American Express, Discover und JCB (Japan Credit Bureau) – akzeptieren. Die Einhaltung von PCI DSS ist für jede Organisation obligatorisch, die Zahlungs- und Karteninhaberdaten speichert, verarbeitet oder überträgt.

## <a name="microsoft-and-pci-dss"></a>Microsoft und PCI DSS

Microsoft hat eine jährliche PCI-DSS-Bewertung mit einem zugelassenen qualifizierten Sicherheitsassessor (QSA – Qualified Security Assessor) durchgeführt. Die Auditoren überprüften die Umgebungen von Microsoft Azure, Microsoft OneDrive for Business und Microsoft SharePoint Online, einschließlich der Überprüfung von Infrastruktur, Entwicklung, Betrieb, Management, Support und eingeschlossene Dienste. PCI DSS legt basierend auf dem Transaktionsvolumen vier Compliance-Ebenen fest. Azure, OneDrive for Business und SharePoint Online sind gemäß PCI DSS Version 3.2 als Dienstleister der Ebene 1 (mit höchstem Transaktionsvolumen von mehr als 6 Millionen pro Jahr) konform zertifiziert.

Die Bewertung führt zu einer Konformitätsbescheinigung (AoC – Attestation of Compliance), die für Kunden einsehbar ist, und einem vom Assessor (QSA) herausgegebenen Bericht über die Konformität (RoC – Report on Compliance). Der Gültigkeitszeitraum der Compliance beginnt mit dem Bestehen des Audits und dem Erhalt der AoC vom Assessor und endet ein Jahr nach dem Datum der Unterzeichnung der AoC. 

Kunden, die eine Umgebung für Karteninhaber oder einen Kartenverarbeitungsdienst entwickeln möchten, können diese Zertifizierung in vielen der zugrunde liegenden Bereiche verwenden, wodurch sich der Aufwand und die Kosten für die Erlangung der eigenen PCI DSS-Zertifizierung verringern.

Es ist wichtig zu verstehen, dass der PCI DSS-Compliance-Status für Azure, OneDrive for Business und SharePoint Online nicht automatisch die PCI DSS-Zertifizierung für die Dienstleistungen bedeutet, welche Kunden auf diesen Plattformen erstellen oder hosten. Die Kunden sind dafür verantwortlich, dass sie die PCI DSS-Anforderungen gesamtheitlich erfüllen.

## <a name="microsoft-in-scope-cloud-services"></a>Eingeschlossene Microsoft-Clouddienste

- [Azure und Azure Government](https://azure.microsoft.com/global-infrastructure/government/)
- Microsoft Cloud App Security
- Flow Cloud-Dienst entweder als eigenständiger Dienst oder als Bestandteil eines Plans oder einer Suite von Office 365 oder Dynamics 365
- Microsoft Graph
- Intune
- [Microsoft Defender für Endpunkt](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- PowerApps-Clouddienst als eigenständigen Dienst oder in einem firmenspezifischen Office 365- oder Dynamics 365-Plan bzw. -Anwendungssuite enthalten
- Power BI-Clouddienst entweder als eigenständiger Dienst oder als Bestandteil eines Office 365-Plans oder -Suite
- OneDrive for Business und SharePoint Online (nur Vereinigte Staaten)

## <a name="audit-reports-and-certificates"></a>Audit, Berichte und Zertifikate

- [Azure PCI DSS Attestation of Compliance (AoC)](https://aka.ms/azure-pci)
- [OneDrive for Business and SharePoint Online PCI DSS Attestation of Compliance (AoC)](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a>Bringen Sie Ihre PCI DSS-Lösung in Azure zum Laufen

Erstellen und Implementieren Sie Ihre PCI DSS-Lösung in der Cloud noch schneller mit dem PCI DSS-Blueprint von Azure Security and Compliance. Erhalten Sie Referenzarchitekturen, Anleitungen zur Implementierung, Steuerungsimplementierungszuordnungen, automatisierte Skripts und mehr. [Starten Sie mit der Verwendung des Azure PCI DSS-Blueprint](https://aka.ms/pciblueprint).

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Warum steht auf dem Deckblatt der Konformitätsbescheinigung (AoC – Attestation of Compliance) „Juni 2018“?**

Die AoC-Vorlage wurde im Juni 2018 veröffentlicht. Das eigentliche Datum der Beurteilung finden Sie im Abschnitt 2.

**Warum gibt es mehrere Konformitätsbescheinigungen (AoCs) für Azure?**

Das Azure AoC-Paket enthält Konformitätsbescheinigungen für Azure Public, Deutschland und die Government Cloud. Kunden sollten den AoC verwenden, der ihrer Azure-Umgebung entspricht.  

**Welche Beziehung besteht zwischen PA DSS und PCI DSS?**

Der Datensicherheitsstandard für Zahlungsanwendungen (PA DSS – Payment Application Data Security Standard) stellt eine Reihe von Anforderungen dar, die PCI DSS entsprechen. Er ersetzt die „Payment Application Best Practices“ (Bewährte Methoden für die Entwicklung von Zahlungsanwendungen) von Visa und konsolidiert die Compliance-Anforderungen der anderen primären Kartenherausgeber. Der PA DSS unterstützt Softwarelieferanten bei der Entwicklung von Drittanbietern-Anwendungen, die Zahlungsdaten von Karteninhabern als Teil der Kartenautorisierung oder des Abrechnungsprozesses speichern, verarbeiten oder übertragen. Einzelhändler sollten PA DSS-zertifizierte Anwendungen verwenden, um ihre PCI DSS-Compliance effizient zu erreichen. Der PA DSS gilt nicht für Azure.

**Was ist ein Acquirer und setzt Azure einen solchen ein?**

Ein Acquirer ist eine Bank oder ein anderes Unternehmen, das Zahlungskartentransaktionen entgegennimmt und verarbeitet. Azure bietet keine Zahlungskartenverarbeitung als Dienstleistung an und benötigt deshalb keinen Acquirer.

**Für welche Unternehmen und Händler gilt der PCI DSS-Standard?**

PCI DSS gilt für jedes Unternehmen, das Karteninhaberdaten akzeptiert, überträgt oder speichert, unabhängig von der Größe oder der Anzahl der Transaktionen. Die PCI-DSS-Anforderungen gelten also, sobald ein Kunde ein Unternehmen mit einer Kredit- oder Debitkarte bezahlt. Unternehmen werden auf einer von vier Stufen validiert, basierend auf dem gesamten Transaktionsvolumen über einen Zeitraum von 12 Monaten. Die Stufe 1 ist für Unternehmen gedacht, die mehr als 6 Millionen Transaktionen pro Jahr abwickeln, die Stufe 2 für 1 bis 6 Millionen Transaktionen, die Stufe 3 für 20 000 bis 1 Million Transaktionen und die Stufe 4 für weniger als 20 000 Transaktionen.

**Wo beginne ich mit den PCI DSS-Compliance-Anstrengungen meines Unternehmens für eine auf Azure bereitgestellte Lösung?**

Die Informationen, die der PCI-Rat für Sicherheitsstandards (PCI SSC – Payment Card Industry Security Standards Council) zur Verfügung stellt, sind ein guter Ort, um sich über spezifische Compliance-Anforderungen zu informieren. Der Rat veröffentlicht die [PCI DSS-Kurzanleitung](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) für Händler und andere an der Verarbeitung von Zahlungskarten Beteiligte. In diesem Handbuch wird erläutert, wie PCI DSS beim Schutz einer Zahlungskartentransaktionsumgebung hilft und wie er angewendet wird. 

Die Compliance umfasst mehrere Faktoren, einschließlich der Bewertung der Systeme und Prozesse, die nicht auf Azure gehostet werden. Die einzelnen Anforderungen hängen davon ab, welche Azure-Dienste verwendet und wie sie in der Lösung eingesetzt sind.

**Gibt es Pläne, OneDrive for Business und SharePoint Online außerhalb der Vereinigten Staaten PCI DSS-konform zu machen?**

Zur Zeit sind OneDrive for Business und SharePoint Online nur in den Vereinigten Staaten (USA) nach PCI-DSS zertifiziert. Microsoft wird die Anforderungen und Zeitpläne für Regionen außerhalb der USA bewerten und Updates bereitstellen, falls andere Regionen zur Roadmap hinzugefügt werden.

**Was ist in OneDrive for Business und SharePoint Online enthalten?**

Derzeit werden nur Dateien und Dokumente, die zu OneDrive for Business und SharePoint Online hochgeladen wurden, mit PCI DSS beanstandet.

## <a name="use-microsoft-compliance-manager-to-assess-your-risk"></a>Verwenden Sie den Microsoft Compliance-Manager, um Ihr Risiko einzuschätzen

Der [Microsoft Compliance-Manager](compliance-manager.md) ist ein Feature im [Microsoft 365 Compliance Center](microsoft-365-compliance-center.md), mit dem Sie die Compliance-Position Ihres Unternehmens verstehen und Maßnahmen zur Risikominderung ergreifen können. Der Compliance Manager bietet eine Premium-Vorlage zum Erstellen einer Bewertung für diese Verordnung. Suchen Sie die Vorlage auf der Seite **Bewertungsvorlagen** im Compliance-Manager. Erfahren Sie, wie Sie [Bewertungen im Compliance-Manager erstellen](compliance-manager-assessments.md).

## <a name="resources"></a>Ressourcen

- [PCI Security Standards Council](https://www.pcisecuritystandards.org/)
- [PCI Data Security Standard](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [Azure PCI DSS 3.2.1 Blueprint](https://docs.microsoft.com/azure/governance/blueprints/samples/pci-dss-3.2.1/)
- [PCI DSS Quick Reference Guide](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [Compliance im Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)
