---
title: Schritt 1 – Beenden der Anmeldung eines Mitarbeiters bei Microsoft 365
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
description: Blockieren der Anmeldung eines ehemaligen Mitarbeiters und Sperren des Zugriffs auf Microsoft 365 Dienste.
ms.openlocfilehash: 84852e9bccb1d4370db07492baf7ccaed7f6db3d
ms.sourcegitcommit: 4bcac4cb4f9399ebbd7c8cff0abb4d6ecedb731e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/28/2021
ms.locfileid: "52698904"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="f5b9d-103">Schritt 1 – Verhindern, dass sich ein ehemaliger Mitarbeiter an einem Dienst anmelden und den Zugriff auf Microsoft 365 blockieren</span><span class="sxs-lookup"><span data-stu-id="f5b9d-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="f5b9d-104">Wenn Sie den Anmeldezugriff eines Benutzers sofort verhindern müssen, sollten Sie sein Kennwort zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="f5b9d-105">Erzwingen Sie in diesem Schritt das Abmelden des Benutzers aus Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="f5b9d-106">Sie müssen ein globaler Administrator sein, um das Abmelden für andere Administratoren zu initiieren.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-106">You need to be a global administrator to initiate sign-out for other administrators.</span></span> <span data-ttu-id="f5b9d-107">Für Benutzer ohne Administratorrechte können Sie einen Benutzeradministrator oder einen Helpdeskadministrator verwenden, um diese Aktion durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-107">For non administrator users, you can use a User Administrator or a Helpdesk Administrator user to perform this action.</span></span>
> <span data-ttu-id="f5b9d-108">Weitere Informationen zu Administratorrollen <a href="https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles">zu Administratorrollen</a></span><span class="sxs-lookup"><span data-stu-id="f5b9d-108">Learn more about the Admin Roles <a href="https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles">About Admin Roles</a></span></span>

1. <span data-ttu-id="f5b9d-109">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f5b9d-110">Wählen Sie das Feld neben dem Namen des Benutzers aus, und wählen Sie dann **Kennwort zurücksetzen aus.**</span><span class="sxs-lookup"><span data-stu-id="f5b9d-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="f5b9d-111">Geben Sie ein neues Kennwort ein, und wählen Sie dann **Zurücksetzen aus.**</span><span class="sxs-lookup"><span data-stu-id="f5b9d-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="f5b9d-112">(Senden Sie es nicht an sie.)</span><span class="sxs-lookup"><span data-stu-id="f5b9d-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="f5b9d-113">Wählen Sie den Namen des Benutzers aus, um  zum Eigenschaftenbereich zu wechseln, und wählen Sie auf der Registerkarte Konto die Option **Abmelden initiieren aus.**</span><span class="sxs-lookup"><span data-stu-id="f5b9d-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

<span data-ttu-id="f5b9d-114">Innerhalb einer Stunde – oder nachdem sie die aktuelle Seite Microsoft 365 verlassen, auf der sie sich befinden – werden sie aufgefordert, sich erneut zu melden.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-114">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="f5b9d-115">Ein Zugriffstoken ist für eine Stunde gut, daher hängt die Zeitachse davon ab, wie viel Zeit auf diesem Token noch bleibt und ob sie aus ihrer aktuellen Webseite navigieren.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-115">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="f5b9d-116">Wenn sich der Benutzer im Outlook im Web befindet, indem er einfach in ihrem Postfach herumklickt, wird er möglicherweise nicht sofort raus.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-116">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="f5b9d-117">Sobald sie eine andere Kachel auswählen, z. B. OneDrive oder den Browser aktualisieren, wird die Abmeldeung initiiert.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-117">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="f5b9d-118">Informationen zum sofortigen Abmelden eines Benutzers mithilfe von PowerShell finden Sie im [Cmdlet Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)</span><span class="sxs-lookup"><span data-stu-id="f5b9d-118">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="f5b9d-119">Weitere Informationen dazu, wie lange es dauert, für jemand die E-Mail-Nutzung zu beenden, finden Sie unter [Wichtige Informationen zum Beenden der E-Mail-Sitzung eines Mitarbeiters](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span><span class="sxs-lookup"><span data-stu-id="f5b9d-119">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="f5b9d-120">Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf Microsoft 365 Dienste</span><span class="sxs-lookup"><span data-stu-id="f5b9d-120">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="f5b9d-121">Das Blockieren eines Kontos kann bis zu 24 Stunden in Kraft treten.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-121">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="f5b9d-122">Wenn Sie den Anmeldezugriff eines Benutzers sofort verhindern müssen, führen Sie die obigen Schritte aus, und setzen Sie ihr Kennwort zurück.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-122">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="f5b9d-123">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-123">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="f5b9d-124">Wählen Sie den Namen des Mitarbeiters aus, den Sie blockieren möchten, und wählen Sie unter dem Namen des Benutzers das Symbol für **Diesen Benutzer blockieren aus.**</span><span class="sxs-lookup"><span data-stu-id="f5b9d-124">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="f5b9d-125">Wählen **Sie Anmelden des Benutzers blockieren** aus, und wählen Sie dann Speichern **aus.**</span><span class="sxs-lookup"><span data-stu-id="f5b9d-125">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="f5b9d-126">Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf E-Mail (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="f5b9d-126">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="f5b9d-127">Wenn Sie E-Mails im Rahmen Ihres Microsoft 365-Abonnements haben, melden Sie sich beim Exchange Admin Center an, und führen Sie die folgenden Schritte aus, um ihren ehemaligen Mitarbeiter am Zugriff auf seine E-Mails zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-127">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="f5b9d-128">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-128">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="f5b9d-129">Navigieren Sie im Exchange Admin Center zu **Empfänger** \> **Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-129">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="f5b9d-130">Doppelklicken Sie auf den Benutzer, und wechseln Sie zur **Seite Postfachfeatures.**</span><span class="sxs-lookup"><span data-stu-id="f5b9d-130">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="f5b9d-131">Wählen **Sie unter Mobile** Geräte die Option **Exchange ActiveSync** deaktivieren und OWA für Geräte deaktivieren **aus,** und **antworten** Sie bei Aufforderung mit Ja auf beide.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-131">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="f5b9d-132">Wählen **Sie unter E-Mail-Konnektivität** **die Option Deaktivieren** aus, und antworten Sie **auf Ja,** wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="f5b9d-132">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
