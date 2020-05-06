---
title: Angriffs Simulator in ATP
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
ms.custom:
- seo-marvel-apr2020
description: Erfahren Sie, wie Sie mithilfe des Angriffs Simulators simulierte Phishing-und Kennwortangriffe in Ihrer Microsoft 365 E5-oder ATP-Plan 2-Organisation ausführen.
ms.openlocfilehash: e2c6859291e4a25e56dd8dd20a8ecc5962310680
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035858"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="6cb64-103">Angriffs Simulator in ATP</span><span class="sxs-lookup"><span data-stu-id="6cb64-103">Attack Simulator in ATP</span></span>

<span data-ttu-id="6cb64-104">**Zusammenfassung** Wenn Sie globaler Administrator oder Sicherheitsadministrator sind und Ihre Organisation Office 365 Advanced Threat Protection Plan 2, einschließlich der [Funktionen zur Ermittlung und Reaktion von Bedrohungen](office-365-ti.md), verwendet, können Sie mit dem Angriffs Simulator realistische Angriffsszenarien in Ihrer Organisation ausführen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-104">**Summary** If you are a global administrator or a security administrator and your organization has Office 365 Advanced Threat Protection Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="6cb64-105">Auf diese Weise können Sie Benutzer mit Sicherheitslücken leichter identifizieren und finden, bevor ein echter Angriff passiert.</span><span class="sxs-lookup"><span data-stu-id="6cb64-105">This can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="6cb64-106">Lesen Sie diesen Artikel, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="6cb64-106">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="6cb64-107">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="6cb64-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="6cb64-108">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="6cb64-108">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="6cb64-109">Angriffs Simulator ist unter **Threat Management** \> **Attack Simulator**verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6cb64-109">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span>

  ![Threat Management – Angriffs Simulator](../../media/ThreatMgmt-AttackSimulator.png)

