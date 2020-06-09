---
title: Konfigurieren der Spoofintelligenz
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können Informationen zu Spoof Intelligence in Exchange Online Protection (EoP) erhalten, in der Sie bestimmte gefälschte Absender zulassen oder blockieren können.
ms.openlocfilehash: fe1e8f8a2e9f0cc792dc802ea5c7362af00687ae
ms.sourcegitcommit: 73b2426001dc5a3f4b857366ef51e877db549098
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/09/2020
ms.locfileid: "44613240"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="d3fe5-103">Konfigurieren von Spoof Intelligence in EoP</span><span class="sxs-lookup"><span data-stu-id="d3fe5-103">Configure spoof intelligence in EOP</span></span>

<span data-ttu-id="d3fe5-104">In Microsoft 365-Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächer werden eingehende e-Mail-Nachrichten automatisch ab Oktober 2018 vor Spoofing durch EoP geschützt.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-104">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="d3fe5-105">EoP verwendet Spoof Intelligence als Teil der gesamten Verteidigung ihrer Organisation gegen Phishing.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-105">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="d3fe5-106">Weitere Informationen finden Sie unter [Anti-Spoofing-Schutz in EoP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-106">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="d3fe5-107">Wenn ein Absender eine e-Mail-Adresse spooft, scheinen Sie ein Benutzer in einer ihrer Organisationsdomänen oder ein Benutzer in einer externen Domäne zu sein, der e-Mails an Ihre Organisation sendet.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-107">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="d3fe5-108">Angreifer, die Absender zum Senden von Spam-oder Phishing-e-Mails Spoofing, müssen blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-108">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="d3fe5-109">Es gibt jedoch Szenarien, in denen legitime Absender Spoofing durchsetzen.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-109">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="d3fe5-110">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-110">For example:</span></span>

- <span data-ttu-id="d3fe5-111">Legitime Szenarien für Spoofing interner Domänen:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-111">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="d3fe5-112">Absender von Drittanbietern verwenden Ihre Domäne, um Massen-e-Mails an Ihre eigenen Mitarbeiter für Unternehmensumfragen zu senden.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-112">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>

  - <span data-ttu-id="d3fe5-113">Ein externes Unternehmen generiert und sendet Werbungs-oder Produktaktualisierungen in Ihrem Auftrag.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-113">An external company generates and sends advertising or product updates on your behalf.</span></span>

  - <span data-ttu-id="d3fe5-114">Ein Assistent muss regelmäßig e-Mails für eine andere Person in Ihrer Organisation senden.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-114">An assistant regularly needs to send email for another person within your organization.</span></span>

  - <span data-ttu-id="d3fe5-115">Eine interne Anwendung sendet e-Mail-Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-115">An internal application sends email notifications.</span></span>

- <span data-ttu-id="d3fe5-116">Legitime Szenarien für Spoofing externer Domänen:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-116">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="d3fe5-117">Der Absender befindet sich auf einer Mailingliste (wird auch als Diskussionsliste bezeichnet), und die Mailingliste leitet e-Mails vom ursprünglichen Absender an alle Teilnehmer der Mailingliste weiter.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-117">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>

  - <span data-ttu-id="d3fe5-118">Ein externes Unternehmen sendet e-Mails im Auftrag eines anderen Unternehmens (beispielsweiseeines automatisierten Berichts oder eines Software-as-a-Service-Unternehmens).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-118">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="d3fe5-119">Spoof Intelligence und speziell die standardmäßige Spoof Intelligence-Richtlinie gewährleisten, dass die gefälschten e-Mail-Nachrichten, die von legitimen Absendern gesendet werden, nicht in EoP-Spamfiltern oder externen e-Mail-Systemen erfasst werden, während Ihre Benutzer vor Spam-oder Phishing-Angriffen geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-119">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="d3fe5-120">Sie können Spoof Intelligence im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer) verwalten.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-120">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="d3fe5-121">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="d3fe5-121">What do you need to know before you begin?</span></span>

