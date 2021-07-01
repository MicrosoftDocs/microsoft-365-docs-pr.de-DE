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
description: Erfahren Sie, wie Sie Mithilfe von PowerShell Inhalte aus einem Quell-E-Mail-System im Laufe der Zeit mithilfe einer mehrstufigen Migration zu Microsoft 365 verschieben.
ms.openlocfilehash: 6a458f6164a842394ec87f59df11939a8c435ea2
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2021
ms.locfileid: "53229647"
---
# <a name="use-powershell-to-perform-a-staged-migration-to-microsoft-365"></a>Verwenden von PowerShell zum Ausführen einer mehrstufigen Migration zu Microsoft 365

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Mithilfe einer mehrstufigen Migration können Sie die Inhalte von Benutzerpostfächern von einem Quell-E-Mail-System in Microsoft 365 migrieren.

Dieser Artikel führt Sie durch die Aufgaben im Zusammenhang mit einer mehrstufigen E-Mail-Migration mit Exchange Online PowerShell. Das Thema, [was Sie über eine mehrstufige E-Mail-Migration wissen müssen,](/Exchange/mailbox-migration/what-to-know-about-a-staged-migration)bietet Ihnen einen Überblick über den Migrationsprozess. Wenn Sie mit dem Inhalt dieses Artikels vertraut sind, verwenden Sie ihn, um mit der Migration der Postfächer von einem E-Mail-System zu einem anderen zu beginnen.

> [!NOTE]
> Sie können auch mit der Exchange-Verwaltungskonsole eine mehrstufige Migration durchführen. Weitere Informationen finden Sie unter [Durchführen einer mehrstufigen Migration von E-Mails zu Microsoft 365.](/Exchange/mailbox-migration/perform-a-staged-migration/perform-a-staged-migration)

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

Geschätzte Zeit bis zum Abschließen dieser Aufgabe: 2 bis 5 Minuten, um einen Migrationsbatch zu erstellen. Nach dem Start der Migration variiert die Dauer der Migration abhängig von der Anzahl von Postfächern in dem Batch, der Größe der einzelnen Postfächer und Ihrer verfügbaren Netzkapazität. Weitere Informationen zu anderen Faktoren, die sich auf die Dauer der Migration von Postfächern zu Microsoft 365 auswirken, finden Sie unter ["Migrationsleistung".](/Exchange/mailbox-migration/office-365-migration-best-practices)

Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Berechtigungen, die Sie benötigen, finden Sie unter dem Eintrag "Migration" unter dem Thema [Empfängerberechtigungen](/exchange/recipients-permissions-exchange-2013-help).

Um die Exchange Online-PowerShell-Cmdlets zu verwenden, müssen Sie angemeldet sein und die Cmdlets in Ihre lokale Windows PowerShell Sitzung importieren. Finden Sie Anweisungen unter[Herstellen einer Verbindung mit Exchange Online mithilfe der Remote-PowerShelll](/powershell/exchange/connect-to-exchange-online-powershell).

Eine vollständige Liste der Migrationsbefehle finden Sie unter [Verschiebungs- und Migrations-Cmdlets](/powershell/exchange/).

## <a name="migration-steps"></a>Migrationsschritte

### <a name="step-1-prepare-for-a-staged-migration"></a>Schritt 1: Auf eine mehrstufige Migration vorbereiten

Bevor Sie Postfächer mithilfe einer mehrstufigen Migration zu Microsoft 365 migrieren, müssen Sie einige Änderungen an Ihrer Exchange Umgebung vornehmen.

 **Konfigurieren Sie Outlook Anywhere auf Ihrem lokalen Exchange Server**. Der E-Mail-Migrationsdienst verwendet Outlook Anywhere (auch bekannt als RPC über HTTP), um eine Verbindung mit Ihrem lokalen Exchange Server herzustellen. Informationen zum Einrichten von Outlook Anywhere für Exchange Server 2007 und Exchange 2003 finden Sie im Folgenden:

- [Exchange 2007: Aktivieren von Outlook Anywhere](/previous-versions/office/exchange-server-2007/bb123889(v=exchg.80))

- [Konfigurieren von Outlook Anywhere mit Exchange 2003](/previous-versions/office/exchange-server-2007/aa996922(v=exchg.80))

> [!IMPORTANT]
> Sie müssen ein Zertifikat verwenden, das von einer vertrauenswürdigen Zertifizierungsstelle (CA) mit Ihrer Outlook Anywhere-Konfiguration erstellt wurde. Outlook Anywhere kann nicht mit einem selbstsignierten Zertifikat konfiguriert werden. Weitere Informationen finden Sie unter [Konfigurieren von SSL für Outlook Anywhere](/previous-versions/office/exchange-server-2007/aa995982(v=exchg.80)).

 **Optional: Stellen Sie sicher, dass Sie eine Verbindung zu Ihrer Exchange Organisation mit Outlook Anywhere** herstellen können. Versuchen Sie eine der folgenden Methoden, um die Verbindungseinstellungen zu testen.

