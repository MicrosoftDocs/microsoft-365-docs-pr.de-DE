---
title: Evaluierungslabor für Microsoft Defender für Endpunkt
description: Erfahren Sie mehr über die Funktionen von Microsoft Defender für Endpunkt, führen Sie Angriffssimulationen aus und erfahren Sie, wie Bedrohungen verhindert, erkannt und behoben werden.
keywords: Auswerten von Microsoft Defender für Endpunkt, Auswertung, Labor, Simulation, Windows 10, Windows Server 2019, Evaluierungslabor
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
ms.openlocfilehash: c785dbb759afe77b14f41985b9f451a4ec52e29f
ms.sourcegitcommit: 83df0be7144c9c5d606f70b4efa65369e86693d2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52778233"
---
# <a name="microsoft-defender-for-endpoint-evaluation-lab"></a><span data-ttu-id="f5382-104">Evaluierungslabor für Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f5382-104">Microsoft Defender for Endpoint evaluation lab</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f5382-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f5382-105">**Applies to:**</span></span>
- [<span data-ttu-id="f5382-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f5382-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f5382-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f5382-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="f5382-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="f5382-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f5382-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f5382-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)


<span data-ttu-id="f5382-110">Die Durchführung einer umfassenden Sicherheitsproduktbewertung kann ein komplexer Prozess sein, der eine umständliche Umgebung und Gerätekonfiguration erfordert, bevor tatsächlich eine End-to-End-Angriffssimulation durchgeführt werden kann.</span><span class="sxs-lookup"><span data-stu-id="f5382-110">Conducting a comprehensive security product evaluation can be a complex process requiring cumbersome environment and device configuration before an end-to-end attack simulation can actually be done.</span></span> <span data-ttu-id="f5382-111">Zusätzlich zur Komplexität besteht die Herausforderung, nachzuverfolgen, wo die Simulationsaktivitäten, Warnungen und Ergebnisse während der Auswertung widergespiegelt werden.</span><span class="sxs-lookup"><span data-stu-id="f5382-111">Adding to the complexity is the challenge of tracking where the simulation activities, alerts, and results are reflected during the evaluation.</span></span>

<span data-ttu-id="f5382-112">Das Evaluierungslabor von Microsoft Defender für Endpunkt wurde entwickelt, um die Komplexität der Geräte- und Umgebungskonfiguration zu beseitigen, sodass Sie sich auf die Bewertung der Funktionen der Plattform, das Ausführen von Simulationen und das Anzeigen der Funktionen zur Verhinderung, Erkennung und Wartung konzentrieren können.</span><span class="sxs-lookup"><span data-stu-id="f5382-112">The Microsoft Defender for Endpoint evaluation lab is designed to eliminate the complexities of device and environment configuration so that you can  focus on evaluating the capabilities of the platform, running simulations, and seeing the prevention, detection, and remediation features in action.</span></span>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4qLUM]

<span data-ttu-id="f5382-113">Mit der vereinfachten Einrichtungsoberfläche können Sie sich auf die Ausführung Ihrer eigenen Testszenarien und die vordefinierten Simulationen konzentrieren, um zu sehen, wie Defender für Endpunkt funktioniert.</span><span class="sxs-lookup"><span data-stu-id="f5382-113">With the simplified set-up experience, you can focus on running your own test scenarios and the pre-made simulations to see how Defender for Endpoint performs.</span></span> 

<span data-ttu-id="f5382-114">Sie haben vollständigen Zugriff auf die leistungsstarken Funktionen der Plattform, z. B. automatisierte Untersuchungen, erweiterte Suche und Bedrohungsanalyse, sodass Sie den umfassenden Schutzstapel testen können, den Defender für Endpunkt bietet.</span><span class="sxs-lookup"><span data-stu-id="f5382-114">You'll have full access to the powerful capabilities of the platform such as automated investigations, advanced hunting, and threat analytics, allowing you to test the comprehensive protection stack that Defender for Endpoint offers.</span></span> 

<span data-ttu-id="f5382-115">Sie können Windows 10 oder Windows Server 2019-Geräte hinzufügen, die vorkonfiguriert sind, um die neuesten Betriebssystemversionen und die richtigen Sicherheitskomponenten sowie Office 2019 Standard installiert zu haben.</span><span class="sxs-lookup"><span data-stu-id="f5382-115">You can add Windows 10 or Windows Server 2019 devices that come pre-configured to have the latest OS versions and the right security components in place as well as Office 2019 Standard installed.</span></span>

