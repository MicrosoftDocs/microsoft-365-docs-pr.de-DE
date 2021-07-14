---
title: Verwenden von Office 365 Content Delivery Network (CDN) mit SharePoint Online
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/13/2021
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
description: Erfahren Sie, wie Sie die Office 365 Content Delivery Network (CDN) verwenden, um die Bereitstellung Ihrer SharePoint Online-Ressourcen zu beschleunigen.
ms.openlocfilehash: 24b86f059e5a59d3b6dadf989bef0ab38ad8e010
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/14/2021
ms.locfileid: "53419568"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online

Sie können statische Objekte im Office 365-Netzwerk für die Inhaltsübermittlung (CDN) hosten, um eine bessere Leistung für Ihre SharePoint Online-Seiten zu ermöglichen. Das Office 365-Netzwerk für die Inhaltsübermittlung verbessert die Leistung, indem statische Objekte näher an den Browsern zwischengespeichert werden, die diese anfordern, wodurch Downloads beschleunigt werden und die Latenz reduziert wird. Außerdem verwendet das Office 365 CDN das [HTTP/2-Protokoll](https://en.wikipedia.org/wiki/HTTP/2) für eine verbesserte Komprimierung und HTTP-Pipelining. Das Office 365-Netzwerk für die Inhaltsübermittlung ist in Ihrem SharePoint Online-Abonnement enthalten.

> [!NOTE]
> Die Office 365 CDN ist nur für Mandanten in der **Produktionscloud** (weltweit) verfügbar. Mandanten in den Clouds der US-Regierung, China und Deutschland unterstützen derzeit nicht die Office 365 CDN.

Das Office 365-Netzwerk für die Inhaltsübermittlung besteht aus mehreren CDNs, über die Sie statische Objekte an mehreren Speicherorten hosten können, oder aus _Ursprüngen_, die aus globalen Hochgeschwindigkeitsnetzwerken bedient werden. In Abhängigkeit von der Art der Inhalte, die Sie im Office 365-Netzwerk für die Inhaltsübermittlung hosten möchten, können Sie **öffentliche** Ursprünge, **private** Ursprünge oder beides hinzufügen. Weitere Informationen zum Unterschied zwischen öffentlichen und privaten Ursprüngen finden Sie unter ["Auswählen, ob jeder Ursprung öffentlich oder privat sein soll".](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

![Office 365 CDN konzeptionelles Diagramm](../media/O365-CDN/o365-cdn-flow-transparent.png "Office 365 CDN konzeptionelles Diagramm")

Wenn Sie bereits mit der Funktionsweise von CDNs vertraut sind, müssen Sie nur einige Schritte ausführen, um die Office 365 CDN für Ihren Mandanten zu aktivieren. In diesem Thema wird beschrieben, wie. Lesen Sie weiter, um Informationen zu den ersten Schritten beim Hosten ihrer statischen Objekte zu erhalten.

> [!TIP]
> Es gibt andere von Microsoft gehostete CDNs, die mit Office 365 für spezielle Verwendungsszenarien verwendet werden können, aber in diesem Thema nicht behandelt werden, da sie nicht in den Bereich der Office 365 CDN fallen. Weitere Informationen finden Sie unter [Andere Microsoft CDNs.](content-delivery-networks.md#other-microsoft-cdns)

 **Kehren Sie zur [Netzwerkplanung und Leistungsoptimierung für Office 365](./network-planning-and-performance.md)zurück.**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>Übersicht über die Arbeit mit den Office 365 CDN in SharePoint Online

Führen Sie die folgenden grundlegenden Schritte aus, um die Office 365 CDN für Ihre Organisation einzurichten:

+ [Planen der Bereitstellung der Office 365 CDN](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [Bestimmen Sie, welche statischen Objekte auf dem CDN gehostet werden sollen.](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Bestimmen Sie, wo Ihre Objekte gespeichert werden sollen.](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets) Dieser Speicherort kann eine SharePoint Website, Bibliothek oder Ordner sein und wird als _Ursprung_ bezeichnet.
  + [Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) Sie können mehrere Ursprünge von öffentlichen und privaten Typen hinzufügen.

+ Einrichten und Konfigurieren der CDN mithilfe von PowerShell oder der SharePoint Online CLI

  + [Einrichten und Konfigurieren der CDN mithilfe der SharePoint Online-Verwaltungsshell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [Einrichten und Konfigurieren der CDN mithilfe von PnP PowerShell](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [Einrichten und Konfigurieren der CDN mithilfe der Office 365 CLI](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  Wenn Sie diesen Schritt abschließen, haben Sie Folgendes:

  + Die CDN für Ihre Organisation aktiviert.
  + Ihre Ursprünge hinzugefügt, wobei jeder Ursprung als öffentlich oder privat identifiziert wird.

Sobald Sie mit der Einrichtung fertig sind, können Sie die Office 365 CDN im Laufe der Zeit [verwalten,](use-microsoft-365-cdn-with-spo.md#CDNManage) indem Sie:

+ Hinzufügen, Aktualisieren und Entfernen von Ressourcen
+ Hinzufügen und Entfernen von Ursprüngen
+ Konfigurieren CDN Richtlinien
+ Deaktivieren sie ggf. die CDN

Weitere Informationen zum Zugriff auf Ihre CDN Ressourcen von öffentlichen und privaten Ursprüngen finden Sie unter ["Verwenden Ihrer CDN-Ressourcen".](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets)

Anleitungen zum Beheben häufig auftretender Probleme finden Sie unter Problembehandlung der [Office 365 CDN.](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>Planen der Bereitstellung der Office 365 CDN

Bevor Sie die Office 365 CDN für Ihren Office 365 Mandanten bereitstellen, sollten Sie die folgenden Faktoren im Rahmen Ihres Planungsprozesses berücksichtigen.

  + [Bestimmen Sie, welche statischen Objekte auf dem CDN gehostet werden sollen.](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [Bestimmen, wo Ihre Ressourcen gespeichert werden sollen](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll.](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>Bestimmen Sie, welche statischen Objekte auf dem CDN gehostet werden sollen.

Im Allgemeinen sind CDNs am effektivsten für das Hosten _statischer Objekte_ oder Objekte, die sich nicht sehr oft ändern. Eine gute Faustregel besteht darin, Dateien zu identifizieren, die einige oder alle dieser Bedingungen erfüllen:

+ Statische Dateien, die in eine Seite eingebettet sind (z. B. Skripts und Bilder), die erhebliche inkrementelle Auswirkungen auf die Seitenladezeiten haben können
+ Große Dateien wie ausführbare Dateien und Installationsdateien
+ Ressourcenbibliotheken, die clientseitigen Code unterstützen

Beispielsweise können kleine Dateien, die wiederholt angefordert werden, z. B. Websiteimages und Skripts, die Leistung beim Rendern von Websites erheblich verbessern und die Last auf Ihren SharePoint Onlinewebsites inkrementell reduzieren, wenn Sie sie einem CDN Ursprung hinzufügen. Größere Dateien, z. B. ausführbare Installationsdateien, können aus dem CDN heruntergeladen werden, was eine positive Auswirkung auf die Leistung und eine nachfolgende Reduzierung der Auslastung Ihrer SharePoint Onlinewebsite zur Folge hat, auch wenn nicht so häufig auf sie zugegriffen wird.

Die Leistungsverbesserung auf Dateibasis hängt von vielen Faktoren ab, einschließlich der Nähe des Clients zum nächstgelegenen CDN Endpunkt, vorübergehenden Bedingungen im lokalen Netzwerk usw. Viele statische Dateien sind recht klein und können in weniger als einer Sekunde von Office 365 heruntergeladen werden. Eine Webseite kann jedoch viele eingebettete Dateien mit einer kumulativen Downloadzeit von mehreren Sekunden enthalten. Die Bereitstellung dieser Dateien aus dem CDN kann die Gesamtladezeit der Seite erheblich reduzieren. Sehen Sie sich [an, welche Leistungsvorteile ein CDN bietet?](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide) Ein Beispiel.

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>Bestimmen, wo Ihre Ressourcen gespeichert werden sollen

Die CDN ruft Ihre Objekte von einem Speicherort ab, der als Ursprung bezeichnet _wird._ Ein Ursprung kann eine SharePoint Website, Eine Dokumentbibliothek oder ein Ordner sein, auf die über eine URL zugegriffen werden kann. Sie haben große Flexibilität, wenn Sie Ursprünge für Ihre Organisation angeben. Sie können z. B. mehrere Ursprünge oder einen einzelnen Ursprung angeben, in dem Sie alle CDN Ressourcen ablegen möchten. Sie können sowohl öffentliche als auch private Ursprünge für Ihre Organisation auswählen. Die meisten Organisationen entscheiden sich dafür, eine Kombination der beiden zu implementieren.

Sie können einen neuen Container für Ihre Ursprünge erstellen, z. B. Ordner oder Dokumentbibliotheken, und Dateien hinzufügen, die Sie über die CDN verfügbar machen möchten. Dies ist ein guter Ansatz, wenn Sie über einen bestimmten Satz von Ressourcen verfügen, die über die CDN verfügbar sein sollen, und den Satz von CDN Ressourcen auf diese Dateien im Container beschränken möchten.

Sie können auch eine vorhandene Websitesammlung, Website, Bibliothek oder einen vorhandenen Ordner als Ursprung konfigurieren, wodurch alle berechtigten Ressourcen im Container über die CDN zur Verfügung gestellt werden. Bevor Sie einen vorhandenen Container als Ursprung hinzufügen, müssen Sie sicherstellen, dass Sie dessen Inhalte und Berechtigungen kennen, damit Sie Objekte nicht versehentlich für anonymen Zugriff oder nicht autorisierte Benutzer verfügbar machen.

Sie können _CDN Richtlinien_ definieren, um Inhalte in Ihren Ursprüngen von der CDN auszuschließen. CDN Richtlinien ressourcen in öffentlichen oder privaten Ursprüngen durch Attribute wie _Dateityp_ und _Websiteklassifizierung_ ausschließen und auf alle Ursprünge des CdnType (privat oder öffentlich) angewendet werden, die Sie in der Richtlinie angeben. Wenn Sie z. B. einen privaten Ursprung hinzufügen, der aus einer Website besteht, die mehrere Unterwebsites enthält, können Sie eine Richtlinie definieren, um Als **vertraulich** markierte Websites auszuschließen, damit Inhalte von Websites mit dieser Klassifizierung nicht vom CDN bereitgestellt werden. Die Richtlinie gilt für Inhalte _aller_ privaten Ursprünge, die Sie dem CDN hinzugefügt haben.

Bedenken Sie, dass je größer die Anzahl der Ursprünge ist, desto größer ist die Auswirkung auf die Zeit, die der CDN Dienst für die Verarbeitung von Anforderungen benötigt. Es wird empfohlen, die Anzahl der Ursprünge so weit wie möglich zu begrenzen.

<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>Wählen Sie aus, ob jeder Ursprung öffentlich oder privat sein soll.

Wenn Sie einen Ursprung identifizieren, geben Sie an, ob er _öffentlich_ oder _privat_ sein soll. Der Zugriff auf CDN Ressourcen in öffentlichen Ursprüngen ist anonym, und CDN Inhalte in privaten Ursprüngen werden durch dynamisch generierte Token gesichert, um die Sicherheit zu erhöhen. Unabhängig davon, welche Option Sie auswählen, erledigt Microsoft die gesamte Arbeit, wenn es um die Verwaltung der CDN selbst geht. Außerdem können Sie Ihre Meinung später ändern, nachdem Sie die CDN eingerichtet und Ihre Ursprünge identifiziert haben.

Sowohl öffentliche als auch private Optionen bieten ähnliche Leistungsvorteile, weisen jedoch jeweils eindeutige Attribute und Vorteile auf.

**Öffentliche** Ursprünge innerhalb der Office 365 CDN sind anonym zugänglich, und auf gehostete Objekte kann von jedem benutzer zugegriffen werden, der über die URL zu dem Objekt verfügt. Da der Zugriff auf Inhalte in öffentlichen Ursprüngen anonym ist, sollten Sie diese nur zum Zwischenspeichern von nicht vertraulichen generischen Inhalten verwenden, z. B. JavaScript-Dateien, Skripts, Symbole oder Bilder.

**Private** Ursprünge innerhalb der Office 365 CDN bieten privaten Zugriff auf Benutzerinhalte wie SharePoint Online-Dokumentbibliotheken, Websites und proprietäre Bilder. Der Zugriff auf Inhalte in privaten Ursprüngen wird durch dynamisch generierte Token gesichert, sodass nur Benutzer mit Berechtigungen für die ursprüngliche Dokumentbibliothek oder den ursprünglichen Speicherort darauf zugreifen können. Private Ursprünge im Office 365 CDN können nur für SharePoint Onlineinhalte verwendet werden, und Sie können nur über die Umleitung von Ihrem SharePoint Onlinemandanten auf Ressourcen in privaten Ursprüngen zugreifen.

Weitere Informationen dazu, wie CDN Zugriff auf Objekte in einem privaten Ursprung funktioniert, finden Sie unter [Verwenden von Ressourcen in privaten Ursprüngen.](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>Attribute und Vorteile des Hostings von Ressourcen in öffentlichen Ursprüngen

+ Objekte, die an einem öffentlichen Ursprung verfügbar gemacht werden, sind für jeden Benutzer anonym zugänglich.
    > [!IMPORTANT]
    > Sie sollten niemals Ressourcen, die Benutzerinformationen enthalten oder für Ihre Organisation vertraulich sind, an einem öffentlichen Ursprung platzieren.

+ Wenn Sie ein Objekt aus einem öffentlichen Ursprung entfernen, ist es unter Umständen bis zu 30 Tage lang weiterhin über den Cache verfügbar. Links zu dem Objekt im CDN werden jedoch innerhalb von 15 Minuten ungültig.

+ Wenn Sie Stylesheets (CSS-Dateien) an einem öffentlichen Ursprung hosten, können Sie im Code relative Pfade und URIs verwenden. Dies bedeutet, dass Sie auf den Speicherort von Hintergrundbildern und anderen Objekten relativ zum Speicherort des Objekts, das sie aufruft, verweisen können.

+ Während Sie die URL eines öffentlichen Ursprungs erstellen können, sollten Sie mit Vorsicht vorgehen und sicherstellen, dass Sie die Seitenkontexteigenschaft verwenden und die Anleitung dazu befolgen. Der Grund hierfür ist folgender: Wenn der Zugriff auf das CDN nicht mehr verfügbar ist, wird die URL nicht automatisch auf Ihre Organisation in SharePoint Online aufgelöst, was zu fehlerhaften Links und anderen Fehlern führen kann. Die URL kann auch geändert werden, weshalb sie nicht nur hartcodiert werden sollte, um ihren aktuellen Wert anzugeben.

+ Die Standarddateitypen, die für öffentliche Ursprünge enthalten sind, sind CSS, EOT, .gif, ICO, JPEG, .jpg, .js, MAP, .png, SVG, TTF, WOFF und WOFF2. Sie können zusätzliche Dateitypen angeben.

+ Sie können eine Richtlinie so konfigurieren, dass Ressourcen ausgeschlossen werden, die durch von Ihnen angegebene Websiteklassifizierungen identifiziert wurden. Beispielsweise können Sie alle Objekte ausschließen, die als „vertraulich“ oder „eingeschränkt“ gekennzeichnet sind, auch wenn sie einen zulässigen Dateityp haben und sich an einem öffentlichen Ursprung befinden.

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>Attribute und Vorteile des Hostings von Ressourcen in privaten Ursprüngen

+ Private Ursprünge können nur für SharePoint Onlineressourcen verwendet werden.

+ Benutzer können nur von einem privaten Ursprung aus auf die Objekte zugreifen, wenn sie über Berechtigungen für den Zugriff auf den Container verfügen. Der anonyme Zugriff auf diese Objekte wird verhindert.

+ Auf Objekte in privaten Ursprüngen muss vom SharePoint Onlinemandanten verwiesen werden. Der direkte Zugriff auf private CDN Ressourcen funktioniert nicht.

+ Wenn Sie eine Ressource aus dem privaten Ursprung entfernen, ist die Ressource möglicherweise bis zu einer Stunde lang aus dem Cache verfügbar. Links zu der Ressource im CDN werden jedoch innerhalb von 15 Minuten nach dem Entfernen des Objekts ungültig.

+ Die standardmäßigen Dateitypen, die für private Ursprünge eingeschlossen werden, sind GIF, ICO, JPEG, JPG, JS und PNG. Sie können zusätzliche Dateitypen angeben.

+ Genau wie bei öffentlichen Ursprüngen können Sie eine Richtlinie so konfigurieren, dass Ressourcen ausgeschlossen werden, die durch von Ihnen angegebene Websiteklassifizierungen identifiziert wurden, auch wenn Sie Platzhalter verwenden, um alle Ressourcen in einem Ordner oder einer Dokumentbibliothek einzuschließen.

Weitere Informationen dazu, warum Sie die Office 365 CDN, allgemeine CDN Konzepte und andere Microsoft CDNs verwenden, die Sie mit Ihrem Office 365 Mandanten verwenden können, finden Sie unter [Content Delivery Networks](content-delivery-networks.md).

### <a name="default-cdn-origins"></a>Standardmäßige CDN Ursprünge

Wenn Sie nichts anderes angeben, richten Office 365 einige Standardursprungseinträge für Sie ein, wenn Sie die Office 365 CDN aktivieren. Wenn Sie sich zunächst dafür entscheiden, sie nicht bereitzustellen, können Sie diese Ursprünge nach Abschluss der Einrichtung hinzufügen. Wenn Sie nicht die Folgen des Überspringens der Einrichtung von Standardursprungen verstehen und einen bestimmten Grund dafür haben, sollten Sie zulassen, dass sie erstellt werden, wenn Sie die CDN aktivieren.

Standardmäßige private CDN Ursprünge:

+ \*/userphoto.aspx
+ \*/siteassets

Standardmäßige öffentliche CDN Ursprünge:

+ \*/masterpage
+ \*/style library
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ is a default public origin that was added to the Office 365 CDN service in December 2017. Dieser Ursprung muss vorhanden sein, damit SharePoint-Framework Lösungen im CDN funktionieren. Wenn Sie die Office 365 CDN vor Dezember 2017 aktiviert haben oder wenn Sie die Einrichtung der Standardursprungs beim Aktivieren der CDN übersprungen haben, können Sie diesen Ursprung manuell hinzufügen. Weitere Informationen finden Sie unter ["Mein clientseitiges Webpart" oder SharePoint-Framework Lösung nicht funktioniert.](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>Einrichten und Konfigurieren der Office 365 CDN mithilfe der SharePoint Online-Verwaltungsshell

Für die Verfahren in diesem Abschnitt müssen Sie die SharePoint Online-Verwaltungsshell verwenden, um eine Verbindung mit SharePoint Online herzustellen. Weitere Anweisungen finden Sie unter [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).

Führen Sie diese Schritte aus, um die CDN zum Hosten Ihrer Ressourcen in SharePoint Online mithilfe der SharePoint Online-Verwaltungsshell einzurichten und zu konfigurieren.

<details>
  <summary>Zum Erweitern klicken</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Ermöglichen Sie Ihrer Organisation die Verwendung der Office 365 CDN

Bevor Sie Änderungen an den Mandanteneinstellungen CDN vornehmen, sollten Sie den aktuellen Status der privaten CDN-Konfiguration in Ihrem Office 365 Mandanten abrufen. Verbinden mithilfe der SharePoint Onlineverwaltungsshell zu Ihrem Mandanten:

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

Verwenden Sie nun das Cmdlet **"Get-SPOTenantCdnEnabled",** um die CDN Statuseinstellungen vom Mandanten abzurufen:

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

Der Status der CDN für den angegebenen CdnType wird auf dem Bildschirm ausgegeben.

Verwenden Sie das Cmdlet **"Set-SPOTenantCdnEnabled",** um Ihrer Organisation die Verwendung der Office 365 CDN zu ermöglichen. Sie können Ihrer Organisation ermöglichen, öffentliche Ursprünge, private Ursprünge oder beide gleichzeitig zu verwenden. Sie können auch die CDN konfigurieren, um die Einrichtung der Standardursprungs beim Aktivieren zu überspringen. Sie können diese Ursprünge immer später hinzufügen, wie in diesem Thema beschrieben.

In Windows PowerShell für SharePoint Online:

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Geben Sie beispielsweise den folgenden Befehl ein, um Ihrer Organisation die Verwendung von öffentlichen und privaten Ursprüngen zu ermöglichen:

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Geben Sie den folgenden Befehl ein, um Ihrer Organisation die Verwendung von öffentlichen und privaten Ursprüngen zu ermöglichen, aber das Einrichten der Standardursprungs zu überspringen:

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Informationen zu den Standardmäßigen [Ursprüngen,](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) die standardmäßig bereitgestellt werden, wenn Sie die Office 365 CDN aktivieren, und zu den potenziellen Auswirkungen des Überspringens der Einrichtung von Standardursprungen finden Sie unter "Default CDN origins".

Um Ihrer Organisation die Verwendung öffentlicher Ursprünge zu ermöglichen, geben Sie den folgenden Befehl ein:

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

Geben Sie den folgenden Befehl ein, um Ihrer Organisation die Verwendung privater Ursprünge zu ermöglichen:

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

Weitere Informationen zu diesem Cmdlet finden Sie unter ["Set-SPOTenantCdnEnabled".](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Ändern der Liste der Dateitypen, die in die Office 365 CDN eingeschlossen werden sollen (optional)

> [!TIP]
> Wenn Sie Dateitypen mithilfe des Cmdlets **"Set-SPOTenantCdnPolicy"** definieren, überschreiben Sie die aktuell definierte Liste. Wenn Sie der Liste zusätzliche Dateitypen hinzufügen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Dateitypen bereits zulässig sind, und fügen Sie sie zusammen mit Ihren neuen in die Liste ein.

Verwenden Sie das Cmdlet **"Set-SPOTenantCdnPolicy",** um statische Dateitypen zu definieren, die von öffentlichen und privaten Ursprüngen im CDN gehostet werden können. Standardmäßig sind allgemeine Objekttypen zulässig, z. B. CSS, .gif, .jpg und .js.

In Windows PowerShell für SharePoint Online:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Um beispielsweise die CDN zum Hosten von CSS- und .png-Dateien zu aktivieren, geben Sie den folgenden Befehl ein:

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Verwenden Sie das Cmdlet **"Get-SPOTenantCdnPolicies",** um zu sehen, welche Dateitypen derzeit vom CDN zugelassen werden:

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Weitere Informationen zu diesen Cmdlets finden Sie unter ["Set-SPOTenantCdnPolicy"](/powershell/module/sharepoint-online/) und ["Get-SPOTenantCdnPolicies".](/powershell/module/sharepoint-online/)

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Ändern der Liste der Websiteklassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten (optional)

> [!TIP]
> Wenn Sie Websiteklassifizierungen mithilfe des Cmdlets **"Set-SPOTenantCdnPolicy"** ausschließen, überschreiben Sie die aktuell definierte Liste. Wenn Sie zusätzliche Websiteklassifizierungen ausschließen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Klassifizierungen bereits ausgeschlossen sind, und fügen Sie sie dann zusammen mit Ihren neuen hinzu.

Verwenden Sie das Cmdlet **Set-SPOTenantCdnPolicy** -Cmdlet zum Ausschließen von Websiteklassifizierungen, die Sie nicht über das CDN zur Verfügung stellen möchten. Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.

In Windows PowerShell für SharePoint Online:

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

Verwenden Sie das Cmdlet **"Get-SPOTenantCdnPolicies",** um zu sehen, welche Websiteklassifizierungen derzeit eingeschränkt sind:

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

Die Eigenschaften, die zurückgegeben werden, sind _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ und _ExcludeIfNoScriptDisabled_.

Die _IncludeFileExtensions-Eigenschaft_ enthält die Liste der Dateierweiterungen, die vom CDN bereitgestellt werden.

> [!NOTE]
> Die Standardmäßigen Dateierweiterungen unterscheiden sich zwischen öffentlichen und privaten Dateierweiterungen.

Die _ExcludeRestrictedSiteClassifications-Eigenschaft_ enthält die Websiteklassifizierungen, die Sie von der CDN ausschließen möchten. Beispielsweise können Sie Websites ausschließen, die als **vertraulich** gekennzeichnet sind, damit Inhalte von Websites mit dieser Klassifizierung nicht aus dem CDN bereitgestellt werden.

Die _ExcludeIfNoScriptDisabled-Eigenschaft_ schließt Inhalte aus dem CDN basierend auf den _NoScript-Attributeinstellungen_ auf Websiteebene aus. Standardmäßig ist das _NoScript-Attribut_ auf **"Enabled"** für _moderne_ Websites und **"Disabled"** für _klassische_ Websites festgelegt. Dies hängt von Ihren Mandanteneinstellungen ab.

Weitere Informationen zu diesen Cmdlets finden Sie unter ["Set-SPOTenantCdnPolicy"](/powershell/module/sharepoint-online/) und ["Get-SPOTenantCdnPolicies".](/powershell/module/sharepoint-online/)

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Hinzufügen eines Ursprungs für Ihre Ressourcen

Verwenden Sie das **Cmdlet "Add-SPOTenantCdnOrigin",** um einen Ursprung zu definieren. Sie können mehrere Ursprünge definieren. Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.

> [!IMPORTANT]
> Sie sollten niemals Ressourcen, die Benutzerinformationen enthalten oder für Ihre Organisation vertraulich sind, an einem öffentlichen Ursprung platzieren.

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Der Wert des _Pfads_ ist der relative Pfad zu der Bibliothek oder dem Ordner, der die Objekte enthält. Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden. Ursprünge unterstützen Platzhalter, die der URL vorangestellt sind. Auf diese Weise können Sie Ursprünge erstellen, die sich über mehrere Websites erstrecken. Um beispielsweise alle Ressourcen in den Masterpages-Ordner für alle Ihre Websites als öffentlichen Ursprung innerhalb des CDN einzuschließen, geben Sie den folgenden Befehl ein:

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Der Platzhaltermodifizierer * **/** kann nur am Anfang des Pfads verwendet werden und gleicht alle URL-Segmente unter der angegebenen URL ab.
+ Der Pfad kann auf eine Dokumentbibliothek, einen Ordner oder eine Website verweisen. Beispielsweise entspricht der Pfad _*/site1_ allen Dokumentbibliotheken unter der Website.

Sie können einen Ursprung mit einem bestimmten relativen Pfad hinzufügen. Sie können keinen Ursprung mithilfe des vollständigen Pfads hinzufügen.

In diesem Beispiel wird ein privater Ursprung der Websiteassets-Bibliothek auf einer bestimmten Website hinzugefügt:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In diesem Beispiel wird ein privater Ursprung des Ordners _"folder1"_ in der Websiteobjektbibliothek der Websitesammlung hinzugefügt:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Wenn ein Leerzeichen im Pfad vorhanden ist, können Sie den Pfad entweder in doppelte Anführungszeichen umgeben oder das Leerzeichen durch die URL-Codierung %20 ersetzen. In den folgenden Beispielen wird ein privater Ursprung des _Ordners 1_ in der Websiteobjektbibliothek der Websitesammlung hinzugefügt:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

> [!NOTE]
> In privaten Ursprüngen müssen Ressourcen, die von einem Ursprung freigegeben werden, über eine Hauptversion verfügen, bevor über die CDN auf sie zugegriffen werden kann.

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Beispiel: Konfigurieren eines öffentlichen Ursprungs für Ihre Gestaltungsvorlagen und für Ihre Formatbibliothek für SharePoint Online

Normalerweise werden diese Ursprünge standardmäßig für Sie eingerichtet, wenn Sie die Office 365 CDN aktivieren. Wenn Sie sie jedoch manuell aktivieren möchten, führen Sie die folgenden Schritte aus.

+ Verwenden Sie das Cmdlet **"Add-SPOTenantCdnOrigin",** um die Formatbibliothek als öffentlichen Ursprung zu definieren.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Verwenden Sie das Cmdlet **"Add-SPOTenantCdnOrigin",** um die Gestaltungsvorlagen als öffentlichen Ursprung zu definieren.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Beispiel: Konfigurieren eines privaten Ursprungs für Ihre Websiteobjekte, Websiteseiten und Veröffentlichungsbilder für SharePoint Online

+ Verwenden Sie das Cmdlet **"Add-SPOTenantCdnOrigin",** um den Websiteressourcenordner als privaten Ursprung zu definieren.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Verwenden Sie das Cmdlet **"Add-SPOTenantCdnOrigin",** um den Ordner "Websiteseiten" als privaten Ursprung zu definieren.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Verwenden Sie das Cmdlet **"Add-SPOTenantCdnOrigin",** um den Ordner "Veröffentlichungsimages" als privaten Ursprung zu definieren.

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Beispiel: Konfigurieren eines privaten Ursprungs für eine Websitesammlung für SharePoint Online

Verwenden Sie das Cmdlet **"Add-SPOTenantCdnOrigin",** um eine Websitesammlung als privaten Ursprung zu definieren. Beispiel:

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum. Möglicherweise wird eine _ausstehende Konfigurationsnachricht_ angezeigt, die erwartet wird, wenn der SharePoint Onlinemandant eine Verbindung mit dem CDN Dienst herstellt. Dies kann bis zu 15 Minuten dauern.

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>Verwalten der Office 365 CDN

Nachdem Sie die CDN eingerichtet haben, können Sie Änderungen an Ihrer Konfiguration vornehmen, wenn Sie Inhalte aktualisieren oder wenn sich Ihre Anforderungen ändern, wie in diesem Abschnitt beschrieben.

<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Hinzufügen, Aktualisieren oder Entfernen von Ressourcen aus dem Office 365 CDN

Nachdem Sie die Einrichtungsschritte abgeschlossen haben, können Sie neue Ressourcen hinzufügen und vorhandene Objekte jederzeit aktualisieren oder entfernen. Nehmen Sie einfach Ihre Änderungen an den Ressourcen im Ordner oder SharePoint Bibliothek vor, die Sie als Ursprung identifiziert haben. Wenn Sie ein neues Objekt hinzufügen, ist es sofort über die CDN verfügbar. Wenn Sie die Ressource aktualisieren, dauert es jedoch bis zu 15 Minuten, bis die neue Kopie verteilt und im CDN verfügbar ist.

Wenn Sie den Speicherort des Ursprungs abrufen müssen, können Sie das Cmdlet **"Get-SPOTenantCdnOrigins"** verwenden. Informationen zur Verwendung dieses Cmdlets finden Sie unter ["Get-SPOTenantCdnOrigins".](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Entfernen eines Ursprungs aus dem Office 365 CDN

Sie können den Zugriff auf einen Ordner oder eine SharePoint Bibliothek entfernen, die Sie als Ursprung identifiziert haben. Verwenden Sie dazu das Cmdlet **"Remove-SPOTenantCdnOrigin".**

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Informationen zur Verwendung dieses Cmdlets finden Sie unter [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin).

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Ändern eines Ursprungs in der Office 365 CDN

Sie können einen von Ihnen erstellten Ursprung nicht ändern. Entfernen Sie stattdessen den Ursprung, und fügen Sie dann einen neuen hinzu. Weitere Informationen finden Sie unter [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh) and To add an origin for your [assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Deaktivieren der Office 365 CDN

Verwenden Sie das Cmdlet **"Set-SPOTenantCdnEnabled",** um die CDN für Ihre Organisation zu deaktivieren. Wenn Sie sowohl den öffentlichen als auch den privaten Ursprung für die CDN aktiviert haben, müssen Sie das Cmdlet zweimal ausführen, wie in den folgenden Beispielen gezeigt.

Um die Verwendung öffentlicher Ursprünge im CDN zu deaktivieren, geben Sie den folgenden Befehl ein:

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

Um die Verwendung der privaten Ursprünge im CDN zu deaktivieren, geben Sie den folgenden Befehl ein:

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

Weitere Informationen zu diesem Cmdlet finden Sie unter ["Set-SPOTenantCdnEnabled".](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>Einrichten und Konfigurieren der Office 365 CDN mithilfe von PnP PowerShell

Für die Verfahren in diesem Abschnitt müssen Sie PnP PowerShell verwenden, um eine Verbindung mit SharePoint Online herzustellen. Anweisungen finden Sie unter ["Erste Schritte mit PnP PowerShell".](https://github.com/SharePoint/PnP-PowerShell#getting-started)

Führen Sie diese Schritte aus, um die CDN zum Hosten Ihrer Objekte in SharePoint Online mit PnP PowerShell einzurichten und zu konfigurieren.

<details>
  <summary>Zum Erweitern klicken</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>Ermöglichen Sie Ihrer Organisation die Verwendung der Office 365 CDN

Bevor Sie Änderungen an den Mandanteneinstellungen CDN vornehmen, sollten Sie den aktuellen Status der privaten CDN-Konfiguration in Ihrem Office 365 Mandanten abrufen. Verbinden zu Ihrem Mandanten mithilfe von PnP PowerShell:

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

Verwenden Sie nun das Cmdlet **"Get-PnPTenantCdnEnabled",** um die CDN Statuseinstellungen vom Mandanten abzurufen:

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

Der Status der CDN für den angegebenen CdnType wird auf dem Bildschirm ausgegeben.

Verwenden Sie das Cmdlet **"Set-PnPTenantCdnEnabled",** um Ihrer Organisation die Verwendung der Office 365 CDN zu ermöglichen. Sie können Ihrer Organisation ermöglichen, öffentliche Ursprünge, private Ursprünge oder beide gleichzeitig zu verwenden. Sie können auch die CDN konfigurieren, um die Einrichtung der Standardursprungs beim Aktivieren zu überspringen. Sie können diese Ursprünge immer später hinzufügen, wie in diesem Thema beschrieben.

In PnP PowerShell:

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

Geben Sie beispielsweise den folgenden Befehl ein, um Ihrer Organisation die Verwendung von öffentlichen und privaten Ursprüngen zu ermöglichen:

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

Geben Sie den folgenden Befehl ein, um Ihrer Organisation die Verwendung von öffentlichen und privaten Ursprüngen zu ermöglichen, aber das Einrichten der Standardursprungs zu überspringen:

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

Informationen zu den [Ursprüngen,](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) die standardmäßig bereitgestellt werden, wenn Sie die Office 365 CDN aktivieren, und zu den potenziellen Auswirkungen des Überspringens der Einrichtung der Standardursprungs finden Sie unter "Standard CDN Ursprünge".

Um Ihrer Organisation die Verwendung von öffentlichen Ursprüngen zu ermöglichen, geben Sie den folgenden Befehl ein:

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

Geben Sie den folgenden Befehl ein, um Ihrer Organisation die Verwendung privater Ursprünge zu ermöglichen:

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

Weitere Informationen zu diesem Cmdlet finden Sie unter ["Set-PnPTenantCdnEnabled".](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>Ändern der Liste der Dateitypen, die in die Office 365 CDN eingeschlossen werden sollen (optional)

> [!TIP]
> Wenn Sie Dateitypen mithilfe des Cmdlets **"Set-PnPTenantCdnPolicy"** definieren, überschreiben Sie die aktuell definierte Liste. Wenn Sie der Liste zusätzliche Dateitypen hinzufügen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Dateitypen bereits zulässig sind, und fügen Sie sie zusammen mit Ihren neuen in die Liste ein.

Verwenden Sie das Cmdlet **"Set-PnPTenantCdnPolicy",** um statische Dateitypen zu definieren, die von öffentlichen und privaten Ursprüngen im CDN gehostet werden können. Standardmäßig sind allgemeine Objekttypen zulässig, z. B. CSS, .gif, .jpg und .js.

In PnP PowerShell:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

Um beispielsweise die CDN zum Hosten von CSS- und .png-Dateien zu aktivieren, geben Sie den folgenden Befehl ein:

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

Verwenden Sie das Cmdlet **"Get-PnPTenantCdnPolicies",** um zu sehen, welche Dateitypen derzeit vom CDN zugelassen werden:

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Weitere Informationen zu diesen Cmdlets finden Sie unter ["Set-PnPTenantCdnPolicy"](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) und ["Get-PnPTenantCdnPolicies".](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>Ändern der Liste der Websiteklassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten (optional)

> [!TIP]
> Wenn Sie Websiteklassifizierungen mithilfe des Cmdlets **"Set-PnPTenantCdnPolicy"** ausschließen, überschreiben Sie die aktuell definierte Liste. Wenn Sie zusätzliche Websiteklassifizierungen ausschließen möchten, verwenden Sie zuerst das Cmdlet, um herauszufinden, welche Klassifizierungen bereits ausgeschlossen sind, und fügen Sie sie dann zusammen mit Ihren neuen hinzu.

Verwenden Sie das Cmdlet **"Set-PnPTenantCdnPolicy",** um Websiteklassifizierungen auszuschließen, die Sie nicht über die CDN verfügbar machen möchten. Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.

In PnP PowerShell:

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

Verwenden Sie das Cmdlet **"Get-PnPTenantCdnPolicies",** um zu sehen, welche Websiteklassifizierungen derzeit eingeschränkt sind:

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

Die Eigenschaften, die zurückgegeben werden, sind _IncludeFileExtensions_, _ExcludeRestrictedSiteClassifications_ und _ExcludeIfNoScriptDisabled_.

Die _IncludeFileExtensions-Eigenschaft_ enthält die Liste der Dateierweiterungen, die vom CDN bereitgestellt werden.

> [!NOTE]
> Die Standardmäßigen Dateierweiterungen unterscheiden sich zwischen öffentlichen und privaten Dateierweiterungen.

Die _ExcludeRestrictedSiteClassifications-Eigenschaft_ enthält die Websiteklassifizierungen, die Sie von der CDN ausschließen möchten. Beispielsweise können Sie Websites ausschließen, die als **vertraulich** gekennzeichnet sind, damit Inhalte von Websites mit dieser Klassifizierung nicht aus dem CDN bereitgestellt werden.

Die _ExcludeIfNoScriptDisabled-Eigenschaft_ schließt Inhalte aus dem CDN basierend auf den _NoScript-Attributeinstellungen_ auf Websiteebene aus. Standardmäßig ist das _NoScript-Attribut_ auf **"Enabled"** für _moderne_ Websites und **"Disabled"** für _klassische_ Websites festgelegt. Dies hängt von Ihren Mandanteneinstellungen ab.

Weitere Informationen zu diesen Cmdlets finden Sie unter ["Set-PnPTenantCdnPolicy"](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy) und ["Get-PnPTenantCdnPolicies".](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>Hinzufügen eines Ursprungs für Ihre Ressourcen

Verwenden Sie das **Cmdlet "Add-PnPTenantCdnOrigin",** um einen Ursprung zu definieren. Sie können mehrere Ursprünge definieren. Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.

> [!IMPORTANT]
> Sie sollten niemals Ressourcen, die Benutzerinformationen enthalten oder für Ihre Organisation vertraulich sind, an einem öffentlichen Ursprung platzieren.

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

Der Wert des _Pfads_ ist der relative Pfad zu der Bibliothek oder dem Ordner, der die Ressourcen enthält. Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden. Ursprünge unterstützen Platzhalter, die der URL vorangestellt sind. Auf diese Weise können Sie Ursprünge erstellen, die sich über mehrere Websites erstrecken. Um beispielsweise alle Ressourcen in den Masterpages-Ordner für alle Ihre Websites als öffentlichen Ursprung innerhalb des CDN einzuschließen, geben Sie den folgenden Befehl ein:

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ Der Platzhaltermodifizierer * **/** kann nur am Anfang des Pfads verwendet werden und gleicht alle URL-Segmente unter der angegebenen URL ab.
+ Der Pfad kann auf eine Dokumentbibliothek, einen Ordner oder eine Website verweisen. Beispielsweise entspricht der Pfad _*/site1_ allen Dokumentbibliotheken unter der Website.

Sie können einen Ursprung mit einem bestimmten relativen Pfad hinzufügen. Sie können keinen Ursprung mithilfe des vollständigen Pfads hinzufügen.

In diesem Beispiel wird ein privater Ursprung der Websiteressourcenbibliothek auf einer bestimmten Website hinzugefügt:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

In diesem Beispiel wird ein privater Ursprung des Ordners _"folder1"_ in der Websiteobjektbibliothek der Websitesammlung hinzugefügt:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

Wenn ein Leerzeichen im Pfad vorhanden ist, können Sie den Pfad entweder in doppelte Anführungszeichen umgeben oder das Leerzeichen durch die URL-Codierung %20 ersetzen. In den folgenden Beispielen wird ein privater Ursprung des _Ordners 1_ in der Websiteobjektbibliothek der Websitesammlung hinzugefügt:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

> [!NOTE]
> In privaten Ursprüngen müssen Ressourcen, die von einem Ursprung freigegeben werden, über eine Hauptversion verfügen, bevor über die CDN auf sie zugegriffen werden kann.

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>Beispiel: Konfigurieren eines öffentlichen Ursprungs für Ihre Gestaltungsvorlagen und für Ihre Formatbibliothek für SharePoint Online

Normalerweise werden diese Ursprünge standardmäßig für Sie eingerichtet, wenn Sie die Office 365 CDN aktivieren. Wenn Sie sie jedoch manuell aktivieren möchten, führen Sie die folgenden Schritte aus.

+ Verwenden Sie das Cmdlet **"Add-PnPTenantCdnOrigin",** um die Formatbibliothek als öffentlichen Ursprung zu definieren.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ Verwenden Sie das Cmdlet **"Add-PnPTenantCdnOrigin",** um die Gestaltungsvorlagen als öffentlichen Ursprung zu definieren.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>Beispiel: Konfigurieren eines privaten Ursprungs für Ihre Websiteressourcen, Websiteseiten und Veröffentlichungsbilder für SharePoint Online

+ Verwenden Sie das Cmdlet **"Add-PnPTenantCdnOrigin",** um den Websiteressourcenordner als privaten Ursprung zu definieren.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ Verwenden Sie das Cmdlet **"Add-PnPTenantCdnOrigin",** um den Ordner "Websiteseiten" als privaten Ursprung zu definieren.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ Verwenden Sie das Cmdlet **"Add-PnPTenantCdnOrigin",** um den Ordner "Veröffentlichungsimages" als privaten Ursprung zu definieren.

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum. Dies kann bis zu 15 Minuten dauern.

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>Beispiel: Konfigurieren eines privaten Ursprungs für eine Websitesammlung für SharePoint Online

Verwenden Sie das Cmdlet **"Add-PnPTenantCdnOrigin",** um eine Websitesammlung als privaten Ursprung zu definieren. Beispiel:

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

Weitere Informationen zu diesem Befehl und seiner Syntax finden Sie unter [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin).

Nachdem Sie den Befehl ausgeführt haben, synchronisiert das System die Konfiguration im gesamten Rechenzentrum. Möglicherweise wird eine _ausstehende Konfigurationsnachricht_ angezeigt, die erwartet wird, wenn der SharePoint Onlinemandant eine Verbindung mit dem CDN Dienst herstellt. Dies kann bis zu 15 Minuten dauern.

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>Verwalten der Office 365 CDN

Nachdem Sie die CDN eingerichtet haben, können Sie Änderungen an Ihrer Konfiguration vornehmen, wenn Sie Inhalte aktualisieren oder wenn sich Ihre Anforderungen ändern, wie in diesem Abschnitt beschrieben.

<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>Hinzufügen, Aktualisieren oder Entfernen von Ressourcen aus dem Office 365 CDN

Nachdem Sie die Einrichtungsschritte abgeschlossen haben, können Sie neue Ressourcen hinzufügen und vorhandene Objekte jederzeit aktualisieren oder entfernen. Nehmen Sie einfach Ihre Änderungen an den Ressourcen im Ordner oder SharePoint Bibliothek vor, die Sie als Ursprung identifiziert haben. Wenn Sie ein neues Objekt hinzufügen, ist es sofort über die CDN verfügbar. Wenn Sie die Ressource aktualisieren, dauert es jedoch bis zu 15 Minuten, bis die neue Kopie verteilt wurde und im CDN verfügbar ist.

Wenn Sie den Speicherort des Ursprungs abrufen müssen, können Sie das Cmdlet **"Get-PnPTenantCdnOrigin"** verwenden. Informationen zur Verwendung dieses Cmdlets finden Sie unter ["Get-PnPTenantCdnOrigin".](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>Entfernen eines Ursprungs aus dem Office 365 CDN

Sie können den Zugriff auf einen Ordner oder eine SharePoint Bibliothek entfernen, die Sie als Ursprung identifiziert haben. Verwenden Sie dazu das Cmdlet **"Remove-PnPTenantCdnOrigin".**

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

Informationen zur Verwendung dieses Cmdlets finden Sie unter [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin).

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>Ändern eines Ursprungs in der Office 365 CDN

Sie können einen von Ihnen erstellten Ursprung nicht ändern. Entfernen Sie stattdessen den Ursprung, und fügen Sie dann einen neuen hinzu. Weitere Informationen finden Sie unter [To remove an origin from the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh) and To add an origin for your [assets](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh).

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>Deaktivieren der Office 365 CDN

Verwenden Sie das Cmdlet **"Set-PnPTenantCdnEnabled",** um die CDN für Ihre Organisation zu deaktivieren. Wenn Sie sowohl den öffentlichen als auch den privaten Ursprung für die CDN aktiviert haben, müssen Sie das Cmdlet zweimal ausführen, wie in den folgenden Beispielen gezeigt.

Um die Verwendung öffentlicher Ursprünge im CDN zu deaktivieren, geben Sie den folgenden Befehl ein:

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

Um die Verwendung der privaten Ursprünge im CDN zu deaktivieren, geben Sie den folgenden Befehl ein:

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

Weitere Informationen zu diesem Cmdlet finden Sie unter ["Set-PnPTenantCdnEnabled".](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>Einrichten und Konfigurieren des Office 365 CDN mithilfe von Office 365 CLI

Die Verfahren in diesem Abschnitt erfordern, dass Sie die [Office 365 CLI](https://aka.ms/o365cli)installiert haben. Stellen Sie als Nächstes mithilfe des [Anmeldebefehls](https://pnp.github.io/office365-cli/cmd/login/) eine Verbindung mit Ihrem Office 365 Mandanten her.

Führen Sie diese Schritte aus, um die CDN zum Hosten Ihrer Objekte in SharePoint Online mithilfe der Office 365 CLI einzurichten und zu konfigurieren.

<details>
  <summary>Zum Erweitern klicken</summary>

### <a name="enable-the-office-365-cdn"></a>Aktivieren der Office 365 CDN

Sie können den Status des Office 365 CDN in Ihrem Mandanten mithilfe des Cmdlets [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) verwalten.

Um das öffentliche Office 365 CDN in Ihrem Mandanten zu aktivieren, führen Sie Folgendes aus:

```cli
spo cdn set --type Public --enabled true
```

Führen Sie zum Aktivieren der Office 365 SharePoint CDN Folgendes aus:

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>Anzeigen des aktuellen Status des Office 365 CDN

Um zu überprüfen, ob der bestimmte Typ von Office 365 CDN aktiviert oder deaktiviert ist, verwenden Sie den Befehl [spo cdn get.](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)

Um zu überprüfen, ob das öffentliche Office 365 CDN aktiviert ist, führen Sie Folgendes aus:

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>Anzeigen der Office 365 CDN Ursprünge

Um die derzeit konfigurierten öffentlichen Office 365 CDN-Ursprünge anzuzeigen, führen Sie Folgendes aus:

```cli
spo cdn origin list --type Public
```

Informationen zu den [Ursprüngen,](use-microsoft-365-cdn-with-spo.md#default-cdn-origins) die standardmäßig bereitgestellt werden, wenn Sie die Office 365 CDN aktivieren, finden Sie unter "Standard CDN Ursprünge".

### <a name="add-an-office-365-cdn-origin"></a>Hinzufügen eines Office 365 CDN Ursprungs

> [!IMPORTANT]
> Sie sollten niemals Ressourcen, die für Ihre Organisation als vertraulich gelten, in einer SharePoint Dokumentbibliothek platzieren, die als öffentlicher Ursprung konfiguriert ist.

Verwenden Sie den Befehl [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) zum Definieren eines CDN-Ursprungs. Sie können mehrere Ursprünge definieren. Der Ursprung ist eine URL, die auf eine SharePoint-Bibliothek oder einen Ordner mit den Objekten verweist, die vom CDN gehostet werden sollen.

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

Gibt `path` den relativen Pfad zu dem Ordner an, der die Ressourcen enthält. Sie können Platzhalter zusätzlich zu relativen Pfaden verwenden.

Führen Sie Folgendes aus, um alle Objekte in den **Gestaltungsvorlagenkatalog** aller Websites als öffentlichen Ursprung einzuschließen:

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

Führen Sie Folgendes aus, um einen öffentlichen Ursprung aus der CDN-Konfiguration zu entfernen:

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> Das Entfernen eines CDN Ursprungs wirkt sich nicht auf die Dateien aus, die in einer Dokumentbibliothek gespeichert sind, die mit diesem Ursprung übereinstimmt. Wenn auf diese Ressourcen mithilfe ihrer SharePoint-URL verwiesen wurde, wechseln SharePoint automatisch zurück zur ursprünglichen URL, die auf die Dokumentbibliothek verweist. Wenn jedoch auf Ressourcen mithilfe einer öffentlichen CDN-URL verwiesen wurde, wird beim Entfernen des Ursprungs der Link beschädigt, und Sie müssen sie manuell ändern.

### <a name="modify-an-office-365-cdn-origin"></a>Ändern eines Office 365 CDN Ursprungs

Es ist nicht möglich, einen vorhandenen CDN-Ursprung zu ändern. Stattdessen sollten Sie den zuvor definierten CDN-Ursprung mit dem Befehl `spo cdn origin remove` entfernen und mit dem Befehl `spo cdn origin add` einen neuen hinzufügen.

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>Ändern der Dateitypen, die in die Office 365 CDN

Standardmäßig sind die folgenden Dateitypen in der CDN enthalten: _CSS, EOT, .gif, ICO, JPEG, .jpg, .js, MAP, .png, SVG, TTF, WOFF UND WOFF2_. Wenn Sie weitere Dateitypen in das CDN einbeziehen müssen, können Sie die CDN-Konfiguration mit dem Befehl [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) ändern.

> [!NOTE]
> Durch das Ändern der Liste von Dateitypen überschreiben Sie die aktuell definierte Liste. Wenn Sie weitere Dateitypen einbeziehen möchten, verwenden Sie zunächst den Befehl [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/), um herauszufinden, welche Dateitypen derzeit konfiguriert sind.

Führen Sie Folgendes aus, um den _JSON-Dateityp_ der Standardliste der Im öffentlichen CDN enthaltenen Dateitypen hinzuzufügen:

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>Ändern der Liste von Websiteklassifizierungen, die Sie aus dem Office 365 CDN ausschließen möchten

Verwenden Sie den Befehl [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) zum Ausschließen von Websiteklassifizierungen, die Sie nicht über das CDN zur Verfügung stellen möchten. Standardmäßig sind keine Websiteklassifizierungen ausgeschlossen.

> [!NOTE]
> Durch das Ändern der Liste der ausgeschlossenen Websiteklassifizierungen überschreiben Sie die aktuell definierte Liste. Wenn Sie zusätzliche Klassifizierungen ausschließen möchten, verwenden Sie zunächst den Befehl [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/), um herauszufinden, welche Klassifizierungen derzeit konfiguriert sind.

Um als _HBI_ klassifizierte Websites von der öffentlichen CDN auszuschließen, führen Sie

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>Deaktivieren der Office 365 CDN

Um das Office 365 CDN zu deaktivieren, verwenden Sie den Befehl `spo cdn set`. Beispiel:

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>Verwenden Ihrer CDN-Ressourcen

Nachdem Sie nun die CDN und konfigurierten Ursprünge und Richtlinien aktiviert haben, können Sie mit der Verwendung Ihrer CDN-Ressourcen beginnen.

In diesem Abschnitt erfahren Sie, wie Sie CDN URLs in Ihren SharePoint Seiten und Inhalten verwenden, sodass SharePoint Anforderungen für Ressourcen in öffentlichen und privaten Ursprüngen an die CDN weiterleitet.

+ [Aktualisieren von Links zu CDN Ressourcen](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [Verwenden von Ressourcen in öffentlichen Ursprüngen](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [Verwenden von Ressourcen in privaten Ursprüngen](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

Informationen zur Verwendung der CDN zum Hosten clientseitiger Webparts finden Sie im Thema [Hosten ihres clientseitigen Webparts aus Office 365 CDN (Hello World Teil 4).](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)

> [!NOTE]
> Wenn Sie den _Ordner "ClientSideAssets"_ zur liste der **privaten** CDN Ursprünge hinzufügen, können CDN gehostete benutzerdefinierte Webparts nicht gerendert werden. Dateien, die von SPFX-Webparts verwendet werden, können nur die öffentliche CDN verwenden, und der ClientSideAssets-Ordner ist ein Standardursprung für öffentliche CDN.

### <a name="updating-links-to-cdn-assets"></a>Aktualisieren von Links zu CDN Ressourcen

Um Ressourcen zu verwenden, die Sie einem Ursprung hinzugefügt haben, aktualisieren Sie einfach Links zur Originaldatei mit dem Pfad zu der Datei im Ursprung.

+ Bearbeiten Sie die Seite oder den Inhalt, die Links zu Ressourcen enthält, die Sie einem Ursprung hinzugefügt haben. Sie können auch eine von mehreren Methoden verwenden, um Links über eine Eingabewebsite oder Websitesammlung hinweg global zu suchen und zu ersetzen, wenn Sie den Link zu einem bestimmten Objekt überall dort aktualisieren möchten, wo er angezeigt wird.
+ Ersetzen Sie für jeden Link zu einer Ressource in einem Ursprung den Pfad durch den Pfad zur Datei im CDN Ursprung. Sie können relative Pfade verwenden.
+ Speichern Sie die Seite oder den Inhalt.

Betrachten Sie beispielsweise das Bild _/site/SiteAssets/images/image.png_, das Sie in den Dokumentbibliotheksordner _/site/CDN_origins/public/_ kopiert haben. Um die CDN Ressource zu verwenden, ersetzen Sie den ursprünglichen Pfad zum Speicherort der Bilddatei durch den Pfad zum Ursprung, um die neue URL _/site/CDN_origins/public/image.png_ zu erstellen.

Wenn Sie die vollständige URL zu der Ressource anstelle eines relativen Pfads verwenden möchten, erstellen Sie den Link wie folgt:

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> Im Allgemeinen sollten Sie URLs nicht direkt in Ressourcen im CDN hartcodieren. Sie können jedoch bei Bedarf manuell URLs für Ressourcen in öffentlichen Ursprüngen erstellen. Weitere Informationen finden Sie unter [Hardcoding CDN URLs für öffentliche Ressourcen.](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)

Informationen dazu, wie Sie überprüfen können, ob Ressourcen von der CDN bereitgestellt werden, finden Sie unter ["Wie kann ich bestätigen, dass Ressourcen von der CDN bereitgestellt werden?"](use-microsoft-365-cdn-with-spo.md#CDNConfirm) unter [Problembehandlung beim Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting).

### <a name="using-assets-in-public-origins"></a>Verwenden von Ressourcen in öffentlichen Ursprüngen

Das **Veröffentlichungsfeature** in SharePoint Online schreibt URLs von Ressourcen, die in öffentlichen Ursprüngen gespeichert sind, automatisch in ihre CDN Entsprechungen um, sodass Ressourcen vom CDN Dienst anstatt von SharePoint bereitgestellt werden.

Wenn sich Ihr Ursprung in einer Website mit aktivierter Veröffentlichungsfunktion befindet und die Objekte, die Sie an die CDN auslagern möchten, in einer der folgenden Kategorien sind, werden SharePoint URLs für Ressourcen im Ursprung automatisch neu schreiben, vorausgesetzt, dass die Ressource nicht von einer CDN Richtlinie ausgeschlossen wurde.

Es folgt eine Übersicht über die Links, die automatisch vom SharePoint-Veröffentlichungsfeature umgeschrieben werden:

+ IMG/LINK/CSS-URLs in den HTML-Antworten klassischer Veröffentlichungsseiten
  + Dies schließt von Autoren im HTML-Inhalt einer Seite hinzugefügte Bilder ein.
+ Bild-URLs des Webparts „Bildbibliothek-Bildschirmpräsentation“
+ Bildfelder in Ergebnissen der SPList-REST-API (RenderListDataAsStream)
  + Verwenden Sie die neue Eigenschaft _ImageFieldsToTryRewriteToCdnUrls,_ um eine durch Kommas getrennte Liste von Feldern bereitzustellen.
  + Unterstützt Hyperlinkfelder und PublishingImage-Felder
+ SharePoint Bilddarstellungen

Das folgende Diagramm veranschaulicht den Workflow, wenn SharePoint eine Anforderung für eine Seite empfängt, die Ressourcen von einem öffentlichen Ursprung enthält.

![Workflowdiagramm: Abrufen Office 365 CDN Ressourcen von einem öffentlichen Ursprung](../media/O365-CDN/o365-cdn-public-steps-transparent.png "Workflow: Abrufen Office 365 CDN Ressourcen von einem öffentlichen Ursprung")

> [!TIP]
> Wenn Sie das automatische Umschreiben für bestimmte URLs auf einer Seite deaktivieren möchten, können Sie die Seite auschecken und den Abfragezeichenfolgenparameter **hinzufügen? NoAutoReWrites=true** bis zum Ende jedes Links, den Sie deaktivieren möchten.

#### <a name="constructing-cdn-urls-for-public-assets"></a>Erstellen CDN URLs für öffentliche Ressourcen

Wenn das _Veröffentlichungsfeature_ für einen öffentlichen Ursprung nicht aktiviert ist oder die Ressource nicht einer der Linktypen ist, die vom Feature für die automatische Neuschreibung des CDN Diensts unterstützt werden, können Sie URLs manuell an den CDN Speicherort der Ressourcen erstellen und diese URLs in Ihren Inhalten verwenden.

> [!NOTE]
> Sie können CDN URLs nicht für Objekte in einem privaten Ursprung hartcodieren oder erstellen, da das erforderliche Zugriffstoken, das den letzten Abschnitt der URL bildet, zum Zeitpunkt der Anforderung der Ressource generiert wird. Sie können die URL für öffentliche CDN erstellen, und die URL sollte nicht hartcodiert sein, da sie geändert werden kann.

Für öffentliche CDN Ressourcen sieht das URL-Format wie folgt aus:

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

Ersetzen Sie **TenantHostName** durch Ihren Mandantennamen. Beispiel:

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> Die Seitenkontexteigenschaft sollte verwendet werden, um das Präfix zu erstellen, anstatt hartcodieren zu https://publiccdn.sharepointonline.com müssen. Die URL kann geändert werden und sollte nicht hartcodiert sein. Wenn Sie Anzeigevorlagen mit klassischem SharePoint Online verwenden, können Sie die Eigenschaft "window._spPageContextInfo.publicCdnBaseUrl" in Ihrer Anzeigevorlage für das Präfix der URL verwenden. Wenn Sie SPFx Webparts für moderne und klassische SharePoint können Sie die Eigenschaft "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" verwenden. Dadurch wird das Präfix bereitgestellt, sodass bei einer Änderung die Implementierung mit ihr aktualisiert wird. Als Beispiel für SPFx kann die URL mithilfe der Eigenschaft "this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item" erstellt werden. Weitere Informationen finden Sie unter [Verwenden von CDN im clientseitigen Code,](https://youtu.be/IH1RbQlbhIA) der Teil der Leistungsserie der [1. Spielzeit](https://aka.ms/sppnp-perfvideos) ist.


### <a name="using-assets-in-private-origins"></a>Verwenden von Ressourcen in privaten Ursprüngen

Für die Verwendung von Ressourcen in privaten Ursprüngen ist keine zusätzliche Konfiguration erforderlich. SharePoint Online schreibt URLs für Objekte in privaten Ursprüngen automatisch um, sodass Anforderungen für diese Ressourcen immer vom CDN bereitgestellt werden. Sie können URLs nicht manuell erstellen, um Ressourcen in privaten Ursprüngen CDN, da diese URLs Token enthalten, die automatisch von SharePoint Online generiert werden müssen, wenn die Ressource angefordert wird.

Der Zugriff auf Ressourcen in privaten Ursprüngen wird durch dynamisch generierte Token basierend auf Benutzerberechtigungen für den Ursprung geschützt, mit den in den folgenden Abschnitten beschriebenen Einschränkungen. Benutzer müssen mindestens **Lesezugriff** auf die Ursprünge haben, damit die CDN Inhalte rendern kann.

Das folgende Diagramm veranschaulicht den Workflow, wenn SharePoint eine Anforderung für eine Seite mit Ressourcen von einem privaten Ursprung empfängt.

![Workflowdiagramm: Abrufen von Office 365 CDN Ressourcen aus einem privaten Ursprung](../media/O365-CDN/o365-cdn-private-steps-transparent.png "Workflow: Abrufen Office 365 CDN Ressourcen von einem privaten Ursprung")

#### <a name="token-based-authorization-in-private-origins"></a>Tokenbasierte Autorisierung in privaten Ursprüngen

Der Zugriff auf Objekte in privaten Ursprüngen im Office 365 CDN wird durch Token gewährt, die von SharePoint Online generiert werden. Benutzern, die bereits über die Berechtigung zum Zugriff auf den vom Ursprung festgelegten Ordner oder die Bibliothek verfügen, werden automatisch Token gewährt, mit denen der Benutzer basierend auf seiner Berechtigungsstufe auf die Datei zugreifen kann. Diese Zugriffstoken sind 30 bis 90 Minuten gültig, nachdem sie generiert wurden, um Tokenwiederholungsangriffe zu verhindern.

Nachdem das Zugriffstoken generiert wurde, gibt SharePoint Online einen benutzerdefinierten  URI an den Client zurück, der zwei Autorisierungsparameter (Edgeautorisierungstoken) und _Oat_ (Ursprungsautorisierungstoken) enthält. Die Struktur der einzelnen Token ist _<'Ablaufzeit im Epoch-Zeitformat'>__<'secure signature'>._ Beispiel:

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> Jeder Benutzer, der das Token besitzt, kann auf die Ressource im CDN zugreifen. URLs, die diese Zugriffstoken enthalten, werden jedoch nur über HTTPS freigegeben. Es sei denn, die URL wird explizit von einem Endbenutzer freigegeben, bevor das Token abläuft, sodass nicht autorisierten Benutzern auf die Ressource zugegriffen werden kann.

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>Berechtigungen auf Elementebene werden für Objekte in privaten Ursprüngen nicht unterstützt.

Es ist wichtig zu beachten, dass SharePoint Online berechtigungen auf Elementebene für Objekte in privaten Ursprüngen nicht unterstützt. Bei einer Datei, die sich unter befindet, haben Benutzer unter `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` den folgenden Bedingungen effektiven Zugriff auf die Datei:

|Benutzer  |Berechtigungen  |Effektiver Zugriff  |
|---------|---------|---------|
|Benutzer 1     |Hat Zugriff auf Ordner1         |Kann über die CDN auf image1.jpg zugreifen         |
|Benutzer 2     |Hat keinen Zugriff auf Ordner1         |Zugriff auf image1.jpg über die CDN         |
|Benutzer 3     |Hat keinen Zugriff auf Ordner1, aber erhält explizite Berechtigung für den Zugriff auf image1.jpg in SharePoint Online         |Kann direkt über SharePoint Online auf die Ressource image1.jpg zugreifen, jedoch nicht über die CDN         |
|Benutzer 4     |Hat Zugriff auf Ordner1, wurde jedoch explizit der Zugriff auf image1.jpg in SharePoint Online verweigert.         |Der Zugriff auf die Ressource kann nicht über SharePoint Online, aber über die CDN möglich sein, obwohl der Zugriff auf die Datei in SharePoint Online verweigert wurde.         |

<a name="CDNTroubleshooting"> </a>
## <a name="troubleshooting-the-office-365-cdn"></a>Problembehandlung beim Office 365 CDN

<a name="CDNConfirm"> </a>
### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>Wie kann ich bestätigen, dass Ressourcen vom CDN bereitgestellt werden?

Nachdem Sie Links zu CDN Ressourcen zu einer Seite hinzugefügt haben, können Sie bestätigen, dass die Ressource vom CDN bereitgestellt wird, indem Sie zur Seite navigieren, mit der rechten Maustaste auf das Bild klicken, nachdem es gerendert wurde, und die Bild-URL überprüfen.

Sie können auch die Entwicklertools Ihres Browsers verwenden, um die URL für jede Ressource auf einer Seite anzuzeigen, oder ein Netzwerküberwachungstool eines Drittanbieters verwenden.

> [!NOTE]
> Wenn Sie ein Netzwerktool wie Fiddler verwenden, um Ihre Ressourcen außerhalb des Renderns der Ressource von einer SharePoint Seite zu testen, müssen Sie den Verweiserheader "Referer: " manuell `https://yourdomain.sharepoint.com` zur GET-Anforderung hinzufügen, wobei die URL die Stamm-URL Ihres SharePoint Onlinemandanten ist.

Sie können CDN URLs nicht direkt in einem Webbrowser testen, da ein Verweiser von SharePoint Online stammen muss. Wenn Sie jedoch die CDN Objekt-URL zu einer SharePoint Seite hinzufügen und dann die Seite in einem Browser öffnen, wird die CDN Ressource auf der Seite gerendert.

Weitere Informationen zur Verwendung der Entwicklertools im Microsoft Edge Browser finden Sie unter [Microsoft Edge Developer Tools](/microsoft-edge/devtools-guide).

Ein kurzes Video, das im [YouTube-Kanal SharePoint Developer Patterns and Practices](https://aka.ms/sppnp-videos) gehostet wird und zeigt, wie Sie überprüfen können, ob Ihre CDN funktioniert, finden Sie unter ["Überprüfen Ihrer CDN Nutzung und Sicherstellen einer optimalen Netzwerkkonnektivität".](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>Warum sind Ressourcen aus einem neuen Ursprung nicht verfügbar?
Ressourcen in neuen Ursprüngen stehen nicht sofort zur Verwendung zur Verfügung, da es zeitaufwendige Zeit dauert, bis die Registrierung über die CDN verteilt wird und die Objekte vom Ursprung in CDN Speicher hochgeladen werden. Die für die Verfügbarkeit von Ressourcen im CDN erforderliche Zeit hängt von der Anzahl der Ressourcen und der Dateigrößen ab.

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>Mein clientseitiges Webpart oder SharePoint-Framework Lösung funktioniert nicht

Wenn Sie die Office 365 CDN für öffentliche Ursprünge aktivieren, erstellt der CDN Dienst automatisch die folgenden Standardursprungs:

+ */MASTERPAGE
+ */STYLE LIBRARY
+ */CLIENTSIDEASSETS

Wenn der */clientsideassets-Ursprung fehlt, schlagen SharePoint-Framework Lösungen fehl, und es werden keine Warnungen oder Fehlermeldungen generiert. Dieser Ursprung fehlt möglicherweise, weil die CDN mit dem auf **$true** festgelegten Parameter _"-NoDefaultOrigins"_ aktiviert war oder weil der Ursprung manuell gelöscht wurde.

Mit dem folgenden PowerShell-Befehl können Sie überprüfen, welche Ursprünge vorhanden sind:

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

Sie können auch die Office 365 CLI überprüfen:

```cli
spo cdn origin list
```

So fügen Sie den Ursprung in PowerShell hinzu:

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

So fügen Sie den Ursprung in der Office 365 CLI hinzu:

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>Welche PowerShell-Module und CLI-Shells muss ich mit dem Office 365 CDN verwenden?

Sie können die Office 365 CDN entweder mit dem **powerShell-Modul SharePoint Onlineverwaltungsshell** oder mit der **Office 365 CLI** verwenden.

+ [Erste Schritte mit der SharePoint Online-Verwaltungsshell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
+ [Installieren von Office 365 CLI](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>Siehe auch

[Netzwerke für die Inhaltsübermittlung](./content-delivery-networks.md)

[Netzwerkplanung und Leistungsoptimierung für Office 365](./network-planning-and-performance.md)

[SharePoint Performance Series – Office 365 CDN Videoreihe](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
