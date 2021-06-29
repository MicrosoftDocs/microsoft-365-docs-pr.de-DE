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
description: In diesem Artikel erfahren Sie mehr über die Routinganforderungen, Schaltungen und Routingdomänen von Azure ExpressRoute für die Verwendung mit Office 365.
ms.openlocfilehash: b27e3cfe41af8cf5e444f1221f1cee2e3bbf5826
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194793"
---
# <a name="routing-with-expressroute-for-office-365"></a>Routing mit ExpressRoute für Office 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Um den Routingdatenverkehr an Office 365 mitHilfe von Azure ExpressRoute richtig zu verstehen, müssen Sie die grundlegenden [ExpressRoute-Routinganforderungen](/azure/expressroute/expressroute-routing) sowie die [ExpressRoute-Leitungen und Routingdomänen](/azure/expressroute/expressroute-circuit-peerings)genau verstehen. Diese enthalten die Grundlagen für die Verwendung von ExpressRoute, auf die sich Office 365 Kunden verlassen werden.
  
Einige der wichtigsten Elemente in den obigen Artikeln, die Sie verstehen müssen, sind:
  
- ExpressRoute-Leitungen werden nicht einer bestimmten physischen Infrastruktur zugeordnet, sondern sind eine logische Verbindung, die von Microsoft und einem Peeringanbieter in Ihrem Auftrag an einem einzigen Peering-Standort hergestellt wird.

- Es gibt eine 1:1-Zuordnung zwischen einer ExpressRoute-Verbindung und einem Kundenschlüssel.

- Jede Schaltung kann zwei unabhängige Peeringbeziehungen (Azure Private Peering und Microsoft Peering) unterstützen. Office 365 erfordert Microsoft-Peering.

- Jeder Schaltkreis verfügt über eine feste Bandbreite, die für alle Peeringbeziehungen gemeinsam genutzt wird.

- Alle öffentlichen IPv4-Adressen und öffentlichen AS-Nummern, die für die ExpressRoute-Verbindung verwendet werden, müssen als Im Besitz Von Ihnen oder exklusiv vom Besitzer des Adressbereichs zugewiesen werden.

- Die virtuellen ExpressRoute-Schaltungen sind global redundant und folgen den standardmäßigen BGP-Routingmethoden. Aus diesem Grund empfehlen wir zwei physische Leitungen pro Ausgang zu Ihrem Anbieter in einer aktiven/aktiven Konfiguration.

