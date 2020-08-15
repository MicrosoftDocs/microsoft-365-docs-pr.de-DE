---
title: Zu verwendende SharePoint 2007-Migrationsoptionen
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 1/31/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
search.appverid:
- MET150
- SPS150
- OSU140
- SPO160
- SPB160
- OSI150
- OSI160
- BSA160
- OSU160
ms.assetid: 66325a43-5816-4f8e-81ba-c11b71345b7c
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
description: Dieser Artikel enthält Informationen für Benutzer, die SharePoint Server 2007 verwenden, um Sie bei der Planung Ihres Upgrades zu unterstützen.
ms.openlocfilehash: 3e37a01f1a2d387cda6723a8df1f73734fa3ba9d
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46694954"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>Zu verwendende SharePoint 2007-Migrationsoptionen

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft SharePoint 2007 und SharePoint Server 2007 haben das Ende der Unterstützung erreicht. Es ist Zeit für ein Upgrade! Dieser Artikel enthält Informationen zu ihren Migrationsoptionen.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Allgemeine Upgrade-Strategien für SharePoint

Es gibt mehrere Methoden zum Aktualisieren einer SharePoint Server Umgebung. Wenn Sie über eine Microsoft Office SharePoint Server 2007 Farm verfügen, finden Sie hier einige Beispiele für die Upgrade-Methoden:
  
- Update durch Datenbankanfügungen
    
- Side-by-Side-Upgrade
    
- Direktes Upgrade
    
- Hybrides Upgrade (in-Place mit getrennten Datenbanken/separater Datenbankanfügung)
    
- SharePoint-Hybriden (Connect Online to on-premises SharePoint)
    
- Manuelles verlagern von Daten zwischen Websitesammlungen oder Bibliotheken
    
