---
title: Erweiterte Indizierung der Daten von Verwaltungsberechtigten
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
description: ''
ms.openlocfilehash: a6259d839dd9a0ca196bae37afe374d1d8f21d53
ms.sourcegitcommit: f0a4290793e296474ecd3c6eb0ca96eae7faa434
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/11/2019
ms.locfileid: "38686153"
---
# <a name="advanced-indexing-of-custodian-data"></a>Erweiterte Indizierung der Daten von Verwaltungsberechtigten

Wenn eine Depotbank einem erweiterten eDiscovery-Fall hinzugefügt wird, werden alle Inhalte in Office 365, die als teilweise indiziert betrachtet wurden, erneut verarbeitet, damit Sie vollständig durchsuchbar sind.  Dieser Vorgang wird als *Erweiterte Indizierung*bezeichnet. Inhalt kann teilweise aus einer Reihe von Gründen indiziert werden, einschließlich des Vorhandenseins von Bildern, nicht unterstützten Dateitypen oder beim Indizieren von Dateigrößenbeschränkungen.

Weitere Informationen zur Verarbeitungsunterstützung in Office 365 und teilweise indizierten Elementen finden Sie unter:

- [Unterstützte Dateitypen in Advanced eDiscovery](supported-filetypes-ediscovery20.md)
- [Teilweise indizierte Elemente in der Inhaltssuche in Office 365](partially-indexed-items-in-content-search.md)
- [Von der Exchange-Suche indizierte Dateiformate](https://docs.microsoft.com/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)
- [Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](https://docs.microsoft.com/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Anzeigen erweiterter Indizierungs Ergebnisse

Nachdem der erweiterte Indizierungsprozess abgeschlossen ist, können Sie ein Verständnis der Effektivität der erneuten Verarbeitung erhalten.  In der Ansicht Depot Indizierung werden im Diagramm alle Elemente aufgeführt, die dem *Hybrid Index*hinzugefügt wurden.  Der Hybrid Index ist der Ort, an dem Advanced eDiscovery den erneut verarbeiteten Inhalt speichert.

Das Diagramm enthält auch die Anzahl der Elemente, die eine Korrektur erfordern, und ein weiteres Diagramm mit Fehlern nach Dateityp. Weitere Informationen finden Sie unter:

- [Beheben von Fehlern beim Verarbeiten von Daten](error-remediation.md)
- [Korrektur von Fehlern einzelner Elemente](single-item-error-remediation.md)

## <a name="updating-advanced-indexes-for-custodians"></a>Aktualisieren erweiterter Indizes für depotverwalter

Wenn eine Depotstelle einem erweiterten eDiscovery-Fall hinzugefügt wird, werden alle teilweise indizierten Elemente erneut verarbeitet. Im Laufe der Zeit werden dem Postfach eines Benutzers oder dem OneDrive-Konto jedoch möglicherweise mehr teilweise indizierte Elemente hinzugefügt.  Bei Bedarf können Sie die Indizes aktualisieren.

> [!NOTE]
> Das Aktualisieren von Depot Indizes ist ein langwieriger Prozess. Es wird empfohlen, die Indizes in einem Fall nicht mehr als einmal pro Tag zu aktualisieren.
