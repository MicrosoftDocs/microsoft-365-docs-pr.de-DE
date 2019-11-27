---
title: Verwenden des Datenklassifizierungsaktivitäten-Explorers
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Der Aktivitäten-Explorer rundet die Funktionalität der Datenklassifizierungsfunktion ab, indem Sie die Aktionen, die Benutzer mit Ihren beschrifteten Inhalten durchführen, anzeigen und filtern können.
ms.openlocfilehash: 272de0400e89f9829b3ead5d4523db27789c0c44
ms.sourcegitcommit: 9d0a025ea9e265d515a034de0102eabcf47d11f5
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 10/31/2019
ms.locfileid: "39268961"
---
# <a name="view-activity-on-your-labeled-content-preview"></a>Anzeigen von Aktivitäten mit beschrifteten Inhalten (Vorschau)

Auf den Registerkarten „Übersicht über die Datenklassifizierung“ und „Inhalts-Explorer“ erfahren Sie, welche Inhalte gefunden und beschriftet wurden und wo sich diese Inhalte befinden. Der Aktivitäten-Explorer rundet diese Funktionalitäten ab, indem Sie überwachen können, was mit Ihren beschrifteten Inhalten geschieht. Der Aktivitäten-Explorer bietet eine Verlaufsanzeige.

![Platzhalter für den Screenshot „Übersicht über den Aktivitäten-Explorer“](media/data-classification-activity-explorer-1.png)

Sie können die Daten filtern nach:

- Zeitraum:
- Aktivitätstyp
- Speicherort
- Benutzer
- Vertraulichkeitsbezeichnung
- Aufbewahrungsbezeichnung


Sie können die Daten in einer Liste oder in einem Balkendiagramm anzeigen.

## <a name="activity-type"></a>Aktivitätstyp

Microsoft 365 überwacht und berichtet über 12 Arten von Aktivitäten in SharePoint Online, OneDrive und Endpunkten. Endpunkte sind Benutzergeräte mit Windows 10.

- Datei erstellt
- Datei geändert
- Datei umbenannt
- Datei in die Cloud kopiert
- Zugriff auf Datei durch eine nicht zulässige App
- Datei gedruckt
- Datei auf Wechselmedien kopiert
- Datei auf die Netzwerkfreigabe kopiert
- Datei gelesen
- Datei in die Zwischenablage kopiert
- Bezeichnung angewendet
- Bezeichnung geändert (aktualisiert, heruntergestuft oder entfernt)

Wenn Sie wissen, welche Aktionen mit Ihren vertraulichen beschrifteten Inhalten durchgeführt werden, können Sie feststellen, ob die von Ihnen bereits eingerichteten Steuerelemente, z. B. [Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md), wirksam sind oder nicht. Wenn dies nicht der Fall ist oder Sie etwas Unerwartetes entdecken, z. B. eine große Anzahl von Elementen, die mit `highly confidential` beschriftet sind und auf `general` herabgestuft werden, können Sie die verschiedenen Richtlinien verwalten und neue Aktionen ausführen, um das unerwünschte Verhalten einzuschränken.

Sobald Ihre Filter festgelegt sind, haben Sie folgende Möglichkeiten:

- Zeigen Sie mit der Maus auf ein Segment des Balkendiagramms, um die Anzahl der Elemente anzuzeigen, die in diese Kategorie fallen ![Mauszeiger Aktivitäten-Explorer](media/data-classification-activity-explorer-hover-over-2.png)
- Exportieren von Daten
- Wählen Sie ein beliebiges Element in der Liste aus und zeigen Sie die Details der Aktion im Flyout an.

![Flyout für Details des Aktivitäten-Explorers](media/data-classification-activity-explorer-fly-out-3.png)

## <a name="see-also"></a>Siehe auch
- [Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Aufbewahrungsbezeichnungen](labels.md)
- [Wonach die Typen von vertraulichen Informationen suchen](what-the-sensitive-information-types-look-for.md)
- [Übersicht über Aufbewahrungsrichtlinien](retention-policies.md)