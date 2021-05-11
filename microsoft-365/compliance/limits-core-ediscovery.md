---
title: Grenzwerte im eDiscovery-Kernfall
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: In diesem Artikel werden die Grenzwerte im eDiscovery-Kernfall in Microsoft 365.
ms.openlocfilehash: e7b1013abd9fd94748baf3b83dd04efbc3831a1d
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311424"
---
# <a name="limits-in-core-ediscovery"></a>Grenzwerte in Core eDiscovery

In der folgenden Tabelle sind die Grenzwerte für eDiscovery-Kernfälle und -Hüllen aufgeführt, die einem eDiscovery-Kernfall zugeordnet sind. Weitere Informationen zu Core eDiscovery finden Sie [unter Overview of Core eDiscovery](./get-started-core-ediscovery.md).
    
  | Beschreibung der Beschränkung | Grenzwert |
  |:-----|:-----|
  |Maximale Anzahl von Fällen für eine Organisation.  <br/> |Keine Begrenzung  <br/> |
  |Maximale Anzahl von Fällen für eine Organisation.  <br/> |10,000  <br/> |
  |Maximale Anzahl von Postfächern in einem einzelnen Fall. Dieser Grenzwert umfasst die gesamtzahl der Benutzerpostfächer und die Postfächer, die Microsoft 365 Gruppen, Microsoft Teams und Yammer zugeordnet sind.  <br/> |1,000  <br/> |
  |Maximale Anzahl von Websites in einem einzigen Fall. Dieser Grenzwert umfasst die gesamtzahl der OneDrive for Business Websites, SharePoint Websites und die Websites, die Microsoft 365-, Microsoft Teams- und Yammer-Gruppen zugeordnet sind.  <br/> |100  <br/> |
  |Maximale Anzahl von Fällen, die auf der eDiscovery-Hauptseite angezeigt werden, und die maximale Anzahl von Elementen, die auf den Registerkarten Halte-, Such- und Exportregisterkarten in einem Fall angezeigt werden. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Zum Anzeigen einer Liste mit mehr als 1.000 Fällen, Halte-, Such- oder Exporten können Sie die entsprechenden Office 365 Security & Compliance-PowerShell-Cmdlets verwenden:
   > 
   > - [Get-ComplianceCase](/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](/powershell/module/exchange/get-compliancesearchaction)

Weitere Informationen zu Beschränkungen im Zusammenhang mit Suchen und Exporten im Zusammenhang mit einem Core eDiscovery-Fall finden Sie unter [Limits for Content search und Core eDiscovery](limits-for-content-search.md).