---
title: Einrichten ihrer Microsoft 365 Defender Testumgebung oder Pilotumgebung
description: Greifen Sie auf Microsoft 365 Security Center zu, und richten Sie dann Ihre Microsoft 365 Defender Testumgebung ein.
keywords: Microsoft 365 Defender Testsetup, Microsoft 365 Defender Piloteinrichtung, testen Sie Microsoft 365 Defender, Microsoft 365 Defender Testumgebungssetup
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454733"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a><span data-ttu-id="51d41-104">Einrichten der Microsoft 365 Defender Testversion in einer Testumgebung</span><span class="sxs-lookup"><span data-stu-id="51d41-104">Set up your Microsoft 365 Defender trial in a lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="51d41-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="51d41-105">**Applies to:**</span></span>
- <span data-ttu-id="51d41-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="51d41-106">Microsoft 365 Defender</span></span> 

<span data-ttu-id="51d41-107">In diesem Thema erfahren Sie, wie Sie eine dedizierte Lab-Umgebung einrichten.</span><span class="sxs-lookup"><span data-stu-id="51d41-107">This topic guides you to set up a dedicated lab environment.</span></span> <span data-ttu-id="51d41-108">Informationen zum Einrichten einer Testversion in der Produktion finden Sie im neuen Leitfaden ["Auswerten und Pilot Microsoft 365 Defender".](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="51d41-108">For information on setting up a trial in production, see the new [Evaluate and pilot Microsoft 365 Defender](eval-overview.md) guide.</span></span> 

## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="51d41-109">Erstellen eines Office 365 E5 Testmandanten</span><span class="sxs-lookup"><span data-stu-id="51d41-109">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="51d41-110">Wenn Sie bereits über ein vorhandenes Office 365- oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen Office 365 E5 Testmandanten überspringen.</span><span class="sxs-lookup"><span data-stu-id="51d41-110">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="51d41-111">Wechseln Sie zum [Office 365 E5 Produktportal,](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) und wählen Sie **"Kostenlose Testversion"** aus.</span><span class="sxs-lookup"><span data-stu-id="51d41-111">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Abbildung of_Office 365 E5–Testversionsseite](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="51d41-113">Schließen Sie die Testregistrierung ab, indem Sie Ihre E-Mail-Adresse (persönlich oder Unternehmensadresse) eingeben.</span><span class="sxs-lookup"><span data-stu-id="51d41-113">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="51d41-114">Klicken Sie auf **Konto einrichten.**</span><span class="sxs-lookup"><span data-stu-id="51d41-114">Click **Set up account**.</span></span>

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite](../../media/mtp-eval-10.png)

3. <span data-ttu-id="51d41-116">Geben Sie Ihren Vornamen, Nachnamen, Ihre Geschäftliche Telefonnummer, Ihren Firmennamen, Ihre Unternehmensgröße und Ihr Land oder Ihre Region ein.</span><span class="sxs-lookup"><span data-stu-id="51d41-116">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite, auf der Nachnamen, Telefon- und Unternehmensdetails gefragt werden](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="51d41-118">Das Land oder die Region, das/die Sie hier festlegen, bestimmt die Rechenzentrumsregion, in der Ihre Office 365 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="51d41-118">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="51d41-119">Wählen Sie Ihre Überprüfungseinstellung aus: über eine SMS oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="51d41-119">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="51d41-120">Klicken Sie auf **"Überprüfungscode senden".**</span><span class="sxs-lookup"><span data-stu-id="51d41-120">Click **Send Verification Code**.</span></span> 

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite mit Aufforderung zur Überprüfung](../../media/mtp-eval-12.png)

5. <span data-ttu-id="51d41-122">Legen Sie den benutzerdefinierten Domänennamen für Ihren Mandanten fest, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="51d41-122">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite, auf der Sie Ihren benutzerdefinierten Domänennamen einrichten können](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="51d41-124">Richten Sie die erste Identität ein, die ein globaler Administrator für den Mandanten ist.</span><span class="sxs-lookup"><span data-stu-id="51d41-124">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="51d41-125">Geben Sie **Name** und **Kennwort ein.**</span><span class="sxs-lookup"><span data-stu-id="51d41-125">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="51d41-126">Klicken Sie auf **Registrieren**.</span><span class="sxs-lookup"><span data-stu-id="51d41-126">Click **Sign up**.</span></span>

   ![Abbildung of_Office 365 E5-Testregistrierungs-Setupseite, auf der Sie Ihre Unternehmensidentität festlegen können](../../media/mtp-eval-14.png)

7. <span data-ttu-id="51d41-128">Klicken Sie auf **"Zum Setup wechseln",** um die Bereitstellung der Office 365 E5 Testmandanten abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="51d41-128">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Abbildung der Setupseite für Office 365 E5 Testversion, auf der sie aufgefordert wird, auf die Schaltfläche "Setup wechseln" zu klicken](../../media/mtp-eval-15.png)

