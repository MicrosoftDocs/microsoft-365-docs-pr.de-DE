---
title: Korrekturaktionen in automatisierten Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection
description: Erhalten Sie einen Überblick über die Funktionen der automatischen Untersuchung und Reaktion in Microsoft Threat Protection.
keywords: automatisch, Untersuchung, Warnung, Trigger, Aktion, Wartung
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 65ace4bda091b3e000d25a984b706f26fe9c8696
ms.sourcegitcommit: 48b69caf6550e68cb14472ea8cfc76b53e7ae9c6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225483"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="302a2-104">Korrekturaktionen in automatisierten Ermittlungs-und Antwortfunktionen in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="302a2-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="302a2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="302a2-105">**Applies to:**</span></span>
- <span data-ttu-id="302a2-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="302a2-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="302a2-107">Zu den automatischen Ermittlungs-und Antwortfunktionen im Microsoft Threat Protection gehören bestimmte Korrekturaktionen.</span><span class="sxs-lookup"><span data-stu-id="302a2-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="302a2-108">Einige Arten von Korrekturaktionen werden auf Geräten durchgeführt, die auch als Endpunkte bezeichnet werden.</span><span class="sxs-lookup"><span data-stu-id="302a2-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="302a2-109">Für e-Mail-Inhalte werden andere Korrekturaktionen ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="302a2-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="302a2-110">In der folgenden Tabelle werden Korrekturaktionen zusammengefasst, die derzeit in Microsoft Threat Protection unterstützt werden:</span><span class="sxs-lookup"><span data-stu-id="302a2-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="302a2-111">Wartungsaktionen für Endpunkte</span><span class="sxs-lookup"><span data-stu-id="302a2-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="302a2-112">Wartungsaktionen für E-Mails</span><span class="sxs-lookup"><span data-stu-id="302a2-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="302a2-113">Quarantänedatei</span><span class="sxs-lookup"><span data-stu-id="302a2-113">Quarantine file</span></span><br/><span data-ttu-id="302a2-114">Registrierungsschlüssel entfernen</span><span class="sxs-lookup"><span data-stu-id="302a2-114">Remove registry key</span></span><br/><span data-ttu-id="302a2-115">Prozess abbrechen</span><span class="sxs-lookup"><span data-stu-id="302a2-115">Kill process</span></span> <br/><span data-ttu-id="302a2-116">Dienst beenden</span><span class="sxs-lookup"><span data-stu-id="302a2-116">Stop service</span></span> <br/><span data-ttu-id="302a2-117">Treiber deaktivieren</span><span class="sxs-lookup"><span data-stu-id="302a2-117">Disable driver</span></span> <br/><span data-ttu-id="302a2-118">Geplante Aufgabe entfernen</span><span class="sxs-lookup"><span data-stu-id="302a2-118">Remove scheduled task</span></span>      |<span data-ttu-id="302a2-119">E-Mail-Nachrichten oder Cluster vorläufig löschen</span><span class="sxs-lookup"><span data-stu-id="302a2-119">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="302a2-120">URL blockieren (Zeitpunkt des Klickens)</span><span class="sxs-lookup"><span data-stu-id="302a2-120">Block URL (time-of-click)</span></span><br/><span data-ttu-id="302a2-121">Externe E-Mail-Weiterleitung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="302a2-121">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="302a2-122">Behebungsaktionen können im [Wartungs Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)angezeigt werden, unabhängig davon, ob Sie genehmigt wurden oder bereits abgeschlossen sind.</span><span class="sxs-lookup"><span data-stu-id="302a2-122">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="302a2-123">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="302a2-123">Next steps</span></span>

- [<span data-ttu-id="302a2-124">Genehmigen oder Ablehnen von Aktionen im Zusammenhang mit der automatischen Untersuchung und Reaktion</span><span class="sxs-lookup"><span data-stu-id="302a2-124">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="302a2-125">Erfahren Sie mehr über das Info-Center</span><span class="sxs-lookup"><span data-stu-id="302a2-125">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
