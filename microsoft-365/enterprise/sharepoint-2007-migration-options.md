---
title: Zu berücksichtigende SharePoint 2007-Migrationsoptionen
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
description: Dieser Artikel enthält Informationen für Benutzer, die SharePoint Server 2007 verwenden, um ihnen bei der Planung ihres Upgrades zu helfen.
ms.openlocfilehash: 38c4713b7dfb705c99d970c5f68a37b031c951a5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924880"
---
# <a name="sharepoint-2007-migration-options-to-consider"></a>Zu berücksichtigende SharePoint 2007-Migrationsoptionen

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Microsoft SharePoint 2007 und SharePoint Server 2007 haben das Ende der Unterstützung erreicht. Es ist an der Zeit, ein Upgrade zu durchführen! Dieser Artikel enthält Informationen zu Ihren Migrationsoptionen.
  
## <a name="common-upgrade-strategies-for-sharepoint"></a>Allgemeine Upgradestrategien für SharePoint

Es gibt mehrere Methoden zum Upgrade einer SharePoint Server-Umgebung. Wenn Sie über eine Microsoft Office SharePoint Server 2007-Farm verfügen, finden Sie hier einige Beispiele für die Upgrademethoden:
  
- Update durch Datenbankanfügungen
    
- Side-by-side-Upgrade
    
- Direktes Upgrade
    
- Hybridupgrade (in-place mit getrennten Datenbanken/separatem Datenbank-Anfügen)
    
- SharePoint-Hybride (Online-Verbindung mit lokalem SharePoint herstellen)
    
- Manuelles Verschieben von Daten zwischen Websitesammlungen oder Bibliotheken
    
