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
search.appverid:
- BCS160
- MET150
- MOE150
- GEA150
ms.assetid: f09696b2-8c29-4588-a08b-b333da19810c
description: Hier erfahren Sie, wie Sie eine alte Domäne aus Microsoft 365 entfernen und Benutzer und Gruppen in eine andere Domäne verlagern.
ms.openlocfilehash: ef0209d6ccb7534745172585fe599f627e386cb4
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140405"
---
# <a name="remove-a-domain"></a><span data-ttu-id="1e1d3-103">Entfernen einer Domäne</span><span class="sxs-lookup"><span data-stu-id="1e1d3-103">Remove a domain</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="1e1d3-104">Das Admin Center wird geändert.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-104">The admin center is changing.</span></span> <span data-ttu-id="1e1d3-105">Wenn Ihre Erfahrung nicht mit den hier dargestellten Details übereinstimmt, lesen Sie [Informationen zum neuen Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="1e1d3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end
  
 <span data-ttu-id="1e1d3-106">**[Überprüfen Sie die häufig gestellten Fragen (FAQ) zu Domänen](../setup/domains-faq.md)**, wenn Sie nicht finden, wonach Sie suchen.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-106">**[Check the Domains FAQ](../setup/domains-faq.md)** if you don't find what you're looking for.</span></span> 
  
<span data-ttu-id="1e1d3-107">Entfernen Sie Ihre Domäne, da Sie Sie einem anderen Microsoft 365-Abonnementplan hinzufügen möchten?</span><span class="sxs-lookup"><span data-stu-id="1e1d3-107">Are you removing your domain because you want to add it to a different Microsoft 365 subscription plan?</span></span> <span data-ttu-id="1e1d3-108">Oder möchten Sie Ihr Abonnement einfach nur kündigen?</span><span class="sxs-lookup"><span data-stu-id="1e1d3-108">Or do you just want to cancel your subscription?</span></span> <span data-ttu-id="1e1d3-109">Sie können [Ihren Plan oder Ihr Abonnement ändern](../../commerce/subscriptions/switch-to-a-different-plan.md) oder [Ihr Abonnement kündigen](../../commerce/subscriptions/cancel-your-subscription.md).</span><span class="sxs-lookup"><span data-stu-id="1e1d3-109">You can [change your plan or subscription](../../commerce/subscriptions/switch-to-a-different-plan.md) or [cancel your subscription](../../commerce/subscriptions/cancel-your-subscription.md).</span></span>
  
### <a name="step-1-move-users-to-another-domain"></a><span data-ttu-id="1e1d3-110">Schritt 1: verlagern von Benutzern in eine andere Domäne</span><span class="sxs-lookup"><span data-stu-id="1e1d3-110">Step 1: Move users to another domain</span></span>

#### <a name="move-users"></a><span data-ttu-id="1e1d3-111">Benutzer verlagern</span><span class="sxs-lookup"><span data-stu-id="1e1d3-111">Move users</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="1e1d3-112">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-112">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="1e1d3-113">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-113">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="1e1d3-114">Wählen Sie **Benutzer** > **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-114">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="1e1d3-115">Aktivieren Sie die Kontrollkästchen neben den Namen aller Benutzer, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-115">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="1e1d3-116">Wählen Sie **Weitere Optionen** (**...**) oben auf der Seite aus, und wählen Sie dann **Domänen ändern**aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-116">Select **More options** (**…**), at the top of the page, and then choose **Change domains**.</span></span>

5. <span data-ttu-id="1e1d3-117">Wählen Sie im Bereich **Domänen ändern** eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-117">In the **Change domains** pane, select a different domain.</span></span>

