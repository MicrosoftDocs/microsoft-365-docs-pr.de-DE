---
title: Konfigurieren von Microsoft Threat Protection-Säulen für die Testlaborumgebung
description: Konfigurieren von Microsoft Threat Protection-Säulen, Office 365 ATP, Azure ATP, Microsoft Cloud App Security und Microsoft Defender ATP für Ihre Testlaborumgebung
keywords: Konfigurieren der Microsoft Threat Protection-Testversion, Microsoft Threat Protection-Testkonfiguration, Konfigurieren von Microsoft Threat Protection-Säulen, Microsoft Threat Protection-Säulen
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
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049509"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="28f49-104">Konfigurieren von Microsoft Threat Protection-Säulen für Ihre Testlaborumgebung</span><span class="sxs-lookup"><span data-stu-id="28f49-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="28f49-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="28f49-105">**Applies to:**</span></span>
- <span data-ttu-id="28f49-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="28f49-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="28f49-107">Das Erstellen einer Microsoft Threat Protection-Test Umgebungsumgebung und deren Bereitstellung ist ein dreistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="28f49-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="Vorbereiten Ihrer Microsoft Threat Protection-Testumgebung" />
      <br/><span data-ttu-id="28f49-109">Phase 1: Vorbereiten</a></span><span class="sxs-lookup"><span data-stu-id="28f49-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="Einrichten Ihrer Microsoft Threat Protection-Testumgebung" />
      <br/><span data-ttu-id="28f49-111">Phase 2: Setup</a></span><span class="sxs-lookup"><span data-stu-id="28f49-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Konfigurieren der einzelnen Microsoft Threat Protection-Pfeiler für Ihre Microsoft Threat Protection-Test Umgebungsumgebung und Onboard-Endpunkte" />
      <br/><span data-ttu-id="28f49-113">Phase 3: Konfigurieren von & Onboard</a></span><span class="sxs-lookup"><span data-stu-id="28f49-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="28f49-114">Sie befinden sich derzeit in der Konfigurationsphase.</span><span class="sxs-lookup"><span data-stu-id="28f49-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="28f49-115">Die Vorbereitung ist für eine erfolgreiche Bereitstellung entscheidend.</span><span class="sxs-lookup"><span data-stu-id="28f49-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="28f49-116">In diesem Artikel werden Sie auf die Punkte hingewiesen, die Sie bei der Vorbereitung der Bereitstellung von Microsoft Defender ATP berücksichtigen müssen.</span><span class="sxs-lookup"><span data-stu-id="28f49-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="28f49-117">Microsoft Threat Protection-Säulen</span><span class="sxs-lookup"><span data-stu-id="28f49-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="28f49-118">Microsoft Threat Protection besteht aus vier Pfeilern.</span><span class="sxs-lookup"><span data-stu-id="28f49-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="28f49-119">Auch wenn ein Pfeiler bereits einen Mehrwert für die Sicherheit ihrer Netzwerkorganisation bieten kann, bietet die Aktivierung der vier Microsoft-Bedrohungsschutz-Pfeiler Ihrer Organisation den größten Nutzen.</span><span class="sxs-lookup"><span data-stu-id="28f49-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![Bild of_page](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="28f49-121">In diesem Abschnitt erhalten Sie Informationen zu configure:</span><span class="sxs-lookup"><span data-stu-id="28f49-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="28f49-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="28f49-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="28f49-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="28f49-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="28f49-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="28f49-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="28f49-125">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="28f49-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="28f49-126">Konfigurieren Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="28f49-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="28f49-127">Überspringen Sie diesen Schritt, wenn Sie bereits Office 365 Advanced Threat Protection aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="28f49-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="28f49-128">Es gibt ein PowerShell-Modul namens *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (Orca)* , mit dem einige dieser Einstellungen ermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="28f49-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="28f49-129">Wenn Sie als Administrator in Ihrem Mandanten ausgeführt wird, hilft Get-ORCAReport bei der Erstellung einer Bewertung der Anti-Spam-, Anti-Phishing-und anderer Nachrichten Hygiene Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="28f49-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="28f49-130">Sie können dieses Modul aus https://www.powershellgallery.com/packages/ORCA/herunterladen.</span><span class="sxs-lookup"><span data-stu-id="28f49-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="28f49-131">Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat Management** > **Policy**.</span><span class="sxs-lookup"><span data-stu-id="28f49-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="28f49-132">![Bild of_page](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-132">![Image of_page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="28f49-133">Klicken Sie auf **ATP-Anti-Phishing**, wählen Sie **Create** aus, und geben Sie den Richtliniennamen und die Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="28f49-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="28f49-134">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="28f49-134">Click **Next**.</span></span>
<span data-ttu-id="28f49-135">![Bild of_page](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-135">![Image of_page](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="28f49-136">Bearbeiten Sie Ihre erweiterte ATP-Richtlinie zum Schutz vor Phishing.</span><span class="sxs-lookup"><span data-stu-id="28f49-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="28f49-137">Ändern Sie den **Advanced Phishing Threshold** in **2-aggressive**.</span><span class="sxs-lookup"><span data-stu-id="28f49-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="28f49-138">Klicken Sie auf das Dropdownmenü **Bedingung hinzufügen** , und wählen Sie Ihre Domäne (n) als Empfängerdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="28f49-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="28f49-139">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="28f49-139">Click **Next**.</span></span>
<span data-ttu-id="28f49-140">![Bild of_page](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-140">![Image of_page](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="28f49-141">Überprüfen Sie Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="28f49-141">Review your settings.</span></span> <span data-ttu-id="28f49-142">Klicken Sie zum bestätigen auf **Diese Richtlinie erstellen** .</span><span class="sxs-lookup"><span data-stu-id="28f49-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="28f49-143">![Bild of_page](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-143">![Image of_page](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="28f49-144">Wählen Sie **ATP-sichere Anlagen** aus, und aktivieren Sie die Option **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="28f49-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="28f49-145">![Bild of_page](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-145">![Image of_page](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="28f49-146">Klicken Sie auf das Symbol +, um eine neue Richtlinie für sichere Anlagen zu erstellen und diese als Empfängerdomäne auf Ihre Domänen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="28f49-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="28f49-147">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="28f49-147">Click **Save**.</span></span>
<span data-ttu-id="28f49-148">![Bild of_page](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-148">![Image of_page](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="28f49-149">Wählen Sie als nächstes die Richtlinie **ATP-sichere Links** aus, und klicken Sie dann auf das Bleistiftsymbol, um die Standardrichtlinie zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="28f49-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="28f49-150">Stellen Sie sicher, dass die Option nicht **nachverfolgen, wenn Benutzer auf sichere Links klicken** ausgewählt ist, während die restlichen Optionen ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="28f49-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="28f49-151">Details finden Sie unter [Einstellungen für sichere Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) .</span><span class="sxs-lookup"><span data-stu-id="28f49-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="28f49-152">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="28f49-152">Click **Save**.</span></span> 
<span data-ttu-id="28f49-153">![Bild of_page](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-153">![Image of_page](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="28f49-154">Wählen Sie als nächstes die **Antischadsoftware-** Richtlinie aus, wählen Sie die Standardeinstellung aus, und wählen Sie das Bleistiftsymbol aus.</span><span class="sxs-lookup"><span data-stu-id="28f49-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="28f49-155">Klicken Sie auf **Einstellungen** und dann auf **Ja, und verwenden Sie den standardmäßigen Benachrichtigungstext** , um die **Malware Erkennungs Antwort**zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="28f49-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="28f49-156">Aktivieren Sie den **Filter allgemeine Anlagentypen** .</span><span class="sxs-lookup"><span data-stu-id="28f49-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="28f49-157">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="28f49-157">Click **Save**.</span></span>
<br><span data-ttu-id="28f49-158">![Bild of_page](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-158">![Image of_page](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="28f49-159">Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > -**Such** > **Überwachungsprotokoll-Suche** , und aktivieren Sie die Überwachung.</span><span class="sxs-lookup"><span data-stu-id="28f49-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="28f49-160">![Bild of_page](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-160">![Image of_page](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="28f49-161">Integrieren Sie Office 365 ATP mit Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="28f49-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="28f49-162">Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat Management** > **Explorer** , und wählen Sie **WDATP-Einstellungen** in der oberen rechten Ecke des Bildschirms aus.</span><span class="sxs-lookup"><span data-stu-id="28f49-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="28f49-163">Aktivieren Sie im Dialogfeld Microsoft Defender ATP Connection die Option **Connect to Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="28f49-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="28f49-164">![Bild of_page](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-164">![Image of_page](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="28f49-165">Konfigurieren von Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="28f49-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="28f49-166">Überspringen Sie diesen Schritt, wenn Sie Azure Advanced Threat Protection bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="28f49-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="28f49-167">Navigieren Sie zum [Microsoft 365 Security Center](https://security.microsoft.com/info) > wählen Sie **Weitere Ressourcen** > **Azure Advanced Threat Protection**aus.</span><span class="sxs-lookup"><span data-stu-id="28f49-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="28f49-168">![Bild of_page](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-168">![Image of_page](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="28f49-169">Klicken Sie auf **Erstellen** , um den Azure Advanced Threat Protection-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="28f49-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="28f49-170">![Bild of_page](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-170">![Image of_page](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="28f49-171">Wählen Sie **Geben Sie einen Benutzernamen und ein Kennwort ein, um eine Verbindung mit Ihrer Active Directory Gesamtstruktur herzustellen**.</span><span class="sxs-lookup"><span data-stu-id="28f49-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="28f49-172">![Bild of_page](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-172">![Image of_page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="28f49-173">Geben Sie Ihre Active Directory lokalen Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="28f49-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="28f49-174">Hierbei kann es sich um ein beliebiges Benutzerkonto handeln, das über Lesezugriff auf Active Directory verfügt.</span><span class="sxs-lookup"><span data-stu-id="28f49-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="28f49-175">![Bild of_page](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-175">![Image of_page](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="28f49-176">Wählen Sie als nächstes **Download Sensor Setup** aus, und übertragen Sie die Datei auf Ihren Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="28f49-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="28f49-177">![Bild of_page](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-177">![Image of_page](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="28f49-178">Führen Sie das Azure ATP-Sensor Setup aus, und folgen Sie dem Assistenten.</span><span class="sxs-lookup"><span data-stu-id="28f49-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="28f49-179">![Bild of_page](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-179">![Image of_page](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="28f49-180">Klicken Sie im Sensor Bereitstellungs auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="28f49-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="28f49-181">![Bild of_page](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-181">![Image of_page](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="28f49-182">Kopieren Sie die Zugriffstaste so, wie Sie Sie als nächstes im Assistenten eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="28f49-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="28f49-183">![Bild of_page](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-183">![Image of_page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="28f49-184">Kopieren Sie den Zugriffsschlüssel in den Assistenten, und klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="28f49-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="28f49-185">![Bild of_page](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-185">![Image of_page](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="28f49-186">Herzlichen Glückwunsch, Sie haben Azure Advanced Threat Protection auf Ihrem Domänencontroller erfolgreich konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="28f49-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="28f49-187">![Bild of_page](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-187">![Image of_page](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="28f49-188">Wählen Sie im Abschnitt [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) -Einstellungen die Option **Windows Defender ATP**aus, und aktivieren Sie dann die Umschaltfläche.</span><span class="sxs-lookup"><span data-stu-id="28f49-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="28f49-189">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="28f49-189">Click **Save**.</span></span> 
<span data-ttu-id="28f49-190">![Bild of_page](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-190">![Image of_page](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="28f49-191">Windows Defender ATP wurde als Microsoft Defender ATP umbenannt.</span><span class="sxs-lookup"><span data-stu-id="28f49-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="28f49-192">Das neubranding von Änderungen in allen Portalen wird für die Konsistenz eingeführt.</span><span class="sxs-lookup"><span data-stu-id="28f49-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="28f49-193">Konfigurieren der Microsoft Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="28f49-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="28f49-194">Überspringen Sie diesen Schritt, wenn Sie Microsoft Cloud App Security bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="28f49-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="28f49-195">Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info) > **Weitere Ressourcen** > **Microsoft Cloud-App-Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="28f49-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="28f49-196">![Bild of_page](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-196">![Image of_page](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="28f49-197">Wählen Sie an der Informations Aufforderung zur Integration von Azure ATP die Option **Azure ATP-Datenintegration aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="28f49-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="28f49-198">![Bild of_page](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-198">![Image of_page](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="28f49-199">Wenn diese Eingabeaufforderung nicht angezeigt wird, kann dies bedeuten, dass Ihre Azure ATP-Datenintegration bereits aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="28f49-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="28f49-200">Wenn Sie sich jedoch nicht sicher sind, wenden Sie sich an Ihren IT-Administrator, um dies zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="28f49-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="28f49-201">Wechseln Sie zu **Einstellungen**, aktivieren Sie die **Azure ATP-Integration** , und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="28f49-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="28f49-202">![Bild of_page](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-202">![Image of_page](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="28f49-203">Für neue Azure ATP-Instanzen wird diese Integrations Toggle automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="28f49-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="28f49-204">Vergewissern Sie sich, dass Ihre Azure ATP-Integration aktiviert wurde, bevor Sie mit dem nächsten Schritt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="28f49-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="28f49-205">Wählen Sie unter den Einstellungen für die Cloud-Ermittlung die Option **Microsoft Defender ATP-Integration**aus, und aktivieren Sie dann die Integration.</span><span class="sxs-lookup"><span data-stu-id="28f49-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="28f49-206">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="28f49-206">Click **Save**.</span></span>
<span data-ttu-id="28f49-207">![Bild of_page](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-207">![Image of_page](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="28f49-208">Wählen Sie unter Einstellungen für die Cloud-Ermittlung die Option **Benutzer Bereicherung**aus, und aktivieren Sie dann die Integration in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="28f49-208">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="28f49-209">![Bild of_page](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-209">![Image of_page](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="28f49-210">Konfigurieren von Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="28f49-210">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="28f49-211">Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender Advanced Threat Protection bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="28f49-211">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="28f49-212">Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info) > **Weitere Ressourcen** > **Microsoft Defender Security Center**.</span><span class="sxs-lookup"><span data-stu-id="28f49-212">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="28f49-213">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="28f49-213">Click **Open**.</span></span>
<br><span data-ttu-id="28f49-214">![Bild of_page](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-214">![Image of_page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="28f49-215">Führen Sie den Microsoft Defender Advanced Threat Protection-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="28f49-215">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="28f49-216">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="28f49-216">Click **Next**.</span></span> 
<br><span data-ttu-id="28f49-217">![Bild of_page](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-217">![Image of_page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="28f49-218">Wählen Sie basierend auf dem bevorzugten Datenspeicherort, der Datenaufbewahrungsrichtlinie, der Organisationsgröße und dem Opt-in für Vorschau Features aus.</span><span class="sxs-lookup"><span data-stu-id="28f49-218">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="28f49-219">![Bild of_page](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-219">![Image of_page](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="28f49-220">Einige Einstellungen wie der Datenspeicherort können anschließend nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="28f49-220">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="28f49-221">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="28f49-221">Click **Next**.</span></span> 

4. <span data-ttu-id="28f49-222">Klicken Sie auf **weiter** , und Sie wird Ihren Microsoft Defender ATP-Mandanten anbieten.</span><span class="sxs-lookup"><span data-stu-id="28f49-222">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="28f49-223">![Bild of_page](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-223">![Image of_page](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="28f49-224">An Bord ihrer Endpunkte durch Gruppenrichtlinien, Microsoft Endpoint Manager oder durch Ausführen eines lokalen Skripts für Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="28f49-224">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="28f49-225">Zur Vereinfachung verwendet dieses Handbuch das lokale Skript.</span><span class="sxs-lookup"><span data-stu-id="28f49-225">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="28f49-226">Klicken Sie auf **Paket herunterladen** , und kopieren Sie das Onboarding-Skript an Ihre (n) Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="28f49-226">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="28f49-227">![Bild of_page](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-227">![Image of_page](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="28f49-228">Führen Sie auf ihrem Endpunkt das Onboarding-Skript als Administrator aus, und wählen Sie Y aus.</span><span class="sxs-lookup"><span data-stu-id="28f49-228">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="28f49-229">![Bild of_page](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-229">![Image of_page](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="28f49-230">Herzlichen Glückwunsch, Sie haben ihren ersten Endpunkt an Bord.</span><span class="sxs-lookup"><span data-stu-id="28f49-230">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![Bild of_page](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="28f49-232">Copy-fügen Sie den Erkennungstest aus dem Microsoft Defender ATP-Assistenten ein.</span><span class="sxs-lookup"><span data-stu-id="28f49-232">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="28f49-233">![Bild of_page](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-233">![Image of_page](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="28f49-234">Kopieren Sie das PowerShell-Skript an eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="28f49-234">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="28f49-235">![Bild of_page](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-235">![Image of_page](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="28f49-236">Wählen Sie im Assistenten die Option **mit Microsoft Defender ATP starten** aus.</span><span class="sxs-lookup"><span data-stu-id="28f49-236">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="28f49-237">![Bild of_page](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-237">![Image of_page](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="28f49-238">Besuchen Sie das [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="28f49-238">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="28f49-239">Wechseln Sie zu **Einstellungen** , und wählen Sie dann **Erweiterte Funktionen**aus.</span><span class="sxs-lookup"><span data-stu-id="28f49-239">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="28f49-240">![Bild of_page](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-240">![Image of_page](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="28f49-241">Aktivieren Sie die Integration in **Azure Advanced Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="28f49-241">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="28f49-242">![Bild of_page](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-242">![Image of_page](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="28f49-243">Aktivieren Sie die Integration mit **Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="28f49-243">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="28f49-244">![Bild of_page](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-244">![Image of_page](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="28f49-245">Aktivieren Sie die Integration in **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="28f49-245">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="28f49-246">![Bild of_page](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-246">![Image of_page](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="28f49-247">Scrollen Sie nach unten, und klicken Sie auf **Einstellungen speichern** , um die neuen Integrationen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="28f49-247">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="28f49-248">![Bild of_page](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="28f49-248">![Image of_page](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="next-steps"></a><span data-ttu-id="28f49-249">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="28f49-249">Next steps</span></span>
<span data-ttu-id="28f49-250">[Aktivieren Sie Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) , und [generieren Sie dann eine Testwarnung](generate-test-alert.md).</span><span class="sxs-lookup"><span data-stu-id="28f49-250">[Turn on Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) and then [generate a test alert](generate-test-alert.md).</span></span>
