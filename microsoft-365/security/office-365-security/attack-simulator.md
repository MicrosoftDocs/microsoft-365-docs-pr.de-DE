---
title: Angriffssimulator in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
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
description: Administratoren erfahren, wie Sie den Angriffssimulator zum Ausführen simulierter Phishing- und Kennwortangriffe in ihren Microsoft 365 E5- oder Microsoft Defender for Office 365 Plan 2-Organisationen verwenden.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 105ca66cdfacaab3b73d8bf89c3a05207b673a3c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921360"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="87424-103">Angriffssimulator in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="87424-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="87424-104">**Gilt für** [Microsoft Defender für Office 365 Plan 2](office-365-atp.md)</span><span class="sxs-lookup"><span data-stu-id="87424-104">**Applies to** [Microsoft Defender for Office 365 plan 2](office-365-atp.md)</span></span>

<span data-ttu-id="87424-105">Wenn Ihre Organisation über Microsoft Defender für Office 365 Plan 2 verfügt, der Funktionen zur Untersuchung und Reaktion auf Bedrohungen [umfasst,](office-365-ti.md)können Sie den Angriffssimulator im Security & Compliance Center verwenden, um realistische Angriffsszenarien in Ihrer Organisation ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="87424-105">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="87424-106">Diese simulierten Angriffe können Ihnen helfen, anfällige Benutzer zu identifizieren und zu finden, bevor sich ein tatsächlicher Angriff auf Ihr Endergebnis aus wirkt.</span><span class="sxs-lookup"><span data-stu-id="87424-106">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="87424-107">Weitere Informationen finden Sie in diesem Artikel.</span><span class="sxs-lookup"><span data-stu-id="87424-107">Read this article to learn more.</span></span>

