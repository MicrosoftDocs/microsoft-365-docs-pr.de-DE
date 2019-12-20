---
title: Verwenden des Netzwerk Uploads zum Importieren von RMS-verschlüsselten PST-Dateien in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 84a595b8-cd77-4f66-ac52-57a33ddd4773
description: Hier erfahren Sie, wie Sie mit dem Netzwerk Upload RMS-verschlüsselte PST-Dateien in Benutzerpostfächer in Office 365 importieren.
ms.openlocfilehash: 59aa489d6f4a3dd2545d5a2475f9e70e65529230
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802290"
---
# <a name="use-network-upload-to-import-rms-encrypted-pst-files-to-office-365"></a>Verwenden des Netzwerk Uploads zum Importieren von RMS-verschlüsselten PST-Dateien in Office 365

**Dieser Artikel richtet sich an Administratoren. Versuchen Sie, PST-Dateien in Ihr eigenes Postfach zu importieren? Siehe [Importieren von e-Mails, Kontakten und Kalendern aus einer Outlook. PST-Datei](https://go.microsoft.com/fwlink/p/?LinkID=785075)**
   
Verwenden Sie die Option "Netzwerk Upload" und den Office 365 Import-Dienst, um PST-Dateien in Benutzerpostfächer zu importieren. Netzwerkupload bedeutet, dass Sie die PST-Dateien in einen temporären Speicherbereich in der Microsoft-Cloud hochladen. Der Office 365-Importdienst kopiert die PST-Dateien dann aus dem Speicherbereich in die Postfächer der Zielbenutzer. Mit einem neuen Feature des Import Diensts können Sie Ihre PST-Dateien verschlüsseln, bevor Sie hochgeladen und in der Microsoft-Cloud gespeichert werden. Diese Dateien werden nicht verschlüsselt, wenn Sie in Benutzerpostfächer importiert werden. 
  
Hier sind die erforderlichen Schritte zum Verschlüsseln und Importieren von PST-Dateien in Office 365 Postfächer:
  
[Schritt 1: Einrichten von Azure Rights Management für PST-Import](#step-1-set-up-azure-rights-management-for-pst-import)

[Schritt 2: Generieren eines Verschlüsselungsschlüssels für den PST-Import](#step-2-generate-an-encryption-key-for-pst-import)

[Schritt 3: Abrufen der RMS-Mandanten-ID und der Lizenzierungs-URL](#step-3-obtain-rms-tenant-id-and-licensing-url)

[Schritt 4: Herunterladen der PST-Import Tools und Kopieren der SAS-URL](#step-4-download-the-pst-import-tools-and-copy-the-sas-url)

[Schritt 5: Verschlüsseln und Hochladen von PST-Dateien in Office 365](#step-5-encrypt-and-upload-your-pst-files-to-office-365)

[Optional Schritt 6: Anzeigen einer Liste der PST-Dateien, die in Office 365 hochgeladen wurden](#optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365)

[Schritt 7: Erstellen der PST-Import Zuordnungsdatei](#step-7-create-the-pst-import-mapping-file)

[Schritt 8: Erstellen eines PST-Import Auftrags in Office 365](#step-8-create-a-pst-import-job-in-office-365)
  
> [!IMPORTANT]
> Sie müssen Schritt 1 bis Schritt 4 nur einmal ausführen, um Ihre Organisation zum Verschlüsseln und Importieren von PST-Dateien in Office 365 Postfächer einzurichten und zu konfigurieren. Nachdem Sie diese Schritte ausgeführt haben, befolgen Sie Schritt 5 bis Schritt 8 jedes Mal, wenn Sie einen Batch von PST-Dateien verschlüsseln, hochladen und importieren möchten. 
  
Weitere Informationen zum Importieren von Daten in Office 365 finden Sie unter [Overview of Import your organization PST files to Office 365](importing-pst-files-to-office-365.md).
  
## <a name="before-you-begin"></a>Bevor Sie beginnen

- Ihnen muss die Rolle für den Postfachimport/-export in Exchange Online zugewiesen werden, damit Sie PST-Dateien in Office 365-Postfächer importieren können. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle „Postfachimport/-export“ zur Rollengruppe „Organisationsverwaltung“ hinzufügen. Or you can create a new role group, assign the Mailbox Import Export role, and then add yourself as a member. Weitere Informationen finden Sie im Abschnitt "Hinzufügen einer Rolle zu einer Rollengruppe" oder "Erstellen einer Rollengruppe" in [Verwalten von Rollengruppen](https://go.microsoft.com/fwlink/p/?LinkId=730688).
    
    Darüber hinaus muss eine der folgenden Bedingungen erfüllt sein, um Importaufträge im Security & Compliance Center erstellen zu können:
    
  - Ihnen muss in Exchange Online die Rolle „E-Mail-Empfänger“ zugewiesen sein. Standardmäßig wird diese Rolle den Rollengruppen "Organisationsverwaltung" und "Empfängerverwaltung" zugewiesen.
    
    Oder
    
  - Sie müssen ein globaler Administrator innerhalb Ihrer Office 365-Organisation sein.
    
  > [!TIP]
  > Erwägen Sie, in Exchange Online eine neue Rollengruppe speziell zum Importieren von PST-Dateien nach Office 365 zu erstellen. Legen Sie für die neue Rollengruppe als mindestens erforderliche Berechtigungen zum Importieren von PST-Dateien die Rollen "Postfachimport/-export" und "E-Mail-Empfänger" fest, und fügen Sie anschließend Mitglieder hinzu. 

- Große PST-Dateien können sich auf die Leistung des PST-Importvorgangs auswirken. Daher wird empfohlen, dass jede PST-Datei, die Sie in Schritt 2 in den Azure-Speicherort hochladen, nicht größer als 20 GB sein sollte.
  
- Sie müssen die PST-Dateien, die Sie in Office 365 importieren möchten, auf einem Dateiserver oder einem freigegebenen Ordner in Ihrer Organisation speichern. In Schritt 5 führen Sie das Office 365 ImportTool aus, mit dem die PST-Dateien, die auf diesem Dateiserver oder freigegebenen Ordner gespeichert sind, in Office 365 verschlüsselt und hochgeladen werden.
    
- Dieses Verfahren umfasst das Kopieren und Speichern einer Kopie eines Verschlüsselungsschlüssels, eines Speicher Schlüssels und einer Reihe von Identifikations Schlüsseln und URLs. Diese Informationen werden in Schritt 5 zum Verschlüsseln und Hochladen von PST-Dateien verwendet. Ergreifen Sie entsprechende Vorsichtsmaßnahmen, um diese so zu schützen, wie Sie Kennwörter oder andere Sicherheitsinformationen schützen würden. Sie können sie zum Beispiel in einem kennwortgeschützten Microsoft Word-Dokument oder auf einem verschlüsselten USB-Laufwerk speichern. Ein Beispiel für diese Schlüssel, IDs und URLs finden Sie im Abschnitt [Weitere Informationen](#more-information) . 
    
- Sie können PST-Dateien in ein inaktives Postfach in Office 365 importieren. Geben Sie hierzu den GUID des inaktiven Postfachs im Parameter `Mailbox` in der PST-Importzuordnungsdatei an. Weitere Informationen finden Sie in [Schritt 7](#step-7-create-the-pst-import-mapping-file) . 
    
- In einer Exchange-Hybridumgebung können Sie PST-Dateien für einen Benutzer, dessen primäres Postfach lokal gehostet wird, in ein cloudbasiertes Archivpostfach importieren. Gehen Sie hierzu in der PST-Importzuordnungsdatei folgendermaßen vor:
    
  - Geben Sie die E-Mail-Adresse des lokalen Postfachs des Benutzers im Parameter `Mailbox` an. 
    
  - Geben Sie den Wert **TRUE** im Parameter `IsArchive` an. 
    
    Weitere Informationen finden Sie in [Schritt 7](#step-7-create-the-pst-import-mapping-file) . 
    
- Nachdem PST-Dateien in ein Office 365-Postfach importiert wurden, wird die Einstellung zum Anhalten der Aufbewahrungszeit für das Postfach für eine unbestimmte Dauer aktiviert. Dies bedeutet: Die dem Postfach zugewiesene Aufbewahrungsrichtlinie wird erst verarbeitet, nachdem Sie das Anhalten der Aufbewahrungszeit deaktiviert oder aber ein Datum zum Deaktivieren des Anhaltens festgelegt haben. Warum tun wir dies? Wenn die in ein Postfach importierten Nachrichten alt sind, werden sie möglicherweise endgültig gelöscht, weil ihr Aufbewahrungszeitraum, basierend auf den für das Postfach konfigurierten Aufbewahrungseinstellungen, abgelaufen ist. Wenn Sie das Postfach in Aufbewahrungszeit halten, erhält der Postfachbesitzer Zeit, diese neu importierten Nachrichten zu verwalten, oder Sie erhalten Zeit, um die Aufbewahrungseinstellungen für das Postfach zu ändern. Im Abschnitt [Weitere Informationen](#more-information) finden Sie Vorschläge zum Verwalten des Aufbewahrungs Speichers. 
    
- Wenn Sie Ihre PST-Dateien nicht verschlüsseln müssen, bevor Sie Sie in Office 365 hochladen, lesen Sie [Verwenden des Netzwerk Uploads zum Importieren von PST-Dateien in Office 365](use-network-upload-to-import-pst-files.md).
    
- Häufig gestellte Fragen zur Verwendung des Netzwerk Uploads zum Importieren von PST-Dateien in Office 365 finden Sie unter [FAQ zum Importieren von PST-Dateien in Office 365](faqimporting-pst-files-to-office-365.md).
  
## <a name="step-1-set-up-azure-rights-management-for-pst-import"></a>Schritt 1: Einrichten von Azure Rights Management für PST-Import

Der PST-Import verwendet die Verschlüsselungsfunktionalität, die vom Azure Rights Management (Azure RMS)-Dienst in Office 365 bereitgestellt wird. Auf diese Weise können Sie PST-Dateien vor dem Hochladen in Office 365 verschlüsseln. 
  
Das Konfigurieren von Azure RMS für PST-Import besteht aus drei Schritten:
  
- [Aktivieren von Azure RMS](#activating-azure-rms)
    
- [Konfigurieren von RMS in Exchange Online](#configuring-rms-in-exchange-online)
    
- [Installieren des Active Directory RMS-Clients](#installing-the-active-directory-rms-client)
    
### <a name="activating-azure-rms"></a>Aktivieren von Azure RMS

Azure RMS ist standardmäßig deaktiviert, aber Sie oder ein anderer Administrator in Ihrer Organisation haben ihn möglicherweise aktiviert. Befolgen Sie die Anweisungen zum [Aktivieren von Azure Rights Management](https://docs.microsoft.com/azure/information-protection/deploy-use/activate-service) , um Azure DRM zu installieren und zu aktivieren.
  
### <a name="configuring-rms-in-exchange-online"></a>Konfigurieren von RMS in Exchange Online

Nachdem Sie den Rights Management-Dienst aktiviert haben, besteht der nächste Schritt darin, die Verwaltung von Informationsrechten (Information Rights Management, IRM) in Exchange Online für die Verwendung von Azure RMS einzurichten. Weitere Informationen finden Sie unter [Konfigurieren von IRM für die Verwendung von Azure Rights Management](https://go.microsoft.com/fwlink/p/?LinkId=394816).
  
1. Stellen [Sie mithilfe von Remote-PowerShell eine Verbindung zu Exchange Online her](https://go.microsoft.com/fwlink/p/?LinkId=396554 ).
    
2. Führen Sie den folgenden Befehl aus, um die RMS-Schlüssel Freigabe-URL festzulegen.
    
    ```powershell
    Set-IRMConfiguration -RMSOnlineKeySharingLocation <RMS key sharing location>
    ```

    Verwenden Sie die folgende Tabelle, um den richtigen RMS-Schlüssel Freigabespeicherort für den Standort Ihrer Organisation zu ermitteln.
    
    |**Location**|**RMS-Key-Sharing-Location**|
    |:-----|:-----|
    |Nordamerika  <br/> | `https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Europäische Union  <br/> | `https://sp-rms.eu.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Asien  <br/> | `https://sp-rms.ap.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Südamerika  <br/> | `https://sp-rms.sa.aadrm.com/TenantManagement/ServicePartner.svc` <br/> |
    |Office 365 für Behörden (Community-Cloud der US-Regierung)  <br/> | `https://sp-rms.govus.aadrm.com/TenantManagement/ServicePartner.svc`<sup>1</sup> <br/> |
   
    > [!NOTE]
    > <sup>1</sup> nur Kunden, die Office 365 für die Government-SKUs (Government Community Cloud) erworben haben, sollten diesen RMS-Schlüssel Freigabespeicherort verwenden. 
  
    Mit diesem Befehl wird beispielsweise der Speicherort der RMS-Online Schlüssel Freigabe in Exchange Online für einen Kunden in Nordamerika konfiguriert.
    
    ```powershell
    Set-IRMConfiguration -RMSOnlineKeySharingLocation "https://sp-rms.na.aadrm.com/TenantManagement/ServicePartner.svc"
    ```

3. Führen Sie den folgenden Befehl aus, um eine vertrauenswürdige Veröffentlichungsdomäne (Trusted Publishing Domain, TPD) von RMS Online in Ihre Office 365 Organisation zu importieren. 
    
    ```powershell
    Import-RMSTrustedPublishingDomain -RMSOnline -Name "RMS Online"
    ```

    Ein TPD enthält die Einstellungen, die für die Verwendung von RMS-Funktionen in Ihrer Organisation erforderlich sind, einschließlich der Verschlüsselung von PST-Dateien. 
    
4. Führen Sie den folgenden Befehl aus, um IRM für Ihre Office 365 Organisation zu aktivieren.
    
    ```powershell
    Set-IRMConfiguration -InternalLicensingEnabled $true
    ```

### <a name="installing-the-active-directory-rms-client"></a>Installieren des Active Directory RMS-Clients

Der letzte Schritt in diesem Abschnitt ist das Herunterladen des RMS-Clients (Rights Management Services, Rechteverwaltungsdienste) 2,1. Diese Software dient zum Schutz des Zugriffs auf Azure RMS und zum Schutz von Informationen, die über Anwendungen mit Azure RMS fließen. Installieren Sie den RMS-Client auf demselben Computer, den Sie zum Verschlüsseln und Hochladen von PST-Dateien in Schritt 5 verwenden werden. 
  
1. Download [Rights Management Service Client 2,1](https://www.microsoft.com/download/details.aspx?id=38396).
    
2. Führen Sie den Client 2,1-Assistenten für Active Directory Rights Management Service aus, um den Client zu installieren.

## <a name="step-2-generate-an-encryption-key-for-pst-import"></a>Schritt 2: Generieren eines Verschlüsselungsschlüssels für den PST-Import

Nachdem Sie Azure RMS eingerichtet haben, ist der nächste Schritt das Generieren eines Verschlüsselungsschlüssels (als symmetrischer Schlüssel bezeichnet), der zum Verschlüsseln der PST-Dateien verwendet wird, die Sie in Office 365 hochladen. Hierzu fügen Sie den PST-Import Dienst als Dienstprinzipal in Azure Active Directory hinzu. Durch das Hinzufügen dieser Anwendung als Dienstprinzipal kann der PST-Import Dienst sich direkt bei Azure Active Directory authentifizieren, wenn Sie in Schritt 5 verschlüsselte PST-Dateien an den Azure-Speicherort hochladen.
  
1. Starten Sie das Azure Active Directory-Modul für Windows PowerShell.
    
2. Führen Sie den folgenden Befehl aus, um eine Verbindung mit dem Microsoft Online-Dienst herzustellen.
    
    ```powershell
    Connect-MsolService
    ```

3. Geben Sie die Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation ein, und klicken Sie dann auf **OK**.
    
4. Führen Sie den folgenden Befehl aus, um einen Verschlüsselungsschlüssel zu generieren (einen symmetrischen Schlüssel aufrufen). Hierzu erstellen Sie einen neuen PST-Verschlüsselungs Prinzipal.
    
    ```powershell
    New-MsolServicePrincipal -DisplayName PstEncryptionPrincipal
    ```

    Das System zeigt den symmetrischen Schlüssel und die Eigenschaften für den neuen PST-Verschlüsselungs Prinzipal an.
    
    ![Kopieren und Speichern des angezeigten symmetrischen Schlüssels](media/0003fdea-dace-41d2-b49d-f5c98c6230ca.png)
  
5. Kopieren Sie den symmetrischen Schlüssel in eine Text-oder Word-Datei. Wie bereits erwähnt, müssen Sie Vorkehrungen treffen, um diese Datei zu schützen. Da dies der einzige Zeitpunkt ist, an dem der symmetrische Schlüssel angezeigt wird, können Sie auch in Betracht ziehen, einen Screenshot dieses Fensters zu erstellen und in derselben Datei zu speichern. 
    
    > [!IMPORTANT]
    > Nachdem Sie den PST-Verschlüsselungs Prinzipal erstellt haben, können Sie den symmetrischen Schlüssel nicht mithilfe des **Get-MsolServicePrincipal-** Cmdlets abrufen. Deshalb ist es wichtig, den Schlüssel zu speichern. 
  
Halten Sie das Azure Active Directory-Modul für Windows PowerShell geöffnet und mit dem Microsoft Online-Dienst verbunden. Im nächsten Schritt führen Sie in diesem Fenster einen Befehl aus.

## <a name="step-3-obtain-rms-tenant-id-and-licensing-url"></a>Schritt 3: Abrufen der RMS-Mandanten-ID und der Lizenzierungs-URL

Der nächste Schritt besteht darin, die Mandanten-ID und die URL für den Lizenzierungs Speicherort für den Azure RMS-Dienst für Ihre Organisation zu erhalten. Kopieren und speichern Sie diese Informationen in derselben Datei, die den symmetrischen Schlüssel aus Schritt 2 enthält. Die ID und die URL werden in Schritt 5 zum Verschlüsseln der PST-Dateien verwendet.
  
1. Führen Sie im Azure Active Directory-Modul für Windows PowerShell (das mit dem Microsoft Online-Dienst verbunden ist) den folgenden Befehl aus, um eine Verbindung mit dem Azure RMS-Dienst in Ihrer Office 365 Organisation herzustellen.
    
    ```powershell
    Connect-AadrmService 
    ```

2. Geben Sie die Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation ein, und klicken Sie dann auf **OK**.
    
3. Führen Sie den folgenden Befehl aus, um die Mandanten-ID für den Azure RMS-Dienst in Ihrer Office 365 Organisation anzuzeigen.
    
    ```powershell
    Get-AadrmConfiguration | FL BPOSId
    ```

    Kopieren Sie den Wert für die `BPOSId` Eigenschaft, und speichern Sie ihn. 
    
4. Führen Sie den folgenden Befehl aus, um den Lizenzierungs Speicherort für Ihren Azure RMS-Dienst anzuzeigen.
    
    ```powershell
    Get-AadrmConfiguration | FL LicensingIntranetDistributionPointUrl
    ```

    Kopieren Sie den Wert für die `LicensingIntranetDistributionPointUrl` Eigenschaft, und speichern Sie ihn. 

## <a name="step-4-download-the-pst-import-tools-and-copy-the-sas-url"></a>Schritt 4: Herunterladen der PST-Import Tools und Kopieren der SAS-URL

Nachdem Sie Azure RMS konfiguriert und die zum Verschlüsseln von PST-Dateien erforderlichen IDs erhalten haben, müssen Sie im nächsten Schritt die in Schritt 5 ausgeführten Tools herunterladen und installieren, um PST-Dateien in Office 365 zu verschlüsseln und hochzuladen. Diese Tools sind das Azure AzCopy-Tool und das Office 365 Daten Verschlüsselungstool. Außerdem kopieren Sie die SAS-URL für Ihre Organisation. Diese URL ist eine Kombination aus der Netzwerk-URL des Azure Storage-Speicherorts in der Microsoft-Cloud Ihrer Organisation und einem SAS-Schlüssel (Shared Access Signature). Mit diesem Schlüssel erhalten Sie die notwendigen Berechtigungen zum Hochladen von PST-Dateien an Ihren Azure Storage-Speicherort. Speichern Sie Sie in derselben Datei, in der Sie die anderen Informationen in Schritt 2 und Schritt 3 kopiert haben. Wie bereits erwähnt, sollten Sie Vorkehrungen treffen, um die SAS-URL zu schützen. 
  
> [!IMPORTANT]
> Sie müssen Azure AzCopy Version 5,0 verwenden, um PST-Dateien erfolgreich an den Azure-Speicherort hochzuladen. Neuere Versionen des AzCopy-Tools werden nicht für den Import von PST-Dateien in Office 365 unterstützt. Stellen Sie sicher, dass Sie das AzCopy-Tool von der Seite " **Dateien über das Netzwerk hochladen** " herunterladen, indem Sie die Verfahren in diesem Schritt befolgen. 
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich bei Office 365 mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation an.
    
3. Klicken Sie im linken Bereich auf Import- **PST-Dateien**für den Import von **Informationssteuerung** \> **importieren** \> .
    
4. Klicken Sie auf der Seite **PST-Dateien importieren** auf **zum Import Dienst wechseln**.
    
5. Klicken Sie auf der Seite **Daten in Office 365 importieren** auf **Neues Auftrags** ![hinzu](media/ITPro-EAC-AddIcon.gif)fügen-Symbol, und klicken Sie dann auf **e-Mail-Nachrichten hochladen (PST-Dateien)**.
    
6. Klicken Sie auf der Seite **Dateien über das Netzwerk hochladen** in Schritt 2 auf **Netzwerk Upload-SAS-URL anzeigen**.
    
7. Nachdem die URL angezeigt wurde, kopieren Sie Sie, und speichern Sie Sie in der Datei, in der Sie die anderen Schlüssel gespeichert haben. Achten Sie darauf, die gesamte URL zu kopieren. 
    
8. Klicken Sie in Schritt 3 auf **das Azure AzCopy-Tool herunterladen** , um das Azure AzCopy-Tool herunterzuladen und zu installieren. 
    
9. Klicken Sie im Popupfenster auf **Ausführen** , um das Azure AzCopy-Tool zu installieren. 
    
    > [!IMPORTANT]
    > Stellen Sie sicher, dass Sie das Azure AzCopy-Tool am Standardspeicherort `%ProgramFiles(x86)%\Microsoft SDKs\Azure\AzCopy` auf einem Computer mit 64-Bit-Windows installieren. Das liegt daran, dass beim Ausführen von "o365importtool. exe in Schritt 5 das AzCopy-Tool an diesem Speicherort gesucht wird. 
  
10. Nachdem Sie das Azure AzCopy-Tool installiert haben, klicken Sie auf **herunterladen des Tools Office 365 Datenverschlüsselung und-Import**.
    
11. **Klicken Sie** \> im Popupfenster auf Save **As** speichern unter, um die Datei "o365importtool. zip in einem Ordner auf Ihrem lokalen Computer zu speichern. 
    
12. Extrahieren Sie die Datei "o365importtool. zip.
    
13. Klicken Sie auf **Abbrechen** , um die Seite **Dateien über das Netzwerk hochladen** zu schließen. 
 
## <a name="step-5-encrypt-and-upload-your-pst-files-to-office-365"></a>Schritt 5: Verschlüsseln und Hochladen von PST-Dateien in Office 365

Nachdem Sie Schritt 1 bis Schritt 4 abgeschlossen haben, können Sie das Tool "o365importtool. exe zum Verschlüsseln und Hochladen von PST-Dateien in Office 365 verwenden. Dieses Tool verschlüsselt Ihre PST-Dateien und lädt diese dann hoch und speichert Sie an einem Azure-Speicherort in der Microsoft-Cloud. Damit Sie diesen Schritt ausführen können, müssen sich die PST-Dateien in einer Dateifreigabe oder auf einem Dateiserver in Ihrer Organisation befinden. Im folgenden Verfahren wird dies als das Quellverzeichnis bezeichnet. Jedes Mal, wenn Sie das Tool "o365importtool. exe ausführen, können Sie ein anderes Quellverzeichnis angeben. 

> [!NOTE]
> Wie bereits erwähnt, sollte jede PST-Datei, die Sie in den Azure-Speicherort hochladen, nicht größer als 20 GB sein. PST-Dateien mit einer Größe von mehr als 20 GB können sich auf die Leistung des PST-Importvorgangs auswirken, den Sie in Schritt 8 starten.
  
1. Öffnen Sie eine Eingabeaufforderung auf dem lokalen Computer.
    
2. Wechseln Sie zu dem Verzeichnis, in dem Sie das Tool "o365importtool. exe in Schritt 4 installiert haben.
    
3. Führen Sie den folgenden Befehl zum Verschlüsseln und Hochladen von PST-Dateien in Office 365 aus.
    
    ```powershell
    O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL> /upload-destSAS:<SAS key>
    ```

    In der folgenden Tabelle werden die Parameter und deren erforderliche Werte beschrieben. Die Informationen, die Sie in den vorherigen Schritten erhalten haben, werden in den Werten für diese Parameter verwendet.
    
    |**Parameter**|**Beschreibung**|**Beispiel**|
    |:-----|:-----|:-----|
    | `/srcdir:` <br/> |Gibt das Quellverzeichnis in Ihrer Organisation an, das die PST-Dateien enthält, die in Office 365 hochgeladen werden.  <br/> | `/srcdir:\\FILESERVER01\PSTs` <br/> |
    | `/protect-rmsserver:` <br/> |Gibt den Lizenzierungs Speicherort für Ihren Azure RMS-Dienst an. Verwenden Sie den Wert der `LicensingIntranetDistributionPointUrl` Eigenschaft, die Sie in Schritt 3 abgerufen haben. Stellen Sie sicher, dass Sie den Wert dieses Parameters mit doppelten Anführungszeichen ("") umgeben.  <br/> | `/protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing"` <br/> |
    | `/protect-tenantid:` <br/> |Gibt die Identität ihrer Azure RMS-Organisation an. Verwenden Sie den Wert der `BPOSId` Eigenschaft, die Sie in Schritt 3 abgerufen haben.  <br/> | `/protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b` <br/> |
    | `/protect-key:` <br/> |Gibt den symmetrischen Schlüssel an, den Sie in Schritt 2 erhalten haben. Beachten Sie, den Wert dieses Parameters in doppelte Anführungszeichen (" ") einzuschließen.  <br/> | `/protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867="` <br/> |
    | `/transfer:` <br/> |Gibt an, ob Sie PST-Dateien über das Netzwerk hochladen oder auf einer Festplatte versenden. Der Wert `upload` gibt an, dass Sie die Dateien über das Netzwerk hochladen. Der Wert `drive` gibt an, dass Sie den PST auf einer Festplatte verschicken.  <br/> | `/transfer:upload` <br/> |
    | `/upload-dest:` <br/> |Gibt das Ziel in Office 365 an, in dem Ihre PST-Dateien hochgeladen werden. Dies ist der Azure-Speicherort für Ihre Organisation. Der Wert für diesen Parameter besteht aus der Netzwerk-Upload-URL aus der SAS-URL, die Sie in Schritt 4 kopiert haben. Beachten Sie, den Wert dieses Parameters in doppelte Anführungszeichen (" ") einzuschließen.  <br/><br/> **Tipp:** (optional) Sie können einen Unterordner am Azure-Speicherort angeben, in den die verschlüsselten PST-Dateien hochgeladen werden sollen. Hierzu fügen Sie einen Unterordner Speicherort (nach "ingestiondata") in der Netzwerk-Upload-URL hinzu. Im ersten Beispiel wird kein Unterordner angegeben. Das bedeutet, dass das PST in den Stamm (namens *ingestiondata*) des Azure-Speicherorts hochgeladen wird. Das zweite Beispiel lädt die PST-Dateien in einen Unterordner (mit dem Namen *EncryptedPSTs*) am Azure-Speicherort hoch.           | `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata"` <br/> Oder  <br/>  `/upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs"` <br/> |
    | `/upload-destSAS:` <br/> |Gibt den SAS-Schlüssel für Ihre Organisation an. Der Wert für diesen Parameter besteht aus dem SAS-Schlüssel aus der SAS-URL, die Sie in Schritt 4 kopiert haben. Das erste Zeichen im SAS-Schlüssel ist ein Fragezeichen ("?"). Beachten Sie, den Wert dieses Parameters in doppelte Anführungszeichen (" ") einzuschließen.<br/><br/>**Hinweis:** Wenn Sie die SAS-URL in einem Skript oder einer Batchdatei verwenden, müssen Sie auf bestimmte Zeichen achten, die mit Escapezeichen versehen werden müssen. Beispielsweise müssen `%` Sie zu ändern `%%` und zu `&` `^&`ändern. | `/upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"` <br/> |
    | `/recurse` <br/> |Diese optionale Option gibt den rekursiven Modus an, sodass das Tool "o365importtool. exe PST-Dateien kopiert, die sich in Unterordnern im Quellverzeichnis befinden, das durch den `/srcdir:` -Parameter angegeben wird.  <br/><br/> **Hinweis:** Wenn Sie diesen Schalter einschließen, haben PST-Dateien in Unterordnern einen anderen Dateinamen am Azure Storage-Speicherort, nachdem sie hochgeladen wurden. Sie müssen den genauen Dateipfadname in der CSV-Datei angeben, die Sie in Schritt 7 erstellen.           | `/recurse` <br/> |
   
    Im folgenden finden Sie ein Beispiel für die Syntax für das Tool "o365importtool. exe unter Verwendung der tatsächlichen Werte für die einzelnen Parameter:
    
    ```powershell
    O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b  /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
    ```

    Nachdem Sie den Befehl ausgeführt haben, werden Statusmeldungen angezeigt, die den Fortschritt beim Verschlüsseln und Hochladen der PST-Dateien anzeigen. Eine abschließende Statusmeldung zeigt die Gesamtzahl der erfolgreich verschlüsselten und hochgeladenen Dateien an. 
    
    > [!TIP]
    > Nachdem Sie den Befehl "o365importtool. exe erfolgreich ausgeführt haben und sichergestellt haben, dass alle Parameter korrekt sind, speichern Sie eine Kopie der Befehlszeilensyntax in derselben (gesicherten) Datei, in der Sie die Informationen kopiert haben, die Sie in den vorherigen Schritten erhalten haben. Anschließend können Sie diesen Befehl jedes Mal kopieren und in eine Eingabeaufforderung einfügen, wenn Sie das Tool "o365importtool. exe zum Verschlüsseln und Hochladen von PST-Dateien in Office 365 ausführen möchten. Die einzigen Werte, die Sie möglicherweise ändern müssen, sind `/srcdir:` diejenigen `/upload-dest:` für die-und-Parameter. 
  
## <a name="optional-step-6-view-a-list-of-the-pst-files-uploaded-to-office-365"></a>Optional Schritt 6: Anzeigen einer Liste der PST-Dateien, die in Office 365 hochgeladen wurden

Als optionalen Schritt können Sie den Microsoft Azure Speicher-Explorer (ein kostenloses Open-Source-Tool) installieren und verwenden, um die Liste der PST-Dateien anzuzeigen, die Sie in das Azure-BLOB hochgeladen haben. Hierfür gibt es drei gute Gründe:
  
- Sie können sicherstellen, dass die PST-Dateien aus dem freigegebenen Ordner oder von dem Dateiserver in Ihrer Organisation erfolgreich in den Azure-Blob hochgeladen wurden.

- Stellen Sie sicher, dass die PST-Dateien verschlüsselt sind. Verschlüsselte PST- `.pfile` Dateien haben eine Erweiterung an den PST-Dateinamen angehängt; Beispiel: `pilarp.pst.pfile`.
    
- Sie können den Dateinamen (und den Pfadnamen des Unterordners, sofern eingeschlossen) für jede PST-Datei prüfen, die in den Azure-Blob hochgeladen wurde. Dies ist hilfreich, wenn Sie die PST-Zuordnungsdatei im nächsten Schritt erstellen, da Sie sowohl den Pfadnamen des Ordners als auch den Dateinamen für jede PST-Datei angeben müssen. Durch Überprüfen dieser Namen können mögliche Fehler in der PST-Zuordnungsdatei verhindert werden.
    
Der Microsoft Azure Storage-Explorer befindet sich in der Vorschau.  
  
 > [!IMPORTANT]
>  Sie können den Azure Storage-Explorer nicht verwenden, um PST-Dateien hochzuladen oder zu ändern. Die einzige unterstützte Methode zum Importieren von PST-Dateien nach Office 365 besteht in der Verwendung von AzCopy. Außerdem können Sie keine PST-Dateien löschen, die Sie in das Azure-Blob hochgeladen haben. Wenn Sie versuchen, eine PST-Datei zu löschen, wird eine Fehlermeldung angezeigt, in der Sie darauf hingewiesen werden, dass Sie nicht über die erforderlichen Berechtigungen verfügen. Beachten Sie, die alle PST-Dateien automatisch aus dem Azure-Speicherbereich gelöscht werden. Wenn keine Importaufträge in Bearbeitung sind, werden alle PST-Dateien im Container **Erfassungsdaten** 30 Tage nach Erstellung des letzten Importauftrags gelöscht. 
  
So installieren Sie den Azure Storage-Explorer und Verbinden diesen mit Ihrem -Speicherbereich:
  
1. Laden Sie das Tool [Microsoft Azure Storage-Explorer](https://go.microsoft.com/fwlink/p/?LinkId=544842) herunter, und installieren Sie es.
    
2. Starten Sie den Microsoft Azure Storage-Explorer, klicken Sie im linken Bereich mit der rechten Maustaste auf **Speicherkonten**, und klicken Sie dann auf **Mit Azure Storage verbinden**. 
    
    ![Klicken Sie mit der rechten Maustaste auf "Speicherkonten", und klicken Sie dann auf "Mit Azure Storage verbinden".](media/75b80cc3-c336-4f96-ad32-54ac9b96a7af.png)
  
3. Fügen Sie in das Feld unter **Verbindung mit Azure-Speicher verbinden**die SAS-URL ein, die Sie in Schritt 4 erhalten haben, und klicken Sie dann auf **weiter**. 
    
    ![Fügen Sie die SAS-URL in das Feld auf der Seite Connect to Azure Storage ein.](media/5d034128-e087-48e1-9ebc-4c9fa262d5b7.png)
  
4. Auf der Seite **Verbindungszusammenfassung** können Sie die Verbindungsinformationen überprüfen und dann auf **Verbinden** klicken. 
    
5. Erweitern Sie unter **Speicherkonten**den Knoten **(Service SAS)** , und erweitern Sie dann den Knoten **BLOB-Container** . 
    
6. Klicken Sie mit der rechten Maustaste auf **ingestiondata**, und klicken Sie dann auf **BLOB-Container-Editor öffnen**.
    
    ![Klicken Sie mit der rechten Maustaste auf ingestiondata, und klicken Sie dann auf BLOB-Container Editor öffnen](media/f50eee30-9202-4efc-904a-2895a0bc388d.png)
  
    Der Azure-Speicherbereich mit einer Liste der PST-Dateien, die Sie in Schritt 5 hochgeladen haben, wird angezeigt.
    
    ![Im Azure Storage-Explorer wird eine Liste der PST-Dateien angezeigt, die Sie hochgeladen haben.](media/a448ae43-e744-4153-8304-22b59e93883c.png)
  
7. Wenn Sie mit der Verwendung des Microsoft Azure Storage-Explorers fertig sind, klicken Sie mit der rechten Maustaste auf **ingestiondata**, und klicken Sie dann auf **Trennen**, um die Verbindung mit dem Azure-Speicherbereich zu trennen. Andernfalls wird beim nächsten Anfügen eine Fehlermeldung angezeigt. 
    
    ![Klicken Sie mit der rechten Maustaste auf "ingestion", und klicken Sie dann auf "Trennen", um die Verbindung von Ihrem Azure-Speicherbereich zu trennen.](media/1e8e5e95-4215-4ce4-a13d-ab5f826a0510.png)
  
## <a name="step-7-create-the-pst-import-mapping-file"></a>Schritt 7: Erstellen der PST-Import Zuordnungsdatei

Nachdem die PST-Dateien verschlüsselt und in den Azure-Speicherort für Ihre Office 365 Organisation hochgeladen wurden, besteht der nächste Schritt darin, eine CSV-Datei (Comma-Separated Value) zu erstellen, in der die Benutzerpostfächer angegeben werden, in die die PST-Dateien importiert werden. Diese CSV-Datei wird im nächsten Schritt übermittelt, wenn Sie einen PST-Importauftrag erstellen.
  
1. [Laden Sie eine Kopie der PST-Importzuordnungsdatei herunter](https://go.microsoft.com/fwlink/p/?LinkId=544717). 
    
2. Öffnen oder speichern Sie die CSV-Datei auf Ihrem lokalen Computer. Das folgende Beispiel zeigt eine abgeschlossene PST-Importzuordnungsdatei (in Editor geöffnet). Es ist wesentlich einfacher, Microsoft Excel zum Bearbeiten der CSV-Datei zu verwenden.
    
    ```text
    Workload,FilePath,Name,Mailbox,IsArchive,TargetRootFolder,ContentCodePage,SPFileContainer,SPManifestContainer,SPSiteUrl
    Exchange,,annb.pst.pfile,annb@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,annb_archive.pst.pfile,annb@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,,donh.pst.pfile,donh@contoso.onmicrosoft.com,FALSE,/,,,,
    Exchange,,donh_archive.pst.pfile,donh@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,pilarp.pst.pfile,pilarp@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,pilarp_archive.pst.pfile,pilarp@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,tonyk.pst.pfile,tonyk@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,tonyk_archive.pst.pfile,tonyk@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    Exchange,EncryptedPSTs,zrinkam.pst.pfile,zrinkam@contoso.onmicrosoft.com,FALSE,,,,,
    Exchange,EncryptedPSTs,zrinkam_archive.pst.pfile,zrinkam@contoso.onmicrosoft.com,TRUE,/ImportedPst,,,,
    ```

    Die erste Zeile oder Kopfzeile der CSV-Datei enthält die Parameter, die vom PST-Importdienst verwendet werden, um die PST-Dateien in Benutzerpostfächer zu importieren. Die einzelnen Parameternamen werden jeweils durch ein Komma getrennt. Jede Zeile unter der Kopfzeile stellt die Parameterwerte für das Importieren einer PST-Datei in ein bestimmtes Postfach dar. Sie benötigen eine Zeile für jede PST-Datei, die in ein Benutzerpostfach importiert werden soll. Vergessen Sie nicht, die Platzhalterdaten in der Zuordnungsdatei durch die tatsächlichen Werte zu ersetzen.
    
    > [!NOTE]
    > Ändern Sie nichts in der Kopfzeile, einschließlich der SharePoint-Parameter; diese werden während des PST-Importvorgangs ignoriert. 
  
3. Verwenden Sie die Informationen in der folgenden Tabelle, um die CSV-Datei mit den erforderlichen Informationen zu füllen.
    
    |**Parameter**|**Beschreibung**|**Beispiel**|
    |:-----|:-----|:-----|
    | `Workload` <br/> |Gibt den Office 365-Dienst an, in den Daten importiert werden. Verwenden Sie `Exchange`, um PST-Dateien in Benutzerpostfächer zu importieren.  <br/> | `Exchange` <br/> |
    | `FilePath` <br/> |Gibt den Speicherort des Ordners am Azure-Speicherort an, an den Sie die PST-Dateien in Schritt 5 hochgeladen haben.  <br/>  Wenn Sie keinen optionalen Unterordnernamen in die Netzwerk-URL in den `/upload-dest:` Parameter in Schritt 5 aufgenommen haben, lassen Sie diesen Parameter in der CSV-Datei leer. Wenn Sie einen Unterordnernamen angegeben haben, geben Sie ihn in diesem Parameter an. Beim Wert für diesen Parameter muss die Groß-/Kleinschreibung beachtet werden. In beiden Fällen schließen Sie "ingestiondata" *nicht* in den Wert für den Parameter `FilePath` ein.  <br/> <br/>**Wichtig:** Der Fall für den Dateipfadname muss derselbe Fall sein, den Sie verwendet haben, wenn Sie einen optionalen Unterordnernamen in die SAS-URL `/upload-dest:` des Parameters in Schritt 5 aufgenommen haben. Wenn Sie beispielsweise den Namen `EncryptedPSTs` des Unterordners in Schritt 5 verwendet haben und dann `encryptedpsts` im Parameter `FilePath` in der CSV-Datei verwenden, tritt beim Import für die PST-Datei ein Fehler auf. Denken Sie deshalb daran, in beiden Fällen dieselbe Groß-/Kleinschreibung zu verwenden.           |(leer lassen)  <br/> Oder  <br/>  `EncryptedPSTs` <br/> |
    | `Name` <br/> |Gibt den Namen der PST-Datei an, die in das Benutzerpostfach importiert wird. Beim Wert für diesen Parameter muss die Groß-/Kleinschreibung beachtet werden. Da die PST-Dateien, die in den Azure-Speicherort hochgeladen werden, `.pfile` verschlüsselt sind, wird dem PST-Dateinamen eine Erweiterung hinzugefügt. Sie müssen die `.pfile` Erweiterung dem Namen der PST-Dateien in der CSV-Datei hinzufügen.  <br/><br/> **Wichtig:** Der Fall für den Namen der PST-Datei in der CSV-Datei muss mit der PST-Datei identisch sein, die in Schritt 5 in den Azure-Speicherort hochgeladen wurde. Wenn Sie beispielsweise `annb.pst.pfile` im Parameter `Name` der CSV-Datei verwenden, der Name der tatsächlichen PST-Datei aber `AnnB.pst` lautet, schlägt der Import für diese PST-Datei fehl. Sorgen Sie deshalb dafür, dass im Namen der PST-Datei in der CSV-Datei dieselbe Groß-/Kleinschreibung wie in der tatsächlichen PST-Datei verwendet wird.           | `annb.pst.pfile` <br/> |
    | `Mailbox` <br/> |Gibt die E-Mail-Adresse des Postfachs an, in das die PST-Datei importiert werden soll.  <br/> Zum Importieren einer PST-Datei in ein inaktives Postfach müssen Sie für diesen Parameter die Postfach-GUID angeben. Zum Abrufen dieser GUID führen Sie den folgenden PowerShell-Befehl in Exchange Online aus: `Get-Mailbox -InactiveMailboxOnly <identity of inactive mailbox> | FL Guid`. <br/><br/> **Hinweis:** In einigen Fällen verfügen Sie möglicherweise über mehrere Postfächer mit derselben e-Mail-Adresse, wobei ein Postfach ein aktives Postfach ist und sich das andere Postfach in einem weichen-gelöschten (oder inaktiven) Status befindet. In diesen Fällen müssen Sie die Postfach-GUID angeben, um das Postfach eindeutig zu identifizieren, in das die PST-Datei importiert werden soll. Zum Abrufen dieser GUID für aktive Postfächer führen Sie den folgenden PowerShell-Befehl aus: `Get-Mailbox - <identity of active mailbox> | FL Guid`. Um die GUID für vorläufig gelöschte (oder inaktive) Postfächer zu erhalten, führen Sie diesen Befehl aus.`Get-Mailbox - <identity of soft-deleted or inactive mailbox> -SoftDeletedMailbox | FL Guid`           | `annb@contoso.onmicrosoft.com` <br/> Oder  <br/>  `2d7a87fe-d6a2-40cc-8aff-1ebea80d4ae7` <br/> |
    | `IsArchive` <br/> | Gibt an, ob die PST-Datei in das Archivpostfach des Benutzers importiert werden soll. Es gibt zwei Möglichkeiten:  <br/> **False** Importiert die PST-Datei in das primäre Postfach des Benutzers.  <br/> **True** Importiert die PST-Datei in das Archivpostfach des Benutzers.  <br/>  Wenn Sie diesen Parameter leer lassen, wird die PST-Datei in das primäre Postfach des Benutzers importiert.  <br/><br/> **Hinweis:** Wenn Sie eine PST-Datei in ein Cloud-basiertes Archivpostfach für einen Benutzer importieren möchten, dessen primäres Postfach lokal ist, geben Sie **true** für diesen Parameter an, und geben Sie die e-Mail-Adresse `Mailbox` für das lokale Postfach des Benutzers für den Parameter an.           | `FALSE` <br/> Oder  <br/>  `TRUE` <br/> |
    | `TargetRootFolder` <br/> | Gibt den Postfachordner an, in den die PST-Datei importiert wird.  <br/>  Wenn Sie diesen Parameter leer lassen, wird die PST-Datei in einen neuen Ordner mit dem Namen " **imported** " importiert, der sich auf der Stammebene des Postfachs befindet (die gleiche Ebene wie der Posteingangsordner und die anderen standardmäßigen Postfachordner).  <br/>  Wenn Sie angeben `/`, werden Elemente in der PST-Datei direkt in den Posteingangsordner des Benutzers importiert.  <br/>  Wenn Sie angeben `/<foldername>`, werden Elemente in der PST-Datei in einen Unterordner mit dem Namen * \<FolderName\> * importiert. Wenn Sie beispielsweise verwendet `/ImportedPst`haben, werden Elemente in einen Unterordner mit dem Namen **ImportedPst**importiert. Dieser Unterordner befindet sich im Posteingangsordner des Benutzers.  <br/><br/> **Tipp:** Sie sollten einige Test Batches durchführen, um mit diesem Parameter zu experimentieren, damit Sie den Speicherort für den besten Ordner zum Importieren von PST-Dateien ermitteln können.           |(leer lassen)  <br/> Oder  <br/>  `/` <br/> Oder  <br/>  `/ImportedPst` <br/> |
    | `ContentCodePage` <br/> |Dieser optionale Parameter gibt einen numerischen Wert für die Codepage an, die zum Importieren von PST-Dateien im ANSI-Dateiformat verwendet werden muss. Der Parameter wird zum Importieren von PST-Dateien aus chinesischen, japanischen und koreanischen (CJK) Organisationen verwendet, weil in diesen Sprachen normalerweise ein Doppelbyte-Zeichensatz (double byte character set, DBCS) verwendet wird. Wenn dieser Parameter nicht verwendet wird, um PST-Dateien für Sprachen zu importieren, die DBCS für die Namen von Postfachordnern verwenden, sind die Ordnernamen nach dem Import oft nicht leserlich. Eine Liste von unterstützten Werten, die für diesen Parameter verwendet werden müssen, finden Sie unter [CodePage-Bezeichner](https://go.microsoft.com/fwlink/p/?LinkId=328514).  <br/><br/> **Hinweis:** Wie vorstehend erwähnt, ist dies ein optionaler Parameter, den Sie in die CSV-Datei nicht einschließen müssen. Sie können ihn aber auch einschließen und den Wert für eine oder mehrere Zeilen leer lassen.           |(leer lassen)  <br/> Oder  <br/>  `932` (dies ist der Codepagebezeichner für ANSI/OEM – Japanisch)  <br/> |
    | `SPFileContainer` <br/> |Lassen Sie diesen Parameter für den PST-Import leer.  <br/> |Nicht zutreffend  <br/> |
    | `SPManifestContainer` <br/> |Lassen Sie diesen Parameter für den PST-Import leer.  <br/> |Nicht zutreffend  <br/> |
    | `SPSiteUrl` <br/> |Lassen Sie diesen Parameter für den PST-Import leer.  <br/> |Nicht zutreffend  <br/> |
  
## <a name="step-8-create-a-pst-import-job-in-office-365"></a>Schritt 8: Erstellen eines PST-Import Auftrags in Office 365

Der letzte Schritt besteht darin, den PST-Importauftrag im Import Dienst in Office 365 zu erstellen. Wie bereits erläutert, übermitteln Sie die PST-Import Zuordnungsdatei, die Sie in Schritt 7 erstellt haben. Nachdem Sie den neuen Auftrag erstellt haben, verwendet der Import Dienst die Informationen in der Zuordnungsdatei, um die Verschlüsselung aufzugeben und die PST-Dateien (die Sie in Office 365 in Schritt 5 hochgeladen haben) in das angegebene Benutzerpostfach zu importieren. 
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich bei Office 365 mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Office 365 Organisation an.
    
3. Klicken Sie im linken Bereich auf **Informationssteuerung #a0 Import #a1 PST-Dateien importieren**.
    
4. Klicken Sie auf der Seite **PST-Dateien importieren** auf **zum Import Dienst wechseln**.
    
5. Klicken Sie auf der Seite **Daten in Office 365 importieren** auf **Neues Auftrags**![hinzu](media/ITPro-EAC-AddIcon.gif)fügen-Symbol, und klicken Sie dann auf **e-Mail-Nachrichten hochladen (PST-Dateien)**.
    
6. Klicken Sie auf der Seite **Dateien über das Netzwerk hochladen** auf die Kontrollkästchen **Ich bin fertig, meine Dateien hochzuladen** , und **Ich habe Zugriff auf die Zuordnungsdatei** , und klicken Sie dann auf **weiter**. 
    
7. Geben Sie einen Namen für den PST-Importauftrag an, und klicken Sie dann auf **Weiter**.
    
8. Klicken Sie auf Add](media/ITPro-EAC-AddIcon.gif) -Symbol **Hinzufügen** ![, um die PST-Zuordnungsdatei auszuwählen, die Sie in Schritt 7 erstellt haben. 
    
9. Nachdem der Name der CSV-Datei in der Liste angezeigt wird, wählen Sie ihn aus, und klicken Sie dann auf **überprüfen, um die** CSV-Datei auf Fehler zu überprüfen. 
    
    > [!NOTE]
    > Wie bereits erläutert, wird beim Verschlüsseln der PST- `.pfile` Dateien eine Erweiterung an den PST-Dateinamen angehängt. Sie müssen die `.pfile` Erweiterung dem Namen der PST-Dateien in der CSV-Datei hinzufügen. Wenn dies nicht der Fall ist, schlägt die Überprüfung der CSV-Datei fehl. 
  
    Die CSV-Datei muss erfolgreich überprüft werden, um einen PST-Importauftrag zu erstellen. Wenn die Überprüfung fehlschlägt, klicken Sie in der Spalte **Status** auf den Link **ungültig** . Eine Kopie der PST-Import Zuordnungsdatei wird geöffnet, wobei für jede Zeile in der Datei, die nicht erfolgreich war, eine Fehlermeldung angezeigt wird. 
    
10. Wenn die PST-Zuordnungsdatei erfolgreich überprüft wurde, lesen Sie das Dokument mit den allgemeinen Geschäftsbedingungen, und klicken Sie dann auf das Kontrollkästchen.
    
11. Klicken Sie auf **Fertig stellen** , um den Auftrag zu senden. 
    
    Der Auftrag wird in der Liste der PST-Importaufträge auf der Seite **Daten in Office 365 importieren** angezeigt. 
    
12. Wählen Sie den Auftrag aus, **und klicken Sie**![auf Aktualisierungssymbol](media/O365-MDM-Policy-RefreshIcon.gif) aktualisieren, um die Statusinformationen zu aktualisieren, die im Detailbereich angezeigt werden. 
    
13. Klicken Sie im Detailbereich auf **Details anzeigen** , um den aktuellen Status für den ausgewählten Auftrag abzurufen. 
 
## <a name="more-information"></a>Weitere Informationen

- Warum PST-Dateien in Office 365 importieren?
    
  - Es ist eine gute Möglichkeit, die e-Mail-Adresse Ihrer Organisation in Office 365 zu migrieren.
    
  - Es hilft Ihnen, die Anforderungen Ihrer Organisation an die Compliance zu adressieren, indem Sie Folgendes zulassen:
    
  - Aktivieren der Archivierung von Postfächern, um Benutzern zusätzlichen Speicherplatz im Postfach bereitzustellen.
    
  - Aufbewahrung von Postfächern, um Inhalte beizubehalten.
    
  - Verwenden Sie Microsoft eDiscovery-Tools, um nach Inhalten in Postfächern zu suchen.
    
  - Verwenden Sie Aufbewahrungsrichtlinien, um zu steuern, wie lange Postfachinhalt aufbewahrt wird.
    
  - Durchsuchen Sie das Office 365 Überwachungsprotokoll nach Post fachbezogenen Ereignissen.
    
  - Sie schützt vor Datenverlust. PST-Dateien, die in Office 365 Postfächer importiert werden, erben die Hochverfügbarkeitsfeatures von Exchange Online, im Gegensatz zum Speichern der Daten auf dem Computer eines Benutzers.
    
  - Die Daten sind für den Benutzer auf allen Geräten verfügbar, da sie in der Cloud gespeichert sind.
    
- Im folgenden finden Sie ein Beispiel für die Schlüssel, IDs und URLs, die in den Schritten 2, 3 und 4 abgerufen werden. Dieses Beispiel enthält auch die Syntax für den Befehl, den Sie im Tool "o365importtool. exe ausführen, um PST-Dateien in Office 365 zu verschlüsseln und hochzuladen. Ergreifen Sie entsprechende Vorsichtsmaßnahmen, um diese so zu schützen, wie Sie Kennwörter oder andere Sicherheitsinformationen schützen würden.
    
  ```text
  Symmetric key: l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=

  BPOSId: 42745b33-2a5c-4726-8a2a-ca43caa0f74b

  LicensingIntranetDistributionPointUrl (RMS licensing location): https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing
  
  SAS URL: https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D
  
  O365ImportTool.exe /srcdir:<Location of PST files> /protect-rmsserver:<RMS licensing location> /protect-tenantid:<BPOSId> /protect-key:<Symmetric key> /transfer:upload /upload-dest:<Network upload URL from the SAS URL> /upload-destSAS:<SAS key from the SAS URL>
  
  EXAMPLES
  
  This example uploads PST files to the root of the Azure storage location:

  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  
  This example uploads PST files to a subfolder named EncryptedPSTs  in the Azure storage location:
  
  O365ImportTool.exe /srcdir:\\FILESERVER01\PSTs /protect-rmsserver:"https://afcbd8ec-cb2b-4a1a-8246-0b4bc22d1978.rms.na.aadrm.com/_wmcs/licensing" /protect-tenantid:42745b33-2a5c-4726-8a2a-ca43caa0f74b /protect-ownerid:45beb445-4d06-47df-8e61-6ca1a88a080e /protect-key:"l+R+Umc5RGmSBh1oW+DoyMxm/h5h2JJXFcNOFiNp867=" /transfer:upload /upload-dest:"https://3c3e5952a2764023ad14984.blob.core.windows.net/ingestiondata/EncryptedPSTs" /upload-destSAS:"?sv=2012-02-12&amp;se=9999-12-31T23%3A59%3A59Z&amp;sr=c&amp;si=IngestionSasForAzCopy201601121920498117&amp;sig=Vt5S4hVzlzMcBkuH8bH711atBffdrOS72TlV1mNdORg%3D"
  ```

- Wie bereits erläutert, aktiviert der Office 365-Import Dienst die Einstellung Aufbewahrungsdauer (für unbestimmte Zeit), nachdem PST-Dateien in ein Postfach importiert wurden. Dies bedeutet, dass die *RentionHoldEnabled* -Eigenschaft `True` so festgelegt ist, dass die dem Postfach zugewiesene Aufbewahrungsrichtlinie nicht verarbeitet wird. Dadurch erhält der Postfachbesitzer die Zeit, die neu importierten Nachrichten zu verwalten, indem verhindert wird, dass eine Löschung oder Archivrichtlinie ältere Nachrichten löscht oder archiviert. Hier sind einige Schritte, die Sie zum Verwalten dieser Aufbewahrungszeit durchführen können: 
    
  - Nach einem bestimmten Zeitraum können Sie die Aufbewahrungszeit deaktivieren, indem Sie den `Set-Mailbox -RetentionHoldEnabled $false` Befehl ausführen. Anweisungen finden Sie unter [platzieren eines Postfachs in der Aufbewahrungs](https://go.microsoft.com/fwlink/p/?LinkId=544749)Zeit.
    
  - Sie können den Aufbewahrungsspeicher so konfigurieren, dass er an einem bestimmten Datum in der Zukunft deaktiviert ist. Hierzu führen Sie den `Set-Mailbox -EndDateForRetentionHold <date>` Befehl aus. Wenn beispielsweise angenommen wird, dass das heutige Datum der 1. Juni 2016 ist und Sie möchten, dass der Aufbewahrungszeitraum in 30 Tagen deaktiviert ist, führen `Set-Mailbox -EndDateForRetentionHold 7/1/2016`Sie den folgenden Befehl aus:. In diesem Szenario lassen Sie die *RentionHoldEnabled* -Eigenschaft auf `True`festgelegt. Weitere Informationen finden Sie unter [festlegen-Mailbox](https://go.microsoft.com/fwlink/p/?LinkId=150317).
    
  - Sie können die Einstellungen für die Aufbewahrungsrichtlinie ändern, die dem Postfach zugewiesen ist, sodass ältere Elemente, die importiert wurden, nicht sofort gelöscht oder in das Archivpostfach des Benutzers verschoben werden. Beispielsweise können Sie das Aufbewahrungs Alter für eine Lösch-oder Archivrichtlinie verlängern, die dem Postfach zugewiesen ist. In diesem Szenario würden Sie die Aufbewahrungszeit für das Postfach deaktivieren, nachdem Sie die Einstellungen der Aufbewahrungsrichtlinie geändert haben. Weitere Informationen finden Sie unter [Einrichten einer Archiv-und Löschrichtlinie für Postfächer in Ihrer Office 365 Organisation](set-up-an-archive-and-deletion-policy-for-mailboxes.md).