8. <span data-ttu-id="51d41-130">Verbinden Sie Ihre Unternehmensdomäne an den Office 365 Mandanten weiter.</span><span class="sxs-lookup"><span data-stu-id="51d41-130">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="51d41-131">[Optional] Wählen Sie **Verbinden eine Domäne aus, die Sie bereits besitzen,** und geben Sie Ihren Domänennamen ein.</span><span class="sxs-lookup"><span data-stu-id="51d41-131">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="51d41-132">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="51d41-132">Click **Next**.</span></span>

   ![Abbildung of_Office 365 E5-Setupseite, auf der Sie Ihre Anmeldung und E-Mail personalisieren sollten](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="51d41-134">Fügen Sie einen TXT- oder MX-Eintrag hinzu, um den Domänenbesitz zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="51d41-134">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="51d41-135">Nachdem Sie ihrer Domäne den TXT- oder MX-Eintrag hinzugefügt haben, wählen Sie **"Überprüfen"** aus.</span><span class="sxs-lookup"><span data-stu-id="51d41-135">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Abbildung of_Office 365 E5-Setupseite, auf der Sie eine TXT mit MX-Eintrag hinzufügen sollten, um Ihre Domäne zu überprüfen](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="51d41-137">[Optional] Erstellen Sie weitere Benutzerkonten für Ihren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="51d41-137">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="51d41-138">Sie können diesen Schritt überspringen, indem Sie auf **"Weiter"** klicken.</span><span class="sxs-lookup"><span data-stu-id="51d41-138">You can skip this step by clicking **Next**.</span></span>

    ![Abbildung of_Office 365 E5-Setupseite, auf der Sie weitere Benutzer hinzufügen können](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="51d41-140">[Optional] Laden Sie Office Apps herunter.</span><span class="sxs-lookup"><span data-stu-id="51d41-140">[Optional] Download Office apps.</span></span> <span data-ttu-id="51d41-141">Klicken Sie auf **"Weiter",** um diesen Schritt zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="51d41-141">Click **Next** to skip this step.</span></span> 

    ![Abbildung of_Office 365 E5-Seite, auf der Sie Ihre Office-Apps installieren können](../../media/mtp-eval-19.png)

12. <span data-ttu-id="51d41-143">[Optional] Migrieren von E-Mail-Nachrichten.</span><span class="sxs-lookup"><span data-stu-id="51d41-143">[Optional] Migrate email messages.</span></span> <span data-ttu-id="51d41-144">Auch hier können Sie diesen Schritt überspringen.</span><span class="sxs-lookup"><span data-stu-id="51d41-144">Again, you can skip this step.</span></span>

    ![Abbildung of_Office 365 E5, in dem Sie festlegen können, ob E-Mail-Nachrichten migriert werden sollen oder nicht](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="51d41-146">Wählen Sie Onlinedienste aus.</span><span class="sxs-lookup"><span data-stu-id="51d41-146">Choose online services.</span></span> <span data-ttu-id="51d41-147">Wählen Sie **Exchange** aus, und klicken Sie auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="51d41-147">Select **Exchange** and click **Next**.</span></span> 

    ![Abbildung of_Office 365 E5, in dem Sie Ihre Onlinedienste auswählen können](../../media/mtp-eval-21.png)

14. <span data-ttu-id="51d41-149">Fügen Sie IHRER Domäne MX-, CNAME- und TXT-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="51d41-149">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="51d41-150">Wählen Sie nach Abschluss des Vorgangs **"Überprüfen"** aus.</span><span class="sxs-lookup"><span data-stu-id="51d41-150">When completed, select **Verify**.</span></span>

    ![Abbildung of_Office 365 E5 hier können Sie Ihre DNS-Einträge hinzufügen](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="51d41-152">Herzlichen Glückwunsch, Sie haben die Bereitstellung Ihres Office 365 Mandanten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="51d41-152">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Abbildung of_Office Seite zur Bestätigung des Abschlusses des Setups für 365 E5](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="51d41-154">Aktivieren Microsoft 365 Testabonnements</span><span class="sxs-lookup"><span data-stu-id="51d41-154">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="51d41-155">Wenn Sie sich für eine Testversion registrieren, erhalten Sie 25 Benutzerlizenzen, die Sie für einen Monat verwenden können.</span><span class="sxs-lookup"><span data-stu-id="51d41-155">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="51d41-156">Weitere Informationen finden Sie unter ["Testen oder Kaufen eines M365-Abonnements".](../../commerce/try-or-buy-microsoft-365.md)</span><span class="sxs-lookup"><span data-stu-id="51d41-156">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="51d41-157">Klicken Sie [im Microsoft 365 Admin Center](https://admin.microsoft.com/)auf **"Abrechnung",** und navigieren Sie dann zu **"Dienste kaufen".**</span><span class="sxs-lookup"><span data-stu-id="51d41-157">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="51d41-158">Wählen Sie **Microsoft 365 E5** aus, und klicken Sie auf **"Kostenlose Testversion starten".**</span><span class="sxs-lookup"><span data-stu-id="51d41-158">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Abbildung of_Microsoft 365 E5 – Startseite der kostenlosen Testversion](../../media/mtp-eval-24.png)

3. <span data-ttu-id="51d41-160">Wählen Sie Ihre Überprüfungseinstellung aus: über eine SMS oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="51d41-160">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="51d41-161">Sobald Sie sich entschieden haben, geben Sie die Telefonnummer ein, wählen Sie **"Mich anrufen"** oder **"Anrufen"** aus, je nach Auswahl.</span><span class="sxs-lookup"><span data-stu-id="51d41-161">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Abbildung of_Microsoft 365 E5–Startseite für die kostenlose Testversion, auf der Sie nach Kontaktdetails gefragt werden, um Code zu senden, um nachzuweisen, dass Sie kein Roboter sind](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="51d41-163">Geben Sie den Überprüfungscode ein, und klicken Sie auf **"Kostenlose Testversion starten".**</span><span class="sxs-lookup"><span data-stu-id="51d41-163">Enter the verification code and click **Start your free trial**.</span></span>

   ![Abbildung of_Microsoft 365 E5–Startseite für die kostenlose Testversion, auf der Sie den vom System gesendeten Überprüfungscode ausfüllen können, um nachzuweisen, dass Sie kein Roboter sind](../../media/mtp-eval-26.png)

5. <span data-ttu-id="51d41-165">Klicken Sie auf **"Jetzt testen",** um Ihre Microsoft 365 E5 Testversion zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="51d41-165">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Abbildung of_Microsoft 365 E5–Startseite für die kostenlose Testversion, auf der Sie die Schaltfläche "Jetzt testen" anzeigen sollten, um zu starten](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="51d41-167">Wechseln Sie zu den aktiven Benutzern **Microsoft 365 Admin**  >  **Center-Benutzer.**  >  </span><span class="sxs-lookup"><span data-stu-id="51d41-167">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="51d41-168">Wählen Sie Ihr Benutzerkonto aus, wählen **Sie "Produktlizenzen verwalten"** und dann die Lizenz von Office 365 E5 in **Microsoft 365 E5** aus.</span><span class="sxs-lookup"><span data-stu-id="51d41-168">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="51d41-169">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="51d41-169">Click **Save**.</span></span>

   ![Abbildung of_Microsoft 365 Admin Center-Seite, auf der Sie Microsoft 365 E5 Lizenz auswählen können](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="51d41-171">Wählen Sie das globale Administratorkonto erneut aus, und klicken Sie dann auf **"Benutzernamen verwalten".**</span><span class="sxs-lookup"><span data-stu-id="51d41-171">Select the global administrator account again then click **Manage username**.</span></span>

   ![Abbildung of_Microsoft 365 Admin Center-Seite, auf der Sie "Konto" und dann "Benutzername verwalten" auswählen können](../../media/mtp-eval-29.png)

8. <span data-ttu-id="51d41-173">[Optional] Ändern Sie die Domäne von *onmicrosoft.com* in Ihre eigene Domäne, je nachdem, was Sie in den vorherigen Schritten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="51d41-173">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="51d41-174">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="51d41-174">Click **Save changes**.</span></span>

   ![Abbildung of_Microsoft 365 Admin Center-Seite, auf der Sie Ihre Domäneneinstellung ändern können](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="51d41-176">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="51d41-176">Next step</span></span>
|[<span data-ttu-id="51d41-177">Phase 3: Konfigurieren & Onboarding</span><span class="sxs-lookup"><span data-stu-id="51d41-177">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="51d41-178">Konfigurieren Sie jede Microsoft 365 Defender Säulen für Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung, und integrieren Sie Ihre Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="51d41-178">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
