---
title: Microsoft 365 Netzwerkverbindungstesttool
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 09/21/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
description: Microsoft 365 Netzwerkverbindungstesttool
ms.openlocfilehash: 8cb25dfc8d11ca28d1a3c35985d84126f0652439
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470592"
---
# <a name="microsoft-365-network-connectivity-test-tool"></a>Microsoft 365 Netzwerkverbindungstesttool

Das Microsoft 365 Netzwerkverbindungstesttool befindet sich unter <https://connectivity.office.com> . Es handelt sich um ein Zusätzliches Tool zu den Netzwerkbewertungs- und Netzwerkeinblickinformationen, die im Microsoft 365 Admin Center unter health **| Konnektivitätsmenü.**

> [!IMPORTANT]
> Es ist wichtig, sich bei Ihrem mandanten Microsoft 365 anmelden, da alle Testberichte für Ihren Administrator freigegeben und während der Anmeldung in den Mandanten hochgeladen werden.

> [!div class="mx-imgBorder"]
> ![Konnektivitätstesttool](../media/m365-mac-perf/m365-mac-perf-test-tool-page.png)

>[!NOTE]
>Das Testtool für netzwerkkonnektivität unterstützt Mandanten in WW Commercial und Deutschland, aber nicht GCC Moderate, GCC High, DoD oder China.

Die Netzwerkeinblicke im Microsoft 365 Admin Center basieren auf regelmäßigen Produktmessungen für Microsoft 365 Mandanten, die täglich aggregiert werden. Im Vergleich dazu werden die Netzwerkeinblicke Microsoft 365 netzwerkkonnektivitätstests lokal und einmal im Tool ausgeführt. Tests, die im Produkt durchgeführt werden können, sind begrenzt, und durch das Ausführen lokaler Tests für den Benutzer können mehr Daten gesammelt werden, was zu tieferen Einblicken führt. Berücksichtigen Sie dann, dass die Netzwerkeinblicke im Microsoft 365 Admin Center zeigen, dass es ein Netzwerkproblem für die Verwendung von Microsoft 365 an einem bestimmten Bürostandort gibt. Der Microsoft 365 Konnektivitätstest kann helfen, die Ursache dieses Problems zu ermitteln, die zu einer empfohlenen Verbesserung der Netzwerkleistung führt.

Es wird empfohlen, diese Erkenntnisse zusammen zu verwenden, bei denen der Netzwerkqualitätsstatus für jeden Bürostandort im Microsoft 365 Admin Center bewertet werden kann und weitere Spezifisches nach der Bereitstellung von Tests basierend auf dem Microsoft 365-Konnektivitätstest gefunden werden können.

>[!IMPORTANT]
>Netzwerkeinblicke, Leistungsempfehlungen und Bewertungen im Microsoft 365 Admin Center befinden sich derzeit im Vorschaustatus und sind nur für Microsoft 365-Mandanten verfügbar, die im Featurevorschauprogramm registriert wurden.

## <a name="what-happens-at-each-test-step"></a>Was bei jedem Testschritt passiert

### <a name="office-location-identification"></a>Office Standortidentifikation

Wenn Sie auf die Schaltfläche Test ausführen klicken, wird die ausgeführte Testseite angezeigt und der Standort des Büros identifiziert. Sie können Ihren Standort nach Stadt, Bundesland und Land eingeben oder im Webbrowser erkennen lassen. Wenn Sie ihn erkennen, fordern wir den Breiten- und Längengrad vom Webbrowser an und begrenzen die Genauigkeit vor der Verwendung auf 300 Meter um 300 Meter. Wir tun dies, da es nicht erforderlich ist, den Standort genauer zu identifizieren als das Gebäude für die Netzwerkleistung. 

### <a name="javascript-tests"></a>JavaScript-Tests

Nach der Identifizierung des Standorts im Büro führen wir einen TCP-Latenztest in JavaScript aus, und wir fordern Daten vom Dienst zu den verwendeten und empfohlenen Office 365-Front-Door-Servern an. Wenn diese Tests abgeschlossen sind, werden sie auf der Karte und auf der Registerkarte Details angezeigt, wo sie vor dem nächsten Schritt angezeigt werden können.

