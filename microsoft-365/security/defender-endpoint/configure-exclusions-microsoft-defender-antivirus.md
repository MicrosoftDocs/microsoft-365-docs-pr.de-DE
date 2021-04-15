---
title: Einrichten von Ausschlüssen für Microsoft Defender Antivirus-Scans
description: Sie können Dateien (einschließlich Dateien, die durch bestimmte Prozesse geändert wurden) und Ordner von Microsoft Defender AV aus der Scanung ausschließen. Überprüfen Sie Ihre Ausschlüsse mit PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 08f7f9d4a6e9e70d3ef071f30712b2ae53f4ea52
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764663"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="15423-104">Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender Antivirus-Scans</span><span class="sxs-lookup"><span data-stu-id="15423-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="15423-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="15423-105">**Applies to:**</span></span>

- [<span data-ttu-id="15423-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="15423-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="15423-107">Sie können bestimmte Dateien, Ordner, Prozesse und prozessge öffnende Dateien aus Microsoft Defender Antivirus-Scans ausschließen.</span><span class="sxs-lookup"><span data-stu-id="15423-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="15423-108">Solche Ausschlüsse gelten für [geplante](scheduled-catch-up-scans-microsoft-defender-antivirus.md)Scans, [Bedarfsscans](run-scan-microsoft-defender-antivirus.md)und [Immer-on-Echtzeitschutz und -überwachung.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="15423-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="15423-109">Ausschlüsse für vom Prozess geöffnete Dateien gelten nur für den Echtzeitschutz.</span><span class="sxs-lookup"><span data-stu-id="15423-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="15423-110">Konfigurieren und Überprüfen von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="15423-110">Configure and validate exclusions</span></span>

<span data-ttu-id="15423-111">Informationen zum Konfigurieren und Überprüfen von Ausschlüssen finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="15423-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="15423-112">[Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateinamen, Erweiterung und Ordnerspeicherort](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="15423-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="15423-113">Auf diese Weise können Sie Dateien basierend auf der Dateierweiterung, dem Dateinamen oder dem Speicherort von Microsoft Defender Antivirus-Scans ausschließen.</span><span class="sxs-lookup"><span data-stu-id="15423-113">This enables you to exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="15423-114">[Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="15423-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="15423-115">Auf diese Weise können Sie Dateien von Scans ausschließen, die von einem bestimmten Prozess geöffnet wurden.</span><span class="sxs-lookup"><span data-stu-id="15423-115">This enables you to exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="15423-116">Empfehlungen zum Definieren von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="15423-116">Recommendations for defining exclusions</span></span>
[!IMPORTANT]
<span data-ttu-id="15423-117">Microsoft Defender Antivirus enthält viele automatische Ausschlüsse, die auf bekannten Betriebssystemverhalten und typischen Verwaltungsdateien basieren, z. B. solche, die in der Unternehmensverwaltung, datenbankverwaltung und anderen Unternehmensszenarien und -situationen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="15423-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
<span data-ttu-id="15423-118">Durch das Definieren von Ausschlüssen wird der von Microsoft Defender Antivirus gebotene Schutz gesenkt.</span><span class="sxs-lookup"><span data-stu-id="15423-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="15423-119">Sie sollten immer die Risiken bewerten, die mit der Implementierung von Ausschlüssen verbunden sind, und Sie sollten nur Dateien ausschließen, von deren Ausführung Sie sicher sind, dass sie nicht bösartig sind.</span><span class="sxs-lookup"><span data-stu-id="15423-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="15423-120">Im Folgenden finden Sie eine Liste von Empfehlungen, die Sie beim Definieren von Ausschlüssen berücksichtigen sollten:</span><span class="sxs-lookup"><span data-stu-id="15423-120">The following is a list of recommendations that you should keep in mind when defining exclusions:</span></span>  

- <span data-ttu-id="15423-121">Ausschlüsse sind technisch eine Schutzlücke – berücksichtigen Sie bei der Definition von Ausschlüssen immer zusätzliche Gegenmaßnahmen.</span><span class="sxs-lookup"><span data-stu-id="15423-121">Exclusions are technically a protection gap—always consider additional mitigations when defining exclusions.</span></span> <span data-ttu-id="15423-122">Zusätzliche Gegenmaßnahmen können so einfach sein, dass sichergestellt wird, dass der ausgeschlossene Speicherort über die entsprechenden Zugriffssteuerungslisten (Access Control Lists, ACLs), Überwachungsrichtlinien, von einer aktuellen Software usw. verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="15423-122">Additional mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="15423-123">Überprüfen Sie die Ausschlüsse regelmäßig.</span><span class="sxs-lookup"><span data-stu-id="15423-123">Review the exclusions periodically.</span></span> <span data-ttu-id="15423-124">Überprüfen und erzwingen Sie die Gegenmaßnahmen im Rahmen des Überprüfungsprozesses erneut.</span><span class="sxs-lookup"><span data-stu-id="15423-124">Re-check and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="15423-125">Vermeiden Sie im Idealfall das Definieren proaktiver Ausschlüsse.</span><span class="sxs-lookup"><span data-stu-id="15423-125">Ideally, avoid defining proactive exclusions.</span></span> <span data-ttu-id="15423-126">Schließen Sie beispielsweise etwas nicht aus, nur weil Sie denken, dass es in Zukunft ein Problem sein könnte.</span><span class="sxs-lookup"><span data-stu-id="15423-126">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="15423-127">Verwenden Sie Ausschlüsse nur für bestimmte Probleme– hauptsächlich im Zusammenhang mit der Leistung oder manchmal im Zusammenhang mit der Anwendungskompatibilität, die durch Ausschlüsse verringert werden könnten.</span><span class="sxs-lookup"><span data-stu-id="15423-127">Use exclusions only for specific issues—mostly around performance, or sometimes around application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="15423-128">Überwachen sie die Änderungen an der Ausschlussliste.</span><span class="sxs-lookup"><span data-stu-id="15423-128">Audit the exclusion list changes.</span></span> <span data-ttu-id="15423-129">Der Sicherheitsadministrator sollte genügend Kontext beibehalten, um zu verstehen, warum ein bestimmter Ausschluss hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="15423-129">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="15423-130">Sie sollten in der Lage sein, eine Antwort mit einer bestimmten Begründung zu geben, warum ein bestimmter Pfad ausgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="15423-130">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="15423-131">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="15423-131">Related articles</span></span>

- [<span data-ttu-id="15423-132">Microsoft Defender Antivirus-Ausschlüsse unter Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="15423-132">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="15423-133">Häufige Fehler beim Definieren von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="15423-133">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
