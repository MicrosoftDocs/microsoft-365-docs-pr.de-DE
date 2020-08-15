---
title: Bewährte Methoden für die Verwendung von Office 365 in einem langsamen Netzwerk
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/29/2016
audience: End User
ms.topic: overview
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
search.appverid:
- MET150
- MET150
- MOP150
- MEW150
- BCS160
ms.assetid: fd16c8d2-4799-4c39-8fd7-045f06640166
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
description: Dieser Artikel führt Sie durch die bewährten Methoden, die Sie für die Verwendung von Office 365 in einem langsamen Netzwerk übernehmen können.
ms.openlocfilehash: a0a15191fa0240f24cecc5e595de9a259cacc9f9
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690696"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Bewährte Methoden für die Verwendung von Office 365 in einem langsamen Netzwerk

Wäre es nicht schön, wenn Ihre Internet Verbindung immer schnell und nie nach unten war? Vielleicht wird dieser Tag kommen. Aber in der Zwischenzeit gibt es praktische Dinge, die Sie tun können, um ein unruhiges Netzwerk zu umgehen und immer noch Ihre tägliche Arbeit erledigen zu lassen. Obwohl Office 365 ein Cloud-basierter Dienst ist, bietet es auch viele Möglichkeiten, um Ihre Inhalte offline zu bearbeiten und Ihre Änderungen reibungslos synchron zu halten. Außerdem ist es manchmal effizienter, offline mit Inhalten zu arbeiten, nur weil Anwendungen schneller ausgeführt werden und die Benutzeroberfläche besser reagiert. Der Sinn ist: Office 365 gibt Ihnen das Beste aus beiden Welten. Hier erfahren Sie, wie Sie dies nutzen können. 
  
