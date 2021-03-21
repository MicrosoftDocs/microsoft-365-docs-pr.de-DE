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
description: Erfahren Sie, wie Sie PowerShell verwenden, um die Inhalte aus einem Quell-E-Mail-System auf einmal zu verschieben, indem Sie eine Umstiegsmigration zu Microsoft 365 durchführen.
ms.openlocfilehash: 60bd3cb246e04aba37be06f7a951abbf25708412
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924804"
---
# <a name="use-powershell-to-perform-a-cutover-migration-to-microsoft-365"></a>Verwenden von PowerShell zum Ausführen einer Übernahmemigration zu Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können den Inhalt von Benutzerpostfächern aus einem Quell-E-Mail-System auf einmal zu Microsoft 365 migrieren, indem Sie eine Umstiegsmigration verwenden. Dieser Artikel führt Sie durch die Aufgaben für eine E-Mail-Übernahmemigration mithilfe von Exchange Online PowerShell.

Wenn Sie das Thema What [you need to know about a cutover email migration to Microsoft 365](/Exchange/mailbox-migration/what-to-know-about-a-cutover-migration)lesen, erhalten Sie eine Übersicht über den Migrationsprozess. Wenn Sie mit dem Inhalt dieses Artikels vertraut sind, verwenden Sie die Informationen, um Postfächer von einem E-Mail-System zu einem anderen zu migrieren.

> [!NOTE]
> Sie können auch die Exchange-Verwaltungskonsole zum Durchführen einer Übernahmemigration verwenden. Weitere [Informationen finden Sie unter Perform a cutover migration of email to Microsoft 365](/Exchange/mailbox-migration/cutover-migration-to-office-365).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

Geschätzte Zeit bis zum Abschließen dieser Aufgabe: 2 bis 5 Minuten, um einen Migrationsbatch zu erstellen. Nach dem Start der Migration variiert die Dauer der Migration abhängig von der Anzahl von Postfächern in dem Batch, der Größe der einzelnen Postfächer und Ihrer verfügbaren Netzkapazität. Weitere Informationen zu anderen Faktoren, die sich auf die Dauer der Migration von Postfächern zu Microsoft 365 [auswirken,](/Exchange/mailbox-migration/office-365-migration-best-practices)finden Sie unter Migration Performance .

Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Berechtigungen, die Sie benötigen, finden Sie unter dem Eintrag „Migration" in einer Tabelle im Thema [Empfängerberechtigungen](/exchange/recipients-permissions-exchange-2013-help).

Um die Exchange Online-PowerShell-Cmdlets zu verwenden, müssen Sie angemeldet sein und die Cmdlets in Ihre lokale Windows PowerShell Sitzung importieren. Finden Sie Anweisungen unter[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShelll](/powershell/exchange/connect-to-exchange-online-powershell).

Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](/powershell/exchange/).

## <a name="migration-steps"></a>Migrationsschritte

### <a name="step-1-prepare-for-a-cutover-migration"></a>Schritt 1: Übernahmemigration vorbereiten
<a name="BK_Step1"> </a>

- **Fügen Sie Ihre lokale Exchange-Organisation als akzeptierte Domäne Ihrer Microsoft 365-Organisation hinzu.** Der Migrationsdienst verwendet die SMTP-Adresse Ihrer lokalen Postfächer, um die Microsoft Online Services-Benutzer-ID und E-Mail-Adresse für die neuen Microsoft 365-Postfächer zu erstellen. Die Migration wird fehlschlagen, wenn Ihre Exchange-Domäne keine akzeptierte Domäne oder die primäre Domäne Ihrer Microsoft 365-Organisation ist. Weitere Informationen finden Sie unter [Verify your domain](../admin/setup/add-domain.md).

