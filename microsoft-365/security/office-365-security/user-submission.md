---
title: Angeben eines Postfachs für Benutzerübermittlungen von Spam-und Phishing-Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie ein Postfach So konfigurieren, dass Spam-und Phishing-e-Mails erfasst werden, die von Benutzern gemeldet werden.
ms.openlocfilehash: 7b4b913a29c3eb16286d5a2874fe48bbc1c121fe
ms.sourcegitcommit: 93c0088d272cd45f1632a1dcaf04159f234abccd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2020
ms.locfileid: "44208501"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="e2926-103">Angeben eines Postfachs für Benutzer Übermittlungen von Spam-und Phishing-Nachrichten in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e2926-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="e2926-104">In Microsoft 365-Organisationen mit Exchange Online Postfächern können Sie ein Postfach für den Empfang von Nachrichten angeben, die von Benutzern als bösartig oder nicht bösartig gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="e2926-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="e2926-105">Wenn Benutzer Nachrichten über die verschiedenen Berichtsoptionen übermitteln, können Sie dieses Postfach zum Abfangen von Nachrichten (nur an das benutzerdefinierte Postfach senden) oder zum Empfangen von Kopien von Nachrichten (senden an das benutzerdefinierte Postfach und Microsoft) verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2926-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="e2926-106">Dieses Feature funktioniert mit den folgenden Optionen für die Nachrichtenberichterstattung:</span><span class="sxs-lookup"><span data-stu-id="e2926-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="e2926-107">Das Add-in "Berichtsnachricht"</span><span class="sxs-lookup"><span data-stu-id="e2926-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="e2926-108">[Integrierte Berichterstellung in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (früher bekannt als Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="e2926-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

