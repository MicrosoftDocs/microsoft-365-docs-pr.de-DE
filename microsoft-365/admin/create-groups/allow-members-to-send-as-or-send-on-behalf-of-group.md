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
# <a name="allow-members-to-send-as-or-send-on-behalf-of-a-group"></a><span data-ttu-id="e393a-103">Mitgliedern das Senden als oder senden im Auftrag einer Gruppe gestatten</span><span class="sxs-lookup"><span data-stu-id="e393a-103">Allow members to send as or send on behalf of a Group</span></span>

<span data-ttu-id="e393a-104">Ein Mitglied einer Microsoft 365-Gruppe, denen die Berechtigung " **Senden als** " oder " **Senden im Auftrag** von" erteilt wurde, kann e-Mails als Gruppe oder im Namen der Gruppe senden.</span><span class="sxs-lookup"><span data-stu-id="e393a-104">A member of a Microsoft 365 group who has been granted **Send as** or **Send on behalf** permissions can send email as the group, or on behalf of the group.</span></span> <span data-ttu-id="e393a-105">In diesem Thema wird erläutert, wie ein Administrator diese Berechtigungen festlegen kann.</span><span class="sxs-lookup"><span data-stu-id="e393a-105">This topic explains how an admin can set these permissions.</span></span>
  
<span data-ttu-id="e393a-106">Wenn Megan Bowen beispielsweise Teil der Microsoft 365- **Schulungs** Gruppe ist und über die Berechtigung " **Senden als** " für die Gruppe verfügt, wenn Sie eine e-Mail-Nachricht als Gruppe sendet, sieht Sie aus wie die Gruppe " **Training** ", die die e-Mail gesendet hat.</span><span class="sxs-lookup"><span data-stu-id="e393a-106">For example, if Megan Bowen is part of the **Training** Microsoft 365 group, and has **Send as** permissions on the group, if she sends an email as the group, it will look like the **Training** group sent the email.</span></span> 
  
<span data-ttu-id="e393a-107">Mit der Berechtigung " **Senden im Auftrag** von" kann ein Benutzer e-Mails im Auftrag einer Microsoft 365-Gruppe senden.</span><span class="sxs-lookup"><span data-stu-id="e393a-107">The **Send on Behalf** permission lets a user send email on behalf of a Microsoft 365 group.</span></span> <span data-ttu-id="e393a-108">Wenn beispielsweise Alex Wilber ein Teil der Microsoft 365- **Marketing** Gruppe ist und über die Berechtigung " **Senden im Auftrag** von" verfügt und eine e-Mail als Gruppe sendet, sieht die e-Mail so aus, als ob Sie von **Alex Wilber im Auftrag von Marketing**gesendet wurde.</span><span class="sxs-lookup"><span data-stu-id="e393a-108">For example, if Alex Wilber is a part of the **Marketing** Microsoft 365 group, and has **Send on Behalf** permissions and sends an email as the group, the email looks like it was sent by **Alex Wilber on behalf of Marketing**.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e393a-109">Sie können " **Senden als** " oder " **Senden im Auftrag** von" für einen bestimmten Benutzer konfigurieren, jedoch nicht für beide.</span><span class="sxs-lookup"><span data-stu-id="e393a-109">You can configure **Send as** or **Send on behalf** for a given user, but not both.</span></span> <span data-ttu-id="e393a-110">Wenn Sie beides konfigurieren, ist es standardmäßig **Senden als**.</span><span class="sxs-lookup"><span data-stu-id="e393a-110">If you configure both, it will default to **Send as**.</span></span>

