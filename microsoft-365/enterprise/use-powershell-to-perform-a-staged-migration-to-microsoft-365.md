---
title: Verwenden von PowerShell zum Ausführen einer mehrstufigen Migration zu Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: a20f9dbd-6102-4ffa-b72c-ff813e700930
description: Erfahren Sie, wie Sie Mithilfe von PowerShell Inhalte aus einem Quell-E-Mail-System im Laufe der Zeit mithilfe einer mehrstufigen Migration zu einem Microsoft 365.
ms.openlocfilehash: 0c93de181c54fb1c4021d23d787b63577317aad4
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924792"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>Verwenden von PowerShell zum Ausführen einer mehrstufigen Migration zu Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können den Inhalt von Benutzerpostfächern aus einem Quell-E-Mail-System mithilfe einer mehrstufigen Migration Microsoft 365 migrieren.
  
Dieser Artikel führt Sie durch die Aufgaben im Zusammenhang mit einer mehrstufigen E-Mail-Migration mit Exchange Online PowerShell. Im Thema Was Sie über eine mehrstufige [E-Mail-Migration](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration)wissen müssen, erhalten Sie einen Überblick über den Migrationsprozess. Wenn Sie mit dem Inhalt dieses Artikels vertraut sind, verwenden Sie ihn, um mit der Migration der Postfächer von einem E-Mail-System zu einem anderen zu beginnen.
  
> [!NOTE]
> Sie können auch mit der Exchange-Verwaltungskonsole eine mehrstufige Migration durchführen. Weitere [Informationen finden Sie unter Perform a staged migration of email to Microsoft 365](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

Geschätzte Zeit bis zum Abschließen dieser Aufgabe: 2 bis 5 Minuten, um einen Migrationsbatch zu erstellen. Nach dem Start der Migration variiert die Dauer der Migration abhängig von der Anzahl von Postfächern in dem Batch, der Größe der einzelnen Postfächer und Ihrer verfügbaren Netzkapazität. Weitere Informationen zu anderen Faktoren, die sich auf die Dauer der Migration von Postfächern zu Microsoft 365, finden Sie unter [Migration Performance](/Exchange/mailbox-migration/office-365-migration-best-practices).
  
Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Berechtigungen, die Sie benötigen, finden Sie unter dem Eintrag "Migration" unter dem Thema [Empfängerberechtigungen](/exchange/recipients-permissions-exchange-2013-help).
  
Um die Exchange Online-PowerShell-Cmdlets zu verwenden, müssen Sie angemeldet sein und die Cmdlets in Ihre lokale Windows PowerShell Sitzung importieren. Finden Sie Anweisungen unter[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShelll](/powershell/exchange/connect-to-exchange-online-powershell).
  
Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](/powershell/exchange/).
  
## <a name="migration-steps"></a>Migrationsschritte

### <a name="step-1-prepare-for-a-staged-migration"></a>Schritt 1: Auf eine mehrstufige Migration vorbereiten

Bevor Sie Postfächer mithilfe einer mehrstufigen Migration zu Microsoft 365, müssen Sie einige Änderungen an Ihrer Umgebung Exchange vornehmen.
  
 **Konfigurieren Sie Outlook Anywhere auf Ihrem lokalen Exchange Server**. Der E-Mail-Migrationsdienst verwendet Outlook Anywhere (auch bekannt als RPC über HTTP), um eine Verbindung mit Ihrem lokalen Exchange Server herzustellen. Informationen zum Einrichten von Outlook Anywhere für Exchange Server 2007 und Exchange 2003 finden Sie im Folgenden:
  
- [Exchange 2007: Aktivieren von Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))
    
- [Konfigurieren von Outlook Anywhere mit Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))
    
> [!IMPORTANT]
> Sie müssen ein Zertifikat verwenden, das von einer vertrauenswürdigen Zertifizierungsstelle (CA) mit Ihrer Outlook Anywhere-Konfiguration erstellt wurde. Outlook Anywhere kann nicht mit einem selbstsignierten Zertifikat konfiguriert werden. Weitere Informationen finden Sie unter [Konfigurieren von SSL für Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)). 
  
 **Optional: Stellen Sie sicher, dass Sie eine Verbindung zu Ihrer Exchange Organisation mit Outlook Anywhere** herstellen können. Versuchen Sie eine der folgenden Methoden, um die Verbindungseinstellungen zu testen.
  
- Verwenden Sie Outlook von außerhalb des Unternehmensnetzwerks zur Verbindung mit Ihrem lokalen Exchange-Postfach.
    
