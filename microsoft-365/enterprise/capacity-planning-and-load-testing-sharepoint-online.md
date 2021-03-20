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
description: In diesem Artikel wird beschrieben, wie Sie sharePoint Online bereitstellen können, ohne herkömmliche Auslastungstests durchführen zu müssen, da dies nicht zulässig ist.
ms.openlocfilehash: fb54864168b35fed290ccb1139cb6c607969820d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905224"
---
# <a name="capacity-planning-and-load-testing-sharepoint-online"></a>Kapazitätsplanung und Auslastungstests für SharePoint Online
In diesem Artikel wird beschrieben, wie Sie sharePoint Online ohne herkömmliche Auslastungstests bereitstellen können, da Auslastungstests in SharePoint Online nicht zulässig sind. SharePoint Online ist ein Clouddienst, und die Ladefunktionen, die Integrität und das Gesamtgewicht der Last im Dienst werden von Microsoft verwaltet.
  
Der beste Ansatz, um den Erfolg des Startens Ihrer Website sicherzustellen, besteht in der Einhaltung grundlegender Prinzipien, Methoden und Empfehlungen, die im Plan [ihres Portalstartroll-outs hervorgehoben werden.](planportallaunchroll-out.md)

## <a name="overview-of-how-sharepoint-online-performs-capacity-planning"></a>Übersicht über die Durchführung der Kapazitätsplanung in SharePoint Online 
Einer der hauptvorteile von SharePoint Online gegenüber einer lokalen Bereitstellung ist die Elastizität der Cloud sowie Optimierungen für Benutzer in verteilten Regionen. Unsere groß angelegte Umgebung ist so eingerichtet, dass Millionen von Benutzern täglich bedienen werden. Daher ist es wichtig, dass wir die Kapazität effektiv verarbeiten, indem wir Farmen ausbalancieren und erweitern.
  
Während das Wachstum für jeden Mandanten in einer Farm häufig unvorhersehbar ist, ist die aggregierte Summe der Anforderungen im Laufe der Zeit vorhersehbar. Indem wir die Wachstumstrends in SharePoint Online identifizieren, können wir eine zukünftige Expansion planen.
  
Um kapazität effizient zu nutzen und unerwartetes Wachstum zu umgehen, verfügen wir in jeder Farm über automatisierung, die verschiedene Elemente des Diensts verfolgt und überwacht. Es werden mehrere Metriken verwendet, bei denen eine der Hauptmetriken die CPU-Last ist, die als Signal zum Skalieren von Front-End-Servern verwendet wird. Darüber hinaus wird [](planportallaunchroll-out.md)ein Phasen-/Welleansatz empfohlen, da SQL-Umgebungen im Laufe der Zeit nach Last und Wachstum skaliert werden und das Folgen der Phasen und Wellen die richtige Verteilung dieser Last und des Wachstums ermöglicht. 

Bei der Kapazität geht es nicht nur darum, kontinuierlich mehr Hardware zu hinzufügen, sondern es geht auch darum, diese Kapazität zu verwalten und zu steuern, um sicherzustellen, dass sie gültige Lastanforderungen bedient. Es wird empfohlen, dass Kunden die empfohlenen Anleitungen befolgen, um sicherzustellen, dass sie die beste Erfahrung haben. Es bedeutet auch, dass wir Drosselungsmuster und -steuerelemente haben, um sicherzustellen, dass wir kein "missbräuchliches" Verhalten im Dienst zulassen. Obwohl nicht alle "schlechten" Verhaltensweisen beabsichtigt sind, müssen wir sicherstellen, dass die Auswirkungen dieses Verhaltens begrenzt werden. Weitere Informationen zur Einschränkung und zur Vermeidung dieser Einschränkung finden Sie im Artikel zur Vermeidung von [Drosselungsanleitungen.](/sharepoint/dev/general-development/how-to-avoid-getting-throttled-or-blocked-in-sharepoint-online)

## <a name="why-you-cannot-load-test-sharepoint-online"></a>Warum Sie SharePoint Online nicht laden können
In lokalen Umgebungen werden Auslastungstests verwendet, um die Skalierungsannahme zu überprüfen und letztendlich den Ausgangspunkt einer Farm zu finden. durch saturieren sie mit Load. 

Bei SharePoint Online müssen wir dies anders tun, da die Skalierung relativ flüssig ist und die Last basierend auf bestimmten Heuristiken an, drosselt und steuert. Da es sich um eine so umfangreiche Mehr-Mandanten-Umgebung gibt, müssen wir alle Mandanten in derselben Farm schützen, sodass wir alle Auslastungstests automatisch drosseln. Wenn Sie jedoch versuchen, den Test zu laden, erhalten Sie nicht nur gedrosselt, sondern auch enttäuschende und potenziell irreführende Ergebnisse, da die Farm, die Sie heute getestet haben, wahrscheinlich während des Testfensters oder innerhalb von Stunden nach dem Testen Änderungen an der Skalierung vorgenommen hat, da Skalierungs- und Farmausgleichsaktionen regelmäßig ausgeführt werden.

Anstatt zu versuchen, SharePoint als Dienst zu testen, konzentrieren Sie sich stattdessen darauf, die empfohlenen Methoden zu befolgen und den Leitfaden Erstellen, Starten und Verwalten eines fehlerfreien [Portals zu](/sharepoint/portal-health) befolgen.