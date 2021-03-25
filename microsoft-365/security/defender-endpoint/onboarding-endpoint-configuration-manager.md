---
title: Onboarding mit Microsoft Endpoint Configuration Manager
description: Informationen zum Onboarding in Microsoft Defender for Endpoint mithilfe von Microsoft Endpoint Configuration Manager
keywords: onboarding, configuration, deploy, deployment, endpoint configuration manager, mdatp, advanced threat protection, collection creation, endpoint detection response, next generation protection, attack surface reduction, microsoft endpoint configuration manager
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
ms.openlocfilehash: 31c946ccad84aca3b2fc86c95655cea9e66e182f
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186401"
---
# <a name="onboarding-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="9fc9f-104">Onboarding mit Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9fc9f-104">Onboarding using Microsoft Endpoint Configuration Manager</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9fc9f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-105">**Applies to:**</span></span>
- [<span data-ttu-id="9fc9f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9fc9f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="9fc9f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9fc9f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="9fc9f-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9fc9f-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="9fc9f-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="9fc9f-110">Dieser Artikel ist Teil des Bereitstellungshandbuchs und dient als Beispiel für ein Onboarding.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-110">This article is part of the Deployment guide and acts as an example onboarding method.</span></span> 

<span data-ttu-id="9fc9f-111">Im Thema [Planning](deployment-strategy.md) wurden verschiedene Methoden zum Onboarding von Geräten in den Dienst bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-111">In the [Planning](deployment-strategy.md) topic, there were several methods provided to onboard devices to the service.</span></span> <span data-ttu-id="9fc9f-112">In diesem Thema wird die Architektur der gemeinsamen Verwaltung behandelt.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-112">This topic covers the co-management architecture.</span></span> 

<span data-ttu-id="9fc9f-113">![Abbildung der cloudeigenen Architektur ](images/co-management-architecture.png)
 *Diagramm der Umgebungsarchitekturen*</span><span class="sxs-lookup"><span data-stu-id="9fc9f-113">![Image of cloud-native architecture](images/co-management-architecture.png)
*Diagram of environment architectures*</span></span>


<span data-ttu-id="9fc9f-114">Während Defender for Endpoint das Onboarding verschiedener Endpunkte und Tools unterstützt, werden diese in diesem Artikel nicht behandelt.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-114">While Defender for Endpoint supports onboarding of various endpoints and tools, this article does not cover them.</span></span> <span data-ttu-id="9fc9f-115">Informationen zum allgemeinen Onboarding mit anderen unterstützten Bereitstellungstools und -methoden finden Sie unter [Onboarding overview](onboarding.md).</span><span class="sxs-lookup"><span data-stu-id="9fc9f-115">For information on general onboarding using other supported deployment tools and methods, see [Onboarding overview](onboarding.md).</span></span>



<span data-ttu-id="9fc9f-116">In diesem Thema werden Benutzer in den themen:</span><span class="sxs-lookup"><span data-stu-id="9fc9f-116">This topic guides users in:</span></span>
- <span data-ttu-id="9fc9f-117">Schritt 1: Onboarding von Windows-Geräten in den Dienst</span><span class="sxs-lookup"><span data-stu-id="9fc9f-117">Step 1: Onboarding Windows devices to the service</span></span> 
- <span data-ttu-id="9fc9f-118">Schritt 2: Konfigurieren von Defender for Endpoint-Funktionen</span><span class="sxs-lookup"><span data-stu-id="9fc9f-118">Step 2: Configuring Defender for Endpoint capabilities</span></span>

<span data-ttu-id="9fc9f-119">In diesem Onboardingleitfaden werden Sie durch die folgenden grundlegenden Schritte geleitet, die Sie bei der Verwendung von Microsoft Endpoint Configuration Manager ausführen müssen:</span><span class="sxs-lookup"><span data-stu-id="9fc9f-119">This onboarding guidance will walk you through the following basic steps that you need to take when using Microsoft Endpoint Configuration Manager:</span></span>
- <span data-ttu-id="9fc9f-120">**Erstellen einer Auflistung in Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-120">**Creating a collection in Microsoft Endpoint Configuration Manager**</span></span>
- <span data-ttu-id="9fc9f-121">**Konfigurieren von Microsoft Defender for Endpoint-Funktionen mithilfe von Microsoft Endpoint Configuration Manager**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-121">**Configuring Microsoft Defender for Endpoint capabilities using Microsoft Endpoint Configuration Manager**</span></span>

>[!NOTE]
><span data-ttu-id="9fc9f-122">In dieser Beispielbereitstellung werden nur Windows-Geräte behandelt.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-122">Only Windows devices are covered in this example deployment.</span></span> 



## <a name="step-1-onboard-windows-devices-using-microsoft-endpoint-configuration-manager"></a><span data-ttu-id="9fc9f-123">Schritt 1: Onboarding von Windows-Geräten mit Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="9fc9f-123">Step 1: Onboard Windows devices using Microsoft Endpoint Configuration Manager</span></span>

### <a name="collection-creation"></a><span data-ttu-id="9fc9f-124">Sammlungserstellung</span><span class="sxs-lookup"><span data-stu-id="9fc9f-124">Collection creation</span></span>
<span data-ttu-id="9fc9f-125">Um Windows 10-Geräte mit Microsoft Endpoint Configuration Manager zu integrieren, kann die Bereitstellung auf eine vorhandene Auflistung oder eine neue Auflistung für Tests verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-125">To onboard Windows 10 devices with Microsoft Endpoint Configuration Manager, the deployment can target an existing collection or a new collection can be created for testing.</span></span> 

<span data-ttu-id="9fc9f-126">Beim Onboarding mithilfe von Tools wie Gruppenrichtlinien oder manuellen Methoden wird kein Agent auf dem System installiert.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-126">Onboarding using tools such as Group policy or manual method does not install any agent on the system.</span></span> 

<span data-ttu-id="9fc9f-127">In der Microsoft Endpoint Configuration Manager-Konsole wird der Onboardingprozess als Teil der Kompatibilitätseinstellungen in der Konsole konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-127">Within the Microsoft Endpoint Configuration Manager console the onboarding process will be configured as part of the compliance settings within the console.</span></span>

<span data-ttu-id="9fc9f-128">Jedes System, das diese erforderliche Konfiguration empfängt, wird diese Konfiguration beibehalten, solange der Configuration Manager-Client diese Richtlinie weiterhin vom Verwaltungspunkt empfängt.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-128">Any system that receives this required configuration will maintain that configuration for as long as the Configuration Manager client continues to receive this policy from the management point.</span></span> 

<span data-ttu-id="9fc9f-129">Führen Sie die folgenden Schritte aus, um Endpunkte mithilfe von Microsoft Endpoint Configuration Manager zu integrieren.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-129">Follow the steps below to onboard endpoints using Microsoft Endpoint Configuration Manager.</span></span>

1. <span data-ttu-id="9fc9f-130">Navigieren Sie in der Microsoft Endpoint Configuration Manager-Konsole zu **Assets and Compliance Overview Device \> \> Collections**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-130">In Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Device Collections**.</span></span>            

    ![Abbildung des Microsoft Endpoint Configuration Manager-Assistenten1](images/configmgr-device-collections.png)

2. <span data-ttu-id="9fc9f-132">Klicken Sie mit **der rechten Maustaste auf Gerätesammlung,** und wählen Sie **Gerätesammlung erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-132">Right Click **Device Collection** and select **Create Device Collection**.</span></span>

    ![Abbildung des Microsoft Endpoint Configuration Manager-Assistenten2](images/configmgr-create-device-collection.png)

3. <span data-ttu-id="9fc9f-134">Geben Sie **einen Namen und** eine **Einschränkende Auflistung an,** und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-134">Provide a **Name** and **Limiting Collection**, then select **Next**.</span></span>

    ![Abbildung des Microsoft Endpoint Configuration Manager-Assistenten3](images/configmgr-limiting-collection.png)

4. <span data-ttu-id="9fc9f-136">Wählen **Sie Regel hinzufügen** aus, und wählen Sie **Abfrageregel aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-136">Select **Add Rule** and choose **Query Rule**.</span></span>

    ![Abbildung des Microsoft Endpoint Configuration Manager-Assistenten4](images/configmgr-query-rule.png)

5.  <span data-ttu-id="9fc9f-138">Klicken **Sie im** Assistenten für direkte **Mitgliedschaft** auf Weiter, und klicken Sie auf **Abfrageanweisung bearbeiten.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-138">Click **Next** on the **Direct Membership Wizard** and click on **Edit Query Statement**.</span></span>

     ![Abbildung des Microsoft Endpoint Configuration Manager-Assistenten5](images/configmgr-direct-membership.png)

6. <span data-ttu-id="9fc9f-140">Wählen **Sie Kriterien** aus, und wählen Sie dann das Sternsymbol aus.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-140">Select **Criteria** and then choose the star icon.</span></span>

     ![Abbildung des Microsoft Endpoint Configuration Manager-Assistenten6](images/configmgr-criteria.png)

7. <span data-ttu-id="9fc9f-142">Halten Sie den Kriterientyp als einfachen **Wert,** wählen  Sie als Betriebssystem **- Buildnummer**, Operator, größer oder gleich und Wert **14393** aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-142">Keep criterion type as **simple value**, choose where as **Operating System - build number**, operator as **is greater than or equal to** and value **14393** and click on **OK**.</span></span>

    ![Abbildung des Microsoft Endpoint Configuration Manager-Assistenten7](images/configmgr-simple-value.png)

8. <span data-ttu-id="9fc9f-144">Wählen **Sie Weiter** und Schließen **aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-144">Select **Next** and **Close**.</span></span>

    ![Abbildung des Microsoft Endpoint Configuration Manager-Assistenten8](images/configmgr-membership-rules.png)

9. <span data-ttu-id="9fc9f-146">Wählen Sie **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-146">Select **Next**.</span></span>

    ![Abbildung des Microsoft Endpoint Configuration Manager-Assistenten9](images/configmgr-confirm.png)


<span data-ttu-id="9fc9f-148">Nachdem Sie diese Aufgabe abgeschlossen haben, verfügen Sie nun über eine Gerätesammlung mit allen Windows 10-Endpunkten in der Umgebung.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-148">After completing this task, you now have a device collection with all the Windows 10 endpoints in the environment.</span></span> 


## <a name="step-2-configure-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="9fc9f-149">Schritt 2: Konfigurieren von Microsoft Defender for Endpoint-Funktionen</span><span class="sxs-lookup"><span data-stu-id="9fc9f-149">Step 2: Configure Microsoft Defender for Endpoint capabilities</span></span> 
<span data-ttu-id="9fc9f-150">In diesem Abschnitt werden Sie beim Konfigurieren der folgenden Funktionen mithilfe von Microsoft Endpoint Configuration Manager auf Windows-Geräten unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9fc9f-150">This section guides you in configuring the following capabilities using Microsoft Endpoint Configuration Manager on Windows devices:</span></span>

- [<span data-ttu-id="9fc9f-151">**Endpunkterkennung und -antwort**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-151">**Endpoint detection and response**</span></span>](#endpoint-detection-and-response)
- [<span data-ttu-id="9fc9f-152">**Schutz der nächsten Generation**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-152">**Next-generation protection**</span></span>](#next-generation-protection)
- [<span data-ttu-id="9fc9f-153">**Reduzierung der Angriffsfläche**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-153">**Attack surface reduction**</span></span>](#attack-surface-reduction)


### <a name="endpoint-detection-and-response"></a><span data-ttu-id="9fc9f-154">Erkennung und Reaktion am Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9fc9f-154">Endpoint detection and response</span></span>
#### <a name="windows-10"></a><span data-ttu-id="9fc9f-155">Windows 10</span><span class="sxs-lookup"><span data-stu-id="9fc9f-155">Windows 10</span></span>
<span data-ttu-id="9fc9f-156">Im Microsoft Defender Security Center können Sie die Richtlinie ".onboarding" herunterladen, mit der die Richtlinie im System Center Configuration Manager erstellt und auf Windows 10-Geräten bereitgestellt werden kann.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-156">From within the Microsoft Defender Security Center it is possible to download the '.onboarding' policy that can be used to create the policy in System Center Configuration Manager and deploy that policy to Windows 10 devices.</span></span>

1. <span data-ttu-id="9fc9f-157">Wählen Sie in einem Microsoft Defender Security Center-Portal [Einstellungen und dann Onboarding aus.](https://securitycenter.windows.com/preferences2/onboarding)</span><span class="sxs-lookup"><span data-stu-id="9fc9f-157">From a Microsoft Defender Security Center Portal, select [Settings and then Onboarding](https://securitycenter.windows.com/preferences2/onboarding).</span></span>



2. <span data-ttu-id="9fc9f-158">Wählen Sie unter Bereitstellungsmethode die unterstützte Version von **Microsoft Endpoint Configuration Manager aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-158">Under Deployment method select the supported version of **Microsoft Endpoint Configuration Manager**.</span></span>

    ![Abbildung des Microsoft Defender for Endpoint-Onboarding-Assistenten10](images/mdatp-onboarding-wizard.png)

3. <span data-ttu-id="9fc9f-160">Wählen **Sie Paket herunterladen aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-160">Select **Download package**.</span></span>

    ![Abbildung des Microsoft Defender for Endpoint-Onboarding-Assistenten11](images/mdatp-download-package.png)

4. <span data-ttu-id="9fc9f-162">Speichern Sie das Paket an einem barrierefreien Speicherort.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-162">Save the package to an accessible location.</span></span>
5. <span data-ttu-id="9fc9f-163">Navigieren Sie in Microsoft Endpoint Configuration Manager zu: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-163">In  Microsoft Endpoint Configuration Manager, navigate to: **Assets and Compliance > Overview > Endpoint Protection > Microsoft Defender ATP Policies**.</span></span>

6. <span data-ttu-id="9fc9f-164">Klicken Sie mit der rechten **Maustaste auf Microsoft Defender ATP-Richtlinien,** und wählen Sie Microsoft Defender **ATP-Richtlinie erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-164">Right-click **Microsoft Defender ATP Policies** and select **Create Microsoft Defender ATP Policy**.</span></span>

    ![Abbildung des Microsoft Endpoint Configuration Manager-Assistenten12](images/configmgr-create-policy.png)

7. <span data-ttu-id="9fc9f-166">Geben Sie den Namen und die Beschreibung ein, überprüfen Sie, ob **onboarding** ausgewählt ist, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-166">Enter the name and description, verify **Onboarding** is selected, then select **Next**.</span></span>

    ![Abbildung des Microsoft Endpoint Configuration Manager-Assistenten13](images/configmgr-policy-name.png)


8. <span data-ttu-id="9fc9f-168">Klicken Sie auf **Durchsuchen**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-168">Click **Browse**.</span></span>

9. <span data-ttu-id="9fc9f-169">Navigieren Sie aus Schritt 4 oben zum Speicherort der heruntergeladenen Datei.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-169">Navigate to the location of the downloaded file from step 4 above.</span></span>

10. <span data-ttu-id="9fc9f-170">Klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-170">Click **Next**.</span></span>
11. <span data-ttu-id="9fc9f-171">Konfigurieren Sie den Agent mit den entsprechenden Beispielen (**Keine** oder **Alle Dateitypen**).</span><span class="sxs-lookup"><span data-stu-id="9fc9f-171">Configure the Agent with the appropriate samples (**None** or **All file types**).</span></span>

    ![Abbildung der Konfigurationseinstellungen1](images/configmgr-config-settings.png)

12. <span data-ttu-id="9fc9f-173">Wählen Sie die entsprechende Telemetrie (**Normal** oder **Expedited**) aus, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-173">Select the appropriate telemetry (**Normal** or **Expedited**) then click **Next**.</span></span>

    ![Abbildung der Konfigurationseinstellungen2](images/configmgr-telemetry.png)

14. <span data-ttu-id="9fc9f-175">Überprüfen Sie die Konfiguration, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-175">Verify the configuration, then click **Next**.</span></span>

     ![Abbildung der Konfigurationseinstellungen3](images/configmgr-verify-configuration.png)

15. <span data-ttu-id="9fc9f-177">Klicken **Sie auf Schließen,** wenn der Assistent abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-177">Click **Close** when the Wizard completes.</span></span>

16.  <span data-ttu-id="9fc9f-178">Klicken Sie in der Microsoft Endpoint Configuration Manager-Konsole mit der rechten Maustaste auf die gerade erstellte Defender for Endpoint-Richtlinie, und wählen Sie **Bereitstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-178">In the Microsoft Endpoint Configuration Manager console, right-click the Defender for Endpoint policy you just created and select **Deploy**.</span></span>

     ![Abbildung der Konfigurationseinstellungen4](images/configmgr-deploy.png)

17. <span data-ttu-id="9fc9f-180">Wählen Sie im rechten Bereich die zuvor erstellte Auflistung aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-180">On the right panel, select the previously created collection and click **OK**.</span></span>

    ![Abbildung der Konfigurationseinstellungen5](images/configmgr-select-collection.png)


#### <a name="previous-versions-of-windows-client-windows-7-and-windows-81"></a><span data-ttu-id="9fc9f-182">Frühere Versionen von Windows Client (Windows 7 und Windows 8.1)</span><span class="sxs-lookup"><span data-stu-id="9fc9f-182">Previous versions of Windows Client (Windows 7 and Windows 8.1)</span></span>
<span data-ttu-id="9fc9f-183">Führen Sie die folgenden Schritte aus, um die Defender for Endpoint Workspace ID und den Arbeitsbereichsschlüssel zu identifizieren, die für das Onboarding früherer Versionen von Windows erforderlich sind.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-183">Follow the steps below to identify the Defender for Endpoint Workspace ID and Workspace Key, that will be required for the onboarding of previous versions of Windows.</span></span>

1. <span data-ttu-id="9fc9f-184">Wählen Sie in einem Microsoft Defender Security Center-Portal Einstellungen **> Onboarding aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-184">From a Microsoft Defender Security Center Portal, select **Settings > Onboarding**.</span></span>

2. <span data-ttu-id="9fc9f-185">Wählen Sie unter Betriebssystem **Windows 7 SP1 und 8.1 aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-185">Under operating system choose **Windows 7 SP1 and 8.1**.</span></span>

3. <span data-ttu-id="9fc9f-186">Kopieren Sie **die Arbeitsbereichs-ID** und **den Arbeitsbereichsschlüssel,** und speichern Sie sie.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-186">Copy the **Workspace ID** and **Workspace Key** and save them.</span></span> <span data-ttu-id="9fc9f-187">Sie werden später im Prozess verwendet.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-187">They will be used later in the process.</span></span>

    ![Abbildung des Onboardings](images/91b738e4b97c4272fd6d438d8c2d5269.png)

4. <span data-ttu-id="9fc9f-189">Installieren Sie den Microsoft Monitoring Agent (MMA).</span><span class="sxs-lookup"><span data-stu-id="9fc9f-189">Install the Microsoft Monitoring Agent (MMA).</span></span> <br>
    <span data-ttu-id="9fc9f-190">MMA wird derzeit (ab Januar 2019) unter den folgenden Windows-Betriebssystemen unterstützt:</span><span class="sxs-lookup"><span data-stu-id="9fc9f-190">MMA is currently (as of January 2019) supported on the following Windows Operating Systems:</span></span>

    -   <span data-ttu-id="9fc9f-191">Server-SKUs: Windows Server 2008 SP1 oder neuer</span><span class="sxs-lookup"><span data-stu-id="9fc9f-191">Server SKUs: Windows Server 2008 SP1 or Newer</span></span>

    -   <span data-ttu-id="9fc9f-192">Client-SKUs: Windows 7 SP1 und höher</span><span class="sxs-lookup"><span data-stu-id="9fc9f-192">Client SKUs: Windows 7 SP1 and later</span></span>

    <span data-ttu-id="9fc9f-193">Der MMA-Agent muss auf Windows-Geräten installiert werden.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-193">The MMA agent will need to be installed on Windows devices.</span></span> <span data-ttu-id="9fc9f-194">Zum Installieren des Agents müssen einige Systeme das [Update](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) für die Benutzererfahrung und die Diagnosetelemetrie herunterladen, um die Daten mit MMA zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-194">To install the agent, some systems will need to download the [Update for customer experience and diagnostic telemetry](https://support.microsoft.com/help/3080149/update-for-customer-experience-and-diagnostic-telemetry) in order to collect the data with MMA.</span></span> <span data-ttu-id="9fc9f-195">Diese Systemversionen umfassen u. U. folgende Versionen:</span><span class="sxs-lookup"><span data-stu-id="9fc9f-195">These system versions include but may not be limited to:</span></span>

    -   <span data-ttu-id="9fc9f-196">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="9fc9f-196">Windows 8.1</span></span>

    -   <span data-ttu-id="9fc9f-197">Windows 7</span><span class="sxs-lookup"><span data-stu-id="9fc9f-197">Windows 7</span></span>

    -   <span data-ttu-id="9fc9f-198">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="9fc9f-198">Windows Server 2016</span></span>

    -   <span data-ttu-id="9fc9f-199">Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="9fc9f-199">Windows Server 2012 R2</span></span>

    -   <span data-ttu-id="9fc9f-200">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="9fc9f-200">Windows Server 2008 R2</span></span>

    <span data-ttu-id="9fc9f-201">Insbesondere für Windows 7 SP1 müssen die folgenden Patches installiert werden:</span><span class="sxs-lookup"><span data-stu-id="9fc9f-201">Specifically, for Windows 7 SP1, the following patches must be installed:</span></span>

    -   <span data-ttu-id="9fc9f-202">Installieren [von KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span><span class="sxs-lookup"><span data-stu-id="9fc9f-202">Install [KB4074598](https://support.microsoft.com/help/4074598/windows-7-update-kb4074598)</span></span>

    -   <span data-ttu-id="9fc9f-203">Installieren Sie [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (oder höher) **oder** 
         [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span><span class="sxs-lookup"><span data-stu-id="9fc9f-203">Install either [.NET Framework 4.5](https://www.microsoft.com/download/details.aspx?id=30653) (or later) **or**
        [KB3154518](https://support.microsoft.com/help/3154518/support-for-tls-system-default-versions-included-in-the-net-framework).</span></span>
        <span data-ttu-id="9fc9f-204">Installieren Sie beide nicht auf demselben System.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-204">Do not install both on the same system.</span></span>

5. <span data-ttu-id="9fc9f-205">Wenn Sie einen Proxy zum Herstellen einer Verbindung mit dem Internet verwenden, lesen Sie den Abschnitt Konfigurieren von Proxyeinstellungen.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-205">If you're using a proxy to connect to the Internet see the Configure proxy settings section.</span></span>

<span data-ttu-id="9fc9f-206">Sobald sie abgeschlossen sind, sollten integrierte Endpunkte innerhalb einer Stunde im Portal angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-206">Once completed, you should see onboarded endpoints in the portal within an hour.</span></span>

### <a name="next-generation-protection"></a><span data-ttu-id="9fc9f-207">Schutz der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="9fc9f-207">Next generation protection</span></span> 
<span data-ttu-id="9fc9f-208">Microsoft Defender Antivirus ist eine integrierte Lösung zur Bekämpfung von Schadsoftware, die Schutz der nächsten Generation für Desktops, tragbare Computer und Server bietet.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-208">Microsoft Defender Antivirus is a built-in antimalware solution that provides next generation protection for desktops, portable computers, and servers.</span></span>

1. <span data-ttu-id="9fc9f-209">Navigieren Sie in der Microsoft Endpoint Configuration Manager-Konsole zu **Assets and Compliance Overview Endpoint Protection \> \> \> Anmalware Polices,** und wählen Sie **Antischalwarerichtlinie erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-209">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Antimalware Polices** and choose **Create Antimalware Policy**.</span></span>

    ![Abbildung der Antischabschmierenrichtlinie](images/9736e0358e86bc778ce1bd4c516adb8b.png)

2. <span data-ttu-id="9fc9f-211">Wählen **Sie Geplante Scans**, **Scaneinstellungen**, **Standardaktionen**, **Echtzeitschutz** **,** Ausschlusseinstellungen , **Erweitert**, **Bedrohungsüberschreibungen**, Cloud **Protection Service-** und **Security Intelligence-Updates aus,** und wählen Sie **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-211">Select **Scheduled scans**, **Scan settings**, **Default actions**, **Real-time protection**, **Exclusion settings**, **Advanced**, **Threat overrides**, **Cloud Protection Service** and **Security intelligence   updates** and choose **OK**.</span></span>

    ![Abbildung des Schutzbereichs der nächsten Generation1](images/1566ad81bae3d714cc9e0d47575a8cbd.png)

    <span data-ttu-id="9fc9f-213">In bestimmten Branchen oder einigen ausgewählten Unternehmenskunden können bestimmte Anforderungen an die Konfiguration von Antivirus erfüllt sein.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-213">In certain industries or some select enterprise customers might have specific needs on how Antivirus is configured.</span></span>

  
    [<span data-ttu-id="9fc9f-214">Schnellscan im Vergleich zu vollständiger Überprüfung und benutzerdefinierter Überprüfung</span><span class="sxs-lookup"><span data-stu-id="9fc9f-214">Quick scan versus full scan and custom scan</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/scheduled-catch-up-scans-microsoft-defender-antivirus#quick-scan-versus-full-scan-and-custom-scan)

    <span data-ttu-id="9fc9f-215">Weitere Informationen finden Sie unter [Windows Security Configuration Framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span><span class="sxs-lookup"><span data-stu-id="9fc9f-215">For more details, see [Windows Security configuration framework](https://docs.microsoft.com/windows/security/threat-protection/windows-security-configuration-framework/windows-security-configuration-framework)</span></span>
  
    ![Abbildung des Schutzbereichs der nächsten Generation2](images/cd7daeb392ad5a36f2d3a15d650f1e96.png)

    ![Abbildung des Schutzbereichs der nächsten Generation3](images/36c7c2ed737f2f4b54918a4f20791d4b.png)

    ![Abbildung des Schutzbereichs der nächsten Generation4](images/a28afc02c1940d5220b233640364970c.png)

    ![Abbildung des Schutzbereichs der nächsten Generation5](images/5420a8790c550f39f189830775a6d4c9.png)

    ![Abbildung des Schutzbereichs der nächsten Generation6](images/33f08a38f2f4dd12a364f8eac95e8c6b.png)

    ![Abbildung des Schutzbereichs der nächsten Generation7](images/41b9a023bc96364062c2041a8f5c344e.png)

    ![Abbildung des Schutzbereichs der nächsten Generation8](images/945c9c5d66797037c3caeaa5c19f135c.png)

    ![Abbildung des Schutzbereichs der nächsten Generation9](images/3876ca687391bfc0ce215d221c683970.png)

3. <span data-ttu-id="9fc9f-224">Klicken Sie mit der rechten Maustaste auf die neu erstellte Antischalwarerichtlinie, und wählen Sie **Bereitstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-224">Right-click on the newly created antimalware policy and select **Deploy**.</span></span>

    ![Abbildung des Schutzbereichs der nächsten Generation10](images/f5508317cd8c7870627cb4726acd5f3d.png)

4. <span data-ttu-id="9fc9f-226">Wählen Sie die neue Antischalwarerichtlinie auf Ihre Windows 10-Auflistung aus, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-226">Target the new antimalware policy to your Windows 10 collection and click **OK**.</span></span>

     ![Abbildung des Schutzbereichs der nächsten Generation11](images/configmgr-select-collection.png)

<span data-ttu-id="9fc9f-228">Nachdem Sie diese Aufgabe abgeschlossen haben, haben Sie die Antivirus-Windows Defender konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-228">After completing this task, you now have successfully configured Windows Defender Antivirus.</span></span>

### <a name="attack-surface-reduction"></a><span data-ttu-id="9fc9f-229">Angriffsfläche verringern</span><span class="sxs-lookup"><span data-stu-id="9fc9f-229">Attack surface reduction</span></span>
<span data-ttu-id="9fc9f-230">Die Angriffsflächenreduzierungssäule von Defender for Endpoint umfasst den Funktionssatz, der unter Exploit Guard verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-230">The attack surface reduction pillar of Defender for Endpoint includes the feature set that is available under Exploit Guard.</span></span> <span data-ttu-id="9fc9f-231">Attack Surface Reduction (ASR)-Regeln, kontrollierter Ordnerzugriff, Netzwerkschutz und Exploit-Schutz.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-231">Attack surface reduction (ASR) rules, Controlled Folder Access, Network Protection and Exploit Protection.</span></span> 

<span data-ttu-id="9fc9f-232">Alle diese Features bieten einen Überwachungsmodus und einen Blockmodus.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-232">All these features provide an audit mode and a block mode.</span></span> <span data-ttu-id="9fc9f-233">Im Überwachungsmodus gibt es keine Auswirkungen auf endbenutzer.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-233">In audit mode there is no end-user impact.</span></span> <span data-ttu-id="9fc9f-234">Sie sammelt nur zusätzliche Telemetrie und stellt sie im Microsoft Defender Security Center zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-234">All it does is collect additional telemetry and make it available in the Microsoft Defender Security Center.</span></span> <span data-ttu-id="9fc9f-235">Das Ziel einer Bereitstellung besteht in der schrittweisen Bewegung von Sicherheitssteuerelementen in den Blockmodus.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-235">The goal with a deployment is to step-by-step move security controls into block mode.</span></span>

<span data-ttu-id="9fc9f-236">So legen Sie ASR-Regeln im Überwachungsmodus ein:</span><span class="sxs-lookup"><span data-stu-id="9fc9f-236">To set ASR rules in Audit mode:</span></span>

1. <span data-ttu-id="9fc9f-237">Navigieren Sie in der Microsoft Endpoint Configuration Manager-Konsole zu **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard,** und wählen Sie **Exploit Guard-Richtlinie erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-237">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

   ![Abbildung der Microsoft Endpoint Configuration Manager-Konsole0](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2.  <span data-ttu-id="9fc9f-239">Wählen Sie **Attack Surface Reduction aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-239">Select **Attack Surface Reduction**.</span></span>
   

3. <span data-ttu-id="9fc9f-240">Legen Sie Regeln auf **Überwachung** und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-240">Set rules to **Audit** and click **Next**.</span></span>


    ![Abbildung der Microsoft Endpoint Configuration Manager-Konsole1](images/d18e40c9e60aecf1f9a93065cb7567bd.png)

4. <span data-ttu-id="9fc9f-242">Bestätigen Sie die neue Exploit Guard-Richtlinie, indem Sie auf **Weiter klicken.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-242">Confirm the new Exploit Guard policy by clicking on **Next**.</span></span>

    ![Abbildung der Microsoft Endpoint Configuration Manager-Konsole2](images/0a6536f2c4024c08709cac8fcf800060.png)

    
5. <span data-ttu-id="9fc9f-244">Klicken Sie nach dem Erstellen der Richtlinie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-244">Once the policy is created click **Close**.</span></span>

    ![Abbildung der Microsoft Endpoint Configuration Manager-Konsole3](images/95d23a07c2c8bc79176788f28cef7557.png)

    ![Abbildung der Microsoft Endpoint Manager-Konsole1](images/95d23a07c2c8bc79176788f28cef7557.png)
   

6.  <span data-ttu-id="9fc9f-247">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und wählen Sie **Bereitstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-247">Right-click on the newly created policy and choose **Deploy**.</span></span>
    
    ![Abbildung der Microsoft Endpoint Configuration Manager-Konsole4](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="9fc9f-249">Zielen Sie die Richtlinie auf die neu erstellte Windows 10-Auflistung ab, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-249">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Abbildung der Microsoft Endpoint Configuration Manager-Konsole5](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="9fc9f-251">Nachdem Sie diese Aufgabe abgeschlossen haben, haben Sie jetzt erfolgreich DIE REGELN im Überwachungsmodus konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-251">After completing this task, you now have successfully configured ASR rules in audit mode.</span></span>  
  
<span data-ttu-id="9fc9f-252">Im Folgenden finden Sie weitere Schritte, um zu überprüfen, ob DIE REGELN ordnungsgemäß auf Endpunkte angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-252">Below are additional steps to verify whether ASR rules are correctly applied to endpoints.</span></span> <span data-ttu-id="9fc9f-253">(Dies kann einige Minuten dauern)</span><span class="sxs-lookup"><span data-stu-id="9fc9f-253">(This may take few minutes)</span></span>


1. <span data-ttu-id="9fc9f-254">Navigieren Sie in einem Webbrowser zu <https://securitycenter.windows.com> .</span><span class="sxs-lookup"><span data-stu-id="9fc9f-254">From a web browser, navigate to <https://securitycenter.windows.com>.</span></span>

2.  <span data-ttu-id="9fc9f-255">Wählen **Sie im linken** Menü Konfigurationsverwaltung aus.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-255">Select **Configuration management** from left side menu.</span></span>

3. <span data-ttu-id="9fc9f-256">Klicken **Sie im Bereich Angriffsoberflächenverwaltung** auf Gehe, um die Oberflächenverwaltung zu attackieren.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-256">Click **Go to attack surface management** in the Attack surface management panel.</span></span> 
    
    ![Abbildung der Angriffsoberflächenverwaltung](images/security-center-attack-surface-mgnt-tile.png)

4. <span data-ttu-id="9fc9f-258">Klicken **Sie auf der** Registerkarte Konfiguration in Berichten zu Attack surface reduction rules.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-258">Click **Configuration** tab in Attack surface reduction rules reports.</span></span> <span data-ttu-id="9fc9f-259">Es zeigt eine Übersicht über die Konfiguration von ASR-Regeln und den Status von ASR-Regeln auf jedem Gerät.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-259">It shows ASR rules configuration overview and ASR rules status on each devices.</span></span>

    ![Screenshot von Berichten zu Angriffsflächenreduzierungsregeln1](images/f91f406e6e0aae197a947d3b0e8b2d0d.png)

5. <span data-ttu-id="9fc9f-261">Klicken Sie auf jedes Gerät, um Konfigurationsdetails der ASR-Regeln anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-261">Click each device shows configuration details of ASR rules.</span></span>

    ![Ein Screenshot der Berichte über Angriffsflächenreduzierungsregeln2](images/24bfb16ed561cbb468bd8ce51130ca9d.png)

<span data-ttu-id="9fc9f-263">Weitere Informationen finden Sie unter [Optimize ASR rule deployment and detections.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)</span><span class="sxs-lookup"><span data-stu-id="9fc9f-263">See [Optimize ASR rule deployment and detections](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-asr)   for more details.</span></span>  


#### <a name="set-network-protection-rules-in-audit-mode"></a><span data-ttu-id="9fc9f-264">Festlegen von Netzwerkschutzregeln im Überwachungsmodus:</span><span class="sxs-lookup"><span data-stu-id="9fc9f-264">Set Network Protection rules in Audit mode:</span></span>
1. <span data-ttu-id="9fc9f-265">Navigieren Sie in der Microsoft Endpoint Configuration Manager-Konsole zu **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard,** und wählen Sie **Exploit Guard-Richtlinie erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-265">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and  Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![A screenshot System Center Configuration Manager1](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="9fc9f-267">Wählen Sie **Netzwerkschutz aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-267">Select **Network protection**.</span></span>

3. <span data-ttu-id="9fc9f-268">Legen Sie die Einstellung auf **Überwachung** und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-268">Set the setting to **Audit** and click **Next**.</span></span> 

    ![A screenshot System Center Confirugatiom Manager2](images/c039b2e05dba1ade6fb4512456380c9f.png)

4. <span data-ttu-id="9fc9f-270">Bestätigen Sie die neue Exploit Guard-Richtlinie, indem Sie auf **Weiter klicken.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-270">Confirm the new Exploit Guard Policy by clicking **Next**.</span></span>
    
    ![Screenshot Exploit GUard policy1](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="9fc9f-272">Klicken Sie nach dem Erstellen der Richtlinie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-272">Once the policy is created click on **Close**.</span></span>

    ![Screenshot Exploit-GUard-Richtlinie2](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="9fc9f-274">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und wählen Sie **Bereitstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-274">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![A screenshot Microsoft Endpoint Configuration Manager1](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7. <span data-ttu-id="9fc9f-276">Wählen Sie die Richtlinie für die neu erstellte Windows 10-Auflistung aus, und wählen Sie **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-276">Select the policy to the newly created Windows 10 collection and choose **OK**.</span></span>

    ![Screenshot Von Microsoft Endpoint Configuration Manager2](images/0ccfe3e803be4b56c668b220b51da7f7.png)



<span data-ttu-id="9fc9f-278">Nachdem Sie diese Aufgabe abgeschlossen haben, haben Sie Network Protection im Überwachungsmodus erfolgreich konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-278">After completing this task, you now have successfully configured Network Protection in audit mode.</span></span>

#### <a name="to-set-controlled-folder-access-rules-in-audit-mode"></a><span data-ttu-id="9fc9f-279">So legen Sie Regeln für den kontrollierten Ordnerzugriff im Überwachungsmodus ein:</span><span class="sxs-lookup"><span data-stu-id="9fc9f-279">To set Controlled Folder Access rules in Audit mode:</span></span>

1. <span data-ttu-id="9fc9f-280">Navigieren Sie in der Microsoft Endpoint Configuration Manager-Konsole zu **Assets and Compliance Overview Endpoint Protection Windows Defender Exploit \> \> \> Guard,** und wählen Sie **Exploit Guard-Richtlinie erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-280">In the Microsoft Endpoint Configuration Manager console, navigate to **Assets and Compliance \> Overview \> Endpoint Protection \> Windows Defender Exploit Guard** and choose **Create Exploit Guard Policy**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager3](images/728c10ef26042bbdbcd270b6343f1a8a.png)

2. <span data-ttu-id="9fc9f-282">Wählen **Sie Kontrollierter Ordnerzugriff aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-282">Select **Controlled folder access**.</span></span>
    
3. <span data-ttu-id="9fc9f-283">Legen Sie die Konfiguration auf **Überwachung und** klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-283">Set the configuration to **Audit** and click **Next**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager4](images/a8b934dab2dbba289cf64fe30e0e8aa4.png)    
    
4. <span data-ttu-id="9fc9f-285">Bestätigen Sie die neue Exploit Guard-Richtlinie, indem Sie auf **Weiter klicken.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-285">Confirm the new Exploit Guard Policy by clicking on **Next**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager5](images/0a6536f2c4024c08709cac8fcf800060.png)

5. <span data-ttu-id="9fc9f-287">Klicken Sie nach dem Erstellen der Richtlinie auf **Schließen**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-287">Once the policy is created click on **Close**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager6](images/95d23a07c2c8bc79176788f28cef7557.png)

6. <span data-ttu-id="9fc9f-289">Klicken Sie mit der rechten Maustaste auf die neu erstellte Richtlinie, und wählen Sie **Bereitstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="9fc9f-289">Right-click on the newly created policy and choose **Deploy**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager7](images/8999dd697e3b495c04eb911f8b68a1ef.png)

7.  <span data-ttu-id="9fc9f-291">Zielen Sie die Richtlinie auf die neu erstellte Windows 10-Auflistung ab, und klicken Sie auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-291">Target the policy to the newly created Windows 10 collection and click **OK**.</span></span>

    ![Screenshot von Microsoft Endpoint Configuration Manager8](images/0ccfe3e803be4b56c668b220b51da7f7.png)

<span data-ttu-id="9fc9f-293">Sie haben nun den kontrollierten Ordnerzugriff im Überwachungsmodus erfolgreich konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="9fc9f-293">You have now successfully configured Controlled folder access in audit mode.</span></span>

## <a name="related-topic"></a><span data-ttu-id="9fc9f-294">Verwandtes Thema</span><span class="sxs-lookup"><span data-stu-id="9fc9f-294">Related topic</span></span>
- [<span data-ttu-id="9fc9f-295">Onboarding mit Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="9fc9f-295">Onboarding using Microsoft Endpoint Manager</span></span>](onboarding-endpoint-manager.md)
