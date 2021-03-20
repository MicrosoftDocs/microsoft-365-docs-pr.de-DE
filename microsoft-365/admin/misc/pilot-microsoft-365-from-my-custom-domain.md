---
title: Testen von Microsoft 365 aus Ihrer benutzerdefinierten Domäne
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie die E-Mail-Funktionalität aus Ihrer benutzerdefinierten Domäne an ein Microsoft 365-Postfach mit nur zwei Testkonten testen können.
ms.openlocfilehash: 019f1786756a036132f95fd5e8ef8a1d42cd515b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914714"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a><span data-ttu-id="c620b-103">Testen von Microsoft 365 aus Ihrer benutzerdefinierten Domäne</span><span class="sxs-lookup"><span data-stu-id="c620b-103">Pilot Microsoft 365 from my custom domain</span></span>

<span data-ttu-id="c620b-104">Sie können Microsoft 365 mit den folgenden Anforderungen und Einschränkungen testen:</span><span class="sxs-lookup"><span data-stu-id="c620b-104">You can pilot Microsoft 365 with these requirements and limitations:</span></span>

- <span data-ttu-id="c620b-105">Ihr aktueller E-Mail-Anbieter muss E-Mail-Weiterleitung unterstützen.</span><span class="sxs-lookup"><span data-stu-id="c620b-105">Your current email provider must provide email forwarding.</span></span>

