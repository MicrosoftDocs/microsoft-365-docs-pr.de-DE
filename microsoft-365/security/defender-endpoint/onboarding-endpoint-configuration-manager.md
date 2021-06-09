---
title: Onboarding mithilfe des Microsoft Endpoint Configuration Manager
description: Erfahren Sie, wie Sie das Onboarding in Microsoft Defender für Endpunkt mithilfe von Microsoft Endpoint Configuration Manager
keywords: Onboarding, Konfiguration, bereitstellen, Bereitstellung, Endpunkt-Konfigurations-Manager, Microsoft Defender für Endpunkt, Sammlungserstellung, Endpunkterkennungsantwort, Schutz der nächsten Generation, Verringerung der Angriffsfläche, Microsoft Endpoint Configuration Manager
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: eab23ddeb9011e80cf2835b8d38b2d3fad4b7089
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52843506"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="eba94-104">Onboarding mithilfe des Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eba94-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="eba94-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="eba94-105">**Applies to:**</span></span>
- [<span data-ttu-id="eba94-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eba94-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="eba94-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="eba94-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="eba94-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="eba94-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="eba94-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="eba94-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="eba94-110">Dieser Artikel ist Teil des Bereitstellungshandbuchs und dient als Beispiel für eine Onboardingmethode.</span><span class="sxs-lookup"><span data-stu-id="eba94-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="eba94-111">Im [Thema "Planung"](deployment-strategy.md) wurden verschiedene Methoden zum Onboarding von Geräten in den Dienst bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="eba94-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="eba94-112">In diesem Thema wird die Co-Management-Architektur behandelt.</span><span class="sxs-lookup"><span data-stu-id="eba94-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="eba94-113">![Abbildung der cloudeigenen Architektur ](images/co-management-architecture.png)
 *(Diagramm der Umgebungsarchitekturen)*</span><span class="sxs-lookup"><span data-stu-id="eba94-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="eba94-114">Während Defender für Endpunkt das Onboarding verschiedener Endpunkte und Tools unterstützt, werden diese in diesem Artikel nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="eba94-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="eba94-115">Informationen zum allgemeinen Onboarding mit anderen unterstützten Bereitstellungstools und -methoden finden Sie in der [Onboarding-Übersicht.](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="eba94-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="eba94-116">In diesem Thema werden Benutzer zu folgenden Themen geleitet:</span><span class="sxs-lookup"><span data-stu-id="eba94-116">This topic guides users in:</span></span>
- <span data-ttu-id="eba94-117">Schritt 1: Onboarding Windows Geräte in den Dienst</span><span class="sxs-lookup"><span data-stu-id="eba94-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="eba94-118">Schritt 2: Konfigurieren von Defender für Endpunkt-Funktionen</span><span class="sxs-lookup"><span data-stu-id="eba94-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="eba94-119">Dieser Onboardingleitfaden führt Sie durch die folgenden grundlegenden Schritte, die Sie bei der Verwendung von Microsoft Endpoint Configuration Manager ausführen müssen:</span><span class="sxs-lookup"><span data-stu-id="eba94-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="eba94-120">**Erstellen einer Sammlung in Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="eba94-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="eba94-121">**Konfigurieren von Microsoft Defender für Endpunktfunktionen mit Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="eba94-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="eba94-122">In dieser Beispielbereitstellung werden nur Windows Geräte behandelt.</span><span class="sxs-lookup"><span data-stu-id="eba94-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="eba94-123">Schritt 1: Onboarding von Windows Geräten mit Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="eba94-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="eba94-124">Sammlungserstellung</span><span class="sxs-lookup"><span data-stu-id="eba94-124">Collection creation</span></span>
<span data-ttu-id="eba94-125">Um Windows 10 Geräte mit Microsoft Endpoint Configuration Manager zu integrieren, kann die Bereitstellung auf eine vorhandene Sammlung abzielen, oder eine neue Sammlung kann zu Testzwecken erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="eba94-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="eba94-126">Beim Onboarding mit Tools wie Gruppenrichtlinien oder manuellen Methoden wird kein Agent auf dem System installiert.</span><span class="sxs-lookup"><span data-stu-id="eba94-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="eba94-127">Innerhalb der Microsoft Endpoint Configuration Manager Konsole wird der Onboardingprozess als Teil der Complianceeinstellungen innerhalb der Konsole konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="eba94-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="eba94-128">Jedes System, das diese erforderliche Konfiguration empfängt, behält diese Konfiguration so lange bei, wie der Configuration Manager-Client diese Richtlinie weiterhin vom Verwaltungspunkt erhält.</span><span class="sxs-lookup"><span data-stu-id="eba94-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="eba94-129">Führen Sie die folgenden Schritte aus, um Endpunkte mithilfe von Microsoft Endpoint Configuration Manager zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="eba94-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="eba94-130">Navigieren Sie in Microsoft Endpoint Configuration Manager Konsole zu **\> \> Gerätesammlungen für Objekte und Kompatibilitätsübersicht.**</span><span class="sxs-lookup"><span data-stu-id="eba94-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Abbildung des Assistenten Microsoft Endpoint Configuration Manager 1](images/configmgr-device-collections.png)

2. <span data-ttu-id="eba94-132">Klicken Sie mit der rechten Maustaste auf **"Gerätesammlung",** und wählen **Sie "Gerätesammlung erstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="eba94-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Abbildung von Microsoft Endpoint Configuration Manager Assistenten2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="eba94-134">Geben Sie einen **Namen** und eine **begrenzende Auflistung** an, und wählen Sie dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Abbildung von Microsoft Endpoint Configuration Manager Assistenten3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="eba94-136">Wählen Sie **"Regel hinzufügen"** und dann **"Abfrageregel"** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Abbildung von Microsoft Endpoint Configuration Manager Assistenten4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="eba94-138">Klicken Sie im **Assistenten für** direkte Mitgliedschaft auf **"Weiter",** und klicken Sie auf **"Abfrage-Anweisung bearbeiten".**</span><span class="sxs-lookup"><span data-stu-id="eba94-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Abbildung des Assistenten Microsoft Endpoint Configuration Manager 5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="eba94-140">Wählen Sie **Kriterien** aus, und wählen Sie dann das Sternsymbol aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Abbildung von Microsoft Endpoint Configuration Manager Assistenten6](images/configmgr-criteria.png)

7. <span data-ttu-id="eba94-142">Behalten Sie den Kriterientyp als **einfachen Wert** bei, wählen Sie aus, wo als **Betriebssystem – Buildnummer**, Operator größer als oder gleich und Wert **14393** **ist,** und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="eba94-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Abbildung von Microsoft Endpoint Configuration Manager Assistenten7](images/configmgr-simple-value.png)

8. <span data-ttu-id="eba94-144">Wählen Sie **"Weiter"** und **"Schließen"** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-144">Select **Next** and **Close**.</span></span>

    ![Abbildung von Microsoft Endpoint Configuration Manager Assistenten8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="eba94-146">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="eba94-146">Select **Next**.</span></span>

    ![Abbildung des Assistenten für Microsoft Endpoint Configuration Manager 9](images/configmgr-confirm.png)


<span data-ttu-id="eba94-148">Nach Abschluss dieser Aufgabe verfügen Sie nun über eine Gerätesammlung mit allen Windows 10 Endpunkten in der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="eba94-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="eba94-149">Schritt 2: Konfigurieren der Microsoft Defender für Endpunkt-Funktionen</span><span class="sxs-lookup"><span data-stu-id="eba94-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="eba94-150">In diesem Abschnitt werden Die folgenden Funktionen mithilfe von Microsoft Endpoint Configuration Manager auf Windows Geräten konfiguriert:</span><span class="sxs-lookup"><span data-stu-id="eba94-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="eba94-151">**Erkennung und Reaktion am Endpunkt**</span><span class="sxs-lookup"><span data-stu-id="eba94-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="eba94-152">**Schutzlösungen der nächsten Generation**</span><span class="sxs-lookup"><span data-stu-id="eba94-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="eba94-153">**Verringerung der Angriffsfläche**</span><span class="sxs-lookup"><span data-stu-id="eba94-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="eba94-154">Erkennung und Reaktion am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="eba94-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="eba94-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="eba94-155">Windows 10</span></span>
<span data-ttu-id="eba94-156">Innerhalb der Microsoft Defender Security Center ist es möglich, die Richtlinie ".onboarding" herunterzuladen, mit der die Richtlinie in System Center Configuration Manager erstellt und auf Windows 10 Geräten bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="eba94-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="eba94-157">Wählen Sie in einem Microsoft Defender Security Center-Portal [Einstellungen und dann Onboarding](https://securitycenter.windows.com/preferences2/onboarding)aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="eba94-158">Wählen Sie unter "Bereitstellungsmethode" die unterstützte Version von **Microsoft Endpoint Configuration Manager** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Abbildung des Onboarding-Assistenten für Microsoft Defender für Endpunkt10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="eba94-160">Wählen Sie **"Paket herunterladen" aus.**</span><span class="sxs-lookup"><span data-stu-id="eba94-160">Select **Download package**.</span></span>

    ![Abbildung des Onboarding-Assistenten für Microsoft Defender für Endpunkt11](images/mdatp-download-package.png)

4. <span data-ttu-id="eba94-162">Speichern Sie das Paket an einem zugänglichen Speicherort.</span><span class="sxs-lookup"><span data-stu-id="eba94-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="eba94-163">Navigieren Sie in Microsoft Endpoint Configuration Manager zu: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span><span class="sxs-lookup"><span data-stu-id="eba94-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="eba94-164">Klicken Sie mit der rechten Maustaste auf **Microsoft Defender ATP Richtlinien,** und wählen **Sie Microsoft Defender ATP Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Abbildung von Microsoft Endpoint Configuration Manager Assistenten12](images/configmgr-create-policy.png)

7. <span data-ttu-id="eba94-166">Geben Sie den Namen und die Beschreibung ein, überprüfen Sie, ob **das Onboarding** ausgewählt ist, und wählen Sie dann **"Weiter"** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Abbildung von Microsoft Endpoint Configuration Manager Assistenten13](images/configmgr-policy-name.png)