### <a name="download-the-advanced-tests-client-application"></a>Herunterladen der Clientanwendung für erweiterte Tests

Als Nächstes starten wir den Download der Clientanwendung für erweiterte Tests. Wir verlassen uns darauf, dass der Benutzer die Clientanwendung startet, und er muss auch .NET Core installiert haben.

Der Netzwerkverbindungstest Microsoft 365 zwei Teile: die Website und eine herunterladbare Windows Clientanwendung, die erweiterte <https://connectivity.office.com> Netzwerkkonnektivitätstests ausgeführt. Für die meisten Tests muss die Anwendung ausgeführt werden. Die Ergebnisse werden bei derEn Läufe wieder in die Webseite auffüllt.

Sie werden aufgefordert, die erweiterte Clienttestanwendung von der Website herunterzuladen, nachdem die Webbrowsertests abgeschlossen sind. Öffnen Sie die Datei, und führen Sie sie aus, wenn Sie dazu aufgefordert werden.

> [!div class="mx-imgBorder"]
> ![Erweiterte Tests der Clientanwendung](../media/m365-mac-perf/m365-mac-perf-open-run-file.png)

### <a name="start-the-advanced-tests-client-application"></a>Starten der Clientanwendung für erweiterte Tests

Sobald die Clientanwendung gestartet wird, wird die Webseite aktualisiert, um dieses Ergebnis zu zeigen. Testdaten werden auf der Webseite empfangen. Die Seite wird jedes Mal aktualisiert, wenn neue Daten empfangen werden, und Sie können die Daten beim Eintreffen überprüfen.

### <a name="advanced-tests-completed-and-test-report-upload"></a>Erweiterte Tests abgeschlossen und Testbericht hochgeladen

Wenn die Tests abgeschlossen sind, wird dies sowohl auf der Webseite als auch auf dem Client für erweiterte Tests angezeigt. Wenn der Benutzer angemeldet ist, wird der Testbericht in den Mandanten des Kunden hochgeladen.

## <a name="sharing-your-test-report"></a>Freigeben des Testberichts

Für den Testbericht ist die Anmeldung bei Ihrem Office 365 erforderlich. Ihr Administrator wählt aus, wie Sie Ihren Testbericht freigeben können.

### <a name="sharing-your-report-with-your-administrator"></a>Freigeben Des Berichts für Ihren Administrator

Wenn Sie bei einem Testbericht angemeldet sind, werden diese Berichte für Ihren Administrator freigegeben.

### <a name="sharing-with-your-microsoft-account-team-support-or-other-personnel"></a>Teilen mit Ihrem Microsoft-Kontoteam, Support oder anderen Mitarbeitern

Testberichte (ohne persönliche Identifikation) werden an Microsoft-Mitarbeiter weitergegeben. Diese Freigabe ist standardmäßig aktiviert und kann von Ihrem Administrator in der Integritätsverwaltung **| Seite "Netzwerkkonnektivität"** im Microsoft 365 Admin Center.

### <a name="sharing-with-other-users-who-sign-in-to-the-same-office-365-tenant"></a>Freigabe für andere Benutzer, die sich beim gleichen Mandanten Office 365 anmelden

Sie können Benutzer auswählen, für die Sie Ihren Bericht freigeben möchten. Die Auswahl ist standardmäßig aktiviert, kann jedoch von Ihrem Administrator deaktiviert werden.

> [!div class="mx-imgBorder"]
> ![Freigeben eines Links zu Den Testergebnissen für einen Benutzer](../media/m365-mac-perf/m365-mac-perf-share-to-user.png)

### <a name="sharing-with-anyone-using-a-reportid-link"></a>Freigeben für alle Personen, die einen ReportID-Link verwenden

