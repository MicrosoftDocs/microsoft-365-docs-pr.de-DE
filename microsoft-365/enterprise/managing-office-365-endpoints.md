---
title: Verwalten von Office 365-Endpunkten
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 1/24/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOE150
ms.assetid: 99cab9d4-ef59-4207-9f2b-3728eb46bf9a
description: Hier erfahren Sie, wie Sie Office 365 Endpunkte so verwalten, dass Sie mit der Netzwerkarchitektur ihrer Unternehmensorganisation zusammenarbeiten.
ms.openlocfilehash: 1c1e76ae6f6ca2c034258c5ba06e3efefd51d04c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690424"
---
# <a name="managing-office-365-endpoints"></a>Verwalten von Office 365-Endpunkten

Die meisten Unternehmen, die über mehrere geographische Standorte und ein sie verbindendes WAN verfügen, müssen für die Office 365-Netzwerkverbindung konfiguriert werden. Sie können Ihr Netzwerk optimieren, indem alle vertrauenswürdigen Office 365-Netzwerkanfragen direkt über Ihre Firewall gesendet und so alle zusätzlichen Überprüfungen oder Verarbeitungen auf Paketebene umgangen werden. Dadurch werden die Latenz und die Anforderungen an die Umkreiskapazität reduziert. Die Identifikation des Office 365-Netzwerkdatenverkehrs ist der erste Schritt, um Ihren Benutzern eine optimale Leistung zu garantieren. Weitere Informationen zur Office 365-Netzwerkkonnektivität finden Sie unter [ Prinzipien der Office 365-Netzwerkkonnektivität](microsoft-365-network-connectivity-principles.md).

Microsoft empfiehlt, dass Sie mithilfe des [Office 365-IP-Adress-und URL-Webdiensts](microsoft-365-ip-web-service.md) auf die Office 365-Netzwerkendpunkte zugreifen und Änderungen vornehmen.

Unabhängig davon, wie Sie den notwendigen Office 365-Netzwerkdatenverkehr verwalten, benötigt Office 365 eine Verbindung zum Internet. Weitere Netzwerkendpunkte, für die eine Verbindung erforderlich ist, sind in [Weitere Endpunkten, die nicht in der Office 365-IP-Adresse und dem URL-Webdienst enthalten sind](additional-office365-ip-addresses-and-urls.md) aufgelistet.

Wie Sie die Office 365-Netzwerkendpunkte verwenden, hängt von der Netzwerkarchitektur ihres Unternehmens ab. In diesem Artikel werden verschiedene Möglichkeiten beschrieben, wie Netzwerkarchitekturen Office 365-IP-Adressen und -URLs integrieren können. Der einfachste Weg, um zu entscheiden, welche Netzwerkanfragen als vertrauenswürdig eingestuft werden sollen, ist die Verwendung von SDWAN-Geräte, die die automatisierte Office 365-Konfiguration an jedem Ihrer Standorte unterstützen.

## <a name="sdwan-for-local-branch-egress-of-vital-office-365-network-traffic"></a>SDWAN für Office 365-Netzwerkdatenverkehr an Ihren Standorten

Sie können an jedem Standort Ihres Unternehmens ein SDWAN-Gerät bereitstellen, das für das optimale Routing des Datenverkehrs zu Endpunkten der Office 365- Kategorie „Optimize“, oder der Kategorien „Optimize“ und „Allow“ direkt zum Microsoft-Netzwerk konfiguriert ist. Weiterer Netzwerkdatenverkehr einschließlich des Datenverkehrs des lokalen Datenzentrums, des allgemeinen Website-Datenverkehrs und des Datenverkehrs zu Office 365 Standardkategorie-Endpunkten wird an einen anderen Ort gesendet, an dem Sie einen größeren Netzwerkrand haben.

Microsoft arbeitet mit SDWAN-Anbietern zusammen, um eine automatisierte Konfiguration zu ermöglichen. Weitere Informationen finden Sie unter [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md).

