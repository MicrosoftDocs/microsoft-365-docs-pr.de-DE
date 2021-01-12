---
title: Angriffssimulator in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: da5845db-c578-4a41-b2cb-5a09689a551b
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie mithilfe des Angriffssimulators simulierte Phishing- und Kennwortangriffe in ihren Microsoft 365 E5- oder Microsoft Defender für Office 365 Plan 2-Organisationen ausführen.
ms.openlocfilehash: 2ffec891f7b1021f3c6c51b003c78aacb0ec0d6a
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794532"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="7a479-103">Angriffssimulator in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="7a479-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="7a479-104">Wenn Ihre Organisation über Microsoft Defender für Office 365 Plan 2 verfügt, der Funktionen zur Bedrohungsuntersuchung und -reaktion [umfasst,](office-365-ti.md)können Sie den Angriffssimulator im Security & Compliance Center verwenden, um realistische Angriffsszenarien in Ihrer Organisation zu führen.</span><span class="sxs-lookup"><span data-stu-id="7a479-104">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="7a479-105">Diese simulierten Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren und zu finden, bevor sich ein tatsächlicher Angriff auf Ihr Endergebnis ausdingt.</span><span class="sxs-lookup"><span data-stu-id="7a479-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="7a479-106">Lesen Sie diesen Artikel, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="7a479-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="7a479-107">Angriffssimulations- und Schulungsdaten werden mit anderen Kundendaten für Microsoft 365-Dienste gespeichert.</span><span class="sxs-lookup"><span data-stu-id="7a479-107">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="7a479-108">Weitere Informationen finden Sie unter [Microsoft 365-Datenspeicherorte.](/microsoft-365/enterprise/o365-data-locations)</span><span class="sxs-lookup"><span data-stu-id="7a479-108">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

> [!TIP]
> <span data-ttu-id="7a479-109">Das Training zur Angriffssimulation ist für die öffentliche Vorschau im Microsoft 365 Security Center verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7a479-109">Attack simulation training is available for public preview in the Microsoft 365 security center.</span></span> <span data-ttu-id="7a479-110">Weitere Informationen finden Sie hier: Simulieren eines Phishingangriffs mit [Microsoft Defender für Office 365.](attack-simulation-training.md)</span><span class="sxs-lookup"><span data-stu-id="7a479-110">Check out [Simulate a phishing attack with Microsoft Defender for Office 365](attack-simulation-training.md) to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="7a479-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="7a479-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="7a479-112">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="7a479-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="7a479-113">Der Angriffssimulator ist im **Angriffssimulator für die Bedrohungsverwaltung** \> **verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="7a479-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="7a479-114">Wechseln Sie direkt zum Angriffssimulator, öffnen Sie <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="7a479-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="7a479-115">Weitere Informationen zur Verfügbarkeit des Angriffssimulators in verschiedenen Microsoft 365-Abonnements finden Sie in der [Microsoft Defender für Office 365-Dienstbeschreibung.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)</span><span class="sxs-lookup"><span data-stu-id="7a479-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="7a479-116">Sie müssen Mitglied der Rollengruppe **"Organisationsverwaltung"** oder **"Sicherheitsadministrator"** sein.</span><span class="sxs-lookup"><span data-stu-id="7a479-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="7a479-117">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="7a479-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="7a479-118">Ihr Konto muss für die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) konfiguriert sein, um Kampagnen im Angriffssimulator zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="7a479-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="7a479-119">Anweisungen finden Sie unter [Einrichten der mehrstufigen Authentifizierung.](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)</span><span class="sxs-lookup"><span data-stu-id="7a479-119">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="7a479-120">Phishingkampagnen sammeln und verarbeiten Ereignisse 30 Tage lang.</span><span class="sxs-lookup"><span data-stu-id="7a479-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="7a479-121">Verlaufsdaten für Kampagnen sind nach dem Start der Kampagne bis zu 90 Tage lang verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7a479-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="7a479-122">Es gibt keine entsprechenden PowerShell-Cmdlets für den Angriffssimulator.</span><span class="sxs-lookup"><span data-stu-id="7a479-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="7a479-123">Phishingkampagnen mit Speerspitze</span><span class="sxs-lookup"><span data-stu-id="7a479-123">Spear phishing campaigns</span></span>

