---
title: Office 365 Content Delivery Network (CDN) Schnellstart
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
- m365initiative-coredeploy
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- SPO160
description: Office 365 Content Delivery Network (CDN) Schnellstart
ms.openlocfilehash: 3539ad1f11b27c60b5641976ae66a1480ef4be98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921594"
---
# <a name="office-365-content-delivery-network-cdn-quickstart"></a>Office 365 Content Delivery Network (CDN) Schnellstart

Mit dem integrierten **Office 365 Content Delivery Network (CDN)** können Sie statische Objekte (Bilder, JavaScript, Stylesheets, WOFF-Dateien) hosten, um eine bessere Leistung für Ihre SharePoint Onlineseiten zu bieten. Das Office 365-Netzwerk für die Inhaltsübermittlung verbessert die Leistung, indem statische Objekte näher an den Browsern zwischengespeichert werden, die diese anfordern, wodurch Downloads beschleunigt werden und die Latenz reduziert wird. Darüber hinaus verwendet Office 365 CDN http/2-Protokoll für verbesserte Komprimierung und HTTP-Pipelining. Das Office 365-Netzwerk für die Inhaltsübermittlung ist in Ihrem SharePoint Online-Abonnement enthalten.

Ausführlichere Informationen finden Sie unter [Use the Office 365 Content Delivery Network (CDN) with SharePoint Online](use-microsoft-365-cdn-with-spo.md).

>[!NOTE]
>Die Office 365 CDN ist nur für Mandanten in der Produktions-Cloud (weltweit) verfügbar. Mandanten in der US-Regierung, China und Deutschland unterstützen die Office 365 CDN.

## <a name="use-the-page-diagnostics-for-sharepoint-tool-to-identify-items-not-in-cdn"></a>Verwenden Sie das Tool Seitendiagnose für SharePoint, um Elemente zu identifizieren, die nicht in CDN

Sie können  die Seitendiagnose für SharePoint-Browsererweiterung verwenden, um Objekte auf Ihren SharePoint Online-Seiten auflisten zu können, die einem CDN hinzugefügt werden können.

Das **Tool Seitendiagnose für SharePoint** ist eine Browsererweiterung für die neuen browser Microsoft Edge ( und Chrome-Browser, die sowohl moderne SharePoint Online-Portal- als auch klassische https://www.microsoft.com/edge) Veröffentlichungswebsiteseiten analysiert. Das Tool stellt für jede analysierte Seite einen Bericht bereit, in dem die Leistung der Seite anhand einer definierten Gruppe von Leistungskriterien dargestellt wird. Wenn Sie das Tool "Seitendiagnose für SharePoint" installieren und mehr darüber erfahren möchten, besuchen Sie [Verwenden des Seitendiagnose-Tools für SharePoint Online](./page-diagnostics-for-spo.md).

Wenn Sie das Tool Seitendiagnose für SharePoint auf einer SharePoint Online-Seite ausführen, können Sie auf die Registerkarte Diagnosetests klicken, um eine Liste der Objekte zu sehen, die nicht von der Website gehostet CDN.  Diese Objekte werden unter der Überschrift Content Delivery Network **(CDN) aufgelistet,** wie im screenshot unten gezeigt.

![Seitendiagnose](../media/page-diagnostics-for-spo/pagediag-results-general.PNG)

>[!NOTE]
>Das Seitendiagnose-Tool funktioniert nur für SharePoint Online und kann nicht auf einer SharePoint-Systemseite verwendet werden.

## <a name="cdn-overview"></a>CDN Übersicht

Das Office 365 CDN dient dazu, die Leistung für Benutzer zu optimieren, indem häufig verwendete Objekte wie Bilder und Javascriptdateien über ein globales Hochgeschwindigkeitsnetzwerk verteilt werden, die Ladezeit der Seite reduziert und der Zugriff auf gehostete Objekte so nah wie möglich für den Benutzer ermöglicht wird. Die CDN ruft Ihre Objekte von einem Speicherort ab, der als Ursprung _bezeichnet wird._ Ein Ursprung kann eine website SharePoint Dokumentbibliothek oder ein Ordner sein, auf die über eine URL zugegriffen werden kann.

Die Office 365 CDN ist in zwei grundlegende Typen getrennt:

- **Public CDN** ist für JS (JavaScript), CSS (StyleSheets), Web Font File (WOFF, WOFF2) und nicht proprietäre Bilder wie Firmenlogos konzipiert.
- **Private CDN** für Bilder (PNG, JPG, JPEG usw.) entwickelt.

Sie können sowohl öffentliche als auch private Ursprünge für Ihre Organisation auswählen. Die meisten Organisationen entscheiden sich dafür, eine Kombination aus beiden zu implementieren. Sowohl öffentliche als auch private Optionen bieten ähnliche Leistungsgewinne, aber jede bietet eindeutige Attribute und Vorteile. Weitere Informationen zu öffentlichen und privaten CDN finden Sie unter [Choose whether each origin should be public or private](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate).

## <a name="how-to-enable-public-and-private-cdn-with-the-default-configuration"></a>Aktivieren von öffentlichen und privaten CDN mit der Standardkonfiguration
Bevor Sie Änderungen an den Mandanteneinstellungen CDN, sollten Sie überprüfen, ob sie den Compliance-, Sicherheits- und Datenschutzrichtlinien Ihrer Organisation entspricht.

Ausführlichere Konfigurationseinstellungen oder wenn Sie CDN bereits aktiviert haben und zusätzliche Speicherorte (Ursprünge) hinzufügen möchten, finden Sie im Abschnitt Einrichten und Konfigurieren der Office 365 CDN mithilfe der [SharePoint Online-Verwaltungsshell.](use-microsoft-365-cdn-with-spo.md#set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell)

Verbinden sie mithilfe der SharePoint Online-Verwaltungsshell an Ihren Mandanten:

```PowerShell
Connect-SPOService -Url https://<YourTenantName>-admin.sharepoint.com
```

Geben Sie den folgenden Befehl ein, damit Ihre Organisation sowohl öffentliche als auch private Ursprünge mit der Standardkonfiguration verwenden kann:

```PowerShell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

Die Ausgabe dieser Cmdlets sollte wie folgt aussehen:

![Ausgabe von Set-SPOTenantCdnEnabled](../media/O365-CDN/o365-cdn-enable-output.png)

## <a name="see-also"></a>Siehe auch

[Verwenden des Tools "Seitendiagnose" für SharePoint Online](./page-diagnostics-for-spo.md)

[Verwenden des Office 365 Content Delivery Network (CDN) mit SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Netzwerke für die Inhaltsübermittlung](./content-delivery-networks.md)

[Netzwerkplanung und Leistungsoptimierung für Office 365](./network-planning-and-performance.md)

[SharePoint Leistungsserie – Office 365 CDN Videoreihe](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)