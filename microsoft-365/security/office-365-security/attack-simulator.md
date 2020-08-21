---
title: Angriffs Simulator in ATP
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
ms.custom:
- seo-marvel-apr2020
description: Administratoren erfahren, wie Sie mithilfe des Angriffs Simulators simulierte Phishing-und Kennwortangriffe in Ihren Microsoft 365 E5-oder ATP-Plan-2-Organisationen ausführen können.
ms.openlocfilehash: 017376d8002811398fe3ce2d94f7c207cd718a78
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825833"
---
# <a name="attack-simulator-in-atp"></a><span data-ttu-id="2ef85-103">Angriffs Simulator in ATP</span><span class="sxs-lookup"><span data-stu-id="2ef85-103">Attack Simulator in ATP</span></span>

<span data-ttu-id="2ef85-104">Wenn Ihre Organisation Office 365 Advanced Threat Protection (ATP) Plan 2, einschließlich der [Funktionen zur Ermittlung und Reaktion von Bedrohungen](office-365-ti.md), verfügt, können Sie den Angriffs Simulator im Security & Compliance Center verwenden, um realistische Angriffsszenarien in Ihrer Organisation auszuführen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-104">If your organization has Office 365 Advanced Threat Protection (ATP) Plan 2, which includes [Threat Investigation and Response capabilities](office-365-ti.md), you can use Attack Simulator in the Security & Compliance Center to run realistic attack scenarios in your organization.</span></span> <span data-ttu-id="2ef85-105">Diese simulierten Angriffe können Sie bei der Identifizierung und Suche nach anfälligen Benutzern unterstützen, bevor ein echter Angriff Ihr Endergebnis beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="2ef85-105">These simulated attacks can help you identify and find vulnerable users before a real attack impacts your bottom line.</span></span> <span data-ttu-id="2ef85-106">Lesen Sie diesen Artikel, um mehr zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="2ef85-106">Read this article to learn more.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="2ef85-107">Was sollten Sie wissen, bevor Sie beginnen?</span><span class="sxs-lookup"><span data-stu-id="2ef85-107">What do you need to know before you begin?</span></span>

- <span data-ttu-id="2ef85-108">Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com/>.</span><span class="sxs-lookup"><span data-stu-id="2ef85-108">To open the Security & Compliance Center, go to <https://protection.office.com/>.</span></span> <span data-ttu-id="2ef85-109">Angriffs Simulator ist unter **Threat Management** \> **Attack Simulator**verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2ef85-109">Attack simulator is available at **Threat management** \> **Attack simulator**.</span></span> <span data-ttu-id="2ef85-110">Wechseln Sie direkt zum Angriffs Simulator, öffnen Sie <https://protection.office.com/attacksimulator> .</span><span class="sxs-lookup"><span data-stu-id="2ef85-110">Go go directly to attack simulator, open <https://protection.office.com/attacksimulator>.</span></span>

- <span data-ttu-id="2ef85-111">Weitere Informationen zur Verfügbarkeit des Angriffs Simulators in verschiedenen Microsoft 365-Abonnements finden Sie unter [Office 365 Advanced Threat Protection-Dienstbeschreibung](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span><span class="sxs-lookup"><span data-stu-id="2ef85-111">For more information about the availability of Attack Simulator across different Microsoft 365 subscriptions, see [Office 365 Advanced Threat Protection service description](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description).</span></span>

- <span data-ttu-id="2ef85-112">Sie müssen Mitglied der Rollengruppen " **Organisationsverwaltung** " oder " **Sicherheits Administrator** " sein.</span><span class="sxs-lookup"><span data-stu-id="2ef85-112">You need to be a member of the **Organization Management** or **Security Administrator** role groups.</span></span> <span data-ttu-id="2ef85-113">Weitere Informationen zu Rollengruppen im Security & Compliance Center finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span><span class="sxs-lookup"><span data-stu-id="2ef85-113">For more information about role groups in the Security & Compliance Center, see [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).</span></span>

- <span data-ttu-id="2ef85-114">Ihr Konto muss für die mehrstufige Authentifizierung (MFA) konfiguriert sein, um Kampagnen im Angriffs Simulator zu erstellen und zu verwalten.</span><span class="sxs-lookup"><span data-stu-id="2ef85-114">Your account needs to be configured for multi-factor authentication (MFA) to create and manage campaigns in Attack Simulator.</span></span> <span data-ttu-id="2ef85-115">Anweisungen finden Sie unter [Einrichten der mehr](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication)stufigen Authentifizierung.</span><span class="sxs-lookup"><span data-stu-id="2ef85-115">For instructions, see [Set up multi-factor authentication](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/set-up-multi-factor-authentication).</span></span>

- <span data-ttu-id="2ef85-116">Bei Phishing-Kampagnen werden Ereignisse für 30 Tage gesammelt und verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="2ef85-116">Phishing campaigns will collect and process events for 30 days.</span></span> <span data-ttu-id="2ef85-117">Die Daten der Verlaufs Kampagne werden bis zu 90 Tage nach dem Start der Kampagne zur Verfügung stehen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-117">Historical campaign data will be available for up to 90 days after you launch the campaign.</span></span>

- <span data-ttu-id="2ef85-118">Es gibt keine entsprechenden PowerShell-Cmdlets für den Angriffs Simulator.</span><span class="sxs-lookup"><span data-stu-id="2ef85-118">There are no corresponding PowerShell cmdlets for Attack Simulator.</span></span>

## <a name="spear-phishing-campaigns"></a><span data-ttu-id="2ef85-119">Speer-Phishing-Kampagnen</span><span class="sxs-lookup"><span data-stu-id="2ef85-119">Spear phishing campaigns</span></span>

<span data-ttu-id="2ef85-120">*Phishing* ist ein allgemeiner Begriff für e-Mail-Angriffe, die versuchen, vertrauliche Informationen in Nachrichten zu stehlen, die anscheinend von legitimen oder vertrauenswürdigen Absendern sind.</span><span class="sxs-lookup"><span data-stu-id="2ef85-120">*Phishing* is a generic term for email attacks that try to steal sensitive information in messages that appear to be from legitimate or trusted senders.</span></span> <span data-ttu-id="2ef85-121">*Spear-Phishing* ist ein gezielter Phishing-Angriff, der fokussierte und angepasste Inhalte verwendet, die speziell auf die Zielempfänger zugeschnitten sind (normalerweise nach Aufklärung der Empfänger durch den Angreifer).</span><span class="sxs-lookup"><span data-stu-id="2ef85-121">*Spear phishing* is a targeted phishing attack that uses focused and customized content that's specifically tailored to the targeted recipients (typically, after reconnaissance on the recipients by the attacker).</span></span>

<span data-ttu-id="2ef85-122">In Attack Simulator stehen zwei verschiedene Arten von Speer-Phishing-Kampagnen zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="2ef85-122">In Attack Simulator, two different types of spear phishing campaigns are available:</span></span>

- <span data-ttu-id="2ef85-123">**Spear Phishing (Credentials Harvest)**: der Angriff versucht, die Empfänger davon zu überzeugen, auf eine URL in der Nachricht zu klicken.</span><span class="sxs-lookup"><span data-stu-id="2ef85-123">**Spear phishing (credentials harvest)**: The attack tries to convince the recipients to click a URL in the message.</span></span> <span data-ttu-id="2ef85-124">Wenn Sie auf den Link klicken, werden Sie aufgefordert, Ihre Anmeldeinformationen einzugeben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-124">If they click the link, they're asked to enter their credentials.</span></span> <span data-ttu-id="2ef85-125">Wenn dies der Fall ist, werden Sie an einen der folgenden Speicherorte geleitet:</span><span class="sxs-lookup"><span data-stu-id="2ef85-125">If they do, they're taken to one of the following locations:</span></span>

  - <span data-ttu-id="2ef85-126">Eine Standardseite, die erklärt, dass dies ein nur ein Test war, und gibt Tipps zum Erkennen von Phishing-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="2ef85-126">A default page that explains that this was a just a test, and gives tips for recognizing phishing messages.</span></span>

    ![Was die Benutzer sehen, wenn Sie auf den Phishing-Link klicken und Ihre Anmeldeinformationen eingeben](../../media/attack-simulator-phishing-result.png)

  - <span data-ttu-id="2ef85-128">Eine benutzerdefinierte Seite (URL), die Sie angeben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-128">A custom page (URL) that you specify.</span></span>

- <span data-ttu-id="2ef85-129">**Spear-Phishing (Attachment)**: der Angriff versucht, die Empfänger davon zu überzeugen, eine DOCX-oder PDF-Anlage in der Nachricht zu öffnen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-129">**Spear phishing (attachment)**: The attack tries to convince the recipients to open a .docx or .pdf attachment in the message.</span></span> <span data-ttu-id="2ef85-130">Die Anlage enthält denselben Inhalt aus dem standardmäßigen Phishing-Link, aber der erste Satz beginnt mit " \<Display Name\> , diese Nachricht wird als kürzlich geöffnete e-Mail-Nachricht angezeigt...".</span><span class="sxs-lookup"><span data-stu-id="2ef85-130">The attachment contains the same content from the default phishing link, but the first sentence starts with "\<Display Name\>, you are seeing this message as a recent email message you opened...".</span></span>

> [!NOTE]
> <span data-ttu-id="2ef85-131">Derzeit laufen Speer-Phishing-Kampagnen in Attack Simulator nicht ab.</span><span class="sxs-lookup"><span data-stu-id="2ef85-131">Currently, spear phishing campaigns in Attack Simulator don't expire.</span></span>

### <a name="create-a-spear-phishing-campaign"></a><span data-ttu-id="2ef85-132">Erstellen einer Speer-Phishing-Kampagne</span><span class="sxs-lookup"><span data-stu-id="2ef85-132">Create a spear phishing campaign</span></span>

<span data-ttu-id="2ef85-133">Ein wichtiger Bestandteil jeder Speer-Phishing-Kampagne ist das Aussehen und Verhalten der e-Mail-Nachricht, die an die Zielempfänger gesendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ef85-133">An important part of any spear phishing campaign is the look and feel of the email message that's sent to the targeted recipients.</span></span> <span data-ttu-id="2ef85-134">Sie haben folgende Möglichkeiten, um die e-Mail-Nachricht zu erstellen und zu konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="2ef85-134">To create and configure the email message, you have these options:</span></span>

- <span data-ttu-id="2ef85-135">**Verwenden Sie eine integrierte e-Mail-Vorlage**: zwei integrierte Vorlagen stehen zur Verfügung: **Preis Giveaway** -und **Gehaltslisten Update**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-135">**Use a built-in email template**: Two built-in templates are available: **Prize Giveaway** and **Payroll Update**.</span></span> <span data-ttu-id="2ef85-136">Sie können einige, alle oder keine der e-Mail-Eigenschaften von der Vorlage anpassen, wenn Sie die Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="2ef85-136">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="2ef85-137">**Erstellen einer wiederverwendbaren e-Mail-Vorlage**: Nachdem Sie die e-Mail-Vorlage erstellt und gespeichert haben, können Sie Sie in künftigen Spear-Phishing-Kampagnen erneut verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ef85-137">**Create a reusable email template**: After you create and save the email template, you can use it again in future spear phishing campaigns.</span></span> <span data-ttu-id="2ef85-138">Sie können einige, alle oder keine der e-Mail-Eigenschaften von der Vorlage anpassen, wenn Sie die Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="2ef85-138">You can further customize some, all, or none of the email properties from the template when you create and launch the campaign.</span></span>

- <span data-ttu-id="2ef85-139">**Erstellen Sie die e-Mail-Nachricht im Assistenten**: Sie können die e-Mail-Nachricht direkt im Assistenten erstellen, während Sie die Spear-Phishing-Kampagne erstellen und starten.</span><span class="sxs-lookup"><span data-stu-id="2ef85-139">**Create the email message in the wizard**: You can create the email message directly in the wizard as you create and launch the spear phishing campaign.</span></span>

#### <a name="step-1-optional-create-a-custom-email-template"></a><span data-ttu-id="2ef85-140">Schritt 1 (optional): Erstellen einer benutzerdefinierten e-Mail-Vorlage</span><span class="sxs-lookup"><span data-stu-id="2ef85-140">Step 1 (Optional): Create a custom email template</span></span>

<span data-ttu-id="2ef85-141">Wenn Sie eine der integrierten Vorlagen verwenden oder die e-Mail-Nachricht direkt im Assistenten erstellen, können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-141">If you're going to use one of the built-in templates or create the email message directly in the wizard, you can skip this step.</span></span>

1. <span data-ttu-id="2ef85-142">Wechseln Sie im Security & Compliance Center zum **Threat Management** - \> **Angriffs Simulator**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-142">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="2ef85-143">Klicken Sie auf der Seite " **Angriffe simulieren** " entweder in den Abschnitten **Spear Phishing (Credentials Harvest)** oder **Spear Phishing (Attachment)** auf **Attack Details**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-143">On the **Simulate attacks** page, in either the **Spear Phishing (Credentials Harvest)** or **Spear Phishing (Attachment)** sections, click **Attack Details**.</span></span>

   <span data-ttu-id="2ef85-144">Es spielt keine Rolle, wo Sie die Vorlage erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-144">It doesn't matter where you create the template.</span></span> <span data-ttu-id="2ef85-145">Die verfügbaren Optionen in der Vorlage sind für beide Arten von Phishing-Angriffen identisch.</span><span class="sxs-lookup"><span data-stu-id="2ef85-145">The available options in the template are the same for both types of phishing attacks.</span></span>

3. <span data-ttu-id="2ef85-146">Klicken Sie auf der daraufhin geöffneten Seite mit den **Angriffs Details** im Abschnitt **Phishing-Vorlagen** im Bereich **Vorlagen erstellen** auf **neue Vorlage**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-146">In the **Attack details** page that opens, in the **Phishing Templates** section, in the **Create Templates** area, click **New Template**.</span></span>

4. <span data-ttu-id="2ef85-147">Der Assistent zum **Konfigurieren von Phishing-Vorlagen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="2ef85-147">The **Configure Phishing Template** wizard starts in a new flyout.</span></span> <span data-ttu-id="2ef85-148">Geben Sie im Schritt **Start** einen eindeutigen Anzeigenamen für die Vorlage ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-148">In the **Start** step, enter a unique display name for the template, and then click **Next**.</span></span>

5. <span data-ttu-id="2ef85-149">Konfigurieren Sie im Schritt **e-Mail-Details konfigurieren** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="2ef85-149">In the **Configure email details** step, configure the following settings:</span></span>

   - <span data-ttu-id="2ef85-150">**From (Name)**: der Anzeige Name, der für den Absender der Nachricht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ef85-150">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="2ef85-151">**Von (e-Mail)**: die e-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="2ef85-151">**From (Email)**: The sender's email address.</span></span>

   - <span data-ttu-id="2ef85-152">**URL des Phishing-Anmeldeservers**: Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="2ef85-152">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="2ef85-153">Dies ist die URL, auf die Benutzer klicken sollen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-153">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="2ef85-154">Sie können wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="2ef85-154">The choices are:</span></span>

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
     > - <span data-ttu-id="2ef85-155">Alle URLs sind absichtlich HTTP und nicht HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2ef85-155">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="2ef85-156">Ein URL-Reputations Dienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher.</span><span class="sxs-lookup"><span data-stu-id="2ef85-156">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="2ef85-157">Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishing-Kampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ef85-157">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>

   - <span data-ttu-id="2ef85-158">**Benutzerdefinierte Startseiten-URL**: Geben Sie eine optionale Startseite ein, auf der Benutzer angezeigt werden, wenn Sie auf den Link Phishing klicken und die Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-158">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="2ef85-159">Dieser Link ersetzt die standardmäßige Ziel Seite.</span><span class="sxs-lookup"><span data-stu-id="2ef85-159">This link replaces the default landing page.</span></span> <span data-ttu-id="2ef85-160">Wenn Sie beispielsweise ein internes Bewusstseinstraining haben, können Sie diese URL hier angeben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-160">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="2ef85-161">**Kategorie**: Derzeit wird diese Einstellung nicht verwendet (alles, was Sie eingeben, wird ignoriert).</span><span class="sxs-lookup"><span data-stu-id="2ef85-161">**Category**: Currently, this setting isn't used (anything you enter is ignored).</span></span>

   - <span data-ttu-id="2ef85-162">**Subject**: das **Subject** -Feld der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="2ef85-162">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="2ef85-163">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-163">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="2ef85-164">Erstellen Sie im Schritt **e-Mail verfassen** den Nachrichtentext der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="2ef85-164">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="2ef85-165">Sie können die Registerkarte " **e-Mail** " (ein Rich-HTML-Editor) oder die Registerkarte " **Quelle** " (unformatierter HTML-Code) verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ef85-165">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="2ef85-166">Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-166">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="2ef85-167">Sie können Bilder und Text einfügen, um die Glaubwürdigkeit erhöhen der Nachricht im e-Mail-Client des Empfängers zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="2ef85-167">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="2ef85-168">`${username}` Fügt den Namen des Empfängers ein.</span><span class="sxs-lookup"><span data-stu-id="2ef85-168">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="2ef85-169">`${loginserverurl}` Fügt den URL-Wert des **Phishing-Anmeldeservers** aus dem vorherigen Schritt ein.</span><span class="sxs-lookup"><span data-stu-id="2ef85-169">`${loginserverurl}` inserts the **Phishing Login Server URL** value from the previous step.</span></span>

   <span data-ttu-id="2ef85-170">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-170">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="2ef85-171">Klicken Sie im Schritt **bestätigen** auf **Fertig stellen**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-171">In the **Confirm** step, click **Finish**.</span></span>

#### <a name="step-2-create-and-launch-the-spear-phishing-campaign"></a><span data-ttu-id="2ef85-172">Schritt 2: Erstellen und Starten der Spear-Phishing-Kampagne</span><span class="sxs-lookup"><span data-stu-id="2ef85-172">Step 2: Create and launch the spear phishing campaign</span></span>

1. <span data-ttu-id="2ef85-173">Wechseln Sie im Security & Compliance Center zum **Threat Management** - \> **Angriffs Simulator**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-173">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="2ef85-174">Wählen Sie auf der Seite **Angriffe simulieren** eine der folgenden Optionen basierend auf der Art der Kampagne aus, die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="2ef85-174">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="2ef85-175">Klicken Sie im Abschnitt **Spear Phishing (Credentials Harvest)** auf **Angriff starten** oder auf Angriff **Details** \> **starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-175">In the **Spear Phishing (Credentials Harvest)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="2ef85-176">Klicken Sie im Abschnitt **Spear Phishing (Attachment)** auf **Angriff starten** oder auf Angriff **Details** \> **starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-176">In the **Spear Phishing (Attachment)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="2ef85-177">Der Assistent zum **Konfigurieren von Phishing-Angriffen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="2ef85-177">The **Configure Phishing Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="2ef85-178">Führen Sie im **Start** Schritt einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2ef85-178">In the **Start** step, do one of the following steps:</span></span>

   - <span data-ttu-id="2ef85-179">Geben Sie im Feld **Name** einen eindeutigen Anzeigenamen für die Kampagne ein.</span><span class="sxs-lookup"><span data-stu-id="2ef85-179">In the **Name** box, enter a unique display name for the campaign.</span></span> <span data-ttu-id="2ef85-180">Klicken Sie nicht auf **Vorlage verwenden**, da Sie die e-Mail-Nachricht später im Assistenten erstellen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-180">Don't click **Use Template**, because you'll create the email message later in the wizard.</span></span>

   - <span data-ttu-id="2ef85-181">Klicken Sie auf **Vorlage verwenden** , und wählen Sie eine integrierte oder benutzerdefinierte e-Mail-Vorlage aus.</span><span class="sxs-lookup"><span data-stu-id="2ef85-181">Click **Use Template** and select a built-in or custom email template.</span></span> <span data-ttu-id="2ef85-182">Nachdem Sie die Vorlage ausgewählt haben, wird das Feld **Name** automatisch basierend auf der Vorlage ausgefüllt, aber Sie können den Namen ändern.</span><span class="sxs-lookup"><span data-stu-id="2ef85-182">After you select the template, the **Name** box is automatically filled based on the template, but you can change the name.</span></span>

   ![Phishing-Start Seite](../../media/5e93b3cc-5981-462f-8b45-bdf85d97f1b8.jpg)

   <span data-ttu-id="2ef85-184">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-184">When you're finished, click **Next**.</span></span>

4. <span data-ttu-id="2ef85-185">Führen Sie im Schritt **Zielempfänger** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2ef85-185">In the **Target recipients** step, do one of the following steps:</span></span>

   - <span data-ttu-id="2ef85-186">Klicken Sie auf **Adressbuch** , um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-186">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="2ef85-187">Jeder Zielempfänger muss über ein Exchange Online Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-187">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="2ef85-188">Wenn Sie auf **Filtern** und **anwenden** klicken, ohne Suchkriterien einzugeben, werden alle Empfänger zurückgegeben und zur Kampagne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2ef85-188">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="2ef85-189">Klicken Sie auf **Import** dann auf **Dateiimport** , um einen durch Kommas getrennten Wert (CSV) oder eine durch die Datei getrennte Datei mit e-Mail-Adressen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="2ef85-189">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="2ef85-190">Jede Reihe muss die e-Mail-Adresse des Empfängers enthalten.</span><span class="sxs-lookup"><span data-stu-id="2ef85-190">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="2ef85-191">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-191">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2ef85-192">Konfigurieren Sie im Schritt **e-Mail-Details konfigurieren** die folgenden Einstellungen:</span><span class="sxs-lookup"><span data-stu-id="2ef85-192">In the **Configure email details** step, configure the following settings:</span></span>

   <span data-ttu-id="2ef85-193">Wenn Sie im **Start** Schritt eine Vorlage ausgewählt haben, sind die meisten dieser Werte bereits konfiguriert, aber Sie können Sie ändern.</span><span class="sxs-lookup"><span data-stu-id="2ef85-193">If you selected a template in the **Start** step, most of these values are already configured, but you can change them.</span></span>

   - <span data-ttu-id="2ef85-194">**From (Name)**: der Anzeige Name, der für den Absender der Nachricht verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="2ef85-194">**From (Name)**: The display name that's used for the message sender.</span></span>

   - <span data-ttu-id="2ef85-195">**Von (e-Mail)**: die e-Mail-Adresse des Absenders.</span><span class="sxs-lookup"><span data-stu-id="2ef85-195">**From (Email)**: The sender's email address.</span></span> <span data-ttu-id="2ef85-196">Sie können eine reale oder gefälschte e-Mail-Adresse aus der e-Mail-Domäne Ihrer Organisation eingeben, oder Sie können eine reale oder gefälschte externe e-Mail-Adresse eingeben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-196">You can enter a real or fake email address from your organization's email domain, or you can enter a real or fake external email address.</span></span> <span data-ttu-id="2ef85-197">Eine gültige Absender-e-Mail-Adresse aus Ihrer Organisation wird tatsächlich im e-Mail-Client des Empfängers aufgelöst.</span><span class="sxs-lookup"><span data-stu-id="2ef85-197">A valid sender email address from your organization will actually resolve in the recipient's email client.</span></span>

   - <span data-ttu-id="2ef85-198">**URL des Phishing-Anmeldeservers**: Klicken Sie auf die Dropdownliste, und wählen Sie eine der verfügbaren URLs aus der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="2ef85-198">**Phishing Login Server URL**: Click the drop down and select one of the available URLs from the list.</span></span> <span data-ttu-id="2ef85-199">Dies ist die URL, auf die Benutzer klicken sollen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-199">This is the URL that users will be tempted to click.</span></span> <span data-ttu-id="2ef85-200">Sie können wie folgt vorgehen:</span><span class="sxs-lookup"><span data-stu-id="2ef85-200">The choices are:</span></span>

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
     > - <span data-ttu-id="2ef85-201">Alle URLs sind absichtlich HTTP und nicht HTTPS.</span><span class="sxs-lookup"><span data-stu-id="2ef85-201">All of the URLs are intentionally http, not https.</span></span>
     >
     > - <span data-ttu-id="2ef85-202">Ein URL-Reputations Dienst identifiziert möglicherweise eine oder mehrere dieser URLs als unsicher.</span><span class="sxs-lookup"><span data-stu-id="2ef85-202">A URL reputation service might identify one or more of these URLs as unsafe.</span></span> <span data-ttu-id="2ef85-203">Überprüfen Sie die Verfügbarkeit der URL in Ihren unterstützten Webbrowsern, bevor Sie die URL in einer Phishing-Kampagne verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ef85-203">Check the availability of the URL in your supported web browsers before you use the URL in a phishing campaign.</span></span>
     >
     > - <span data-ttu-id="2ef85-204">Sie müssen eine URL auswählen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-204">You are required to select a URL.</span></span> <span data-ttu-id="2ef85-205">Bei Kampagnen mit **Spear-Phishing (Attachment)** können Sie den Link aus dem Textkörper der Nachricht im nächsten Schritt entfernen (andernfalls enthält die Nachricht sowohl einen Link als **auch** eine Anlage).</span><span class="sxs-lookup"><span data-stu-id="2ef85-205">For **Spear Phishing (Attachment)** campaigns, you can remove the link from the body of the message in the next step (otherwise, the message will contain both a link **and** an attachment).</span></span>

   - <span data-ttu-id="2ef85-206">**Anlagentyp**: Diese Einstellung ist nur in Kampagnen für **Spear-Phishing (Attachment)** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2ef85-206">**Attachment Type**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="2ef85-207">Klicken Sie auf die Dropdownliste, und wählen Sie aus **. DOCX** oder **. PDF** aus der Liste.</span><span class="sxs-lookup"><span data-stu-id="2ef85-207">Click the drop down and select **.DOCX** or **.PDF** from the list.</span></span>

   - <span data-ttu-id="2ef85-208">**Name der Anlage**: Diese Einstellung ist nur in Kampagnen für **Spear-Phishing (Attachment)** verfügbar.</span><span class="sxs-lookup"><span data-stu-id="2ef85-208">**Attachment Name**: This setting is only available in **Spear Phishing (Attachment)** campaigns.</span></span> <span data-ttu-id="2ef85-209">Geben Sie einen Dateinamen für die Datei. docx oder. PDF ein.</span><span class="sxs-lookup"><span data-stu-id="2ef85-209">Enter a filename for the .docx or .pdf attachment.</span></span>

   - <span data-ttu-id="2ef85-210">**Benutzerdefinierte Startseiten-URL**: Geben Sie eine optionale Startseite ein, auf der Benutzer angezeigt werden, wenn Sie auf den Link Phishing klicken und die Anmeldeinformationen eingeben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-210">**Custom Landing Page URL**: Enter an optional landing page where users are taken if they click the phishing link and enter their credentials.</span></span> <span data-ttu-id="2ef85-211">Dieser Link ersetzt die standardmäßige Ziel Seite.</span><span class="sxs-lookup"><span data-stu-id="2ef85-211">This link replaces the default landing page.</span></span> <span data-ttu-id="2ef85-212">Wenn Sie beispielsweise ein internes Bewusstseinstraining haben, können Sie diese URL hier angeben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-212">For example, if you have internal awareness training, you can specify that URL here.</span></span>

   - <span data-ttu-id="2ef85-213">**Subject**: das **Subject** -Feld der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="2ef85-213">**Subject**: The **Subject** field of the email message.</span></span>

   <span data-ttu-id="2ef85-214">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-214">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="2ef85-215">Erstellen Sie im Schritt **e-Mail verfassen** den Nachrichtentext der e-Mail-Nachricht.</span><span class="sxs-lookup"><span data-stu-id="2ef85-215">In the **Compose email** step, create the message body of the email message.</span></span> <span data-ttu-id="2ef85-216">Wenn Sie im **Start** Schritt eine Vorlage ausgewählt haben, ist der Nachrichtentext bereits konfiguriert, Sie können ihn jedoch anpassen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-216">If you selected a template in the **Start** step, the message body is already configured, but you can customize it.</span></span> <span data-ttu-id="2ef85-217">Sie können die Registerkarte " **e-Mail** " (ein Rich-HTML-Editor) oder die Registerkarte " **Quelle** " (unformatierter HTML-Code) verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ef85-217">You can use the **Email** tab (a rich HTML editor) or the **Source** tab (raw HTML code).</span></span>

   <span data-ttu-id="2ef85-218">Die HTML-Formatierung kann so einfach oder komplex sein, wie Sie es benötigen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-218">The HTML formatting can be as simple or complex as you need it to be.</span></span> <span data-ttu-id="2ef85-219">Sie können Bilder und Text einfügen, um die Glaubwürdigkeit erhöhen der Nachricht im e-Mail-Client des Empfängers zu verbessern.</span><span class="sxs-lookup"><span data-stu-id="2ef85-219">You can insert images and text to enhance the believability of the message in the recipient's email client.</span></span>

   - <span data-ttu-id="2ef85-220">`${username}` Fügt den Namen des Empfängers ein.</span><span class="sxs-lookup"><span data-stu-id="2ef85-220">`${username}` inserts the recipient's name.</span></span>

   - <span data-ttu-id="2ef85-221">`${loginserverurl}` Fügt den URL-Wert für den **Phishing-Anmelde Server** ein.</span><span class="sxs-lookup"><span data-stu-id="2ef85-221">`${loginserverurl}` inserts the **Phishing Login Server URL** value.</span></span>

   <span data-ttu-id="2ef85-222">Bei Kampagnen mit **Spear-Phishing (Attachment)** sollten Sie den Link aus dem Nachrichtentext entfernen (andernfalls enthält die Nachricht sowohl einen Link als **auch** eine Anlage, und Link Klicks werden nicht in einer Anlagen Kampagne nachverfolgt).</span><span class="sxs-lookup"><span data-stu-id="2ef85-222">For **Spear Phishing (Attachment)** campaigns, you should remove the link from the body of the message (otherwise, the message will contain both a link **and** an attachment, and link clicks aren't tracked in an attachment campaign).</span></span>

   ![E-Mail-Textkörper erstellen](../../media/9bd65af4-1f9d-45c1-8c06-796d7ccfd425.jpg)

   <span data-ttu-id="2ef85-224">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-224">When you're finished, click **Next**.</span></span>

7. <span data-ttu-id="2ef85-225">Klicken Sie im Schritt **bestätigen** auf **Fertig stellen** , um die Kampagne zu starten.</span><span class="sxs-lookup"><span data-stu-id="2ef85-225">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="2ef85-226">Die Phishing-Nachricht wird an die Zielempfänger übermittelt.</span><span class="sxs-lookup"><span data-stu-id="2ef85-226">The phishing message is delivered to the targeted recipients.</span></span>

## <a name="password-attack-campaigns"></a><span data-ttu-id="2ef85-227">Kenn Wort Angriffs Kampagnen</span><span class="sxs-lookup"><span data-stu-id="2ef85-227">Password attack campaigns</span></span>

<span data-ttu-id="2ef85-228">Ein *Kennwortangriff* versucht, Kennwörter für Benutzerkonten in einer Organisation zu erraten, in der Regel, nachdem der Angreifer mindestens ein gültiges Benutzerkonto erkannt hat.</span><span class="sxs-lookup"><span data-stu-id="2ef85-228">A *password attack* tries to guess passwords for user accounts in an organization, typically after the attacker has identified one or more valid user accounts.</span></span>

<span data-ttu-id="2ef85-229">In Attack Simulator stehen zwei verschiedene Arten von Kenn Wort Angriffs Kampagnen zur Verfügung, um die Komplexität der Kennwörter Ihrer Benutzer zu testen:</span><span class="sxs-lookup"><span data-stu-id="2ef85-229">In Attack Simulator, two different types of password attack campaigns are available for you to test the complexity of your users' passwords:</span></span>

- <span data-ttu-id="2ef85-230">**Brute-Force-Kennwort (Wörterbuchangriff)**: bei einem *Brute-Force* -oder *Wörterbuch* Angriff wird eine große Wörterbuchdatei mit Kennwörtern für ein Benutzerkonto verwendet, wobei die Hoffnung besteht, dass einer von Ihnen funktioniert (viele Kennwörter für ein Konto).</span><span class="sxs-lookup"><span data-stu-id="2ef85-230">**Brute force password (dictionary attack)**: A *brute force* or *dictionary* attack uses a large dictionary file of passwords on a user account with the hope that one of them will work (many passwords against one account).</span></span> <span data-ttu-id="2ef85-231">Falsche Kenn Wort Sperren helfen, Brute-Force-Kennwortangriffe zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="2ef85-231">Incorrect password lock-outs help deter brute force password attacks.</span></span>

  <span data-ttu-id="2ef85-232">Für den Wörterbuchangriff können Sie ein oder mehrere Kennwörter angeben, die Sie ausprobieren möchten (manuell eingegeben oder in eine hochgeladene Datei), und Sie können einen oder mehrere Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-232">For the dictionary attack, you can specify one or many passwords to try (manually entered or in an uploaded file), and you can specify one or many users.</span></span>

- <span data-ttu-id="2ef85-233">**Kenn Wort Sprüh Angriff**: bei einem *Kenn Wort Sprüh* Angriff wird dasselbe sorgfältig überprüfte Kennwort für eine Liste von Benutzerkonten verwendet (ein Kennwort für viele Konten).</span><span class="sxs-lookup"><span data-stu-id="2ef85-233">**Password spray attack**: A *password spray* attack uses the same carefully considered password against a list of user accounts (one password against many accounts).</span></span> <span data-ttu-id="2ef85-234">Kenn Wort Sprüh Angriffe sind schwerer zu erkennen als Brute-Force-Kennwortangriffe (die Erfolgswahrscheinlichkeit steigt, wenn ein Angreifer ein Kennwort in Dutzenden oder Hunderten von Konten versucht, ohne dass die falsche Kenn Wort Sperrung des Benutzers ausgelöst wird).</span><span class="sxs-lookup"><span data-stu-id="2ef85-234">Password spray attacks are harder to detect than brute force password attacks (the probability of success increases when an attacker tries one password across dozens or hundreds of accounts without the risk of tripping the user's incorrect password lock-out).</span></span>

  <span data-ttu-id="2ef85-235">Für den Kenn Wort Sprüh Angriff können Sie nur ein Kennwort angeben, das Sie ausprobieren möchten, und Sie können einen oder mehrere Benutzer angeben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-235">For the password spray attack, you can only specify one password to try, and you can specify one or many users.</span></span>

> [!NOTE]
> <span data-ttu-id="2ef85-236">Die Kennwortangriffe im Angriffs Simulator übergeben Benutzernamen-und Kenn Wort grundlegende Authentifizierungsanforderungen an einen Endpunkt, sodass Sie auch mit anderen Authentifizierungsmethoden (AD FS, Kennworthash Synchronisierung, Pass-Through, PingFederate usw.) funktionieren.</span><span class="sxs-lookup"><span data-stu-id="2ef85-236">The password attacks in Attack Simulator pass username and password Basic auth requests to an endpoint, so they also work with other authentication methods (AD FS, password hash sync, pass-through, PingFederate, etc.).</span></span> <span data-ttu-id="2ef85-237">Für Benutzer, die MFA aktiviert haben, wird der Versuch, selbst wenn der Kennwortangriff sein tatsächliches Kennwort versucht, immer als Fehler registriert (in anderen Worten: MFA-Benutzer werden nie in der Anzahl der **erfolgreichen Versuche** der Kampagne angezeigt).</span><span class="sxs-lookup"><span data-stu-id="2ef85-237">For users that have MFA enabled, even if the password attack tries their actual password, the attempt will always register as a failure (in other words, MFA users will never appear in the **Successful attempts** count of the campaign).</span></span> <span data-ttu-id="2ef85-238">Dies ist das erwartete Ergebnis.</span><span class="sxs-lookup"><span data-stu-id="2ef85-238">This is the expected result.</span></span> <span data-ttu-id="2ef85-239">MFA ist eine primäre Methode zum Schutz vor Kennwortangriffen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-239">MFA is a primary method to help protect against password attacks.</span></span>

### <a name="create-and-launch-a-password-attack-campaign"></a><span data-ttu-id="2ef85-240">Erstellen und Starten einer Kenn Wort Angriffs Kampagne</span><span class="sxs-lookup"><span data-stu-id="2ef85-240">Create and launch a password attack campaign</span></span>

1. <span data-ttu-id="2ef85-241">Wechseln Sie im Security & Compliance Center zum **Threat Management** - \> **Angriffs Simulator**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-241">In the Security & Compliance Center, go to **Threat management** \> **Attack simulator**.</span></span>

2. <span data-ttu-id="2ef85-242">Wählen Sie auf der Seite **Angriffe simulieren** eine der folgenden Optionen basierend auf der Art der Kampagne aus, die Sie erstellen möchten:</span><span class="sxs-lookup"><span data-stu-id="2ef85-242">On the **Simulate attacks** page, make one of the following selections based on the type of campaign you want to create:</span></span>

   - <span data-ttu-id="2ef85-243">Klicken Sie im Abschnitt **Brute-Force-Kennwort (Wörterbuchangriff)** auf **Angriff starten** , oder klicken Sie auf Angriff **Details** \> **starten**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-243">In the **Brute Force Password (Dictionary Attack)** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

   - <span data-ttu-id="2ef85-244">Klicken Sie im Abschnitt **Kenn Wort Sprüh Angriff** auf **Angriff starten** oder auf Angriff **Details** \> **starten Angriff**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-244">in the **Password spray attack** section, click **Launch Attack** or click **Attack Details** \> **Launch Attack**.</span></span>

3. <span data-ttu-id="2ef85-245">Der Assistent zum **Konfigurieren von Kennwortangriffen** wird in einem neuen Flyout gestartet.</span><span class="sxs-lookup"><span data-stu-id="2ef85-245">The **Configure Password Attack** wizard starts in a new flyout.</span></span> <span data-ttu-id="2ef85-246">Geben Sie im Schritt **Start** einen eindeutigen Anzeigenamen für die Kampagne ein, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-246">In the **Start** step, enter a unique display name for the campaign, and then click **Next**.</span></span>

4. <span data-ttu-id="2ef85-247">Führen Sie im Schritt **Zielbenutzer** einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2ef85-247">In the **Target users** step, do one of the following steps:</span></span>

   - <span data-ttu-id="2ef85-248">Klicken Sie auf **Adressbuch** , um die Empfänger (Benutzer oder Gruppen) für die Kampagne auszuwählen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-248">Click **Address Book** to select the recipients (users or groups) for the campaign.</span></span> <span data-ttu-id="2ef85-249">Jeder Zielempfänger muss über ein Exchange Online Postfach verfügen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-249">Each targeted recipient must have an Exchange Online mailbox.</span></span> <span data-ttu-id="2ef85-250">Wenn Sie auf **Filtern** und **anwenden** klicken, ohne Suchkriterien einzugeben, werden alle Empfänger zurückgegeben und zur Kampagne hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2ef85-250">If you click **Filter** and **Apply** without entering a search criteria, all recipients are returned and added to the campaign.</span></span>

   - <span data-ttu-id="2ef85-251">Klicken Sie auf **Import** dann auf **Dateiimport** , um einen durch Kommas getrennten Wert (CSV) oder eine durch die Datei getrennte Datei mit e-Mail-Adressen zu importieren.</span><span class="sxs-lookup"><span data-stu-id="2ef85-251">Click **Import** then **File Import** to import a comma-separated value (CSV) or line-separated file of email addresses.</span></span> <span data-ttu-id="2ef85-252">Jede Reihe muss die e-Mail-Adresse des Empfängers enthalten.</span><span class="sxs-lookup"><span data-stu-id="2ef85-252">Each line must contain the recipient's email address.</span></span>

   <span data-ttu-id="2ef85-253">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-253">When you're finished, click **Next**.</span></span>

5. <span data-ttu-id="2ef85-254">Wählen Sie im Schritt **Angriffs Einstellungen auswählen** aus, welche Aktionen basierend auf dem Kampagnentyp vorgenommen werden sollen:</span><span class="sxs-lookup"><span data-stu-id="2ef85-254">In the **Choose attack settings** step, choose what to do based on the campaign type:</span></span>

   - <span data-ttu-id="2ef85-255">**Brute-Force-Kennwort (Wörterbuchangriff)**: führen Sie einen der folgenden Schritte aus:</span><span class="sxs-lookup"><span data-stu-id="2ef85-255">**Brute Force Password (Dictionary Attack)**: Do either of the following steps:</span></span>

     - <span data-ttu-id="2ef85-256">**Manuelles Eingeben von Kennwörtern**: Geben Sie in das Feld **EINGABETASTE drücken, um ein Kennwort hinzuzufügen** ein Kennwort ein, und drücken Sie dann die EINGABETASTE.</span><span class="sxs-lookup"><span data-stu-id="2ef85-256">**Enter passwords manually**: In the **Press enter to add a password** box, type a password and then press ENTER.</span></span> <span data-ttu-id="2ef85-257">Wiederholen Sie diesen Schritt so oft wie nötig.</span><span class="sxs-lookup"><span data-stu-id="2ef85-257">Repeat this step as many times as necessary.</span></span>

     - <span data-ttu-id="2ef85-258">**Hochladen von Kennwörtern aus einer Wörterbuchdatei**: Klicken Sie auf **hochladen** , um eine vorhandene Textdatei zu importieren, die in jeder Zeile ein Kennwort enthält, und eine leere letzte Zeile.</span><span class="sxs-lookup"><span data-stu-id="2ef85-258">**Upload passwords from a dictionary file**: Click **Upload** to import an existing text file that contains one password on each line and a blank last line.</span></span> <span data-ttu-id="2ef85-259">Die Textdatei muss mindestens 10 MB groß sein und darf nicht mehr als 30000 Kennwörter enthalten.</span><span class="sxs-lookup"><span data-stu-id="2ef85-259">The text file must be 10 MB or less in size, and can't contain more than 30000 passwords.</span></span>

   - <span data-ttu-id="2ef85-260">**Kenn Wort Sprüh Angriff**: Geben Sie in **den zu verwendenden Kennwörtern im Feld Angriff** ein Kennwort ein.</span><span class="sxs-lookup"><span data-stu-id="2ef85-260">**Password spray attack**: In **The password(s) to use in the attack** box, enter one password.</span></span>

   <span data-ttu-id="2ef85-261">Klicken Sie nach Abschluss des Vorgangs auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-261">When you're finished, click **Next**.</span></span>

6. <span data-ttu-id="2ef85-262">Klicken Sie im Schritt **bestätigen** auf **Fertig stellen** , um die Kampagne zu starten.</span><span class="sxs-lookup"><span data-stu-id="2ef85-262">In the **Confirm** step, click **Finish** to launch the campaign.</span></span> <span data-ttu-id="2ef85-263">Die von Ihnen angegebenen Kennwörter werden für Benutzer ausprobiert, die Sie angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-263">The passwords you specified are tried on users you specified.</span></span>

## <a name="view-campaign-results"></a><span data-ttu-id="2ef85-264">Anzeigen von kampagnenergebnissen</span><span class="sxs-lookup"><span data-stu-id="2ef85-264">View campaign results</span></span>

<span data-ttu-id="2ef85-265">Nachdem Sie eine Kampagne gestartet haben, können Sie den Fortschritt und die Ergebnisse auf der Seite Haupt **Angriffe simulieren** überprüfen.</span><span class="sxs-lookup"><span data-stu-id="2ef85-265">After you launch a campaign, you can check the progress and results on the main **Simulate attacks** page.</span></span>

<span data-ttu-id="2ef85-266">In aktiven Kampagnen wird eine Statusleiste, ein abgeschlossener Prozentwert und "(abgeschlossene Benutzer) von (Gesamtanzahl der Benutzer)" angezeigt.</span><span class="sxs-lookup"><span data-stu-id="2ef85-266">Active campaigns will show a status bar, a completed percentage value and "(completed users) of (total users)" count.</span></span> <span data-ttu-id="2ef85-267">Durch Klicken auf die Schaltfläche **Aktualisieren** wird der Status aller aktiven Kampagnen aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="2ef85-267">Clicking the **Refresh** button will update the progress of any active campaigns.</span></span> <span data-ttu-id="2ef85-268">Sie können auch auf **Beenden** klicken, um eine aktive Kampagne zu beenden.</span><span class="sxs-lookup"><span data-stu-id="2ef85-268">You can also click **Terminate** to stop an active campaign.</span></span>

<span data-ttu-id="2ef85-269">Wenn die Kampagne abgeschlossen ist, wird der Status in **Angriff abgeschlossen**geändert.</span><span class="sxs-lookup"><span data-stu-id="2ef85-269">When the campaign is finished, the status changes to **Attack completed**.</span></span> <span data-ttu-id="2ef85-270">Sie können die Ergebnisse der Kampagne anzeigen, indem Sie eine der folgenden Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="2ef85-270">You can view the results of the campaign by doing either of the following actions:</span></span>

- <span data-ttu-id="2ef85-271">Klicken Sie auf der Seite Haupt **Angriffe simulieren** auf **Bericht anzeigen** unter dem Namen der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="2ef85-271">On the main **Simulate attacks** page, click **View Report** under the name of the campaign.</span></span>

- <span data-ttu-id="2ef85-272">Klicken Sie auf der Seite Haupt **Angriffe simulieren** auf **Angriffs Details** im Abschnitt für den Typ des Angriffs.</span><span class="sxs-lookup"><span data-stu-id="2ef85-272">On the main **Simulate attacks** page, click **Attack Details** in the section for the type of attack.</span></span> <span data-ttu-id="2ef85-273">Wählen Sie auf der Seite **Angriffs Details** , die geöffnet wird, die Kampagne im Abschnitt **Angriffs Verlauf** aus.</span><span class="sxs-lookup"><span data-stu-id="2ef85-273">On the **Attack details** page that opens, select the campaign in the **Attack History** section.</span></span>

<span data-ttu-id="2ef85-274">Mit einer der vorherigen Aktionen gelangen Sie zu einer Seite mit dem Namen " **Angriffs Details**".</span><span class="sxs-lookup"><span data-stu-id="2ef85-274">Either of the previous actions will take you to a page named **Attack details**.</span></span> <span data-ttu-id="2ef85-275">Die Informationen, die auf dieser Seite für jede Art von Kampagne zur Verfügung stehen, werden in den folgenden Abschnitten beschrieben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-275">The information that's available on this page for each type of campaign is described in the following sections.</span></span>

### <a name="spear-phishing-credentials-harvest-campaign-results"></a><span data-ttu-id="2ef85-276">Kampagnenergebnisse für Spear-Phishing (Sammeln von Anmeldeinformationen)</span><span class="sxs-lookup"><span data-stu-id="2ef85-276">Spear Phishing (Credentials Harvest) campaign results</span></span>

<span data-ttu-id="2ef85-277">Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="2ef85-277">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="2ef85-278">Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="2ef85-278">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="2ef85-279">**Zielgruppe der Gesamtbenutzer**</span><span class="sxs-lookup"><span data-stu-id="2ef85-279">**Total users targeted**</span></span>

- <span data-ttu-id="2ef85-280">**Erfolgreiche Versuche**: die Anzahl der Benutzer, die auf den Link geklickt **und** Ihre Anmeldeinformationen eingegeben haben (*beliebiger* Benutzername und Kennwortwert).</span><span class="sxs-lookup"><span data-stu-id="2ef85-280">**Successful attempts**: The number of users who clicked the link **and** entered their credentials (*any* username and password value).</span></span>

- <span data-ttu-id="2ef85-281">**Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen**berechnet wird  /  .**Gesamtzahl der Benutzer**, die gezielt sind.</span><span class="sxs-lookup"><span data-stu-id="2ef85-281">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="2ef85-282">**Schnellster Mausklick**: wie lange es dauerte, bis der erste Benutzer auf den Link klickt, nachdem Sie die Kampagne gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-282">**Fastest Click**: How long it took the first user to click the link after you launched the campaign.</span></span>

- <span data-ttu-id="2ef85-283">**Durchschnittlicher Mausklick**: die Summe, wie lange es dauerte, bis jeder auf den Link geklickt hat, dividiert durch die Anzahl der Benutzer, die auf den Link geklickt haben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-283">**Average Click**: The sum of how long it took everyone to click the link divided by the number of users who clicked the link.</span></span>

- <span data-ttu-id="2ef85-284">**Klicken Sie auf Erfolgs Rate**: einen Prozentsatz, der von berechnet wird (Anzahl der Benutzer, die auf den Link geklickt haben)/Gesamtanzahl der Benutzer, die als **Ziel**ausgewählt wurden</span><span class="sxs-lookup"><span data-stu-id="2ef85-284">**Click Success Rate**: A percentage that's calculated by (number of users who clicked the link) / **Total users targeted**.</span></span>

- <span data-ttu-id="2ef85-285">**Schnellste Anmeldeinformationen**: wie lange dauerte es, bis der erste Benutzer seine Anmeldeinformationen eingegeben hat, nachdem die Kampagne gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="2ef85-285">**Fastest Credentials**: How long it took the first user to enter their credentials after you launched the campaign.</span></span>

- <span data-ttu-id="2ef85-286">**Durchschnittliche Anmeldeinformationen**: die Summe der Dauer, die jeder zum Eingeben der Anmeldeinformationen benötigte, dividiert durch die Anzahl der Benutzer, die Ihre Anmeldeinformationen eingegeben haben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-286">**Average Credentials**: The sum of how long it took everyone to enter their credentials divided by the number of users who entered their credentials.</span></span>

- <span data-ttu-id="2ef85-287">**Erfolgs Rate der Anmeldeinformationen**: ein Prozentsatz, der von berechnet wird (Anzahl der Benutzer, die Ihre Anmeldeinformationen eingegeben haben)/Gesamtanzahl der Benutzer, die **zielgerichtet**sind.</span><span class="sxs-lookup"><span data-stu-id="2ef85-287">**Credential Success Rate**: A percentage that's calculated by (number of users who entered their credentials) / **Total users targeted**.</span></span>

- <span data-ttu-id="2ef85-288">Ein Balkendiagramm, in dem der **Link geklickt** wird und die Anzahl der **Anmeldeinformationen** pro Tag angegeben wird.</span><span class="sxs-lookup"><span data-stu-id="2ef85-288">A bar graph that shows the **Link clicked** and **Credential supplied** numbers per day.</span></span>

- <span data-ttu-id="2ef85-289">Ein Kreisdiagramm, in dem der **angeklickte Link**, die **angegebenen Anmeldeinformationen**und **keine** Prozentsätze für die Kampagne angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="2ef85-289">A circle graph that shows the **Link clicked**, **Credential supplied**, and **None** percentages for the campaign.</span></span>

- <span data-ttu-id="2ef85-290">Im Abschnitt **kompromittierte Benutzer** werden die Details der Benutzer aufgelistet, die auf den Link geklickt haben:</span><span class="sxs-lookup"><span data-stu-id="2ef85-290">The **Compromised Users** section lists the details of the users who clicked the link:</span></span>

  - <span data-ttu-id="2ef85-291">Die E-Mail-Adresse des Benutzers</span><span class="sxs-lookup"><span data-stu-id="2ef85-291">The user's email address</span></span>

  - <span data-ttu-id="2ef85-292">Das Datum/die Uhrzeit, zu dem der Link geklickt hat.</span><span class="sxs-lookup"><span data-stu-id="2ef85-292">The date/time when they clicked the link.</span></span>

  - <span data-ttu-id="2ef85-293">Die Client-IP-Adresse.</span><span class="sxs-lookup"><span data-stu-id="2ef85-293">The client IP address.</span></span>

  - <span data-ttu-id="2ef85-294">Details zur Benutzerversion von Windows und Webbrowser.</span><span class="sxs-lookup"><span data-stu-id="2ef85-294">Details about the user's version of Windows and web browser.</span></span>

  <span data-ttu-id="2ef85-295">Sie können auf **exportieren** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="2ef85-295">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="spear-phishing-attachment-campaign-results"></a><span data-ttu-id="2ef85-296">Kampagnenergebnisse für Spear-Phishing (Attachment)</span><span class="sxs-lookup"><span data-stu-id="2ef85-296">Spear Phishing (Attachment) campaign results</span></span>

<span data-ttu-id="2ef85-297">Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="2ef85-297">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="2ef85-298">Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="2ef85-298">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="2ef85-299">**Zielgruppe der Gesamtbenutzer**</span><span class="sxs-lookup"><span data-stu-id="2ef85-299">**Total users targeted**</span></span>

- <span data-ttu-id="2ef85-300">**Erfolgreiche Versuche**: die Anzahl der Benutzer, die die Anlage geöffnet oder heruntergeladen und geöffnet haben (Vorschau wird nicht gezählt).</span><span class="sxs-lookup"><span data-stu-id="2ef85-300">**Successful attempts**: The number of users who opened or downloaded and opened the attachment (preview doesn't count).</span></span>

- <span data-ttu-id="2ef85-301">**Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen**berechnet wird  /  .**Gesamtzahl der Benutzer**, die gezielt sind.</span><span class="sxs-lookup"><span data-stu-id="2ef85-301">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="2ef85-302">**Schnellste Anlage Open Time**: wie lange dauerte es, bis der erste Benutzer die Anlage geöffnet hat, nachdem Sie die Kampagne gestartet haben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-302">**Fastest attachment open time**: How long it took the first user to open the attachment after you launched the campaign.</span></span>

- <span data-ttu-id="2ef85-303">**Open Time (durchschnittliche Anlage**): die Summe der Dauer, die jeder zum Öffnen der Anlage benötigte, dividiert durch die Anzahl der Benutzer, die die Anlage geöffnet haben.</span><span class="sxs-lookup"><span data-stu-id="2ef85-303">**Average attachment open time**: The sum of how long it took everyone to open the attachment divided by the number of users who opened the attachment.</span></span>

- <span data-ttu-id="2ef85-304">**Anlage offene Erfolgsrate**: ein Prozentsatz, der von berechnet wird (Anzahl der Benutzer, die die Anlage geöffnet haben)/Gesamtanzahl der **Zielbenutzer**.</span><span class="sxs-lookup"><span data-stu-id="2ef85-304">**Attachment open success rate**: A percentage that's calculated by (number of users who opened the attachment) / **Total users targeted**.</span></span>

### <a name="brute-force-password-dictionary-attack-campaign-results"></a><span data-ttu-id="2ef85-305">Kampagnenergebnisse für Brute-Force-Kennwort (Wörterbuchangriffe)</span><span class="sxs-lookup"><span data-stu-id="2ef85-305">Brute Force Password (Dictionary Attack) campaign results</span></span>

<span data-ttu-id="2ef85-306">Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="2ef85-306">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="2ef85-307">Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="2ef85-307">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="2ef85-308">**Zielgruppe der Gesamtbenutzer**</span><span class="sxs-lookup"><span data-stu-id="2ef85-308">**Total users targeted**</span></span>

- <span data-ttu-id="2ef85-309">**Erfolgreiche Versuche**: die Anzahl der Benutzer, bei denen festgestellt wurde, dass Sie eines der angegebenen Kennwörter verwenden.</span><span class="sxs-lookup"><span data-stu-id="2ef85-309">**Successful attempts**: The number of users who were found to be using one of the specified passwords.</span></span>

- <span data-ttu-id="2ef85-310">**Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen**berechnet wird  /  .**Gesamtzahl der Benutzer**, die gezielt sind.</span><span class="sxs-lookup"><span data-stu-id="2ef85-310">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>

- <span data-ttu-id="2ef85-311">Im Abschnitt **kompromittierte Benutzer** werden die e-Mail-Adressen der betroffenen Benutzer aufgelistet.</span><span class="sxs-lookup"><span data-stu-id="2ef85-311">The **Compromised Users** section lists the email addresses of the affected users.</span></span> <span data-ttu-id="2ef85-312">Sie können auf **exportieren** klicken, um die Ergebnisse in eine CSV-Datei zu exportieren.</span><span class="sxs-lookup"><span data-stu-id="2ef85-312">You can click **Export** to export the results to a CSV file.</span></span>

### <a name="password-spray-attack-campaign-results"></a><span data-ttu-id="2ef85-313">Kenn Wort Sprüh Angriff-Kampagnenergebnisse</span><span class="sxs-lookup"><span data-stu-id="2ef85-313">Password spray attack campaign results</span></span>

<span data-ttu-id="2ef85-314">Die folgenden Informationen sind auf der Seite mit den **Angriffs Details** für jede Kampagne verfügbar:</span><span class="sxs-lookup"><span data-stu-id="2ef85-314">The following information is available on the **Attack details** page for each campaign:</span></span>

- <span data-ttu-id="2ef85-315">Die Dauer (Startdatum/-Uhrzeit und Enddatum/-Uhrzeit) der Kampagne.</span><span class="sxs-lookup"><span data-stu-id="2ef85-315">The duration (start date/time and end date/time) of the campaign.</span></span>

- <span data-ttu-id="2ef85-316">**Zielgruppe der Gesamtbenutzer**</span><span class="sxs-lookup"><span data-stu-id="2ef85-316">**Total users targeted**</span></span>

- <span data-ttu-id="2ef85-317">**Erfolgreiche Versuche**: die Anzahl der Benutzer, für die das angegebene Kennwort verwendet wurde.</span><span class="sxs-lookup"><span data-stu-id="2ef85-317">**Successful attempts**: The number of users who were found to be using the specified password.</span></span>

- <span data-ttu-id="2ef85-318">**Gesamterfolgs Rate**: ein Prozentsatz, der von **erfolgreichen versuchen**berechnet wird  /  .**Gesamtzahl der Benutzer**, die gezielt sind.</span><span class="sxs-lookup"><span data-stu-id="2ef85-318">**Overall Success Rate**: A percentage that's calculated by **Successful attempts** / **Total users targeted**.</span></span>
