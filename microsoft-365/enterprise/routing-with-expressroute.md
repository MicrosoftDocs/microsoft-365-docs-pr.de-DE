---
title: Routing mit ExpressRoute für Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: e1da26c6-2d39-4379-af6f-4da213218408
description: In diesem Artikel erfahren Sie mehr über Azure ExpressRoute-Routinganforderungen, -Schaltungen und Routingdomänen für die Verwendung mit Office 365.
ms.openlocfilehash: 9d3c381cfb6e24c1c87ef3dcfb83a9b93f991b93
ms.sourcegitcommit: 1244bbc4a3d150d37980cab153505ca462fa7ddc
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51222407"
---
# <a name="routing-with-expressroute-for-office-365"></a>Routing mit ExpressRoute für Office 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Um den Routingdatenverkehr zu Office 365 mithilfe von Azure ExpressRoute richtig zu verstehen, benötigen Sie ein festes Verständnis der wichtigsten [ExpressRoute-Routinganforderungen](/azure/expressroute/expressroute-routing) sowie der ExpressRoute-Schaltungen und [Routingdomänen.](/azure/expressroute/expressroute-circuit-peerings) Diese legen die Grundlagen für die Verwendung von ExpressRoute fest, auf die Sich Office 365-Kunden verlassen.
  
Zu den wichtigsten Elementen in den oben genannten Artikeln, die Sie verstehen müssen, gehören:
  
- ExpressRoute-Schaltungen werden nicht einer bestimmten physischen Infrastruktur zugeordnet, sondern sind eine logische Verbindung, die von Microsoft und einem Peeringanbieter in Ihrem Auftrag an einem einzelnen Peeringstandort hergestellt wird.

- Es gibt eine 1:1-Zuordnung zwischen einer ExpressRoute-Schaltung und einem Kundenschlüssel.

- Jede Schaltung kann zwei unabhängige Peeringbeziehungen unterstützen (Azure Private Peering und Microsoft Peering); Office 365 erfordert Microsoft-Peering.

- Jede Schaltung verfügt über eine feste Bandbreite, die für alle Peeringbeziehungen freigegeben wird.

- Alle öffentlichen IPv4-Adressen und öffentlichen AS-Nummern, die für die ExpressRoute-Schaltung verwendet werden, müssen als Eigentum von Ihnen überprüft oder ausschließlich vom Besitzer des Adressbereichs zugewiesen werden.

- Die virtuellen ExpressRoute-Schaltungen sind global redundant und folgen standardmäßigen BGP-Routingmethoden. Aus diesem Grund empfehlen wir zwei physische Schaltungen pro Auslauf an Ihren Anbieter in einer aktiven/aktiven Konfiguration.

