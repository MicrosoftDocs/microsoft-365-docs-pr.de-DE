---
title: Einrichten Ihres Microsoft Threat Protection-Testlabors oder einer Pilotumgebung
description: Greifen Sie auf Microsoft 365 Security Center zu, und richten Sie Ihre Microsoft Threat Protection Test Lab-Umgebung ein.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: a0997c107e78104619e1e05b8d1073e8690a3667
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48195559"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="ba344-104">Einrichten Ihrer Microsoft Threat Protection-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="ba344-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ba344-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ba344-105">**Applies to:**</span></span>
- <span data-ttu-id="ba344-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="ba344-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="ba344-107">Das Erstellen eines Microsoft Threat Protection-Testlabors oder einer Pilotumgebung und deren Bereitstellung ist ein dreistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="ba344-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Vorbereiten des Microsoft Threat Protection-Evaluierungs Labors oder der Pilotumgebung" />
      <br/><span data-ttu-id="ba344-109">Phase 1: Vorbereiten </a></span><span class="sxs-lookup"><span data-stu-id="ba344-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Einrichten Ihres Microsoft Threat Protection-Testlabors oder einer Pilotumgebung" />
      <br/><span data-ttu-id="ba344-111">Phase 2: Setup </a></span><span class="sxs-lookup"><span data-stu-id="ba344-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab or pilot environment and onboard your endpoints" title="
