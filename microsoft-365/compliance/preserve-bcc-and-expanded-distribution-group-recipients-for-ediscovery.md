---
title: Speichern von Bcc-Empfängern und Empfängern aus erweiterten Verteilergruppen für eDiscovery
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 6/19/2017
audience: ITPro
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: eb8ddf15-0080-457e-9d83-e73e193da334
description: In-Place Aufbewahrungs-, Microsoft 365- und Aufbewahrungsrichtlinien ermöglichen ihnen das Beibehalten von Postfachinhalten, um gesetzliche Vorschriften und eDiscovery-Anforderungen zu erfüllen.
ms.openlocfilehash: f00ed951fb68778b9c62ae874c2cca964bd6cb5c
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927941"
---
# <a name="preserve-bcc-and-expanded-distribution-group-recipients-for-ediscovery"></a>Speichern von Bcc-Empfängern und Empfängern aus erweiterten Verteilergruppen für eDiscovery
  
In-Place Aufbewahrungs-, Microsoft 365- und Microsoft 365-Aufbewahrungsrichtlinien [(die](./retention.md) im Security & Compliance Center erstellt wurden) ermöglichen es Ihnen, Postfachinhalte zu erhalten, um gesetzliche Vorschriften und eDiscovery-Anforderungen zu erfüllen. Informationen zu Empfängern, die direkt in den Feldern An und Cc einer Nachricht adressiert sind, sind standardmäßig in allen Nachrichten enthalten. Ihre Organisation erfordert jedoch möglicherweise die Möglichkeit, Details zu allen Empfängern einer Nachricht zu suchen und zu reproduzieren. Dies umfasst Folgendes:
  
- **Empfänger, die mithilfe des Felds Bcc einer Nachricht adressiert werden:** Bcc-Empfänger werden in der Nachricht im Postfach des Absenders gespeichert, aber nicht in Kopfzeilen der An Empfänger zugestellten Nachricht enthalten. 
    
- **Empfänger erweiterter Verteilergruppen:** Empfänger, die die Nachricht empfangen, weil sie Mitglieder einer Verteilergruppe sind, an die die Nachricht adressiert wurde, entweder in den Feldern An, Cc oder Bcc. 
    
Exchange Online und Exchange Server 2013 (kumulatives Update 7 und höher) behalten Informationen zu Bcc-Empfängern und Empfängern in erweiterten Verteilergruppen bei. Sie können nach diesen Informationen suchen, indem Sie eine In-Place eDiscovery-Suche im Exchange Admin Center (EAC) oder eine Inhaltssuche im Security & Compliance Center verwenden. 
  
## <a name="how-bcc-recipients-and-expanded-distribution-group-recipients-are-preserved"></a>Wie Bcc-Empfänger und Empfänger in erweiterten Verteilergruppen beibehalten werden

Wie schon zuvor erwähnt werden Informationen über Bcc-Empfänger mit der Nachricht im Postfach des Absenders gespeichert. Diese Informationen werden indiziert und stehen dann in eDiscovery und im Archiv zur Verfügung. 
  
Informationen über Empfänger in erweiterten Verteilergruppen werden mit der Nachricht gespeichert, nachdem Sie ein Postfach in das Compliance-Archiv verschoben oder einem Beweissicherungsverfahren unterzogen haben. In Office 365 werden diese Informationen auch gespeichert, wenn Microsoft 365 Aufbewahrungsrichtlinie auf ein Postfach angewendet wird. Die Mitgliedschaft in einer Verteilergruppe wird zu dem Zeitpunkt festgelegt, zu dem die Nachricht gesendet wird. Die mit der Nachricht gespeicherte erweiterte Empfängerliste ist nicht von Änderungen an der Mitgliedschaft betroffen, die nach dem Senden der Nachricht erfolgen. 
  
