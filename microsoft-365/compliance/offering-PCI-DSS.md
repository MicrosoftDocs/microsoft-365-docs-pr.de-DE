---
title: Payment Card Industry (PCI) Data Security Standard (DSS)
description: Azure, SharePoint Online und OneDrive for Business erfüllen die Payment Card Industry Data Security Standards der Stufe 1, Version 3.2.
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
ms.openlocfilehash: 1b0e4ae933591f41c99a4b88d31eca6504322c92
ms.sourcegitcommit: b2197dbf723d11992bbad568a84df3ef3cff421d
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/04/2019
ms.locfileid: "39218694"
---
# <a name="compliance-offering-payment-card-industry-pci-data-security-standard-dss"></a>Compliance-Angebot: Payment Card Industry (PCI) Data Security Standard (DSS)

## <a name="pci-dss-overview"></a>PCI DSS – Überblick

Der Payment Card Industry (PCI) Data Security Standards (DSS) ist ein globaler Informationssicherheitsstandard, der Betrug durch verstärkte Kontrolle von Kreditkartendaten verhindern soll. Unternehmen aller Größen müssen den PCI-DSS-Standards folgen, wenn sie Zahlungskarten der fünf wichtigsten Kreditkartenmarken akzeptieren – Visa, MasterCard, American Express, Discover und das Japan Credit Bureau (JCB). Compliance mit den PCI DSS-Standards ist für jedes Unternehmen erforderlich, das Daten von Zahlungen und Karteninhabern speichert, verarbeitet oder überträgt.

## <a name="microsoft-and-pci-dss"></a>Microsoft und PCI DSS

Microsoft hat eine jährliche PCI-DSS-Bewertung mit einem anerkannten Qualified Security Assessor (QSA) durchgeführt. Die Prüfer überprüften Microsoft Azure-, Microsoft OneDrive for Business- und Microsoft SharePoint Online-Umgebungen, in denen die Infrastruktur, die Entwicklung, der Betrieb, die Verwaltung, der Support und die In-Scope-Services überprüft wurden. Der PCI-DSS legt vier Compliance-Ebenen fest, die auf dem Transaktionsvolumen basieren. Azure, OneDrive for Business und SharePoint Online sind gemäß PCI DSS Version 3.2 auf Service Provider Level 1 als konform zertifiziert (das höchste Transaktionsvolumen – mehr als 6 Millionen pro Jahr).

Die Bewertung führt zu einer Attestation of Compliance (AoC), die den Kunden zur Verfügung steht, und einem vom QSA herausgegebenen Bericht über die Konformität (RoC). Die effektive Frist für die Einhaltung beginnt mit dem Bestehen des Audits und dem Erhalt der AoC vom Assessor und endet ein Jahr ab dem Datum der Unterzeichnung der AoC. 

Kunden, die eine Umgebung für Karteninhaber oder einen Kartenverarbeitungsdienst entwickeln möchten, können diese Zertifizierung in vielen der zugrunde liegenden Bereiche verwenden, wodurch sich der Aufwand und die Kosten für die Erlangung einer eigenen PCI-DSS-Zertifizierung verringern.

Es ist wichtig zu verstehen, dass der PCI-DSS-Kompatibilitätsstatus für Azure, OneDrive for Business und SharePoint Online nicht automatisch in eine PCI-DSS-Zertifizierung für die Dienste übersetzt wird, die Kunden auf diesen Plattformen erstellen oder hosten. Kunden sind dafür verantwortlich, dass sie die Compliance mit den PCI-DSS-Anforderungen erfüllen.

## <a name="microsoft-in-scope-cloud-services"></a>In-Scope-Cloud-Dienste von Microsoft