- Update Assistent – Upgrade auf Microsoft 365 ([SharePoint Online Bereitstellungs Ratgeber](https://aka.ms/spoguidance))
    
- Migrations-API zu SharePoint Online (SPO) in Microsoft 365
    
Was funktioniert am besten für Sie?
  
Ihr Wissen darüber, was Ihre Farm macht und wofür Sie verwendet wird, ist eine taktische Stärke, wenn es darum geht, ein Upgrade durchführen zu können. Die Art und Weise, wie Benutzer die SharePoint-Farm verwenden, hilft Ihnen bei der Auswahl Ihrer Optionen.
  
> [!TIP]
> Microsoft Office SharePoint Server 2007 hat auch ein schrittweises Upgrade, das hier nicht behandelt wird. Eine Liste mit Schritt spezifischen Upgrade-Artikeln finden Sie in der [Roadmap für das Ende des Supports SharePoint Server 2007](sharepoint-2007-end-of-support.md). 
  
Denken Sie daran, den [Produktlebenszyklus](https://support.microsoft.com/lifecycle/search) und die System Anforderungen für jede Version von SharePoint zu überprüfen, auf die Sie ein Upgrade durchführen. Dies ist so, dass Sie wissen, wann das nächste Upgrade erforderlich ist (wenn Sie beispielsweise bei einem Legacy Produkt wie SharePoint Server 2010 anhalten, weitere Upgrades zu planen, sicherzustellen, dass Sie das Ende des Support Datums kennen), und sicherzustellen, dass Sie über Hardware verfügen, die ihren Plan unterstützt. 
  
Wenn Sie planen, einige oder alle Ihrer SharePoint-Websites auf Microsoft 365 in der Cloud umzustellen, ist dies eine Zeit, um einen Link zu den [Microsoft 365-und Office 365-Dienstbeschreibungen](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)zu bookmarken. Sie benötigen die Dienstbeschreibungen, um mehr über SharePoint Online Features und deren Unterschiede zwischen lokalen SharePoint Server zu erfahren. Aktualisieren von Funktions Microsoft Office SharePoint Server 2007 Farmen. Wenn Ihre Installation Websites enthält, die beschädigt sind, beheben Sie diese vor dem Upgrade.
  
## <a name="a-note-about-managing-risk"></a>Hinweis zur Risikoverwaltung

Methoden wie "nebeneinander" sind im Schema der Upgrade-Logik wichtig. Wenn Sie das Upgrade nebeneinander durchführen, verwalten Sie Ihre Microsoft Office SharePoint Server 2007 Farm, erstellen jedoch eine Farm mit der nächsten Version (SharePoint Server 2010) auf neuer Hardware. Dies hilft auf drei Arten:
  
1. Sie haben einen Ort, um Sicherungen Ihrer Microsoft Office SharePoint Server 2007-Datenbanken zu erstellen, um Sie separat mithilfe von Datenbankanfügungen zu aktualisieren.
    
2. Wenn Sie feststellen, dass nur eine kleine Anzahl von wichtigen Dokumentbibliotheken und anderen Informationen in Ihrer Microsoft Office SharePoint Server 2007 Farm verwendet wird, können Sie die Daten manuell aus Microsoft Office SharePoint Server 2007 in SharePoint Server 2010 oder nur bestimmte Websites und Webs zur nächsten Version migrieren (was Ihre Arbeit erleichtern kann).
    
3. Je niedriger die Microsoft Office SharePoint Server 2007 Server Farm ist, desto sicherer sind die Daten, die die Farm beim Upgrade enthält.
    
Methoden wie direkte Upgrades fungieren direkt in Ihrer Microsoft Office SharePoint Server 2007 Farm und geben Ihnen weniger einfache Optionen, um einen Pfad zu verlassen und erneut mit ihrer unberührten Umgebung zu beginnen. Erstellen Sie so weit wie möglich einige Sicherheitsmaßnahmen (wie das Aufzeichnen und Testen von Sicherungen der ursprünglichen Umgebung). Wenn Ihre Microsoft Office SharePoint Server 2007-Farm beispielsweise virtuell ist und für die Sicherung und Wiederherstellung dupliziert wurde, sichern Sie die neuesten Datenbanken vor dem Dienstfenster, und stellen Sie Sie für das Upgrade wieder her. Wenn Sie wissen, dass Sie die Möglichkeit haben, Datenbanksicherungen wiederherzustellen, erhalten Sie nicht nur eine ausfallsichere Lösung, sondern Sie können Ihnen Sicherheit geben.
  
> [!TIP]
> Bewährte Methoden für das Upgrade sind für [Microsoft Office SharePoint Server 2007](https://technet.microsoft.com/library/cc261992%28v=office.12%29.aspx), [SharePoint Server 2010](https://technet.microsoft.com/library/cc261992%28v=office.14%29.aspx), [SharePoint Server 2013](https://technet.microsoft.com/library/cc261992%28v=office.15%29.aspx)und [SharePoint Server 2016](https://technet.microsoft.com/library/cc261992%28v=office.16%29.aspx)vorhanden. Sie können auch nach [Microsoft-Partnern](https://partnercenter.microsoft.com/pcv/search) suchen, die Erfahrung mit Upgrades oder Microsoft 365-Migrationen haben. 
  
## <a name="make-your-plan"></a>Erstellen eines Plans

Wenn Sie ein Upgrade durchführen müssen, benötigen Sie einen Plan, und in diesen Fällen passt eine Größe nicht alle. Ihr Plan ist möglicherweise so einfach wie: "Erstellen eines Microsoft 365-Abonnements mit SharePoint Online, Registrieren einer Domäne und Umleiten von Personen zum Speichern der dort gespeicherten Dateien". Und es ist möglicherweise nicht. Diese Entscheidung gehört Ihnen, und es liegt an dem, was Sie und Ihre Benutzer wirklich benötigen.
  
> [!NOTE]
> Es ist riskant, auf Software zu laufen, deren Lebenszyklus beendet ist. Produkte, die nicht mehr unterstützt werden, werden nicht mehr gepatcht, wenn Probleme gefunden werden. Dies bedeutet auch, dass beim Auftreten neuer Sicherheitsbedrohungen keine Sicherheitspatches oder Fixes vorhanden sein werden, da die End-of-Lifecycle-Produkte nicht mehr unterstützt werden. Vermeiden Sie diese Situation! 
  
### <a name="first-know-your-farm"></a>Kennen Sie zunächst Ihre Farm

Wenn Sie ein Upgrade durchführen, sollten Sie Ihre Entscheidung auf der Grundlage Ihrer Serverfarm für Ihre Organisation vornehmen. Welche Anforderungen werden erfüllt? Was ist seine Rolle? Jede Farm in Ihrem Unternehmen kann eine andere Rolle haben. Einige Ihrer SharePoint-Farmen sind möglicherweise  *kritisch*  , einige möglicherweise Dateiarchive-dort zur sicheren Aufbewahrung. Oder wenn Ihre Farm viele Rollen gleichzeitig füllt, müssen Sie möglicherweise wissen, welche Websitesammlungen, Webs oder sogar Dokumentbibliotheken ausführen, alle Anpassungen und wie wichtig Sie sind. Die Analyse Ihrer Daten auf dieser Ebene kann eine Menge Arbeit sein, aber es spart Zeit und Mühe, Ihre Domäne zu meistern, bevor Sie Sie upgraden oder migrieren. Sobald Sie alle beweglichen Teile und die wichtigsten Bits kennen, werden Sie auch wissen, was Sie herausgewachsen sind und zurücklassen können. Dieses Wissen wird Ihnen nur für die Zukunft zugute kommen. 
  
Was sagen Benutzer also am wichtigsten über Ihre SharePoint Server Farm?
  
- Integrierte SharePoint-Features
    
- Der umfangreiche Datenkorpus (beispielsweise ein Archiv von Dateien)
    
- Verfügbarkeit
    
- Wichtige apps, Webparts oder Dokumente in der Farm (geschäftskritische Farm)
    
- Compliance-Standards erfüllt
    
- Anpassungen
    
Wenn Sie etwas wichtiges für Ihr Unternehmen aus Ihrer SharePoint-Farm ausführen, sagen wir, dass es wie ein großer Katalog wichtiger Daten zu Clientdienstanforderungen wirkt, können Sie ein Häkchen neben "Critical Apps" setzen, aber auch "Verfügbarkeit"--das heißt, Ihr Unternehmen würde betroffen sein, wenn Sie SharePoint für eine Weile nicht verwenden konnten. Ebenso können Sie "Anpassungen" überprüfen, da die von Ihrer Farm angebotenen wichtigen Dienste auf benutzerdefiniertem Code, Websitedefinitionen oder einer Reihe von Anpassungen basieren, die zusammenarbeiten.
  
Wenn SharePoint diese Anforderungen erfüllt, ohne dass Sie etwas außerhalb der Verwendung von What es Built-in zur Software vornehmen müssen, und Sie es in der Regel aktualisieren und die normale Verwaltung und Wartung durchführen, haben Sie möglicherweise "Built-in SharePoint" ausgewählt--Dies kann auch der Grund sein, auf einer älteren Version von SharePoint zu sitzen. Mit anderen Worten: Sie macht bereits das, was Sie benötigen, und Sie haben bis jetzt noch kein Upgrade durch Microsoft Office SharePoint Server 2007 Ende des Supports durchführen müssen.
  
Wenn Sie diese Elemente Aufzählungszeichen auflisten, erstellen Sie Kriterien für Ihr Upgrade. Mit anderen Worten: jedes Upgrade müsste diesen Balken erfüllen, um berücksichtigt zu werden. Auf diese Weise können Sie Methoden ausschließen, die derzeit nicht Ihren Anforderungen entsprechen.
  
### <a name="a-simple-sample-plan"></a>Ein einfacher Beispielplan

Möglicherweise muss ein breiter Konsens mit Führungskräften und anderen Administratoren auf dem Pfad erforderlich sein, den Ihr SharePoint-Upgrade durchführen wird. SharePoint Server Administratoren kooperieren häufig mit Microsoft SQL Server Administratoren, arbeiten mit Netzwerk-und Sicherheitsteams zusammen und vieles mehr. Wo viele Beteiligte vorhanden sind, müssen Sie möglicherweise einen Vertrag für den Upgrade-und Migrationsplan erstellen oder diesen anpassen. Wenn Sie beispielsweise Daten migrieren, sodass ein Teil Ihres Unternehmens SharePoint Online in Microsoft 365 verwendet, muss es in Ihrem Netzwerk wahrscheinlich zu Leistungsoptimierungen oder Tests kommen. Betroffene Teams sollten frühzeitig informiert werden.
  
In meinem einfachen Beispiel zeige ich den Vorschlag eines SharePoint-Administrators und verzeichnen dann den Plan, den alle Beteiligten vereinbart haben. Zur besseren Übersichtlichkeit dokumentieren Sie Ihre Vereinbarungen und Entscheidungen.
  
Der Plan beginnt nach einer eingehenden Analyse einer Farm und versucht, die Rolle der Farm, die Problempunkte und andere wichtige Informationen zu identifizieren, die dazu führen, dass einige Upgrade-Optionen eingeschränkt werden. Anschließend wird ein Upgrade-Vorschlag von SharePoint-Administrator vorgenommen, und die beteiligten vereinbaren einen Aktionsplan.
  
Meine "wichtigste" Aufzählungsliste:
  
- Verfügbarkeit, integrierte Features in SharePoint und Compliance-Standards.
    
- Die meisten Daten befinden sich in drei Websitesammlungen, wobei ein von einem Entwicklerteam verwendeter Besprechungsarbeitsbereich besonders wichtig und in starkem Maße in mehreren Zeitzonen weltweit verwendet wird.
    
- Es gibt siebzehn andere Websites, die häufig verwendet werden.
    
- Zwei Dokumentbibliotheken (Besprechungsarbeitsbereich und Dokumente in der Stammwebsitesammlung) sind die größten (jeweils über 8000 Dokumentationen). Wir haben eine große Anzahl von archivierten Dokumenten und Listen mit Tabellen Kalkulations Anlagen.
    
- Es gibt vierzehn Listen mit Bibliotheken mit vertraulichen Daten, die in Übereinstimmung bleiben müssen.
    
- Wir müssen in der Lage sein, Holds und e-Discovery zu erledigen, wohin auch immer wir gehen.
    
- Einige dieser Daten müssen aufgrund von INFOSEC-Regeln lokal bleiben.
    
 **Meine Upgrade-und Migrationsoptionen:**
  
| Ja | Nein |
|:-----|:-----|
|Aktualisieren von Datenbanken mit Datenbankanfügung  <br/> |Direktes Upgrade  <br/> |
|Upgrade mit Farmen nebeneinander  <br/> |Hybrides Upgrade  <br/> |
|Migrations-API zu SPO in Microsoft 365 (für persönliche Website Daten)  <br/> |SharePoint-Hybrid (noch nicht erforderlich)  <br/> |
|Einige manuelle Datenmigrationen zu SharePoint Online für wichtige Daten  <br/> |Update Assistent-Upgrade auf Microsoft 365  <br/> |
   
 **Mein geplanter Plan:**
  
Lokales Upgrade mit SharePoint-Versionen nebeneinander, einige virtualisiert, sodass wir die Datenbanken zuerst aktualisieren können. Wechseln Sie von SharePoint 2007 zu SharePoint 2010. Administratoren und Entwickler testen die resultierende Farm. Benutzer testen die resultierende Farm. Beheben Sie während dieser Zeit alle Probleme mit dem anzeigen Stopp. Aktualisieren Sie SharePoint 2010 Datenbanken erneut nebeneinander auf SharePoint 2013. Testen. Benutzer Test/Pilot. Beheben Sie während dieser Zeit alle Probleme mit dem anzeigen Stopp.
  
- Prüfen Sie, ob eine Such-Verbund Hybride mit SPO Ihren Anforderungen entspricht.
    
- Wenn Sie von hier aus ein Upgrade auf SharePoint Online durchführen möchten, sollten Sie sich die [Kurzhilfe](https://fasttrack.microsoft.com) ansehen. 
    
- Ermitteln Sie, ob Websitesammlungen an ein Microsoft 365-Abonnement abgeladen werden können. (Microsoft 365 erfüllt viele [Compliance-Standards](https://technet.microsoft.com/library/office-365-compliance.aspx). Microsoft 365 verfügt über [eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) und kann über das Compliance Center [verwaltet](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) werden.) 
    
Fahren Sie andernfalls mit einem parallelen Upgrade auf SharePoint Server 2016 fort.
  
> [!NOTE]
> Zwischen den Empfehlungen der Administratoren für die Planung des Upgrades und des tatsächlichen Prozesses sind die Unterhaltungen, die mit anderen Beteiligten ausgeführt werden, auf denen das Upgrade basiert. Beispielsweise zwingen Ökonomie Administratoren manchmal dazu, ihre Pläne zu ändern. Unabhängig von der endgültigen Entscheidung sollten Sie dokumentieren, was der vereinbarte Plan ist, und zwar weiter. Dies kann etwa so aussehen: 
  
 **Mein Aktionsplan:**
  
Lokal verwenden wir eine virtuelle Umgebung zum Erstellen von Standard SharePoint Server 2010 und 2013. SharePoint Server 2016 wird auf neuer Hardware aufbauen, die die Systemanforderungen für 2016 erfüllt. Wir werden Datenbankanfügungen an das Upgrade von Datenbanken aus SharePoint 2007 über alle Versionen zwischen diesem und SharePoint Server 2016 durchführen. Kern Anpassungen werden derzeit in der SharePoint Server 2016-Umgebung neu erstellt und getestet, wenn systemeigene Features nicht bereits unsere Anforderungen erfüllen. Wenn wir erfolgreich sind, haben wir eine lokale Farm auf neuer Hardware mit aktualisierten Datenbanken und weniger Anpassungen. Wir fügen die aktualisierten Inhaltsdatenbanken in SharePoint Server 2013, Test, User Test/Pilot an neue Websitesammlungen an und führen dann einen DNS-Schnitt für die neue SharePoint Server 2016-Umgebung für die Live Nutzung durch.
  
- Wir werden keine Verbund Hybridität zwischen SharePoint Server 2016 und SharePoint Online im Moment in Frage stellen.
    
- Schätzungsweise 35% unserer Websites können in neue SPO-Websites mit Vanity-Domänen umgewandelt werden oder letztendlich OneDrive für Unternehmen Speicher werden. Suchen Sie nach anderen Möglichkeiten zum Konvertieren von Websites oder zum Weiterleiten neuer Websites an SPO.
    
- Ein Teil dieses Teils der Migration wird manuell, per Drag & Drop zu OneDrive für Unternehmen persönlichen Websites und einige durch die Migrations-API.
    
Ausführlichere Schritte oder eine Reihe von Links zu bestimmten Upgrade-Anweisungen sollten einem Plan folgen. Der MOSS 2007-Computer sollte nicht außer Betrieb genommen werden, und virtuelle Umgebungen sollten aus Gründen des Vergleichs beibehalten werden. das Upgrade ist jedoch abgeschlossen, wenn Benutzer zu SharePoint Server 2016 umgeleitet werden.
  
Bei der Auswahl einer Methode sind häufig die Gesamtkosten des Upgrades und die Kosten in der Zeit (Weitere Informationen hierzu finden Sie im Artikel SharePoint-Migrationsplanung). Vorausschauendes Planen wird Ihnen jedoch eine große Bedeutung bei der Festlegung der Erwartungen, der klugen Auswahl und der Gestaltung der Erfolgsaussichten bieten.
  
## <a name="related-links"></a>Verwandte Links

[Ressourcen für das Upgrade von Office 2007-Servern und-Clients](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft Lifecycle Policy and Lifecycle Search](https://support.microsoft.com/lifecycle)
  
[Suchen nach Microsoft-Partnern, die bei einem Upgrade oder einer Migration helfen können](https://partnercenter.microsoft.com/pcv/search)
  

