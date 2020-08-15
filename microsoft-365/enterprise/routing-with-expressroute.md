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
description: In diesem Artikel erfahren Sie mehr über Azure Express Route-Routing Anforderungen, Schaltkreise und Routingdomänen für die Verwendung mit Office 365.
ms.openlocfilehash: 7201c23777cbf4ca5285736db5a947955a443c51
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690346"
---
# <a name="routing-with-expressroute-for-office-365"></a>Routing mit ExpressRoute für Office 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Um den Routing Datenverkehr zu Office 365 mithilfe von Azure Express Route richtig zu verstehen, benötigen Sie einen festen Überblick über die wichtigsten [Express Route-Routing Anforderungen](https://azure.microsoft.com/documentation/articles/expressroute-routing/) und die [Express Route-Schaltkreise und Routingdomänen](https://azure.microsoft.com/documentation/articles/expressroute-circuit-peerings/). Diese legen die Grundlagen für die Verwendung von Express Route fest, auf die sich Office 365 Kunden verlassen.
  
Einige der wichtigsten Elemente in den oben genannten Artikeln, die Sie verstehen müssen, sind:
  
- Express Route-Schaltkreise werden nicht einer bestimmten physischen Infrastruktur zugeordnet, sondern stellen eine logische Verbindung dar, die an einem einzelnen Peering-Standort von Microsoft und einem Peering-Anbieter in Ihrem Namen erfolgt ist.

- Es gibt eine 1:1-Zuordnung zwischen einer Express Route-Schaltung und einem Kunden-s-Key.

- Jede Schaltung kann 2 unabhängige Peering-Beziehungen unterstützen (Azure private Peering und Microsoft Peering); Office 365 erfordert Microsoft Peering.

- Jeder Schaltkreis hat eine feste Bandbreite, die für alle Peering-Beziehungen freigegeben ist.

- Alle öffentlichen IPv4-Adressen und öffentlichen AS-Nummern, die für die Express Route-Schaltung verwendet werden, müssen als von Ihnen besessen oder ausschließlich Ihnen vom Besitzer des Adressbereichs zugewiesen werden.

- Die virtuellen Express Route-Schaltkreise sind Global redundant und werden standardmäßigen BGP-Routingverfahren befolgt. Aus diesem Grund empfehlen wir in einer aktiv/aktiv-Konfiguration zwei physische Schaltkreise pro Ausstieg an Ihren Anbieter.

