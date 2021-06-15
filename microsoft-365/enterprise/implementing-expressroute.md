---
title: Implementieren von ExpressRoute für Office 365
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/5/2017
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
ms.assetid: 77735c9d-8b80-4d2f-890e-a8598547dea6
description: Erfahren Sie, wie Sie ExpressRoute für Office 365 implementieren, das einen alternativen Routingpfad zu vielen mit dem Internet Office 365 Diensten bereitstellt.
ms.openlocfilehash: 3ad6102193a12325de0e4bb2ff16087738688587
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52924939"
---
# <a name="implementing-expressroute-for-office-365"></a>Implementieren von ExpressRoute für Office 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

ExpressRoute für Office 365 bietet einen alternativen Routingpfad zu vielen mit dem Internet Office 365 Diensten. Die Architektur von ExpressRoute für Office 365 basiert auf werbenden öffentlichen IP-Präfixen von Office 365 Diensten, auf die bereits über das Internet in ihre bereitgestellten ExpressRoute-Leitungen zugegriffen werden kann, um diese IP-Präfixe in Ihr Netzwerk weiterverteilen zu können. Mit ExpressRoute aktivieren Sie effektiv mehrere verschiedene Routingpfade über das Internet und über ExpressRoute für viele Office 365 Dienste. Dieser Routingstatus in Ihrem Netzwerk kann eine erhebliche Änderung der Art und Weise darstellen, wie Ihre interne Netzwerktopologie konzipiert ist.
  
 **Status:** Vollständige Anleitung v2
  
Sie müssen ExpressRoute sorgfältig für Office 365 Implementierung planen, um den Netzwerkkomplexitäten gerecht zu werden, die das Routing über einen dedizierten Stromkreis mit Routen bietet, die in Ihr Kernnetzwerk und das Internet eingefügt werden. Wenn Sie und Ihr Team die detaillierte Planung und die Tests in diesem Leitfaden nicht durchführen, besteht ein hohes Risiko, dass die Verbindung mit Office 365 Diensten unterbrochen oder total verloren geht, wenn die ExpressRoute-Verbindung aktiviert ist.
  
Um eine erfolgreiche Implementierung zu erhalten, müssen Sie Ihre Infrastrukturanforderungen analysieren, eine detaillierte Netzwerkbewertung und ein detailliertes Design durchlaufen, das Rollout schrittweise und kontrolliert planen und einen detaillierten Validierungs- und Testplan erstellen. Für eine große, verteilte Umgebung ist es nicht ungewöhnlich, Implementierungen über mehrere Monate hinweg zu sehen. Dieser Leitfaden soll Ihnen bei der Planung helfen.
  
Große erfolgreiche Bereitstellungen können sechs Monate in der Planung dauern und umfassen häufig Teammitglieder aus vielen Bereichen der Organisation, einschließlich Netzwerk-, Firewall- und Proxyserveradministratoren, Office 365 Administratoren, Sicherheit, Endbenutzerunterstützung, Projektmanagement und Executive-Förderung. Ihre Investition in den Planungsprozess verringert die Wahrscheinlichkeit, dass Bereitstellungsfehler auftreten, die zu Ausfallzeiten oder komplexen und teuren Problembehandlungen führen.
  
Wir gehen davon aus, dass die folgenden Voraussetzungen erfüllt sind, bevor dieser Implementierungsleitfaden gestartet wird.
  
1. Sie haben eine Netzwerkbewertung abgeschlossen, um festzustellen, ob ExpressRoute empfohlen und genehmigt wird.

2. Sie haben einen ExpressRoute-Netzwerkdienstanbieter ausgewählt. Hier finden Sie Details zu den [ExpressRoute-Partnern und Peering-Standorten.](/azure/expressroute/expressroute-locations)

