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
description: Blockieren der Anmeldung eines ehemaligen Mitarbeiters und Sperren des Zugriffs auf Microsoft 365-Dienste.
ms.openlocfilehash: 60f4cf6b5c9a0b5dc2023b3ef7b6460685142d07
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244252"
---
# <a name="step-1---prevent-a-former-employee-from-logging-in-and-block-access-to-microsoft-365-services"></a><span data-ttu-id="4655b-103">Schritt 1 – Verhindern, dass sich ein ehemaliger Mitarbeiter an der Anmeldung einloggt und den Zugriff auf Microsoft 365-Dienste blockiert</span><span class="sxs-lookup"><span data-stu-id="4655b-103">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>

<span data-ttu-id="4655b-104">Wenn Sie den Anmeldezugriff eines Benutzers sofort verhindern müssen, sollten Sie sein Kennwort zurücksetzen.</span><span class="sxs-lookup"><span data-stu-id="4655b-104">If you need to immediately prevent a user's sign-in access, you should reset their password.</span></span> <span data-ttu-id="4655b-105">Erzwingen Sie in diesem Schritt das Abmelden des Benutzers von Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4655b-105">In this step, force a sign out of the user from Microsoft 365.</span></span>

1. <span data-ttu-id="4655b-106">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="4655b-106">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4655b-107">Wählen Sie das Feld neben dem Namen des Benutzers aus, und wählen Sie dann **Kennwort zurücksetzen aus.**</span><span class="sxs-lookup"><span data-stu-id="4655b-107">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="4655b-108">Geben Sie ein neues Kennwort ein, und wählen Sie dann **Zurücksetzen aus.**</span><span class="sxs-lookup"><span data-stu-id="4655b-108">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="4655b-109">(Senden Sie es nicht an sie.)</span><span class="sxs-lookup"><span data-stu-id="4655b-109">(Don't send it to them.)</span></span>
4. <span data-ttu-id="4655b-110">Wählen Sie den Namen des Benutzers aus, um  zum Eigenschaftenbereich zu wechseln, und wählen Sie auf der Registerkarte Konto die Option **Abmelden initiieren aus.**</span><span class="sxs-lookup"><span data-stu-id="4655b-110">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

<span data-ttu-id="4655b-111">Innerhalb einer Stunde – oder nachdem sie die aktuelle Microsoft 365-Seite verlassen haben, auf der sie sich befinden – werden sie aufgefordert, sich erneut zu registrieren.</span><span class="sxs-lookup"><span data-stu-id="4655b-111">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="4655b-112">Ein Zugriffstoken ist für eine Stunde gut, daher hängt die Zeitachse davon ab, wie viel Zeit auf diesem Token noch bleibt und ob sie aus ihrer aktuellen Webseite navigieren.</span><span class="sxs-lookup"><span data-stu-id="4655b-112">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4655b-113">Wenn sich der Benutzer in Outlook im Web befindet und einfach in ihrem Postfach herumklickt, wird er möglicherweise nicht sofort angezeigt.</span><span class="sxs-lookup"><span data-stu-id="4655b-113">If the user is in Outlook on the web, just clicking around in their mailbox, they may not be kicked out immediately.</span></span> <span data-ttu-id="4655b-114">Sobald sie eine andere Kachel auswählen, z. B. OneDrive, oder ihren Browser aktualisieren, wird die Abmeldeung initiiert.</span><span class="sxs-lookup"><span data-stu-id="4655b-114">As soon as they select a different tile, such as OneDrive, or refresh their browser, the sign-out is initiated.</span></span>
  
<span data-ttu-id="4655b-115">Informationen zum sofortigen Abmelden eines Benutzers mithilfe von PowerShell finden Sie im [Cmdlet Revoke-AzureADUserAllRefreshToken.](/powershell/module/azuread/revoke-azureaduserallrefreshtoken)</span><span class="sxs-lookup"><span data-stu-id="4655b-115">To use PowerShell to sign out a user immediately, see the [Revoke-AzureADUserAllRefreshToken](/powershell/module/azuread/revoke-azureaduserallrefreshtoken) cmdlet.</span></span>
  
