---
title: Aktivieren oder Deaktivieren von Microsoft-Buchungen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Erfahren Sie, wie Sie Zugriff auf Microsoft-Buchungen in Microsoft 365 erhalten.
ms.openlocfilehash: 7e4eaa1e474f3f49807b842097c855193f028af0
ms.sourcegitcommit: 0402d3275632fceda9137b6abc3ce48c8020172a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/17/2020
ms.locfileid: "49126591"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="88d9e-103">Aktivieren oder Deaktivieren von Microsoft-Buchungen</span><span class="sxs-lookup"><span data-stu-id="88d9e-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="88d9e-104">Buchungen können für die gesamte Organisation oder für bestimmte Benutzer aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="88d9e-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="88d9e-105">Wenn Sie Buchungen für Benutzer aktivieren, können Sie eine Buchungsseite erstellen, einen Kalender erstellen und anderen Personen die Möglichkeit geben, Zeit mit Ihnen zu buchen.</span><span class="sxs-lookup"><span data-stu-id="88d9e-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="88d9e-106">Die in diesen Abschnitten beschriebenen Administrator Steuerelemente sind für Office 365, die von 21Vianet-Kunden (China) betrieben werden, nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="88d9e-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="88d9e-107">Aktivieren oder Deaktivieren von Buchungen für Ihre Organisation mithilfe des Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="88d9e-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="88d9e-108">Melden Sie sich beim Microsoft 365 Admin Center als globaler Administrator an.</span><span class="sxs-lookup"><span data-stu-id="88d9e-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="88d9e-109">Wechseln Sie im Admin Center zu  **Einstellungen**   \> **org-Einstellungen** , und wählen Sie **Buchungen** aus.</span><span class="sxs-lookup"><span data-stu-id="88d9e-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="88d9e-110">Aktivieren oder deaktivieren Sie das Kontrollkästchen **Ihre Organisation kann Buchungen verwenden** , um Buchungen für Ihre Organisation zu aktivieren oder zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="88d9e-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="88d9e-111">Durch das Deaktivieren von Buchungen wird der gesamte Zugriff auf den Dienst deaktiviert, einschließlich der Erstellung und Verwaltung von Buchungsseiten.</span><span class="sxs-lookup"><span data-stu-id="88d9e-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="88d9e-112">Wählen Sie **Save Changes** aus.</span><span class="sxs-lookup"><span data-stu-id="88d9e-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="88d9e-113">Aktivieren oder Deaktivieren von Reservierungen für Ihre Organisation mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="88d9e-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="88d9e-114">Zum Aktivieren oder Deaktivieren von Buchungen für Ihre Organisation mit dem PowerShell-Cmdlet " [OrganizationConfig" stellen](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) , und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="88d9e-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="88d9e-115">Aktivieren oder Deaktivieren von Buchungen für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="88d9e-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="88d9e-116">Sie können Buchungen für einzelne Benutzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="88d9e-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="88d9e-117">Wechseln Sie zum Microsoft 365 Admin Center, und wählen Sie dann **Benutzer** \> **aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="88d9e-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="88d9e-118">Wählen Sie den gewünschten Benutzer aus, und wählen Sie dann **Lizenzen und apps** aus.</span><span class="sxs-lookup"><span data-stu-id="88d9e-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="88d9e-119">Erweitern Sie **apps** , und deaktivieren Sie das Kontrollkästchen für Microsoft-Buchungen.</span><span class="sxs-lookup"><span data-stu-id="88d9e-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="88d9e-120">Personal Genehmigungen erfordern, bevor Sie Frei/Gebucht-Informationen freigeben</span><span class="sxs-lookup"><span data-stu-id="88d9e-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="88d9e-121">Administratoren können von Mitarbeitern in Ihrer Organisation verlangen, dass Sie sich anmelden, bevor Ihre Verfügbarkeitsinformationen Überbuchungen freigegeben werden und bevor Sie über eine Buchungsseite gebucht werden können.</span><span class="sxs-lookup"><span data-stu-id="88d9e-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="88d9e-122">Diese Einstellung steht im Microsoft 365 Admin Center unter Einstellungen für **Settings** \> **Settings** \> **Reservierungen** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="88d9e-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="88d9e-123">Wenn diese Einstellung aktiviert ist, werden Mitarbeiter, die in Buchungs Kalendern als Mitarbeiter hinzugefügt wurden, in der von Ihnen empfangenen e-Mail-Benachrichtigung einen Link genehmigen/ablehnen finden.</span><span class="sxs-lookup"><span data-stu-id="88d9e-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="88d9e-124">Dieses Feature wird schrittweise weltweit auf Microsoft 365-Kunden verteilt.</span><span class="sxs-lookup"><span data-stu-id="88d9e-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="88d9e-125">Wenn diese Option im Microsoft 365 Admin Center nicht angezeigt wird, schauen Sie bald zurück.</span><span class="sxs-lookup"><span data-stu-id="88d9e-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="88d9e-126">Blockieren von Optionen für die soziale Freigabe</span><span class="sxs-lookup"><span data-stu-id="88d9e-126">Block social sharing options</span></span>

<span data-ttu-id="88d9e-127">Administratoren können steuern, wie Buchungsseiten in sozialen Netzwerken freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="88d9e-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="88d9e-128">Diese Einstellung steht im Microsoft 365 Admin Center unter Einstellungen für **Settings** \> **Settings** \> **Reservierungen** zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="88d9e-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="88d9e-129">Dieses Feature wird schrittweise weltweit auf Microsoft 365-Kunden verteilt.</span><span class="sxs-lookup"><span data-stu-id="88d9e-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="88d9e-130">Wenn diese Option im Microsoft 365 Admin Center nicht angezeigt wird, schauen Sie bald zurück.</span><span class="sxs-lookup"><span data-stu-id="88d9e-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="88d9e-131">Nur ausgewählten Benutzern das Erstellen von Buchungs Kalendern erlauben</span><span class="sxs-lookup"><span data-stu-id="88d9e-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="88d9e-132">Durch die Verwendung von Richtlinieneinschränkungen können Sie die Lizenzierung von lizenzierten Benutzern daran hindern, Buchungen von Kalendern erstellen zu können.</span><span class="sxs-lookup"><span data-stu-id="88d9e-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="88d9e-133">Sie müssen zunächst Buchungen für Ihre gesamte Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="88d9e-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="88d9e-134">Alle Benutzer in Ihrer Organisation verfügen über Buchungs Lizenzen, aber nur die in der Richtlinie enthaltenen Buchungen können Buchungskalender erstellen und Vollzugriff auf die von Ihnen erstellten Kalender erhalten.</span><span class="sxs-lookup"><span data-stu-id="88d9e-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="88d9e-135">Benutzer, die in dieser Richtlinie enthalten sind, können neue Buchungskalender erstellen und können als Mitarbeiter in beliebiger Kapazität (einschließlich der Administratorrolle) vorhandenen Buchungs Kalendern hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="88d9e-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="88d9e-136">Benutzer, die nicht in dieser Richtlinie enthalten sind, können keine neuen Buchungen Kalender erstellen und erhalten eine Fehlermeldung, wenn Sie versuchen, dies zu tun.</span><span class="sxs-lookup"><span data-stu-id="88d9e-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="88d9e-137">Sie müssen die folgenden Befehle mit Exchange Online PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="88d9e-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="88d9e-138">Weitere Informationen zum Ausführen von Exchange Online-Cmdlets finden Sie unter [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="88d9e-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88d9e-139">In den folgenden Schritten wird davon ausgegangen, dass in Ihrer Organisation keine anderen Outlook Web App (OWA)-Postfachrichtlinien erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="88d9e-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="88d9e-140">Erstellen Sie eine neue Postfachrichtlinie für Benutzer, die Kalender mit Buchungen erstellen dürfen.</span><span class="sxs-lookup"><span data-stu-id="88d9e-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="88d9e-141">(Buchungen Kalendererstellung ist standardmäßig durch neue Postfachrichtlinien zulässig.)</span><span class="sxs-lookup"><span data-stu-id="88d9e-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="88d9e-142">Weitere Informationen finden Sie unter [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="88d9e-142">For more information, see [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="88d9e-143">Weisen Sie diese Richtlinie den relevanten Benutzern zu, indem Sie diesen Befehl für jeden Benutzer ausführen, dem Sie die Berechtigung zum Erstellen von Buchungs Kalendern erteilen möchten.</span><span class="sxs-lookup"><span data-stu-id="88d9e-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="88d9e-144">Weitere Informationen finden Sie unter [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="88d9e-144">For more information, see [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="88d9e-145">Optional: führen Sie diesen Befehl aus, wenn Sie Buchungen für alle anderen Benutzer in Ihrer Organisation deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="88d9e-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="88d9e-146">Weitere Informationen finden Sie unter [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="88d9e-146">For more information, see [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="88d9e-147">Weitere Informationen zu OWA-Postfachrichtlinien finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="88d9e-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="88d9e-148">Erstellen einer Outlook im Internet-Postfachrichtlinie in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="88d9e-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="88d9e-149">Anwenden oder Entfernen einer Outlook im webpostfach-Richtlinie für ein Postfach in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="88d9e-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)