<span data-ttu-id="f5382-116">Sie können auch Bedrohungssimulatoren installieren.</span><span class="sxs-lookup"><span data-stu-id="f5382-116">You can also install threat simulators.</span></span> <span data-ttu-id="f5382-117">Defender für Endpunkt arbeitet mit branchenführenden Bedrohungssimulationsplattformen zusammen, um Ihnen zu helfen, die Defender für Endpunkt-Funktionen zu testen, ohne das Portal verlassen zu müssen.</span><span class="sxs-lookup"><span data-stu-id="f5382-117">Defender for Endpoint has partnered with industry leading threat simulation platforms to help you test out the Defender for Endpoint capabilities without having to leave the portal.</span></span>

 <span data-ttu-id="f5382-118">Installieren Sie Ihren bevorzugten Simulator, führen Sie Szenarien innerhalb des Evaluierungslabors aus, und sehen Sie sofort, wie die Plattform funktioniert – alles bequem ohne zusätzliche Kosten für Sie verfügbar.</span><span class="sxs-lookup"><span data-stu-id="f5382-118">Install your preferred simulator, run scenarios within the evaluation lab, and instantly see how the platform performs - all conveniently available at no extra cost to you.</span></span> <span data-ttu-id="f5382-119">Sie haben auch bequemen Zugriff auf eine vielzahl von Simulationen, auf die Sie im Simulationskatalog zugreifen und diese ausführen können.</span><span class="sxs-lookup"><span data-stu-id="f5382-119">You'll also have convenient access to wide array of simulations which you can access and run from the simulations catalog.</span></span>
    

## <a name="before-you-begin"></a><span data-ttu-id="f5382-120">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="f5382-120">Before you begin</span></span>
<span data-ttu-id="f5382-121">Sie müssen die [Lizenzierungsanforderungen](minimum-requirements.md#licensing-requirements) erfüllen oder Testzugriff auf Microsoft Defender für Endpunkt haben, um auf das Evaluierungslabor zuzugreifen.</span><span class="sxs-lookup"><span data-stu-id="f5382-121">You'll need to fulfill the [licensing requirements](minimum-requirements.md#licensing-requirements) or have trial access to Microsoft Defender for Endpoint to access the evaluation lab.</span></span>

<span data-ttu-id="f5382-122">Sie benötigen Berechtigungen zum **Verwalten von Sicherheitseinstellungen** für Folgendes:</span><span class="sxs-lookup"><span data-stu-id="f5382-122">You must have **Manage security settings** permissions to:</span></span>
- <span data-ttu-id="f5382-123">Erstellen des Labors</span><span class="sxs-lookup"><span data-stu-id="f5382-123">Create the lab</span></span>
- <span data-ttu-id="f5382-124">Erstellen von Geräten</span><span class="sxs-lookup"><span data-stu-id="f5382-124">Create devices</span></span>
- <span data-ttu-id="f5382-125">Kennwort zurücksetzen</span><span class="sxs-lookup"><span data-stu-id="f5382-125">Reset password</span></span>
- <span data-ttu-id="f5382-126">Erstellen von Simulationen</span><span class="sxs-lookup"><span data-stu-id="f5382-126">Create simulations</span></span> 
 
<span data-ttu-id="f5382-127">Wenn Sie die rollenbasierte Zugriffssteuerung (RBAC) aktiviert und mindestens eine Computergruppe erstellt haben, müssen Benutzer Zugriff auf alle Computergruppen haben.</span><span class="sxs-lookup"><span data-stu-id="f5382-127">If you enabled role-based access control (RBAC) and created at least a one machine group, users must have access to All machine groups.</span></span>

<span data-ttu-id="f5382-128">Weitere Informationen finden Sie unter [Erstellen und Verwalten von Rollen.](user-roles.md)</span><span class="sxs-lookup"><span data-stu-id="f5382-128">For more information, see [Create and manage roles](user-roles.md).</span></span>

<span data-ttu-id="f5382-129">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="f5382-129">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f5382-130">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f5382-130">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-main-abovefoldlink)


## <a name="get-started-with-the-lab"></a><span data-ttu-id="f5382-131">Erste Schritte mit der Übung</span><span class="sxs-lookup"><span data-stu-id="f5382-131">Get started with the lab</span></span>
<span data-ttu-id="f5382-132">Sie können über das Menü auf das Lab zugreifen.</span><span class="sxs-lookup"><span data-stu-id="f5382-132">You can access the lab from the menu.</span></span> <span data-ttu-id="f5382-133">Wählen Sie im Navigationsmenü **evaluierungs- und lernprogramme > Evaluation Lab** aus.</span><span class="sxs-lookup"><span data-stu-id="f5382-133">In the navigation menu, select **Evaluation and tutorials > Evaluation lab**.</span></span>

![Abbildung des Auswertungslabors im Menü](images/evaluation-lab-menu.png)

>[!NOTE]
>- <span data-ttu-id="f5382-135">Je nachdem, welche Art von Umgebungsstruktur Sie auswählen, stehen geräte für die angegebene Anzahl von Stunden ab dem Tag der Aktivierung zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="f5382-135">Depending the type of environment structure you select, devices will be available for the specified number of hours from the day of activation.</span></span>
>- <span data-ttu-id="f5382-136">Jede Umgebung wird mit einer begrenzten Gruppe von Testgeräten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f5382-136">Each environment is provisioned with a limited set of test devices.</span></span> <span data-ttu-id="f5382-137">Wenn Sie die bereitgestellten Geräte verwendet und gelöscht haben, können Sie weitere Geräte anfordern.</span><span class="sxs-lookup"><span data-stu-id="f5382-137">When you've used up the provisioned devices and have deleted them, you can request for more devices.</span></span> 
>- <span data-ttu-id="f5382-138">Sie können einmal im Monat Lab-Ressourcen anfordern.</span><span class="sxs-lookup"><span data-stu-id="f5382-138">You can request for lab resources once a month.</span></span> 

