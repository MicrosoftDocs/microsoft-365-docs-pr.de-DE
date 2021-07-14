---
title: Verwalten von Windows Defender in Ihrem Unternehmen
description: Erfahren Sie, wie Sie Gruppenrichtlinien, Configuration Manager, PowerShell, WMI, Intune und die Befehlszeile zum Verwalten von Microsoft Defender AV verwenden.
keywords: Gruppenrichtlinie, GPO, Konfigurations-Manager, sccm, scep, powershell, wmi, intune, defender, antivirus, antischadsoftware, Sicherheit, Schutz
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 07/13/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: f9ecade23964db88076347b3a89085b25c1b1538
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415563"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="0bf74-104">Verwalten von Microsoft Defender Antivirus in Ihrem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="0bf74-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="0bf74-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="0bf74-105">**Applies to:**</span></span>

- [<span data-ttu-id="0bf74-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="0bf74-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)
- [<span data-ttu-id="0bf74-107">Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0bf74-107">Microsoft Defender Antivirus</span></span>](/microsoft-365/security/defender-endpoint/microsoft-defender-antivirus-windows)

<span data-ttu-id="0bf74-108">Sie können Microsoft Defender Antivirus mit den folgenden Tools verwalten und konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="0bf74-108">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="0bf74-109">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (jetzt Teil von Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="0bf74-109">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="0bf74-110">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (jetzt Teil von Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="0bf74-110">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="0bf74-111">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="0bf74-111">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0bf74-112">PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0bf74-112">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="0bf74-113">Windows-Verwaltungsinstrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="0bf74-113">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="0bf74-114">Das [Befehlszeilenprogramm](./command-line-arguments-microsoft-defender-antivirus.md) zum Schutz vor Schadsoftware (auch als *hilfsprogrammmpcmdrun.exe* bezeichnet)</span><span class="sxs-lookup"><span data-stu-id="0bf74-114">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="0bf74-115">Die folgenden Artikel enthalten weitere Informationen, Links und Ressourcen für die Verwendung dieser Tools zum Verwalten und Konfigurieren Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="0bf74-115">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="0bf74-116">Artikel</span><span class="sxs-lookup"><span data-stu-id="0bf74-116">Article</span></span> | <span data-ttu-id="0bf74-117">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="0bf74-117">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="0bf74-118">Verwalten von Microsoft Defender Antivirus mit Microsoft Intune und Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="0bf74-118">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="0bf74-119">Informationen zur Verwendung von Intune und Configuration Manager zum Bereitstellen, Verwalten, Melden und Konfigurieren Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0bf74-119">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="0bf74-120">Verwalten von Microsoft Defender Antivirus mit Gruppenrichtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="0bf74-120">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="0bf74-121">Liste aller Gruppenrichtlinieneinstellungen in ADMX-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="0bf74-121">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="0bf74-122">Verwalten von Microsoft Defender Antivirus mit PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="0bf74-122">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="0bf74-123">Anweisungen zur Verwendung von PowerShell-Cmdlets zum Verwalten von Microsoft Defender Antivirus sowie Links zur Dokumentation für alle Cmdlets und zulässigen Parameter</span><span class="sxs-lookup"><span data-stu-id="0bf74-123">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="0bf74-124">Verwalten von Microsoft Defender Antivirus mit Windows-Verwaltungsinstrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="0bf74-124">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="0bf74-125">Anweisungen zur Verwendung von WMI zum Verwalten von Microsoft Defender Antivirus sowie Links zur Dokumentation für die WMIv2-APIs (einschließlich aller Klassen, Methoden und Eigenschaften)</span><span class="sxs-lookup"><span data-stu-id="0bf74-125">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="0bf74-126">Verwalten von Microsoft Defender Antivirus mit dem Befehlszeilentool MpCmdRun.exe</span><span class="sxs-lookup"><span data-stu-id="0bf74-126">Manage Microsoft Defender Antivirus with the MpCmdRun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)| <span data-ttu-id="0bf74-127">Anweisungen zur Verwendung des dedizierten Befehlszeilentools zum Verwalten und Verwenden Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="0bf74-127">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |
