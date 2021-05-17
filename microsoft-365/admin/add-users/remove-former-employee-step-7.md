---
title: 'Schritt 7 : Löschen des Benutzerkontos eines ehemaligen Mitarbeiters'
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
description: Führen Sie die folgenden Schritte aus, um das Benutzerkonto eines ehemaligen Mitarbeiters zu löschen.
ms.openlocfilehash: 0afa9b112919d2668d7553ac5bcf08e664bc1749
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244233"
---
# <a name="step-7---delete-a-former-employees-user-account"></a><span data-ttu-id="24222-103">Schritt 7 : Löschen des Benutzerkontos eines ehemaligen Mitarbeiters</span><span class="sxs-lookup"><span data-stu-id="24222-103">Step 7 - Delete a former employee's user account</span></span>

<span data-ttu-id="24222-104">Nachdem Sie auf alle Benutzerdaten des ehemaligen Mitarbeiters zugegriffen und diese gespeichert haben, können Sie das Konto des ehemaligen Mitarbeiters löschen.</span><span class="sxs-lookup"><span data-stu-id="24222-104">After you've saved and accessed all the former employee's user data, you can delete the former employee's account.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="24222-p101">Löschen Sie das Konto nicht, wenn Sie eine E-Mail-Weiterleitung eingerichtet oder das Konto in ein freigegebenes Postfach konvertiert haben. Für beide Funktionen wird das Konto benötigt, damit die Weiterleitung oder Postfachfreigabe funktioniert.</span><span class="sxs-lookup"><span data-stu-id="24222-p101">Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.</span></span>

1. <span data-ttu-id="24222-107">Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.</span><span class="sxs-lookup"><span data-stu-id="24222-107">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="24222-108">Wählen Sie den Namen des Mitarbeiters aus, den Sie löschen möchten.</span><span class="sxs-lookup"><span data-stu-id="24222-108">Select the name of the employee that you want to delete.</span></span>
3. <span data-ttu-id="24222-109">Wählen Sie unter dem Namen des Benutzers Benutzer **löschen aus.**</span><span class="sxs-lookup"><span data-stu-id="24222-109">Under the user's name, select **Delete user**.</span></span> <span data-ttu-id="24222-110">Wählen Sie die optionen aus, die Sie für diesen Benutzer wünschen, und wählen Sie dann **Benutzer löschen aus.**</span><span class="sxs-lookup"><span data-stu-id="24222-110">Choose the options you want for this user, and then select **Delete user**.</span></span> <span data-ttu-id="24222-111">Wenn Sie bereits einem anderen Benutzer Zugriff auf die E-Mails und OneDrive dieses Benutzers gegeben haben, müssen Sie dies hier nicht erneut tun.</span><span class="sxs-lookup"><span data-stu-id="24222-111">If you've already given another user access to this user's email and OneDrive, you don't have to do it again here.</span></span>

<span data-ttu-id="24222-p103">Wenn Sie einen Benutzer löschen, wird das Konto ungefähr 30 Tage lang deaktiviert (inaktiv). Sie haben in dieser Zeit noch die Möglichkeit, das Konto wiederherzustellen, bevor es endgültig gelöscht wird.</span><span class="sxs-lookup"><span data-stu-id="24222-p103">When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.</span></span>
  
## <a name="does-your-organization-use-active-directory"></a><span data-ttu-id="24222-114">Verwendet Ihre Organisation Active Directory?</span><span class="sxs-lookup"><span data-stu-id="24222-114">Does your organization use Active Directory?</span></span>

<span data-ttu-id="24222-115">Wenn Ihre Organisation Benutzerkonten mit Microsoft 365 einer lokalen Active Directory-Umgebung synchronisiert, müssen Sie diese Benutzerkonten in Ihrem lokalen Active Directory-Dienst löschen und wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="24222-115">If your organization synchronizes user accounts to Microsoft 365 from a local Active Directory environment, you must delete and restore those user accounts in your local Active Directory service.</span></span> <span data-ttu-id="24222-116">Sie können sie nicht in Office 365 löschen und wiederherstellen.</span><span class="sxs-lookup"><span data-stu-id="24222-116">You can't delete or restore them in Office 365.</span></span>

