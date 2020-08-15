---
title: 'Office 365-Leistung optimieren mit Basisplänen und Leistungsverlauf '
ms.author: tracyp
author: MSFTTracyP
manager: laurawi
ms.date: 8/31/2017
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 1492cb94-bd62-43e6-b8d0-2a61ed88ebae
ms.collection:
- M365-security-compliance
- Ent_O365
- SPO_Content
description: Hier erfahren Sie, wie Sie den Verlauf ihrer Clientcomputerverbindungen überprüfen, damit Sie frühzeitig auftretende Probleme erkennen.
ms.openlocfilehash: 2337b14542f894e9a62037b2f032632147e45e09
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690550"
---
# <a name="office-365-performance-tuning-using-baselines-and-performance-history"></a>Office 365-Leistung optimieren mit Basisplänen und Leistungsverlauf 

Es gibt einige einfache Möglichkeiten, die Verbindungsleistung zwischen Office 365 und Ihrem Unternehmen zu überprüfen, sodass Sie eine grobe Basislinie ihrer Konnektivität einrichten können. Wenn Sie den Leistungsverlauf ihrer Clientcomputerverbindungen kennen, können Sie auftretende Probleme frühzeitig erkennen, Probleme identifizieren und Vorhersagen.
  
Wenn Sie nicht mit Leistungsproblemen arbeiten, sollten Sie sich in diesem Artikel mit einigen häufig gestellten Fragen vertraut machen, wie Sie wissen, dass das Problem, das Sie sehen, ein Leistungsproblem ist und kein Office 365 Dienst Vorfall ist? Wie können Sie langfristig eine gute Leistung planen? Wie können Sie die Leistung im Auge behalten? Wenn Ihr Team oder Ihre Clients bei der Verwendung von Office 365 eine langsame Leistung erzielen und Sie sich über diese Fragen Gedanken machen, lesen Sie weiter.
  
> [!IMPORTANT]
> **Haben Sie ein Leistungsproblem zwischen Ihrem Client und Office 365 im Moment?** Führen Sie die Schritte aus, die im [Leistungsproblem Behandlungsplan für Office 365](performance-troubleshooting-plan.md)beschrieben werden. 
    
## <a name="something-you-should-know-about-office-365-performance"></a>Was Sie über Office 365 Leistung wissen sollten

Office 365 lebt in einem dedizierten Microsoft-Netzwerk mit hoher Kapazität, das nicht nur von der Automatisierung, sondern auch von echten Personen ständig überwacht wird. Ein Teil der Rolle des Aufrechterhaltens der Office 365 Cloud besteht in der Leistungsoptimierung und-Optimierung, sofern möglich. Da Clients der Office 365 Cloud über das Internet eine Verbindung herstellen müssen, besteht ein kontinuierlicher Aufwand zur Optimierung der Leistung in Office 365 Diensten. Leistungsverbesserungen werden in der Cloud nie wirklich angehalten, und es gibt eine Menge gesammelter Erfahrungen, um die Cloud gesund und schnell zu halten. Wenn ein Leistungsproblem beim Herstellen einer Verbindung zwischen Ihrem Standort und Office 365 auftritt, sollten Sie am besten nicht mit einem Support Fall beginnen und warten. Stattdessen sollten Sie mit der Untersuchung des Problems von "Inside Out" beginnen. Das heißt, starten Sie innerhalb Ihres Netzwerks, und arbeiten Sie sich an Office 365. Bevor Sie einen Fall mit Office 365-Unterstützung öffnen, können Sie Daten sammeln und Aktionen ausführen, mit denen Ihr Problem erforscht und möglicherweise behoben wird.
  
