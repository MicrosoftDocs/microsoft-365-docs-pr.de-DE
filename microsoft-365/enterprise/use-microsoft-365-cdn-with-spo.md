---
title: Verwenden Office 365 Content Delivery Network (CDN) mit SharePoint Online
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
description: Erfahren Sie, wie Sie Office 365 Content Delivery Network (CDN) verwenden, um die Bereitstellung Ihrer SharePoint Onlineressourcen zu beschleunigen.
ms.openlocfilehash: 6819f627d3590cd2739b36cb1bc303f197d6aaa5
ms.sourcegitcommit: 6e5c00f84b5201422aed094f2697016407df8fc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51570405"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online

Sie können statische Objekte im Office 365-Netzwerk für die Inhaltsübermittlung (CDN) hosten, um eine bessere Leistung für Ihre SharePoint Online-Seiten zu ermöglichen. Das Office 365-Netzwerk für die Inhaltsübermittlung verbessert die Leistung, indem statische Objekte näher an den Browsern zwischengespeichert werden, die diese anfordern, wodurch Downloads beschleunigt werden und die Latenz reduziert wird. Darüber hinaus verwendet Office 365 CDN [http/2-Protokoll](https://en.wikipedia.org/wiki/HTTP/2) für verbesserte Komprimierung und HTTP-Pipelining. Das Office 365-Netzwerk für die Inhaltsübermittlung ist in Ihrem SharePoint Online-Abonnement enthalten.

> [!NOTE]
> Die Office 365 CDN ist nur für Mandanten in der **Produktions-Cloud** (weltweit) verfügbar. Mandanten in der US-Regierung, China und Deutschland unterstützen die Office 365 CDN.

Das Office 365-Netzwerk für die Inhaltsübermittlung besteht aus mehreren CDNs, über die Sie statische Objekte an mehreren Speicherorten hosten können, oder aus _Ursprüngen_, die aus globalen Hochgeschwindigkeitsnetzwerken bedient werden. In Abhängigkeit von der Art der Inhalte, die Sie im Office 365-Netzwerk für die Inhaltsübermittlung hosten möchten, können Sie **öffentliche** Ursprünge, **private** Ursprünge oder beides hinzufügen. Weitere Informationen zum Unterschied zwischen öffentlichen und privaten Ursprüngen finden Sie unter Choose whether each [origin should be public or private.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

![Office 365 CDN Konzeptionelles Diagramm](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN Konzeptionelles Diagramm")

Wenn Sie bereits mit der Funktion von CDNs vertraut sind, müssen Sie nur einige Schritte ausführen, um die Office 365 CDN für Ihren Mandanten zu aktivieren. In diesem Thema wird die Funktionsweise beschrieben. Weitere Informationen dazu, wie Sie mit dem Hosten Ihrer statischen Objekte beginnen können, finden Sie weiter.

> [!TIP]
> Es gibt andere von Microsoft gehostete CDNs, die mit Office 365 für spezielle Verwendungsszenarien verwendet werden können, aber in diesem Thema nicht behandelt werden, da sie nicht in den Bereich der Office 365 CDN. Weitere Informationen finden Sie unter [Other Microsoft CDNs](content-delivery-networks.md#other-microsoft-cdns).

 **Führen Sie zurück zu [Netzwerkplanung und Leistungsoptimierung für Office 365.](./network-planning-and-performance.md)**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Übersicht über die Arbeit mit Office 365 CDN in SharePoint Online

Zum Einrichten der Office 365 CDN für Ihre Organisation führen Sie die folgenden grundlegenden Schritte aus:

+ [Planen der Bereitstellung der Office 365 CDN](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Bestimmen Sie, welche statischen Objekte Sie auf der CDN.](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Bestimmen Sie, wo Ihre Objekte gespeichert werden.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets) Dieser Speicherort kann eine SharePoint, Bibliothek oder Ordner sein und wird als Ursprung _bezeichnet._
  + [Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) Sie können mehrere Ursprünge von öffentlichen und privaten Typen hinzufügen.

+ Einrichten und Konfigurieren der CDN mithilfe von PowerShell oder der SharePoint Online CLI

  + [Einrichten und Konfigurieren der CDN mithilfe der SharePoint Online-Verwaltungsshell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Einrichten und Konfigurieren der CDN mithilfe von PnP PowerShell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Einrichten und Konfigurieren der CDN mithilfe der Office 365 CLI](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  Wenn Sie diesen Schritt abschließen, haben Sie:

  + Aktiviert die CDN für Ihre Organisation.
  + Ihre Ursprünge wurden hinzugefügt, und jeder Ursprung wurde als öffentlich oder privat identifiziert.

Nachdem Sie das Setup abgeschlossen haben, können Sie die Office 365 CDN [verwalten,](use-microsoft-365-cdn-with-spo.md#CDNManage) indem Sie:
  
+ Hinzufügen, Aktualisieren und Entfernen von Ressourcen
+ Hinzufügen und Entfernen von Ursprüngen
+ Konfigurieren CDN Richtlinien
+ Falls erforderlich, deaktivieren Sie CDN

Weitere Informationen zum Zugriff auf CDN von öffentlichen und privaten Ursprüngen finden Sie unter Using [your CDN assets.](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets)

Unter [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) finden Sie Anleitungen zur Lösung gängiger Probleme.

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Planen der Bereitstellung der Office 365 CDN

Bevor Sie die Office 365 CDN für Office 365 bereitstellen, sollten Sie die folgenden Faktoren im Rahmen des Planungsprozesses berücksichtigen.

  + [Bestimmen Sie, welche statischen Objekte Sie auf dem Server hosten CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Bestimmen, wo Ihre Objekte gespeichert werden möchten](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Bestimmen Sie, welche statischen Objekte Sie auf dem Server hosten CDN

Im Allgemeinen sind CDNs am effektivsten für das Hosten statischer Objekte _oder_ Objekte, die sich nicht sehr häufig ändern. Eine gute Faustregel ist das Identifizieren von Dateien, die einige oder alle dieser Bedingungen erfüllen:

+ Statische Dateien, die in eine Seite eingebettet sind (z. B. Skripts und Bilder), die erhebliche inkrementelle Auswirkungen auf die Ladezeiten der Seite haben können
+ Große Dateien wie ausführbare Dateien und Installationsdateien
+ Ressourcenbibliotheken, die clientseitigen Code unterstützen

Beispielsweise können kleine Dateien, die wiederholt angefordert werden, z. B. Websitebilder und Skripts, die Leistung des Websiterenderings erheblich verbessern und die Auslastung Ihrer SharePoint Onlinewebsites inkrementell reduzieren, wenn Sie sie einem CDN hinzufügen. Größere Dateien, z. B. ausführbare Installationsdateien, können aus dem CDN heruntergeladen werden, was eine positive Leistungsbelastung und eine nachfolgende Reduzierung der Last auf Ihrer SharePoint Online-Website zur Folge hat, auch wenn nicht so oft darauf zugegriffen wird.

Die Leistungsverbesserung pro Datei hängt von vielen Faktoren ab, z. B. der Nähe des Clients zum nächstgelegenen CDN-Endpunkt, vorübergehenden Bedingungen im lokalen Netzwerk usw. Viele statische Dateien sind recht klein und können aus Office 365 in weniger als einer Sekunde heruntergeladen werden. Eine Webseite kann jedoch viele eingebettete Dateien mit einer kumulierten Downloadzeit von mehreren Sekunden enthalten. Wenn Sie diese Dateien aus dem CDN, kann die Ladezeit der Seite insgesamt erheblich reduziert werden. Ein Beispiel finden Sie unter [Welche Leistungsgewinne bietet CDN?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide)

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Bestimmen, wo Ihre Objekte gespeichert werden möchten

Die CDN ruft Ihre Objekte von einem Speicherort ab, der als Ursprung _bezeichnet wird._ Ein Ursprung kann eine website SharePoint Dokumentbibliothek oder ein Ordner sein, auf die über eine URL zugegriffen werden kann. Sie haben große Flexibilität beim Angeben von Ursprüngen für Ihre Organisation. Sie können z. B. mehrere Ursprünge oder einen einzelnen Ursprung angeben, an dem Sie alle CDN festlegen möchten. Sie können sowohl öffentliche als auch private Ursprünge für Ihre Organisation auswählen. Die meisten Organisationen entscheiden sich dafür, eine Kombination aus beiden zu implementieren.

Sie können einen neuen Container für Ihre Ursprünge erstellen, z. B. Ordner oder Dokumentbibliotheken, und Dateien hinzufügen, die Sie über die Website CDN. Dies ist ein guter Ansatz, wenn Sie über eine bestimmte Gruppe von Ressourcen verfügen, die über die CDN verfügbar sein sollen, und den Satz von CDN-Ressourcen auf diese Dateien im Container beschränken möchten.

Sie können auch eine vorhandene Websitesammlung, Website, Bibliothek oder einen Ordner als Ursprung konfigurieren, wodurch alle berechtigten Objekte im Container über die CDN. Bevor Sie einen vorhandenen Container als Ursprung hinzufügen, müssen Sie sicherstellen, dass Sie sich dessen Inhalte und Berechtigungen bewusst sind, damit Sie Objekte nicht versehentlich anonymen Zugriffen oder nicht autorisierten Benutzern verfügbar machen.

Sie können _richtlinienrichtlinien CDN,_ um Inhalte in Ihren Ursprüngen aus dem CDN. CDN werden Objekte in öffentlichen oder privaten Ursprüngen  durch Attribute wie Dateityp und Websiteklassifizierung ausgeschlossen und auf alle Ursprünge des cdnType (privat oder öffentlich) angewendet, den Sie in der Richtlinie angeben. Wenn Sie z. B. einen privaten Ursprung hinzufügen, der aus einer Website besteht,  die mehrere Unterwebsites enthält, können Sie eine Richtlinie zum Ausschließen von Websites definieren, die als Vertraulich markiert sind, damit Inhalte von Websites, auf die diese Klassifizierung angewendet wurde, nicht von der Website CDN. Die Richtlinie gilt für Inhalte von _allen_ privaten Ursprüngen, die Sie dem CDN.
  
Denken Sie daran, dass je größer die Anzahl der Ursprünge ist, desto größer ist die Auswirkung auf die Zeit, die der Dienst CDN Verarbeiten von Anforderungen benötigt. Es wird empfohlen, die Anzahl der Ursprünge so weit wie möglich zu beschränken.
  
<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll

Wenn Sie einen Ursprung identifizieren, geben Sie an, ob er öffentlich _oder_ privat gemacht werden _soll._ Der Zugriff auf CDN öffentlichen Ursprüngen ist anonym, und CDN Inhalte privater Ursprünge werden durch dynamisch generierte Token für mehr Sicherheit gesichert. Unabhängig davon, welche Option Sie auswählen, führt Microsoft alles für Sie aus, wenn es um die Verwaltung des CDN geht. Darüber hinaus können Sie Ihre Meinung später ändern, nachdem Sie den CDN und Ihre Ursprünge identifiziert haben.

Sowohl öffentliche als auch private Optionen bieten ähnliche Leistungsgewinne, aber jede bietet eindeutige Attribute und Vorteile.

**Öffentliche** Ursprünge innerhalb der Office 365 CDN anonym zugänglich, und auf gehostete Objekte kann jeder zugreifen, der über die URL zum Objekt verfügt. Da der Zugriff auf Inhalte in öffentlichen Ursprüngen anonym ist, sollten Sie diese nur zum Zwischenspeichern von nicht vertraulichen generischen Inhalten verwenden, z. B. JavaScript-Dateien, Skripts, Symbole oder Bilder.

**Private** Ursprünge innerhalb der Office 365 CDN privaten Zugriff auf Benutzerinhalte wie SharePoint Online-Dokumentbibliotheken, Websites und proprietäre Bilder. Der Zugriff auf Inhalte privater Herkunft wird durch dynamisch generierte Token gesichert, sodass nur benutzer mit Berechtigungen für die ursprüngliche Dokumentbibliothek oder den Speicherort darauf zugreifen können. Private Ursprünge im Office 365 CDN können nur für SharePoint Onlineinhalte verwendet werden, und Sie können nur über eine Umleitung von Ihrem SharePoint Online-Mandanten auf Objekte privater Ursprünge zugreifen.

Weitere Informationen dazu, wie CDN zugriff auf Objekte privater Herkunft funktioniert, finden Sie unter Verwenden von Vermögenswerten [in privaten Ursprüngen](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins).

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Attribute und Vorteile des Hostings von Ressourcen in öffentlichen Ursprüngen
  
+ Objekte, die an einem öffentlichen Ursprung verfügbar gemacht werden, sind für jeden Benutzer anonym zugänglich.
    > [!IMPORTANT]
    > Sie sollten niemals Ressourcen platzieren, die Benutzerinformationen enthalten oder als vertraulich für Ihre Organisation in einem öffentlichen Ursprung betrachtet werden.

+ Wenn Sie ein Objekt aus einem öffentlichen Ursprung entfernen, ist es unter Umständen bis zu 30 Tage lang weiterhin über den Cache verfügbar. Links zu dem Objekt im CDN werden jedoch innerhalb von 15 Minuten ungültig.

+ Wenn Sie Stylesheets (CSS-Dateien) an einem öffentlichen Ursprung hosten, können Sie im Code relative Pfade und URIs verwenden. Dies bedeutet, dass Sie auf den Speicherort von Hintergrundbildern und anderen Objekten relativ zum Speicherort des Objekts, das sie aufruft, verweisen können.

+ Während Sie die URL eines öffentlichen Ursprungs erstellen können, sollten Sie mit Vorsicht vorgehen und sicherstellen, dass Sie die Seitenkontexteigenschaft verwenden und die Anleitungen dazu befolgen. Der Grund hierfür ist folgender: Wenn der Zugriff auf das CDN nicht mehr verfügbar ist, wird die URL nicht automatisch auf Ihre Organisation in SharePoint Online aufgelöst, was zu fehlerhaften Links und anderen Fehlern führen kann. Die URL kann ebenfalls geändert werden, weshalb sie nicht nur hart auf den aktuellen Wert codiert werden sollte.

+ Die Standarddateitypen, die für öffentliche Ursprünge enthalten sind, sind CSS, .eot, .gif, .ico, .jpeg, .jpg, .js, .map, .png, .svg, .ttf, .woff und .woff2. Sie können zusätzliche Dateitypen angeben.

+ Sie können eine Richtlinie so konfigurieren, dass Objekte ausgeschlossen werden, die durch von Ihnen festgelegte Websiteklassifizierungen identifiziert wurden. Beispielsweise können Sie alle Objekte ausschließen, die als „vertraulich“ oder „eingeschränkt“ gekennzeichnet sind, auch wenn sie einen zulässigen Dateityp haben und sich an einem öffentlichen Ursprung befinden.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Attribute und Vorteile des Hostings von Ressourcen in privaten Ursprüngen

+ Private Ursprünge können nur für online SharePoint verwendet werden.

+ Benutzer können nur von einem privaten Ursprung aus auf die Objekte zugreifen, wenn sie über Berechtigungen für den Zugriff auf den Container verfügen. Der anonyme Zugriff auf diese Objekte wird verhindert.

+ Objekte mit privatem Ursprung müssen vom SharePoint Online-Mandanten verwiesen werden. Der direkte Zugriff auf private CDN funktioniert nicht.

+ Wenn Sie eine Ressource aus dem privaten Ursprung entfernen, ist die Ressource möglicherweise bis zu einer Stunde lang aus dem Cache verfügbar. Links zum Objekt werden jedoch innerhalb von CDN 15 Minuten nach dem Entfernen der Ressource ungültig.

+ Die standardmäßigen Dateitypen, die für private Ursprünge eingeschlossen werden, sind GIF, ICO, JPEG, JPG, JS und PNG. Sie können zusätzliche Dateitypen angeben.

+ Wie bei öffentlichen Ursprüngen können Sie eine Richtlinie so konfigurieren, dass Objekte ausgeschlossen werden, die durch von Ihnen festgelegte Websiteklassifizierungen identifiziert wurden, auch wenn Sie Platzhalter verwenden, um alle Objekte in einen Ordner oder eine Dokumentbibliothek einschließen zu können.

Weitere Informationen zur Verwendung der Office 365 CDN, allgemeinen CDN-Konzepten und anderen Microsoft CDNs, die Sie mit Ihrem Office 365-Mandanten verwenden können, finden Sie unter [Content Delivery Networks](content-delivery-networks.md).

### <a name="default-cdn-origins"></a>Standard CDN Ursprungs

Wenn Sie nichts anderes angeben, Office 365 sie einige Standardherkunftseinstellungen für Sie ein, wenn Sie die Office 365 CDN. Wenn Sie sie zunächst nicht bereitstellen möchten, können Sie diese Ursprünge hinzufügen, nachdem Sie die Einrichtung abgeschlossen haben. Wenn Sie die Folgen des Überspringens der Einrichtung der Standardherkunft nicht verstehen und einen bestimmten Grund dafür haben, sollten Sie zulassen, dass sie erstellt werden, wenn Sie die CDN.
  
Standardmäßige private CDN:
  
+ \*/userphoto.aspx
+ \*/siteassets

Standardmäßige öffentliche CDN:
  
+ \*/masterpage
+ \*/style library
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ ist ein öffentlicher Standardherkunft, der dem Dienst Office 365 CDN Dezember 2017 hinzugefügt wurde. Dieser Ursprung muss vorhanden sein, damit SharePoint-Framework Lösungen in der CDN funktionieren. Wenn Sie die Office 365 CDN vor Dezember 2017 aktiviert haben oder das Setup der Standardherkunft übersprungen haben, wenn Sie die CDN aktiviert haben, können Sie diesen Ursprung manuell hinzufügen. Weitere Informationen finden Sie unter [My client-side web part or SharePoint-Framework solution isn't working](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working).

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Einrichten und Konfigurieren der Office 365 CDN mithilfe der SharePoint Online-Verwaltungsshell

Für die Verfahren in diesem Abschnitt müssen Sie die SharePoint Online-Verwaltungsshell verwenden, um eine Verbindung mit SharePoint Online herzustellen. Weitere Anweisungen finden Sie unter [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps).

Führen Sie die folgenden Schritte aus, um das CDN für das Hosten Ihrer Ressourcen in SharePoint Online mithilfe der SharePoint Online-Verwaltungsshell zu konfigurieren.

<details>
  <summary>Zum Erweitern klicken</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Ermöglichen Sie Ihrer Organisation die Verwendung Office 365 CDN

Bevor Sie Änderungen an den Mandanteneinstellungen CDN vornehmen, sollten Sie den aktuellen Status der privaten CDN-Konfiguration in Ihrem Office 365 abrufen. Verbinden sie mithilfe der SharePoint Online-Verwaltungsshell an Ihren Mandanten:

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Verwenden Sie nun **das Cmdlet Get-SPOTenantCdnEnabled,** um die CDN statuseinstellungen aus dem Mandanten abzurufen:

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

Der Status der CDN für den angegebenen CdnType wird auf dem Bildschirm ausgegeben.

Verwenden Sie **das Cmdlet Set-SPOTenantCdnEnabled,** um Ihrer Organisation die Verwendung der Office 365 CDN. Sie können Ihrer Organisation die Verwendung öffentlicher, privater Oder beides gleichzeitig ermöglichen. Sie können das CDN auch so konfigurieren, dass die Einrichtung von Standardherkunftseinstellungen beim Aktivieren übersprungen wird. Sie können diese Ursprünge immer später hinzufügen, wie in diesem Thema beschrieben.
  
In Windows PowerShell for SharePoint Online:

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Geben Sie beispielsweise den folgenden Befehl ein, um ihrer Organisation die Verwendung öffentlicher und privater Ursprünge zu ermöglichen:

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Geben Sie den folgenden Befehl ein, um ihrer Organisation die Verwendung öffentlicher und privater Ursprünge zu ermöglichen, aber das Einrichten der Standardherkunftstypen zu überspringen:

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Informationen zu den CDN, die standardmäßig bereitgestellt werden, wenn Sie die Office 365 CDN aktivieren, sowie zu den möglichen Auswirkungen des Überspringens der Einrichtung von Standardherkunftsinformationen finden Sie unter Default [CDN origins.](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)

Geben Sie den folgenden Befehl ein, um ihrer Organisation die Verwendung öffentlicher Ursprünge zu ermöglichen:

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Geben Sie den folgenden Befehl ein, um ihrer Organisation die Verwendung privater Ursprünge zu ermöglichen:

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Weitere Informationen zu diesem Cmdlet finden Sie unter [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Ändern der Liste der Dateitypen, die in das Verzeichnis Office 365 CDN (Optional)

> [!TIP]
> Wenn Sie Dateitypen mithilfe des **Cmdlets Set-SPOTenantCdnPolicy** definieren, überschreiben Sie die aktuell definierte Liste. Wenn Sie der Liste weitere Dateitypen hinzufügen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Dateitypen bereits zulässig sind, und fügen Sie sie zusammen mit Ihren neuen in die Liste ein.
  
Verwenden Sie **das Cmdlet Set-SPOTenantCdnPolicy,** um statische Dateitypen zu definieren, die von öffentlichen und privaten Ursprüngen in der CDN. Standardmäßig sind allgemeine Objekttypen zulässig, z. B. CSS, .gif, .jpg und .js.

In Windows PowerShell for SharePoint Online:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Um z. B. das Hosten CDN CSS- und .png zu ermöglichen, geben Sie den Befehl ein:

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Verwenden Sie das **Cmdlet Get-SPOTenantCdnPolicies,** um zu sehen, welche Dateitypen derzeit vom CDN zulässig sind:

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Weitere Informationen zu diesen Cmdlets finden Sie unter [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) und [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Ändern der Liste der Websiteklassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten (Optional)

> [!TIP]
> Wenn Sie Websiteklassifizierungen mithilfe des **Cmdlets Set-SPOTenantCdnPolicy** ausschließen, überschreiben Sie die aktuell definierte Liste. Wenn Sie zusätzliche Websiteklassifizierungen ausschließen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Klassifizierungen bereits ausgeschlossen sind, und fügen Sie sie dann zusammen mit Ihren neuen hinzu.

Verwenden Sie das Cmdlet **Set-SPOTenantCdnPolicy** -Cmdlet zum Ausschließen von Websiteklassifizierungen, die Sie nicht über das CDN zur Verfügung stellen möchten. Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.

In Windows PowerShell for SharePoint Online:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Verwenden Sie das **Cmdlet Get-SPOTenantCdnPolicies,** um zu sehen, welche Websiteklassifizierungen derzeit eingeschränkt sind:

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Die zurückgegebenen Eigenschaften sind _IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ und _ExcludeIfNoScriptDisabled_.

Die _IncludeFileExtensions-Eigenschaft_ enthält die Liste der Dateierweiterungen, die aus dem CDN.

> [!NOTE]
> Die Standarddateierweiterungen unterscheiden sich zwischen öffentlich und privat.

Die _ExcludeRestrictedSiteClassifications-Eigenschaft_ enthält die Websiteklassifikationen, die Sie aus dem CDN. Sie können z. B. Websites ausschließen, die als **Vertraulich** gekennzeichnet sind, damit Inhalte von Websites, auf die diese Klassifizierung angewendet wurde, nicht aus dem CDN.

Die _ExcludeIfNoScriptDisabled-Eigenschaft_ schließt Inhalte aus CDN basierend auf den NoScript-Attributeinstellungen auf _Websiteebene_ aus. Standardmäßig ist das _NoScript-Attribut_ auf **Enabled** for _Modern sites_ und **Disabled** for _Classic sites_ festgelegt. Dies hängt von ihren Mandanteneinstellungen ab.

Weitere Informationen zu diesen Cmdlets finden Sie unter [Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/) und [Get-SPOTenantCdnPolicies](/powershell/module/sharepoint-online/).

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Hinzufügen eines Ursprungs für Ihre Objekte

Verwenden Sie **das Cmdlet Add-SPOTenantCdnOrigin,** um einen Ursprung zu definieren. Sie können mehrere Ursprünge definieren. Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.
  
> [!IMPORTANT]
> Sie sollten niemals Ressourcen platzieren, die Benutzerinformationen enthalten oder als vertraulich für Ihre Organisation in einem öffentlichen Ursprung betrachtet werden.

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Der Wert des _Pfads_ ist der relative Pfad zu der Bibliothek oder dem Ordner, der die Objekte enthält. Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden. Origins unterstützen Platzhalter, die der URL vorausgesprungen sind. Auf diese Weise können Sie Ursprünge erstellen, die mehrere Websites umfassen. Geben Sie z. B. den folgenden Befehl ein, um alle Ressourcen im Ordner Masterpages für alle Websites als öffentlichen Ursprung innerhalb der CDN ein:

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Der Platzhaltermodifizierer * kann nur am Anfang des Pfads verwendet werden und wird mit allen **/** #A0 unter der angegebenen URL übereinstimmen.
+ Der Pfad kann auf eine Dokumentbibliothek, einen Ordner oder eine Website verweisen. Beispielsweise wird der Pfad _*/site1_ mit allen Dokumentbibliotheken unter der Website übereinstimmen.

Sie können einen Ursprung mit einem bestimmten relativen Pfad hinzufügen. Sie können keinen Ursprung mithilfe des vollständigen Pfads hinzufügen.

In diesem Beispiel wird auf einer bestimmten Website ein privater Ursprung der Websiteassetbibliothek hinzugefügt:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In diesem Beispiel wird der Websiteressourcenbibliothek der Websitesammlung ein privater Ursprung des Ordners _"Ordner1"_ hinzugefügt:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Wenn ein Leerzeichen im Pfad vorhanden ist, können Sie den Pfad entweder in doppelte Anführungszeichen setzen oder das Leerzeichen durch die URL-Codierung "%20" ersetzen. In den folgenden Beispielen wird der Websiteressourcenbibliothek der Websitesammlung ein privater Ursprung des Ordners _1_ hinzugefügt:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

> [!NOTE]
> Bei privaten Ursprüngen muss für Objekte, die von einem Ursprung freigegeben werden, eine Hauptversion veröffentlicht werden, bevor sie von der CDN.
  
Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Beispiel: Konfigurieren eines öffentlichen Ursprungs für Ihre Masterseiten und für Ihre Formatbibliothek für SharePoint Online

Normalerweise werden diese Ursprünge standardmäßig für Sie eingerichtet, wenn Sie die Office 365 CDN. Wenn Sie sie jedoch manuell aktivieren möchten, führen Sie die folgenden Schritte aus.
  
+ Verwenden Sie **das Cmdlet Add-SPOTenantCdnOrigin,** um die Formatbibliothek als öffentlichen Ursprung zu definieren.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Verwenden Sie **das Cmdlet Add-SPOTenantCdnOrigin,** um die Masterseiten als öffentlichen Ursprung zu definieren.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Beispiel: Konfigurieren eines privaten Ursprungs für Ihre Websiteressourcen, Websiteseiten und Veröffentlichungsbilder für SharePoint Online

+ Verwenden Sie **das Cmdlet Add-SPOTenantCdnOrigin,** um den Ordner "Websiteressourcen" als privaten Ursprung zu definieren.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Verwenden Sie **das Cmdlet Add-SPOTenantCdnOrigin,** um den Websiteseitenordner als privaten Ursprung zu definieren.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Verwenden Sie **das Cmdlet Add-SPOTenantCdnOrigin,** um den Veröffentlichungsbildordner als privaten Ursprung zu definieren.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Beispiel: Konfigurieren eines privaten Ursprungs für eine Websitesammlung für SharePoint Online

Verwenden Sie **das Cmdlet Add-SPOTenantCdnOrigin,** um eine Websitesammlung als privaten Ursprung zu definieren. Beispiel:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).
  
Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter. Möglicherweise wird eine _Ausstehende Konfigurationsnachricht_ angezeigt, die erwartet wird, wenn der SharePoint Online-Mandant eine Verbindung mit dem CDN herstellt. Dies kann bis zu 15 Minuten dauern.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Verwalten der Office 365 CDN

Nachdem Sie die CDN eingerichtet haben, können Sie Änderungen an Ihrer Konfiguration vornehmen, wenn Sie Inhalte aktualisieren oder sich Ihre Anforderungen ändern, wie in diesem Abschnitt beschrieben.
  
<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Hinzufügen, Aktualisieren oder Entfernen von Ressourcen aus dem Office 365 CDN

Nachdem Sie die Setupschritte abgeschlossen haben, können Sie neue Objekte hinzufügen und vorhandene Objekte jederzeit aktualisieren oder entfernen. Nehmen Sie einfach Ihre Änderungen an den Ressourcen im Ordner oder SharePoint, die Sie als Ursprung identifiziert haben. Wenn Sie ein neues Objekt hinzufügen, ist es über die CDN verfügbar. Wenn Sie das Objekt aktualisieren, dauert es jedoch bis zu 15 Minuten, bis die neue Kopie in der Neuen Kopie verfügbar CDN.
  
Wenn Sie den Speicherort des Ursprungs abrufen müssen, können Sie das **Cmdlet Get-SPOTenantCdnOrigins** verwenden. Informationen zur Verwendung dieses Cmdlets finden Sie unter [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins).

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Entfernen eines Ursprungs aus Office 365 CDN

Sie können den Zugriff auf einen Ordner oder eine SharePoint, die Sie als Ursprung identifiziert haben, entfernen. Verwenden Sie dazu das **Cmdlet Remove-SPOTenantCdnOrigin.**

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Informationen zur Verwendung dieses Cmdlets finden Sie unter [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Ändern eines Ursprungs im Office 365 CDN

Sie können einen von Ihnen erstellten Ursprung nicht ändern. Entfernen Sie stattdessen den Ursprung, und fügen Sie dann einen neuen hinzu. Weitere Informationen finden Sie unter So entfernen Sie einen Ursprung [aus dem Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) und Fügen Sie einen Ursprung für Ihre Objekte [hinzu.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Deaktivieren der Office 365 CDN

Verwenden Sie **das Cmdlet Set-SPOTenantCdnEnabled,** um CDN für Ihre Organisation zu deaktivieren. Wenn sie sowohl die öffentlichen als auch die privaten Ursprünge für die CDN aktiviert haben, müssen Sie das Cmdlet zweimal ausführen, wie in den folgenden Beispielen gezeigt.
  
Geben Sie den folgenden Befehl ein, um die Verwendung öffentlicher CDN zu deaktivieren:

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Geben Sie den folgenden Befehl ein, um die Verwendung der privaten Ursprünge im CDN zu deaktivieren:

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Weitere Informationen zu diesem Cmdlet finden Sie unter [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled).

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Einrichten und Konfigurieren der Office 365 CDN mithilfe von PnP PowerShell

Für die Verfahren in diesem Abschnitt müssen Sie PnP PowerShell verwenden, um eine Verbindung mit SharePoint Online herzustellen. Anweisungen finden Sie unter [Erste Schritte mit PnP PowerShell](https://github.com/SharePoint/PnP-PowerShell#getting-started).

Führen Sie die folgenden Schritte aus, um das CDN für das Hosten Ihrer Ressourcen in SharePoint Online mit PnP PowerShell zu konfigurieren.

<details>
  <summary>Zum Erweitern klicken</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Ermöglichen Sie Ihrer Organisation die Verwendung Office 365 CDN

Bevor Sie Änderungen an den Mandanteneinstellungen CDN vornehmen, sollten Sie den aktuellen Status der privaten CDN-Konfiguration in Ihrem Office 365 abrufen. Verbinden mit PnP PowerShell an Ihren Mandanten:

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

Verwenden Sie nun **das Cmdlet Get-PnPTenantCdnEnabled,** um CDN Statuseinstellungen aus dem Mandanten abzurufen:

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

Der Status der CDN für den angegebenen CdnType wird auf dem Bildschirm ausgegeben.

Verwenden Sie **das Cmdlet Set-PnPTenantCdnEnabled,** um Ihrer Organisation die Verwendung der Office 365 CDN. Sie können Ihrer Organisation ermöglichen, öffentliche Ursprünge, private Ursprünge oder beides gleichzeitig zu verwenden. Sie können das CDN auch so konfigurieren, dass die Einrichtung von Standardherkunftseinstellungen beim Aktivieren übersprungen wird. Sie können diese Ursprünge immer später hinzufügen, wie in diesem Thema beschrieben.
  
In PnP PowerShell:

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Geben Sie beispielsweise den folgenden Befehl ein, um ihrer Organisation die Verwendung öffentlicher und privater Ursprünge zu ermöglichen:

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Geben Sie den folgenden Befehl ein, um ihrer Organisation die Verwendung öffentlicher und privater Ursprünge zu ermöglichen, aber das Einrichten der Standardherkunftstypen zu überspringen:

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Informationen zu den CDN, die standardmäßig bereitgestellt werden, wenn Sie die Office 365 CDN aktivieren, sowie zu den möglichen Auswirkungen des Überspringens der Einrichtung von Standardherkunftsinformationen finden Sie unter Default [CDN origins.](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)

Geben Sie den folgenden Befehl ein, um ihrer Organisation die Verwendung öffentlicher Ursprünge zu ermöglichen:

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Geben Sie den folgenden Befehl ein, um ihrer Organisation die Verwendung privater Ursprünge zu ermöglichen:

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Weitere Informationen zu diesem Cmdlet finden Sie unter [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Ändern der Liste der Dateitypen, die in das Verzeichnis Office 365 CDN (Optional)

> [!TIP]
> Wenn Sie Dateitypen mithilfe des **Cmdlets Set-PnPTenantCdnPolicy** definieren, überschreiben Sie die aktuell definierte Liste. Wenn Sie der Liste weitere Dateitypen hinzufügen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Dateitypen bereits zulässig sind, und fügen Sie sie zusammen mit Ihren neuen in die Liste ein.
  
Verwenden Sie **das Cmdlet Set-PnPTenantCdnPolicy,** um statische Dateitypen zu definieren, die von öffentlichen und privaten Ursprüngen im CDN. Standardmäßig sind allgemeine Objekttypen zulässig, z. B. CSS, .gif, .jpg und .js.

In PnP PowerShell:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Um z. B. das Hosten CDN CSS- und .png zu ermöglichen, geben Sie den Befehl ein:

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Verwenden Sie das **Cmdlet Get-PnPTenantCdnPolicies,** um zu sehen, welche Dateitypen derzeit vom CDN zulässig sind:

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Weitere Informationen zu diesen Cmdlets finden Sie unter [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) und [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Ändern der Liste der Websiteklassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten (Optional)

> [!TIP]
> Wenn Sie Websiteklassifizierungen mithilfe des **Cmdlets Set-PnPTenantCdnPolicy** ausschließen, überschreiben Sie die aktuell definierte Liste. Wenn Sie zusätzliche Websiteklassifizierungen ausschließen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Klassifizierungen bereits ausgeschlossen sind, und fügen Sie sie dann zusammen mit Ihren neuen hinzu.

Verwenden Sie **das Cmdlet Set-PnPTenantCdnPolicy,** um Websiteklassifizierungen auszuschließen, die Sie nicht über das CDN. Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.

In PnP PowerShell:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Verwenden Sie das **Cmdlet Get-PnPTenantCdnPolicies,** um zu sehen, welche Websiteklassifizierungen derzeit eingeschränkt sind:

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Die zurückgegebenen Eigenschaften sind _IncludeFileExtensions,_ _ExcludeRestrictedSiteClassifications_ und _ExcludeIfNoScriptDisabled_.

Die _IncludeFileExtensions-Eigenschaft_ enthält die Liste der Dateierweiterungen, die aus dem CDN.

> [!NOTE]
> Die Standarddateierweiterungen unterscheiden sich zwischen öffentlich und privat.

Die _ExcludeRestrictedSiteClassifications-Eigenschaft_ enthält die Websiteklassifikationen, die Sie aus dem CDN. Sie können z. B. Websites ausschließen, die als **Vertraulich** gekennzeichnet sind, damit Inhalte von Websites, auf die diese Klassifizierung angewendet wurde, nicht aus dem CDN.

Die _ExcludeIfNoScriptDisabled-Eigenschaft_ schließt Inhalte aus CDN basierend auf den NoScript-Attributeinstellungen auf _Websiteebene_ aus. Standardmäßig ist das _NoScript-Attribut_ auf **Enabled** for _Modern sites_ und **Disabled** for _Classic sites_ festgelegt. Dies hängt von ihren Mandanteneinstellungen ab.

Weitere Informationen zu diesen Cmdlets finden Sie unter [Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) und [Get-PnPTenantCdnPolicies](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies).

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Hinzufügen eines Ursprungs für Ihre Objekte

Verwenden Sie **das Cmdlet Add-PnPTenantCdnOrigin,** um einen Ursprung zu definieren. Sie können mehrere Ursprünge definieren. Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.
  
> [!IMPORTANT]
> Sie sollten niemals Ressourcen platzieren, die Benutzerinformationen enthalten oder als vertraulich für Ihre Organisation in einem öffentlichen Ursprung betrachtet werden.

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Der Wert des _Pfads_ ist der relative Pfad zu der Bibliothek oder dem Ordner, der die Objekte enthält. Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden. Origins unterstützen Platzhalter, die der URL vorausgesprungen sind. Auf diese Weise können Sie Ursprünge erstellen, die mehrere Websites umfassen. Geben Sie z. B. den folgenden Befehl ein, um alle Ressourcen im Ordner Masterpages für alle Websites als öffentlichen Ursprung innerhalb der CDN ein:

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Der Platzhaltermodifizierer * kann nur am Anfang des Pfads verwendet werden und wird mit allen **/** #A0 unter der angegebenen URL übereinstimmen.
+ Der Pfad kann auf eine Dokumentbibliothek, einen Ordner oder eine Website verweisen. Beispielsweise wird der Pfad _*/site1_ mit allen Dokumentbibliotheken unter der Website übereinstimmen.

Sie können einen Ursprung mit einem bestimmten relativen Pfad hinzufügen. Sie können keinen Ursprung mithilfe des vollständigen Pfads hinzufügen.

In diesem Beispiel wird auf einer bestimmten Website ein privater Ursprung der Websiteressourcenbibliothek hinzugefügt:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In diesem Beispiel wird der Websiteressourcenbibliothek der Websitesammlung ein privater Ursprung des Ordners _"Ordner1"_ hinzugefügt:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Wenn ein Leerzeichen im Pfad vorhanden ist, können Sie den Pfad entweder in doppelte Anführungszeichen setzen oder das Leerzeichen durch die URL-Codierung "%20" ersetzen. In den folgenden Beispielen wird der Websiteressourcenbibliothek der Websitesammlung ein privater Ursprung des Ordners _1_ hinzugefügt:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

> [!NOTE]
> Bei privaten Ursprüngen muss für Objekte, die von einem Ursprung freigegeben werden, eine Hauptversion veröffentlicht werden, bevor sie von der CDN.
  
Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Beispiel: Konfigurieren eines öffentlichen Ursprungs für Ihre Masterseiten und für Ihre Formatbibliothek für SharePoint Online

Normalerweise werden diese Ursprünge standardmäßig für Sie eingerichtet, wenn Sie die Office 365 CDN. Wenn Sie sie jedoch manuell aktivieren möchten, führen Sie die folgenden Schritte aus.
  
+ Verwenden Sie **das Cmdlet Add-PnPTenantCdnOrigin,** um die Formatbibliothek als öffentlichen Ursprung zu definieren.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Verwenden Sie **das Add-PnPTenantCdnOrigin-Cmdlet,** um die Masterseiten als öffentlichen Ursprung zu definieren.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Beispiel: Konfigurieren eines privaten Ursprungs für Ihre Websiteressourcen, Websiteseiten und Veröffentlichungsbilder für SharePoint Online

+ Verwenden Sie **das Cmdlet Add-PnPTenantCdnOrigin,** um den Ordner "Websiteressourcen" als privaten Ursprung zu definieren.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Verwenden Sie **das Cmdlet Add-PnPTenantCdnOrigin,** um den Websiteseitenordner als privaten Ursprung zu definieren.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Verwenden Sie **das Cmdlet Add-PnPTenantCdnOrigin,** um den Veröffentlichungsbildordner als privaten Ursprung zu definieren.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Beispiel: Konfigurieren eines privaten Ursprungs für eine Websitesammlung für SharePoint Online

Verwenden Sie **das Cmdlet Add-PnPTenantCdnOrigin,** um eine Websitesammlung als privaten Ursprung zu definieren. Beispiel:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).
  
Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration über das Datencenter. Möglicherweise wird eine _Ausstehende Konfigurationsnachricht_ angezeigt, die erwartet wird, wenn der SharePoint Online-Mandant eine Verbindung mit dem CDN herstellt. Dies kann bis zu 15 Minuten dauern.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Verwalten der Office 365 CDN

Nachdem Sie die CDN eingerichtet haben, können Sie Änderungen an Ihrer Konfiguration vornehmen, wenn Sie Inhalte aktualisieren oder sich Ihre Anforderungen ändern, wie in diesem Abschnitt beschrieben.
  
<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Hinzufügen, Aktualisieren oder Entfernen von Ressourcen aus dem Office 365 CDN

Nachdem Sie die Setupschritte abgeschlossen haben, können Sie neue Objekte hinzufügen und vorhandene Objekte jederzeit aktualisieren oder entfernen. Nehmen Sie einfach Ihre Änderungen an den Ressourcen im Ordner oder SharePoint, die Sie als Ursprung identifiziert haben. Wenn Sie ein neues Objekt hinzufügen, ist es über die CDN verfügbar. Wenn Sie das Objekt aktualisieren, dauert es jedoch bis zu 15 Minuten, bis die neue Kopie in der Neuen Kopie verfügbar CDN.
  
Wenn Sie den Speicherort des Ursprungs abrufen müssen, können Sie das **Cmdlet Get-PnPTenantCdnOrigin** verwenden. Informationen zur Verwendung dieses Cmdlets finden Sie unter [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin).

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Entfernen eines Ursprungs aus Office 365 CDN

Sie können den Zugriff auf einen Ordner oder eine SharePoint, die Sie als Ursprung identifiziert haben, entfernen. Verwenden Sie dazu das **Cmdlet Remove-PnPTenantCdnOrigin.**

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Informationen zur Verwendung dieses Cmdlets finden Sie unter [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Ändern eines Ursprungs im Office 365 CDN

Sie können einen von Ihnen erstellten Ursprung nicht ändern. Entfernen Sie stattdessen den Ursprung, und fügen Sie dann einen neuen hinzu. Weitere Informationen finden Sie unter So entfernen Sie einen Ursprung [aus dem Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) und Fügen Sie einen Ursprung für Ihre Objekte [hinzu.](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Deaktivieren der Office 365 CDN

Verwenden Sie **das Cmdlet Set-PnPTenantCdnEnabled,** um CDN für Ihre Organisation zu deaktivieren. Wenn sie sowohl die öffentlichen als auch die privaten Ursprünge für die CDN aktiviert haben, müssen Sie das Cmdlet zweimal ausführen, wie in den folgenden Beispielen gezeigt.
  
Geben Sie den folgenden Befehl ein, um die Verwendung öffentlicher CDN zu deaktivieren:

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Geben Sie den folgenden Befehl ein, um die Verwendung der privaten Ursprünge im CDN zu deaktivieren:

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Weitere Informationen zu diesem Cmdlet finden Sie unter [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled).

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Einrichten und Konfigurieren des Office 365 CDN mithilfe von Office 365 CLI

Für die Verfahren in diesem Abschnitt müssen Sie die cli Office 365 [installiert haben.](https://aka.ms/o365cli) Stellen Sie als Nächstes eine Verbindung Office 365 Mandanten mithilfe des [Anmeldebefehls.](https://pnp.github.io/office365-cli/cmd/login/)

Führen Sie die folgenden Schritte aus, um die CDN für das Hosten Ihrer Ressourcen in SharePoint Online mithilfe der Office 365 zu konfigurieren.

<details>
  <summary>Zum Erweitern klicken</summary>

### <a name="enable-the-office-365-cdn"></a>Aktivieren der Office 365 CDN

Sie können den Status des Office 365 CDN in Ihrem Mandanten mithilfe des Cmdlets [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) verwalten.

Um das öffentliche Office 365 CDN in Ihrem Mandanten zu aktivieren, führen Sie Folgendes aus:

```cli
spo cdn set --type Public --enabled true
```

Führen Sie zum Aktivieren Office 365 SharePoint CDN aus:

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Anzeigen des aktuellen Status des Office 365 CDN

Verwenden Sie den [Befehl spo cdn get,](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/) um zu überprüfen, ob der Office 365 CDN aktiviert oder deaktiviert ist.

Um zu überprüfen, ob das öffentliche Office 365 CDN aktiviert ist, führen Sie Folgendes aus:

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Anzeigen der Office 365 CDN Ursprünge

Um die derzeit konfigurierten öffentlichen Office 365 CDN-Ursprünge anzuzeigen, führen Sie Folgendes aus:

```cli
spo cdn origin list --type Public
```

Informationen [zu den](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) CDN, die standardmäßig bereitgestellt werden, wenn Sie die Office 365 CDN.

### <a name="add-an-office-365-cdn-origin"></a>Hinzufügen eines Office 365 CDN Ursprungs

> [!IMPORTANT]
> Sie sollten Ressourcen, die als vertraulich für Ihre Organisation gelten, niemals in einer SharePoint, die als öffentlicher Ursprung konfiguriert ist, platzieren.

Verwenden Sie den Befehl [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) zum Definieren eines CDN-Ursprungs. Sie können mehrere Ursprünge definieren. Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

Dabei `path` handelt es sich um den relativen Pfad zu dem Ordner, der die Objekte enthält. Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden.

Führen Sie Folgendes aus, um alle Objekte in den **Master page Gallery** aller Websites als öffentlichen Ursprung zu schließen:

```cli
spo cdn origin add --type Public --origin */masterpage
```

Um einen privaten Ursprung für eine bestimmte Websitesammlung zu konfigurieren, führen Sie Folgendes aus:

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> Nach dem Hinzufügen eines CDN-Ursprungs dauert es bis zu 15 Minuten, bis Sie Dateien mithilfe des CDN-Diensts abrufen können. Sie können überprüfen, ob der betreffende Ursprung bereits aktiviert wurde, indem Sie den Befehl [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) verwenden.

### <a name="remove-an-office-365-cdn-origin"></a>Entfernen eines Office 365 CDN Ursprungs

Verwenden Sie den Befehl [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/), um einen CDN-Ursprung für den angegebenen CDN-Typ zu entfernen.

Führen Sie zum Entfernen eines öffentlichen Ursprungs aus der CDN aus:

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> Das Entfernen CDN Ursprungs wirkt sich nicht auf die Dateien aus, die in einer Dokumentbibliothek gespeichert sind, die mit diesem Ursprung übereinstimmen. Wenn auf diese Objekte mithilfe ihrer SharePoint-URL verwiesen wurde, SharePoint automatisch zur ursprünglichen URL zurück, die auf die Dokumentbibliothek verweist. Wenn jedoch auf Ressourcen mithilfe einer öffentlichen CDN-URL verwiesen wurde, wird der Link durch Entfernen des Ursprungs nicht mehr verwendet, und Sie müssen sie manuell ändern.

### <a name="modify-an-office-365-cdn-origin"></a>Ändern eines Office 365 CDN Ursprungs

Es ist nicht möglich, einen vorhandenen CDN-Ursprung zu ändern. Stattdessen sollten Sie den zuvor definierten CDN-Ursprung mit dem Befehl `spo cdn origin remove` entfernen und mit dem Befehl `spo cdn origin add` einen neuen hinzufügen.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Ändern der Dateitypen, die in die Datei enthalten Office 365 CDN

Standardmäßig sind die folgenden Dateitypen im CDN enthalten: _CSS, .eot, .gif, .ico, JPEG, .jpg, .js, .map, .png, SVG, TTF, .woff und .woff2_. Wenn Sie weitere Dateitypen in das CDN einbeziehen müssen, können Sie die CDN-Konfiguration mit dem Befehl [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) ändern.

> [!NOTE]
> Durch das Ändern der Liste von Dateitypen überschreiben Sie die aktuell definierte Liste. Wenn Sie weitere Dateitypen einbeziehen möchten, verwenden Sie zunächst den Befehl [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/), um herauszufinden, welche Dateitypen derzeit konfiguriert sind.

Führen Sie zum Hinzufügen des _Dateityps JSON_ zur Standardliste der Dateitypen im öffentlichen CDN aus:

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Ändern der Liste von Websiteklassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten

Verwenden Sie den Befehl [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) zum Ausschließen von Websiteklassifizierungen, die Sie nicht über das CDN zur Verfügung stellen möchten. Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.

> [!NOTE]
> Durch das Ändern der Liste der ausgeschlossenen Websiteklassifizierungen überschreiben Sie die aktuell definierte Liste. Wenn Sie zusätzliche Klassifizierungen ausschließen möchten, verwenden Sie zunächst den Befehl [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/), um herauszufinden, welche Klassifizierungen derzeit konfiguriert sind.

Führen Sie zum Ausschließen von Websites, die _als HBI_ klassifiziert sind, CDN aus

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Deaktivieren der Office 365 CDN

Um das Office 365 CDN zu deaktivieren, verwenden Sie den Befehl `spo cdn set`. Beispiel:

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Verwenden ihrer CDN Ressourcen

Nachdem Sie die CDN und konfigurierten Ursprünge und Richtlinien aktiviert haben, können Sie mit der Verwendung ihrer CDN beginnen.

Dieser Abschnitt hilft Ihnen, die Verwendung von CDN-URLs in Ihren SharePoint-Seiten und Inhalten zu verstehen, sodass SharePoint Anforderungen für Objekte öffentlicher und privater Herkunft an die CDN.

+ [Aktualisieren von Links zu CDN Ressourcen](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Verwenden von Ressourcen in öffentlichen Ursprüngen](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Verwenden von Ressourcen in privaten Ursprüngen](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Informationen zur Verwendung der CDN zum Hosten clientseitiger Webparts finden Sie im Thema [Host your client-side web part from Office 365 CDN (Hello World part 4).](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)

> [!NOTE]
> Wenn Sie den _Ordner ClientSideAssets_ zur Liste der privaten CDN hinzufügen, können CDN gehosteten benutzerdefinierten Webparts nicht gerendert werden.  Von SPFX-Webparts verwendete Dateien können nur die öffentliche CDN und der Ordner ClientSideAssets ist ein Standardherkunft für öffentliche CDN. 

### <a name="updating-links-to-cdn-assets"></a>Aktualisieren von Links zu CDN Ressourcen

Um Objekte zu verwenden, die Sie einem Ursprung hinzugefügt haben, aktualisieren Sie einfach Links zur ursprünglichen Datei mit dem Pfad zur Datei im Ursprung.

+ Bearbeiten Sie die Seite oder den Inhalt, die Links zu Ressourcen enthält, die Sie einem Ursprung hinzugefügt haben. Sie können auch eine von mehreren Methoden verwenden, um Links in einer Eingabewebsite oder Websitesammlung global zu suchen und zu ersetzen, wenn Sie den Link zu einem bestimmten Objekt überall dort aktualisieren möchten, wo er angezeigt wird.
+ Ersetzen Sie für jeden Link zu einem Objekt in einem Ursprung den Pfad durch den Pfad zur Datei im CDN. Sie können relative Pfade verwenden.
+ Speichern Sie die Seite oder den Inhalt.

Betrachten Sie beispielsweise das Bild _/site/SiteAssets/images/image.png_, das Sie in den Dokumentbibliotheksordner _/site/CDN_origins/public/_ kopiert haben. Um das CDN zu verwenden, ersetzen Sie den ursprünglichen Pfad zum Speicherort der Bilddatei durch den Pfad zum Ursprung, um die neue URL _/site/CDN_origins/public/image.pngzu erstellen._

Wenn Sie die vollständige URL zum Objekt anstelle eines relativen Pfads verwenden möchten, erstellen Sie den Link wie so:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> Im Allgemeinen sollten Sie URLs nicht direkt für Ressourcen in der CDN. Sie können jedoch bei Bedarf manuell URLs für Objekte in öffentlichen Ursprüngen erstellen. Weitere Informationen finden Sie unter [Hardcoding CDN URLs for public assets](use-microsoft-365-cdn-with-spo.md).

Informationen dazu, wie Sie überprüfen, ob Ressourcen aus dem CDN bedient werden, finden Sie unter How do I confirm that assets are served by [the CDN?](use-microsoft-365-cdn-with-spo.md#CDNConfirm) in [Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).

### <a name="using-assets-in-public-origins"></a>Verwenden von Ressourcen in öffentlichen Ursprüngen

Das Veröffentlichungsfeature **in** SharePoint Online schreibt URLs von Ressourcen, die in öffentlichen Ursprüngen gespeichert sind, automatisch in ihre CDN-Entsprechungen um, sodass Ressourcen vom CDN-Dienst statt von SharePoint.

Wenn Sich Ihr Ursprung in einer Website befindet, für die das Veröffentlichungsfeature aktiviert ist, und die Ressourcen, die Sie auf die CDN ausladen möchten, in einer der folgenden Kategorien enthalten sind, schreibt SharePoint urLs für Objekte im Ursprung automatisch um, vorausgesetzt, die Ressource wurde nicht durch eine CDN-Richtlinie ausgeschlossen.

Es folgt eine Übersicht über die Links, die automatisch vom SharePoint-Veröffentlichungsfeature umgeschrieben werden:

+ IMG/LINK/CSS-URLs in den HTML-Antworten klassischer Veröffentlichungsseiten
  + Dies schließt von Autoren im HTML-Inhalt einer Seite hinzugefügte Bilder ein.
+ Bild-URLs des Webparts „Bildbibliothek-Bildschirmpräsentation“
+ Bildfelder in Ergebnissen der SPList-REST-API (RenderListDataAsStream)
  + Verwenden der neuen _Eigenschaft ImageFieldsToTryRewriteToCdnUrls_ zum Bereitstellen einer durch Kommas getrennten Liste von Feldern
  + Unterstützt Hyperlinkfelder und PublishingImage-Felder
+ SharePoint Bildversionen

Das folgende Diagramm veranschaulicht den Workflow, wenn SharePoint eine Anforderung für eine Seite mit Ressourcen von einem öffentlichen Ursprung empfängt.

![Workflowdiagramm: Abrufen Office 365 CDN Objekte von einem öffentlichen Ursprung](../media/O365-CDN/o365-cdn-public-steps-transparent.svg "Workflow: Abrufen Office 365 CDN Objekte von einem öffentlichen Ursprung")

> [!TIP]
> Wenn Sie die automatische Umschreibung für bestimmte URLs auf einer Seite deaktivieren möchten, können Sie die Seite überprüfen und den Abfragezeichenfolgenparameter **hinzufügen? NoAutoReWrites=true** bis zum Ende jedes Links, den Sie deaktivieren möchten.

#### <a name="constructing-cdn-urls-for-public-assets"></a>Erstellen CDN URLs für öffentliche Objekte

Wenn  das Veröffentlichungsfeature für einen öffentlichen Ursprung nicht aktiviert ist oder das Objekt nicht einer der Linktypen ist, die vom Feature zum automatischen Umschreiben des CDN-Diensts unterstützt werden, können Sie URLs manuell am CDN-Speicherort der Objekte erstellen und diese URLs in Ihren Inhalten verwenden.

> [!NOTE]
> Sie können keine CDN URLs für Objekte mit privatem Ursprung hartcodieren oder erstellen, da das erforderliche Zugriffstoken, das den letzten Abschnitt der URL bildet, zum Zeitpunkt der Ressourcenerreichung generiert wird. Sie können die URL für öffentliche CDN und die URL sollte nicht hart codiert werden, da sie geändert werden kann.

Bei öffentlichen CDN sieht das URL-Format wie folgt aus:

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Ersetzen **Sie TenantHostName** durch Ihren Mandantennamen. Beispiel:

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> Die Seitenkontexteigenschaft sollte zum Erstellen des Präfixes anstelle von Hartcodierung " " verwendet https://publiccdn.sharepointonline.com werden. Die URL kann geändert werden und sollte nicht hart codiert werden. Wenn Sie Anzeigevorlagen mit klassischem SharePoint Online verwenden, können Sie die Eigenschaft "window._spPageContextInfo.publicCdnBaseUrl" in Ihrer Anzeigevorlage für das Präfix der URL verwenden. Wenn Sie SPFx webparts für moderne und klassische SharePoint können Sie die Eigenschaft "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" verwenden. Dadurch wird das Präfix so angegeben, dass die Implementierung mit dem Präfix aktualisiert wird, wenn es geändert wird. Als Beispiel für SPFx kann die URL mithilfe der Eigenschaft "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL für das Element" erstellt werden. Weitere Informationen finden Sie unter Verwenden [CDN im clientseitigen Code,](https://youtu.be/IH1RbQlbhIA) der Teil der Leistungsreihe [1 der Staffel 1 ist.](https://aka.ms/sppnp-perfvideos)


### <a name="using-assets-in-private-origins"></a>Verwenden von Ressourcen in privaten Ursprüngen

Für die Verwendung von Ressourcen in privaten Ursprüngen ist keine zusätzliche Konfiguration erforderlich. SharePoint Online schreibt URLs für Objekte privater Herkunft automatisch um, sodass Anforderungen für diese Objekte immer von der CDN. Sie können URLs nicht manuell erstellen, um CDN objekte privater Ursprünge zu erstellen, da diese URLs Token enthalten, die von SharePoint Online automatisch generiert werden müssen, wenn die Ressource angefordert wird.

Der Zugriff auf Objekte privater Ursprünge wird durch dynamisch generierte Token geschützt, die auf den Benutzerberechtigungen für den Ursprung basieren, mit den in den folgenden Abschnitten beschriebenen Einschränkungen. Benutzer müssen mindestens **Lesezugriff auf** die Ursprünge haben, damit CDN Inhalte rendern können.

Das folgende Diagramm veranschaulicht den Workflow, wenn SharePoint eine Anforderung für eine Seite mit Ressourcen von privatem Ursprung empfängt.

![Workflowdiagramm: Abrufen Office 365 CDN Objekte von einem privaten Ursprung](../media/O365-CDN/o365-cdn-private-steps-transparent.svg "Workflow: Abrufen Office 365 CDN Objekte von einem privaten Ursprung")

#### <a name="token-based-authorization-in-private-origins"></a>Tokenbasierte Autorisierung in privaten Ursprüngen

Der Zugriff auf Objekte privater Office 365 CDN wird durch Token gewährt, die von SharePoint Online generiert werden. Benutzern, die bereits über die Berechtigung zum Zugriff auf den vom Ursprung festgelegten Ordner oder die Bibliothek verfügen, werden automatisch Token gewährt, mit denen der Benutzer basierend auf seiner Berechtigungsstufe auf die Datei zugreifen kann. Diese Zugriffstoken sind 30 bis 90 Minuten gültig, nachdem sie generiert wurden, um Tokenwiedergabeangriffe zu verhindern.

Nachdem das Zugriffstoken generiert wurde, gibt SharePoint Online einen benutzerdefinierten  URI an den Client zurück, der zwei Autorisierungsparameter (Edgeautorisierungstoken) und Einat  (Ursprungsautorisierungstoken) enthält. Die Struktur der einzelnen Token _< "Ablaufzeit" im Epoch-Zeitformat'>__<'secure signature'>_. Beispiel:

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Jeder, der im Besitz des Tokens ist, kann auf die Ressource in der CDN. URLs, die diese Zugriffstoken enthalten, werden jedoch nur über HTTPS freigegeben. Wenn die URL also nicht explizit von einem Endbenutzer freigegeben wird, bevor das Token abläuft, ist der Zugriff auf das Objekt für nicht autorisierte Benutzer nicht möglich.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Berechtigungen auf Elementebene werden für Objekte in privaten Ursprüngen nicht unterstützt

Beachten Sie, dass SharePoint Online keine Berechtigungen auf Elementebene für Objekte privater Herkunft unterstützt. Für eine Datei, die sich unter befindet, haben Benutzer beispielsweise unter den folgenden Bedingungen effektiven Zugriff auf `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` die Datei:

|Benutzer  |Berechtigungen  |Effektiver Zugriff  |
|---------|---------|---------|
|Benutzer 1     |Zugriff auf Ordner1         |Kann über image1.jpg auf CDN         |
|Benutzer 2     |Hat keinen Zugriff auf Ordner1         |Zugriff auf image1.jpg aus der CDN         |
|Benutzer 3     |Hat keinen Zugriff auf Ordner1, erhält jedoch explizite Berechtigung für den Zugriff auf image1.jpg in SharePoint Online         |Kann direkt über image1.jpg online SharePoint auf das Objekt zugreifen, jedoch nicht über CDN         |
|Benutzer 4     |Hat Zugriff auf Ordner1, wurde jedoch explizit der Zugriff auf image1.jpg in SharePoint Online verweigert         |Der Zugriff auf das Objekt SharePoint Online nicht möglich, kann jedoch über das CDN auf das Objekt zugreifen, obwohl der Zugriff auf die Datei in SharePoint Online verweigert wurde         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Problembehandlung Office 365 CDN

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Wie kann ich bestätigen, dass die Ressourcen von der CDN?

Nachdem Sie einer Seite Links zu CDN-Ressourcen hinzugefügt haben, können Sie bestätigen, dass das Objekt von der CDN bedient wird, indem Sie zur Seite browsen, mit der rechten Maustaste auf das Bild klicken, sobald es gerendert wurde, und die Bild-URL überprüfen.

Sie können auch die Entwicklertools Ihres Browsers verwenden, um die URL für jedes Objekt auf einer Seite anzuzeigen, oder ein Drittanbieter-Netzwerk-Ablaufverfolgungstool verwenden.

> [!NOTE]
> Wenn Sie ein Netzwerktool wie Fiddler verwenden, um Ihre Objekte außerhalb des Renderns der Ressource von einer SharePoint-Seite zu testen, müssen Sie manuell den Refererheader "Referer: " zur GET-Anforderung hinzufügen, wobei die URL die `https://yourdomain.sharepoint.com` Stamm-URL Ihres SharePoint Online-Mandanten ist.

Sie können die CDN urLs nicht direkt in einem Webbrowser testen, da sie über einen Referer von SharePoint Online verfügen müssen. Wenn Sie jedoch die CDN-Objekt-URL zu einer SharePoint-Seite hinzufügen und dann die Seite in einem Browser öffnen, wird das CDN-Objekt auf der Seite gerendert.

Weitere Informationen zur Verwendung der Entwicklertools im Microsoft Edge finden Sie [unter Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).

Ein kurzes Video, das im SharePoint Developer [Patterns and Practices YouTube-Kanal](https://aka.ms/sppnp-videos) gehostet wird und zeigt, wie Sie überprüfen können, ob Ihre CDN funktioniert, finden Sie unter [Verifying your CDN usage](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)and ensuring optimal network connectivity .

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Warum sind Objekte mit einem neuen Ursprung nicht verfügbar?
Ressourcen mit neuen Ursprüngen stehen nicht sofort zur Verwendung zur Verfügung, da es zeitaufhörend dauert, bis die Registrierung über das CDN und die Objekte aus dem Ursprung in den speicher hochgeladen CDN werden. Die Zeit, die erforderlich ist, damit Ressourcen im CDN verfügbar sind, hängt von der Größe der Objekte und der Dateigröße ab.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>Mein clientseitiges Webteil oder meine SharePoint-Framework funktioniert nicht

Wenn Sie die Office 365 CDN öffentlichen Ursprüngen aktivieren, erstellt der CDN automatisch die folgenden Standardherkunftsherkunft:

+ */MASTERPAGE
+ */STYLE LIBRARY
+ */CLIENTSIDEASSETS

Wenn der */clientsideassets-Ursprung fehlt, SharePoint-Framework lösungen fehl, und es werden keine Warnmeldungen oder Fehlermeldungen generiert. Dieser Ursprung fehlt möglicherweise, weil CDN _-NoDefaultOrigins-Parameter_ auf **$true** festgelegt wurde oder weil der Ursprung manuell gelöscht wurde.

Mit dem folgenden PowerShell-Befehl können Sie überprüfen, welche Ursprünge vorhanden sind:

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

Sie können dies auch mit der Office 365 CLI überprüfen:

```cli
spo cdn origin list
```

So fügen Sie den Ursprung in PowerShell hinzu:

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

So fügen Sie den Ursprung in der Office 365 hinzu:

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Welche PowerShell-Module und CLI-Shells muss ich für die Office 365 CDN?

Sie können entweder das Office 365 CDN PowerShell-Modul SharePoint **Der** Onlineverwaltungsshell oder die Office 365 **CLI verwenden.**

+ [Erste Schritte mit der SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?view=sharepoint-ps)
+ [Installieren von Office 365 CLI](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>Siehe auch

[Netzwerke für die Inhaltsübermittlung](./content-delivery-networks.md)

[Netzwerkplanung und Leistungsoptimierung für Office 365](./network-planning-and-performance.md)

[SharePoint Leistungsserie – Office 365 CDN Videoreihe](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)