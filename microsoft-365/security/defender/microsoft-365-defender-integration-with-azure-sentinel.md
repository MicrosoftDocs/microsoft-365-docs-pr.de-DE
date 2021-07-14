---
title: Microsoft 365 Defender-Integration in Azure Sentinel
description: Verwenden Sie Azure Sentinel als SIEM für Microsoft 365 Defender Vorfälle und Ereignisse.
keywords: Vorfälle, Warnungen, untersuchen, analysieren, Reagieren, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: adb65c82713464da2df4d473d2fd7a055e0dbeb3
ms.sourcegitcommit: 4046c2c390851dffcdb430e1ba38c4df23fe2e69
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/13/2021
ms.locfileid: "53415578"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="f2d5c-104">Microsoft 365 Defender-Integration in Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="f2d5c-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="f2d5c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f2d5c-105">**Applies to:**</span></span>
- <span data-ttu-id="f2d5c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2d5c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="f2d5c-107">Der Microsoft 365 Defender Connector für Azure Sentinel (Vorschau) sendet alle Microsoft 365 Defender Vorfall- und Warnungsinformationen an Azure Sentinel und hält die Vorfälle synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="f2d5c-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="f2d5c-108">Nachdem Sie den Connector hinzugefügt haben, werden Microsoft 365 Defender Vorfälle, &mdash; die alle zugehörigen Warnungen, Entitäten und relevanten Informationen enthalten, die von Microsoft Defender für Endpunkt, Microsoft Defender for Identity, Microsoft Defender für Office 365 und Microsoft Cloud App Security empfangen &mdash; werden, als SIEM-Daten (Security Information and Event Management) an Azure Sentinel gestreamt, sodass Sie kontextbezogen sind, um Triage- und Vorfallreaktionen mit Azure Sentinel durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="f2d5c-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="f2d5c-109">In Azure Sentinel bleiben Vorfälle bidirektional mit Microsoft 365 Defender synchronisiert, sodass Sie die Vorteile des Microsoft 365 Defender-Portals und von Azure Sentinel im Azure-Portal für die Untersuchung und Reaktion auf Vorfälle nutzen können.</span><span class="sxs-lookup"><span data-stu-id="f2d5c-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 Defender portal and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="f2d5c-110">Sehen Sie sich diese kurze Übersicht über die Azure Sentinel-Integration in Microsoft 365 Defender (4 Minuten) an.</span><span class="sxs-lookup"><span data-stu-id="f2d5c-110">Watch this short overview of Azure Sentinel integration with Microsoft 365 Defender (4 minutes).</span></span>

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


<span data-ttu-id="f2d5c-111">So funktioniert es.</span><span class="sxs-lookup"><span data-stu-id="f2d5c-111">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Der Fluss und die Freigabe von Vorfalldaten zwischen Microsoft 365 Defender und Azure Sentinel":::

## <a name="next-steps"></a><span data-ttu-id="f2d5c-113">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="f2d5c-113">Next steps</span></span>

1. <span data-ttu-id="f2d5c-114">Erhalten Sie ein tieferes Verständnis der [Microsoft 365 Defender Integration in Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)</span><span class="sxs-lookup"><span data-stu-id="f2d5c-114">Get a deeper understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="f2d5c-115">[Verbinden Daten von Microsoft 365 Defender zu Azure Sentinel.](/azure/sentinel/connect-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="f2d5c-115">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="f2d5c-116">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="f2d5c-116">See also</span></span>

- [<span data-ttu-id="f2d5c-117">Übersicht über Vorfälle in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f2d5c-117">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="f2d5c-118">Untersuchen von Vorfällen mit Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="f2d5c-118">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
