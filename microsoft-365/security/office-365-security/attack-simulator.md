---
title: Angriffs Simulator in Microsoft Defender für Office 365
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
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Administratoren können erfahren, wie Sie mithilfe von Attack Simulator simulierte Phishing-und Kennwortangriffe in Ihren Microsoft 365 E5 oder Microsoft Defender für Office 365 Plan 2-Organisationen ausführen.
ms.openlocfilehash: b1c2ad265c4812f67aee66f0f59664480b4db229
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49615204"
---
# <a name="attack-simulator-in-microsoft-defender-for-office-365"></a><span data-ttu-id="f82f2-103">Angriffs Simulator in Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="f82f2-103">Attack Simulator in Microsoft Defender for Office 365</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="f82f2-104">Wenn Ihre Organisation Microsoft Defender für Office 365 Plan 2, einschließlich [Bedrohungs Ermittlungs-und-Antwortfunktionen](office-365-ti.md), verwendet, können Sie den Angriffs Simulator im Security & Compliance Center verwenden, um realistische Angriffsszenarien in Ihrer Organisation auszuführen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-104">If your organization has Microsoft Defender for Office 365 Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="f82f2-105">Diese simulierten Angriffe können Sie bei der Identifizierung und Suche nach anfälligen Benutzern unterstützen, bevor ein echter Angriff Ihr Endergebnis beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="f82f2-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="f82f2-106">Lesen Sie diesen Artikel, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="f82f2-106">Read this article to learn more.</span></span>

> [!NOTE]
> <span data-ttu-id="f82f2-107">Angriffssimulation und schulungsbezogene Daten werden mit anderen Kundendaten für Microsoft 365-Dienste gespeichert.</span><span class="sxs-lookup"><span data-stu-id="f82f2-107">Attack simulation and training related data is stored with other customer data for Microsoft 365 services.</span></span> <span data-ttu-id="f82f2-108">Weitere Informationen finden Sie unter [Microsoft 365-Datenspeicherorte](/microsoft-365/enterprise/o365-data-locations).</span><span class="sxs-lookup"><span data-stu-id="f82f2-108">For more information see [Microsoft 365 data locations](/microsoft-365/enterprise/o365-data-locations).</span></span>

> [!TIP]
> <span data-ttu-id="f82f2-109">Das Training zur Angriffssimulation steht im Microsoft 365 Security Center für die öffentliche Vorschau zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f82f2-109">Attack simulation training is available for public preview in the Microsoft 365 security center.</span></span> <span data-ttu-id="f82f2-110">Weitere Informationen finden Sie unter [Simulieren eines Phishing-Angriffs mit Microsoft Defender für Office 365](attack-simulation-training.md) .</span><span class="sxs-lookup"><span data-stu-id="f82f2-110">Check out [Simulate a phishing attack with Microsoft Defender for Office 365](attack-simulation-training.md) to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="f82f2-111">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="f82f2-111">What do you need to know before you begin?</span></span>

- <span data-ttu-id="f82f2-112">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="f82f2-112">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="f82f2-113">Angriffs Simulator ist unter **Threat Management** \> **Attack Simulator** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f82f2-113">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="f82f2-114">Wechseln Sie direkt zum Angriffs Simulator, öffnen Sie <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="f82f2-114">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="f82f2-115">Weitere Informationen zur Verfügbarkeit des Angriffs Simulators in verschiedenen Microsoft 365-Abonnements finden Sie unter [Microsoft Defender for Office 365 Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="f82f2-115">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Microsoft Defender for Office 365 service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="f82f2-116">Sie müssen Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="f82f2-116">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="f82f2-117">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="f82f2-117">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="f82f2-118">Ihr Konto muss für die mehrstufige Authentifizierung (MFA) konfiguriert sein, um Kampagnen im Angriffs Simulator zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="f82f2-118">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="f82f2-119">Anweisungen finden Sie unter [Einrichten der mehr](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)stufigen Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="f82f2-119">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="f82f2-120">Bei Phishing-Kampagnen werden Ereignisse für 30 Tage gesammelt und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="f82f2-120">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="f82f2-121">Die Daten der Verlaufs Kampagne werden bis zu 90 Tage nach dem Start der Kampagne zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-121">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="f82f2-122">Es gibt keine entsprechenden PowerShell-Cmdlets für den Angriffs Simulator.</span><span class="sxs-lookup"><span data-stu-id="f82f2-122">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="f82f2-123">Speer-Phishing-Kampagnen</span><span class="sxs-lookup"><span data-stu-id="f82f2-123">Spear phishing campaigns</span></span>

