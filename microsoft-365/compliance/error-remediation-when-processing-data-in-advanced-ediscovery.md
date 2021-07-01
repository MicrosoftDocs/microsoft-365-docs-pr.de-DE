---
title: Beheben von Fehlern beim Verarbeiten von Daten
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
description: Erfahren Sie, wie Sie die Fehlerbehebung verwenden, um Datenprobleme in Advanced eDiscovery zu beheben, die eine ordnungsgemäße Verarbeitung von Inhalten verhindern können.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 891e8292fca629669a48684e95f522c08838d3aa
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226659"
---
# <a name="error-remediation-when-processing-data"></a>Beheben von Fehlern beim Verarbeiten von Daten

Die Fehlerbehebung ermöglicht eDiscovery-Administratoren die Behebung von Datenproblemen, die verhindern, dass Advanced eDiscovery den Inhalt ordnungsgemäß verarbeiten. Beispielsweise können kennwortgeschützte Dateien nicht verarbeitet werden, da die Dateien gesperrt oder verschlüsselt sind. Mithilfe der Fehlerbehebung können eDiscovery-Administratoren Dateien mit solchen Fehlern herunterladen, den Kennwortschutz entfernen und dann die korrigierten Dateien hochladen.

Verwenden Sie den folgenden Workflow, um Dateien mit Fehlern in Advanced eDiscovery Fällen zu beheben.

## <a name="create-an-error-remediation-session-to-remediate-files-with-processing-errors"></a>Erstellen einer Fehlerbehebungssitzung zum Beheben von Dateien mit Verarbeitungsfehlern

> [!NOTE]
> Wenn der Assistent zur Fehlerbehebung während des folgenden Verfahrens zu einem beliebigen Zeitpunkt geschlossen wird, können Sie auf der Registerkarte **"Verarbeitung"** zur Fehlerbehebungssitzung zurückkehren, indem Sie im Dropdownmenü **"Ansicht"** die Option **"Korrekturen"** auswählen.

1. Wählen Sie auf der Registerkarte **"Verarbeitung"** im Fall Advanced eDiscovery im Dropdownmenü **"Ansicht"** die Option **"Fehler"** aus, und wählen Sie dann im Dropdownmenü **"Bereich"** einen Prüfdateisatz oder den gesamten Fall aus. In diesem Abschnitt werden alle Fehler aus dem Fall oder einem bestimmten Prüfdateisatz angezeigt.

   ![Fehlerbehebung](../media/8c2faf1a-834b-44fc-b418-6a18aed8b81a.png)

2. Wählen Sie die Fehler aus, die Sie beheben möchten, indem Sie auf das Optionsfeld neben dem Fehlertyp oder dateityp klicken.  Im folgenden Beispiel korrigieren wir eine kennwortgeschützte Datei.

3. Klicken Sie auf **"Neue Fehlerbehebung".**

    Der Fehlerbehebungsworkflow beginnt mit einer Vorbereitungsphase, in der die Dateien mit Fehlern an einen von Microsoft bereitgestellten Azure Storage Speicherort kopiert werden, sodass Sie sie zur Korrektur auf Ihren lokalen Computer herunterladen können.

    ![Vorbereiten der Fehlerbehebung](../media/390572ec-7012-47c4-a6b6-4cbb5649e8a8.png)

4. Klicken Sie nach Abschluss der Vorbereitung auf **"Weiter: Dateien herunterladen",** um mit dem Download fortzufahren.

    ![Herunterladen von Dateien](../media/6ac04b09-8e13-414a-9e24-7c75ba586363.png)

5. Geben Sie für den Download von Dateien den **Zielpfad für den Download** an. Dies ist ein Pfad zum übergeordneten Ordner auf Ihrem lokalen Computer, in den die Datei heruntergeladen wird.  Der Standardpfad "%USERPROFILE%\Downloads\errors" verweist auf den Downloadordner des angemeldeten Benutzers. Sie können diesen Pfad bei Bedarf ändern. Wenn Sie dies ändern, wird empfohlen, einen lokalen Dateipfad zu verwenden, um die beste Leistung zu erzielen. Verwenden Sie keinen Remotenetzwerkpfad. Sie können z. B. den Pfad **C:\Remediation** verwenden.

   Der Pfad zum übergeordneten Ordner wird automatisch dem AzCopy-Befehl hinzugefügt (als Wert des Parameters **/Dest).**

