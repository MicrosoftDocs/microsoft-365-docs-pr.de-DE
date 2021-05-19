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
ms.openlocfilehash: 21eaf1c0e0d3f61bb5798c8a4de6fe8f97ce4a0b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538795"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="cd94c-104">Neues in Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="cd94c-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012964-30121042129640"></a><span data-ttu-id="cd94c-105">101.29.64 (30.121042.12964.0)</span><span class="sxs-lookup"><span data-stu-id="cd94c-105">101.29.64 (30.121042.12964.0)</span></span>

- <span data-ttu-id="cd94c-106">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="cd94c-106">Performance improvements & bug fixes</span></span>

## <a name="1012572-30121022125630"></a><span data-ttu-id="cd94c-107">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="cd94c-107">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="cd94c-108">Microsoft Defender for Endpoint unter Linux ist jetzt in der Vorschau für Us Government-Kunden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="cd94c-108">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="cd94c-109">Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint for US Government customers](gov.md).</span><span class="sxs-lookup"><span data-stu-id="cd94c-109">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="cd94c-110">Es wurde ein Problem behoben, bei dem die Verwendung von Microsoft Defender for Endpoint unter Linux auf Systemen mit DENOE-Dateisystemen dazu führte, dass das Betriebssystem hängte.</span><span class="sxs-lookup"><span data-stu-id="cd94c-110">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="cd94c-111">Leistungsverbesserungen & anderen Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="cd94c-111">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="cd94c-112">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="cd94c-112">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="cd94c-113">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="cd94c-113">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="cd94c-114">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="cd94c-114">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="cd94c-115">Leistungsverbesserung für die Situation, dass ein ganzer Bereitstellungspunkt zur Liste der Antivirenausschlüsse hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="cd94c-115">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="cd94c-116">Vor dieser Version wurde die Dateiaktivität, die vom Bereitstellungspunkt stammt, noch vom Produkt verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="cd94c-116">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="cd94c-117">Ab dieser Version wird die Dateiaktivität für ausgeschlossene Bereitstellungspunkte unterdrückt, was zu einer besseren Produktleistung führt.</span><span class="sxs-lookup"><span data-stu-id="cd94c-117">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="cd94c-118">Dem Befehlszeilentool wurde eine neue Option hinzugefügt, um Informationen zum letzten On-Demand-Scan anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="cd94c-118">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="cd94c-119">Führen Sie zum Anzeigen von Informationen zum letzten Bedarfsscan aus `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="cd94c-119">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="cd94c-120">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="cd94c-120">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="cd94c-121">101.18.53</span><span class="sxs-lookup"><span data-stu-id="cd94c-121">101.18.53</span></span>

- <span data-ttu-id="cd94c-122">EDR für Linux ist jetzt [allgemein verfügbar](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="cd94c-122">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="cd94c-123">Ein neuer Befehlszeilenschalter ( ) wurde hinzugefügt, `--ignore-exclusions` um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="cd94c-123">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="cd94c-124">Erweitert mit einem neuen Parameter ( ), der das Speichern der Diagnoseprotokolle `mdatp diagnostic create` in einem anderen Verzeichnis `--path [directory]` ermöglicht</span><span class="sxs-lookup"><span data-stu-id="cd94c-124">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="cd94c-125">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="cd94c-125">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="cd94c-126">101.12.99</span><span class="sxs-lookup"><span data-stu-id="cd94c-126">101.12.99</span></span>

- <span data-ttu-id="cd94c-127">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="cd94c-127">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="cd94c-128">101.04.76</span><span class="sxs-lookup"><span data-stu-id="cd94c-128">101.04.76</span></span>

- <span data-ttu-id="cd94c-129">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="cd94c-129">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="cd94c-130">101.03.48</span><span class="sxs-lookup"><span data-stu-id="cd94c-130">101.03.48</span></span>

- <span data-ttu-id="cd94c-131">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="cd94c-131">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="cd94c-132">101.02.55</span><span class="sxs-lookup"><span data-stu-id="cd94c-132">101.02.55</span></span>

- <span data-ttu-id="cd94c-133">Ein Problem wurde behoben, bei dem das Produkt nach einem Neustart/Upgrade manchmal nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="cd94c-133">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="cd94c-134">Behebung eines Problems, bei dem Proxyeinstellungen nicht über Produktupgrades hinweg beibehalten wurden</span><span class="sxs-lookup"><span data-stu-id="cd94c-134">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="cd94c-135">101.00.75</span><span class="sxs-lookup"><span data-stu-id="cd94c-135">101.00.75</span></span>

- <span data-ttu-id="cd94c-136">Unterstützung für die folgenden Dateisystemtypen hinzugefügt: `ecryptfs` , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` und `vfat`</span><span class="sxs-lookup"><span data-stu-id="cd94c-136">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="cd94c-137">Neue Syntax für [das Befehlszeilentool](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="cd94c-137">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="cd94c-138">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="cd94c-138">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="cd94c-139">100.90.70</span><span class="sxs-lookup"><span data-stu-id="cd94c-139">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="cd94c-140">Beim Upgrade des installierten Pakets von einer Produktversion vor 100.90.70 kann das Update bei Red Hat- und SLES-Verteilungen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="cd94c-140">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="cd94c-141">Dies liegt an einer wesentlichen Änderung in einem Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="cd94c-141">This is because of a major change in a file path.</span></span> <span data-ttu-id="cd94c-142">Eine temporäre Lösung besteht in der Entfernung des älteren Pakets und anschließender Installation des neueren Pakets.</span><span class="sxs-lookup"><span data-stu-id="cd94c-142">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="cd94c-143">Dieses Problem ist in neueren Versionen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="cd94c-143">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="cd94c-144">[Antivirusausschlüsse unterstützen jetzt Platzhalter](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="cd94c-144">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="cd94c-145">Die Möglichkeit zur Problembehandlung [bei Leistungsproblemen wurde](linux-support-perf.md) über das `mdatp` Befehlszeilentool hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="cd94c-145">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="cd94c-146">Verbesserungen, um die Paketinstallation robuster zu machen</span><span class="sxs-lookup"><span data-stu-id="cd94c-146">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="cd94c-147">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="cd94c-147">Performance improvements & bug fixes</span></span>
