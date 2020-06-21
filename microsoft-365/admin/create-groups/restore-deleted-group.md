---
title: Wiederherstellen einer gelöschten Gruppe
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
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b7c66b59-657a-4e1a-8aa0-8163b1f4eb54
description: Informationen zum Wiederherstellen einer gelöschten Microsoft 365-Gruppe.
ms.openlocfilehash: d7cf548816af1661298458f27c704d654845075d
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44818507"
---
# <a name="restore-a-deleted-group"></a>Wiederherstellen einer gelöschten Gruppe

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Wenn Sie eine Gruppe gelöscht haben, wird Sie standardmäßig 30 Tage lang aufbewahrt. Dieser 30-Tage-Zeitraum wird als Aufbewahrungsfrist für das vorläufige Löschen betrachtet, weil ein Wiederherstellen der Gruppe während dieses Zeitraums noch möglich ist. Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.

Beim Wiederherstellen einer Gruppe werden folgende Inhalte wiederhergestellt:
  
- Azure Active Directory (AD) Microsoft 365 Groups-Objekt, Eigenschaften und Member.
    
- E-Mail-Adressen von Gruppen.
    
- Der freigegebene Posteingang und Kalender in Exchange Online.
    
- Die SharePoint Online-Teamwebsite und die entsprechenden Dateien.
    
- OneNote-Notizbuch
    
- Planner
    
- Microsoft Teams

- Jammern von Gruppen-und Gruppeninhalten (wenn die Microsoft 365-Gruppe aus jammern erstellt wurde)

## <a name="restore-a-group-that-you-own-by-using-outlook-on-the-web"></a>Wiederherstellen einer eigenen Gruppe mithilfe von Outlook im Internet

Wenn Sie der Besitzer einer Microsoft 365-Gruppe sind, können Sie die Gruppe selbst in Outlook im Internet wiederherstellen, indem Sie die folgenden Schritte ausführen:

1. Wählen Sie auf der Seite [Gelöschte Gruppen](https://outlook.office.com/people/group/deleted)die Option **Gruppen verwalten** unter dem Knoten **Gruppen** und dann **Gelöscht** aus.

2. Klicken Sie auf die Schaltfläche **Wiederherstellen** neben der Gruppe, die Sie wiederherstellen möchten.

Wenn die gelöschte Gruppe hier nicht angezeigt wird, wenden Sie sich an einen Administrator.

## <a name="restore-a-group-in-the-microsoft-365-admin-center"></a>Wiederherstellen einer Gruppe im Microsoft 365 Admin Center

Wenn Sie globaler Administrator oder Gruppenadministrator sind, können Sie eine gelöschte Gruppe im Microsoft 365 Admin Center wiederherstellen:

1. Wechseln Sie zum [Admin Center](https://admin.microsoft.com).
2. Erweitern Sie **Gruppen**, und klicken Sie dann auf **Gelöschte Gruppen**.
3. Wählen Sie die Gruppe aus, die Sie wiederherstellen möchten, und klicken Sie dann auf **Gruppe wiederherstellen**.

> [!NOTE]
> In einigen Fällen kann es bis zu 24 Stunden dauern, bis die Gruppe und alle Daten wiederhergestellt werden. 
  
## <a name="permanently-delete-a-microsoft-365-group"></a>Dauerhaftes Löschen einer Microsoft 365-Gruppe

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

To confirm that the group has been successfully purged, run the  *Get-AzureADMSDeletedGroup*  cmdlet again to confirm that the group no longer appears on the list of soft-deleted groups. In some cases it may take as long as 24 hours for the group and all of its data to be permanently deleted. 
  
## <a name="got-questions-about-microsoft-365-groups"></a>Haben Sie Fragen zu Microsoft 365-Gruppen?

Besuchen Sie die [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) , um Fragen zu veröffentlichen und an Unterhaltungen zu Microsoft 365-Gruppen teilzunehmen. 
  
## <a name="related-articles"></a>Verwandte Artikel

[Verwalten von Microsoft 365-Gruppen mit PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/manage-office-365-groups-with-powershell)
  
[Löschen von Gruppen mit dem Cmdlet "Remove-UnifiedGroup"](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Verwalten Ihrer gruppenabhängigen Teamwebsiteeinstellungen](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Löschen einer Gruppe in Outlook 2016](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
