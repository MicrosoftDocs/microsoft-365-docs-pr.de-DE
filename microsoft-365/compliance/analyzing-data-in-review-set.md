---
title: Analysieren von Daten in einem Überprüfungssatz in Advanced eDiscovery
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
description: Erfahren Sie mehr über die Tools, die zum Organisieren von Dokumentsätzen bei der Analyse eines Advanced eDiscovery sind.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 7c63e7eca2e032bfa11c4d4e6f961bb7a7700a4e
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751370"
---
# <a name="analyze-data-in-a-review-set-in-advanced-ediscovery"></a>Analysieren von Daten in einem Überprüfungssatz in Advanced eDiscovery

Wenn die Anzahl der gesammelten Dokumente groß ist, kann es schwierig sein, sie alle zu überprüfen. Advanced eDiscovery bietet eine Reihe von Tools, um die Dokumente zu analysieren, um die Menge der zu überprüfenden Dokumente ohne Informationsverlust zu reduzieren und ihnen bei der zusammenhängenden Organisation der Dokumente zu helfen. Weitere Informationen zu diesen Funktionen finden Sie unter:

- [Erkennen von Quasiduplikaten](near-duplicate-detection-in-advanced-ediscovery.md)

- [E-Mail-Threading](email-threading-in-advanced-ediscovery.md)

- [Designs](themes-in-advanced-ediscovery.md)

So analysieren Sie Daten in einem Überprüfungssatz:

1. Konfigurieren Sie die Analyseeinstellungen für Ihren Fall. Weitere Informationen finden Sie unter [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md).

2. Öffnen Sie den Zu analysierenden Überprüfungssatz.

3. Klicken **Sie auf Überprüfungssatz verwalten.**

4. Klicken **Sie auf Analyse für den Überprüfungssatz ausführen.**

Sie können den Fortschritt der Analyse auf der Registerkarte **Aufträge** des Falls überprüfen.

 Nachdem die Analyse abgeschlossen ist, können Sie den Analysebericht anzeigen, Abfragen in Ihrem Überprüfungssatz für Ausgaben der Analyse ausführen (siehe Abfrage innerhalb des Überprüfungssatz [),](review-set-search.md)und verwandte Dokumente eines bestimmten Dokuments anzeigen (siehe Überprüfen von Daten [im](reviewing-data-in-review-set.md)Überprüfungssatz ).

## <a name="analytics-report"></a>Analysebericht

So zeigen Sie einen Analysebericht für einen Überprüfungssatz an:

1. Öffnen Sie den Überprüfungssatz.

2. Klicken **Sie auf Überprüfungssatz verwalten.**

3. Klicken Sie **auf Bericht anzeigen**.

Der Bericht enthält sieben Komponenten aus der Analyse:

- **Zielgesamtheit:** Die Anzahl der E-Mail-Nachrichten, Anlagen und lose Dokumente, die im Überprüfungssatz gefunden wurden.

- **Dokumente (ohne Anlagen):** Die Anzahl der lose Dokumente, die Pivots sind, eindeutige Beinaheduplikate eines Pivots oder ein genaues Duplikat eines anderen Dokuments.

- **E-Mails:** Die Anzahl der E-Mail-Nachrichten, die inklusiv sind, einschließlich Kopien, inklusive Minuszeichen oder keine der oben genannten.

- **Anlagen:** Die Anzahl der E-Mail-Anlagen, die eindeutig oder Duplikate einer anderen E-Mail-Anlage im Überprüfungssatz sind.

- **Anzahl der Dateien nach Typ:** Die Anzahl der Dateien, die durch die Dateierweiterung identifiziert werden.

- **Dokumente nach Quelle:** Eine Zusammenfassung des Inhalts nach der ursprünglichen Datenquelle.

- **Nach Prozess aggregierte Dokumente:** Eine Zusammenfassung der Inhalte nach Überprüfungssatzprozessen. 
