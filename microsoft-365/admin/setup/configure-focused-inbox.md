---
title: Konfigurieren des Posteingangs mit Relevanz für jeden Benutzer in Ihrer Organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: 'Erfahren Sie, wie Sie den Posteingang mit Relevanz mit dem Posteingang für alle oder bestimmte Benutzer Ihrer Organisation konfigurieren. '
ms.openlocfilehash: f56e85e79fcf17cde89ec3d6094ca757ccf0cc68
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779929"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a><span data-ttu-id="e91b6-103">Konfigurieren des Posteingangs mit Relevanz für jeden Benutzer in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="e91b6-103">Configure Focused Inbox for everyone in your organization</span></span>

  <span data-ttu-id="e91b6-104">Wenn Sie dafür zuständig sind, die Funktion der E-Mail für JEDEN in einem Unternehmen zu konfigurieren, dann ist das genau der Artikel für Sie!</span><span class="sxs-lookup"><span data-stu-id="e91b6-104">If you're responsible for configuring how email works for EVERYONE in a business this article is for you!</span></span> <span data-ttu-id="e91b6-105">Es wird erläutert, wie Sie die E-Mail-Funktion für Ihr Unternehmen anpassen oder deaktivieren und beantwortet [Häufig gestellte Fragen](#faq-for-focused-inbox).</span><span class="sxs-lookup"><span data-stu-id="e91b6-105">It explains how to customize it or turn it off for your business, and answers [frequently asked questions](#faq-for-focused-inbox).</span></span>  <br/> <span data-ttu-id="e91b6-106">Wenn Sie den Posteingang mit Relevanz für sich selbst deaktivieren möchten, lesen Sie [Deaktivieren des Posteingangs mit Relevanz](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span><span class="sxs-lookup"><span data-stu-id="e91b6-106">If you would like to turn off Focused Inbox for just yourself, please see [Turn off Focused Inbox](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).</span></span>  
   
<span data-ttu-id="e91b6-107">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view.</span><span class="sxs-lookup"><span data-stu-id="e91b6-107">If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view.</span></span> <span data-ttu-id="e91b6-108">You can also control whether users in your organization see the Focused Inbox in their mailbox.</span><span class="sxs-lookup"><span data-stu-id="e91b6-108">You can also control whether users in your organization see the Focused Inbox in their mailbox.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a><span data-ttu-id="e91b6-109">Aktivieren oder Deaktivieren von "Posteingang mit Relevanz" in Ihrer Organisation</span><span class="sxs-lookup"><span data-stu-id="e91b6-109">Turn Focused Inbox On or Off in your organization</span></span>

<span data-ttu-id="e91b6-110">Sie verwenden PowerShell, um den Posteingang mit Relevanz für alle Benutzer in Ihrer Organisation zu aktivieren oder deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e91b6-110">You use PowerShell to turn Focused Inbox on or off for everyone in your organization.</span></span> <span data-ttu-id="e91b6-111">Möchten Sie diesen Vorgang im Microsoft 365 Admin Center ausführen?</span><span class="sxs-lookup"><span data-stu-id="e91b6-111">Do you want to do this in the Microsoft 365 admin center?</span></span> <span data-ttu-id="e91b6-112">Teilen Sie dies unserem Entwicklungsteam mit.</span><span class="sxs-lookup"><span data-stu-id="e91b6-112">Let our Engineering team know.</span></span> <span data-ttu-id="e91b6-113">**[Stimmen Sie hier ab!](https://go.microsoft.com/fwlink/?linkid=862489)**</span><span class="sxs-lookup"><span data-stu-id="e91b6-113">**[Vote here!](https://go.microsoft.com/fwlink/?linkid=862489)**</span></span>
  
 <span data-ttu-id="e91b6-114">**So deaktivieren Sie den Posteingang mit Relevanz:**</span><span class="sxs-lookup"><span data-stu-id="e91b6-114">**To turn off Focused Inbox:**</span></span>
  
