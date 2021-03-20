---
title: Wiederherstellen einer gelöschten Microsoft 365-Gruppe
ms.reviewer: arvaradh
f1.keywords: CSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
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
description: Erfahren Sie, wie Sie eine gelöschte Microsoft 365-Gruppe wiederherstellen können.
ms.openlocfilehash: f3b6435d82d5beddf44f5920011b076b39c7dcd5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50910546"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Wiederherstellen einer gelöschten Microsoft 365-Gruppe

Wenn Sie eine Gruppe gelöscht haben, wird Sie standardmäßig 30 Tage lang aufbewahrt. Dieser 30-Tage-Zeitraum wird als Aufbewahrungsfrist für das vorläufige Löschen betrachtet, weil ein Wiederherstellen der Gruppe während dieses Zeitraums noch möglich ist. Nach 30 Tagen werden die Gruppe und die zugehörigen Inhalte endgültig gelöscht und können nicht wiederhergestellt werden.

Beim Wiederherstellen einer Gruppe werden folgende Inhalte wiederhergestellt:
  
- Objekte, Eigenschaften und Mitglieder von Microsoft 365-Gruppen in Azure Active Directory (AD).
    
- E-Mail-Adressen von Gruppen.
    
- Der freigegebene Posteingang und Kalender in Exchange Online.
    
- Die SharePoint Online-Teamwebsite und die entsprechenden Dateien.
    
- OneNote-Notizbuch
    
- Planner
    
- Microsoft Teams

- Yammer-Gruppe und Gruppeninhalt (wenn die Microsoft 365-Gruppe aus Yammer erstellt wurde)

> [!NOTE]
> In diesem Artikel wird nur die Wiederherstellung von Microsoft 365-Gruppen beschrieben. Alle anderen Gruppen können nach dem Löschen nicht wiederhergestellt werden.

## <a name="restore-a-group"></a>Wiederherstellen einer Gruppe

# <a name="outlook"></a>[Outlook](#tab/outlook)

Wenn Sie der Besitzer einer Microsoft 365-Gruppe sind, können Sie die Gruppe selbst in Outlook im Web wiederherstellen, indem Sie die folgenden Schritte ausführen:

1. Wählen Sie auf der Seite [Gelöschte Gruppen](https://outlook.office.com/people/group/deleted)die Option **Gruppen verwalten** unter dem Knoten **Gruppen** und dann **Gelöscht** aus.

2. Klicken Sie auf die Schaltfläche **Wiederherstellen** neben der Gruppe, die Sie wiederherstellen möchten.

Wenn die gelöschte Gruppe hier nicht angezeigt wird, wenden Sie sich an einen Administrator.

# <a name="admin-center"></a>[Admin Center](#tab/admin-center)

Wenn Sie ein globaler Administrator oder ein Gruppenadministrator sind, können Sie eine gelöschte Gruppe im Microsoft 365 Admin Center wiederherstellen:

1. Wechseln Sie zum [Admin Center](https://admin.microsoft.com).
2. Erweitern Sie **Gruppen**, und klicken Sie dann auf **Gelöschte Gruppen**.
3. Wählen Sie die Gruppe aus, die Sie wiederherstellen möchten, und klicken Sie dann auf **Gruppe wiederherstellen**.

> [!NOTE]
> In einigen Fällen kann es bis zu 24 Stunden dauern, bis die Gruppe und alle zugehörigen Daten wiederhergestellt wurden. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Haben Sie Fragen zu Microsoft 365-Gruppen?

Besuchen Sie die [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups), um Fragen zu posten und an Unterhaltungen zu Microsoft 365-Gruppen teilzunehmen. 
  
## <a name="related-articles"></a>Verwandte Artikel

[Verwalten von Microsoft 365-Gruppen mit PowerShell](../../enterprise/manage-microsoft-365-groups-with-powershell.md)
  
[Löschen von Gruppen mit dem Cmdlet "Remove-UnifiedGroup"](/powershell/module/exchange/remove-unifiedgroup)
  
[Verwalten Ihrer gruppenabhängigen Teamwebsiteeinstellungen](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Löschen einer Gruppe in Outlook 2016](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)