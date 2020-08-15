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
description: Dieser Artikel enthält allgemeine Tipps und Links zu anderen Ressourcen, in denen Sie erfahren, wie Sie die Leistung von Exchange Online verbessern.
ms.openlocfilehash: 495b662aa6ef247a5751febbf2d50e1c1f21a44e
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690725"
---
# <a name="tune-exchange-online-performance"></a>Optimieren der Leistung von Exchange Online

Dieser Artikel enthält allgemeine Tipps und Links zu anderen Ressourcen, in denen Sie erfahren, wie Sie die Leistung von Exchange Online verbessern, insbesondere vor einer Migration. Dieser Artikel ist Teil der [Netzwerkplanung und Leistungsoptimierung für Office 365](https://aka.ms/tune) -Projekt.
   
## <a name="things-to-consider-in-order-to-improve-exchange-online-performance"></a>Dinge, die Sie beachten sollten, um Exchange Online Leistung zu verbessern

Um die Geschwindigkeit der Migration zu verbessern und die Bandbreiteneinschränkungen Ihrer Organisation für Exchange Online zu reduzieren, sollten Sie folgendes befolgen:
  
- **Verringern der Postfachgröße** Die geringere Postfachgröße verbessert die Migrations Geschwindigkeit. 
    
- **Verwenden Sie die Post Fach Verschiebefunktionen mit einer Exchange-hybridbereitstellung.** Bei einer Exchange-hybridbereitstellung werden Offline Nachrichten (in Form von. Ost-Dateien) erfordert keinen erneuten Download bei der Migration zu Exchange Online. Dadurch werden die Anforderungen an die Download Bandbreite erheblich reduziert. 
    
- **Planen von Postfachverschiebungen, die während Zeiträumen mit niedrigem Internet Datenverkehr und niedriger lokaler Exchange-Nutzung ausgeführt werden.** Beim Planen von Verschiebungen werden Migrationsanforderungen an den Proxy für die Post Fach Replikation übermittelt und möglicherweise nicht sofort durchgeführt. 
    
- **Verwenden Sie Lean Popouts für Outlook im Internet.** Lean-Popouts bieten kleinere, weniger arbeitsspeicherintensive Versionen bestimmter e-Mail-Nachrichten in Microsoft Edge oder Internet Explorer, indem einige Komponenten auf dem Server gerendert werden. Weitere Informationen finden Sie unter [Verwenden von Lean Popouts zum Reduzieren des beim Lesen von e-Mail-Nachrichten verwendeten Arbeitsspeichers](https://support.office.com/article/a6d6ba01-2562-4c3d-a8f1-78748dd506cf).


## <a name="general-advice"></a>Allgemeine Ratschläge

- Stellen Sie sicher, dass DNS-Lookup für Outlook.Office.com das MS-Datacenter an einem logischen eintragsort für Ihren Standort eingibt.

- Recherchieren Sie die Post Fach Zwischenspeicherung, und wählen Sie die entsprechenden Optionen aus (Re. zwischen Speicherungszeitraum, Zwischenspeicherung von freigegebenen Postfächern, usw.).

- Halten Sie Ihre Outlook-Daten davon ab, VPN-Verbindungen (an ein zentrales Büro) weiterzugeben, bevor Sie über das Internet übermittelt werden.

- Stellen Sie sicher, dass die Postfachdaten den Einschränkungen für Ordner und Element, Beträge entsprechen.
    
Weitere Informationen zur Leistung der Exchange-Migration finden Sie unter [Office 365 Migrationsleistung und bewährte Methoden](https://support.office.com/article/d9acb371-fd6c-4c14-aa8e-db5cbe39aa57).
  

