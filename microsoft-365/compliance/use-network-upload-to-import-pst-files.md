---
title: Verwenden Sie Netzwerkuploads zum Importieren von PST-Dateien Ihrer Organisation
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 103f940c-0468-4e1a-b527-cc8ad13a5ea6
description: 'Für Administratoren: Sie erfahren, wie Sie über den Netzwerkupload einen Massenimport mehrerer PST-Dateien in Benutzerpostfächer in Office 365 ausführen.'
ms.openlocfilehash: 4420c2a684b020053bab88a14f46a73a795bd37d
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/13/2020
ms.locfileid: "42634623"
---
# <a name="use-network-upload-to-import-your-organizations-pst-files-to-office-365"></a>Verwenden Sie Netzwerkuploads zum Importieren von PST-Dateien Ihrer Organisation in Office 365

> [!NOTE]
> Dieser Artikel richtet sich an Administratoren. Möchten Sie PST-Dateien in Ihr eigenes Postfach importieren? Siehe [Importieren von E-Mails, Kontakten und Kalendern aus einer Outlook-PST-Datei](https://go.microsoft.com/fwlink/p/?LinkID=785075).
  
Nachfolgend finden Sie die Schritt-für-Schritt-Anleitungen zum Ausführen eines Massenimports mehrerer PST-Dateien in Office 365-Postfächer unter Verwendung des Netzwerkupload. Häufig gestellte Fragen zur Verwendung des Netzwerkuploads zum Ausführen eines Massenimports von PST-Dateien in Office 365-Postfächer finden Sie unter [Häufig gestellte Fragen zum Importieren von PST-Dateien unter Verwendung des Netzwerkuploads](faqimporting-pst-files-to-office-365.md#using-network-upload-to-import-pst-files).
  
[Schritt 1: Kopieren der SAS-URL und Installieren von AzCopy](#step-1-copy-the-sas-url-and-install-azcopy)

[Schritt 2: Hochladen Ihrer PST-Dateien in Office 365](#step-2-upload-your-pst-files-to-office-365)

[(Optional) Schritt 3: Anzeigen einer Liste der PST-Dateien, die in Office 365 hochgeladen wurden](#optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Schritt 4: Erstellen der PST-Importzuordnungsdatei](#step-4-create-the-pst-import-mapping-file)

[Schritt 5: Erstellen eines PST-Importauftrags in Office 365](#step-5-create-a-pst-import-job-in-office-365)

[Schritt 6: Filtern von Daten und Starten des PST-Importauftrags](#step-6-filter-data-and-start-the-pst-import-job)

Sie müssen Schritt 1 nur einmal ausführen, um PST-Dateien in Office 365-Postfächer zu importieren. Nachdem Sie diese Schritte ausgeführt haben, führen Sie Schritt 2 bis Schritt 6 jedes Mal aus, wenn Sie eine Reihe von PST-Dateien hochladen und importieren möchten.

## <a name="before-you-begin"></a>Bevor Sie beginnen
  
- Ihnen muss die Rolle für den Postfachimport/-export in Exchange Online zugewiesen werden, damit Sie PST-Dateien in Office 365-Postfächer importieren können. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle „Postfachimport/-export“ zur Rollengruppe „Organisationsverwaltung“ hinzufügen. Oder Sie erstellen eine Rollengruppe, weisen die Rolle „Postfachimport/-export“ zu und fügen sich dann selbst als Mitglied hinzu. Weitere Informationen finden Sie im Abschnitt "Hinzufügen einer Rolle zu einer Rollengruppe" oder "Erstellen einer Rollengruppe" in [Verwalten von Rollengruppen](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Außerdem muss eine der folgenden Bedingungen erfüllt sein, um Importaufträge im Security & Compliance Center erstellen zu können:
    
  - Ihnen muss in Exchange Online die Rolle „E-Mail-Empfänger“ zugewiesen sein. Standardmäßig wird diese Rolle den Rollengruppen "Organisationsverwaltung" und "Empfängerverwaltung" zugewiesen.
    
    Oder
    
  - Sie müssen ein globaler Administrator innerhalb Ihrer Office 365-Organisation sein.
    
  > [!TIP]
    > Erwägen Sie, in Exchange Online eine neue Rollengruppe speziell zum Importieren von PST-Dateien nach Office 365 zu erstellen. Legen Sie für die neue Rollengruppe als mindestens erforderliche Berechtigungen zum Importieren von PST-Dateien die Rollen "Postfachimport/-export" und "E-Mail-Empfänger" fest, und fügen Sie anschließend Mitglieder hinzu.
  
- Die einzige unterstützte Methode zum Importieren von PST-Dateien in Office 365 ist die Verwendung des AzCopy-Tools, wie in diesem Thema beschrieben. Sie können den Azure Storage-Explorer nicht verwenden, um PST-Dateien direkt in den Azure-Speicherbereich hochzuladen.
    
- Sie müssen die PST-Dateien, die Sie in Office 365 importieren möchten, auf einem Dateiserver oder einem freigegebenen Ordner in Ihrer Organisation speichern. In Schritt 2 führen Sie das AzCopy-Tool aus, um die PST-Dateien in Office 365 hochzuladen, die auf diesem Dateiserver in einem freigegebenen Ordner gespeichert sind.
    
- Große PST-Dateien können sich auf die Leistung des PST-Importprozesses auswirken. Deshalb empfehlen wir, dass jede PST-Datei, die Sie in Schritt 2 in den Azure-Speicherort hochladen, nicht größer als 20 GB sein sollte.

- Diese Vorgehensweise umfasst das Kopieren und Speichern einer Kopie einer URL, die einen Zugriffsschlüssel enthält. Diese Informationen werden in Schritt 2 zum Hochladen Ihrer PST-Dateien und in Schritt 3 verwendet, wenn Sie eine Liste der PST-Dateien anzeigen möchten, die in Office 365 hochgeladen wurden. Schützen Sie diese URL unbedingt genauso wie Kennwörter und andere sicherheitsbezogene Informationen. Sie können sie beispielsweise in einem kennwortgeschützten Microsoft Word-Dokument vermerken oder auf einem verschlüsselten USB-Laufwerk speichern. Im Abschnitt [Weitere Informationen](#more-information) finden Sie ein Beispiel für diese Kombination aus Schlüssel und URL.
    
- Sie können PST-Dateien in ein inaktives Postfach in Office 365 importieren. Geben Sie hierzu den GUID des inaktiven Postfachs im Parameter `Mailbox` in der PST-Importzuordnungsdatei an. Informationen hierzu finden Sie in diesem Thema auf der Registerkarte **Anweisungen** im Schritt 4. 
    
- In einer Exchange-Hybridumgebung können Sie PST-Dateien für einen Benutzer, dessen primäres Postfach lokal gehostet wird, in ein cloudbasiertes Archivpostfach importieren. Gehen Sie hierzu in der PST-Importzuordnungsdatei folgendermaßen vor:
    
  - Geben Sie die E-Mail-Adresse des lokalen Postfachs des Benutzers im Parameter `Mailbox` an.
    
  - Geben Sie den Wert **TRUE** im Parameter `IsArchive` an.
    
    Weitere Informationen finden Sie unter [Schritt 4](#step-4-create-the-pst-import-mapping-file).
    
- Nachdem PST-Dateien in ein Office 365-Postfach importiert wurden, wird die Einstellung zum Anhalten der Aufbewahrungszeit für das Postfach für eine unbestimmte Dauer aktiviert. Dies bedeutet: Die dem Postfach zugewiesene Aufbewahrungsrichtlinie wird erst verarbeitet, nachdem Sie das Anhalten der Aufbewahrungszeit deaktiviert oder aber ein Datum zum Deaktivieren des Anhaltens festgelegt haben. Warum tun wir dies? Wenn die in ein Postfach importierten Nachrichten alt sind, werden sie möglicherweise endgültig gelöscht, weil ihr Aufbewahrungszeitraum, basierend auf den für das Postfach konfigurierten Aufbewahrungseinstellungen, abgelaufen ist. Wenn Sie das Postfach auf Anhalten der Aufbewahrungszeit setzen, erhält der Postfachbesitzer Zeit zum Verwalten dieser neu importierten Nachrichten, oder Sie erhalten Zeit zum Ändern der Aufbewahrungseinstellungen für das Postfach. Im Abschnitt[Weitere Informationen](#more-information) finden Sie Vorschläge, wie Sie die Aufbewahrungszeit verwalten können.
    
- Standardmäßig beträgt die maximale Nachrichtengröße, die von einem Office 365-Postfach empfangen werden kann, 35 MB. Der Grund hierfür ist, dass der Standardwert für die Eigenschaft *MaxReceiveSize* für ein Postfach auf 35 MB festgelegt ist. Der Grenzwert für die maximale Größe empfangener Nachrichten in Office 365 beträgt jedoch 150 MB. Wenn Sie also eine PST-Datei importieren, die ein Element enthält, das größer als 35 MB ist, ändert der Office 365-Importdienst den Wert der Eigenschaft *MaxReceiveSize* für das Zielpostfach automatisch in "150 MB". Dadurch können Nachrichten mit bis zu 150 MB in Benutzerpostfächer importiert werden.
    
    > [!TIP]
    > Wenn Sie die Größe empfangener Nachrichten für ein Postfach ermitteln möchten, können Sie diesen Befehl in Exchange Online PowerShell ausführen: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`.

## <a name="step-1-copy-the-sas-url-and-install-azcopy"></a>Schritt 1: Kopieren der SAS-URL und Installieren von AzCopy

Im ersten Schritt laden Sie das AzCopy-Tool herunter (das Tool, das Sie in Schritt 2 ausführen, um PST-Dateien in Office 365 hochzuladen) und installieren es. Sie kopieren außerdem die SAS-URL für Ihre Organisation. Diese URL ist eine Kombination aus der Netzwerk-URL des Azure Storage-Speicherorts in der Microsoft-Cloud Ihrer Organisation und einem SAS-Schlüssel (Shared Access Signature). Mit diesem Schlüssel erhalten Sie die notwendigen Berechtigungen zum Hochladen von PST-Dateien an Ihren Azure Storage-Speicherort. Achten Sie darauf, dass Sie entsprechende Vorsichtsmaßnahmen ergreifen, um die SAS-URL zu schützen. Sie ist für Ihre Organisation eindeutig und wird in Schritt 2 verwendet.

> [!IMPORTANT]
> Wenn Sie PST-Dateien mit der in diesem Artikel beschriebenen Netzwerkuploadmethode und Befehlssyntax importieren möchten, müssen Sie die Version von AzCopy verwenden, die in Schritt 6b im folgenden Verfahren heruntergeladen werden kann. Sie können die gleiche Version von AzCopy auch [hier](https://aka.ms/downloadazcopy) herunterladen. Die Verwendung einer anderen Version von AzCopy wird nicht unterstützt.
  
1. Navigieren Sie zu [https://protection.office.com](https://protection.office.com), und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365-Organisation an. 
    
2. Klicken Sie im linken Bereich des Security & Compliance Centers auf **Information Governance** \> **Import** \> **Importieren von PST-Dateien**.
    
    > [!NOTE]
    > Sie müssen über die erforderlichen Berechtigungen für den Zugriff auf die Seite **Import** im Security & Compliance Center verfügen. Weitere Informationen finden Sie im Abschnitt **Bevor Sie beginnen**. 
    
3. Klicken Sie auf der Seite **Import von PST-Dateien** ![Symbol hinzufügen](../media/ITPro-EAC-AddIcon.gif) **Neuer Importauftrag**.
    
    Der Assistent für Importaufträge wird angezeigt.
    
4. Geben Sie einen Namen für den PST-Importauftrag ein, und klicken Sie dann auf **Weiter**. Verwenden Sie Kleinbuchstaben, Zahlen, Bindestriche und Unterstriche. Sie dürfen weder Großbuchstaben noch Leerzeichen in dem Namen verwenden.
    
5. Klicken Sie auf der Seite **Möchten Sie Daten hochladen oder ausliefern?** auf **Daten hochladen** und dann auf **Weiter**.
    
    ![Klicken Sie auf "Daten hochladen", um einen Importauftrags für den Netzwerkupload zu erstellen.](../media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. Führen Sie auf der Seite **Daten importieren** einen der folgenden Schritte aus: 
    
    ![Kopieren der SAS-URL und Herunterladen des AzCopy-Tools auf der Seite "Daten importieren"](../media/74411014-ec4b-4e25-9065-404c934cce17.png)
  
    a. Klicken Sie in Schritt 2 auf **SAS-URL für Netzwerkupload anzeigen**. Nachdem die SAS-URL angezeigt wird, klicken Sie auf **In die Zwischenablage kopieren**, fügen Sie die URL in eine Datei ein, und speichern Sie diese, damit Sie später darauf zugreifen können.
    
    b. Klicken Sie in Schritt 3 auf **Azure AzCopy herunterladen**, um das AzCopy-Tool herunterzuladen. Klicken Sie im Popupfenster auf **Ausführen**, um AzCopy zu installieren. 
    
> [!NOTE]
> Sie können die Seite **Daten importieren** geöffnet lassen (für den Fall, dass Sie die SAS-URL erneut kopieren müssen), oder Sie können auf **Abbrechen** klicken, um sie zu schließen. 
 
## <a name="step-2-upload-your-pst-files-to-office-365"></a>Schritt 2: Hochladen Ihrer PST-Dateien in Office 365

Jetzt können Sie Tool "AzCopy.exe" verwenden, um PST-Dateien in Office 365 hochzuladen. Dieses Tool lädt die Dateien an einen Azure Storage-Speicherort in der Microsoft-Cloud hoch und speichert sie dort. Wie zuvor erläutert, befindet sich der Azure Storage-Speicherort, in den Sie Ihre PST-Dateien hochladen, im selben regionalen Microsoft-Rechenzentrum wie Ihre Office 365-Organisation. Damit Sie diesen Schritt ausführen können, müssen sich die PST-Dateien in einer Dateifreigabe oder auf einem Dateiserver in Ihrer Organisation befinden. In diesem Verfahren wird dies als das Quellverzeichnis bezeichnet. Bei jeder Ausführung des Tools AzCopy können Sie ein anderes Quellverzeichnis angeben. 

> [!NOTE]
> Wie bereits erwähnt, sollte jede PST-Datei, die Sie in den Azure-Speicherort hochladen, nicht größer als 20 GB sein. PST-Dateien mit mehr als 20 GB können sich auf die Leistung des PST-Importprozesses auswirken, die Sie in Schritt 6 starten.

1. Öffnen Sie eine Eingabeaufforderung auf dem lokalen Computer.
    
2. Wechseln Sie zu dem Verzeichnis, in dem Sie das Tool "AzCopy.exe" in Schritt 1 installiert haben. Wenn Sie das Tool am Standardspeicherort installiert haben, wechseln Sie zu `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy`.
    
3. Führen Sie den folgenden Befehl aus, um die PST-Dateien in Office365 hochzuladen.

    ```powershell
    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y
    ```

    > [!IMPORTANT] 
    > Sie müssen im vorherigen Befehl ein Verzeichnis als Quellspeicherort angeben. Sie können keine einzelne PST-Datei angeben. Alle PST-Dateien im Quellverzeichnis werden hochgeladen.
 
    In der folgenden Tabelle werden die AzCopy.exe-Parameter und deren erforderliche Werte beschrieben. Die Informationen aus dem vorherigen Schritt werden in den Werten für diese Parameter verwendet.
    
    |**Parameter**|**Beschreibung**|**Beispiel**|
    |:-----|:-----|:-----|
    | `/Source:` <br/> |Gibt das Quellverzeichnis in Ihrer Organisation an, das die PST-Dateien enthält, die in Office 365 hochgeladen werden.  <br/> Beachten Sie, den Wert dieses Parameters in doppelte Anführungszeichen (" ") einzuschließen.  <br/> | `/Source:"\\FILESERVER01\PSTs"` <br/> |
    | `/Dest:` <br/> |Gibt den SAS-Schlüssel an, den Sie in Schritt 1 abgerufen haben.  <br/> Achten Sie darauf, den Wert dieses Parameters in doppelte Anführungszeichen (" ") einzuschließen.<br/><br/>**Bitte beachten:** Wenn Sie die SAS-URL in einem Skript oder in einer Batchdatei verwenden, müssen Sie auf bestimmte Zeichen achten, die Sie vermeiden sollten. Sie müssen beispielsweise `%` in `%%` ändern und `&` in `^&`ändern.<br/><br/>**Tipp:** (Optional) Sie können einen Unterordner am Azure Storage-Speicherort anlegen, in den Sie die PST-Dateien hochladen können. Hierzu fügen Sie den Speicherort des Unterordners (nach "ingestiondata") in die SAS-URL ein. Im ersten Beispiel wird kein Unterordner angegeben. Dies bedeutet, dass die PSTs in den Stammordner (mit Namen *ingestiondata*) des Azure Storage-Speicherorts hochgeladen werden. Im zweiten Beispiel werden die PST-Dateien in einen Unterordner (mit Namen *PSTFiles*) im Stammordner des Azure Storage-Speicherorts hochgeladen.  <br/> | `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> Oder  <br/>  `/Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/V:` <br/> |Gibt ausführliche Statusmeldungen in einer Protokolldatei aus. Standardmäßig hat die ausführliche Protokolldatei den Namen „AzCopyVerbose.log“ und wird im Verzeichnis „%LocalAppData%\Microsoft\Azure\AzCopy“ gespeichert. Wenn Sie einen vorhandenen Speicherort für diese Option angeben, wird das ausführliche Protokoll an diese Datei angefügt.  <br/> Beachten Sie, den Wert dieses Parameters in doppelte Anführungszeichen (" ") einzuschließen.  <br/> | `/V:"c:\Users\Admin\Desktop\Uploadlog.log"` <br/> |
    | `/S` <br/> |Dieser optionale Schalter gibt den rekursiven Modus an, sodass das Tool AzCopy PST-Dateien kopiert, die sich in Unterordnern im Quellverzeichnis befinden, das vom Parameter `/Source:` angegeben wird.  <br/> **Hinweis:** Wenn Sie diesen Schalter einschließen, haben PST-Dateien in Unterordnern einen anderen Dateinamen am Azure Storage-Speicherort, nachdem sie hochgeladen wurden. Sie müssen den genauen Dateipfadnamen in der CSV-Datei angeben, die Sie in Schritt 4 erstellt haben.  <br/> | `/S` <br/> |
    | `/Y` <br/> |Dieser erforderliche Schalter ermöglicht die Verwendung von schreibgeschützten SAS-Token beim Hochladen der PST-Dateien in den Azure Storage-Speicherort. Die in Schritt 1 abgerufene (und im Parameter `/Dest:` angegebene) SAS-URL ist eine schreibgeschützte SAS-URL, weshalb Sie diesen Schalter einschließen müssen. Eine schreibgeschützte SAS-URL hindert Sie nicht daran, den Azure Storage-Explorer zu verwenden, um eine Liste der in den Azure Storage-Speicherort hochgeladenen PST-Dateien anzuzeigen.  <br/> | `/Y` <br/> |

Nachfolgend sehen Sie ein Beispiel der Syntax für das Tool "AzCopy.exe", in dem die tatsächlichen Werte für jeden Parameter verwendet werden:
    
```powershell
  AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
```

Nachdem Sie den Befehl ausgeführt haben, werden Statusmeldungen angezeigt, die den Fortschritt des Hochladens der PST-Dateien anzeigen. Eine endgültige Statusmeldung zeigt die Gesamtzahl der Dateien an, die erfolgreich hochgeladen wurden.

> [!TIP]
> Nachdem Sie den Befehl "AzCopy.exe" erfolgreich ausgeführt und sichergestellt haben, dass alle Parameter richtig sind, speichern Sie eine Kopie der Befehlszeilensyntax in der gleichen (gesicherten) Datei, in die Sie die in Schritt 1 abgerufenen Informationen kopiert haben. Anschließend können Sie diesen Befehl jedes Mal, wenn Sie das Tool "AzCopy.exe" zum Hochladen von PST-Dateien in Office 365 ausführen möchten, in eine Eingabeaufforderung kopieren und einfügen. Der einzige Wert, den Sie möglicherweise ändern müssen, ist der Wert für den `/Source:`-Parameter.  Dies hängt vom Quellverzeichnis ab, in dem sich die PST-Dateien befinden.

## <a name="optional-step-3-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>(Optional) Schritt 3: Anzeigen einer Liste der PST-Dateien, die in Office 365 hochgeladen wurden

Als optionalen Schritt können Sie den Microsoft Azure Storage-Explorer (ein kostenloses Open-Source-Tool) installieren und verwenden, um die Liste der in den Azure-Blob hochgeladenen PST-Dateien anzuzeigen. Es gibt zwei gute Gründe hierfür:
  
- Sie können sicherstellen, dass die PST-Dateien aus dem freigegebenen Ordner oder von dem Dateiserver in Ihrer Organisation erfolgreich in den Azure-Blob hochgeladen wurden.
    
- Sie können den Dateinamen (und den Pfadnamen des Unterordners, sofern eingeschlossen) für jede PST-Datei prüfen, die in den Azure-Blob hochgeladen wurde. Dies ist hilfreich, wenn Sie die PST-Zuordnungsdatei im nächsten Schritt erstellen, da Sie sowohl den Pfadnamen des Ordners als auch den Dateinamen für jede PST-Datei angeben müssen. Durch Überprüfen dieser Namen können mögliche Fehler in der PST-Zuordnungsdatei verhindert werden.
    
Der Microsoft Azure Storage-Explorer befindet sich in der Vorschau. 
  
> [!IMPORTANT]
> Sie können den Azure Storage-Explorer nicht verwenden, um PST-Dateien hochzuladen oder zu ändern. Die einzige unterstützte Methode zum Importieren von PST-Dateien nach Office 365 besteht in der Verwendung von AzCopy. Außerdem können Sie keine PST-Dateien löschen, die Sie in das Azure-Blob hochgeladen haben. Wenn Sie versuchen, eine PST-Datei zu löschen, wird eine Fehlermeldung angezeigt, in der Sie darauf hingewiesen werden, dass Sie nicht über die erforderlichen Berechtigungen verfügen. Beachten Sie, die alle PST-Dateien automatisch aus dem Azure-Speicherbereich gelöscht werden. Wenn keine Importaufträge in Bearbeitung sind, werden alle PST-Dateien im Container **Erfassungsdaten** 30 Tage nach Erstellung des letzten Importauftrags gelöscht.
  
So installieren Sie den Azure Storage-Explorer und Verbinden diesen mit Ihrem -Speicherbereich:
  
1. Laden Sie das Tool [Microsoft Azure Storage-Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842) herunter, und installieren Sie es.
    
2. Starten Sie den Microsoft Azure Storage-Explorer, klicken Sie im linken Bereich mit der rechten Maustaste auf **Speicherkonten**, und klicken Sie dann auf **Mit Azure Storage verbinden**.
    
    ![Klicken Sie mit der rechten Maustaste auf "Speicherkonten", und klicken Sie dann auf "Mit Azure Storage verbinden".](../media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. Klicken Sie auf **SAS-URI (Shared Access Signature) oder -Verbindungszeichenfolge verwenden**, und klicken Sie dann auf **Weiter**.
    
4. Klicken Sie auf **SAS-URI verwenden**, fügen Sie die SAS-URL, die Sie in Schritt 1 abgerufen haben, in das Feld unter **URI** ein, und klicken Sie dann auf **Weiter**. 
    
5. Auf der Seite **Verbindungszusammenfassung** können Sie die Verbindungsinformationen überprüfen und dann auf **Verbinden** klicken.
    
    Der **Container** ingestiondata wird geöffnet. Er enthält die PST-Dateien, die Sie in Schritt 2 hochgeladen haben. Der Container **ingestiondata** befindet sich unter **Speicherkonten** \> **(SAS-Attached Services)** \> **BLOB-Container**. 
    
    ![Im Azure Storage-Explorer wird eine Liste der PST-Dateien angezeigt, die Sie hochgeladen haben.](../media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
6. Wenn Sie mit der Verwendung des Microsoft Azure Storage-Explorers fertig sind, klicken Sie mit der rechten Maustaste auf **ingestiondata**, und klicken Sie dann auf **Trennen**, um die Verbindung mit dem Azure-Speicherbereich zu trennen. Andernfalls wird beim nächsten Anfügen eine Fehlermeldung angezeigt. 
    
    ![Klicken Sie mit der rechten Maustaste auf "ingestion", und klicken Sie dann auf "Trennen", um die Verbindung von Ihrem Azure-Speicherbereich zu trennen.](../media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-4-create-the-pst-import-mapping-file"></a>Schritt 4: Erstellen der PST-Importzuordnungsdatei

Nachdem die PST-Datei Dateien an den Azure Storage-Speicherort für Ihre Office 365-Organisation hochgeladen wurden, besteht der nächste Schritt darin, eine durch Trennzeichen getrennte Datei (CSV) zu erstellen, die angibt, in welche Benutzerpostfächer die PST-Dateien importiert werden. Diese CSV-Datei wird im nächsten Schritt übermittelt, wenn Sie einen PST-Importauftrag erstellen.
  
1. [Laden Sie eine Kopie der PST-Importzuordnungsdatei herunter](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
2. Öffnen oder speichern Sie die CSV-Datei auf Ihrem lokalen Computer. Das folgende Beispiel zeigt eine abgeschlossene PST-Importzuordnungsdatei (in Editor geöffnet). Es ist wesentlich einfacher, Microsoft Excel zum Bearbeiten der CSV-Datei zu verwenden.

    ```text
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,PSTFiles,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,PSTFiles,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,PSTFiles,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,PSTFiles,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```
    
    Die erste Zeile oder Kopfzeile der CSV-Datei enthält die Parameter, die vom PST-Importdienst verwendet werden, um die PST-Dateien in Benutzerpostfächer zu importieren. Die einzelnen Parameternamen werden jeweils durch ein Komma getrennt. Jede Zeile unter der Kopfzeile stellt die Parameterwerte für das Importieren einer PST-Datei in ein bestimmtes Postfach dar. Sie benötigen eine Zeile für jede PST-Datei, die Sie in ein Benutzerpostfach importieren möchten. Vergessen Sie nicht, die Platzhalterdaten in der Zuordnungsdatei durch die tatsächlichen Werte zu ersetzen.

   **Hinweis:** Ändern Sie nichts in der Kopfzeile, einschließlich der SharePoint-Parameter; diese werden während des PST-Importvorgangs ignoriert. 

 3. Verwenden Sie die Informationen in der folgenden Tabelle, um die CSV-Datei mit den erforderlichen Informationen zu füllen.


    |**Parameter**|**Beschreibung**|**Beispiel**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Gibt den Office 365-Dienst an, in den Daten importiert werden. Verwenden Sie `Exchange`, um PST-Dateien in Benutzerpostfächer zu importieren.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Gibt den Speicherort des Ordners am Azure Storage-Speicherort an, an den Sie die PST-Dateien in Schritt 2 hochgeladen haben.  <br/> Wenn Sie in Schritt 2 keinen optionalen Namen für den Unterordner in die SAS-URL im Parameter `/Dest:` eingeschlossen haben, lassen Sie diesen Parameter in der CSV-Datei leer. Wenn Sie aber einen Unterordnernamen eingeschlossen haben, geben Sie ihn in diesem Parameter an (siehe zweites Beispiel). Beim Wert für diesen Parameter muss die Groß-/Kleinschreibung beachtet werden.  <br/> In beiden Fällen schließen Sie "ingestiondata" *nicht* in den Wert für den Parameter `FilePath` ein.  <br/><br/> **Wichtig:** Die Groß-/Kleinschreibung für den Dateipfadnamen muss mit derjenigen identisch sein, die Sie verwendet haben, als Sie in Schritt 2 einen optionalen Unterordnernamen in die SAS-URL im Parameter `/Dest:` eingeschlossen haben. Wenn Sie in Schritt 2 beispielsweise für den Unterordnernamen `PSTFiles` verwendet haben und dann `pstfiles` im Parameter `FilePath` in der CSV-Datei verwenden, schlägt der Import für die PST-Datei fehl. Denken Sie deshalb daran, in beiden Fällen dieselbe Groß-/Kleinschreibung zu verwenden.  <br/> |(leer lassen)  <br/> Oder  <br/>  `PSTFiles` <br/> |
    | `Name` <br/> |Gibt den Namen der PST-Datei an, die in das Benutzerpostfach importiert wird. Beim Wert für diesen Parameter muss die Groß-/Kleinschreibung beachtet werden.  <br/> <br/>**Wichtig:** Die Groß-/Kleinschreibung für den PST-Dateinamen in der CSV-Datei muss mit derjenigen der PST-Datei identisch sein, die in Schritt 2 in den Azure Storage-Speicherort hochgeladen wurde. Wenn Sie beispielsweise `annb.pst` im Parameter `Name` der CSV-Datei verwenden, der Name der tatsächlichen PST-Datei aber `AnnB.pst` lautet, schlägt der Import für diese PST-Datei fehl. Sorgen Sie deshalb dafür, dass im Namen der PST-Datei in der CSV-Datei dieselbe Groß-/Kleinschreibung wie in der tatsächlichen PST-Datei verwendet wird.  <br/> | `annb.pst` <br/> |
    | `Mailbox` <br/> |Gibt die E-Mail-Adresse des Postfachs an, in das die PST-Datei importiert werden soll. Sie können keinen öffentlichen Ordner angeben, da der PST-Importdienst keine Unterstützung für den Import von PST-Dateien in öffentliche Ordner bietet.  <br/> Zum Importieren einer PST-Datei in ein inaktives Postfach müssen Sie für diesen Parameter die Postfach-GUID angeben. Zum Abrufen dieser GUID führen Sie den folgenden PowerShell-Befehl in Exchange Online aus: `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid`. <br/> <br/>**Hinweis:** In einigen Fällen besitzen Sie möglicherweise mehrere Postfächer mit derselben E-Mail-Adresse, bei der ein Postfach ein aktives Postfach ist und sich das andere Postfach in einem Status "vorübergehend gelöscht" (oder "inaktiv") befindet. In diesen Fällen müssen Sie die Postfach-GUID angeben, um das Postfach eindeutig zu identifizieren, in das die PST-Datei importiert werden soll. Zum Abrufen dieser GUID für aktive Postfächer führen Sie den folgenden PowerShell-Befehl aus: `Get-Mailbox <identity of active mailbox> | FL Guid`. Zum Abrufen der GUID für vorübergehend gelöschte (oder inaktive) Postfächer führen Sie diesen Befehl aus: `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`.  <br/> | `annb@contoso.onmicrosoft.com` <br/> Oder  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Gibt an, ob die PST-Datei in das Archivpostfach des Benutzers importiert werden soll. Es gibt zwei Möglichkeiten:  <br/><br/>**FALSE:** Importiert die PST-Datei in das primäre Postfach des Benutzers.  <br/> **TRUE:** Importiert die PST-Datei in das Archivpostfach des Benutzers. Dies setzt voraus, dass das [Archivpostfach des Benutzers aktiviert ist](enable-archive-mailboxes.md). <br/><br/>Wenn Sie diesen Parameter auf `TRUE` festlegen und das Archivpostfach des Benutzers nicht aktiviert ist, schlägt der Import für diesen Benutzer fehl. Wenn der Import für einen Benutzer fehlschlägt (weil sein Archiv nicht aktiviert und diese Eigenschaft auf `TRUE` festgelegt ist), sind die übrigen Benutzer im Importauftrag davon nicht betroffen.  <br/>  Wenn Sie diesen Parameter leer lassen, wird die PST-Datei in das primäre Postfach des Benutzers importiert.  <br/> <br/>**Hinweis:** Zum Importieren einer PST-Datei in ein cloudbasiertes Archivpostfach für einen Benutzer, dessen primäres Postfach lokal gehostet wird, geben Sie für diesen Parameter einfach `TRUE` an und geben Sie die E-Mail-Adresse des lokalen Postfachs des Benutzers für den Parameter `Mailbox` an.  <br/> | `FALSE` <br/> Oder  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Gibt den Postfachordner an, in den die PST-Datei importiert wird.  <br/> <br/> Wenn Sie diesen Parameter leer lassen, wird die PST-Datei in einen neuen Ordner mit dem Namen **Imported** auf der Stammebene des Postfachs importiert (dieselbe Ebene wie der Ordner "Posteingang" und die anderen Standardordner des Postfachs).  <br/> <br/> Wenn Sie `/` angeben, werden Ordner und Elemente auf oberster Ebene in der Ordnerstruktur des Zielpostfachs oder -archivs importiert. Wenn im Zielpostfach ein Ordner vorhanden ist (z. b. Standardordner wie "Posteingang", "Gesendete Elemente" und "Gelöschte Elemente"), werden die Elemente dieses Ordners in der PST-Datei in den vorhandenen Ordner im Zielpostfach zusammengeführt. Wenn die PST-Datei beispielsweise einen Ordner "Posteingang" enthält, werden die Elemente in diesem Ordner in den Ordner "Posteingang" im Zielpostfach importiert. Neue Ordner werden erstellt, wenn Sie in der Ordnerstruktur des Zielpostfachs nicht vorhanden sind.  <br/><br/>  Wenn Sie `/<foldername>` angeben, werden Elemente und Ordner in der PST-Datei in einen Ordner mit dem Namen *\<Ordnername\>* importiert. Bei Verwendung von `/ImportedPst` würden beispielsweise Elemente in einen Ordner mit dem Namen **ImportedPst** importiert. Dieser Ordner befindet sich im Postfach des Benutzers auf der gleichen Ebene wie der Ordner "Posteingang".  <br/><br/> **Tipp:** Sie sollten ein paar Testbatches ausführen, um mit diesem Parameter zu experimentieren, damit Sie den besten Ordnerspeicherort für das Importieren der PST-Dateien ermitteln können.  <br/> |(leer lassen)  <br/> Oder  <br/>  `/` <br/> Oder  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Dieser optionale Parameter gibt einen numerischen Wert für die Codepage an, die zum Importieren von PST-Dateien im ANSI-Dateiformat verwendet werden muss. Der Parameter wird zum Importieren von PST-Dateien aus chinesischen, japanischen und koreanischen (CJK) Organisationen verwendet, weil in diesen Sprachen normalerweise ein Doppelbyte-Zeichensatz (double byte character set, DBCS) verwendet wird. Wenn dieser Parameter nicht verwendet wird, um PST-Dateien für Sprachen zu importieren, die DBCS für die Namen von Postfachordnern verwenden, sind die Ordnernamen nach dem Import oft nicht leserlich.  <br/><br/> Eine Liste von unterstützten Werten, die für diesen Parameter verwendet werden müssen, finden Sie unter [CodePage-Bezeichner](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/> <br/>**Hinweis:** Wie vorstehend erwähnt, ist dies ein optionaler Parameter, den Sie in die CSV-Datei nicht einschließen müssen. Sie können ihn aber auch einschließen und den Wert für eine oder mehrere Zeilen leer lassen.  <br/> |(leer lassen)  <br/> Oder  <br/>  `932` (dies ist der Codepagebezeichner für ANSI/OEM – Japanisch)  <br/> |
    | `SPFileContainer` <br/> |Lassen Sie diesen Parameter für den PST-Import leer.  <br/> |Nicht zutreffend  <br/> |
    | `SPManifestContainer` <br/> |Lassen Sie diesen Parameter für den PST-Import leer.  <br/> |Nicht zutreffend  <br/> |
    | `SPSiteUrl` <br/> |Lassen Sie diesen Parameter für den PST-Import leer.  <br/> |Nicht zutreffend  <br/> |

## <a name="step-5-create-a-pst-import-job-in-office-365"></a>Schritt 5: Erstellen eines PST-Importauftrags in Office 365

Der nächste Schritt besteht darin, den PST-Importauftrag im Importdienst in Office 365 zu erstellen. Wie zuvor beschrieben, übermitteln Sie die erstellte PST-Importzuordnungsdatei in Schritt 4. Nachdem Sie den Auftrag erstellt haben, analysiert Office 365 die Daten in den PST-Dateien und gibt Ihnen die Möglichkeit, die Daten zu filtern, die tatsächlich in die Postfächer importiert werden, die in der PST-Importzuordnungsdatei angegeben sind (siehe [Schritt 6](#step-6-filter-data-and-start-the-pst-import-job)).
  
1. Navigieren Sie zu [https://protection.office.com](https://protection.office.com), und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365-Organisation an. 
    
2. Klicken Sie im linken Bereich des Security & Compliance Center auf **Information Governance > Import > Importieren von PST-Dateien**.
    
3. Klicken Sie auf der Seite **Import von PST-Dateien** ![Symbol hinzufügen](../media/ITPro-EAC-AddIcon.gif) **Neuer Importauftrag**.
    
    **Hinweis:** Sie müssen über die erforderlichen Berechtigungen für den Zugriff auf die Seite **Import** im Security & Compliance Center verfügen, um einen Importauftrag erstellen zu können. Weitere Informationen finden Sie im Abschnitt **Bevor Sie beginnen**. 
    
4. Geben Sie einen Namen für den PST-Importauftrag ein, und klicken Sie dann auf **Weiter**. Verwenden Sie Kleinbuchstaben, Zahlen, Bindestriche und Unterstriche. Sie dürfen weder Großbuchstaben noch Leerzeichen in dem Namen verwenden.
    
5. Klicken Sie auf der Seite **Möchten Sie Daten hochladen oder ausliefern?** auf **Daten hochladen** und dann auf **Weiter**.
    
    ![Klicken Sie auf "Daten hochladen", um einen Importauftrags für den Netzwerkupload zu erstellen.](../media/e59f9dc3-ccde-44ff-ac38-c4e39d76ae85.png)
  
6. Klicken Sie in Schritt 4 auf der Seite zum **Importieren von Daten** auf die Kontrollkästchen zur Angabe, dass **das Hochladen der Dateien abgeschlossen ist** und **Zugriff auf die Zuordnungsdatei besteht**, und klicken Sie dann auf **Weiter**.
    
    ![Klicken Aktivieren Sie die beiden Kontrollkästchen in Schritt 4.](../media/9f2427e8-3af2-4e27-95e6-a9f08430d3d8.png)
  
7. Klicken Sie auf der Seite **Auswählen der Zuordnungsdatei** auf **Zuordnungsdatei auswählen**, um die PST-Importzuordnungsdatei zu übermitteln, die Sie in Schritt 4 erstellt haben. 
    
    ![Klicken Sie auf "Zuordnungsdatei auswählen", um die CSV-Datei zu übermitteln, die Sie für den Importvorgang erstellt haben.](../media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
8. Wenn der Name der CSV-Datei unter **Name der Zuordnungsdatei** angezeigt wird, klicken Sie auf **Überprüfen**, um die CSV-Datei auf Fehler zu überprüfen. 
    
    ![Klicken Sie auf "Überprüfen", um die CSV-Datei auf Fehler zu überprüfen.](../media/4680999d-5538-4059-b878-2736a5445037.png)
  
    Die CSV-Datei muss erfolgreich überprüft werden, um einen PST-Importauftrag zu erstellen. Der Dateiname wird grün angezeigt, wenn die Überprüfung der Datei erfolgreich war. Wenn die Überprüfung fehlschlägt, klicken Sie auf den Link **Protokoll anzeigen**. Der Bericht mit den Überprüfungsfehlern wird geöffnet, in dem für jede Zeile in der Datei, in der ein Fehler aufgetreten ist, eine Fehlermeldung aufgeführt ist.
    
9. Nachdem die PST-Zuordnungsdatei erfolgreich überprüft wurde, lesen Sie das Dokument mit den allgemeinen Geschäftsbedingungen, und aktivieren Sie dann das Kontrollkästchen.
    
10. Klicken Sie auf **Speichern**, um den Auftrag zu übermitteln, und klicken Sie dann auf **Schließen**, nachdem der Auftrag erfolgreich erstellt wurde. 
    
    Es wird eine Status-Flyout-Seite mit dem Status **Analyse in Bearbeitung ** angezeigt, und der neue Importauftrag wird in der Liste auf der Seite **PST-Dateien importieren** angezeigt. 
    
11. Klicken Sie auf **Aktualisieren** ![Aktualisieren-Symbol](../media/O365-MDM-Policy-RefreshIcon.gif), um die Statusinformationen zu aktualisieren, die in der Spalte **Status** angezeigt werden. Wenn die Analyse abgeschlossen ist und die Daten importiert werden können, wird der Status in **Analyse abgeschlossen** geändert.
    
    Sie können auf den Importauftrag klicken, um die Status-Flyout-Seite anzuzeigen, die ausführlichere Informationen zu dem Importauftrag enthält, z. B. den Status jeder PST-Datei, die in der Zuordnungsdatei aufgeführt ist.
 
## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Schritt 6: Filtern von Daten und Starten des PST-Importauftrags

Nachdem Sie den Importauftrag in Schritt 5 erstellt haben, analysiert Office 365 die Daten in den PST-Dateien (auf gefahrlose und sichere Weise), indem das Alter der Elemente und die unterschiedlichen Nachrichtentypen identifiziert werden, die in den PST-Dateien enthalten sind. Wenn die Analyse abgeschlossen ist und die Daten für den Import bereit sind, haben Sie die Möglichkeit, alle in den PST-Dateien enthaltenen Daten zu importieren oder die zu importierenden Daten einzuschränken, indem Sie Filter festlegen, mit denen gesteuert wird, welche Daten importiert werden.
  
1. Klicken Sie auf der Seite **Import von PST-Dateien** im Security & Compliance Center auf **bereit zum Import in Office 365** für den Importvorgang, den Sie in Schritt 5 erstellt haben. 
    
    ![Klicken Sie neben dem von Ihnen erstellten Importvorgang auf "Bereit für den Import in Office 365".](../media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Nun wird eine Flyout-Seite mit Informationen zu den PST-Dateien und anderen Informationen zur Importaufgabe angezeigt.
    
2. Klicken Sie auf der Flyoutseite auf **In Office 365 importieren**.
    
    Die Seite **Ihre Daten filtern** wird angezeigt. Sie enthält die Datenerkenntnisse, die sich aus der Analyse ergeben haben, die Office 365 für die PST-Dateien ausgeführt hat, einschließlich Informationen über das Alter der Daten. An diesem Punkt haben Sie die Möglichkeit, die zu importierenden Daten zu filtern oder alle Daten ungeändert zu importieren. 
    
    ![Sie können die Daten in den PST-Dateien kürzen oder alles importieren](../media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
3. Führen Sie einen der folgenden Schritte aus:
    
    a. Um die Daten, die Sie importieren, zu trimmen, klicken Sie auf **Ja, ich möchte meine Daten vor dem Import filtern**.
    
    Detaillierte schrittweise Anweisungen zum Filtern der Daten in den PST-Dateien und anschließenden Starten des Importvorgangs finden Sie unter [Filtern von Daten beim Importieren von PST-Dateien in Office 365](filter-data-when-importing-pst-files.md).
    
    Oder
    
    b. Um alle Daten zu importieren, die sich in den PST-Dateien befinden, klicken Sie auf **Nein, ich möchte alles importieren**, und klicken Sie auf **Weiter**.
    
4. Wenn Sie sich entschieden haben, alle Daten zu importieren, klicken Sie auf **Daten importieren**, um den Importvorgang zu starten. 
    
    Der Status des Importauftrags wird auf der Seite **Import von PST-Dateien** angezeigt. Klicken Sie auf ![Aktualisieren-Symbol](../media/O365-MDM-Policy-RefreshIcon.gif) **Aktualisieren**, um die Statusinformationen zu aktualisieren, die in der Spalte **Status** angezeigt werden. Klicken Sie auf den Importauftrag, um die Status-Flyout-Seite anzuzeigen, auf der die Statusinformationen zu jeder zu importierenden PST-Datei angezeigt werden. 

## <a name="how-the-import-process-works"></a>Funktionsweise des Importvorgangs
  
Sie können die Netzwerkuploadoption und den Office 365-Importdienst verwenden, um PST-Dateien in einem Massenimport in Benutzerpostfächer zu importieren. Netzwerkupload bedeutet, dass Sie die PST-Dateien in einen temporären Speicherbereich in der Microsoft-Cloud hochladen. Der Office 365-Importdienst kopiert die PST-Dateien dann aus dem Speicherbereich in die Postfächer der Zielbenutzer.
  
Es folgen eine Darstellung und eine Beschreibung des Netzwerkuploadprozesses, in dem PST-Dateien in Postfächer in Office 365 importiert werden.
  
![Workflow des Netzwerkuploadprozesses zum Importieren von PST-Dateien in Office 365](../media/9e05a19e-1e7a-4f1f-82df-9118f51588c4.png)
  
1. **PST-Importtool und Schlüssel für den privaten Azure Storage-Speicherort herunterladen**: Der erste Schritt besteht darin, das Befehlszeilentool AzCopy und einen Zugriffsschlüssel herunterzuladen, die dazu verwendet werden, die PST-Dateien in einen Azure Storage-Speicherort in der Microsoft Cloud hochzuladen. Sie erhalten das Tool und den Schlüssel über die Seite **Import** im Security & Compliance Center. Der Schlüssel, der als SAS-Schlüssel (Shared Access Signature) bezeichnet wird, stellt Ihnen die Berechtigungen bereit, die erforderlich sind, um PST-Dateien in einen privaten und sicheren Azure Storage-Speicherort hochzuladen. Dieser Zugriffsschlüssel ist für Ihr Unternehmen eindeutig und verhindert nicht autorisierten Zugriff auf Ihre PST-Dateien, nachdem diese in die Microsoft-Cloud hochgeladen wurden. Für das Importieren von PST-Dateien in Office 365 ist es nicht erforderlich, dass Ihre Organisation über ein eigenes Azure-Abonnement verfügt. 
    
2. **PST-Dateien in den Azure Storage-Speicherort hochladen**: Der nächste Schritt besteht darin, mit dem (in Schritt 1 heruntergeladenen) Tool "AzCopy.exe" Ihre PST-Dateien in einen Azure Storage-Speicherort hochzuladen, der sich im selben regionalen Microsoft-Datencenter befindet wie Ihre Office 365-Organisation. Damit Sie die PST-Dateien, die Sie in Office 365 importieren möchten, hochladen können, müssen sich diese in einer Dateifreigabe oder auf einem Dateiserver in Ihrer Organisation befinden.
    
    Sie können einen optionalen Schritt ausführen, in dem Sie die Liste der PST-Dateien anzeigen können, nachdem diese in den Azure Storage-Speicherort hochgeladen wurden.
    
3. **Erstellung einer PST-Importzuordnungsdatei**: Nachdem die PST-Dateien in den Azure Storage-Speicherort hochgeladen wurden, besteht der nächste Schritt darin, eine Datei mit kommagetrennten Werten (CSV-Datei) zu erstellen, die angibt, in welche Benutzerpostfächer die PST-Dateien importiert werden (wobei eine PST-Datei in das primäre Postfach eines Benutzers oder in dessen Archivpostfach importiert werden kann). Der Office 365-Importdienst verwendet die Informationen in der CSV-Datei, um die PST-Dateien zu importieren.
    
4. **Erstellen eines PST-Importauftrags**: Im nächsten Schritt wird auf der Seite **PST_Dateien importieren** im Security & Compliance Center ein PST-Importauftrag erstellt und die im vorherigen Schritt erstellte PST-Importzuordnungsdatei gesendet. Nachdem Sie den Importauftrag erstellt haben, analysiert Office 365 die Daten in den PST-Dateien und gibt Ihnen die Möglichkeit, Filter festzulegen, mit denen gesteuert wird, welche Daten tatsächlich in die Postfächer importiert werden, die in der PST-Importzuordnungsdatei angegeben sind. 
    
5. **PST-Daten, die in Postfächer importiert werden sollen, filtern**: Nachdem der Importauftrag erstellt und gestartet wurde, analysiert Office 365 die Daten in den PST-Dateien (gefahrlos und sicher), indem das Alter der Elemente und die verschiedenen Nachrichtentypen bestimmt werden, die in den PST-Dateien enthalten sind. Wenn die Analyse abgeschlossen ist und die Daten für den Import bereit sind, haben Sie die Möglichkeit, alle in den PST-Dateien enthaltenen Daten zu importieren oder die zu importierenden Daten einzuschränken, indem Sie Filter festlegen, mit denen gesteuert wird, welche Daten importiert werden.
    
6. **Starten des PST-Importauftrags**: Nachdem der Importauftrag gestartet wurde, verwendet Office 365 die Informationen in der PST-Importzuordnungsdatei, um die PST-Dateien aus dem Azure Storage-Speicherort in Benutzerpostfächer zu importieren. Statusinformationen zu dem Importauftrag (einschließlich Informationen zu jeder PST-Datei, die importiert wird) werden auf der Seite **PST-Dateien importieren** im Security & Compliance Center angezeigt. Wenn der Importauftrag abgeschlossen ist, wird sein Status auf **Abgeschlossen** festgelegt.
  
## <a name="more-information"></a>Weitere Informationen

- Warum PST-Dateien in Office 365 importieren?
    
  - Es ist eine gute Möglichkeit zum Importieren archivierter Nachrichtendaten Ihrer Organisation in Office 365.
    
  - Die Daten sind für den Benutzer auf allen Geräten verfügbar, da sie in der Cloud gespeichert sind.
    
  - Auf diese Weise können Sie Complianceanforderungen Ihrer Organisation erfüllen, indem Sie Office 365-Compliancefeatures auf die Daten aus den importierten PST-Dateien anwenden. Dies umfasst Folgendes:
    
  - Aktivieren von [Archivpostfächern](enable-archive-mailboxes.md) und [automatisch erweiternden Archiven](enable-unlimited-archiving.md), um Benutzern zusätzlichen Postfachspeicher zum Speichern der importierten Daten bereitzustellen. 
    
  - Kennzeichnen von Postfächern für [Beweissicherungsverfahren](https://go.microsoft.com/fwlink/?linkid=856286), um die importierten Daten aufzubewahren. 
    
  - Verwenden von Microsoft [eDiscovery-Tools](search-for-content.md), um die importierten Daten zu durchsuchen. 
    
  - Verwenden von [Office 365-Aufbewahrungsrichtlinien](retention-policies.md), um zu steuern, wie lange die importierten Daten aufbewahrt und welche Maßnahmen nach Ablauf des Aufbewahrungszeitraums durchgeführt werden. 
    
  - Durchsuchen des [Office 365-Überwachungsprotokolls](search-the-audit-log-in-security-and-compliance.md) nach postfachbezogenen Ereignissen, die sich auf die importierten Daten auswirken. 
    
  - Importieren von Daten in [inaktive Postfächer](create-and-manage-inactive-mailboxes.md), um Daten für Compliancezwecke zu archivieren. 
    
  - Verwenden von [Richtlinien zur Verhinderung von Datenverlust](data-loss-prevention-policies.md), um zu verhindern, dass vertrauliche Daten außerhalb Ihrer Organisation offengelegt werden. 
  
- Hier finden Sie ein Beispiel für die SAS-URL (Shared Access Signature), den Sie in Schritt 1 abgerufen haben. Dieses Beispiel enthält auch die Syntax für den Befehl, den Sie im Tool "AzCopy.exe" zum Hochladen von PST-Dateien in Office 365 ausführen. Schützen Sie diese SAS-URL unbedingt genauso wie Kennwörter und andere sicherheitsbezogene Informationen.

    ```text
    SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D

    AzCopy.exe /Source:<Location of PST files> /Dest:<SAS URL> /V:<Log file location> /Y

    EXAMPLES

    This example uploads PST files to the root of the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    
    This example uploads PST files to a subfolder named PSTFiles  in the Azure storage location:

    AzCopy.exe /Source:"\\FILESERVER1\PSTs" /Dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/PSTFiles?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D" /V:"c:\Users\Admin\Desktop\AzCopy1.log" /Y
    ```

- Wie weiter oben erläutert, aktiviert der Office 365-Import-Dienst die Einstellung zum Anhalten der Aufbewahrungszeit (für eine unbestimmte Dauer), nachdem PST-Dateien in ein Postfach importiert wurden. Dies bedeutet: Die Eigenschaft *RetentionHoldEnabled* wird auf **true** festgelegt, sodass die dem Postfach zugewiesene Aufbewahrungsrichtlinie nicht verarbeitet wird. Dadurch erhält der Postfachbesitzer Zeit zum Verwalten der neu importierten Nachrichten, indem verhindert wird, dass eine Lösch- oder Archivrichtlinie ältere Nachrichten löscht oder archiviert. Hier sind einige Schritte, die Sie zum Verwalten des Anhaltens der Aufbewahrungszeit ausführen können: 
    
    - Nach einem bestimmten Zeitraum können Sie das Anhalten der Aufbewahrungszeit deaktivieren, indem Sie den Befehl **Set-Mailbox -RetentionHoldEnabled $false** ausführen. Entsprechende Anweisungen finden Sie unter [Anhalten der Aufbewahrungszeit für ein Postfach](https://go.microsoft.com/fwlink/p/?LinkId=544749).
    
   - Sie können das Anhalten der Aufbewahrungszeit so konfigurieren, dass es an irgendeinem Datum in der Zukunft deaktiviert wird. Dazu führen Sie den Befehl **Set-Mailbox-EndDateForRetentionHold *date*** aus. Nehmen wir beispielsweise an, dass das heutige Datum der 1. Juni 2016 ist und das Anhalten der Aufbewahrungszeit in 30 Tagen deaktiviert werden soll. Dann würden Sie folgenden Befehl ausführen:  **Set-Mailbox -EndDateForRetentionHold 7/1/2016**. In diesem Szenario würden Sie für die Eigenschaft **RetentionHoldEnabled** den Wert *True* beibehalten. Weitere Informationen finden Sie unter [Set-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
   - Sie können die Einstellungen für die dem Postfach zugewiesene Aufbewahrungsrichtlinie ändern, damit ältere importierte Elemente nicht sofort gelöscht oder in das Archivpostfach des Benutzers verschoben werden. So könnten Sie beispielsweise die Aufbewahrungszeit bei einer Lösch- oder Archivrichtlinie, die dem Postfach zugewiesen wurde, verlängern. In diesem Szenario würden Sie das Anhalten der Aufbewahrungszeit für das Postfach deaktivieren, nachdem Sie die Einstellungen der Aufbewahrungsrichtlinie geändert haben. Weitere Informationen finden Sie unter [Einrichten einer Archivierungs- und Löschrichtlinie für Postfächer in Ihrer Office 365-Organisation](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
