---
title: Indikatoren erstellen
ms.reviewer: ''
description: Erstellen sie Indikatoren für einen Dateihash, eine IP-Adresse, URLs oder Domänen, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.
keywords: verwalten, zulässig, blockiert, blockieren, sauber, bösartig, Dateihash, IP-Adresse, URLs, Domäne
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
ms.openlocfilehash: fb87f36c5289d622df2615046c5bb2fd8fad9543
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842242"
---
# <a name="create-indicators"></a><span data-ttu-id="2da87-104">Indikatoren erstellen</span><span class="sxs-lookup"><span data-stu-id="2da87-104">Create indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="2da87-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="2da87-105">**Applies to:**</span></span>
- [<span data-ttu-id="2da87-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="2da87-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="2da87-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2da87-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!TIP]
> <span data-ttu-id="2da87-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="2da87-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2da87-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="2da87-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)

<span data-ttu-id="2da87-110">Der Kompromissindikator (Indicator of Compromise, IoCs) ist ein wesentliches Feature in jeder Endpunktschutzlösung.</span><span class="sxs-lookup"><span data-stu-id="2da87-110">Indicator of compromise (IoCs) matching is an essential feature in every endpoint protection solution.</span></span> <span data-ttu-id="2da87-111">Diese Funktion bietet SecOps die Möglichkeit, eine Liste von Indikatoren für die Erkennung und die Blockierung (Verhinderung und Reaktion) festzulegen.</span><span class="sxs-lookup"><span data-stu-id="2da87-111">This capability gives SecOps the ability to set a list of indicators for detection and for blocking (prevention and response).</span></span>

<span data-ttu-id="2da87-112">Erstellen Sie Indikatoren, die die Erkennung, Verhinderung und den Ausschluss von Entitäten definieren.</span><span class="sxs-lookup"><span data-stu-id="2da87-112">Create indicators that define the detection, prevention, and exclusion of entities.</span></span> <span data-ttu-id="2da87-113">Sie können die auszuführende Aktion sowie die Dauer für das Anwenden der Aktion sowie den Bereich der Gerätegruppe definieren, auf die sie angewendet werden soll.</span><span class="sxs-lookup"><span data-stu-id="2da87-113">You can define the action to be taken as well as the duration for when to apply the action as well as the scope of the device group to apply it to.</span></span>

<span data-ttu-id="2da87-114">Derzeit unterstützte Quellen sind das Clouderkennungsmodul von Defender für Endpunkt, das automatisierte Untersuchungs- und Wartungsmodul und das Modul zur Endpunktverhinderung (Microsoft Defender Antivirus).</span><span class="sxs-lookup"><span data-stu-id="2da87-114">Currently supported sources are the cloud detection engine of Defender for Endpoint, the automated investigation and remediation engine, and the endpoint prevention engine (Microsoft Defender Antivirus).</span></span>

<span data-ttu-id="2da87-115">**Cloud-Erkennungsmodul**</span><span class="sxs-lookup"><span data-stu-id="2da87-115">**Cloud detection engine**</span></span><br>
<span data-ttu-id="2da87-116">Das Clouderkennungsmodul von Defender für Endpunkt überprüft regelmäßig gesammelte Daten und versucht, die von Ihnen festgelegten Indikatoren zuzuordnen.</span><span class="sxs-lookup"><span data-stu-id="2da87-116">The cloud detection engine of Defender for Endpoint regularly scans collected data and tries to match the indicators you set.</span></span> <span data-ttu-id="2da87-117">Wenn eine Übereinstimmung vorliegt, wird die Aktion gemäß den Einstellungen ausgeführt, die Sie für ioC angegeben haben.</span><span class="sxs-lookup"><span data-stu-id="2da87-117">When there is a match, action will be taken according to the settings you specified for the IoC.</span></span>

<span data-ttu-id="2da87-118">**Endpunktverhütungsmodul**</span><span class="sxs-lookup"><span data-stu-id="2da87-118">**Endpoint prevention engine**</span></span><br>
<span data-ttu-id="2da87-119">Die gleiche Liste von Indikatoren wird vom Präventions-Agent berücksichtigt.</span><span class="sxs-lookup"><span data-stu-id="2da87-119">The same list of indicators is honored by the prevention agent.</span></span> <span data-ttu-id="2da87-120">Wenn Microsoft Defender AV also der primäre konfigurierte AV ist, werden die übereinstimmenden Indikatoren entsprechend den Einstellungen behandelt.</span><span class="sxs-lookup"><span data-stu-id="2da87-120">Meaning, if Microsoft Defender AV is the primary AV configured, the matched indicators will be treated according to the settings.</span></span> <span data-ttu-id="2da87-121">Wenn die Aktion z. B. "Warnung und Blockierung" lautet, verhindert Microsoft Defender AV Dateiausführungen (blockieren und korrigieren), und eine entsprechende Warnung wird ausgelöst.</span><span class="sxs-lookup"><span data-stu-id="2da87-121">For example, if the action is "Alert and Block", Microsoft Defender AV will prevent file executions (block and remediate) and a corresponding alert will be raised.</span></span> <span data-ttu-id="2da87-122">Wenn die Aktion hingegen auf "Zulassen" festgelegt ist, erkennt oder blockiert Microsoft Defender AV die Ausführung der Datei nicht.</span><span class="sxs-lookup"><span data-stu-id="2da87-122">On the other hand, if the Action is set to "Allow", Microsoft Defender AV will not detect nor block the file from being run.</span></span>

<span data-ttu-id="2da87-123">**Automatisiertes Untersuchungs- und Wartungsmodul**</span><span class="sxs-lookup"><span data-stu-id="2da87-123">**Automated investigation and remediation engine**</span></span><BR>
<span data-ttu-id="2da87-124">Die automatische Untersuchung und Korrektur verhält sich gleich.</span><span class="sxs-lookup"><span data-stu-id="2da87-124">The automated investigation and remediation behave the same.</span></span> <span data-ttu-id="2da87-125">Wenn ein Indikator auf "Zulassen" festgelegt ist, ignoriert die automatisierte Untersuchung und Behebung ein "schlechtes" Bewertungszeichen dafür.</span><span class="sxs-lookup"><span data-stu-id="2da87-125">If an indicator is set to "Allow", Automated investigation and remediation will ignore a "bad" verdict for it.</span></span> <span data-ttu-id="2da87-126">Wenn sie auf "Blockieren" festgelegt ist, wird sie von der automatischen Untersuchung und Behebung als "schlecht" behandelt.</span><span class="sxs-lookup"><span data-stu-id="2da87-126">If set to "Block", Automated investigation and remediation will treat it as "bad".</span></span>

> [!NOTE]
> <span data-ttu-id="2da87-127">Die EnableFileHashComputation-Einstellung berechnet den Dateihash für das Zertifikat und die Datei-IoC während Dateiüberprüfungen.</span><span class="sxs-lookup"><span data-stu-id="2da87-127">The EnableFileHashComputation setting computes the file hash for the cert and file IoC during file scans.</span></span> <span data-ttu-id="2da87-128">Es unterstützt die IoC-Erzwingung von Hashes und Zertifikaten, die zu vertrauenswürdigen Anwendungen gehören.</span><span class="sxs-lookup"><span data-stu-id="2da87-128">It supports IoC enforcement of hashes and certs belong to trusted applications.</span></span> <span data-ttu-id="2da87-129">Sie wird gleichzeitig aktiviert und mit der Einstellung "Datei zulassen" oder "Datei blockieren" deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2da87-129">It will be concurrently enabled and disabled with the allow or block file setting.</span></span> <span data-ttu-id="2da87-130">EnableFileHashComputation wird manuell über die Gruppenrichtlinie aktiviert und ist standardmäßig deaktiviert.</span><span class="sxs-lookup"><span data-stu-id="2da87-130">EnableFileHashComputation is enabled manually through Group Policy, and is disabled by default.</span></span>


<span data-ttu-id="2da87-131">Die aktuellen unterstützten Aktionen sind:</span><span class="sxs-lookup"><span data-stu-id="2da87-131">The current supported actions are:</span></span>
- <span data-ttu-id="2da87-132">Zulassen</span><span class="sxs-lookup"><span data-stu-id="2da87-132">Allow</span></span>
- <span data-ttu-id="2da87-133">Nur Warnung</span><span class="sxs-lookup"><span data-stu-id="2da87-133">Alert only</span></span>
- <span data-ttu-id="2da87-134">Warnung und Blockierung</span><span class="sxs-lookup"><span data-stu-id="2da87-134">Alert and block</span></span>


<span data-ttu-id="2da87-135">Sie können einen Indikator für Folgendes erstellen:</span><span class="sxs-lookup"><span data-stu-id="2da87-135">You can create an indicator for:</span></span>
- [<span data-ttu-id="2da87-136">Files</span><span class="sxs-lookup"><span data-stu-id="2da87-136">Files</span></span>](indicator-file.md)
- [<span data-ttu-id="2da87-137">IP-Adressen, URLs/Domänen</span><span class="sxs-lookup"><span data-stu-id="2da87-137">IP addresses, URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="2da87-138">Zertifikate</span><span class="sxs-lookup"><span data-stu-id="2da87-138">Certificates</span></span>](indicator-certificates.md)


> [!NOTE]
> <span data-ttu-id="2da87-139">Es gibt einen Grenzwert von 15.000 Indikatoren pro Mandant.</span><span class="sxs-lookup"><span data-stu-id="2da87-139">There is a limit of 15,000 indicators per tenant.</span></span> <span data-ttu-id="2da87-140">Datei- und Zertifikatindikatoren blockieren keine [Ausschlüsse, die für Microsoft Defender Antivirus definiert sind.](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="2da87-140">File and certificate indicators do not block [exclusions defined for Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/configure-exclusions-microsoft-defender-antivirus).</span></span> <span data-ttu-id="2da87-141">Indikatoren werden in Microsoft Defender Antivirus nicht unterstützt, wenn sie sich im passiven Modus befinden.</span><span class="sxs-lookup"><span data-stu-id="2da87-141">Indicators are not supported in Microsoft Defender Antivirus when it is in passive mode.</span></span> 


## <a name="related-topics"></a><span data-ttu-id="2da87-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="2da87-142">Related topics</span></span>

- [<span data-ttu-id="2da87-143">Erstellen von Kontext-IoC</span><span class="sxs-lookup"><span data-stu-id="2da87-143">Create contextual IoC</span></span>](respond-file-alerts.md#add-indicator-to-block-or-allow-a-file)
- [<span data-ttu-id="2da87-144">Verwenden der Microsoft Defender für Endpunkt-Indikatoren-API</span><span class="sxs-lookup"><span data-stu-id="2da87-144">Use the Microsoft Defender for Endpoint indicators API</span></span>](ti-indicator.md)
- [<span data-ttu-id="2da87-145">Verwenden von integrierten Partnerlösungen</span><span class="sxs-lookup"><span data-stu-id="2da87-145">Use partner integrated solutions</span></span>](partner-applications.md)