> [!TIP]
> <span data-ttu-id="e393a-111">Informationen zum Verwenden von Outlook und Outlook im Internet zum Senden von e-Mails aus einer Gruppe finden Sie unter [Senden von e-Mails aus oder im Namen einer Microsoft 365-Gruppe](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) .</span><span class="sxs-lookup"><span data-stu-id="e393a-111">See [Send email from or on behalf of a Microsoft 365 group](https://support.microsoft.com/office/0f4964af-aec6-484b-a65c-0434df8cdb6b) to learn how to use Outlook and Outlook on the Web to send email from a group.</span></span>
    
## <a name="allow-members-to-send-email-as-a-group"></a><span data-ttu-id="e393a-112">Zulassen, dass Mitglieder e-Mails als Gruppe senden</span><span class="sxs-lookup"><span data-stu-id="e393a-112">Allow members to send email as a group</span></span>

<span data-ttu-id="e393a-113">In diesem Abschnitt wird erläutert, wie Sie Benutzern das Senden von e-Mails als Gruppe im [Exchange Admin Center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e393a-113">This section explains how to allow users to send email as a group in the [Exchange admin center](https://go.microsoft.com/fwlink/p/?linkid=2059104) (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="e393a-114">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="e393a-114">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="e393a-115">Wählen **Edit**Sie Edit ![ Group Symbol bearbeiten ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) in der Gruppe aus, die Sie Benutzern erlauben möchten, als zu senden.  </span><span class="sxs-lookup"><span data-stu-id="e393a-115">Select **Edit**  ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="e393a-116">Wählen Sie **Gruppendelegierung** aus.</span><span class="sxs-lookup"><span data-stu-id="e393a-116">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="e393a-117">Wählen Sie im Abschnitt **Senden als** das Zeichen aus, **+** um die Benutzer hinzuzufügen, die Sie als Gruppe senden möchten.</span><span class="sxs-lookup"><span data-stu-id="e393a-117">In the **Send As** section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Wählen Sie das Pluszeichen aus, um die Benutzer hinzuzufügen, die Sie als Microsoft 365-Gruppe senden möchten.](../../media/1df167f6-1eff-4f98-9ecd-4230fab46557.png)
  
5. <span data-ttu-id="e393a-119">Geben Sie einen Namen ein, um einen Benutzer zu suchen, oder wählen Sie ihn aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="e393a-119">Type to search or pick a user from the list.</span></span> <span data-ttu-id="e393a-120">Wählen Sie **OK** und **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="e393a-120">Select **OK** and **Save**.</span></span>
    
    ![Typ zum Suchen oder Auswählen eines Benutzers aus der Liste](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)
  
## <a name="allow-members-to-send-email-on-behalf-of-a-group"></a><span data-ttu-id="e393a-122">Zulassen, dass Mitglieder e-Mail-Nachrichten im Auftrag einer Gruppe senden</span><span class="sxs-lookup"><span data-stu-id="e393a-122">Allow members to send email on behalf of a group</span></span>

<span data-ttu-id="e393a-123">In diesem Abschnitt wird erläutert, wie Sie Benutzern das Senden von e-Mails im Namen einer Gruppe im Exchange Admin Center (EAC) in Exchange Online ermöglichen.</span><span class="sxs-lookup"><span data-stu-id="e393a-123">This section explains how to allow users to send email on behalf of a group in the Exchange admin center (EAC) in Exchange Online.</span></span>
  
1. <span data-ttu-id="e393a-124">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>zu **Empfänger** \> **Gruppen**.</span><span class="sxs-lookup"><span data-stu-id="e393a-124">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>, go to **Recipients** \> **Groups**.</span></span>
    
2. <span data-ttu-id="e393a-125">Wählen **Edit** Sie Edit ![ Group Icon bearbeiten ](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) in der Gruppe aus, der Sie Benutzern das Senden als erlauben möchten.</span><span class="sxs-lookup"><span data-stu-id="e393a-125">Select **Edit** ![Edit group icon](../../media/0cfcb590-dc51-4b4f-9276-bb2ce300d87e.png) on the Group that you want to allow users to send as.</span></span> 
    
3. <span data-ttu-id="e393a-126">Wählen Sie **Gruppendelegierung** aus.</span><span class="sxs-lookup"><span data-stu-id="e393a-126">Select **group delegation**.</span></span>
    
4. <span data-ttu-id="e393a-127">Wählen Sie im Abschnitt Senden im Auftrag das **+** Vorzeichen aus, um die Benutzer hinzuzufügen, die Sie als Gruppe senden möchten.</span><span class="sxs-lookup"><span data-stu-id="e393a-127">In the Send on Behalf section, select the **+** sign to add the users that you want to send as the Group.</span></span> 
    
    ![Wählen Sie das Pluszeichen aus, um die Benutzer hinzuzufügen, die Sie als Microsoft 365-Gruppe senden möchten.](../../media/2bae0579-8907-4d6b-8920-ddd6555897b4.png)
  
5. <span data-ttu-id="e393a-129">Geben Sie einen Namen ein, um einen Benutzer zu suchen, oder wählen Sie ihn aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="e393a-129">Type to search or pick a user from the list.</span></span> <span data-ttu-id="e393a-130">Wählen Sie **OK** und **Speichern**aus.</span><span class="sxs-lookup"><span data-stu-id="e393a-130">Select **OK** and **Save**.</span></span>
    
    ![Typ zum Suchen oder Auswählen eines Benutzers aus der Liste](../../media/522919cf-664c-4a25-8076-c51c8c9fbe43.png)

## <a name="related-articles"></a><span data-ttu-id="e393a-132">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="e393a-132">Related articles</span></span>

[<span data-ttu-id="e393a-133">Weitere Informationen zu Microsoft 365-Gruppen</span><span class="sxs-lookup"><span data-stu-id="e393a-133">Learn more about Microsoft 365 groups</span></span>](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

[<span data-ttu-id="e393a-134">Add-RecipientPermission</span><span class="sxs-lookup"><span data-stu-id="e393a-134">Add-RecipientPermission</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=723960)

[<span data-ttu-id="e393a-135">Set-UnifiedGroup</span><span class="sxs-lookup"><span data-stu-id="e393a-135">Set-UnifiedGroup</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=616189)