Weitere Informationen [zu unterstützten](/azure/expressroute/expressroute-faqs) Diensten, Kosten und Konfigurationsdetails finden Sie auf der Seite HÄUFIG GESTELLTE Fragen. Informationen zur Liste der Konnektivitätsanbieter, die Microsoft-Peering-Support anbieten, finden Sie im Artikel [expressRoute locations.](/azure/expressroute/expressroute-locations) Außerdem haben wir eine 10- teilige [Azure ExpressRoute für Office 365-Schulungsreihe](https://channel9.msdn.com/series/aer) auf Kanal 9 aufgezeichnet, um die Konzepte gründlicher zu erläutern.
  
## <a name="ensuring-route-symmetry"></a>Sicherstellen der Routensymmetrie

Auf die Office 365-Front-End-Server kann sowohl im Internet als auch auf ExpressRoute zugegriffen werden. Diese Server werden es vorziehen, über ExpressRoute-Schaltungen zurück an die lokale Route zu gehen, wenn beide verfügbar sind. Aus diesem Grund besteht die Möglichkeit der Routenasymmetrie, wenn Datenverkehr aus Ihrem Netzwerk die Route über Ihre Internetschaltungen bevorzugt. Asymmetrische Routen sind ein Problem, da Geräte, die zustandsbehaftete Paketprüfungen durchführen, den Datenverkehr blockieren können, der einen anderen Pfad als die ausgehenden Pakete folgt.
  
Unabhängig davon, ob Sie eine Verbindung mit Office 365 über das Internet oder ExpressRoute initiieren, muss es sich bei der Quelle um eine öffentlich routingfähige Adresse sein. Da viele Kunden direkt mit Microsoft peeren, ist es nicht möglich, private Adressen zu haben, bei denen Duplizierungen zwischen Kunden möglich sind.
  
Im Folgenden werden Szenarien beschrieben, in denen die Kommunikation von Office 365 zu Ihrem lokalen Netzwerk initiiert wird. Um Ihren Netzwerkentwurf zu vereinfachen, empfehlen wir das Routing über den Internetpfad.
  
- SMTP-Dienste wie E-Mails von einem Exchange Online-Mandanten an einen lokalen Host oder SharePoint Online-E-Mails, die von SharePoint Online an einen lokalen Host gesendet werden. Das SMTP-Protokoll wird im Netzwerk von Microsoft breiter verwendet als die Überleitungspräfixe, die über ExpressRoute-Schaltungen und lokale SMTP-Server über ExpressRoute geteilt werden, führen zu Fehlern bei diesen anderen Diensten.

- ADFS während der Kennwortüberprüfung für die Anmeldung.

- [Exchange Server Hybridbereitstellungen](/exchange/exchange-hybrid).

- [SharePoint-Verbundhybridsuche](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online).

- [SharePoint-Hybrid-BCS](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution).

- [Skype for Business Hybrid-](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) und/oder [Skype for Business-Verbund](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

- [Skype for Business Cloud Connector](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Damit Microsoft für diese bidirektionalen Datenverkehrsflüsse zurück zu Ihrem Netzwerk routen kann, müssen die BGP-Routen zu Ihren lokalen Geräten mit Microsoft geteilt werden. Wenn Sie Routenpräfixe an Microsoft über ExpressRoute ankündigen, sollten Sie die folgenden bewährten Methoden befolgen:

1) Bewerben Sie nicht dasselbe öffentliche IP-Adressroutenpräfix für das öffentliche Internet und über ExpressRoute. Es wird empfohlen, dass die Ankündigungen des IP-BGP-Routenpräfixs an Microsoft über ExpressRoute aus einem Bereich kommen, der überhaupt nicht im Internet angekündigt wird. Wenn dies aufgrund des verfügbaren IP-Adressraums nicht möglich ist, müssen Sie sicherstellen, dass Sie einen spezifischeren Bereich über ExpressRoute bewerben als alle Internetschaltungen.

2) Verwenden Sie separate NAT-IP-Pools pro ExpressRoute-Schaltung und separat für die Ihrer Internetschaltungen.

3) Beachten Sie, dass jede an Microsoft angekündigte Route Netzwerkdatenverkehr von jedem Server im Netzwerk von Microsoft anlockt, nicht nur von denen, für die Routen über ExpressRoute an Ihr Netzwerk angekündigt werden. Bewerben Sie nur Routen zu Servern, auf denen Routingszenarien von Ihrem Team definiert und verstanden werden. Ankündigung separater IP-Adressroutenpräfixe für jede von mehreren ExpressRoute-Leitungen aus Ihrem Netzwerk.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Entscheiden, welche Anwendungen und Features über ExpressRoute geroutet werden

Wenn Sie eine Peeringbeziehung mithilfe der Microsoft-Peeringroutingdomäne konfigurieren und für den entsprechenden Zugriff genehmigt sind, können Sie alle über ExpressRoute verfügbaren PaaS- und SaaS-Dienste sehen. Die für ExpressRoute entworfenen Office 365-Dienste können mit [BGP-Communitys](./bgp-communities-in-expressroute.md) oder [Routenfiltern verwaltet werden.](/azure/expressroute/how-to-routefilter-portal)
  
