---
title: Abfragen der Daten in einem Prüfdateisatz
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Erfahren Sie, wie Sie eine Abfrage in einem Überprüfungssatz erstellen und ausführen, um Daten für eine effizientere Überprüfung in einem Advanced eDiscovery organisieren.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 5a03b0c863f9cc2050b18ce83ed11b8a71d1db4d
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345800"
---
# <a name="query-the-data-in-a-review-set"></a>Abfragen der Daten in einem Prüfdateisatz

In den meisten Fällen ist es hilfreich, sich tiefer in die Daten in einem Überprüfungssatz zu vertiefen und diese Daten zu organisieren, um eine effizientere Überprüfung zu ermöglichen. Die Verwendung von Abfragen in einem Überprüfungssatz hilft Ihnen, sich auf eine Teilmenge von Dokumenten zu konzentrieren, die die Kriterien Ihrer Überprüfung erfüllen.

## <a name="creating-and-running-a-query-in-a-review-set"></a>Erstellen und Ausführen einer Abfrage in einem Überprüfungssatz

Wenn Sie eine Abfrage für die Dokumente in einem Überprüfungssatz erstellen und ausführen möchten, wählen Sie im Überprüfungssatz **Neue** Abfrage aus. Nachdem Sie die Abfrage benennen und die Bedingungen definiert haben, wählen Sie **Speichern** aus, um die Abfrage zu speichern und ausführen. Wählen Sie zum Ausführen einer zuvor gespeicherten Abfrage eine gespeicherte Abfrage aus.

![Überprüfen von Satzabfragen](../media/AeDReviewSetQueries.png)

## <a name="building-a-review-set-query"></a>Erstellen einer Überprüfungssatzabfrage

Sie können eine Abfrage mithilfe einer Kombination aus Schlüsselwörtern, Eigenschaften und Bedingungen in der Keywords-Bedingung erstellen. Sie können Bedingungen auch als Block gruppieren (als *Bedingungsgruppe* bezeichnet), um eine komplexere Abfrage zu erstellen. Eine Liste und Beschreibung der Metadaten-Eigenschaften, die Sie durchsuchen können, finden Sie unter [Dokumentmetadatenfeldern in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

### <a name="conditions"></a>Bedingungen

Jedes durchsuchbare Feld in einem Überprüfungssatz hat eine entsprechende Bedingung, die Sie zum Erstellen ihrer Abfrage verwenden können.

Es gibt mehrere Arten von Bedingungen:

- Freetext: Eine Freetextbedingung wird für Textfelder wie betreff verwendet. Sie können mehrere Suchbegriffe auflisten, indem Sie sie durch ein Komma trennen.

- Date: Eine Datumsbedingung wird für Datumsfelder wie das Datum der letzten Änderung verwendet.

- Suchoptionen: Eine Suchoptionenbedingung enthält eine Liste der möglichen Werte für das bestimmte Feld in Ihrem Überprüfungssatz. Dies wird für Felder verwendet, z. B. Absender, bei denen eine begrenzte Anzahl möglicher Werte in Ihrem Überprüfungssatz enthalten ist.

- Schlüsselwort: Eine Schlüsselwortbedingung ist eine bestimmte Instanz von Freetextbedingung, die Sie zum Suchen nach Begriffen oder verwenden KQL- like query language in verwenden können. Weitere Informationen finden Sie unten.

### <a name="query-language"></a>Abfragesprache

Zusätzlich zu den Bedingungen können Sie eine KQL- like query language in der Keywords-Bedingung verwenden, um Ihre Abfrage zu erstellen. Die Abfragesprache für Überprüfungssatzabfragen unterstützt standardmäßige boolesche Operatoren, z. B. **AND**, **OR**, **NOT** und **NEAR**. Es unterstützt auch einen einstelligen Platzhalter (?) und einen mehrstelligen Platzhalter (*).

## <a name="filters"></a>Filter

Zusätzlich zu den Abfragen, die Sie speichern können, können Sie Mithilfe von Überprüfungssatzfiltern schnell zusätzliche Bedingungen auf eine Überprüfungssatzabfrage anwenden. Mithilfe von Filtern können Sie die Ergebnisse, die von einer Überprüfungssatzabfrage angezeigt werden, weiter verfeinern.

![Überprüfen von Satzfiltern](../media/AeDReviewSetFilters.png)

Filter unterscheiden sich auf zwei wesentliche Weise von Abfragen:

- Filter sind vorübergehend. Sie bleiben nicht über die vorhandene Sitzung hinaus erhalten. Anders ausgedrückt: Sie können keinen Filter speichern. Abfragen werden im Überprüfungssatz gespeichert und greifen auf sie zu, wenn Sie den Überprüfungssatz öffnen.

- Filter sind immer additiv. Filter werden zusätzlich zur aktuellen Prüfdateisatz-Abfrage angewendet. Durch das Anwenden einer anderen Abfrage werden die von der aktuellen Abfrage zurückgegebenen Ergebnisse ersetzt.
