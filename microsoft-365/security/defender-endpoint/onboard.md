---
title: Konfigurieren und Verwalten der Microsoft Defender für Endpunkt-Funktionen
ms.reviewer: ''
description: Konfigurieren und Verwalten von Microsoft Defender für Endpunktfunktionen wie Angriffsflächenreduzierung und Schutz der nächsten Generation
keywords: konfigurieren, verwalten, Funktionen, Verringerung der Angriffsfläche, Schutz der nächsten Generation, Sicherheitskontrollen, EDR, automatische Untersuchung und Wartung, Sicherheitskontrollen, Steuerelemente
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
ms.openlocfilehash: c58d7d4192afd0aa13a5ffb0c7f3204b4eaf0315
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844406"
---
# <a name="configure-and-manage-microsoft-defender-for-endpoint-capabilities"></a><span data-ttu-id="f8fad-104">Konfigurieren und Verwalten der Microsoft Defender für Endpunkt-Funktionen</span><span class="sxs-lookup"><span data-stu-id="f8fad-104">Configure and manage Microsoft Defender for Endpoint capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f8fad-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f8fad-105">**Applies to:**</span></span>

- [<span data-ttu-id="f8fad-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="f8fad-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f8fad-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f8fad-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="f8fad-108">Möchten Sie Microsoft Defender für Endpunkt erleben?</span><span class="sxs-lookup"><span data-stu-id="f8fad-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f8fad-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="f8fad-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="f8fad-110">Erfahren Sie, wie Sie Defender für Endpunkt-Features konfigurieren und verwalten, um den besten Sicherheitsschutz für Ihre Organisation zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="f8fad-110">Learn how to configure and manage Defender for Endpoint features, to get the best security protection for your organization.</span></span>

<span data-ttu-id="f8fad-111">Praktische Hinweise zum Verbinden neuer Geräte in Ihrer Organisation finden Sie unter [Onboarding von Geräten mit dem Microsoft Defender für Endpunkt-Dienst.](./onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="f8fad-111">For practical advice on connecting new devices in your organization, see [Onboard devices to the Microsoft Defender for Endpoint service](./onboard-configure.md).</span></span>

## <a name="in-this-section"></a><span data-ttu-id="f8fad-112">Inhalt dieses Abschnitts</span><span class="sxs-lookup"><span data-stu-id="f8fad-112">In this section</span></span>

<span data-ttu-id="f8fad-113">Thema</span><span class="sxs-lookup"><span data-stu-id="f8fad-113">Topic</span></span> | <span data-ttu-id="f8fad-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f8fad-114">Description</span></span>
:---|:---
[<span data-ttu-id="f8fad-115">Konfigurieren Microsoft Defender Security Center Einstellungen</span><span class="sxs-lookup"><span data-stu-id="f8fad-115">Configure Microsoft Defender Security Center settings</span></span>](preferences-setup.md) | <span data-ttu-id="f8fad-116">Konfigurieren Sie portalbezogene Einstellungen wie allgemeine Einstellungen, erweiterte Features oder aktivieren Sie die Vorschau.</span><span class="sxs-lookup"><span data-stu-id="f8fad-116">Configure portal-related settings such as general settings, advanced features, or enable the preview experience.</span></span>
[<span data-ttu-id="f8fad-117">Konfigurieren der Funktionen zur Verringerung der Angriffsfläche</span><span class="sxs-lookup"><span data-stu-id="f8fad-117">Configure attack surface reduction capabilities</span></span>](configure-attack-surface-reduction.md) | <span data-ttu-id="f8fad-118">Konfigurieren Sie die Funktionen zur Verringerung der Angriffsfläche, um sicherzustellen, dass die Einstellungen ordnungsgemäß angewendet und Techniken zur Exploit-Minderung festgelegt werden.</span><span class="sxs-lookup"><span data-stu-id="f8fad-118">Configure attack surface reduction capabilities, to ensure that settings are properly applied, and exploit mitigation techniques are set.</span></span>
[<span data-ttu-id="f8fad-119">Konfigurieren des Schutzes der nächsten Generation</span><span class="sxs-lookup"><span data-stu-id="f8fad-119">Configure next-generation protection</span></span>](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) | <span data-ttu-id="f8fad-120">Konfigurieren Sie den Schutz der nächsten Generation, um alle Arten von bedrohungen abzufangen.</span><span class="sxs-lookup"><span data-stu-id="f8fad-120">Configure next-generation protection to catch all types of emerging threats.</span></span>
[<span data-ttu-id="f8fad-121">Konfigurieren Microsoft-Bedrohungsexperten Funktionen</span><span class="sxs-lookup"><span data-stu-id="f8fad-121">Configure Microsoft Threat Experts capabilities</span></span>](configure-microsoft-threat-experts.md) | <span data-ttu-id="f8fad-122">Konfigurieren und Verwalten der Cybersicherheits-Bedrohungserkennung aus Microsoft-Bedrohungsexperten.</span><span class="sxs-lookup"><span data-stu-id="f8fad-122">Configure and manage cybersecurity threat intelligence from Microsoft Threat Experts.</span></span>
[<span data-ttu-id="f8fad-123">Konfigurieren Microsoft 365 Defender-Integration</span><span class="sxs-lookup"><span data-stu-id="f8fad-123">Configure Microsoft 365 Defender integration</span></span>](/microsoft-365/security/defender-endpoint/threat-protection-integration) | <span data-ttu-id="f8fad-124">Konfigurieren Sie andere Lösungen, die in Defender für Endpunkt integriert sind.</span><span class="sxs-lookup"><span data-stu-id="f8fad-124">Configure other solutions that integrate with Defender for Endpoint.</span></span>
[<span data-ttu-id="f8fad-125">Verwaltungs- und API-Unterstützung</span><span class="sxs-lookup"><span data-stu-id="f8fad-125">Management and API support</span></span>](/microsoft-365/security/defender-endpoint/management-apis) | <span data-ttu-id="f8fad-126">Rufen Sie Warnungen an Ihre Sicherheitsinformations- und Ereignisverwaltung (Security Information and Event Management, SIEM) ab, oder verwenden Sie APIs zum Erstellen benutzerdefinierter Warnungen.</span><span class="sxs-lookup"><span data-stu-id="f8fad-126">Pull alerts to your Security Information and Event Management (SIEM) or use APIs to create custom alerts.</span></span> <span data-ttu-id="f8fad-127">Erstellen und Erstellen von Power BI Berichten.</span><span class="sxs-lookup"><span data-stu-id="f8fad-127">Create and build Power BI reports.</span></span>
