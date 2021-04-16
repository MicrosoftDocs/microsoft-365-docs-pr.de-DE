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
ms.technology: mde
ms.openlocfilehash: 3ad23e030048506784edd8f1988fa33263a085ae
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51861335"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="64548-104">Konfigurieren und Verwalten von Microsoft Defender for Endpoint-Funktionen</span><span class="sxs-lookup"><span data-stu-id="64548-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="64548-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="64548-105">**Applies to:**</span></span>

- [<span data-ttu-id="64548-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="64548-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="64548-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="64548-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="64548-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="64548-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="64548-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="64548-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="64548-110">Erfahren Sie, wie Sie Defender for Endpoint-Features konfigurieren und verwalten, um den besten Sicherheitsschutz für Ihre Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="64548-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="64548-111">Praktische Hinweise zum Verbinden neuer Geräte in Ihrer Organisation finden Sie unter [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="64548-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="64548-112">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="64548-112">In this section</span></span>

<span data-ttu-id="64548-113">Thema</span><span class="sxs-lookup"><span data-stu-id="64548-113">Topic</span></span> | <span data-ttu-id="64548-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="64548-114">Description</span></span>
:---|:---
[<span data-ttu-id="64548-115">Konfigurieren von Microsoft Defender Security Center-Einstellungen</span><span class="sxs-lookup"><span data-stu-id="64548-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="64548-116">Konfigurieren Sie portalbezogene Einstellungen, z. B. allgemeine Einstellungen, erweiterte Features, oder aktivieren Sie die Vorschau.</span><span class="sxs-lookup"><span data-stu-id="64548-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="64548-117">Konfigurieren von Funktionen zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="64548-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="64548-118">Konfigurieren Sie Funktionen zur Reduzierung der Angriffsfläche, um sicherzustellen, dass die Einstellungen ordnungsgemäß angewendet werden, und Es werden Techniken zur Risikominderung für Exploits festgelegt.</span><span class="sxs-lookup"><span data-stu-id="64548-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="64548-119">Konfigurieren des Schutzes der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="64548-119">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="64548-120">Konfigurieren Sie den Schutz der nächsten Generation, um alle Arten von neuen Bedrohungen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="64548-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="64548-121">Konfigurieren von Microsoft Threat Experts-Funktionen</span><span class="sxs-lookup"><span data-stu-id="64548-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="64548-122">Konfigurieren und Verwalten von Cybersecurity Threat Intelligence von Microsoft Threat Experts.</span><span class="sxs-lookup"><span data-stu-id="64548-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="64548-123">Konfigurieren der Microsoft Threat Protection-Integration</span><span class="sxs-lookup"><span data-stu-id="64548-123">Configure Microsoft Threat Protection integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="64548-124">Konfigurieren sie andere Lösungen, die in Defender for Endpoint integriert werden.</span><span class="sxs-lookup"><span data-stu-id="64548-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="64548-125">Unterstützung von Verwaltung und API</span><span class="sxs-lookup"><span data-stu-id="64548-125">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="64548-126">Ziehen Sie Warnungen an Ihre Sicherheitsinformationen und Ereignisverwaltung (SECURITY Information and Event Management, SIEM) oder verwenden Sie APIs zum Erstellen benutzerdefinierter Warnungen.</span><span class="sxs-lookup"><span data-stu-id="64548-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="64548-127">Erstellen und Erstellen von Power BI-Berichten.</span><span class="sxs-lookup"><span data-stu-id="64548-127">Create and build Power BI reports.</span></span>