<span data-ttu-id="e2926-109">Sie können auch Nachrichten Berichterstattungstools von Drittanbietern konfigurieren, um Nachrichten an das von Ihnen angegebene Postfach weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="e2926-109">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="e2926-110">Durch das Übermitteln von Benutzern gemeldeten Nachrichten an ein benutzerdefiniertes Postfach anstatt direkt an Microsoft können Ihre Administratoren Nachrichten selektiv und manuell über [Administrator Übermittlung](admin-submission.md)an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="e2926-110">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e2926-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="e2926-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="e2926-112">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="e2926-112">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="e2926-113">Wenn Sie direkt zur Seite **Benutzereingaben** wechseln möchten, verwenden Sie <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="e2926-113">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="e2926-114">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="e2926-114">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="e2926-115">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="e2926-115">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="e2926-116">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="e2926-116">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="e2926-117">Um das Postfach für Benutzer Übermittlungen zu konfigurieren, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="e2926-117">To configure the mailbox for user submissions, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="e2926-118">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="e2926-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="e2926-119">Konfigurieren des Postfachs für Benutzer Übermittlungen mithilfe des Security & Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="e2926-119">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="e2926-120">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Users Submissions**.</span><span class="sxs-lookup"><span data-stu-id="e2926-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="e2926-121">Wählen Sie auf der Seite **Benutzereingaben** , die angezeigt wird, eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="e2926-121">In the **User submissions** page that appears, select one of the following options:</span></span>

   - <span data-ttu-id="e2926-122">**Aktivieren der Berichtsnachrichten Funktion für Outlook (empfohlen)**: Wählen Sie diese Option aus, wenn Sie das Add-in "Berichtsnachricht" oder die integrierte Berichterstellung in Outlook im Internet verwenden, und konfigurieren Sie dann die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="e2926-122">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     - <span data-ttu-id="e2926-123">**Anpassen der Bestätigungsnachricht für Endbenutzer**: Klicken Sie auf diesen Link.</span><span class="sxs-lookup"><span data-stu-id="e2926-123">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="e2926-124">Konfigurieren Sie im angezeigten Flyout für die **Bestätigung der Nachrichten Anpassung** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="e2926-124">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

       - <span data-ttu-id="e2926-125">**Vor der Übermittlung**: Geben Sie in den Feldern **Titel** und **Bestätigungsmeldung** den beschreibenden Text ein, den Benutzer sehen, bevor Sie eine Nachricht mithilfe des Berichtsnachrichten-Add-Ins melden.</span><span class="sxs-lookup"><span data-stu-id="e2926-125">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="e2926-126">Sie können die Variable% type% verwenden, um den Übermittlungs einzubeziehen (Junk, not Junk, Phishing, etc.).</span><span class="sxs-lookup"><span data-stu-id="e2926-126">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

         <span data-ttu-id="e2926-127">Wie bereits erwähnt, wird der Benachrichtigung auch der folgende Text hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="e2926-127">As noted, the following text is also added to the notification:</span></span>

         > <span data-ttu-id="e2926-128">Ihre e-Mail-Nachricht wird an Microsoft zur Analyse übermittelt.</span><span class="sxs-lookup"><span data-stu-id="e2926-128">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="e2926-129">Einige e-Mails enthalten möglicherweise persönliche oder vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="e2926-129">Some emails might contain personal or sensitive information.</span></span>

       - <span data-ttu-id="e2926-130">**Nach der Übermittlung**: Klicken Sie auf ![ Symbol erweitern ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="e2926-130">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="e2926-131">Geben Sie in die **Meldungs** Felder **Titel** und Bestätigung den beschreibenden Text ein, den Benutzer sehen, nachdem Sie eine Nachricht mithilfe des Berichtsnachrichten-Add-ins gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="e2926-131">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="e2926-132">Sie können die Variable% type% verwenden, um den Übermittlungs einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="e2926-132">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="e2926-133">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="e2926-133">When you're finished, click **Save**.</span></span> <span data-ttu-id="e2926-134">Klicken Sie auf der Seite **Benutzereingaben** auf wieder **herstellen** , um diese Werte zu löschen.</span><span class="sxs-lookup"><span data-stu-id="e2926-134">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

   - <span data-ttu-id="e2926-135">**Senden Sie die gemeldeten Nachrichten an**: führen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="e2926-135">**Send the reported messages to**: Make one of the following selections:</span></span>

     - <span data-ttu-id="e2926-136">**Microsoft (empfohlen)**: das Postfach "Benutzer Übermittlungen" wird nicht verwendet (alle gemeldeten Nachrichten werden an Microsoft weitergegeben).</span><span class="sxs-lookup"><span data-stu-id="e2926-136">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

     - <span data-ttu-id="e2926-137">**Microsoft und ein benutzerdefiniertes Postfach**: Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein.</span><span class="sxs-lookup"><span data-stu-id="e2926-137">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="e2926-138">Verteilergruppen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="e2926-138">Distribution groups are not allowed.</span></span>

     - <span data-ttu-id="e2926-139">**Benutzerdefiniertes Postfach**: Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein.</span><span class="sxs-lookup"><span data-stu-id="e2926-139">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="e2926-140">Verteilergruppen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="e2926-140">Distribution groups are not allowed.</span></span>

     <span data-ttu-id="e2926-141">Wenn Sie fertig sind, klicken Sie auf **bestätigen**.</span><span class="sxs-lookup"><span data-stu-id="e2926-141">When you're finished, click **Confirm**.</span></span>

     ![Senden von gemeldeten Nachrichten an Microsoft und ein benutzerdefiniertes Postfach](../../media/user-submission-enable-outlook-report-message.png)

   - <span data-ttu-id="e2926-143">**Deaktivieren der Berichtsnachrichten Funktion für Outlook**: Wählen Sie diese Option aus, wenn Sie Drittanbieter-Berichterstattungstools anstelle des Berichtsnachrichten-Add-Ins oder der integrierten Berichterstellung in Outlook im Internet verwenden, und konfigurieren Sie dann die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="e2926-143">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

     <span data-ttu-id="e2926-144">Wählen Sie **dieses benutzerdefinierte Postfach verwenden aus, um Benutzer gemeldete Übermittlungen zu empfangen**.</span><span class="sxs-lookup"><span data-stu-id="e2926-144">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="e2926-145">Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Postfachs oder die e-Mail-Adresse des Postfachs ein, das Sie erstellen möchten.</span><span class="sxs-lookup"><span data-stu-id="e2926-145">In the box that appears, enter the email address of an existing mailbox, or the email address of the mailbox that you want to create.</span></span>

     <span data-ttu-id="e2926-146">Wenn Sie fertig sind, klicken Sie auf **bestätigen**.</span><span class="sxs-lookup"><span data-stu-id="e2926-146">When you're finished, click **Confirm**.</span></span>

     ![Senden von gemeldeten Nachrichten an ein benutzerdefiniertes Postfach mithilfe von Drittanbietertools](../../media/user-submission-disable-outlook-report-message.png)