<span data-ttu-id="f5382-139">Haben Sie bereits ein Labor?</span><span class="sxs-lookup"><span data-stu-id="f5382-139">Already have a lab?</span></span> <span data-ttu-id="f5382-140">Stellen Sie sicher, dass Sie die neuen Bedrohungssimulatoren aktivieren und über aktive Geräte verfügen.</span><span class="sxs-lookup"><span data-stu-id="f5382-140">Make sure to enable the new threat simulators and have active devices.</span></span>

## <a name="setup-the-evaluation-lab"></a><span data-ttu-id="f5382-141">Einrichten des Evaluierungslabors</span><span class="sxs-lookup"><span data-stu-id="f5382-141">Setup the evaluation lab</span></span>

1. <span data-ttu-id="f5382-142">Wählen Sie im Navigationsbereich **Evaluierungs- und Lernprogramm-Evaluierungslabor aus,**  >  und wählen Sie dann **Setup lab** aus.</span><span class="sxs-lookup"><span data-stu-id="f5382-142">In the navigation pane, select **Evaluation and tutorials** > **Evaluation lab**, then select **Setup lab**.</span></span>

    ![Abbildung der Willkommensseite der Evaluierungsumgebung](images/evaluation-lab-setup.png)

2. <span data-ttu-id="f5382-144">Je nach Ihren Evaluierungsanforderungen können Sie eine Umgebung mit weniger Geräten für einen längeren Zeitraum oder mehrere Geräte für einen kürzeren Zeitraum einrichten.</span><span class="sxs-lookup"><span data-stu-id="f5382-144">Depending on your evaluation needs, you can choose to setup an environment with fewer devices for a longer period or more devices for a shorter period.</span></span> <span data-ttu-id="f5382-145">Wählen Sie Ihre bevorzugte Lab-Konfiguration aus, und klicken Sie dann auf **"Weiter".**</span><span class="sxs-lookup"><span data-stu-id="f5382-145">Select your preferred lab configuration then select **Next**.</span></span>

    ![Abbildung der Lab-Konfigurationsoptionen](images/lab-creation-page.png) 


3. <span data-ttu-id="f5382-147">(Optional) Sie können sich dafür entscheiden, Bedrohungssimulatoren im Labor zu installieren.</span><span class="sxs-lookup"><span data-stu-id="f5382-147">(Optional) You can choose to install threat simulators in the lab.</span></span> 

    ![Abbildung des Installationssimulator-Agents](images/install-agent.png)

    >[!IMPORTANT]
    ><span data-ttu-id="f5382-149">Sie müssen zunächst die Ausdrücke und Informationen, die Sie teilen, akzeptieren und zustimmen.</span><span class="sxs-lookup"><span data-stu-id="f5382-149">You'll first need to accept and provide consent to the terms and information sharing statements.</span></span> 

4. <span data-ttu-id="f5382-150">Wählen Sie den Agent für die Bedrohungssimulation aus, den Sie verwenden möchten, und geben Sie Ihre Details ein.</span><span class="sxs-lookup"><span data-stu-id="f5382-150">Select the threat simulation agent you'd like to use and enter your details.</span></span> <span data-ttu-id="f5382-151">Sie können auch zu einem späteren Zeitpunkt Bedrohungssimulatoren installieren.</span><span class="sxs-lookup"><span data-stu-id="f5382-151">You can also choose to install threat simulators at a later time.</span></span> <span data-ttu-id="f5382-152">Wenn Sie während des Lab-Setups Bedrohungssimulations-Agents installieren möchten, profitieren Sie von dem Vorteil, dass sie bequem auf den von Ihnen hinzugefügten Geräten installiert werden.</span><span class="sxs-lookup"><span data-stu-id="f5382-152">If you choose to install threat simulation agents during the lab setup, you'll enjoy the benefit of having them conveniently installed on the devices you add.</span></span>  
    
    ![Abbildung der Zusammenfassungsseite](images/lab-setup-summary.png)

5.  <span data-ttu-id="f5382-154">Überprüfen Sie die Zusammenfassung, und wählen Sie **Setup Lab** aus.</span><span class="sxs-lookup"><span data-stu-id="f5382-154">Review the summary and select **Setup lab**.</span></span>  

<span data-ttu-id="f5382-155">Nach Abschluss des Lab-Setupprozesses können Sie Geräte hinzufügen und Simulationen ausführen.</span><span class="sxs-lookup"><span data-stu-id="f5382-155">After the lab setup process is complete, you can add devices and run simulations.</span></span> 


## <a name="add-devices"></a><span data-ttu-id="f5382-156">Hinzufügen von Geräten</span><span class="sxs-lookup"><span data-stu-id="f5382-156">Add devices</span></span>
<span data-ttu-id="f5382-157">Wenn Sie Ihrer Umgebung ein Gerät hinzufügen, richtet Defender für Endpunkt ein gut konfiguriertes Gerät mit Verbindungsdetails ein.</span><span class="sxs-lookup"><span data-stu-id="f5382-157">When you add a device to your environment, Defender for Endpoint sets up a well-configured device with connection details.</span></span> <span data-ttu-id="f5382-158">Sie können Windows 10- oder Windows Server 2019-Geräte hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f5382-158">You can add Windows 10 or Windows Server 2019 devices.</span></span>

