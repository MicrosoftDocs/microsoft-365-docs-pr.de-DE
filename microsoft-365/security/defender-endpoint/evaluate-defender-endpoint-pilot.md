---
title: Microsoft Defender für Endpunkt (MDE) durch simulierte Angriffe erleben
description: Testen Sie Ihre Microsoft 365 Defender Testumgebung oder Pilotumgebung.
keywords: Microsoft 365 Defender Testversion, testen Sie Microsoft 365 Defender, bewerten Sie Microsoft 365 Defender, Microsoft 365 Defender Evaluierungslabor, Microsoft 365 Defender Pilotprojekt, Cybersicherheit, erweiterte dauerhafte Bedrohung, Unternehmenssicherheit, Geräte, Gerät, Identität, Benutzer, Daten, Anwendungen, Vorfälle, automatisierte Untersuchung und Behebung, erweiterte Suche
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 131a048e806976afa3bffbd3f3bce2d61a370225
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458141"
---
# <a name="experience-microsoft-defender-for-endpoint-mde-through-simulated-attacks"></a><span data-ttu-id="790e8-104">Microsoft Defender für Endpunkt (MDE) durch simulierte Angriffe erleben</span><span class="sxs-lookup"><span data-stu-id="790e8-104">Experience Microsoft Defender for Endpoint (MDE) through simulated attacks</span></span>