Auf der [FAQ-Seite](https://azure.microsoft.com/documentation/articles/expressroute-faqs/) finden Sie weitere Informationen zu unterstützten Diensten, Kosten und Konfigurationsdetails. Im [Artikel Express Route Locations](https://azure.microsoft.com/documentation/articles/expressroute-locations/) finden Sie Informationen zur Liste der Verbindungsanbieter, die Microsoft Peering-Unterstützung anbieten. Wir haben auch eine 10-teilige [Azure-Express Route für Office 365-Schulungs](https://channel9.msdn.com/series/aer) Reihe auf Kanal 9 aufgezeichnet, um die Konzepte gründlicher zu erläutern.
  
## <a name="ensuring-route-symmetry"></a>Sicherstellen der Routen Symmetrie

Auf die Office 365-Front-End-Server kann sowohl im Internet als auch in Express Route zugegriffen werden. Diese Server werden lieber zurück zu lokalen über Express Route-Schaltkreisen weitergeleitet, wenn beide verfügbar sind. Aus diesem Grund besteht die Möglichkeit der Routen Asymmetrie, wenn der Datenverkehr von Ihrem Netzwerk bevorzugt über Ihre Internet-Schaltkreise geroutet wird. Asymmetrische Routen stellen ein Problem dar, da Geräte, die eine statusbehaftete Paketüberprüfung durchführen, den Rückgabe Datenverkehr blockieren können, der einem anderen Pfad folgt als die eingehenden Pakete.
  
Unabhängig davon, ob Sie eine Verbindung mit Office 365 über das Internet oder Express Route initiieren, muss es sich bei der Quelle um eine öffentlich routingfähige Adresse handeln. Da viele Kunden direkt mit Microsoft in Kontakt treten, sind private Adressen, bei denen eine Duplizierung zwischen den Kunden möglich ist, nicht möglich.
  
Im folgenden werden Szenarien beschrieben, in denen die Kommunikation zwischen Office 365 und Ihrem lokalen Netzwerk initiiert wird. Zur Vereinfachung Ihres netzwerkdesigns empfehlen wir die Weiterleitung über den Internet Pfad.
  
- SMTP-Dienste wie e-Mail von einem Exchange Online-Mandanten an einen lokalen Host oder SharePoint Online von SharePoint Online an einen lokalen Host gesendete e-Mail. Das SMTP-Protokoll wird im Microsoft-Netzwerk breiter verwendet, als die für Express Route-Schaltungen freigegebenen Routen Präfixe und lokale SMTP-Server Werbung über Express Route zu Fehlern bei diesen anderen Diensten führen werden.

- ADFS während der Kennwortüberprüfung für die Anmeldung.

- [Exchange Server Hybrid Bereitstellungen](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx).

- [SharePoint-Verbund Hybrid Suche](https://technet.microsoft.com/library/dn197174.aspx).

- [SharePoint-Hybrid-BCS](https://technet.microsoft.com/library/dn197239.aspx ).

- [Skype for Business Hybrid](https://technet.microsoft.com/library/jj205403.aspx) -und/oder [Skype for Business-Verbund](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx).

- [Skype for Business Cloud Connector](https://technet.microsoft.com/library/mt605227.aspx ).

Damit Microsoft für diese bidirektionalen Datenströme wieder zu Ihrem Netzwerk weitergeleitet werden kann, müssen die BGP-Routen zu Ihren lokalen Geräten für Microsoft freigegeben werden. Wenn Sie an Microsoft über Express Route Routen Präfixe ankündigen, sollten Sie die folgenden bewährten Methoden anwenden:

1) Werben Sie nicht für das gleiche öffentliche IP-Adress Routenpräfix im öffentlichen Internet und über Express Route. Es wird dringend empfohlen, dass die IP-BGP-Routenpräfix-Ankündigungen an Microsoft über Express Route aus einem Bereich stammt, der überhaupt nicht im Internet beworben wird. Wenn dies aufgrund des verfügbaren IP-Adressraums nicht möglich ist, müssen Sie unbedingt sicherstellen, dass Sie einen spezifischeren Bereich über Express Route als alle Internet-Schaltkreise werben.

2) Verwenden Sie separate NAT-IP-Pools pro Express Route-Schaltung, und trennen Sie Sie von den Netz Stromkreisen.

3) Beachten Sie, dass jede Route, die bei Microsoft beworben wird, Netzwerkdatenverkehr von einem beliebigen Server im Microsoft-Netzwerk anzieht, und nicht nur diejenigen, für die Routen für Ihr Netzwerk über Express Route beworben werden. Werben Sie nur Routen zu Servern, auf denen Routingszenarien definiert sind und von Ihrem Team gut verstanden werden. Werben Sie getrennte IP-Adress Routen Präfixe an jedem der mehreren Express Route-Schaltkreise von Ihrem Netzwerk aus.
  
## <a name="deciding-which-applications-and-features-route-over-expressroute"></a>Bestimmen, welche Anwendungen und Features über Express Route weitergeleitet werden

Wenn Sie eine Peering-Beziehung mithilfe der Microsoft Peering-Routingdomäne konfigurieren und für den entsprechenden Zugriff genehmigt wurden, können Sie alle PaaS-und Saas-Dienste anzeigen, die über Express Route verfügbar sind. Die Office 365 für Express Route entwickelten Dienste können mit BGP- [Communities](https://aka.ms/bgpexpressroute365) oder [Routenfiltern](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal)verwaltet werden.
  
Andere Anwendungen wie Office 365 Video ist eine Office 365 Anwendung; Office 365 Video besteht jedoch aus drei verschiedenen Komponenten, dem Portal, dem Streamingdienst und dem Inhalts Zustellungs Netzwerk. Das Portal lebt in SharePoint Online, der Streamingdienst lebt in Azure Media Services, und das Inhalts Zustellungs Netzwerk lebt im Azure CDN. In der folgenden Tabelle sind diese Komponenten aufgeführt.

|**Komponente**|**Zugrunde liegende Anwendung**|**Enthalten in SharePoint Online BGP Community?**|**Verwendung**|
|:-----|:-----|:-----|:-----|
|Office 365 Video Portal  <br/> |SharePoint Online  <br/> |Ja  <br/> |Konfiguration, hochladen  <br/> |
|Office 365 Video Streaming-Dienst  <br/> |Azure Media Services  <br/> |Nein  <br/> |Streamingdienst, verwendet für den Fall, dass das Video aus dem CDN nicht verfügbar ist  <br/> |
|Office 365 Video-Inhalts Übermittlungs Netzwerk  <br/> |Azure CDN  <br/> |Nein  <br/> |Primäre Quelle für Video Download/-Streaming. [Erfahren Sie mehr über Office 365 Video Netzwerke](https://support.office.com/article/Office-365-Video-networking-Frequently-Asked-Questions-FAQ-2bed67a1-4052-49ff-a4ce-b7e6530eb98e).  <br/> |

Alle Office 365 Features, die mit Microsoft Peering verfügbar sind, werden im [Artikel Office 365 Endpunkte](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) nach Anwendungstyp und FQDN aufgeführt. Der Grund für die Verwendung des FQDN in den Tabellen besteht darin, dass Kunden den Datenverkehr mithilfe von PAC-Dateien oder anderen Proxy Konfigurationen verwalten können, siehe unser Leitfaden zum [Verwalten von Office 365 Endpunkten](https://aka.ms/manageo365endpoints) , beispielsweise PAC-Dateien.
  
In einigen Situationen haben wir eine Platzhalterdomäne verwendet, in der mindestens eine untergeordnete FQDNs anders als die Platzhalterdomäne der höheren Ebene beworben wird. Dies geschieht normalerweise, wenn der Platzhalter eine lange Liste von Servern darstellt, die alle für Express Route und das Internet beworben werden, während eine kleine Untergruppe von Zielen nur im Internet beworben wird, oder umgekehrt. Lesen Sie die folgenden Tabellen, um zu verstehen, wo die Unterschiede liegen.
  
In dieser Tabelle werden die Platzhalter-FQDNs angezeigt, die sowohl für das Internet als auch für Azure Express Route neben den untergeordneten FQDNs, die nur im Internet beworben werden, beworben werden.

|**Platzhalterdomäne für Express Route und Internet Schaltungen beworben**|**Untergeordneter FQDN nur für Internet Schaltungen beworben**|
|:-----|:-----|
|\*. microsoftonline.com  <br/> |click.email.microsoftonline.com  <br/> portal.microsoftonline.com  <br/> provisioningapi.microsoftonline.com  <br/> adminwebservice.microsoftonline.com  <br/> |
|\*. officeapps.Live.com  <br/> |nexusRules.officeapps.live.com  <br/> nexus.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> odc.officeapps.live.com  <br/> cdn.odc.officeapps.live.com  <br/> ols.officeapps.live.com  <br/> ocsredir.officeapps.live.com  <br/> ocws.officeapps.live.com  <br/> ocsa.officeapps.live.com  <br/> |

In der Regel sollen PAC-Dateien Netzwerkanforderungen an Express Route-angekündigte Endpunkte direkt an den Circuit und alle anderen Netzwerkanforderungen an Ihren Proxy senden. Wenn Sie eine PAC-Datei wie die folgende konfigurieren, verfassen Sie die PAC-Datei in der folgenden Reihenfolge:
  
1. Schließen Sie die untergeordneten FQDNs aus Spalte 2 in die obige Tabelle oben in ihrer PAC-Datei ein, und senden Sie den Datenverkehr an Ihren Proxy. Wir haben eine Beispiel-PAC-Datei erstellt, die Sie in unserem Artikel zum [Verwalten von Office 365 Endpunkten](https://aka.ms/manageexpressroute365)verwenden können.

2. Schließen Sie alle in [diesem Artikel](https://aka.ms/o365endpoints) unter dem ersten Abschnitt beworbenen FQDNs mit der Bezeichnung Express Route ein, und senden Sie den Datenverkehr direkt an Ihre Express Route-Schaltung.

3. Schließen Sie alle anderen Netzwerkendpunkte oder Regeln unterhalb dieser beiden Einträge ein, und senden Sie den Datenverkehr an Ihren Proxy.

In dieser Tabelle werden die Platzhalterdomänen angezeigt, die für Internet Schaltkreise nur neben den unter FQDNs beworben werden, die für Azure Express Route und Internet Circuits beworben werden. Für Ihre PAC-Datei oben werden die FQDNs in Spalte 2 der folgenden Tabelle als für Express Route in der angegebenen Verknüpfung beworben aufgeführt, was bedeutet, dass Sie in der zweiten Gruppe von Einträgen in der Datei enthalten wären.

|**Platzhalterdomäne nur für Internet Schaltungen beworben**|**Untergeordneter FQDN für Express Route und Internet Schaltungen beworben**|
|:-----|:-----|
|\*. Office.com  <br/> |\*. Outlook.Office.com  <br/> home.office.com  <br/> outlook.office.com  <br/> portal.office.com  <br/> <div style="display: inline">www.office.com</div>  <br/> |
|\*. Office.net  <br/> |agent.office.net  <br/> |
|\*. office365.com  <br/> |outlook.office365.com  <br/> smtp.office365.com  <br/> |
|\*. Outlook.com  <br/> |\*. Protection.Outlook.com  <br/> \*. Mail.Protection.Outlook.com  <br/> AutoErmittlung- \<tenant\> . Outlook.com  <br/> |
|\*. Windows.net  <br/> |login.windows.net  <br/> |

## <a name="routing-office-365-traffic-over-the-internet-and-expressroute"></a>Weiterleiten Office 365 Datenverkehrs über das Internet und Express Route

Um zur Office 365 Anwendung Ihrer Wahl weiterzuleiten, müssen Sie eine Reihe von Schlüsselfaktoren bestimmen.
  
1. Wie viel Bandbreite die Anwendung benötigt. Das Sampling der vorhandenen Nutzung ist die einzige zuverlässige Methode, um dies in Ihrer Organisation zu ermitteln.

2. Welche Ausgangsposition (n) Sie möchten, dass der Netzwerkdatenverkehr Ihr Netzwerk verlässt. Sie sollten die Netzwerkwartezeit für die Konnektivität mit Office 365 minimieren, da sich dies auf die Leistung auswirkt. Da Skype for Business Echtzeit-sprach-und-Video verwendet, ist es besonders anfällig für eine schlechte Netzwerkwartezeit.

3. Wenn Sie möchten, dass alle oder eine Teilmenge ihrer Netzwerkstandorte Express Route nutzen.

4. Von welchen Standorten Ihr ausgewählter Netzwerkanbieter Express Route anbietet.

Nachdem Sie die Antworten auf diese Fragen ermittelt haben, können Sie einen Express Route-Schaltkreis bereitstellen, der die Bandbreiten-und Standortanforderungen erfüllt. Weitere Informationen zur Netzwerkplanung finden Sie im [Office 365 Network Tuning Guide](https://aka.ms/tune) und in der [Fallstudie zur Planung von Netzwerkleistung durch Microsoft](https://aka.ms/tunemsit).
  
### <a name="example-1-single-geographic-location"></a>Beispiel 1: einzelner geografischer Standort
  
Dieses Beispiel ist ein Szenario für ein fiktives Unternehmen namens Trey Research, das über einen einzigen geografischen Standort verfügt.
  
Mitarbeiter von Trey Research dürfen nur eine Verbindung zu den Diensten und Websites im Internet herstellen, die die Sicherheitsabteilung explizit auf dem Paar von ausgehenden Proxys zulässt, die zwischen dem Unternehmensnetzwerk und dem ISP sitzen.
  
Trey Research plant die Verwendung von Azure Express Route für Office 365 und erkennt, dass einige Datenverkehr wie etwa Datenverkehr, der für Inhalts Übermittlungs Netzwerke bestimmt ist, nicht über die Express Route für Office 365 Verbindung weitergeleitet werden kann. Da der gesamte Datenverkehr standardmäßig zu den Proxy Geräten weitergeleitet wird, funktionieren diese Anforderungen weiterhin wie bisher. Nachdem Trey Research festgestellt hat, dass Sie die Anforderungen für das Azure Express Route-Routing erfüllen können, fahren Sie mit dem Erstellen eines Circuits, Konfigurieren des Routings und Verknüpfen der neuen Express Route-Schaltung mit einem virtuellen Netzwerk fort. Sobald die grundlegende Azure Express Route-Konfiguration vorhanden ist, verwendet Trey Research die [#2 PAC-Datei, die wir veröffentlichen](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) , um Datenverkehr mit kundenspezifischen Daten über die direkte Express Route für Office 365 Verbindungen weiterzuleiten.
  
Wie im folgenden Diagramm dargestellt, kann Trey Research die Anforderung erfüllen, Office 365 Datenverkehr über das Internet und eine Teilmenge des Datenverkehrs über Express Route mit einer Kombination aus Routing-und ausgehenden Proxy Konfigurationsänderungen weiterzuleiten.
  
1. Verwenden der von [uns veröffentlichten #2 PAC-Datei](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies) zum Weiterleiten des Datenverkehrs über einen separaten Internet Ausgangspunkt für Azure Express Route für Office 365.

2. Clients werden mit einer Standardroute zu den Proxys von Trey Research konfiguriert.

In diesem Beispielszenario verwendet Trey Research ein ausgehendes Proxygerät. In ähnlicher Weise möchten Kunden, die Azure Express Route nicht für Office 365 verwenden, diese Technik verwenden, um Datenverkehr basierend auf den Kosten für die Überprüfung des Datenverkehrs, der für bekannte High-Volume-Endpunkte bestimmt ist, weiterzuleiten.
  
Die höchsten FQDNs für Exchange Online, SharePoint Online und Skype for Business Online lauten wie folgt:
  
![Express Route Kunden-Edge-Netzwerk](../media/dab8cc42-b1d6-46d6-b2f6-d70f9e16d5ea.png)
  
- Outlook.office365.com, Outlook.Office.com

- \<tenant-name\>. SharePoint.com, \<tenant-name\> -My.SharePoint.com, \<tenant-name\> - \<app\> . SharePoint.com

- \*. Lync.com zusammen mit den IP-Bereichen für nicht-TCP-Datenverkehr

- \*Broadcast.officeapps.Live.com, \* Excel.officeapps.Live.com, \* OneNote.officeapps.Live.com, \* PowerPoint.officeapps.Live.com, \* View.officeapps.Live.com, \* Visio.officeapps.Live.com, \* Word-Edit.officeapps.Live.com, \* Word-View.officeapps.Live.com, Office.Live.com

Erfahren Sie mehr über das [bereitstellen und Verwalten von Proxyeinstellungen in Windows 8](https://blogs.technet.com/b/deploymentguys/archive/2013/05/08/windows-8-supporting-proxy-services-with-static-configurations-web-hosted-pac-files-and-domain-policy-configured-proxy.aspx) und stellen Sie sicher, dass [Office 365 nicht von Ihrem Proxy gedrosselt wird](https://blogs.technet.com/b/onthewire/archive/2014/03/28/ensuring-your-office-365-network-connection-isn-t-throttled-by-your-proxy.aspx).
  
Bei einer einzelnen Express Route-Schaltung gibt es keine hohe Verfügbarkeit für Trey Research. In dem Fall, in dem Trey redundante Edge-Geräte, die die Express Route-Konnektivität verarbeiten, fehlschlagen, wird keine zusätzliche Express Route-Schaltung zum Failover ausgeführt. Dadurch wird die Trey-Forschung in einem Dilemma gelassen, da das Failover in das Internet eine manuelle Neukonfiguration und in einigen Fällen neue IP-Adressen erfordert. Wenn Trey hohe Verfügbarkeit hinzufügen möchte, besteht die einfachste Lösung darin, für jeden Standort zusätzliche Express Route-Schaltkreise hinzuzufügen und die Schaltkreise aktiv/aktiv zu konfigurieren.
  
## <a name="routing-expressroute-for-office-365-with-multiple-locations"></a>Routing Express Route für Office 365 mit mehreren Standorten

Das letzte Szenario: das Routing Office 365 Datenverkehrs über Express Route ist die Grundlage für eine noch komplexere Routingarchitektur. Unabhängig von der Anzahl der Standorte, der Anzahl von Kontinenten, in denen diese Standorte vorhanden sind, wird die Anzahl von Express Route-Schaltkreisen usw. erforderlich sein, um einige Datenverkehr zum Internet und einige Datenverkehr über Express Route weiterleiten zu können.
  
Die zusätzlichen Fragen, die für Kunden mit mehreren Standorten in mehreren geografischen Regionen beantwortet werden müssen, sind:
  
1. Benötigen Sie einen Express Route-Schaltkreis an jedem Standort? Wenn Sie Skype for Business Online verwenden oder sich mit der Latenz Empfindlichkeit für SharePoint Online oder Exchange Online beschäftigen, wird an jedem Standort ein redundantes Paar aktiver/aktiver Express Route-Schaltungen empfohlen. Weitere Informationen finden Sie im Leitfaden zur Skype for Business Medienqualität und Netzwerkkonnektivität.

2. Wenn eine Express Route-Schaltung in einer bestimmten Region nicht verfügbar ist, wie soll Office 365 bestimmten Datenverkehr weitergeleitet werden?

3. Was ist die bevorzugte Methode für die Konsolidierung des Datenverkehrs im Fall von Netzwerken mit vielen kleinen Standorten?

Jede dieser Anforderungen stellt eine besondere Herausforderung dar, bei der Sie Ihr eigenes Netzwerk sowie die von Microsoft verfügbaren Optionen bewerten müssen.

|**Berücksichtigt**|**Auszuwertende Netzwerkkomponenten**|
|:-----|:-----|
|Schaltungen an mehr als einem Standort  <br/> |Es wird empfohlen, mindestens zwei Schaltkreise aktiv/aktiv zu konfigurieren.  <br/> Kosten, Wartezeit und Bandbreitenbedarf müssen verglichen werden.  <br/> Verwenden Sie BGP-Routen Kosten, PAC-Dateien und NAT, um das Routing mit mehreren Schaltkreisen zu verwalten.  <br/> |
|Routing von Speicherorten ohne Express Route-Schaltkreis  <br/> |Wir empfehlen die Ausstiegs-und DNS-Auflösung so nahe wie die Person, die die Anforderung für Office 365 initiiert.  <br/> Die DNS-Weiterleitung kann verwendet werden, damit Remoteniederlassungen den entsprechenden Endpunkt ermitteln können.  <br/> Für Clients in der Remoteniederlassung muss eine Route zur Verfügung stehen, die Zugriff auf die Express Route-Schaltung bietet.  <br/> |
|Kleine Office-Konsolidierung  <br/> |Die verfügbare Bandbreite und Datennutzung sollten sorgfältig verglichen werden.  <br/> |

> [!NOTE]
> Microsoft bevorzugt Express Route über das Internet, wenn die Route unabhängig vom physischen Standort verfügbar ist.
  
Jeder dieser Aspekte muss für jedes eindeutige Netzwerk berücksichtigt werden. Unten sehen Sie ein Beispiel.
  
### <a name="example-2-multi-geographic-locations"></a>Beispiel 2: mehr geografische Standorte
  
Dieses Beispiel ist ein Szenario für ein fiktives Unternehmen namens Humongous Insurance, das über mehrere geografische Standorte verfügt.
  
Humongous Insurance ist geografisch mit Niederlassungen auf der ganzen Welt verstreut. Sie möchten Azure Express Route für Office 365 implementieren, um den Großteil des Office 365 Datenverkehrs in direkten Netzwerkverbindungen beizubehalten. Humongous Insurance verfügt auch über Niederlassungen auf zwei weiteren Kontinenten. Die Mitarbeiter in der Remoteniederlassung, in der Express Route nicht durchführbar ist, müssen an eine oder beide der primären Einrichtungen zurückgeleitet werden, um eine Express Route-Verbindung zu verwenden.
  
Das Leitprinzip besteht darin, so schnell wie möglich Office 365 bestimmten Datenverkehr an ein Microsoft-Rechenzentrum zu erhalten. In diesem Beispiel muss Humongous Insurance entscheiden, ob Ihre Remoteniederlassungen so schnell wie möglich über eine Verbindung über das Internet an ein Microsoft-Rechenzentrum weitergeleitet werden sollen oder ob Ihre Remoteniederlassungen über ein internes Netzwerk weitergeleitet werden sollen, um so schnell wie möglich über eine Express Route-Verbindung an ein Microsoft-Rechenzentrum zu gelangen.
  
Die Rechenzentren, Netzwerke und Anwendungsarchitektur von Microsoft sind so konzipiert, dass Sie eine global verteilte Kommunikation durchführen und Sie so effizient wie möglich bedienen. Dies ist eines der größten Netzwerke der Welt. Anforderungen für Office 365, die länger als erforderlich in Kundennetzwerken verbleiben, können diese Architektur nicht nutzen.
  
In der Situation von Humongous Insurance sollten diese abhängig von den Anwendungen, die Sie über Express Route verwenden möchten, fortgesetzt werden. Wenn es sich beispielsweise um einen Skype for Business Online Kunden handelt oder wenn Sie die Express Route-Konnektivität beim Herstellen einer Verbindung mit externen Skype for Business Online Besprechungen verwenden möchten, empfiehlt es sich, im Skype for Business Online Media Quality and Network Connectivity Guide eine zusätzliche Express Route-Schaltung für den dritten Standort zu erstellen. Dies kann aus Sicht des Netzwerks teurer sein; das Weiterleiten von Anforderungen von einem Kontinent an einen anderen, bevor es an ein Microsoft-Rechenzentrum weitergeleitet wird, kann bei Skype for Business Online Besprechungen und Kommunikationen jedoch zu einer schlechten oder unbrauchbaren Erfahrung führen.
  
Wenn Humongous Insurance keine Skype for Business Online in irgendeiner Weise nutzt oder plant, kann das Weiterleiten Office 365 bestimmtem Netzwerkdatenverkehr zurück an einen Kontinent mit einer Express Route-Verbindung möglicherweise jedoch zu unnötiger Wartezeit oder TCP-Überlastung führen. In beiden Fällen wird empfohlen, das Internet, das an den lokalen Standort gesendet wird, an das Internet weiterzuleiten, um die Netzwerke für die Inhaltsübermittlung zu nutzen, auf denen Office 365 basiert.
  
![Express Route Multi-geography](../media/98fdd883-2c5a-4df7-844b-bd28cd0b9f50.png)
  
Wenn Humongous Insurance die Multi-geography-Strategie plant, müssen Sie eine Reihe von Aspekten berücksichtigen, die sich auf die Größe der Schaltung, die Anzahl der Schaltkreise, das Failover und so weiter ausgehen.
  
Mit Express Route an einem zentralen Standort mit mehreren Regionen, die versuchen, die Schaltung zu verwenden, möchte Humongous Insurance sicherstellen, dass Verbindungen mit Office 365 aus dem Remote-Office an das nächstgelegene Office 365-Rechenzentrum gesendet werden und am Hauptsitz des Standorts empfangen werden. Dazu implementiert Humongous Insurance die DNS-Weiterleitung, um die Anzahl von Roundtrips und DNS-Lookups zu reduzieren, die erforderlich sind, um die entsprechende Verbindung mit der Office 365 Umgebung herzustellen, die am nächsten am Hauptsitz des Internet Ausgangs Points liegt. Dadurch wird verhindert, dass der Client einen lokalen Front-End-Server auflöst und stellt sicher, dass der Front-End-Server, mit dem die Person eine Verbindung herstellt, sich in der Nähe des Hauptquartiers befindet, in dem Humongous Insurance Microsoft Sie können auch erfahren, [wie Sie eine bedingte Weiterleitung für einen Domänennamen zuweisen](https://technet.microsoft.com/library/Cc794735%28v=WS.10%29.aspx).
  
In diesem Szenario würde der Datenverkehr vom Remotestandort die Office 365-Front-End-Infrastruktur in Nordamerika auflösen und Office 365 nutzen, um gemäß der Architektur der Office 365 Anwendung eine Verbindung mit den Back-End-Servern herzustellen. Beispielsweise würde Exchange Online die Verbindung in Nordamerika beenden, und diese Front-End-Server würden eine Verbindung mit dem Back-End-Postfachserver herstellen, wo auch immer der Mandant gewohnt hat. Alle Dienste verfügen über einen weit verteilten Front-Door-Dienst, der aus Unicast-und Anycast-Destinationen besteht.
  
Wenn Humongous wichtige Niederlassungen in mehreren Kontinenten aufweist, werden mindestens zwei aktive/aktive Schaltkreise pro Region empfohlen, um die Wartezeit für vertrauliche Anwendungen wie Skype for Business Online zu verringern. Wenn sich alle Niederlassungen auf einem einzelnen Kontinent befinden oder keine Zusammenarbeit in Echtzeit verwendet wird, ist die Verwendung eines konsolidierten oder verteilten Ausgangs Points eine kundenspezifische Entscheidung. Wenn mehrere Schaltkreise verfügbar sind, wird durch das BGP-Routing ein Failover sichergestellt, wenn ein einzelner Schaltkreis nicht mehr verfügbar ist.
  
Erfahren Sie mehr über Beispiel [Routingkonfigurationen](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-routing/) und [https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/](https://azure.microsoft.com/documentation/articles/expressroute-config-samples-nat/) .
  
## <a name="selective-routing-with-expressroute"></a>Selektives Routing mit Express Route

Das selektive Routing mit Express Route ist möglicherweise aus einer Vielzahl von Gründen erforderlich, beispielsweisedurch testen und Rollout von Express Route auf eine Teilmenge von Benutzern. Es gibt verschiedene Tools, mit denen Kunden Office 365 Netzwerkdatenverkehr über Express Route selektiv weiterleiten können:
  
1. **Routen Filterung/-Trennung** : das BGP führt zu Office 365 über Express Route zu einer Teilmenge der Subnetze oder Router. Diese selektiv Routen nach Kundennetzwerk Segment oder Standort des physischen Büros. Dies ist häufig für eine atemberaubende Einführung von Express Route für Office 365 und ist auf Ihren BGP-Geräten konfiguriert.

2. **PAC-Dateien/URLs** – Directing Office 365 bestimmten Netzwerkdatenverkehr für bestimmte FQDNs an einen bestimmten Pfad weiterleiten. Diese selektive Routen von Clientcomputer, wie durch [PAC-Datei Bereitstellung](https://aka.ms/manageo365endpoints#ID0EACAAA=2._Proxies)identifiziert.

3. **Routen Filterung**  -  [Routenfilter](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) sind eine Möglichkeit, eine Teilmenge unterstützter Dienste über Microsoft Peering zu nutzen.

4. **BGP Communities** – Filterung basierend auf [BGP-Community-Tags](https://aka.ms/bgpexpressroute365) ermöglicht es einem Kunden, festzustellen, welche Office 365 Anwendungen Express Route durchlaufen und welche durch das Internet übertragen werden.

Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/erorouting](https://aka.ms/erorouting)
  
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
  
[Verwenden von BGP-Communities in Express Route für Office 365 Szenarien](bgp-communities-in-expressroute.md)
  
[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](performance-tuning-using-baselines-and-history.md)
  
[Plan zur Problembehandlung für Office 365](performance-troubleshooting-plan.md)
  
[URLs und IP-Adressbereiche für Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365-Netzwerk- und Leistungsoptimierung](network-planning-and-performance.md)
