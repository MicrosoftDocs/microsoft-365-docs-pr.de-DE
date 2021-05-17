---
title: Verwenden von BGP-Communitys in ExpressRoute für Office 365 Szenarien
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 6/26/2018
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099
description: Erfahren Sie, wie Sie mithilfe von BGP-Communitys in Azure ExpressRoute die Anzahl der IP-Präfixe und die erforderliche Bandbreite für Office 365 verwalten.
ms.openlocfilehash: 9cb6980c1d8cc120f99cac087602856aeacf1adf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905212"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Verwenden von BGP-Communitys in ExpressRoute für Office 365 Szenarien

Die Verbindung mit Office 365 Azure ExpressRoute basiert auf BGP-Ankündigungen bestimmter IP-Subnetze, die Netzwerke darstellen, Office 365 Endpunkte bereitgestellt werden. Aufgrund der globalen Art der Office 365 und der Anzahl von Diensten, die Office 365 bilden, müssen Kunden häufig die Anzeigen verwalten, die sie in ihrem Netzwerk annehmen. Verringern der Anzahl von #A0 Als IP-Präfixe im restlichen Teil dieses Artikels bezeichnet, um sich an die BGP-Netzwerkverwaltungsterminologie auszurichten, werden die folgenden Endziele für Kunden erfüllt:
  
-  Verwalten der Anzahl der angekündigten IP-Präfixe akzeptiert – Kunden, die über eine interne Netzwerkinfrastruktur oder einen Netzwerkanbieter verfügen, der nur eine begrenzte Anzahl von IP-Präfixen unterstützt, und Kunden, die über einen Netzwerkanbieter verfügen, der für die Annahme von Präfixen über einer begrenzten Anzahl gebührent, möchten die Gesamtzahl der bereits für ihr Netzwerk angekündigten Präfixe auswerten und auswählen, welche Office 365-Anwendungen für ExpressRoute am besten geeignet sind.

- Verwalten der für die **Azure ExpressRoute-Schaltung** erforderlichen Bandbreite – Kunden möchten möglicherweise den Bandbreitenumschlag der Office 365-Dienste über den ExpressRoute-Pfad im Vergleich zum Internetpfad steuern. Auf diese Weise können Kunden die ExpressRoute-Bandbreite für bestimmte Anwendungen wie Skype for Business reservieren und die verbleibenden Office 365 über den Internetpfad routen.

Um Kunden bei diesen Zielen zu unterstützen, werden Office 365-IP-Präfixe, die über ExpressRoute angekündigt werden, mit dienstspezifischen BGP-Communitywerten markiert, wie im folgenden Beispiel gezeigt.
  
> [!NOTE]
> Sie sollten erwarten, dass ein Teil des Netzwerkdatenverkehrs, der anderen Anwendungen zugeordnet ist, in den Communitywert einbezogen wird. Dies ist das erwartete Verhalten für ein globales Software as a Service-Angebot mit gemeinsam genutzten Diensten und Rechenzentren. Dies wurde nach Möglichkeit mit den beiden oben genannten Zielen minimiert, wobei die Anzahl von Präfixen und/oder die Bandbreite verwaltet werden.

|**Dienst**|**BGP Community Value**|**Notizen**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Umfasst Exchange- und EOP-Dienste\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype for Business\*  <br/> |12076:5030  <br/> |Skype for Business Online& Microsoft Teams dienste  <br/> |
|Andere Office 365 Dienste\*  <br/> |12076:5100  <br/> |Umfasst Azure Active Directory (Authentifizierungs- und Verzeichnissynchronisierungsszenarien) sowie Office 365 Portaldienste  <br/> |
|\*Der Umfang von Dienstszenarien, die in ExpressRoute enthalten sind, ist im Artikel [Office 365-Endpunkte](./urls-and-ip-address-ranges.md) dokumentiert.  <br/> \*\*Weitere Dienste und BGP-Communitywerte können in Zukunft hinzugefügt werden. [Sehen Sie sich die aktuelle Liste der BGP-Communities an.](/azure/expressroute/expressroute-routing)  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>Was sind die am häufigsten verwendeten Szenarien für die Verwendung von BGP-Communities?

