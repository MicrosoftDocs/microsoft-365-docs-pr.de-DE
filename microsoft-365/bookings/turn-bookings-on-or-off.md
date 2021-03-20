---
title: Microsoft Bookings an- oder ausschalten
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Erfahren Sie, wie Sie zugriff auf Microsoft Bookings in Microsoft 365 erhalten.
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913766"
---
# <a name="turn-microsoft-bookings-on-or-off"></a><span data-ttu-id="714c6-103">Microsoft Bookings an- oder ausschalten</span><span class="sxs-lookup"><span data-stu-id="714c6-103">Turn Microsoft Bookings on or off</span></span>

<span data-ttu-id="714c6-104">Buchungen können für Ihre gesamte Organisation oder für bestimmte Benutzer aktiviert oder deaktiviert werden.</span><span class="sxs-lookup"><span data-stu-id="714c6-104">Bookings can be turned on or off for your entire organization or for specific users.</span></span> <span data-ttu-id="714c6-105">Wenn Sie Bookings für Benutzer aktivieren, können sie eine Bookings-Seite erstellen, einen Kalender erstellen und anderen Personen erlauben, Zeit mit ihnen zu reservieren.</span><span class="sxs-lookup"><span data-stu-id="714c6-105">When you turn on Bookings for users, they can create a Bookings page, create a calendar, and allow other people to book time with them.</span></span>

> [!NOTE]
> <span data-ttu-id="714c6-106">Die in diesen Abschnitten beschriebenen Administratorsteuerelemente sind für Office 365 Operated by 21Vianet (China)-Kunden nicht verfügbar.</span><span class="sxs-lookup"><span data-stu-id="714c6-106">The admin controls described in these sections are not available for Office 365 Operated by 21Vianet (China) customers.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a><span data-ttu-id="714c6-107">Aktivieren oder Deaktivieren von Bookings für Ihre Organisation mithilfe des Microsoft 365 Admin Centers</span><span class="sxs-lookup"><span data-stu-id="714c6-107">Turn Bookings on or off for your organization using the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="714c6-108">Melden Sie sich beim Microsoft 365 Admin Center als globaler Administrator an.</span><span class="sxs-lookup"><span data-stu-id="714c6-108">Sign in to the Microsoft 365 admin center as a global admin.</span></span>

2. <span data-ttu-id="714c6-109">Wechseln Sie im Admin Center zu  **Einstellungen**   \> **Organisationseinstellungen,** und wählen Sie **Bookings aus.**</span><span class="sxs-lookup"><span data-stu-id="714c6-109">In the admin center, go to  **Settings** \> **Org Settings** and select **Bookings**.</span></span>

3. <span data-ttu-id="714c6-110">Aktivieren Sie das Kontrollkästchen **Zulassen, dass Ihre Organisation Bookings zum** Aktivieren oder Deaktivieren von Bookings für Ihre Organisation verwendet.</span><span class="sxs-lookup"><span data-stu-id="714c6-110">Select the checkbox for **Allow your organization to use Bookings** to enable or disable Bookings for your organization.</span></span>

   > [!NOTE]
   > <span data-ttu-id="714c6-111">Wenn Sie Bookings deaktivieren, wird der Zugriff auf den Dienst deaktiviert, einschließlich der Erstellung und Verwaltung von Bookings-Seiten.</span><span class="sxs-lookup"><span data-stu-id="714c6-111">Turning off Bookings will disable all access to the service including creation and management of Bookings pages.</span></span>

4. <span data-ttu-id="714c6-112">Wählen **Sie Änderungen speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="714c6-112">Select **Save Changes**.</span></span>

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a><span data-ttu-id="714c6-113">Aktivieren oder Deaktivieren von Bookings für Ihre Organisation mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="714c6-113">Turn Bookings on or off for your organization using PowerShell</span></span>

<span data-ttu-id="714c6-114">Um Bookings für Ihre Organisation mit dem PowerShell-Cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)zu aktivieren oder zu deaktivieren, stellen Sie eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) auf, und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="714c6-114">To turn Bookings on or off for your organization using the PowerShell cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig), [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) and run the following command:</span></span>

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a><span data-ttu-id="714c6-115">Aktivieren oder Deaktivieren von Bookings für einzelne Benutzer</span><span class="sxs-lookup"><span data-stu-id="714c6-115">Turn Bookings on or off for individual users</span></span>

<span data-ttu-id="714c6-116">Sie können Bookings für einzelne Benutzer deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="714c6-116">You can disable Bookings for individual users.</span></span>

1. <span data-ttu-id="714c6-117">Wechseln Sie zum Microsoft 365 Admin Center, und wählen Sie **dann Benutzer** Aktive \> **Benutzer aus.**</span><span class="sxs-lookup"><span data-stu-id="714c6-117">Go to the Microsoft 365 admin center, then select **Users** \> **Active users**.</span></span>