<span data-ttu-id="e91b6-115">The following PowerShell example turns Focused Inbox **Off** in your organization.</span><span class="sxs-lookup"><span data-stu-id="e91b6-115">The following PowerShell example turns Focused Inbox **Off** in your organization.</span></span> <span data-ttu-id="e91b6-116">However, it doesn't block the availability of the feature for your users.</span><span class="sxs-lookup"><span data-stu-id="e91b6-116">However, it doesn't block the availability of the feature for your users.</span></span> <span data-ttu-id="e91b6-117">If they want, they can still re-enable Focused Inbox again on each of their clients.</span><span class="sxs-lookup"><span data-stu-id="e91b6-117">If they want, they can still re-enable Focused Inbox again on each of their clients.</span></span> 
  
1. <span data-ttu-id="e91b6-118">[Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="e91b6-118">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="e91b6-119">You need to be assigned permissions before you can perform this procedure or procedures.</span><span class="sxs-lookup"><span data-stu-id="e91b6-119">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="e91b6-120">To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span><span class="sxs-lookup"><span data-stu-id="e91b6-120">To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>
    
3. <span data-ttu-id="e91b6-121">Führen Sie das Cmdlet **Get-OrganizationConfig** aus.</span><span class="sxs-lookup"><span data-stu-id="e91b6-121">Run the **Get-OrganizationConfig** cmdlet.</span></span> 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. <span data-ttu-id="e91b6-122">Suchen Sie nach **FocusedInboxOn**, um die aktuelle Einstellung anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="e91b6-122">Look for **FocusedInboxOn** to view its current setting:</span></span> 
    
    ![Antwort von PowerShell zum Status des Posteingangs mit Relevanz.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="e91b6-124">Führen Sie das folgende Cmdlet aus, um "Posteingang mit Relevanz" zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e91b6-124">Run the following cmdlet to turn Focused Inbox off.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. <span data-ttu-id="e91b6-125">Führen Sie das Cmdlet **Get-OrganizationConfig** erneut aus, und Sie sehen, dass "FocusedInboxOn" auf "$false" festgelegt ist, d. h. dass der Posteingang mit Relevanz deaktiviert ist.</span><span class="sxs-lookup"><span data-stu-id="e91b6-125">Run the **Get-OrganizationConfig** cmdlet again and you'll see that FocusedInboxOn is set to $false, which means it's been turned off.</span></span> 
    
 <span data-ttu-id="e91b6-126">**So aktivieren Sie den Posteingang mit Relevanz:**</span><span class="sxs-lookup"><span data-stu-id="e91b6-126">**To turn on Focused Inbox:**</span></span>
  
- <span data-ttu-id="e91b6-127">Führen Sie in Schritt 5 oben das folgende Cmdlet aus, um "Posteingang mit Relevanz" zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="e91b6-127">In Step 5 above, run the following cmdlet to turn Focused Inbox on.</span></span>
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a><span data-ttu-id="e91b6-128">Was wird Benutzern angezeigt, nachdem der Posteingang mit Relevanz aktiviert wurde? </span><span class="sxs-lookup"><span data-stu-id="e91b6-128">What do users see after I turn on Focused Inbox?</span></span>

<span data-ttu-id="e91b6-129">Your users will see the Focused view only after they close and restart Outlook.</span><span class="sxs-lookup"><span data-stu-id="e91b6-129">Your users will see the Focused view only after they close and restart Outlook.</span></span> <span data-ttu-id="e91b6-130">When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span><span class="sxs-lookup"><span data-stu-id="e91b6-130">When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.</span></span>
  
![Die Abbildung zeigt, wie der Posteingang mit Relevanz aussieht, wenn ein Benutzer Outlook im Web zum ersten Mal öffnet.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
<span data-ttu-id="e91b6-132">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature.</span><span class="sxs-lookup"><span data-stu-id="e91b6-132">If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature.</span></span> <span data-ttu-id="e91b6-133">If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one.</span><span class="sxs-lookup"><span data-stu-id="e91b6-133">If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one.</span></span> <span data-ttu-id="e91b6-134">The tip looks like this:</span><span class="sxs-lookup"><span data-stu-id="e91b6-134">The tip looks like this:</span></span>
  
![So sieht der Posteingang mit Relevanz aus, wenn er für Ihre Benutzer bereitgestellt wurde und Outlook erneut geöffnet wird.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
<span data-ttu-id="e91b6-136">When a user decides to start using Focused Inbox, Clutter gets disabled automatically.</span><span class="sxs-lookup"><span data-stu-id="e91b6-136">When a user decides to start using Focused Inbox, Clutter gets disabled automatically.</span></span> <span data-ttu-id="e91b6-137">The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span><span class="sxs-lookup"><span data-stu-id="e91b6-137">The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.</span></span>
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a><span data-ttu-id="e91b6-138">Aktivieren oder Deaktivieren des Posteingangs mit Relevanz für bestimmte Benutzer</span><span class="sxs-lookup"><span data-stu-id="e91b6-138">Turn Focused Inbox On or Off for specific users</span></span>

<span data-ttu-id="e91b6-139">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization.</span><span class="sxs-lookup"><span data-stu-id="e91b6-139">This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization.</span></span> <span data-ttu-id="e91b6-140">However, it doesn't block the availability of the feature to him.</span><span class="sxs-lookup"><span data-stu-id="e91b6-140">However, it doesn't block the availability of the feature to him.</span></span> <span data-ttu-id="e91b6-141">If his wants, he can still re-enable Focused Inbox again on each of his clients.</span><span class="sxs-lookup"><span data-stu-id="e91b6-141">If his wants, he can still re-enable Focused Inbox again on each of his clients.</span></span> 
  
1. <span data-ttu-id="e91b6-142">[Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="e91b6-142">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="e91b6-143">You need to be assigned permissions before you can perform this procedure or procedures.</span><span class="sxs-lookup"><span data-stu-id="e91b6-143">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="e91b6-144">To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span><span class="sxs-lookup"><span data-stu-id="e91b6-144">To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.</span></span>
    
3. <span data-ttu-id="e91b6-145">Führen Sie das cmdlet **Get-FocusedInbox** aus, z. B.:</span><span class="sxs-lookup"><span data-stu-id="e91b6-145">Run the **Get-FocusedInbox** cmdlet, for example:</span></span> 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. <span data-ttu-id="e91b6-146">Suchen Sie nach "FocusedInboxOn", um die aktuelle Einstellung anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="e91b6-146">Look for FocusedInboxOn to view its current setting:</span></span>
    
    ![Antwort von PowerShell zum Status des Posteingangs mit Relevanz.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. <span data-ttu-id="e91b6-148">Führen Sie das folgende Cmdlet aus, um "Posteingang mit Relevanz" zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="e91b6-148">Run the following cmdlet to turn Focused Inbox off:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. <span data-ttu-id="e91b6-149">Oder führen Sie das folgende Cmdlet aus, um "Posteingang mit Relevanz" zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="e91b6-149">OR, run the following cmdlet to turn it on:</span></span>
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="e91b6-150">Verwenden der Benutzeroberfläche, um für alle Benutzer eine Transportregel zum Weiterleiten von E-Mail-Nachrichten an die Ansicht "Relevant" zu erstellen</span><span class="sxs-lookup"><span data-stu-id="e91b6-150">Use the UI to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="e91b6-151">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="e91b6-151">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
    
2. <span data-ttu-id="e91b6-152">Navigieren Sie zu **Nachrichtenfluss** \> **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="e91b6-152">Navigate to **mail flow** \> **Rules**.</span></span> <span data-ttu-id="e91b6-153">Wählen Sie ![EAC Symbol hinzufügen](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) und wählen Sie dann **Neue Regel erstellen...** aus.</span><span class="sxs-lookup"><span data-stu-id="e91b6-153">Select ![EAC Add icon](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) and then select **Create a new rule...**.</span></span> 
    
3. <span data-ttu-id="e91b6-154">Nachdem Sie die neue Regel erstellt haben, wählen Sie **Speichern**, um die Regel zu starten.</span><span class="sxs-lookup"><span data-stu-id="e91b6-154">After you're done creating the new rule, select **Save** to start the rule.</span></span> 
    
    <span data-ttu-id="e91b6-155">Die folgende Abbildung zeigt ein Beispiel, bei dem alle Nachrichten vom „Lohnbuchhaltung“ an den Posteingang mit Relevanz zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e91b6-155">The following image shows an example where all messages From "Payroll Department" are to be delivered to the Focused Inbox.</span></span>
    
    ![focusedinbox payroll](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a><span data-ttu-id="e91b6-157">Verwenden von PowerShell, um für alle Benutzer eine Transportregel zum Weiterleiten von E-Mail-Nachrichten an die Ansicht "Relevant" zu erstellen</span><span class="sxs-lookup"><span data-stu-id="e91b6-157">Use PowerShell to create a transport rule to direct email messages to the Focused view for all your users</span></span>

1. <span data-ttu-id="e91b6-158">[Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span><span class="sxs-lookup"><span data-stu-id="e91b6-158">[Connect to Exchange Online using remote PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=396554).</span></span>
    
2. <span data-ttu-id="e91b6-159">You need to be assigned permissions before you can perform this procedure or procedures.</span><span class="sxs-lookup"><span data-stu-id="e91b6-159">You need to be assigned permissions before you can perform this procedure or procedures.</span></span> <span data-ttu-id="e91b6-160">To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span><span class="sxs-lookup"><span data-stu-id="e91b6-160">To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).</span></span>

3. <span data-ttu-id="e91b6-161">Führen Sie den folgenden Befehl aus, um zuzulassen, dass alle Nachrichten beispielsweise von der Lohnbuchhaltung an den Posteingang mit Relevanz zugestellt werden.</span><span class="sxs-lookup"><span data-stu-id="e91b6-161">Run the following command to allow all messages from "Payroll Department," for example, to be delivered to the Focused Inbox.</span></span>
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> <span data-ttu-id="e91b6-162">In diesem Beispiel wird sowohl bei "X-MS-Exchange-Organization-BypassFocusedInbox" als auch bei "true" die Groß- und Kleinschreibung berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="e91b6-162">In this example, both "X-MS-Exchange-Organization-BypassFocusedInbox" and "true" are case sensitive.</span></span>
> <span data-ttu-id="e91b6-163">Der Posteingang mit Relevanz berücksichtigt den X-Header zur Umgehung von Clutter - wenn Sie diese Einstellung in "Clutter" verwenden, wird sie im Posteingang mit Relevanz verwendet.</span><span class="sxs-lookup"><span data-stu-id="e91b6-163">Also, Focused Inbox will honor the X-header that bypasses Clutter, so if you use this setting in Clutter, it will be used in Focused Inbox.</span></span> <span data-ttu-id="e91b6-164">Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).</span><span class="sxs-lookup"><span data-stu-id="e91b6-164">For detailed syntax and parameter information, see [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e91b6-165">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="e91b6-165">How do you know this worked?</span></span>

<span data-ttu-id="e91b6-166">Sie können die Kopfzeilen der E-Mail-Nachrichten überprüfen, um zu sehen, ob die E-Mail-Nachrichten basierend auf der Transportregelumleitung für den Posteingang mit Relevanz im Postfach ankommen.</span><span class="sxs-lookup"><span data-stu-id="e91b6-166">You can check email message headers to see if the email messages are landing in the Inbox due to the Focused Inbox transport rule bypass.</span></span> <span data-ttu-id="e91b6-167">Wählen Sie in einem Postfach in Ihrer Organisation eine E-Mail-Nachricht aus, auf die die Transportregel "Posteingang mit Relevanz" angewendet wird.</span><span class="sxs-lookup"><span data-stu-id="e91b6-167">Pick an email message from a mailbox in your organization that has the Focused Inbox transport rule applied.</span></span> <span data-ttu-id="e91b6-168">Schauen Sie sich die Kopfzeilen der Nachricht an. Hier sollte **X-MS-Exchange-Organization-BypassFocusedInbox: true** angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="e91b6-168">Look at the headers stamped on the message, and you should see the **X-MS-Exchange-Organization-BypassFocusedInbox: true** header.</span></span> <span data-ttu-id="e91b6-169">Dies bedeutet, dass die Umgehung funktioniert.</span><span class="sxs-lookup"><span data-stu-id="e91b6-169">This means the bypass is working.</span></span> <span data-ttu-id="e91b6-170">Informationen zum Anzeigen der Kopfzeileninformationen finden Sie unter [Anzeigen der Internetkopfzeileninformationen einer E-Mail-Nachricht](https://go.microsoft.com/fwlink/p/?LinkId=822530).</span><span class="sxs-lookup"><span data-stu-id="e91b6-170">Check out the [View the Internet header information for an email message](https://go.microsoft.com/fwlink/p/?LinkId=822530) article for info on how to find the header information.</span></span> 
 
## <a name="turn-onoff-clutter"></a><span data-ttu-id="e91b6-171">Aktivieren/Deaktivieren von "Clutter"</span><span class="sxs-lookup"><span data-stu-id="e91b6-171">Turn on/off Clutter</span></span>
 
<span data-ttu-id="e91b6-172">We've received reports that Clutter suddenly stopped working for some users.</span><span class="sxs-lookup"><span data-stu-id="e91b6-172">We've received reports that Clutter suddenly stopped working for some users.</span></span> <span data-ttu-id="e91b6-173">If this happens, you can enable it again for specific users.</span><span class="sxs-lookup"><span data-stu-id="e91b6-173">If this happens, you can enable it again for specific users.</span></span> <span data-ttu-id="e91b6-174">See [Configure Clutter for your organization](../email/configure-clutter.md).</span><span class="sxs-lookup"><span data-stu-id="e91b6-174">See [Configure Clutter for your organization](../email/configure-clutter.md).</span></span>
 
## <a name="faq-for-focused-inbox"></a><span data-ttu-id="e91b6-175">Häufig gestellte Fragen (FAQ) zum Posteingang mit Relevanz</span><span class="sxs-lookup"><span data-stu-id="e91b6-175">FAQ for Focused Inbox</span></span>

<span data-ttu-id="e91b6-176">Dies sind Antworten auf häufig gestellte Fragen zum Posteingang mit Relevanz.</span><span class="sxs-lookup"><span data-stu-id="e91b6-176">Here are answers to Frequently Asked Questions about Focused Inbox.</span></span> 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a><span data-ttu-id="e91b6-177">Kann ich steuern, wie "Posteingang mit Relevanz" in meiner Organisation implementiert wird?</span><span class="sxs-lookup"><span data-stu-id="e91b6-177">Can I control how I roll out Focused Inbox in my organization?</span></span>

<span data-ttu-id="e91b6-178">Yes.</span><span class="sxs-lookup"><span data-stu-id="e91b6-178">Yes.</span></span> <span data-ttu-id="e91b6-179">You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users.</span><span class="sxs-lookup"><span data-stu-id="e91b6-179">You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users.</span></span> <span data-ttu-id="e91b6-180">See above.</span><span class="sxs-lookup"><span data-stu-id="e91b6-180">See above.</span></span>
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a><span data-ttu-id="e91b6-181">Steht die Funktion "Posteingang mit Relevanz" NUR auf Office 2016-Clients zur Verfügung?</span><span class="sxs-lookup"><span data-stu-id="e91b6-181">Is the Focused Inbox feature ONLY available for Office 2016 clients?</span></span>

<span data-ttu-id="e91b6-182">Ja, sie betrifft nur Benutzer mit Office 2016.</span><span class="sxs-lookup"><span data-stu-id="e91b6-182">Yes, only users with Office 2016 are affected.</span></span> <span data-ttu-id="e91b6-183">Die Funktion wird nicht rückwirkend in Outlook 2013 und früheren Versionen implementiert.</span><span class="sxs-lookup"><span data-stu-id="e91b6-183">The feature is not going to be backported to Outlook 2013 or earlier.</span></span>
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a><span data-ttu-id="e91b6-184">Wie lange dauert es, bis Änderungen am Posteingang mit Relevanz in Outlook wirksam werden?</span><span class="sxs-lookup"><span data-stu-id="e91b6-184">How long does it take for Focused Inbox changes to take place in Outlook?</span></span>

<span data-ttu-id="e91b6-185">Nachdem Sie den Posteingang mit Relevanz aktiviert oder deaktiviert haben, werden die Einstellungen wirksam, sobald Ihre Benutzer Outlook schließen und erneut starten.</span><span class="sxs-lookup"><span data-stu-id="e91b6-185">Once you turn on or turn off Focused Inbox, the settings will take effect once your users close and restart Outlook.</span></span>
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a><span data-ttu-id="e91b6-186">Was geschieht mit "Clutter", nachdem ich den Posteingang mit Relevanz aktiviert habe?</span><span class="sxs-lookup"><span data-stu-id="e91b6-186">What happens to Clutter once I turn on Focused Inbox?</span></span>

<span data-ttu-id="e91b6-187">After switching, you'll no longer receive less actionable email in the Clutter folder.</span><span class="sxs-lookup"><span data-stu-id="e91b6-187">After switching, you'll no longer receive less actionable email in the Clutter folder.</span></span> <span data-ttu-id="e91b6-188">Instead, email will be split between the Focused and Other tabs in your inbox.</span><span class="sxs-lookup"><span data-stu-id="e91b6-188">Instead, email will be split between the Focused and Other tabs in your inbox.</span></span> <span data-ttu-id="e91b6-189">The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other.</span><span class="sxs-lookup"><span data-stu-id="e91b6-189">The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other.</span></span> <span data-ttu-id="e91b6-190">Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span><span class="sxs-lookup"><span data-stu-id="e91b6-190">Any messages already in your Clutter folder will remain there until you decide to delete or move them.</span></span>
  
<span data-ttu-id="e91b6-191">Lesen Sie dazu diesen Beitrag von [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365) (So ersetzt der Posteingang mit Relevanz den Ordner "Clutter" in Office 365).</span><span class="sxs-lookup"><span data-stu-id="e91b6-191">Check out this post by [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365).</span></span>
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a><span data-ttu-id="e91b6-192">Kann "Clutter" für Benutzer aktiviert bleiben?</span><span class="sxs-lookup"><span data-stu-id="e91b6-192">Can I keep users on Clutter?</span></span> <span data-ttu-id="e91b6-193">Was empfiehlt Microsoft hinsichtlich der Verwendung von Clutter gegenüber dem Posteingang mit Relevanz?</span><span class="sxs-lookup"><span data-stu-id="e91b6-193">What is Microsoft's recommendation when it comes to using Clutter vs Focused Inbox?</span></span>

<span data-ttu-id="e91b6-194">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now.</span><span class="sxs-lookup"><span data-stu-id="e91b6-194">Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now.</span></span> <span data-ttu-id="e91b6-195">To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span><span class="sxs-lookup"><span data-stu-id="e91b6-195">To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).</span></span>
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a><span data-ttu-id="e91b6-196">Sollte "Clutter" für Endbenutzer deaktiviert werden, wenn wir die Umstellung aller Benutzer auf den Posteingang mit Relevanz planen?</span><span class="sxs-lookup"><span data-stu-id="e91b6-196">Should I disable Clutter for my end users if we are going to move everyone to Focused Inbox?</span></span>

<span data-ttu-id="e91b6-197">No.</span><span class="sxs-lookup"><span data-stu-id="e91b6-197">No.</span></span> <span data-ttu-id="e91b6-198">It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet.</span><span class="sxs-lookup"><span data-stu-id="e91b6-198">It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet.</span></span> <span data-ttu-id="e91b6-199">However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox.</span><span class="sxs-lookup"><span data-stu-id="e91b6-199">However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox.</span></span> <span data-ttu-id="e91b6-200">It's therefore best not to disable Clutter until the upgraded clients are available.</span><span class="sxs-lookup"><span data-stu-id="e91b6-200">It's therefore best not to disable Clutter until the upgraded clients are available.</span></span>
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a><span data-ttu-id="e91b6-201">Warum gibt es zwei unterschiedliche Cmdlets für die Verwaltung von "Posteingang mit Relevanz"?</span><span class="sxs-lookup"><span data-stu-id="e91b6-201">Why are there two different cmdlets for managing Focused Inbox?</span></span>

<span data-ttu-id="e91b6-202">In Verbindung mit "Posteingang mit Relevanz" gibt es zwei Zustände.</span><span class="sxs-lookup"><span data-stu-id="e91b6-202">There are two states associated with Focused Inbox.</span></span>
  
- <span data-ttu-id="e91b6-203">**Organisationsebene**: Status "Posteingang mit Relevanz" und einen zugehörigen Zeitstempel mit der letzten Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="e91b6-203">**Organization Level**: Focused Inbox state, and an associated last update time-stamp.</span></span> 
    
- <span data-ttu-id="e91b6-204">**Postfachebene**: Status "Posteingang mit Relevanz" und einen zugehörigen Zeitstempel mit der letzten Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="e91b6-204">**Mailbox Level**: Focused Inbox state, and an associated last update time-stamp</span></span> 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a><span data-ttu-id="e91b6-205">Wie kann Outlook entscheiden, ob die Benutzeroberfläche "Posteingang mit Relevanz" mit diesen beiden Zuständen angezeigt werden soll?</span><span class="sxs-lookup"><span data-stu-id="e91b6-205">How does Outlook decide to show the Focused Inbox experience with these two states?</span></span>

<span data-ttu-id="e91b6-206">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp.</span><span class="sxs-lookup"><span data-stu-id="e91b6-206">Outlook decides to show the experience by choosing which cmdlet has the latest time stamp.</span></span> <span data-ttu-id="e91b6-207">By default, both time stamps are "null" and in this case, the feature is enabled.</span><span class="sxs-lookup"><span data-stu-id="e91b6-207">By default, both time stamps are "null" and in this case, the feature is enabled.</span></span>
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a><span data-ttu-id="e91b6-208">Warum gibt das Cmdlet Get-FocusedInbox "true" zurück, wenn ich "Posteingang mit Relevanz" in meiner Organisation deaktiviert habe?</span><span class="sxs-lookup"><span data-stu-id="e91b6-208">Why does the Get-FocusedInbox cmdlet return "true", when I've turned Focused Inbox off in my organization?</span></span>

<span data-ttu-id="e91b6-209">There are two cmdlets for controlling Focused Inbox.</span><span class="sxs-lookup"><span data-stu-id="e91b6-209">There are two cmdlets for controlling Focused Inbox.</span></span> <span data-ttu-id="e91b6-210">When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature.</span><span class="sxs-lookup"><span data-stu-id="e91b6-210">When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature.</span></span> <span data-ttu-id="e91b6-211">The experience in Outlook is chosen based on which cmdlet state was last modified.</span><span class="sxs-lookup"><span data-stu-id="e91b6-211">The experience in Outlook is chosen based on which cmdlet state was last modified.</span></span>
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a><span data-ttu-id="e91b6-212">Kann ich ein Skript ausführen, um zu sehen, wer den Posteingang mit Relevanz aktiviert hat?</span><span class="sxs-lookup"><span data-stu-id="e91b6-212">Can I run a script to see who has turned on Focused Inbox?</span></span>

<span data-ttu-id="e91b6-213">No, and this is by design.</span><span class="sxs-lookup"><span data-stu-id="e91b6-213">No, and this is by design.</span></span> <span data-ttu-id="e91b6-214">Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience.</span><span class="sxs-lookup"><span data-stu-id="e91b6-214">Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience.</span></span> <span data-ttu-id="e91b6-215">It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span><span class="sxs-lookup"><span data-stu-id="e91b6-215">It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.</span></span>