- <span data-ttu-id="6cb64-111">Weitere Informationen zur Verfügbarkeit des Angriffs Simulators in verschiedenen Microsoft 365-Abonnements finden Sie unter [Office 365 Advanced Threat Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="6cb64-111">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="6cb64-112">Sie müssen Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="6cb64-112">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="6cb64-113">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="6cb64-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="6cb64-114">Ihr Konto muss für die mehrstufige Authentifizierung (MFA) konfiguriert sein, um Kampagnen im Angriffs Simulator zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="6cb64-114">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="6cb64-115">Anweisungen finden Sie unter [Einrichten der mehr](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication)stufigen Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="6cb64-115">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

<span data-ttu-id="6cb64-116">Damit ein Angriff erfolgreich gestartet werden kann, müssen Sie sicherstellen, dass das Konto, mit dem Simulierte Angriffe ausgeführt werden, die mehrstufige Authentifizierung verwendet.</span><span class="sxs-lookup"><span data-stu-id="6cb64-116">For an attack to be successfully launched, make sure that the account you are using to run simulated attacks is using multi-factor authentication.</span></span> <span data-ttu-id="6cb64-117">Darüber hinaus müssen Sie ein globaler Administrator oder Sicherheitsadministrator sein.</span><span class="sxs-lookup"><span data-stu-id="6cb64-117">In addition, you must be a global administrator or a security administrator.</span></span> <span data-ttu-id="6cb64-118">(Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span><span class="sxs-lookup"><span data-stu-id="6cb64-118">(To learn more about roles and permissions, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).)</span></span>

- <span data-ttu-id="6cb64-119">Bei Phishing-Kampagnen werden Ereignisse für 30 Tage gesammelt und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="6cb64-119">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="6cb64-120">Die Daten der Verlaufs Kampagne werden bis zu 90 Tage nach dem Start der Kampagne zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-120">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="6cb64-121">Es gibt keine entsprechenden PowerShell-Cmdlets für den Angriffs Simulator.</span><span class="sxs-lookup"><span data-stu-id="6cb64-121">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="6cb64-122">Speer-Phishing-Kampagnen</span><span class="sxs-lookup"><span data-stu-id="6cb64-122">Spear phishing campaigns</span></span>

<span data-ttu-id="6cb64-123">*Phishing* ist ein allgemeiner Begriff für e-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die anscheinend von legitimen oder vertrauenswürdigen Absendern sind.</span><span class="sxs-lookup"><span data-stu-id="6cb64-123">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="6cb64-124">*Spear-Phishing* ist ein gezielter Phishing-Angriff, der sehr fokussierte und angepasste Inhalte verwendet, die speziell auf die Zielempfänger zugeschnitten sind (normalerweise nach Aufklärung der Empfänger durch den Angreifer).</span><span class="sxs-lookup"><span data-stu-id="6cb64-124">*Spear phishing* is a targeted phishing attack that uses very focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

- <span data-ttu-id="6cb64-125">Sie sind globaler Administrator oder Sicherheitsadministrator</span><span class="sxs-lookup"><span data-stu-id="6cb64-125">You are a global administrator or security administrator</span></span>

<span data-ttu-id="6cb64-126">In Attack Simulator stehen zwei verschiedene Arten von Speer-Phishing-Kampagnen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="6cb64-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="6cb64-127">[Mehrstufige Authentifizierung/bedingter Zugriff](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) ist aktiviert, für mindestens das globale Administratorkonto und Sicherheitsadministratoren, die den Angriffs Simulator verwenden werden.</span><span class="sxs-lookup"><span data-stu-id="6cb64-127">[Multi-factor authentication/Conditional Access](https://docs.microsoft.com/office365/admin/security-and-compliance/set-up-multi-factor-authentication) is turned on, for at least the global administrator account and security administrators who will be using Attack Simulator.</span></span> <span data-ttu-id="6cb64-128">(Im Idealfall ist mehrstufige Authentifizierung/bedingter Zugriff für alle Benutzer in Ihrer Organisation aktiviert.)</span><span class="sxs-lookup"><span data-stu-id="6cb64-128">(Ideally, multi-factor authentication/conditional access is turned on for all users in your organization.)</span></span>

  - <span data-ttu-id="6cb64-129">Eine Standardseite, auf der dies erläutert wurde, war nur ein Test und gibt Tipps zum Erkennen von Phishing-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="6cb64-129">A default page that explains this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Was die Benutzer sehen, wenn Sie auf den Phishing-Link klicken und Ihre Anmeldeinformationen eingeben](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="6cb64-131">Eine benutzerdefinierte Seite (URL), die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-131">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="6cb64-132">**Spear-Phishing (Attachment)**: der Angriff versucht, die Empfänger davon zu überzeugen, eine DOCX-oder PDF-Anlage in der Nachricht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-132">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="6cb64-133">Die Anlage enthält denselben Inhalt aus dem standardmäßigen Phishing-Link, aber der erste Satz beginnt mit\<"Anzeige\>Name, Sie sehen diese Nachricht als kürzlich geöffnete e-Mail-Nachricht...".</span><span class="sxs-lookup"><span data-stu-id="6cb64-133">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="6cb64-134">Derzeit laufen Speer-Phishing-Kampagnen in Attack Simulator nicht ab.</span><span class="sxs-lookup"><span data-stu-id="6cb64-134">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="6cb64-135">Erstellen einer Speer-Phishing-Kampagne</span><span class="sxs-lookup"><span data-stu-id="6cb64-135">Create a spear phishing campaign</span></span>

<span data-ttu-id="6cb64-136">Ein wichtiger Bestandteil jeder Speer-Phishing-Kampagne ist das Aussehen und Verhalten der e-Mail-Nachricht, die an die Zielempfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="6cb64-136">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="6cb64-137">Sie haben folgende Möglichkeiten, um die e-Mail-Nachricht zu erstellen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="6cb64-137">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="6cb64-138">**Verwenden Sie eine integrierte e-Mail-Vorlage**: zwei integrierte Vorlagen stehen zur Verfügung: **Preis Giveaway** -und **Gehaltslisten Update**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-138">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="6cb64-139">Sie können einige, alle oder keine der e-Mail-Eigenschaften von der Vorlage anpassen, wenn Sie die Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="6cb64-139">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="6cb64-140">**Erstellen einer wiederverwendbaren e-Mail-Vorlage**: Nachdem Sie die e-Mail-Vorlage erstellt und gespeichert haben, können Sie Sie in künftigen Spear-Phishing-Kampagnen erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cb64-140">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="6cb64-141">Sie können einige, alle oder keine der e-Mail-Eigenschaften von der Vorlage anpassen, wenn Sie die Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="6cb64-141">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="6cb64-142">**Erstellen Sie die e-Mail-Nachricht im Assistenten**: Sie können die e-Mail-Nachricht direkt im Assistenten erstellen, während Sie die Spear-Phishing-Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="6cb64-142">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="6cb64-143">Schritt 1 (optional): Erstellen einer benutzerdefinierten e-Mail-Vorlage</span><span class="sxs-lookup"><span data-stu-id="6cb64-143">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="6cb64-144">Wenn Sie eine der integrierten Vorlagen verwenden oder die e-Mail-Nachricht direkt im Assistenten erstellen, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-144">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="6cb64-145">Wechseln Sie im Security & Compliance Center zum **Threat Management** \> - **Angriffs Simulator**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-145">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6cb64-146">Klicken Sie auf der Seite " **Angriffe simulieren** " entweder in den Abschnitten **Spear Phishing (Credentials Harvest)** oder **Spear Phishing (Attachment)** auf **Attack Details**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-146">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="6cb64-147">Es spielt keine Rolle, wo Sie die Vorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-147">It doesn't matter where you create the template.</span></span> <span data-ttu-id="6cb64-148">Die verfügbaren Optionen in der Vorlage sind für beide Arten von Phishing-Angriffen identisch.</span><span class="sxs-lookup"><span data-stu-id="6cb64-148">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="6cb64-149">Klicken Sie auf der daraufhin geöffneten Seite mit den **Angriffs Details** im Abschnitt **Phishing-Vorlagen** im Bereich **Vorlagen erstellen** auf **neue Vorlage**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-149">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="6cb64-150">Der Assistent zum **Konfigurieren von Phishing-Vorlagen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="6cb64-150">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="6cb64-151">Geben Sie im Schritt **Start** einen eindeutigen Anzeigenamen für die Vorlage ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-151">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="6cb64-152">Konfigurieren Sie im Schritt **e-Mail-Details konfigurieren** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="6cb64-152">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="6cb64-153">**From (Name)**: der Anzeige Name, der für den Absender der Nachricht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6cb64-153">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="6cb64-154">**Von (e-Mail)**: die e-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="6cb64-154">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="6cb64-155">**URL des Phishing-Anmeldeservers**: Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="6cb64-155">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="6cb64-156">Dies ist die URL, auf die Benutzer klicken sollen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-156">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="6cb64-157">Sie können wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="6cb64-157">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     > <ul><li><span data-ttu-id="6cb64-158">Alle URLs sind absichtlich HTTP und nicht HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6cb64-158">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="6cb64-159">Ein URL-Reputations Dienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher.</span><span class="sxs-lookup"><span data-stu-id="6cb64-159">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="6cb64-160">Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishing-Kampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cb64-160">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li></ul>

   - <span data-ttu-id="6cb64-161">**Benutzerdefinierte Startseiten-URL**: Geben Sie eine optionale Startseite ein, auf der Benutzer angezeigt werden, wenn Sie auf den Link Phishing klicken und die Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-161">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="6cb64-162">Dieser Link ersetzt die standardmäßige Ziel Seite.</span><span class="sxs-lookup"><span data-stu-id="6cb64-162">This link replaces the default landing page.</span></span> <span data-ttu-id="6cb64-163">Wenn Sie beispielsweise ein internes Bewusstseinstraining haben, können Sie diese URL hier angeben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-163">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="6cb64-164">**Kategorie**: Derzeit wird diese Einstellung nicht verwendet (alles, was Sie eingeben, wird ignoriert).</span><span class="sxs-lookup"><span data-stu-id="6cb64-164">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="6cb64-165">**Subject**: das **Subject** -Feld der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="6cb64-165">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="6cb64-166">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-166">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6cb64-167">Erstellen Sie im Schritt **e-Mail verfassen** den Nachrichtentext der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="6cb64-167">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="6cb64-168">Sie können die Registerkarte " **e-Mail** " (ein Rich-HTML-Editor) oder die Registerkarte " **Quelle** " (unformatierter HTML-Code) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cb64-168">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="6cb64-169">Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-169">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="6cb64-170">Sie können Bilder und Text einfügen, um die Glaubwürdigkeit erhöhen der Nachricht im e-Mail-Client des Empfängers zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="6cb64-170">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="6cb64-171">`${username}`Fügt den Namen des Empfängers ein.</span><span class="sxs-lookup"><span data-stu-id="6cb64-171">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="6cb64-172">`${loginserverurl}`Fügt den URL-Wert des **Phishing-Anmeldeservers** aus dem vorherigen Schritt ein.</span><span class="sxs-lookup"><span data-stu-id="6cb64-172">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="6cb64-173">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-173">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="6cb64-174">Klicken Sie im Schritt **bestätigen** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-174">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="6cb64-175">Schritt 2: Erstellen und Starten der Spear-Phishing-Kampagne</span><span class="sxs-lookup"><span data-stu-id="6cb64-175">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="6cb64-176">Wechseln Sie im Security & Compliance Center zum **Threat Management** \> - **Angriffs Simulator**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-176">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6cb64-177">Wählen Sie auf der Seite **Angriffe simulieren** eine der folgenden Optionen basierend auf der Art der Kampagne aus, die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="6cb64-177">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="6cb64-178">Klicken Sie im Abschnitt **Spear Phishing (Credentials Harvest)** auf **Angriff starten** oder auf Angriff **Details** \> **starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-178">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="6cb64-179">Klicken Sie im Abschnitt **Spear Phishing (Attachment)** auf **Angriff starten** oder auf Angriff **Details** \> **starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-179">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="6cb64-180">Der Assistent zum **Konfigurieren von Phishing-Angriffen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="6cb64-180">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="6cb64-181">Führen Sie im **Start** Schritt einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6cb64-181">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6cb64-182">Geben Sie im Feld **Name** einen eindeutigen Anzeigenamen für die Kampagne ein.</span><span class="sxs-lookup"><span data-stu-id="6cb64-182">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="6cb64-183">Klicken Sie nicht auf **Vorlage verwenden**, da Sie die e-Mail-Nachricht später im Assistenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-183">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="6cb64-184">Klicken Sie auf **Vorlage verwenden** , und wählen Sie eine integrierte oder benutzerdefinierte e-Mail-Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="6cb64-184">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="6cb64-185">Nachdem Sie die Vorlage ausgewählt haben, wird das Feld **Name** automatisch basierend auf der Vorlage ausgefüllt, aber Sie können den Namen ändern.</span><span class="sxs-lookup"><span data-stu-id="6cb64-185">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Phishing-Start Seite](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="6cb64-187">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="6cb64-188">Führen Sie im Schritt **Zielempfänger** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6cb64-188">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6cb64-189">Klicken Sie auf **Adressbuch** , um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-189">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="6cb64-190">Jeder Zielempfänger muss über ein Exchange Online Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-190">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="6cb64-191">Wenn Sie auf **Filtern** und **anwenden** klicken, ohne Suchkriterien einzugeben, werden alle Empfänger zurückgegeben und zur Kampagne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6cb64-191">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="6cb64-192">Klicken Sie auf **Import** dann auf **Dateiimport** , um einen durch Kommas getrennten Wert (CSV) oder eine durch die Datei getrennte Datei mit e-Mail-Adressen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="6cb64-192">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="6cb64-193">Jede Reihe muss die e-Mail-Adresse des Empfängers enthalten.</span><span class="sxs-lookup"><span data-stu-id="6cb64-193">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="6cb64-194">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-194">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6cb64-195">Konfigurieren Sie im Schritt **e-Mail-Details konfigurieren** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="6cb64-195">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="6cb64-196">Wenn Sie im **Start** Schritt eine Vorlage ausgewählt haben, sind die meisten dieser Werte bereits konfiguriert, aber Sie können Sie ändern.</span><span class="sxs-lookup"><span data-stu-id="6cb64-196">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="6cb64-197">**From (Name)**: der Anzeige Name, der für den Absender der Nachricht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="6cb64-197">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="6cb64-198">**Von (e-Mail)**: die e-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="6cb64-198">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="6cb64-199">Sie können eine reale oder gefälschte e-Mail-Adresse aus der e-Mail-Domäne Ihrer Organisation eingeben, oder Sie können eine reale oder gefälschte externe e-Mail-Adresse eingeben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-199">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="6cb64-200">Eine gültige Absender-e-Mail-Adresse aus Ihrer Organisation wird tatsächlich im e-Mail-Client des Empfängers aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="6cb64-200">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="6cb64-201">**URL des Phishing-Anmeldeservers**: Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="6cb64-201">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="6cb64-202">Dies ist die URL, auf die Benutzer klicken sollen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-202">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="6cb64-203">Sie können wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="6cb64-203">The choices are:</span></span>

     - <http://portal.docdeliveryapp.com>
     - <http://portal.docdeliveryapp.net>
     - <http://portal.docstoreinternal.com>
     - <http://portal.docstoreinternal.net>
     - <http://portal.hardwarecheck.net>
     - <http://portal.hrsupportint.com>
     - <http://portal.payrolltooling.com>
     - <http://portal.payrolltooling.net>
     - <http://portal.prizegiveaway.net>
     - <http://portal.prizesforall.com>
     - <http://portal.salarytoolint.com>
     - <http://portal.salarytoolint.net>

     > [!NOTE]
     > <ul><li><span data-ttu-id="6cb64-204">Alle URLs sind absichtlich HTTP und nicht HTTPS.</span><span class="sxs-lookup"><span data-stu-id="6cb64-204">All of the URLs are intentionally http, not https.</span></span></li><li><span data-ttu-id="6cb64-205">Ein URL-Reputations Dienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher.</span><span class="sxs-lookup"><span data-stu-id="6cb64-205">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="6cb64-206">Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishing-Kampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cb64-206">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span></li><li><span data-ttu-id="6cb64-207">Sie müssen eine URL auswählen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-207">You are required to select a URL.</span></span> <span data-ttu-id="6cb64-208">Bei Kampagnen mit <b>Spear-Phishing (Attachment)</b> können Sie den Link aus dem Textkörper der Nachricht im nächsten Schritt entfernen (andernfalls enthält die Nachricht sowohl einen Link als <b>auch</b> eine Anlage).</span><span class="sxs-lookup"><span data-stu-id="6cb64-208">For <b>Spear Phishing (Attachment)</b> campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link <b>and</b> an attachment).</span></span></li></ul>

   - <span data-ttu-id="6cb64-209">**Anlagentyp**: Diese Einstellung ist nur in Kampagnen für **Spear-Phishing (Attachment)** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6cb64-209">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="6cb64-210">Klicken Sie auf die Dropdownliste, und wählen Sie aus **. DOCX** oder **. PDF** aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="6cb64-210">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="6cb64-211">**Name der Anlage**: Diese Einstellung ist nur in Kampagnen für **Spear-Phishing (Attachment)** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6cb64-211">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="6cb64-212">Geben Sie einen Dateinamen für die Datei. docx oder. PDF ein.</span><span class="sxs-lookup"><span data-stu-id="6cb64-212">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="6cb64-213">**Benutzerdefinierte Startseiten-URL**: Geben Sie eine optionale Startseite ein, auf der Benutzer angezeigt werden, wenn Sie auf den Link Phishing klicken und die Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-213">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="6cb64-214">Dieser Link ersetzt die standardmäßige Ziel Seite.</span><span class="sxs-lookup"><span data-stu-id="6cb64-214">This link replaces the default landing page.</span></span> <span data-ttu-id="6cb64-215">Wenn Sie beispielsweise ein internes Bewusstseinstraining haben, können Sie diese URL hier angeben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-215">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="6cb64-216">**Subject**: das **Subject** -Feld der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="6cb64-216">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="6cb64-217">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-217">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6cb64-218">Erstellen Sie im Schritt **e-Mail verfassen** den Nachrichtentext der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="6cb64-218">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="6cb64-219">Wenn Sie im **Start** Schritt eine Vorlage ausgewählt haben, ist der Nachrichtentext bereits konfiguriert, Sie können ihn jedoch anpassen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-219">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="6cb64-220">Sie können die Registerkarte " **e-Mail** " (ein Rich-HTML-Editor) oder die Registerkarte " **Quelle** " (unformatierter HTML-Code) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cb64-220">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="6cb64-221">Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-221">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="6cb64-222">Sie können Bilder und Text einfügen, um die Glaubwürdigkeit erhöhen der Nachricht im e-Mail-Client des Empfängers zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="6cb64-222">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="6cb64-223">`${username}`Fügt den Namen des Empfängers ein.</span><span class="sxs-lookup"><span data-stu-id="6cb64-223">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="6cb64-224">`${loginserverurl}`Fügt den URL-Wert für den **Phishing-Anmelde Server** ein.</span><span class="sxs-lookup"><span data-stu-id="6cb64-224">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="6cb64-225">Bei Kampagnen mit **Spear-Phishing (Attachment)** sollten Sie den Link aus dem Nachrichtentext entfernen (andernfalls enthält die Nachricht sowohl einen Link als **auch** eine Anlage, und Link Klicks werden nicht in einer Anlagen Kampagne nachverfolgt).</span><span class="sxs-lookup"><span data-stu-id="6cb64-225">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![E-Mail-Textkörper erstellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="6cb64-227">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-227">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="6cb64-228">Klicken Sie im Schritt **bestätigen** auf **Fertig stellen** , um die Kampagne zu starten.</span><span class="sxs-lookup"><span data-stu-id="6cb64-228">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="6cb64-229">Die Phishing-Nachricht wird an die Zielempfänger übermittelt.</span><span class="sxs-lookup"><span data-stu-id="6cb64-229">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="6cb64-230">Kenn Wort Angriffs Kampagnen</span><span class="sxs-lookup"><span data-stu-id="6cb64-230">Password attack campaigns</span></span>

<span data-ttu-id="6cb64-231">Ein *Kennwortangriff* versucht, Kennwörter für Benutzerkonten in einer Organisation zu erraten, in der Regel, nachdem der Angreifer mindestens ein gültiges Benutzerkonto erkannt hat.</span><span class="sxs-lookup"><span data-stu-id="6cb64-231">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="6cb64-232">In Attack Simulator stehen zwei verschiedene Arten von Kenn Wort Angriffs Kampagnen zur Verfügung, um die Komplexität der Kennwörter Ihrer Benutzer zu testen:</span><span class="sxs-lookup"><span data-stu-id="6cb64-232">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="6cb64-233">**Brute-Force-Kennwort (Wörterbuchangriff)**: bei einem *Brute-Force* -oder *Wörterbuch* Angriff wird eine große Wörterbuchdatei mit Kennwörtern für ein Benutzerkonto verwendet, wobei die Hoffnung besteht, dass einer von Ihnen funktioniert (viele Kennwörter für ein Konto).</span><span class="sxs-lookup"><span data-stu-id="6cb64-233">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="6cb64-234">Falsche Kenn Wort Sperren helfen, Brute-Force-Kennwortangriffe zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="6cb64-234">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="6cb64-235">Für den Wörterbuchangriff können Sie ein oder mehrere Kennwörter angeben, die Sie ausprobieren möchten (manuell eingegeben oder in eine hochgeladene Datei), und Sie können einen oder mehrere Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-235">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="6cb64-236">**Kenn Wort Sprüh Angriff**: bei einem *Kenn Wort Sprüh* Angriff wird dasselbe sorgfältig überprüfte Kennwort für eine Liste von Benutzerkonten verwendet (ein Kennwort für viele Konten).</span><span class="sxs-lookup"><span data-stu-id="6cb64-236">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="6cb64-237">Kenn Wort Sprüh Angriffe sind schwerer zu erkennen als Brute-Force-Kennwortangriffe (die Erfolgswahrscheinlichkeit steigt, wenn ein Angreifer ein Kennwort in Dutzenden oder Hunderten von Konten versucht, ohne dass die falsche Kenn Wort Sperrung des Benutzers ausgelöst wird).</span><span class="sxs-lookup"><span data-stu-id="6cb64-237">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="6cb64-238">Für den Kenn Wort Sprüh Angriff können Sie nur ein Kennwort angeben, das Sie ausprobieren möchten, und Sie können einen oder mehrere Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-238">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="6cb64-239">Die Kennwortangriffe im Angriffs Simulator übergeben Benutzernamen-und Kenn Wort grundlegende Authentifizierungsanforderungen an einen Endpunkt, sodass Sie auch mit anderen Authentifizierungsmethoden (AD FS, Kennworthash Synchronisierung, Pass-Through, PingFederate usw.) funktionieren.</span><span class="sxs-lookup"><span data-stu-id="6cb64-239">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="6cb64-240">Für Benutzer, die MFA aktiviert haben, wird der Versuch, selbst wenn der Kennwortangriff sein tatsächliches Kennwort versucht, immer als Fehler registriert (in anderen Worten: MFA-Benutzer werden nie in der Anzahl der **erfolgreichen Versuche** der Kampagne angezeigt).</span><span class="sxs-lookup"><span data-stu-id="6cb64-240">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="6cb64-241">Dies ist das erwartete Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="6cb64-241">This is the expected result.</span></span> <span data-ttu-id="6cb64-242">MFA ist eine primäre Methode zum Schutz vor Kennwortangriffen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-242">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="6cb64-243">Erstellen und Starten einer Kenn Wort Angriffs Kampagne</span><span class="sxs-lookup"><span data-stu-id="6cb64-243">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="6cb64-244">Wechseln Sie im Security & Compliance Center zum **Threat Management** \> - **Angriffs Simulator**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-244">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="6cb64-245">Wählen Sie auf der Seite **Angriffe simulieren** eine der folgenden Optionen basierend auf der Art der Kampagne aus, die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="6cb64-245">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="6cb64-246">Klicken Sie im Abschnitt **Brute-Force-Kennwort (Wörterbuchangriff)** auf **Angriff starten** , oder klicken Sie auf Angriff **Details** \> **starten**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-246">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="6cb64-247">Klicken Sie im Abschnitt **Kenn Wort Sprüh Angriff** auf **Angriff starten** oder auf Angriff **Details** \> **starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-247">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="6cb64-248">Der Assistent zum **Konfigurieren von Kennwortangriffen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="6cb64-248">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="6cb64-249">Geben Sie im Schritt **Start** einen eindeutigen Anzeigenamen für die Kampagne ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-249">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="6cb64-250">Führen Sie im Schritt **Zielbenutzer** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6cb64-250">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="6cb64-251">Klicken Sie auf **Adressbuch** , um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-251">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="6cb64-252">Jeder Zielempfänger muss über ein Exchange Online Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-252">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="6cb64-253">Wenn Sie auf **Filtern** und **anwenden** klicken, ohne Suchkriterien einzugeben, werden alle Empfänger zurückgegeben und zur Kampagne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="6cb64-253">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="6cb64-254">Klicken Sie auf **Import** dann auf **Dateiimport** , um einen durch Kommas getrennten Wert (CSV) oder eine durch die Datei getrennte Datei mit e-Mail-Adressen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="6cb64-254">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="6cb64-255">Jede Reihe muss die e-Mail-Adresse des Empfängers enthalten.</span><span class="sxs-lookup"><span data-stu-id="6cb64-255">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="6cb64-256">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-256">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="6cb64-257">Wählen Sie im Schritt **Angriffs Einstellungen auswählen** aus, welche Aktionen basierend auf dem Kampagnentyp vorgenommen werden sollen:</span><span class="sxs-lookup"><span data-stu-id="6cb64-257">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="6cb64-258">**Brute-Force-Kennwort (Wörterbuchangriff)**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="6cb64-258">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="6cb64-259">**Manuelles Eingeben von Kennwörtern**: Geben Sie in das Feld **EINGABETASTE drücken, um ein Kennwort hinzuzufügen** ein Kennwort ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="6cb64-259">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="6cb64-260">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="6cb64-260">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="6cb64-261">**Hochladen von Kennwörtern aus einer Wörterbuchdatei**: Klicken Sie auf **hochladen** , um eine vorhandene Textdatei zu importieren, die in jeder Zeile ein Kennwort enthält, und eine leere letzte Zeile.</span><span class="sxs-lookup"><span data-stu-id="6cb64-261">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="6cb64-262">Die Textdatei muss mindestens 10 MB groß sein und darf nicht mehr als 30000 Kennwörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="6cb64-262">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="6cb64-263">**Kenn Wort Sprüh Angriff**: Geben Sie in **den zu verwendenden Kennwörtern im Feld Angriff** ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="6cb64-263">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="6cb64-264">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-264">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="6cb64-265">Klicken Sie im Schritt **bestätigen** auf **Fertig stellen** , um die Kampagne zu starten.</span><span class="sxs-lookup"><span data-stu-id="6cb64-265">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="6cb64-266">Die von Ihnen angegebenen Kennwörter werden für Benutzer ausprobiert, die Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-266">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="6cb64-267">Anzeigen von kampagnenergebnissen</span><span class="sxs-lookup"><span data-stu-id="6cb64-267">View campaign results</span></span>