> [!IMPORTANT]
> Beachten Sie die Kapazitätsplanung und Grenzwerte in Office 365. Diese Informationen werden Sie bei dem Versuch, ein Leistungsproblem zu beheben, vor die Kurve stellen. Hier ist ein Link zu den [Microsoft 365-und Office 365-Dienstbeschreibungen](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library). Dies ist ein zentraler Hub, und alle von Office 365 angebotenen Dienste verfügen über einen Link, der von hier aus zu ihren eigenen Dienstbeschreibungen wechselt. Wenn Sie also beispielsweise die Standardgrenzwerte für SharePoint Online anzeigen möchten, klicken Sie auf [SharePoint Online Dienstbeschreibung](https://technet.microsoft.com/library/sharepoint-online-service-description.aspx) , und suchen Sie den [Abschnitt SharePoint Online Grenzwerte](https://go.microsoft.com/fwlink/p/?LinkID=856113). 
  
Stellen Sie sicher, dass Sie in die Problembehandlung mit dem Verständnis eingehen, dass Leistung eine gleitende Skala ist, dass es nicht darum geht, einen idealisierten Wert zu erzielen und ihn dauerhaft beizubehalten (wenn Sie dies so glauben, sind gelegentliche Aufgaben mit hoher Bandbreite wie das on-Boarding einer großen Anzahl von Benutzern oder das Ausführen großer Datenmigrationen sehr stressig – planen Sie also die Sie können und sollten eine grobe Vorstellung von ihren Leistungszielen haben, aber viele Variablen spielen in der Leistung, daher variiert die Leistung. Das ist die Art der Leistung. 
  
Bei der Leistungsproblembehandlung geht es nicht darum, bestimmte Ziele zu erreichen und diese Zahlen auf unbestimmte Zeit beizubehalten, sondern es geht um die Verbesserung vorhandener Aktivitäten, da alle Variablen vorhanden sind. 
  
## <a name="okay-what-does-a-performance-problem-look-like"></a>Okay, wie sieht ein Leistungsproblem aus?

Zunächst müssen Sie sicherstellen, dass das, was Sie erleben, tatsächlich ein Leistungsproblem und kein Dienst Vorfall ist. Ein Leistungsproblem unterscheidet sich von einem Dienst Vorfall in Office 365. Hier erfahren Sie, wie Sie sie voneinander unterscheiden.
  
Wenn der Office 365 Dienst Probleme hat, handelt es sich um einen Dienst Vorfall. Sie werden rote oder gelbe Symbole unter **aktuelle Integrität** im Microsoft 365 Admin Center angezeigt werden, können Sie auch feststellen, langsame Leistung auf Clientcomputern, die sich mit Office 365 verbinden. Wenn beispielsweise der aktuelle Status ein rotes Symbol meldet und Sie die unter **suchung** neben Exchange sehen, erhalten Sie möglicherweise auch eine Reihe von Anrufen von Personen in Ihrer Organisation, die sich darüber beschweren, dass Clientpostfächer, die Exchange Online verwenden, schlecht ausgeführt werden. In diesem Fall ist es sinnvoll, davon ausgehen, dass Ihre Exchange Online Leistung nur ein Opfer von Problemen innerhalb des Diensts geworden ist. 
  
![Das Office 365 Integritäts Dashboard mit allen Arbeitsauslastungen, die grün angezeigt werden, mit Ausnahme von Exchange, das den wiederhergestellten Dienst anzeigt.](../media/ec7f0325-9e61-4e1a-bec0-64b87f4469be.PNG)
  
An diesem Punkt sollten Sie, der Office 365 Administrator, die **aktuelle Integrität** überprüfen und dann häufig **Details und Verlauf anzeigen**, um auf dem Laufenden zu bleiben, was die Wartung betrifft, die wir im System durchführen. Das **aktuelle Integritäts** Dashboard wurde erstellt, um Sie über Änderungen an und Probleme in dem Dienst zu informieren. Die Hinweise und Erläuterungen, die in den Integritäts Verlauf geschrieben wurden, Administrator an Administrator, stehen Ihnen zur Verfügung, um ihre Auswirkungen zu beurteilen und um Sie über die laufende Arbeit auf dem Laufenden zu halten. 
  
![Ein Bild des Office 365 Integritäts Dashboards, in dem erklärt wird, dass der Exchange Online Dienst wiederhergestellt wurde und warum.](../media/66609554-426a-4448-8be6-ea09817f41ba.PNG)
  
Ein Leistungsproblem ist kein Dienst Vorfall, auch wenn Vorfälle eine langsame Leistung verursachen können. Ein Leistungsproblem sieht wie folgt aus:
  
- Ein Leistungsproblem tritt auf, unabhängig davon, was die **aktuelle Integrität** des Admin Centers für den Dienst meldet. 
    
-  Ein Verhalten, das früher relativ nahtlos verläuft, erfordert lange Zeit bis zum Abschluss oder wird nie abgeschlossen. 
    
- Sie können das Problem auch replizieren, oder zumindest wissen Sie, dass es passieren wird, wenn Sie die richtige Reihe von Schritten ausführen.
    
-  Wenn das Problem nur sporadisch auftritt, gibt es ein Muster, beispielsweise wissen Sie, dass Sie von 10:00 Uhr Anrufe von Benutzern haben, die nicht zuverlässig auf Office 365 zugreifen können, und dass die Anrufe um 12.00 Uhr Absterben werden. 
    
Dies klingt wahrscheinlich vertraut; vielleicht zu vertraut. Wenn Sie wissen, dass es sich um ein Leistungsproblem handelt, wird die Frage "Was tun Sie als nächstes tun?". Der Rest dieses Artikels hilft Ihnen, genau zu bestimmen.
  
## <a name="how-to-define-and-test-the-performance-problem"></a>Vorgehensweise definieren und Testen des Leistungsproblems

Leistungsprobleme treten häufig im Laufe der Zeit auf, daher kann es schwierig sein, das tatsächliche Problem zu definieren. Sie müssen eine gute Problemstellung und eine gute Idee des Problem Kontexts erstellen, und dann müssen Sie wiederholbare Testschritte durchführen, um den Tag zu gewinnen. Andernfalls können Sie verloren gehen, ohne dass Sie selbst verschuldet haben. Warum? Nun, hier sind einige Beispiele für Problem-Statements, die nicht genügend Informationen liefern:
  
- Das Wechseln von meinem Posteingang in meinen Kalender war früher etwas, das ich nicht bemerkt habe, und jetzt ist es ein Kaffeepause. Kann es wie gewohnt handeln?
    
- Das Hochladen von Dateien in SharePoint Online dauert für immer an. Warum ist es am Nachmittag langsam, aber jedes andere Mal ist es schnell? Kann es nicht einfach schnell sein?
    
Die obigen Problemstellungen stellen mehrere große Herausforderungen dar. Konkret gibt es viele Unklarheiten, mit denen Sie umgehen müssen. Beispiel:
  
- Es ist Unklarheiten darüber, wie das Wechseln zwischen Posteingang und Kalender verwendet wurde, um auf dem Laptop zu agieren.
    
- Wenn der Benutzer sagt: "kann nicht einfach schnell sein", was ist "schnell"?
    
- Wie lange ist "Forever"? Ist das einige Sekunden oder Minuten, oder kann der Benutzer zu einem Mittagessen wechseln und es würde zehn Minuten nach dem zurückkehren des Benutzers fertig sein?
    
All dies ist ohne Rücksicht darauf, dass der Administrator und die Problembehandlung viele Details aus Problem Anweisungen wie diese nicht erkennen können. Zum Beispiel, als das Problem begann; , Dass der Benutzer von zu Hause aus funktioniert und immer nur langsames wechseln in einem Heimnetzwerk sieht; , Dass der Benutzer mehrere andere arbeitsspeicherintensive Anwendungen auf dem lokalen Client ausführen muss, oder dass der Benutzer ein älteres Betriebssystem ausführt oder keine letzten Aktualisierungen ausgeführt hat.
  
Wenn Benutzer ein Leistungsproblem melden, werden viele Informationen gesammelt. Das Sammeln dieser Informationen ist Teil eines Prozesses, der das Problem als Bereichsdefinition bezeichnet wird, oder Untersuchung. Im folgenden finden Sie eine grundlegende Bereichs Übersichtsliste, mit der Sie Informationen zu Ihrem Leistungsproblem erfassen können. Diese Liste ist nicht erschöpfend, aber Sie ist die erste Anlaufstelle: 
  
- An welchem Datum ist das Problem aufgetreten, und um welche Tageszeit oder Nacht?
    
- Welche Art von Clientcomputer haben Sie verwendet, und wie stellt er eine Verbindung mit dem Unternehmensnetzwerk her (VPN, verkabelt, drahtlos)?
    
- Haben Sie Remote gearbeitet oder waren Sie im Büro?
    
- Haben Sie die gleichen Aktionen auf einem anderen Computer ausprobiert und dasselbe Verhalten gesehen?
    
- Führen Sie die Schritte durch, die Ihnen die Probleme bereiten, damit Sie die von Ihnen ausgeführten Aktionen schreiben können.
    
- Wie langsam ist die Leistung in Sekunden oder Minuten?
    
- Wo auf der Welt befinden Sie sich?
    
Einige dieser Fragen sind offensichtlicher als andere. Die meisten Benutzer verstehen, dass eine Problembehandlung die genauen Schritte zum Reproduzieren des Problems benötigt. Wie sonst können Sie aufzeichnen, was falsch ist, und wie sonst können Sie testen, ob das Problem behoben ist? Nicht so offensichtlich sind Dinge wie "Datum und Uhrzeit, zu der das Problem angezeigt wurde?" und "wo in der Welt befinden Sie sich?", Informationen, die gemeinsam verwendet werden können. Je nachdem, wann der Benutzer arbeitete, kann ein paar Stunden Zeitunterschied bedeuten, dass in Teilen des Netzwerks des Unternehmens bereits Wartungsarbeiten ausgeführt werden. Wenn Ihr Unternehmen beispielsweise eine hybride Implementierung wie eine hybride SharePoint-Suche aufweist, die Suchindizes sowohl in SharePoint Online als auch in einer lokalen SharePoint Server 2013-Instanz Abfragen kann, sind Updates möglicherweise in der lokalen Farm im Gange. Wenn sich Ihr Unternehmen in der Cloud befindet, kann die Systemwartung das Hinzufügen oder Entfernen von Netzwerkhardware, das Bereitstellen von unternehmensweiten Updates oder das vornehmen von Änderungen an DNS oder einer anderen Kerninfrastruktur umfassen.
  
Wenn Sie ein Leistungsproblem beheben, ist es ein bisschen wie ein Tatort, Sie müssen genau und aufmerksam sein, um daraus Schlussfolgerungen aus dem Beweis zu ziehen. Um dies zu erreichen, müssen Sie eine gute Problem Anweisung erhalten, indem Sie Beweise sammeln. Es sollte den Kontext des Computers, den Kontext des Benutzers, wenn das Problem begann, und die genauen Schritte, die das Leistungsproblem verfügbar gemacht enthalten. Diese Problemstellung sollte die oberste Seite in Ihren Notizen sein und bleiben. Wenn Sie die Problemstellung durchlaufen, nachdem Sie die Lösung bearbeitet haben, führen Sie die Schritte aus, um zu testen und zu überprüfen, ob die von Ihnen ausgeführten Aktionen das Problem gelöst haben. Dies ist wichtig, um zu wissen, wann Ihre Arbeit dort fertig ist.
  
## <a name="do-you-know-how-performance-used-to-look-when-it-was-good"></a>Wissen Sie, wie die Leistung verwendet wurde, um zu sehen, wenn es gut war?

Wenn Sie Pech haben, weiß niemand Bescheid. Niemand hatte Zahlen. Das bedeutet, dass niemand die einfache Frage beantworten kann: "wie viele Sekunden hat es verwendet, um einen Posteingang in Office 365 zu öffnen?" oder "wie lange dauerte es, bis die Führungskräfte eine lync Online Besprechung durchgeführt haben?", was ein gängiges Szenario für viele Unternehmen ist.
  
Hier fehlt eine Leistungsbasis.
  
Baselines bieten Ihnen einen Kontext für Ihre Leistung. Je nach den Anforderungen Ihres Unternehmens sollten Sie gelegentlich einen Basisplan erstellen. Wenn Sie ein größeres Unternehmen sind, kann Ihr Betriebsteam bereits Basispläne für Ihre lokale Umgebung nutzen. Wenn Sie beispielsweise alle Exchange-Server am ersten Montag des Monats und alle Ihre SharePoint-Server am dritten Montag Patchen, verfügt Ihr Betriebsteam wahrscheinlich über eine Liste von Aufgaben und Szenarien, die nach dem Patchen ausgeführt werden, um nachzuweisen, dass wichtige Funktionen funktionsfähig sind. Öffnen Sie beispielsweise den Posteingang, klicken Sie auf senden/empfangen, und stellen Sie sicher, dass die Ordner aktualisiert werden, oder führen Sie in SharePoint die Hauptseite der Website durch, navigieren Sie zur Seite Enterprise-Suche, und führen Sie eine Suche aus, die Ergebnisse zurückgibt.
  
Wenn sich Ihre Anwendungen in Office 365 befinden, sind einige der grundlegendsten Grundlagen, die Sie für die Zeit (in Millisekunden) von einem Clientcomputer innerhalb Ihres Netzwerks, bis hin zu einem Ausgangspunkt oder dem Punkt, an dem Sie Ihr Netzwerk verlassen, und zum ausgehen Office 365 zu ermitteln. Hier sind einige hilfreiche Basispläne, die Sie untersuchen und aufzeichnen können:
  
- Identifizieren Sie die Geräte zwischen dem Clientcomputer und dem Ausgangspunkte, beispielsweise Ihrem Proxy Server.
    
  - Sie müssen Ihre Geräte kennen, damit Sie über einen Kontext (IP-Adressen, Gerätetyp, usw.) für Leistungsprobleme verfügen, die entstehen.
    
  - Proxy Server sind häufige Ausgangspunkte, sodass Sie Ihren Webbrowser überprüfen können, um zu sehen, welchen Proxy Server er verwendet (sofern vorhanden).
    
  - Es gibt Tools von Drittanbietern, die Ihr Netzwerk erkennen und zuordnen können, aber die sicherste Möglichkeit, Ihre Geräte zu kennen, ist, ein Mitglied Ihres Netzwerkteams zu Fragen.
    
- Identifizieren Sie Ihren Internet Dienstanbieter (ISP), notieren Sie Ihre Kontaktinformationen, und Fragen Sie, wie viele Schaltkreise die Bandbreite aufweisen.
    
- Identifizieren Sie innerhalb Ihres Unternehmens Ressourcen für die Geräte zwischen Ihrem Client und dem Ausgangspunkte, oder identifizieren Sie einen Notfallkontakt, mit dem Sie über Netzwerkprobleme sprechen.
    
Hier sind einige Grundlinien, die einfache Tests mit Tools für Sie berechnen können:
  
- Zeit zwischen dem Clientcomputer und Ihrem Ausgangspunkte in Millisekunden
    
- Zeit von Ihrem Ausgangspunkte bis Office 365 in Millisekunden
    
- Speicherort in der Welt des Servers, der die URLs für Office 365 auflöst, wenn Sie durchsuchen
    
- Die Geschwindigkeit der DNS-Auflösung Ihres ISP in Millisekunden, Inkonsistenzen bei der Paket Ankunft (Netzwerk Jitter), Upload-und Downloadzeiten in Millisekunden
    
Wenn Sie mit der Ausführung dieser Schritte nicht vertraut sind, werden wir in diesem Artikel ausführlicher darauf eingehen. 
  
## <a name="what-is-a-baseline"></a>Was ist ein Basisplan?

Sie kennen die Auswirkungen, wenn es schlecht geht, aber wenn Sie Ihre historischen Leistungsdaten nicht kennen, kann es nicht möglich sein, einen Kontext dafür zu haben, wie schlecht er geworden ist und wann. Ohne einen Basisplan fehlt Ihnen also der Schlüssel Hinweis zur Lösung des Rätsels: das Bild im Puzzle-Feld. Bei der Leistungsproblembehandlung benötigen Sie eine  *Vergleichs*  Position. Einfache Leistungsbasislinien sind nicht schwer zu übernehmen. Ihr Betriebsteam kann mit dem Ausführen dieser Aufgaben nach einem Zeitplan beauftragt werden. Angenommen, Ihre Verbindung sieht wie folgt aus: 
  
![Eine grundlegende Netzwerk Grafik mit Client, Proxy und Office 365 Cloud.](../media/c6ca7140-09f9-4c2d-a775-dbf2820eaa0c.PNG)
  
Das bedeutet, dass Sie mit Ihrem Netzwerkteam überprüfen und herausgefunden haben, dass Sie Ihr Unternehmen über einen Proxy Server für das Internet verlassen, und dass der Proxy alle Anforderungen verarbeitet, die Ihr Clientcomputer an die Cloud sendet. In diesem Fall sollten Sie eine vereinfachte Version Ihrer Verbindung zeichnen, die alle dazwischen liegenden Geräte auflistet. Fügen Sie nun Tools ein, mit denen Sie die Leistung zwischen dem Client, dem Ausgangspunkt (wo Sie Ihr Netzwerk für das Internet verlassen) und der Office 365 Cloud testen können.
  
![Grundlegendes Netzwerk mit Client-, Proxy-und Cloud-und Tools-Vorschlägen PSPing, TraceTCP und Netzwerkablaufverfolgungen.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
Die Optionen werden aufgrund des Umfangs an Fachwissen, das Sie benötigen, um die Leistungsdaten zu finden, als **einfach** und **erweitert** aufgeführt. Eine Netzwerkablaufverfolgung dauert im Vergleich zur Ausführung von Befehlszeilentools wie PsPing und TraceTCP viel Zeit. Diese beiden Befehlszeilentools wurden ausgewählt, da Sie keine ICMP-Pakete verwenden, die von Office 365 blockiert werden, und weil Sie die Zeit in Millisekunden geben, die zum Verlassen des Clientcomputers oder des Proxyservers (sofern Sie Zugriff haben) benötigt werden und zu Office 365 gelangen. Jeder einzelne Hop von einem Computer auf einen anderen wird mit einem Zeitwert enden, und das ist für Baselines groß. Ebenso wichtig: mit diesen Befehlszeilentools können Sie dem Befehl eine Portnummer hinzufügen, dies ist hilfreich, da Office 365 über Port 443 kommuniziert, bei dem es sich um den von Secure Sockets Layer und Transport Layer Security (SSL und TLS) verwendeten Port handelt. Andere Drittanbietertools sind jedoch möglicherweise bessere Lösungen für Ihre Situation. Microsoft unterstützt diese Tools nicht, wenn Sie aus irgendeinem Grund PsPing und TraceTCP nicht mehr funktionsfähig machen können, fahren Sie mit einem Tool wie Netmon fort zu einer Netzwerkablaufverfolgung. 
  
Sie können einen Basisplan vor Geschäftszeiten, wieder bei starker Verwendung und dann wieder nach Stunden nutzen. Dies bedeutet, dass Sie am Ende möglicherweise eine Ordnerstruktur haben, die ein bisschen wie folgt aussieht:
  
![Grafik, die eine Möglichkeit zum Organisieren Ihrer Leistungsdaten in Ordnern vorschlägt.](../media/13e01ffa-f0f2-4d10-b89d-d5980ec89fae.png)
  
Sie sollten auch eine Benennungskonvention für Ihre Dateien auswählen. Im Folgenden finden Sie einige Beispiele:
  
- Feb_09_2015_9amPST_PerfBaseline_Netmon_ClientToEgress_Normal
    
- Jan_10_2015_3pmCST_PerfBaseline_PsPing_ClientToO365_bypassProxy_SLOW
    
- Feb_08_2015_2pmEST_PerfBaseline_BADPerf
    
- Feb_08_2015_8-30amEST_PerfBaseline_GoodPerf
    
Es gibt viele verschiedene Möglichkeiten, dies zu tun, aber die Verwendung des Formats **\<dateTime\>\<what's happening in the test\>** ist ein guter Ausgangspunkt. Das sorgfältige Vorgehen hilft viel, wenn Sie Probleme später beheben möchten. Später können Sie sagen: "Ich habe am 8. Februar zwei Spuren genommen, eine zeigte eine gute Leistung und eine zeigte sich schlecht, damit wir Sie vergleichen können". Dies ist äußerst hilfreich bei der Problembehandlung. 
  
Sie müssen eine organisierte Möglichkeit haben, ihre Verlaufs Basislinien beizubehalten. In diesem Beispiel wurden mit den einfachen Methoden drei Befehlszeilenausgaben erstellt, und die Ergebnisse wurden als Bildschirmfotos erfasst, aber möglicherweise haben Sie stattdessen Netzwerk-Capture-Dateien. Verwenden Sie die Methode, die für Sie am besten geeignet ist. Speichern Sie Ihre Verlaufs Basislinien, und wenden Sie sich an den Punkten, an denen Sie Änderungen am Verhalten von Onlinediensten bemerken. 
  
## <a name="why-collect-performance-data-during-a-pilot"></a>Gründe für das Erfassen von Leistungsdaten während eines Pilotprojekts

Es gibt keinen besseren Zeitpunkt, um Basispläne zu erstellen als bei einem Pilotprojekt des Office 365 Diensts. Ihr Büro verfügt möglicherweise über Tausende von Benutzern, Hunderttausende, oder es kann fünf sein, aber sogar mit einer kleinen Anzahl von Benutzern können Sie Tests durchführen, um Fluktuationen bei der Leistung zu messen. Im Fall eines großen Unternehmens kann eine repräsentative Stichprobe von mehreren hundert Benutzern, die Office 365 pilotieren, auf mehrere tausend nach außen projiziert werden, damit Sie wissen, wo Probleme auftreten können, bevor Sie auftreten.
  
Im Fall eines kleinen Unternehmens, bei dem ein on-Boarding bedeutet, dass alle Benutzer gleichzeitig an den Dienst wechseln und kein Pilotprojekt vorliegt, müssen Sie die Leistungs Maßnahmen so belassen, dass Sie Daten für alle Personen anzeigen können, die möglicherweise eine fehlerhafte Operation beheben müssen. Wenn Sie beispielsweise feststellen, dass Sie plötzlich in der Zeit, in der eine mittelgroße Grafik hochgeladen wurde, wo Sie sehr schnell verwendet wurde, um Ihr Gebäude herumlaufen können.
  
## <a name="how-to-collect-baselines"></a>Sammeln von Baselines

Für alle Pläne zur Problembehandlung müssen Sie diese Dinge mindestens identifizieren:
  
- Der verwendete Clientcomputer (der Typ des Computers oder Geräts, eine IP-Adresse und die Aktionen, die das Problem verursacht haben)
    
- Wo sich der Clientcomputer in der Welt befindet (beispielsweise ob dieser Benutzer in einem VPN mit dem Netzwerk, Remote arbeiten oder im Intranet des Unternehmens arbeitet)
    
- Der Ausgangspunkte, den der Clientcomputer in Ihrem Netzwerk verwendet (der Zeitpunkt, an dem der Datenverkehr für einen Internetdienstanbieter oder das Internet aus Ihrem Unternehmen Austritt)
    
 Sie können das Layout Ihres Netzwerks über den Netzwerkadministrator herausfinden. Wenn Sie sich in einem kleinen Netzwerk befinden, schauen Sie sich die Geräte an, die Sie mit dem Internet verbinden, und rufen Sie Ihren ISP an, wenn Sie Fragen zum Layout haben. Erstellen Sie eine Grafik des endgültigen Layouts für Ihren Verweis. 
  
In diesem Abschnitt werden einfache Befehlszeilentools und-Methoden sowie erweiterte Tools-Optionen unterteilt. Zunächst werden einfache Methoden behandelt. Wenn Sie jedoch im Moment ein Leistungsproblem haben, sollten Sie zu erweiterten Methoden wechseln und den Aktionsplan für die Leistungsproblembehandlung testen.
  
### <a name="simple-methods"></a>Einfache Methoden

Diese einfachen Methoden zielen darauf ab, einfache Leistungsbasislinien im Laufe der Zeit zu ergreifen, zu verstehen und ordnungsgemäß zu speichern, damit Sie über Office 365 Leistung informiert werden. Hier ist das sehr einfache Diagramm für einfache, wie Sie bereits gesehen haben:
  
![Grundlegendes Netzwerk mit Client-, Proxy-und Cloud-und Tools-Vorschlägen PSPing, TraceTCP und Netzwerkablaufverfolgungen.](../media/627bfb77-abf7-4ef1-bbe8-7f8cbe48e1d2.png)
  
> [!NOTE]
> TraceTCP ist in diesem Screenshot enthalten, da es ein nützliches Tool ist, um in Millisekunden anzuzeigen, wie lange eine Anforderung verarbeitet werden muss und wie viele Netzwerkhops oder Verbindungen von einem Computer zum nächsten, die die Anforderung zum Erreichen eines Ziels benötigt. TraceTCP kann auch die Namen der während des Hops verwendeten Server enthalten, was für eine Microsoft Office 365-Problembehandlung in Support hilfreich sein kann. > TraceTCP-Befehle können sehr einfach sein, beispielsweise: >  `tracetcp.exe outlook.office365.com:443`> denken Sie daran, die Portnummer in den Befehl einzuschließen! > [TraceTCP](https://simulatedsimian.github.io/tracetcp_download.html) ist ein kostenloser Download, stützt sich aber auf Wincap. Wincap ist ein Tool, das auch von Netmon verwendet und installiert wird. Wir verwenden auch NetMon im Abschnitt Advanced methods. 
  
 Wenn Sie mehrere Niederlassungen haben, müssen Sie auch eine Reihe von Daten von einem Client an jedem dieser Standorte beibehalten. Dieser Test misst die Wartezeit, bei der es sich in diesem Fall um einen Zahlenwert handelt, der die Zeitspanne zwischen einem Client, der eine Anforderung an Office 365 sendet, und Office 365, der auf die Anforderung antwortet, beschreibt. Der Test stammt aus Ihrer Domäne auf einem Clientcomputer und sucht nach einem Roundtrip aus dem Netzwerk, über einen Ausgangs-, über das Internet bis hin zu Office 365 und zurück. 
  
Es gibt einige Möglichkeiten, um mit dem Ausgangspunkte zu kämpfen, in diesem Fall dem Proxy Server. Sie können entweder zwischen 1 und 2 und dann auf 2 bis 3 zurückverfolgen und dann die Zahlen in Millisekunden hinzufügen, um eine endgültige Summe am Rand Ihres Netzwerks zu erhalten. Oder Sie können die Verbindung so konfigurieren, dass der Proxy für Office 365 Adressen umgangen wird. In einem größeren Netzwerk mit einer Firewall, einem Reverseproxy oder einer Kombination aus beiden müssen Sie möglicherweise Ausnahmen auf dem Proxy Server vornehmen, mit dem Datenverkehr für viele URLs übergeben werden kann. Eine Liste der von Office 365 verwendeten Endpunkte finden Sie unter [Office 365-URLs und IP-Adressbereiche](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2). Wenn Sie über einen authentifizierenden Proxy verfügen, testen Sie zunächst Ausnahmen für Folgendes:
  
- Ports 80 und 443
    
- TCP und HTTPS
    
- Verbindungen, die zu einer dieser URLs ausgehen:
    
- \*. microsoftonline.com
    
- \*. microsoftonline-p.com
    
- \*.sharepoint.com
    
- \*. Outlook.com
    
- \*. lync.com
    
- osub.microsoft.com
    
Alle Benutzer müssen diese Adressen ohne Proxy-Interferenz oder Authentifizierung abrufen können. In einem kleineren Netzwerk sollten Sie diese zu ihrer Proxyumgehungsliste im Webbrowser hinzufügen. 
  
Um diese zu ihrer Proxyumgehungsliste in Internet Explorer hinzuzufügen, wechseln Sie zu **Tools** \> **Internet Options** \> **Connections** \> **LAN Settings** \> **Advanced**. Auf der Registerkarte "Erweitert" finden Sie auch den Proxy Server und den Proxy Server Port. Möglicherweise müssen Sie auf das Kontrollkästchen **Proxy Server für LAN verwenden**klicken, um auf die Schaltfläche **erweitert** zuzugreifen. Sie sollten sicherstellen, dass die **Umgehung des Proxyservers für lokale Adressen** aktiviert ist. Wenn Sie auf **erweitert**klicken, wird ein Textfeld angezeigt, in dem Sie Ausnahmen eingeben können. Trennen Sie die oben aufgeführten Platzhalter-URLs mit Semikolons, beispielsweise:
  
\*. microsoftonline.com; \*. SharePoint.com
  
Nachdem Sie Ihren Proxy umgangen haben, sollten Sie in der Lage sein, Ping oder PsPing direkt für eine Office 365-URL zu verwenden. Der nächste Schritt besteht darin, ping- **Outlook.office365.com**zu testen. Oder wenn Sie PsPing oder ein anderes Tool verwenden, mit dem Sie eine Portnummer für den Befehl bereitstellen können, PsPing Sie gegen **Portal.microsoftonline.com:443** , um die durchschnittliche Roundtripzeit in Millisekunden anzuzeigen. 
  
Bei der Roundtripzeit (RTT) handelt es sich um einen Zahlenwert, der misst, wie lange es dauert, eine HTTP-Anforderung an einen Server wie Outlook.office365.com zu senden und eine Antwort zurückzugeben, die den Server erkennt, dass Sie es getan haben. Manchmal wird diese Abkürzung als RTT angezeigt. Dies sollte eine relativ kurze Zeitspanne sein.
  
Sie müssen [PSPing](https://technet.microsoft.com/sysinternals/jj729731.aspx) oder ein anderes Tool verwenden, das keine ICMP-Pakete verwendet, die von Office 365 blockiert werden, um diesen Test durchführen zu können. 
  
 **Vorgehensweise verwenden von PsPing, um eine allgemeine Roundtrip-Zeit in Millisekunden direkt aus einer Office 365-URL zu erhalten**
  
1. Führen Sie die folgenden Schritte aus, um eine Eingabeaufforderung mit erhöhten Rechten auszuführen:
    
1. Klicken Sie auf **Start**.
    
2. Geben Sie im Feld **Suche starten** den Befehl cmd ein, und drücken Sie dann STRG + UMSCHALT + EINGABETASTE.
    
3. Wenn das Dialogfeld **Benutzerkontensteuerung** eingeblendet wird, bestätigen Sie die angegebene Aktion und klicken dann auf **Weiter**.
    
2. Navigieren Sie zu dem Ordner, in dem das Tool (in diesem Fall PsPing) installiert ist, und testen Sie diese Office 365 URLs:
    
  - psping Portal.Office.com:443
    
  - psping Microsoft-My.SharePoint.com:443
    
  - psping Outlook.office365.com:443
    
  - psping www.Yammer.com:443
    
    ![Der PSPing-Befehl geht an Microsoft-My.SharePoint.com Port 443.](../media/3258f620-4513-4e82-95c9-06b387fc3a82.PNG)
  
Stellen Sie sicher, dass Sie die Portnummer 443 angeben. Denken Sie daran, dass Office 365 auf einem verschlüsselten Kanal funktioniert. Wenn Sie PsPing ohne die Portnummer haben, tritt bei Ihrer Anforderung ein Fehler auf. Nachdem Sie Ihre kurze Liste angepingt haben, suchen Sie nach der durchschnittlichen Zeit in Millisekunden (MS). Das möchten Sie aufzeichnen!
  
![Grafik, die eine Abbildung des Clients zum Proxy PSPing mit einer Roundtrip-Zeit von 2,8 Millisekunden zeigt.](../media/96901aea-1093-4f1b-b5a3-6078e9035e6c.png)
  
Wenn Sie mit der Proxyumgehung nicht vertraut sind und die Schritte lieber Schritt für Schritt durchführen möchten, müssen Sie zuerst den Namen Ihres Proxyservers herausfinden. In Internet Explorer wechseln Sie zu **Tools** \> **Internet Options** \> **Connections** \> **LAN Settings** \> **Advanced**. Auf der Registerkarte **erweitert** wird der Proxy Server aufgelistet angezeigt. Pingen Sie diesen Proxy Server an einer Eingabeaufforderung aus, indem Sie diese Aufgabe ausführen: 
  
 **So Pingen Sie den Proxy Server an und erhalten einen Roundtrip-Wert in Millisekunden für Phase 1 bis 2**
  
1. Führen Sie die folgenden Schritte aus, um eine Eingabeaufforderung mit erhöhten Rechten auszuführen:
    
1. Klicken Sie auf **Start**.
    
2. Geben Sie im Feld **Suche starten** den Befehl cmd ein, und drücken Sie dann STRG + UMSCHALT + EINGABETASTE.
    
3. Wenn das Dialogfeld **Benutzerkontensteuerung** eingeblendet wird, bestätigen Sie die angegebene Aktion und klicken dann auf **Weiter**.
    
2. Geben Sie ping \<the name of the proxy server your browser uses, or the IP address of the proxy server\> ein, und drücken Sie die EINGABETASTE. Wenn Sie PsPing oder ein anderes Tool installiert haben, können Sie stattdessen auswählen, dieses Tool zu verwenden. 
    
    Ihr Befehl kann wie jedes der folgenden Beispiele aussehen: 
    
  - Ping-ourproxy.ourdomain.Industry.Business.com
    
  - Ping-155.55.121.55
    
  - Ping-ourproxy
    
  - psping ourproxy.ourdomain.Industry.Business.com:80
    
  - psping 155.55.121.55:80
    
  - psping ourproxy: 80
    
3. Wenn die Ablaufverfolgung das Senden von Testpaketen beendet, erhalten Sie eine kleine Zusammenfassung, die einen durchschnittlichen Wert in Millisekunden auflistet, und der ist der Wert, nach dem Sie sich befinden. Erstellen Sie einen Screenshot der Eingabeaufforderung, und speichern Sie ihn mit Ihrer Benennungskonvention. An dieser Position kann es auch hilfreich sein, das Diagramm mit dem Wert auszufüllen.
    
Vielleichthaben Sie eine Spur in den frühen Morgenstunden, und Ihr Client kann an den Proxy (oder was auch immer Ausstieg-Server mit dem Internet) schnell zu erhalten. In diesem Fall können Ihre Nummern wie folgt aussehen:
  
![Grafik, die die Roundtripzeit zwischen einem Client und einem Proxy von 2,8 Millisekunden anzeigt.](../media/1bd03544-23fc-47d4-bbae-c1feb466a5d8.PNG)
  
Wenn der Clientcomputer einer der wenigen mit Zugriff auf den Proxy Server (oder den Ausgang) ist, können Sie den nächsten Testabschnitt ausführen, indem Sie eine Remoteverbindung mit diesem Computer herstellen, indem Sie die Eingabeaufforderung ausführen, um von dort aus eine Office 365-URL PsPing. Wenn Sie keinen Zugriff auf diesen Computer haben, können Sie sich an Ihre Netzwerkressourcen wenden, um Hilfe zum nächsten Bein zu erhalten und so genaue Zahlen zu erhalten. Wenn dies nicht möglich ist, nehmen Sie ein PsPing gegen die fragliche Office 365 URL, und vergleichen Sie Sie mit der PsPing-oder Ping-Zeit mit Ihrem Proxy Server. 
  
Wenn Sie beispielsweise 51,84 Millisekunden vom Client an die Office 365-URL haben und 2,8 Millisekunden vom Client zum Proxy (oder Ausgangsstelle) haben, haben Sie 49,04 Millisekunden vom Ausgang bis Office 365. Wenn Sie eine PsPing von 12,25 Millisekunden zwischen dem Client und dem Proxy während der Tages Höhe und 62,01 Millisekunden vom Client in die Office 365-URL haben, beträgt der durchschnittliche Wert für den Proxy Ausstieg an die Office 365-URL 49,76 Millisekunden.
  
![Zusätzliche Grafik, die den Ping in Millisekunden zwischen Client und Proxy neben dem Client Office 365 zeigt, sodass die Werte subtrahiert werden können.](../media/cd764e77-5154-44ba-a5cd-443a628eb2d9.PNG)
  
Im Hinblick auf die Problembehandlung finden Sie möglicherweise etwas interessantes, wenn Sie diese Basislinien beibehalten. Wenn Sie beispielsweise feststellen, dass Sie im allgemeinen etwa 40 bis 59 Millisekunden Wartezeit vom Proxy oder Ausgangspunkte auf die Office 365-URL haben, und haben einen Client zu Proxy-oder Ausgangspunkte Wartezeit von etwa 3 bis 7 Millisekunden (abhängig von der Menge Netzwerkdatenverkehr, den Sie während dieser Tageszeit sehen), dann werden Sie sicherlich wissen, dass etwas problematisch ist, wenn die letzten drei Client-Proxy-oder Ausgangsbasis Linien eine Wartezeit von 45 Millisekunden aufweisen.
  
### <a name="advanced-methods"></a>Erweiterte Methoden

Wenn Sie wirklich wissen möchten, was mit Ihren Internet Anforderungen an Office 365 passiert, müssen Sie sich mit Netzwerkablaufverfolgungen vertraut machen. Es spielt keine Rolle, welche Tools Sie für diese Ablaufverfolgungen, HTTPWatch, netmon, Message Analyzer, Wireshark, Fiddler, Developer Dashboard Tool oder andere tun möchten, solange dieses Tool den Netzwerkdatenverkehr erfassen und Filtern kann. In diesem Abschnitt sehen Sie, dass es vorteilhaft ist, mehr als eines dieser Tools auszuführen, um ein vollständigeres Bild des Problems zu erhalten. Wenn Sie testen, fungieren einige dieser Tools auch als Proxies in Ihrem eigenen Recht. Zu den im Begleitartikel, dem [Plan zur Leistungsproblembehandlung für Office 365](performance-troubleshooting-plan.md), verwendeten Tools gehören [Netmon 3,4](https://www.microsoft.com/download/details.aspx?id=4865), [HTTPWatch](https://www.httpwatch.com/download/)oder [wireshark](https://www.wireshark.org/).
  
Das Erstellen einer Leistungsbasislinie ist der einfache Teil dieser Methode, und viele der Schritte sind identisch mit der Behandlung eines Leistungsproblems. Die fortgeschritteneren Methoden zum Erstellen von Basislinien für die Leistung erfordern das übernehmen und Speichern von Netzwerkablaufverfolgungen. In den meisten Beispielen in diesem Artikel wird SharePoint Online verwendet, Sie sollten jedoch eine Liste allgemeiner Aktionen für die Office 365 Dienste entwickeln, für die Sie den Test und die Aufzeichnung abonnieren. Es folgt ein grundlegendes Beispiel:
  
- Baselineliste für SpO-* * Schritt 1: * * Durchsuchen Sie die Homepage der SPO-Website, und führen Sie eine Netzwerkablaufverfolgung aus. Speichern Sie die Ablaufverfolgung. 
    
- Baselineliste für SpO- **Schritt 2:** suchen Sie nach einem Begriff (wie Ihrem Firmennamen) über die Unternehmenssuche, und führen Sie eine Netzwerkablaufverfolgung aus. Speichern Sie die Ablaufverfolgung. 
    
- Baselineliste für SpO- **Schritt 3:** Hochladen einer großen Datei in eine SharePoint Online Dokumentbibliothek und Ausführen einer Netzwerkablaufverfolgung. Speichern Sie die Ablaufverfolgung. 
    
- Baselineliste für SpO- **Step 4:** Durchsuchen der Startseite der OneDrive-Website und Ausführen einer Netzwerkablaufverfolgung. Speichern Sie die Ablaufverfolgung. 
    
Diese Liste sollte die wichtigsten allgemeinen Aktionen enthalten, die Benutzer gegen SharePoint Online durchführen. Beachten Sie, dass der letzte Schritt zur Ablaufverfolgung OneDrive für Unternehmen einen Vergleich zwischen der Last der SharePoint Online Homepage (die häufig von Unternehmen angepasst wird) und OneDrive für Unternehmen Startseite darstellt, die selten angepasst wird. Dies ist ein sehr grundlegender Test, wenn es um eine langsame laden SharePoint Online Website geht. Sie können einen Datensatz dieser Differenz in Ihren Tests erstellen.
  
Wenn Sie sich mitten in einem Leistungsproblem befinden, sind viele der Schritte identisch mit dem Erstellen eines Basisplans. Netzwerkablaufverfolgungen werden kritisch, daher behandeln wir,  *wie*  Sie die wichtigsten Ablaufverfolgungen weiterleiten. 
  
Um ein Leistungsproblem zu beheben, müssen Sie  *gerade jetzt*  eine Ablaufverfolgung ausführen, wenn das Leistungsproblem auftritt. Sie müssen über die erforderlichen Tools zum Sammeln von Protokollen verfügen, und Sie benötigen einen Aktionsplan, also eine Liste der Problem Behandlungs Aktionen, die Sie ausführen müssen, um die besten Informationen zu sammeln, die Ihnen zur Verfügung stehen. Als erstes müssen Sie das Datum und die Uhrzeit des Tests aufzeichnen, damit die Dateien in einem Ordner gespeichert werden können, der das Timing widerspiegelt. Als nächstes beschränken Sie die Problemschritte selbst. Dies sind die genauen Schritte, die Sie für die Tests verwenden werden. Vergessen Sie nicht die Grundlagen: Wenn das Problem nur mit Outlook besteht, stellen Sie sicher, dass das Problemverhalten nur in einem Office 365 Dienst auftritt. Das Einschränken des Umfangs dieses Problems hilft Ihnen, sich auf etwas zu konzentrieren, das Sie lösen können. 
  
## <a name="see-also"></a>Siehe auch

[Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

