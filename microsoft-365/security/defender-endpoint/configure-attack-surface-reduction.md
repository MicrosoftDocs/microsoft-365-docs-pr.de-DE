---
title: Konfigurieren der Reduzierung der Angriffsfläche
description: Verwenden Sie Microsoft Intune, Microsoft Endpoint Configuration Manager, PowerShell-Cmdlets und Gruppenrichtlinien, um die Reduzierung der Angriffsfläche zu konfigurieren.
keywords: asr, attack surface reduction, windows defender, microsoft defender, antivirus, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6129fb889e2bd42f177c4e3be30f676854119f91
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166161"
---
# <a name="configure-attack-surface-reduction"></a><span data-ttu-id="cd7cd-104">Konfigurieren der Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="cd7cd-104">Configure attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="cd7cd-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="cd7cd-105">**Applies to:**</span></span>
- [<span data-ttu-id="cd7cd-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="cd7cd-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cd7cd-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cd7cd-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="cd7cd-108">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="cd7cd-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cd7cd-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="cd7cd-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="cd7cd-110">Sie können die Reduzierung der Angriffsfläche mit vielen Tools konfigurieren, darunter:</span><span class="sxs-lookup"><span data-stu-id="cd7cd-110">You can configure attack surface reduction with many tools, including:</span></span>

* <span data-ttu-id="cd7cd-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="cd7cd-111">Microsoft Intune</span></span>
* <span data-ttu-id="cd7cd-112">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="cd7cd-112">Microsoft Endpoint Configuration Manager</span></span>
* <span data-ttu-id="cd7cd-113">Gruppenrichtlinien</span><span class="sxs-lookup"><span data-stu-id="cd7cd-113">Group Policy</span></span>
* <span data-ttu-id="cd7cd-114">PowerShell-Cmdlets</span><span class="sxs-lookup"><span data-stu-id="cd7cd-114">PowerShell cmdlets</span></span>

<span data-ttu-id="cd7cd-115">Artikel</span><span class="sxs-lookup"><span data-stu-id="cd7cd-115">Article</span></span> | <span data-ttu-id="cd7cd-116">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="cd7cd-116">Description</span></span>
-|-
[<span data-ttu-id="cd7cd-117">Aktivieren der hardwarebasierten Isolation für Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="cd7cd-117">Enable hardware-based isolation for Microsoft Edge</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard) | <span data-ttu-id="cd7cd-118">Vorbereiten und Installieren von Application Guard, einschließlich Hardware- und Softwareanforderungen</span><span class="sxs-lookup"><span data-stu-id="cd7cd-118">How to prepare for and install Application Guard, including hardware and software requirements</span></span>
[<span data-ttu-id="cd7cd-119">Aktivieren der Anwendungssteuerung</span><span class="sxs-lookup"><span data-stu-id="cd7cd-119">Enable application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)|<span data-ttu-id="cd7cd-120">Steuern von Anwendungen, die von Benutzern ausgeführt werden, und Schützen von Kernelmodusprozessen</span><span class="sxs-lookup"><span data-stu-id="cd7cd-120">How to control applications run by users and protect kernel mode processes</span></span>
[<span data-ttu-id="cd7cd-121">Exploit-Schutz</span><span class="sxs-lookup"><span data-stu-id="cd7cd-121">Exploit protection</span></span>](./enable-exploit-protection.md)|<span data-ttu-id="cd7cd-122">Automatisches Anwenden von Techniken zur Risikominderung von Exploits sowohl auf Betriebssystemprozesse als auch auf einzelne Apps</span><span class="sxs-lookup"><span data-stu-id="cd7cd-122">How to automatically apply exploit mitigation techniques on both operating system processes and on individual apps</span></span>
[<span data-ttu-id="cd7cd-123">Netzwerkschutz</span><span class="sxs-lookup"><span data-stu-id="cd7cd-123">Network protection</span></span>](./enable-network-protection.md)|<span data-ttu-id="cd7cd-124">So verhindern Sie, dass Benutzer Apps für den Zugriff auf gefährliche Domänen verwenden</span><span class="sxs-lookup"><span data-stu-id="cd7cd-124">How to prevent users from using any apps to access dangerous domains</span></span>
[<span data-ttu-id="cd7cd-125">Kontrollierter Ordnerzugriff</span><span class="sxs-lookup"><span data-stu-id="cd7cd-125">Controlled folder access</span></span>](./enable-controlled-folders.md)|<span data-ttu-id="cd7cd-126">Schützen wertvoller Daten vor schädlichen Apps</span><span class="sxs-lookup"><span data-stu-id="cd7cd-126">How to protect valuable data from malicious apps</span></span>
[<span data-ttu-id="cd7cd-127">Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="cd7cd-127">Attack surface reduction</span></span>](./enable-attack-surface-reduction.md)|<span data-ttu-id="cd7cd-128">Verhindern von Aktionen und Apps, die in der Regel von Schadsoftware mit Exploits verwendet werden</span><span class="sxs-lookup"><span data-stu-id="cd7cd-128">How to prevent actions and apps that are typically used by exploit-seeking malware</span></span>
[<span data-ttu-id="cd7cd-129">Netzwerkfirewall</span><span class="sxs-lookup"><span data-stu-id="cd7cd-129">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)|<span data-ttu-id="cd7cd-130">Schützen von Geräten und Daten über ein Netzwerk hinweg</span><span class="sxs-lookup"><span data-stu-id="cd7cd-130">How to protect devices and data across a network</span></span>

