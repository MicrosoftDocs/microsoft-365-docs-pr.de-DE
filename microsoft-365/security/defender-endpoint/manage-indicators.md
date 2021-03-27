---
title: Erstellen von Indikatoren
ms.reviewer: ''
description: 'Erstellen Sie Indikatoren für einen Dateihash, eine #A0, URLs oder Domänen, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.'
keywords: manage, allowed, blocked, block, clean, malicious, file hash, ip address, urls, domain
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 670c6449c1121bc329b1dfb37cd1d9948c99a3f8
ms.sourcegitcommit: a965c498e6b3890877f895d5197898b306092813
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51379298"
---
# <a name="create-indicators"></a><span data-ttu-id="93516-104">Erstellen von Indikatoren</span><span class="sxs-lookup"><span data-stu-id="93516-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="93516-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="93516-105">**Applies to:**</span></span>
- [<span data-ttu-id="93516-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="93516-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="93516-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="93516-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> <span data-ttu-id="93516-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="93516-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="93516-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="93516-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="93516-110">Der Kompromissindikator (IoCs) ist ein wesentliches Feature in jeder Endpunktschutzlösung.</span><span class="sxs-lookup"><span data-stu-id="93516-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="93516-111">Diese Funktion bietet SecOps die Möglichkeit, eine Liste von Indikatoren für die Erkennung und das Blockieren (Verhinderung und Reaktion) zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="93516-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="93516-112">Erstellen Sie Indikatoren, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="93516-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="93516-113">Sie können die zu ergreifende Aktion sowie die Dauer für die Anwendung der Aktion sowie den Bereich der Gerätegruppe definieren, auf die sie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="93516-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="93516-114">Derzeit unterstützte Quellen sind das Clouderkennungsmodul von Defender for Endpoint, das automatisierte Untersuchungs- und Korrekturmodul und das Modul zur Verhinderung von Endpunkten (Microsoft Defender Antivirus).</span><span class="sxs-lookup"><span data-stu-id="93516-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender Antivirus).</span></span>

<span data-ttu-id="93516-115">**Clouderkennungsmodul**</span><span class="sxs-lookup"><span data-stu-id="93516-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="93516-116">Das Clouderkennungsmodul von Defender for Endpoint überprüft regelmäßig gesammelte Daten und versucht, die von Ihnen festgelegten Indikatoren zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="93516-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="93516-117">Wenn eine Übereinstimmung vor liegt, werden die Aktionen entsprechend den Einstellungen ausgeführt, die Sie für das IoC angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="93516-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="93516-118">**Endpoint Prevention Engine**</span><span class="sxs-lookup"><span data-stu-id="93516-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="93516-119">Die gleiche Liste von Indikatoren wird vom Präventions-Agent berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="93516-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="93516-120">Wenn Microsoft Defender AV die primäre AV-Konfiguration ist, werden die übereinstimmende Indikatoren entsprechend den Einstellungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="93516-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="93516-121">Wenn die Aktion z. B. "Warnung und Block" ist, verhindert Microsoft Defender AV Dateiausführungen (blockieren und beugen) und eine entsprechende Warnung wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="93516-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="93516-122">Wenn die Aktion jedoch auf "Zulassen" festgelegt ist, erkennt oder blockiert Microsoft Defender AV die Ausführung der Datei nicht.</span><span class="sxs-lookup"><span data-stu-id="93516-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="93516-123">**Automatisiertes Untersuchungs- und Korrekturmodul**</span><span class="sxs-lookup"><span data-stu-id="93516-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="93516-124">Die automatisierte Untersuchung und Korrektur verhält sich gleich.</span><span class="sxs-lookup"><span data-stu-id="93516-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="93516-125">Wenn ein Indikator auf "Zulassen" festgelegt ist, ignoriert die automatisierte Untersuchung und Korrektur ein "schlechtes" Urteil dafür.</span><span class="sxs-lookup"><span data-stu-id="93516-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="93516-126">Wenn sie auf "Block" festgelegt ist, wird die automatische Untersuchung und Korrektur als "schlecht" behandelt.</span><span class="sxs-lookup"><span data-stu-id="93516-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>


<span data-ttu-id="93516-127">Die derzeit unterstützten Aktionen sind:</span><span class="sxs-lookup"><span data-stu-id="93516-127">The current supported actions are:</span></span>
- <span data-ttu-id="93516-128">Zulassen</span><span class="sxs-lookup"><span data-stu-id="93516-128">Allow</span></span>
- <span data-ttu-id="93516-129">Nur Warnung</span><span class="sxs-lookup"><span data-stu-id="93516-129">Alert only</span></span>
- <span data-ttu-id="93516-130">Warnung und Blockierung</span><span class="sxs-lookup"><span data-stu-id="93516-130">Alert and block</span></span>


<span data-ttu-id="93516-131">Sie können einen Indikator für:</span><span class="sxs-lookup"><span data-stu-id="93516-131">You can create an indicator for:</span></span>
- [<span data-ttu-id="93516-132">Files</span><span class="sxs-lookup"><span data-stu-id="93516-132">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="93516-133">IP-Adressen, URLs/Domänen</span><span class="sxs-lookup"><span data-stu-id="93516-133">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="93516-134">Zertifikate</span><span class="sxs-lookup"><span data-stu-id="93516-134">Certificates</span></span>](indicator-certificates.md)


> [!NOTE]
> <span data-ttu-id="93516-135">Es gibt eine Grenze von 15.000 Indikatoren pro Mandant.</span><span class="sxs-lookup"><span data-stu-id="93516-135">There is a limit of 15,000 indicators per tenant.</span></span> <span data-ttu-id="93516-136">Datei- und Zertifikatindikatoren blockieren keine [für Microsoft Defender Antivirus definierten Ausschlüsse.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="93516-136">File and certificate indicators do not block [exclusions defined for Microsoft Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="93516-137">Indikatoren werden in Microsoft Defender Antivirus nicht unterstützt, wenn sie sich im passiven Modus befinden.</span><span class="sxs-lookup"><span data-stu-id="93516-137">Indicators are not supported in Microsoft Defender Antivirus when it is in passive mode.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="93516-138">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="93516-138">Related topics</span></span>

- [<span data-ttu-id="93516-139">Erstellen von kontextbezogenem IoC</span><span class="sxs-lookup"><span data-stu-id="93516-139">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="93516-140">Verwenden der Microsoft Defender for Endpoint Indicators-API</span><span class="sxs-lookup"><span data-stu-id="93516-140">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="93516-141">Verwenden von partnerintegrierte Lösungen</span><span class="sxs-lookup"><span data-stu-id="93516-141">Use partner integrated solutions</span></span>](partner-applications.md)
