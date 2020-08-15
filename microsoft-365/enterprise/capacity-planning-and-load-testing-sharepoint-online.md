---
title: Kapazitätsplanung und Auslastungstests für SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 04/10/2019
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
ms.assetid: c932bd9b-fb9a-47ab-a330-6979d03688c0
description: In diesem Artikel wird beschrieben, wie Sie für SharePoint Online bereitstellen können, ohne herkömmliche Auslastungstests durchführen zu müssen, da dies nicht zulässig ist.
ms.openlocfilehash: a20ed3b5f9b3108d90ec912ec78efa348d4281b1
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690730"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Kapazitätsplanung und Auslastungstests für SharePoint Online
In diesem Artikel wird beschrieben, wie Sie für SharePoint Online ohne herkömmliche Auslastungstests bereitstellen können, da das Laden von Tests auf SharePoint Online nicht zulässig ist. SharePoint Online ist ein clouddienst, und die Ladefunktionen, die Integrität und der Gesamtsaldo der Last im Dienst werden von Microsoft verwaltet.
  
Der beste Ansatz, um den Erfolg beim Start Ihrer Website sicherzustellen, ist die Einhaltung grundlegender Prinzipien, Methoden und Empfehlungen, die im [Plan Your Portal Launch Rollout](planportallaunchroll-out.md)hervorgehoben werden.

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Übersicht darüber, wie SharePoint Online Kapazitätsplanung ausführt 
Einer der Hauptvorteile von SharePoint Online über eine lokale Bereitstellung ist die Elastizität der Cloud sowie Optimierungen für Benutzer in verteilten Regionen. Unsere groß angelegte Umgebung ist so eingerichtet, dass täglich Millionen von Benutzern zur Verfügung gestellt werden, daher ist es wichtig, dass wir die Kapazität effektiv durch das ausbalancieren und Erweitern von Farmen bewältigen.
  
Während das Wachstum für einen Mandanten in einer Farm häufig unvorhersehbar ist, ist die aggregierte Summe von Anforderungen im Laufe der Zeit vorhersehbar. Durch die Ermittlung der Wachstumstrends in SharePoint Online können wir die zukünftige Expansion planen.
  
Um die Kapazität effizient zu nutzen und unerwartetes Wachstum zu bewältigen, gibt es in jeder Farm Automatisierung, die verschiedene Elemente des Diensts verfolgt und überwacht. Es werden mehrere Metriken verwendet, wobei eine der wichtigsten CPU-Auslastung ist, die als Signal für die Skalierung von Front-End-Servern dient. Darüber hinaus wird ein [Phasenweises/Wave-Ansatz](planportallaunchroll-out.md)empfohlen, da SQL-Umgebungen im Laufe der Zeit entsprechend der Auslastung und des Wachstums skaliert werden und die Phasen und Wellen die richtige Verteilung dieser Last und des Wachstums ermöglichen. 

Kapazität ist mehr als nur das Hinzufügen von mehr Hardware kontinuierlich, aber Sie bezieht sich auch auf die Verwaltung und Steuerung dieser Kapazität, um sicherzustellen, dass Sie gültige Lastanforderungen bedient. Es wird empfohlen, dass Kunden die empfohlenen Anleitungen befolgten, um sicherzustellen, dass Sie die beste Erfahrung haben. Es bedeutet auch, dass wir Drosselungs Muster und Steuerelemente vorhanden haben, um sicherzustellen, dass das Verhalten von "missbräuchlich" im Dienst nicht zulässig ist. Während nicht alle "schlechten" Verhaltensweisen absichtlich sind, müssen wir sicherstellen, dass wir die Auswirkung dieses Verhaltens einschränken. Weitere Informationen zur Einschränkung und wie Sie dies vermeiden können, finden Sie unter [How to Avoid be Throttle Guidance](https://docs.microsoft.com/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online) article.

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Gründe für das Laden von Test SharePoint Online
Bei lokalen Umgebungen werden Auslastungstests verwendet, um die Skalierungs Annahme zu validieren und letztendlich den Unterbrechungs Pfad einer Farm zu finden. durch Sättigung mit Last. 

Mit SharePoint Online müssen wir die Dinge unterschiedlich ausführen, da die Skalierung relativ flüssig ist und die Last basierend auf bestimmten Heuristiken anpasst, drosselt und steuert. Da es sich um eine derart große Multi-Mandanten Umgebung handelt, müssen wir alle Mandanten in der gleichen Farm schützen, sodass alle Auslastungstests automatisch gedrosselt werden. Wenn Sie jedoch versuchen, den Test zu laden, werden Sie nicht nur eingeschränkt, sondern auch enttäuschende und potenziell irreführende Ergebnisse erhalten, da die Farm, die Sie heute getestet haben, wahrscheinlich im Testfenster oder innerhalb von Stunden nach dem Testen Skalierungs-und Farm Ausgleichs Aktionen ausgeführt wird.

Anstatt zu versuchen, SharePoint-Test als Dienst zu laden, konzentrieren Sie sich lieber auf die empfohlenen Vorgehensweisen und folgen Sie den Anleitungen zum [erstellen, starten und Verwalten eines gesunden Portals](https://go.microsoft.com/fwlink/?linkid=2105838) .
