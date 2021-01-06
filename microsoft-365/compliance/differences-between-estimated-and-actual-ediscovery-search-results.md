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
description: Verstehen Sie, warum geschätzte und tatsächliche Suchergebnisse bei Suchvorgängen mit eDiscovery-Tools in Office 365 variieren können.
ms.openlocfilehash: a5a66e070bf41cf6b3263dbae1e6ac5d136d9465
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760253"
---
# <a name="differences-between-estimated-and-actual-ediscovery-search-results"></a>Unterschiede zwischen geschätzten und tatsächlichen eDiscovery-Suchergebnissen

Dieses Thema bezieht sich auf Suchvorgänge, die Sie mit einem der folgenden Microsoft 365-eDiscovery-Tools ausführen können: 

- Inhaltssuche
- Core eDiscovery 
   
Wenn Sie eine eDiscovery-Suche ausführen, gibt das Tool, das Sie verwenden, eine Schätzung der Anzahl von Elementen (und deren Gesamtgröße) zurück, die den Suchkriterien entsprechen. Wenn Sie beispielsweise eine Suche im Microsoft 365 Compliance Center ausführen, werden die geschätzten Suchergebnisse auf der Flyout-Seite für die ausgewählte Suche angezeigt.
  
![Schätzung der Ergebnisse, die im Detailbereich der ausgewählten Suche angezeigt werden](../media/74e4ce83-40be-41a9-b60f-5ad447e79fe4.png)
  
Dies ist die gleiche Schätzung der Gesamtgröße und der Anzahl von Elementen, die im eDiscovery-Export Tool angezeigt wird, wenn Sie Ergebnisse auf einen lokalen Computer und im Export Zusammenfassungsbericht exportieren, der mit den Suchergebnissen heruntergeladen wird.
  
**Geschätzte Ergebnisse im eDiscovery-Export Tool**

![Geschätzte Ergebnisse im eDiscovery-Export Tool](../media/d34312a5-0ee6-49aa-9460-7ea0015a6e66.png)
  
**Geschätzte Ergebnisse im Export Zusammenfassungsbericht**

![Geschätzte Suchergebnisse sind im Export Zusammenfassungsbericht enthalten.](../media/44b579da-86c2-4f33-81b5-84d604003eda.png)
  
Wie Sie jedoch im vorherigen Screenshot des Export Zusammenfassungsberichts bemerken, unterscheiden sich die Größe und Anzahl der tatsächlichen Suchergebnisse, die heruntergeladen werden, von der Größe und Anzahl der geschätzten Suchergebnisse.
  
![Unterschied zwischen geschätzten und heruntergeladenen Suchergebnissen](../media/84aef318-230f-430d-9d9e-02f21342d364.png)
  
Hier sind einige Gründe für diese Unterschiede:
  
- **Die Art und Weise, wie Ergebnisse geschätzt werden**. Eine Schätzung der Suchergebnisse ist lediglich eine Schätzung (und keine tatsächliche Anzahl) der Elemente, die den Suchabfrage Kriterien entsprechen. Um die Schätzung von Exchange-Elementen zu kompilieren, wird eine Liste der Nachrichten-IDs, die die Suchkriterien erfüllen, von der Exchange-Datenbank nach dem von Ihnen verwendeten eDiscovery-Tool angefordert. Wenn Sie die Suchergebnisse exportieren, wird die Suche jedoch erneut ausgeführt, und die tatsächlichen Nachrichten werden aus der Exchange-Datenbank abgerufen. Diese Unterschiede können daher dadurch entstehen, dass die geschätzte Anzahl von Elementen und die tatsächliche Anzahl von Elementen bestimmt werden.

- **Änderungen, die zwischen dem Zeitpunkt der Schätzung und dem Export von Suchergebnissen auftreten**. Wenn Sie Suchergebnisse exportieren, wird die Suche neu gestartet, um die letzten Elemente im Suchindex zu erfassen, die den Suchkriterien entsprechen. Es ist möglich, dass zusätzliche Elemente erstellt, gesendet oder empfangen wurden, die die Suchkriterien in dem Zeitraum erfüllen, in dem die geschätzten Suchergebnisse gesammelt wurden und die Suchergebnisse exportiert wurden. Es ist auch möglich, dass Elemente, die sich im Suchindex befanden, als die Suchergebnisse geschätzt wurden, nicht mehr vorhanden sind, da Sie vom Inhaltsspeicherort gelöscht wurden, bevor die Suchergebnisse exportiert wurden. Eine Möglichkeit zur Minderung dieses Problems besteht darin, einen Datumsbereich für eine eDiscovery-Suche anzugeben. Eine andere Möglichkeit besteht darin, inhaltsspeicherorte so einzuhalten, dass Elemente beibehalten werden und nicht gelöscht werden können. 

   Obwohl selten, selbst im Fall, wenn ein Haltebereich angewendet wird, kann die Wartung von integrierten Kalenderelementen (die nicht vom Benutzer bearbeitet werden, aber in vielen Suchergebnissen enthalten sind) möglicherweise von Zeit zu Zeit entfernt werden. Durch diese regelmäßige Entfernung von Kalenderelementen werden weniger Elemente exportiert.

