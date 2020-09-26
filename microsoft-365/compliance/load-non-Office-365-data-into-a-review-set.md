---
title: Laden von nicht von Microsoft 365 stammenden Daten in einen Prüfdateisatz
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
description: In diesem Artikel erfahren Sie, wie Sie nicht von Microsoft 365 Daten in einen Überprüfungs für die Analyse in einem erweiterten eDiscovery-Fall importieren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ad70207bdc015107a5aba074e2df06a42c0618b3
ms.sourcegitcommit: 2160e7cf373f992dd4d11793a59cb8c44f8d587e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/26/2020
ms.locfileid: "48285861"
---
# <a name="load-non-microsoft-365-data-into-a-review-set"></a>Laden von nicht von Microsoft 365 stammenden Daten in einen Prüfdateisatz

Nicht alle Dokumente, die Sie in Advanced eDiscovery analysieren müssen, befinden sich in Microsoft 365. Mit dem Microsoft 365-Datenimport-Feature in Advanced eDiscovery können Sie Dokumente, die sich nicht in Microsoft 365 befinden, in einen Prüfdateisatz hochladen. In diesem Artikel erfahren Sie, wie Sie Ihre nicht-Microsoft 365-Dokumente in Advanced eDiscovery for Analysis integrieren.

## <a name="requirements-to-upload-non-office-365-content"></a>Anforderungen zum Hochladen nicht Office 365der Inhalte

Bei Verwendung des in diesem Artikel beschriebenen Features zum Hochladen nicht von Microsoft 365 ist Folgendes erforderlich:

- Allen Betreuern, denen kein Inhalt von Microsoft 365 zugeordnet werden soll, muss die entsprechende Lizenz zugewiesen sein. Weitere Informationen finden Sie unter [Erste Schritte mit Advanced eDiscovery](get-started-with-advanced-ediscovery.md#step-1-verify-and-assign-appropriate-licenses).

- Ein vorhandener erweiterter eDiscovery-Fall.

- Verwalter müssen dem Fall hinzugefügt werden, bevor Sie Sie hochladen und den nicht von Microsoft 365 Daten zuordnen können.

- Nicht von Microsoft 365 stammende Daten müssen einen Dateityp aufweisen, der von Advanced eDiscovery unterstützt wird. Weitere Informationen finden Sie unter [Unterstützte Dateitypen in Advanced eDiscovery](supported-filetypes-ediscovery20.md).

- Alle Dateien, die in einen Prüfdateisatz hochgeladen werden, müssen sich in Ordnern befinden, wobei jeder Ordner einem bestimmten Verwahrer zugeordnet ist. Für die Namen dieser Ordner muss das folgende Namensformat verwendet werden: *alias@domainname*. Bei „alias@domainname“ muss es sich um den Microsoft 365-Alias und die Domäne des Benutzers handeln. Sie können alle Alias@Domainname Ordner in einem Stammordner sammeln. Der Stammordner kann nur die Alias@Domainname Ordner enthalten. Lose Dateien im Stammordner werden nicht unterstützt.

   Die Ordnerstruktur für die Daten, die nicht von Microsoft 365 hochgeladen werden sollen, würde dem folgenden Beispiel ähneln:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Dabei sind Abraham.McMahon@contoso.com, Jewell.Gordon@contoso.com und Staci.Gonzalez@contoso.com die SMTP-Adressen der Verwalter in dem Fall.

   ![Ordnerstruktur eines nicht von Microsoft 365 Datenuploads](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Ein Konto, das der Rollengruppe "eDiscovery-Manager" zugewiesen ist (und als eDiscovery-Administrator hinzugefügt wurde).

- Das AzCopy v 8.1-Tool, das auf einem Computer installiert ist, der Zugriff auf die Inhaltsordner Struktur nicht von Microsoft 365 hat. Informationen zum Installieren von AzCopy finden Sie unter [übertragen von Daten mit der AzCopy v 8.1 unter Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy). Stellen Sie sicher, dass Sie AzCopy im Standardspeicherort installieren, also **% Programme (x86)% \ Microsoft SDKs\Azure\AzCopy**. Sie müssen AzCopy v 8.1 verwenden. Andere Versionen von AzCopy funktionieren möglicherweise nicht, wenn nicht-Microsoft 365-Daten in Advanced eDiscovery geladen werden.


## <a name="upload-non-microsoft-365-content-into-advanced-ediscovery"></a>Hochladen von nicht-Microsoft 365-Inhalten in Erweiterte eDiscovery

1. Öffnen Sie als eDiscovery-Manager oder eDiscovery-Administrator Advanced eDiscovery, und wechseln Sie zu dem Fall, in den die Daten nicht von Microsoft 365 hochgeladen werden.  

2. Klicken Sie auf **Überprüfungs Sätze**, und wählen Sie dann den Überprüfungs Satz aus, um die nicht von Microsoft 365 Daten hochzuladen.  Wenn Sie keinen Überprüfungs Sätze haben, können Sie einen erstellen. 
 
3. Klicken Sie im Prüfdateisatz auf **Prüfdateisatz verwalten**, und klicken Sie dann auf der Kachel **Nicht von Microsoft 365 stammende Daten** auf **Uploads anzeigen**.

4. Klicken Sie auf **Dateien hochladen**, um den Datenimport-Assistenten zu starten.

   ![Dateien hochladen](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   Der erste Schritt im Assistenten bereitet einen von Microsoft bereitgestellten sicheren Azure-Speicherort vor, in den die Dateien hochgeladen werden sollen.  Wenn die Vorbereitung abgeschlossen ist, wird die Schaltfläche **Weiter: Dateien hochladen** aktiviert.

   ![Nicht-Microsoft-365-Import: Prepare](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. Klicken Sie auf **Weiter: Dateien hochladen**.

6. Führen Sie auf der Seite **Dateien hochladen** folgende Schritte aus:

   ![Nicht-Microsoft 365 Import: Hochladen von Dateien](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. Überprüfen Sie im Feld **Pfad zum Speicherort der Dateien** , oder geben Sie den Speicherort des Stammordners ein, in dem Sie die nicht von Microsoft 365 Daten gespeichert haben, die Sie hochladen möchten. Wenn Sie beispielsweise den Speicherort der Beispieldateien im **Abschnitt bevor Sie beginnen**sehen möchten, geben Sie **%USERPROFILE\Downloads\nonO365**ein. Durch Bereitstellen des richtigen Speicherorts wird sichergestellt, dass der im Feld unter dem Pfad angezeigte AzCopy-Befehl ordnungsgemäß aktualisiert wird.

   b. Klicken Sie auf in **Zwischenablage kopieren** , um den Befehl zu kopieren, der in dem Feld angezeigt wird.

7. Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, den Sie im vorherigen Schritt kopiert haben, und drücken Sie dann die **EINGABETASTE** , um den AzCopy-Befehl zu starten.  Nachdem Sie den Befehl gestartet haben, werden die nicht von Microsoft 365 Dateien an den Azure-Speicherort hochgeladen, der in Schritt 4 vorbereitet wurde.

   ![Nicht-Microsoft 365 Import: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Wie bereits erwähnt, müssen Sie AzCopy v 8.1 verwenden, um den Befehl, der auf der Seite **Dateien hochladen** bereitgestellt wird, erfolgreich zu verwenden. Wenn der angegebene AzCopy-Befehl fehlschlägt, finden Sie weitere Informationen unter [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).

8. Wechseln Sie zurück zum Security & Compliance Center, und klicken Sie auf **Weiter: Dateien** im Assistenten verarbeiten.  Die Verarbeitung, Textextraktion und Indizierung der nicht von Microsoft 365 stammenden Dateien, die in den Azure-Speicherort hochgeladen wurden, wird gestartet.  

9. Verfolgen Sie den Fortschritt der Verarbeitung der Dateien auf der Seite " **Prozessdateien** " oder auf der Registerkarte " **Aufträge** ", indem Sie einen Auftrag mit dem Namen **Hinzufügen von nicht-Microsoft 365-Daten zu einem Überprüfungs Satzes**anzeigen.  Nachdem der Auftrag abgeschlossen ist, sind die neuen Dateien in der Überprüfungsgruppe verfügbar.

   ![Nicht-Microsoft 365-Import: Verarbeiten von Dateien](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. Nachdem die Verarbeitung abgeschlossen ist, können Sie den Assistenten schließen.
