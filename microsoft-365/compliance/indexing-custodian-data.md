---
title: Erweiterte Indizierung der Daten von Verwaltungsberechtigten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Wenn einem Advanced eDiscovery-Fall ein Verwahrer hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert betrachtet wurden, erneut verarbeitet, um sie vollständig durchsuchbar zu machen.
ms.openlocfilehash: 904c8fe626ce8ece8f4b48bd5504e4011e9f4fb2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911209"
---
# <a name="advanced-indexing-of-custodian-data"></a>Erweiterte Indizierung der Daten von Verwaltungsberechtigten

Wenn einem Advanced eDiscovery-Fall ein Verwahrer hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert betrachtet wurden, erneut verarbeitet, um sie vollständig durchsuchbar zu machen.  Dieser Prozess wird als *Erweiterte Indizierung bezeichnet.* Inhalte können aus einer Reihe von Gründen teilweise indiziert werden, z. B. aus dem Vorhandensein von Bildern, nicht unterstützten Dateitypen oder beim Indizierung von Dateigrößenbeschränkungen.

Weitere Informationen zur Verarbeitung von Support und teilweise indizierten Elementen finden Sie unter:

- [Unterstützte Dateitypen in Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [Teilweise indizierte Elemente in der Inhaltssuche in Office 365](partially-indexed-items-in-content-search.md)

- [Von der Exchange-Suche indizierte Dateiformate](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Anzeigen erweiterter Indizierungsergebnisse

Nachdem der Erweiterte Indizierungsprozess abgeschlossen ist, können Sie sich ein Verständnis der Effektivität der Neuverarbeitung machen.  In der Ansicht Erweiterte Indizierungsergebnisse auf der Registerkarte **Verarbeitung** für einen Fall listet das Diagramm die Anzahl der Elemente auf, die dem *Hybridindex hinzugefügt wurden.*  Im Hybridindex speichert Advanced eDiscovery den erneut verarbeiteten Inhalt.

Diese Ansicht enthält auch die Anzahl der Elemente, die eine Korrektur erfordern, und ein weiteres Diagramm mit Fehlern nach Dateityp. Weitere Informationen finden Sie unter:

- [Beheben von Fehlern beim Verarbeiten von Daten](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Korrektur von Fehlern einzelner Elemente](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Aktualisieren des erweiterten Indexes für Verwahrer

Wenn einem Advanced eDiscovery-Fall ein Verwahrer hinzugefügt wird, werden alle teilweise indizierten Elemente erneut verarbeitet. Im Weiteren können jedoch dem Postfach oder #A0 eines Benutzers teilweise indizierte Elemente hinzugefügt werden.  Bei Bedarf können Sie den Index für bestimmte Verwahrer aktualisieren. Weitere Informationen finden Sie [unter Manage custodians in an Advanced eDiscovery case](manage-new-custodians.md#re-index-custodian-data). Sie können den Index auch für alle Custodians in einem Fall aktualisieren, indem Sie auf der Registerkarte Verarbeitung auf den **Index** Aktualisieren **klicken.**

> [!NOTE]
> Das Aktualisieren von Indizes für Custodian ist ein langer Prozess. Es wird empfohlen, Indizes in einem Fall nicht mehr als einmal täglich zu aktualisieren.