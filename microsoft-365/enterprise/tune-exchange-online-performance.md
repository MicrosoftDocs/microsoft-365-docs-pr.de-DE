---
title: Optimieren der Leistung von Exchange Online
ms.author: krowley
author: tracyp
manager: laurawi
ms.date: 12/14/2017
audience: Admin
ms.topic: troubleshooting
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom: Adm_O365
ms.assetid: 026e83cb-a945-4543-97b0-a8af6e80ac61
description: Dieser Artikel enthält allgemeine Tipps und Links zu anderen Ressourcen, die Ihnen mitteilen, wie Sie die Leistung von Exchange Online verbessern können.
ms.openlocfilehash: a7d3268f9f3cf1922319b03cf69d3f044272b27f
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909442"
---
# <a name="tune-exchange-online-performance"></a>Optimieren der Leistung von Exchange Online

Dieser Artikel enthält allgemeine Tipps und Links zu anderen Ressourcen, die Ihnen mitteilen, wie Sie die Leistung von Exchange Online verbessern können, insbesondere vor einer Migration. Dieser Artikel ist Teil des [Projekts Netzwerkplanung und Leistungsoptimierung für Office 365.](./network-planning-and-performance.md)
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Zu berücksichtigende Dinge zur Verbesserung der Exchange Online-Leistung

Um die Geschwindigkeit der Migration zu verbessern und die Bandbreiteneinschränkungen Ihrer Organisation für Exchange Online zu reduzieren, sollten Sie Folgendes beachten:
  
- **Reduzieren Sie die Postfachgrößen.** Die geringere Postfachgröße verbessert die Migrationsgeschwindigkeit. 
    
- **Verwenden Sie die Postfach verschieben-Funktionen mit einer Exchange-Hybridbereitstellung.** Bei einer Exchange-Hybridbereitstellung werden Offline-E-Mails (in Form von . OST-Dateien) erfordert keinen erneuten Download bei der Migration zu Exchange Online. Dadurch werden die Anforderungen an die Downloadbandbreite erheblich reduziert. 
    
- **Planen Sie, dass Postfachbewegungen in Zeiten mit geringem Internetverkehr und geringer lokalen Exchange-Nutzung stattfinden.** Beim Planen von Verschieben werden Migrationsanforderungen an den Postfachreplikationsproxy übermittelt und werden möglicherweise nicht sofort ausgeführt. 
    
- **Verwenden Sie schlanke Popouts für Outlook im Web.** Schlanke Popouts bieten kleinere, weniger arbeitsspeicherintensive Versionen bestimmter E-Mail-Nachrichten in Microsoft Edge oder Internet Explorer, indem einige Komponenten auf dem Server gerendert werden. Weitere Informationen finden Sie unter Verwenden von schlanken Popouts zum Reduzieren des beim [Lesen von E-Mail-Nachrichten verwendeten Arbeitsspeichers.](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf)


## <a name="general-advice"></a>Allgemeine Hinweise

- Stellen Sie sicher, dass die DNS-Suche nach outlook.office.com das MS-Datencenter an einem logischen Eintragsspeicherort für Ihren Standort einbetritt.

- Suchen Sie das Zwischenspeichern von Postfächern, und wählen Sie die entsprechenden Optionen (re. Zwischenspeicherungszeitraum, Zwischenspeicherung freigegebener Postfächer usw.).

- Halten Sie Ihre Outlook-Daten davon ab, VPN-Verbindungen (an eine Zentralstelle) zu übergeben, bevor sie über das Internet übertragen werden.

- Achten Sie darauf, dass Ihre Postfachdaten die Einschränkungen für Ordner- und Elementbeträge einhalten.
    
Weitere Informationen zur Leistung der Exchange-Migration finden Sie unter [Office 365-Migrationsleistung und bewährte Methoden](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).
