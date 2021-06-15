---
title: Aktivieren und Konfigurieren Microsoft Defender Antivirus Schutzfeatures
description: Aktivieren Sie verhaltensbasierten, heuristischen und Echtzeitschutz in Microsoft Defender AV.
keywords: Heuristic, Machine Learning, Verhaltensüberwachung, Echtzeitschutz, always-on, Microsoft Defender Antivirus, Antischadsoftware, Sicherheit, Defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.openlocfilehash: d8ce2ded8fd3270bcb095022c714f07d8030e1f7
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52925563"
---
# <a name="configure-behavioral-heuristic-and-real-time-protection"></a><span data-ttu-id="831b6-104">Konfigurieren von verhaltensbasiertem, heuristischem und Echtzeitschutz</span><span class="sxs-lookup"><span data-stu-id="831b6-104">Configure behavioral, heuristic, and real-time protection</span></span>


<span data-ttu-id="831b6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="831b6-105">**Applies to:**</span></span>

- [<span data-ttu-id="831b6-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="831b6-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="831b6-107">Microsoft Defender Antivirus verwendet verschiedene Methoden zum Schutz vor Bedrohungen:</span><span class="sxs-lookup"><span data-stu-id="831b6-107">Microsoft Defender Antivirus uses several methods to provide threat protection:</span></span>

- <span data-ttu-id="831b6-108">Über die Cloud bereitgestellter Schutz für nahezu sofortige Erkennung und Blockierung neuer und neuer Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="831b6-108">Cloud-delivered protection for near-instant detection and blocking of new and emerging threats</span></span>
- <span data-ttu-id="831b6-109">Always-On-Überprüfung unter Verwendung der Datei- und Prozessverhaltensüberwachung und anderer Heuristiken (auch als "Echtzeitschutz" bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="831b6-109">Always-on scanning, using file and process behavior monitoring and other heuristics (also known as "real-time protection")</span></span>
- <span data-ttu-id="831b6-110">Dedizierte Updates für den Schutz, die auf Machine Learning, von Personen oder automatisch durchgeführten Big Data-Analysen und umfassenden Forschungen zur Abwehr von Bedrohungen basieren</span><span class="sxs-lookup"><span data-stu-id="831b6-110">Dedicated protection updates based on machine-learning, human and automated big-data analysis, and in-depth threat resistance research</span></span>

<span data-ttu-id="831b6-111">Sie können konfigurieren, wie Microsoft Defender Antivirus diese Methoden mit Gruppenrichtlinien, System Center Konfigurationsverwaltung, PowerShell-Cmdlets und Windows-Verwaltungsinstrumentation (Management Instrumentation, WMI) verwenden.</span><span class="sxs-lookup"><span data-stu-id="831b6-111">You can configure how Microsoft Defender Antivirus uses these methods with Group Policy, System Center Configuration Manage, PowerShell cmdlets, and Windows Management Instrumentation (WMI).</span></span>

<span data-ttu-id="831b6-112">In diesem Abschnitt wird die Konfiguration für always-on-Scans behandelt, einschließlich der Erkennung und Blockierung von Apps, die als unsicher eingestuft werden, aber möglicherweise nicht als Schadsoftware erkannt werden.</span><span class="sxs-lookup"><span data-stu-id="831b6-112">This section covers configuration for always-on scanning, including how to detect and block apps that are deemed unsafe, but may not be detected as malware.</span></span>

<span data-ttu-id="831b6-113">Informationen zum Aktivieren und Konfigurieren von Microsoft Defender Antivirus über die Cloud bereitgestellten Schutz finden Sie unter "Verwenden von Technologien der nächsten Generation Microsoft Defender Antivirus über den über die [Cloud bereitgestellten Schutz".](cloud-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="831b6-113">See [Use next-gen Microsoft Defender Antivirus technologies through cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for how to enable and configure Microsoft Defender Antivirus cloud-delivered protection.</span></span>

## <a name="in-this-section"></a><span data-ttu-id="831b6-114">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="831b6-114">In this section</span></span>

 <span data-ttu-id="831b6-115">Thema</span><span class="sxs-lookup"><span data-stu-id="831b6-115">Topic</span></span> | <span data-ttu-id="831b6-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="831b6-116">Description</span></span>
---|---
[<span data-ttu-id="831b6-117">Erkennen und Blockieren von potenziell unerwünschten Anwendungen</span><span class="sxs-lookup"><span data-stu-id="831b6-117">Detect and block potentially unwanted applications</span></span>](detect-block-potentially-unwanted-apps-microsoft-defender-antivirus.md) | <span data-ttu-id="831b6-118">Erkennen und Blockieren von Apps, die in Ihrem Netzwerk möglicherweise unerwünscht sind, z. B. Adware, Browsermodifizierer und Symbolleisten sowie nicht autorisierte oder gefälschte Antiviren-Apps</span><span class="sxs-lookup"><span data-stu-id="831b6-118">Detect and block apps that may be unwanted in your network, such as adware, browser modifiers and toolbars, and rogue or fake antivirus apps</span></span>
[<span data-ttu-id="831b6-119">Aktivieren und Konfigurieren Microsoft Defender Antivirus Schutzfunktionen</span><span class="sxs-lookup"><span data-stu-id="831b6-119">Enable and configure Microsoft Defender Antivirus protection capabilities</span></span>](configure-real-time-protection-microsoft-defender-antivirus.md) | <span data-ttu-id="831b6-120">Aktivieren und Konfigurieren von Echtzeitschutz, Heuristiken und anderen ständig aktivierten Microsoft Defender Antivirus-Überwachungsfeatures</span><span class="sxs-lookup"><span data-stu-id="831b6-120">Enable and configure real-time protection, heuristics, and other always-on Microsoft Defender Antivirus monitoring features</span></span>
