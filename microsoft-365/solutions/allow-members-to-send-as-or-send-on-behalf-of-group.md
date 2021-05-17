---
title: Zulassen, dass Mitglieder im Namen einer Gruppe senden oder senden
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
description: Erfahren Sie, wie Sie Gruppenmitgliedern das Senden von E-Mails als Microsoft 365 oder das Senden von E-Mails im Namen einer Microsoft 365 ermöglichen.
ms.openlocfilehash: cc0a9472f127fae94d77f618ed7347d844879ba8
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904744"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Zulassen, dass Mitglieder im Namen einer Gruppe senden oder senden

Ein Mitglied einer Microsoft 365, dem die Berechtigungen **Senden** als oder Senden im Auftrag erteilt wurden, kann E-Mails als Gruppe oder im Namen der Gruppe senden.  (Gästen in der Gruppe können diese Berechtigungen nicht erteilt werden.)

In diesem Artikel wird erläutert, wie ein globaler oder Exchange diese Berechtigungen festlegen kann.
  
Wenn Megan Bowen z. B. Teil der Gruppe  **Training** Microsoft 365 ist und über Die Berechtigung Senden als Berechtigung für  die Gruppe verfügt, sieht es aus, als würde die Schulungsgruppe die E-Mail gesendet, wenn sie eine E-Mail als Gruppe sendet. 
  
Mit der Berechtigung Senden **im Auftrag** kann ein Benutzer E-Mails im Namen einer Microsoft 365 senden. Wenn Alex Wilber z. B. Teil der **Gruppe Marketing**  Microsoft 365 ist und über Berechtigungen für "Senden im Auftrag" verfügt und eine E-Mail als Gruppe sendet, sieht die E-Mail so aus, als ob sie von **Alex Wilber** im Namen von Marketing gesendet wurde.

> [!IMPORTANT]
> Sie können **Senden als** oder Senden im Auftrag **eines** bestimmten Benutzers konfigurieren, aber nicht beides. Wenn Sie beides konfigurieren, wird standardmäßig **Senden als verwendet.**

> [!TIP]
> Weitere [Informationen zur](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) Verwendung von Outlook und Outlook im Web zum Senden von E-Mails von einer Gruppe finden Sie unter Senden von E-Mails von oder im Namen einer Microsoft 365-Gruppe.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Zulassen, dass Mitglieder E-Mails als Gruppe senden

In diesem Abschnitt wird erläutert, wie Benutzern das Senden von E-Mails als Gruppe im [Exchange Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.
  
1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>zu  \> **Empfängergruppen**.
    
2. Wählen **Sie Gruppensymbol** bearbeiten in der Gruppe aus, die Benutzer ![ senden können ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) möchten.   
    
3. Wählen Sie **Gruppendelegierung** aus.
    
4. Wählen Sie **im Abschnitt** Senden als das Zeichen aus, um die Benutzer hinzuzufügen, die Sie als Gruppe **+** senden möchten. 
    
    ![Screenshot des Dialogfelds "Senden als"](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Geben Sie einen Namen ein, um einen Benutzer zu suchen, oder wählen Sie ihn aus der Liste aus. Wählen Sie **OK** und **Speichern aus.**
    
    ![Geben Sie ein, um einen Benutzer in der Liste zu suchen oder zu wählen.](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Zulassen, dass Mitglieder E-Mails im Namen einer Gruppe senden

In diesem Abschnitt wird erläutert, wie Benutzern das Senden von E-Mails im Namen einer Gruppe im Exchange Admin Center (EAC) in Exchange Online.
  
1. Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>zu  \> **Empfängergruppen**.
    
2. Wählen **Sie Gruppensymbol** bearbeiten in der Gruppe aus, die Benutzer ![ senden können ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) möchten. 
    
3. Wählen Sie **Gruppendelegierung** aus.
    
4. Wählen Sie im Abschnitt Senden im Auftrag das Zeichen aus, um die Benutzer hinzuzufügen, die Sie **+** als Gruppe senden möchten. 
    
    ![Screenshot des Sendens im Auftrag des Dialogfelds](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Geben Sie einen Namen ein, um einen Benutzer zu suchen, oder wählen Sie ihn aus der Liste aus. Wählen Sie **OK** und **Speichern aus.**
    
    ![Geben Sie ein, um einen Benutzer in der Liste zu suchen oder zu wählen.](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Verwandte Artikel

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)

[Weitere Informationen zu Microsoft 365 Gruppen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)

[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup)