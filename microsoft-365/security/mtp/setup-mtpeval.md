---
title: Einrichten Ihrer Microsoft 365 Defender Test Lab-oder Pilotumgebung
description: Greifen Sie auf Microsoft 365 Security Center zu, und richten Sie Ihre Microsoft 365 Defender Test Lab-Umgebung ein.
keywords: Microsoft Threat Protection-Test-Setup, Microsoft Threat Protection Pilot-Setup, Testen von Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab-Setup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 503b7a6a6b3ad6394293e9f70dbdd336f6bee9dd
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131309"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="f51ec-104">Einrichten Ihrer Microsoft 365 Defender Test Lab-Umgebung</span><span class="sxs-lookup"><span data-stu-id="f51ec-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="f51ec-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f51ec-105">**Applies to:**</span></span>
- <span data-ttu-id="f51ec-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f51ec-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="f51ec-107">Das Erstellen eines Microsoft 365 Defender-Testlabors oder einer Pilotumgebung und deren Bereitstellung ist ein dreistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="f51ec-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="f51ec-108">[![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="f51ec-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="f51ec-109">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="f51ec-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="f51ec-111">Phase 2: Einrichten</span><span class="sxs-lookup"><span data-stu-id="f51ec-111">Phase 2: Set up</span></span> |<span data-ttu-id="f51ec-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="f51ec-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span></span><br/>[<span data-ttu-id="f51ec-113">Phase 3: Onboard</span><span class="sxs-lookup"><span data-stu-id="f51ec-113">Phase 3: Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="f51ec-114">[![Zurück zu Pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="f51ec-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="f51ec-115">Zurück zu Pilot Textbuch</span><span class="sxs-lookup"><span data-stu-id="f51ec-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="f51ec-116">*Sie sind hier!*</span><span class="sxs-lookup"><span data-stu-id="f51ec-116">*You are here!*</span></span>  | | |


<span data-ttu-id="f51ec-117">Sie befinden sich derzeit in der Setupphase.</span><span class="sxs-lookup"><span data-stu-id="f51ec-117">You're currently in the set up phase.</span></span> <span data-ttu-id="f51ec-118">Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, und richten Sie die Testumgebung oder Pilotumgebung ein.</span><span class="sxs-lookup"><span data-stu-id="f51ec-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="f51ec-119">Registrieren Sie sich für ein Office 365 oder Azure Active Directory-Abonnement, um einen *. onmicrosoft.com-* Mandanten zu generieren, mit dem Sie sich für Ihre Microsoft 365 E5-Lizenz anmelden können.</span><span class="sxs-lookup"><span data-stu-id="f51ec-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="f51ec-120">Wenn Sie bereits über ein vorhandenes Office 365-oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Test-oder Pilot Mandanten überspringen.</span><span class="sxs-lookup"><span data-stu-id="f51ec-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="f51ec-121">In dieser Phase werden Sie zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="f51ec-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="f51ec-122">Erstellen eines Office 365 E5-Testmandanten</span><span class="sxs-lookup"><span data-stu-id="f51ec-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="f51ec-123">Microsoft 365-Testabonnement aktivieren</span><span class="sxs-lookup"><span data-stu-id="f51ec-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="f51ec-124">Erstellen eines Office 365 E5-Testmandanten</span><span class="sxs-lookup"><span data-stu-id="f51ec-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="f51ec-125">Wenn Sie bereits über ein vorhandenes Office 365-oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Testmandanten überspringen.</span><span class="sxs-lookup"><span data-stu-id="f51ec-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="f51ec-126">Wechseln Sie zum [Office 365 E5-Produkt Portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) , und wählen Sie **﻿Kostenlose Testversion** aus.</span><span class="sxs-lookup"><span data-stu-id="f51ec-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Image of_Office 365 E5 ﻿kostenlose Test Seite](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="f51ec-128">Schließen Sie die Testregistrierung ab, indem Sie Ihre e-Mail-Adresse (persönlich oder Unternehmen) eingeben.</span><span class="sxs-lookup"><span data-stu-id="f51ec-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="f51ec-129">Klicken Sie auf **Konto einrichten**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-129">Click **Set up account**.</span></span>

   ![Setup Seite für Bild of_Office 365 E5-Testregistrierung](../../media/mtp-eval-10.png)

3. <span data-ttu-id="f51ec-131">Geben Sie den Vornamen, den Nachnamen, die geschäftliche Telefonnummer, den Firmennamen, die Unternehmensgröße und das Land oder die Region ein.</span><span class="sxs-lookup"><span data-stu-id="f51ec-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Image of_Office 365 E5-Test Registrierungs Setup-Seite Fragen nach Namen, Telefon-und Firmendetails](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="f51ec-133">Das Land oder die Region, die Sie hier festgelegt haben, bestimmt die Rechenzentrums Region, in der Ihr Office 365 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="f51ec-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="f51ec-134">Wählen Sie Ihre Verifizierungs Präferenz: durch eine Textnachricht oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="f51ec-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="f51ec-135">Klicken Sie auf **Bestätigungs Code senden**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-135">Click **Send Verification Code**.</span></span> 

   ![Image of_Office 365 E5-Test Registrierungs Setup Seite mit der Aufforderung zur Überprüfung bevorzugt](../../media/mtp-eval-12.png)

5. <span data-ttu-id="f51ec-137">Legen Sie den benutzerdefinierten Domänennamen für Ihren Mandanten fest, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Image of_Office 365 E5-Test Registrierungs Setup-Seite, auf der Sie Ihren benutzerdefinierten Domänennamen einrichten können](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="f51ec-139">Richten Sie die erste Identität ein, die ein globaler Administrator für den Mandanten sein wird.</span><span class="sxs-lookup"><span data-stu-id="f51ec-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="f51ec-140">Geben Sie den **Namen** und das **Kennwort ein**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="f51ec-141">Klicken Sie auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-141">Click **Sign up**.</span></span>

   ![Image of_Office 365 E5-Test Registrierungs Setup Seite, auf der Sie Ihre Geschäftsidentität festlegen können](../../media/mtp-eval-14.png)

7. <span data-ttu-id="f51ec-143">Klicken Sie auf **Gehe zu Setup** , um die Office 365 E5-Testmandanten Provision abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="f51ec-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Bild der Office 365 E5-Test Registrierungsseite, die zum Klicken auf die Schaltfläche "Gehe zu Setup" auffordert](../../media/mtp-eval-15.png)

8. <span data-ttu-id="f51ec-145">Verbinden Sie Ihre Unternehmensdomäne mit dem Office 365 Mandanten.</span><span class="sxs-lookup"><span data-stu-id="f51ec-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="f51ec-146">Optional Wählen **Sie Verbinden einer Domäne aus, die Sie bereits besitzen** , und geben Sie Ihren Domänennamen ein.</span><span class="sxs-lookup"><span data-stu-id="f51ec-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="f51ec-147">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-147">Click **Next**.</span></span>

   ![Image of_Office 365 E5-Setup Seite, auf der Sie Ihre Anmeldung und e-Mail personalisieren sollten](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="f51ec-149">Hinzufügen eines txt-oder MX-Eintrags zum Überprüfen des Domänenbesitzes.</span><span class="sxs-lookup"><span data-stu-id="f51ec-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="f51ec-150">Nachdem Sie den txt-oder MX-Eintrag zu Ihrer Domäne hinzugefügt haben, wählen Sie **überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="f51ec-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Image of_Office 365 E5-Setup Seite, auf der Sie einen MX-Eintrag txt hinzufügen sollten, um Ihre Domäne zu überprüfen](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="f51ec-152">Optional Erstellen Sie weitere Benutzerkonten für Ihren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="f51ec-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="f51ec-153">Sie können diesen Schritt überspringen, indem Sie auf **weiter** klicken.</span><span class="sxs-lookup"><span data-stu-id="f51ec-153">You can skip this step by clicking **Next**.</span></span>

    ![Image of_Office 365 E5-Setup Seite, auf der Sie weitere Benutzer hinzufügen können](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="f51ec-155">Optional Laden Sie Office-Apps herunter.</span><span class="sxs-lookup"><span data-stu-id="f51ec-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="f51ec-156">Klicken Sie auf **weiter** , um diesen Schritt zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="f51ec-156">Click **Next** to skip this step.</span></span> 

    ![Image of_Office 365 E5-Seite, auf der Sie Ihre Office-Apps installieren können](../../media/mtp-eval-19.png)

12. <span data-ttu-id="f51ec-158">Optional Migrieren von e-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="f51ec-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="f51ec-159">Sie können diesen Schritt auch wieder überspringen.</span><span class="sxs-lookup"><span data-stu-id="f51ec-159">Again, you can skip this step.</span></span>

    ![Image of_Office 365 E5, in dem Sie festlegen können, ob e-Mail-Nachrichten migriert werden sollen oder nicht](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="f51ec-161">Wählen Sie Onlinedienste aus.</span><span class="sxs-lookup"><span data-stu-id="f51ec-161">Choose online services.</span></span> <span data-ttu-id="f51ec-162">Wählen Sie **Exchange** aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-162">Select **Exchange** and click **Next**.</span></span> 

    ![Image of_Office 365 E5, wo Sie Ihre Onlinedienste auswählen können](../../media/mtp-eval-21.png)

14. <span data-ttu-id="f51ec-164">Fügen Sie Ihrer Domäne MX-, CNAME-und TXT-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="f51ec-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="f51ec-165">Wählen Sie nach Abschluss die Option **überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="f51ec-165">When completed, select **Verify**.</span></span>

    ![Bild of_Office 365 E5 hier können Sie Ihre DNS-Einträge hinzufügen](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="f51ec-167">Herzlichen Glückwunsch, Sie haben die Überstellung Ihres Office 365 Mandanten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="f51ec-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Bestätigungsseite für Bild of_Office 365 E5-Setup Abschluss](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="f51ec-169">Microsoft 365-Testabonnement aktivieren</span><span class="sxs-lookup"><span data-stu-id="f51ec-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="f51ec-170">Wenn Sie sich für eine Testversion registrieren, erhalten Sie 25 Benutzerlizenzen, die für einen Monat verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="f51ec-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="f51ec-171">Weitere Informationen finden Sie unter [Testen oder kaufen eines M365-Abonnements](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) .</span><span class="sxs-lookup"><span data-stu-id="f51ec-171">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="f51ec-172">Klicken Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/)auf **Abrechnung** , und navigieren Sie zu **Dienste kaufen**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="f51ec-173">Wählen Sie **Microsoft 365 E5** aus, und klicken Sie auf **﻿Kostenlose Testversion starten**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Image of_Microsoft 365 E5 Start ﻿kostenlose Test Seite](../../media/mtp-eval-24.png)

3. <span data-ttu-id="f51ec-175">Wählen Sie Ihre Verifizierungs Präferenz: durch eine Textnachricht oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="f51ec-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="f51ec-176">Wenn Sie sich entschieden haben, geben Sie die Telefonnummer ein, wählen Sie **Text mich** oder **rufen Sie mich** je nach Ihrer Auswahl an.</span><span class="sxs-lookup"><span data-stu-id="f51ec-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 Start ﻿kostenlose Test Seite Fragen Sie nach Kontaktdetails zum Senden von Code, um zu beweisen, dass Sie kein Roboter sind](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="f51ec-178">Geben Sie den Verifizierungscode ein, und klicken Sie auf **﻿Kostenlose Testversion starten**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Image of_Microsoft 365 E5 Start ﻿kostenlose Test Seite, auf der Sie den Überprüfungscode ausfüllen können das System, das zum Nachweis gesendet wird, dass Sie kein Roboter sind](../../media/mtp-eval-26.png)

5. <span data-ttu-id="f51ec-180">Klicken Sie auf **jetzt testen** , um Ihre Microsoft 365 E5-Testversion zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="f51ec-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 Startkosten lose Test Seite, auf der Sie die Schaltfläche "jetzt testen" starten sollten](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="f51ec-182">Wechseln Sie zum **Microsoft 365 Admin Center**  >  **Users**  >  **Active Users**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="f51ec-183">Wählen Sie Ihr Benutzerkonto aus, wählen Sie **Produktlizenzen verwalten** aus, und tauschen Sie dann die Lizenz von Office 365 E5 auf **Microsoft 365 E5** aus.</span><span class="sxs-lookup"><span data-stu-id="f51ec-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="f51ec-184">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-184">Click **Save**.</span></span>

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie die Microsoft 365 E5-Lizenz auswählen können](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="f51ec-186">Wählen Sie erneut das globale Administratorkonto aus, und klicken Sie dann auf **Benutzername verwalten**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie Konto auswählen und dann Benutzername verwalten können](../../media/mtp-eval-29.png)

8. <span data-ttu-id="f51ec-188">Optional Ändern Sie die Domäne von *onmicrosoft.com* in Ihre eigene Domäne – je nachdem, was Sie in den vorherigen Schritten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="f51ec-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="f51ec-189">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="f51ec-189">Click **Save changes**.</span></span>

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie die Domäneneinstellung ändern können](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="f51ec-191">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="f51ec-191">Next step</span></span>
|[<span data-ttu-id="f51ec-192">Phase 3: Konfigurieren von & Onboard</span><span class="sxs-lookup"><span data-stu-id="f51ec-192">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="f51ec-193">Konfigurieren Sie jede Microsoft 365 Defender-Säule für Ihre Microsoft 365 Defender Test Lab oder Pilotumgebung und an Bord ihrer Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="f51ec-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
