---
title: Multi-Geo-Funktionen in Microsoft Teams
ms.reviewer: daro
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: ''
ms.collection:
- Strat_SP_gtc
- SPO_Content
- m365solution-scenario
- m365solution-spintranet
localization_priority: Normal
description: Erfahren Sie, wie Teams mit Microsoft 365 Multi-Geo funktioniert.
ms.openlocfilehash: 7da2032e1106d03178eccf3bcfb4f37fc63780d7
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53453525"
---
# <a name="multi-geo-capabilities-in-microsoft-teams"></a>Multi-Geo-Funktionen in Microsoft Teams

Multi-Geo-Funktionen in Teams ermöglichen das Speichern Teams ruhenden Chatdaten an einem angegebenen geografischen Standort. Chatdaten bestehen aus Chatnachrichten, einschließlich privater Nachrichten, Kanalnachrichten und Bildern, die in Chats verwendet werden.

Teams verwendet den bevorzugten Datenspeicherort (Preferred Data Location, PDL) für Benutzer und Gruppen, um zu bestimmen, wo Daten gespeichert werden sollen. Wenn der PDL nicht festgelegt ist oder ungültig ist, werden die Daten am zentralen Standort des Mandanten gespeichert.

## <a name="user-chat"></a>Benutzerchat

Der Benutzerchat umfasst 1:1-, 1:n- und private Besprechungsnachrichten.

Wenn ein neuer Benutzer erstellt wird, liest Teams den PDL des Benutzers und speichert alle seine Chatdaten an diesem geografischen Standort.

Wenn ein Administrator für vorhandene Benutzer den PDL für einen Benutzer hinzufügt oder ändert, werden die Chatdaten dieses Benutzers einer Migrationswarteschlange hinzugefügt, um an den angegebenen geografischen Standort verschoben zu werden.

Der Speicherort für einen 1:1- oder 1:n-Chat basiert auf dem PDL der Person, die den Chat erstellt hat. Wenn der PDL dieses Benutzers geändert wird, wird der Chat an den neuen geografischen Standort migriert. Der Speicherort für einen Besprechungschat basiert auf dem PDL des Besprechungsorganisators.

Um den aktuellen Speicherort der Teams Daten eines Benutzers zu finden, [stellen Sie eine Verbindung mit Teams PowerShell](/powershell/module/teams/connect-microsoftteams) her, und führen Sie den folgenden Befehl aus:

```PowerShell
Get-MultiGeoRegion -EntityType User -EntityId <UPN>
```

## <a name="channel-messages"></a>Kanalnachrichten

Jede Microsoft 365 Gruppe verfügt über einen bevorzugten Datenspeicherort (Preferred Data Location, PDL), der den geografischen Standort angibt, an dem verwandte Daten gespeichert werden sollen. Teams verwendet den PDL für die Gruppe, die jedem Team zugeordnet ist, um zu bestimmen, wo Kanalnachrichtendaten für dieses Team gespeichert werden sollen. Dazu gehören private Kanäle sowie Chats, die innerhalb einer Kanalbesprechung stattfinden.

Wenn ein Benutzer ein neues Team erstellt, bestimmt der PDL dieses Benutzers, welcher PDL der Microsoft 365 Gruppe zugewiesen ist. Der Gruppen-PDL bestimmt, wo die Daten dieses Teams gespeichert werden. Wenn sich der PDL dieses Benutzers später ändert, wird der PDL der Gruppe nicht geändert.

Wenn ein Administrator für vorhandene Teams den PDL für die Microsoft 365 Gruppe hinzufügt oder ändert, die ein Team unterstützt, werden die Kanalnachrichtendaten dieses Teams zu einer Migrationswarteschlange hinzugefügt, um an den angegebenen geografischen Standort verschoben zu werden.

Wenn Sie den PDL der Microsoft 365-Gruppe ändern, werden die Teams Daten in die Warteschlange für die Migration an den ausgewählten Speicherort gestellt. Dadurch wird jedoch nicht automatisch die SharePoint Website oder dateien migriert, die der Gruppe zugeordnet sind. Sie müssen die Website separat verschieben, indem Sie die Verfahren unter [Verschieben eines SharePoint-Standorts an einen anderen geografischen Standort](/microsoft-365/enterprise/move-sharepoint-between-geo-locations)ausführen. Führen Sie beide Schritte aus, um zu vermeiden, dass Daten Teams und Daten für eine Gruppe an unterschiedlichen Speicherorten SharePoint.

Um den aktuellen Speicherort der Daten eines Teams zu finden, [stellen Sie eine Verbindung mit Teams PowerShell](/powershell/module/teams/connect-microsoftteams) her, und führen Sie den folgenden Befehl aus:

```PowerShell
Get-MultiGeoRegion -EntityType Group -EntityId <GroupObjectId>
```

## <a name="user-experience"></a>Benutzererfahrung

Teams Multi-Geo ist nahtlos für den Endbenutzer. Sobald Sie den PDL eines Benutzers oder einer Gruppe geändert haben, werden die entsprechenden Daten für die Migration in die Warteschlange warteschlangen, und die Migration erfolgt automatisch ohne Auswirkung auf den Benutzer oder den Teams Client, auch wenn sie während der Migration aktiv sind.

## <a name="see-also"></a>Siehe auch

[Microsoft 365 Multi-Geo-Mandantenkonfiguration](/microsoft-365/enterprise/multi-geo-tenant-configuration)

[Verwalten einer Multi-Geo-Umgebung](administering-a-multi-geo-environment.md)

[Verwalten von Exchange Online-Postfächern in einer Multi-Geo-Umgebung](administering-exchange-online-multi-geo.md)
