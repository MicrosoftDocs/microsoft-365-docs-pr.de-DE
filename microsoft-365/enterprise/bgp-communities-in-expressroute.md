---
title: Verwenden von BGP-Communities in Express Route für Office 365 Szenarien
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
description: In diesem Artikel erfahren Sie, wie Sie BGP-Communities in Azure Express Route verwenden, um die Anzahl der IP-Präfixe und die erforderliche Bandbreite für Office 365 Szenarien zu verwalten.
ms.openlocfilehash: 3a1de8725ae967352723649e602d944ca6948310
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690733"
---
# <a name="using-bgp-communities-in-expressroute-for-office-365-scenarios"></a>Verwenden von BGP-Communities in Express Route für Office 365 Szenarien

Das Herstellen einer Verbindung mit Office 365 mithilfe von Azure Express Route basiert auf BGP-Ankündigungen bestimmter IP-Subnetze, die Netzwerke darstellen, in denen Office 365 Endpunkte bereitgestellt werden. Aufgrund des globalen Charakters von Office 365 und der Anzahl von Diensten, die Office 365 darstellen, müssen Kunden häufig die Ankündigungen verwalten, die Sie in Ihrem Netzwerk annehmen. Verringern der Anzahl von IP-Subnetzen; bezeichnet als IP-Präfixe im restlichen Teil dieses Artikels, um Sie an die BGP-Netzwerk Verwaltungsterminologie anzupassen, werden die folgenden Endziele für Kunden bereitgestellt:
  
- **Verwalten der Anzahl** der angemeldeten IP-Präfixe – Kunden mit einer internen Netzwerkinfrastruktur oder einem Netzwerk Träger, die nur eine beschränkte Anzahl von IP-Präfixen unterstützen, und Kunden, die über einen Netzwerk Träger verfügen, der für die Annahme von Präfixen oberhalb einer begrenzten Nummer steht, möchten die Gesamtzahl der bereits in Ihrem Netzwerk beworbenen Präfixe auswerten und auswählen, welche Office 365

- **Verwalten der erforderlichen Bandbreite für den Azure Express Route Circuit** -Kunden möchten möglicherweise den Bandbreiten Umschlag der Office 365 Dienste über den Express Route-Pfad vs. Internet Pfad steuern. Auf diese Weise können Kunden Express Route Bandbreite für bestimmte Anwendungen wie Skype for Business reservieren und die restlichen Office 365 Anwendungen über den Internet Pfad weiterleiten.

Um Kunden bei diesen Zielen zu unterstützen, werden Office 365 IP-Präfixe, die über Express Route beworben werden, mit dienstspezifischen BGP-Community-Werten versehen, wie im folgenden Beispiel dargestellt.
  
> [!NOTE]
> Sie sollten davon ausgehen, dass einige mit anderen Anwendungen verknüpfte Netzwerkdatenverkehr in den Community-Wert einbezogen werden. Dies ist das erwartete Verhalten für eine globale Software als Dienstangebot mit gemeinsamen Diensten und Rechenzentren. Dies wurde möglichst mit den beiden oben genannten Zielen minimiert, wobei die Verwaltung der Präfix Anzahl und/oder der Bandbreite berücksichtigt wurde.

