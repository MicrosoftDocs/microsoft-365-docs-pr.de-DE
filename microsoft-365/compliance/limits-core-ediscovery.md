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
description: In diesem Artikel werden die Grenzen im eDiscovery-Kernfall in Microsoft 365 beschrieben.
ms.openlocfilehash: 2699e9b2511c742bb295f69611a976f6a3955980
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423446"
---
# <a name="limits-in-core-ediscovery"></a>Grenzwerte in Core eDiscovery

In der folgenden Tabelle sind die Grenzwerte für eDiscovery-Kernfälle und -Hüllen aufgeführt, die einem eDiscovery-Kernfall zugeordnet sind. Weitere Informationen zu Core eDiscovery finden Sie [unter Overview of Core eDiscovery](ediscovery-cases.md).
    
  | Beschreibung der Beschränkung | Grenze |
  |:-----|:-----|
  |Maximale Anzahl von Fällen für eine Organisation.  <br/> |Keine Begrenzung  <br/> |
  |Maximale Anzahl von Fällen für eine Organisation.  <br/> |10.000  <br/> |
  |Maximale Anzahl von Postfächern in einem einzelnen Fall. Dieser Grenzwert umfasst die gesamtzahl der Benutzerpostfächer und die Postfächer, die Microsoft 365-Gruppen, Microsoft Teams und Yammer zugeordnet sind.  <br/> |1.000  <br/> |
  |Maximale Anzahl von Websites in einem einzigen Fall. Dieser Grenzwert umfasst die gesamtzahl der OneDrive for #A0 und #A1 sowie die Websites, die Microsoft 365-Gruppen, Microsoft Teams und Yammer zugeordnet sind.  <br/> |100  <br/> |
  |Maximale Anzahl von Fällen, die auf der eDiscovery-Hauptseite angezeigt werden, und die maximale Anzahl von Elementen, die auf den Registerkarten Halte-, Such- und Exportregisterkarten in einem Fall angezeigt werden. <sup>1</sup> |1.000|
  |||

   > [!NOTE]
   > <sup>1</sup> Zum Anzeigen einer Liste mit mehr als 1.000 Fällen, Halte-, Such- oder Exporten können Sie die entsprechenden Office 365 Security & Compliance-PowerShell-Cmdlets verwenden:
   > 
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

Weitere Informationen zu Beschränkungen im Zusammenhang mit Inhaltssuchen und -exporten im Zusammenhang mit einem Core eDiscovery-Fall finden Sie unter [Limits for Content Search und Core eDiscovery](limits-for-content-search.md).