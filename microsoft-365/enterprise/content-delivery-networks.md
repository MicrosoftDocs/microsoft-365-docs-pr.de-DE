---
title: Netzwerke für die Inhaltsübermittlung
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 0140f704-6614-49bb-aa6c-89b75dcd7f1f
description: Verwenden Sie diese Informationen, um zu erfahren, wie Office 365 content delivery Networks (CDNs) verwendet, um die Leistung zu verbessern.
ms.openlocfilehash: 1a963d14df14e8644072a159e35c8590f953dae6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911096"
---
# <a name="content-delivery-networks-cdns"></a>Netzwerke für die Inhaltsübermittlung (CDNs)

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

CDNs helfen, Office 365 für Endbenutzer schnell und zuverlässig zu halten. Clouddienste wie Office 365 verwenden CDNs, um statische Objekte näher an den Browsern zwischenspeichern, die sie anfordern, um Downloads zu beschleunigen und die wahrgenommene Wartezeit für Endbenutzer zu reduzieren. Die Informationen in diesem Thema helfen Ihnen, mehr über Inhaltszustellungsnetzwerke (Content Delivery Networks, CDNs) und deren Verwendung durch Office 365.

## <a name="what-exactly-is-a-cdn"></a>Was genau ist ein CDN?

Ein CDN ist ein geografisch verteiltes Netzwerk, das aus Proxy- und Dateiservern in Rechenzentren besteht, die über Hochgeschwindigkeits-Backbonenetzwerke verbunden sind. CDNs werden verwendet, um Wartezeiten und Ladezeiten für eine bestimmte Gruppe von Dateien und Objekten in einer Website oder einem Dienst zu reduzieren. Ein CDN kann viele Tausend Endpunkte für eine optimale Wartung eingehender Anforderungen von jedem Beliebigen Standort haben.

CDNs werden häufig verwendet, um schnellere Downloads generischer Inhalte für eine Website oder einen Dienst wie Javascript-Dateien, Symbole und Bilder zu ermöglichen und können auch privaten Zugriff auf Benutzerinhalte wie Dateien in SharePoint Online-Dokumentbibliotheken, Streamingmediendateien und benutzerdefiniertem Code bieten.

CDNs werden von den meisten Unternehmens-Clouddiensten verwendet. Clouddienste wie Office 365 millionen von Kunden, die eine Mischung aus proprietären Inhalten (z. B. E-Mails) und generischen Inhalten (z. B. Symbolen) gleichzeitig herunterladen. Es ist effizienter, Bilder, die von allen Benutzern verwendet werden, wie z. B. Symbole, so nah wie möglich am Computer des Benutzers zu stellen. Es ist nicht für jeden Clouddienst praktisch, CDN Rechenzentren zu erstellen, die diese generischen Inhalte in jedem Großraum oder sogar in jedem wichtigen Internethub auf der ganzen Welt speichern, sodass einige dieser CDNs freigegeben werden.

## <a name="how-do-cdns-make-services-work-faster"></a>Wie lassen CDNs Dienste schneller funktionieren?

Das Herunterladen gängiger Objekte wie Websitebilder und Symbole kann immer wieder Netzwerkbandbreite beanspruchen, die besser zum Herunterladen wichtiger persönlicher Inhalte wie E-Mails oder Dokumente verwendet werden kann. Da Office 365 eine Architektur verwendet, die CDNs enthält, können die Symbole, Skripts und andere generische Inhalte von Servern heruntergeladen werden, die näher an Clientcomputern sind, wodurch die Downloads schneller werden. Dies bedeutet einen schnelleren Zugriff auf Ihre persönlichen Inhalte, die sicher in Office 365 gespeichert werden.

CDNs helfen auf verschiedene Weise, die Leistung des Clouddiensts zu verbessern:

- CDNs verschieben einen Teil der Netzwerk- und Dateidownloadlast vom Clouddienst, wodurch Clouddienstressourcen für die Nutzung von Benutzerinhalten und anderen Diensten frei werden, indem die Notwendigkeit reduziert wird, Anforderungen für statische Ressourcen zu erfüllen.
- CDNs dienen dazu, dateizugriff mit geringer Latenz zu ermöglichen, indem sie Hochleistungsnetzwerke und Dateiserver implementieren und aktualisierte Netzwerkprotokolle wie [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) mit hocheffizienter Komprimierung und Anforderungs-Multiplexing nutzen.
- CDN verwenden viele global verteilte Endpunkte, um Inhalte benutzern so nah wie möglich zur Verfügung zu stellen.

## <a name="the-office-365-cdn"></a>Die Office 365 CDN

Mit dem integrierten Office 365 Content Delivery Network (CDN) können Office 365-Administratoren eine bessere Leistung für die SharePoint Onlineseiten ihrer Organisation bereitstellen, indem statische Ressourcen näher an den Browsern zwischenspeichert werden, die sie anfordern, wodurch Downloads beschleunigt und wartezeiten reduziert werden. Das Office 365 CDN verwendet das [HTTP/2-Protokoll für](https://en.wikipedia.org/wiki/HTTP/2) verbesserte Komprimierungs- und Downloadgeschwindigkeiten.

> [!NOTE]
> Die Office 365 CDN ist nur für Mandanten in der **Produktions-Cloud** (weltweit) verfügbar. Mandanten in der US-Regierung, China und Deutschland unterstützen die Office 365 CDN.

Das Office 365-Netzwerk für die Inhaltsübermittlung besteht aus mehreren CDNs, über die Sie statische Objekte an mehreren Speicherorten hosten können, oder aus _Ursprüngen_, die aus globalen Hochgeschwindigkeitsnetzwerken bedient werden. In Abhängigkeit von der Art der Inhalte, die Sie im Office 365-Netzwerk für die Inhaltsübermittlung hosten möchten, können Sie **öffentliche** Ursprünge, **private** Ursprünge oder beides hinzufügen.

![Office 365 CDN Konzeptionelles Diagramm](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN Konzeptionelles Diagramm")

Auf Inhalte in **öffentlichen** Ursprüngen im Office 365-Netzwerk für die Inhaltsübermittlung kann anonym zugegriffen werden und von jeder Person, die URLs zu gehosteten Objekten aufweist. Da der Zugriff auf Inhalte in öffentlichen Ursprüngen anonym ist, sollten Sie diese nur zum Zwischenspeichern von nicht vertraulichen generischen Inhalten verwenden, z. B. JavaScript-Dateien, Skripts, Symbole oder Bilder. Das Office 365-Netzwerk für die Inhaltsübermittlung wird standardmäßig zum Herunterladen von allgemeinen Ressourcenobjekten verwenden, z. B. die Office 365-Clientanwendungen von einem öffentlichen Ursprung.

**Private** Ursprünge innerhalb der Office 365 CDN privaten Zugriff auf Benutzerinhalte wie SharePoint Online-Dokumentbibliotheken, Websites und proprietäre Bilder. Der Zugriff auf Inhalte in private Ursprüngen wird mit dynamisch generierten Token geschützt, auf diese Inhalte kann daher nur von Benutzern mit Berechtigungen für die ursprüngliche Dokumentbibliothek oder den ursprünglichen Speicherort zugegriffen werden. Private Ursprünge Office 365-Netzwerk für die Inhaltsübermittlung können nur für SharePoint Online-Inhalte verwendet werden, und Sie können auf Objekte nur über Umleitung von Ihrem SharePoint Online-Mandanten zugreifen.

Das Office 365-Netzwerk für die Inhaltsübermittlung ist in Ihrem SharePoint Online-Abonnement enthalten.

Weitere Informationen zur Verwendung der Office 365 CDN finden Sie unter [Use the Office 365 content delivery network with SharePoint Online](use-microsoft-365-cdn-with-spo.md).

Eine Reihe von kurzen Videos, die konzeptionelle und HOWTO-Informationen zur Verwendung der Office 365 CDN enthalten, finden Sie im [youTube-Kanal SharePoint Developer Patterns and Practices](https://aka.ms/sppnp-videos).

## <a name="other-microsoft-cdns"></a>Andere Microsoft CDNs

Obwohl sie nicht Teil der Office 365 CDN, können Sie diese CDNs in Ihrem Office 365-Mandanten für den Zugriff auf SharePoint-Entwicklungsbibliotheken, benutzerdefinierten Code und andere Zwecke verwenden, die außerhalb des Gültigkeitsbereichs Office 365 CDN.

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>Ab Q3 2020 beginnt SharePoint Online mit dem Zwischenspeichern von Videos auf dem Azure CDN, um eine verbesserte Videowiedergabe und Zuverlässigkeit zu unterstützen. Beliebte Videos werden aus dem CDN, der dem Benutzer am nächsten ist, gestreamt. Diese Daten verbleiben innerhalb der Microsoft 365 Compliancegrenze. Dies ist ein kostenloser Dienst für alle Mandanten, für den keine Kundenaktion konfiguriert werden muss.

Mit der **Azure CDN** können Sie Ihre eigene CDN-Instanz für das Hosten von benutzerdefinierten Webparts, Bibliotheken und anderen Ressourcenressourcen bereitstellen. Dadurch können Sie Zugriffstasten auf Ihren CDN-Speicher anwenden und eine größere Kontrolle über Ihre CDN-Konfiguration ausüben. Die Verwendung der Azure CDN ist nicht kostenlos und erfordert ein Azure-Abonnement.

Weitere Informationen zum Konfigurieren einer Azure CDN finden Sie unter [Schnellstart: Integrieren eines Azure-Speicherkontos in Azure CDN](/azure/cdn/cdn-create-a-storage-account-with-cdn).

Ein Beispiel dafür, wie das Azure CDN zum Hosten von SharePoint Webparts verwendet werden kann, finden Sie unter [Deploy your SharePoint client-side web part to Azure CDN](/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn).

Weitere Informationen zum Azure CDN PowerShell-Modul finden Sie unter [Manage Azure CDN with PowerShell](/azure/cdn/cdn-manage-powershell).

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

Microsofts **Ajax CDN** ist eine schreibgeschützte CDN, die viele beliebte Entwicklungsbibliotheken bietet, darunter jQuery (und alle anderen Bibliotheken), ASP.NET Ajax, Bootstrap, Knockout.js und andere.
  
Um diese Skripts in Ihr Projekt zu verwenden, ersetzen Sie einfach alle Verweise auf diese öffentlich verfügbaren Bibliotheken durch Verweise auf die CDN-Adresse, anstatt sie in Ihr Projekt selbst zu verwenden. Verwenden Sie beispielsweise den folgenden Code, um eine Verknüpfung zu jQuery zu erstellen:

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

Weitere Informationen zur Verwendung der Microsoft Ajax-CDN finden Sie unter [Microsoft Ajax CDN](/aspnet/ajax/cdn/overview).

## <a name="how-does-office-365-use-content-from-a-cdn"></a>Wie verwendet Office 365 Inhalte aus einem CDN?

Unabhängig davon, CDN Sie für Ihren mandanten Office 365 konfigurieren, ist der grundlegende Datenabrufvorgang identisch.

1. Ihr Client (ein Browser oder Office Clientanwendung) fordert Daten von Office 365.

2. Office 365 gibt die Daten entweder direkt an Ihren Client zurück, oder, wenn die Daten Teil einer Gruppe von Inhalten sind, die von der CDN gehostet werden, leitet Ihren Client an die url CDN um.

    a. Wenn die Daten bereits in  einem öffentlichen Ursprung zwischengespeichert wurden, lädt Ihr Client die Daten direkt vom nächsten CDN auf Ihren Client herunter.

    b. Wenn die Daten bereits in  einem privaten Ursprung zwischengespeichert wurden, überprüft der CDN-Dienst die Berechtigungen Office 365 Benutzerkontos für den Ursprung. Wenn Sie über Berechtigungen verfügen, generiert SharePoint Online dynamisch eine benutzerdefinierte URL, die aus dem Pfad zum Objekt im CDN und zwei Zugriffstoken besteht, und gibt die benutzerdefinierte URL an Ihren Client zurück. Der Client lädt die Daten dann direkt vom nächstgelegenen CDN über die benutzerdefinierte URL auf Ihren Client herunter.

3. Wenn die Daten nicht am CDN zwischengespeichert werden, fordert der knoten CDN die Daten von Office 365 an und speichert die Daten für einen Bestimmten Zeitraum zwischen, nachdem Der Client die Daten heruntergeladen hat.

Der CDN das nächstgelegene Datencenter zum Browser des Benutzers und lädt die angeforderten Daten mithilfe der Umleitung von dort herunter. CDN Umleitung ist schnell und kann Benutzern viel Downloadzeit sparen.

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>Wie sollte ich mein Netzwerk so einrichten, dass CDNs am besten mit Office 365?

Die Minimierung der Wartezeit zwischen Clients in Ihrem Netzwerk und CDN endpunkten ist die wichtigste Überlegung, um eine optimale Leistung sicherzustellen. Sie können die unter Managing [Office 365 endpoints](managing-office-365-endpoints.md) beschriebenen bewährten Methoden verwenden, um sicherzustellen, dass Ihre Netzwerkkonfiguration Clientbrowsern den direkten Zugriff auf die CDN ermöglicht, anstatt CDN Datenverkehr über zentrale Proxys zu weiterleiten, um unnötige Wartezeiten zu vermeiden.

Sie können auch die Office 365 [Netzwerkverbindungsprinzipien](./microsoft-365-network-connectivity-principles.md) lesen, um die Konzepte für die Optimierung der Office 365 verstehen.

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>Gibt es eine Liste aller cdNs, die Office 365 verwenden?

Die von Office 365 verwendeten CDNs können immer geändert werden, und in vielen Fällen sind mehrere CDN partner konfiguriert, wenn der erste nicht verfügbar ist. Die primären cdNs, die von Office 365 verwendet werden, sind:

|CDN  |Unternehmen  |Verwendung  |Linkdatenbank  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |Generische Objekte in öffentlichen Ursprüngen, SharePoint benutzerinhalten in privaten Ursprüngen         |[Verwenden des Office 365 Content Delivery Network mit SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|Azure CDN     |Microsoft         |Benutzerdefinierter Code, SharePoint-Framework Lösungen         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN (schreibgeschützt)     |Microsoft         |Allgemeine Bibliotheken für Ajax, jQuery, ASP.NET, Bootstrap, Knockout.js usw.         |[Microsoft Ajax CDN](/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>Welche Leistungsgewinne bietet CDN?

Es gibt viele Faktoren, die bei der Messung spezifischer Leistungsunterschiede zwischen Daten, die direkt aus Office 365 heruntergeladen werden, und Daten, die von einem bestimmten CDN heruntergeladen werden, beteiligt sind, z. B. ihr Standort relativ zu Ihrem Mandanten und zum nächstgelegenen CDN-Endpunkt, die Anzahl der Objekte auf einer Seite, die von der CDN bedient werden, sowie vorübergehende Änderungen in der Netzwerklatenz und Bandbreite. Ein einfacher A/B-Test kann jedoch helfen, den Unterschied bei der Downloadzeit für eine bestimmte Datei zu erkennen.

Die folgenden Screenshot zeigen den Unterschied bei der Downloadgeschwindigkeit zwischen dem systemeigenen Dateispeicherort in Office 365 und derselben Datei, die auf der [Microsoft Ajax-Content Delivery Network gehostet wird.](/aspnet/ajax/cdn/overview) Diese Screenshotansichten finden Sie auf der Registerkarte **Netzwerk** in den Internet Explorer 11-Entwicklertools. Diese Screenshot zeigen die Wartezeit für die beliebte Bibliothek jQuery. Um diesen Bildschirm anzuzeigen, drücken Sie in Internet  Explorer **F12,** und wählen Sie die Registerkarte Netzwerk aus, die mit einem Symbol Wi-Fi wird.
  
![Screenshot des F12-Netzwerks](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
Dieser Screenshot zeigt die Bibliothek, die in den Masterseitenkatalog auf der SharePoint Onlinewebsite selbst hochgeladen wurde. Die Zeit zum Hochladen der Bibliothek beträgt 1,51 Sekunden.
  
![Screenshot der Ladezeit 1.51s](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
Der zweite Screenshot zeigt die gleiche Datei, die von Microsofts CDN. Dieses Mal beträgt die Latenz etwa 496 Millisekunden. Dies ist eine große Verbesserung und zeigt, dass eine ganze Sekunde die Gesamtzeit zum Herunterladen des Objekts abrasiert wird.
  
![Screenshot der Ladezeiten in 469 ms](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>Sind meine Daten sicher?

Wir achten sehr darauf, die Daten zu schützen, die Ihr Unternehmen betreibt. Die im Office 365 CDN gespeicherten Daten werden sowohl während der Übertragung als auch während des Ruhezeitens verschlüsselt, und der Zugriff auf Daten im Office 365 SharePoint CDN wird durch Office 365 Benutzerberechtigungen und tokenautorisierung gesichert. Anforderungen für Daten in der Office 365 SharePoint CDN müssen von Ihrem Mandanten umgeleitet (umgeleitet) werden Office 365 oder es wird kein Autorisierungstoken generiert.

Um sicherzustellen, dass Ihre Daten sicher bleiben, wird empfohlen, niemals Benutzerinhalte oder andere vertrauliche Daten in einem öffentlichen CDN. Da der Zugriff auf Daten in einer öffentlichen CDN anonym ist, sollten öffentliche CDNs nur zum Hosten generischer Inhalte wie Webskriptdateien, Symbole, Bilder und andere nicht vertrauliche Objekte verwendet werden.

> [!NOTE]
> Drittanbieter CDN haben möglicherweise Datenschutz- und Compliancestandards, die sich von den vom Office 365 Trust Center beschriebenen Verpflichtungen unterscheiden. Daten, die über den CDN-Dienst zwischengespeichert werden, entsprechen möglicherweise nicht den Microsoft Data Processing Terms (DPT) und können sich außerhalb der Office 365 Trust Center-Compliancegrenzen befinden.

Ausführliche Informationen zu Datenschutz und Datenschutz für Office 365 CDN finden Sie unter:  

- Weitere Informationen zu Office 365 datenschutz und datenschutz finden Sie im [Microsoft Trust Center](https://www.microsoft.com/trustcenter)
- Weitere Informationen zum Datenschutz und zum Datenschutz von Akamai finden Sie im [Akamai Privacy Trust Center.](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)
- Weitere Informationen zu Azure Privacy and Data Protection finden Sie im [Azure Trust Center.](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>Wie kann ich mein Netzwerk mit all diesen Drittanbieterdiensten sichern?

Die Nutzung einer umfangreichen Gruppe von Partnerdiensten ermöglicht Office 365, die Verfügbarkeitsanforderungen zu skalieren und zu erfüllen sowie die Benutzerfreundlichkeit bei der Verwendung von Office 365. Die 3rd-Office 365 umfassen beide Zertifikatsperrlisten. z. B. crl.microsoft.com oder sa.symcb.com und CDNs; z. B. r3.res.outlook.com. Jeder CDN von Office 365 generierte FQDN ist ein benutzerdefinierter FQDN für Office 365. Wenn Sie auf Anforderung von Office 365 an einen FQDN gesendet werden, können Sie sicher sein, dass der CDN-Anbieter den FQDN und die zugrunde liegenden Inhalte an diesem Speicherort steuert.
  
Für Kunden, die Anforderungen, die für ein Microsoft- oder Office 365-Rechenzentrum bestimmt sind, von Anforderungen trennen möchten, die für einen Drittanbieter bestimmt sind, haben wir Anleitungen zum Verwalten von Office 365-Endpunkten [geschrieben.](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>Gibt es eine Liste aller FQDNs, die CDNs nutzen?

Die Liste der FQDNs und ihre Nutzung von CDNs ändern sich im Laufe der Zeit. Auf der Seite veröffentlichte Office 365 urLs und [IP-Adressbereiche](./urls-and-ip-address-ranges.md) finden Sie Informationen zu den neuesten FQDNs, die CDNs nutzen.

Sie können auch den [Office 365-IP-Adresse](microsoft-365-ip-web-service.md) und -URL-Webdienst verwenden, um die aktuellen Office 365 URLs und IP-Adressbereiche anzu fordern, die als CSV oder JSON formatiert sind.

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>Kann ich meine eigenen inhalte CDN in meinem lokalen Netzwerk zwischenspeichern?

Wir sind ständig auf der Suche nach neuen Möglichkeiten, um die Anforderungen unserer Kunden zu unterstützen, und untersuchen derzeit die Verwendung von Zwischenspeicherungsproxylösungen und anderen lokalen CDN Lösungen.

Obwohl es nicht Teil der Office 365 CDN ist, können Sie die **Azure CDN** auch zum Hosten von benutzerdefinierten Webparts, Bibliotheken und anderen Ressourcenressourcen verwenden, wodurch Sie Zugriffstasten auf Ihren CDN-Speicher anwenden und eine größere Kontrolle über Ihre CDN-Konfiguration ausüben können. Die Verwendung der Azure CDN ist nicht kostenlos und erfordert ein Azure-Abonnement. Weitere Informationen zum Konfigurieren einer Azure CDN finden Sie unter [Schnellstart: Integrieren eines Azure-Speicherkontos in Azure CDN](/azure/cdn/cdn-create-a-storage-account-with-cdn).

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>Ich verwendet Azure ExpressRoute für Office 365 ändert sich das?

[Azure ExpressRoute für Office 365](azure-expressroute.md) stellt eine dedizierte Verbindung mit Office 365, die vom öffentlichen Internet getrennt ist. Dies bedeutet, dass Clients weiterhin über Nicht-ExpressRoute-Verbindungen eine Verbindung herstellen müssen, um eine Verbindung mit CDNs und anderer Microsoft-Infrastruktur herzustellen, die nicht explizit in der Liste der von ExpressRoute unterstützten Dienste enthalten ist. Weitere Informationen zum Routen von bestimmtem Datenverkehr, z. B. Anforderungen für CDNs, finden Sie unter Office 365 [Netzwerkdatenverkehrverwaltung](routing-with-expressroute.md).

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>Kann ich CDNs mit SharePoint Server lokal verwenden?

Die Verwendung von CDNs ist nur in einem SharePoint Onlinekontext sinnvoll und sollte mit SharePoint vermieden werden. Dies liegt daran, dass alle Vorteile des geografischen Standorts nicht wahr sind, wenn sich der Server lokal oder geografisch in der Nähe befindet. Wenn außerdem eine Netzwerkverbindung zu den Servern besteht, auf denen er gehostet wird, kann der Standort ohne Internetverbindung verwendet werden und kann daher die CDN abrufen. Andernfalls sollten Sie eine CDN verwenden, wenn für die Bibliothek und die Dateien, die Sie für Ihre Website benötigen, verfügbar und stabil ist.
  
Mit diesem kurzen Link gelangen Sie wieder hierher zurück: [https://aka.ms/o365cdns]()
  
## <a name="see-also"></a>Weitere Artikel

[Prinzipien von Office 365-Netzwerkverbindungen](./microsoft-365-network-connectivity-principles.md)

[Bewerten der Office 365-Netzwerkkonnektivität](assessing-network-connectivity.md)

[Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md)

[URLs und IP-Adressbereiche für Office 365](./urls-and-ip-address-ranges.md)

[Verwenden des Office 365 Content Delivery Network mit SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Microsoft Trust Center](https://www.microsoft.com/trustcenter)

[Optimieren der Leistung von Office 365](tune-microsoft-365-performance.md)