<a name="pacfiles"> </a>
## <a name="use-a-pac-file-for-direct-routing-of-vital-office-365-traffic"></a>Verwenden einer PAC-Datei für das Routing von wichtigem Office 365-Datenverkehr

Verwenden Sie PAC- oder WPAD-Dateien, um Netzwerkanforderungen zu verwalten, die Office 365 zugeordnet sind, aber keine IP-Adresse besitzen. In der Regel erhöhen Netzwerkanfragen, die über ein Proxy- oder Umkreisgerät gesendet werden, die Latenz. Während SSL-Unterbrechung und -prüfung die größte Latenz erzeugen, können andere Dienste wie die Proxyauthentifizierung und die Reputationssuche zu niedriger Leistung und einer entsprechend schlechten Benutzererfahrung führen. Darüber hinaus benötigen diese Umkreisnetzwerkgeräte ausreichend Kapazität, um alle Netzwerkanfragen zu verarbeiten. Es empfiehlt sich, Proxy- bzw. Überprüfungsgeräte für direkte Office 365-Netzwerkanforderungen zu umgehen.
  
[PowerShell Gallery Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) ist ein PowerShell-Skript, das die neuesten Netzwerkendpunkte aus dem IP-Adress- und URL-Webdienst von Office 365 ausliest und eine PAC-Beispieldatei erstellt. Sie können das Skript so ändern, dass es in Ihre vorhandene PAC-Dateiverwaltung integriert werden kann.

![Herstellen einer Verbindung mit Office 365 über Firewalls und Proxys.](../media/34d402f3-f502-42a0-8156-24a7c4273fa5.png)

**Abbildung 1: Einfaches Unternehmensumkreisnetzwerk**

Die PAC-Datei wird für Webbrowser in Punkt 1 in Abbildung 1 bereitgestellt. Wenn Sie eine PAC-Datei für den direkten Ausgang von wichtigem Office 365-Netzwerkdatenverkehr verwenden, müssen Sie auch die Verbindung zu den IP-Adressen hinter diesen URLs in ihrer Umkreisnetzwerk-Firewall zulassen. Dazu rufen Sie die IP-Adressen für die gleichen Office 365-Endpunktkategorien ab, die in der PAC-Datei angegeben sind, und erstellen basierend auf diesen Adressen Firewall-ACLs. Die Firewall ist Punkt 3 in Abbildung 1.

Wenn Sie gesondert festlegen, dass für die Endpunkte der Kategorie „Optimize“ nur direktes Routing ausgeführt werden soll, müssen alle erforderlichen Endpunkte der Kategorie „Allow“, die Sie an den Proxyserver senden, in diesem aufgelistet werden, um die Weiterverarbeitung zu umgehen. So sind beispielsweise die SSL-Unterbrechung und -Überprüfung und die Proxyauthentifizierung mit den Endpunkten der Kategorien „Optimize“ und „Allow“ nicht kompatibel. Der Proxy Server ist Punkt 2 in Abbildung 1.

