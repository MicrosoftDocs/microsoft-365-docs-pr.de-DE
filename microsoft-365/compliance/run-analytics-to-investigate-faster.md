---
title: Durchführen von Analysen zur schnelleren Untersuchung
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
description: In diesem Artikel erfahren Sie, wie Sie analytische Tools wie die Erkennung von Duplikaten, e-Mail-Threads und Designs verwenden, um Ihre Untersuchungen zu beschleunigen.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e7c5103adabadf88028351f0314bcdfaa2cd4d0f
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035847"
---
# <a name="run-analytics-to-investigate-faster"></a>Durchführen von Analysen zur schnelleren Untersuchung

Wenn eine Beweissammlung groß ist, kann es schwierig sein, Sie alle zu überprüfen. Eine Reihe von beweisen umfasst häufig mehrere Kopien derselben oder ähnlicher e-Mail-Nachrichten oder Dokumente. Data Investigations (Preview) enthält eine Reihe von Analysetools, mit denen Sie das Volumen von Dokumenten reduzieren können, die ohne Verlust von Informationen überprüft werden müssen. Weitere Informationen zu diesen Funktionen finden Sie unter:

- [Erkennen von Quasiduplikaten](near-duplicates.md)

- [E-Mail-Threading](email-threading.md)

- [Designs](themes.md)

So analysieren Sie Daten in einem Beweis Sätze:

1. Konfigurieren Sie die Analyse Einstellungen für Ihre Untersuchung. Weitere Informationen finden Sie unter [Configure Search and Analytics Settings](configure-search-analytics-settings.md).

2. Öffnen Sie den Beweis Sätze.

3. Klicken Sie auf **Evidence verwalten**.

4. Klicken Sie unter **Analyse**auf **analysieren**.

Sie können den Fortschritt der Analyse auf der Registerkarte **Aufträge** in ihrer Untersuchung überprüfen. Der angestoßene Auftragstyp wird als **Running Analytics**bezeichnet.

 Nachdem die Analyse abgeschlossen ist, wird eine Liste der genauen Duplikate oder nahe Duplikate des Dokuments angezeigt, das Sie im Bereich auf der rechten Seite überprüft haben. Wenn Sie alle Duplikate des Dokuments auswählen möchten, das Sie gerade anzeigen, können Sie dies ganz einfach mithilfe dieses Bereichs tun. Weitere Informationen zu anderen Features in diesem Bereich finden Sie unter [Überprüfen von Daten in Evidence](review-data-in-evidence.md). 

Sie können auch zusätzliche Abfragen innerhalb ihrer Beweise ausführen, indem Sie die Ergebnisse der Analyse wie Designs verwenden. Weitere Informationen finden Sie unter [Abfragen der Daten in Evidence](evidence-query.md).

## <a name="analytics-report"></a>Analysebericht

So zeigen Sie einen Analysebericht für Ihre Beweise an:

1. Öffnen Sie den Beweis Sätze.

2. Klicken Sie auf **Evidence verwalten**.

3. Klicken Sie unter **Analyse**auf **Bericht anzeigen**.

Der Bericht enthält vier Komponenten aus der Analyse:

- **Aufschlüsselung** – die Anzahl der unformatierten e-Mails, Anlagen und Dokumente, die im Beweissatz gefunden wurden.

- **E-Mails** -die Anzahl von eamil-Nachrichten, die inklusive, einschließlich minus, inklusiver Kopien oder keiner der oben genannten sind.
   - Inclusives: die letzte Nachricht im e-Mail-Thread, die den gesamten vorherigen Verlauf enthält und eine Überprüfung erfordert.
   - Inclusive minus: die Nachricht im Thread, die eine oder mehrere unterschiedliche Anlagen enthält, für die eine Überprüfung erforderlich ist.
   - Inklusive Kopien: die Nachricht, bei der es sich um eine Kopie einer anderen inklusiven oder inklusiven minus Nachricht (Betreff und Text) handelt.

- **Attachments** : die Anzahl der eindeutigen e-Mail-Anlagen oder Duplikate einer anderen e-Mail-Anlage innerhalb desselben Nachweises.

- **Dokumente (mit Ausnahme von e-Mail-Anlagen)** – die Anzahl der eindeutigen Dokumente, die überprüft werden müssen, beispielsweise das repräsentativste Dokument der Gruppe mit Nahem Duplikat oder ein exaktes Duplikat eines anderen Dokuments).
