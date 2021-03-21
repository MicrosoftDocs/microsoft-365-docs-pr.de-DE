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
description: In diesem Artikel erfahren Sie mehr über Azure ExpressRoute für Office 365 und die Verwendung für die Netzwerkplanung.
ms.openlocfilehash: 440d4fafadd7e9b504dc4ffdac1123a2956ed798
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923576"
---
# <a name="network-planning-with-expressroute-for-office-365"></a>Netzwerkplanung mit ExpressRoute für Office 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

ExpressRoute für Office 365 bietet Layer 3-Konnektivität zwischen Ihrem Netzwerk und den Rechenzentren von Microsoft. Die Schaltungen verwenden Border Gateway Protocol (BGP)-Routenanzeigen der Front-End-Server von Office 365. Aus der Sicht Ihrer lokalen Geräte wird Azure ExpressRoute als Alternative zum Internet betrachtet, wenn sie den richtigen TCP/IP-Pfad zu Office 365 auswählen müssen.
  
Azure ExpressRoute fügt einen direkten Pfad zu einem bestimmten Satz unterstützter Features und Dienste hinzu, die von Office 365-Servern in den Rechenzentren von Microsoft angeboten werden. Azure ExpressRoute ersetzt keine Internetverbindung zu Microsoft-Rechenzentren oder grundlegenden Internetdiensten wie der Domänennamenauflösung. Azure ExpressRoute und Ihre Internetschaltungen sollten gesichert und redundant sein.
  
In der folgenden Tabelle werden einige Unterschiede zwischen internet- und Azure ExpressRoute-Verbindungen im Kontext von Office 365 hervorgehoben.

|**Unterschiede bei der Netzwerkplanung**|**Internetnetzwerkverbindung**|**ExpressRoute-Netzwerkverbindung**|
|:-----|:-----|:-----|
| Zugriff auf erforderliche Internetdienste, einschließlich;  <br/>  DNS-Namensauflösung  <br/>  Zertifikatsperrüberprüfung  <br/>  Netzwerke für die Inhaltsübermittlung (CDNs)  <br/> |Ja  <br/> |Anforderungen an microsofteigene DNS- und/oder CDN-Infrastruktur können das ExpressRoute-Netzwerk verwenden.  <br/> |
| Zugriff auf Office 365-Dienste, einschließlich;  <br/>  Exchange Online  <br/>  SharePoint Online  <br/>  Skype for Business Online  <br/>  Office in einem Browser  <br/>  Office 365-Portal und -Authentifizierung  <br/> |Ja, alle Anwendungen und Features  <br/> |Ja, [bestimmte Anwendungen und Features](./urls-and-ip-address-ranges.md) <br/> |
|Lokale Sicherheit am Umkreis.  <br/> |Ja  <br/> |Ja  <br/> |
|Hochverfügbarkeitsplanung.  <br/> |Failover zu einer alternativen Internetnetzwerkverbindung  <br/> |Failover zu einer alternativen ExpressRoute-Verbindung  <br/> |
|Direkte Verbindung mit einem vorhersehbaren Netzwerkprofil.  <br/> |Nein  <br/> |Ja  <br/> |
|IPv6-Konnektivität.  <br/> |Ja  <br/> |Ja  <br/> |