Sie können Ihren Testbericht für jeden benutzer freigeben, indem Sie Zugriff auf einen ReportID-Link bereitstellen. Dieser Link generiert eine URL, die Sie an eine Person senden können, damit sie den Testbericht ohne Anmeldung erstellen kann. Diese Freigabe ist standardmäßig deaktiviert und muss vom Administrator aktiviert werden.

> [!div class="mx-imgBorder"]
> ![Freigeben eines Links zu Den Testergebnissen](../media/m365-mac-perf/m365-mac-perf-share-link.png)

## <a name="network-connectivity-test-results"></a>Testergebnisse für netzwerkkonnektivität

Die Ergebnisse werden auf den Registerkarten **Zusammenfassung** **und Details** angezeigt. Die Registerkarte Zusammenfassung zeigt eine Karte des erkannten Netzwerkperimeters und einen Vergleich der Netzwerkbewertung mit anderen Office 365 Kunden in der Nähe. Es ermöglicht auch die Freigabe des Testberichts. So sieht die Zusammenfassungsergebnisansicht aus:

> [!div class="mx-imgBorder"]
> ![Zusammenfassende Ergebnisse des Netzwerkverbindungstesttools](../media/m365-mac-perf/m365-mac-perf-summary-page.png)

Hier sehen Sie ein Beispiel für die Detailregisterkartenausgabe, die das Tool zeigt. Auf der Registerkarte Details wird ein grünes Kreis-Häkchen angezeigt, wenn das Ergebnis positiv mit einem Schwellenwert verglichen wurde. Wir zeigen ein rotes Dreieck-Ausrufezeichen an, wenn das Ergebnis einen Schwellenwert überschritten hat, der einen Netzwerkblick angibt. In den folgenden Abschnitten werden die einzelnen Detailregisterkartenergebniszeilen beschrieben und die Schwellenwerte erläutert, die für Netzwerkeinblicke verwendet werden.

> [!div class="mx-imgBorder"]
> ![Testergebnisse des Testtools für netzwerkkonnektivität](../media/m365-mac-perf/m365-mac-perf-all-details.png)

### <a name="your-location-information"></a>Ihre Standortinformationen

Dieser Abschnitt zeigt Testergebnisse im Zusammenhang mit Ihrem Standort.

#### <a name="your-location"></a>Ihr Standort

Der Benutzerspeicherort wird vom Webbrowser der Benutzer erkannt. Sie kann auch nach Wahl des Benutzers eingeben. Es wird verwendet, um Netzwerkabstände zu bestimmten Teilen des Unternehmensnetzwerkperimeters zu identifizieren. Nur die Stadt von dieser Standorterkennung und der Abstand zu anderen Netzwerkpunkten werden im Bericht gespeichert.

Der Standort des Benutzerbüros wird in der Kartenansicht angezeigt.

#### <a name="network-egress-location-the-location-where-your-network-connects-to-your-isp"></a>Netzwerk-Ausgangsspeicherort (der Ort, an dem Ihr Netzwerk eine Verbindung mit Ihrem Internetdienstanbieter herstellt)

Wir identifizieren die netzwerkseitige IP-Adresse auf serverseitiger Seite. Standortdatenbanken werden verwendet, um den ungefähren Standort für den Netzwerkress nach zu suchen. Diese Datenbanken haben in der Regel eine Genauigkeit von ca. 90 % der IP-Adressen. Wenn der Standort, der von der IP-Adresse des Netzwerk-Ausgangs aus gesucht wurde, nicht genau ist, würde dies zu einem falschen Ergebnis aus diesem Test führen. Um zu überprüfen, ob dieser Fehler für eine bestimmte IP-Adresse auftritt, können Sie öffentlich zugängliche Websites für Netzwerk-IP-Adressen zum Vergleich mit Ihrem tatsächlichen Speicherort verwenden.

#### <a name="your-distance-from-the-network-egress-location"></a>Ihr Abstand zum Netzwerk-Ausgangsspeicherort

