---
title: 'Schritt 2: Konfigurieren der Klassifizierung für Ihre Umgebung'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren verschiedener Methoden zum Klassifizieren von Daten in Ihrer Organisation.
ms.openlocfilehash: ca64b98bceb6f969adc964e93a6a1cc872763199
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32286974"
---
# <a name="step-2-configure-classification-for-your-environment"></a>Schritt 2: Konfigurieren der Klassifizierung für Ihre Umgebung

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

In diesem Schritt arbeiten Sie mit der Rechts- und Complianceabteilung zusammen, um ein Klassifizierungsschema für die Daten in Ihrer Organisation zu erstellen.

## <a name="microsoft-365-classification-types"></a>Microsoft 365 Klassifizierungstypen

Microsoft 365 umfasst vier Typen von Klassifizierung:

- Typen vertraulicher Informationen
- Aufbewahrungsbezeichnungen
- Vertraulichkeitsbezeichnungen
- Bezeichnungen und Schutz in Azure Information Protection

### <a name="sensitive-information-types"></a>Typen vertraulicher Informationen

Typen vertraulicher Informationen für Microsoft 365 definieren, wie automatisierte Prozesse wie z. B. „Suche“ bestimmte Informationstypen erkennen. Dazu gehören sensible Mitarbeiter- oder Kundendaten wie Nummern des Gesundheitsdiensts und Kreditkartennummern. Sie verwenden die Typen sensibler Informationen, um sensible Daten zu finden und wenden DLP-Regeln und Richtlinien zum Schutz dieser Daten an. Weitere Informationen finden Sie unter [Was eine DLP-Richtlinie enthält](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies#what-a-dlp-policy-contains). 

Typen vertraulicher Informationen sind besonders hilfreich, um Compliance- und Regulierungsanforderungen zu erfüllen, wie zum Beispiel die Datenschutz-Grundverordnung  (DSGVO).

### <a name="retention-labels"></a>Aufbewahrungsbezeichnungen

Ein Teil der Definition einer Datenkontrolle-Strategie ist die Entscheidung, wie lange bestimmte Arten von Dokumenten oder Dokumente mit bestimmten Inhalten in Übereinstimmung mit den Organisationsrichtlinien und regionalen Vorschriften aufbewahrt werden sollen. Beispielsweise sollten einige Arten von Dokumenten für eine bestimmte Zeit aufbewahrt und dann gelöscht werden, während andere auf unbestimmte Zeit aufbewahrt werden müssen.

Für Dokumente, die in Microsoft 365 gespeichert sind, definieren und wenden Sie Aufbewahrungsbezeichnungen auf Dokumente und Daten an, die in Exchange-E-Mails, SharePoint Online, OneDrive for Business und Teams gespeichert sind. Weitere Informationen, einschließlich wie Sie diese erstellen können, finden Sie unter [Übersicht der Aufbewahrungsbezeichnungen](https://docs.microsoft.com/office365/securitycompliance/labels).

Wenn Sie Aufbewahrungsbezeichnungen verwenden, sollten Sie für jede Kategorie von Dateien, für die eine Aufbewahrungsrichtlinie angewendet werden muss, eine Bezeichnung konfigurieren. Innerhalb der Aufbewahrungskennzeichnung können Sie folgendes angeben:

- Eine Reihe von Deskriptoren für die Dateien (z.B. nach Fachabteilung, Dateityp oder Verordnung).

- Die Aufbewahrungseinstellungen für die Dateien, die mit der Aufbewahrungskennzeichnung versehen sind, wie z.B. Aufbewahrungszeiten und -verhalten nach Erreichen der Aufbewahrungszeit.

Sie können Dateien auch automatisch mit einer Aufbewahrungsbezeichnung versehen, indem Sie eine SharePoint Online-Site so konfigurieren, dass alle neuen Dokumente in der Site mit einer Standard-Aufbewahrungsbezeichnung versehen werden. 

Weitere Informationen finden Sie unter [Übersicht zu Aufbewahrungsbezeichnungen](https://docs.microsoft.com/office365/securitycompliance/labels).

### <a name="sensitivity-labels"></a>Vertraulichkeitsbezeichnungen

Zum Schutz und zur Implementierung der Sicherheit für bestimmte Arten von Dokumenten oder Dokumenten mit bestimmten Inhalten gehört es, diese mit einer Bezeichnung zu versehen, damit die zusätzliche Sicherheit angewendet werden kann. Mit Vertraulichkeitsbezeichnungen in Microsoft 365 können Sie:

- Erzwingen von Schutzeinstellungen, wie Verschlüsselung, Berechtigungen oder das Hinzufügen eines Wasserzeichens.

- Verhindern, dass sensible Inhalte Ihre Organisation auf Geräten mit Windows verlassen, indem Sie den Endpoint Protection in Microsoft Intune verwenden. 

- Verwenden von Windows Information Protection (WIP) Endpoint Protection, um zu verhindern, dass Inhalte in eine Drittanbieteranwendung wie Twitter oder Gmail kopiert oder auf einen Wechselspeicher wie ein USB-Laufwerk kopiert werden.

- Verwenden von Microsoft Cloud App Security zum Schutz von Inhalten in Anwendungen und Diensten von Drittanbietern. 

- Klassifizieren von Inhalten ohne Verwendung von Schutzeinstellungen.

Wenn Sie Vertraulichkeitsbezeichnungen verwenden, sollten Sie für jede Sicherheits- und Information Protection-Stufe eine Bezeichnung konfigurieren. Beispielsweise, können Sie drei Vertraulichkeitsbezeichnungen erstellen für:

- Baseline

- Vertraulich

- Streng geregelt

Weitere Informationen finden Sie unter [Übersicht über Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels).

### <a name="azure-information-protection-labels-and-protection"></a>Bezeichnungen und Schutz in Azure Information Protection

Sie können die Azure Information Protection-Bezeichnungen verwenden, um die Dokumente und E-Mails Ihrer Organisation zu klassifizieren und optional zu schützen. Diese Bezeichnungen können sich auf Dokumente anwenden, die außerhalb von Microsoft 365 gespeichert sind. Diese Bezeichnungen können von Administratoren, die Regeln und Bedingungen definieren, automatisch angewendet werden, von Benutzern manuell oder in einer Kombination, bei der den Benutzern Empfehlungen gegeben werden.

Gehen Sie zum Planen und Bereitstellen von Bezeichnungen und Schutz in Azure Information Protection folgendermaßen vor:

1. Überprüfen der [Anforderungen für Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).
2. Befolgen der [Roadmap für die Bereitstellung von Klassifizierung, Bezeichnung und Schutz](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).

Weitere Informationen finden Sie in der [Bibliothek mit der Azure Information Protection-Dokumentation](https://docs.microsoft.com/information-protection/).

Bestehende Azure Information Protection Bezeichnungen arbeiten nahtlos mit Vertraulichkeitsbezeichnungen zusammen. Beispielsweise können Sie Ihre vorhandenen Azure Information Protection-Bezeichnungen sowie die Bezeichnungen, die auf Dokumente und E-Mails angewendet werden, beibehalten.

Wenn Sie sowohl über Vertraulichkeits- als auch über Azure Information Protection-Bezeichnungen verfügen, sollten Sie Ihre[Azure Information Protection-Bezeichnungen auf Vertraulichkeitsbezeichnungen migrieren](https://docs.microsoft.com/office365/securitycompliance/sensitivity-labels#how-sensitivity-labels-work-with-existing-azure-information-protection-labels). 

## <a name="example-classification-for-gdpr"></a>Beispiel: Klassifizierung für die DSGVO

Ein Beispiel für ein Klassifizierungsschema, das personenbezogene Daten für die DSGVO enthält, finden Sie unter [Entwerfen eines Klassifikationsschemas für personenbezogene Daten](https://docs.microsoft.com/office365/enterprise/architect-a-classification-schema-for-personal-data).

|||
|:-------|:-----|
|![Testumgebungsanleitungen für die Microsoft-Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [Testumgebungsanleitung: Klassifizierung von Daten](data-classification-microsoft-365-enterprise-dev-test-environment.md) |
|||

Als Zwischenprüfung können Sie die [Beendigungskriterien](infoprotect-exit-criteria.md#crit-infoprotect-step3) für diesen Schritt betrachten.

## <a name="next-step"></a>Nächster Schritt

|||
|:-------|:-----|
|![](./media/stepnumbers/Step3.png)|[Konfigurieren der erhöhten Sicherheit für Office 365](infoprotect-configure-increased-security-office-365.md)|