- **Konfigurieren von Outlook Anywhere auf dem lokalen Exchange-Server** Der E-Mail-Migrationsdienst verwendet RPC über HTTP oder Outlook Anywhere, um eine Verbindung mit dem lokalen Exchange-Server herzustellen. Informationen zum Einrichten von Outlook Anywhere für Exchange 2010, Exchange 2007 und Exchange 2003 finden Sie unter den folgenden Themen:

  - [Exchange 2010: Aktivieren von Outlook Anywhere](/previous-versions/office/exchange-server-2010/bb123542(v=exchg.141))

  - [Exchange 2007: Aktivieren von Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))

  - [Exchange 2003: Bereitstellungsszenarien für RPC über HTTP](/previous-versions/tn-archive/bb124876(v=exchg.65))

  - [Konfigurieren von Outlook Anywhere mit Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))

    > [!IMPORTANT]
    > Die Outlook Anywhere-Konfiguration muss mit einem Zertifikat einer vertrauenswürdigen Zertifizierungsstelle konfiguriert werden. Outlook Anywhere kann nicht mit einem selbstsignierten Zertifikat konfiguriert werden. Weitere Informationen finden Sie unter [Konfigurieren von SSL für Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).

- **Sicherstellen, dass mit Outlook Anywhere eine Verbindung mit der Exchange-Organisation hergestellt werden kann** Sie können eine der folgenden Methoden verwenden, um die Verbindungseinstellungen zu testen:

  - Verwenden Sie Microsoft Outlook von außerhalb Ihre Firmennetzwerks, um eine Verbindung mit Ihrem lokalen Exchange-Postfach herzustellen.

  - Verwenden Sie die Microsoft [Exchange-Remoteverbindungsuntersuchung](https://www.testexchangeconnectivity.com/) zum Testen der Verbindungseinstellungen. Verwenden Sie die Outlook Anywhere- (RPC über HTTP)- oder Outlook-AutoErmittlungs-Tests.

  - Führen Sie die folgenden Befehle in Exchange Online PowerShell aus:

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

- **Zuweisen der erforderlichen Berechtigungen für das lokale Benutzerkonto für den Zugriff auf Postfächer in der Exchange-Organisation** Das lokale Benutzerkonto, mit dem Sie eine Verbindung mit Ihrer lokalen Exchange-Organisation herstellen (auch Migrationsadministrator genannt), muss über die erforderlichen Berechtigungen für den Zugriff auf die lokalen Postfächer verfügen, die Sie zu Microsoft 365 migrieren möchten. Dieses Benutzerkonto wird zur Erstellung eines Migrationsendpunkts zu Ihrer lokalen Organisation verwendet.

    Die folgende Liste zeigt die Administratorrechte an, die erforderlich sind, um Postfächer mithilfe einer Übernahmemigration zu migrieren. Es gibt drei mögliche Optionen.

  - Der Migrationsadministrator muss Mitglied der Gruppe **Domänen-Admins** in Active Directory in der lokalen Organisation sein.

    oder -

  - Dem Migrationsadministrator muss die Berechtigung **FullAccess** für jedes lokale Postfach zugewiesen werden.

    oder -

  - Dem Migrationsadministrator muss die Berechtigung **Receive As** für die lokale Postfachdatenbank zugewiesen werden, in der die Benutzerpostfächer gespeichert sind.

- **Deaktivieren von Unified Messaging** Wenn die zu migrierenden lokalen Postfächer für Unified Messaging (UM) aktiviert sind, müssen Sie vor der Migration UM in den Postfächern deaktivieren. Nach Abschluss der Migration können Sie UM dann für die Postfächer wieder aktivieren.

- **Sicherheitsgruppen und Stellvertretung** Der E-Mail-Migrationsdienst kann nicht erkennen, ob lokale Active Directory-Gruppen Sicherheitsgruppen sind oder nicht. Daher kann er keine migrierten Gruppen als Sicherheitsgruppen in Microsoft 365 bereitstellen. Wenn Sie Sicherheitsgruppen in Ihrem Microsoft 365-Mandanten haben möchten, müssen Sie zunächst eine leere E-Mail-aktivierte Sicherheitsgruppe in Ihrem Microsoft 365-Mandanten bereitstellen, bevor Sie mit der Umstellung beginnen. Zudem werden bei dieser Migrationsmethode nur Postfächer, E-Mail-Benutzer, E-Mail-Kontakte und E-Mail-aktivierte Gruppen verschoben. Wenn ein anderes Active Directory-Objekt, z. B. ein Benutzer, der nicht zu Microsoft 365 migriert wird, als Vorgesetzter oder Stellvertretung für ein migriertes Objekt zugewiesen ist, müssen sie vor der Migration aus dem Objekt entfernt werden.

### <a name="step-2-create-a-migration-endpoint"></a>Schritt 2: Migrationsendpunkt erstellen
<a name="BK_Step2"> </a>

Um E-Mails erfolgreich zu migrieren, muss Microsoft 365 eine Verbindung herstellen und mit dem Quell-E-Mail-System kommunizieren. Zu diesem Zwecke verwendet Microsoft 365 einen Migrationsendpunkt. Um einen Outlook Anywhere-Migrationsendpunkt für die Übernahmemigration zu erstellen, [stellen Sie zunächst eine Verbindung mit Exchange Online her](/powershell/exchange/connect-to-exchange-online-powershell).

Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](/powershell/exchange/).

