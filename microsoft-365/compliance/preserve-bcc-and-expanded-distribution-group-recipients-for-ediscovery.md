---
title: Speichern von Bcc-Empfängern und Empfängern aus erweiterten Verteilergruppen für eDiscovery
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: In-situ-Speicher, Beweissicherungsverfahren und Office 365 Aufbewahrungsrichtlinien können Sie Postfachinhalte beibehalten, um die behördlichen Vorschriften und eDiscovery-Anforderungen einzuhalten.
ms.openlocfilehash: 46ec9f39f4fe5629ca1854fab44304f30784dbf4
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2019
ms.locfileid: "38686154"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>Speichern von Bcc-Empfängern und Empfängern aus erweiterten Verteilergruppen für eDiscovery
  
In-situ-Speicher, Beweissicherungsverfahren und [Office 365-Aufbewahrungsrichtlinien](https://go.microsoft.com/fwlink/?LinkID=827811) (erstellt im Security #a0 Compliance Center) ermöglichen Ihnen das Beibehalten von Postfachinhalten, um die behördlichen Vorschriften und eDiscovery-Anforderungen zu erfüllen. Informationen über Empfänger, die direkt in den Feldern "An" und "Cc" einer Nachricht adressiert werden, sind standardmäßig in allen Nachrichten enthalten, aber in Ihrer Organisation kann es erforderlich sein, nach detaillierten Informationen über alle Empfänger einer Nachricht zu suchen und sie zu reproduzieren. Dazu gehört Folgendes: 
  
- **Empfänger, die über das Feld "Bcc" einer Nachricht adressiert werden:** BCC-Empfänger werden in der Nachricht im Postfach des Absenders gespeichert, jedoch nicht in den Kopfzeilen der Nachricht, die an die Empfänger gesendet wird. 
    
- **Erweiterte Verteilergruppenempfänger:** Empfänger, die die Nachricht erhalten, weil Sie Mitglieder einer Verteilergruppe sind, an die die Nachricht adressiert war, entweder in den Feldern an, CC oder Bcc. 
    
Exchange Online und Exchange Server 2013 (kumulatives Update 7 und höher) behalten Informationen zu Bcc-Empfängern und Empfängern in erweiterten Verteilergruppen bei. Sie können diese Informationen mithilfe einer Compliance-eDiscovery-Suche im Exchange Admin Center (EAC) oder einer Inhaltssuche im Security #a0 Compliance Center durchsuchen. 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Wie Bcc-Empfänger und Empfänger in erweiterten Verteilergruppen beibehalten werden

Wie schon zuvor erwähnt werden Informationen über Bcc-Empfänger mit der Nachricht im Postfach des Absenders gespeichert. Diese Informationen werden indiziert und stehen dann in eDiscovery und im Archiv zur Verfügung. 
  
Informationen über Empfänger in erweiterten Verteilergruppen werden mit der Nachricht gespeichert, nachdem Sie ein Postfach in das Compliance-Archiv verschoben oder einem Beweissicherungsverfahren unterzogen haben. In Office 365 werden diese Informationen auch gespeichert, wenn eine Office 365-Aufbewahrungsrichtlinie auf ein Postfach angewendet wird. Die Mitgliedschaft in einer Verteilergruppe wird zu dem Zeitpunkt festgelegt, zu dem die Nachricht gesendet wird. Die mit der Nachricht gespeicherte erweiterte Empfängerliste ist nicht von Änderungen an der Mitgliedschaft betroffen, die nach dem Senden der Nachricht erfolgen. 
  
|**Informationen über...**|**Werden gespeichert in...**|**Werden standardmäßig gespeichert...**|**Sind zugänglich für…**|
|:-----|:-----|:-----|:-----|
|Felder "An" und "Cc"  <br/> |Nachrichteneigenschaften in den Postfächer des Absenders und der Empfänger  <br/> |Ja  <br/> |Absender, Empfänger und Compliance Officers  <br/> |
|Bcc-Empfänger  <br/> |Nachrichteneigenschaft im Postfach des Absenders  <br/> |Ja  <br/> |Absender, Empfänger und Compliance Officers  <br/> |
|Empfänger in erweiterten Verteilergruppen  <br/> |Nachrichteneigenschaften im Postfach des Absenders  <br/> |Keine. Die Informationen über die Empfänger in erweiterten Verteilergruppen werden gespeichert, nachdem ein Postfach in einem In-Situ-Speicher platziert oder ein Beweissicherungsverfahren für das Postfach aktiviert oder einer Office 365-Aufbewahrungsrichtlinie zugewiesen worden ist.  <br/> |Compliance Officers  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Suche nach an Bcc-Empfänger oder an Empfänger in erweiterten Verteilergruppen gesendeten Nachrichten

Bei der Suche nach Nachrichten an einen bestimmten Empfänger enthalten eDiscovery-Suchergebnisse nun auch Nachrichten an Verteilergruppen, deren Mitglied der Empfänger ist. In der folgenden Tabelle werden die Szenarien gezeigt, in denen an Bcc-Empfänger oder an Empfänger in erweiterten Verteilergruppen gesendete Nachrichten in eDiscovery-Suchen zurückgegeben werden.
  
Szenario 1: John ist ein Mitglied der Verteilergruppe Vertrieb USA. Diese Tabelle zeigt die eDiscovery-Suchergebnisse, die zurückgegeben werden, wenn Bob eine Nachricht direkt oder (über eine Verteilergruppe) indirekt an John sendet.
  
|**Wenn Sie in Bobs Postfach nach gesendeten Nachrichten suchen...**|**Und die Nachricht gesendet wird mit...**|**Enthalten die Ergebnisse die Nachricht...**|
|:-----|:-----|:-----|
|An:John  <br/> |John in "An"  <br/> |Ja  <br/> |
|An:John  <br/> |Vertrieb USA in "An"  <br/> |Ja  <br/> |
|An:Vertrieb USA  <br/> |Vertrieb USA in "An"  <br/> |Ja  <br/> |
|Cc:John  <br/> |John auf CC  <br/> |Ja  <br/> |
|Cc:John  <br/> |Vertrieb USA auf CC  <br/> |Ja  <br/> |
|Cc:Vertrieb USA  <br/> |Vertrieb USA auf CC  <br/> |Ja  <br/> |
   
Szenario 2: Bob sendet eine E-Mail an John (An/Cc) und Jack (direkt über BCC oder indirekt über eine Verteilergruppe). Die folgende Tabelle zeigt eDiscovery-Suchergebnisse.
  
|**Bei der Suche...**|**Nach gesendeten Nachrichten...**|**Enthalten die Ergebnisse die Nachricht...**|**Hinweise**|
|:-----|:-----|:-----|:-----|
|Bobs Postfach  <br/> |An/Cc:John  <br/> |Ja  <br/> |Gibt an, dass Jack auf Bcc stand  <br/> |
|Bobs Postfach  <br/> |Bcc:Jack  <br/> |Ja  <br/> |Gibt an, dass Jack auf Bcc stand  <br/> |
|Bobs Postfach  <br/> |Bcc:Jack (über Verteilergruppe)  <br/> |Ja  <br/> |Liste der Mitglieder der Bcc-Verteilergruppe, die beim Senden der Nachricht erweitert wurde, wird in der eDiscovery-Suchvorschau, im Export und in den Protokollen angezeigt.  <br/> |
|Johns Postfach  <br/> |An/Cc:John  <br/> |Ja  <br/> |Keine Hinweise auf Bcc-Empfänger.  <br/> |
|Johns Postfach  <br/> |Bcc:Jack (direkt oder über Verteilergruppe)  <br/> |Nein  <br/> |Bcc-Informationen werden nicht in der an die Empfänger gesendeten Nachricht gespeichert. Sie müssen das Postfach des Absenders durchsuchen.  <br/> |
|Jacks Postfach  <br/> |An/Cc:John (direkt oder über Verteilergruppe)  <br/> |Ja  <br/> |An/Cc-Informationen sind in der an alle Empfänger gesendeten Nachricht enthalten.  <br/> |
|Jacks Postfach  <br/> |Bcc:Jack (direkt oder über Verteilergruppe)  <br/> |Nein  <br/> |Bcc-Informationen werden nicht in der an die Empfänger gesendeten Nachricht gespeichert. Sie müssen das Postfach des Absenders durchsuchen.  <br/> |
   
## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

 **F. Wann und wo werden die Bcc-Empfänger-Informationen gespeichert?**
  
A. Informationen über einen Bcc-Empfänger werden standardmäßig in der ursprünglichen Nachricht im Postfach des Absenders gespeichert. Wenn der Bcc-Empfänger eine Verteilergruppe ist, wird die Mitgliedschaft in der Verteilergruppe nur erweitert, wenn das Postfach des Absenders archiviert oder einer Office 365-Aufbewahrungsrichtlinie zugewiesen wird.
  
 **F. Wann und wo wird die Liste der Empfänger in erweiterten Verteilergruppen gespeichert?**
  
A. Die Mitgliedschaft in einer Verteilergruppe wird zu dem Zeitpunkt erweitert, zu dem die Nachricht gesendet wird. Die Liste der Mitglieder erweiterter Verteilergruppen wird in der ursprünglichen Nachricht im Postfach des Absenders gespeichert. Für das Postfach des Absenders muss das Compliance-Archiv oder die Beweissicherung aktiviert oder eine Office 365-Aufbewahrungsrichtlinie zugewiesen worden sein.
  
 **F. Können die unter An/Cc aufgeführten Empfänger sehen, welche Empfänger auf Bcc stehen?**
  
A. Nein. Diese Informationen sind nicht in den Nachrichtenkopfzeilen enthalten und nicht für die Empfänger unter An/Cc sichtbar. Der Absender kann das Bcc-Feld in der ursprünglichen Nachricht sehen, die in seinem Postfach gespeichert wird. Compliance Officers können diese Informationen sehen, wenn Sie das Postfach des Absenders durchsuchen.
  
 **F. wie kann ich sicherstellen, dass erweiterte Verteilergruppenempfänger immer beibehalten werden?**
  
A. Um sicherzustellen, dass erweiterte Verteilergruppenmitglieder immer mit einer Nachricht beibehalten werden, [platzieren Sie alle Postfächer in der Warteschleife](https://technet.microsoft.com/library/4c141604-3210-44cc-b98e-f3e0f15613b8.aspx) , oder erstellen Sie eine organisationsweite Office 365 Aufbewahrungsrichtlinie. 
  
 **F. Welche Arten von Gruppen werden unterstützt?**
  
A. Verteilergruppen, E-Mail-aktivierte Sicherheitsgruppen und dynamische Verteilergruppen werden unterstützt. 
  
 **F. Ist die Anzahl der Empfänger in Verteilergruppen, die erweitert und in der Nachricht gespeichert werden können, begrenzt?**
  
A. Bis zu 10.000 Mitglieder einer Verteilergruppe werden gespeichert.
  
 **F. Werden geschachtelte Verteilergruppen unterstützt?**
  
A. Ja, 25 Ebenen von geschachtelten Verteilergruppen werden erweitert.
  
 **F. Wo sind die Informationen über Bcc-Empfänger und Empfänger in erweiterten Verteilergruppen sichtbar?**
  
A. Die Informationen über Bcc-Empfänger und Empfänger in erweiterten Verteilergruppen sind für Compliance Officers sichtbar, wenn sie eine eDiscovery-Suche durchführen. Bcc-Empfänger und Empfänger in erweiterten Verteilergruppen sind in den Suchergebnissen, die in ein Discoverypostfach kopiert oder in eine PST-Datei exportiert werden, sowie im eDiscovery-Protokoll enthalten, das Teil der Suchergebnisse ist. Die Informationen über Bcc-Empfänger sind auch in der Suchvorschau verfügbar.
  
 **F. Was passiert, wenn ein Mitglied einer Verteilergruppe aus der globalen Adressliste (GAL) Ihrer Organisation ausgeblendet ist?**
  
A. Dies hat keine Auswirkungen. Wenn Empfänger aus der GAL ausgeblendet sind, sind Sie weiterhin in der Liste der Empfänger für die erweiterte Verteilergruppe enthalten.