Kunden können BGP-Communitys verwenden, um Gruppen von IP-Präfixen zu regeln, die von ihrem Netzwerk über Azure ExpressRoute akzeptiert werden, und dadurch die Gesamtzahl der IP-Präfixe und den erwarteten Bandbreitenumschlag bestimmter Office 365 beeinflussen. Es ist wichtig zu wissen, dass alle Office 365 internetgebundenen Datenverkehr benötigen, unabhängig von der Verwendung von Azure ExpressRoute- oder BGP-Communities. Die folgenden drei Szenarien sind die am häufigsten verwendeten Funktionen.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Szenario 1: Minimieren der Anzahl Office 365 IP-Präfixe

Contoso Corporation ist ein 50.000-Personen-Unternehmen, das derzeit Office 365 für Exchange Online und SharePoint Online verwendet. Bei der Überprüfung der ExpressRoute-Anforderungen bestimmt Contoso, dass seine Netzwerkgeräte an vielen regionalen Standorten Routingtabellesgrößen über 100 zusätzliche Routeneinträge nicht verarbeiten können. Contoso hat die Gesamtzahl der IP-Präfixe überprüft, die ExpressRoute für den vollständigen Satz von Office 365-Diensten ankündigen würde, und kam zu dem Schluss, dass es 100 überschreitet. Um unter den 100 zusätzlichen Routeneinträgen zu bleiben, begrenzt Contoso die Verwendung von ExpressRoute für Office 365 auf nur den SharePoint Online BGP-Communitywert 12076:5020, der über das ExpressRoute Microsoft-Peering empfangen wurde.

|**Verwendetes BGP-Communitytag**|**Über Azure ExpressRoute umleitende Funktionalität**|**Internetrouten erforderlich**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint &amp;Online OneDrive for Business  <br/> | DNS-, CRL-, &amp; CDN Anforderungen  <br/>  Alle anderen Office 365, die nicht speziell über Azure ExpressRoute unterstützt werden  <br/>  Alle anderen Microsoft Cloud Services  <br/>  Office 365 Portal, Office 365 &amp; Authentifizierung, Office in einem Browser  <br/>  Exchange Online, Exchange Online Protection und Skype for Business Online  <br/> |

> [!NOTE]
> Um eine niedrigere Präfixanzahl für jeden Dienst zu erzielen, bleibt eine minimale Überlappung zwischen Diensten erhalten. Dieses Verhalten ist normal und beabsichtigt.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Szenario 2: Scoping ExpressRoute und interne Bandbreitennutzung für einige Office 365 Dienste

Fabrikam Inc, ein großes multinationales Unternehmen mit einem verteilten heterogenen Netzwerk, ist ein Abonnent vieler Office 365 einschließlich; Exchange Online, SharePoint Online und Skype for Business Online. Die interne Routinginfrastruktur von Fabrikam kann Tausende von #A0 in ihren Routingtabellen verarbeiten. Fabrikam möchte jedoch nur ExpressRoute und interne Bandbreite für Office 365-Anwendungen bereitstellen, die für die Netzwerkleistung am sensibelsten sind und ihre vorhandene Internetbandbreite für alle anderen Office 365 verwenden.
  
Aus diesem Grund begrenzt Fabrikam seine Azure ExpressRoute-Bandbreite auf nur Skype for Business Online BGP Community-Wert, 12076:5030, der über das ExpressRoute Microsoft-Peering empfangen wurde. Der verbleibende Netzwerkdatenverkehr, der mit Office 365 verknüpft ist, verwendet weiterhin die Internet-Ausgangspunkte.

