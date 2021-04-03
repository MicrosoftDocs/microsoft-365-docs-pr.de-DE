---
title: Übersicht über benutzerdefinierte Erkennungen in Microsoft Defender ATP
ms.reviewer: ''
description: Erfahren Sie, wie Sie die erweiterte Suche verwenden können, um benutzerdefinierte Erkennungen zu erstellen und Warnungen zu generieren.
keywords: Benutzerdefinierte Erkennungen, Warnungen, Erkennungsregeln, erweiterte Suche, Suche, Abfrage, Reaktionsaktionen, Intervall, Mdatp, microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 20bd70653f535bb732c252224c1e6efd5cf65035
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500652"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="da525-104">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="da525-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="da525-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="da525-105">**Applies to:**</span></span>
- [<span data-ttu-id="da525-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="da525-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="da525-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da525-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="da525-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="da525-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="da525-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="da525-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="da525-110">Mit benutzerdefinierten Erkennungen können Sie proaktiv verschiedene Ereignisse und Systemzustände überwachen und darauf reagieren, einschließlich mutmaßlicher Sicherheitsverletzungen und falsch konfigurierter Geräte.</span><span class="sxs-lookup"><span data-stu-id="da525-110">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="da525-111">Sie können dies mit anpassbaren Erkennungsregeln tun, die automatisch Warnungen und Reaktionsaktionen auslösen.</span><span class="sxs-lookup"><span data-stu-id="da525-111">You can do this with customizable detection rules that automatically trigger alerts and response actions.</span></span>

<span data-ttu-id="da525-112">Benutzerdefinierte Erkennungen funktionieren [mit](advanced-hunting-overview.md)der erweiterten Suche, die eine leistungsstarke, flexible Abfragesprache bietet, die eine breite Palette von Ereignis- und Systeminformationen aus Ihrem Netzwerk deckt.</span><span class="sxs-lookup"><span data-stu-id="da525-112">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="da525-113">Sie können festlegen, dass sie in regelmäßigen Intervallen ausgeführt werden, Warnungen generieren und Reaktionsaktionen ausführen, wenn Übereinstimmungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="da525-113">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="da525-114">Benutzerdefinierte Erkennungen bieten:</span><span class="sxs-lookup"><span data-stu-id="da525-114">Custom detections provide:</span></span>
- <span data-ttu-id="da525-115">Warnungen für regelbasierte Erkennungen, die aus erweiterten Suchabfragen erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="da525-115">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="da525-116">Automatische Reaktionsaktionen, die auf Dateien und Geräte angewendet werden</span><span class="sxs-lookup"><span data-stu-id="da525-116">Automatic response actions that apply to files and devices</span></span>

## <a name="related-topics"></a><span data-ttu-id="da525-117">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="da525-117">Related topics</span></span>
- [<span data-ttu-id="da525-118">Erstellen von Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="da525-118">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="da525-119">Anzeigen und Verwalten von Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="da525-119">View and manage detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="da525-120">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="da525-120">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
