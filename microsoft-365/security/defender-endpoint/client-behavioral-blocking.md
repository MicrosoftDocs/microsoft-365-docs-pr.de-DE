---
title: Clientverhaltensblockierung
description: Das Blockieren von Clientverhalten ist Teil der Funktionen zum Blockieren und Eindähen von Verhaltensweisen in Microsoft Defender ATP
keywords: Verhaltensblockierung, schneller Schutz, Clientverhalten, Microsoft Defender ATP
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
ms.openlocfilehash: c37a1180f9def51daa4229418b05abe7cf787aa3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165261"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="0b33b-104">Clientverhaltensblockierung</span><span class="sxs-lookup"><span data-stu-id="0b33b-104">Client behavioral blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="0b33b-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0b33b-105">**Applies to:**</span></span>
- [<span data-ttu-id="0b33b-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0b33b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="0b33b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0b33b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="0b33b-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="0b33b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="0b33b-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="0b33b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="0b33b-110">Übersicht</span><span class="sxs-lookup"><span data-stu-id="0b33b-110">Overview</span></span>

<span data-ttu-id="0b33b-111">Die Clientverhaltensblockierung ist eine Komponente von Funktionen zum [Blockieren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) und Eindämmung von Verhaltensweisen in Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="0b33b-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span></span> <span data-ttu-id="0b33b-112">Da verdächtige Verhaltensweisen auf Geräten (auch als Clients oder Endpunkte bezeichnet) erkannt werden, werden Artefakte (z. B. Dateien oder Anwendungen) automatisch blockiert, überprüft und behoben.</span><span class="sxs-lookup"><span data-stu-id="0b33b-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Cloud- und Clientschutz":::

<span data-ttu-id="0b33b-114">Antivirusschutz funktioniert am besten, wenn er mit Cloudschutz gekoppelt ist.</span><span class="sxs-lookup"><span data-stu-id="0b33b-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="0b33b-115">Funktionsweise der Clientverhaltensblockierung</span><span class="sxs-lookup"><span data-stu-id="0b33b-115">How client behavioral blocking works</span></span>

<span data-ttu-id="0b33b-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) kann verdächtiges Verhalten, bösartigen Code, Datei- und Speicherangriffe und vieles mehr auf einem Gerät erkennen.</span><span class="sxs-lookup"><span data-stu-id="0b33b-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="0b33b-117">Wenn verdächtige Verhaltensweisen erkannt werden, überwacht und sendet Microsoft Defender Antivirus diese verdächtigen Verhaltensweisen und ihre Prozessstrukturen an den Cloudschutzdienst.</span><span class="sxs-lookup"><span data-stu-id="0b33b-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="0b33b-118">Maschinelles Lernen unterscheidet zwischen schädlichen Anwendungen und gutem Verhalten innerhalb von Millisekunden und klassiert jedes Artefakt.</span><span class="sxs-lookup"><span data-stu-id="0b33b-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="0b33b-119">Sobald sich ein Artefakt als schädlich herausgefunden hat, wird es in fast Echtzeit auf dem Gerät blockiert.</span><span class="sxs-lookup"><span data-stu-id="0b33b-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="0b33b-120">Wenn ein verdächtiges Verhalten erkannt wird, wird [eine](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) Warnung generiert und ist im Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) sichtbar.</span><span class="sxs-lookup"><span data-stu-id="0b33b-120">Whenever a suspicious behavior is detected, an [alert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="0b33b-121">Die Clientverhaltensblockierung ist effektiv, da sie nicht nur den Start eines Angriffs verhindert, sondern auch dazu beitragen kann, einen Angriff zu beenden, der mit der Ausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="0b33b-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="0b33b-122">Und mit der [Blockierung von Feedbackschleifen](feedback-loop-blocking.md) (eine weitere Funktion der Verhaltensblockierung und -eindämmung) werden Angriffe auf andere Geräte in Ihrer Organisation verhindert.</span><span class="sxs-lookup"><span data-stu-id="0b33b-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="0b33b-123">Verhaltensbasierte Erkennungen</span><span class="sxs-lookup"><span data-stu-id="0b33b-123">Behavior-based detections</span></span>

<span data-ttu-id="0b33b-124">Verhaltensbasierte Erkennungen werden gemäß der [MITRE ATT-&CK Matrix for Enterprise benannt.](https://attack.mitre.org/matrices/enterprise)</span><span class="sxs-lookup"><span data-stu-id="0b33b-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="0b33b-125">Die Benennungskonvention hilft dabei, die Angriffsphase zu identifizieren, in der das schädliche Verhalten beobachtet wurde:</span><span class="sxs-lookup"><span data-stu-id="0b33b-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="0b33b-126">Taktik</span><span class="sxs-lookup"><span data-stu-id="0b33b-126">Tactic</span></span> |   <span data-ttu-id="0b33b-127">Name der Erkennungsbedrohung</span><span class="sxs-lookup"><span data-stu-id="0b33b-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="0b33b-128">Anfänglicher Zugriff</span><span class="sxs-lookup"><span data-stu-id="0b33b-128">Initial Access</span></span> | <span data-ttu-id="0b33b-129">Verhalten:Win32/InitialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-129">Behavior:Win32/InitialAccess.\*!ml</span></span> |
|<span data-ttu-id="0b33b-130">Ausführung</span><span class="sxs-lookup"><span data-stu-id="0b33b-130">Execution</span></span>  | <span data-ttu-id="0b33b-131">Behavior:Win32/Execution.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-131">Behavior:Win32/Execution.\*!ml</span></span> |
|<span data-ttu-id="0b33b-132">Persistenz</span><span class="sxs-lookup"><span data-stu-id="0b33b-132">Persistence</span></span>    | <span data-ttu-id="0b33b-133">Behavior:Win32/Persistence.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-133">Behavior:Win32/Persistence.\*!ml</span></span> |
|<span data-ttu-id="0b33b-134">Berechtigungseskalation</span><span class="sxs-lookup"><span data-stu-id="0b33b-134">Privilege Escalation</span></span>   | <span data-ttu-id="0b33b-135">Verhalten:Win32/PrivilegeEscalation.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span></span> |
|<span data-ttu-id="0b33b-136">Schutzhinterziehung</span><span class="sxs-lookup"><span data-stu-id="0b33b-136">Defense Evasion</span></span>    | <span data-ttu-id="0b33b-137">Behavior:Win32/DefenseEvasion.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-137">Behavior:Win32/DefenseEvasion.\*!ml</span></span> |
|<span data-ttu-id="0b33b-138">Zugriff auf Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="0b33b-138">Credential Access</span></span>  | <span data-ttu-id="0b33b-139">Verhalten:Win32/CredentialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-139">Behavior:Win32/CredentialAccess.\*!ml</span></span> |
|<span data-ttu-id="0b33b-140">Suche</span><span class="sxs-lookup"><span data-stu-id="0b33b-140">Discovery</span></span>  | <span data-ttu-id="0b33b-141">Behavior:Win32/Discovery.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-141">Behavior:Win32/Discovery.\*!ml</span></span> |
|<span data-ttu-id="0b33b-142">Laterale Bewegung</span><span class="sxs-lookup"><span data-stu-id="0b33b-142">Lateral Movement</span></span> | <span data-ttu-id="0b33b-143">Verhalten:Win32/LateralMovement.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-143">Behavior:Win32/LateralMovement.\*!ml</span></span> |
|<span data-ttu-id="0b33b-144">Auflistung</span><span class="sxs-lookup"><span data-stu-id="0b33b-144">Collection</span></span> |   <span data-ttu-id="0b33b-145">Behavior:Win32/Collection.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-145">Behavior:Win32/Collection.\*!ml</span></span> |
|<span data-ttu-id="0b33b-146">Befehl und Steuerelement</span><span class="sxs-lookup"><span data-stu-id="0b33b-146">Command and Control</span></span> | <span data-ttu-id="0b33b-147">Verhalten:Win32/CommandAndControl.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-147">Behavior:Win32/CommandAndControl.\*!ml</span></span> |
|<span data-ttu-id="0b33b-148">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="0b33b-148">Exfiltration</span></span>   | <span data-ttu-id="0b33b-149">Verhalten:Win32/Exfiltration.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-149">Behavior:Win32/Exfiltration.\*!ml</span></span> |
|<span data-ttu-id="0b33b-150">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="0b33b-150">Impact</span></span> | <span data-ttu-id="0b33b-151">Behavior:Win32/Impact.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-151">Behavior:Win32/Impact.\*!ml</span></span> |
|<span data-ttu-id="0b33b-152">Nicht kategorisiert</span><span class="sxs-lookup"><span data-stu-id="0b33b-152">Uncategorized</span></span>  | <span data-ttu-id="0b33b-153">Verhalten:Win32/Generic.\*!ml</span><span class="sxs-lookup"><span data-stu-id="0b33b-153">Behavior:Win32/Generic.\*!ml</span></span> |

> [!TIP]
> <span data-ttu-id="0b33b-154">Weitere Informationen zu bestimmten Bedrohungen finden Sie unter **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span><span class="sxs-lookup"><span data-stu-id="0b33b-154">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="0b33b-155">Konfigurieren von Clientverhaltensblockierung</span><span class="sxs-lookup"><span data-stu-id="0b33b-155">Configuring client behavioral blocking</span></span>

<span data-ttu-id="0b33b-156">Wenn Ihre Organisation Defender for Endpoint verwendet, ist die Clientverhaltensblockierung standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="0b33b-156">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="0b33b-157">Um jedoch von allen Defender for [](behavioral-blocking-containment.md)Endpoint-Funktionen zu profitieren, einschließlich der Verhaltensblockierung und -eindämmung, stellen Sie sicher, dass die folgenden Features und Funktionen von Defender for Endpoint aktiviert und konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="0b33b-157">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="0b33b-158">Defender for Endpoint-Baselines</span><span class="sxs-lookup"><span data-stu-id="0b33b-158">Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="0b33b-159">In Defender for Endpoint integrierte Geräte</span><span class="sxs-lookup"><span data-stu-id="0b33b-159">Devices onboarded to Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="0b33b-160">EDR im Blockmodus</span><span class="sxs-lookup"><span data-stu-id="0b33b-160">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [<span data-ttu-id="0b33b-161">Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="0b33b-161">Attack surface reduction</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- <span data-ttu-id="0b33b-162">[Schutz der nächsten Generation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (Antivirus)</span><span class="sxs-lookup"><span data-stu-id="0b33b-162">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="0b33b-163">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="0b33b-163">Related articles</span></span>

- [<span data-ttu-id="0b33b-164">Verhaltensblockierung und -eindämmung</span><span class="sxs-lookup"><span data-stu-id="0b33b-164">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="0b33b-165">Blockieren von Feedbackschleifen</span><span class="sxs-lookup"><span data-stu-id="0b33b-165">Feedback-loop blocking</span></span>](feedback-loop-blocking.md)

- [<span data-ttu-id="0b33b-166">(Blog) Verhaltensblockierung und -eindämmung: Transformieren von Optik in Schutz</span><span class="sxs-lookup"><span data-stu-id="0b33b-166">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="0b33b-167">Hilfreiche Defender for Endpoint-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="0b33b-167">Helpful Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