- Verwenden Sie [die Microsoft Remote Connectivity Analyzer,](https://https://testconnectivity.microsoft.com/) um Ihre Verbindungseinstellungen zu testen. Verwenden Sie Outlook Anywhere (RPC über HTTP) oder Outlook AutoErmittlung-Tests.
    
- Führen Sie die folgenden Befehle in Exchange Online PowerShell aus:
    
  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **Festlegen von Berechtigungen** Das lokale Benutzerkonto, das Sie zum Herstellen einer Verbindung mit Ihrer lokalen Exchange-Organisation (auch migrationsadministrator genannt) verwenden, muss über die erforderlichen Berechtigungen für den Zugriff auf die lokalen Postfächer verfügen, die Sie zu Microsoft 365. Dieses Benutzerkonto wird verwendet, wenn Sie sich mit Ihrem E-Mail-System durch das Erstellen eines Migrationsendpunkts im laufenden Prozess ([Schritt 3: Migrationsendpunkt erstellen](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint) ) verbinden.
  
Um die Postfächer zu migrieren, muss der Administrator eine der folgenden Berechtigungen haben:
  
- Ein Mitglied der **Domänen-Admins** -Gruppe in Active Directory in der lokalen Organisation sein.
    
    oder
    
- **FullAccess** -Berechtigung für jedes lokale Postfach und die **WriteProperty** -Berechtigung zum Ändern der **TargetAddress** -Eigenschaft für die lokale Benutzerkonten besitzen.
    
    oder
    
- Die **ReceiveAs** -Berechtigung für die lokale Postfachdatenbank besitzen, in der die Benutzerpostfächer gespeichert sind und die **WriteProperty** -Berechtigung besitzen, um die **TargetAddress** -Eigenschaft für die lokalen Benutzerkonten ändern zu können.
    
Anweisungen zum Festlegen dieser Berechtigungen finden Sie unter [Assign permissions to migrate mailboxes to Microsoft 365](/Exchange/mailbox-migration/assign-permissions-for-migration).
  
 **Deaktivieren von Unified Messaging (UM)** Wenn UM für die lokalen Postfächer aktiviert ist, die Sie migrieren, deaktivieren Sie UM vor der Migration. Aktivieren Sie UM für die Postfächer nach Abschluss der Migration. Weitere Anleitungen finden Sie unter [Deaktivieren von Unified Messaging](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80)).
  
 **Verwenden Sie die Verzeichnissynchronisierung, um neue Benutzer in Microsoft 365.** Sie verwenden die Verzeichnissynchronisierung, um alle lokalen Benutzer in Ihrer Organisation Microsoft 365 erstellen.
  
Sie müssen die Benutzer nach der Erstellung lizenzieren. Sie haben 30 Tage zum Hinzufügen von Lizenzen, nachdem die Benutzer erstellt wurden. Weitere Informationen zum Hinzufügen von Lizenzen finden Sie unter [Schritt 8: Aufgaben nach der Migration abschließen](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).
  
 Sie können entweder das Microsoft Azure Active Directory (Azure AD)-Synchronisierungstool oder die Microsoft Azure AD-Synchronisierungsdienste verwenden, um Ihre lokalen Benutzer in Microsoft 365. Nachdem Postfächer zu Microsoft 365 migriert wurden, verwalten Sie Benutzerkonten in Ihrer lokalen Organisation und werden mit Ihrer Microsoft 365 synchronisiert. Weitere Informationen finden Sie unter [Verzeichnisintegration](/previous-versions/azure/azure-services/jj573653(v=azure.100)).
  
### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>Schritt 2: Erstellen einer CSV-Datei für einen Batch der mehrstufigen Migration

Nachdem Sie die Benutzer identifiziert haben, deren lokale Postfächer Sie zu Microsoft 365 migrieren möchten, verwenden Sie eine CSV-Datei (Comma Separated Value), um einen Migrationsbatch zu erstellen. Jede Zeile in der CSV-Datei, die von Microsoft 365 zum Ausführen der Migration verwendet wird, enthält Informationen zu einem lokalen Postfach. 
  
> [!NOTE]
> Es gibt keinen Grenzwert für die Anzahl von Postfächern, die Sie mithilfe einer mehrstufigen Migration zu Microsoft 365 migrieren können. Die CSV-Datei für einen Migrationsbatch kann maximal 2.000 Zeilen enthalten. Erstellen Sie zum Migrieren von mehr als 2.000 Postfächern zusätzliche CSV-Dateien und verwenden Sie jede Datei, um einen neuen Migrationsbatch zu erstellen. 
  
 **Unterstützte Attribute**
  