- [Azure und Azure Government](https://aka.ms/AzureCompliance)
- Cloud App Security
- Flow Cloud-Dienst entweder als eigenständiger Dienst oder als Bestandteil eines Plans oder einer Suite von Office 365 oder Dynamics 365
- Graph
- Intune
- Der PowerApps-Clouddienst ist entweder als eigenständiger Dienst oder als Bestandteil eines Plans oder einer Suite von Office 365 oder Dynamics 365 verfügbar
- Power BI-Clouddienst entweder als eigenständiger Dienst oder als Bestandteil eines Office 365-Plans oder -Suite
- OneDrive for Business und SharePoint Online (nur Vereinigte Staaten)

## <a name="audit-reports-and-certificates"></a>Audit, Berichte und Zertifikate

- [Azure PCI DSS Attestation of Compliance (AoC)](https://aka.ms/azure-pci)
- [OneDrive for Business and SharePoint Online PCI DSS Attestation of Compliance (AoC)](https://aka.ms/spo-pci)

## <a name="get-your-pci-dss-solution-running-on-azure"></a>Führen Sie Ihre PCI-DSS-Lösung in Azure aus

PCI-DSS-Lösung mit dem PCI-DSS-Blueprint von Azure Security and Compliance noch schneller in der Cloud erstellen und bereitstellen. Erhalten Sie Referenzarchitekturen, Anleitungen zur Bereitstellung, steuern Sie Implementierungszuordnungen, automatisierte Skripts und vieles mehr. [Beginnen Sie mit der Verwendung des Azure PCI DSS Blueprint](https://aka.ms/pciblueprint)

## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

**Warum steht auf dem Deckblatt der Attestation of Compl (AoC) „Juni 2018“?**

Das Datum Juni 2018 auf dem Deckblatt ist der Zeitpunkt, an dem die AoC-Vorlage veröffentlicht wurde. Das Datum der Bescheinigung können Sie dem Abschnitt 2 entnehmen.

**Warum gibt es zwei Azure Attestations of Compliance (AoCs)?**

Das Azure AoC-Paket enthält AoCs für Azure Public, Deutschland und Government Cloud. Kunden sollten den AoC verwenden, der ihrer Azure-Umgebung entspricht.  

**Welche Beziehung besteht zwischen PA DSS und PCI DSS?**

Der Payment Application Data Security Standard (PA DSS) enthält eine Reihe von Anforderungen, die mit dem PCI DSS übereinstimmen. Er ersetzt die Best Practices von Visa für Zahlungsanwendungen und konsolidiert die Compliance-Anforderungen der anderen primären Kartenaussteller. Der PA DSS unterstützt Softwareanbieter bei der Entwicklung von Anwendungen von Drittanbietern, die im Rahmen eines Kartenautorisierungs- oder Abrechnungsprozesses Zahlungsdaten von Karteninhabern speichern, verarbeiten oder übertragen. Einzelhändler müssen nach PA DSS zertifizierte Anwendungen verwenden, um Compliance mit PCI DSS wirksam zu erreichen. Der PA DSS gilt nicht für Azure.

**Was ist ein Acquirer und setzt Azure einen solchen ein?**

Ein Acquirer ist eine Bank oder ein anderes Unternehmen, das Zahlungskartentransaktionen abwickelt. Azure bietet die Verarbeitung von Zahlungskarten nicht als Dienst an und setzt daher keinen Acquirer ein.

**Für welche Organisationen und Händler gilt der PCI DSS-Standard?**

PCI DSS gilt für jedes Unternehmen, unabhängig von der Größe oder Anzahl der Transaktionen, das Karteninhaberdaten akzeptiert, überträgt oder speichert. Das heißt, wenn ein Kunde jemals ein Unternehmen mit einer Kredit- oder Debitkarte bezahlt, gelten die PCI-DSS-Anforderungen. Unternehmen werden auf einer von vier Ebenen basierend auf dem Gesamttransaktionsvolumen über einen Zeitraum von 12 Monaten validiert. Level 1 ist für Unternehmen gedacht, die mehr als 6 Millionen Transaktionen pro Jahr abwickeln. Level 2 für 1 Million bis 6 Millionen Transaktionen; Level 3 gilt für 20.000 bis 1 Million Transaktionen und Level 4 für weniger als 20.000 Transaktionen.

**Wo beginne ich mit den PCI DSS-Compliance-Anstrengungen meiner Organisation für eine auf Azure bereitgestellte Lösung?**

Die Informationen, die der PCI Security Standards Council zur Verfügung stellt, geben Aufschluss über die spezifischen Complianceanforderungen. Der Rat veröffentlicht den [PCI DSS Quick Reference Guide](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf) für Händler und andere an der Verarbeitung von Zahlungskarten beteiligte Personen. In diesem Handbuch wird erläutert, wie der PCI-DSS zum Schutz einer Zahlungskartentransaktionsumgebung beitragen kann und wie er angewendet wird.

Die Compliance umfasst mehrere Faktoren, einschließlich das Bewerten der Systeme und Prozesse, die nicht in Azure gehostet werden. Die einzelnen Anforderungen hängen davon ab, welche Azure-Dienste verwendet werden und wie sie in der Lösung verwendet werden.

**Gibt es Pläne, damit OneDrive for Business und SharePoint Online außerhalb der Vereinigten Staaten PCI DSS-konform sind?**

Derzeit ist OneDrive for Business und SharePoint Online nur in den Vereinigten Staaten PCI-DSS-kompatibel. Microsoft bewertet die Anforderungen und Zeitpläne für Regionen außerhalb der Vereinigten Staaten und stellt Updates bereit, wenn und wenn andere Regionen zur Roadmap hinzugefügt werden.

**Was ist in OneDrive for Business und SharePoint Online enthalten?**

Derzeit werden nur Dateien und Dokumente, die zu OneDrive for Business und SharePoint Online hochgeladen wurden, mit PCI DSS beanstandet.

## <a name="resources"></a>Ressourcen

- [PCI Security Standards Council](https://www.pcisecuritystandards.org/)
- [PCI Data Security Standard](https://www.pcisecuritystandards.org/documents/PCI_DSS_v3-1.pdf)
- [Azure PCI DSS 3.2.1 Verantwortlichkeitsmatrix](https://aka.ms/pciresponsibilitymatrix)
- [PCI DSS Quick Reference Guide](https://www.pcisecuritystandards.org/documents/PCISSC%20QRG%20August%202014%20-print.pdf)
- [Compliance im Microsoft Trust Center](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>Hintergrundinformationen zum Angebot herunterladen

Benötigen Sie das Dokument mit Hintergrundwissen für dieses Angebot? Laden Sie die [PDF-Datei](https://download.microsoft.com/download/3/7/7/377F1BBC-37D5-4677-AB4A-7C01D089CA67/PCI_DSS_Compliance_Backgrounder.pdf) herunter.
