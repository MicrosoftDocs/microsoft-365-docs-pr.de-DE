---
title: Konfigurieren und Verwalten von Microsoft Defender for Endpoint-Funktionen
ms.reviewer: ''
description: Konfigurieren und Verwalten von Microsoft Defender for Endpoint-Funktionen wie Reduzierung der Angriffsfläche und Schutz der nächsten Generation
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 95c462829b43ae41c1fe664b2313a716078baea7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51064599"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="9ed34-104">Konfigurieren und Verwalten von Microsoft Defender for Endpoint-Funktionen</span><span class="sxs-lookup"><span data-stu-id="9ed34-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="9ed34-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9ed34-105">**Applies to:**</span></span>

- [<span data-ttu-id="9ed34-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9ed34-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="9ed34-107">Konfigurieren und verwalten Sie alle Microsoft Defender for Endpoint-Funktionen, um den besten Sicherheitsschutz für Ihre Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="9ed34-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="9ed34-108">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="9ed34-108">In this section</span></span> 
<span data-ttu-id="9ed34-109">Thema</span><span class="sxs-lookup"><span data-stu-id="9ed34-109">Topic</span></span> | <span data-ttu-id="9ed34-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9ed34-110">Description</span></span> 
:---|:---
[<span data-ttu-id="9ed34-111">Konfigurieren von Funktionen zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="9ed34-111">Configure attack surface reduction capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="9ed34-112">Indem sie sicherstellen, dass Konfigurationseinstellungen ordnungsgemäß festgelegt sind und Techniken zur Exploitminderung angewendet werden, wehren sich diese Funktionen gegen Angriffe und Nutzung.</span><span class="sxs-lookup"><span data-stu-id="9ed34-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="9ed34-113">Konfigurieren des Schutzes der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="9ed34-113">Configure next generation protection</span></span>](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="9ed34-114">Konfigurieren Sie den Schutz der nächsten Generation, um alle Arten von neu auftretenden Bedrohungen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="9ed34-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="9ed34-115">Konfigurieren von Microsoft Threat Experts-Funktionen</span><span class="sxs-lookup"><span data-stu-id="9ed34-115">Configure Microsoft Threat Experts capabilities</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="9ed34-116">Konfigurieren und verwalten Sie, wie Sie Informationen zu Cybersicherheitsbedrohungen von Microsoft Threat Experts erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="9ed34-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="9ed34-117">Konfigurieren der Microsoft 365 Defender-Integration</span><span class="sxs-lookup"><span data-stu-id="9ed34-117">Configure Microsoft 365 Defender integration</span></span>](/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="9ed34-118">Konfigurieren sie andere Lösungen, die in Microsoft Defender for Endpoint integriert werden.</span><span class="sxs-lookup"><span data-stu-id="9ed34-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="9ed34-119">Unterstützung von Verwaltung und API</span><span class="sxs-lookup"><span data-stu-id="9ed34-119">Management and API support</span></span>](/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="9ed34-120">Ziehen Sie Warnungen an Ihr SIEM, oder verwenden Sie APIs, um benutzerdefinierte Warnungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="9ed34-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="9ed34-121">Erstellen und Erstellen von Power BI-Berichten.</span><span class="sxs-lookup"><span data-stu-id="9ed34-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="9ed34-122">Konfigurieren von Microsoft Defender Security Center-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="9ed34-122">Configure Microsoft Defender Security Center settings</span></span>](/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="9ed34-123">Konfigurieren Sie portalbezogene Einstellungen wie allgemeine Einstellungen, erweiterte Features, aktivieren Sie die Vorschau und andere.</span><span class="sxs-lookup"><span data-stu-id="9ed34-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>