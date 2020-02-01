---
title: Deduplizierung in eDiscovery-Suchergebnissen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 12/21/2016
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid: MOE150
ms.assetid: 5af334b6-a15d-4f73-97f8-1423457d9f6b
description: Sie haben die Möglichkeit, eDiscovery-Suchergebnisse zu deduplizieren, die exportiert werden, sodass nur eine Kopie einer e-Mail-Nachricht exportiert wird, obwohl möglicherweise mehrere Instanzen derselben Nachricht in unterschiedlichen Postfächern gefunden wurden.
ms.openlocfilehash: fa04b83e9ec06b3b0d20d42d3d800040aa6178ed
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595392"
---
# <a name="de-duplication-in-ediscovery-search-results"></a>Deduplizierung in eDiscovery-Suchergebnissen

In diesem Artikel wird beschrieben, wie die Deduplizierung von eDiscovery-Suchergebnissen funktioniert, und es werden die Einschränkungen des Algorithmus für die Deduplizierung erläutert.
  
Wenn Sie Office 365 eDiscovery-Tools verwenden, um die Ergebnisse einer eDiscovery-Suche zu exportieren, haben Sie die Möglichkeit, die exportierten Ergebnisse zu deduplizieren. Szenario Wenn Sie die Deduplizierung aktivieren (Standardmäßig ist die Deduplizierung nicht aktiviert), wird nur eine Kopie einer e-Mail-Nachricht exportiert, obwohl in den durchsuchten Postfächern möglicherweise mehrere Instanzen derselben Nachricht gefunden wurden. Die Deduplizierung hilft Ihnen, Zeit zu sparen, indem die Anzahl der Elemente verringert wird, die Sie nach dem Exportieren der Suchergebnisse überprüfen und analysieren müssen. Es ist jedoch wichtig zu verstehen, wie die Deduplizierung funktioniert, und beachten Sie, dass es Einschränkungen für den Algorithmus gibt, die möglicherweise dazu führen, dass ein eindeutiges Element während des Exportvorgangs als Duplikat markiert wird.
  
## <a name="how-duplicate-messages-are-identified"></a>Identifizieren von doppelten Nachrichten

Office 365 eDiscovery-Tools verwenden Sie eine Kombination der folgenden e-Mail-Eigenschaften, um zu ermitteln, ob eine Nachricht doppelt vorhanden ist:
  
- **InternetMessageId** – diese Eigenschaft gibt den Internet Nachrichtenbezeichner einer e-Mail-Nachricht an, bei der es sich um eine global eindeutige ID handelt, die auf eine bestimmte Version einer bestimmten Nachricht verweist. Diese ID wird vom e-Mail-Clientprogramm des Absenders oder vom Host-e-Mail-System generiert, das die Nachricht sendet. Wenn eine Person eine Nachricht an mehrere Empfänger sendet, ist die Internet Nachrichten-ID für jede Instanz der Nachricht identisch. Bei nachfolgenden Überarbeitungen an die ursprüngliche Nachricht wird eine andere Nachrichtenkennung empfangen. 
    
- **ConversationTopic** -his-Eigenschaft gibt den Betreff des Unterhaltungs Threads einer Nachricht an. Der Wert der **ConversationTopic** -Eigenschaft ist die Zeichenfolge, die das allgemeine Thema der Unterhaltung beschreibt. Eine Bestandserhaltung besteht aus einer anfänglichen Nachricht und allen Nachrichten, die als Antwort auf die ursprüngliche Nachricht gesendet wurden. Nachrichten in derselben Unterhaltung haben denselben Wert für die **ConversationTopic** -Eigenschaft. Der Wert dieser Eigenschaft ist normalerweise die Betreffzeile der anfänglichen Nachricht, die die Unterhaltung hervorgerufen hat. 
    
- **BodyTagInfo** -Dies ist eine interne Exchange-Informationsspeicher Eigenschaft. Der Wert dieser Eigenschaft wird durch Überprüfen verschiedener Attribute im Textkörper der Nachricht berechnet. Diese Eigenschaft wird verwendet, um Unterschiede im Nachrichtentext zu identifizieren. 
    
Während des eDiscovery-Exportprozesses werden diese drei Eigenschaften für jede Nachricht verglichen, die mit den Suchkriterien übereinstimmt. Wenn diese Eigenschaften für zwei (oder mehr) Nachrichten identisch sind, werden diese Nachrichten als Duplikate festgelegt, und das Ergebnis ist, dass nur eine Kopie der Nachricht exportiert wird, wenn die Deduplizierung aktiviert ist. Die exportierte Nachricht wird als "Quellelement" bezeichnet. Informationen zu doppelten Nachrichten sind in den Berichten **results. CSV** und **Manifest. XML** enthalten, die in den exportierten Suchergebnissen enthalten sind. In der Datei **results. CSV** wird eine doppelte Nachricht durch einen Wert in der Spalte **Duplikat zu Element** identifiziert. Der Wert in dieser Spalte stimmt mit dem Wert in der **Element Identitäts** Spalte für die exportierte Nachricht überein. 
  
