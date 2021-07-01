---
title: Microsoft 365 Defender-Integration in Azure Sentinel
description: Verwenden Sie Azure Sentinel als SIEM für Microsoft 365 Defender Vorfälle und Ereignisse.
keywords: Vorfälle, Warnungen, untersuchen, analysieren, Reaktion, Korrelation, Angriff, Computer, Geräte, Benutzer, Identitäten, Identität, Postfach, E-Mail, 365, Microsoft, m365
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
ms.openlocfilehash: b9a9a6381c93e2d252f75710adc206868c0a5546
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229911"
---
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365 Defender-Integration in Azure Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Der Microsoft 365 Defender Connector für Azure Sentinel (Vorschau) sendet alle Microsoft 365 Defender Vorfall- und Warnungsinformationen an Azure Sentinel und hält die Vorfälle synchronisiert. 

Nachdem Sie den Connector hinzugefügt haben, werden Microsoft 365 Defender Vorfälle, &mdash; die alle zugehörigen Warnungen, Entitäten und relevanten Informationen enthalten, die von Microsoft Defender für Endpunkt, Microsoft Defender for Identity, Microsoft Defender für Office 365 und Microsoft Cloud App Security empfangen &mdash; werden, als SIEM-Daten (Security Information and Event Management) an Azure Sentinel gestreamt, sodass Sie kontextbezogen sind, um Triage- und Vorfallreaktionen mit Azure Sentinel durchzuführen. 

In Azure Sentinel bleiben Vorfälle bidirektional mit Microsoft 365 Defender synchronisiert, sodass Sie die Vorteile sowohl des Microsoft 365 Security Centers als auch von Azure Sentinel im Azure-Portal für die Untersuchung und Reaktion auf Vorfälle nutzen können.

Sehen Sie sich diese kurze Übersicht über die Azure Sentinel-Integration in Microsoft 365 Defender (4 Minuten) an.

<br>

>[!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RWFIRo]


So funktioniert es.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Der Fluss und die Freigabe von Vorfalldaten zwischen Microsoft 365 Defender und Azure Sentinel":::

## <a name="next-steps"></a>Nächste Schritte

1. Erhalten Sie ein tieferes Verständnis der [Microsoft 365 Defender Integration in Azure Sentinel.](/azure/sentinel/microsoft-365-defender-sentinel-integration)
2. [Verbinden Daten von Microsoft 365 Defender zu Azure Sentinel.](/azure/sentinel/connect-microsoft-365-defender)

## <a name="see-also"></a>Siehe auch

- [Übersicht über Vorfälle in Microsoft 365 Defender](incidents-overview.md)
- [Untersuchen von Vorfällen mit Azure Sentinel](/azure/sentinel/tutorial-investigate-cases)