<span data-ttu-id="1e1d3-p103">Sie müssen diesen Vorgang auch für die eigene E-Mail-Adresse ausführen, wenn Sie Mitglied der Domäne sind, die Sie entfernen möchten. Wenn Sie die Domäne für Ihr Konto bearbeiten, müssen Sie sich abmelden und mit der ausgewählten neuen Domäne wieder anmelden, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-p103">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1e1d3-120">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-120">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="1e1d3-121">Wählen Sie **Benutzer** > **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-121">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="1e1d3-122">Aktivieren Sie die Kontrollkästchen neben den Namen aller Benutzer, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-122">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="1e1d3-123">Klicken Sie oben auf der Seite auf **Weitere** > **Bearbeiten von Domänen**.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-123">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="1e1d3-124">Wählen Sie im Bereich **Bearbeiten von Domänen** eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-124">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="1e1d3-p104">Sie müssen diesen Vorgang auch für die eigene E-Mail-Adresse ausführen, wenn Sie Mitglied der Domäne sind, die Sie entfernen möchten. Wenn Sie die Domäne für Ihr Konto bearbeiten, müssen Sie sich abmelden und mit der ausgewählten neuen Domäne wieder anmelden, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-p104">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1e1d3-127">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-127">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>  

2. <span data-ttu-id="1e1d3-128">Wählen Sie **Benutzer** > **aktive Benutzer**aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-128">Select **Users** > **Active users**.</span></span>

3. <span data-ttu-id="1e1d3-129">Aktivieren Sie die Kontrollkästchen neben den Namen aller Benutzer, die Sie migrieren möchten.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-129">Select the boxes next to the names of all the users you want to move.</span></span>

4. <span data-ttu-id="1e1d3-130">Klicken Sie oben auf der Seite auf **Weitere** > **Bearbeiten von Domänen**.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-130">At the top of the page, choose **More** > **Edit domains**.</span></span>

5. <span data-ttu-id="1e1d3-131">Wählen Sie im Bereich **Bearbeiten von Domänen** eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-131">In the **Edit domains** pane, select a different domain.</span></span>
  
<span data-ttu-id="1e1d3-p105">Sie müssen diesen Vorgang auch für die eigene E-Mail-Adresse ausführen, wenn Sie Mitglied der Domäne sind, die Sie entfernen möchten. Wenn Sie die Domäne für Ihr Konto bearbeiten, müssen Sie sich abmelden und mit der ausgewählten neuen Domäne wieder anmelden, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-p105">You'll need to do this for yourself, too, if you're on the domain that you want to remove. When you edit the domain for your account, you'll have to log out and log back in using the new domain you chose to continue.</span></span>

::: moniker-end

#### <a name="move-yourself"></a><span data-ttu-id="1e1d3-134">Selbst positionieren</span><span class="sxs-lookup"><span data-stu-id="1e1d3-134">Move yourself</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="1e1d3-135">Wenn Sie das neue Microsoft 365 Admin Center nicht verwenden, können Sie es aktivieren, indem Sie den Umschalter **Das neue Admin Center** am oberen Rand der Startseite auswählen.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-135">If you're not using the new Microsoft 365 admin center, you can turn it on by selecting the **Try the new admin center** toggle located at the top of the Home page.</span></span>

1. <span data-ttu-id="1e1d3-136">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-136">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>.</span></span>

2. <span data-ttu-id="1e1d3-137">Wechseln Sie zu **Benutzer** \> **aktive Benutzer**, und wählen Sie Ihr Konto aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-137">Go to **Users** \> **Active Users**, and select your account from the list.</span></span>

3. <span data-ttu-id="1e1d3-138">Wählen Sie auf der Registerkarte **Konto** die Option **Benutzername verwalten**aus, und wählen Sie dann eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-138">On the **Account** tab, select **Manage username**, and then choose a different domain.</span></span>
  
