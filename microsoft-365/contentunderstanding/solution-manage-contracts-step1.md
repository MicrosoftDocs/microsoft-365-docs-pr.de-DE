---
title: Schritt 1. Verwenden SharePoint Syntex zum Identifizieren von Vertragsdateien und Extrahieren von Daten
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: 05/10/2021
ms.prod: microsoft-365-enterprise
search.appverid: ''
localization_priority: None
ROBOTS: NOINDEX, NOFOLLOW
description: Erfahren Sie, wie Sie SharePoint Syntex verwenden, um Vertragsdateien zu identifizieren und Daten mithilfe einer Microsoft 365 extrahieren.
ms.openlocfilehash: e0d58164d1a12987a4606ef84c15fa3d20c0195f
ms.sourcegitcommit: 8e4c107e4da3a00be0511b05bc655a98fe871a54
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52281213"
---
# <a name="step-1-use-sharepoint-syntex-to-identify-contract-files-and-extract-data"></a>Schritt 1. Verwenden SharePoint Syntex zum Identifizieren von Vertragsdateien und Extrahieren von Daten

Ihre Organisation benötigt eine Möglichkeit, alle Vertragsdokumente aus den vielen empfangenen Dateien zu identifizieren und zu klassifizieren. Sie möchten auch in der Lage sein, schnell mehrere Schlüsselelemente in jeder der identifizierten Vertragsdateien (z. B. *Client,* *Auftragnehmer* und *Gebührenbetrag) anzeigen zu können.* Verwenden Sie dazu SharePoint [Syntex,](index.md) um ein Dokumentverständnismodell zu erstellen und es auf eine Dokumentbibliothek zu anwenden.

[Zur Dokumenterteilung](document-understanding-overview.md) werden KI-Modelle (Artificial Intelligence) verwendet, um die Klassifizierung von Dateien und die Extraktion von Informationen zu automatisieren. Dokumentverständnismodelle sind auch optimal beim Extrahieren von Informationen aus unstrukturierten und semistrukturierten Dokumenten, bei denen die benötigten Informationen nicht in Tabellen oder Formularen enthalten sind, z. B. Verträgen.

1. Zunächst müssen Sie mindestens fünf Beispieldateien finden, mit deren Hilfe Sie das Modell "schulen" können, um nach Merkmalen zu suchen, die spezifisch für den Inhaltstyp sind, den Sie identifizieren möchten (ein Vertrag). 

2. Erstellen SharePoint Syntex ein neues Dokumentverständnismodell. Mithilfe Ihrer Beispieldateien müssen Sie [einen Klassifikator erstellen.](create-a-classifier.md) Indem Sie den Klassifikator mit Ihren Beispieldateien trainieren, vermitteln Sie ihm, nach Merkmalen zu suchen, die speziell für die Verträge Ihres Unternehmens spezifisch sind. Erstellen Sie beispielsweise [eine "Erläuterung",](create-a-classifier.md#create-an-explanation) die nach bestimmten Zeichenfolgen in Ihren Verträgen sucht, z. B. *Servicevertrag,* Vertragsbedingungen *und* *Vergütung.* Sie können Ihre Erklärung sogar so schulen, dass sie in bestimmten Abschnitten des Dokuments oder neben anderen Zeichenfolgen nach diesen Zeichenfolgen sucht. Wenn Sie denken, Dass Sie Ihren Klassifikator mit den benötigten Informationen geschult haben, können Sie Ihr Modell in einem Beispielsatz von Beispieldateien testen, um zu sehen, wie effizient es ist. Nach dem Testen können Sie bei Bedarf Änderungen an Ihren Erläuterungen vornehmen, um sie effizienter zu gestalten. 

3. In Ihrem Modell können Sie einen [Extractor](create-an-extractor.md) erstellen, um bestimmte Datenteile aus jedem Vertrag herausziehen zu können. Für jeden Vertrag sind z. B. die Informationen, über die Sie sich am meisten Gedanken machen, wer der Kunde ist, der Name des Auftragnehmers und die Gesamtkosten.

4. Nachdem Sie ihr Modell erfolgreich erstellt haben, wenden Sie es auf [eine SharePoint Dokumentbibliothek an.](apply-a-model.md) Beim Hochladen von Dokumenten in die Dokumentbibliothek wird Ihr Dokumentverständnismodell ausgeführt und identifiziert und klassifiziert alle Dateien, die dem vertragsinhaltstyp entsprechen, den Sie in Ihrem Modell definiert haben. Alle Als Verträge klassifizierten Dateien werden in einer benutzerdefinierten Bibliotheksansicht angezeigt. Die Dateien zeigen auch die Werte aus jedem Vertrag an, den Sie in Ihrem Extractor definiert haben.

   ![Verträge in der Dokumentbibliothek](../media/content-understanding/doc-lib-solution.png)

5. Wenn Sie Aufbewahrungsanforderungen für Ihre Verträge haben, können [](apply-a-retention-label-to-a-model.md) Sie ihr Modell auch verwenden, um eine Aufbewahrungsbezeichnung anzuwenden, die verhindert, dass Ihre Verträge für einen bestimmten Zeitraum gelöscht werden.

## <a name="next-step"></a>Nächster Schritt

[Schritt 2. Erstellen Microsoft Teams Vertragsverwaltungskanals mithilfe von Microsoft Teams](solution-manage-contracts-step2.md)