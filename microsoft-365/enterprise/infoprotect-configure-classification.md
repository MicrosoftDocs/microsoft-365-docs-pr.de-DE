---
title: 'Schritt 2: Konfigurieren der Klassifizierung für Ihre Umgebung'
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/19/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Verstehen und Konfigurieren verschiedener Methoden zum Klassifizieren von Daten in Ihrer Organisation.
ms.openlocfilehash: bee0885eb3f8899560532895d1558723b281ab02
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26867757"
---
# <a name="step-2-configure-classification-for-your-environment"></a>Schritt 2: Konfigurieren der Klassifizierung für Ihre Umgebung

*Dieser Schritt ist optional und gilt für die Versionen E3 und E5 von Microsoft 365 Enterprise.*

![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

In diesem Schritt arbeiten Sie mit der Rechts- und Complianceabteilung zusammen, um ein Klassifizierungsschema für die Daten in Ihrer Organisation zu erstellen.

## <a name="microsoft-classifications"></a>Microsoft-Klassifizierungen

Microsoft 365 umfasst drei Typen von Klassifizierung:

- Typen vertraulicher Informationen für Office 365
- Office 365-Bezeichnungen
- Bezeichnungen und Schutz in Azure Information Protection

### <a name="sensitive-information-types-for-office-365"></a>Typen vertraulicher Informationen für Office 365

Typen vertraulicher Informationen für Office 365 definieren wie automatisierte Prozesse, z. B. die Suche, bestimmte Informationstypen erkennen, z. B. Health Service-Nummern und Kreditkartennummern. Verwenden Sie Typen vertraulicher Informationen für die Suche nach vertraulichen Daten und zum Anwenden von DLP-Regeln und -Richtlinien zum Schutz dieser Daten. Weitere Informationen finden Sie unter [Überblick über DLP-Richtlinien](https://support.office.com/article/overview-of-data-loss-prevention-policies-1966b2a7-d1e2-4d92-ab61-42efbb137f5e). Typen vertraulicher Informationen sind besonders hilfreich, um Compliance- und gesetzliche Anforderungen zu erfüllen, z. B. die Datenschutz-Grundverordnung (DSGVO).

### <a name="office-365-labels"></a>Office 365-Bezeichnungen
Sie können Office 365-Bezeichnungen für persönliche Daten und streng geregelte Dateien und Dateien mit Betriebsgeheimnissen verwenden, die in SharePoint Online und OneDrive for Business gespeichert sind. Weitere Informationen, darunter Schritte zum Erstellen, finden Sie unter [Übersicht über Bezeichnungen](https://support.office.com/article/overview-of-labels-af398293-c69d-465e-a249-d74561552d30).

Wenn Sie beschließen, Office 365-Bezeichnungen zu verwenden, sollten Sie mindestens eine für jede Schutzebene konfigurieren. Erstellen Sie beispielsweise drei Bezeichnungen für:

- Baseline
- Vertraulich
- Streng geregelt

### <a name="azure-information-protection-labels-and-protection"></a>Bezeichnungen und Schutz in Azure Information Protection

Sie können Azure Information Protection-Bezeichnungen zum Klassifizieren und für optionalen Schutz von Dokumenten und E-Mails in Ihrer Organisation verwenden. Diese Bezeichnungen können auf Dokumente angewendet werden, die außerhalb von Office 365 gespeichert sind. Diese Bezeichnungen können von Administratoren, die Regeln und Kriterien definieren, automatisch angewendet, manuell durch einen Benutzer oder eine Kombination aus beiden angewendet werden, indem Benutzern Empfehlungen bereitgestellt werden.

Gehen Sie zum Planen und Bereitstellen von Bezeichnungen und Schutz in Azure Information Protection folgendermaßen vor:

1. Überprüfen der [Anforderungen für Azure Information Protection](https://docs.microsoft.com/information-protection/get-started/requirements).
2. Befolgen der [Roadmap für die Bereitstellung von Klassifizierung, Bezeichnung und Schutz](https://docs.microsoft.com/information-protection/plan-design/deployment-roadmap#deployment-roadmap-for-classification-labeling-and-protection).

Weitere Informationen finden Sie in der [Bibliothek mit der Azure Information Protection-Dokumentation](https://docs.microsoft.com/information-protection/).

## <a name="classification-for-gdpr"></a>Klassifizierung für die DSGVO

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

