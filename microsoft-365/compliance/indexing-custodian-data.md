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
description: Wenn ein Verwahrer zu einem Advanced eDiscovery Fall hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert eingestuft wurden, erneut verarbeitet, um sie vollständig durchsuchbar zu machen.
ms.openlocfilehash: 34855eb168dd10fc500e2e57fe1d57ad81449452
ms.sourcegitcommit: 2fd60871975d61e60d4827b36cd689021fd2a4c8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53437976"
---
# <a name="advanced-indexing-of-custodian-data"></a>Erweiterte Indizierung der Daten von Verwaltungsberechtigten

Wenn ein Verwahrer zu einem Advanced eDiscovery Fall hinzugefügt wird, werden alle Inhalte, die als teilweise indiziert betrachtet wurden oder mit denen Indizierungsfehler aufgetreten sind, neu indiziert, um sie vollständig durchsuchbar zu machen.  Dieser Neuindizierungsprozess wird als *erweiterte Indizierung* bezeichnet. Es gibt eine Reihe von Gründen, warum Inhalte teilweise indiziert werden oder Indizierungsfehler aufweisen. Dazu gehören Bilddateien oder das Vorhandensein von Bildern in einer Datei, nicht unterstützte Dateitypen oder Indizierungsgrenzwerte für die Dateigröße. Bei SharePoint Dateien wird die erweiterte Indizierung nur für Elemente ausgeführt, die als teilweise indiziert gekennzeichnet sind oder die Indizierungsfehler aufweisen. In Exchange werden E-Mail-Nachrichten mit Bildanlagen nicht als teilweise indiziert oder mit Indizierungsfehlern gekennzeichnet. Dies bedeutet, dass diese Dateien nicht vom erweiterten Indizierungsprozess neu indiziert werden.

Weitere Informationen zur Verarbeitungsunterstützung und teilweise indizierten Elementen finden Sie unter:

- [Unterstützte Dateitypen in Advanced eDiscovery](supported-filetypes-ediscovery20.md)

- [Teilweise indizierte Elemente in der Inhaltssuche in Office 365](partially-indexed-items-in-content-search.md)

- [Von der Exchange-Suche indizierte Dateiformate](/exchange/file-formats-indexed-by-exchange-search-exchange-2013-help)

- [Standardmäßig durchforstete Dateinamenerweiterungen und analysierte Dateitypen in SharePoint Server](/SharePoint/technical-reference/default-crawled-file-name-extensions-and-parsed-file-types)

## <a name="viewing-advanced-indexing-results"></a>Anzeigen erweiterter Indizierungsergebnisse

Nachdem der Prozess der erweiterten Indizierung abgeschlossen ist, können Sie die Effektivität der Erneutverarbeitung verstehen.  In der Ansicht "Erweiterte Indizierungsergebnisse" auf der Registerkarte **"Verarbeitung"** für einen Fall listet das Diagramm die Anzahl der Elemente auf, die dem *Hybridindex* hinzugefügt wurden.  Im Hybridindex speichert Advanced eDiscovery den erneut verarbeiteten Inhalt.

Diese Ansicht enthält auch die Anzahl der Elemente, die eine Korrektur erfordern, und ein weiteres Diagramm von Fehlern nach Dateityp. Weitere Informationen finden Sie unter:

- [Beheben von Fehlern beim Verarbeiten von Daten](error-remediation-when-processing-data-in-advanced-ediscovery.md)

- [Korrektur von Fehlern einzelner Elemente](single-item-error-remediation.md)

## <a name="updating-the-advanced-index-for-custodians"></a>Aktualisieren des erweiterten Index für Verwahrer

Wenn ein Verwahrer zu einem Advanced eDiscovery Fall hinzugefügt wird, werden alle teilweise indizierten Elemente erneut verarbeitet. Wenn die Zeit vergeht, können jedoch mehr teilweise indizierte Elemente zum Postfach oder OneDrive Konto eines Benutzers hinzugefügt werden.  Bei Bedarf können Sie den Index für einen bestimmten Verwahrer aktualisieren. Weitere Informationen finden Sie unter [Verwalten von Verwaltern in einem Advanced eDiscovery Fall.](manage-new-custodians.md#re-index-custodian-data) Sie können den Index für alle Verwahrer in einem Fall auch aktualisieren, indem Sie auf der Registerkarte **"Verarbeitung"** auf den **Index aktualisieren** klicken.

> [!NOTE]
> Das Aktualisieren von Verwahrungsindizes ist ein langer Prozess. Es wird empfohlen, indizes nicht mehr als einmal pro Tag in einem Fall zu aktualisieren.
