---
title: Verwenden von PowerShell zum Ausführen einer IMAP-Migration zu Microsoft 365
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
ms.assetid: c28de4a5-1e8e-4491-9421-af066cde7cdd
description: Erfahren Sie, wie Sie PowerShell verwenden, um eine Internet Mail Access Protocol (IMAP)-Migration zu Microsoft 365 durchzuführen.
ms.openlocfilehash: fbfc0340e80ce70aa8a706d89a4d27729b91535b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924768"
---
# <a name="use-powershell-to-perform-an-imap-migration-to-microsoft-365"></a>Verwenden von PowerShell zum Ausführen einer IMAP-Migration zu Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Im Rahmen der Bereitstellung von Microsoft 365 können Sie den Inhalt von Benutzerpostfächern von einem ImAP-E-Mail-Dienst (Internet Mail Access Protocol) zu Microsoft 365 migrieren. Dieser Artikel führt Sie durch die Aufgaben für eine IMAP-Migration mithilfe von Exchange Online PowerShell. 
  
> [!NOTE]
> Sie können auch die Exchange-Verwaltungskonsole zum Durchführen einer IMAP-Migration verwenden. Weitere [Informationen finden Sie unter Migrate your IMAP mailboxes](/Exchange/mailbox-migration/migrating-imap-mailboxes/migrating-imap-mailboxes). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

Geschätzte Zeit bis zum Abschließen dieser Aufgabe: 2 bis 5 Minuten, um einen Migrationsbatch zu erstellen. Nach dem Start der Migration variiert die Dauer der Migration abhängig von der Anzahl von Postfächern in dem Batch, der Größe der einzelnen Postfächer und Ihrer verfügbaren Netzkapazität. Weitere Informationen zu anderen Faktoren, die sich auf die Dauer der Migration von Postfächern zu Microsoft 365 [auswirken,](/Exchange/mailbox-migration/office-365-migration-best-practices)finden Sie unter Migration Performance .
  
Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Berechtigungen, die Sie benötigen, finden Sie unter dem Eintrag „Migration" in einer Tabelle im Thema [Empfängerberechtigungen](/exchange/recipients-permissions-exchange-2013-help).
  
Um die Exchange Online-PowerShell-Cmdlets zu verwenden, müssen Sie angemeldet sein und die Cmdlets in Ihre lokale Windows PowerShell Sitzung importieren. Finden Sie Anweisungen unter[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShelll](/powershell/exchange/connect-to-exchange-online-powershell).
  
Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](/powershell/exchange/).
  
Folgende Einschränkungen gelten für IMAP-Migrationen:
  
- Nur Elemente aus dem Posteingang oder anderen E-Mail-Ordnern eines Benutzers können migriert werden. Sie können keine Kontakte, Kalenderelemente oder Aufgaben migrieren.
    
- Maximal 500.000 Elemente können aus dem Postfach eines Benutzers migriert werden.
    
- Die maximale Nachrichtengröße, die migriert werden kann, beträgt 35 MB.
    
## <a name="migration-steps"></a>Migrationsschritte

### <a name="step-1-prepare-for-an-imap-migration"></a>Schritt 1: IMAP-Migration vorbereiten
<a name="BK_Step1"> </a>

- **Wenn Sie über eine Domäne für Ihre IMAP-Organisation verfügen, fügen Sie sie als akzeptierte Domäne Ihrer Microsoft 365-Organisation hinzu.** Wenn Sie dieselbe Domäne verwenden möchten, die Sie bereits für Ihre Microsoft 365-Postfächer besitzen, müssen Sie sie zunächst als akzeptierte Domäne zu Microsoft 365 hinzufügen. Nachdem Sie sie hinzugefügt haben, können Sie Ihre Benutzer in Microsoft 365 erstellen. Weitere Informationen finden Sie unter[Verify your domain](../admin/setup/add-domain.md).
    
- **Fügen Sie jeden Benutzer zu Microsoft 365 hinzu, damit er über ein Postfach verfügen kann.** Anweisungen finden Sie unter[Hinzufügen von Benutzern zu Microsoft 365 Business](../admin/add-users/add-users.md).
    
