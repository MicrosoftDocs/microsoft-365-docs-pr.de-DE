---
title: Funktionsweise von DLP mit Security & Compliance Center & Exchange Admin Center
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Erfahren Sie, wie DLP im Security & Compliance Center mit DLP und Nachrichtenflussregeln (Transportregeln) im Exchange Admin Center funktioniert.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: c5249279e1dd04447235aae813128cf458adde03
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114073"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>Funktionsweise von DLP zwischen dem Security & Compliance Center und Exchange Admin Center

In Office 365 können Sie eine Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) in zwei verschiedenen Admin Centern erstellen:
  
- Im **Security & Compliance Center** können Sie eine einzelne & erstellen, um Inhalte in SharePoint, OneDrive, Exchange und jetzt Microsoft Teams zu schützen. Wenn möglich, wird empfohlen, hier eine DLP-Richtlinie zu erstellen. Weitere Informationen finden Sie unter [Data Loss Prevention reference](data-loss-prevention-policies.md).
    
- Im **Exchange Admin Center** können Sie eine DLP-Richtlinie erstellen, um Inhalte nur in Exchange zu schützen. Diese Richtlinie kann Exchange-Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, sodass sie mehr Optionen für die Verarbeitung von E-Mails bietet. Weitere Informationen finden Sie unter [DLP im Exchange Admin Center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).
    
In diesen Admin Centern erstellte DLP-Richtlinien funktionieren nebeneinander – in diesem Thema wird die Funktionsweise erläutert.
  
![DLP-Seiten im Security and Compliance Center und Exchange Admin Center](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Funktionsweise von DLP im Security & Compliance Center mit DLP- und Nachrichtenflussregeln im Exchange Admin Center

Nachdem Sie eine DLP-Richtlinie im Security & Compliance Center erstellt haben, wird die Richtlinie an allen In der Richtlinie enthaltenen Speicherorten bereitgestellt. Wenn die Richtlinie Exchange Online enthält, wird die Richtlinie dort synchronisiert und auf die gleiche Weise erzwungen wie eine im Exchange Admin Center erstellte DLP-Richtlinie. 
  
Wenn Sie im Exchange Admin Center DLP-Richtlinien erstellt haben, funktionieren diese Richtlinien weiterhin nebeneinander mit allen Richtlinien für E-Mails, die Sie im Security & Compliance Center erstellen. Beachten Sie jedoch, dass im Exchange Admin Center erstellte Regeln Vorrang haben. Alle Exchange-Nachrichtenflussregeln werden zuerst verarbeitet, und dann werden die DLP-Regeln aus dem Security & Compliance Center verarbeitet.
  
Dies bedeutet:
  
- Nachrichten, die von Exchange-Nachrichtenflussregeln blockiert werden, werden nicht von im Security & Compliance Center erstellten DLP-Regeln überprüft.
    
- Wenn eine Exchange-Nachrichtenflussregel eine Nachricht so ändert, dass sie einer DLP-Richtlinie im Security & Compliance Center - z. B. dem Hinzufügen externer Benutzer - zu entsprechen hat, erkennen die DLP-Regeln dies und erzwingen die Richtlinie bei Bedarf.
    
Beachten Sie außerdem, dass sich Exchange-Nachrichtenflussregeln, die die Aktion "Verarbeitung beenden" verwenden, nicht auf die Verarbeitung von DLP-Regeln im Security & Compliance Center auswirken – sie werden weiterhin verarbeitet.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Richtlinientipps im Security & Compliance Center im Vergleich zum Exchange Admin Center

Richtlinientipps können entweder mit im Exchange Admin Center erstellten DLP-Richtlinien und Nachrichtenflussregeln oder mit im Security & Compliance Center erstellten DLP-Richtlinien funktionieren, jedoch nicht mit beiden. Dies liegt daran, dass diese Richtlinien an unterschiedlichen Speicherorten gespeichert werden, Richtlinientipps können jedoch nur von einem einzigen Speicherort aus zeichnen.
  
Wenn Sie Richtlinientipps im Exchange Admin Center konfiguriert haben, werden alle Richtlinientipps, die Sie im Security & Compliance Center konfigurieren, benutzern in Outlook im Web und Outlook 2013 und höher erst angezeigt, wenn Sie die Tipps im Exchange Admin Center deaktivieren. Dadurch wird sichergestellt, dass Ihre aktuellen Exchange-Nachrichtenflussregeln weiterhin funktionieren, bis Sie zum Security & Compliance Center wechseln.
  
Beachten Sie, dass Richtlinientipps zwar nur von einem einzigen Speicherort aus zeichnen können, E-Mail-Benachrichtigungen jedoch immer gesendet werden, auch wenn Sie DLP-Richtlinien sowohl im Security & Compliance Center als auch im Exchange Admin Center verwenden.