Wir bestimmen den Abstand zwischen diesem Standort und dem Bürostandort. Dies wird als Netzwerk-Einblick gezeigt, wenn die Entfernung größer als **800** Kilometer ist, da dies wahrscheinlich die TCP-Latenz um mehr als 25 ms erhöht und sich auf die Benutzererfahrung auswirken kann.

Der Netzwerk-Ausgangsspeicherort wird in der Kartenansicht angezeigt und mit dem Standort des Benutzerbüros verbunden, der den Netzwerk-Backhaul innerhalb des Unternehmens-WAN angibt.

Die Implementierung des lokalen und direkten Netzwerkeinbindungs von Denkstandorten in das Internet wird für die Microsoft 365 empfohlen. Verbesserungen am lokalen und direkten Ausgangs sind die beste Methode, um diese Netzwerkeinblicke zu verbessern.

#### <a name="proxy-server-information"></a>Proxyserverinformationen

Wir identifizieren Proxyserver, die auf dem lokalen Computer konfiguriert sind. Wir identifizieren, ob eine dieser Einstellungen im Netzwerkpfad zur Optimierung der Kategorie Microsoft 365 konfiguriert ist. Wir identifizieren den Abstand vom Standort des Benutzerbüros zu den Proxyservern. Der Abstand wird zuerst durch ICMP-Ping getestet, und wenn dies fehlschlägt, testen wir mit TCP-Ping und schließlich, wenn dies fehlschlägt, suchen wir die Proxyserver-IP-Adresse in einer IP-Adressspeicherortdatenbank. Wir zeigen einen Netzwerkblick, wenn der Proxyserver mehr als **800** Kilometer vom Standort des Benutzerbüros entfernt ist.

#### <a name="virtual-private-network-vpn-you-use-to-connect-to-your-organization"></a>Virtuelles privates Netzwerk (VPN), das Sie zum Herstellen einer Verbindung mit Ihrer Organisation verwenden

Dadurch wird erkannt, ob Sie ein VPN zum Herstellen einer Verbindung mit Office 365. Ein übergebenes Ergebnis zeigt, ob Sie über kein VPN verfügen oder wenn Sie über ein VPN mit empfohlener Konfiguration für geteilten Tunnel für Office 365.

#### <a name="vpn-split-tunnel"></a>GETEILTE VPN-Tunnel

Jede optimierte Kategorieroute für Exchange Online, SharePoint Online und Microsoft Teams wird getestet, um zu prüfen, ob sie über das VPN getunnelt wird oder nicht. Durch eine aufgeteilte Arbeitsauslastung wird das VPN vollständig vermieden. Eine getunnelte Arbeitsauslastung wird alle über das VPN gesendet. Bei einer selektiven Tunnelarbeitsauslastung werden einige Routen über das VPN gesendet und einige aufgeteilt. Ein übergebenes Ergebnis zeigt an, ob alle Arbeitsauslastungen aufgeteilt oder selektiv getunnelt werden.

#### <a name="customers-in-your-metropolitan-area-with-better-performance"></a>Kunden in Ihrer Metropolregion mit besserer Leistung

Die Netzwerk-TCP-Latenz des Standorts des Benutzerbüros zur Exchange Online-Service-Eingangstür wird mit anderen Microsoft 365 Kunden im gleichen U-Bahn-Bereich verglichen. Ein Netzwerkblick wird angezeigt, wenn 10 % oder mehr Kunden im gleichen U-Bahn-Bereich eine bessere Leistung haben. Dies bedeutet, dass ihre Benutzer eine bessere Leistung in der Microsoft 365 haben.

Diese Netzwerkinblicke werden auf der Grundlage generiert, dass alle Benutzer in einer Stadt Zugriff auf dieselbe Telekommunikationsinfrastruktur und die gleiche Nähe zu Internetschaltungen und microsofts Netzwerk haben.

#### <a name="time-to-make-a-dns-request-on-your-network"></a>Zeit zum Erstellen einer DNS-Anforderung in Ihrem Netzwerk

