---
title: Konfigurieren und Verwalten von Microsoft Defender ATP-Funktionen
ms.reviewer: ''
description: Konfigurieren und Verwalten von Microsoft Defender ATP-Funktionen wie Reduzierung der Angriffsfläche und Schutz der nächsten Generation
keywords: Konfigurieren, Verwalten, Funktionen, Reduzierung der Angriffsfläche, Schutz der nächsten Generation, Sicherheitskontrollen, Endpunkterkennung und -reaktion, automatische Untersuchung und Behebung, Sicherheitskontrollen, Steuerelemente
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
ms.openlocfilehash: a0872de9774773c136bca6febd621daba5b2d7d3
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186377"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="ec248-104">Konfigurieren und Verwalten von Microsoft Defender for Endpoint-Funktionen</span><span class="sxs-lookup"><span data-stu-id="ec248-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ec248-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ec248-105">**Applies to:**</span></span>
- [<span data-ttu-id="ec248-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="ec248-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="ec248-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ec248-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="ec248-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="ec248-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="ec248-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="ec248-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="ec248-110">Konfigurieren und verwalten Sie alle Defender for Endpoint-Funktionen, um den besten Sicherheitsschutz für Ihre Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="ec248-110">Configure and manage all the Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="ec248-111">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="ec248-111">In this section</span></span> 
<span data-ttu-id="ec248-112">Thema</span><span class="sxs-lookup"><span data-stu-id="ec248-112">Topic</span></span> | <span data-ttu-id="ec248-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ec248-113">Description</span></span> 
:---|:---
[<span data-ttu-id="ec248-114">Konfigurieren von Funktionen zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="ec248-114">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) |  <span data-ttu-id="ec248-115">Indem sie sicherstellen, dass Konfigurationseinstellungen ordnungsgemäß festgelegt sind und Techniken zur Exploitminderung angewendet werden, wehren sich diese Funktionen gegen Angriffe und Nutzung.</span><span class="sxs-lookup"><span data-stu-id="ec248-115">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="ec248-116">Konfigurieren des Schutzes der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="ec248-116">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="ec248-117">Konfigurieren Sie den Schutz der nächsten Generation, um alle Arten von neuen Bedrohungen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="ec248-117">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="ec248-118">Konfigurieren von Microsoft Threat Experts-Funktionen</span><span class="sxs-lookup"><span data-stu-id="ec248-118">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="ec248-119">Konfigurieren und verwalten Sie, wie Sie Informationen zu Cybersicherheitsbedrohungen von Microsoft Threat Experts erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="ec248-119">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="ec248-120">Konfigurieren der Microsoft Threat Protection-Integration</span><span class="sxs-lookup"><span data-stu-id="ec248-120">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration)| <span data-ttu-id="ec248-121">Konfigurieren sie andere Lösungen, die in Defender for Endpoint integriert werden.</span><span class="sxs-lookup"><span data-stu-id="ec248-121">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="ec248-122">Unterstützung von Verwaltung und API</span><span class="sxs-lookup"><span data-stu-id="ec248-122">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis)| <span data-ttu-id="ec248-123">Ziehen Sie Warnungen an Ihr SIEM, oder verwenden Sie APIs, um benutzerdefinierte Warnungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="ec248-123">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="ec248-124">Erstellen und Erstellen von Power BI-Berichten.</span><span class="sxs-lookup"><span data-stu-id="ec248-124">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="ec248-125">Konfigurieren von Microsoft Defender Security Center-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="ec248-125">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) |  <span data-ttu-id="ec248-126">Konfigurieren Sie portalbezogene Einstellungen wie allgemeine Einstellungen, erweiterte Features, aktivieren Sie die Vorschau und andere.</span><span class="sxs-lookup"><span data-stu-id="ec248-126">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



