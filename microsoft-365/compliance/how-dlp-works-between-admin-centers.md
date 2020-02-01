---
title: Funktionsweise von DLP zwischen dem Security & Compliance Center und Exchange Admin Center
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
description: 'Erfahren Sie, wie DLP im Security #a0 Compliance Center mit DLP-und Nachrichtenfluss Regeln (Transportregeln) in der Exchange-Verwaltungskonsole arbeitet.'
ms.openlocfilehash: a491317727cce571f0f9e1c527557595f6adf7b5
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596512"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a>Funktionsweise von DLP zwischen dem Security & Compliance Center und Exchange Admin Center

In Office 365 können Sie eine DLP-Richtlinie (Data Loss Prevention, Verhinderung von Datenverlust) in zwei verschiedenen Verwaltungszentren erstellen:
  
- Im **Security #a0 Compliance Center**können Sie eine einzelne DLP-Richtlinie erstellen, die zum Schutz von Inhalten in SharePoint, OneDrive, Exchange und jetzt Microsoft Teams beiträgt. Wenn möglich, wird empfohlen, hier eine DLP-Richtlinie zu erstellen. Weitere Informationen finden Sie unter [DLP im Security #a0 Compliance Center](data-loss-prevention-policies.md).
    
- Im **Exchange Admin Center**können Sie eine DLP-Richtlinie erstellen, die den Schutz von Inhalten in Exchange unterstützt. Diese Richtlinie kann Exchange-Nachrichtenfluss Regeln verwenden (auch als Transportregeln bezeichnet), sodass mehr Optionen speziell für die e-Mail-Verarbeitung zur Verfügung stehen. Weitere Informationen finden Sie unter [DLP im Exchange Admin Center](https://go.microsoft.com/fwlink/?linkid=852311).
    
In diesen Verwaltungszentren erstellte DLP-Richtlinien arbeiten nebeneinander – in diesem Thema wird erläutert, wie.
  
![DLP-Seiten im Security and Compliance Center und im Exchange Admin Center](media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a>Funktionsweise von DLP im Security #a0 Compliance Center mit DLP-und Nachrichtenfluss Regeln im Exchange Admin Center

Nachdem Sie eine DLP-Richtlinie im Security #a0 Compliance Center erstellt haben, wird die Richtlinie für alle in der Richtlinie enthaltenen Speicherorte bereitgestellt. Wenn die Richtlinie Exchange Online enthält, wird die Richtlinie dort synchronisiert und genauso erzwungen wie eine in der Exchange-Verwaltungskonsole erstellte DLP-Richtlinie. 
  
Wenn Sie DLP-Richtlinien im Exchange Admin Center erstellt haben, arbeiten diese Richtlinien weiterhin nebeneinander mit allen Richtlinien für e-Mails, die Sie im Security #a0 Compliance Center erstellt haben. Beachten Sie jedoch, dass Regeln, die im Exchange Admin Center erstellt wurden, Vorrang haben. Alle Exchange-Nachrichtenfluss Regeln werden zuerst verarbeitet, und dann werden die DLP-Regeln aus dem Security #a0 Compliance Center verarbeitet.
  
Dies bedeutet, dass:
  
- Nachrichten, die durch Exchange-Nachrichtenfluss Regeln blockiert werden, werden nicht durch DLP-Regeln überprüft, die im Security #a0 Compliance Center erstellt wurden.
    
- Wenn eine Nachricht in einer Exchange-Nachrichtenfluss Regel so geändert wird, dass Sie einer DLP-Richtlinie im Security #a0 Compliance Center wie dem Hinzufügen externer Benutzer entspricht, werden die DLP-Regeln dies erkennen und die Richtlinie nach Bedarf erzwingen.
    
Beachten Sie auch, dass Exchange-Nachrichtenfluss Regeln, die die Aktion "Verarbeitung beenden" verwenden, sich nicht auf die Verarbeitung von DLP-Regeln im Security #a0 Compliance Center auswirken – Sie werden weiterhin verarbeitet.
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a>Richtlinien Tipps im Security #a0 Compliance Center im Vergleich zum Exchange Admin Center

Richtlinien Tipps können entweder mit DLP-Richtlinien und Nachrichtenfluss Regeln funktionieren, die im Exchange Admin Center erstellt wurden, oder mit DLP-Richtlinien, die im Security #a0 Compliance Center erstellt wurden, jedoch nicht in beiden. Dies liegt daran, dass diese Richtlinien an unterschiedlichen Speicherorten gespeichert werden, aber Richtlinien Tipps nur von einem einzelnen Speicherort aus gezeichnet werden können.
  
Wenn Sie Richtlinien Tipps im Exchange Admin Center konfiguriert haben, werden alle Richtlinien Tipps, die Sie im Security #a0 Compliance Center konfigurieren, nicht für Benutzer in Outlook im Internet und Outlook 2013 und höher angezeigt, bis Sie die Tipps im Exchange Admin Center deaktivieren. Dadurch wird sichergestellt, dass Ihre aktuellen Exchange-Nachrichtenfluss Regeln weiterhin funktionieren, bis Sie das Sicherheits #a0 Compliance Center aktivieren.
  
Beachten Sie, dass Richtlinien Tipps zwar nur von einem einzigen Speicherort aus gezeichnet werden können, e-Mail-Benachrichtigungen jedoch immer gesendet werden, selbst wenn Sie DLP-Richtlinien sowohl im Security #a0 Compliance Center als auch im Exchange Admin Center verwenden.
  