Die CSV-Datei für eine mehrstufige Migration unterstützt die folgenden drei Attribute. Jede Zeile der CSV-Datei entspricht einem Postfach und muss einen Wert für jedes dieser Attribute enthalten.
  
|**Attribut**|**Beschreibung**|**Erforderlich?**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |Gibt die primäre SMTP-E-Mail-Adresse, z. B. pilarp@contoso.com für lokale Postfächer an.  <br/> Verwenden Sie die primäre SMTP-Adresse für lokale Postfächer und keine Benutzer-IDs aus Microsoft 365. Wenn die lokale Domäne beispielsweise den Namen contoso.com aber die Microsoft 365-E-Mail-Domäne service.contoso.com hat, verwenden Sie den contoso.com-Domänennamen für E-Mail-Adressen in der CSV-Datei.  <br/> |Erforderlich  <br/> |
|Kennwort  <br/> |Das Kennwort, das für das neue Postfach Microsoft 365 werden soll. Alle Kennworteinschränkungen, die auf Ihre organisation Microsoft 365 angewendet werden, gelten auch für die Kennwörter, die in der CSV-Datei enthalten sind.  <br/> |Optional  <br/> |
|ForceChangePassword  <br/> |Gibt an, ob ein Benutzer das Kennwort bei der ersten Anmeldung beim neuen Postfach ändern Microsoft 365 muss. Verwenden Sie **True** oder **False** als Wert für diesen Parameter. <br/> > [!NOTE]> Wenn Sie eine Lösung für einmaliges Anmelden (SSO) durch die Bereitstellung von Active Directory-Verbunddiensten (AD FS) oder höher in Ihrer lokalen Organisation implementiert haben, verwenden Sie **False** als Wert für das Attribut **ForceChangePassword**.          |Optional  <br/> |
   
 **CSV-Dateiformat**
  
Das folgende Beispiel zeigt das Format der CSV-Datei. In diesem Beispiel werden drei lokale Postfächer zu Microsoft 365.
  
In der ersten Zeile (auch als Kopfzeile bezeichnet) der CSV-Datei sind die Namen der Attribute oder Felder aufgelistet, die in den folgenden Zeilen angegeben werden. Die einzelnen Attributnamen werden jeweils durch ein Komma getrennt.
  
```powershell
EmailAddress,Password,ForceChangePassword 
pilarp@contoso.com,Pa$$w0rd,False 
tobyn@contoso.com,Pa$$w0rd,False 
briant@contoso.com,Pa$$w0rd,False 
```

Die Zeilen unter der Kopfzeile stellen einen Benutzer dar und enthalten die Informationen, die zum Migrieren des Postfachs des Benutzers verwendet werden. Die Attributwerte in jeder einzelnen Zeile müssen die gleiche Reihenfolge aufweisen wie die Attributnamen in der Kopfzeile. 
  
Sie können einen beliebigen Text-Editor oder eine Anwendung wie Excel zum Erstellen der CSV-Datei verwenden. Speichern Sie die Datei als CSV- oder TXT-Datei.
  
> [!NOTE]
> Wenn die CSV-Datei Nicht-ASCII-Zeichen oder Sonderzeichen enthält, muss sie mit UTF-8-Codierung oder einer anderen Unicode-Codierung gespeichert werden. Abhängig von der Anwendung kann es leichter sein, die CSV-Datei mit UTF-8-Codierung oder einer anderen Unicode-Codierung zu speichern, wenn das Systemgebietsschema des Computers der in der CSV-Datei verwendeten Sprache entspricht. 
  
### <a name="step-3-create-a-migration-endpoint"></a>Schritt 3: Migrationsendpunkt erstellen
<a name="BK_Endpoint"> </a>

Um E-Mails erfolgreich zu migrieren, Microsoft 365 E-Mail-System eine Verbindung herstellen und mit dem Quell-E-Mail-System kommunizieren. Dazu verwendet Microsoft 365 einen Migrationsendpunkt. Zum Erstellen eines Migrationsendpunkts von Outlook Anywhere durch die Verwendung von PowerShell, für eine mehrstufige Migration, stellen Sie zuerst eine [Verbindung mit Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) her. 
  
Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](/powershell/exchange/).
  
Zum Erstellen eines Migrationsendpunkts von Outlook Anywhere, bezeichnet als "StagedEndpoint" in Exchange Online PowerShell, führen Sie den folgenden Befehl aus:
  
```powershell
$Credentials = Get-Credential
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name StagedEndpoint -Autodiscover -EmailAddress administrator@contoso.com -Credentials $Credentials
```

Weitere Informationen zu den **New-MigrationEndpoint** -Cmdlets finden Sie unter [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).
  