<span data-ttu-id="6cb64-268">Nachdem Sie eine Kampagne gestartet haben, können Sie den Fortschritt und die Ergebnisse auf der Seite Haupt **Angriffe simulieren** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="6cb64-268">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="6cb64-269">In aktiven Kampagnen wird eine Statusleiste, ein abgeschlossener Prozentwert und "(abgeschlossene Benutzer) von (Gesamtanzahl der Benutzer)" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6cb64-269">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="6cb64-270">Durch Klicken auf die Schaltfläche **Aktualisieren** wird der Status aller aktiven Kampagnen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="6cb64-270">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="6cb64-271">Sie können auch auf **Beenden** klicken, um eine aktive Kampagne zu beenden.</span><span class="sxs-lookup"><span data-stu-id="6cb64-271">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="6cb64-272">Wenn die Kampagne abgeschlossen ist, wird der Status in **Angriff abgeschlossen**geändert.</span><span class="sxs-lookup"><span data-stu-id="6cb64-272">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="6cb64-273">Sie können die Ergebnisse der Kampagne anzeigen, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="6cb64-273">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="6cb64-274">Klicken Sie auf der Seite Haupt **Angriffe simulieren** auf **Bericht anzeigen** unter dem Namen der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="6cb64-274">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="6cb64-275">Klicken Sie auf der Seite Haupt **Angriffe simulieren** auf **Angriffs Details** im Abschnitt für den Typ des Angriffs.</span><span class="sxs-lookup"><span data-stu-id="6cb64-275">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="6cb64-276">Wählen Sie auf der Seite **Angriffs Details** , die geöffnet wird, die Kampagne im Abschnitt **Angriffs Verlauf** aus.</span><span class="sxs-lookup"><span data-stu-id="6cb64-276">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="6cb64-277">Mit einer der vorherigen Aktionen gelangen Sie zu einer Seite mit dem Namen " **Angriffs Details**".</span><span class="sxs-lookup"><span data-stu-id="6cb64-277">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="6cb64-278">Die Informationen, die auf dieser Seite für jede Art von Kampagne zur Verfügung stehen, werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-278">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="6cb64-279">Kampagnenergebnisse für Spear-Phishing (Sammeln von Anmeldeinformationen)</span><span class="sxs-lookup"><span data-stu-id="6cb64-279">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="6cb64-280">Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="6cb64-280">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6cb64-281">Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="6cb64-281">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6cb64-282">**Zielgruppe der Gesamtbenutzer**</span><span class="sxs-lookup"><span data-stu-id="6cb64-282">**Total users targeted**</span></span>

