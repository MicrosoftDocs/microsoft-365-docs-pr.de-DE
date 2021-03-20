---
title: Networking up (to the cloud) – Der Standpunkt eines Architekten
description: Erfahren Sie, wie Sie Ihr Netzwerk für die Cloudkonnektivität optimieren, indem Sie die häufigsten Fallstricke vermeiden.
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
ms.custom: ''
f1.keywords: NOCSH
ms.openlocfilehash: 7de9aec29b0a57e85e3539fc2e99384de545c52a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904636"
---
# <a name="networking-up-to-the-cloudone-architects-viewpoint"></a>Networking up (to the cloud) – Der Standpunkt eines Architekten

In diesem Artikel beschreibt [Ed Fisher](https://www.linkedin.com/in/edfisher/), Security & Compliance Architect bei Microsoft, wie Sie Ihr Netzwerk für die Cloudkonnektivität optimieren, indem die häufigsten Fallstricke vermieden werden. 

## <a name="about-the-author"></a>Über den Autor

![Ed Fisher-Foto](../media/solutions-architecture-center/ed-fisher-networking.jpg) 

Ich bin derzeit als Principal Technical Specialist in der Region Südost mit dem Schwerpunkt Sicherheit & Compliance. Ich habe mit Kunden zusammengearbeitet, die in den letzten 10 Jahren zu Office 365 um wechselten. Ich habe mit kleineren Geschäften gearbeitet, mit einer Handvoll Standorten für Behörden und Unternehmen mit Millionen von Benutzern, die auf der ganzen Welt verteilt sind, und vielen anderen Kunden dazwischen, mit der Mehrzahl mit Zehntausenden von Benutzern, mehreren Standorten in verschiedenen Teilen der Welt, der Notwendigkeit eines höheren Sicherheitsgrads und einer Vielzahl von Complianceanforderungen. Ich habe Hunderte von Unternehmen und Millionen von Benutzern dabei unterstützt, sicher und sicher in die Cloud zu wechseln.

Mit einem Hintergrund in den letzten 25 Jahren, der Sicherheit, Infrastruktur und Netzwerktechnik umfasst, und nachdem zwei meiner vorherigen Arbeitgeber zu Office 365 umgezogen sind, bevor ich zu Microsoft kam, war ich viele Male auf Ihrer Seite der Tabelle, und denken Sie daran, wie das ist. Obwohl keine zwei Kunden identisch sind, haben die meisten ähnliche Anforderungen, und wenn sie einen standardisierten Dienst wie eine SaaS- oder PaaS-Plattform nutzen, sind die besten Ansätze in der Regel identisch.

## <a name="its-not-the-networkits-how-youre-misusing-it"></a>Es ist nicht das Netzwerk– so verwenden Sie es (falsch)!

Wie oft dies auch geschieht, es überrascht mich  nie, wie kreative Sicherheitsteams und Netzwerkteams versuchen, eine Verbindung mit Microsoft Cloud Services herzustellen. Es gibt immer eine Sicherheitsrichtlinie, einen Compliancestandard oder eine bessere Möglichkeit, die sie verwenden möchten, ohne bereit  zu sein, eine Unterhaltung darüber zu führen, was sie zu erreichen versuchen, oder wie sie besser, einfacher, kostengünstiger und performanter sind.

Wenn mir diese Art von Sache eskaliert wird, bin ich in der Regel bereit, die Herausforderung anzunehmen und sie durch das Wie und das Warum zu gehen und sie an den Ort zu holen, an dem sie sein müssen. Wenn ich jedoch völlig offen bin, muss ich ihnen sagen, dass ich manchmal einfach nur das tun möchte, was sie tun möchten, und dann sagen, dass ich ihnen gesagt habe, dass es nicht funktioniert, wenn sie schließlich einrußen, dass es nicht funktioniert. Ich möchte dies manchmal tun, aber *nicht*. Was ich tun möchte, ist, alles zu erklären, was ich in diesem Beitrag enthalten möchte. Unabhängig von Ihrer Rolle, wenn Ihre Organisation Microsoft-Clouddienste verwenden möchte, gibt es wahrscheinlich eine gewisse Weisheit in den folgenden Informationen, die Ihnen helfen können.

## <a name="guiding-principles"></a>Leitprinzipien

Beginnen wir mit einigen Grundregeln für das, was wir hier tun. Wir besprechen, wie Sie eine sichere Verbindung mit Clouddiensten herstellen können, um die minimale Komplexität und die maximale Leistung zu gewährleisten und gleichzeitig echte Sicherheit zu gewährleisten. Keines der folgenden Folgen steht im Gegengewicht dazu, auch wenn Sie oder Ihr Kunde ihren bevorzugten Proxyserver nicht für alles verwenden können.

- **Nur weil Sie dies können,** bedeutet dies nicht, dass Sie : Oder um Dr. Ian Malcolm aus dem Film "Jurassic Park" zu paraphrasieren... Ja, ja, aber Ihr Sicherheitsteam war so beschäftigt, ob es es konnte oder nicht, dass es nicht aufzuhören, zu überlegen, ob es sollte."
- **Sicherheit bedeutet nicht Komplexität:** Sie sind nicht sicherer, nur weil Sie mehr Geld ausgeben, mehr Geräte durchrouten oder auf weitere Schaltflächen klicken.
- **Auf Office 365 wird** über das Internet zugegriffen: Das ist jedoch nicht dasselbe wie office 365 ist das Internet. Es ist ein von Microsoft verwalteter und von Ihnen verwalteter SaaS-Dienst. Im Gegensatz zu Websites, die Sie im Internet besuchen, können Sie tatsächlich einen Blick hinter den Vorhang werfen und die Steuerelemente anwenden, die Sie benötigen, um Ihre Richtlinien und Compliancestandards zu erfüllen, solange Sie wissen, dass Sie zwar Ihre Ziele erfüllen können, sie aber möglicherweise auf andere Weise tun müssen.
- **Chokepoints** sind schlecht, lokalisierte Brüche sind gut: Jeder möchte immer seinen ganzen Internetdatenverkehr für alle Benutzer an einem zentralen Punkt zurückstellen, in der Regel, damit er ihn überwachen und Richtlinien erzwingen kann, aber oft, weil es entweder günstiger ist als die Bereitstellung des Internetzugriffs an allen Standorten oder einfach nur so. Diese Drosselungen sind jedoch genau dies... Punkt, an denen der Datenverkehr erstickt. Es ist nichts falsch daran, ihre Benutzer daran zu verhindern, zu Instagram zu browsen oder Katzenvideos zu streamen, aber behandeln Sie Ihren geschäftskritischen Anwendungsdatenverkehr nicht auf die gleiche Weise.
- Wenn DNS nicht zufrieden ist, ist **ain't** nothing happy: Das am besten entworfene Netzwerk kann durch schlechtes DNS ge hamstriert werden, sei es durch das Rekursieren von Anforderungen an Server in anderen Bereichen der Welt oder die Verwendung der DNS-Server ihres Internetdienstanbieters oder anderer öffentlicher DNS-Server, die DNS-Auflösungsinformationen zwischenspeichern.
- Nur weil Sie dies früher gemacht haben, bedeutet dies **nicht,** dass Sie dies jetzt tun sollten: Die Technologie ändert sich ständig, und Office 365 ist keine Ausnahme. Die Anwendung von Sicherheitsmaßnahmen, die für lokale Dienste entwickelt und bereitgestellt wurden, oder um das Surfen im Web zu steuern, bietet nicht die gleiche Sicherheitssicherheit und kann sich erheblich negativ auf die Leistung auswirken.
- **Office 365 wurde** für den Zugriff über das Internet erstellt: Das ist es, kurz gesagt. Unabhängig davon, was Sie zwischen Ihren Benutzern und Ihrem Edge tun möchten, wird der Datenverkehr immer noch über das Internet übertragen, sobald er Ihr Netzwerk verlässt und bevor er auf uns zukommt. Auch wenn Sie Azure ExpressRoute verwenden, um einen Teil des latenzempfindlichen Datenverkehrs von Ihrem Netzwerk direkt an uns weiter zu leitet, ist die Internetverbindung absolut erforderlich. Akzeptieren Sie es. Denken Sie nicht darüber nach.

## <a name="where-bad-choices-are-often-made"></a>Wo häufig schlechte Entscheidungen getroffen werden

Es gibt zwar viele Orte, an denen im Namen der Sicherheit schlechte Entscheidungen getroffen werden, aber dies sind diejenigen, die ich am häufigsten mit Kunden stoße. Viele Kundenunterhaltungen umfassen alle diese gleichzeitig.

### <a name="insufficient-resources-at-the-edge"></a>Unzureichende Ressourcen am Rand

Nur sehr wenige Kunden stellen Greenfield-Umgebungen bereit, und sie verfügen über jahrelange Erfahrung mit der Funktionsweise ihrer Benutzer und ihrer Internet-Ausgangsumgebung. Unabhängig davon, ob Kunden über Proxyserver verfügen oder direkten Zugriff zulassen und einfach nat-ausgehenden Datenverkehr zulassen, tun sie dies seit Jahren und überlegen nicht, wie viel mehr sie beginnen, ihren Edge zu durchpumpen, während sie traditionell interne Anwendungen in die Cloud verschieben.

Bandbreite ist immer ein Problem, aber NAT-Geräte verfügen möglicherweise nicht über genügend Leistung, um die erhöhte Last zu bewältigen, und sie können vorzeitig damit beginnen, Verbindungen zu schließen, um Ressourcen frei zu machen. Die meisten Clientsoftware, die eine Verbindung mit Office 365 herstellt, erwartet dauerhafte Verbindungen, und ein Benutzer, der Office 365 vollständig nutzt, kann über 32 oder mehr gleichzeitige Verbindungen verfügen. Wenn das NAT-Gerät sie vorzeitig ablegen, reagieren diese Apps möglicherweise nicht mehr, wenn sie versuchen, die verbindungen zu verwenden, die nicht mehr verfügbar sind. Wenn sie aufgeben und versuchen, neue Verbindungen herzustellen, werden die Netzwerkgeräte noch stärker geladen.

### <a name="localized-breakout"></a>Lokalisierter Breakout

Alles andere in dieser Liste geht auf eine Sache zurück: ihr Netzwerk und unsere so schnell wie möglich zu erreichen. Das Zurückhauen des Datenverkehrs Ihrer Benutzer an einen zentralen Ausgangspunkt, insbesondere wenn sich dieser Ausgangspunkt in einer anderen Region befindet als die Benutzer, führt zu unnötigen Wartezeiten und wirkt sich sowohl auf die Clienterfahrung als auch auf die Downloadgeschwindigkeit aus. Microsoft verfügt über Präsenzpunkte auf der ganzen Welt mit Front-Ends für alle unsere Dienste und  Peering, die mit praktisch jedem wichtigen ISP eingerichtet wurden. Daher wird durch das Routing des Datenverkehrs Ihrer Benutzer lokal sichergestellt, dass der Datenverkehr schnell und mit minimaler Latenz in unser Netzwerk eingespeiert wird.

### <a name="dns-resolution-traffic-should-follow-the-internet-egress-path"></a>DNS-Auflösungsdatenverkehr sollte dem Internet-Ausgangspfad folgen

Damit ein Client einen Endpunkt finden kann, muss er natürlich DNS verwenden. Die DNS-Server von Microsoft werten die Quelle von DNS-Anforderungen aus, um sicherzustellen, dass wir die Antwort zurückgeben, die im Internet der Quelle der Anforderung am nächsten ist. Stellen Sie sicher, dass Ihr DNS so konfiguriert ist, dass Namensauflösungsanforderungen denselben Pfad wie der Datenverkehr Ihrer Benutzer gehen, damit Sie ihnen keinen lokalen Ausweg geben, sondern an einen Endpunkt in einer anderen Region. Dies bedeutet, dass lokale DNS-Server "zum Stamm" wechseln und nicht an DNS-Server in Remotedatencentern weitergeleitet werden. Achten Sie auf öffentliche und private DNS-Dienste, die Ergebnisse aus einem Teil der Welt zwischenspeichern und an Anforderungen aus anderen Teilen der Welt verarbeiten können.

### <a name="to-proxy-or-not-to-proxy-that-is-the-question"></a>Um proxy oder nicht zu proxy, das ist die Frage

Eine der ersten Dinge, die Sie berücksichtigen sollten, ist, ob Die Verbindungen von Benutzern mit Office 365 proxyen werden. Das ist einfach. keinen Proxy verwenden. Auf Office 365 wird über das Internet zugegriffen, es ist jedoch nicht DAS Internet. Es ist eine Erweiterung Ihrer Kerndienste und sollte als solche behandelt werden. Alles, was ein Proxy möglicherweise tun soll, z. B. DLP oder Antischantischung oder Inhaltsuntersuchung, steht Ihnen im Dienst bereits zur Verfügung und kann im Großen und Umfang verwendet werden, ohne dass TLS-verschlüsselte Verbindungen geknackt werden müssen. Wenn Sie den Datenverkehr jedoch wirklich proxyen möchten, den Sie sonst nicht steuern können, achten Sie auf unsere Anleitungen und die Kategorien des Datenverkehrs [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) unter [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) . Wir haben drei Kategorien von Datenverkehr für Office 365. Optimieren und Zulassen sollte wirklich direkt gehen und Ihren Proxy umgehen. Der Standardwert kann proxied sein. Die Details finden Sie in diesen Dokumenten... lesen.

Die meisten Kunden, die darauf bestehen, einen Proxy zu verwenden, wenn sie tatsächlich sehen, was sie tun, werden feststellen, dass der Proxy jetzt nur ein teurer zusätzlicher Router ist, wenn der Client eine HTTP CONNECT-Anforderung an den Proxy stellt. Bei den verwendeten Protokollen wie MAPI und RTC handelt es sich nicht einmal um Protokolle, die Webproxies verstehen. Selbst bei TLS-Cracking erhalten Sie also nicht wirklich zusätzliche Sicherheit. Sie *erhalten* eine zusätzliche Latenz. Weitere Informationen finden Sie unter Optimieren, Zulassen und Standard für [https://aka.ms/pnc](../enterprise/microsoft-365-network-connectivity-principles.md) Microsoft 365-Datenverkehr.

Berücksichtigen Sie schließlich die Gesamtwirkung auf den Proxy und die entsprechende Antwort, um diese Auswirkungen zu berücksichtigen. Da immer mehr Verbindungen über den Proxy hergestellt werden, kann dies den TCP-Skalierungsfaktor verringern, sodass er nicht so viel Datenverkehr puffern muss. Ich habe Kunden gesehen, bei denen ihre Proxys so überlastet waren, dass sie den Skalierungsfaktor 0 verwendeten. Da der Skalierungsfaktor ein exponentieller Wert ist und wir gerne 8 verwenden, hat jede Reduzierung des Skalierungsfaktors einen großen negativen Einfluss auf den Durchsatz.

TLS-Überprüfung bedeutet SICHERHEIT! Aber nicht wirklich! Viele Kunden mit Proxys möchten sie verwenden, um den datenverkehr zu überprüfen, was bedeutet, dass TLS "Unterbrechung und Überprüfung" bedeutet. Wenn Sie dies für eine Website tun, auf die über HTTPS zugegriffen wird (ungeachtet von Datenschutzbedenken), muss Ihr Proxy dies möglicherweise für 10 oder sogar 20 gleichzeitige Datenströme für ein paar hundert Millisekunden tun. Wenn es einen großen Download oder möglicherweise ein Video gibt, kann eine oder mehrere dieser Verbindungen viel länger dauern, aber insgesamt können die meisten dieser Verbindungen sehr schnell herstellen, übertragen und schließen. Das Tun von Unterbrechung und Überprüfung bedeutet, dass der Proxy die doppelte Arbeit tun muss. Für jede Verbindung vom Client zum Proxy muss der Proxy auch eine separate Verbindung mit dem Endpunkt herstellen. 1 wird also 2, 2 wird 4, 32 wird 64...siehe wohin ich gehe? Wahrscheinlich haben Sie die Größe Ihrer Proxylösung für typische Websurfings genau so dimensioniert, aber wenn Sie versuchen, dasselbe für Clientverbindungen mit Office 365 zu tun, ist die Anzahl gleichzeitiger, langlebiger Verbindungen möglicherweise um eine Größenordnung größer als die Größe, für die Sie die Größe haben.

### <a name="streaming-isnt-important-except-that-it-is"></a>Streaming ist nicht wichtig, es sei denn, es *ist*

Die einzigen Dienste in Office 365, die UDP verwenden, sind Skype (bald eingestellt) und Microsoft Teams. Teams verwendet UDP für Streamingdatenverkehr, einschließlich Audio-, Video- und Präsentationsfreigabe. Streamingdatenverkehr ist live, z. B. wenn Sie eine Onlinebesprechung mit Sprach-, Video- und Präsentationsdecks haben oder Demos durchführen. Diese verwenden UDP, da Pakete, wenn Pakete verworfen werden oder nicht mehr in der Reihenfolge ankommen, für den Benutzer praktisch nicht lesbar sind und der Datenstrom einfach weiter gehen kann.

Wenn Sie ausgehenden UDP-Datenverkehr von Clients an den Dienst nicht zulassen, können sie auf TCP zurückfallen. Wenn jedoch ein TCP-Paket gelöscht *wird,* wird alles angehalten, bis das Timeout für die Erneute Übertragung (Retransmission Timeout, RTO) abläuft und das fehlende Paket erneut übertragen werden kann. Wenn ein Paket nicht mehr in ordnung kommt, wird alles angehalten, bis die anderen Pakete eintreffen und in der Reihenfolge neu zusammengehören können. Beides führt zu wahrnehmbaren Störungen im Audio (denken Sie an Max Headroom?) und Video (haben Sie auf etwas geklickt... Oh, gibt es) und führen zu schlechter Leistung und schlechter Benutzererfahrung. Und denken Sie daran, was ich oben über Proxys oben gesagt habe? Wenn Sie erzwingen, dass ein Teams-Client einen Proxy verwendet, erzwingen Sie die Verwendung von TCP. Jetzt verursachen Sie also zweimal negative Leistungsauswirkungen.

### <a name="split-tunneling-may-seem-scary"></a>Split tunneling may seem scary

Aber nicht. Alle Verbindungen mit Office 365 sind über TLS. Wir bieten TLS 1.2 bereits seit einer Weile an und werden ältere Versionen bald deaktivieren, da ältere Clients sie weiterhin verwenden und dies ein Risiko ist.

Wenn Sie eine TLS-Verbindung oder 32 davon erzwingen, über ein VPN zu wechseln, bevor sie dann zum Dienst wechseln, wird keine Sicherheit hinzugefügt. Es erhöht die Latenz und reduziert den Gesamtdurchsatz. In einigen VPN-Lösungen erzwingt dies sogar den Tunnel durch TCP, was wiederum sehr negative Auswirkungen auf den Streamingdatenverkehr hat. Und wenn Sie keine TLS-Überprüfung machen, gibt es keine Nachteile, alle Nachteile. Ein sehr häufiges Thema bei Kunden, da die meisten Ihrer Mitarbeiter remote arbeiten, ist, dass sie erhebliche Bandbreiten- und Leistungsauswirkungen sehen, indem sie alle Ihre Benutzer über ein VPN verbinden, anstatt split tunneling für den Zugriff auf Die Kategorie Optimieren von [Office 365-Endpunkten](../enterprise/microsoft-365-network-connectivity-principles.md#new-office-365-endpoint-categories)zu konfigurieren.

Es ist eine einfache Lösung, geteiltes Tunneln zu tun, und dies sollten Sie tun. Weitere Informationen finden Sie unter [Optimize Office 365 connectivity for remote users using VPN split tunneling](../enterprise/microsoft-365-vpn-split-tunnel.md).

## <a name="the-sins-of-the-past"></a>Die Unfünde der Vergangenheit

Viele Male werden schlechte Entscheidungen getroffen, weil (1) nicht weiß, wie der Dienst funktioniert, (2) versucht, unternehmensrichtlinien einzuhalten, die vor der Einführung der Cloud geschrieben wurden, und (3) Sicherheitsteams, die möglicherweise nicht leicht davon überzeugt sind, dass es mehr als eine Möglichkeit gibt, ihre Ziele zu erreichen. Hoffentlich helfen die obigen und die unten stehenden Links bei der ersten. Das Sponsoring von Führungskräften kann erforderlich sein, um den zweiten Schritt zu überkraften. Das Erreichen der Ziele der Sicherheitsrichtlinien anstelle ihrer Methoden hilft beim dritten. Von bedingtem Zugriff auf Inhaltsmoderation, DLP über Informationsschutz, Endpunktüberprüfung bis zu Zero-Day-Bedrohungen – jedes Endziel, das eine angemessene Sicherheitsrichtlinie möglicherweise erreicht hat, kann mit den verfügbaren Informationen in Office 365 und ohne Abhängigkeit von lokalen Netzwerkgeräten, erzwungenen VPN-Tunneln und TLS-Unterbrechungen und -Überprüfungen erreicht werden.

In anderen Zeiten kann die Hardware, die vor dem Wechsel der Organisation in die Cloud dimensioniert und erworben wurde, einfach nicht skaliert werden, um die neuen Datenverkehrsmuster und -lasten zu verarbeiten. Wenn Sie wirklich den ganzen Datenverkehr über einen einzelnen Ausgangspunkt routen und/oder ihn proxyen müssen, müssen Sie darauf vorbereitet sein, Netzwerkgeräte und Bandbreite entsprechend zu aktualisieren. Überwachen Sie die Auslastung für beides sorgfältig, da die Benutzererfahrung nicht langsam abnimmt, wenn sich mehr Benutzer integrieren. Alles ist in Ordnung, bis der Kipppunkt erreicht ist, dann leidet jeder.

## <a name="exceptions-to-the-rules"></a>Ausnahmen von den Regeln

Wenn Für Ihre Organisation Mandanteneinschränkungen erforderlich [sind,](/azure/active-directory/manage-apps/tenant-restrictions)müssen Sie einen Proxy mit TLS-Unterbrechung und -Überprüfung verwenden, um einen bestimmten Datenverkehr über den Proxy zu erzwingen. Sie müssen jedoch nicht den ganzen Datenverkehr durch den Proxy erzwingen.  Es ist kein Alles- oder Nichts-Vorschlag, achten Sie also darauf, was vom Proxy geändert werden muss.

Wenn Sie geteiltes Tunneln zulassen, aber auch einen Proxy für den allgemeinen Webdatenverkehr verwenden möchten, müssen Sie sicherstellen, dass ihre PAC-Datei definiert, was direkt ausgeführt werden muss, und wie Sie interessanten Datenverkehr für den VPN-Tunnel definieren. Wir bieten Beispiele für [https://aka.ms/ipaddrs](../enterprise/urls-and-ip-address-ranges.md) PAC-Dateien an, die die Verwaltung vereinfachen.

## <a name="conclusion"></a>Schlussbemerkung

Zehntausende organisationen, einschließlich fast aller Fortune 500, verwenden Office 365 täglich für ihre wichtigen Funktionen. Sie tun dies sicher, und dies über das Internet.

Unabhängig von ihren Sicherheitszielen gibt es Möglichkeiten, sie zu erreichen, die keine VPN-Verbindungen, Proxyserver, TLS-Unterbrechungen und -Überprüfungen oder zentralisierten Internet-Ableitungen erfordern, um den Datenverkehr Ihrer Benutzer so schnell wie möglich von Ihrem Netzwerk und von uns zu erhalten. Dies bietet die beste Leistung, unabhängig davon, ob Ihr Netzwerk die Unternehmenszentrale, ein Remotebüro ist. , oder der Benutzer, der zu Hause arbeitet. Unsere Anleitung basiert darauf, wie die Office 365-Dienste erstellt werden und um eine sichere und performante Benutzeroberfläche sicherzustellen.

## <a name="further-reading"></a>Weitere Informationen

[Die Office 365 Network Connectivity Principles](../enterprise/microsoft-365-network-connectivity-principles.md)

[URLs und IP-Adressbereiche für Office 365](../enterprise/urls-and-ip-address-ranges.md)

[Verwalten von Office 365-Endpunkten](../enterprise/managing-office-365-endpoints.md)

[Office 365 – IP-Adress- und URL-Webdienst](../enterprise/microsoft-365-ip-web-service.md)

[Bewerten der Office 365-Netzwerkkonnektivität](../enterprise/assessing-network-connectivity.md)

[Office 365-Netzwerk- und Leistungsoptimierung](../enterprise/network-planning-and-performance.md)

[Bewerten der Office 365-Netzwerkkonnektivität](../enterprise/assessing-network-connectivity.md)

[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](../enterprise/performance-tuning-using-baselines-and-history.md)

[Plan zur Problembehandlung für Office 365](../enterprise/performance-troubleshooting-plan.md)

[Netzwerke für die Inhaltsübermittlung](../enterprise/content-delivery-networks.md)

[Microsoft 365-Konnektivitätstest](https://connectivity.office.com/)

[So erstellt Microsoft sein schnelles und zuverlässiges globales Netzwerk](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/)

[Office 365-Networking-Blog](https://techcommunity.microsoft.com/t5/office-365-networking/bd-p/Office365Networking)

[Office 365-Konnektivität für Remotebenutzer mithilfe von geteilten VPN-Tunneln](../enterprise/microsoft-365-vpn-split-tunnel.md)