---
title: Angeben eines Postfachs für Benutzerübermittlungen von Spam-und Phishing-Nachrichten
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie ein Postfach So konfigurieren, dass Spam-und Phishing-e-Mails erfasst werden, die von Benutzern gemeldet werden.
ms.openlocfilehash: 6ae534278f4471f98f2d3bdd2318c687cea9f1d3
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195807"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="a194e-103">Angeben eines Postfachs für Benutzer Übermittlungen von Spam-und Phishing-Nachrichten in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a194e-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="a194e-104">In Microsoft 365-Organisationen mit Exchange Online Postfächern können Sie ein Postfach für den Empfang von Nachrichten angeben, die von Benutzern als bösartig oder nicht bösartig gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="a194e-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="a194e-105">Wenn Benutzer Nachrichten über die verschiedenen Berichtsoptionen übermitteln, können Sie dieses Postfach zum Abfangen von Nachrichten (nur an das benutzerdefinierte Postfach senden) oder zum Empfangen von Kopien von Nachrichten (senden an das benutzerdefinierte Postfach und Microsoft) verwenden.</span><span class="sxs-lookup"><span data-stu-id="a194e-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="a194e-106">Dieses Feature funktioniert mit den folgenden Optionen für die Nachrichtenberichterstattung:</span><span class="sxs-lookup"><span data-stu-id="a194e-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="a194e-107">Das Add-in "Berichtsnachricht"</span><span class="sxs-lookup"><span data-stu-id="a194e-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="a194e-108">[Integrierte Berichterstellung in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (früher bekannt als Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="a194e-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="a194e-109">Integrierte Berichterstellung in Outlook für IOS und Android</span><span class="sxs-lookup"><span data-stu-id="a194e-109">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="a194e-110">Wenn die Berichterstellung [in Outlook im Internet deaktiviert](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)wurde, werden durch die Aktivierung von Benutzereingaben hier die Einstellungen außer Kraft gesetzt, und Benutzer können erneut Nachrichten in Outlook im Internet melden.</span><span class="sxs-lookup"><span data-stu-id="a194e-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="a194e-111">Sie können auch Nachrichten Berichterstattungstools von Drittanbietern konfigurieren, um Nachrichten an das von Ihnen angegebene Postfach weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="a194e-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="a194e-112">Durch das Übermitteln von Benutzern gemeldeten Nachrichten an ein benutzerdefiniertes Postfach anstatt direkt an Microsoft können Ihre Administratoren Nachrichten selektiv und manuell über [Administrator Übermittlung](admin-submission.md)an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="a194e-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a194e-113">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="a194e-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a194e-114">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="a194e-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="a194e-115">Wenn Sie direkt zur Seite **Benutzereingaben** wechseln möchten, verwenden Sie <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="a194e-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="a194e-116">Um die Konfiguration für Benutzer Übermittlungen zu ändern, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="a194e-116">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

  - <span data-ttu-id="a194e-117">**Organisationsverwaltung** oder **Sicherheitsadministrator** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="a194e-117">**Organization Management** or **Security Administrator** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
  - <span data-ttu-id="a194e-118">**Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="a194e-118">**Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="a194e-119">Konfigurieren des Postfachs für Benutzer Übermittlungen mithilfe des Security & Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="a194e-119">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="a194e-120">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Users Submissions**.</span><span class="sxs-lookup"><span data-stu-id="a194e-120">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="a194e-121">Wählen Sie auf der Seite **Benutzereingaben** , die angezeigt wird, eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a194e-121">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="a194e-122">a.</span><span class="sxs-lookup"><span data-stu-id="a194e-122">a.</span></span> <span data-ttu-id="a194e-123">**Aktivieren der Berichtsnachrichten Funktion für Outlook (empfohlen)**: Wählen Sie diese Option aus, wenn Sie das Add-in "Berichtsnachricht" oder die integrierte Berichterstellung in Outlook im Internet verwenden, und konfigurieren Sie dann die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="a194e-123">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="a194e-124">**Anpassen der Bestätigungsnachricht für Endbenutzer**: Klicken Sie auf diesen Link.</span><span class="sxs-lookup"><span data-stu-id="a194e-124">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="a194e-125">Konfigurieren Sie im angezeigten Flyout für die **Bestätigung der Nachrichten Anpassung** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="a194e-125">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="a194e-126">**Vor der Übermittlung**: Geben Sie in den Feldern **Titel** und **Bestätigungsmeldung** den beschreibenden Text ein, den Benutzer sehen, bevor Sie eine Nachricht mithilfe des Berichtsnachrichten-Add-Ins melden.</span><span class="sxs-lookup"><span data-stu-id="a194e-126">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="a194e-127">Sie können die Variable% type% verwenden, um den Übermittlungs einzubeziehen (Junk, not Junk, Phishing, etc.).</span><span class="sxs-lookup"><span data-stu-id="a194e-127">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="a194e-128">Wenn Sie eine Option auswählen, die die gemeldeten Nachrichten an Microsoft sendet, wird der Benachrichtigung auch der folgende Text hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="a194e-128">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="a194e-129">Ihre e-Mail-Nachricht wird an Microsoft zur Analyse übermittelt.</span><span class="sxs-lookup"><span data-stu-id="a194e-129">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="a194e-130">Einige e-Mails enthalten möglicherweise persönliche oder vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="a194e-130">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="a194e-131">**Nach der Übermittlung**: Klicken Sie auf ![ Symbol erweitern ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="a194e-131">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="a194e-132">Geben Sie in die **Meldungs** Felder **Titel** und Bestätigung den beschreibenden Text ein, den Benutzer sehen, nachdem Sie eine Nachricht mithilfe des Berichtsnachrichten-Add-ins gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="a194e-132">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="a194e-133">Sie können die Variable% type% verwenden, um den Übermittlungs einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="a194e-133">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="a194e-134">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a194e-134">When you're finished, click **Save**.</span></span> <span data-ttu-id="a194e-135">Klicken Sie auf der Seite **Benutzereingaben** auf wieder **herstellen** , um diese Werte zu löschen.</span><span class="sxs-lookup"><span data-stu-id="a194e-135">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="a194e-136">**Senden Sie die gemeldeten Nachrichten an**: führen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="a194e-136">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="a194e-137">**Microsoft (empfohlen)**: das Postfach "Benutzer Übermittlungen" wird nicht verwendet (alle gemeldeten Nachrichten werden an Microsoft weitergegeben).</span><span class="sxs-lookup"><span data-stu-id="a194e-137">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="a194e-138">**Microsoft und ein benutzerdefiniertes Postfach**: Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein.</span><span class="sxs-lookup"><span data-stu-id="a194e-138">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="a194e-139">Verteilergruppen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a194e-139">Distribution groups are not allowed.</span></span> <span data-ttu-id="a194e-140">Benutzer Übermittlungen werden sowohl an Microsoft für die Analyse als auch an das benutzerdefinierte Postfach für Ihr Administrator-oder Sicherheits Betriebsteam zu analysieren gehen.</span><span class="sxs-lookup"><span data-stu-id="a194e-140">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="a194e-141">**Benutzerdefiniertes Postfach**: Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein.</span><span class="sxs-lookup"><span data-stu-id="a194e-141">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="a194e-142">Verteilergruppen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="a194e-142">Distribution groups are not allowed.</span></span> <span data-ttu-id="a194e-143">Verwenden Sie diese Option, wenn die Nachricht nur für die Analyse zuerst an ein Administrator-oder Sicherheits Betriebsteam gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="a194e-143">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="a194e-144">Nachrichten werden nicht an Microsoft weitergeleitet, es sei denn, der Administrator leitet Sie selbst weiter.</span><span class="sxs-lookup"><span data-stu-id="a194e-144">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="a194e-145">US-Regierungsorganisationen (gcc, gcc-H und DoD) können nur **benutzerdefiniertes Postfach**konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="a194e-145">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="a194e-146">Die beiden anderen Optionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="a194e-146">The other two options are disabled.</span></span> 

      <span data-ttu-id="a194e-147">Wenn Sie fertig sind, klicken Sie auf **bestätigen**.</span><span class="sxs-lookup"><span data-stu-id="a194e-147">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="a194e-148">Wenn Sie die [Junk-e-Mail-Berichterstellung in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) im Internet mit Outlook im WebPost Fach Richtlinien deaktiviert haben, aber eine der vorherigen Einstellungen für das Melden von Nachrichten an Microsoft konfiguriert haben, können Benutzer Nachrichten an Microsoft in Outlook im Internet über das Add-in "Berichtsnachricht" melden.</span><span class="sxs-lookup"><span data-stu-id="a194e-148">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="a194e-149">**Deaktivieren der Berichtsnachrichten Funktion für Outlook**: Wählen Sie diese Option aus, wenn Sie Drittanbieter-Berichterstattungstools anstelle des Berichtsnachrichten-Add-Ins oder der integrierten Berichterstellung in Outlook im Internet verwenden, und konfigurieren Sie dann die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="a194e-149">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="a194e-150">Wählen Sie **dieses benutzerdefinierte Postfach verwenden aus, um Benutzer gemeldete Übermittlungen zu empfangen**.</span><span class="sxs-lookup"><span data-stu-id="a194e-150">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="a194e-151">Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Postfachs ein, das sich bereits in Office 365 befindet.</span><span class="sxs-lookup"><span data-stu-id="a194e-151">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="a194e-152">Hierbei muss es sich um ein vorhandenes Postfach in Exchange Online handeln, das e-Mails empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="a194e-152">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="a194e-153">Wenn Sie fertig sind, klicken Sie auf **bestätigen**.</span><span class="sxs-lookup"><span data-stu-id="a194e-153">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="a194e-154">Nachrichten Übermittlungs Format</span><span class="sxs-lookup"><span data-stu-id="a194e-154">Message submission format</span></span>

