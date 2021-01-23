---
title: Erste Schritte mit dem Aktivitäten-Explorer
f1.keywords:
- NOCSH
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
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Der Aktivitäten-Explorer rundet die Funktionalität der Datenklassifizierungsfunktion ab, indem Sie die Aktionen, die Benutzer mit Ihren beschrifteten Inhalten durchführen, anzeigen und filtern können.
ms.openlocfilehash: 6825c00373617011db28fa484f272086f887ea40
ms.sourcegitcommit: 7ecd10b302b3b3dfa4ba3be3a6986dd3c189fbff
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 01/21/2021
ms.locfileid: "49921633"
---
# <a name="get-started-with-activity-explorer"></a>Erste Schritte mit dem Aktivitäten-Explorer

Auf den Registerkarten „Übersicht über die Datenklassifizierung“ und „Inhalts-Explorer“ erfahren Sie, welche Inhalte gefunden und beschriftet wurden und wo sich diese Inhalte befinden. Der Aktivitäten-Explorer rundet diese Funktionalitäten ab, indem Sie überwachen können, was mit Ihren beschrifteten Inhalten geschieht. Der Aktivitäten-Explorer bietet eine Verlaufsanzeige.

![Platzhalter für den Screenshot „Übersicht über den Aktivitäten-Explorer“](../media/data-classification-activity-explorer-1.png)

Es stehen über 30 verschiedene Filter zur Verfügung, einschließlich:

- Zeitraum:
- Aktivitätstyp
- Speicherort
- Benutzer
- Vertraulichkeitsbezeichnung
- Aufbewahrungsbezeichnung
- Dateipfad
- DLP-Richtlinie


## <a name="prerequisites"></a>Voraussetzungen

Jedem Konto, das auf die Datenklassifizierung zugreift und sie verwendet, muss eine Lizenz aus einem dieser Abonnements zugewiesen sein:

- Microsoft 365 (E5)
- Office 365 (E5)
- Advanced Compliance (E5)-Add-on
- Advanced Threat Intelligence (E5)-Add-on
- Microsoft 365 E5/A5 Info Protection & Governance
- Microsoft 365 E5/A5 Compliance

### <a name="permissions"></a>Berechtigungen

 Um Zugriff auf die Registerkarte „Aktivitäts-Explorer“ zu erhalten, muss einem Konto die Mitgliedschaft in einer dieser Rollen oder Rollengruppen zugewiesen werden.

**Microsoft 365-Rollengruppen**

- Globaler Administrator
- Compliance-Administrator
- Sicherheitsadministrator
- Compliancedatenadministrator

## <a name="activity-type"></a>Aktivitätstyp

Microsoft 365 überwacht und berichtet über Arten von Aktivitäten in SharePoint Online und OneDrive, wie z. B.:

- Bezeichnung angewendet
- Bezeichnung geändert (aktualisiert, heruntergestuft oder entfernt)
- Simulation der automatischen Bezeichnung

Wenn Sie wissen, welche Aktionen mit Ihren vertraulichen beschrifteten Inhalten durchgeführt werden, können Sie feststellen, ob die von Ihnen bereits eingerichteten Steuerelemente, z. B. [Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md), wirksam sind oder nicht. Wenn dies nicht der Fall ist oder Sie etwas Unerwartetes entdecken, z. B. eine große Anzahl von Elementen, die mit `highly confidential` beschriftet sind und auf `general` herabgestuft werden, können Sie die verschiedenen Richtlinien verwalten und neue Aktionen ausführen, um das unerwünschte Verhalten einzuschränken.

> [!NOTE]
> Der Aktivitäts-Explorer überwacht derzeit keine Aufbewahrungsaktivitäten für Exchange Online.

## <a name="see-also"></a>Siehe auch
- [Weitere Informationen zu Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md)
- [Entitätsdefinitionen für Typen vertraulicher Informationen](sensitive-information-type-entity-definitions.md)

