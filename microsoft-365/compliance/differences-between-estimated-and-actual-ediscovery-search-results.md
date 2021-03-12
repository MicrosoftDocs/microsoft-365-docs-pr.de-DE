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
description: Verstehen Sie, warum geschätzte und tatsächliche Suchergebnisse bei Suchdurchsuchungen mit eDiscovery-Tools in Office 365 variieren können.
ms.openlocfilehash: 79f76f573303246e8a5ec733c84a4f684c65513a
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741564"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results"></a>Unterschiede zwischen geschätzten und tatsächlichen eDiscovery-Suchergebnissen

Dieses Thema gilt für Suchprogramme, die Sie mit einem der folgenden Microsoft 365 eDiscovery-Tools ausführen können: 

- Inhaltssuche
- Core eDiscovery

Wenn Sie eine eDiscovery-Suche ausführen, gibt das tool, das Sie verwenden, eine Schätzung der Anzahl der Elemente (und deren Gesamtgröße) zurück, die die Suchkriterien erfüllen. Wenn Sie beispielsweise eine Suche im Microsoft 365 Compliance Center ausführen, werden die geschätzten Suchergebnisse auf der Flyoutseite für die ausgewählte Suche angezeigt.
  
![Schätzung der im Detailbereich der ausgewählten Suche angezeigten Ergebnisse](../media/74e4ce83-40be-41a9-b60f-5ad447e79fe4.png)
  
Dies ist dieselbe Schätzung der Gesamtgröße und Der Anzahl der Elemente, die im eDiscovery-Exporttool angezeigt werden, wenn Sie Ergebnisse auf einen lokalen Computer exportieren, und im Bericht Zusammenfassung exportieren, der mit den Suchergebnissen heruntergeladen wird.
  
**Geschätzte Ergebnisse im eDiscovery-Exporttool**

