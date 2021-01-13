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
description: In diesem Artikel werden die Grenzwerte im eDiscovery-Kernfall in Microsoft 365 beschrieben.
ms.openlocfilehash: 43d267acdb0c1fee0202c74832b376e066241d7c
ms.sourcegitcommit: 495b66b77d6dbe6d69e5b06b304089e4e476e568
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/12/2021
ms.locfileid: "49799662"
---
# <a name="limits-in-core-ediscovery"></a>Grenzwerte in Core eDiscovery

In der folgenden Tabelle sind die Grenzwerte für eDiscovery-Kernfälle und -Haltebereich aufgeführt, die einem eDiscovery-Kernfall zugeordnet sind. Weitere Informationen zu Core eDiscovery finden Sie [unter Übersicht über Core eDiscovery](ediscovery-cases.md).
    
  | Beschreibung der Beschränkung | Grenze |
  |:-----|:-----|
  |Maximale Anzahl von Fällen für eine Organisation  <br/> |Keine Begrenzung  <br/> |
  |Maximale Anzahl von Fall-Halte-Ins für eine Organisation  <br/> |10.000  <br/> |
  |Maximale Anzahl von Postfächern in einem Einzelfallspeicher  <br/> |1,000  <br/> |
  |Maximale Anzahl von SharePoint- und OneDrive for #A0 in einem #A1  <br/> |100  <br/> |
  |Die maximale Anzahl von Fällen, die auf der zentralen eDiscovery-Startseite angezeigt werden, und die maximale Anzahl von Elementen, die auf den Registerkarten "Haltebereich", "Suchen" und "Exportieren" in einem Fall angezeigt werden. <sup>1</sup> |1,000|
  |||

   > [!NOTE]
   > <sup>1</sup> Um eine Liste mit mehr als 1.000 Fällen, Halte-, Such- oder Exporten anzeigen zu können, können Sie die entsprechenden Office 365 Security & Compliance -PowerShell-Cmdlets verwenden:
   > 
   > - [Get-ComplianceCase](https://docs.microsoft.com/powershell/module/exchange/get-compliancecase)
   > - [Get-CaseHoldPolicy](https://docs.microsoft.com/powershell/module/exchange/get-caseholdpolicy)
   > - [Get-ComplianceSearch](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearch)
   > - [Get-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/get-compliancesearchaction)

Weitere Informationen zu Beschränkungen im Zusammenhang mit Inhaltssuchen und Exporten im Zusammenhang mit einem Core eDiscovery-Fall finden Sie unter "Grenzwerte für die Inhaltssuche" und ["Core eDiscovery".](limits-for-content-search.md)