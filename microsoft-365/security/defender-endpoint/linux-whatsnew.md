---
title: Neues in Microsoft Defender for Endpoint unter Linux
description: Liste der wichtigsten Änderungen für Microsoft Defender for Endpoint unter Linux.
keywords: microsoft, defender, Microsoft Defender for Endpoint, linux, whatsnew, release
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 0adcecefc19c681ef68498a3e7c375913d85985d
ms.sourcegitcommit: 07e536f1a6e335f114da55048844e4a866fe731b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52651128"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="702d1-104">Neues in Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="702d1-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012964-30121042129640"></a><span data-ttu-id="702d1-105">101.29.64 (30.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="702d1-105">101.29.64 (30.121042.12964.0)</span></span>

- <span data-ttu-id="702d1-106">Ab dieser Version werden Bedrohungen, die während der überprüfungen bei Bedarf erkannt werden, die über den Befehlszeilenclient ausgelöst werden, automatisch behoben.</span><span class="sxs-lookup"><span data-stu-id="702d1-106">Starting with this version, threats detected during on-demand antivirus scans triggered through the command-line client are automatically remediated.</span></span> <span data-ttu-id="702d1-107">Bedrohungen, die bei Scans erkannt werden, die über die Benutzeroberfläche ausgelöst werden, erfordern weiterhin manuelle Aktionen.</span><span class="sxs-lookup"><span data-stu-id="702d1-107">Threats detected during scans triggered through the user interface still require manual action.</span></span>
- <span data-ttu-id="702d1-108">`mdatp diagnostic real-time-protection-statistics` unterstützt jetzt zwei zusätzliche Switches:</span><span class="sxs-lookup"><span data-stu-id="702d1-108">`mdatp diagnostic real-time-protection-statistics` now supports two additional switches:</span></span>
  - <span data-ttu-id="702d1-109">`--sort`: sortiert die Ausgabe absteigend nach der Gesamtzahl der gescannten Dateien</span><span class="sxs-lookup"><span data-stu-id="702d1-109">`--sort`: sorts the output descending by total number of files scanned</span></span>
  - <span data-ttu-id="702d1-110">`--top N`: zeigt die obersten N-Ergebnisse an (funktioniert nur, wenn `--sort` auch angegeben ist)</span><span class="sxs-lookup"><span data-stu-id="702d1-110">`--top N`: displays the top N results (only works if `--sort` is also specified)</span></span>
- <span data-ttu-id="702d1-111">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="702d1-111">Performance improvements & bug fixes</span></span>

## <a name="1012572-30121022125630"></a><span data-ttu-id="702d1-112">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="702d1-112">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="702d1-113">Microsoft Defender for Endpoint unter Linux ist jetzt in der Vorschau für Us Government-Kunden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="702d1-113">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="702d1-114">Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint for US Government customers](gov.md).</span><span class="sxs-lookup"><span data-stu-id="702d1-114">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="702d1-115">Es wurde ein Problem behoben, bei dem die Verwendung von Microsoft Defender for Endpoint unter Linux auf Systemen mit DENOE-Dateisystemen dazu führte, dass das Betriebssystem hängte.</span><span class="sxs-lookup"><span data-stu-id="702d1-115">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="702d1-116">Leistungsverbesserungen & anderen Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="702d1-116">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="702d1-117">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="702d1-117">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="702d1-118">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="702d1-118">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="702d1-119">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="702d1-119">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="702d1-120">Leistungsverbesserung für die Situation, dass ein ganzer Bereitstellungspunkt zur Liste der Antivirenausschlüsse hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="702d1-120">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="702d1-121">Vor dieser Version wurde die Dateiaktivität, die vom Bereitstellungspunkt stammt, noch vom Produkt verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="702d1-121">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="702d1-122">Ab dieser Version wird die Dateiaktivität für ausgeschlossene Bereitstellungspunkte unterdrückt, was zu einer besseren Produktleistung führt.</span><span class="sxs-lookup"><span data-stu-id="702d1-122">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="702d1-123">Dem Befehlszeilentool wurde eine neue Option hinzugefügt, um Informationen zum letzten On-Demand-Scan anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="702d1-123">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="702d1-124">Führen Sie zum Anzeigen von Informationen zum letzten Bedarfsscan aus `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="702d1-124">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="702d1-125">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="702d1-125">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="702d1-126">101.18.53</span><span class="sxs-lookup"><span data-stu-id="702d1-126">101.18.53</span></span>