Dies zeigt den DNS-Server, der auf dem Clientcomputer konfiguriert ist, auf dem die Tests ausgeführt wurden. Es kann sich um einen DNS-Rekursiven Resolver-Server handelt, dies ist jedoch ungewöhnlich. Es ist wahrscheinlicher, dass es sich um einen DNS-Weiterleitungsserver handelt, der DNS-Ergebnisse zwischenspeichert und nicht zwischengespeicherte DNS-Anforderungen an einen anderen DNS-Server weitersent.

Dies wird nur für Informationen bereitgestellt und trägt nicht zu Netzwerkinformationen bei.

#### <a name="your-distance-from-andor-time-to-connect-to-a-dns-recursive-resolver"></a>Ihre Entfernung und/oder Zeit zum Herstellen einer Verbindung mit einem rekursiven DNS-Resolver

Der in-use DNS Recursive Resolver wird identifiziert, indem eine bestimmte DNS-Anforderung ausgeführt wird und der DNS-Nameserver dann nach der IP-Adresse gefragt wird, von der er dieselbe Anforderung erhalten hat. Diese IP-Adresse ist der DNS-Rekursive Resolver und wird in ip-Adressspeicherortdatenbanken nach dem Speicherort gesucht. Der Abstand zwischen dem Standort des Benutzerbüros und dem DNS Recursive Resolver-Serverspeicherort wird dann berechnet. Dies wird als Netzwerk-Einblick angezeigt, wenn die Entfernung größer als **800** Kilometer ist.

Der Von der Netzwerk-IP-Adresse aus gesuchte Speicherort ist möglicherweise nicht genau, und dies würde zu einem falschen Ergebnis aus diesem Test führen. Um zu überprüfen, ob dieser Fehler für eine bestimmte IP-Adresse auftritt, können Sie öffentlich zugängliche Netzwerk-IP-Adressspeicherortwebsites verwenden.

Dieser Netzwerkblick wirkt sich speziell auf die Auswahl der Exchange Online-Front-Door aus. Um diese Erkenntnisse zu beheben, sollte der lokale und direkte Netzwerkeinfall eine Voraussetzung sein, und dann sollte sich der DNS Recursive Resolver in der Nähe dieses Netzwerk-Ausgangs befinden.

### <a name="exchange-online"></a>Exchange Online

Dieser Abschnitt enthält Testergebnisse im Zusammenhang mit Exchange Online.

#### <a name="exchange-service-front-door-location"></a>Exchange Der Standort der Eingangstür des Diensts

Die In-Use-Exchange-Dienst-Eingangstür wird auf die gleiche Weise identifiziert, wie Outlook dies tut, und wir messen die Netzwerk-TCP-Latenz vom Benutzerspeicherort zu ihr. Die TCP-Latenz wird angezeigt, und die Exchange verwendeten Eingangstür des Diensts wird mit der Liste der besten Dienst-Fronttüren für den aktuellen Standort verglichen. Dies wird als Netzwerk-Einblick angezeigt, wenn eine der besten Exchange-Fronttüren nicht verwendet wird.

Das Nicht verwenden einer der besten Exchange-Fronttüren des Diensts könnte durch netzwerk backhaul verursacht werden, bevor das Unternehmensnetzwerk abfresst. In diesem Fall wird der lokale und direkte Netzwerkeinschwung empfohlen. Dies kann auch durch die Verwendung eines rekursiven Remote-DNS-Resolverservers verursacht werden. In diesem Fall wird empfohlen, den rekursiven DNS-Resolverserver an den Netzwerkress auszurichten.

Wir berechnen eine potenzielle Verbesserung der TCP-Latenz (ms) für die Exchange-Eingangstür des Diensts. Dazu wird die getestete Netzwerklatenz des Office-Standorts des Benutzers untersucht und die Netzwerklatenz vom aktuellen Standort an die Schränke Exchange Eingangstür des Diensts subtrahiert. Der Unterschied stellt die potenzielle Verbesserungsmöglichkeiten dar.

#### <a name="best-exchange-service-front-doors-for-your-location"></a>Best Exchange service front door(s) for your location

