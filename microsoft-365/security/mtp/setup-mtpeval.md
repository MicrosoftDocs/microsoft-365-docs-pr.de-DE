---
title: Einrichten Ihrer Microsoft Threat Protection-Testumgebung
description: Greifen Sie auf Microsoft 365 Security Center zu, und richten Sie Ihre Microsoft Threat Protection Test Lab-Umgebung ein.
keywords: Microsoft Threat Protection-Test-Setup, testen Sie Microsoft Threat Protection, Microsoft Threat Protection Evaluation Lab Setup
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
ms.openlocfilehash: 50557b0824999f0220af4d12b906b0274db4471e
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049615"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="7bc27-104">Einrichten Ihrer Microsoft Threat Protection-Testumgebung</span><span class="sxs-lookup"><span data-stu-id="7bc27-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="7bc27-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="7bc27-105">**Applies to:**</span></span>
- <span data-ttu-id="7bc27-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="7bc27-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="7bc27-107">Das Erstellen einer Microsoft Threat Protection-Test Umgebungsumgebung und deren Bereitstellung ist ein dreistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="7bc27-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Vorbereiten des Microsoft Threat Protection-Evaluierungs Labors" />
      <br/><span data-ttu-id="7bc27-109">Phase 1: Vorbereiten</a></span><span class="sxs-lookup"><span data-stu-id="7bc27-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Einrichten Ihres Microsoft Threat Protection-Evaluierungs Labors" />
      <br/><span data-ttu-id="7bc27-111">Phase 2: Setup</a></span><span class="sxs-lookup"><span data-stu-id="7bc27-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
