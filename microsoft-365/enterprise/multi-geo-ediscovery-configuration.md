---
title: Konfigurieren von Microsoft 365 Multi-Geo eDiscovery
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
localization_priority: Normal
ms.collection: Strat_SP_gtc
description: In diesem Artikel erfahren Sie, wie Sie mithilfe des Parameters Region eDiscovery für die Verwendung an Satellitenstandorten in Microsoft 365 Multi-Geo konfigurieren.
ms.openlocfilehash: d1d66a9e7953b540e318c8364bdcb8d72654b482
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48636805"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Konfiguration von Microsoft 365 Multi-Geo eDiscovery

Mit den [erweiterten eDiscovery-Funktionen](https://docs.microsoft.com/microsoft-365/compliance/overview-ediscovery-20) kann ein Multi-Geo-eDiscovery-Administrator alle GEOSS durchsuchen, ohne einen Sicherheitsfilter für die Region verwenden zu müssen. Daten werden in die Azure-Instanz des zentralen Speicherorts des Multi-Geo-Mandanten exportiert. 

Ohne erweiterte eDiscovery-Funktionen kann ein eDiscovery-Manager oder Administrator eines Multi-Geo-Mandanten eDiscovery nur am zentralen Standort dieses Mandanten durchführen. Um die Möglichkeit zur Durchführung von eDiscovery für Satellitenstandorte zu unterstützen, steht ein neuer Kompatibilitäts Sicherheitsfilter Parameter mit dem Namen "Region" über PowerShell zur Verfügung. Dieser Parameter kann von Mandanten verwendet werden, deren zentraler Standort in Nordamerika, Europa oder im asiatisch-pazifischen Raum liegt. Erweiterte eDiscovery wird für Mandanten empfohlen, deren zentraler Standort nicht in Nordamerika, Europa oder im asiatisch-pazifischen Raum liegt und die eDiscovery über Satelliten geografische Standorte hinweg ausführen müssen. 

Der globale Microsoft 365-Administrator muss eDiscovery-Managerberechtigungen zuweisen, damit andere Personen eDiscovery durchführen können, und einen "Region"-Parameter im entsprechenden Compliancesicherheitsfilter zuweisen, um die Region zum Durchführen von eDiscovery als Satellitenstandort festzulegen. Andernfalls wird eDiscovery nicht für den Satellitenstandort durchgeführt werden.

Wenn die eDiscovery-Manager- oder Administratorrolle für einen bestimmten Satellitenstandort festgelegt ist, kann der eDiscovery-Manager oder Administrator nur eDiscovery-Suchaktionen für die SharePoint-Websites und OneDrive-Websites an diesem Satellitenstandort durchführen. Wenn ein eDiscovery-Manager oder Administrator versucht, SharePoint- oder OneDrive-Websites außerhalb des angegebenen Satellitenstandorts zu durchsuchen, werden keine Ergebnisse zurückgegeben. Wenn der eDiscovery-Manager oder Administrator für einen Satellitenstandort einen Export auslöst, werden Daten in der Azure-Instanz dieses Bereichs exportiert. So können Organisationen Compliance gewährleisten, indem nicht zugelassen wird, dass Inhalte über den kontrollierten Rahmen hinaus exportiert werden.

> [!NOTE]
> Wenn ein eDiscovery-Manager mehrere SharePoint-Satellitenstandorte durchsuchen möchte, muss ein anderes Benutzerkonto für den eDiscovery-Manager erstellt werden, das den alternativen Satellitenstandort angibt, in dem sich OneDrive- oder SharePoint-Websites befinden.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

So legen Sie den Compliancesicherheitsfilter für eine Region fest

1. [Herstellen einer Verbindung mit Microsoft 365 Security Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)

2. Verwenden Sie die folgende Syntax:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Zum Beispiel:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Informationen zu weiteren Parametern und zur Syntax finden Sie im Artikel [New-ComplianceSecurityFilter](https://docs.microsoft.com/powershell/module/exchange/new-compliancesecurityfilter).
