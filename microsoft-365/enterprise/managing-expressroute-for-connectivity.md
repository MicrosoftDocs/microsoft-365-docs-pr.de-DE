---
title: Verwalten von ExpressRoute für Office 365-Verbindungen
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 7/13/2017
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid:
- MET150
- BCS160
ms.assetid: e4468915-15e1-4530-9361-cd18ce82e231
description: Erfahren Sie, wie Sie ExpressRoute für Office 365 verwalten, einschließlich der öffentlichen Bereiche für die Konfiguration wie Präfixfilterung, Sicherheit und Compliance.
ms.openlocfilehash: e8de0763df7d592bc41802b1ead48df06891e6dc
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50916668"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Verwalten von ExpressRoute für Office 365-Verbindungen

ExpressRoute für Office 365 bietet einen alternativen Routingpfad, um viele Office 365-Dienste zu erreichen, ohne dass der datenverkehr zum Ableiten in das Internet benötigt wird. Obwohl die Internetverbindung zu Office 365 weiterhin benötigt wird, werden die von Microsoft über BGP an Ihr Netzwerk angekündigten spezifischen Routen die direkte ExpressRoute-Schaltung bevorzugt, es sei denn, es gibt andere Konfigurationen in Ihrem Netzwerk. Zu den drei öffentlichen Bereichen, die Sie für die Verwaltung dieses Routings konfigurieren möchten, gehören Präfixfilterung, Sicherheit und Compliance.
  
