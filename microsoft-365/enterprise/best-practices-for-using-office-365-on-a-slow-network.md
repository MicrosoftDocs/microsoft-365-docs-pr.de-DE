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
description: Dieser Artikel führt Sie durch die bewährten Methoden, die Sie für die Verwendung von Office 365 in einem langsamen Netzwerk anwenden können.
ms.openlocfilehash: d217ee8bb40898716844717e84db112f356f6672
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226023"
---
# <a name="best-practices-for-using-office-365-on-a-slow-network"></a>Bewährte Methoden für die Verwendung von Office 365 in einem langsamen Netzwerk

Wäre es nicht gut, wenn Ihre Internetverbindung immer schnell und nie ausgefallen wäre? Vielleicht wird dieser Tag kommen. Aber in der Zwischenzeit gibt es praktische Dinge, die Sie tun können, um ein balkys Netzwerk zu umgehen und ihre tägliche Arbeit zu erledigen. Obwohl Office 365 ein cloudbasierter Dienst ist, bietet er auch viele Möglichkeiten, um mit Ihren Inhalten offline zu arbeiten und Ihre Änderungen reibungslos zu synchronisieren. Außerdem ist es manchmal effizienter, offline mit Inhalten zu arbeiten, nur weil Anwendungen schneller ausgeführt werden und die Benutzeroberfläche reaktionsfähiger ist. Der Punkt ist folgende: Office 365 bietet Ihnen das Beste aus beiden Welten. Hier erfahren Sie, wie Sie dies nutzen können.

