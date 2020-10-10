---
title: Konfigurieren von Microsoft Threat Protection-Säulen für die Test Labor-oder Pilotumgebung
description: Konfigurieren Sie Microsoft Threat Protection-Säulen wie Office 365 ATP, Azure ATP, Microsoft Cloud App Security und Microsoft Defender ATP für Ihre Test Labor-oder Pilotumgebung.
keywords: Konfigurieren von Microsoft Threat Protection-Testversion, Microsoft Threat Protection-Testkonfiguration, Microsoft Threat Protection-Pilotprojekt konfigurieren, Microsoft Threat Protection-Säulen konfigurieren, Microsoft Threat Protection-Säulen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 7e9060c804fcdb8445c8d833d8a43dc90a738b04
ms.sourcegitcommit: a83acd5b9eeefd2e20e5bac916fe29d09fb53de9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2020
ms.locfileid: "48418157"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="c34cf-104">Konfigurieren von Microsoft Threat Protection-Säulen für Ihre Test Labor-oder Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="c34cf-104">Configure Microsoft Threat Protection pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c34cf-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c34cf-105">**Applies to:**</span></span>
- <span data-ttu-id="c34cf-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c34cf-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="c34cf-107">Das Erstellen eines Microsoft Threat Protection-Testlabors oder einer Pilotumgebung und deren Bereitstellung ist ein dreistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="c34cf-107">Creating a Microsoft Threat Protection trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab or pilot environment" title="Vorbereiten Ihrer Testlabor-oder Pilotumgebung für den Microsoft Threat Protection-Test" />
      <br/><span data-ttu-id="c34cf-109">Phase 1: Vorbereiten </a></span><span class="sxs-lookup"><span data-stu-id="c34cf-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab or pilot environment" title="Einrichten Ihres Microsoft Threat Protection-Testlabors oder einer Pilotumgebung" />
      <br/><span data-ttu-id="c34cf-111">Phase 2: Setup </a></span><span class="sxs-lookup"><span data-stu-id="c34cf-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="Konfigurieren der einzelnen Microsoft Threat Protection-Pfeiler für Ihr Microsoft Threat Protection-Test Labor oder Ihre Pilotumgebung sowie Onboard-Endpunkte" />
      <br/><span data-ttu-id="c34cf-113">Phase 3: Konfigurieren von & Onboard </a></span><span class="sxs-lookup"><span data-stu-id="c34cf-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>
  </tr>
</table>

<span data-ttu-id="c34cf-114">Sie befinden sich derzeit in der Konfigurationsphase.</span><span class="sxs-lookup"><span data-stu-id="c34cf-114">You're currently in the configuration phase.</span></span>


<span data-ttu-id="c34cf-115">Die Vorbereitung ist für eine erfolgreiche Bereitstellung entscheidend.</span><span class="sxs-lookup"><span data-stu-id="c34cf-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="c34cf-116">In diesem Artikel werden Sie auf die Punkte hingewiesen, die Sie bei der Vorbereitung der Bereitstellung von Microsoft Defender ATP berücksichtigen müssen.</span><span class="sxs-lookup"><span data-stu-id="c34cf-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="c34cf-117">Microsoft Threat Protection-Säulen</span><span class="sxs-lookup"><span data-stu-id="c34cf-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="c34cf-118">Microsoft Threat Protection besteht aus vier Pfeilern.</span><span class="sxs-lookup"><span data-stu-id="c34cf-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="c34cf-119">Auch wenn ein Pfeiler bereits einen Mehrwert für die Sicherheit ihrer Netzwerkorganisation bieten kann, bietet die Aktivierung der vier Microsoft-Bedrohungsschutz-Pfeiler Ihrer Organisation den größten Nutzen.</span><span class="sxs-lookup"><span data-stu-id="c34cf-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![<span data-ttu-id="c34cf-120">Image of_Microsoft Threat Protection-Lösung für Benutzer, Azure Advanced Threat Protection, für Endpoint Microsoft Defender Advanced Threat Protection, für Cloud-apps, Microsoft Cloud App Security und für Daten, Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c34cf-120">Image of_Microsoft Threat Protection solution for users, Azure Advanced Threat Protection, for endpoints Microsoft Defender Advanced Threat Protection, for cloud apps, Microsoft Cloud App Security, and for data, Office 365 Advanced Threat Protection</span></span>  ](../../media/mtp-eval-31.png)

