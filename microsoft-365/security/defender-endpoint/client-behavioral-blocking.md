---
title: Client-Verhaltensblockierung
description: Das Blockieren von Clientverhalten ist Teil der Funktionen zum Blockieren und Eindämmen von Verhaltensweisen in Microsoft Defender für Endpunkt.
keywords: Verhaltensblockierung, schneller Schutz, Clientverhalten, Microsoft Defender für Endpunkt
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: fcf2310929937d1dacfc9c101d3e14414bad262b
ms.sourcegitcommit: 33d19853a38dfa4e6ed21b313976643670a14581
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52903744"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="64d9a-104">Client-Verhaltensblockierung</span><span class="sxs-lookup"><span data-stu-id="64d9a-104">Client behavioral blocking</span></span>

<span data-ttu-id="64d9a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="64d9a-105">**Applies to:**</span></span>
- [<span data-ttu-id="64d9a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="64d9a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64d9a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64d9a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="64d9a-108">Möchten Sie Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="64d9a-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="64d9a-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="64d9a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="64d9a-110">Übersicht</span><span class="sxs-lookup"><span data-stu-id="64d9a-110">Overview</span></span>

<span data-ttu-id="64d9a-111">Das Blockieren von Clientverhalten ist eine Komponente der Funktionen zum [Blockieren und Eindämmen](behavioral-blocking-containment.md) von Verhaltensweisen in Defender für Endpunkt.</span><span class="sxs-lookup"><span data-stu-id="64d9a-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](behavioral-blocking-containment.md) in Defender for Endpoint.</span></span> <span data-ttu-id="64d9a-112">Da verdächtige Verhaltensweisen auf Geräten erkannt werden (auch als Clients oder Endpunkte bezeichnet), werden Artefakte (z. B. Dateien oder Anwendungen) automatisch blockiert, überprüft und behoben.</span><span class="sxs-lookup"><span data-stu-id="64d9a-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Cloud- und Clientschutz":::

<span data-ttu-id="64d9a-114">Antivirusschutz funktioniert am besten, wenn er mit Cloudschutz kombiniert wird.</span><span class="sxs-lookup"><span data-stu-id="64d9a-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="64d9a-115">Funktionsweise der Blockierung von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="64d9a-115">How client behavioral blocking works</span></span>

<span data-ttu-id="64d9a-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) können verdächtiges Verhalten, bösartigen Code, Datei- und Speicherangriffe und vieles mehr auf einem Gerät erkennen.</span><span class="sxs-lookup"><span data-stu-id="64d9a-116">[Microsoft Defender Antivirus](microsoft-defender-antivirus-in-windows-10.md) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="64d9a-117">Wenn verdächtige Verhaltensweisen erkannt werden, überwacht und sendet Microsoft Defender Antivirus diese verdächtigen Verhaltensweisen und deren Prozessstrukturen an den Cloudschutzdienst.</span><span class="sxs-lookup"><span data-stu-id="64d9a-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="64d9a-118">Machine Learning unterscheidet zwischen schädlichen Anwendungen und gutem Verhalten innerhalb von Millisekunden und klassifiziert jedes Artefakt.</span><span class="sxs-lookup"><span data-stu-id="64d9a-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="64d9a-119">Sobald ein Artefakt als bösartig eingestuft wird, wird es nahezu in Echtzeit auf dem Gerät blockiert.</span><span class="sxs-lookup"><span data-stu-id="64d9a-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="64d9a-120">Wenn ein verdächtiges Verhalten erkannt wird, wird eine [Warnung](alerts-queue.md) generiert und ist in [Microsoft 365 Defender](microsoft-defender-security-center.md) (vormals Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) )) sichtbar.</span><span class="sxs-lookup"><span data-stu-id="64d9a-120">Whenever a suspicious behavior is detected, an [alert](alerts-queue.md) is generated, and is visible in [Microsoft 365 Defender](microsoft-defender-security-center.md) (formerly the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com))).</span></span>

<span data-ttu-id="64d9a-121">Das Blockieren von Clientverhalten ist effektiv, da es nicht nur dazu beiträgt, den Start eines Angriffs zu verhindern, es kann auch dazu beitragen, einen Angriff zu stoppen, der mit der Ausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="64d9a-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="64d9a-122">Und mit der Blockierung von [Feedbackschleifen](feedback-loop-blocking.md) (eine weitere Möglichkeit zum Blockieren und Eindämmen von Verhaltensweisen) werden Angriffe auf anderen Geräten in Ihrer Organisation verhindert.</span><span class="sxs-lookup"><span data-stu-id="64d9a-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="64d9a-123">Verhaltensbasierte Erkennungen</span><span class="sxs-lookup"><span data-stu-id="64d9a-123">Behavior-based detections</span></span>

