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
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6c9befcc4b1224cacb2ab4eb8530e30a397aab49
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51060907"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="8819e-104">Benutzerdefinierte Erkennungen – Übersicht</span><span class="sxs-lookup"><span data-stu-id="8819e-104">Custom detections overview</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="8819e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="8819e-105">**Applies to:**</span></span>
- [<span data-ttu-id="8819e-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="8819e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="8819e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8819e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="8819e-108">Möchten Sie Microsoft Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="8819e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="8819e-109">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="8819e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)


<span data-ttu-id="8819e-110">Mit benutzerdefinierten Erkennungen können Sie proaktiv verschiedene Ereignisse und Systemzustände überwachen und darauf reagieren, einschließlich mutmaßlicher Sicherheitsverletzungen und falsch konfigurierter Geräte.</span><span class="sxs-lookup"><span data-stu-id="8819e-110">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured devices.</span></span> <span data-ttu-id="8819e-111">Sie können dies mit anpassbaren Erkennungsregeln tun, die automatisch Warnungen und Reaktionsaktionen auslösen.</span><span class="sxs-lookup"><span data-stu-id="8819e-111">You can do this with customizable detection rules that automatically trigger alerts and response actions.</span></span>

<span data-ttu-id="8819e-112">Benutzerdefinierte Erkennungen funktionieren [mit](advanced-hunting-overview.md)der erweiterten Suche, die eine leistungsstarke, flexible Abfragesprache bietet, die eine breite Palette von Ereignis- und Systeminformationen aus Ihrem Netzwerk deckt.</span><span class="sxs-lookup"><span data-stu-id="8819e-112">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="8819e-113">Sie können festlegen, dass sie in regelmäßigen Intervallen ausgeführt werden, Warnungen generieren und Reaktionsaktionen ausführen, wenn Übereinstimmungen angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="8819e-113">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="8819e-114">Benutzerdefinierte Erkennungen bieten:</span><span class="sxs-lookup"><span data-stu-id="8819e-114">Custom detections provide:</span></span>
- <span data-ttu-id="8819e-115">Warnungen für regelbasierte Erkennungen, die aus erweiterten Suchabfragen erstellt wurden</span><span class="sxs-lookup"><span data-stu-id="8819e-115">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="8819e-116">Automatische Reaktionsaktionen, die auf Dateien und Geräte angewendet werden</span><span class="sxs-lookup"><span data-stu-id="8819e-116">Automatic response actions that apply to files and devices</span></span>

## <a name="related-topics"></a><span data-ttu-id="8819e-117">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="8819e-117">Related topics</span></span>
- [<span data-ttu-id="8819e-118">Erstellen von Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="8819e-118">Create detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="8819e-119">Anzeigen und Verwalten von Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="8819e-119">View and manage detection rules</span></span>](custom-detections-manage.md)
- [<span data-ttu-id="8819e-120">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="8819e-120">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