Weitere Informationen zu unterstützten Diensten, Kosten und Konfigurationsdetails finden Sie auf der [Faq-Seite.](/azure/expressroute/expressroute-faqs) Informationen zur Liste der Konnektivitätsanbieter, die Microsoft-Peering-Unterstützung anbieten, finden Sie im [Artikel "ExpressRoute-Standorte".](/azure/expressroute/expressroute-locations) Wir haben auch eine 10-teilige [Azure ExpressRoute für Office 365 Schulungsreihe](https://channel9.msdn.com/series/aer) auf Channel 9 aufgezeichnet, um die Konzepte ausführlicher zu erläutern.
  
## <a name="ensuring-route-symmetry"></a>Sicherstellen der Routen symmetrie

Auf die Office 365 Front-End-Server kann sowohl über das Internet als auch über ExpressRoute zugegriffen werden. Diese Server ziehen es vor, über ExpressRoute-Leitungen zurück zu lokalen Verbindungen zu geleitet werden, wenn beide verfügbar sind. Aus diesem Grund besteht die Möglichkeit einer Routenaverteilung, wenn der Datenverkehr aus Ihrem Netzwerk lieber über Ihre Internetleitungen geleitet wird. Asymmetrische Routen stellen ein Problem dar, da Geräte, die eine zustandsbehaftete Paketüberprüfung durchführen, Datenverkehr blockieren können, der einem anderen Pfad folgt als die gefolgten ausgehenden Pakete.
  
Unabhängig davon, ob Sie eine Verbindung mit Office 365 über das Internet oder ExpressRoute initiieren, muss die Quelle eine öffentlich routingfähige Adresse sein. Da viele Kunden direkt mit Microsoft peeren, ist es nicht machbar, private Adressen zu haben, bei denen Duplizierung zwischen Kunden möglich ist.
  
Im Folgenden finden Sie Szenarien, in denen die Kommunikation von Office 365 mit Ihrem lokalen Netzwerk initiiert wird. Um das Netzwerkdesign zu vereinfachen, empfehlen wir, diese über den Internetpfad zu routing.
  
- SMTP-Dienste, z. B. E-Mails von einem Exchange Online Mandanten an einen lokalen Host oder SharePoint Online-E-Mail, die von SharePoint Online an einen lokalen Host gesendet werden. Das SMTP-Protokoll wird im Microsoft-Netzwerk umfassender verwendet, als die Routenpräfixe, die über ExpressRoute-Leitungen freigegeben werden, und Werbung für lokale SMTP-Server über ExpressRoute führt zu Fehlern bei diesen anderen Diensten.

- ADFS während der Kennwortüberprüfung für die Anmeldung.

- [Exchange Server Hybridbereitstellungen.](/exchange/exchange-hybrid)

- [SharePoint Hybridsuche](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online)im Verbund.

- [SharePoint Hybrid-BCS.](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution)

- [Skype for Business Hybrid-](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) und/oder [Skype for Business-Partnerverbund.](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features)

- [Skype for Business Cloud Connector](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Damit Microsoft für diese bidirektionalen Datenverkehrsflüsse zurück zu Ihrem Netzwerk geleitet werden kann, müssen die BGP-Routen zu Ihren lokalen Geräten für Microsoft freigegeben werden. Wenn Sie Routenpräfixe über ExpressRoute an Microsoft ankündigen, sollten Sie die folgenden bewährten Methoden befolgen:

1) Kündigen Sie nicht dasselbe öffentliche IP-Adressroutenpräfix für das öffentliche Internet und über ExpressRoute an. Es wird empfohlen, dass die Ip-BGP-Routenpräfix-Ankündigungen an Microsoft über ExpressRoute aus einem Bereich stammen, der überhaupt nicht im Internet angekündigt wird. Wenn dies aufgrund des verfügbaren IP-Adressraums nicht möglich ist, müssen Sie sicherstellen, dass Sie einen spezifischeren Bereich über ExpressRoute als alle Internetleitungen ankündigen.

2) Verwenden Sie separate NAT-IP-Pools pro ExpressRoute-Leitung und getrennt von denen Ihrer Internet-Leitungen.

3) Beachten Sie, dass jede an Microsoft angekündigte Route Netzwerkdatenverkehr von jedem Server im Microsoft-Netzwerk anzieht, nicht nur von den Servern, für die Routen über ExpressRoute an Ihr Netzwerk angekündigt werden. Nur Ankündigen von Routen zu Servern, auf denen Routingszenarien von Ihrem Team definiert und verstanden werden. Ankündigung separater IP-Adressroute-Präfixe an jeder von mehreren ExpressRoute-Leitungen aus Ihrem Netzwerk.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Entscheiden, welche Anwendungen und Features über ExpressRoute geleitet werden

Wenn Sie eine Peeringbeziehung mithilfe der Microsoft-Peeringroutingdomäne konfigurieren und für den entsprechenden Zugriff genehmigt sind, können Sie alle PaaS- und SaaS-Dienste anzeigen, die über ExpressRoute verfügbar sind. Die Office 365 für ExpressRoute entwickelten Dienste können mit [BGP-Communitys](./bgp-communities-in-expressroute.md) oder [Routenfiltern](/azure/expressroute/how-to-routefilter-portal)verwaltet werden.
  
Jede der Office 365 Features, die über Microsoft-Peering verfügbar sind, sind im [Artikel Office 365 Endpunkte](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) nach Anwendungstyp und FQDN aufgeführt. Der Grund für die Verwendung des FQDN in den Tabellen besteht darin, Kunden die Verwaltung des Datenverkehrs mithilfe von PAC-Dateien oder anderen Proxykonfigurationen zu ermöglichen. Weitere Informationen finden Sie in unserem Leitfaden zum [Verwalten Office 365 Endpunkte,](./managing-office-365-endpoints.md) z. B. PAC-Dateien.
  
