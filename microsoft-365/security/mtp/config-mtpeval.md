---
title: Konfigurieren von Microsoft 365 Defender-Säulen für die Test Labor-oder Pilotumgebung
description: Konfigurieren Sie Microsoft 365 Defender-Säulen wie Microsoft Defender für Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security und Microsoft Defender for Endpoint für Ihre Test Labor-oder Pilotumgebung.
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
ms.openlocfilehash: 240ffd7ec8d46da33c43ec2f9cb50cf59c89f11b
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131297"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="ae50f-104">Konfigurieren von Microsoft 365 Defender-Säulen für Ihre Test Labor-oder Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="ae50f-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ae50f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ae50f-105">**Applies to:**</span></span>
- <span data-ttu-id="ae50f-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ae50f-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="ae50f-107">Das Erstellen eines Microsoft 365 Defender-Testlabors oder einer Pilotumgebung und deren Bereitstellung ist ein dreistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="ae50f-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="ae50f-108">[![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="ae50f-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="ae50f-109">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="ae50f-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |<span data-ttu-id="ae50f-110">[![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="ae50f-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-mtpeval.md)</span></span><br/>[<span data-ttu-id="ae50f-111">Phase 2: Einrichten</span><span class="sxs-lookup"><span data-stu-id="ae50f-111">Phase 2: Set up</span></span>](setup-mtpeval.md) |![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="ae50f-113">Phase 3: Onboard</span><span class="sxs-lookup"><span data-stu-id="ae50f-113">Phase 3: Onboard</span></span> | <span data-ttu-id="ae50f-114">[![Zurück zu Pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="ae50f-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="ae50f-115">Zurück zu Pilot Textbuch</span><span class="sxs-lookup"><span data-stu-id="ae50f-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="ae50f-116">*Sie sind hier!*</span><span class="sxs-lookup"><span data-stu-id="ae50f-116">*You are here!*</span></span> | |

<span data-ttu-id="ae50f-117">Sie befinden sich derzeit in der Konfigurationsphase.</span><span class="sxs-lookup"><span data-stu-id="ae50f-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="ae50f-118">Die Vorbereitung ist für eine erfolgreiche Bereitstellung entscheidend.</span><span class="sxs-lookup"><span data-stu-id="ae50f-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="ae50f-119">In diesem Artikel werden Sie mit den Punkten geführt, die Sie bei der Vorbereitung der Bereitstellung von Microsoft Defender für Endpoint berücksichtigen müssen.</span><span class="sxs-lookup"><span data-stu-id="ae50f-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="ae50f-120">Microsoft 365 Defender-Säulen</span><span class="sxs-lookup"><span data-stu-id="ae50f-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="ae50f-121">Microsoft 365 Defender besteht aus vier Pfeilern.</span><span class="sxs-lookup"><span data-stu-id="ae50f-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="ae50f-122">Auch wenn ein Pfeiler bereits einen Mehrwert für die Sicherheit ihrer Netzwerkorganisation bieten kann, bietet die Aktivierung der vier Microsoft 365 Defender-Säulen Ihrem Unternehmen den größten Nutzen.</span><span class="sxs-lookup"><span data-stu-id="ae50f-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Image of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte von Microsoft Defender für Endpoint, für Cloud-apps, Microsoft Cloud-App-Sicherheit und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="ae50f-124">In diesem Abschnitt erhalten Sie Informationen zu configure:</span><span class="sxs-lookup"><span data-stu-id="ae50f-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="ae50f-125">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="ae50f-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="ae50f-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="ae50f-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="ae50f-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="ae50f-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="ae50f-128">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ae50f-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="ae50f-129">Konfigurieren von Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="ae50f-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="ae50f-130">Überspringen Sie diesen Schritt, wenn Sie Defender bereits für Office 365 aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="ae50f-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="ae50f-131">Es gibt ein PowerShell-Modul mit dem Namen *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (Orca)* , mit dem einige dieser Einstellungen ermittelt werden können.</span><span class="sxs-lookup"><span data-stu-id="ae50f-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="ae50f-132">Wenn Sie als Administrator in Ihrem Mandanten ausgeführt wird, hilft Get-ORCAReport bei der Erstellung einer Bewertung der Anti-Spam-, Anti-Phishing-und anderer Nachrichten Hygiene Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ae50f-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="ae50f-133">Sie können dieses Modul aus herunterladen https://www.powershellgallery.com/packages/ORCA/ .</span><span class="sxs-lookup"><span data-stu-id="ae50f-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="ae50f-134">Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 Security & Compliance Center Threat Management-Richtlinie (Seite)](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="ae50f-136">Klicken Sie auf **Anti-Phishing**, wählen Sie **Create** aus, und geben Sie den Richtliniennamen und die Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="ae50f-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="ae50f-137">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-137">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center-Richtlinie zur Anti-Phishing-Politik, auf der Sie Ihre Richtlinie benennen können](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="ae50f-139">Bearbeiten Sie die erweiterte Richtlinie zum Schutz vor Phishing in Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="ae50f-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="ae50f-140">Ändern Sie den **Advanced Phishing Threshold** in **2-aggressive**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="ae50f-141">Klicken Sie auf das Dropdownmenü **Bedingung hinzufügen** , und wählen Sie Ihre Domäne (n) als Empfängerdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="ae50f-142">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-142">Click **Next**.</span></span>

   ![Image of_Office 365 Security & Compliance Center-Richtlinie zur Anti-Phishing-Politik, auf der Sie eine Bedingung für Ihre Anwendung hinzufügen können](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="ae50f-144">Überprüfen Sie Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="ae50f-144">Review your settings.</span></span> <span data-ttu-id="ae50f-145">Klicken Sie zum bestätigen auf **Diese Richtlinie erstellen** .</span><span class="sxs-lookup"><span data-stu-id="ae50f-145">Click **Create this policy** to confirm.</span></span> 

   ![Image of_Office 365 Security & Compliance Center-Richtlinie zur Anti-Phishing-Politik, auf der Sie Ihre Einstellungen überprüfen und auf die Schaltfläche Richtlinie erstellen klicken können](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="ae50f-147">Wählen Sie **sichere Anlagen** aus, und aktivieren Sie die Option **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren** .</span><span class="sxs-lookup"><span data-stu-id="ae50f-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 Security & Compliance Center Seite, auf der Sie ATP für SharePoint, OneDrive und Microsoft Teams aktivieren können](../../media/mtp-eval-36.png)

6. <span data-ttu-id="ae50f-149">Klicken Sie auf das Symbol +, um eine neue Richtlinie für sichere Anlagen zu erstellen und diese als Empfängerdomäne auf Ihre Domänen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="ae50f-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="ae50f-150">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-150">Click **Save**.</span></span>

   ![Image of_Office 365 Security & Compliance Center-Seite, auf der Sie eine neue Richtlinie zum Erstellen einer neuen sicheren Anlage erstellen können](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="ae50f-152">Wählen Sie als nächstes die Richtlinie für **sichere Links** aus, und klicken Sie dann auf das Bleistiftsymbol, um die Standardrichtlinie zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="ae50f-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="ae50f-153">Stellen Sie sicher, dass die Option nicht **nachverfolgen, wenn Benutzer auf sichere Links klicken** ausgewählt ist, während die restlichen Optionen ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="ae50f-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="ae50f-154">Details finden Sie unter [Einstellungen für sichere Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) .</span><span class="sxs-lookup"><span data-stu-id="ae50f-154">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="ae50f-155">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-155">Click **Save**.</span></span> 

   ![Image of_Office 365 Security & Compliance Center Seite, die zeigt, dass die Option nicht nachverfolgt werden kann, wenn Benutzer auf sicher klicken nicht ausgewählt ist.](../../media/mtp-eval-38.png)

9. <span data-ttu-id="ae50f-157">Wählen Sie als nächstes die **Antischadsoftware-** Richtlinie aus, wählen Sie die Standardeinstellung aus, und wählen Sie das Bleistiftsymbol aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="ae50f-158">Klicken Sie auf **Einstellungen** und dann auf **Ja, und verwenden Sie den standardmäßigen Benachrichtigungstext** , um die **Malware Erkennungs Antwort** zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="ae50f-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="ae50f-159">Aktivieren Sie den **Filter allgemeine Anlagentypen** .</span><span class="sxs-lookup"><span data-stu-id="ae50f-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="ae50f-160">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-160">Click **Save**.</span></span>

    ![Image of_Office 365 Security & Compliance Center Seite, die zeigt, dass die Malware Erkennungs Antwort mit Standardbenachrichtigung aktiviert ist und der Filter "allgemeine Anlagentypen" aktiviert ist.](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="ae50f-162">Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  -**Such**  >  **Überwachungsprotokoll-Suche** , und aktivieren Sie die Überwachung.</span><span class="sxs-lookup"><span data-stu-id="ae50f-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Image of_Office 365 Security & Compliance Center Seite, auf der Sie die Überwachungsprotokoll Suche aktivieren können](../../media/mtp-eval-40.png)

12. <span data-ttu-id="ae50f-164">Integrieren Sie Microsoft Defender für Office 365 mit Microsoft Defender für Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ae50f-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ae50f-165">Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)  >  **Threat Management**  >  **Explorer** , und wählen Sie in der oberen rechten Ecke des Bildschirms **Microsoft Defender for Endpoint Settings** aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="ae50f-166">Aktivieren Sie im Dialogfeld Verteidiger für Endpunkt Verbindung die Option **Verbindung mit Microsoft Defender für Endpunkt herstellen**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Image of_Office 365 Security & Compliance Center Seite, auf der Sie die Microsoft Defender für Endpoint-Verbindung aktivieren können](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="ae50f-168">Konfigurieren von Microsoft Defender für Identity</span><span class="sxs-lookup"><span data-stu-id="ae50f-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="ae50f-169">Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender bereits für Identity aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="ae50f-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="ae50f-170">Navigieren Sie zum [Microsoft 365 Security Center](https://security.microsoft.com/info) > wählen Sie **Weitere Ressourcen**  >  **Microsoft Defender for Identity** aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Image of_Microsoft 365-Sicherheits Center Seite, auf der eine Option zum Öffnen von Microsoft Defender for Identity verfügbar ist](../../media/mtp-eval-42.png)

2. <span data-ttu-id="ae50f-172">Klicken Sie auf **Erstellen** , um den Microsoft Defender for Identity-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="ae50f-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Seite "Image of_Microsoft Defender for Identity Wizard", auf der Sie auf Erstellen klicken sollten](../../media/mtp-eval-43.png)

3. <span data-ttu-id="ae50f-174">Wählen Sie **Geben Sie einen Benutzernamen und ein Kennwort ein, um eine Verbindung mit Ihrer Active Directory Gesamtstruktur herzustellen**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Image of_Microsoft Defender for Identity Welcome page](../../media/mtp-eval-44.png)

4. <span data-ttu-id="ae50f-176">Geben Sie Ihre Active Directory lokalen Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="ae50f-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="ae50f-177">Hierbei kann es sich um ein beliebiges Benutzerkonto handeln, das über Lesezugriff auf Active Directory verfügt.</span><span class="sxs-lookup"><span data-stu-id="ae50f-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Image of_Microsoft Defender für Identity Directory Services-Seite, auf der Sie Ihre Anmeldeinformationen platzieren sollten](../../media/mtp-eval-45.png)

5. <span data-ttu-id="ae50f-179">Wählen Sie als nächstes **Download Sensor Setup** aus, und übertragen Sie die Datei auf Ihren Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="ae50f-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Image of_Microsoft Defender for Identity-Seite, auf der Sie Download Sensor Setup auswählen können](../../media/mtp-eval-46.png)

6. <span data-ttu-id="ae50f-181">Führen Sie den Microsoft Defender für Identity Sensor Setup aus, und folgen Sie dem Assistenten.</span><span class="sxs-lookup"><span data-stu-id="ae50f-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Image of_Microsoft Defender for Identity-Seite, auf der Sie auf Weiter klicken sollten, um den Assistenten Microsoft Defender for Identity Sensor zu verfolgen](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="ae50f-183">Klicken Sie im Sensor Bereitstellungs auf **weiter** .</span><span class="sxs-lookup"><span data-stu-id="ae50f-183">Click **Next** at the sensor deployment type.</span></span>

   ![Image of_Microsoft Defender für Identity-Seite, auf der Sie auf Weiter klicken sollten, um zur nächsten Seite zu wechseln](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="ae50f-185">Kopieren Sie die Zugriffstaste, da Sie Sie als nächstes im Assistenten eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="ae50f-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Seite "Bild of_the Sensoren", auf der Sie die Zugriffstaste kopieren sollten, die Sie auf der nächsten Seite des Setup-Assistenten von Microsoft Defender für Identity Sensor eingeben müssen](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="ae50f-187">Kopieren Sie den Zugriffsschlüssel in den Assistenten, und klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Seite "Image of_Microsoft Defender for Identity Sensor", auf der Sie die Zugriffstaste eingeben und dann auf die Schaltfläche "installieren" klicken müssen](../../media/mtp-eval-50.png)

10. <span data-ttu-id="ae50f-189">Herzlichen Glückwunsch, Sie haben Microsoft Defender erfolgreich für Identity auf Ihrem Domänencontroller konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="ae50f-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Image of_Microsoft Defender für den Installationsabschluss des Identitäts Sensor-Assistenten, wo Sie auf die Schaltfläche Fertig stellen klicken sollten](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="ae50f-191">Wählen Sie im Abschnitt [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) Settings die Option \* \* Microsoft Defender for Endpoint \* \* aus, und aktivieren Sie dann die Umschaltfläche.</span><span class="sxs-lookup"><span data-stu-id="ae50f-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="ae50f-192">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-192">Click **Save**.</span></span> 

    ![Image of_the Microsoft Defender für Identity Settings-Seite, auf der Sie den Microsoft Defender für Endpoint aktivieren sollten](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="ae50f-194">Windows Defender ATP wurde als Microsoft Defender für Endpoint umbenannt.</span><span class="sxs-lookup"><span data-stu-id="ae50f-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ae50f-195">Das neubranding von Änderungen in allen Portalen wird für die Konsistenz eingeführt.</span><span class="sxs-lookup"><span data-stu-id="ae50f-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="ae50f-196">Konfigurieren der Microsoft Cloud-App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="ae50f-196">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="ae50f-197">Überspringen Sie diesen Schritt, wenn Sie Microsoft Cloud App Security bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="ae50f-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="ae50f-198">Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **Weitere Ressourcen**  >  **Microsoft Cloud-App-Sicherheit**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Image of_Microsoft 365-Sicherheits Center Seite, auf der Sie die Microsoft Cloud-App-Karte anzeigen und auf die Schaltfläche Öffnen klicken können](../../media/mtp-eval-53.png)

2. <span data-ttu-id="ae50f-200">Wählen Sie an der Informations Aufforderung zur Integration von Microsoft Defender for Identity die Option **Microsoft Defender für die Identitätsdaten Integration aktivieren** aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Bild of_the Informations Aufforderung zur Integration von Microsoft Defender für Identity, in der Sie den Link Microsoft Defender für Identitätsdaten Integration aktivieren auswählen sollten](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="ae50f-202">Wenn diese Aufforderung nicht angezeigt wird, kann dies bedeuten, dass Ihr Microsoft Defender for Identity Data Integration bereits aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="ae50f-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="ae50f-203">Wenn Sie sich jedoch nicht sicher sind, wenden Sie sich an Ihren IT-Administrator, um dies zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="ae50f-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="ae50f-204">Wechseln Sie zu **Einstellungen**, aktivieren Sie die Umschaltfläche **Microsoft Defender for Identity Integration** , und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Seite Bild of_the Einstellungen, auf der Sie die Umschaltfläche Microsoft Defender for Identity Integration aktivieren sollten, und klicken Sie dann auf Speichern](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="ae50f-206">Für neue Microsoft Defender für Identitäts Instanzen wird diese Integration Toggle automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ae50f-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="ae50f-207">Vergewissern Sie sich, dass Ihr Microsoft Defender for Identity Integration aktiviert wurde, bevor Sie mit dem nächsten Schritt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="ae50f-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="ae50f-208">Wählen Sie unter den Einstellungen für die Cloud-Ermittlung die Option **Microsoft Defender für die Endpunkt Integration** aus, und aktivieren Sie dann die Integration.</span><span class="sxs-lookup"><span data-stu-id="ae50f-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="ae50f-209">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-209">Click **Save**.</span></span>

   ![Image of_the Microsoft Defender für die Endpunkt Seite, auf der das Kontrollkästchen nicht sanktionierte apps blockieren unter Microsoft Defender for Endpoint Integration ausgewählt ist.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="ae50f-212">Wählen Sie unter Einstellungen für die Cloud-Ermittlung die Option **Benutzer Bereicherung** aus, und aktivieren Sie dann die Integration in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="ae50f-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Bild des Abschnitts "Benutzer Anreicherung", in dem das Kontrollkästchen "ermittelte Benutzerbezeichner mit Azure Active Directory Benutzernamen erweitern" aktiviert ist](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="ae50f-214">Konfigurieren von Microsoft Defender für den Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ae50f-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="ae50f-215">Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender für Endpoint bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="ae50f-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="ae50f-216">Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info)  >  **Weitere Ressourcen**  >  **Microsoft Defender Security Center**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="ae50f-217">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-217">Click **Open**.</span></span>

   ![Sicherheitscenter "Image of_Microsoft Defender" auf der Seite "Microsoft 365 Security Center"](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="ae50f-219">Führen Sie den Microsoft Defender for Endpoint-Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="ae50f-220">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-220">Click **Next**.</span></span> 

   ![Seite "Image of_the Microsoft Defender Security Center-Willkommens Assistent"](../../media/mtp-eval-59.png)

3. <span data-ttu-id="ae50f-222">Wählen Sie basierend auf dem bevorzugten Datenspeicherort, der Datenaufbewahrungsrichtlinie, der Organisationsgröße und dem Opt-in für Vorschau Features aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Image of_the Page, um das Datenspeicher Land, die Aufbewahrungsrichtlinie und die Organisationsgröße auszuwählen.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="ae50f-225">Einige Einstellungen wie der Datenspeicherort können anschließend nicht mehr geändert werden.</span><span class="sxs-lookup"><span data-stu-id="ae50f-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="ae50f-226">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-226">Click **Next**.</span></span> 

4. <span data-ttu-id="ae50f-227">Klicken Sie auf **weiter** , und stellt Ihren Microsoft Defender für den Endpunkt Mandanten zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="ae50f-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Bild of_the Seite, die Sie anfordert, indem Sie auf die Schaltfläche Weiter klicken, um Ihre Cloud-Instanz zu erstellen](../../media/mtp-eval-61.png)

5. <span data-ttu-id="ae50f-229">An Bord ihrer Endpunkte über Gruppenrichtlinien, Microsoft Endpoint Manager oder durch Ausführen eines lokalen Skripts an Microsoft Defender für Endpoint.</span><span class="sxs-lookup"><span data-stu-id="ae50f-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="ae50f-230">Zur Vereinfachung verwendet dieses Handbuch das lokale Skript.</span><span class="sxs-lookup"><span data-stu-id="ae50f-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="ae50f-231">Klicken Sie auf **Paket herunterladen** , und kopieren Sie das Onboarding-Skript an Ihre (n) Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="ae50f-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Image of_page Sie auf die Schaltfläche Paket herunterladen klicken, um das Onboarding-Skript auf ihren Endpunkt oder ihre Endpunkte zu kopieren.](../../media/mtp-eval-62.png)

7. <span data-ttu-id="ae50f-233">Führen Sie auf ihrem Endpunkt das Onboarding-Skript als Administrator aus, und wählen Sie Y aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Image of_the CommandLine, in der Sie das Onboarding-Skript ausführen, und wählen Sie Y, um fortzufahren.](../../media/mtp-eval-63.png)

8. <span data-ttu-id="ae50f-235">Herzlichen Glückwunsch, Sie haben ihren ersten Endpunkt an Bord.</span><span class="sxs-lookup"><span data-stu-id="ae50f-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Image of_the CommandLine, wo Sie die Bestätigung erhalten, dass Sie Ihren ersten Endpunkt an Bord haben.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="ae50f-238">Copy-fügen Sie den Erkennungstest aus dem Microsoft Defender for Endpoint-Assistenten ein.</span><span class="sxs-lookup"><span data-stu-id="ae50f-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Image of_the führen Sie einen Erkennungstest Schritt aus, in dem Sie auf Kopieren klicken sollten, um das Erkennungstest Skript zu kopieren, das Sie an der Eingabeaufforderung einfügen sollten.](../../media/mtp-eval-65.png)

10. <span data-ttu-id="ae50f-240">Kopieren Sie das PowerShell-Skript an eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Bild of_command Aufforderung, bei der das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten kopiert und ausgeführt wird.](../../media/mtp-eval-66.png)

11. <span data-ttu-id="ae50f-242">Wählen Sie im Assistenten **Microsoft Defender für Endpoint starten** aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Bestätigungsaufforderung für Bild of_the aus dem Assistenten, auf der Sie mit Microsoft Defender für Endpoint beginnen sollten](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="ae50f-244">Besuchen Sie das [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="ae50f-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="ae50f-245">Wechseln Sie zu **Einstellungen** , und wählen Sie dann **Erweiterte Funktionen** aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Image of_Microsoft Defender-Sicherheits Center-Einstellungsmenü, in dem Sie erweiterte Funktionen auswählen sollten](../../media/mtp-eval-68.png)

13. <span data-ttu-id="ae50f-247">Aktivieren Sie die Integration mit **Microsoft Defender für Identity**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Image of_Microsoft Defender Security Center erweiterte Funktionen, Microsoft Defender für Identity Option Toggle, die Sie aktivieren müssen](../../media/mtp-eval-69.png)

14. <span data-ttu-id="ae50f-249">Aktivieren Sie die Integration mit **Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Erweiterte Features für Image of_Microsoft Defender Security Center, Office 365 Option Toggle für Threat Intelligence, die Sie aktivieren müssen](../../media/mtp-eval-70.png)

15. <span data-ttu-id="ae50f-251">Aktivieren Sie die Integration in **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="ae50f-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center erweiterte Funktionen, Microsoft Cloud App-Sicherheitsoption Umschaltfläche, die Sie aktivieren müssen](../../media/mtp-eval-71.png)

16. <span data-ttu-id="ae50f-253">Scrollen Sie nach unten, und klicken Sie auf **Einstellungen speichern** , um die neuen Integrationen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="ae50f-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Schaltfläche "Bild of_Save Einstellungen", auf die Sie klicken müssen](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="ae50f-255">Starten des Microsoft 365 Defender-Diensts</span><span class="sxs-lookup"><span data-stu-id="ae50f-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="ae50f-256">Ab dem 1. Juni 2020 Microsoft 365 Defender-Features für alle berechtigten Mandanten automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ae50f-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="ae50f-257">Weitere Informationen finden Sie [in diesem Artikel Microsoft Tech Community on License Berechtigung](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) .</span><span class="sxs-lookup"><span data-stu-id="ae50f-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="ae50f-258">Wechseln Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="ae50f-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="ae50f-259">Navigieren Sie zu **Einstellungen** , und wählen Sie dann **Microsoft 365 Defender** aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="ae50f-260">Image of_Microsoft 365 Defender-Option Screenshot von der Microsoft 365-Seite "Sicherheits Center-Einstellungen"</span><span class="sxs-lookup"><span data-stu-id="ae50f-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="ae50f-261">Eine umfassendere Anleitung finden Sie unter [Aktivieren von Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="ae50f-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="ae50f-262">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="ae50f-262">Congratulations!</span></span> <span data-ttu-id="ae50f-263">Sie haben soeben Ihr Microsoft 365 Defender-Test Labor oder Ihre Pilotumgebung erstellt.</span><span class="sxs-lookup"><span data-stu-id="ae50f-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="ae50f-264">Jetzt können Sie sich mit der Benutzeroberfläche von Microsoft 365 Defender vertraut machen.</span><span class="sxs-lookup"><span data-stu-id="ae50f-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="ae50f-265">Erfahren Sie, was Sie im folgenden interaktiven Leitfaden von Microsoft 365 Defender erfahren und wie Sie die einzelnen Dashboards für Ihre täglichen Aufgaben im Zusammenarbeit mit dem Sicherheitsdienst verwenden können.</span><span class="sxs-lookup"><span data-stu-id="ae50f-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="ae50f-266">Als nächstes können Sie einen Angriff simulieren und sehen, wie die produktübergreifenden Funktionen erkennen, Warnungen erstellen und automatisch auf einen Datei übergreifenden Angriff auf einen Endpunkt reagieren.</span><span class="sxs-lookup"><span data-stu-id="ae50f-266">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="ae50f-267">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="ae50f-267">Next step</span></span>
|[<span data-ttu-id="ae50f-268">Angriffs Simulationsphase</span><span class="sxs-lookup"><span data-stu-id="ae50f-268">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="ae50f-269">Führen Sie die Angriffssimulation für Ihre Microsoft 365 Defender-Pilotumgebung aus.</span><span class="sxs-lookup"><span data-stu-id="ae50f-269">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
