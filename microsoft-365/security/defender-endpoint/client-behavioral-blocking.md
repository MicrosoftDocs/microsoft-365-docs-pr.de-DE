---
title: Client-Verhaltensblockierung
description: Das Blockieren von Clientverhalten ist Teil der Funktionen zum Blockieren und Eindähen von Verhaltensweisen in Microsoft Defender for Endpoint
keywords: Verhaltensblockierung, schneller Schutz, Clientverhalten, Microsoft Defender for Endpoint
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
ms.openlocfilehash: c58c81cd4623ec03850c167cad285e052413174c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933421"
---
# <a name="client-behavioral-blocking"></a><span data-ttu-id="530b1-104">Client-Verhaltensblockierung</span><span class="sxs-lookup"><span data-stu-id="530b1-104">Client behavioral blocking</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="530b1-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="530b1-105">**Applies to:**</span></span>
- [<span data-ttu-id="530b1-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="530b1-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="530b1-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="530b1-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="530b1-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="530b1-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="530b1-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="530b1-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a><span data-ttu-id="530b1-110">Übersicht</span><span class="sxs-lookup"><span data-stu-id="530b1-110">Overview</span></span>

<span data-ttu-id="530b1-111">Die Clientverhaltensblockierung ist eine Komponente von Funktionen zum [Blockieren](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) und Eindämmung von Verhaltensweisen in Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="530b1-111">Client behavioral blocking is a component of [behavioral blocking and containment capabilities](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) in Defender for Endpoint.</span></span> <span data-ttu-id="530b1-112">Da verdächtige Verhaltensweisen auf Geräten (auch als Clients oder Endpunkte bezeichnet) erkannt werden, werden Artefakte (z. B. Dateien oder Anwendungen) automatisch blockiert, überprüft und behoben.</span><span class="sxs-lookup"><span data-stu-id="530b1-112">As suspicious behaviors are detected on devices (also referred to as clients or endpoints), artifacts (such as files or applications) are blocked, checked, and remediated automatically.</span></span> 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="Cloud- und Clientschutz":::

<span data-ttu-id="530b1-114">Antivirusschutz funktioniert am besten, wenn er mit Cloudschutz gekoppelt ist.</span><span class="sxs-lookup"><span data-stu-id="530b1-114">Antivirus protection works best when paired with cloud protection.</span></span>

## <a name="how-client-behavioral-blocking-works"></a><span data-ttu-id="530b1-115">Funktionsweise der Clientverhaltensblockierung</span><span class="sxs-lookup"><span data-stu-id="530b1-115">How client behavioral blocking works</span></span>

<span data-ttu-id="530b1-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) können verdächtiges Verhalten, bösartigen Code, Datei- und Speicherangriffe und vieles mehr auf einem Gerät erkennen.</span><span class="sxs-lookup"><span data-stu-id="530b1-116">[Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) can detect suspicious behavior, malicious code, fileless and in-memory attacks, and more on a device.</span></span> <span data-ttu-id="530b1-117">Wenn verdächtige Verhaltensweisen erkannt werden, Microsoft Defender Antivirus überwacht und sendet diese verdächtigen Verhaltensweisen und deren Prozessstrukturen an den Cloudschutzdienst.</span><span class="sxs-lookup"><span data-stu-id="530b1-117">When suspicious behaviors are detected, Microsoft Defender Antivirus monitors and sends those suspicious behaviors and their process trees to the cloud protection service.</span></span> <span data-ttu-id="530b1-118">Maschinelles Lernen unterscheidet zwischen schädlichen Anwendungen und gutem Verhalten innerhalb von Millisekunden und klassiert jedes Artefakt.</span><span class="sxs-lookup"><span data-stu-id="530b1-118">Machine learning differentiates between malicious applications and good behaviors within milliseconds, and classifies each artifact.</span></span> <span data-ttu-id="530b1-119">Sobald sich ein Artefakt als schädlich herausgefunden hat, wird es in fast Echtzeit auf dem Gerät blockiert.</span><span class="sxs-lookup"><span data-stu-id="530b1-119">In almost real time, as soon as an artifact is found to be malicious, it's blocked on the device.</span></span> 

<span data-ttu-id="530b1-120">Wenn ein verdächtiges Verhalten erkannt wird, wird [eine](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) Warnung generiert und im Microsoft Defender Security Center ( [https://securitycenter.windows.com](https://securitycenter.windows.com) ) angezeigt.</span><span class="sxs-lookup"><span data-stu-id="530b1-120">Whenever a suspicious behavior is detected, an [alert](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue) is generated, and is visible in the Microsoft Defender Security Center ([https://securitycenter.windows.com](https://securitycenter.windows.com)).</span></span>

<span data-ttu-id="530b1-121">Die Clientverhaltensblockierung ist effektiv, da sie nicht nur den Start eines Angriffs verhindert, sondern auch dazu beitragen kann, einen Angriff zu beenden, der mit der Ausführung begonnen hat.</span><span class="sxs-lookup"><span data-stu-id="530b1-121">Client behavioral blocking is effective because it not only helps prevent an attack from starting, it can help stop an attack that has begun executing.</span></span> <span data-ttu-id="530b1-122">Und mit der [Blockierung von Feedbackschleifen](feedback-loop-blocking.md) (eine weitere Funktion der Verhaltensblockierung und -eindämmung) werden Angriffe auf andere Geräte in Ihrer Organisation verhindert.</span><span class="sxs-lookup"><span data-stu-id="530b1-122">And, with [feedback-loop blocking](feedback-loop-blocking.md) (another capability of behavioral blocking and containment), attacks are prevented on other devices in your organization.</span></span>

## <a name="behavior-based-detections"></a><span data-ttu-id="530b1-123">Verhaltensbasierte Erkennungen</span><span class="sxs-lookup"><span data-stu-id="530b1-123">Behavior-based detections</span></span>

<span data-ttu-id="530b1-124">Verhaltensbasierte Erkennungen werden gemäß der [MITRE ATT-&CK-Matrix für Enterprise.](https://attack.mitre.org/matrices/enterprise)</span><span class="sxs-lookup"><span data-stu-id="530b1-124">Behavior-based detections are named according to the [MITRE ATT&CK Matrix for Enterprise](https://attack.mitre.org/matrices/enterprise).</span></span> <span data-ttu-id="530b1-125">Die Benennungskonvention hilft dabei, die Angriffsphase zu identifizieren, in der das schädliche Verhalten beobachtet wurde:</span><span class="sxs-lookup"><span data-stu-id="530b1-125">The naming convention helps identify the attack stage where the malicious behavior was observed:</span></span>


|<span data-ttu-id="530b1-126">Taktik</span><span class="sxs-lookup"><span data-stu-id="530b1-126">Tactic</span></span> |   <span data-ttu-id="530b1-127">Name der Erkennungsbedrohung</span><span class="sxs-lookup"><span data-stu-id="530b1-127">Detection threat name</span></span> |
|----|----|
|<span data-ttu-id="530b1-128">Anfänglicher Zugriff</span><span class="sxs-lookup"><span data-stu-id="530b1-128">Initial Access</span></span> | <span data-ttu-id="530b1-129">Verhalten:Win32/InitialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-129">Behavior:Win32/InitialAccess.\*!ml</span></span> |
|<span data-ttu-id="530b1-130">Ausführung</span><span class="sxs-lookup"><span data-stu-id="530b1-130">Execution</span></span>  | <span data-ttu-id="530b1-131">Behavior:Win32/Execution.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-131">Behavior:Win32/Execution.\*!ml</span></span> |
|<span data-ttu-id="530b1-132">Persistenz</span><span class="sxs-lookup"><span data-stu-id="530b1-132">Persistence</span></span>    | <span data-ttu-id="530b1-133">Behavior:Win32/Persistence.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-133">Behavior:Win32/Persistence.\*!ml</span></span> |
|<span data-ttu-id="530b1-134">Berechtigungseskalation</span><span class="sxs-lookup"><span data-stu-id="530b1-134">Privilege Escalation</span></span>   | <span data-ttu-id="530b1-135">Verhalten:Win32/PrivilegeEscalation.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-135">Behavior:Win32/PrivilegeEscalation.\*!ml</span></span> |
|<span data-ttu-id="530b1-136">Schutzhinterziehung</span><span class="sxs-lookup"><span data-stu-id="530b1-136">Defense Evasion</span></span>    | <span data-ttu-id="530b1-137">Behavior:Win32/DefenseEvasion.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-137">Behavior:Win32/DefenseEvasion.\*!ml</span></span> |
|<span data-ttu-id="530b1-138">Zugriff auf Anmeldeinformationen</span><span class="sxs-lookup"><span data-stu-id="530b1-138">Credential Access</span></span>  | <span data-ttu-id="530b1-139">Verhalten:Win32/CredentialAccess.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-139">Behavior:Win32/CredentialAccess.\*!ml</span></span> |
|<span data-ttu-id="530b1-140">Suche</span><span class="sxs-lookup"><span data-stu-id="530b1-140">Discovery</span></span>  | <span data-ttu-id="530b1-141">Behavior:Win32/Discovery.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-141">Behavior:Win32/Discovery.\*!ml</span></span> |
|<span data-ttu-id="530b1-142">Laterale Bewegung</span><span class="sxs-lookup"><span data-stu-id="530b1-142">Lateral Movement</span></span> | <span data-ttu-id="530b1-143">Verhalten:Win32/LateralMovement.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-143">Behavior:Win32/LateralMovement.\*!ml</span></span> |
|<span data-ttu-id="530b1-144">Auflistung</span><span class="sxs-lookup"><span data-stu-id="530b1-144">Collection</span></span> |   <span data-ttu-id="530b1-145">Behavior:Win32/Collection.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-145">Behavior:Win32/Collection.\*!ml</span></span> |
|<span data-ttu-id="530b1-146">Befehl und Steuerelement</span><span class="sxs-lookup"><span data-stu-id="530b1-146">Command and Control</span></span> | <span data-ttu-id="530b1-147">Verhalten:Win32/CommandAndControl.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-147">Behavior:Win32/CommandAndControl.\*!ml</span></span> |
|<span data-ttu-id="530b1-148">Exfiltration</span><span class="sxs-lookup"><span data-stu-id="530b1-148">Exfiltration</span></span>   | <span data-ttu-id="530b1-149">Verhalten:Win32/Exfiltration.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-149">Behavior:Win32/Exfiltration.\*!ml</span></span> |
|<span data-ttu-id="530b1-150">Auswirkung</span><span class="sxs-lookup"><span data-stu-id="530b1-150">Impact</span></span> | <span data-ttu-id="530b1-151">Behavior:Win32/Impact.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-151">Behavior:Win32/Impact.\*!ml</span></span> |
|<span data-ttu-id="530b1-152">Nicht kategorisiert</span><span class="sxs-lookup"><span data-stu-id="530b1-152">Uncategorized</span></span>  | <span data-ttu-id="530b1-153">Verhalten:Win32/Generic.\*!ml</span><span class="sxs-lookup"><span data-stu-id="530b1-153">Behavior:Win32/Generic.\*!ml</span></span> |

> [!TIP]
> <span data-ttu-id="530b1-154">Weitere Informationen zu bestimmten Bedrohungen finden Sie unter **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span><span class="sxs-lookup"><span data-stu-id="530b1-154">To learn more about specific threats, see **[recent global threat activity](https://www.microsoft.com/wdsi/threats)**.</span></span>


## <a name="configuring-client-behavioral-blocking"></a><span data-ttu-id="530b1-155">Konfigurieren von Clientverhaltensblockierung</span><span class="sxs-lookup"><span data-stu-id="530b1-155">Configuring client behavioral blocking</span></span>

<span data-ttu-id="530b1-156">Wenn Ihre Organisation Defender for Endpoint verwendet, ist die Clientverhaltensblockierung standardmäßig aktiviert.</span><span class="sxs-lookup"><span data-stu-id="530b1-156">If your organization is using Defender for Endpoint, client behavioral blocking is enabled by default.</span></span> <span data-ttu-id="530b1-157">Um jedoch von allen Defender for [](behavioral-blocking-containment.md)Endpoint-Funktionen zu profitieren, einschließlich der Verhaltensblockierung und -eindämmung, stellen Sie sicher, dass die folgenden Features und Funktionen von Defender for Endpoint aktiviert und konfiguriert sind:</span><span class="sxs-lookup"><span data-stu-id="530b1-157">However, to benefit from all Defender for Endpoint capabilities, including [behavioral blocking and containment](behavioral-blocking-containment.md), make sure the following features and capabilities of Defender for Endpoint are enabled and configured:</span></span>

- [<span data-ttu-id="530b1-158">Defender for Endpoint-Baselines</span><span class="sxs-lookup"><span data-stu-id="530b1-158">Defender for Endpoint baselines</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [<span data-ttu-id="530b1-159">In Defender for Endpoint integrierte Geräte</span><span class="sxs-lookup"><span data-stu-id="530b1-159">Devices onboarded to Defender for Endpoint</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [<span data-ttu-id="530b1-160">EDR im Blockmodus</span><span class="sxs-lookup"><span data-stu-id="530b1-160">EDR in block mode</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- <span data-ttu-id="530b1-161">[Verringerung der Angriffsfläche](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction):</span><span class="sxs-lookup"><span data-stu-id="530b1-161">[Attack surface reduction](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)</span></span>

- <span data-ttu-id="530b1-162">[Schutz der nächsten Generation](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (Antivirus)</span><span class="sxs-lookup"><span data-stu-id="530b1-162">[Next-generation protection](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (antivirus)</span></span>

## <a name="related-articles"></a><span data-ttu-id="530b1-163">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="530b1-163">Related articles</span></span>

- [<span data-ttu-id="530b1-164">Verhaltensbasiertes Blockieren und Eindämmen</span><span class="sxs-lookup"><span data-stu-id="530b1-164">Behavioral blocking and containment</span></span>](behavioral-blocking-containment.md)

- [<span data-ttu-id="530b1-165">Feedback-Loop-Blockierung</span><span class="sxs-lookup"><span data-stu-id="530b1-165">Feedback-loop blocking</span></span>](feedback-loop-blocking.md)

- [<span data-ttu-id="530b1-166">(Blog) Verhaltensblockierung und -eindämmung: Transformieren von Optik in Schutz</span><span class="sxs-lookup"><span data-stu-id="530b1-166">(Blog) Behavioral blocking and containment: Transforming optics into protection</span></span>](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [<span data-ttu-id="530b1-167">Hilfreiche Defender for Endpoint-Ressourcen</span><span class="sxs-lookup"><span data-stu-id="530b1-167">Helpful Defender for Endpoint resources</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
