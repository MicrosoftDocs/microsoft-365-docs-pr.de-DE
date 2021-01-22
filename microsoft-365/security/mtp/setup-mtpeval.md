---
title: Einrichten ihrer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung
description: Greifen Sie auf Das Microsoft 365 Security Center zu, und richten Sie dann Ihre Microsoft 365 Defender-Testumgebung ein.
keywords: Einrichtung der Microsoft Threat Protection-Testversion, Microsoft Threat Protection-Pilotinstallation, Testen der Microsoft Threat Protection- und Microsoft Threat Protection-Evaluierungsumgebung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: 835adc5c2bf9fd1c9a14c2d53b17a032a89a6240
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49932982"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="58d69-104">Einrichten ihrer Microsoft 365 Defender-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="58d69-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="58d69-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="58d69-105">**Applies to:**</span></span>
- <span data-ttu-id="58d69-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="58d69-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="58d69-107">Das Erstellen einer Microsoft 365 Defender-Testumgebung oder -Pilotumgebung und deren Bereitstellung besteht aus drei Phasen:</span><span class="sxs-lookup"><span data-stu-id="58d69-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="58d69-108">[![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="58d69-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="58d69-109">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="58d69-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="58d69-111">Phase 2: Einrichten</span><span class="sxs-lookup"><span data-stu-id="58d69-111">Phase 2: Set up</span></span> |<span data-ttu-id="58d69-112">[![Phase 3: Onboarding](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="58d69-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span></span><br/>[<span data-ttu-id="58d69-113">Phase 3: Onboarding</span><span class="sxs-lookup"><span data-stu-id="58d69-113">Phase 3: Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="58d69-114">[![Zurück zum Pilotprojekt](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="58d69-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="58d69-115">Zurück zum Pilot-Playbook</span><span class="sxs-lookup"><span data-stu-id="58d69-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="58d69-116">*Sie sind hier!*</span><span class="sxs-lookup"><span data-stu-id="58d69-116">*You are here!*</span></span>  | | |


<span data-ttu-id="58d69-117">Sie sind derzeit in der Einrichtungsphase.</span><span class="sxs-lookup"><span data-stu-id="58d69-117">You're currently in the set up phase.</span></span> <span data-ttu-id="58d69-118">Nehmen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center vor, und richten Sie dann Ihre Testumgebung oder Pilotumgebung ein.</span><span class="sxs-lookup"><span data-stu-id="58d69-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="58d69-119">Registrieren Sie sich für ein Office 365- oder Azure Active Directory-Abonnement, um einen *.onmicrosoft.com-Mandanten* zu generieren, mit dem Sie sich für Ihre Microsoft 365 E5-Lizenz registrieren können.</span><span class="sxs-lookup"><span data-stu-id="58d69-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="58d69-120">Wenn Sie bereits über ein Vorhandenes Office 365- oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Testversionen oder Pilot-Mandanten überspringen.</span><span class="sxs-lookup"><span data-stu-id="58d69-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="58d69-121">In dieser Phase werden Sie geführt zu:</span><span class="sxs-lookup"><span data-stu-id="58d69-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="58d69-122">Erstellen eines Office 365 E5-Test-Mandanten</span><span class="sxs-lookup"><span data-stu-id="58d69-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="58d69-123">Aktivieren des Microsoft 365-Testabonnements</span><span class="sxs-lookup"><span data-stu-id="58d69-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="58d69-124">Erstellen eines Office 365 E5-Test-Mandanten</span><span class="sxs-lookup"><span data-stu-id="58d69-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="58d69-125">Wenn Sie bereits über ein vorhandenes Office 365- oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen des Office 365 E5-Test-Mandanten überspringen.</span><span class="sxs-lookup"><span data-stu-id="58d69-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="58d69-126">Wechseln Sie zum [Office 365 E5-Produktportal,](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) und wählen Sie kostenlose **Testversion aus.**</span><span class="sxs-lookup"><span data-stu-id="58d69-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Abbildung of_Office 365 E5 ( kostenlose Testversion)](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="58d69-128">Schließen Sie die Testregistrierung ab, indem Sie Ihre E-Mail-Adresse (persönlich oder unternehmensanmeldend) eingeben.</span><span class="sxs-lookup"><span data-stu-id="58d69-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="58d69-129">Klicken **Sie auf Konto einrichten**.</span><span class="sxs-lookup"><span data-stu-id="58d69-129">Click **Set up account**.</span></span>

   ![Abbildung of_Office 365 E5-Testregistrierungsseite](../../media/mtp-eval-10.png)

3. <span data-ttu-id="58d69-131">Geben Sie Ihren Vornamen, Nachnamen, Ihre Geschäftliche Telefonnummer, den Firmennamen, die Unternehmensgröße sowie das Land oder die Region ein.</span><span class="sxs-lookup"><span data-stu-id="58d69-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Abbildung of_Office 365 E5-Testregistrierungsseite, auf der Nach Namen, Telefon und Unternehmensdetails gefragt werden](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="58d69-133">Das Land oder die Region, das Sie hier festgelegt haben, bestimmt die Rechenzentrumsregion, in der Office 365 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="58d69-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="58d69-134">Wählen Sie Ihre Überprüfungseinstellung aus: über eine Textnachricht oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="58d69-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="58d69-135">Klicken **Sie auf "Überprüfungscode senden".**</span><span class="sxs-lookup"><span data-stu-id="58d69-135">Click **Send Verification Code**.</span></span> 

   ![Abbildung of_Office 365 E5-Testregistrierungsseite, auf der Die Überprüfungseinstellung angezeigt wird](../../media/mtp-eval-12.png)

5. <span data-ttu-id="58d69-137">Legen Sie den benutzerdefinierten Domänennamen für Ihren Mandanten, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="58d69-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Abbildung of_Office 365 E5-Testregistrierungsseite, auf der Sie Ihren benutzerdefinierten Domänennamen einrichten können](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="58d69-139">Richten Sie die erste Identität ein, die ein globaler Administrator für den Mandanten ist.</span><span class="sxs-lookup"><span data-stu-id="58d69-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="58d69-140">Geben Sie **"Name"** und **"Password" ein.**</span><span class="sxs-lookup"><span data-stu-id="58d69-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="58d69-141">Klicken Sie auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="58d69-141">Click **Sign up**.</span></span>

   ![Abbildung of_Office 365 E5-Testregistrierungsseite, auf der Sie Ihre Unternehmensidentität festlegen können](../../media/mtp-eval-14.png)

7. <span data-ttu-id="58d69-143">Klicken **Sie auf "Setup",** um die Bereitstellung des Office 365 E5-Test-Mandanten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="58d69-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Abbildung der Office 365 E5-Testregistrierungsseite, auf der Sie aufgefordert werden, auf die Schaltfläche "Setup wechseln" zu klicken](../../media/mtp-eval-15.png)

8. <span data-ttu-id="58d69-145">Verbinden Sie Ihre Unternehmensdomäne mit dem Office 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="58d69-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="58d69-146">[Optional] Wählen **Sie "Verbinden" aus, die Sie bereits besitzen,** und geben Sie Ihren Domänennamen ein.</span><span class="sxs-lookup"><span data-stu-id="58d69-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="58d69-147">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="58d69-147">Click **Next**.</span></span>

   ![Abbildung of_Office 365 E5-Setupseite, auf der Sie Ihre Anmeldung und E-Mail personalisieren sollten](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="58d69-149">Fügen Sie einen TXT- oder MX-Eintrag hinzu, um den Domänenbesitz zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="58d69-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="58d69-150">Nachdem Sie Den TXT- oder MX-Eintrag zu Ihrer Domäne hinzugefügt haben, wählen Sie **"Überprüfen" aus.**</span><span class="sxs-lookup"><span data-stu-id="58d69-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Abbildung of_Office 365 E5-Setupseite, auf der Sie einen TXT-mx-Eintrag hinzufügen sollten, um Ihre Domäne zu überprüfen](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="58d69-152">[Optional] Erstellen Sie weitere Benutzerkonten für Ihren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="58d69-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="58d69-153">Sie können diesen Schritt überspringen, indem Sie auf **"Weiter" klicken.**</span><span class="sxs-lookup"><span data-stu-id="58d69-153">You can skip this step by clicking **Next**.</span></span>

    ![Abbildung of_Office 365 E5-Setupseite, auf der Sie weitere Benutzer hinzufügen können](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="58d69-155">[Optional] Laden Sie Die Office-Apps herunter.</span><span class="sxs-lookup"><span data-stu-id="58d69-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="58d69-156">Klicken Sie **auf "Weiter",** um diesen Schritt zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="58d69-156">Click **Next** to skip this step.</span></span> 

    ![Bild of_Office 365 E5-Seite, auf der Sie Ihre Office-Apps installieren können](../../media/mtp-eval-19.png)

12. <span data-ttu-id="58d69-158">[Optional] Migrieren von E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="58d69-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="58d69-159">Auch hier können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="58d69-159">Again, you can skip this step.</span></span>

    ![Abbildung of_Office 365 E5, in der Sie festlegen können, ob E-Mail-Nachrichten migriert werden sollen oder nicht](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="58d69-161">Wählen Sie Onlinedienste aus.</span><span class="sxs-lookup"><span data-stu-id="58d69-161">Choose online services.</span></span> <span data-ttu-id="58d69-162">Wählen Sie **Exchange** aus, und klicken Sie auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="58d69-162">Select **Exchange** and click **Next**.</span></span> 

    ![Abbildung of_Office 365 E5, in der Sie Ihre Onlinedienste auswählen können](../../media/mtp-eval-21.png)

14. <span data-ttu-id="58d69-164">Fügen Sie Ihrer Domäne MX-, CNAME- und #A0 hinzu.</span><span class="sxs-lookup"><span data-stu-id="58d69-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="58d69-165">Wenn Sie fertig sind, wählen Sie **"Überprüfen"** aus.</span><span class="sxs-lookup"><span data-stu-id="58d69-165">When completed, select **Verify**.</span></span>

    ![Abbildung of_Office 365 E5 hier können Sie Ihre DNS-Einträge hinzufügen](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="58d69-167">Herzlichen Glückwunsch, Sie haben die Bereitstellung Ihres Office 365-Mandanten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="58d69-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Abbildung of_Office 365 E5-Einrichtungsbestätigungsseite](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="58d69-169">Aktivieren des Microsoft 365-Testabonnements</span><span class="sxs-lookup"><span data-stu-id="58d69-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="58d69-170">Wenn Sie sich für eine Testversion anmelden, erhalten Sie 25 Benutzerlizenzen für einen Monat.</span><span class="sxs-lookup"><span data-stu-id="58d69-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="58d69-171">Weitere [Informationen finden Sie unter "Testen oder Kaufen eines M365-Abonnements".](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1)</span><span class="sxs-lookup"><span data-stu-id="58d69-171">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="58d69-172">Klicken [Sie im Microsoft 365 Admin Center](https://admin.microsoft.com/)auf **"Abrechnung",** und navigieren Sie dann zu **"Dienste kaufen".**</span><span class="sxs-lookup"><span data-stu-id="58d69-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="58d69-173">Wählen **Sie Microsoft 365 E5** aus, und klicken **Sie auf "Kostenlose Testversion starten".**</span><span class="sxs-lookup"><span data-stu-id="58d69-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Abbildung of_Microsoft 365 E5 Kostenlose Testversion](../../media/mtp-eval-24.png)

3. <span data-ttu-id="58d69-175">Wählen Sie Ihre Überprüfungseinstellung aus: über eine Textnachricht oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="58d69-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="58d69-176">Nachdem Sie sich entschieden haben, geben Sie die Telefonnummer ein, wählen Sie **"Text me"** oder **"Call me"** aus, je nach Ihrer Auswahl.</span><span class="sxs-lookup"><span data-stu-id="58d69-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Abbildung of_Microsoft 365 E5 - Kostenlose Testseite, auf der Sie nach Kontaktdetails gefragt werden, um Code zu senden, um nachzuweisen, dass Sie kein Robot sind](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="58d69-178">Geben Sie den Überprüfungscode ein, und klicken **Sie auf "Kostenlose Testversion starten".**</span><span class="sxs-lookup"><span data-stu-id="58d69-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Abbildung of_Microsoft 365 E5 - Kostenlose Testseite, auf der Sie den vom System gesendeten Überprüfungscode ausfüllen können, um zu bestätigen, dass Sie kein Robot sind](../../media/mtp-eval-26.png)

5. <span data-ttu-id="58d69-180">Klicken **Sie auf "Jetzt testen",** um Ihre Microsoft 365 E5-Testversion zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="58d69-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Abbildung of_Microsoft 365 E5 Kostenlose Testversionsseite, auf der Sie die Schaltfläche "Jetzt testen" zum Starten probieren sollten](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="58d69-182">Wechseln Sie zu den aktiven Benutzern im **Microsoft 365 Admin**  >    >  Center.</span><span class="sxs-lookup"><span data-stu-id="58d69-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="58d69-183">Wählen Sie Ihr Benutzerkonto aus, **wählen** Sie "Produktlizenzen verwalten" aus, und tauschen Sie dann die Lizenz von Office 365 E5 zu **Microsoft 365 E5 aus.**</span><span class="sxs-lookup"><span data-stu-id="58d69-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="58d69-184">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="58d69-184">Click **Save**.</span></span>

   ![Abbildung of_Microsoft 365 Admin Center-Seite, auf der Sie die Microsoft 365 E5-Lizenz auswählen können](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="58d69-186">Wählen Sie das globale Administratorkonto erneut aus, und klicken Sie dann **auf "Benutzername verwalten".**</span><span class="sxs-lookup"><span data-stu-id="58d69-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Abbildung of_Microsoft 365 Admin Center- Seite, auf der Sie "Konto" und dann "Benutzernamen verwalten" auswählen können](../../media/mtp-eval-29.png)

8. <span data-ttu-id="58d69-188">[Optional] Ändern Sie die Domäne *von onmicrosoft.com* in Ihre eigene Domäne – je nachdem, was Sie in den vorherigen Schritten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="58d69-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="58d69-189">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="58d69-189">Click **Save changes**.</span></span>

   ![Abbildung of_Microsoft 365 Admin Center- Seite, auf der Sie Ihre Domäneneinstellung ändern können](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="58d69-191">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="58d69-191">Next step</span></span>
|[<span data-ttu-id="58d69-192">Phase 3: Konfigurieren & Onboarding</span><span class="sxs-lookup"><span data-stu-id="58d69-192">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="58d69-193">Konfigurieren Sie jede Microsoft 365 Defender-Säulen für Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung, und integrieren Sie Ihre Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="58d69-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