<span data-ttu-id="24222-117">Informationen zum Löschen und Wiederherstellen des Benutzerkontos in Active Directory finden Sie [unter Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span><span class="sxs-lookup"><span data-stu-id="24222-117">To learn how to delete and restore user account in Active Directory, see [Delete a User Account](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc753730(v=ws.11)).</span></span>
  
<span data-ttu-id="24222-118">Wenn Sie eine Azure Active Directory, lesen Sie [das Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="24222-118">If you're using Azure Active Directory, see the [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230) PowerShell cmdlet.</span></span>
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a><span data-ttu-id="24222-119">Wichtige Informationen zum Beenden der E-Mail-Sitzung eines Mitarbeiters</span><span class="sxs-lookup"><span data-stu-id="24222-119">What you need to know about terminating an employee's email session</span></span>

<span data-ttu-id="24222-120">Hier finden Sie Informationen dazu, wie Sie die E-Mail-Nutzung für einen Mitarbeiter beenden können (Exchange).</span><span class="sxs-lookup"><span data-stu-id="24222-120">Here's information about how to get an employee out of email (Exchange).</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="24222-121">**Mögliche Aktionen**</span><span class="sxs-lookup"><span data-stu-id="24222-121">**What you can do**</span></span> <br/> |<span data-ttu-id="24222-122">**Wie geht das?**</span><span class="sxs-lookup"><span data-stu-id="24222-122">**How you do it**</span></span> <br/> |
|<span data-ttu-id="24222-123">Sitzung beenden (z. B. Outlook im Web, Outlook, Exchange Active Sync usw.) und Öffnen einer neuen Sitzung erzwingen</span><span class="sxs-lookup"><span data-stu-id="24222-123">Terminate a session (such as Outlook on the web, Outlook, Exchange active sync, etc.) and force to open a new session</span></span>  <br/> |<span data-ttu-id="24222-124">Kennwort zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="24222-124">Reset password</span></span>  <br/> |
|<span data-ttu-id="24222-125">Sitzung beenden und Zugriff auf zukünftige Sitzungen (für alle Protokolle) sperren</span><span class="sxs-lookup"><span data-stu-id="24222-125">Terminate a session and block access to future sessions (for all protocols)</span></span>  <br/> |<span data-ttu-id="24222-126">Deaktivieren Sie das Konto.</span><span class="sxs-lookup"><span data-stu-id="24222-126">Disable the account.</span></span> <span data-ttu-id="24222-127">Beispiel: (im Exchange Admin Center oder mithilfe von PowerShell):</span><span class="sxs-lookup"><span data-stu-id="24222-127">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|<span data-ttu-id="24222-128">Sitzung für ein bestimmtes Protokoll (z. B. ActiveSync) beenden</span><span class="sxs-lookup"><span data-stu-id="24222-128">Terminate the session for a particular protocol (such as ActiveSync)</span></span>  <br/> |<span data-ttu-id="24222-129">Deaktivieren Sie das Protokoll.</span><span class="sxs-lookup"><span data-stu-id="24222-129">Disable the protocol.</span></span> <span data-ttu-id="24222-130">Beispiel: (im Exchange Admin Center oder mithilfe von PowerShell):</span><span class="sxs-lookup"><span data-stu-id="24222-130">For example, (in the Exchange admin center or using PowerShell):</span></span>  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |

<span data-ttu-id="24222-131">Die oben genannten Vorgänge können an drei Stellen durchgeführt werden:</span><span class="sxs-lookup"><span data-stu-id="24222-131">The above operations can be done in three places:</span></span>
  
|||
|:-----|:-----|
|<span data-ttu-id="24222-132">**Ort zum Beenden der Sitzung**</span><span class="sxs-lookup"><span data-stu-id="24222-132">**If you terminate the session here**</span></span> <br/> |<span data-ttu-id="24222-133">**Dauer der Maßnahme**</span><span class="sxs-lookup"><span data-stu-id="24222-133">**How long it takes**</span></span> <br/> |
|<span data-ttu-id="24222-134">Im Exchange Admin Center oder mithilfe von PowerShell</span><span class="sxs-lookup"><span data-stu-id="24222-134">In the Exchange admin center or using PowerShell</span></span>  <br/> |<span data-ttu-id="24222-135">Voraussichtliche Verzögerung = innerhalb von 30 Minuten</span><span class="sxs-lookup"><span data-stu-id="24222-135">Expected delay is within 30 min</span></span>  <br/> |
|<span data-ttu-id="24222-136">Azure Active Directory Admin Center</span><span class="sxs-lookup"><span data-stu-id="24222-136">In the Azure Active Directory admin center</span></span>  <br/> |<span data-ttu-id="24222-137">Voraussichtliche Verzögerung = 60 Minuten</span><span class="sxs-lookup"><span data-stu-id="24222-137">Expected delay is 60 min</span></span>  <br/> |
|<span data-ttu-id="24222-138">Lokale Umgebung</span><span class="sxs-lookup"><span data-stu-id="24222-138">In an on-premises environment</span></span>  <br/> |<span data-ttu-id="24222-139">Voraussichtliche Verzögerung = 3 Stunden oder mehr</span><span class="sxs-lookup"><span data-stu-id="24222-139">Expected delay is 3 hours or more</span></span>  <br/> |

### <a name="how-to-get-fastest-response-for-account-termination"></a><span data-ttu-id="24222-140">So erhalten Sie eine schnelle Reaktion auf die Kündigung eines Kontos</span><span class="sxs-lookup"><span data-stu-id="24222-140">How to get fastest response for account termination</span></span>

 <span data-ttu-id="24222-p107">**Schnellste Option**: Verwenden Sie das Exchange Admin Center (über PowerShell) oder das Azure Active Directory Admin Center. In einer lokalen Umgebung kann es mehrere Stunden dauern, bis die Änderung über das Azure Active Directory-Synchronisierungstool synchronisiert wurde.</span><span class="sxs-lookup"><span data-stu-id="24222-p107">**Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync.</span></span>
  
 <span data-ttu-id="24222-p108">**Schnellste Option für einen Benutzer mit lokaler Präsenz und im Exchange-Rechenzentrum**: Beenden Sie die Sitzung über das Azure Active Directory Admin Center bzw. das Exchange Admin Center, UND führen Sie die Änderung auch in der lokalen Umgebung auch. Andernfalls wird die Änderung im Azure Active Directory Admin Center bzw. Exchange Admin Center durch DirSync überschrieben.</span><span class="sxs-lookup"><span data-stu-id="24222-p108">**Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync.</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="24222-145">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="24222-145">Related articles</span></span>

[<span data-ttu-id="24222-146">Wiederherstellen eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="24222-146">Restore a user</span></span>](restore-user.md)
