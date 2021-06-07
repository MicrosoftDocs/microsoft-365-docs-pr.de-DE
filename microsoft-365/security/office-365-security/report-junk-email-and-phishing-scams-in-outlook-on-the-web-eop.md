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
description: Administratoren können sich über die integrierten Optionen für Junk-, nicht Junk- und Phishing-E-Mail-Berichterstellung in Outlook im Web (Outlook Web App) in Exchange Online informieren und erfahren, wie diese Berichtsoptionen für Benutzer deaktiviert werden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1139871f5929ff9fef29e980b7614e5bc7b92570
ms.sourcegitcommit: b09aee96a1e2266b33ba81dfe497f24c5300bb56
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/06/2021
ms.locfileid: "52788307"
---
# <a name="report-junk-and-phishing-email-in-outlook-on-the-web-in-exchange-online"></a><span data-ttu-id="5ccee-103">Melden von Junk- und Phishing-E-Mails in Outlook im Web in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="5ccee-103">Report junk and phishing email in Outlook on the web in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="5ccee-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="5ccee-104">**Applies to**</span></span>
- [<span data-ttu-id="5ccee-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="5ccee-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="5ccee-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="5ccee-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="5ccee-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5ccee-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="5ccee-108">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder lokalen Postfächern mit [moderner Hybridauthentifizierung](../../enterprise/hybrid-modern-auth-overview.md)können Sie falsch positive Ergebnisse (als Spam markierte gute E-Mails), falsch negative Nachrichten (ungültige E-Mails sind zulässig) und Phishingnachrichten an Exchange Online Protection (EOP) übermitteln.</span><span class="sxs-lookup"><span data-stu-id="5ccee-108">In Microsoft 365 organizations with mailboxes in Exchange Online or on-premises mailboxes using [hybrid modern authentication](../../enterprise/hybrid-modern-auth-overview.md), you can submit false positives (good email marked as spam), false negatives (bad email allowed), and phishing messages to Exchange Online Protection (EOP).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5ccee-109">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="5ccee-109">What do you need to know before you begin?</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ccee-110">Wir empfehlen das Add-In "Nachricht melden" oder das Add-In "Phishing melden" für Benutzerübermittlungen.</span><span class="sxs-lookup"><span data-stu-id="5ccee-110">We recommend the Report Message add-in or the Report Phishing add-in for user submissions.</span></span> <span data-ttu-id="5ccee-111">Weitere Informationen finden Sie unter [Aktivieren der Berichtsnachricht oder der Phishing-Add-Ins "Bericht".](./enable-the-report-message-add-in.md) Es wird nicht empfohlen, die integrierte Berichterstellung in Outlook zu verwenden, da die [Benutzerübermittlungsrichtlinie](./user-submission.md)nicht verwendet werden kann.</span><span class="sxs-lookup"><span data-stu-id="5ccee-111">For more information, see [Enable the Report Message or the Report Phishing add-ins](./enable-the-report-message-add-in.md). We don't recommend the built-in reporting experience in Outlook because it can't use the [user submission policy](./user-submission.md).</span></span>

- <span data-ttu-id="5ccee-112">Wenn Sie ein Administrator in einer Organisation mit Exchange Online Postfächern sind, empfehlen wir, das Übermittlungsportal im Security & Compliance Center zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="5ccee-112">If you're an admin in an organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="5ccee-113">Weitere Informationen finden Sie unter ["Verwenden der Administratorübermittlung" zum Übermitteln von verdächtigem Spam, Phishing, URLs und Dateien an Microsoft.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="5ccee-113">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

- <span data-ttu-id="5ccee-114">Administratoren können die Möglichkeit für Benutzer deaktivieren oder aktivieren, Nachrichten in Outlook im Web an Microsoft zu melden.</span><span class="sxs-lookup"><span data-stu-id="5ccee-114">Admins can disable or enable the ability for users to report messages to Microsoft in Outlook on the web.</span></span> <span data-ttu-id="5ccee-115">Ausführliche Informationen finden Sie unter "Deaktivieren oder Aktivieren der [Junk-E-Mail-Berichterstellung in Outlook im Webabschnitt](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) weiter unten in diesem Artikel".</span><span class="sxs-lookup"><span data-stu-id="5ccee-115">For details, see the [Disable or enable junk email reporting in Outlook on the web](#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) section later in this article.</span></span>

- <span data-ttu-id="5ccee-116">Sie können gemeldete Nachrichten so konfigurieren, dass sie in ein von Ihnen angegebenes Postfach kopiert oder umgeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="5ccee-116">You can configure reported messages to be copied or redirected to a mailbox that you specify.</span></span> <span data-ttu-id="5ccee-117">Weitere Informationen finden Sie unter [Richtlinien für Benutzerübermittlungen.](user-submission.md)</span><span class="sxs-lookup"><span data-stu-id="5ccee-117">For more information, see [User submissions policies](user-submission.md).</span></span>

- <span data-ttu-id="5ccee-118">Weitere Informationen zum Melden von Nachrichten an Microsoft finden Sie unter [Melden von Nachrichten und Dateien an Microsoft.](report-junk-email-messages-to-microsoft.md)</span><span class="sxs-lookup"><span data-stu-id="5ccee-118">For more information about reporting messages to Microsoft, see [Report messages and files to Microsoft](report-junk-email-messages-to-microsoft.md).</span></span>

## <a name="disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="5ccee-119">Deaktivieren oder Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="5ccee-119">Disable or enable junk email reporting in Outlook on the web</span></span>

<span data-ttu-id="5ccee-120">Standardmäßig können Benutzer Falsch positive Spamnachrichten, falsch negative Ergebnisse und Phishingnachrichten zur Analyse in Outlook im Web an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="5ccee-120">By default, users can report spam false positives, false negatives, and phishing messages to Microsoft for analysis in Outlook on the web.</span></span> <span data-ttu-id="5ccee-121">Administratoren können Outlook in den Postfachrichtlinien im Web in Exchange Online PowerShell konfigurieren, um zu verhindern, dass Benutzer Spam falsch positive ergebnisse und falsch negative Spamnachrichten an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="5ccee-121">Admins can configure Outlook on the web mailbox policies in Exchange Online PowerShell to prevent users from reporting spam false positives and spam false negatives to Microsoft.</span></span> <span data-ttu-id="5ccee-122">Sie können die Möglichkeit für Benutzer, Phishingnachrichten an Microsoft zu melden, nicht deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="5ccee-122">You can't disable the ability for users to report phishing messages to Microsoft.</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="5ccee-123">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="5ccee-123">What do you need to know before you begin?</span></span>

- <span data-ttu-id="5ccee-124">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="5ccee-124">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

- <span data-ttu-id="5ccee-125">Bevor Sie die Verfahren in diesem Artikel ausführen können, müssen Ihnen in Exchange Online Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="5ccee-125">You need to be assigned permissions in Exchange Online before you can do the procedures in this article.</span></span> <span data-ttu-id="5ccee-126">Insbesondere benötigen Sie die **Empfängerrichtlinien** oder **E-Mail-Empfängerrollen,** die standardmäßig den Rollengruppen **"Organisationsverwaltung"** und **"Empfängerverwaltung"** zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="5ccee-126">Specifically you need the **Recipient Policies** or **Mail Recipients** roles, which are assigned to the **Organization Management** and **Recipient Management** role groups by default.</span></span> <span data-ttu-id="5ccee-127">Weitere Informationen zu Rollengruppen in Exchange Online finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo) und Ändern von [Rollengruppen in Exchange Online.](/Exchange/permissions-exo/role-groups#modify-role-groups)</span><span class="sxs-lookup"><span data-stu-id="5ccee-127">For more information about role groups in Exchange Online, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo) and [Modify role groups in Exchange Online](/Exchange/permissions-exo/role-groups#modify-role-groups).</span></span>

- <span data-ttu-id="5ccee-128">Jede Organisation verfügt über eine Standardrichtlinie mit dem Namen OwaMailboxPolicy-Default, Sie können jedoch benutzerdefinierte Richtlinien erstellen.</span><span class="sxs-lookup"><span data-stu-id="5ccee-128">Every organization has a default policy named OwaMailboxPolicy-Default, but you can create custom policies.</span></span> <span data-ttu-id="5ccee-129">Benutzerdefinierte Richtlinien werden vor der Standardrichtlinie auf bereichsbezogene Benutzer angewendet.</span><span class="sxs-lookup"><span data-stu-id="5ccee-129">Custom policies are applied to scoped users before the default policy.</span></span> <span data-ttu-id="5ccee-130">Weitere Informationen zu Outlook im Web-Postfachrichtlinien finden Sie unter [Outlook in den Webpostfachrichtlinien in Exchange Online.](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies)</span><span class="sxs-lookup"><span data-stu-id="5ccee-130">For more information about Outlook on the web mailbox policies, see [Outlook on the web mailbox policies in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/outlook-web-app-mailbox-policies).</span></span>

- <span data-ttu-id="5ccee-131">Das Deaktivieren der Junk-E-Mail-Berichterstellung entfernt nicht die Möglichkeit, eine Nachricht in Outlook im Web als Junk oder nicht als Junk zu kennzeichnen.</span><span class="sxs-lookup"><span data-stu-id="5ccee-131">Disabling junk email reporting doesn't remove the ability to mark a message as junk or not junk in Outlook on the web.</span></span> <span data-ttu-id="5ccee-132">Wenn Sie eine Nachricht im Junk-E-Mail-Ordner auswählen und auf **"Keine Junk-Junk-Nachricht"** klicken, \>  wird die Nachricht trotzdem zurück in den Posteingang verschoben.</span><span class="sxs-lookup"><span data-stu-id="5ccee-132">Selecting a message in the Junk email folder and clicking **Not junk** \> **Not junk** still moves the message back into the Inbox.</span></span> <span data-ttu-id="5ccee-133">Wenn Sie eine Nachricht in einem  beliebigen anderen E-Mail-Ordner auswählen und auf \> **Junk-Junk** klicken, wird die Nachricht dennoch in den Junk-E-Mail-Ordner verschoben.</span><span class="sxs-lookup"><span data-stu-id="5ccee-133">Selecting a message in any other email folder and clicking **Junk** \> **Junk** still moves the message into the Junk Email folder.</span></span> <span data-ttu-id="5ccee-134">Was nicht mehr verfügbar ist, ist die Option, die Nachricht an Microsoft zu melden.</span><span class="sxs-lookup"><span data-stu-id="5ccee-134">What's no longer available is the option to report the message to Microsoft.</span></span>

### <a name="use-exchange-online-powershell-to-disable-or-enable-junk-email-reporting-in-outlook-on-the-web"></a><span data-ttu-id="5ccee-135">Verwenden Exchange Online PowerShell zum Deaktivieren oder Aktivieren der Junk-E-Mail-Berichterstellung in Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="5ccee-135">Use Exchange Online PowerShell to disable or enable junk email reporting in Outlook on the web</span></span>

1. <span data-ttu-id="5ccee-136">Führen Sie den folgenden Befehl aus, um Ihre vorhandenen Outlook im Web-Postfachrichtlinien und den Status der Junk-E-Mail-Berichterstellung zu finden:</span><span class="sxs-lookup"><span data-stu-id="5ccee-136">To find your existing Outlook on the web mailbox policies and the status of junk email reporting, run the following command:</span></span>

   ```powershell
   Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
   ```

2. <span data-ttu-id="5ccee-137">Verwenden Sie die folgende Syntax, um die Junk-E-Mail-Berichterstellung in Outlook im Web zu deaktivieren oder zu aktivieren:</span><span class="sxs-lookup"><span data-stu-id="5ccee-137">To disable or enable junk email reporting in Outlook on the web, use the following syntax:</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "<OWAMailboxPolicyName>" -ReportJunkEmailEnabled <$true | $false>
   ```

   <span data-ttu-id="5ccee-138">In diesem Beispiel wird die Junk-E-Mail-Berichterstellung in der Standardrichtlinie deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="5ccee-138">This example disables junk email reporting in the default policy.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "OwaMailboxPolicy-Default" -ReportJunkEmailEnabled $false
   ```

   <span data-ttu-id="5ccee-139">In diesem Beispiel wird die Junk-E-Mail-Berichterstellung in der benutzerdefinierten Richtlinie namens Contoso Managers aktiviert.</span><span class="sxs-lookup"><span data-stu-id="5ccee-139">This example enables junk email reporting in the custom policy named Contoso Managers.</span></span>

   ```powershell
   Set-OwaMailboxPolicy -Identity "Contoso Managers" -ReportJunkEmailEnabled $true
   ```

<span data-ttu-id="5ccee-140">Ausführliche Informationen zu Syntax und Parametern finden Sie unter ["Get-OwaMailboxPolicy"](/powershell/module/exchange/get-owamailboxpolicy) und ["Set-OwaMailboxPolicy".](/powershell/module/exchange/set-owamailboxpolicy)</span><span class="sxs-lookup"><span data-stu-id="5ccee-140">For detailed syntax and parameter information, see [Get-OwaMailboxPolicy](/powershell/module/exchange/get-owamailboxpolicy) and [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="5ccee-141">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="5ccee-141">How do you know this worked?</span></span>

<span data-ttu-id="5ccee-142">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Die Junk-E-Mail-Berichterstellung in Outlook im Web erfolgreich aktiviert oder deaktiviert wurde:</span><span class="sxs-lookup"><span data-stu-id="5ccee-142">To verify that you've successfully enabled or disabled junk email reporting in Outlook on the web, use any of the following steps:</span></span>

- <span data-ttu-id="5ccee-143">Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, und überprüfen Sie den Wert der **ReportJunkEmailEnabled-Eigenschaft:**</span><span class="sxs-lookup"><span data-stu-id="5ccee-143">In Exchange Online PowerShell, run the following command and verify the **ReportJunkEmailEnabled** property value:</span></span>

  ```powershell
  Get-OwaMailboxPolicy | Format-Table Name,ReportJunkEmailEnabled
  ```

- <span data-ttu-id="5ccee-144">Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Web, wählen Sie eine Nachricht im Posteingang aus, klicken Sie auf **Junk-Junk,** \>  und überprüfen Sie, ob die Aufforderung, die Nachricht an Microsoft zu melden, angezeigt wird oder nicht.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5ccee-144">Open an affected user's mailbox in Outlook on the web, select a message in the Inbox, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

- <span data-ttu-id="5ccee-145">Öffnen Sie das Postfach eines betroffenen Benutzers in Outlook im Web, wählen Sie eine Nachricht im Junk-E-Mail-Ordner aus, klicken Sie auf **Junk-Junk,** \>  und überprüfen Sie, ob die Aufforderung, die Nachricht an Microsoft zu melden, angezeigt wird oder nicht.<sup>\*</sup></span><span class="sxs-lookup"><span data-stu-id="5ccee-145">Open an affected user's mailbox in Outlook on the web, select a message in the Junk Email folder, click **Junk** \> **Junk** and verify the prompt to report the message to Microsoft is or is not displayed.<sup>\*</sup></span></span>

<span data-ttu-id="5ccee-146"><sup>\*</sup> Benutzer können die Eingabeaufforderung ausblenden, um die Nachricht zu melden, während sie die Nachricht weiterhin melden.</span><span class="sxs-lookup"><span data-stu-id="5ccee-146"><sup>\*</sup> Users can hide the prompt to report the message while still reporting the message.</span></span> <span data-ttu-id="5ccee-147">So überprüfen Sie diese Einstellung in Outlook im Web:</span><span class="sxs-lookup"><span data-stu-id="5ccee-147">To check this setting in Outlook on the web:</span></span>

1. <span data-ttu-id="5ccee-148">Klicken Sie **auf Einstellungen** Outlook im ![ Symbol "Webeinstellungen ](../../media/owa-settings-icon.png) \> **anzeigen alle Outlook Einstellungen** \> **Junk-E-Mail** anzeigen".</span><span class="sxs-lookup"><span data-stu-id="5ccee-148">Click **Settings** ![Outlook on the web settings icon](../../media/owa-settings-icon.png) \> **View all Outlook settings** \> **Junk email**.</span></span>
2. <span data-ttu-id="5ccee-149">Überprüfen Sie im Abschnitt **"Berichterstellung"** den Wert: **Fragen Sie mich vor dem Senden eines Berichts.**</span><span class="sxs-lookup"><span data-stu-id="5ccee-149">In the **Reporting** section, verify the value: **Ask me before sending a report**.</span></span>

   ![Outlook in den Junk-E-Mail-Berichterstellungseinstellungen im Web](../../media/owa-junk-email-reporting-options.png)