|**Dienst**|**BGP Community-Wert**|**Notizen**|
|:-----|:-----|:-----|
|Exchange Online\*  <br/> |12076:5010  <br/> |Umfasst Exchange-und EOP-Dienste\*  <br/> |
|SharePoint Online\*  <br/> |12076:5020  <br/> |SharePoint Online  <br/> |
|Skype for Business\*  <br/> |12076:5030  <br/> |Skype for Business Online & Microsoft Teams-Dienste  <br/> |
|Andere Office 365 Dienste\*  <br/> |12076:5100  <br/> |Umfasst Azure Active Directory (Authentifizierungs-und Verzeichnis Synchronisierungsszenarien) sowie Office 365 Portal Dienste  <br/> |
|\* Der Umfang von Dienst Szenarien, die in Express Route enthalten sind, ist im Artikel [Office 365 Endpunkte](https://aka.ms/o365endpoints) dokumentiert.  <br/> \*\*Zusätzliche Dienste und BGP Community-Werte können in der Zukunft hinzugefügt werden. [Siehe die aktuelle Liste der BGP-Communities](https://azure.microsoft.com/documentation/articles/expressroute-routing/).  <br/> |

## <a name="what-are-the-most-common-scenarios-for-using-bgp-communities"></a>Was sind die am häufigsten verwendeten Szenarien für die Verwendung von BGP-Communities?

Kunden können BGP-Communities verwenden, um Gruppen von IP-Präfixen zu regulieren, die von Ihrem Netzwerk mithilfe von Azure Express Route akzeptiert werden, wodurch sich die Gesamtanzahl der IP-Präfixe und die erwartete Bandbreiten Hülle bestimmter Office 365 Dienste beeinflussen. Es ist wichtig zu verstehen, dass alle Office 365 internetgebundenen Datenverkehr erfordern, unabhängig von der Verwendung von Azure Express Route oder BGP Communities. Die folgenden drei Szenarien sind die am häufigsten verwendeten Funktionen.
  
### <a name="scenario-1-minimizing-the-number-of-office-365-ip-prefixes"></a>Szenario 1: Minimierung der Anzahl von Office 365-IP-Präfixen

Die Contoso Corporation ist ein Unternehmen mit 50.000 Personen, das derzeit Office 365 für Exchange Online und SharePoint Online verwendet. Bei der Überprüfung der Express Route-Anforderungen legt Contoso fest, dass seine Netzwerkgeräte an vielen regionalen Standorten keine Routingtabellen Größen über 100 zusätzliche Routen Einträge verarbeiten können. Contoso hat die Gesamtzahl der IP-Präfixe überprüft, die Express Route für den vollständigen Satz von Office 365 Diensten werben würde, und folgerte, dass er 100 überschreitet. Um unter den 100 zusätzlichen Routen Einträgen zu bleiben, umfasst Contoso die Verwendung von Express Route für Office 365 nur auf den SharePoint Online BGP-communitywert 12076:5020, der über Express Route Microsoft Peering empfangen wurde.

|**BGP-Community-Tag verwendet**|**Routing Fähigkeit über Azure Express Route**|**Erforderliche Internet Routen**|
|:-----|:-----|:-----|
|SharePoint  <br/> (12076:5020)  <br/> |SharePoint Online &amp; OneDrive für Unternehmen  <br/> | DNS-, CRL-, &amp; CDN-Anforderungen  <br/>  Alle anderen Office 365 Dienste, die nicht speziell über Azure Express Route unterstützt werden  <br/>  Alle anderen Microsoft Cloud-Dienste  <br/>  Office 365 Portal, Office 365 Authentifizierung, &amp; Office in einem Browser  <br/>  Exchange Online, Exchange Online Schutz und Skype for Business Online  <br/> |

> [!NOTE]
> Um niedrigere Präfix Anzahlen für jeden Dienst zu erzielen, wird eine minimale Menge an Überschneidungen zwischen Diensten fortgesetzt. Dieses Verhalten ist normal und beabsichtigt.
  
### <a name="scenario-2-scoping-expressroute-and-internal-bandwidth-use-to-some-office-365-services"></a>Szenario 2: Bereichs Express Route und interne Bandbreitennutzung für einige Office 365 Dienste

Fabrikam Inc, ein großes multinationales Unternehmen mit einem verteilten heterogenen Netzwerk, ist ein Abonnent vieler Office 365-Dienste, einschließlich; Exchange Online, SharePoint Online und Skype for Business Online. Die interne Routinginfrastruktur von Fabrikam kann Tausende von IP-Präfixen in ihren Routingtabellen verarbeiten; Fabrikam möchte jedoch nur die Express Route und die interne Bandbreite für Office 365 Anwendungen bereitstellen, die für die Netzwerkleistung am sensibelsten sind und die vorhandene Internet Bandbreite für alle anderen Office 365-Anwendungen verwenden.
  
Aus diesem Grund umfasst Fabrikam seine Azure Express Route-Bandbreite auf Skype for Business Online BGP-communitywert 12076:5030, der über Express Route Microsoft Peering empfangen wurde. Der restliche Netzwerkdatenverkehr, der Office 365 zugeordnet ist, verwendet weiterhin die Internet Ausgangspunkte.

|**BGP-Community-Tag verwendet**|**Routing Fähigkeit über Azure Express Route**|**Erforderliche Internet Routen**|
|:-----|:-----|:-----|
|Skype for Business  <br/> (12076:5030)  <br/> |Skype SIP-Signalisierung, Downloads, sprach-, Video-und Desktopfreigabe  <br/> | DNS-, CRL-, &amp; CDN-Anforderungen  <br/>  Alle anderen Office 365 Dienste, die nicht speziell über Azure Express Route unterstützt werden  <br/>  Alle anderen Microsoft Cloud-Dienste  <br/>  Office 365 Portal, Office 365 Authentifizierung, &amp; Office in einem Browser  <br/>  Skype for Business Telemetrie, Skype-Client-Quick Tipps, öffentliche Instant Messaging-Konnektivität  <br/>  Exchange Online, Exchange Online Schutz und SharePoint Online  <br/> |

### <a name="scenario-3-scoping-azure-expressroute-for-office-365-services-only"></a>Szenario 3: Definieren von Azure-Express Route nur für Office 365 Dienste

Die Woodgrove Bank ist ein Kunde mehrerer Microsoft Cloud-Dienste, einschließlich Office 365. Nach der Bewertung ihrer Netzwerkkapazität und ihres Verbrauchs entscheidet die Woodgrove Bank, Azure Express Route als bevorzugten Pfad für die unterstützten Office 365 Dienste bereitzustellen. Die Routingtabellen können den vollständigen Satz von Office 365 IP-Präfixen und den von Ihnen gestellten Azure Express Route-Schaltungen unterstützen alle geplanten Bandbreiten-und Latenz Anforderungen unterstützen.
  
Um sicherzustellen, dass der Netzwerkdatenverkehr mit anderen Microsoft-Cloud-Diensten als Office 365 verbunden ist, umfasst die Woodgrove Bank die Verwendung von Express Route für Office 365 auf alle IP-Präfixe, die mit Office 365 spezifischen BGP Community Values getaggt sind, 12076:5010, 12076:5020, 12076:5030, 12076:5100.

|**BGP-Community-Tag verwendet**|**Routing Fähigkeit über Azure Express Route**|**Erforderliche Internet Routen**|
|:-----|:-----|:-----|
|Exchange, Skype for Business & Microsoft Teams, SharePoint, &amp; andere Dienste  <br/> (12076:5010, 12076:5020, 12076:5030, 12076:5100)  <br/> |Exchange Online &amp; Exchange Online Schutz  <br/> SharePoint Online &amp; OneDrive für Unternehmen  <br/> Skype SIP-Signalisierung, Downloads, sprach-, Video-und Desktopfreigabe  <br/> Office 365 Portal, Office 365 Authentifizierung, &amp; Office in einem Browser  <br/> | DNS-, CRL-, &amp; CDN-Anforderungen  <br/>  Alle anderen Office 365 Dienste, die nicht speziell über Azure Express Route unterstützt werden  <br/>  Alle anderen Microsoft Cloud-Dienste  <br/> |

## <a name="key-planning-considerations-to-using-bgp-communities"></a>Wichtige Planungsüberlegungen für die Verwendung von BGP-Communities

Kunden, die sich für die Verwendung von BGP-Communities entscheiden, um zu beeinflussen, wie Express Route im Kundennetzwerk beworben und weitergegeben wird, sollten die folgenden Aspekte berücksichtigen:
  
- Wenn Sie BGP-Communities in Ihrem Netzwerkentwurf verwenden, müssen Sie sicherstellen, dass die Routen Symmetrie weiterhin beibehalten wird. In einigen Fällen kann das Hinzufügen oder Entfernen von BGP-Communities eine Situation verursachen, in der das symmetrische Routing unterbrochen wird und ihre Routingkonfiguration aktualisiert werden muss, um das symmetrische Routing wiederherzustellen.

- Das Definieren von Azure Express Route mit BGP Community values ist eine Kunden Aktion. Microsoft wirbt für alle IP-Präfixe, die der Peering-Beziehung zugeordnet sind, unabhängig von den vom Kunden konfigurierten Bereichs Übersichten.

- Azure Express Route unterstützt keine Aktionen im Microsoft-Netzwerk basierend auf von Kunden zugewiesenen BGP-Communities.

- Die von Office 365 verwendeten IP-Präfixe sind nur mit dienstspezifischen BGP-Community-Werten gekennzeichnet, standortspezifische BGP-Communities werden nicht unterstützt. Office 365 Dienste in der Natur Global sind, werden Filter Präfixe basierend auf dem Standort des Mandanten oder der Daten in der Office 365 Wolke nicht unterstützt. Die empfohlene Vorgehensweise besteht darin, Ihr Netzwerk so zu konfigurieren, dass der kürzeste oder bevorzugte Netzwerkpfad vom Netzwerkstandort des Benutzers in das globale Netzwerk von Microsoft, unabhängig vom physischen Speicherort der IP-Adresse des Office 365 Diensts, der angefordert wird, koordiniert wird.

- Die in den einzelnen BGP-Community-Werten enthaltenen IP-Präfixe stellen ein Subnetz dar, das IP-Adressen für die Office 365 Anwendung enthält, die dem Wert zugeordnet ist. In einigen Fällen verfügt mehr als eine Office 365 Anwendung über IP-Adressen in einem Subnetz, was dazu führt, dass ein IP-Präfix in mehr als einem Community-Wert vorhanden ist. Dies wird, wenn auch selten, zu einem Verhalten aufgrund von Zuordnungs Fragmentierung und hat keine Auswirkungen auf die Präfix Zählung oder die Ziele der Bandbreitenverwaltung. Kunden werden ermutigt, den Ansatz "zulassen, was erforderlich ist" im Gegensatz zu "verweigern, was nicht erforderlich ist", wenn Sie die Vorteile von BGP-Communities nutzen, um die Auswirkungen von Office 365 zu minimieren.

- Bei Verwendung von BGP-Communities werden die zugrunde liegenden Netzwerkverbindungsanforderungen oder die für die Verwendung von Office 365 erforderliche Konfiguration nicht geändert. Kunden, die auf Office 365 zugreifen möchten, müssen weiterhin auf das Internet zugreifen können.

- Das Definieren von Azure Express Route mit BGP-Communities wirkt sich nur auf die Routen aus, die Ihr internes Netzwerk über die Microsoft-Peering-Beziehung sehen kann. Möglicherweise müssen Sie zusätzliche Konfigurationen auf Anwendungsebene wie die Verwendung einer PAC-oder WPAD-Konfiguration in Verbindung mit dem bereichsbezogenen Routing vornehmen.

- Zusätzlich zur Verwendung der von Microsoft zugewiesenen BGP-Communities können Kunden wählen, ihre eigenen BGP-Communities Office 365 IP-Präfixen zuzuweisen, die über Azure Express Route gelernt wurden, um das interne Routing zu beeinflussen. Ein beliebter Anwendungsfall ist das Zuweisen einer standortbasierten BGP-Community zu allen Routen, die über die einzelnen Express Route-Peering-Standorte erlernt werden, und anschließendes Verwenden dieser Informationen im Kundennetzwerk, um den kürzesten oder bevorzugten Netzwerkpfad in das Microsoft-Netzwerk zu koordinieren. Die Verwendung von Kunden zugewiesenen BGP-Communities mit Express Route für Office 365 Szenarien liegt außerhalb des Bereichs von Microsoft-Steuerelement oder Sichtbarkeit.

Hier ist ein kurzer Link, den Sie verwenden können, um zurückzukehren: [https://aka.ms/bgpexpressroute365](https://aka.ms/bgpexpressroute365) .
  
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
  
[Unterstützung für BGP-Communities](https://azure.microsoft.com/documentation/articles/expressroute-routing/)
  
[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](performance-tuning-using-baselines-and-history.md)
  
[Plan zur Problembehandlung für Office 365](performance-troubleshooting-plan.md)
  
[Schulung zu Azure ExpressRoute für Office 365](https://channel9.msdn.com/series/aer)