<span data-ttu-id="4655b-116">Weitere Informationen dazu, wie lange es dauert, für jemand die E-Mail-Nutzung zu beenden, finden Sie unter [Wichtige Informationen zum Beenden der E-Mail-Sitzung eines Mitarbeiters](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span><span class="sxs-lookup"><span data-stu-id="4655b-116">For more information about how long it takes to get someone out of email, see [What you need to know about terminating an employee's email session](remove-former-employee-step-7.md#what-you-need-to-know-about-terminating-an-employees-email-session).</span></span>

## <a name="block-a-former-employees-access-to-microsoft-365-services"></a><span data-ttu-id="4655b-117">Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf Microsoft 365-Dienste</span><span class="sxs-lookup"><span data-stu-id="4655b-117">Block a former employee's access to Microsoft 365 services</span></span>

> [!IMPORTANT]
 > <span data-ttu-id="4655b-118">Das Blockieren eines Kontos kann bis zu 24 Stunden in Kraft treten.</span><span class="sxs-lookup"><span data-stu-id="4655b-118">Blocking an account can take up to 24 hours to take effect.</span></span> <span data-ttu-id="4655b-119">Wenn Sie den Anmeldezugriff eines Benutzers sofort verhindern müssen, führen Sie die obigen Schritte aus, und setzen Sie ihr Kennwort zurück.</span><span class="sxs-lookup"><span data-stu-id="4655b-119">If you need to immediately prevent a user's sign-in access, follow the steps above and reset their password.</span></span>

1. <span data-ttu-id="4655b-120">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="4655b-120">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="4655b-121">Wählen Sie den Namen des Mitarbeiters aus, den Sie blockieren möchten, und wählen Sie unter dem Namen des Benutzers das Symbol für **Diesen Benutzer blockieren aus.**</span><span class="sxs-lookup"><span data-stu-id="4655b-121">Select the name of the employee that you want to block, and under the user's name, select the symbol for **Block this user**.</span></span>
3. <span data-ttu-id="4655b-122">Wählen **Sie Anmelden des Benutzers blockieren** aus, und wählen Sie dann Speichern **aus.**</span><span class="sxs-lookup"><span data-stu-id="4655b-122">Select **Block the user from signing in**, and then select **Save**.</span></span>

## <a name="block-a-former-employees-access-to-email-exchange-online"></a><span data-ttu-id="4655b-123">Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf E-Mail (Exchange Online)</span><span class="sxs-lookup"><span data-stu-id="4655b-123">Block a former employee's access to email (Exchange Online)</span></span>

<span data-ttu-id="4655b-124">Wenn Sie über E-Mails im Rahmen Ihres Microsoft 365-Abonnements verfügen, melden Sie sich beim Exchange Admin Center an, und führen Sie die folgenden Schritte aus, um ihren ehemaligen Mitarbeiter am Zugriff auf seine E-Mails zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="4655b-124">If you have email as part of your Microsoft 365 subscription, sign in to the Exchange admin center and follow these steps to block your former employee from accessing their email.</span></span>
  
1. <span data-ttu-id="4655b-125">Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.</span><span class="sxs-lookup"><span data-stu-id="4655b-125">Go to the <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange admin center</a>.</span></span>
2. <span data-ttu-id="4655b-126">Navigieren Sie im Exchange Admin Center zu **Empfänger** \> **Postfächer**.</span><span class="sxs-lookup"><span data-stu-id="4655b-126">In the Exchange admin center, navigate to **Recipients** \> **Mailboxes**.</span></span>
3. <span data-ttu-id="4655b-127">Doppelklicken Sie auf den Benutzer, und wechseln Sie zur **Seite Postfachfeatures.**</span><span class="sxs-lookup"><span data-stu-id="4655b-127">Double-click the user and go to the **Mailbox features** page.</span></span> <span data-ttu-id="4655b-128">Wählen **Sie unter Mobile** Geräte die Option **Exchange ActiveSync** deaktivieren und OWA für Geräte deaktivieren **aus,** und **antworten** Sie bei Aufforderung mit Ja auf beide.</span><span class="sxs-lookup"><span data-stu-id="4655b-128">Under **Mobile Devices**, select **Disable Exchange ActiveSync** and **Disable OWA for Devices,** and answer **Yes** to both when prompted.</span></span>
4. <span data-ttu-id="4655b-129">Wählen **Sie unter E-Mail-Konnektivität** **die Option Deaktivieren** aus, und antworten Sie **auf Ja,** wenn Sie dazu aufgefordert werden.</span><span class="sxs-lookup"><span data-stu-id="4655b-129">Under **Email Connectivity**, select **Disable** and answer **Yes** when prompted.</span></span>
