---
title: Entfernen einer Domäne
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- Adm_O365_Setup
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Hier erfahren Sie, wie Sie eine alte Domäne aus Microsoft 365 entfernen und Benutzer und Gruppen in eine andere Domäne verlagern.
ms.openlocfilehash: 6f5e36a897316c8cdc057a725957c54e7eb53edc
ms.sourcegitcommit: 5b769f74bcc76ac8d38aad815d1728824783cd9f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2020
ms.locfileid: "45079761"
---
# <a name="remove-a-domain"></a><span data-ttu-id="e1a5e-103">Entfernen einer Domäne</span><span class="sxs-lookup"><span data-stu-id="e1a5e-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="e1a5e-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-104">The admin center is changing.</span></span> <span data-ttu-id="e1a5e-105">Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="e1a5e-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="e1a5e-106">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="e1a5e-107">Entfernen Sie Ihre Domäne, da Sie Sie einem anderen Microsoft 365-Abonnementplan hinzufügen möchten?</span><span class="sxs-lookup"><span data-stu-id="e1a5e-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="e1a5e-108">Oder möchten Sie Ihr Abonnement einfach nur kündigen?</span><span class="sxs-lookup"><span data-stu-id="e1a5e-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="e1a5e-109">Sie können [Ihren Plan oder Ihr Abonnement ändern](../../commerce/subscriptions/switch-to-a-different-plan.md) oder [Ihr Abonnement kündigen](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="e1a5e-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="e1a5e-110">Schritt 1: verlagern von Benutzern in eine andere Domäne</span><span class="sxs-lookup"><span data-stu-id="e1a5e-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="e1a5e-111">Benutzer verlagern</span><span class="sxs-lookup"><span data-stu-id="e1a5e-111">Move users</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e1a5e-112">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-112">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="e1a5e-113">Wählen Sie **Benutzer** > **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-113">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e1a5e-114">Aktivieren Sie die Kontrollkästchen neben den Namen aller Benutzer, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-114">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e1a5e-115">Wählen Sie **Weitere Optionen** (**...**) oben auf der Seite aus, und wählen Sie dann **Domänen ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-115">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="e1a5e-116">Wählen Sie im Bereich **Domänen ändern** eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-116">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="e1a5e-p103">Sie müssen diesen Vorgang auch für die eigene E-Mail-Adresse ausführen, wenn Sie Mitglied der Domäne sind, die Sie entfernen möchten. Wenn Sie die Domäne für Ihr Konto bearbeiten, müssen Sie sich abmelden und mit der ausgewählten neuen Domäne wieder anmelden, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e1a5e-119">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-119">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="e1a5e-120">Wählen Sie **Benutzer** > **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-120">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e1a5e-121">Aktivieren Sie die Kontrollkästchen neben den Namen aller Benutzer, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-121">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e1a5e-122">Klicken Sie oben auf der Seite auf **Weitere** > **Bearbeiten von Domänen**.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-122">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="e1a5e-123">Wählen Sie im Bereich **Bearbeiten von Domänen** eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-123">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="e1a5e-p104">Sie müssen diesen Vorgang auch für die eigene E-Mail-Adresse ausführen, wenn Sie Mitglied der Domäne sind, die Sie entfernen möchten. Wenn Sie die Domäne für Ihr Konto bearbeiten, müssen Sie sich abmelden und mit der ausgewählten neuen Domäne wieder anmelden, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e1a5e-126">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-126">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="e1a5e-127">Wählen Sie **Benutzer** > **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-127">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="e1a5e-128">Aktivieren Sie die Kontrollkästchen neben den Namen aller Benutzer, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-128">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="e1a5e-129">Klicken Sie oben auf der Seite auf **Weitere** > **Bearbeiten von Domänen**.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-129">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="e1a5e-130">Wählen Sie im Bereich **Bearbeiten von Domänen** eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-130">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="e1a5e-p105">Sie müssen diesen Vorgang auch für die eigene E-Mail-Adresse ausführen, wenn Sie Mitglied der Domäne sind, die Sie entfernen möchten. Wenn Sie die Domäne für Ihr Konto bearbeiten, müssen Sie sich abmelden und mit der ausgewählten neuen Domäne wieder anmelden, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="e1a5e-133">Selbst positionieren</span><span class="sxs-lookup"><span data-stu-id="e1a5e-133">Move yourself</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e1a5e-134">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-134">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="e1a5e-135">Wechseln Sie zu **Benutzer** \> **aktive Benutzer**, und wählen Sie Ihr Konto aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-135">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="e1a5e-136">Wählen Sie auf der Registerkarte **Konto** die Option **Benutzername verwalten**aus, und wählen Sie dann eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-136">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="e1a5e-137">Wählen Sie oben Ihren Kontonamen aus, und wählen Sie **Abmelden aus**.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-137">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e1a5e-138">Melden Sie sich mit der neuen Domäne und ihrem gleichen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-138">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e1a5e-139">Sie können Sie auch PowerShell verwenden, um Benutzer in eine andere Domäne zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-139">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e1a5e-140">Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="e1a5e-140">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e1a5e-141">Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="e1a5e-141">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e1a5e-142">Wechseln Sie zu **Benutzer** \> **aktive Benutzer**, und wählen Sie in der Liste Ihren Namen aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-142">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="e1a5e-143">Wählen Sie im Abschnitt **Benutzername/e-Mail** die Option **Bearbeiten**aus, und wählen Sie dann eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-143">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="e1a5e-144">Wählen Sie **als primären** > **Speicher** > **Schließen**festlegen aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-144">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="e1a5e-145">Wählen Sie oben Ihren Kontonamen aus, und wählen Sie **Abmelden aus**.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-145">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e1a5e-146">Melden Sie sich mit der neuen Domäne und ihrem gleichen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-146">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e1a5e-147">Sie können Sie auch PowerShell verwenden, um Benutzer in eine andere Domäne zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-147">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e1a5e-148">Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="e1a5e-148">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e1a5e-149">Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="e1a5e-149">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e1a5e-150">Wechseln Sie zu **Benutzer** \> **aktive Benutzer**, und wählen Sie in der Liste Ihren Namen aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-150">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="e1a5e-151">Wählen Sie im Abschnitt **Benutzername/e-Mail** die Option **Bearbeiten**aus, und wählen Sie dann eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-151">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="e1a5e-152">Wählen Sie **als primären** > **Speicher** > **Schließen**festlegen aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-152">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="e1a5e-153">Wählen Sie oben Ihren Kontonamen aus, und wählen Sie **Abmelden aus**.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-153">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="e1a5e-154">Melden Sie sich mit der neuen Domäne und ihrem gleichen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-154">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="e1a5e-155">Sie können Sie auch PowerShell verwenden, um Benutzer in eine andere Domäne zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-155">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="e1a5e-156">Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="e1a5e-156">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="e1a5e-157">Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="e1a5e-157">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="e1a5e-158">Schritt 2: Gruppen in eine andere Domäne verlagern</span><span class="sxs-lookup"><span data-stu-id="e1a5e-158">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e1a5e-159">Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-159">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="e1a5e-160">Wählen Sie den Gruppennamen aus, und wählen Sie dann auf der Registerkarte **Allgemein** unter **e-Mail-Adresse, primär**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-160">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="e1a5e-161">Wählen Sie in der Dropdownliste eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-161">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e1a5e-162">Wählen Sie **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-162">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e1a5e-163">Wiederholen Sie diesen Vorgang für alle Gruppen oder Verteilerlisten, die der Domäne zugeordnet sind, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-163">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e1a5e-164">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a>zur Seite **Gruppen** > **Gruppen** .</span><span class="sxs-lookup"><span data-stu-id="e1a5e-164">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="e1a5e-165">Wählen Sie den Gruppennamen aus, und klicken Sie dann neben **Name**auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="e1a5e-165">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="e1a5e-166">Wählen Sie in der Dropdownliste eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-166">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e1a5e-167">Wählen Sie **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-167">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e1a5e-168">Wiederholen Sie diesen Vorgang für alle Gruppen oder Verteilerlisten, die der Domäne zugeordnet sind, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-168">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e1a5e-169">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>zur Seite **Gruppen** > **Gruppen** .</span><span class="sxs-lookup"><span data-stu-id="e1a5e-169">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="e1a5e-170">Wählen Sie den Gruppennamen aus, und klicken Sie dann neben **Name**auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="e1a5e-170">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="e1a5e-171">Wählen Sie in der Dropdownliste eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-171">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="e1a5e-172">Wählen Sie **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-172">Select **Save**, then **Close**.</span></span> <span data-ttu-id="e1a5e-173">Wiederholen Sie diesen Vorgang für alle Gruppen oder Verteilerlisten, die der Domäne zugeordnet sind, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-173">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="e1a5e-174">Schritt 3: Entfernen der alten Domäne</span><span class="sxs-lookup"><span data-stu-id="e1a5e-174">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="e1a5e-175">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-175">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="e1a5e-176">Wechseln Sie im Admin Center zur Seite **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="e1a5e-176">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="e1a5e-177">Wechseln Sie im Admin Center zur Seite **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="e1a5e-177">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="e1a5e-178">Wählen Sie auf der Seite **Domänen** die Domäne aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-178">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="e1a5e-179">Wählen Sie im rechten Bereich **Entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-179">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="e1a5e-180">Befolgt alle weiteren Eingabeaufforderungen, und wählen Sie dann **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-180">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="e1a5e-181">Wie lange dauert es, bis eine Domäne entfernt wurde?</span><span class="sxs-lookup"><span data-stu-id="e1a5e-181">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="e1a5e-182">Es kann weniger als 5 Minuten dauern, bis Microsoft 365 eine Domäne entfernt, wenn Sie nicht an vielen Stellen wie Sicherheitsgruppen, Verteilerlisten, Benutzern und Microsoft 365-Gruppen referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-182">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="e1a5e-183">Wenn es viele Verweise gibt, die die Domäne verwenden, kann es mehrere Stunden (einen Tag) dauern, bis die Domäne entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-183">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="e1a5e-p113">Wenn Sie über Hunderte oder Tausende von Benutzern verfügen, verwenden Sie PowerShell, um alle Benutzer abzufragen und in eine andere Domäne zu verschieben. Andernfalls könnte es passieren, dass einige Benutzer der Benutzeroberfläche vergessen werden. Wenn dann das Entfernen der Domäne nicht möglich ist, wissen Sie nicht, warum. Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="e1a5e-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="e1a5e-188">Benötigen Sie weitere Hilfe?</span><span class="sxs-lookup"><span data-stu-id="e1a5e-188">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="e1a5e-189">Sie können die [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)-Domäne nicht aus Ihrem Konto entfernen.</span><span class="sxs-lookup"><span data-stu-id="e1a5e-189">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="e1a5e-p114">Funktioniert es immer noch nicht? Die Domäne muss möglicherweise manuell entfernt werden. [Rufen Sie uns an](../contact-support-for-business-products.md), und wir helfen Ihnen bei der Problemlösung!</span><span class="sxs-lookup"><span data-stu-id="e1a5e-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="e1a5e-193">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="e1a5e-193">Related articles</span></span>

[<span data-ttu-id="e1a5e-194">Häufig gestellte Fragen zu Domänen</span><span class="sxs-lookup"><span data-stu-id="e1a5e-194">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="e1a5e-195">Erhalten von Hilfe zu Microsoft 365-Domänen</span><span class="sxs-lookup"><span data-stu-id="e1a5e-195">Get help with Microsoft 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="e1a5e-196">Wechseln zu einem anderen Microsoft 365 Business-Plan</span><span class="sxs-lookup"><span data-stu-id="e1a5e-196">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="e1a5e-197">Kündigen Ihres Abonnements</span><span class="sxs-lookup"><span data-stu-id="e1a5e-197">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
