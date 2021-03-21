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
description: Erfahren Sie, wie Sie den Parameter Region verwenden, um eDiscovery für die Verwendung an Satellitenstandorten in Microsoft 365 Multi-Geo zu konfigurieren.
ms.openlocfilehash: 4d3481fe8b72bb970893ce065293a7a2cc717331
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923720"
---
# <a name="microsoft-365-multi-geo-ediscovery-configuration"></a>Konfiguration von Microsoft 365 Multi-Geo eDiscovery

[Erweiterte eDiscovery-Funktionen](../compliance/overview-ediscovery-20.md) ermöglichen es einem Multi-Geo-eDiscovery-Administrator, alle Geografischen zu durchsuchen, ohne einen "Region"-Sicherheitsfilter verwenden zu müssen. Daten werden in die Azure-Instanz des zentralen Standorts des Multi-Geo-Mandanten exportiert. 

Ohne erweiterte eDiscovery-Funktionen kann ein eDiscovery-Manager oder Administrator eines Multi-Geo-Mandanten eDiscovery nur am zentralen Standort dieses Mandanten durchführen. Um die Möglichkeit zur Durchführung von eDiscovery für Satellitenstandorte zu unterstützen, steht über PowerShell ein neuer Compliancesicherheitsfilterparameter namens "Region" zur Verfügung. Dieser Parameter kann von Mandanten verwendet werden, deren zentraler Standort sich in Nordamerika, Europa oder dem Asiatisch-Pazifischen Raum befindet. Advanced eDiscovery wird für Mandanten empfohlen, deren zentraler Standort sich nicht in Nordamerika, Europa oder dem Asiatisch-Pazifischen Raum befindet und die eDiscovery über geografische Satellitenstandorte hinweg durchführen müssen. 

Der globale Microsoft 365-Administrator muss eDiscovery-Managerberechtigungen zuweisen, damit andere Personen eDiscovery durchführen können, und einen "Region"-Parameter im entsprechenden Compliancesicherheitsfilter zuweisen, um die Region zum Durchführen von eDiscovery als Satellitenstandort festzulegen. Andernfalls wird eDiscovery nicht für den Satellitenstandort durchgeführt werden.

Wenn die eDiscovery-Manager- oder Administratorrolle für einen bestimmten Satellitenstandort festgelegt ist, kann der eDiscovery-Manager oder Administrator nur eDiscovery-Suchaktionen für die SharePoint-Websites und OneDrive-Websites an diesem Satellitenstandort durchführen. Wenn ein eDiscovery-Manager oder Administrator versucht, SharePoint- oder OneDrive-Websites außerhalb des angegebenen Satellitenstandorts zu durchsuchen, werden keine Ergebnisse zurückgegeben. Wenn der eDiscovery-Manager oder Administrator für einen Satellitenstandort einen Export auslöst, werden Daten in der Azure-Instanz dieses Bereichs exportiert. So können Organisationen Compliance gewährleisten, indem nicht zugelassen wird, dass Inhalte über den kontrollierten Rahmen hinaus exportiert werden.

> [!NOTE]
> Wenn ein eDiscovery-Manager mehrere SharePoint-Satellitenstandorte durchsuchen möchte, muss ein anderes Benutzerkonto für den eDiscovery-Manager erstellt werden, das den alternativen Satellitenstandort angibt, in dem sich OneDrive- oder SharePoint-Websites befinden.

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

So legen Sie den Compliancesicherheitsfilter für eine Region fest

1. [Herstellen einer Verbindung mit Microsoft 365 Security Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell)

2. Verwenden Sie die folgende Syntax:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName <TheNameYouWantToAssign> -Region <RegionValue> -Users <UserPrincipalName>
   ```

   Zum Beispiel:

   ```powershell
   New-ComplianceSecurityFilter -Action All -FilterName "NAM eDiscovery Managers" -Region NAM -Users adwood@contoso.onmicrosoft.com
   ```

Informationen zu weiteren Parametern und zur Syntax finden Sie im Artikel [New-ComplianceSecurityFilter](/powershell/module/exchange/new-compliancesecurityfilter).