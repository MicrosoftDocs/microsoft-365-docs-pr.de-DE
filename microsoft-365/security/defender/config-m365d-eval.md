---
title: Konfigurieren von Microsoft 365 Defender-Säulen für die Testumgebung oder Pilotumgebung
description: Konfigurieren Sie Microsoft 365 Defender-Säulen, z. B. Microsoft Defender für Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security und Microsoft Defender for Endpoint, für Ihre Testumgebung oder Pilotumgebung.
keywords: Konfigurieren der Microsoft 365 Defender-Testversion, Microsoft 365 Defender-Testkonfiguration, Konfigurieren des Microsoft 365 Defender-Pilotprojekts, Konfigurieren von Microsoft 365 Defender-Säulen, Microsoft 365 Defender-Säulen
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 05bdc9cbb678a3d6c1cee726fc4d8c2e45d2d360
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933505"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="77cde-104">Konfigurieren von Microsoft 365 Defender-Säulen für Ihre Testumgebung oder Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="77cde-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="77cde-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="77cde-105">**Applies to:**</span></span>
- <span data-ttu-id="77cde-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="77cde-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="77cde-107">Das Erstellen einer Microsoft 365 Defender-Testumgebung oder Pilotumgebung und deren Bereitstellung ist ein drei phasenweiser Prozess:</span><span class="sxs-lookup"><span data-stu-id="77cde-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="77cde-108">[![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="77cde-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="77cde-109">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="77cde-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |<span data-ttu-id="77cde-110">[![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span><span class="sxs-lookup"><span data-stu-id="77cde-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span></span><br/>[<span data-ttu-id="77cde-111">Phase 2: Einrichten</span><span class="sxs-lookup"><span data-stu-id="77cde-111">Phase 2: Set up</span></span>](setup-m365deval.md) |![Phase 3: Onboarding](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="77cde-113">Phase 3: Onboarding</span><span class="sxs-lookup"><span data-stu-id="77cde-113">Phase 3: Onboard</span></span> | <span data-ttu-id="77cde-114">[![Zurück zum Pilotprojekt](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="77cde-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="77cde-115">Zurück zum Testspielbuch</span><span class="sxs-lookup"><span data-stu-id="77cde-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="77cde-116">*Sie sind hier!*</span><span class="sxs-lookup"><span data-stu-id="77cde-116">*You are here!*</span></span> | |

<span data-ttu-id="77cde-117">Sie sind derzeit in der Konfigurationsphase.</span><span class="sxs-lookup"><span data-stu-id="77cde-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="77cde-118">Die Vorbereitung ist der Schlüssel zu jeder erfolgreichen Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="77cde-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="77cde-119">In diesem Artikel werden Sie zu den Punkten geführt, die Sie bei der Vorbereitung der Bereitstellung von Microsoft Defender for Endpoint berücksichtigen müssen.</span><span class="sxs-lookup"><span data-stu-id="77cde-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="77cde-120">Microsoft 365 Defender-Säulen</span><span class="sxs-lookup"><span data-stu-id="77cde-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="77cde-121">Microsoft 365 Defender besteht aus vier Säulen.</span><span class="sxs-lookup"><span data-stu-id="77cde-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="77cde-122">Obwohl eine Säule bereits einen Mehrwert für die Sicherheit Ihrer Netzwerkorganisation bieten kann, bietet das Aktivieren der vier Microsoft 365 Defender-Säulen Ihrer Organisation den größten Nutzen.</span><span class="sxs-lookup"><span data-stu-id="77cde-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Image of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte Microsoft Defender for Endpoint, für Cloud-Apps, Microsoft Cloud App Security und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="77cde-124">In diesem Abschnitt werden Sie beim Konfigurieren von:</span><span class="sxs-lookup"><span data-stu-id="77cde-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="77cde-125">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="77cde-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="77cde-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="77cde-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="77cde-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="77cde-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="77cde-128">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="77cde-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="77cde-129">Konfigurieren von Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="77cde-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="77cde-130">Überspringen Sie diesen Schritt, wenn Sie Defender für Office 365 bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="77cde-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="77cde-131">Es gibt ein PowerShell-Modul namens *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA),* das einige dieser Einstellungen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="77cde-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="77cde-132">Wenn get-ORCAReport als Administrator in Ihrem Mandanten ausgeführt wird, wird eine Bewertung der Antispam-, Antispam- und anderen Nachrichtenhygieneeinstellungen generiert.</span><span class="sxs-lookup"><span data-stu-id="77cde-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="77cde-133">Sie können dieses Modul von https://www.powershellgallery.com/packages/ORCA/ herunterladen.</span><span class="sxs-lookup"><span data-stu-id="77cde-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="77cde-134">Navigieren Sie [zu Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Policy**.</span><span class="sxs-lookup"><span data-stu-id="77cde-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Abbildung of_Office 365 Security & Compliance Center Threat Management Policy Page](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="77cde-136">Klicken **Sie auf Antiphishing,** wählen **Sie Erstellen** aus, und geben Sie den Richtliniennamen und die Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="77cde-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="77cde-137">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="77cde-137">Click **Next**.</span></span>

   ![Abbildung of_Office 365 Security & Compliance Center–Antiphishingrichtlinienseite, auf der Sie Ihre Richtlinie benennen können](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="77cde-139">Bearbeiten Sie Ihre Erweiterte Antiphishingrichtlinie in Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="77cde-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="77cde-140">Ändern **des erweiterten Phishingschwellenwerts** **auf 2 – Aggressiv**.</span><span class="sxs-lookup"><span data-stu-id="77cde-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="77cde-141">Klicken Sie **auf das Dropdownmenü** Bedingung hinzufügen, und wählen Sie Ihre Domäne als Empfängerdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="77cde-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="77cde-142">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="77cde-142">Click **Next**.</span></span>

   ![Abbildung of_Office 365 Security & Compliance Center–Antiphishingrichtlinienseite, auf der Sie eine Bedingung für die Anwendung hinzufügen können](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="77cde-144">Überprüfen Sie Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="77cde-144">Review your settings.</span></span> <span data-ttu-id="77cde-145">Klicken **Sie auf Diese Richtlinie erstellen,** um dies zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="77cde-145">Click **Create this policy** to confirm.</span></span> 

   ![Abbildung of_Office 365 Security & Compliance Center– Antiphishingrichtlinienseite, auf der Sie Ihre Einstellungen überprüfen und auf die Schaltfläche Diese Richtlinie erstellen klicken können](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="77cde-147">Wählen **Sie Sichere Anlagen** aus, und wählen Sie die Option **ATP für SharePoint, OneDrive** und Microsoft Teams aktivieren aus.</span><span class="sxs-lookup"><span data-stu-id="77cde-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 Security & Compliance Center-Seite, auf der Sie ATP für SharePoint, OneDrive und Microsoft Teams aktivieren können](../../media/mtp-eval-36.png)

6. <span data-ttu-id="77cde-149">Klicken Sie auf das Symbol +, um eine neue Richtlinie für sichere Anlagen zu erstellen, und wenden Sie sie als Empfängerdomäne auf Ihre Domänen an.</span><span class="sxs-lookup"><span data-stu-id="77cde-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="77cde-150">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="77cde-150">Click **Save**.</span></span>

   ![Abbildung of_Office 365 Security & Compliance Center-Seite, auf der Sie eine neue Richtlinie für sichere Anlagen erstellen können](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="77cde-152">Wählen Sie als Nächstes die Richtlinie für **sichere** Links aus, und klicken Sie dann auf das Stiftsymbol, um die Standardrichtlinie zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="77cde-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="77cde-153">Stellen Sie sicher, dass die Option Nicht **nachverfolgen, wenn** Benutzer auf sichere Links klicken, nicht ausgewählt ist, während die restlichen Optionen ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="77cde-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="77cde-154">Weitere [Informationen finden Sie unter Einstellungen für sichere](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) Links.</span><span class="sxs-lookup"><span data-stu-id="77cde-154">See [Safe Links settings](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) for details.</span></span> <span data-ttu-id="77cde-155">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="77cde-155">Click **Save**.</span></span> 

   ![Abbildung of_Office 365 Security & Compliance Center-Seite, die zeigt, dass die Option Nicht nachverfolgen, wenn Benutzer auf sicher klicken nicht ausgewählt ist](../../media/mtp-eval-38.png)

9. <span data-ttu-id="77cde-157">Wählen Sie als Nächstes **die Richtlinie An malware** aus, wählen Sie die Standardeinstellung aus, und wählen Sie das Stiftsymbol aus.</span><span class="sxs-lookup"><span data-stu-id="77cde-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="77cde-158">Klicken **Sie auf** Einstellungen, und wählen Sie Ja aus, und verwenden Sie den Standardbenachrichtigungstext, um die Reaktion auf  **schadsoftwareerkennung zu aktivieren.**</span><span class="sxs-lookup"><span data-stu-id="77cde-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="77cde-159">Aktivieren Sie **den Filter für allgemeine Anlagentypen.**</span><span class="sxs-lookup"><span data-stu-id="77cde-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="77cde-160">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="77cde-160">Click **Save**.</span></span>

    ![Abbildung of_Office 365 Security & Compliance Center-Seite, die zeigt, dass die Reaktion auf schadsoftwareerkennung mit Standardbenachrichtigung aktiviert ist und der Filter für allgemeine Anlagentypen aktiviert ist.](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="77cde-162">Navigieren Sie [zu Office 365 Security & Compliance Center](https://protection.office.com/homepage)Search  >  **Audit** log  >  **search,** und aktivieren Sie die Überwachung.</span><span class="sxs-lookup"><span data-stu-id="77cde-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Image of_Office 365 Security & Compliance Center-Seite, auf der Sie die Überwachungsprotokollsuche aktivieren können](../../media/mtp-eval-40.png)

12. <span data-ttu-id="77cde-164">Integrieren Sie Microsoft Defender für Office 365 in Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="77cde-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="77cde-165">Navigieren Sie [zu Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat Management Explorer, und wählen Sie microsoft Defender for Endpoint Settings in der oberen rechten Ecke des  >    >   Bildschirms aus. </span><span class="sxs-lookup"><span data-stu-id="77cde-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="77cde-166">Aktivieren Sie im Dialogfeld Verbindung mit Defender for Endpoint die Verbindung **mit Microsoft Defender for Endpoint verbinden.**</span><span class="sxs-lookup"><span data-stu-id="77cde-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Abbildung of_Office 365 Security & Compliance Center-Seite, auf der Sie die Microsoft Defender for Endpoint-Verbindung aktivieren können](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="77cde-168">Konfigurieren von Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="77cde-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="77cde-169">Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender for Identity bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="77cde-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="77cde-170">Navigieren Sie [zu Microsoft 365 Security Center,](https://security.microsoft.com/info) > Weitere **Ressourcen** Microsoft Defender for  >  **Identity auswählen.**</span><span class="sxs-lookup"><span data-stu-id="77cde-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Bild of_Microsoft 365 Security Center-Seite, auf der eine Option zum Öffnen von Microsoft Defender for Identity verfügbar ist](../../media/mtp-eval-42.png)

2. <span data-ttu-id="77cde-172">Klicken **Sie auf Erstellen,** um den Microsoft Defender for Identity-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="77cde-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   ![Image of_Microsoft Defender for Identity Wizard-Seite, auf der Sie auf Schaltfläche Erstellen klicken sollten](../../media/mtp-eval-43.png)

3. <span data-ttu-id="77cde-174">Wählen **Sie Geben Sie einen Benutzernamen und ein Kennwort an, um eine Verbindung mit Ihrer Active Directory-Gesamtstruktur herzustellen.**</span><span class="sxs-lookup"><span data-stu-id="77cde-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![Willkommensseite of_Microsoft Defender for Identity](../../media/mtp-eval-44.png)

4. <span data-ttu-id="77cde-176">Geben Sie Ihre lokalen Active Directory-Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="77cde-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="77cde-177">Dies kann ein beliebiges Benutzerkonto sein, das Lesezugriff auf Active Directory hat.</span><span class="sxs-lookup"><span data-stu-id="77cde-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Abbildung of_Microsoft Defender for Identity Directory-Dienstseite, auf der Sie Ihre Anmeldeinformationen eingeben sollten](../../media/mtp-eval-45.png)

5. <span data-ttu-id="77cde-179">Wählen Sie als Nächstes **Sensoreinrichtung herunterladen aus,** und übertragen Sie die Datei auf den Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="77cde-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Image of_Microsoft Defender for Identity-Seite, auf der Sie Sensoreinrichtung herunterladen auswählen können](../../media/mtp-eval-46.png)

6. <span data-ttu-id="77cde-181">Führen Sie das Microsoft Defender for Identity Sensor Setup aus, und beginnen Sie mit dem Ausführen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="77cde-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Bild of_Microsoft Defender for Identity-Seite, auf der Sie neben dem Microsoft Defender for Identity-Sensor-Assistenten klicken sollten](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="77cde-183">Klicken **Sie im** Sensorbereitstellungstyp auf Weiter.</span><span class="sxs-lookup"><span data-stu-id="77cde-183">Click **Next** at the sensor deployment type.</span></span>

   ![Bild of_Microsoft Defender for Identity-Seite, auf die Sie klicken sollten, um zur nächsten Seite zu wechseln](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="77cde-185">Kopieren Sie den Zugriffsschlüssel, da Sie ihn als Nächstes im Assistenten eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="77cde-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Abbildung of_the-Sensorseite, auf der Sie die Zugriffstaste kopieren sollten, die Sie auf der nächsten Seite des Microsoft Defender for Identity-Sensor-Setup-Assistenten eingeben müssen.](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="77cde-187">Kopieren Sie die Zugriffstaste in den Assistenten, und klicken Sie auf **Installieren**.</span><span class="sxs-lookup"><span data-stu-id="77cde-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Abbildung of_Microsoft Defender for Identity-Sensor-Assistentenseite, auf der Sie die Zugriffstaste bereitstellen und dann auf die Schaltfläche Installieren klicken sollten](../../media/mtp-eval-50.png)

10. <span data-ttu-id="77cde-189">Herzlichen Glückwunsch, Sie haben Microsoft Defender for Identity auf Ihrem Domänencontroller erfolgreich konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="77cde-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Abbildung of_Microsoft Defender for Identity-Sensor-Assistent-Installation abgeschlossen, in der Sie auf die Schaltfläche Fertig stellen klicken sollten](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="77cde-191">Wählen Sie [im Abschnitt Microsoft Defender for Identity-Einstellungen](https://go.microsoft.com/fwlink/?linkid=2040449) \*\*Microsoft Defender for Endpoint \*\*, und aktivieren Sie dann den Umschalter.</span><span class="sxs-lookup"><span data-stu-id="77cde-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="77cde-192">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="77cde-192">Click **Save**.</span></span> 

    ![Bild of_the Microsoft Defender for Identity-Einstellungsseite, auf der Sie die Microsoft Defender for Endpoint-Umschaltseite aktivieren sollten](../../media/mtp-eval-52.png)


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="77cde-194">Konfigurieren von Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="77cde-194">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="77cde-195">Überspringen Sie diesen Schritt, wenn Sie Microsoft Cloud App Security bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="77cde-195">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="77cde-196">Navigieren Sie [zu Microsoft 365 Security Center](https://security.microsoft.com/info)Weitere  >  **Ressourcen** Microsoft Cloud  >  **App Security**.</span><span class="sxs-lookup"><span data-stu-id="77cde-196">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Bild of_Microsoft 365 Security Center-Seite, auf der Sie die Microsoft Cloud App-Karte sehen können und auf die Schaltfläche Öffnen klicken sollten](../../media/mtp-eval-53.png)

2. <span data-ttu-id="77cde-198">Wählen Sie an der Eingabeaufforderung zum Integrieren von Microsoft Defender for Identity die Option **Microsoft Defender for Identity-Datenintegration aktivieren aus.**</span><span class="sxs-lookup"><span data-stu-id="77cde-198">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Bild of_the Eingabeaufforderung zur Integration von Microsoft Defender for Identity, in der Sie den Link Microsoft Defender for Identity-Datenintegration aktivieren auswählen sollten](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="77cde-200">Wenn diese Eingabeaufforderung nicht angezeigt wird, kann dies bedeuten, dass Ihre Microsoft Defender for Identity-Datenintegration bereits aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="77cde-200">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="77cde-201">Wenn Sie jedoch nicht sicher sind, wenden Sie sich an Ihren IT-Administrator, um dies zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="77cde-201">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="77cde-202">Wechseln Sie zu **Einstellungen,** aktivieren Sie die **Umschalte Microsoft Defender for Identity-Integration,** und klicken Sie dann auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="77cde-202">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![Bild of_the Einstellungsseite, auf der Sie die Microsoft Defender for Identity-Integration aktivieren sollten, und klicken Sie dann auf Speichern.](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="77cde-204">Bei neuen Microsoft Defender for Identity-Instanzen wird diese Integrationsschalte automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="77cde-204">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="77cde-205">Vergewissern Sie sich, dass Ihre Microsoft Defender for Identity-Integration aktiviert wurde, bevor Sie mit dem nächsten Schritt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="77cde-205">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="77cde-206">Wählen Sie unter cloud discovery settings **die Option Microsoft Defender for Endpoint integration** aus, und aktivieren Sie dann die Integration.</span><span class="sxs-lookup"><span data-stu-id="77cde-206">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="77cde-207">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="77cde-207">Click **Save**.</span></span>

   ![Abbildung of_the Microsoft Defender for Endpoint-Seite, auf der das Kontrollkästchen nicht installierte Apps blockieren unter Microsoft Defender for Endpoint-Integration aktiviert ist.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="77cde-210">Wählen Sie unter Einstellungen für die Clouderkennung **die Option Benutzererweiterung** aus, und aktivieren Sie dann die Integration in Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="77cde-210">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Abbildung des Abschnitts "Benutzererweiterung", in dem das Kontrollkästchen "Anreichern ermittelter Benutzerbezeichner mit Azure Active Directory-Benutzernamen" aktiviert ist](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="77cde-212">Konfigurieren von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="77cde-212">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="77cde-213">Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender for Endpoint bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="77cde-213">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="77cde-214">Navigieren Sie [zu Microsoft 365 Security Center](https://security.microsoft.com/info)Weitere  >  **Ressourcen** Microsoft Defender  >  **Security Center**.</span><span class="sxs-lookup"><span data-stu-id="77cde-214">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="77cde-215">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="77cde-215">Click **Open**.</span></span>

   ![Option of_Microsoft Defender Security Center auf der Microsoft 365 Security Center-Seite](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="77cde-217">Folgen Sie dem Microsoft Defender for Endpoint-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="77cde-217">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="77cde-218">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="77cde-218">Click **Next**.</span></span> 

   ![Bild of_the Microsoft Defender Security Center-Willkommens-Assistentenseite](../../media/mtp-eval-59.png)

3. <span data-ttu-id="77cde-220">Wählen Sie basierend auf Dem bevorzugten Datenspeicherort, Datenaufbewahrungsrichtlinie, Organisationsgröße und Opt-In für Vorschaufeatures aus.</span><span class="sxs-lookup"><span data-stu-id="77cde-220">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Bild of_the seite, um Ihr Datenspeicherland, die Aufbewahrungsrichtlinie und die Organisationsgröße auszuwählen.](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="77cde-223">Sie können einige der Einstellungen, z. B. den Datenspeicherort, danach nicht mehr ändern.</span><span class="sxs-lookup"><span data-stu-id="77cde-223">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="77cde-224">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="77cde-224">Click **Next**.</span></span> 

4. <span data-ttu-id="77cde-225">Klicken **Sie auf Weiter,** und der Microsoft Defender for Endpoint-Mandant wird bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="77cde-225">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Bild of_the Seite, auf der Sie auf die Schaltfläche Weiter klicken, um Ihre Cloudinstanz zu erstellen](../../media/mtp-eval-61.png)

5. <span data-ttu-id="77cde-227">Onboarding Ihrer Endpunkte über Gruppenrichtlinien, Microsoft Endpoint Manager oder durch Ausführen eines lokalen Skripts für Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="77cde-227">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="77cde-228">Der Einfachheit halber verwendet dieses Handbuch das lokale Skript.</span><span class="sxs-lookup"><span data-stu-id="77cde-228">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="77cde-229">Klicken **Sie auf Paket herunterladen,** und kopieren Sie das Onboardingskript auf Ihre Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="77cde-229">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Abbildung of_page, mit der Sie auf die Schaltfläche Paket herunterladen klicken, um das Onboardingskript auf Ihren Endpunkt oder Ihre Endpunkte zu kopieren.](../../media/mtp-eval-62.png)

7. <span data-ttu-id="77cde-231">Führen Sie auf Ihrem Endpunkt das Onboardingskript als Administrator aus, und wählen Sie Y aus.</span><span class="sxs-lookup"><span data-stu-id="77cde-231">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![Abbildung of_the Befehlszeile, in der Sie das Onboardingskript ausführen und Y auswählen, um fortzufahren](../../media/mtp-eval-63.png)

8. <span data-ttu-id="77cde-233">Herzlichen Glückwunsch, Sie haben Ihren ersten Endpunkt onboardiert.</span><span class="sxs-lookup"><span data-stu-id="77cde-233">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Abbildung of_the Befehlszeile, in der Sie die Bestätigung erhalten, dass Sie Ihren ersten Endpunkt onboardiert haben.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="77cde-236">Kopieren Sie den Erkennungstest aus dem Microsoft Defender for Endpoint-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="77cde-236">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Image of_the einen Erkennungstestschritt ausführen, in dem Sie auf Kopieren klicken sollten, um das Erkennungstestskript zu kopieren, das Sie in die Eingabeaufforderung einfügen sollten](../../media/mtp-eval-65.png)

10. <span data-ttu-id="77cde-238">Kopieren Sie das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="77cde-238">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![Bild of_command Eingabeaufforderung, an der Sie das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten kopieren und ausführen sollten](../../media/mtp-eval-66.png)

11. <span data-ttu-id="77cde-240">Wählen **Sie im Assistenten Starten mit Microsoft Defender for Endpoint** aus.</span><span class="sxs-lookup"><span data-stu-id="77cde-240">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Bild of_the Bestätigungsaufforderung aus dem Assistenten, in dem Sie auf Starten mit Microsoft Defender for Endpoint klicken sollten](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="77cde-242">Besuchen Sie [das Microsoft Defender Security Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="77cde-242">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="77cde-243">Wechseln Sie zu **Einstellungen,** und wählen Sie **dann Erweiterte Features aus.**</span><span class="sxs-lookup"><span data-stu-id="77cde-243">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![Menü of_Microsoft Einstellungen von Defender Security Center, in dem Sie erweiterte Features auswählen sollten](../../media/mtp-eval-68.png)

13. <span data-ttu-id="77cde-245">Aktivieren Sie die Integration in **Microsoft Defender for Identity**.</span><span class="sxs-lookup"><span data-stu-id="77cde-245">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Image of_Microsoft Defender Security Center Advanced-Features, Microsoft Defender for Identity-Option umschalten, die Sie aktivieren müssen](../../media/mtp-eval-69.png)

14. <span data-ttu-id="77cde-247">Aktivieren Sie die Integration in **Office 365 Threat Intelligence**.</span><span class="sxs-lookup"><span data-stu-id="77cde-247">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced-Features, Office 365 Threat Intelligence-Option umschalten, die Sie aktivieren müssen](../../media/mtp-eval-70.png)

15. <span data-ttu-id="77cde-249">Aktivieren der Integration in **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="77cde-249">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced-Features, Microsoft Cloud App Security-Option umschalten, die Sie aktivieren müssen](../../media/mtp-eval-71.png)

16. <span data-ttu-id="77cde-251">Scrollen Sie nach unten, und klicken **Sie auf Einstellungen speichern,** um die neuen Integrationen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="77cde-251">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Schaltfläche of_Save Einstellungen, auf die Sie klicken müssen](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="77cde-253">Starten des Microsoft 365 Defender-Diensts</span><span class="sxs-lookup"><span data-stu-id="77cde-253">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="77cde-254">Ab dem 1. Juni 2020 aktiviert Microsoft automatisch Microsoft 365 Defender-Features für alle berechtigten Mandanten.</span><span class="sxs-lookup"><span data-stu-id="77cde-254">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="77cde-255">Weitere Informationen finden Sie in diesem [Microsoft Tech Community-Artikel](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) zur Lizenzberechtigung.</span><span class="sxs-lookup"><span data-stu-id="77cde-255">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="77cde-256">Wechseln Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span><span class="sxs-lookup"><span data-stu-id="77cde-256">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="77cde-257">Navigieren Sie zu **Einstellungen,** und wählen Sie **dann Microsoft 365 Defender aus.**</span><span class="sxs-lookup"><span data-stu-id="77cde-257">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="77cde-258">Screenshot of_Microsoft 365 Defender-Optionen auf der Seite Microsoft 365 Security Center-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="77cde-258">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="77cde-259">Eine umfassendere Anleitung finden Sie unter [Turn on Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="77cde-259">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](m365d-enable.md).</span></span> 

<span data-ttu-id="77cde-260">Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="77cde-260">Congratulations!</span></span> <span data-ttu-id="77cde-261">Sie haben gerade Ihre Microsoft 365 Defender-Testumgebung oder Pilotumgebung erstellt!</span><span class="sxs-lookup"><span data-stu-id="77cde-261">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="77cde-262">Jetzt können Sie sich mit der Microsoft 365 Defender-Benutzeroberfläche vertraut machen!</span><span class="sxs-lookup"><span data-stu-id="77cde-262">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="77cde-263">Erfahren Sie, was Sie aus dem folgenden interaktiven Microsoft 365 Defender-Leitfaden lernen können, und erfahren Sie, wie Sie jedes Dashboard für Ihre täglichen Sicherheitsaufgaben verwenden.</span><span class="sxs-lookup"><span data-stu-id="77cde-263">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>

[<span data-ttu-id="77cde-264">Sehen Sie sich den interaktiven Leitfaden an</span><span class="sxs-lookup"><span data-stu-id="77cde-264">Check out the interactive guide</span></span>](https://aka.ms/MTP-Interactive-Guide)

<span data-ttu-id="77cde-265">Als Nächstes können Sie einen Angriff simulieren und sehen, wie produktübergreifende Funktionen Warnungen erkennen, erstellen und automatisch auf einen dateilosen Angriff auf einen Endpunkt reagieren.</span><span class="sxs-lookup"><span data-stu-id="77cde-265">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="77cde-266">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="77cde-266">Next step</span></span>

- <span data-ttu-id="77cde-267">[Generieren einer Testwarnung](generate-test-alert.md) – Führen Sie eine Angriffssimulation in Ihrem Microsoft 365 Defender-Testlabor aus.</span><span class="sxs-lookup"><span data-stu-id="77cde-267">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>