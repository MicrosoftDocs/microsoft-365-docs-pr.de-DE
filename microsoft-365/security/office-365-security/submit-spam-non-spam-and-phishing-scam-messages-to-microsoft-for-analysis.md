---
title: Manuelles übermitteln von Nachrichten an Microsoft zur Analyse
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
ms.assetid: dad30e2f-93fe-4d21-9a36-21c87ced85c1
ms.collection:
- M365-security-compliance
description: 'Sie und Ihre Benutzer können falsche Negative und falsch positive Spamnachrichten zur Analyse an Microsoft übermitteln. '
ms.openlocfilehash: f6dbd808fac54ae273c21773bf8caeabce09b7fb
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43631241"
---
# <a name="manually-submit-messages-to-microsoft-for-analysis"></a><span data-ttu-id="a7f60-103">Manuelles übermitteln von Nachrichten an Microsoft zur Analyse</span><span class="sxs-lookup"><span data-stu-id="a7f60-103">Manually submit messages to Microsoft for analysis</span></span>

> [!NOTE]
> <span data-ttu-id="a7f60-104">Wenn Sie ein Administrator in einer Microsoft 365-Organisation mit Exchange Online Postfächern sind, wird empfohlen, dass Sie das Portal für Übermittlungen im Security & Compliance Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7f60-104">If you're an admin in an Microsoft 365 organization with Exchange Online mailboxes, we recommend that you use the Submissions portal in the Security & Compliance Center.</span></span> <span data-ttu-id="a7f60-105">Weitere Informationen finden Sie unter [Verwenden der Administrator Übermittlung zum Übermitteln von verdächtigen Spam, Phishing, URLs und Dateien an Microsoft](admin-submission.md).</span><span class="sxs-lookup"><span data-stu-id="a7f60-105">For more information, see [Use Admin Submission to submit suspected spam, phish, URLs, and files to Microsoft](admin-submission.md).</span></span>

<span data-ttu-id="a7f60-106">Es kann frustrierend sein, wenn Benutzer in Ihrer Organisation Junk-Nachrichten (Spam) oder Phishing-Nachrichten in Ihrem Posteingang empfangen oder wenn Sie keine legitime e-Mail-Nachricht erhalten, weil Sie als Junk gekennzeichnet ist.</span><span class="sxs-lookup"><span data-stu-id="a7f60-106">It can be frustrating when users in your organization receive junk messages (spam) or phishing messages in their Inbox, or if they don't receive a legitimate email message because it's marked as junk.</span></span> <span data-ttu-id="a7f60-107">Wir optimieren unsere Spamfilter ständig, um genauere Angaben zu machen.</span><span class="sxs-lookup"><span data-stu-id="a7f60-107">We're constantly fine-tuning our spam filters to be more accurate.</span></span>

<span data-ttu-id="a7f60-108">Sie und Ihre Benutzer können diesen Prozess unterstützen, indem Sie falsch positive Ergebnisse (gute e-Mail-Nachrichten als ungültig markiert), falsche Negative Zeichen (ungültige e-Mail-Nachricht) und Phishing-Nachrichten zur Analyse an Microsoft senden.</span><span class="sxs-lookup"><span data-stu-id="a7f60-108">You and your users can help this process by submitting false positives (good email marked as bad), false negatives (bad mail allowed) and phishing messages to Microsoft for analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="a7f60-109">Aufgrund der hohen Anzahl von Übermittlungen, die wir erhalten, können wir möglicherweise nicht alle Anfragen zur Analyse beantworten.</span><span class="sxs-lookup"><span data-stu-id="a7f60-109">Because of the high volume of submissions that we receive, we may not be able to answer all requests for analysis.</span></span>

