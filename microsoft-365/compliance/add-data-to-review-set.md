---
title: Hinzufügen von Suchergebnissen zu einem Prüfdateisatz
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
ms.custom:
- seo-marvel-apr2020
description: Informationen zum Hinzufügen von Suchergebnissen oder Beispielen dieser Suchergebnisse zu einem Advanced eDiscovery Fallüberprüfungssatz.
ms.openlocfilehash: 25ea5fe076753d4a5685f1224b98a2005d334f5f
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/05/2020
ms.locfileid: "48919977"
---
# <a name="add-search-results-to-a-review-set"></a>Hinzufügen von Suchergebnissen zu einem Prüfdateisatz

Wenn Sie mit den Ergebnissen einer Suche zufrieden sind und bereit sind, diese Suchergebnisse zu überprüfen und zu analysieren, können Sie sie in diesem Fall einem Überprüfungssatz hinzufügen. Das Kopieren der ursprünglichen Daten in den Überprüfungssatz erleichtert außerdem den Überprüfungs- und Analyseprozess, indem Sie erweiterte Analysetools wie die Erkennung von Designs, die Erkennung von Beinaheduplizieren und die E-Mail-Threadidentifikation bereitstellen. Sie können auch Daten aus nicht Microsoft 365 Datenquellen zu einem Überprüfungssatz hinzufügen, damit Sie diese Daten zusätzlich zu den daten, die Sie von diesem Microsoft 365.

Wenn Sie die Ergebnisse einer Suche zu einem Überprüfungssatz hinzufügen (die Überprüfungssätze in einem Fall werden auf der Registerkarte **Überprüfungssätze** aufgeführt), geschieht Folgendes:

- Die Suche wird erneut ausgeführt. Dies bedeutet, dass sich die tatsächlichen Suchergebnisse, die in den Überprüfungssatz kopiert wurden, möglicherweise von den geschätzten Ergebnissen unterscheiden, die bei der letzten Ausführung der Suche zurückgegeben wurden.

- Alle Elemente in den Suchergebnissen werden aus der ursprünglichen Datenquelle in den Livediensten kopiert und an einen sicheren Speicherort Azure Storage in der Microsoft Cloud kopiert.

- Alle Elemente (einschließlich Inhalt und Metadaten) werden neu indiziert, sodass alle Daten im Überprüfungssatz während der Überprüfung der Falldaten vollständig durchsuchbar sind. Die Erneute Indizierung der Daten führt zu gründlichen und schnellen Suchen, wenn Sie die Daten im Überprüfungssatz während der Falluntersuchung durchsuchen.

- Eine mit einer [](encryption.md) Microsoft-Verschlüsselungstechnologie verschlüsselte Datei, die an eine E-Mail-Nachricht angefügt ist, die in den Suchergebnissen zurückgegeben wird, wird entschlüsselt, wenn die E-Mail-Nachricht und die angefügte Datei dem Überprüfungssatz hinzugefügt werden. Sie können die entschlüsselte Datei im Überprüfungssatz überprüfen und abfragen. Ihnen muss die Rolle RMS Decrypt zugewiesen werden, um einem Überprüfungssatz entschlüsselte E-Mail-Anlagen hinzuzufügen. Weitere Informationen finden Sie unter [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).

Klicken Sie zum Hinzufügen von Daten zu  einem Überprüfungssatz auf  der Registerkarte Suchen auf eine Suche, und klicken Sie dann auf Ergebnisse hinzufügen, um den Satz auf der Flyoutseite zu überprüfen.

Sie können einem vorhandenen Überprüfungssatz hinzufügen oder einen neuen Überprüfungssatz erstellen.  Wenn Sie einem neuen Überprüfungssatz hinzufügen, geben Sie den Namen an, und klicken Sie dann auf **Hinzufügen,** um die Flyoutseite anzeigen zu können.

![Auswählen eines Überprüfungssatzs und Konfigurieren von Sammlungsoptionen](../media/AeD_AddToReviewSet.png)

Das Hinzufügen von Daten zu einem Prüfdateisatz ist ein langwieriger Prozess. Dieser Prozess umfasst das Sammeln von Elementen aus den ursprünglichen Datenquellen in Microsoft 365 (z. B. aus Postfächern und Websites), das Kopieren an den Azure Storage-Speicherort (dieser Kopiervorgang wird auch als *Ingestion* bezeichnet), und anschließend die Elemente neu zu indizieren. Sie können den Fortschritt  auf der  Registerkarte Aufträge oder auf der Registerkarte Suchen nachverfolgen, indem Sie den Status in der Spalte Zu überprüfende Daten hinzugefügt **überwachen.** Nachdem die Verarbeitung des Überprüfungssatzs abgeschlossen ist, klicken Sie in dem Fall auf die Registerkarte Überprüfungssätze, und klicken Sie dann auf den Überprüfungssatz, um den Prozess des Filterns, Überprüfens, Markierens und Exportierens von Daten im Überprüfungssatz zu starten. 

