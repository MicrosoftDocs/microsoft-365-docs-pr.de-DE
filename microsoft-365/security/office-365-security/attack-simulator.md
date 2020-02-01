---
title: Angriffssimulator in Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
description: Als Office 365 globaler Administrator können Sie mit dem Angriffs Simulator realistische Angriffsszenarien in Ihrer Organisation ausführen. Dies kann Sie dabei unterstützen, gefährdete Benutzer zu identifizieren und zu finden, bevor ein echter Angriff auf Ihr Unternehmen trifft.
ms.openlocfilehash: 0bdb4a0ffac139f45d842025238d3780f41d594c
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41599822"
---
# <a name="attack-simulator-in-office-365"></a><span data-ttu-id="252ee-104">Angriffssimulator in Office 365</span><span class="sxs-lookup"><span data-stu-id="252ee-104">Attack Simulator in Office 365</span></span>

<span data-ttu-id="252ee-105">**Zusammenfassung** Wenn Sie ein Office 365 globaler Administrator oder Sicherheitsadministrator sind und Ihre Organisation Office 365 Advanced Threat Protection Plan 2, einschließlich der Funktionen zur [Ermittlung und Reaktion von Bedrohungen](office-365-ti.md), verwendet, können Sie mit dem Angriffs Simulator realistische Angriffsszenarien in Ihrer Organisation ausführen.</span><span class="sxs-lookup"><span data-stu-id="252ee-105">**Summary** If you are an Office 365 global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="252ee-106">Auf diese Weise können Sie Benutzer mit Sicherheitslücken leichter identifizieren und finden, bevor ein echter Angriff passiert.</span><span class="sxs-lookup"><span data-stu-id="252ee-106">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="252ee-107">Lesen Sie diesen Artikel, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="252ee-107">Read this article to learn more.</span></span>

## <a name="the-attacks"></a><span data-ttu-id="252ee-108">Die Angriffe</span><span class="sxs-lookup"><span data-stu-id="252ee-108">The Attacks</span></span>

<span data-ttu-id="252ee-109">Derzeit stehen drei Arten von Angriffssimulationen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="252ee-109">Three kinds of attack simulations are currently available:</span></span>

