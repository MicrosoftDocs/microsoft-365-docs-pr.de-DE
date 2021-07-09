---
title: Microsoft Defender für Endpunkt durch simulierte Angriffe erleben
description: Führen Sie die bereitgestellten Angriffsszenariosimulationen aus, um zu erfahren, wie Microsoft Defender für Endpunkt Verstöße erkennen, untersuchen und darauf reagieren kann.
keywords: Test, Szenario, Angriff, Simulation, simuliert, Auslauf, Microsoft Defender für Endpunkt
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
ms.openlocfilehash: 9a56167f0025ec42f4fd441886f83026c1bf23d6
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339538"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a><span data-ttu-id="0e54d-104">Microsoft Defender für Endpunkt durch simulierte Angriffe erleben</span><span class="sxs-lookup"><span data-stu-id="0e54d-104">Experience Microsoft Defender for Endpoint through simulated attacks</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0e54d-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0e54d-105">**Applies to:**</span></span>
- [<span data-ttu-id="0e54d-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0e54d-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="0e54d-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0e54d-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="0e54d-108">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="0e54d-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0e54d-109">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="0e54d-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- <span data-ttu-id="0e54d-110">Erfahren Sie mehr über die neuesten Verbesserungen in Microsoft Defender für Endpunkt: [Was ist neu in Defender für Endpunkt?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span><span class="sxs-lookup"><span data-stu-id="0e54d-110">Learn about the latest enhancements in Microsoft Defender for Endpoint: [What's new in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).</span></span>
>- <span data-ttu-id="0e54d-111">Defender für Endpunkt hat in der letzten MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen demonstriert.</span><span class="sxs-lookup"><span data-stu-id="0e54d-111">Defender for Endpoint demonstrated industry-leading optics and detection capabilities in the recent MITRE evaluation.</span></span> <span data-ttu-id="0e54d-112">Lesen Sie: [Insights aus der MITRE ATT&CK-basierten Auswertung.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)</span><span class="sxs-lookup"><span data-stu-id="0e54d-112">Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).</span></span>

<span data-ttu-id="0e54d-113">Möglicherweise möchten Sie Defender für Endpunkt testen, bevor Sie mehr als ein paar Geräte in den Dienst integrieren.</span><span class="sxs-lookup"><span data-stu-id="0e54d-113">You might want to experience Defender for Endpoint before you onboard more than a few devices to the service.</span></span> <span data-ttu-id="0e54d-114">Dazu können Sie kontrollierte Angriffssimulationen auf einigen Testgeräten ausführen.</span><span class="sxs-lookup"><span data-stu-id="0e54d-114">To do this, you can run controlled attack simulations on a few test devices.</span></span> <span data-ttu-id="0e54d-115">Nachdem Sie die simulierten Angriffe ausgeführt haben, können Sie überprüfen, wie Defender für Endpunkt bösartige Aktivitäten aufdecken und untersuchen, wie es eine effiziente Reaktion ermöglicht.</span><span class="sxs-lookup"><span data-stu-id="0e54d-115">After running the simulated attacks, you can review how Defender for Endpoint surfaces malicious activity and explore how it enables an efficient response.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="0e54d-116">Bevor Sie beginnen</span><span class="sxs-lookup"><span data-stu-id="0e54d-116">Before you begin</span></span>

