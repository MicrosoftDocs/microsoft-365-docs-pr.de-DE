---
title: Commit einer Entwurfssammlung für einen Überprüfungssatz
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
ms.reviewer: nickrob
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
description: Nachdem Sie eine Entwurfssammlung erstellt und iteriert haben, können Sie einen Commit für einen Überprüfungssatz erstellen. Wenn Sie ein Commit für eine Entwurfssammlung festlegen, werden die gesammelten Elemente der Überprüfungssatz für den Fall hinzugefügt. Nachdem die gesammelten Elemente im Überprüfungssatz enthalten sind, können Sie sie analysieren, überprüfen und exportieren.
ms.openlocfilehash: e28592e7aac289bfc0cc29d312963fa21d9f8fd4
ms.sourcegitcommit: 8f1721de52dbe3a12c11a0fa5ed0ef5972ca8196
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/17/2021
ms.locfileid: "50838857"
---
# <a name="commit-a-draft-collection-to-a-review-set-in-advanced-ediscovery"></a>Commit einer Entwurfssammlung für einen Überprüfungssatz in Advanced eDiscovery

Wenn Sie mit den Elementen, die Sie in einer Entwurfssammlung gesammelt haben, zufrieden sind und bereit sind, sie zu analysieren, zu kennzeichnen und zu überprüfen, können Sie einer Überprüfungssammlung in diesem Fall eine Auflistung hinzufügen. Wenn Sie eine Entwurfssammlung für einen Überprüfungssatz festlegen, werden gesammelte Elemente aus ihrem ursprünglichen Inhaltsspeicherort in Microsoft 365 in einen Überprüfungssatz kopiert. Ein Überprüfungssatz ist ein sicherer, von Microsoft bereitgestellter Azure Storage-Speicherort in der Microsoft-Cloud.

## <a name="commit-a-draft-collection-to-a-review-set"></a>Commit einer Entwurfssammlung für einen Überprüfungssatz

1. Öffnen Sie im Microsoft 365 Compliance Center den Fall Advanced eDiscovery, und wählen Sie dann die Registerkarte Sammlungen aus, um eine Liste der Sammlungen in diesem Fall anzeigen zu können. 

   ![Liste der Sammlungen in einem Fall](../media/CommitDraftCollections1.png)

   > [!TIP]
   > Ein Wert `Estimated` in der Spalte **Status** identifiziert die Entwurfssammlungen, die einem Überprüfungssatz hinzugefügt werden können. Ein Status von gibt an, dass einer Überprüfungssammlung bereits eine `Committed` Auflistung hinzugefügt wurde.

2. Wählen Sie **auf** der Seite Sammlungen die Entwurfssammlung aus, die Sie für einen Überprüfungssatz festlegen möchten.

3. Wählen Sie unten auf der Flyoutseite **Aktionen**  >  **Bearbeiten -Auflistung aus.**

4. Klicken Sie im Assistenten für die Bearbeitungssammlung auf **Weiter,** bis die Seite **Entwurf oder** Sammlung speichern angezeigt wird.

5. Konfigurieren Sie die folgenden Einstellungen:

   1. Wählen **Sie Elemente sammeln aus, und fügen Sie zum Überprüfen des Satz hinzu.**

   2. Entscheiden Sie, ob die Auflistung einem neuen Überprüfungssatz (der nach dem Übermitteln der Auflistung erstellt wird) oder einem vorhandenen Überprüfungssatz hinzugefügt werden soll. Führen Sie diesen Abschnitt basierend auf Ihrer Entscheidung aus.

   3. Konfigurieren Sie die zusätzlichen Sammlungseinstellungen:

       - **Teams und Yammer:** Wählen Sie diese Option aus, um der Auflistung Unterhaltungsthreads hinzuzufügen, die die von der Suchabfrage in der Auflistung zurückgegebenen Chatelemente enthalten. Dies bedeutet, dass die Chat-Unterhaltung, die Elemente enthält, die den Suchkriterien entsprechen, rekonstruiert wird. Auf diese Weise können Sie Chatelemente im Kontext der Hin- und Her-Unterhaltung überprüfen. Weitere Informationen finden Sie unter [Conversation threading in Advanced eDiscovery](conversation-review-sets.md).

       - **Cloudanlagen:** Wählen Sie diese Option aus, um moderne Anlagen oder verknüpfte Dateien zu verwenden, wenn die Sammlungsergebnisse dem Überprüfungssatz hinzugefügt werden. Dies bedeutet, dass die Zieldatei einer modernen Anlage oder verknüpften Datei dem Überprüfungssatz hinzugefügt wird.

       - **SharePoint-Versionen:** Wählen Sie diese Option aus, um die Auflistung aller Versionen eines SharePoint-Dokuments nach den Versionsgrenzwerte und Suchparametern der Auflistung zu aktivieren. Wenn Sie diese Option auswählen, wird die Größe der Elemente, die dem Überprüfungssatz hinzugefügt werden, erheblich erhöht.

   4. Konfigurieren Sie die Einstellungen, um die Skalierung der Auflistung zu definieren, die dem Überprüfungssatz hinzugefügt werden soll:

      - **Alle Auflistungsergebnisse hinzufügen:** Wählen Sie diese Option aus, um alle Elemente hinzuzufügen, die den Suchkriterien der Auflistung entsprechen.

      - **Fügen Sie ein Beispiel der Auflistungsergebnisse hinzu:** Wählen Sie diese Option aus, um dem Überprüfungssatz ein Beispiel der Auflistungsergebnisse hinzuzufügen, anstatt alle Ergebnisse hinzuzufügen. Wenn Sie diese Option auswählen, klicken Sie auf **Beispielparameter bearbeiten,** und wählen Sie eine der folgenden Optionen aus:

         - **Beispiel basierend auf der Konfidenz:** Elemente aus der Auflistung werden dem Überprüfungssatz hinzugefügt und werden durch die von Ihnen festgelegten statistischen Parameter bestimmt. Wenn Sie in der Regel eine Konfidenzstufe und ein Intervall beim Sampling von Ergebnissen verwenden, geben Sie sie in den Dropdownfeldern an. Verwenden Sie andernfalls die Standardeinstellungen.

         - **Zufälliges Beispiel:** Elemente aus der Auflistung werden dem Überprüfungssatz basierend auf einer zufälligen Auswahl des angegebenen Prozentsatzes der Gesamtzahl der von der Suche zurückgegebenen Elemente hinzugefügt.