Erweitern Sie die folgenden Titel, um weitere Anleitungen zur Netzwerkplanung zu erhalten. Außerdem haben wir eine zehngeteilte [Azure ExpressRoute für Office 365-Schulungsreihe](https://channel9.msdn.com/series/aer) aufgezeichnet, die tiefer geht.

## <a name="existing-azure-expressroute-customers"></a>Vorhandene Azure ExpressRoute-Kunden

Wenn Sie eine vorhandene Azure ExpressRoute-Schaltung verwenden und Office 365-Konnektivität über diese Schaltung hinzufügen möchten, sollten Sie sich die Anzahl der Schaltungen, Ausgangsstandorte und die Größe der Schaltungen anschauen, um sicherzustellen, dass sie die Anforderungen Ihrer Office 365-Nutzung erfüllen. Die meisten Kunden benötigen zusätzliche Bandbreite und viele zusätzliche Schaltungen.
  
Konfigurieren Sie die Routenfilter, um den Zugriff auf Office 365 über Ihre vorhandenen Azure ExpressRoute-Leitungen zu [ermöglichen,](/azure/expressroute/how-to-routefilter-portal) um sicherzustellen, dass auf die Office 365-Dienste zugegriffen werden kann.
  
Das Azure ExpressRoute-Abonnement ist kundenzentriert, d. h. Abonnements sind an Kunden gebunden. Als Kunde können Sie über mehrere Azure ExpressRoute-Schaltungen verfügen und über diese Schaltungen auf viele Microsoft-Cloudressourcen zugreifen. Sie können beispielsweise auf einen von Azure gehosteten virtuellen Computer, einen Office 365-Test-Mandanten und einen Office 365-Produktions-Mandanten über ein Paar redundanter Azure ExpressRoute-Schaltungen zugreifen.
  
In dieser Tabelle sind die beiden Arten von Peeringbeziehungen aufgeführt, die Sie über Ihre Schaltungen implementieren können.

|**Peeringbeziehung**|**Azure Private**|**Microsoft**|
|:-----|:-----|:-----|
|**Dienste** <br/> |IaaS: Virtuelle Azure-Computer  <br/> |PaaS: Öffentliche Azure-Dienste  <br/> SaaS: Office 365  <br/> SaaS: Dynamics 365  <br/> |
|Verbindungsinitiierung**** <br/> |Customer-to-Microsoft  <br/> Microsoft-to-Customer  <br/> |Customer-to-Microsoft  <br/> Microsoft-to-Customer  <br/> |
|**QoS-Unterstützung** <br/> |Keine QoS  <br/> |QoS<sup>1</sup> <br/> |

<sup>1 </sup> QoS unterstützt Derzeit nur Skype for Business.
  
## <a name="bandwidth-planning-for-azure-expressroute"></a>Bandbreitenplanung für Azure ExpressRoute

Jeder Office 365-Kunde hat eindeutige Bandbreitenanforderungen, abhängig von der Anzahl der Personen an jedem Standort, der Aktiven bei jeder Office 365-Anwendung und anderen Faktoren, z. B. der Verwendung von lokalen oder Hybridgeräten und Netzwerksicherheitskonfigurationen.
  
Zu wenig Bandbreite führt zu Überlastung, erneuten Übertragungen von Daten und unvorhersehbaren Verzögerungen. Zu viel Bandbreite führt zu unnötigen Kosten. In einem vorhandenen Netzwerk wird die Bandbreite häufig als Prozentsatz der verfügbaren Kopffreiheit auf der Leitung bezeichnet. Eine Kopffreiheit von 10 % führt wahrscheinlich zu Überlastung und 80 % Kopffreiheit bedeutet in der Regel unnötige Kosten. Typische Kopfraumzielzuordnungen liegen zwischen 20 % und 50 %.
  
Um die richtige Bandbreite zu finden, testen Sie am besten Ihren vorhandenen Netzwerkverbrauch. Dies ist die einzige Möglichkeit, um ein echtes Maß an Nutzung und Bedarf zu erhalten, da alle Netzwerkkonfigurationen und Anwendungen in mancher Hinsicht eindeutig sind. Bei der Messung sollten Sie den Gesamtbandbreitenverbrauch, die Latenz und die TCP-Überlastung genau beachten, um Ihre Netzwerkanforderungen zu verstehen.
  
Nachdem Sie über einen geschätzten Basisplan verfügen, der alle Netzwerkanwendungen umfasst, piloten Sie Office 365 mit einer kleinen Gruppe, die die verschiedenen Profile von Personen in Ihrer Organisation umfasst, um die tatsächliche Nutzung zu ermitteln, und verwenden Sie die beiden Messungen, um die Bandbreite zu schätzen, die Sie für jeden Bürostandort benötigen. Wenn in Ihren Tests Latenz- oder TCP-Überlastungsprobleme auftreten, müssen Sie den Ausgangsvorgang möglicherweise näher an die Benutzer mit Office 365 verschieben oder intensive Netzwerkprüfungen wie z. B. DIE SSL-Entschlüsselung/-überprüfung entfernen.
  
Alle unsere Empfehlungen zur empfohlenen Art der Netzwerkverarbeitung gelten sowohl für ExpressRoute als auch für Internetschaltungen. Dies gilt auch für die restlichen Anleitungen auf unserer [Website für leistungsoptimierung.](./network-planning-and-performance.md)
  
## <a name="applying-security-controls-to-azure-expressroute-for-office-365-scenarios"></a>Anwenden von Sicherheitssteuerelementen auf Azure ExpressRoute für Office 365-Szenarien

Das Sichern der Azure ExpressRoute-Konnektivität beginnt mit den gleichen Prinzipien wie das Sichern der Internetverbindung. Viele Kunden entscheiden sich für die Bereitstellung von Netzwerk- und Umkreissteuerelementen entlang des ExpressRoute-Pfads, der ihr lokales Netzwerk mit Office 365 und anderen Microsoft Clouds verbindet. Diese Steuerelemente können Firewalls, Anwendungsproxies, Verhinderung von Datenlecks, Angriffserkennung, Systeme zur Verhinderung von Angriffen und so weiter umfassen. In vielen Fällen wenden Kunden unterschiedliche Steuerungsebenen auf Datenverkehr an, der von lokalen Verbindungen zu Microsoft initiiert wird, im Vergleich zu Datenverkehr, der von Microsoft an das lokale Kundennetzwerk initiiert wird, im Vergleich zu Datenverkehr, der von einem lokalen Datenverkehr an ein allgemeines Internetziel initiiert wird.
  
Im Folgenden finden Sie einige Beispiele für die Integration der Sicherheit in das [ExpressRoute-Konnektivitätsmodell,](/azure/expressroute/expressroute-connectivity-models) das Sie bereitstellen möchten.

|**ExpressRoute-Integrationsoption**|**Netzwerksicherheitsperimetermodell**|
|:-----|:-----|
|Co-Location bei einem Cloud Exchange  <br/> |Installieren Sie neue oder nutzen Sie die vorhandene Sicherheits-/Umkreisinfrastruktur in der Co-Location-Einrichtung, in der die ExpressRoute-Verbindung hergestellt wird.  <br/> Nutzen Sie die Einrichtung für den gemeinsamen Standort nur für Routing-/Verbindungszwecke und back-haul-Verbindungen von der Co-Location-Einrichtung in die lokale Sicherheits-/Umkreisinfrastruktur.  <br/> |
|Point-to-Point Ethernet  <br/> |Beenden Sie die Point-to-Point-ExpressRoute-Verbindung am vorhandenen lokalen Sicherheits-/Umkreisinfrastrukturspeicherort.  <br/> Installieren Sie eine neue Sicherheits-/Umkreisinfrastruktur speziell für den ExpressRoute-Pfad, und beenden Sie die Point-to-Point-Verbindung dort.  <br/> |
|Any-to-Any IPVPN  <br/> |Nutzen Sie eine vorhandene lokale Sicherheits-/Umkreisinfrastruktur an allen Standorten, die in den ipVPN überleiten, der für die ExpressRoute für Office 365-Konnektivität verwendet wird.  <br/> Den ipVPN, der für ExpressRoute für Office 365 verwendet wird, an bestimmte lokale Standorte, die als Sicherheits-/Umkreisdienst dienen sollen, abfingen.  <br/> |

Einige Dienstanbieter bieten auch verwaltete Sicherheits-/Umkreisfunktionen als Teil ihrer Integrationslösungen mit Azure ExpressRoute.
  
Wenn Sie die Topologieplatzierung der Netzwerk-/Sicherheitsperimeteroptionen berücksichtigen, die für ExpressRoute für Office 365-Verbindungen verwendet werden, werden die folgenden zusätzlichen Überlegungen berücksichtigt:
  
- Die Tiefen- und Typnetzwerk-/Sicherheitssteuerelemente können sich auf die Leistung und Skalierbarkeit der Office 365-Benutzeroberfläche auswirken.

- Ausgehende (lokale - Microsoft) und eingehende \> (Microsoft- lokale) Flüsse [sofern aktiviert] haben möglicherweise \> unterschiedliche Anforderungen. Diese unterscheiden sich wahrscheinlich von ausgehenden zu allgemeinen Internetzielen.

- Office 365-Anforderungen für Ports/Protokolle und erforderliche IP-Subnetze sind identisch, unabhängig davon, ob Datenverkehr über ExpressRoute für Office 365 oder über das Internet geroutet wird.

- Die topologische Platzierung der Kundennetzwerk-/Sicherheitssteuerelemente bestimmt das end-to-end-Netzwerk zwischen dem Benutzer und dem Office 365-Dienst und kann erhebliche Auswirkungen auf die Netzwerklatenz und -überlastung haben.

- Kunden werden aufgefordert, ihre Sicherheits-/Umkreistopologie für die Verwendung mit ExpressRoute für Office 365 in Übereinstimmung mit bewährten Methoden für Redundanz, hohe Verfügbarkeit und Notfallwiederherstellung zu entwerfen.

Im Folgenden finden Sie ein Beispiel für die Woodgrove Bank, die die verschiedenen Azure ExpressRoute-Konnektivitätsoptionen mit den oben erläuterten Umkreissicherheitsmodellen vergleicht.
  
### <a name="example-1-securing-azure-expressroute"></a>Beispiel 1: Schützen von Azure ExpressRoute
  
Die Woodgrove Bank erwägt die Implementierung von Azure ExpressRoute, und nach der Planung der optimalen Architektur für Routing mit [ExpressRoute für Office 365](routing-with-expressroute.md) und nach der Verwendung der obigen Anleitung zum Verständnis der Bandbreitenanforderungen bestimmen sie die beste Methode zum Schützen ihres Umkreises.
  
Für Woodgrove, eine multinationale Organisation mit Standorten auf mehreren Kontinenten, muss die Sicherheit alle Umkreise umfassen. Die optimale Konnektivitätsoption für Woodgrove ist eine Mehrpunktverbindung mit mehreren Peeringstandorten auf der ganzen Welt, um die Anforderungen ihrer Mitarbeiter auf jedem Kontinent zu erfüllen. Jeder Kontinent umfasst redundante Azure ExpressRoute-Schaltungen innerhalb des Kontinents, und die Sicherheit muss sich über alle diese Leitungen erstreckt.
  
Die vorhandene Infrastruktur von Woodgrove ist zuverlässig und kann die zusätzlichen Arbeiten verarbeiten, was dazu führt, dass die Woodgrove Bank die Infrastruktur für ihre Azure ExpressRoute- und Internetperimetersicherheit verwenden kann. Wenn dies nicht der Fall wäre, könnte Woodgrove zusätzliche Geräte kaufen, um die vorhandenen Geräte zu ergänzen oder einen anderen Verbindungstyp zu verarbeiten.
  
## <a name="high-availability-and-failover-with-azure-expressroute"></a>Hohe Verfügbarkeit und Failover mit Azure ExpressRoute
<a name="BKMK_high-availability"> </a>

Es wird empfohlen, mindestens zwei aktive Schaltungen von jedem Abgang mit ExpressRoute an Ihren ExpressRoute-Anbieter zu stellen. Dies ist der häufigste Ort, an dem Ausfälle für Kunden zu sehen sind, und Sie können dies problemlos vermeiden, indem Sie ein Paar aktiver/aktiver ExpressRoute-Schaltungen bereitstellen. Wir empfehlen außerdem mindestens zwei aktive/aktive Internetschaltungen, da viele Office 365-Dienste nur über das Internet verfügbar sind.
  
Innerhalb des Ausgangspunkts Ihres Netzwerks befinden sich viele andere Geräte und Schaltungen, die eine wichtige Rolle bei der Wahrnehmung der Verfügbarkeit von Personen spielen. Diese Teile Ihrer Konnektivitätsszenarien werden nicht von ExpressRoute- oder Office 365-SLAs abgedeckt, spielen aber eine wichtige Rolle bei der End-to-End-Dienstverfügbarkeit, wie sie von Personen in Ihrer Organisation wahrgenommen werden.
  
Konzentrieren Sie sich auf die Personen, die Office 365 verwenden und verwenden, und suchen Sie nach Möglichkeiten, um den Gesamtprozentsatz der betroffenen Personen zu begrenzen, wenn sich ein Ausfall einer Komponente auf die Erfahrung der Bevölkerung auswirken würde. Wenn ein Failovermodus operativ komplex ist, sollten Sie die Erfahrung der Bevölkerung von langer Zeit für die Wiederherstellung berücksichtigen und nach betriebsbereiten einfachen und automatisierten Failovermodi suchen.
  
Außerhalb Ihres Netzwerks verfügen Office 365, ExpressRoute und Ihr ExpressRoute-Anbieter über unterschiedliche Verfügbarkeitsebenen.
  
### <a name="service-availability"></a>Service Availability
  
- Office 365-Dienste werden durch gut definierte Vereinbarungen zum [Servicelevel](/office365/servicedescriptions/office-365-platform-service-description/service-level-agreement)abgedeckt, die Verfügbarkeits- und Verfügbarkeitsmetriken für einzelne Dienste enthalten. Ein Grund dafür, dass Office 365 so hohe Dienstverfügbarkeitsstufen beibehalten kann, ist die Möglichkeit für einzelne Komponenten, ein nahtloses Failover zwischen den vielen Microsoft-Rechenzentren mithilfe des globalen Microsoft-Netzwerks auszuführen. Dieses Failover erstreckt sich vom Datencenter und Netzwerk bis zu mehreren Internet-Ausgangspunkten und ermöglicht ein nahtloses Failover aus der Sicht der Personen, die den Dienst verwenden.

- ExpressRoute [bietet eine Verfügbarkeits-SLA von 99,9 %](https://azure.microsoft.com/support/legal/sla/expressroute/v1_0/) für einzelne dedizierte Schaltungen zwischen dem Microsoft Network Edge und der ExpressRoute-Anbieter- oder Partnerinfrastruktur. Diese [Servicelevels](/azure/expressroute/expressroute-introduction) werden auf Der ExpressRoute-Leitungsebene angewendet, die aus zwei unabhängigen Verbindungen zwischen dem redundanten Microsoft-Gerät und der Netzwerkanbieterausrüstung an jedem Peeringstandort besteht.

### <a name="provider-availability"></a>Anbieterverfügbarkeit
  
- Die Vereinbarungen zum Servicelevel von Microsoft werden bei Ihrem ExpressRoute-Anbieter oder -Partner beendet. Dies ist auch der erste Ort, an dem Sie Entscheidungen treffen können, die Ihren Verfügbarkeitsgrad beeinflussen. Sie sollten die Architektur,Verfügbarkeit und Ausfallsicherheitsmerkmale, die Ihr ExpressRoute-Anbieter zwischen Ihrem Netzwerkperimeter und Ihrer Anbieterverbindung an jedem Microsoft-Peeringstandort bietet, genau auswerten. Achten Sie sowohl auf die logischen als auch physischen Aspekte von Redundanz, Peeringgeräten, vom Netzbetreiber bereitgestellten WAN-Schaltungen und zusätzlichen Mehrwertdiensten wie NAT-Diensten oder verwalteten Firewalls.

### <a name="designing-your-availability-plan"></a>Entwerfen Ihres Verfügbarkeitsplans
  
Es wird dringend empfohlen, hohe Verfügbarkeit und Ausfallsicherheit in Ihren End-to-End-Konnektivitätsszenarien für Office 365 zu planen und zu entwerfen. Ein Entwurf sollte folgendes enthalten:
  
- keine einzelnen Fehlerpunkte, einschließlich Internet- und ExpressRoute-Schaltungen.

- Minimierung der Anzahl betroffener Personen und Dauer dieser Auswirkungen für die meisten erwarteten Fehlermodi.

- Optimierung für einen einfachen, wiederholbaren und automatischen Wiederherstellungsprozess aus den meisten erwarteten Fehlermodi.

- Unterstützung der vollständigen Anforderungen ihres Netzwerkdatenverkehrs und ihrer Funktionalität über redundante Pfade ohne erhebliche Beeinträchtigung.

Ihre Konnektivitätsszenarien sollten eine Netzwerktopologie enthalten, die für mehrere unabhängige und aktive Netzwerkpfade zu Office 365 optimiert ist. Dadurch erhalten Sie eine bessere End-to-End-Verfügbarkeit als eine Topologie, die nur für Redundanz auf Geräte- oder Geräteebene optimiert ist.
  
> [!TIP]
> Wenn Ihre Benutzer auf mehrere Kontinente oder geografische Regionen verteilt sind und jeder dieser Standorte über redundante WAN-Schaltungen eine Verbindung mit einem einzigen lokalen Standort herstellt, an dem sich eine einzelne ExpressRoute-Schaltung befindet, wird den Benutzern weniger End-to-End-Dienstverfügbarkeit zur Verfügung stehen als bei einem Netzwerktopologieentwurf, der unabhängige ExpressRoute-Schaltungen enthält, die die verschiedenen Regionen mit dem nächstgelegenen Peeringstandort verbinden.
  
Es wird empfohlen, mindestens zwei ExpressRoute-Schaltungen mit jeder Verbindung mit einem anderen geografischen Peeringstandort zu stellen. Sie sollten dieses aktiv-aktive Leitungspaar für jede Region bereitstellen, in der Personen die ExpressRoute-Konnektivität für Office 365-Dienste verwenden. Dadurch kann jede Region während eines Notfalls verbunden bleiben, der sich auf einen wichtigen Standort wie ein Rechenzentrum oder einen Peeringspeicherort auswirkt. Wenn Sie sie als aktiv/aktiv konfigurieren, kann der Datenverkehr des Endbenutzers über mehrere Netzwerkpfade verteilt werden. Dadurch wird der Umfang der Personen reduziert, die während Geräte- oder Netzwerkgeräteausfällen betroffen sind.
  
Es wird nicht empfohlen, eine einzelne ExpressRoute-Schaltung mit dem Internet als Sicherung zu verwenden.
  
### <a name="example-2-failover-and-high-availability"></a>Beispiel 2: Failover und Hohe Verfügbarkeit
  
Das multi-geografische Design der Woodgrove Bank wurde einer Überprüfung von Routing, Bandbreite, Sicherheit unterzogen und muss nun einer Überprüfung der hohen Verfügbarkeit unterzogen werden. Woodgrove geht davon aus, dass hohe Verfügbarkeit drei Kategorien abdecken soll. Ausfallsicherheit, Zuverlässigkeit und Redundanz.
  
Die Ausfallsicherheit ermöglicht Woodgrove die schnelle Wiederherstellung nach Fehlern. Zuverlässigkeit ermöglicht Woodgrove ein konsistentes Ergebnis innerhalb des Systems. Redundanz ermöglicht Woodgrove das Verschieben zwischen einer oder mehreren gespiegelten Infrastrukturinstanzen.
  
In jeder Edgekonfiguration verfügt Woodgrove über redundante Firewalls, Proxys und IDS. Für Nordamerika verfügt Woodgrove über eine Edgekonfiguration im Datencenter von Dallas und eine weitere Edgekonfiguration im Rechenzentrum von Virginia. Die redundanten Geräte an jedem Standort bieten Ausfallsicherheit gegenüber diesem Standort.
  
Die Netzwerkkonfiguration bei der Woodgrove Bank basiert auf einigen wichtigen Prinzipien:
  
- Innerhalb jeder geografischen Region gibt es mehrere Azure ExpressRoute-Schaltungen.

- Jeder Stromkreis innerhalb einer Region kann den ganzen Netzwerkdatenverkehr innerhalb dieser Region unterstützen.

- Das Routing bevorzugt den einen oder anderen Pfad je nach Verfügbarkeit, Standort und so weiter.

- Failover zwischen Azure ExpressRoute-Schaltungen erfolgt automatisch ohne zusätzliche Konfiguration oder Aktion, die von Woodgrove erforderlich ist.

- Failover zwischen Internetschaltungen erfolgt automatisch ohne zusätzliche Konfiguration oder Aktion, die von Woodgrove erforderlich ist.

In dieser Konfiguration ist die Woodgrove Bank mit Redundanz auf physischer und virtueller Ebene in der Lage, lokale Ausfallsicherheit, regionale Ausfallsicherheit und globale Ausfallsicherheit zuverlässig zu bieten. Woodgrove wählte diese Konfiguration nach der Auswertung einer einzelnen Azure ExpressRoute-Schaltung pro Region sowie nach der Möglichkeit eines Fehlers im Internet.
  
Wenn Woodgrove nicht über mehrere Azure ExpressRoute-Schaltungen pro Region verfügen konnte, würde das Routing von Datenverkehr, der aus Nordamerika an die Azure ExpressRoute-Schaltung im Asiatisch-Pazifischen Raum führt, eine inakzeptable Latenzstufe hinzufügen, und die erforderliche DNS-Forwarderkonfiguration erhöht die Komplexität.
  
Es wird nicht empfohlen, das Internet als Sicherungskonfiguration zu nutzen. Dadurch wird das Zuverlässigkeitsprinzip von Woodgrove bricht, was zu einer inkonsistenten Verwendung der Verbindung führt. Darüber hinaus wäre eine manuelle Konfiguration erforderlich, um ein Failover unter Berücksichtigung der konfigurierten BGP-Ankündigungen, der NAT-Konfiguration, der DNS-Konfiguration und der Proxykonfiguration auszuführen. Dadurch wird die Failoverkomplexität erhöht, die Wiederherstellungszeit erhöht und die Fähigkeit zur Diagnose und Problembehandlung der betroffenen Schritte verringert.
  
Haben Sie noch Fragen zum Planen und Implementieren der Datenverkehrsverwaltung oder Azure ExpressRoute? Lesen Sie die restlichen [Netzwerk- und Leistungsleitfäden](./network-planning-and-performance.md) oder die Häufig gestellten Fragen zu [Azure ExpressRoute](/azure/expressroute/expressroute-faqs).
  
## <a name="working-with-azure-expressroute-providers"></a>Arbeiten mit Azure ExpressRoute-Anbietern
<a name="BKMK_high-availability"> </a>

Wählen Sie die Speicherorte Ihrer Schaltungen basierend auf Ihrer Bandbreite, Latenz, Sicherheit und Hochverfügbarkeitsplanung aus. Sobald Sie die optimalen Standorte kennen, die Sie Schaltungen platzieren möchten, überprüfen Sie die aktuelle Liste der [Anbieter nach Region.](/azure/expressroute/expressroute-locations)
  
Arbeiten Sie mit Ihrem Anbieter oder Ihren Anbietern zusammen, um die besten Konnektivitätsoptionen, Punkt-zu-Punkt-, Mehrpunkt- oder gehostete Optionen auszuwählen. Denken Sie daran, dass Sie die Konnektivitätsoptionen so lange kombinieren und übereinstimmen können, wie die Bandbreite und andere redundante Komponenten Ihr Routing- und Hochverfügbarkeitsdesign unterstützen.
  
Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/planningexpressroute365]()
  
## <a name="related-topics"></a>Verwandte Themen
<a name="BKMK_high-availability"> </a>

[Bewerten der Office 365-Netzwerkkonnektivität](assessing-network-connectivity.md)
  
[Azure ExpressRoute für Office 365](azure-expressroute.md)
  
[Verwalten von ExpressRoute für Office 365-Verbindungen](managing-expressroute-for-connectivity.md)
  
[Routing mit ExpressRoute für Office 365](routing-with-expressroute.md)
  
[Implementierung von ExpressRoute für Office 365](implementing-expressroute.md)
  
[Verwenden von BGP-Communitys in ExpressRoute für Office 365-Szenarien](bgp-communities-in-expressroute.md)
  
[Medienqualität und Netzwerkverbindungsleistung in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimieren Ihres Netzwerks für Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute und QoS in Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Anruffluss mit ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](performance-tuning-using-baselines-and-history.md)
  
[Plan zur Problembehandlung für Office 365](performance-troubleshooting-plan.md)
  
[URLs und IP-Adressbereiche für Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365-Netzwerk- und Leistungsoptimierung](network-planning-and-performance.md)
  
[Häufig gestellte Fragen zu Office 365-Endpunkten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)