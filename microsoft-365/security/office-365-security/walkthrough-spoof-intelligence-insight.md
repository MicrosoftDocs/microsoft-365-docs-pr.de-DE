---
title: Verwalten von gefälschten Absendern mithilfe der Spoof Intelligence Policy und spoof intelligence insight
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: Administratoren können erfahren, wie Sie die Spoof Intelligence Policy und den Einblick in spoof intelligence verwenden, um erkannte spoofierte Absender zu erlauben oder zu blockieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 821488f79186e1b5c306b587764377989346eea5
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52530886"
---
# <a name="manage-spoofed-senders-using-the-spoof-intelligence-policy-and-spoof-intelligence-insight-in-eop"></a><span data-ttu-id="ffc27-103">Verwalten von gefälschten Absendern mithilfe der Spoof Intelligence Policy und spoof intelligence insight in EOP</span><span class="sxs-lookup"><span data-stu-id="ffc27-103">Manage spoofed senders using the spoof intelligence policy and spoof intelligence insight in EOP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="ffc27-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="ffc27-104">**Applies to**</span></span>
- [<span data-ttu-id="ffc27-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="ffc27-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ffc27-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ffc27-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

> [!NOTE]
> <span data-ttu-id="ffc27-107">In diesem Artikel wird die ältere spoofierte Absenderverwaltungserfahrung beschrieben, die ersetzt wird.</span><span class="sxs-lookup"><span data-stu-id="ffc27-107">This article describes the older spoofed sender management experience that's being replaced.</span></span> <span data-ttu-id="ffc27-108">Weitere Informationen zur neuen Erfahrung finden Sie unter [Spoof Intelligence Insight in EOP](learn-about-spoof-intelligence.md)</span><span class="sxs-lookup"><span data-stu-id="ffc27-108">For more information about the new experience, see [Spoof intelligence insight in EOP](learn-about-spoof-intelligence.md)</span></span>

<span data-ttu-id="ffc27-109">In Microsoft 365 Organisationen mit Postfächern in Exchange Online oder eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer werden eingehende E-Mail-Nachrichten ab Oktober 2018 automatisch vor Spoofing durch EOP geschützt.</span><span class="sxs-lookup"><span data-stu-id="ffc27-109">In Microsoft 365 organizations with mailboxes in Exchange Online or standalone Exchange Online Protection (EOP) organizations without Exchange Online mailboxes, inbound email messages are automatically protected against spoofing by EOP as of October 2018.</span></span> <span data-ttu-id="ffc27-110">EOP verwendet **Spoof Intelligence** als Teil der allgemeinen Verteidigung Ihrer Organisation gegen Phishing.</span><span class="sxs-lookup"><span data-stu-id="ffc27-110">EOP uses **spoof intelligence** as part of your organization's overall defense against phishing.</span></span> <span data-ttu-id="ffc27-111">Weitere Informationen finden Sie unter Schutz vor [Spoofing in EOP](anti-spoofing-protection.md).</span><span class="sxs-lookup"><span data-stu-id="ffc27-111">For more information, see [Anti-spoofing protection in EOP](anti-spoofing-protection.md).</span></span>

<span data-ttu-id="ffc27-112">Die Standardmäßige (und einzige) **Spoof** intelligence-Richtlinie hilft sicherzustellen, dass die gefälschten E-Mails, die von legitimen Absendern gesendet werden, nicht in #A0 versenkt werden, während Ihre Benutzer vor Spam- oder Phishingangriffen geschützt werden.</span><span class="sxs-lookup"><span data-stu-id="ffc27-112">The default (and only) **spoof intelligence policy** helps ensure that the spoofed email sent by legitimate senders doesn't get caught up in EOP spam filters while protecting your users from spam or phishing attacks.</span></span> <span data-ttu-id="ffc27-113">Sie können auch den Einblick in die **Spoof-Intelligenz** verwenden, um schnell zu ermitteln, welche externen Absender Ihnen legitimerweise nicht authentifizierte E-Mails senden (Nachrichten von Domänen, die keine SPF-, DKIM- oder DMARC-Prüfungen bestehen).</span><span class="sxs-lookup"><span data-stu-id="ffc27-113">You can also use the **Spoof intelligence insight** to quickly determine which external senders are legitimately sending you unauthenticated email (messages from domains that don't pass SPF, DKIM, or DMARC checks).</span></span>

<span data-ttu-id="ffc27-114">Sie können Spoof Intelligence im Security & Compliance Center oder in PowerShell (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer) verwalten.</span><span class="sxs-lookup"><span data-stu-id="ffc27-114">You can manage spoof intelligence in the Security & Compliance Center, or in PowerShell (Exchange Online PowerShell for Microsoft 365 organizations with mailboxes in Exchange Online; standalone EOP PowerShell for organizations without Exchange Online mailboxes).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="ffc27-115">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="ffc27-115">What do you need to know before you begin?</span></span>

- <span data-ttu-id="ffc27-116">Sie öffnen das Security & Compliance Center unter <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="ffc27-116">You open the Security & Compliance Center at <https://protection.office.com/>.</span></span>
  - <span data-ttu-id="ffc27-117">Um direkt zur Seite **Antispameinstellungen** für die Spoof Intelligence-Richtlinie zu wechseln, verwenden Sie <https://protection.office.com/antispam> .</span><span class="sxs-lookup"><span data-stu-id="ffc27-117">To go directly to the **Anti-spam settings** page for the spoof intelligence policy, use <https://protection.office.com/antispam>.</span></span>
  - <span data-ttu-id="ffc27-118">Verwenden Sie , um direkt zur **Seite Sicherheitsdashboard** zu wechseln, um einen Einblick in spoof intelligence zu <https://protection.office.com/searchandinvestigation/dashboard> erhalten.</span><span class="sxs-lookup"><span data-stu-id="ffc27-118">To go directly to the **Security dashboard** page for the spoof intelligence insight, use <https://protection.office.com/searchandinvestigation/dashboard>.</span></span>

- <span data-ttu-id="ffc27-119">Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span><span class="sxs-lookup"><span data-stu-id="ffc27-119">To connect to Exchange Online PowerShell, see [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span> <span data-ttu-id="ffc27-120">Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span><span class="sxs-lookup"><span data-stu-id="ffc27-120">To connect to standalone EOP PowerShell, see [Connect to Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell).</span></span>

- <span data-ttu-id="ffc27-121">Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:</span><span class="sxs-lookup"><span data-stu-id="ffc27-121">You need to be assigned permissions in **Exchange Online** before you can do the procedures in this article:</span></span>
  - <span data-ttu-id="ffc27-122">Um die Spoof Intelligence-Richtlinie zu ändern oder Spoof Intelligence zu  aktivieren oder zu deaktivieren, müssen Sie Mitglied der Rollengruppen Organisationsverwaltung oder **Sicherheitsadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="ffc27-122">To modify the spoof intelligence policy or enable or disable spoof intelligence, you need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span>
  - <span data-ttu-id="ffc27-123">Für den schreibgeschützten Zugriff auf die Spoof Intelligence-Richtlinie müssen Sie Mitglied der Rollengruppen **"Globaler Leser"** oder **"Sicherheitsleser"** sein.</span><span class="sxs-lookup"><span data-stu-id="ffc27-123">For read-only access to the spoof intelligence policy, you need to be a member of the **Global Reader** or **Security Reader** role groups.</span></span>

  <span data-ttu-id="ffc27-124">Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).</span><span class="sxs-lookup"><span data-stu-id="ffc27-124">For more information, see [Permissions in Exchange Online](/exchange/permissions-exo/permissions-exo).</span></span>

  <span data-ttu-id="ffc27-125">**Hinweise**:</span><span class="sxs-lookup"><span data-stu-id="ffc27-125">**Notes**:</span></span>

  - <span data-ttu-id="ffc27-126">Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ffc27-126">Adding users to the corresponding Azure Active Directory role in the Microsoft 365 admin center gives users the required permissions _and_ permissions for other features in Microsoft 365.</span></span> <span data-ttu-id="ffc27-127">Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).</span><span class="sxs-lookup"><span data-stu-id="ffc27-127">For more information, see [About admin roles](../../admin/add-users/about-admin-roles.md).</span></span>
  - <span data-ttu-id="ffc27-128">Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.</span><span class="sxs-lookup"><span data-stu-id="ffc27-128">The **View-Only Organization Management** role group in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) also gives read-only access to the feature.</span></span>

