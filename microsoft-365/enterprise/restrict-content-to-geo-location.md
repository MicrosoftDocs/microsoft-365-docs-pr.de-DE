---
title: Einschränken der SharePoint-Websiteinhalte auf einen geografischen Standort
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection: Strat_SP_gtc
localization_priority: Normal
description: In diesem Artikel erfahren Sie, wie SharePoint auf einen angegebenen geografischen Standort in einer Multi-Geo-Umgebung beschränkt werden.
ms.openlocfilehash: 74255db19b2ecf9b333d33208c63da260b2bd747
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927264"
---
# <a name="restrict-sharepoint-site-content-to-a-geo-location"></a>Einschränken der SharePoint-Websiteinhalte auf einen geografischen Standort

Unter bestimmten Umständen können Sie möglicherweise erzwingen, dass eine Seite und Ihre Inhalte an dem geographischen Standort verbleiben, an dem Sie erstellt wurden. Dies ist möglich, indem Sie entweder die Seite daran hindern, verschoben zu werden, oder indem Sie das Zwischenspeichern der Dateiinhalte der Seite an einem anderen geographischen Standort verhindern.

Um dies zu tun, verwenden Sie [Set-SPOSite](/powershell/module/sharepoint-online/set-sposite) cmdlet mit dem Parameter **RestrictedToGeo**. Dieser Parameter hat einen Standardwert von NULL, aber Sie können ihn wie folgt ändern:

|Einschränkung|Beschreibung|
|:----------|:----------|
|NoRestriction|Die Website kann an einen anderen Geo-Standort verschoben werden.|
|BlockMoveOnly|Seite kann nicht an einen anderen Geo-Standort verschoben werden, aber Seiteninhalte können an einem anderen geografischen Standort zwischengespeichert werden.|
|BlockFull|Seite kann nicht an einen anderen Geo-Standort verschoben werden und der gesamte Seiteninhalt wird nicht an anderen geografischen Standorten zwischengespeichert. Der Titel der Datei (aus dem Inhalt abgerufen), der Dateiname und andere Eigenschaften der Datei können weiterhin an anderen geographischen Standorten zwischengespeichert werden.<br>Inhalte, die vor der Konfiguration als BlockFull auf der Seite gespeichert wurden, können möglicherweise weiterhin an anderen geographischen Standorten zwischengespeichert werden.|

Verwenden Sie die folgende Syntax:

`Set-SPOSite -Identity <siteURL> -RestrictedToGeo <restriction>`

Beispiel:

`Set-SPOSite -Identity https://contoso.sharepoint.com/sites/RegionRestrictedTeamSite -RestrictedToGeo BlockFull`