---
title: Office 365 Schnellstart für Inhalts Übermittlungs Netzwerk (CDN)
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/04/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
- M365initiative-CoreDeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 Schnellstart für Inhalts Übermittlungs Netzwerk (CDN)
ms.openlocfilehash: e9975721b5cfaaed2c9ad7562c47f12c7a5a5bc3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326889"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 Schnellstart für Inhalts Übermittlungs Netzwerk (CDN)

Sie können das integrierte **Office 365 Content Delivery Network (CDN)** verwenden, um statische Objekte (Bilder, JavaScript, Stylesheets, WOFF-Dateien) zu hosten, um eine bessere Leistung für Ihre SharePoint Online Seiten bereitzustellen. Das Office 365-Netzwerk für die Inhaltsübermittlung verbessert die Leistung, indem statische Objekte näher an den Browsern zwischengespeichert werden, die diese anfordern, wodurch Downloads beschleunigt werden und die Latenz reduziert wird. Außerdem verwendet das Office 365 CDN das http/2-Protokoll für verbesserte Komprimierung und HTTP-Pipelining. Das Office 365-Netzwerk für die Inhaltsübermittlung ist in Ihrem SharePoint Online-Abonnement enthalten.

Ausführlichere Informationen finden Sie unter [Verwenden des Office 365 Inhalts Zustellungs Netzwerks (CDN) mit SharePoint Online](use-microsoft-365-cdn-with-spo.md).

>[!NOTE]
>Das Office 365 CDN steht nur Mandanten in der Produktionsumgebung (weltweit) zur Verfügung. Die Mandanten in der US-Regierung, in China und in Deutschland unterstützen derzeit nicht die Office 365 CDN.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Verwenden Sie das Tool Seite Diagnostics für SharePoint, um Elemente zu identifizieren, die sich nicht in CDN befinden.

Sie können die **Seiten Diagnose für die SharePoint-Tool** Browser Erweiterung verwenden, um Objekte auf Ihren SharePoint Online Seiten ganz einfach aufzulisten, die einem CDN-Ursprung hinzugefügt werden können.

Das **Seiten Diagnosetool für SharePoint** ist eine Browser Erweiterung für die neuen Microsoft Edge ( https://www.microsoft.com/edge) und Chrome-Browser, die sowohl SharePoint Online moderne Portal-als auch klassische Veröffentlichungswebsite-Seiten analysieren. Das Tool stellt für jede analysierte Seite einen Bericht bereit, in dem die Leistung der Seite anhand einer definierten Gruppe von Leistungskriterien dargestellt wird. Wenn Sie das Tool "Seitendiagnose für SharePoint" installieren und mehr darüber erfahren möchten, besuchen Sie [Verwenden des Seitendiagnose-Tools für SharePoint Online](https://aka.ms/perftool).

Wenn Sie das Tool Seite Diagnostics für SharePoint auf einer SharePoint Online Seite ausführen, können Sie auf die Registerkarte **Diagnose Tests** klicken, um eine Liste der Objekte anzuzeigen, die nicht vom CDN gehostet werden. Diese Objekte werden unter der **Überschrift Content Delivery Network (CDN) Check aufgeführt (** siehe Screenshot unten).

![Seiten Diagnose](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>Das Seitendiagnose-Tool funktioniert nur für SharePoint Online und kann nicht auf einer SharePoint-Systemseite verwendet werden.

## <a name="cdn-overview"></a>CDN (Übersicht)

Das Office 365 CDN wurde entwickelt, um die Leistung für Benutzer zu optimieren, indem häufig abgerufene Objekte wie Bilder und JavaScript-Dateien über ein globales Hochgeschwindigkeits-Netzwerk verteilt werden, wodurch die Ladezeit der Seite verringert und der Zugriff auf gehostete Objekte so nah wie möglich für den Benutzer bereitgestellt wird. Das CDN ruft Ihre Objekte von einem Standort ab, der als _Ursprung_bezeichnet wird. Ein Ursprung kann eine SharePoint-Website, eine Dokumentbibliothek oder ein Ordner sein, auf die über eine URL zugegriffen werden kann.

Das Office 365 CDN wird in zwei grundlegende Typen aufgeteilt:

- **Public CDN** ist für JS (JavaScript), CSS (Stylesheets), Webschriftart Dateien (WOFF, WOFF2) und nicht-proprietäre Bilder wie Firmenlogos geeignet.
- **Private CDN** ist für die Verwendung für Bilder (PNG, JPG, JPEG, usw.) vorgesehen.

Sie können festlegen, dass sowohl öffentliche als auch private Ursprünge für Ihre Organisation gelten. Die meisten Organisationen entscheiden sich für die Implementierung einer Kombination aus beiden. Sowohl öffentliche als auch private Optionen bieten ähnliche Leistungssteigerungen, aber jedes verfügt über eindeutige Attribute und Vorteile. Weitere Informationen zu öffentlichen und privaten CDN-Ursprüngen finden Sie unter [Choose, ob jeder Ursprung öffentlich oder privat sein soll](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Aktivieren von öffentlichen und privaten CDN mit der Standardkonfiguration
Bevor Sie Änderungen an den Mandanten-CDN-Einstellungen vornehmen, sollten Sie sicherstellen, dass er die Konformitäts-, Sicherheits-und Datenschutzrichtlinien Ihrer Organisation erfüllt.

Ausführlichere Konfigurationseinstellungen oder wenn Sie bereits CDN aktiviert haben und zusätzliche Standorte (Origins) hinzufügen möchten, finden Sie im Abschnitt [Einrichten und Konfigurieren des Office 365 CDN mithilfe der SharePoint Online-Verwaltungsshell](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)

Stellen Sie über die SharePoint Online-Verwaltungsshell eine Verbindung zu Ihrem Mandanten her:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Geben Sie den folgenden Befehl ein, damit Ihre Organisation sowohl öffentliche als auch private Ursprünge mit der Standardkonfiguration verwenden kann:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Die Ausgabe dieser Cmdlets sollte wie folgt aussehen:

![Ausgabe von "Sets-SPOTenantCdnEnabled"](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Mehr dazu

[Verwenden des Seiten Diagnosetools für SharePoint Online](https://aka.ms/perftool)

[Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Netzwerke für die Inhaltsübermittlung](https://aka.ms/o365cdns)

[Netzwerkplanung und Leistungsoptimierung für Office 365](https://aka.ms/tune)

[SharePoint-Leistungsreihe-Office 365 CDN-Videoreihe](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
