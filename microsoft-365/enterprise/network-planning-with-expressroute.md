---
title: Netzwerkplanung mit ExpressRoute für Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/14/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 103208f1-e788-4601-aa45-504f896511cd
description: In diesem Artikel erfahren Sie mehr über Azure Express Route für Office 365 und wie Sie es für die Netzwerkplanung nutzen können.
ms.openlocfilehash: 7159640adeae1b4a4ff364683f939a97b6e06a92
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690600"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Netzwerkplanung mit ExpressRoute für Office 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Express Route für Office 365 bietet Layer 3-Konnektivität zwischen Ihrem Netzwerk und den Rechenzentren von Microsoft. Die Schaltkreise verwenden BGP (Border Gateway Protocol)-Routenankündigungen von Office 365-Front-End-Servern. Wenn Sie den richtigen TCP/IP-Pfad für Office 365 auswählen müssen, wird Azure Express Route aus Sicht Ihrer lokalen Geräte als Alternative zum Internet betrachtet.
  
Azure Express Route fügt einen direkten Pfad zu einer bestimmten Gruppe unterstützter Features und Dienste hinzu, die von Office 365 Servern in den Microsoft-Rechenzentren angeboten werden. Azure Express Route ersetzt keine Internetkonnektivität mit Microsoft-Rechenzentren oder grundlegenden Internetdiensten wie der Auflösung von Domänennamen. Azure Express Route und Ihre Internet Schaltungen sollten gesichert und redundant sein.
  
In der folgenden Tabelle werden einige Unterschiede zwischen den Internet-und Azure Express Route-Verbindungen im Kontext von Office 365 hervorgehoben.