- <span data-ttu-id="702d1-127">EDR für Linux ist jetzt [allgemein verfügbar](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="702d1-127">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="702d1-128">Ein neuer Befehlszeilenschalter ( ) wurde hinzugefügt, `--ignore-exclusions` um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="702d1-128">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="702d1-129">Erweitert mit einem neuen Parameter ( ), der das Speichern der Diagnoseprotokolle `mdatp diagnostic create` in einem anderen Verzeichnis `--path [directory]` ermöglicht</span><span class="sxs-lookup"><span data-stu-id="702d1-129">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="702d1-130">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="702d1-130">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="702d1-131">101.12.99</span><span class="sxs-lookup"><span data-stu-id="702d1-131">101.12.99</span></span>

- <span data-ttu-id="702d1-132">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="702d1-132">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="702d1-133">101.04.76</span><span class="sxs-lookup"><span data-stu-id="702d1-133">101.04.76</span></span>

- <span data-ttu-id="702d1-134">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="702d1-134">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="702d1-135">101.03.48</span><span class="sxs-lookup"><span data-stu-id="702d1-135">101.03.48</span></span>

- <span data-ttu-id="702d1-136">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="702d1-136">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="702d1-137">101.02.55</span><span class="sxs-lookup"><span data-stu-id="702d1-137">101.02.55</span></span>

- <span data-ttu-id="702d1-138">Ein Problem wurde behoben, bei dem das Produkt nach einem Neustart/Upgrade manchmal nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="702d1-138">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="702d1-139">Behebung eines Problems, bei dem Proxyeinstellungen nicht über Produktupgrades hinweg beibehalten wurden</span><span class="sxs-lookup"><span data-stu-id="702d1-139">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="702d1-140">101.00.75</span><span class="sxs-lookup"><span data-stu-id="702d1-140">101.00.75</span></span>

- <span data-ttu-id="702d1-141">Unterstützung für die folgenden Dateisystemtypen hinzugefügt: `ecryptfs` , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` und `vfat`</span><span class="sxs-lookup"><span data-stu-id="702d1-141">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="702d1-142">Neue Syntax für [das Befehlszeilentool](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="702d1-142">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="702d1-143">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="702d1-143">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="702d1-144">100.90.70</span><span class="sxs-lookup"><span data-stu-id="702d1-144">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="702d1-145">Beim Upgrade des installierten Pakets von einer Produktversion vor 100.90.70 kann das Update bei Red Hat- und SLES-Verteilungen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="702d1-145">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="702d1-146">Dies liegt an einer wesentlichen Änderung in einem Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="702d1-146">This is because of a major change in a file path.</span></span> <span data-ttu-id="702d1-147">Eine temporäre Lösung besteht in der Entfernung des älteren Pakets und anschließender Installation des neueren Pakets.</span><span class="sxs-lookup"><span data-stu-id="702d1-147">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="702d1-148">Dieses Problem ist in neueren Versionen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="702d1-148">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="702d1-149">[Antivirusausschlüsse unterstützen jetzt Platzhalter](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="702d1-149">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="702d1-150">Die Möglichkeit zur Problembehandlung [bei Leistungsproblemen wurde](linux-support-perf.md) über das `mdatp` Befehlszeilentool hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="702d1-150">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="702d1-151">Verbesserungen, um die Paketinstallation robuster zu machen</span><span class="sxs-lookup"><span data-stu-id="702d1-151">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="702d1-152">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="702d1-152">Performance improvements & bug fixes</span></span>