| Informationen über... | Werden gespeichert in... | Werden standardmäßig gespeichert... | Sind zugänglich für… |
|:-----|:-----|:-----|:-----|
|Felder "An" und "Cc"  <br/> |Nachrichteneigenschaften in den Postfächer des Absenders und der Empfänger  <br/> |Ja  <br/> |Absender, Empfänger und Compliance Officers  <br/> |
|Bcc-Empfänger  <br/> |Nachrichteneigenschaft im Postfach des Absenders  <br/> |Ja  <br/> |Absender, Empfänger und Compliance Officers  <br/> |
|Empfänger in erweiterten Verteilergruppen  <br/> |Nachrichteneigenschaften im Postfach des Absenders  <br/> |Keine. Empfängerinformationen für erweiterte Verteilergruppen werden gespeichert, nachdem ein Postfach in einem In-Place oder einem Prozessaufbewahrungsverfahren platziert oder einer Aufbewahrungsrichtlinie Microsoft 365 zugewiesen wurde.  <br/> |Compliance-Beauftragte  <br/> |
   
## <a name="searching-for-messages-sent-to-bcc-and-expanded-distribution-group-recipients"></a>Suche nach an Bcc-Empfänger oder an Empfänger in erweiterten Verteilergruppen gesendeten Nachrichten

Bei der Suche nach Nachrichten an einen bestimmten Empfänger enthalten eDiscovery-Suchergebnisse nun auch Nachrichten an Verteilergruppen, deren Mitglied der Empfänger ist. In der folgenden Tabelle werden die Szenarien gezeigt, in denen an Bcc-Empfänger oder an Empfänger in erweiterten Verteilergruppen gesendete Nachrichten in eDiscovery-Suchen zurückgegeben werden.
  
Szenario 1: John ist ein Mitglied der Verteilergruppe Vertrieb USA. Diese Tabelle zeigt die eDiscovery-Suchergebnisse, die zurückgegeben werden, wenn Bob eine Nachricht direkt oder (über eine Verteilergruppe) indirekt an John sendet.
  
| Wenn Sie in Bobs Postfach nach gesendeten Nachrichten suchen... | Und die Nachricht gesendet wird mit... | Enthalten die Ergebnisse die Nachricht... |
|:-----|:-----|:-----|
|An:John  <br/> |John in "An"  <br/> |Ja  <br/> |
|An:John  <br/> |Vertrieb USA in "An"  <br/> |Ja  <br/> |
|An:Vertrieb USA  <br/> |Vertrieb USA in "An"  <br/> |Ja  <br/> |
|Cc:John  <br/> |John auf CC  <br/> |Ja  <br/> |
|Cc:John  <br/> |Vertrieb USA auf CC  <br/> |Ja  <br/> |
|Cc:Vertrieb USA  <br/> |Vertrieb USA auf CC  <br/> |Ja  <br/> |
   
Szenario 2: Bob sendet eine E-Mail an John (An/Cc) und Jack (direkt über BCC oder indirekt über eine Verteilergruppe). Die folgende Tabelle zeigt eDiscovery-Suchergebnisse.
  
| Bei der Suche... | Nach gesendeten Nachrichten... | Enthalten die Ergebnisse die Nachricht... | Hinweise |
|:-----|:-----|:-----|:-----|
|Bobs Postfach  <br/> |An/Cc:John  <br/> |Ja  <br/> |Gibt an, dass Jack auf Bcc stand  <br/> |
|Bobs Postfach  <br/> |Bcc:Jack  <br/> |Ja  <br/> |Gibt an, dass Jack auf Bcc stand  <br/> |
|Bobs Postfach  <br/> |Bcc:Jack (über Verteilergruppe)  <br/> |Ja  <br/> |Liste der Mitglieder der Bcc'ed-Verteilergruppe, die beim Senden der Nachricht erweitert wurde, wird in der eDiscovery-Suchvorschau, dem Export und den Protokollen angezeigt.  <br/> |
|Johns Postfach  <br/> |An/Cc:John  <br/> |Ja  <br/> |Keine Hinweise auf Bcc-Empfänger.  <br/> |
|Johns Postfach  <br/> |Bcc:Jack (direkt oder über Verteilergruppe)  <br/> |Nein  <br/> |Bcc-Informationen werden nicht in der an die Empfänger gesendeten Nachricht gespeichert. Sie müssen das Postfach des Absenders durchsuchen.  <br/> |
|Jacks Postfach  <br/> |An/Cc:John (direkt oder über Verteilergruppe)  <br/> |Ja  <br/> |An/Cc-Informationen sind in der an alle Empfänger gesendeten Nachricht enthalten.  <br/> |
|Jacks Postfach  <br/> |Bcc:Jack (direkt oder über Verteilergruppe)  <br/> |Nein  <br/> |Bcc-Informationen werden nicht in der an die Empfänger gesendeten Nachricht gespeichert. Sie müssen das Postfach des Absenders durchsuchen.  <br/> |
   
