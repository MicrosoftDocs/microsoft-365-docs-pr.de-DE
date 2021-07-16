---
title: Erste Schritte mit der App-Bedrohungserkennung und -Behebung
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
description: Beginnen Sie mit der App-Bedrohungserkennung und -Behebung.
ms.openlocfilehash: 77de3676a9a486bbed572a4a16bf62ad4d038406
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430720"
---
# <a name="get-started-with-app-threat-detection-and-remediation"></a>Erste Schritte mit der App-Bedrohungserkennung und -Behebung

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Die Microsoft App-Governance sammelt Bedrohungsbenachrichtigungen, die durch systemeigene App-Governance-Erkennungsmethoden basierend auf Aktivitäten bösartiger Apps erzeugt werden, und richtlinienbasierte Benachrichtigungen, die durch von Ihnen erstellte aktive App-Richtlinien erzeugt werden.

Der erste Ort, um App-Benachrichtigungen anzuzeigen, ist das App-Governance-Dashboard auf [https://aka.ms/appgovernance](https://aka.ms/appgovernance).

![Die Übersichtsseite der App-Governance im Microsoft 365 Compliance Center mir dem hervorgehobenen Abschnitt „Erkennungs- und Richtlinienbenachrichtigungen“](..\media\manage-app-protection-governance\mapg-cc-overview-alerts.png)

Der Abschnitt **Erkennungs- und Richtlinienbenachrichtigungen** auf dieser Übersichtsseite listet die neuesten Benachrichtigungen auf. Sie können dies verwenden, um schnell die aktuelle App-Benachrichtigungsaktivität für Ihren Mandanten sehen.

Wählen Sie die Registerkarte **Benachrichtigungen** aus, um alle Benachrichtigungen zu sehen.

## <a name="whats-available-on-the-alerts-page"></a>Das ist auf der Benachrichtigungen-Seite verfügbar

Die Seite **Benachrichtigungen** listet alle auf der App-Governance basierenden Benachrichtigungen für Ihren Mandanten auf.

![Die Zusammenfassungsseite der Benachrichtigungen der App-Governance im Microsoft 365 Compliance Center](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

Jede aufgeführte Benachrichtigung enthält die folgenden Informationen:

- **Benachrichtigungsname**: Der Typ des anomalen Verhaltens.
- **App-Name**: Die App, welche die Benachrichtigung erzeugt hat.
- **Schweregrad**: Der von der App-Governance zugewiesene Schweregrad für von ihr erstellte Benachrichtigungen, oder der Schweregrad der App-Richtlinie, die den Alarm erzeugt hat.
- **Quelle**: Ursprung der Benachrichtigung, die das Ergebnis einer Richtlinie (vom Benutzer erstellte Richtlinien), einer Erkennung (systemeigene Erkennungsrichtlinien) oder von MCAS sein kann.
- **Status**: **Neu** deutet auf eine Benachrichtigung hin, der noch kein Status zugewiesen wurde. Nach der Zuweisung ist der Status entweder **In Bearbeitung** während der Untersuchung, oder **Behoben** für Benachrichtigungen, die durch eine automatische oder manuelle Korrektur behoben wurden.
- **Erstelldatum**: Das Datum, an der die Benachrichtigung entweder durch App-Governance-Erkennung oder durch eine App-Richtlinie erzeugt wurde. Alle angezeigten Datumsangaben sind in der lokalen Zeitzone des Microsoft 365 Compliance Center.
- **Letzte Aktivität**: Das Datum, an dem der Status der Benachrichtigung zuletzt geändert wurde. Alle angezeigten Datumsangaben sind in der lokalen Zeitzone des Microsoft 365 Compliance Center.

Die Benachrichtigungsliste ist standardmäßig nach **Erstelldatum** sortiert. Um die Liste nach einem anderen Attribut zu sortieren, wählen Sie den Attributnamen aus.

Sie können die aktuelle Benachrichtigungsliste auch in eine CSV (comma separated value)-Datei exportieren. Sie können die CVS-Datei beispielsweise in Microsoft Excel öffnen, und die Liste der Benachrichtigungen nach **Schweregrad** und dann nach **Erstelldatum** sortieren.

## <a name="next-step"></a>Nächster Schritt

[Beheben von App-Bedrohungen.](app-governance-detect-remediate-detect-threats.md)
