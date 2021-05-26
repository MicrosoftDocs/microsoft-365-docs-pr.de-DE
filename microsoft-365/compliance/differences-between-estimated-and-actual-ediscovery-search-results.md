---
title: Unterschiede zwischen geschätzten und tatsächlichen eDiscovery-Suchergebnissen
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: 8f20ca4f-a908-46ec-99e6-9890d269ecf2
description: Verstehen Sie, warum geschätzte und tatsächliche Suchergebnisse bei Suchdurchsuchungen mit eDiscovery-Tools in Office 365.
ms.openlocfilehash: 17a4c2eea9833afa2112fa8ab918dcda074eeb36
ms.sourcegitcommit: 727a75b604d5ff5946a0854662ad5a8b049f2874
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/25/2021
ms.locfileid: "52653511"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results"></a>Unterschiede zwischen geschätzten und tatsächlichen eDiscovery-Suchergebnissen

Dieses Thema gilt für Suchprogramme, die Sie mit einem der folgenden eDiscovery Microsoft 365 ausführen können: 

- Inhaltssuche
- Core eDiscovery

Wenn Sie eine eDiscovery-Suche ausführen, gibt das tool, das Sie verwenden, eine Schätzung der Anzahl der Elemente (und deren Gesamtgröße) zurück, die den Suchkriterien entsprechen. Wenn Sie beispielsweise eine Suche im compliance center Microsoft 365 ausführen, werden die geschätzten Suchergebnisse auf der Flyoutseite für die ausgewählte Suche angezeigt.
  
![Schätzung der Ergebnisse, die auf der Suchf flyout-Seite angezeigt werden](../media/EstimatedSearchResults1.png)
  
Dies ist dieselbe Schätzung der Gesamtgröße und Der Anzahl der Elemente, die im eDiscovery-Exporttool angezeigt werden, wenn Sie Ergebnisse auf einen lokalen Computer exportieren, und im Bericht Zusammenfassung exportieren, der mit den Suchergebnissen heruntergeladen wird.
  
**Geschätzte Ergebnisse im eDiscovery-Exporttool**