## <a name="frequently-asked-questions"></a>Häufig gestellte Fragen

 **F. Wann und wo werden die Bcc-Empfänger-Informationen gespeichert?**
  
A. Informationen über einen Bcc-Empfänger werden standardmäßig in der ursprünglichen Nachricht im Postfach des Absenders gespeichert. Wenn es sich bei dem Bcc-Empfänger um eine Verteilergruppe handelt, wird die Mitgliedschaft in Verteilergruppen nur erweitert, wenn das Postfach des Absenders in der Warteschleife ist oder einer aufbewahrungsrichtlinie Microsoft 365 zugewiesen ist.
  
 **F. Wann und wo wird die Liste der Empfänger in erweiterten Verteilergruppen gespeichert?**
  
A. Die Mitgliedschaft in einer Verteilergruppe wird zu dem Zeitpunkt erweitert, zu dem die Nachricht gesendet wird. Die Liste der Mitglieder erweiterter Verteilergruppen wird in der ursprünglichen Nachricht im Postfach des Absenders gespeichert. Das Postfach des Absenders muss sich im In-Place, dem Aufbewahrungsverfahren oder einer Aufbewahrungsrichtlinie Microsoft 365 sein.
  
 **F. Können die unter An/Cc aufgeführten Empfänger sehen, welche Empfänger auf Bcc stehen?**
  
A. Nein. Diese Informationen sind nicht in den Nachrichtenkopfzeilen enthalten und nicht für die Empfänger unter An/Cc sichtbar. Der Absender kann das Bcc-Feld in der ursprünglichen Nachricht sehen, die in seinem Postfach gespeichert wird. Compliance Officers können diese Informationen sehen, wenn Sie das Postfach des Absenders durchsuchen.
  
 **F. Wie kann ich sicherstellen, dass Empfänger erweiterter Verteilergruppen immer erhalten bleiben?**
  
A. Um sicherzustellen, dass Mitglieder erweiterter Verteilergruppen immer mit einer Nachricht beibehalten [werden,](/Exchange/policy-and-compliance/holds/place-all-mailboxes-on-hold) platzieren Sie alle Postfächer in einem Archiv, oder erstellen Sie eine organisationsweite Microsoft 365 Aufbewahrungsrichtlinie. 
  
 **F. Welche Arten von Gruppen werden unterstützt?**
  
A. Verteilergruppen, E-Mail-aktivierte Sicherheitsgruppen und dynamische Verteilergruppen werden unterstützt. 
  
 **F. Ist die Anzahl der Empfänger in Verteilergruppen, die erweitert und in der Nachricht gespeichert werden können, begrenzt?**
  
A. Bis zu 10.000 Mitglieder einer Verteilergruppe werden gespeichert.
  
 **F. Werden geschachtelte Verteilergruppen unterstützt?**
  
A. Ja, 25 Ebenen von geschachtelten Verteilergruppen werden erweitert.
  
 **F. Wo sind die Informationen über Bcc-Empfänger und Empfänger in erweiterten Verteilergruppen sichtbar?**
  
A. Die Informationen über Bcc-Empfänger und Empfänger in erweiterten Verteilergruppen sind für Compliance Officers sichtbar, wenn sie eine eDiscovery-Suche durchführen. Bcc-Empfänger und Empfänger in erweiterten Verteilergruppen sind in den Suchergebnissen, die in ein Discoverypostfach kopiert oder in eine PST-Datei exportiert werden, sowie im eDiscovery-Protokoll enthalten, das Teil der Suchergebnisse ist. Die Informationen über Bcc-Empfänger sind auch in der Suchvorschau verfügbar.
  
 **F. Was passiert, wenn ein Mitglied einer Verteilergruppe aus der globalen Adressliste (GAL) Ihrer Organisation ausgeblendet ist?**
  
A. Dies hat keine Auswirkungen. Wenn Empfänger in der GAL ausgeblendet sind, sind sie weiterhin in der Liste der Empfänger für die erweiterte Verteilergruppe enthalten.