|**Verwendetes BGP-Communitytag**|**Über Azure ExpressRoute umleitende Funktionalität**|**Internetrouten erforderlich**|
|:-----|:-----|:-----|
|Skype for Business  <br/> (12076:5030)  <br/> |Skype SIP-Signalisierung, Downloads, Sprach-, Video- und Desktopfreigabe  <br/> | DNS-, CRL-, &amp; CDN Anforderungen  <br/>  Alle anderen Office 365, die nicht speziell über Azure ExpressRoute unterstützt werden  <br/>  Alle anderen Microsoft Cloud Services  <br/>  Office 365 Portal, Office 365 &amp; Authentifizierung, Office in einem Browser  <br/>  Skype for Business Telemetrie, Skype-Client-Schnelltipps, Verbindungen mit öffentlichen Öffentlichen Konnektivität  <br/>  Exchange Online, Exchange Online Protection und SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Szenario 3: Scoping Azure ExpressRoute nur für Office 365 Dienste

Die Woodgrove Bank ist Ein Kunde mehrerer Microsoft-Clouddienste, einschließlich Office 365. Nach der Auswertung ihrer Netzwerkkapazität und -nutzung beschließt die Woodgrove Bank, Azure ExpressRoute als bevorzugten Pfad für die unterstützten Office 365 bereitstellen. Die Routingtabellen können den vollständigen Satz von Office 365-IP-Präfixen unterstützen, und die bereitgestellten Azure ExpressRoute-Schaltungen unterstützen alle projizierten Bandbreiten- und Latenzanforderungen.
  
Um sicherzustellen, dass der Netzwerkdatenverkehr, der anderen Microsoft-Clouddiensten als Office 365 zugeordnet ist, verwendet die Woodgrove Bank ExpressRoute für Office 365 für alle IP-Präfixe, die mit Office 365 bestimmten BGP-Communitywerten markiert sind, 12076:5010, 12076:5020, 12076:5030, 12076:5100.

|**Verwendetes BGP-Communitytag**|**Über Azure ExpressRoute umleitende Funktionalität**|**Internetrouten erforderlich**|
|:-----|:-----|:-----|
|Exchange, Skype for Business & Microsoft Teams, SharePoint, &amp; andere Dienste  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |&amp;Exchange Online Exchange Online Protection  <br/> SharePoint &amp;Online OneDrive for Business  <br/> Skype SIP-Signalisierung, Downloads, Sprach-, Video- und Desktopfreigabe  <br/> Office 365 Portal, Office 365 &amp; Authentifizierung, Office in einem Browser  <br/> | DNS-, CRL-, &amp; CDN Anforderungen  <br/>  Alle anderen Office 365, die nicht speziell über Azure ExpressRoute unterstützt werden  <br/>  Alle anderen Microsoft Cloud Services  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Wichtige Planungsüberlegungen für die Verwendung von BGP-Communitys

Kunden, die die Vorteile von BGP-Communitys nutzen, um zu beeinflussen, wie ExpressRoute über das Kundennetzwerk angekündigt und verbreitet wird, sollten die folgenden Überlegungen berücksichtigen:
  
- Bei der Verwendung von BGP-Communitys in Ihrem Netzwerkentwurf ist es wichtig, sicherzustellen, dass die Routensymmetrie weiterhin erhalten bleibt. In einigen Fällen kann das Hinzu- oder Entfernen von BGP-Communitys zu einer Situation kommen, in der das symmetrische Routing unterbrochen ist und Ihre Routingkonfiguration aktualisiert werden muss, um ein symmetrisches Routing wie möglich zu erstellen.

- Das Tauschen von Azure ExpressRoute mit BGP-Communitywerten ist eine Kundenaktion. Microsoft wirbt für alle IP-Präfixe, die der Peeringbeziehung zugeordnet sind, unabhängig von den vom Kunden konfigurierten Scopings.

- Azure ExpressRoute unterstützt keine Aktionen im Netzwerk von Microsoft, die auf kundenbezogenen BGP-Communitys basieren.

- Die von der Office 365 verwendeten IP-Präfixe werden nur mit dienstspezifischen BGP-Communitywerten gekennzeichnet, standortspezifische BGP-Communitys werden nicht unterstützt. Office 365 Dienste globaler Natur sind, werden Filterpräfixe basierend auf dem Speicherort des Mandanten oder der Daten innerhalb der Office 365 nicht unterstützt. Der empfohlene Ansatz besteht in der Konfiguration Ihres Netzwerks, um den kürzesten oder bevorzugten Netzwerkpfad vom Netzwerkstandort des Benutzers in das globale Microsoft-Netzwerk zu koordinieren, unabhängig vom physischen Standort der IP-Adresse des Office 365-Diensts, den er anfordert.

