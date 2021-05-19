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
recommendations: false
description: Erfahren Sie, wie Sie Gruppenmitgliedern das Senden von E-Mails als Microsoft 365 oder das Senden von E-Mails im Namen einer Microsoft 365 ermöglichen.
ms.openlocfilehash: 07db8f415da46e6235c051e262237de79e61c8b9
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538255"
---
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="5b51f-103">Zulassen, dass Mitglieder im Namen einer Gruppe senden oder senden</span><span class="sxs-lookup"><span data-stu-id="5b51f-103">Allow members to send as or send on behalf of a group</span></span>

<span data-ttu-id="5b51f-104">Ein Mitglied einer Microsoft 365, dem die Berechtigungen **Senden** als oder Senden im Auftrag erteilt wurden, kann E-Mails als Gruppe oder im Namen der Gruppe senden. </span><span class="sxs-lookup"><span data-stu-id="5b51f-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="5b51f-105">(Gästen in der Gruppe können diese Berechtigungen nicht erteilt werden.)</span><span class="sxs-lookup"><span data-stu-id="5b51f-105">(Guests in the group cannot be granted these permissions.)</span></span>

<span data-ttu-id="5b51f-106">In diesem Artikel wird erläutert, wie ein globaler oder Exchange diese Berechtigungen festlegen kann.</span><span class="sxs-lookup"><span data-stu-id="5b51f-106">This article explains how a global or Exchange administrator can set these permissions.</span></span>
  
<span data-ttu-id="5b51f-107">Wenn Megan Bowen z. B. Teil der Gruppe  **Training** Microsoft 365 ist und über Die Berechtigung Senden als Berechtigung für  die Gruppe verfügt, sieht es aus, als würde die Schulungsgruppe die E-Mail gesendet, wenn sie eine E-Mail als Gruppe sendet.</span><span class="sxs-lookup"><span data-stu-id="5b51f-107">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="5b51f-108">Mit der Berechtigung Senden **im Auftrag** kann ein Benutzer E-Mails im Namen einer Microsoft 365 senden.</span><span class="sxs-lookup"><span data-stu-id="5b51f-108">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="5b51f-109">Wenn Alex Wilber z. B. Teil der **Gruppe Marketing**  Microsoft 365 ist und über Berechtigungen für "Senden im Auftrag" verfügt und eine E-Mail als Gruppe sendet, sieht die E-Mail so aus, als ob sie von **Alex Wilber** im Namen von Marketing gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="5b51f-109">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5b51f-110">Sie können **Senden als** oder Senden im Auftrag **eines** bestimmten Benutzers konfigurieren, aber nicht beides.</span><span class="sxs-lookup"><span data-stu-id="5b51f-110">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="5b51f-111">Wenn Sie beides konfigurieren, wird standardmäßig **Senden als verwendet.**</span><span class="sxs-lookup"><span data-stu-id="5b51f-111">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="5b51f-112">Weitere [Informationen zur](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) Verwendung von Outlook und Outlook im Web zum Senden von E-Mails von einer Gruppe finden Sie unter Senden von E-Mails von oder im Namen einer Microsoft 365-Gruppe.</span><span class="sxs-lookup"><span data-stu-id="5b51f-112">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="5b51f-113">Zulassen, dass Mitglieder E-Mails als Gruppe senden</span><span class="sxs-lookup"><span data-stu-id="5b51f-113">Allow members to send email as a group</span></span>

<span data-ttu-id="5b51f-114">In diesem Abschnitt wird erläutert, wie Benutzern das Senden von E-Mails als Gruppe im [Exchange Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5b51f-114">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="5b51f-115">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>zu  \> **Empfängergruppen**.</span><span class="sxs-lookup"><span data-stu-id="5b51f-115">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="5b51f-116">Wählen **Sie Gruppensymbol** bearbeiten in der Gruppe aus, die Benutzer ![ senden können ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) möchten.  </span><span class="sxs-lookup"><span data-stu-id="5b51f-116">Select **Edit**  ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="5b51f-117">Wählen Sie **Gruppendelegierung** aus.</span><span class="sxs-lookup"><span data-stu-id="5b51f-117">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="5b51f-118">Wählen Sie **im Abschnitt** Senden als das Zeichen aus, um die Benutzer hinzuzufügen, die Sie als Gruppe **+** senden möchten.</span><span class="sxs-lookup"><span data-stu-id="5b51f-118">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Screenshot des Dialogfelds "Senden als"](../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="5b51f-120">Geben Sie einen Namen ein, um einen Benutzer zu suchen, oder wählen Sie ihn aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="5b51f-120">Type to search or pick a user from the list.</span></span> <span data-ttu-id="5b51f-121">Wählen Sie **OK** und **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="5b51f-121">Select **OK** and **Save**.</span></span>
    
    ![Geben Sie ein, um einen Benutzer in der Liste zu suchen oder zu wählen.](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="5b51f-123">Zulassen, dass Mitglieder E-Mails im Namen einer Gruppe senden</span><span class="sxs-lookup"><span data-stu-id="5b51f-123">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="5b51f-124">In diesem Abschnitt wird erläutert, wie Benutzern das Senden von E-Mails im Namen einer Gruppe im Exchange Admin Center (EAC) in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="5b51f-124">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="5b51f-125">Wechseln Sie <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>zu  \> **Empfängergruppen**.</span><span class="sxs-lookup"><span data-stu-id="5b51f-125">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="5b51f-126">Wählen **Sie Gruppensymbol** bearbeiten in der Gruppe aus, die Benutzer ![ senden können ](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) möchten.</span><span class="sxs-lookup"><span data-stu-id="5b51f-126">Select **Edit** ![Edit group icon](../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="5b51f-127">Wählen Sie **Gruppendelegierung** aus.</span><span class="sxs-lookup"><span data-stu-id="5b51f-127">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="5b51f-128">Wählen Sie im Abschnitt Senden im Auftrag das Zeichen aus, um die Benutzer hinzuzufügen, die Sie **+** als Gruppe senden möchten.</span><span class="sxs-lookup"><span data-stu-id="5b51f-128">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Screenshot des Sendens im Auftrag des Dialogfelds](../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="5b51f-130">Geben Sie einen Namen ein, um einen Benutzer zu suchen, oder wählen Sie ihn aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="5b51f-130">Type to search or pick a user from the list.</span></span> <span data-ttu-id="5b51f-131">Wählen Sie **OK** und **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="5b51f-131">Select **OK** and **Save**.</span></span>
    
    ![Geben Sie ein, um einen Benutzer in der Liste zu suchen oder zu wählen.](../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="5b51f-133">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="5b51f-133">Related articles</span></span>

[<span data-ttu-id="5b51f-134">Schritt-für-Schritt-Planung für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="5b51f-134">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="5b51f-135">Erstellen eines Plans für die Zusammenarbeitsgovernance</span><span class="sxs-lookup"><span data-stu-id="5b51f-135">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="5b51f-136">Weitere Informationen zu Microsoft 365 Gruppen</span><span class="sxs-lookup"><span data-stu-id="5b51f-136">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="5b51f-137">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="5b51f-137">Add-RecipientPermission</span></span>](/powershell/module/exchange/add-recipientpermission)

[<span data-ttu-id="5b51f-138">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="5b51f-138">Set-UnifiedGroup</span></span>](/powershell/module/exchange/set-unifiedgroup)