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
ms.openlocfilehash: 47f4ceeebd50784b1880a028ebe2698012c406da
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844824"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="994b1-104">Einrichten Ihrer Microsoft 365 Defender Test Lab-Umgebung</span><span class="sxs-lookup"><span data-stu-id="994b1-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="994b1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="994b1-105">**Applies to:**</span></span>
- <span data-ttu-id="994b1-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="994b1-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="994b1-107">Das Erstellen eines Microsoft 365 Defender-Testlabors oder einer Pilotumgebung und deren Bereitstellung ist ein dreistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="994b1-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="Vorbereiten Ihres Microsoft 365 Defender-Evaluierungs Labors oder einer Pilotumgebung" />
      <br/><span data-ttu-id="994b1-109">Phase 1: Vorbereiten </a></span><span class="sxs-lookup"><span data-stu-id="994b1-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab or pilot environment" title="Einrichten Ihrer Microsoft 365 Defender Test Lab-oder Pilotumgebung" />
      <br/><span data-ttu-id="994b1-111">Phase 2: Setup </a></span><span class="sxs-lookup"><span data-stu-id="994b1-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints" title="
Konfigurieren der einzelnen Microsoft 365 Defender-Pfeiler für Ihre Microsoft 365 Defender Test Lab oder Pilotumgebung und an Bord ihrer Endpunkte" />
      <br/><span data-ttu-id="994b1-113">Phase 3: Konfigurieren von & Onboard </a></span><span class="sxs-lookup"><span data-stu-id="994b1-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="994b1-114">Sie befinden sich derzeit in der Setupphase.</span><span class="sxs-lookup"><span data-stu-id="994b1-114">You're currently in the set up phase.</span></span> <span data-ttu-id="994b1-115">Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, und richten Sie die Testumgebung oder Pilotumgebung ein.</span><span class="sxs-lookup"><span data-stu-id="994b1-115">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="994b1-116">Registrieren Sie sich für ein Office 365 oder Azure Active Directory-Abonnement, um einen *. onmicrosoft.com-* Mandanten zu generieren, mit dem Sie sich für Ihre Microsoft 365 E5-Lizenz anmelden können.</span><span class="sxs-lookup"><span data-stu-id="994b1-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="994b1-117">Wenn Sie bereits über ein vorhandenes Office 365-oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Test-oder Pilot Mandanten überspringen.</span><span class="sxs-lookup"><span data-stu-id="994b1-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="994b1-118">In dieser Phase werden Sie zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="994b1-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="994b1-119">Erstellen eines Office 365 E5-Testmandanten</span><span class="sxs-lookup"><span data-stu-id="994b1-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="994b1-120">Microsoft 365-Testabonnement aktivieren</span><span class="sxs-lookup"><span data-stu-id="994b1-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="994b1-121">Erstellen eines Office 365 E5-Testmandanten</span><span class="sxs-lookup"><span data-stu-id="994b1-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="994b1-122">Wenn Sie bereits über ein vorhandenes Office 365-oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Testmandanten überspringen.</span><span class="sxs-lookup"><span data-stu-id="994b1-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="994b1-123">Wechseln Sie zum [Office 365 E5-Produkt Portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) , und wählen Sie **﻿Kostenlose Testversion** aus.</span><span class="sxs-lookup"><span data-stu-id="994b1-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Image of_Office 365 E5 ﻿kostenlose Test Seite](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="994b1-125">Schließen Sie die Testregistrierung ab, indem Sie Ihre e-Mail-Adresse (persönlich oder Unternehmen) eingeben.</span><span class="sxs-lookup"><span data-stu-id="994b1-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="994b1-126">Klicken Sie auf **Konto einrichten**.</span><span class="sxs-lookup"><span data-stu-id="994b1-126">Click **Set up account**.</span></span>

   ![Setup Seite für Bild of_Office 365 E5-Testregistrierung](../../media/mtp-eval-10.png)