Bei anderen Anwendungen wie Office 365 Video handelt es sich um eine Office 365-Anwendung. Office 365 Video besteht jedoch aus drei verschiedenen Komponenten, dem Portal, dem Streamingdienst und dem Netzwerk für die Inhaltszustellung. Das Portal ist in SharePoint Online, der Streamingdienst in Azure Media Services und das Netzwerk für die Inhaltszustellung innerhalb des Azure CDNs enthalten. In der folgenden Tabelle sind diese Komponenten aufgeführt.

|**Komponente**|**Zugrunde liegende Anwendung**|**In der SharePoint Online -BGP-Community enthalten?**|**Verwendung**|
|:-----|:-----|:-----|:-----|
|Office 365-Videoportal  <br/> |SharePoint Online  <br/> |Ja  <br/> |Konfiguration, Hochladen  <br/> |
|Office 365 Video streaming service  <br/> |Azure Media Services  <br/> |Nein  <br/> |Streamingdienst, der für den Fall verwendet wird, dass das Video nicht im CDN verfügbar ist  <br/> |
|Office 365 Video Content Delivery Network  <br/> |Azure CDN  <br/> |Nein  <br/> |Primäre Quelle für Videodownload/Streaming. [Erfahren Sie mehr über Office 365-Videonetzwerke.](https://support.office.com/article/Office-365-Video-networking-Frequently-Asked-Questions-FAQ-2bed67a1-4052-49ff-a4ce-b7e6530eb98e)  <br/> |

Jede der Office 365-Features, die über Microsoft-Peering verfügbar sind, sind im [Artikel office 365-Endpunkte](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) nach Anwendungstyp und FQDN aufgeführt. Der Grund für die Verwendung des FQDN in den Tabellen ist, dass Kunden Datenverkehr mithilfe von PAC-Dateien oder anderen Proxykonfigurationen verwalten können. Weitere Informationen finden Sie in unserem Leitfaden zum Verwalten von [Office 365-Endpunkten,](./managing-office-365-endpoints.md) z. B. PAC-Dateien.
  
In einigen Situationen haben wir eine Platzhalterdomäne verwendet, in der ein oder mehrere Unter-FQDNs anders als die Platzhalterdomäne auf höherer Ebene angekündigt werden. Dies geschieht in der Regel, wenn der Platzhalter eine lange Liste von Servern darstellt, die alle für ExpressRoute und das Internet angekündigt werden, während eine kleine Teilmenge von Zielen nur für das Internet oder umgekehrt angekündigt wird. In den folgenden Tabellen finden Sie Informationen dazu, wo sich die Unterschiede befinden.
  
In dieser Tabelle werden die Platzhalter-FQDNs angezeigt, die sowohl für das Internet als auch für Azure ExpressRoute angekündigt werden, zusammen mit den Teil-FQDNs, die nur für das Internet angekündigt werden.

|**Für ExpressRoute- und Internetschaltungen angekündigte Platzhalterdomäne**|**Sub-FQDN nur für Internetschaltungen angekündigt**|
|:-----|:-----|
|\*.microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*.officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

In der Regel sollen PAC-Dateien Netzwerkanforderungen an von ExpressRoute angekündigte Endpunkte direkt an die Leitung und alle anderen Netzwerkanforderungen an Ihren Proxy senden. Wenn Sie eine PAC-Datei wie die folgende konfigurieren, erstellen Sie die PAC-Datei in der folgenden Reihenfolge:
  
1. Schließen Sie die Unter-FQDNs aus Spalte 2 in die obige Tabelle oben in Der PAC-Datei ein, und senden Sie den Datenverkehr an Ihren Proxy. Wir haben eine Beispiel-PAC-Datei für Sie erstellt, die Sie in unserem Artikel zum Verwalten von [Office 365-Endpunkten verwenden können.](./managing-expressroute-for-connectivity.md)

2. Schließen Sie alle FQDNs ein, die [für](./urls-and-ip-address-ranges.md) ExpressRoute in diesem Artikel unterhalb des ersten Abschnitts angekündigt sind, und senden Sie den Datenverkehr direkt an Ihre ExpressRoute-Schaltung.

3. Schließen Sie alle anderen Netzwerkendpunkte oder Regeln unter diesen beiden Einträgen ein, und senden Sie den Datenverkehr an Ihren Proxy.

In dieser Tabelle werden die Platzhalterdomänen angezeigt, die für Internetschaltungen nur zusammen mit den Unter-FQDNs angekündigt werden, die für Azure ExpressRoute- und Internetschaltungen angekündigt werden. Für Die oben aufgeführte PAC-Datei werden die FQDNs in Spalte 2 in der folgenden Tabelle als angekündigt für ExpressRoute in dem Link aufgeführt, auf den verwiesen wird, was bedeutet, dass sie in der zweiten Gruppe von Einträgen in der Datei enthalten wären.

|**Nur für Internetschaltungen angekündigte Platzhalterdomäne**|**Teil-FQDN für ExpressRoute- und Internetschaltungen angekündigt**|
|:-----|:-----|
|\*.office.com  <br/> |\*.outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*.office.net  <br/> |agent.office.net  <br/> |
|\*.office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*.outlook.com  <br/> |\*.protection.outlook.com  <br/> \*.mail.protection.outlook.com  <br/> autodiscover- \<tenant\> .outlook.com  <br/> |
|\*.windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Routing von Office 365-Datenverkehr über das Internet und ExpressRoute

Um zur Office 365-Anwendung Ihrer Wahl zu routen, müssen Sie eine Reihe wichtiger Faktoren bestimmen.
  
1. Wie viel Bandbreite die Anwendung benötigt. Das Sampling der vorhandenen Verwendung ist die einzige zuverlässige Methode, um dies in Ihrer Organisation zu ermitteln.

2. Von welchem Ausgangsstandort möchten Sie den Netzwerkdatenverkehr verlassen. Sie sollten planen, die Netzwerklatenz für die Konnektivität mit Office 365 zu minimieren, da sich dies auf die Leistung auswirken wird. Da Skype for Business Sprach- und Videonachrichten in Echtzeit verwendet, ist es besonders anfällig für eine geringe Netzwerklatenz.

3. Wenn Sie möchten, dass expressRoute für alle oder eine Teilmenge Ihrer Netzwerkstandorte verwendet wird.

4. Von welchen Standorten ihr gewählter Netzwerkanbieter ExpressRoute anbietet.

Sobald Sie die Antworten auf diese Fragen ermittelt haben, können Sie eine ExpressRoute-Schaltung bereitstellen, die die Bandbreiten- und Standortanforderungen erfüllt. Weitere Unterstützung bei der Netzwerkplanung finden Sie im [Office 365-Netzwerkoptimierungshandbuch](./network-planning-and-performance.md) und in der Fallstudie, wie Microsoft die Netzwerkleistungsplanung [behandelt.](https://aka.ms/tunemsit)
  
### <a name="example-1-single-geographic-location"></a>Beispiel 1: Einzelner geografischer Standort
  
Dieses Beispiel ist ein Szenario für ein fiktives Unternehmen namens Trey Research, das über einen einzigen geografischen Standort verfügt.
  
Mitarbeiter von Trey Research dürfen nur eine Verbindung mit den Diensten und Websites im Internet herstellen, die die Sicherheitsabteilung explizit für das Paar ausgehender Proxys zulässt, die zwischen dem Unternehmensnetzwerk und dem Internetdienstanbieter liegen.
  
Trey Research plant die Verwendung von Azure ExpressRoute für Office 365 und erkennt, dass ein Teil des Datenverkehrs, z. B. Datenverkehr, der für Inhaltszustellungsnetzwerke bestimmt ist, nicht über die ExpressRoute für Office 365-Verbindung umleiten kann. Da der datenverkehr bereits standardmäßig an die Proxygeräte weitergeht, funktionieren diese Anforderungen weiterhin wie zuvor. Nachdem Trey Research ermittelt hat, dass sie die Azure ExpressRoute-Routinganforderungen erfüllen können, erstellen sie eine Schaltung, konfigurieren das Routing und verknüpfen die neue ExpressRoute-Schaltung mit einem virtuellen Netzwerk. Sobald die grundlegende Azure ExpressRoute-Konfiguration erstellt wurde, verwendet Trey Research die [#2-PAC-Datei,](./managing-office-365-endpoints.md)  die wir veröffentlichen, um Datenverkehr mit kundenspezifischen Daten über die direkten ExpressRoute für Office 365-Verbindungen zu routen.
  
Wie im folgenden Diagramm gezeigt, ist Trey Research in der Lage, die Anforderung zum Weiterleiten von Office 365-Datenverkehr über das Internet und eine Teilmenge des Datenverkehrs über ExpressRoute mithilfe einer Kombination aus Routing- und ausgehenden Proxykonfigurationsänderungen zu erfüllen.
  
1. Mithilfe der [#2 PAC-Datei,](./managing-office-365-endpoints.md) die wir veröffentlichen, um Datenverkehr über einen separaten Internet-Ausgangspunkt für Azure ExpressRoute für Office 365 zu routen.

2. Clients sind mit einer Standardroute zu den Proxys von Trey Research konfiguriert.

In diesem Beispielszenario verwendet Trey Research ein ausgehendes Proxygerät. Ebenso können Kunden, die Azure ExpressRoute für Office 365 nicht verwenden, diese Technik verwenden, um Datenverkehr basierend auf den Kosten für die Überprüfung des Datenverkehrs, der für bekannte Endpunkte mit hohem Volumen bestimmt ist, weiter zu routen.
  
Die FQDNs mit dem höchsten Volumen für Exchange Online, SharePoint Online und Skype for Business Online sind die folgenden:
  
![ExpressRoute-Kunden-Edgenetzwerk](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com, outlook.office.com

- \<tenant-name\>.sharepoint.com, \<tenant-name\> -my.sharepoint.com, \<tenant-name\> - \<app\> .sharepoint.com

- \*. Lync.com mit den IP-Bereichen für Nicht-TCP-Datenverkehr

- \*broadcast.officeapps.live.com, \* excel.officeapps.live.com, \* onenote.officeapps.live.com, \* powerpoint.officeapps.live.com, \* view.officeapps.live.com, \* visio.officeapps.live.com, \* word-edit.officeapps.live.com, \* word-view.officeapps.live.com, office.live.com

Erfahren Sie mehr [über das Bereitstellen](/archive/blogs/deploymentguys/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy) und Verwalten von Proxyeinstellungen in Windows 8 und sicherstellen, dass Office 365 nicht von Ihrem Proxy [gedrosselt wird.](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx)
  
Bei einer einzelnen ExpressRoute-Schaltung gibt es keine hohe Verfügbarkeit für Trey Research. Für den Fall, dass das redundante Edgegerätepaar von Trey, das die ExpressRoute-Verbindung bedient, ausfällt, gibt es keine zusätzliche ExpressRoute-Schaltung zum Failover. Dies belässt Trey Research in einer Predicament, da ein Ausfall in das Internet eine manuelle Neukonfiguration und in einigen Fällen neue IP-Adressen erfordert. Wenn Trey hohe Verfügbarkeit hinzufügen möchte, ist die einfachste Lösung, zusätzliche ExpressRoute-Schaltungen für jeden Standort hinzuzufügen und die Schaltungen aktiv/aktiv zu konfigurieren.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>Routing von ExpressRoute für Office 365 mit mehreren Standorten

Das letzte Szenario, das Routing von Office 365-Datenverkehr über ExpressRoute, ist die Grundlage für eine noch komplexere Routingarchitektur. Unabhängig von der Anzahl der Standorte, der Anzahl der Kontinente, auf denen diese Standorte vorhanden sind, der Anzahl der ExpressRoute-Schaltungen und so weiter, ist die Möglichkeit erforderlich, einen Teil des Datenverkehrs an das Internet und einen Teil des Datenverkehrs über ExpressRoute weiter zu leitet.
  
Die weiteren Fragen, die für Kunden mit mehreren Standorten in mehreren Regionen beantwortet werden müssen, sind:
  
1. Benötigen Sie an jedem Standort eine ExpressRoute-Schaltung? Wenn Sie Skype for Business Online verwenden oder die Latenzempfindlichkeit für SharePoint Online oder Exchange Online bedenken, wird an jedem Standort ein redundantes Paar aktiver/aktiver ExpressRoute-Schaltungen empfohlen. Weitere Informationen finden Sie im Skype for Business-Handbuch für Medienqualität und Netzwerkkonnektivität.

2. Wie soll office 365-Datenverkehr umgeleitet werden, wenn in einer bestimmten Region keine ExpressRoute-Schaltung verfügbar ist?

3. Was ist die bevorzugte Methode für die Konsolidierung des Datenverkehrs bei Netzwerken mit vielen kleinen Standorten?

Jede dieser Optionen stellt eine einzigartige Herausforderung dar, bei der Sie Ihr eigenes Netzwerk und die von Microsoft verfügbaren Optionen auswerten müssen.

|**Überlegungen**|**Auszuwertende Netzwerkkomponenten**|
|:-----|:-----|
|Schaltungen an mehreren Speicherorten  <br/> |Es wird empfohlen, mindestens zwei Schaltungen aktiv/aktiv zu konfigurieren.  <br/> Kosten-, Latenz- und Bandbreitenanforderungen müssen verglichen werden.  <br/> Verwenden Sie BGP-Routenkosten, PAC-Dateien und NAT, um Routing mit mehreren Leitungen zu verwalten.  <br/> |
|Routing von Standorten ohne ExpressRoute-Schaltung  <br/> |Es wird empfohlen, die Ausgangs- und DNS-Auflösung so nah wie die Person zu verwenden, die die Anforderung für Office 365 initiiert.  <br/> Die DNS-Weiterleitung kann verwendet werden, um Remotebüros das Ermitteln des entsprechenden Endpunkts zu ermöglichen.  <br/> Clients in der Remotebüro müssen über eine Route verfügen, die Zugriff auf die ExpressRoute-Schaltung bietet.  <br/> |
|Kleine Office-Konsolidierung  <br/> |Verfügbare Bandbreite und Datennutzung sollten sorgfältig verglichen werden.  <br/> |

> [!NOTE]
> Microsoft bevorzugt ExpressRoute über das Internet, wenn die Route unabhängig vom physischen Standort verfügbar ist.
  
Jede dieser Überlegungen muss für jedes eindeutige Netzwerk berücksichtigt werden. Nachfolgend finden Sie ein Beispiel.
  
### <a name="example-2-multi-geographic-locations"></a>Beispiel 2: Multi-geographic locations
  
Dieses Beispiel ist ein Szenario für ein fiktives Unternehmen namens Humongous Insurance mit mehreren geografischen Standorten.
  
Humongous Insurance ist geografisch mit Niederlassungen auf der ganzen Welt verteilt. Sie möchten Azure ExpressRoute für Office 365 implementieren, um den großteil ihres Office 365-Datenverkehrs über direkte Netzwerkverbindungen zu erhalten. Humongous Insurance verfügt auch über Büros auf zwei weiteren Kontinenten. Die Mitarbeiter in der Remotestelle, in der ExpressRoute nicht möglich ist, müssen an eine oder beide primäre Einrichtungen zurückgeleitet werden, um eine ExpressRoute-Verbindung zu verwenden.
  
Das Leitprinzip besteht in der schnellstmöglichen Datenübertragung von Office 365 an ein Microsoft-Datencenter. In diesem Beispiel muss humongous Insurance entscheiden, ob ihre Remotebüros über das Internet zu einem Microsoft-Rechenzentrum über eine beliebige Verbindung so schnell wie möglich umgeleitet werden sollen oder ob ihre Remotebüros über ein internes Netzwerk umgeleitet werden sollen, um so schnell wie möglich über eine ExpressRoute-Verbindung zu einem Microsoft-Rechenzentrum zu kommen.
  
Die Rechenzentren, Netzwerke und Anwendungsarchitekturen von Microsoft sind so konzipiert, dass sie global unterschiedliche Kommunikationen nutzen und diese so effizient wie möglich nutzen. Dies ist eines der größten Netzwerke der Welt. Anforderungen für Office 365, die länger als erforderlich in Kundennetzwerken verbleiben, können diese Architektur nicht nutzen.
  
In der Situation von Humongous Insurance sollten sie abhängig von den Anwendungen, die sie über ExpressRoute verwenden möchten, fortfahren. Wenn sie beispielsweise Ein Skype for Business Online-Kunde sind oder die Verwendung der ExpressRoute-Konnektivität beim Herstellen einer Verbindung mit externen Skype for Business Online-Besprechungen planen, wird im Skype for Business Online-Leitfaden für Medienqualität und Netzwerkkonnektivität empfohlen, eine zusätzliche ExpressRoute-Schaltung für den dritten Standort zur Verfügung zu stellen. Dies kann aus Netzwerksicht teurer sein. Das Weiterleiten von Anforderungen von einem Kontinent zu einem anderen vor der Bereitstellung an ein Microsoft-Rechenzentrum kann jedoch zu einer schlechten oder unbrauchbaren Erfahrung bei Skype for Business Online-Besprechungen und -Kommunikationen führen.
  
Wenn Humongous Insurance Skype for Business Online in keinem Fall verwendet oder nicht plant, ist das Routing von Office 365-Netzwerkdatenverkehr zurück zu einem Kontinent mit einer ExpressRoute-Verbindung möglich, kann jedoch unnötige Wartezeiten oder TCP-Überlastung verursachen. In beiden Fällen wird empfohlen, internetkontinierten Datenverkehr an das Internet am lokalen Standort zu weiterleiten, um die Von Office 365 verwendeten Netzwerke für die Inhaltszustellung zu nutzen.
  
![ExpressRoute multi-geography](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Wenn Humongous Insurance seine Multigeografiestrategie plant, gibt es eine Reihe von Dingen zu berücksichtigen, die die Größe der Schaltung, die Anzahl der Schaltungen, das Failover und so weiter berücksichtigen.
  
Mit ExpressRoute an einem einzigen Standort mit mehreren Regionen, die versuchen, die Schaltung zu verwenden, möchte Humongous Insurance sicherstellen, dass Verbindungen mit Office 365 von der Remotestelle an die nächstgelegene Zentrale des Office 365-Rechenzentrums gesendet und vom Standort der Zentrale empfangen werden. Zu diesem Zeitpunkt implementiert Humongous Insurance die DNS-Weiterleitung, um die Anzahl der Roundtrips und DNS-Suchen zu reduzieren, die erforderlich sind, um eine entsprechende Verbindung mit der Office 365-Umgebung herzustellen, die dem Internetausgangspunkt der Zentrale am nächsten ist. Dadurch wird verhindert, dass der Client einen lokalen Front-End-Server auflösen kann, und es wird sichergestellt, dass sich der Front-End-Server, den die Person verbindet, in der Nähe der Zentrale befindet, in der Humongous Insurance peering mit Microsoft führt. Sie können auch erfahren, [wie Sie eine bedingte Weiterleitung für einen Domänennamen zuweisen.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc794735(v=ws.10))
  
In diesem Szenario würde der Datenverkehr von der Remotestelle die Office 365-Front-End-Infrastruktur in Nordamerika auflösen und Office 365 verwenden, um eine Verbindung mit den Back-End-Servern gemäß der Architektur der Office 365-Anwendung herzustellen. Beispielsweise würde Exchange Online die Verbindung in Nordamerika beenden, und diese Front-End-Server würden eine Verbindung mit dem Back-End-Postfachserver herstellen, wo immer sich der Mandant befindet. Alle Dienste verfügen über einen weit verbreiteten Front-Door-Dienst, der aus Unicast- und Anycastzielen besteht.
  
Wenn Humongous über Hauptbüros auf mehreren Kontinenten verfügt, werden mindestens zwei aktive/aktive Schaltungen pro Region empfohlen, um die Wartezeit für vertrauliche Anwendungen wie Skype for Business Online zu reduzieren. Wenn sich alle Büros auf einem einzigen Kontinent befinden oder keine Echtzeitzusammenarbeit verwenden, ist es eine kundenspezifische Entscheidung, einen konsolidierten oder verteilten Ausgangspunkt zu haben. Wenn mehrere Schaltungen verfügbar sind, stellt das BGP-Routing ein Failover sicher, wenn eine einzelne Leitung nicht mehr verfügbar ist.
  
Erfahren Sie mehr über [Beispielroutingkonfigurationen und](/azure/expressroute/expressroute-config-samples-routing) [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](/azure/expressroute/expressroute-config-samples-nat) .
  
## <a name="selective-routing-with-expressroute"></a>Selektives Routing mit ExpressRoute

Selektives Routing mit ExpressRoute kann aus einer Vielzahl von Gründen erforderlich sein, z. B. testen und ExpressRoute für eine Teilmenge von Benutzern durchführen. Es gibt verschiedene Tools, die Kunden zum selektiven Routen von Office 365-Netzwerkdatenverkehr über ExpressRoute verwenden können:
  
1. **Routenfilterung/-trennung** – ermöglicht die BGP-Routen zu Office 365 über ExpressRoute zu einer Teilmenge Ihrer Subnetze oder Router. Dies wird selektiv nach Kundennetzwerksegment oder physischem Bürostandort geroutet. Dies ist üblich für das staffelende Rollout von ExpressRoute für Office 365 und wird auf Ihren BGP-Geräten konfiguriert.

2. **PAC-Dateien/URLs** – Leitet den von Office 365 bestimmten Netzwerkdatenverkehr für bestimmte FQDNs an, um die Route auf einem bestimmten Pfad zu verwenden. Dies leitet selektiv nach Clientcomputern, wie durch die [PAC-Dateibereitstellung identifiziert.](./managing-office-365-endpoints.md)

3. **Routenfilterung**  -  [Routenfilter](/azure/expressroute/how-to-routefilter-portal) sind eine Möglichkeit, eine Teilmenge der unterstützten Dienste über Microsoft-Peering zu nutzen.

4. **BGP-Communitys** – Mit der Filterung basierend auf [BGP-Communitytags](./bgp-communities-in-expressroute.md) kann ein Kunde bestimmen, welche Office 365-Anwendungen ExpressRoute durchlaufen und welche das Internet durchlaufen.

Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/erorouting]()
  
## <a name="related-topics"></a>Verwandte Themen

[Bewerten der Office 365-Netzwerkkonnektivität](assessing-network-connectivity.md)
  
[Azure ExpressRoute für Office 365](azure-expressroute.md)
  
[Verwalten von ExpressRoute für Office 365-Verbindungen](managing-expressroute-for-connectivity.md)
  
[Netzwerkplanung mit ExpressRoute für Office 365](network-planning-with-expressroute.md)
  
[Implementierung von ExpressRoute für Office 365](implementing-expressroute.md)
  
[Medienqualität und Netzwerkverbindungsleistung in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimieren Ihres Netzwerks für Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute und QoS in Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Anruffluss mit ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Verwenden von BGP-Communitys in ExpressRoute für Office 365-Szenarien](bgp-communities-in-expressroute.md)
  
[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](performance-tuning-using-baselines-and-history.md)
  
[Plan zur Problembehandlung für Office 365](performance-troubleshooting-plan.md)
  
[URLs und IP-Adressbereiche für Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365-Netzwerk- und Leistungsoptimierung](network-planning-and-performance.md)