- <span data-ttu-id="6cb64-283">**Erfolgreiche Versuche**: die Anzahl der Benutzer, die auf den Link geklickt **und** Ihre Anmeldeinformationen eingegeben haben (*beliebiger* Benutzername und Kennwortwert).</span><span class="sxs-lookup"><span data-stu-id="6cb64-283">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="6cb64-284">**Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen** / berechnet wird.**Gesamtzahl der Benutzer**, die gezielt sind.</span><span class="sxs-lookup"><span data-stu-id="6cb64-284">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6cb64-285">**Schnellster Mausklick**: wie lange es dauerte, bis der erste Benutzer auf den Link klickt, nachdem Sie die Kampagne gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-285">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="6cb64-286">**Durchschnittlicher Mausklick**: die Summe, wie lange es dauerte, bis jeder auf den Link geklickt hat, dividiert durch die Anzahl der Benutzer, die auf den Link geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-286">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="6cb64-287">**Klicken Sie auf Erfolgs Rate**: einen Prozentsatz, der von berechnet wird (Anzahl der Benutzer, die auf den Link geklickt haben)/Gesamtanzahl der Benutzer, die als **Ziel**ausgewählt wurden</span><span class="sxs-lookup"><span data-stu-id="6cb64-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="6cb64-288">**Schnellste Anmeldeinformationen**: wie lange dauerte es, bis der erste Benutzer seine Anmeldeinformationen eingegeben hat, nachdem die Kampagne gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="6cb64-288">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="6cb64-289">**Durchschnittliche Anmeldeinformationen**: die Summe der Dauer, die jeder zum Eingeben der Anmeldeinformationen benötigte, dividiert durch die Anzahl der Benutzer, die Ihre Anmeldeinformationen eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-289">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="6cb64-290">**Erfolgs Rate der Anmeldeinformationen**: ein Prozentsatz, der von berechnet wird (Anzahl der Benutzer, die Ihre Anmeldeinformationen eingegeben haben)/Gesamtanzahl der Benutzer, die **zielgerichtet**sind.</span><span class="sxs-lookup"><span data-stu-id="6cb64-290">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="6cb64-291">Ein Balkendiagramm, in dem der **Link geklickt** wird und die Anzahl der **Anmeldeinformationen** pro Tag angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="6cb64-291">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="6cb64-292">Ein Kreisdiagramm, in dem der **angeklickte Link**, die **angegebenen Anmeldeinformationen**und **keine** Prozentsätze für die Kampagne angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="6cb64-292">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="6cb64-293">Im Abschnitt **kompromittierte Benutzer** werden die Details der Benutzer aufgelistet, die auf den Link geklickt haben:</span><span class="sxs-lookup"><span data-stu-id="6cb64-293">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="6cb64-294">Die E-Mail-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="6cb64-294">The user's email address</span></span>

  - <span data-ttu-id="6cb64-295">Das Datum/die Uhrzeit, zu dem der Link geklickt hat.</span><span class="sxs-lookup"><span data-stu-id="6cb64-295">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="6cb64-296">Die Client-IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="6cb64-296">The client IP address.</span></span>

  - <span data-ttu-id="6cb64-297">Details zur Benutzerversion von Windows und Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="6cb64-297">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="6cb64-298">Sie können auf **exportieren** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="6cb64-298">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="6cb64-299">Kampagnenergebnisse für Spear-Phishing (Attachment)</span><span class="sxs-lookup"><span data-stu-id="6cb64-299">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="6cb64-300">Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="6cb64-300">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6cb64-301">Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="6cb64-301">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6cb64-302">**Zielgruppe der Gesamtbenutzer**</span><span class="sxs-lookup"><span data-stu-id="6cb64-302">**Total users targeted**</span></span>

