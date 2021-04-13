---
title: Ausführen und Anpassen geplanter und bei Bedarf durchgeführter Scans
description: Anpassen und Initiieren von Microsoft Defender Antivirus-Scans auf Endpunkten im gesamten Netzwerk.
keywords: Scannen, Planen, Anpassen, Ausschlüsse, Ausschließen von Dateien, Korrektur, Scanergebnisse, Quarantäne, Bedrohung entfernen, Schnellscan, vollständige Überprüfung, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 5f8e5606b01186e31a58f6d506b5898f20b63511
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690281"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans--remediation"></a><span data-ttu-id="54e7a-104">Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus-Scans & Korrektur</span><span class="sxs-lookup"><span data-stu-id="54e7a-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans & remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="54e7a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="54e7a-105">**Applies to:**</span></span>

- [<span data-ttu-id="54e7a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="54e7a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="54e7a-107">Sie können Gruppenrichtlinien, PowerShell und Windows Management Instrumentation (WMI) verwenden, um Microsoft Defender Antivirus-Scans zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="54e7a-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="54e7a-108">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="54e7a-108">In this section</span></span>

| <span data-ttu-id="54e7a-109">Artikel</span><span class="sxs-lookup"><span data-stu-id="54e7a-109">Article</span></span> | <span data-ttu-id="54e7a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="54e7a-110">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="54e7a-111">Konfigurieren und Überprüfen von Datei-, Ordner- und prozess geöffneten Dateiausschlüssen in Microsoft Defender Antivirus-Scans</span><span class="sxs-lookup"><span data-stu-id="54e7a-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="54e7a-112">Sie können Dateien (einschließlich Dateien, die von bestimmten Prozessen geändert wurden) und Ordner von Bedarfsscans, geplanten Scans und der Überwachung und Überprüfung des Immer-On-Schutzes in Echtzeit ausschließen.</span><span class="sxs-lookup"><span data-stu-id="54e7a-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span> |
|[<span data-ttu-id="54e7a-113">Konfigurieren von Microsoft Defender Antivirus-Überprüfungsoptionen</span><span class="sxs-lookup"><span data-stu-id="54e7a-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="54e7a-114">Sie können Microsoft Defender Antivirus so konfigurieren, dass bestimmte Typen von E-Mail-Speicherdateien, Back-up- oder Reparse-Punkte und archivierte Dateien (z. B. ZIP-Dateien) in Scans enthalten sind.</span><span class="sxs-lookup"><span data-stu-id="54e7a-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="54e7a-115">Sie können auch die Überprüfung von Netzwerkdatei aktivieren.</span><span class="sxs-lookup"><span data-stu-id="54e7a-115">You can also enable network file scanning</span></span> |
|[<span data-ttu-id="54e7a-116">Konfigurieren der Korrektur für Scans</span><span class="sxs-lookup"><span data-stu-id="54e7a-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="54e7a-117">Konfigurieren, was Microsoft Defender Antivirus beim Erkennen einer Bedrohung tun soll und wie lange isolierte Dateien im Quarantäneordner aufbewahrt werden sollen</span><span class="sxs-lookup"><span data-stu-id="54e7a-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span> |
|[<span data-ttu-id="54e7a-118">Konfigurieren geplanter Scans</span><span class="sxs-lookup"><span data-stu-id="54e7a-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="54e7a-119">Einrichten von wiederkehrenden (geplanten) Scans, einschließlich der Ausführung und der Ausführung als vollständige oder schnelle Scans</span><span class="sxs-lookup"><span data-stu-id="54e7a-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span> |
|[<span data-ttu-id="54e7a-120">Konfigurieren und Ausführen von Scans</span><span class="sxs-lookup"><span data-stu-id="54e7a-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="54e7a-121">Ausführen und Konfigurieren von Bedarfsscans mithilfe von PowerShell, Windows Management Instrumentation oder einzeln auf Endpunkten mit der Windows Security App</span><span class="sxs-lookup"><span data-stu-id="54e7a-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span> |
|[<span data-ttu-id="54e7a-122">Überprüfen der Scanergebnisse</span><span class="sxs-lookup"><span data-stu-id="54e7a-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="54e7a-123">Überprüfen der Ergebnisse von Scans mit Microsoft Endpoint Configuration Manager, Microsoft Intune oder der Windows Security App</span><span class="sxs-lookup"><span data-stu-id="54e7a-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span> |