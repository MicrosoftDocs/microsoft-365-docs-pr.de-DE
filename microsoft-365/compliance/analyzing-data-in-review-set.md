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
description: ''
ms.openlocfilehash: 5705edcc4015460a8c6c5a2edc6ebf922dabbb2f
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2020
ms.locfileid: "41596152"
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

Der Bericht enthält vier Komponenten aus der Analyse:

- **Aufschlüsselung** – wie viele e-Mail-Nachrichten, Anlagen und lose Dokumente wurden im Überprüfungs Satz gefunden.

- **Dokumente (ohne Anlagen)** – wie viele Lose Dokumente waren Pivots, eindeutig in der Nähe von Duplikaten eines Pivots oder ein exaktes Duplikat eines anderen Dokuments.

- **E-Mails** -wie viele e-Mail-Nachrichten inklusive, einschließlich Kopien, einschließlich minus oder keines der oben genannten waren.

- **Attachments** -wie viele e-Mail-Anlagen wurden eindeutig oder Duplikate einer anderen e-Mail-Anlage in der Überprüfungsgruppe.