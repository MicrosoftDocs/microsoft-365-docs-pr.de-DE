---
title: Vernetzen (zur Cloud) – ein Architektur Standpunkt
description: Eine Beschreibung.
ms.author: bcarter
author: brendacarter
manager: bcarter
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- M365solutions
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: c8b8416b276ce0e5335b0c0193c6cd79a81d7959
ms.sourcegitcommit: a418195dc11e6251ae37e788c102bbaa7087e44e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2020
ms.locfileid: "44581586"
---
# <a name="networking-up-to-the-cloud--one-architects-viewpoint"></a>Vernetzen (zur Cloud) – ein Architektur Standpunkt

In diesem Artikel wird von [Ed Fisher](https://www.linkedin.com/in/edfisher/), Security & Compliance Architect bei Microsoft, beschrieben, wie Sie Ihr Netzwerk für die Cloud-Konnektivität optimieren, indem Sie die häufigsten Fallstricke vermeiden. 

## <a name="about-the-author"></a>Über den Autor

![Ed Fisher-Foto](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Ich bin derzeit ein technischer Hauptspezialist in der Südostregion mit Schwerpunkt auf Sicherheit & Compliance. Ich habe mit Kunden zusammengearbeitet, die sich in den letzten zehn Jahren in Office 365 bewegt haben. Ich habe mit kleineren Shops mit einer Handvoll von Standorten an Behörden und Unternehmen mit Millionen von Benutzern, die auf der ganzen Welt verteilt sind, und vielen anderen Kunden dazwischen gearbeitet, wobei die Mehrheit Zehntausende von Benutzern, mehrere Standorte in verschiedenen Teilen der Welt, ein höheres Maß an Sicherheit und eine Vielzahl von Compliance-Anforderungen benötigt. Ich habe dazu beigetragen, dass Hunderte von Unternehmen und Millionen von Benutzern sicher und sicher in die Cloud umsteigen.

Mit einem Hintergrund in den letzten 25 Jahren, der Sicherheit, Infrastruktur und Netzwerktechnik umfasst und zwei meiner vorherigen Arbeitgeber zu Office 365 verschoben hat, bevor ich zu Microsoft kam, habe ich viele Male auf Ihrer Seite des Tables gearbeitet und erinnere mich daran, wie das ist. Während keine zwei Kunden gleich sind, haben die meisten ähnliche Anforderungen, und wenn Sie einen standardisierten Dienst wie jede SaaS-oder PaaS-Plattform nutzen, sind die besten Ansätze in der Regel gleich.



## <a name="its-not-the-network--its-how-youre-misusing-it"></a>Es ist nicht das Netzwerk-es ist, wie Sie (MIS) mit IT!

Unabhängig davon, wie oft es passiert, erstaunt es nie, wie *kreativ* Sicherheitsteams und Netzwerkteams versuchen, zu erfahren, wie Sie denken, dass Sie eine Verbindung mit Microsoft Cloud Services herstellen sollten. Es gibt immer einige Sicherheitsrichtlinien, Kompatibilitätsstandards oder bessere voraus setendungen für die Verwendung von, ohne dass Sie bereit sind, eine Unterhaltung darüber zu führen, was Sie zu erreichen versuchen, oder *wie* Sie besser, einfacher, kostengünstiger und leistungsfähiger Vorgehen. 

Wenn diese Art der Sache an mich eskaliert wird, bin ich normalerweise bereit, die Herausforderung zu ergreifen und Sie durch das hows und das Warum zu führen und Sie dorthin zu bringen, wo Sie sein müssen. Aber wenn ich ganz offen bin, muss ich teilen, dass ich manchmal möchte, dass Sie das tun, was Sie tun, und wieder zu sagen, dass ich Ihnen gesagt, wenn Sie schließlich zugeben, dass es nicht funktioniert. Ich möchte vielleicht manchmal tun, aber ich *weiß nicht*. Was ich tue, ist zu versuchen, all das zu erklären, was ich in diesen Beitrag einbeziehen werde. Unabhängig von ihrer Rolle, wenn Ihre Organisation Microsoft Cloud Services verwenden möchte, gibt es wahrscheinlich einige Weisheiten, die Ihnen helfen können.


## <a name="guiding-principles"></a>Leitlinien
Beginnen wir mit einigen Grundregeln rund um das, was wir hier tun. In diesem Artikel wird erläutert, wie eine sichere Verbindung mit Cloud-Diensten hergestellt werden kann, um die minimale Komplexität und maximale Leistung zu gewährleisten und gleichzeitig echte Sicherheit sicherzustellen. Keines von dem, was folgt, ist gegen jede dieser, auch wenn Sie oder Ihr Kunde, wird nicht erhalten, um Ihren bevorzugten Proxy Server für alles verwenden.

- **Nur weil Sie es können, bedeutet nicht, dass Sie** -oder Dr. Ian Malcolm aus dem Jurassic Park-Film in Anlehnung schreiben sollten. " . . Ja, ja, aber Ihr Sicherheitsteam war so beschäftigt, dass Sie nicht angehalten haben, zu überlegen, ob Sie es sollten. "    
- **Sicherheit bedeutet nicht die Komplexität** – Sie sind nicht sicherer, nur weil Sie mehr Geld ausgeben, mehr Geräte weiterleiten oder auf weitere Schaltflächen klicken.
- **Auf Office 365 wird über das Internet zugegriffen** – aber das ist nicht dasselbe wie Office 365 das Internet ist. Es handelt sich dabei um einen SaaS-Dienst, der von Microsoft verwaltet und von Ihnen administriert wird. Im Gegensatz zu Websites, die Sie im Internet besuchen, erhalten Sie tatsächlich einen Blick hinter den Vorhang und können die Steuerelemente anwenden, die Sie benötigen, um Ihre Richtlinien und Konformitätsstandards zu erfüllen, solange Sie verstehen, dass Sie Ihre Ziele möglicherweise nur auf andere Weise erfüllen müssen.
- **Engpässe sind schlecht, lokalisierte Ausbrüche sind gut** – jeder möchte immer den gesamten Internetdatenverkehr für alle Benutzer an einen zentralen Punkt Backhaul, in der Regel, um ihn zu überwachen und Richtlinien zu erzwingen, aber oft, weil er entweder billiger ist als die Bereitstellung des Internetzugriffs an allen Standorten, oder nur, wie er es tut. Aber diese Engpässe sind genau das... Punkte, an denen der Datenverkehr erstickt. Es ist nichts falsch daran, dass Ihre Benutzer nicht auf Instagram oder Streaming von Cat-Videos Browsen, sondern den geschäftskritischen Anwendungsdatenverkehr auf die gleiche Weise behandeln.
- **Wenn DNS nicht glücklich ist, gibt es nichts glückliches** – das am besten entwickelte Netzwerk kann von einem schlechten DNS-gelähmt werden, unabhängig davon, ob Anforderungen an Server in anderen Bereichen der Welt zurückgekehrt werden oder die DNS-Server Ihres ISP oder andere öffentliche DNS-Server verwendet werden, die DNS-Auflösungsinformationen Zwischenspeichern. 
- **Nur weil Sie es früher getan haben, bedeutet das nicht, dass Sie es jetzt tun sollten** – Technologie ändert sich ständig, und Office 365 ist keine Ausnahme. Das Anwenden von Sicherheitsmaßnahmen, die für lokale Dienste entwickelt und bereitgestellt wurden, oder das Surfen im Internet zu steuern, bietet nicht dasselbe Maß an Sicherheits Zusicherung und kann sich erheblich negativ auf die Leistung auswirken.
- **Office 365 wurde für den Zugriff über das Internet entwickelt** – ganz kurz. Unabhängig davon, was Sie zwischen Ihren Benutzern und Ihrem Edge durchführen möchten, der Datenverkehr geht noch immer über das Internet, sobald das Netzwerk verlassen wird und bevor es auf unser Gerät gelangt. Selbst wenn Sie Azure Express Route verwenden, um einige Latenz sensiblen Datenverkehr aus Ihrem Netzwerk direkt zu unserem weiterzuleiten, ist eine Internet Verbindung absolut erforderlich. Akzeptieren. Überdenken Sie das nicht.

## <a name="where-bad-choices-are-often-made"></a>Bei denen häufig falsche Entscheidungen getroffen werden

Es gibt zwar viele Orte, an denen schlechte Entscheidungen im Namen der Sicherheit getroffen werden, aber diese sind die, denen ich am häufigsten bei Kunden begegne. In vielen Kundengesprächen werden alle diese gleichzeitig einbezogen.

### <a name="insufficient-resources-at-the-edge"></a>Unzureichende Ressourcen am Rand
Nur wenige Kunden bieten Greenfield-Umgebungen an, und Sie verfügen über jahrelange Erfahrung mit der Funktionsweise der Benutzer und der Art und Weise, wie Ihr Internet Ausstieg aussieht. Unabhängig davon, ob Kunden über Proxy Server verfügen oder direkten Zugriff und einfachen NAT-ausgehenden Datenverkehr zulassen, sind Sie seit Jahren dabei und berücksichtigen nicht, wie viel mehr Sie mit der Verlagerung von herkömmlichen internen Anwendungen in die Cloud beginnen.

Bandbreite ist immer ein Problem, aber NAT-Geräte verfügen möglicherweise nicht über genügend PS, um die erhöhte Last zu verarbeiten, und beginnen möglicherweise vorzeitiges schließen von Verbindungen, um Ressourcen freizugeben. Der Großteil der Client Software, die eine Verbindung mit Office 365 herstellt, erwartet persistente Verbindungen, und ein Benutzer, der Office 365 vollständig nutzt, verfügt möglicherweise über 32 oder mehr gleichzeitige Verbindungen. Wenn das NAT-Gerät Sie vorzeitig ablässt, werden diese apps möglicherweise nicht mehr reagiert, wenn Sie versuchen, die Verbindungen zu verwenden, die nicht mehr vorhanden sind. Wenn Sie aufgeben und versuchen, neue Verbindungen herzustellen, stellen Sie noch mehr Last auf Ihrem Netzwerkgerät.

### <a name="localized-breakout"></a>Lokalisierter Ausbruch
Alles andere in dieser Liste ist auf eine Sache beschränkt: Wenn Sie Ihr Netzwerk und unser System so schnell wie möglich aussteigen. Das Durchlaufen des Datenverkehrs Ihrer Benutzer an einen zentralen Ausgangspunkt, vor allem, wenn sich dieser Ausgangspunkt in einer anderen Region befindet als die Benutzer, führt zu unnötiger Wartezeit und wirkt sich sowohl auf die Clientumgebung als auch auf die Downloadgeschwindigkeit aus. Microsoft hat überall in der Welt Präsenzpunkte mit Front-Ends für alle unsere Dienste und Peering, die mit praktisch jedem wichtigen ISP eingerichtet wurden, sodass der Datenverkehr Ihrer Benutzer *lokal* mit minimaler Wartezeit schnell in unser Netzwerk gelangt. 

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS-Auflösungs Datenverkehr sollte dem Internet Ausgangspfad entsprechen
Damit ein Client einen beliebigen Endpunkt findet, muss er natürlich DNS verwenden. Die DNS-Server von Microsoft bewerten die Quelle von DNS-Anforderungen, um sicherzustellen, dass die Antwort im Internet ausgedrückt wird, die der Quelle der Anforderung am nächsten ist. Stellen Sie sicher, dass Ihr DNS so konfiguriert ist, dass Namensauflösungsanforderungen denselben Pfad wie der Datenverkehr Ihrer Benutzer ausgehen, damit Sie Ihnen keinen lokalen Ausgang, sondern einen Endpunkt in einer anderen Region geben. Das bedeutet, dass lokale DNS-Server "in den Stamm wechseln" statt an DNS-Server in Remote-Rechenzentren weitergeleitet werden. Und achten Sie auf öffentliche und private DNS-Dienste, die Ergebnisse aus einem Teil der Welt Zwischenspeichern und für Anfragen aus anderen Teilen der Welt verarbeiten können.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>An Proxy oder nicht an Proxy, das ist die Frage
Eines der ersten Punkte, die Sie beachten sollten, ist, ob die Verbindungen von Benutzern zu Office 365 hergestellt werden sollen. Das ist einfach; kein Proxy. Auf Office 365 wird über das Internet zugegriffen, aber es handelt sich nicht um das Internet. Es handelt sich um eine Erweiterung ihrer Kerndienste, die als solche behandelt werden sollte. Alles, was Sie vielleicht für einen Proxy verwenden möchten, wie etwa DLP oder Antischadsoftware oder Inhaltsüberprüfung, steht Ihnen bereits im Dienst zur Verfügung und kann im Maßstab verwendet werden, ohne dass TLS-verschlüsselte Verbindungen geknackt werden müssen. Wenn Sie jedoch den Datenverkehr, den Sie nicht anderweitig steuern können, wirklich proxyieren möchten, achten Sie auf unsere Anweisungen unter [https://aka.ms/pnc](https://aka.ms/pnc) und die Kategorien des Datenverkehrs unter [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) . Für Office 365 gibt es drei Kategorien von Datenverkehr. Optimieren und zulassen sollte wirklich direkt gehen und den Proxy umgehen. Standardmäßig kann ein Proxy weitergeleitet werden. Die Details befinden sich in diesen Dokumenten. . . Lesen Sie diese.

Die meisten Kunden, die auf der Verwendung eines Proxys beharren, wenn Sie tatsächlich sehen, was Sie tun, erkennen, dass der Proxy, wenn der Client eine HTTP CONNECT-Anforderung an den Proxy sendet, jetzt nur ein teurer zusätzlicher Router ist. Bei den verwendeten Protokollen wie MAPI und RTC handelt es sich nicht einmal um Protokolle, die von Webproxys verstanden werden, sodass Sie auch bei TLS-Cracks nicht wirklich zusätzliche Sicherheit erhalten. Es *wird* eine zusätzliche Wartezeit abgerufen. Weitere Informationen hierzu [https://aka.ms/pnc](https://aka.ms/pnc) , einschließlich der Kategorien Optimize, allow und Default für den Datenverkehr von Microsoft 365.

Schließlich sollten Sie die Gesamtauswirkung auf den Proxy und die entsprechende Antwort zur Behandlung dieser Auswirkungen überprüfen. Da immer mehr Verbindungen über den Proxy vorgenommen werden, kann der TCP-Skalierungsfaktor verringert werden, damit er nicht so viel Datenverkehr Puffern muss. Ich habe Kunden gesehen, bei denen Ihre Proxies so überladen waren, dass Sie einen Skalierungsfaktor von 0 verwendeten. Da der Skalierungsfaktor ein exponentieller Wert ist und wir gerne 8 verwenden, ist jede Verringerung des Skalierungsfaktors ein enormer negativer Einfluss auf die Durchsatzleistung.

TLS-Inspektion bedeutet Sicherheit! Aber nicht wirklich! Viele Kunden mit Proxies möchten Sie verwenden, um den gesamten Datenverkehr zu überprüfen, und das bedeutet, dass TLS "unterbrechen und inspizieren". Wenn Sie dies für eine Website tun, auf die über HTTPS zugegriffen wird (ungeachtet der Datenschutzbelange), muss Ihr Proxy möglicherweise zehn oder sogar zwanzig gleichzeitige Streams für einige hundert Millisekunden ausführen. Wenn es einen großen Download oder vielleicht ein Video gibt, können eine oder mehrere dieser Verbindungen viel länger dauern, aber insgesamt werden die meisten dieser Verbindungen sehr schnell hergestellt, übertragen und geschlossen. Das Ausführen von Break and Inspect bedeutet, dass der Proxy die Arbeit verdoppeln muss. Für jede Verbindung zwischen dem Client und dem Proxy muss der Proxy auch eine separate Verbindung zurück zum Endpunkt herstellen. So wird man zwei, zwei wird vier, 32 wird 64. . . sehen Sie, wohin ich gehe? Sie haben wahrscheinlich die Größe Ihrer Proxy Lösung für das typische Websurfen gut gemacht, aber wenn Sie versuchen, dasselbe für Clientverbindungen zu Office 365 zu tun, kann die Anzahl gleichzeitiger, langlebiger Verbindungen eine Größenordnung größer sein als die Größe, für die Sie sich für die Größe auszahlen.

### <a name="streaming-isnt-important-except-that-it-is"></a>Streaming ist nicht wichtig, es sei denn, es *ist*
Die einzigen Dienste in Office 365, die UDP verwenden, sind Skype (bald im Ruhestand) und Microsoft Teams. Microsoft Teams verwendet UDP für Streaming-Datenverkehr, einschließlich Audio-, Video-und Präsentations Freigaben. Streaming-Datenverkehr ist Live, beispielsweise wenn Sie eine Onlinebesprechung mit sprach-, Video-und Präsentationsplattformen oder Demos durchführen. Diese verwenden UDP, weil, wenn Pakete gelöscht werden oder nicht in der richtigen Reihenfolge ankommen, es vom Benutzer praktisch unauffällig ist und der Datenstrom einfach weiter gehen kann. 

Wenn Sie ausgehenden UDP-Datenverkehr von Clients an den Dienst nicht zulassen, können Sie auf die Verwendung von TCP zurückgreifen. Wenn jedoch ein TCP-Paket gelöscht wird, wird *alles angehalten* , bis das Timeout für die erneute Übertragung (RTO) abgelaufen ist und das fehlende Paket erneut übertragen werden kann. Wenn ein Paket nicht ordnungsgemäß eingeht, wird alles angehalten, bis die anderen Pakete eintreffen und in der richtigen Reihenfolge wieder zusammengesetzt werden können. Beide führen zu spürbaren Störschüben in den Audiodaten (maximale Kopffreiheit speichern?) und Video (haben Sie auf SOMETH. . . Oh, da ist es) und führt zu schlechter Leistung und einer schlechten Benutzererfahrung. Und denken Sie daran, was ich oben über Proxies aufgestellt habe? Wenn Sie einen Microsoft Teams-Client für die Verwendung eines Proxys zwingen, erzwingen Sie die Verwendung von TCP. Jetzt verursachen Sie zwei mal negative Leistungseinbußen.

### <a name="split-tunneling-may-seem-scary"></a>Split-Tunneling mag beängstigend erscheinen
Dies ist jedoch nicht der Fall. Alle Verbindungen mit Office 365 über TLS. Seit langem bieten wir TLS 1,2 an und werden ältere Versionen bald deaktivieren, da Sie von älteren Clients weiterhin verwendet werden und das ein Risiko darstellt.

Wenn Sie eine TLS-Verbindung oder 32 von diesen erzwingen, um über ein VPN zu wechseln, bevor Sie dann zu dem Dienst wechseln, wird keine Sicherheit hinzugefügt. Dadurch wird Latenz hinzugefügt, und der Gesamtdurchsatz wird reduziert. In einigen VPN-Lösungen wird UDP sogar dazu gezwungen, über TCP zu Tunneln, was sich wiederum sehr negativ auf den Streaming-Datenverkehr auswirkt. Und, es sei denn, Sie tun TLS-Inspektion, gibt es keinen Kopf, alle Nachteile. Ein sehr häufiges Thema bei den Kunden, jetzt, da die meisten ihrer Mitarbeiter Remote sind, ist, dass Sie erhebliche Bandbreiten-und Leistungseinbußen feststellen, dass alle Ihre Benutzer eine Verbindung über ein VPN herstellen, anstatt den geteilten Tunnel für den Zugriff zur [Optimierung der Kategorie Office 365 Endpunkten](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles#new-office-365-endpoint-categories)zu konfigurieren.

Es ist eine einfache Lösung, um Split-Tunneling durchführen, und es ist eine, die Sie tun sollten. Weitere Informationen finden Sie unter Überprüfen der [Optimierung Office 365 Konnektivität für Remotebenutzer mithilfe des VPN-Split-Tunnelings](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel).


## <a name="the-sins-of-the-past"></a>Die Sünden der Vergangenheit
Viele Male ist der Grund, warum schlechte Entscheidungen getroffen werden, aus einer Kombination von (1) nicht zu wissen, wie der Dienst funktioniert, (2) der Versuch, sich an Unternehmensrichtlinien zu halten, die vor der Cloud geschrieben wurden, und (3) Sicherheitsteams, die möglicherweise nicht leicht davon überzeugt sind, dass es mehr als einen Weg gibt, ihre Ziele zu erreichen. Ich hoffe, dass die oben und die Links unten, wird mit der ersten Hilfe. Das Sponsoring von Führungskräften kann erforderlich sein, um die zweite Vergangenheit zu erhalten. Das adressieren der Ziele der Sicherheitsrichtlinien und nicht ihrer Methoden hilft bei der dritten. Von bedingtem Zugriff auf Inhaltsmoderation, DLP zum Informationsschutz, Endpunkt Überprüfung bis hin zu Zero-Day-Bedrohungen – jedes Endziel, das eine angemessene Sicherheitsrichtlinie aufweisen kann, kann mit den verfügbaren Informationen in Office 365 und ohne Abhängigkeit von lokalen Netzwerken, erzwungenen VPN-Tunneln und TLS-Unterbrechung und-Inspektion erreicht werden. 

Andere Zeiten, Hardware, die Größe und erworben wurde, bevor die Organisation mit dem Wechsel in die Cloud gestartet wurde, kann einfach nicht skaliert werden, um die neuen Datenverkehrsmuster und Lasten zu verarbeiten. Wenn Sie den gesamten Datenverkehr über einen einzelnen Ausgangspunkte weiterleiten und/oder Proxy stellen müssen, sollten Sie bereit sein, Netzwerkgeräte und Bandbreite entsprechend zu aktualisieren. Überwachen Sie die Nutzung sorgfältig auf beiden Seiten, da die Benutzerfreundlichkeit nicht mehr so langsam abnimmt, wie bei mehr Benutzern Onboard. Alles ist in Ordnung, bis der Wendepunkte erreicht ist, dann leidet jeder. 

## <a name="exceptions-to-the-rules"></a>Ausnahmen von den Regeln

Wenn Ihre Organisation [Mandanten Beschränkungen](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions)erfordert, müssen Sie einen Proxy mit TLS-Unterbrechung und Überprüfung verwenden, um einen bestimmten Datenverkehr über den Proxy zu erzwingen, aber Sie müssen nicht den gesamten Datenverkehr erzwingen.  Es handelt sich nicht um einen ganz oder gar keinen Vorschlag, achten Sie also darauf, was durch den Proxy geändert werden muss. 

Wenn Sie Split-Tunneling zulassen, aber auch einen Proxy für den allgemeinen Webdatenverkehr verwenden möchten, stellen Sie sicher, dass Ihre PAC-Datei definiert, was direkt sein muss, und wie Sie interessanten Datenverkehr für die Vorgänge definieren, die über den VPN-Tunnel durchlaufen werden. Wir bieten Beispiel-PAC-Dateien an [https://aka.ms/ipaddrs](https://aka.ms/ipaddrs) , die die Verwaltung vereinfachen.

## <a name="conclusion"></a>Schlussbemerkung

Zehntausende von Organisationen, darunter fast alle Fortune 500, verwenden Office 365 Alltag für Ihre geschäftskritischen Funktionen. Sie tun dies sicher und über das Internet.

 Unabhängig davon, welche Sicherheitsziele Sie im Spiel haben, gibt es Möglichkeiten, um diese zu erreichen, die keine VPN-Verbindungen, Proxy Server, TLS-unterbrechungs-und-Inspektionen oder zentralisierten Internet Ausstieg erfordern, um den Datenverkehr Ihrer Benutzer so schnell wie möglich von Ihrem Netzwerk aus zu erhalten, was die beste Leistung bietet, unabhängig davon, ob Ihr Netzwerk die Unternehmenszentrale, ein Remote oder der Benutzer, der zu Hause arbeitet. Unser Leitfaden basiert auf der Art und Weise, wie die Office 365-Dienste erstellt werden, und um eine sichere und leistungsorientierte Benutzeroberfläche sicherzustellen.

## <a name="further-reading"></a>Weiterführende Literatur

[Die Office 365 Prinzipien für die Netzwerkkonnektivität](https://docs.microsoft.com/office365/enterprise/office-365-network-connectivity-principles)

[URLs und IP-Adressbereiche für Office 365](https://docs.microsoft.com/office365/enterprise/urls-and-ip-address-ranges?redirectSourcePath=%252fen-us%252farticle%252fOffice-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Verwalten von Office 365-Endpunkten](https://docs.microsoft.com/office365/enterprise/managing-office-365-endpoints)

[Office 365 – IP-Adress- und URL-Webdienst](https://docs.microsoft.com/office365/enterprise/office-365-ip-web-service)

[Bewerten der Office 365-Netzwerkkonnektivität](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity)

[Office 365-Netzwerk- und Leistungsoptimierung](https://docs.microsoft.com/office365/enterprise/network-planning-and-performance)

[Bewerten der Office 365-Netzwerkkonnektivität](https://docs.microsoft.com/office365/enterprise/assessing-network-connectivity)

[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](https://docs.microsoft.com/office365/enterprise/performance-tuning-using-baselines-and-history)

[Plan zur Problembehandlung für Office 365](https://docs.microsoft.com/office365/enterprise/performance-troubleshooting-plan)

[Netzwerke für die Inhaltsübermittlung](https://docs.microsoft.com/office365/enterprise/content-delivery-networks)

[Microsoft 365-Konnektivitätstest](https://connectivity.office.com/)

[So erstellt Microsoft sein schnelles und zuverlässiges globales Netzwerk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365-Networking-Blog](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365 Konnektivität für Remotebenutzer mit VPN-Split-Tunneling](https://docs.microsoft.com/office365/enterprise/office-365-vpn-split-tunnel)