In einigen Situationen haben wir eine Platzhalterdomäne verwendet, in der mindestens ein Sub-FQDN anders als die Platzhalterdomäne auf höherer Ebene angekündigt wird. Dies geschieht in der Regel, wenn der Platzhalter eine lange Liste von Servern darstellt, die alle für ExpressRoute und das Internet angekündigt werden, während eine kleine Teilmenge der Ziele nur im Internet angekündigt wird, oder umgekehrt. In den folgenden Tabellen erfahren Sie, wo sich die Unterschiede befinden.
  
In dieser Tabelle werden die Platzhalter-FQDNs angezeigt, die sowohl im Internet als auch in Azure ExpressRoute angekündigt werden, zusammen mit den Sub-FQDNs, die nur im Internet angekündigt werden.

|**Platzhalterdomäne für ExpressRoute- und Internet-Leitungen angekündigt**|**Sub-FQDN wird nur für Internetleitungen angekündigt**|
|:-----|:-----|
|\*.microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*.officeapps.live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

In der Regel sind PAC-Dateien dafür vorgesehen, Netzwerkanforderungen an von ExpressRoute angekündigte Endpunkte direkt an die Leitung und alle anderen Netzwerkanforderungen an Ihren Proxy zu senden. Wenn Sie eine PAC-Datei wie folgt konfigurieren, verfassen Sie Ihre PAC-Datei in der folgenden Reihenfolge:
  
1. Schließen Sie die sub-FQDNs aus Spalte 2 in der obigen Tabelle am oberen Rand der PAC-Datei ein, und senden Sie den Datenverkehr in Richtung Ihres Proxys. Wir haben eine BEISPIEL-PAC-Datei erstellt, die Sie in unserem Artikel zum [Verwalten von Office 365 Endpunkten](./managing-office-365-endpoints.md)verwenden können.

2. Schließen Sie alle FQDNs ein, die für ExpressRoute angekündigt sind, in [diesem Artikel](./urls-and-ip-address-ranges.md) unterhalb des ersten Abschnitts, und senden Sie den Datenverkehr direkt an Ihre ExpressRoute-Verbindung.

3. Schließen Sie alle anderen Netzwerkendpunkte oder -regeln unter diesen beiden Einträgen ein, und senden Sie den Datenverkehr an Ihren Proxy.

In dieser Tabelle werden die Platzhalterdomänen angezeigt, die nur zusammen mit den sub-FQDNs, die für Azure ExpressRoute und Internet-Leitungen angekündigt werden, für Internetleitungen angekündigt werden. Für Ihre PAC-Datei oben werden die FQDNs in Spalte 2 in der folgenden Tabelle in dem Link, auf den verwiesen wird, als für ExpressRoute angekündigt aufgeführt, was bedeutet, dass sie in der zweiten Gruppe von Einträgen in der Datei enthalten sind.

|**Platzhalterdomäne nur für Internetschaltungen angekündigt**|**Sub-FQDN für ExpressRoute und Internet-Leitungen angekündigt**|
|:-----|:-----|
|\*.office.com  <br/> |\*.outlook.office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*.office.net  <br/> |agent.office.net  <br/> |
|\*.office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*.outlook.com  <br/> |\*.protection.outlook.com  <br/> \*.mail.protection.outlook.com  <br/> autodiscover- \<tenant\> .outlook.com  <br/> |
|\*.windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Weiterleiten Office 365 Datenverkehrs über das Internet und ExpressRoute

Um zur Office 365 Anwendung Ihrer Wahl zu navigieren, müssen Sie eine Reihe von Schlüsselfaktoren ermitteln.
  
1. Wie viel Bandbreite die Anwendung benötigt. Das Sampling der vorhandenen Nutzung ist die einzige zuverlässige Methode, um dies in Ihrer Organisation zu bestimmen.

2. Von welchem/n Ausgangspunkt(en) der Netzwerkdatenverkehr Ihr Netzwerk verlassen soll. Sie sollten planen, die Netzwerklatenz für die Verbindung mit Office 365 zu minimieren, da sich dies auf die Leistung auswirkt. Da Skype for Business Echtzeit-VoIP und -Video verwendet, ist es besonders anfällig für eine schlechte Netzwerklatenz.

3. Wenn Sie möchten, dass alle oder eine Teilmenge Ihrer Netzwerkstandorte ExpressRoute verwenden.