- <span data-ttu-id="6cb64-303">**Erfolgreiche Versuche**: die Anzahl der Benutzer, die die Anlage geöffnet oder heruntergeladen und geöffnet haben (Vorschau wird nicht gezählt).</span><span class="sxs-lookup"><span data-stu-id="6cb64-303">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="6cb64-304">**Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen** / berechnet wird.**Gesamtzahl der Benutzer**, die gezielt sind.</span><span class="sxs-lookup"><span data-stu-id="6cb64-304">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6cb64-305">**Schnellste Anlage Open Time**: wie lange dauerte es, bis der erste Benutzer die Anlage geöffnet hat, nachdem Sie die Kampagne gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-305">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="6cb64-306">**Open Time (durchschnittliche Anlage**): die Summe der Dauer, die jeder zum Öffnen der Anlage benötigte, dividiert durch die Anzahl der Benutzer, die die Anlage geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="6cb64-306">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="6cb64-307">**Anlage offene Erfolgsrate**: ein Prozentsatz, der von berechnet wird (Anzahl der Benutzer, die die Anlage geöffnet haben)/Gesamtanzahl der **Zielbenutzer**.</span><span class="sxs-lookup"><span data-stu-id="6cb64-307">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="6cb64-308">Kampagnenergebnisse für Brute-Force-Kennwort (Wörterbuchangriffe)</span><span class="sxs-lookup"><span data-stu-id="6cb64-308">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="6cb64-309">Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="6cb64-309">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6cb64-310">Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="6cb64-310">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6cb64-311">**Zielgruppe der Gesamtbenutzer**</span><span class="sxs-lookup"><span data-stu-id="6cb64-311">**Total users targeted**</span></span>