>[!TIP]
>
>- <span data-ttu-id="790e8-105">Erfahren Sie mehr über die neuesten Verbesserungen in Microsoft Defender für Endpunkt: [Was ist neu in Defender für Endpunkt?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="790e8-105">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="790e8-106">Defender für Endpunkt hat in der letzten MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen demonstriert.</span><span class="sxs-lookup"><span data-stu-id="790e8-106">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="790e8-107">Lesen Sie: [Insights aus der MITRE ATT&CK-basierten Auswertung.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="790e8-107">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="790e8-108">Möglicherweise möchten Sie Defender für Endpunkt testen, bevor Sie mehr als ein paar Geräte in den Dienst integrieren.</span><span class="sxs-lookup"><span data-stu-id="790e8-108">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="790e8-109">Dazu können Sie kontrollierte Angriffssimulationen auf einigen Testgeräten ausführen.</span><span class="sxs-lookup"><span data-stu-id="790e8-109">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="790e8-110">Nachdem Sie die simulierten Angriffe ausgeführt haben, können Sie überprüfen, wie Defender für Endpunkt bösartige Aktivitäten aufdecken und untersuchen, wie es eine effiziente Reaktion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="790e8-110">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="790e8-111">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="790e8-111">Before you begin</span></span>

<span data-ttu-id="790e8-112">Zum Ausführen einer der bereitgestellten Simulationen benötigen Sie mindestens [ein integriertes Gerät.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="790e8-112">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span>

<span data-ttu-id="790e8-113">Lesen Sie das exemplarische Vorgehensweisendokument, das für jedes Angriffsszenario bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="790e8-113">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="790e8-114">Jedes Dokument enthält Betriebssystem- und Anwendungsanforderungen sowie detaillierte Anweisungen, die für ein Angriffsszenario spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="790e8-114">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="790e8-115">Ausführen einer Simulation</span><span class="sxs-lookup"><span data-stu-id="790e8-115">Run a simulation</span></span>

1. <span data-ttu-id="790e8-116">Wählen Sie **in**  >  **Hilfesimulationen & Lernprogrammen** aus, welche der verfügbaren Angriffsszenarien Sie simulieren möchten:</span><span class="sxs-lookup"><span data-stu-id="790e8-116">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="790e8-117">**Szenario 1: Dokument fällt Hintertür ab** – simuliert die Bereitstellung eines Social Engineering-Lockdokuments.</span><span class="sxs-lookup"><span data-stu-id="790e8-117">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="790e8-118">Das Dokument startet eine speziell gestaltete Hintertür, die Angreifern die Kontrolle gibt.</span><span class="sxs-lookup"><span data-stu-id="790e8-118">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="790e8-119">**Szenario 2: PowerShell-Skript bei dateilosen Angriffen** – simuliert einen dateilosen Angriff, der auf PowerShell basiert, die Reduzierung der Angriffsfläche und die Erkennung bösartiger Speicheraktivitäten durch Geräte.</span><span class="sxs-lookup"><span data-stu-id="790e8-119">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>

   - <span data-ttu-id="790e8-120">**Szenario 3: Automatisierte Reaktion auf Sicherheitsvorfälle** – löst eine automatisierte Untersuchung aus, die automatisch Nach- und Korrektur von Verletzungsartefakten auslöst, um Ihre Reaktionsfähigkeit auf Vorfälle zu skalieren.</span><span class="sxs-lookup"><span data-stu-id="790e8-120">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="790e8-121">Laden Sie das entsprechende Exemplarische Vorgehensweise-Dokument herunter, und lesen Sie es, das sie in Ihrem ausgewählten Szenario bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="790e8-121">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="790e8-122">Laden Sie die Simulationsdatei herunter, oder kopieren Sie das Simulationsskript, indem **Sie** zu  >  **Hilfesimulationen & Lernprogrammen** navigieren.</span><span class="sxs-lookup"><span data-stu-id="790e8-122">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="790e8-123">Sie können die Datei oder das Skript auf das Testgerät herunterladen, dies ist jedoch nicht obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="790e8-123">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="790e8-124">Führen Sie die Simulationsdatei oder das Skript auf dem Testgerät aus, wie im Dokument mit exemplarischer Vorgehensweise beschrieben.</span><span class="sxs-lookup"><span data-stu-id="790e8-124">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="790e8-125">Simulationsdateien oder Skripts imitieren Angriffsaktivitäten, sind aber eigentlich gutartig und schaden dem Testgerät nicht.</span><span class="sxs-lookup"><span data-stu-id="790e8-125">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
>

## <a name="alternate-topic-text"></a><span data-ttu-id="790e8-126">ALTERNATIVER THEMENTEXT</span><span class="sxs-lookup"><span data-stu-id="790e8-126">ALTERNATE TOPIC TEXT</span></span>

## <a name="simulate-attack-scenarios"></a><span data-ttu-id="790e8-127">Simulieren von Angriffsszenarien</span><span class="sxs-lookup"><span data-stu-id="790e8-127">Simulate attack scenarios</span></span>

<span data-ttu-id="790e8-128">Verwenden Sie die Testgeräte, um Ihre eigenen Angriffssimulationen auszuführen, indem Sie eine Verbindung mit ihnen herstellen.</span><span class="sxs-lookup"><span data-stu-id="790e8-128">Use the test devices to run your own attack simulations by connecting to them.</span></span>

<span data-ttu-id="790e8-129">Sie können Angriffsszenarien mit folgenden Aktionen simulieren:</span><span class="sxs-lookup"><span data-stu-id="790e8-129">You can simulate attack scenarios using:</span></span>

- <span data-ttu-id="790e8-130">Die [Angriffsszenarien "Selbst erledigen"](https://securitycenter.windows.com/tutorials)</span><span class="sxs-lookup"><span data-stu-id="790e8-130">The ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials)</span></span>
- <span data-ttu-id="790e8-131">Bedrohungssimulatoren</span><span class="sxs-lookup"><span data-stu-id="790e8-131">Threat simulators</span></span>

<span data-ttu-id="790e8-132">Sie können die [erweiterte Suche](advanced-hunting-overview.md) auch verwenden, um Daten und [Bedrohungsanalysen](threat-analytics.md) abzufragen, um Berichte über neue Bedrohungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="790e8-132">You can also use [Advanced hunting](advanced-hunting-overview.md) to query data and [Threat analytics](threat-analytics.md) to view reports about emerging threats.</span></span>

### <a name="do-it-yourself-attack-scenarios"></a><span data-ttu-id="790e8-133">Do-it-yourself-Angriffsszenarien</span><span class="sxs-lookup"><span data-stu-id="790e8-133">Do-it-yourself attack scenarios</span></span>

<span data-ttu-id="790e8-134">Wenn Sie nach einer vorgefertigten Simulation suchen, können Sie unsere ["Do It Yourself"-Angriffsszenarien](https://securitycenter.windows.com/tutorials)verwenden.</span><span class="sxs-lookup"><span data-stu-id="790e8-134">If you are looking for a pre-made simulation, you can use our ["Do It Yourself" attack scenarios](https://securitycenter.windows.com/tutorials).</span></span> <span data-ttu-id="790e8-135">Diese Skripts sind sicher, dokumentiert und einfach zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="790e8-135">These scripts are safe, documented, and easy to use.</span></span> <span data-ttu-id="790e8-136">Diese Szenarien spiegeln die Defender für Endpunkt-Funktionen wider und führen Sie durch die Untersuchungserfahrung.</span><span class="sxs-lookup"><span data-stu-id="790e8-136">These scenarios will reflect Defender for Endpoint capabilities and walk you through investigation experience.</span></span>

>[!NOTE]
><span data-ttu-id="790e8-137">Die Verbindung mit den Testgeräten erfolgt über RDP.</span><span class="sxs-lookup"><span data-stu-id="790e8-137">The connection to the test devices is done using RDP.</span></span> <span data-ttu-id="790e8-138">Stellen Sie sicher, dass ihre Firewalleinstellungen RDP-Verbindungen zulassen.</span><span class="sxs-lookup"><span data-stu-id="790e8-138">Make sure that your firewall settings allow RDP connections.</span></span>

1. <span data-ttu-id="790e8-139">Verbinden zu Ihrem Gerät, und führen Sie eine Angriffssimulation **aus,** indem Sie Verbinden auswählen.</span><span class="sxs-lookup"><span data-stu-id="790e8-139">Connect to your device and run an attack simulation by selecting **Connect**.</span></span>

    ![Abbildung der Schaltfläche "Verbinden" für Testgeräte](images/test-machine-table.png)

2. <span data-ttu-id="790e8-141">Speichern Sie die RDP-Datei, und starten Sie sie, indem Sie **Verbinden** auswählen.</span><span class="sxs-lookup"><span data-stu-id="790e8-141">Save the RDP file and launch it by selecting **Connect**.</span></span>

    ![Abbildung der Remotedesktopverbindung](images/remote-connection.png)

    >[!NOTE]
    ><span data-ttu-id="790e8-143">Wenn Sie während der Ersteinrichtung keine Kopie des Kennworts gespeichert haben, können Sie das Kennwort zurücksetzen, indem Sie im Menü **"Kennwort zurücksetzen"** auswählen: ![ Abbildung des Kennworts zurücksetzen](images/reset-password-test-machine.png)</span><span class="sxs-lookup"><span data-stu-id="790e8-143">If you don't have a copy of the password saved during the initial setup, you can reset the password by selecting **Reset password** from the menu: ![Image of reset password](images/reset-password-test-machine.png)</span></span>
    >
    > <span data-ttu-id="790e8-144">Das Gerät ändert seinen Zustand in "Ausführen der Kennwortzurücksetzung", dann wird Ihnen das neue Kennwort in ein paar Minuten angezeigt.</span><span class="sxs-lookup"><span data-stu-id="790e8-144">The device will change it’s state to “Executing password reset", then you’ll be presented with your new password in a few minutes.</span></span>

3. <span data-ttu-id="790e8-145">Geben Sie das Kennwort ein, das während des Geräteerstellungsschritts angezeigt wurde.</span><span class="sxs-lookup"><span data-stu-id="790e8-145">Enter the password that was displayed during the device creation step.</span></span>

   ![Abbildung des Fensters zum Eingeben von Anmeldeinformationen](images/enter-password.png)

4. <span data-ttu-id="790e8-147">Führen Sie Do-it-yourself-Angriffssimulationen auf dem Gerät aus.</span><span class="sxs-lookup"><span data-stu-id="790e8-147">Run Do-it-yourself attack simulations on the device.</span></span>

### <a name="threat-simulator-scenarios"></a><span data-ttu-id="790e8-148">Szenarien des Bedrohungssimulators</span><span class="sxs-lookup"><span data-stu-id="790e8-148">Threat simulator scenarios</span></span>

<span data-ttu-id="790e8-149">Wenn Sie sich entschieden haben, während des Lab-Setups einen der unterstützten Bedrohungssimulatoren zu installieren, können Sie die integrierten Simulationen auf den Evaluierungslaborgeräten ausführen.</span><span class="sxs-lookup"><span data-stu-id="790e8-149">If you chose to install any of the supported threat simulators during the lab setup, you can run the built-in simulations on the evaluation lab devices.</span></span>

<span data-ttu-id="790e8-150">Das Ausführen von Bedrohungssimulationen mitHilfe von Drittanbieterplattformen ist eine gute Möglichkeit, um Die Funktionen von Microsoft Defender für Endpunkte innerhalb einer Lab-Umgebung zu bewerten.</span><span class="sxs-lookup"><span data-stu-id="790e8-150">Running threat simulations using third-party platforms is a good way to evaluate Microsoft Defender for Endpoint capabilities within the confines of a lab environment.</span></span>

>[!NOTE]
>
><span data-ttu-id="790e8-151">Bevor Sie Simulationen ausführen können, stellen Sie sicher, dass die folgenden Anforderungen erfüllt sind:</span><span class="sxs-lookup"><span data-stu-id="790e8-151">Before you can run simulations, ensure the following requirements are met:</span></span>

>- <span data-ttu-id="790e8-152">Geräte müssen dem Evaluierungslabor hinzugefügt werden</span><span class="sxs-lookup"><span data-stu-id="790e8-152">Devices must be added to the evaluation lab</span></span>
>- <span data-ttu-id="790e8-153">Bedrohungssimulatoren müssen im Evaluierungslabor installiert werden.</span><span class="sxs-lookup"><span data-stu-id="790e8-153">Threat simulators must be installed in the evaluation lab</span></span>

1. <span data-ttu-id="790e8-154">Wählen Sie im Portal **Simulation erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="790e8-154">From the portal select **Create simulation**.</span></span>

2. <span data-ttu-id="790e8-155">Wählen Sie einen Bedrohungssimulator aus.</span><span class="sxs-lookup"><span data-stu-id="790e8-155">Select a threat simulator.</span></span>

    ![Abbildung der Auswahl des Bedrohungssimulators](images/select-simulator.png)

3. <span data-ttu-id="790e8-157">Wählen Sie eine Simulation aus, oder sehen Sie sich den Simulationskatalog an, um die verfügbaren Simulationen zu durchsuchen.</span><span class="sxs-lookup"><span data-stu-id="790e8-157">Choose a simulation or look through the simulation gallery to browse through the available simulations.</span></span>

    <span data-ttu-id="790e8-158">Sie können den Simulationskatalog von:</span><span class="sxs-lookup"><span data-stu-id="790e8-158">You can get to the simulation gallery from:</span></span>
    - <span data-ttu-id="790e8-159">Das Hauptauswertungsdashboard in der Kachel **"Simulationsübersicht"** oder</span><span class="sxs-lookup"><span data-stu-id="790e8-159">The main evaluation dashboard in the **Simulations overview** tile or</span></span>
    - <span data-ttu-id="790e8-160">Wählen Sie dann im Navigationsbereich **"Evaluierung" und "Lernprogramme**  >  **Simulation & Lernprogramme"** den **Simulationskatalog** aus.</span><span class="sxs-lookup"><span data-stu-id="790e8-160">By navigating from the navigation pane **Evaluation and tutorials** > **Simulation & tutorials**, then select **Simulations catalog**.</span></span>

4. <span data-ttu-id="790e8-161">Wählen Sie die Geräte aus, auf denen Sie die Simulation ausführen möchten.</span><span class="sxs-lookup"><span data-stu-id="790e8-161">Select the devices where you'd like to run the simulation on.</span></span>

5. <span data-ttu-id="790e8-162">Wählen Sie **Simulation erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="790e8-162">Select **Create simulation**.</span></span>

6. <span data-ttu-id="790e8-163">Zeigen Sie den Fortschritt einer Simulation an, indem Sie die Registerkarte **Simulationen** auswählen. Zeigen Sie den Simulationsstatus, aktive Warnungen und andere Details an.</span><span class="sxs-lookup"><span data-stu-id="790e8-163">View the progress of a simulation by selecting the **Simulations** tab. View the simulation state, active alerts, and other details.</span></span>

    <span data-ttu-id="790e8-164">![Abbildung der Registerkarte "Simulationen"](images/simulations-tab.png)
</span><span class="sxs-lookup"><span data-stu-id="790e8-164">![Image of simulations tab](images/simulations-tab.png)
</span></span><br>

<span data-ttu-id="790e8-165">Nachdem Sie Ihre Simulationen ausgeführt haben, empfehlen wir Ihnen, die Testfortschrittsleiste zu durchlaufen und Microsoft Defender für Endpunkt zu erkunden, um **eine automatisierte Untersuchung und Behebung auszulösen.**</span><span class="sxs-lookup"><span data-stu-id="790e8-165">After running your simulations, we encourage you to walk through the lab progress bar and explore **Microsoft Defender for Endpoint triggered an automated investigation and remediation**.</span></span> <span data-ttu-id="790e8-166">Sehen Sie sich die von der Funktion gesammelten und analysierten Nachweise an.</span><span class="sxs-lookup"><span data-stu-id="790e8-166">Check out the evidence collected and analyzed by the feature.</span></span>

<span data-ttu-id="790e8-167">Suchen Sie nach Angriffsnachweisen durch die erweiterte Suche mithilfe der umfangreichen Abfragesprache und der unformatierten Telemetrie, und sehen Sie sich einige weltweite Bedrohungen an, die in der Bedrohungsanalyse dokumentiert sind.</span><span class="sxs-lookup"><span data-stu-id="790e8-167">Hunt for attack evidence through advanced hunting by using the rich query language and raw telemetry and check out some world-wide threats documented in Threat analytics.</span></span>