Dies listet die Exchange Für den Dienst an der Eingangstür nach Ort für Ihren Standort auf.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Im Client-DNS aufgezeichnete Dienst-Front-Door

Dies zeigt den DNS-Namen und die IP-Adresse des Exchange-Front-Door-Servers an, an den Sie geleitet wurden. Es wird nur für Informationen bereitgestellt, und es gibt keine zugeordneten Netzwerkinformationen.

### <a name="sharepoint-online"></a>SharePoint Online

Dieser Abschnitt zeigt Testergebnisse im Zusammenhang mit SharePoint Online und OneDrive.

#### <a name="the-service-front-door-location"></a>Der Standort der Dienst-Eingangstür

Die In-Use-SharePoint-Dienst-Eingangstür wird auf die gleiche Weise identifiziert wie der OneDrive-Client, und wir messen die Netzwerk-TCP-Latenz vom Standort des Benutzerbüros bis zu diesem.

#### <a name="download-speed"></a>Downloadgeschwindigkeit

Wir messen die Downloadgeschwindigkeit für eine 15-Mb-Datei von der SharePoint-Front-Door. Das Ergebnis wird in Megabyte pro Sekunde angezeigt, um anzugeben, welche Größendatei in Megabyte von SharePoint oder OneDrive in einer Sekunde **heruntergeladen werden kann.** Die Zahl sollte etwa einem Zehntel der Minimalbandbreite in Megabits pro Sekunde ähneln. Wenn Sie z. B. über eine 100 Mb/s-Internetverbindung verfügen, können Sie mit 10 Megabyte pro Sekunde (10 MBit/s) rechnen.

#### <a name="buffer-bloat"></a>Pufferbloat

Während des 15 Mb-Downloads messen wir die TCP-Latenz für die SharePoint-Eingangstür des Diensts. Dies ist die Latenz unter Last, und sie wird mit der Latenz verglichen, wenn sie nicht unter Last liegt. Die Zunahme der Latenz bei Last ist häufig auf Verbrauchernetzwerkgerätepuffer zurückzuführen, die geladen (oder aufgebläht) werden. Ein Netzwerkblick wird für alle Bloat von 1.000 oder mehr angezeigt.

#### <a name="service-front-door-recorded-in-the-client-dns"></a>Im Client-DNS aufgezeichnete Dienst-Front-Door

Dies zeigt den DNS-Namen und die IP-Adresse des SharePoint-Front-Door-Servers an, an den Sie geleitet wurden. Es wird nur für Informationen bereitgestellt, und es gibt keine zugeordneten Netzwerkinformationen.

### <a name="microsoft-teams"></a>Microsoft Teams

Dieser Abschnitt zeigt Testergebnisse im Zusammenhang mit Microsoft Teams.

#### <a name="media-connectivity-audio-video-and-application-sharing"></a>Medienkonnektivität (Audio-, Video- und Anwendungsfreigabe)

Dadurch wird die UDP-Konnektivität mit der Microsoft Teams-Eingangstür des Diensts getestet. Wenn dies blockiert ist, Microsoft Teams weiterhin mit TCP funktionieren, aber Audio und Video werden beeinträchtigt. Weitere Informationen zu diesen UDP-Netzwerkmessungen, die auch für Microsoft Teams unter [Media Quality and Network Connectivity Performance in Skype for Business Online gelten.](/skypeforbusiness/optimizing-your-network/media-quality-and-network-connectivity-performance)

#### <a name="packet-loss"></a>Paketverlust

Zeigt den INP-Paketverlust an, der in einem 10-Sekunden-Testaudioanruf vom Client an die Microsoft Teams-Front-Door gemessen wird. Dies sollte für einen Pass **unter 1,00 %** liegen.

#### <a name="latency"></a>Latency

Zeigt die gemessene UDP-Latenz an, die kleiner als **100 ms sein sollte.**

#### <a name="jitter"></a>Jitter

Zeigt den gemessenen UDP-Jitter an, der kleiner als **30 ms sein sollte.**

#### <a name="connectivity"></a>Konnektivität

