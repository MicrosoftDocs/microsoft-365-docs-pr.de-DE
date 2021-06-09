---
title: 'Schritt 1: Beenden der Anmeldung eines Mitarbeiters bei Microsoft 365'
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Blockieren der Anmeldung eines ehemaligen Mitarbeiters und Blockieren des Zugriffs auf Microsoft 365 Dienste.
ms.openlocfilehash: cdba6dcaf239e94cf33f3bf88e7f217b4793bfd6
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52840850"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="cd89b-103">Schritt 1: Verhindern, dass sich ein ehemaliger Mitarbeiter anmeldet und den Zugriff auf Microsoft 365 Dienste blockiert</span><span class="sxs-lookup"><span data-stu-id="cd89b-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="cd89b-104">Wenn Sie den Anmeldezugriff eines Benutzers sofort verhindern müssen, sollten Sie sein Kennwort zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="cd89b-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="cd89b-105">Erzwingen Sie in diesem Schritt, dass sich der Benutzer von Microsoft 365 abmeldet.</span><span class="sxs-lookup"><span data-stu-id="cd89b-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="cd89b-106">Sie müssen ein globaler Administrator sein, um die Abmeldung für andere Administratoren zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="cd89b-106">You need to be a global administrator to initiate sign-out for other administrators.</span></span> <span data-ttu-id="cd89b-107">Für Benutzer, die keine Administratoren sind, können Sie einen Benutzeradministrator oder einen Helpdesk-Administratorbenutzer verwenden, um diese Aktion auszuführen.</span><span class="sxs-lookup"><span data-stu-id="cd89b-107">For non administrator users, you can use a User Administrator or a Helpdesk Administrator user to perform this action.</span></span> [<span data-ttu-id="cd89b-108">Weitere Informationen zu den Administratorrollen</span><span class="sxs-lookup"><span data-stu-id="cd89b-108">Learn more about the Admin Roles</span></span>](about-admin-roles.md)

1. <span data-ttu-id="cd89b-109">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="cd89b-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cd89b-110">Wählen Sie das Kontrollkästchen neben dem Benutzernamen aus, und wählen Sie dann **Kennwort zurücksetzen** aus.</span><span class="sxs-lookup"><span data-stu-id="cd89b-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="cd89b-111">Geben Sie ein neues Kennwort ein, und wählen Sie dann **Zurücksetzen** aus.</span><span class="sxs-lookup"><span data-stu-id="cd89b-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="cd89b-112">(Senden Sie es nicht an sie.)</span><span class="sxs-lookup"><span data-stu-id="cd89b-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="cd89b-113">Wählen Sie den Namen des Benutzers aus, um zum Eigenschaftenbereich zu wechseln, und wählen Sie auf der Registerkarte **"Konto"** die Option **"Abmelden initiieren" aus.**</span><span class="sxs-lookup"><span data-stu-id="cd89b-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

<span data-ttu-id="cd89b-114">Innerhalb einer Stunde – oder nachdem sie die aktuelle Microsoft 365 Seite verlassen haben, auf der sie sich befinden – werden sie aufgefordert, sich erneut anzumelden.</span><span class="sxs-lookup"><span data-stu-id="cd89b-114">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="cd89b-115">Ein Zugriffstoken ist eine Stunde lang gut, daher hängt die Zeitachse davon ab, wie viel Zeit für dieses Token verbleibt und ob er aus seiner aktuellen Webseite navigiert.</span><span class="sxs-lookup"><span data-stu-id="cd89b-115">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="cd89b-116">Wenn sich der Benutzer in Outlook im Web befindet und einfach nur in sein Postfach klickt, wird er möglicherweise nicht sofort herausgeklickt.</span><span class="sxs-lookup"><span data-stu-id="cd89b-116">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="cd89b-117">Sobald sie eine andere Kachel auswählen, z. B. OneDrive, oder ihren Browser aktualisieren, wird die Abmeldung initiiert.</span><span class="sxs-lookup"><span data-stu-id="cd89b-117">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="cd89b-118">Informationen zum sofortigen Abmelden eines Benutzers mitHilfe von PowerShell finden Sie im Cmdlet ["Revoke-AzureADUserAllRefreshToken".](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)</span><span class="sxs-lookup"><span data-stu-id="cd89b-118">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="cd89b-119">Weitere Informationen dazu, wie lange es dauert, für jemand die E-Mail-Nutzung zu beenden, finden Sie unter [Wichtige Informationen zum Beenden der E-Mail-Sitzung eines Mitarbeiters](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span><span class="sxs-lookup"><span data-stu-id="cd89b-119">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="cd89b-120">Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf Microsoft 365 Dienste</span><span class="sxs-lookup"><span data-stu-id="cd89b-120">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="cd89b-121">Das Blockieren eines Kontos kann bis zu 24 Stunden dauern, bis es wirksam wird.</span><span class="sxs-lookup"><span data-stu-id="cd89b-121">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="cd89b-122">Wenn Sie den Anmeldezugriff eines Benutzers sofort verhindern müssen, führen Sie die oben beschriebenen Schritte aus, und setzen Sie das Kennwort zurück.</span><span class="sxs-lookup"><span data-stu-id="cd89b-122">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="cd89b-123">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="cd89b-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="cd89b-124">Wählen Sie den Namen des Mitarbeiters aus, den Sie blockieren möchten, und wählen Sie unter dem Namen des Benutzers das Symbol für **"Diesen Benutzer blockieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="cd89b-124">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="cd89b-125">Wählen Sie **"Benutzeranmeldung blockieren" und** dann **"Speichern"** aus.</span><span class="sxs-lookup"><span data-stu-id="cd89b-125">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="cd89b-126">Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf E-Mail (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="cd89b-126">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="cd89b-127">Wenn Sie E-Mails als Teil Ihres Microsoft 365-Abonnements haben, melden Sie sich beim Exchange Admin Center an, und führen Sie die folgenden Schritte aus, um zu verhindern, dass Ihr ehemaliger Mitarbeiter auf seine E-Mails zugreift.</span><span class="sxs-lookup"><span data-stu-id="cd89b-127">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="cd89b-128">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="cd89b-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="cd89b-129">Navigieren Sie im Exchange Admin Center zu **Empfänger** \> **Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="cd89b-129">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="cd89b-130">Doppelklicken Sie auf den Benutzer, und wechseln Sie zur Seite **"Postfachfeatures".**</span><span class="sxs-lookup"><span data-stu-id="cd89b-130">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="cd89b-131">Wählen Sie unter **"Mobile Geräte"** die Option **"Exchange ActiveSync deaktivieren"** und **"OWA für Geräte deaktivieren" aus,** und antworten Sie bei Aufforderung **"Ja".**</span><span class="sxs-lookup"><span data-stu-id="cd89b-131">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="cd89b-132">Wählen Sie unter **"E-Mail-Konnektivität"** die Option **"Deaktivieren"** und **"Ja"** aus, wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="cd89b-132">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