4. Von welchen Standorten Ihr ausgewählter Netzwerkanbieter ExpressRoute anbietet.

Nachdem Sie die Antworten auf diese Fragen ermittelt haben, können Sie einen ExpressRoute-Netzschalter bereitstellen, der die Bandbreiten- und Standortanforderungen erfüllt. Weitere Unterstützung bei der Netzwerkplanung finden Sie im [Office 365 Leitfaden zur Netzwerkoptimierung](./network-planning-and-performance.md) und in der [Fallstudie, wie Microsoft die Planung der Netzwerkleistung behandelt.](https://aka.ms/tunemsit)
  
### <a name="example-1-single-geographic-location"></a>Beispiel 1: Einzelner geografischer Standort
  
Dieses Beispiel ist ein Szenario für ein fiktives Unternehmen namens Trey Research mit einem einzigen geografischen Standort.
  
Mitarbeiter von Trey Research dürfen sich nur mit den Diensten und Websites im Internet verbinden, die die Sicherheitsabteilung explizit für das Paar ausgehender Proxys zulässt, die sich zwischen dem Unternehmensnetzwerk und ihrem ISP befinden.
  
Trey Research plant die Verwendung von Azure ExpressRoute für Office 365 und erkennt, dass datenverkehr wie z. B. Datenverkehr, der für Netzwerke zur Inhaltsübermittlung bestimmt ist, nicht über expressRoute für Office 365 Verbindung weitergeleitet werden kann. Da der gesamte Datenverkehr bereits standardmäßig an die Proxygeräte geleitet wird, funktionieren diese Anforderungen weiterhin wie zuvor. Nachdem Trey Research festgestellt hat, dass sie die Azure ExpressRoute-Routinganforderungen erfüllen können, erstellen sie eine Leitung, konfigurieren routing und verknüpfen die neue ExpressRoute-Verbindung mit einem virtuellen Netzwerk. Sobald die grundlegende Azure ExpressRoute-Konfiguration eingerichtet ist, verwendet Trey Research die [#2 PAC-Datei,](./managing-office-365-endpoints.md) die wir veröffentlichen, um Datenverkehr mit kundenspezifischen Daten über die direkte ExpressRoute für Office 365 Verbindungen weiterzuleiten.
  
Wie im folgenden Diagramm dargestellt, kann Trey Research die Anforderung erfüllen, Office 365 Datenverkehr über das Internet und eine Teilmenge des Datenverkehrs über ExpressRoute mithilfe einer Kombination aus Routing- und ausgehenden Proxykonfigurationsänderungen weiterzuleiten.
  
1. Verwenden Sie die [#2 PAC-Datei, die wir veröffentlichen,](./managing-office-365-endpoints.md) um Datenverkehr über einen separaten Internetausgangspunkt für Azure ExpressRoute für Office 365 weiterzuleiten.

2. Clients sind mit einer Standardroute zu den Proxys von Trey Research konfiguriert.

In diesem Beispielszenario verwendet Trey Research ein ausgehendes Proxygerät. Ebenso können Kunden, die Azure ExpressRoute nicht für Office 365 verwenden, diese Technik verwenden, um Datenverkehr basierend auf den Kosten für die Überprüfung des Datenverkehrs für bekannte Endpunkte mit hohem Volumen weiterzuleiten.
  
Die höchsten Volume-FQDNs für Exchange Online, SharePoint Online und Skype for Business Online sind die folgenden:
  
![ExpressRoute-Kunden-Edgenetzwerk](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- outlook.office365.com, outlook.office.com

- \<tenant-name\>.sharepoint.com, \<tenant-name\> -my.sharepoint.com, \<tenant-name\> - \<app\> .sharepoint.com

- \*. Lync.com zusammen mit den IP-Bereichen für Nicht-TCP-Datenverkehr

- \*broadcast.officeapps.live.com, \* excel.officeapps.live.com, \* onenote.officeapps.live.com, \* powerpoint.officeapps.live.com, \* view.officeapps.live.com, \* visio.officeapps.live.com, \* word-edit.officeapps.live.com, \* word-view.officeapps.live.com, office.live.com

Erfahren Sie mehr über [das Bereitstellen und Verwalten von Proxyeinstellungen in Windows 8](/archive/blogs/deploymentguys/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy) und [sicherstellen, dass Office 365 nicht von Ihrem Proxy gedrosselt wird.](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx)
  
Bei einer einzelnen ExpressRoute-Leitung besteht keine hohe Verfügbarkeit für Trey Research. Für den Fall, dass treys redundantes Edgegerätpaar, das die ExpressRoute-Konnektivität bedient, fehlschlägt, gibt es keinen zusätzlichen ExpressRoute-Netzschalter für ein Failover. Dadurch befindet sich Trey Research in einer notierten Situation, da ein Failover auf das Internet eine manuelle Neukonfiguration und in einigen Fällen neue IP-Adressen erfordert. Wenn Trey hohe Verfügbarkeit hinzufügen möchte, besteht die einfachste Lösung darin, zusätzliche ExpressRoute-Leitungen für jeden Standort hinzuzufügen und die Leitungen aktiv/aktiv zu konfigurieren.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>Routing ExpressRoute für Office 365 mit mehreren Standorten

Das letzte Szenario, das Routing Office 365 Datenverkehr über ExpressRoute ist die Grundlage für eine noch komplexere Routingarchitektur. Unabhängig von der Anzahl der Standorte, der Anzahl der Kontinente, in denen diese Standorte vorhanden sind, der Anzahl der ExpressRoute-Leitungen usw. ist eine Weiterleitung von Datenverkehr an das Internet und etwas Datenverkehr über ExpressRoute erforderlich.
  
Zu den zusätzlichen Fragen, die für Kunden mit mehreren Standorten in mehreren Regionen beantwortet werden müssen, gehören:
  
1. Benötigen Sie an jedem Standort eine ExpressRoute-Leitung? Wenn Sie Skype for Business Online verwenden oder die Latenzempfindlichkeit für SharePoint Online oder Exchange Online bedenken, wird an jedem Standort ein redundantes Paar von aktiven/aktiven ExpressRoute-Schaltungen empfohlen. Weitere Informationen finden Sie im Leitfaden zur Skype for Business Medienqualität und Netzwerkkonnektivität.

2. Wenn eine ExpressRoute-Verbindung in einer bestimmten Region nicht verfügbar ist, wie sollte Office 365 bestimmter Datenverkehr weitergeleitet werden?

3. Was ist die bevorzugte Methode zum Konsolidieren von Datenverkehr bei Netzwerken mit vielen kleinen Standorten?

Jede dieser Optionen stellt eine einzigartige Herausforderung dar, bei der Sie Ihr eigenes Netzwerk und die von Microsoft verfügbaren Optionen auswerten müssen.

|**Überlegungen**|**Zu bewertende Netzwerkkomponenten**|
|:-----|:-----|
|Schaltungen an mehreren Positionen  <br/> |Es wird empfohlen, mindestens zwei Schaltungen aktiv/aktiv zu konfigurieren.  <br/> Kosten-, Latenz- und Bandbreitenanforderungen müssen verglichen werden.  <br/> Verwenden Sie BGP-Routenkosten, PAC-Dateien und NAT, um das Routing mit mehreren Schaltungen zu verwalten.  <br/> |
|Routing von Standorten ohne ExpressRoute-Leitung  <br/> |Es wird empfohlen, den Ausgang und die DNS-Auflösung so nahe an die Person zu senden, die die Anforderung für Office 365 initiiert.  <br/> Die DNS-Weiterleitung kann verwendet werden, damit Remote-Büros den entsprechenden Endpunkt ermitteln können.  <br/> Clients im Remotebüro müssen über eine Route verfügen, die Zugriff auf die ExpressRoute-Verbindung bietet.  <br/> |
|Kleine Bürokonsolidierung  <br/> |Die verfügbare Bandbreite und die Datennutzung sollten sorgfältig verglichen werden.  <br/> |

> [!NOTE]
> Microsoft bevorzugt ExpressRoute über das Internet, wenn die Route unabhängig vom physischen Standort verfügbar ist.
  
Jede dieser Überlegungen muss für jedes einzelne Netzwerk berücksichtigt werden. Unten sehen Sie ein Beispiel.
  
### <a name="example-2-multi-geographic-locations"></a>Beispiel 2: Mehrere geografische Standorte
  
Dieses Beispiel ist ein Szenario für ein fiktives Unternehmen namens "Humongous Insurance", das über mehrere geografische Standorte verfügt.
  
Die kunterbunte Versicherungsbranche ist geografisch mit Büros auf der ganzen Welt verteilt. Sie möchten Azure ExpressRoute für Office 365 implementieren, um den größten Teil des Office 365 Datenverkehrs über direkte Netzwerkverbindungen zu behalten. Die Kellnige-Versicherungsbranche verfügt auch über Büros auf zwei zusätzlichen Kontinenten. Die Mitarbeiter im Remotebüro, in dem ExpressRoute nicht machbar ist, müssen zu einer oder beiden der primären Einrichtungen zurückkehren, um eine ExpressRoute-Verbindung zu verwenden.
  
Das Leitprinzip besteht darin, Office 365 bestimmten Datenverkehr so schnell wie möglich an ein Microsoft-Rechenzentrum zu übertragen. In diesem Beispiel muss Humongous Insurance entscheiden, ob ihre Remote-Büros über das Internet geleitet werden sollen, um über eine beliebige Verbindung so schnell wie möglich zu einem Microsoft-Rechenzentrum zu gelangen, oder ob ihre Remote-Büros über ein internes Netzwerk geleitet werden sollen, um so schnell wie möglich über eine ExpressRoute-Verbindung zu einem Microsoft-Rechenzentrum zu gelangen.
  
Die Rechenzentren, Netzwerke und Anwendungsarchitektur von Microsoft sind so konzipiert, dass sie global unterschiedliche Kommunikationen nutzen und sie so effizient wie möglich warten. Dies ist eines der größten Netzwerke der Welt. Anforderungen für Office 365, die länger als erforderlich in Kundennetzwerken verbleiben, können diese Architektur nicht nutzen.
  
In der Situation von Humongous Insurance sollten sie je nach den Anwendungen fortfahren, die sie über ExpressRoute verwenden möchten. Wenn es sich beispielsweise um einen Skype for Business Onlinekunden handelt oder die ExpressRoute-Konnektivität beim Herstellen einer Verbindung mit externen Skype for Business Onlinebesprechungen verwendet werden soll, empfiehlt sich im Handbuch für Skype for Business Onlinemedienqualität und Netzwerkkonnektivität die Bereitstellung eines zusätzlichen ExpressRoute-Netzschalters für den dritten Standort. Dies kann aus Netzwerkperspektive teurer sein. Das Weiterleiten von Anforderungen von einem Kontinent an einen anderen vor der Bereitstellung an ein Microsoft-Rechenzentrum kann jedoch während Skype for Business Onlinebesprechungen und -kommunikationen zu einer schlechten oder unbrauchbaren Erfahrung führen.
  
Wenn Humongous Insurance Skype for Business Online in keiner Weise verwendet oder nicht verwenden möchte, kann es möglich sein, Office 365 bestimmten Netzwerkdatenverkehr zu einem Kontinent mit einer ExpressRoute-Verbindung zurückzuleiten. Dies kann jedoch zu unnötiger Latenz oder TCP-Überlastung führen. In beiden Fällen wird empfohlen, internetdeterminierten Datenverkehr an das Internet am lokalen Standort weiterzuleiten, um die Vorteile der Netzwerke für die Inhaltsübermittlung zu nutzen, auf denen Office 365 basiert.
  
![ExpressRoute multi-geography](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Wenn Humongous Insurance ihre Multigeografiestrategie plant, gibt es eine Reihe von Aspekten, die in Bezug auf die Größe der Schaltung, die Anzahl der Schaltungen, das Failover usw. zu berücksichtigen sind.
  
Wenn ExpressRoute an einem einzigen Standort mit mehreren Regionen, die versuchen, die Leitung zu verwenden, verwendet wird, möchte Humongous Insurance sicherstellen, dass Verbindungen zu Office 365 aus dem Remotebüro an das Office 365 Rechenzentrum am nächstgelegenen Hauptsitz gesendet und vom Hauptsitzstandort empfangen werden. Zu diesem Zweck implementiert Humongous Insurance DNS-Weiterleitung, um die Anzahl der Roundtrips und DNS-Lookups zu reduzieren, die erforderlich sind, um die entsprechende Verbindung mit der Office 365 Umgebung herzustellen, die dem Internetausgangspunkt der Zentrale am nächsten ist. Dies verhindert, dass der Client einen lokalen Front-End-Server auflöst, und stellt sicher, dass sich der Front-End Server, mit dem sich die Person verbindet, in der Nähe des Hauptsitzes befindet, in dem Humongous Insurance mit Microsoft peert. Sie können auch lernen, [eine bedingte Weiterleitung für einen Domänennamen zuzuweisen.](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc794735(v=ws.10))
  
In diesem Szenario würde der Datenverkehr aus dem Remotebüro die Office 365 Front-End-Infrastruktur in Nordamerika auflösen und Office 365 verwenden, um eine Verbindung mit den Back-End-Servern gemäß der Architektur der Office 365 Anwendung herzustellen. Beispielsweise würde Exchange Online die Verbindung in Nordamerika beenden, und diese Front-End-Server würden eine Verbindung mit dem Back-End-Postfachserver herstellen, unabhängig davon, wo sich der Mandant befindet. Alle Dienste verfügen über einen weit verteilten Front-Door-Dienst, der aus Unicast- und Anycast-Zielen besteht.
  
Wenn Humongous über Große Büros in mehreren Kontinenten verfügt, werden mindestens zwei aktive/aktive Schaltungen pro Region empfohlen, um die Latenz für sensible Anwendungen wie Skype for Business Online zu verringern. Wenn sich alle Büros auf einem einzelnen Kontinent befinden oder keine Zusammenarbeit in Echtzeit nutzen, ist ein konsolidierter oder verteilter Ausgangspunkt eine kundenspezifische Entscheidung. Wenn mehrere Schaltungen verfügbar sind, stellt das BGP-Routing ein Failover sicher, wenn ein einzelner Stromkreis nicht mehr verfügbar ist.
  
Erfahren Sie mehr über [Beispielroutingkonfigurationen](/azure/expressroute/expressroute-config-samples-routing) und [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](/azure/expressroute/expressroute-config-samples-nat) .
  
## <a name="selective-routing-with-expressroute"></a>Selektives Routing mit ExpressRoute

Selektives Routing mit ExpressRoute kann aus einer Vielzahl von Gründen erforderlich sein, z. B. tests, Rollout von ExpressRoute für eine Teilmenge von Benutzern. Es gibt verschiedene Tools, mit denen Kunden Office 365 Netzwerkdatenverkehr selektiv über ExpressRoute weiterleiten können:
  
1. **Routenfilterung/-trennung** – Ermöglicht es den BGP-Routen, über ExpressRoute zu einer Teilmenge Ihrer Subnetze oder Router zu Office 365. Dies wird selektiv nach Kundennetzwerksegment oder physischem Bürostandort geleitet. Dies ist üblich für das staffelliche Rollout von ExpressRoute für Office 365 und wird auf Ihren BGP-Geräten konfiguriert.

2. **PAC-Dateien/URLs** – Leitet Office 365 bestimmten Netzwerkdatenverkehr für bestimmte FQDNs an, die auf einen bestimmten Pfad weitergeleitet werden. Dies wird selektiv nach Clientcomputern weiter geroutet, wie durch die [PAC-Dateibereitstellung](./managing-office-365-endpoints.md)identifiziert.

3. **Routenfilterung**  -  [Routenfilter](/azure/expressroute/how-to-routefilter-portal) sind eine Möglichkeit, eine Teilmenge der unterstützten Dienste über Microsoft-Peering zu nutzen.

4. **BGP-Communitys** – Das Filtern basierend auf [BGP-Communitytags](./bgp-communities-in-expressroute.md) ermöglicht es einem Kunden zu bestimmen, welche Office 365 Anwendungen ExpressRoute durchlaufen und welche das Internet durchqueren.

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
  
[Verwenden von BGP-Communitys in ExpressRoute für Office 365 Szenarien](bgp-communities-in-expressroute.md)
  
[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](performance-tuning-using-baselines-and-history.md)
  
[Plan zur Problembehandlung für Office 365](performance-troubleshooting-plan.md)
  
[Office 365-URLs und IP-Adressbereiche.](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365-Netzwerk- und Leistungsoptimierung](network-planning-and-performance.md)
