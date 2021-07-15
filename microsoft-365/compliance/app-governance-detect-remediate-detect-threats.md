---
title: Beheben von App-Bedrohungen
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
description: Beheben Sie App-Bedrohungen.
ms.openlocfilehash: 73776621ef86523d64b2a216538412bb46ab5586
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420184"
---
# <a name="remediate-app-threats"></a>Beheben von App-Bedrohungen

>*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*

Sie beheben App-Bedrohungen gegen Ihren Microsoft 365-Mandanten über die Seite **Benachrichtigungen** im Abschnitt Microsoft App-Governance des Microsoft 365 Compliance Center.

![Die Zusammenfassungsseite der Benachrichtigungen der App-Governance im Microsoft 365 Compliance Center](..\media\manage-app-protection-governance\mapg-cc-alerts.png)

Die Seite **Benachrichtigungen** listet standardmäßig neue Bedrohungsbenachrichtigungen auf, die von der App-Governance erzeugt wurden, sowie richtlinienbasierte Benachrichtigungen, die von aktiven App-Richtlinien generiert wurden. Sie können die Details einer bestimmten Benachrichtigung anzeigen, indem Sie diese auswählen, wodurch ein Benachrichtigungsbereich mit zusätzlichen Benachrichtigungsinformationen geöffnet wird, mit der Möglichkeit, den Status zu ändern.

![Die Benachrichtigungen-Detailseite der App-Governance im Microsoft 365 Compliance Center](..\media\manage-app-protection-governance\mapg-cc-alerts-alert.png)

Aus diesem Bereich können Sie diese zusätzlichen Informationen abrufen: 

- Zusätzliche Details zur Benachrichtigung aus dem Feld **Beschreibung**.
- Der Name der App-Richtlinie, welche die Benachrichtigung erzeugt hat, aus dem Feld **Richtlinienname**. Sie können auch **Richtlinie anzeigen** auswählen, um zur App-Richtlinie zu wechseln, welche die Benachrichtigung erzeugt hat.

App-Richtlinien, welche Sie für die automatische Behebung über die **Aktion** konfiguriert haben, erhalten den Status **Behoben**.

Sie können eine App-Benachrichtigung über diese Schritte beheben:

1. Untersuchung: Untersuchen Sie die Informationen in der Benachrichtigung, und ändern Sie ihren Status in **„In Bearbeitung“ markieren**.
2. Auflösung: Nach Ihrer Untersuchung und allenfalls der Festlegung von App-Richtlinienänderungen oder fortgesetzter App-Unterstützung in Ihrem Mandanten, ändern Sie den Status auf **Gelöst**.

Basierend auf App-Benachrichtigungsmustern können Sie die entsprechende App-Richtlinie aktualisieren, und ihre Einstellung für **Aktion** ändern, um eine automatische Behebung durchzuführen. Damit entfällt die Notwendigkeit, zukünftige Benachrichtigungen, die von der App-Richtlinie erzeugt werden, zu untersuchen und manuell zu beheben. Weitere Informationen finden Sie unter [Verwalten Ihrer App-Richtlinien](app-governance-app-policies-manage.md).
