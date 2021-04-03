---
title: Neues in Microsoft Defender for Endpoint für Linux
description: Liste der wichtigsten Änderungen für Microsoft Defender ATP für Linux.
keywords: microsoft, defender, atp, linux, whatsnew, release
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
ms.openlocfilehash: 02a446f47ce4292b214c868e773802c53f7e3353
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51581002"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="11049-104">Neues in Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="11049-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012563-30121022125630"></a><span data-ttu-id="11049-105">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="11049-105">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="11049-106">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="11049-106">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="11049-107">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="11049-107">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="11049-108">Leistungsverbesserung für die Situation, dass ein ganzer Bereitstellungspunkt zur Liste der Antivirenausschlüsse hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="11049-108">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="11049-109">Vor dieser Version wurde die Dateiaktivität, die vom Bereitstellungspunkt stammt, noch vom Produkt verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="11049-109">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="11049-110">Ab dieser Version wird die Dateiaktivität für ausgeschlossene Bereitstellungspunkte unterdrückt, was zu einer besseren Produktleistung führt.</span><span class="sxs-lookup"><span data-stu-id="11049-110">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="11049-111">Dem Befehlszeilentool wurde eine neue Option hinzugefügt, um Informationen zum letzten On-Demand-Scan anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="11049-111">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="11049-112">Führen Sie zum Anzeigen von Informationen zum letzten Bedarfsscan aus `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="11049-112">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="11049-113">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="11049-113">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="11049-114">101.18.53</span><span class="sxs-lookup"><span data-stu-id="11049-114">101.18.53</span></span>

- <span data-ttu-id="11049-115">EDR für Linux ist jetzt [allgemein verfügbar](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="11049-115">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="11049-116">Ein neuer Befehlszeilenschalter ( ) wurde hinzugefügt, `--ignore-exclusions` um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="11049-116">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="11049-117">Erweitert mit einem neuen Parameter ( ), der das Speichern der Diagnoseprotokolle `mdatp diagnostic create` in einem anderen Verzeichnis `--path [directory]` ermöglicht</span><span class="sxs-lookup"><span data-stu-id="11049-117">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="11049-118">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="11049-118">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="11049-119">101.12.99</span><span class="sxs-lookup"><span data-stu-id="11049-119">101.12.99</span></span>

- <span data-ttu-id="11049-120">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="11049-120">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="11049-121">101.04.76</span><span class="sxs-lookup"><span data-stu-id="11049-121">101.04.76</span></span>

- <span data-ttu-id="11049-122">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="11049-122">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="11049-123">101.03.48</span><span class="sxs-lookup"><span data-stu-id="11049-123">101.03.48</span></span>

- <span data-ttu-id="11049-124">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="11049-124">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="11049-125">101.02.55</span><span class="sxs-lookup"><span data-stu-id="11049-125">101.02.55</span></span>

- <span data-ttu-id="11049-126">Ein Problem wurde behoben, bei dem das Produkt nach einem Neustart/Upgrade manchmal nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="11049-126">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="11049-127">Behebung eines Problems, bei dem Proxyeinstellungen nicht über Produktupgrades hinweg beibehalten wurden</span><span class="sxs-lookup"><span data-stu-id="11049-127">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="11049-128">101.00.75</span><span class="sxs-lookup"><span data-stu-id="11049-128">101.00.75</span></span>

- <span data-ttu-id="11049-129">Unterstützung für die folgenden Dateisystemtypen hinzugefügt: `ecryptfs` , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` und `vfat`</span><span class="sxs-lookup"><span data-stu-id="11049-129">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="11049-130">Neue Syntax für [das Befehlszeilentool](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="11049-130">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="11049-131">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="11049-131">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="11049-132">100.90.70</span><span class="sxs-lookup"><span data-stu-id="11049-132">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="11049-133">Beim Upgrade des installierten Pakets von einer Produktversion vor 100.90.70 kann das Update bei Red Hat- und SLES-Verteilungen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="11049-133">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="11049-134">Dies liegt an einer wesentlichen Änderung in einem Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="11049-134">This is because of a major change in a file path.</span></span> <span data-ttu-id="11049-135">Eine temporäre Lösung besteht in der Entfernung des älteren Pakets und anschließender Installation des neueren Pakets.</span><span class="sxs-lookup"><span data-stu-id="11049-135">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="11049-136">Dieses Problem ist in neueren Versionen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="11049-136">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="11049-137">[Antivirusausschlüsse unterstützen jetzt Platzhalter](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="11049-137">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="11049-138">Die Möglichkeit zur Problembehandlung [bei Leistungsproblemen wurde](linux-support-perf.md) über das `mdatp` Befehlszeilentool hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="11049-138">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="11049-139">Verbesserungen, um die Paketinstallation robuster zu machen</span><span class="sxs-lookup"><span data-stu-id="11049-139">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="11049-140">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="11049-140">Performance improvements & bug fixes</span></span>
