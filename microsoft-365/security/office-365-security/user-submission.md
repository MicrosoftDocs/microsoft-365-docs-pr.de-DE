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
ms.openlocfilehash: 458938105d03cb82dfa4e9a7824f8b026fddec5d
ms.sourcegitcommit: 89b2ad0793c68415f178b8792a9757b9448345a6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/28/2020
ms.locfileid: "47294753"
---
# <a name="specify-a-mailbox-for-user-submissions-of-spam-and-phishing-messages-in-exchange-online"></a><span data-ttu-id="91b2e-103">Angeben eines Postfachs für Benutzer Übermittlungen von Spam-und Phishing-Nachrichten in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="91b2e-103">Specify a mailbox for user submissions of spam and phishing messages in Exchange Online</span></span>

<span data-ttu-id="91b2e-104">In Microsoft 365-Organisationen mit Exchange Online Postfächern können Sie ein Postfach für den Empfang von Nachrichten angeben, die von Benutzern als bösartig oder nicht bösartig gemeldet werden.</span><span class="sxs-lookup"><span data-stu-id="91b2e-104">In Microsoft 365 organizations with Exchange Online mailboxes, you can specify a mailbox to receive messages that users report as malicious or not malicious.</span></span> <span data-ttu-id="91b2e-105">Wenn Benutzer Nachrichten über die verschiedenen Berichtsoptionen übermitteln, können Sie dieses Postfach zum Abfangen von Nachrichten (nur an das benutzerdefinierte Postfach senden) oder zum Empfangen von Kopien von Nachrichten (senden an das benutzerdefinierte Postfach und Microsoft) verwenden.</span><span class="sxs-lookup"><span data-stu-id="91b2e-105">When users submit messages using the various reporting options, you can use this mailbox to intercept messages (send to the custom mailbox only) or receive copies of messages (send to the custom mailbox and Microsoft).</span></span> <span data-ttu-id="91b2e-106">Dieses Feature funktioniert mit den folgenden Optionen für die Nachrichtenberichterstattung:</span><span class="sxs-lookup"><span data-stu-id="91b2e-106">This feature works with the following message reporting options:</span></span>

- [<span data-ttu-id="91b2e-107">Das Add-in "Berichtsnachricht"</span><span class="sxs-lookup"><span data-stu-id="91b2e-107">The Report Message add-in</span></span>](enable-the-report-message-add-in.md)