<span data-ttu-id="f5382-159">Das Gerät wird mit der aktuellsten Version des Betriebssystems und Office 2019 Standard sowie anderen Apps wie Java, Python und SysIntenals konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="f5382-159">The device will be configured with the most up-to-date version of the OS and Office 2019 Standard as well as other apps such as Java, Python, and SysIntenals.</span></span> 

<span data-ttu-id="f5382-160">Wenn Sie während des Lab-Setups einen Bedrohungssimulator hinzugefügt haben, wird auf allen Geräten der Bedrohungssimulator-Agent auf den geräten installiert, die Sie hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f5382-160">If you chose to add a threat simulator during the lab setup, all devices will have the threat simulator agent installed in the devices that you add.</span></span>

<span data-ttu-id="f5382-161">Das Gerät wird automatisch in Ihren Mandanten integriert, wobei die empfohlenen Windows Sicherheitskomponenten aktiviert sind und sich im Überwachungsmodus befinden – ohne Aufwand auf Ihrer Seite.</span><span class="sxs-lookup"><span data-stu-id="f5382-161">The device will automatically be onboarded to your tenant with the recommended Windows security components turned on and in audit mode - with no effort on your side.</span></span> 

<span data-ttu-id="f5382-162">Die folgenden Sicherheitskomponenten sind auf den Testgeräten vorkonfiguriert:</span><span class="sxs-lookup"><span data-stu-id="f5382-162">The following security components are pre-configured in the test devices:</span></span>