- <span data-ttu-id="c620b-106">Sie müssen Ihre Microsoft 365-DNS-Einträge bei Ihrem DNS-Hostinganbieter verwalten, statt diese Einträge von Microsoft 365 verwalten zu lassen.</span><span class="sxs-lookup"><span data-stu-id="c620b-106">You must manage your Microsoft 365 DNS records at your DNS hosting provider, rather than have Microsoft 365 manage these records for you.</span></span>

    <span data-ttu-id="c620b-107">Weitere Informationen finden Sie unter [Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c620b-107">To learn more, see [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

- <span data-ttu-id="c620b-108">Frei/Gebucht-Informationen für Benutzer auf dem anderen E-Mail-Server stehen nicht zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="c620b-108">Free/busy information for users on the other email server is not available.</span></span>

- <span data-ttu-id="c620b-109">Administratoren können nicht alle Benutzerkonten von einem einzigen Standort aus verwalten.</span><span class="sxs-lookup"><span data-stu-id="c620b-109">Admins can't administer all user accounts from a single location.</span></span>

- <span data-ttu-id="c620b-110">Möglicherweise sind die Benutzer nicht in der Lage, Microsoft 365-Spamfilter zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="c620b-110">Users might not be able to use Microsoft 365 spam filtering.</span></span>

- <span data-ttu-id="c620b-111">Dies wird für eine sehr kleine Anzahl von Benutzern empfohlen und gilt nur für die Verwendung von E-Mails für ein Pilotprojekt.</span><span class="sxs-lookup"><span data-stu-id="c620b-111">This is recommended for a very small number of users and only applies to the use of email for a pilot.</span></span>

## <a name="set-up-a-microsoft-365-pilot"></a><span data-ttu-id="c620b-112">Einrichten eines Microsoft 365-Pilotprojekts</span><span class="sxs-lookup"><span data-stu-id="c620b-112">Set up a Microsoft 365 pilot</span></span>

<span data-ttu-id="c620b-113">Führen Sie die folgenden Schritte aus, um ein Microsoft 365-Pilotprojekt einzurichten:</span><span class="sxs-lookup"><span data-stu-id="c620b-113">Follow these steps to set up a Microsoft 365 pilot:</span></span>

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a><span data-ttu-id="c620b-114">Schritt 1: Anmelden beim Microsoft 365 Admin Center</span><span class="sxs-lookup"><span data-stu-id="c620b-114">Step 1: Sign in to the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="c620b-115">Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.</span><span class="sxs-lookup"><span data-stu-id="c620b-115">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your work or school account.</span></span>

2. <span data-ttu-id="c620b-116">Wählen Sie im linken Navigationsbereich **Einstellungen** > **Domänen** aus.</span><span class="sxs-lookup"><span data-stu-id="c620b-116">Select **Settings** > **Domains** in the left navigation pane.</span></span>

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a><span data-ttu-id="c620b-117">Schritt 2: Überprüfung, ob Sie die gewünschte Domäne besitzen</span><span class="sxs-lookup"><span data-stu-id="c620b-117">Step 2: Verify that you own the domain you want to use</span></span>

1. <span data-ttu-id="c620b-118">Klicken Sie auf der Seite **Domänen** auf **Domäne hinzufügen**.</span><span class="sxs-lookup"><span data-stu-id="c620b-118">On the **Domains** page, select **Add domain**.</span></span>

2. <span data-ttu-id="c620b-119">Geben Sie den Domänennamen in das Feld ein, wählen Sie **Diese Domäne verwenden** aus, und wählen Sie dann **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c620b-119">Type the domain name in the box, select **Use this domain**, and then select **Continue**.</span></span>

3. <span data-ttu-id="c620b-120">Wählen Sie die Dienste aus, die Sie mit Ihrer Domäne testen möchten, z. B. E-Mail und Chat.</span><span class="sxs-lookup"><span data-stu-id="c620b-120">Select the services you want to test with your domain, like email and instant messaging.</span></span>

5. <span data-ttu-id="c620b-121">Befolgen Sie auf der Seite **Domäne überprüfen** die schrittweisen Anleitungen, und wählen Sie dann **Überprüfen**.</span><span class="sxs-lookup"><span data-stu-id="c620b-121">On the **Verify** domain page, follow the step-by-step instructions, amd then select **Verify**.</span></span>

    <span data-ttu-id="c620b-122">Es kann zwischen einigen Minuten und 72 Stunden dauern, bis DNS-Änderungen wirksam werden.</span><span class="sxs-lookup"><span data-stu-id="c620b-122">It takes between a few minutes and 72 hours for DNS changes to take effect.</span></span>

    <span data-ttu-id="c620b-123">Wenn die Überprüfung erfolgreich ist, werden Sie aufgefordert, Ihre DNS-Einträge zu ändern.</span><span class="sxs-lookup"><span data-stu-id="c620b-123">When verification is successful, you are asked to modify your DNS records.</span></span>

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a><span data-ttu-id="c620b-124">Schritt 3: Kennzeichnen der Domäne als freigegeben in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="c620b-124">Step 3: Mark the domain as shared in Exchange Online</span></span>

1. <span data-ttu-id="c620b-125">Wählen Sie im Exchange Admin Center im Abschnitt **Nachrichtenfluss** die Option **Akzeptierte Domänen** aus, und wählen Sie dann die Domäne aus, die Sie ändern möchten.</span><span class="sxs-lookup"><span data-stu-id="c620b-125">In the Exchange admin center, in the **Mail flow** section, select **Accepted domains**, and then select the domain you want to modify.</span></span>

2. <span data-ttu-id="c620b-126">Doppelklicken Sie, um das Fenster zu öffnen, und wählen Sie dann **Internes Relay** aus.</span><span class="sxs-lookup"><span data-stu-id="c620b-126">Double-click to open the window, and then select **Internal Relay**.</span></span> 

3. <span data-ttu-id="c620b-127">Wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="c620b-127">Select **Save**.</span></span>

    <span data-ttu-id="c620b-128">Diese Einstellung wird möglicherweise erst nach einigen Minuten wirksam.</span><span class="sxs-lookup"><span data-stu-id="c620b-128">This setting might require a few minutes to take effect.</span></span>

### <a name="step-4-unblock-the-existing-email-server-optional"></a><span data-ttu-id="c620b-129">Schritt 4: Entsperren des vorhandenen Mailservers (optional)</span><span class="sxs-lookup"><span data-stu-id="c620b-129">Step 4: Unblock the existing email server (optional)</span></span>

<span data-ttu-id="c620b-130">Microsoft 365 verwendet Exchange Online Protection (EOP) zum Schutz vor Spam.</span><span class="sxs-lookup"><span data-stu-id="c620b-130">Microsoft 365 uses Exchange Online Protection (EOP) for spam protection.</span></span> <span data-ttu-id="c620b-131">EOP blockiert möglicherweise Ihren vorhandenen E-Mail-Server, wenn ein hohes Spamaufkommen erkannt wird, das von Ihrem aktuellen E-Mail-Server weitergeleitet wird.</span><span class="sxs-lookup"><span data-stu-id="c620b-131">EOP might block your existing mail server if it detects a high volume of spam being forwarded by your current mail server.</span></span> <span data-ttu-id="c620b-132">Wenn Sie den Spamschutz für Ihren anderen E-Mail-Anbieter als vertrauenswürdig einstufen, können Sie die Blockierung des Servers in Microsoft 365 aufheben.</span><span class="sxs-lookup"><span data-stu-id="c620b-132">If you trust the spam protection for your other email provider, you can unblock the server in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="c620b-133">Wenn Sie die Blockierung des vorhandenen E-Mail-Servers aufheben, können alle Spamnachrichten, die über den ursprünglichen Server eintreffen, an die Microsoft 365-Postfächer übermittelt werden, und Sie können den Spamschutz durch Microsoft 365 nicht auswerten.</span><span class="sxs-lookup"><span data-stu-id="c620b-133">Unblocking your existing email server allows any spam that arrives through your original server to come to the Microsoft 365 mailboxes, and you can’t evaluate how well Microsoft 365 prevents spam.</span></span>

1. <span data-ttu-id="c620b-134">Wählen Sie im Navigationsbereich des Exchange Admin Centers **Schutz** aus, und wählen Sie dann **Verbindungsfilter** aus.</span><span class="sxs-lookup"><span data-stu-id="c620b-134">In the Exchange admin center navigation pane, select **Protection**, and then select **Connection filter**.</span></span>

2. <span data-ttu-id="c620b-135">Wählen Sie in der **IP-Zulassungsliste** den Eintrag **+** aus, und fügen Sie die IP-Adresse des Mailservers für Ihren aktuellen E-Mail-Anbieter hinzu.</span><span class="sxs-lookup"><span data-stu-id="c620b-135">In the **IP Allow list**, select **+**, and add the mail server IP address for your current email provider.</span></span> 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a><span data-ttu-id="c620b-136">Schritt 5: Erstellen von Benutzerkonten und Festlegen der primären Antwortadresse</span><span class="sxs-lookup"><span data-stu-id="c620b-136">Step 5: Create user accounts and set the primary reply-to address</span></span>

1. <span data-ttu-id="c620b-137">Wählen Sie linken Navigationsbereich des Microsoft 365 Admin Centers **Benutzer** > **Aktive Benutzer** aus.</span><span class="sxs-lookup"><span data-stu-id="c620b-137">In the Microsoft 365 admin center left navigation, select **Users** > **Active Users**.</span></span>

2. <span data-ttu-id="c620b-138">Erstellen Sie zwei Testkonten, indem Sie zwei vorhandene Benutzer hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="c620b-138">Create two test accounts by adding two existing users.</span></span>

    <span data-ttu-id="c620b-139">Wählen Sie für jedes Konto **+ Benutzer hinzufügen** aus, und geben Sie die erforderlichen Informationen ein, einschließlich der Kennwortmethode, die Sie testen möchten.</span><span class="sxs-lookup"><span data-stu-id="c620b-139">For each account, select **+ Add a user**, and fill out the required information, including the password method you want to test.</span></span>

    <span data-ttu-id="c620b-140">Um sicherzustellen, dass die E-Mail eines Benutzers unverändert bleibt, muss das Feld **Benutzername** der aktuellen E-Mail-Adresse des Benutzers entsprechen.</span><span class="sxs-lookup"><span data-stu-id="c620b-140">To ensure a user’s email stays the same, the **User name** field must match the user’s current email address.</span></span>

3. <span data-ttu-id="c620b-141">Wählen Sie die entsprechende Lizenz aus, klicken Sie auf **Weiter**, und klicken Sie dann auf **Hinzufügen fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="c620b-141">Choose the appropriate license, click **Next**, and then click **Finish adding**.</span></span> 

4. <span data-ttu-id="c620b-142">Wählen Sie neben **Benutzername** Ihren benutzerdefinierten Domänennamen aus der Dropdownliste aus.</span><span class="sxs-lookup"><span data-stu-id="c620b-142">Next to **User name**, select your custom domain name from the drop-down list.</span></span> 

5. <span data-ttu-id="c620b-143">Wählen Sie **Erstellen** > **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="c620b-143">Select **Create** > **Close**.</span></span>

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a><span data-ttu-id="c620b-144">Teil 6: \*\*Konfigurieren von E-Mails für den Fluss von Microsoft 365 oder Office 365 zum E-Mail-Server</span><span class="sxs-lookup"><span data-stu-id="c620b-144">Step 6: \*\*Configure mail to flow from Microsoft 365 or Office 365 to Email server</span></span>

<span data-ttu-id="c620b-145">Dafür sind zwei Schritte nötig:</span><span class="sxs-lookup"><span data-stu-id="c620b-145">There are two steps for this:</span></span>

1. <span data-ttu-id="c620b-146">Konfigurieren Ihrer Microsoft 365- oder Office 365-Umgebung.</span><span class="sxs-lookup"><span data-stu-id="c620b-146">Configure your Microsoft 365 or Office 365 environment.</span></span>

2. <span data-ttu-id="c620b-147">Einrichten eines Connectors von Microsoft 365 oder Office 365 zu Ihrem E-Mail-Server.</span><span class="sxs-lookup"><span data-stu-id="c620b-147">Set up a connector from Microsoft 365 or Office 365 to your email server.</span></span>

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a><span data-ttu-id="c620b-148">1. Konfigurieren Ihrer Microsoft 365- oder Office 365-Umgebung</span><span class="sxs-lookup"><span data-stu-id="c620b-148">1. Configure your Microsoft 365 or Office 365 environment</span></span>

<span data-ttu-id="c620b-149">Stellen Sie sicher, dass Sie Folgendes in Microsoft 365 oder Office 365 erledigt haben:</span><span class="sxs-lookup"><span data-stu-id="c620b-149">Make sure you have completed the following in Microsoft 365 or Office 365:</span></span>

1. <span data-ttu-id="c620b-150">Zum Einrichten von Connectors benötigen Sie Ihnen zugewiesene Berechtigungen, bevor Sie beginnen können.</span><span class="sxs-lookup"><span data-stu-id="c620b-150">To set up connectors, you need permissions assigned before you can begin.</span></span> <span data-ttu-id="c620b-151">Welche Berechtigungen Sie benötigen, können Sie dem Eintrag "Microsoft 365- und Office 365-Connectors" im Thema [Featureberechtigungen in EOP](../../security/office-365-security/feature-permissions-in-eop.md) entnehmen.</span><span class="sxs-lookup"><span data-stu-id="c620b-151">To check what permissions you need, see the Microsoft 365 and Office 365 connectors entry in the [Feature permissions in EOP](../../security/office-365-security/feature-permissions-in-eop.md) topic.</span></span>

2. <span data-ttu-id="c620b-152">Wenn Sie möchten, dass EOP oder Exchange Online E-Mails von Ihren E-Mail-Servern an das Internet weiterleitet, gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="c620b-152">If you want EOP or Exchange Online to relay email from your email servers to the Internet, either:</span></span>

   - <span data-ttu-id="c620b-153">Verwenden Sie ein Zertifikat, das mit einem Antragstellernamen konfiguriert ist, der einer akzeptierte Domäne in Microsoft 365 oder Office 365 entspricht.</span><span class="sxs-lookup"><span data-stu-id="c620b-153">Use a certificate configured with a subject name that matches an accepted domain in Microsoft 365 or Office 365.</span></span> <span data-ttu-id="c620b-154">Es wird empfohlen, dass der allgemeine Name des Zertifikats oder der alternative Antragstellername mit der primären SMTP-Domäne für Ihre Organisation übereinstimmt.</span><span class="sxs-lookup"><span data-stu-id="c620b-154">We recommend that your certificate's common name or subject alternative name matches the primary SMTP domain for your organization.</span></span> <span data-ttu-id="c620b-155">Ausführliche Informationen finden Sie unter [Voraussetzungen für Ihre lokale E-Mail-Umgebung](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span><span class="sxs-lookup"><span data-stu-id="c620b-155">For details, see [Prerequisites for your on-premises email environment](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).</span></span>

   <span data-ttu-id="c620b-156">– ODER –</span><span class="sxs-lookup"><span data-stu-id="c620b-156">-OR-</span></span>

   - <span data-ttu-id="c620b-157">Stellen Sie sicher, dass alle Absenderdomänen und -unterdomänen in Ihrer Organisation in Microsoft 365 oder Office 365 als akzeptierte Domänen konfiguriert sind.</span><span class="sxs-lookup"><span data-stu-id="c620b-157">Make sure that all your organization sender domains and subdomains are configured as accepted domains in Microsoft 365 or Office 365.</span></span>

   <span data-ttu-id="c620b-158">Weitere Informationen zum Definieren von akzeptierten Domänen finden Sie unter [Verwalten von akzeptierten Domänen in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) und [Aktivieren des Nachrichtenflusses für Unterdomänen in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span><span class="sxs-lookup"><span data-stu-id="c620b-158">For more information about defining accepted domains, see [Manage accepted domains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) and [Enable mail flow for subdomains in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).</span></span>

3. <span data-ttu-id="c620b-159">Entscheiden Sie, ob Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) oder Domänennamen verwenden möchten, um E-Mails von Microsoft 365 oder Office 365 an Ihre E-Mail-Server zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="c620b-159">Decide whether you want to use mail flow rules (also known as transport rules) or domain names to deliver mail from Microsoft 365 or Office 365 to your email servers.</span></span> <span data-ttu-id="c620b-160">Die meisten Unternehmen entscheiden sich dafür, E-Mails für alle akzeptierten Domänen zu übermitteln.</span><span class="sxs-lookup"><span data-stu-id="c620b-160">Most businesses choose to deliver mail for all accepted domains.</span></span> <span data-ttu-id="c620b-161">Weitere Informationen finden Sie unter [Szenario: Bedingtes E-Mail-Routing in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span><span class="sxs-lookup"><span data-stu-id="c620b-161">For more information, see [Scenario: Conditional mail routing in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).</span></span>

> [!NOTE]
> <span data-ttu-id="c620b-162">Sie können Nachrichtenflussregel einrichten, wie in [Aktionen für die Nachrichtenflussregel in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) beschrieben.</span><span class="sxs-lookup"><span data-stu-id="c620b-162">You can set up mail flow rules as described in [Mail flow rule actions in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).</span></span> <span data-ttu-id="c620b-163">Beispielsweise möchten Sie Nachrichtenflussregeln möglicherweise mit Connectors verwenden, wenn Ihre E-Mails zurzeit über Verteilerlisten an mehrere Standorte weitergeleitet werden.</span><span class="sxs-lookup"><span data-stu-id="c620b-163">For example, you might want to use mail flow rules with connectors if your mail is currently directed via distribution lists to multiple sites.</span></span>

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a><span data-ttu-id="c620b-164">2. Einrichten eines Connectors von Microsoft 365 oder Office 365 zu Ihrem E-Mail-Server</span><span class="sxs-lookup"><span data-stu-id="c620b-164">2. Set up a connector from Microsoft 365 or Office 365 to your email server</span></span>

<span data-ttu-id="c620b-165">Um in Microsoft 365 oder Office 365 einen Connector zu erstellen, wählen Sie **Administrator** aus, und klicken Sie dann auf **Exchange**, um zum Exchange-Verwaltungskonsole zu gelangen.</span><span class="sxs-lookup"><span data-stu-id="c620b-165">To create a connector in Microsoft 365 or Office 365, click **Admin**, and then click **Exchange** to go to the Exchange admin center.</span></span> <span data-ttu-id="c620b-166">Klicken Sie dann auf **Nachrichtenfluss** und auf **Connectors**.</span><span class="sxs-lookup"><span data-stu-id="c620b-166">Next, click **mail flow**, and click **connectors**.</span></span>

<span data-ttu-id="c620b-167">Einrichten von Connectors mithilfe des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="c620b-167">Set up connectors using the wizard.</span></span>

<span data-ttu-id="c620b-168">Klicken Sie zum Starten des Assistenten auf das Pluszeichen **+**.</span><span class="sxs-lookup"><span data-stu-id="c620b-168">To start the wizard, click the plus symbol **+**.</span></span> <span data-ttu-id="c620b-169">Wählen Sie auf dem ersten Bildschirm **Von** Office 365 und **An** den E-Mail-Server Ihrer Organisation aus.</span><span class="sxs-lookup"><span data-stu-id="c620b-169">On the first screen, choose **From** Office 365 and **To** Your Organization Mail server.</span></span>

<span data-ttu-id="c620b-170">Klicken Sie auf **Weiter**, und befolgen Sie die Anweisungen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="c620b-170">Click **Next**, and follow the instructions in the wizard.</span></span> <span data-ttu-id="c620b-171">Klicken Sie auf die Links **Hilfe** oder **Weitere Informationen**, wenn Sie weitere Informationen benötigen.</span><span class="sxs-lookup"><span data-stu-id="c620b-171">Click the **Help** or **Learn More** links if you need more information.</span></span> <span data-ttu-id="c620b-172">Der Assistent führt Sie durch das Setup.</span><span class="sxs-lookup"><span data-stu-id="c620b-172">The wizard will guide you through setup.</span></span> <span data-ttu-id="c620b-173">Stellen Sie am Ende sicher, dass Ihr Connector eine Bestätigung vornimmt.</span><span class="sxs-lookup"><span data-stu-id="c620b-173">At the end, make sure your connector validates.</span></span> <span data-ttu-id="c620b-174">Wenn der Connector keine Bestätigung vornimmt, doppelklicken Sie auf angezeigte Meldung, um mehr Informationen zu erhalten, und lesen Sie [Validieren von Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors), um Hilfe zur Problembehebung zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="c620b-174">If the connector does not validate, double-click the message displayed to get more information, and see [Validate connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors) for help resolving issues.</span></span>



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a><span data-ttu-id="c620b-175">Schritt 7: Aktualisieren der DNS-Einträge bei Ihrem DNS-Hostinganbieter</span><span class="sxs-lookup"><span data-stu-id="c620b-175">Step 7: Update DNS records at your DNS hosting provider</span></span>

<span data-ttu-id="c620b-176">Melden Sie sich bei der Website Ihres DNS-Hostinganbieters an, und folgen Sie den Anweisungen unter [Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span><span class="sxs-lookup"><span data-stu-id="c620b-176">Sign in to your DNS hosting provider's website, and follow the instructions at [Add DNS records to connect your domain](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).</span></span>

<span data-ttu-id="c620b-177">**Machen Sie die folgenden beiden Ausnahmen:**</span><span class="sxs-lookup"><span data-stu-id="c620b-177">**Make the following two exceptions:**</span></span>

- <span data-ttu-id="c620b-178">Erstellen Sie keinen neuen MX-Eintrag bzw. ändern Sie Ihren bestehenden MX-Eintrag nicht.</span><span class="sxs-lookup"><span data-stu-id="c620b-178">Do not create a new MX record or change your existing MX record.</span></span>

- <span data-ttu-id="c620b-179">Wenn Sie bereits über einen SPF-Eintrag (Sender Policy Framework) für Ihren bisherigen E-Mail-Anbieter verfügen, erstellen Sie keinen neuen SPF (TXT)-Eintrag für Exchange Online, sondern fügen Sie dem vorhandenen TXT-Eintrag "include:spf.protection.outlook.com" hinzu.</span><span class="sxs-lookup"><span data-stu-id="c620b-179">If you already have a Sender Policy Framework (SPF) record for your previous email provider, instead of creating a new SPF (TXT) record for Exchange Online, add "include:spf.protection.outlook.com" to the current TXT record.</span></span>

    <span data-ttu-id="c620b-180">Beispiel: "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all"</span><span class="sxs-lookup"><span data-stu-id="c620b-180">For example, "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all".</span></span>

    <span data-ttu-id="c620b-181">Wenn Sie nicht über einen SPF-Eintrag verfügen, ändern Sie den von Microsoft 365 empfohlenen so, dass er die Domäne für Ihren aktuellen E-Mail-Anbieter einschließt, und fügen Sie "spf.protection.outlook.com" hinzu.</span><span class="sxs-lookup"><span data-stu-id="c620b-181">If you don't have an SPF record, modify the one recommended by Microsoft 365 to include the domain for your current email provider, and add spf.protection.outlook.com.</span></span> <span data-ttu-id="c620b-182">Dadurch werden ausgehende Nachrichten von beiden E-Mail-Systemen autorisiert.</span><span class="sxs-lookup"><span data-stu-id="c620b-182">This authorizes outgoing messages from both email systems.</span></span>

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a><span data-ttu-id="c620b-183">Schritt 8: Einrichten von E-Mail-Weiterleitung bei Ihrem aktuellen Anbieter</span><span class="sxs-lookup"><span data-stu-id="c620b-183">Step 8: Set up email forwarding at your current provider</span></span>

<span data-ttu-id="c620b-184">Richten Sie bei Ihrem aktuellen E-Mail-Anbieter Weiterleitung für die E-Mail-Konten Ihrer Benutzer an Ihre onmicrosoft.com-Domäne ein:</span><span class="sxs-lookup"><span data-stu-id="c620b-184">At your current email provider, set up forwarding for your users email accounts to your onmicrosoft.com domain:</span></span>

- <span data-ttu-id="c620b-185">Leiten Sie das Postfach des Benutzers A an usera@yourcompany.onmicrosoft.com weiter.</span><span class="sxs-lookup"><span data-stu-id="c620b-185">Forward User A mailbox to usera@yourcompany.onmicrosoft.com</span></span>

- <span data-ttu-id="c620b-186">Leiten Sie das Postfach des Benutzers B an userb@yourcompany.onmicrosoft.com weiter.</span><span class="sxs-lookup"><span data-stu-id="c620b-186">Forward User B mailbox to userb@yourcompany.onmicrosoft.com</span></span>

<span data-ttu-id="c620b-187">Nachdem Sie diesen Schritt ausgeführt haben, sind alle an usera@yourcompany.com und userb@yourcompany.com gesendeten E-Mails in Microsoft 365 verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c620b-187">When you complete this step, all email sent to usera@yourcompany.com and userb@yourcompany.com is available in Microsoft 365.</span></span>

> [!NOTE]
> <span data-ttu-id="c620b-188">Wenden Sie sich an Ihren derzeitigen E-Mail-Anbieter, um die genauen Schritte für das Einrichten der E-Mail-Weiterleitung zu erfragen.</span><span class="sxs-lookup"><span data-stu-id="c620b-188">Contact your current email provider for the exact steps to set up email forwarding.</span></span><br/>
> <span data-ttu-id="c620b-189">Sie brauchen keine Kopie von Nachrichten beim aktuellen E-Mail-Anbieter zu behalten.</span><span class="sxs-lookup"><span data-stu-id="c620b-189">You don't need to keep a copy of messages at the current email provider.</span></span><br/>
> <span data-ttu-id="c620b-190">Die meisten Anbieter leiten E-Mail so weiter, dass die Antwortadresse des Absenders erhalten bleibt, sodass Antworten an den ursprünglichen Absender gehen.</span><span class="sxs-lookup"><span data-stu-id="c620b-190">Most providers forward email by leaving the Reply-to address of the sender intact so that replies go to the original sender.</span></span>

### <a name="step-9-test-mail-flow"></a><span data-ttu-id="c620b-191">Schritt 9: Testen des Nachrichtenflusses</span><span class="sxs-lookup"><span data-stu-id="c620b-191">Step 9: Test mail flow</span></span>

1. <span data-ttu-id="c620b-192">Melden Sie sich mit den Anmeldeinformationen für Benutzer A bei Outlook Web App an.</span><span class="sxs-lookup"><span data-stu-id="c620b-192">Sign in to Outlook Web App using the credentials for User A.</span></span>

2. <span data-ttu-id="c620b-193">Führen Sie die folgenden Tests aus:</span><span class="sxs-lookup"><span data-stu-id="c620b-193">Perform these tests:</span></span>

    - <span data-ttu-id="c620b-194">Testen Sie lokale Microsoft-E-Mail, indem Sie eine E-Mail z. B. an Benutzer B senden. Die E-Mail wird sofort zugestellt.</span><span class="sxs-lookup"><span data-stu-id="c620b-194">Test local Microsoft email by sending an email, for example, to User B. The email is delivered immediately.</span></span> <span data-ttu-id="c620b-195">In diesem Szenario wird die Nachricht nicht an das Postfach für Benutzer B auf dem ursprünglichen Server weitergeleitet, da das Microsoft 365-Postfach lokal ist.</span><span class="sxs-lookup"><span data-stu-id="c620b-195">In this scenario, the message is not routed to the mailbox for User B on your original server because the Microsoft 365 mailbox is local.</span></span>

    - <span data-ttu-id="c620b-196">Testen Sie E-Mail an einen Benutzer auf dem vorhandenen E-Mail-System, indem Sie eine E-Mail z. B. an Benutzer C senden. Die E-Mail wird an das Postfach für Benutzer C auf Ihrem ursprünglichen E-Mail-Server übermittelt.</span><span class="sxs-lookup"><span data-stu-id="c620b-196">Test email to a user on the existing email system by sending an email, for example, to User C. The email is delivered to the mailbox for User C on your original mail server.</span></span>

    - <span data-ttu-id="c620b-197">Überprüfen Sie, ob die Weiterleitung von einem externen Konto oder von einem E-Mail-Konto eines Mitarbeiters auf dem vorhandenen E-Mail-System ordnungsgemäß eingerichtet wurde.</span><span class="sxs-lookup"><span data-stu-id="c620b-197">Verify that forwarding is set up properly from an outside account, or from an employee email account on the existing email system.</span></span> <span data-ttu-id="c620b-198">Senden Sie beispielsweise vom ursprünglichen Serverkonto für Benutzer C oder einem Hotmail-Konto eine E-Mail an Benutzer A, und überprüfen Sie, ob sie im Microsoft 365-Postfach für Benutzer A eingetroffen ist.</span><span class="sxs-lookup"><span data-stu-id="c620b-198">For example, from the original server account for User C or a Hotmail account, send User A an email and verify that it arrives in the Microsoft 365 mailbox for User A.</span></span>

### <a name="step-10-move-mailbox-contents"></a><span data-ttu-id="c620b-199">Schritt 10: Verschieben von Postfachinhalten</span><span class="sxs-lookup"><span data-stu-id="c620b-199">Step 10: Move mailbox contents</span></span>

<span data-ttu-id="c620b-200">Da Sie nur zwei Testbenutzer verschieben und Benutzer A und Benutzer B beide Outlook verwenden, können Sie die E-Mail verschieben, indem Sie die alte .PST-Datei im neuen Outlook-Profil öffnen und die Nachrichten, Kalenderelemente, Kontakte usw. kopieren.</span><span class="sxs-lookup"><span data-stu-id="c620b-200">Because you are moving only two test users, and User A and User B are both using Outlook, you can move the email by opening the old .PST file in the new Outlook profile and copying the messages, calendar items, contacts, and so on.</span></span> <span data-ttu-id="c620b-201">Weitere Informationen hierzu finden Sie unter [Importieren von E-Mails, Kontakten und Kalendern aus einer Outlook-PST-Datei](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span><span class="sxs-lookup"><span data-stu-id="c620b-201">For more information, see [Import email, contacts, and calendar from an Outlook .pst file](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).</span></span>

<span data-ttu-id="c620b-202">Nachdem sie in die entsprechenden Speicherorte im Microsoft 365-Postfach importiert wurden, kann auf die Elemente von jedem beliebigen Gerät aus zugegriffen werden.</span><span class="sxs-lookup"><span data-stu-id="c620b-202">After they’re imported to the appropriate locations in the Microsoft 365 mailbox, the items can be accessed from any device, anywhere.</span></span>