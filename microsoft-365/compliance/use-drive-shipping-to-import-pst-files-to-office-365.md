---
title: Verwenden des Laufwerkversands zum Importieren der PST-Dateien Ihrer Organisation
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
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 40829b57-793c-4d41-b171-e9270129173d
ms.custom: seo-marvel-apr2020
description: Administratoren erfahren, wie Sie PST-Dateien Microsoft 365 massenimportieren, indem Sie PST-Dateien auf eine Festplatte kopieren und dann an Microsoft senden.
ms.openlocfilehash: 54b4e3bd7e092699017626c8257c17f965f46f6a
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114371"
---
# <a name="use-drive-shipping-to-import-your-organizations-pst-files"></a>Verwenden des Laufwerkversands zum Importieren der PST-Dateien Ihrer Organisation

**Dieser Artikel ist für Administratoren vorgesehen. Versuchen Sie, PST-Dateien in Ihr eigenes Postfach zu importieren? Weitere Informationen finden Sie unter Importieren von [E-Mails, Kontakten und Kalendern aus Outlook PST-Datei](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Verwenden Sie Office 365 Dienst importieren und den Laufwerkversand zum Massenimport von PST-Dateien in Benutzerpostfächer verwenden. Beim Laufwerkversand kopieren Sie die PST-Dateien auf eine Festplatte und senden diese auf dem Postweg an Microsoft. Wenn Microsoft Ihre Festplatte empfängt, kopiert das Rechenzentrumspersonal die Daten von der Festplatte in einen Speicherbereich in der Microsoft Cloud. Anschließend haben Sie die Möglichkeit, die in die Zielpostfächer importierten PST-Daten zu kürzen, indem Sie Filter festlegen, die steuern, welche Daten importiert werden. Nachdem Sie den Importauftrag gestartet haben, importiert der Importdienst die PST-Daten aus dem Speicherbereich in Benutzerpostfächer. Die Verwendung des Laufwerkversands zum Importieren von PST-Dateien in Benutzerpostfächer ist eine Möglichkeit, die E-Mails Ihrer Organisation zu Office 365.
  
Hier sind die schritte, die zum Importieren von PST-Dateien in Microsoft 365 verwendet werden müssen:
  
[Schritt 1: Herunterladen des Sicheren Speicherschlüssels und des PST-Importtools](#step-1-download-the-secure-storage-key-and-pst-import-tool)

[Schritt 2: Kopieren der PST-Dateien auf die Festplatte](#step-2-copy-the-pst-files-to-the-hard-drive)

[Schritt 3: Erstellen der PST-Importzuordnungsdatei](#step-3-create-the-pst-import-mapping-file)

[Schritt 4: Erstellen eines PST-Importauftrags in Office 365](#step-4-create-a-pst-import-job-in-office-365)

[Schritt 5: Versenden der Festplatte an Microsoft](#step-5-ship-the-hard-drive-to-microsoft)

[Schritt 6: Filtern von Daten und Starten des PST-Importauftrags](#step-6-filter-data-and-start-the-pst-import-job)
  
> [!IMPORTANT]
> Sie müssen Schritt 1 einmal ausführen, um den sicheren Speicherschlüssel und das Importtool zu laden. Folgen Sie nach dem Ausführen dieser Schritte Schritt 2 bis Schritt 6 jedes Mal, wenn Sie eine Festplatte an Microsoft senden möchten. 
  
Häufig gestellte Fragen zur Verwendung des Laufwerkversands zum Importieren von PST-Dateien in Office 365 finden Sie unter [FAQs for using drive shipping to import PST files](./faqimporting-pst-files-to-office-365.yml#using-drive-shipping-to-import-pst-files). 
  
## <a name="before-you-import-pst-files"></a>Vor dem Importieren von PST-Dateien

- Ihnen muss die Rolle für den Postfachimport/-export in Exchange Online zugewiesen werden, damit Sie PST-Dateien in Microsoft 365-Postfächer importieren können. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle „Postfachimport/-export“ zur Rollengruppe „Organisationsverwaltung“ hinzufügen. Oder Sie erstellen eine Rollengruppe, weisen die Rolle „Postfachimport/-export“ zu und fügen sich dann selbst als Mitglied hinzu. Weitere Informationen finden Sie im Abschnitt "Hinzufügen einer Rolle zu einer Rollengruppe" oder "Erstellen einer Rollengruppe" in [Verwalten von Rollengruppen](/Exchange/permissions-exo/role-groups).
    
    Darüber hinaus muss eine der folgenden Bedingungen erfüllt sein, um Importaufträge im Security & Compliance Center erstellen zu können:
    
  - Ihnen muss in Exchange Online die Rolle „E-Mail-Empfänger“ zugewiesen sein. Standardmäßig wird diese Rolle den Rollengruppen "Organisationsverwaltung" und "Empfängerverwaltung" zugewiesen.
    
    Oder
    
  - Sie müssen ein globaler Administrator in Ihrer Organisation sein.
    
    > [!TIP]
    > Erwägen Sie, in Exchange Online eine neue Rollengruppe speziell zum Importieren von PST-Dateien nach Office 365 zu erstellen. Legen Sie für die neue Rollengruppe als mindestens erforderliche Berechtigungen zum Importieren von PST-Dateien die Rollen "Postfachimport/-export" und "E-Mail-Empfänger" fest, und fügen Sie anschließend Mitglieder hinzu. 
  
- Sie müssen die PST-Dateien, die Sie auf die Festplatte kopieren möchten, auf einem Dateiserver oder einem freigegebenen Ordner in Ihrer Organisation speichern. In Schritt 2 führen Sie das Azure Import Export Tool (WAImportExport.exe) aus, das die auf diesem Dateiserver oder freigegebenen Ordner gespeicherten PST-Dateien auf die Festplatte kopiert.

- Große PST-Dateien können sich auf die Leistung des PST-Importprozesses auswirken. Daher wird empfohlen, dass jede PST-Datei, die Sie in Schritt 2 auf die Festplatte kopieren, nicht größer als 20 GB sein sollte.
    
- Nur 2,5-Zoll-SSDs (Solid-State Drives) oder 2,5-Zoll- oder 3,5-Zoll-SATA II/III-interne Festplatten werden für die Verwendung mit dem Office 365-Importdienst unterstützt. Sie können Festplatten bis zu 10 TB verwenden. Bei Importaufträgen wird nur das erste Datenvolume auf der Festplatte verarbeitet. Das Datenvolume muss mit NTFS formatiert sein. Beim Kopieren von Daten auf eine Festplatte können Sie sie direkt mit einer 2,5-Zoll-SSD oder einem 2,5-Zoll- oder 3,5-Zoll-SATA II/III-Connector anfügen oder extern mit einer externen 2,5-Zoll-SSD oder einem 2,5-Zoll- oder 3,5-Zoll-SATA II/III-USB-Adapter anfügen.
    
    > [!IMPORTANT]
    > Externe Festplatten mit einem integrierten USB-Adapter werden vom Office 365-Importdienst nicht unterstützt. Darüber hinaus kann der Datenträger innerhalb des Gehäuses einer externen Festplatte nicht verwendet werden. Versenden Sie keine externen Festplatten. 
  
- Die Festplatte, auf die Sie die PST-Dateien kopieren, muss mit BitLocker verschlüsselt sein. Das Tool WAImportExport.exe, das Sie in Schritt 2 ausführen, unterstützt Sie bei der Einrichtung von BitLocker. Außerdem wird ein BitLocker generiert, den Mitarbeiter des Microsoft Rechenzentrums verwenden, um auf das Laufwerk zu zugreifen, um die PST-Dateien in den Azure Storage in der Microsoft Cloud hochzuladen.
    
- Der Laufwerkversand ist über ein Microsoft Enterprise Agreement (EA) verfügbar. Der Laufwerkversand steht nicht im Rahmen von Microsoft Products und Services Agreement (MPSA) zur Verfügung.
    
- Die Kosten für den Import von PST-Dateien Microsoft 365 Postfächern mithilfe des Laufwerkversands beträgt 2 USD pro GB Daten. Wenn Sie z. B. eine Festplatte versenden, die 1.000 GB (1 TB) an PST-Dateien enthält, betragen die Kosten beispielsweise 2.000 Euro. Um die Importgebühren zu zahlen, können Sie mit einem Partner zusammenarbeiten. Informationen zum Suchen von Partnern finden Sie unter [Microsoft-Partner oder -Händler finden](../admin/manage/find-your-partner-or-reseller.md).
    
- Sie bzw. Ihre Organisation müssen über ein Konto bei FedEx oder DHL verfügen. 
    
  - Organisationen in den USA, Brasilien und Europa müssen über FedEx-Konten verfügen.
    
  - Organisationen in Ostasien, Südostasien, Japan, der Republik Korea und Australien müssen über DHL-Konten verfügen.
    
    Microsoft verwendet (und berechnet) dieses Konto, um die Festplatte an Sie zurückzukehren.
    
- Die Festplatte, die Sie an Microsoft senden, kann internationale Grenzen überschreiten. In diesem Fall sind Sie dafür verantwortlich, sicherzustellen, dass die Festplatte und die daten, die sie enthält, gemäß den geltenden Gesetzen importiert und/oder exportiert werden. Überprüfen Sie vor dem Versand einer Festplatte bei Ihren Beratern, ob Ihr Laufwerk und Ihre Daten legal an das identifizierte Microsoft-Rechenzentrum gesendet werden können. Dadurch wird sichergestellt, dass microsoft zeitnah erreicht wird.
    
- Bei diesem Verfahren werden ein sicherer Speicherschlüssel und ein BitLocker-Verschlüsselungsschlüssel kopiert und gespeichert. Ergreifen Sie entsprechende Vorsichtsmaßnahmen, um diese Schlüssel so zu schützen, wie Sie Kennwörter oder andere Sicherheitsinformationen schützen würden. Sie können sie zum Beispiel in einem kennwortgeschützten Microsoft Word-Dokument oder auf einem verschlüsselten USB-Laufwerk speichern. Ein Beispiel [für diese Schlüssel](#more-information) finden Sie im Abschnitt Weitere Informationen. 
    
- Nachdem PST-Dateien in ein postfach Microsoft 365 importiert wurden, ist die Aufbewahrungsaufbewahrungseinstellung für das Postfach für unbestimmte Zeit aktiviert. Dies bedeutet: Die dem Postfach zugewiesene Aufbewahrungsrichtlinie wird erst verarbeitet, nachdem Sie das Anhalten der Aufbewahrungszeit deaktiviert oder aber ein Datum zum Deaktivieren des Anhaltens festgelegt haben. Warum tun wir dies? Wenn die in ein Postfach importierten Nachrichten alt sind, werden sie möglicherweise endgültig gelöscht, weil ihr Aufbewahrungszeitraum, basierend auf den für das Postfach konfigurierten Aufbewahrungseinstellungen, abgelaufen ist. Wenn Sie das Postfach auf Anhalten der Aufbewahrungszeit setzen, erhält der Postfachbesitzer Zeit zum Verwalten dieser neu importierten Nachrichten, oder Sie erhalten Zeit zum Ändern der Aufbewahrungseinstellungen für das Postfach. Vorschläge [zum](#more-information) Verwalten des Aufbewahrungsspeichers finden Sie im Abschnitt Weitere Informationen. 
    
- Standardmäßig beträgt die maximale Nachrichtengröße, die von einem Microsoft 365-Postfach empfangen werden kann, 35 MB. Der Grund hierfür ist, dass der Standardwert für die Eigenschaft *MaxReceiveSize* für ein Postfach auf 35 MB festgelegt ist. Der Grenzwert für die maximale Größe empfangener Nachrichten in Microsoft 365 beträgt jedoch 150 MB. Wenn Sie also eine PST-Datei importieren, die ein Element enthält, das größer als 35 MB ist, ändert der Office 365-Importdienst den Wert der Eigenschaft *MaxReceiveSize* für das Zielpostfach automatisch in "150 MB". Dadurch können Nachrichten mit bis zu 150 MB in Benutzerpostfächer importiert werden. 
    
    > [!TIP]
    > Wenn Sie die Größe empfangener Nachrichten für ein Postfach ermitteln möchten, können Sie diesen Befehl in Exchange Online PowerShell ausführen: `Get-Mailbox <user mailbox> | FL MaxReceiveSize`. 
  
- Sie können PST-Dateien in ein inaktives Postfach in Office 365 importieren. Geben Sie hierzu den GUID des inaktiven Postfachs im Parameter `Mailbox` in der PST-Importzuordnungsdatei an. Weitere Informationen finden Sie unter [Schritt 3: Erstellen der PST-Importzuordnungsdatei.](#step-3-create-the-pst-import-mapping-file) 
    
- In einer Exchange-Hybridumgebung können Sie PST-Dateien für einen Benutzer, dessen primäres Postfach lokal gehostet wird, in ein cloudbasiertes Archivpostfach importieren. Gehen Sie hierzu in der PST-Importzuordnungsdatei folgendermaßen vor:
    
  - Geben Sie die E-Mail-Adresse des lokalen Postfachs des Benutzers im Parameter `Mailbox` an. 
    
  - Geben Sie den Wert **TRUE** im Parameter `IsArchive` an. 
    
    Weitere Informationen finden Sie unter [Schritt 3: Erstellen der PST-Importzuordnungsdatei.](#step-3-create-the-pst-import-mapping-file) 

## <a name="step-1-download-the-secure-storage-key-and-pst-import-tool"></a>Schritt 1: Herunterladen des Sicheren Speicherschlüssels und des PST-Importtools

Der erste Schritt besteht im Herunterladen des sicheren Speicherschlüssels und des Tools, den Sie in Schritt 2 zum Kopieren von PST-Dateien auf die Festplatte verwenden.
  
> [!IMPORTANT]
> Sie müssen Azure Import/Export Tool Version 1 (WAimportExportV1) verwenden, um PST-Dateien mithilfe der Laufwerkversandmethode erfolgreich zu importieren. Version 2 des Azure Import/Export wird nicht unterstützt, und die Verwendung dieses Tools führt zu einer fehlerhaften Vorbereitung der Festplatte für den Importauftrag. Laden Sie das Azure Import/Export-Tool aus dem Security & Compliance Center herunter, indem Sie die Verfahren in diesem Schritt durchführen. 
  
1. Navigieren Sie zu [https://protection.office.com/](https://protection.office.com/), und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an. 
    
2. Klicken Sie im linken Bereich des Security & Compliance Centers auf **Information Governance** \> **Import** \> **Importieren von PST-Dateien**.
    
    > [!NOTE]
    > Wie bereits erwähnt, müssen Ihnen die entsprechenden  Berechtigungen für den Zugriff auf die Importseite im Security & Compliance Center zugewiesen werden. 
  
3. Klicken Sie auf der Seite **Import von PST-Dateien** ![Symbol hinzufügen](../media/ITPro-EAC-AddIcon.gif) **Neuer Importauftrag**.
    
4. Geben Sie im Assistenten für den Importauftrag einen Namen für den PST-Importauftrag ein, und klicken Sie dann auf **Weiter**. Verwenden Sie Kleinbuchstaben, Zahlen, Bindestriche und Unterstriche. Sie dürfen weder Großbuchstaben noch Leerzeichen in dem Namen verwenden.
    
5. Klicken Sie **auf der Seite Auftragstyp** importieren auf **Festplatten** an einen unserer physischen Speicherorte versenden, und klicken Sie dann auf **Weiter**.
    
    ![Klicken Sie auf Festplatten an einen unserer physischen Speicherorte versenden, um einen Importauftrag für den Laufwerkversand zu erstellen.](../media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. Führen Sie auf der Seite **Daten importieren** einen der folgenden Schritte aus: 
    
    ![Kopieren Sie den Sicheren Speicherschlüssel, und laden Sie das Azure Import Export-Tool auf der Seite Daten importieren herunter.](../media/e22e0b48-e5ce-48e0-95bc-0490a2b3b983.png)
  
    a. Klicken Sie in Schritt 2 auf **Sicherer Speicherschlüssel kopieren.** Nachdem der Speicherschlüssel angezeigt wurde, klicken Sie auf **In** Zwischenablage kopieren, fügen Sie ihn ein, und speichern Sie ihn in einer Datei, damit Sie später darauf zugreifen können.
    
    b. Laden Sie in Schritt 3 das **Tool Azure Import/Export herunter,** um das Azure Import/Export (Version 1) herunterzuladen und zu installieren.
    
    - Klicken Sie im Popupfenster  auf Speichern unter, um die WaImportExportV1.zip in einem Ordner auf dem lokalen \>  Computer zu speichern. 
    
    - Extrahieren Sie WaImportExportV1.zip Datei.
    
7. Klicken **Sie auf Abbrechen,** um den Assistenten zu schließen. 
    
    Beim Erstellen des **Importauftrags** in Schritt 4 & Sie zur Seite Importieren im Security & Compliance Center zurück. 

## <a name="step-2-copy-the-pst-files-to-the-hard-drive"></a>Schritt 2: Kopieren der PST-Dateien auf die Festplatte

Der nächste Schritt besteht darin, die PST-Dateien mithilfe des Tools WAImportExport.exe auf die Festplatte zu kopieren. Mit diesem Tool werden die Festplatte mit BitLocker verschlüsselt, die PST-Dateien auf die Festplatte kopiert und eine Journaldatei erstellt, die Informationen zum Kopiervorgang speichert. Damit Sie diesen Schritt ausführen können, müssen sich die PST-Dateien in einer Dateifreigabe oder auf einem Dateiserver in Ihrer Organisation befinden. Im folgenden Verfahren wird dies als das Quellverzeichnis bezeichnet. 

 Wie bereits erwähnt, sollte jede PST-Datei, die Sie auf die Festplatte kopieren, nicht größer als 20 GB sein. PST-Dateien mit mehr als 20 GB können sich auf die Leistung des PST-Importprozesses auswirken, die Sie in Schritt 6 starten.
  
> [!IMPORTANT]
> Nach der ersten Verwendung des Tools WAImportExport.exe für ein Laufwerk müssen Sie jedes weitere Mal eine andere Syntax verwenden. Diese Syntax wird in Schritt 4 dieses Verfahrens erläutert, um #A0 auf die Festplatte zu kopieren. 
  
1. Öffnen Sie eine Eingabeaufforderung auf dem lokalen Computer.
    
    > [!TIP]
    > Wenn Sie die Eingabeaufforderung als Administrator ausführen (durch Auswahl von „Als Administrator ausführen“ beim Öffnen), werden im Fenster der Eingabeaufforderung Fehlermeldungen angezeigt. Dies kann Ihnen bei der Behandlung von Problemen beim Ausführen des Tools „WAImportExport.exe“ helfen. 
  
2. Wechseln Sie zu dem Verzeichnis, in dem Sie das Tool „WAImportExport.exe“ in Schritt 1 installiert haben.
    
3. Wenn Sie „WAImportExport.exe“ zum ersten Mal verwenden, um die PST-Dateien auf eine Festplatte zu kopieren, führen Sie den folgenden Befehl aus.

    ```powershell
    WAImportExport.exe PrepImport /j:<Name of journal file> /t:<Drive letter> /id:<Name of session> /srcdir:<Location of PST files> /dstdir:<PST file path> /sk:<Storage account key> /blobtype:BlockBlob /encrypt /logdir:<Log file location>
    ```

    In der folgenden Tabelle werden die Parameter und deren erforderliche Werte beschrieben.
    
    |**Parameter**|**Beschreibung**|**Beispiel**|
    |:-----|:-----|:-----|
    | `/j:` <br/> |Gibt den Namen der Journaldatei an. Diese Datei wird im selben Ordner gespeichert, in dem sich das Tool „WAImportExport.exe“ befindet. Jede Festplatte, die Sie an Microsoft senden, muss eine Journaldatei enthalten. Jedes Mal, wenn Sie „WAImportTool.exe“ zum Kopieren von PST-Dateien auf eine Festplatte ausführen, werden Informationen zur Journaldatei dieser Festplatte hinzugefügt. 
  <br/> Mitarbeiter des Microsoft Rechenzentrums verwenden die Informationen in der Journaldatei, um die Festplatte dem in Schritt 4 erstellten Importauftrag zuzuordnen und die PST-Dateien in den bereich Azure Storage in der Microsoft Cloud hochzuladen.  <br/> | `/j:PSTHDD1.jrn` <br/> |
    | `/t:` <br/> |Gibt den Buchstaben des Laufwerks an, wenn die Festplatte an Ihren lokalen Computer angeschlossen ist.  <br/> | `/t:h` <br/> |
    | `/id:` <br/> |Gibt den Namen der Kopiersitzung an. Eine Sitzung ist definiert als jeder einzelne Vorgang, in dem Sie das Tool „WAImportExport.exe“ ausführen und Dateien auf die Festplatte kopieren. Die PST-Dateien werden in einen Ordner mit dem Namen der Sitzung kopiert, der durch diesen Parameter angegeben wird.   <br/> | `/id:driveship1` <br/> |
    | `/srcdir:` <br/> |Gibt das Quellverzeichnis in Ihrer Organisation an, das die PST-Dateien enthält, die während der Sitzung kopiert werden. Beachten Sie, den Wert dieses Parameters in doppelte Anführungszeichen (" ") einzuschließen.  <br/> | `/srcdir:"\\FILESERVER01\PSTs"` <br/> |
    | `/dstdir:` <br/> |Gibt das Zielverzeichnis im Azure Storage in der Microsoft Cloud an, in dem die PSTs hochgeladen werden. Sie müssen den Wert  `ingestiondata/` verwenden. Beachten Sie, den Wert dieses Parameters in doppelte Anführungszeichen (" ") einzuschließen.  <br/> Optional können Sie dem Wert dieses Parameters auch einen zusätzlichen Dateipfad hinzufügen. Sie können z. B. den Dateipfad des Quellverzeichnisses auf der Festplatte (in ein URL-Format konvertiert) verwenden, der im Parameter angegeben  `/srcdir:` ist. Wird z.  `\\FILESERVER01\PSTs` B. in  `FILESERVER01/PSTs` geändert. In diesem Fall müssen Sie den  `ingestiondata` Dateipfad weiterhin verwenden. In diesem Beispiel ist der Wert für den  `/dstdir:` Parameter also  `"ingestiondata/FILESERVER01/PSTs"` .  <br/> Das Hinzufügen des zusätzlichen Dateipfads ist z. B. dann sinnvoll, wenn einige Ihrer PST-Dateien den gleichen Dateinamen aufweisen.  <br/> > [!NOTE]> Wenn Sie den optionalen Pfadnamen eingeben, enthält der Namespace für eine #A0 nach dem Hochladen in den bereich Azure Storage den Pfadnamen und den Namen der PST-Datei. Beispiel: `FILESERVER01/PSTs/annb.pst` . Wenn Sie keinen Pfadnamen eingeben, ist der Namespace nur der PST-Dateiname. beispiel:  `annb.pst` .           | `/dstdir:"ingestiondata/"` <br/> Oder  <br/>  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` <br/> |
    | `/sk:` <br/> |Gibt den Speicherkontoschlüssel an, den Sie in Schritt 1 abgerufen haben. Beachten Sie, den Wert dieses Parameters in doppelte Anführungszeichen (" ") einzuschließen.  <br/> | `"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ=="` <br/> |
    | `/blobtype:` <br/> |Gibt den Typ der Blobs im Bereich Azure Storage an, in den die PST-Dateien importiert werden. Verwenden Sie zum Importieren von PST-Dateien den Wert **BlockBlob**. Dieser Parameter ist erforderlich.   <br/> | `/blobtype:BlockBlob` <br/> |
    | `/encrypt` <br/> |Diese Option aktiviert BitLocker für die Festplatte. Dieser Parameter ist beim erstmaligen Ausführen des Tools „WAImportExport.exe“ erforderlich.  <br/> Der BitLocker-Verschlüsselungsschlüssel wird in die Journaldatei und die Protokolldatei kopiert, die erstellt wird, wenn Sie den Parameter `/logfile:` verwenden. Wie bereits erwähnt wird die Journaldatei im selben Ordner gespeichert, in dem sich das Tool „WAImportExport.exe“ befindet.  <br/> | `/encrypt` <br/> |
    | `/logdir:` <br/> |Dieser optionale Parameter gibt einen Ordner an, in dem die Protokolldateien gespeichert werden können. Wenn nicht angegeben, werden die Protokolldateien in dem Ordner gespeichert, in dem sich WAImportExport.exe befindet. Beachten Sie, den Wert dieses Parameters in doppelte Anführungszeichen (" ") einzuschließen.  <br/> | `/logdir:"c:\users\admin\desktop\PstImportLogs"` <br/> |
   
    Nachfolgend sehen Sie ein Beispiel der Syntax für das Tool „WAImportExport.exe“, in dem die tatsächlichen Werte für jeden Parameter verwendet werden:
    
    ```powershell
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /t:f /id:driveship1 /srcdir:"\\FILESERVER01\PSTs" /dstdir:"ingestiondata/" /sk:"yaNIIs9Uy5g25Yoak+LlSHfqVBGOeNwjqtBEBGqRMoidq6/e5k/VPkjOXdDIXJHxHvNoNoFH5NcVUJXHwu9ZxQ==" blobtype:BlockBlob /encrypt /logdir:"c:\users\admin\desktop\PstImportLogs"
    ```

    Nachdem Sie den Befehl ausgeführt haben, werden Statusmeldungen angezeigt, die den Fortschritt des Kopierens der PST-Dateien auf die Festplatte anzeigen. Eine endgültige Statusmeldung zeigt die Gesamtzahl der Dateien an, die erfolgreich kopiert wurden. 
    
4. Führen Sie diesen Befehl jedes Mal aus, wenn Sie das Tool „WAImportExport.exe“ zum Kopieren der PST-Dateien auf dieselbe Festplatte ausführen.

    ```powershell
    WAImportExport.exe PrepImport /j:<Name of journal file> /id:<Name of new session> /srcdir:<Location of PST files> /dstdir:<PST file path> /blobtype:BlockBlob 
    ```

    Im Folgenden sehen Sie ein Beispiel der Syntax für die Ausführung weiterer Sitzungen zum Kopieren von PST-Dateien auf dieselbe Festplatte.  

    ```powershell
    WAImportExport.exe PrepImport /j:PSTHDD1.jrn /id:driveship2 /srcdir:"\\FILESERVER01\PSTs\SecondBatch" /dstdir:"ingestiondata/" /blobtype:BlockBlob
    ```

## <a name="step-3-create-the-pst-import-mapping-file"></a>Schritt 3: Erstellen der PST-Importzuordnungsdatei

Nachdem Mitarbeiter des Microsoft Rechenzentrums die PST-Dateien von der Festplatte in den bereich Azure Storage hochgeladen haben, verwendet der Importdienst die Informationen in der PST-Importzuordnungsdatei, einer CSV-Datei (Comma-separated Value), die angibt, in welche Benutzerpostfächer die PST-Dateien importiert werden. Diese CSV-Datei wird im nächsten Schritt übermittelt, wenn Sie einen PST-Importauftrag erstellen.
  
1. [Laden Sie eine Kopie der PST-Importzuordnungsdatei herunter](https://go.microsoft.com/fwlink/p/?LinkId=544717).
    
2. Öffnen oder speichern Sie die CSV-Datei auf Ihrem lokalen Computer. Das folgende Beispiel zeigt eine abgeschlossene PST-Importzuordnungsdatei (in Editor geöffnet). Es ist wesentlich einfacher, Microsoft Excel zum Bearbeiten der CSV-Datei zu verwenden.

    ```text
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
  
3. Verwenden Sie die Informationen in der folgenden Tabelle, um die CSV-Datei mit den erforderlichen Informationen zu füllen.
    
    |**Parameter**|**Beschreibung**|**Beispiel**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Gibt den Dienst an, in den Daten importiert werden. Verwenden Sie `Exchange`, um PST-Dateien in Benutzerpostfächer zu importieren.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> | Gibt den Ordnerspeicherort im Azure Storage an, in den PST-Dateien kopiert werden, wenn die Festplatte an Microsoft gesendet wird.  <br/>  Was Sie in dieser Spalte in der CSV-Datei hinzufügen, hängt davon ab, was Sie im vorherigen Schritt für den Parameter  `/dstdir:` angegeben haben. Wenn Sie über Unterordner am Quellspeicherort verfügen, muss der Wert im Parameter den relativen Pfad für den Unterordner enthalten, z. B. `FilePath` /folder1/user1/.  <br/>  Wenn Sie verwendet  `/dstdir:"ingestiondata/"` haben, lassen Sie diesen Parameter in der CSV-Datei leer.  <br/>  Wenn Sie einen optionalen Pfadnamen für den Wert des Parameters (z. B. ) angegeben haben, verwenden Sie diesen  `/dstdir:`  `/dstdir:"ingestiondata/FILESERVER01/PSTs"` Pfadnamen (ohne "Ingestiondata") für diesen Parameter in der CSV-Datei. Beim Wert für diesen Parameter muss die Groß-/Kleinschreibung beachtet werden.  <br/>  In beiden Fällen schließen Sie "ingestiondata" *nicht* in den Wert für den Parameter `FilePath` ein. Lassen Sie diesen Parameter leer, oder geben Sie nur den optionalen Pfadnamen an.  <br/> > [!IMPORTANT]> Der Fall für den Dateinamen muss der gleiche Fall sein, den Sie im Parameter im  `/dstdir:` vorherigen Schritt angegeben haben. Wenn Sie beispielsweise im vorherigen Schritt für den Unterordnernamen verwendet haben, aber dann im Parameter in der CSV-Datei verwendet werden, tritt beim Import für die  `"ingestiondata/FILESERVER01/PSTs"`  `fileserver01/psts`  `FilePath` PST-Datei ein Fehler auf. Denken Sie deshalb daran, in beiden Fällen dieselbe Groß-/Kleinschreibung zu verwenden.           |(leer lassen)  <br/> Oder  <br/>  `FILESERVER01/PSTs` <br/> |
    | `Name` <br/> |Gibt den Namen der PST-Datei an, die in das Benutzerpostfach importiert wird. Beim Wert für diesen Parameter muss die Groß-/Kleinschreibung beachtet werden.  <br/> > [!IMPORTANT]> Der Fall für den PST-Dateinamen in der CSV-Datei muss mit der PST-Datei identisch sein, die in Schritt 2 an den Speicherort Azure Storage hochgeladen wurde. Wenn Sie beispielsweise `annb.pst` im Parameter `Name` der CSV-Datei verwenden, der Name der tatsächlichen PST-Datei aber `AnnB.pst` lautet, schlägt der Import für diese PST-Datei fehl. Sorgen Sie deshalb dafür, dass im Namen der PST-Datei in der CSV-Datei dieselbe Groß-/Kleinschreibung wie in der tatsächlichen PST-Datei verwendet wird.           | `annb.pst` <br/> |
    | `Mailbox` <br/> |Gibt die E-Mail-Adresse des Postfachs an, in das die PST-Datei importiert werden soll. Sie können keinen öffentlichen Ordner angeben, da der PST-Importdienst keine Unterstützung für den Import von PST-Dateien in öffentliche Ordner bietet.  <br/> Zum Importieren einer PST-Datei in ein inaktives Postfach müssen Sie für diesen Parameter die Postfach-GUID angeben. Zum Abrufen dieser GUID führen Sie den folgenden PowerShell-Befehl in Exchange Online aus: `Get-Mailbox <identity of inactive mailbox> -InactiveMailboxOnly | FL Guid`. <br/> > [!NOTE]> Manchmal haben Sie mehrere Postfächer mit derselben E-Mail-Adresse, wobei ein Postfach ein aktives Postfach und das andere Postfach sich in einem zustand mit soft-deleted (oder inaktiv) befindet. In diesen Fällen müssen Sie die Postfach-GUID angeben, um das Postfach eindeutig zu identifizieren, in das die PST-Datei importiert werden soll. Zum Abrufen dieser GUID für aktive Postfächer führen Sie den folgenden PowerShell-Befehl aus: `Get-Mailbox <identity of active mailbox> | FL Guid`. Führen Sie den folgenden Befehl aus, um die GUID für nicht gelöschte (oder inaktive) Postfächer zu erhalten:  `Get-Mailbox <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid` .           | `annb@contoso.onmicrosoft.com` <br/> Oder  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Gibt an, ob die PST-Datei in das Archivpostfach des Benutzers importiert werden soll. Es gibt zwei Möglichkeiten:  <br/> **FALSE** Importiert die PST-Datei in das primäre Postfach des Benutzers.  <br/> **TRUE** Importiert die PST-Datei in das Archivpostfach des Benutzers. Dies setzt voraus, dass das [Archivpostfach des Benutzers aktiviert ist](enable-archive-mailboxes.md). Wenn Sie diesen Parameter auf `TRUE` festlegen und das Archivpostfach des Benutzers nicht aktiviert ist, schlägt der Import für diesen Benutzer fehl. Wenn der Import für einen Benutzer fehlschlägt (weil sein Archiv nicht aktiviert und diese Eigenschaft auf `TRUE` festgelegt ist), sind die übrigen Benutzer im Importauftrag davon nicht betroffen.  <br/>  Wenn Sie diesen Parameter leer lassen, wird die PST-Datei in das primäre Postfach des Benutzers importiert.  <br/> **Hinweis:** Zum Importieren einer PST-Datei in ein cloudbasiertes Archivpostfach für einen Benutzer, dessen primäres Postfach lokal gehostet wird, geben Sie für diesen Parameter einfach `TRUE` an und geben Sie die E-Mail-Adresse des lokalen Postfachs des Benutzers für den Parameter `Mailbox` an.  <br/> | `FALSE` <br/> Oder  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Gibt den Postfachordner an, in den die PST-Datei importiert wird.  <br/>  Wenn Sie diesen Parameter leer lassen, wird das PST in einen neuen Ordner mit dem Namen **Importiert** importiert importiert, der sich auf der Stammebene des Postfachs befindet (die gleiche Ebene wie der Posteingangsordner und die anderen Standardpostfachordner).  <br/>  Wenn Sie  `/` angeben, werden Elemente in der PST-Datei direkt in den Posteingangsordner des Benutzers importiert.  <br/>  Wenn Sie  `/<foldername>` angeben, werden Elemente in der PST-Datei in einen Ordner namens  *\<foldername\>* importiert. Bei Verwendung von `/ImportedPst` würden beispielsweise Elemente in einen Ordner mit dem Namen **ImportedPst** importiert. Dieser Ordner befindet sich im Postfach des Benutzers auf der gleichen Ebene wie der Ordner "Posteingang".  <br/> |(leer lassen)  <br/> Oder  <br/>  `/` <br/> Oder  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Dieser optionale Parameter gibt einen numerischen Wert für die Codepage an, die zum Importieren von PST-Dateien im ANSI-Dateiformat verwendet werden muss. Der Parameter wird zum Importieren von PST-Dateien aus chinesischen, japanischen und koreanischen (CJK) Organisationen verwendet, weil in diesen Sprachen normalerweise ein Doppelbyte-Zeichensatz (double byte character set, DBCS) verwendet wird. Wenn dieser Parameter nicht verwendet wird, um PST-Dateien für Sprachen zu importieren, die DBCS für die Namen von Postfachordnern verwenden, sind die Ordnernamen nach dem Import oft nicht leserlich.  <br/> Eine Liste von unterstützten Werten, die für diesen Parameter verwendet werden müssen, finden Sie unter [CodePage-Bezeichner](/windows/win32/intl/code-page-identifiers).  <br/> > [!NOTE]> Wie bereits erwähnt, handelt es sich um einen optionalen Parameter, und Sie müssen ihn nicht in die CSV-Datei angeben. Sie können ihn aber auch einschließen und den Wert für eine oder mehrere Zeilen leer lassen.           |(leer lassen)  <br/> Oder  <br/>  `932` (dies ist der Codepagebezeichner für ANSI/OEM – Japanisch)  <br/> |
    | `SPFileContainer` <br/> |Lassen Sie diesen Parameter für den PST-Import leer.  <br/> |Nicht zutreffend  <br/> |
    | `SPManifestContainer` <br/> |Lassen Sie diesen Parameter für den PST-Import leer.  <br/> |Nicht zutreffend  <br/> |
    | `SPSiteUrl` <br/> |Lassen Sie diesen Parameter für den PST-Import leer.  <br/> |Nicht zutreffend  <br/> |

## <a name="step-4-create-a-pst-import-job-in-office-365"></a>Schritt 4: Erstellen eines PST-Importauftrags in Office 365

Der nächste Schritt besteht darin, den PST-Importauftrag im Importdienst in Office 365 zu erstellen. Wie bereits erläutert, übermitteln Sie die pst-Importzuordnungsdatei, die Sie in Schritt 3 erstellt haben. Nachdem Sie den Auftrag erstellt haben, verwendet der Importdienst die Informationen in der Zuordnungsdatei, um die PST-Dateien in das angegebene Benutzerpostfach zu importieren, nachdem die PST-Dateien von der Festplatte in den Bereich Azure Storage kopiert wurden und Sie den Importauftrag erstellen und starten.
  
1. Navigieren Sie zu [https://protection.office.com](https://protection.office.com), und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an. 
    
2. Klicken Sie im linken Bereich des Security & Compliance Centers auf **Information Governance** \> **Import** \> **Importieren von PST-Dateien**.
    
3. Klicken Sie auf der Seite **Import von PST-Dateien** ![Symbol hinzufügen](../media/ITPro-EAC-AddIcon.gif) **Neuer Importauftrag**.
    
    > [!NOTE]
    > Wie bereits erwähnt, müssen Ihnen die entsprechenden  Berechtigungen für den Zugriff auf die Importseite im Security & Compliance Center zugewiesen werden. 
  
4. Geben Sie einen Namen für den PST-Importauftrag ein, und klicken Sie dann auf **Weiter**. Verwenden Sie Kleinbuchstaben, Zahlen, Bindestriche und Unterstriche. Sie dürfen weder Großbuchstaben noch Leerzeichen in dem Namen verwenden.
    
5. Klicken Sie **auf der Seite Auftragstyp** importieren auf **Festplatten** an einen unserer physischen Speicherorte versenden, und klicken Sie dann auf **Weiter**.
    
    ![Klicken Sie auf Festplatten an einen unserer physischen Speicherorte versenden, um einen Importauftrag für den Laufwerkversand zu erstellen.](../media/1584fdc5-cd4c-4e47-932e-db6c8e07f5f8.png)
  
6. Klicken Sie in Schritt 6 auf die Kontrollkästchen Ich **habe** meine  Festplatten vorbereitet und habe Zugriff auf die erforderlichen Laufwerkjournaldateien, und ich habe Zugriff auf die Zuordnungsdatei, und klicken Sie dann auf **Weiter**.
    
    ![Klicken Sie in Schritt 6 auf die beiden Kontrollkästchen.](../media/fad43078-ea68-4acd-b2ed-75a800183262.png)
  
7. Klicken Sie **auf** der Seite Laufwerkdatei auswählen auf Laufwerksdatei **auswählen,** und wechseln Sie dann zu dem Ordner, in dem sich WAImportExport.exe befindet. Die in Schritt 2 erstellte Journaldatei wurde in diesen Ordner kopiert.
    
    ![Klicken Sie auf Laufwerksdatei auswählen, um die Journaldatei zu übermitteln, die beim Durchführen des Tools WAImportExport.exe wurde](../media/1ea35c04-bd88-4d7e-b7d9-dc390149d94f.png)
  
8. Wählen Sie die Journaldatei aus. Beispiel: `PSTHDD1.jrn` .
    
    > [!TIP]
    > Wenn Sie das Tool WAImportExport.exe Schritt 2 ausgeführt haben, wurde der Name der Journaldatei durch den Parameter  `/j:` angegeben. 
  
9. Nachdem der Name der Laufwerksdatei unter **Laufwerkdateiname** angezeigt wird, klicken Sie auf **Überprüfen,** um die Laufwerksdatei auf Fehler zu überprüfen. 
    
    ![Klicken Sie auf Überprüfen, um die ausgewählte Laufwerksdatei zu überprüfen.](../media/4b707f5a-152a-4e74-b9f5-449c88d1fec4.png)
  
    Die Laufwerksdatei muss erfolgreich überprüft werden, um einen PST-Importauftrag zu erstellen. Der Dateiname wird grün angezeigt, wenn die Überprüfung der Datei erfolgreich war. Wenn die Überprüfung fehlschlägt, klicken Sie auf den Link **Protokoll anzeigen**. Es wird ein Überprüfungsfehlerbericht mit einer Fehlermeldung mit Informationen dazu geöffnet, warum die Datei fehlgeschlagen ist. 
    
    > [!NOTE]
    > Sie müssen eine Journaldatei für jede Festplatte hinzufügen und überprüfen, die Sie an Microsoft senden. 
  
10. Klicken Sie nach dem Hinzufügen und Überprüfen einer Journaldatei für jede Festplatte, die Sie an Microsoft senden, auf **Weiter**.
    
11. Klicken ![ Sie auf Symbol auswählen ](../media/ITPro-EAC-AddIcon.gif) **Zuordnungsdatei auswählen,** um die pst-Importzuordnungsdatei zu übermitteln, die Sie in Schritt 3 erstellt haben. 
    
    ![Klicken Sie auf "Zuordnungsdatei auswählen", um die CSV-Datei zu übermitteln, die Sie für den Importvorgang erstellt haben.](../media/d30b1d73-80bb-491e-a642-a21673d06889.png)
  
12. Wenn der Name der CSV-Datei unter **Name der Zuordnungsdatei** angezeigt wird, klicken Sie auf **Überprüfen**, um die CSV-Datei auf Fehler zu überprüfen. 
    
    ![Klicken Sie auf "Überprüfen", um die CSV-Datei auf Fehler zu überprüfen.](../media/4680999d-5538-4059-b878-2736a5445037.png)
  
    Die CSV-Datei muss erfolgreich überprüft werden, um einen PST-Importauftrag zu erstellen. Der Dateiname wird grün angezeigt, wenn die Überprüfung der Datei erfolgreich war. Wenn die Überprüfung fehlschlägt, klicken Sie auf den Link **Protokoll anzeigen**. Der Bericht mit den Überprüfungsfehlern wird geöffnet, in dem für jede Zeile in der Datei, in der ein Fehler aufgetreten ist, eine Fehlermeldung aufgeführt ist. 
    
13. Nachdem die PST-Zuordnungsdatei erfolgreich überprüft wurde, klicken Sie auf **Weiter**.
    
14. Geben Sie **auf der Seite Kontaktinformationen** bereitstellen Ihre Kontaktinformationen in die entsprechenden Felder ein. 
    
    Die Adresse für den Microsoft-Standort, an den Sie Ihre Festplatten versenden, wird angezeigt. Diese Adresse wird basierend auf Ihrem Microsoft-Rechenzentrumsspeicherort automatisch generiert. Kopieren Sie diese Adresse in eine Datei oder erstellen Sie einen Screenshot.
    
15. Lesen Sie das Dokument mit den Geschäftsbedingungen, klicken Sie auf das Kontrollkästchen, und klicken Sie dann auf **Speichern,** um den Importauftrag zu übermitteln. 
    
    Wenn der Importauftrag erfolgreich erstellt wurde, wird eine Statusseite angezeigt, auf der die nächsten Schritte des Laufwerkversandprozesses erläutert werden.
    
16. Klicken Sie **auf der Seite PST-Dateien** importieren auf Aktualisierungssymbol Aktualisieren, um den neuen Importauftrag für den Laufwerkversand in der Liste ![ der ](../media/O365-MDM-Policy-RefreshIcon.gif)  Importaufträge angezeigt zu bekommen. Der Status ist auf Warten **auf Nachverfolgungsnummer festgelegt.** Sie können auch auf den Importauftrag klicken, um die Statusf flyout-Seite mit ausführlicheren Informationen zum Importauftrag anzeigen zu können.
 
## <a name="step-5-ship-the-hard-drive-to-microsoft"></a>Schritt 5: Versenden der Festplatte an Microsoft

Im nächsten Schritt wird die Festplatte an Microsoft gesendet und dann die Nachverfolgungsnummer für die Lieferung und die Lieferinformationen für den Laufwerkversandauftrag zur Verfügung stellen. Nachdem das Laufwerk von Microsoft empfangen wurde, dauert es zwischen 7 und 10 Werktagen, bis Mitarbeiter des Rechenzentrums Ihre PST-Dateien in den Azure Storage ihrer Organisation hochladen.
  
> [!NOTE]
> Wenn Sie die Nachverfolgungsnummer und die Lieferinformationen nicht innerhalb von 14 Tagen nach dem Erstellen des Importauftrags zurückgeben, läuft der Importauftrag ab. In diesem Fall müssen Sie einen neuen Importauftrag für den Laufwerkversand erstellen (siehe Schritt 4: Erstellen eines [PST-Importauftrags in Office 365](#step-4-create-a-pst-import-job-in-office-365)) und die Laufwerksdatei und die PST-Importzuordnungsdatei erneut übermitteln. 
  
### <a name="ship-the-hard-drive"></a>Versenden der Festplatte

Beachten Sie die folgenden Punkte, wenn Sie Festplatten an Microsoft senden:
  
- Versenden Sie den SATA-zu-USB-Adapter nicht. Sie müssen nur die Festplatte versenden.
    
- Verpacken Sie die Laufwerke ordnungsgemäß; verwenden Sie z. B. antistatische Verpackung oder Luftpolsterfolie.
    
- Senden Sie die Festplatte mit einem Spediteur Ihrer Wahl an Microsoft.
    
- Verwenden Sie als Versandadresse den Microsoft-Standort, der Ihnen beim Erstellen des Importauftrags in Schritt 4 angezeigt wurde. Vergessen Sie nicht, in der Versandadresse den Zusatz „Office 365 Import Service“ anzugeben.
    
- Nachdem Sie die Festplatte versendet haben, notieren Sie sich den Namen des Spediteurs und die Nachverfolgungsnummer. Diese müssen Sie im nächsten Schritt angeben.
    
### <a name="enter-the-tracking-number-and-other-shipping-information"></a>Eingabe der Nachverfolgungsnummer und anderer Versandinformationen

Nachdem Sie die Festplatte an Microsoft gesendet haben, führen Sie auf der Seite des Importdiensts die folgenden Schritte aus.
  
1. Navigieren Sie zu [https://protection.office.com](https://protection.office.com), und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an. 
    
2. Klicken Sie im linken Bereich auf **Informationsverwaltung > Importieren > Importieren von PST-Dateien**.
    
3. Klicken Sie auf der Seite **PST-Dateien** importieren auf den Auftrag für die Laufwerkslieferung, für die Sie die Nachverfolgungsnummer eingeben möchten. 
    
4. Klicken Sie auf der Seite Statusf flyout auf **Trackingnummer eingeben.**
    
5. Geben Sie die folgenden Versandinformationen an:
    
1. **Zustellungsanbieter** Geben Sie den Namen des Zustellanbieters ein, den Sie zum Versenden der Festplatte an Microsoft verwendet haben. 
    
2. **Nachverfolgungsnummer** Geben Sie die Nachverfolgungsnummer für die Festplattenlieferung ein. 
    
3. **Kontonummer des Netzbetreibers zurückgeben** Geben Sie die Kontonummer Ihrer Organisation für den Netzbetreiber ein, der unter **Rückgabeanbieter aufgeführt ist.** Microsoft verwendet (und berechnet) dieses Konto, um Ihre Festplatte an Sie zurück zu senden. Organisationen in den USA und Europa müssen über ein Konto bei FedEx verfügen. Organisationen in Asien und dem Rest der Welt müssen über ein Konto bei DHL verfügen.
    
6. Klicken Sie auf **Speichern**, um diese Informationen für den Importauftrag zu speichern. 
    
    Klicken Sie **auf der Seite PST-Dateien** importieren auf Aktualisierungssymbol Aktualisieren, um die Informationen für Ihren Importauftrag für ![ den ](../media/O365-MDM-Policy-RefreshIcon.gif)  Laufwerkversand zu aktualisieren. Beachten Sie, dass der Status jetzt **Festplatten werden gesendet** lautet.

## <a name="step-6-filter-data-and-start-the-pst-import-job"></a>Schritt 6: Filtern von Daten und Starten des PST-Importauftrags

Nachdem Ihre Festplatte von Microsoft empfangen wurde, ändert sich der Status für den Importauftrag auf der Seite **PST-Dateien** importieren in **"Empfangene Laufwerke".** Mitarbeiter des Rechenzentrums verwenden die Informationen in der Journaldatei, um Ihre PST-Dateien in den Azure Storage Ihrer Organisation hochzuladen. An diesem Punkt ändert sich der Status in **In Bearbeitung importieren**. Wie bereits erwähnt, dauert es zwischen 7 und 10 Werktage, nachdem Sie Ihre Festplatte erhalten haben, um die PST-Dateien hochzuladen.
  
Nachdem PST-Dateien in Azure hochgeladen wurden, wird der Status in **Analyse in Bearbeitung geändert.** Dies bedeutet, Microsoft 365 die Daten in den PST-Dateien (sicher und sicher) analysiert, um das Alter der Elemente und die verschiedenen Nachrichtentypen zu identifizieren, die in den PST-Dateien enthalten sind. Wenn die Analyse abgeschlossen ist und die Daten importiert werden können, wird der Status für den Importauftrag in **Analysis completed geändert.** An diesem Punkt haben Sie die Möglichkeit, alle In den PST-Dateien enthaltenen Daten zu importieren, oder Sie können die importierten Daten kürzen, indem Sie Filter festlegen, die steuern, welche Daten importiert werden.
  
1. Navigieren Sie zu [https://protection.office.com](https://protection.office.com), und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an. 
    
2. Klicken Sie im linken Bereich auf **Informationsverwaltung** \> **Importieren von** \> **PST-Dateien importieren.**
    
3. Klicken Sie auf der Seite **PST-Dateien** importieren auf Bereit zum Importieren in **Office 365** für den Importauftrag, den Sie in Schritt 4 erstellt haben. 
    
    ![Klicken Sie neben dem von Ihnen erstellten Importvorgang auf "Bereit für den Import in Microsoft 365".](../media/5760aac3-300b-4e31-b894-253c42a4b82b.png)
  
    Nun wird eine Flyout-Seite mit Informationen zu den PST-Dateien und anderen Informationen zur Importaufgabe angezeigt.
    
4. Klicken **Sie auf Importieren in Office 365**.
    
5. Die Seite **Ihre Daten filtern** wird angezeigt. Sie enthält die Datenerkenntnisse, die sich aus der Analyse ergeben haben, die Office 365 für die PST-Dateien ausgeführt hat, einschließlich Informationen über das Alter der Daten. An diesem Punkt haben Sie die Möglichkeit, die zu importierenden Daten zu filtern oder alle Daten ungeändert zu importieren. 
    
    ![Sie können die Daten in den PST-Dateien kürzen oder alles importieren](../media/287fc030-99e9-417b-ace7-f64617ea5d4e.png)
  
6. Führen Sie einen der folgenden Schritte aus:
    
    a. Um die Daten, die Sie importieren, zu trimmen, klicken Sie auf **Ja, ich möchte meine Daten vor dem Import filtern**.
    
    Detaillierte schrittweise Anweisungen zum Filtern der Daten in den PST-Dateien und anschließenden Starten des Importvorgangs finden Sie unter [Filtern von Daten beim Importieren von PST-Dateien in Office 365](filter-data-when-importing-pst-files.md).
    
    Oder
    
    b. Um alle Daten zu importieren, die sich in den PST-Dateien befinden, klicken Sie auf **Nein, ich möchte alles importieren**, und klicken Sie auf **Weiter**.
    
7. Wenn Sie sich entschieden haben, alle Daten zu importieren, klicken Sie auf **Daten importieren**, um den Importvorgang zu starten. 
    
    Der Status des Importauftrags wird auf der Seite **PST-Dateien importieren** angezeigt. Klicken Sie auf ![Aktualisieren-Symbol](../media/O365-MDM-Policy-RefreshIcon.gif) **Aktualisieren**, um die Statusinformationen zu aktualisieren, die in der Spalte **Status** angezeigt werden. Klicken Sie auf den Importauftrag, um die Status-Flyout-Seite anzuzeigen, auf der die Statusinformationen zu jeder zu importierenden PST-Datei angezeigt werden. Wenn der Import abgeschlossen ist, und die PST-Dateien in die Benutzerpostfächer importiert wurden, wird der Status in **Abgeschlossen** geändert.

## <a name="view-a-list-of-the-pst-files-uploaded-to-microsoft-365"></a>Anzeigen einer Liste der pst-Dateien, die in das Microsoft 365

Sie können das Microsoft Azure Storage-Explorer (ein kostenloses Open-Source-Tool) installieren und verwenden, um die Liste der PST-Dateien, die wir hochgeladen haben (von Mitarbeitern des Microsoft Rechenzentrums) in den Azure Storage-Bereich für Ihre Organisation zu sehen. So können Sie überprüfen, ob PST-Dateien von den festplatten, die Sie an Microsoft gesendet haben, erfolgreich in den Azure Storage wurden.
  
Der Microsoft Azure Storage-Explorer befindet sich in der Vorschau. 
  
 **Wichtig:** Sie können das Azure Storage-Explorer nicht zum Hochladen oder Ändern von PST-Dateien verwenden. Die einzige unterstützte Methode zum Importieren von PST-Dateien in Microsoft 365 ist die Verwendung von AzCopy. Außerdem können Sie keine PST-Dateien löschen, die Sie in das Azure-Blob hochgeladen haben. Wenn Sie versuchen, eine PST-Datei zu löschen, wird eine Fehlermeldung angezeigt, dass Sie nicht über die erforderlichen Berechtigungen verfügen. Alle PST-Dateien werden automatisch aus Ihrem Azure Storage gelöscht. Wenn keine Importaufträge ausgeführt werden, werden alle PST-Dateien im Container ** ingestiondata ** 30 Tage nach dem Erstellen des letzten Importauftrags gelöscht. 
  
So installieren Sie den Azure Storage-Explorer und Verbinden diesen mit Ihrem -Speicherbereich:
  
1. Führen Sie die folgenden Schritte aus, um die SAS-URL (Shared Access Signature) für Ihre Organisation zu erhalten. Diese URL ist eine Kombination aus der Netzwerk-URL für Azure Storage standort in der Microsoft-Cloud für Ihre Organisation und einem SAS-Schlüssel. Dieser Schlüssel bietet Ihnen die erforderlichen Berechtigungen für den Zugriff auf den Standort Azure Storage Organisation.
    
1. Navigieren Sie zu [https://protection.office.com/](https://protection.office.com/), und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Organisation an. 
    
2. Klicken Sie im linken Bereich des Security & Compliance Center auf **Information Governance > Import > Importieren von PST-Dateien**.
    
3. Klicken Sie auf der Seite **Import von PST-Dateien** ![Symbol hinzufügen](../media/ITPro-EAC-AddIcon.gif) **Neuer Importauftrag**.
    
4. Geben Sie im Assistenten für den Importauftrag einen Namen für den PST-Importauftrag ein, und klicken Sie dann auf **Weiter**. Verwenden Sie Kleinbuchstaben, Zahlen, Bindestriche und Unterstriche. Sie dürfen weder Großbuchstaben noch Leerzeichen in dem Namen verwenden.
    
5. Klicken Sie auf der Seite **Auftragstyp** importieren auswählen **auf Hochladen** Und klicken Sie dann auf **Weiter**.
    
6. Klicken Sie in Schritt 2 auf **SAS-URL für Netzwerkupload anzeigen**.
    
7. Nachdem die URL angezeigt wurde, kopieren Sie sie, und speichern Sie sie in einer Datei. Kopieren Sie unbedingt die gesamte URL.
    
    > [!IMPORTANT]
    > Achten Sie darauf, dass Sie entsprechende Vorsichtsmaßnahmen ergreifen, um die SAS-URL zu schützen. Dies kann von jedem Benutzer verwendet werden, um auf den Azure-Speicherbereich für Ihre Organisation zu zugreifen. 
  
8. Klicken **Sie auf Abbrechen,** um den Importauftrags-Assistenten zu schließen. 
    
2. Laden Sie das Tool [Microsoft Azure Storage-Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842) herunter, und installieren Sie es.
    
3. Starten Sie den Microsoft Azure Storage-Explorer, klicken Sie im linken Bereich mit der rechten Maustaste auf **Speicherkonten**, und klicken Sie dann auf **Mit Azure Storage verbinden**.
    
    ![Klicken Sie mit der rechten Maustaste auf "Speicherkonten", und klicken Sie dann auf "Mit Azure Storage verbinden".](../media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
4. Klicken Sie auf **SAS-URI (Shared Access Signature) oder -Verbindungszeichenfolge verwenden**, und klicken Sie dann auf **Weiter**.
    
5. Klicken **Sie auf SAS-URI verwenden,** fügen Sie die IN-URL, die Sie in Schritt 1 erhalten haben, in das Feld unter **URI** ein, und klicken Sie dann auf **Weiter**.
    
6. Auf der Seite **Verbindungszusammenfassung** können Sie die Verbindungsinformationen überprüfen und dann auf **Verbinden** klicken.
    
    Der **Container** ingestiondata wird geöffnet. Es enthält die PST-Dateien von Ihrer Festplatte. Der Container **ingestiondata** befindet sich unter **Speicherkonten** \> **(SAS-Attached Services)** \> **BLOB-Container**.
    
    ![Im Azure Storage-Explorer wird eine Liste der PST-Dateien angezeigt, die Sie hochgeladen haben.](../media/12376fed-13a5-4a09-8fe6-e819e011b334.png)
  
7. Wenn Sie mit der Verwendung des Microsoft Azure Storage-Explorers fertig sind, klicken Sie mit der rechten Maustaste auf **ingestiondata**, und klicken Sie dann auf **Trennen**, um die Verbindung mit dem Azure-Speicherbereich zu trennen. Andernfalls wird beim nächsten Anfügen eine Fehlermeldung angezeigt. 
    
    ![Klicken Sie mit der rechten Maustaste auf "ingestion", und klicken Sie dann auf "Trennen", um die Verbindung von Ihrem Azure-Speicherbereich zu trennen.](../media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)

## <a name="troubleshooting-tips"></a>Tipps zur Problembehandlung

- **Was geschieht, wenn der Importauftrag aufgrund von Fehlern in der PST-Import-CSV-Zuordnungsdatei fehlschlägt?** Wenn ein Importauftrag aufgrund von Fehlern in der Zuordnungsdatei fehlschlägt, müssen Sie die Festplatte nicht erneut an Microsoft senden, um einen Importauftrag zu erstellen. Der Grund dafür ist, dass die PST-Dateien von der Festplatte, die Sie für den Importauftrag zum Laufwerkversand übermittelt haben, bereits in den Azure Storage für Ihre Organisation hochgeladen wurden. In diesem Fall müssen Sie nur die Fehler in der PST-Import-CSV-Zuordnungsdatei beheben und dann einen neuen Importauftrag "Netzwerkupload" erstellen und die überarbeitete CSV-Zuordnungsdatei übermitteln. Informationen zum Erstellen und Starten eines neuen Netzwerkuploadimportauftrags finden Sie unter [Schritt 5:](use-network-upload-to-import-pst-files.md#step-5-create-a-pst-import-job) Erstellen eines PST-Importauftrags in Microsoft 365 und [Schritt 6:](use-network-upload-to-import-pst-files.md#step-6-filter-data-and-start-the-pst-import-job) Filtern von Daten und Starten des Auftrags für den PST-Import im Thema "Verwenden des Netzwerkuploads zum Importieren von PST-Dateien in Office 365". 
    
    > [!NOTE]
    > Verwenden Sie das [Tool Azure Storage-Explorer](#view-a-list-of-the-pst-files-uploaded-to-microsoft-365) zum Anzeigen der Ordnerstruktur im Container "Ingestiondata" für die PST-Dateien von Ihrer Festplatte, die in den Azure-Speicherbereich hochgeladen wurden, um Sie bei der Problembehandlung bei der PST-Import-CSV-Zuordnungsdatei zu unterstützen.  Zuordnungsdateifehler werden in der Regel durch einen falschen Wert im Parameter FilePath verursacht. Dieser Parameter gibt den Speicherort einer PST-Datei im Azure-Speicherbereich an. Weitere Informationen finden Sie in der Beschreibung des FilePath-Parameters in Tabelle in [Schritt 3](#step-3-create-the-pst-import-mapping-file). Wie bereits erläutert, wurde der Speicherort von PST-Dateien im Azure-Speicherbereich durch den Parameter angegeben, als Sie das Tool WAImportExport.exe Schritt 2 ausgeführt `/dstdir:` [haben.](#step-2-copy-the-pst-files-to-the-hard-drive) 
  
## <a name="more-information"></a>Weitere Informationen

- Der Laufwerkversand ist eine effektive Möglichkeit, große Mengen von Archivnachrichtendaten in Microsoft 365 zu importieren, um die Compliancefeatures zu nutzen, die In Ihrer Organisation zur Verfügung stehen. Nachdem Archivdaten in Benutzerpostfächer importiert wurden, können Sie:
    
  - Aktivieren [Sie Archivpostfächer und](enable-archive-mailboxes.md) automatisch [erweiternde Archivierung,](enable-unlimited-archiving.md) um Benutzern mehr Speicherplatz für die Daten zu bieten. 
    
  - Platzieren Sie Postfächer im [Prozesssicherungsverfahren,](./create-a-litigation-hold.md) um die Daten zu speichern. 
    
  - Verwenden Sie Microsoft [eDiscovery-Tools,](search-for-content.md) um die Daten zu durchsuchen. 
    
  - Wenden [Microsoft 365 Aufbewahrungsrichtlinien](retention.md) an, um zu steuern, wie lange die Daten aufbewahrt werden und welche Maßnahmen nach Ablauf des Aufbewahrungszeitraums zu ergreifen sind. 
    
  - Durchsuchen Sie [das Überwachungsprotokoll](search-the-audit-log-in-security-and-compliance.md) nach Ereignissen im Zusammenhang mit diesen Daten. 
    
  - Importieren Sie Daten [in inaktive Postfächer,](create-and-manage-inactive-mailboxes.md) um Daten zu Compliancezwecken zu archivieren. 
    
  - Schützen Sie Ihre Organisation [vor Datenverlusten](dlp-learn-about-dlp.md) vertraulicher Informationen. 
    
- Im Folgenden sehen Sie ein Beispiel für einen sicheren Speicherkontoschlüssel und einen BitLocker-Verschlüsselungsschlüssel. Dieses Beispiel enthält auch die Syntax für den Befehl „WAImportExport.exe“, den Sie zum Kopieren der PST-Dateien auf die Festplatte ausführen. Ergreifen Sie entsprechende Vorsichtsmaßnahmen, um diese so zu schützen, wie Sie Kennwörter oder andere Sicherheitsinformationen schützen würden.
    

    ```text
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

- Wie weiter oben erläutert, aktiviert der Office 365-Import-Dienst die Einstellung zum Anhalten der Aufbewahrungszeit (für eine unbestimmte Dauer), nachdem PST-Dateien in ein Postfach importiert wurden. Dies  *bedeutet, dass die Eigenschaft RentionHoldEnabled*  auf festgelegt ist, damit die dem Postfach zugewiesene  `True` Aufbewahrungsrichtlinie nicht verarbeitet wird. Dadurch erhält der Postfachbesitzer Zeit zum Verwalten der neu importierten Nachrichten, indem verhindert wird, dass eine Lösch- oder Archivrichtlinie ältere Nachrichten löscht oder archiviert. Hier sind einige Schritte, die Sie zum Verwalten des Anhaltens der Aufbewahrungszeit ausführen können: 
    
  - Nach einem bestimmten Zeitraum können Sie die Aufbewahrungsaufbewahrung deaktivieren, indem Sie den Befehl  `Set-Mailbox -RetentionHoldEnabled $false` ausführen. Entsprechende Anweisungen finden Sie unter [Anhalten der Aufbewahrungszeit für ein Postfach](/exchange/security-and-compliance/messaging-records-management/mailbox-retention-hold).
    
  - Sie können das Anhalten der Aufbewahrungszeit so konfigurieren, dass es an irgendeinem Datum in der Zukunft deaktiviert wird. Dazu wird der Befehl  `Set-Mailbox -EndDateForRetentionHold <date>` ausgeführt. Angenommen, das heutige Datum ist der 1. Juni 2016, und Sie möchten, dass die Aufbewahrungsaufbewahrung in 30 Tagen deaktiviert ist, führen Sie den folgenden Befehl aus:  `Set-Mailbox -EndDateForRetentionHold 7/1/2016` . In diesem Szenario würden Sie die *RentionHoldEnabled-Eigenschaft* auf *True festlegen.* Weitere Informationen finden Sie unter [Set-Mailbox](/powershell/module/exchange/set-mailbox).
    
  - Sie können die Einstellungen für die dem Postfach zugewiesene Aufbewahrungsrichtlinie ändern, damit ältere importierte Elemente nicht sofort gelöscht oder in das Archivpostfach des Benutzers verschoben werden. So könnten Sie beispielsweise die Aufbewahrungszeit bei einer Lösch- oder Archivrichtlinie, die dem Postfach zugewiesen wurde, verlängern. In diesem Szenario würden Sie das Anhalten der Aufbewahrungszeit für das Postfach deaktivieren, nachdem Sie die Einstellungen der Aufbewahrungsrichtlinie geändert haben. Weitere Informationen finden Sie unter [Einrichten einer Archivierungs- und Löschrichtlinie für Postfächer in Ihrer Organisation](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
    

