---
title: Navigationsoptionen für SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 4/7/2020
audience: Admin
ms.topic: overview
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
- SPO160
- MET150
ms.assetid: adb92b80-b342-4ecb-99a1-da2a2b4782eb
description: In diesem Artikel werden Navigationsoptionenswebsites mit aktivierter SharePoint in SharePoint Online beschrieben.
ms.openlocfilehash: b5989bf26ebf7bb1452f983af89a6e6739821d53
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923624"
---
# <a name="navigation-options-for-sharepoint-online"></a>Navigationsoptionen für SharePoint Online

In diesem Artikel werden Navigationsoptionenswebsites mit aktivierter SharePoint in SharePoint Online beschrieben. Die Auswahl und Konfiguration der Navigation wirkt sich erheblich auf die Leistung und Skalierbarkeit von Websites in SharePoint Online aus. Die SharePoint Veröffentlichungswebsitevorlage sollte nur verwendet werden, wenn dies für ein zentrales Portal erforderlich ist, und das Veröffentlichungsfeature sollte nur auf bestimmten Websites und nur dann aktiviert werden, wenn dies absolut erforderlich ist, da es sich bei falscher Verwendung auf die Leistung auswirken kann.

>[!NOTE]
>Wenn Sie moderne Navigationsoptionen wie SharePoint, kaskadierende Navigation oder Hubnavigation verwenden, gilt dieser Artikel nicht für Ihre Website. Moderne SharePoint nutzen eine flachere Websitehierarchie und ein Hub-and-Spoke-Modell. Auf diese Weise können viele Szenarien erreicht werden, für die keine Verwendung des features SharePoint erforderlich ist.

## <a name="overview-of-navigation-options"></a>Übersicht über Navigationsoptionen

Die Konfiguration des Navigationsanbieters kann sich erheblich auf die Leistung für die gesamte Website auswirken, und es ist sorgfältig zu berücksichtigen, einen Navigationsanbieter und eine Konfiguration zu wählen, die effektiv für die Anforderungen einer website SharePoint wird. Es gibt zwei einsatzfertige Navigationsanbieter sowie benutzerdefinierte Navigationsimplementierung.