- Verwenden Sie Outlook von außerhalb des Unternehmensnetzwerks zur Verbindung mit Ihrem lokalen Exchange-Postfach.

- Verwenden Sie [microsoft Remote Connectivity Analyzer,](https://https://testconnectivity.microsoft.com/) um Ihre Verbindungseinstellungen zu testen. Verwenden Sie Outlook Anywhere (RPC über HTTP) oder Outlook AutoErmittlung-Tests.

- Führen Sie die folgenden Befehle in Exchange Online PowerShell aus:

  ```powershell
  $Credentials = Get-Credential
  ```

  ```powershell
  Test-MigrationServerAvailability -ExchangeOutlookAnywhere -Autodiscover -EmailAddress <email address for on-premises administrator> -Credentials $credentials
  ```

 **Festlegen von Berechtigungen** Das lokale Benutzerkonto, das Sie zum Herstellen einer Verbindung mit Ihrer lokalen Exchange Organisation (auch als Migrationsadministrator bezeichnet) verwenden, muss über die erforderlichen Berechtigungen verfügen, um auf die lokalen Postfächer zuzugreifen, die Sie zu Microsoft 365 migrieren möchten. Dieses Benutzerkonto wird verwendet, wenn Sie eine Verbindung mit Ihrem E-Mail-System herstellen, indem Sie später in diesem Verfahren einen Migrationsendpunkt erstellen ([Schritt 3: Erstellen eines Migrationsendpunkts).](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Endpoint)

Um die Postfächer zu migrieren, muss der Administrator eine der folgenden Berechtigungen haben:

- Ein Mitglied der **Domänen-Admins** -Gruppe in Active Directory in der lokalen Organisation sein.

    oder

- **FullAccess** -Berechtigung für jedes lokale Postfach und die **WriteProperty** -Berechtigung zum Ändern der **TargetAddress** -Eigenschaft für die lokale Benutzerkonten besitzen.

    oder

- Die **ReceiveAs** -Berechtigung für die lokale Postfachdatenbank besitzen, in der die Benutzerpostfächer gespeichert sind und die **WriteProperty** -Berechtigung besitzen, um die **TargetAddress** -Eigenschaft für die lokalen Benutzerkonten ändern zu können.

Anweisungen zum Festlegen dieser Berechtigungen finden Sie unter [Zuweisen von Berechtigungen zum Migrieren von Postfächern zu Microsoft 365.](/Exchange/mailbox-migration/assign-permissions-for-migration)

 **Deaktivieren von Unified Messaging (UM)** Wenn UM für die lokalen Postfächer aktiviert ist, die Sie migrieren, deaktivieren Sie UM vor der Migration. Aktivieren Sie UM für die Postfächer nach Abschluss der Migration. Weitere Anleitungen finden Sie unter [Deaktivieren von Unified Messaging](/previous-versions/office/exchange-server-2007/bb124691(v=exchg.80)).

 **Verwenden Sie die Verzeichnissynchronisierung, um neue Benutzer in Microsoft 365 zu erstellen.** Sie verwenden die Verzeichnissynchronisierung, um alle lokalen Benutzer in Ihrer Microsoft 365 Organisation zu erstellen.

Sie müssen die Benutzer nach der Erstellung lizenzieren. Sie haben 30 Tage zum Hinzufügen von Lizenzen, nachdem die Benutzer erstellt wurden. Weitere Informationen zum Hinzufügen von Lizenzen finden Sie unter [Schritt 8: Aufgaben nach der Migration abschließen](use-powershell-to-perform-a-staged-migration-to-microsoft-365.md#BK_Postmigration).

 Sie können entweder das Synchronisierungstool Microsoft Azure Active Directory (Azure AD) oder die Microsoft Azure AD-Synchronisierungsdienste verwenden, um Ihre lokalen Benutzer in Microsoft 365 zu synchronisieren und zu erstellen. Nachdem Postfächer zu Microsoft 365 migriert wurden, verwalten Sie Benutzerkonten in Ihrer lokalen Organisation und werden mit Ihrer Microsoft 365 Organisation synchronisiert. Weitere Informationen finden Sie unter [Verzeichnisintegration](/previous-versions/azure/azure-services/jj573653(v=azure.100)).

### <a name="step-2-create-a-csv-file-for-a-staged-migration-batch"></a>Schritt 2: Erstellen einer CSV-Datei für einen Batch der mehrstufigen Migration

Nachdem Sie die Benutzer identifiziert haben, deren lokale Postfächer Sie zu Microsoft 365 migrieren möchten, verwenden Sie eine CSV-Datei (Comma Separated Value), um einen Migrationsbatch zu erstellen. Jede Zeile in der CSV-Datei, die von Microsoft 365 zum Ausführen der Migration verwendet wird, enthält Informationen zu einem lokalen Postfach.

> [!NOTE]
> Es gibt keine Beschränkung für die Anzahl der Postfächer, die Sie mithilfe einer mehrstufigen Migration zu Microsoft 365 migrieren können. Die CSV-Datei für einen Migrationsbatch kann maximal 2.000 Zeilen enthalten. Erstellen Sie zum Migrieren von mehr als 2.000 Postfächern zusätzliche CSV-Dateien und verwenden Sie jede Datei, um einen neuen Migrationsbatch zu erstellen.

 **Unterstützte Attribute**

Die CSV-Datei für eine mehrstufige Migration unterstützt die folgenden drei Attribute. Jede Zeile der CSV-Datei entspricht einem Postfach und muss einen Wert für jedes dieser Attribute enthalten.

|**Attribut**|**Beschreibung**|**Erforderlich?**|
|:-----|:-----|:-----|
|EmailAddress  <br/> |Gibt die primäre SMTP-E-Mail-Adresse, z. B. pilarp@contoso.com für lokale Postfächer an.  <br/> Verwenden Sie die primäre SMTP-Adresse für lokale Postfächer und nicht für Benutzer-IDs aus dem Microsoft 365. Wenn die lokale Domäne beispielsweise contoso.com heißt, die Microsoft 365 E-Mail-Domäne jedoch service.contoso.com heißt, verwenden Sie den contoso.com Domänennamen für E-Mail-Adressen in der CSV-Datei.  <br/> |Erforderlich  <br/> |
|Kennwort  <br/> |Das Kennwort, das für das neue Microsoft 365 Postfach festgelegt werden soll. Alle Kennworteinschränkungen, die auf Ihre Microsoft 365 Organisation angewendet werden, gelten auch für die In der CSV-Datei enthaltenen Kennwörter.  <br/> |Optional  <br/> |
|ForceChangePassword  <br/> |Gibt an, ob ein Benutzer das Kennwort ändern muss, wenn er sich zum ersten Mal bei seiner neuen Microsoft 365 Postfach anmeldet. Verwenden Sie **True** oder **False** als Wert für diesen Parameter. <br/> > [!NOTE]> Wenn Sie eine Lösung für einmaliges Anmelden (SSO) durch die Bereitstellung von Active Directory-Verbunddiensten (AD FS) oder höher in Ihrer lokalen Organisation implementiert haben, verwenden Sie **False** als Wert für das Attribut **ForceChangePassword**.          |Optional  <br/> |

 **CSV-Dateiformat**

Das folgende Beispiel zeigt das Format der CSV-Datei. In diesem Beispiel werden drei lokale Postfächer zu Microsoft 365 migriert.

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

Um E-Mails erfolgreich zu migrieren, muss Microsoft 365 eine Verbindung mit dem Quell-E-Mail-System herstellen und mit diesem kommunizieren. Dazu verwendet Microsoft 365 einen Migrationsendpunkt. Zum Erstellen eines Migrationsendpunkts von Outlook Anywhere durch die Verwendung von PowerShell, für eine mehrstufige Migration, stellen Sie zuerst eine [Verbindung mit Exchange Online](/powershell/exchange/connect-to-exchange-online-powershell) her.

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

Nachdem Sie einen Batch Postfächer erfolgreich migriert haben, benötigen Sie eine Methode, damit die Benutzer auf ihre E-Mail zugreifen können. Ein Benutzer, dessen Postfach migriert wurde, verfügt jetzt sowohl über ein lokales Postfach als auch über ein Postfach in Microsoft 365. Benutzer, die über ein Postfach in Microsoft 365 verfügen, erhalten keine neuen E-Mails mehr in ihrem lokalen Postfach.

Da Sie nicht mit Ihren Migrationen fertig sind, können Sie noch nicht alle Benutzer an Microsoft 365 für ihre E-Mails weiterleiten. Was also tun Sie für diese Personen, die beide haben? Sie können die lokalen Postfächer ändern, die Sie bereits zu E-Mail-aktivierte Benutzer migriert haben. Wenn Sie von einem Postfach zu einem E-Mail-aktivierten Benutzer wechseln, können Sie den Benutzer an Microsoft 365 für seine E-Mails leiten, anstatt zum lokalen Postfach zu wechseln.

Ein weiterer wichtiger Grund für die Konvertierung von lokalen Postfächern in E-Mail-aktivierte Benutzer ist das Beibehalten von Proxyadressen aus den Microsoft 365 Postfächern durch Kopieren von Proxyadressen an die E-Mail-aktivierten Benutzer. So können Sie Cloud-basierte Benutzer mithilfe von Active Directory von der lokalen Organisation aus verwalten. Wenn Sie ihre lokale Exchange Server Organisation außer Betrieb nehmen möchten, nachdem alle Postfächer zu Microsoft 365 migriert wurden, verbleiben die Proxyadressen, die Sie in die E-Mail-aktivierten Benutzer kopiert haben, in Ihrem lokalen Active Directory.

### <a name="step-6-delete-a-staged-migration-batch"></a>Schritt 6: Löschen eines Batches für die mehrstufige Migration
<a name="BK_Endpoint"> </a>

 Nachdem alle Postfächer in einem Migrationsbatch erfolgreich migriert wurden und Sie die lokalen Postfächer im Batch in E-Mail-aktivierte Benutzer konvertiert haben, können Sie einen Batch der mehrstufigen Migration löschen. Stellen Sie sicher, dass E-Mails an die Microsoft 365 Postfächer im Migrationsbatch weitergeleitet werden. Wenn Sie einen Batch für die mehrstufige Migration löschen, bereinigt der Migrationsdienst alle zum Migrationsbatch gehörenden Datensätze und löscht den Migrationsbatch.

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

### <a name="step7-assign-licenses-to-microsoft-365-users"></a>Schritt 7: Zuweisen von Lizenzen zu Microsoft 365 Benutzern
<a name="BK_Endpoint"> </a>

Aktivieren Sie Microsoft 365 Benutzerkonten für die migrierten Konten, indem Sie Lizenzen zuweisen. Wenn Sie keine Lizenz zuweisen, wird das Postfach deaktiviert, sobald die Karenzzeit (30 Tage) endet. Informationen zum Zuweisen einer Lizenz im Microsoft 365 Admin Center finden Sie unter Zuweisen oder Aufheben der [Zuweisung von Lizenzen.](../admin/manage/assign-licenses-to-users.md)

### <a name="step-8-complete-post-migration-tasks"></a>Schritt 8: Aufgaben nach der Migration abschließen
<a name="BK_Postmigration"> </a>

- **Erstellen Sie einen AutoErmittlung-DNS-Eintrag, damit Benutzer problemlos auf ihre Postfächer zugreifen können.** Nachdem alle lokalen Postfächer zu Microsoft 365 migriert wurden, können Sie einen AutoErmittlungs-DNS-Eintrag für Ihre Microsoft 365 Organisation konfigurieren, damit Benutzer problemlos eine Verbindung mit ihren neuen Microsoft 365 Postfächern mit Outlook und mobilen Clients herstellen können. Dieser neue AutoErmittlungs-DNS-Eintrag muss denselben Namespace verwenden, den Sie für Ihre Microsoft 365 Organisation verwenden. Wenn der Namespace für die Cloud-basierte Organisation beispielsweise "cloud.contoso.com" lautet, müssen Sie den DNS-Datensatz "autodiscover.cloud.contoso.com" für die AutoErmittlung erstellen.

    Microsoft 365 verwendet einen CNAME-Eintrag, um den AutoErmittlungsdienst für Outlook und mobile Clients zu implementieren. Der CNAME-Eintrag für die AutoErmittlung muss folgende Informationen enthalten:

  - **Alias:** autodiscover

  - **Ziel:** autodiscover.outlook.com

    Weitere Informationen finden Sie unter [Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md)

- **Nehmen Sie lokale Exchange-Server außer Betrieb.** Nachdem Sie überprüft haben, dass alle E-Mails direkt an die Microsoft 365 Postfächer weitergeleitet werden, und Sie ihre lokale E-Mail-Organisation nicht mehr verwalten müssen oder nicht planen, eine SSO-Lösung zu implementieren, können Sie Exchange von Ihren Servern deinstallieren und Ihre lokale Exchange Organisation entfernen.

    Weitere Informationen erhalten Sie unter den folgenden Themen:

  - [Ändern oder Entfernen von Exchange 2010](/previous-versions/office/exchange-server-2010/ee332361(v=exchg.141))

  - [Entfernen einer Exchange 2007-Organisation](/previous-versions/office/exchange-server-2007/aa998313(v=exchg.80))

  - [Deinstallieren von Exchange Server 2003](/previous-versions/tn-archive/bb125110(v=exchg.65))
