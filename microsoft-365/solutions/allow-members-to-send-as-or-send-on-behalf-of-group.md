---
title: Mitgliedern das Senden als oder senden im Namen einer Gruppe gestatten
ms.reviewer: arvaradh
f1.keywords: NOCSH
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
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 0ad41414-0cc6-4b97-90fb-06bec7bcf590
recommendations: false
description: Erfahren Sie, wie Sie Gruppenmitgliedern das Senden von E-Mails als Microsoft 365 Gruppe oder das Senden von E-Mails im Namen einer Microsoft 365 Gruppe gestatten.
ms.openlocfilehash: 437040700361c6a09b107a87d8228d2a156375d1
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926139"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a>Mitgliedern das Senden als oder senden im Namen einer Gruppe gestatten

Ein Mitglied einer Microsoft 365-Gruppe, dem die Berechtigung **"Senden als"** oder **"Senden im Auftrag von"** gewährt wurde, kann E-Mails als Gruppe oder im Namen der Gruppe senden. (Gästen in der Gruppe können diese Berechtigungen nicht gewährt werden.)

In diesem Artikel wird erläutert, wie ein globaler oder Exchange Administrator diese Berechtigungen festlegen kann.
  
Wenn Megan Bowen beispielsweise Teil der Gruppe **"Training** Microsoft 365" ist und über die Berechtigung **"Senden als"** für die Gruppe verfügt und eine E-Mail als Gruppe sendet, sieht es so aus, als hätte die **Schulungsgruppe** die E-Mail gesendet. 
  
Mit der Berechtigung **"Senden im Auftrag von"** kann ein Benutzer E-Mails im Namen einer Microsoft 365 Gruppe senden. Wenn Alex Wilber beispielsweise Teil der Gruppe **"Marketing** Microsoft 365" ist und über Die Berechtigung **"Senden im Auftrag von"** verfügt und eine E-Mail als Gruppe sendet, sieht die E-Mail so aus, als ob sie von **Alex Wilber im Auftrag von Marketing** gesendet wurde.

> [!IMPORTANT]
> Sie können **"Senden als"** oder **"Senden im Auftrag** eines bestimmten Benutzers" konfigurieren, aber nicht beides. Wenn Sie beide konfigurieren, wird standardmäßig **"Senden als" verwendet.**

> [!TIP]
> Unter [Senden von E-Mails von oder im Namen einer Microsoft 365 Gruppe](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) erfahren Sie, wie Sie Outlook und Outlook im Web verwenden, um E-Mails von einer Gruppe zu senden.
    
## <a name="allow-members-to-send-email-as-a-group"></a>Mitgliedern das Senden von E-Mails als Gruppe gestatten

In diesem Abschnitt wird erläutert, wie Benutzer E-Mails als Gruppe im [Exchange Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online senden können.
  
1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>zu  \> **Empfängergruppen.**
    
2. Wählen Sie ![ das Gruppensymbol Bearbeiten in der Gruppe ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) aus, an die Benutzer senden dürfen.   
    
3. Wählen Sie **Gruppendelegierung** aus.
    
4. Wählen Sie im Abschnitt **"Senden als"** das Zeichen aus, **+** um die Benutzer hinzuzufügen, die Sie als Gruppe senden möchten. 
    
    ![Screenshot des Dialogfelds "Senden als"](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. Geben Sie einen Namen ein, um einen Benutzer zu suchen, oder wählen Sie ihn aus der Liste aus. Wählen Sie **"OK"** und **"Speichern" aus.**
    
    ![Geben Sie ein, um einen Benutzer in der Liste zu suchen oder aus der Liste zu wählen](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a>Mitgliedern das Senden von E-Mails im Namen einer Gruppe gestatten

In diesem Abschnitt wird erläutert, wie Benutzer E-Mails im Namen einer Gruppe im Exchange Admin Center (EAC) in Exchange Online senden können.
  
1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>zu  \> **Empfängergruppen.**
    
2. Wählen  Sie ![ das Gruppensymbol Bearbeiten in der Gruppe ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) aus, an die Benutzer senden dürfen. 
    
3. Wählen Sie **Gruppendelegierung** aus.
    
4. Wählen Sie im Abschnitt "Senden im Auftrag von" das Zeichen aus, **+** um die Benutzer hinzuzufügen, die Sie als Gruppe senden möchten. 
    
    ![Screenshot des Dialogfelds "Senden im Auftrag von"](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. Geben Sie einen Namen ein, um einen Benutzer zu suchen, oder wählen Sie ihn aus der Liste aus. Wählen Sie **"OK"** und **"Speichern" aus.**
    
    ![Geben Sie ein, um einen Benutzer in der Liste zu suchen oder aus der Liste zu wählen](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a>Verwandte Artikel

[Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[Erstellen eines Plans für die Zusammenarbeitsgovernance](collaboration-governance-first.md)

[Weitere Informationen zu Microsoft 365-Gruppen](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[Add-RecipientPermission](/powershell/module/exchange/add-recipientpermission)

[Set-UnifiedGroup](/powershell/module/exchange/set-unifiedgroup)