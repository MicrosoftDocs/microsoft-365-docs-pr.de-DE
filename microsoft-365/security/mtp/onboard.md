---
title: Konfigurieren und Verwalten von Microsoft Defender für Endpunkt Funktionen
ms.reviewer: ''
description: Konfigurieren und Verwalten von Microsoft Defender für Endpunkt Funktionen wie Angriffs Oberflächenreduzierung und Schutz der nächsten Generation
keywords: konfigurieren, verwalten, Funktionen, Angriffsflächen Reduzierung, Schutz der nächsten Generation, Sicherheitskontrollen, Endpunkterkennung und-Antwort, automatische Untersuchung und Behebung, Sicherheitskontrollen, Steuerelemente
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.openlocfilehash: b202b30e218448794eac7588078ff3ac9cfe9ee3
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844812"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="3984c-104">Konfigurieren und Verwalten von Microsoft Defender für Endpunkt Funktionen</span><span class="sxs-lookup"><span data-stu-id="3984c-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3984c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3984c-105">**Applies to:**</span></span>

- [<span data-ttu-id="3984c-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="3984c-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="3984c-107">Konfigurieren und verwalten Sie alle Microsoft Defender for Endpoint-Funktionen, um den besten Sicherheitsschutz für Ihre Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="3984c-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="3984c-108">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="3984c-108">In this section</span></span> 
<span data-ttu-id="3984c-109">Thema</span><span class="sxs-lookup"><span data-stu-id="3984c-109">Topic</span></span> | <span data-ttu-id="3984c-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="3984c-110">Description</span></span> 
:---|:---
[<span data-ttu-id="3984c-111">Konfigurieren von Funktionen zur Angriffs Oberflächenreduzierung</span><span class="sxs-lookup"><span data-stu-id="3984c-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="3984c-112">Wenn Sie sicherstellen, dass die Konfigurationseinstellungen ordnungsgemäß festgelegt sind und Methoden zur Minderung der Ausschöpfung angewendet werden, widersetzen diese Funktionen Angriffe und Ausbeutung.</span><span class="sxs-lookup"><span data-stu-id="3984c-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="3984c-113">Konfigurieren des Schutzes der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="3984c-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="3984c-114">Konfigurieren Sie den Schutz der nächsten Generation, um alle Arten von neuen Bedrohungen zu erfassen.</span><span class="sxs-lookup"><span data-stu-id="3984c-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="3984c-115">Konfigurieren von Microsoft Threat Experts-Funktionen</span><span class="sxs-lookup"><span data-stu-id="3984c-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="3984c-116">Konfigurieren und verwalten Sie, wie Sie Cyber Threat Intelligence von Microsoft Threat Experts erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="3984c-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="3984c-117">Konfigurieren der Integration von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3984c-117">Configure Microsoft 365 Defender integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="3984c-118">Konfigurieren Sie andere Lösungen, die in Microsoft Defender for Endpoint integriert werden.</span><span class="sxs-lookup"><span data-stu-id="3984c-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="3984c-119">Verwaltung und API-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="3984c-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="3984c-120">Ziehen Sie Warnungen an Ihr Siem, oder verwenden Sie APIs, um benutzerdefinierte Warnungen zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="3984c-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="3984c-121">Erstellen und Erstellen von Power BI-Berichten.</span><span class="sxs-lookup"><span data-stu-id="3984c-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="3984c-122">Konfigurieren von Einstellungen für das Microsoft Defender-Sicherheits Center</span><span class="sxs-lookup"><span data-stu-id="3984c-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="3984c-123">Konfigurieren Sie Portal bezogene Einstellungen wie allgemeine Einstellungen, erweiterte Funktionen, aktivieren Sie die Vorschau und andere.</span><span class="sxs-lookup"><span data-stu-id="3984c-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