6. Kopieren Sie den vordefinierten Befehl, indem Sie auf **In Zwischenablage kopieren** klicken. Öffnen Sie eine Windows Eingabeaufforderung, fügen Sie den AzCopy-Befehl ein, und drücken Sie dann die **EINGABETASTE.**

    ![Vorbereiten der Fehlerbehebung](../media/f364ab4d-31c5-4375-b69f-650f694a2f69.png)

    > [!NOTE]
    > Sie müssen AzCopy v8.1 verwenden, um den Befehl, der auf der Seite **"Dateien herunterladen"** bereitgestellt wird, erfolgreich zu verwenden. Sie müssen auch AzCopy v8.1 verwenden, um die Dateien in Schritt 10 hochzuladen. Informationen zum Installieren dieser Version von AzCopy finden Sie unter Übertragen von [Daten mit AzCopy v8.1 auf Windows](/previous-versions/azure/storage/storage-use-azcopy). Wenn der angegebene AzCopy-Befehl fehlschlägt, finden Sie Informationen zur [Problembehandlung bei AzCopy in Advanced eDiscovery.](troubleshooting-azcopy.md)

    Die von Ihnen ausgewählten Dateien werden an den Speicherort heruntergeladen, den Sie in Schritt 5 angegeben haben. Im übergeordneten Ordner (beispielsweise **C:\Remediation**) wird die folgende Unterordnerstruktur automatisch erstellt:

    `<Parent folder>\Subfolder 1\Subfolder 2\<file>`

    - *Subfolder 1* wird abhängig vom Bereich, den Sie in Schritt 1 ausgewählt haben, mit der ID des Falls oder des Prüfdateisatzes benannt.

    - *Subfolder 2* wird mit der Datei-ID der heruntergeladenen Datei benannt.

    - Die heruntergeladene Datei befindet sich in *Subfolder 2* und ist ebenfalls mit der Datei-ID benannt.

    Hier ist ein Beispiel für den Ordnerpfad und den Fehlerdateinamen, die beim Herunterladen von Elementen in den übergeordneten Ordner **"C:\Remediation"** erstellt werden:

    `C:\Remediation\232f8b7e-089c-4781-88c6-210da0615d32\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938\d1459499146268a096ea20202cd029857d64087706e6d6ca2a224970ae3b8938.docx`

    Wenn mehrere Dateien heruntergeladen werden, wird jede in einen Unterordner heruntergeladen, der mit der Datei-ID benannt ist.

    > [!IMPORTANT]
    > Wenn Sie Dateien in Schritt 9 und Schritt 10 hochladen, müssen die korrigierten Dateien denselben Dateinamen aufweisen und sich in derselben Unterordnerstruktur befinden. Der Unterordner und die Dateinamen werden verwendet, um die bereinigte Datei der ursprünglichen Fehlerdatei zuzuordnen. Wenn die Ordnerstruktur oder Dateinamen geändert werden, wird der folgende Fehler angezeigt: `Cannot apply Error Remediation to the current Workingset` . Um Probleme zu vermeiden, empfehlen wir, die korrigierten Dateien in derselben übergeordneten Ordner- und Unterordnerstruktur zu speichern.

7. Nach dem Herunterladen der Dateien können Sie diese mit einem geeigneten Tool beheben. Für kennwortgeschützte Dateien gibt es mehrere Tools zum Entschlüsseln von Kennwörtern, die Sie verwenden können. Wenn Sie die Kennwörter für die Dateien kennen, können Sie sie öffnen und den Kennwortschutz entfernen.

8. Kehren Sie zu Advanced eDiscovery und zum Fehlerbehebungs-Assistenten zurück, und klicken Sie dann auf **Weiter: Hochladen Dateien.**  Dadurch gelangen Sie zur nächsten Seite, auf der Sie die Dateien jetzt hochladen können.

    ![Hochladen Dateien](../media/af3d8617-1bab-4ecd-8de0-22e53acba240.png)