3. <span data-ttu-id="994b1-128">Geben Sie den Vornamen, den Nachnamen, die geschäftliche Telefonnummer, den Firmennamen, die Unternehmensgröße und das Land oder die Region ein.</span><span class="sxs-lookup"><span data-stu-id="994b1-128">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Image of_Office 365 E5-Test Registrierungs Setup-Seite Fragen nach Namen, Telefon-und Firmendetails](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="994b1-130">Das Land oder die Region, die Sie hier festgelegt haben, bestimmt die Rechenzentrums Region, in der Ihr Office 365 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="994b1-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="994b1-131">Wählen Sie Ihre Verifizierungs Präferenz: durch eine Textnachricht oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="994b1-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="994b1-132">Klicken Sie auf **Bestätigungs Code senden**.</span><span class="sxs-lookup"><span data-stu-id="994b1-132">Click **Send Verification Code**.</span></span> 

   ![Image of_Office 365 E5-Test Registrierungs Setup Seite mit der Aufforderung zur Überprüfung bevorzugt](../../media/mtp-eval-12.png)

5. <span data-ttu-id="994b1-134">Legen Sie den benutzerdefinierten Domänennamen für Ihren Mandanten fest, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="994b1-134">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Image of_Office 365 E5-Test Registrierungs Setup-Seite, auf der Sie Ihren benutzerdefinierten Domänennamen einrichten können](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="994b1-136">Richten Sie die erste Identität ein, die ein globaler Administrator für den Mandanten sein wird.</span><span class="sxs-lookup"><span data-stu-id="994b1-136">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="994b1-137">Geben Sie den **Namen** und das **Kennwort ein**.</span><span class="sxs-lookup"><span data-stu-id="994b1-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="994b1-138">Klicken Sie auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="994b1-138">Click **Sign up**.</span></span>

   ![Image of_Office 365 E5-Test Registrierungs Setup Seite, auf der Sie Ihre Geschäftsidentität festlegen können](../../media/mtp-eval-14.png)

7. <span data-ttu-id="994b1-140">Klicken Sie auf **Gehe zu Setup** , um die Office 365 E5-Testmandanten Provision abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="994b1-140">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Bild der Office 365 E5-Test Registrierungsseite, die zum Klicken auf die Schaltfläche "Gehe zu Setup" auffordert](../../media/mtp-eval-15.png)

