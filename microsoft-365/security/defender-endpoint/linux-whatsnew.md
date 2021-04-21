---
title: Neues in Microsoft Defender for Endpoint unter Linux
description: Liste der wichtigsten Änderungen für Microsoft Defender for Endpoint unter Linux.
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
ms.openlocfilehash: 999463f92c014e061bc4e2fdc22eedcd8f680a72
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903814"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="5b8ca-104">Neues in Microsoft Defender for Endpoint unter Linux</span><span class="sxs-lookup"><span data-stu-id="5b8ca-104">What's new in Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1012572-30121022125630"></a><span data-ttu-id="5b8ca-105">101.25.72 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-105">101.25.72 (30.121022.12563.0)</span></span>

- <span data-ttu-id="5b8ca-106">Microsoft Defender for Endpoint unter Linux ist jetzt in der Vorschau für Us Government-Kunden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-106">Microsoft Defender for Endpoint on Linux is now available in preview for US Government customers.</span></span> <span data-ttu-id="5b8ca-107">Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint for US Government customers](gov.md).</span><span class="sxs-lookup"><span data-stu-id="5b8ca-107">For more information, see [Microsoft Defender for Endpoint for US Government customers](gov.md).</span></span>
- <span data-ttu-id="5b8ca-108">Es wurde ein Problem behoben, bei dem die Verwendung von Microsoft Defender for Endpoint unter Linux auf Systemen mit DENOE-Dateisystemen dazu führte, dass das Betriebssystem hängte.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-108">Fixed an issue where usage of Microsoft Defender for Endpoint on Linux on systems with FUSE filesystems was leading to OS hang</span></span>
- <span data-ttu-id="5b8ca-109">Leistungsverbesserungen & anderen Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5b8ca-109">Performance improvements & other bug fixes</span></span>

## <a name="1012563-30121022125630"></a><span data-ttu-id="5b8ca-110">101.25.63 (30.121022.12563.0)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-110">101.25.63 (30.121022.12563.0)</span></span>

- <span data-ttu-id="5b8ca-111">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5b8ca-111">Performance improvements & bug fixes</span></span>

## <a name="1012364-30121021123640"></a><span data-ttu-id="5b8ca-112">101.23.64 (30.121021.12364.0)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-112">101.23.64 (30.121021.12364.0)</span></span>

- <span data-ttu-id="5b8ca-113">Leistungsverbesserung für die Situation, dass ein ganzer Bereitstellungspunkt zur Liste der Antivirenausschlüsse hinzugefügt wird.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-113">Performance improvement for the situation where an entire mount point is added to the antivirus exclusion list.</span></span> <span data-ttu-id="5b8ca-114">Vor dieser Version wurde die Dateiaktivität, die vom Bereitstellungspunkt stammt, noch vom Produkt verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-114">Prior to this version, file activity originating from the mount point was still processed by the product.</span></span> <span data-ttu-id="5b8ca-115">Ab dieser Version wird die Dateiaktivität für ausgeschlossene Bereitstellungspunkte unterdrückt, was zu einer besseren Produktleistung führt.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-115">Starting with this version, file activity for excluded mount points is suppressed, leading to better product performance</span></span>
- <span data-ttu-id="5b8ca-116">Dem Befehlszeilentool wurde eine neue Option hinzugefügt, um Informationen zum letzten On-Demand-Scan anzeigen zu können.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-116">Added a new option to the command-line tool to view information about the last on-demand scan.</span></span> <span data-ttu-id="5b8ca-117">Führen Sie zum Anzeigen von Informationen zum letzten Bedarfsscan aus `mdatp health --details antivirus`</span><span class="sxs-lookup"><span data-stu-id="5b8ca-117">To view information about the last on-demand scan, run `mdatp health --details antivirus`</span></span>
- <span data-ttu-id="5b8ca-118">Weitere Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5b8ca-118">Other performance improvements & bug fixes</span></span>

## <a name="1011853"></a><span data-ttu-id="5b8ca-119">101.18.53</span><span class="sxs-lookup"><span data-stu-id="5b8ca-119">101.18.53</span></span>

- <span data-ttu-id="5b8ca-120">EDR für Linux ist jetzt [allgemein verfügbar](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-120">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="5b8ca-121">Ein neuer Befehlszeilenschalter ( ) wurde hinzugefügt, `--ignore-exclusions` um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="5b8ca-121">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="5b8ca-122">Erweitert mit einem neuen Parameter ( ), der das Speichern der Diagnoseprotokolle `mdatp diagnostic create` in einem anderen Verzeichnis `--path [directory]` ermöglicht</span><span class="sxs-lookup"><span data-stu-id="5b8ca-122">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="5b8ca-123">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5b8ca-123">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="5b8ca-124">101.12.99</span><span class="sxs-lookup"><span data-stu-id="5b8ca-124">101.12.99</span></span>

- <span data-ttu-id="5b8ca-125">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5b8ca-125">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="5b8ca-126">101.04.76</span><span class="sxs-lookup"><span data-stu-id="5b8ca-126">101.04.76</span></span>

- <span data-ttu-id="5b8ca-127">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5b8ca-127">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="5b8ca-128">101.03.48</span><span class="sxs-lookup"><span data-stu-id="5b8ca-128">101.03.48</span></span>

- <span data-ttu-id="5b8ca-129">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5b8ca-129">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="5b8ca-130">101.02.55</span><span class="sxs-lookup"><span data-stu-id="5b8ca-130">101.02.55</span></span>

- <span data-ttu-id="5b8ca-131">Ein Problem wurde behoben, bei dem das Produkt nach einem Neustart/Upgrade manchmal nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-131">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="5b8ca-132">Behebung eines Problems, bei dem Proxyeinstellungen nicht über Produktupgrades hinweg beibehalten wurden</span><span class="sxs-lookup"><span data-stu-id="5b8ca-132">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="5b8ca-133">101.00.75</span><span class="sxs-lookup"><span data-stu-id="5b8ca-133">101.00.75</span></span>

- <span data-ttu-id="5b8ca-134">Unterstützung für die folgenden Dateisystemtypen hinzugefügt: `ecryptfs` , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` und `vfat`</span><span class="sxs-lookup"><span data-stu-id="5b8ca-134">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="5b8ca-135">Neue Syntax für [das Befehlszeilentool](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="5b8ca-135">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="5b8ca-136">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5b8ca-136">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="5b8ca-137">100.90.70</span><span class="sxs-lookup"><span data-stu-id="5b8ca-137">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="5b8ca-138">Beim Upgrade des installierten Pakets von einer Produktversion vor 100.90.70 kann das Update bei Red Hat- und SLES-Verteilungen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-138">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="5b8ca-139">Dies liegt an einer wesentlichen Änderung in einem Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-139">This is because of a major change in a file path.</span></span> <span data-ttu-id="5b8ca-140">Eine temporäre Lösung besteht in der Entfernung des älteren Pakets und anschließender Installation des neueren Pakets.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-140">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="5b8ca-141">Dieses Problem ist in neueren Versionen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-141">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="5b8ca-142">[Antivirusausschlüsse unterstützen jetzt Platzhalter](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="5b8ca-142">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="5b8ca-143">Die Möglichkeit zur Problembehandlung [bei Leistungsproblemen wurde](linux-support-perf.md) über das `mdatp` Befehlszeilentool hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5b8ca-143">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="5b8ca-144">Verbesserungen, um die Paketinstallation robuster zu machen</span><span class="sxs-lookup"><span data-stu-id="5b8ca-144">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="5b8ca-145">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5b8ca-145">Performance improvements & bug fixes</span></span>
