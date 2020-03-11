---
title: Wiederherstellen einer gelöschten Office 365 Gruppe
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Hier erfahren Sie, wie Sie eine gelöschte Office 365 Gruppe wiederherstellen.
ms.openlocfilehash: 31d6481f87d7da219e042eefa8f004425caee133
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583162"
---
# <a name="restore-a-deleted-office-365-group"></a>Wiederherstellen einer gelöschten Office 365-Gruppe

Wenn Sie eine Gruppe gelöscht haben, wird Sie standardmäßig 30 Tage lang aufbewahrt. Dieser 30-Tage-Zeitraum wird als Aufbewahrungsfrist für das vorläufige Löschen betrachtet, weil ein Wiederherstellen der Gruppe während dieses Zeitraums noch möglich ist. Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.

Beim Wiederherstellen einer Gruppe werden folgende Inhalte wiederhergestellt:
  
- Objekte, Eigenschaften und Mitglieder von Office 365-Gruppen in Azure Active Directory (AD).
    
- E-Mail-Adressen von Gruppen.
    
- Der freigegebene Posteingang und Kalender in Exchange Online.
    
- Die SharePoint Online-Teamwebsite und die entsprechenden Dateien.
    
- OneNote-Notizbuch
    
- Planner
    
- Microsoft Teams

- Yammer-Gruppe und Gruppeninhalt (wenn die Office 365-Gruppe aus Yammer erstellt wurde)

## <a name="restore-a-group-that-you-own-by-using-outlook"></a>Wiederherstellen einer eigenen Gruppe mithilfe von Outlook

Wenn Sie der Besitzer einer Office 365 Gruppe sind, können Sie die Gruppe selbst in Outlook wiederherstellen, indem Sie die folgenden Schritte ausführen:

1. Wählen Sie auf der Seite [Gelöschte Gruppen](https://outlook.office.com/people/group/deleted)die Option **Gruppen verwalten** unter dem Knoten **Gruppen** und dann **Gelöscht** aus.
2. Klicken Sie auf die Schaltfläche **Wiederherstellen** neben der Gruppe, die Sie wiederherstellen möchten.

Wenn die gelöschte Gruppe hier nicht angezeigt wird, wenden Sie sich an einen Administrator.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Wiederherstellen einer Gruppe im Microsoft 365 Admin Center

Wenn Sie globaler Administrator oder Gruppenadministrator sind, können Sie eine gelöschte Gruppe im Microsoft 365 Admin Center wiederherstellen:

1. Wechseln Sie zum Admin Center auf [https://admin.microsoft.com](Go to the admin center at https://admin.microsoft.com).
2. Erweitern Sie **Gruppen**, und klicken Sie dann auf **Gelöschte Gruppen**.
3. Wählen Sie die Gruppe aus, die Sie wiederherstellen möchten, und klicken Sie dann auf **Gruppe wiederherstellen**.
  
## <a name="permanently-delete-an-office-365-group"></a>Endgültiges Löschen einer Office 365-Gruppe

Manchmal möchten Sie vielleicht eine Gruppe endgültig löschen, ohne den Ablauf der 30-Tage-Frist für das vorläufige Löschen abzuwarten. Starten Sie hierzu PowerShell, und führen Sie den folgenden Befehl aus, um die Objekt-ID der Gruppe abzurufen:
  
```
Get-AzureADMSDeletedGroup
```

Notieren Sie sich die Objekt-ID der Gruppe(n), die Sie endgültig löschen möchten.
  
> [!CAUTION]
> Durch das endgültige Löschen der Gruppe werden die Gruppe und alle zugehörigen Daten für immer entfernt. 
  
Führen Sie in PowerShell den folgenden Befehl aus, um die Gruppe endgültig zu löschen:
  
```
Remove-AzureADMSDeletedDirectoryObject -Id <objectId>
```

Führen Sie zur Bestätigung, dass die Gruppe erfolgreich endgültig gelöscht wurde, das Cmdlet  *Get-AzureADMSDeletedGroup*  erneut aus, um sicherzustellen, dass die Gruppe nicht mehr in der Liste vorläufig gelöschter Gruppen angezeigt wird. In einigen Fällen kann es bis zu 24 Stunden dauern, bis die Gruppe und alle zugehörigen Daten endgültig gelöscht wurden. 
  
## <a name="got-questions-about-office-365-groups"></a>Haben Sie Fragen zu Office 365-Gruppen?

Besuchen Sie die [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups), um Fragen zu posten und an Unterhaltungen zu Office 365-Gruppen teilzunehmen. 
  
## <a name="related-articles"></a>Verwandte Artikel

[Verwalten von Office 365-Gruppen mit PowerShell](https://support.office.com/article/aeb669aa-1770-4537-9de2-a82ac11b0540)
  
[Löschen von Gruppen mit dem Cmdlet "Remove-UnifiedGroup"](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Verwalten Ihrer gruppenabhängigen Teamwebsiteeinstellungen](https://support.office.com/article/8376034d-d0c7-446e-9178-6ab51c58df42.aspx)
  
[Löschen einer Gruppe in Outlook 2016](https://support.office.com/article/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f.aspx)