<span data-ttu-id="f82f2-124">*Phishing* ist ein allgemeiner Begriff für e-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die anscheinend von legitimen oder vertrauenswürdigen Absendern sind.</span><span class="sxs-lookup"><span data-stu-id="f82f2-124">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="f82f2-125">*Spear-Phishing* ist ein gezielter Phishing-Angriff, der fokussierte und angepasste Inhalte verwendet, die speziell auf die Zielempfänger zugeschnitten sind (normalerweise nach Aufklärung der Empfänger durch den Angreifer).</span><span class="sxs-lookup"><span data-stu-id="f82f2-125">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="f82f2-126">In Attack Simulator stehen zwei verschiedene Arten von Speer-Phishing-Kampagnen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="f82f2-126">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="f82f2-127">**Spear Phishing (Credentials Harvest)**: der Angriff versucht, die Empfänger davon zu überzeugen, auf eine URL in der Nachricht zu klicken.</span><span class="sxs-lookup"><span data-stu-id="f82f2-127">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="f82f2-128">Wenn Sie auf den Link klicken, werden Sie aufgefordert, Ihre Anmeldeinformationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-128">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="f82f2-129">Wenn dies der Fall ist, werden Sie an einen der folgenden Speicherorte geleitet:</span><span class="sxs-lookup"><span data-stu-id="f82f2-129">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="f82f2-130">Eine Standardseite, die erklärt, dass dies ein nur ein Test war, und gibt Tipps zum Erkennen von Phishing-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="f82f2-130">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Was die Benutzer sehen, wenn Sie auf den Phishing-Link klicken und Ihre Anmeldeinformationen eingeben](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="f82f2-132">Eine benutzerdefinierte Seite (URL), die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-132">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="f82f2-133">**Spear-Phishing (Attachment)**: der Angriff versucht, die Empfänger davon zu überzeugen, eine DOCX-oder PDF-Anlage in der Nachricht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-133">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="f82f2-134">Die Anlage enthält denselben Inhalt aus dem standardmäßigen Phishing-Link, aber der erste Satz beginnt mit " \<Display Name\> , diese Nachricht wird als kürzlich geöffnete e-Mail-Nachricht angezeigt...".</span><span class="sxs-lookup"><span data-stu-id="f82f2-134">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="f82f2-135">Derzeit laufen Speer-Phishing-Kampagnen in Attack Simulator nicht ab.</span><span class="sxs-lookup"><span data-stu-id="f82f2-135">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="f82f2-136">Erstellen einer Speer-Phishing-Kampagne</span><span class="sxs-lookup"><span data-stu-id="f82f2-136">Create a spear phishing campaign</span></span>