<span data-ttu-id="c34cf-121">In diesem Abschnitt erhalten Sie Informationen zu configure:</span><span class="sxs-lookup"><span data-stu-id="c34cf-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="c34cf-122">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c34cf-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="c34cf-123">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c34cf-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="c34cf-124">Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c34cf-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="c34cf-125">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c34cf-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="c34cf-126">Konfigurieren Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c34cf-126">Configure Office 365 Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="c34cf-127">Überspringen Sie diesen Schritt, wenn Sie bereits Office 365 Advanced Threat Protection aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="c34cf-127">Skip this step if you've already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="c34cf-128">Es gibt ein PowerShell-Modul mit dem Namen *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (Orca)* , mit dem einige dieser Einstellungen ermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="c34cf-128">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="c34cf-129">Wenn Sie als Administrator in Ihrem Mandanten ausgeführt wird, hilft Get-ORCAReport bei der Erstellung einer Bewertung der Anti-Spam-, Anti-Phishing-und anderer Nachrichten Hygiene Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="c34cf-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="c34cf-130">Sie können dieses Modul aus herunterladen https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="c34cf-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="c34cf-131">Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 Security & Compliance Center Threat Management-Richtlinie (Seite)](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="c34cf-133">Klicken Sie auf **ATP-Anti-Phishing**, wählen Sie **Create** aus, und geben Sie den Richtliniennamen und die Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="c34cf-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="c34cf-134">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-134">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center-Richtlinie zur Anti-Phishing-Politik, auf der Sie Ihre Richtlinie benennen können](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="c34cf-136">Bearbeiten Sie Ihre erweiterte ATP-Richtlinie zum Schutz vor Phishing.</span><span class="sxs-lookup"><span data-stu-id="c34cf-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="c34cf-137">Ändern Sie den **Advanced Phishing Threshold** in **2-aggressive**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="c34cf-138">Klicken Sie auf das Dropdownmenü **Bedingung hinzufügen** , und wählen Sie Ihre Domäne (n) als Empfängerdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="c34cf-139">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-139">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center-Richtlinie zur Anti-Phishing-Politik, auf der Sie eine Bedingung für Ihre Anwendung hinzufügen können](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="c34cf-141">Überprüfen Sie Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="c34cf-141">Review your settings.</span></span> <span data-ttu-id="c34cf-142">Klicken Sie zum bestätigen auf **Diese Richtlinie erstellen** .</span><span class="sxs-lookup"><span data-stu-id="c34cf-142">Click **Create this policy** to confirm.</span></span> 

   ![Image of_Office 365 Security & Compliance Center-Richtlinie zur Anti-Phishing-Politik, auf der Sie Ihre Einstellungen überprüfen und auf die Schaltfläche Richtlinie erstellen klicken können](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="c34cf-144">Wählen Sie **ATP-sichere Anlagen** aus, und aktivieren Sie die Option **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="c34cf-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 Security & Compliance Center Seite, auf der Sie ATP für SharePoint, OneDrive und Microsoft Teams aktivieren können](../../media/mtp-eval-36.png)

6. <span data-ttu-id="c34cf-146">Klicken Sie auf das Symbol +, um eine neue Richtlinie für sichere Anlagen zu erstellen und diese als Empfängerdomäne auf Ihre Domänen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="c34cf-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="c34cf-147">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-147">Click **Save**.</span></span>

   ![Image of_Office 365 Security & Compliance Center-Seite, auf der Sie eine neue Richtlinie zum Erstellen einer neuen sicheren Anlage erstellen können](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="c34cf-149">Wählen Sie als nächstes die Richtlinie **ATP-sichere Links** aus, und klicken Sie dann auf das Bleistiftsymbol, um die Standardrichtlinie zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c34cf-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="c34cf-150">Stellen Sie sicher, dass die Option nicht **nachverfolgen, wenn Benutzer auf sichere Links klicken** ausgewählt ist, während die restlichen Optionen ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="c34cf-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="c34cf-151">Details finden Sie unter [Einstellungen für sichere Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) .</span><span class="sxs-lookup"><span data-stu-id="c34cf-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="c34cf-152">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-152">Click **Save**.</span></span> 

   ![Image of_Office 365 Security & Compliance Center Seite, die zeigt, dass die Option nicht nachverfolgt werden kann, wenn Benutzer auf sicher klicken nicht ausgewählt ist.](../../media/mtp-eval-38.png)

9. <span data-ttu-id="c34cf-154">Wählen Sie als nächstes die **Antischadsoftware-** Richtlinie aus, wählen Sie die Standardeinstellung aus, und wählen Sie das Bleistiftsymbol aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="c34cf-155">Klicken Sie auf **Einstellungen** und dann auf **Ja, und verwenden Sie den standardmäßigen Benachrichtigungstext** , um die **Malware Erkennungs Antwort**zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c34cf-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="c34cf-156">Aktivieren Sie den **Filter allgemeine Anlagentypen** .</span><span class="sxs-lookup"><span data-stu-id="c34cf-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="c34cf-157">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-157">Click **Save**.</span></span>

    ![Image of_Office 365 Security & Compliance Center Seite, die zeigt, dass die Malware Erkennungs Antwort mit Standardbenachrichtigung aktiviert ist und der Filter "allgemeine Anlagentypen" aktiviert ist.](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="c34cf-159">Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  -**Such**  >  **Überwachungsprotokoll-Suche** , und aktivieren Sie die Überwachung.</span><span class="sxs-lookup"><span data-stu-id="c34cf-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Image of_Office 365 Security & Compliance Center Seite, auf der Sie die Überwachungsprotokoll Suche aktivieren können](../../media/mtp-eval-40.png)

12. <span data-ttu-id="c34cf-161">Integrieren Sie Office 365 ATP mit Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="c34cf-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="c34cf-162">Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **Explorer** , und wählen Sie **WDATP-Einstellungen** in der oberen rechten Ecke des Bildschirms aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="c34cf-163">Aktivieren Sie im Dialogfeld Microsoft Defender ATP Connection die Option **Connect to Windows ATP**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>

    ![Image of_Office 365 Security & Compliance Center Seite, auf der Sie die ATP-Verbindung von Windows Defender aktivieren können](../../media/mtp-eval-41.png)

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="c34cf-165">Konfigurieren von Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c34cf-165">Configure Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="c34cf-166">Überspringen Sie diesen Schritt, wenn Sie Azure Advanced Threat Protection bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="c34cf-166">Skip this step if you've already enabled Azure Advanced Threat Protection</span></span>

1. <span data-ttu-id="c34cf-167">Navigieren Sie zum [Microsoft 365 Security Center](https://security.microsoft.com/info) > wählen Sie **Weitere Ressourcen**  >  **Azure Advanced Threat Protection**aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>

   ![Image of_Microsoft 365-Sicherheits Center Seite, auf der eine Option zum Öffnen von Azure Advanced Threat Protection verfügbar ist](../../media/mtp-eval-42.png)

2. <span data-ttu-id="c34cf-169">Klicken Sie auf **Erstellen** , um den Azure Advanced Threat Protection-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="c34cf-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 

   ![Seite "Image of_Azure Advanced Threat Protection", auf der Sie auf die Schaltfläche "erstellen" klicken sollten](../../media/mtp-eval-43.png)

3. <span data-ttu-id="c34cf-171">Wählen Sie **Geben Sie einen Benutzernamen und ein Kennwort ein, um eine Verbindung mit Ihrer Active Directory Gesamtstruktur herzustellen**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Willkommensseite für Image of_Azure Advanced Threat Protection](../../media/mtp-eval-44.png)

4. <span data-ttu-id="c34cf-173">Geben Sie Ihre Active Directory lokalen Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="c34cf-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="c34cf-174">Hierbei kann es sich um ein beliebiges Benutzerkonto handeln, das über Lesezugriff auf Active Directory verfügt.</span><span class="sxs-lookup"><span data-stu-id="c34cf-174">This can be any user account that has read access to Active Directory.</span></span>

   ![Image of_Azure Advanced Threat Protection-Verzeichnisdienst Seite, auf der Sie Ihre Anmeldeinformationen platzieren sollten](../../media/mtp-eval-45.png)

5. <span data-ttu-id="c34cf-176">Wählen Sie als nächstes **Download Sensor Setup** aus, und übertragen Sie die Datei auf Ihren Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="c34cf-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Image of_Azure Advanced Threat Protection-Seite, auf der Sie Download Sensor Setup auswählen können](../../media/mtp-eval-46.png)

6. <span data-ttu-id="c34cf-178">Führen Sie das Azure ATP-Sensor Setup aus, und folgen Sie dem Assistenten.</span><span class="sxs-lookup"><span data-stu-id="c34cf-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>

   ![Image of_Azure Advanced Threat Protection-Seite, auf der Sie auf Weiter klicken, um dem Azure ATP-Sensor-Assistenten zu entsprechen](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="c34cf-180">Klicken Sie im Sensor Bereitstellungs auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="c34cf-180">Click **Next** at the sensor deployment type.</span></span>

   ![Image of_Azure Advanced Threat Protection-Seite, auf der Sie auf Weiter klicken sollten, um zur nächsten Seite zu wechseln](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="c34cf-182">Kopieren Sie die Zugriffstaste, da Sie Sie als nächstes im Assistenten eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="c34cf-182">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Seite "Bild of_the Sensoren", auf der Sie die Zugriffstaste kopieren sollten, die Sie auf der nächsten Seite des Azure ATP-Sensor-Setup-Assistenten eingeben müssen](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="c34cf-184">Kopieren Sie den Zugriffsschlüssel in den Assistenten, und klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-184">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Image of_Azure Advanced Threat Protection Azure ATP-Sensor-Assistent-Seite, auf der Sie die Zugriffstaste eingeben und dann auf die Schaltfläche "installieren" klicken sollten](../../media/mtp-eval-50.png)

10. <span data-ttu-id="c34cf-186">Herzlichen Glückwunsch, Sie haben Azure Advanced Threat Protection erfolgreich auf Ihrem Domänencontroller konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="c34cf-186">Congratulations, you've successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>

    ![Image of_Azure Advanced Threat Protection Azure ATP-Sensor-Assistent-Installationsabschluss, in dem Sie auf die Schaltfläche Fertig stellen klicken sollten](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="c34cf-188">Wählen Sie im Abschnitt [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) -Einstellungen die Option **Windows Defender ATP**aus, und aktivieren Sie dann die Umschaltfläche.</span><span class="sxs-lookup"><span data-stu-id="c34cf-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn on the toggle.</span></span> <span data-ttu-id="c34cf-189">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-189">Click **Save**.</span></span> 

    ![Bild of_the Azure Azure ATP-Einstellungsseite, auf der Sie den Windows Defender ATP-Schalter aktivieren sollten](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="c34cf-191">Windows Defender ATP wurde als Microsoft Defender ATP umbenannt.</span><span class="sxs-lookup"><span data-stu-id="c34cf-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="c34cf-192">Das neubranding von Änderungen in allen Portalen wird für die Konsistenz eingeführt.</span><span class="sxs-lookup"><span data-stu-id="c34cf-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="c34cf-193">Konfigurieren der Microsoft Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c34cf-193">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="c34cf-194">Überspringen Sie diesen Schritt, wenn Sie Microsoft Cloud App Security bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="c34cf-194">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="c34cf-195">Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **Weitere Ressourcen**  >  **Microsoft Cloud-App-Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Image of_Microsoft 365-Sicherheits Center Seite, auf der Sie die Microsoft Cloud-App-Karte anzeigen und auf die Schaltfläche Öffnen klicken können](../../media/mtp-eval-53.png)

2. <span data-ttu-id="c34cf-197">Wählen Sie an der Informations Aufforderung zur Integration von Azure ATP die Option **Azure ATP-Datenintegration aktivieren**aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span>
  
   ![Bild of_the Informations Aufforderung zur Integration von Azure ATP, in der Sie den Link Azure ATP-Datenintegration aktivieren auswählen sollten](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="c34cf-199">Wenn diese Eingabeaufforderung nicht angezeigt wird, kann dies bedeuten, dass Ihre Azure ATP-Datenintegration bereits aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="c34cf-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="c34cf-200">Wenn Sie sich jedoch nicht sicher sind, wenden Sie sich an Ihren IT-Administrator, um dies zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="c34cf-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="c34cf-201">Wechseln Sie zu **Einstellungen**, aktivieren Sie die **Azure ATP Integration** Toggle, und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-201">Go to **Settings**, turn on the **Azure ATP integration** toggle, then click **Save**.</span></span> 

   ![Seite Image of_the Settings, auf der Sie die Azure ATP-Integration aktivieren und dann auf Speichern klicken.](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="c34cf-203">Für neue Azure ATP-Instanzen wird diese Integrations Toggle automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c34cf-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="c34cf-204">Vergewissern Sie sich, dass Ihre Azure ATP-Integration aktiviert wurde, bevor Sie mit dem nächsten Schritt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="c34cf-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="c34cf-205">Wählen Sie unter den Einstellungen für die Cloud-Ermittlung die Option **Microsoft Defender ATP-Integration**aus, und aktivieren Sie dann die Integration.</span><span class="sxs-lookup"><span data-stu-id="c34cf-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="c34cf-206">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-206">Click **Save**.</span></span>

   ![Image of_the Microsoft Defender ATP-Seite, auf der das Kontrollkästchen nicht sanktionierte apps blockieren unter Microsoft Defender ATP-Integration ausgewählt ist.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="c34cf-209">Wählen Sie unter Einstellungen für die Cloud-Ermittlung die Option **Benutzer Bereicherung**aus, und aktivieren Sie dann die Integration in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c34cf-209">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Bild des Abschnitts "Benutzer Anreicherung", in dem das Kontrollkästchen "ermittelte Benutzerbezeichner mit Azure Active Directory Benutzernamen erweitern" aktiviert ist](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="c34cf-211">Konfigurieren von Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c34cf-211">Configure Microsoft Defender Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="c34cf-212">Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender Advanced Threat Protection bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="c34cf-212">Skip this step if you've already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="c34cf-213">Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **Weitere Ressourcen**  >  **Microsoft Defender Security Center**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="c34cf-214">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-214">Click **Open**.</span></span>

   ![Sicherheitscenter "Image of_Microsoft Defender" auf der Seite "Microsoft 365 Security Center"](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="c34cf-216">Führen Sie den Microsoft Defender Advanced Threat Protection-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-216">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="c34cf-217">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-217">Click **Next**.</span></span> 

   ![Seite "Image of_the Microsoft Defender Security Center-Willkommens Assistent"](../../media/mtp-eval-59.png)

3. <span data-ttu-id="c34cf-219">Wählen Sie basierend auf dem bevorzugten Datenspeicherort, der Datenaufbewahrungsrichtlinie, der Organisationsgröße und dem Opt-in für Vorschau Features aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Image of_the Page, um das Datenspeicher Land, die Aufbewahrungsrichtlinie und die Organisationsgröße auszuwählen.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="c34cf-222">Einige Einstellungen wie der Datenspeicherort können anschließend nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="c34cf-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="c34cf-223">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-223">Click **Next**.</span></span> 

4. <span data-ttu-id="c34cf-224">Klicken Sie auf **weiter** , und Sie wird Ihren Microsoft Defender ATP-Mandanten anbieten.</span><span class="sxs-lookup"><span data-stu-id="c34cf-224">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>

   ![Bild of_the Seite, die Sie anfordert, indem Sie auf die Schaltfläche Weiter klicken, um Ihre Cloud-Instanz zu erstellen](../../media/mtp-eval-61.png)

5. <span data-ttu-id="c34cf-226">An Bord ihrer Endpunkte durch Gruppenrichtlinien, Microsoft Endpoint Manager oder durch Ausführen eines lokalen Skripts für Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="c34cf-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="c34cf-227">Zur Vereinfachung verwendet dieses Handbuch das lokale Skript.</span><span class="sxs-lookup"><span data-stu-id="c34cf-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="c34cf-228">Klicken Sie auf **Paket herunterladen** , und kopieren Sie das Onboarding-Skript an Ihre (n) Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="c34cf-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Image of_page Sie auf die Schaltfläche Paket herunterladen klicken, um das Onboarding-Skript auf ihren Endpunkt oder ihre Endpunkte zu kopieren.](../../media/mtp-eval-62.png)

7. <span data-ttu-id="c34cf-230">Führen Sie auf ihrem Endpunkt das Onboarding-Skript als Administrator aus, und wählen Sie Y aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Image of_the CommandLine, in der Sie das Onboarding-Skript ausführen, und wählen Sie Y, um fortzufahren.](../../media/mtp-eval-63.png)

8. <span data-ttu-id="c34cf-232">Herzlichen Glückwunsch, Sie haben ihren ersten Endpunkt an Bord.</span><span class="sxs-lookup"><span data-stu-id="c34cf-232">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Image of_the CommandLine, wo Sie die Bestätigung erhalten, dass Sie Ihren ersten Endpunkt an Bord haben.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="c34cf-235">Copy-fügen Sie den Erkennungstest aus dem Microsoft Defender ATP-Assistenten ein.</span><span class="sxs-lookup"><span data-stu-id="c34cf-235">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>

   ![Image of_the führen Sie einen Erkennungstest Schritt aus, in dem Sie auf Kopieren klicken sollten, um das Erkennungstest Skript zu kopieren, das Sie an der Eingabeaufforderung einfügen sollten.](../../media/mtp-eval-65.png)

10. <span data-ttu-id="c34cf-237">Kopieren Sie das PowerShell-Skript an eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Bild of_command Aufforderung, bei der das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten kopiert und ausgeführt wird.](../../media/mtp-eval-66.png)

11. <span data-ttu-id="c34cf-239">Wählen Sie im Assistenten die Option **mit Microsoft Defender ATP starten** aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-239">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>

    ![Bestätigungsaufforderung für Bild of_the aus dem Assistenten, auf der Sie mit Microsoft Defender ATP beginnen sollten](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="c34cf-241">Besuchen Sie das [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="c34cf-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="c34cf-242">Wechseln Sie zu **Einstellungen** , und wählen Sie dann **Erweiterte Funktionen**aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-242">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Image of_Microsoft Defender-Sicherheits Center-Einstellungsmenü, in dem Sie erweiterte Funktionen auswählen sollten](../../media/mtp-eval-68.png)

13. <span data-ttu-id="c34cf-244">Aktivieren Sie die Integration in **Azure Advanced Threat Protection**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-244">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  

    ![Image of_Microsoft Defender Security Center erweiterte Funktionen, Azure Advanced Threat Protection Option Umschaltfläche, die Sie aktivieren müssen](../../media/mtp-eval-69.png)

14. <span data-ttu-id="c34cf-246">Aktivieren Sie die Integration mit **Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Erweiterte Features für Image of_Microsoft Defender Security Center, Office 365 Option Toggle für Threat Intelligence, die Sie aktivieren müssen](../../media/mtp-eval-70.png)

15. <span data-ttu-id="c34cf-248">Aktivieren Sie die Integration in **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="c34cf-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center erweiterte Funktionen, Microsoft Cloud App-Sicherheitsoption Umschaltfläche, die Sie aktivieren müssen](../../media/mtp-eval-71.png)

16. <span data-ttu-id="c34cf-250">Scrollen Sie nach unten, und klicken Sie auf **Einstellungen speichern** , um die neuen Integrationen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="c34cf-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Schaltfläche "Bild of_Save Einstellungen", auf die Sie klicken müssen](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-threat-protection-service"></a><span data-ttu-id="c34cf-252">Microsoft Thread Protection-Dienst starten</span><span class="sxs-lookup"><span data-stu-id="c34cf-252">Start the Microsoft Threat Protection service</span></span>

>[!NOTE]
><span data-ttu-id="c34cf-253">Ab dem 1. Juni 2020 Microsoft Threat Protection-Features für alle berechtigten Mandanten automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="c34cf-253">Starting June 1, 2020, Microsoft automatically enables Microsoft Threat Protection features for all eligible tenants.</span></span> <span data-ttu-id="c34cf-254">Weitere Informationen finden Sie [in diesem Artikel Microsoft Tech Community on License Berechtigung](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) .</span><span class="sxs-lookup"><span data-stu-id="c34cf-254">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="c34cf-255">Wechseln Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="c34cf-255">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="c34cf-256">Navigieren Sie zu **Einstellungen** , und wählen Sie dann **Microsoft Threat Protection**aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-256">Navigate to **Settings** and then select **Microsoft Threat Protection**.</span></span>

![<span data-ttu-id="c34cf-257">Screenshot der Option "Image of_Microsoft Threat Protection" auf der Seite "Microsoft 365 Security Center Settings"</span><span class="sxs-lookup"><span data-stu-id="c34cf-257">Image of_Microsoft Threat Protection option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="c34cf-258">Eine umfassendere Anleitung finden Sie unter [Aktivieren von Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="c34cf-258">For a more comprehensive guidance, see [Turn on Microsoft Threat Protection](mtp-enable.md).</span></span> 

<span data-ttu-id="c34cf-259">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="c34cf-259">Congratulations!</span></span> <span data-ttu-id="c34cf-260">Sie haben soeben Ihr Microsoft Threat Protection-Test Labor oder Ihre Pilotumgebung erstellt.</span><span class="sxs-lookup"><span data-stu-id="c34cf-260">You've just created your Microsoft Threat Protection trial lab or pilot environment!</span></span> <span data-ttu-id="c34cf-261">Jetzt können Sie sich mit der Microsoft Threat Protection-Benutzeroberfläche vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="c34cf-261">Now you can familiarize yourself with the Microsoft Threat Protection user interface!</span></span> <span data-ttu-id="c34cf-262">Erfahren Sie, was Sie im folgenden interaktiven Leitfaden für Microsoft Threat Protection erfahren und wie Sie die einzelnen Dashboards für Ihre täglichen Aufgaben im Zusammenarbeit mit dem Sicherheitsdienst verwenden können.</span><span class="sxs-lookup"><span data-stu-id="c34cf-262">See what you can learn from the following Microsoft Threat Protection interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="c34cf-263">Als nächstes können Sie einen Angriff simulieren und sehen, wie die produktübergreifenden Funktionen erkennen, Warnungen erstellen und automatisch auf einen Datei übergreifenden Angriff auf einen Endpunkt reagieren.</span><span class="sxs-lookup"><span data-stu-id="c34cf-263">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="c34cf-264">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="c34cf-264">Next step</span></span>
|<span data-ttu-id="c34cf-265">![Angriffs Simulationsphase](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="c34cf-265">![Attack simulation phase](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="c34cf-266">Angriffs Simulationsphase</span><span class="sxs-lookup"><span data-stu-id="c34cf-266">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="c34cf-267">Führen Sie die Angriffssimulation für Ihre Microsoft Threat Protection-Pilotumgebung aus.</span><span class="sxs-lookup"><span data-stu-id="c34cf-267">Run the attack simulation for your Microsoft Threat Protection pilot environment.</span></span>
|:-------|:-----|
