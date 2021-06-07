---
title: Microsoft 365 Defender-Integration in Azure Sentinel
description: Verwenden Sie Azure Sentinel als SIEM für Microsoft 365 Defender-Vorfälle und -Ereignisse.
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
ms.openlocfilehash: 7d9cff584f35c39544034501c607b7156a0f1bf2
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782921"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a><span data-ttu-id="3af38-104">Microsoft 365 Defender-Integration in Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="3af38-104">Microsoft 365 Defender integration with Azure Sentinel</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="3af38-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="3af38-105">**Applies to:**</span></span>
- <span data-ttu-id="3af38-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3af38-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3af38-107">Der Microsoft 365 Defender-Connector für Azure Sentinel (Vorschau) sendet alle Microsoft 365 Defender-Vorfälle und Warnungsinformationen an Azure Sentinel und hält die Vorfälle synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="3af38-107">The Microsoft 365 Defender connector for Azure Sentinel (preview) sends all Microsoft 365 Defender incidents and alerts information to Azure Sentinel and keeps the incidents synchronized.</span></span> 

<span data-ttu-id="3af38-108">Nachdem Sie den Connector hinzugefügt haben, werden Microsoft 365 Defender-Vorfälle, &mdash; die alle zugehörigen Warnungen, Entitäten und relevanten Informationen enthalten, die von Microsoft Defender für Endpunkt, Microsoft Defender for Identity, Microsoft Defender für Office 365 und Microsoft Cloud App Security empfangen &mdash; werden, als SIEM-Daten (Security Information and Event Management) an Azure Sentinel gestreamt, sodass Sie kontextbezogen sind, um Triage- und Vorfallreaktionen mit Azure Sentinel durchzuführen.</span><span class="sxs-lookup"><span data-stu-id="3af38-108">Once you add the connector, Microsoft 365 Defender incidents&mdash;which include all associated alerts, entities, and relevant information received from Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender for Office 365, and Microsoft Cloud App Security&mdash;are streamed to Azure Sentinel as security information and event management (SIEM) data, providing you with context to perform triage and incident response with Azure Sentinel.</span></span> 

<span data-ttu-id="3af38-109">In Azure Sentinel bleiben Vorfälle bidirektional mit Microsoft 365 Defender synchronisiert, sodass Sie die Vorteile sowohl des Microsoft 365 Security Centers als auch von Azure Sentinel im Azure-Portal für die Untersuchung und Reaktion auf Vorfälle nutzen können.</span><span class="sxs-lookup"><span data-stu-id="3af38-109">Once in Azure Sentinel, incidents remain bi-directionally synchronized with Microsoft 365 Defender, allowing you to take advantage of the benefits of both the Microsoft 365 security center and Azure Sentinel in the Azure portal for incident investigation and response.</span></span>

<span data-ttu-id="3af38-110">So funktioniert es.</span><span class="sxs-lookup"><span data-stu-id="3af38-110">Here's how it works.</span></span>

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Der Fluss und die Freigabe von Vorfalldaten zwischen Microsoft 365 Defender und Azure Sentinel":::

## <a name="next-steps"></a><span data-ttu-id="3af38-112">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="3af38-112">Next steps</span></span>

1. <span data-ttu-id="3af38-113">Erhalten Sie ein tieferes Verständnis der [Microsoft 365 Defender-Integration in Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)</span><span class="sxs-lookup"><span data-stu-id="3af38-113">Get a deeper understanding of [Microsoft 365 Defender integration with Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).</span></span>
2. <span data-ttu-id="3af38-114">[Verbinden Daten von Microsoft 365 Defender zu Azure Sentinel.](/azure/sentinel/connect-microsoft-365-defender)</span><span class="sxs-lookup"><span data-stu-id="3af38-114">[Connect data from Microsoft 365 Defender to Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).</span></span>

## <a name="see-also"></a><span data-ttu-id="3af38-115">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="3af38-115">See also</span></span>

- [<span data-ttu-id="3af38-116">Übersicht über Vorfälle in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="3af38-116">Overview of incidents in Microsoft 365 Defender</span></span>](incidents-overview.md)
- [<span data-ttu-id="3af38-117">Untersuchen von Vorfällen mit Azure Sentinel</span><span class="sxs-lookup"><span data-stu-id="3af38-117">Investigate incidents with Azure Sentinel</span></span>](/azure/sentinel/tutorial-investigate-cases)