<span data-ttu-id="f82f2-137">Ein wichtiger Bestandteil jeder Speer-Phishing-Kampagne ist das Aussehen und Verhalten der e-Mail-Nachricht, die an die Zielempfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="f82f2-137">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="f82f2-138">Sie haben folgende Möglichkeiten, um die e-Mail-Nachricht zu erstellen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="f82f2-138">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="f82f2-139">**Verwenden Sie eine integrierte e-Mail-Vorlage**: zwei integrierte Vorlagen stehen zur Verfügung: **Preis Giveaway** -und **Gehaltslisten Update**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-139">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="f82f2-140">Sie können einige, alle oder keine der e-Mail-Eigenschaften von der Vorlage anpassen, wenn Sie die Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="f82f2-140">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="f82f2-141">**Erstellen einer wiederverwendbaren e-Mail-Vorlage**: Nachdem Sie die e-Mail-Vorlage erstellt und gespeichert haben, können Sie Sie in künftigen Spear-Phishing-Kampagnen erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="f82f2-141">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="f82f2-142">Sie können einige, alle oder keine der e-Mail-Eigenschaften von der Vorlage anpassen, wenn Sie die Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="f82f2-142">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="f82f2-143">**Erstellen Sie die e-Mail-Nachricht im Assistenten**: Sie können die e-Mail-Nachricht direkt im Assistenten erstellen, während Sie die Spear-Phishing-Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="f82f2-143">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="f82f2-144">Schritt 1 (optional): Erstellen einer benutzerdefinierten e-Mail-Vorlage</span><span class="sxs-lookup"><span data-stu-id="f82f2-144">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="f82f2-145">Wenn Sie eine der integrierten Vorlagen verwenden oder die e-Mail-Nachricht direkt im Assistenten erstellen, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-145">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="f82f2-146">Wechseln Sie im Security & Compliance Center zum **Threat Management** - \> **Angriffs Simulator**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-146">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f82f2-147">Klicken Sie auf der Seite " **Angriffe simulieren** " entweder in den Abschnitten **Spear Phishing (Credentials Harvest)** oder **Spear Phishing (Attachment)** auf **Attack Details**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-147">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="f82f2-148">Es spielt keine Rolle, wo Sie die Vorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-148">It doesn't matter where you create the template.</span></span> <span data-ttu-id="f82f2-149">Die verfügbaren Optionen in der Vorlage sind für beide Arten von Phishing-Angriffen identisch.</span><span class="sxs-lookup"><span data-stu-id="f82f2-149">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="f82f2-150">Klicken Sie auf der daraufhin geöffneten Seite mit den **Angriffs Details** im Abschnitt **Phishing-Vorlagen** im Bereich **Vorlagen erstellen** auf **neue Vorlage**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-150">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="f82f2-151">Der Assistent zum **Konfigurieren von Phishing-Vorlagen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="f82f2-151">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="f82f2-152">Geben Sie im Schritt **Start** einen eindeutigen Anzeigenamen für die Vorlage ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-152">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="f82f2-153">Konfigurieren Sie im Schritt **e-Mail-Details konfigurieren** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f82f2-153">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="f82f2-154">**From (Name)**: der Anzeige Name, der für den Absender der Nachricht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f82f2-154">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="f82f2-155">**Von (e-Mail)**: die e-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="f82f2-155">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="f82f2-156">**URL des Phishing-Anmeldeservers**: Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="f82f2-156">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="f82f2-157">Dies ist die URL, auf die Benutzer klicken sollen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-157">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="f82f2-158">Sie können wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="f82f2-158">The choices are:</span></span>

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
     > - <span data-ttu-id="f82f2-159">Alle URLs sind absichtlich HTTP und nicht HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f82f2-159">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="f82f2-160">Ein URL-Reputations Dienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher.</span><span class="sxs-lookup"><span data-stu-id="f82f2-160">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="f82f2-161">Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishing-Kampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="f82f2-161">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="f82f2-162">**Benutzerdefinierte Startseiten-URL**: Geben Sie eine optionale Startseite ein, auf der Benutzer angezeigt werden, wenn Sie auf den Link Phishing klicken und die Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-162">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="f82f2-163">Dieser Link ersetzt die standardmäßige Ziel Seite.</span><span class="sxs-lookup"><span data-stu-id="f82f2-163">This link replaces the default landing page.</span></span> <span data-ttu-id="f82f2-164">Wenn Sie beispielsweise ein internes Bewusstseinstraining haben, können Sie diese URL hier angeben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-164">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="f82f2-165">**Kategorie**: Derzeit wird diese Einstellung nicht verwendet (alles, was Sie eingeben, wird ignoriert).</span><span class="sxs-lookup"><span data-stu-id="f82f2-165">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="f82f2-166">**Subject**: das **Subject** -Feld der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f82f2-166">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="f82f2-167">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-167">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f82f2-168">Erstellen Sie im Schritt **e-Mail verfassen** den Nachrichtentext der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f82f2-168">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="f82f2-169">Sie können die Registerkarte " **e-Mail** " (ein Rich-HTML-Editor) oder die Registerkarte " **Quelle** " (unformatierter HTML-Code) verwenden.</span><span class="sxs-lookup"><span data-stu-id="f82f2-169">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="f82f2-170">Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-170">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="f82f2-171">Sie können Bilder und Text einfügen, um die Glaubwürdigkeit erhöhen der Nachricht im e-Mail-Client des Empfängers zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="f82f2-171">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="f82f2-172">`${username}` Fügt den Namen des Empfängers ein.</span><span class="sxs-lookup"><span data-stu-id="f82f2-172">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="f82f2-173">`${loginserverurl}` Fügt den URL-Wert des **Phishing-Anmeldeservers** aus dem vorherigen Schritt ein.</span><span class="sxs-lookup"><span data-stu-id="f82f2-173">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="f82f2-174">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-174">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f82f2-175">Klicken Sie im Schritt **bestätigen** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-175">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="f82f2-176">Schritt 2: Erstellen und Starten der Spear-Phishing-Kampagne</span><span class="sxs-lookup"><span data-stu-id="f82f2-176">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="f82f2-177">Wechseln Sie im Security & Compliance Center zum **Threat Management** - \> **Angriffs Simulator**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-177">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f82f2-178">Wählen Sie auf der Seite **Angriffe simulieren** eine der folgenden Optionen basierend auf der Art der Kampagne aus, die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="f82f2-178">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="f82f2-179">Klicken Sie im Abschnitt **Spear Phishing (Credentials Harvest)** auf **Angriff starten** oder auf Angriff **Details** \> **starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-179">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="f82f2-180">Klicken Sie im Abschnitt **Spear Phishing (Attachment)** auf **Angriff starten** oder auf Angriff **Details** \> **starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-180">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="f82f2-181">Der Assistent zum **Konfigurieren von Phishing-Angriffen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="f82f2-181">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="f82f2-182">Führen Sie im **Start** Schritt einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f82f2-182">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f82f2-183">Geben Sie im Feld **Name** einen eindeutigen Anzeigenamen für die Kampagne ein.</span><span class="sxs-lookup"><span data-stu-id="f82f2-183">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="f82f2-184">Klicken Sie nicht auf **Vorlage verwenden**, da Sie die e-Mail-Nachricht später im Assistenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-184">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="f82f2-185">Klicken Sie auf **Vorlage verwenden** , und wählen Sie eine integrierte oder benutzerdefinierte e-Mail-Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="f82f2-185">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="f82f2-186">Nachdem Sie die Vorlage ausgewählt haben, wird das Feld **Name** automatisch basierend auf der Vorlage ausgefüllt, aber Sie können den Namen ändern.</span><span class="sxs-lookup"><span data-stu-id="f82f2-186">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Phishing-Start Seite](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="f82f2-188">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-188">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="f82f2-189">Führen Sie im Schritt **Zielempfänger** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f82f2-189">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f82f2-190">Klicken Sie auf **Adressbuch** , um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-190">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="f82f2-191">Jeder Zielempfänger muss über ein Exchange Online Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-191">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="f82f2-192">Wenn Sie auf **Filtern** und **anwenden** klicken, ohne Suchkriterien einzugeben, werden alle Empfänger zurückgegeben und zur Kampagne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f82f2-192">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="f82f2-193">Klicken Sie auf **Import** dann auf **Dateiimport** , um einen durch Kommas getrennten Wert (CSV) oder eine durch die Datei getrennte Datei mit e-Mail-Adressen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="f82f2-193">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="f82f2-194">Jede Reihe muss die e-Mail-Adresse des Empfängers enthalten.</span><span class="sxs-lookup"><span data-stu-id="f82f2-194">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="f82f2-195">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-195">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f82f2-196">Konfigurieren Sie im Schritt **e-Mail-Details konfigurieren** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="f82f2-196">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="f82f2-197">Wenn Sie im **Start** Schritt eine Vorlage ausgewählt haben, sind die meisten dieser Werte bereits konfiguriert, aber Sie können Sie ändern.</span><span class="sxs-lookup"><span data-stu-id="f82f2-197">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="f82f2-198">**From (Name)**: der Anzeige Name, der für den Absender der Nachricht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="f82f2-198">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="f82f2-199">**Von (e-Mail)**: die e-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="f82f2-199">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="f82f2-200">Sie können eine reale oder gefälschte e-Mail-Adresse aus der e-Mail-Domäne Ihrer Organisation eingeben, oder Sie können eine reale oder gefälschte externe e-Mail-Adresse eingeben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-200">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="f82f2-201">Eine gültige Absender-e-Mail-Adresse aus Ihrer Organisation wird tatsächlich im e-Mail-Client des Empfängers aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="f82f2-201">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="f82f2-202">**URL des Phishing-Anmeldeservers**: Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="f82f2-202">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="f82f2-203">Dies ist die URL, auf die Benutzer klicken sollen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-203">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="f82f2-204">Sie können wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="f82f2-204">The choices are:</span></span>

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
     > - <span data-ttu-id="f82f2-205">Alle URLs sind absichtlich HTTP und nicht HTTPS.</span><span class="sxs-lookup"><span data-stu-id="f82f2-205">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="f82f2-206">Ein URL-Reputations Dienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher.</span><span class="sxs-lookup"><span data-stu-id="f82f2-206">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="f82f2-207">Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishing-Kampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="f82f2-207">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="f82f2-208">Sie müssen eine URL auswählen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-208">You are required to select a URL.</span></span> <span data-ttu-id="f82f2-209">Bei Kampagnen mit **Spear-Phishing (Attachment)** können Sie den Link aus dem Textkörper der Nachricht im nächsten Schritt entfernen (andernfalls enthält die Nachricht sowohl einen Link als **auch** eine Anlage).</span><span class="sxs-lookup"><span data-stu-id="f82f2-209">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="f82f2-210">**Anlagentyp**: Diese Einstellung ist nur in Kampagnen für **Spear-Phishing (Attachment)** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f82f2-210">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="f82f2-211">Klicken Sie auf die Dropdownliste, und wählen Sie aus **. DOCX** oder **. PDF** aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="f82f2-211">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="f82f2-212">**Name der Anlage**: Diese Einstellung ist nur in Kampagnen für **Spear-Phishing (Attachment)** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f82f2-212">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="f82f2-213">Geben Sie einen Dateinamen für die Datei. docx oder. PDF ein.</span><span class="sxs-lookup"><span data-stu-id="f82f2-213">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="f82f2-214">**Benutzerdefinierte Startseiten-URL**: Geben Sie eine optionale Startseite ein, auf der Benutzer angezeigt werden, wenn Sie auf den Link Phishing klicken und die Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-214">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="f82f2-215">Dieser Link ersetzt die standardmäßige Ziel Seite.</span><span class="sxs-lookup"><span data-stu-id="f82f2-215">This link replaces the default landing page.</span></span> <span data-ttu-id="f82f2-216">Wenn Sie beispielsweise ein internes Bewusstseinstraining haben, können Sie diese URL hier angeben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-216">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="f82f2-217">**Subject**: das **Subject** -Feld der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f82f2-217">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="f82f2-218">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-218">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f82f2-219">Erstellen Sie im Schritt **e-Mail verfassen** den Nachrichtentext der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="f82f2-219">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="f82f2-220">Wenn Sie im **Start** Schritt eine Vorlage ausgewählt haben, ist der Nachrichtentext bereits konfiguriert, Sie können ihn jedoch anpassen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-220">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="f82f2-221">Sie können die Registerkarte " **e-Mail** " (ein Rich-HTML-Editor) oder die Registerkarte " **Quelle** " (unformatierter HTML-Code) verwenden.</span><span class="sxs-lookup"><span data-stu-id="f82f2-221">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="f82f2-222">Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-222">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="f82f2-223">Sie können Bilder und Text einfügen, um die Glaubwürdigkeit erhöhen der Nachricht im e-Mail-Client des Empfängers zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="f82f2-223">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="f82f2-224">`${username}` Fügt den Namen des Empfängers ein.</span><span class="sxs-lookup"><span data-stu-id="f82f2-224">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="f82f2-225">`${loginserverurl}` Fügt den URL-Wert für den **Phishing-Anmelde Server** ein.</span><span class="sxs-lookup"><span data-stu-id="f82f2-225">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="f82f2-226">Bei Kampagnen mit **Spear-Phishing (Attachment)** sollten Sie den Link aus dem Nachrichtentext entfernen (andernfalls enthält die Nachricht sowohl einen Link als **auch** eine Anlage, und Link Klicks werden nicht in einer Anlagen Kampagne nachverfolgt).</span><span class="sxs-lookup"><span data-stu-id="f82f2-226">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![E-Mail-Textkörper erstellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="f82f2-228">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-228">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="f82f2-229">Klicken Sie im Schritt **bestätigen** auf **Fertig stellen** , um die Kampagne zu starten.</span><span class="sxs-lookup"><span data-stu-id="f82f2-229">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="f82f2-230">Die Phishing-Nachricht wird an die Zielempfänger übermittelt.</span><span class="sxs-lookup"><span data-stu-id="f82f2-230">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="f82f2-231">Kenn Wort Angriffs Kampagnen</span><span class="sxs-lookup"><span data-stu-id="f82f2-231">Password attack campaigns</span></span>

<span data-ttu-id="f82f2-232">Ein *Kennwortangriff* versucht, Kennwörter für Benutzerkonten in einer Organisation zu erraten, in der Regel, nachdem der Angreifer mindestens ein gültiges Benutzerkonto erkannt hat.</span><span class="sxs-lookup"><span data-stu-id="f82f2-232">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="f82f2-233">In Attack Simulator stehen zwei verschiedene Arten von Kenn Wort Angriffs Kampagnen zur Verfügung, um die Komplexität der Kennwörter Ihrer Benutzer zu testen:</span><span class="sxs-lookup"><span data-stu-id="f82f2-233">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="f82f2-234">**Brute-Force-Kennwort (Wörterbuchangriff)**: bei einem *Brute-Force* -oder *Wörterbuch* Angriff wird eine große Wörterbuchdatei mit Kennwörtern für ein Benutzerkonto verwendet, wobei die Hoffnung besteht, dass einer von Ihnen funktioniert (viele Kennwörter für ein Konto).</span><span class="sxs-lookup"><span data-stu-id="f82f2-234">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="f82f2-235">Falsche Kenn Wort Sperren helfen, Brute-Force-Kennwortangriffe zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="f82f2-235">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="f82f2-236">Für den Wörterbuchangriff können Sie ein oder mehrere Kennwörter angeben, die Sie ausprobieren möchten (manuell eingegeben oder in eine hochgeladene Datei), und Sie können einen oder mehrere Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-236">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="f82f2-237">**Kenn Wort Sprüh Angriff**: bei einem *Kenn Wort Sprüh* Angriff wird dasselbe sorgfältig überprüfte Kennwort für eine Liste von Benutzerkonten verwendet (ein Kennwort für viele Konten).</span><span class="sxs-lookup"><span data-stu-id="f82f2-237">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="f82f2-238">Kenn Wort Sprüh Angriffe sind schwerer zu erkennen als Brute-Force-Kennwortangriffe (die Erfolgswahrscheinlichkeit steigt, wenn ein Angreifer ein Kennwort in Dutzenden oder Hunderten von Konten versucht, ohne dass die falsche Kenn Wort Sperrung des Benutzers ausgelöst wird).</span><span class="sxs-lookup"><span data-stu-id="f82f2-238">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="f82f2-239">Für den Kenn Wort Sprüh Angriff können Sie nur ein Kennwort angeben, das Sie ausprobieren möchten, und Sie können einen oder mehrere Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-239">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="f82f2-240">Die Kennwortangriffe im Angriffs Simulator übergeben Benutzernamen-und Kenn Wort grundlegende Authentifizierungsanforderungen an einen Endpunkt, sodass Sie auch mit anderen Authentifizierungsmethoden (AD FS, Kennworthash Synchronisierung, Pass-Through, PingFederate usw.) funktionieren.</span><span class="sxs-lookup"><span data-stu-id="f82f2-240">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="f82f2-241">Für Benutzer, die MFA aktiviert haben, wird der Versuch, selbst wenn der Kennwortangriff sein tatsächliches Kennwort versucht, immer als Fehler registriert (in anderen Worten: MFA-Benutzer werden nie in der Anzahl der **erfolgreichen Versuche** der Kampagne angezeigt).</span><span class="sxs-lookup"><span data-stu-id="f82f2-241">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="f82f2-242">Dies ist das erwartete Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="f82f2-242">This is the expected result.</span></span> <span data-ttu-id="f82f2-243">MFA ist eine primäre Methode zum Schutz vor Kennwortangriffen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-243">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="f82f2-244">Erstellen und Starten einer Kenn Wort Angriffs Kampagne</span><span class="sxs-lookup"><span data-stu-id="f82f2-244">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="f82f2-245">Wechseln Sie im Security & Compliance Center zum **Threat Management** - \> **Angriffs Simulator**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-245">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="f82f2-246">Wählen Sie auf der Seite **Angriffe simulieren** eine der folgenden Optionen basierend auf der Art der Kampagne aus, die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="f82f2-246">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="f82f2-247">Klicken Sie im Abschnitt **Brute-Force-Kennwort (Wörterbuchangriff)** auf **Angriff starten** , oder klicken Sie auf Angriff **Details** \> **starten**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-247">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="f82f2-248">Klicken Sie im Abschnitt **Kenn Wort Sprüh Angriff** auf **Angriff starten** oder auf Angriff **Details** \> **starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-248">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="f82f2-249">Der Assistent zum **Konfigurieren von Kennwortangriffen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="f82f2-249">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="f82f2-250">Geben Sie im Schritt **Start** einen eindeutigen Anzeigenamen für die Kampagne ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-250">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="f82f2-251">Führen Sie im Schritt **Zielbenutzer** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f82f2-251">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="f82f2-252">Klicken Sie auf **Adressbuch** , um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-252">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="f82f2-253">Jeder Zielempfänger muss über ein Exchange Online Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-253">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="f82f2-254">Wenn Sie auf **Filtern** und **anwenden** klicken, ohne Suchkriterien einzugeben, werden alle Empfänger zurückgegeben und zur Kampagne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="f82f2-254">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="f82f2-255">Klicken Sie auf **Import** dann auf **Dateiimport** , um einen durch Kommas getrennten Wert (CSV) oder eine durch die Datei getrennte Datei mit e-Mail-Adressen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="f82f2-255">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="f82f2-256">Jede Reihe muss die e-Mail-Adresse des Empfängers enthalten.</span><span class="sxs-lookup"><span data-stu-id="f82f2-256">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="f82f2-257">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-257">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="f82f2-258">Wählen Sie im Schritt **Angriffs Einstellungen auswählen** aus, welche Aktionen basierend auf dem Kampagnentyp vorgenommen werden sollen:</span><span class="sxs-lookup"><span data-stu-id="f82f2-258">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="f82f2-259">**Brute-Force-Kennwort (Wörterbuchangriff)**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="f82f2-259">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="f82f2-260">**Manuelles Eingeben von Kennwörtern**: Geben Sie in das Feld **EINGABETASTE drücken, um ein Kennwort hinzuzufügen** ein Kennwort ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="f82f2-260">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="f82f2-261">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="f82f2-261">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="f82f2-262">**Hochladen von Kennwörtern aus einer Wörterbuchdatei**: Klicken Sie auf **hochladen** , um eine vorhandene Textdatei zu importieren, die in jeder Zeile ein Kennwort enthält, und eine leere letzte Zeile.</span><span class="sxs-lookup"><span data-stu-id="f82f2-262">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="f82f2-263">Die Textdatei muss mindestens 10 MB groß sein und darf nicht mehr als 30000 Kennwörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="f82f2-263">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="f82f2-264">**Kenn Wort Sprüh Angriff**: Geben Sie in **den zu verwendenden Kennwörtern im Feld Angriff** ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="f82f2-264">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="f82f2-265">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-265">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="f82f2-266">Klicken Sie im Schritt **bestätigen** auf **Fertig stellen** , um die Kampagne zu starten.</span><span class="sxs-lookup"><span data-stu-id="f82f2-266">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="f82f2-267">Die von Ihnen angegebenen Kennwörter werden für Benutzer ausprobiert, die Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-267">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="f82f2-268">Anzeigen von kampagnenergebnissen</span><span class="sxs-lookup"><span data-stu-id="f82f2-268">View campaign results</span></span>

<span data-ttu-id="f82f2-269">Nachdem Sie eine Kampagne gestartet haben, können Sie den Fortschritt und die Ergebnisse auf der Seite Haupt **Angriffe simulieren** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="f82f2-269">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="f82f2-270">In aktiven Kampagnen wird eine Statusleiste, ein abgeschlossener Prozentwert und "(abgeschlossene Benutzer) von (Gesamtanzahl der Benutzer)" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f82f2-270">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="f82f2-271">Durch Klicken auf die Schaltfläche **Aktualisieren** wird der Status aller aktiven Kampagnen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="f82f2-271">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="f82f2-272">Sie können auch auf **Beenden** klicken, um eine aktive Kampagne zu beenden.</span><span class="sxs-lookup"><span data-stu-id="f82f2-272">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="f82f2-273">Wenn die Kampagne abgeschlossen ist, wird der Status in **Angriff abgeschlossen** geändert.</span><span class="sxs-lookup"><span data-stu-id="f82f2-273">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="f82f2-274">Sie können die Ergebnisse der Kampagne anzeigen, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="f82f2-274">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="f82f2-275">Klicken Sie auf der Seite Haupt **Angriffe simulieren** auf **Bericht anzeigen** unter dem Namen der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="f82f2-275">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="f82f2-276">Klicken Sie auf der Seite Haupt **Angriffe simulieren** auf **Angriffs Details** im Abschnitt für den Typ des Angriffs.</span><span class="sxs-lookup"><span data-stu-id="f82f2-276">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="f82f2-277">Wählen Sie auf der Seite **Angriffs Details** , die geöffnet wird, die Kampagne im Abschnitt **Angriffs Verlauf** aus.</span><span class="sxs-lookup"><span data-stu-id="f82f2-277">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="f82f2-278">Mit einer der vorherigen Aktionen gelangen Sie zu einer Seite mit dem Namen " **Angriffs Details**".</span><span class="sxs-lookup"><span data-stu-id="f82f2-278">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="f82f2-279">Die Informationen, die auf dieser Seite für jede Art von Kampagne zur Verfügung stehen, werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-279">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="f82f2-280">Kampagnenergebnisse für Spear-Phishing (Sammeln von Anmeldeinformationen)</span><span class="sxs-lookup"><span data-stu-id="f82f2-280">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="f82f2-281">Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f82f2-281">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f82f2-282">Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="f82f2-282">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f82f2-283">**Zielgruppe der Gesamtbenutzer**</span><span class="sxs-lookup"><span data-stu-id="f82f2-283">**Total users targeted**</span></span>

- <span data-ttu-id="f82f2-284">**Erfolgreiche Versuche**: die Anzahl der Benutzer, die auf den Link geklickt **und** Ihre Anmeldeinformationen eingegeben haben (*beliebiger* Benutzername und Kennwortwert).</span><span class="sxs-lookup"><span data-stu-id="f82f2-284">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="f82f2-285">**Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen** berechnet wird  /  .**Gesamtzahl der Benutzer**, die gezielt sind.</span><span class="sxs-lookup"><span data-stu-id="f82f2-285">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f82f2-286">**Schnellster Mausklick**: wie lange es dauerte, bis der erste Benutzer auf den Link klickt, nachdem Sie die Kampagne gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-286">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="f82f2-287">**Durchschnittlicher Mausklick**: die Summe, wie lange es dauerte, bis jeder auf den Link geklickt hat, dividiert durch die Anzahl der Benutzer, die auf den Link geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-287">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="f82f2-288">**Klicken Sie auf Erfolgs Rate**: einen Prozentsatz, der von berechnet wird (Anzahl der Benutzer, die auf den Link geklickt haben)/Gesamtanzahl der Benutzer, die als **Ziel** ausgewählt wurden</span><span class="sxs-lookup"><span data-stu-id="f82f2-288">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="f82f2-289">**Schnellste Anmeldeinformationen**: wie lange dauerte es, bis der erste Benutzer seine Anmeldeinformationen eingegeben hat, nachdem die Kampagne gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="f82f2-289">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="f82f2-290">**Durchschnittliche Anmeldeinformationen**: die Summe der Dauer, die jeder zum Eingeben der Anmeldeinformationen benötigte, dividiert durch die Anzahl der Benutzer, die Ihre Anmeldeinformationen eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-290">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="f82f2-291">**Erfolgs Rate der Anmeldeinformationen**: ein Prozentsatz, der von berechnet wird (Anzahl der Benutzer, die Ihre Anmeldeinformationen eingegeben haben)/Gesamtanzahl der Benutzer, die **zielgerichtet** sind.</span><span class="sxs-lookup"><span data-stu-id="f82f2-291">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="f82f2-292">Ein Balkendiagramm, in dem der **Link geklickt** wird und die Anzahl der **Anmeldeinformationen** pro Tag angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="f82f2-292">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="f82f2-293">Ein Kreisdiagramm, in dem der **angeklickte Link**, die **angegebenen Anmeldeinformationen** und **keine** Prozentsätze für die Kampagne angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="f82f2-293">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="f82f2-294">Im Abschnitt **kompromittierte Benutzer** werden die Details der Benutzer aufgelistet, die auf den Link geklickt haben:</span><span class="sxs-lookup"><span data-stu-id="f82f2-294">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="f82f2-295">Die E-Mail-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="f82f2-295">The user's email address</span></span>

  - <span data-ttu-id="f82f2-296">Das Datum/die Uhrzeit, zu dem der Link geklickt hat.</span><span class="sxs-lookup"><span data-stu-id="f82f2-296">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="f82f2-297">Die Client-IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="f82f2-297">The client IP address.</span></span>

  - <span data-ttu-id="f82f2-298">Details zur Benutzerversion von Windows und Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="f82f2-298">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="f82f2-299">Sie können auf **exportieren** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="f82f2-299">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="f82f2-300">Kampagnenergebnisse für Spear-Phishing (Attachment)</span><span class="sxs-lookup"><span data-stu-id="f82f2-300">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="f82f2-301">Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f82f2-301">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f82f2-302">Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="f82f2-302">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f82f2-303">**Zielgruppe der Gesamtbenutzer**</span><span class="sxs-lookup"><span data-stu-id="f82f2-303">**Total users targeted**</span></span>

- <span data-ttu-id="f82f2-304">**Erfolgreiche Versuche**: die Anzahl der Benutzer, die die Anlage geöffnet oder heruntergeladen und geöffnet haben (Vorschau wird nicht gezählt).</span><span class="sxs-lookup"><span data-stu-id="f82f2-304">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="f82f2-305">**Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen** berechnet wird  /  .**Gesamtzahl der Benutzer**, die gezielt sind.</span><span class="sxs-lookup"><span data-stu-id="f82f2-305">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f82f2-306">**Schnellste Anlage Open Time**: wie lange dauerte es, bis der erste Benutzer die Anlage geöffnet hat, nachdem Sie die Kampagne gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-306">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="f82f2-307">**Open Time (durchschnittliche Anlage**): die Summe der Dauer, die jeder zum Öffnen der Anlage benötigte, dividiert durch die Anzahl der Benutzer, die die Anlage geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="f82f2-307">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="f82f2-308">**Anlage offene Erfolgsrate**: ein Prozentsatz, der von berechnet wird (Anzahl der Benutzer, die die Anlage geöffnet haben)/Gesamtanzahl der **Zielbenutzer**.</span><span class="sxs-lookup"><span data-stu-id="f82f2-308">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="f82f2-309">Kampagnenergebnisse für Brute-Force-Kennwort (Wörterbuchangriffe)</span><span class="sxs-lookup"><span data-stu-id="f82f2-309">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="f82f2-310">Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f82f2-310">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f82f2-311">Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="f82f2-311">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f82f2-312">**Zielgruppe der Gesamtbenutzer**</span><span class="sxs-lookup"><span data-stu-id="f82f2-312">**Total users targeted**</span></span>

- <span data-ttu-id="f82f2-313">**Erfolgreiche Versuche**: die Anzahl der Benutzer, bei denen festgestellt wurde, dass Sie eines der angegebenen Kennwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="f82f2-313">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="f82f2-314">**Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen** berechnet wird  /  .**Gesamtzahl der Benutzer**, die gezielt sind.</span><span class="sxs-lookup"><span data-stu-id="f82f2-314">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="f82f2-315">Im Abschnitt **kompromittierte Benutzer** werden die e-Mail-Adressen der betroffenen Benutzer aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="f82f2-315">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="f82f2-316">Sie können auf **exportieren** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="f82f2-316">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="f82f2-317">Kenn Wort Sprüh Angriff-Kampagnenergebnisse</span><span class="sxs-lookup"><span data-stu-id="f82f2-317">Password spray attack campaign results</span></span>

<span data-ttu-id="f82f2-318">Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="f82f2-318">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="f82f2-319">Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="f82f2-319">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="f82f2-320">**Zielgruppe der Gesamtbenutzer**</span><span class="sxs-lookup"><span data-stu-id="f82f2-320">**Total users targeted**</span></span>

- <span data-ttu-id="f82f2-321">**Erfolgreiche Versuche**: die Anzahl der Benutzer, für die das angegebene Kennwort verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="f82f2-321">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="f82f2-322">**Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen** berechnet wird  /  .**Gesamtzahl der Benutzer**, die gezielt sind.</span><span class="sxs-lookup"><span data-stu-id="f82f2-322">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
