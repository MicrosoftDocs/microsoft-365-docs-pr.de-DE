---
title: Fehlerkorrektur beim Verarbeiten von Daten für eine Untersuchung
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
ms.openlocfilehash: 614397a81fd898975e5163c669fb8693fcdfe77c
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081476"
---
# <a name="error-remediation-when-processing-data-for-an-investigation"></a>Fehlerkorrektur beim Verarbeiten von Daten für eine Untersuchung

Durch die Fehlerkorrektur können Ermittler Daten Probleme beheben, die verhindern, dass Daten Untersuchungen (Preview) die Inhalte ordnungsgemäß verarbeiten. Beispielsweise können Dateien, die kennwortgeschützt sind, nicht verarbeitet werden, da die Dateien gesperrt oder verschlüsselt sind. Mithilfe der Fehlerkorrektur können Ermittler Dateien mit solchen Fehlern herunterladen, den Kennwortschutz entfernen und die korrigierten Dateien hochladen.

Verwenden Sie den folgenden Workflow, um Dateien mit Fehlern in Daten Ermittlungs Fällen (Vorschau) zu beheben.

## <a name="creating-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Erstellen einer Fehlerbehebungssitzung zum Beheben von Dateien mit Verarbeitungsfehlern

>[!NOTE]
>Wenn der Fehlerkorrektur-Assistent während des folgenden Verfahrens zu einem beliebigen Zeitpunkt geschlossen wird, können Sie auf der Registerkarte **Verarbeitung** zur Fehlerbehebungssitzung zurückkehren, indem Sie im Dropdownmenü **Ansicht** die Option **Fehler** Korrekturen auswählen.

1. Wählen Sie auf der Registerkarte **Verarbeitung** in einer Datenermittlung im Dropdownmenü **Ansicht** die Option **Fehler** aus.

2. Wählen Sie die Fehler aus, die Sie korrigieren möchten, indem Sie auf das Optionsfeld neben dem Fehlertyp oder-Dateityp klicken.  Im folgenden Beispiel werden wir eine kennwortgeschützte Datei remediationieren.

3. Klicken Sie auf **+ neue Fehlerkorrektur**.

    ![Fehlerbehebung](media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

    Die Fehlerbehebungssitzung beginnt, beginnend mit einer Vorbereitungsphase, in der die Dateien mit Fehlern an einen sicheren Azure-Speicherort kopiert werden, damit Sie heruntergeladen werden können.

    ![Vorbereiten der Fehlerbehebung](media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Nachdem die Vorbereitung abgeschlossen ist, klicken Sie auf **Weiter: Dateien herunterladen** , um den Download fortzusetzen.

    ![Herunterladen von Dateien](media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Geben Sie zum Herunterladen von Dateien den **Ziel Pfad für den Download**an. Dies ist ein Pfad auf dem lokalen Computer, auf dem die Datei heruntergeladen werden soll.  Der Standardpfad,%USERPROFILE%\Downloads\errors, verweist auf den Ordner "Downloads" des angemeldeten Benutzers; Dies kann bei Bedarf geändert werden.

    >[!NOTE]
    >Es wird empfohlen, einen lokalen Dateipfad anstelle eines Remotenetzwerk Pfads zu verwenden, um eine optimale Leistung zu erzielen.

    > [!NOTE]
    > Wenn Sie AzCopy nicht installiert haben, können Sie es von hier aus installieren:https://docs.microsoft.com/en-us/azure/storage/common/storage-use-azcopy

6. Kopieren Sie den vordefinierten Befehl **, indem Sie auf in Zwischenablage kopieren**klicken. Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, und drücken Sie dann die **Eingabe**Taste.  

    Die Dateien werden heruntergeladen.

    ![Vorbereiten der Fehlerbehebung](media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > Wenn beim Ausführen dieses Befehls Probleme auftreten, lesen Sie [Troubleshooting AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).

7. Nachdem Sie die Dateien heruntergeladen haben, können Sie Sie mit einem geeigneten Tool korrigieren. Für kennwortgeschützte Dateien gibt es mehrere Kenn Wort Knack Tools, die Sie verwenden können. Wenn Sie die Kennwörter für die Dateien kennen, können Sie Sie öffnen und den Kennwortschutz entfernen.
    
   > [!NOTE]
    > Es ist wichtig, dass Sie die Verzeichnisstruktur und die Dateinamen der korrigierten Dateien beibehalten. Die Pfadnamen der heruntergeladenen Dateien und Ordner ermöglichen das Zuordnen der korrigierten Dateien zu den Originaldateien.  Wenn die Verzeichnisstruktur oder die Dateinamen geändert werden, erhalten Sie den folgenden Fehler: `Cannot apply Error Remediation to the current Evidenceset`.

8. Kehren Sie nun zu Daten Untersuchungen (Vorschau) zurück, und klicken Sie auf **Weiter: Dateien hochladen**.  Dadurch gelangen Sie zum nächsten Schritt, in dem Sie die Dateien jetzt hochladen können.

    ![Hochladen von Dateien](media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Geben Sie den Speicherort der korrigierten Dateien in das Textfeld **Pfad zum Speicherort der Dateien** ein, und klicken Sie dann auf **in Zwischenablage kopieren**.

10. Fügen Sie den Befehl in eine Windows-Eingabeaufforderung ein, und drücken **Sie die EINGABETASTE** , um die Dateien hochzuladen.

    ![ff2ff691-629f-4065-9b37-5333f937daf6. png](media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Kehren Sie schließlich zu Daten Untersuchungen (Vorschau) zurück, und klicken Sie auf **Weiter: Process files**.

12. Nach Abschluss der Verarbeitung.  Sie können zum Arbeitsmappe zurückkehren und die korrigierte Datei anzeigen.

## <a name="what-happens-when-files-are-remediated"></a>Was geschieht, wenn Dateien behoben werden

Bei hochzuladenden Dateien werden die ursprünglichen Metadaten mit Ausnahme der folgenden Felder beibehalten: 

- ExtractedTextSize
- HasText
- IsErrorRemediate
- Lade-Nr
- ProcessingErrorMessage
- ProcessingStatus
- Text
- WordCount
- WorkingsetId

Eine Definition aller Document Metadata fields in Data Investigations (Preview) finden Sie unter [Document Metadata fields](document-metadata-fields.md).