## <a name="submit-false-negatives-to-microsoft"></a><span data-ttu-id="a7f60-110">Senden von falschen negativen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="a7f60-110">Submit false negatives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="a7f60-111">Anstatt die folgenden Verfahren zum Melden von falsch negativen Daten zu verwenden, können Benutzer in Outlook und Outlook im Internet (früher als Outlook Web App bezeichnet) das Add-in "Berichtsnachricht" für Microsoft Outlook verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7f60-111">Instead of using the following procedures to report false negatives, users in Outlook and Outlook on the web (formerly known as Outlook Web App) can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="a7f60-112">Informationen zum Installieren und verwenden dieses Tools finden Sie unter [enable the Report Message Add-in](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="a7f60-112">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="a7f60-113">Wenn Sie eine Nachricht erhalten, die durch die Spamfilterung geleitet wurde, die als Spam oder Phishing identifiziert werden sollte, können Sie die Nachricht nach Bedarf an die Microsoft-Spam Analyse-und Microsoft-Phishing-Analyseteams senden.</span><span class="sxs-lookup"><span data-stu-id="a7f60-113">If you receive a message that passed through spam filtering that should have been identified as spam or phishing, you can submit the message to the Microsoft Spam Analysis and Microsoft Phishing Analysis teams as appropriate.</span></span> <span data-ttu-id="a7f60-114">Die Analysten überprüfen die Nachricht und fügen Sie den Dienst weiten Filtern hinzu, wenn Sie die Klassifizierungskriterien erfüllen.</span><span class="sxs-lookup"><span data-stu-id="a7f60-114">The analysts will review the message and add it to the service-wide filters if it meets the classification criteria.</span></span>