- **Abrufen des FQDN des IMAP-Servers**. Sie müssen den vollqualifizierten Domänennamen (FQDN, auch als vollständiger Computername bezeichnet) des IMAP-Servers angeben, von dem Sie Postfachdaten migrieren möchten, wenn Sie einen IMAP-Migrationsendpunkt erstellen. Verwenden Sie einen IMAP-Client oder den Ping-Befehl, um sicherzustellen, dass Sie mit dem FQDN über das Internet mit dem IMAP-Server kommunizieren können.
    
- **Konfigurieren der Firewall zum Zulassen von IMAP-Verbindungen**. Sie müssen unter Umständen Ports in der Firewall der Organisation öffnen, in der sich der IMAP-Server befindet, damit Netzwerkdatenverkehr, der während der Migration aus dem Microsoft-Datencenter stammt, in die Organisation gelangen darf, in der sich der IMAP-Server befindet. Eine Liste der IP-Adressen, die von Microsoft-Datencentern verwendet werden, finden Sie unter [Ausgehende IP-Adressen](./urls-and-ip-address-ranges.md).
    
- **Zuweisen der Administratorkontoberechtigungen für den Zugriff auf Postfächer in der IMAP-Organisation**. Wenn Sie Administratoranmeldeinformationen in der CSV-Datei verwenden, muss das verwendete Konto die erforderlichen Berechtigungen für den Zugriff auf die lokalen Postfächer besitzen. Die für den Zugriff auf Benutzerpostfächer erforderlichen Berechtigungen werden durch den jeweiligen IMAP-Server bestimmt. 
    
- **Um die Exchange Online-PowerShell-Cmdlets zu verwenden**, müssen Sie angemeldet sein und die Cmdlets in Ihre lokale Windows PowerShell-Sitzung importieren. Anweisungen finden Sie unter [Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).
    
    Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](/powershell/exchange/).
    
- **Überprüfen, ob Sie mit Ihrem IMAP-Server eine Verbindung herstellen können**. Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um die Einstellungen für die Verbindung mit Ihrem IMAP-Server zu testen.
    
  ```powershell
  Test-MigrationServerAvailability -IMAP -RemoteServer <FQDN of IMAP server> -Port <143 or 993> -Security <None, Ssl, or Tls>
  ```

    Normalerweise wird für den **Port** -Parameter der Wert 143 für unverschlüsselte oder TLS-Verbindungen (Transport Layer Security) verwendet und der Wert 993 für SSL-Verbindungen.
    
### <a name="step-2-create-a-csv-file-for-an-imap-migration-batch"></a>Schritt 2: CSV-Datei für einen IMAP-Migrationsbatch erstellen
<a name="BK_Step2"> </a>

Identifizieren Sie die Gruppe der Benutzer, deren Postfächer Sie in einem IMAP-Migrationsbatch migrieren möchten. Jede Zeile in der CSV-Datei enthält Informationen, die zum Herstellen einer Verbindung mit einem Postfach im IMAP-Messaging-System erforderlich sind.
  
Die folgenden Attribute sind für jeden Benutzer erforderlich: 
  
- **EmailAddress** gibt die Benutzer-ID für das Microsoft 365-Postfach des Benutzers an.
    
- **UserName** gibt den Anmeldenamen für das Konto an, das für den Zugriff auf das Postfach auf dem IMAP-Server verwendet werden soll.
    
- **Password** gibt das Kennwort für das Konto in der Spalte UserName **UserName** an.
    