4. <span data-ttu-id="1e1d3-139">Wählen Sie oben Ihren Kontonamen aus, und wählen Sie **Abmelden aus**.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-139">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="1e1d3-140">Melden Sie sich mit der neuen Domäne und ihrem gleichen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-140">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="1e1d3-141">Sie können Sie auch PowerShell verwenden, um Benutzer in eine andere Domäne zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-141">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="1e1d3-142">Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="1e1d3-142">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="1e1d3-143">Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="1e1d3-143">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1e1d3-144">Wechseln Sie zu **Benutzer** \> **aktive Benutzer**, und wählen Sie in der Liste Ihren Namen aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-144">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="1e1d3-145">Wählen Sie im Abschnitt **Benutzername/e-Mail** die Option **Bearbeiten**aus, und wählen Sie dann eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-145">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="1e1d3-146">Wählen Sie **als primären** > **Speicher** > **Schließen**festlegen aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-146">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="1e1d3-147">Wählen Sie oben Ihren Kontonamen aus, und wählen Sie **Abmelden aus**.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-147">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="1e1d3-148">Melden Sie sich mit der neuen Domäne und ihrem gleichen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-148">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="1e1d3-149">Sie können Sie auch PowerShell verwenden, um Benutzer in eine andere Domäne zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-149">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="1e1d3-150">Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="1e1d3-150">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="1e1d3-151">Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="1e1d3-151">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1e1d3-152">Wechseln Sie zu **Benutzer** \> **aktive Benutzer**, und wählen Sie in der Liste Ihren Namen aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-152">Go to **Users** \> **Active Users**, and select your name in the list.</span></span>

2. <span data-ttu-id="1e1d3-153">Wählen Sie im Abschnitt **Benutzername/e-Mail** die Option **Bearbeiten**aus, und wählen Sie dann eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-153">In the **Username / Email** section, select **Edit**, and then choose a different domain.</span></span>

3. <span data-ttu-id="1e1d3-154">Wählen Sie **als primären** > **Speicher** > **Schließen**festlegen aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-154">Select **Set as primary** > **Save** > **Close**.</span></span>
  
4. <span data-ttu-id="1e1d3-155">Wählen Sie oben Ihren Kontonamen aus, und wählen Sie **Abmelden aus**.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-155">At the top, select your account name, then select **Sign Out**.</span></span>

5. <span data-ttu-id="1e1d3-156">Melden Sie sich mit der neuen Domäne und ihrem gleichen Kennwort an.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-156">Sign in with the new domain and your same password.</span></span>

<span data-ttu-id="1e1d3-157">Sie können Sie auch PowerShell verwenden, um Benutzer in eine andere Domäne zu verschieben.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-157">You can also use PowerShell to move users to another domain.</span></span> <span data-ttu-id="1e1d3-158">Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="1e1d3-158">See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information.</span></span> <span data-ttu-id="1e1d3-159">Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="1e1d3-159">To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>

::: moniker-end

### <a name="step-2-move-groups-to-another-domain"></a><span data-ttu-id="1e1d3-160">Schritt 2: Gruppen in eine andere Domäne verlagern</span><span class="sxs-lookup"><span data-stu-id="1e1d3-160">Step 2: Move groups to another domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1e1d3-161">Wechseln Sie im Admin Center zur Seite **Gruppen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Gruppen</a>.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-161">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>
  
2. <span data-ttu-id="1e1d3-162">Wählen Sie den Gruppennamen aus, und wählen Sie dann auf der Registerkarte **Allgemein** unter **e-Mail-Adresse, primär**die Option **Bearbeiten**aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-162">Select the group name, and then on the **General** tab under **Email address, Primary**, select **Edit**.</span></span>

