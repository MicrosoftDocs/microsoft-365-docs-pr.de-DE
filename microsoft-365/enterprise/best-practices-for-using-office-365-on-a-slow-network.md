---
title: Bewährte Methoden für die Verwendung Office 365 in einem langsamen Netzwerk
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
description: Dieser Artikel führt Sie durch die bewährten Methoden, die Sie für die Verwendung von Office 365 in einem langsamen Netzwerk verwenden können.
ms.openlocfilehash: effa1038b03a9fcafc74166a1f53682186688906
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905260"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Bewährte Methoden für die Verwendung Office 365 in einem langsamen Netzwerk

Wäre es nicht schön, wenn Ihre Internetverbindung immer schnell und niemals heruntergefahren wäre? Vielleicht wird dieser Tag kommen. In der Zwischenzeit gibt es jedoch praktische Dinge, die Sie tun können, um ein wackliges Netzwerk zu umarbeiten und ihre täglichen Arbeiten trotzdem zu erledigen. Obwohl Office 365 ein cloudbasierter Dienst ist, bietet er auch viele Möglichkeiten, mit Ihren Inhalten offline zu arbeiten und Ihre Änderungen reibungslos zu synchronisieren. Außerdem ist es manchmal effizienter, offline mit Inhalten zu arbeiten, nur weil Anwendungen schneller ausgeführt werden und die Benutzeroberfläche reaktionsfähiger ist. Der Punkt ist: Office 365 bietet Ihnen das Beste aus beiden Welten. Hier erfahren Sie, wie Sie dies nutzen können. 
  
