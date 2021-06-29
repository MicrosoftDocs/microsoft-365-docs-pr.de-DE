---
title: Funktionsweise von DLP mit Security & Compliance Center & Exchange Admin Center
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: Erfahren Sie, wie DLP im Security & Compliance Center mit DLP- und Nachrichtenflussregeln (Transportregeln) im Exchange Admin Center funktioniert.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 34ddee1c1f0997852b6e59295ab9b630acc3ba3c
ms.sourcegitcommit: cfd7644570831ceb7f57c61401df6a0001ef0a6a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53177177"
---
# <a name="how-dlp-works-between-the-microsoft-365-compliance-center-and-exchange-admin-center"></a>Funktionsweise von DLP zwischen dem Microsoft 365 Compliance Center und Exchange Admin Center

In Microsoft 365 können Sie eine Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) in zwei verschiedenen Admin Centern erstellen:
  
- Im **Microsoft 365 Compliance Center** können Sie eine einzelne DLP-Richtlinie erstellen, um Inhalte in SharePoint, OneDrive, Exchange, Teams und jetzt Endpunktgeräten zu schützen. Es wird empfohlen, hier eine DLP-Richtlinie zu erstellen. Weitere Informationen finden Sie in der [Referenz zur Verhinderung von Datenverlust.](data-loss-prevention-policies.md)
    
- Im **Exchange Admin Center** können Sie eine DLP-Richtlinie erstellen, um Inhalte nur in Exchange zu schützen. Diese Richtlinie kann Exchange Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, sodass sie spezifischere Optionen für die Verarbeitung von E-Mails bietet. Weitere Informationen finden Sie unter [DLP im Exchange Admin Center.](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention)
    
DLP-Richtlinien, die in diesen Admin Centern erstellt wurden, arbeiten nebeneinander . In diesem Thema wird erläutert, wie.
  
![DLP-Seiten im Security and Compliance Center und Exchange Admin Center](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Funktionsweise von DLP im Security & Compliance Center mit DLP- und Nachrichtenflussregeln im Exchange Admin Center

Nachdem Sie eine DLP-Richtlinie im Security & Compliance Center erstellt haben, wird die Richtlinie an allen in der Richtlinie enthaltenen Speicherorten bereitgestellt. Wenn die Richtlinie Exchange Online enthält, wird die Richtlinie dort synchronisiert und auf die gleiche Weise wie eine im Exchange Admin Center erstellte DLP-Richtlinie erzwungen. 
  
Wenn Sie DLP-Richtlinien im Exchange Admin Center erstellt haben, funktionieren diese Richtlinien weiterhin seite an Seite mit allen Richtlinien für E-Mails, die Sie im Security & Compliance Center erstellen. Beachten Sie jedoch, dass im Exchange Admin Center erstellte Regeln Vorrang haben. Alle Exchange Nachrichtenflussregeln werden zuerst verarbeitet, und dann werden die DLP-Regeln aus dem Security & Compliance Center verarbeitet.
  
Dies bedeutet Folgendes:
  
- Nachrichten, die durch Exchange Nachrichtenflussregeln blockiert werden, werden nicht durch DLP-Regeln gescannt, die im Security & Compliance Center erstellt wurden.

- Nachrichten, die durch Exchange Nachrichtenflussregeln unter Quarantäne gestellt werden, oder andere Filter, die ausgeführt werden, bevor DLP von DLP gescannt wird
    
- Wenn eine Exchange Nachrichtenflussregel eine Nachricht so ändert, dass sie mit einer DLP-Richtlinie im Security & Compliance Center übereinstimmt , z. B. durch hinzufügen externer Benutzer, werden die DLP-Regeln dies erkennen und die Richtlinie nach Bedarf erzwingen.
    
Beachten Sie außerdem, dass Exchange Nachrichtenflussregeln, die die Aktion "Verarbeitung beenden" verwenden, keine Auswirkungen auf die Verarbeitung von DLP-Regeln im Security & Compliance Center haben – sie werden weiterhin verarbeitet.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Richtlinientipps im Security & Compliance Center im Vergleich zum Exchange Admin Center

Richtlinientipps können entweder mit DLP-Richtlinien und Nachrichtenflussregeln funktionieren, die im Exchange Admin Center erstellt wurden, oder mit DLP-Richtlinien, die im Security & Compliance Center erstellt wurden, aber nicht mit beiden. Dies liegt daran, dass diese Richtlinien an verschiedenen Speicherorten gespeichert werden, Richtlinientipps jedoch nur von einem einzigen Speicherort gezeichnet werden können.
  
Wenn Sie Richtlinientipps im Exchange Admin Center konfiguriert haben, werden alle Richtlinientipps, die Sie im Security & Compliance Center konfigurieren, benutzern in Outlook im Web und Outlook 2013 und höher erst angezeigt, wenn Sie die Tipps im Exchange Admin Center deaktivieren. Dadurch wird sichergestellt, dass Ihre aktuellen Exchange Nachrichtenflussregeln weiterhin funktionieren, bis Sie zum Security & Compliance Center wechseln möchten.
  
Beachten Sie, dass Richtlinientipps zwar nur von einem einzigen Speicherort aus gezeichnet werden können, E-Mail-Benachrichtigungen aber immer gesendet werden, auch wenn Sie DLP-Richtlinien sowohl im Security & Compliance Center als auch im Exchange Admin Center verwenden.