Führen Sie die folgenden Befehle in Exchange Online PowerShell aus:

```powershell
$Credentials = Get-Credential
```

Dabei wird das Cmdlet [Test-MigrationServerAvailability](/powershell/module/exchange/test-migrationserveravailability) verwendet, um die Einstellungen für die Verbindung mit dem lokalen Exchange-Server abzurufen und zu testen. Anschließend werden diese Verbindungseinstellungen zum Erstellen des Migrationsendpunkts verwendet.

```powershell
$TSMA = Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress administrator@contoso.com -Credentials $credentials
```

```powershell
New-MigrationEndpoint -ExchangeOutlookAnywhere -Name CutoverEndpoint -ConnectionSettings $TSMA.ConnectionSettings
```

> [!NOTE]
> Beim Cmdlet **New-MigrationEndpoint** können Sie mit der Option **-TargetDatabase** eine von dem Dienst zu verwendende Datenbank angeben. Andernfalls wird nach dem Zufallsprinzip eine Datenbank aus dem Active Directory-Verbunddienste (AD FS) 2.0-Standort zugewiesen, in dem sich das Verwaltungspostfach befindet.

#### <a name="verify-it-worked"></a>Stellen Sie die Funktion sicher

Führen Sie den folgenden Befehl zum Anzeigen von Informationen zum Migrationsendpunkt „CutoverEndpoint“ in Exchange Online PowerShell aus:

```powershell
Get-MigrationEndpoint CutoverEndpoint | Format-List EndpointType,ExchangeServer,UseAutoDiscover,Max*

```

### <a name="step-3-create-the-cutover-migration-batch"></a>Schritt 3: Übernahmemigrationsbatch erstellen
<a name="BK_Step3"> </a>