> [!TIP]
> Möchten Sie sehen, wie langsam (oder schnell) Ihre Netzwerkverbindung ist? Testen Sie [den OOKLA-Geschwindigkeitstest oder](https://www.speedtest.net/) die [Netzwerkgeschwindigkeitstest-App.](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70) 

## <a name="why-is-my-network-so-slow"></a>Warum ist mein Netzwerk so langsam?

Obwohl Sie die Netzwerkleistung selbst nicht steuern können, hilft es, zu verstehen, was hinter den Kulissen vor sich geht. Das Internet ist sehr komplex, aber es gibt einige Konzepte, die Ihnen dabei helfen können, die Situation viel besser zu verstehen. Wenn Sie die bewährten Methoden in diesem Artikel verwenden, können Sie Leistungsprobleme umgehen und Frustration reduzieren.
  
**Wichtige Faktoren, die sich auf die Netzwerkleistung auswirken**

![Netzwerkleistungsfaktoren](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)
  
 **Bandbreite und Latenz** Die beiden wichtigsten Maße für die Netzwerkleistung sind Bandbreite und Latenz: 
  
- Bandbreite ist die Durchsatzrate, die in Bits pro Sekunde gemessen wird. Größer ist besser. Bandbreite gleicht einer Wasserleitung. Je größer die Leitung ist, desto mehr Wasser können Sie "durch".

- Latenz ist die Zeit, die es dauert, bis Inhalte von einem Server oder Dienst auf Ihr Gerät übertragen werden und in Millisekunden gemessen werden. Schneller ist besser. Latenz kann durch eine Reihe von Faktoren verursacht werden, z. B. geringe Bandbreite, eine geringe Verbindung oder Übertragungszeit.

 **Häufige Probleme** Neben Bandbreite und Latenz haben andere Probleme Auswirkungen auf die Netzwerkleistung und sind häufig unvorhersehbar. Die Netzwerkleistung kann je nach Tageszeit oder physischem Standort schwanken. Das Netzwerk kann verstopft werden, wenn bestimmte Ereignisse auftreten, die die Nutzung des Internets in die Spitze setzen, z. B. eine Naturkatastrophe oder ein großes öffentliches Ereignis. Die Größe und Komplexität der geladenen Seite sowie Anzahl und Größe der übertragenen Dateien haben direkte Auswirkungen auf die Leistung. Eine WLAN-Verbindung kann vorübergehend beeinträchtigt werden: Sie können z. B. eine große Konferenz mit Tausenden von Besprechungen abfragen, indem Sie alle bitten, gleichzeitig zu twittern. 
  
 **Überlegungen für ein Satellitennetzwerk** Ein Satellitennetzwerk ist nützlich, wenn ein landgestütztes Netzwerk nicht möglich ist, z. B. das Rückland, ein Kreuzfahrtschiff oder ein wissenschaftlicher Remotebereich. Diese Netzwerke sind auf Satelliten angewiesen, die in einer geosynchronen Umlaufbahn 22.000 Meilen über dem Äquator positioniert sind. Eine Übertragung geht jedoch tatsächlich etwa 90.000 Meilen, sodass ein Satellitennetzwerk eine langsamere Latenz (500 ms oder mehr) als ein netzwerkgestütztes Netzwerk (20 bis 50 ms) hat. Unter den besten Bedingungen bemerken Sie diese Wartezeit möglicherweise nicht, aber für das Herunterladen großer Dateien, das Streamen von Videos und das Spielen von Spielen wird dies wahrscheinlich der Fall sein. Ein weiteres Problem ist der "Regenblass", bei dem schweres Wetter wie Gewitter und Schneesturm die Satellitenübertragung vorübergehend unterbrechen kann.
  
## <a name="are-you-sure-its-the-network"></a>Sind Sie sicher, dass es sich um das Netzwerk handelt?

Stellen Sie immer dann sicher, dass Ihr Gerät nicht die Hauptursache des Problems ist, wenn Leistungsprobleme auftreten. Es gibt zwei Dinge, die Sie tun können, um eine große Verbesserung zu machen:
  
- Stellen Sie sicher, dass Ihr Gerät gut ausgeführt wird und auf Ihrem Computer keine Schadsoftware enthalten ist.

- Wenn möglich, kaufen Sie mehr Arbeitsspeicher. Das Hinzufügen von Arbeitsspeicher ist die einfachste und häufig effektivste Methode, um die Leistung auf Ihrem Gerät zu verbessern. Es ist besonders hilfreich, wenn Sie mit großen Dateien und Videos arbeiten.

Weitere Informationen finden Sie unter [Windows Performance and maintenance](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) and Tipps to improve PC performance in [Windows 10](https://support.microsoft.com/en-za/help/4002019/windows-10-improve-pc-performance).

## <a name="best-practices-for-using-your-browser"></a>Bewährte Methoden für die Verwendung Ihres Browsers

Ihr Browser ist Ihr Gateway für Office 365, sodass er sich auf die Leistung auswirken kann, insbesondere mit der Zeit, die zum Laden einer Seite benötigt wird und wie oft Sie einen Roundtrip zum Office 365 haben.
  
 **Browser im Allgemeinen**
  
Hier sind einige Vorschläge für Browser im Allgemeinen:
  
- Deaktivieren Sie Browser-Add-Ons, die sich auf die Leistung auswirken können oder die Sie nicht wirklich benötigen.

- Erhöhen Sie die Cachegröße für Ihre temporären Internetdateien.

- Nachdem Sie sich bei Ihrem Arbeits- oder Schulkonto angemeldet haben, lassen Sie das Browserfenster den ganzen Tag geöffnet. Sie können andere Registerkarten und Fenster öffnen, ohne sich erneut zu anmelden. Wenn Sie sich bei einem anderen Konto anmelden müssen, verwenden Sie privates Browsen. 

- Nachdem jede Seite heruntergeladen und geöffnet wurde, lassen Sie sie mithilfe von Registerkarten geöffnet. Es ist einfach, zwischen Registerkarten zu navigieren und die Seite später am Tag zu verwenden. Aktualisieren Sie eine Seite nur, wenn Sie die neuesten Daten auf dieser Seite benötigen.

- Wenn das Öffnen einer Seite zu lang ist, beenden Sie den Seitendownload (drücken Sie ESC), und aktualisieren Sie die Seite (drücken Sie F5). 

-  Reduzieren Sie nach Möglichkeit Roundtrips zu Office 365. Verwenden Sie beispielsweise die Suche, um Dateien in einer großen Bibliothek zu suchen und in einer Liste zu filtern, um direkt zu den ergebnissen zu kommen, die Sie möchten, anstatt Listen oder Bibliotheken auslagerungen zu müssen. Oder erstellen Sie Ansichten, die die Ladezeit der Seite minimieren. Weitere Informationen finden Sie unter [Verwalten großer Listen und](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES)Bibliotheken in Office 365 .

- Wenn die Videoleistung schlecht ist, können Sie das Video möglicherweise herunterladen und auf Ihrem Gerät ansehen. Möglicherweise ist ein Downloadlink verfügbar, oder Sie können mit der rechten Maustaste auf den Videolink klicken und **Ziel speichern als auswählen.**

 **Browserspezifisch**
  
Hier sind einige Vorschläge für Ihren bestimmten Browser:
  
- **Internet Explorer** Upgrade auf Internet Explorer, Version 11 oder höher, um erhebliche Leistungsverbesserungen gegenüber früheren Versionen zu erzielen. Weitere Informationen finden Sie unter [Troubleshooting guide for Internet Explorer](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365).

- **FireFox** Weitere Informationen finden Sie unter [Firefox ist langsam oder funktioniert nicht mehr.](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging)

- **Safari** Weitere Informationen finden Sie unter [Apple - Safari](https://www.apple.com/safari/).

- **Chrome** Weitere Informationen finden Sie unter [Chrome Help](https://support.google.com/chrome/?hl=en).
  
## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Bewährte Methoden für die Verwendung Outlook und Outlook Web App

Lesen, Schreiben und Organisieren von E-Mails ist ein wichtiger Bestandteil des Täglichen. Sowohl Outlook als auch Outlook Web App (OWA) bieten Offlineunterstützung. Die Verwendung einer E-Mail-App auf Ihrem Smartphone ist eine weitere nützliche Alternative. Verwenden Sie die folgenden Optionen, die Ihren Anforderungen am besten entsprechen:
  
- Upgrade auf die neueste Version von Outlook für erhebliche Leistungsverbesserungen gegenüber früheren Versionen. 

-  Outlook Web App können Sie Offlinenachrichten, Kontakte und Kalenderereignisse erstellen, die hochgeladen werden, wenn OWA als nächstes eine Verbindung mit Office 365. Weitere Informationen zum Einrichten und Verwenden von OWA im Offlinemodus finden Sie unter [Using Outlook Web App offline](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36).

- Outlook können Sie im zwischengespeicherten Modus arbeiten, in dem sie nach Möglichkeit automatisch eine Verbindung herstellt. Sie können Outlook ihr gesamtes Postfach oder nur einen Teil davon herunterladen. Weitere Informationen finden Sie unter [Turn on Cached Exchange Mode](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) and Work offline in [Outlook](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633).

- Outlook bietet auch einen Offlinemodus. Um dies zu verwenden, müssen Sie zuerst den zwischengespeicherten Modus einrichten, damit Informationen aus Ihrem Konto auf Ihren Computer kopiert werden. Im Offlinemodus versucht Outlook, eine Verbindung über die Sende- und Empfangseinstellungen herzustellen, oder wenn Sie manuell festlegen, dass es online funktioniert. Weitere Informationen finden Sie unter Offline [arbeiten,](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282)um Datenverbindungsgebühren zu vermeiden, Senden und Empfangen von Einstellungen ändern, wenn Sie [offline](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)arbeiten, und Wechseln von offline zu [online](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9).

- Wenn Sie über ein Smartphone verfügen, können Sie es verwenden, um Ihre E-Mails und Ihren Kalender über das Netzwerk Ihres Telefonanbieters zu tridieren.

> [!NOTE]
> Hier finden Sie einige Anleitungen zur Verwendung von Outlook oder OWA. Wenn Der Speicherplatz auf Ihrem Gerät kein Problem ist, Outlook eine vollständige Reihe von Features verfügt und möglicherweise am besten für Sie funktioniert. Wenn Speicherplatz auf Ihrem Gerät ein Problem ist, sollten Sie OWA verwenden, das über eine Teilmenge von Features verfügt, aber auch in einer Onlinesituation am besten funktioniert. Natürlich können Sie beides verwenden, da sie gut zusammenarbeiten.
  
## <a name="best-practices-for-using-onedrive-for-business"></a>Bewährte Methoden für die Verwendung OneDrive for Business

OneDrive for Business ist von Grund auf für die Online- und Offlinearbeit mit Ihren Dateien konzipiert. Sobald Sie sie eingerichtet haben, erfolgt die Synchronisierung von Änderungen automatisch und zuverlässig, wo und wann immer Sie sie vornehmen. Wenn das Netzwerk langsam ist, können Sie mit der Offlineversion der Dateien arbeiten.
  
Die OneDrive for Business Synchronisierungs-App verfügt über ein SharePoint Online- und Office 365 [](https://support.microsoft.com/kb/2903984) Business-Abonnement, oder Sie können die OneDrive for Business-Synchronisierungs-App kostenlos herunterladen. Diese App ist auch schneller als die Verwendung der **Befehle Im Explorer öffnen** oder **Hochladen** verwenden. Weitere Informationen finden Sie unter Einrichten des Computers zum Synchronisieren [ihrer OneDrive for Business in Office 365](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16).
  
Hier sind einige zusätzliche Anleitungen für die Verwendung der OneDrive for Business Synchronisierungs-App:
  
- Wenn Sie eine große Bibliothek zum ersten Mal synchronisieren, starten Sie die Synchronisierung während der Zeiten, z. B. über Nacht.

- Sie können die Synchronisierung [einer](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) Bibliothek mit dem Feature OneDrive for Business beenden, um die Synchronisierung von Updates vorübergehend zu beenden. Verwenden Sie dieses Feature jedoch für kurze Zeiträume, z. B. einige Stunden, um zu vermeiden, dass eine große Anzahl von Updates in die Warteschlange kommt, und um das Risiko von Zusammenführungskonflikten zu minimieren, wenn mehrere Personen an demselben Dokument arbeiten.
  
## <a name="best-practices-for-using-onenote"></a>Bewährte Methoden für die Verwendung OneNote

Jede SharePoint Teamwebsite verfügt über ein integriertes OneNote Notizbuch, und Sie können ganz einfach Ihr eigenes erstellen. OneNote ist eine großartige Möglichkeit, zeitnahe Informationen zu sammeln, die Sie jeden Tag benötigen, um Aufgaben auszuführen. Viele Teams verwenden beispielsweise OneNote als Sammelstelle für wöchentliche Besprechungen, Projektnotizen, Ideen, Pläne und Statusberichte. Sie können diese unterschiedlichen Informationen mithilfe von Seiten, Abschnitten und Registerkarten übersichtlich organisieren.
  
Das Schöne an OneNote ist, dass Sie von praktisch jedem Gerät aus auf den Inhalt zugreifen können, sei es ein Desktop, ein Laptop, ein Tablet oder ein Smartphone. Und Sie müssen sich keine Gedanken über das Speichern oder Synchronisieren machen, da OneNote dies für Sie tut.
  
Weitere Informationen finden Sie unter [Microsoft OneNote](https://office.microsoft.com/onenote).

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Bewährte Methoden für die Verwendung von Skype for Business und Lync Online

Im Folgenden finden Sie allgemeine Richtlinien für Skype for Business oder Lync Online, wenn Ihr Netzwerk langsam ist:

- Verwenden Sie Instant Messaging, wann immer möglich, da es in einem langsamen Netzwerk gut funktioniert.

- Vermeiden Sie Telefonanrufe über vpn- oder RAS-Verbindungen (Virtual Private Network).

- Stellen Sie sicher, dass Ihr Audiogerät genehmigt ist. Weitere Informationen finden Sie unter [Phones and Devices Qualified for Microsoft Lync](/skypeforbusiness/lync-cert/ip-phones).

- Reduzieren Sie bei PowerPoint in einer Onlinepräsentation die Größe und Komplexität der Folien. Weitere Informationen finden Sie [unter Tipps, um die Leistung Ihrer Präsentation zu verbessern.](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949)

- Die Videoleistung hängt stark von der Netzwerkleistung ab. Vermeiden Sie die Verwendung von Video, wenn Ihr Netzwerk langsam ist.

Weitere Informationen finden Sie unter Schlechte Audio- oder [Videoqualität in Lync Online](https://support.microsoft.com/kb/2386655)oder wie Sie Verbindungsprobleme in lync online [Skype for Business.](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771)
  
## <a name="best-practices-for-using-sharepoint-lists"></a>Bewährte Methoden für die Verwendung SharePoint Listen

Das Offline arbeiten mit Listendaten zum "Scrubn", Analysieren oder Melden von Daten ist eine hervorragende Möglichkeit, um die Auswirkungen eines langsamen Netzwerks zu minimieren. Sie können die meisten Listen aus Microsoft Access 2019 und Microsoft Access 2016, indem Sie sie verknüpfen. Sie können auch eine Liste in eine tabelle Excel exportieren, die eine one-way-Datenverbindung zwischen der Excel und der Liste erstellt. Erfahren Sie, wie [Sie offline mit Tabellen arbeiten, die mit SharePoint verknüpft sind.](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e)
  
Weitere Informationen finden Sie im Abschnitt "Weitere Informationen zum Verwalten großer Listen" unter Verwalten großer Listen und [Bibliotheken in Office 365](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784).
  
## <a name="best-practices-for-customizing-web-pages"></a>Bewährte Methoden zum Anpassen von Webseiten

Wenn Sie eine Webseite anpassen, können Sie versehentlich eine schlechte Leistung mit der Seite verursachen. Eine Reihe von Faktoren kann Auswirkungen haben, z. B. die Komplexität und Größe der Seite, die Anzahl der hinzugefügten Webparts, die Anzahl der anfänglich angezeigten Listen- oder Bibliothekselemente und die Art und Weise, wie Sie die Seite codiert haben.
  
Weitere Informationen finden Sie unter [Tune SharePoint Online performance](tune-sharepoint-online-performance.md).
  
## <a name="best-practices-for-using-project-online"></a>Bewährte Methoden für die Verwendung Project Online

Die folgenden Richtlinien können zur Verbesserung der Netzwerkleistung beitragen.
  
- Project Online und SharePoint Online erfordern eine Synchronisierung, was zeitaufwändig sein kann. Wenn Ihre Projektteams einen geringen Umsatz haben, deaktivieren Sie Project Websitesynchronisierung, um die Leistung Project Veröffentlichen und Project Detailseiten zu verbessern. Beschränken Sie die Active Directory-Synchronisierung auf Ressourcengruppen, die das System tatsächlich verwenden müssen, und überwachen Sie potenzielle Berechtigungsprobleme nach der Synchronisierung großer Gruppen.

- Wenn Ihre Organisation Projektwebsites verwendet, erstellen Sie diese bei Bedarf und nicht automatisch. Dadurch wird die erste Veröffentlichungserfahrung beschleunigt und unnötige Websites und Inhalte vermieden.

- Project Detailseiten (PDP) können eine Neuberechnung des gesamten Projekts auslösen und Workflowaktionen auslösen, die beide leistungsintensive Vorgänge sein können. Vermeiden Sie es, die Kalenderfelder (Startdatum, Enddatum, Statusdatum und Aktuelles Datum) und die nicht geplanten Felder (Projektname, Beschreibung und Besitzer) zu aktualisieren, um zu vermeiden, dass zwei Aktualisierungsprozesse gleichzeitig auf derselben PDP ausgelöst werden.

- Verringern Sie die Anzahl Webparts und benutzerdefinierten Feldern, die in jedem PDP angezeigt werden. Erstellen Sie eine dedizierte PDP mit den einzigen Feldern, die aktualisiert werden müssen, um die Auslastung zu verbessern und Zeit zu sparen.

- Wenn Sie OData für die Berichterstellung verwenden, begrenzen Sie die Datenmenge, die Sie zur Laufzeit abfragen, mithilfe der serverseitigen Filterung.

Weitere Informationen finden Sie unter [Tune Project Online performance](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c).
  
## <a name="whats-the-best-way-to-report-problems"></a>Was ist die beste Methode, um Probleme zu melden?

Microsoft verbessert kontinuierlich die Gesamtleistung von Office 365, indem es das Netzwerk überwacht, Bandbreite und Latenz misst, die Ladezeit der Seite verbessert, die Datenträger-E/A reduziert, Seiten so umgestaltet, dass die Minimale Downloadstrategie verwendet wird, Hardware zu Rechenzentren hinzugefügt und weitere Rechenzentren hinzugefügt werden. Weitere Informationen zum Überprüfen des aktuellen Status und der Berichterstellung finden Sie unter [Überprüfen Office 365 Dienststatus](view-service-health.md).
  
## <a name="see-also"></a>Siehe auch

[Netzwerkplanung und Leistungsoptimierung für Office 365](network-planning-and-performance.md)
  
[Prinzipien von Office 365-Netzwerkverbindungen](microsoft-365-network-connectivity-principles.md)
  
[Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Häufig gestellte Fragen zu Office 365-Endpunkten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