- Die in jedem BGP-Communitywert enthaltenen IP-Präfixe stellen ein Subnetz dar, das IP-Adressen für die Office 365 dem Wert zugeordneten Anwendung enthält. In einigen Fällen verfügt mehr als eine Office 365-Anwendung über IP-Adressen innerhalb eines Subnetzes, was zu einem IP-Präfix führt, das in mehr als einem Communitywert vorhanden ist. Dieses Verhalten wird aufgrund der Zuweisungsfragmentierung erwartet, wenn auch selten, und wirkt sich nicht auf die Präfixanzahl oder die Bandbreitenverwaltungsziele aus. Kunden werden ermutigt, den Ansatz "Was erforderlich ist zulassen" zu verwenden, statt "was nicht benötigt wird" zu verweigern, wenn sie BGP-Communitys für Office 365 nutzen, um den Effekt zu minimieren.

- Die Verwendung von BGP-Communitys ändert nicht die zugrunde liegenden Netzwerkkonnektivitätsanforderungen oder -konfigurationen, die für die Verwendung von Office 365. Kunden, die auf Office 365 zugreifen möchten, müssen weiterhin auf das Internet zugreifen können.

- Die Verwendung von Azure ExpressRoute mit BGP-Communitys wirkt sich nur auf die Routen aus, die Ihr internes Netzwerk über die Microsoft-Peeringbeziehung sehen kann. Möglicherweise müssen Sie zusätzliche Konfigurationen auf Anwendungsebene wie die Verwendung einer PAC- oder WPAD-Konfiguration in Verbindung mit dem Bereichsrouting erstellen.

- Zusätzlich zur Verwendung der von Microsoft zugewiesenen BGP-Communitys können Kunden ihre eigenen BGP-Communitys Office 365 ip-Präfixen zuweisen, die über Azure ExpressRoute gelernt wurden, um das interne Routing zu beeinflussen. Ein beliebter Verwendungsfall ist das Zuweisen einer standortbasierten BGP-Community zu allen Routen, die über jeden angegebenen ExpressRoute-Peeringstandort gelernt wurden, und diese Informationen dann im Kundennetzwerk weiter unten zu verwenden, um den kürzesten oder bevorzugten Netzwerkpfad in das Netzwerk von Microsoft zu koordinieren. Die Verwendung von vom Kunden zugewiesenen BGP-Communitys mit ExpressRoute für Office 365 liegt außerhalb der Kontrolle oder Sichtbarkeit von Microsoft.

Hier ist ein kurzer Link, den Sie verwenden können, um zurück zu kommen: [https://aka.ms/bgpexpressroute365]() .
  
## <a name="related-topics"></a>Verwandte Themen

[Bewerten der Office 365-Netzwerkkonnektivität](assessing-network-connectivity.md)
  
[Azure ExpressRoute für Office 365](azure-expressroute.md)
  
[Verwalten von ExpressRoute für Office 365-Verbindungen](managing-expressroute-for-connectivity.md)
  
[Routing mit ExpressRoute für Office 365](routing-with-expressroute.md)
  
[Netzwerkplanung mit ExpressRoute für Office 365](network-planning-with-expressroute.md)
  
[Medienqualität und Netzwerkverbindungsleistung in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[ExpressRoute und QoS in Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Anruffluss mit ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Implementierung von ExpressRoute für Office 365](implementing-expressroute.md)
  
[Unterstützung für BGP-Communitys](/azure/expressroute/expressroute-routing)
  
[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](performance-tuning-using-baselines-and-history.md)
  
[Plan zur Problembehandlung für Office 365](performance-troubleshooting-plan.md)
  
[Schulung zu Azure ExpressRoute für Office 365](https://channel9.msdn.com/series/aer)