<span data-ttu-id="a194e-155">Nachrichten, die an benutzerdefinierte Postfächer gesendet werden, müssen einem bestimmten Übermittlungs Nachrichtenformat entsprechen.</span><span class="sxs-lookup"><span data-stu-id="a194e-155">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="a194e-156">Der Betreff (Umschlag Titel) der Übermittlung sollte in folgendem Format vorliegen:</span><span class="sxs-lookup"><span data-stu-id="a194e-156">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="a194e-157">were SafetyAPIAction ist einer der folgenden Integer-Werte:</span><span class="sxs-lookup"><span data-stu-id="a194e-157">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="a194e-158">1: Junk</span><span class="sxs-lookup"><span data-stu-id="a194e-158">1: Junk</span></span>
- <span data-ttu-id="a194e-159">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="a194e-159">2: NotJunk</span></span>
- <span data-ttu-id="a194e-160">3: Phishing</span><span class="sxs-lookup"><span data-stu-id="a194e-160">3: Phish</span></span>

<span data-ttu-id="a194e-161">Im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="a194e-161">In the following example:</span></span>

- <span data-ttu-id="a194e-162">Die Nachricht wird als Phishing gemeldet.</span><span class="sxs-lookup"><span data-stu-id="a194e-162">The message is being reported as Phish.</span></span>
- <span data-ttu-id="a194e-163">Die Netzwerknachrichten-ID lautet 49871234-6dc6-43E8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="a194e-163">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="a194e-164">Die Absender-IP-Adresse lautet 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="a194e-164">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="a194e-165">Die von-Adresse lautet Test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="a194e-165">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="a194e-166">Die Betreffzeile der Nachricht lautet "Testen der Phishing-Übermittlung"</span><span class="sxs-lookup"><span data-stu-id="a194e-166">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="a194e-167">Nachrichten, die diesem Format nicht entsprechen, werden im Übermittlungen-Portal nicht ordnungsgemäß angezeigt.</span><span class="sxs-lookup"><span data-stu-id="a194e-167">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