## <a name="define-options-to-scope-your-collection-for-review"></a>Definieren von Optionen für den Bereich Ihrer Sammlung für die Überprüfung

Wenn Sie den Inhalt einer Suche zu einem vorhandenen oder neuen Überprüfungssatz hinzufügen, stehen Ihnen die folgenden Optionen zur Verfügung, um den Inhalt zur Überprüfung zu erfassen:

- **Include versions from SharePoint (beta)**: Verwenden Sie diese Option, um die Auflistung aller Versionen eines SharePoint-Dokuments nach den Versionsgrenzwerte und Suchparametern der Auflistung zu aktivieren. Wenn Sie diese Option auswählen, wird die Größe der Elemente, die dem Überprüfungssatz hinzugefügt werden, erheblich erhöht.

- **Optionen zum Abrufen von** Unterhaltungen: Elemente, die dem Überprüfungssatz hinzugefügt wurden, sind für Threadunterhaltungen aktiviert, um Inhalte im Kontext der Hin- und Her-Unterhaltung zu überprüfen. Weitere Informationen finden Sie unter [Überprüfen von Unterhaltungen in Advanced eDiscovery](conversation-review-sets.md).

- **Abrufen für moderne Anlagen aktivieren:** Verwenden Sie diese Option, um moderne Anlagen oder verknüpfte Dateien zur weiteren Überprüfung in die Auflistung zu verwenden. Weitere Informationen zu den durchsuchbaren Eigenschaften im Zusammenhang mit modernen Anlagen finden Sie unter [Dokumentmetadatenfelder in Advanced eDiscovery](document-metadata-fields-in-Advanced-eDiscovery.md).

## <a name="add-a-sample-to-a-review-set"></a>Hinzufügen eines Beispiels zu einem Überprüfungssatz

Wenn Sie die Ergebnisse einer Suche gründlicher überprüfen möchten, bevor Sie alle zu einem Überprüfungssatz hinzufügen, können Sie einem Überprüfungssatz ein Beispiel der Suchergebnisse hinzufügen, anstatt alles hinzuzufügen.

Wenn Sie einem Überprüfungssatz ein Beispiel  hinzufügen möchten,  klicken Sie auf der Registerkarte Suchen auf eine Suche, und klicken Sie auf der Flyoutseite auf Beispiel. Wählen Sie **auf der** Seite Samplingparameter eine der folgenden Optionen aus:

- **Konfidenzniveau %** und **Konfidenzintervall %** – Die elemente, die dem Überprüfungssatz hinzugefügt wurden, werden durch die von Ihnen festgelegten statistischen Parameter bestimmt. Wenn Sie in der Regel eine Konfidenzstufe und ein Intervall beim Sampling von Ergebnissen verwenden, geben Sie sie in den Dropdownfeldern an. Verwenden Sie andernfalls die Standardeinstellungen.

- **Zufallsstichprobe %** – Die elemente, die dem Überprüfungssatz hinzugefügt wurden, basieren auf einer zufälligen Auswahl des angegebenen Prozentsatzes der Gesamtzahl der von der Suche zurückgegebenen Elemente.

Nachdem Sie eine der vorherigen Optionen ausgewählt und konfiguriert haben, wählen Sie einen Überprüfungssatz aus, um das Beispiel hinzuzufügen, und klicken Sie dann auf **Senden**. Auch hier können Sie den  Fortschritt auf  der Registerkarte Aufträge oder auf der Registerkarte Suchen nachverfolgen, indem Sie den Status in der Spalte Hinzugefügte Daten zum Überprüfen von **Satzdaten** überwachen.

## <a name="optical-character-recognition"></a>Optical Character Recognition (optische Zeichenerkennung)

Wenn Sie einem Überprüfungssatz Suchergebnisse hinzufügen, extrahiert die Funktion zur optischen Zeichenerkennung (OCR) in Advanced eDiscovery automatisch Text aus Bildern und enthält den Bildtext mit den Daten, die einem Überprüfungssatz hinzugefügt werden. Sie können den extrahierten Text in der Textanzeige der ausgewählten Bilddatei im Überprüfungssatz anzeigen. Auf diese Weise können Sie den Text in Bildern genauer überprüfen und analysieren. OCR wird für lose Dateien, E-Mail-Anlagen und eingebettete Bilder unterstützt. Eine Liste der Bilddateiformate, für die OCR unterstützt wird, finden Sie unter [Unterstützte Dateitypen in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).

Sie müssen die OCR-Funktion für jeden Fall aktivieren, den Sie in Advanced eDiscovery erstellen. Weitere Informationen finden Sie unter [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).