- <span data-ttu-id="6cb64-312">**Erfolgreiche Versuche**: die Anzahl der Benutzer, bei denen festgestellt wurde, dass Sie eines der angegebenen Kennwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="6cb64-312">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="6cb64-313">**Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen** / berechnet wird.**Gesamtzahl der Benutzer**, die gezielt sind.</span><span class="sxs-lookup"><span data-stu-id="6cb64-313">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="6cb64-314">Im Abschnitt **kompromittierte Benutzer** werden die e-Mail-Adressen der betroffenen Benutzer aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="6cb64-314">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="6cb64-315">Sie können auf **exportieren** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="6cb64-315">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="6cb64-316">Kenn Wort Sprüh Angriff-Kampagnenergebnisse</span><span class="sxs-lookup"><span data-stu-id="6cb64-316">Password spray attack campaign results</span></span>

<span data-ttu-id="6cb64-317">Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="6cb64-317">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="6cb64-318">Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="6cb64-318">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="6cb64-319">**Zielgruppe der Gesamtbenutzer**</span><span class="sxs-lookup"><span data-stu-id="6cb64-319">**Total users targeted**</span></span>

- <span data-ttu-id="6cb64-320">**Erfolgreiche Versuche**: die Anzahl der Benutzer, für die das angegebene Kennwort verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="6cb64-320">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="6cb64-321">**Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen** / berechnet wird.**Gesamtzahl der Benutzer**, die gezielt sind.</span><span class="sxs-lookup"><span data-stu-id="6cb64-321">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