- <span data-ttu-id="d3fe5-122">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-122">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="d3fe5-123">Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-123">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="d3fe5-124">Wenn Sie direkt zur Seite **Anti-Phishing** wechseln möchten, verwenden Sie <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="d3fe5-124">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="d3fe5-125">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-125">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="d3fe5-126">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-126">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="d3fe5-127">Bevor Sie diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-127">You need to be assigned permissions before you can perform these procedures.</span></span> <span data-ttu-id="d3fe5-128">Um die Spoof Intelligence-Richtlinie zu ändern oder Spoof Intelligence zu aktivieren oder zu deaktivieren, müssen Sie Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-128">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="d3fe5-129">Für den schreibgeschützten Zugriff auf die Spoof Intelligence-Richtlinie müssen Sie Mitglied der Rollengruppe **Sicherheits Leser** sein.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-129">For read-only access to the spoof intelligence policy, you need to be a member of the **Security Reader** role group.</span></span> <span data-ttu-id="d3fe5-130">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-130">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="d3fe5-131">Unsere empfohlenen Einstellungen für Spoof Intelligence finden Sie unter [EoP default Anti-Phishing Policy Settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-131">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="d3fe5-132">Verwenden des Security & Compliance Center zum Verwalten von gefälschten Absendern</span><span class="sxs-lookup"><span data-stu-id="d3fe5-132">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="d3fe5-133">Wenn Sie ein Microsoft 365 Enterprise E5-Abonnement haben oder ein Office 365 Advanced Threat Protection (Office 365 ATP)-Add-on separat erworben haben, können Sie auch Absender verwalten, die Ihre Domäne durch [Spoofing Intelligence Insight](walkthrough-spoof-intelligence-insight.md)manipulieren.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-133">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased an Office 365 Advanced Threat Protection (Office 365 ATP) add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="d3fe5-134">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-134">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="d3fe5-135">Klicken Sie auf der Seite **Anti-Spam-Einstellungen** auf ![ Symbol erweitern ](../../media/scc-expand-icon.png) , um **Spoof Intelligence Policy**zu erweitern.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-135">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Auswählen der Spoof Intelligence-Richtlinie](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="d3fe5-137">Wählen Sie eine der folgenden Optionen aus:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-137">Make one of the following selections:</span></span>

   - <span data-ttu-id="d3fe5-138">**Überprüfen neuer Absender**</span><span class="sxs-lookup"><span data-stu-id="d3fe5-138">**Review new senders**</span></span>
   - <span data-ttu-id="d3fe5-139">**Mir bereits überprüfte Absender anzeigen**</span><span class="sxs-lookup"><span data-stu-id="d3fe5-139">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="d3fe5-140">Wählen Sie im Feld entscheiden Sie, ob diese Absender das geöffnete Flyout des **Benutzers spoofen dürfen** , eine der folgenden Registerkarten aus:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-140">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="d3fe5-141">**Ihre Domänen**: Absender Spoofing-Benutzer in ihren internen Domänen.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-141">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="d3fe5-142">**Externe Domänen**: Absender Spoofing-Benutzer in externen Domänen.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-142">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="d3fe5-143">Klicken Sie ![ ](../../media/scc-expand-icon.png) in der Spalte **zulässig als spoof?** auf Symbol erweitern.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-143">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="d3fe5-144">Wählen Sie **Ja** aus, um den gefälschten Absender zuzulassen, oder wählen Sie **Nein** aus, um die Nachricht als gefälscht zu markieren.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-144">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="d3fe5-145">Die Aktion wird von der standardmäßigen Anti-Phishing-Richtlinie oder von benutzerdefinierten ATP-Richtlinien für Anti-Phishing gesteuert (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-145">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="d3fe5-146">Weitere Informationen finden Sie unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-146">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Screenshot mit dem Flyout für gefälschte Absender und ob der Absender Spoofing zulässig ist](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="d3fe5-148">Die Spalten und Werte, die angezeigt werden, werden in der folgenden Liste erläutert:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-148">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="d3fe5-149">**Spoofed User**: das Benutzerkonto, das gefälscht wird.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-149">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="d3fe5-150">Dies ist der Absender der Nachricht in der von-Adresse (auch als `5322.From` Adresse bezeichnet), die in e-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-150">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="d3fe5-151">Die Gültigkeit dieser Adresse wird von SPF nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-151">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="d3fe5-152">Auf der Registerkarte **Ihre Domänen** enthält der Wert eine einzelne e-Mail-Adresse, oder wenn der Quell-e-Mail-Server mehrere Benutzerkonten fälscht, enthält er **mehr als einen**.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-152">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="d3fe5-153">Auf der Registerkarte **externe Domänen** enthält der Wert die Domäne des gefälschten Benutzers und nicht die vollständige e-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-153">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="d3fe5-154">**Sendeinfrastruktur**: die Domäne, die in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-e-Mail-Servers gefunden wurde, oder die IP-Adresse, wenn die Quelle keinen PTR-Eintrag aufweist.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-154">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address, or the IP address if the source has no PTR record.</span></span>

     <span data-ttu-id="d3fe5-155">Weitere Informationen zu Nachrichtenquellen und Nachrichten Absendern finden Sie unter [Übersicht über Standards für e-Mail-Nachrichten](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-155">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="d3fe5-156">Anzahl von **Nachrichten**: die Anzahl der Nachrichten von der sendenden Infrastruktur an Ihre Organisation, die die angegebenen gefälschten Absender oder Absender innerhalb der letzten 30 Tage enthalten.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-156">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="d3fe5-157">**Anzahl von Benutzer Reklamationen**: Beschwerden, die von Ihren Benutzern in den letzten 30 Tagen gegen diesen Absender eingereicht wurden.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-157">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="d3fe5-158">Beschwerden sind in der Regel in Form von Junk-Übermittlungen an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-158">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="d3fe5-159">**Authentifizierungsergebnis**: einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-159">**Authentication result**: One of the following values:</span></span>

      - <span data-ttu-id="d3fe5-160">**Übergeben**: der Absender hat Absender-e-Mail-Authentifizierungsprüfungen (SPF oder DKIM) übergeben.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-160">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="d3fe5-161">**Fehler**: Fehler beim Absender Authentifizierungsüberprüfung bei EoP.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-161">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="d3fe5-162">**Unbekannt**: das Ergebnis dieser Prüfungen ist nicht bekannt.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-162">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="d3fe5-163">**Entscheidung festgelegt von**: zeigt an, wer ermittelt hat, ob die sendende Infrastruktur den Benutzer Spoofing erlaubt:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-163">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>

       - <span data-ttu-id="d3fe5-164">**Spoof Intelligence Policy** (automatisch)</span><span class="sxs-lookup"><span data-stu-id="d3fe5-164">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="d3fe5-165">**Admin** (manuell)</span><span class="sxs-lookup"><span data-stu-id="d3fe5-165">**Admin** (manual)</span></span>

   - <span data-ttu-id="d3fe5-166">**Zuletzt gesehen**: das letzte Datum, an dem eine Nachricht von der sendenden Infrastruktur empfangen wurde, die den gefälschten Benutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-166">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="d3fe5-167">**Spoofing erlaubt?**: die Werte, die Sie hier sehen, sind:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-167">**Allowed to spoof?**: The values that you see here are:</span></span>

     - <span data-ttu-id="d3fe5-168">**Yes**: Nachrichten aus der Kombination von Spoofing-Benutzer und sendender Infrastruktur sind zulässig und werden nicht als gefälschte e-Mails behandelt.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-168">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>

     - <span data-ttu-id="d3fe5-169">**No**: Nachrichten aus der Kombination von Spoofing-Benutzer und-Sendeinfrastruktur werden als gefälscht gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-169">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="d3fe5-170">Die Aktion wird von der standardmäßigen Anti-Phishing-Richtlinie oder von benutzerdefinierten ATP-Richtlinien für Anti-Phishing gesteuert (der Standardwert ist **"Nachricht in Junk-e-Mail-Ordner"**).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-170">The action is controlled by the default anti-phishing policy or custom ATP anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="d3fe5-171">Weitere Informationen finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-171">See the next section for more information.</span></span>

     - <span data-ttu-id="d3fe5-172">**Einige Benutzer** (nur die Registerkarte "**Domains** "): eine sendende Infrastruktur Spoofing mehrere Benutzer, bei denen einige gefälschte Benutzer zulässig sind und andere nicht.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-172">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="d3fe5-173">Verwenden Sie die **detaillierte** Registerkarte, um die spezifischen Adressen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-173">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="d3fe5-174">Klicken Sie unten auf der Seite auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-174">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="d3fe5-175">Verwenden von PowerShell zum Verwalten von gefälschten Absendern</span><span class="sxs-lookup"><span data-stu-id="d3fe5-175">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="d3fe5-176">Verwenden Sie die folgende Syntax, um zugelassene und blockierte Absender in Spoof Intelligence anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-176">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="d3fe5-177">In diesem Beispiel werden detaillierte Informationen zu allen Absendern zurückgegeben, die Benutzer in ihren Domänen spoofen dürfen.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-177">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="d3fe5-178">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-178">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="d3fe5-179">Führen Sie die folgenden Schritte aus, um zugelassene und blockierte Absender in Spoof Intelligence zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-179">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="d3fe5-180">Erfassen Sie die aktuelle Liste der erkannten gefälschten Absender, indem Sie die Ausgabe des Cmdlets **Get-PhishFilterPolicy** in eine CSV-Datei schreiben:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-180">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="d3fe5-181">Bearbeiten Sie die CSV-Datei, um die Werte **SpoofedUser** (e-Mail-Adresse) und **AllowedToSpoof** (ja oder Nein) hinzuzufügen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-181">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="d3fe5-182">Speichern Sie die Datei, lesen Sie die Datei, und speichern Sie den Inhalt als Variable mit dem Namen `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="d3fe5-182">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="d3fe5-183">Verwenden Sie die- `$UpdateSpoofedSenders` Variable, um die Spoof Intelligence-Richtlinie zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-183">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="d3fe5-184">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Sets-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-184">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="d3fe5-185">Konfigurieren von Spoof Intelligence mithilfe des Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="d3fe5-185">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="d3fe5-186">Die Konfigurationsoptionen für Spoof Intelligence werden unter [Spoof Settings in Anti-Phishing Policies](set-up-anti-phishing-policies.md#spoof-settings)beschrieben.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-186">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="d3fe5-187">Sie können Spoof Intelligence-Einstellungen in der standardmäßigen Anti-Phishing-Richtlinie und auch in benutzerdefinierten Richtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-187">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="d3fe5-188">Anweisungen basierend auf Ihrem Abonnement finden Sie in einem der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-188">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="d3fe5-189">[Konfigurieren von Anti-Phishing-Richtlinien in EoP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-189">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="d3fe5-190">[Konfigurieren von Richtlinien für die ATP-Anti-Phishing in Microsoft 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-190">[Configure ATP anti-phishing policies in Microsoft 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="d3fe5-191">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="d3fe5-191">How do you know these procedures worked?</span></span>

<span data-ttu-id="d3fe5-192">Führen Sie einen der folgenden Schritte aus, um zu überprüfen, ob Sie Spoof Intelligence mit Absendern konfiguriert haben, die zulässig sind und nicht gefälscht werden dürfen und dass Sie die Spoof Intelligence-Einstellungen konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-192">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="d3fe5-193">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Spam** \> Erweitern Sie **Spoof Intelligence Policy** \> Select **Show Me Senders I bereits überprüft** \> Wählen Sie die Registerkarte **Domänen** oder **externe Domänen** aus, und überprüfen Sie die **Berechtigung zum Spoofing?** Wert für den Absender.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-193">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="d3fe5-194">Führen Sie in PowerShell die folgenden Befehle aus, um die Absender anzuzeigen, die zulässig sind und nicht Spoofing zulässig sind:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-194">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="d3fe5-195">Führen Sie in PowerShell den folgenden Befehl aus, um die Liste aller gefälschten Absender in eine CSV-Datei zu exportieren:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-195">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="d3fe5-196">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Policy** \> **Anti-Phishing** oder **ATP Anti-Phishing**, und führen Sie einen der folgenden Schritte aus:  </span><span class="sxs-lookup"><span data-stu-id="d3fe5-196">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="d3fe5-197">Wählen Sie eine Richtlinie aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-197">Select a policy from the list.</span></span> <span data-ttu-id="d3fe5-198">Überprüfen Sie im Flyout, das angezeigt wird, die Werte im **Spoof** -Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-198">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="d3fe5-199">Klicken Sie auf **Standardrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-199">Click **Default policy**.</span></span> <span data-ttu-id="d3fe5-200">Überprüfen Sie im Flyout, das angezeigt wird, die Werte im **Spoof** -Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-200">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="d3fe5-201">Ersetzen Sie in Exchange Online PowerShell \<Name\> durch Office365 AntiPhishing default oder den Namen einer benutzerdefinierten Richtlinie, und führen Sie den folgenden Befehl aus, um die Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-201">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="d3fe5-202">Andere Methoden zum Verwalten von Spoofing und Phishing</span><span class="sxs-lookup"><span data-stu-id="d3fe5-202">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="d3fe5-203">Sie sollten sich sorgfältig mit Spoofing und Phishing-Schutz bemühen.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-203">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="d3fe5-204">Im folgenden finden Sie ähnliche Möglichkeiten zum Überprüfen von Absendern, die Ihre Domäne Spoofing und dazu beitragen, dass Sie Ihre Organisation nicht schädigen:</span><span class="sxs-lookup"><span data-stu-id="d3fe5-204">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="d3fe5-205">Überprüfen Sie den **Spoof-e-Mail-Bericht**.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-205">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="d3fe5-206">Sie können diesen Bericht häufig verwenden, um gefälschte Absender anzuzeigen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-206">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="d3fe5-207">Weitere Informationen finden Sie unter [Spoof Detections Report](view-email-security-reports.md#spoof-detections-report).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-207">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="d3fe5-208">Überprüfen Sie die SPF-Konfiguration (Sender Policy Framework).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-208">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="d3fe5-209">Eine kurze Einführung in SPF und seine schnelle Konfiguration finden Sie unter [Einrichten von SPF in Microsoft 365 zur Verhinderung von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-209">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="d3fe5-210">Ausführlichere Informationen zur Verwendung von SPF durch Office 365 oder zur Problembehandlung oder zu nicht standardmäßigen Bereitstellungen, z. B. Hybridbereitstellungen, finden Sie unter [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-210">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="d3fe5-211">Überprüfen Sie Ihre DomainKeys Identified Mail (DKIM)-Konfiguration.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-211">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="d3fe5-212">Sie sollten zusätzlich zu SPF und DMARC DKIM verwenden, um zu verhindern, dass Angreifer Nachrichten senden können, die so aussehen, wie Sie von Ihrer Domäne stammen.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-212">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="d3fe5-213">Mit DKIM können Sie E-Mail-Nachrichten in der Kopfzeile der Nachricht eine digitale Signatur hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-213">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="d3fe5-214">Weitere Informationen finden Sie unter [Verwenden von DKIM zum Überprüfen von ausgehenden e-Mails, die von Ihrer benutzerdefinierten Domäne in Office 365 gesendet wurden](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-214">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="d3fe5-215">Überprüfen Sie die Konfiguration der domänenbasierten Nachrichtenauthentifizierung, Berichterstellung und Konformität (DMARC).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-215">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="d3fe5-216">Die Implementierung von DMARC zusammen mit SPF und DKIM bietet zusätzlichen Schutz vor Spoofing- und Phishing-E-Mails.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-216">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="d3fe5-217">DMARC unterstützt die E-Mail-Systeme der Empfänger bei der Behandlung von Nachrichten, die von Ihrer Domäne gesendet wurden, jedoch die SPF- oder DKIM-Prüfungen nicht bestanden haben.</span><span class="sxs-lookup"><span data-stu-id="d3fe5-217">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="d3fe5-218">Weitere Informationen finden Sie unter [Verwenden von DMARC zum Überprüfen von e-Mails in Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="d3fe5-218">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