- Upgrade des FastTrack-Assistenten auf Microsoft 365 ([SharePoint Online-Bereitstellungsratgeber](https://aka.ms/spoguidance))
    
- Migrations-API zu SharePoint Online (SPO) in Microsoft 365
    
Was funktioniert am besten für Sie?
  
Ihr Wissen darüber, wofür Ihre Farm funktioniert und wofür sie verwendet wird, ist eine taktische Stärke beim Upgrade. Die Art und Weise, wie Personen die SharePoint-Farm verwenden, hilft Ihnen bei der Auswahl Ihrer Optionen.
  
> [!TIP]
> Microsoft Office Von SharePoint Server 2007 wird auch ein schrittweises Upgrade nicht behandelt. Eine Liste der schrittspezifischen Upgradeartikel finden Sie im [SharePoint Server 2007-Ende der Support-Roadmap](sharepoint-2007-end-of-support.md). 
  
Denken Sie daran, die [Produktlebenszyklus-](https://support.microsoft.com/lifecycle/search) und Systemanforderungen auf die Version von SharePoint zu überprüfen, auf die Sie ein Upgrade durchführen. Dies ist so, dass Sie wissen, wann das nächste Upgrade erforderlich ist (z. B. wenn Sie bei einem Legacyprodukt wie SharePoint Server 2010 anhalten, um weitere Upgrades zu planen, stellen Sie sicher, dass Sie das Ende des Supportdatums kennen), und um sicher zu sein, dass Sie über Hardware verfügen, die Ihren Plan unterstützt. 
  
Wenn Sie planen, einige oder alle Ihrer SharePoint-Websites zu Microsoft 365 in der Cloud zu überstellen, ist es an der Zeit, einen Link zu den [Microsoft 365- und Office 365-Dienstbeschreibungen](/office365/servicedescriptions/office-365-service-descriptions-technet-library)mit einem Lesezeichen zu versehen. Sie benötigen die Dienstbeschreibungen, um mehr über SharePoint Online-Features und deren Unterschiede zu lokalen SharePoint Server zu erfahren. Aktualisieren sie Microsoft Office SharePoint Server 2007-Farmen. Wenn ihre Installation beschädigte Websites hat, beheben Sie sie vor dem Upgrade.
  
## <a name="a-note-about-managing-risk"></a>Hinweis zum Verwalten von Risiken

Methoden wie "nebeneinander" sind im Schema der Upgradelogik wichtig. Wenn Sie ein nebeneinander ausgeführtes Upgrade durchführen, verwalten Sie Ihre Microsoft Office SharePoint Server 2007-Farm, erstellen jedoch auf neuer Hardware die nächste Version von dieser Farm (SharePoint Server 2010). Dies hilft auf drei Arten:
  
1. Sie haben die Stelle, um Sicherungen ihrer Microsoft Office SharePoint Server 2007-Datenbanken zu erstellen, um sie mithilfe von Datenbankattaching getrennt zu aktualisieren.
    
2. Wenn Sie herausfinden, dass in Ihrer Microsoft Office SharePoint Server 2007-Farm nur eine kleine Anzahl kritischer Dokumentbibliotheken und anderer Informationen verwendet wird, können Sie daten manuell von Microsoft Office SharePoint Server 2007 nach SharePoint Server 2010 verschieben oder nur bestimmte Websites und Webs zur nächsten Version verschieben (was Ihre Arbeit vereinfachen kann).
    
3. Je weniger Sie für die Microsoft Office SharePoint Server 2007-Serverfarm tun, desto sicherer sind die Daten, die die Farm beim Upgrade enthält.
    
Methoden wie In-Place-Upgrade wirken sich direkt auf Ihre Microsoft Office SharePoint Server 2007-Farm aus, was Ihnen weniger einfache Optionen zum Verlassen eines Pfads und zum erneuten Starten mit Ihrer ursprünglichen Umgebung bietet. Erstellen Sie so weit wie möglich einige Sicherheitsmaßnahmen (z. B. das Erstellen und Testen von Sicherungen der ursprünglichen Umgebung). Wenn Ihre Microsoft Office SharePoint Server 2007-Farm beispielsweise virtuell ist und zum Sichern und Wiederherstellen dupliziert wird, sichern und wiederherstellen Sie die aktuellen Datenbanken vor dem Dienstfenster für das Upgrade. Wenn Sie wissen, dass Sie über die Möglichkeit zum Wiederherstellen von Datenbanksicherungen verfügen, erhalten Sie nicht nur einen failsafe-Fehler, sondern können sich sicher sein.
  
> [!TIP]
> Best practices documents for upgrade exist for [Microsoft Office SharePoint Server 2007](/previous-versions/office/sharepoint-2007-products-and-technologies/cc261992(v=office.12)), [SharePoint Server 2010](/previous-versions/office/sharepoint-server-2010/cc261992(v=office.14)), [SharePoint Server 2013](/SharePoint/upgrade-and-update/best-practices-for-upgrading-from-sharepoint-2010-to-sharepoint-2013)und [SharePoint Server 2016](/SharePoint/upgrade-and-update/best-practices-for-upgrade). Sie können auch nach [Microsoft-Partnern suchen,](https://partnercenter.microsoft.com/pcv/search) die Erfahrung mit Upgrades oder Microsoft 365-Migrationen haben. 
  
## <a name="make-your-plan"></a>Erstellen Ihres Plans

Wenn Sie ein Upgrade durchführen müssen, benötigen Sie einen Plan, und eine Größe passt in diesen Fällen nicht zu allen. Ihr Plan kann so einfach sein wie "Erstellen eines Microsoft 365-Abonnements mit SharePoint Online, Registrieren einer Domäne und Umleiten von Personen zum Speichern ihrer Dateien dort". Und das ist es möglicherweise nicht. Diese Entscheidung liegt bei Ihnen, und es liegt an dem, was Sie und Ihre Benutzer wirklich benötigen.
  
> [!NOTE]
> Es ist riskant, auf Software ausgeführt zu werden, deren Lebenszyklus beendet ist. Produkte, die nicht mehr unterstützt werden, werden nicht mehr gepatcht, wenn Probleme gefunden werden. Dies bedeutet auch, dass es keine Sicherheitspatches oder -korrekturen gibt, wenn neue Sicherheitsbedrohungen auftreten, da die Produkte am Ende des Lebenszyklus nicht mehr unterstützt werden. Vermeiden Sie diese Situation! 
  
### <a name="first-know-your-farm"></a>Kennen Sie zuerst Ihre Farm

Beim Upgrade sollte Ihre Entscheidungsfindung auf der Farm für Ihre Organisation basieren. Welche Anforderungen erfüllt sie? Welche Rolle spielt sie? Jede Farm in Ihrem Unternehmen hat möglicherweise eine andere Rolle. Einige Ihrer SharePoint-Farmen sind möglicherweise  *kritisch,*  einige sind Dateiarchive – dort zur Aufbewahrung. Wenn Ihre Farm viele Rollen gleichzeitig ausfüllt, müssen Sie möglicherweise wissen, welche Websitesammlungen, Webs oder sogar Dokumentbibliotheken, welche Anpassungen vorgenommen werden und wie wichtig sie sind. Die Analyse Ihrer Daten auf dieser Ebene mag wie eine Menge Arbeit erscheinen, aber es spart Zeit und Mühe, Ihre Domäne zu beherrschen, bevor Sie sie aktualisieren oder migrieren. Sobald Sie alle sich bewegenden Teile und die wichtigsten Bits kennen, wissen Sie auch, was Sie auswachsen und hinterlassen können. Dieses Wissen nützt Ihnen nur weiter. 
  
Was sagen die Benutzer also vor allem über Ihre SharePoint Server-Farm?
  
- Integrierte SharePoint-Features
    
- Der große Datenkorpus (z. B. ein Archiv von Dateien)
    
- Verfügbarkeit
    
- Kritische Apps, Webparts oder Dokumente in der Farm (mission critical farm)
    
- Die Compliancestandards erfüllt
    
- Anpassungen
    
Wenn Sie etwas Wesentliches für Ihr Unternehmen in Ihrer SharePoint-Farm ausführen, sagen Sie, dass es wie ein großer Katalog wichtiger Daten zu Clientdienstanforderungen funktioniert, können Sie neben "Kritische Apps" einen Tick setzen, aber auch "Verfügbarkeit". Das heißt, Ihr Unternehmen würde sich auswirken, wenn Sie SharePoint für eine Weile nicht verwenden könnten. Ebenso können Sie "Anpassungen" überprüfen, da die kritischen Dienste, die Ihre Farm anbietet, auf benutzerdefiniertem Code, Websitedefinitionen oder einer Reihe von Anpassungen basieren, die zusammenarbeiten.
  
Wenn SharePoint diese Anforderungen erfüllt hat, ohne dass Sie etwas außerhalb der Verwendung der integrierten Software tun müssen, und Sie es im Allgemeinen aktualisieren und normale Verwaltung und Wartung durchführen, haben Sie möglicherweise "Integriertes SharePoint" ausgewählt – dies kann auch Der Grund dafür sein, auf einer älteren Version von SharePoint zu sitzen. Mit anderen Worten: Sie macht bereits das, wofür Sie es benötigen, und Sie müssen bis jetzt am Ende der Supportunterstützung Microsoft Office SharePoint Server 2007 kein Upgrade durchführen.
  
Wenn Sie diese Dinge auflisten, erstellen Sie Kriterien für Ihr Upgrade. Anders ausgedrückt: Jedes Upgrade müsste diese Leiste erfüllen, um berücksichtigt zu werden. Auf diese Weise können Sie Methoden ausschließen, die derzeit nicht Ihren Anforderungen entsprechen.
  
### <a name="a-simple-sample-plan"></a>Ein einfacher Beispielplan

Es kann erforderlich sein, einen umfassenderen Konsens mit der Führung und anderen Administratoren auf dem Weg zu finden, den Ihr SharePoint-Upgrade einschlagen wird. SharePoint Server-Administratoren arbeiten häufig mit Microsoft SQL Server zusammen, arbeiten mit Netzwerk- und Sicherheitsteams zusammen und vieles mehr. Wenn es viele Beteiligte gibt, müssen Sie möglicherweise eine Vereinbarung für Ihren Upgrade- und Migrationsplan erstellen oder anpassen. Wenn Sie z. B. Daten so migrieren, dass ein Teil Ihres Unternehmens SharePoint Online in Microsoft 365 verwendet, muss wahrscheinlich eine Leistungsoptimierung oder Tests in Ihrem Netzwerk durchgeführt werden. Betroffene Teams sollten im Voraus informiert werden.
  
In meinem einfachen Beispiel zeige ich den Vorschlag eines SharePoint-Administrators und dann den Plan auf, auf den sich alle Beteiligten verständigt haben. Dokumentieren Sie aus Gründen der Übersichtlichkeit Ihre Vereinbarungen und Entscheidungen.
  
Der Plan beginnt nach einer eingehenden Analyse einer Farm und versucht, die Rolle der Farm, Diekpunkte und andere wichtige Informationen zu identifizieren, die zu einer Verengung einiger Upgradeoptionen führen. Anschließend wird ein Upgradevorschlag vom SharePoint-Administrator gemacht, und die Beteiligten einigen sich auf einen Aktionsplan.
  
Meine "wichtigste" Aufzählung:
  
- Verfügbarkeit, in SharePoint integrierte Features und Compliancestandards.
    
- Die meisten Daten befinden sich in drei Websitesammlungen, und ein Besprechungsarbeitsbereich wird von einem Dev-Team besonders wichtig und in mehreren Zeitzonen weltweit verwendet.
    
- Es gibt 17 weitere Websites, die weit verbreitet sind.
    
- Zwei Dokumentbibliotheken (Besprechungsarbeitsbereich und Dokumente in der Stammwebsitesammlung) sind die größten (jeweils über 8000 Dokumente). Wir haben eine große Anzahl von archivierten Dokumenten und Listen mit Tabellenkalkulationsanlagen.
    
- Es gibt 14 Listen von Bibliotheken mit vertraulichen Daten, die in Der Compliance bleiben müssen.
    
- Wir MÜSSEN in der Lage sein, halte- und e-discovery-Möglichkeiten zu haben, wo immer wir hingehen.
    
- Einige dieser Daten müssen aufgrund von InfoSec-Regeln lokal bleiben.
    
 **Meine Upgrade- und Migrationsentscheidungen:**
  
| Ja | Nein |
|:-----|:-----|
|Aktualisieren von Datenbanken mit Datenbank-Anfügen  <br/> |Direktes Upgrade  <br/> |
|Upgrade mit Farmen nebeneinander  <br/> |Hybridupgrade  <br/> |
|Migrations-API zu SPO in Microsoft 365 (für persönliche Websitedaten)  <br/> |SharePoint Hybrid (noch nicht erforderlich)  <br/> |
|Einige manuelle Datenmigrationen zu SharePoint Online für kritische Daten  <br/> |Upgrade des FastTrack-Assistenten auf Microsoft 365  <br/> |
   
 **Mein vorgeschlagener Plan:**
  
Aktualisieren Sie lokal mit Versionen von SharePoint nebeneinander, einige virtualisiert, sodass wir die Datenbanken zuerst aktualisieren können. Wechseln Sie von SharePoint 2007 zu SharePoint 2010. Administratoren und Devs testen die resultierende Farm. Benutzer testen die resultierende Farm. Behebung von Showstoppproblemen während dieser Zeit. Aktualisieren Sie sharePoint 2010-Datenbanken auf SharePoint 2013. Testen. Benutzertest/Pilot. Behebung von Showstoppproblemen während dieser Zeit.
  
- Überlegen Sie, ob eine Such-Verbundhybrid mit SPO Ihren Anforderungen entspricht.
    
- Erwägen [Sie die FastTrack-Unterstützung,](https://fasttrack.microsoft.com) wenn Sie von hier aus ein Upgrade auf SharePoint Online durchführen möchten. 
    
- Ermitteln Sie, ob Websitesammlungen in ein Microsoft 365-Abonnement offloaded werden können. (Microsoft 365 erfüllt viele [Compliancestandards.](/compliance/regulatory/offering-home) Microsoft 365 verfügt [über eDiscovery](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da) und kann [halte über](https://support.office.com/article/A18F8975-AA7F-43B4-A7D6-001D14744D8E) das Compliance Center tun.) 
    
Andernfalls führen Sie ein nebeneinander ausgeführtes Upgrade auf SharePoint Server 2016 aus.
  
> [!NOTE]
> Zwischen den Empfehlungen der Administratoren, die das Upgrade planen, und dem tatsächlichen Prozess liegen die Unterhaltungen mit anderen Beteiligten, auf denen das Upgrade basiert. So z. B. z. B. z. B. die wirtschaftlichen Aspekte, die Administratoren zwingen, ihre Pläne zu ändern. Unabhängig von der endgültigen Entscheidung sollten Sie dokumentieren, was der vereinbarte Plan ist. Dies kann etwa so aussehen: 
  
 **Mein Aktionsplan:**
  
Lokal verwenden wir eine virtuelle Umgebung zum Erstellen von SharePoint Server 2010 und 2013. SharePoint Server 2016 wird auf neuer Hardware aufgebaut, die die Systemanforderungen für 2016 erfüllt. Wir führen Datenbank-Attaches aus, um Datenbanken von SharePoint 2007 über alle Versionen zwischen sharePoint Server und SharePoint Server 2016 zu aktualisieren. Kernanpassungen werden derzeit für die SharePoint Server 2016-Umgebung neu erstellt und getestet, wenn systemeigene Features unsere Anforderungen noch nicht erfüllen. Wenn wir erfolgreich sind, verfügen wir über eine lokale Farm auf neuer Hardware mit aktualisierten Datenbanken und weniger Anpassungen. Wir fügen die aktualisierten Inhaltsdatenbanken an neue Websitesammlungen in SharePoint Server 2013 an, testen, benutzertest/pilot und nehmen dann einen DNS-Cut-Over für die neue SharePoint Server 2016-Umgebung zur Livenutzung vor.
  
- Wir werden derzeit keine Verbundhybrid zwischen SharePoint Server 2016 und SharePoint Online in Betracht ziehen.
    
- Geschätzte 35 % unserer Websites können in neue #A0 mit Eitelkeitsdomänen oder letztendlich in OneDrive for #A1 verwandelt werden. Suchen Sie nach anderen Möglichkeiten zum Konvertieren von Websites oder zum Routen neuer Websites an SPO.
    
- Einige dieser Teile der Migration werden manuell per Drag #A0 zu persönlichen OneDrive for #A1 und andere per Migrations-API erstellt.
    
Ausführlichere Schritte oder eine Reihe von Links zu bestimmten Upgraderichtungen sollten einem Plan folgen. Der MOSS 2007-Computer sollte nicht außer Betrieb genommen werden, und virtuelle Umgebungen sollten zum Vergleich beibehalten werden. Das Upgrade ist jedoch abgeschlossen, wenn Benutzer zu SharePoint Server 2016 umgeleitet werden.
  
Häufig sind die Gesamtkosten des Upgrades und die Zeitkosten bei der Auswahl einer Methode (weitere Informationen dazu finden Sie im Artikel SharePoint Migration Roadmap). Die Vorausplanung nützt Ihnen jedoch erheblich, wenn Sie Erwartungen festlegen, mit Bedacht auswählen und festlegen, wie der Erfolg aussehen wird.
  
## <a name="related-links"></a>Verwandte Links

[Ressourcen, die Ihnen beim Upgrade von Office 2007-Servern und -Clients helfen](upgrade-from-office-2007-servers-and-products.md)
  
[Microsoft Lifecycle Policy and Lifecycle search](https://support.microsoft.com/lifecycle)
  
[Suchen nach Microsoft-Partnern, die beim Upgrade oder bei der Migration helfen können](https://partnercenter.microsoft.com/pcv/search)