8. <span data-ttu-id="eba94-168">Klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="eba94-168">Click **Browse**.</span></span>

9. <span data-ttu-id="eba94-169">Navigieren Sie zum Speicherort der heruntergeladenen Datei aus Schritt 4 oben.</span><span class="sxs-lookup"><span data-stu-id="eba94-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="eba94-170">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="eba94-170">Click **Next**.</span></span>
11. <span data-ttu-id="eba94-171">Konfigurieren Sie den Agent mit den entsprechenden Beispielen (**Keine** oder **alle Dateitypen).**</span><span class="sxs-lookup"><span data-stu-id="eba94-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![Abbildung der Konfigurationseinstellungen1](images/configmgr-config-settings.png)

12. <span data-ttu-id="eba94-173">Wählen Sie die entsprechende Telemetrie (**Normal** oder **beschleunigt)** aus, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="eba94-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![Abbildung der Konfigurationseinstellungen2](images/configmgr-telemetry.png)

14. <span data-ttu-id="eba94-175">Überprüfen Sie die Konfiguration, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="eba94-175">Verify the configuration, then click **Next**.</span></span>

     ![Abbildung der Konfigurationseinstellungen3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="eba94-177">Klicken Sie auf **"Schließen",** wenn der Assistent abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="eba94-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="eba94-178">Klicken Sie in der konsole Microsoft Endpoint Configuration Manager mit der rechten Maustaste auf die soeben erstellte Defender für Endpunkt-Richtlinie, und wählen Sie **"Bereitstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="eba94-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![Abbildung der Konfigurationseinstellungen4](images/configmgr-deploy.png)

17. <span data-ttu-id="eba94-180">Wählen Sie im rechten Bereich die zuvor erstellte Sammlung aus, und klicken Sie auf **"OK".**</span><span class="sxs-lookup"><span data-stu-id="eba94-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![Abbildung der Konfigurationseinstellungen5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="eba94-182">Frühere Versionen von Windows Client (Windows 7 und Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="eba94-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="eba94-183">Führen Sie die folgenden Schritte aus, um die Defender für Endpunkt-Arbeitsbereichs-ID und den Arbeitsbereichsschlüssel zu identifizieren, die für das Onboarding früherer Versionen von Windows erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="eba94-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="eba94-184">Wählen Sie in einem Microsoft Defender Security Center-Portal **Einstellungen > Onboarding** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="eba94-185">Wählen Sie unter Betriebssystem **Windows 7 SP1 und 8.1** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="eba94-186">Kopieren Sie die **Arbeitsbereichs-ID** und den **Arbeitsbereichsschlüssel,** und speichern Sie sie.</span><span class="sxs-lookup"><span data-stu-id="eba94-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="eba94-187">Sie werden später im Prozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="eba94-187">They will be used later in the process.</span></span>

    ![Abbildung des Onboardings](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="eba94-189">Installieren Sie die Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="eba94-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="eba94-190">MMA wird derzeit (ab Januar 2019) unter den folgenden Windows Betriebssystemen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="eba94-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="eba94-191">Server-SKUs: Windows Server 2008 SP1 oder höher</span><span class="sxs-lookup"><span data-stu-id="eba94-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="eba94-192">Client-SKUs: Windows 7 SP1 und höher</span><span class="sxs-lookup"><span data-stu-id="eba94-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="eba94-193">Der MMA-Agent muss auf Windows Geräten installiert werden.</span><span class="sxs-lookup"><span data-stu-id="eba94-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="eba94-194">Um den Agent zu installieren, müssen einige Systeme das [Update für Kundenerfahrung und Diagnosetelemetrie](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) herunterladen, um die Daten mit MMA zu sammeln.</span><span class="sxs-lookup"><span data-stu-id="eba94-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="eba94-195">Diese Systemversionen umfassen unter anderem Folgendes:</span><span class="sxs-lookup"><span data-stu-id="eba94-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="eba94-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="eba94-196">Windows 8.1</span></span>

    -   <span data-ttu-id="eba94-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="eba94-197">Windows 7</span></span>

    -   <span data-ttu-id="eba94-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="eba94-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="eba94-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="eba94-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="eba94-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="eba94-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="eba94-201">Insbesondere für Windows 7 SP1 müssen die folgenden Patches installiert werden:</span><span class="sxs-lookup"><span data-stu-id="eba94-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="eba94-202">Installieren von [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="eba94-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="eba94-203">Installieren Sie entweder [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (oder höher) **oder** 
         [KB3154518.](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework)</span><span class="sxs-lookup"><span data-stu-id="eba94-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="eba94-204">Installieren Sie nicht beide auf demselben System.</span><span class="sxs-lookup"><span data-stu-id="eba94-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="eba94-205">Wenn Sie einen Proxy zum Herstellen einer Verbindung mit dem Internet verwenden, lesen Sie den Abschnitt "Proxyeinstellungen konfigurieren".</span><span class="sxs-lookup"><span data-stu-id="eba94-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="eba94-206">Nach Abschluss des Vorgangs sollten innerhalb einer Stunde integrierte Endpunkte im Portal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="eba94-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="eba94-207">Schutz der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="eba94-207">Next generation protection</span></span> 
<span data-ttu-id="eba94-208">Microsoft Defender Antivirus ist eine integrierte Lösung zur Bekämpfung von Schadsoftware, die Schutz der nächsten Generation für Desktops, tragbare Computer und Server bietet.</span><span class="sxs-lookup"><span data-stu-id="eba94-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="eba94-209">Navigieren Sie in der konsole Microsoft Endpoint Configuration Manager zu **Ressourcen und \> Complianceübersicht Endpoint Protection \> \> Antischadsoftwarerichtlinien,** und wählen **Sie "Antischadsoftwarerichtlinie erstellen"** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![Abbildung der Antischadsoftwarerichtlinie](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="eba94-211">Wählen Sie **geplante Scans**, **Scaneinstellungen**, **Standardaktionen**, **Echtzeitschutz**, **Ausschlusseinstellungen**, **Erweitert**, **Außerkraftsetzungen von Bedrohungen**, **Cloud Protection Service** und Security **Intelligence-Updates** aus, und wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![Abbildung des Schutzbereichs1 der nächsten Generation](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="eba94-213">In bestimmten Branchen oder einigen ausgewählten Unternehmen haben Kunden möglicherweise bestimmte Anforderungen an die Konfiguration von Antivirus.</span><span class="sxs-lookup"><span data-stu-id="eba94-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="eba94-214">Schnellscan im Vergleich zum vollständigen Scan und benutzerdefinierter Scan</span><span class="sxs-lookup"><span data-stu-id="eba94-214">Quick scan versus full scan and custom scan</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="eba94-215">Weitere Informationen finden Sie unter [Windows-Sicherheit Konfigurationsframework.](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="eba94-215">For more details, see [Windows Security configuration framework](/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![Abbildung des Schutzbereichs2 der nächsten Generation](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Abbildung des Schutzbereichs3 der nächsten Generation](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Abbildung des Schutzbereichs der nächsten Generation4](images/a28afc02c1940d5220b233640364970c.png)

    ![Abbildung des Schutzbereichs5 der nächsten Generation](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Abbildung des Schutzbereichs der nächsten Generation6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Abbildung des Schutzes der nächsten Generation7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Abbildung des Schutzbereichs8 der nächsten Generation](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Abbildung des Schutzbereichs der nächsten Generation9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="eba94-224">Klicken Sie mit der rechten Maustaste auf die neu erstellte Antischadsoftwarerichtlinie, und wählen Sie **"Bereitstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="eba94-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![Abbildung des Schutzbereichs der nächsten Generation10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="eba94-226">Richten Sie die neue Antischadsoftwarerichtlinie an Ihre Windows 10-Sammlung aus, und klicken Sie auf **"OK".**</span><span class="sxs-lookup"><span data-stu-id="eba94-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![Abbildung des Schutzbereichs der nächsten Generation11](images/configmgr-select-collection.png)

<span data-ttu-id="eba94-228">Nachdem Sie diese Aufgabe abgeschlossen haben, haben Sie nun Windows Defender Antivirus erfolgreich konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="eba94-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="eba94-229">Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="eba94-229">Attack surface reduction</span></span>
<span data-ttu-id="eba94-230">Die Attack Surface Reduction-Säule von Defender für Endpunkt umfasst den Featuresatz, der unter Exploit Guard verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="eba94-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="eba94-231">Attack Surface Reduction (ASR)-Regeln, kontrollierter Ordnerzugriff, Netzwerkschutz und Exploit-Schutz.</span><span class="sxs-lookup"><span data-stu-id="eba94-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="eba94-232">Alle diese Features bieten einen Überwachungsmodus und einen Blockierungsmodus.</span><span class="sxs-lookup"><span data-stu-id="eba94-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="eba94-233">Im Überwachungsmodus gibt es keine Auswirkungen auf endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="eba94-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="eba94-234">Sie sammeln nur zusätzliche Telemetriedaten und stellen sie im Microsoft Defender Security Center zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="eba94-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="eba94-235">Das Ziel bei einer Bereitstellung ist das schrittweise Verschieben von Sicherheitssteuerelementen in den Blockierungsmodus.</span><span class="sxs-lookup"><span data-stu-id="eba94-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="eba94-236">So legen Sie ASR-Regeln im Überwachungsmodus fest:</span><span class="sxs-lookup"><span data-stu-id="eba94-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="eba94-237">Navigieren Sie in der konsole Microsoft Endpoint Configuration Manager zu **Ressourcen und \> Complianceübersicht Endpoint Protection Windows Defender Exploit \> \> Guard,** und wählen **Sie Exploit Guard-Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Abbildung von Microsoft Endpoint Configuration Manager Konsole0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="eba94-239">Wählen Sie **Attack Surface Reduction aus.**</span><span class="sxs-lookup"><span data-stu-id="eba94-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="eba94-240">Legen Sie Regeln zum **Überwachen fest,** und klicken Sie auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="eba94-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Abbildung von Microsoft Endpoint Configuration Manager Konsole1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="eba94-242">Bestätigen Sie die neue Exploit Guard-Richtlinie, indem Sie auf **"Weiter"** klicken.</span><span class="sxs-lookup"><span data-stu-id="eba94-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Abbildung von Microsoft Endpoint Configuration Manager Konsole2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="eba94-244">Nachdem die Richtlinie erstellt wurde, klicken Sie auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="eba94-244">Once the policy is created click **Close**.</span></span>

    ![Abbildung von Microsoft Endpoint Configuration Manager Konsole3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Abbildung von Microsoft Endpoint Manager Konsole1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="eba94-247">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und wählen Sie **"Bereitstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="eba94-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Abbildung von Microsoft Endpoint Configuration Manager Konsole4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="eba94-249">Legen Sie die Richtlinie auf die neu erstellte Windows 10 sammlung fest, und klicken Sie auf **"OK".**</span><span class="sxs-lookup"><span data-stu-id="eba94-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Abbildung von Microsoft Endpoint Configuration Manager Konsole5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="eba94-251">Nachdem Sie diese Aufgabe abgeschlossen haben, haben Sie die ASR-Regeln jetzt erfolgreich im Überwachungsmodus konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="eba94-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="eba94-252">Nachfolgend finden Sie zusätzliche Schritte, um zu überprüfen, ob ASR-Regeln korrekt auf Endpunkte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="eba94-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="eba94-253">(Dies kann einige Minuten dauern.)</span><span class="sxs-lookup"><span data-stu-id="eba94-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="eba94-254">Navigieren Sie in einem Webbrowser zu <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="eba94-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="eba94-255">Wählen Sie im linken Menü die **Option "Konfigurationsverwaltung"** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="eba94-256">Klicken Sie im Verwaltungsbereich "Angriffsoberfläche" auf **"Zur Angriffsflächenverwaltung** wechseln".</span><span class="sxs-lookup"><span data-stu-id="eba94-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![Abbildung der Angriffsflächenverwaltung](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="eba94-258">Klicken Sie auf die Registerkarte **"Konfiguration"** in den Berichten zu Attack Surface Reduction-Regeln.</span><span class="sxs-lookup"><span data-stu-id="eba94-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="eba94-259">Es enthält eine Übersicht über die ASR-Regelkonfiguration und den ASR-Regelstatus auf jedem Gerät.</span><span class="sxs-lookup"><span data-stu-id="eba94-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![Screenshot der Berichte zu Attack Surface Reduction-Regeln1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="eba94-261">Klicken Sie auf jedes Gerät, um Konfigurationsdetails der ASR-Regeln anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="eba94-261">Click each device shows configuration details of ASR rules.</span></span>

    ![Screenshot der Berichte zu Attack Surface Reduction-Regeln2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="eba94-263">Weitere Informationen finden Sie unter Optimieren der [BEREITSTELLUNG und Erkennung von ASR-Regeln.](/microsoft-365/security/defender-endpoint/configure-machines-asr)</span><span class="sxs-lookup"><span data-stu-id="eba94-263">See [Optimize ASR rule deployment and detections](/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="eba94-264">Festlegen von Netzwerkschutzregeln im Überwachungsmodus:</span><span class="sxs-lookup"><span data-stu-id="eba94-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="eba94-265">Navigieren Sie in der konsole Microsoft Endpoint Configuration Manager zu **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard,** und wählen **Sie Exploit Guard-Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Screenshot System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="eba94-267">Wählen Sie **"Netzwerkschutz"** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="eba94-268">Legen Sie die Einstellung auf **"Überwachen"** fest, und klicken Sie auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="eba94-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![Screenshot System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="eba94-270">Bestätigen Sie die neue Exploit Guard-Richtlinie, indem Sie auf **"Weiter"** klicken.</span><span class="sxs-lookup"><span data-stu-id="eba94-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![Screenshot exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="eba94-272">Klicken Sie nach dem Erstellen der Richtlinie auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="eba94-272">Once the policy is created click on **Close**.</span></span>

    ![Screenshot exploit GUard policy2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="eba94-274">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und wählen Sie **"Bereitstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="eba94-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="eba94-276">Wählen Sie die Richtlinie für die neu erstellte Windows 10 sammlung aus, und wählen Sie **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="eba94-278">Nachdem Sie diese Aufgabe abgeschlossen haben, haben Sie den Netzwerkschutz jetzt erfolgreich im Überwachungsmodus konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="eba94-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="eba94-279">So legen Sie regeln für den kontrollierten Ordnerzugriff im Überwachungsmodus fest:</span><span class="sxs-lookup"><span data-stu-id="eba94-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="eba94-280">Navigieren Sie in der konsole Microsoft Endpoint Configuration Manager zu **Ressourcen und \> Complianceübersicht Endpoint Protection Windows Defender Exploit \> \> Guard,** und wählen **Sie Exploit Guard-Richtlinie erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="eba94-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="eba94-282">Wählen Sie **den kontrollierten Ordnerzugriff aus.**</span><span class="sxs-lookup"><span data-stu-id="eba94-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="eba94-283">Legen Sie die Konfiguration auf **"Überwachen"** fest, und klicken Sie auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="eba94-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="eba94-285">Bestätigen Sie die neue Exploit Guard-Richtlinie, indem Sie auf **"Weiter"** klicken.</span><span class="sxs-lookup"><span data-stu-id="eba94-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="eba94-287">Klicken Sie nach dem Erstellen der Richtlinie auf **"Schließen".**</span><span class="sxs-lookup"><span data-stu-id="eba94-287">Once the policy is created click on **Close**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="eba94-289">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und wählen Sie **"Bereitstellen" aus.**</span><span class="sxs-lookup"><span data-stu-id="eba94-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="eba94-291">Legen Sie die Richtlinie auf die neu erstellte Windows 10 sammlung fest, und klicken Sie auf **"OK".**</span><span class="sxs-lookup"><span data-stu-id="eba94-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="eba94-293">Sie haben nun den kontrollierten Ordnerzugriff im Überwachungsmodus erfolgreich konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="eba94-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="eba94-294">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="eba94-294">Related topic</span></span>
- [<span data-ttu-id="eba94-295">Onboarding mithilfe des Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="eba94-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
