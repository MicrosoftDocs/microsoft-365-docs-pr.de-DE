---
title: Konfigurieren Microsoft 365 Defender Säulen für die Testumgebung oder Pilotumgebung
description: Konfigurieren Sie Microsoft 365 Defender Säulen, z. B. Microsoft Defender für Office 365, Microsoft Defender for Identity, Microsoft Cloud App Security und Microsoft Defender für Endpunkt, für Ihre Testumgebung oder Pilotumgebung.
keywords: Konfigurieren Microsoft 365 Defender Testversion, Microsoft 365 Defender Testkonfiguration, Konfigurieren Microsoft 365 Defender Pilotprojekts, Konfigurieren Microsoft 365 Defender Säulen, Microsoft 365 Defender Säulen
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
ms.openlocfilehash: e50210f02d14be33c357517515d456318aac4bb6
ms.sourcegitcommit: 9856f86532bdcf0befbcdbdb7c6dc6bf89fe63b5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53458445"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="3c520-104">Konfigurieren Microsoft 365 Defender Säulen für Ihre Testumgebung oder Pilotumgebung</span><span class="sxs-lookup"><span data-stu-id="3c520-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3c520-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3c520-105">**Applies to:**</span></span>
- <span data-ttu-id="3c520-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3c520-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="3c520-107">Das Erstellen einer Microsoft 365 Defender Testumgebung oder Einer Pilotumgebung und deren Bereitstellung ist ein dreistufiger Prozess:</span><span class="sxs-lookup"><span data-stu-id="3c520-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="3c520-108">[![Phase 1: Vorbereiten](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="3c520-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="3c520-109">Phase 1: Vorbereiten</span><span class="sxs-lookup"><span data-stu-id="3c520-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |<span data-ttu-id="3c520-110">[![Phase 2: Einrichten](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span><span class="sxs-lookup"><span data-stu-id="3c520-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span></span><br/>[<span data-ttu-id="3c520-111">Phase 2: Einrichten</span><span class="sxs-lookup"><span data-stu-id="3c520-111">Phase 2: Set up</span></span>](setup-m365deval.md) |![Phase 3: Onboarding](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="3c520-113">Phase 3: Onboarding</span><span class="sxs-lookup"><span data-stu-id="3c520-113">Phase 3: Onboard</span></span> | <span data-ttu-id="3c520-114">[![Zurück zum Pilotprojekt](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="3c520-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="3c520-115">Zurück zum Pilot-Playbook</span><span class="sxs-lookup"><span data-stu-id="3c520-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="3c520-116">*Sie sind hier!*</span><span class="sxs-lookup"><span data-stu-id="3c520-116">*You are here!*</span></span> | |

<span data-ttu-id="3c520-117">Sie befinden sich derzeit in der Konfigurationsphase.</span><span class="sxs-lookup"><span data-stu-id="3c520-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="3c520-118">Die Vorbereitung ist der Schlüssel für eine erfolgreiche Bereitstellung.</span><span class="sxs-lookup"><span data-stu-id="3c520-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="3c520-119">In diesem Artikel werden Sie zu den Punkten geführt, die Sie bei der Vorbereitung der Bereitstellung von Microsoft Defender für Endpunkt berücksichtigen müssen.</span><span class="sxs-lookup"><span data-stu-id="3c520-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>

## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="3c520-120">Microsoft 365 Defender Säulen</span><span class="sxs-lookup"><span data-stu-id="3c520-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="3c520-121">Microsoft 365 Defender besteht aus vier Säulen.</span><span class="sxs-lookup"><span data-stu-id="3c520-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="3c520-122">Obwohl eine Säule bereits einen Wert für die Sicherheit Ihrer Netzwerkorganisation bieten kann, bietet die Aktivierung der vier säulen Microsoft 365 Defender Ihrer Organisation den größten Nutzen.</span><span class="sxs-lookup"><span data-stu-id="3c520-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Abbildung of_Microsoft 365 Defender-Lösung für Benutzer, Microsoft Defender for Identity, für Endpunkte Microsoft Defender für Endpunkt, für Cloud-Apps, Microsoft Cloud App Security und für Daten, Microsoft Defender für Office 365](../../media/mtp/m365pillars.png)

<span data-ttu-id="3c520-124">In diesem Abschnitt erfahren Sie, wie Sie Folgendes konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="3c520-124">This section will guide you to configure:</span></span>

- <span data-ttu-id="3c520-125">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="3c520-125">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="3c520-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="3c520-126">Microsoft Defender for Identity</span></span>
- <span data-ttu-id="3c520-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3c520-127">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="3c520-128">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3c520-128">Microsoft Defender for Endpoint</span></span>

## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="3c520-129">Konfigurieren von Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="3c520-129">Configure Microsoft Defender for Office 365</span></span>

> [!NOTE]
> <span data-ttu-id="3c520-130">Überspringen Sie diesen Schritt, wenn Sie Defender bereits für Office 365 aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="3c520-130">Skip this step if you've already enabled Defender for Office 365.</span></span>

<span data-ttu-id="3c520-131">Es gibt ein PowerShell-Modul namens *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA),* das einige dieser Einstellungen bestimmt.</span><span class="sxs-lookup"><span data-stu-id="3c520-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="3c520-132">Wenn sie als Administrator in Ihrem Mandanten ausgeführt wird, hilft get-ORCAReport dabei, eine Bewertung der Antispam-, Antiphishing- und anderen Nachrichtenschutzeinstellungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3c520-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="3c520-133">Sie können dieses Modul von https://www.powershellgallery.com/packages/ORCA/ herunterladen.</span><span class="sxs-lookup"><span data-stu-id="3c520-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span>

1. <span data-ttu-id="3c520-134">Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Policy.**</span><span class="sxs-lookup"><span data-stu-id="3c520-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Seite "Image of_Office 365 Security & Compliance Center Threat Management Policy"](../../media/mtp-eval-32.png)

2. <span data-ttu-id="3c520-136">Klicken Sie auf **"Antiphishing",** wählen Sie **"Erstellen"** aus, und geben Sie den Richtliniennamen und die Beschreibung ein.</span><span class="sxs-lookup"><span data-stu-id="3c520-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="3c520-137">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3c520-137">Click **Next**.</span></span>

   ![Abbildung of_Office 365 Security & Compliance Center-Antiphishingrichtlinienseite, auf der Sie Ihre Richtlinie benennen können](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="3c520-139">Bearbeiten Sie Ihre erweiterte Antiphishingrichtlinie in Microsoft Defender für Office 365.</span><span class="sxs-lookup"><span data-stu-id="3c520-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="3c520-140">Ändern Sie den **Erweiterten Phishingschwellenwert** auf **2 – Aggressiv.**</span><span class="sxs-lookup"><span data-stu-id="3c520-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="3c520-141">Klicken Sie auf das Dropdownmenü **"Bedingung hinzufügen",** und wählen Sie Ihre Domäne(n) als Empfängerdomäne aus.</span><span class="sxs-lookup"><span data-stu-id="3c520-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="3c520-142">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3c520-142">Click **Next**.</span></span>

   ![Abbildung of_Office Seite "365 Security & Compliance Center antiphishing policy", auf der Sie eine Bedingung für die Anwendung hinzufügen können](../../media/mtp-eval-34.png)

4. <span data-ttu-id="3c520-144">Überprüfen Sie Ihre Einstellungen.</span><span class="sxs-lookup"><span data-stu-id="3c520-144">Review your settings.</span></span> <span data-ttu-id="3c520-145">Klicken Sie auf **"Diese Richtlinie** erstellen", um dies zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="3c520-145">Click **Create this policy** to confirm.</span></span>

   ![Abbildung of_Office Seite "365 Security & Compliance Center antiphishing policy", auf der Sie Ihre Einstellungen überprüfen und auf die Schaltfläche zum Erstellen dieser Richtlinie klicken können](../../media/mtp-eval-35.png)

5. <span data-ttu-id="3c520-147">Wählen Sie **Tresor Anlagen** aus, und aktivieren Sie **atP für SharePoint, OneDrive und Microsoft Teams** Option.</span><span class="sxs-lookup"><span data-stu-id="3c520-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Abbildung of_Office Seite "365 Security & Compliance Center", auf der Sie ATP für SharePoint, OneDrive und Microsoft Teams aktivieren können](../../media/mtp-eval-36.png)

6. <span data-ttu-id="3c520-149">Klicken Sie auf das Symbol +, um eine neue Richtlinie für sichere Anlagen zu erstellen und sie als Empfängerdomäne auf Ihre Domänen anzuwenden.</span><span class="sxs-lookup"><span data-stu-id="3c520-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="3c520-150">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3c520-150">Click **Save**.</span></span>

   ![Abbildung of_Office Seite "365 Security & Compliance Center", auf der Sie eine neue Richtlinie für sichere Anlagen erstellen können](../../media/mtp-eval-37.png)

7. <span data-ttu-id="3c520-152">Wählen Sie als Nächstes die **Richtlinie Tresor Links** aus, und klicken Sie dann auf das Stiftsymbol, um die Standardrichtlinie zu bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="3c520-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="3c520-153">Stellen Sie sicher, dass die Option **"Nicht nachverfolgen", wenn Benutzer auf** die Option "Sichere Links" klicken, nicht ausgewählt ist, während die restlichen Optionen ausgewählt sind.</span><span class="sxs-lookup"><span data-stu-id="3c520-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="3c520-154">Weitere Informationen finden Sie [unter Tresor Links-Einstellungen.](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365)</span><span class="sxs-lookup"><span data-stu-id="3c520-154">See [Safe Links settings](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) for details.</span></span> <span data-ttu-id="3c520-155">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3c520-155">Click **Save**.</span></span>

   ![Abbildung of_Office Seite "365 Security & Compliance Center", die zeigt, dass die Option "Nicht nachverfolgen" angezeigt wird, wenn Benutzer auf "Sicher" klicken, nicht ausgewählt ist](../../media/mtp-eval-38.png)

9. <span data-ttu-id="3c520-157">Wählen Sie als Nächstes die **Antischadsoftwarerichtlinie** aus, wählen Sie die Standardeinstellung aus, und wählen Sie das Stiftsymbol aus.</span><span class="sxs-lookup"><span data-stu-id="3c520-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="3c520-158">Klicken Sie auf **Einstellungen,** und wählen Sie **"Ja" aus, und verwenden Sie den Standardbenachrichtigungstext,** um die **Schadsoftwareerkennungsantwort** zu aktivieren.</span><span class="sxs-lookup"><span data-stu-id="3c520-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="3c520-159">Aktivieren Sie den **Filter für allgemeine Anlagentypen.**</span><span class="sxs-lookup"><span data-stu-id="3c520-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="3c520-160">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3c520-160">Click **Save**.</span></span>

    ![Abbildung of_Office Seite "365 Security & Compliance Center", die zeigt, dass die Antwort auf die Schadsoftwareerkennung mit Standardbenachrichtigung aktiviert ist und der Filter für allgemeine Anlagentypen aktiviert ist](../../media/mtp-eval-39.png)

11. <span data-ttu-id="3c520-162">Navigieren Sie zu Office 365 Überwachungsprotokollsuche [im Security & Compliance](https://protection.office.com/homepage)  >    >   Center, und aktivieren Sie die Überwachung.</span><span class="sxs-lookup"><span data-stu-id="3c520-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Abbildung of_Office Seite "365 Security & Compliance Center", auf der Sie die Überwachungsprotokollsuche aktivieren können](../../media/mtp-eval-40.png)

12. <span data-ttu-id="3c520-164">Integrieren Sie Microsoft Defender für Office 365 in Microsoft Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="3c520-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3c520-165">Navigieren Sie zu [Office 365 Security & Compliance Center](https://protection.office.com/homepage)Threat  >  **Management**  >  **Explorer,** und wählen Sie **Microsoft Defender für Endpunkt Einstellungen** in der oberen rechten Ecke des Bildschirms aus.</span><span class="sxs-lookup"><span data-stu-id="3c520-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="3c520-166">Aktivieren Sie im Dialogfeld "Defender für Endpunkt-Verbindung" **Verbinden zu Microsoft Defender für Endpunkt.**</span><span class="sxs-lookup"><span data-stu-id="3c520-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Abbildung of_Office Seite "365 Security & Compliance Center", auf der Sie die Microsoft Defender für Endpunkt-Verbindung aktivieren können](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="3c520-168">Konfigurieren von Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="3c520-168">Configure Microsoft Defender for Identity</span></span>

> [!NOTE]
> <span data-ttu-id="3c520-169">Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender for Identity bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="3c520-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="3c520-170">Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info) > wählen Sie weitere **Ressourcen** Microsoft Defender  >  **for Identity** aus.</span><span class="sxs-lookup"><span data-stu-id="3c520-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Abbildung of_Microsoft 365 Security Center-Seite, auf der es eine Option zum Öffnen von Microsoft Defender for Identity gibt](../../media/mtp-eval-42.png)

2. <span data-ttu-id="3c520-172">Klicken Sie auf **"Erstellen",** um den Microsoft Defender for Identity-Assistenten zu starten.</span><span class="sxs-lookup"><span data-stu-id="3c520-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span>

   ![Abbildung of_Microsoft Seite des Defender for Identity-Assistenten, auf der Sie auf die Schaltfläche "Erstellen" klicken sollten](../../media/mtp-eval-43.png)

3. <span data-ttu-id="3c520-174">Wählen **Sie Einen Benutzernamen und ein Kennwort angeben, um eine Verbindung mit Ihrer Active Directory-Gesamtstruktur herzustellen.**</span><span class="sxs-lookup"><span data-stu-id="3c520-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>

   ![Willkommensseite von "Image of_Microsoft Defender for Identity"](../../media/mtp-eval-44.png)

4. <span data-ttu-id="3c520-176">Geben Sie Ihre lokalen Active Directory-Anmeldeinformationen ein.</span><span class="sxs-lookup"><span data-stu-id="3c520-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="3c520-177">Dies kann ein beliebiges Benutzerkonto sein, das Lesezugriff auf Active Directory hat.</span><span class="sxs-lookup"><span data-stu-id="3c520-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Seite "Image of_Microsoft Defender for Identity Directory services", auf der Sie Ihre Anmeldeinformationen ablegen sollten](../../media/mtp-eval-45.png)

5. <span data-ttu-id="3c520-179">Wählen Sie als Nächstes **"Sensorsetup herunterladen"** aus, und übertragen Sie die Datei an Ihren Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="3c520-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Abbildung of_Microsoft Defender for Identity-Seite, auf der Sie "Sensor-Setup herunterladen" auswählen können](../../media/mtp-eval-46.png)

6. <span data-ttu-id="3c520-181">Führen Sie das Microsoft Defender for Identity Sensor-Setup aus, und beginnen Sie mit dem Folgen des Assistenten.</span><span class="sxs-lookup"><span data-stu-id="3c520-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Abbildung of_Microsoft Defender for Identity-Seite, auf der Sie neben klicken sollten, um dem Microsoft Defender for Identity-Sensor-Assistenten zu folgen](../../media/mtp-eval-47.png)

7. <span data-ttu-id="3c520-183">Klicken Sie im Sensorbereitstellungstyp auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="3c520-183">Click **Next** at the sensor deployment type.</span></span>

   ![Abbildung of_Microsoft Defender for Identity-Seite, auf der Sie neben klicken sollten, um zur nächsten Seite zu wechseln](../../media/mtp-eval-48.png)

8. <span data-ttu-id="3c520-185">Kopieren Sie die Zugriffstaste, da Sie sie als Nächstes im Assistenten eingeben müssen.</span><span class="sxs-lookup"><span data-stu-id="3c520-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![Abbildung of_the Sensorseite, auf der Sie die Zugriffstaste kopieren sollten, die Sie auf der nächsten Microsoft Defender for Identity-Assistenten-Assistentenseite eingeben müssen](../../media/mtp-eval-49.png)

9. <span data-ttu-id="3c520-187">Kopieren Sie die Zugriffstaste in den Assistenten, und klicken Sie auf **"Installieren".**</span><span class="sxs-lookup"><span data-stu-id="3c520-187">Copy the access key into the Wizard and click **Install**.</span></span>

   ![Abbildung of_Microsoft Assistentenseite des Defender for Identity-Sensors, auf der Sie die Zugriffstaste bereitstellen und dann auf die Schaltfläche "Installieren" klicken sollten](../../media/mtp-eval-50.png)

10. <span data-ttu-id="3c520-189">Herzlichen Glückwunsch, Sie haben Microsoft Defender for Identity auf Ihrem Domänencontroller erfolgreich konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="3c520-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Abbildung of_Microsoft Abschluss der Installation des Defender for Identity-Sensor-Assistenten, in dem Sie auf die Schaltfläche "Fertig stellen" klicken sollten](../../media/mtp-eval-51.png)

11. <span data-ttu-id="3c520-191">Wählen Sie im Abschnitt ["Einstellungen für Microsoft Defender for Identity"](https://go.microsoft.com/fwlink/?linkid=2040449) \*\*Microsoft Defender für Endpunkt \*\* aus, und aktivieren Sie dann die Umschaltfläche.</span><span class="sxs-lookup"><span data-stu-id="3c520-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="3c520-192">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3c520-192">Click **Save**.</span></span>

    ![Abbildung of_the Einstellungsseite von Microsoft Defender for Identity, auf der Sie die Microsoft Defender für Endpunkt-Umschaltfläche aktivieren sollten](../../media/mtp-eval-52.png)

## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="3c520-194">Konfigurieren Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="3c520-194">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="3c520-195">Überspringen Sie diesen Schritt, wenn Sie Microsoft Cloud App Security bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="3c520-195">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span>

1. <span data-ttu-id="3c520-196">Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info)Weitere  >  **Ressourcen**  >  **Microsoft Cloud App Security**.</span><span class="sxs-lookup"><span data-stu-id="3c520-196">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Abbildung of_Microsoft 365 Security Center-Seite, auf der Sie die Microsoft Cloud App-Karte sehen können und auf die Schaltfläche "Öffnen" klicken sollten](../../media/mtp-eval-53.png)

2. <span data-ttu-id="3c520-198">Wählen Sie an der Informationsaufforderung zum Integrieren von Microsoft Defender for Identity die Option **"Microsoft Defender for Identity-Datenintegration aktivieren"** aus.</span><span class="sxs-lookup"><span data-stu-id="3c520-198">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>

   ![Abbildung of_the Eingabeaufforderung zur Integration von Microsoft Defender for Identity, in der Sie den Link "Microsoft Defender for Identity-Datenintegration aktivieren" auswählen sollten](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="3c520-200">Wenn diese Aufforderung nicht angezeigt wird, bedeutet dies möglicherweise, dass Die Microsoft Defender for Identity-Datenintegration bereits aktiviert wurde.</span><span class="sxs-lookup"><span data-stu-id="3c520-200">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="3c520-201">Wenn Sie sich jedoch nicht sicher sind, wenden Sie sich an Ihren IT-Administrator, um dies zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="3c520-201">However, if you are not sure, contact your IT Administrator to confirm.</span></span>

3. <span data-ttu-id="3c520-202">Wechseln Sie zu **Einstellungen,** aktivieren Sie die **Microsoft Defender for Identity-Integrationsschaltfläche,** und klicken Sie dann auf **"Speichern".**</span><span class="sxs-lookup"><span data-stu-id="3c520-202">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span>

   ![Abbildung of_the Einstellungsseite, auf der Sie die Microsoft Defender for Identity-Integrations-Umschaltfläche aktivieren sollten, und klicken Sie dann auf "Speichern".](../../media/mtp-eval-55.png)

   > [!NOTE]
   > <span data-ttu-id="3c520-204">Bei neuen Microsoft Defender for Identity-Instanzen wird diese Integrationsschaltfläche automatisch aktiviert.</span><span class="sxs-lookup"><span data-stu-id="3c520-204">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="3c520-205">Vergewissern Sie sich, dass Ihre Microsoft Defender for Identity-Integration aktiviert wurde, bevor Sie mit dem nächsten Schritt fortfahren.</span><span class="sxs-lookup"><span data-stu-id="3c520-205">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>

4. <span data-ttu-id="3c520-206">Wählen Sie unter den Cloud-Ermittlungseinstellungen **die Integration von Microsoft Defender für Endpunkt** aus, und aktivieren Sie dann die Integration.</span><span class="sxs-lookup"><span data-stu-id="3c520-206">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="3c520-207">Klicken Sie auf **Speichern**.</span><span class="sxs-lookup"><span data-stu-id="3c520-207">Click **Save**.</span></span>

   ![Abbildung of_the Microsoft Defender für Endpunkt-Seite, auf der das Kontrollkästchen "Nicht autorisierte Apps blockieren" unter Microsoft Defender für Endpunktintegration aktiviert ist.](../../media/mtp-eval-56.png)

5. <span data-ttu-id="3c520-210">Wählen Sie unter "Cloud Discovery"-Einstellungen **"Benutzererweiterung"** aus, und aktivieren Sie dann die Integration mit Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="3c520-210">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![Abbildung des Abschnitts "Benutzeranreicherung", in dem das Kontrollkästchen "Benutzeranreicherung" mit Azure Active Directory Benutzerbezeichner aktiviert ist](../../media/mtp-eval-57.png)

## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="3c520-212">Konfigurieren von Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3c520-212">Configure Microsoft Defender for Endpoint</span></span>

> [!NOTE]
> <span data-ttu-id="3c520-213">Überspringen Sie diesen Schritt, wenn Sie Microsoft Defender für Endpunkt bereits aktiviert haben.</span><span class="sxs-lookup"><span data-stu-id="3c520-213">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="3c520-214">Navigieren Sie zu [Microsoft 365 Security Center](https://security.microsoft.com/info)Weitere  >  **Ressourcen**  >  **Microsoft Defender Security Center**.</span><span class="sxs-lookup"><span data-stu-id="3c520-214">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="3c520-215">Klicken Sie auf **Öffnen**.</span><span class="sxs-lookup"><span data-stu-id="3c520-215">Click **Open**.</span></span>

   ![Abbildung of_Microsoft Defender Security Center-Option auf der Seite Microsoft 365 Security Center](../../media/mtp-eval-58.png)

2. <span data-ttu-id="3c520-217">Folgen Sie dem Microsoft Defender für Endpunkt-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="3c520-217">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="3c520-218">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3c520-218">Click **Next**.</span></span>

   ![Abbildung of_the Microsoft Defender Security Center Willkommens-Assistentenseite](../../media/mtp-eval-59.png)

3. <span data-ttu-id="3c520-220">Wählen Sie basierend auf Ihrem bevorzugten Datenspeicherort, der Datenaufbewahrungsrichtlinie, der Organisationsgröße und dem Opt-In für Vorschaufeatures.</span><span class="sxs-lookup"><span data-stu-id="3c520-220">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![Abbildung of_the Seite, um Ihr Datenspeicherland, Ihre Aufbewahrungsrichtlinie und die Organisationsgröße auszuwählen.](../../media/mtp-eval-60.png)

   > [!NOTE]
   > <span data-ttu-id="3c520-223">Sie können einige Einstellungen, z. B. den Datenspeicherort, danach nicht ändern.</span><span class="sxs-lookup"><span data-stu-id="3c520-223">You cannot change some of the settings, like data storage location, afterwards.</span></span>

   <span data-ttu-id="3c520-224">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="3c520-224">Click **Next**.</span></span>

4. <span data-ttu-id="3c520-225">Klicken Sie auf **"Weiter",** und es wird Ihr Microsoft Defender für Endpunkt-Mandant bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="3c520-225">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![Abbildung of_the Seite, auf der Sie auf die Schaltfläche "Weiter" klicken, um Ihre Cloudinstanz zu erstellen](../../media/mtp-eval-61.png)

5. <span data-ttu-id="3c520-227">Integrieren Sie Ihre Endpunkte über Gruppenrichtlinien, Microsoft Endpoint Manager oder durch Ausführen eines lokalen Skripts in Microsoft Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="3c520-227">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="3c520-228">Der Einfachheit halber wird in diesem Leitfaden das lokale Skript verwendet.</span><span class="sxs-lookup"><span data-stu-id="3c520-228">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="3c520-229">Klicken Sie auf **"Paket herunterladen",** und kopieren Sie das Onboarding-Skript auf Ihre Endpunkte.</span><span class="sxs-lookup"><span data-stu-id="3c520-229">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![Abbildung of_page Aufforderung, auf die Schaltfläche "Paket herunterladen" zu klicken, um das Integrationsskript auf Ihren Endpunkt oder Endpunkt zu kopieren](../../media/mtp-eval-62.png)

7. <span data-ttu-id="3c520-231">Führen Sie auf Ihrem Endpunkt das Onboardingskript als Administrator aus, und wählen Sie "Y" aus.</span><span class="sxs-lookup"><span data-stu-id="3c520-231">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>

   ![Abbildung of_the Befehlszeile, in der Sie das Onboardingskript ausführen, und wählen Sie "Y" aus, um fortzufahren](../../media/mtp-eval-63.png)

8. <span data-ttu-id="3c520-233">Herzlichen Glückwunsch, Sie haben Ihren ersten Endpunkt integriert.</span><span class="sxs-lookup"><span data-stu-id="3c520-233">Congratulations, you've onboarded your first endpoint.</span></span>

   ![Abbildung of_the Befehlszeile, in der Sie die Bestätigung erhalten, dass Sie Ihren ersten Endpunkt integriert haben.](../../media/mtp-eval-64.png)

9. <span data-ttu-id="3c520-236">Kopieren Sie den Erkennungstest aus dem Microsoft Defender für Endpunkt-Assistenten.</span><span class="sxs-lookup"><span data-stu-id="3c520-236">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Abbildung of_the Ausführen eines Erkennungstestschritts, in dem Sie auf "Kopieren" klicken sollten, um das Erkennungstestskript zu kopieren, das Sie in die Eingabeaufforderung einfügen sollten](../../media/mtp-eval-65.png)

10. <span data-ttu-id="3c520-238">Kopieren Sie das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten, und führen Sie es aus.</span><span class="sxs-lookup"><span data-stu-id="3c520-238">Copy the PowerShell script to an elevated command prompt and run it.</span></span>

    ![Abbildung of_command Eingabeaufforderung, in der Sie das PowerShell-Skript in eine Eingabeaufforderung mit erhöhten Rechten kopieren und ausführen sollten](../../media/mtp-eval-66.png)

11. <span data-ttu-id="3c520-240">Wählen Sie **"Start using Microsoft Defender for Endpoint"** aus dem Assistenten aus.</span><span class="sxs-lookup"><span data-stu-id="3c520-240">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![Abbildung of_the Bestätigungsaufforderung des Assistenten, in der Sie auf "Verwenden von Microsoft Defender für Endpunkt starten" klicken sollten](../../media/mtp-eval-67.png)

12. <span data-ttu-id="3c520-242">Besuchen Sie die [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span><span class="sxs-lookup"><span data-stu-id="3c520-242">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="3c520-243">Wechseln Sie zu **Einstellungen,** und wählen Sie dann **erweiterte Features aus.**</span><span class="sxs-lookup"><span data-stu-id="3c520-243">Go to **Settings** and then select **Advanced features**.</span></span>

    ![Image of_Microsoft Defender Security Center Einstellungen Menü, in dem Sie erweiterte Features auswählen sollten](../../media/mtp-eval-68.png)

13. <span data-ttu-id="3c520-245">Aktivieren Sie die Integration in **Microsoft Defender for Identity.**</span><span class="sxs-lookup"><span data-stu-id="3c520-245">Turn on the integration with **Microsoft Defender for Identity**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced-Features, Umschaltfläche der Microsoft Defender for Identity-Option, die Sie aktivieren müssen](../../media/mtp-eval-69.png)

14. <span data-ttu-id="3c520-247">Aktivieren Sie die Integration mit **Office 365 Threat Intelligence.**</span><span class="sxs-lookup"><span data-stu-id="3c520-247">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Erweiterte Features von Image of_Microsoft Defender Security Center Office 365 Option "Threat Intelligence", die Sie aktivieren müssen](../../media/mtp-eval-70.png)

15. <span data-ttu-id="3c520-249">Aktivieren Sie die Integration in **Microsoft Cloud App Security.**</span><span class="sxs-lookup"><span data-stu-id="3c520-249">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center Advanced-Features, Microsoft Cloud App Security Umschaltfläche, die Sie aktivieren müssen](../../media/mtp-eval-71.png)

16. <span data-ttu-id="3c520-251">Scrollen Sie nach unten, und klicken Sie auf **"Einstellungen speichern",** um die neuen Integrationen zu bestätigen.</span><span class="sxs-lookup"><span data-stu-id="3c520-251">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![Bild of_Save Schaltfläche "Einstellungen", auf die Sie klicken müssen](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="3c520-253">Starten des Microsoft 365 Defender-Diensts</span><span class="sxs-lookup"><span data-stu-id="3c520-253">Start the Microsoft 365 Defender service</span></span>

> [!NOTE]
> <span data-ttu-id="3c520-254">Ab dem 1. Juni 2020 aktiviert Microsoft automatisch Microsoft 365 Defender Features für alle berechtigten Mandanten.</span><span class="sxs-lookup"><span data-stu-id="3c520-254">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="3c520-255">Weitere Informationen finden Sie in diesem [Microsoft Tech Community Artikel zur Lizenzberechtigung.](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426)</span><span class="sxs-lookup"><span data-stu-id="3c520-255">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span>

<span data-ttu-id="3c520-256">Wechseln Sie zu [Microsoft 365 Security Center.](https://security.microsoft.com/homepage)</span><span class="sxs-lookup"><span data-stu-id="3c520-256">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="3c520-257">Navigieren Sie zu **Einstellungen,** und wählen Sie dann **Microsoft 365 Defender** aus.</span><span class="sxs-lookup"><span data-stu-id="3c520-257">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![Screenshot der Option of_Microsoft 365 Defender auf der Seite Microsoft 365 Security Center Einstellungen](../../media/mtp-eval-72b.png)

<span data-ttu-id="3c520-259">Eine umfassendere Anleitung finden Sie unter [Aktivieren Microsoft 365 Defender.](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="3c520-259">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="3c520-260">Herzlichen Glückwunsch!</span><span class="sxs-lookup"><span data-stu-id="3c520-260">Congratulations!</span></span> <span data-ttu-id="3c520-261">Sie haben gerade Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung erstellt!</span><span class="sxs-lookup"><span data-stu-id="3c520-261">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="3c520-262">Jetzt können Sie sich mit der Microsoft 365 Defender Benutzeroberfläche vertraut machen!</span><span class="sxs-lookup"><span data-stu-id="3c520-262">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="3c520-263">Erfahren Sie, was Sie aus dem folgenden Microsoft 365 Defender interaktiven Leitfaden lernen und wissen, wie Sie jedes Dashboard für Ihre täglichen Sicherheitsaufgaben verwenden.</span><span class="sxs-lookup"><span data-stu-id="3c520-263">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>

[<span data-ttu-id="3c520-264">Sehen Sie sich den interaktiven Leitfaden an</span><span class="sxs-lookup"><span data-stu-id="3c520-264">Check out the interactive guide</span></span>](https://aka.ms/MTP-Interactive-Guide)

<span data-ttu-id="3c520-265">Als Nächstes können Sie einen Angriff simulieren und sehen, wie die produktübergreifenden Funktionen Warnungen erkennen, erstellen und automatisch auf einen dateilosen Angriff auf einen Endpunkt reagieren.</span><span class="sxs-lookup"><span data-stu-id="3c520-265">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="3c520-266">Nächster Schritt</span><span class="sxs-lookup"><span data-stu-id="3c520-266">Next step</span></span>

- <span data-ttu-id="3c520-267">[Generieren Sie eine Testwarnung–](generate-test-alert.md) Führen Sie eine Angriffssimulation in Ihrem Microsoft 365 Defender Testlabor aus.</span><span class="sxs-lookup"><span data-stu-id="3c520-267">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>