3. <span data-ttu-id="1e1d3-163">Wählen Sie in der Dropdownliste eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-163">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="1e1d3-164">Wählen Sie **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-164">Select **Save**, then **Close**.</span></span> <span data-ttu-id="1e1d3-165">Wiederholen Sie diesen Vorgang für alle Gruppen oder Verteilerlisten, die der Domäne zugeordnet sind, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-165">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1e1d3-166">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a>zur Seite **Gruppen** > **Gruppen.**</span><span class="sxs-lookup"><span data-stu-id="1e1d3-166">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="1e1d3-167">Wählen Sie den Gruppennamen aus, und klicken Sie dann neben **Name**auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="1e1d3-167">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="1e1d3-168">Wählen Sie in der Dropdownliste eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-168">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="1e1d3-169">Wählen Sie **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-169">Select **Save**, then **Close**.</span></span> <span data-ttu-id="1e1d3-170">Wiederholen Sie diesen Vorgang für alle Gruppen oder Verteilerlisten, die der Domäne zugeordnet sind, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-170">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1e1d3-171">Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a>zur Seite **Gruppen** > **Gruppen.**</span><span class="sxs-lookup"><span data-stu-id="1e1d3-171">In the <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">admin center</a>,  go to the **Groups** > **Groups** page.</span></span>

2. <span data-ttu-id="1e1d3-172">Wählen Sie den Gruppennamen aus, und klicken Sie dann neben **Name**auf **Bearbeiten** .</span><span class="sxs-lookup"><span data-stu-id="1e1d3-172">Select the group name, and then select **Edit** next to **Name**.</span></span>

3. <span data-ttu-id="1e1d3-173">Wählen Sie in der Dropdownliste eine andere Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-173">Use the drop-down list to choose another domain.</span></span>

4. <span data-ttu-id="1e1d3-174">Wählen Sie **Speichern** und dann **Schließen** aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-174">Select **Save**, then **Close**.</span></span> <span data-ttu-id="1e1d3-175">Wiederholen Sie diesen Vorgang für alle Gruppen oder Verteilerlisten, die der Domäne zugeordnet sind, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-175">Repeat this process for any groups or distribution lists associated with the domain that you want to remove.</span></span>

::: moniker-end

### <a name="step-3-remove-the-old-domain"></a><span data-ttu-id="1e1d3-176">Schritt 3: Entfernen der alten Domäne</span><span class="sxs-lookup"><span data-stu-id="1e1d3-176">Step 3: Remove the old domain</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="1e1d3-177">Wechseln Sie im Admin Center zur Seite **Einstellungen** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domänen</a>.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-177">In the admin center, go to the **Settings** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834818" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="1e1d3-178">Wechseln Sie im Admin Center zur Seite **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="1e1d3-178">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=854615" target="_blank">Domains</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="1e1d3-179">Wechseln Sie im Admin Center zur Seite **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domänen</a> .</span><span class="sxs-lookup"><span data-stu-id="1e1d3-179">In the admin center, go to the **Setup** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2007048" target="_blank">Domains</a> page.</span></span>

::: moniker-end
  
2. <span data-ttu-id="1e1d3-180">Wählen Sie auf der Seite **Domänen** die Domäne aus, die Sie entfernen möchten.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-180">On the **Domains** page, select the domain that you want to remove.</span></span>

3. <span data-ttu-id="1e1d3-181">Wählen Sie im rechten Bereich **Entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-181">In the right pane, select **Remove**.</span></span>

4. <span data-ttu-id="1e1d3-182">Befolgt alle weiteren Eingabeaufforderungen, und wählen Sie dann **Schließen**aus.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-182">Follow any additional prompts, and then select **Close**.</span></span>

## <a name="how-long-does-it-take-for-a-domain-to-be-removed"></a><span data-ttu-id="1e1d3-183">Wie lange dauert es, bis eine Domäne entfernt wurde?</span><span class="sxs-lookup"><span data-stu-id="1e1d3-183">How long does it take for a domain to be removed?</span></span>