9. Geben Sie im Textfeld **Pfad zum Speicherort der Dateien** den übergeordneten Ordner an, in dem sich die korrigierten Dateien befinden. Auch hier muss der übergeordnete Ordner dieselbe Unterordnerstruktur aufweisen, die beim Herunterladen der Dateien erstellt wurde.

    Der Pfad zum übergeordneten Ordner wird automatisch dem AzCopy-Befehl hinzugefügt (als Wert des Parameters **"/Source").**

10. Kopieren Sie den vordefinierten Befehl, indem Sie auf **In Zwischenablage kopieren** klicken. Öffnen Sie eine Windows Eingabeaufforderung, fügen Sie den AzCopy-Befehl ein, und drücken Sie dann die **EINGABETASTE.** Laden Sie die Dateien hoch.

    ![Ergebnisse des erfolgreichen Hochladens von korrigierten Dateien in Azcopy](../media/ff2ff691-629f-4065-9b37-5333f937daf6.png)

11. Klicken Sie nach dem Ausführen des AzCopy-Befehls auf **"Weiter: Dateien verarbeiten".**

    Wenn die Verarbeitung abgeschlossen ist, können Sie den Prüfdateisatz aufrufen und die korrigierten Dateien anzeigen.

## <a name="remediating-errors-in-container-files"></a>Beheben von Fehlern in Containerdateien

In Situationen, in denen der Inhalt einer Containerdatei (z. B. eine .zip-Datei) nicht von Advanced eDiscovery extrahiert werden kann, können die Container heruntergeladen und der Inhalt in denselben Ordner erweitert werden, in dem sich der ursprüngliche Container befindet. Die erweiterten Dateien werden dem übergeordneten Container zugeordnet, als ob sie ursprünglich um Advanced eDiscovery erweitert worden wären. Der Vorgang funktioniert wie oben beschrieben, mit Ausnahme des Hochladens einer einzelnen Datei als Ersatzdatei.  Wenn Sie bereinigte Dateien hochladen, schließen Sie die ursprüngliche Containerdatei nicht ein.

## <a name="remediating-errors-by-uploading-the-extracted-text"></a>Beheben von Fehlern durch Hochladen des extrahierten Texts

Manchmal ist es nicht möglich, eine Datei in ein systemeigenes Format zu ändern, das Advanced eDiscovery interpretieren kann. Sie können die Originaldatei jedoch durch eine Textdatei ersetzen, die den ursprünglichen Text der systemeigenen Datei enthält (in einem Prozess, der als *Textüberlagerung* bezeichnet wird). Führen Sie dazu die in diesem Artikel beschriebenen Schritte aus, aber anstatt die ursprüngliche Datei im nativen Format zu korrigieren, erstellen Sie eine Textdatei, die den extrahierten Text aus der Originaldatei enthält, und laden die Textdatei dann mithilfe des ursprünglichen Dateinamens hoch, der mit einem .txt Suffix angefügt wurde. Beispielsweise laden Sie eine Datei während der Fehlerbehebung mit dem Dateinamen 335850cc-6602-4af0-acfa-1d14d9128ca2.abc herunter. Sie öffnen die Datei in der systemeigenen Anwendung, kopieren den Text und fügen sie dann in eine neue Datei mit dem Namen 335850cc-6602-4af0-acfa-1d14d9128ca2.abc.txt ein. Wenn Sie dies tun, müssen Sie die Originaldatei im nativen Format aus dem Speicherort der korrigierten Datei auf Dem lokalen Computer entfernen, bevor Sie die korrigierte Textdatei in Advanced eDiscovery hochladen.

## <a name="what-happens-when-files-are-remediated"></a>Was geschieht, wenn Dateien korrigiert werden

Wenn korrigierte Dateien hochgeladen werden, werden die ursprünglichen Metadaten mit Ausnahme der folgenden Felder beibehalten:

- ExtractedTextSize
- HasText
- IsErrorRemediate
- LoadId
- ProcessingErrorMessage
- ProcessingStatus
- Text
- Wordcount
- WorkingsetId

Eine Definition aller Metadatenfelder in Advanced eDiscovery finden Sie unter [Dokumentmetadatenfelder.](document-metadata-fields-in-advanced-ediscovery.md)