> [!NOTE]
>
> <span data-ttu-id="87424-108">Der Angriffssimulator wie in diesem Artikel beschrieben  ist jetzt schreibgeschützt und wurde durch Angriffssimulationsschulungen im Knoten **E-Mail & Zusammenarbeit** im [Microsoft 365 Security Center ersetzt.](https://security.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="87424-108">Attack Simulator as described in this article is now read-only and has been replaced by **Attack simulation training** in the **Email & collaboration** node in the [Microsoft 365 security center](https://security.microsoft.com).</span></span> <span data-ttu-id="87424-109">Weitere Informationen finden Sie unter [Erste Schritte mit attack simulation training](attack-simulation-training-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="87424-109">For more information, see [Get started using Attack simulation training](attack-simulation-training-get-started.md).</span></span>
>
> <span data-ttu-id="87424-110">Die Möglichkeit, neue Simulationen aus dieser Version des Angriffssimulators zu starten, wurde deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="87424-110">The ability to launch new simulations from this version of Attack Simulator has been disabled.</span></span> <span data-ttu-id="87424-111">Sie können jedoch ab dem 24. Januar 2021 bis zu 90 Tage lang auf Berichte zugreifen.</span><span class="sxs-lookup"><span data-stu-id="87424-111">However, you can still access reports for up to 90 days from January 24, 2021.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="87424-112">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="87424-112">What do you need to know before you begin?</span></span>

- <span data-ttu-id="87424-113">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="87424-113">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="87424-114">Der Angriffssimulator ist unter **Threat Management** \> **Attack simulator verfügbar.**</span><span class="sxs-lookup"><span data-stu-id="87424-114">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="87424-115">Wechseln Sie direkt zum Angriffssimulator, öffnen Sie <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="87424-115">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="87424-116">Weitere Informationen zur Verfügbarkeit von Attack Simulator für verschiedene Microsoft 365-Abonnements finden Sie unter [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="87424-116">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="87424-117">Sie müssen Mitglied der Rollengruppen **Organisationsverwaltung** oder **Sicherheitsadministrator** sein.</span><span class="sxs-lookup"><span data-stu-id="87424-117">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="87424-118">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="87424-118">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="87424-119">Ihr Konto muss für die mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) konfiguriert werden, um Kampagnen im Angriffssimulator zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="87424-119">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="87424-120">Anweisungen finden Sie unter [Einrichten der mehrstufigen Authentifizierung](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="87424-120">For instructions, see [Set up multi-factor authentication](../../admin/security-and-compliance/set-up-multi-factor-authentication.md).</span></span>

- <span data-ttu-id="87424-121">Der Angriffssimulator funktioniert nur für cloudbasierte Postfächer.</span><span class="sxs-lookup"><span data-stu-id="87424-121">Attack Simulator only works on cloud-based mailboxes.</span></span>

- <span data-ttu-id="87424-122">Phishingkampagnen sammeln und verarbeiten Ereignisse für 30 Tage.</span><span class="sxs-lookup"><span data-stu-id="87424-122">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="87424-123">Verlaufskampagnendaten sind bis zu 90 Tage nach dem Starten der Kampagne verfügbar.</span><span class="sxs-lookup"><span data-stu-id="87424-123">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="87424-124">Angriffssimulations- und Schulungsdaten werden mit anderen Kundendaten für Microsoft 365-Dienste gespeichert.</span><span class="sxs-lookup"><span data-stu-id="87424-124">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="87424-125">Weitere Informationen finden Sie unter [Microsoft 365 Data Locations](../../enterprise/o365-data-locations.md).</span><span class="sxs-lookup"><span data-stu-id="87424-125">For more information see [Microsoft 365 data locations](../../enterprise/o365-data-locations.md).</span></span>

- <span data-ttu-id="87424-126">Es gibt keine entsprechenden PowerShell-Cmdlets für Den Angriffssimulator.</span><span class="sxs-lookup"><span data-stu-id="87424-126">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="87424-127">Phishingkampagnen für Speerer</span><span class="sxs-lookup"><span data-stu-id="87424-127">Spear phishing campaigns</span></span>

<span data-ttu-id="87424-128">*Phishing* ist ein allgemeiner Begriff für E-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die von legitimen oder vertrauenswürdigen Absendern zu sein scheinen.</span><span class="sxs-lookup"><span data-stu-id="87424-128">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="87424-129">*Bei Dem Phishing* handelt es sich um einen gezielten Phishingangriff, bei dem fokussierte und angepasste Inhalte verwendet werden, die speziell auf die Zielempfänger zugeschnitten sind (in der Regel nach der Aufklärung der Empfänger durch den Angreifer).</span><span class="sxs-lookup"><span data-stu-id="87424-129">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="87424-130">Im Angriffssimulator stehen zwei verschiedene Arten von Speerphishingkampagnen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="87424-130">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="87424-131">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span><span class="sxs-lookup"><span data-stu-id="87424-131">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="87424-132">Wenn sie auf den Link klicken, werden sie aufgefordert, ihre Anmeldeinformationen ein eingeben.</span><span class="sxs-lookup"><span data-stu-id="87424-132">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="87424-133">In diesem Beispiel werden sie an einen der folgenden Speicherorte übernommen:</span><span class="sxs-lookup"><span data-stu-id="87424-133">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="87424-134">Eine Standardseite, auf der erklärt wird, dass dies nur ein Test war, und gibt Tipps zum Erkennen von Phishingnachrichten.</span><span class="sxs-lookup"><span data-stu-id="87424-134">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Was Benutzer sehen, wenn sie auf den Phishinglink klicken und ihre Anmeldeinformationen eingeben](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="87424-136">Eine benutzerdefinierte Seite (URL), die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="87424-136">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="87424-137">**Speerphishing (Anlage)**: Der Angriff versucht, die Empfänger davon zu überzeugen, eine .docx- oder .pdf-Anlage in der Nachricht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="87424-137">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="87424-138">Die Anlage enthält den gleichen Inhalt aus dem Standardmäßigen Phishinglink, aber der erste Satz beginnt mit " , Sie sehen diese Nachricht als kürzlich geöffnete \<Display Name\> E-Mail-Nachricht...".</span><span class="sxs-lookup"><span data-stu-id="87424-138">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="87424-139">Derzeit laufen Speerphishingkampagnen im Angriffssimulator nicht ab.</span><span class="sxs-lookup"><span data-stu-id="87424-139">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="87424-140">Erstellen einer Speerphishingkampagne</span><span class="sxs-lookup"><span data-stu-id="87424-140">Create a spear phishing campaign</span></span>

<span data-ttu-id="87424-141">Ein wichtiger Bestandteil jeder Speerphishingkampagne ist das Aussehen und Gefühl der E-Mail-Nachricht, die an die Zielempfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="87424-141">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="87424-142">Zum Erstellen und Konfigurieren der E-Mail-Nachricht stehen Ihnen die folgenden Optionen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="87424-142">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="87424-143">**Verwenden Sie eine integrierte E-Mail-Vorlage:** Zwei integrierte Vorlagen sind verfügbar: Preiszusend und **Gehaltsabrechnungsupdate**. </span><span class="sxs-lookup"><span data-stu-id="87424-143">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="87424-144">Sie können einige, alle oder keine der E-Mail-Eigenschaften aus der Vorlage weiter anpassen, wenn Sie die Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="87424-144">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="87424-145">**Erstellen einer wiederverwendbaren** E-Mail-Vorlage: Nachdem Sie die E-Mail-Vorlage erstellt und gespeichert haben, können Sie sie in zukünftigen Phishingkampagnen erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="87424-145">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="87424-146">Sie können einige, alle oder keine der E-Mail-Eigenschaften aus der Vorlage weiter anpassen, wenn Sie die Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="87424-146">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="87424-147">**Erstellen Sie die E-Mail-Nachricht** im Assistenten: Sie können die E-Mail-Nachricht direkt im Assistenten erstellen, während Sie die Speerphishingkampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="87424-147">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="87424-148">Schritt 1 (Optional): Erstellen einer benutzerdefinierten E-Mail-Vorlage</span><span class="sxs-lookup"><span data-stu-id="87424-148">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="87424-149">Wenn Sie eine der integrierten Vorlagen verwenden oder die E-Mail-Nachricht direkt im Assistenten erstellen möchten, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="87424-149">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="87424-150">Wechseln Sie im Security & Compliance Center zu **Angriffssimulator für die Bedrohungsverwaltung.** \> </span><span class="sxs-lookup"><span data-stu-id="87424-150">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="87424-151">Klicken Sie **auf der Seite** Angriffe simulieren in den Abschnitten Spear Phishing **(Credentials Harvest)** oder **Spear Phishing (Attachment)** auf **Angriffsdetails**.</span><span class="sxs-lookup"><span data-stu-id="87424-151">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="87424-152">Es spielt keine Rolle, wo Sie die Vorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="87424-152">It doesn't matter where you create the template.</span></span> <span data-ttu-id="87424-153">Die verfügbaren Optionen in der Vorlage sind für beide Arten von Phishingangriffen identisch.</span><span class="sxs-lookup"><span data-stu-id="87424-153">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="87424-154">Klicken Sie auf der Seite **Angriffsdetails,** die  geöffnet wird, im Abschnitt **Phishingvorlagen** im Bereich Vorlagen erstellen auf **Neue Vorlage**.</span><span class="sxs-lookup"><span data-stu-id="87424-154">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="87424-155">Der **Assistent zum** Konfigurieren von Phishingvorlagen wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="87424-155">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="87424-156">Geben Sie **im Schritt Start** einen eindeutigen Anzeigenamen für die Vorlage ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87424-156">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="87424-157">Konfigurieren Sie **im Schritt** Konfigurieren von E-Mail-Details die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="87424-157">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="87424-158">**From (Name)**: Der Anzeigename, der für den Nachrichtensender verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87424-158">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="87424-159">**From (Email)**: Die E-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="87424-159">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="87424-160">**Phishing-Anmeldeserver-URL:** Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="87424-160">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="87424-161">Dies ist die URL, auf die Benutzer versucht sind zu klicken.</span><span class="sxs-lookup"><span data-stu-id="87424-161">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="87424-162">Sie können wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="87424-162">The choices are:</span></span>

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
     > <span data-ttu-id="87424-163">Ein URL-Reputationsdienst identifiziert eine oder mehrere dieser URLs möglicherweise als unsicher.</span><span class="sxs-lookup"><span data-stu-id="87424-163">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="87424-164">Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="87424-164">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="87424-165">**Url der benutzerdefinierten** Zielseite: Geben Sie eine optionale Zielseite ein, auf der Benutzer aufgenommen werden, wenn sie auf den Phishinglink klicken und ihre Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="87424-165">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="87424-166">Dieser Link ersetzt die Standardlandeseite.</span><span class="sxs-lookup"><span data-stu-id="87424-166">This link replaces the default landing page.</span></span> <span data-ttu-id="87424-167">Wenn Sie beispielsweise über ein internes Sensibilisierungstraining verfügen, können Sie diese URL hier angeben.</span><span class="sxs-lookup"><span data-stu-id="87424-167">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="87424-168">**Kategorie**: Derzeit wird diese Einstellung nicht verwendet (alles, was Sie eingeben, wird ignoriert).</span><span class="sxs-lookup"><span data-stu-id="87424-168">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="87424-169">**Betreff**: Das **Betrefffeld** der E-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="87424-169">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="87424-170">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87424-170">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="87424-171">Erstellen Sie **im Schritt** E-Mail verfassen den Nachrichtentext der E-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="87424-171">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="87424-172">Sie können die Registerkarte **E-Mail** (ein Rich-HTML-Editor) oder die **Registerkarte Quelle** (html-Rohcode) verwenden.</span><span class="sxs-lookup"><span data-stu-id="87424-172">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="87424-173">Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="87424-173">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="87424-174">Sie können Bilder und Text einfügen, um die Glaubhaftigkeit der Nachricht im E-Mail-Client des Empfängers zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="87424-174">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="87424-175">`${username}` fügt den Namen des Empfängers ein.</span><span class="sxs-lookup"><span data-stu-id="87424-175">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="87424-176">`${loginserverurl}` fügt den **Wert der Phishing-Anmeldeserver-URL** aus dem vorherigen Schritt ein.</span><span class="sxs-lookup"><span data-stu-id="87424-176">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="87424-177">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87424-177">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="87424-178">Klicken Sie **im Schritt** Bestätigen auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="87424-178">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="87424-179">Schritt 2: Erstellen und Starten der Speerphishingkampagne</span><span class="sxs-lookup"><span data-stu-id="87424-179">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="87424-180">Wechseln Sie im Security & Compliance Center zu **Angriffssimulator für die Bedrohungsverwaltung.** \> </span><span class="sxs-lookup"><span data-stu-id="87424-180">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="87424-181">Treffen Sie **auf** der Seite Angriffe simulieren eine der folgenden Auswahlen basierend auf dem Typ der Kampagne, die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="87424-181">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="87424-182">Klicken Sie **im Abschnitt Spear Phishing (Credentials Harvest)** auf Angriff **starten** oder **Angriffsdetails** \> **Starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="87424-182">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="87424-183">Klicken Sie **im Abschnitt Speerphishing (Anlage)** auf **Angriff starten** oder **Angriffsdetails** \> **Starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="87424-183">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="87424-184">Der **Assistent zum Konfigurieren von Phishingangriffen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="87424-184">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="87424-185">Gehen Sie **im Schritt** Start wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="87424-185">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="87424-186">Geben Sie **im Feld Name** einen eindeutigen Anzeigenamen für die Kampagne ein.</span><span class="sxs-lookup"><span data-stu-id="87424-186">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="87424-187">Klicken Sie nicht auf **Vorlage verwenden,** da Sie die E-Mail-Nachricht später im Assistenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="87424-187">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="87424-188">Klicken **Sie auf Vorlage verwenden,** und wählen Sie eine integrierte oder benutzerdefinierte E-Mail-Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="87424-188">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="87424-189">Nachdem Sie die Vorlage ausgewählt haben, wird das **Feld Name** basierend auf der Vorlage automatisch gefüllt, Sie können den Namen jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="87424-189">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="87424-190">![Phishing-Startseite](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span><span class="sxs-lookup"><span data-stu-id="87424-190">![Phishing Start Page](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)</span></span>

   <span data-ttu-id="87424-191">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87424-191">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="87424-192">Gehen Sie **im Schritt** Zielempfänger wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="87424-192">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="87424-193">Klicken **Sie auf Adressbuch,** um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="87424-193">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="87424-194">Jeder Zielempfänger muss über ein Exchange Online-Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="87424-194">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="87424-195">Wenn Sie auf **Filtern** und **Anwenden** klicken, ohne ein Suchkriterium ein eingeben zu müssen, werden alle Empfänger zurückgegeben und der Kampagne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="87424-195">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="87424-196">Klicken **Sie auf Importieren** und anschließend auf **Dateiimport,** um einen durch Kommas getrennten Wert (CSV) oder eine zeilenge trennte Datei mit E-Mail-Adressen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="87424-196">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="87424-197">Jede Zeile muss die E-Mail-Adresse des Empfängers enthalten.</span><span class="sxs-lookup"><span data-stu-id="87424-197">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="87424-198">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87424-198">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="87424-199">Konfigurieren Sie **im Schritt** Konfigurieren von E-Mail-Details die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="87424-199">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="87424-200">Wenn Sie im Schritt **Start** eine Vorlage ausgewählt haben, sind die meisten dieser Werte bereits konfiguriert, Sie können sie jedoch ändern.</span><span class="sxs-lookup"><span data-stu-id="87424-200">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="87424-201">**From (Name)**: Der Anzeigename, der für den Nachrichtensender verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="87424-201">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="87424-202">**From (Email)**: Die E-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="87424-202">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="87424-203">Sie können eine echte oder gefälschte E-Mail-Adresse aus der E-Mail-Domäne Ihrer Organisation eingeben, oder Sie können eine echte oder gefälschte externe E-Mail-Adresse eingeben.</span><span class="sxs-lookup"><span data-stu-id="87424-203">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="87424-204">Eine gültige Absender-E-Mail-Adresse aus Ihrer Organisation wird tatsächlich im E-Mail-Client des Empfängers aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="87424-204">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="87424-205">**Phishing-Anmeldeserver-URL:** Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="87424-205">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="87424-206">Dies ist die URL, auf die Benutzer versucht sind zu klicken.</span><span class="sxs-lookup"><span data-stu-id="87424-206">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="87424-207">Sie können wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="87424-207">The choices are:</span></span>

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
     > - <span data-ttu-id="87424-208">Alle URLs sind absichtlich http, nicht https.</span><span class="sxs-lookup"><span data-stu-id="87424-208">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="87424-209">Ein URL-Reputationsdienst identifiziert eine oder mehrere dieser URLs möglicherweise als unsicher.</span><span class="sxs-lookup"><span data-stu-id="87424-209">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="87424-210">Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishingkampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="87424-210">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="87424-211">Sie müssen eine URL auswählen.</span><span class="sxs-lookup"><span data-stu-id="87424-211">You are required to select a URL.</span></span> <span data-ttu-id="87424-212">Bei **Spear Phishing (Attachment)-Kampagnen** können Sie den Link im nächsten Schritt aus dem Nachrichtentext entfernen  (andernfalls enthält die Nachricht sowohl einen Link als auch eine Anlage).</span><span class="sxs-lookup"><span data-stu-id="87424-212">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="87424-213">**Anlagentyp**: Diese Einstellung ist nur in **Spear Phishing (Attachment)-Kampagnen** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="87424-213">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="87424-214">Klicken Sie auf die Dropdownliste, und wählen Sie **aus. DOCX** oder **. PDF** aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="87424-214">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="87424-215">**Anlagenname**: Diese Einstellung ist nur in **Spear Phishing (Attachment)-Kampagnen** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="87424-215">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="87424-216">Geben Sie einen Dateinamen für die .docx- oder .pdf-Anlage ein.</span><span class="sxs-lookup"><span data-stu-id="87424-216">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="87424-217">**Url der benutzerdefinierten** Zielseite: Geben Sie eine optionale Zielseite ein, auf der Benutzer aufgenommen werden, wenn sie auf den Phishinglink klicken und ihre Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="87424-217">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="87424-218">Dieser Link ersetzt die Standardlandeseite.</span><span class="sxs-lookup"><span data-stu-id="87424-218">This link replaces the default landing page.</span></span> <span data-ttu-id="87424-219">Wenn Sie beispielsweise über ein internes Sensibilisierungstraining verfügen, können Sie diese URL hier angeben.</span><span class="sxs-lookup"><span data-stu-id="87424-219">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="87424-220">**Betreff**: Das **Betrefffeld** der E-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="87424-220">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="87424-221">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87424-221">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="87424-222">Erstellen Sie **im Schritt** E-Mail verfassen den Nachrichtentext der E-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="87424-222">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="87424-223">Wenn Sie im Schritt **Start** eine Vorlage ausgewählt haben, ist der Nachrichtentext bereits konfiguriert, Sie können sie jedoch anpassen.</span><span class="sxs-lookup"><span data-stu-id="87424-223">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="87424-224">Sie können die Registerkarte **E-Mail** (ein Rich-HTML-Editor) oder die **Registerkarte Quelle** (html-Rohcode) verwenden.</span><span class="sxs-lookup"><span data-stu-id="87424-224">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="87424-225">Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="87424-225">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="87424-226">Sie können Bilder und Text einfügen, um die Glaubhaftigkeit der Nachricht im E-Mail-Client des Empfängers zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="87424-226">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="87424-227">`${username}` fügt den Namen des Empfängers ein.</span><span class="sxs-lookup"><span data-stu-id="87424-227">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="87424-228">`${loginserverurl}` fügt den **Wert der Phishing-Anmeldeserver-URL** ein.</span><span class="sxs-lookup"><span data-stu-id="87424-228">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="87424-229">Bei **Spear Phishing (Attachment)-Kampagnen** sollten Sie den Link aus dem Nachrichtentext entfernen (andernfalls enthält die Nachricht sowohl einen Link als auch eine Anlage, und Linkklicks werden in einer Anlagenkampagne nicht nachverfolgt). </span><span class="sxs-lookup"><span data-stu-id="87424-229">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="87424-230">![Verfassen des E-Mail-Textkörpers](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span><span class="sxs-lookup"><span data-stu-id="87424-230">![Compose Email Body](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)</span></span>

   <span data-ttu-id="87424-231">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87424-231">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="87424-232">Klicken Sie **im Schritt Bestätigen** auf Fertig **stellen,** um die Kampagne zu starten.</span><span class="sxs-lookup"><span data-stu-id="87424-232">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="87424-233">Die Phishingnachricht wird an die Zielempfänger übermittelt.</span><span class="sxs-lookup"><span data-stu-id="87424-233">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="87424-234">Kennwortangriffskampagnen</span><span class="sxs-lookup"><span data-stu-id="87424-234">Password attack campaigns</span></span>

<span data-ttu-id="87424-235">Ein *Kennwortangriff versucht,* Kennwörter für Benutzerkonten in einer Organisation zu erraten, in der Regel, nachdem der Angreifer ein oder mehrere gültige Benutzerkonten identifiziert hat.</span><span class="sxs-lookup"><span data-stu-id="87424-235">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="87424-236">Im Angriffssimulator stehen Ihnen zwei verschiedene Arten von Kennwortangriffskampagnen zur Verfügung, um die Komplexität der Kennwörter Ihrer Benutzer zu testen:</span><span class="sxs-lookup"><span data-stu-id="87424-236">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="87424-237">**Brute Force Password (Wörterbuchangriff):** Ein  *Brute* Force- oder Wörterbuchangriff verwendet eine große Wörterbuchdatei mit Kennwörtern für ein Benutzerkonto mit der Hoffnung, dass eines davon funktioniert (viele Kennwörter für ein Konto).</span><span class="sxs-lookup"><span data-stu-id="87424-237">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="87424-238">Falsche Kennwortsperrungen helfen, Brute Force-Kennwortangriffe zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="87424-238">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="87424-239">Für den Wörterbuchangriff können Sie ein oder mehrere Kennwörter angeben, die Sie ausprobieren möchten (manuell eingegeben oder in eine hochgeladene Datei), und Sie können einen oder mehrere Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="87424-239">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="87424-240">**Kennwort-Spray-Angriff:** Ein *Kennwort-Spray-Angriff* verwendet dasselbe sorgfältig überlegte Kennwort für eine Liste von Benutzerkonten (ein Kennwort für viele Konten).</span><span class="sxs-lookup"><span data-stu-id="87424-240">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="87424-241">Kennwortschutzangriffe sind schwieriger zu erkennen als Brute-Force-Kennwortangriffe (die Wahrscheinlichkeit eines Erfolgs steigt, wenn ein Angreifer ein Kennwort über Dutzende oder Hunderte von Konten versucht, ohne das Risiko zu riskieren, dass die falsche Kennwortsperre des Benutzers ausreist).</span><span class="sxs-lookup"><span data-stu-id="87424-241">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="87424-242">Für den Kennwort-Spray-Angriff können Sie nur ein Kennwort angeben, das Sie ausprobieren möchten, und Sie können einen oder mehrere Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="87424-242">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="87424-243">Die Kennwortangriffe im Angriffssimulator übergeben Benutzernamen und Kennwort Grundlegende Authentifizierungsanforderungen an einen Endpunkt, damit sie auch mit anderen Authentifizierungsmethoden (AD FS, Kennworthashsynchronisierung, Pass-Through, PingFederate usw.) funktionieren.</span><span class="sxs-lookup"><span data-stu-id="87424-243">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="87424-244">Für Benutzer, für die MFA aktiviert ist, wird der Versuch auch dann, wenn der Kennwortangriff sein **tatsächliches** Kennwort versucht, immer als Fehler registriert (D. h. MFA-Benutzer werden nie in der Anzahl der erfolgreichen Versuche der Kampagne angezeigt).</span><span class="sxs-lookup"><span data-stu-id="87424-244">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="87424-245">Dies ist das erwartete Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="87424-245">This is the expected result.</span></span> <span data-ttu-id="87424-246">MFA ist eine primäre Methode zum Schutz vor Kennwortangriffen.</span><span class="sxs-lookup"><span data-stu-id="87424-246">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="87424-247">Erstellen und Starten einer Kennwortangriffskampagne</span><span class="sxs-lookup"><span data-stu-id="87424-247">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="87424-248">Wechseln Sie im Security & Compliance Center zu **Angriffssimulator für die Bedrohungsverwaltung.** \> </span><span class="sxs-lookup"><span data-stu-id="87424-248">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="87424-249">Treffen Sie **auf** der Seite Angriffe simulieren eine der folgenden Auswahlen basierend auf dem Typ der Kampagne, die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="87424-249">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="87424-250">Klicken Sie **im Abschnitt Brute Force Password (Dictionary Attack)** auf **Angriff starten** oder **Angriffsdetails** \> **Starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="87424-250">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="87424-251">Klicken Sie **im Abschnitt Kennwort-Sprayangriff** auf **Angriff starten,** oder klicken Sie auf **Angriffsdetails** \> **Starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="87424-251">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="87424-252">Der **Assistent zum Konfigurieren von Kennwortangriffen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="87424-252">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="87424-253">Geben Sie **im Schritt Start** einen eindeutigen Anzeigenamen für die Kampagne ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87424-253">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="87424-254">Gehen Sie **im Schritt** Zielbenutzer wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="87424-254">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="87424-255">Klicken **Sie auf Adressbuch,** um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="87424-255">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="87424-256">Jeder Zielempfänger muss über ein Exchange Online-Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="87424-256">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="87424-257">Wenn Sie auf **Filtern** und **Anwenden** klicken, ohne ein Suchkriterium ein eingeben zu müssen, werden alle Empfänger zurückgegeben und der Kampagne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="87424-257">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="87424-258">Klicken **Sie auf Importieren** und anschließend auf **Dateiimport,** um einen durch Kommas getrennten Wert (CSV) oder eine zeilenge trennte Datei mit E-Mail-Adressen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="87424-258">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="87424-259">Jede Zeile muss die E-Mail-Adresse des Empfängers enthalten.</span><span class="sxs-lookup"><span data-stu-id="87424-259">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="87424-260">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87424-260">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="87424-261">Wählen Sie **im Schritt Angriffseinstellungen** auswählen basierend auf dem Kampagnentyp die schritte aus:</span><span class="sxs-lookup"><span data-stu-id="87424-261">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="87424-262">**Brute Force Password (Dictionary Attack)**: Gehen Sie wie folgt vor:</span><span class="sxs-lookup"><span data-stu-id="87424-262">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="87424-263">**Geben Sie Kennwörter manuell** ein: Geben Sie in das Feld **Drücken** Sie die Eingabetaste ein, um ein Kennwort hinzuzufügen, geben Sie ein Kennwort ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="87424-263">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="87424-264">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="87424-264">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="87424-265">**Hochladen von Kennwörtern** aus einer Wörterbuchdatei: Klicken Sie auf **Hochladen,** um eine vorhandene Textdatei zu importieren, die ein Kennwort in jeder Zeile und eine leere letzte Zeile enthält.</span><span class="sxs-lookup"><span data-stu-id="87424-265">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="87424-266">Die Textdatei muss mindestens 10 MB groß sein und darf nicht mehr als 30.000 Kennwörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="87424-266">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="87424-267">**Kennwort-Spray-Angriff:** Geben Sie im **Feld Kennwort(en)** ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="87424-267">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="87424-268">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="87424-268">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="87424-269">Klicken Sie **im Schritt Bestätigen** auf Fertig **stellen,** um die Kampagne zu starten.</span><span class="sxs-lookup"><span data-stu-id="87424-269">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="87424-270">Die von Ihnen angegebenen Kennwörter werden für Benutzer ausprobiert, die Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="87424-270">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="87424-271">Anzeigen von Kampagnenergebnissen</span><span class="sxs-lookup"><span data-stu-id="87424-271">View campaign results</span></span>

<span data-ttu-id="87424-272">Nachdem Sie eine Kampagne gestartet haben, können Sie den Fortschritt und die Ergebnisse auf der Hauptseite Simulierte **Angriffe** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="87424-272">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="87424-273">Aktive Kampagnen zeigen eine Statusleiste, einen abgeschlossenen Prozentwert und die Anzahl "(abgeschlossene Benutzer) (Gesamtbenutzer)" an.</span><span class="sxs-lookup"><span data-stu-id="87424-273">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="87424-274">Durch Klicken auf **die Schaltfläche Aktualisieren** wird der Fortschritt aller aktiven Kampagnen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="87424-274">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="87424-275">Sie können auch auf **Beenden klicken,** um eine aktive Kampagne zu beenden.</span><span class="sxs-lookup"><span data-stu-id="87424-275">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="87424-276">Nach Abschluss der Kampagne wird der Status in **Angriff abgeschlossen geändert.**</span><span class="sxs-lookup"><span data-stu-id="87424-276">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="87424-277">Sie können die Ergebnisse der Kampagne anzeigen, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="87424-277">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="87424-278">Klicken Sie auf der **Hauptseite** Angriffe simulieren **unter** dem Namen der Kampagne auf Bericht anzeigen.</span><span class="sxs-lookup"><span data-stu-id="87424-278">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="87424-279">Klicken Sie auf der **Hauptseite** Angriffe simulieren im Abschnitt für den Angriffstyp auf **Angriffsdetails.**</span><span class="sxs-lookup"><span data-stu-id="87424-279">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="87424-280">Wählen Sie **auf der Seite Angriffsdetails,** die geöffnet wird, die Kampagne im **Abschnitt Angriffsverlauf** aus.</span><span class="sxs-lookup"><span data-stu-id="87424-280">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="87424-281">Mit einer der vorherigen Aktionen gelangen Sie zu einer Seite mit dem Namen **Attack details**.</span><span class="sxs-lookup"><span data-stu-id="87424-281">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="87424-282">Die Informationen, die auf dieser Seite für jeden Kampagnentyp verfügbar sind, werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="87424-282">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="87424-283">Spear Phishing (Credentials Harvest)-Kampagnenergebnisse</span><span class="sxs-lookup"><span data-stu-id="87424-283">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="87424-284">Die folgenden Informationen sind auf der Seite **Angriffsdetails** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="87424-284">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="87424-285">Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="87424-285">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="87424-286">**Ziel aller Benutzer**</span><span class="sxs-lookup"><span data-stu-id="87424-286">**Total users targeted**</span></span>

- <span data-ttu-id="87424-287">**Erfolgreiche Versuche:** Die Anzahl der Benutzer,  die auf den Link geklickt und ihre Anmeldeinformationen eingegeben haben *(beliebiger* Benutzername und Kennwortwert).</span><span class="sxs-lookup"><span data-stu-id="87424-287">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="87424-288">**Gesamterfolgsrate:** Ein Prozentsatz, der durch erfolgreiche Versuche berechnet wird  /  **Gesamtbenutzer gezielt**.</span><span class="sxs-lookup"><span data-stu-id="87424-288">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="87424-289">**Schnellster Klick**: Wie lange es dauerte, bis der erste Benutzer auf den Link geklickt hat, nachdem Sie die Kampagne gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="87424-289">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="87424-290">**Durchschnittlicher Klick**: Die Summe der Dauer, die jeder benutzer brauchte, um auf den Link zu klicken, geteilt durch die Anzahl der Benutzer, die auf den Link geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="87424-290">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="87424-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span><span class="sxs-lookup"><span data-stu-id="87424-291">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="87424-292">**Schnellste Anmeldeinformationen:** Wie lange es dauerte, bis der erste Benutzer seine Anmeldeinformationen eingegeben hat, nachdem Sie die Kampagne gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="87424-292">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="87424-293">**Durchschnittliche** Anmeldeinformationen : Die Summe der Dauer, die jeder für die Eingabe seiner Anmeldeinformationen brauchte, geteilt durch die Anzahl der Benutzer, die seine Anmeldeinformationen eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="87424-293">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="87424-294">**Erfolgsrate der Anmeldeinformationen**: Ein Prozentsatz, der durch (Anzahl der Benutzer, die ihre Anmeldeinformationen eingegeben haben) / **Zielbenutzer insgesamt berechnet wird.**</span><span class="sxs-lookup"><span data-stu-id="87424-294">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="87424-295">Ein Balkendiagramm, das zeigt, **auf "Link geklickt"** und **"Anmeldeinformationen" zahlen** pro Tag angegeben sind.</span><span class="sxs-lookup"><span data-stu-id="87424-295">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="87424-296">Ein Kreisdiagramm, in dem die Prozentsätze **Link geklickt,** Angegebene Anmeldeinformationen **und** **Keine** für die Kampagne angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="87424-296">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="87424-297">Im **Abschnitt "Gefährdete Benutzer"** werden die Details der Benutzer aufgeführt, die auf den Link geklickt haben:</span><span class="sxs-lookup"><span data-stu-id="87424-297">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="87424-298">Die E-Mail-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="87424-298">The user's email address</span></span>

  - <span data-ttu-id="87424-299">Datum/Uhrzeit, zu dem sie auf den Link geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="87424-299">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="87424-300">Die Client-IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="87424-300">The client IP address.</span></span>

  - <span data-ttu-id="87424-301">Details zur Windows- und Webbrowserversion des Benutzers.</span><span class="sxs-lookup"><span data-stu-id="87424-301">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="87424-302">Sie können auf **Exportieren klicken,** um die Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="87424-302">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="87424-303">Spear Phishing (Attachment)-Kampagnenergebnisse</span><span class="sxs-lookup"><span data-stu-id="87424-303">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="87424-304">Die folgenden Informationen sind auf der Seite **Angriffsdetails** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="87424-304">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="87424-305">Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="87424-305">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="87424-306">**Ziel aller Benutzer**</span><span class="sxs-lookup"><span data-stu-id="87424-306">**Total users targeted**</span></span>

- <span data-ttu-id="87424-307">**Erfolgreiche Versuche:** Die Anzahl der Benutzer, die die Anlage geöffnet oder heruntergeladen und geöffnet haben (vorschau zählt nicht).</span><span class="sxs-lookup"><span data-stu-id="87424-307">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="87424-308">**Gesamterfolgsrate:** Ein Prozentsatz, der durch erfolgreiche Versuche berechnet wird  /  **Gesamtbenutzer gezielt**.</span><span class="sxs-lookup"><span data-stu-id="87424-308">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="87424-309">**Schnellstmögliche Anlagenöffnzeit:** Wie lange der erste Benutzer die Anlage geöffnet hat, nachdem Sie die Kampagne gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="87424-309">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="87424-310">**Durchschnittliche Anlagenöffnzeit:** Die Summe der Dauer, die jeder zum Öffnen der Anlage brauchte, geteilt durch die Anzahl der Benutzer, die die Anlage geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="87424-310">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="87424-311">**Erfolgsrate für offene Anlagen:** Ein Prozentsatz, der durch (Anzahl der Benutzer, die die Anlage geöffnet haben) / **Zielbenutzer insgesamt berechnet wird.**</span><span class="sxs-lookup"><span data-stu-id="87424-311">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="87424-312">Brute Force Password (Dictionary Attack)-Kampagnenergebnisse</span><span class="sxs-lookup"><span data-stu-id="87424-312">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="87424-313">Die folgenden Informationen sind auf der Seite **Angriffsdetails** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="87424-313">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="87424-314">Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="87424-314">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="87424-315">**Ziel aller Benutzer**</span><span class="sxs-lookup"><span data-stu-id="87424-315">**Total users targeted**</span></span>

- <span data-ttu-id="87424-316">**Erfolgreiche Versuche:** Die Anzahl der Benutzer, die eines der angegebenen Kennwörter verwendet haben.</span><span class="sxs-lookup"><span data-stu-id="87424-316">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="87424-317">**Gesamterfolgsrate:** Ein Prozentsatz, der durch erfolgreiche Versuche berechnet wird  /  **Gesamtbenutzer gezielt**.</span><span class="sxs-lookup"><span data-stu-id="87424-317">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="87424-318">Im **Abschnitt Gefährdete Benutzer** werden die E-Mail-Adressen der betroffenen Benutzer aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="87424-318">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="87424-319">Sie können auf **Exportieren klicken,** um die Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="87424-319">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="87424-320">Ergebnisse der Kennwort-Spray-Angriffskampagne</span><span class="sxs-lookup"><span data-stu-id="87424-320">Password spray attack campaign results</span></span>

<span data-ttu-id="87424-321">Die folgenden Informationen sind auf der Seite **Angriffsdetails** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="87424-321">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="87424-322">Die Dauer (Startdatum/-uhrzeit und Enddatum/-uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="87424-322">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="87424-323">**Ziel aller Benutzer**</span><span class="sxs-lookup"><span data-stu-id="87424-323">**Total users targeted**</span></span>

- <span data-ttu-id="87424-324">**Erfolgreiche Versuche:** Die Anzahl der Benutzer, die gefunden wurden, dass sie das angegebene Kennwort verwenden.</span><span class="sxs-lookup"><span data-stu-id="87424-324">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="87424-325">**Gesamterfolgsrate:** Ein Prozentsatz, der durch erfolgreiche Versuche berechnet wird  /  **Gesamtbenutzer gezielt**.</span><span class="sxs-lookup"><span data-stu-id="87424-325">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>