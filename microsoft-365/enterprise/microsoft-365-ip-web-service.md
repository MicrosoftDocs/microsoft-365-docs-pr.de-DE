---
title: Office 365-IP-Adress- und -URL-Webdienst
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 8/6/2019
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.reviewer: pandrew
search.appverid:
- MET150
- MOE150
- BCS160
description: Erfahren Sie, wie Sie den Office 365-IP-Adress- und URL-Webdienst nutzen können, um den Netzwerkverkehr von Office 365 besser zu identifizieren und zu differenzieren.
ms.openlocfilehash: 6a8786d99c92fae43113d550b76a87281cde0c5b
ms.sourcegitcommit: ea8de1b48adb6df92fb9351ea862184a9f16cbbb
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/16/2021
ms.locfileid: "53461291"
---
# <a name="office-365-ip-address-and-url-web-service"></a>Office 365-IP-Adress- und -URL-Webdienst

Der Webdienst für Office 365-IP-Adressen und -URLs unterstützt Sie beim besseren Erkennen und Differenzieren des Netzwerkdatenverkehrs in Office 365, was die Auswertung von Änderungen und die Konfiguration vereinfacht und Ihnen erleichtert, auf dem neuesten Stand zu bleiben. Dieser REST-basierte Webdienst ersetzt die vorherigen herunterladbaren XML-Dateien, die am 2. Oktober 2018 ausliefen.

Als Kunde oder Anbieter von Netzwerkperimetergeräten können Sie den Webdienst für Office 365-IP-Adress- und -FQDN-Einträge verwenden. Sie können direkt in einem Webbrowser auf die Daten zugreifen, indem Sie diese URLs verwenden:

