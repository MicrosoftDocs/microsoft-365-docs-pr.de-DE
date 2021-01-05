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
description: Wenn eine Depotbank einem erweiterten eDiscovery-Fall hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert betrachtet wurden, erneut verarbeitet, damit Sie vollständig durchsuchbar sind.
ms.openlocfilehash: 908d01cacc103639e1f9efe965240c33a5296ba9
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49750756"
---
# <a name="advanced-indexing-of-custodian-data"></a>Erweiterte Indizierung der Daten von Verwaltungsberechtigten

Wenn eine Depotbank einem erweiterten eDiscovery-Fall hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert betrachtet wurden, erneut verarbeitet, damit Sie vollständig durchsuchbar sind.  Dieser Vorgang wird als *Erweiterte Indizierung* bezeichnet. Inhalt kann teilweise aus einer Reihe von Gründen indiziert werden, einschließlich des Vorhandenseins von Bildern, nicht unterstützten Dateitypen oder beim Indizieren von Dateigrößenbeschränkungen.

Weitere Informationen zur Verarbeitung von Unterstützung und teilweise indizierten Elementen finden Sie unter:

- [Unterstützte Dateitypen in Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [Teilweise indizierte Elemente in der Inhaltssuche in Office 365](partially-indexed-items-in-content-search.md)

- [Von der Exchange-Suche indizierte Dateiformate](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Anzeigen erweiterter Indizierungs Ergebnisse

Nachdem der erweiterte Indizierungsprozess abgeschlossen ist, können Sie ein Verständnis der Effektivität der erneuten Verarbeitung erhalten.  In der Ansicht Erweiterte Indizierungs Ergebnisse auf der Registerkarte **Verarbeitung** für einen Fall wird im Diagramm die Anzahl der Elemente aufgeführt, die dem *Hybrid Index* hinzugefügt werden.  Der Hybrid Index ist der Ort, an dem Advanced eDiscovery die wiederaufgearbeiteten Inhalte speichert.

Diese Ansicht enthält auch die Anzahl der Elemente, die eine Korrektur erfordern, und ein weiteres Diagramm mit Fehlern nach Dateityp. Weitere Informationen finden Sie unter:

- [Beheben von Fehlern beim Verarbeiten von Daten](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Korrektur von Fehlern einzelner Elemente](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Aktualisieren des erweiterten Index für depotverwalter

Wenn eine Depotstelle einem erweiterten eDiscovery-Fall hinzugefügt wird, werden alle teilweise indizierten Elemente neu verarbeitet. Im Laufe der Zeit werden dem Postfach eines Benutzers oder dem OneDrive-Konto jedoch möglicherweise mehr teilweise indizierte Elemente hinzugefügt.  Bei Bedarf können Sie den Index für eine bestimmte Depotbank aktualisieren. Weitere Informationen finden Sie unter [Manage depotbanks in a Advanced eDiscovery Case](manage-new-custodians.md#re-index-custodian-data). Sie können den Index für alle Verwalter in einem Fall auch aktualisieren, indem Sie auf der Registerkarte **Verarbeitung** auf den **Index aktualisieren** klicken.

> [!NOTE]
> Das Aktualisieren von Depot Indizes ist ein langwieriger Prozess. Es wird empfohlen, dass Sie Indizes nicht mehr als einmal pro Tag in einem Fall aktualisieren.
