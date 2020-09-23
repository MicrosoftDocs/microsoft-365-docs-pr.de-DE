---
title: Implementieren eines geteilten VPN-Tunnels für Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 9/22/2020
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: Implementierung von VPN-Split-Tunneling für Office 365
ms.openlocfilehash: af5c2ea35df921abe8eaa9a85ab2ab244931c098
ms.sourcegitcommit: 4ee683c18442386f6fc5c76ffabfad2c28b81d42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/23/2020
ms.locfileid: "48214878"
---
# <a name="implementing-vpn-split-tunneling-for-office-365"></a>Implementieren eines geteilten VPN-Tunnels für Office 365

>[!NOTE]
>Dieses Thema ist Teil einer Reihe von Themen, die sich mit der Optimierung von Office 365 für Remotebenutzer befassen.
>- Einen Überblick über die Verwendung von VPN-Split-Tunneling zum Optimieren der Office 365-Konnektivität für Remotebenutzer finden Sie unter [Übersicht: VPN-Split-Tunneling für Office 365](microsoft-365-vpn-split-tunnel.md).
>- Informationen zur Optimierung der weltweiten Mandantenleistung von Office 365 für Benutzer in China finden Sie unter Leistungsoptimierung von [Office 365 für Benutzer in China](microsoft-365-networking-china.md).

Seit vielen Jahren verwenden Unternehmen VPNs, um Remote-Erfahrungen für ihre Benutzer zu unterstützen. Während die wichtigsten Workloads weiterhin lokal bleiben, war ein VPN vom Remote-Client aus, das durch ein Rechenzentrum im Unternehmensnetzwerk geleitet wurde, die primäre Methode für Remotebenutzer, um auf Unternehmensressourcen zuzugreifen. Um diese Verbindungen zu schützen, bauen Unternehmen entlang der VPN-Pfade Schichten von Netzwerksicherheitslösungen auf. Dies geschah sowohl zum Schutz der internen Infrastruktur als auch zum Schutz des mobilen Surfens auf externen Websites, indem der Datenverkehr in das VPN umgeleitet und dann über den Internet-Perimeter vor Ort hinaus geleitet wurde. VPNs, Netzwerkperimeter und zugehörige Sicherheitsinfrastruktur wurden häufig für ein definiertes Volumen von Datenverkehr Zweck entwickelt und skaliert, wobei in der Regel der Großteil der Konnektivität innerhalb des Unternehmensnetzwerks initiiert wurde und der größte Teil innerhalb der internen Netzwerkgrenzen bleibt.

Eine Zeit lang waren VPN-Modelle, bei denen alle Verbindungen vom Gerät des Remotebenutzers zurück in das firmeninterne Netzwerk geroutet werden (bekannt als **Tunnelerzwingung**), weitgehend tragfähig, solange die gleichzeitige Anzahl der Remotebenutzer gering war und das Datenverkehrsvolumen, welches das VPN durchquert, gering war.  Einige Kunden setzten VPN-Tunnelerzwingung weiterhin als Ist-Zustand ein, auch nachdem ihre Anwendungen von innerhalb des Unternehmensumfelds in öffentliche SaaS-Clouds umgezogen waren, wobei Office 365 ein Paradebeispiel ist.

Für die Verbindung zu verteilten und leistungsempfindlichen Cloud-Anwendungen ist die Verwendung von Tunnelerzwingung in VPNs äußerst suboptimal, aber die negativen Auswirkungen davon mögen von einigen Unternehmen akzeptiert worden sein, um den Ist-Zustand aus Sicherheitssicht zu erhalten. Ein Beispieldiagramm für dieses Szenario ist unten zu sehen:

![Split-Tunnel-VPN – Konfiguration](../media/vpn-split-tunneling/enterprise-network-traditional.png)

Dieses Problem nimmt seit einigen Jahren zu, und viele Kunden berichten von einer signifikanten Verschiebung der Netzwerkverkehrsmuster. Der Datenverkehr, der früher in lokal betrieben wurde, stellt nun eine Verbindung mit externen Cloud-Endpunkten her. Zahlreiche Microsoft-Kunden berichten, dass früher etwa 80 % ihres Netzwerkverkehrs auf eine interne Quelle entfielen (in der obigen Abbildung durch die gepunktete Linie dargestellt). Im Jahr 2020 liegt diese Zahl nun bei etwa 20 % oder weniger, da sie große Workloads in die Cloud verlagert haben, diese Trends sind bei anderen Unternehmen nicht ungewöhnlich. Im Laufe der Zeit wird das oben beschriebene Modell mit fortschreitender Cloud-Journey immer umständlicher und nicht mehr tragfähig, was ein Unternehmen daran hindert, auf dem Weg in eine „Cloud First World“ agil zu sein.

Durch die weltweite COVID-19-Krise hat sich dieses Problem so ausgeweitet, dass sofortige Abhilfe geschaffen werden muss. Die Notwendigkeit, die Sicherheit der Mitarbeiter zu gewährleisten, hat zu beispiellosen Anforderungen an die Unternehmens-IT geführt, um die Produktivität der Arbeit von zu Hause aus massiv zu unterstützen. Microsoft Office 365 ist gut positioniert, um Kunden bei der Erfüllung dieser Nachfrage zu unterstützen, aber hohe Gleichzeitigkeit von Benutzern, die von zu Hause aus arbeiten, generiert eine große Menge an Office 365 Datenverkehr, der, wenn er über einen erzwungenen Tunnel-VPN und lokale Netzwerkperimeter geleitet wird, eine schnelle Sättigung verursacht und die VPN-Infrastruktur außerhalb der Kapazität führt. In dieser neuen Realität ist die Verwendung von VPN für den Zugriff auf Office 365 nicht mehr nur ein Leistungshindernis, sondern eine harte Wand, die sich nicht nur auf Office 365, sondern auch auf kritische Geschäftsvorgänge auswirkt, die sich weiterhin auf das VPN auswirken müssen.

