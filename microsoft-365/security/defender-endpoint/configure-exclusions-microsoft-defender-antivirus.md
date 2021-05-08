---
title: Einrichten von Ausschlüssen für Microsoft Defender Antivirus Scans
description: Sie können Dateien (einschließlich Dateien, die von angegebenen Prozessen geändert wurden) und Ordner davon ausschließen, dass sie von der Microsoft Defender Antivirus. Überprüfen Sie Ihre Ausschlüsse mit PowerShell.
keywords: ''
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ksarens
manager: dansimp
ms.technology: mde
ms.audience: ITPro
ms.topic: how-to
ms.openlocfilehash: 7065aa7cd1975b2f5a38e79da8618ba3efdcdac5
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52275120"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-antivirus-scans"></a><span data-ttu-id="49e6f-104">Konfigurieren und Überprüfen von Ausschlüssen für Microsoft Defender Antivirus Scans</span><span class="sxs-lookup"><span data-stu-id="49e6f-104">Configure and validate exclusions for Microsoft Defender Antivirus scans</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="49e6f-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="49e6f-105">**Applies to:**</span></span>

- [<span data-ttu-id="49e6f-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="49e6f-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="49e6f-107">Sie können bestimmte Dateien, Ordner, Prozesse und vom Prozess geöffnete Dateien aus Microsoft Defender Antivirus ausschließen.</span><span class="sxs-lookup"><span data-stu-id="49e6f-107">You can exclude certain files, folders, processes, and process-opened files from Microsoft Defender Antivirus scans.</span></span> <span data-ttu-id="49e6f-108">Solche Ausschlüsse gelten für [geplante](scheduled-catch-up-scans-microsoft-defender-antivirus.md)Scans, [Bedarfsscans](run-scan-microsoft-defender-antivirus.md)und [Immer-on-Echtzeitschutz und -überwachung.](configure-real-time-protection-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="49e6f-108">Such exclusions apply to [scheduled scans](scheduled-catch-up-scans-microsoft-defender-antivirus.md), [on-demand scans](run-scan-microsoft-defender-antivirus.md), and [always-on real-time protection and monitoring](configure-real-time-protection-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="49e6f-109">Ausschlüsse für vom Prozess geöffnete Dateien gelten nur für den Echtzeitschutz.</span><span class="sxs-lookup"><span data-stu-id="49e6f-109">Exclusions for process-opened files only apply to real-time protection.</span></span>

## <a name="configure-and-validate-exclusions"></a><span data-ttu-id="49e6f-110">Konfigurieren und Überprüfen von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="49e6f-110">Configure and validate exclusions</span></span>

<span data-ttu-id="49e6f-111">Informationen zum Konfigurieren und Überprüfen von Ausschlüssen finden Sie im Folgenden:</span><span class="sxs-lookup"><span data-stu-id="49e6f-111">To configure and validate exclusions, see the following:</span></span>

- <span data-ttu-id="49e6f-112">[Konfigurieren und Überprüfen von Ausschlüssen basierend auf Dateinamen, Erweiterung und Ordnerspeicherort](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="49e6f-112">[Configure and validate exclusions based on file name, extension, and folder location](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="49e6f-113">Sie können Dateien von Microsoft Defender Antivirus dateierweiterung, Dateinamen oder Speicherort ausschließen.</span><span class="sxs-lookup"><span data-stu-id="49e6f-113">You can exclude files from Microsoft Defender Antivirus scans based on their file extension, file name, or location.</span></span>

- <span data-ttu-id="49e6f-114">[Konfigurieren und Überprüfen von Ausschlüssen für Dateien, die von Prozessen geöffnet werden.](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="49e6f-114">[Configure and validate exclusions for files opened by processes](configure-process-opened-file-exclusions-microsoft-defender-antivirus.md).</span></span> <span data-ttu-id="49e6f-115">Sie können Dateien von Scans ausschließen, die von einem bestimmten Prozess geöffnet wurden.</span><span class="sxs-lookup"><span data-stu-id="49e6f-115">You can exclude files from scans that have been opened by a specific process.</span></span>

## <a name="recommendations-for-defining-exclusions"></a><span data-ttu-id="49e6f-116">Empfehlungen zum Definieren von Ausschlüssen</span><span class="sxs-lookup"><span data-stu-id="49e6f-116">Recommendations for defining exclusions</span></span>

> [!IMPORTANT]
> <span data-ttu-id="49e6f-117">Microsoft Defender Antivirus umfasst viele automatische Ausschlüsse basierend auf bekannten Betriebssystemverhalten und typischen Verwaltungsdateien, z. B. in unternehmensweitem Management, Datenbankverwaltung und anderen Unternehmensszenarien und -situationen.</span><span class="sxs-lookup"><span data-stu-id="49e6f-117">Microsoft Defender Antivirus includes many automatic exclusions based on known operating system behaviors and typical management files, such as those used in enterprise management, database management, and other enterprise scenarios and situations.</span></span>  
> 
> <span data-ttu-id="49e6f-118">Durch das Definieren von Ausschlüssen wird der von der Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="49e6f-118">Defining exclusions lowers the protection offered by Microsoft Defender Antivirus.</span></span> <span data-ttu-id="49e6f-119">Sie sollten immer die Risiken bewerten, die mit der Implementierung von Ausschlüssen verbunden sind, und Sie sollten nur Dateien ausschließen, von deren Ausführung Sie sicher sind, dass sie nicht bösartig sind.</span><span class="sxs-lookup"><span data-stu-id="49e6f-119">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

<span data-ttu-id="49e6f-120">Beachten Sie beim Definieren von Ausschlüssen die folgenden Punkte:</span><span class="sxs-lookup"><span data-stu-id="49e6f-120">Keep the following points in mind when you are defining exclusions:</span></span>  

- <span data-ttu-id="49e6f-121">Ausschlüsse sind technisch eine Schutzlücke.</span><span class="sxs-lookup"><span data-stu-id="49e6f-121">Exclusions are technically a protection gap.</span></span> <span data-ttu-id="49e6f-122">Berücksichtigen Sie beim Definieren von Ausschlüssen immer Gegenmaßnahmen.</span><span class="sxs-lookup"><span data-stu-id="49e6f-122">Always consider mitigations when defining exclusions.</span></span> <span data-ttu-id="49e6f-123">Andere Gegenmaßnahmen können so einfach sein, dass sichergestellt wird, dass der ausgeschlossene Speicherort über die entsprechenden Zugriffssteuerungslisten (Access Control Lists, ACLs), Überwachungsrichtlinien, von einer aktuellen Software usw. verarbeitet wird.</span><span class="sxs-lookup"><span data-stu-id="49e6f-123">Other mitigations could be as simple as making sure the excluded location has the appropriate access-control lists (ACLs), audit policy, is processed by an up-to-date software, etc.</span></span>

- <span data-ttu-id="49e6f-124">Überprüfen Sie die Ausschlüsse regelmäßig.</span><span class="sxs-lookup"><span data-stu-id="49e6f-124">Review the exclusions periodically.</span></span> <span data-ttu-id="49e6f-125">Überprüfen und erzwingen Sie die Gegenmaßnahmen im Rahmen des Überprüfungsprozesses erneut.</span><span class="sxs-lookup"><span data-stu-id="49e6f-125">Recheck and re-enforce the mitigations as part of the review process.</span></span>

- <span data-ttu-id="49e6f-126">Vermeiden Sie im Idealfall das Definieren von Ausschlüssen, die proaktiv sein sollen.</span><span class="sxs-lookup"><span data-stu-id="49e6f-126">Ideally, avoid defining exclusions intending to be proactive.</span></span> <span data-ttu-id="49e6f-127">Schließen Sie beispielsweise etwas nicht aus, nur weil Sie denken, dass es in Zukunft ein Problem sein könnte.</span><span class="sxs-lookup"><span data-stu-id="49e6f-127">For instance, don't exclude something just because you think it might be a problem in the future.</span></span> <span data-ttu-id="49e6f-128">Verwenden Sie Ausschlüsse nur für bestimmte Probleme, z. B. für Leistungs- oder Anwendungskompatibilität, die durch Ausschlüsse verringert werden könnten.</span><span class="sxs-lookup"><span data-stu-id="49e6f-128">Use exclusions only for specific issues, such as those pertaining to performance or application compatibility that exclusions could mitigate.</span></span>

- <span data-ttu-id="49e6f-129">Überwachen sie die Änderungen an der Ausschlussliste.</span><span class="sxs-lookup"><span data-stu-id="49e6f-129">Audit the exclusion list changes.</span></span> <span data-ttu-id="49e6f-130">Der Sicherheitsadministrator sollte genügend Kontext beibehalten, um zu verstehen, warum ein bestimmter Ausschluss hinzugefügt wurde.</span><span class="sxs-lookup"><span data-stu-id="49e6f-130">The security admin should preserve enough context around why a certain exclusion was added.</span></span> <span data-ttu-id="49e6f-131">Sie sollten in der Lage sein, eine Antwort mit einer bestimmten Begründung zu geben, warum ein bestimmter Pfad ausgeschlossen wurde.</span><span class="sxs-lookup"><span data-stu-id="49e6f-131">You should be able to provide answer with specific reasoning as to why a certain path was excluded.</span></span>

## <a name="related-articles"></a><span data-ttu-id="49e6f-132">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="49e6f-132">Related articles</span></span>

- [<span data-ttu-id="49e6f-133">Microsoft Defender Antivirus Ausschlüsse auf Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="49e6f-133">Microsoft Defender Antivirus exclusions on Windows Server 2016</span></span>](configure-server-exclusions-microsoft-defender-antivirus.md)
- [<span data-ttu-id="49e6f-134">Häufige Fehler, die beim Festlegen von Ausschlüssen vermieden werden sollten</span><span class="sxs-lookup"><span data-stu-id="49e6f-134">Common mistakes to avoid when defining exclusions</span></span>](common-exclusion-mistakes-microsoft-defender-antivirus.md)