Das folgende Beispiel zeigt das Format der CSV-Datei. In diesem Beispiel werden drei Postfächer migriert:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams,1091990
annb@contoso.edu,ann.beebe,2111991
paulc@contoso.edu,paul.cannon,3281986
```

Für das Attribut **UserName** können Sie zusätzlich zum Benutzernamen die Anmeldeinformationen eines Kontos verwenden, dem die erforderlichen Berechtigungen für den Zugriff auf Postfächer auf dem IMAP-Server zugewiesen wurden. Es folgen einige spezielle Formate, die für einige IMAP-Server verwendet werden:
  
 **Microsoft Exchange**
  
Wenn Sie E-Mails aus der IMAP-Implementierung für Microsoft Exchange migrieren, verwenden Sie das Format **Domain/Admin_UserName/User_UserName** für das **UserName** -Attribut in der CSV-Datei. Angenommen, Sie migrieren die E-Mails für die Benutzer Terry Adams, Ann Beebe und Paul Cannon von Exchange. Sie haben ein E-Mail-Administratorkonto, wobei der Benutzername **mailadmin** und das Kennwort **P \@ ssw0rd ist.** Die CSV-Datei würde dann folgendermaßen aussehen:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,contoso-students/mailadmin/terry.adams,P@ssw0rd
annb@contoso.edu,contoso-students/mailadmin/ann.beebe,P@ssw0rd
paulc@contoso.edu,contoso-students/mailadmin/paul.cannon,P@ssw0rd
```

 **Dovecot**
  
Verwenden Sie für IMAP-Server wie Dovecot-IMAP-Server, die Simple Authentication and Security Layer (SASL) unterstützen, das Format **User_UserName*Admin_UserName**, wobei das Sternchen ( * ) ein konfigurierbares Trennzeichen ist. Angenommen, Sie migrieren die E-Mails dieser Benutzer von einem Dovecot-IMAP-Server mit den Administratoranmeldeinformationen **mailadmin** und **P \@ ssw0rd**. Die CSV-Datei würde dann folgendermaßen aussehen:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,terry.adams*mailadmin,P@ssw0rd
annb@contoso.edu,ann.beebe*mailadmin,P@ssw0rd
paulc@contoso.edu,paul.cannon*mailadmin,P@ssw0rd
```

 **Mirapoint**
  
Wenn Sie E-Mails von Mirapoint Message Server migrieren, verwenden Sie das Format **#user \@ Domäne#Admin_UserName#** für die Administratoranmeldeinformationen. Zum Migrieren von E-Mails von Mirapoint mit den Administratoranmeldeinformationen **mailadmin** und **P \@ ssw0rd** würde Ihre CSV-Datei wie dies aussehen:
  
```powershell
EmailAddress,UserName,Password
terrya@contoso.edu,#terry.adams@contoso-students.edu#mailadmin#,P@ssw0rd
annb@contoso.edu,#ann.beebe@contoso-students.edu#mailadmin#,P@ssw0rd
paulc@contoso.edu,#paul.cannon@contoso-students.edu#mailadmin#,P@ssw0rd
```

 **Courier IMAP:**
  
Einige Quell-E-Mail-Systeme, z. B. Courier IMAP, unterstützen die Verwendung von Postfachadministratoranmeldeinformationen zum Migrieren von Postfächern zu Microsoft 365 nicht. Stattdessen können Sie Ihr E-Mail-Quellsystem für die Verwendung virtueller freigegebener Ordner einrichten. Mithilfe der virtuellen freigegebenen Ordner können Sie die Postfach-Administratoranmeldeinformationen verwenden, um auf Benutzerpostfächer im E-Mail-Quellsystem zuzugreifen. Weitere Informationen zum Konfigurieren von virtuellen freigegebenen Ordnern für Courier IMAP finden Sie unter [Shared Folders](https://go.microsoft.com/fwlink/p/?LinkId=398870).
  
Um Postfächer zu migrieren, nachdem Sie auf dem E-Mail-Quellsystem virtuelle freigegebene Ordner eingerichtet haben, müssen Sie das optionale Attribut **UserRoot** in die Migrationsdatei einfügen. Dieses Attribut gibt das Verzeichnis an, in dem die einzelnen Benutzerpostfächer in der Struktur der virtuellen freigegebenen Ordner im E-Mail-Quellsystem gespeichert sind. Der Pfad zu Terrys Postfach lautet beispielsweise „/users/terry.adams".
  
Beispiel für eine CSV-Datei, die das Attribut **UserRoot** enthält:
  
```powershell
EmailAddress,UserName,Password,UserRoot
terrya@contoso.edu,mailadmin,P@ssw0rd,/users/terry.adams
annb@contoso.edu,mailadmin,P@ssw0rd,/users/ann.beebe
paulc@contoso.edu,mailadmin,P@ssw0rd,/users/paul.cannon
```

### <a name="step-3-create-an-imap-migration-endpoint"></a>Schritt 3: IMAP-Migrationsendpunkt erstellen
<a name="BK_Step3"> </a>

Um E-Mails erfolgreich zu migrieren, muss Microsoft 365 eine Verbindung mit dem Quell-E-Mail-System herstellen und mit diesem kommunizieren. Zu diesem Zwecke verwendet Microsoft 365 einen Migrationsendpunkt. Der Migrationsendpunkt definiert außerdem die Anzahl der Postfächer, die gleichzeitig migriert werden, sowie die Anzahl der Postfächer, die gleichzeitig während einer inkrementellen Synchronisierung synchronisiert werden, die alle 24 Stunden auftritt. Um einen Migrationsendpunkt für die IMAP-Migration zu erstellen, [stellen Sie zunächst eine Verbindung mit Exchange Online her](/powershell/exchange/connect-to-exchange-online-powershell). 
  
Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](/powershell/exchange/).
  
Zum Erstellen eines IMAP-Migrationsendpunkts namens „IMAPEndpoint“ in Exchange Online PowerShell, führen Sie den folgenden Befehl aus:
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 993 -Security Ssl

```

