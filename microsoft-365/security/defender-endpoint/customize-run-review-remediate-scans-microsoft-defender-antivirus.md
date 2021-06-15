---
title: Führen Sie geplante scans und Bedarfsscans aus, und passen Sie sie an.
description: Anpassen und Initiieren Microsoft Defender Antivirus Scans auf Endpunkten in Ihrem Netzwerk
keywords: Scannen, planen, anpassen, Ausschlüsse, Dateien ausschließen, Korrektur, Scanergebnisse, Quarantäne, Bedrohung entfernen, Schnellscan, vollständiger Scan, Microsoft Defender Antivirus
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: bce3fe1b6490803cb571a1a8a2387c19cc589114
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926247"
---
# <a name="customize-initiate-and-review-the-results-of-microsoft-defender-antivirus-scans-and-remediation"></a><span data-ttu-id="0f53a-104">Anpassen, Initiieren und Überprüfen der Ergebnisse von Microsoft Defender Antivirus Überprüfungen und Korrekturen</span><span class="sxs-lookup"><span data-stu-id="0f53a-104">Customize, initiate, and review the results of Microsoft Defender Antivirus scans and remediation</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0f53a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0f53a-105">**Applies to:**</span></span>

- [<span data-ttu-id="0f53a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0f53a-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="0f53a-107">Sie können Gruppenrichtlinien, PowerShell und Windows-Verwaltungsinstrumentation (WMI) verwenden, um Microsoft Defender Antivirus Scans zu konfigurieren.</span><span class="sxs-lookup"><span data-stu-id="0f53a-107">You can use Group Policy, PowerShell, and Windows Management Instrumentation (WMI) to configure Microsoft Defender Antivirus scans.</span></span> 

## <a name="in-this-section"></a><span data-ttu-id="0f53a-108">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="0f53a-108">In this section</span></span>

<span data-ttu-id="0f53a-109">Thema</span><span class="sxs-lookup"><span data-stu-id="0f53a-109">Topic</span></span> | <span data-ttu-id="0f53a-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0f53a-110">Description</span></span>
---|---
[<span data-ttu-id="0f53a-111">Konfigurieren und Überprüfen von Datei-, Ordner- und prozesseröffnten Dateiausschlüssen in Microsoft Defender Antivirus Scans</span><span class="sxs-lookup"><span data-stu-id="0f53a-111">Configure and validate file, folder, and process-opened file exclusions in Microsoft Defender Antivirus scans</span></span>](configure-exclusions-microsoft-defender-antivirus.md) | <span data-ttu-id="0f53a-112">Sie können Dateien (einschließlich Dateien, die von angegebenen Prozessen geändert wurden) und Ordner von Bedarfsscans, geplanten Scans und always-on-Echtzeitschutzüberwachung und -überprüfung ausschließen.</span><span class="sxs-lookup"><span data-stu-id="0f53a-112">You can exclude files (including files modified by specified processes) and folders from on-demand scans, scheduled scans, and always-on real-time protection monitoring and scanning</span></span>
[<span data-ttu-id="0f53a-113">Konfigurieren der Scanoptionen von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0f53a-113">Configure Microsoft Defender Antivirus scanning options</span></span>](configure-advanced-scan-types-microsoft-defender-antivirus.md) | <span data-ttu-id="0f53a-114">Sie können Microsoft Defender Antivirus so konfigurieren, dass bestimmte Typen von E-Mail-Speicherdateien, Sicherungs- oder Analysepunkte und archivierte Dateien (z. B. .zip Dateien) in Scans einbezogen werden.</span><span class="sxs-lookup"><span data-stu-id="0f53a-114">You can configure Microsoft Defender Antivirus to include certain types of email storage files, back-up or reparse points, and archived files (such as .zip files) in scans.</span></span> <span data-ttu-id="0f53a-115">Sie können auch die Netzwerkdateiüberprüfung aktivieren.</span><span class="sxs-lookup"><span data-stu-id="0f53a-115">You can also enable network file scanning</span></span>
[<span data-ttu-id="0f53a-116">Konfigurieren der Problembehebung für Scans</span><span class="sxs-lookup"><span data-stu-id="0f53a-116">Configure remediation for scans</span></span>](configure-remediation-microsoft-defender-antivirus.md) | <span data-ttu-id="0f53a-117">Konfigurieren, was Microsoft Defender Antivirus tun sollten, wenn eine Bedrohung erkannt wird und wie lange isolierte Dateien im Quarantäneordner aufbewahrt werden sollen</span><span class="sxs-lookup"><span data-stu-id="0f53a-117">Configure what Microsoft Defender Antivirus should do when it detects a threat, and how long quarantined files should be retained in the quarantine folder</span></span>
[<span data-ttu-id="0f53a-118">Konfigurieren von geplanten Scans</span><span class="sxs-lookup"><span data-stu-id="0f53a-118">Configure scheduled scans</span></span>](scheduled-catch-up-scans-microsoft-defender-antivirus.md) | <span data-ttu-id="0f53a-119">Einrichten von wiederkehrenden (geplanten) Scans, z. B. wann sie ausgeführt werden sollen und ob sie als vollständige oder schnelle Scans ausgeführt werden sollen</span><span class="sxs-lookup"><span data-stu-id="0f53a-119">Set up recurring (scheduled) scans, including when they should run and whether they run as full or quick scans</span></span>
[<span data-ttu-id="0f53a-120">Konfigurieren und Ausführen von Scans</span><span class="sxs-lookup"><span data-stu-id="0f53a-120">Configure and run scans</span></span>](run-scan-microsoft-defender-antivirus.md) | <span data-ttu-id="0f53a-121">Ausführen und Konfigurieren von Scans bei Bedarf mithilfe von PowerShell, Windows Verwaltungsinstrumentation oder einzeln auf Endpunkten mit der Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="0f53a-121">Run and configure on-demand scans using PowerShell, Windows Management Instrumentation, or individually on endpoints with the Windows Security app</span></span>
[<span data-ttu-id="0f53a-122">Überprüfen der Scanergebnisse</span><span class="sxs-lookup"><span data-stu-id="0f53a-122">Review scan results</span></span>](review-scan-results-microsoft-defender-antivirus.md) | <span data-ttu-id="0f53a-123">Überprüfen der Ergebnisse von Scans mit Microsoft Endpoint Configuration Manager, Microsoft Intune oder der Windows-Sicherheit-App</span><span class="sxs-lookup"><span data-stu-id="0f53a-123">Review the results of scans using  Microsoft Endpoint Configuration Manager, Microsoft Intune, or the Windows Security app</span></span>