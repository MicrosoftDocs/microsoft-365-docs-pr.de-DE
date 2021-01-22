---
title: Konfigurieren und Verwalten von Microsoft Defender für Endpunktfunktionen
ms.reviewer: ''
description: Konfigurieren und Verwalten von Microsoft Defender für Endpunktfunktionen wie Attack Surface Reduction und Schutz der nächsten Generation
keywords: konfigurieren, verwalten, Funktionen, Reduzierung der Angriffsfläche, Schutz der nächsten Generation, Sicherheitskontrollen, Endpunkterkennung und -reaktion, automatische Untersuchung und Wartung, Sicherheitskontrollen, Steuerelemente
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.technology: m365d
ms.openlocfilehash: d04177ef38c1bd04b0b73e29de9d8ab6fc0893ce
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49930126"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="bbce2-104">Konfigurieren und Verwalten von Microsoft Defender für Endpunktfunktionen</span><span class="sxs-lookup"><span data-stu-id="bbce2-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="bbce2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="bbce2-105">**Applies to:**</span></span>

- [<span data-ttu-id="bbce2-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="bbce2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2069559)

<span data-ttu-id="bbce2-107">Konfigurieren und verwalten Sie alle Microsoft Defender for Endpoint-Funktionen, um den besten Sicherheitsschutz für Ihre Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="bbce2-107">Configure and manage all the Microsoft Defender for Endpoint capabilities to get the best security protection for your organization.</span></span> 


## <a name="in-this-section"></a><span data-ttu-id="bbce2-108">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="bbce2-108">In this section</span></span> 
<span data-ttu-id="bbce2-109">Thema</span><span class="sxs-lookup"><span data-stu-id="bbce2-109">Topic</span></span> | <span data-ttu-id="bbce2-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="bbce2-110">Description</span></span> 
:---|:---
[<span data-ttu-id="bbce2-111">Konfigurieren der Funktionen zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="bbce2-111">Configure attack surface reduction capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-attack-surface-reduction) |  <span data-ttu-id="bbce2-112">Indem sichergestellt wird, dass die Konfigurationseinstellungen ordnungsgemäß festgelegt sind und Exploit-Gegentechniken angewendet werden, wehren sich diese Funktionen gegen Angriffe und Angriffe.</span><span class="sxs-lookup"><span data-stu-id="bbce2-112">By ensuring configuration settings are properly set and exploit mitigation techniques are applied, these set of capabilities resist attacks and exploitation.</span></span> 
[<span data-ttu-id="bbce2-113">Konfigurieren des Schutzes der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="bbce2-113">Configure next generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features) | <span data-ttu-id="bbce2-114">Konfigurieren Sie den Schutz der nächsten Generation, um alle Arten von neuen Bedrohungen zu fangen.</span><span class="sxs-lookup"><span data-stu-id="bbce2-114">Configure next generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="bbce2-115">Konfigurieren der Funktionen von Microsoft Threat Experts</span><span class="sxs-lookup"><span data-stu-id="bbce2-115">Configure Microsoft Threat Experts capabilities</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-microsoft-threat-experts) | <span data-ttu-id="bbce2-116">Konfigurieren und verwalten Sie, wie Sie Informationen zu Cybersicherheitsbedrohungen von Microsoft Threat Experts erhalten möchten.</span><span class="sxs-lookup"><span data-stu-id="bbce2-116">Configure and manage how you would like to get cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="bbce2-117">Konfigurieren der Microsoft 365 Defender-Integration</span><span class="sxs-lookup"><span data-stu-id="bbce2-117">Configure Microsoft 365 Defender integration</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/threat-protection-integration)| <span data-ttu-id="bbce2-118">Konfigurieren Sie andere Lösungen, die in Microsoft Defender for Endpoint integriert werden.</span><span class="sxs-lookup"><span data-stu-id="bbce2-118">Configure other solutions that integrate with Microsoft Defender for Endpoint.</span></span>
[<span data-ttu-id="bbce2-119">Verwaltungs- und API-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="bbce2-119">Management and API support</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/management-apis)| <span data-ttu-id="bbce2-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span><span class="sxs-lookup"><span data-stu-id="bbce2-120">Pull alerts to your SIEM or use APIs to create custom alerts.</span></span> <span data-ttu-id="bbce2-121">Erstellen und Erstellen von Power BI-Berichten.</span><span class="sxs-lookup"><span data-stu-id="bbce2-121">Create and build Power BI reports.</span></span> 
[<span data-ttu-id="bbce2-122">Konfigurieren von Microsoft Defender Security Center-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="bbce2-122">Configure Microsoft Defender Security Center settings</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/preferences-setup) |  <span data-ttu-id="bbce2-123">Konfigurieren Sie portalbezogene Einstellungen, z. B. allgemeine Einstellungen, erweiterte Features, aktivieren Sie die Vorschau und andere.</span><span class="sxs-lookup"><span data-stu-id="bbce2-123">Configure portal-related settings such as general settings, advanced features, enable the preview experience and others.</span></span>



