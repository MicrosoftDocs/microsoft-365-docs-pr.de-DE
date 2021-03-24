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
ms.openlocfilehash: 43324b0f3a0d5d351d7164bb05415899bf7d181c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51062448"
---
# <a name="whats-new-in-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="5cce7-104">Neues in Microsoft Defender for Endpoint für Linux</span><span class="sxs-lookup"><span data-stu-id="5cce7-104">What's new in Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

## <a name="1011853"></a><span data-ttu-id="5cce7-105">101.18.53</span><span class="sxs-lookup"><span data-stu-id="5cce7-105">101.18.53</span></span>

- <span data-ttu-id="5cce7-106">EDR für Linux ist jetzt [allgemein verfügbar](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span><span class="sxs-lookup"><span data-stu-id="5cce7-106">EDR for Linux is now [generally available](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/edr-for-linux-is-now-is-generally-available/ba-p/2048539)</span></span>
- <span data-ttu-id="5cce7-107">Ein neuer Befehlszeilenschalter ( ) wurde hinzugefügt, `--ignore-exclusions` um AV-Ausschlüsse während benutzerdefinierter Scans zu ignorieren ( `mdatp scan custom` )</span><span class="sxs-lookup"><span data-stu-id="5cce7-107">Added a new command-line switch (`--ignore-exclusions`) to ignore AV exclusions during custom scans (`mdatp scan custom`)</span></span>
- <span data-ttu-id="5cce7-108">Erweitert mit einem neuen Parameter ( ), der das Speichern der Diagnoseprotokolle `mdatp diagnostic create` in einem anderen Verzeichnis `--path [directory]` ermöglicht</span><span class="sxs-lookup"><span data-stu-id="5cce7-108">Extended `mdatp diagnostic create` with a new parameter (`--path [directory]`) that allows the diagnostic logs to be saved to a different directory</span></span>
- <span data-ttu-id="5cce7-109">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5cce7-109">Performance improvements & bug fixes</span></span>

## <a name="1011299"></a><span data-ttu-id="5cce7-110">101.12.99</span><span class="sxs-lookup"><span data-stu-id="5cce7-110">101.12.99</span></span>

- <span data-ttu-id="5cce7-111">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5cce7-111">Performance improvements & bug fixes</span></span>

## <a name="1010476"></a><span data-ttu-id="5cce7-112">101.04.76</span><span class="sxs-lookup"><span data-stu-id="5cce7-112">101.04.76</span></span>

- <span data-ttu-id="5cce7-113">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5cce7-113">Bug fixes</span></span>

## <a name="1010348"></a><span data-ttu-id="5cce7-114">101.03.48</span><span class="sxs-lookup"><span data-stu-id="5cce7-114">101.03.48</span></span>

- <span data-ttu-id="5cce7-115">Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5cce7-115">Bug fixes</span></span>

## <a name="1010255"></a><span data-ttu-id="5cce7-116">101.02.55</span><span class="sxs-lookup"><span data-stu-id="5cce7-116">101.02.55</span></span>

- <span data-ttu-id="5cce7-117">Ein Problem wurde behoben, bei dem das Produkt nach einem Neustart/Upgrade manchmal nicht gestartet wurde.</span><span class="sxs-lookup"><span data-stu-id="5cce7-117">Fixed an issue where the product sometimes does not start following a reboot / upgrade</span></span>
- <span data-ttu-id="5cce7-118">Behebung eines Problems, bei dem Proxyeinstellungen nicht über Produktupgrades hinweg beibehalten wurden</span><span class="sxs-lookup"><span data-stu-id="5cce7-118">Fixed an issue where proxy settings are not persisted across product upgrades</span></span>

## <a name="1010075"></a><span data-ttu-id="5cce7-119">101.00.75</span><span class="sxs-lookup"><span data-stu-id="5cce7-119">101.00.75</span></span>

- <span data-ttu-id="5cce7-120">Unterstützung für die folgenden Dateisystemtypen hinzugefügt: `ecryptfs` , , , , , , , , `fuse` , `fuseblk` `jfs` `nfs` `overlay` `ramfs` `reiserfs` `udf` und `vfat`</span><span class="sxs-lookup"><span data-stu-id="5cce7-120">Added support for the following file system types: `ecryptfs`, `fuse`, `fuseblk`, `jfs`, `nfs`, `overlay`, `ramfs`, `reiserfs`, `udf`, and `vfat`</span></span>
- <span data-ttu-id="5cce7-121">Neue Syntax für [das Befehlszeilentool](linux-resources.md#configure-from-the-command-line).</span><span class="sxs-lookup"><span data-stu-id="5cce7-121">New syntax for the [command-line tool](linux-resources.md#configure-from-the-command-line).</span></span>
- <span data-ttu-id="5cce7-122">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5cce7-122">Performance improvements & bug fixes</span></span>

## <a name="1009070"></a><span data-ttu-id="5cce7-123">100.90.70</span><span class="sxs-lookup"><span data-stu-id="5cce7-123">100.90.70</span></span>

> [!WARNING]
> <span data-ttu-id="5cce7-124">Beim Upgrade des installierten Pakets von einer Produktversion vor 100.90.70 kann das Update bei Red Hat- und SLES-Verteilungen fehlschlagen.</span><span class="sxs-lookup"><span data-stu-id="5cce7-124">When upgrading the installed package from a product version earlier than 100.90.70, the update may fail on Red Hat-based and SLES distributions.</span></span> <span data-ttu-id="5cce7-125">Dies liegt an einer wesentlichen Änderung in einem Dateipfad.</span><span class="sxs-lookup"><span data-stu-id="5cce7-125">This is because of a major change in a file path.</span></span> <span data-ttu-id="5cce7-126">Eine temporäre Lösung besteht in der Entfernung des älteren Pakets und anschließender Installation des neueren Pakets.</span><span class="sxs-lookup"><span data-stu-id="5cce7-126">A temporary solution is to remove the older package, and then install the newer one.</span></span> <span data-ttu-id="5cce7-127">Dieses Problem ist in neueren Versionen nicht vorhanden.</span><span class="sxs-lookup"><span data-stu-id="5cce7-127">This issue does not exist in newer versions.</span></span>

- <span data-ttu-id="5cce7-128">[Antivirusausschlüsse unterstützen jetzt Platzhalter](linux-exclusions.md#supported-exclusion-types)</span><span class="sxs-lookup"><span data-stu-id="5cce7-128">Antivirus [exclusions now support wildcards](linux-exclusions.md#supported-exclusion-types)</span></span>
- <span data-ttu-id="5cce7-129">Die Möglichkeit zur Problembehandlung [bei Leistungsproblemen wurde](linux-support-perf.md) über das `mdatp` Befehlszeilentool hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5cce7-129">Added the ability to [troubleshoot performance issues](linux-support-perf.md) through the `mdatp` command-line tool</span></span>
- <span data-ttu-id="5cce7-130">Verbesserungen, um die Paketinstallation robuster zu machen</span><span class="sxs-lookup"><span data-stu-id="5cce7-130">Improvements to make the package installation more robust</span></span>
- <span data-ttu-id="5cce7-131">Leistungsverbesserungen & Fehlerbehebungen</span><span class="sxs-lookup"><span data-stu-id="5cce7-131">Performance improvements & bug fixes</span></span>
