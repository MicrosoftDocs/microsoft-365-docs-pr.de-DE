---
title: Erleben von Microsoft Defender ATP durch simulierte Angriffe
description: Führen Sie die bereitgestellten Simulationen des Angriffsszenarios aus, um zu erfahren, wie Microsoft Defender ATP Verstöße erkennen, untersuchen und darauf reagieren kann.
keywords: wdatp, test, scenario, attack, simulation, simulated, diy, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: b3fb862ac6e845ed4a3f5b72bae902f00c125b53
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498302"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="17c1e-104">Erleben von Microsoft Defender for Endpoint durch simulierte Angriffe</span><span class="sxs-lookup"><span data-stu-id="17c1e-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="17c1e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="17c1e-105">**Applies to:**</span></span>
- [<span data-ttu-id="17c1e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="17c1e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="17c1e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="17c1e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="17c1e-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="17c1e-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="17c1e-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="17c1e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="17c1e-110">Erfahren Sie mehr über die neuesten Verbesserungen in Microsoft Defender ATP: [Was ist neu in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="17c1e-110">Learn about the latest enhancements in Microsoft Defender ATP: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="17c1e-111">Defender for Endpoint hat in der kürzlichen MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen gezeigt.</span><span class="sxs-lookup"><span data-stu-id="17c1e-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="17c1e-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="17c1e-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="17c1e-113">Möglicherweise möchten Sie Defender for Endpoint nutzen, bevor Sie mehr als ein paar Geräte in den Dienst integrieren.</span><span class="sxs-lookup"><span data-stu-id="17c1e-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="17c1e-114">Dazu können Sie kontrollierte Angriffssimulationen auf einigen Testgeräten ausführen.</span><span class="sxs-lookup"><span data-stu-id="17c1e-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="17c1e-115">Nachdem Sie die simulierten Angriffe ausgeführt haben, können Sie überprüfen, wie Defender for Endpoint schädliche Aktivitäten aufgreift, und untersuchen, wie eine effiziente Reaktion ermöglicht wird.</span><span class="sxs-lookup"><span data-stu-id="17c1e-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="17c1e-116">Vorbereitung</span><span class="sxs-lookup"><span data-stu-id="17c1e-116">Before you begin</span></span>

<span data-ttu-id="17c1e-117">Zum Ausführen einer der bereitgestellten Simulationen benötigen Sie mindestens [ein integriertes Gerät.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="17c1e-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="17c1e-118">Lesen Sie das exemplarische Vorgehensweisendokument, das für jedes Angriffsszenario bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="17c1e-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="17c1e-119">Jedes Dokument enthält Betriebssystem- und Anwendungsanforderungen sowie detaillierte Anweisungen, die für ein Angriffsszenario spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="17c1e-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="17c1e-120">Ausführen einer Simulation</span><span class="sxs-lookup"><span data-stu-id="17c1e-120">Run a simulation</span></span>

1. <span data-ttu-id="17c1e-121">Wählen **Sie** in & Hilfesimulationen die verfügbaren  >  **Angriffsszenarien** aus, die Sie simulieren möchten:</span><span class="sxs-lookup"><span data-stu-id="17c1e-121">In **Help** > **Simulations & tutorials**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="17c1e-122">**Szenario 1: Dokument fällt hinter die Hintertür** – simuliert die Zustellung eines sozial entwickelten Lockure-Dokuments.</span><span class="sxs-lookup"><span data-stu-id="17c1e-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="17c1e-123">Das Dokument startet eine speziell entworfene Backdoor, die Angreifern die Kontrolle gibt.</span><span class="sxs-lookup"><span data-stu-id="17c1e-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="17c1e-124">**Szenario 2: PowerShell-Skript** bei dateilosem Angriff – simuliert einen dateilosen Angriff, der auf PowerShell basiert, und zeigt die Reduzierung der Angriffsfläche und die Erkennung bösartiger Speicheraktivitäten durch Gerätelernen an.</span><span class="sxs-lookup"><span data-stu-id="17c1e-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="17c1e-125">**Szenario 3: Automatisierte** Reaktion auf Sicherheitsvorfälle – löst eine automatisierte Untersuchung aus, die automatisch nach Verletzungsartefakten fahnen und diese behoben, um Ihre Kapazität für die Reaktion auf Vorfälle zu skalieren.</span><span class="sxs-lookup"><span data-stu-id="17c1e-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="17c1e-126">Laden Sie das entsprechende exemplarische Vorgehensweisendokument herunter, das im ausgewählten Szenario bereitgestellt wird, und lesen Sie es.</span><span class="sxs-lookup"><span data-stu-id="17c1e-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="17c1e-127">Laden Sie die Simulationsdatei herunter, oder kopieren Sie das Simulationsskript, indem Sie zu  >  **Hilfesimulationen & navigieren.**</span><span class="sxs-lookup"><span data-stu-id="17c1e-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="17c1e-128">Sie können die Datei oder das Skript auf dem Testgerät herunterladen, es ist jedoch nicht zwingend erforderlich.</span><span class="sxs-lookup"><span data-stu-id="17c1e-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="17c1e-129">Führen Sie die Simulationsdatei oder das Skript auf dem Testgerät wie im exemplarischen Vorgehensweisendokument angewiesen aus.</span><span class="sxs-lookup"><span data-stu-id="17c1e-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="17c1e-130">Simulationsdateien oder Skripts imitieren Angriffsaktivitäten, sind aber tatsächlich gutartig und schaden dem Testgerät nicht.</span><span class="sxs-lookup"><span data-stu-id="17c1e-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="17c1e-131">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="17c1e-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="17c1e-132">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="17c1e-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="17c1e-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="17c1e-133">Related topics</span></span>

- [<span data-ttu-id="17c1e-134">Onboarding von Geräten</span><span class="sxs-lookup"><span data-stu-id="17c1e-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="17c1e-135">Onboarding von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="17c1e-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