![Geschätzte Ergebnisse im eDiscovery-Exporttool](../media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Geschätzte Ergebnisse im Zusammenfassenden Exportbericht**

![Geschätzte Suchergebnisse sind im Bericht "Zusammenfassung exportieren" enthalten.](../media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
Wie Sie jedoch im vorherigen Screenshot des Berichts "Zusammenfassung exportieren" sehen, unterscheiden sich Größe und Anzahl der tatsächlich heruntergeladenen Suchergebnisse von der Größe und Anzahl der geschätzten Suchergebnisse.
  
![Unterschied zwischen geschätzten und heruntergeladenen Suchergebnissen](../media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Hier sind einige Gründe für diese Unterschiede:
  
- **Die Art und Weise, wie Ergebnisse geschätzt werden.** Eine Schätzung der Suchergebnisse ist nur das, eine Schätzung (und keine tatsächliche Anzahl) der Elemente, die die Suchabfragekriterien erfüllen. Zum Kompilieren der Schätzung von Exchange-Elementen wird eine Liste der Nachrichten-IDs, die die Suchkriterien erfüllen, von der Exchange-Datenbank vom verwendeten eDiscovery-Tool angefordert. Wenn Sie jedoch die Suchergebnisse exportieren, wird die Suche erneut ausgeführt, und die tatsächlichen Nachrichten werden aus der Exchange-Datenbank abgerufen. Diese Unterschiede können daher aufgrund der Art und Weise, wie die geschätzte Anzahl von Elementen und die tatsächliche Anzahl von Elementen bestimmt werden, resulten.

- **Änderungen, die zwischen dem Zeitpunkt** beim Schätzen und Exportieren von Suchergebnissen auftreten. Wenn Sie Suchergebnisse exportieren, wird die Suche neu gestartet, um die neuesten Elemente im Suchindex zu erfassen, die den Suchkriterien entsprechen. Es ist möglich, dass zusätzliche Elemente erstellt, gesendet oder empfangen wurden, die die Suchkriterien in der Zeit zwischen dem Sammeln der geschätzten Suchergebnisse und dem Export der Suchergebnisse erfüllen. Es ist auch möglich, dass Elemente, die sich bei der Schätzung der Suchergebnisse im Suchindex befinden, nicht mehr dort sind, da sie vor dem Exportieren der Suchergebnisse aus dem Inhaltsspeicherort gelöscht wurden. Eine Möglichkeit, dieses Problem zu beheben, besteht in der Angabe eines Datumsbereichs für eine eDiscovery-Suche. Eine weitere Möglichkeit besteht in der Einbehalten von Inhaltspositionen, damit Elemente beibehalten werden und nicht gelöscht werden können. 

   Obwohl selten, auch wenn ein Haltemodus angewendet wird, kann die Wartung von integrierten Kalenderelementen (die vom Benutzer nicht bearbeitet werden können, aber in vielen Suchergebnissen enthalten sind) von Zeit zu Zeit entfernt werden. Dieses regelmäßige Entfernen von Kalenderelementen führt zu weniger exportierten Elementen.

- **Nicht indizierte Elemente**. Elemente, die für die Suche nicht indiziert sind, können Unterschiede zwischen geschätzten und tatsächlichen Suchergebnissen verursachen. Sie können nicht indizierte Elemente beim Exportieren der Suchergebnisse verwenden. Wenn Sie beim Exportieren von Suchergebnissen nicht indizierte Elemente enthalten, können weitere Elemente exportiert werden. Dies führt zu einem Unterschied zwischen den geschätzten und exportierten Suchergebnissen.

    Bei Verwendung des Inhaltssuchtools haben Sie die Möglichkeit, nicht indizierte Elemente in die Suchschätzung einzuf en. Die Anzahl der nicht indizierten Elemente, die von der Suche zurückgegeben werden, wird zusammen mit den anderen geschätzten Suchergebnissen auf der Flyoutseite aufgelistet. Alle nicht indizierten Elemente würden auch in der Gesamtgröße der geschätzten Suchergebnisse enthalten sein. Wenn Sie Suchergebnisse exportieren, haben Sie die Möglichkeit, nicht indizierte Elemente ein- oder nicht zu enthalten. Die Konfiguration dieser Optionen kann zu Unterschieden zwischen geschätzten und tatsächlichen Suchergebnissen führen, die heruntergeladen werden.

- **Exportieren der Ergebnisse einer Inhaltssuche, die alle Inhaltsstandorte enthält.** Wenn die Suche, aus der Sie Ergebnisse exportieren, eine Suche nach allen Inhaltsstandorten in Ihrer Organisation war, werden nur die nicht indizierten Elemente aus Inhaltsverzeichnissen exportiert, die Elemente enthalten, die den Suchkriterien entsprechen. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Nicht indizierte Elemente von allen Inhaltsverzeichnissen (auch solche, die keine Elemente enthalten, die mit der Suchabfrage übereinstimmen) werden jedoch in die geschätzten Suchergebnisse einbezogen.

    Wenn die Suche, von der Sie Ergebnisse aus bestimmten Inhaltsverzeichnissen exportieren, nicht indizierte Elemente (die nicht von den Suchkriterien ausgeschlossen werden) aus allen in der Suche angegebenen Inhaltsverzeichnissen exportiert wird. In diesem Fall sollten die geschätzte Anzahl nicht indizierter Elemente und die Anzahl der nicht indizierten Elemente, die exportiert werden, identisch sein.

    Der Grund dafür, dass nicht indizierte Elemente nicht von jedem Speicherort in der Organisation exportiert werden, liegt daran, dass die Wahrscheinlichkeit von Exportfehlern erhöht und die Zeit zum Exportieren und Herunterladen der Suchergebnisse erhöht werden kann.

- **Nicht indizierte Elemente in SharePoint und OneDrive sind nicht in Suchschätzungen enthalten.** Nicht indizierte Elemente von #A0 und OneDrive for #A1 sind nicht in den geschätzten Suchergebnissen enthalten. Dies liegt daran, dass der SharePoint-Index keine Daten für nicht indizierte Elemente enthält. In den Suchschätzungen sind nur nicht indizierte Elemente aus Postfächern enthalten. Wenn Sie jedoch beim Exportieren von Suchergebnissen nicht indizierte Elemente enthalten, sind nicht indizierte Elemente in SharePoint und OneDrive enthalten. Dies kann zu Unterschieden zwischen den geschätzten Ergebnissen (die nicht indizierte Elemente in SharePoint- und #A0 nicht enthalten) und den tatsächlich heruntergeladenen Elementen führen. Die Regel zum Exportieren nicht indizierter Elemente nur aus Inhaltsverzeichnissen, die Elemente enthalten, die den Suchkriterien entsprechen, gilt in dieser Situation weiterhin.

- **Unformatierte Dateiformate im Vergleich zu exportierten Dateiformaten**. Für Exchange-Elemente wird die geschätzte Größe der Suchergebnisse mithilfe der unformatierten Exchange-Nachrichtengrößen berechnet. E-Mail-Nachrichten werden jedoch in einer PST-Datei oder als einzelne Nachrichten (die als EML-Dateien formatiert sind) exportiert. Beide Exportoptionen verwenden ein anderes Dateiformat als unformatierte Exchange-Nachrichten, was dazu führt, dass sich die gesamt exportierte Dateigröße von der geschätzten Dateigröße abt.

- **Dokumentversionen**. Bei SharePoint-Dokumenten sind mehrere Versionen eines Dokuments nicht in den geschätzten Suchergebnissen enthalten. Sie haben jedoch die Möglichkeit, beim Exportieren der Suchergebnisse alle Dokumentversionen einzunehmen, wodurch die tatsächliche Anzahl (und Gesamtgröße) der exportierten Dokumente erhöht wird. 

- **Deduplizierung**. Bei Exchange-Elementen verringert die Deduplizierung die Anzahl der exportierten Elemente. Sie haben die Möglichkeit, die Suchergebnisse beim Exportieren zu deduplizieren. Für Exchange-Nachrichten bedeutet dies, dass nur eine einzelne Instanz einer Nachricht exportiert wird, auch wenn diese Nachricht in mehreren Postfächern gefunden werden kann. Die geschätzten Suchergebnisse umfassen jede Instanz einer Nachricht. Wenn Sie also beim Exportieren von Suchergebnissen die Deduplizierungsoption auswählen, ist die tatsächliche Anzahl der exportierten Elemente möglicherweise erheblich kleiner als die geschätzte Anzahl von Elementen.

    Wenn Sie die Deduplizierungsoption auswählen, sollten Sie auch beachten, dass alle Exchange-Elemente in einer einzelnen PST-Datei exportiert werden und die Ordnerstruktur aus den Quellpostfächern nicht beibehalten wird. Die exportierte PST-Datei enthält nur die E-Mail-Elemente. Ein Suchergebnisseinsbericht enthält jedoch einen Eintrag für jede exportierte Nachricht, der das Quellpostfach identifiziert, in dem sich die Nachricht befindet. Dadurch können Sie alle Postfächer identifizieren, die eine doppelte Nachricht enthalten. Wenn Sie Deduplizierung nicht aktivieren, wird für jedes durchsuchte Postfach eine separate PST-Datei exportiert. 





> [!NOTE]
> Wenn Sie beim Exportieren von **Suchergebnissen** oder beim Herunterladen der Berichte nicht die Option Verschlüsselte Elemente enthalten oder über ein nicht unbekanntes Format verfügen, werden die Indexfehlerberichte heruntergeladen, aber keine Einträge. Dies bedeutet nicht, dass es keine Indizierungsfehler gibt. Das bedeutet nur, dass nicht indizierte Elemente nicht in den Export einbezogen wurden. 