Konfigurieren der einzelnen Microsoft Threat Protection-Pfeiler für Ihre Microsoft Threat Protection-Test Umgebungsumgebung und die Bereitstellung an Bord ihrer Endpunkte" />
      <br/><span data-ttu-id="7bc27-113">Phase 3: Konfigurieren von & Onboard</a></span><span class="sxs-lookup"><span data-stu-id="7bc27-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="7bc27-114">Sie befinden sich derzeit in der Setupphase.</span><span class="sxs-lookup"><span data-stu-id="7bc27-114">You are currently in the set up phase.</span></span> <span data-ttu-id="7bc27-115">Führen Sie die ersten Schritte für den Zugriff auf das Microsoft 365 Security Center aus, und installieren Sie dann die Testumgebung.</span><span class="sxs-lookup"><span data-stu-id="7bc27-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="7bc27-116">Registrieren Sie sich für ein Office 365 oder Azure Active Directory-Abonnement, um einen *. onmicrosoft.com-* Mandanten zu generieren, mit dem Sie sich für Ihre Microsoft 365 E5-Lizenz anmelden können.</span><span class="sxs-lookup"><span data-stu-id="7bc27-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="7bc27-117">Wenn Sie bereits über ein vorhandenes Office 365-oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Testmandanten überspringen.</span><span class="sxs-lookup"><span data-stu-id="7bc27-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="7bc27-118">In dieser Phase werden Sie zu folgenden Themen geführt:</span><span class="sxs-lookup"><span data-stu-id="7bc27-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="7bc27-119">Erstellen eines Office 365 E5-Testmandanten</span><span class="sxs-lookup"><span data-stu-id="7bc27-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="7bc27-120">Microsoft 365-Testabonnement aktivieren</span><span class="sxs-lookup"><span data-stu-id="7bc27-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="7bc27-121">Erstellen eines Office 365 E5-Testmandanten</span><span class="sxs-lookup"><span data-stu-id="7bc27-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="7bc27-122">Wenn Sie bereits über ein vorhandenes Office 365-oder Azure Active Directory-Abonnement verfügen, können Sie die Schritte zum Erstellen von Office 365 E5-Testmandanten überspringen.</span><span class="sxs-lookup"><span data-stu-id="7bc27-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="7bc27-123">Wechseln Sie zum [Office 365 E5-Produkt Portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) , und wählen Sie **﻿Kostenlose Testversion**aus.</span><span class="sxs-lookup"><span data-stu-id="7bc27-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="7bc27-124">![Bild of_page](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-124">![Image of_page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="7bc27-125">Schließen Sie die Testregistrierung ab, indem Sie Ihre e-Mail-Adresse (persönlich oder Unternehmen) eingeben.</span><span class="sxs-lookup"><span data-stu-id="7bc27-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="7bc27-126">Klicken Sie auf **Konto einrichten**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-126">Click **Set up account**.</span></span>
<span data-ttu-id="7bc27-127">![Bild of_page](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-127">![Image of_page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="7bc27-128">Geben Sie den Vornamen, den Nachnamen, die geschäftliche Telefonnummer, den Firmennamen, die Unternehmensgröße und das Land oder die Region ein.</span><span class="sxs-lookup"><span data-stu-id="7bc27-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![Bild of_page](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="7bc27-130">Das Land oder die Region, die Sie hier festgelegt haben, bestimmt die Rechenzentrums Region, in der Ihr Office 365 gehostet wird.</span><span class="sxs-lookup"><span data-stu-id="7bc27-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="7bc27-131">Wählen Sie Ihre Verifizierungs Präferenz: durch eine Textnachricht oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="7bc27-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="7bc27-132">Klicken Sie auf **Bestätigungs Code senden**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="7bc27-133">![Bild of_page](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-133">![Image of_page](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="7bc27-134">Legen Sie den benutzerdefinierten Domänennamen für Ihren Mandanten fest, und klicken Sie dann auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="7bc27-135">![Bild of_page](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-135">![Image of_page](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="7bc27-136">Richten Sie die erste Identität ein, die ein globaler Administrator für den Mandanten sein wird.</span><span class="sxs-lookup"><span data-stu-id="7bc27-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="7bc27-137">Geben Sie den **Namen** und das **Kennwort ein**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="7bc27-138">Klicken Sie auf **Anmelden**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-138">Click **Sign up**.</span></span>
<span data-ttu-id="7bc27-139">![Bild of_page](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-139">![Image of_page](../../media/mtp-eval-14.png)</span></span> <br>
<span data-ttu-id="7bc27-140">c</span><span class="sxs-lookup"><span data-stu-id="7bc27-140">c</span></span>
7. <span data-ttu-id="7bc27-141">Klicken Sie auf **Gehe zu Setup** , um die Office 365 E5-Testmandanten Provision abzuschließen.</span><span class="sxs-lookup"><span data-stu-id="7bc27-141">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="7bc27-142">![Bild of_page](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-142">![Image of_page](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="7bc27-143">Verbinden Sie Ihre Unternehmensdomäne mit dem Office 365 Mandanten.</span><span class="sxs-lookup"><span data-stu-id="7bc27-143">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="7bc27-144">Optional Wählen **Sie Verbinden einer Domäne aus, die Sie bereits besitzen** , und geben Sie Ihren Domänennamen ein.</span><span class="sxs-lookup"><span data-stu-id="7bc27-144">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="7bc27-145">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-145">Click **Next**.</span></span>
<br><span data-ttu-id="7bc27-146">![Bild of_page](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-146">![Image of_page](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="7bc27-147">Sie müssen einen txt-oder MX-Eintrag hinzufügen, um den Domänenbesitz zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="7bc27-147">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="7bc27-148">Nachdem Sie den txt-oder MX-Eintrag zu Ihrer Domäne hinzugefügt haben, wählen Sie **überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="7bc27-148">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="7bc27-149">![Bild of_page](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-149">![Image of_page](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="7bc27-150">Optional Erstellen Sie weitere Benutzerkonten für Ihren Mandanten.</span><span class="sxs-lookup"><span data-stu-id="7bc27-150">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="7bc27-151">Sie können diesen Schritt überspringen, indem Sie auf **weiter**klicken.</span><span class="sxs-lookup"><span data-stu-id="7bc27-151">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="7bc27-152">![Bild of_page](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-152">![Image of_page](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="7bc27-153">Optional Laden Sie Office-Apps herunter.</span><span class="sxs-lookup"><span data-stu-id="7bc27-153">[Optional] Download Office apps.</span></span> <span data-ttu-id="7bc27-154">Klicken Sie auf **weiter** , um diesen Schritt zu überspringen.</span><span class="sxs-lookup"><span data-stu-id="7bc27-154">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="7bc27-155">![Bild of_page](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-155">![Image of_page](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="7bc27-156">Optional Migrieren von e-Mail-Nachrichten</span><span class="sxs-lookup"><span data-stu-id="7bc27-156">[Optional] Migrate email messages.</span></span> <span data-ttu-id="7bc27-157">Sie können diesen Schritt auch wieder überspringen.</span><span class="sxs-lookup"><span data-stu-id="7bc27-157">Again, you can skip this step.</span></span>
<br><span data-ttu-id="7bc27-158">![Bild of_page](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-158">![Image of_page](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="7bc27-159">Wählen Sie Onlinedienste aus.</span><span class="sxs-lookup"><span data-stu-id="7bc27-159">Choose online services.</span></span> <span data-ttu-id="7bc27-160">Wählen Sie **Exchange** aus, und klicken Sie auf **weiter**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-160">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="7bc27-161">![Bild of_page](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-161">![Image of_page](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="7bc27-162">Fügen Sie Ihrer Domäne MX-, CNAME-und TXT-Einträge hinzu.</span><span class="sxs-lookup"><span data-stu-id="7bc27-162">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="7bc27-163">Wählen Sie nach Abschluss die Option **überprüfen**aus.</span><span class="sxs-lookup"><span data-stu-id="7bc27-163">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="7bc27-164">![Bild of_page](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-164">![Image of_page](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="7bc27-165">Herzlichen Glückwunsch, Sie haben die Überstellung Ihres Office 365 Mandanten abgeschlossen.</span><span class="sxs-lookup"><span data-stu-id="7bc27-165">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="7bc27-166">![Bild of_page](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-166">![Image of_page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="7bc27-167">Microsoft 365-Testabonnement aktivieren</span><span class="sxs-lookup"><span data-stu-id="7bc27-167">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="7bc27-168">Wenn Sie sich für eine Testversion registrieren, erhalten Sie 25 Benutzerlizenzen, die für einen Monat verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="7bc27-168">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="7bc27-169">Weitere Informationen finden Sie unter [Testen oder kaufen eines M365-Abonnements](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) .</span><span class="sxs-lookup"><span data-stu-id="7bc27-169">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="7bc27-170">Klicken Sie im [Microsoft 365 Admin Center](https://admin.microsoft.com/)auf **Abrechnung** , und navigieren Sie zu **Dienste kaufen**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-170">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="7bc27-171">Wählen Sie **Microsoft 365 E5** aus, und klicken Sie auf **﻿Kostenlose Testversion starten**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-171">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="7bc27-172">![Bild of_page](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-172">![Image of_page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="7bc27-173">Wählen Sie Ihre Verifizierungs Präferenz: durch eine Textnachricht oder einen Anruf.</span><span class="sxs-lookup"><span data-stu-id="7bc27-173">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="7bc27-174">Wenn Sie sich entschieden haben, geben Sie die Telefonnummer ein, wählen Sie **Text mich** oder **rufen Sie mich** je nach Ihrer Auswahl an.</span><span class="sxs-lookup"><span data-stu-id="7bc27-174">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="7bc27-175">![Bild of_page](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-175">![Image of_page](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="7bc27-176">Geben Sie den Verifizierungscode ein, und klicken Sie auf **﻿Kostenlose Testversion starten**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-176">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="7bc27-177">![Bild of_page](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-177">![Image of_page](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="7bc27-178">Klicken Sie auf **jetzt testen** , um Ihre Microsoft 365 E5-Testversion zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="7bc27-178">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="7bc27-179">![Bild of_page](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-179">![Image of_page](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="7bc27-180">Wechseln Sie zum **Microsoft 365 Admin Center** > **Users** > **Active Users**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-180">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="7bc27-181">Wählen Sie Ihr Benutzerkonto aus, wählen Sie **Produktlizenzen verwalten**aus, und tauschen Sie dann die Lizenz von Office 365 E5 auf **Microsoft 365 E5**aus.</span><span class="sxs-lookup"><span data-stu-id="7bc27-181">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="7bc27-182">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-182">Click **Save**.</span></span>
<span data-ttu-id="7bc27-183">![Bild of_page](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-183">![Image of_page](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="7bc27-184">Wählen Sie erneut das globale Administratorkonto aus, und klicken Sie dann auf **Benutzername verwalten**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-184">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="7bc27-185">![Bild of_page](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-185">![Image of_page](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="7bc27-186">Optional Ändern Sie die Domäne von *onmicrosoft.com* in Ihre eigene Domäne – je nachdem, was Sie in den vorherigen Schritten ausgewählt haben.</span><span class="sxs-lookup"><span data-stu-id="7bc27-186">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="7bc27-187">Klicken Sie auf **Änderungen speichern**.</span><span class="sxs-lookup"><span data-stu-id="7bc27-187">Click **Save changes**.</span></span>
<br><span data-ttu-id="7bc27-188">![Bild of_page](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-188">![Image of_page](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="7bc27-189">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="7bc27-189">Next step</span></span>
<span data-ttu-id="7bc27-190">||| |:-------|:-----| config-Onboard. png)</span><span class="sxs-lookup"><span data-stu-id="7bc27-190">||| |:-------|:-----|config-onboard.png)</span></span> <br><span data-ttu-id="7bc27-191">[Phase 3: Konfigurieren von & Onboard](config-mtpeval.md) | Konfigurieren Sie jede Microsoft Threat Protection-Säule für Ihre Microsoft Threat Protection-Test Umgebungsumgebung und ihre Endpunkte an Bord.</span><span class="sxs-lookup"><span data-stu-id="7bc27-191">[Phase 3: Configure & Onboard](config-mtpeval.md) | Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints.</span></span>
