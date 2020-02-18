---
title: Laden von Nicht-Office 365-Daten in einen Prüfdateisatz
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
description: Importieren Sie nicht Office 365 Daten in einen Überprüfungs in einem erweiterten eDiscovery-Fall.
ms.openlocfilehash: ae5effafd8a208d3c03ce40e03c9da2b0ea6b8d1
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42072207"
---
# <a name="load-non-office-365-data-into-a-review-set"></a>Laden von Nicht-Office 365-Daten in einen Prüfdateisatz

Nicht alle Dokumente, die Sie in Advanced eDiscovery analysieren müssen, befinden sich in Office 365. Mit der nicht Office 365 datenimportfunktion in Advanced eDiscovery können Sie Dokumente, die sich nicht in Office 365 befinden, in einen Überprüfungs-Datensatz hochladen. In diesem Artikel erfahren Sie, wie Sie Ihre nicht-Office 365-Dokumente zur Analyse in Advanced eDiscovery integrieren.

>[!Note]
>Advanced eDiscovery erfordert ein Microsoft 365-oder Office 365 E5-Abonnement für Ihre Organisation oder ein E3-Abonnement mit dem Add-on-Abonnement für erweiterte Kompatibilität. Wenn Sie diesen Plan nicht haben und Advanced eDiscovery testen möchten, können Sie sich für eine Testversion von Office 365 Enterprise E5 anmelden.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Bei Verwendung der in diesem Artikel beschriebenen Funktion "nicht Office 365 hochladen" müssen Sie über Folgendes verfügen:

- Allen Betreuern, denen nicht Office 365 Inhalte zugeordnet werden sollen, muss eine E5-Lizenz oder eine E3-Lizenz mit einer Advanced Compliance-Add-on-Lizenz zugewiesen sein.

- Ein vorhandener erweiterter eDiscovery-Fall.

- Verwalter müssen dem Fall hinzugefügt werden, bevor Sie Sie hochladen und den nicht Office 365-Daten zuordnen können.

- Nicht Office 365 Daten müssen einen Dateityp aufweisen, der von Advanced eDiscovery unterstützt wird. Weitere Informationen finden Sie unter [Supported file types in Advanced eDiscovery](supported-filetypes-ediscovery20.md).

- Alle Dateien, die in einen Überprüfungs Sätze hochgeladen werden, müssen sich in Ordnern befinden, in denen jeder Ordner einer bestimmten Depotbank zugeordnet ist. Für die Namen dieser Ordner muss Folgendes Benennungsformat verwendet werden: *Alias@Domainname*. Das Alias@Domainname muss der Office 365 Alias und die Domäne des Benutzers sein. Sie können alle Alias@Domainname Ordner in einem Stammordner sammeln. Der Stammordner kann nur die Alias@Domainname Ordner enthalten. Lose Dateien im Stammordner werden nicht unterstützt.

   Die Ordnerstruktur für die nicht Office 365 Daten, die Sie hochladen möchten, würde dem folgenden Beispiel ähneln:

   - c:\nonO365\abraham.mcmahon@contoso.com
   - c:\nonO365\jewell.gordon@contoso.com
   - c:\nonO365\staci.gonzalez@contoso.com

   Dabei sind Abraham.McMahon@contoso.com, Jewell.Gordon@contoso.com und Staci.Gonzalez@contoso.com die SMTP-Adressen der Verwalter in dem Fall.

   ![Ordnerstruktur für nicht Office 365E Datenuploads](../media/3f2dde84-294e-48ea-b44b-7437bd25284c.png)

- Ein Konto, das der Rollengruppe "eDiscovery-Manager" zugewiesen ist (und als eDiscovery-Administrator hinzugefügt wurde).

- Das AzCopy v 8.1-Tool, das auf einem Computer installiert ist, der Zugriff auf die Struktur nicht Office 365 Inhaltsordner hat. Informationen zum Installieren von AzCopy finden Sie unter [übertragen von Daten mit der AzCopy v 8.1 unter Windows](https://docs.microsoft.com/previous-versions/azure/storage/storage-use-azcopy). Stellen Sie sicher, dass Sie AzCopy im Standardspeicherort installieren, also **% Programme (x86)% \ Microsoft SDKs\Azure\AzCopy**. Sie müssen AzCopy v 8.1 verwenden. Andere Versionen von AzCopy funktionieren möglicherweise nicht, wenn nicht Office 365 Daten in Advanced eDiscovery geladen werden.


## <a name="upload-non-office-365-content-into-advanced-ediscovery"></a>Hochladen nicht Office 365er Inhalte in die erweiterte eDiscovery

1. Öffnen Sie als eDiscovery-Manager oder eDiscovery-Administrator Advanced eDiscovery, dann werden die nicht Office 365-Daten hochgeladen.  

2. Klicken Sie auf **Überprüfungs Sätze**, und wählen Sie dann den Überprüfungs Satz aus, an den die nicht Office 365 Daten hochgeladen werden sollen.  Wenn Sie keinen Überprüfungs Sätze haben, können Sie einen erstellen. 
 
3. Klicken Sie in der Überprüfungsgruppe auf **Überarbeitungs Gruppe verwalten**, und klicken Sie dann auf der **Daten Kachel nicht Office 365** auf **Uploads anzeigen** .

4. Klicken Sie auf **Dateien hochladen** , um den nicht Office 365 Datenimport-Assistenten zu starten.

   ![Dateien hochladen](../media/574f4059-4146-4058-9df3-ec97cf28d7c7.png)

   Im ersten Schritt des Assistenten wird ein sicherer von Microsoft bereitgestellter Azure-Speicherort für den Upload der Dateien vorbereitet.  Wenn die Vorbereitung abgeschlossen ist, wird die Schaltfläche **Weiter: Dateien hochladen** aktiviert.

   ![Nicht Office 365 Import: Prepare](../media/0670a347-a578-454a-9b3d-e70ef47aec57.png)
 
5. Klicken Sie auf **Weiter: Dateien hochladen**.

6. Führen Sie auf der Seite **Dateien hochladen** folgende Schritte aus:

   ![Nicht Office 365 Import: Hochladen von Dateien](../media/3ea53b5d-7f9b-4dfc-ba63-90a38c14d41a.png)

   a. Überprüfen Sie im Feld **Pfad zum Speicherort der Dateien** den Speicherort des Stammordners, in dem Sie die nicht Office 365 Daten, die Sie hochladen möchten, gespeichert haben, oder geben Sie ihn ein. Wenn Sie beispielsweise den Speicherort der Beispieldateien im **Abschnitt bevor Sie beginnen**sehen möchten, geben Sie **%USERPROFILE\Downloads\nonO365**ein. Durch Bereitstellen des richtigen Speicherorts wird sichergestellt, dass der im Feld unter dem Pfad angezeigte AzCopy-Befehl ordnungsgemäß aktualisiert wird.

   b. Klicken Sie auf in **Zwischenablage kopieren** , um den Befehl zu kopieren, der in dem Feld angezeigt wird.

7. Starten Sie eine Windows-Eingabeaufforderung, fügen Sie den Befehl ein, den Sie im vorherigen Schritt kopiert haben, und drücken Sie dann die **EINGABETASTE** , um den AzCopy-Befehl zu starten.  Nachdem Sie den Befehl gestartet haben, werden die nicht Office 365 Dateien in den Azure-Speicherort hochgeladen, der in Schritt 4 vorbereitet wurde.

   ![Nicht Office 365 Import: AzCopy](../media/504e2dbe-f36f-4f36-9b08-04aea85d8250.png)

   > [!NOTE]
   > Wie bereits erwähnt, müssen Sie AzCopy v 8.1 verwenden, um den Befehl, der auf der Seite **Dateien hochladen** bereitgestellt wird, erfolgreich zu verwenden. Wenn der angegebene AzCopy-Befehl fehlschlägt, finden Sie weitere Informationen unter [Troubleshoot AzCopy in Advanced eDiscovery](troubleshooting-azcopy.md).

8. Wechseln Sie zurück zum Security & Compliance Center, und klicken Sie auf **Weiter: Dateien** im Assistenten verarbeiten.  Dadurch werden Verarbeitung, Textextraktion und Indizierung der nicht Office 365 Dateien initiiert, die in den Azure-Speicherort hochgeladen wurden.  

9. Verfolgen Sie den Fortschritt der Verarbeitung nicht Office 365er Dateien auf der Seite **Prozessdateien** oder auf der Registerkarte **Aufträge** , indem Sie einen Auftrag mit dem Namen **Hinzufügen von nicht Office 365 Daten zu einem Überprüfungs Satzes**anzeigen.  Nachdem der Auftrag abgeschlossen ist, sind die neuen Dateien in der Überprüfungsgruppe verfügbar.

   ![Nicht Office 365 Import: Verarbeiten von Dateien](../media/218b1545-416a-4a9f-9b25-3b70e8508f67.png)

10. Nachdem die Verarbeitung abgeschlossen ist, können Sie den Assistenten schließen.
