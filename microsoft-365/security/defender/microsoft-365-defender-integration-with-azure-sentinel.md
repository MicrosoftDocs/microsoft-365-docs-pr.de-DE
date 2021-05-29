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
# <a name="microsoft-365-defender-integration-with-azure-sentinel"></a>Microsoft 365 Defender-Integration in Azure Sentinel

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Der Microsoft 365 Defender Connector für Azure Sentinel (Vorschau) sendet alle Microsoft 365 Defender-Vorfälle und Benachrichtigungen an Azure Sentinel und hält die Vorfälle synchronisiert. 

Nachdem Sie den Connector hinzugefügt haben, werden Microsoft 365 Defender-Vorfälle, die alle zugeordneten Warnungen, Entitäten und relevanten Informationen enthalten, die von Microsoft Defender for Endpoint, Microsoft Defender for Identity, Microsoft Defender für Office 365 und Microsoft Cloud App Security empfangen wurden, als SieM-Daten (Security Information and Event Management, Sicherheitsinformationen und Ereignisverwaltung) an Azure Sentinel gestreamt, um Ihnen Kontext zur Durchführung von Triage- und Vorfallreaktionen mit Azure Sentinel zu &mdash; &mdash; bieten. 

In Azure Sentinel werden Vorfälle weiterhin bidirektional mit Microsoft 365 Defender synchronisiert, sodass Sie die Vorteile des Microsoft 365 Security Centers und von Azure Sentinel im Azure-Portal für die Untersuchung und Reaktion auf Vorfälle nutzen können.

Hier sehen Sie, wie es funktioniert.

:::image type="content" source="../../media/microsoft-365-defender-integration-with-azure-sentinel/microsoft-365-defender-integration-with-azure-sentinel.png" alt-text="Der Fluss und die Freigabe von Vorfalldaten zwischen Microsoft 365 Defender und Azure Sentinel":::

## <a name="next-steps"></a>Nächste Schritte

1. Erhalten Sie ein besseres Verständnis [Microsoft 365 Integration von Defender in Azure Sentinel](/azure/sentinel/microsoft-365-defender-sentinel-integration).
2. [Verbinden daten von Microsoft 365 Defender zu Azure Sentinel](/azure/sentinel/connect-microsoft-365-defender).

## <a name="see-also"></a>Weitere Informationen:

- [Übersicht über Vorfälle in Microsoft 365 Defender](incidents-overview.md)
- [Untersuchen von Vorfällen mit Azure Sentinel](/azure/sentinel/tutorial-investigate-cases)
