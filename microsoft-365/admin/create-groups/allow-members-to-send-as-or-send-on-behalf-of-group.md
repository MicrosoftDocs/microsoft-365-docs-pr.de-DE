---
title: Mitgliedern das Senden als oder senden im Auftrag einer Gruppe gestatten
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Hier erfahren Sie, wie Sie Mitgliedern erlauben, e-Mails als Microsoft 365-Gruppe zu senden oder e-Mails im Namen einer Microsoft 365-Gruppe zu senden.
ms.openlocfilehash: 3a93dda83b10d7c38c8c6e7d8fd484b37df565d0
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780469"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Mitgliedern das Senden als oder senden im Auftrag einer Gruppe gestatten

Ein Mitglied einer Microsoft 365-Gruppe, denen die Berechtigung " **Senden als** " oder " **Senden im Auftrag** von" erteilt wurde, kann e-Mails als Gruppe oder im Namen der Gruppe senden. In diesem Thema wird erläutert, wie ein Administrator diese Berechtigungen festlegen kann.
  
Wenn Megan Bowen beispielsweise Teil der Microsoft 365- **Schulungs** Gruppe ist und über die Berechtigung " **Senden als** " für die Gruppe verfügt, wenn Sie eine e-Mail-Nachricht als Gruppe sendet, sieht Sie aus wie die Gruppe " **Training** ", die die e-Mail gesendet hat. 
  
Mit der Berechtigung " **Senden im Auftrag** von" kann ein Benutzer e-Mails im Auftrag einer Microsoft 365-Gruppe senden. Wenn beispielsweise Alex Wilber ein Teil der Microsoft 365- **Marketing** Gruppe ist und über die Berechtigung " **Senden im Auftrag** von" verfügt und eine e-Mail als Gruppe sendet, sieht die e-Mail so aus, als ob Sie von **Alex Wilber im Auftrag von Marketing**gesendet wurde.

> [!IMPORTANT]
> Sie können " **Senden als** " oder " **Senden im Auftrag** von" für einen bestimmten Benutzer konfigurieren, jedoch nicht für beide. Wenn Sie beides konfigurieren, ist es standardmäßig **Senden als**.

> [!TIP]
> Informationen zum Verwenden von Outlook und Outlook im Internet zum Senden von e-Mails aus einer Gruppe finden Sie unter [Senden von e-Mails aus oder im Namen einer Microsoft 365-Gruppe](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) .
    
## <a name="allow-members-to-send-email-as-a-group"></a>Zulassen, dass Mitglieder e-Mails als Gruppe senden

In diesem Abschnitt wird erläutert, wie Sie Benutzern das Senden von e-Mails als Gruppe im [Exchange Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online ermöglichen.
  
1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>zu **Empfänger** \> **Gruppen**.
    
2. Wählen **Edit**Sie Edit ![ Group Symbol bearbeiten ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) in der Gruppe aus, die Sie Benutzern erlauben möchten, als zu senden.   
    
3. Wählen Sie **Gruppendelegierung** aus.
    
4. Wählen Sie im Abschnitt **Senden als** das Zeichen aus, **+** um die Benutzer hinzuzufügen, die Sie als Gruppe senden möchten. 
    
    ![Wählen Sie das Pluszeichen aus, um die Benutzer hinzuzufügen, die Sie als Microsoft 365-Gruppe senden möchten.](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Geben Sie einen Namen ein, um einen Benutzer zu suchen, oder wählen Sie ihn aus der Liste aus. Wählen Sie **OK** und **Speichern**aus.
    
    ![Typ zum Suchen oder Auswählen eines Benutzers aus der Liste](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Zulassen, dass Mitglieder e-Mail-Nachrichten im Auftrag einer Gruppe senden

In diesem Abschnitt wird erläutert, wie Sie Benutzern das Senden von e-Mails im Namen einer Gruppe im Exchange Admin Center (EAC) in Exchange Online ermöglichen.
  
1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>zu **Empfänger** \> **Gruppen**.
    
2. Wählen **Edit** Sie Edit ![ Group Icon bearbeiten ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) in der Gruppe aus, der Sie Benutzern das Senden als erlauben möchten. 
    
3. Wählen Sie **Gruppendelegierung** aus.
    
4. Wählen Sie im Abschnitt Senden im Auftrag das **+** Vorzeichen aus, um die Benutzer hinzuzufügen, die Sie als Gruppe senden möchten. 
    
    ![Wählen Sie das Pluszeichen aus, um die Benutzer hinzuzufügen, die Sie als Microsoft 365-Gruppe senden möchten.](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Geben Sie einen Namen ein, um einen Benutzer zu suchen, oder wählen Sie ihn aus der Liste aus. Wählen Sie **OK** und **Speichern**aus.
    
    ![Typ zum Suchen oder Auswählen eines Benutzers aus der Liste](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Verwandte Artikel

[Weitere Informationen zu Microsoft 365-Gruppen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[Set-UnifiedGroup](https://go.microsoft.com/fwlink/p/?LinkId=616189)