|**Unterschiede bei der Netzwerkplanung**|**Internet Netzwerkverbindung**|**Express Route-Netzwerkverbindung**|
|:-----|:-----|:-----|
| Zugriff auf erforderliche Internetdienste, einschließlich;  <br/>  DNS-Namensauflösung  <br/>  Überprüfung der Zertifikatsperrung  <br/>  Netzwerke für die Inhaltsübermittlung (CDNs)  <br/> |Ja  <br/> |Anforderungen an die in Microsoft Besitz befindliche DNS-und/oder CDN-Infrastruktur verwenden möglicherweise das Express Route-Netzwerk.  <br/> |
| Zugriff auf Office 365 Dienste, einschließlich;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype for Business Online  <br/>  Office in einem Browser  <br/>  Office 365 Portal und Authentifizierung  <br/> |Ja, alle Anwendungen und Funktionen  <br/> |Ja, [bestimmte Anwendungen und Features](https://aka.ms/o365endpoints) <br/> |
|Lokale Sicherheit im Umkreis.  <br/> |Ja  <br/> |Ja  <br/> |
|Planung für hohe Verfügbarkeit.  <br/> |Failover auf eine Alternative Internetnetzwerkverbindung  <br/> |Failover auf eine Alternative Express Route-Verbindung  <br/> |
|Direkte Verbindung mit einem vorhersagbaren Netzwerkprofil.  <br/> |Nein  <br/> |Ja  <br/> |
|IPv6-Konnektivität.  <br/> |Ja  <br/> |Ja  <br/> |

Erweitern Sie die folgenden Titel, um weitere Anleitungen zur Netzwerkplanung zu finden. Wir haben auch ein 10-teiliges [Azure-Express Route für Office 365 Schulungs](https://channel9.msdn.com/series/aer) Reihe aufgenommen, die tiefer geht.

## <a name="existing-azure-expressroute-customers"></a>Vorhandene Azure Express Route-Kunden

Wenn Sie eine vorhandene Azure Express Route-Schaltung verwenden und über diese Schaltung Office 365 Konnektivität hinzufügen möchten, sollten Sie sich die Anzahl der Schaltkreise, Ausgangspositionen und die Größe der Schaltkreise ansehen, um sicherzustellen, dass Sie die Anforderungen Ihrer Office 365 Nutzung erfüllen. Die meisten Kunden benötigen zusätzliche Bandbreite, und viele erfordern zusätzliche Schaltkreise.
  
Um den Zugriff auf Office 365 über Ihre vorhandenen Azure Express Route-Schaltkreise zu ermöglichen, [Konfigurieren Sie die Routenfilter](https://docs.microsoft.com/azure/expressroute/how-to-routefilter-portal) , um sicherzustellen, dass auf die Office 365 Dienste zugegriffen werden kann.
  
Das Azure Express Route-Abonnement ist kundenorientiert, was bedeutet, dass Abonnements an Kunden gebunden sind. Als Kunde können Sie mehrere Azure Express Route-Schaltkreise haben und auf viele Microsoft-Cloud-Ressourcen über diese Schaltkreise zugreifen können. Sie können beispielsweise festlegen, dass auf einen Azure Hosted Virtual Machine, einen Office 365 Testmandanten und einen Office 365 Produktions Mandanten über ein paar redundanter Azure Express Route-Schaltkreise zuzugreifen.
  
In dieser Tabelle werden die beiden Arten von Peering-Beziehungen beschrieben, die Sie für die Implementierung über Ihre Schaltkreise auswählen können.

|**Peering-Beziehung**|**Azure privat**|**Microsoft**|
|:-----|:-----|:-----|
|**Dienste** <br/> |IaaS: virtuelle Azure-Computer  <br/> |PaaS: Azure Public Services  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Verbindungs Initiierung * * * * <br/> |Kunden-zu-Microsoft  <br/> Microsoft-to-Customer  <br/> |Kunden-zu-Microsoft  <br/> Microsoft-to-Customer  <br/> |
|**QoS-Unterstützung** <br/> |Keine QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1 </sup> QoS unterstützt Skype for Business nur zu diesem Zeitpunkt.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Bandbreitenplanung für Azure Express Route

Jeder Office 365-Kunde hat eine eindeutige Bandbreitenanforderung, je nach Anzahl der Personen an den einzelnen Standorten, wie aktiv Sie mit jeder Office 365 Anwendung sind, und anderen Faktoren wie der Verwendung von lokalen oder hybriden Geräten und Netzwerk Sicherheitskonfigurationen.
  
Eine zu geringe Bandbreite führt zu Überlastung, Datenübertragungen und unvorhersehbaren Verzögerungen. Eine zu große Bandbreite führt zu unnötigen Kosten. In einem vorhandenen Netzwerk wird die Bandbreite häufig im Hinblick auf die verfügbaren Kopf Freiheitsgrade auf dem Stromkreis als Prozentsatz bezeichnet. Bei einer Kapazität von 10% wird eine Überlastung voraussichtlich zur Folge haben, und eine Kapazität von 80% bedeutet im allgemeinen unnötige Kosten. Typische Kapazitätszuweisungen für die Zielvorgabe liegen bei 20% bis 50%.
  
Um die richtige Bandbreite zu finden, ist es am besten, den vorhandenen Netzwerk Verbrauch zu testen. Dies ist die einzige Möglichkeit, ein echtes Maß an Nutzung und Bedarf zu erhalten, da jede Netzwerkkonfiguration und Anwendungen in gewisser Hinsicht eindeutig sind. Wenn Sie messen möchten, müssen Sie genau auf die gesamte Bandbreitenauslastung, Wartezeit und TCP-Überlastung achten, um Ihre Netzwerkanforderungen zu verstehen.
  
Sobald Sie einen geschätzten Basisplan mit allen Netzwerkanwendungen haben, wird Pilot Office 365 mit einer kleinen Gruppe, die die verschiedenen Profile von Personen in Ihrer Organisation umfasst, um die tatsächliche Nutzung zu ermitteln, und die beiden Messungen verwenden, um die Bandbreite zu schätzen, die Sie für die einzelnen Office-Standorte benötigen. Wenn bei Ihren Tests Latenz-oder TCP-Überlastungsprobleme auftreten, müssen Sie den Ausstieg möglicherweise näher an die Personen mit Office 365 oder intensiven Netzwerkscans wie SSL-Entschlüsselung/-Inspektion ziehen.
  
Alle unsere Empfehlungen für die Art der Netzwerkverarbeitung, die empfohlen wird, gelten sowohl für Express Route als auch für Internet-Schaltkreise. Dies gilt auch für die restlichen Anleitungen auf unserer [Leistungs Optimierungs Website](https://aka.ms/tune).
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Anwenden von Sicherheitssteuerelementen auf Azure Express Route für Office 365 Szenarien

Das Sichern der Azure Express Route-Konnektivität beginnt mit den gleichen Prinzipien wie das Sichern der Internet Konnektivität. Viele Kunden entscheiden sich für die Bereitstellung von Netzwerk-und Umkreis Steuerungen entlang des Express Route-Pfads, der Ihr lokales Netzwerk mit Office 365 und anderen Microsoft-Clouds verbindet. Diese Steuerelemente können Firewalls, Anwendungsproxys, Verhinderung von Datenverlust, Intrusionserkennung, Intrusion Prevention-Systeme usw. umfassen. In vielen Fällen wenden Kunden unterschiedliche Ebenen von Steuerelementen auf den Datenverkehr an, der von lokalen Microsoft-Datenverkehr initiiert wird, im Gegensatz zum von Microsoft initiierten Datenverkehr, der von einem lokalen Kundendienst initiiert wird, im Gegensatz zum Datenverkehr, der von lokalen Benutzern zu einem allgemeinen Internet Ziel gestartet wird.
  
Im folgenden finden Sie einige Beispiele für die Integration von Sicherheit mit dem [Express Route-Verbindungsmodell](https://docs.microsoft.com/azure/expressroute/expressroute-connectivity-models) , das Sie bereitstellen möchten.

|**Express Route-Integrations Option**|**Netzwerk Sicherheitsumkreis Modell**|
|:-----|:-----|
|Co-Location bei einem Cloud Exchange  <br/> |Installieren neuer oder nutzen vorhandener Sicherheit/Umkreis Infrastruktur in der Co-Location-Einrichtung, in der die Express Route-Verbindung hergestellt wird.  <br/> Nutzen Sie die Co-Location-Funktion ausschließlich für Routing/Interconnect-Zwecke und für Back-Haul-Verbindungen von einer Co-Location-Anlage in die lokale Sicherheits-/Umkreis Infrastruktur.  <br/> |
|Punkte-zu-Ort-Ethernet  <br/> |Beenden Sie die Punkt-zu-Punkt-Express Route-Verbindung in dem vorhandenen lokalen Sicherheits-/Umkreis Infrastruktur Standort.  <br/> Installieren Sie die neue Sicherheits-/Umkreis Infrastruktur speziell für den Express Route-Pfad, und beenden Sie die Verbindung zu einem Endpunkt.  <br/> |
|Any-to-any-IPVPN  <br/> |Nutzen Sie eine vorhandene lokale Security/Perimeter-Infrastruktur an allen Standorten, die sich in das IPVPN für Express Route für Office 365-Konnektivität Eingewöhnen.  <br/> Haarnadeln Sie die für Express Route verwendeten IPVPN für Office 365 auf bestimmte lokale Standorte, die als Sicherheit/Umkreis dienen.  <br/> |

Einige Dienstanbieter bieten auch verwaltete Sicherheit/Perimeter-Funktionalität als Teil ihrer Integrationslösungen mit Azure Express Route.
  
Wenn Sie die Topologie der Netzwerk/Sicherheitsperimeter-Optionen für die Express Route für Office 365 Verbindungen in Betracht ziehen, sind weitere Überlegungen zu berücksichtigen:
  
- Die Steuerelemente Depth und Type Network/Security haben möglicherweise Auswirkungen auf die Leistung und Skalierbarkeit der Office 365 Benutzeroberfläche.

- Ausgehende (lokal- \> Microsoft) und eingehende (Microsoft- \> lokale) [Wenn aktiviert] fließt möglicherweise andere Anforderungen. Diese sind wahrscheinlich unterschiedlich als ausgehende zu allgemeinen Internet-Destinationen.

- Office 365 Anforderungen für Ports/Protokolle und erforderliche IP-Subnetze sind identisch, unabhängig davon, ob der Datenverkehr über Express Route für Office 365 oder über das Internet weitergeleitet wird.

- Die topologische Platzierung der Kunden-Netzwerk/Sicherheitskontrollen bestimmt das ultimative End-to-End-Netzwerk zwischen dem Benutzer und Office 365 Dienst und kann erhebliche Auswirkungen auf die Wartezeit und Überlastung des Netzwerks haben.

- Kunden werden ermutigt, ihre Sicherheit/Umkreis Topologie für die Verwendung mit Express Route für Office 365 gemäß den bewährten Methoden für Redundanz, hohe Verfügbarkeit und Notfallwiederherstellung zu entwerfen.

Hier ist ein Beispiel für die Woodgrove Bank, die die verschiedenen Azure Express Route-Verbindungsoptionen mit den oben besprochenen Sicherheitsmodellen für Perimeter vergleicht.
  
### <a name="example-1-securing-azure-expressroute"></a>Beispiel 1: Sichern von Azure Express Route
  
Die Woodgrove Bank erwägt die Implementierung von Azure Express Route und nach der Planung der optimalen Architektur für das [Routing mit Express Route für Office 365](routing-with-expressroute.md) und nach der Verwendung der obigen Anleitungen zum Verständnis der Bandbreitenanforderungen bestimmen Sie die beste Methode für die Sicherung Ihres Perimeters.
  
Für Woodgrove, eine multinationale Organisation mit Standorten auf mehreren Kontinenten, muss sich die Sicherheit über alle Perimeter erstrecken. Die optimale Verbindungsoption für Woodgrove ist eine Mehrpunkt-Verbindung mit mehreren Peering-Standorten auf der ganzen Welt, um die Anforderungen Ihrer Mitarbeiter in jedem Kontinent zu bedienen. Jeder Kontinent umfasst redundante Azure Express Route-Schaltkreise innerhalb des Kontinents, und die Sicherheit muss alle diese umfassen.
  
Die vorhandene Infrastruktur von Woodgrove ist zuverlässig und kann die zusätzliche Arbeit bewältigen, sodass die Woodgrove Bank in der Lage ist, die Infrastruktur für Ihre Azure-Express Route und die Sicherheit des Internet Perimeters zu nutzen. Wenn dies nicht der Fall war, könnte Woodgrove beschließen, zusätzliche Geräte zu erwerben, um die vorhandenen Geräte zu ergänzen oder um eine andere Art von Verbindung zu verarbeiten.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Hohe Verfügbarkeit und Failover mit Azure Express Route
<a name="BKMK_high-availability"> </a>

Es wird empfohlen, mindestens zwei aktive Schaltkreise für jeden Ausstieg mit Express Route an Ihren Express Route-Anbieter zu über stellen. Dies ist der häufigste Ort, an dem Fehler für Kunden angezeigt werden, und Sie können dies ganz einfach vermeiden, indem Sie ein paar aktiver/aktiver Express Route-Schaltkreise einteilen. Außerdem empfehlen wir mindestens zwei Active/Active-Internet-Schaltkreise, da viele Office 365 Dienste nur über das Internet verfügbar sind.
  
Innerhalb des Ausgangs Points Ihres Netzwerks sind viele andere Geräte und Schaltkreise, die eine wichtige Rolle bei der Wahrnehmung von Verfügbarkeit spielen. Diese Bereiche Ihrer Verbindungsszenarien werden nicht von Express Route oder Office 365-SLAs abgedeckt, aber Sie spielen eine wichtige Rolle in der End-to-End-Dienstverfügbarkeit, die von Personen in Ihrer Organisation wahrgenommen wird.
  
Konzentrieren Sie sich auf die Personen, die Office 365 verwenden, und wenn ein Ausfall einer Komponente die Erfahrung der Benutzer mit dem Dienst beeinträchtigen würde, suchen Sie nach Möglichkeiten, den Gesamtprozentsatz betroffener Personen zu begrenzen. Wenn ein Failovermodus operativ Komplex ist, sollten Sie die langjährige Erfahrung der Benutzer für die Wiederherstellung betrachten und nach Betriebs einfachen und automatischen Failover-Modi suchen.
  
Außerhalb Ihres Netzwerks haben Office 365, Express Route und Ihr Express Route-Anbieter unterschiedliche Verfügbarkeitsstufen.
  
### <a name="service-availability"></a>Service Availability
  
- Office 365 Dienste werden durch gut definierte Vereinbarungen zum [Service Level](https://technet.microsoft.com/library/office-365-service-level-agreement.aspx)abgedeckt, die Verfügbarkeits-und Verfügbarkeits Metriken für einzelne Dienste umfassen. Ein Grund Office 365 eine solche hohe Service Verfügbarkeitsstufe aufrecht erhalten kann, besteht darin, dass einzelne Komponenten nahtlos zwischen den zahlreichen Microsoft-Rechenzentren mit dem globalen Microsoft-Netzwerk ein Failover ausführen können. Dieses Failover reicht vom Rechenzentrum und Netzwerk bis hin zu den mehreren Internet Ausgangspunkten und ermöglicht ein nahtloses Failover aus der Perspektive der Personen, die den Dienst verwenden.

- Express Route [bietet eine 99,9% ige Verfügbarkeits SLA](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) für einzelne dedizierte Schaltkreise zwischen dem Microsoft-Netzwerk Edge und dem Express Route-Anbieter oder der Partner Infrastruktur. Diese Dienststufen werden auf der Express Route-Schaltkreisebene angewendet, die aus [zwei unabhängigen Verbindungen](https://azure.microsoft.com/documentation/articles/expressroute-introduction/) zwischen den redundanten Microsoft-Geräten und den Netzwerkanbieter Geräten an jedem Peering-Standort besteht.

### <a name="provider-availability"></a>Anbieter Verfügbarkeit
  
- Die Vereinbarungen zum Service Level von Microsoft halten bei Ihrem Express Route-Anbieter oder-Partner an. Dies ist auch der erste Ort, an dem Sie Entscheidungen treffen können, die ihre Verfügbarkeitsstufe beeinflussen. Sie sollten die Architektur-, Verfügbarkeits-und Ausfall Sicherheitsmerkmale, die Ihr Express Route-Anbieter zwischen dem Netzwerkperimeter und ihrer Anbieterverbindung an jedem Microsoft Peering-Standort bietet, genau bewerten. Achten Sie genau auf die logischen und physischen Aspekte der Redundanz, der Peering-Ausrüstung, der Anbieter für WAN-Schaltungen sowie auf alle zusätzlichen Mehrwertdienste wie NAT-Dienste oder verwaltete Firewalls.

### <a name="designing-your-availability-plan"></a>Entwerfen Ihres Verfügbarkeits Plans
  
Es wird dringend empfohlen, hohe Verfügbarkeit und Ausfallsicherheit in ihren End-to-End-Verbindungsszenarien für Office 365 zu planen und zu entwerfen. Ein Entwurf sollte enthalten;
  
- keine einzelnen Fehlerquellen, einschließlich Internet-und Express Route-Schaltungen.

- Minimierung der Anzahl betroffener Personen und der Dauer dieser Auswirkungen für die meisten erwarteten Fehlermodi.

- Optimieren für einfachen, wiederholbaren und automatischen Wiederherstellungsprozess von den meisten erwarteten Fehlermodi.

- unterstützen der vollständigen Anforderungen Ihres Netzwerkdatenverkehrs und ihrer Funktionalität über redundante Pfade ohne erhebliche Beeinträchtigungen.

Ihre Verbindungsszenarien sollten eine Netzwerktopologie enthalten, die für mehrere unabhängige und aktive Netzwerkpfade zu Office 365 optimiert ist. Dadurch ergibt sich eine bessere End-to-End-Verfügbarkeit als eine Topologie, die nur für die Redundanz auf der Ebene der einzelnen Geräte oder Geräte optimiert ist.
  
> [!TIP]
> Wenn Ihre Benutzer über mehrere Kontinente oder geografische Regionen verteilt sind und jeder dieser Standorte über redundante WAN-Schaltkreise mit einem einzigen lokalen Standort verbunden ist, auf dem sich eine einzelne Express Route-Schaltung befindet, wird Ihren Benutzern eine geringere End-to-End-Dienstverfügbarkeit als ein Netzwerktopologie-Design mit unabhängigen Express Route-Schaltkreisen zur Verfügung gestellt, die die verschiedenen Regionen mit dem
  
Es wird empfohlen, mindestens zwei Express Route-Schaltkreise für jede Verbindung mit einem anderen geografischen Peering-Standort zu bieten. Sie sollten dieses aktive-aktive Paar von Schaltkreisen für jede Region, in der Benutzer die Express Route-Konnektivität für Office 365 Dienste verwenden, vorsehen. Dadurch kann jede Region während eines Notfalls verbunden bleiben, der sich auf einen Hauptstandort wie ein Rechenzentrum oder einen Peering-Standort auswirkt. Wenn Sie Sie als aktiv/aktiv konfigurieren, können Endbenutzer Datenverkehr über mehrere Netzwerkpfade verteilt werden. Dies reduziert den Umfang der Personen, die bei Geräten oder Netzwerkausfällen betroffen sind.
  
Es wird nicht empfohlen, eine einzelne Express Route-Schaltung mit dem Internet als Sicherung zu verwenden.
  
### <a name="example-2-failover-and-high-availability"></a>Beispiel 2: Failover und hohe Verfügbarkeit
  
Das Multi-Geographic-Design der Woodgrove Bank hat eine Überprüfung des Routings, der Bandbreite und der Sicherheit durchlaufen und muss nun über eine hoch Verfügbarkeitsüberprüfung verfügen. Woodgrove denkt an hohe Verfügbarkeit als Deckung für drei Kategorien; Ausfallsicherheit, Zuverlässigkeit und Redundanz.
  
Ausfallsicherheit ermöglicht Woodgrove die schnelle Wiederherstellung nach Fehlern. Zuverlässigkeit ermöglicht es Woodgrove, ein konsistentes Ergebnis innerhalb des Systems anzubieten. Durch Redundanz kann Woodgrove zwischen einer oder mehreren gespiegelten Infrastruktur Instanzen umsteigen.
  
Innerhalb jeder Edge-Konfiguration verfügt Woodgrove über redundante Firewalls, Proxys und IDs. Für Nordamerika verfügt Woodgrove über eine Edge-Konfiguration in Ihrem Dallas-Rechenzentrum und eine weitere Edge-Konfiguration in Ihrem Virginia-Rechenzentrum. Die redundanten Geräte an jedem Standort bieten Ausfallsicherheit für diesen Standort.
  
Die Netzwerkkonfiguration bei der Woodgrove Bank wird basierend auf einigen wichtigen Grundsätzen erstellt:
  
- Innerhalb jeder geografischen Region gibt es mehrere Azure Express Route-Schaltkreise.

- Jeder Stromkreis innerhalb eines Bereichs kann den gesamten Netzwerkdatenverkehr in dieser Region unterstützen.

- Routing bevorzugt den einen oder anderen Pfad je nach Verfügbarkeit, Standort usw.

- Das Failover zwischen Azure Express Route-Schaltkreisen erfolgt automatisch ohne zusätzliche Konfiguration oder Aktion, die von Woodgrove benötigt wird.

- Das Failover zwischen Internet Schaltkreisen erfolgt automatisch ohne zusätzliche Konfiguration oder Aktion, die von Woodgrove benötigt wird.

In dieser Konfiguration mit Redundanz auf physischer und virtueller Ebene ist die Woodgrove Bank in der Lage, die lokale Ausfallsicherheit, regionale Ausfallsicherheit und globale Ausfallsicherheit auf zuverlässige Weise anzubieten. Woodgrove hat diese Konfiguration gewählt, nachdem eine einzelne Azure Express Route-Schaltung pro Region ausgewertet wurde und die Möglichkeit eines Failovers auf das Internet vorliegt.
  
Wenn Woodgrove keine mehrere Azure Express Route-Schaltkreise pro Region haben konnte, würde das Routing von Datenverkehr mit Ursprung in Nordamerika an die Azure Express Route-Schaltung in Asia Pacific ein unannehmbares Maß an Latenz und die erforderliche DNS-Weiterleitungskonfiguration zu Komplexität hinzufügen.
  
Die Nutzung des Internets als Sicherungskonfiguration wird nicht empfohlen. Dadurch wird das Woodgrove-Zuverlässigkeits Prinzip gebrochen, was zu einer inkonsistenten Erfahrung mit der Verbindung führt. Darüber hinaus wäre eine manuelle Konfiguration für ein Failover erforderlich, in dem die konfigurierten BGP-Ankündigungen, die NAT-Konfiguration, die DNS-Konfiguration und die Proxykonfiguration berücksichtigt wurden. Diese zusätzliche Failover-Komplexität erhöht die Wiederherstellungszeit und verringert die Diagnose-und Problembehandlungsschritte.
  
Haben Sie noch Fragen zur Planung und Implementierung von Traffic Management oder Azure Express Route? Lesen Sie den Rest unserer [Netzwerk-und Leistungshinweise](https://aka.ms/tune) oder die [Azure Express Route FAQ](https://azure.microsoft.com/documentation/articles/expressroute-faqs/).
  
## <a name="working-with-azure-expressroute-providers"></a>Arbeiten mit Azure Express Route-Anbietern
<a name="BKMK_high-availability"> </a>

Wählen Sie die Speicherorte ihrer Schaltungen basierend auf der Planung Ihrer Bandbreite, Wartezeit, Sicherheit und hoher Verfügbarkeit aus. Wenn Sie die optimalen Standorte kennen, an denen Sie Schaltkreise platzieren möchten, [Überprüfen Sie die aktuelle Liste der Anbieter nach Regionen](https://azure.microsoft.com/documentation/articles/expressroute-locations/).
  
Arbeiten Sie mit Ihrem Anbieter oder Anbieter zusammen, um die besten Verbindungsoptionen, Punkte-zu-Ort-Konnektivität, Multi-Points-oder gehostete Verbindungen auszuwählen. Denken Sie daran, dass Sie die Verbindungsoptionen kombinieren und abgleichen können, solange die Bandbreite und andere redundante Komponenten Ihr Routing und Ihr Hochverfügbarkeitsdesign unterstützen.
  
Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/planningexpressroute365](https://aka.ms/planningexpressroute365)
  
## <a name="related-topics"></a>Verwandte Themen
<a name="BKMK_high-availability"> </a>

[Bewerten der Office 365-Netzwerkkonnektivität](assessing-network-connectivity.md)
  
[Azure ExpressRoute für Office 365](azure-expressroute.md)
  
[Verwalten von ExpressRoute für Office 365-Verbindungen](managing-expressroute-for-connectivity.md)
  
[Routing mit ExpressRoute für Office 365](routing-with-expressroute.md)
  
[Implementierung von ExpressRoute für Office 365](implementing-expressroute.md)
  
[Verwenden von BGP-Communities in Express Route für Office 365 Szenarien](bgp-communities-in-expressroute.md)
  
[Medienqualität und Netzwerkverbindungsleistung in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimieren Ihres Netzwerks für Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute und QoS in Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Anruffluss mit ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](performance-tuning-using-baselines-and-history.md)
  
[Plan zur Problembehandlung für Office 365](performance-troubleshooting-plan.md)
  
[URLs und IP-Adressbereiche für Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365-Netzwerk- und Leistungsoptimierung](network-planning-and-performance.md)
  
[Häufig gestellte Fragen zu Office 365-Endpunkten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)