> [!NOTE]
> Beim Cmdlet **New-MigrationEndpoint** können Sie mit der Option **-TargetDatabase** eine von dem Dienst zu verwendende Datenbank angeben. Andernfalls wird nach dem Zufallsprinzip eine Datenbank aus dem Active Directory-Verbunddienste (AD FS) 2.0-Standort zugewiesen, in dem sich das Verwaltungspostfach befindet.
  
#### <a name="verify-it-worked"></a>Stellen Sie die Funktion sicher

Führen Sie den folgenden Befehl zum Anzeigen von Informationen zum Migrationsendpunkt "StagedEndpoint" in Exchange Online PowerShell aus:
  
```powershell
Get-MigrationEndpoint StagedEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*
```

### <a name="step-4-create-and-start-a-stage-migration-batch"></a>Schritt 4: Erstellen und starten eines Batches für eine mehrstufige Migration
<a name="BK_Endpoint"> </a>

Sie können das **New-MigrationBatch** -Cmdlet in Exchange Online PowerShell verwenden, um einen Migrationsbatch für eine Übernahmemigration zu erstellen. Sie können einen Migrationsbatch erstellen und diesen automatisch starten, indem Sie den Parameter _AutoStart_ verwenden. Alternativ können Sie den Migrationsbatch erstellen und später mithilfe des **Start-MigrationBatch** -Cmdlets manuell starten. In diesem Beispiel wird ein Migrationsbatch namens "StagedBatch1" erstellt und verwendet den Migrationsendpunkt, der im vorherigen Schritt erstellt wurde.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint -AutoStart
```

In diesem Beispiel wird auch ein Migrationsbatch namens "StagedBatch1" erstellt und verwendet den Migrationsendpunkt, der im vorherigen Schritt erstellt wurde. Da der Parameter  _AutoStart_ nicht verwendet wird, muss der Migrationsbatch manuell im Migrationsdashboard gestartet werden oder mithilfe des **Start-MigrationBatch** -Cmdlets . Wie bereits erwähnt, kann immer nur ein Übernahmemigrationsbatch ausgeführt werden.
  
```powershell
New-MigrationBatch -Name StagedBatch1 -SourceEndpoint StagedEndpoint
```

#### <a name="verify-it-worked"></a>Stellen Sie die Funktion sicher

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um Informationen über den "StagedBatch1" anzuzeigen:
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List
```

Sie können auch überprüfen, ob der Batch gestartet wurde, indem Sie den folgenden Befehl ausführen:
  
```powershell
Get-MigrationBatch -Identity StagedBatch1 | Format-List Status
```

Weitere Informationen zu den **Get-MigrationBatch** -Cmdlets finden Sie unter [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).
  
### <a name="step-5-convert-on-premises-mailboxes-to-mail-enabled-users"></a>Schritt 5: Konvertieren lokaler Postfächer in E-Mail-aktivierte Benutzer
<a name="BK_Endpoint"> </a>

Nachdem Sie einen Batch Postfächer erfolgreich migriert haben, benötigen Sie eine Methode, damit die Benutzer auf ihre E-Mail zugreifen können. Ein Benutzer, dessen Postfach migriert wurde, verfügt jetzt sowohl über ein lokales als auch ein lokales Postfach Microsoft 365. Benutzer, die über ein Postfach in Microsoft 365 empfangen keine neuen E-Mails mehr in ihrem lokalen Postfach. 
  
Da Sie mit Ihren Migrationen noch nicht fertig sind, können Sie noch nicht alle Benutzer an Microsoft 365 E-Mail-Adresse weiterverschicken. Was also tun Sie für diese Personen, die beide haben? Sie können die lokalen Postfächer ändern, die Sie bereits zu E-Mail-aktivierte Benutzer migriert haben. Wenn Sie von einem Postfach zu einem E-Mail-aktivierten Benutzer wechseln, können Sie den Benutzer an Microsoft 365 E-Mail-Adresse anstatt zu ihrem lokalen Postfach zu wechseln. 
  
Ein weiterer wichtiger Grund für die Konvertierung von lokalen Postfächern in E-Mail-aktivierte Benutzer ist das Beibehalten von Proxyadressen aus den Microsoft 365-Postfächern, indem Proxyadressen in die E-Mail-aktivierten Benutzer kopiert werden. So können Sie Cloud-basierte Benutzer mithilfe von Active Directory von der lokalen Organisation aus verwalten. Wenn Sie ihre lokale Exchange Server-Organisation außer Betrieb gesetzt haben, nachdem alle Postfächer zu Microsoft 365 migriert wurden, verbleiben die Proxyadressen, die Sie in die E-Mail-aktivierten Benutzer kopiert haben, in Ihrem lokalen Active Directory.
    
