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
description: Erfahren Sie, wie Sie Express Route für Office 365 verwalten, einschließlich allgemeiner Bereiche für die Konfiguration wie Präfix Filterung, Sicherheit und Compliance.
ms.openlocfilehash: 5b55150b91b68954cb7b701afb7cf46ab9b951dd
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690887"
---
# <a name="managing-expressroute-for-office-365-connectivity"></a>Verwalten von ExpressRoute für Office 365-Verbindungen

Express Route für Office 365 bietet einen alternativen Routingpfad zum erreichen vieler Office 365 Dienste, ohne dass der gesamte Datenverkehr zum Ausstieg ins Internet erforderlich ist. Auch wenn die Internetverbindung mit Office 365 noch benötigt wird, wird die direkte Express Route-Schaltung durch die spezifischen Routen, die von Microsoft über BGP in Ihrem Netzwerk beworben werden, bevorzugt, es sei denn, es sind andere Konfigurationen in Ihrem Netzwerk vorhanden. Die drei allgemeinen Bereiche, die Sie für die Verwaltung dieses Routings konfigurieren können, sind Präfix Filterung, Sicherheit und Compliance.
  
> [!NOTE]
> Microsoft hat geändert, wie die Microsoft Peering-Routingdomäne für Azure Express Route überprüft wird. Ab dem 31. Juli 2017 können alle Azure Express Route-Kunden Microsoft Peering direkt über die Azure-Verwaltungskonsole oder über PowerShell aktivieren. Nachdem Microsoft Peering aktiviert wurde, kann jeder Kunde Routenfilter erstellen, um BGP-Routenankündigungen für Dynamics 365-Kunden Bindungs Anwendungen (ehemals CRM Online genannt) zu erhalten. Kunden, die Azure Express Route für Office 365 benötigen, müssen eine Überprüfung von Microsoft erhalten, bevor Sie Routenfilter für Office 365 erstellen können. Wenden Sie sich an Ihr Microsoft-Konto Team, um mehr darüber zu erfahren, wie Sie eine Überprüfung anfordern, um Office 365 Express Route zu aktivieren. Nicht autorisierte Abonnements beim Erstellen von Routenfiltern für Office 365 wird eine [Fehlermeldung](https://support.microsoft.com/kb/3181709) angezeigt.
  
## <a name="prefix-filtering"></a>Präfix Filterung

Microsoft empfiehlt, dass Kunden alle BGP-Routen wie von Microsoft ausgeschrieben akzeptieren, die bereitgestellten Routen unterliegeneiner rigorosen Überprüfung und einem Validierungsprozess, wodurch jegliche Vorteile für die hinzugefügte Prüfung entfernt werden. Express Route bietet nativ die empfohlenen Steuerelemente wie IP-Präfix-Besitz, Integrität und Skalierung-ohne eingehende Routen Filterung auf Kundenseite.
  
Wenn Sie eine zusätzliche Überprüfung des Routen Besitzes in Express Route Public Peering benötigen, können Sie die angekündigten Routen anhand der Liste aller IPv4-und IPv6-IP-Präfixe überprüfen, die die [öffentlichen IP-Bereiche von Microsoft](https://www.microsoft.com/download/details.aspx?id=53602)darstellen. Diese Bereiche decken den vollständigen Microsoft-Adressraum ab und ändern sich selten, sodass ein zuverlässiger Bereich von Bereichen zum Filtern bereitgestellt wird, der auch zusätzlichen Schutz für Kunden mit sich bringt, die sich um nicht von Microsoft befasste Routen in Ihrer Umgebung kümmern. Für den Fall, dass eine Änderung vorliegt, wird Sie am 1. des Monats vorgenommen, und die Versionsnummer im Abschnitt **Details** der Seite ändert sich jedes Mal, wenn die Datei aktualisiert wird.
  
Es gibt eine Reihe von Gründen, um die Verwendung der [Office 365-URLs und IP-Adressbereiche](https://aka.ms/o365endpoints) zum Generieren von Präfixfilter Listen zu vermeiden. Einschließlich der folgenden:
  
- Die Office 365 IP-Präfixe werden häufig von Änderungen unterzogen.

- Die Office 365-URLs und IP-Adressbereiche sind für die Verwaltung von Firewall-Zulassungslisten und Proxy-Infrastrukturen, nicht für Routing vorgesehen.

- Die Office 365-URLs und IP-Adressbereiche beziehen sich nicht auf andere Microsoft-Dienste, die möglicherweise im Bereich ihrer Express Route-Verbindungen liegen.

|**Option**|**Komplexität**|**Änderungs Steuerelement**|
|:-----|:-----|:-----|
|Alle Microsoft-Routen akzeptieren  <br/> |**Niedrig:** Der Kunde verwendet Microsoft-Steuerelemente, um sicherzustellen, dass alle Routen ordnungsgemäß im Besitz sind.  <br/> |Keine  <br/> |
|Microsoft-besessene supernets Filtern  <br/> |**Mittel:** Kunden implementiert zusammengefasste Präfixfilter Listen, um nur Microsoft-eigene Routen zuzulassen.  <br/> |Kunden müssen sicherstellen, dass die seltenen Aktualisierungen in Routenfiltern wiedergegeben werden.  <br/> |
|Filtern Office 365 IP-Bereichen  <br/> [!CAUTION] Nicht empfohlen |**Hoch:** Kunden filtert Routen basierend auf definierten Office 365 IP-Präfixen.  <br/> |Kunden müssen einen robusten Änderungsverwaltungsprozess für die monatlichen Updates implementieren.  <br/> [!CAUTION] Diese Lösung erfordert wichtige fortlaufende Änderungen. Änderungen, die nicht rechtzeitig implementiert werden, führen wahrscheinlich zu einem Dienstausfall.   |

Das Herstellen einer Verbindung mit Office 365 mithilfe von Azure Express Route basiert auf BGP-Ankündigungen bestimmter IP-Subnetze, die Netzwerke darstellen, in denen Office 365 Endpunkte bereitgestellt werden. Aufgrund des globalen Charakters von Office 365 und der Anzahl von Diensten, aus denen Office 365 besteht, müssen Kunden häufig die Ankündigungen verwalten, die Sie in Ihrem Netzwerk annehmen. Wenn Sie sich mit der Anzahl der in Ihrer Umgebung beworbenen Präfixe befassen, können Sie mit dem [BGP-Community](https://support.office.com/article/Using-BGP-communities-in-ExpressRoute-for-Office-365-scenarios-preview-9ac4d7d4-d9f8-40a8-8c78-2a6d7fe96099) -Feature die Ankündigungen auf eine bestimmte Gruppe von Office 365 Diensten filtern. Dieses Feature befindet sich jetzt in der Vorschau.
  
Unabhängig davon, wie Sie die BGP-Routenankündigungen von Microsoft verwalten, erhalten Sie keine besondere Exposition gegenüber Office 365 Diensten, wenn Sie mit dem Herstellen einer Verbindung mit Office 365 über eine Internet Schaltung allein verbunden sind. Microsoft behält die gleichen Sicherheits-, Compliance-und Leistungsstufen unabhängig von der Art der Schaltung, die ein Kunde verwendet, um eine Verbindung mit Office 365 herzustellen.
  
### <a name="security"></a>Sicherheit

Microsoft empfiehlt, dass Sie Ihre eigenen Netzwerk-und Sicherheitsperimeter-Steuerelemente für Verbindungen zu und von Express Route Public und Microsoft Peering verwalten, einschließlich Verbindungen zu und von Office 365 Diensten. Für Netzwerkanforderungen, die ausgehend von Ihrem Netzwerk zum Microsoft-Netzwerk Reisen, sowie das eingehende aus dem Netzwerk von Microsoft in Ihr Netzwerk müssen Sicherheitskontrollen eingerichtet werden.
  
#### <a name="outbound-from-customer-to-microsoft"></a>Ausgehend vom Kunden an Microsoft
  
Wenn Computer eine Verbindung mit Office 365 herstellen, stellen Sie eine Verbindung mit demselben Endpunkt her, unabhängig davon, ob die Verbindung über eine Internet-oder Express Route-Schaltung hergestellt wird. Unabhängig von der verwendeten Schaltung empfiehlt Microsoft, dass Sie Office 365 Dienste als vertrauenswürdiger als generische Internet Ziele behandeln. Ihre ausgehenden Sicherheitskontrollen sollten sich auf die Ports und Protokolle konzentrieren, um die Belichtung zu reduzieren und die laufende Wartung zu minimieren. Die erforderlichen Portinformationen sind im Referenzartikel zu [Office 365 Endpunkten](https://aka.ms/o365endpoints) verfügbar.
  
Für hinzugefügte Steuerelemente können Sie die Filterung auf FQDN-Ebene in ihrer Proxy Infrastruktur zum einschränken oder überprüfen einiger oder aller Netzwerkanforderungen verwenden, die für das Internet oder Office 365 bestimmt sind. Das Verwalten der Liste der FQDNs, wenn Features veröffentlicht werden, und das Entwickeln der Office 365 Angebote erfordern eine robustere Änderungsverwaltung und Nachverfolgung von Änderungen an den veröffentlichten [Office 365 Endpunkten](https://aka.ms/o365endpoints).
  
> [!CAUTION]
> Microsoft empfiehlt, dass Sie sich nicht ausschließlich auf IP-Präfixe verlassen, um die ausgehende Sicherheit für Office 365 zu verwalten.

|**Option**|**Komplexität**|**Änderungs Steuerelement**|
|:-----|:-----|:-----|
|Keine Einschränkungen  <br/> |**Niedrig:** Der Kunde ermöglicht den uneingeschränkten ausgehenden Zugriff auf Microsoft.  <br/> |Keine  <br/> |
|Port Einschränkungen  <br/> |**Niedrig:** Der Kunde schränkt den ausgehenden Zugriff auf Microsoft durch die erwarteten Ports ein.  <br/> |Selten.  <br/> |
|FQDN-Einschränkungen  <br/> |**Hoch:** Der Kunde schränkt den ausgehenden Zugriff auf Office 365 basierend auf den veröffentlichten FQDNs ein.  <br/> |Monatliche Änderungen.  <br/> |

#### <a name="inbound-from-microsoft-to-customer"></a>Eingehend von Microsoft an den Kunden
  
Es gibt verschiedene optionale Szenarien, in denen Microsoft Verbindungen mit Ihrem Netzwerk initiieren muss.
  
- ADFS während der Kennwortüberprüfung für die Anmeldung.

- [Exchange Server Hybrid Bereitstellungen](https://technet.microsoft.com/library/jj200581%28v=exchg.150%29.aspx).

- E-Mail von einem Exchange Online-Mandanten an einen lokalen Host.

- SharePoint Online von e-Mail-Nachrichten von SharePoint Online an einen lokalen Host senden.

- [SharePoint-Verbund Hybrid Suche](https://technet.microsoft.com/library/dn197174.aspx).

- [SharePoint-Hybrid-BCS](https://technet.microsoft.com/library/dn197239.aspx ).

- [Skype for Business Hybrid](https://technet.microsoft.com/library/jj205403.aspx) -und/oder [Skype for Business-Verbund](https://technet.microsoft.com/library/skype-for-business-online-federation-and-public-im-conectivity.aspx).

- [Skype for Business Cloud Connector](https://technet.microsoft.com/library/mt605227.aspx ).

Microsoft empfiehlt, dass Sie diese Verbindungen über Ihren Internet Stromkreis anstelle Ihres Express Route-Circuits akzeptieren, um die Komplexität zu verringern. Wenn Ihre Konformitäts-oder Leistungsanforderungen diese eingehenden Verbindungen müssen über eine Express Route-Schaltung akzeptiert werden, wobei die Verwendung einer Firewall oder eines Reverse-Proxys zum Bereich der akzeptierten Verbindungen empfohlen wird. Sie können die [Office 365 Endpunkte](https://aka.ms/o365endpoints) verwenden, um die richtigen FQDNs und IP-Präfixe herauszufinden.
  
### <a name="compliance"></a>Compliance

Wir verlassen uns nicht auf den Routingpfad, den Sie für unsere Compliance-Steuerelemente verwenden. Unabhängig davon, ob Sie über eine Express Route-oder Internet Schaltung eine Verbindung mit Office 365 Diensten herstellen, werden sich unsere Konformitätskontrollen nicht ändern. Sie sollten die verschiedenen Konformitäts-und Sicherheits Zertifizierungsstufen für Office 365 überprüfen, um die beste Wahl zu finden, um die Anforderungen Ihrer Organisation zu erfüllen.
  
Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/manageexpressroute365](https://aka.ms/manageexpressroute365)
  
## <a name="related-topics"></a>Verwandte Themen

[Netzwerke für die Inhaltsübermittlung](content-delivery-networks.md)
  
[URLs und IP-Adressbereiche für Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)
  
[Verwalten von Office 365-Endpunkten](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)
  
[Schulung zu Azure ExpressRoute für Office 365](https://channel9.msdn.com/series/aer)