- [<span data-ttu-id="252ee-110">Speer-Phishing-Angriff (Anzeigename)</span><span class="sxs-lookup"><span data-stu-id="252ee-110">Display name spear-phishing attack</span></span>](#display-name-spear-phishing-attack)

- [<span data-ttu-id="252ee-111">Kennwort-Spray-Angriff</span><span class="sxs-lookup"><span data-stu-id="252ee-111">Password-spray attack</span></span>](#password-spray-attack)

- [<span data-ttu-id="252ee-112">Brute-Force-Kennwortangriff</span><span class="sxs-lookup"><span data-stu-id="252ee-112">Brute-force password attack</span></span>](#brute-force-password-attack)

<span data-ttu-id="252ee-113">Damit ein Angriff erfolgreich gestartet werden kann, müssen Sie sicherstellen, dass das Konto, mit dem Simulierte Angriffe ausgeführt werden, die mehrstufige Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="252ee-113">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="252ee-114">Darüber hinaus müssen Sie ein Office 365 globaler Administrator oder Sicherheitsadministrator sein.</span><span class="sxs-lookup"><span data-stu-id="252ee-114">In addition, you must be an Office 365 global administrator or a security administrator.</span></span> <span data-ttu-id="252ee-115">(Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Office 365 Security #a0 Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="252ee-115">(To learn more about roles and permissions, see [Permissions in the Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

<span data-ttu-id="252ee-116">Um auf &amp; den Angriffs Simulator zuzugreifen, wählen Sie im Security Compliance Center **Threat Management** \> **Attack Simulator**aus.</span><span class="sxs-lookup"><span data-stu-id="252ee-116">To access Attack Simulator, in the Security &amp; Compliance Center, choose **Threat management** \> **Attack simulator**.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="252ee-117">Bevor Sie beginnen...</span><span class="sxs-lookup"><span data-stu-id="252ee-117">Before you begin...</span></span>

<span data-ttu-id="252ee-118">Stellen Sie sicher, dass Sie und Ihre Organisation die folgenden Anforderungen für den Angriffs Simulator erfüllen:</span><span class="sxs-lookup"><span data-stu-id="252ee-118">Make sure that you and your organization meet the following requirements for Attack Simulator:</span></span>

- <span data-ttu-id="252ee-119">Die e-Mail-Adresse Ihrer Organisation wird in Exchange Online gehostet.</span><span class="sxs-lookup"><span data-stu-id="252ee-119">Your organization's email is hosted in Exchange Online.</span></span> <span data-ttu-id="252ee-120">(Der Angriffs Simulator steht für lokale e-Mail-Server nicht zur Verfügung.)</span><span class="sxs-lookup"><span data-stu-id="252ee-120">(Attack Simulator is not available for on-premises email servers.)</span></span>

- <span data-ttu-id="252ee-121">Sie sind ein Office 365 globaler Administrator oder Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="252ee-121">You are an Office 365 global administrator or security administrator</span></span>

- <span data-ttu-id="252ee-122">[Mehrstufige Authentifizierung/bedingter Zugriff](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) ist aktiviert, für mindestens das Office 365 globales Administratorkonto und Sicherheitsadministratoren, die den Angriffs Simulator verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="252ee-122">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the Office 365 global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="252ee-123">(Im Idealfall ist mehrstufige Authentifizierung/bedingter Zugriff für alle Benutzer in Ihrer Organisation aktiviert.)</span><span class="sxs-lookup"><span data-stu-id="252ee-123">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

- <span data-ttu-id="252ee-124">Ihre Organisation verfügt über [Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), in dem der Angriffs &amp; Simulator im Security Compliance Center sichtbar ist (zu **Threat Management** \> **Attack Simulator**wechseln).</span><span class="sxs-lookup"><span data-stu-id="252ee-124">Your organization has [Office 365 Advanced Threat Protection Plan 2](office-365-atp.md), with Attack Simulator visible in the Security &amp; Compliance Center (go to **Threat management** \> **Attack simulator**)</span></span>

    ![Threat Management – Angriffs Simulator](../media/ThreatMgmt-AttackSimulator.png)

## <a name="display-name-spear-phishing-attack"></a><span data-ttu-id="252ee-126">Spear-Phishing-Angriff (Anzeigename)</span><span class="sxs-lookup"><span data-stu-id="252ee-126">Display name spear-phishing attack</span></span>

<span data-ttu-id="252ee-127">Phishing ist ein generischer Ausdruck für eine große Sammlung von Angriffen, die als Angriffs für soziale Technik bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="252ee-127">Phishing is a generic term for a broad suite of attacks classed as a social engineering style attack.</span></span> <span data-ttu-id="252ee-128">Dieser Angriff konzentriert sich auf Speer-Phishing, einen gezielteren Angriff, der auf eine bestimmte Gruppe von Personen oder eine Organisation abzielt.</span><span class="sxs-lookup"><span data-stu-id="252ee-128">This attack is focused on spear phishing, a more targeted attack that is aimed at a specific group of individuals or an organization.</span></span> <span data-ttu-id="252ee-129">Normalerweise wird ein benutzerdefinierter Angriff mit einiger Aufklärung durchgeführt und ein Anzeigename verwendet, der eine Vertrauensstellung für den Empfänger generiert, beispielsweise eine e-Mail-Nachricht, die aussieht, als käme sie von einer Führungskraft in Ihrer Organisation.</span><span class="sxs-lookup"><span data-stu-id="252ee-129">Typically, a customized attack with some reconnaissance performed and using a display name that will generate trust in the recipient, such as an email message that looks like it came from an executive within your organization.</span></span>

<span data-ttu-id="252ee-130">Dieser Angriff konzentriert sich darauf, dass Sie den Anzeigenamen und die Quelladresse ändern können, aus dem die Nachricht anscheinend entstanden ist.</span><span class="sxs-lookup"><span data-stu-id="252ee-130">This attack focuses on letting you manipulate who the message appears to have originated from by changing the display name and source address.</span></span> <span data-ttu-id="252ee-131">Wenn Speer-Phishing-Angriffe erfolgreich sind, erhalten cyberattackers Zugriff auf die Anmeldeinformationen von Benutzern.</span><span class="sxs-lookup"><span data-stu-id="252ee-131">When spear-phishing attacks are successful, cyberattackers gain access to users' credentials.</span></span>

### <a name="to-simulate-a-spear-phishing-attack"></a><span data-ttu-id="252ee-132">So simulieren Sie einen Speer-Phishing-Angriff</span><span class="sxs-lookup"><span data-stu-id="252ee-132">To simulate a spear-phishing attack</span></span>

![E-Mail-Textkörper erstellen](../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

<span data-ttu-id="252ee-134">Sie können den Rich-HTML-Editor direkt im Feld **e-Mail-Textkörper** selbst oder mit HTML-Quelle arbeiten.</span><span class="sxs-lookup"><span data-stu-id="252ee-134">You can craft the rich HTML editor directly in the **Email body** field itself or work with HTML source.</span></span>

1. <span data-ttu-id="252ee-135">Wählen Sie [im &amp; Security Compliance Center](https://protection.office.com) **Threat Management** \> **Attack Simulator**aus.</span><span class="sxs-lookup"><span data-stu-id="252ee-135">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="252ee-136">Geben Sie einen aussagekräftigen Kampagnennamen für den Angriff an, oder wählen Sie eine Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="252ee-136">Specify a meaningful campaign name for the attack or select a template.</span></span>

   ![Phishing-Start Seite](../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

3. <span data-ttu-id="252ee-138">Geben Sie die Zielempfänger an.</span><span class="sxs-lookup"><span data-stu-id="252ee-138">Specify the target recipients.</span></span> <span data-ttu-id="252ee-139">Hierbei kann es sich um Einzelpersonen oder Gruppen in Ihrer Organisation handeln.</span><span class="sxs-lookup"><span data-stu-id="252ee-139">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="252ee-140">Jeder Zielempfänger muss über ein Exchange Online Postfach verfügen, damit der Angriff erfolgreich verläuft.</span><span class="sxs-lookup"><span data-stu-id="252ee-140">Each targeted recipient must have an Exchange Online Mailbox in order for the attack to be successful.</span></span>

   ![Empfängerauswahl](../media/faf8c2e0-6175-4cd7-8265-0c8e727f4d0f.jpg)

4. <span data-ttu-id="252ee-142">Konfigurieren Sie die Phishing-e-Mail-Details.</span><span class="sxs-lookup"><span data-stu-id="252ee-142">Configure the Phishing email details.</span></span>

   ![Konfigurieren von e-Mail-Details](../media/f043608f-f8ce-4aae-be28-86e8ecc524a9.jpg)

   <span data-ttu-id="252ee-144">Die HTML-Formatierung kann so komplex oder einfach sein, wie Ihre Kampagne benötigt.</span><span class="sxs-lookup"><span data-stu-id="252ee-144">The HTML formatting can be as complex or basic as your campaign needs.</span></span> <span data-ttu-id="252ee-145">Da das e-Mail-Format HTML ist, können Sie Bilder und Text einfügen, um die Glaubwürdigkeit erhöhen zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="252ee-145">As the email format is HTML, you can insert images and text to enhance believability.</span></span> <span data-ttu-id="252ee-146">Sie haben die Kontrolle darüber, wie die empfangene Nachricht im empfangenden e-Mail-Client aussehen wird.</span><span class="sxs-lookup"><span data-stu-id="252ee-146">You have control on what the received message will look like in the receiving email client.</span></span>

5. <span data-ttu-id="252ee-147">Geben Sie den Text für das Feld **from (Name)** an.</span><span class="sxs-lookup"><span data-stu-id="252ee-147">Specify text for the **From (Name)** field.</span></span> <span data-ttu-id="252ee-148">Dies ist das Feld, das im empfangenden e-Mail-Client im **Anzeigenamen** angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="252ee-148">This is the field that shows in the **Display Name** in the receiving email client.</span></span>

6. <span data-ttu-id="252ee-149">Geben Sie Text oder das Feld **von** an.</span><span class="sxs-lookup"><span data-stu-id="252ee-149">Specify text or the **From** field.</span></span> <span data-ttu-id="252ee-150">Dies ist das Feld, das als e-Mail-Adresse des Absenders im empfangenden e-Mail-Client angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="252ee-150">This is the field that shows as the email address of the sender in the receiving email client.</span></span>

   <span data-ttu-id="252ee-151">Sie können in Ihrer Organisation einen vorhandenen e-Mail-Namespace eingeben (Dadurch wird die e-Mail-Adresse tatsächlich im empfangenden Client aufgelöst, wodurch ein sehr hohes Vertrauensmodell erleichtert wird), oder Sie können eine externe e-Mail-Adresse eingeben.</span><span class="sxs-lookup"><span data-stu-id="252ee-151">You can enter an existing email namespace within your organization (doing this will make the email address actually resolve in the receiving client, facilitating a very high trust model), or you can enter an external email address.</span></span> <span data-ttu-id="252ee-152">Die angegebene e-Mail-Adresse muss nicht tatsächlich vorhanden sein, Sie muss jedoch dem Format einer gültigen SMTP-Adresse wie `user@domainname.extension`.</span><span class="sxs-lookup"><span data-stu-id="252ee-152">The email address that you specify does not have to actually exist, but it does need to follow the format of a valid SMTP address, such as `user@domainname.extension`.</span></span>

7. <span data-ttu-id="252ee-153">Wählen Sie mithilfe der Dropdownauswahl eine URL für den Phishing-Anmeldeserver aus, die die Art der Inhalte widerspiegelt, die Sie in ihrem Angriff haben werden.</span><span class="sxs-lookup"><span data-stu-id="252ee-153">Using the drop-down selector, select a Phishing Login server URL that reflects the type of content you will have within your attack.</span></span> <span data-ttu-id="252ee-154">Es werden mehrere Themen-URLs bereitgestellt, aus denen Sie auswählen können, beispielsweise Dokumentzustellung, technische, Lohnbuchhaltung usw. Dies ist effektiv die URL, auf die Zielbenutzer klicken müssen.</span><span class="sxs-lookup"><span data-stu-id="252ee-154">Several themed URLs are provided for you to choose from, such as document delivery, technical, payroll etc. This is effectively the URL that targeted users are asked to click.</span></span>

8. <span data-ttu-id="252ee-155">Geben Sie eine benutzerdefinierte URL für die Zielseiten an.</span><span class="sxs-lookup"><span data-stu-id="252ee-155">Specify a custom landing page URL.</span></span> <span data-ttu-id="252ee-156">Mit dieser Methode werden Benutzer zu einer URL umgeleitet, die Sie am Ende eines erfolgreichen Angriffs angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="252ee-156">Using this will redirect users to a URL you specify at the end of a successful attack.</span></span> <span data-ttu-id="252ee-157">Wenn Sie beispielsweise ein internes Bewusstseinstraining haben, können Sie dies hier angeben.</span><span class="sxs-lookup"><span data-stu-id="252ee-157">If you have internal awareness training, for example, you can specify that here.</span></span>

9. <span data-ttu-id="252ee-158">Geben Sie den Text für das Feld **Betreff** an.</span><span class="sxs-lookup"><span data-stu-id="252ee-158">Specify text for the **Subject** field.</span></span> <span data-ttu-id="252ee-159">Dies ist das Feld, das als **Antragsteller Name** im empfangenden e-Mail-Client angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="252ee-159">This is the field that shows as the **Subject Name** in the receiving email client.</span></span>

10. <span data-ttu-id="252ee-160">Erstellen Sie den **e-Mail-Text** , den das Ziel empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="252ee-160">Compose the **Email body** that the target will receive.</span></span>

    <span data-ttu-id="252ee-161">`${username}`Fügt den Namen Targets in den e-Mail-Text ein.</span><span class="sxs-lookup"><span data-stu-id="252ee-161">`${username}` inserts the targets name into the Email body.</span></span>

    <span data-ttu-id="252ee-162">`${loginserverurl}`Fügt die URL ein, auf die die Zielbenutzer klicken sollen.</span><span class="sxs-lookup"><span data-stu-id="252ee-162">`${loginserverurl}` inserts the URL we want target users to click</span></span>

11. <span data-ttu-id="252ee-163">Klicken Sie auf **weiter und** anschließend auf **Fertig stellen** , um den Angriff zu starten.</span><span class="sxs-lookup"><span data-stu-id="252ee-163">Choose **Next,** then **Finish** to launch the attack.</span></span> <span data-ttu-id="252ee-164">Die Phishing-e-Mail-Nachricht wird an die Postfächer ihrer Zielempfänger übermittelt.</span><span class="sxs-lookup"><span data-stu-id="252ee-164">The spear phishing email message is delivered to your target recipients' mailboxes.</span></span>

## <a name="password-spray-attack"></a><span data-ttu-id="252ee-165">Kennwort-Spray-Angriff</span><span class="sxs-lookup"><span data-stu-id="252ee-165">Password-spray attack</span></span>

<span data-ttu-id="252ee-166">Ein Kenn Wort Sprüh Angriff auf eine Organisation wird in der Regel verwendet, nachdem ein schlechter Akteur eine Liste gültiger Benutzer aus dem Mandanten erfolgreich erworben hat.</span><span class="sxs-lookup"><span data-stu-id="252ee-166">A password spray attack against an organization is typically used after a bad actor has successfully acquired a list of valid users from the tenant.</span></span> <span data-ttu-id="252ee-167">Der fehlerhafte Akteur weiß um häufige Kennwörter, die von Benutzern verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="252ee-167">The bad actor knows about common passwords that people use.</span></span> <span data-ttu-id="252ee-168">Dies ist ein weit verbreiteter Angriff, da es sich um einen günstigen Angriff handelt und schwerer zu erkennen ist als Brute-Force-Ansätze.</span><span class="sxs-lookup"><span data-stu-id="252ee-168">This is a widely used attack, as it is a cheap attack to run, and harder to detect than brute force approaches.</span></span>

<span data-ttu-id="252ee-169">Dieser Angriff konzentriert sich darauf, dass Sie ein gemeinsames Kennwort für eine große Zieldatenbank von Benutzern angeben können.</span><span class="sxs-lookup"><span data-stu-id="252ee-169">This attack focuses on letting you specify a common password against a large target base of users.</span></span>

### <a name="to-simulate-a-password-spray-attack"></a><span data-ttu-id="252ee-170">So simulieren Sie einen Kenn Wort Sprüh Angriff</span><span class="sxs-lookup"><span data-stu-id="252ee-170">To simulate a password-spray attack</span></span>

1. <span data-ttu-id="252ee-171">Wählen Sie [im &amp; Security Compliance Center](https://protection.office.com) **Threat Management** \> **Attack Simulator**aus.</span><span class="sxs-lookup"><span data-stu-id="252ee-171">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="252ee-172">Geben Sie einen aussagekräftigen Kampagnennamen für den Angriff an.</span><span class="sxs-lookup"><span data-stu-id="252ee-172">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="252ee-173">Geben Sie die Zielempfänger an.</span><span class="sxs-lookup"><span data-stu-id="252ee-173">Specify the target recipients.</span></span> <span data-ttu-id="252ee-174">Hierbei kann es sich um Einzelpersonen oder Gruppen in Ihrer Organisation handeln.</span><span class="sxs-lookup"><span data-stu-id="252ee-174">This can be individuals or groups in your organization.</span></span> <span data-ttu-id="252ee-175">Ein Zielempfänger muss über ein Exchange Online Postfach verfügen, damit der Angriff erfolgreich verläuft.</span><span class="sxs-lookup"><span data-stu-id="252ee-175">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="252ee-176">Geben Sie ein Kennwort an, das für den Angriff verwendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="252ee-176">Specify a password to use for the attack.</span></span> <span data-ttu-id="252ee-177">Beispielsweise ist ein gemeinsames, relevantes Kennwort, das `Summer2019`Sie ausprobieren können.</span><span class="sxs-lookup"><span data-stu-id="252ee-177">For example, one common, relevant password you could try is `Summer2019`.</span></span> <span data-ttu-id="252ee-178">Ein anderer könnte `Fall2019`sein, `Password1`oder.</span><span class="sxs-lookup"><span data-stu-id="252ee-178">Another might be `Fall2019`, or `Password1`.</span></span>

5. <span data-ttu-id="252ee-179">Wählen Sie **Fertig stellen** aus, um den Angriff zu starten.</span><span class="sxs-lookup"><span data-stu-id="252ee-179">Choose **Finish** to launch the attack.</span></span>

## <a name="brute-force-password-attack"></a><span data-ttu-id="252ee-180">Brute-Force-Kennwortangriff</span><span class="sxs-lookup"><span data-stu-id="252ee-180">Brute-force password attack</span></span>

<span data-ttu-id="252ee-181">Ein Brute-Force-Kennwortangriff auf eine Organisation wird in der Regel verwendet, nachdem ein schlechter Akteur erfolgreich eine Liste mit wichtigen Benutzern aus dem Mandanten abgerufen hat.</span><span class="sxs-lookup"><span data-stu-id="252ee-181">A brute-force password attack against an organization is typically used after a bad actor has successfully acquired a list of key users from the tenant.</span></span> <span data-ttu-id="252ee-182">Dieser Angriff konzentriert sich auf das Ausprobieren einer Gruppe von Kennwörtern für das Konto eines einzelnen Benutzers.</span><span class="sxs-lookup"><span data-stu-id="252ee-182">This attack focuses on trying a set of passwords on a single user's account.</span></span>

### <a name="to-simulate-a-brute-force-password-attack"></a><span data-ttu-id="252ee-183">So simulieren Sie einen Brute-Force-Kennwortangriff</span><span class="sxs-lookup"><span data-stu-id="252ee-183">To simulate a brute-force password attack</span></span>

1. <span data-ttu-id="252ee-184">Wählen Sie [im &amp; Security Compliance Center](https://protection.office.com) **Threat Management** \> **Attack Simulator**aus.</span><span class="sxs-lookup"><span data-stu-id="252ee-184">In the [Security &amp; Compliance Center](https://protection.office.com), choose **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="252ee-185">Geben Sie einen aussagekräftigen Kampagnennamen für den Angriff an.</span><span class="sxs-lookup"><span data-stu-id="252ee-185">Specify a meaningful campaign name for the attack.</span></span>

3. <span data-ttu-id="252ee-186">Geben Sie den Zielempfänger an.</span><span class="sxs-lookup"><span data-stu-id="252ee-186">Specify the target recipient.</span></span> <span data-ttu-id="252ee-187">Ein Zielempfänger muss über ein Exchange Online Postfach verfügen, damit der Angriff erfolgreich verläuft.</span><span class="sxs-lookup"><span data-stu-id="252ee-187">A targeted recipient must have an Exchange Online mailbox in order for the attack to be successful.</span></span>

4. <span data-ttu-id="252ee-188">Geben Sie eine Gruppe von Kennwörtern an, die für den Angriff verwendet werden sollen.</span><span class="sxs-lookup"><span data-stu-id="252ee-188">Specify a set of passwords to use for the attack.</span></span> <span data-ttu-id="252ee-189">Zu diesem Zweck können Sie eine Textdatei (txt-Datei) für die Liste der Kennwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="252ee-189">To do this, you can use a text (.txt) file for your list of passwords.</span></span> <span data-ttu-id="252ee-190">Die Textdatei darf die Dateigröße von 10 MB nicht überschreiten.</span><span class="sxs-lookup"><span data-stu-id="252ee-190">The text file cannot exceed 10 MB in file size.</span></span> <span data-ttu-id="252ee-191">Verwenden Sie ein Kennwort pro Zeilen, und stellen Sie sicher, dass Sie nach dem letzten Kennwort in Ihrer Liste eine harte Rückgabe einschließen.</span><span class="sxs-lookup"><span data-stu-id="252ee-191">Use one password per line, and make sure to include a hard return after the last password in your list.</span></span>

5. <span data-ttu-id="252ee-192">Wählen Sie **Fertig stellen** aus, um den Angriff zu starten.</span><span class="sxs-lookup"><span data-stu-id="252ee-192">Choose **Finish** to launch the attack.</span></span>

## <a name="new-features-in-attack-simulator"></a><span data-ttu-id="252ee-193">Neue Features in Attack Simulator</span><span class="sxs-lookup"><span data-stu-id="252ee-193">New features in Attack Simulator</span></span>

<span data-ttu-id="252ee-194">Neue Features wurden kürzlich dem Angriffs Simulator hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="252ee-194">New features have recently been added to Attack Simulator.</span></span> <span data-ttu-id="252ee-195">Zu diesen zählen:</span><span class="sxs-lookup"><span data-stu-id="252ee-195">These include:</span></span>

- <span data-ttu-id="252ee-196">Erweiterte Berichtsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="252ee-196">Advanced reporting capabilities.</span></span> <span data-ttu-id="252ee-197">Die Möglichkeit, Daten wie die schnellste (oder langsamste) Zeit anzuzeigen, um eine e-Mail-Nachricht zur Angriffssimulation zu öffnen, die schnellste (oder langsamste) Zeit zum Klicken auf einen Link in der Nachricht und weitere Visualisierungen.</span><span class="sxs-lookup"><span data-stu-id="252ee-197">The ability to see data such as the fastest (or slowest) time to open an attack simulation email message, the fastest (or slowest) time to click a link in the message, and more visualizations.</span></span>

- <span data-ttu-id="252ee-198">E-Mail-Vorlageneditor.</span><span class="sxs-lookup"><span data-stu-id="252ee-198">Email template editor.</span></span> <span data-ttu-id="252ee-199">Die Möglichkeit zum Erstellen einer benutzerdefinierten, wiederverwendbaren e-Mail-Vorlage, die Sie für zukünftige Angriffssimulationen verwenden können.</span><span class="sxs-lookup"><span data-stu-id="252ee-199">The ability to create a custom, reusable email template's that you can use for future attack simulations.</span></span>

- <span data-ttu-id="252ee-200">CSV-Empfänger Import.</span><span class="sxs-lookup"><span data-stu-id="252ee-200">CSV Recipient Import.</span></span> <span data-ttu-id="252ee-201">Die Möglichkeit, eine CSV-Datei zu verwenden, um Ihre Zielempfänger Liste zu importieren, anstatt die Adressbuch Auswahl zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="252ee-201">The ability to use a .csv file to import your target recipient list instead of using the address book picker.</span></span>

<span data-ttu-id="252ee-202">Weitere neue Features kommen in Kürze zum Angriff Simulator.</span><span class="sxs-lookup"><span data-stu-id="252ee-202">More new features are coming soon to Attack Simulator.</span></span> <span data-ttu-id="252ee-203">Zu diesen zählen:</span><span class="sxs-lookup"><span data-stu-id="252ee-203">These include:</span></span>

- <span data-ttu-id="252ee-204">Phishing-Simulation für Anlagen Nutzlast.</span><span class="sxs-lookup"><span data-stu-id="252ee-204">Attachment payload phishing simulation.</span></span> <span data-ttu-id="252ee-205">Die Möglichkeit, eine Anlage als Nutzlast für die Phishing-Simulation anstelle einer URL zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="252ee-205">The ability to use an attachment as the payload for phishing simulation in place of a URL.</span></span>

<span data-ttu-id="252ee-206">Besuchen Sie die [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap) , um zu sehen, was sich in der Entwicklung befindet, was sich ausrollt und was bereits gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="252ee-206">Visit the [Microsoft 365 Roadmap](https://www.microsoft.com/microsoft-365/roadmap) to see what's in development, what's rolling out, and what's already launched.</span></span>

## <a name="see-also"></a><span data-ttu-id="252ee-207">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="252ee-207">See also</span></span>

[<span data-ttu-id="252ee-208">Office 365 Advanced Threat Protection-Dienstbeschreibung</span><span class="sxs-lookup"><span data-stu-id="252ee-208">Office 365 Advanced Threat Protection Service Description</span></span>](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

[<span data-ttu-id="252ee-209">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="252ee-209">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)