> [!TIP]
> Möchten Sie sehen, wie langsam (oder schnell) Ihre Netzwerkverbindung ist? Testen Sie den [ OOKLA-Geschwindigkeitstest ](https://www.speedtest.net/) oder die [Netzwerk Geschwindigkeitstest-App](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70). 

## <a name="why-is-my-network-so-slow"></a>Warum ist mein Netzwerk so langsam?

Sie haben zwar keine Kontrolle über die Netzwerkleistung selbst, aber Sie können verstehen, was hinter den Kulissen vor sich geht. Das Internet ist enorm komplex, aber es gibt ein paar Konzepte, die Ihnen helfen, die Situation besser zu verstehen. Wenn Sie die bewährten Methoden in diesem Artikel befolgen, können Sie Leistungsprobleme umgehen und Frustration reduzieren.
  
**Wichtige Faktoren, die sich auf die Netzwerkleistung auswirken**

![Netzwerk Leistungsfaktoren](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)
  
 **Bandbreite und Wartezeit** Die beiden wichtigsten Maßnahmen zur Netzwerkleistung sind Bandbreite und Wartezeit: 
  
- Bandbreite ist die Rate des Durchsatzes, die in Bits pro Sekunde gemessen wird. Größer ist besser. Bandbreite ist wie eine Wasserpfeife. Je größer die Pipe ist, desto mehr Wasser kann Sie durchsetzen.

- Wartezeit ist die Zeit, die es dauert, bis Inhalte von einem Server oder Dienst auf Ihr Gerät übermittelt werden und in Millisekunden gemessen werden. Schneller ist besser. Die Wartezeit kann durch eine Reihe von Faktoren verursacht werden, darunter eine geringe Bandbreite, eine spärliche Verbindung oder eine Übertragungszeit.

 **Häufige Probleme** Neben Bandbreite und Wartezeit haben andere Probleme Auswirkungen auf die Netzwerkleistung und sind oft unvorhersehbar. Die Netzwerkleistung kann je nach Tageszeit oder physischem Standort schwanken. Das Netzwerk kann verstopft werden, wenn bestimmte Ereignisse eintreten, die die Nutzung des Internets anstacheln, beispielsweise eine Naturkatastrophe oder ein wichtiges öffentliches Ereignis. Die Größe und Komplexität der geladenen Seite sowie die Anzahl und Größe der übertragenen Dateien haben einen direkten Einfluss auf die Leistung. Eine WiFi-Verbindung kann sich vorübergehend vermindern: zum Beispiel rufen Sie eine große Konferenz Besprechung mit Tausenden ab, indem Sie alle gleichzeitig um Tweet bitten. 
  
 **Überlegungen zu einem Satellitennetzwerk** Ein Satellitennetzwerk ist nützlich, wenn ein terrestrisches Netzwerk nicht möglich ist, wie beispielsweise das Backcountry, ein Kreuzfahrtschiff oder ein Remote-Wissenschaftsbereich. Diese Netzwerke basieren auf Satelliten, die in einer geosynchronen Umlaufbahn 22.000 Meilen über dem Äquator positioniert sind. Allerdings reist eine Übertragung tatsächlich etwa 90.000 Meilen, sodass ein Satellitennetzwerk eine langsamere Wartezeit (500 ms oder mehr) als ein terrestrisches Netzwerk (20 bis 50ms) hat. Unter den besten Bedingungen bemerken Sie diese Wartezeit möglicherweise nicht, aber für das Herunterladen großer Dateien, Streaming-Videos und das Abspielen von spielen werden Sie wahrscheinlich. Ein weiteres Problem ist "Rain Fade", bei dem bei starkem Wetter wie Gewittern und Schneestürmen die Satellitenübertragung vorübergehend unterbrochen werden kann.
  
## <a name="are-you-sure-its-the-network"></a>Sind Sie sicher, dass es sich um das Netzwerk handelt?

Stellen Sie bei Auftreten von Leistungsproblemen zunächst sicher, dass Ihr Gerät nicht die Ursache des Problems ist. Es gibt zwei Dinge, die Sie tun können, was eine große Verbesserung sein könnte:
  
- Stellen Sie sicher, dass Ihr Gerät ordnungsgemäß funktioniert und keine Schadsoftware auf Ihrem Computer vorhanden ist.

- Kaufen Sie nach Möglichkeit mehr Arbeitsspeicher. Das Hinzufügen von Arbeitsspeicher ist die einfachste und meist effektivste Möglichkeit, die Leistung auf Ihrem Gerät zu verbessern. Besonders hilfreich bei der Arbeit mit großen Dateien und Videos.

Weitere Informationen finden Sie unter [ Windows-Leistung und-Wartung ](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) sowie [Tipps zum Verbessern der Leistung von PCs in Windows 10](https://support.microsoft.com/en-za/help/4002019/windows-10-improve-pc-performance).

## <a name="best-practices-for-using-your-browser"></a>Bewährte Methoden für die Verwendung des Browsers

Ihr Browser ist Ihr Gateway zu Office 365, sodass es sich auf die Leistung auswirken kann, vor allem mit der Zeit, die zum Laden einer Seite erforderlich ist, und wie oft Sie Roundtrips zum Office 365 Dienst ausführen.
  
 **Browser allgemein**
  
Hier sind einige Vorschläge für Browser im allgemeinen:
  
- Deaktivieren Sie Browser-Add-ons, die sich möglicherweise auf die Leistung auswirken oder die Sie nicht wirklich benötigen.

- Verbessern Sie die Cachegröße für Ihre temporären Internetdateien.

- Wenn Sie sich bei Ihrem geschäftlichen oder Schulkonto angemeldet haben, lassen Sie das Browserfenster den ganzen Tag geöffnet. Sie können andere Registerkarten und Fenster öffnen, ohne sich erneut anzumelden. Wenn Sie sich bei einem anderen Konto anmelden müssen, verwenden Sie das private Browsen. 

- Nachdem jede Seite heruntergeladen und geöffnet wurde, sollten Sie Sie mithilfe von Registerkarten öffnen. Es ist ganz einfach, zwischen Registerkarten zu navigieren und die Seite später am Tag zu verwenden. Aktualisieren Sie eine Seite nur, wenn Sie auf dieser Seite die neuesten Daten benötigen.

- Wenn das Öffnen einer Seite zu lange dauert, beenden Sie den Seiten Download (drücken Sie die ESC-Taste), und aktualisieren Sie die Seite (drücken Sie F5). 

-  Reduzieren Sie nach Möglichkeit Roundtrips auf Office 365. Verwenden Sie beispielsweise die Suche, um nach Dateien in einer großen Bibliothek zu suchen und in einer Liste zu filtern, um direkt zu den gewünschten Ergebnissen zu gelangen, anstatt überlisten oder Bibliotheken zu blättern. Sie können auch Ansichten erstellen, mit denen die Ladezeit der Seite minimiert wird. Weitere Informationen finden Sie unter [Verwalten umfangreicher Listen und Bibliotheken in Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES).

- Wenn die Videoleistung schlecht ist, können Sie das Video möglicherweise herunterladen und auf Ihrem Gerät ansehen. Möglicherweise ist ein Download Link verfügbar, oder Sie können mit der rechten Maustaste auf den Link Video klicken und **Ziel speichern**unter auswählen.

 **Browser spezifisch**
  
Hier sind einige Vorschläge für Ihren speziellen Browser:
  
- **Internet Explorer** Führen Sie ein Upgrade auf Internet Explorer Version 11 oder höher durch, um deutliche Leistungsverbesserungen gegenüber früheren Versionen zu erzielen. Weitere Informationen finden Sie unter [Troubleshooting Guide for Internet Explorer](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365).

- **Firefox** Weitere Informationen finden Sie unter [Firefox ist langsam oder funktioniert nicht](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging)mehr.

- **Safari** Weitere Informationen finden Sie unter [Apple-Safari](https://www.apple.com/safari/).

- **Chrome** Weitere Informationen finden Sie unter [Chrome-Hilfe](https://support.google.com/chrome/?hl=en).
  
## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Bewährte Methoden für die Verwendung von Outlook und Outlook Web App

Das Lesen, schreiben und organisieren von e-Mails ist ein wichtiger Bestandteil des jeden Tages. Sowohl Outlook als auch Outlook Web App (OWA) bieten Offlineunterstützung. Die Verwendung einer e-Mail-App auf Ihrem Smartphone ist eine weitere nützliche Alternative. Verwenden Sie die folgenden Optionen, die Ihren Anforderungen am besten entsprechen:
  
- Führen Sie ein Upgrade auf die neueste Version von Outlook durch, um deutliche Leistungsverbesserungen gegenüber früheren Versionen zu erzielen. 

-  In Outlook Web App können Sie Offline Nachrichten, Kontakte und Kalenderereignisse erstellen, die hochgeladen werden, wenn OWA als nächstes eine Verbindung mit Office 365 herstellen kann. Weitere Informationen zum Einrichten und Verwenden von OWA im Offlinemodus finden Sie unter [using Outlook Web App Offline](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36).

- In Outlook können Sie im Cachemodus arbeiten, in dem Sie automatisch eine Verbindung herstellt, wenn möglich. Sie können Outlook das gesamte Postfach oder nur einen Teil davon herunterladen. Weitere Informationen finden Sie unter [Aktivieren des Exchange-Cache-Modus](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) und [Arbeiten offline in Outlook](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

- Outlook bietet auch einen Offlinemodus. Um dies zu verwenden, müssen Sie zuerst den Cache-Modus einrichten, damit Informationen aus Ihrem Konto auf Ihren Computer kopiert werden. Im Offlinemodus versucht Outlook, eine Verbindung über die Sende-und Empfangseinstellungen herzustellen oder wenn Sie es manuell für Online Arbeiten festgelegt haben. Weitere Informationen finden Sie unter [Offline arbeiten, um datenverbindungsgebühren zu vermeiden](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282), [Sende-und Empfangseinstellungen zu ändern, wenn Sie offline arbeiten](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a), und [von Offline arbeiten in Online zu wechseln](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9).

- Wenn Sie über ein Smartphone verfügen, können Sie es verwenden, um Ihre e-Mails und Kalender über das Netzwerk Ihres Mobilfunkanbieters zu selektieren.

> [!NOTE]
> Hier finden Sie einige Anleitungen zur Verwendung von Outlook oder OWA. Wenn auf Ihrem Gerät kein Speicherplatz vorhanden ist, verfügt Outlook über einen vollständigen Funktionsumfang und kann für Sie am besten geeignet sein. Wenn es sich bei dem Speicherplatz um ein Problem auf Ihrem Gerät handelt, sollten Sie OWA verwenden, das über eine Teilmenge von Funktionen verfügt, aber auch in Online Situationen am besten funktioniert. Selbstverständlich können Sie auch verwenden, weil Sie gut zusammenarbeiten.
  
## <a name="best-practices-for-using-onedrive-for-business"></a>Bewährte Methoden für die Verwendung von OneDrive für Unternehmen

OneDrive für Unternehmen wurde von Grund auf für die Online-und Offlinearbeit mit Ihren Dateien entwickelt. Nachdem Sie es eingerichtet haben, erfolgt die Synchronisierung von Änderungen automatisch und zuverlässig, wo und wann immer Sie Sie vornehmen. Wenn das Netzwerk langsam ist, können Sie mit der Offline Version der Dateien arbeiten.
  
Die OneDrive für Unternehmen Sync-app enthält ein SharePoint Online-und Office 365-Geschäfts Abonnement, oder Sie können die OneDrive für Unternehmen Sync-App kostenlos [herunterladen](https://support.microsoft.com/kb/2903984) . Diese APP ist auch schneller als die Verwendung der Befehle **Öffnen in Explorer** oder **hochladen** . Weitere Informationen finden Sie unter [Einrichten des Computers zum Synchronisieren Ihrer OneDrive für Unternehmen Dateien in Office 365](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16).
  
Hier finden Sie einige zusätzliche Anleitungen für die Verwendung der OneDrive für Unternehmen Sync-App:
  
- Wenn Sie eine große Bibliothek zum ersten Mal synchronisieren, starten Sie die Synchronisierung außerhalb der Arbeitszeiten, beispielsweise über Nacht.

- Sie können die Synchronisierung [einer Bibliothek mit dem OneDrive für Unternehmen-App](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) -Feature beenden, um das Synchronisieren von Updates vorübergehend zu beenden. Verwenden Sie dieses Feature jedoch nur für kurze Zeiträume, beispielsweise für einige Stunden, um Warteschlangen für eine große Anzahl von Updates zu vermeiden und um das Risiko von Zusammenführungskonflikten zu minimieren, wenn mehrere Personen an demselben Dokument arbeiten.
  
## <a name="best-practices-for-using-onenote"></a>Bewährte Methoden für die Verwendung von OneNote

Jede SharePoint-Teamwebsite verfügt über ein integriertes OneNote-Notizbuch, das Sie ganz einfach erstellen können. OneNote ist eine großartige Möglichkeit zum Erfassen rechtzeitiger Informationen, die Sie täglich benötigen, um Aufgaben zu erledigen. Beispielsweise verwenden viele Teams OneNote als Sammel Pfad für wöchentliche Besprechungen, Projektnotizen, Ideen, Pläne und Statusberichte. Sie können diese unterschiedlichen Informationen ordentlich organisieren, indem Sie Seiten, Abschnitte und Registerkarten verwenden.
  
Die Schönheit von OneNote besteht darin, dass Sie auf die Inhalte von nahezu jedem Gerät aus zugreifen können, unabhängig davon, ob es sich um einen Desktop, einen Laptop, ein Tablet oder ein Smart Phone handelt. Außerdem müssen Sie sich keine Gedanken über das Speichern oder die Synchronisierung machen, da OneNote dies für Sie erledigt.
  
Weitere Informationen finden Sie unter [Microsoft OneNote](https://office.microsoft.com/onenote).

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Bewährte Methoden für die Verwendung von Skype for Business und lync Online

Im folgenden finden Sie allgemeine Richtlinien für die Verwendung von Skype for Business oder lync Online, wenn Ihr Netzwerk langsam ist:

- Verwenden Sie Sofortnachrichten, wenn möglich, da es in einem langsamen Netzwerk gut funktioniert.

- Vermeiden Sie, dass Telefonanrufe über VPN-Verbindungen (Virtual Private Network) oder RAS-Verbindungen (Remote Access Service) getätigt werden.

- Stellen Sie sicher, dass Ihr Audiogerät genehmigt wurde. Weitere Informationen finden Sie unter [Telefone und Geräte, die für Microsoft lync qualifiziert](https://docs.microsoft.com/skypeforbusiness/lync-cert/ip-phones)sind.

- Wenn Sie PowerPoint in einer Online Präsentation verwenden, reduzieren Sie die Größe und Komplexität der Folien. Weitere Informationen finden Sie unter [Tipps zum Verbessern der Leistung Ihrer Präsentation](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949).

- Die Video Leistung hängt stark von der Netzwerkleistung ab. Vermeiden Sie die Verwendung von Video, wenn Ihr Netzwerk langsam ist.

Weitere Informationen finden Sie unter [schlechte Audio-oder Videoqualität in lync Online](https://support.microsoft.com/kb/2386655)oder [Problembehandlung von Verbindungsproblemen in Skype for Business](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771).
  
## <a name="best-practices-for-using-sharepoint-lists"></a>Bewährte Methoden für die Verwendung von SharePoint-Listen

Das Offline arbeiten mit Listendaten zum "Scrubben", analysieren oder melden von Daten ist eine großartige Möglichkeit, um die Auswirkungen eines langsamen Netzwerks zu minimieren. Sie können die meisten Listen in Microsoft Access 2019 und Microsoft Access 2016 lesen und schreiben, indem Sie darauf verweisen. Sie können auch eine Liste in eine Excel-Tabelle exportieren, die eine unidirektionale Datenverbindung zwischen der Excel-Tabelle und der Liste erstellt. Hier erfahren Sie, wie Sie [Offline mit Tabellen arbeiten, die mit SharePoint-Listen verknüpft sind](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e).
  
Weitere Informationen finden Sie im Abschnitt "Weitere Informationen zum Verwalten umfangreicher Listen" in [Verwalten von umfangreichen Listen und Bibliotheken in Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784).
  
## <a name="best-practices-for-customizing-web-pages"></a>Bewährte Methoden für das Anpassen von Webseiten

Wenn Sie eine Webseite anpassen, verursachen Sie möglicherweise versehentlich eine schlechte Leistung für die Seite. Eine Reihe von Faktoren kann Auswirkungen haben, beispielsweise die Komplexität und Größe der Seite, wie viele Webparts hinzugefügt werden, wie viele Listen oder Bibliothekselemente anfänglich angezeigt werden und wie Sie die Seite codieren.
  
Weitere Informationen finden Sie unter [Tune SharePoint Online Performance](tune-sharepoint-online-performance.md).
  
## <a name="best-practices-for-using-project-online"></a>Bewährte Methoden für die Verwendung von Project Online

Die folgenden Richtlinien können zur Verbesserung der Netzwerkleistung beitragen.
  
- Project Online und SharePoint Online erfordern eine Synchronisierung, was zeitaufwändig sein kann. Wenn Ihre Projektteams einen niedrigen Umsatz haben, deaktivieren Sie die Projektstandort Synchronisierung, um die Leistung der Projektveröffentlichung und der Projekt Detail Seiten zu verbessern. Beschränken Sie Active Directory Synchronisierung mit Ressourcengruppen, die das System tatsächlich verwenden müssen, und überwachen Sie mögliche Berechtigungsprobleme nach der Synchronisierung großer Gruppen.

- Wenn Ihre Organisation Projektwebsites verwendet, erstellen Sie diese bei Bedarf anstatt automatisch. Dies beschleunigt die erste Veröffentlichungsumgebung und verhindert das Erstellen unnötiger Websites und Inhalte.

- Projekt Detail Seiten (PDP) können eine Neuberechnung des gesamten Projekts auslösen und Workflowaktionen starten, die beide leistungsintensiv sein können. Um zu vermeiden, dass zwei Aktualisierungsprozesse gleichzeitig auf derselben PDP ausgelöst werden, sollten Sie die Kalender Felder nicht aktualisieren (Start Datum, Endtermin, Status Datum und Aktuelles Datum) und nicht geplante Felder (Projektname, Beschreibung und Besitzer).

- Verringern Sie die Anzahl von Webparts und benutzerdefinierten Feldern, die auf den einzelnen PDP-Elementen angezeigt werden. Erstellen Sie eine dedizierte PDP mit den einzigen Feldern, die aktualisiert werden müssen, um die Last zu verbessern und Zeit zu sparen.

- Wenn Sie OData für die Berichterstellung verwenden, begrenzen Sie die Datenmenge, die Sie zur Laufzeit Abfragen, mithilfe der serverseitigen Filterung.

Weitere Informationen finden Sie unter [Tune Project Online Performance](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c).
  
## <a name="whats-the-best-way-to-report-problems"></a>Was ist die beste Möglichkeit zum Melden von Problemen?

Microsoft verbessert die Gesamtleistung von Office 365 kontinuierlich, indem es das Netzwerk überwacht, Bandbreite und Wartezeit misst, die Ladezeit verbessert, die Datenträger-e/a reduziert, die Seiten neu gestaltet, um eine minimale Download Strategie zu verwenden, Hardware zu Rechenzentren hinzufügt und weitere Rechenzentren hinzufügt. Weitere Informationen zum Überprüfen des aktuellen Status und zu Berichtsproblemen finden Sie unter [How to Check Office 365 Service Health](view-service-health.md).
  
## <a name="see-also"></a>Siehe auch

[Netzwerkplanung und Leistungsoptimierung für Office 365](network-planning-and-performance.md)
  
[Prinzipien von Office 365-Netzwerkverbindungen](microsoft-365-network-connectivity-principles.md)
  
[Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Häufig gestellte Fragen zu Office 365-Endpunkten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
 
