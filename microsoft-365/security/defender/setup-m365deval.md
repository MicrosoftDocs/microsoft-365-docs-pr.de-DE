---
title: Einrichten ihrer Microsoft 365 Testumgebung oder Pilotumgebung für Defender
description: Access Microsoft 365 Security Center, und richten Sie dann Ihre Microsoft 365 Defender-Testumgebung ein.
keywords: Microsoft 365 Defender-Testeinrichtung, Microsoft 365 defender pilot setup, try Microsoft 365 Defender, Microsoft 365 Defender evaluation lab setup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae81f6be0a83d5d0141f0f0c8c89f8f2207cc56c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935425"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="3bf7d-104">Einrichten ihrer Microsoft 365 Defender-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="3bf7d-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3bf7d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3bf7d-105">**Applies to:**</span></span>
- <span data-ttu-id="3bf7d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3bf7d-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="3bf7d-107">Das Erstellen Microsoft 365 einer Defender-Testumgebung oder Pilotumgebung und deren Bereitstellung ist ein drei phasenweiser Prozess:</span><span class="sxs-lookup"><span data-stu-id="3bf7d-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="3bf7d-108">[![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="3bf7d-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="3bf7d-109">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="3bf7d-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="3bf7d-111">Phase 2: Einrichten</span><span class="sxs-lookup"><span data-stu-id="3bf7d-111">Phase 2: Set up</span></span> |<span data-ttu-id="3bf7d-112">[![Phase 3: Onboarding](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="3bf7d-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span></span><br/>[<span data-ttu-id="3bf7d-113">Phase 3: Onboarding</span><span class="sxs-lookup"><span data-stu-id="3bf7d-113">Phase 3: Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="3bf7d-114">[![Zurück zum Pilotprojekt](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="3bf7d-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="3bf7d-115">Zurück zum Testspielbuch</span><span class="sxs-lookup"><span data-stu-id="3bf7d-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="3bf7d-116">*Sie sind hier!*</span><span class="sxs-lookup"><span data-stu-id="3bf7d-116">*You are here!*</span></span>  | | |


<span data-ttu-id="3bf7d-117">Sie sind derzeit in der Einrichtungsphase.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-117">You're currently in the set up phase.</span></span> <span data-ttu-id="3bf7d-118">Ergreifen Sie die ersten Schritte, um auf Microsoft 365 Security Center zu zugreifen, und richten Sie dann Ihre Testumgebung oder Pilotumgebung ein.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="3bf7d-119">Registrieren Sie sich für ein Office 365- oder Azure Active Directory-Abonnement, um einen *.onmicrosoft.com-Mandanten* zu generieren, mit dem Sie sich für Ihre Microsoft 365 E5 registrieren können.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="3bf7d-120">Wenn Sie bereits über ein vorhandenes Office 365 oder Azure Active Directory verfügen, können Sie die Schritte Office 365 E5-Test- oder Pilot-Mandantenerstellung überspringen.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="3bf7d-121">In dieser Phase werden Sie geführt zu:</span><span class="sxs-lookup"><span data-stu-id="3bf7d-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="3bf7d-122">Erstellen eines Office 365 E5-Test-Mandanten</span><span class="sxs-lookup"><span data-stu-id="3bf7d-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="3bf7d-123">Aktivieren Microsoft 365 Testabonnements</span><span class="sxs-lookup"><span data-stu-id="3bf7d-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="3bf7d-124">Erstellen eines Office 365 E5-Test-Mandanten</span><span class="sxs-lookup"><span data-stu-id="3bf7d-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="3bf7d-125">Wenn Sie bereits über ein vorhandenes Office 365 oder Azure Active Directory verfügen, können Sie die Schritte zum Erstellen Office 365 E5-Test-Mandanten überspringen.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="3bf7d-126">Wechseln Sie zum [Office 365 E5-Produktportal,](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) und wählen Sie **Kostenlose Testversion aus.**</span><span class="sxs-lookup"><span data-stu-id="3bf7d-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Kostenlose of_Office 365 E5](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="3bf7d-128">Schließen Sie die Testregistrierung ab, indem Sie Ihre E-Mail-Adresse (privat oder unternehmensanmeldend) eingeben.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="3bf7d-129">Klicken **Sie auf Konto einrichten**.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-129">Click **Set up account**.</span></span>

   ![Setupseite of_Office 365 E5-Testversion](../../media/mtp-eval-10.png)

3. <span data-ttu-id="3bf7d-131">Geben Sie Ihren Vornamen, Nachnamen, Ihre Geschäftliche Telefonnummer, den Firmennamen, die Unternehmensgröße und das Land oder die Region ein.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite, auf der nach Namen, Telefon und Firmendetails gefragt wird](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="3bf7d-133">Das land oder die Region, das Sie hier festgelegt haben, bestimmt die Rechenzentrumsregion, Office 365 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="3bf7d-134">Wählen Sie Ihre Überprüfungseinstellung aus: über eine Textnachricht oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="3bf7d-135">Klicken **Sie auf Überprüfungscode senden**.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-135">Click **Send Verification Code**.</span></span> 

   ![Abbildung of_Office 365 E5-Testregistrierungseinrichtungsseite mit der Bitte um Überprüfungseinstellung](../../media/mtp-eval-12.png)

5. <span data-ttu-id="3bf7d-137">Legen Sie den benutzerdefinierten Domänennamen für Ihren Mandanten ein, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite, auf der Sie Ihren benutzerdefinierten Domänennamen einrichten können](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="3bf7d-139">Richten Sie die erste Identität ein, die ein globaler Administrator für den Mandanten ist.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="3bf7d-140">Geben Sie **Name und** **Kennwort ein.**</span><span class="sxs-lookup"><span data-stu-id="3bf7d-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="3bf7d-141">Klicken Sie auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-141">Click **Sign up**.</span></span>

   ![Abbildung of_Office 365 E5-Testregistrierungseinrichtungsseite, auf der Sie Ihre Geschäftsidentität festlegen können](../../media/mtp-eval-14.png)

7. <span data-ttu-id="3bf7d-143">Klicken **Sie auf Zu Setup** wechseln, um Office 365 E5-Test-Mandantenbereitstellung abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Abbildung der Office 365 E5-Testregistrierungsseite, auf der sie aufgefordert wird, auf Setup gehen zu klicken](../../media/mtp-eval-15.png)

8. <span data-ttu-id="3bf7d-145">Verbinden Ihrer Unternehmensdomäne an den Office 365 mandanten.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="3bf7d-146">[Optional] Wählen **Verbinden eine Domäne aus, die Sie bereits besitzen,** und geben Sie Ihren Domänennamen ein.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="3bf7d-147">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-147">Click **Next**.</span></span>

   ![Bild of_Office 365 E5-Setupseite, auf der Sie Ihre Anmeldung und E-Mail personalisieren sollten](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="3bf7d-149">Fügen Sie einen TXT- oder MX-Eintrag hinzu, um den Domänenbesitz zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="3bf7d-150">Nachdem Sie den TXT- oder MX-Eintrag zu Ihrer Domäne hinzugefügt haben, wählen Sie **Überprüfen aus.**</span><span class="sxs-lookup"><span data-stu-id="3bf7d-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Bild of_Office 365 E5-Setupseite, auf der Sie einen TXT-MX-Eintrag hinzufügen sollten, um Ihre Domäne zu überprüfen](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="3bf7d-152">[Optional] Erstellen Sie weitere Benutzerkonten für Ihren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="3bf7d-153">Sie können diesen Schritt überspringen, indem Sie auf **Weiter klicken.**</span><span class="sxs-lookup"><span data-stu-id="3bf7d-153">You can skip this step by clicking **Next**.</span></span>

    ![Image of_Office 365 E5-Setupseite, auf der Sie weitere Benutzer hinzufügen können](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="3bf7d-155">[Optional] Laden Office Apps herunter.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="3bf7d-156">Klicken Sie **auf Weiter,** um diesen Schritt zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-156">Click **Next** to skip this step.</span></span> 

    ![Image of_Office 365 E5-Seite, auf der Sie Ihre Office installieren können](../../media/mtp-eval-19.png)

12. <span data-ttu-id="3bf7d-158">[Optional] Migrieren von E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="3bf7d-159">Auch hier können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-159">Again, you can skip this step.</span></span>

    ![Image of_Office 365 E5, in dem Sie festlegen können, ob E-Mail-Nachrichten migriert werden sollen oder nicht](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="3bf7d-161">Wählen Sie Onlinedienste aus.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-161">Choose online services.</span></span> <span data-ttu-id="3bf7d-162">Wählen **Exchange** aus, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-162">Select **Exchange** and click **Next**.</span></span> 

    ![Bild of_Office 365 E5, in dem Sie Ihre Onlinedienste auswählen können](../../media/mtp-eval-21.png)

14. <span data-ttu-id="3bf7d-164">Fügen Sie Ihrer Domäne MX-, CNAME- und #A0 hinzu.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="3bf7d-165">Wenn Sie abgeschlossen sind, wählen Sie **Überprüfen aus.**</span><span class="sxs-lookup"><span data-stu-id="3bf7d-165">When completed, select **Verify**.</span></span>

    ![Bild of_Office 365 E5 hier können Sie Ihre DNS-Einträge hinzufügen](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="3bf7d-167">Herzlichen Glückwunsch, Sie haben die Bereitstellung Ihres mandanten Office 365 abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Bestätigungsseite of_Office 365 E5-Setupabschluss](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="3bf7d-169">Aktivieren Microsoft 365 Testabonnements</span><span class="sxs-lookup"><span data-stu-id="3bf7d-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="3bf7d-170">Wenn Sie sich für eine Testversion anmelden, können Sie 25 Benutzerlizenzen für einen Monat verwenden.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="3bf7d-171">Weitere [Informationen finden Sie unter Try or Buy an M365 subscription.](../../commerce/try-or-buy-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="3bf7d-171">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="3bf7d-172">Klicken [Microsoft 365 Admin Center](https://admin.microsoft.com/)auf **Abrechnung,** und navigieren Sie dann zu **Dienste kaufen**.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="3bf7d-173">Wählen **Microsoft 365 E5** aus, und klicken Sie **auf Kostenlose Testversion starten.**</span><span class="sxs-lookup"><span data-stu-id="3bf7d-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Image of_Microsoft 365 E5 Kostenlose Testversion starten](../../media/mtp-eval-24.png)

3. <span data-ttu-id="3bf7d-175">Wählen Sie Ihre Überprüfungseinstellung aus: über eine Textnachricht oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="3bf7d-176">Nachdem Sie sich entschieden haben, geben Sie die Telefonnummer ein, wählen Sie **Text me** oder Rufen Sie **mich** je nach Auswahl auf.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 Kostenlose Testseite starten und um Kontaktdetails bitten, um Code zu senden, um zu beweisen, dass Sie kein Roboter sind](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="3bf7d-178">Geben Sie den Überprüfungscode ein, und klicken **Sie auf Kostenlose Testversion starten.**</span><span class="sxs-lookup"><span data-stu-id="3bf7d-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Abbildung of_Microsoft 365 E5 Kostenlose Testseite starten, auf der Sie den vom System gesendeten Überprüfungscode ausfüllen können, um zu bestätigen, dass Sie kein Roboter sind](../../media/mtp-eval-26.png)

5. <span data-ttu-id="3bf7d-180">Klicken **Sie auf Jetzt** testen, um ihre Microsoft 365 E5 bestätigen.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 Kostenlose Testseite starten, auf der Sie die Schaltfläche Jetzt testen zum Starten sehen sollten](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="3bf7d-182">Wechseln Sie zum **Microsoft 365 Admin Center**  >  **Users**  >  **Active users**.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="3bf7d-183">Wählen Sie Ihr Benutzerkonto aus, wählen Sie **Produktlizenzen verwalten** aus, und tauschen Sie dann die Lizenz von Office 365 E5 in **Microsoft 365 E5**.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="3bf7d-184">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-184">Click **Save**.</span></span>

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie eine Microsoft 365 E5 auswählen können](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="3bf7d-186">Wählen Sie das globale Administratorkonto erneut aus, und klicken Sie dann **auf Benutzername verwalten.**</span><span class="sxs-lookup"><span data-stu-id="3bf7d-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Bild of_Microsoft 365 Admin Center-Seite, auf der Sie Konto auswählen und dann Benutzernamen verwalten auswählen können](../../media/mtp-eval-29.png)

8. <span data-ttu-id="3bf7d-188">[Optional] Ändern Sie die Domäne *von onmicrosoft.com* in Ihre eigene Domäne , je nachdem, was Sie bei den vorherigen Schritten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="3bf7d-189">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-189">Click **Save changes**.</span></span>

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie Ihre Domäneneinstellung ändern können](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="3bf7d-191">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="3bf7d-191">Next step</span></span>
|[<span data-ttu-id="3bf7d-192">Phase 3: Konfigurieren & Onboard</span><span class="sxs-lookup"><span data-stu-id="3bf7d-192">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="3bf7d-193">Konfigurieren Sie Microsoft 365 Defender-Säule für Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung und integrieren Sie Ihre Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="3bf7d-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
