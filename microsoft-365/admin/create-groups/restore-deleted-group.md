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
description: Informationen zum Wiederherstellen einer gelöschten Microsoft 365-Gruppe.
ms.openlocfilehash: 091697be54b1127a5cb336179733d51519947e14
ms.sourcegitcommit: 3cdb670f10519f7af4015731e7910954ba9f70dc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48753243"
---
# <a name="restore-a-deleted-microsoft-365-group"></a>Wiederherstellen einer gelöschten Microsoft 365-Gruppe

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

> [!NOTE]
> In diesem Artikel wird das Wiederherstellen nur von Microsoft 365 Gruppen beschrieben. Alle anderen Gruppen können nicht wiederhergestellt werden, nachdem Sie gelöscht wurden.

## <a name="restore-a-group"></a>Wiederherstellen einer Gruppe

# <a name="outlook"></a>[Outlook](#tab/outlook)

Wenn Sie der Besitzer einer Microsoft 365-Gruppe sind, können Sie die Gruppe selbst in Outlook im Internet wiederherstellen, indem Sie die folgenden Schritte ausführen:

1. Wählen Sie auf der Seite [Gelöschte Gruppen](https://outlook.office.com/people/group/deleted)die Option **Gruppen verwalten** unter dem Knoten **Gruppen** und dann **Gelöscht** aus.

2. Klicken Sie auf die Schaltfläche **Wiederherstellen** neben der Gruppe, die Sie wiederherstellen möchten.

Wenn die gelöschte Gruppe hier nicht angezeigt wird, wenden Sie sich an einen Administrator.

# <a name="admin-center"></a>[Admin Center](#tab/admin-center)

Wenn Sie globaler Administrator oder Gruppenadministrator sind, können Sie eine gelöschte Gruppe im Microsoft 365 Admin Center wiederherstellen:

1. Wechseln Sie zum [Admin Center](https://admin.microsoft.com).
2. Erweitern Sie **Gruppen**, und klicken Sie dann auf **Gelöschte Gruppen**.
3. Wählen Sie die Gruppe aus, die Sie wiederherstellen möchten, und klicken Sie dann auf **Gruppe wiederherstellen**.

> [!NOTE]
> In einigen Fällen kann es bis zu 24 Stunden dauern, bis die Gruppe und alle Daten wiederhergestellt werden. 

---

## <a name="got-questions-about-microsoft-365-groups"></a>Haben Sie Fragen zu Microsoft 365-Gruppen?

Besuchen Sie die [Microsoft Tech Community](https://techcommunity.microsoft.com/t5/Office-365-Groups/ct-p/Office365Groups) , um Fragen zu veröffentlichen und an Unterhaltungen zu Microsoft 365-Gruppen teilzunehmen. 
  
## <a name="related-articles"></a>Verwandte Artikel

[Verwalten von Microsoft 365-Gruppen mit PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-groups-with-powershell)
  
[Löschen von Gruppen mit dem Cmdlet "Remove-UnifiedGroup"](https://technet.microsoft.com/library/mt238270%28v=exchg.160%29.aspx)
  
[Verwalten Ihrer gruppenabhängigen Teamwebsiteeinstellungen](https://support.microsoft.com/office/8376034d-d0c7-446e-9178-6ab51c58df42)
  
[Löschen einer Gruppe in Outlook 2016](https://support.microsoft.com/office/ca7f5a9e-ae4f-4cbe-a4bc-89c469d1726f)