Die folgenden Grafiken zeigen, wie doppelte Nachrichten in den Berichten **results. CSV** und **Manifest. XML** angezeigt werden, die mit den Suchergebnissen exportiert werden. Diese Berichte enthalten nicht die zuvor beschriebenen e-Mail-Eigenschaften, die im Algorithmus für die Deduplizierung verwendet werden. Stattdessen enthalten die Berichte die **Element Identitäts** Eigenschaft, die Elementen vom Exchange-Informationsspeicher zugewiesen ist. 
  
 ### <a name="resultscsv-report-viewed-in-excel"></a>Results. CSV-Bericht (in Excel angezeigt)
  
![Anzeigen von Informationen zu doppelten Elementen im Bericht "results. csv"](media/e3d64004-3b91-4cba-b6f3-934b46cbdcdb.png)
  
 ### <a name="manifestxml-report-viewed-in-excel"></a>Manifest. XML-Bericht (in Excel angezeigt)
  
![Anzeigen von Informationen zu doppelten Elementen im Bericht "Manifest. xml"](media/69aa4786-9883-46ff-bcae-b35e0daf4a6d.png)
  
Darüber hinaus sind andere Eigenschaften aus doppelten Nachrichten in den Export Berichten enthalten. Dies umfasst das Postfach, in dem sich die doppelte Nachricht befindet, ob die Nachricht an eine Verteilergruppe gesendet wurde und ob die Nachricht CC 'd oder Bcc an einen anderen Benutzer gesendet wurde.
  
## <a name="limitations-of-the-de-duplication-algorithm"></a>Einschränkungen des Algorithmus zur Deduplizierung

Es gibt einige bekannte Einschränkungen des Algorithmus zur Deduplizierung, die dazu führen können, dass eindeutige Elemente als Duplikate markiert werden. Es ist wichtig, dass Sie diese Einschränkungen kennen, damit Sie entscheiden können, ob Sie das optionale Feature zur Deduplizierung verwenden möchten.
  
Es gibt eine Situation, in der die Deduplizierung möglicherweise fälschlicherweise eine Nachricht als Duplikat identifiziert und nicht exportiert (Sie wird jedoch weiterhin als Duplikat in den Export Berichten zitiert). Dabei handelt es sich um Nachrichten, die ein Benutzer bearbeitet, aber nicht sendet. Angenommen, ein Benutzer wählt eine Nachricht in Outlook aus, kopiert den Inhalt der Nachricht und fügt Sie dann in eine neue Nachricht ein. Der Benutzer ändert dann eine der Kopien, indem er eine Anlage entfernt oder hinzufügt oder die Betreffzeile oder den Textkörper selbst ändert. Wenn diese beiden Nachrichten mit der Abfrage einer eDiscovery-Suche übereinstimmen, wird nur eine der Nachrichten exportiert, wenn die Deduplizierung aktiviert wird, wenn die Suchergebnisse exportiert werden. Obwohl die ursprüngliche Nachricht oder die kopierte Nachricht geändert wurde, wurden keine der überarbeiteten Nachrichten gesendet, weshalb die Werte der Eigenschaften **InternetMessageId**, **ConversationTopic** und **BodyTagInfo** nicht aktualisiert wurden. Aber wie bereits erläutert, werden beide Nachrichten in den Export Berichten aufgelistet. 
  
Beachten Sie, dass eindeutige Nachrichten auch als Duplikate markiert werden können, wenn das Feature zum Schutz durch Copy-on-Write-Seite aktiviert ist, wie bei einem Postfach, das das Beweissicherungsverfahren oder das Compliance-Archiv besitzt. Das Feature Copy-on-Write kopiert die ursprüngliche Nachricht (und speichert Sie im Ordner "Versionen" des Ordners "refundable Items" des Benutzers), bevor die Revision des ursprünglichen Elements gespeichert wird. In diesem Fall werden die überarbeitete Kopie und die ursprüngliche Nachricht (im Ordner "Wiederherstellbare Elemente") möglicherweise als doppelte Nachrichten betrachtet, daher wird nur eine exportiert.
  
> [!IMPORTANT]
> Wenn sich die Einschränkungen des Algorithmus für die Deduplizierung auf die Qualität Ihrer Suchergebnisse auswirken können, sollten Sie die Deduplizierung nicht aktivieren, wenn Sie Elemente exportieren. Wenn die in diesem Abschnitt beschriebenen Situationen unwahrscheinlich sind, dass Sie einen Faktor in ihren Suchergebnissen darstellen und die Anzahl der Elemente verringern möchten, die am ehesten Duplikate sind, sollten Sie die Deduplizierung aktivieren. 
  
## <a name="more-information"></a>Weitere Informationen

- Die Informationen in diesem Artikel gelten beim Exportieren von Suchergebnissen mithilfe eines der folgenden eDiscovery-Tools:
    
  - Inhaltssuche im Compliance Center in Office 365
    
  - Compliance-eDiscovery in Exchange Online
    
  - Das eDiscovery Center in SharePoint Online
    
- Weitere Informationen zum Exportieren von Suchergebnissen finden Sie unter:
    
  - [Exportieren der Inhaltssuche](export-search-results.md)
    
  - [Exportieren eines Inhaltssuchberichts](export-a-content-search-report.md)
    
  - [Exportieren von in-Place-eDiscovery-Suchergebnissen in eine PST-Datei](https://go.microsoft.com/fwlink/p/?linkid=832671)
    
  - [Exportieren von Inhalten und Erstellen von Berichten im eDiscovery Center](https://support.office.com/article/7b2ea190-5f9b-4876-86e5-4440354c381a)
