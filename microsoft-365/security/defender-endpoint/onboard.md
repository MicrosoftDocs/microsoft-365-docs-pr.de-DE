---
title: Konfigurieren und Verwalten von Microsoft Defender for Endpoint-Funktionen
ms.reviewer: ''
description: Konfigurieren und Verwalten von Microsoft Defender for Endpoint-Funktionen wie Reduzierung der Angriffsfläche und Schutz der nächsten Generation
keywords: Konfigurieren, Verwalten, Funktionen, Reduzierung der Angriffsfläche, Schutz der nächsten Generation, Sicherheitskontrollen, EDR, automatische Untersuchung und Behebung, Sicherheitskontrollen, Steuerelemente
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
ms.openlocfilehash: 25b70f91824db2a6d05db5d3981dd50f4f2b477a
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934741"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="f4208-104">Konfigurieren und Verwalten von Microsoft Defender for Endpoint-Funktionen</span><span class="sxs-lookup"><span data-stu-id="f4208-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f4208-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f4208-105">**Applies to:**</span></span>

- [<span data-ttu-id="f4208-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f4208-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f4208-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f4208-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f4208-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="f4208-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f4208-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f4208-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f4208-110">Erfahren Sie, wie Sie Defender for Endpoint-Features konfigurieren und verwalten, um den besten Sicherheitsschutz für Ihre Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f4208-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="f4208-111">Praktische Hinweise zum Verbinden neuer Geräte in Ihrer Organisation finden Sie unter [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span><span class="sxs-lookup"><span data-stu-id="f4208-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f4208-112">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="f4208-112">In this section</span></span>

<span data-ttu-id="f4208-113">Thema</span><span class="sxs-lookup"><span data-stu-id="f4208-113">Topic</span></span> | <span data-ttu-id="f4208-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f4208-114">Description</span></span>
:---|:---
[<span data-ttu-id="f4208-115">Konfigurieren Microsoft Defender Security Center Einstellungen</span><span class="sxs-lookup"><span data-stu-id="f4208-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="f4208-116">Konfigurieren Sie portalbezogene Einstellungen, z. B. allgemeine Einstellungen, erweiterte Features, oder aktivieren Sie die Vorschau.</span><span class="sxs-lookup"><span data-stu-id="f4208-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="f4208-117">Konfigurieren von Funktionen zur Reduzierung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="f4208-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="f4208-118">Konfigurieren Sie Funktionen zur Reduzierung der Angriffsfläche, um sicherzustellen, dass die Einstellungen ordnungsgemäß angewendet werden, und Es werden Techniken zur Risikominderung für Exploits festgelegt.</span><span class="sxs-lookup"><span data-stu-id="f4208-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="f4208-119">Konfigurieren des Schutzes der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="f4208-119">Configure next-generation protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="f4208-120">Konfigurieren Sie den Schutz der nächsten Generation, um alle Arten von neuen Bedrohungen zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="f4208-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="f4208-121">Konfigurieren Microsoft-Bedrohungsexperten Funktionen</span><span class="sxs-lookup"><span data-stu-id="f4208-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="f4208-122">Konfigurieren und Verwalten von Cybersecurity Threat Intelligence von Microsoft-Bedrohungsexperten.</span><span class="sxs-lookup"><span data-stu-id="f4208-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="f4208-123">Konfigurieren Microsoft 365 Defender-Integration</span><span class="sxs-lookup"><span data-stu-id="f4208-123">Configure Microsoft 365 Defender integration</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="f4208-124">Konfigurieren sie andere Lösungen, die in Defender for Endpoint integriert werden.</span><span class="sxs-lookup"><span data-stu-id="f4208-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="f4208-125">Unterstützung von Verwaltung und API</span><span class="sxs-lookup"><span data-stu-id="f4208-125">Management and API support</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="f4208-126">Ziehen Sie Warnungen an Ihre Sicherheitsinformationen und Ereignisverwaltung (SECURITY Information and Event Management, SIEM) oder verwenden Sie APIs zum Erstellen benutzerdefinierter Warnungen.</span><span class="sxs-lookup"><span data-stu-id="f4208-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="f4208-127">Erstellen und Erstellen Power BI Berichte.</span><span class="sxs-lookup"><span data-stu-id="f4208-127">Create and build Power BI reports.</span></span>