<span data-ttu-id="0e54d-117">Zum Ausführen einer der bereitgestellten Simulationen benötigen Sie mindestens [ein integriertes Gerät.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="0e54d-117">To run any of the provided simulations, you need at least [one onboarded device](onboard-configure.md).</span></span> 

<span data-ttu-id="0e54d-118">Lesen Sie das exemplarische Vorgehensweisendokument, das für jedes Angriffsszenario bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="0e54d-118">Read the walkthrough document provided with each attack scenario.</span></span> <span data-ttu-id="0e54d-119">Jedes Dokument enthält Betriebssystem- und Anwendungsanforderungen sowie detaillierte Anweisungen, die für ein Angriffsszenario spezifisch sind.</span><span class="sxs-lookup"><span data-stu-id="0e54d-119">Each document includes OS and application requirements as well as detailed instructions that are specific to an attack scenario.</span></span>

## <a name="run-a-simulation"></a><span data-ttu-id="0e54d-120">Ausführen einer Simulation</span><span class="sxs-lookup"><span data-stu-id="0e54d-120">Run a simulation</span></span>

1. <span data-ttu-id="0e54d-121">Wählen Sie in Lernprogrammen zur  >  **Endpunktauswertung &**  >  **Lernprogrammen & Simulationen** aus, welche der verfügbaren Angriffsszenarien Sie simulieren möchten:</span><span class="sxs-lookup"><span data-stu-id="0e54d-121">In **Endpoints** > **Evaluation & tutorials** > **Tutorials & simulations**, select which of the available attack scenarios you would like to simulate:</span></span>

   - <span data-ttu-id="0e54d-122">**Szenario 1: Dokument fällt Hintertür ab** – simuliert die Bereitstellung eines Social Engineering-Lockdokuments.</span><span class="sxs-lookup"><span data-stu-id="0e54d-122">**Scenario 1: Document drops backdoor** - simulates delivery of a socially engineered lure document.</span></span> <span data-ttu-id="0e54d-123">Das Dokument startet eine speziell gestaltete Hintertür, die Angreifern die Kontrolle gibt.</span><span class="sxs-lookup"><span data-stu-id="0e54d-123">The document launches a specially crafted backdoor that gives attackers control.</span></span>

   - <span data-ttu-id="0e54d-124">**Szenario 2: PowerShell-Skript bei dateilosen Angriffen** – simuliert einen dateilosen Angriff, der auf PowerShell basiert, die Reduzierung der Angriffsfläche und die Erkennung bösartiger Speicheraktivitäten durch Geräte.</span><span class="sxs-lookup"><span data-stu-id="0e54d-124">**Scenario 2: PowerShell script in fileless attack** - simulates a fileless attack that relies on PowerShell, showcasing attack surface reduction and device learning detection of malicious memory activity.</span></span>
    
   - <span data-ttu-id="0e54d-125">**Szenario 3: Automatisierte Reaktion auf Sicherheitsvorfälle** – löst eine automatisierte Untersuchung aus, die automatisch Nach- und Korrektur von Verletzungsartefakten auslöst, um Ihre Reaktionsfähigkeit auf Vorfälle zu skalieren.</span><span class="sxs-lookup"><span data-stu-id="0e54d-125">**Scenario 3: Automated incident response** - triggers automated investigation, which automatically hunts for and remediates breach artifacts to scale your incident response capacity.</span></span>

2. <span data-ttu-id="0e54d-126">Laden Sie das entsprechende Exemplarische Vorgehensweise-Dokument herunter, und lesen Sie es, das sie in Ihrem ausgewählten Szenario bereitgestellt haben.</span><span class="sxs-lookup"><span data-stu-id="0e54d-126">Download and read the corresponding walkthrough document provided with your selected scenario.</span></span>

3. <span data-ttu-id="0e54d-127">Laden Sie die Simulationsdatei herunter, oder kopieren Sie das Simulationsskript, indem **Sie** zu  >  **Hilfesimulationen & Lernprogrammen** navigieren.</span><span class="sxs-lookup"><span data-stu-id="0e54d-127">Download the simulation file or copy the simulation script by navigating to **Help** > **Simulations & tutorials**.</span></span> <span data-ttu-id="0e54d-128">Sie können die Datei oder das Skript auf dem Testgerät herunterladen, dies ist jedoch nicht obligatorisch.</span><span class="sxs-lookup"><span data-stu-id="0e54d-128">You can choose to download the file or script on the test device but it's not mandatory.</span></span>

4. <span data-ttu-id="0e54d-129">Führen Sie die Simulationsdatei oder das Skript auf dem Testgerät aus, wie im Dokument mit exemplarischer Vorgehensweise beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0e54d-129">Run the simulation file or script on the test device as instructed in the walkthrough document.</span></span>

> [!NOTE]
> <span data-ttu-id="0e54d-130">Simulationsdateien oder Skripts imitieren Angriffsaktivitäten, sind aber eigentlich gutartig und schaden dem Testgerät nicht.</span><span class="sxs-lookup"><span data-stu-id="0e54d-130">Simulation files or scripts mimic attack activity but are actually benign and will not harm or compromise the test device.</span></span>
> 
> 
> <span data-ttu-id="0e54d-131">Möchten Sie Defender für Endpunkt erfahren?</span><span class="sxs-lookup"><span data-stu-id="0e54d-131">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0e54d-132">Registrieren Sie sich für eine kostenlose Testversion</span><span class="sxs-lookup"><span data-stu-id="0e54d-132">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a><span data-ttu-id="0e54d-133">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="0e54d-133">Related topics</span></span>

- [<span data-ttu-id="0e54d-134">Onboarding von Geräten</span><span class="sxs-lookup"><span data-stu-id="0e54d-134">Onboard devices</span></span>](onboard-configure.md)
- [<span data-ttu-id="0e54d-135">Onboarding von Windows 10-Geräten</span><span class="sxs-lookup"><span data-stu-id="0e54d-135">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