<span data-ttu-id="64d9a-124">Verhaltensbasierte Erkennungen werden gemäß der [MITRE ATT-&CK-Matrix für Enterprise](https://attack.mitre.org/matrices/enterprise)benannt.</span><span class="sxs-lookup"><span data-stu-id="64d9a-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="64d9a-125">Die Benennungskonvention hilft bei der Identifizierung der Angriffsphase, in der das böswillige Verhalten beobachtet wurde:</span><span class="sxs-lookup"><span data-stu-id="64d9a-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="64d9a-126">Taktik</span><span class="sxs-lookup"><span data-stu-id="64d9a-126">Tactic</span></span> |   <span data-ttu-id="64d9a-127">Name der Erkennungsgefahr</span><span class="sxs-lookup"><span data-stu-id="64d9a-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="64d9a-128">Anfänglicher Zugriff</span><span class="sxs-lookup"><span data-stu-id="64d9a-128">Initial Access</span></span> | `Behavior:Win32/InitialAccess.*!ml` |
|<span data-ttu-id="64d9a-129">Ausführung</span><span class="sxs-lookup"><span data-stu-id="64d9a-129">Execution</span></span>  | `Behavior:Win32/Execution.*!ml` |
|<span data-ttu-id="64d9a-130">Persistenz</span><span class="sxs-lookup"><span data-stu-id="64d9a-130">Persistence</span></span>    | `Behavior:Win32/Persistence.*!ml` |
|<span data-ttu-id="64d9a-131">Berechtigungseskalation</span><span class="sxs-lookup"><span data-stu-id="64d9a-131">Privilege Escalation</span></span>   | `Behavior:Win32/PrivilegeEscalation.*!ml` |
|<span data-ttu-id="64d9a-132">DefenseSynekte</span><span class="sxs-lookup"><span data-stu-id="64d9a-132">Defense Evasion</span></span>    | `Behavior:Win32/DefenseEvasion.*!ml` |
|<span data-ttu-id="64d9a-133">Zugriff auf Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="64d9a-133">Credential Access</span></span>  | `Behavior:Win32/CredentialAccess.*!ml` |
|<span data-ttu-id="64d9a-134">Suche</span><span class="sxs-lookup"><span data-stu-id="64d9a-134">Discovery</span></span>  | `Behavior:Win32/Discovery.*!ml` |
|<span data-ttu-id="64d9a-135">Lateralverschiebung</span><span class="sxs-lookup"><span data-stu-id="64d9a-135">Lateral Movement</span></span> | `Behavior:Win32/LateralMovement.*!ml` |
|<span data-ttu-id="64d9a-136">Auflistung</span><span class="sxs-lookup"><span data-stu-id="64d9a-136">Collection</span></span> |   `Behavior:Win32/Collection.*!ml` |
|<span data-ttu-id="64d9a-137">Befehl und Steuerelement</span><span class="sxs-lookup"><span data-stu-id="64d9a-137">Command and Control</span></span> | `Behavior:Win32/CommandAndControl.*!ml` |
|<span data-ttu-id="64d9a-138">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="64d9a-138">Exfiltration</span></span>   | `Behavior:Win32/Exfiltration.*!ml` |
|<span data-ttu-id="64d9a-139">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="64d9a-139">Impact</span></span> | `Behavior:Win32/Impact.*!ml` |
|<span data-ttu-id="64d9a-140">Uncategorized</span><span class="sxs-lookup"><span data-stu-id="64d9a-140">Uncategorized</span></span>  | `Behavior:Win32/Generic.*!ml` |

> [!TIP]
> <span data-ttu-id="64d9a-141">Weitere Informationen zu bestimmten Bedrohungen finden Sie unter **[den aktuellen globalen Bedrohungsaktivitäten.](https://www.microsoft.com/wdsi/threats)**</span><span class="sxs-lookup"><span data-stu-id="64d9a-141">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="64d9a-142">Konfigurieren der Blockierung von Clientverhalten</span><span class="sxs-lookup"><span data-stu-id="64d9a-142">Configuring client behavioral blocking</span></span>

<span data-ttu-id="64d9a-143">Wenn Ihre Organisation Defender für Endpunkt verwendet, ist die Blockierung von Clientverhalten standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="64d9a-143">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="64d9a-144">Um jedoch von allen Defender für Endpunkt-Funktionen zu profitieren, einschließlich [verhaltensbasierter Blockierung und Eindämmung,](behavioral-blocking-containment.md)stellen Sie sicher, dass die folgenden Features und Funktionen von Defender für Endpunkt aktiviert und konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="64d9a-144">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="64d9a-145">Baselines für Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="64d9a-145">Defender for Endpoint baselines</span></span>](configure-machines-security-baseline.md)

- [<span data-ttu-id="64d9a-146">Geräte, die in Defender für Endpunkt integriert sind</span><span class="sxs-lookup"><span data-stu-id="64d9a-146">Devices onboarded to Defender for Endpoint</span></span>](onboard-configure.md)

- [<span data-ttu-id="64d9a-147">EDR im Blockmodus</span><span class="sxs-lookup"><span data-stu-id="64d9a-147">EDR in block mode</span></span>](edr-in-block-mode.md)

- <span data-ttu-id="64d9a-148">[Verringerung der Angriffsfläche](attack-surface-reduction.md):</span><span class="sxs-lookup"><span data-stu-id="64d9a-148">[Attack surface reduction](attack-surface-reduction.md)</span></span>

- <span data-ttu-id="64d9a-149">[Schutz](configure-microsoft-defender-antivirus-features.md) der nächsten Generation (Antivirus, Antischadsoftware und andere Bedrohungsschutzfunktionen)</span><span class="sxs-lookup"><span data-stu-id="64d9a-149">[Next-generation protection](configure-microsoft-defender-antivirus-features.md) (antivirus, antimalware, and other threat protection capabilities)</span></span>

