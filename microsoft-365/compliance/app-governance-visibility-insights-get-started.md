---
title: Erste Schritte mit Sichtbarkeit und Insights
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Beginnen Sie mit Sichtbarkeit und Insights.
ms.openlocfilehash: 12c1a01667b1bda545b619e931d99132e6611e35
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420133"
---
# <a name="get-started-with-visibility-and-insights"></a>Erste Schritte mit Sichtbarkeit und Insights

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Der Ort für die ersten Schritte ist das App-Governance-Dashboard auf [https://compliance.microsoft.com/appgovernance](https://compliance.microsoft.com/appgovernance). Beachten Sie, dass Ihr Anmeldekonto über eine [dieser App-Governance-Administratorrollen](app-governance-get-started.md#administrator-roles) verfügen muss, um App-Governance-Daten anzuzeigen.

![Die Übersichtsseite der App-Governance im Microsoft 365 Compliance Center](..\media\manage-app-protection-governance\mapg-cc-overview.png)

Sie können auch über **Microsoft 365 Admin Center > Microsoft 365 Compliance Center > App-Governance > Übersichtsseite** auf das Dashboard für die App-Governance zugreifen.

## <a name="whats-available-on-the-dashboard"></a>Was ist auf dem Dashboard verfügbar

Das Dashboard enthält eine Zusammenfassung der Komponenten des Microsoft 365 App-Ökosystems im Mandanten:

- **Mandantenzusammenfassung**: Die Anzahl der wichtigsten App- und Benachrichtigungskategorien.
- **Erkennungs- und Richtlinienbenachrichtigungen**: Die neuesten aktiven Benachrichtigungen im Mandanten
- **Daten- und Ressourcenzugriff**: Aggregieren Sie den Zugriff auf die Anwendungs-API und die Gesamtnutzung der wichtigsten Ressourcen im Mandanten. Bewegen Sie den Mauszeiger über jede Monatsspalte im Diagramm, um den entsprechenden Wert anzuzeigen.
- **Verbessern des Schutzes und der Governance Ihrer App**: Empfohlene Aktionen wie das Erstellen einer App-Nutzungs- oder Berechtigungsrichtlinie.
- **Wichtigste Apps nach Kategorien**: Die wichtigsten Apps, sortiert nach diesen Kategorien:
  
  - **Alle Kategorien**: Sortiert über alle verfügbaren Kategorien.
  - **Hohe Berechtigung**: „Hohe Berechtigung“ ist eine intern festgelegte Kategorie, die auf maschinellem Lernen und Signalen der Plattform basiert.
  - **Überprivilegiert**: Wenn die App-Governance Telemetriedaten empfängt, die angeben, dass eine einer Anwendung erteilte Berechtigung in den letzten 90 Tagen nicht verwendet wurde, ist diese Anwendung überprivilegiert. Die App-Governance muss mindestens 90 Tage lang ausgeführt werden, um festzustellen, ob eine App überprivilegiert ist.  
  - **Nicht überprüft**: Anwendungen, die keine [Herausgeberzertifizierung](https://docs.microsoft.com/azure/active-directory/develop/publisher-verification-overview) erhalten haben, werden als nicht überprüft betrachtet.
  - **Nur App**: [Anwendungsberechtigungen](https://docs.microsoft.com/azure/active-directory/develop/v2-permissions-and-consent#permission-types) werden von Apps verwendet, die ohne die Anwesenheit eines angemeldeten Benutzers ausgeführt werden können. Apps mit mandantenübergreifenden Zugriffsberechtigungen auf Daten stellen ein potenziell höheres Risiko dar.
  - **Neue Apps**: Neue Microsoft 365 Apps, die in den letzten sieben Tagen registriert wurden.  

## <a name="next-step"></a>Nächster Schritt

[Erhalten Sie detaillierte Insights in eine bestimmte App](app-governance-visibility-insights-view-apps.md).