Konfigurieren der einzelnen Microsoft Threat Protection-Pfeiler für Ihre Microsoft Threat Protection-Testumgebung oder-Pilotumgebung und an Bord ihrer Endpunkte" />
      <br/><span data-ttu-id="ba344-113">Phase 3: Konfigurieren von & Onboard </a></span><span class="sxs-lookup"><span data-stu-id="ba344-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="ba344-114">Sie befinden sich derzeit in der Setupphase.</span><span class="sxs-lookup"><span data-stu-id="ba344-114">You're currently in the set up phase.</span></span> <span data-ttu-id="ba344-115">Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, und richten Sie die Testumgebung oder Pilotumgebung ein.</span><span class="sxs-lookup"><span data-stu-id="ba344-115">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="ba344-116">Registrieren Sie sich für ein Office 365 oder Azure Active Directory-Abonnement, um einen *. onmicrosoft.com-* Mandanten zu generieren, mit dem Sie sich für Ihre Microsoft 365 E5-Lizenz anmelden können.</span><span class="sxs-lookup"><span data-stu-id="ba344-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="ba344-117">Wenn Sie bereits über ein vorhandenes Office 365-oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Test-oder Pilot Mandanten überspringen.</span><span class="sxs-lookup"><span data-stu-id="ba344-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="ba344-118">In dieser Phase werden Sie zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="ba344-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="ba344-119">Erstellen eines Office 365 E5-Testmandanten</span><span class="sxs-lookup"><span data-stu-id="ba344-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="ba344-120">Microsoft 365-Testabonnement aktivieren</span><span class="sxs-lookup"><span data-stu-id="ba344-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="ba344-121">Erstellen eines Office 365 E5-Testmandanten</span><span class="sxs-lookup"><span data-stu-id="ba344-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="ba344-122">Wenn Sie bereits über ein vorhandenes Office 365-oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Testmandanten überspringen.</span><span class="sxs-lookup"><span data-stu-id="ba344-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="ba344-123">Wechseln Sie zum [Office 365 E5-Produkt Portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) , und wählen Sie **﻿Kostenlose Testversion**aus.</span><span class="sxs-lookup"><span data-stu-id="ba344-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="ba344-124">![Image of_Office 365 E5 ﻿kostenlose Test Seite](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-124">![Image of_Office 365 E5 free trial page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="ba344-125">Schließen Sie die Testregistrierung ab, indem Sie Ihre e-Mail-Adresse (persönlich oder Unternehmen) eingeben.</span><span class="sxs-lookup"><span data-stu-id="ba344-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="ba344-126">Klicken Sie auf **Konto einrichten**.</span><span class="sxs-lookup"><span data-stu-id="ba344-126">Click **Set up account**.</span></span>
<span data-ttu-id="ba344-127">![Setup Seite für Bild of_Office 365 E5-Testregistrierung](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-127">![Image of_Office 365 E5 trial registration setup page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="ba344-128">Geben Sie den Vornamen, den Nachnamen, die geschäftliche Telefonnummer, den Firmennamen, die Unternehmensgröße und das Land oder die Region ein.</span><span class="sxs-lookup"><span data-stu-id="ba344-128">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  
<br>![Image of_Office 365 E5-Test Registrierungs Setup-Seite Fragen nach Namen, Telefon-und Firmendetails](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="ba344-130">Das Land oder die Region, die Sie hier festgelegt haben, bestimmt die Rechenzentrums Region, in der Ihr Office 365 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="ba344-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="ba344-131">Wählen Sie Ihre Verifizierungs Präferenz: durch eine Textnachricht oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="ba344-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="ba344-132">Klicken Sie auf **Bestätigungs Code senden**.</span><span class="sxs-lookup"><span data-stu-id="ba344-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="ba344-133">![Image of_Office 365 E5-Test Registrierungs Setup Seite mit der Aufforderung zur Überprüfung bevorzugt](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-133">![Image of_Office 365 E5 trial registration setup page asking for verification preference](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="ba344-134">Legen Sie den benutzerdefinierten Domänennamen für Ihren Mandanten fest, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="ba344-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="ba344-135">![Image of_Office 365 E5-Test Registrierungs Setup-Seite, auf der Sie Ihren benutzerdefinierten Domänennamen einrichten können](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-135">![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="ba344-136">Richten Sie die erste Identität ein, die ein globaler Administrator für den Mandanten sein wird.</span><span class="sxs-lookup"><span data-stu-id="ba344-136">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="ba344-137">Geben Sie den **Namen** und das **Kennwort ein**.</span><span class="sxs-lookup"><span data-stu-id="ba344-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="ba344-138">Klicken Sie auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="ba344-138">Click **Sign up**.</span></span>
<span data-ttu-id="ba344-139">![Image of_Office 365 E5-Test Registrierungs Setup Seite, auf der Sie Ihre Geschäftsidentität festlegen können](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-139">![Image of_Office 365 E5 trial registration setup page where you can set your business identity](../../media/mtp-eval-14.png)</span></span> <br>

7. <span data-ttu-id="ba344-140">Klicken Sie auf **Gehe zu Setup** , um die Office 365 E5-Testmandanten Provision abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="ba344-140">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="ba344-141">![Bild der Office 365 E5-Test Registrierungsseite, die zum Klicken auf die Schaltfläche "Gehe zu Setup" auffordert](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-141">![Image of Office 365 E5 trial registration setup page prompting to click Go Setup button](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="ba344-142">Verbinden Sie Ihre Unternehmensdomäne mit dem Office 365 Mandanten.</span><span class="sxs-lookup"><span data-stu-id="ba344-142">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="ba344-143">Optional Wählen **Sie Verbinden einer Domäne aus, die Sie bereits besitzen** , und geben Sie Ihren Domänennamen ein.</span><span class="sxs-lookup"><span data-stu-id="ba344-143">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="ba344-144">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ba344-144">Click **Next**.</span></span>
<br><span data-ttu-id="ba344-145">![Image of_Office 365 E5-Setup Seite, auf der Sie Ihre Anmeldung und e-Mail personalisieren sollten](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-145">![Image of_Office 365 E5 Setup page where you should personalize your sign-in and email](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="ba344-146">Hinzufügen eines txt-oder MX-Eintrags zum Überprüfen des Domänenbesitzes.</span><span class="sxs-lookup"><span data-stu-id="ba344-146">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="ba344-147">Nachdem Sie den txt-oder MX-Eintrag zu Ihrer Domäne hinzugefügt haben, wählen Sie **überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="ba344-147">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="ba344-148">![Image of_Office 365 E5-Setup Seite, auf der Sie einen MX-Eintrag txt hinzufügen sollten, um Ihre Domäne zu überprüfen](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-148">![Image of_Office 365 E5 setup page where you should add a TXT of MX record to verify your domain](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="ba344-149">Optional Erstellen Sie weitere Benutzerkonten für Ihren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="ba344-149">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="ba344-150">Sie können diesen Schritt überspringen, indem Sie auf **weiter**klicken.</span><span class="sxs-lookup"><span data-stu-id="ba344-150">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="ba344-151">![Image of_Office 365 E5-Setup Seite, auf der Sie weitere Benutzer hinzufügen können](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-151">![Image of_Office 365 E5 setup page where you can add more users](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="ba344-152">Optional Laden Sie Office-Apps herunter.</span><span class="sxs-lookup"><span data-stu-id="ba344-152">[Optional] Download Office apps.</span></span> <span data-ttu-id="ba344-153">Klicken Sie auf **weiter** , um diesen Schritt zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="ba344-153">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="ba344-154">![Image of_Office 365 E5-Seite, auf der Sie Ihre Office-Apps installieren können](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-154">![Image of_Office 365 E5 page where you can install your Office apps](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="ba344-155">Optional Migrieren von e-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="ba344-155">[Optional] Migrate email messages.</span></span> <span data-ttu-id="ba344-156">Sie können diesen Schritt auch wieder überspringen.</span><span class="sxs-lookup"><span data-stu-id="ba344-156">Again, you can skip this step.</span></span>
<br><span data-ttu-id="ba344-157">![Image of_Office 365 E5, in dem Sie festlegen können, ob e-Mail-Nachrichten migriert werden sollen oder nicht](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-157">![Image of_Office 365 E5 where you can set whether to migrate email messages or not](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="ba344-158">Wählen Sie Onlinedienste aus.</span><span class="sxs-lookup"><span data-stu-id="ba344-158">Choose online services.</span></span> <span data-ttu-id="ba344-159">Wählen Sie **Exchange** aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="ba344-159">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="ba344-160">![Image of_Office 365 E5, wo Sie Ihre Onlinedienste auswählen können](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-160">![Image of_Office 365 E5 where you can choose your online services](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="ba344-161">Fügen Sie Ihrer Domäne MX-, CNAME-und TXT-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="ba344-161">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="ba344-162">Wählen Sie nach Abschluss die Option **überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="ba344-162">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="ba344-163">![Bild of_Office 365 E5 hier können Sie Ihre DNS-Einträge hinzufügen](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-163">![Image of_Office 365 E5 here you can add your DNS records](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="ba344-164">Herzlichen Glückwunsch, Sie haben die Überstellung Ihres Office 365 Mandanten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="ba344-164">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="ba344-165">![Bestätigungsseite für Bild of_Office 365 E5-Setup Abschluss](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-165">![Image of_Office 365 E5 setup completion confirmation page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="ba344-166">Microsoft 365-Testabonnement aktivieren</span><span class="sxs-lookup"><span data-stu-id="ba344-166">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="ba344-167">Wenn Sie sich für eine Testversion registrieren, erhalten Sie 25 Benutzerlizenzen, die für einen Monat verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ba344-167">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="ba344-168">Weitere Informationen finden Sie unter [Testen oder kaufen eines M365-Abonnements](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) .</span><span class="sxs-lookup"><span data-stu-id="ba344-168">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="ba344-169">Klicken Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/)auf **Abrechnung** , und navigieren Sie zu **Dienste kaufen**.</span><span class="sxs-lookup"><span data-stu-id="ba344-169">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="ba344-170">Wählen Sie **Microsoft 365 E5** aus, und klicken Sie auf **﻿Kostenlose Testversion starten**.</span><span class="sxs-lookup"><span data-stu-id="ba344-170">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="ba344-171">![Image of_Microsoft 365 E5 Start ﻿kostenlose Test Seite](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-171">![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="ba344-172">Wählen Sie Ihre Verifizierungs Präferenz: durch eine Textnachricht oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="ba344-172">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="ba344-173">Wenn Sie sich entschieden haben, geben Sie die Telefonnummer ein, wählen Sie **Text mich** oder **rufen Sie mich** je nach Ihrer Auswahl an.</span><span class="sxs-lookup"><span data-stu-id="ba344-173">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="ba344-174">![Image of_Microsoft 365 E5 Start ﻿kostenlose Test Seite Fragen Sie nach Kontaktdetails zum Senden von Code, um zu beweisen, dass Sie kein Roboter sind](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-174">![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="ba344-175">Geben Sie den Verifizierungscode ein, und klicken Sie auf **﻿Kostenlose Testversion starten**.</span><span class="sxs-lookup"><span data-stu-id="ba344-175">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="ba344-176">![Image of_Microsoft 365 E5 Start ﻿kostenlose Test Seite, auf der Sie den Überprüfungscode ausfüllen können das System, das zum Nachweis gesendet wird, dass Sie kein Roboter sind](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-176">![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="ba344-177">Klicken Sie auf **jetzt testen** , um Ihre Microsoft 365 E5-Testversion zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="ba344-177">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="ba344-178">![Image of_Microsoft 365 E5 Startkosten lose Test Seite, auf der Sie die Schaltfläche "jetzt testen" starten sollten](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-178">![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="ba344-179">Wechseln Sie zum **Microsoft 365 Admin Center**  >  **Users**  >  **Active Users**.</span><span class="sxs-lookup"><span data-stu-id="ba344-179">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="ba344-180">Wählen Sie Ihr Benutzerkonto aus, wählen Sie **Produktlizenzen verwalten**aus, und tauschen Sie dann die Lizenz von Office 365 E5 auf **Microsoft 365 E5**aus.</span><span class="sxs-lookup"><span data-stu-id="ba344-180">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="ba344-181">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ba344-181">Click **Save**.</span></span>
<span data-ttu-id="ba344-182">![Image of_Microsoft 365 Admin Center-Seite, auf der Sie die Microsoft 365 E5-Lizenz auswählen können](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-182">![Image of_Microsoft 365 Admin Center page where you can select Microsoft 365 E5 license](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="ba344-183">Wählen Sie erneut das globale Administratorkonto aus, und klicken Sie dann auf **Benutzername verwalten**.</span><span class="sxs-lookup"><span data-stu-id="ba344-183">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="ba344-184">![Image of_Microsoft 365 Admin Center-Seite, auf der Sie Konto auswählen und dann Benutzername verwalten können](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-184">![Image of_Microsoft 365 Admin Center page where you can select Account and then Manage username](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="ba344-185">Optional Ändern Sie die Domäne von *onmicrosoft.com* in Ihre eigene Domäne – je nachdem, was Sie in den vorherigen Schritten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="ba344-185">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="ba344-186">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="ba344-186">Click **Save changes**.</span></span>
<br><span data-ttu-id="ba344-187">![Image of_Microsoft 365 Admin Center-Seite, auf der Sie die Domäneneinstellung ändern können](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-187">![Image of_Microsoft 365 Admin Center page where you can change your domain preference](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="ba344-188">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ba344-188">Next step</span></span>
|<span data-ttu-id="ba344-189">![Phase 3: Konfigurieren von & Onboard](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="ba344-189">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="ba344-190">Phase 3: Konfigurieren von & Onboard</span><span class="sxs-lookup"><span data-stu-id="ba344-190">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="ba344-191">Konfigurieren Sie jede Microsoft Threat Protection-Säule für Ihr Microsoft Threat Protection-Test Labor oder Ihre Pilotumgebung und an Bord ihrer Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="ba344-191">Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
