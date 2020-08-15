---
title: Verwenden von PowerShell zum Ausführen einer Übernahmemigration zu Microsoft 365
ms.author: sirkkuw
author: sirkkuw
manager: laurawi
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
ms.assetid: b468cb4b-a35c-43d3-85bf-65446998af40
description: In diesem Artikel erfahren Sie, wie Sie mithilfe von PowerShell die Inhalte aus einem Quell-e-Mail-System auf einmal durch Ausführen einer Cutover-Migration zu Microsoft 365 migrieren.
ms.openlocfilehash: bf97fef7e0e927dc901b0223978a3eef377def2c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46690299"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a>Verwenden von PowerShell zum Ausführen einer Übernahmemigration zu Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können die Inhalte von Benutzerpostfächern aus einem Quell-e-Mail-System auf einmal mithilfe einer Cutover-Migration zu Microsoft 365 migrieren. Dieser Artikel führt Sie durch die Aufgaben für eine E-Mail-Übernahmemigration mithilfe von Exchange Online PowerShell. 
  
Durch die Überprüfung des Themas, [was Sie über eine Cutover-e-Mail-Migration zu Microsoft 365 wissen müssen](https://go.microsoft.com/fwlink/p/?LinkId=536688), erhalten Sie einen Überblick über den Migrationsprozess. Wenn Sie mit dem Inhalt dieses Artikels vertraut sind, verwenden Sie die Informationen, um Postfächer von einem E-Mail-System zu einem anderen zu migrieren.
  
> [!NOTE]
> Sie können auch die Exchange-Verwaltungskonsole zum Durchführen einer Übernahmemigration verwenden. Weitere Informationen finden Sie unter [Durchführen einer Cutover Migration von e-Mails zu Microsoft 365](https://go.microsoft.com/fwlink/p/?LinkId=536689). 
  
## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

Geschätzte Zeit bis zum Abschließen dieser Aufgabe: 2 bis 5 Minuten, um einen Migrationsbatch zu erstellen. Nach dem Start der Migration variiert die Dauer der Migration abhängig von der Anzahl von Postfächern in dem Batch, der Größe der einzelnen Postfächer und Ihrer verfügbaren Netzkapazität. Informationen zu anderen Faktoren, die sich auf die Dauer der Migration von Postfächern zu Microsoft 365 auswirken, finden Sie unter [Migrationsleistung](https://go.microsoft.com/fwlink/p/?LinkId=275079).
  
Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Berechtigungen, die Sie benötigen, finden Sie unter dem Eintrag „Migration" in einer Tabelle im Thema [Empfängerberechtigungen](https://go.microsoft.com/fwlink/p/?LinkId=534105).
  
Um die Exchange Online-PowerShell-Cmdlets zu verwenden, müssen Sie angemeldet sein und die Cmdlets in Ihre lokale Windows PowerShell Sitzung importieren. Finden Sie Anweisungen unter[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShelll](https://go.microsoft.com/fwlink/p/?LinkId=534121).
  
Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).
  
## <a name="migration-steps"></a>Migrationsschritte

### <a name="step-1-prepare-for-a-cutover-migration"></a>Schritt 1: Übernahmemigration vorbereiten
<a name="BK_Step1"> </a>

- **Fügen Sie Ihre lokale Exchange-Organisation als akzeptierte Domäne Ihrer Microsoft 365-Organisation hinzu.** Der Migrationsdienst verwendet die SMTP-Adresse Ihrer lokalen Postfächer, um die Microsoft Online Services-Benutzer-ID und die e-Mail-Adresse für die neuen Microsoft 365-Postfächer zu erstellen. Die Migration schlägt fehl, wenn es sich bei Ihrer Exchange-Domäne nicht um eine akzeptierte Domäne oder die primäre Domäne Ihrer Microsoft 365-Organisation handelt. Weitere Informationen finden Sie unter [Überprüfen Ihrer Domäne](https://go.microsoft.com/fwlink/p/?LinkId=534110).
    
- **Konfigurieren von Outlook Anywhere auf dem lokalen Exchange-Server** Der E-Mail-Migrationsdienst verwendet RPC über HTTP oder Outlook Anywhere, um eine Verbindung mit dem lokalen Exchange-Server herzustellen. Informationen zum Einrichten von Outlook Anywhere für Exchange 2010, Exchange 2007 und Exchange 2003 finden Sie unter den folgenden Themen:
    
  - [Exchange 2010: Aktivieren von Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=187249)
    
  - [Exchange 2007: Aktivieren von Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=167210)
    
  - [Exchange 2003: Bereitstellungsszenarien für RPC über HTTP](https://go.microsoft.com/fwlink/?LinkID=73657)
    
  - [Konfigurieren von Outlook Anywhere mit Exchange 2003](https://go.microsoft.com/fwlink/?LinkID=167209)
    
    > [!IMPORTANT]
    > Die Outlook Anywhere-Konfiguration muss mit einem Zertifikat einer vertrauenswürdigen Zertifizierungsstelle konfiguriert werden. Outlook Anywhere kann nicht mit einem selbstsignierten Zertifikat konfiguriert werden. Weitere Informationen finden Sie unter [Konfigurieren von SSL für Outlook Anywhere](https://go.microsoft.com/fwlink/?LinkID=80875). 
  
- **Sicherstellen, dass mit Outlook Anywhere eine Verbindung mit der Exchange-Organisation hergestellt werden kann** Sie können eine der folgenden Methoden verwenden, um die Verbindungseinstellungen zu testen:
    
  - Verwenden Sie Microsoft Outlook von außerhalb Ihre Firmennetzwerks, um eine Verbindung mit Ihrem lokalen Exchange-Postfach herzustellen.
    
  - Verwenden Sie die Microsoft [Exchange-Remoteverbindungsuntersuchung](https://www.testexchangeconnectivity.com/) zum Testen der Verbindungseinstellungen. Verwenden Sie die Outlook Anywhere- (RPC über HTTP)- oder Outlook-AutoErmittlungs-Tests.
    
  - Führen Sie die folgenden Befehle in Exchange Online PowerShell aus:
    
  ```
  $Credentials = Get-Credential
  ```

  ```
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- **Zuweisen der erforderlichen Berechtigungen für das lokale Benutzerkonto für den Zugriff auf Postfächer in der Exchange-Organisation** Das lokale Benutzerkonto, das Sie zum Herstellen einer Verbindung mit Ihrer lokalen Exchange-Organisation (auch als Migrations Administrator bezeichnet) verwenden, muss über die erforderlichen Berechtigungen für den Zugriff auf die lokalen Postfächer verfügen, die Sie zu Microsoft 365 migrieren möchten. Dieses Benutzerkonto wird zur Erstellung eines Migrationsendpunkts zu Ihrer lokalen Organisation verwendet.
    
    Die folgende Liste zeigt die Administratorrechte an, die erforderlich sind, um Postfächer mithilfe einer Übernahmemigration zu migrieren. Es gibt drei mögliche Optionen.
    
  - Der Migrationsadministrator muss Mitglied der Gruppe **Domänen-Admins** in Active Directory in der lokalen Organisation sein.
    
    oder -
    
  - Dem Migrationsadministrator muss die Berechtigung **FullAccess** für jedes lokale Postfach zugewiesen werden.
    
    oder -
    
  - Dem Migrationsadministrator muss die Berechtigung **Receive As** für die lokale Postfachdatenbank zugewiesen werden, in der die Benutzerpostfächer gespeichert sind.
    
- **Deaktivieren von Unified Messaging** Wenn die zu migrierenden lokalen Postfächer für Unified Messaging (UM) aktiviert sind, müssen Sie vor der Migration UM in den Postfächern deaktivieren. Nach Abschluss der Migration können Sie UM dann für die Postfächer wieder aktivieren.
    
- **Sicherheitsgruppen und Stellvertretungen** Der e-Mail-Migrationsdienst kann nicht erkennen, ob lokale Active Directory Gruppen Sicherheitsgruppen sind oder nicht, sodass migrierte Gruppen nicht als Sicherheitsgruppen in Microsoft 365 bereitgestellt werden können. Wenn Sie Sicherheitsgruppen in Ihrem Microsoft 365-Mandanten haben möchten, müssen Sie zuerst eine leere e-Mail-aktivierte Sicherheitsgruppe in Ihrem Microsoft 365-Mandanten vorsehen, bevor Sie die Cutover-Migration starten. Zudem werden bei dieser Migrationsmethode nur Postfächer, E-Mail-Benutzer, E-Mail-Kontakte und E-Mail-aktivierte Gruppen verschoben. Wenn ein anderes Active Directory-Objekt, wie beispielsweise ein Benutzer, der nicht zu Microsoft 365 migriert wird, als Manager oder Stellvertreter für ein migriertes Objekt zugewiesen wird, müssen Sie vor der Migration aus dem Objekt entfernt werden.
    
### <a name="step-2-create-a-migration-endpoint"></a>Schritt 2: Migrationsendpunkt erstellen
<a name="BK_Step2"> </a>

Um e-Mails erfolgreich zu migrieren, muss Microsoft 365 eine Verbindung herstellen und mit dem Quell-e-Mail-System kommunizieren. Zu diesem Zwecke verwendet Microsoft 365 einen Migrations Endpunkt. Um einen Outlook Anywhere-Migrationsendpunkt für die Übernahmemigration zu erstellen, [stellen Sie zunächst eine Verbindung mit Exchange Online her](https://go.microsoft.com/fwlink/p/?LinkId=534121). 
  
Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](https://go.microsoft.com/fwlink/p/?LinkId=534750).
  
Führen Sie die folgenden Befehle in Exchange Online PowerShell aus:
  
```
$Credentials = Get-Credential
```

Dabei wird das Cmdlet [Test-MigrationServerAvailability](https://go.microsoft.com/fwlink/p/?LinkId=534752) verwendet, um die Einstellungen für die Verbindung mit dem lokalen Exchange-Server abzurufen und zu testen. Anschließend werden diese Verbindungseinstellungen zum Erstellen des Migrationsendpunkts verwendet.
  
```
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> Beim Cmdlet **New-MigrationEndpoint** können Sie mit der Option **-TargetDatabase** eine von dem Dienst zu verwendende Datenbank angeben. Andernfalls wird nach dem Zufallsprinzip eine Datenbank aus dem Active Directory-Verbunddienste (AD FS) 2.0-Standort zugewiesen, in dem sich das Verwaltungspostfach befindet.
  
#### <a name="verify-it-worked"></a>Stellen Sie die Funktion sicher

Führen Sie den folgenden Befehl zum Anzeigen von Informationen zum Migrationsendpunkt „CutoverEndpoint“ in Exchange Online PowerShell aus:
  
```
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a>Schritt 3: Übernahmemigrationsbatch erstellen
<a name="BK_Step3"> </a>

Sie können das **New-MigrationBatch** -Cmdlet in Exchange Online PowerShell verwenden, um einen Migrationsbatch für eine Übernahmemigration zu erstellen. Sie können einen Migrationsbatch erstellen und diesen automatisch starten, indem Sie den _AutoStart_-Parameter verwenden. Alternativ können Sie den Migrationsbatch erstellen und später mithilfe des **Start-MigrationBatch** -Cmdlets manuell starten. In diesem Beispiel wird ein Migrationsbatch namens „CutoverBatch" erstellt und der im vorherigen Schritt erstellte Migrationsendpunkt verwendet.
  
```
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

In diesem Beispiel wird auch ein Migrationsbatch namens „CutoverBatch" erstellt und verwendet den Migrationsendpunkt, der im vorherigen Schritt erstellt wurde. Da der Parameter  _AutoStart_ nicht verwendet wird, muss der Migrationsbatch manuell im Migrationsdashboard gestartet werden oder mithilfe des **Start-MigrationBatch** -Cmdlets . Wie bereits erwähnt, kann immer nur ein Übernahmemigrationsbatch ausgeführt werden.
  
```
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a>Stellen Sie die Funktion sicher

Um zu überprüfen, ob Sie erfolgreich einen Migrationsbatch für eine Übernahmemigration erstellt haben, führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um Informationen zum neuen Migrationsbatch anzuzeigen:
  
```
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a>Schritt 4: Übernahmemigrationsbatch starten
<a name="BK_Step4"> </a>

Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um den Migrationsbatch zu starten. Dadurch wird ein Migrationsbatch namens „CutoverBatch“ erstellt.
  
```
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a>Stellen Sie die Funktion sicher

Wenn ein Migrationsbatch erfolgreich gestartet wurde, lautet sein Status im Migrationsdashboard Synchronisierung. Führen Sie den folgenden Befehl aus, um zu überprüfen, ob ein Migrationsbatch erfolgreich mithilfe von Exchange Online PowerShell gestartet wurde:
  
```
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Schritt 5: weiterleiten Ihrer e-Mail an Microsoft 365
<a name="BK_Step5"> </a>

E-Mail-Systeme verwenden einen als MX-Eintrag bezeichneten DNS-Eintrag, um zu ermitteln, wohin E-Mails gesendet werden sollen. Während der E-Mail-Migration hat Ihr MX-Eintrag auf Ihr Quell-E-Mail-System verwiesen. Nachdem die e-Mail-Migration zu Microsoft 365 abgeschlossen ist, ist es an der Zeit, Ihren MX-Eintrag auf Microsoft 365 zu richten. Dadurch kann sichergestellt werden, dass e-Mails an Ihre Microsoft 365-Postfächer gesendet werden. Wenn Sie den MX-Eintrag verschieben, können Sie auch Ihr altes e-Mail-System ausschalten, wenn Sie fertig sind. 
  
Für viele DNS-Anbieter gibt es bestimmte Anweisungen zum [Ändern des MX-Eintrags](https://go.microsoft.com/fwlink/p/?LinkId=279163). Wenn Ihr DNS-Anbieter nicht enthalten ist oder wenn Sie allgemeine Anweisungen erhalten möchten, finden Sie entsprechende Informationen unter [Erstellen und Konfigurieren eines DNS-Eintrags für Office 365](https://go.microsoft.com/fwlink/?LinkId=397449).
  
Es kann bis zu 72 Stunden dauern, bis die E-Mail-Systeme der Kunden und Partnern den geänderten MX-Eintrag erkennen. Warten Sie mindestens 72 Stunden, bevor Sie mit dem nächsten Schritt fortfahren: [Schritt 6: Übernahmemigrationsbatch löschen](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6). 
  
### <a name="step-6-delete-the-cutover-migration-batch"></a>Schritt 6: Übernahmemigrationsbatch löschen
<a name="Bk_step6"> </a>

Nachdem Sie den MX-Eintrag geändert und sichergestellt haben, dass alle e-Mails an Microsoft 365-Postfächer weitergeleitet werden, Benachrichtigen Sie die Benutzer, dass Ihre e-Mail-Nachrichten an Microsoft 365 gesendet werden. Danach können Sie den Übernahmemigrationsbatch löschen. Überprüfen Sie Folgendes, bevor Sie den Migrationsbatch löschen.
  
- Alle Benutzer verwenden Microsoft 365-Postfächer. Nach dem Löschen des Batches werden e-Mails, die an Postfächer im lokalen Exchange Server gesendet werden, nicht in die entsprechenden Microsoft 365-Postfächer kopiert.
    
- Microsoft 365-Postfächer wurden mindestens einmal synchronisiert, nachdem e-Mails direkt an Sie gesendet wurden. Stellen Sie dazu sicher, dass der Wert im Feld zuletzt synchronisierte Zeit für den Migrationsbatch aktueller ist als die Weiterleitung von e-Mails direkt an Microsoft 365-Postfächer.
    
Führen Sie den folgenden Befehl aus, um den Migrationsbatch „CutoverBatch“ in Exchange Online PowerShell zu löschen:
  
```
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a>Abschnitt 7: Zuweisen von Benutzerlizenzen
<a name="BK_Step7"> </a>

 **Aktivieren Sie Microsoft 365-Benutzerkonten für die migrierten Konten durch Zuweisen von Lizenzen.** Wenn Sie keine Lizenz zuweisen, wird das Postfach nach Ablauf der Kulanzzeit (30 Tage) deaktiviert. Informationen zum Zuweisen einer Lizenz im Microsoft 365 Admin Center finden Sie unter [zuweisen oder](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)Aufheben der Zuweisung von Lizenzen.
  
### <a name="step-8-complete-post-migration-tasks"></a>Schritt 8: Aufgaben nach der Migration abschließen
<a name="BK_Step8"> </a>

- **Erstellen Sie einen AutoErmittlung-DNS-Eintrag, damit Benutzer problemlos auf ihre Postfächer zugreifen können.** Nachdem alle lokalen Postfächer zu Microsoft 365 migriert wurden, können Sie einen Auto Ermittlungs-DNS-Eintrag für Ihre Microsoft 365-Organisation konfigurieren, um Benutzern die einfache Verbindung mit ihren neuen Microsoft 365-Postfächern mit Outlook und mobilen Clients zu ermöglichen. In diesem neuen DNS-Eintrag für die AutoErmittlung muss derselbe Namespace verwendet werden, den Sie für Ihre Microsoft 365-Organisation verwenden. Wenn der Namespace für die Cloud-basierte Organisation beispielsweise "cloud.contoso.com" lautet, müssen Sie den DNS-Datensatz "autodiscover.cloud.contoso.com" für die AutoErmittlung erstellen.
    
    Wenn Sie Ihre Exchange Server beibehalten, sollten Sie auch sicherstellen, dass der AutoErmittlungs-DNS-CNAME-Eintrag sowohl im internen als auch im externen DNS nach der Migration auf Microsoft 365 verweist, damit der Outlook-Client eine Verbindung mit dem richtigen Postfach herstellen kann.
    
    > [!NOTE]
    >  In Exchange 2007, Exchange 2010 und Exchange 2013 sollten Sie auch  `Set-ClientAccessServer AutodiscoverInternalConnectionURI` auf `Null` festlegen. 
  
    Microsoft 365 verwendet einen CNAME-Eintrag, um den AutoErmittlungsdienst für Outlook und Mobile Clients zu implementieren. Der CNAME-Eintrag für die AutoErmittlung muss folgende Informationen enthalten:
    
  - **Alias:** autodiscover
    
  - **Ziel:** autodiscover.outlook.com
    
    Weitere Informationen finden Sie unter [Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne](https://go.microsoft.com/fwlink/p/?LinkId=535028).
    
- **Nehmen Sie lokale Exchange-Server außer Betrieb.** Nachdem Sie sichergestellt haben, dass alle e-Mails direkt an die Microsoft 365-Postfächer weitergeleitet werden und Sie Ihre lokale e-Mail-Organisation nicht mehr warten müssen oder nicht die Implementierung einer Lösung für einmaliges Anmelden (Single Sign-on, SSO) planen möchten, können Sie Exchange von ihren Servern deinstallieren und Ihre lokale Exchange-Organisation entfernen.
    
    Weitere Informationen erhalten Sie unter den folgenden Themen:
    
  - [Ändern oder Entfernen von Exchange 2010](https://go.microsoft.com/fwlink/?LinkId=217936)
    
  - [Entfernen einer Exchange 2007-Organisation](https://go.microsoft.com/fwlink/?LinkID=100485)
    
  - [Deinstallieren von Exchange Server 2003](https://go.microsoft.com/fwlink/?LinkID=56561)
    