1. <span data-ttu-id="714c6-118">Wählen Sie den gewünschten Benutzer aus, und wählen Sie **dann Lizenzen und Apps aus.**</span><span class="sxs-lookup"><span data-stu-id="714c6-118">Select the desired user, then select **Licenses and Apps**.</span></span>

1. <span data-ttu-id="714c6-119">Erweitern **Sie Apps,** und aktivieren Sie das Kontrollkästchen für Microsoft Bookings.</span><span class="sxs-lookup"><span data-stu-id="714c6-119">Expand **Apps** and clear the checkbox for Microsoft Bookings.</span></span>

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a><span data-ttu-id="714c6-120">Vor der Freigabe von Frei/Gebucht-Informationen Mitarbeitergenehmigungen benötigen</span><span class="sxs-lookup"><span data-stu-id="714c6-120">Require staff approvals before sharing free/busy information</span></span>

<span data-ttu-id="714c6-121">Administratoren können mitarbeiter in ihrer Organisation die Anmeldung verlangen, bevor ihre Verfügbarkeitsinformationen über Bookings freigegeben werden und bevor sie über eine Buchungsseite gebucht werden können.</span><span class="sxs-lookup"><span data-stu-id="714c6-121">Admins can require employees in their organization to opt-in before their availability information is shared through Bookings and before they can be bookable through a booking page.</span></span> <span data-ttu-id="714c6-122">Diese Einstellung ist im Microsoft 365 Admin Center unter **Einstellungen** \> **Einstellungen** \> **Bookings verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="714c6-122">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="714c6-123">Wenn diese Einstellung aktiviert ist, finden Mitarbeiter, die als Mitarbeiter in Buchungskalendern hinzugefügt werden, einen Link genehmigen/ablehnen in der E-Mail-Benachrichtigung, die sie erhalten.</span><span class="sxs-lookup"><span data-stu-id="714c6-123">When this setting is enabled, employees added as staff in booking calendars will find an Approve/Reject link in the email notification they receive.</span></span>

<span data-ttu-id="714c6-124">Dieses Feature wird schrittweise weltweit für Microsoft 365-Kunden eingeführt.</span><span class="sxs-lookup"><span data-stu-id="714c6-124">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="714c6-125">Wenn diese Option im Microsoft 365 Admin Center nicht angezeigt wird, schauen Sie bald zurück.</span><span class="sxs-lookup"><span data-stu-id="714c6-125">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="block-social-sharing-options"></a><span data-ttu-id="714c6-126">Blockieren von Optionen für die freigabe für soziale Netzwerke</span><span class="sxs-lookup"><span data-stu-id="714c6-126">Block social sharing options</span></span>

<span data-ttu-id="714c6-127">Administratoren können steuern, wie Buchungsseiten in sozialen Netzwerken freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="714c6-127">Admins can control how booking pages are shared on social networks.</span></span> <span data-ttu-id="714c6-128">Diese Einstellung ist im Microsoft 365 Admin Center unter **Einstellungen** \> **Einstellungen** \> **Bookings verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="714c6-128">This setting is available in the Microsoft 365 admin center under **Settings** \> **Settings** \> **Bookings**.</span></span>

<span data-ttu-id="714c6-129">Dieses Feature wird schrittweise weltweit für Microsoft 365-Kunden eingeführt.</span><span class="sxs-lookup"><span data-stu-id="714c6-129">This feature is gradually rolling out world wide to Microsoft 365 customers.</span></span> <span data-ttu-id="714c6-130">Wenn diese Option im Microsoft 365 Admin Center nicht angezeigt wird, schauen Sie bald zurück.</span><span class="sxs-lookup"><span data-stu-id="714c6-130">If you don't see this option in the Microsoft 365 admin center, check back soon.</span></span>

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a><span data-ttu-id="714c6-131">Nur ausgewählte Benutzer zum Erstellen von Bookings-Kalendern zulassen</span><span class="sxs-lookup"><span data-stu-id="714c6-131">Allow only selected users to create Bookings calendars</span></span>

<span data-ttu-id="714c6-132">Mithilfe von Richtlinieneinschränkungen können Sie verhindern, dass lizenzierte Benutzer Bookings-Kalender erstellen können.</span><span class="sxs-lookup"><span data-stu-id="714c6-132">By using policy restrictions, you can restrict licensed users from being able to create Bookings calendars.</span></span> <span data-ttu-id="714c6-133">Sie müssen zuerst Bookings für Ihre gesamte Organisation aktivieren.</span><span class="sxs-lookup"><span data-stu-id="714c6-133">You must first enable Bookings for your entire organization.</span></span> <span data-ttu-id="714c6-134">Alle Benutzer in Ihrer Organisation verfügen über Bookings-Lizenzen, aber nur diejenigen, die in der Richtlinie enthalten sind, können Bookings-Kalender erstellen und voll darauf zugreifen, wer auf die von ihnen erstellten Kalender zugreifen kann.</span><span class="sxs-lookup"><span data-stu-id="714c6-134">All users in you organization will have Bookings licenses, but only those included in the policy can create Bookings calendars and have full control over who can access the calendars they create.</span></span>