3. Sie haben die [ExpressRoute-Dokumentation](https://azure.microsoft.com/documentation/services/expressroute/) bereits gelesen und verstehen, und Ihr internes Netzwerk kann die ExpressRoute-Voraussetzungen bis zum Ende erfüllen.

4. Ihr Team hat alle öffentlichen Anleitungen und Dokumentationen unter gelesen [https://aka.ms/expressrouteoffice365](./azure-expressroute.md) und sich die Azure [https://aka.ms/ert](https://aka.ms/ert) [ExpressRoute for Office 365 Training-Reihe](https://channel9.msdn.com/series/aer) auf Channel 9 angesehen, um ein Verständnis wichtiger technischer Details zu erhalten, einschließlich:

      - Die Internetabhängigkeiten von SaaS-Diensten.

      - So vermeiden Sie asymmetrische Routen und behandeln komplexes Routing.

      - Integrieren von Perimetersicherheits-, Verfügbarkeits- und Anwendungssteuerungen.

## <a name="begin-by-gathering-requirements"></a>Beginnen Sie mit dem Sammeln von Anforderungen
<a name="requirements"> </a>

Bestimmen Sie zunächst, welche Features und Dienste Sie in Ihrer Organisation einführen möchten. Sie müssen ermitteln, welche Features der verschiedenen Office 365 Dienste verwendet werden und an welchen Standorten in Ihrem Netzwerk Personen gehostet werden, die diese Features verwenden. Mit dem Katalog der Szenarien müssen Sie die Netzwerkattribute hinzufügen, die für jedes dieser Szenarien erforderlich sind. z. B. eingehenden und ausgehenden Netzwerkdatenverkehr und ob die Office 365 Endpunkte über ExpressRoute verfügbar sind oder nicht.
  
So erfassen Sie die Anforderungen Ihrer Organisation:
  
- Katalogisieren Sie den eingehenden und ausgehenden Netzwerkdatenverkehr für die Office 365 Dienste, die Ihre Organisation verwendet. Auf der Seite Office 365 URLs und IP-Adressbereiche finden Sie eine Beschreibung der Flüsse, die für unterschiedliche Office 365 Szenarien erforderlich sind.

- Erfassen Sie die Dokumentation der vorhandenen Netzwerktopologie mit Details zu Ihrem internen WAN-Backbone und ihrer Topologie, zur Konnektivität von Satellitenstandorten, zur letzten Benutzerverbindung, zum Routing zu Netzwerkperimeter-Ausgangspunkten und zu Proxydiensten.

  - Identifizieren Sie eingehende Dienstendpunkte in den Netzwerkdiagrammen, mit denen Office 365 und andere Microsoft-Dienste eine Verbindung herstellen, und zeigen Sie sowohl Internet- als auch vorgeschlagene ExpressRoute-Verbindungspfade an.

  - Identifizieren Sie alle geografischen Benutzerstandorte und die WAN-Konnektivität zwischen Standorten, zusammen mit welchen Standorten derzeit ein Ausgang in das Internet besteht und welche Standorte für einen Ausgang zu einem ExpressRoute-Peeringstandort vorgeschlagen werden.

  - Identifizieren Sie alle Edgegeräte, z. B. Proxys, Firewalls usw., und katalogisieren Sie ihre Beziehung zu Flüssen, die über das Internet und ExpressRoute fließen.

  - Dokumentieren Sie, ob Endbenutzer über direktes Routing oder indirekten Anwendungsproxy für Internet- und ExpressRoute-Flüsse auf Office 365 Dienste zugreifen.

- Fügen Sie den Standort Ihres Mandanten und Die-mich-Standorte zu Ihrem Netzwerkdiagramm hinzu.

- Schätzen Sie die erwarteten und beobachteten Netzwerkleistungs- und Latenzmerkmale von hauptbenutzerstandorten bis Office 365. Beachten Sie, dass Office 365 eine globale und verteilte Gruppe von Diensten ist und Benutzer verbindungen mit Standorten herstellen, die sich vom Standort ihres Mandanten unterscheiden können. Aus diesem Grund wird empfohlen, die Latenz zwischen dem Benutzer und dem nächstgelegenen Edge des globalen Microsoft-Netzwerks über ExpressRoute und Internetverbindungen zu messen und zu optimieren. Sie können Ihre Ergebnisse aus der Netzwerkbewertung verwenden, um diese Aufgabe zu unterstützen.

- Listet die Netzwerksicherheits- und Hochverfügbarkeitsanforderungen des Unternehmens auf, die mit der neuen ExpressRoute-Verbindung erfüllt werden müssen. Beispiel: Wie erhalten Benutzer weiterhin Zugriff auf Office 365 im Falle eines Ausfalls des Internetausgangs oder expressRoute-Netzschalters.

- Dokumentieren Sie, welche eingehenden und ausgehenden Office 365 Netzwerkflüsse den Internetpfad und welche ExpressRoute verwenden. Die Einzelheiten der geografischen Standorte Ihrer Benutzer und Details zu Ihrer lokalen Netzwerktopologie erfordern möglicherweise, dass sich der Plan von einem Benutzerstandort zum anderen unterscheidet.

### <a name="catalog-your-outbound-and-inbound-network-traffic"></a>Katalogisieren des ausgehenden und eingehenden Netzwerkdatenverkehrs
<a name="trafficCatalog"> </a>

Um Routing und andere Netzwerkkomplexitäten zu minimieren, empfehlen wir, ExpressRoute nur für Office 365 für die Netzwerkdatenströme zu verwenden, die aufgrund behördlicher Anforderungen oder als Ergebnis der Netzwerkbewertung eine dedizierte Verbindung durchlaufen müssen. Darüber hinaus wird empfohlen, dass Sie den Umfang des ExpressRoute-Routings bereitstellen und ausgehenden und eingehenden Netzwerkdatenverkehr als unterschiedliche und unterschiedliche Phasen des Implementierungsprojekts nähern. Stellen Sie ExpressRoute für Office 365 nur für benutzerinitiierte ausgehende Netzwerkdatenströme bereit, und lassen Sie eingehenden Netzwerkdatenverkehr über das Internet zurück, um den Anstieg der komplexitätsbezogenen Topologie und die Risiken zu steuern, die durch die Einführung zusätzlicher asymmetrischer Routingmöglichkeiten entsteht.
  
Ihr Netzwerkdatenverkehr-Katalog sollte Auflistungen aller eingehenden und ausgehenden Netzwerkverbindungen enthalten, über die Sie zwischen Ihrem lokalen Netzwerk und Microsoft verfügen.
  
- Ausgehender Netzwerkdatenverkehr ist jedes Szenario, in dem eine Verbindung von Ihrer lokalen Umgebung initiiert wird, z. B. von internen Clients oder Servern, mit einem Ziel der Microsoft-Dienste. Diese Verbindungen können direkt zu Office 365 oder indirekt erfolgen, z. B. wenn die Verbindung proxyserver, Firewalls oder andere Netzwerkgeräte auf dem Pfad zum Office 365 durchläuft.

- Eingehende Netzwerkdatenverkehrflüsse sind alle Szenarien, in denen eine Verbindung von der Microsoft-Cloud zu einem lokalen Host initiiert wird. Diese Verbindungen müssen in der Regel firewall- und andere Sicherheitsinfrastruktur durchlaufen, die die Sicherheitsrichtlinie des Kunden für Extern-Flüsse erfordert.

Lesen Sie den Abschnitt "Sicherstellen der **Routen symmetrie"** im Artikel ["Routing mit ExpressRoute" für Office 365,](https://support.office.com/article/Routing-with-ExpressRoute-for-Office-365-e1da26c6-2d39-4379-af6f-4da213218408) um zu bestimmen, welche Dienste eingehenden Datenverkehr senden, und suchen Sie nach der Spalte, die **expressRoute für Office 365** im Referenzartikel Office 365 Endpunkte markiert ist, um die restlichen [Konnektivitätsinformationen](https://support.office.com/article/Office-365-URLs-and-IP-address-ranges-8548a211-3fe7-47cb-abb1-355ea5aa88a2) zu ermitteln.
  
Für jeden Dienst, der eine ausgehende Verbindung erfordert, sollten Sie die geplante Konnektivität für den Dienst beschreiben, einschließlich Netzwerkrouting, Proxykonfiguration, Paketüberprüfung und Bandbreitenanforderungen.
  
Für jeden Dienst, der eine eingehende Verbindung erfordert, benötigen Sie einige zusätzliche Informationen. Server in der Microsoft-Cloud stellen Verbindungen mit Ihrem lokalen Netzwerk her. Um sicherzustellen, dass die Verbindungen ordnungsgemäß hergestellt werden, sollten Sie alle Aspekte dieser Konnektivität beschreiben, einschließlich; die öffentlichen DNS-Einträge für die Dienste, die diese eingehenden Verbindungen akzeptieren, die cidr-formatierten IPv4-IP-Adressen, welche ISP-Geräte beteiligt sind und wie eingehende NAT- oder Quell-NAT für diese Verbindungen behandelt wird.
  
Eingehende Verbindungen sollten unabhängig davon überprüft werden, ob sie eine Verbindung über das Internet oder ExpressRoute herstellen, um sicherzustellen, dass asymmetrisches Routing nicht eingeführt wurde. In einigen Fällen müssen lokale Endpunkte, die Office 365 Dienste eingehende Verbindungen initiieren, möglicherweise auch von anderen Microsoft- und nicht-Microsoft-Dienste aufgerufen werden. Es ist äußerst wichtig, dass das Aktivieren des ExpressRoute-Routings zu diesen Diensten für Office 365 Zwecke andere Szenarien nicht unterbricht. In vielen Fällen müssen Kunden möglicherweise bestimmte Änderungen an ihrem internen Netzwerk implementieren, z. B. quellbasierte NAT, um sicherzustellen, dass eingehende Flüsse von Microsoft symmetrisch bleiben, nachdem ExpressRoute aktiviert wurde.
  
Hier ist ein Beispiel für die erforderliche Detailebene. In diesem Fall würde Exchange Hybrid über ExpressRoute an das lokale System weitergeleitet. 

|Connection-Eigenschaft   |Wert  |
|----------|-----------|
|**Richtung des Netzwerkdatenverkehrs** <br/> |Eingehend  <br/> |
|**Dienst** <br/> |Exchange Hybrid  <br/> |
|**Öffentlicher Office 365-Endpunkt (Quelle)** <br/> |Exchange Online (IP-Adressen)  <br/> |
|**Öffentlicher lokaler Endpunkt (Ziel)** <br/> |5.5.5.5  <br/> |
|**Öffentlicher (Internet)-DNS-Eintrag** <br/> |Autodiscover.contoso.com  <br/> |
|**Wird dieser lokale Endpunkt von anderen (nicht Office 365) Microsoft-Dienste** <br/> |Nein  <br/> |
|**Wird dieser lokale Endpunkt von Benutzern/Systemen im Internet verwendet?** <br/> |Ja  <br/> |
|**Interne Systeme, die über öffentliche Endpunkte veröffentlicht werden** <br/> |Exchange Server Clientzugriffsrolle (lokal) 192.168.101, 192.168.102, 192.168.103  <br/> |
|**IP-Ankündigung des öffentlichen Endpunkts** <br/> |**To Internet**: 5.5.0.0/16 **To ExpressRoute**: 5.5.5.0/24  <br/> |
|**Sicherheits-/Umkreiskontrollen** <br/> |**Internetpfad**: DeviceID_002  **ExpressRoute-Pfad:** DeviceID_003  <br/> |
|**Hochverfügbarkeit** <br/> |Aktiv/Aktiv über zwei georedundante/ExpressRoute-Leitungen – Chicago und Chicago  <br/> |
|**Pfad-Symmetrie-Steuerelement** <br/> |**Methode**: **Quell-NAT-Internetpfad:** Quell-NAT-eingehende Verbindungen zu 192.168.5.5 **ExpressRoute-Pfad:** Quell-NAT-Verbindungen zu 192.168.1.0 (Chicago) und 192.168.2.0 (Seattle)  <br/> |

Hier ist ein Beispiel für einen Dienst, der nur ausgehend ist:

|**Connection-Eigenschaft**|**Wert**|
|----------|-----------|
|**Richtung des Netzwerkdatenverkehrs** <br/> |Ausgehend  <br/> |
|**Dienst** <br/> |SharePoint Online  <br/> |
|**Lokaler Endpunkt (Quelle)** <br/> |Benutzerarbeitsstation  <br/> |
|**Öffentlicher Office 365-Endpunkt (Ziel)** <br/> |SharePoint Online (IP-Adressen)  <br/> |
|**Öffentlicher (Internet)-DNS-Eintrag** <br/> |\*.sharepoint.com (und zusätzliche FQDNs)  <br/> |
|**CDN Verweise** <br/> |cdn.sharepointonline.com (und zusätzliche FQDNs) – IP-Adressen, die von CDN Anbietern verwaltet werden)  <br/> |
|**VERWENDETE IP-Ankündigung und NAT** <br/> |**Internetpfad/Quell-NAT:** 1.1.1.0/24  <br/> **ExpressRoute-Pfad/Quell-NAT:** 1.1.2.0/24 (Chicago) und 1.1.3.0/24 (Chicago)  <br/> |
|**Konnektivitätsmethode** <br/> |**Internet:** über Layer-7-Proxy (PAC-Datei)  <br/> **ExpressRoute:** Direct Routing (kein Proxy)  <br/> |
|**Sicherheits-/Umkreiskontrollen** <br/> |**Internetpfad:** DeviceID_002  <br/> **ExpressRoute-Pfad:** DeviceID_003  <br/> |
|**Hochverfügbarkeit** <br/> |**Internetpfad:** Redundanter Internetausgang  <br/> **ExpressRoute-Pfad:** Aktives/aktives "Hot-Routing" über zwei georedundante ExpressRoute-Leitungen – Chicago und Chicago  <br/> |
|**Pfad-Symmetrie-Steuerelement** <br/> |**Methode:** Quell-NAT für alle Verbindungen  <br/> |

### <a name="your-network-topology-design-with-regional-connectivity"></a>Ihr Netzwerktopologiedesign mit regionaler Konnektivität
<a name="topology"> </a>

Sobald Sie die Dienste und die zugehörigen Netzwerkdatenverkehrflüsse verstanden haben, können Sie ein Netzwerkdiagramm erstellen, das diese neuen Konnektivitätsanforderungen enthält und die Änderungen veranschaulicht, die Sie zur Verwendung von ExpressRoute für Office 365 vornehmen werden. Das Diagramm sollte Folgendes enthalten:
  
1. Alle Benutzerspeicherorte, von denen aus Office 365 und andere Dienste aufgerufen werden.

2. Alle Internet- und ExpressRoute-Ausgangspunkte.

3. Alle ausgehenden und eingehenden Geräte, die die Konnektivität im und aus dem Netzwerk verwalten, einschließlich Router, Firewalls, Anwendungsproxyserver und Angriffserkennung/-verhinderung.

4. Interne Ziele für den gesamten eingehenden Datenverkehr, z. B. interne ADFS-Server, die Verbindungen von den Proxyservern der ADFS-Webanwendung akzeptieren.

5. Katalog aller IP-Subnetze, die angekündigt werden

6. Identifizieren Sie jeden Ort, an dem Personen auf Office 365 zugreifen, und listen Sie die Meet-Me-Orte auf, die für ExpressRoute verwendet werden.

7. Standorte und Teile Ihrer internen Netzwerktopologie, an denen von ExpressRoute gelernte Microsoft-IP-Präfixe akzeptiert, gefiltert und weitergegeben werden.

8. Die Netzwerktopologie sollte den geografischen Standort der einzelnen Netzwerksegmente und die Verbindung mit dem Microsoft-Netzwerk über ExpressRoute und/oder das Internet veranschaulichen.

Das folgende Diagramm zeigt jeden Ort, an dem Personen Office 365 verwenden werden, zusammen mit den eingehenden und ausgehenden Routinganzeigen für Office 365.
  
![ExpressRoute – Regionale geografische Besprechung – ich](../media/d866b36b-49bf-416b-af1b-d054e24989d2.png)
  
Für ausgehenden Datenverkehr greifen die Benutzer auf drei Arten auf Office 365 zu:
  
1. Über einen Meet-Me-Standort in Nordamerika für die Menschen in Kalifornien.

2. Über einen Meet-Me-Ort in Hongkong für die Personen in Hongkong.

3. Über das Internet in Bangladesch, wo weniger Personen und kein ExpressRoute-Netz bereitgestellt werden.

![Ausgehende Verbindungen für regionales Diagramm](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
Ebenso gibt der eingehende Netzwerkdatenverkehr von Office 365 auf eine von drei Arten zurück:
  
1. Über einen Meet-Me-Standort in Nordamerika für die Menschen in Kalifornien.

2. Über einen Meet-Me-Ort in Hongkong für die Personen in Hongkong.

3. Über das Internet in Bangladesch, wo weniger Personen und kein ExpressRoute-Netz bereitgestellt werden.

![Eingehende Verbindungen für regionales Diagramm](../media/d6d6160d-bf28-4de3-a787-186c7432b306.png)
  
### <a name="determine-the-appropriate-meet-me-location"></a>Ermitteln des geeigneten Meet-Me-Standorts

Die Auswahl von Meet-Me-Standorten, bei denen es sich um den physischen Standort handelt, an dem Ihre ExpressRoute-Verbindung Ihr Netzwerk mit dem Microsoft-Netzwerk verbindet, wird durch die Standorte beeinflusst, von denen aus Personen auf Office 365 zugreifen. Als SaaS-Angebot wird Office 365 nicht auf die gleiche Weise wie Azure unter dem regionalen IaaS- oder PaaS-Modell ausgeführt. Stattdessen ist Office 365 eine verteilte Gruppe von Diensten für die Zusammenarbeit, bei denen Benutzer möglicherweise eine Verbindung mit Endpunkten über mehrere Rechenzentren und Regionen hinweg herstellen müssen, die sich möglicherweise nicht unbedingt am selben Standort oder in derselben Region befinden, in der der Mandant des Benutzers gehostet wird.
  
Dies bedeutet, dass Sie bei der Auswahl von Meet-Me-Standorten für ExpressRoute für Office 365 die wichtigsten Überlegungen anstellen müssen, von wo aus die Personen in Ihrer Organisation eine Verbindung herstellen. Die allgemeine Empfehlung für eine optimale Office 365 Konnektivität besteht darin, Routing zu implementieren, sodass Benutzeranforderungen an Office 365 Dienste über den kürzesten Netzwerkpfad an das Microsoft-Netzwerk weitergeleitet werden. Dies wird auch häufig als "Hot-Routing" bezeichnet. Wenn sich z. B. die meisten Office 365 Benutzer an einem oder zwei Orten befinden, wird durch auswählen von Besprechungs-mir-Orten, die sich in der nächstgelegenen Nähe zum Standort dieser Benutzer befinden, das optimale Design erstellt. Wenn Ihr Unternehmen über große Benutzerzahlen in vielen verschiedenen Regionen verfügt, sollten Sie mehrere ExpressRoute-Schaltungen und Meet-Me-Standorte in Betracht ziehen. Für einige Ihrer Benutzerstandorte ist der kürzeste/optimalste Pfad zum Microsoft-Netzwerk und Office 365 möglicherweise nicht über Ihr internes WAN und ExpressRoute-Meet-Me-Punkte, sondern über das Internet.
  
Häufig gibt es mehrere Meet-Me-Orte, die in einer Region mit relativer Nähe zu Ihren Benutzern ausgewählt werden können. Füllen Sie die folgende Tabelle aus, um Ihre Entscheidungen zu leiten.

**Geplante ExpressRoute-Meet-Me-Standorte in Kalifornien und New York**

|Speicherort  <br/> |Anzahl der Personen  <br/> |Wartezeit für Microsoft-Netzwerk über Internetausgang erwartet  <br/> |Wartezeit für Microsoft-Netzwerk über ExpressRoute erwartet  <br/> |
|----------|-----------|----------|-----------|
|München  <br/> |10.000  <br/> |~15 ms  <br/> |~10 ms (über Silicon Silicon)  <br/> |
|Washington DC  <br/> |15.000  <br/> |~20 ms  <br/> |~10 ms (über New York)  <br/> |
|Dallas  <br/> |5 000  <br/> |~15 ms  <br/> |~40 ms (über New York)  <br/> |

Sobald die globale Netzwerkarchitektur mit der Office 365 Region, den Meet-Me-Standorten des ExpressRoute-Netzwerkdienstanbieters und der Anzahl der Personen nach Standort entwickelt wurde, kann sie verwendet werden, um festzustellen, ob Optimierungen vorgenommen werden können. Es kann auch globale Spitzkehrennetzwerkverbindungen anzeigen, bei denen der Datenverkehr an einen entfernten Ort weiterleitet, um den Meet-Me-Standort zu erhalten. Wenn eine Spitzkehren im globalen Netzwerk erkannt wird, sollte sie behoben werden, bevor Sie fortfahren. Suchen Sie entweder einen anderen Meet-Me-Speicherort, oder verwenden Sie selektive Internet-Breakout-Ausgangspunkte, um die Spitzkehren zu vermeiden.
  
Das erste Diagramm zeigt ein Beispiel für einen Kunden mit zwei physischen Standorten in Nordamerika. Sie können die Informationen zu Bürostandorten, Office 365 Mandantenstandorten und verschiedene Auswahlmöglichkeiten für ExpressRoute-Besprechungsstandorte anzeigen. In diesem Beispiel hat der Kunde den Meet-Me-Standort basierend auf zwei Prinzipien ausgewählt, in der Reihenfolge:
  
1. Die nächste Nähe zu den Personen in ihrer Organisation.

2. Am nächstgelegenen in der Nähe eines Microsoft-Rechenzentrums, in dem Office 365 gehostet wird.

![ExpressRoute US geographic meet-me](../media/5ec38274-b317-4ec1-91c8-90c2a7fd32ca.png)
  
Das zweite Diagramm erweitert dieses Konzept etwas weiter und zeigt ein Beispiel für einen multinationalen Kunden, der mit ähnlichen Informationen und Entscheidungen konfrontiert ist. Dieser Kunde verfügt über ein kleines Büro in Bangladesch mit nur einem kleinen Team von zehn Personen, das sich auf die Erweiterung seines Fußabdrucks in der Region konzentriert. Es gibt einen Meet-Me-Standort in Chennai und ein Microsoft-Rechenzentrum mit Office 365 in Chennai gehostet, sodass ein Meet-Me-Ort sinnvoll wäre. Für zehn Personen ist der Aufwand für den zusätzlichen Kreis jedoch beschwerlich. Wenn Sie sich Ihr Netzwerk ansehen, müssen Sie ermitteln, ob die Latenz beim Senden des Netzwerkdatenverkehrs über Ihr Netzwerk effektiver ist als die Ausgabe des Kapitals, um einen anderen ExpressRoute-Stromkreis zu erwerben.
  
Alternativ können die zehn Personen in Bangladesch mit ihrem Netzwerkdatenverkehr, der über das Internet an das Microsoft-Netzwerk gesendet wird, eine bessere Leistung erzielen, als sie in ihrem internen Netzwerk weiterleiten würden, wie in den einführenden Diagrammen gezeigt und unten wiedergegeben.
  
![Ausgehende Verbindungen für regionales Diagramm](../media/8319943d-08f0-4781-9ef3-d23de2ad4671.png)
  
## <a name="create-your-expressroute-for-office-365-implementation-plan"></a>Erstellen Ihres ExpressRoute für Office 365 Implementierungsplans
<a name="implementation"> </a>

Ihr Implementierungsplan sollte sowohl die technischen Details der Konfiguration von ExpressRoute als auch die Details der Konfiguration aller anderen Infrastruktur in Ihrem Netzwerk umfassen, z. B. die folgenden.
  
- Planen Sie, welche Dienste zwischen ExpressRoute und Internet aufgeteilt werden.

- Planen sie Bandbreite, Sicherheit, hohe Verfügbarkeit und Failover.

- Entwerfen des eingehenden und ausgehenden Routings, einschließlich ordnungsgemäßer Routingpfadoptimierungen für verschiedene Standorte

- Entscheiden Sie, wie weit ExpressRoute-Routen in Ihr Netzwerk angekündigt werden und wie clients den Internet- oder ExpressRoute-Pfad auswählen können. Beispielsweise direktes Routing oder Anwendungsproxy.

- Planen von Änderungen an DNS-Einträgen, einschließlich [Einträgen des Sender Policy Frameworks.](../security/office-365-security/set-up-spf-in-office-365-to-help-prevent-spoofing.md)

- Planen Sie die NAT-Strategie, einschließlich ausgehender und eingehender Quell-NAT.

### <a name="plan-your-routing-with-both-internet-and-expressroute-network-paths"></a>Planen des Routings mit Internet- und ExpressRoute-Netzwerkpfaden
<a name="paths"> </a>

- Für Ihre anfängliche Bereitstellung wird empfohlen, dass alle eingehenden Dienste, z. B. eingehende E-Mails oder Hybridkonnektivität, das Internet verwenden.

- Planen Sie das LAN-Routing des Endbenutzerclients, z. B. [konfigurieren einer PAC/WPAD-Datei,](./managing-office-365-endpoints.md)einer Standardroute, Proxyservern und BGP-Routenanzeigen.

- Planen Sie das Umkreisrouting, einschließlich Proxyservern, Firewalls und Cloudproxys.

### <a name="plan-your-bandwidth-security-high-availability-and-failover"></a>Planen von Bandbreite, Sicherheit, hoher Verfügbarkeit und Failover
<a name="availability"> </a>

Erstellen Sie einen Plan für die Bandbreite, die für jede wichtige Office 365 Workload erforderlich ist. Ermitteln Sie die Bandbreitenanforderungen für Exchange Online, SharePoint Online und Skype for Business Online separat. Sie können die Berechnungsrechner, die wir für Exchange Online und Skype for Business bereitgestellt haben, als Ausgangspunkt verwenden. Es ist jedoch ein Pilottest mit einer repräsentativen Stichprobe der Benutzerprofile und -standorte erforderlich, um die Bandbreitenanforderungen Ihrer Organisation vollständig zu verstehen.
  
Fügen Sie hinzu, wie die Sicherheit an jedem Internet- und ExpressRoute-Ausgangspunkt zu Ihrem Plan verarbeitet wird. Denken Sie daran, dass alle ExpressRoute-Verbindungen Office 365 öffentliches Peering verwenden und weiterhin in Übereinstimmung mit den Sicherheitsrichtlinien Ihres Unternehmens für die Verbindung mit externen Netzwerken gesichert werden müssen.
  
Fügen Sie Details zu Ihrem Plan hinzu, welche Personen von welcher Art des Ausfalls betroffen sind und wie diese Personen ihre Arbeit auf einfachste Weise in voller Kapazität ausführen können.
  
#### <a name="plan-bandwidth-requirements-including-skype-for-business-requirements-on-jitter-latency-congestion-and-headroom"></a>Planen von Bandbreitenanforderungen einschließlich Skype for Business Anforderungen für Jitter, Latenz, Überlastung und Headroom
  
Skype for Business Online verfügt auch über spezifische zusätzliche Netzwerkanforderungen, die im Artikel ["Medienqualität und Leistung der Netzwerkkonnektivität" in Skype for Business Online](https://support.office.com/article/Media-Quality-and-Network-Connectivity-Performance-in-Skype-for-Business-Online-5fe3e01b-34cf-44e0-b897-b0b2a83f0917)beschrieben werden.
  
Lesen Sie den Abschnitt **Bandbreitenplanung für Azure ExpressRoute** in [der Netzwerkplanung mit ExpressRoute für Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
Wenn Sie eine Bandbreitenbewertung mit Ihren Pilotbenutzern durchführen, können Sie unseren Leitfaden verwenden. [Office 365 Leistungsoptimierung mit Basisplänen und Leistungsverlauf.](https://support.office.com/article/Office-365-performance-tuning-using-baselines-and-performance-history-1492cb94-bd62-43e6-b8d0-2a61ed88ebae)
  
#### <a name="plan-for-high-availability-requirements"></a>Planen von Anforderungen für hohe Verfügbarkeit
  
Erstellen Sie einen Plan für hohe Verfügbarkeit, um Ihre Anforderungen zu erfüllen, und integrieren Sie diesen in Ihr aktualisiertes Netztopologiediagramm. Lesen Sie den Abschnitt **"Hohe Verfügbarkeit und Failover mit Azure ExpressRoute"** in [der Netzwerkplanung mit ExpressRoute für Office 365.](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd)
  
#### <a name="plan-for-network-security-requirements"></a>Planen von Netzwerksicherheitsanforderungen
  
Erstellen Sie einen Plan, um Ihre Netzwerksicherheitsanforderungen zu erfüllen, und integrieren Sie diesen in Ihr aktualisiertes Netztopologiediagramm. Lesen Sie den Abschnitt **Anwenden von Sicherheitssteuerelementen auf Azure ExpressRoute für Office 365 Szenarien** in der [Netzwerkplanung mit ExpressRoute für Office 365](https://support.office.com/article/Network-planning-with-ExpressRoute-for-Office-365-103208f1-e788-4601-aa45-504f896511cd).
  
### <a name="design-outbound-service-connectivity"></a>Entwerfen ausgehender Dienstkonnektivität
<a name="outbound"> </a>

ExpressRoute für Office 365 weist *ausgehende* Netzwerkanforderungen auf, die möglicherweise unbekannt sind. Insbesondere müssen die IP-Adressen, die Ihre Benutzer und Netzwerke darstellen, Office 365 und als Quellendpunkte für ausgehende Netzwerkverbindungen mit Microsoft fungieren, bestimmte Anforderungen erfüllen, die unten beschrieben werden.
  
1. Die Endpunkte müssen öffentliche IP-Adressen sein, die bei Ihrem Unternehmen oder beim Netzbetreiber registriert sind, der Ihnen ExpressRoute-Konnektivität bereitstellt.

2. Die Endpunkte müssen an Microsoft angekündigt und von ExpressRoute überprüft/akzeptiert werden.

3. Die Endpunkte dürfen nicht mit der gleichen oder einer bevorzugten Routingmetrik im Internet angekündigt werden.

4. Die Endpunkte dürfen nicht für verbindungen mit Microsoft-Dienste verwendet werden, die nicht über ExpressRoute konfiguriert sind.

Wenn Ihr Netzwerkdesign diese Anforderungen nicht erfüllt, besteht ein hohes Risiko, dass bei Benutzern Verbindungsfehler bei Office 365 und anderen Microsoft-Dienste aufgrund von schwarzen Holing oder asymmetrischem Routing auftreten. Dies geschieht, wenn Anforderungen an Microsoft-Dienste über ExpressRoute weitergeleitet werden, Antworten jedoch über das Internet oder umgekehrt zurückgeleitet werden und die Antworten von zustandsbehafteten Netzwerkgeräten wie Firewalls gelöscht werden.
  
Die gängigste Methode, die Sie verwenden können, um die oben genannten Anforderungen zu erfüllen, ist die Verwendung der Quell-NAT, die entweder als Teil Ihres Netzwerks implementiert oder von Ihrem ExpressRoute-Netzbetreiber bereitgestellt wird. Mit der Quell-NAT können Sie die Details und die private IP-Adressierung Ihres Internetnetzwerks von ExpressRoute abstrahieren. In Verbindung mit korrekten IP-Routenanzeigen bieten Sie einen einfachen Mechanismus, um die Pfad-Symmetrie sicherzustellen. Wenn Sie zustandsbehaftete Netzwerkgeräte verwenden, die für ExpressRoute-Peeringstandorte spezifisch sind, müssen Sie separate NAT-Pools für jedes ExpressRoute-Peering implementieren, um die Pfad-Symmetrie sicherzustellen.
  
Weitere Informationen zu den [ExpressRoute-NAT-Anforderungen.](/azure/expressroute/expressroute-nat)
  
Fügen Sie dem Netzwerktopologiediagramm die Änderungen für die ausgehende Verbindung hinzu.
  
### <a name="design-inbound-service-connectivity"></a>Entwerfen der Verbindung mit eingehenden Diensten
<a name="inbound"> </a>

Der Großteil der Unternehmensbereitstellungen Office 365 setzt eine Form der eingehenden Konnektivität von Office 365 zu lokalen Diensten voraus, z. B. für Exchange, SharePoint und Skype for Business Hybridszenarien, Postfachmigrationen und Authentifizierung mithilfe der ADFS-Infrastruktur. Wenn Sie expressRoute einen zusätzlichen Routingpfad zwischen Ihrem lokalen Netzwerk und Microsoft für ausgehende Verbindungen aktivieren, können diese eingehenden Verbindungen versehentlich durch asymmetrisches Routing beeinträchtigt werden, auch wenn Sie beabsichtigen, dass diese Flüsse weiterhin das Internet verwenden. Es werden einige nachstehend beschriebene Vorsichtsmaßnahmen empfohlen, um sicherzustellen, dass es keine Auswirkungen auf internetbasierte eingehende Flüsse von Office 365 zu lokalen Systemen gibt.
  
Um die Risiken des asymmetrischen Routings für eingehende Netzwerkdatenströme zu minimieren, sollten alle eingehenden Verbindungen die Quell-NAT verwenden, bevor sie in Segmente Ihres Netzwerks weitergeleitet werden, die über Routing-Sichtbarkeit in ExpressRoute verfügen. Wenn die eingehenden Verbindungen auf ein Netzwerksegment mit Routing-Sichtbarkeit in ExpressRoute ohne Quell-NAT zulässig sind, werden Anforderungen, die von Office 365 stammen, aus dem Internet eingegeben, aber die Antwort zurück zu Office 365 bevorzugt den ExpressRoute-Netzwerkpfad zurück zum Microsoft-Netzwerk, was zu asymmetrischem Routing führt.
  
Sie können eines der folgenden Implementierungsmuster in Betracht ziehen, um diese Anforderung zu erfüllen:
  
1. Führen Sie die Nat-Quell-NAT durch, bevor Anforderungen mithilfe von Netzwerkgeräten wie Firewalls oder Lastenausgleichsgeräten über den Pfad vom Internet zu Ihren lokalen Systemen an Ihr internes Netzwerk weitergeleitet werden.

2. Stellen Sie sicher, dass ExpressRoute-Routen nicht an die Netzwerksegmente weitergegeben werden, in denen sich eingehende Dienste wie Front-End-Server oder Reverseproxysysteme befinden, in denen Internetverbindungen verarbeitet werden.

Die explizite Rechnung dieser Szenarien in Ihrem Netzwerk und das Beibehalten des gesamten eingehenden Netzwerkdatenverkehrs über das Internet trägt dazu bei, das Bereitstellungs- und Betriebsrisiko eines asymmetrischen Routings zu minimieren.
  
Es kann Fälle geben, in denen Sie einige eingehende Flüsse über ExpressRoute-Verbindungen leiten möchten. Berücksichtigen Sie für diese Szenarien die folgenden zusätzlichen Überlegungen.
  
1. Office 365 können nur auf lokale Endpunkte abzielen, die öffentliche IPs verwenden. Dies bedeutet, dass auch wenn der lokale eingehende Endpunkt nur für Office 365 über ExpressRoute verfügbar gemacht wird, ihm dennoch eine öffentliche IP zugeordnet sein muss.

2. Alle DNS-Namensauflösungen, die Office 365 Dienste ausführen, um lokale Endpunkte aufzulösen, erfolgen mit öffentlichem DNS. Dies bedeutet, dass Sie den FQDN für eingehende Dienstendpunkte für IP-Zuordnungen im Internet registrieren müssen.

3. Um eingehende Netzwerkverbindungen über ExpressRoute zu empfangen, müssen die öffentlichen IP-Subnetze für diese Endpunkte für Microsoft über ExpressRoute angekündigt werden.

4. Werten Sie diese eingehenden Netzwerkdatenströme sorgfältig aus, um sicherzustellen, dass entsprechende Sicherheits- und Netzwerkkontrollen in Übereinstimmung mit den Sicherheits- und Netzwerkrichtlinien Ihres Unternehmens angewendet werden.

5. Sobald Ihre lokalen eingehenden Endpunkte über ExpressRoute an Microsoft angekündigt wurden, wird ExpressRoute effektiv zum bevorzugten Routingpfad zu diesen Endpunkten für alle Microsoft-Dienste, einschließlich Office 365. Dies bedeutet, dass diese Endpunktsubnetze nur für die Kommunikation mit Office 365 Diensten und keinen anderen Diensten im Microsoft-Netzwerk verwendet werden dürfen. Andernfalls führt Ihr Entwurf zu asymmetrischem Routing, bei dem eingehende Verbindungen von anderen Microsoft-Dienste es vorziehen, eingehende Verbindungen über ExpressRoute weiterzuleiten, während der Rückgabepfad das Internet verwendet.

6. Für den Fall, dass ein ExpressRoute- oder Meet-Me-Standort ausgefallen ist, müssen Sie sicherstellen, dass die lokalen eingehenden Endpunkte weiterhin verfügbar sind, um Anforderungen über einen separaten Netzwerkpfad zu akzeptieren. Dies kann bedeuten, dass Subnetze für diese Endpunkte über mehrere ExpressRoute-Leitungen angezeigt werden.

7. Es wird empfohlen, die Quell-NAT für alle eingehenden Netzwerkdatenverkehrströme anzuwenden, die über ExpressRoute in Ihr Netzwerk gelangen, insbesondere wenn diese über zustandsübergreifende Netzwerkgeräte wie Firewalls fließen.

8. Einige lokale Dienste, z. B. ADFS-Proxy oder Exchange AutoErmittlung, empfangen möglicherweise eingehende Anforderungen von Office 365 Diensten und Benutzern aus dem Internet. Für diese Anforderungen wird Office 365 auf den gleichen FQDN wie Benutzeranforderungen über das Internet abzielen. Das Zulassen von eingehenden Benutzerverbindungen aus dem Internet zu diesen lokalen Endpunkten und gleichzeitiges Erzwingen Office 365 Verbindungen zur Verwendung von ExpressRoute stellt eine erhebliche Routingkomplexität dar. Für die große Mehrheit der Kunden, die solche komplexen Szenarien über ExpressRoute implementieren, wird aus betrieblichen Gründen nicht empfohlen. Dieser zusätzliche Aufwand umfasst das Verwalten der Risiken des asymmetrischen Routings und erfordert, dass Sie Ankündigungen und Richtlinien sorgfältig über mehrere Dimensionen hinweg verwalten.

### <a name="update-your-network-topology-plan-to-show-how-you-would-avoid-asymmetric-routes"></a>Aktualisieren Ihres Netzwerktopologieplans, um anzuzeigen, wie Sie asymmetrische Routen vermeiden würden
<a name="asymmetric"> </a>

Sie möchten asymmetrisches Routing vermeiden, um sicherzustellen, dass Personen in Ihrer Organisation nahtlos Office 365 sowie andere wichtige Dienste im Internet nutzen können. Es gibt zwei allgemeine Konfigurationen, die Kunden haben, die asymmetrisches Routing verursachen. Jetzt ist ein guter Zeitpunkt, um die Netzwerkkonfiguration zu überprüfen, die Sie verwenden möchten, und zu überprüfen, ob eines dieser asymmetrischen Routingszenarien vorhanden sein könnte.
  
Zunächst untersuchen wir einige verschiedene Situationen im Zusammenhang mit dem folgenden Netzwerkdiagramm. In diesem Diagramm befinden sich alle Server, die eingehende Anforderungen empfangen, z. B. ADFS oder lokale Hybridserver, im New Jersey-Rechenzentrum und werden im Internet angekündigt.
  
1. Während das Umkreisnetzwerk sicher ist, ist für eingehende Anforderungen keine Quell-NAT verfügbar.

2. Die Server im New Jersey-Rechenzentrum können sowohl Internet- als auch ExpressRoute-Routen anzeigen.

![Übersicht über expressRoute-Konnektivität](../media/8f074af6-ef38-44e8-bc5a-8b4d981fbb20.png)
  
Wir haben auch Vorschläge, wie sie behoben werden können.
  
#### <a name="problem-1-cloud-to-on-premises-connection-over-the-internet"></a>Problem 1: Cloud-zu-lokale Verbindung über das Internet
  
Das folgende Diagramm veranschaulicht den asymmetrischen Netzwerkpfad, der ausgeführt wird, wenn Ihre Netzwerkkonfiguration keine NAT für eingehende Anforderungen aus der Microsoft-Cloud über das Internet bereitstellt.
  
1. Die eingehende Anforderung von Office 365 ruft die IP-Adresse des lokalen Endpunkts aus öffentlichem DNS ab und sendet die Anforderung an Ihr Umkreisnetzwerk.

2. In dieser fehlerhaften Konfiguration ist keine Quell-NAT konfiguriert oder im Umkreisnetzwerk verfügbar, in dem der Datenverkehr gesendet wird, was dazu führt, dass die tatsächliche Quell-IP-Adresse als Rückgabeziel verwendet wird.

  - Der Server in Ihrem Netzwerk leitet den Rückgabedatenverkehr über eine beliebige verfügbare ExpressRoute-Netzwerkverbindung an Office 365 weiter.

  - Das Ergebnis ist ein asymmetrischer Pfad für diesen Fluss zu Office 365, was zu einer fehlerhaften Verbindung führt.

![ExpressRoute Asymetric Routing Problem 1](../media/9c210c2a-e0ea-4180-8ede-1bf41746ce7a.png)
  
##### <a name="solution-1a-source-nat"></a>Lösung 1a: Quell-NAT
  
Durch einfaches Hinzufügen einer Quell-NAT zur eingehenden Anforderung wird dieses falsch konfigurierte Netzwerk aufgelöst. Inhalt dieses Diagramms:
  
1. Die eingehende Anforderung wird weiterhin über das Umkreisnetzwerk des New Jersey-Rechenzentrums eingegeben. Dieses Mal ist die Quell-NAT verfügbar.

2. Die Antwort vom Server leitet zurück zur IP, die der Quell-NAT zugeordnet ist, anstelle der ursprünglichen IP-Adresse, was dazu führt, dass die Antwort entlang desselben Netzwerkpfads zurückgegeben wird.

![ExpressRoute Asymetric routing solution 1](../media/0e87a155-f8de-48ed-92ac-27367b727a82.png)
  
##### <a name="solution-1b-route-scoping"></a>Lösung 1b: Bereichsdefinition weiterleiten
  
Alternativ können Sie die Angabe der ExpressRoute-BGP-Präfixe nicht zulassen, indem Sie den alternativen Netzwerkpfad für diese Computer entfernen. Inhalt dieses Diagramms:
  
1. Die eingehende Anforderung wird weiterhin über das Umkreisnetzwerk des New Jersey-Rechenzentrums eingegeben. Dieses Mal sind die von Microsoft über den ExpressRoute-Kreis angekündigten Präfixe im New Jersey-Rechenzentrum nicht verfügbar.

2. Die Antwort vom Server wird zurück zu der IP geleitet, die der ursprünglichen IP-Adresse über die einzige verfügbare Route zugeordnet ist, was dazu führt, dass die Antwort entlang desselben Netzwerkpfads zurückgegeben wird.

![ExpressRoute Asymetric routing solution 2](../media/9cb4b2bf-7aa6-487a-bc02-e02af8a979f6.png)
  
#### <a name="problem-2-cloud-to-on-premises-connection-over-expressroute"></a>Problem 2: Cloud-zu-lokale Verbindung über ExpressRoute
  
Das folgende Diagramm veranschaulicht den asymmetrischen Netzwerkpfad, der ausgeführt wird, wenn Ihre Netzwerkkonfiguration keine NAT für eingehende Anforderungen von der Microsoft-Cloud über ExpressRoute bereitstellt.
  
1. Die eingehende Anforderung von Office 365 ruft die IP-Adresse von DNS ab und sendet die Anforderung an Ihr Umkreisnetzwerk.

2. In dieser fehlerhaften Konfiguration ist keine Quell-NAT konfiguriert oder im Umkreisnetzwerk verfügbar, in dem der Datenverkehr gesendet wird, was dazu führt, dass die tatsächliche Quell-IP-Adresse als Rückgabeziel verwendet wird.

  - Der Computer in Ihrem Netzwerk leitet den Rückgabedatenverkehr über eine beliebige verfügbare ExpressRoute-Netzwerkverbindung an Office 365 weiter.

  - Das Ergebnis ist eine asymmetrische Verbindung mit Office 365.

![ExpressRoute Asymetric Routing Problem 2](../media/f6fd155b-bbb7-472a-846e-039a99f09913.png)
  
##### <a name="solution-2-source-nat"></a>Lösung 2: Quell-NAT
  
Durch einfaches Hinzufügen einer Quell-NAT zur eingehenden Anforderung wird dieses falsch konfigurierte Netzwerk aufgelöst. Inhalt dieses Diagramms:
  
1. Die eingehende Anforderung wird weiterhin über das Umkreisnetzwerk des New York-Rechenzentrums eingegeben. Dieses Mal ist die Quell-NAT verfügbar.

2. Die Antwort vom Server leitet zurück zur IP, die der Quell-NAT zugeordnet ist, anstelle der ursprünglichen IP-Adresse, was dazu führt, dass die Antwort entlang desselben Netzwerkpfads zurückgegeben wird.

![ExpressRoute Asymetric routing solution 3](../media/a5d2b90d-a3ec-4047-afbf-6e6e99f376a7.png)
  
### <a name="paper-verify-that-the-network-design-has-path-symmetry"></a>Papier, um zu überprüfen, ob das Netzwerkdesign pfad symmetrisch ist

An diesem Punkt müssen Sie auf dem Papier überprüfen, ob Ihr Implementierungsplan Routen symmetrisch für die verschiedenen Szenarien bietet, in denen Sie Office 365 verwenden. Sie identifizieren die spezifische Netzwerkroute, die erwartet wird, wenn eine Person unterschiedliche Funktionen des Diensts verwendet. Vom lokalen Netzwerk und WAN-Routing über die Umkreisgeräte bis zum Verbindungspfad; ExpressRoute oder das Internet und an der Verbindung mit dem Onlineendpunkt.
  
Sie müssen dies für alle Office 365 Netzwerkdienste tun, die zuvor als Dienste identifiziert wurden, die Ihre Organisation übernehmen wird.
  
Es hilft bei diesem Papierspaziergang durch Routen mit einer zweiten Person. Erläutern Sie ihnen, von wo von jedem Netzwerkho hop die nächste Route erwartet wird, und stellen Sie sicher, dass Sie mit den Routingpfaden vertraut sind. Bedenken Sie, dass ExpressRoute immer eine umfassendere Route zu Microsoft-Server-IP-Adressen bereitstellt, wodurch die Routenkosten niedriger sind als bei einer Standardroute im Internet.
  
### <a name="design-client-connectivity-configuration"></a>Entwerfen der Clientkonnektivitätskonfiguration
<a name="asymmetric"> </a>

![Verwenden von PAC-Dateien mit ExpressRoute](../media/7cfa6482-dbae-416a-ae6f-a45e5f4de23b.png)
  
Wenn Sie einen Proxyserver für internetgebundenen Datenverkehr verwenden, müssen Sie pac- oder clientkonfigurationsdateien anpassen, um sicherzustellen, dass Clientcomputer in Ihrem Netzwerk ordnungsgemäß konfiguriert sind, um den ExpressRoute-Datenverkehr zu senden, den Sie Office 365 möchten, ohne Ihren Proxyserver zu übertragen, und der verbleibende Datenverkehr, einschließlich einiger Office 365 Datenverkehr, wird an den entsprechenden Proxy gesendet. Lesen Sie unseren Leitfaden zum [Verwalten von Office 365 Endpunkten,](./managing-office-365-endpoints.md) z. B. PAC-Dateien.
  
> [!NOTE]
> Die Endpunkte ändern sich häufig, so oft wie wöchentlich. Sie sollten nur Änderungen basierend auf den Diensten und Features vornehmen, die Ihre Organisation übernommen hat, um die Anzahl der Änderungen zu reduzieren, die Sie vornehmen müssen, um auf dem neuesten Stand zu bleiben. Achten Sie im RSS-Feed genau auf das Datum des **Gültigkeitsdatums,** an dem die Änderungen angekündigt werden und ein Datensatz aller früheren Änderungen, angekündigten IP-Adressen möglicherweise nicht angekündigt oder aus der Ankündigung entfernt wird, bis das Gültigkeitsdatum erreicht ist.
  
## <a name="build-your-deployment-and-testing-procedures"></a>Erstellen von Bereitstellungs- und Testverfahren
<a name="testing"> </a>

Ihr Implementierungsplan sollte sowohl Test- als auch Rollbackplanung umfassen. Wenn Ihre Implementierung nicht wie erwartet funktioniert, sollte der Plan so konzipiert sein, dass er sich auf die geringste Anzahl von Personen auswirkt, bevor Probleme erkannt werden. Es folgen einige allgemeine Grundsätze, die Ihr Plan berücksichtigen sollte.
  
1. Bereitstellen des Netzwerksegments und des Benutzerdienst-Onboardings, um Unterbrechungen zu minimieren.

2. Planen Sie das Testen von Routen mit Traceroute und TCP-Verbindung von einem separaten mit dem Internet verbundenen Host.

3. Vorzugsweise sollten Sie eingehende und ausgehende Dienste in einem isolierten Testnetzwerk mit einem Test-Office 365 Mandanten testen.

      - Alternativ können Tests in einem Produktionsnetzwerk durchgeführt werden, wenn der Kunde noch keine Office 365 verwendet oder sich im Pilotprojekt befindet.

      - Alternativ können Tests während eines Produktionsausfalls durchgeführt werden, der nur für Tests und Überwachung reserviert ist.

      - Alternativ können Tests durchgeführt werden, indem Routen für jeden Dienst auf jedem Layer-3-Routerknoten überprüft werden. Dieser Fallback sollte nur verwendet werden, wenn keine anderen Tests möglich sind, da ein Mangel an physischen Tests ein Risiko mit sich bringt.

### <a name="build-your-deployment-procedures"></a>Erstellen der Bereitstellungsverfahren

Ihre Bereitstellungsverfahren sollten schrittweise für kleine Gruppen von Personen bereitgestellt werden, damit Tests durchgeführt werden können, bevor sie für größere Personengruppen bereitgestellt werden. Es folgen mehrere Möglichkeiten zum Bereitstellen von ExpressRoute.
  
1. Richten Sie ExpressRoute mit Microsoft-Peering ein, und lassen Sie die Routenanzeige nur zu mehrstufigen Testzwecken an einen einzelnen Host weiterleiten.

2. Stellen Sie zunächst Routen zum ExpressRoute-Netzwerk zu einem einzelnen Netzwerksegment an, und erweitern Sie Routenanzeigen nach Netzwerksegment oder Region.

3. Wenn Sie Office 365 zum ersten Mal bereitstellen, verwenden Sie die ExpressRoute-Netzwerkbereitstellung als Pilotprojekt für eine kleine Anzahl von Personen.

4. Wenn Sie Proxyserver verwenden, können Sie alternativ eine PAC-Testdatei konfigurieren, um eine kleine Anzahl von Personen mit Tests und Feedback an ExpressRoute weiterzuleiten, bevor Sie weitere hinzufügen.

Der Implementierungsplan sollte die einzelnen Bereitstellungsverfahren auflisten, die ausgeführt werden müssen, oder Befehle, die zum Bereitstellen der Netzwerkkonfiguration verwendet werden müssen. Wenn der Netzwerkausfallzeitpunkt eingeht, sollten alle vorgenommenen Änderungen aus dem schriftlichen Bereitstellungsplan stammen, der im Voraus geschrieben und von Peers überprüft wurde. Sehen Sie sich unsere Anleitungen zur technischen Konfiguration von ExpressRoute an.
  
- Aktualisieren Ihrer SPF TXT-Einträge, wenn Sie IP-Adressen für lokale Server geändert haben, die weiterhin E-Mails senden.

- Aktualisieren von DNS-Einträgen für lokale Server, wenn Sie IP-Adressen für eine neue NAT-Konfiguration geändert haben.

- Stellen Sie sicher, dass Sie den RSS-Feed für Office 365 Endpunktbenachrichtigungen abonniert haben, um Routing- oder Proxykonfigurationen beizubehalten.

Nach Abschluss der ExpressRoute-Bereitstellung sollten die Verfahren im Testplan ausgeführt werden. Die Ergebnisse für jede Prozedur sollten protokolliert werden. Sie müssen Verfahren zum Zurücksetzen auf die ursprüngliche Produktionsumgebung in den Fall einschließen, dass die Testplanergebnisse angeben, dass die Implementierung nicht erfolgreich war.
  
### <a name="build-your-test-procedures"></a>Erstellen von Testprozeduren

Ihre Testprozeduren sollten Tests für jeden ausgehenden und eingehenden Netzwerkdienst für Office 365 sowohl, die ExpressRoute verwenden, als auch solche, die nicht verwendet werden. Die Verfahren sollten Tests von jedem eindeutigen Netzwerkstandort aus umfassen, einschließlich Benutzern, die nicht lokal im Unternehmens-LAN sind.
  
Beispiele für Testaktivitäten sind:
  
1. Pingen von Ihrem lokalen Router zu Ihrem Netzwerkoperatorrouter.

2. Überprüfen Sie, ob die Mehr als 500 Office 365 und CRM Online-IP-Adressanzeigen von Ihrem lokalen Router empfangen werden.

3. Überprüfen Sie, ob Die eingehende und ausgehende NAT zwischen ExpressRoute und dem internen Netzwerk ausgeführt wird.

4. Überprüfen Sie, ob Routen zu Ihrer NAT von Ihrem Router angekündigt werden.

5. Überprüfen Sie, ob ExpressRoute Ihre angekündigten Präfixe akzeptiert hat.

      - Verwenden Sie das folgende Cmdlet, um Peering-Ankündigungen zu überprüfen:

      ```PowerShell
      Get-AzureRmExpressRouteCircuitRouteTable -DevicePath Primary -ExpressRouteCircuitName TestER -ResourceGroupName RG -PeeringType MicrosoftPeering
      ```

6. Überprüfen Sie, ob Ihr öffentlicher NAT-IP-Bereich für Microsoft nicht über eine andere ExpressRoute- oder öffentliche Internetnetzwerkverbindung angekündigt wird, es sei denn, es handelt sich um eine bestimmte Teilmenge eines größeren Bereichs wie im vorherigen Beispiel.

7. ExpressRoute-Schaltungen sind gekoppelt und überprüfen, ob beide BGP-Sitzungen ausgeführt werden.

8. Richten Sie einen einzelnen Host innerhalb Ihrer NAT ein, und verwenden Sie Ping, Tracert und Tcpping, um die Konnektivität über den neuen Schaltkreis mit dem Host outlook.office365.com zu testen. Alternativ können Sie ein Tool wie Wireshark oder Microsoft Network Monitor 3.4 auf einem gespiegelten Port zum MSEE verwenden, um zu überprüfen, ob Sie eine Verbindung mit der IP-Adresse herstellen können, die outlook.office365.com zugeordnet ist.

9. Testen der Funktionalität auf Anwendungsebene für Exchange Online.

  - Testen Sie, Outlook eine Verbindung mit Exchange Online herstellen und E-Mails senden/empfangen kann.

  - Test Outlook den Onlinemodus verwenden kann.

  - Testen sie die Smartphone-Konnektivität und die Sende-/Empfangsfunktion.

10. Testen der Funktionalität auf Anwendungsebene für SharePoint Online

  - Testen Sie OneDrive for Business Synchronisierungsclient.

  - Testen sie SharePoint Online-Webzugriff.

11. Testen der Funktionalität auf Anwendungsebene für Skype for Business Anrufszenarien:

  - Teilnehmen an Einem Konferenzanruf als authentifizierter Benutzer [vom Endbenutzer initiierte Einladung]

  - Benutzer zur Telefonkonferenz einladen [von MCU gesendete Einladung]

  - Treten Sie der Konferenz als anonymer Benutzer mithilfe der Skype for Business Webanwendung bei.

  - Nehmen Sie an Anrufen von Ihrer kabelgebundenen PC-Verbindung, ihrem IP-Telefon und mobilen Gerät teil.

  - Anruf an Verbundbenutzer o Anruf bei PSTN-Überprüfung: Anruf ist abgeschlossen, Anrufqualität ist akzeptabel, Verbindungszeit ist akzeptabel.

  - Überprüfen Sie, ob der Anwesenheitsstatus für Kontakte sowohl für Mitglieder des Mandanten als auch für Verbundbenutzer aktualisiert wird.

### <a name="common-problems"></a>Häufig auftretende Probleme

Asymmetrisches Routing ist das häufigste Implementierungsproblem. Hier sind einige allgemeine Quellen, nach denen Gesucht werden sollte:
  
- Verwenden einer offenen oder flachen Netzwerkroutingtopologie ohne nat-Quelldaten.

- Verwenden Sie SNAT nicht zum Weiterleiten zu eingehenden Diensten über das Internet und ExpressRoute-Verbindungen.

- Keine Tests eingehender Dienste auf ExpressRoute in einem Testnetzwerk vor der allgemeinen Bereitstellung.

## <a name="deploying-expressroute-connectivity-through-your-network"></a>Bereitstellen der ExpressRoute-Konnektivität über Ihr Netzwerk
<a name="testing"> </a>

Stellen Sie die Bereitstellung für jeweils ein Segment des Netzwerks bereit, und stellen Sie die Konnektivität schrittweise für verschiedene Teile des Netzwerks bereit, und planen Sie ein Rollback für jedes neue Netzwerksegment. Wenn Ihre Bereitstellung an einer Office 365 Bereitstellung ausgerichtet ist, stellen Sie zuerst die Bereitstellung für Ihre Office 365 Pilotbenutzer bereit und erweitern Sie sie von dort aus.
  
Zuerst für Ihren Test und dann für die Produktion:
  
- Führen Sie die Bereitstellungsschritte aus, um ExpressRoute zu aktivieren.

- Testen Sie, ob die Netzwerkrouten wie erwartet sind.

- Führen Sie Tests für jeden eingehenden und ausgehenden Dienst durch.

- Rollback, wenn Sie Probleme feststellen.

### <a name="set-up-a-test-connection-to-expressroute-with-a-test-network-segment"></a>Einrichten einer Testverbindung mit ExpressRoute mit einem Testnetzwerksegment

Nachdem Sie nun den abgeschlossenen Plan auf dem Papier haben, ist es an der Zeit, einen kleinen Test durchzuführen. In diesem Test stellen Sie eine einzelne ExpressRoute-Verbindung mit Microsoft Peering mit einem Testsubnetz in Ihrem lokalen Netzwerk her. Sie können eine [Testversion Office 365 Mandanten](https://go.microsoft.com/fwlink/p/?LinkID=403802) mit Konnektivität zum und vom Testsubnetz konfigurieren und alle ausgehenden und eingehenden Dienste einschließen, die Sie in der Produktion im Testsubnetz verwenden werden. Richten Sie DNS für das Testnetzwerksegment ein, und richten Sie alle eingehenden und ausgehenden Dienste ein. Führen Sie Ihren Testplan aus, und stellen Sie sicher, dass Sie mit dem Routing für jeden Dienst und der Routenverteilung vertraut sind.
  
### <a name="execute-the-deployment-and-test-plans"></a>Ausführen der Bereitstellungs- und Testpläne

Wenn Sie die oben beschriebenen Elemente abschließen, überprüfen Sie die bereiche, die Sie abgeschlossen haben, und stellen Sie sicher, dass Sie und Ihr Team diese überprüft haben, bevor Sie Ihre Bereitstellungs- und Testpläne ausführen.
  
- Liste der ausgehenden und eingehenden Dienste, die an der Netzwerkänderung beteiligt sind.

- Diagramm der globalen Netzwerkarchitektur, das sowohl den Internetausgang als auch ExpressRoute-Besprechungsorte zeigt.

- Diagramm für das Netzwerkrouting, das die verschiedenen Netzwerkpfade veranschaulicht, die für jeden bereitgestellten Dienst verwendet werden.

- Ein Bereitstellungsplan mit Schritten zum Implementieren der Änderungen und ggf. eines Rollbacks.

- Ein Testplan zum Testen der einzelnen Office 365 und Netzwerkdienste.

- Überprüfung der Produktionsrouten für eingehende und ausgehende Dienste abgeschlossen.

- Ein abgeschlossener Test in einem Testnetzwerksegment einschließlich Verfügbarkeitstests.

Wählen Sie ein Ausfallfenster aus, das lang genug ist, um den gesamten Bereitstellungsplan und den Testplan auszuführen, für die Problembehandlung und bei Bedarf Zeit für ein Rollback zur Verfügung steht.
  
> [!CAUTION]
> Aufgrund der komplexen Art des Routings über das Internet und ExpressRoute wird empfohlen, diesem Fenster zusätzliche Pufferzeit hinzuzufügen, um die Problembehandlung bei komplexem Routing zu behandeln.
  
### <a name="configure-qos-for-skype-for-business-online"></a>Konfigurieren von QoS für Skype for Business Online

QoS ist erforderlich, um Sprach- und Besprechungsvorteile für Skype for Business Online zu erhalten. Sie können QoS konfigurieren, nachdem Sie sichergestellt haben, dass die ExpressRoute-Netzwerkverbindung keinen Anderen Office 365 Dienstzugriff blockiert. Die Konfiguration für QoS wird im Artikel [ExpressRoute und QoS in Skype for Business Online](https://support.office.com/article/ExpressRoute-and-QoS-in-Skype-for-Business-Online-20c654da-30ee-4e4f-a764-8b7d8844431d) beschrieben.
  
## <a name="troubleshooting-your-implementation"></a>Problembehandlung bei der Implementierung
<a name="troubleshooting"> </a>

Sehen Sie sich zunächst die Schritte in diesem Implementierungshandbuch an, wurden sie in Ihrem Implementierungsplan übersehen? Gehen Sie zurück, und führen Sie nach Möglichkeit weitere kleine Netzwerktests aus, um den Fehler zu replizieren und ihn dort zu debuggen.
  
Ermitteln Sie, welche eingehenden oder ausgehenden Dienste während der Tests fehlgeschlagen sind. Rufen Sie speziell die IP-Adressen und Subnetze für jeden fehlgeschlagenen Dienst ab. Gehen Sie voran, und führen Sie das Diagramm der Netzwerktopologie auf Papier durch, und überprüfen Sie das Routing. Überprüfen Sie genau, wo das ExpressRoute-Routing angekündigt wird, testen Sie dieses Routing während des Ausfalls nach Möglichkeit mit Ablaufverfolgungen.
  
Führen Sie PSPing mit einer Netzwerkablaufverfolgung zu jedem Kundenendpunkt aus, und werten Sie Quell- und Ziel-IP-Adressen aus, um zu überprüfen, ob sie wie erwartet sind. Führen Sie Telnet auf einem beliebigen E-Mail-Host aus, den Sie an Port 25 verfügbar machen, und stellen Sie sicher, dass SNAT die ursprüngliche Quell-IP-Adresse ausblendet, wenn dies erwartet wird.
  
Beachten Sie, dass Sie beim Bereitstellen von Office 365 mit einer ExpressRoute-Verbindung sicherstellen müssen, dass sowohl die Netzwerkkonfiguration für ExpressRoute optimal gestaltet ist als auch die anderen Komponenten in Ihrem Netzwerk optimiert wurden, z. B. Clientcomputer. Zusätzlich zur Verwendung dieses Planungshandbuchs zur Problembehandlung der möglicherweise verpassten Schritte haben wir auch einen [Plan zur Leistungsbehandlung für Office 365](https://support.office.com/article/Performance-troubleshooting-plan-for-Office-365-e241e5d9-b1d8-4f1d-a5c8-4106b7325f8c) geschrieben.
  
Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/implementexpressroute365]()
  
## <a name="related-topics"></a>Verwandte Themen

[Bewerten der Office 365-Netzwerkkonnektivität](assessing-network-connectivity.md)
  
[Azure ExpressRoute für Office 365](azure-expressroute.md)
  
[Verwalten von ExpressRoute für Office 365-Verbindungen](managing-expressroute-for-connectivity.md)
  
[Routing mit ExpressRoute für Office 365](routing-with-expressroute.md)
  
[Netzwerkplanung mit ExpressRoute für Office 365](network-planning-with-expressroute.md)
  
[Verwenden von BGP-Communitys in ExpressRoute für Office 365 Szenarien](bgp-communities-in-expressroute.md)
  
[Medienqualität und Netzwerkverbindungsleistung in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimieren Ihres Netzwerks für Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)
  
[ExpressRoute und QoS in Skype for Business Online](https://support.office.com/article/20c654da-30ee-4e4f-a764-8b7d8844431d)
  
[Anruffluss mit ExpressRoute](https://support.office.com/article/413acb29-ad83-4393-9402-51d88e7561ab)
  
[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](performance-tuning-using-baselines-and-history.md)
  
[Plan zur Problembehandlung für Office 365](performance-troubleshooting-plan.md)
  
[URLs und IP-Adressbereiche für Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Office 365-Netzwerk- und Leistungsoptimierung](network-planning-and-performance.md)