> [!TIP]
> Möchten Sie sehen, wie langsam (oder schnell) Ihre Netzwerkverbindung ist? Testen Sie den [OOKLA Speed-Test](https://www.speedtest.net/) oder die [Netzwerkgeschwindigkeit-Test-App.](https://www.windowsphone.com/store/app/network-speed-test/9b9ae06b-2961-41ef-987d-b09567cffe70)

## <a name="why-is-my-network-so-slow"></a>Warum ist mein Netzwerk so langsam?

Obwohl Sie keine Kontrolle über die Netzwerkleistung selbst haben, hilft es, zu verstehen, was im Hintergrund geschieht. Das Internet ist äußerst komplex, aber es gibt einige Konzepte, die Ihnen dabei helfen können, die Situation viel besser zu verstehen. Das Befolgen der bewährten Methoden in diesem Artikel kann dazu beitragen, Leistungsprobleme zu umgehen und Frustration zu verringern.

### <a name="major-factors-that-affect-network-performance"></a>Wichtige Faktoren, die sich auf die Netzwerkleistung auswirken

![Netzwerkleistungsfaktoren](../media/62a94322-3f1a-4d2d-bbdc-2aa0722d2d96.png)

 **Bandbreite und Latenz:** Die beiden wichtigsten Messwerte für die Netzwerkleistung sind Bandbreite und Latenz:

- Die Bandbreite ist die in Bit pro Sekunde gemessene Durchsatzrate. Größer ist besser. Die Bandbreite ähnelt einer Wasserleitung. Je größer die Leitungen sind, desto mehr Wasser können Sie sie "durchsetzen".

- Latenz ist die Zeit, die es dauert, bis Inhalte von einem Server oder Dienst zu Ihrem Gerät gelangen, und wird in Millisekunden gemessen. Schneller ist besser. Die Latenz kann durch eine Reihe von Faktoren verursacht werden, z. B. geringe Bandbreite, eine geringe Verbindung oder Übertragungszeit.

 **Häufige Probleme:** Neben Bandbreite und Latenz wirken sich andere Probleme auf die Netzwerkleistung aus und sind häufig unvorhersehbar. Die Netzwerkleistung kann je nach Tageszeit oder ihrem physischen Standort variieren. Das Netzwerk kann protokolliert werden, wenn bestimmte Ereignisse auftreten, die die Nutzung des Internets an sich nehmen, z. B. eine Naturkatastrophe oder ein öffentliches Großereignis. Die Größe und Komplexität der geladenen Seite und die Anzahl und Größe der übertragenen Dateien wirken sich direkt auf die Leistung aus. Eine WLAN-Verbindung kann vorübergehend beeinträchtigt werden: Sie fragen beispielsweise eine große Konferenzbesprechung von Tausenden ab, indem Sie alle gleichzeitig zum Twittern auffordern.

 **Überlegungen für ein Satellitennetzwerk:** Ein Satellitennetzwerk ist nützlich, wenn ein netzgebundenes Netzwerk nicht machbar ist, z. B. das Hintergrundland, ein Versandland oder ein wissenschaftlicher Remotebereich. Diese Netzwerke basieren auf Satelliten, die sich in einem geosynchronen Orbit von 22.000 Meilen über dem Äquator befinden. Eine Übertragung dauert jedoch tatsächlich ca. 90.000 Meilen, und daher hat ein Satellitennetzwerk eine langsamere Latenz (500 ms oder mehr) als ein netzgebundenes Netzwerk (20 bis 50 ms). Unter den besten Bedingungen bemerken Sie diese Latenz möglicherweise nicht, aber für das Herunterladen großer Dateien, das Streamen von Videos und das Spielen von Spielen werden Sie wahrscheinlich. Ein weiteres Problem ist "Regenschwenken", bei dem bei starkem Wetter, z. B. Wetterböen und Wetterkapriolen, die Satellitenübertragung vorübergehend unterbrochen werden kann.

## <a name="are-you-sure-its-the-network"></a>Sind Sie sicher, dass es sich um das Netzwerk handelt?

Stellen Sie bei Leistungsproblemen zunächst sicher, dass Ihr Gerät nicht die Ursache des Problems ist. Es gibt zwei Dinge, die Sie tun können, um eine große Verbesserung zu erzielen:

- Stellen Sie sicher, dass Ihr Gerät gut ausgeführt wird und keine Schadsoftware auf Ihrem Computer vorhanden ist.

- Wenn möglich, kaufen Sie mehr Arbeitsspeicher. Das Hinzufügen von Arbeitsspeicher ist die einfachste und häufig effektivste Möglichkeit, die Leistung auf Ihrem Gerät zu verbessern. Es ist besonders hilfreich, wenn Sie mit großen Dateien und Videos arbeiten.

Weitere Informationen finden Sie unter [Windows Leistung und Wartung](https://windows.microsoft.com/windows/performance-maintenance-help#performance-maintenance-help) und Tipps zur Verbesserung der [PC-Leistung in Windows 10.](https://support.microsoft.com/help/4002019/windows-10-improve-pc-performance)

## <a name="best-practices-for-using-your-browser"></a>Bewährte Methoden für die Verwendung Ihres Browsers

Ihr Browser ist Ihr Gateway zu Office 365, sodass er sich auf die Leistung auswirken kann, insbesondere mit der Zeit, die zum Laden einer Seite benötigt wird, und der Anzahl der Roundtrips zum Office 365 Dienst.

### <a name="browsers-in-general"></a>Browser im Allgemeinen

Hier sind einige Vorschläge für Browser im Allgemeinen:

- Deaktivieren Sie Browser-Add-Ons, die sich möglicherweise auf die Leistung auswirken oder die Sie nicht wirklich benötigen.

- Erhöhen Sie die Cachegröße für ihre temporären Internetdateien.

- Nachdem Sie sich bei Ihrem Geschäfts-, Schul- oder Unikonto angemeldet haben, lassen Sie das Browserfenster den ganzen Tag geöffnet. Sie können andere Registerkarten und Fenster öffnen, ohne sich erneut anzumelden. Wenn Sie sich bei einem anderen Konto anmelden müssen, verwenden Sie privates Browsen.

- Sobald jede Seite heruntergeladen und geöffnet ist, lassen Sie sie mithilfe von Registerkarten geöffnet. Es ist einfach, zwischen Registerkarten zu navigieren und die Seite später am Tag zu verwenden. Aktualisieren Sie eine Seite nur, wenn Sie die neuesten Daten auf dieser Seite benötigen.

- Wenn das Öffnen einer Seite zu lange dauert, beenden Sie den Seitendownload (drücken Sie ESC), und aktualisieren Sie die Seite (drücken Sie F5).

- Reduzieren Sie nach Möglichkeit Roundtrips zu Office 365. Anstatt z. B. Listen oder Bibliotheken zu durchsuchen, verwenden Sie die Suche, um Dateien in einer großen Bibliothek zu suchen und in einer Liste zu filtern, um direkt zu den gewünschten Ergebnissen zu gelangen. Oder erstellen Sie Ansichten, die die Seitenladezeit minimieren. Weitere Informationen finden Sie unter [Verwalten großer Listen und Bibliotheken in Office 365.](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784#BKMK_PAGES)

- Wenn die Videoleistung schlecht ist, können Sie das Video möglicherweise herunterladen und auf Ihrem Gerät ansehen. Möglicherweise ist ein Downloadlink verfügbar, oder Sie können mit der rechten Maustaste auf den Videolink klicken und **"Ziel speichern unter"** auswählen.

### <a name="browser-specific"></a>Browserspezifisch

Hier sind einige Vorschläge für Ihren spezifischen Browser:

- **Internet Explorer:** Upgrade auf Internet Explorer Version 11 oder höher für erhebliche Leistungsverbesserungen gegenüber früheren Versionen. Weitere Informationen finden Sie im [Handbuch zur Problembehandlung für Internet Explorer.](https://support.microsoft.com/help/2437121/troubleshooting-guide-for-internet-explorer-when-you-access-office-365)
- **FireFirefox**: Weitere Informationen finden Sie unter [Firefox ist langsam oder funktioniert nicht mehr.](https://support.mozilla.org/products/firefox/fix-problems/slowness-or-hanging)
- **Safari:** Weitere Informationen finden Sie unter [Apple – Safari](https://www.apple.com/safari/).
- **Chrome:** Weitere Informationen finden Sie in der [Chrome-Hilfe.](https://support.google.com/chrome/?hl=en)

## <a name="best-practices-for-using-outlook-and-outlook-web-app"></a>Bewährte Methoden für die Verwendung von Outlook und Outlook Web App

Das Lesen, Schreiben und Organisieren von E-Mails ist ein großer Teil des Tages. Sowohl Outlook als auch Outlook Web App (OWA) bieten Offlinesupport. Die Verwendung einer E-Mail-App auf Ihrem Smartphone ist eine weitere nützliche Alternative. Verwenden Sie die folgenden Optionen, die Ihren Anforderungen am besten entsprechen:

- Upgrade auf die neueste Version von Outlook für erhebliche Leistungsverbesserungen gegenüber früheren Versionen.

- Outlook Web App können Sie Offlinenachrichten, Kontakte und Kalenderereignisse erstellen, die hochgeladen werden, wenn OWA als Nächstes eine Verbindung mit Office 365 herstellen kann. Weitere Informationen zum Einrichten und Verwenden von OWA im Offlinemodus finden Sie unter [Verwenden von Outlook Web App offline.](https://support.office.com/article/3214839c-0604-4162-8a97-6856b4c27b36)

- Outlook können Sie im Cachemodus arbeiten, in dem nach Möglichkeit automatisch eine Verbindung hergestellt wird. Sie können Outlook Ihr gesamtes Postfach oder nur einen Teil davon herunterladen. Weitere Informationen finden Sie unter [Aktivieren zwischengespeicherter Exchange Modus](https://support.office.com/article/7885af08-9a60-4ec3-850a-e221c1ed0c1c) und [Offlinearbeit in Outlook.](https://support.office.com/article/f3a1251c-6dd5-4208-aef9-7c8c9522d633)

- Outlook bietet auch einen Offlinemodus. Um dies zu verwenden, müssen Sie zuerst den Cachemodus einrichten, damit Informationen von Ihrem Konto auf Ihren Computer kopiert werden. Im Offlinemodus versuchen Outlook, eine Verbindung mithilfe der Sende- und Empfangseinstellungen herzustellen, oder wenn Sie sie manuell für die Onlinearbeit festlegen. Weitere Informationen finden Sie unter [Offlinearbeit, um Datenverbindungsgebühren zu vermeiden,](https://support.office.com/article/827fe51f-5609-4062-82b4-3578057f9282) [Ändern von Sende- und Empfangseinstellungen, wenn Sie offline arbeiten,](https://support.office.com/article/f681ec10-cb14-40cb-8709-1909a13c304a)und [Wechseln von offline zu online.](https://support.office.com/article/2460e4a8-16c7-47fc-b204-b1549275aac9)

- Wenn Sie über ein Smartphone verfügen, können Sie es verwenden, um Ihre E-Mails und Ihren Kalender über das Netzwerk Ihres Telefonanbieters zu triagen.

> [!NOTE]
> Hier sind einige Anleitungen zur Verwendung von Outlook oder OWA. Wenn der Speicherplatz auf Ihrem Gerät kein Problem darstellt, verfügt Outlook über einen vollständigen Satz von Features und funktioniert möglicherweise am besten für Sie. Wenn der Speicherplatz auf Ihrem Gerät ein Problem darstellt, sollten Sie OWA verwenden, das eine Teilmenge von Features aufweist, aber auch in einer Onlinesituation am besten funktioniert. Natürlich können Sie beides verwenden, da sie gut zusammenarbeiten.

## <a name="best-practices-for-using-onedrive-for-business"></a>Bewährte Methoden für die Verwendung von OneDrive for Business

OneDrive for Business wurde von Grund auf für die Arbeit mit Ihren Dateien online und offline entwickelt. Sobald Sie sie eingerichtet haben, erfolgt die Synchronisierung von Änderungen automatisch und zuverlässig, unabhängig davon, wo und wann Sie sie vornehmen. Wenn das Netzwerk langsam ist, können Sie mit der Offlineversion der Dateien arbeiten.

Die OneDrive for Business-Synchronisierungs-App enthält ein SharePoint Online- und Office 365 Business-Abonnement, oder Sie können die OneDrive for Business-Synchronisierungs-App kostenlos [herunterladen.](https://support.microsoft.com/kb/2903984) Diese App ist auch schneller als die Verwendung der Befehle **"Im Explorer öffnen"** oder **"Hochladen".** Weitere Informationen finden Sie unter [Einrichten des Computers zum Synchronisieren der OneDrive for Business Dateien in Office 365.](https://support.office.com/article/23e1f12b-d896-4cb1-a238-f91d19827a16)

Hier finden Sie einige zusätzliche Anleitungen für die Verwendung der OneDrive for Business-Synchronisierungs-App:

- Wenn Sie eine große Bibliothek zum ersten Mal synchronisieren, starten Sie die Synchronisierung außerhalb der Geschäftszeiten, z. B. über Nacht.
- Sie können die [Synchronisierung einer Bibliothek mit dem Feature OneDrive for Business App](https://support.office.com/article/a7e41f1f-3a98-4ca7-9443-f10250688330) beenden verwenden, um die Synchronisierung von Updates vorübergehend zu beenden. Verwenden Sie dieses Feature jedoch für kurze Zeiträume, z. B. einige Stunden gleichzeitig, um zu vermeiden, eine große Anzahl von Updates in die Warteschlange zu stellen, und um das Risiko von Zusammenführungskonflikten zu minimieren, wenn mehrere Personen am gleichen Dokument arbeiten.

## <a name="best-practices-for-using-onenote"></a>Bewährte Methoden für die Verwendung von OneNote

Jede SharePoint Teamwebsite verfügt über ein integriertes OneNote Notizbuch, das Sie ganz einfach erstellen können. OneNote ist eine großartige Möglichkeit zum Sammeln von zeitnahen Informationen, die Sie täglich benötigen, um Aufgaben zu erledigen. Viele Teams verwenden beispielsweise OneNote als Sammelpunkt für wöchentliche Besprechungen, Projektnotizen, Ideen, Pläne und Statusberichte. Sie können diese unterschiedlichen Informationen übersichtlich organisieren, indem Sie Seiten, Abschnitte und Registerkarten verwenden.

Der Vorteil von OneNote besteht darin, dass Sie von praktisch jedem Gerät aus auf den Inhalt zugreifen können, ob auf einem Desktop, einem Laptop, einem Tablet oder einem Smartphone. Und Sie müssen sich keine Gedanken über das Speichern oder Synchronisieren machen, da OneNote dies für Sie erledigt.

Weitere Informationen finden Sie unter [Microsoft OneNote](https://office.microsoft.com/onenote).

## <a name="best-practices-for-using-skype-for-business-and-lync-online"></a>Bewährte Methoden für die Verwendung von Skype for Business und Lync Online

Es folgen allgemeine Richtlinien für die Verwendung von Skype for Business oder Lync Online, wenn Ihr Netzwerk langsam ist:

- Verwenden Sie Chat, wann immer möglich, da es in einem langsamen Netzwerk gut funktioniert.

- Vermeiden Sie Telefonanrufe über ein virtuelles privates Netzwerk (VPN) oder RAS-Verbindungen (Remote Access Service).

- Stellen Sie sicher, dass Ihr Audiogerät genehmigt ist. Weitere Informationen finden Sie unter [Telefone und Geräte, die für Microsoft Lync qualifiziert sind.](/skypeforbusiness/lync-cert/ip-phones)

- Wenn Sie PowerPoint in einer Onlinepräsentation verwenden, verringern Sie die Größe und Komplexität der Folien. Weitere Informationen finden Sie unter [Tipps zur Verbesserung der Leistung Ihrer Präsentation.](https://support.office.com/article/34c82835-5f23-4bf0-98cc-72235bbd2949)

- Die Videoleistung hängt stark von der Netzwerkleistung ab. Vermeiden Sie die Verwendung von Video, wenn Ihr Netzwerk langsam ist.

Weitere Informationen finden Sie unter ["Schlechte Audio- oder Videoqualität" in Lync Online](https://support.microsoft.com/kb/2386655)oder wie [Verbindungsprobleme in Skype for Business behoben werden.](https://support.office.com/article/troubleshoot-connection-issues-in-skype-for-business-ca302828-783f-425c-bbe2-356348583771)

## <a name="best-practices-for-using-sharepoint-lists"></a>Bewährte Methoden für die Verwendung SharePoint Listen

Das Arbeiten mit Listendaten offline, um Daten zu "scruben", zu analysieren oder zu melden, ist eine hervorragende Möglichkeit, um die Auswirkungen eines langsamen Netzwerks zu minimieren. Sie können die meisten Listen aus Microsoft Access 2019 und Microsoft Access 2016 lesen und schreiben, indem Sie sie verknüpfen. Sie können eine Liste auch in eine Excel Tabelle exportieren, wodurch eine unidirektionale Datenverbindung zwischen der Excel Tabelle und der Liste erstellt wird. Erfahren Sie, wie Sie [offline mit Tabellen arbeiten, die mit SharePoint Listen verknüpft sind.](https://support.office.com/article/work-offline-with-tables-that-are-linked-to-sharepoint-lists-5d66594a-6176-4a25-a198-320f13ccf41e)

Weitere Informationen finden Sie im Abschnitt "Weitere Informationen zum Verwalten großer Listen" unter [Verwalten großer Listen und Bibliotheken in Office 365.](https://support.office.com/article/b4038448-ec0e-49b7-b853-679d3d8fb784)

## <a name="best-practices-for-customizing-web-pages"></a>Bewährte Methoden zum Anpassen von Webseiten

Wenn Sie eine Webseite anpassen, können Sie versehentlich eine schlechte Leistung mit der Seite verursachen. Eine Reihe von Faktoren kann sich auswirken, z. B. die Komplexität und Größe der Seite, wie viele Webparts hinzugefügt werden, wie viele Listen- oder Bibliothekselemente anfänglich angezeigt werden und wie Sie die Seite codieren.

Weitere Informationen finden Sie unter [Optimieren SharePoint Onlineleistung.](tune-sharepoint-online-performance.md)

## <a name="best-practices-for-using-project-online"></a>Bewährte Methoden für die Verwendung von Project Online

Die folgenden Richtlinien können zur Verbesserung der Netzwerkleistung beitragen.

- Project Online und SharePoint Online erfordern eine Synchronisierung, was zeitaufwändig sein kann. Wenn Ihre Projektteams über geringe Auslastung verfügen, deaktivieren Sie Project Websitesynchronisierung, um die Leistung der Project veröffentlichen und Project Detailseiten zu verbessern. Beschränken Sie die Active Directory-Synchronisierung auf Ressourcengruppen, die das System tatsächlich verwenden müssen, und überwachen Sie alle potenziellen Berechtigungsprobleme nach der Synchronisierung großer Gruppen.

- Wenn Ihre Organisation Projektwebsites verwendet, erstellen Sie sie nach Bedarf und nicht automatisch. Dies beschleunigt die erste Veröffentlichungserfahrung und verhindert das Erstellen unnötiger Websites und Inhalte.

- Project Detailseiten (PDP) können eine Neuberechnung des gesamten Projekts auslösen und Workflowaktionen starten, die beide leistungsintensive Vorgänge sein können. Um zu vermeiden, dass zwei Aktualisierungsprozesse gleichzeitig auf demselben PDP ausgelöst werden, vermeiden Sie das Aktualisieren der Kalenderfelder (Startdatum, Endtermin, Statusdatum und Aktuelles Datum) und der nicht geplanten Felder (Projektname, Beschreibung und Besitzer).

- Verringern Sie die Anzahl der Webparts und benutzerdefinierten Felder, die auf jedem PDP angezeigt werden. Erstellen Sie einen dedizierten PDP mit den einzigen Feldern, die aktualisiert werden müssen, um das Laden zu verbessern und Zeit zu sparen.

- Wenn Sie OData für die Berichterstellung verwenden, beschränken Sie die Datenmenge, die Sie zur Laufzeit abfragen, mithilfe der serverseitigen Filterung.

Weitere Informationen finden Sie unter [Optimieren Project Online Leistung.](https://support.office.com/article/12ba0ebd-c616-42e5-b9b6-cad570e8409c)

## <a name="whats-the-best-way-to-report-problems"></a>Was ist die beste Möglichkeit zum Melden von Problemen?

Microsoft verbessert kontinuierlich die Gesamtleistung von Office 365, indem es das Netzwerk überwacht, Bandbreite und Latenz misst, die Seitenladezeit verbessert, Datenträger-E/A reduziert, Seiten für die minimale Downloadstrategie neu gestaltet, Hardware zu Rechenzentren hinzufügt und weitere Rechenzentren hinzufügt. Weitere Informationen zum Überprüfen ihres aktuellen Status und zum Melden von Problemen finden Sie unter [Überprüfen Office 365 Dienststatus.](view-service-health.md)

## <a name="see-also"></a>Siehe auch

[Netzwerkplanung und Leistungsoptimierung für Office 365](network-planning-and-performance.md)

[Prinzipien von Office 365-Netzwerkverbindungen](microsoft-365-network-connectivity-principles.md)

[Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

[Häufig gestellte Fragen zu Office 365-Endpunkten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