- <span data-ttu-id="ffc27-129">Die Optionen für spoof intelligence werden unter [Spoofeinstellungen in Antiphishingrichtlinien beschrieben.](set-up-anti-phishing-policies.md#spoof-settings)</span><span class="sxs-lookup"><span data-stu-id="ffc27-129">The options for spoof intelligence are described in [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

- <span data-ttu-id="ffc27-130">Sie können die Einstellungen für spoof intelligence in Antiphishingrichtlinien aktivieren, deaktivieren und konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="ffc27-130">You can enable, disable, and configure the spoof intelligence settings in anti-phishing policies.</span></span> <span data-ttu-id="ffc27-131">Anweisungen basierend auf Ihrem Abonnement finden Sie in einem der folgenden Themen:</span><span class="sxs-lookup"><span data-stu-id="ffc27-131">For instructions based on your subscription, see one of the following topics:</span></span>

  - <span data-ttu-id="ffc27-132">[Konfigurieren von Antiphishingrichtlinien in EOP](configure-anti-phishing-policies-eop.md).</span><span class="sxs-lookup"><span data-stu-id="ffc27-132">[Configure anti-phishing policies in EOP](configure-anti-phishing-policies-eop.md).</span></span>
  - <span data-ttu-id="ffc27-133">[Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365.](configure-atp-anti-phishing-policies.md)</span><span class="sxs-lookup"><span data-stu-id="ffc27-133">[Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).</span></span>

- <span data-ttu-id="ffc27-134">Unsere empfohlenen Einstellungen für spoof intelligence finden Sie unter [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span><span class="sxs-lookup"><span data-stu-id="ffc27-134">For our recommended settings for spoof intelligence, see [EOP default anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-default-anti-phishing-policy-settings).</span></span>

## <a name="manage-spoofed-senders"></a><span data-ttu-id="ffc27-135">Verwalten gefälschter Absender</span><span class="sxs-lookup"><span data-stu-id="ffc27-135">Manage spoofed senders</span></span>

<span data-ttu-id="ffc27-136">Es gibt zwei Möglichkeiten, gefälschte Absender zu erlauben und zu blockieren:</span><span class="sxs-lookup"><span data-stu-id="ffc27-136">There are two ways to allow and block spoofed senders:</span></span>

- [<span data-ttu-id="ffc27-137">Verwenden der Spoof Intelligence-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ffc27-137">Use the spoof intelligence policy</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-policy)
- [<span data-ttu-id="ffc27-138">Verwenden der Einblicke in spoof intelligence</span><span class="sxs-lookup"><span data-stu-id="ffc27-138">Use the spoof intelligence insight</span></span>](#manage-spoofed-senders-in-the-spoof-intelligence-insight)

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-policy"></a><span data-ttu-id="ffc27-139">Verwalten gefälschter Absender in der Spoof Intelligence-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="ffc27-139">Manage spoofed senders in the spoof intelligence policy</span></span>

1. <span data-ttu-id="ffc27-140">Navigieren Sie im Security & Compliance Center zu **Bedrohungsmanagement** \> **Richtlinie** \> **Antispam**.</span><span class="sxs-lookup"><span data-stu-id="ffc27-140">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam**.</span></span>

2. <span data-ttu-id="ffc27-141">Klicken Sie auf der Seite **Antispameinstellungen** auf ![ Symbol erweitern, ](../../media/scc-expand-icon.png) um die **Spoof Intelligence-Richtlinie zu erweitern.**</span><span class="sxs-lookup"><span data-stu-id="ffc27-141">On the **Anti-spam settings** page, click ![Expand icon](../../media/scc-expand-icon.png) to expand **Spoof intelligence policy**.</span></span>

   ![Auswählen der Spoof Intelligence-Richtlinie](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. <span data-ttu-id="ffc27-143">Treffen Sie eine der folgenden Auswahlen:</span><span class="sxs-lookup"><span data-stu-id="ffc27-143">Make one of the following selections:</span></span>

   - <span data-ttu-id="ffc27-144">**Überprüfen neuer Absender**</span><span class="sxs-lookup"><span data-stu-id="ffc27-144">**Review new senders**</span></span>
   - <span data-ttu-id="ffc27-145">**Absender anzeigen, die ich bereits überprüft habe**</span><span class="sxs-lookup"><span data-stu-id="ffc27-145">**Show me senders I already reviewed**</span></span>

4. <span data-ttu-id="ffc27-146">Wählen Sie im angezeigten Flyout "Entscheiden, ob diese Absender ihre Benutzer-Flyouts **spoofen** dürfen" eine der folgenden Registerkarten aus:</span><span class="sxs-lookup"><span data-stu-id="ffc27-146">In the **Decide if these senders are allowed to spoof your users** flyout that appears, select one of the following tabs:</span></span>

   - <span data-ttu-id="ffc27-147">**Ihre Domänen:** Absender, die Benutzer in Ihren internen Domänen spoofieren.</span><span class="sxs-lookup"><span data-stu-id="ffc27-147">**Your Domains**: Senders spoofing users in your internal domains.</span></span>
   - <span data-ttu-id="ffc27-148">**Externe Domänen:** Absender, die Benutzer in externen Domänen spoofieren.</span><span class="sxs-lookup"><span data-stu-id="ffc27-148">**External Domains**: Senders spoofing users in external domains.</span></span>

5. <span data-ttu-id="ffc27-149">Klicken ![ Sie in der Spalte ](../../media/scc-expand-icon.png) **Spoofing?** auf Erweitern(Symbol).</span><span class="sxs-lookup"><span data-stu-id="ffc27-149">Click ![Expand icon](../../media/scc-expand-icon.png) in the **Allowed to spoof?** column.</span></span> <span data-ttu-id="ffc27-150">Wählen **Sie Ja** aus, um den gefälschten Absender zu erlauben, oder wählen Sie **Nein** aus, um die Nachricht als spoofed zu markieren.</span><span class="sxs-lookup"><span data-stu-id="ffc27-150">Choose **Yes** to allow the spoofed sender, or choose **No** to mark the message as spoofed.</span></span> <span data-ttu-id="ffc27-151">Die Aktion wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist **Move message to Junk Email folder**).</span><span class="sxs-lookup"><span data-stu-id="ffc27-151">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="ffc27-152">Weitere Informationen finden Sie unter [Spoofeinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md#spoof-settings).</span><span class="sxs-lookup"><span data-stu-id="ffc27-152">For more information, see [Spoof settings in anti-phishing policies](set-up-anti-phishing-policies.md#spoof-settings).</span></span>

   ![Screenshot des Flyouts von spoofierten Absendern und der Frage, ob der Absender spoofen darf](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   <span data-ttu-id="ffc27-154">Die angezeigten Spalten und Werte werden in der folgenden Liste erläutert:</span><span class="sxs-lookup"><span data-stu-id="ffc27-154">The columns and values that you see are explained in the following list:</span></span>

   - <span data-ttu-id="ffc27-155">**Spoofed user:** Das Benutzerkonto, das gefälscht wird.</span><span class="sxs-lookup"><span data-stu-id="ffc27-155">**Spoofed user**: The user account that's being spoofed.</span></span> <span data-ttu-id="ffc27-156">Dies ist der Absender der Nachricht in der Absenderadresse (auch als Adresse bezeichnet), die `5322.From` in E-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ffc27-156">This is the message sender in the From address (also known as the `5322.From` address) that's shown in email clients.</span></span> <span data-ttu-id="ffc27-157">Die Gültigkeit dieser Adresse wird von SPF nicht überprüft.</span><span class="sxs-lookup"><span data-stu-id="ffc27-157">The validity of this address is not checked by SPF.</span></span>
     - <span data-ttu-id="ffc27-158">Auf der Registerkarte Ihre **Domänen** enthält der Wert eine einzelne E-Mail-Adresse, oder wenn der Quell-E-Mail-Server mehrere Benutzerkonten spoofiert, enthält er **mehrere**.</span><span class="sxs-lookup"><span data-stu-id="ffc27-158">On the **Your Domains** tab, the value contains a single email address, or if the source email server is spoofing multiple user accounts, it contains **More than one**.</span></span>
     - <span data-ttu-id="ffc27-159">Auf der **Registerkarte Externe Domänen** enthält der Wert die Domäne des spoofierten Benutzers, nicht die vollständige E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="ffc27-159">On the **External Domains** tab, the value contains the domain of the spoofed user, not the full email address.</span></span>

   - <span data-ttu-id="ffc27-160">**Sendeinfrastruktur**: Die Domäne, die in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers gefunden wurde.</span><span class="sxs-lookup"><span data-stu-id="ffc27-160">**Sending Infrastructure**: The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="ffc27-161">Wenn die Quell-IP-Adresse keinen PTR-Eintrag enthält, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="ffc27-161">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>

     <span data-ttu-id="ffc27-162">Weitere Informationen zu Nachrichtenquellen und Nachrichtensendern finden Sie unter [Eine Übersicht über E-Mail-Nachrichtenstandards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span><span class="sxs-lookup"><span data-stu-id="ffc27-162">For more information about message sources and message senders, see [An overview of email message standards](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards).</span></span>

   - <span data-ttu-id="ffc27-163">**Anzahl der Nachrichten**: Die Anzahl der Nachrichten aus der sendenden Infrastruktur an Ihre Organisation, die den angegebenen gefälschten Absender oder Absender innerhalb der letzten 30 Tage enthalten.</span><span class="sxs-lookup"><span data-stu-id="ffc27-163">**# of messages**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed sender or senders within the last 30 days.</span></span>

   - <span data-ttu-id="ffc27-164">**# der Benutzerbeschwerden**: Beschwerden, die von Ihren Benutzern gegen diesen Absender innerhalb der letzten 30 Tage eingereicht wurden.</span><span class="sxs-lookup"><span data-stu-id="ffc27-164">**# of user complaints**: Complaints filed by your users against this sender within the last 30 days.</span></span> <span data-ttu-id="ffc27-165">Beschwerden werden in der Regel in Form von Junk-Übermittlungen an Microsoft eingereicht.</span><span class="sxs-lookup"><span data-stu-id="ffc27-165">Complaints are usually in the form of junk submissions to Microsoft.</span></span>

   - <span data-ttu-id="ffc27-166">**Authentifizierungsergebnis**: Einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="ffc27-166">**Authentication result**: One of the following values:</span></span>
      - <span data-ttu-id="ffc27-167">**Übergeben:** Der Absender hat E-Mail-Authentifizierungsprüfungen (SPF oder DKIM) bestanden.</span><span class="sxs-lookup"><span data-stu-id="ffc27-167">**Passed**: The sender passed sender email authentication checks (SPF or DKIM).</span></span>
      - <span data-ttu-id="ffc27-168">**Fehler:** Fehler beim EOP-Absenderauthentifizierungsüberprüfungen.</span><span class="sxs-lookup"><span data-stu-id="ffc27-168">**Failed**: The sender failed EOP sender authentication checks.</span></span>
      - <span data-ttu-id="ffc27-169">**Unbekannt:** Das Ergebnis dieser Prüfungen ist nicht bekannt.</span><span class="sxs-lookup"><span data-stu-id="ffc27-169">**Unknown**: The result of these checks isn't known.</span></span>

   - <span data-ttu-id="ffc27-170">**Entscheidungssatz von**: Zeigt an, wer ermittelt hat, ob die sendende Infrastruktur den Benutzer spoofen darf:</span><span class="sxs-lookup"><span data-stu-id="ffc27-170">**Decision set by**: Shows who determined if the sending infrastructure is allowed to spoof the user:</span></span>
       - <span data-ttu-id="ffc27-171">**Spoof Intelligence Policy** (automatisch)</span><span class="sxs-lookup"><span data-stu-id="ffc27-171">**Spoof intelligence policy** (automatic)</span></span>
       - <span data-ttu-id="ffc27-172">**Administrator** (manuell)</span><span class="sxs-lookup"><span data-stu-id="ffc27-172">**Admin** (manual)</span></span>

   - <span data-ttu-id="ffc27-173">**Zuletzt gesehen:** Das letzte Datum, an dem eine Nachricht von der sendenden Infrastruktur empfangen wurde, die den spoofierten Benutzer enthält.</span><span class="sxs-lookup"><span data-stu-id="ffc27-173">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed user.</span></span>

   - <span data-ttu-id="ffc27-174">**Darf ges spooft werden?**: Die hier angezeigten Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ffc27-174">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="ffc27-175">**Ja:** Nachrichten aus der Kombination aus spoofierten Benutzern und sendender Infrastruktur sind zulässig und werden nicht als spoofierte E-Mails behandelt.</span><span class="sxs-lookup"><span data-stu-id="ffc27-175">**Yes**: Messages from the combination of spoofed user and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="ffc27-176">**Nein:** Nachrichten aus der Kombination aus spoofiertem Benutzer und sendender Infrastruktur werden als Spoofing gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="ffc27-176">**No**: Messages from the combination of spoofed user and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="ffc27-177">Die Aktion wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist **Move message to Junk Email folder**).</span><span class="sxs-lookup"><span data-stu-id="ffc27-177">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span> <span data-ttu-id="ffc27-178">Weitere Informationen finden Sie im nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="ffc27-178">See the next section for more information.</span></span>

     - <span data-ttu-id="ffc27-179">**Einige Benutzer** (**Nur Registerkarte "Ihre** Domänen"): Eine sendende Infrastruktur fälscht mehrere Benutzer, wobei einige spoofierte Benutzer zulässig sind und andere nicht.</span><span class="sxs-lookup"><span data-stu-id="ffc27-179">**Some users** (**Your Domains** tab only): A sending infrastructure is spoofing multiple users, where some spoofed users are allowed and others are not.</span></span> <span data-ttu-id="ffc27-180">Verwenden Sie die **Registerkarte Detail,** um die spezifischen Adressen zu sehen.</span><span class="sxs-lookup"><span data-stu-id="ffc27-180">Use the **Detailed** tab to see the specific addresses.</span></span>

6. <span data-ttu-id="ffc27-181">Klicken Sie unten auf der Seite auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ffc27-181">At the bottom of the page, click **Save**.</span></span>

#### <a name="use-powershell-to-manage-spoofed-senders"></a><span data-ttu-id="ffc27-182">Verwenden von PowerShell zum Verwalten gefälschter Absender</span><span class="sxs-lookup"><span data-stu-id="ffc27-182">Use PowerShell to manage spoofed senders</span></span>

<span data-ttu-id="ffc27-183">Verwenden Sie die folgende Syntax, um zugelassene und blockierte Absender in Spoof Intelligence zu sehen:</span><span class="sxs-lookup"><span data-stu-id="ffc27-183">To view allowed and blocked senders in spoof intelligence, use the following syntax:</span></span>

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

<span data-ttu-id="ffc27-184">In diesem Beispiel werden detaillierte Informationen zu allen Absendern zurückgegeben, die Benutzer in Ihren Domänen spoofen dürfen.</span><span class="sxs-lookup"><span data-stu-id="ffc27-184">This example returns detailed information about all senders that are allowed to spoof users in your domains.</span></span>

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

<span data-ttu-id="ffc27-185">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ffc27-185">For detailed syntax and parameter information, see [Get-PhishFilterPolicy](/powershell/module/exchange/get-phishfilterpolicy).</span></span>

<span data-ttu-id="ffc27-186">Führen Sie die folgenden Schritte aus, um zugelassene und blockierte Absender in Spoof Intelligence zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="ffc27-186">To configure allowed and blocked senders in spoof intelligence, follow these steps:</span></span>

1. <span data-ttu-id="ffc27-187">Erfassen Sie die aktuelle Liste der erkannten gefälschten Absender, indem Sie die Ausgabe des **Get-PhishFilterPolicy-Cmdlets** in eine CSV-Datei schreiben, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ffc27-187">Capture the current list of detected spoofed senders by writing the output of the **Get-PhishFilterPolicy** cmdlet to a CSV file by running the following command:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. <span data-ttu-id="ffc27-188">Bearbeiten Sie die CSV-Datei, um die folgenden Werte hinzuzufügen oder zu ändern:</span><span class="sxs-lookup"><span data-stu-id="ffc27-188">Edit the CSV file to add or modify the following values:</span></span>
   - <span data-ttu-id="ffc27-189">**Sender** (Domäne im PTR-Eintrag oder der IP/24-Adresse des Quellservers)</span><span class="sxs-lookup"><span data-stu-id="ffc27-189">**Sender** (domain in source server's PTR record or IP/24 address)</span></span>
   - <span data-ttu-id="ffc27-190">**SpoofedUser**: Einer der folgenden Werte:</span><span class="sxs-lookup"><span data-stu-id="ffc27-190">**SpoofedUser**: One of the following values:</span></span>
     - <span data-ttu-id="ffc27-191">Die E-Mail-Adresse des internen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ffc27-191">The internal user's email address.</span></span>
     - <span data-ttu-id="ffc27-192">Die E-Mail-Domäne des externen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="ffc27-192">The external user's email domain.</span></span>
     - <span data-ttu-id="ffc27-193">Ein leerer Wert, der angibt, dass Sie spoofierte Nachrichten vom angegebenen **Absender** blockieren oder zulassen möchten, unabhängig von der gefälschten E-Mail-Adresse.</span><span class="sxs-lookup"><span data-stu-id="ffc27-193">A blank value that indicates you want to block or allow any and all spoofed messages from the specified **Sender**, regardless of the spoofed email address.</span></span>
   - <span data-ttu-id="ffc27-194">**AllowedToSpoof** (Ja oder Nein)</span><span class="sxs-lookup"><span data-stu-id="ffc27-194">**AllowedToSpoof** (Yes or No)</span></span>
   - <span data-ttu-id="ffc27-195">**SpoofType** (Intern oder Extern)</span><span class="sxs-lookup"><span data-stu-id="ffc27-195">**SpoofType** (Internal or External)</span></span>

   <span data-ttu-id="ffc27-196">Speichern Sie die Datei, lesen Sie die Datei, und speichern Sie den Inhalt als Variable `$UpdateSpoofedSenders` namens, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ffc27-196">Save the file, read the file, and store the contents as a variable named `$UpdateSpoofedSenders` by running the following command:</span></span>

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. <span data-ttu-id="ffc27-197">Verwenden Sie `$UpdateSpoofedSenders` die Variable, um die Spoof Intelligence-Richtlinie zu konfigurieren, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="ffc27-197">Use the `$UpdateSpoofedSenders` variable to configure the spoof intelligence policy by running the following command:</span></span>

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

<span data-ttu-id="ffc27-198">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span><span class="sxs-lookup"><span data-stu-id="ffc27-198">For detailed syntax and parameter information, see [Set-PhishFilterPolicy](/powershell/module/exchange/set-phishfilterpolicy).</span></span>

### <a name="manage-spoofed-senders-in-the-spoof-intelligence-insight"></a><span data-ttu-id="ffc27-199">Verwalten von gefälschten Absendern in der Einblicke in spoof intelligence</span><span class="sxs-lookup"><span data-stu-id="ffc27-199">Manage spoofed senders in the spoof intelligence insight</span></span>

1. <span data-ttu-id="ffc27-200">Wechseln Sie im Security & Compliance Center zu **Threat Management** \> **Dashboard**.</span><span class="sxs-lookup"><span data-stu-id="ffc27-200">In the Security & Compliance Center, go to **Threat Management** \> **Dashboard**.</span></span>

2. <span data-ttu-id="ffc27-201">Suchen Sie **in** der Zeile Insights nach einem der folgenden Elemente:</span><span class="sxs-lookup"><span data-stu-id="ffc27-201">In the **Insights** row, look for one of the following items:</span></span>

   - <span data-ttu-id="ffc27-202">**Wahrscheinlich spoofierte Domänen in** den letzten sieben Tagen: Diese Einsicht gibt an, dass Spoofintelligenz aktiviert ist (standardmäßig aktiviert).</span><span class="sxs-lookup"><span data-stu-id="ffc27-202">**Likely spoofed domains over the past seven days**: This insight indicates that spoof intelligence is enabled (it's enabled by default).</span></span>
   - <span data-ttu-id="ffc27-203">**Spoofschutz** aktivieren: Diese Einsicht zeigt an, dass die Spoofintelligenz deaktiviert ist, und wenn Sie auf die Einblicke klicken, können Sie die Spoofintelligenz aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ffc27-203">**Enable Spoof Protection**: This insight indicates that spoof intelligence is disabled, and clicking on the insight allows you to enable spoof intelligence.</span></span>

3. <span data-ttu-id="ffc27-204">Die Einblicke im Dashboard zeigen Ihnen Informationen wie dies:</span><span class="sxs-lookup"><span data-stu-id="ffc27-204">The insight on the dashboard shows you information like this:</span></span>

   ![Screenshot der Einblicke in spoof intelligence](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   <span data-ttu-id="ffc27-206">Diese Einsicht hat zwei Modi:</span><span class="sxs-lookup"><span data-stu-id="ffc27-206">This insight has two modes:</span></span>

   - <span data-ttu-id="ffc27-207">**Einblicksmodus:** Wenn spoof intelligence aktiviert ist, zeigt die Einsicht, wie viele Nachrichten in den letzten sieben Tagen von unseren Funktionen für spoof intelligence betroffen waren.</span><span class="sxs-lookup"><span data-stu-id="ffc27-207">**Insight mode**: If spoof intelligence is enabled, the insight shows you how many messages were impacted by our spoof intelligence capabilities over the past seven days.</span></span>
   - <span data-ttu-id="ffc27-208">**Was wäre,** wenn Der Modus : Wenn die Spoofintelligenz deaktiviert ist, zeigt die Einsicht, wie viele Nachrichten in den letzten sieben Tagen von unseren Funktionen für spoof intelligence betroffen waren. </span><span class="sxs-lookup"><span data-stu-id="ffc27-208">**What if mode**: If spoof intelligence is disabled, then the insight shows you how many messages *would* have been impacted by our spoof intelligence capabilities over the past seven days.</span></span>

   <span data-ttu-id="ffc27-209">So oder so sind die spoofierten Domänen, die in der Einsicht angezeigt werden, in zwei Kategorien unterteilt: Verdächtige **Domänen** und **Nicht verdächtige Domänen.**</span><span class="sxs-lookup"><span data-stu-id="ffc27-209">Either way, the spoofed domains displayed in the insight are separated into two categories: **Suspicious domains** and **Non-suspicious domains**.</span></span>

   - <span data-ttu-id="ffc27-210">**Verdächtige Domänen**:</span><span class="sxs-lookup"><span data-stu-id="ffc27-210">**Suspicious domains**:</span></span>
     - <span data-ttu-id="ffc27-211">**Spoofing** mit hoher Vertrauenswürdigkeit: Basierend auf den historischen Sendemustern und der Reputationsnote der Domänen sind wir sehr sicher, dass die Domänen Spoofing sind, und Nachrichten von diesen Domänen sind mit hoher Wahrscheinlichkeit schädlich.</span><span class="sxs-lookup"><span data-stu-id="ffc27-211">**High-confidence spoof**: Based on the historical sending patterns and the reputation score of the domains, we're highly confident that the domains are spoofing, and messages from these domains are more likely to be malicious.</span></span>
     - <span data-ttu-id="ffc27-212">**Moderater** Konfidenzs spoof : Basierend auf historischen Sendemustern und der Reputationsnote der Domänen sind wir moderat davon überzeugt, dass die Domänen spoofing sind und dass nachrichten, die von diesen Domänen gesendet werden, legitim sind.</span><span class="sxs-lookup"><span data-stu-id="ffc27-212">**Moderate confidence spoof**: Based on historical sending patterns and the reputation score of the domains, we're moderately confident that the domains are spoofing, and that messages sent from these domains are legitimate.</span></span> <span data-ttu-id="ffc27-213">Falsch positive Ergebnisse sind in dieser Kategorie wahrscheinlicher als spoof mit hoher Wahrscheinlichkeit.</span><span class="sxs-lookup"><span data-stu-id="ffc27-213">False positives are more likely in this category than high-confidence spoof.</span></span>
   - <span data-ttu-id="ffc27-214">**Nicht verdächtige Domänen:** Die explizite E-Mail-Authentifizierung der Domäne hat [SPF,](how-office-365-uses-spf-to-prevent-spoofing.md) [DKIM](use-dkim-to-validate-outbound-email.md)und [DMARC nicht überprüft.](use-dmarc-to-validate-email.md)</span><span class="sxs-lookup"><span data-stu-id="ffc27-214">**Non-suspicious domains**: The domain failed explicit email authentication checks [SPF](how-office-365-uses-spf-to-prevent-spoofing.md), [DKIM](use-dkim-to-validate-outbound-email.md), and [DMARC](use-dmarc-to-validate-email.md)).</span></span> <span data-ttu-id="ffc27-215">Die Domäne hat jedoch unsere impliziten E-Mail-Authentifizierungsprüfungen ([zusammengesetzte Authentifizierung](email-validation-and-authentication.md#composite-authentication)) bestanden.</span><span class="sxs-lookup"><span data-stu-id="ffc27-215">However, the domain passed our implicit email authentication checks ([composite authentication](email-validation-and-authentication.md#composite-authentication)).</span></span> <span data-ttu-id="ffc27-216">Aus diesem Grund wurde keine Antis spoofing-Aktion für die Nachricht ergriffen.</span><span class="sxs-lookup"><span data-stu-id="ffc27-216">As a result, no anti-spoofing action was taken on the message.</span></span>

#### <a name="view-detailed-information-about-suspicious-and-nonsuspicious-domains"></a><span data-ttu-id="ffc27-217">Anzeigen detaillierter Informationen zu verdächtigen und nicht unauffälligen Domänen</span><span class="sxs-lookup"><span data-stu-id="ffc27-217">View detailed information about suspicious and nonsuspicious domains</span></span>

1. <span data-ttu-id="ffc27-218">Klicken Sie auf der Einblicksseite  spoof intelligence auf Verdächtige **Domänen** oder nicht verdächtige Domänen, um zur **Seite Spoof Intelligence Insight zu** wechseln.</span><span class="sxs-lookup"><span data-stu-id="ffc27-218">On the Spoof intelligence insight, click **Suspicious domains** or **Non-suspicious domains** to go to the **Spoof intelligence insight** page.</span></span> <span data-ttu-id="ffc27-219">Die **Seite Spoof Intelligence Insight** enthält die folgenden Informationen:</span><span class="sxs-lookup"><span data-stu-id="ffc27-219">The **Spoof Intelligence insight** page contains the following information:</span></span>

   - <span data-ttu-id="ffc27-220">**Spoofed domain:** Die Domäne des spoofierten Benutzers, die im Feld **Von** in E-Mail-Clients angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="ffc27-220">**Spoofed domain**: The domain of the spoofed user that's displayed in the **From** box in email clients.</span></span> <span data-ttu-id="ffc27-221">Diese Adresse wird auch als Adresse `5322.From` bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="ffc27-221">This address is also known as the `5322.From` address.</span></span>
   - <span data-ttu-id="ffc27-222">**Infrastruktur**: Wird auch als sendende _Infrastruktur bezeichnet._</span><span class="sxs-lookup"><span data-stu-id="ffc27-222">**Infrastructure**: Also known as the _sending infrastructure_.</span></span> <span data-ttu-id="ffc27-223">Die Domäne in einer Reverse-DNS-Suche (PTR-Eintrag) der IP-Adresse des Quell-E-Mail-Servers.</span><span class="sxs-lookup"><span data-stu-id="ffc27-223">The domain found in a reverse DNS lookup (PTR record) of the source email server's IP address.</span></span> <span data-ttu-id="ffc27-224">Wenn die Quell-IP-Adresse keinen PTR-Eintrag enthält, wird die sendende Infrastruktur als \<source IP\> /24 identifiziert (z. B. 192.168.100.100/24).</span><span class="sxs-lookup"><span data-stu-id="ffc27-224">If the source IP address has no PTR record, then the sending infrastructure is identified as \<source IP\>/24 (for example, 192.168.100.100/24).</span></span>
   - <span data-ttu-id="ffc27-225">**Nachrichtenanzahl**: Die Anzahl der Nachrichten aus der sendenden Infrastruktur an Ihre Organisation, die die angegebene spoofed-Domäne innerhalb der letzten 7 Tage enthalten.</span><span class="sxs-lookup"><span data-stu-id="ffc27-225">**Message count**: The number of messages from the sending infrastructure to your organization that contain the specified spoofed domain within the last 7 days.</span></span>
   - <span data-ttu-id="ffc27-226">**Zuletzt gesehen:** Das letzte Datum, an dem eine Nachricht von der sendenden Infrastruktur empfangen wurde, die die spoofierte Domäne enthält.</span><span class="sxs-lookup"><span data-stu-id="ffc27-226">**Last seen**: The last date when a message was received from the sending infrastructure that contains the spoofed domain.</span></span>
   - <span data-ttu-id="ffc27-227">**Spooftyp**: Dieser Wert ist **External**.</span><span class="sxs-lookup"><span data-stu-id="ffc27-227">**Spoof type**: This value is **External**.</span></span>
   - <span data-ttu-id="ffc27-228">**Darf ges spooft werden?**: Die hier angezeigten Werte sind:</span><span class="sxs-lookup"><span data-stu-id="ffc27-228">**Allowed to spoof?**: The values that you see here are:</span></span>
     - <span data-ttu-id="ffc27-229">**Ja:** Nachrichten aus der Kombination aus der Domäne des spoofierten Benutzers und der Sendeinfrastruktur sind zulässig und werden nicht als gefälschte E-Mails behandelt.</span><span class="sxs-lookup"><span data-stu-id="ffc27-229">**Yes**: Messages from the combination of spoofed user's domain and sending infrastructure are allowed and not treated as spoofed email.</span></span>
     - <span data-ttu-id="ffc27-230">**Nein:** Nachrichten aus der Kombination aus der Domäne des spoofierten Benutzers und der sendenden Infrastruktur werden als Spoofing gekennzeichnet.</span><span class="sxs-lookup"><span data-stu-id="ffc27-230">**No**: Messages from the combination of spoofed user's domain and sending infrastructure are marked as spoofed.</span></span> <span data-ttu-id="ffc27-231">Die Aktion wird durch die standardmäßige Antiphishingrichtlinie oder benutzerdefinierte Antiphishingrichtlinien gesteuert (der Standardwert ist **Move message to Junk Email folder**).</span><span class="sxs-lookup"><span data-stu-id="ffc27-231">The action is controlled by the default anti-phishing policy or custom anti-phishing policies (the default value is **Move message to Junk Email folder**).</span></span>

2. <span data-ttu-id="ffc27-232">Wählen Sie ein Element in der Liste aus, um Details zum Domänen-/Sendeinfrastrukturpaar in einem Flyout anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="ffc27-232">Select an item in the list to view details about the domain/sending infrastructure pair in a flyout.</span></span> <span data-ttu-id="ffc27-233">Die Informationen umfassen:</span><span class="sxs-lookup"><span data-stu-id="ffc27-233">The information includes:</span></span>
   - <span data-ttu-id="ffc27-234">Warum wir dies erwischt haben.</span><span class="sxs-lookup"><span data-stu-id="ffc27-234">Why we caught this.</span></span>
   - <span data-ttu-id="ffc27-235">Was Sie tun müssen.</span><span class="sxs-lookup"><span data-stu-id="ffc27-235">What you need to do.</span></span>
   - <span data-ttu-id="ffc27-236">Eine Domänenzusammenfassung.</span><span class="sxs-lookup"><span data-stu-id="ffc27-236">A domain summary.</span></span>
   - <span data-ttu-id="ffc27-237">WhoIs-Daten über den Absender.</span><span class="sxs-lookup"><span data-stu-id="ffc27-237">WhoIs data about the sender.</span></span>
   - <span data-ttu-id="ffc27-238">Ähnliche Nachrichten, die wir in Ihrem Mandanten vom gleichen Absender gesehen haben.</span><span class="sxs-lookup"><span data-stu-id="ffc27-238">Similar messages we have seen in your tenant from the same sender.</span></span>

   <span data-ttu-id="ffc27-239">Von hier aus können Sie auch das Domänen-/Sendeinfrastrukturpaar aus der Liste zugelassener Absender **spoofieren** hinzufügen oder entfernen.</span><span class="sxs-lookup"><span data-stu-id="ffc27-239">From here, you can also choose to add or remove the domain/sending infrastructure pair from the **Allowed to spoof** sender allow list.</span></span> <span data-ttu-id="ffc27-240">Legen Sie einfach die Umschalte entsprechend ein.</span><span class="sxs-lookup"><span data-stu-id="ffc27-240">Simply set the toggle accordingly.</span></span>

   ![Screenshot einer Domäne im Detailbereich "Spoof Intelligence Insight"](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

## <a name="how-do-you-know-these-procedures-worked"></a><span data-ttu-id="ffc27-242">Wie können Sie feststellen, dass diese Verfahren erfolgreich waren?</span><span class="sxs-lookup"><span data-stu-id="ffc27-242">How do you know these procedures worked?</span></span>

<span data-ttu-id="ffc27-243">Verwenden Sie einen der folgenden Schritte, um sicherzustellen, dass Sie spoof intelligence mit Absendern konfiguriert haben, die spoofen dürfen und nicht spoofen dürfen:</span><span class="sxs-lookup"><span data-stu-id="ffc27-243">To verify that you've configured spoof intelligence with senders who are allowed and not allowed to spoof, use any of the following steps:</span></span>

- <span data-ttu-id="ffc27-244">Wechseln Sie im Security & Compliance  Center zu Bedrohungsverwaltungsrichtlinie \>  \> **Antispam** erweitern \> **Spoof Intelligence Policy** select Show me \> **senders I already reviewed** select the Your \> **Domains** or **External Domains,** and verify the **Allowed to spoof?** value for the sender.</span><span class="sxs-lookup"><span data-stu-id="ffc27-244">In the Security & Compliance Center, go to **Threat management** \> **Policy** \> **Anti-spam** \> expand **Spoof intelligence policy** \> select **Show me senders I already reviewed** \> select the **Your Domains** or **External Domains** tab, and verify the **Allowed to spoof?** value for the sender.</span></span>

- <span data-ttu-id="ffc27-245">Führen Sie in PowerShell die folgenden Befehle aus, um die Absender anzuzeigen, die spoofen dürfen und nicht dürfen:</span><span class="sxs-lookup"><span data-stu-id="ffc27-245">In PowerShell, run the following commands to view the senders who are allowed and not allowed to spoof:</span></span>

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- <span data-ttu-id="ffc27-246">Führen Sie in PowerShell den folgenden Befehl aus, um die Liste aller gefälschten Absender in eine CSV-Datei zu exportieren:</span><span class="sxs-lookup"><span data-stu-id="ffc27-246">In PowerShell, run the following command to export the list of all spoofed senders to a CSV file:</span></span>

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```