<span data-ttu-id="714c6-135">Benutzer, die in dieser Richtlinie enthalten sind, können neue Bookings-Kalender erstellen und als Mitarbeiter in beliebiger Kapazität (einschließlich der Administratorrolle) vorhandenen Bookings-Kalendern hinzugefügt werden.</span><span class="sxs-lookup"><span data-stu-id="714c6-135">Users who are included in this policy can create new Bookings calendars and can be added as staff in any capacity (including the administrator role) to existing Bookings calendars.</span></span> <span data-ttu-id="714c6-136">Benutzer, die nicht in dieser Richtlinie enthalten sind, können keine neuen Bookings-Kalender erstellen und erhalten eine Fehlermeldung, wenn sie dies versuchen.</span><span class="sxs-lookup"><span data-stu-id="714c6-136">Users who aren't included in this policy won't be able to create new Bookings calendars and will receive an error message if they try to do so.</span></span>

<span data-ttu-id="714c6-137">Sie müssen die folgenden Befehle mit Exchange Online PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="714c6-137">You'll need to run the following commands using Exchange Online PowerShell.</span></span> <span data-ttu-id="714c6-138">Weitere Informationen zum Ausführen von Exchange Online-Cmdlets finden Sie unter [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="714c6-138">For more information on running Exchange Online cmdlets, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="714c6-139">In den folgenden Schritten wird davon ausgegangen, dass keine anderen Outlook Web App (OWA)-Postfachrichtlinien in Ihrer Organisation erstellt wurden.</span><span class="sxs-lookup"><span data-stu-id="714c6-139">The steps below assume that no other Outlook Web App (OWA) mailbox policies have been created in your organization.</span></span>

1. <span data-ttu-id="714c6-140">Erstellen Sie eine neue Postfachrichtlinie für Benutzer, die Bookings-Kalender erstellen dürfen sollten.</span><span class="sxs-lookup"><span data-stu-id="714c6-140">Create a new mailbox policy for users that should be allowed to create Bookings calendars.</span></span> <span data-ttu-id="714c6-141">(Die Erstellung von Bookings-Kalendern ist standardmäßig durch neue Postfachrichtlinien zulässig.)</span><span class="sxs-lookup"><span data-stu-id="714c6-141">(Bookings calendar creation is allowed by default by new mailbox policies.)</span></span>

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   <span data-ttu-id="714c6-142">Weitere Informationen finden Sie unter [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="714c6-142">For more information, see [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).</span></span>

2. <span data-ttu-id="714c6-143">Weisen Sie diese Richtlinie den relevanten Benutzern zu, indem Sie diesen Befehl für jeden Benutzer ausführen, den Sie zum Erstellen von Bookings-Kalendern berechtigt sein möchten.</span><span class="sxs-lookup"><span data-stu-id="714c6-143">Assign this policy to the relevant users by running this command for each user you want to grant permission to create Bookings calendars.</span></span>

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   <span data-ttu-id="714c6-144">Weitere Informationen finden Sie unter [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span><span class="sxs-lookup"><span data-stu-id="714c6-144">For more information, see [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).</span></span>

3. <span data-ttu-id="714c6-145">Optional: Führen Sie diesen Befehl aus, wenn Sie Bookings für alle anderen Benutzer in Ihrer Organisation deaktivieren möchten.</span><span class="sxs-lookup"><span data-stu-id="714c6-145">Optional: Run this command if you want to disable Bookings for all other users in your organization.</span></span>

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   <span data-ttu-id="714c6-146">Weitere Informationen finden Sie unter [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="714c6-146">For more information, see [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

<span data-ttu-id="714c6-147">Weitere Informationen zu OWA-Postfachrichtlinien finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="714c6-147">For more information on OWA mailbox policies, check out the following topics:</span></span>

- [<span data-ttu-id="714c6-148">Erstellen einer Outlook im Webpostfachrichtlinie in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="714c6-148">Create an Outlook on the web mailbox policy in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [<span data-ttu-id="714c6-149">Anwenden oder Entfernen einer Outlook im Webpostfachrichtlinie für ein Postfach in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="714c6-149">Apply or remove an Outlook on the web mailbox policy on a mailbox in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)