- Nicht **indizierte Elemente**. Elemente, die für die Suche nicht indiziert sind, können Unterschiede zwischen geschätzten und tatsächlichen Suchergebnissen verursachen. Sie können nicht indizierte Elemente einschließen, wenn Sie die Suchergebnisse exportieren. Wenn Sie nicht indizierte Elemente beim Exportieren von Suchergebnissen einbeziehen, werden möglicherweise weitere Elemente exportiert. Dies führt zu einem Unterschied zwischen den geschätzten und den exportierten Suchergebnissen.

    Wenn Sie das Inhalts Such Tool verwenden, haben Sie die Möglichkeit, nicht indizierte Elemente in die Such Schätzung einzubeziehen. Die Anzahl der nicht indizierten Elemente, die von der Suche zurückgegeben werden, wird auf der Flyout-Seite zusammen mit den anderen geschätzten Suchergebnissen aufgeführt. Alle nicht indizierten Elemente wären auch in der Gesamtgröße der geschätzten Suchergebnisse enthalten. Wenn Sie Suchergebnisse exportieren, haben Sie die Möglichkeit, nicht indizierte Elemente einzubeziehen oder nicht einzubeziehen. Die Art und Weise, wie Sie diese Optionen konfigurieren, kann zu Unterschieden zwischen den geschätzten und den tatsächlichen Suchergebnissen führen, die heruntergeladen werden.

- **Exportieren der Ergebnisse einer Inhaltssuche, die alle inhaltsspeicherorte enthält**. Wenn es sich bei der Suche, aus der Sie Ergebnisse exportieren, um die Suche aller inhaltsspeicherorte in Ihrer Organisation handelt, werden nur die nicht indizierten Elemente aus Inhaltsspeicherorten exportiert, die Elemente enthalten, die mit den Suchkriterien übereinstimmen. In other words, if no search results are found in a mailbox or site, then any unindexed items in that mailbox or site won't be exported. Nicht indizierte Elemente aller inhaltsspeicherorte (auch solche, die keine Elemente enthalten, die mit der Suchabfrage übereinstimmen) werden in die geschätzten Suchergebnisse aufgenommen.

    Wenn die Suche, die Sie exportieren, aus bestimmten Inhaltsspeicherorten stammt, werden auch nicht indizierte Elemente (die nicht von den Suchkriterien ausgeschlossen werden) aus allen in der Suche angegebenen Inhaltsspeicherorten exportiert. In diesem Fall sollte die geschätzte Anzahl nicht indexierter Elemente und die Anzahl der exportierten nicht indizierten Elemente identisch sein.

    Der Grund für das nicht exportieren von nicht indizierten Elementen von allen Standorten in der Organisation liegt darin, dass es möglicherweise die Wahrscheinlichkeit von Exportfehlern erhöht und die Zeit für das Exportieren und Herunterladen der Suchergebnisse erhöht.

- **RAW-Dateiformate im Vergleich zu exportierten Dateiformaten**. Für Exchange-Elemente wird die geschätzte Größe der Suchergebnisse mithilfe der rohen Exchange-Nachrichtengrößen berechnet. E-Mail-Nachrichten werden jedoch in einer PST-Datei oder als einzelne Nachrichten (die als EML-Dateien formatiert sind) exportiert. Beide Exportoptionen verwenden ein anderes Dateiformat als rohe Exchange-Nachrichten, was dazu führt, dass die Gesamtgröße der exportierten Datei von der geschätzten Dateigröße abweicht.

- **Dokumentversionen**. Für SharePoint-Dokumente sind mehrere Versionen eines Dokuments nicht in den geschätzten Suchergebnissen enthalten. Sie haben jedoch die Möglichkeit, beim Exportieren der Suchergebnisse alle Dokumentversionen einzubeziehen, wodurch die tatsächliche Zahl (und Gesamtgröße) der exportierten Dokumente erhöht wird. 

- **Datendeduplizierung.** Bei Exchange-Elementen reduziert die Deduplizierung die Anzahl der exportierten Elemente. Sie haben die Möglichkeit, die Suchergebnisse beim Exportieren zu deduplizieren. Bei Exchange-Nachrichten bedeutet dies, dass nur eine einzige Instanz einer Nachricht exportiert wird, obwohl diese Nachricht in mehreren Postfächern gefunden werden kann. Die geschätzten Suchergebnisse enthalten jede Instanz einer Nachricht. Wenn Sie also die Option "Deduplizierung" beim Exportieren von Suchergebnissen auswählen, ist die tatsächliche Anzahl der exportierten Elemente möglicherweise erheblich kleiner als die geschätzte Anzahl von Elementen.

    Beachten Sie beim Auswählen der Option für die Deduplizierung, dass alle Exchange-Elemente in einer einzigen PST-Datei exportiert werden und die Ordnerstruktur aus den Quellpostfächern nicht beibehalten wird. Die exportierte PST-Datei enthält nur die e-Mail-Elemente. Ein Suchergebnisbericht enthält jedoch einen Eintrag für jede exportierte Nachricht, die das Quellpostfach identifiziert, in dem sich die Nachricht befindet. Auf diese Weise können Sie alle Postfächer identifizieren, die eine doppelte Nachricht enthalten. Wenn Sie Deduplizierung nicht aktivieren, wird für jedes durchsuchte Postfach eine separate PST-Datei exportiert. 
 
> [!NOTE]
> Wenn Sie beim Exportieren von Suchergebnissen oder einfach nur zum Herunterladen der Berichte die Option **Elemente einschließen, die verschlüsselt sind oder nicht erkannt** sind, nicht auswählen, werden die Indexfehler Berichte heruntergeladen, aber keine Einträge. Dies bedeutet nicht, dass keine Indizierungsfehler vorliegen. Dies bedeutet nur, dass nicht indizierte Elemente nicht in den Export eingeschlossen wurden. 