### <a name="step-6-delete-a-staged-migration-batch"></a>Schritt 6: Löschen eines Batches für die mehrstufige Migration
<a name="BK_Endpoint"> </a>

 Nachdem alle Postfächer in einem Migrationsbatch erfolgreich migriert wurden und Sie die lokalen Postfächer im Batch in E-Mail-aktivierte Benutzer konvertiert haben, können Sie einen Batch der mehrstufigen Migration löschen. Stellen Sie sicher, dass E-Mails an die Microsoft 365 im Migrationsbatch weitergeleitet werden. Wenn Sie einen Batch für die mehrstufige Migration löschen, bereinigt der Migrationsdienst alle zum Migrationsbatch gehörenden Datensätze und löscht den Migrationsbatch.
  
Führen Sie den folgenden Befehl aus, um den Migrationsbatch "StagedBatch1" in Exchange Online PowerShell zu löschen.
  
```powershell
Remove-MigrationBatch -Identity StagedBatch1
```

Weitere Informationen zu dem **Remove-MigrationBatch** -Cmdlet finden Sie unter [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).
  
#### <a name="verify-it-worked"></a>Stellen Sie die Funktion sicher

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um Informationen über den "IMAPBatch1" anzuzeigen:
  
```powershell
Get-MigrationBatch StagedBatch1
```

Der Befehl gibt entweder den Migrationsbatch mit dem Status **Removing** zurück oder einen Fehler, der besagt, dass der Migrationsbatch nicht gefunden werden konnte, was bestätigt, dass er gelöscht wurde.
  
Weitere Informationen zu den **Get-MigrationBatch** -Cmdlets finden Sie unter [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).
  
### <a name="step7-assign-licenses-to-microsoft-365-users"></a>Schritt 7: Zuweisen von Lizenzen Microsoft 365 Benutzern
<a name="BK_Endpoint"> </a>

Aktivieren Microsoft 365 benutzerkonten für die migrierten Konten durch Zuweisen von Lizenzen. Wenn Sie keine Lizenz zuweisen, wird das Postfach deaktiviert, sobald die Karenzzeit (30 Tage) endet. Informationen zum Zuweisen einer Lizenz im Microsoft 365 Admin Center finden Sie unter [Assign or unassign licenses](../admin/manage/assign-licenses-to-users.md).
  
### <a name="step-8-complete-post-migration-tasks"></a>Schritt 8: Aufgaben nach der Migration abschließen
<a name="BK_Postmigration"> </a>

- **Erstellen Sie einen AutoErmittlung-DNS-Eintrag, damit Benutzer problemlos auf ihre Postfächer zugreifen können.** Nachdem alle lokalen Postfächer zu Microsoft 365 migriert wurden, können Sie einen AutoErmittlungs-DNS-Eintrag für Ihre Microsoft 365-Organisation konfigurieren, damit Benutzer problemlos eine Verbindung mit ihren neuen Microsoft 365-Postfächern mit Outlook- und mobilen Clients herstellen können. Dieser neue AutoErmittlungs-DNS-Eintrag muss denselben Namespace verwenden, den Sie für Ihre organisation Microsoft 365 verwenden. Wenn der Namespace für die Cloud-basierte Organisation beispielsweise "cloud.contoso.com" lautet, müssen Sie den DNS-Datensatz "autodiscover.cloud.contoso.com" für die AutoErmittlung erstellen.
    
    Microsoft 365 verwendet einen CNAME-Eintrag, um den AutoErmittlungsdienst für Outlook und mobile Clients zu implementieren. Der CNAME-Eintrag für die AutoErmittlung muss folgende Informationen enthalten:
    
  - **Alias:** autodiscover
    
  - **Ziel:** autodiscover.outlook.com
    
    Weitere Informationen finden Sie unter [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).
    
- **Nehmen Sie lokale Exchange-Server außer Betrieb.** Nachdem Sie überprüft haben, ob alle E-Mails direkt an die Microsoft 365-Postfächer geroutet werden und Sie ihre lokale E-Mail-Organisation nicht mehr verwalten müssen oder keine Implementierung einer SSO-Lösung planen, können Sie Exchange von Ihren Servern deinstallieren und Ihre lokale Exchange-Organisation entfernen.
    
    Weitere Informationen erhalten Sie unter den folgenden Themen:
    
  - [Ändern oder Entfernen von Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))
    
  - [Entfernen einer Exchange 2007-Organisation](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))
    
  - [Deinstallieren von Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))