> [!NOTE]
> Microsoft hat geändert, wie die Microsoft Peering-Routingdomäne für Azure ExpressRoute überprüft wird. Ab dem 31. Juli 2017 können alle Azure ExpressRoute-Kunden Microsoft Peering direkt über die Azure Administrative Konsole oder über PowerShell aktivieren. Nach der Aktivierung von Microsoft Peering kann jeder Kunde Routenfilter erstellen, um BGP-Routenanzeigen für Dynamics 365 Customer Engagement-Anwendungen (früher crm Online) zu erhalten. Kunden, die Azure ExpressRoute für Office 365 benötigen, müssen eine Überprüfung von Microsoft erhalten, bevor sie Routenfilter für Office 365 erstellen können. Wenden Sie sich an Ihr Microsoft-Konto-Team, um zu erfahren, wie Sie eine Überprüfung zum Aktivieren von Office 365 ExpressRoute anfordern. Nicht autorisierte Abonnements, die Routenfilter für Office 365 erstellen möchten, erhalten [eine Fehlermeldung.](https://support.microsoft.com/kb/3181709)
  
## <a name="prefix-filtering"></a>Präfixfilterung

Microsoft empfiehlt Kunden, alle von Microsoft angekündigten BGP-Routen zu akzeptieren. Die bereitgestellten Routen werden einem strengen Überprüfungs- und Überprüfungsprozess unterzogen, ohne dass vorteile für zusätzliche Überprüfungen vorhanden sind. ExpressRoute bietet nativ die empfohlenen Steuerelemente wie Ip-Präfixbesitz, Integrität und Skalierung – ohne eingehende Routenfilterung auf Kundenseite.
  
Wenn Sie eine zusätzliche Überprüfung des Routenbesitzes im öffentlichen ExpressRoute-Peering benötigen, können Sie die angekündigten Routen mit der Liste aller IPv4- und IPv6-IP-Präfixe überprüfen, die die öffentlichen IP-Bereiche von [Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)darstellen. Diese Bereiche decken den vollständigen Microsoft-Adressraum ab und ändern sich selten, da eine zuverlässige Reihe von Bereichen, nach denen gefiltert werden soll, auch zusätzlichen Schutz für Kunden bietet, die sich sorgen, dass Routen, die nicht von Microsoft gehören, in ihrer Umgebung undicht sind. Für den Fall, dass eine Änderung vor liegt, wird sie am 1. des Monats vorgenommen, und die Versionsnummer im Detailabschnitt der Seite ändert sich jedes Mal, wenn die Datei aktualisiert wird. 
  
Es gibt eine Reihe von Gründen, die Verwendung der [Office 365-URLs](./urls-and-ip-address-ranges.md) und IP-Adressbereiche zum Generieren von Präfixfilterlisten zu vermeiden. Einschließlich der folgenden:
  
- Die Office 365-IP-Präfixe werden häufig geändert.

- Die UrLs und IP-Adressbereiche von Office 365 sind für die Verwaltung von Firewall-Zulässigen Listen und Proxyinfrastrukturen konzipiert, nicht für das Routing.

- Die Office 365-URLs und -IP-Adressbereiche umfassen keine anderen Microsoft-Dienste, die möglicherweise für Ihre ExpressRoute-Verbindungen verfügbar sind.

|**Option**|**Komplexität**|**Änderungssteuerung**|
|:-----|:-----|:-----|
|Akzeptieren aller Microsoft-Routen  <br/> |**Niedrig:** Der Kunde verlässt sich auf Microsoft-Steuerelemente, um sicherzustellen, dass alle Routen ordnungsgemäß im Besitz sind.  <br/> |Keine  <br/> |
|Filtern von Microsoft-eigenen Supernets  <br/> |**Mittel:** Der Kunde implementiert zusammengefasste Präfixfilterlisten, um nur microsofteigene Routen zu erlauben.  <br/> |Kunden müssen sicherstellen, dass die unregelmäßigen Updates in Routenfiltern angezeigt werden.  <br/> |
|Filtern von Office 365-IP-Bereichen  <br/> [!CAUTION] Not-Recommended |**Hoch:** Der Kunde filtert Routen basierend auf definierten Office 365-IP-Präfixen.  <br/> |Kunden müssen einen robusten Änderungsverwaltungsprozess für die monatlichen Updates implementieren.  <br/> [!CAUTION] Diese Lösung erfordert erhebliche änderungen. Änderungen, die nicht in der Zeit implementiert werden, führen wahrscheinlich zu einem Dienstausfall.   |

Die Verbindung mit Office 365 mithilfe von Azure ExpressRoute basiert auf BGP-Ankündigungen bestimmter IP-Subnetze, die Netzwerke darstellen, in denen Office 365-Endpunkte bereitgestellt werden. Aufgrund des globalen Charakters von Office 365 und der Anzahl der Dienste, aus der Office 365 ist, müssen Kunden häufig die Inserate verwalten, die sie in ihrem Netzwerk annehmen. Wenn Sie sich Gedanken über die Anzahl der in [](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) Ihrer Umgebung angekündigten Präfixe machen, können Sie mit dem BGP-Communityfeature die Ankündigungen nach einem bestimmten Satz von Office 365-Diensten filtern. Dieses Feature befindet sich jetzt in der Vorschau.
  
Unabhängig davon, wie Sie die BGP-Routenanzeigen verwalten, die von Microsoft kommen, erhalten Sie keine besondere Belastung für Office 365-Dienste, wenn Sie eine Verbindung mit Office 365 über eine Internetschaltung allein herstellen. Microsoft behält die gleichen Sicherheits-, Compliance- und Leistungsstufen bei, unabhängig davon, welche Art von Schaltung ein Kunde zum Herstellen einer Verbindung mit Office 365 verwendet.
  
### <a name="security"></a>Sicherheit

Microsoft empfiehlt, eigene Netzwerk- und Sicherheitsperimeterkontrollen für Verbindungen zu und von öffentlichen ExpressRoute- und Microsoft-Peerings zu verwalten, die Verbindungen zu und von Office 365-Diensten umfassen. Sicherheitskontrollen sollten für Netzwerkanforderungen vorhanden sein, die ausgehend von Ihrem Netzwerk in das Netzwerk von Microsoft und von Microsofts Netzwerk in Ihr Netzwerk ein- und ausgehend sind.
  
#### <a name="outbound-from-customer-to-microsoft"></a>Ausgehend vom Kunden zu Microsoft
  
Wenn Computer eine Verbindung mit Office 365 herstellen, stellen sie eine Verbindung mit demselben Satz von Endpunkten unabhängig davon, ob die Verbindung über ein Internet oder eine ExpressRoute-Verbindung hergestellt wird. Unabhängig von der verwendeten Schaltung empfiehlt Microsoft, Office 365-Dienste als vertrauenswürdiger als generische Internetziele zu behandeln. Ihre ausgehenden Sicherheitssteuerelemente sollten sich auf die Ports und Protokolle konzentrieren, um die Gefährdung zu reduzieren und die laufende Wartung zu minimieren. Die erforderlichen Portinformationen sind im [Office 365-Referenzartikel](./urls-and-ip-address-ranges.md) für Endpunkte verfügbar.
  
Für hinzugefügte Steuerelemente können Sie die FQDN-Filterung in Ihrer Proxyinfrastruktur verwenden, um einige oder alle Netzwerkanforderungen einzuschränken oder zu überprüfen, die für das Internet oder Office 365 bestimmt sind. Die Verwaltung der Liste der FQDNs bei der Veröffentlichung von Features und der Weiterentwicklung der Office 365-Angebote erfordert eine stabilere Änderungsverwaltung und nachverfolgung von Änderungen an den veröffentlichten [Office 365-Endpunkten.](./urls-and-ip-address-ranges.md)
  
> [!CAUTION]
> Microsoft empfiehlt, dass Sie sich nicht ausschließlich auf IP-Präfixe verlassen, um die ausgehende Sicherheit für Office 365 zu verwalten.

|**Option**|**Komplexität**|**Änderungssteuerung**|
|:-----|:-----|:-----|
|Keine Einschränkungen  <br/> |**Niedrig:** Der Kunde ermöglicht uneingeschränkten ausgehenden Zugriff auf Microsoft.  <br/> |Keine  <br/> |
|Porteinschränkungen  <br/> |**Niedrig:** Der Kunde schränkt den ausgehenden Zugriff auf Microsoft über die erwarteten Ports ein.  <br/> |Selten.  <br/> |
|FQDN-Einschränkungen  <br/> |**Hoch:** Der Kunde schränkt ausgehenden Zugriff auf Office 365 basierend auf den veröffentlichten FQDNs ein.  <br/> |Monatliche Änderungen.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Eingehende Nachrichten von Microsoft zum Kunden
  
Es gibt mehrere optionale Szenarien, in denen Microsoft Verbindungen mit Ihrem Netzwerk initiieren muss.
  
- ADFS während der Kennwortüberprüfung für die Anmeldung.

- [Exchange Server Hybridbereitstellungen](/exchange/exchange-hybrid).

- E-Mails von einem Exchange Online-Mandanten an einen lokalen Host.

- SharePoint Online-E-Mails, die von SharePoint Online an einen lokalen Host gesendet werden.

- [SharePoint-Verbundhybridsuche](/SharePoint/hybrid/display-hybrid-federated-search-results-in-sharepoint-online).

- [SharePoint-Hybrid-BCS](/SharePoint/hybrid/deploy-a-business-connectivity-services-hybrid-solution).

- [Skype for Business Hybrid-](/skypeforbusiness/hybrid/plan-hybrid-connectivity?bc=%2fSkypeForBusiness%2fbreadcrumb%2ftoc.json&toc=%2fSkypeForBusiness%2ftoc.json) und/oder [Skype for Business-Verbund](/office365/servicedescriptions/skype-for-business-online-service-description/skype-for-business-online-features).

- [Skype for Business Cloud Connector](/skypeforbusiness/skype-for-business-hybrid-solutions/plan-your-phone-system-cloud-pbx-solution/plan-skype-for-business-cloud-connector-edition).

Microsoft empfiehlt, diese Verbindungen über Ihre Internetverbindung anstelle Ihrer ExpressRoute-Schaltung zu akzeptieren, um die Komplexität zu reduzieren. Wenn Ihre Compliance- oder Leistungsanforderungen diese eingehenden Verbindungen über eine ExpressRoute-Schaltung erfordern, wird die Verwendung einer Firewall oder eines Reverseproxys für den Bereich der akzeptierten Verbindungen empfohlen. Sie können die [Office 365-Endpunkte](./urls-and-ip-address-ranges.md) verwenden, um die richtigen FQDNs und IP-Präfixe zu finden.
  
### <a name="compliance"></a>Compliance

Wir verlassen uns nicht auf den Routingpfad, den Sie für unsere Compliancesteuerelemente verwenden. Unabhängig davon, ob Sie eine Verbindung mit Office 365-Diensten über eine ExpressRoute- oder Internetleitung herstellen, ändern sich unsere Compliancesteuerelemente nicht. Sie sollten die verschiedenen Compliance- und Sicherheitszertifizierungsstufen für Office 365 überprüfen, um die beste Wahl für die Erfüllung der Anforderungen Ihrer Organisation zu finden.
  
Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/manageexpressroute365]()
  
## <a name="related-topics"></a>Verwandte Themen

[Netzwerke für die Inhaltsübermittlung](content-delivery-networks.md)
  
[URLs und IP-Adressbereiche für Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Schulung zu Azure ExpressRoute für Office 365](https://channel9.msdn.com/series/aer)