<span data-ttu-id="1e1d3-184">Es kann weniger als 5 Minuten dauern, bis Microsoft 365 eine Domäne entfernt, wenn Sie nicht an vielen Stellen wie Sicherheitsgruppen, Verteilerlisten, Benutzern und Microsoft 365-Gruppen referenziert wird.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-184">It can take as little as 5 minutes for Microsoft 365 to remove a domain if it's not referenced in a lot of places such as security groups, distribution lists, users, and Microsoft 365 groups.</span></span> <span data-ttu-id="1e1d3-185">Wenn es viele Verweise gibt, die die Domäne verwenden, kann es mehrere Stunden (einen Tag) dauern, bis die Domäne entfernt wird.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-185">If there are many references that use the domain it can take several hours (a day) for the domain to be removed.</span></span>
  
<span data-ttu-id="1e1d3-p113">Wenn Sie über Hunderte oder Tausende von Benutzern verfügen, verwenden Sie PowerShell, um alle Benutzer abzufragen und in eine andere Domäne zu verschieben. Andernfalls könnte es passieren, dass einige Benutzer der Benutzeroberfläche vergessen werden. Wenn dann das Entfernen der Domäne nicht möglich ist, wissen Sie nicht, warum. Weitere Informationen finden Sie unter [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0). Wenn die Standarddomäne festlegen möchten, verwenden Sie [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="1e1d3-p113">If you have hundreds or thousands of users, use PowerShell to query for all users and then move them to another domain. Otherwise, it's possible for a handful of users to be missed in the UI, and then when you go to remove the domain, you won't be able to and you won't know why. See [Set-MsolUserPrincipalName](https://docs.microsoft.com/powershell/module/msonline/set-msoluserprincipalname?view=azureadps-1.0) for more information. To set the default domain, use [Set-MsolDomain](https://docs.microsoft.com/powershell/module/msonline/set-msoldomain?view=azureadps-1.0).</span></span>
  
## <a name="still-need-help"></a><span data-ttu-id="1e1d3-190">Benötigen Sie weitere Hilfe?</span><span class="sxs-lookup"><span data-stu-id="1e1d3-190">Still need help?</span></span>

::: moniker range="o365-worldwide"

> [!NOTE]
> <span data-ttu-id="1e1d3-191">Sie können die [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq)-Domäne nicht aus Ihrem Konto entfernen.</span><span class="sxs-lookup"><span data-stu-id="1e1d3-191">You can't remove the [".onmicrosoft.com"](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) domain from your account.</span></span>
  
<span data-ttu-id="1e1d3-p114">Funktioniert es immer noch nicht? Die Domäne muss möglicherweise manuell entfernt werden. [Rufen Sie uns an](../contact-support-for-business-products.md), und wir helfen Ihnen bei der Problemlösung!</span><span class="sxs-lookup"><span data-stu-id="1e1d3-p114">Still not working? Your domain might need to be manually removed. [Give us a call](../contact-support-for-business-products.md) and we'll help you take care of it!</span></span>
  
::: moniker-end

## <a name="related-articles"></a><span data-ttu-id="1e1d3-195">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="1e1d3-195">Related articles</span></span>

[<span data-ttu-id="1e1d3-196">Häufig gestellte Fragen zu Domänen</span><span class="sxs-lookup"><span data-stu-id="1e1d3-196">Domains FAQ</span></span>](../setup/domains-faq.md)

[<span data-ttu-id="1e1d3-197">Hilfe zu Office 365-Domänen erhalten</span><span class="sxs-lookup"><span data-stu-id="1e1d3-197">Get help with Office 365 domains</span></span>](get-help-with-domains.md)

[<span data-ttu-id="1e1d3-198">Wechseln zu einem anderen Microsoft 365 Business-Plan</span><span class="sxs-lookup"><span data-stu-id="1e1d3-198">Switch to a different Microsoft 365 for business plan</span></span>](../../commerce/subscriptions/switch-to-a-different-plan.md)

[<span data-ttu-id="1e1d3-199">Kündigen Ihres Abonnements</span><span class="sxs-lookup"><span data-stu-id="1e1d3-199">Cancel your subscription</span></span>](../../commerce/subscriptions/cancel-your-subscription.md)