- Verwenden Sie für die neueste Version der Office 365-URLs und -IP-Adressbereiche [https://endpoints.office.com/version](https://endpoints.office.com/version?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).
- Verwenden Sie für die Daten auf der Seite für die Office 365-URLs und -IP-Adressbereiche für Firewalls und Proxyserver [https://endpoints.office.com/endpoints/worldwide](https://endpoints.office.com/endpoints/worldwide?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).
- Um die neuesten Änderungen seit Juli 2018 zu erhalten (Datum, zu dem der Webdienst erstmalig verfügbar war), verwenden Sie [https://endpoints.office.com/changes/worldwide/0000000000](https://endpoints.office.com/changes/worldwide/0000000000?clientrequestid=b10c5ed1-bad1-445f-b386-b919946339a7).

Als Kunde können Sie diesen Webdienst für Folgendes verwenden:

- Aktualisieren Sie Ihre PowerShell-Skripte zum Abrufen von Daten auf Office 365-Endpunkten und zum Ändern der Formatierung für Ihre Netzwerkgeräte.
- Verwenden Sie diese Informationen, um auf Clientcomputern bereitgestellte PAC-Dateien zu aktualisieren.

Als Anbieter von Netzwerkperimetergeräten können Sie diesen Webdienst für Folgendes verwenden:

- Erstellen und testen Sie Gerätesoftware für den Download der Liste für die automatische Konfiguration.
- Suchen Sie die aktuelle Version.
- Rufen Sie die aktuellen Änderungen ab.

> [!NOTE]
> Wenn Sie Azure ExpressRoute für die Verbindung mit Office 365 verwenden, lesen Sie bitte [Azure ExpressRoute for Office 365](azure-expressroute.md), um sich mit den Office 365-Diensten vertraut zu machen, die von Azure ExpressRoute unterstützt werden.  Bitte lesen Sie auch den Artikel [Office 365-URLs und -IP-Adressbereiche](urls-and-ip-address-ranges.md), um zu verstehen, welche Netzwerke für Office 365-Apps eine Internetverbindung benötigen. Das wird Ihnen helfen, Ihre Umkreis-Sicherheitsgeräte besser zu konfigurieren.

Weitere Informationen finden Sie unter:

- [Ankündigungsblogbeitrag im Office 365 Tech-Community-Forum](https://techcommunity.microsoft.com/t5/Office-365-Blog/Announcing-Office-365-endpoint-categories-and-Office-365-IP/ba-p/177638)
- [Office 365-Tech-Community-Forum für Fragen zur Verwendung der Webdienste](https://techcommunity.microsoft.com/t5/Office-365-Networking/bd-p/Office365Networking)

## <a name="common-parameters"></a>Allgemeine Parameter

Diese Parameter gelten für sämtliche Webdienstmethoden:

- **format=\<JSON \| CSV\>** – Standardmäßig ist das zurückgegebene Dateiformat JSON. Verwenden Sie diesen optionalen Parameter, um die Daten in durch Trennzeichen getrennten Werten (CSV-Format) zurückzuerhalten.
- **ClientRequestId=\<guid\>** – eine erforderliche GUID, die Sie für die Clientzuordnung generieren. Generieren Sie eine eindeutige GUID für jeden Computer, von dem der Webdienst aufgerufen wird (die auf dieser Seite enthaltenen Skripts generieren eine GUID für Sie). Nutzen Sie nicht die in den folgenden Beispielen dargestellten GUIDs, da sie künftig durch den Webdienst blockiert werden könnten. Das GUID-Format ist _xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx_, wobei x eine hexadezimale Zahl darstellt.

  Wenn Sie eine GUID generieren möchten, können Sie den PowerShell-Befehl [New-Guid](/powershell/module/microsoft.powershell.utility/new-guid) verwenden oder einen Onlinedienst wie den [Online GUID Generator](https://www.guidgenerator.com/) nutzen.

## <a name="version-web-method"></a>Versionswebmethode

Microsoft aktualisiert die Office 365-IP-Adress- und -FQDN-Einträge am Anfang jeden Monats. Out-of-Band-Updates werden manchmal aufgrund von Supportfällen, Sicherheitsupdates oder sonstigen betrieblichen Anforderungen veröffentlicht.

Den Daten für jede veröffentlichte Instanz wird eine Versionsnummer zugewiesen, und mit der Versionswebmethode können Sie nach der neuesten Version jeder Office 365-Dienstinstanz suchen. Wir empfehlen, die Version nicht mehr als einmal pro Stunde zu überprüfen.

Parameter für die Versionswebmethode sind:

- **AllVersions=\<true \| false\>** – Standardmäßig ist die zurückgegebene Version die neueste. Nehmen Sie diesen optionalen Parameter mit auf, um alle veröffentlichten Versionen seit dem ersten Release des Webdiensts anzufordern.
- **Format=\<JSON \| CSV \| RSS\>** – Zusätzlich zu den Formaten JSON und CSV unterstützt die Versionswebmethode auch RSS. Diesen optionalen Parameter können Sie zusammen mit dem Parameter _AllVersions=true_ verwenden, um einen RSS-Feed anzufordern, der mit Outlook oder anderen RSS-Readern genutzt werden kann.
- **Instance=\<Worldwide \| China \| Germany \| USGovDoD \| USGovGCCHigh\>** – Dieser optionale Parameter gibt die Instanz an, für welche die Version zurückgegeben werden soll. Wenn nicht angegeben, werden alle Instanzen zurückgegeben. Gültige Instanzen sind: Weltweit, China, Deutschland, USGovDoD, USGovGCCHigh.

Die Versionswebmethode ist nicht beschränkt und gibt nie die HTTP-Antwortcodes 429 zurück. Das Ergebnis der Versionswebmethode umfasst keinen Cache-Control-Header, der empfiehlt, die Daten eine Stunde lang zwischenzuspeichern. Das Ergebnis der Versionswebmethode kann ein einzelner Datensatz oder ein Datensatzarray sein. Die Elemente der einzelnen Datensätze sind:

- instance – die Kurzform der Office 365-Serviceinstanz.
- latest – die neueste Version für Endpunkte der angegebenen Instanz.
- versions – Eine Liste aller vorherigen Versionen für die angegebene Instanz. Dieses Element ist nur enthalten, wenn der Parameter _AllVersions_ „true“ ist.

### <a name="version-web-method-examples"></a>Beispiele für die Versionswebmethode

Beispiel 1 – Anforderungs-URI: <https://endpoints.office.com/version?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7>

Dieser URI gibt die aktuelle Version jeder Instanz des Office 365-Diensts zurück. Beispielergebnis:

```json
[
 {
  "instance": "Worldwide",
  "latest": "2018063000"
 },
 {
  "instance": "USGovDoD",
  "latest": "2018063000"
 },
 {
  "instance": "USGovGCCHigh",
  "latest": "2018063000"
 },
 {
  "instance": "China",
  "latest": "2018063000"
 },
 {
  "instance": "Germany",
  "latest": "2018063000"
 }
]
```

> [!IMPORTANT]
> Die GUID für den Parameter „ClientRequestID“ in diesen URIs dient nur als Beispiel. Um die Webdienst-URIs auszuprobieren, erstellen Sie Ihre eigene GUID. Die in den folgenden Beispielen gezeigten GUIDs werden möglicherweise in Zukunft vom Webdienst gesperrt.

Beispiel 2 – Anforderungs-URI: <https://endpoints.office.com/version/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7>

Dieser URI gibt die aktuelle Version der angegebenen Instanz des Office 365-Diensts zurück. Beispielergebnis:

```json
{
 "instance": "Worldwide",
 "latest": "2018063000"
}
```

Beispiel 3 – Anforderungs-URI: <https://endpoints.office.com/version/Worldwide?Format=CSV&ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7>

Dieser URI zeigt die Ausgabe im CSV-Format an. Beispielergebnis:

```csv
instance,latest
Worldwide,2018063000
```

Beispiel 4 – Anforderungs-URI: <https://endpoints.office.com/version/Worldwide?AllVersions=true&ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7>

Dieser URI zeigt alle vorherigen Versionen an, die für die Dienstinstanz von Office 365 weltweit veröffentlicht wurden. Beispielergebnis:

```json
{
  "instance": "Worldwide",
  "latest": "2018063000",
  "versions": [
    "2018063000",
    "2018062000"
  ]
}
```

Beispiel 5 – RSS-Feed-URI: <https://endpoints.office.com/version/worldwide?clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7&allVersions=true&format=RSS>

Dieser URI zeigt einen RSS-Feed der veröffentlichten Versionen, die Links zu der Liste der Änderungen für jede Version enthalten. Beispielergebnis:

```xml
<?xml version="1.0" encoding="ISO-8859-1"?>
<rss version="2.0" xmlns:a10="https://www.w3.org/2005/Atom">
<channel>
<link>https://aka.ms/o365ip</link>
<description/>
<language>en-us</language>
<lastBuildDate>Thu, 02 Aug 2018 00:00:00 Z</lastBuildDate>
<item>
<guid isPermaLink="false">2018080200</guid>
<link>https://endpoints.office.com/changes/Worldwide/2018080200?singleVersion&clientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7</link> <description>Version 2018080200 includes 2 changes. IPs: 2 added and 0 removed.</description>
<pubDate>Thu, 02 Aug 2018 00:00:00 Z</pubDate>
</item>
```

## <a name="endpoints-web-method"></a>Endpunktwebmethode

Die Endpunktwebmethode gibt alle Datensätze für IP-Adressbereiche und URLs zurück, die den Office 365-Dienst bilden. Die neuesten Daten aus der Endpunkt-Webmethode sollten immer für die Konfiguration von Netzwerkgeräten verwendet werden. Microsoft kündigt neue Ergänzungen 30 Tage vor der Veröffentlichung an, um Ihnen Zeit zum Aktualisieren von Zugriffssteuerungs- und Proxyserver-Umgehungslisten zu lassen. Wir empfehlen Ihnen, die Endpunktwebmethode erst wieder einzusetzen, wenn die Versionswebmethode besagt, dass eine neue Version der Daten verfügbar ist.

Parameter für die Endpunktwebmethode sind:

- **ServiceAreas=\<Common \| Exchange \| SharePoint \| Skype\>** – Eine kommagetrennte Liste von Dienstbereichen. Gültige Elemente sind _Common_, _Exchange_, _SharePoint_ und _Skype_. Da _Common_-Dienstbereich-Elemente Voraussetzung für alle anderen Dienstbereiche sind, bezieht der Webdienst sie stets mit ein. Wenn Sie diesen Parameter nicht miteinschließen, werden alle Dienstbereiche zurückgegeben.
- **TenantName=\<tenant_name\>** – Ihr Office 365-Mandantenname. Der Webdienst übernimmt Ihren angegebenen Namen und fügt ihn in URL-Teile ein, die den Mandantennamen enthalten. Wenn Sie keinen Mandantennamen angeben, haben diese URL-Teile das Platzhalterzeichen (\*).
- **NoIPv6=\<true \| false\>** – Legen Sie diesen Wert auf _true_ fest, um IPv6-Adressen von der Ausgabe auszuschließen, wenn Sie IPv6 in Ihrem Netzwerk nicht verwenden.
- **Instance=\<Worldwide \| China \| Germany \| USGovDoD \| USGovGCCHigh\>** – Dieser erforderliche Parameter gibt die Instanz an, von welcher die Endpunkte zurückgegeben werden sollen. Gültige Instanzen sind: _Weltweit_, _China_, _Deutschland_, _USGovDoD_ und _USGovGCCHigh_.

Wenn Sie die Endpunktwebmethode zu häufig von derselben Client-IP-Adresse abrufen, erhalten Sie möglicherweise den HTTP-Antwortcode _429 (zu viele Anforderungen)_. Wenn Sie diesen Antwortcode erhalten, warten Sie eine Stunde, bevor Sie Ihre Anforderung wiederholen, oder generieren Sie eine neue GUID für sie. Als allgemein bewährte Methode rufen Sie die Endpunktwebmethode nur auf, wenn die Versionswebmethode besagt, dass eine neue Version verfügbar ist.

Das Ergebnis der Endpunktwebmethode ist ein Datensatz-Array, bei dem jeder Datensatz einen Endpunktsatz darstellt. Die Elemente für jeden Datensatz lauten:

- id – die unveränderliche ID-Nummer des Endpunktsatzes.
- serviceArea – der Servicebereich, zu dem Folgendes gehört: _Common_, _Exchange_, _SharePoint_ oder _Skype_.
- urls – URLs für den Endpunktsatz. Ein JSON-Array von DNS-Datensätzen. Wird ausgelassen, falls leer.
- tcpPorts – TCP-Ports für den Endpunktsatz. Alle Portelemente werden als eine kommagetrennte Liste von Ports oder Portbereichen formatiert, getrennt durch einen Bindestrich (-). Ports gelten für alle IP-Adressen und alle URLs im Endpunktsatz für eine bestimmte Kategorie. Wird ausgelassen, falls leer.
- udpPorts – UDP-Ports für die IP-Adressbereiche in diesem Endpunktsatz. Wird ausgelassen, falls leer.
- ips – Der mit diesem Endpunktsatz verknüpfte IP-Adressbereich (verknüpft mit den aufgeführten TCP- oder UDP-Ports). Ein JSON-Array von IP-Adressbereichen. Wird ausgelassen, falls lehr.
- category – die Kategorie „Konnektivität“ des Endpunktsatzes. Gültige Werte sind _Optimize_, _Allow_ und _Default_. Wenn Sie die Ausgabe der Endpunktwebmethode für die Kategorie einer bestimmten IP-Adresse oder URL durchsuchen, kann die Abfrage mehrere Kategorien zurückgeben. Folgen Sie in diesem Fall der Empfehlung für die Kategorie mit der höchsten Priorität. Wenn der Endpunkt beispielsweise sowohl in _Optimize_ als auch _Allow_ angezeigt wird, sollten Sie den Anforderungen für _Optimize_ entsprechen. Erforderlich.
- expressRoute – _True_, wenn dieser Endpunktsatz über ExpressRoute weitergeleitet wird; _False_, wenn nicht.
- required – _True_, wenn für diesen Endpunktsatz Konnektivität erforderlich ist, damit Office 365 unterstützt wird. _False_, wenn dieser Endpunktsatz optional ist.
- notes – Für optionale Endpunkte beschreibt dieser Text die Office 365-Funktionalität, die nicht verfügbar wäre, wenn der Zugriff auf IP-Adressen oder URLs in diesem Endpunktsatz nicht auf Netzwerkebene möglich ist. Wird ausgelassen, falls leer.

### <a name="endpoints-web-method-examples"></a>Beispiele für die Endpunktwebmethode

Beispiel 1 – Anforderungs-URI: <https://endpoints.office.com/endpoints/Worldwide?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7>

Dieser URI ruft alle Endpunkte für die Instanz von Office 365 weltweit für alle Workloads ab. Das Beispielergebnis zeigt einen Auszug der Ausgabe an:

```json
[
 {
  "id": 1,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.protection.outlook.com"
   ],
  "ips":
   [
    "2a01:111:f403::/48", "23.103.132.0/22", "23.103.136.0/21", "23.103.198.0/23", "23.103.212.0/22", "40.92.0.0/14", "40.107.0.0/17", "40.107.128.0/18", "52.100.0.0/14", "213.199.154.0/24", "213.199.180.128/26", "94.245.120.64/26", "207.46.163.0/24", "65.55.88.0/24", "216.32.180.0/23", "23.103.144.0/20", "65.55.169.0/24", "207.46.100.0/24", "2a01:111:f400:7c00::/54", "157.56.110.0/23", "23.103.200.0/22", "104.47.0.0/17", "2a01:111:f400:fc00::/54", "157.55.234.0/24", "157.56.112.0/24", "52.238.78.88/32"
   ],
  "tcpPorts": "443",
  "expressRoute": true,
  "category": "Allow"
 },
 {
  "id": 2,
  "serviceArea": "Exchange",
  "serviceAreaDisplayName": "Exchange Online",
  "urls":
   [
    "*.mail.protection.outlook.com"
   ],
```

Beachten Sie, dass die vollständige Ausgabe der Anforderung in diesem Beispiel weitere Endpunktsätze enthalten würde.

Anfrage-URI – Beispiel 2: [https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7](https://endpoints.office.com/endpoints/Worldwide?ServiceAreas=Exchange&amp;ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7)

In diesem Beispiel werden nur Endpunkte für die Instanz von Office 365 weltweit für Exchange Online und Abhängigkeiten abgerufen.

Die Ausgabe für Beispiel 2 ähnelt Beispiel 1 mit dem Unterschied, dass die Ergebnisse keine Endpunkte für SharePoint Online oder Skype for Business Online enthalten würden.

## <a name="changes-web-method"></a>Änderungswebmethode

Die Änderungswebmethode gibt die neuesten Updates zurück, die veröffentlicht wurden, typischerweise die Änderungen des vorherigen Monats an IP-Adressbereichen und URLs.

Die wichtigsten Änderungen an Endpunktdaten sind neue URLs und IP-Adressen. Wenn eine IP-Adresse nicht zu einer Firewall-Zugriffssteuerungsliste oder eine URL nicht zu einer Proxyserver-Umgehungsliste hinzugefügt wird, kann dies zu einem Ausfall für Benutzer von Office 365 auf diesem Netzwerkgerät führen. Ungeachtet betrieblicher Anforderungen werden neue Endpunkte 30 Tage vor dem Datum, an dem die Endpunkte bereitgestellt werden, im Webdienst veröffentlicht, um Ihnen Zeit zum Aktualisieren von Zugriffssteuerungs- und Proxyserver-Umgehungslisten zu lassen.

Die nötigen Parameter für die Änderungswebmethode sind:

- **Version=\<YYYYMMDDNN>** – Erforderlicher URL-Routenparameter. Dieser Wert steht für die Version, die derzeit implementiert ist. Der Webdienst wird die Änderungen seit dieser Version zurückgeben. Das Format ist _JJJJMMTTNN_, wobei _NN_ eine natürliche Zahl ist, die erhöht wird, falls mehrere Versionen am gleichen Tag herausgegeben werden müssen. Dabei steht _00_ für das erste Update an einen bestimmten Tag. Der Webdienst erfordert, dass der _Versions_-Parameter genau 10 Ziffern enthält.

Für die Änderungswebmethode sind die Gebühren auf dieselbe Art und Weise beschränkt wie bei der Endpunktwebmethode. Wenn Sie einen 429-HTTP-Antwortcode erhalten, warten Sie eine Stunde, bevor Sie Ihre Anforderung wiederholen, oder generieren Sie eine neue GUID für sie.

Das Ergebnis der Änderungswebmethode ist ein Datensatz-Array, bei dem jeder Datensatz eine Änderung in einer speziellen Version des Endpunkts darstellt. Die Elemente für jeden Datensatz lauten:

- id – die unveränderliche ID des Änderungsdatensatzes.
- endpointSetId – die ID des Endpunktsatz-Datensatzes, der geändert wird.
- disposition – beschreibt, was die Änderung am Endpunktsatz bewirkt hat. Die Werte sind _change_, _add_ oder _remove_.
- Auswirkung – nicht alle Änderungen sind für jede Umgebung gleichermaßen wichtig. Dieses Element beschreibt die erwartete Wirkung auf die Umgebung eines Unternehmensnetzwerkumkreises infolge dieser Änderung. Dieses Element wird nur in Änderungsdatensätze der Version **2018112800** und höher einbezogen. Die Optionen für die Wirkung sind: AddedIp – eine IP-Adresse wurde zu Office 365 hinzugefügt und ist in Kürze im Dienst online. Dies stellt eine Änderung dar, die Sie an einer Firewall oder einem anderem Netzwerkumkreisgerät der Schicht 3 vornehmen müssen. Wenn Sie dies nicht hinzufügen, bevor wir starten, erleben Sie möglicherweise einen Ausfall.
  – AddedUrl – ein URL wurde Office 365 hinzugefügt und ist in Kürze im Dienst live. Dies stellt eine Änderung dar, die Sie auf einem Netzwerkumkreisgerät für die Proxyserver- oder URL-Analyse vornehmen müssen. Wenn Sie diesen URL nicht hinzufügen, bevor wir starten, erleben Sie möglicherweise einen Ausfall.
  – AddedIpAndUrl: Sowohl eine IP-Adresse als auch ein URL wurden hinzugefügt. Dies stellt eine Änderung dar, die Sie entweder auf einem Firewall-Gerät der Schicht 3 oder einem Gerät zur Proxyserver- oder URL-Analyse vornehmen müssen. Wenn Sie diese IP bzw. URL nicht hinzufügen, bevor wir starten, erleben Sie möglicherweise einen Ausfall.
  – RemovedIpOrUrl: Mindestens eine IP-Adresse oder URL wurde aus Office 365 entfernt. Sie entfernen die Netzwerkendpunkte von ihren Umkreisgeräten, aber dafür gibt es keinen Stichtag.
  – ChangedIsExpressRoute: Das Supportattribut „Express Route“ wurde geändert. Wenn Sie ExpressRoute verwenden, müssen Sie möglicherweise je nach Konfiguration Maßnahmen ergreifen.
  – MovedIpOrUrl: Eine IP-Adresse oder URL wurde zwischen diesem Endpunktsatz und einem anderen verschoben. Im Allgemeinen ist keine Aktion erforderlich.
  – RemovedDuplicateIpOrUrl: Eine doppelte IP-Adresse oder URL wurde entfernt, diese ist aber immer noch für Office 365 veröffentlicht. Im Allgemeinen ist keine Aktion erforderlich.
  – OtherNonPriorityChanges: Es wurde etwas weniger wichtiges als alle anderen Optionen geändert, z. B. die Inhalte eines Notizfelds.
- version – Die Version des veröffentlichten Endpunktsatzes, in dem die Änderung eingeführt wurde. Versionsnummern werden im Format _JJJJMMTTNN_ angegeben, wobei _NN_ eine natürliche Zahl ist, die erhöht wird, wenn mehrere Versionen an einem einzigen Tag veröffentlicht werden müssen.
- previous – eine Unterstruktur, die vorherige Werte von Änderungselementen im Endpunktsatz angibt. Dies ist bei neu hinzugefügten Endpunktsätzen nicht enthalten. Umfasst _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ und _notes_.
- current – eine Unterstruktur, die aktualisierte Werte von Änderungselementen im Endpunktsatz angibt. Umfasst _ExpressRoute_, _serviceArea_, _category_, _required_, _tcpPorts_, _udpPorts_ und _notes_.
- add – eine Unterstruktur, die Elemente angibt, die zu Endpunktsatzsammlungen hinzugefügt werden sollen. Wird weggelassen, wenn es keine Ergänzungen gibt.
  – effectiveDate: definiert die Daten, wann die Ergänzungen live im Dienst sind.
  – ips: Elemente, die dem Array _ips_ hinzugefügt werden sollen.
  – urls: Elemente, die zum Array _urls_ hinzugefügt werden sollen.
- remove – eine Unterstruktur, die aus dem Endpunktsatz zu entfernende Elemente angibt. Wird weggelassen, wenn es keine Entfernungen gibt.
  – ips: Elemente, die aus dem Array _ips_ entfernt werden sollen.
  – urls: Elemente, die aus dem Array _urls_ entfernt werden sollen.

### <a name="changes-web-method-examples"></a>Beispiele für die Änderungswebmethode

Beispiel 1 – Anforderungs-URI: <https://endpoints.office.com/changes/worldwide/0000000000?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7>

Dies fordert alle vorherigen Änderungen an der Dienstinstanz von Office 365 weltweit an. Beispielergebnis:

```json
[
 {
  "id": 424,
  "endpointSetId": 32,
  "disposition": "Change",
  "version": "2018062700",
  "remove":
   {
    "urls":
     [
      "*.api.skype.com", "skypegraph.skype.com"
     ]
   }
 },
 {
  "id": 426,
  "endpointSetId": 31,
  "disposition": "Change",
  "version": "2018062700",
  "add":
   {
    "effectiveDate": "20180609",
    "ips":
     [
      "51.140.203.190/32"
     ]
   },
  "remove":
   {
    "ips":
     [
```

Beispiel 2 – Anforderungs-URI: <https://endpoints.office.com/changes/worldwide/2018062700?ClientRequestId=b10c5ed1-bad1-445f-b386-b919946339a7>

Dies fordert Änderungen seit der angegebenen Version der Instanz von Office 365 weltweite an. Die angegebene Version ist in diesem Fall die neueste. Beispielergebnis:

```json
[
  {
    "id":3,
    "endpointSetId":33,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["65.55.127.0/24","66.119.157.192/26","66.119.158.0/25",
      "111.221.76.128/25","111.221.77.0/26","207.46.5.0/24"]
    }
  },
  {
    "id":4,
    "endpointSetId":45,
    "changeDescription":"Removing old IP prefixes",
    "disposition":"Change",
    "version":"2018031301",
    "remove":{
      "ips":["13.78.93.8/32","40.113.87.220/32","40.114.149.220/32",
      "40.117.100.83/32","40.118.214.164/32","104.208.31.113/32"]
    }
  }
]
```

## <a name="example-powershell-script"></a>Beispiel für PowerShell-Skript

Sie können dieses PowerShell-Skript ausführen, um festzustellen, ob es Aktionen gibt, die Sie für aktualisierte Daten setzen müssen. Sie können dieses Skript als geplante Aufgabe ausführen, um nach einer Versionsaktualisierung zu suchen. Um zu vermeiden, dass der Webdienst überlastet ist, versuchen Sie, das Skript nicht mehr als einmal pro Stunde auszuführen.

Dieses Skript führt folgende Aktionen aus:

- Überprüfen der Versionsnummer der aktuellen Office 365 weltweit-Instanzendpunkte durch Aufrufen der Webdienst-REST-API.
- Suchen nach einer aktuellen Versionsdatei unter _$Env:TEMP\O365_endpoints_latestversion.txt_. Der Pfad der globalen Variablen **$Env:TEMP** ist in der Regel _C:\Users\\<username\>\AppData\Local\Temp_.
- Wenn dies das erste Mal ist, dass das Skript ausgeführt wurde, gibt es die aktuelle Version sowie alle aktuellen IP-Adressen und URLs zurück, schreibt die Endpunkt-Version in die Datei _$Env:TEMP\O365_endpoints_latestversion.txt_ und die Endpunkt-Datenausgabe in die Datei _$Env:TEMP\O365_endpoints_data.txt_. Sie können den Pfad und/oder den Namen der Ausgabedatei ändern, indem Sie die folgenden Zeilen bearbeiten:

    ``` powershell
    $versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
    $datapath = $Env:TEMP + "\O365_endpoints_data.txt"
    ```

- Wenn die neueste Webdienst-Version bei jeder nachfolgenden Ausführung des Skripts mit der Version in der Datei _O365_endpoints_latestversion.txt_ identisch ist, wird das Skript beendet, ohne Änderungen vorzunehmen.
- Wenn die neueste Webdienst-Version neuer als die Version in der Datei _O365_endpoints_latestversion.txt_ ist, gibt das Skript die Endpunkte und Filter für die Endpunkte der Kategorien **Allow** und **Optimize** zurück, aktualisiert die Version in der Datei _O365_endpoints_latestversion.txt_ und schreibt die aktualisierten Daten in die Datei _O365_endpoints_data.txt_.

Das Skript generiert eine eindeutige _ClientRequestId_ für den Computer, auf dem es ausgeführt wird, und verwendet diese ID über mehrere Aufrufe hinweg. Diese ID wird in der Datei _O365_endpoints_latestversion.txt_ gespeichert.

### <a name="to-run-the-powershell-script"></a>Ausführen des PowerShell-Skripts

1. Kopieren Sie das Skript, und speichern Sie es auf der Festplatte oder am Speicherort des Skripts als _Get-O365WebServiceUpdates.ps1_.
1. Führen Sie das Skript in Ihrem bevorzugten Skript-Editor, z. B. PowerShell ISE oder VS Code, oder auf einer PowerShell-Konsole mithilfe des folgenden Befehls aus:

    ``` powershell
   powershell.exe -file <path>\Get-O365WebServiceUpdates.ps1
    ```

    Es gibt keine Parameter, die an das Skript weiterzugeben sind.

```powershell
<# Get-O365WebServiceUpdates.ps1
From https://aka.ms/ipurlws
v1.1 8/6/2019

DESCRIPTION
This script calls the REST API of the Office 365 IP and URL Web Service (Worldwide instance)
and checks to see if there has been a new update since the version stored in an existing
$Env:TEMP\O365_endpoints_latestversion.txt file in your user directory's temp folder
(usually C:\Users\<username>\AppData\Local\Temp).
If the file doesn't exist, or the latest version is newer than the current version in the
file, the script returns IPs and/or URLs that have been changed, added or removed in the latest
update and writes the new version and data to the output file $Env:TEMP\O365_endpoints_data.txt.

USAGE
Run as a scheduled task every 60 minutes.

PARAMETERS
n/a

PREREQUISITES
PS script execution policy: Bypass
PowerShell 3.0 or later
Does not require elevation
#>

#Requires -Version 3.0

# web service root URL
$ws = "https://endpoints.office.com"
# path where output files will be stored
$versionpath = $Env:TEMP + "\O365_endpoints_latestversion.txt"
$datapath = $Env:TEMP + "\O365_endpoints_data.txt"

# fetch client ID and version if version file exists; otherwise create new file and client ID
if (Test-Path $versionpath) {
    $content = Get-Content $versionpath
    $clientRequestId = $content[0]
    $lastVersion = $content[1]
    Write-Output ("Version file exists! Current version: " + $lastVersion)
}
else {
    Write-Output ("First run! Creating version file at " + $versionpath + ".")
    $clientRequestId = [GUID]::NewGuid().Guid
    $lastVersion = "0000000000"
    @($clientRequestId, $lastVersion) | Out-File $versionpath
}

# call version method to check the latest version, and pull new data if version number is different
$version = Invoke-RestMethod -Uri ($ws + "/version/Worldwide?clientRequestId=" + $clientRequestId)
if ($version.latest -gt $lastVersion) {
    Write-Host "New version of Office 365 worldwide commercial service instance endpoints detected"
    # write the new version number to the version file
    @($clientRequestId, $version.latest) | Out-File $versionpath
    # invoke endpoints method to get the new data
    $endpointSets = Invoke-RestMethod -Uri ($ws + "/endpoints/Worldwide?clientRequestId=" + $clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into custom objects with port and category
    # URL results
    $flatUrls = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $urls = $(if ($endpointSet.urls.Count -gt 0) { $endpointSet.urls } else { @() })
        $urlCustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $urlCustomObjects = $urls | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    url      = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $urlCustomObjects
    }
    # IPv4 results
    $flatIp4s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv4 strings contain dots
        $ip4s = $ips | Where-Object { $_ -like '*.*' }
        $ip4CustomObjects = @()
        if ($endpointSet.category -in ("Allow", "Optimize")) {
            $ip4CustomObjects = $ip4s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip4CustomObjects
    }
    # IPv6 results
    $flatIp6s = $endpointSets | ForEach-Object {
        $endpointSet = $_
        $ips = $(if ($endpointSet.ips.Count -gt 0) { $endpointSet.ips } else { @() })
        # IPv6 strings contain colons
        $ip6s = $ips | Where-Object { $_ -like '*:*' }
        $ip6CustomObjects = @()
        if ($endpointSet.category -in ("Optimize")) {
            $ip6CustomObjects = $ip6s | ForEach-Object {
                [PSCustomObject]@{
                    category = $endpointSet.category;
                    ip = $_;
                    tcpPorts = $endpointSet.tcpPorts;
                    udpPorts = $endpointSet.udpPorts;
                }
            }
        }
        $ip6CustomObjects
    }

    # write output to screen
    Write-Output ("Client Request ID: " + $clientRequestId)
    Write-Output ("Last Version: " + $lastVersion)
    Write-Output ("New Version: " + $version.latest)
    Write-Output ""
    Write-Output "IPv4 Firewall IP Address Ranges"
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "IPv6 Firewall IP Address Ranges"
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-String
    Write-Output "URLs for Proxy Server"
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-String
    Write-Output ("IP and URL data written to " + $datapath)

    # write output to data file
    Write-Output "Office 365 IP and UL Web Service data" | Out-File $datapath
    Write-Output "Worldwide instance" | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output ("Version: " + $version.latest) | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv4 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp4s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "IPv6 Firewall IP Address Ranges" | Out-File $datapath -Append
    ($flatIp6s.ip | Sort-Object -Unique) -join "," | Out-File $datapath -Append
    Write-Output "" | Out-File $datapath -Append
    Write-Output "URLs for Proxy Server" | Out-File $datapath -Append
    ($flatUrls.url | Sort-Object -Unique) -join "," | Out-File $datapath -Append
}
else {
    Write-Host "Office 365 worldwide commercial service instance endpoints are up-to-date."
}
```

## <a name="example-python-script"></a>Python-Beispielskript

Hier ist ein Python-Skript, das mit Python 3.6.3 unter Windows 10 getestet wurde. Sie können es ausführen, um festzustellen, ob es Aktionen gibt, die Sie für aktualisierte Daten ausführen müssen. Dieses Skript überprüft die Versionsnummer für Endpunkte mit der Instanz von Office 365 weltweit. Wenn eine Änderung vorhanden ist, lädt es die Endpunkte herunter und filtert nach den Endpunkten der Kategorie _Zulassen_ und _Optimieren_. Außerdem verwendet es eine eindeutige ClientRequestId über mehrere Anrufe hinweg und speichert die aktuelle Version in einer temporären Datei. Sie sollten dieses Skript einmal pro Stunde aufrufen, um zu überprüfen, ob ein Versionsupdate vorhanden ist.

```python
import json
import tempfile
from pathlib import Path
import urllib.request
import uuid
# helper to call the webservice and parse the response
def webApiGet(methodName, instanceName, clientRequestId):
    ws = "https://endpoints.office.com"
    requestPath = ws + '/' + methodName + '/' + instanceName + '?clientRequestId=' + clientRequestId
    request = urllib.request.Request(requestPath)
    with urllib.request.urlopen(request) as response:
        return json.loads(response.read().decode())
# path where client ID and latest version number will be stored
datapath = Path(tempfile.gettempdir() + '/endpoints_clientid_latestversion.txt')
# fetch client ID and version if data exists; otherwise create new file
if datapath.exists():
    with open(datapath, 'r') as fin:
        clientRequestId = fin.readline().strip()
        latestVersion = fin.readline().strip()
else:
    clientRequestId = str(uuid.uuid4())
    latestVersion = '0000000000'
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + latestVersion)
# call version method to check the latest version, and pull new data if version number is different
version = webApiGet('version', 'Worldwide', clientRequestId)
if version['latest'] > latestVersion:
    print('New version of Office 365 worldwide commercial service instance endpoints detected')
    # write the new version number to the data file
    with open(datapath, 'w') as fout:
        fout.write(clientRequestId + '\n' + version['latest'])
    # invoke endpoints method to get the new data
    endpointSets = webApiGet('endpoints', 'Worldwide', clientRequestId)
    # filter results for Allow and Optimize endpoints, and transform these into tuples with port and category
    flatUrls = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            category = endpointSet['category']
            urls = endpointSet['urls'] if 'urls' in endpointSet else []
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatUrls.extend([(category, url, tcpPorts, udpPorts) for url in urls])
    flatIps = []
    for endpointSet in endpointSets:
        if endpointSet['category'] in ('Optimize', 'Allow'):
            ips = endpointSet['ips'] if 'ips' in endpointSet else []
            category = endpointSet['category']
            # IPv4 strings have dots while IPv6 strings have colons
            ip4s = [ip for ip in ips if '.' in ip]
            tcpPorts = endpointSet['tcpPorts'] if 'tcpPorts' in endpointSet else ''
            udpPorts = endpointSet['udpPorts'] if 'udpPorts' in endpointSet else ''
            flatIps.extend([(category, ip, tcpPorts, udpPorts) for ip in ip4s])
    print('IPv4 Firewall IP Address Ranges')
    print(','.join(sorted(set([ip for (category, ip, tcpPorts, udpPorts) in flatIps]))))
    print('URLs for Proxy Server')
    print(','.join(sorted(set([url for (category, url, tcpPorts, udpPorts) in flatUrls]))))

    # TODO send mail (e.g. with smtplib/email modules) with new endpoints data
else:
    print('Office 365 worldwide commercial service instance endpoints are up-to-date')
```

## <a name="web-service-interface-versioning"></a>Versionsverwaltung der Webdienstschnittstelle

In der Zukunft sind möglicherweise Updates für die Parameter oder die Ergebnisse für diese Webdienstmethoden erforderlich. Nachdem die allgemein verfügbare Version dieser Webdienste veröffentlicht wurde, bemüht sich Microsoft in angemessener Weise, bedeutende Updates im Hinblick auf den Webdienst im Vorfeld anzukündigen. Wenn Microsoft davon ausgeht, dass für ein Update Änderungen an Clients erforderlich sind, die den Webdienst nutzen, behält Microsoft die vorherige Version (eine Version zurück) des verfügbaren Webdiensts für mindestens 12 Monate nach der Veröffentlichung der neuen Version bei. Kunden, die während dieses Zeitraums nicht aktualisieren, können möglicherweise nicht mehr auf den Webdienst und die zugehörigen Methoden zugreifen. Kunden müssen sicherstellen, dass Clients des Webdiensts weiterhin ohne Fehler funktionieren, wenn die folgenden Änderungen an der Webdienst-Schnittstellensignatur vorgenommen werden:

- Hinzufügen eines neuen optionalen Parameters zu einer vorhandenen Webmethode, die nicht notwendigerweise von älteren Clients bereitgestellt werden muss und das Ergebnis nicht beeinträchtigt, das ein älterer Client erhält.
- Hinzufügen eines neuen benannten Attributs zu einem der REST-Antwortelemente oder zusätzlicher Spalten zur Antwort-CSV.
- Hinzufügen einer neuen Webmethode unter einem neuen Namen, die nicht von älteren Clients aufgerufen wird.

## <a name="update-notifications"></a>Updatebenachrichtigungen

Sie können einige unterschiedliche Methoden nutzen, um E-Mail-Benachrichtigungen zu erhalten, wenn Änderungen an den IP-Adressen und URLs im Webdienst veröffentlicht werden.

- Wenn Sie eine Microsoft Flow-Lösung verwenden möchten, lesen Sie [Verwenden von Microsoft Flow, um eine E-Mail wegen Änderungen an Office 365-IP-Adressen und -URLs zu erhalten](https://techcommunity.microsoft.com/t5/Office-365-Networking/Use-Microsoft-Flow-to-receive-an-email-for-changes-to-Office-365/m-p/240651).
- Um eine Azure Logic App mithilfe einer ARM-Vorlage bereitzustellen, lesen Sie [Office 365-Updatebenachrichtigung (v1.1)](https://aka.ms/ipurlws-updates-template).
- Wenn Sie Ihr eigenes Benachrichtigungsskript mithilfe von PowerShell schreiben möchten, lesen Sie [Send-MailMessage](/powershell/module/microsoft.powershell.utility/send-mailmessage).

## <a name="exporting-a-proxy-pac-file"></a>Exportieren einer Proxy-PAC-Datei

[Get-PacFile](https://www.powershellgallery.com/packages/Get-PacFile) ist ein PowerShell-Skript, das die neuesten Netzwerkendpunkte aus dem IP-Adress- und URL-Webdienst von Office 365 liest und eine PAC-Beispieldatei erstellt. Informationen zur Verwendung von Get-PacFile finden Sie unter [Verwenden einer PAC-Datei für das direkte Routing von wichtigem Office 365-Datenverkehr](managing-office-365-endpoints.md#use-a-pac-file-for-direct-routing-of-vital-office-365-traffic).

## <a name="related-topics"></a>Verwandte Themen
  
[URLs und IP-Adressbereiche für Office 365](https://support.office.com/article/8548a211-3fe7-47cb-abb1-355ea5aa88a2)

[Verwalten von Office 365-Endpunkten](managing-office-365-endpoints.md)
  
[Häufig gestellte Fragen zu Office 365-Endpunkten](https://support.office.com/article/d4088321-1c89-4b96-9c99-54c75cae2e6d)

[Prinzipien von Office 365-Netzwerkverbindungen](microsoft-365-network-connectivity-principles.md)

[Office 365-Netzwerk- und Leistungsoptimierung](network-planning-and-performance.md)

[Bewerten der Office 365-Netzwerkkonnektivität](assessing-network-connectivity.md)
  
[Medienqualität und Netzwerkverbindungsleistung in Skype for Business Online](https://support.office.com/article/5fe3e01b-34cf-44e0-b897-b0b2a83f0917)
  
[Optimieren Ihres Netzwerks für Skype for Business Online](https://support.office.com/article/b363bdca-b00d-4150-96c3-ec7eab5a8a43)

[Office 365-Leistungsoptimierung mit Basisplänen und Leistungsverlauf](performance-tuning-using-baselines-and-history.md)
  
[Plan zur Problembehandlung für Office 365](performance-troubleshooting-plan.md)