Sie können auch Parameter zum Angeben gleichzeitiger Migrationen, gleichzeitiger inkrementeller Migrationen und des zu verwendenden Ports hinzufügen. Der folgende Exchange Online PowerShell-Befehl erstellt einen IMAP-Migrationsendpunkt namens „IMAPEndpoint", der 50 gleichzeitige Migrationen und bis zu 25 gleichzeitige inkrementelle Synchronisierungen unterstützt. Darüber hinaus wird der Endpunkt für die Verwendung von Port 143 für die TLS-Verschlüsselung konfiguriert.
  
```powershell
New-MigrationEndpoint -IMAP -Name IMAPEndpoint -RemoteServer imap.contoso.com -Port 143 -Security Tls -MaxConcurrentMigrations
50 -MaxConcurrentIncrementalSyncs 25
```

Weitere Informationen zu den **New-MigrationEndpoint** -Cmdlets finden Sie unter [New-MigrationEndpoint](/powershell/module/exchange/new-migrationendpoint).
  
#### <a name="verify-it-worked"></a>Stellen Sie die Funktion sicher

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um Informationen über den „IMAPEndpoint“ anzuzeigen:
  
```powershell
Get-MigrationEndpoint IMAPEndpoint | Format-List EndpointType,RemoteServer,Port,Security,Max*
```

### <a name="step-4-create-and-start-an-imap-migration-batch"></a>Schritt 4: Erstellen und Starten eines IMAP-Migrationsbatches
<a name="BK_Step4"> </a>

Sie können das [New-MigrationBatch](/powershell/module/exchange/new-migrationbatch)-Cmdlet verwenden, um einen Migrationsbatch für eine IMAP-Migration zu erstellen. Sie können einen Migrationsbatch erstellen und automatisch durch Einschließen des  _AutoStart_-Parameters starten. Alternativ können Sie den Migrationsbatch erstellen und danach mithilfe des [Start-MigrationBatch](/powershell/module/exchange/start-migrationbatch)-Cmdlets starten.
  
Der folgende Exchange Online PowerShell-Befehl startet automatisch den Migrationsbatch namens „IMAPBatch1“ mit den IMAP-Endpunkt namens „IMAPEndpoint“:
  
```powershell
New-MigrationBatch -Name IMAPBatch1 -SourceEndpoint IMAPEndpoint -CSVData ([System.IO.File]::ReadAllBytes("C:\Users\Administrator\Desktop\IMAPmigration_1.csv")) -AutoStart
```

#### <a name="verify-it-worked"></a>Stellen Sie die Funktion sicher

Führen Sie das [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch)-Cmdlet aus, um Informationen zu „IMAPBatch1" anzuzeigen:
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List
```

Sie können auch überprüfen, ob der Batch gestartet wurde, indem Sie den folgenden Befehl ausführen:
  
```powershell
Get-MigrationBatch -Identity IMAPBatch1 | Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Schritt 5: Route your email to Microsoft 365
<a name="BK_Step5"> </a>