Microsoft arbeitet seit vielen Jahren eng mit Kunden und der gesamten Branche zusammen, um effektive, moderne Lösungen für diese Probleme aus unseren eigenen Diensten heraus anzubieten und sich an den besten Praktiken der Branche auszurichten. [Die Grundsätze der Konnektivität](https://aka.ms/pnc) für den Office 365-Dienst wurden so konzipiert, dass sie für Remotebenutzer effizient funktionieren und es einer Organisation dennoch ermöglichen, die Sicherheit und Kontrolle über ihre Konnektivität aufrechtzuerhalten. Diese Lösungen können auch sehr schnell mit begrenzter Arbeit umgesetzt werden, aber dennoch eine bedeutende positive Auswirkung auf die oben beschriebenen Probleme erzielen.

Die von Microsoft empfohlene Strategie zur Optimierung der Konnektivität von Remote-Mitarbeitern konzentriert sich darauf, die Probleme mit dem traditionellen Ansatz schnell zu lindern und mit wenigen einfachen Schritten eine hohe Leistung zu erzielen. Mit diesen Schritten wird der VPN-Legacy Ansatz für eine kleine Anzahl definierter Endpunkte angepasst, die Engpässe bei VPN-Servern umgehen. Ein gleichwertiges oder sogar überlegenes Sicherheitsmodell kann auf verschiedenen Ebenen angewendet werden, um die Notwendigkeit zu beseitigen, den gesamten Datenverkehr am Ausgang des Unternehmensnetzwerks zu sichern. In den meisten Fällen kann dies innerhalb von Stunden effektiv erreicht werden und ist dann auf andere Arbeitslasten skalierbar, wenn die Anforderungen es erfordern und die Zeit es erlaubt.

## <a name="common-vpn-scenarios"></a>Gängige VPN-Szenarien

In der Liste unten sehen Sie die häufigsten VPN-Szenarien, die in Unternehmensumgebungen vorkommen. Die meisten Kunden arbeiten traditionell mit Modell 1 (VPN-Tunnelerzwingung). Dieser Abschnitt unterstützt Sie bei der schnellen und sicheren Umstellung auf das **Modell 2**, das mit relativ geringem Aufwand erreicht werden kann, und bietet enorme Vorteile für Netzwerkleistung und Benutzerfreundlichkeit.

| **Modell** | **Beschreibung** |
| --- | --- |
| [1. VPN-Tunnelerzwingung](#1-vpn-forced-tunnel) | 100% des Datenverkehrs gehen in den VPN-Tunnel, einschließlich lokaler, Internet-und aller O365/M365 |
| [2. VPN-Tunnelerzwingung mit wenigen Ausnahmen](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) | VPN-Tunnel wird standardmäßig verwendet (Standard-Route zeigt auf VPN), mit wenigen, wichtigsten Ausnahmeszenarien, die erlaubt sind, direkt zu gehen |
| [3. VPN-Tunnelerzwingung mit breiten Ausnahmen](#3-vpn-forced-tunnel-with-broad-exceptions) | VPN-Tunnel wird standardmäßig verwendet (Standard-Route zeigt auf VPN), mit breiten Ausnahmen, die direkt gehen dürfen (z. B. alle Office 365, alle Salesforce, alle Zoom) |
| [4. Selektiver VPN-Tunnel](#4-vpn-selective-tunnel) | VPN-Tunnel wird nur für Corpnet-basierte Dienste verwendet. Die Standardroute (Internet und alle internetbasierten Dienste) wird direkt verwendet. |
| [5. Kein VPN](#5-no-vpn) | Eine Variation von #2, bei der anstelle von Legacy-VPN alle Corpnet-Dienste über moderne Sicherheitsansätze (wie Zscaler ZPA, Azure Active Directory (Azure AD) Proxy/MCAS usw. veröffentlicht werden) |

### <a name="1-vpn-forced-tunnel"></a>1. VPN-Tunnelerzwingung

Dies ist das häufigste Startszenario für die meisten Unternehmenskunden. Es wird ein erzwungenes VPN verwendet, was bedeutet, dass 100% des Datenverkehrs an das Unternehmensnetzwerk weitergeleitet werden, unabhängig davon, ob sich der Endpunkt innerhalb des Unternehmensnetzwerks befindet oder nicht. Jeglicher externe (internetgebundene) Datenverkehr wie z. B. Office 365 oder das Surfen im Internet wird dann aus der Sicherheitsausrüstung vor Ort, wie z. B. Proxies, wieder herausgeschnitten. In der derzeitigen Situation, in der fast 100 % der Benutzer aus der Ferne arbeiten, stellt dieses Modell daher eine extrem hohe Belastung für die VPN-Infrastruktur dar und wird wahrscheinlich die Leistung des gesamten Unternehmensverkehrs und damit die Effizienz des Unternehmens in einer Krisenzeit erheblich beeinträchtigen.

![VPN-Tunnelerzwingung – Modell 1](../media/vpn-split-tunneling/vpn-model-1.png)

### <a name="2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions"></a>2. VPN-Tunnelerzwingung mit einer kleinen Anzahl von vertrauenswürdigen Ausnahmen

Dieses Modell ist für ein Unternehmen wesentlich effizienter, da es eine kleine Anzahl von kontrollierten und definierten Endpunkten ermöglicht, bei denen es sich um eine sehr hohe Last-und Latenzzeit handelt, um den VPN-Tunnel zu umgehen und in diesem Beispiel direkt zum Office 365 Dienst zu wechseln. Dadurch wird die Leistung für die abgeladenen Dienste erheblich verbessert, und auch die Auslastung der VPN-Infrastruktur wird verringert, sodass Elemente, für die die Ressource weiterhin mit geringerer Konflikte ausgeführt werden muss, für Ressourcen arbeiten können. Dieses Modell konzentriert sich auf die Unterstützung beim Übergang, da es einfache, definierte Aktionen ermöglicht, die mit zahlreichen positiven Ergebnissen sehr schnell ausgeführt werden können.

![Split-Tunnel-VPN – Modell 2](../media/vpn-split-tunneling/vpn-model-2.png)

### <a name="3-vpn-forced-tunnel-with-broad-exceptions"></a>3. VPN-Tunnelerzwingung mit breiten Ausnahmen

Das dritte Modell erweitert den Bereich von Modell 2, anstatt lediglich eine kleine Gruppe definierter Endpunkte direkt zu senden, sondern sendet den gesamten Datenverkehr direkt an vertrauenswürdige Dienste wie Office 365 und salesforce. Dadurch wird die Belastung der VPN-Infrastruktur des Unternehmens weiter reduziert und die Leistung der definierten Dienste verbessert. Da dieses Modell wahrscheinlich mehr Zeit in Anspruch nimmt, um die Durchführbarkeit und Implementierung zu bewerten, ist es wahrscheinlich ein Schritt, der zu einem späteren Zeitpunkt iterativ eingeleitet werden kann, nachdem das zweite Modell erfolgreich eingerichtet wurde.

![Split-Tunnel-VPN – Modell 3](../media/vpn-split-tunneling/vpn-model-3.png)

### <a name="4-vpn-selective-tunnel"></a>4. Selektiver VPN-Tunnel

Dieses Modell kehrt das dritte Modell insofern um, als nur der Datenverkehr, der als mit einer Unternehmens-IP-Adresse identifiziert wurde, durch den VPN-Tunnel geleitet wird und somit der Internet-Pfad die Standardroute für alles andere ist. Dieses Modell setzt voraus, dass sich eine Organisation auf dem Weg zu [Zero Trust](https://www.microsoft.com/security/zero-trust?rtc=1) befindet, um dieses Modell sicher umsetzen zu können. Es ist zu beachten, dass dieses Modell oder eine Variation davon im Laufe der Zeit wahrscheinlich zum notwendigen Standard werden wird, da sich immer mehr Dienste vom Unternehmensnetzwerk weg und in die Cloud verlagern. Microsoft verwendet dieses Modell intern; weitere Informationen über die Implementierung von VPN Split-Tunneling durch Microsoft finden Sie unter [Ausführen auf VPN: Wie Microsoft die Verbindung zu seinen Remote-Mitarbeitern aufrechterhält](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv).

![Split-Tunnel-VPN – Modell 4](../media/vpn-split-tunneling/vpn-model-4.png)

### <a name="5-no-vpn"></a>5. Kein VPN

Eine erweiterte Version von Modellnummer 2, wobei alle internen Dienste über einen modernen Sicherheitsansatz oder eine SDWAN-Lösung wie Azure AD Proxy, MCAS, Zscaler ZPA usw. veröffentlicht werden.

![Split-Tunnel-VPN – Modell 5](../media/vpn-split-tunneling/vpn-model-5.png)

## <a name="implement-vpn-split-tunneling"></a>Implementierung von VPN-Split-Tunneling

In diesem Abschnitt finden Sie die einfachen Schritte, die erforderlich sind, um Ihre VPN-Client-Architektur von einer _VPN-Tunnelerzwingung_ zu einer _VPN-Tunnelerzwingung mit einer kleinen Anzahl von vertrauenswürdigen Ausnahmen_ zu migrieren, [VPN-Split-Tunnel-Modell 2](#2-vpn-forced-tunnel-with-a-small-number-of-trusted-exceptions) im Abschnitt [Allgemeine VPN-Szenarien](#common-vpn-scenarios).

Das folgende Diagramm veranschaulicht, wie die empfohlene VPN-Split-Tunnellösung funktioniert:

![Split-Tunnel-VPN – Lösungsdetails](../media/vpn-split-tunneling/vpn-split-tunnel-example.png)

### <a name="1-identify-the-endpoints-to-optimize"></a>1. Ermitteln der zu optimierenden Endpunkte

Im Thema [Office 365 URLs und IP-Adressbereiche](urls-and-ip-address-ranges.md) identifiziert Microsoft klar die wichtigsten Endpunkte, die Sie zum Optimieren benötigen, und kategorisiert sie als **Optimieren**. Derzeit gibt es nur vier URLs und 20 IP-Subnetze, die optimiert werden müssen. Diese kleine Gruppe von Endpunkten macht etwa 70 % bis 80 % des Verkehrsaufkommens des Office 365-Diensts aus, einschließlich der latenzempfindlichen Endpunkte wie die für die Teams-Medien. Im Wesentlichen ist dies der Datenverkehr, auf den wir besonders achten müssen, und auch der Datenverkehr, der zu einem enormen Druck auf herkömmliche Netzwerkpfade und VPN-Infrastrukturen führen wird.

URLS in dieser Kategorie besitzen die folgenden Merkmale:

- Sind Endgeräte im Besitz Microsoft und Verwalteten Endpunkten, auf der Microsoft-Infrastruktur gehostet?
- Lassen Sie IPs bereitstellen
- Geringe Änderungsrate, und es wird erwartet, dass die Zahl klein ist (zurzeit 20 IP-Subnetze)
- Sind bandbreiten- und/oder latenzempfindlich
- Sind in der Lage, die erforderlichen Sicherheitselemente im Dienst und nicht inline im Netzwerk bereitzustellen
- Ungefähr 70 bis 80 % des Verkehrsaufkommens des Office 365-Diensts

Weitere Informationen zu Office 365-Endpunkten und deren Kategorisierung und Verwaltung finden Sie im Artikel [Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md).

#### <a name="optimize-urls"></a>Optimieren der URLs

Die aktuellen Optimieren-URLs finden Sie in der folgenden Tabelle. In den meisten Fällen sollten Sie nur URL-Endpunkte in einer [Browser-PAC-Datei](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic) verwenden müssen, wobei die Endpunkte so konfiguriert sind, dass sie nicht an den Proxy, sondern direkt gesendet werden.

| Optimieren der URLs | Port/Protokoll | Zweck |
| --- | --- | --- |
| <https://outlook.office365.com> | TCP 443 | Dies ist eine der primären URLs, die Outlook für die Verbindung mit seinem Exchange Online-Server verwendet, und hat ein hohes Volumen an Bandbreitennutzung und Verbindungsanzahl. Für Online-Funktionen wie Sofortsuche, andere Postfachkalender, freies/besetztes Nachschlagen, Verwaltung von Regeln und Warnungen, Exchange-Online-Archiv, E-Mails, die den Postausgang verlassen, ist eine geringe Netzwerklatenzzeit erforderlich. |
| <https://outlook.office.com> | TCP 443 | Diese URL wird für Outlook Online Web Access verwendet, um eine Verbindung mit dem Exchange Online-Server herzustellen, und ist empfindlich für die Netzwerklatenz. Konnektivität ist insbesondere für das Hoch- und Herunterladen großer Dateien mit SharePoint Online erforderlich. |
| https:// \<tenant\> . SharePoint.com | TCP 443 | Dies ist die primäre URL für SharePoint Online und hat eine hohe Bandbreitennutzung. |
| https:// \<tenant\> -My.SharePoint.com | TCP 443 | Dies ist die primäre URL für OneDrive for Business und hat eine hohe Bandbreitennutzung und möglicherweise eine hohe Anzahl an Verbindungen vom OneDrive for Business Sync-Tool. |
| Teams Media IPs (keine URL) | UDP 3478, 3479, 3480 und 3481 | Relay Discovery Allocation und Real-Time Traffic (3478), Audio (3479), Video (3480) und Video Screen Sharing (3481). Dabei handelt es sich um die Endpunkte, die für Skype for Business und Microsoft Teams Mediendatenverkehr (Anrufe, Besprechungen usw.) verwendet werden. Die meisten Endpunkte werden bereitgestellt, wenn der Microsoft Teams-Client einen Anruf einleitet (und sind in den für den Dienst aufgelisteten erforderlichen IPs enthalten). Für eine optimale Medienqualität ist die Verwendung des UDP-Protokolls erforderlich.   |

In den obigen Beispielen sollte der **Mandant** durch den Namen Ihres Office 365-Mandanten ersetzt werden. Beispielsweise würde **contoso.onmicrosoft.com** _contoso.sharepoint.com_ und _constoso-my.sharepoint.com_ verwenden.

#### <a name="optimize-ip-address-ranges"></a>Optimieren der IP-Adressbereiche

Zum Zeitpunkt der Erstellung der IP-Bereiche, denen diese Endpunkte entsprechen, lauten wie folgt. Es wird **dringend** empfohlen, ein [Skript wie dieses](https://github.com/microsoft/Office365NetworkTools/tree/master/Scripts/Display%20URL-IPs-Ports%20per%20Category) Beispiel, den [IP- und URL-Webdienst von Office 365](microsoft-365-ip-web-service.md) oder die [URL/IP-Seite](urls-and-ip-address-ranges.md) zu verwenden, um bei der Anwendung der Konfiguration nach Aktualisierungen zu suchen und eine Richtlinie zu erstellen, um dies regelmäßig zu tun.

```
104.146.128.0/17
13.107.128.0/22
13.107.136.0/22
13.107.18.10/31
13.107.6.152/31
13.107.64.0/18
131.253.33.215/32
132.245.0.0/16
150.171.32.0/22
150.171.40.0/22
191.234.140.0/22
204.79.197.215/32
23.103.160.0/20
40.104.0.0/15
40.108.128.0/17
40.96.0.0/13
52.104.0.0/14
52.112.0.0/14
52.96.0.0/14
52.120.0.0/14
```

### <a name="2-optimize-access-to-these-endpoints-via-the-vpn"></a>2. Optimieren des Zugriffs auf diese Endpunkte über das VPN

Nun, da wir diese kritischen Endpunkte identifiziert haben, müssen wir sie vom VPN-Tunnel ablenken und ihnen erlauben, die lokale Internetverbindung des Benutzers zu nutzen, um sich direkt mit dem Dienst zu verbinden. Die Art und Weise, wie dies erreicht wird, hängt vom verwendeten VPN-Produkt und der Maschinenplattform ab, aber die meisten VPN-Lösungen ermöglichen eine einfache Konfiguration der Richtlinien zur Anwendung dieser Logik. Informationen zur plattformspezifischen Anleitung für geteilte Tunnel finden Sie in den [HOWTO-Leitfäden für gängige VPN-Plattformen](#howto-guides-for-common-vpn-platforms).

Wenn Sie die Lösung manuell testen möchten, können Sie das folgende PowerShell-Beispiel ausführen, um die Lösung auf der Ebene der Routingtabelle zu emulieren. In diesem Beispiel wird eine Route für jedes Subnetz des Teams Media IP in die Routingtabelle eingefügt. Sie können die Medienleistung des Teams vorher und nachher testen und die Unterschiede in den Routen für die angegebenen Endpunkte beobachten.

#### <a name="example-add-teams-media-ip-subnets-into-the-route-table"></a>Beispiel: Hinzufügen von Teams Medien-IP-Subnetzen in der Routingtabelle

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18" # Teams Media endpoints
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

Im obigen Skript ist _$intIndex_ der Index der Schnittstelle, die mit dem Internet verbunden ist (Suche durch Ausführen von **get-netadapter** in PowerShell; suchen Sie nach dem Wert von _ifIndex_) und _$gateway_ ist das Standardgateway dieser Schnittstelle (Suche durch Ausführen von **ipconfig** in einer Befehlszeile oder **(Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop** in PowerShell).

Nachdem Sie die Routen hinzugefügt haben, können Sie bestätigen, dass die Routentabelle korrekt ist, indem Sie den **Route Print** in einer Eingabeaufforderung oder in PowerShell ausführen. Die Ausgabe sollte die von Ihnen hinzugefügten Routen enthalten und den Schnittstellenindex (_22_ in diesem Beispiel) und das Gateway für diese Schnittstelle (_ 192.168.1.1_ in diesem Beispiel) anzeigen:

![Route Print-Ausgabe](../media/vpn-split-tunneling/vpn-route-print.png)

Um Routen für **alle** aktuellen IP-Adressbereiche in der Kategorie Optimieren hinzuzufügen, können Sie die folgende Skriptvariante verwenden, um den [Office 365 IP- und URL-Webdienst](microsoft-365-ip-web-service.md) für den aktuellen Satz von IP-Subnetzen der Kategorie Optimieren abzufragen und sie der Routingtabelle hinzuzufügen.

#### <a name="example-add-all-optimize-subnets-into-the-route-table"></a>Beispiel: Hinzufügen aller Optimieren-Subnetze in die Routingtabelle

```powershell
$intIndex = "" # index of the interface connected to the internet
$gateway = "" # default gateway of that interface
# Query the web service for IPs in the Optimize category
$ep = Invoke-RestMethod ("https://endpoints.office.com/endpoints/worldwide?clientrequestid=" + ([GUID]::NewGuid()).Guid)
# Output only IPv4 Optimize IPs to $optimizeIps
$destPrefix = $ep | where {$_.category -eq "Optimize"} | Select-Object -ExpandProperty ips | Where-Object { $_ -like '*.*' }
# Add routes to the route table
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

Wenn Sie versehentlich Routen mit falschen Parametern hinzugefügt haben oder einfach nur Ihre Änderungen rückgängig machen wollen, können Sie die soeben hinzugefügten Routen mit dem folgenden Befehl entfernen:

```powershell
foreach ($prefix in $destPrefix) {Remove-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```

<!--- remmed until we add more reliable interface selection logic
#### Example script to add Teams Media subnets to the route table

```powershell
$adapter = get-netadapter | ? {$_.Status -eq "Up"}
$adapterIndex = $adapter.ifIndex
$gateway = (Get-NetIPConfiguration | Foreach IPv4DefaultGateway).NextHop

$destPrefix = "52.120.0.0/14", "52.112.0.0/14", "13.107.64.0/18"
foreach ($prefix in $destPrefix) {New-NetRoute -DestinationPrefix $prefix -InterfaceIndex $intIndex -NextHop $gateway}
```
-->

Der VPN-Client sollte so konfiguriert werden, dass der Datenverkehr zu den **Optimieren**-IPs auf diese Weise geleitet wird. Auf diese Weise kann der Datenverkehr lokale Microsoft-Ressourcen wie Office 365-Dienst-Front-Doors wie [die Azure-Haustür](https://azure.microsoft.com/blog/azure-front-door-service-is-now-generally-available/) verwenden, die Office 365 Dienste und Verbindungsendpunkte so nah wie möglich an Ihre Benutzer weiter gibt. Dies ermöglicht es uns, den Benutzern, wo auch immer in der Welt sie sich befinden, ein extrem hohes Leistungsniveau zu bieten und das globale [Netzwerk von Microsoft auf Weltklasseniveau voll auszunutzen](https://azure.microsoft.com/blog/how-microsoft-builds-its-fast-and-reliable-global-network/), was sehr wahrscheinlich innerhalb weniger Millisekunden nach dem direkten Austritt Ihrer Benutzer geschieht.

## <a name="configuring-and-securing-teams-media-traffic"></a>Konfigurieren und Sichern von Teams-Mediendatenverkehr

Einige Administratoren benötigen möglicherweise detailliertere Informationen darüber, wie Anrufströme in Teams mit einem Split-Tunneling-Modell ablaufen und wie die Verbindungen gesichert werden.

### <a name="configuration"></a>Konfiguration

Wenn Microsoft Teams die [GetBestRoute](https://docs.microsoft.com/windows/win32/api/iphlpapi/nf-iphlpapi-getbestroute) -Funktion aufruft, um zu ermitteln, welche lokale Schnittstelle der Route entspricht, die für ein bestimmtes Ziel verwendet werden soll, wird für Anrufe und Besprechungen, solange die erforderlichen Optimize IP-Subnetze für Teams-Medien ordnungsgemäß in der Route-Tabelle vorhanden sind, die lokale Schnittstelle in den oben aufgeführten Microsoft-IP-Blöcken zurückgegeben.

Einige VPN-Client-Software ermöglicht die Routing-Manipulation auf der Basis von URLs. Dem Medienverkehr des Teams ist jedoch keine URL zugeordnet, so dass die Steuerung des Routings für diesen Verkehr über IP-Subnetze erfolgen muss.

In bestimmten Szenarien, die häufig nichts mit der Client-Konfiguration des Teams zu tun haben, durchläuft der Medienverkehr den VPN-Tunnel auch dann noch, wenn die richtigen Routen vorhanden sind. Wenn Sie auf dieses Szenario stoßen, sollte die Verwendung einer Firewall-Regel zur Blockierung der IP-Subnetze oder Ports des Teams für die Verwendung des VPN ausreichen.

>[!IMPORTANT]
>Stellen Sie sicher, dass die Benutzer Microsoft Teams-Client Version **1.3.00.13565** oder höher ausgeführt werden, um sicherzustellen, dass der Mediendatenverkehr von Teams über die gewünschte Methode in allen VPN-Szenarien weitergeleitet wird. Diese Version enthält Verbesserungen in der Art und Weise, wie der Client verfügbare Netzwerkpfade erkennt.

Der Signalisierungs Datenverkehr wird über HTTPS ausgeführt und ist nicht so anfällig wie der Mediendatenverkehr und wird in den URL/IP-Daten als **zulässig** gekennzeichnet und kann daher gefahrlos über den VPN-Client weitergeleitet werden, falls gewünscht.

### <a name="security"></a>Sicherheit

Ein häufiges Argument für die Vermeidung von Split-Tunneln ist, dass dies weniger sicher ist, d. h. jeder Datenverkehr, der nicht durch den VPN-Tunnel geht, profitiert nicht von dem Verschlüsselungsschema, das auf den VPN-Tunnel angewendet wird, und ist daher weniger sicher.

Das wichtigste Gegenargument dazu ist, dass der Medienverkehr bereits über das _Secure Real-Time Transport Protocol (SRTP)_ verschlüsselt wird, ein Profil des Real-Time Transport Protocol (RTP), das dem RTP-Datenverkehr Vertraulichkeit, Authentifizierung und Schutz vor Replay-Angriffen bietet. SRTP selbst stützt sich auf einen zufällig generierten Sitzungsschlüssel, der über den TLS-gesicherten Signalisierungskanal ausgetauscht wird. Dies wird in [diesem Sicherheitsleitfaden](https://docs.microsoft.com/skypeforbusiness/optimizing-your-network/security-guide-for-skype-for-business-online) sehr ausführlich behandelt, aber der wichtigste Abschnitt von Interesse ist die Medienverschlüsselung.

Der Medienverkehr wird mit SRTP verschlüsselt, das einen Sitzungsschlüssel verwendet, der von einem sicheren Zufallszahlengenerator generiert und über den TLS-Signalisierungskanal ausgetauscht wird. Darüber hinaus werden Medien, die in beide Richtungen zwischen dem Mediationsserver und seinem internen Next Hop fließen, ebenfalls mit SRTP verschlüsselt.

Skype for Business Online generiert Benutzername/Passwörter für den sicheren Zugriff auf Medienrelais über _Traversal unter Verwendung von Relays um NAT (TURN)_. Medienrelays tauschen den Benutzernamen/Kennwort über einen TLS-gesicherten SIP-Kanal aus. Es ist erwähnenswert, dass ein VPN-Tunnel zwar zur Verbindung des Clients mit dem Unternehmensnetzwerk verwendet werden kann, der Datenverkehr aber dennoch in seiner SRTP-Form fließen muss, wenn er das Unternehmensnetzwerk verlässt, um den Dienst zu erreichen.

Informationen darüber, wie die Teams gemeinsame Sicherheitsbedenken wie Sprach- oder _Session Traversal Utilities for NAT (STUN)_-Verstärkungsangriffe entschärfen, [finden Sie in diesem Artikel](https://docs.microsoft.com/openspecs/office_protocols/ms-ice2/69525351-8c68-4864-b8a6-04bfbc87785c).

Sie können auch über moderne Sicherheitskontrollen in entfernten Arbeitsszenarien lesen unter [Alternative Möglichkeiten für Sicherheitsexperten und IT, moderne Sicherheitskontrollen in den heutigen eindeutigen Remote arbeitsszenarios zu erreichen (Microsoft Security-Teamblog)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/).

## <a name="testing"></a>Testen

Sobald die Richtlinie in Kraft ist, sollten Sie bestätigen, dass sie wie erwartet funktioniert. Es gibt mehrere Möglichkeiten, um zu testen, ob der Pfad korrekt für die Nutzung der lokalen Internetverbindung eingestellt ist:

- Führen Sie den [Microsoft 365 Connectivity Test](https://aka.ms/netonboard) aus, mit dem Verbindungstests für Sie ausgeführt werden, einschließlich der Ablauf Verfolgungs Routen wie oben. In diesem Tool werden auch VPN-Tests hinzugefügt, die zusätzliche Einblicke bieten sollten.

- Ein einfacher Tracert zu einem Endpunkt im Bereich des geteilten Tunnels sollte z. B. den eingeschlagenen Weg zeigen:

  ```powershell
  tracert worldaz.tr.teams.microsoft.com
  ```

  Sie sollten dann einen Pfad über den lokalen ISP zu diesem Endpunkt sehen, der in eine IP in den Teams-Bereichen aufgelöst werden soll, die wir für den geteilten Tunneling konfiguriert haben.

- Nehmen Sie eine Netzwerkerfassung mit einem Tool wie Wireshark vor. Filtern Sie während eines Anrufs auf UDP und Sie sollten sehen, wie der Datenverkehr zu einer IP im Bereich **Optimieren** von Teams fließt. Wenn der VPN-Tunnel für diesen Datenverkehr verwendet wird, ist der Mediendatenverkehr in der Verfolgung nicht sichtbar.

### <a name="additional-support-logs"></a>Zusätzliche Supportprotokolle

Wenn Sie weitere Daten zur Fehlerbehebung benötigen oder Hilfe vom Microsoft-Support anfordern, sollten die folgenden Informationen es Ihnen ermöglichen, schneller eine Lösung zu finden. Mit dem Microsoft-Support-Tool für die **Windows-CMD-basierte, universelle Problembehandlung-Skript** Erstellung können Sie die relevanten Protokolle auf einfache Weise erfassen. Das Tool und die Gebrauchsanweisung finden Sie unter <https://aka.ms/TssTools.>

## <a name="howto-guides-for-common-vpn-platforms"></a>HOWTO-Leitfäden für gängige VPN-Plattformen

Dieser Abschnitt enthält Links zu ausführlichen Leitfäden für die Implementierung von geteilten Tunneln für den Office 365-Datenverkehr von den gängigsten Partnern in diesem Raum. Wir werden zusätzliche Leitfäden hinzufügen, sobald sie verfügbar sind.

- **Windows 10-VPN-Client**: [Optimieren des Office 365-Datenverkehrs für Remotemitarbeiter mit dem nativen Windows 10-VPN-Client](https://docs.microsoft.com/windows/security/identity-protection/vpn/vpn-office-365-optimization)
- **Cisco AnyConnect**: [Optimieren des AnyConnect-Split-Tunnels für Office365](https://www.cisco.com/c/en/us/support/docs/security/anyconnect-secure-mobility-client/215343-optimize-anyconnect-split-tunnel-for-off.html)
- **Palo Alto GlobalProtect**: [Optimieren des Office 365-Datenverkehrs über einen geteilten VPN-Tunnel mit Zugriffsausschlussroute](https://live.paloaltonetworks.com/t5/Prisma-Access-Articles/GlobalProtect-Optimizing-Office-365-Traffic/ta-p/319669)
- **F5 Networks BIG-IP APM**: [Optimieren des Office 365-Datenverkehrs beim Remotezugriff über VPNs bei Verwendung von BIG-IP APM](https://devcentral.f5.com/s/articles/SSL-VPN-Split-Tunneling-and-Office-365)
- **Citrix Gateway**: [Optimiere Citrix Gateway VPN Split-Tunnel für Office365](https://docs.citrix.com/en-us/citrix-gateway/13/optimizing-citrix-gateway-vpn-split-tunnel-for-office365.html)
- **Pulse Secure**: [VPN-Tunneling: Konfigurieren von geteilten Tunneln zum Ausschließen von Office365-Anwendungen](https://kb.pulsesecure.net/articles/Pulse_Secure_Article/KB44417)
- **Check Points VPN**: [Konfigurieren des geteilten Tunnels für Office 365 und andere SaaS-Anwendungen](https://supportcenter.checkpoint.com/supportcenter/portal?eventSubmit_doGoviewsolutiondetails=&solutionid=sk167000)

## <a name="faq"></a>Häufig gestellte Fragen (FAQ)

Das Microsoft-Sicherheits Team hat [einen Artikel](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/) veröffentlicht, in dem die wichtigsten Möglichkeiten für Sicherheitsexperten erläutert werden, und es können moderne Sicherheitssteuerelemente in den eindeutigen Remote-arbeitsszenarien von heute erreicht werden. Darüber hinaus finden Sie im Folgenden einige der häufigsten Kundenfragen und Antworten zu diesem Thema.

### <a name="how-do-i-stop-users-accessing-other-tenants-i-do-not-trust-where-they-could-exfiltrate-data"></a>Wie verhindere ich, dass Benutzer auf andere Mieter zugreifen, denen ich nicht traue, wo sie Daten exfiltrieren könnten?

Die Antwort ist eine [Funktion namens Mandanteneinschränkungen](https://docs.microsoft.com/azure/active-directory/manage-apps/tenant-restrictions). Der Authentifizierungsdatenverkehr ist weder hochvolumig noch besonders latenzempfindlich und kann daher über die VPN-Lösung an den lokalen Proxy gesendet werden, wo die Funktion angewendet wird. Eine Liste der zulässigen vertrauenswürdigen Mandanten wird hier beibehalten, und wenn der Client versucht, ein Token für einen nicht vertrauenswürdigen Mandanten abzurufen, verweigert der Proxy einfach die Anforderung. Wenn der Mandant vertrauenswürdig ist, dann ist ein Token zugänglich, wenn der Benutzer die richtigen Anmeldedaten und Berechtigungen hat.

Auch wenn ein Benutzer eine TCP/UDP-Verbindung zu den oben mit „Optimieren“ markierten Endpunkten herstellen kann, kann er sich also ohne ein gültiges Token für den Zugriff auf den betreffenden Mandanten einfach nicht anmelden und auf Daten zugreifen/verschieben.

### <a name="does-this-model-allow-access-to-consumer-services-such-as-personal-onedrive-accounts"></a>Ermöglicht dieses Modell den Zugang zu Verbraucherdiensten wie z. B. privaten OneDrive-Konten?

Nein, es ist nicht der Fall. Die Endpunkte des Office 365 sind nicht die gleichen wie die Verbraucherdienste (Onedrive.live.com als Beispiel), so dass der geteilte Tunnel einem Benutzer keinen direkten Zugang zu den Verbraucherdiensten ermöglicht. Der Datenverkehr zu Verbraucher-Endpunkten wird weiterhin den VPN-Tunnel nutzen, und die bestehenden Richtlinien gelten weiterhin.

### <a name="how-do-i-apply-dlp-and-protect-my-sensitive-data-when-the-traffic-no-longer-flows-through-my-on-premises-solution"></a>Wie wende ich DLP an und schütze meine sensiblen Daten, wenn der Datenverkehr nicht mehr durch meine firmeninterne Lösung fließt?

Um die versehentliche Offenlegung von vertraulichen Informationen zu verhindern, verfügt Office 365 über eine Reihe von [integrierten Tools](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies). Sie können die integrierten [DLP-Funktionen](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies) von Teams und SharePoint nutzen, um unangemessen gespeicherte oder gemeinsam genutzte vertrauliche Informationen zu erkennen. Wenn ein Teil Ihrer Remote Arbeitsstrategie eine BYOD-Richtlinie ("Holen Sie Ihr eigenes Gerät") umfasst, können Sie den [App-basierten bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) verwenden, um zu verhindern, dass vertrauliche Daten auf die persönlichen Geräte der Benutzer heruntergeladen werden.

### <a name="how-do-i-evaluate-and-maintain-control-of-the-users-authentication-when-they-are-connecting-directly"></a>Wie bewerte und kontrolliere ich die Authentisierung des Benutzers, wenn er sich direkt verbindet?

Zusätzlich zu den in Q1 erwähnten Mandateneinschränkungen können [Richtlinien für den bedingten Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) angewendet werden, um das Risiko einer Authentifizierungsanfrage dynamisch zu bewerten und angemessen zu reagieren. Microsoft empfiehlt, das Modell [Zero Trust](https://www.microsoft.com/security/zero-trust?rtc=1) im Laufe der Zeit zu implementieren, und wir können die Richtlinien für den bedingten Zugriff von Azure AD nutzen, um die Kontrolle in einer mobilen und Cloud First World zu behalten. Richtlinien für den bedingten Zugriff können verwendet werden, um eine Echtzeit-Entscheidung darüber zu treffen, ob eine Authentifizierungsanfrage erfolgreich ist, basierend auf zahlreichen Faktoren wie z. B:

- Gerät, ist das Gerät bekannt/vertraut/Domäne verbunden?
- IP – kommt die Authentifizierungsanfrage von einer bekannten Unternehmens-IP-Adresse? Oder aus einem Land, dem wir nicht vertrauen?
- Anwendung – ist der Benutzer zur Nutzung dieser Anwendung berechtigt?

Wir können dann Richtlinien auslösen, wie z. B. die Genehmigung, die Auslösung von MFA oder die Blockierung der Authentifizierung auf der Grundlage dieser Richtlinien.

### <a name="how-do-i-protect-against-viruses-and-malware"></a>Wie kann ich mich vor Viren und Schadsoftware schützen?

Auch hier bietet Office 365 Schutz für die mit „Optimieren“ markierten Endpunkte in verschiedenen Ebenen des Diensts selbst, die [in diesem Dokument beschrieben werden](https://docs.microsoft.com/office365/Enterprise/office-365-malware-and-ransomware-protection). Wie bereits erwähnt, ist es wesentlich effizienter, diese Sicherheitselemente im Dienst selbst bereitzustellen, anstatt es im Einklang mit Geräten zu versuchen, die die Protokolle/den Datenverkehr möglicherweise nicht vollständig verstehen. Standardmäßig scannt SharePoint Online [Dateiuploads automatisch](https://docs.microsoft.com/microsoft-365/security/office-365-security/virus-detection-in-spo) auf bekannte Schadsoftware.

Für die oben aufgelisteten Exchange-Endpunkte leisten der [Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) und der [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) eine hervorragende Arbeit, um die Sicherheit des Datenverkehrs für den Dienst zu gewährleisten.

### <a name="can-i-send-more-than-just-the-optimize-traffic-direct"></a>Kann ich mehr als nur den „Optimieren“-Datenverkehr direkt senden?

Den mit **Optimieren** markierten Endpunkten sollte Vorrang eingeräumt werden, da diese bei einem geringen Arbeitsaufwand den maximalen Nutzen bringen. Wenn Sie dies wünschen, sind die zulässigen Endpunkte jedoch erforderlich, damit der Dienst funktioniert und IPS für die Endpunkte bereitgestellt werden, die bei Bedarf verwendet werden können.

Es gibt auch verschiedene Anbieter, die Cloud-basierte Proxy/Sicherheitslösungen namens Secure-webgateways anbieten, die zentrale Sicherheits-, Steuerungs-und Unternehmensrichtlinien Anwendung für das allgemeine Surfen im Internet bieten. Diese Lösungen können in einer Cloud-First-Welt, wenn hoch verfügbar, leistungsfähig und in der Nähe ihrer Benutzer bereitgestellt werden, gut funktionieren, indem der sichere Internet Zugriff von einem Cloud-basierten Standort in der Nähe des Benutzers ermöglicht wird. Dadurch entfällt die Notwendigkeit einer Haarnadelkurve durch das VPN/Unternehmensnetzwerk für den allgemeinen Browserverkehr, während die zentrale Sicherheitskontrolle weiterhin möglich ist.

Selbst mit diesen Lösungen empfiehlt Microsoft jedoch nach wie vor dringend, den mit „Optimieren“ markierten Office-365-Datenverkehr direkt an den Dienst zu senden.

Eine Anleitung für den direkten Zugang zu einem Azure Virtual Network finden Sie im Artikel [Remote-Arbeit mit Azure VPN Gateway Point-to-Site](https://docs.microsoft.com/azure/vpn-gateway/work-remotely-support).

### <a name="why-is-port-80-required-is-traffic-sent-in-the-clear"></a>Warum ist Port 80 erforderlich? Ist der gesendete Datenverkehr in Ordnung?

Port 80 wird nur für Dinge wie die Umleitung auf eine Port 443-Sitzung verwendet, es werden keine Kundendaten gesendet oder sind über Port 80 zugänglich. [Dieser Artikel](https://docs.microsoft.com/microsoft-365/compliance/encryption) beschreibt die Verschlüsselung von Daten im Transit und in Ruhe für Office 365, und [dieser Artikel](https://docs.microsoft.com/microsoftteams/microsoft-teams-online-call-flows#types-of-traffic) beschreibt, wie wir SRTP verwenden, um den Medienverkehr des Teams zu schützen.

### <a name="does-this-advice-apply-to-users-in-china-using-a-worldwide-instance-of-office-365"></a>Gilt dieser Ratschlag für Benutzer in der VR China, die eine weltweite Instanz von Office 365 benutzen?

**Nein**, es ist nicht der Fall. Der einzige Vorbehalt zu den obigen Ratschlägen sind Benutzer in der VR China, die eine Verbindung zu einer weltweiten Instanz von Office 365 herstellen. Aufgrund des häufigen Auftretens von grenzüberschreitenden Netzwerküberlastungen in der Region kann die Leistung des direkten Internetaustritts variabel sein. Die meisten Kunden in der Region arbeiten mit einem VPN, um den Datenverkehr in das Unternehmensnetzwerk zu bringen und ihre autorisierte MPLS-Leitung oder einen ähnlichen Weg zum Ausgang außerhalb des Landes über einen optimierten Pfad zu nutzen. Dies wird in dem Artikel [Office 365-Leistungsoptimierung für Benutzer in de VR China](microsoft-365-networking-china.md) näher erläutert.

## <a name="related-topics"></a>Verwandte Themen

[Übersicht über geteiltes VPN-Tunneln für Office 365](microsoft-365-vpn-split-tunnel.md)

[Office 365-Leistungsoptimierung für Benutzer in China](microsoft-365-networking-china.md)

[Alternative Möglichkeiten für Sicherheitsexperten und IT-Mitarbeiter, moderne Sicherheitskontrollen in den heutigen einzigartigen Remotearbeitsszenarien zu erreichen (Blog des Microsoft Security Teams)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Verbessern der VPN-Leistung bei Microsoft: Verwenden von Windows 10-VPN-Profilen zur Aktivierung automatischer Verbindungen](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[Betrieb über VPN: Wie Microsoft seine Remotemitarbeitern in Verbindung hält](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Prinzipien von Office 365-Netzwerkverbindungen](microsoft-365-network-connectivity-principles.md)

[Bewerten der Office 365-Netzwerkkonnektivität](assessing-network-connectivity.md)

[Office 365-Netzwerk- und Leistungsoptimierung](network-planning-and-performance.md)
