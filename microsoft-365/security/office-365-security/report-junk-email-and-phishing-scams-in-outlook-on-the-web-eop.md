---
title: Melden von Junk- und Phishing-E-Mails in Outlook im Web
f1.keywords:
- NOCSH
ms.author: siosulli
author: siosulli
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 758822b5-0126-463a-9d08-7366bb2a807d
ms.collection:
- M365-security-compliance
description: Administratoren können sich über die integrierten Junk-, nicht Junk- und Phishing-E-Mail-Berichterstellungsoptionen in Outlook im Web (Outlook Web App) in Exchange Online informieren und erfahren, wie Sie diese Berichterstellungsoptionen für Benutzer deaktivieren.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 933387dd32a6c1ca1e27ee11e4a9384615e8fdec
ms.sourcegitcommit: 0ff6edbf52562138a69c6675cb0274ec984986c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/07/2021
ms.locfileid: "51615211"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="e0feb-103">Melden von Junk- und Phishing-E-Mails in Outlook im Web in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e0feb-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="e0feb-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="e0feb-104">**Applies to**</span></span>
- [<span data-ttu-id="e0feb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="e0feb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="e0feb-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="e0feb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e0feb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e0feb-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e0feb-108">In Microsoft 365-Organisationen mit Postfächern in Exchange [](../../enterprise/hybrid-modern-auth-overview.md)Online oder lokalen Postfächern mit moderner Hybridauthentifizierung können Sie falsch positive Nachrichten (gute E-Mails als Spam gekennzeichnet), falsch negative Nachrichten (ungültige E-Mails zulässig) und Phishingnachrichten an Exchange Online Protection (EOP) senden.</span><span class="sxs-lookup"><span data-stu-id="e0feb-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e0feb-109">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="e0feb-109">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e0feb-110">Für eine optimale Benutzerübermittlung empfehlen wir die Verwendung der Berichtsnachricht und der Phishing-Add-Ins melden. Weitere [Informationen finden Sie unter Enable the Report Message add-in](./enable-the-report-message-add-in.md) und Enable the Report Phishing [add-in.](./enable-the-report-phish-add-in.md)</span><span class="sxs-lookup"><span data-stu-id="e0feb-110">For the best user submission experience we recommend using the Report Message and the Report Phishing add-ins. See [Enable the Report Message add-in](./enable-the-report-message-add-in.md) and [Enable the Report Phishing add-in](./enable-the-report-phish-add-in.md) for more information.</span></span>

- <span data-ttu-id="e0feb-111">Wenn Sie ein Administrator in einer Organisation mit Exchange Online-Postfächern sind, wird empfohlen, das Übermittlungsportal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="e0feb-111">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="e0feb-112">Weitere Informationen finden Sie unter [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e0feb-112">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="e0feb-113">Administratoren können die Möglichkeit für Benutzer deaktivieren oder aktivieren, Nachrichten an Microsoft in Outlook im Web zu melden.</span><span class="sxs-lookup"><span data-stu-id="e0feb-113">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="e0feb-114">Weitere Informationen finden Sie im Abschnitt Deaktivieren oder [Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) weiter in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="e0feb-114">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="e0feb-115">Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen festgelegtes Postfach kopiert oder umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="e0feb-115">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="e0feb-116">Weitere Informationen finden Sie unter [Benutzerübermittlungsrichtlinien](user-submission.md).</span><span class="sxs-lookup"><span data-stu-id="e0feb-116">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="e0feb-117">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft](report-junk-email-messages-to-microsoft.md).</span><span class="sxs-lookup"><span data-stu-id="e0feb-117">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="e0feb-118">Deaktivieren oder Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="e0feb-118">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="e0feb-119">Standardmäßig können Benutzer Spam falsch positive, falsch negative und Phishingnachrichten zur Analyse in Outlook im Web an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="e0feb-119">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="e0feb-120">Administratoren können Outlook im Web-Postfachrichtlinien in Exchange Online PowerShell konfigurieren, um zu verhindern, dass Benutzer Spam falsch positive und Spam-falsch negative Nachrichten an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="e0feb-120">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="e0feb-121">Sie können die Möglichkeit für Benutzer, Phishingnachrichten an Microsoft zu melden, nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e0feb-121">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e0feb-122">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="e0feb-122">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e0feb-123">Wie Sie eine Verbindung mit Exchange Online-PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e0feb-123">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="e0feb-124">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in Exchange Online die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e0feb-124">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="e0feb-125">Insbesondere benötigen Sie die Rollen **Empfängerrichtlinien** oder **E-Mail-Empfänger,** die standardmäßig den Rollengruppen Organisationsverwaltung und Empfängerverwaltung zugewiesen sind.  </span><span class="sxs-lookup"><span data-stu-id="e0feb-125">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="e0feb-126">Weitere Informationen zu Rollengruppen in Exchange Online finden Sie unter [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) und Modify role groups in Exchange [Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span><span class="sxs-lookup"><span data-stu-id="e0feb-126">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="e0feb-127">Jede Organisation verfügt über eine Standardrichtlinie mit dem Namen OwaMailboxPolicy-Default, Sie können jedoch benutzerdefinierte Richtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="e0feb-127">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="e0feb-128">Benutzerdefinierte Richtlinien werden auf Bereichsbenutzer vor der Standardrichtlinie angewendet.</span><span class="sxs-lookup"><span data-stu-id="e0feb-128">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="e0feb-129">Weitere Informationen zu Outlook im Webpostfachrichtlinien finden Sie unter [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span><span class="sxs-lookup"><span data-stu-id="e0feb-129">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="e0feb-130">Durch das Deaktivieren der Junk-E-Mail-Berichterstellung kann eine Nachricht nicht als Junk oder nicht als Junk in Outlook im Web markiert werden.</span><span class="sxs-lookup"><span data-stu-id="e0feb-130">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="e0feb-131">Wenn Sie eine Nachricht im Ordner Junk-E-Mail auswählen und auf **Nicht** Junk Nicht Junk klicken, wird die Nachricht trotzdem wieder \>  in den Posteingang verschoben.</span><span class="sxs-lookup"><span data-stu-id="e0feb-131">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="e0feb-132">Wenn Sie eine Nachricht in einem  anderen E-Mail-Ordner auswählen und auf Junk-Junk klicken, wird die Nachricht weiterhin \>  in den Junk-E-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="e0feb-132">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="e0feb-133">Was nicht mehr verfügbar ist, ist die Option, die Nachricht an Microsoft zu melden.</span><span class="sxs-lookup"><span data-stu-id="e0feb-133">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="e0feb-134">Verwenden von Exchange Online PowerShell zum Deaktivieren oder Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="e0feb-134">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="e0feb-135">Führen Sie den folgenden Befehl aus, um ihre vorhandenen Outlook im Webpostfachrichtlinien und den Status der Junk-E-Mail-Berichterstellung zu finden:</span><span class="sxs-lookup"><span data-stu-id="e0feb-135">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="e0feb-136">Verwenden Sie die folgende Syntax, um die Junk-E-Mail-Berichterstellung in Outlook im Web zu deaktivieren oder zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="e0feb-136">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="e0feb-137">In diesem Beispiel wird die Junk-E-Mail-Berichterstellung in der Standardrichtlinie deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="e0feb-137">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="e0feb-138">In diesem Beispiel wird die Junk-E-Mail-Berichterstellung in der benutzerdefinierten Richtlinie namens Contoso Managers aktiviert.</span><span class="sxs-lookup"><span data-stu-id="e0feb-138">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="e0feb-139">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) und [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span><span class="sxs-lookup"><span data-stu-id="e0feb-139">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="e0feb-140">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="e0feb-140">How do you know this worked?</span></span>

<span data-ttu-id="e0feb-141">Um zu überprüfen, ob Sie die Junk-E-Mail-Berichterstellung in Outlook im Web erfolgreich aktiviert oder deaktiviert haben, verwenden Sie einen der folgenden Schritte:</span><span class="sxs-lookup"><span data-stu-id="e0feb-141">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="e0feb-142">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, und überprüfen Sie den Wert der **ReportJunkEmailEnabled-Eigenschaft:**</span><span class="sxs-lookup"><span data-stu-id="e0feb-142">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="e0feb-143">Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Web,  wählen Sie eine Nachricht im Posteingang aus, klicken Sie auf Junk-Junk, und überprüfen Sie, ob die Meldung an Microsoft angezeigt wird oder nicht \>  angezeigt wird.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0feb-143">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="e0feb-144">Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Web,  wählen Sie eine Nachricht im Ordner Junk-E-Mail aus, klicken Sie auf Junk-Junk, und überprüfen Sie, ob die Meldung an Microsoft angezeigt wird oder nicht \>  angezeigt wird.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="e0feb-144">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="e0feb-145"><sup>\*</sup> Benutzer können die Aufforderung zum Melden der Nachricht ausblenden, während sie die Nachricht weiterhin melden.</span><span class="sxs-lookup"><span data-stu-id="e0feb-145"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="e0feb-146">So überprüfen Sie diese Einstellung in Outlook im Web:</span><span class="sxs-lookup"><span data-stu-id="e0feb-146">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="e0feb-147">Klicken **Sie auf Einstellungen** Outlook im ![ Webeinstellungen Symbol Alle ](../../media/owa-settings-icon.png) \> **Outlook-Einstellungen** \> **Junk-E-Mail anzeigen.**</span><span class="sxs-lookup"><span data-stu-id="e0feb-147">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="e0feb-148">Überprüfen Sie **im Abschnitt** Berichterstellung den Wert: Fragen **Sie mich, bevor Sie einen Bericht senden.**</span><span class="sxs-lookup"><span data-stu-id="e0feb-148">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Einstellungen für die Junk-E-Mail-Berichterstellung in Outlook im Web](../../media/owa-junk-email-reporting-options.png)