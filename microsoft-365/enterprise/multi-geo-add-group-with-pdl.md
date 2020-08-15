---
title: Erstellen einer Microsoft 365-Gruppe mit einer bestimmten PDL
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: In diesem Artikel erfahren Sie, wie Sie eine Microsoft 365-Gruppe mit einem angegebenen bevorzugten Datenspeicherort in einer Multi-Geo-Umgebung erstellen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0906d0b4881dd69bbf47cbb536c6c448a1a4f611
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690603"
---
# <a name="create-a-microsoft-365-group-with-a-specific-pdl"></a>Erstellen einer Microsoft 365-Gruppe mit einer bestimmten PDL

Wenn Benutzer in einer Multi-Geo-Umgebung eine Microsoft 365-Gruppe erstellen, wird der bevorzugte Datenspeicherort der Gruppe automatisch auf den des Benutzers festgelegt. Globale, SharePoint- und Exchange-Administratoren können Gruppen in jeder ausgewählten Region erstellen. 

Wenn Sie eine Gruppe mit einem bestimmten PLD erstellen möchten, können Sie dies über das SharePoint Admin Center oder unter Verwendung des Exchange Online New-UnifiedGroup Microsoft PowerShell-Cmdlets vornehmen. Wenn Sie dies tun, werden das zugewiesene Gruppenpostfach und die SharePoint-Website für die Gruppe der angegebenen Verteilerliste an diesem bestimmten PLD bereitgestellt.

Um eine Microsoft 365-Gruppe mit der von Ihnen angegebenen PDL zu erstellen, wechseln Sie zum SharePoint Admin Center am geografischen Speicherort, an dem Sie die Gruppen Website erstellen möchten.

Zum Beispiel:

Wenn Sie eine Gruppenwebsite an Ihrem Standort in Australien erstellen möchten, wechseln Sie zu https://ContosoAUS-admin.sharepoint.com/_layouts/15/online/AdminHome.aspx#/siteManagement.

1. Wählen Sie **+ Erstellen** aus.
2. Führen Sie den Vorgang zum Erstellen einer Gruppenwebsite aus.

Ihre Gruppenwebsite wird an dem geografischen Standort bereitgestellt, der dem SharePoint Admin Center entspricht, von dem aus Sie die Anforderung für die Websiteerstellung initiiert haben. 

Verwenden von Exchange PowerShell 

Stellen Sie eine Verbindung zu Exchange Online PowerShell her, und geben Sie den Parameter *-MailBoxRegion* mit dem Code des geografischen Standorts weiter.

Zum Beispiel: 

```PowerShell
New-UnifiedGroup -DisplayName MultiGeoEUR -Alias "MultiGeoEUR" -AccessType Public -MailboxRegion EUR 
```

![Screenshot des New-UnifiedGroup PowerShell cmdlet mit Syntax](../media/multi-geo-new-group-with-pdl-powershell.png)

Beachten Sie, dass die Bereitstellung von SharePoint-Gruppenseiten nach Bedarf erfolgt. Die Seite wird bereitgestellt, wenn ein Gruppenbesitzer oder -mitglied zum ersten Mal auf diese zugreift.

## <a name="geo-location-codes"></a>Codes für geografische Standorte

[!INCLUDE [Microsoft 365 Multi-Geo locations](../includes/microsoft-365-multi-geo-locations.md)]

## <a name="related-topics"></a>Verwandte Themen

[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).