Sie können das **New-MigrationBatch** -Cmdlet in Exchange Online PowerShell verwenden, um einen Migrationsbatch für eine Übernahmemigration zu erstellen. Sie können einen Migrationsbatch erstellen und diesen automatisch starten, indem Sie den _AutoStart_-Parameter verwenden. Alternativ können Sie den Migrationsbatch erstellen und später mithilfe des **Start-MigrationBatch** -Cmdlets manuell starten. In diesem Beispiel wird ein Migrationsbatch namens „CutoverBatch" erstellt und der im vorherigen Schritt erstellte Migrationsendpunkt verwendet.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint -AutoStart
```

In diesem Beispiel wird auch ein Migrationsbatch namens „CutoverBatch" erstellt und verwendet den Migrationsendpunkt, der im vorherigen Schritt erstellt wurde. Da der Parameter  _AutoStart_ nicht verwendet wird, muss der Migrationsbatch manuell im Migrationsdashboard gestartet werden oder mithilfe des **Start-MigrationBatch** -Cmdlets . Wie bereits erwähnt, kann immer nur ein Übernahmemigrationsbatch ausgeführt werden.

```powershell
New-MigrationBatch -Name CutoverBatch -SourceEndpoint CutoverEndpoint
```

#### <a name="verify-it-worked"></a>Stellen Sie die Funktion sicher

Um zu überprüfen, ob Sie erfolgreich einen Migrationsbatch für eine Übernahmemigration erstellt haben, führen Sie den folgenden Befehl in Exchange Online PowerShell aus, um Informationen zum neuen Migrationsbatch anzuzeigen:

```powershell
Get-MigrationBatch | Format-List
```

### <a name="step-4-start-the-cutover-migration-batch"></a>Schritt 4: Übernahmemigrationsbatch starten
<a name="BK_Step4"> </a>

Führen Sie in Exchange Online PowerShell den folgenden Befehl aus, um den Migrationsbatch zu starten. Dadurch wird ein Migrationsbatch namens „CutoverBatch“ erstellt.

```powershell
Start-MigrationBatch -Identity CutoverBatch
```

#### <a name="verify-it-worked"></a>Stellen Sie die Funktion sicher

Wenn ein Migrationsbatch erfolgreich gestartet wurde, lautet sein Status im Migrationsdashboard Synchronisierung. Führen Sie den folgenden Befehl aus, um zu überprüfen, ob ein Migrationsbatch erfolgreich mithilfe von Exchange Online PowerShell gestartet wurde:

```powershell
Get-MigrationBatch -Identity CutoverBatch |  Format-List Status
```

### <a name="step-5-route-your-email-to-microsoft-365"></a>Schritt 5: Route your email to Microsoft 365
<a name="BK_Step5"> </a>

E-Mail-Systeme verwenden einen als MX-Eintrag bezeichneten DNS-Eintrag, um zu ermitteln, wohin E-Mails gesendet werden sollen. Während der E-Mail-Migration hat Ihr MX-Eintrag auf Ihr Quell-E-Mail-System verwiesen. Nachdem die E-Mail-Migration zu Microsoft 365 abgeschlossen ist, ist es an der Zeit, Ihren MX-Eintrag auf Microsoft 365 zu verweisen. Dadurch wird sichergestellt, dass E-Mails an Ihre Microsoft 365-Postfächer zugestellt werden. Durch Verschieben des MX-Eintrags können Sie auch Ihr altes E-Mail-System deaktivieren, wenn Sie bereit sind.

Für viele DNS-Anbieter gibt es bestimmte Anweisungen zum Ändern des MX-Eintrags. Für den Fall, dass Ihr DNS-Anbieter nicht aufgeführt ist oder Sie eine Vorstellung von den allgemeinen Anweisungen erhalten möchten, werden auch [allgemeine Anweisungen für MX-Einträge](https://support.office.microsoft.com/article/7b7b075d-79f9-4e37-8a9e-fb60c1d95166#bkmk_add_mx) bereitgestellt.

Es kann bis zu 72 Stunden dauern, bis die E-Mail-Systeme der Kunden und Partnern den geänderten MX-Eintrag erkennen. Warten Sie mindestens 72 Stunden, bevor Sie mit dem nächsten Schritt fortfahren: [Schritt 6: Übernahmemigrationsbatch löschen](use-powershell-to-perform-a-cutover-migration-to-microsoft-365.md#Bk_step6).

### <a name="step-6-delete-the-cutover-migration-batch"></a>Schritt 6: Übernahmemigrationsbatch löschen
<a name="Bk_step6"> </a>

Nachdem Sie den MX-Eintrag geändert und überprüft haben, ob alle E-Mails an Microsoft 365-Postfächer geroutet werden, benachrichtigen Sie die Benutzer, dass ihre E-Mails an Microsoft 365 gesendet werden. Danach können Sie den Übernahmemigrationsbatch löschen. Überprüfen Sie Folgendes, bevor Sie den Migrationsbatch löschen.

- Alle Benutzer verwenden Microsoft 365-Postfächer. Nachdem der Batch gelöscht wurde, werden E-Mails, die an Postfächer in der lokalen Exchange Server gesendet werden, nicht in die entsprechenden Microsoft 365-Postfächer kopiert.

- Microsoft 365-Postfächer wurden mindestens einmal synchronisiert, nachdem E-Mails direkt an sie gesendet wurden. Stellen Sie dazu sicher, dass der Wert im Feld Letzte Synchronisierungszeit für den Migrationsbatch aktueller ist als der Wert, als E-Mails direkt an Microsoft 365-Postfächer geroutet wurden.

Führen Sie den folgenden Befehl aus, um den Migrationsbatch „CutoverBatch“ in Exchange Online PowerShell zu löschen:

```powershell
Remove-MigrationBatch -Identity CutoverBatch
```

### <a name="section-7-assign-user-licenses"></a>Abschnitt 7: Zuweisen von Benutzerlizenzen
<a name="BK_Step7"> </a>

 **Aktivieren Sie Microsoft 365-Benutzerkonten für die migrierten Konten, indem Sie Lizenzen zuweisen.** Wenn Sie keine Lizenz zuweisen, wird das Postfach nach Ablauf der Kulanzzeit (30 Tage) deaktiviert. Informationen zum Zuweisen einer Lizenz im Microsoft 365 Admin Center finden Sie unter [Assign or unassign licenses](../admin/manage/assign-licenses-to-users.md).

### <a name="step-8-complete-post-migration-tasks"></a>Schritt 8: Aufgaben nach der Migration abschließen
<a name="BK_Step8"> </a>

- **Erstellen Sie einen AutoErmittlung-DNS-Eintrag, damit Benutzer problemlos auf ihre Postfächer zugreifen können.** Nachdem alle lokalen Postfächer zu Microsoft 365 migriert wurden, können Sie einen AutoErmittlungs-DNS-Eintrag für Ihre Microsoft 365-Organisation konfigurieren, damit Benutzer problemlos eine Verbindung mit ihren neuen Microsoft 365-Postfächern mit Outlook und mobilen Clients herstellen können. Dieser neue AutoErmittlungs-DNS-Eintrag muss denselben Namespace verwenden, den Sie für Ihre Microsoft 365-Organisation verwenden. Wenn der Namespace für die Cloud-basierte Organisation beispielsweise "cloud.contoso.com" lautet, müssen Sie den DNS-Datensatz "autodiscover.cloud.contoso.com" für die AutoErmittlung erstellen.

    Wenn Sie Ihre Exchange Server behalten, sollten Sie auch sicherstellen, dass der #A0 für die AutoErmittlung nach der Migration sowohl im internen als auch im externen DNS auf Microsoft 365 verweisen muss, damit der #A1 eine Verbindung mit dem richtigen Postfach herstellen kann.

    > [!NOTE]
    >  In Exchange 2007, Exchange 2010 und Exchange 2013 sollten Sie auch  `Set-ClientAccessServer AutodiscoverInternalConnectionURI` auf `Null` festlegen.

    Microsoft 365 verwendet einen CNAME-Eintrag, um den AutoErmittlungsdienst für Outlook und mobile Clients zu implementieren. Der CNAME-Eintrag für die AutoErmittlung muss folgende Informationen enthalten:

  - **Alias:** autodiscover

  - **Ziel:** autodiscover.outlook.com

    Weitere Informationen finden Sie unter [Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

- **Nehmen Sie lokale Exchange-Server außer Betrieb.** Nachdem Sie überprüft haben, dass alle E-Mails direkt an die Microsoft 365-Postfächer geroutet werden und Sie ihre lokale E-Mail-Organisation nicht mehr verwalten müssen oder keine Implementierung einer Lösung für einmaliges Anmelden (Single Sign-On, SSO) planen, können Sie Exchange von Ihren Servern deinstallieren und Ihre lokale Exchange-Organisation entfernen.

    Weitere Informationen erhalten Sie unter den folgenden Themen:

  - [Ändern oder Entfernen von Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))

  - [Entfernen einer Exchange 2007-Organisation](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))

  - [Deinstallieren von Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))