Wir testen die HTTP-Verbindung vom Standort des Benutzerbüros zu allen erforderlichen Microsoft 365 Netzwerkendpunkten. Diese werden unter [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md) veröffentlicht. Für alle erforderlichen Netzwerkendpunkte, mit denen keine Verbindung besteht, wird ein Netzwerkblick angezeigt.

Die Konnektivität kann von einem Proxyserver, einer Firewall oder einem anderen Netzwerksicherheitsgerät auf dem Unternehmensnetzwerkperimeter blockiert werden. Die Konnektivität mit TCP-Port 80 wird mit einer HTTP-Anforderung getestet, und die Konnektivität zu TCP-Port 443 wird mit einer HTTPS-Anforderung getestet. Wenn keine Antwort vor liegt, wird der FQDN als Fehler gekennzeichnet. Wenn der HTTP-Antwortcode 407 vor ist, wird der FQDN als Fehler gekennzeichnet. Wenn der HTTP-Antwortcode 403 vorhanden ist, überprüfen wir das Server-Attribut der Antwort, und wenn es sich anscheinend um einen Proxyserver handelt, wird dies als Fehler bezeichnet. Sie können die Tests simulieren, die wir mit Windows Befehlszeilentool curl.exe.

Wir testen das SSL-Zertifikat an jedem erforderlichen Microsoft 365 Netzwerkendpunkt, der sich in der Kategorie optimieren oder zulassen befindet, wie unter [https://aka.ms/o365ip](./urls-and-ip-address-ranges.md) definiert. Wenn tests kein Microsoft SSL-Zertifikat finden, muss das verbundene verschlüsselte Netzwerk von einem zwischengeschalteten Netzwerkgerät abgefangen worden sein. Ein Netzwerkblick wird auf allen abgefangenen verschlüsselten Netzwerkendpunkten angezeigt.

Wenn ein SSL-Zertifikat gefunden wird, das nicht von Microsoft bereitgestellt wird, wird der FQDN für den Test und der besitzer des verwendeten SSL-Zertifikats gezeigt. Dieser SSL-Zertifikatbesitzer kann ein Proxyserveranbieter oder ein selbst signiertes Zertifikat des Unternehmens sein.

#### <a name="network-path"></a>Netzwerkpfad

In diesem Abschnitt werden die Ergebnisse einer ICMP-Ablaufverfolgungsroute zur Exchange Online-Dienst-Eingangstür, der SharePoint Online-Dienst-Eingangstür und der Microsoft Teams-Service-Eingangstür angezeigt. Es wird nur für Informationen bereitgestellt, und es gibt keine zugeordneten Netzwerkinformationen. Es werden drei Ablaufverfolgungsrouten bereitgestellt. Eine Traceroute zu _outlook.office365.com_, eine Ablaufverfolgungsroute zu den Kunden SharePoint Front-End oder zu _microsoft.sharepoint.com_ wenn keines bereitgestellt wurde, und eine Traceroute zu _world.tr.teams.microsoft.com_.

## <a name="connectivity-reports"></a>Konnektivitätsberichte

Wenn Sie angemeldet sind, können Sie vorherige Berichte überprüfen, die Sie ausgeführt haben. Sie können sie auch freigeben oder aus der Liste löschen.

> [!div class="mx-imgBorder"]
> ![Berichte](../media/m365-mac-perf/m365-mac-perf-reports-list.png)

## <a name="network-health-status"></a>Status des Netzwerkstatus

Dies zeigt alle wichtigen Integritätsprobleme mit dem globalen Netzwerk von Microsoft, die sich auf Microsoft 365 auswirken können.

> [!div class="mx-imgBorder"]
> ![Status des Netzwerkstatus](../media/m365-mac-perf/m365-mac-perf-status-page.png)

## <a name="faq"></a>Häufig gestellte Fragen

Hier finden Sie Antworten auf einige unserer häufig gestellten Fragen.

### <a name="is-this-tool-released-and-supported-by-microsoft"></a>Wird dieses Tool von Microsoft veröffentlicht und unterstützt?

Es handelt sich derzeit um eine Vorschau, und wir planen, updates regelmäßig zur Verfügung zu stellen, bis wir den Status der allgemeinen Verfügbarkeitsfreigabe mit Unterstützung von Microsoft erreichen. Bitte geben Sie Feedback, um uns bei der Verbesserung zu unterstützen. Wir planen die Veröffentlichung eines detaillierten Office 365 network onboarding guide als Teil dieses Tools, das durch die Testergebnisse für die Organisation angepasst wird.

### <a name="what-is-required-to-run-the-advanced-test-client"></a>Was ist erforderlich, um den erweiterten Testclient ausführen zu können?

Für den erweiterten Testclient ist .NET Core 3.1 Desktop Runtime erforderlich. Wenn Sie den erweiterten Testclient ausführen, ohne dass dieser installiert ist, werden Sie zur [.NET Core 3.1-Installationsseite weitergeleitet.](https://dotnet.microsoft.com/download/dotnet-core/3.1) Installieren Sie unbedingt die Desktop-Runtime und nicht das SDK oder die ASP.NET Core Runtime, die höher auf der Seite sind. Administratorberechtigungen auf dem Computer sind erforderlich, um .NET Core zu installieren.

### <a name="what-is-microsoft-365-service-front-door"></a>Was ist Microsoft 365 Service-Eingangstür?

Die Microsoft 365 ist ein Einstiegspunkt im globalen Netzwerk von Microsoft, in dem Office und Dienste ihre Netzwerkverbindung beenden. Für eine optimale Netzwerkverbindung mit Microsoft 365 wird empfohlen, dass Ihre Netzwerkverbindung an der nächsten Microsoft 365 in Ihrer Stadt oder U-Bahn beendet wird.

> [!NOTE]
> Microsoft 365-Front-Door-Dienst hat keine direkte Beziehung zum Azure Front Door Service-Produkt, das im **Azure** Marketplace verfügbar ist.

### <a name="what-is-the-best-microsoft-365-service-front-door"></a>Was ist die beste Microsoft 365- und Eingangstür?

Eine optimale Microsoft 365 (früher als optimale Service-Eingangstür bezeichnet) ist eine, die Ihrem Netzwerkeingang am nächsten ist, in der Regel in Ihrer Stadt oder Ihrer U-Bahn. Verwenden Sie Microsoft 365 Netzwerkleistungstool, um den Standort Ihrer Microsoft 365 und die besten Fronttüren des Diensts zu ermitteln. Wenn das Tool bestimmt, dass Ihre in-Use-Fronttür eine der besten ist, sollten Sie eine gute Verbindung mit dem globalen Netzwerk von Microsoft erwarten.

### <a name="what-is-an-internet-egress-location"></a>Was ist ein Internet-Ausgangsspeicherort?

Der Standort des Internetaustritts ist der Ort, an dem Ihr Netzwerkdatenverkehr Ihr Unternehmensnetzwerk verlässt und eine Verbindung mit dem Internet herstellt. Dies wird auch als Standort identifiziert, an dem Sie über ein Nat-Gerät (Network Address Translation) verfügen und in der Regel eine Verbindung mit einem Internetdienstanbieter (Internet Service Provider, ISP) herstellen. Wenn sie einen langen Abstand zwischen Ihrem Standort und Ihrem Internet-Ausgangsspeicherort sehen, kann dies einen erheblichen WAN-Backhaul identifizieren.

## <a name="related-topics"></a>Verwandte Themen

[Netzwerkkonnektivität im Microsoft 365 Admin Center (Vorschau)](office-365-network-mac-perf-overview.md)

[Microsoft 365 Einblicke in die Netzwerkleistung (Vorschau)](office-365-network-mac-perf-insights.md)

[Microsoft 365 Netzwerkbewertung (Vorschau)](office-365-network-mac-perf-score.md)

[Microsoft 365 Network Connectivity Location Services (Vorschau)](office-365-network-mac-location-services.md)