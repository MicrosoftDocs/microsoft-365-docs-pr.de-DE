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
ms.openlocfilehash: dc3d775aced2ea3da42312cbf5a4d5e5af9fae50
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198777"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="a676d-104">Neues in Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="a676d-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012364-30121021123640"></a><span data-ttu-id="a676d-105">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="a676d-105">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="a676d-106">Leistungsverbesserung für die Situation, dass ein ganzer Bereitstellungspunkt zur Liste der Antivirenausschlüsse hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="a676d-106">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="a676d-107">Vor dieser Version wurde die Dateiaktivität, die vom Bereitstellungspunkt stammt, noch vom Produkt verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="a676d-107">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="a676d-108">Ab dieser Version wird die Dateiaktivität für ausgeschlossene Bereitstellungspunkte unterdrückt, was zu einer besseren Produktleistung führt.</span><span class="sxs-lookup"><span data-stu-id="a676d-108">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="a676d-109">Dem Befehlszeilentool wurde eine neue Option hinzugefügt, um Informationen zum letzten On-Demand-Scan anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="a676d-109">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="a676d-110">Führen Sie zum Anzeigen von Informationen zum letzten Bedarfsscan aus `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="a676d-110">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="a676d-111">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="a676d-111">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="a676d-112">101.18.53</span><span class="sxs-lookup"><span data-stu-id="a676d-112">101.18.53</span></span>

- <span data-ttu-id="a676d-113">EDR für Linux ist jetzt [allgemein verfügbar](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="a676d-113">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="a676d-114">Ein neuer Befehlszeilenschalter ( ) wurde hinzugefügt, `--ignore-exclusions` um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="a676d-114">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="a676d-115">Erweitert mit einem neuen Parameter ( ), der das Speichern der Diagnoseprotokolle `mdatp diagnostic create` in einem anderen Verzeichnis `--path [directory]` ermöglicht</span><span class="sxs-lookup"><span data-stu-id="a676d-115">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="a676d-116">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="a676d-116">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="a676d-117">101.12.99</span><span class="sxs-lookup"><span data-stu-id="a676d-117">101.12.99</span></span>

- <span data-ttu-id="a676d-118">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="a676d-118">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="a676d-119">101.04.76</span><span class="sxs-lookup"><span data-stu-id="a676d-119">101.04.76</span></span>

- <span data-ttu-id="a676d-120">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="a676d-120">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="a676d-121">101.03.48</span><span class="sxs-lookup"><span data-stu-id="a676d-121">101.03.48</span></span>

- <span data-ttu-id="a676d-122">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="a676d-122">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="a676d-123">101.02.55</span><span class="sxs-lookup"><span data-stu-id="a676d-123">101.02.55</span></span>

- <span data-ttu-id="a676d-124">Ein Problem wurde behoben, bei dem das Produkt nach einem Neustart/Upgrade manchmal nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="a676d-124">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="a676d-125">Behebung eines Problems, bei dem Proxyeinstellungen nicht über Produktupgrades hinweg beibehalten wurden</span><span class="sxs-lookup"><span data-stu-id="a676d-125">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="a676d-126">101.00.75</span><span class="sxs-lookup"><span data-stu-id="a676d-126">101.00.75</span></span>

- <span data-ttu-id="a676d-127">Unterstützung für die folgenden Dateisystemtypen hinzugefügt: `ecryptfs` , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` und `vfat`</span><span class="sxs-lookup"><span data-stu-id="a676d-127">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="a676d-128">Neue Syntax für [das Befehlszeilentool](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="a676d-128">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="a676d-129">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="a676d-129">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="a676d-130">100.90.70</span><span class="sxs-lookup"><span data-stu-id="a676d-130">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="a676d-131">Beim Upgrade des installierten Pakets von einer Produktversion vor 100.90.70 kann das Update bei Red Hat- und SLES-Verteilungen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="a676d-131">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="a676d-132">Dies liegt an einer wesentlichen Änderung in einem Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="a676d-132">This is because of a major change in a file path.</span></span> <span data-ttu-id="a676d-133">Eine temporäre Lösung besteht in der Entfernung des älteren Pakets und anschließender Installation des neueren Pakets.</span><span class="sxs-lookup"><span data-stu-id="a676d-133">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="a676d-134">Dieses Problem ist in neueren Versionen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="a676d-134">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="a676d-135">[Antivirusausschlüsse unterstützen jetzt Platzhalter](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="a676d-135">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="a676d-136">Die Möglichkeit zur Problembehandlung [bei Leistungsproblemen wurde](linux-support-perf.md) über das `mdatp` Befehlszeilentool hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="a676d-136">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="a676d-137">Verbesserungen, um die Paketinstallation robuster zu machen</span><span class="sxs-lookup"><span data-stu-id="a676d-137">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="a676d-138">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="a676d-138">Performance improvements & bug fixes</span></span>
