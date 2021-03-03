---
title: Konfigurieren der Spoofintelligenz
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren können sich über Spoof Intelligence in Exchange Online Protection (EOP) informieren, wo Sie bestimmte gefälschte Absender zulassen oder blockieren können.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 482978e93325344d897fcf907b026743fc393d47
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50406640"
---
# <a name="configure-spoof-intelligence-in-eop"></a><span data-ttu-id="2e621-103">Konfigurieren von Spoof Intelligence in EOP</span><span class="sxs-lookup"><span data-stu-id="2e621-103">Configure spoof intelligence in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="2e621-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="2e621-104">**Applies to**</span></span>
- [<span data-ttu-id="2e621-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2e621-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2e621-106">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="2e621-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="2e621-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2e621-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

<span data-ttu-id="2e621-108">In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden eingehende E-Mail-Nachrichten ab Oktober 2018 automatisch vor Spoofing durch EOP geschützt.</span><span class="sxs-lookup"><span data-stu-id="2e621-108">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="2e621-109">EOP verwendet Spoof Intelligence als Teil der allgemeinen Verteidigung Ihrer Organisation gegen Phishing.</span><span class="sxs-lookup"><span data-stu-id="2e621-109">EOP uses spoof intelligence as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="2e621-110">Weitere Informationen finden Sie unter Schutz vor [Spoofing in EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="2e621-110">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="2e621-111">Wenn ein Absender eine E-Mail-Adresse spooft, scheint er ein Benutzer in einer der Domänen Ihrer Organisation oder ein Benutzer in einer externen Domäne zu sein, die E-Mails an Ihre Organisation sendet.</span><span class="sxs-lookup"><span data-stu-id="2e621-111">When a sender spoofs an email address, they appear to be a user in one of your organization's domains, or a user in an external domain that sends email to your organization.</span></span> <span data-ttu-id="2e621-112">Angreifer, die Absender zum Senden von Spam- oder Phishing-E-Mails spoofen, müssen blockiert werden.</span><span class="sxs-lookup"><span data-stu-id="2e621-112">Attackers who spoof senders to send spam or phishing email need to be blocked.</span></span> <span data-ttu-id="2e621-113">Es gibt jedoch Szenarien, in denen legitime Absender Spoofing verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e621-113">But there are scenarios where legitimate senders are spoofing.</span></span> <span data-ttu-id="2e621-114">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="2e621-114">For example:</span></span>

- <span data-ttu-id="2e621-115">Legitime Szenarien für das Spoofing interner Domänen:</span><span class="sxs-lookup"><span data-stu-id="2e621-115">Legitimate scenarios for spoofing internal domains:</span></span>

  - <span data-ttu-id="2e621-116">Drittanbietersender verwenden Ihre Domäne, um Massen-E-Mails für Unternehmensumfragen an Ihre eigenen Mitarbeiter zu senden.</span><span class="sxs-lookup"><span data-stu-id="2e621-116">Third-party senders use your domain to send bulk mail to your own employees for company polls.</span></span>
  - <span data-ttu-id="2e621-117">Ein externes Unternehmen generiert und sendet Werbe- oder Produktupdates in Ihrem Auftrag.</span><span class="sxs-lookup"><span data-stu-id="2e621-117">An external company generates and sends advertising or product updates on your behalf.</span></span>
  - <span data-ttu-id="2e621-118">Ein Assistent muss regelmäßig E-Mails für eine andere Person in Ihrer Organisation senden.</span><span class="sxs-lookup"><span data-stu-id="2e621-118">An assistant regularly needs to send email for another person within your organization.</span></span>
  - <span data-ttu-id="2e621-119">Eine interne Anwendung sendet E-Mail-Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="2e621-119">An internal application sends email notifications.</span></span>

- <span data-ttu-id="2e621-120">Legitime Szenarien für das Spoofing externer Domänen:</span><span class="sxs-lookup"><span data-stu-id="2e621-120">Legitimate scenarios for spoofing external domains:</span></span>

  - <span data-ttu-id="2e621-121">Der Absender befindet sich in einer Mailingliste (auch als Diskussionsliste bezeichnet), und die Mailingliste leitet E-Mails vom ursprünglichen Absender an alle Teilnehmer in der Mailingliste weiter.</span><span class="sxs-lookup"><span data-stu-id="2e621-121">The sender is on a mailing list (also known as a discussion list), and the mailing list relays email from the original sender to all the participants on the mailing list.</span></span>
  - <span data-ttu-id="2e621-122">Ein externes Unternehmen sendet E-Mails im Auftrag eines anderen Unternehmens (z. B. einen automatisierten Bericht oder ein Software-as-a-Service-Unternehmen).</span><span class="sxs-lookup"><span data-stu-id="2e621-122">An external company sends email on behalf of another company (for example, an automated report or a software-as-a-service company).</span></span>

<span data-ttu-id="2e621-123">Spoof Intelligence, insbesondere die standardmäßige (und nur) Spoof Intelligence-Richtlinie, trägt dazu bei, sicherzustellen, dass die gefälschten E-Mails, die von legitimen Absendern gesendet werden, nicht in EOP-Spamfilter oder externe E-Mail-Systeme versenkt werden, während Ihre Benutzer vor Spam- oder Phishingangriffen geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="2e621-123">Spoof intelligence, and specifically the default (and only) spoof intelligence policy, helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters or external email systems, while protecting your users from spam or phishing attacks.</span></span>

<span data-ttu-id="2e621-124">Sie können Spoof Intelligence im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange &) verwalten.</span><span class="sxs-lookup"><span data-stu-id="2e621-124">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2e621-125">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="2e621-125">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2e621-126">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2e621-126">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span> <span data-ttu-id="2e621-127">Um direkt zur Seite **Antispameinstellungen** zu wechseln, verwenden Sie <https://protection.office.com/antispam>.</span><span class="sxs-lookup"><span data-stu-id="2e621-127">To go directly to the **Anti-spam settings** page, use <https://protection.office.com/antispam>.</span></span> <span data-ttu-id="2e621-128">Um direkt zur Seite **"Antiphishing" zu** wechseln, verwenden Sie <https://protection.office.com/antiphishing> .</span><span class="sxs-lookup"><span data-stu-id="2e621-128">To go directly to the **Anti-phishing** page, use <https://protection.office.com/antiphishing>.</span></span>

- <span data-ttu-id="2e621-129">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="2e621-129">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="2e621-130">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="2e621-130">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="2e621-131">Bevor Sie die Verfahren in diesem Artikel tun können, müssen Ihnen in **Exchange Online** die entsprechenden Berechtigungen zugewiesen werden:</span><span class="sxs-lookup"><span data-stu-id="2e621-131">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="2e621-132">Um die Spoof Intelligence-Richtlinie zu ändern oder Spoof Intelligence zu  aktivieren oder zu deaktivieren, müssen Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="2e621-132">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="2e621-133">Für den schreibgeschützten Zugriff auf die Spoof Intelligence-Richtlinie müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="2e621-133">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="2e621-134">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="2e621-134">For more information, see [Permissions in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="2e621-135">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="2e621-135">**Notes**:</span></span>

  - <span data-ttu-id="2e621-136">Durch hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft  365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen und Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="2e621-136">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="2e621-137">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="2e621-137">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="2e621-138">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="2e621-138">The **View-Only Organization Management** role group in [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="2e621-139">Unsere empfohlenen Einstellungen für spoof intelligence finden Sie unter [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="2e621-139">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a><span data-ttu-id="2e621-140">Verwenden des Security & Compliance Center zum Verwalten gefälschter Absender</span><span class="sxs-lookup"><span data-stu-id="2e621-140">Use the Security & Compliance Center to manage spoofed senders</span></span>

> [!NOTE]
> <span data-ttu-id="2e621-141">Wenn Sie über ein Microsoft 365 Enterprise E5-Abonnement verfügen oder ein Microsoft Defender for Office 365-Add-On separat erworben haben, können Sie auch Absender verwalten, die Ihre Domäne spoofen, über den [Spoof](walkthrough-spoof-intelligence-insight.md)Intelligence-Einblick.</span><span class="sxs-lookup"><span data-stu-id="2e621-141">If you have an Microsoft 365 Enterprise E5 subscription or have separately purchased a Microsoft Defender for Office 365 add-on, you can also manage senders who are spoofing your domain through the [Spoof Intelligence insight](walkthrough-spoof-intelligence-insight.md).</span></span>

1. <span data-ttu-id="2e621-142">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="2e621-142">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="2e621-143">Klicken Sie auf der Seite **Antispameinstellungen** auf ![ Symbol erweitern, ](../../media/scc-expand-icon.png) um die **Spoof Intelligence-Richtlinie zu erweitern.**</span><span class="sxs-lookup"><span data-stu-id="2e621-143">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Auswählen der Spoof Intelligence-Richtlinie](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="2e621-145">Treffen Sie eine der folgenden Auswahlen:</span><span class="sxs-lookup"><span data-stu-id="2e621-145">Make one of the following selections:</span></span>

   - <span data-ttu-id="2e621-146">**Überprüfen neuer Absender**</span><span class="sxs-lookup"><span data-stu-id="2e621-146">**Review new senders**</span></span>
   - <span data-ttu-id="2e621-147">**Absender anzeigen, die ich bereits überprüft habe**</span><span class="sxs-lookup"><span data-stu-id="2e621-147">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="2e621-148">Wählen Sie im angezeigten Flyout "Entscheiden, ob diese Absender ihre Benutzer-Flyouts **spoofen** dürfen" eine der folgenden Registerkarten aus:</span><span class="sxs-lookup"><span data-stu-id="2e621-148">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="2e621-149">**Ihre Domänen:** Absender, die Benutzer in Ihren internen Domänen spoofieren.</span><span class="sxs-lookup"><span data-stu-id="2e621-149">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="2e621-150">**Externe Domänen:** Absender, die Benutzer in externen Domänen spoofieren.</span><span class="sxs-lookup"><span data-stu-id="2e621-150">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="2e621-151">Klicken ![ Sie in der Spalte ](../../media/scc-expand-icon.png) **Spoofing?** auf Erweitern(Symbol).</span><span class="sxs-lookup"><span data-stu-id="2e621-151">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="2e621-152">Wählen **Sie Ja** aus, um den gefälschten Absender zu erlauben, oder wählen Sie **Nein** aus, um die Nachricht als spoofed zu markieren.</span><span class="sxs-lookup"><span data-stu-id="2e621-152">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="2e621-153">Die Aktion wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist **Move message to Junk Email folder**).</span><span class="sxs-lookup"><span data-stu-id="2e621-153">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="2e621-154">Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="2e621-154">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Screenshot des Flyouts von spoofierten Absendern und der Frage, ob der Absender spoofen darf](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="2e621-156">Die angezeigten Spalten und Werte werden in der folgenden Liste erläutert:</span><span class="sxs-lookup"><span data-stu-id="2e621-156">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="2e621-157">**Spoofed user:** Das Benutzerkonto, das gefälscht wird.</span><span class="sxs-lookup"><span data-stu-id="2e621-157">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="2e621-158">Dies ist der Absender der Nachricht in der Absenderadresse (auch als Adresse bezeichnet), die `5322.From` in E-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="2e621-158">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="2e621-159">Die Gültigkeit dieser Adresse wird von SPF nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="2e621-159">The validity of this address is not checked by SPF.</span></span>

     - <span data-ttu-id="2e621-160">Auf der Registerkarte Ihre **Domänen** enthält der Wert eine einzelne E-Mail-Adresse, oder wenn der Quell-E-Mail-Server mehrere Benutzerkonten spoofiert, enthält er **mehrere**.</span><span class="sxs-lookup"><span data-stu-id="2e621-160">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>

     - <span data-ttu-id="2e621-161">Auf der **Registerkarte Externe Domänen** enthält der Wert die Domäne des spoofierten Benutzers, nicht die vollständige E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="2e621-161">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="2e621-162">**Sendeinfrastruktur**: Die Domäne, die in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="2e621-162">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="2e621-163">Wenn die Quell-IP-Adresse keinen PTR-Eintrag enthält, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="2e621-163">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="2e621-164">Weitere Informationen zu Nachrichtenquellen und Nachrichtensendern finden Sie unter [Eine Übersicht über E-Mail-Nachrichtenstandards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span><span class="sxs-lookup"><span data-stu-id="2e621-164">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="2e621-165">**Anzahl der Nachrichten**: Die Anzahl der Nachrichten aus der sendenden Infrastruktur an Ihre Organisation, die den angegebenen gefälschten Absender oder Absender innerhalb der letzten 30 Tage enthalten.</span><span class="sxs-lookup"><span data-stu-id="2e621-165">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="2e621-166">**# der Benutzerbeschwerden**: Beschwerden, die von Ihren Benutzern gegen diesen Absender innerhalb der letzten 30 Tage eingereicht wurden.</span><span class="sxs-lookup"><span data-stu-id="2e621-166">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="2e621-167">Beschwerden werden in der Regel in Form von Junk-Übermittlungen an Microsoft eingereicht.</span><span class="sxs-lookup"><span data-stu-id="2e621-167">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="2e621-168">**Authentifizierungsergebnis**: Einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="2e621-168">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="2e621-169">**Übergeben:** Der Absender hat E-Mail-Authentifizierungsprüfungen (SPF oder DKIM) bestanden.</span><span class="sxs-lookup"><span data-stu-id="2e621-169">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="2e621-170">**Fehler:** Fehler beim EOP-Absenderauthentifizierungsüberprüfungen.</span><span class="sxs-lookup"><span data-stu-id="2e621-170">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="2e621-171">**Unbekannt:** Das Ergebnis dieser Prüfungen ist nicht bekannt.</span><span class="sxs-lookup"><span data-stu-id="2e621-171">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="2e621-172">**Entscheidungssatz von**: Zeigt an, wer ermittelt hat, ob die sendende Infrastruktur den Benutzer spoofen darf:</span><span class="sxs-lookup"><span data-stu-id="2e621-172">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="2e621-173">**Spoof Intelligence Policy** (automatisch)</span><span class="sxs-lookup"><span data-stu-id="2e621-173">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="2e621-174">**Administrator** (manuell)</span><span class="sxs-lookup"><span data-stu-id="2e621-174">**Admin** (manual)</span></span>

   - <span data-ttu-id="2e621-175">**Zuletzt gesehen:** Das letzte Datum, an dem eine Nachricht von der sendenden Infrastruktur empfangen wurde, die den spoofierten Benutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="2e621-175">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="2e621-176">**Darf ges spooft werden?**: Die hier angezeigten Werte sind:</span><span class="sxs-lookup"><span data-stu-id="2e621-176">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="2e621-177">**Ja:** Nachrichten aus der Kombination aus spoofierten Benutzern und sendender Infrastruktur sind zulässig und werden nicht als spoofierte E-Mails behandelt.</span><span class="sxs-lookup"><span data-stu-id="2e621-177">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="2e621-178">**Nein:** Nachrichten aus der Kombination aus spoofiertem Benutzer und sendender Infrastruktur werden als Spoofing gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="2e621-178">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="2e621-179">Die Aktion wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist **Move message to Junk Email folder**).</span><span class="sxs-lookup"><span data-stu-id="2e621-179">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="2e621-180">Weitere Informationen finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="2e621-180">See the next section for more information.</span></span>

     - <span data-ttu-id="2e621-181">**Einige Benutzer** (**Nur Registerkarte "Ihre** Domänen"): Eine sendende Infrastruktur fälscht mehrere Benutzer, wobei einige spoofierte Benutzer zulässig sind und andere nicht.</span><span class="sxs-lookup"><span data-stu-id="2e621-181">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="2e621-182">Verwenden Sie die **Registerkarte Detail,** um die spezifischen Adressen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="2e621-182">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="2e621-183">Klicken Sie unten auf der Seite auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="2e621-183">At the bottom of the page, click **Save**.</span></span>

## <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="2e621-184">Verwenden von PowerShell zum Verwalten gefälschter Absender</span><span class="sxs-lookup"><span data-stu-id="2e621-184">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="2e621-185">Verwenden Sie die folgende Syntax, um zugelassene und blockierte Absender in Spoof Intelligence zu sehen:</span><span class="sxs-lookup"><span data-stu-id="2e621-185">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="2e621-186">In diesem Beispiel werden detaillierte Informationen zu allen Absendern zurückgegeben, die Benutzer in Ihren Domänen spoofen dürfen.</span><span class="sxs-lookup"><span data-stu-id="2e621-186">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="2e621-187">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="2e621-187">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="2e621-188">Führen Sie die folgenden Schritte aus, um zugelassene und blockierte Absender in Spoof Intelligence zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="2e621-188">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="2e621-189">Erfassen Sie die aktuelle Liste der erkannten gefälschten Absender, indem Sie die Ausgabe des **Get-PhishFilterPolicy-Cmdlets** in eine CSV-Datei schreiben:</span><span class="sxs-lookup"><span data-stu-id="2e621-189">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="2e621-190">Bearbeiten Sie die CSV-Datei, um die **Werte SpoofedUser** (E-Mail-Adresse) und **AllowedToSpoof** (Ja oder Nein) hinzuzufügen oder zu ändern.</span><span class="sxs-lookup"><span data-stu-id="2e621-190">Edit the CSV file to add or modify the **SpoofedUser** (email address) and **AllowedToSpoof** (Yes or No) values.</span></span> <span data-ttu-id="2e621-191">Speichern Sie die Datei, lesen Sie die Datei, und speichern Sie den Inhalt als Variable namens `$UpdateSpoofedSenders` :</span><span class="sxs-lookup"><span data-stu-id="2e621-191">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders`:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="2e621-192">Verwenden Sie die `$UpdateSpoofedSenders` Variable, um die Spoof Intelligence-Richtlinie zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="2e621-192">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="2e621-193">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="2e621-193">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy).</span></span>

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a><span data-ttu-id="2e621-194">Konfigurieren von Spoof Intelligence mithilfe & Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="2e621-194">Use the Security & Compliance Center to configure spoof intelligence</span></span>

<span data-ttu-id="2e621-195">Die Konfigurationsoptionen für spoof intelligence werden unter [Spoofeinstellungen in Antiphishingrichtlinien beschrieben.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="2e621-195">The configuration options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

<span data-ttu-id="2e621-196">Sie können Einstellungen für spoof intelligence in der Standardmäßigen Antiphishingrichtlinie und auch in benutzerdefinierten Richtlinien konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="2e621-196">You can configure spoof intelligence settings in the default anti-phishing policy, and also in custom policies.</span></span> <span data-ttu-id="2e621-197">Anweisungen basierend auf Ihrem Abonnement finden Sie in einem der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="2e621-197">For instructions based on your subscription, see one of the following topics:</span></span>

- <span data-ttu-id="2e621-198">[Konfigurieren von Antiphishingrichtlinien in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="2e621-198">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>

- <span data-ttu-id="2e621-199">[Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365](configure-atp-anti-phishing-policies.md).</span><span class="sxs-lookup"><span data-stu-id="2e621-199">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="2e621-200">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="2e621-200">How do you know these procedures worked?</span></span>

<span data-ttu-id="2e621-201">Verwenden Sie einen der folgenden Schritte, um zu überprüfen, ob Sie spoof intelligence mit Absendern konfiguriert haben, die spoofen dürfen und nicht spoofen dürfen, und ob Sie die Einstellungen für spoof intelligence konfiguriert haben:</span><span class="sxs-lookup"><span data-stu-id="2e621-201">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, and that you've configured the spoof intelligence settings, use any of the following steps:</span></span>

- <span data-ttu-id="2e621-202">Wechseln Sie im Security & Compliance  Center zu Bedrohungsverwaltungsrichtlinie \>  \> **Antispam** erweitern \> **Spoof Intelligence Policy** select Show me \> **senders I already reviewed** select the Your \> **Domains** or **External Domains,** and verify the **Allowed to spoof?** value for the sender.</span><span class="sxs-lookup"><span data-stu-id="2e621-202">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="2e621-203">Führen Sie in PowerShell die folgenden Befehle aus, um die Absender anzuzeigen, die spoofen dürfen und nicht dürfen:</span><span class="sxs-lookup"><span data-stu-id="2e621-203">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="2e621-204">Führen Sie in PowerShell den folgenden Befehl aus, um die Liste aller gefälschten Absender in eine CSV-Datei zu exportieren:</span><span class="sxs-lookup"><span data-stu-id="2e621-204">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- <span data-ttu-id="2e621-205">Wechseln Sie im Security & Compliance  Center zu Bedrohungsverwaltungsrichtlinie \>  \> **Antiphishing** oder **ATP-Antiphishing,** und gehen Sie wie folgt vor:  </span><span class="sxs-lookup"><span data-stu-id="2e621-205">In the Security & Compliance Center, go to **Threat management** \> **Policy**  \> **Anti-phishing**  or **ATP anti-phishing**, and do either of the following steps:</span></span>

  - <span data-ttu-id="2e621-206">Wählen Sie eine Richtlinie aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="2e621-206">Select a policy from the list.</span></span> <span data-ttu-id="2e621-207">Überprüfen Sie im angezeigten Flyout die Werte im **Abschnitt Spoof.**</span><span class="sxs-lookup"><span data-stu-id="2e621-207">In the flyout that appears, verify the values in the **Spoof** section.</span></span>
  - <span data-ttu-id="2e621-208">Klicken Sie **auf Standardrichtlinie**.</span><span class="sxs-lookup"><span data-stu-id="2e621-208">Click **Default policy**.</span></span> <span data-ttu-id="2e621-209">Überprüfen Sie im angezeigten Flyout die Werte im **Abschnitt Spoof.**</span><span class="sxs-lookup"><span data-stu-id="2e621-209">In the flyout that appears, verify the values in the **Spoof** section.</span></span>

- <span data-ttu-id="2e621-210">Ersetzen Sie in Exchange Online PowerShell durch Office365 AntiPhish Default oder den Namen einer benutzerdefinierten Richtlinie, und führen Sie den folgenden Befehl aus, um die \<Name\> Einstellungen zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="2e621-210">In Exchange Online PowerShell, replace \<Name\> with Office365 AntiPhish Default or the name of a custom policy, and run the following command to verify the settings:</span></span>

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a><span data-ttu-id="2e621-211">Weitere Möglichkeiten zum Verwalten von Spoofing und Phishing</span><span class="sxs-lookup"><span data-stu-id="2e621-211">Other ways to manage spoofing and phishing</span></span>

<span data-ttu-id="2e621-212">Sind Sie sorgfältig beim Thema Spoofing und Phishingschutz.</span><span class="sxs-lookup"><span data-stu-id="2e621-212">Be diligent about spoofing and phishing protection.</span></span> <span data-ttu-id="2e621-213">Hier finden Sie verwandte Möglichkeiten zum Überprüfen von Absendern, die Ihre Domäne spoofieren, und um zu verhindern, dass diese Ihre Organisation beschädigen:</span><span class="sxs-lookup"><span data-stu-id="2e621-213">Here are related ways to check on senders spoofing your domain and help prevent them from damaging your organization:</span></span>

- <span data-ttu-id="2e621-214">Überprüfen Sie **den Spoof-E-Mail-Bericht**.</span><span class="sxs-lookup"><span data-stu-id="2e621-214">Check the **Spoof Mail Report**.</span></span> <span data-ttu-id="2e621-215">Sie können diesen Bericht häufig zum Anzeigen und Verwalten gefälschter Absender verwenden.</span><span class="sxs-lookup"><span data-stu-id="2e621-215">You can use this report often to view and help manage spoofed senders.</span></span> <span data-ttu-id="2e621-216">Weitere Informationen finden Sie unter [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span><span class="sxs-lookup"><span data-stu-id="2e621-216">For information, see [Spoof Detections report](view-email-security-reports.md#spoof-detections-report).</span></span>

- <span data-ttu-id="2e621-217">Überprüfen Sie die Konfiguration des Sender Policy Framework (SPF).</span><span class="sxs-lookup"><span data-stu-id="2e621-217">Review your Sender Policy Framework (SPF) configuration.</span></span> <span data-ttu-id="2e621-218">Eine kurze Einführung in SPF und seine schnelle Konfiguration finden Sie unter [Einrichten von SPF in Microsoft 365 zur Verhinderung von Spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="2e621-218">For a quick introduction to SPF and to get it configured quickly, see [Set up SPF in Microsoft 365 to help prevent spoofing](set-up-spf-in-office-365-to-help-prevent-spoofing.md).</span></span> <span data-ttu-id="2e621-219">Ausführlichere Informationen zur Verwendung von SPF durch Office 365 oder zur Problembehandlung oder zu nicht standardmäßigen Bereitstellungen, z. B. Hybridbereitstellungen, finden Sie unter [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span><span class="sxs-lookup"><span data-stu-id="2e621-219">For a more in-depth understanding of how Office 365 uses SPF, or for troubleshooting or non-standard deployments such as hybrid deployments, start with [How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md).</span></span>

- <span data-ttu-id="2e621-220">Überprüfen Sie Die Konfiguration von "DomainKeys Identified Mail" (DKIM).</span><span class="sxs-lookup"><span data-stu-id="2e621-220">Review your DomainKeys Identified Mail (DKIM) configuration.</span></span> <span data-ttu-id="2e621-221">Sie sollten DKIM zusätzlich zu SPF und DMARC verwenden, um zu verhindern, dass Angreifer Nachrichten senden, die so aussehen, als würden sie von Ihrer Domäne kommen.</span><span class="sxs-lookup"><span data-stu-id="2e621-221">You should use DKIM in addition to SPF and DMARC to help prevent attackers from sending messages that look like they are coming from your domain.</span></span> <span data-ttu-id="2e621-222">Mit DKIM können Sie E-Mail-Nachrichten in der Kopfzeile der Nachricht eine digitale Signatur hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="2e621-222">DKIM lets you add a digital signature to email messages in the message header.</span></span> <span data-ttu-id="2e621-223">Weitere Informationen finden Sie unter [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span><span class="sxs-lookup"><span data-stu-id="2e621-223">For information, see [Use DKIM to validate outbound email sent from your custom domain in Office 365](use-dkim-to-validate-outbound-email.md).</span></span>

- <span data-ttu-id="2e621-224">Überprüfen Sie Die Domänenbasierte Nachrichtenauthentifizierung, -berichterstellung und -konformität (DMARC).</span><span class="sxs-lookup"><span data-stu-id="2e621-224">Review your Domain-based Message Authentication, Reporting, and Conformance (DMARC) configuration.</span></span> <span data-ttu-id="2e621-225">Die Implementierung von DMARC zusammen mit SPF und DKIM bietet zusätzlichen Schutz vor Spoofing- und Phishing-E-Mails.</span><span class="sxs-lookup"><span data-stu-id="2e621-225">Implementing DMARC with SPF and DKIM provides additional protection against spoofing and phishing email.</span></span> <span data-ttu-id="2e621-226">DMARC unterstützt die E-Mail-Systeme der Empfänger bei der Behandlung von Nachrichten, die von Ihrer Domäne gesendet wurden, jedoch die SPF- oder DKIM-Prüfungen nicht bestanden haben.</span><span class="sxs-lookup"><span data-stu-id="2e621-226">DMARC helps receiving mail systems determine what to do with messages sent from your domain that fail SPF or DKIM checks.</span></span> <span data-ttu-id="2e621-227">Weitere Informationen finden Sie unter [Verwenden von DMARC zum Überprüfen von E-Mails in Office 365](use-dmarc-to-validate-email.md).</span><span class="sxs-lookup"><span data-stu-id="2e621-227">For information, see [Use DMARC to validate email in Office 365](use-dmarc-to-validate-email.md).</span></span>
