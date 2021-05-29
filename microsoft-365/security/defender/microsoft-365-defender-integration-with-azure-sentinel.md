---
title: Microsoft 365 Defender-Integration in Azure Sentinel
description: Verwenden Sie Azure Sentinel als SIEM für Microsoft 365 und Ereignisse von Defender.
keywords: Vorfälle, Warnungen, untersuchen, analysieren, Reaktion, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, microsoft, m365
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
ms.openlocfilehash: b5a53131733d1c7c539676c1d45abe7eabbe2de7
ms.sourcegitcommit: 76c91e7b0d3172de57988eb4576d2b91c2f9ce18
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52707337"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="49908-104">Microsoft 365 Defender-Integration in Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="49908-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="49908-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="49908-105">**Applies to:**</span></span>
- <span data-ttu-id="49908-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49908-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="49908-107">Der Microsoft 365 Defender Connector für Azure Sentinel (Vorschau) sendet alle Microsoft 365 Defender-Vorfälle und Benachrichtigungen an Azure Sentinel und hält die Vorfälle synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="49908-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="49908-108">Nachdem Sie den Connector hinzugefügt haben, werden Microsoft 365 Defender-Vorfälle, die alle zugeordneten Warnungen, Entitäten und relevanten Informationen enthalten, die von Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender für Office 365 und Microsoft Cloud App Security empfangen wurden, als SieM-Daten (Security Information and Event Management, Sicherheitsinformationen und Ereignisverwaltung) an Azure Sentinel gestreamt, um Ihnen Kontext zur Durchführung von Triage- und Vorfallreaktionen mit Azure Sentinel zu &mdash; &mdash; bieten.</span><span class="sxs-lookup"><span data-stu-id="49908-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="49908-109">In Azure Sentinel werden Vorfälle weiterhin bidirektional mit Microsoft 365 Defender synchronisiert, sodass Sie die Vorteile des Microsoft 365 Security Centers und von Azure Sentinel im Azure-Portal für die Untersuchung und Reaktion auf Vorfälle nutzen können.</span><span class="sxs-lookup"><span data-stu-id="49908-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 security center and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="49908-110">Hier sehen Sie, wie es funktioniert.</span><span class="sxs-lookup"><span data-stu-id="49908-110">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Der Fluss und die Freigabe von Vorfalldaten zwischen Microsoft 365 Defender und Azure Sentinel":::

## <a name="next-steps"></a><span data-ttu-id="49908-112">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="49908-112">Next steps</span></span>

1. <span data-ttu-id="49908-113">Erhalten Sie ein besseres Verständnis [Microsoft 365 Integration von Defender in Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span><span class="sxs-lookup"><span data-stu-id="49908-113">Get a better understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="49908-114">[Verbinden daten von Microsoft 365 Defender zu Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span><span class="sxs-lookup"><span data-stu-id="49908-114">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="49908-115">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="49908-115">See also</span></span>

- [<span data-ttu-id="49908-116">Übersicht über Vorfälle in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="49908-116">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="49908-117">Untersuchen von Vorfällen mit Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="49908-117">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
