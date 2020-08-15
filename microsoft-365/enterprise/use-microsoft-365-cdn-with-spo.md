---
title: Verwenden Sie Office 365 Inhalts Zustellungs Netzwerk (CDN) mit SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 2/19/2020
audience: ITPro
ms.topic: article
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
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: In diesem Artikel erfahren Sie, wie Sie das Office 365 Content Delivery Network (CDN) verwenden, um die Zustellung Ihrer SharePoint Online Ressourcen zu beschleunigen.
ms.openlocfilehash: 0ef7922f4e8881065f97a5fdeb4f21242c2b6467
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690307"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online

Sie können statische Objekte im Office 365-Netzwerk für die Inhaltsübermittlung (CDN) hosten, um eine bessere Leistung für Ihre SharePoint Online-Seiten zu ermöglichen. Das Office 365-Netzwerk für die Inhaltsübermittlung verbessert die Leistung, indem statische Objekte näher an den Browsern zwischengespeichert werden, die diese anfordern, wodurch Downloads beschleunigt werden und die Latenz reduziert wird. Außerdem verwendet das Office 365 CDN das [http/2-Protokoll](https://en.wikipedia.org/wiki/HTTP/2) für verbesserte Komprimierung und HTTP-Pipelining. Das Office 365-Netzwerk für die Inhaltsübermittlung ist in Ihrem SharePoint Online-Abonnement enthalten.

> [!NOTE]
> Das Office 365 CDN steht nur Mandanten in der **Produktionsumgebung** (weltweit) zur Verfügung. Die Mandanten in der US-Regierung, in China und in Deutschland unterstützen derzeit nicht die Office 365 CDN.

Das Office 365-Netzwerk für die Inhaltsübermittlung besteht aus mehreren CDNs, über die Sie statische Objekte an mehreren Speicherorten hosten können, oder aus _Ursprüngen_, die aus globalen Hochgeschwindigkeitsnetzwerken bedient werden. In Abhängigkeit von der Art der Inhalte, die Sie im Office 365-Netzwerk für die Inhaltsübermittlung hosten möchten, können Sie **öffentliche** Ursprünge, **private** Ursprünge oder beides hinzufügen. Weitere Informationen zum Unterschied zwischen öffentlichen und privaten Quellen finden Sie unter [Choose, ob jeder Ursprung öffentlich oder privat sein soll](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) .

![Office 365 CDN-konzeptionelles Diagramm](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN-konzeptionelles Diagramm")

Wenn Sie bereits mit der Funktionsweise von CDNs vertraut sind, müssen Sie nur einige Schritte ausführen, um das Office 365 CDN für Ihren Mandanten zu aktivieren. In diesem Thema wird beschrieben, wie. Weitere Informationen zum Einstieg in das Hosten Ihrer statischen Objekte finden Sie unter.

> [!TIP]
> Es gibt andere von Microsoft gehostete CDNs, die mit Office 365 für spezielle Verwendungsszenarien verwendet werden können, aber in diesem Thema nicht behandelt werden, da Sie nicht in den Bereich des Office 365 CDN fallen. Weitere Informationen finden Sie unter [andere Microsoft-CDNs](content-delivery-networks.md#other-microsoft-cdns).

 **Wechseln Sie zurück zu [Netzwerkplanung und Leistungsoptimierung für Office 365](https://aka.ms/tune).**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Übersicht über das Arbeiten mit dem Office 365 CDN in SharePoint Online

Um die Office 365 CDN für Ihre Organisation einzurichten, führen Sie die folgenden grundlegenden Schritte aus:

+ [Planen der Bereitstellung des Office 365 CDN](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Bestimmen Sie, welche statischen Objekte im CDN gehostet werden sollen](use-microsoft-365-cdn-with-spo.md#CDNAssets).
  + [Bestimmen Sie, wo Ihre Objekte gespeichert werden sollen](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets). Bei diesem Speicherort kann es sich um eine SharePoint-Website,-Bibliothek oder-Ordner handeln, die als _Ursprung_bezeichnet wird.
  + [Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate). Sie können mehrere Ursprünge sowohl für öffentliche als auch für private Typen hinzufügen.

+ Einrichten und Konfigurieren des CDN mithilfe von PowerShell oder der SharePoint Online CLI

  + [Einrichten und Konfigurieren des CDN mithilfe der SharePoint Online Management-Shell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Einrichten und Konfigurieren des CDN mithilfe von PNP-PowerShell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Einrichten und Konfigurieren des CDN mithilfe der Office 365 CLI](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  Wenn Sie diesen Schritt ausführen, haben Sie folgende Möglichkeiten:

  + Das CDN für Ihre Organisation wurde aktiviert.
  + Origins hinzugefügt, wobei jeder Ursprung als öffentlich oder privat identifiziert wurde.

Nachdem Sie das Setup abgeschlossen haben, können Sie [das Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNManage) im Laufe der Zeit verwalten:
  
+ Hinzufügen, aktualisieren und Entfernen von Objekten
+ Hinzufügen und Entfernen von Ursprüngen
+ Konfigurieren von CDN-Richtlinien
+ Falls erforderlich, Deaktivieren des CDN

Weitere Informationen zum Zugreifen auf Ihre CDN-Ressourcen sowohl aus öffentlichen als auch aus privaten Quellen finden Sie unter [using your CDN Assets](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets) .

Anleitungen zum Beheben häufig auftretender Probleme finden Sie unter [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) .

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Planen der Bereitstellung des Office 365 CDN

Bevor Sie das Office 365 CDN für Ihren Office 365-Mandanten bereitstellen, sollten Sie die folgenden Faktoren im Rahmen Ihres Planungsprozesses berücksichtigen.

  + [Bestimmen Sie, welche statischen Objekte im CDN gehostet werden sollen.](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Bestimmen, wo Ihre Objekte gespeichert werden sollen](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Bestimmen Sie, welche statischen Objekte im CDN gehostet werden sollen.

Im Allgemeinen sind CDNs am effektivsten für das Hosten von _statischen Objekten_oder von Objekten, die sich nicht sehr häufig ändern. Eine gute Faustregel besteht darin, Dateien zu identifizieren, die einige oder alle dieser Bedingungen erfüllen:

+ In einer Seite eingebettete statische Dateien (wie Skripts und Bilder), die sich möglicherweise erheblich inkrementell auf die Seitenladezeiten auswirken
+ Große Dateien wie ausführbare Dateien und Installationsdateien
+ Ressourcen Bibliotheken, die clientseitigen Code unterstützen

Beispielsweise können kleine Dateien, die wiederholt wie Website Bilder und Skripts angefordert werden, die Leistung von Website Renderings erheblich verbessern und die Last auf Ihren SharePoint Online Websites inkrementell reduzieren, wenn Sie Sie einem CDN-Ursprung hinzufügen. Größere Dateien wie Installationsdateien können aus dem CDN heruntergeladen werden, was sich positiv auf die Leistung auswirkt und die Last auf Ihrer SharePoint Online Website verringert, auch wenn Sie nicht so häufig auf Sie zugreifen.

Die Leistungsverbesserung pro Datei hängt von vielen Faktoren ab, einschließlich der Nähe des Clients zum nächstgelegenen CDN-Endpunkt, der vorübergehenden Bedingungen im lokalen Netzwerk und so weiter. Viele statische Dateien sind relativ klein und können in weniger als einer Sekunde von Office 365 heruntergeladen werden. Eine Webseite enthält jedoch möglicherweise viele eingebettete Dateien mit einer kumulierten Downloadzeit von mehreren Sekunden. Das servieren dieser Dateien aus dem CDN kann die Ladezeit der gesamten Seite erheblich verkürzen. Sehen Sie, [welche Leistungssteigerungen ein CDN bietet?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) ein Beispiel.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Bestimmen, wo Ihre Objekte gespeichert werden sollen

Das CDN ruft Ihre Objekte von einem Standort ab, der als _Ursprung_bezeichnet wird. Ein Ursprung kann eine SharePoint-Website, eine Dokumentbibliothek oder ein Ordner sein, auf die über eine URL zugegriffen werden kann. Sie haben eine große Flexibilität, wenn Sie den Ursprung für Ihre Organisation angeben. Sie können beispielsweise mehrere Ursprünge oder einen einzelnen Ursprung angeben, in dem Sie alle CDN-Objekte ablegen möchten. Sie können festlegen, dass sowohl öffentliche als auch private Ursprünge für Ihre Organisation gelten. Die meisten Organisationen entscheiden sich für die Implementierung einer Kombination aus beiden.

Sie können neuen Container für ihre Herkunft wie Ordner oder Dokumentbibliotheken erstellen und Dateien hinzufügen, die Sie im CDN zur Verfügung stellen möchten. Dies ist ein guter Ansatz, wenn Sie über einen bestimmten Satz von Objekten verfügen, die im CDN verfügbar sein sollen, und den Satz von CDN-Objekten auf diese Dateien im Container beschränken möchten.

Sie können auch eine vorhandene Websitesammlung, Website, Bibliothek oder einen Ordner als Ursprung konfigurieren, mit der alle berechtigten Ressourcen im Container im CDN verfügbar gemacht werden. Bevor Sie einen vorhandenen Container als Ursprung hinzufügen, müssen Sie sicherstellen, dass Sie den Inhalt und die Berechtigungen kennen, damit Sie Objekte nicht versehentlich anonymen Zugriffen oder nicht autorisierten Benutzern offen legen.

Sie können _CDN-Richtlinien_ definieren, um Inhalte in ihren Ursprüngen aus dem CDN auszuschließen. CDN-Richtlinien schließen Objekte in öffentlichem oder privatem Ursprung durch Attribute wie _Dateityp_ und _Website Klassifizierung_aus und werden auf alle Ursprünge der CdnType (privat oder öffentlich) angewendet, die Sie in der Richtlinie angeben. Wenn Sie beispielsweise einen privaten Ursprung hinzufügen, der aus einer Website besteht, die mehrere Unterwebsites enthält, können Sie eine Richtlinie definieren, um als **vertraulich** gekennzeichnete Websites auszuschließen, sodass Inhalte von Websites mit dieser Klassifizierung nicht aus dem CDN bereitgestellt werden. Die Richtlinie wird auf Inhalte _aller_ privaten Ursprünge angewendet, die Sie dem CDN hinzugefügt haben.
  
Beachten Sie, dass je größer die Anzahl der Ursprünge ist, desto größer sind die Auswirkungen auf die Zeit, die der CDN-Dienst zum Verarbeiten von Anforderungen benötigt. Es wird empfohlen, die Anzahl der Ursprünge so weit wie möglich zu begrenzen.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll.

Wenn Sie einen Ursprung identifizieren, geben Sie an, ob er _öffentlich_ oder _Privat_sein soll. Der Zugriff auf CDN-Objekte im öffentlichen Ursprung ist anonym, und CDN-Inhalte in privater Herkunft werden durch dynamisch generierte Token für mehr Sicherheit gesichert. Unabhängig davon, welche Option Sie auswählen, bietet Microsoft für Sie alle Schwerlasten, wenn es um die Verwaltung des CDN selbst geht. Außerdem können Sie Ihre Meinung später ändern, nachdem Sie das CDN eingerichtet und ihre Ursprünge identifiziert haben.

Sowohl öffentliche als auch private Optionen bieten ähnliche Leistungssteigerungen, aber jedes verfügt über eindeutige Attribute und Vorteile.

**Öffentliche** Ursprünge im Office 365 CDN sind anonym zugänglich, und auf gehostete Objekte kann jeder zugreifen, der über die URL der Ressource verfügt. Da der Zugriff auf Inhalte in öffentlichen Ursprüngen anonym ist, sollten Sie diese nur zum Zwischenspeichern von nicht vertraulichen generischen Inhalten verwenden, z. B. JavaScript-Dateien, Skripts, Symbole oder Bilder.

**Private** Ursprünge im Office 365 CDN bieten privaten Zugriff auf Benutzer Inhalte wie SharePoint Online Dokumentbibliotheken, Websites und proprietäre Bilder. Der Zugriff auf Inhalte in privater Herkunft wird durch dynamisch generierte Token gesichert, sodass nur Benutzer mit Berechtigungen für die ursprüngliche Dokumentbibliothek oder den Speicherort darauf zugreifen können. Private Ursprünge im Office 365 CDN können nur für SharePoint Online Inhalte verwendet werden, und Sie können nur über die Umleitung von Ihrem SharePoint Online Mandanten auf Objekte im privaten Ursprung zugreifen.

Sie können mehr darüber erfahren, wie der CDN-Zugriff auf Objekte in einem privaten Ursprung in der [Verwendung von Objekten in privater](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)Herkunft funktioniert.

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Attribute und Vorteile des Hostens von Objekten im öffentlichen Ursprung
  
+ Objekte, die an einem öffentlichen Ursprung verfügbar gemacht werden, sind für jeden Benutzer anonym zugänglich.
    > [!IMPORTANT]
    > Sie sollten niemals Ressourcen platzieren, die Benutzerinformationen enthalten oder als vertraulich für Ihre Organisation in einem öffentlichen Ursprung betrachtet werden.
+ Wenn Sie ein Objekt aus einem öffentlichen Ursprung entfernen, ist es unter Umständen bis zu 30 Tage lang weiterhin über den Cache verfügbar. Links zu dem Objekt im CDN werden jedoch innerhalb von 15 Minuten ungültig.
+ Wenn Sie Stylesheets (CSS-Dateien) an einem öffentlichen Ursprung hosten, können Sie im Code relative Pfade und URIs verwenden. Dies bedeutet, dass Sie auf den Speicherort von Hintergrundbildern und anderen Objekten relativ zum Speicherort des Objekts, das sie aufruft, verweisen können.
+ Die URL eines öffentlichen Ursprungs kann zwar hartcodiert werden, dies wird jedoch nicht empfohlen. Der Grund hierfür ist folgender: Wenn der Zugriff auf das CDN nicht mehr verfügbar ist, wird die URL nicht automatisch auf Ihre Organisation in SharePoint Online aufgelöst, was zu fehlerhaften Links und anderen Fehlern führen kann.
+ Zu den standardmäßigen Dateitypen, die für öffentliche Ursprünge gehören, Gehören CSS, EOT, GIF, ICO, JPEG, JPG, JS, map, PNG, SVG, ttf, WOFF und woff2. Sie können zusätzliche Dateitypen angeben.
+ Sie können eine Richtlinie so konfigurieren, dass Objekte ausgeschlossen werden, die durch von Ihnen angegebene Website Klassifikationen identifiziert wurden. Beispielsweise können Sie alle Objekte ausschließen, die als „vertraulich“ oder „eingeschränkt“ gekennzeichnet sind, auch wenn sie einen zulässigen Dateityp haben und sich an einem öffentlichen Ursprung befinden.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Attribute und Vorteile des Hostens von Objekten in privater Herkunft

+ Private Origins können nur für SharePoint Online Objekte verwendet werden.
+ Benutzer können nur auf die Objekte von einem privaten Ursprung aus zugreifen, wenn Sie über Berechtigungen für den Zugriff auf den Container verfügen. Der anonyme Zugriff auf diese Objekte wird verhindert.
+ Objekte im privaten Ursprung müssen vom SharePoint Online Mandanten verwiesen werden. Der direkte Zugriff auf private CDN-Objekte funktioniert nicht.
+ Wenn Sie ein Objekt aus dem privaten Ursprung entfernen, ist das Objekt möglicherweise bis zu einer Stunde nach dem Cache verfügbar. Es werden jedoch Links zu dem Objekt im CDN innerhalb von 15 Minuten nach dem Entfernen der Ressource ungültig.
+ Die standardmäßigen Dateitypen, die für private Ursprünge eingeschlossen werden, sind GIF, ICO, JPEG, JPG, JS und PNG. Sie können zusätzliche Dateitypen angeben.
+ Wie beim öffentlichen Ursprung können Sie eine Richtlinie so konfigurieren, dass Objekte ausgeschlossen werden, die anhand von Website Klassifikationen identifiziert wurden, die Sie selbst dann angeben, wenn Sie Platzhalter verwenden, um alle Objekte in einen Ordner oder eine Dokumentbibliothek einzuschließen.

Weitere Informationen dazu, warum Sie die Office 365 CDN, allgemeine CDN-Konzepte und andere Microsoft-CDNs verwenden können, die Sie mit Ihrem Office 365-Mandanten verwenden können, finden Sie unter [Content Delivery Networks](content-delivery-networks.md).

### <a name="default-cdn-origins"></a>Standard-CDN-Ursprünge

Wenn Sie nichts anderes angeben, legt Office 365 eine Standard Herkunft fest, wenn Sie das Office 365 CDN aktivieren. Wenn Sie diese ursprünglich nicht anbieten möchten, können Sie diese Ursprünge nach Abschluss des Setups hinzufügen. Wenn Sie die Auswirkungen des Überspringens der Einrichtung von Standard Ursprüngen nicht verstehen und einen bestimmten Grund dafür haben, sollten Sie Sie beim Aktivieren des CDN erstellen lassen.
  
Standardmäßige private CDN-Ursprünge:
  
+ \*/userphoto.aspx
+ \*/siteassets

Standardmäßige öffentliche CDN-Ursprünge:
  
+ \*/masterpage
+ \*/Style-Bibliothek
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ ist ein öffentlicher Standardursprung, der dem Office 365 CDN-Dienst im Dezember 2017 hinzugefügt wurde. Dieser Ursprung muss vorhanden sein, damit SharePoint-Framework-Lösungen im CDN funktionieren. Wenn Sie das Office 365 CDN vor Dezember 2017 aktiviert haben oder wenn Sie das Setup der Standard Ursprünge übersprungen haben, als Sie das CDN aktiviert haben, können Sie diesen Ursprung manuell hinzufügen. Weitere Informationen finden Sie unter [meine clientseitige Webparts oder SharePoint Framework-Lösung funktioniert nicht](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Einrichten und Konfigurieren des Office 365 CDN mithilfe der SharePoint Online Management-Shell

Für die Verfahren in diesem Abschnitt müssen Sie die SharePoint Online-Verwaltungsshell verwenden, um eine Verbindung mit SharePoint Online herzustellen. Weitere Anweisungen finden Sie unter [Connect to SharePoint Online PowerShell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

Führen Sie die folgenden Schritte aus, um das CDN so einzurichten und zu konfigurieren, dass es Ihre Objekte in SharePoint Online mithilfe der SharePoint Online-Verwaltungsshell hostet.

<details>
  <summary>Zum Erweitern klicken</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Aktivieren Ihrer Organisation für die Verwendung des Office 365 CDN

Bevor Sie Änderungen an den Mandanten-CDN-Einstellungen vornehmen, sollten Sie den aktuellen Status der privaten CDN-Konfiguration in Ihrem Office 365 Mandanten abrufen. Stellen Sie über die SharePoint Online-Verwaltungsshell eine Verbindung zu Ihrem Mandanten her:

``` powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Verwenden Sie nun das Cmdlet **Get-SPOTenantCdnEnabled** , um die CDN-Statuseinstellungen aus dem Mandanten abzurufen:

``` powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

Der Status des CDN für das angegebene CdnType-Objekt wird auf dem Bildschirm ausgegeben.

Verwenden Sie das Cmdlet " **SPOTenantCdnEnabled** ", um Ihrer Organisation die Verwendung des Office 365 CDN zu ermöglichen. Sie können Ihre Organisation in die Lage versetzen, öffentliche Ursprünge, private Ursprünge oder beides gleichzeitig zu verwenden. Sie können das CDN auch so konfigurieren, dass das Setup von Standard Ursprüngen übersprungen wird, wenn Sie es aktivieren. Sie können diese Ursprünge immer später wie in diesem Thema beschrieben hinzufügen.
  
In Windows PowerShell für SharePoint Online:

``` powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Geben Sie beispielsweise den folgenden Befehl ein, damit Ihre Organisation sowohl öffentliche als auch private Ursprünge verwenden kann:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Geben Sie den folgenden Befehl ein, um zu ermöglichen, dass Ihre Organisation sowohl öffentliche als auch private Ursprünge verwendet, aber das Einrichten der Standard Ursprünge überspringt:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Unter [default CDN Origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) finden Sie Informationen zu den Ursprüngen, die standardmäßig bereitgestellt werden, wenn Sie das Office 365 CDN aktivieren, und die potenziellen Auswirkungen des Überspringens der Einrichtung von Standard Ursprüngen.

Geben Sie den folgenden Befehl ein, um Ihre Organisation für die Verwendung von öffentlichen Ursprüngen zu aktivieren:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Geben Sie den folgenden Befehl ein, um Ihre Organisation für die Verwendung privater Origins zu aktivieren:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Weitere Informationen zu diesem Cmdlet finden Sie unter [Sets-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Ändern der Liste der Dateitypen, die in das Office 365 CDN eingeschlossen werden sollen (optional)

> [!TIP]
> Wenn Sie Dateitypen mithilfe des Cmdlets "Cmdlet **festlegen-SPOTenantCdnPolicy** " definieren, überschreiben Sie die aktuell definierte Liste. Wenn Sie der Liste weitere Dateitypen hinzufügen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Dateitypen bereits zulässig sind, und fügen Sie sie zusammen mit ihren neuen Dateien in die Liste ein.
  
Verwenden Sie das Cmdlet " **SPOTenantCdnPolicy** ", um statische Dateitypen zu definieren, die von öffentlichen und privaten Quellen im CDN gehostet werden können. Standardmäßig sind allgemeine Objekttypen zulässig, beispielsweise CSS, GIF, JPG und JS.

In Windows PowerShell für SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Um beispielsweise das CDN zum Hosten von CSS-und PNG-Dateien zu aktivieren, geben Sie den folgenden Befehl ein:

``` powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Verwenden Sie das Cmdlet **Get-SPOTenantCdnPolicies** , um zu sehen, welche Dateitypen derzeit im CDN zulässig sind:

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Weitere Informationen zu diesen Cmdlets finden Sie unter [Sets-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) und [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Ändern Sie die Liste der Website Klassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten (optional).

> [!TIP]
> Wenn Sie Website Klassifizierungen mithilfe des Cmdlets " **SPOTenantCdnPolicy** " ausschließen, überschreiben Sie die aktuell definierte Liste. Wenn Sie zusätzliche Website Klassifizierungen ausschließen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Klassifizierungen bereits ausgeschlossen sind, und fügen Sie Sie dann zusammen mit ihren neuen hinzu.

Verwenden Sie das Cmdlet **Set-SPOTenantCdnPolicy** -Cmdlet zum Ausschließen von Websiteklassifizierungen, die Sie nicht über das CDN zur Verfügung stellen möchten. Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.

In Windows PowerShell für SharePoint Online:

``` powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Um anzuzeigen, welche Website Klassifizierungen derzeit eingeschränkt sind, verwenden Sie das Cmdlet **Get-SPOTenantCdnPolicies** :

``` powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Die Eigenschaften, die zurückgegeben werden, sind _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ und _ExcludeIfNoScriptDisabled_.

Die _IncludeFileExtensions_ -Eigenschaft enthält die Liste der Dateierweiterungen, die vom CDN bereitgestellt werden.

> [!NOTE]
> Die standardmäßigen Dateierweiterungen unterscheiden sich zwischen öffentlichen und privaten.

Die _ExcludeRestrictedSiteClassifications_ -Eigenschaft enthält die Website Klassifizierungen, die Sie aus dem CDN ausschließen möchten. Beispielsweise können Sie als **vertraulich** gekennzeichnete Websites ausschließen, sodass Inhalte von Websites mit dieser Klassifizierung nicht aus dem CDN bereitgestellt werden.

Die _ExcludeIfNoScriptDisabled_ -Eigenschaft schließt Inhalte aus dem CDN basierend auf den _NoScript_ -Attributeinstellungen auf Websiteebene aus. Standardmäßig ist das _NoScript_ -Attribut auf für _moderne_ Websites **aktiviert** und für _klassische_ Websites **deaktiviert** festgelegt. Dies hängt von ihren Mandanten Einstellungen ab.

Weitere Informationen zu diesen Cmdlets finden Sie unter [Sets-SPOTenantCdnPolicy](https://technet.microsoft.com/library/mt800839.aspx) und [Get-SPOTenantCdnPolicies](https://technet.microsoft.com/library/mt800838.aspx).

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Hinzufügen eines Ursprungs für Ihre Objekte

Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um einen Ursprung zu definieren. Sie können mehrere Ursprünge definieren. Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.
  
> [!IMPORTANT]
> Sie sollten niemals Ressourcen platzieren, die Benutzerinformationen enthalten oder als vertraulich für Ihre Organisation in einem öffentlichen Ursprung betrachtet werden.

``` powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Der Wert von _path_ ist der relative Pfad zu der Bibliothek oder dem Ordner, der die Objekte enthält. Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden. Origins unterstützen Platzhalter für die URL. Auf diese Weise können Sie Ursprünge erstellen, die sich über mehrere Standorte erstrecken. Geben Sie beispielsweise den folgenden Befehl ein, um alle Objekte im MasterPages-Ordner für alle Websites als öffentlichen Ursprung innerhalb des CDN einzuschließen:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Der Platzhalter-Modifizierer * **/** kann nur am Anfang des Pfads verwendet werden und wird allen URL-Segmenten unter der angegebenen URL zugeordnet.
+ Der Pfad kann auf eine Dokumentbibliothek, einen Ordner oder eine Website deuten. Beispielsweise wird der Pfad _*/site1_ alle Dokumentbibliotheken unter der Website entsprechen.

Sie können einen Ursprung mit einem bestimmten relativen Pfad hinzufügen. Sie können keinen Ursprung mithilfe des vollständigen Pfads hinzufügen.

In diesem Beispiel wird ein privater Ursprung der SiteAssets-Bibliothek auf einem bestimmten Standort hinzugefügt:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In diesem Beispiel wird ein privater Ursprung des _Folder1_ -Ordners in der Bibliothek Website Objekte der Websitesammlung hinzugefügt:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Wenn ein Leerzeichen im Pfad vorhanden ist, können Sie entweder den Pfad in doppelte Anführungszeichen einschließen oder den Platz durch die URL-Codierung %20 ersetzen. In den folgenden Beispielen wird ein privater Ursprung des Ordners _Folder 1_ in der Bibliothek Website Objekte der Websitesammlung hinzugefügt:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).

> [!NOTE]
> In privaten Quellen muss für Objekte, die von einem Ursprung freigegeben werden, eine Hauptversion veröffentlicht werden, bevor auf Sie über das CDN zugegriffen werden kann.
  
Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Beispiel: Konfigurieren eines öffentlichen Ursprungs für Ihre Gestaltungsvorlagen und für Ihre Stilbibliothek für SharePoint Online

Normalerweise werden diese Ursprünge standardmäßig für Sie eingerichtet, wenn Sie das Office 365 CDN aktivieren. Wenn Sie Sie jedoch manuell aktivieren möchten, führen Sie die folgenden Schritte aus.
  
+ Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um die Formatbibliothek als öffentlichen Ursprung zu definieren.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um die Gestaltungsvorlagen als öffentlichen Ursprung zu definieren.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Beispiel: Konfigurieren eines privaten Ursprungs für Ihre Website Objekte, Website Seiten und Veröffentlichungs Bilder für SharePoint Online

+ Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um den Ordner Website Objekte als privaten Ursprung zu definieren.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um den Ordner Website Seiten als privaten Ursprung zu definieren.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um den Ordner Veröffentlichungs Bilder als privaten Ursprung zu definieren.

``` powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Beispiel: Konfigurieren eines privaten Ursprungs für eine Websitesammlung für SharePoint Online

Verwenden Sie das Cmdlet **Add-SPOTenantCdnOrigin** , um eine Websitesammlung als privaten Ursprung zu definieren. Beispiel:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790772.aspx).
  
Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg. Möglicherweise wird eine _ausstehende Konfigurations_ Meldung angezeigt, die erwartet wird, wenn der SharePoint Online-Mandant eine Verbindung mit dem CDN-Dienst herstellt. Dies kann bis zu 15 Minuten dauern.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Verwalten des Office 365 CDN

Nachdem Sie das CDN eingerichtet haben, können Sie, wie in diesem Abschnitt beschrieben, Änderungen an der Konfiguration vornehmen, wenn Sie Inhalte aktualisieren oder Ihre Anforderungen ändern.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Hinzufügen, aktualisieren oder Entfernen von Objekten aus dem Office 365 CDN

Nachdem Sie die Setupschritte abgeschlossen haben, können Sie neue Objekte hinzufügen und vorhandene Objekte aktualisieren oder entfernen, wann immer Sie möchten. Nehmen Sie einfach Ihre Änderungen an den Objekten im Ordner oder in der SharePoint-Bibliothek vor, die Sie als Ursprung identifiziert haben. Wenn Sie ein neues Objekt hinzufügen, steht es sofort über das CDN zur Verfügung. Wenn Sie das Objekt aktualisieren, dauert es jedoch bis zu 15 Minuten, bis die neue Kopie weitergegeben wird und im CDN verfügbar ist.
  
Wenn Sie den Speicherort des Ursprungs abrufen möchten, können Sie das Cmdlet **Get-spotenantcdnorigins ausführen** verwenden. Informationen zur Verwendung dieses Cmdlets finden Sie unter [Get-spotenantcdnorigins ausführen](https://technet.microsoft.com/library/mt790770.aspx).

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Entfernen eines Ursprungs aus dem Office 365 CDN

Sie können den Zugriff auf einen Ordner oder eine SharePoint-Bibliothek, den Sie als Ursprung identifiziert haben, entfernen. Verwenden Sie dazu das Cmdlet **Remove-SPOTenantCdnOrigin** .

``` powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Informationen zur Verwendung dieses Cmdlets finden Sie unter [Remove-SPOTenantCdnOrigin](https://technet.microsoft.com/library/mt790761.aspx).

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Ändern eines Ursprungs im Office 365 CDN

Sie können einen erstellten Ursprung nicht ändern. Entfernen Sie stattdessen den Ursprung, und fügen Sie dann einen neuen ein. Weitere Informationen finden Sie unter [So entfernen Sie einen Ursprung aus dem Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) und [fügen einen Ursprung für Ihre Objekte hinzu](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Deaktivieren des Office 365 CDN

Verwenden Sie das Cmdlet " **SPOTenantCdnEnabled** ", um das CDN für Ihre Organisation zu deaktivieren. Wenn Sie sowohl den öffentlichen als auch den privaten Ursprung für das CDN aktiviert haben, müssen Sie das Cmdlet zweimal ausführen, wie in den folgenden Beispielen dargestellt.
  
Geben Sie den folgenden Befehl ein, um die Verwendung der öffentlichen Herkunft im CDN zu deaktivieren:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Geben Sie den folgenden Befehl ein, um die Verwendung der privaten Ursprünge im CDN zu deaktivieren:

``` powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Weitere Informationen zu diesem Cmdlet finden Sie unter [Sets-SPOTenantCdnEnabled](https://technet.microsoft.com/library/mt790765.aspx).

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Einrichten und Konfigurieren des Office 365 CDN mithilfe von PNP PowerShell

Für die Verfahren in diesem Abschnitt müssen Sie PNP PowerShell verwenden, um eine Verbindung mit SharePoint Online herzustellen. Anweisungen finden Sie unter [Erste Schritte mit PNP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).

Führen Sie die folgenden Schritte aus, um das CDN so einzurichten und zu konfigurieren, dass es Ihre Objekte in SharePoint Online mithilfe von PNP PowerShell hostet.

<details>
  <summary>Zum Erweitern klicken</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Aktivieren Ihrer Organisation für die Verwendung des Office 365 CDN

Bevor Sie Änderungen an den Mandanten-CDN-Einstellungen vornehmen, sollten Sie den aktuellen Status der privaten CDN-Konfiguration in Ihrem Office 365 Mandanten abrufen. Stellen Sie über PNP PowerShell eine Verbindung zu Ihrem Mandanten her:

``` powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

Verwenden Sie nun das Cmdlet **Get-PnPTenantCdnEnabled** , um die CDN-Statuseinstellungen aus dem Mandanten abzurufen:

``` powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

Der Status des CDN für das angegebene CdnType-Objekt wird auf dem Bildschirm ausgegeben.

Verwenden Sie das Cmdlet " **PnPTenantCdnEnabled** ", um Ihrer Organisation die Verwendung des Office 365 CDN zu ermöglichen. Sie können Ihre Organisation zur gleichzeitigen Verwendung von öffentlichem Ursprung, privatem Ursprung oder beides aktivieren. Sie können das CDN auch so konfigurieren, dass das Setup von Standard Ursprüngen übersprungen wird, wenn Sie es aktivieren. Sie können diese Ursprünge immer später wie in diesem Thema beschrieben hinzufügen.
  
In PNP PowerShell:

``` powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Geben Sie beispielsweise den folgenden Befehl ein, damit Ihre Organisation sowohl öffentliche als auch private Ursprünge verwenden kann:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Geben Sie den folgenden Befehl ein, um zu ermöglichen, dass Ihre Organisation sowohl öffentliche als auch private Ursprünge verwendet, aber das Einrichten der Standard Ursprünge überspringt:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Unter [default CDN Origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) finden Sie Informationen zu den Ursprüngen, die standardmäßig bereitgestellt werden, wenn Sie das Office 365 CDN aktivieren, und die potenziellen Auswirkungen des Überspringens der Einrichtung von Standard Ursprüngen.

Geben Sie den folgenden Befehl ein, um Ihre Organisation für die Verwendung von öffentlichen Ursprüngen zu aktivieren:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Geben Sie den folgenden Befehl ein, um Ihre Organisation für die Verwendung privater Origins zu aktivieren:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Weitere Informationen zu diesem Cmdlet finden Sie unter [Sets-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Ändern der Liste der Dateitypen, die in das Office 365 CDN eingeschlossen werden sollen (optional)

> [!TIP]
> Wenn Sie Dateitypen mithilfe des Cmdlets "Cmdlet **festlegen-PnPTenantCdnPolicy** " definieren, überschreiben Sie die aktuell definierte Liste. Wenn Sie der Liste weitere Dateitypen hinzufügen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Dateitypen bereits zulässig sind, und fügen Sie sie zusammen mit ihren neuen Dateien in die Liste ein.
  
Verwenden Sie das Cmdlet " **PnPTenantCdnPolicy** ", um statische Dateitypen zu definieren, die von öffentlichen und privaten Quellen im CDN gehostet werden können. Standardmäßig sind allgemeine Objekttypen zulässig, beispielsweise CSS, GIF, JPG und JS.

In PNP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Um beispielsweise das CDN zum Hosten von CSS-und PNG-Dateien zu aktivieren, geben Sie den folgenden Befehl ein:

``` powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Verwenden Sie das Cmdlet **Get-PnPTenantCdnPolicies** , um zu sehen, welche Dateitypen derzeit im CDN zulässig sind:

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Weitere Informationen zu diesen Cmdlets finden Sie unter [Sets-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) und [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Ändern Sie die Liste der Website Klassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten (optional).

> [!TIP]
> Wenn Sie Website Klassifizierungen mithilfe des Cmdlets " **PnPTenantCdnPolicy** " ausschließen, überschreiben Sie die aktuell definierte Liste. Wenn Sie zusätzliche Website Klassifizierungen ausschließen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Klassifizierungen bereits ausgeschlossen sind, und fügen Sie Sie dann zusammen mit ihren neuen hinzu.

Verwenden Sie das Cmdlet " **PnPTenantCdnPolicy** ", um Website Klassifizierungen auszuschließen, die nicht über das CDN verfügbar gemacht werden sollen. Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.

In PNP PowerShell:

``` powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Um anzuzeigen, welche Website Klassifizierungen derzeit eingeschränkt sind, verwenden Sie das Cmdlet **Get-PnPTenantCdnPolicies** :

``` powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Die Eigenschaften, die zurückgegeben werden, sind _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ und _ExcludeIfNoScriptDisabled_.

Die _IncludeFileExtensions_ -Eigenschaft enthält die Liste der Dateierweiterungen, die vom CDN bereitgestellt werden.

> [!NOTE]
> Die standardmäßigen Dateierweiterungen unterscheiden sich zwischen öffentlichen und privaten.

Die _ExcludeRestrictedSiteClassifications_ -Eigenschaft enthält die Website Klassifizierungen, die Sie aus dem CDN ausschließen möchten. Beispielsweise können Sie als **vertraulich** gekennzeichnete Websites ausschließen, sodass Inhalte von Websites mit dieser Klassifizierung nicht aus dem CDN bereitgestellt werden.

Die _ExcludeIfNoScriptDisabled_ -Eigenschaft schließt Inhalte aus dem CDN basierend auf den _NoScript_ -Attributeinstellungen auf Websiteebene aus. Standardmäßig ist das _NoScript_ -Attribut auf für _moderne_ Websites **aktiviert** und für _klassische_ Websites **deaktiviert** festgelegt. Dies hängt von ihren Mandanten Einstellungen ab.

Weitere Informationen zu diesen Cmdlets finden Sie unter [Sets-PnPTenantCdnPolicy](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) und [Get-PnPTenantCdnPolicies](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Hinzufügen eines Ursprungs für Ihre Objekte

Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um einen Ursprung zu definieren. Sie können mehrere Ursprünge definieren. Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.
  
> [!IMPORTANT]
> Sie sollten niemals Ressourcen platzieren, die Benutzerinformationen enthalten oder als vertraulich für Ihre Organisation in einem öffentlichen Ursprung betrachtet werden.

``` powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Der Wert von _path_ ist der relative Pfad zu der Bibliothek oder dem Ordner, der die Objekte enthält. Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden. Origins unterstützen Platzhalter für die URL. Auf diese Weise können Sie Ursprünge erstellen, die sich über mehrere Standorte erstrecken. Geben Sie beispielsweise den folgenden Befehl ein, um alle Objekte im MasterPages-Ordner für alle Websites als öffentlichen Ursprung innerhalb des CDN einzuschließen:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Der Platzhalter-Modifizierer * **/** kann nur am Anfang des Pfads verwendet werden und wird allen URL-Segmenten unter der angegebenen URL zugeordnet.
+ Der Pfad kann auf eine Dokumentbibliothek, einen Ordner oder eine Website deuten. Beispielsweise wird der Pfad _*/site1_ alle Dokumentbibliotheken unter der Website entsprechen.

Sie können einen Ursprung mit einem bestimmten relativen Pfad hinzufügen. Sie können keinen Ursprung mithilfe des vollständigen Pfads hinzufügen.

In diesem Beispiel wird ein privater Ursprung der Bibliothek Website Objekte auf einem bestimmten Standort hinzugefügt:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In diesem Beispiel wird ein privater Ursprung des _Folder1_ -Ordners in der Bibliothek Website Objekte der Websitesammlung hinzugefügt:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Wenn ein Leerzeichen im Pfad vorhanden ist, können Sie entweder den Pfad in doppelte Anführungszeichen einschließen oder den Platz durch die URL-Codierung %20 ersetzen. In den folgenden Beispielen wird ein privater Ursprung des Ordners _Folder 1_ in der Bibliothek Website Objekte der Websitesammlung hinzugefügt:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

> [!NOTE]
> In privaten Quellen muss für Objekte, die von einem Ursprung freigegeben werden, eine Hauptversion veröffentlicht werden, bevor auf Sie über das CDN zugegriffen werden kann.
  
Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Beispiel: Konfigurieren eines öffentlichen Ursprungs für Ihre Gestaltungsvorlagen und für Ihre Stilbibliothek für SharePoint Online

Normalerweise werden diese Ursprünge standardmäßig für Sie eingerichtet, wenn Sie das Office 365 CDN aktivieren. Wenn Sie Sie jedoch manuell aktivieren möchten, führen Sie die folgenden Schritte aus.
  
+ Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um die Formatbibliothek als öffentlichen Ursprung zu definieren.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um die Gestaltungsvorlagen als öffentlichen Ursprung zu definieren.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Beispiel: Konfigurieren eines privaten Ursprungs für Ihre Website Objekte, Website Seiten und Veröffentlichungs Bilder für SharePoint Online

+ Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um den Ordner Website Objekte als privaten Ursprung zu definieren.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um den Ordner Website Seiten als privaten Ursprung zu definieren.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um den Ordner Veröffentlichungs Bilder als privaten Ursprung zu definieren.

``` powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Beispiel: Konfigurieren eines privaten Ursprungs für eine Websitesammlung für SharePoint Online

Verwenden Sie das Cmdlet **Add-PnPTenantCdnOrigin** , um eine Websitesammlung als privaten Ursprung zu definieren. Beispiel:

``` powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).
  
Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter hinweg. Möglicherweise wird eine _ausstehende Konfigurations_ Meldung angezeigt, die erwartet wird, wenn der SharePoint Online-Mandant eine Verbindung mit dem CDN-Dienst herstellt. Dies kann bis zu 15 Minuten dauern.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Verwalten des Office 365 CDN

Nachdem Sie das CDN eingerichtet haben, können Sie, wie in diesem Abschnitt beschrieben, Änderungen an der Konfiguration vornehmen, wenn Sie Inhalte aktualisieren oder Ihre Anforderungen ändern.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Hinzufügen, aktualisieren oder Entfernen von Objekten aus dem Office 365 CDN

Nachdem Sie die Setupschritte abgeschlossen haben, können Sie neue Objekte hinzufügen und vorhandene Objekte aktualisieren oder entfernen, wann immer Sie möchten. Nehmen Sie einfach Ihre Änderungen an den Objekten im Ordner oder in der SharePoint-Bibliothek vor, die Sie als Ursprung identifiziert haben. Wenn Sie ein neues Objekt hinzufügen, steht es sofort über das CDN zur Verfügung. Wenn Sie das Objekt aktualisieren, dauert es jedoch bis zu 15 Minuten, bis die neue Kopie weitergegeben wird und im CDN verfügbar ist.
  
Wenn Sie den Speicherort des Ursprungs abrufen möchten, können Sie das Cmdlet **Get-PnPTenantCdnOrigin** verwenden. Informationen zur Verwendung dieses Cmdlets finden Sie unter [Get-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Entfernen eines Ursprungs aus dem Office 365 CDN

Sie können den Zugriff auf einen Ordner oder eine SharePoint-Bibliothek, den Sie als Ursprung identifiziert haben, entfernen. Verwenden Sie dazu das Cmdlet **Remove-PnPTenantCdnOrigin** .

``` powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Informationen zur Verwendung dieses Cmdlets finden Sie unter [Remove-PnPTenantCdnOrigin](https://docs.microsoft.com/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Ändern eines Ursprungs im Office 365 CDN

Sie können einen erstellten Ursprung nicht ändern. Entfernen Sie stattdessen den Ursprung, und fügen Sie dann einen neuen ein. Weitere Informationen finden Sie unter [So entfernen Sie einen Ursprung aus dem Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) und [fügen einen Ursprung für Ihre Objekte hinzu](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Deaktivieren des Office 365 CDN

Verwenden Sie das Cmdlet " **PnPTenantCdnEnabled** ", um das CDN für Ihre Organisation zu deaktivieren. Wenn Sie sowohl den öffentlichen als auch den privaten Ursprung für das CDN aktiviert haben, müssen Sie das Cmdlet zweimal ausführen, wie in den folgenden Beispielen dargestellt.
  
Geben Sie den folgenden Befehl ein, um die Verwendung der öffentlichen Herkunft im CDN zu deaktivieren:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Geben Sie den folgenden Befehl ein, um die Verwendung der privaten Ursprünge im CDN zu deaktivieren:

``` powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Weitere Informationen zu diesem Cmdlet finden Sie unter [Sets-PnPTenantCdnEnabled](https://docs.microsoft.com/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Einrichten und Konfigurieren des Office 365 CDN mithilfe von Office 365 CLI

Für die Verfahren in diesem Abschnitt müssen Sie die [Office 365 CLI](https://aka.ms/o365cli)installiert haben. Stellen Sie als nächstes eine Verbindung mit dem Office 365-Mandanten mithilfe des [Login](https://pnp.github.io/office365-cli/cmd/login/) -Befehls her.

Führen Sie die folgenden Schritte aus, um das CDN so einzurichten und zu konfigurieren, dass es Ihre Objekte in SharePoint Online mithilfe der Office 365 CLI hostet.

<details>
  <summary>Zum Erweitern klicken</summary>

### <a name="enable-the-office-365-cdn"></a>Aktivieren Sie das Office 365 CDN

Sie können den Status des Office 365 CDN in Ihrem Mandanten mithilfe des Cmdlets [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) verwalten.

Um das öffentliche Office 365 CDN in Ihrem Mandanten zu aktivieren, führen Sie Folgendes aus:

```sh
spo cdn set --type Public --enabled true
```

Um die Office 365 SharePoint CDN zu aktivieren, führen Sie Folgendes aus:

```sh
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Anzeigen des aktuellen Status des Office 365 CDN

Um zu überprüfen, ob der bestimmte Typ von Office 365 CDN aktiviert oder deaktiviert ist, verwenden Sie den Befehl [SPO CDN Get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) .

Um zu überprüfen, ob das öffentliche Office 365 CDN aktiviert ist, führen Sie Folgendes aus:

```sh
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Anzeigen der Office 365 CDN-Ursprünge

Um die derzeit konfigurierten öffentlichen Office 365 CDN-Ursprünge anzuzeigen, führen Sie Folgendes aus:

```sh
spo cdn origin list --type Public
```

Informationen zu den Ursprüngen, die standardmäßig bereitgestellt werden, wenn Sie das Office 365 CDN aktivieren, finden Sie unter [default CDN Origins](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) .

### <a name="add-an-office-365-cdn-origin"></a>Hinzufügen eines Office 365 CDN-Ursprungs

> [!IMPORTANT]
> Sie sollten niemals Ressourcen, die als vertraulich für Ihre Organisation betrachtet werden, in einer SharePoint-Dokumentbibliothek platzieren, die als öffentlicher Ursprung konfiguriert ist.

Verwenden Sie den Befehl [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) zum Definieren eines CDN-Ursprungs. Sie können mehrere Ursprünge definieren. Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.

```sh
spo cdn origin add --type [Public | Private] --origin <path>
```

Dabei `path` ist der relative Pfad zu dem Ordner, der die Objekte enthält. Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden.

Wenn Sie alle Objekte im **gestaltungsvorlagenkatalog** aller Websites als öffentlichen Ursprung einbeziehen möchten, führen Sie Folgendes aus:

```sh
spo cdn origin add --type Public --origin */masterpage
```

Um einen privaten Ursprung für eine bestimmte Websitesammlung zu konfigurieren, führen Sie Folgendes aus:

```sh
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> Nach dem Hinzufügen eines CDN-Ursprungs dauert es bis zu 15 Minuten, bis Sie Dateien mithilfe des CDN-Diensts abrufen können. Sie können überprüfen, ob der betreffende Ursprung bereits aktiviert wurde, indem Sie den Befehl [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) verwenden.

### <a name="remove-an-office-365-cdn-origin"></a>Entfernen eines Office 365 CDN-Ursprungs

Verwenden Sie den Befehl [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/), um einen CDN-Ursprung für den angegebenen CDN-Typ zu entfernen.

Wenn Sie einen öffentlichen Ursprung aus der CDN-Konfiguration entfernen möchten, führen Sie Folgendes aus:

```sh
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> Das Entfernen eines CDN-Ursprungs wirkt sich nicht auf die Dateien aus, die in einer Dokumentbibliothek gespeichert sind, die diesem Ursprung entspricht. Wenn auf diese Objekte über Ihre SharePoint-URL verwiesen wurde, wechselt SharePoint automatisch wieder zu der ursprünglichen URL, die auf die Dokumentbibliothek zeigt. Wenn jedoch auf Objekte mithilfe einer öffentlichen CDN-URL verwiesen wurde, wird durch das Entfernen des Ursprungs die Verknüpfung aufgehoben, und Sie müssen Sie manuell ändern.

### <a name="modify-an-office-365-cdn-origin"></a>Ändern eines Office 365 CDN-Ursprungs

Es ist nicht möglich, einen vorhandenen CDN-Ursprung zu ändern. Stattdessen sollten Sie den zuvor definierten CDN-Ursprung mit dem Befehl `spo cdn origin remove` entfernen und mit dem Befehl `spo cdn origin add` einen neuen hinzufügen.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Ändern der Dateitypen, die in das Office 365 CDN eingeschlossen werden sollen

Standardmäßig sind die folgenden Dateitypen in den CDN-Dateien enthalten: _CSS, EOT, GIF, ICO, JPEG, JPG, JS, map, PNG, SVG, ttf, WOFF und woff2_. Wenn Sie weitere Dateitypen in das CDN einbeziehen müssen, können Sie die CDN-Konfiguration mit dem Befehl [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) ändern.

> [!NOTE]
> Durch das Ändern der Liste von Dateitypen überschreiben Sie die aktuell definierte Liste. Wenn Sie weitere Dateitypen einbeziehen möchten, verwenden Sie zunächst den Befehl [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/), um herauszufinden, welche Dateitypen derzeit konfiguriert sind.

Um den _JSON_ -Dateityp der Standardliste der im öffentlichen CDN enthaltenen Dateitypen hinzuzufügen, führen Sie Folgendes aus:

```sh
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Ändern der Liste von Websiteklassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten

Verwenden Sie den Befehl [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) zum Ausschließen von Websiteklassifizierungen, die Sie nicht über das CDN zur Verfügung stellen möchten. Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.

> [!NOTE]
> Durch das Ändern der Liste der ausgeschlossenen Websiteklassifizierungen überschreiben Sie die aktuell definierte Liste. Wenn Sie zusätzliche Klassifizierungen ausschließen möchten, verwenden Sie zunächst den Befehl [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/), um herauszufinden, welche Klassifizierungen derzeit konfiguriert sind.

Zum Ausschließen von als _HBI_ klassifizierten Websites aus dem öffentlichen CDN führen Sie

```sh
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Deaktivieren des Office 365 CDN

Um das Office 365 CDN zu deaktivieren, verwenden Sie den Befehl `spo cdn set`. Beispiel:

```sh
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Verwenden Ihrer CDN-Ressourcen

Nachdem Sie nun das CDN und die konfigurierten Ursprünge und Richtlinien aktiviert haben, können Sie mit der Verwendung ihrer CDN-Objekte beginnen.

In diesem Abschnitt erfahren Sie, wie Sie CDN-URLs in SharePoint-Seiten und-Inhalten verwenden, damit SharePoint-Anforderungen für Objekte sowohl in öffentlichen als auch privaten Quellen an das CDN umleiten.

+ [Aktualisieren von Links zu CDN-Objekten](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Verwenden von Objekten im öffentlichen Ursprung](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Verwenden von Objekten im privaten Ursprung](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Informationen zum Verwenden des CDN zum Hosten clientseitiger Webparts finden Sie im Thema Hosten des [clientseitigen Webparts aus Office 365 CDN (Hello World Teil 4)](https://docs.microsoft.com/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn).

> [!NOTE]
> Wenn Sie den Ordner _ClientSideAssets_ der Liste **private** CDN Origins hinzufügen, wird das Rendern von in CDN gehosteten benutzerdefinierten Webparts nicht möglich. Dateien, die von SPFX-Webparts verwendet werden, können nur das öffentliche CDN verwenden, und der ClientSideAssets-Ordner ist ein Standardursprung für das öffentliche CDN. 

### <a name="updating-links-to-cdn-assets"></a>Aktualisieren von Links zu CDN-Objekten

Um Objekte zu verwenden, die Sie einem Ursprung hinzugefügt haben, aktualisieren Sie einfach Links zur ursprünglichen Datei mit dem Pfad zur Datei im Ursprung.

+ Bearbeiten Sie die Seite oder den Inhalt, die Links zu Objekten enthält, die Sie zu einem Ursprung hinzugefügt haben. Sie können auch eine von mehreren Methoden verwenden, um Links in einer Website oder Websitesammlung Global zu suchen und zu ersetzen, wenn Sie den Link zu einem bestimmten Objekt überall dort aktualisieren möchten, wo es angezeigt wird.
+ Ersetzen Sie für jeden Link zu einem Objekt in einem Ursprung den Pfad durch den Pfad zu der Datei im CDN-Ursprung. Sie können relative Pfade verwenden.
+ Speichern Sie die Seite oder den Inhalt.

Sehen Sie sich beispielsweise das Bild _/Site/SiteAssets/Images/image.png_an, das Sie in den Dokumentbibliotheksordner _/Site/CDN_origins/Public/_ kopiert haben. Um das CDN-Objekt zu verwenden, ersetzen Sie den ursprünglichen Pfad zum Speicherort der Bild Datei durch den Pfad zum Ursprung, um die neue URL _/Site/CDN_origins/Public/image.png_zu machen.

Wenn Sie die vollständige URL für das Objekt anstelle eines relativen Pfads verwenden möchten, erstellen Sie den Link wie folgt:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> Im Allgemeinen sollten Sie URLs nicht direkt in Objekten im CDN hartcodieren. Sie können jedoch URLs für Objekte im öffentlichen Ursprung bei Bedarf manuell erstellen. Weitere Informationen finden Sie unter [hartcodieren von CDN-URLs für öffentliche Objekte](use-microsoft-365-cdn-with-spo.md#hardcoding-cdn-urls-for-public-assets).

Informationen dazu, wie Sie überprüfen können, ob Objekte aus dem CDN bedient werden, finden Sie unter [wie kann ich bestätigen, dass Objekte vom CDN bedient werden?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in der [Problembehandlung im Abschnitt Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) .

### <a name="using-assets-in-public-origins"></a>Verwenden von Objekten im öffentlichen Ursprung

Das **Veröffentlichungsfeature** in SharePoint Online schreibt automatisch URLs von Objekten, die im öffentlichen Ursprung gespeichert sind, in Ihre CDN-äquivalente um, sodass Objekte vom CDN-Dienst anstelle von SharePoint bereitgestellt werden.

Wenn sich Ihr Ursprung in einer Website befindet, in der das Veröffentlichungsfeature aktiviert ist, und die Objekte, die Sie an das CDN Abladen möchten, sich in einer der folgenden Kategorien befinden, werden von SharePoint automatisch URLs für Objekte im Ursprung umgeschrieben, vorausgesetzt, das Objekt wurde nicht durch eine CDN-Richtlinie ausgeschlossen.

Es folgt eine Übersicht über die Links, die automatisch vom SharePoint-Veröffentlichungsfeature umgeschrieben werden:

+ IMG/LINK/CSS-URLs in den HTML-Antworten klassischer Veröffentlichungsseiten
  + Dies schließt von Autoren im HTML-Inhalt einer Seite hinzugefügte Bilder ein.
+ Bild-URLs des Webparts „Bildbibliothek-Bildschirmpräsentation“
+ Bildfelder in Ergebnissen der SPList-REST-API (RenderListDataAsStream)
  + Verwenden Sie die neue Eigenschaft _ImageFieldsToTryRewriteToCdnUrls_ , um eine durch Kommas getrennte Liste von Feldern bereitzustellen.
  + Unterstützt Hyperlink-Felder und Publishing Image-Felder
+ SharePoint-Bildwiedergaben

Das folgende Diagramm veranschaulicht den Workflow, wenn SharePoint eine Anforderung für eine Seite erhält, die Objekte aus einem öffentlichen Ursprung enthält.

![Workflow Diagramm: Abrufen Office 365 CDN-Ressourcen von einem öffentlichen Ursprung](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Abrufen von Office 365 CDN-Ressourcen von einem öffentlichen Ursprung")

> [!TIP]
> Wenn Sie die automatische Umschreibung für bestimmte URLs auf einer Seite deaktivieren möchten, können Sie die Seite Auschecken und den Abfragezeichenfolgenparameter hinzufügen **? NoAutoReWrites = true** an das Ende jeder Verknüpfung, die Sie deaktivieren möchten.

#### <a name="hardcoding-cdn-urls-for-public-assets"></a>Codieren von CDN-URLs für öffentliche Objekte

Wenn das _Veröffentlichungs_ Feature nicht für einen öffentlichen Ursprung aktiviert ist oder wenn es sich nicht um einen der Linktypen handelt, die von der Funktion zum automatischen Umschreiben des CDN-Diensts unterstützt werden, können Sie URLs manuell für den CDN-Speicherort der Objekte erstellen und diese URLs in ihren Inhalten verwenden.

> [!NOTE]
> Sie können CDN-URLs nicht für Objekte in einem privaten Ursprung hartcodieren, da das erforderliche Zugriffstoken, das den letzten Abschnitt der URL bildet, zu dem Zeitpunkt generiert wird, zu dem die Ressource angefordert wird.

Für öffentliche CDN-Objekte wird das URL-Format wie folgt aussehen:

``` html
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Ersetzen Sie **TenantHostName** durch ihren Mandantennamen. Beispiel:

``` html
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

### <a name="using-assets-in-private-origins"></a>Verwenden von Objekten im privaten Ursprung

Für die Verwendung von Objekten in privater Herkunft ist keine zusätzliche Konfiguration erforderlich. SharePoint Online automatisch URLs für Objekte in privater Herkunft umschreibt, sodass Anforderungen für diese Objekte immer vom CDN bedient werden. Sie können keine URLs manuell für CDN-Objekte in privater Herkunft erstellen, da diese URLs Token enthalten, die von SharePoint Online automatisch generiert werden müssen, wenn das Objekt angefordert wird.

Der Zugriff auf Objekte im privaten Ursprung wird durch dynamisch generierte Token geschützt, die auf Benutzerberechtigungen für den Ursprung basieren, wobei die in den folgenden Abschnitten beschriebenen Einschränkungen beachtet werden. Benutzer benötigen mindestens **Lese** Zugriff auf die Ursprünge des CDN zum Rendern von Inhalten.

Das folgende Diagramm veranschaulicht den Workflow, wenn SharePoint eine Anforderung für eine Seite erhält, die Objekte aus einem privaten Ursprung enthält.

![Workflow Diagramm: Abrufen von Office 365 CDN-Ressourcen aus einem privaten Ursprung](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Abrufen von Office 365 CDN-Ressourcen aus einem privaten Ursprung")

#### <a name="token-based-authorization-in-private-origins"></a>Token-basierte Autorisierung in privater Herkunft

Der Zugriff auf Objekte im privaten Ursprung im Office 365 CDN wird durch von SharePoint Online generierte Token gewährt. Benutzer, die bereits über Berechtigungen für den Zugriff auf den vom Ursprung benannten Ordner oder die Bibliothek verfügen, erhalten automatisch Token, die dem Benutzer den Zugriff auf die Datei basierend auf Ihrer Berechtigungsstufe ermöglichen. Diese Zugriffstoken sind gültig für 30 bis 90 Minuten, nachdem Sie generiert wurden, um die Wiedergabe von Token zu schützen.

Nachdem das Zugriffstoken generiert wurde, gibt SharePoint Online einen benutzerdefinierten URI an den Client zurück, der zwei Autorisierungsparameter " _Eat_ " (Edge Authorization Token) und _OAT_ (Origin Authorization Token) enthält. Die Struktur der einzelnen Token ist _< "Ablaufzeit im Epoch Time-Format" >__< "Secure Signature" >_. Beispiel:

``` html
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Jeder, der das Token besitzt, kann auf die Ressource im CDN zugreifen. URLs, die diese Zugriffstoken enthalten, werden jedoch nur über HTTPS freigegeben, sodass nicht autorisierte Benutzer auf das Objekt nicht zugreifen können, wenn die URL nicht explizit von einem Endbenutzer freigegeben wird, bevor das Token abläuft.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Berechtigungen auf Elementebene werden für Objekte im privaten Ursprung nicht unterstützt.

Es ist wichtig zu beachten, dass SharePoint Online keine Berechtigungen auf Elementebene für Objekte in privater Herkunft unterstützt. Beispielsweise haben Benutzer bei einer Datei `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` , die sich unter den folgenden Bedingungen befindet, effektiven Zugriff auf die Datei:

|Benutzer  |Berechtigungen  |Effektiver Zugriff  |
|---------|---------|---------|
|Benutzer 1     |Zugriff auf Folder1         |Zugriff auf image1.jpg aus dem CDN möglich         |
|Benutzer 2     |Kein Zugriff auf Folder1         |Zugriff auf image1.jpg aus dem CDN nicht möglich         |
|Benutzer 3     |Verfügt nicht über Zugriff auf Folder1, erhält jedoch explizite Berechtigungen für den Zugriff auf image1.jpg in SharePoint Online         |Kann direkt von SharePoint Online auf das Objekt image1.jpg zugreifen, jedoch nicht aus dem CDN         |
|Benutzer 4     |Hat Zugriff auf Folder1, wurde jedoch explizit den Zugriff auf image1.jpg in SharePoint Online verweigert.         |Der Zugriff auf das Objekt ist nicht von SharePoint Online möglich, kann jedoch aus dem CDN auf das Objekt zugreifen, obwohl der Zugriff auf die Datei in SharePoint Online verweigert wurde.         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Problembehandlung beim Office 365 CDN

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Wie bestätige ich, dass Objekte vom CDN bereitgestellt werden?

Nachdem Sie einer Seite Links zu CDN-Objekten hinzugefügt haben, können Sie überprüfen, ob das Objekt vom CDN bedient wird, indem Sie zur Seite navigieren, mit der rechten Maustaste auf das Bild klicken, nachdem es gerendert und die Bild-URL überprüft hat.

Sie können auch die Entwicklertools Ihres Browsers verwenden, um die URL für jedes Objekt auf einer Seite anzuzeigen, oder verwenden Sie ein Netzwerk Ablaufverfolgungstool eines Drittanbieters.

> [!NOTE]
> Wenn Sie ein Netzwerktool wie Fiddler verwenden, um Ihre Objekte außerhalb des Renderings des Objekts von einer SharePoint-Seite zu testen, müssen Sie den Referer-Header "Referer: `https://yourdomain.sharepoint.com` " manuell zur Get-Anforderung hinzufügen, wobei die URL die Stamm-URL des SharePoint Online Mandanten ist.

Sie können CDN-URLs nicht direkt in einem Webbrowser testen, da ein Referer aus SharePoint Online stammen muss. Wenn Sie jedoch die CDN-Ressourcen-URL zu einer SharePoint-Seite hinzufügen und dann die Seite in einem Browser öffnen, wird das auf der Seite gerenderte CDN-Objekt angezeigt.

Weitere Informationen zur Verwendung der Entwicklertools im Microsoft Edge-Browser finden Sie unter [Microsoft Edge Developer Tools](https://docs.microsoft.com/microsoft-edge/devtools-guide).

Wenn Sie ein kurzes Video im [YouTube-Kanal für SharePoint-Entwickler Muster und-Methoden](https://aka.ms/sppnp-videos) sehen möchten, in dem gezeigt wird, wie Sie überprüfen können, ob Ihr CDN funktioniert, lesen Sie bitte [Überprüfen der CDN-Nutzung und sicherstellen einer optimalen Netzwerkkonnektivität](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5).

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Warum sind Objekte aus einem neuen Ursprung nicht verfügbar?
Objekte in neuem Ursprung stehen nicht sofort zur Verwendung zur Verfügung, da es Zeit dauert, bis sich die Registrierung über das CDN verbreitet und die Ressourcen vom Ursprung bis zum CDN-Speicher hochgeladen werden. Die erforderliche Zeit für die Verfügbarkeit von Objekten im CDN hängt davon ab, wie viele Objekte und Dateigrößen verfügbar sind.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>Mein clientseitiges Webpart oder SharePoint Framework-Lösung funktioniert nicht

Wenn Sie das Office 365 CDN für öffentliche Ursprünge aktivieren, erstellt der CDN-Dienst automatisch diese Standard Ursprünge:

+ */MASTERPAGE
+ */Style-Bibliothek
+ */CLIENTSIDEASSETS

Wenn der */clientsideassets-Ursprung fehlt, treten bei SharePoint-Framework-Lösungen Fehler auf, und es werden keine Warnungen oder Fehlermeldungen generiert. Dieser Ursprung fehlt möglicherweise, weil das CDN aktiviert wurde, wenn der Parameter _-NoDefaultOrigins_ auf **$true**festgelegt wurde oder der Ursprung manuell gelöscht wurde.

Sie können überprüfen, welche Ursprünge mit dem folgenden PowerShell-Befehl vorhanden sind:

``` powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

Oder Sie können mit der Office 365 CLI überprüfen:

``` powershell
spo cdn origin list
```

So fügen Sie den Ursprung in PowerShell hinzu:

``` powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

So fügen Sie den Ursprung in der Office 365 CLI hinzu:

``` powershell
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Welche PowerShell-Module und CLI-Shells muss ich mit dem Office 365 CDN verwenden?

Sie können mit dem Office 365 CDN entweder mithilfe des PowerShell-Moduls von **SharePoint Online Verwaltungsshell** oder der **Office 365 CLI**arbeiten.

+ [Erste Schritte mit der SharePoint Online-Verwaltungsshell](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [Installieren von Office 365 CLI](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>Siehe auch

[Netzwerke für die Inhaltsübermittlung](https://aka.ms/o365cdns)

[Netzwerkplanung und Leistungsoptimierung für Office 365](https://aka.ms/tune)

[SharePoint-Leistungsreihe-Office 365 CDN-Videoreihe](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