Die allgemeine Konfiguration erlaubt den Office 365-Netzwerkdatenverkehr, der auf den Proxy Server trifft, ohne dass der gesamte ausgehende Datenverkehr vom Proxyserver verarbeitet wird. Informationen zu Problemen mit SSL-Unterbrechung und -Prüfung finden Sie unter [Verwenden von Netzwerkgeräten oder-Lösungen von Drittanbietern im Office 365-Datenverkehr](https://support.microsoft.com/help/2690045/using-third-party-network-devices-or-solutions-with-office-365).

Es gibt zwei Arten von PAC-Dateien, die vom Get-PacFile-Skript erzeugt werden.

| Typ | Beschreibung |
|:-----|:-----|
|**1** <br/> |Senden des Endpunktdatenverkehrs der Kategorie „Optimize“ direkt und des sonstigen Datenverkehrs an den Proxyserver. <br/> |
|**2** <br/> |Senden des Endpunktdatenverkehrs der Kategorien „Optimize“ und „Allow“ direkt und des sonstigen Datenverkehrs an den Proxyserver. Mit diesem Typ können Sie auch den gesamten ExpressRoute für Office 365-Datenverkehr zu ExpressRoute-Netzwerksegmenten und den sonstigen Datenverkehr an den Proxyserver senden. <br/> |

Hier ein einfaches Beispiel für das Aufrufen des PowerShell-Skripts:

```powershell
Get-PacFile -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

Es gibt eine Reihe von Parametern, die Sie an das Skript weitergeben können:

| Parameter | Beschreibung |
|:-----|:-----|
|**ClientRequestId** <br/> |Dies ist erforderlich, und es handelt sich um einen GUID, der an den Webdienst übergeben wird, der den Clientcomputer darstellt, der den Anruf macht. <br/> |
|**Instanz** <br/> |Die Instanz des Office 365-Diensts, die standardmäßig auf „Weltweit“ eingestellt ist. Sie wird ebenfalls an den Webdienst übergeben. <br/> |
|**TenantName** <br/> |Der Name Ihres Office 365-Mandanten. Wird an den Webdienst übergeben und in einigen Office 365-URLs als ersetzbarer Parameter verwendet. <br/> |
|**Typ** <br/> |Der Typ der Proxy-PAC-Datei, die Sie generieren möchten. <br/> |

Hier ist ein weiteres Beispiel für das Aufrufen des PowerShell-Skripts mit zusätzlichen Parametern:

```powershell
Get-PacFile -Type 2 -Instance Worldwide -TenantName Contoso -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7
```

## <a name="proxy-server-bypass-processing-of-office-365-network-traffic"></a>Umgehungsverarbeitung des Office 365-Netzwerkdatenverkehrs durch einen Proxyserver

Wo PAC-Dateien für den direkten ausgehenden Datenverkehr nicht verwendet werden, sollten Sie die Verarbeitung auf ihrem Umkreisnetzwerk trotzdem weiterhin umgehen, indem Sie Ihren Proxyserver entsprechend konfigurieren. Einige Anbieter von Proxyservern haben diese automatisierte Konfiguration aktiviert, wie sie in [Office 365 Networking Partner Program](microsoft-365-networking-partner-program.md) beschrieben ist.

Wenn Sie dies manuell durchführen möchten, benötigen Sie die Daten der Endpunkt-Kategorien „Optimize“ und „Allow“ der Office 365-IP-Adresse und des URL-Webdienstes, um ihren Proxyserver so zu konfigurieren, dass er ihre Verarbeitung umgeht. Es ist wichtig, die SSL-Unterbrechung und -Überprüfung und die Proxyauthentifizierung mit den Endpunkten der Kategorien „Optimize“ und „Allow“ zu vermeiden.
  
<a name="bkmk_changes"> </a>
## <a name="change-management-for-office-365-ip-addresses-and-urls"></a>Änderungsverwaltung für Office 365-IP-Adressen und-URLs

Zusätzlich zur Auswahl der geeigneten Konfiguration für Ihre Netzwerkumgebung, müssen Sie auch einen Änderungsverwaltungsprozess für Office 365-Endpunkte einrichten. Diese Endpunkte ändern sich regelmäßig, und wenn Sie die Änderungen nicht verwalten, kann das dazu führen, dass Benutzer blockiert werden oder sich die Leistung verschlechtert, nachdem eine neue IP-Adresse oder URL hinzugefügt worden ist.

Änderungen an den Office 365-IP-Adressen und -URLs werden üblicherweise am letzten Tag eines jeden Monats veröffentlicht. Es aber kann vorkommen, dass eine Änderung aufgrund von Betriebs-, Support- oder Sicherheitsanforderungen auch zu einem anderen Zeitpunkt veröffentlicht wird.

Wenn eine Änderung veröffentlicht wird, die Ihr Eingreifen erforderlich macht, da eine IP-Adresse oder URL hinzugefügt wurde, können Sie davon ausgehen, dass es ab dem Zeitpunkt der Veröffentlichung 30 Tage dauert, bis ein Office 365-Dienst für diesen Endpunkt vorhanden ist. Obwohl wir diesen Benachrichtigungszeitraum anstreben, ist dies aufgrund von Betriebs-, Support- oder Sicherheitsanforderungen unter Umständen nicht immer möglich. Über Änderungen, für die keine sofortigen Maßnahmen erforderlich sind, um die Verbindung aufrechtzuerhalten, wie z. b. entfernte IP-Adressen oder URLs oder weniger signifikante Änderungen, erhalten Sie keine Vorabbenachrichtigung. Unabhängig davon, welche Benachrichtigung bereitgestellt wird, wird für jede Änderung der Termin der Aktivierung des Dienstes aufgelistet.

### <a name="change-notification-using-the-web-service"></a>Änderungsbenachrichtigungen mithilfe des Webdiensts

Sie können den Office 365-IP-Adresse und -URL-Webdienst verwenden, um eine Änderungsbenachrichtigung zu erhalten. Wir empfehlen, die **/version**-Webmethode einmal pro Stunde aufzurufen, um die Version der Endpunkte zu überprüfen, die Sie für die Verbindung zu Office 365 verwenden. Wenn sich diese Version im Vergleich zu der von Ihnen verwendeten Version ändert, sollten Sie die neuesten Endpunktdaten aus der **/endpoints**-Webmethode und optional die Unterschiede aus der **/changes**-Webmethode abrufen. Wenn die von Ihnen gefundene Version nicht geändert wurde, müssen Sie die **/endpoints**- und **/changes**-Webmethode nicht aufrufen.

Weitere Informationen finden Sie unter [Office 365-IP-Adresse und -URL-Webdienst](microsoft-365-ip-web-service.md).

### <a name="change-notification-using-rss-feeds"></a>Änderungsbenachrichtigungen mithilfe von RSS-Feeds

Der Office 365-IP-Adresse- und -URL-Webdienst bietet einen Feed, den Sie in Outlook abonnieren können. Es gibt Links zu den RSS-URLs auf den einzelnen Office 365 Service instanzspezifischen Seiten für die IP-Adressen und URLs. Weitere Informationen finden Sie unter [Office 365-IP-Adresse und -URL-Webdienst](microsoft-365-ip-web-service.md).

### <a name="change-notification-and-approval-review-using-microsoft-flow"></a>Änderungsbenachrichtigungen und Genehmigungsüberprüfungen mit Microsoft Flow

Uns ist bewusst, dass Sie möglicherweise weiterhin die monatlichen Änderungen an Netzwerkendpunkten manuell vornehmen müssen. Sie können Microsoft Flow zum Erstellen eines Workflows verwenden, der Sie per E-Mail benachrichtigt, und optional einen Genehmigungsprozess anstößt, wenn Änderungen an den Office 365-Netzwerkendpunkten vorgenommen werden müssen. Nach Abschluss der Überprüfung können Sie den Workflow per E-Mail automatisch an Ihr Firewall- und das Proxyserver-Managementteam senden.

Informationen über ein Microsoft Flow-Beispiel und eine -Vorlage finden sie unter [Verwenden von Microsoft Flow, um eine E-Mail wegen Änderungen an Office 365-IP-Adressen und -URLs zu erhalten](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/td-p/240651).
  
<a name="FAQ"> </a>
## <a name="office-365-network-endpoints-faq"></a>Häufig gestellte Fragen zu Office 365-Netzwerkendpunkten

Häufig gestellte Administratorfragen zur Office 365-Konnektivität:
  
### <a name="how-do-i-submit-a-question"></a>Wie übermittle ich eine Frage?

Klicken Sie auf den Link unten, um anzugeben, ob die Artikel hilfreich war, und weiteren Fragen zu übermitteln. Wir überwachen das Feedback und aktualisieren die Liste der am häufigsten gestellten Fragen.
  
### <a name="how-do-i-determine-the-location-of-my-tenant"></a>Wie kann ich den Standort meines Mandanten ermitteln?

 Der **Mandantenstandort** lässt sich am besten mit unserer [Karte der Rechenzentren](https://aka.ms/datamaps) ermitteln.
  
### <a name="am-i-peering-appropriately-with-microsoft"></a>Bin ich in geeigneter Weise über Peering mit Microsoft verbunden?

 Die **Peeringstandorte** werden unter [Peering mit Microsoft](https://www.microsoft.com/peering) im Detail beschrieben.
  
Mit mehr als 2500 ISP-Peeringbeziehungen weltweit und 70 Präsenzpunkten sollte der Zugang aus Ihrem Netzwerk in unseres nahtlos möglich sein. Es lohnt sich, ein paar Minuten zu investieren, um sicherzustellen, dass die Peeringbeziehung Ihres ISPs optimal ist. [Hier finden Sie ein paar Beispiele](https://blogs.technet.microsoft.com/onthewire/2017/03/22/__guidance/) guter und weniger guter Peeringübergaben an Ihr Netzwerk.
  
<a name="bkmk_MissingIP"> </a>
### <a name="i-see-network-requests-to-ip-addresses-not-on-the-published-list-do-i-need-to-provide-access-to-them"></a>Ich sehe Netzwerkanforderungen an IP-Adressen, die nicht in der Liste "Veröffentlicht" angezeigt werden. Muss ich Zugriff auf diese Netzwerkanforderungen zulassen?

In der Liste werden nur IP-Adressen für die Office 365-Server angezeigt, zu denen Sie direkt routen sollten. Es handelt sich nicht um eine vollständige Liste aller IP-Adressen, für die Netzwerkanforderungen angezeigt werden. Es werden Netzwerkanforderungen Microsoft und unveröffentlichte IP-Adressen von Drittanbietern angezeigt. Diese IP-Adressen werden dynamisch generiert oder auf eine Weise verwaltet, die bei Änderungen eine rechtzeitige Benachrichtigung verhindert. Wenn Ihre Firewall den Zugriff für diese Netzwerkanforderungen nicht basierend auf den FQDNs zulassen kann, verwenden Sie zum Verwalten der Anforderungen eine PAC- oder WPAD-Datei.
  
Sie sehen eine Office 365 zugeordnete IP-Adresse, über die Sie weitere Informationen erhalten möchten?
  
1. Überprüfen Sie mithilfe eines CIDR-Rechners, ob die IP-Adresse in einem größeren veröffentlichten Bereich enthalten ist, z. B. dem für [IPv4](https://www.ipaddressguide.com/cidr) oder [IPv6](https://www.ipaddressguide.com/ipv6-cidr).. Beispielsweise enthält 40.96.0.0/13 die IP-Adresse 40.103.0.1, obwohl 40.96 nicht mit 40.103 übereinstimmt.
2. Überprüfen Sie mithilfe einer [Whois-Abfrage](https://dnsquery.org/), ob die IP-Adresse einem Partner gehört. Wenn die IP-Adresse von Microsoft betrieben wird, kann es sich um einen internen Partner handeln. Viele Partnernetzwerk-Endpunkte werden als zur _Standardkategorie_ gehörend aufgelistet, für die keine IP-Adressen veröffentlicht werden.
3. Die IP-Adresse darf nicht Teil von Office 365 oder einer Abhängigkeit sein. Die Office 365-Netzwerkendpunkt-Veröffentlichung umfasst nicht alle Microsoft-Netzwerkendpunkte.
4. Überprüfen Sie das Zertifikat, stellen Sie in einem Browser unter Verwendung von *HTTPS://\<IP_ADDRESS\>* eine Verbindung mit der IP-Adresse her, und überprüfen Sie die auf dem Zertifikat aufgelisteten Domänen, um zu verstehen, welche Domänen der IP-Adresse zugeordnet sind. Wenn es sich um eine von Microsoft betriebene IP-Adresse handelt, die sich nicht in der Liste der Office 365-IP-Adressen befindet, ist die IP-Adresse wahrscheinlich einem Microsoft-CDN, z. B. *MSOCDN.NET*, oder einer anderen Microsoft-Domäne ohne veröffentlichte IP-Informationen zugeordnet. Wenn Sie feststellen, dass es sich bei der Domäne auf dem Zertifikat um eine Domäne handelt, für die die IP-Adresse aufgelistet sein sollte, teilen Sie uns dies bitte mit.

<a name="bkmk_cname"> </a>
### <a name="some-office-365-urls-point-to-cname-records-instead-of-a-records-in-the-dns-what-do-i-have-to-do-with-the-cname-records"></a>Einige Office 365-URLs verweisen auf CNAME-Einträge anstelle von A-Einträgen im DNS. Was muss ich mit den CNAME-Einträgen tun?

Clientcomputer benötigen einen DNS A- oder AAAA-Eintrag, der mindestens eine IP-Adresse enthält, um eine Verbindung mit einem Clouddienst herzustellen. Einige URLs in Office 365 zeigen CNAME-Einträge anstelle von A- oder AAAA-Einträgen an. Diese CNAME-Einträge sind zwischengeschaltet und es können mehrere als Kette vorhanden sein. Sie werden immer in einen A- oder AAAA-Eintrag für eine IP-Adresse aufgelöst. Sehen Sie sich beispielsweise die folgende Liste von DNS-Einträgen an, die schließlich in die IP-Adresse _IP_1_ aufgelöst werden:

```console
serviceA.office.com -> CNAME: serviceA.domainA.com -> CNAME: serviceA.domainB.com -> A: IP_1
```

Diese CNAME-Umleitungen sind ein normaler Bestandteil des DNS, und für den Clientcomputer wie für den Proxyserver transparent. Sie werden für den Lastenausgleich, Netzwerke für die Inhaltsübermittlung, hohe Verfügbarkeit und die Minimierung von Servicevorfällen verwendet. Microsoft veröffentlicht die zwischengeschalteten CNAME-Einträge nicht. Sie können sich jederzeit ändern, und Sie sollten Sie in Ihrem Proxyserver nicht als zulässig konfigurieren.

Ein Proxy Server überprüft die anfängliche URL, im obigen Beispiel ServiceA.Office.com, und diese URL wäre in der Office 365-Veröffentlichung enthalten. Der Proxy Server fordert die DNS-Auflösung dieser URL in eine IP-Adresse an und empfängt IP_1. Er überprüft dabei nicht die Einträge der zwischengeschalteten CNAME-Einträge.

Hartcodiert Konfigurationen oder auf indirekten vollständig qualifizierten Office 365-Domänennamen basierendes Whitelisting wird nicht empfohlen und nicht von Microsoft unterstützt, da bekannt ist, dass dabei Probleme mit der Verbindung zu Kunden entstehen. DNS-Lösungen, die die CNAME-Umleitung blockieren oder die Office 365-DNS-Einträge andernfalls falsch auflösen, können bei aktivierter DNS-Rekursion über die DNS-bedingte Weiterleitung behoben werden (für direkt verwendete vollständig qualifizierte Office 365-Domänennamen). Viele Netzwerkperimeterprodukte von Drittanbietern integrieren die empfohlenen Whitelists für Office 365-Endpunkte mithilfe des [Office 365-IP-Adress- und URL-Webdiensts](microsoft-365-ip-web-service.md) direkt in ihre Konfiguration.

<a name="bkmk_akamai"> </a>
### <a name="why-do-i-see-names-such-as-nsatcnet-or-akadnsnet-in-the-microsoft-domain-names"></a>Warum enthalten Microsoft-Domänennamen Namen wie "nsatc.net" oder "akadns.net"?

Office 365 und andere Microsoft-Dienste nutzen verschiedene Drittanbieterdienste wie Akamai und MarkMonitor, um die Office 365-Benutzererfahrung zu optimieren. Um stets die besten Ergebnisse zu ermöglichen, können sich diese Dienste in Zukunft ändern. Drittanbieterdomänen können Inhalt, z. B. ein CDN, oder einen Dienst, z. B. einen geographische Datenverkehrsverwaltungsdienst, hosten. Zu den derzeit genutzten Dienste gehören unter anderem:
  
[MarkMonitor](https://www.markmonitor.com/) wird verwendet, wenn Sie Anforderungen sehen, die *\*.nsatc.net* enthalten. Dieser Dienst bietet Schutz und Überwachung von Domänennamen zum Schutz vor böswilligem Verhalten.
  
[ExactTarget](https://www.marketingcloud.com/) wird verwendet, wenn Sie Anforderungen an *\*.exacttarget.com* sehen. Dieser Dienst bietet E-Mail-Linkverwaltung und Überwachung vor böswilligem Verhalten.
  
[Akamai](https://www.akamai.com/) wird verwendet, wenn Sie Anforderungen sehen, die einen der folgenden vollqualifizierten Domänennamen enthalten. Dieser Dienst stellt Geo-DNS- und CDN-Dienste (Content Delivery Network) bereit.
  
```console
*.akadns.net
*.akam.net
*.akamai.com
*.akamai.net
*.akamaiedge.net
*.akamaihd.net
*.akamaized.net
*.edgekey.net
*.edgesuite.net
```

<a name="bkmk_thirdparty"> </a>
### <a name="i-have-to-have-the-minimum-connectivity-possible-for-office-365"></a>Ich benötige die geringstmögliche Konnektivität für Office 365

Office 365 ist eine Suite von Diensten, die für die Verwendung über das Internet konzipiert sind. Die Versprechen hinsichtlich Zuverlässigkeit und Verfügbarkeit basieren auf der Verfügbarkeit zahlreicher Standardinternetdienste. Standardinternetdienste wie DNS, CRL und CDNs müssen beispielsweise erreichbar sein, um Office 365 zu verwenden, genau so, wie es für die meisten modernem Internetdienste der Fall ist.

Die Office 365-Suite ist in ihre wichtigsten Dienstbereiche unterteilt. Diese können für die Verbindung selektiv aktiviert werden, und es gibt einen gemeinsamen Bereich, von dem alle Dienste abhängig sind und die immer erforderlich sind.

| Dienstbereich | Beschreibung |
|:-----|:-----|
|**Exchange** <br/> |Exchange Online und Exchange Online Protection <br/> |
|**SharePoint** <br/> |SharePoint Online und OneDrive for Business <br/> |
|**Skype for Business Online und Microsoft Teams** <br/> |Skype for Business auf Microsoft Teams <br/> |
|**Standard** <br/> |Office 365 pro Plus, Office in einem Browser, Azure AD und andere häufige Netzwerkendpunkte <br/> |

Zusätzlich zu diesen grundlegenden Internetdiensten gibt es Drittanbieterservices, die nur zur Integration zusätzlicher Funktionalitäten dienen. Diese Dienste sind zwar für die Integration erforderlich, im Artikel über Office 365-Endpunkte sind sie jedoch als optional gekennzeichnet, d. h. die Kernfunktionen des Diensts funktionieren auch dann weiterhin, wenn kein Zugriff auf den Endpunkt besteht. Bei jedem benötigten Netzwerkendpunkt muss das erforderliche Attribut „wahr“ festgelegt sein. Bei jedem optionalen Netzwerkendpunkt wird das erforderliche Attribut auf „falsch“ festgelegt, und das Attribut „Notizen“ enthält die fehlenden Funktionalitäten, die Sie bei blockierter Konnektivität erwarten sollten.
  
Wenn Sie versuchen, Office 365 zu verwenden und feststellen, dass Sie auf Dienste von Drittanbietern nicht zugreifen können, sollten Sie [sicherstellen, dass für alle vollqualifizierten Domänennamen, die in diesem Artikel als erforderlich oder optional gekennzeichnet sind, der Zugriff durch Proxy und Firewall erlaubt ist](urls-and-ip-address-ranges.md).
  
<a name="bkmk_consumer"> </a>
### <a name="how-do-i-block-access-to-microsofts-consumer-services"></a>Wie blockiere ich den Zugriff auf Microsoft-Services für Endverbraucher?

Das Blockieren des Zugriffs auf unsere Services für Endverbraucher geschieht auf eigene Gefahr. Die einzige zuverlässige Methode zum Blockieren der Services für Endverbraucher ist das Einschränken des Zugriffs auf den vollqualifizierten Domänennamen*Login.Live.com*. Dieser vollqualifizierte Domänenname wird von einer großen Zahl von Diensten verwendet, einschließlich Nicht-Verbraucherdienste wie MSDN, TechNet und anderen. Dieser vollqualifizierte Domänenname wird auch vom Secure File Exchange-Programm des Microsoft-Supports und für die Übertragung von Dateien verwendet, die Problembehandlung bei Microsoft-Produkten erleichtern.  Das Einschränken des Zugriffs auf diesen vollqualifizierten Domänennamen kann dazu führen, dass außerdem Ausnahmen zur Regel für Netzwerkanforderungen im Zusammenhang mit diesen Diensten eingeschlossen werden müssen.
  
Beachten Sie, dass das Blockieren des Zugriffs auf die Microsoft-Verbraucherdienste allein nicht verhindert, dass andere Personen in Ihrem Netzwerk Informationen unter Verwendung eines Office 365-Mandanten oder eines anderen Diensts exfiltrieren können. 


<a name="bkmk_IPOnlyFirewall"> </a>
### <a name="my-firewall-requires-ip-addresses-and-cannot-process-urls-how-do-i-configure-it-for-office-365"></a>Meine Firewall benötigt IP-Adressen und kann keine URLs verarbeiten. Wie konfiguriere ich sie für Office 365?

Office 365 stellt nicht die IP-Adressen aller erforderlichen Netzwerkendpunkte zur Verfügung. Einige werden nur als URLs bereitgestellt und sind als Standard kategorisiert. URLs in der Standardkategorie, die erforderlich sind, sollten über einen Proxyserver zugelassen werden. Wenn Sie über keinen Proxyserver verfügen, schauen Sie sich die Konfiguration der Webanforderungen für URLs an, die Benutzer in die Adressleiste eines Webbrowsers eingeben. Der Benutzer gibt auch keine IP-Adresse an. Die URLs der Office 365-Standardkategorie, die keine IP-Adressen angeben, sollten auf die gleiche Weise konfiguriert werden.

## <a name="related-topics"></a>Verwandte Themen

[Office 365 – IP-Adress- und URL-Webdienst](microsoft-365-ip-web-service.md)

[IP-Bereiche von Microsoft Azure-Rechenzentren](https://www.microsoft.com/download/details.aspx?id=41653)
  
[Öffentlicher Microsoft IP-Bereich](https://www.microsoft.com/download/details.aspx?id=53602)
  
[Anforderungen an die Netzwerkinfrastruktur für Microsoft Intune](https://docs.microsoft.com/intune/get-started/network-infrastructure-requirements-for-microsoft-intune)
  
[ExpressRoute und Power BI](https://powerbi.microsoft.com/documentation/powerbi-admin-power-bi-expressroute/)
  
[URLs und IP-Adressbereiche für Office 365](urls-and-ip-address-ranges.md)
  
[Verwalten von ExpressRoute für Office 365-Verbindungen](managing-expressroute-for-connectivity.md)
  
[Prinzipien von Office 365-Netzwerkverbindungen](microsoft-365-network-connectivity-principles.md)