- <span data-ttu-id="91b2e-108">[Integrierte Berichterstellung in Outlook im Internet](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (früher bekannt als Outlook Web App)</span><span class="sxs-lookup"><span data-stu-id="91b2e-108">[Built-in reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md) (formerly known as Outlook Web App)</span></span>

- [<span data-ttu-id="91b2e-109">Integrierte Berichterstellung in Outlook für IOS und Android</span><span class="sxs-lookup"><span data-stu-id="91b2e-109">Built-in reporting in Outlook for iOS and Android</span></span>](report-junk-email-and-phishing-scams-in-outlook-for-iOS-and-Android.md)

  > [!NOTE]
  > <span data-ttu-id="91b2e-110">Wenn die Berichterstellung [in Outlook im Internet deaktiviert](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web)wurde, werden durch die Aktivierung von Benutzereingaben hier die Einstellungen außer Kraft gesetzt, und Benutzer können erneut Nachrichten in Outlook im Internet melden.</span><span class="sxs-lookup"><span data-stu-id="91b2e-110">If reporting has been [disabled in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web), enabling user submissions here will override that setting and enable users to report messages in Outlook on the web again.</span></span>

<span data-ttu-id="91b2e-111">Sie können auch Nachrichten Berichterstattungstools von Drittanbietern konfigurieren, um Nachrichten an das von Ihnen angegebene Postfach weiterzuleiten.</span><span class="sxs-lookup"><span data-stu-id="91b2e-111">You can also configure third-party message reporting tools to forward messages to the mailbox that you specify.</span></span>

<span data-ttu-id="91b2e-112">Durch das Übermitteln von Benutzern gemeldeten Nachrichten an ein benutzerdefiniertes Postfach anstatt direkt an Microsoft können Ihre Administratoren Nachrichten selektiv und manuell über [Administrator Übermittlung](admin-submission.md)an Microsoft melden.</span><span class="sxs-lookup"><span data-stu-id="91b2e-112">Delivering user reported messages to a custom mailbox instead of directly to Microsoft allows your admins to selectively and manually report messages to Microsoft using [Admin submission](admin-submission.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="91b2e-113">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="91b2e-113">What do you need to know before you begin?</span></span>

- <span data-ttu-id="91b2e-114">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="91b2e-114">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="91b2e-115">Wenn Sie direkt zur Seite **Benutzereingaben** wechseln möchten, verwenden Sie <https://protection.office.com/userSubmissionsReportMessage> .</span><span class="sxs-lookup"><span data-stu-id="91b2e-115">To go directly to the **User submissions** page, use <https://protection.office.com/userSubmissionsReportMessage>.</span></span>

- <span data-ttu-id="91b2e-116">Bevor Sie die in diesem Artikel besprochenen Verfahren ausführen können, müssen Ihnen Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="91b2e-116">You need to be assigned permissions before you can do the procedures in this topic:</span></span>

  - <span data-ttu-id="91b2e-117">Um die Konfiguration für Benutzer Übermittlungen zu ändern, müssen Sie Mitglied einer der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="91b2e-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>

    - <span data-ttu-id="91b2e-118">**[Exchange-Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in Azure AD **und Organisationsverwaltung** oder **Sicherheits Administrator** und im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="91b2e-118">**[Exchange Administrator](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles#exchange-administrator)** in Azure AD and **Organization Management** or **Security Administrator** and in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="91b2e-119">**Organisationsverwaltung** oder **Nachrichtenschutz** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="91b2e-119">**Organization Management** or **Hygiene Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

  - <span data-ttu-id="91b2e-120">Für den schreibgeschützten Zugriff auf Benutzereingaben müssen Sie Mitglied der folgenden Rollengruppen sein:</span><span class="sxs-lookup"><span data-stu-id="91b2e-120">For read-only access to User submissions, you need to be a member of both of the following role groups:</span></span>

    - <span data-ttu-id="91b2e-121">**Security Reader** im [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="91b2e-121">**Security Reader** in the [Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>
    - <span data-ttu-id="91b2e-122">**Schreibgeschützte Organisationsverwaltung** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="91b2e-122">**View-Only Organization Management** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

## <a name="use-the-security--compliance-center-to-configure-the-user-submissions-mailbox"></a><span data-ttu-id="91b2e-123">Konfigurieren des Postfachs für Benutzer Übermittlungen mithilfe des Security & Compliance Centers</span><span class="sxs-lookup"><span data-stu-id="91b2e-123">Use the Security & Compliance Center to configure the user submissions mailbox</span></span>

1. <span data-ttu-id="91b2e-124">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Users Submissions**.</span><span class="sxs-lookup"><span data-stu-id="91b2e-124">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **User submissions**.</span></span>

2. <span data-ttu-id="91b2e-125">Wählen Sie auf der Seite **Benutzereingaben** , die angezeigt wird, eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="91b2e-125">In the **User submissions** page that appears, select one of the following options:</span></span>

   <span data-ttu-id="91b2e-126">a.</span><span class="sxs-lookup"><span data-stu-id="91b2e-126">a.</span></span> <span data-ttu-id="91b2e-127">**Aktivieren der Berichtsnachrichten Funktion für Outlook (empfohlen)**: Wählen Sie diese Option aus, wenn Sie das Add-in "Berichtsnachricht" oder die integrierte Berichterstellung in Outlook im Internet verwenden, und konfigurieren Sie dann die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="91b2e-127">**Enable the Report Message feature for Outlook (Recommended)**: Select this option if you use the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      - <span data-ttu-id="91b2e-128">**Anpassen der Bestätigungsnachricht für Endbenutzer**: Klicken Sie auf diesen Link.</span><span class="sxs-lookup"><span data-stu-id="91b2e-128">**Customize the end-user confirmation message**: Click this link.</span></span> <span data-ttu-id="91b2e-129">Konfigurieren Sie im angezeigten Flyout für die **Bestätigung der Nachrichten Anpassung** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="91b2e-129">In the **Customize confirmation message** flyout that appears, configure the following settings:</span></span>

      - <span data-ttu-id="91b2e-130">**Vor der Übermittlung**: Geben Sie in den Feldern **Titel** und **Bestätigungsmeldung** den beschreibenden Text ein, den Benutzer sehen, bevor Sie eine Nachricht mithilfe des Berichtsnachrichten-Add-Ins melden.</span><span class="sxs-lookup"><span data-stu-id="91b2e-130">**Before submission**: In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see before they report a message using the Report Message add-in.</span></span> <span data-ttu-id="91b2e-131">Sie können die Variable% type% verwenden, um den Übermittlungs einzubeziehen (Junk, not Junk, Phishing, etc.).</span><span class="sxs-lookup"><span data-stu-id="91b2e-131">You can use the variable %type% to include the submission type (junk, not junk, phish, etc.).</span></span>

        <span data-ttu-id="91b2e-132">Wenn Sie eine Option auswählen, die die gemeldeten Nachrichten an Microsoft sendet, wird der Benachrichtigung auch der folgende Text hinzugefügt:</span><span class="sxs-lookup"><span data-stu-id="91b2e-132">As noted, if you select an option that sends the reported messages to Microsoft, the following text is also added to the notification:</span></span>

        > <span data-ttu-id="91b2e-133">Ihre e-Mail-Nachricht wird an Microsoft zur Analyse übermittelt.</span><span class="sxs-lookup"><span data-stu-id="91b2e-133">Your email will be submitted as-is to Microsoft for analysis.</span></span> <span data-ttu-id="91b2e-134">Einige e-Mails enthalten möglicherweise persönliche oder vertrauliche Informationen.</span><span class="sxs-lookup"><span data-stu-id="91b2e-134">Some emails might contain personal or sensitive information.</span></span>

      - <span data-ttu-id="91b2e-135">**Nach der Übermittlung**: Klicken Sie auf ![ Symbol erweitern ](../../media/scc-expand-icon.png) .</span><span class="sxs-lookup"><span data-stu-id="91b2e-135">**After submission**: Click ![Expand icon](../../media/scc-expand-icon.png).</span></span> <span data-ttu-id="91b2e-136">Geben Sie in die **Meldungs** Felder **Titel** und Bestätigung den beschreibenden Text ein, den Benutzer sehen, nachdem Sie eine Nachricht mithilfe des Berichtsnachrichten-Add-ins gemeldet haben.</span><span class="sxs-lookup"><span data-stu-id="91b2e-136">In the **Title** and **Confirmation message** boxes, enter the descriptive text that users see after they report a message using the Report Message add-in.</span></span> <span data-ttu-id="91b2e-137">Sie können die Variable% type% verwenden, um den Übermittlungs einzubeziehen.</span><span class="sxs-lookup"><span data-stu-id="91b2e-137">You can use the variable %type% to include the submission type.</span></span>

      <span data-ttu-id="91b2e-138">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="91b2e-138">When you're finished, click **Save**.</span></span> <span data-ttu-id="91b2e-139">Klicken Sie auf der Seite **Benutzereingaben** auf wieder **herstellen** , um diese Werte zu löschen.</span><span class="sxs-lookup"><span data-stu-id="91b2e-139">To clear these values, click **Restore** back on the **User submissions** page.</span></span>

      - <span data-ttu-id="91b2e-140">**Senden Sie die gemeldeten Nachrichten an**: führen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="91b2e-140">**Send the reported messages to**: Make one of the following selections:</span></span>

        - <span data-ttu-id="91b2e-141">**Microsoft (empfohlen)**: das Postfach "Benutzer Übermittlungen" wird nicht verwendet (alle gemeldeten Nachrichten werden an Microsoft weitergegeben).</span><span class="sxs-lookup"><span data-stu-id="91b2e-141">**Microsoft (Recommended)**: The user submissions mailbox isn't used (all reported messages go to Microsoft).</span></span>

        - <span data-ttu-id="91b2e-142">**Microsoft und ein benutzerdefiniertes Postfach**: Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein.</span><span class="sxs-lookup"><span data-stu-id="91b2e-142">**Microsoft and a custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="91b2e-143">Verteilergruppen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="91b2e-143">Distribution groups are not allowed.</span></span> <span data-ttu-id="91b2e-144">Benutzer Übermittlungen werden sowohl an Microsoft für die Analyse als auch an das benutzerdefinierte Postfach für Ihr Administrator-oder Sicherheits Betriebsteam zu analysieren gehen.</span><span class="sxs-lookup"><span data-stu-id="91b2e-144">User submissions will go to both Microsoft for analysis and to the custom mailbox for your admin or security operations team to analyze.</span></span>

        - <span data-ttu-id="91b2e-145">**Benutzerdefiniertes Postfach**: Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Exchange Online Postfachs ein.</span><span class="sxs-lookup"><span data-stu-id="91b2e-145">**Custom mailbox**: In the box that appears, enter the email address of an existing Exchange Online mailbox.</span></span> <span data-ttu-id="91b2e-146">Verteilergruppen sind nicht zulässig.</span><span class="sxs-lookup"><span data-stu-id="91b2e-146">Distribution groups are not allowed.</span></span> <span data-ttu-id="91b2e-147">Verwenden Sie diese Option, wenn die Nachricht nur für die Analyse zuerst an ein Administrator-oder Sicherheits Betriebsteam gesendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="91b2e-147">Use this option if you want the message to only go to an admin or the security operations team for analysis first.</span></span> <span data-ttu-id="91b2e-148">Nachrichten werden nicht an Microsoft weitergeleitet, es sei denn, der Administrator leitet Sie selbst weiter.</span><span class="sxs-lookup"><span data-stu-id="91b2e-148">Messages will not go to Microsoft unless the admin forwards it themselves.</span></span>

        > [!NOTE]
        > <span data-ttu-id="91b2e-149">US-Regierungsorganisationen (gcc, gcc-H und DoD) können nur **benutzerdefiniertes Postfach**konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="91b2e-149">U.S. Government organizations (GCC, GCC-H, and DoD) can only configure **Custom mailbox**.</span></span> <span data-ttu-id="91b2e-150">Die beiden anderen Optionen sind deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="91b2e-150">The other two options are disabled.</span></span> 

      <span data-ttu-id="91b2e-151">Wenn Sie fertig sind, klicken Sie auf **bestätigen**.</span><span class="sxs-lookup"><span data-stu-id="91b2e-151">When you're finished, click **Confirm**.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="91b2e-152">Wenn Sie die [Junk-e-Mail-Berichterstellung in Outlook](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) im Internet mit Outlook im WebPost Fach Richtlinien deaktiviert haben, aber eine der vorherigen Einstellungen für das Melden von Nachrichten an Microsoft konfiguriert haben, können Benutzer Nachrichten an Microsoft in Outlook im Internet über das Add-in "Berichtsnachricht" melden.</span><span class="sxs-lookup"><span data-stu-id="91b2e-152">If you have [disabled junk email reporting in Outlook on the web](report-junk-email-and-phishing-scams-in-outlook-on-the-web-eop.md#disable-or-enable-junk-email-reporting-in-outlook-on-the-web) using Outlook on the web mailbox policies, but you configure either of the previous settings to report messages to Microsoft, users will be able to report messages to Microsoft in Outlook on the web using the Report Message add-in.</span></span>

   - <span data-ttu-id="91b2e-153">**Deaktivieren der Berichtsnachrichten Funktion für Outlook**: Wählen Sie diese Option aus, wenn Sie Drittanbieter-Berichterstattungstools anstelle des Berichtsnachrichten-Add-Ins oder der integrierten Berichterstellung in Outlook im Internet verwenden, und konfigurieren Sie dann die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="91b2e-153">**Disable the Report Message feature for Outlook**: Select this option if you use third-party reporting tools instead of the Report Message add-in or the built-in reporting in Outlook on the web, and then configure the following settings:</span></span>

      <span data-ttu-id="91b2e-154">Wählen Sie **dieses benutzerdefinierte Postfach verwenden aus, um Benutzer gemeldete Übermittlungen zu empfangen**.</span><span class="sxs-lookup"><span data-stu-id="91b2e-154">Select **Use this custom mailbox to receive user reported submissions**.</span></span> <span data-ttu-id="91b2e-155">Geben Sie in das Feld, das angezeigt wird, die e-Mail-Adresse eines vorhandenen Postfachs ein, das sich bereits in Office 365 befindet.</span><span class="sxs-lookup"><span data-stu-id="91b2e-155">In the box that appears, enter the email address of an existing mailbox that is already in Office 365.</span></span> <span data-ttu-id="91b2e-156">Hierbei muss es sich um ein vorhandenes Postfach in Exchange Online handeln, das e-Mails empfangen kann.</span><span class="sxs-lookup"><span data-stu-id="91b2e-156">This has to be an existing mailbox in Exchange Online that can receive email.</span></span>

      <span data-ttu-id="91b2e-157">Wenn Sie fertig sind, klicken Sie auf **bestätigen**.</span><span class="sxs-lookup"><span data-stu-id="91b2e-157">When you're finished, click **Confirm**.</span></span>

## <a name="message-submission-format"></a><span data-ttu-id="91b2e-158">Nachrichten Übermittlungs Format</span><span class="sxs-lookup"><span data-stu-id="91b2e-158">Message submission format</span></span>

<span data-ttu-id="91b2e-159">Nachrichten, die an benutzerdefinierte Postfächer gesendet werden, müssen einem bestimmten Übermittlungs Nachrichtenformat entsprechen.</span><span class="sxs-lookup"><span data-stu-id="91b2e-159">Messages sent to custom mailboxes need to follow a specific submission mail format.</span></span> <span data-ttu-id="91b2e-160">Der Betreff (Umschlag Titel) der Übermittlung sollte in folgendem Format vorliegen:</span><span class="sxs-lookup"><span data-stu-id="91b2e-160">The Subject (Envelope Title) of the submission should be in this format:</span></span>

`SafetyAPIAction|NetworkMessageId|SenderIp|FromAddress|(Message Subject)`

<span data-ttu-id="91b2e-161">were SafetyAPIAction ist einer der folgenden Integer-Werte:</span><span class="sxs-lookup"><span data-stu-id="91b2e-161">were SafetyAPIAction is one of the following integer values:</span></span>

- <span data-ttu-id="91b2e-162">1: Junk</span><span class="sxs-lookup"><span data-stu-id="91b2e-162">1: Junk</span></span>
- <span data-ttu-id="91b2e-163">2: NotJunk</span><span class="sxs-lookup"><span data-stu-id="91b2e-163">2: NotJunk</span></span>
- <span data-ttu-id="91b2e-164">3: Phishing</span><span class="sxs-lookup"><span data-stu-id="91b2e-164">3: Phish</span></span>

<span data-ttu-id="91b2e-165">Im folgenden Beispiel:</span><span class="sxs-lookup"><span data-stu-id="91b2e-165">In the following example:</span></span>

- <span data-ttu-id="91b2e-166">Die Nachricht wird als Phishing gemeldet.</span><span class="sxs-lookup"><span data-stu-id="91b2e-166">The message is being reported as Phish.</span></span>
- <span data-ttu-id="91b2e-167">Die Netzwerknachrichten-ID lautet 49871234-6dc6-43E8-ABCD-08d797f20abe.</span><span class="sxs-lookup"><span data-stu-id="91b2e-167">The Network Message ID is 49871234-6dc6-43e8-abcd-08d797f20abe.</span></span>
- <span data-ttu-id="91b2e-168">Die Absender-IP-Adresse lautet 167.220.232.101.</span><span class="sxs-lookup"><span data-stu-id="91b2e-168">The Sender IP is 167.220.232.101.</span></span>
- <span data-ttu-id="91b2e-169">Die von-Adresse lautet Test@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="91b2e-169">The From address is test@contoso.com.</span></span>
- <span data-ttu-id="91b2e-170">Die Betreffzeile der Nachricht lautet "Testen der Phishing-Übermittlung"</span><span class="sxs-lookup"><span data-stu-id="91b2e-170">The message's subject line is "test phish submission"</span></span>

`3|49871234-6dc6-43e8-abcd-08d797f20abe|167.220.232.101|test@contoso.com|(test phish submission)`

<span data-ttu-id="91b2e-171">Nachrichten, die diesem Format nicht entsprechen, werden im Übermittlungen-Portal nicht ordnungsgemäß angezeigt.</span><span class="sxs-lookup"><span data-stu-id="91b2e-171">Messages that do not follow this format will not display properly in the Submissions portal.</span></span>