E-Mail-Systeme verwenden einen als MX-Eintrag bezeichneten DNS-Eintrag, um zu ermitteln, wohin E-Mails gesendet werden sollen. Während der E-Mail-Migration hat Ihr MX-Eintrag auf Ihr Quell-E-Mail-System verwiesen. Nachdem die E-Mail-Migration zu Microsoft 365 abgeschlossen ist, ist es an der Zeit, Ihren MX-Eintrag auf Microsoft 365 zu verweisen. Dadurch wird sichergestellt, dass E-Mails an Ihre Microsoft 365-Postfächer zugestellt werden. Durch Verschieben des MX-Eintrags können Sie auch Ihr altes E-Mail-System deaktivieren, wenn Sie bereit sind. 
  
Für viele DNS-Anbieter gibt es bestimmte Anweisungen zum Ändern des MX-Eintrags. Wenn Ihr DNS-Anbieter nicht enthalten ist oder wenn Sie allgemeine Anweisungen erhalten möchten, finden Sie entsprechende Informationen unter [Erstellen und Konfigurieren eines DNS-Eintrags für Office 365](https://go.microsoft.com/fwlink/?LinkId=397449).
  
Es kann bis zu 72 Stunden dauern, bis die E-Mail-Systeme der Kunden und Partnern den geänderten MX-Eintrag erkennen. Warten Sie mindestens 72 Stunden, bevor Sie mit dem nächsten Schritt fortfahren: Schritt 6: IMAP-Migrationsbatch löschen. 
  
### <a name="step-6-delete-imap-migration-batch"></a>Schritt 6: IMAP-Migrationsbatch löschen
<a name="BK_Step6"> </a>

Nachdem Sie den MX-Eintrag geändert und überprüft haben, ob alle E-Mails an Microsoft 365-Postfächer geroutet werden, benachrichtigen Sie die Benutzer, dass ihre E-Mails an Microsoft 365 gesendet werden. Danach können Sie den IMAP-Migrationsbatch löschen. Überprüfen Sie Folgendes, bevor Sie den Migrationsbatch löschen.
  
- Alle Benutzer verwenden Microsoft 365-Postfächer. Nachdem der Batch gelöscht wurde, werden E-Mails, die an Postfächer in der lokalen Exchange Server gesendet werden, nicht in die entsprechenden Microsoft 365-Postfächer kopiert.
    
- Microsoft 365-Postfächer wurden mindestens einmal synchronisiert, nachdem E-Mails direkt an sie gesendet wurden. Stellen Sie dazu sicher, dass der Wert im Feld Letzte Synchronisierungszeit für den Migrationsbatch aktueller ist als der Wert, als E-Mails direkt an Microsoft 365-Postfächer geroutet wurden.
    
Führen Sie den folgenden Befehl aus, um den Migrationsbatch „IMAPBatch1“ in Exchange Online PowerShell zu löschen:

  
```powershell
Remove-MigrationBatch -Identity IMAPBatch1
```

Weitere Informationen zu dem **Remove-MigrationBatch** -Cmdlet finden Sie unter [Remove-MigrationBatch](/powershell/module/exchange/remove-migrationbatch).
  
#### <a name="verify-it-worked"></a>Stellen Sie die Funktion sicher

Führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um Informationen über den "IMAPBatch1" anzuzeigen:
  
```powershell
Get-MigrationBatch IMAPBatch1"
```

Der Befehl gibt entweder den Migrationsbatch mit dem Status **Removing** zurück oder einen Fehler, der besagt, dass der Migrationsbatch nicht gefunden werden konnte, was bestätigt, dass er gelöscht wurde.
  
Weitere Informationen zu den **Get-MigrationBatch** -Cmdlets finden Sie unter [Get-MigrationBatch](/powershell/module/exchange/get-migrationbatch).
  
## <a name="see-also"></a>Siehe auch

[Problembehandlung der IMAP-Migration](/exchange/troubleshoot/move-or-migrate-mailboxes/troubleshoot-issues-with-imap-mailbox-migration)