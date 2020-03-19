---
title: Entfernen einer Domäne aus Office 365
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Hier erfahren Sie, wie Sie eine alte Domäne aus Office 365 entfernen und Benutzer und Gruppen in eine andere Domäne verlagern.
ms.openlocfilehash: efbd49daa28b5d15989e1531929cb2d9355aeb8f
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857427"
---
# <a name="remove-a-domain-from-office-365"></a><span data-ttu-id="ee1bc-103">Entfernen einer Domäne aus Office 365</span><span class="sxs-lookup"><span data-stu-id="ee1bc-103">Remove a domain from Office 365</span></span>

<span data-ttu-id="ee1bc-104">[] Mitwirkende: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span><span class="sxs-lookup"><span data-stu-id="ee1bc-104">Contributors: [![Peter Baumgartner](../../media/e70dc696-c5f8-4717-a48b-9087431503e7.png)](https://go.microsoft.com/fwlink/p/?linkid=847121)</span></span>
  
 <span data-ttu-id="ee1bc-105">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-105">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="ee1bc-p101">Entfernen Sie Ihre Domäne, weil Sie sie einem anderen Office 365-Abonnementplan hinzufügen möchten? Oder möchten Sie Ihr Abonnement einfach nur kündigen? Sie können [Ihren Plan oder Ihr Abonnement ändern](../../commerce/subscriptions/switch-to-a-different-plan.md) oder [Ihr Abonnement kündigen](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-p101">Are you removing your domain because you want to add it to a different Office 365 subscription plan? Or do you just want to cancel your subscription? You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="ee1bc-109">Schritt 1: verlagern von Benutzern in eine andere Domäne</span><span class="sxs-lookup"><span data-stu-id="ee1bc-109">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="ee1bc-110">Benutzer verlagern</span><span class="sxs-lookup"><span data-stu-id="ee1bc-110">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="ee1bc-111">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-111">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="ee1bc-112">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="ee1bc-113">Wählen Sie **Benutzer** > **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="ee1bc-114">Aktivieren Sie die Kontrollkästchen neben den Namen aller Benutzer, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="ee1bc-115">Wählen Sie **Weitere Optionen** (**...**) oben auf der Seite aus, und wählen Sie dann **Domänen ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="ee1bc-116">Wählen Sie im Bereich **Domänen ändern** eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="ee1bc-p102">Sie müssen diesen Vorgang auch für die eigene E-Mail-Adresse ausführen, wenn Sie Mitglied der Domäne sind, die Sie entfernen möchten. Wenn Sie die Domäne für Ihr Konto bearbeiten, müssen Sie sich abmelden und mit der ausgewählten neuen Domäne wieder anmelden, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-p102">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ee1bc-119">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="ee1bc-120">Wählen Sie **Benutzer** > **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="ee1bc-121">Aktivieren Sie die Kontrollkästchen neben den Namen aller Benutzer, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="ee1bc-122">Klicken Sie oben auf der Seite auf **Weitere** > **Bearbeiten von Domänen**.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="ee1bc-123">Wählen Sie im Bereich **Bearbeiten von Domänen** eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="ee1bc-p103">Sie müssen diesen Vorgang auch für die eigene E-Mail-Adresse ausführen, wenn Sie Mitglied der Domäne sind, die Sie entfernen möchten. Wenn Sie die Domäne für Ihr Konto bearbeiten, müssen Sie sich abmelden und mit der ausgewählten neuen Domäne wieder anmelden, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ee1bc-126">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="ee1bc-127">Wählen Sie **Benutzer** > **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="ee1bc-128">Aktivieren Sie die Kontrollkästchen neben den Namen aller Benutzer, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="ee1bc-129">Klicken Sie oben auf der Seite auf **Weitere** > **Bearbeiten von Domänen**.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="ee1bc-130">Wählen Sie im Bereich **Bearbeiten von Domänen** eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="ee1bc-p104">Sie müssen diesen Vorgang auch für die eigene E-Mail-Adresse ausführen, wenn Sie Mitglied der Domäne sind, die Sie entfernen möchten. Wenn Sie die Domäne für Ihr Konto bearbeiten, müssen Sie sich abmelden und mit der ausgewählten neuen Domäne wieder anmelden, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="ee1bc-133">Selbst positionieren</span><span class="sxs-lookup"><span data-stu-id="ee1bc-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="ee1bc-134">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-134">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="ee1bc-135">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-135">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="ee1bc-136">Wechseln Sie zu **Benutzer** \> **aktive Benutzer**, und wählen Sie Ihr Konto aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-136">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="ee1bc-137">Wählen Sie auf der Registerkarte **Konto** die Option **Benutzername verwalten**aus, und wählen Sie dann eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-137">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="ee1bc-138">Wählen Sie oben Ihren Kontonamen aus, und wählen Sie **Abmelden aus**.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-138">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="ee1bc-139">Melden Sie sich mit der neuen Domäne und ihrem gleichen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-139">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="ee1bc-140">Sie können Sie auch PowerShell verwenden, um Benutzer in eine andere Domäne zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-140">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="ee1bc-141">Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-141">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="ee1bc-142">Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-142">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ee1bc-143">Wechseln Sie zu **Benutzer** \> **aktive Benutzer**, und wählen Sie in der Liste Ihren Namen aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-143">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="ee1bc-144">Wählen Sie im Abschnitt **Benutzername/e-Mail** die Option **Bearbeiten**aus, und wählen Sie dann eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-144">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="ee1bc-145">Wählen Sie **als primären** > **Speicher** > **Schließen**festlegen aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-145">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="ee1bc-146">Wählen Sie oben Ihren Kontonamen aus, und wählen Sie **Abmelden aus**.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-146">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="ee1bc-147">Melden Sie sich mit der neuen Domäne und ihrem gleichen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-147">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="ee1bc-148">Sie können Sie auch PowerShell verwenden, um Benutzer in eine andere Domäne zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-148">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="ee1bc-149">Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-149">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="ee1bc-150">Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-150">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ee1bc-151">Wechseln Sie zu **Benutzer** \> **aktive Benutzer**, und wählen Sie in der Liste Ihren Namen aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-151">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="ee1bc-152">Wählen Sie im Abschnitt **Benutzername/e-Mail** die Option **Bearbeiten**aus, und wählen Sie dann eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-152">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="ee1bc-153">Wählen Sie **als primären** > **Speicher** > **Schließen**festlegen aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-153">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="ee1bc-154">Wählen Sie oben Ihren Kontonamen aus, und wählen Sie **Abmelden aus**.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-154">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="ee1bc-155">Melden Sie sich mit der neuen Domäne und ihrem gleichen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-155">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="ee1bc-156">Sie können Sie auch PowerShell verwenden, um Benutzer in eine andere Domäne zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-156">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="ee1bc-157">Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-157">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="ee1bc-158">Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-158">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="ee1bc-159">Schritt 2: Gruppen in eine andere Domäne verlagern</span><span class="sxs-lookup"><span data-stu-id="ee1bc-159">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ee1bc-160">Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-160">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="ee1bc-161">Wählen Sie den Gruppennamen aus, und wählen Sie dann auf der Registerkarte **Allgemein** unter **e-Mail-Adresse, primär**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-161">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="ee1bc-162">Wählen Sie in der Dropdownliste eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-162">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="ee1bc-163">Wählen Sie **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-163">Select **Save**, then **Close**.</span></span> <span data-ttu-id="ee1bc-164">Wiederholen Sie diesen Vorgang für alle Gruppen oder Verteilerlisten, die der Domäne zugeordnet sind, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-164">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ee1bc-165">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a>zur Seite **Gruppen** > **Gruppen.**</span><span class="sxs-lookup"><span data-stu-id="ee1bc-165">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="ee1bc-166">Wählen Sie den Gruppennamen aus, und klicken Sie dann neben **Name**auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-166">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="ee1bc-167">Wählen Sie in der Dropdownliste eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-167">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="ee1bc-168">Wählen Sie **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-168">Select **Save**, then **Close**.</span></span> <span data-ttu-id="ee1bc-169">Wiederholen Sie diesen Vorgang für alle Gruppen oder Verteilerlisten, die der Domäne zugeordnet sind, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-169">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ee1bc-170">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>zur Seite **Gruppen** > **Gruppen.**</span><span class="sxs-lookup"><span data-stu-id="ee1bc-170">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="ee1bc-171">Wählen Sie den Gruppennamen aus, und klicken Sie dann neben **Name**auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-171">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="ee1bc-172">Wählen Sie in der Dropdownliste eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-172">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="ee1bc-173">Wählen Sie **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-173">Select **Save**, then **Close**.</span></span> <span data-ttu-id="ee1bc-174">Wiederholen Sie diesen Vorgang für alle Gruppen oder Verteilerlisten, die der Domäne zugeordnet sind, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-174">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="ee1bc-175">Schritt 3: Entfernen der alten Domäne</span><span class="sxs-lookup"><span data-stu-id="ee1bc-175">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="ee1bc-176">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-176">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="ee1bc-177">Wechseln Sie im Admin Center zur Seite **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="ee1bc-178">Wechseln Sie im Admin Center zur Seite **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="ee1bc-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="ee1bc-179">Wählen Sie auf der Seite **Domänen** die Domäne aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-179">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="ee1bc-180">Wählen Sie im rechten Bereich **Entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-180">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="ee1bc-181">Befolgt alle weiteren Eingabeaufforderungen, und wählen Sie dann **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-181">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="ee1bc-182">Wie lange dauert es, bis eine Domäne entfernt wurde?</span><span class="sxs-lookup"><span data-stu-id="ee1bc-182">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="ee1bc-183">Es kann weniger als 5 Minuten dauern, bis Office 365 eine Domäne entfernen, wenn Sie nicht an vielen Stellen wie Sicherheitsgruppen, Verteilerlisten, Benutzern und Office 365 Gruppen referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-183">It can take as little as 5 minutes for Office 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Office 365 groups.</span></span> <span data-ttu-id="ee1bc-184">Wenn es viele Verweise gibt, die die Domäne verwenden, kann es mehrere Stunden (einen Tag) dauern, bis die Domäne entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-184">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="ee1bc-p112">Wenn Sie über Hunderte oder Tausende von Benutzern verfügen, verwenden Sie PowerShell, um alle Benutzer abzufragen und in eine andere Domäne zu verschieben. Andernfalls könnte es passieren, dass einige Benutzer der Benutzeroberfläche vergessen werden. Wenn dann das Entfernen der Domäne nicht möglich ist, wissen Sie nicht, warum. Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="ee1bc-p112">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="ee1bc-189">Benötigen Sie weitere Hilfe?</span><span class="sxs-lookup"><span data-stu-id="ee1bc-189">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="ee1bc-190">Sie können die [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx)-Domäne nicht aus Ihrem Konto entfernen.</span><span class="sxs-lookup"><span data-stu-id="ee1bc-190">You can't remove the [".onmicrosoft.com"](https://support.office.com/article/b9fc3018-8844-43f3-8db1-1b3a8e9cfd5a.aspx) domain from your account.</span></span>
  
<span data-ttu-id="ee1bc-p113">Funktioniert es immer noch nicht? Die Domäne muss möglicherweise manuell entfernt werden. [Rufen Sie uns an](../contact-support-for-business-products.md), und wir helfen Ihnen bei der Problemlösung!</span><span class="sxs-lookup"><span data-stu-id="ee1bc-p113">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="ee1bc-194">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="ee1bc-194">Related articles</span></span>

[<span data-ttu-id="ee1bc-195">Häufig gestellte Fragen zu Domänen</span><span class="sxs-lookup"><span data-stu-id="ee1bc-195">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="ee1bc-196">Hilfe zu Office 365-Domänen erhalten</span><span class="sxs-lookup"><span data-stu-id="ee1bc-196">Get help with Office 365 domains</span></span>](get-help-with-domains.yml)

[<span data-ttu-id="ee1bc-197">Wechseln zu einem anderen Office 365 Business-Plan</span><span class="sxs-lookup"><span data-stu-id="ee1bc-197">Switch to a different Office 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="ee1bc-198">Kündigen Ihres Abonnements</span><span class="sxs-lookup"><span data-stu-id="ee1bc-198">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