<span data-ttu-id="7a479-124">*Phishing* ist ein allgemeiner Begriff für E-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die von legitimen oder vertrauenswürdigen Absendern zu sein scheinen.</span><span class="sxs-lookup"><span data-stu-id="7a479-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="7a479-125">*Bei Phishing* handelt es sich um einen gezielten Phishingangriff, bei dem fokussierte und angepasste Inhalte verwendet werden, die speziell auf die Zielempfänger zugeschnitten sind (in der Regel nach der Aufarbeitung der Empfänger durch den Angreifer).</span><span class="sxs-lookup"><span data-stu-id="7a479-125">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="7a479-126">Im Angriffssimulator sind zwei verschiedene Arten von Phishingkampagnen verfügbar:</span><span class="sxs-lookup"><span data-stu-id="7a479-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="7a479-127">**Phishing mit Phishing (Anmeldeinformationen)**– Der Angriff versucht, die Empfänger zu überzeugen, auf eine URL in der Nachricht zu klicken.</span><span class="sxs-lookup"><span data-stu-id="7a479-127">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="7a479-128">Wenn sie auf den Link klicken, werden sie aufgefordert, ihre Anmeldeinformationen ein eingeben.</span><span class="sxs-lookup"><span data-stu-id="7a479-128">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="7a479-129">Wenn sie dies tun, werden sie an einen der folgenden Speicherorte weiterverortet:</span><span class="sxs-lookup"><span data-stu-id="7a479-129">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="7a479-130">Eine Standardseite, auf der erläutert wird, dass dies nur ein Test war, und enthält Tipps zum Erkennen von Phishingnachrichten.</span><span class="sxs-lookup"><span data-stu-id="7a479-130">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Was Benutzer sehen, wenn sie auf den Phishinglink klicken und ihre Anmeldeinformationen eingeben](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="7a479-132">Eine benutzerdefinierte Seite (URL), die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="7a479-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="7a479-133">**Speerphishing (Anlage):** Der Angriff versucht, die Empfänger zu überzeugen, eine DOCX- oder PDF-Anlage in der Nachricht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="7a479-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="7a479-134">Die Anlage enthält den gleichen Inhalt des standardmäßigen Phishinglinks, aber der erste Satz beginnt mit " , Sie sehen diese Nachricht als kürzlich geöffnete E-Mail-Nachricht...". \<Display Name\></span><span class="sxs-lookup"><span data-stu-id="7a479-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="7a479-135">Derzeit laufen Phishingkampagnen im Angriffssimulator nicht ab.</span><span class="sxs-lookup"><span data-stu-id="7a479-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="7a479-136">Erstellen einer Phishingkampagne mit Phishing</span><span class="sxs-lookup"><span data-stu-id="7a479-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="7a479-137">Ein wichtiger Bestandteil jeder Phishingkampagne ist das Aussehen und Gefühl der E-Mail-Nachricht, die an die Zielempfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="7a479-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="7a479-138">Zum Erstellen und Konfigurieren der E-Mail-Nachricht stehen Ihnen die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="7a479-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="7a479-139">**Verwenden Sie eine integrierte E-Mail-Vorlage:** Es stehen zwei integrierte Vorlagen zur Verfügung: **"Giveaway"** und **"Payroll Update".**</span><span class="sxs-lookup"><span data-stu-id="7a479-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="7a479-140">Sie können einige, alle oder keine der E-Mail-Eigenschaften aus der Vorlage weiter anpassen, wenn Sie die Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="7a479-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="7a479-141">**Erstellen Sie eine wiederverwendbare** E-Mail-Vorlage: Nachdem Sie die E-Mail-Vorlage erstellt und gespeichert haben, können Sie sie in zukünftigen Phishingkampagnen erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a479-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="7a479-142">Sie können einige, alle oder keine der E-Mail-Eigenschaften aus der Vorlage weiter anpassen, wenn Sie die Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="7a479-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="7a479-143">**Erstellen Sie die E-Mail-Nachricht im** Assistenten: Sie können die E-Mail-Nachricht direkt im Assistenten erstellen, während Sie die Phishingkampagne für Die Speerspitze erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="7a479-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="7a479-144">Schritt 1 (Optional): Erstellen einer benutzerdefinierten E-Mail-Vorlage</span><span class="sxs-lookup"><span data-stu-id="7a479-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="7a479-145">Wenn Sie eine der integrierten Vorlagen verwenden oder die E-Mail-Nachricht direkt im Assistenten erstellen möchten, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="7a479-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="7a479-146">Wechseln Sie im Security & Compliance  Center zum Angriffssimulator für die \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="7a479-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="7a479-147">Klicken Sie **auf der Seite** "Simulierte Angriffe" in den Abschnitten "Phishing mit Anmeldeinformationen" oder **"Phishing(Anlage)"** auf **"Angriffsdetails".** </span><span class="sxs-lookup"><span data-stu-id="7a479-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="7a479-148">Es spielt keine Rolle, wo Sie die Vorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="7a479-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="7a479-149">Die verfügbaren Optionen in der Vorlage sind für beide Arten von Phishingangriffen identisch.</span><span class="sxs-lookup"><span data-stu-id="7a479-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="7a479-150">Klicken Sie **auf der Seite "Angriffsdetails",** die geöffnet wird, im Abschnitt **"Phishingvorlagen"** im Bereich "Vorlagen erstellen" auf **"Neue Vorlage".** </span><span class="sxs-lookup"><span data-stu-id="7a479-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="7a479-151">Der **Assistent zum Konfigurieren von Phishingvorlagen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="7a479-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="7a479-152">Geben Sie **im Startschritt** einen eindeutigen Anzeigenamen für die Vorlage ein, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="7a479-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="7a479-153">Konfigurieren Sie **im Schritt "E-Mail-Details** konfigurieren" die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="7a479-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="7a479-154">**From (Name):** Der Anzeigename, der für den Absender der Nachricht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7a479-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="7a479-155">**From (E-Mail):** Die E-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="7a479-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="7a479-156">**Phishing-Anmeldeserver-URL:** Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="7a479-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="7a479-157">Dies ist die URL, auf die Benutzer verlockend klicken.</span><span class="sxs-lookup"><span data-stu-id="7a479-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="7a479-158">Sie können wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="7a479-158">The choices are:</span></span>

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
     >
     > <span data-ttu-id="7a479-159">Ein URL-Reputationsdienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher.</span><span class="sxs-lookup"><span data-stu-id="7a479-159">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="7a479-160">Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a479-160">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="7a479-161">**URL der benutzerdefinierten** Startseite: Geben Sie eine optionale Zielseite ein, auf der Benutzer weitergeleitet werden, wenn sie auf den Phishinglink klicken und ihre Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="7a479-161">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="7a479-162">Dieser Link ersetzt die Standardmäßige Zielseite.</span><span class="sxs-lookup"><span data-stu-id="7a479-162">This link replaces the default landing page.</span></span> <span data-ttu-id="7a479-163">Wenn Sie beispielsweise eine interne Bewusstseinsschulung haben, können Sie diese URL hier angeben.</span><span class="sxs-lookup"><span data-stu-id="7a479-163">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="7a479-164">**Kategorie**: Derzeit wird diese Einstellung nicht verwendet (alles, was Sie eingeben, wird ignoriert).</span><span class="sxs-lookup"><span data-stu-id="7a479-164">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="7a479-165">**Betreff:** Das **Feld "Betreff"** der E-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="7a479-165">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="7a479-166">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7a479-166">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7a479-167">Erstellen Sie **im Schritt zum** Verfassen einer E-Mail den Nachrichtentext der E-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="7a479-167">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="7a479-168">Sie können die Registerkarte **"E-Mail"** (ein Rich-HTML-Editor) oder die Registerkarte **"Quelle"** (unformatiertes HTML-Code) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a479-168">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="7a479-169">Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="7a479-169">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="7a479-170">Sie können Bilder und Text einfügen, um die Gfähigkeit der Nachricht im E-Mail-Client des Empfängers zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="7a479-170">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="7a479-171">`${username}` fügt den Namen des Empfängers ein.</span><span class="sxs-lookup"><span data-stu-id="7a479-171">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="7a479-172">`${loginserverurl}` Fügt den Wert der **Phishing-Anmeldeserver-URL** aus dem vorherigen Schritt ein.</span><span class="sxs-lookup"><span data-stu-id="7a479-172">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="7a479-173">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7a479-173">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="7a479-174">Klicken Sie **im Schritt "Bestätigen"** auf **"Fertig stellen".**</span><span class="sxs-lookup"><span data-stu-id="7a479-174">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="7a479-175">Schritt 2: Erstellen und Starten der Phishingkampagne</span><span class="sxs-lookup"><span data-stu-id="7a479-175">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="7a479-176">Wechseln Sie im Security & Compliance  Center zum Angriffssimulator für die \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="7a479-176">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="7a479-177">Treffen Sie **auf** der Seite "Angriffe simulieren" eine der folgenden Optionen basierend auf dem Typ der Kampagne, die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="7a479-177">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="7a479-178">Klicken Sie **im Abschnitt "Phishing mit Phishing (Credentials Harvest)"** auf **"Angriff** starten" oder **"Angriffsdetails** \> **Starten".**</span><span class="sxs-lookup"><span data-stu-id="7a479-178">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="7a479-179">Klicken Sie **im Abschnitt "Phishing(Anlage)"** auf **"Angriff** starten" oder auf **"Angriffsdetails** \> **Starten".**</span><span class="sxs-lookup"><span data-stu-id="7a479-179">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="7a479-180">Der **Assistent zum Konfigurieren von Phishingangriffen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="7a479-180">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="7a479-181">Gehen Sie **im Startschritt** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="7a479-181">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="7a479-182">Geben Sie **in das Feld "Name"** einen eindeutigen Anzeigenamen für die Kampagne ein.</span><span class="sxs-lookup"><span data-stu-id="7a479-182">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="7a479-183">Klicken Sie nicht auf Vorlage **verwenden,** da Sie die E-Mail-Nachricht später im Assistenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="7a479-183">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="7a479-184">Klicken **Sie auf Vorlage verwenden,** und wählen Sie eine integrierte oder benutzerdefinierte E-Mail-Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="7a479-184">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="7a479-185">Nachdem Sie die Vorlage ausgewählt haben, wird das Feld **"Name"** automatisch basierend auf der Vorlage ausgefüllt, Aber Sie können den Namen ändern.</span><span class="sxs-lookup"><span data-stu-id="7a479-185">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Phishingstartseite](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="7a479-187">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7a479-187">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="7a479-188">Gehen Sie **im Schritt "Zielempfänger"** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="7a479-188">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="7a479-189">Klicken **Sie auf "Adressbuch",** um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="7a479-189">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="7a479-190">Jeder Zielempfänger muss über ein Exchange Online-Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="7a479-190">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="7a479-191">Wenn Sie auf **"Filtern"** und **"Anwenden"** klicken, ohne ein Suchkriterium ein eingeben zu müssen, werden alle Empfänger zurückgegeben und der Kampagne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7a479-191">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="7a479-192">Klicken **Sie auf "Importieren"** und dann **auf "Datei importieren",** um einen durch Kommas getrennten Wert (CSV) oder eine durch Zeilen getrennte Datei mit E-Mail-Adressen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="7a479-192">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="7a479-193">Jede Zeile muss die E-Mail-Adresse des Empfängers enthalten.</span><span class="sxs-lookup"><span data-stu-id="7a479-193">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="7a479-194">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7a479-194">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7a479-195">Konfigurieren Sie **im Schritt "E-Mail-Details** konfigurieren" die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="7a479-195">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="7a479-196">Wenn Sie im Startschritt eine Vorlage ausgewählt haben, sind die meisten dieser Werte bereits konfiguriert, sie können jedoch geändert werden. </span><span class="sxs-lookup"><span data-stu-id="7a479-196">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="7a479-197">**From (Name):** Der Anzeigename, der für den Absender der Nachricht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="7a479-197">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="7a479-198">**From (E-Mail):** Die E-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="7a479-198">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="7a479-199">Sie können eine echte oder gefälschte E-Mail-Adresse aus der E-Mail-Domäne Ihrer Organisation oder eine echte oder gefälschte externe E-Mail-Adresse eingeben.</span><span class="sxs-lookup"><span data-stu-id="7a479-199">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="7a479-200">Eine gültige Absender-E-Mail-Adresse aus Ihrer Organisation wird tatsächlich im E-Mail-Client des Empfängers aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="7a479-200">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="7a479-201">**Phishing-Anmeldeserver-URL:** Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="7a479-201">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="7a479-202">Dies ist die URL, auf die Benutzer verlockend klicken.</span><span class="sxs-lookup"><span data-stu-id="7a479-202">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="7a479-203">Sie können wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="7a479-203">The choices are:</span></span>

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
     >
     > - <span data-ttu-id="7a479-204">Alle URLs sind absichtlich http, nicht https.</span><span class="sxs-lookup"><span data-stu-id="7a479-204">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="7a479-205">Ein URL-Reputationsdienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher.</span><span class="sxs-lookup"><span data-stu-id="7a479-205">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="7a479-206">Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a479-206">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="7a479-207">Sie müssen eine URL auswählen.</span><span class="sxs-lookup"><span data-stu-id="7a479-207">You are required to select a URL.</span></span> <span data-ttu-id="7a479-208">Bei **Einer Phishingkampagne (Anlage)** können Sie den Link im nächsten Schritt aus dem Nachrichtentext entfernen  (andernfalls enthält die Nachricht sowohl einen Link als auch eine Anlage).</span><span class="sxs-lookup"><span data-stu-id="7a479-208">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="7a479-209">**Anlagentyp:** Diese Einstellung ist nur in **Phishingkampagnen (Anlagen)** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7a479-209">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="7a479-210">Klicken Sie auf die Dropdownliste, und wählen Sie **. DOCX oder** **. PDF** aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="7a479-210">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="7a479-211">**Anlagenname:** Diese Einstellung ist nur in **Phishingkampagnen (Anlagen)** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="7a479-211">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="7a479-212">Geben Sie einen Dateinamen für die DOCX- oder PDF-Anlage ein.</span><span class="sxs-lookup"><span data-stu-id="7a479-212">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="7a479-213">**URL der benutzerdefinierten** Startseite: Geben Sie eine optionale Zielseite ein, auf der Benutzer weitergeleitet werden, wenn sie auf den Phishinglink klicken und ihre Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="7a479-213">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="7a479-214">Dieser Link ersetzt die Standardmäßige Zielseite.</span><span class="sxs-lookup"><span data-stu-id="7a479-214">This link replaces the default landing page.</span></span> <span data-ttu-id="7a479-215">Wenn Sie beispielsweise eine interne Bewusstseinsschulung haben, können Sie diese URL hier angeben.</span><span class="sxs-lookup"><span data-stu-id="7a479-215">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="7a479-216">**Betreff:** Das **Feld "Betreff"** der E-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="7a479-216">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="7a479-217">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7a479-217">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7a479-218">Erstellen Sie **im Schritt zum** Verfassen einer E-Mail den Nachrichtentext der E-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="7a479-218">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="7a479-219">Wenn Sie im Startschritt eine Vorlage ausgewählt haben, ist der Nachrichtentext bereits konfiguriert, Sie können ihn jedoch anpassen. </span><span class="sxs-lookup"><span data-stu-id="7a479-219">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="7a479-220">Sie können die Registerkarte **"E-Mail"** (ein Rich-HTML-Editor) oder die Registerkarte **"Quelle"** (unformatiertes HTML-Code) verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a479-220">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="7a479-221">Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="7a479-221">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="7a479-222">Sie können Bilder und Text einfügen, um die Gfähigkeit der Nachricht im E-Mail-Client des Empfängers zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="7a479-222">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="7a479-223">`${username}` fügt den Namen des Empfängers ein.</span><span class="sxs-lookup"><span data-stu-id="7a479-223">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="7a479-224">`${loginserverurl}` Fügt den Wert der **Phishing-Anmeldeserver-URL** ein.</span><span class="sxs-lookup"><span data-stu-id="7a479-224">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="7a479-225">Für Kampagnen mit **Phishing (Anlage)** sollten Sie den Link aus dem Nachrichtentext entfernen (andernfalls enthält die Nachricht sowohl einen Link als auch eine Anlage, und Linkklicks werden in einer Anlagenkampagne nicht nachverfolgt). </span><span class="sxs-lookup"><span data-stu-id="7a479-225">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![Verfassen des E-Mail-Textkörpers](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="7a479-227">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7a479-227">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="7a479-228">Klicken Sie **im Schritt "Bestätigen"** auf **"Fertig** stellen", um die Kampagne zu starten.</span><span class="sxs-lookup"><span data-stu-id="7a479-228">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="7a479-229">Die Phishingnachricht wird an die Zielempfänger zugestellt.</span><span class="sxs-lookup"><span data-stu-id="7a479-229">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="7a479-230">Kennwortangriffskampagnen</span><span class="sxs-lookup"><span data-stu-id="7a479-230">Password attack campaigns</span></span>

<span data-ttu-id="7a479-231">Ein *Kennwortangriff versucht,* Kennwörter für Benutzerkonten in einer Organisation zu erraten, in der Regel, nachdem der Angreifer mindestens ein gültiges Benutzerkonto identifiziert hat.</span><span class="sxs-lookup"><span data-stu-id="7a479-231">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="7a479-232">Im Angriffssimulator stehen Ihnen zwei verschiedene Arten von Kennwortangriffskampagnen zur Verfügung, um die Komplexität der Kennwörter Ihrer Benutzer zu testen:</span><span class="sxs-lookup"><span data-stu-id="7a479-232">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="7a479-233">**Brute-Force-Kennwort (Wörterbuchangriff):** Ein  *Brute-Force-* oder Wörterbuchangriff verwendet eine große Wörterbuchdatei mit Kennwörtern für ein Benutzerkonto mit der Hoffen, dass eines davon funktioniert (viele Kennwörter für ein Konto).</span><span class="sxs-lookup"><span data-stu-id="7a479-233">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="7a479-234">Falsche Kennwortsperrungen helfen, Brute-Force-Kennwortangriffe zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="7a479-234">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="7a479-235">Für den Wörterbuchangriff können Sie ein oder mehrere Kennwörter angeben, die Sie ausprobieren möchten (manuell eingegeben oder in eine hochgeladene Datei), und Sie können einen oder mehrere Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="7a479-235">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="7a479-236">**Kennwort-Spray-Angriff:** Ein *Kennwort-Spray-Angriff* verwendet dasselbe sorgfältig überlegte Kennwort für eine Liste von Benutzerkonten (ein Kennwort für viele Konten).</span><span class="sxs-lookup"><span data-stu-id="7a479-236">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="7a479-237">Kennwort-Spray-Angriffe sind schwieriger zu erkennen als Brute-Force-Kennwortangriffe (die Erfolgswahrscheinlichkeit steigt, wenn ein Angreifer ein Kennwort über Dutzende oder Hunderte von Konten versucht, ohne das Risiko zu riskieren, dass das falsche Kennwort gesperrt wird).</span><span class="sxs-lookup"><span data-stu-id="7a479-237">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="7a479-238">Für den Kennwort-Spray-Angriff können Sie nur ein Kennwort angeben, das Sie testen möchten, und Sie können einen oder mehrere Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="7a479-238">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="7a479-239">Die Kennwortangriffe im Angriffssimulator übergeben benutzernamen- und kennwortbasierte Authentifizierungsanforderungen an einen Endpunkt, damit sie auch mit anderen Authentifizierungsmethoden (AD FS, Kennworthashsynchronisierung, Pass-Through, PingFederate usw.) funktionieren.</span><span class="sxs-lookup"><span data-stu-id="7a479-239">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="7a479-240">Für Benutzer, für die MFA aktiviert ist, wird der Versuch auch dann, wenn der Kennwortangriff sein **tatsächliches** Kennwort versucht, immer als Fehler registriert (mit anderen Worten, MFA-Benutzer werden nie in der Anzahl der erfolgreichen Versuche der Kampagne angezeigt).</span><span class="sxs-lookup"><span data-stu-id="7a479-240">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="7a479-241">Dies ist das erwartete Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="7a479-241">This is the expected result.</span></span> <span data-ttu-id="7a479-242">MFA ist eine primäre Methode zum Schutz vor Kennwortangriffen.</span><span class="sxs-lookup"><span data-stu-id="7a479-242">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="7a479-243">Erstellen und Starten einer Kennwortangriffskampagne</span><span class="sxs-lookup"><span data-stu-id="7a479-243">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="7a479-244">Wechseln Sie im Security & Compliance  Center zum Angriffssimulator für die \> **Bedrohungsverwaltung.**</span><span class="sxs-lookup"><span data-stu-id="7a479-244">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="7a479-245">Treffen Sie **auf** der Seite "Angriffe simulieren" eine der folgenden Optionen basierend auf dem Typ der Kampagne, die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="7a479-245">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="7a479-246">Klicken Sie **im Abschnitt "Brute Force Password (Dictionary Attack) "** auf **"Angriff** starten" oder auf **"Angriffsdetails** \> **Starten".**</span><span class="sxs-lookup"><span data-stu-id="7a479-246">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="7a479-247">Klicken Sie **im Abschnitt "Kennwort-Spray-Angriff"** auf **"Angriff starten"** oder auf **"Angriffsdetails** \> **Starten".**</span><span class="sxs-lookup"><span data-stu-id="7a479-247">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="7a479-248">Der **Assistent zum Konfigurieren von Kennwortangriffen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="7a479-248">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="7a479-249">Geben Sie **im Startschritt** einen eindeutigen Anzeigenamen für die Kampagne ein, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="7a479-249">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="7a479-250">Gehen Sie **im Schritt "Zielbenutzer"** wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="7a479-250">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="7a479-251">Klicken **Sie auf "Adressbuch",** um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="7a479-251">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="7a479-252">Jeder Zielempfänger muss über ein Exchange Online-Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="7a479-252">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="7a479-253">Wenn Sie auf **"Filtern"** und **"Anwenden"** klicken, ohne ein Suchkriterium ein eingeben zu müssen, werden alle Empfänger zurückgegeben und der Kampagne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="7a479-253">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="7a479-254">Klicken **Sie auf "Importieren"** und dann **auf "Datei importieren",** um einen durch Kommas getrennten Wert (CSV) oder eine durch Zeilen getrennte Datei mit E-Mail-Adressen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="7a479-254">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="7a479-255">Jede Zeile muss die E-Mail-Adresse des Empfängers enthalten.</span><span class="sxs-lookup"><span data-stu-id="7a479-255">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="7a479-256">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7a479-256">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="7a479-257">Wählen Sie **im Schritt "Angriffseinstellungen** auswählen" die Aktion basierend auf dem Kampagnentyp aus:</span><span class="sxs-lookup"><span data-stu-id="7a479-257">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="7a479-258">**Brute Force Password (Dictionary Attack):** Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="7a479-258">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="7a479-259">**Geben Sie Kennwörter manuell** ein: Geben Sie in **der** Eingabetaste ein Kennwortfeld ein, geben Sie ein Kennwort ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="7a479-259">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="7a479-260">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="7a479-260">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="7a479-261">**Hochladen von Kennwörtern** aus einer Wörterbuchdatei: Klicken Sie auf **"Hochladen",** um eine vorhandene Textdatei zu importieren, die ein Kennwort in jeder Zeile und eine leere letzte Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="7a479-261">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="7a479-262">Die Textdatei muss eine Größe von 10 MB oder weniger haben und darf nicht mehr als 30.000 Kennwörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="7a479-262">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="7a479-263">**Kennwort-Spray-Angriff:** Geben Sie in den **Kennwörtern,** die im Angriffsfeld verwendet werden, ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="7a479-263">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="7a479-264">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7a479-264">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="7a479-265">Klicken Sie **im Schritt "Bestätigen"** auf **"Fertig** stellen", um die Kampagne zu starten.</span><span class="sxs-lookup"><span data-stu-id="7a479-265">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="7a479-266">Die von Ihnen angegebenen Kennwörter werden für Benutzer ausprobiert, die Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="7a479-266">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="7a479-267">Anzeigen von Kampagnenergebnissen</span><span class="sxs-lookup"><span data-stu-id="7a479-267">View campaign results</span></span>

<span data-ttu-id="7a479-268">Nachdem Sie eine Kampagne gestartet haben, können Sie den Fortschritt und die Ergebnisse auf der Hauptseite "Simulierte **Angriffe"** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7a479-268">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="7a479-269">Aktive Kampagnen zeigen eine Statusleiste, einen abgeschlossenen Prozentsatz und die Anzahl "(abgeschlossene Benutzer) (Gesamtbenutzer)" an.</span><span class="sxs-lookup"><span data-stu-id="7a479-269">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="7a479-270">Durch Klicken **auf** die Schaltfläche "Aktualisieren" wird der Fortschritt aller aktiven Kampagnen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="7a479-270">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="7a479-271">Sie können auch auf **"Beenden" klicken,** um eine aktive Kampagne zu beenden.</span><span class="sxs-lookup"><span data-stu-id="7a479-271">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="7a479-272">Wenn die Kampagne abgeschlossen ist, ändert sich der Status in **Angriff abgeschlossen**.</span><span class="sxs-lookup"><span data-stu-id="7a479-272">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="7a479-273">Sie können die Ergebnisse der Kampagne anzeigen, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="7a479-273">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="7a479-274">Klicken Sie auf der Hauptseite **"Angriffe** **simulieren"** unter dem Namen der Kampagne auf "Bericht anzeigen".</span><span class="sxs-lookup"><span data-stu-id="7a479-274">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="7a479-275">Klicken Sie **auf** der Hauptseite "Simulierte Angriffe" im Abschnitt auf **"Angriffsdetails"** für den Angriffstyp.</span><span class="sxs-lookup"><span data-stu-id="7a479-275">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="7a479-276">Wählen Sie **auf der Seite "Angriffsdetails",** die geöffnet wird, die Kampagne im Abschnitt **"Angriffsverlauf"** aus.</span><span class="sxs-lookup"><span data-stu-id="7a479-276">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="7a479-277">Mit einer der vorherigen Aktionen gelangen Sie zu einer Seite mit dem Namen **"Angriffsdetails".**</span><span class="sxs-lookup"><span data-stu-id="7a479-277">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="7a479-278">Die Informationen, die auf dieser Seite für jeden Kampagnentyp verfügbar sind, werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="7a479-278">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="7a479-279">Phishing (Credentials Harvest) – Kampagnenergebnisse</span><span class="sxs-lookup"><span data-stu-id="7a479-279">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="7a479-280">Die folgenden Informationen sind auf der Seite **"Angriffsdetails"** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="7a479-280">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="7a479-281">Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="7a479-281">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="7a479-282">**Gesamtzahl der benutzerorientierten Benutzer**</span><span class="sxs-lookup"><span data-stu-id="7a479-282">**Total users targeted**</span></span>

- <span data-ttu-id="7a479-283">**Erfolgreiche Versuche:** Die Anzahl der Benutzer,  die auf den Link geklickt und ihre Anmeldeinformationen eingegeben haben *(beliebiger* Benutzername und Kennwortwert).</span><span class="sxs-lookup"><span data-stu-id="7a479-283">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="7a479-284">**Gesamterfolgsrate:** Ein Prozentsatz, der von erfolgreichen Versuchen berechnet  /  **wird. Zielbenutzer insgesamt.**</span><span class="sxs-lookup"><span data-stu-id="7a479-284">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="7a479-285">**Schnellster Klick:** Wie lange es ge dauere, bis der erste Benutzer auf den Link geklickt hat, nachdem Sie die Kampagne gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="7a479-285">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="7a479-286">**Durchschnittlicher Klick:** Die Summe, wie lange es ge dauern hat, bis alle Benutzer auf den Link geklickt haben, dividiert durch die Anzahl der Benutzer, die auf den Link geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="7a479-286">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="7a479-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span><span class="sxs-lookup"><span data-stu-id="7a479-287">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="7a479-288">**Schnellste Anmeldeinformationen:** Wie lange es ge dauern hat, bis der erste Benutzer seine Anmeldeinformationen eingegeben hat, nachdem Sie die Kampagne gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="7a479-288">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="7a479-289">**Durchschnittliche** Anmeldeinformationen: Die Summe der Zeit, die jeder für die Eingabe seiner Anmeldeinformationen brauchte, dividiert durch die Anzahl der Benutzer, die ihre Anmeldeinformationen eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="7a479-289">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="7a479-290">**Erfolgsrate für Anmeldeinformationen:** Ein Prozentsatz, der von (Anzahl der Benutzer, die ihre Anmeldeinformationen eingegeben haben) / der Gesamtzahl der **benutzerorientierten Benutzer berechnet wird.**</span><span class="sxs-lookup"><span data-stu-id="7a479-290">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="7a479-291">Ein Balkendiagramm, das zeigt, auf den **link geklickt** und **Anmeldeinformationen Zahlen** pro Tag angegeben.</span><span class="sxs-lookup"><span data-stu-id="7a479-291">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="7a479-292">Ein Kreisdiagramm, das zeigt, auf den **Link geklickt** **wurde,** die angegebenen Anmeldeinformationen und die Prozentsätze **"Keine"** für die Kampagne.</span><span class="sxs-lookup"><span data-stu-id="7a479-292">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="7a479-293">Im **Abschnitt "Gefährdete Benutzer"** werden die Details der Benutzer aufgeführt, die auf den Link geklickt haben:</span><span class="sxs-lookup"><span data-stu-id="7a479-293">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="7a479-294">Die E-Mail-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="7a479-294">The user's email address</span></span>

  - <span data-ttu-id="7a479-295">Datum/Uhrzeit, an dem/der auf den Link geklickt wurde.</span><span class="sxs-lookup"><span data-stu-id="7a479-295">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="7a479-296">Die Client-IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="7a479-296">The client IP address.</span></span>

  - <span data-ttu-id="7a479-297">Details zur Windows- und Webbrowserversion des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="7a479-297">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="7a479-298">Sie können auf **"Exportieren"** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="7a479-298">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="7a479-299">Kampagnenergebnisse für Das Phishing (Anlage)</span><span class="sxs-lookup"><span data-stu-id="7a479-299">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="7a479-300">Die folgenden Informationen sind auf der Seite **"Angriffsdetails"** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="7a479-300">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="7a479-301">Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="7a479-301">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="7a479-302">**Gesamtzahl der benutzerorientierten Benutzer**</span><span class="sxs-lookup"><span data-stu-id="7a479-302">**Total users targeted**</span></span>

- <span data-ttu-id="7a479-303">**Erfolgreiche Versuche:** Die Anzahl der Benutzer, die die Anlage geöffnet oder heruntergeladen und geöffnet haben (Die Vorschau zählt nicht).</span><span class="sxs-lookup"><span data-stu-id="7a479-303">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="7a479-304">**Gesamterfolgsrate:** Ein Prozentsatz, der von erfolgreichen Versuchen berechnet  /  **wird. Zielbenutzer insgesamt.**</span><span class="sxs-lookup"><span data-stu-id="7a479-304">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="7a479-305">**Schnellste Anlagenöffnzeit:** Wie lange das Öffnen der Anlage durch den ersten Benutzer nach dem Starten der Kampagne gezeit hat.</span><span class="sxs-lookup"><span data-stu-id="7a479-305">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="7a479-306">**Durchschnittliche Anlageneröffnungszeit:** Die Summe der Zeit, in der alle Benutzer die Anlage geöffnet haben, dividiert durch die Anzahl der Benutzer, die die Anlage geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="7a479-306">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="7a479-307">**Erfolgsrate für anlagenöffnend:** Ein Prozentsatz, der von (Anzahl der Benutzer, die die Anlage geöffnet haben) /Gesamtzahl der **benutzerorientierten berechnet wird.**</span><span class="sxs-lookup"><span data-stu-id="7a479-307">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="7a479-308">Brute Force Password (Dictionary Attack)-Kampagnenergebnisse</span><span class="sxs-lookup"><span data-stu-id="7a479-308">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="7a479-309">Die folgenden Informationen sind auf der Seite **"Angriffsdetails"** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="7a479-309">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="7a479-310">Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="7a479-310">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="7a479-311">**Gesamtzahl der benutzerorientierten Benutzer**</span><span class="sxs-lookup"><span data-stu-id="7a479-311">**Total users targeted**</span></span>

- <span data-ttu-id="7a479-312">**Erfolgreiche Versuche:** Die Anzahl der Benutzer, die eines der angegebenen Kennwörter verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="7a479-312">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="7a479-313">**Gesamterfolgsrate:** Ein Prozentsatz, der von erfolgreichen Versuchen berechnet  /  **wird. Zielbenutzer insgesamt.**</span><span class="sxs-lookup"><span data-stu-id="7a479-313">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="7a479-314">Im **Abschnitt "Gefährdete Benutzer"** werden die E-Mail-Adressen der betroffenen Benutzer aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="7a479-314">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="7a479-315">Sie können auf **"Exportieren"** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="7a479-315">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="7a479-316">Ergebnisse der Kennwort-Spray-Angriffskampagne</span><span class="sxs-lookup"><span data-stu-id="7a479-316">Password spray attack campaign results</span></span>

<span data-ttu-id="7a479-317">Die folgenden Informationen sind auf der Seite **"Angriffsdetails"** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="7a479-317">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="7a479-318">Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="7a479-318">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="7a479-319">**Gesamtzahl der benutzerorientierten Benutzer**</span><span class="sxs-lookup"><span data-stu-id="7a479-319">**Total users targeted**</span></span>

- <span data-ttu-id="7a479-320">**Erfolgreiche Versuche:** Die Anzahl der Benutzer, die gefunden wurden, dass sie das angegebene Kennwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="7a479-320">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="7a479-321">**Gesamterfolgsrate:** Ein Prozentsatz, der von erfolgreichen Versuchen berechnet  /  **wird. Zielbenutzer insgesamt.**</span><span class="sxs-lookup"><span data-stu-id="7a479-321">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