6. Auf der **Seite Ihre Sammlung überprüfen** können Sie die Sammlungseinstellungen überprüfen, die Sie auf der vorherigen Seite konfiguriert haben. Klicken **Sie auf Bearbeiten,** wenn Sie sie ändern möchten.

7. Klicken Sie **auf Übermitteln,** um die Entwurfssammlung zu erstellen. Es wird eine Seite angezeigt, die bestätigt, dass die Auflistung erstellt wurde.

## <a name="what-happens-after-you-commit-a-draft-collection"></a>Was geschieht nach dem Commit einer Entwurfssammlung?

Wenn Sie eine Entwurfssammlung für einen Überprüfungssatz festlegen, geschieht Folgendes:

- Die Auflistungssuchabfrage wird erneut ausgeführt. Dies bedeutet, dass sich die tatsächlichen Suchergebnisse, die in den Überprüfungssatz kopiert wurden, möglicherweise von den geschätzten Ergebnissen unterscheiden, die bei der letzten Ausführung der Sammlungssuche zurückgegeben wurden.

- Alle Elemente in den Suchergebnissen werden aus der ursprünglichen Datenquelle im Livedienst kopiert und an einen sicheren Azure Storage-Speicherort in der Microsoft Cloud kopiert.

- Alle Elemente (einschließlich der Inhalte und Metadaten), die sich nicht in Custodian- oder Non-Custodian-Datenquellen befinden, werden neu indiziert (in einem Prozess, der als tiefe Indizierung *bezeichnet* wird), sodass alle Daten im Überprüfungssatz während der Überprüfung der Falldaten vollständig durchsucht werden können. Das erneute Indizieren des Inhalts in einer Sammlung führt zu gründlichen und schnellen Suchen, wenn Sie den Inhalt im Überprüfungssatz während der Falluntersuchung durchsuchen oder filtern.

- Verschlüsselte SharePoint- und #A0 und verschlüsselte Dateien angefügte E-Mail-Nachrichten, die in den Suchergebnissen zurückgegeben werden, werden entschlüsselt, wenn Sie die Sammlung zu einem Überprüfungssatz verpflichten. Sie können die entschlüsselten Dateien im Überprüfungssatz überprüfen und abfragen. Weitere Informationen finden Sie unter [Decryption in Microsoft 365 eDiscovery tools](ediscovery-decryption.md).

- Die Funktion zur optischen Zeichenerkennung (Optical Character Recognition, OCR) extrahiert Text aus Bildern und enthält den Bildtext mit dem Inhalt, der einem Überprüfungssatz hinzugefügt wird. Weitere Informationen finden Sie im Abschnitt [Optische Zeichenerkennung](#optical-character-recognition) in diesem Artikel.

- Nachdem der Commit erfolgreich abgeschlossen wurde, wird der Wert der Statusspalte auf der Registerkarte **Sammlungen** in `Committed` geändert.

## <a name="optical-character-recognition"></a>Optical Character Recognition (optische Zeichenerkennung)

Wenn Sie eine Auflistung auf einen Überprüfungssatz festlegen, extrahiert die Funktionalität der optischen Zeichenerkennung (OCR) in Advanced eDiscovery automatisch Text aus Bildern und enthält den Bildtext mit dem Inhalt, der einem Überprüfungssatz hinzugefügt wird. Sie können den extrahierten Text in der Textanzeige der ausgewählten Bilddatei im Überprüfungssatz anzeigen. Auf diese Weise können Sie den Text in Bildern genauer überprüfen und analysieren. OCR wird für lose Dateien, E-Mail-Anlagen und eingebettete Bilder unterstützt. Eine Liste der Bilddateiformate, für die OCR unterstützt wird, finden Sie unter [Unterstützte Dateitypen in Advanced eDiscovery](supported-filetypes-ediscovery20.md#image).

Sie müssen die OCR-Funktion für jeden Fall aktivieren, den Sie in Advanced eDiscovery erstellen. Weitere Informationen finden Sie unter [Configure search and analytics settings](configure-search-and-analytics-settings-in-advanced-ediscovery.md#optical-character-recognition-ocr).
