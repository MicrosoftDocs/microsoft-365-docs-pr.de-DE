---
title: Konfigurieren der Suche für Microsoft 365 Multi-Geo
ms.reviewer: adwood
ms.author: tlarsen
author: tklarsen
manager: arnek
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.custom: seo-marvel-mar2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
f1.keywords:
- NOCSH
description: Erfahren Sie, wie Sie die Suche in einer Multi-Geo-Umgebung konfigurieren. Nur einige Clients, z. B. OneDrive for Business, können Ergebnisse in einer Multi-Geo-Umgebung zurückgeben.
ms.openlocfilehash: b3a96b1d0652cb954c58ae410583befa078460d9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911162"
---
# <a name="configure-search-for-microsoft-365-multi-geo"></a>Konfigurieren der Suche für Microsoft 365 Multi-Geo

In einer Multi-Geo-Umgebung besitzt jeder geografische Standort einen eigenen Suchindex und ein Suchcenter. Wenn ein Benutzer eine Suche durchführt, wird die Abfrage in alle Indizes aufgefächert, und die zurückgegebenen Ergebnisse werden zusammengeführt.

Ein Benutzer an einem geografischen Standort kann zum Beispiel nach Inhalten an einem anderen Standort oder auf einer SharePoint-Website suchen, die auf einen anderen geografischen Standort eingeschränkt ist. Wenn der Benutzer Zugriff auf diese Inhalte hat, liefert die Suche das Ergebnis.

## <a name="which-search-clients-work-in-a-multi-geo-environment"></a>Welche Suchclients können in einer Multi-Geo-Umgebung verwendet werden?

Diese Clients können von allen geografischen Standorten Ergebnisse zurückgeben:

- OneDrive for Business
- Delve
- Die SharePoint-Homepage
- Das Suchcenter
- Benutzerdefinierte Suchanwendungen, die die SharePoint-Suche-API verwenden

### <a name="onedrive-for-business"></a>OneDrive for Business

Sobald die Multi-Geo-Umgebung eingerichtet wurde, erhalten Benutzer, die eine Suche in OneDrive durchführen, Ergebnisse aus allen geografischen Standorten.

### <a name="delve"></a>Delve

Sobald die Multi-Geo-Umgebung eingerichtet wurde, erhalten Benutzer, die eine Suche in Delve durchführen, Ergebnisse aus allen geografischen Standorten.

Der Delve-Feed und die Profilkarte zeigen nur eine Vorschau der Dateien an, die sich an dem zentralen Standort befinden. Für Dateien, die sich an Satellitenstandorten befinden, wird stattdessen das Symbol für den Dateityp angezeigt.

### <a name="the-sharepoint-home-page"></a>Die SharePoint-Homepage

Sobald die Multi-Geo-Umgebung eingerichtet wurde, werden Benutzern Neuigkeiten, zuletzt verwendete und gefolgte Websites von mehreren geografischen Standorten auf ihrer SharePoint-Homepage angezeigt. Wenn sie das Suchfeld auf der SharePoint-Homepage verwenden, werden die Ergebnisse aus mehreren geografischen Standorten zusammengeführt.

### <a name="the-search-center"></a>Das Suchcenter

