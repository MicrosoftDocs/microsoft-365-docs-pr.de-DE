---
title: Microsoft Defender for Endpoint-Evaluierungslabor
description: Erfahren Sie mehr über Microsoft Defender for Endpoint-Funktionen, führen Sie Angriffssimulationen aus, und erfahren Sie, wie Bedrohungen verhindert, erkannt und behoben werden.
keywords: evaluieren von mdatp, evaluation, lab, simulation, windows 10, windows server 2019, evaluation lab
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
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ead616b7af3df05f4c0c5755ad779f0251555734
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51066544"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="6d2ab-104">Microsoft Defender for Endpoint-Evaluierungslabor</span><span class="sxs-lookup"><span data-stu-id="6d2ab-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="6d2ab-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-105">**Applies to:**</span></span>
- [<span data-ttu-id="6d2ab-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="6d2ab-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="6d2ab-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6d2ab-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="6d2ab-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="6d2ab-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6d2ab-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="6d2ab-110">Die Durchführung einer umfassenden Sicherheitsproduktbewertung kann ein komplexer Prozess sein, der eine aufwändige Umgebung und Gerätekonfiguration erfordert, bevor eine End-to-End-Angriffssimulation tatsächlich durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="6d2ab-111">Das Hinzufügen der Komplexität ist die Herausforderung, zu verfolgen, wo die Simulationsaktivitäten, Warnungen und Ergebnisse während der Auswertung widergespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="6d2ab-112">Das Microsoft Defender for Endpoint-Evaluierungslabor ist so konzipiert, dass die Komplexität der Geräte- und Umgebungskonfiguration eliminiert wird, sodass Sie sich auf die Auswertung der Funktionen der Plattform, das Ausführen von Simulationen und das Sehen der Funktionen zur Verhinderung, Erkennung und Behebung konzentrieren können.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="6d2ab-113">Mit der vereinfachten Einrichtungsumgebung können Sie sich auf die Ausführung eigener Testszenarien und der vordefinierten Simulationen konzentrieren, um die Leistung von Defender for Endpoint zu sehen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="6d2ab-114">Sie haben vollsten Zugriff auf die leistungsstarken Funktionen der Plattform, z. B. automatisierte Untersuchungen, erweiterte Suche und Bedrohungsanalyse, sodass Sie den umfassenden Schutzstapel testen können, den Defender for Endpoint bietet.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="6d2ab-115">Sie können Windows 10- oder Windows Server 2019-Geräte hinzufügen, die vorkonfiguriert sind, um die neuesten Betriebssystemversionen und die richtigen Sicherheitskomponenten sowie Office 2019 Standard installiert zu haben.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="6d2ab-116">Sie können auch Bedrohungssimulatoren installieren.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-116">You can also install threat simulators.</span></span> <span data-ttu-id="6d2ab-117">Defender for Endpoint hat sich mit branchenführenden Bedrohungssimulationsplattformen zusammen gefunden, um die Defender for Endpoint-Funktionen zu testen, ohne das Portal verlassen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="6d2ab-118">Installieren Sie Ihren bevorzugten Simulator, führen Sie Szenarien innerhalb des Evaluierungslabors aus, und sehen Sie sich sofort an, wie die Plattform funktioniert – alles bequem und ohne zusätzliche Kosten für Sie verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="6d2ab-119">Außerdem haben Sie bequemen Zugriff auf eine breite Palette von Simulationen, auf die Sie im Simulationskatalog zugreifen und diese ausführen können.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="6d2ab-120">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="6d2ab-120">Before you begin</span></span>
<span data-ttu-id="6d2ab-121">Sie müssen die Lizenzierungsanforderungen [erfüllen](minimum-requirements.md#licensing-requirements) oder Testzugriff auf Microsoft Defender for Endpoint haben, um auf das Evaluierungslabor zu zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="6d2ab-122">Sie müssen über **Berechtigungen zum Verwalten von Sicherheitseinstellungen verfügen** für:</span><span class="sxs-lookup"><span data-stu-id="6d2ab-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="6d2ab-123">Erstellen der Übungseinheit</span><span class="sxs-lookup"><span data-stu-id="6d2ab-123">Create the lab</span></span>
- <span data-ttu-id="6d2ab-124">Erstellen von Geräten</span><span class="sxs-lookup"><span data-stu-id="6d2ab-124">Create devices</span></span>
- <span data-ttu-id="6d2ab-125">Kennwort zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="6d2ab-125">Reset password</span></span>
- <span data-ttu-id="6d2ab-126">Erstellen von Simulationen</span><span class="sxs-lookup"><span data-stu-id="6d2ab-126">Create simulations</span></span> 
 
<span data-ttu-id="6d2ab-127">Wenn Sie die rollenbasierte Zugriffssteuerung aktiviert und mindestens eine Computergruppe erstellt haben, müssen Benutzer Zugriff auf Alle Computergruppen haben.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="6d2ab-128">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen](user-roles.md).</span><span class="sxs-lookup"><span data-stu-id="6d2ab-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="6d2ab-129">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="6d2ab-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="6d2ab-130">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="6d2ab-131">Erste Schritte mit der Übungseinheit</span><span class="sxs-lookup"><span data-stu-id="6d2ab-131">Get started with the lab</span></span>
<span data-ttu-id="6d2ab-132">Sie können über das Menü auf die Übungseinheit zugreifen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-132">You can access the lab from the menu.</span></span> <span data-ttu-id="6d2ab-133">Wählen Sie im Navigationsmenü Die Option Evaluierung und Lernprogramme > **Evaluierungsumgebung aus.**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![Abbildung des Evaluierungslabors im Menü](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="6d2ab-135">Jede Umgebung wird mit einer begrenzten Anzahl von Testgeräten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-135">Each environment is provisioned with a limited set of test devices.</span></span>
>- <span data-ttu-id="6d2ab-136">Je nachdem, welche Umgebungsstruktur Sie auswählen, stehen Geräte für die angegebene Anzahl von Stunden ab dem Aktivierungstag zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-136">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="6d2ab-137">Wenn Sie die bereitgestellten Geräte verwendet haben, werden keine neuen Geräte bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-137">When you've used up the provisioned devices, no new devices are provided.</span></span> <span data-ttu-id="6d2ab-138">Ein gelöschtes Gerät aktualisiert die anzahl der verfügbaren Testgeräte nicht.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-138">A deleted device does not refresh the available test device count.</span></span>
>- <span data-ttu-id="6d2ab-139">Angesichts der begrenzten Ressourcen empfiehlt es sich, die Geräte sorgfältig zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-139">Given the limited resources, it’s advisable to use the devices carefully.</span></span>

<span data-ttu-id="6d2ab-140">Sie haben bereits ein Labor?</span><span class="sxs-lookup"><span data-stu-id="6d2ab-140">Already have a lab?</span></span> <span data-ttu-id="6d2ab-141">Stellen Sie sicher, dass sie die neuen Bedrohungssimulatoren aktivieren und über aktive Geräte verfügen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-141">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="6d2ab-142">Einrichten der Evaluierungsumgebung</span><span class="sxs-lookup"><span data-stu-id="6d2ab-142">Setup the evaluation lab</span></span>

1. <span data-ttu-id="6d2ab-143">Wählen Sie im Navigationsbereich **Evaluierungs- und Lernprogramme**  >  **Evaluierungslabor** aus, und wählen Sie **dann Setup lab aus.**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-143">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![Bild der Willkommensseite des Evaluierungslabors](images/evaluation-lab-setup.png)

2. <span data-ttu-id="6d2ab-145">Je nach Bewertungsanforderungen können Sie eine Umgebung mit weniger Geräten für einen längeren Zeitraum oder mehr Geräte für einen kürzeren Zeitraum einrichten.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-145">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="6d2ab-146">Wählen Sie Ihre bevorzugte Lab-Konfiguration aus, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-146">Select your preferred lab configuration then select **Next**.</span></span>

    ![Abbildung der Lab-Konfigurationsoptionen](images/lab-creation-page.png) 


3. <span data-ttu-id="6d2ab-148">(Optional) Sie können in der Übungsumgebung Bedrohungssimulatoren installieren.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-148">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![Abbildung des Installationssimulator-Agents](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="6d2ab-150">Sie müssen zunächst die Bedingungen und Anweisungen zur Freigabe von Informationen akzeptieren und zustimmen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-150">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="6d2ab-151">Wählen Sie den Agent für die Bedrohungssimulation aus, den Sie verwenden möchten, und geben Sie Ihre Details ein.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-151">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="6d2ab-152">Sie können auch zu einem späteren Zeitpunkt Bedrohungssimulatoren installieren.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-152">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="6d2ab-153">Wenn Sie während des Lab-Setups Bedrohungssimulations-Agents installieren möchten, profitieren Sie davon, dass sie bequem auf den hinzugefügten Geräten installiert werden.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-153">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![Abbildung der Zusammenfassungsseite](images/lab-setup-summary.png)

5.  <span data-ttu-id="6d2ab-155">Überprüfen Sie die Zusammenfassung, und wählen **Sie Setup lab aus.**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-155">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="6d2ab-156">Nach Abschluss des Lab-Setupprozesses können Sie Geräte hinzufügen und Simulationen ausführen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-156">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="6d2ab-157">Hinzufügen von Geräten</span><span class="sxs-lookup"><span data-stu-id="6d2ab-157">Add devices</span></span>
<span data-ttu-id="6d2ab-158">Wenn Sie Ihrer Umgebung ein Gerät hinzufügen, richtet Defender for Endpoint ein gut konfiguriertes Gerät mit Verbindungsdetails ein.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-158">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="6d2ab-159">Sie können Windows 10- oder Windows Server 2019-Geräte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-159">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="6d2ab-160">Das Gerät wird mit der neuesten Version des Betriebssystems und office 2019 Standard sowie mit anderen Apps wie Java, Python und SysIntenals konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-160">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

   >[!TIP]
   > <span data-ttu-id="6d2ab-161">Benötigen Sie weitere Geräte in Ihrem Labor?</span><span class="sxs-lookup"><span data-stu-id="6d2ab-161">Need more devices in your lab?</span></span> <span data-ttu-id="6d2ab-162">Senden Sie ein Supportticket, damit Ihre Anforderung vom Defender for Endpoint-Team überprüft wird.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-162">Submit a support ticket to have your request reviewed by the Defender for Endpoint team.</span></span> 

<span data-ttu-id="6d2ab-163">Wenn Sie während der Übungseinrichtung einen Bedrohungssimulator hinzufügen möchten, wird auf allen Geräten der Threat Simulator Agent auf den geräten installiert, die Sie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-163">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="6d2ab-164">Das Gerät wird automatisch in Ihren Mandanten onboardiert, und die empfohlenen Windows-Sicherheitskomponenten sind aktiviert und im Überwachungsmodus – ohne Aufwand auf Ihrer Seite.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-164">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="6d2ab-165">Die folgenden Sicherheitskomponenten sind auf den Testgeräten vorkonfiguriert:</span><span class="sxs-lookup"><span data-stu-id="6d2ab-165">The following security components are pre-configured in the test devices:</span></span>

- [<span data-ttu-id="6d2ab-166">Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="6d2ab-166">Attack surface reduction</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)
- [<span data-ttu-id="6d2ab-167">Bei erster Sicht blockieren</span><span class="sxs-lookup"><span data-stu-id="6d2ab-167">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="6d2ab-168">Kontrollierter Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="6d2ab-168">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="6d2ab-169">Exploit-Schutz</span><span class="sxs-lookup"><span data-stu-id="6d2ab-169">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="6d2ab-170">Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="6d2ab-170">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="6d2ab-171">Erkennung potenziell unerwünschter Anwendungen</span><span class="sxs-lookup"><span data-stu-id="6d2ab-171">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="6d2ab-172">In der Cloud zugestellter Schutz</span><span class="sxs-lookup"><span data-stu-id="6d2ab-172">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="6d2ab-173">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="6d2ab-173">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="6d2ab-174">Microsoft Defender Antivirus ist aktiviert (nicht im Überwachungsmodus).</span><span class="sxs-lookup"><span data-stu-id="6d2ab-174">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="6d2ab-175">Wenn Sie von Microsoft Defender Antivirus nicht mehr ausgeführt werden können, können Sie den Echtzeitschutz auf dem Gerät über Windows Security deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-175">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="6d2ab-176">Weitere Informationen finden Sie unter [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="6d2ab-176">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="6d2ab-177">Automatische Untersuchungseinstellungen hängen von den Mandanteneinstellungen ab.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-177">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="6d2ab-178">Sie wird standardmäßig als halbautomatisiert konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-178">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="6d2ab-179">Weitere Informationen finden Sie unter [Overview of Automated investigations](automated-investigations.md).</span><span class="sxs-lookup"><span data-stu-id="6d2ab-179">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="6d2ab-180">Die Verbindung mit den Testgeräten erfolgt mithilfe von RDP.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-180">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="6d2ab-181">Stellen Sie sicher, dass ihre Firewalleinstellungen RDP-Verbindungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-181">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="6d2ab-182">Wählen Sie im Dashboard Geräte **hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-182">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="6d2ab-183">Wählen Sie den Typ des hinzuzufügende Geräts aus.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-183">Choose the type of device to add.</span></span> <span data-ttu-id="6d2ab-184">Sie können Windows 10 oder Windows Server 2019 hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-184">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![Abbildung des Lab-Setups mit Geräteoptionen](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="6d2ab-186">Wenn beim Erstellungsprozess des Geräts ein Fehler vorgeht, werden Sie benachrichtigt, und Sie müssen eine neue Anforderung übermitteln.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-186">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="6d2ab-187">Wenn die Geräteerstellung fehlschlägt, wird sie nicht mit dem insgesamt zulässigen Kontingent gezählt.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-187">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="6d2ab-188">Die Verbindungsdetails werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-188">The connection details are displayed.</span></span> <span data-ttu-id="6d2ab-189">Wählen **Sie Kopieren** aus, um das Kennwort für das Gerät zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-189">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="6d2ab-190">Das Kennwort wird nur einmal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-190">The password is only displayed once.</span></span> <span data-ttu-id="6d2ab-191">Achten Sie darauf, sie für eine spätere Verwendung zu speichern.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-191">Be sure to save it for later use.</span></span>

    ![Abbildung des Geräts, das mit Verbindungsdetails hinzugefügt wurde](images/add-machine-eval-lab.png)

4. <span data-ttu-id="6d2ab-193">Die Geräteeinrichtung beginnt.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-193">Device set up begins.</span></span> <span data-ttu-id="6d2ab-194">Dies kann bis zu ca. 30 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-194">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="6d2ab-195">Sehen Sie sich den Status von Testgeräten, die Risiko- und Belichtungsstufen sowie den Status von Simulatorinstallationen an, indem Sie die Registerkarte **Geräte** auswählen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-195">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![Abbildung der Registerkarte "Geräte"](images/machines-tab.png)
    

    >[!TIP]
    ><span data-ttu-id="6d2ab-197">In der **Spalte Simulatorstatus** können Sie mit der Maus auf das Informationssymbol zeigen, um den Installationsstatus eines Agents zu erfahren.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-197">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>



## <a name="simulate-attack-scenarios"></a><span data-ttu-id="6d2ab-198">Simulieren von Angriffsszenarien</span><span class="sxs-lookup"><span data-stu-id="6d2ab-198">Simulate attack scenarios</span></span>
<span data-ttu-id="6d2ab-199">Verwenden Sie die Testgeräte, um eigene Angriffssimulationen durchzuführen, indem Sie eine Verbindung mit ihnen herstellen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-199">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="6d2ab-200">Sie können Angriffsszenarien mit folgenden Bedingungen simulieren:</span><span class="sxs-lookup"><span data-stu-id="6d2ab-200">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="6d2ab-201">Die [Angriffsszenarien "Do It Yourself"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="6d2ab-201">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="6d2ab-202">Bedrohungssimulatoren</span><span class="sxs-lookup"><span data-stu-id="6d2ab-202">Threat simulators</span></span>

<span data-ttu-id="6d2ab-203">Sie können die [erweiterte](advanced-hunting-query-language.md) Suche auch verwenden, um Daten und [Bedrohungsanalysen](threat-analytics.md) zu abfragen, um Berichte zu neuen Bedrohungen anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-203">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="6d2ab-204">Do-it-yourself-Angriffsszenarien</span><span class="sxs-lookup"><span data-stu-id="6d2ab-204">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="6d2ab-205">Wenn Sie nach einer vordefinierten Simulation suchen, können Sie unsere [Angriffsszenarien "Do It Yourself" verwenden.](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="6d2ab-205">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="6d2ab-206">Diese Skripts sind sicher, dokumentiert und einfach zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-206">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="6d2ab-207">Diese Szenarien spiegeln die Defender for Endpoint-Funktionen wider und zeigen Ihnen die Untersuchungserfahrung.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-207">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="6d2ab-208">Die Verbindung mit den Testgeräten erfolgt mithilfe von RDP.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-208">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="6d2ab-209">Stellen Sie sicher, dass ihre Firewalleinstellungen RDP-Verbindungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-209">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="6d2ab-210">Stellen Sie eine Verbindung mit Ihrem Gerät ein, und führen Sie eine Angriffssimulation aus, indem Sie **Verbinden auswählen.**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-210">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![Abbildung der Verbindungsschaltfläche für Testgeräte](images/test-machine-table.png)

2. <span data-ttu-id="6d2ab-212">Speichern Sie die RDP-Datei, und starten Sie sie, indem Sie **Verbinden auswählen.**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-212">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Abbildung der Remotedesktopverbindung](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="6d2ab-214">Wenn Sie während der Ersteinrichtung keine Kopie des Kennworts gespeichert haben,  können Sie das Kennwort zurücksetzen, indem Sie im Menü Kennwort zurücksetzen auswählen: Abbildung ![ des Kennworts zurücksetzen](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="6d2ab-214">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="6d2ab-215">Das Gerät ändert den Status in "Kennwortzurücksetzung ausführen", dann wird Ihnen das neue Kennwort in ein paar Minuten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-215">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="6d2ab-216">Geben Sie das Kennwort ein, das während des Geräteerstellungsschritts angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-216">Enter the password that was displayed during the device creation step.</span></span> 

   ![Abbildung des Fensters zum Eingeben von Anmeldeinformationen](images/enter-password.png)

4. <span data-ttu-id="6d2ab-218">Führen Sie Do-it-yourself-Angriffssimulationen auf dem Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-218">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="6d2ab-219">Szenarien des Bedrohungssimulators</span><span class="sxs-lookup"><span data-stu-id="6d2ab-219">Threat simulator scenarios</span></span>
<span data-ttu-id="6d2ab-220">Wenn Sie einen der unterstützten Bedrohungssimulatoren während des Lab-Setups installieren möchten, können Sie die integrierten Simulationen auf den Testumgebungsgeräten ausführen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-220">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="6d2ab-221">Das Ausführen von Bedrohungssimulationen mithilfe von Drittanbieterplattformen ist eine gute Möglichkeit, die Microsoft Defender for Endpoint-Funktionen innerhalb der Grenzen einer Laborumgebung auszuwerten.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-221">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="6d2ab-222">Bevor Sie Simulationen ausführen können, stellen Sie sicher, dass die folgenden Anforderungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="6d2ab-222">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="6d2ab-223">Geräte müssen der Evaluierungsumgebung hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="6d2ab-223">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="6d2ab-224">Bedrohungssimulatoren müssen im Evaluierungslabor installiert werden</span><span class="sxs-lookup"><span data-stu-id="6d2ab-224">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="6d2ab-225">Wählen Sie im Portal Simulation **erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-225">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="6d2ab-226">Wählen Sie einen Bedrohungssimulator aus.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-226">Select a threat simulator.</span></span>

    ![Abbildung der Auswahl des Bedrohungssimulators](images/select-simulator.png)

3. <span data-ttu-id="6d2ab-228">Wählen Sie eine Simulation aus, oder schauen Sie sich den Simulationskatalog an, um die verfügbaren Simulationen zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-228">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="6d2ab-229">Sie können zum Simulationskatalog von:</span><span class="sxs-lookup"><span data-stu-id="6d2ab-229">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="6d2ab-230">Das Hauptauswertungsdashboard in der **Übersichtskachel Simulationen** oder</span><span class="sxs-lookup"><span data-stu-id="6d2ab-230">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="6d2ab-231">Wenn Sie im Navigationsbereich Evaluierung und Lernprogramme & navigieren, wählen Sie  >   **Simulationskatalog aus.**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-231">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="6d2ab-232">Wählen Sie die Geräte aus, auf denen Sie die Simulation ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-232">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="6d2ab-233">Wählen **Sie Simulation erstellen aus.**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-233">Select **Create simulation**.</span></span>

6. <span data-ttu-id="6d2ab-234">Zeigen Sie den Fortschritt einer Simulation an, indem Sie die **Registerkarte Simulationen** auswählen. Anzeigen des Simulationszustands, aktiver Warnungen und anderer Details.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-234">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![Abbildung der Registerkarte Simulationen](images/simulations-tab.png)
    
<span data-ttu-id="6d2ab-236">Nachdem Sie Ihre Simulationen ausgeführt haben, empfehlen wir Ihnen, die Fortschrittsleiste des Labors zu durchforsten und Microsoft Defender for Endpoint zu erkunden, das eine automatisierte Untersuchung und Korrektur **ausgelöst hat.**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-236">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="6d2ab-237">Sehen Sie sich die vom Feature gesammelten und analysierten Nachweise an.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-237">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="6d2ab-238">Suchen Sie mithilfe der reichhaltigen Abfragesprache und der unformatierten Telemetrie nach Angriffsbeweis durch erweiterte Suche, und sehen Sie sich einige der weltweiten Bedrohungen an, die in der Bedrohungsanalyse dokumentiert sind.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-238">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="6d2ab-239">Simulationskatalog</span><span class="sxs-lookup"><span data-stu-id="6d2ab-239">Simulation gallery</span></span>
<span data-ttu-id="6d2ab-240">Microsoft Defender for Endpoint hat eine Partnerschaft mit verschiedenen Bedrohungssimulationsplattformen entwickelt, um Ihnen bequemen Zugriff auf die Funktionen der Plattform direkt im Portal zu bieten.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-240">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="6d2ab-241">Zeigen Sie alle verfügbaren Simulationen an, indem Sie im Menü zum **Simulations- und**  >  **Lernprogrammkatalog Simulationen** gehen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-241">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="6d2ab-242">Eine Liste der unterstützten Agents für die Bedrohungssimulation von Drittanbietern wird aufgelistet, und bestimmte Arten von Simulationen sowie ausführliche Beschreibungen werden im Katalog bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-242">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="6d2ab-243">Sie können alle verfügbaren Simulationen bequem direkt aus dem Katalog ausführen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-243">You can conveniently run any available simulation right from the catalog.</span></span>  


![Abbildung des Simulationskatalogs](images/simulations-catalog.png)

<span data-ttu-id="6d2ab-245">Jede Simulation enthält eine ausführliche Beschreibung des Angriffsszenarios und Verweise wie die verwendeten MITRE-Angriffstechniken und Beispielabfragen für erweiterte Suche.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-245">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="6d2ab-246">**Beispiele:** 
 ![ Abbildung der Simulationsbeschreibungsdetails1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="6d2ab-246">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![Abbildung der Simulationsbeschreibungsdetails2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="6d2ab-248">Evaluierungsbericht</span><span class="sxs-lookup"><span data-stu-id="6d2ab-248">Evaluation report</span></span>
<span data-ttu-id="6d2ab-249">In den Laborberichten werden die Ergebnisse der Simulationen zusammengefasst, die auf den Geräten durchgeführt wurden.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-249">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![Abbildung des Evaluierungsberichts](images/eval-report.png)

<span data-ttu-id="6d2ab-251">Auf einen Blick können Sie schnell sehen:</span><span class="sxs-lookup"><span data-stu-id="6d2ab-251">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="6d2ab-252">Ausgelöste Vorfälle</span><span class="sxs-lookup"><span data-stu-id="6d2ab-252">Incidents that were triggered</span></span>
- <span data-ttu-id="6d2ab-253">Generierte Warnungen</span><span class="sxs-lookup"><span data-stu-id="6d2ab-253">Generated alerts</span></span>
- <span data-ttu-id="6d2ab-254">Bewertungen der Risikostufe</span><span class="sxs-lookup"><span data-stu-id="6d2ab-254">Assessments on exposure level</span></span> 
- <span data-ttu-id="6d2ab-255">Beobachtete Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="6d2ab-255">Threat categories observed</span></span>
- <span data-ttu-id="6d2ab-256">Erkennungsquellen</span><span class="sxs-lookup"><span data-stu-id="6d2ab-256">Detection sources</span></span>
- <span data-ttu-id="6d2ab-257">Automatisierte Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="6d2ab-257">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="6d2ab-258">Feedback geben</span><span class="sxs-lookup"><span data-stu-id="6d2ab-258">Provide feedback</span></span>
<span data-ttu-id="6d2ab-259">Ihr Feedback hilft uns, Ihre Umgebung besser vor erweiterten Angriffen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-259">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="6d2ab-260">Teilen Sie Ihre Erfahrungen und Impressionen von Produktfunktionen und Auswertungsergebnissen.</span><span class="sxs-lookup"><span data-stu-id="6d2ab-260">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="6d2ab-261">Teilen Sie uns ihre Meinung mit, indem Sie **Feedback bereitstellen auswählen.**</span><span class="sxs-lookup"><span data-stu-id="6d2ab-261">Let us know what you think, by selecting **Provide feedback**.</span></span>

![Abbildung des Feedbacks](images/send-us-feedback-eval-lab.png)
