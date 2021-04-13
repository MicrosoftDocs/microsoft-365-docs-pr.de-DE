---
title: Aktivieren und Konfigurieren von Microsoft Defender Antivirus-Schutzfunktionen
description: Aktivieren Sie verhaltensbasierten, heuristischen und Echtzeitschutz in Microsoft Defender AV.
keywords: heuristic, machine-learning, behavior monitor, real-time protection, always-on, Microsoft Defender Antivirus, anmalware, security, defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7a0e0571445e8ec753c3813a81dbcca9c698e7df
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690332"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="220d6-104">Konfigurieren von Verhaltens-, Heuristik- und Echtzeitschutz</span><span class="sxs-lookup"><span data-stu-id="220d6-104">Configure behavioral, heuristic, and real-time protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="220d6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="220d6-105">**Applies to:**</span></span>

- [<span data-ttu-id="220d6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="220d6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="220d6-107">Microsoft Defender Antivirus verwendet verschiedene Methoden zum Schutz vor Bedrohungen:</span><span class="sxs-lookup"><span data-stu-id="220d6-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="220d6-108">In der Cloud zugestellter Schutz für die nahezu sofortige Erkennung und Blockierung neuer und neuer Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="220d6-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="220d6-109">Immer-on-Überprüfung unter Verwendung der Überwachung des Datei- und Prozessverhaltens und anderer Heuristiken (auch als "Echtzeitschutz" bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="220d6-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="220d6-110">Dedizierte Updates für den Schutz, die auf Machine Learning, von Personen oder automatisch durchgeführten Big Data-Analysen und umfassenden Forschungen zur Abwehr von Bedrohungen basieren</span><span class="sxs-lookup"><span data-stu-id="220d6-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="220d6-111">Sie können konfigurieren, wie Microsoft Defender Antivirus diese Methoden mit Gruppenrichtlinien, System Center Configuration Manage, PowerShell-Cmdlets und Windows Management Instrumentation (WMI) verwendet.</span><span class="sxs-lookup"><span data-stu-id="220d6-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="220d6-112">In diesem Abschnitt wird die Konfiguration für die immer eins zu verwendende Überprüfung behandelt, einschließlich der Erkennung und Blockierung von Apps, die als unsicher eingestuft werden, aber möglicherweise nicht als Schadsoftware erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="220d6-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="220d6-113">Informationen zum Aktivieren und Konfigurieren des cloudbasierten Schutzes von Microsoft Defender Antivirus finden Sie unter Use [next-gen Microsoft Defender Antivirus technologies through cloud-delivered](cloud-protection-microsoft-defender-antivirus.md) protection.</span><span class="sxs-lookup"><span data-stu-id="220d6-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="220d6-114">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="220d6-114">In this section</span></span>

 <span data-ttu-id="220d6-115">Thema</span><span class="sxs-lookup"><span data-stu-id="220d6-115">Topic</span></span> | <span data-ttu-id="220d6-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="220d6-116">Description</span></span>
---|---
[<span data-ttu-id="220d6-117">Erkennen und Blockieren potenziell unerwünschter Anwendungen</span><span class="sxs-lookup"><span data-stu-id="220d6-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="220d6-118">Erkennen und Blockieren von Apps, die in Ihrem Netzwerk möglicherweise nicht erwünscht sind, z. B. Adware, Browsermodifizierer und Symbolleisten sowie nicht autorisierte oder gefälschte Antiviren-Apps</span><span class="sxs-lookup"><span data-stu-id="220d6-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="220d6-119">Aktivieren und Konfigurieren von Microsoft Defender Antivirus-Schutzfunktionen</span><span class="sxs-lookup"><span data-stu-id="220d6-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="220d6-120">Aktivieren und Konfigurieren von Echtzeitschutz, Heuristik und anderen immer aktivierten Microsoft Defender Antivirus-Überwachungsfeatures</span><span class="sxs-lookup"><span data-stu-id="220d6-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>