Sobald die Multi-Geo-Umgebung eingerichtet wurde, zeigt jedes Suchcenter weiterhin nur die Ergebnisse vom eigenen geografischen Standort an. Administratoren müssen [die Einstellungen für jedes Suchcenter ändern](#_Set_up_a_1), um Ergebnisse aus allen geografischen Standorten zu erhalten. Anschließend erhalten Benutzer, die eine Suche im Suchcenter durchführen, Ergebnisse aus allen geografischen Standorten.

### <a name="custom-search-applications"></a>Benutzerdefinierte Suchanwendungen

Wie üblich interagieren benutzerdefinierte Suchanwendungen mit den Suchindizes, indem die vorhandenen SharePoint-Suche-REST-APIs verwendet werden. Um Ergebnisse aus allen oder einigen geografischen Standorten zu erhalten, muss die Anwendung [die API aufrufen und die neuen Multi-Geo-Abfrageparameter](#_Get_custom_search) zu der Anforderung hinzufügen. Dadurch wird die Abfrage in alle geografischen Standorte aufgefächert.

## <a name="whats-different-about-search-in-a-multi-geo-environment"></a>Welche Unterschiede gibt es bei der Suche in einer Multi-Geo-Umgebung?

Einige Suchfunktionen, die Sie möglicherweise bereits kennen, funktionieren in einer Multi-Geo-Umgebung anders.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Feature</strong></th>
<th align="left"><strong>Funktionsweise</strong></th>
<th align="left"><strong>Problemumgehung</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Höhergestufte Ergebnisse</td>
<td align="left">Sie können Abfrageregeln mit höhergestuften Ergebnissen auf verschiedenen Ebenen erstellen: für den gesamten Mandanten, für eine Websitesammlung oder für eine Website. Definieren Sie in einer Multi-Geo-Umgebung höhergestufte Ergebnisse auf der Mandantenebene, wenn die Ergebnisse in den Suchcentern an allen geografischen Standorten höhergestuft werden sollen. Wenn Sie nur Ergebnisse im Suchcenter, das sich am geografischen Standort der Websitesammlung oder Website befindet, höherstufen möchten, definieren Sie die höhergestuften Ergebnisse auf der Websitesammlungs- oder Websiteebene. Diese Ergebnisse werden nicht an anderen geografischen Standorten höhergestuft.</td>
<td align="left">Wenn Sie keine unterschiedlichen höhergestuften Ergebnisse pro geografischem Standort benötigen, zum Beispiel verschiedene Regeln für Reisen, wird empfohlen, höhergestufte Ergebnisse auf Mandantenebene zu definieren.</td>
</tr>
<tr class="even">
<td align="left">Sucheinschränkungen</td>
<td align="left">Die Suche gibt Einschränkungen aus allen geografischen Standorten eines Mandanten zurück und aggregiert diese dann. Die Aggregation ist die beste Bemühung und bedeutet, dass die Anzahl der Einschränkungen nicht exakt 100%ig ist. Für die meisten suchgesteuerten Szenarien ist diese Genauigkeit ausreichend. </td>
<td align="left">Führen Sie für suchgesteuerte Anwendungen, die von der Vollständigkeit der Einschränkungen abhängig sind, eine Abfrage für jeden geografischen Standort getrennt voneinander durch.</td>
</tr>
<tr class="odd">
<td align="left"></td>
<td align="left">Das dynamische Zuordnen von Buckets für numerische Einschränkungen wird von der Multi-Geo-Suche nicht unterstützt.</td>
<td align="left">Verwenden Sie <a href="/sharepoint/dev/general-development/query-refinement-in-sharepoint">den Parameter "Discretize" für</a> numerische Einschränkungen.</td>
</tr>
<tr class="even">
<td align="left">Dokument-IDs</td>
<td align="left">Wenn Sie eine suchgesteuerte Anwendung entwickeln, die von Dokument-IDs abhängig ist, müssen Sie beachten, dass die Dokument-IDs in einer Multi-Geo-Umgebung nicht standortübergreifend eindeutig sind, sie sind jeweils pro Standort eindeutig.</td>
<td align="left">Es wurde eine Spalte hinzugefügt, die den geografischen Standort identifiziert. Verwenden Sie diese Spalte, um Eindeutigkeit zu erreichen. Diese Spalte heißt "GeoLocationSource".</td>
</tr>
<tr class="odd">
<td align="left">Anzahl der Ergebnisse</td>
<td align="left">Auf der Seite mit den Suchergebnissen werden die kombinierten Ergebnisse von den geografischen Standorten angezeigt, die Seite darf jedoch 500 Ergebnisse nicht überschreiten.</td>
<td align="left"></td>
</tr>
<tr class="even">
<td align="left">Hybridsuche</td>
<td align="left">In einer SharePoint-Hybridumgebung mit <a href="/sharepoint/hybrid/learn-about-cloud-hybrid-search-for-sharepoint">Cloudhybridsuche</a> werden lokale Inhalte dem Microsoft 365-Index des zentralen Standorts hinzugefügt.</td>
<td align="left"></td>
</tr>
</tbody>
</table>

## <a name="whats-not-supported-for-search-in-a-multi-geo-environment"></a>Was wird bei der Suche in einer Multi-Geo-Umgebung nicht unterstützt?

Einige Suchfunktionen, die Sie möglicherweise bereits kennen, werden in einer Multi-Geo-Umgebung nicht unterstützt.

<table>
<thead>
<tr class="header">
<th align="left"><strong>Suchfunktion</strong></th>
<th align="left"><strong>Hinweis</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Nur-App-Authentifizierung</td>
<td align="left">Nur-App-Authentifizierung (privilegierter Zugriff von Diensten) wird bei der Multi-Geo-Suche nicht unterstützt.</td>
</tr>
<tr class="even">
<td align="left">Gastbenutzer</td>
<td align="left">Gastbenutzer erhalten nur Ergebnisse von dem geografischen Standort, aus dem Sie die Suche durchführen.</td>
</tr>
</tbody>
</table>

## <a name="how-does-search-work-in-a-multi-geo-environment"></a>Wie funktioniert die Suche in einer Multi-Geo-Umgebung?

Alle Suchclients verwenden die vorhandenen SharePoint-Suche-REST-APIs für die Interaktion mit den Suchindizes.

![Diagramm, in dem SharePoint Interaktion von SUCH-REST-APIs mit den Suchindizes dargestellt wird](../media/configure-search-for-multi-geo-image1-1.png)

1. Ein Suchclient ruft den REST-Endpunkt für die Suche mit der Abfrageeigenschaft „EnableMultiGeoSearch= true“ auf.
2. Die Abfrage wird an alle geografischen Standorte im Mandanten gesendet.
3. Die Suchergebnisse von jedem geografischen Standort werden zusammengeführt und bewertet.
4. Der Client erhält einheitliche Suchergebnisse.

<span id="_Set_up_a" class="anchor"><span id="_Ref501388384" class="anchor"></span></span>Beachten Sie, dass die Suchergebnisse erst dann zusammengeführt werden, wenn die Ergebnisse von allen geografischen Standorten abgerufen wurden. Dies bedeutet, dass Multi-Geo-Suchen im Vergleich zu den Suchen in einer Umgebung mit nur einem geografischen Standort eine zusätzliche Wartezeit aufweisen.

<span id="_Set_up_a_1" class="anchor"><span id="_Ref505252370" class="anchor"></span></span>
## <a name="get-a-search-center-to-show-results-from-all-geo-locations"></a>Anzeigen der Ergebnisse von allen geografischen Standorten in einem Suchcenter

Jedes Suchcenter verfügt über mehrere Suchsparten, und Sie müssen jede Sparte einzeln einrichten.

1. Stellen Sie sicher, dass Sie diese Schritte mit einem Konto ausführen, das über die Berechtigung zum Bearbeiten der Suchergebnisseite und des Suchergebnisse-Webparts verfügt.

2. Navigieren Sie zur Seite mit den Suchergebnissen (siehe [Liste](https://support.office.com/article/174d36e0-2f85-461a-ad9a-8b3f434a4213) der Suchergebnisseiten).

3. Wählen Sie die Sparte, die Sie einrichten möchten, klicken Sie in der oberen rechten Ecke auf das Zahnradsymbol für **Einstellungen**, und klicken Sie auf **Seite bearbeiten**. Die Seite mit den Suchergebnissen wird im Bearbeitungsmodus geöffnet.

   ![Bearbeiten der Seitenauswahl in Einstellungen](../media/configure-search-for-multi-geo-image2.png)

4. Bewegen Sie im Suchergebnisse-Webpart den Mauszeiger in die obere rechte Ecke des Webparts, klicken Sie auf den Pfeil, und klicken Sie dann im Menü auf **Webpart bearbeiten**. Der Toolbereich für das Suchergebnisse-Webpart wird unter dem Menüband oben rechts auf der Seite geöffnet.

   ![Bearbeiten der Web part-Auswahl](../media/configure-search-for-multi-geo-image3.png)

5. Wählen Sie im Webpart-Toolbereich im Abschnitt **Einstellungen** unter **Einstellungen für das Ergebnissteuerelement** die Option **Multi-Geo-Ergebnisse anzeigen**, damit das Suchergebnisse-Webpart Ergebnisse von allen geografischen Standorten anzeigt.

6. Klicken Sie auf **OK**, um Ihre Änderungen zu speichern und den Webpart-Toolbereich zu schließen.

7. Überprüfen Sie Ihre Änderungen an dem Suchergebnisse-Webpart, indem Sie im Hauptmenü auf der Registerkarte „Seite“ auf **Einchecken** klicken.

8. Veröffentlichen Sie die Änderungen über den Link in der Notiz oben auf der Seite.

<span id="_Get_custom_search" class="anchor"><span id="_Ref501388387" class="anchor"></span></span>
## <a name="get-custom-search-applications-to-show-results-from-all-or-some-geo-locations"></a>Anzeigen von Ergebnissen von allen oder einigen geografischen Standorten in benutzerdefinierten Suchanwendungen

Benutzerdefinierte Anwendungen rufen Ergebnisse von allen oder einigen geografischen Standorten ab, indem Sie Abfrageparameter mit der Anforderung an die SharePoint-Suche-REST-API angeben. Je nach Abfrageparameter wird die Abfrage in alle geografischen Standorte oder in einige geografischen Standorte aufgefächert. Wenn nur einige geografischen Standorte abgefragt werden sollen, können Sie die Auffächerung nur für diese einschränken. Wenn die Anforderung erfolgreich ist, gibt die SharePoint-Suche-REST-API die Antwortdaten zurück.

### <a name="requirement"></a>Anforderung

Sie müssen für jeden geografischen Standort sicherstellen, dass allen Benutzer in der Organisation die Berechtigungsstufe **Lesen** für die Stammwebsite erteilt wurde (z. B. contoso **APAC**.sharepoint.com/ und contoso **EU**.sharepoint.com/). [Weitere Informationen zu Berechtigungen](https://support.office.com/article/understanding-permission-levels-in-sharepoint-87ecbb0e-6550-491a-8826-c075e4859848).

### <a name="query-parameters"></a>Abfrageparameter

EnableMultiGeoSearch – Dies ist ein boolescher Wert, der angibt, ob die Abfrage in Indizes anderer geografischer Standorte des Multi-Geo-Mandanten aufgefächert werden soll. Legen Sie ihn auf **true** fest, um die Abfrage aufzufächern, oder auf **false**, wenn die Abfrage nicht aufgefächert werden soll. Wenn Sie diesen Parameter nicht angeben, lautet der Standardwert **false**, außer wenn Sie einen Rest API-Aufruf für eine Website durchführen, die die Vorlage "Enterprise-Suchcenter" verwendet. In diesem Fall lautet der Standardwert **true**. Wenn Sie den Parameter in einer Nicht-Multi-Geo-Umgebung verwenden, wird der Parameter ignoriert.

ClientType – Dies ist eine Zeichenfolge. Geben Sie einen eindeutigen Clientnamen für jede Suchanwendung ein. Wenn Sie diesen Parameter nicht angeben, wird die Abfrage nicht in andere geografische Standorte aufgefächert.

MultiGeoSearchConfiguration – Dies ist eine optionale Liste mit geografischen Standorten im Multi-Geo-Mandanten, für die die Abfrage aufgefächert werden soll, wenn **EnableMultiGeoSearch** auf **true** festgelegt ist. Wenn Sie diesen Parameter nicht angeben oder leer lassen, wird die Abfrage für alle geografischen Speicherorte aufgefächert. Geben Sie für jeden geografischen Standort die folgenden Elemente im JSON-Format an:

<table>
<thead>
<tr class="header">
<th align="left">Element</th>
<th align="left">Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">DataLocation</td>
<td align="left">Der geografische Standort, zum Beispiel NAM.</td>
</tr>
<tr class="even">
<td align="left">EndPoint</td>
<td align="left">Der Endpunkt für die Verbindung, zum Beispiel https://contoso.sharepoint.com</td>
</tr>
<tr class="odd">
<td align="left">SourceId</td>
<td align="left">Die GUID der Ergebnisquelle, zum Beispiel B81EAB55-3140-4312-B0F4-9459D1B4FFE.</td>
</tr>
</tbody>
</table>

Wenn Sie DataLocation oder Endpunkt weglassen, oder wenn DataLocation doppelt vorhanden ist, tritt bei der Anforderung ein Fehler auf. [Informationen zu dem Endpunkt von geografischen Standorten eines Mandanten können Sie mithilfe von Microsoft Graph](/sharepoint/dev/solution-guidance/multigeo-discovery) abrufen.

### <a name="response-data"></a>Antwortdaten

MultiGeoSearchStatus – Dies ist eine Eigenschaft, die die SharePoint-Suche-API als Reaktion auf eine Anforderung zurückgibt. Der Wert der Eigenschaft ist eine Zeichenfolge und bietet die folgenden Informationen zu den Ergebnissen, die die SharePoint-Suche-API zurückgibt:

<table>
<thead>
<tr class="header">
<th align="left">Wert</th>
<th align="left">Beschreibung</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Vollständig</td>
<td align="left">Vollständige Ergebnisse von <strong>allen</strong> geografischen Standorten.</td>
</tr>
<tr class="even">
<td align="left">Teilweise</td>
<td align="left">Teilweise Ergebnisse von einem oder mehreren geografischen Standorten. Die Ergebnisse sind aufgrund eines vorübergehenden Fehlers unvollständig.</td>
</tr>
</tbody>
</table>

### <a name="query-using-the-rest-service"></a>Abfrage mithilfe des REST-Diensts

Mit einer GET-Anforderung geben Sie die Abfrageparameter in der URL an. Mit einer POST-Anforderung übergeben Sie die Abfrageparameter im Text im JSON-Format.

#### <a name="request-headers"></a>Anforderungsheader

<table>
<thead>
<tr class="header">
<th align="left">Name</th>
<th align="left">Wert</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">Content-Type</td>
<td align="left">application/json;odata=verbose</td>
</tr>
</tbody>
</table>

#### <a name="sample-get-request-thats-fanned-out-to-all-geo-locations"></a>Beispiel für eine GET-Anforderung, die für **alle** geografischen Standorte aufgefächert wird

https:// \<tenant\> / \_ api/search/query?querytext='sharepoint'&Properties='EnableMultiGeoSearch:true'&ClientType='my \_ client \_ id'

#### <a name="sample-get-request-to-fan-out-to-some-geo-locations"></a>Beispiel für eine GET-Anforderung, die für **einige** geografischen Standorte aufgefächert wird

https:// \<tenant\> / \_ api/search/query?querytext='site'&ClientType='my_client_id'&Properties='EnableMultiGeoSearch:true, MultiGeoSearchConfiguration:[{DataLocation \\ :"NAM" \\ ,Endpoint \\ :"https \\ ://contosoNAM.sharepoint.com" \\ ,SourceId \\ :"B81EAB55-3140-4312-B0F4-9459D1B4FFEE"} \\ ,{DataLocation \\ :"CAN" \\ ,Endpoint \\ :"https \\ ://contosoCAN.sharepoint-df.com"}]'

> [!NOTE]
> Kommas und Doppelpunkten in der Liste der geografischen Standorte für die Eigenschaft MultiGeoSearchConfiguration wird ein **umgekehrtes Schrägstrichzeichen** vorangestellt. Dies hat den Grund, dass in GET-Anforderungen Doppelpunkte zum Trennen von Eigenschaften und Kommas zum Trennen von Argumenten von Eigenschaften verwendet werden. Ohne den umgekehrten Schrägstrich als Escapezeichen würde die MultiGeoSearchConfiguration-Eigenschaft falsch interpretiert.

#### <a name="sample-post-request-thats-fanned-out-to-all-geo-locations"></a>Beispiel für eine POST-Anforderung, die für **alle** geografischen Standorte aufgefächert wird

```text
    {
    "request": {
            "__metadata": {
            "type": "Microsoft.Office.Server.Search.REST.SearchRequest"
        },
        "Querytext": "sharepoint",
        "Properties": {
            "results": [
                {
                    "Name": "EnableMultiGeoSearch",
                    "Value": {
                        "QueryPropertyValueTypeIndex": 3,
                        "BoolVal": true
                    }
                }
            ]
        },
        "ClientType": "my_client_id"
        }
    }
```

#### <a name="sample-post-request-thats-fanned-out-to-some-geo-locations"></a>Beispiel für eine POST-Anforderung, die für **einige** geografische Standorte aufgefächert wird

```text
    {
        "request": {
            "Querytext": "SharePoint",
            "ClientType": "my_client_id",
            "Properties": {
                "results": [
                    {
                        "Name": "EnableMultiGeoSearch",
                        "Value": {
                            "QueryPropertyValueTypeIndex": 3,
                            "BoolVal": true
                        }
                    },
                    {
                        "Name": "MultiGeoSearchConfiguration",
                        "Value": {
                        "StrVal": "[{\"DataLocation\":\"NAM\",\"Endpoint\":\"https://contoso.sharepoint.com\",\"SourceId\":\"B81EAB55-3140-4312-B0F4-9459D1B4FFEE\"},{\"DataLocation\":\"CAN\",\"Endpoint\":\"https://contosoCAN.sharepoint.com\"}]",
                            "QueryPropertyValueTypeIndex": 1
                        }
                    }
                ]
            }
        }
    }
```

### <a name="query-using-csom"></a>Abfrage mithilfe von CSOM

Im Folgenden finden Sie ein Beispiel für eine CSOM-Abfrage, die für **alle** geografischen Standorte aufgefächert wird:

```text
var keywordQuery = new KeywordQuery(ctx);
keywordQuery.QueryText = query.SearchQueryText;
keywordQuery.ClientType = <enter a string here>;
keywordQuery["EnableMultiGeoSearch"] = true;
```