![Geschätzte Ergebnisse im eDiscovery-Exporttool](../media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Geschätzte Ergebnisse im Zusammenfassenden Exportbericht**

![Geschätzte Suchergebnisse sind im Bericht "Zusammenfassung exportieren" enthalten.](../media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
Wie Sie jedoch im vorherigen Screenshot des Berichts "Zusammenfassung exportieren" sehen, unterscheiden sich Größe und Anzahl der tatsächlich heruntergeladenen Suchergebnisse von der Größe und Anzahl der geschätzten Suchergebnisse.
  
![Unterschied zwischen geschätzten und heruntergeladenen Suchergebnissen](../media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Hier sind einige Gründe für diese Unterschiede:
  
- **Die Art und Weise, wie Ergebnisse geschätzt werden.** Eine Schätzung der Suchergebnisse ist nur das, eine Schätzung (und keine tatsächliche Anzahl) der Elemente, die die Suchabfragekriterien erfüllen. Um die Schätzung der Exchange zu kompilieren, wird eine Liste der Nachrichten-IDs, die die Suchkriterien erfüllen, von der Exchange-Datenbank vom verwendeten eDiscovery-Tool angefordert. Wenn Sie die Suchergebnisse exportieren, wird die Suche jedoch erneut ausgeführt, und die tatsächlichen Nachrichten werden aus der Exchange abgerufen. Diese Unterschiede können daher aufgrund der Art und Weise, wie die geschätzte Anzahl von Elementen und die tatsächliche Anzahl von Elementen bestimmt werden, resulten.

- **Änderungen, die zwischen dem Zeitpunkt** beim Schätzen und Exportieren von Suchergebnissen auftreten. Wenn Sie Suchergebnisse exportieren, wird die Suche neu gestartet, um die neuesten Elemente im Suchindex zu erfassen, die den Suchkriterien entsprechen. Es ist möglich, dass zusätzliche Elemente erstellt, gesendet oder empfangen wurden, die die Suchkriterien in der Zeit zwischen dem Sammeln der geschätzten Suchergebnisse und dem Export der Suchergebnisse erfüllen. Es ist auch möglich, dass Elemente, die sich bei der Schätzung der Suchergebnisse im Suchindex befinden, nicht mehr dort sind, da sie vor dem Exportieren der Suchergebnisse aus dem Inhaltsspeicherort gelöscht wurden. Eine Möglichkeit, dieses Problem zu beheben, besteht in der Angabe eines Datumsbereichs für eine eDiscovery-Suche. Eine weitere Möglichkeit besteht in der Einbehalten von Inhaltspositionen, damit Elemente beibehalten werden und nicht gelöscht werden können. 

   Obwohl selten, auch wenn ein Haltemodus angewendet wird, kann die Wartung von integrierten Kalenderelementen (die vom Benutzer nicht bearbeitet werden können, aber in vielen Suchergebnissen enthalten sind) von Zeit zu Zeit entfernt werden. Dieses regelmäßige Entfernen von Kalenderelementen führt zu weniger exportierten Elementen.

- **Nicht indizierte Elemente**. Elemente, die für die Suche nicht indiziert sind, können Unterschiede zwischen geschätzten und tatsächlichen Suchergebnissen verursachen. Sie können nicht indizierte Elemente beim Exportieren der Suchergebnisse verwenden. Wenn Sie beim Exportieren von Suchergebnissen nicht indizierte Elemente enthalten, können weitere Elemente exportiert werden. Dies führt zu einem Unterschied zwischen den geschätzten und exportierten Suchergebnissen.

    Bei Verwendung des Inhaltssuchtools haben Sie die Möglichkeit, beim Exportieren von Suchergebnissen nicht indizierte Elemente ein- und zu verwenden. Die Anzahl der nicht indizierten Elemente, die von der Suche zurückgegeben werden, wird zusammen mit den anderen geschätzten Suchergebnissen auf der Flyoutseite aufgelistet. Alle nicht indizierten Elemente würden auch in der Gesamtgröße der geschätzten Suchergebnisse enthalten sein. Wenn Sie Suchergebnisse exportieren, haben Sie die Möglichkeit, nicht indizierte Elemente ein- oder nicht zu enthalten. Die Konfiguration dieser Optionen kann zu Unterschieden zwischen geschätzten und tatsächlichen Suchergebnissen führen, die heruntergeladen werden.

- **Exportieren der Ergebnisse einer Inhaltssuche, die alle Inhaltsstandorte enthält.** Wenn die Suche, aus der Sie Ergebnisse exportieren, eine Suche nach allen Inhaltsstandorten in Ihrer Organisation war, werden nur die nicht indizierten Elemente aus Inhaltsverzeichnissen exportiert, die Elemente enthalten, die den Suchkriterien entsprechen. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Nicht indizierte Elemente von allen Inhaltsverzeichnissen (auch solche, die keine Elemente enthalten, die mit der Suchabfrage übereinstimmen) werden jedoch in die geschätzten Suchergebnisse einbezogen.

    Wenn die Suche, von der Sie Ergebnisse aus bestimmten Inhaltsverzeichnissen exportieren, nicht indizierte Elemente (die nicht von den Suchkriterien ausgeschlossen werden) aus allen in der Suche angegebenen Inhaltsverzeichnissen exportiert wird. In diesem Fall sollten die geschätzte Anzahl nicht indizierter Elemente und die Anzahl der nicht indizierten Elemente, die exportiert werden, identisch sein.

    Der Grund dafür, dass nicht indizierte Elemente nicht von jedem Speicherort in der Organisation exportiert werden, liegt daran, dass die Wahrscheinlichkeit von Exportfehlern erhöht und die Zeit zum Exportieren und Herunterladen der Suchergebnisse erhöht werden kann.

- **Nicht indizierte Elemente in SharePoint und OneDrive nicht in den Suchschätzungen enthalten.** Nicht indizierte Elemente SharePoint websites und OneDrive for Business werden nicht in die geschätzten Suchergebnisse einbezogen. Dies liegt daran, SharePoint index keine Daten für nicht indizierte Elemente enthält. In den Suchschätzungen sind nur nicht indizierte Elemente aus Postfächern enthalten. Wenn Sie jedoch nicht indizierte Elemente beim Exportieren von Suchergebnissen verwenden, werden nicht indizierte Elemente in SharePoint und OneDrive eingeschlossen, wodurch die Anzahl der tatsächlich exportierten Elemente erhöht wird. Dies führt zu Unterschieden zwischen den geschätzten Ergebnissen (die nicht indizierte Elemente in SharePoint- und OneDrive-Websites nicht enthalten) und den tatsächlich heruntergeladenen Elementen. Die Regel zum Exportieren nicht indizierter Elemente nur aus Inhaltsverzeichnissen, die Elemente enthalten, die den Suchkriterien entsprechen, gilt in dieser Situation weiterhin.

- **Dokumentversionen in SharePoint und OneDrive**. Beim Durchsuchen SharePoint websites und OneDrive werden mehrere Versionen eines Dokuments nicht in die Anzahl der geschätzten Suchergebnisse einbezogen. Beim Exportieren der Suchergebnisse können Sie jedoch alle Dokumentversionen einfügen. Wenn Sie Beim Exportieren von Suchergebnissen Dokumentversionen einfügen, werden die tatsächliche Anzahl (und die Gesamtgröße) der exportierten Elemente erhöht.

- **SharePoint Ordner .** Wenn der Name der Ordner in SharePoint einer Suchabfrage entspricht, enthält die Suchschätzung eine Anzahl dieser Ordner (jedoch nicht die Elemente in diesen Ordnern). Wenn Sie die Suchergebnisse exportieren, werden die Elemente im Ordner exportiert, der tatsächliche Ordner jedoch nicht exportiert. Das Ergebnis ist, dass die Anzahl der exportierten Elemente mehr als die Anzahl der geschätzten Suchergebnisse ist. Wenn ein Ordner leer ist, wird die Anzahl der tatsächlich exportierten Suchergebnisse um ein Element reduziert, da der tatsächliche Ordner nicht exportiert wird.

- **SharePoint Listen**. Wenn der Name einer SharePoint einer Suchabfrage entspricht, enthält die Suchschätzung eine Anzahl aller Elemente in der Liste. Wenn Sie die Suchergebnisse exportieren, wird die Liste (und die Listenelemente) als einzelne CSV-Datei exportiert. Dadurch wird die tatsächliche Anzahl der tatsächlich exportierten Elemente reduziert. Wenn die Liste Anlagen enthält, werden die Anlagen als separate Dokumente exportiert, wodurch sich auch die Anzahl der exportierten Elemente erhöht.

- **Unformatierte Dateiformate im Vergleich zu exportierten Dateiformaten**. Bei Exchange wird die geschätzte Größe der Suchergebnisse mithilfe der unformatierten Exchange berechnet. E-Mail-Nachrichten werden jedoch in einer PST-Datei oder als einzelne Nachrichten (die als EML-Dateien formatiert sind) exportiert. Beide Exportoptionen verwenden ein anderes Dateiformat als unformatierte Exchange, was dazu führt, dass sich die gesamt exportierte Dateigröße von der geschätzten Dateigröße abt.

- **Deduplizierung von Exchange Elementen während des Exports**. Bei Exchange reduziert die Deduplizierung die Anzahl der exportierten Elemente. Sie haben die Möglichkeit, die Suchergebnisse beim Exportieren zu deduplizieren. Bei Exchange bedeutet dies, dass nur eine einzelne Instanz einer Nachricht exportiert wird, auch wenn diese Nachricht in mehreren Postfächern gefunden werden kann. Die geschätzten Suchergebnisse umfassen jede Instanz einer Nachricht. Wenn Sie also beim Exportieren von Suchergebnissen die Deduplizierungsoption auswählen, ist die tatsächliche Anzahl der exportierten Elemente möglicherweise erheblich kleiner als die geschätzte Anzahl von Elementen.

Der Suchergebnisseuchbericht (Results.csv) enthält einen Eintrag für jede doppelte Nachricht und identifiziert das Quellpostfach, in dem sich eine doppelte Nachricht befindet. Dadurch können Sie alle Postfächer identifizieren, die eine doppelte Nachricht enthalten.

> [!NOTE]
> Wenn Sie beim Exportieren von **Suchergebnissen** oder beim Herunterladen der Berichte nicht die Option Verschlüsselte Elemente enthalten oder über ein nicht unbekanntes Format verfügen, werden die Indexfehlerberichte heruntergeladen, aber keine Einträge. Dies bedeutet nicht, dass es keine Indizierungsfehler gibt. Das bedeutet nur, dass nicht indizierte Elemente nicht in den Export einbezogen wurden.
