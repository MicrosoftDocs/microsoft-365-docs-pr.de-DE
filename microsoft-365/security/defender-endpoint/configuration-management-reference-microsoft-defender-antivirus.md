---
title: Verwalten Windows Defender in Ihrem Unternehmen
description: Informationen zur Verwendung von Gruppenrichtlinien, Configuration Manager, PowerShell, WMI, Intune und der Befehlszeile zum Verwalten von Microsoft Defender AV
keywords: gruppenrichtlinie, gpo, config manager, sccm, scep, powershell, wmi, intune, defender, antivirus, anmalware, security, protection
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 12/16/2020
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: ad3e8d2fb61eb5a2a350d061f926dd7bff8ae109
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/13/2021
ms.locfileid: "51690460"
---
# <a name="manage-microsoft-defender-antivirus-in-your-business"></a><span data-ttu-id="98380-104">Verwalten von Microsoft Defender Antivirus in Ihrem Unternehmen</span><span class="sxs-lookup"><span data-stu-id="98380-104">Manage Microsoft Defender Antivirus in your business</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="98380-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="98380-105">**Applies to:**</span></span>

- [<span data-ttu-id="98380-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="98380-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="98380-107">Sie können Microsoft Defender Antivirus mit den folgenden Tools verwalten und konfigurieren:</span><span class="sxs-lookup"><span data-stu-id="98380-107">You can manage and configure Microsoft Defender Antivirus with the following tools:</span></span>

- <span data-ttu-id="98380-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (jetzt Teil von Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="98380-108">[Microsoft Intune](/mem/intune/protect/endpoint-security-antivirus-policy) (now part of Microsoft Endpoint Manager)</span></span>
- <span data-ttu-id="98380-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (jetzt Teil von Microsoft Endpoint Manager)</span><span class="sxs-lookup"><span data-stu-id="98380-109">[Microsoft Endpoint Configuration Manager](/mem/configmgr/protect/deploy-use/endpoint-protection-configure) (now part of Microsoft Endpoint Manager)</span></span>
- [<span data-ttu-id="98380-110">Gruppenrichtlinie</span><span class="sxs-lookup"><span data-stu-id="98380-110">Group Policy</span></span>](./use-group-policy-microsoft-defender-antivirus.md)
- [<span data-ttu-id="98380-111">PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="98380-111">PowerShell cmdlets</span></span>](./use-powershell-cmdlets-microsoft-defender-antivirus.md)
- [<span data-ttu-id="98380-112">Windows-Verwaltungsinstrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="98380-112">Windows Management Instrumentation (WMI)</span></span>](./use-wmi-microsoft-defender-antivirus.md)
- <span data-ttu-id="98380-113">Das [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (alsmpcmdrun.exebezeichnet </span><span class="sxs-lookup"><span data-stu-id="98380-113">The [Microsoft Malware Protection Command Line Utility](./command-line-arguments-microsoft-defender-antivirus.md) (referred to as the *mpcmdrun.exe* utility</span></span>

<span data-ttu-id="98380-114">Die folgenden Artikel enthalten weitere Informationen, Links und Ressourcen für die Verwendung dieser Tools zum Verwalten und Konfigurieren von Microsoft Defender Antivirus.</span><span class="sxs-lookup"><span data-stu-id="98380-114">The following articles provide further information, links, and resources for using these tools to manage and configure Microsoft Defender Antivirus.</span></span>

| <span data-ttu-id="98380-115">Artikel</span><span class="sxs-lookup"><span data-stu-id="98380-115">Article</span></span> | <span data-ttu-id="98380-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="98380-116">Description</span></span> |
|:---|:---|
|[<span data-ttu-id="98380-117">Verwalten von Microsoft Defender Antivirus mit Microsoft Intune und Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="98380-117">Manage Microsoft Defender Antivirus with Microsoft Intune and Microsoft Endpoint Configuration Manager</span></span>](use-intune-config-manager-microsoft-defender-antivirus.md)|<span data-ttu-id="98380-118">Informationen zur Verwendung von Intune und Configuration Manager zum Bereitstellen, Verwalten, Melden und Konfigurieren von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="98380-118">Information about using Intune and Configuration Manager to deploy, manage, report, and configure Microsoft Defender Antivirus</span></span> |
|[<span data-ttu-id="98380-119">Verwalten von Microsoft Defender Antivirus mit Gruppenrichtlinieneinstellungen</span><span class="sxs-lookup"><span data-stu-id="98380-119">Manage Microsoft Defender Antivirus with Group Policy settings</span></span>](use-group-policy-microsoft-defender-antivirus.md)|<span data-ttu-id="98380-120">Liste aller Gruppenrichtlinieneinstellungen in ADMX-Vorlagen</span><span class="sxs-lookup"><span data-stu-id="98380-120">List of all Group Policy settings located in ADMX templates</span></span> |
|[<span data-ttu-id="98380-121">Verwalten von Microsoft Defender Antivirus mit PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="98380-121">Manage Microsoft Defender Antivirus with PowerShell cmdlets</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)|<span data-ttu-id="98380-122">Anweisungen zur Verwendung von PowerShell-Cmdlets zum Verwalten von Microsoft Defender Antivirus sowie Links zur Dokumentation für alle Cmdlets und zulässigen Parameter</span><span class="sxs-lookup"><span data-stu-id="98380-122">Instructions for using PowerShell cmdlets to manage Microsoft Defender Antivirus, plus links to documentation for all cmdlets and allowed parameters</span></span> |
|[<span data-ttu-id="98380-123">Verwalten von Microsoft Defender Antivirus mit Windows Management Instrumentation (WMI)</span><span class="sxs-lookup"><span data-stu-id="98380-123">Manage Microsoft Defender Antivirus with Windows Management Instrumentation (WMI)</span></span>](use-wmi-microsoft-defender-antivirus.md)| <span data-ttu-id="98380-124">Anweisungen zur Verwendung von WMI zum Verwalten von Microsoft Defender Antivirus sowie Links zur Dokumentation für die WMIv2-APIs (einschließlich aller Klassen, Methoden und Eigenschaften)</span><span class="sxs-lookup"><span data-stu-id="98380-124">Instructions for using WMI to manage Microsoft Defender Antivirus, plus links to documentation for the WMIv2 APIs (including all classes, methods, and properties)</span></span> |
|[<span data-ttu-id="98380-125">Verwalten von Microsoft Defender Antivirus mit mpcmdrun.exe Befehlszeilentool</span><span class="sxs-lookup"><span data-stu-id="98380-125">Manage Microsoft Defender Antivirus with the mpcmdrun.exe command-line tool</span></span>](command-line-arguments-microsoft-defender-antivirus.md)|<span data-ttu-id="98380-126">Anweisungen zur Verwendung des dedizierten Befehlszeilentools zum Verwalten und Verwenden von Microsoft Defender Antivirus</span><span class="sxs-lookup"><span data-stu-id="98380-126">Instructions on using the dedicated command-line tool to manage and use Microsoft Defender Antivirus</span></span> |