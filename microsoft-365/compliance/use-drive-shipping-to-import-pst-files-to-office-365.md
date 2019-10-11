---
title: Verwenden des Laufwerk Versands zum Importieren Ihrer Organisations-PST-Dateien in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
description: 'Für Administratoren: Hier erfahren Sie, wie Sie PST-Dateien Ihrer Organisation in Office 365 Postfächer Massenimportieren, indem Sie PST-Dateien auf eine Festplatte kopieren und dann an Microsoft versenden. '
ms.openlocfilehash: 033eee7a5ec33a8839542c8a942c4a1178968cec
ms.sourcegitcommit: cbf117a4cd92a907115c9f10752f3c557361e586
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2019
ms.locfileid: "37440662"
---
# <a name="use-drive-shipping-to-import-your-organization-pst-files-to-office-365"></a>Verwenden des Laufwerk Versands zum Importieren Ihrer Organisations-PST-Dateien in Office 365

**Dieser Artikel richtet sich an Administratoren. Versuchen Sie, PST-Dateien in Ihr eigenes Postfach zu importieren? Siehe [Importieren von e-Mails, Kontakten und Kalendern aus einer Outlook. PST-Datei](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Verwenden Sie die Office 365 Import-Dienst und fahren Sie mit dem Versand von Massenimport-PST-Dateien in Benutzerpostfächer. Beim Laufwerkversand kopieren Sie die PST-Dateien auf eine Festplatte und senden diese auf dem Postweg an Microsoft. Wenn Microsoft Ihre Festplatte empfängt, kopiert das Personal des Rechenzentrums die Daten von der Festplatte in einen Speicherbereich in der Microsoft-Cloud. Anschließend haben Sie die Möglichkeit, die in die Zielpostfächer importierten PST-Daten zu trimmen, indem Sie Filter festlegen, mit denen gesteuert wird, welche Daten importiert werden. Nachdem Sie den Importauftrag gestartet haben, importiert der Import Dienst die PST-Daten aus dem Speicherbereich in Benutzerpostfächer. Das Verwenden des Laufwerk Versands zum Importieren von PST-Dateien in Benutzerpostfächer ist eine Möglichkeit, die e-Mails Ihrer Organisation in Office 365 zu migrieren.
  
Hier sind die erforderlichen Schritte zum Importieren von PST-Dateien in Office 365 Postfächer mithilfe des Laufwerk Versands:
  
[Schritt 1: Herunterladen des Secure Storage Key und des PST-Import Tools](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[Schritt 2: Kopieren der PST-Dateien auf die Festplatte](#step-2-copy-the-pst-files-to-the-hard-drive)

[Schritt 3: Erstellen der PST-Import Zuordnungsdatei](#step-3-create-the-pst-import-mapping-file)

[Schritt 4: Erstellen eines PST-Importauftrags in Office 365](#step-4-create-a-pst-import-job-in-office-365)

[Schritt 5: Versenden der Festplatte an Microsoft](#step-5-ship-the-hard-drive-to-microsoft)

[Schritt 6: Filtern von Daten und Starten des PST-Import Auftrags](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> Sie müssen Schritt 1 einmal ausführen, um den sicheren Speicherschlüssel und das Import Tool zu laden. Nachdem Sie diese Schritte ausgeführt haben, befolgen Sie Schritt 2 bis Schritt 6 jedes Mal, wenn Sie eine Festplatte an Microsoft senden möchten. 
  
Häufig gestellte Fragen zur Verwendung des Laufwerk Versands zum Importieren von PST-Dateien in Office 365 finden Sie unter [FAQs für die Verwendung des Laufwerk Versands zum Importieren von PST-Dateien](faqimporting-pst-files-to-office-365.md#using-drive-shipping-to-import-pst-files). 
  
## <a name="before-you-begin"></a>Bevor Sie beginnen

- Sie müssen in Exchange Online über die Rolle "Postfachimport export" verfügen, um PST-Dateien in Office 365 Postfächer zu importieren. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. You can add the Mailbox Import Export role to the Organization Management role group. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und sich selbst als Mitglied hinzufügen. Weitere Informationen finden Sie im Abschnitt "Hinzufügen einer Rolle zu einer Rollengruppe" oder unter "Erstellen einer Rollengruppe" in [Verwalten von Rollengruppen](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Um außerdem Importaufträge im Security #a0 Compliance Center zu erstellen, muss eine der folgenden Anforderungen erfüllt sein:
    
  - Sie müssen in Exchange Online die Rolle "e-Mail-Empfänger" zugewiesen haben. By default, this role is assigned to the Organization Management and Recipient Management roles groups.
    
    Oder
    
  - Sie müssen ein globaler Administrator in Ihrer Office 365 Organisation sein.
    
    > [!TIP]
    > Sie sollten in Exchange Online eine neue Rollengruppe erstellen, die speziell für den Import von PST-Dateien in Office 365 vorgesehen ist. Weisen Sie die Rollen "Postfachimport" und "e-Mail-Empfänger" für die für den Import von PST-Dateien erforderliche Mindeststufe von Berechtigungen der neuen Rollengruppe zu, und fügen Sie dann Mitglieder hinzu. 
  
- Sie müssen die PST-Dateien, die Sie auf die Festplatte kopieren möchten, auf einem Dateiserver oder einem freigegebenen Ordner in Ihrer Organisation speichern. In Schritt 2 führen Sie das Azure Import Export Tool ("waimportexport. exe) aus, das die auf diesem Dateiserver oder freigegebenen Ordner gespeicherten PST-Dateien auf die Festplatte kopiert.
    
- Nur 2,5-Zoll-Solid-State-Laufwerke (SSDs) oder 2,5-Zoll-oder 3,5-Zoll-SATA II/III-Festplattenlaufwerke werden für die Verwendung mit dem Office 365-Import Dienst unterstützt. You can use hard drives up to 10 TB. Bei Import Aufträgen wird nur das erste Datenvolume auf der Festplatte verarbeitet. The data volume must be formatted with NTFS. Wenn Sie Daten auf eine Festplatte kopieren, können Sie Sie direkt über einen 2,5-Zoll-SSD oder 2,5-Zoll-oder 3,5-Zoll-SATA II/III-Anschluss anhängen oder extern mit einem externen 2,5-Zoll-SSD oder einem 2,5-Zoll-oder 3,5-Zoll-SATA II/III-USB-Adapter verbinden.
    
    > [!IMPORTANT]
    > Externe Festplatten, die mit einem integrierten USB-Adapter ausgeliefert werden, werden vom Office 365-Import Dienst nicht unterstützt. Additionally, the disk inside the casing of an external hard drive can't be used. Please don't ship external hard drives. 
  
- Die Festplatte, auf die Sie die PST-Dateien kopieren, muss mit BitLocker verschlüsselt sein. Das Tool WAImportExport.exe, das Sie in Schritt 2 ausführen, unterstützt Sie bei der Einrichtung von BitLocker. Außerdem wird ein BitLocker-Verschlüsselungsschlüssel generiert, den Microsoft-Rechenzentrumsmitarbeiter für den Zugriff auf das Laufwerk verwenden, um die PST-Dateien in den Azure-Speicherbereich in der Microsoft-Cloud hochzuladen.
    
- Der Laufwerk Versand steht über einen Microsoft Enterprise-Vertrag (EA) zur Verfügung. Der Laufwerk Versand ist über einen Microsoft-Produkt-und Dienstleistungsvertrag (MPSA) nicht verfügbar.
    
- Die Kosten für den Import von PST-Dateien in Office 365 Postfächer mithilfe des Laufwerk Versands sind $2 USD pro GB Daten. For example, if you ship a hard drive that contains 1,000 GB (1 TB) of PST files, the cost is $2,000 USD. You can work with a partner to pay the import fee. Informationen zum Suchen eines Partners finden Sie unter [Suchen nach Ihrem Office 365 Partner oder Wiederverkäufer](https://go.microsoft.com/fwlink/p/?LinkId=785197).
    
- Sie bzw. Ihre Organisation müssen über ein Konto bei FedEx oder DHL verfügen. 
    
  - Organisationen in den Vereinigten Staaten, in Brasilien und in Europa müssen FedEx-Konten besitzen.
    
  - Organisationen in Ostasien, Südostasien, Japan, Republik Korea und Australien müssen über DHL-Konten verfügen.
    
    Microsoft verwendet (und lädt) dieses Konto, um die Festplatte wieder an Sie zurückzugeben.
    
- Die Festplatte, die Sie an Microsoft senden, kann internationale Grenzen überschreiten. In diesem Fall müssen Sie sicherstellen, dass die Festplatte und die darin enthaltenen Daten gemäß den geltenden Gesetzen importiert und/oder exportiert werden. Überprüfen Sie vor dem Versand einer Festplatte mit ihren Beratern, ob das Laufwerk und die Daten legal an das identifizierte Microsoft Data Center ausgeliefert werden können. Auf diese Weise wird sichergestellt, dass Microsoft rechtzeitig erreicht werden kann.
    
- Bei diesem Verfahren werden ein sicherer Speicherschlüssel und ein BitLocker-Verschlüsselungsschlüssel kopiert und gespeichert. Ergreifen Sie entsprechende Vorsichtsmaßnahmen, um diese Schlüssel so zu schützen, wie Sie Kennwörter oder andere Sicherheitsinformationen schützen würden. Sie können sie zum Beispiel in einem kennwortgeschützten Microsoft Word-Dokument oder auf einem verschlüsselten USB-Laufwerk speichern. Ein Beispiel für diese Tasten finden Sie im Abschnitt [Weitere Informationen](#more-information) . 
    
- Nachdem PST-Dateien in ein Office 365 Postfach importiert wurden, ist die Aufbewahrungsdauer für das Postfach auf unbestimmte Zeit aktiviert. Dies bedeutet, dass die dem Postfach zugewiesene Aufbewahrungsrichtlinie erst dann verarbeitet wird, wenn Sie die Aufbewahrungszeit deaktivieren oder ein Datum zum Deaktivieren des Haltestatus festlegen. Warum tun wir das? Wenn Nachrichten, die in ein Postfach importiert werden, alt sind, werden Sie möglicherweise endgültig gelöscht (bereinigt), da ihre Aufbewahrungsdauer auf der Grundlage der für das Postfach konfigurierten Aufbewahrungseinstellungen abgelaufen ist. Wenn Sie das Postfach auf Aufbewahrungszeit halten, erhält der Postfachbesitzer Zeit, diese neu importierten Nachrichten zu verwalten, oder Sie erhalten Zeit, um die Aufbewahrungseinstellungen für das Postfach zu ändern. Im Abschnitt [Weitere Informationen](#more-information) finden Sie Vorschläge zum Verwalten des Aufbewahrungs Speichers. 
    
- Standardmäßig beträgt die maximale Nachrichtengröße, die von einem Office 365 Postfach empfangen werden kann, 35 MB. Das liegt daran, dass der Standardwert für die *MaxReceiveSize* -Eigenschaft für ein Postfach auf 35 MB festgelegt ist. Der Grenzwert für die maximale Nachrichtenempfangs Größe in Office 365 beträgt jedoch 150 MB. Wenn Sie also eine PST-Datei importieren, die ein Element größer als 35 MB enthält Office 365, wird der Wert der *MaxReceiveSize* -Eigenschaft des Zielpostfachs automatisch in 150 MB geändert. Auf diese Weise können Nachrichten bis zu 150 MB in Benutzerpostfächer importiert werden. 
    
    > [!TIP]
    > Um die Nachrichtenempfangs Größe für ein Postfach zu identifizieren, können Sie diesen Befehl in Exchange Online PowerShell: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`ausführen. 
  
- Sie können PST-Dateien in ein inaktives Postfach in Office 365 importieren. Geben Sie dazu die GUID des inaktiven Postfachs im `Mailbox` Parameter in der PST-Import Zuordnungsdatei an. Weitere Informationen finden Sie unter [Schritt 3: Erstellen der PST-Import Zuordnungsdatei](#step-3-create-the-pst-import-mapping-file) . 
    
- In einer Exchange-hybridbereitstellung können Sie PST-Dateien in ein Cloud-basiertes Archivpostfach für einen Benutzer importieren, dessen primäres Postfach lokal ist. Führen Sie dazu in der PST-Import Zuordnungsdatei folgende Schritte aus:
    
  - Geben Sie die e-Mail-Adresse für das lokale Postfach des Benutzers `Mailbox` im Parameter an. 
    
  - Geben Sie den Wert **true** im `IsArchive` Parameter an. 
    
    Weitere Informationen finden Sie unter [Schritt 3: Erstellen der PST-Import Zuordnungsdatei](#step-3-create-the-pst-import-mapping-file) . 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>Schritt 1: Herunterladen des Secure Storage Key und des PST-Import Tools

Der erste Schritt besteht darin, den Schlüssel für sichere Speicherung und das Tool herunterzuladen und in Schritt 2 zum Kopieren von PST-Dateien auf die Festplatte zu verwenden.
  
> [!IMPORTANT]
> Sie müssen Azure Import/Export Tool Version 1 (WAimportExportV1) verwenden, um PST-Dateien erfolgreich mithilfe der Laufwerk Versandart zu importieren. Version 2 des Azure-Import/Export-Tools wird nicht unterstützt, und die Verwendung dieser Funktion führt zu einer fehlerhaften Vorbereitung der Festplatte für den Importauftrag. Stellen Sie sicher, dass Sie das Azure-Import/Export-Tool aus dem Security #a0 Compliance Center herunterladen, indem Sie die Verfahren in diesem Schritt befolgen. 
  
1. Wechseln Sie [https://protection.office.com/](https://protection.office.com/) zu, und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation an. 
    
2. Klicken Sie im linken Bereich des Security #a0 Compliance Center auf **Data Governance** \> **Import**.
    
    > [!NOTE]
    > Wie bereits erwähnt, müssen Sie im Security #a0 Compliance Center die entsprechenden Berechtigungen für den Zugriff auf die **Import** Seite erhalten. 
  
3. Klicken Sie **** ![auf der Seite importieren auf Symbol](media/ITPro-EAC-AddIcon.gif) **neuer Importauftrag**hinzufügen.
    
4. Geben Sie im Assistenten zum Importieren von Aufträgen einen Namen für den PST-Importauftrag ein, und klicken Sie dann auf **weiter**. Verwenden Sie Kleinbuchstaben, Zahlen, Bindestriche und Unterstriche. Sie können keine Großbuchstaben verwenden oder Leerzeichen im Namen einschließen.
    
5. Klicken Sie auf der Seite **Import Auftragstyp auswählen** auf **Verschiffen von Festplatten an einen unserer physischen Standorte** , und klicken Sie dann auf **weiter**.
    
    ![Klicken Sie auf Festplattenlaufwerke an einen unserer physischen Standorte liefern, um einen Importauftrag für den Laufwerk Versand zu erstellen.](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. Führen Sie auf der Seite **Daten importieren** die folgenden zwei Schritte aus: 
    
    ![Kopieren Sie den Schlüssel zum sicheren Speicher, und laden Sie das Tool Azure Import Export auf der Seite Daten importieren herunter.](media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    a. Klicken Sie in Schritt 2 auf **sicheren Speicherschlüssel kopieren**. Nachdem Sie den Speicherschlüssel angezeigt haben, klicken Sie auf **in die Zwischenablage kopieren** und anschließend in eine Datei einfügen und speichern, damit Sie später darauf zugreifen können.
    
    b. Laden Sie in Schritt 3 **das Azure-Import/Export-Tool** herunter, um das Azure-Tool zum Importieren/Exportieren (Version 1) herunterzuladen und zu installieren.
    
    - **Klicken Sie** \> im Popupfenster auf Save **As** speichern unter, um die Datei WaImportExportV1. zip in einem Ordner auf Ihrem lokalen Computer zu speichern. 
    
    - Extrahieren Sie die Datei WaImportExportV1. zip.
    
7. Klicken Sie auf **Abbrechen** , um den Assistenten zu schließen. 
    
    Sie kehren zur Seite **importieren** im Security #a0 Compliance Center zurück, wenn Sie den Importauftrag in Schritt 4 erstellen. 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>Schritt 2: Kopieren der PST-Dateien auf die Festplatte

Der nächste Schritt besteht darin, die PST-Dateien mithilfe des Tools WAImportExport.exe auf die Festplatte zu kopieren. Mit diesem Tool werden die Festplatte mit BitLocker verschlüsselt, die PST-Dateien auf die Festplatte kopiert und eine Journaldatei erstellt, die Informationen zum Kopiervorgang speichert. Damit Sie diesen Schritt ausführen können, müssen sich die PST-Dateien in einer Dateifreigabe oder auf einem Dateiserver in Ihrer Organisation befinden. Im folgenden Verfahren wird dies als das Quellverzeichnis bezeichnet. 
  
> [!IMPORTANT]
> Nach der ersten Verwendung des Tools WAImportExport.exe für ein Laufwerk müssen Sie jedes weitere Mal eine andere Syntax verwenden. Diese Syntax wird in Schritt 4 dieses Verfahrens zum Kopieren von PST-Dateien auf die Festplatte erläutert. 
  
1. Öffnen Sie eine Eingabeaufforderung auf dem lokalen Computer.
    
    > [!TIP]
    > Wenn Sie die Eingabeaufforderung als Administrator ausführen (durch Auswahl von „Als Administrator ausführen“ beim Öffnen), werden im Fenster der Eingabeaufforderung Fehlermeldungen angezeigt. Dies kann Ihnen bei der Behandlung von Problemen beim Ausführen des Tools „WAImportExport.exe“ helfen. 
  
2. Wechseln Sie zu dem Verzeichnis, in dem Sie das Tool „WAImportExport.exe“ in Schritt 1 installiert haben.
    
3. Wenn Sie „WAImportExport.exe“ zum ersten Mal verwenden, um die PST-Dateien auf eine Festplatte zu kopieren, führen Sie den folgenden Befehl aus.

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /blobtype:BlockBlob /encrypt /logdir:<Log file location>
    ```

    In der folgenden Tabelle werden die Parameter und deren erforderliche Werte beschrieben.
    
    |**Parameter**|**Beschreibung**|**Beispiel**|
    |:-----|:-----|:-----|
    | `/j:` <br/> |Gibt den Namen der Journaldatei an. Diese Datei wird im selben Ordner gespeichert, in dem sich das Tool „WAImportExport.exe“ befindet. Jede Festplatte, die Sie an Microsoft senden, muss eine Journaldatei enthalten. Jedes Mal, wenn Sie „WAImportTool.exe“ zum Kopieren von PST-Dateien auf eine Festplatte ausführen, werden Informationen zur Journaldatei dieser Festplatte hinzugefügt.  <br/> Microsoft Data Center-Mitarbeiter verwenden Sie die Informationen in der Journaldatei, um die Festplatte dem in Schritt 4 erstellten Importauftrag zuzuordnen und die PST-Dateien in den Azure-Speicherbereich in der Microsoft-Cloud hochzuladen.  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |Gibt den Buchstaben des Laufwerks an, wenn die Festplatte an Ihren lokalen Computer angeschlossen ist.  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |Gibt den Namen der Kopiersitzung an. Eine Sitzung ist definiert als jeder einzelne Vorgang, in dem Sie das Tool „WAImportExport.exe“ ausführen und Dateien auf die Festplatte kopieren. Die PST-Dateien werden in einen Ordner mit dem Namen der Sitzung kopiert, der durch diesen Parameter angegeben wird.   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |Gibt das Quellverzeichnis in Ihrer Organisation an, das die PST-Dateien enthält, die während der Sitzung kopiert werden. Stellen Sie sicher, dass Sie den Wert dieses Parameters mit doppelten Anführungszeichen ("") umgeben.  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |Gibt das Zielverzeichnis im Azure-Speicherbereich in der Microsoft-Cloud an, in dem der PST hochgeladen wird. Sie müssen den Wert `ingestiondata/`verwenden. Stellen Sie sicher, dass Sie den Wert dieses Parameters mit doppelten Anführungszeichen ("") umgeben.  <br/> Optional können Sie auch einen zusätzlichen Dateipfad zum Wert dieses Parameters hinzufügen. Sie können beispielsweise den Dateipfad des Quellverzeichnisses auf der Festplatte (in ein URL-Format konvertiert) verwenden, das im- `/srcdir:` Parameter angegeben ist. Beispielsweise `\\FILESERVER01\PSTs` wird in `FILESERVER01/PSTs`geändert. In diesem Fall müssen Sie den Dateipfad dennoch `ingestiondata` einschließen. In diesem Beispiel wäre also der Wert für den `/dstdir:` `"ingestiondata/FILESERVER01/PSTs"`-Parameter.  <br/> Das Hinzufügen des zusätzlichen Dateipfads ist z. B. dann sinnvoll, wenn einige Ihrer PST-Dateien den gleichen Dateinamen aufweisen.  <br/> > [!NOTE]> Wenn Sie den optionalen Pfadnamen einschließen, enthält der Namespace für eine PST-Datei nach dem Hochladen in den Azure-Speicherbereich den Pfadnamen und den Namen der PST-Datei. Beispiel: `FILESERVER01/PSTs/annb.pst`. Wenn Sie keinen Pfadnamen angeben, ist der Namespace nur der PST-Dateiname; zum Beispiel `annb.pst`.           | `/dstdir:"ingestiondata/"` <br/> Oder  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |Gibt den Speicherkontoschlüssel an, den Sie in Schritt 1 abgerufen haben. Stellen Sie sicher, dass Sie den Wert dieses Parameters mit doppelten Anführungszeichen ("") umgeben.  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/blobtype:` <br/> |Gibt den Typ der BLOBs im Azure-Speicherbereich an, in den die PST-Dateien importiert werden sollen. Verwenden Sie zum Importieren von PST-Dateien den Wert **BlockBlob**. Dieser Parameter ist erforderlich.   <br/> | `/blobtype:BlockBlob` <br/> |
    | `/encrypt` <br/> |Diese Option aktiviert BitLocker für die Festplatte. Dieser Parameter ist beim erstmaligen Ausführen des Tools „WAImportExport.exe“ erforderlich.  <br/> Der BitLocker-Verschlüsselungsschlüssel wird in die Journaldatei und die Protokolldatei kopiert, die erstellt wird, `/logfile:` Wenn Sie den Parameter verwenden. Wie bereits erwähnt wird die Journaldatei im selben Ordner gespeichert, in dem sich das Tool „WAImportExport.exe“ befindet.  <br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |Dieser optionale Parameter gibt einen Ordner an, in dem die Protokolldateien gespeichert werden können. Wenn nicht angegeben, werden die Protokolldateien im gleichen Ordner gespeichert, in dem sich das Tool "waimportexport. exe befindet. Stellen Sie sicher, dass Sie den Wert dieses Parameters mit doppelten Anführungszeichen ("") umgeben.  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    Nachfolgend sehen Sie ein Beispiel der Syntax für das Tool „WAImportExport.exe“, in dem die tatsächlichen Werte für jeden Parameter verwendet werden:
    
    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" blobtype:BlockBlob /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    Nachdem Sie den Befehl ausgeführt haben, werden Statusmeldungen angezeigt, die den Fortschritt des Kopierens der PST-Dateien auf die Festplatte anzeigen. Eine endgültige Statusmeldung zeigt die Gesamtzahl der Dateien an, die erfolgreich kopiert wurden. 
    
4. Führen Sie diesen Befehl jedes Mal aus, wenn Sie das Tool „WAImportExport.exe“ zum Kopieren der PST-Dateien auf dieselbe Festplatte ausführen.

    ```
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> /blobtype:BlockBlob 
    ```

    Im Folgenden sehen Sie ein Beispiel der Syntax für die Ausführung weiterer Sitzungen zum Kopieren von PST-Dateien auf dieselbe Festplatte.  

    ```
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/" /blobtype:BlockBlob
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a>Schritt 3: Erstellen der PST-Import Zuordnungsdatei

Nachdem Microsoft Data Center-Mitarbeiter die PST-Dateien von der Festplatte in den Azure-Speicherbereich hochgeladen haben, verwendet der Import Dienst die Informationen in der PST-Import Zuordnungsdatei, bei der es sich um eine CSV-Datei (Comma-Separated Value) handelt, mit der angegeben wird, welche Benutzerpostfächer die PST-Dateien werden in importiert. Diese CSV-Datei wird im nächsten Schritt übermittelt, wenn Sie einen PST-Importauftrag erstellen.
  
1. [Laden Sie eine Kopie der PST-Import Zuordnungsdatei herunter](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
2. Öffnen oder speichern Sie die CSV-Datei auf Ihrem lokalen Computer. Das folgende Beispiel zeigt eine abgeschlossene PST-Importzuordnungsdatei (in Editor geöffnet). Es ist wesentlich einfacher, Microsoft Excel zum Bearbeiten der CSV-Datei zu verwenden.

    ```
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,FILESERVER01/PSTs,annb.pst,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,annb_archive.pst,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,donh.pst,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,donh_archive.pst,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,FILESERVER01/PSTs,pilarp.pst,pilarp@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,FILESERVER01/PSTs,pilarp_archive.pst,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,tonyk.pst,tonyk@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,tonyk_archive.pst,tonyk@contoso.onmicrosoft.com,TRUE,,,,,
    Exchange,,zrinkam.pst,zrinkam@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,zrinkam_archive.pst,zrinkam@contoso.onmicrosoft.com,TRUE,,,,,
    ```

    Die erste Zeile oder Kopfzeile der CSV-Datei enthält die Parameter, die vom PST-Importdienst verwendet werden, um die PST-Dateien in Benutzerpostfächer zu importieren. Die einzelnen Parameternamen werden jeweils durch ein Komma getrennt. Jede Zeile unter der Kopfzeile stellt die Parameterwerte für das Importieren einer PST-Datei in ein bestimmtes Postfach dar. Sie benötigen eine Zeile für jede PST-Datei, die auf die Festplatte kopiert wurde. Vergessen Sie nicht, die Platzhalterdaten in der Zuordnungsdatei durch die tatsächlichen Werte zu ersetzen.

    > [!NOTE]
    > Ändern Sie nichts in der Kopfzeile, einschließlich der SharePoint-Parameter; diese werden während des PST-Importvorgangs ignoriert. 
  
3. Verwenden Sie die Informationen in der folgenden Tabelle, um zu die CSV-Datei mit den erforderlichen Informationen zu füllen.
    
    |**Parameter**|**Beschreibung**|**Beispiel**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Gibt den Office 365 Dienst an, in den Daten importiert werden. Um PST-Dateien in Benutzerpostfächer zu importieren `Exchange`, verwenden Sie.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> | Gibt den Speicherort des Ordners im Azure-Speicherbereich an, in den PST-Dateien kopiert werden, wenn die Festplatte an Microsoft ausgeliefert wird.  <br/>  Was Sie in dieser Spalte in der CSV-Datei hinzufügen, hängt davon ab, was `/dstdir:` Sie in für den Parameter im vorherigen Schritt angegeben haben. Wenn Sie Unterordner am Quellspeicherort haben, muss der Wert im `FilePath` Parameter den relativen Pfad für den Unterordner enthalten. Beispiel:/Folder1/user1/.  <br/>  Wenn Sie verwendet `/dstdir:"ingestiondata/"`haben, lassen Sie diesen Parameter in der CSV-Datei leer.  <br/>  Wenn Sie einen optionalen Pfadname für den Wert des `/dstdir:` Parameters angegeben haben (Beispiels `/dstdir:"ingestiondata/FILESERVER01/PSTs"`Weise, dann verwenden Sie diesen Pfadnamen (nicht einschließlich "ingestiondata") für diesen Parameter in der CSV-Datei. Bei dem Wert für diesen Parameter wird die Groß-/Kleinschreibung beachtet.  <br/>  Verwenden Sie in beiden Fällen *nicht* "ingestiondata" in den Wert des `FilePath` Parameters. Lassen Sie diesen Parameter leer, oder geben Sie nur den optionalen Pfadnamen an.  <br/> > [!IMPORTANT]> der Fall des Datei Pfadnamens muss derselbe Fall sein, den Sie im `/dstdir:` Parameter im vorherigen Schritt angegeben haben. Wenn Sie beispielsweise den Namen `"ingestiondata/FILESERVER01/PSTs"` des Unterordners im vorherigen Schritt verwendet haben, dieser jedoch im `fileserver01/psts` Parameter in `FilePath` der CSV-Datei verwendet wird, schlägt der Import für die PST-Datei fehl. Achten Sie darauf, dass Sie in beiden Fällen denselben Fall verwenden.           |(leer lassen)  <br/> Oder  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |Gibt den Namen der PST-Datei an, die in das Benutzerpostfach importiert wird.  Bei dem Wert für diesen Parameter wird die Groß-/Kleinschreibung beachtet.  <br/> > [!IMPORTANT]> der Fall für den Namen der PST-Datei in der CSV-Datei muss mit der PST-Datei übereinstimmen, die in Schritt 2 in den Azure-Speicherort hochgeladen wurde. Wenn Sie beispielsweise im- `annb.pst` `Name` Parameter in der CSV-Datei verwenden, aber der Name der tatsächlichen PST-Datei lautet `AnnB.pst`, tritt beim Import für diese PST-Datei ein Fehler auf. Stellen Sie sicher, dass der Name der PST-Datei in der CSV-Datei den gleichen Fall wie die tatsächliche PST-Datei verwendet.           | `annb.pst` <br/> |
    | `Mailbox` <br/> |Gibt die E-Mail-Adresse des Postfachs an, in das die PST-Datei importiert werden soll.  Sie können keinen öffentlichen Ordner angeben, da der PST-Import Dienst den Import von PST-Dateien in öffentliche Ordner nicht unterstützt.  <br/> Um eine PST-Datei in ein inaktives Postfach zu importieren, müssen Sie die Postfach-GUID für diesen Parameter angeben. Um diese GUID zu erhalten, führen Sie den folgenden PowerShell-Befehl in Exchange Online aus:`Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid` <br/> > [!NOTE]> manchmal verfügen Sie möglicherweise über mehrere Postfächer mit derselben e-Mail-Adresse, wobei ein Postfach ein aktives Postfach und das andere Postfach einen Soft-deleted (oder inaktiven) Status hat. In diesen Situationen müssen Sie die Postfach-GUID angeben, um das Postfach, in das die PST-Datei importiert werden soll, eindeutig zu identifizieren. Führen Sie den folgenden PowerShell-Befehl aus, um diese GUID für aktive `Get-Mailbox <identity of active mailbox> | FL Guid`Postfächer zu erhalten:. Um die GUID für vorläufig gelöschte (oder inaktive) Postfächer zu erhalten, führen `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`Sie den folgenden Befehl aus:.           | `annb@contoso.onmicrosoft.com` <br/> Oder  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Gibt an, ob die PST-Datei in das Archivpostfach des Benutzers importiert werden soll. Es gibt zwei Möglichkeiten:  <br/> **False** Importiert die PST-Datei in das primäre Postfach des Benutzers.  <br/> **True** Importiert die PST-Datei in das Archivpostfach des Benutzers. This assumes that the [user's archive mailbox is enabled](enable-archive-mailboxes.md). Wenn Sie diesen Parameter auf `TRUE` festlegen und das Archivpostfach des Benutzers nicht aktiviert ist, tritt beim Import für diesen Benutzer ein Fehler auf. Wenn ein Importfehler für einen Benutzer auftritt (da das Archiv nicht aktiviert ist und diese Eigenschaft auf `TRUE`festgelegt ist), sind die anderen Benutzer im Importauftrag nicht betroffen.  <br/>  If you leave this parameter blank, the PST file is imported to the user's primary mailbox.  <br/> **Hinweis:** Wenn Sie eine PST-Datei in ein Cloud-basiertes Archivpostfach für einen Benutzer importieren möchten, dessen primäres Postfach lokal `TRUE` ist, geben Sie für diesen Parameter einfach an, und geben Sie die e-Mail- `Mailbox` Adresse für das lokale Postfach des Benutzers für den Parameter an.  <br/> | `FALSE` <br/> Oder  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Gibt den Postfachordner an, in den die PST-Datei importiert wird.  <br/>  Wenn Sie diesen Parameter leer lassen, wird die PST-Datei in einen neuen Ordner mit dem Namen " **imported** " importiert, der sich auf der Stammebene des Postfachs befindet (die gleiche Ebene wie der Posteingangsordner und die anderen standardmäßigen Postfachordner).  <br/>  Wenn Sie angeben `/`, werden Elemente in der PST-Datei direkt in den Posteingangsordner des Benutzers importiert.  <br/>  Wenn Sie angeben `/<foldername>`, werden Elemente in der PST-Datei in einen Ordner mit dem Namen * \<FolderName\>* importiert. Wenn Sie beispielsweise verwenden `/ImportedPst`, werden Elemente in einen Ordner mit dem Namen **ImportedPst**importiert. Dieser Ordner befindet sich im Postfach des Benutzers auf derselben Ebene wie der Posteingangsordner.  <br/> |(leer lassen)  <br/> Oder  <br/>  `/` <br/> Oder  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Dieser optionale Parameter gibt einen numerischen Wert für die Codepage an, die zum Importieren von PST-Dateien im ANSI-Dateiformat verwendet werden soll. Dieser Parameter wird zum Importieren von PST-Dateien aus chinesischen, japanischen und koreanischen Organisationen (CJK) verwendet, da diese Sprachen in der Regel einen Doppelbyte-Zeichensatz (DBCS) für die Zeichencodierung verwenden. Wenn dieser Parameter nicht zum Importieren von PST-Dateien für Sprachen verwendet wird, die DBCS für Postfachordner Namen verwenden, werden die Ordnernamen nach dem Import häufig verstümmelt.  <br/> Eine Liste der unterstützten Werte, die für diesen Parameter verwendet werden sollen, finden Sie unter [Code Page Identifiers](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/> > [!NOTE]> wie bereits erwähnt, ist dies ein optionaler Parameter, den Sie nicht in die CSV-Datei einschließen müssen. Oder Sie können ihn einschließen und den Wert für eine oder mehrere Zeilen leer lassen.           |(leer lassen)  <br/> Oder  <br/>  `932`(Dies ist der Codepagebezeichner für ANSI/OEM Japanisch)  <br/> |
    | `SPFileContainer` <br/> |Lassen Sie diesen Parameter für den PST-Import leer.   <br/> |Nicht zutreffend  <br/> |
    | `SPManifestContainer` <br/> |Lassen Sie diesen Parameter für den PST-Import leer.   <br/> |Nicht zutreffend  <br/> |
    | `SPSiteUrl` <br/> |Lassen Sie diesen Parameter für den PST-Import leer.   <br/> |Nicht zutreffend  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>Schritt 4: Erstellen eines PST-Importauftrags in Office 365

Im nächsten Schritt erstellen Sie den PST-Importauftrag im Import Dienst in Office 365. Wie bereits erläutert, übermitteln Sie die PST-Import Zuordnungsdatei, die Sie in Schritt 3 erstellt haben. Nachdem Sie den Auftrag erstellt haben, wird der Import Dienst die Informationen in der Zuordnungsdatei verwenden, um die PST-Dateien in das angegebene Benutzerpostfach zu importieren, nachdem die PST-Dateien von der Festplatte in den Azure-Speicherbereich kopiert wurden, und Sie erstellen und starten den Import Auftrag.
  
1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation an. 
    
2. Klicken Sie im linken Bereich des Security #a0 Compliance Center auf **Data Governance** , und klicken Sie dann auf **importieren**.
    
3. Klicken Sie **** ![auf der Seite importieren auf Symbol](media/ITPro-EAC-AddIcon.gif) **neuer Importauftrag**hinzufügen.
    
    > [!NOTE]
    > Wie bereits erwähnt, müssen Sie im Security #a0 Compliance Center die entsprechenden Berechtigungen für den Zugriff auf die **Import** Seite erhalten. 
  
4. Geben Sie einen Namen für den PST-Importauftrag ein, und klicken Sie dann auf **weiter**. Verwenden Sie Kleinbuchstaben, Zahlen, Bindestriche und Unterstriche. Sie können keine Großbuchstaben verwenden oder Leerzeichen im Namen einschließen.
    
5. Klicken Sie auf der Seite **Import Auftragstyp auswählen** auf **Verschiffen von Festplatten an einen unserer physischen Standorte** , und klicken Sie dann auf **weiter**.
    
    ![Klicken Sie auf Festplattenlaufwerke an einen unserer physischen Standorte liefern, um einen Importauftrag für den Laufwerk Versand zu erstellen.](media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. Klicken Sie in Schritt 6 auf die Kontrollkästchen **Ich habe meine Festplatten vorbereitet und habe Zugriff auf die erforderlichen Laufwerk Journaldateien** , und **Ich habe Zugriff auf die Zuordnungsdatei** , und klicken Sie dann auf **weiter**.
    
    ![Aktivieren Sie die beiden Kontrollkästchen in Schritt 6.](media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. Klicken Sie auf der Seite **Laufwerksdatei auswählen** auf **Laufwerk Datei auswählen**, und wechseln Sie dann zu dem Ordner, in dem sich das Tool "waimportexport. exe befindet. Die in Schritt 2 erstellte Journaldatei wurde in diesen Ordner kopiert.
    
    ![Klicken Sie auf Laufwerk Datei auswählen, um die Journaldatei zu übermitteln, die erstellt wurde, als Sie das Tool "waimportexport. exe ausgeführt haben.](media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. Wählen Sie die Journaldatei aus. Beispiel: `PSTHDD1.jrn`.
    
    > [!TIP]
    > Wenn Sie das Tool "waimportexport. exe in Schritt 2 ausgeführt haben, wurde der Name der Journaldatei durch den `/j:` -Parameter angegeben. 
  
9. Nachdem der Name der Laufwerk Datei unter Name der **Laufwerksdatei**angezeigt wird **, klicken Sie auf über** prüfen, um die Laufwerk Datei auf Fehler zu überprüfen. 
    
    ![Klicken Sie auf überprüfen, um die ausgewählte Laufwerksdatei zu überprüfen.](media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    Die Laufwerksdatei muss erfolgreich überprüft werden, um einen PST-Import Auftrag zu erstellen. Beachten Sie, dass der Dateiname nach erfolgreicher Validierung in Grün geändert wird. Wenn die Überprüfung fehlschlägt, klicken Sie auf den Link **Protokoll anzeigen** . Es wird ein Validierungsfehler Bericht mit einer Fehlermeldung mit Informationen darüber geöffnet, warum die Datei fehlgeschlagen ist. 
    
    > [!NOTE]
    > Sie müssen für jede Festplatte, die Sie an Microsoft senden, eine Journaldatei hinzufügen und validieren. 
  
10. Nachdem Sie eine Journaldatei für jede Festplatte hinzugefügt und überprüft haben, die Sie an Microsoft senden, klicken Sie auf **weiter**.
    
11. Klicken ![Sie auf](media/ITPro-EAC-AddIcon.gif) Symbol hinzufügen **auswählen Zuordnungsdatei** zum übermitteln der PST-Import Zuordnungsdatei, die Sie in Schritt 3 erstellt haben. 
    
    ![Klicken Sie auf Zuordnungsdatei auswählen, um die CSV-Datei zu übermitteln, die Sie für den Importauftrag erstellt haben.](media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. Nachdem der Name der CSV-Datei unter **Name der Zuordnungsdatei**angezeigt wird **, klicken Sie** auf überprüfen, um die CSV-Datei auf Fehler zu überprüfen. 
    
    ![Klicken Sie auf überprüfen, um die CSV-Datei auf Fehler zu überprüfen](media/4680999d-5538-4059-b878-2736a5445037.png)
  
    Die CSV-Datei muss erfolgreich überprüft werden, um einen PST-Import Auftrag zu erstellen. Beachten Sie, dass der Dateiname nach erfolgreicher Validierung in Grün geändert wird. Wenn die Überprüfung fehlschlägt, klicken Sie auf den Link **Protokoll anzeigen** . Es wird ein Validierungsfehler Bericht mit einer Fehlermeldung für jede Zeile in der Datei geöffnet, die fehlgeschlagen ist. 
    
13. Nachdem die PST-Zuordnungsdatei erfolgreich überprüft wurde, klicken Sie auf **weiter**.
    
14. Geben Sie auf der Seite **Kontaktinformationen bereitstellen** Ihre Kontaktinformationen in die entsprechenden Felder ein. 
    
    Die Adresse für den Microsoft-Standort, an den Sie Ihre Festplatten versenden, wird angezeigt. Diese Adresse wird basierend auf Ihrem Office 365 rechenzentrumsstandort automatisch generiert. Kopieren Sie diese Adresse in eine Datei oder erstellen Sie einen Screenshot.
    
15. Lesen Sie das Dokument Bedingungen und Konditionen, klicken Sie auf das Kontrollkästchen, und klicken Sie dann auf **Speichern** , um den Importauftrag zu übermitteln. 
    
    Wenn der Importauftrag erfolgreich erstellt wurde, wird eine Statusseite angezeigt, in der die nächsten Schritte des Laufwerk Versandprozesses erläutert werden.
    
16. Klicken Sie **** ![auf der Seite importieren auf aktualisieren](media/O365-MDM-Policy-RefreshIcon.gif) Symbol **Aktualisieren** , um den neuen Importauftrag für den Laufwerk Versand in der Liste der Importaufträge anzuzeigen. Der Status ist auf nach **Verfolgungsnummer warten**festgelegt. Sie können auch auf den Importauftrag klicken, um die Status-Flyout-Seite anzuzeigen, die detailliertere Informationen zum Importauftrag enthält.
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>Schritt 5: Versenden der Festplatte an Microsoft

Der nächste Schritt besteht darin, die Festplatte an Microsoft zu senden und dann die Nachverfolgungsnummer für die Versand-und Rück Sendungsinformationen für den Laufwerk Versandauftrag anzugeben. Nachdem das Laufwerk von Microsoft empfangen wurde, dauert es zwischen 7 und 10 Werktage für Rechenzentrumsmitarbeiter, um Ihre PST-Dateien in den Azure-Speicherbereich Ihrer Organisation hochzuladen.
  
> [!NOTE]
> Wenn Sie die Nachverfolgungsnummer und Rück Sendungsinformationen nicht innerhalb von 14 Tagen nach Erstellung des importauftrags angeben, ist der Importauftrag abgelaufen. In diesem Fall müssen Sie einen neuen Importauftrag für den Laufwerk Versand erstellen (siehe [Schritt 4: Erstellen eines PST-importauftrags in Office 365](#step-4-create-a-pst-import-job-in-office-365)) und erneutes übermitteln der Laufwerksdatei und der PST-Import Zuordnungsdatei. 
  
### <a name="ship-the-hard-drive"></a>Versenden der Festplatte

Beachten Sie die folgenden Punkte, wenn Sie Festplatten an Microsoft senden:
  
- Senden Sie den SATA-zu-USB-Adapter nicht. Sie müssen die Festplatte nur versenden.
    
- Verpacken Sie die Laufwerke ordnungsgemäß; verwenden Sie z. B. antistatische Verpackung oder Luftpolsterfolie.
    
- Senden Sie die Festplatte mit einem Spediteur Ihrer Wahl an Microsoft.
    
- Verwenden Sie als Versandadresse den Microsoft-Standort, der Ihnen beim Erstellen des Importauftrags in Schritt 4 angezeigt wurde. Vergessen Sie nicht, in der Versandadresse den Zusatz „Office 365 Import Service“ anzugeben.
    
- Nachdem Sie die Festplatte versendet haben, notieren Sie sich den Namen des Spediteurs und die Nachverfolgungsnummer. Diese müssen Sie im nächsten Schritt angeben.
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>Eingabe der Nachverfolgungsnummer und anderer Versandinformationen

Nachdem Sie die Festplatte an Microsoft gesendet haben, führen Sie auf der Seite des Importdiensts die folgenden Schritte aus.
  
1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation an. 
    
2. Klicken Sie im linken Bereich auf **Datensteuerung** , und klicken Sie dann auf **importieren**.
    
3. Klicken Sie auf der Seite **importieren** auf den Auftrag für die Laufwerk Sendung, für die Sie die Nachverfolgungsnummer eingeben möchten. 
    
4. Klicken Sie auf der Seite Status-Flyout auf **Tracking Number eingeben**.
    
5. Geben Sie die folgenden Versandinformationen an:
    
1. **Zustellungs Träger** Geben Sie den Namen des Zustellungs Trägers ein, den Sie zum Versenden der Festplatte an Microsoft verwendet haben. 
    
2. **Nachverfolgungsnummer** Geben Sie die Nachverfolgungsnummer für die Festplatten-Lieferung ein. 
    
3. **Kontonummer des Rücksende Anbieters** Geben Sie die Kontonummer Ihrer Organisation für den Carrier ein, der unter **Absender der Rücksendung**aufgeführt ist. Microsoft verwendet (und lädt) dieses Konto, um Ihre Festplatte an Sie zurückzuliefern. Organisationen in den USA und Europa müssen über ein Konto bei FedEx verfügen. Organisationen in Asien und dem Rest der Welt müssen über ein Konto bei DHL verfügen.
    
6. Klicken Sie auf **Speichern**, um diese Informationen für den Importauftrag zu speichern. 
    
    Klicken Sie **** ![auf der Seite importieren auf Symbol](media/O365-MDM-Policy-RefreshIcon.gif) **Aktualisierung** aktualisieren, um die Informationen für den Importauftrag für den Laufwerk Versand zu aktualisieren. Beachten Sie, dass der Status jetzt **Festplatten werden gesendet** lautet.

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Schritt 6: Filtern von Daten und Starten des PST-Import Auftrags

Nachdem Ihre Festplatte von Microsoft empfangen wurde, wird der Status des importauftrags auf der Seite " **importieren** " in " **Laufwerke empfangen**" geändert. Mitarbeiter des Rechenzentrums verwenden Sie die Informationen in der Journaldatei, um Ihre PST-Dateien in den Azure-Speicherbereich Ihrer Organisation hochzuladen. Zu diesem Zeitpunkt ändert sich der Status **in "in-Progress" Importieren**. Wie bereits erwähnt, dauert es zwischen 7 und 10 Werktage nach Erhalt Ihrer Festplatte, um die PST-Dateien hochzuladen.
  
Nachdem PST-Dateien in Azure hochgeladen wurden, wird der Status **in "Analysis in Progress**" geändert. Dies deutet darauf hin, dass Office 365 die Daten in den PST-Dateien (auf sichere und sichere Weise) analysiert, um das Alter der Elemente und die unterschiedlichen Nachrichtentypen zu identifizieren, die in den PST-Dateien enthalten sind. Wenn die Analyse abgeschlossen ist und die Daten importiert werden können, wird der Status für den Importauftrag in **Analyse abgeschlossen**geändert. Zu diesem Zeitpunkt haben Sie die Möglichkeit, alle in den PST-Dateien enthaltenen Daten zu importieren, oder Sie können die importierten Daten kürzen, indem Sie Filter festlegen, mit denen gesteuert wird, welche Daten importiert werden.
  
1. Wechseln Sie [https://protection.office.com](https://protection.office.com) zu, und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation an. 
    
2. Klicken Sie im linken Bereich auf **Data Governance** > **Import**.
    
3. Klicken Sie auf der Seite **importieren** auf bereit für den Import in **Office 365** für den Importauftrag, den Sie in Schritt 4 erstellt haben. 
    
    ![Klicken Sie auf Ready to Import to Office 365 neben dem von Ihnen erstellten Importauftrag.](media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Eine Ausklappseite wird mit Informationen über die PST-Dateien und andere Informationen zum Importauftrag angezeigt.
    
4. Klicken Sie auf **Importieren in Office 365**.
    
5. Die Seite **Daten filtern** wird angezeigt. Sie enthält die Daten Insights, die sich aus der Analyse ergeben, die für die PST-Dateien von Office 365 durchgeführt wurde, einschließlich Informationen zum Alter der Daten. Zu diesem Zeitpunkt haben Sie die Möglichkeit, die Daten zu filtern, die importiert werden, oder alle Daten zu importieren. 
    
    ![Sie können die Daten in den PST-Dateien kürzen oder alles importieren.](media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. Führen Sie einen der folgenden Schritte aus:
    
    a. Um die importierten Daten zu trimmen, klicken Sie auf **Ja, ich möchte Sie vor dem Importieren Filtern**.
    
    Ausführliche Schritt-für-Schritt-Anweisungen zum Filtern der Daten in den PST-Dateien und zum Starten des importauftrags finden Sie unter [Filtern von Daten beim Importieren von PST-Dateien in Office 365](filter-data-when-importing-pst-files.md).
    
    Oder
    
    b. Wenn Sie alle Daten in den PST-Dateien importieren möchten, klicken Sie auf **Nein, ich möchte alles importieren,** und klicken Sie dann auf **weiter**.
    
7. Wenn Sie alle Daten importiert haben, klicken Sie auf **Daten importieren** , um den Importauftrag zu starten. 
    
    Der Status des importauftrags wird auf der Seite **importieren** angezeigt. Klicken ![Sie auf](media/O365-MDM-Policy-RefreshIcon.gif) Aktualisierungssymbol **Aktualisieren** , um die Statusinformationen zu aktualisieren, die in der Spalte **Status** angezeigt werden. Klicken Sie auf den Importauftrag, um die Status-Flyout-Seite anzuzeigen, in der Statusinformationen zu den importierten PST-Dateien angezeigt werden. Wenn der Import abgeschlossen ist, und die PST-Dateien in die Benutzerpostfächer importiert wurden, wird der Status in **Abgeschlossen** geändert.

## <a name="view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Anzeigen einer Liste der PST-Dateien, die in Office 365 hochgeladen wurden

Sie können den Microsoft Azure Speicher-Explorer (ein kostenloses Open-Source-Tool) installieren und verwenden, um die Liste der PST-Dateien anzuzeigen, die von Microsoft-Mitarbeitern für Rechenzentren hochgeladen wurden, in den Azure-Speicherbereich Ihrer Organisation. Sie können dies tun, um sicherzustellen, dass PST-Dateien von den Festplatten, die Sie an Microsoft gesendet haben, erfolgreich in den Azure-Speicherbereich hochgeladen wurden.
  
Der Microsoft Azure Speicher-Explorer befindet sich in der Vorschau.
  
 **Wichtig:** Sie können den Azure-Speicher-Explorer nicht zum Hochladen oder Ändern von PST-Dateien verwenden. Die einzige unterstützte Methode zum Importieren von PST-Dateien in Office 365 ist die Verwendung von AzCopy. Außerdem können Sie keine PST-Dateien löschen, die Sie in das Azure-BLOB hochgeladen haben. Wenn Sie versuchen, eine PST-Datei zu löschen, erhalten Sie eine Fehlermeldung, dass Sie nicht über die erforderlichen Berechtigungen verfügen. Alle PST-Dateien werden automatisch aus dem Azure-Speicherbereich gelöscht. Wenn keine Importaufträge ausgeführt werden, werden alle PST-Dateien im * * ingestiondata * *-Container 30 Tage nach der Erstellung des letzten importauftrags gelöscht. 
  
So installieren Sie den Azure Storage-Explorer und stellen eine Verbindung mit Ihrem Azure-Speicherbereich her:
  
1. Führen Sie die folgenden Schritte aus, um die SAS-URL (Shared Access Signature) für Ihre Organisation abzurufen. Diese URL ist eine Kombination aus der Netzwerk-URL für den Azure-Speicherort in der Microsoft-Cloud für Ihre Organisation und einem SAS-Schlüssel. Mit diesem Schlüssel erhalten Sie die erforderlichen Berechtigungen für den Zugriff auf den Azure-Speicherort Ihrer Organisation.
    
1. Wechseln Sie [https://protection.office.com/](https://protection.office.com/) zu, und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation an. 
    
2. Klicken Sie im linken Bereich des Security #a0 Compliance Center auf **Data Governance** \> **Import**.
    
3. Klicken Sie **** ![auf der Seite importieren auf Symbol](media/ITPro-EAC-AddIcon.gif) **neuer Importauftrag**hinzufügen.
    
4. Geben Sie im Assistenten zum Importieren von Aufträgen einen Namen für den PST-Importauftrag ein, und klicken Sie dann auf **weiter**. Verwenden Sie Kleinbuchstaben, Zahlen, Bindestriche und Unterstriche. Sie können keine Großbuchstaben verwenden oder Leerzeichen im Namen einschließen.
    
5. Klicken Sie auf der Seite **Import Auftragstyp auswählen** auf **Daten hochladen**, und klicken Sie dann auf **weiter**.
    
6. Klicken Sie in Schritt 2 auf **Netzwerk-Upload-SAS-URL anzeigen**.
    
7. Nachdem die URL angezeigt wurde, kopieren Sie Sie, und speichern Sie Sie in einer Datei. Achten Sie darauf, die gesamte URL zu kopieren.
    
    > [!IMPORTANT]
    > Achten Sie darauf, Vorkehrungen zu treffen, um die SAS-URL zu schützen. Dies kann von jedem für den Zugriff auf den Azure-Speicherbereich für Ihre Organisation verwendet werden. 
  
8. Klicken Sie auf **Abbrechen** , um den importauftrags-Assistenten zu schließen. 
    
2. Laden Sie das [Tool Microsoft Azure Storage Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842)herunter, und installieren Sie es.
    
3. Starten Sie den Microsoft Azure Speicher-Explorer, klicken Sie im linken Bereich mit der rechten Maustaste auf **Speicherkonten** , und klicken Sie dann auf mit **Azure-Speicher verbinden**.
    
    ![Klicken Sie mit der rechten Maustaste auf Speicherkonten, und klicken Sie dann auf mit Azure Storage verbinden](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. Klicken Sie auf **einen SAS-URI (Shared Access Signature) oder eine Verbindungszeichenfolge verwenden** , und klicken Sie auf **weiter**.
    
5. Klicken Sie auf **SAS-URI verwenden**, fügen Sie die SAS-URL, die Sie in Schritt 1 abgerufen haben, in das Feld unter **URI**ein, und klicken Sie dann auf **weiter**.
    
6. Auf der Seite zusammen **Fassung der Verbindung** können Sie die Verbindungsinformationen überprüfen und dann auf **verbinden**klicken.
    
    Der **ingestiondata** -Container wird geöffnet. Sie enthält die PST-Dateien von Ihrer Festplatte. Der **ingestiondata** -Container befindet sich unter **Speicherkonten** \> **(SAS-Attached Services)** \> **BLOB-Container**.
    
    ![Azure Storage Explorer zeigt eine Liste der PST-Dateien an, die Sie hochgeladen haben.](media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. Wenn Sie mit dem Microsoft Azure Speicher-Explorer fertig sind, klicken Sie mit der rechten Maustaste auf **ingestiondata**, und klicken Sie dann auf **trennen** , um die Verbindung mit dem Azure-Speicherbereich zu trennen. Andernfalls erhalten Sie eine Fehlermeldung, wenn Sie das nächste Mal versuchen anzufügen. 
    
    ![Klicken Sie mit der rechten Maustaste auf die Einnahme, und klicken Sie auf trennen, um die Verbindung mit Ihrem Azure-Speicherbereich](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)

## <a name="troubleshooting-tips"></a>Tipps zur Problembehandlung

- **Was passiert, wenn der Importauftrag aufgrund von Fehlern in der PST-Import-CSV-Zuordnungsdatei fehlschlägt?** Wenn ein Importauftrag aufgrund von Fehlern in der Zuordnungsdatei fehlschlägt, müssen Sie die Festplatte nicht erneut an Microsoft senden, um einen Importauftrag zu erstellen. Das liegt daran, dass die PST-Dateien von der Festplatte, die Sie für den Importauftrag für den Laufwerk versandbereit gestellt haben, bereits in den Azure-Speicherbereich für Ihre Organisation hochgeladen wurden. In diesem Fall müssen Sie die Fehler in der PST-Import CSV-Zuordnungsdatei nur beheben und dann einen neuen Import Auftrag "Netzwerk Upload" erstellen und die geänderte CSV-Zuordnungsdatei übermitteln. Informationen zum Erstellen und Starten eines neuen importauftrags für den Netzwerk Upload finden Sie [in Schritt 5: Erstellen eines PST-importauftrags in Office 365](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job-in-office-365) und [Schritt 6: Filtern von Daten und Starten des PST-importauftrags](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) im Thema "Verwenden des Netzwerk Uploads zum Importieren von PST-Dateien in Office 365". 
    
    > [!NOTE]
    > Zur Unterstützung der Problembehandlung bei der PST-Import-CSV-Zuordnungsdatei verwenden Sie das [Azure Storage Explorer](#view-a-list-of-the-pst-files-uploaded-to-office-365) -Tool, um die Ordnerstruktur im **ingestiondata** -Container für die PST-Dateien von der Festplatte anzuzeigen, die in den Azure-Speicherbereich hochgeladen wurden. Zuordnungsdatei Fehler werden in der Regel durch einen falschen Wert im filePath-Parameter verursacht. Dieser Parameter gibt den Speicherort einer PST-Datei im Azure-Speicherbereich an. Weitere Informationen finden Sie in der Beschreibung des Parameters filePath in der Tabelle in [Schritt 3](#step-3-create-the-pst-import-mapping-file). Wie bereits erläutert, wurde der Speicherort von PST-Dateien im Azure-Speicherbereich durch den `/dstdir:` -Parameter angegeben, als Sie das Tool "waimportexport. exe in [Schritt 2](#step-2-copy-the-pst-files-to-the-hard-drive)ausgeführt haben. 
  
## <a name="more-information"></a>Weitere Informationen

- Der Laufwerk Versand ist eine effektive Möglichkeit, große Mengen an Archiv Nachrichten in Office 365 zu importieren, um die für Ihre Organisation verfügbaren Kompatibilitätsfeatures zu nutzen. Nachdem die Archivdaten in Benutzerpostfächer importiert wurden, haben Sie folgende Möglichkeiten:
    
  - Aktivieren von [archivpostfächern](enable-archive-mailboxes.md) und [automatisch erweiterter Archivierung](enable-unlimited-archiving.md) , damit Benutzer mehr Postfachspeicher Platz für die Daten erhalten. 
    
  - Stellen Sie Postfächer in das [Beweissicherungsverfahren](https://go.microsoft.com/fwlink/?linkid=856286) ein, um die Daten beizubehalten. 
    
  - Verwenden Sie Microsoft [eDiscovery-Tools](search-for-content.md) , um die Daten zu durchsuchen. 
    
  - Wenden Sie [Office 365 Aufbewahrungsrichtlinien](retention-policies.md) an, um zu steuern, wie lange die Daten aufbewahrt werden und welche Aktion nach Ablauf des Aufbewahrungszeitraums ausgeführt werden soll. 
    
  - Durchsuchen Sie das [Office 365 Überwachungsprotokoll](search-the-audit-log-in-security-and-compliance.md) nach Ereignissen im Zusammenhang mit diesen Daten. 
    
  - Importieren von Daten in [inaktive Postfächer](create-and-manage-inactive-mailboxes.md) zum Archivieren von Daten zu Kompatibilitätszwecken. 
    
  - Schützen Sie Ihre Organisation vor [Datenverlust](data-loss-prevention-policies.md) vertraulicher Informationen. 
    
- Im Folgenden sehen Sie ein Beispiel für einen sicheren Speicherkontoschlüssel und einen BitLocker-Verschlüsselungsschlüssel. Dieses Beispiel enthält auch die Syntax für den Befehl „WAImportExport.exe“, den Sie zum Kopieren der PST-Dateien auf die Festplatte ausführen. Ergreifen Sie entsprechende Vorsichtsmaßnahmen, um diese so zu schützen, wie Sie Kennwörter oder andere Sicherheitsinformationen schützen würden.
    

    ```
    Secure storage account key: 

    yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==

    BitLocker encryption key:

    397386-221353-718905-535249-156728-127017-683716-083391

  COMMAND SYNTAX

  First time:

  WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /blobtype:BlockBlob /encrypt /logdir:<Log file location>

  Subsequent times:

  WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> /blobtype:BlockBlob 

  EXAMPLES

  First time:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER1\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" /blobtype:BlockBlob /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"

  Subsequent times:

  WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER1\PSTs\SecondBatch" /dstdir:"ingestiondata/" /blobtype:BlockBlob
    ```
   
- Wie bereits erläutert, aktiviert der Office 365-Import Dienst die Einstellung Aufbewahrungsdauer (für unbestimmte Zeit), nachdem PST-Dateien in ein Postfach importiert wurden. Dies bedeutet, dass die *RentionHoldEnabled* -Eigenschaft `True` so festgelegt ist, dass die dem Postfach zugewiesene Aufbewahrungsrichtlinie nicht verarbeitet wird. Dadurch erhält der Postfachbesitzer die Zeit, die neu importierten Nachrichten zu verwalten, indem verhindert wird, dass eine Löschung oder Archivrichtlinie ältere Nachrichten löscht oder archiviert. Hier sind einige Schritte, die Sie zum Verwalten dieser Aufbewahrungszeit durchführen können: 
    
  - Nach einem bestimmten Zeitraum können Sie die Aufbewahrungszeit deaktivieren, indem Sie den `Set-Mailbox -RetentionHoldEnabled $false` Befehl ausführen. Anweisungen finden Sie unter [platzieren eines Postfachs in der Aufbewahrungs](https://go.microsoft.com/fwlink/p/?LinkId=544749)Zeit.
    
  - Sie können den Aufbewahrungsspeicher so konfigurieren, dass er an einem bestimmten Datum in der Zukunft deaktiviert ist. Hierzu führen Sie den `Set-Mailbox -EndDateForRetentionHold <date>` Befehl aus. Wenn beispielsweise angenommen wird, dass das heutige Datum der 1. Juni 2016 ist und Sie möchten, dass der Aufbewahrungszeitraum in 30 Tagen deaktiviert ist, führen `Set-Mailbox -EndDateForRetentionHold 7/1/2016`Sie den folgenden Befehl aus:. In diesem Szenario lassen Sie die *RentionHoldEnabled* -Eigenschaft auf *true*festgelegt. Weitere Informationen finden Sie unter [festlegen-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
  - Sie können die Einstellungen für die Aufbewahrungsrichtlinie ändern, die dem Postfach zugewiesen ist, sodass ältere Elemente, die importiert wurden, nicht sofort gelöscht oder in das Archivpostfach des Benutzers verschoben werden. Beispielsweise können Sie das Aufbewahrungs Alter für eine Lösch-oder Archivrichtlinie verlängern, die dem Postfach zugewiesen ist. In diesem Szenario würden Sie die Aufbewahrungszeit für das Postfach deaktivieren, nachdem Sie die Einstellungen der Aufbewahrungsrichtlinie geändert haben. Weitere Informationen finden Sie unter [Einrichten einer Archiv-und Löschrichtlinie für Postfächer in Ihrer Office 365 Organisation](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    

  

