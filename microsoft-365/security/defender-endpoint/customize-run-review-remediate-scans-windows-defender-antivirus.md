---
title: Ausführen und Anpassen geplanter und bei Bedarf durchgeführter Scans
description: Anpassen und Initiieren von Microsoft Defender Antivirus-Scans auf Endpunkten im gesamten Netzwerk.
keywords: Scannen, Planen, Anpassen, Ausschlüsse, Ausschließen von Dateien, Korrektur, Scanergebnisse, Quarantäne, Bedrohung entfernen, Schnellscan, vollständige Überprüfung, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: f3e0cc7ffccf02e24b9746d539a44d3a72810ead
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51765671"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a><span data-ttu-id="5c958-104">Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus-Scans & Korrektur</span><span class="sxs-lookup"><span data-stu-id="5c958-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans & remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5c958-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="5c958-105">**Applies to:**</span></span>

- [<span data-ttu-id="5c958-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="5c958-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="5c958-107">Sie können Gruppenrichtlinien, PowerShell und Windows Management Instrumentation (WMI) verwenden, um Microsoft Defender Antivirus-Scans zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="5c958-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="5c958-108">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="5c958-108">In this section</span></span>

| <span data-ttu-id="5c958-109">Artikel</span><span class="sxs-lookup"><span data-stu-id="5c958-109">Article</span></span> | <span data-ttu-id="5c958-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="5c958-110">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="5c958-111">Konfigurieren und Überprüfen von Datei-, Ordner- und prozess geöffneten Dateiausschlüssen in Microsoft Defender Antivirus-Scans</span><span class="sxs-lookup"><span data-stu-id="5c958-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="5c958-112">Sie können Dateien (einschließlich Dateien, die von bestimmten Prozessen geändert wurden) und Ordner von Bedarfsscans, geplanten Scans und der Überwachung und Überprüfung des Immer-On-Schutzes in Echtzeit ausschließen.</span><span class="sxs-lookup"><span data-stu-id="5c958-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span> |
|[<span data-ttu-id="5c958-113">Konfigurieren von Microsoft Defender Antivirus-Überprüfungsoptionen</span><span class="sxs-lookup"><span data-stu-id="5c958-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="5c958-114">Sie können Microsoft Defender Antivirus so konfigurieren, dass bestimmte Typen von E-Mail-Speicherdateien, Back-up- oder Reparse-Punkte und archivierte Dateien (z. B. ZIP-Dateien) in Scans enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="5c958-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="5c958-115">Sie können auch die Überprüfung von Netzwerkdatei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="5c958-115">You can also enable network file scanning</span></span> |
|[<span data-ttu-id="5c958-116">Konfigurieren der Korrektur für Scans</span><span class="sxs-lookup"><span data-stu-id="5c958-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="5c958-117">Konfigurieren, was Microsoft Defender Antivirus beim Erkennen einer Bedrohung tun soll und wie lange isolierte Dateien im Quarantäneordner aufbewahrt werden sollen</span><span class="sxs-lookup"><span data-stu-id="5c958-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span> |
|[<span data-ttu-id="5c958-118">Konfigurieren geplanter Scans</span><span class="sxs-lookup"><span data-stu-id="5c958-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="5c958-119">Einrichten von wiederkehrenden (geplanten) Scans, einschließlich der Ausführung und der Ausführung als vollständige oder schnelle Scans</span><span class="sxs-lookup"><span data-stu-id="5c958-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span> |
|[<span data-ttu-id="5c958-120">Konfigurieren und Ausführen von Scans</span><span class="sxs-lookup"><span data-stu-id="5c958-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="5c958-121">Ausführen und Konfigurieren von Bedarfsscans mithilfe von PowerShell, Windows Management Instrumentation oder einzeln auf Endpunkten mit der Windows Security App</span><span class="sxs-lookup"><span data-stu-id="5c958-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span> |
|[<span data-ttu-id="5c958-122">Überprüfen der Scanergebnisse</span><span class="sxs-lookup"><span data-stu-id="5c958-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="5c958-123">Überprüfen der Ergebnisse von Scans mit Microsoft Endpoint Configuration Manager, Microsoft Intune oder der Windows Security App</span><span class="sxs-lookup"><span data-stu-id="5c958-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span> |