1. <span data-ttu-id="a7f60-115">Erstellen Sie eine neue, leere e-Mail-Nachricht mit einem der folgenden Empfänger:</span><span class="sxs-lookup"><span data-stu-id="a7f60-115">Create a new, blank email message with the one of the following recipients:</span></span>

   - <span data-ttu-id="a7f60-116">**Junk**:`junk@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="a7f60-116">**Junk**: `junk@office365.microsoft.com`</span></span>

   - <span data-ttu-id="a7f60-117">**Phishing**:`phish@office365.microsoft.com`</span><span class="sxs-lookup"><span data-stu-id="a7f60-117">**Phishing**: `phish@office365.microsoft.com`</span></span>

2. <span data-ttu-id="a7f60-118">Ziehen Sie die Junk-oder Phishing-Nachricht per Drag & Drop in die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a7f60-118">Drag and drop the junk or phishing message into the new message.</span></span> <span data-ttu-id="a7f60-119">Dadurch wird die Junk-oder Phishing-Nachricht als Anlage in der neuen Nachricht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a7f60-119">This will save the junk or phishing message as an attachment in the new message.</span></span> <span data-ttu-id="a7f60-120">Kopieren und Einfügen des Inhalts der Nachricht oder Weiterleiten der Nachricht (die ursprüngliche Nachricht ist erforderlich, damit die Nachrichtenkopfzeilen überprüft werden können).</span><span class="sxs-lookup"><span data-stu-id="a7f60-120">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="a7f60-121">Sie können mehrere Nachrichten in der neuen Nachricht anfügen.</span><span class="sxs-lookup"><span data-stu-id="a7f60-121">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="a7f60-122">Stellen Sie sicher, dass alle Nachrichten vom gleichen Typ sind: entweder Phishing-Scam-Nachrichten oder Junk-e-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a7f60-122">Make sure that all the messages are the same type: either phishing scam messages or junk email messages.</span></span></li><li><span data-ttu-id="a7f60-123">Lassen Sie den Nachrichtentext leer.</span><span class="sxs-lookup"><span data-stu-id="a7f60-123">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="a7f60-124">Verwenden Sie entweder msg (Outlook-Standardformat) oder eml (standardmäßige Outlook im Internetformat) für die angefügten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a7f60-124">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="a7f60-125">Wenn Sie fertig sind, klicken Sie auf **senden**.</span><span class="sxs-lookup"><span data-stu-id="a7f60-125">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="a7f60-126">Administratoren haben verschiedene Möglichkeiten, bestimmte Nachrichten, die fälschlicherweise als Spam identifiziert werden, zu blockieren.</span><span class="sxs-lookup"><span data-stu-id="a7f60-126">Admins have several different ways to block specific messages that are being misidentified as spam.</span></span> <span data-ttu-id="a7f60-127">Ausführliche Informationen finden Sie unter [Create blocked Sender Lists in Office 365](create-block-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a7f60-127">For details, see [Create blocked sender lists in Office 365](create-block-sender-lists-in-office-365.md).</span></span>

## <a name="submit-false-positives-to-microsoft"></a><span data-ttu-id="a7f60-128">Senden von falsch positiven Ergebnissen an Microsoft</span><span class="sxs-lookup"><span data-stu-id="a7f60-128">Submit false positives to Microsoft</span></span>

> [!TIP]
> <span data-ttu-id="a7f60-129">Anstatt die folgenden Verfahren zum Melden von falsch positiven Ergebnissen zu verwenden, können Benutzer in Outlook und Outlook im Internet das Add-in "Berichtsnachricht" für Microsoft Outlook verwenden.</span><span class="sxs-lookup"><span data-stu-id="a7f60-129">Instead of using the following procedures to report false positives, users in Outlook and Outlook on the web can use the Report Message Add-in for Microsoft Outlook.</span></span> <span data-ttu-id="a7f60-130">Informationen zum Installieren und verwenden dieses Tools finden Sie unter [enable the Report Message Add-in](enable-the-report-message-add-in.md).</span><span class="sxs-lookup"><span data-stu-id="a7f60-130">For information about how to install and use this tool, see [Enable the Report Message add-in](enable-the-report-message-add-in.md).</span></span>

<span data-ttu-id="a7f60-131">Wenn eine Nachricht fälschlicherweise als Spam identifiziert wurde, können Sie die Nachricht an das Microsoft-Spam Analyse Team übermitteln.</span><span class="sxs-lookup"><span data-stu-id="a7f60-131">If a message was incorrectly identified as spam, you can submit the message to the Microsoft Spam Analysis Team.</span></span> <span data-ttu-id="a7f60-132">Die Analysten bewerten die Nachricht, und (abhängig von den Ergebnissen der Analyse) können die Dienst weiten Filter so angepasst werden, dass die Nachricht durchlassen wird.</span><span class="sxs-lookup"><span data-stu-id="a7f60-132">The analysts will evaluate the message, and (depending on the results of the analysis) the service-wide filters can be adjusted to allow the message through.</span></span>

1. <span data-ttu-id="a7f60-133">Erstellen Sie eine neue, leere e- `not_junk@office365.microsoft.com` Mail-Nachricht mit als Empfänger:</span><span class="sxs-lookup"><span data-stu-id="a7f60-133">Create a new, blank email message with `not_junk@office365.microsoft.com` as the recipient:</span></span>

2. <span data-ttu-id="a7f60-134">Ziehen Sie die nicht identifizierte Nachricht per Drag & Drop in die neue Nachricht.</span><span class="sxs-lookup"><span data-stu-id="a7f60-134">Drag and drop the misidentified message into the new message.</span></span> <span data-ttu-id="a7f60-135">Dadurch wird die nicht identifizierte Nachricht als Anlage in der neuen Nachricht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="a7f60-135">This will save the misidentified message as an attachment in the new message.</span></span> <span data-ttu-id="a7f60-136">Kopieren und Einfügen des Inhalts der Nachricht oder Weiterleiten der Nachricht (die ursprüngliche Nachricht ist erforderlich, damit die Nachrichtenkopfzeilen überprüft werden können).</span><span class="sxs-lookup"><span data-stu-id="a7f60-136">Don't copy and paste the content of the message or forward the message (we need the original message so we can inspect the message headers).</span></span>

   > [!NOTE]
   > <ul><li><span data-ttu-id="a7f60-137">Sie können mehrere Nachrichten in der neuen Nachricht anfügen.</span><span class="sxs-lookup"><span data-stu-id="a7f60-137">You can attach multiple messages in the new message.</span></span> <span data-ttu-id="a7f60-138">Stellen Sie sicher, dass alle Nachrichten vom gleichen Typ sind: entweder Phishing-Nachrichten oder Junk-e-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a7f60-138">Make sure that all the messages are the same type: either phishing messages or junk email messages.</span></span></li><li><span data-ttu-id="a7f60-139">Lassen Sie den Nachrichtentext leer.</span><span class="sxs-lookup"><span data-stu-id="a7f60-139">Leave the body of the new message empty.</span></span></li><li><span data-ttu-id="a7f60-140">Verwenden Sie entweder msg (Outlook-Standardformat) oder eml (standardmäßige Outlook im Internetformat) für die angefügten Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="a7f60-140">Use either .msg (default Outlook format) or .eml (default Outlook on the Web format) formats for the attached messages.</span></span></li></ul>

3. <span data-ttu-id="a7f60-141">Wenn Sie fertig sind, klicken Sie auf **senden**.</span><span class="sxs-lookup"><span data-stu-id="a7f60-141">When you're finished, click **Send**.</span></span>

> [!TIP]
> <span data-ttu-id="a7f60-142">Administratoren haben verschiedene Möglichkeiten, um zu ermöglichen, dass bestimmte Nachrichten die Spamfilterung überspringen.</span><span class="sxs-lookup"><span data-stu-id="a7f60-142">Admins have several different ways to allow specific messages to skip spam filtering.</span></span> <span data-ttu-id="a7f60-143">Ausführliche Informationen finden Sie unter [Create Safe Sender Lists in Office 365](create-safe-sender-lists-in-office-365.md).</span><span class="sxs-lookup"><span data-stu-id="a7f60-143">For details, see [Create safe sender lists in Office 365](create-safe-sender-lists-in-office-365.md).</span></span>

## <a name="create-a-mail-flow-rule-to-receive-copies-of-messages-that-are-reported-to-microsoft"></a><span data-ttu-id="a7f60-144">Erstellen einer e-Mail-Fluss Regel zum Empfangen von Kopien von Nachrichten, die an Microsoft gemeldet werden</span><span class="sxs-lookup"><span data-stu-id="a7f60-144">Create a mail flow rule to receive copies of messages that are reported to Microsoft</span></span>

<span data-ttu-id="a7f60-145">Sie können eine e-Mail-Fluss Regel (auch als Transportregel bezeichnet) erstellen, die nach e-Mail-Nachrichten sucht, die an Microsoft mithilfe der in diesem Thema beschriebenen Methoden gemeldet werden, und Sie können Bcc-Empfänger so konfigurieren, dass Kopien dieser gemeldeten Nachrichten empfangen werden.</span><span class="sxs-lookup"><span data-stu-id="a7f60-145">You can create a mail flow rule (also known as a transport rule) that looks for email messages that are reported to Microsoft by using the methods described in this topic, and you can configure Bcc recipients to receive copies of these reported messages.</span></span>

<span data-ttu-id="a7f60-146">Sie können die Nachrichtenfluss Regel in der Exchange-Verwaltungskonsole (EAC) und PowerShell (Exchange Online PowerShell für Microsoft 365-Kunden erstellen; Exchange Online Protection PowerShell für eigenständige EoP-Kunden).</span><span class="sxs-lookup"><span data-stu-id="a7f60-146">You can create the mail flow rule in the Exchange admin center (EAC) and PowerShell (Exchange Online PowerShell for Microsoft 365 customers; Exchange Online Protection PowerShell for standalone EOP customers).</span></span>

### <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="a7f60-147">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="a7f60-147">What do you need to know before you begin?</span></span>

- <span data-ttu-id="a7f60-148">Sie müssen Berechtigungen in Exchange Online zugewiesen werden, bevor Sie diese Verfahren ausführen können.</span><span class="sxs-lookup"><span data-stu-id="a7f60-148">You need to be assigned permissions in Exchange Online before you can do these procedures.</span></span> <span data-ttu-id="a7f60-149">Insbesondere müssen Sie die Rolle " **Transport Rules** " erhalten, die standardmäßig der Rollen " **Organisationsverwaltung**", " **Richtlinientreue Verwaltung**" und " **Datensatzverwaltung** " zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="a7f60-149">Specifically, you need to be assigned the **Transport Rules** role, which is assigned to the **Organization Management**, **Compliance Management**, and **Records Management** roles by default.</span></span> <span data-ttu-id="a7f60-150">Weitere Informationen finden Sie unter [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span><span class="sxs-lookup"><span data-stu-id="a7f60-150">For more information, see [Manage role groups in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).</span></span>

- <span data-ttu-id="a7f60-151">Informationen zum Öffnen des EAC in Exchange Online finden Sie unter [Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span><span class="sxs-lookup"><span data-stu-id="a7f60-151">To open the EAC in Exchange Online, see [Exchange admin center in Exchange Online](https://docs.microsoft.com/Exchange/exchange-admin-center).</span></span>

- <span data-ttu-id="a7f60-152">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="a7f60-152">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="a7f60-153">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="a7f60-153">To connect to standalone Exchange Online Protection PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="a7f60-154">Weitere Informationen zu Nachrichtenfluss Regeln in Exchange Online und eigenständigen EoP finden Sie in den folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="a7f60-154">For more information about mail flow rules in Exchange Online and standalone EOP, see the following topics:</span></span>

  - [<span data-ttu-id="a7f60-155">Nachrichtenflussregeln (Transportregeln) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a7f60-155">Mail flow rules (transport rules) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)

  - [<span data-ttu-id="a7f60-156">Nachrichtenflussregel-Bedingungen und -Ausnahmen (Prädikate) in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a7f60-156">Mail flow rule conditions and exceptions (predicates) in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/conditions-and-exceptions)

  - [<span data-ttu-id="a7f60-157">Aktionen für Nachrichtenflussregeln in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="a7f60-157">Mail flow rule actions in Exchange Online</span></span>](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

### <a name="use-the-eac-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="a7f60-158">Erstellen einer e-Mail-Fluss Regel zum Empfangen von Kopien gemeldeter Nachrichten mithilfe der Exchange-Verwaltungskonsole</span><span class="sxs-lookup"><span data-stu-id="a7f60-158">Use the EAC to create a mail flow rule to receive copies of reported messages</span></span>

1. <span data-ttu-id="a7f60-159">Navigieren Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln**.</span><span class="sxs-lookup"><span data-stu-id="a7f60-159">In the EAC, go to **Mail flow** \> **Rules**.</span></span>

2. <span data-ttu-id="a7f60-160">Klicken Sie auf Add](../../media/ITPro-EAC-AddIcon.png) -Symbol **Hinzufügen** ![, und wählen Sie dann **neue Regel erstellen**aus.</span><span class="sxs-lookup"><span data-stu-id="a7f60-160">Click **Add** ![Add icon](../../media/ITPro-EAC-AddIcon.png) and then select **Create a new rule**.</span></span>

3. <span data-ttu-id="a7f60-161">Konfigurieren Sie auf der daraufhin geöffneten Seite **Neue Regel** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="a7f60-161">In the **New rule** page that opens, configure the following settings:</span></span>

   - <span data-ttu-id="a7f60-162">**Name**: Geben Sie einen eindeutigen, beschreibenden Namen für die Regel ein.</span><span class="sxs-lookup"><span data-stu-id="a7f60-162">**Name**: Enter a unique, descriptive name for the rule.</span></span> <span data-ttu-id="a7f60-163">Beispielsweise Bcc-Nachrichten, die an Microsoft gemeldet wurden.</span><span class="sxs-lookup"><span data-stu-id="a7f60-163">For example, Bcc Messages Reported to Microsoft.</span></span>

   - <span data-ttu-id="a7f60-164">Klicken Sie auf **Weitere Optionen**.</span><span class="sxs-lookup"><span data-stu-id="a7f60-164">Click **More Options**.</span></span>

   - <span data-ttu-id="a7f60-165">**Diese Regel anwenden, wenn**: Wählen Sie **die Empfänger** \> **Adresse enthält eines dieser Wörter**aus: Geben Sie im angezeigten Dialogfeld **Wörter oder Ausdrücke angeben** einen der folgenden Werte ein, klicken Sie auf](../../media/ITPro-EAC-AddIcon.png)Add-Symbol **Hinzufügen** ![, und wiederholen Sie diese Schritte, bis Sie alle Werte eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="a7f60-165">**Apply this rule if**: Select **The recipient** \> **address includes any of these words**: In the **Specify words or phrases** dialog that appears, enter one of the following values, click **Add** ![Add Icon](../../media/ITPro-EAC-AddIcon.png), and repeat until you've entered all the values.</span></span>

     - `junk@office365.microsoft.com`
     - `abuse@messaging.microsoft.com`
     - `phish@office365.microsoft.com`
     - `false_positive@messaging.microsoft.com`

     <span data-ttu-id="a7f60-166">Um einen Eintrag zu bearbeiten, wählen Sie ihn **Edit** ![aus, und](../../media/ITPro-EAC-EditIcon.png)klicken Sie auf Bearbeitungssymbol bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="a7f60-166">To edit an entry, select it and click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png).</span></span> <span data-ttu-id="a7f60-167">Um einen Eintrag zu entfernen, wählen Sie ihn **Remove** ![aus, und](../../media/ITPro-EAC-DeleteIcon.png)klicken Sie auf entfernen-Symbol entfernen.</span><span class="sxs-lookup"><span data-stu-id="a7f60-167">To remove an entry, select it and click **Remove** ![Remove icon](../../media/ITPro-EAC-DeleteIcon.png).</span></span>

     <span data-ttu-id="a7f60-168">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7f60-168">When you're finished, click **OK**.</span></span>

   - <span data-ttu-id="a7f60-169">**Gehen Sie wie folgt**vor: Wählen Sie Empfänger \> **zum Feld Bcc** **Hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="a7f60-169">**Do the following**: Select **Add recipients** \> **to the Bcc box**.</span></span> <span data-ttu-id="a7f60-170">Suchen Sie im angezeigten Dialogfeld die Empfänger, die Sie hinzufügen möchten, und wählen Sie Sie aus.</span><span class="sxs-lookup"><span data-stu-id="a7f60-170">In the dialog that appears, find and select the recipients that you want to add.</span></span> <span data-ttu-id="a7f60-171">Klicken Sie nach Abschluss des Vorgangs auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="a7f60-171">When you're finished, click **OK**.</span></span>

4. <span data-ttu-id="a7f60-172">Sie können eine weitere Auswahl treffen, um die Regel zu überwachen, die Regel zu testen, die Regel während eines bestimmten Zeitraums zu aktivieren und andere Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a7f60-172">You can make additional selections to audit the rule, test the rule, activate the rule during a specific time period, and other settings.</span></span> <span data-ttu-id="a7f60-173">Es wird empfohlen, die Regel zu testen, bevor Sie Sie erzwingen.</span><span class="sxs-lookup"><span data-stu-id="a7f60-173">We recommend testing the rule before you enforce it.</span></span>

5. <span data-ttu-id="a7f60-174">Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="a7f60-174">When you're finished, click **Save**.</span></span>

### <a name="use-powershell-to-create-a-mail-flow-rule-to-receive-copies-of-reported-messages"></a><span data-ttu-id="a7f60-175">Verwenden von PowerShell zum Erstellen einer e-Mail-Fluss Regel zum Empfangen von Kopien gemeldeter Nachrichten</span><span class="sxs-lookup"><span data-stu-id="a7f60-175">Use PowerShell to create a mail flow rule to receive copies of reported messages</span></span>

<span data-ttu-id="a7f60-176">In diesem Beispiel wird eine neue e-Mail-Fluss Regel namens Bcc-Nachrichten an Microsoft erstellt, die nach e-Mail-Nachrichten sucht, die mithilfe der in diesem Thema beschriebenen Methoden an Microsoft gemeldet werden, und fügt die Benutzer Laura@contoso.com und Julia@contoso.com als Bcc-Empfänger hinzu.</span><span class="sxs-lookup"><span data-stu-id="a7f60-176">This example creates a new mail flow rule named Bcc Messages Reported to Microsoft that looks for email messages that are reported to Microsoft by using the methods described in this topic, and adds the users laura@contoso.com and julia@contoso.com as Bcc recipients.</span></span>

```powershell
New-TransportRule -Name "Bcc Messages Reported to Microsoft" -RecipientAddressContainsWords "junk@office365.microsoft.com","abuse@messaging.microsoft.com","phish@office365.microsoft.com","false_positive@messaging.microsoft.com" -BlindCopyTo "laura@contoso.com","julia@contoso.com".
```

<span data-ttu-id="a7f60-177">Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span><span class="sxs-lookup"><span data-stu-id="a7f60-177">For detailed syntax and parameter information, see [New-TransportRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-transportrule).</span></span>

### <a name="how-do-you-know-this-worked"></a><span data-ttu-id="a7f60-178">Woher wissen Sie, dass dieses Verfahren erfolgreich war?</span><span class="sxs-lookup"><span data-stu-id="a7f60-178">How do you know this worked?</span></span>

<span data-ttu-id="a7f60-179">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie eine Nachrichtenfluss Regel für den Empfang von Kopien gemeldeter Nachrichten konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="a7f60-179">To verify that you've configured a mail flow rules to receive copies of reported messages, do any of the following steps:</span></span>

- <span data-ttu-id="a7f60-180">Wechseln Sie in der Exchange-Verwaltungskonsole zu **Nachrichtenfluss** \> **Regeln** \> \> wählen Sie die Regel](../../media/ITPro-EAC-EditIcon.png)klicken Sie auf Bearbeitungssymbol **Bearbeiten** ![, und überprüfen Sie die Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="a7f60-180">In the EAC, go to **Mail flow** \> **Rules** \> select the rule \> click **Edit** ![Edit icon](../../media/ITPro-EAC-EditIcon.png), and verify the settings.</span></span>

- <span data-ttu-id="a7f60-181">Führen Sie in PowerShell den folgenden Befehl aus, um die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="a7f60-181">In PowerShell, run the following command to verify the settings:</span></span>

  ```powershell
  Get-TransportRule -Identity "Bcc Messages Reported to Microsoft" | Format-List
  ```

- <span data-ttu-id="a7f60-182">Senden Sie eine Testnachricht an eine der Berichts-e-Mail-Adressen, und überprüfen Sie die Ergebnisse.</span><span class="sxs-lookup"><span data-stu-id="a7f60-182">Send a test messages to one of the reporting email addresses and verify the results.</span></span>