Die erste Option, [**Strukturnavigation,**](#using-structural-navigation-in-sharepoint-online)ist die empfohlene Navigationsoption in SharePoint Online für klassische Sharepoint-Websites, wenn Sie die zwischenspeicherung der strukturbaulichen Navigation für **Ihre Website aktivieren.** Dieser Navigationsanbieter zeigt die Navigationselemente unterhalb der aktuellen Website und optional die aktuelle Website und deren gleichgeordnete Elemente an. Es bietet zusätzliche Funktionen, wie z. B. die Sicherheitstrimmerung und die Aufzählung der Websitestruktur. Wenn die Zwischenspeicherung deaktiviert ist, wirkt sich dies negativ auf die Leistung und Skalierbarkeit aus und unterliegt möglicherweise einer Einschränkung.

Die zweite Option, [**verwaltete Navigation (Metadaten),**](#using-managed-navigation-and-metadata-in-sharepoint-online)stellt Navigationselemente mithilfe eines Ausdruckssatz für verwaltete Metadaten dar. Es wird empfohlen, die Sicherheitstrimmerung zu deaktivieren, sofern dies nicht erforderlich ist. Die Sicherheitstrimmerung ist als Standardeinstellung für diesen Navigationsanbieter aktiviert. Viele Websites erfordern jedoch keinen Aufwand für die Sicherheitsbeschneidung, da Navigationselemente häufig für alle Benutzer der Website konsistent sind. Mit der empfohlenen Konfiguration zum Deaktivieren der Sicherheitstrimmer erfordert dieser Navigationsanbieter keine Aufzählen der Websitestruktur und ist hochgradig skalierbar mit akzeptablen Auswirkungen auf die Leistung.

Neben den einsatzfertigen Navigationsanbietern haben viele Kunden erfolgreich alternative benutzerdefinierte Navigationsimplementierung implementiert. Weitere [Informationen finden Sie unter Search-driven client-side scripting](#using-search-driven-client-side-scripting) in this article.
  
## <a name="pros-and-cons-of-sharepoint-online-navigation-options"></a>Vor- und Nachteile SharePoint Onlinenavigationsoptionen

In der folgenden Tabelle sind die Vor- und Nachteile der einzelnen Optionen zusammengefasst.

|Strukturnavigation  |Verwaltete Navigation  |Suchgesteuerte Navigation  |Benutzerdefinierter Navigationsanbieter  |
|---------|---------|---------|---------|
|Vorteile:<br/><br/>Einfach zu warten<br/>Sicherheit gekürzt<br/>Automatische Aktualisierung innerhalb von 24 Stunden, wenn Inhalte geändert werden<br/>     |Vorteile:<br/><br/>Einfach zu warten<br/>|Vorteile:<br/><br/>Sicherheit gekürzt<br/>Automatische Aktualisierungen beim Hinzufügen von Websites<br/>Schnelle Ladezeit und lokal zwischengespeicherte Navigationsstruktur<br/>|Vorteile:<br/><br/>Größere Auswahl an verfügbaren Optionen<br/>Schnelles Laden bei ordnungsgemäßer Zwischenspeicherung<br/>Viele Optionen funktionieren gut mit dem design für reaktionsschnelle Seiten<br/>|
|Nachteile:<br/><br/>**Wirkt sich auf die Leistung aus, wenn die Zwischenspeicherung deaktiviert ist**<br/>Unterliegt Drosselung<br/>|Nachteile:<br/><br/>Nicht automatisch aktualisiert, um die Websitestruktur wider zuspiegeln<br/>**Wirkt sich auf die Leistung aus, wenn die Sicherheitsbeschneidung aktiviert ist** oder wenn die Navigationsstruktur komplex ist<br/>|Nachteile:<br/><br/>Keine Möglichkeit zum einfachen Bestellen von Websites<br/>Erfordert eine Anpassung der Gestaltungsseite (technische Kenntnisse erforderlich)<br/>|Nachteile:<br/><br/>Benutzerdefinierte Entwicklung ist erforderlich<br/>Externe Datenquelle/gespeicherter Cache ist erforderlich, z. B. Azure<br/>|

Die am besten geeignete Option für Ihre Website hängt von Ihren Websiteanforderungen und Ihrer technischen Leistungsfähigkeit ab. Wenn Sie einen einfach zu konfigurierenden Navigationsanbieter wünschen, der automatisch [](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43) aktualisiert wird, wenn Inhalte geändert werden, ist die strukturelle Navigation mit aktivierter Zwischenspeicherung eine gute Option.

>[!NOTE]
>Die Anwendung desselben Prinzips wie SharePoint Websites durch Die Vereinfachung der gesamten Websitestruktur auf eine flacheren, nicht hierarchischen Strukturen verbessert die Leistung und vereinfacht den Wechsel zu modernen SharePoint Websites. Dies bedeutet, dass anstelle einer einzigen Websitesammlung mit Hunderten von Websites (Unterwebsites) ein besserer Ansatz besteht, viele Websitesammlungen mit sehr wenigen Unterwebsites (Unterwebsites) zu haben.

## <a name="analyzing-navigation-performance-in-sharepoint-online"></a>Analysieren der Navigationsleistung in SharePoint Online

Das [Tool Seitendiagnose für SharePoint](./page-diagnostics-for-spo.md) ist eine Browsererweiterung für Microsoft Edge- und Chrome-Browser, die sowohl SharePoint moderne Portal- als auch klassische Veröffentlichungswebsiteseiten analysiert. Dieses Tool funktioniert nur für SharePoint Online und kann nicht auf einer SharePoint verwendet werden.

Das Tool generiert einen Bericht für jede analysierte Seite, in dem gezeigt wird, wie die Seite mit einem vordefinierten Satz von Regeln arbeitet, und zeigt detaillierte Informationen an, wenn ergebnisse für einen Test außerhalb des Basiswerts fallen. SharePoint Onlineadministratoren und Designer können das Tool verwenden, um Leistungsprobleme zu beheben, um sicherzustellen, dass neue Seiten vor der Veröffentlichung optimiert werden.

**SPRequestDuration** ist insbesondere die Zeit, die es dauert, SharePoint die Seite zu verarbeiten. Eine hohe Navigation (z. B. Seiten in der Navigation), komplexe Websitehierarchien sowie andere Konfigurations- und Topologieoptionen können erheblich zu längeren Laufzeiten beitragen.

## <a name="using-structural-navigation-in-sharepoint-online"></a>Verwenden der Strukturnavigation in SharePoint Online

Dies ist die standardmäßig verwendete out-of-the-box-Navigation und die unkomplizierteste Lösung. Es ist keine Anpassung erforderlich, und ein nicht technischer Benutzer kann auch einfach Elemente hinzufügen, Elemente ausblenden und die Navigation auf der Einstellungsseite verwalten. Es wird [empfohlen, die Zwischenspeicherung](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)zu aktivieren, andernfalls gibt es einen kostspieligen Leistungs-Trade-Off.

### <a name="how-to-implement-structural-navigation-caching"></a>Implementieren der strukturellen Navigations-Zwischenspeicherung

Unter **Site Einstellungen** Look and Feel Navigation können Sie überprüfen, ob die Strukturnavigation für die globale oder die aktuelle Navigation ausgewählt  >    >  ist. Das **Auswählen von Seiten** anzeigen hat negative Auswirkungen auf die Leistung.

![Strukturnavigation mit ausgewählten Unterwebsites anzeigen](../media/SPONavOptionsStructuredShowSubsites.png)

Die Zwischenspeicherung kann auf Websitesammlungsebene und auf Websiteebene aktiviert oder deaktiviert werden und ist standardmäßig für beide aktiviert. Aktivieren Sie zum Aktivieren auf Websitesammlungsebene unter Websitesammlungsverwaltungsnavigation **Einstellungen** Websitesammlungsverwaltung das Kontrollkästchen  >    >   **Zwischenspeichern aktivieren.**

![Aktivieren der Zwischenspeicherung auf Standortebene](../media/structural-nav/structural-nav-caching-site-coll.png)

Aktivieren Sie zum Aktivieren auf Standortebene unter **Website Einstellungen** Navigation das Kontrollkästchen  >   **Zwischenspeicherung aktivieren.**

![Aktivieren der Zwischenspeicherung auf Standortebene](../media/structural-nav/structural-nav-caching-site.png)

## <a name="using-managed-navigation-and-metadata-in-sharepoint-online"></a>Verwenden von verwalteter Navigation und Metadaten in SharePoint Online

Die verwaltete Navigation ist eine weitere out-of-the-box-Option, die Sie verwenden können, um die meisten der gleichen Funktionen wie die Strukturnavigation neu zu erstellen. Verwaltete Metadaten können so konfiguriert werden, dass die Sicherheitsbeschneidung aktiviert oder deaktiviert ist. Bei deaktivierter Sicherheitstrimmerung ist die verwaltete Navigation relativ effizient, da sie alle Navigationslinks mit einer konstanten Anzahl von Serveraufrufen lädt. Durch die Aktivierung der Sicherheitstrimmerung werden jedoch einige der Leistungsvorteile der verwalteten Navigation negiert.

Wenn Sie die Sicherheitsbeschneidung aktivieren müssen, wird empfohlen, dass Sie:

- Aktualisieren aller benutzerfreundlichen URL-Links auf einfache Links
- Hinzufügen erforderlicher Knoten zur Sicherheitsbeschneidung als benutzerfreundliche URLs
- Beschränken sie die Anzahl der Navigationselemente auf nicht mehr als 100 und nicht mehr als 3 Ebenen tief

Viele Websites erfordern keine Sicherheitsbeschneidung, da die Navigationsstruktur häufig für alle Benutzer der Website konsistent ist. Wenn die Sicherheitsentschneidung deaktiviert ist und der Navigation ein Link hinzugefügt wird, auf den nicht alle Benutzer Zugriff haben, wird der Link weiterhin angezeigt, führt aber zu einer Zugriffs verweigerten Nachricht. Es besteht kein Risiko eines unbeabsichtigten Zugriffs auf den Inhalt.

### <a name="how-to-implement-managed-navigation-and-the-results"></a>Implementieren der verwalteten Navigation und der Ergebnisse

Es gibt mehrere Artikel zu docs.microsoft.com informationen zu den Details der verwalteten Navigation. Beispiel: Übersicht über [die verwaltete Navigation in SharePoint Server](/sharepoint/administration/overview-of-managed-navigation).

Zum Implementieren der verwalteten Navigation richten Sie Begriffe mit URLs ein, die der Navigationsstruktur der Website entspricht. Die verwaltete Navigation kann sogar manuell kuratiert werden, um die Strukturnavigation in vielen Fällen zu ersetzen. Beispiel:

![SharePoint Onlinewebsitestruktur](../media/SPONavOptionsListOfSites.png))

## <a name="using-search-driven-client-side-scripting"></a>Verwenden von suchgesteuertem clientseitigem Skripting

Eine allgemeine Klasse von benutzerdefinierten Navigationsimplementierung umfasst vom Client gerenderte Entwurfsmuster, die einen lokalen Cache von Navigationsknoten speichern.

Diese Navigationsanbieter haben einige wichtige Vorteile:

- Sie funktionieren in der Regel gut mit ansprechenden Seitendesigns.
- Sie sind äußerst skalierbar und performant, da sie ohne Ressourcenkosten gerendert werden können (und nach einem Timeout im Hintergrund aktualisiert werden).
- Diese Navigationsanbieter können Navigationsdaten mithilfe verschiedener Strategien abrufen, von einfachen statischen Konfigurationen bis hin zu verschiedenen dynamischen Datenanbietern.

Ein Beispiel für einen Datenanbieter ist die Verwendung einer suchgesteuerten **Navigation,** die flexibilität zum Aufzählen von Navigationsknoten und zum effizienten Behandeln von Sicherheitstrimmern ermöglicht.

Es gibt weitere beliebte Optionen zum Erstellen von **benutzerdefinierten Navigationsanbietern.** Weitere Anleitungen zum Erstellen eines benutzerdefinierten [Navigationsanbieters finden Sie SharePoint Navigationslösungen](/sharepoint/dev/solution-guidance/portal-navigation) für SharePoint Onlineportale.

Mithilfe der Suche können Sie die im Hintergrund aufgebauten Indizes mithilfe einer kontinuierlichen Durchforstung nutzen. Die Suchergebnisse werden aus dem Suchindex gezogen, und die Ergebnisse sind sicherheitsbeschnitten. Dies ist in der Regel schneller als bei nicht verwendeten Navigationsanbietern, wenn eine Sicherheitsbeschneidung erforderlich ist. Die Verwendung der Suche nach struktureller Navigation, insbesondere wenn Sie über eine komplexe Websitestruktur verfügen, beschleunigt die Ladezeit der Seite erheblich. Der Hauptvorteil dieser gegenüber der verwalteten Navigation ist, dass Sie von der Sicherheitstrimmerung profitieren.

Dieser Ansatz umfasst das Erstellen einer benutzerdefinierten Gestaltungsmasterseite und das Ersetzen des out-of-the-box-Navigationscodes durch benutzerdefinierten HTML-Code. Gehen Sie wie im folgenden Beispiel beschrieben vor, um den Navigationscode in der Datei zu `seattle.html` ersetzen. In diesem Beispiel öffnen Sie die Datei und ersetzen das `seattle.html` gesamte Element `id="DeltaTopNavigation"` durch benutzerdefinierten HTML-Code.

### <a name="example-replace-the-out-of-the-box-navigation-code-in-a-master-page"></a>Beispiel: Ersetzen des out-of-the-box-Navigationscodes in einer Masterseite

1. Navigieren Sie zur Seite Website Einstellungen Seite.
2. Öffnen Sie den Masterseitenkatalog, indem Sie auf **Masterseiten klicken.**
3. Von hier aus können Sie durch die Bibliothek navigieren und die Datei `seattle.master` herunterladen.
4. Bearbeiten Sie den Code mithilfe eines Texteditors, und löschen Sie den Codeblock im folgenden Screenshot.<br/>![Löschen des angezeigten Codeblocks](../media/SPONavOptionsDeleteCodeBlock.png)<br/>
5. Entfernen Sie den Code zwischen `<SharePoint:AjaxDelta id="DeltaTopNavigation">` den tags `<\SharePoint:AjaxDelta>` und, und ersetzen Sie ihn durch den folgenden Codeausschnitt:<br/>

```javascript
<div id="loading">
  <!--Replace with path to loading image.-->
  <div style="background-image: url(''); height: 22px; width: 22px; ">
  </div>
</div>
<!-- Main Content-->
<div id="navContainer" style="display:none">
    <div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
        </a>
        <ul id="menu" data-bind="foreach: $data.children" style="padding-left:20px">
            <li class="static dynamic-children level1">
                <a class="static dynamic-children menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

                 <!-- ko if: children.length > 0-->
                    <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                <!-- ko if: children.length == 0-->
                    <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
                        <span class="menu-item-text" data-bind="text: item.Title">
                        </span>
                    </span>
                <!-- /ko -->
                </a>

                <!-- ko if: children.length > 0-->
                <ul id="menu"  data-bind="foreach: children;" class="dynamic  level2" >
                    <li class="dynamic level2">
                        <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline  ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">

          <!-- ko if: children.length > 0-->
          <span aria-haspopup="true" class="additional-background ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
           <!-- /ko -->
          <!-- ko if: children.length == 0-->
          <span aria-haspopup="true" class="ms-navedit-flyoutArrow dynamic-children">
           <span class="menu-item-text" data-bind="text: item.Title">
           </span>
          </span>
          <!-- /ko -->
                        </a>
          <!-- ko if: children.length > 0-->
         <ul id="menu" data-bind="foreach: children;" class="dynamic level3" >
          <li class="dynamic level3">
           <a class="dynamic menu-item ms-core-listMenu-item ms-displayInline ms-navedit-linkNode" data-bind="attr: { href: item.Url, title: item.Title }">
            <span class="menu-item-text" data-bind="text: item.Title">
            </span>
           </a>
          </li>
         </ul>
           <!-- /ko -->
                    </li>
                </ul>
                <!-- /ko -->
            </li>
        </ul>
    </div>
</div>
```

<br/>
6. Ersetzen Sie die URL im Laden des Bildankertags am Anfang durch einen Link zu einem Ladenimage in Ihrer Websitesammlung. Nachdem Sie die Änderungen vorgenommen haben, benennen Sie die Datei um, und laden Sie sie dann in den Masterseitenkatalog hoch. Dadurch wird eine neue .master-Datei generiert.<br/>
7. Dieser HTML-Code ist das grundlegende Markup, das von den suchergebnissen aufgefüllt wird, die aus dem JavaScript-Code zurückgegeben werden. Sie müssen den Code bearbeiten, um den Wert für var root = "Websitesammlungs-URL" zu ändern, wie im folgenden Codeausschnitt gezeigt:<br/>

```javascript
var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
```

<br/>
8. Die Ergebnisse werden dem self.nodes-Array zugewiesen, und aus den Objekten wird eine Hierarchie erstellt, indem linq.js die Ausgabe einer Arrayhierarchie self.hierarchy zugewiesen wird. Dieses Array ist das Objekt, das an den HTML-Code gebunden ist. Dies geschieht in der toggleView()-Funktion, indem das self-Objekt an die ko.applyBinding()-Funktion übergeben wird.<br/>Dadurch wird das Hierarchiearray an den folgenden HTML-Code gebunden:<br/>

```javascript
<div data-bind="foreach: hierarchy" class="noindex ms-core-listMenu-horizontalBox">
```

Die Ereignishandler für und werden der Navigation auf oberster Ebene hinzugefügt, um die Dropdownmenüs der Unterwebsite zu behandeln, die in der `mouseenter` `mouseexit` Funktion durchgeführt `addEventsToElements()` werden.

In unserem komplexen Navigationsbeispiel zeigt eine neue Seitenlast ohne lokale Zwischenspeicherung, dass die auf dem Server auf dem Server verbrachte Zeit von der Benchmarkstrukturnavigation abgeschnitten wurde, um ein ähnliches Ergebnis wie den verwalteten Navigationsansatz zu erhalten.

### <a name="about-the-javascript-file"></a>Informationen zur JavaScript-Datei...

>[!NOTE]
>Wenn Sie benutzerdefiniertes JavaScript verwenden, stellen Sie sicher, dass CDN aktiviert ist und sich die Datei an einem CDN befindet.

Die gesamte JavaScript-Datei lautet wie folgt:

```javascript
//Models and Namespaces
var SPOCustom = SPOCustom || {};
SPOCustom.Models = SPOCustom.Models || {}
SPOCustom.Models.NavigationNode = function () {

    this.Url = ko.observable("");
    this.Title = ko.observable("");
    this.Parent = ko.observable("");

};

var root = "https://spperformance.sharepoint.com/sites/NavigationBySearch";
var baseUrl = root + "/_api/search/query?querytext=";
var query = baseUrl + "'contentClass=\"STS_Web\"+path:" + root + "'&trimduplicates=false&rowlimit=300";

var baseRequest = {
    url: "",
    type: ""
};


//Parses a local object from JSON search result.
function getNavigationFromDto(dto) {
    var item = new SPOCustom.Models.NavigationNode();
    if (dto != undefined) {

        var webTemplate = getSearchResultsValue(dto.Cells.results, 'WebTemplate');

        if (webTemplate != "APP") {
            item.Title(getSearchResultsValue(dto.Cells.results, 'Title')); //Key = Title
            item.Url(getSearchResultsValue(dto.Cells.results, 'Path')); //Key = Path
            item.Parent(getSearchResultsValue(dto.Cells.results, 'ParentLink')); //Key = ParentLink
        }

    }
    return item;
}

function getSearchResultsValue(results, key) {

    for (i = 0; i < results.length; i++) {
        if (results[i].Key == key) {
            return results[i].Value;
        }
    }
    return null;
}

//Parse a local object from the serialized cache.
function getNavigationFromCache(dto) {
    var item = new SPOCustom.Models.NavigationNode();

    if (dto != undefined) {

        item.Title(dto.Title);
        item.Url(dto.Url);
        item.Parent(dto.Parent);
    }

    return item;
}

/* create a new OData request for JSON response */
function getRequest(endpoint) {
    var request = baseRequest;
    request.type = "GET";
    request.url = endpoint;
    request.headers = { ACCEPT: "application/json;odata=verbose" };
    return request;
};

/* Navigation Module*/
function NavigationViewModel() {
    "use strict";
    var self = this;
    self.nodes = ko.observableArray([]);
    self.hierarchy = ko.observableArray([]);;
    self.loadNavigatioNodes = function () {
        //Check local storage for cached navigation datasource.
        var fromStorage = localStorage["nodesCache"];
        if (false) {
            var cachedNodes = JSON.parse(localStorage["nodesCache"]);

            if (cachedNodes && timeStamp) {
                //Check for cache expiration. Currently set to 3 hrs.
                var now = new Date();
                var diff = now.getTime() - timeStamp;
                if (Math.round(diff / (1000 * 60 * 60)) < 3) {

                    //return from cache.
                    var cacheResults = [];
                    $.each(cachedNodes, function (i, item) {
                        var nodeitem = getNavigationFromCache(item, true);
                        cacheResults.push(nodeitem);
                    });

                    self.buildHierarchy(cacheResults);
                    self.toggleView();
                    addEventsToElements();
                    return;
                }
            }
        }
        //No cache hit, REST call required.
        self.queryRemoteInterface();
    };

    //Executes a REST call and builds the navigation hierarchy.
    self.queryRemoteInterface = function () {
        var oDataRequest = getRequest(query);
        $.ajax(oDataRequest).done(function (data) {
            var results = [];
            $.each(data.d.query.PrimaryQueryResult.RelevantResults.Table.Rows.results, function (i, item) {

                if (i == 0) {
                    //Add root element.
                    var rootItem = new SPOCustom.Models.NavigationNode();
                    rootItem.Title("Root");
                    rootItem.Url(root);
                    rootItem.Parent(null);
                    results.push(rootItem);
                }
                var navItem = getNavigationFromDto(item);
                results.push(navItem);
            });
            //Add to local cache
            localStorage["nodesCache"] = ko.toJSON(results);

            localStorage["nodesCachedAt"] = new Date().getTime();
            self.nodes(results);
            if (self.nodes().length > 0) {
                var unsortedArray = self.nodes();
                var sortedArray = unsortedArray.sort(self.sortObjectsInArray);

                self.buildHierarchy(sortedArray);
                self.toggleView();
                addEventsToElements();
            }
        }).fail(function () {
            //Handle error here!!
            $("#loading").hide();
            $("#error").show();
        });
    };
    self.toggleView = function () {
        var navContainer = document.getElementById("navContainer");
        ko.applyBindings(self, navContainer);
        $("#loading").hide();
        $("#navContainer").show();

    };
    //Uses linq.js to build the navigation tree.
    self.buildHierarchy = function (enumerable) {
        self.hierarchy(Enumerable.From(enumerable).ByHierarchy(function (d) {
            return d.Parent() == null;
        }, function (parent, child) {
            if (parent.Url() == null || child.Parent() == null)
                return false;
            return parent.Url().toUpperCase() == child.Parent().toUpperCase();
        }).ToArray());

        self.sortChildren(self.hierarchy()[0]);
    };


    self.sortChildren = function (parent) {

        // sjip processing if no children
        if (!parent || !parent.children || parent.children.length === 0) {
            return;
        }

        parent.children = parent.children.sort(self.sortObjectsInArray2);

        for (var i = 0; i < parent.children.length; i++) {
            var elem = parent.children[i];

            if (elem.children && elem.children.length > 0) {
                self.sortChildren(elem);
            }
        }
    };

    // ByHierarchy method breaks the sorting in chrome and firefox
    // we need to resort  as ascending
    self.sortObjectsInArray2 = function (a, b) {
        if (a.item.Title() > b.item.Title())
            return 1;
        if (a.item.Title() < b.item.Title())
            return -1;
        return 0;
    };


    self.sortObjectsInArray = function (a, b) {
        if (a.Title() > b.Title())
            return -1;
        if (a.Title() < b.Title())
            return 1;
        return 0;
    }
}

//Loads the navigation on load and binds the event handlers for mouse interaction.
function InitCustomNav() {
    var viewModel = new NavigationViewModel();
    viewModel.loadNavigatioNodes();
}

function addEventsToElements() {
    //events.
      $("li.level1").mouseover(function () {
          var position = $(this).position();
          $(this).find("ul.level2").css({ width: 100, left: position.left + 10, top: 50 });
      })
   .mouseout(function () {
     $(this).find("ul.level2").css({  left: -99999, top: 0 });
   
    });
   
     $("li.level2").mouseover(function () {
          var position = $(this).position();
          console.log(JSON.stringify(position));
          $(this).find("ul.level3").css({ width: 100, left: position.left + 95, top:  position.top});
      })
   .mouseout(function () {
     $(this).find("ul.level3").css({  left: -99999, top: 0 });
    });
} _spBodyOnLoadFunctionNames.push("InitCustomNav");

```

Um den oben in der Funktion gezeigten Code zusammenzufassen, wird eine erstellt, und dann wird die `jQuery $(document).ready` Funktion für dieses Objekt `viewModel object` `loadNavigationNodes()` aufgerufen. Diese Funktion lädt entweder die zuvor erstellten Navigationshierarchie, die im lokalen HTML5-Speicher des Clientbrowsers gespeichert ist, oder ruft die Funktion `queryRemoteInterface()` auf.

`QueryRemoteInterface()` erstellt eine Anforderung mithilfe der Funktion mit dem zuvor im Skript definierten Abfrageparameter und gibt dann `getRequest()` Daten vom Server zurück. Diese Daten sind im Wesentlichen ein Array aller Websites in der Websitesammlung, die als Datenübertragungsobjekte mit verschiedenen Eigenschaften dargestellt werden.

Diese Daten werden dann in die zuvor definierten Objekte analysiert, die zum Erstellen von beobachtbaren Eigenschaften für die Verwendung durch Datenbindung der Werte an den ZUVOR definierten `SPO.Models.NavigationNode` `Knockout.js` HTML-Code verwendet werden.

Die Objekte werden dann in ein Ergebnisarray hinzugefügt. Dieses Array wird mithilfe von Knockout in JSON analysiert und im lokalen Browserspeicher gespeichert, um die Leistung bei zukünftigen Seitenlasten zu verbessern.

### <a name="benefits-of-this-approach"></a>Vorteile dieses Ansatzes

Ein großer Vorteil dieses [Ansatzes](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page) ist, dass die Navigation mithilfe des lokalen HTML5-Speichers beim nächsten Laden der Seite lokal für den Benutzer gespeichert wird. Wir erhalten wesentliche Leistungsverbesserungen durch die Verwendung der Such-API für die strukturelle Navigation. Es sind jedoch einige technische Funktionen erforderlich, um diese Funktionalität auszuführen und anzupassen.

In der [Beispielimplementierung](#example-replace-the-out-of-the-box-navigation-code-in-a-master-page)werden die Websites auf die gleiche Weise wie die out-of-the-box-Strukturnavigation geordnet. alphabetische Reihenfolge. Wenn Sie von dieser Reihenfolge abweichen möchten, wäre die Entwicklung und Wartung komplizierter. Außerdem müssen Sie bei diesem Ansatz von den unterstützten Masterseiten abweichen. Wenn die benutzerdefinierte Masterseite nicht verwaltet wird, verpasst Ihre Website Updates und Verbesserungen, die Microsoft an den Masterseiten vorgenommen hat.

Der [obige Code](#about-the-javascript-file) hat die folgenden Abhängigkeiten:

- jQuery - https://jquery.com/
- KnockoutJS – https://knockoutjs.com/
- Linq.js - https://linqjs.codeplex.com/ oder github.com/neuecc/linq.js

Die aktuelle Version von LinqJS enthält nicht die im obigen Code verwendete ByHierarchy-Methode und bricht den Navigationscode auf. Um dies zu beheben, fügen Sie der Datei Linq.js vor der Zeile die folgende Methode `Flatten: function ()` hinzu.

```javascript
ByHierarchy: function(firstLevel, connectBy, orderBy, ascending, parent) {
     ascending = ascending == undefined ? true : ascending;
     var orderMethod = ascending == true ? 'OrderBy' : 'OrderByDescending';
     var source = this;
     firstLevel = Utils.CreateLambda(firstLevel);
     connectBy = Utils.CreateLambda(connectBy);
     orderBy = Utils.CreateLambda(orderBy);

     //Initiate or increase level
     var level = parent === undefined ? 1 : parent.level + 1;

    return new Enumerable(function() {
         var enumerator;
         var index = 0;

        var createLevel = function() {
                 var obj = {
                     item: enumerator.Current(),
                     level : level
                 };
                 obj.children = Enumerable.From(source).ByHierarchy(firstLevel, connectBy, orderBy, ascending, obj);
                 if (orderBy !== undefined) {
                     obj.children = obj.children[orderMethod](function(d) {
                         return orderBy(d.item); //unwrap the actual item for sort to work
                     });
                 }
                 obj.children = obj.children.ToArray();
                 Enumerable.From(obj.children).ForEach(function(child) {
                     child.getParent = function() {
                         return obj;
                     };
                 });
                 return obj;
             };

        return new IEnumerator(

        function() {
             enumerator = source.GetEnumerator();
         }, function() {
             while (enumerator.MoveNext()) {
                 var returnArr;
                 if (!parent) {
                     if (firstLevel(enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }

                } else {
                     if (connectBy(parent.item, enumerator.Current(), index++)) {
                         return this.Yield(createLevel());
                     }
                 }
             }
             return false;
         }, function() {
             Utils.Dispose(enumerator);
         })
     });
 },

```
  
## <a name="related-topics"></a>Verwandte Themen

[Übersicht über die verwaltete Navigation in SharePoint Server](/sharepoint/administration/overview-of-managed-navigation)

[Zwischenspeicherung und Leistung der strukturellen Navigation](https://support.office.com/article/structural-navigation-and-performance-f163053f-8eca-4b9c-b973-36b395093b43)