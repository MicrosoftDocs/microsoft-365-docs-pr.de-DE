---
title: Analysieren von Daten in einer Überprüfungsgruppe in Advanced eDiscovery
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
description: Erfahren Sie mehr über die Tools, die zum Organisieren von Dokumentenmappen bei der Analyse eines erweiterten eDiscovery-falls verfügbar sind.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 87788e444a5ef671586567510448dab8b9deddcd
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44033819"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Analysieren von Daten in einer Überprüfungsgruppe in Advanced eDiscovery

Wenn die Anzahl der gesammelten Dokumente groß ist, kann es schwierig sein, Sie alle zu überprüfen. Advanced eDiscovery stellt eine Reihe von Tools zum Analysieren der Dokumente zur Verfügung, um das Volumen von Dokumenten zu reduzieren, die ohne Verlust von Informationen überprüft werden sollen, und um Ihnen dabei zu helfen, die Dokumente auf kohärente Weise zu organisieren. Weitere Informationen zu diesen Funktionen finden Sie unter:

- [Erkennen von Quasiduplikaten](near-duplicates.md)

- [E-Mail-Threading](email-threading.md)

- [Designs](themes.md)

So analysieren Sie Daten in einem Überprüfungs Satzes:

1. Konfigurieren Sie die Analyse Einstellungen für Ihren Fall. Weitere Informationen finden Sie unter [Configure Search and Analytics Settings](configure-search-analytics-settings.md).

2. Öffnen Sie den Überprüfungs Satzes, den Sie analysieren möchten.

3. Klicken Sie auf **Überprüfungs Sätze verwalten**.

4. Klicken Sie auf **Analyse für die Überprüfungsgruppe ausführen**.

Sie können den Fortschritt der Analyse auf der Registerkarte **Aufträge** der Anfrage überprüfen.

 Nachdem die Analyse abgeschlossen ist, können Sie den Analysebericht anzeigen, Abfragen in ihrer Überprüfung ausführen, die auf Ausgaben der Analyse festgelegt sind (siehe [Abfrage innerhalb des Überprüfungs Satzes](review-set-search.md)) und verwandte Dokumente eines bestimmten Dokuments anzeigen (siehe Überprüfen von [Daten im](reviewing-data-in-review-set.md)Überprüfungs).

## <a name="analytics-report"></a>Analysebericht

So zeigen Sie einen Analysebericht für eine Überprüfungsgruppe an:

1. Öffnen Sie den Überprüfungs-Datensatz.

2. Klicken Sie auf **Überprüfungs Sätze verwalten**.

3. Klicken Sie auf **Bericht anzeigen**.

Der Bericht enthält sieben Komponenten aus der Analyse:

- **Zielpopulation:** Die Anzahl von e-Mail-Nachrichten, Anlagen und losen Dokumenten, die im Überprüfungs Satz gefunden wurden.

- **Dokumente (ohne Anlagen):** Die Anzahl von losen Dokumenten, die Pivots sind, eindeutig nahe Duplikate eines Pivot-Elements oder ein exaktes Duplikat eines anderen Dokuments.

- **E-Mails:** Die Anzahl der e-Mail-Nachrichten, die inklusive, einschließlich Kopien, einschließlich minus oder keine der oben genannten sind.

- **Anlagen:** Die Anzahl der eindeutigen e-Mail-Anlagen oder Duplikate einer anderen e-Mail-Anlage in der Überprüfungsgruppe.

- **Anzahl der Dateien nach Typ:** Die Anzahl der Dateien, die durch die Dateierweiterung identifiziert werden.

- **Dokumente nach Quelle:** Eine Zusammenfassung des Inhalts anhand der ursprünglichen Datenquelle.

- **Nach Prozess aggregierte Dokumente:** Eine Zusammenfassung der Inhalte durch Review-Prozess festlegen. 
