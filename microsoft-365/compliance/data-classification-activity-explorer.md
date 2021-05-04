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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: Der Aktivitäten-Explorer rundet die Funktionalität der Datenklassifizierungsfunktion ab, indem Sie die Aktionen, die Benutzer mit Ihren beschrifteten Inhalten durchführen, anzeigen und filtern können.
ms.openlocfilehash: 414ef4e5d9f6472180a5eaef391d3eba33463b02
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114007"
---
# <a name="get-started-with-activity-explorer"></a>Erste Schritte mit dem Aktivitäten-Explorer

Die [](data-classification-overview.md) Datenklassifizierungsübersicht und die Registerkarten des [Inhalts-Explorers](data-classification-content-explorer.md) bieten Ihnen Einen Überblick darüber, welche Inhalte erkannt und gekennzeichnet wurden und wo sich dieser Inhalt befindet. Der Aktivitäten-Explorer rundet diese Funktionalitäten ab, indem Sie überwachen können, was mit Ihren beschrifteten Inhalten geschieht. Der Aktivitäts-Explorer bietet eine verlaufshistorische Ansicht der Aktivitäten in Ihren beschriftet inhalten. Die Aktivitätsinformationen werden aus Microsoft 365 einheitlichen Überwachungsprotokollen gesammelt, transformiert und in der Benutzeroberfläche des Aktivitäts-Explorers verfügbar gemacht. 

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

 Um Zugriff auf die Registerkarte Aktivitäts-Explorer zu erhalten, muss einem Konto explizit die Mitgliedschaft in einer dieser Rollengruppen zugewiesen oder der Rolle explizit erteilt werden.

<!--
> [!IMPORTANT]
> Access to Activity explorer via the Security reader or Device Management role groups or other has been removed-->

**Microsoft 365-Rollengruppen**

- Globaler Administrator
- Compliance-Administrator
- Sicherheitsadministrator
- Compliancedatenadministrator

**Microsoft 365 Rollen**

- Compliance-Administrator
- Sicherheitsadministrator

## <a name="activity-types"></a>Aktivitätstypen

Der Aktivitäts-Explorer sammelt Aktivitätsinformationen aus den Überwachungsprotokollen für mehrere Quellen von Aktivitäten. Ausführlichere Informationen dazu, welche Bezeichnungsaktivität es in den Aktivitäts-Explorer ermöglicht, finden Sie unter [Bezeichnungsereignisse, die im Aktivitäts-Explorer verfügbar sind.](data-classification-activity-explorer-available-events.md)

**Vertraulichkeitsbezeichnungsaktivitäten** und Aufbewahrungsbezeichnungsaktivitäten aus Office systemeigenen Anwendungen, Azure Information Protection-Add-Ins, SharePoint Online, Exchange Online (nur Vertraulichkeitsbezeichnungen) und OneDrive.  Einige Beispiele:

- Bezeichnung angewendet
- Bezeichnung geändert (aktualisiert, heruntergestuft oder entfernt)
- Simulation der automatischen Bezeichnung
- Datei lesen 

**Azure Information Protection (AIP)-Scanner und AIP-Clients**

- Angewendeter Schutz
- Schutz geändert
- Schutz entfernt
- Ermittelte Dateien 

Der Aktivitäts-Explorer sammelt außerdem **Ereignisse** aus Exchange Online, SharePoint Online, OneDrive, Teams Chat und Kanal (Vorschau), lokalen SharePoint-Ordnern und Bibliotheken sowie lokalen Dateifreigaben und Windows 10-Geräten über **DLP (Endpoint Data Loss Prevention).** Einige Beispielereignisse von Windows 10 sind Datei:

- Löschvorgänge
- creations
- in die Zwischenablage kopiert
- geändert
- Lesen
- gedruckt
- umbenannt
- in die Netzwerkfreigabe kopiert
- Zugriff durch nicht zugelassene App 

Der Wert des Verständnisses, welche Aktionen mit Ihren vertraulich gekennzeichneten Inhalten ergriffen werden, ist, dass Sie sehen können, ob die steuerelemente, die Sie bereits ergriffen haben, z. B. verhinderung von Datenverlusten wirksam sind oder nicht. [](dlp-learn-about-dlp.md) Wenn dies nicht der Fall ist oder Sie etwas Unerwartetes entdecken, z. B. eine große Anzahl von Elementen, die mit `highly confidential` beschriftet sind und auf `general` herabgestuft werden, können Sie die verschiedenen Richtlinien verwalten und neue Aktionen ausführen, um das unerwünschte Verhalten einzuschränken.

> [!NOTE]
> Der Aktivitäts-Explorer überwacht derzeit keine Aufbewahrungsaktivitäten für Exchange Online.

## <a name="see-also"></a>Siehe auch

- [Weitere Informationen zu Vertraulichkeitsbezeichnungen](sensitivity-labels.md)
- [Weitere Informationen zu Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen](retention.md)
- [Informationen zu Typen vertraulicher Informationen](sensitive-information-type-learn-about.md)
- [Informationen zur Datenklassifizierung](data-classification-overview.md)