8. <span data-ttu-id="994b1-142">Verbinden Sie Ihre Unternehmensdomäne mit dem Office 365 Mandanten.</span><span class="sxs-lookup"><span data-stu-id="994b1-142">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="994b1-143">Optional Wählen **Sie Verbinden einer Domäne aus, die Sie bereits besitzen** , und geben Sie Ihren Domänennamen ein.</span><span class="sxs-lookup"><span data-stu-id="994b1-143">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="994b1-144">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="994b1-144">Click **Next**.</span></span>

   ![Image of_Office 365 E5-Setup Seite, auf der Sie Ihre Anmeldung und e-Mail personalisieren sollten](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="994b1-146">Hinzufügen eines txt-oder MX-Eintrags zum Überprüfen des Domänenbesitzes.</span><span class="sxs-lookup"><span data-stu-id="994b1-146">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="994b1-147">Nachdem Sie den txt-oder MX-Eintrag zu Ihrer Domäne hinzugefügt haben, wählen Sie **überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="994b1-147">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Image of_Office 365 E5-Setup Seite, auf der Sie einen MX-Eintrag txt hinzufügen sollten, um Ihre Domäne zu überprüfen](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="994b1-149">Optional Erstellen Sie weitere Benutzerkonten für Ihren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="994b1-149">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="994b1-150">Sie können diesen Schritt überspringen, indem Sie auf **weiter** klicken.</span><span class="sxs-lookup"><span data-stu-id="994b1-150">You can skip this step by clicking **Next**.</span></span>

    ![Image of_Office 365 E5-Setup Seite, auf der Sie weitere Benutzer hinzufügen können](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="994b1-152">Optional Laden Sie Office-Apps herunter.</span><span class="sxs-lookup"><span data-stu-id="994b1-152">[Optional] Download Office apps.</span></span> <span data-ttu-id="994b1-153">Klicken Sie auf **weiter** , um diesen Schritt zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="994b1-153">Click **Next** to skip this step.</span></span> 

    ![Image of_Office 365 E5-Seite, auf der Sie Ihre Office-Apps installieren können](../../media/mtp-eval-19.png)

12. <span data-ttu-id="994b1-155">Optional Migrieren von e-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="994b1-155">[Optional] Migrate email messages.</span></span> <span data-ttu-id="994b1-156">Sie können diesen Schritt auch wieder überspringen.</span><span class="sxs-lookup"><span data-stu-id="994b1-156">Again, you can skip this step.</span></span>

    ![Image of_Office 365 E5, in dem Sie festlegen können, ob e-Mail-Nachrichten migriert werden sollen oder nicht](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="994b1-158">Wählen Sie Onlinedienste aus.</span><span class="sxs-lookup"><span data-stu-id="994b1-158">Choose online services.</span></span> <span data-ttu-id="994b1-159">Wählen Sie **Exchange** aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="994b1-159">Select **Exchange** and click **Next**.</span></span> 

    ![Image of_Office 365 E5, wo Sie Ihre Onlinedienste auswählen können](../../media/mtp-eval-21.png)

14. <span data-ttu-id="994b1-161">Fügen Sie Ihrer Domäne MX-, CNAME-und TXT-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="994b1-161">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="994b1-162">Wählen Sie nach Abschluss die Option **überprüfen** aus.</span><span class="sxs-lookup"><span data-stu-id="994b1-162">When completed, select **Verify**.</span></span>

    ![Bild of_Office 365 E5 hier können Sie Ihre DNS-Einträge hinzufügen](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="994b1-164">Herzlichen Glückwunsch, Sie haben die Überstellung Ihres Office 365 Mandanten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="994b1-164">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Bestätigungsseite für Bild of_Office 365 E5-Setup Abschluss](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="994b1-166">Microsoft 365-Testabonnement aktivieren</span><span class="sxs-lookup"><span data-stu-id="994b1-166">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="994b1-167">Wenn Sie sich für eine Testversion registrieren, erhalten Sie 25 Benutzerlizenzen, die für einen Monat verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="994b1-167">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="994b1-168">Weitere Informationen finden Sie unter [Testen oder kaufen eines M365-Abonnements](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) .</span><span class="sxs-lookup"><span data-stu-id="994b1-168">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="994b1-169">Klicken Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/)auf **Abrechnung** , und navigieren Sie zu **Dienste kaufen**.</span><span class="sxs-lookup"><span data-stu-id="994b1-169">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="994b1-170">Wählen Sie **Microsoft 365 E5** aus, und klicken Sie auf **﻿Kostenlose Testversion starten**.</span><span class="sxs-lookup"><span data-stu-id="994b1-170">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Image of_Microsoft 365 E5 Start ﻿kostenlose Test Seite](../../media/mtp-eval-24.png)

3. <span data-ttu-id="994b1-172">Wählen Sie Ihre Verifizierungs Präferenz: durch eine Textnachricht oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="994b1-172">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="994b1-173">Wenn Sie sich entschieden haben, geben Sie die Telefonnummer ein, wählen Sie **Text mich** oder **rufen Sie mich** je nach Ihrer Auswahl an.</span><span class="sxs-lookup"><span data-stu-id="994b1-173">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 Start ﻿kostenlose Test Seite Fragen Sie nach Kontaktdetails zum Senden von Code, um zu beweisen, dass Sie kein Roboter sind](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="994b1-175">Geben Sie den Verifizierungscode ein, und klicken Sie auf **﻿Kostenlose Testversion starten**.</span><span class="sxs-lookup"><span data-stu-id="994b1-175">Enter the verification code and click **Start your free trial**.</span></span>

   ![Image of_Microsoft 365 E5 Start ﻿kostenlose Test Seite, auf der Sie den Überprüfungscode ausfüllen können das System, das zum Nachweis gesendet wird, dass Sie kein Roboter sind](../../media/mtp-eval-26.png)

5. <span data-ttu-id="994b1-177">Klicken Sie auf **jetzt testen** , um Ihre Microsoft 365 E5-Testversion zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="994b1-177">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 Startkosten lose Test Seite, auf der Sie die Schaltfläche "jetzt testen" starten sollten](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="994b1-179">Wechseln Sie zum **Microsoft 365 Admin Center**  >  **Users**  >  **Active Users**.</span><span class="sxs-lookup"><span data-stu-id="994b1-179">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="994b1-180">Wählen Sie Ihr Benutzerkonto aus, wählen Sie **Produktlizenzen verwalten** aus, und tauschen Sie dann die Lizenz von Office 365 E5 auf **Microsoft 365 E5** aus.</span><span class="sxs-lookup"><span data-stu-id="994b1-180">Select your user account, select **Manage product licenses** , then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="994b1-181">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="994b1-181">Click **Save**.</span></span>

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie die Microsoft 365 E5-Lizenz auswählen können](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="994b1-183">Wählen Sie erneut das globale Administratorkonto aus, und klicken Sie dann auf **Benutzername verwalten**.</span><span class="sxs-lookup"><span data-stu-id="994b1-183">Select the global administrator account again then click **Manage username**.</span></span>

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie Konto auswählen und dann Benutzername verwalten können](../../media/mtp-eval-29.png)

8. <span data-ttu-id="994b1-185">Optional Ändern Sie die Domäne von *onmicrosoft.com* in Ihre eigene Domäne – je nachdem, was Sie in den vorherigen Schritten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="994b1-185">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="994b1-186">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="994b1-186">Click **Save changes**.</span></span>

   ![Image of_Microsoft 365 Admin Center-Seite, auf der Sie die Domäneneinstellung ändern können](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="994b1-188">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="994b1-188">Next step</span></span>
|<span data-ttu-id="994b1-189">![Phase 3: Konfigurieren von & Onboard](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="994b1-189">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="994b1-190">Phase 3: Konfigurieren von & Onboard</span><span class="sxs-lookup"><span data-stu-id="994b1-190">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="994b1-191">Konfigurieren Sie jede Microsoft 365 Defender-Säule für Ihre Microsoft 365 Defender Test Lab oder Pilotumgebung und an Bord ihrer Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="994b1-191">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