- <span data-ttu-id="f5382-163">[Verringerung der Angriffsfläche](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard):</span><span class="sxs-lookup"><span data-stu-id="f5382-163">[Attack surface reduction](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction-exploit-guard)</span></span>
- [<span data-ttu-id="f5382-164">Bei erster Anzeige blockieren</span><span class="sxs-lookup"><span data-stu-id="f5382-164">Block at first sight</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
- [<span data-ttu-id="f5382-165">Kontrollierter Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="f5382-165">Controlled folder access</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/controlled-folders-exploit-guard)
- [<span data-ttu-id="f5382-166">Exploit-Schutz.</span><span class="sxs-lookup"><span data-stu-id="f5382-166">Exploit protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/enable-exploit-protection)
- [<span data-ttu-id="f5382-167">Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="f5382-167">Network protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/network-protection-exploit-guard)
- [<span data-ttu-id="f5382-168">Erkennung potenziell unerwünschter Anwendungen</span><span class="sxs-lookup"><span data-stu-id="f5382-168">Potentially unwanted application detection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [<span data-ttu-id="f5382-169">Über die Cloud bereitgestellter Schutz</span><span class="sxs-lookup"><span data-stu-id="f5382-169">Cloud-delivered protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
- [<span data-ttu-id="f5382-170">Microsoft Defender SmartScreen</span><span class="sxs-lookup"><span data-stu-id="f5382-170">Microsoft Defender SmartScreen</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-smartscreen/windows-defender-smartscreen-overview)

>[!NOTE]
> <span data-ttu-id="f5382-171">Microsoft Defender Antivirus ist aktiviert (nicht im Überwachungsmodus).</span><span class="sxs-lookup"><span data-stu-id="f5382-171">Microsoft Defender Antivirus will be on (not in audit mode).</span></span> <span data-ttu-id="f5382-172">Wenn Microsoft Defender Antivirus die Ausführung der Simulation verhindert, können Sie den Echtzeitschutz auf dem Gerät über Windows-Sicherheit deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="f5382-172">If Microsoft Defender Antivirus blocks you from running your simulation, you can turn off real-time protection on the device through Windows Security.</span></span> <span data-ttu-id="f5382-173">Weitere Informationen finden Sie unter ["Always-On-Schutz konfigurieren".](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="f5382-173">For more information, see [Configure always-on protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="f5382-174">Die Einstellungen für die automatische Untersuchung hängen von den Mandanteneinstellungen ab.</span><span class="sxs-lookup"><span data-stu-id="f5382-174">Automated investigation settings will be dependent on tenant settings.</span></span> <span data-ttu-id="f5382-175">Sie wird standardmäßig so konfiguriert, dass sie halbautomatisiert ist.</span><span class="sxs-lookup"><span data-stu-id="f5382-175">It will be configured to be semi-automated by default.</span></span> <span data-ttu-id="f5382-176">Weitere Informationen finden Sie unter [Übersicht über automatisierte Untersuchungen.](automated-investigations.md)</span><span class="sxs-lookup"><span data-stu-id="f5382-176">For more information, see [Overview of Automated investigations](automated-investigations.md).</span></span>

>[!NOTE]
><span data-ttu-id="f5382-177">Die Verbindung mit den Testgeräten erfolgt über RDP.</span><span class="sxs-lookup"><span data-stu-id="f5382-177">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="f5382-178">Stellen Sie sicher, dass ihre Firewalleinstellungen RDP-Verbindungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="f5382-178">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="f5382-179">Wählen Sie im Dashboard **"Gerät hinzufügen"** aus.</span><span class="sxs-lookup"><span data-stu-id="f5382-179">From the dashboard, select **Add device**.</span></span> 

2. <span data-ttu-id="f5382-180">Wählen Sie den Typ des hinzuzufügenden Geräts aus.</span><span class="sxs-lookup"><span data-stu-id="f5382-180">Choose the type of device to add.</span></span> <span data-ttu-id="f5382-181">Sie können Windows 10 oder Windows Server 2019 hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="f5382-181">You can choose to add Windows 10 or Windows Server 2019.</span></span>

    ![Abbildung des Lab-Setups mit Geräteoptionen](images/add-machine-options.png)


    >[!NOTE]
    ><span data-ttu-id="f5382-183">Wenn beim Geräteerstellungsprozess ein Fehler auftritt, werden Sie benachrichtigt, und Sie müssen eine neue Anforderung senden.</span><span class="sxs-lookup"><span data-stu-id="f5382-183">If something goes wrong with the device creation process, you'll be notified and you'll need to submit a new request.</span></span> <span data-ttu-id="f5382-184">Wenn die Geräteerstellung fehlschlägt, wird sie nicht mit dem insgesamt zulässigen Kontingent gezählt.</span><span class="sxs-lookup"><span data-stu-id="f5382-184">If the device creation fails, it will not be counted against the overall allowed quota.</span></span> 

3. <span data-ttu-id="f5382-185">Die Verbindungsdetails werden angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5382-185">The connection details are displayed.</span></span> <span data-ttu-id="f5382-186">Wählen Sie **"Kopieren"** aus, um das Kennwort für das Gerät zu speichern.</span><span class="sxs-lookup"><span data-stu-id="f5382-186">Select **Copy** to save the password for the device.</span></span>

    >[!NOTE]
    ><span data-ttu-id="f5382-187">Das Kennwort wird nur einmal angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5382-187">The password is only displayed once.</span></span> <span data-ttu-id="f5382-188">Speichern Sie es unbedingt für die spätere Verwendung.</span><span class="sxs-lookup"><span data-stu-id="f5382-188">Be sure to save it for later use.</span></span>

    ![Abbildung des Geräts, das mit Verbindungsdetails hinzugefügt wurde](images/add-machine-eval-lab.png)

4. <span data-ttu-id="f5382-190">Die Geräteeinrichtung beginnt.</span><span class="sxs-lookup"><span data-stu-id="f5382-190">Device set up begins.</span></span> <span data-ttu-id="f5382-191">Dies kann bis zu ungefähr 30 Minuten dauern.</span><span class="sxs-lookup"><span data-stu-id="f5382-191">This can take up to approximately 30 minutes.</span></span> 

5. <span data-ttu-id="f5382-192">Sehen Sie sich den Status der Testgeräte, das Risiko und die Belichtungsgrade sowie den Status von Simulatorinstallationen an, indem Sie die Registerkarte **"Geräte"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f5382-192">See the status of test devices, the risk and exposure levels, and the status of simulator installations by selecting the **Devices** tab.</span></span> 

    ![Abbildung der Registerkarte "Geräte"](images/machines-tab.png)
    

    > [!TIP]
    > <span data-ttu-id="f5382-194">In der **Statusspalte des Simulators** können Sie auf das Informationssymbol zeigen, um den Installationsstatus eines Agents zu kennen.</span><span class="sxs-lookup"><span data-stu-id="f5382-194">In the **Simulator status** column, you can hover over the information icon to know the installation status of an agent.</span></span>

## <a name="request-for-more-devices"></a><span data-ttu-id="f5382-195">Anfordern weiterer Geräte</span><span class="sxs-lookup"><span data-stu-id="f5382-195">Request for more devices</span></span>
<span data-ttu-id="f5382-196">Wenn alle vorhandenen Geräte verwendet und gelöscht werden, können Sie weitere Geräte anfordern.</span><span class="sxs-lookup"><span data-stu-id="f5382-196">When all existing devices are used and deleted, you can request for more devices.</span></span> <span data-ttu-id="f5382-197">Sie können einmal im Monat Lab-Ressourcen anfordern.</span><span class="sxs-lookup"><span data-stu-id="f5382-197">You can request for lab resources once a month.</span></span> 


1. <span data-ttu-id="f5382-198">Wählen Sie im Evaluierungslabordashboard die Option **"Anforderung für weitere Geräte"** aus.</span><span class="sxs-lookup"><span data-stu-id="f5382-198">From the evaluation lab dashboard, select **Request for more devices**.</span></span>

   ![Abbildung der Anforderung für weitere Geräte](images/request-more-devices.png)

2. <span data-ttu-id="f5382-200">Wählen Sie Ihre Konfiguration aus.</span><span class="sxs-lookup"><span data-stu-id="f5382-200">Choose your configuration.</span></span> 
3. <span data-ttu-id="f5382-201">Senden Sie die Anforderung.</span><span class="sxs-lookup"><span data-stu-id="f5382-201">Submit the request.</span></span> 

<span data-ttu-id="f5382-202">Wenn die Anforderung erfolgreich übermittelt wurde, sehen Sie ein grünes Bestätigungsbanner und das Datum der letzten Übermittlung.</span><span class="sxs-lookup"><span data-stu-id="f5382-202">When the request is submitted successfully you'll see a green confirmation banner and the date of the last submission.</span></span>
 
<span data-ttu-id="f5382-203">Den Status Ihrer Anforderung finden Sie auf der Registerkarte **"Benutzeraktionen",** die innerhalb von wenigen Stunden genehmigt wird.</span><span class="sxs-lookup"><span data-stu-id="f5382-203">You can find the status of your request in the **User Actions** tab, which will be approved in a matter of hours.</span></span>

<span data-ttu-id="f5382-204">Nach der Genehmigung werden die angeforderten Geräte zu Ihrem Lab-Setup hinzugefügt, und Sie können weitere Geräte erstellen.</span><span class="sxs-lookup"><span data-stu-id="f5382-204">When approved, the requested devices will be added to your lab set up and you’ll be able to create more devices.</span></span> 


> [!TIP]
> <span data-ttu-id="f5382-205">Um mehr aus Ihrem Labor herauszuholen, vergessen Sie nicht, unsere Simulationsbibliothek zu besuchen.</span><span class="sxs-lookup"><span data-stu-id="f5382-205">To get more out of your lab, don’t forget to check out our simulations library.</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="f5382-206">Simulieren von Angriffsszenarien</span><span class="sxs-lookup"><span data-stu-id="f5382-206">Simulate attack scenarios</span></span>
<span data-ttu-id="f5382-207">Verwenden Sie die Testgeräte, um Ihre eigenen Angriffssimulationen auszuführen, indem Sie eine Verbindung mit ihnen herstellen.</span><span class="sxs-lookup"><span data-stu-id="f5382-207">Use the test devices to run your own attack simulations by connecting to them.</span></span> 

<span data-ttu-id="f5382-208">Sie können Angriffsszenarien mit folgenden Aktionen simulieren:</span><span class="sxs-lookup"><span data-stu-id="f5382-208">You can simulate attack scenarios using:</span></span>
- <span data-ttu-id="f5382-209">Die [Angriffsszenarien "Selbst erledigen"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="f5382-209">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="f5382-210">Bedrohungssimulatoren</span><span class="sxs-lookup"><span data-stu-id="f5382-210">Threat simulators</span></span>

<span data-ttu-id="f5382-211">Sie können die [erweiterte Suche](advanced-hunting-query-language.md) auch verwenden, um Daten und [Bedrohungsanalysen](threat-analytics.md) abzufragen, um Berichte über neue Bedrohungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="f5382-211">You can also use [Advanced hunting](advanced-hunting-query-language.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="f5382-212">Do-it-yourself-Angriffsszenarien</span><span class="sxs-lookup"><span data-stu-id="f5382-212">Do-it-yourself attack scenarios</span></span>
<span data-ttu-id="f5382-213">Wenn Sie nach einer vorgefertigten Simulation suchen, können Sie unsere ["Do It Yourself"-Angriffsszenarien](https://securitycenter.windows.com/tutorials)verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5382-213">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="f5382-214">Diese Skripts sind sicher, dokumentiert und einfach zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="f5382-214">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="f5382-215">Diese Szenarien spiegeln die Defender für Endpunkt-Funktionen wider und führen Sie durch die Untersuchungserfahrung.</span><span class="sxs-lookup"><span data-stu-id="f5382-215">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>


>[!NOTE]
><span data-ttu-id="f5382-216">Die Verbindung mit den Testgeräten erfolgt über RDP.</span><span class="sxs-lookup"><span data-stu-id="f5382-216">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="f5382-217">Stellen Sie sicher, dass ihre Firewalleinstellungen RDP-Verbindungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="f5382-217">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="f5382-218">Verbinden zu Ihrem Gerät, und führen Sie eine Angriffssimulation **aus,** indem Sie Verbinden auswählen.</span><span class="sxs-lookup"><span data-stu-id="f5382-218">Connect to your device and run an attack simulation by selecting **Connect**.</span></span> 

    ![Abbildung der Schaltfläche "Verbinden" für Testgeräte](images/test-machine-table.png)

2. <span data-ttu-id="f5382-220">Speichern Sie die RDP-Datei, und starten Sie sie, indem Sie **Verbinden** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f5382-220">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Abbildung der Remotedesktopverbindung](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="f5382-222">Wenn Sie während der Ersteinrichtung keine Kopie des Kennworts gespeichert haben, können Sie das Kennwort zurücksetzen, indem Sie das Kennwort im Menü **zurücksetzen** auswählen: ![ Abbildung des Kennworts zurücksetzen](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="f5382-222">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span><br>
    > <span data-ttu-id="f5382-223">Das Gerät ändert seinen Zustand in "Ausführen der Kennwortzurücksetzung", dann wird Ihnen das neue Kennwort in ein paar Minuten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="f5382-223">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="f5382-224">Geben Sie das Kennwort ein, das während des Geräteerstellungsschritts angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="f5382-224">Enter the password that was displayed during the device creation step.</span></span> 

   ![Abbildung des Fensters zum Eingeben von Anmeldeinformationen](images/enter-password.png)

4. <span data-ttu-id="f5382-226">Führen Sie Do-it-yourself-Angriffssimulationen auf dem Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="f5382-226">Run Do-it-yourself attack simulations on the device.</span></span> 


### <a name="threat-simulator-scenarios"></a><span data-ttu-id="f5382-227">Bedrohungssimulatorszenarien</span><span class="sxs-lookup"><span data-stu-id="f5382-227">Threat simulator scenarios</span></span>
<span data-ttu-id="f5382-228">Wenn Sie sich entschieden haben, während des Lab-Setups einen der unterstützten Bedrohungssimulatoren zu installieren, können Sie die integrierten Simulationen auf den Evaluierungslaborgeräten ausführen.</span><span class="sxs-lookup"><span data-stu-id="f5382-228">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span> 


<span data-ttu-id="f5382-229">Das Ausführen von Bedrohungssimulationen mitHilfe von Drittanbieterplattformen ist eine gute Möglichkeit, um Die Funktionen von Microsoft Defender für Endpunkte innerhalb einer Lab-Umgebung zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="f5382-229">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
><span data-ttu-id="f5382-230">Bevor Sie Simulationen ausführen können, stellen Sie sicher, dass die folgenden Anforderungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="f5382-230">Before you can run simulations, ensure the following requirements are met:</span></span>
>- <span data-ttu-id="f5382-231">Geräte müssen dem Evaluierungslabor hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="f5382-231">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="f5382-232">Bedrohungssimulatoren müssen im Evaluierungslabor installiert werden.</span><span class="sxs-lookup"><span data-stu-id="f5382-232">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="f5382-233">Wählen Sie im Portal **Simulation erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="f5382-233">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="f5382-234">Wählen Sie einen Bedrohungssimulator aus.</span><span class="sxs-lookup"><span data-stu-id="f5382-234">Select a threat simulator.</span></span>

    ![Abbildung der Auswahl des Bedrohungssimulators](images/select-simulator.png)

3. <span data-ttu-id="f5382-236">Wählen Sie eine Simulation aus, oder sehen Sie sich den Simulationskatalog an, um die verfügbaren Simulationen zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="f5382-236">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span> 

    <span data-ttu-id="f5382-237">Sie können den Simulationskatalog von:</span><span class="sxs-lookup"><span data-stu-id="f5382-237">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="f5382-238">Das Hauptauswertungsdashboard in der Kachel **"Simulationsübersicht"** oder</span><span class="sxs-lookup"><span data-stu-id="f5382-238">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="f5382-239">Wählen Sie dann im Navigationsbereich **"Evaluierung" und "Lernprogramme**  >  **Simulation & Lernprogramme"** den **Simulationskatalog** aus.</span><span class="sxs-lookup"><span data-stu-id="f5382-239">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="f5382-240">Wählen Sie die Geräte aus, auf denen Sie die Simulation ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="f5382-240">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="f5382-241">Wählen Sie **Simulation erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="f5382-241">Select **Create simulation**.</span></span>

6. <span data-ttu-id="f5382-242">Zeigen Sie den Fortschritt einer Simulation an, indem Sie die Registerkarte **Simulationen** auswählen. Zeigen Sie den Simulationsstatus, aktive Warnungen und andere Details an.</span><span class="sxs-lookup"><span data-stu-id="f5382-242">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span> 

    ![Abbildung der Registerkarte "Simulationen"](images/simulations-tab.png)
    
<span data-ttu-id="f5382-244">Nachdem Sie Ihre Simulationen ausgeführt haben, empfehlen wir Ihnen, die Testfortschrittsleiste zu durchlaufen und Microsoft Defender für Endpunkt zu erkunden, um **eine automatisierte Untersuchung und Behebung auszulösen.**</span><span class="sxs-lookup"><span data-stu-id="f5382-244">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="f5382-245">Sehen Sie sich die von der Funktion gesammelten und analysierten Nachweise an.</span><span class="sxs-lookup"><span data-stu-id="f5382-245">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="f5382-246">Suchen Sie nach Angriffsnachweisen durch die erweiterte Suche mithilfe der umfangreichen Abfragesprache und der unformatierten Telemetrie, und sehen Sie sich einige weltweite Bedrohungen an, die in der Bedrohungsanalyse dokumentiert sind.</span><span class="sxs-lookup"><span data-stu-id="f5382-246">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>


## <a name="simulation-gallery"></a><span data-ttu-id="f5382-247">Simulationskatalog</span><span class="sxs-lookup"><span data-stu-id="f5382-247">Simulation gallery</span></span>
<span data-ttu-id="f5382-248">Microsoft Defender für Endpunkt hat sich mit verschiedenen Bedrohungssimulationsplattformen zusammen entwickelt, um Ihnen bequemen Zugriff zu bieten, um die Funktionen der Plattform direkt im Portal zu testen.</span><span class="sxs-lookup"><span data-stu-id="f5382-248">Microsoft Defender for Endpoint has partnered with various threat simulation platforms to give you convenient access to test the capabilities of the platform right from the within the portal.</span></span> 

<span data-ttu-id="f5382-249">Zeigen Sie alle verfügbaren Simulationen an, indem Sie im Menü zum Simulations- **und Lernprogrammkatalog**  >   wechseln.</span><span class="sxs-lookup"><span data-stu-id="f5382-249">View all the available simulations by going to  **Simulations and tutorials** > **Simulations catalog**  from the menu.</span></span> 

<span data-ttu-id="f5382-250">Es wird eine Liste der unterstützten Bedrohungssimulations-Agents von Drittanbietern aufgeführt, und bestimmte Simulationstypen sowie detaillierte Beschreibungen werden im Katalog bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="f5382-250">A list of supported third-party threat simulation agents are listed, and specific types of simulations along with detailed descriptions are provided on the catalog.</span></span> 

<span data-ttu-id="f5382-251">Sie können jede verfügbare Simulation direkt aus dem Katalog ausführen.</span><span class="sxs-lookup"><span data-stu-id="f5382-251">You can conveniently run any available simulation right from the catalog.</span></span>  


![Abbildung des Simulationskatalogs](images/simulations-catalog.png)

<span data-ttu-id="f5382-253">Jede Simulation enthält eine ausführliche Beschreibung des Angriffsszenarios und Referenzen wie die verwendeten MITRE-Angriffstechniken und Beispielabfragen für die erweiterte Suche, die Sie ausführen.</span><span class="sxs-lookup"><span data-stu-id="f5382-253">Each simulation comes with an in-depth description of the attack scenario and references such as the MITRE attack techniques used and sample Advanced hunting queries you run.</span></span>

<span data-ttu-id="f5382-254">**Beispiele:** 
 ![ Abbildung der Simulationsbeschreibungsdetails1](images/simulation-details-aiq.png)</span><span class="sxs-lookup"><span data-stu-id="f5382-254">**Examples:**
![Image of simulation description details1](images/simulation-details-aiq.png)</span></span>


![Abbildung der Simulationsbeschreibung – Details2](images/simulation-details-sb.png)


## <a name="evaluation-report"></a><span data-ttu-id="f5382-256">Evaluierungsbericht</span><span class="sxs-lookup"><span data-stu-id="f5382-256">Evaluation report</span></span>
<span data-ttu-id="f5382-257">Die Laborberichte fassen die Ergebnisse der auf den Geräten durchgeführten Simulationen zusammen.</span><span class="sxs-lookup"><span data-stu-id="f5382-257">The lab reports summarize the results of the simulations conducted on the devices.</span></span>

![Abbildung des Evaluierungsberichts](images/eval-report.png)

<span data-ttu-id="f5382-259">Auf einen Blick können Sie schnell folgendes sehen:</span><span class="sxs-lookup"><span data-stu-id="f5382-259">At a glance, you'll quickly be able to see:</span></span>
- <span data-ttu-id="f5382-260">Ausgelöste Vorfälle</span><span class="sxs-lookup"><span data-stu-id="f5382-260">Incidents that were triggered</span></span>
- <span data-ttu-id="f5382-261">Generierte Warnungen</span><span class="sxs-lookup"><span data-stu-id="f5382-261">Generated alerts</span></span>
- <span data-ttu-id="f5382-262">Bewertungen der Belichtungsstufe</span><span class="sxs-lookup"><span data-stu-id="f5382-262">Assessments on exposure level</span></span> 
- <span data-ttu-id="f5382-263">Beobachtete Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="f5382-263">Threat categories observed</span></span>
- <span data-ttu-id="f5382-264">Erkennungsquellen</span><span class="sxs-lookup"><span data-stu-id="f5382-264">Detection sources</span></span>
- <span data-ttu-id="f5382-265">Automatisierte Untersuchungen</span><span class="sxs-lookup"><span data-stu-id="f5382-265">Automated investigations</span></span>


## <a name="provide-feedback"></a><span data-ttu-id="f5382-266">Feedback geben</span><span class="sxs-lookup"><span data-stu-id="f5382-266">Provide feedback</span></span>
<span data-ttu-id="f5382-267">Ihr Feedback hilft uns, Ihre Umgebung besser vor fortgeschrittenen Angriffen zu schützen.</span><span class="sxs-lookup"><span data-stu-id="f5382-267">Your feedback helps us get better in protecting your environment from advanced attacks.</span></span> <span data-ttu-id="f5382-268">Teilen Sie Ihre Erfahrungen und Aufrufe von Produktfunktionen und Evaluierungsergebnissen.</span><span class="sxs-lookup"><span data-stu-id="f5382-268">Share your experience and impressions from product capabilities and evaluation results.</span></span>

<span data-ttu-id="f5382-269">Teilen Sie uns Ihre Meinung mit, indem Sie **"Feedback bereitstellen"** auswählen.</span><span class="sxs-lookup"><span data-stu-id="f5382-269">Let us know what you think, by selecting **Provide feedback**.</span></span>

![Abbildung von Feedback](images/send-us-feedback-eval-lab.png)
