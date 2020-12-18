---
title: Kundenschlüssel für Microsoft 365 auf Mandantenebene (öffentliche Vorschau)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/17/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Hier erfahren Sie, wie Sie den Kundenschlüssel für alle Daten in Ihrem Microsoft 365-Mandanten einrichten.
ms.openlocfilehash: eedf0e8c9d56131016bc798af8ae471df3005bdc
ms.sourcegitcommit: 0867495cb02d0b38b439b16bdce97e6eda483ba9
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/18/2020
ms.locfileid: "49712525"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>Übersicht über den Kundenschlüssel für Microsoft 365 auf Mandantenebene (öffentliche Vorschau)

Mithilfe von von Ihnen bereitgestellten Schlüsseln können Sie eine Daten Verschlüsselungsrichtlinie (Data Encryption Policy, DEP) erstellen und dem Mandanten zuweisen. Die DEP verschlüsselt Daten für den gesamten Mandanten für diese Arbeitslasten:

- Chatnachrichten in Microsoft Teams (1:1 Chats, Gruppenchats, Besprechungs Chats und Kanal Unterhaltungen)
- Teams-Medien Nachrichten (Bilder, Codeausschnitte, Videos, wiki-Bilder)
- Im Microsoft Teams-Speicher gespeicherte Teams-Anruf-und Besprechungsaufzeichnungen
- Chat Benachrichtigungen für Teams
- Vorschläge für Microsoft Teams Chat von Cortana
- Statusmeldungen für Teams
- Benutzer-und Signalinformationen für Exchange Online

Für Microsoft Teams verschlüsselt der Kundenschlüssel auf Mandantenebene neue Daten ab dem Zeitpunkt, zu dem die DEP dem Mandanten zugewiesen ist. In der öffentlichen Vorschau wird das Verschlüsseln vergangener Daten nicht unterstützt. Für Exchange Online verschlüsselt der Kundenschlüssel alle vorhandenen und neuen Daten.

Sie können mehrere DEPs pro Mandanten erstellen, können jedoch nur eine DEP zu einem beliebigen Zeitpunkt zuweisen. Wenn Sie die Datenausführungsverhinderung zuweisen, beginnt die Verschlüsselung automatisch, kann jedoch je nach Größe des Mandanten einige Zeit in Anspruch nehmen.

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>Richtlinien auf Mandantenebene Hinzufügen eines umfassenderen Steuerelements zum Kundenschlüssel für Microsoft 365

Wenn Sie bereits einen Kundenschlüssel für Exchange Online und SharePoint Online eingerichtet haben, erfahren Sie hier, wie die neue öffentliche Vorschau auf Mandantenebene in passt.

Die von Ihnen erstellte Verschlüsselungsrichtlinie auf Mandantenebene verschlüsselt alle Daten für die Microsoft Teams-und Exchange Online-Arbeitslasten in Microsoft 365. Diese Richtlinie stört nicht die fein abgestimmten DEPs, die Sie bereits im Kundenschlüssel erstellt haben.

Beispiele:

Microsoft Teams-Dateien und einige Teams-Anruf-und Besprechungsaufzeichnungen, die in OneDrive für Unternehmen und SharePoint gespeichert sind, werden durch eine SharePoint Online DEP verschlüsselt. Eine einzelne SharePoint Online DEP verschlüsselt Inhalte innerhalb eines einzelnen Geo. Die DEP der Mandantenebene verschlüsselt die verschlüsselten Daten erneut mit der neuen Richtlinie.

Für Exchange Online können Sie eine Datenausführungsverhinderung erstellen, mit der ein oder mehrere Benutzerpostfächer mit dem Kundenschlüssel verschlüsselt werden. Wenn Sie eine Richtlinie auf Mandantenebene erstellen, werden die verschlüsselten Postfächer von dieser Richtlinie nicht verschlüsselt. Der Schlüssel auf Mandantenebene verschlüsseln jedoch die Postfächer, die von einer Datenausführungsverhinderung noch nicht betroffen sind.

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>Einrichten des Kunden Schlüssels auf Mandantenebene (öffentliche Vorschau)

Diese Schritte sind ähnlich, aber nicht identisch mit den Schritten zum Einrichten von Kundenschlüssel auf Anwendungsebene. Sie sollten diese öffentliche Vorschau nur mit Testdaten in Testmandanten verwenden. Verwenden Sie diese Version nicht mit Produktionsdaten oder in Ihrer Produktionsumgebung. Wenn Sie bereits über eine Produktionsbereitstellung von Kundenschlüssel verfügen, führen Sie die folgenden Schritte aus, um den Kundenschlüssel auf Mandantenebene in einer Testumgebung einzurichten.

Die meisten dieser Aufgaben werden durch eine Remoteverbindung mit Azure PowerShell abgeschlossen. Um optimale Ergebnisse zu erzielen, sollten Sie Version 4.4.0 oder höher von Azure PowerShell verwenden.

Stellen Sie vor dem ersten Start Folgendes sicher:

- Sie müssen ein Arbeits-oder Schulkonto verwenden, das über die Administratorrolle "Compliance" verfügt, um den Kundenschlüssel auf Mandantenebene einzurichten.
- Stellen Sie sicher, dass Sie über die entsprechende Lizenzierung für Ihre Organisation verfügen. Verwenden eines kostenpflichtigen, in Rechnung gestellten Azure-Abonnements mithilfe eines Enterprise-Vertrags oder eines Cloud-Dienstanbieters. Azure-Abonnements, die mit Pay as you go-Plänen oder mit einer Kreditkarte erworben wurden, werden für den Kundenschlüssel nicht unterstützt. Ab dem 1. April 2020 wird der Kundenschlüssel in Office 365 in Office 365 E5, M365 E5, M365 E5 Compliance und M365 E5 Information Protection & Governance-SKUs angeboten. Office 365 Advanced Compliance SKU steht nicht mehr für die Beschaffung neuer Lizenzen zur Verfügung. Vorhandene Office 365 Advanced Compliance-Lizenzen werden weiterhin unterstützt. Während der Dienst mit mindestens einer Lizenz unter dem Mandanten mit der entsprechenden Lizenz aktiviert werden kann, sollten Sie dennoch sicherstellen, dass alle Benutzer, die vom Dienst profitieren, über entsprechende Lizenzen verfügen. Sie benötigen eine der folgenden Lizenzen:

### <a name="create-two-new-azure-subscriptions"></a>Zwei neue Azure-Abonnements erstellen

Für Customer Key sind zwei Schlüssel für jede Daten- Verschlüsselungsrichtlinie (DEP) erforderlich. Um dies zu erreichen, müssen Sie zwei Azure-Abonnements erstellen. Als bewährte Methode empfiehlt Microsoft, dass separate Mitglieder Ihrer Organisation jeweils einen Schlüssel für jedes Abonnement konfigurieren. Verwenden Sie diese Azure-Abonnements nur zum Verwalten von Verschlüsselungsschlüsseln für Microsoft 365. Auf diese Weise ist Ihre Organisation geschützt, falls einer ihrer Betreiber versehentlich, absichtlich oder in böswilliger Absicht die Schlüssel, für die Sie verantwortlich sind, löscht oder auf andere Weise unsachgemäß handhabt.

Es gibt praktisch keine Beschränkung hinsichtlich der Anzahl von Azure-Abonnements, die Sie für Ihre Organisation erstellen können. Anhand dieser bewährten Vorgehensweise können Sie die Auswirkungen menschlicher Fehler minimieren und gleichzeitig die vom Kundenschlüssel verwendeten Ressourcen verwalten.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Azure- Abonnements registrieren, um einen obligatorischen Aufbewahrungszeitraum zu nutzen.

Der vorübergehende oder dauerhafte Verlust von Stamm Verschlüsselungsschlüsseln kann störend oder sogar katastrophal für den Dienstbetrieb sein und zu Datenverlusten führen. Aus diesem Grund ist für die mit Customer Key verwendeten Ressourcen ein starker Schutz erforderlich. Alle Azure-Ressourcen, die mit Customer Key verwendet werden, bieten Schutzmechanismen, die weit über die Standardkonfiguration hinaus gehen. Azure-Abonnements können derart gekennzeichnet oder registriert werden, dass eine sofortige und unwiderrufliche Kündigung vermieden wird. Dies wird als Registrierung eines obligatorischen Aufbewahrungszeitraums bezeichnet. Die erforderlichen Schritte zum Registrieren von Azure-Abonnements für einen obligatorischen Aufbewahrungszeitraum erfordern die Zusammenarbeit mit Microsoft. Dieser Vorgang kann bis zu fünf Arbeitstage dauern. Bisher wurde diese Funktion zeitweise als „Nicht kündigen" bezeichnet.
  
Bevor Sie sich an das Microsoft 365-Team wenden, müssen Sie für jedes Azure-Abonnement, das Sie mit dem Kundenschlüssel verwenden, die folgenden Schritte ausführen. Stellen Sie sicher, dass das [Azure PowerShell AZ](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) -Modul installiert ist, bevor Sie beginnen.

1. Melden Sie sich mit Azure PowerShell an. Anweisungen finden Sie unter [Anmelden mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Führen Sie das Register-AzProviderFeature-Cmdlet aus, um Ihre Abonnements für die Verwendung eines obligatorischen Aufbewahrungszeitraums zu registrieren. Führen Sie diese Aktion für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Wenden Sie sich an Microsoft, damit der Prozess bei [m365ck@Microsoft.com](mailto:m365ck@microsoft.com)abgeschlossen ist. Teilen Sie uns in Ihrem E-Mail bitte Folgendes mit:

   **Betreff**: Kundenschlüssel für \<*Your tenant's fully-qualified domain name*\>

   **Textkörper**: Abonnements-IDs, für die Sie einen obligatorischen Aufbewahrungszeitraum verbindlich festlegen möchten.
   Die Ausgabe von Get-AzProviderFeature für jedes Abonnement.

   Die Service-Level-Vereinbarung (Service Level Agreement, SLA) für den Abschluss dieses Vorgangs beläuft sich auf fünf Werktage, nachdem Microsoft benachrichtigt wurde (und überprüft hat, dass Sie Ihre Abonnements für die Nutzung eines obligatorischen Aufbewahrungszeitraums registriert haben).

4. Nachdem Sie eine Benachrichtigung von Microsoft erhalten haben, dass die Registrierung abgeschlossen ist, überprüfen Sie den Status Ihrer Registrierung, indem Sie den Befehl Get-AzProviderFeature wie folgt ausführen. Wenn der Befehl Get-AzProviderFeature überprüft wird, wird der Wert von **registered** für die Eigenschaft **Registrierungsstatus** zurückgegeben. Führen Sie diese Aktion für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Führen Sie den Befehl Register-AzResourceProvider aus, um den Vorgang abzuschließen. Führen Sie diese Aktion für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Erstellen eines Premium Azure Key Vault für jedes Abonnement

Die Schritte zum Erstellen eines Schlüssel Tresors sind in ["erste Schritte mit Azure Key Vault"](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)dokumentiert, das Sie durch das Installieren und Ingangsetzen von Azure PowerShell, das Herstellen einer Verbindung mit Ihrem Azure-Abonnement, das Erstellen einer Ressourcengruppe und das Erstellen eines Schlüsseltresors in dieser Ressourcengruppe führt.
  
Wenn Sie einen Schlüsseltresor erstellen, müssen Sie eine SKU auswählen: entweder Standard oder Premium. Die Standard-SKU ermöglicht das Schützen von Azure Key Vault-Schlüsseln mittels Software – es gibt keinen Schlüsselschutz mittels eines Hardware-Sicherheitsmoduls (HSM) – und die Premium-SKU ermöglicht die Verwendung von Hardware-Sicherheitsmodulen zum Schutz von Key-Vault-Schlüsseln. Customer Key akzeptiert Schlüsseltresore mit jeder SKU, wobei Microsoft dringend empfiehlt, nur die Premium-SKU zu verwenden. Die Betriebskosten mit Schlüsseln eines der beiden Typen sind identisch. Der einzige Unterschied bei den Kosten sind die monatlichen Kosten für jeden HSM-geschützten Schlüsseln. Detailinformationen finden Si unter [Key Vault-Preise](https://azure.microsoft.com/pricing/details/key-vault/).
  
> [!IMPORTANT]
> Verwenden Sie die Premium-SKU-Schlüsseltresore und HSM-geschützten Schlüssel für Produktionsdaten, und verwenden Sie nur standardmäßige SKU-Schlüsseltresore und Schlüssel für Tests und Überprüfungen.

Verwenden Sie ein allgemeines Präfix für Schlüssel Tresore, und geben Sie eine Abkürzung für die Verwendung und den Bereich des Schlüssel Tresors und der Schlüssel ein. Beispielsweise ist für den Contoso-Dienst, in dem sich die Tresore in Nordamerika befinden, ein möglicher paar von Namen contoso-O365-na-VaultA1 und Contoso-O365-na-VaultA2. In Azure sind Tresornamen global eindeutige Zeichenfolgen, daher müssen Sie möglicherweise Variationen Ihrer gewünschten Namen ausprobieren, falls die gewünschten Namen bereits von anderen Azure-Kunden beansprucht werden. Nach der Konfiguration können Tresor Namen nicht geändert werden, daher besteht die bewährte Methode darin, einen schriftlichen Plan für das Setup zu haben und eine zweite Person zu verwenden, um zu überprüfen, ob der Plan ordnungsgemäß ausgeführt wird.

Erstellen Sie Ihre Depots nach Möglichkeit in nicht-gekoppelten Regionen. Gekoppelte Azure-Regionen bieten eine hohe Verfügbarkeit über Dienstausfall-Domänen hinweg. Dementsprechend können regionale Paare gegenseitig als Backup-Region der jeweils anderen betrachtet werden. Dies bedeutet, dass eine Azure-Ressource, die in einer bestimmten Region platziert ist, durch die gekoppelte Region automatisch an Fehlertoleranz gewinnt. Aus diesem Grund bedeutet das Auswählen von Regionen für zwei Tresore, die in einer Daten Verschlüsselungsrichtlinie verwendet werden, in der die Regionen gekoppelt sind, dass nur insgesamt zwei Verfügbarkeits Regionen verwendet werden. In den meisten geografischen Regionen gibt es nur zwei Regionen, weshalb es noch nicht möglich ist, nicht-gekoppelte Regionen auszuwählen. Wählen Sie nach Möglichkeit zwei nicht gepaarte Bereiche für die beiden Tresore aus, die mit einer Daten Verschlüsselungsrichtlinie verwendet werden. Dies hat den positiven Effekt, dass insgesamt vier verfügbare Regionen genutzt werden. Weitere Informationen hierzu sowie ein aktuelles Verzeichnis der Regionenpaare finden Sie unter [Geschäftskontinuität und Notfallwiederherstellung (Business continuity and disaster recovery, BCDR): Gekoppelte Regionen in Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions).

### <a name="assign-permissions-to-each-key-vault"></a>Zuweisen von Berechtigungen für jeden Schlüsseltresor (Key Vault)

Sie müssen für jeden Schlüsseltresor entsprechend der von Ihnen gewählten Implementierung drei gesonderte Berechtigungsgruppen für Customer Key definieren. Sie müssen beispielsweise eine Berechtigungsgruppe für jede der folgenden Optionen definieren:
  
- **Schlüsseltresor-Administratoren**, deren Aufgabe das tägliche Verwalten Ihrer Schlüsseltresore für Ihre Organisation ist. Zu diesen Aufgaben gehören Datensicherung sowie Erstellen, Abrufen, Importieren, Auflisten und Wiederherstellen.

  > [!IMPORTANT]
  > Die Berechtigungsgruppe, die Schlüsseltresor-Administratoren zugewiesen ist, beinhaltet keine Berechtigung zum Löschen von Schlüsseln. Dies ist beabsichtigt und eine wichtige Vorgehensweise. Kryptografische Schlüssel werden normalerweise nicht gelöscht, da dadurch Daten dauerhaft vernichtet werden. Eine bewährte Methode besteht darin, den Schlüsseltresor-Administratoren diese Berechtigung nicht standardmäßig zuzuweisen. Behalten Sie stattdessen diese Berechtigung den Schlüsseltresor-Mitwirkenden vor und weisen Sie diese einem Administrator nur kurzfristig und lediglich, sofern die damit verbundenen Folgen klar verstanden wurden, zu.
  
  Um diese Berechtigungen einem Benutzer in Ihrer Organisation zuzuweisen, melden Sie sich bei Ihrem Azure-Abonnement mit Azure PowerShell an. Anweisungen finden Sie unter [Anmelden mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

   Führen Sie das Set-AzKeyVaultAccessPolicy-Cmdlet aus, um die erforderlichen Berechtigungen zuzuweisen.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Beispiel:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Schlüsseltresor-Mitwirkenden**, die Berechtigungen für den Azure Key Vault selbst ändern können. Sie müssen diese Berechtigungen ändern, wenn Mitarbeiter ihr Team verlassen oder Ihrem Team beitreten, oder in der seltenen Situation, dass die Key Vault-Administratoren berechtigterweise die Berechtigung zum Löschen oder Wiederherstellen eines Schlüssels benötigen. Dieser Gruppe von Schlüsseltresor-Mitwirkenden muss die Rolle Mitwirkender für Ihren Schlüsseltresor zugewiesen werden. Sie können diese Rolle mithilfe des Azure-Ressourcenmanagers zuweisen. Ausführliche Anweisungen finden Sie unter [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) , um den Zugriff auf Ihre Azure-Abonnement Ressourcen zu verwalten. Der Administrator, der ein Abonnement erstellt, verfügt standardmäßig über diesen Zugriff und die Möglichkeit, anderen Administratoren der Rolle "Contributor" zuzuweisen.

- **Microsoft 365-Daten im Rest-Verschlüsselungsdienst** , der die Arbeit des Kunden Schlüssels auf Mandantenebene ausführt. Führen Sie das Cmdlet " **AzKeyVaultAccessPolicy** " mit der folgenden Syntax aus, um die Berechtigung für Microsoft 365 zu erteilen:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  Dabei gilt Folgendes:

  - *Vault Name* ist der Name des Schlüssel Tresors, den Sie erstellt haben.

  Beispiel: für den Microsoft 365 Data at Rest-Verschlüsselungsdienst ersetzen Sie die  *Microsoft 365* -Webanwendung durch `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Aktivieren und Bestätigen des vorläufigen Löschens in Ihren Schlüsseltresoren

Wenn Sie Ihre Schlüssel schnell wiederherstellen können, ist ein umfassender Dienstausfalls aufgrund von versehentlich oder in böswilliger Absicht gelöschten Schlüsseln weniger wahrscheinlich. Aktivieren Sie diese Konfiguration, die als "Soft Delete" bezeichnet wird, bevor Sie Ihre Schlüssel mit dem Kundenschlüssel verwenden können. Das Aktivieren von Soft Delete ermöglicht Ihnen des Wiederherstellen von Schlüsseln oder Tresoren innerhalb von 90 Tagen nach dem Löschen, ohne diese aus der Datensicherung wiederherstellen zu müssen.
  
Führen Sie die folgenden Schritte aus, um Soft Delete für Ihre Schlüsseltresore zu aktivieren:
  
1. Melden Sie sich bei Ihrem Azure-Abonnement mit Windows PowerShell an. Anweisungen finden Sie unter [Anmelden mit Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Führen Sie das Cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) aus. In diesem Beispiel ist *Vault Name* der Name des Schlüssel Tresors, für den Sie Soft Delete aktivieren:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Bestätigen Sie, dass Soft Delete für den schlüsseltresor konfiguriert ist, indem Sie das Cmdlet **Get-AzKeyVault** ausführen. Wenn Soft Delete ordnungsgemäß für den schlüsseltresor konfiguriert ist, gibt die _Soft Delete Enabled_ -Eigenschaft den Wert " **true**" zurück:

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Hinzufügen eines Schlüssels zu jedem Schlüsseltresor durch das Erstellen oder Importieren eines Schlüssels

Es gibt zwei Methoden zum Hinzufügen von Schlüsseln zu einem Azure Key Vault. Sie können entweder direkt im Schlüsseltresor einen Schlüssel erstellen oder aber einen Schlüssel importieren. Das Erstellen eines Schlüssels direkt im Schlüsseltresor ist die einfachere Methode, während der Import eines Schlüssels die vollständige Kontrolle über die Generierung des Schlüssels bietet. Verwenden Sie die RSA-Schlüssel. Azure Key Vault unterstützt das Umbrechen und entpacken mit elliptischen Kurven Tasten nicht.
  
Um einen Schlüssel direkt in Ihrem schlüsseltresor zu erstellen, führen [Sie das Add-AzKeyVaultKey-](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) Cmdlet wie folgt aus:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Dabei gilt Folgendes:

- *Vault Name* ist der Name des Schlüssel Tresors, in dem Sie den Schlüssel erstellen möchten.

- *Key Name* ist der Name, den Sie dem neuen Schlüssel zuweisen möchten.

  > [!TIP]
  > Benennen Sie Schlüssel, die eine ähnliche Benennungskonvention verwenden, nach dem oben für Schlüsseltresore beschriebenen Verfahren. Auf diese Weise ist die Zeichenfolge in Tools, die lediglich den Schlüsselnamen anzeigen, selbsterklärend.
  
Wenn Sie den Schlüssel mit einem HSM schützen möchten, stellen Sie sicher, dass Sie **HSM** als Wert des Parameters _Destination_ angeben, andernfalls geben Sie **Software** an.

Beispiel:
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>Überprüfen der Wiederherstellungsebene Ihrer Schlüssel

Microsoft 365 erfordert, dass das Azure Key Vault-Abonnement auf nicht abbrechen festgelegt ist und dass für die Schlüssel, die von Kunden Schlüsseln verwendet werden, Soft Delete aktiviert ist. Sie können dies sicherstellen, indem Sie die Wiederherstellungsstufe für Ihre Schlüssel überprüfen.
  
Um die Wiederherstellungsebene eines Schlüssels zu überprüfen, führen Sie in Azure PowerShell das Get-AzKeyVaultKey-Cmdlet wie folgt aus:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Wenn die _Wiederherstellungsebene_ einen anderen Wert als "wieder **herstellbare + ProtectedSubscription**" zurückgibt, müssen Sie diesen Artikel lesen und sicherstellen, dass Sie alle Schritte zum Setzen des Abonnements in der Liste "nicht abbrechen" und "Soft Delete" in jedem schlüsseltresor aktiviert haben. Als nächstes senden Sie einen Screenshot der Ausgabe von `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in e-Mail an m365ck@Microsoft.com.

### <a name="back-up-azure-key-vault"></a>Sichern von Azure Key Vault

Unmittelbar nach dem Erstellen oder Ändern eines Schlüssels, dem Durchführen einer Sicherung und dem Speichern von Kopien der Sicherung, sowohl online als auch offline. Verbinden Sie keine Offlinekopien mit einem Netzwerk. Speichern Sie Sie stattdessen in einer physischen sicheren oder kommerziellen Speichereinrichtung. Mindestens eine Kopie der Sicherung sollte an einem Speicherort gespeichert sein, auf den im Fall eines Notfalls zugegriffen werden kann. Die einzelnen Sicherungen sind die einzige Möglichkeit zum Wiederherstellen des Schlüsselmaterials, sollte ein Key-Vault-Schlüssel dauerhaft vernichtet oder auf andere Weise funktionsuntüchtig gemacht worden sein. Schlüssel, die sich außerhalb des Azure Key Vault befinden und in Azure Key Vault importiert wurden, sind als Sicherung nicht geeignet, da die Metadaten, die für die Verwendung des Schlüssels mit Customer Key erforderlich sind, mit dem externen Schlüssel nicht vorhanden sind. Nur eine vom Azure Key Vault erstellte Sicherung kann für Wiederherstellungsvorgänge mit Customer Key verwendet werden. Daher ist es wichtig, dass Sie eine Sicherung des Azure Key Vault durchführen, sobald ein Schlüssel hochgeladen oder erstellt wurde.
  
Um eine Sicherung eines Azure Key-Tresor Schlüssels zu erstellen, führen Sie das Cmdlet [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) wie folgt aus:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Stellen Sie sicher, dass Ihre Ausgabedatei das Suffix verwendet `.backup` .
  
Die aus diesem Cmdlet resultierende Ausgabedatei ist verschlüsselt und kann außerhalb von Azure Key Vault nicht verwendet werden. Die Sicherung kann nur für das Azure-Abonnement wiederhergestellt werden, aus dem die Sicherung erstellt wurde.
  
Beispiel:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Konfigurationseinstellungen von Azure Key Vault verifizieren

Das Durchführen der Überprüfung vor der Verwendung von Schlüsseln in einer Datenverschlüsselungsrichtlinie (DEP) ist optional, wird jedoch dringend empfohlen. Insbesondere, wenn Sie andere als die in diesem Artikel beschriebenen Schritte zum Einrichten Ihrer Schlüssel und Tresore verwenden, sollten Sie den Sicherheitsstatus Ihrer Azure Key Vault-Ressourcen überprüfen, bevor Sie Customer Key konfigurieren.
  
Überprüfen, ob für Ihre Schlüssel die Funktionen „Abrufen“, „WrapKey“ und „unWrapKey“ aktiviert sind:
  
Führen Sie das Cmdlet [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) wie folgt aus:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Suchen Sie in der Ausgabe nach der Zugriffsrichtlinie und der Microsoft 365-APP-ID (GUID) nach Bedarf. Alle drei Vorgänge, Get, wrapKey und unwrapKey, müssen unter Berechtigungen für Keys angezeigt werden.
  
Wenn die Konfiguration der Zugriffsrichtlinie falsch ist, führen Sie das Set-AzKeyVaultAccessPolicy-Cmdlet wie folgt aus:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

Beispiel: für den Microsoft 365 Data at Rest-Verschlüsselungsdienst ersetzen Sie die  *Microsoft 365* -Webanwendung durch `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

Führen Sie das [Get-AzKeyVaultKey-](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) Cmdlet wie folgt aus, um zu überprüfen, ob für Ihre Schlüssel ein Ablaufdatum festgelegt wurde:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Ein abgelaufener Schlüssel kann nicht vom Kundenschlüssel verwendet werden, und Vorgänge, die mit einem abgelaufenen Schlüssel versucht werden, schlagen fehl und führen möglicherweise zu einem Dienstausfall. Es wird dringend empfohlen, dass mit Customer Key verwendete Schlüssel kein Ablaufdatum aufweisen. Ein einmal festgelegtes Ablaufdatum kann nicht gelöscht werden, es kann jedoch eine Datumänderung vorgenommen werden. Wenn ein Schlüssel verwendet werden muss, für den ein Ablaufdatum festgelegt ist, ändern Sie bitte das Ablaufdatum auf 31.12.9999. Schlüssel mit einem Ablaufdatum, das auf ein anderes Datum als 12/31/9999 festgelegt ist, werden nicht von der Microsoft 365-Validierung übergeben.
  
Um ein Ablaufdatum zu ändern, das auf einen anderen Wert als 12/31/9999 festgelegt wurde, führen Sie das Cmdlet [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) wie folgt aus:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Abrufen eines URI für jeden Azure Key Vault-Schlüssel

Nachdem Sie alle Schritte in Azure abgeschlossen haben, um die Schlüsseldepots einzurichten und die Schlüssel hinzugefügt haben, führen Sie den folgenden Befehl aus, um den URI für den Schlüssel in jedem schlüsseltresor abzurufen. Sie müssen diese URI verwenden, wenn Sie in weiterer Folge die einzelnen Datenverschlüsselungsrichtlinien (DEP) erstellen und zuweisen, also speichern Sie diese Informationen an einem sicheren Ort. Denken Sie daran, diesen Befehl jeweils für jeden Schlüsseltresor einmal auszuführen.
  
In Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>Einrichten der Kundenschlüssel-Verschlüsselungsrichtlinie für Ihren Mandanten

Sie müssen Berechtigungen zugewiesen haben, bevor Sie diese Cmdlets ausführen können. In diesem Artikel werden zwar alle Parameter für die Cmdlets aufgelistet, aber Sie haben möglicherweise keinen Zugriff auf einige Parameter, wenn Sie nicht in den Ihnen zugewiesenen Berechtigungen enthalten sind. Wie Sie herausfinden, welche Berechtigungen zur Ausführung eines bestimmten Cmdlets oder Parameters in Ihrer Organisation erforderlich sind, können Sie unter [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions) nachlesen.

### <a name="create-policy"></a>Richtlinie erstellen

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

Beschreibung: Aktivieren Sie Compliance-Administrator, um eine neue Daten Verschlüsselungsrichtlinie (DEP) mit zwei AKV-Stamm Schlüsseln zu erstellen. Sobald eine Richtlinie erstellt wurde, kann Sie mit Set-M365DataAtRestEncryptionPolicy-Cmdlet zugewiesen werden. Bei der ersten Zuweisung von Schlüsseln oder nach dem Drehen von Schlüsseln kann es bis zu 24 Stunden dauern, bis die neuen Tasten wirksam werden. Wenn die neue DEP mehr als 24 Stunden in Anspruch nimmt, wenden Sie sich an Microsoft.

Beispiel:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

Parameter:

| Name | Beschreibung | Optional (j/N) |
|--|--|--|
|Name|Anzeigename der Daten Verschlüsselungsrichtlinie|N|
|AzureKeyIDs|Gibt zwei URI-Werte der Azure Key-Tresorschlüssel an, die durch ein Komma getrennt sind, um Sie der Daten Verschlüsselungsrichtlinie zuzuordnen.|N|
|Beschreibung|Beschreibung der Daten Verschlüsselungsrichtlinie|N|

### <a name="assign-policy"></a>Richtlinie zuweisen

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

Beschreibung: Dieses Cmdlet wird zum Konfigurieren der Standardrichtlinie für Datenverschlüsselung verwendet. Diese Richtlinie wird verwendet, um Daten für alle Unterstützungs Arbeitslasten zu verschlüsseln. 

Beispiel:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

Parameter:
| Name | Beschreibung | Optional (j/N) |
|--|--|--|
-Richtlinie|Gibt die Daten Verschlüsselungsrichtlinie an, die zugewiesen werden muss. Geben Sie entweder den Richtliniennamen oder die Richtlinien-ID an.|N|

### <a name="modify-or-refresh-policy"></a>Richtlinie ändern oder aktualisieren

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

Beschreibung: das Cmdlet kann entweder zum Ändern oder Aktualisieren einer vorhandenen Richtlinie verwendet werden. Es kann auch verwendet werden, um eine Richtlinie zu aktivieren oder zu deaktivieren. Bei der ersten Zuweisung von Schlüsseln oder nach dem Drehen von Schlüsseln kann es bis zu 24 Stunden dauern, bis die neuen Tasten wirksam werden. Wenn die neue DEP mehr als 24 Stunden in Anspruch nimmt, wenden Sie sich an Microsoft.

Beispiele:

Deaktivieren Sie eine Daten Verschlüsselungsrichtlinie.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

Aktualisieren einer Daten Verschlüsselungsrichtlinie.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

Parameter:
| Name | Beschreibung | Optional (j/N) |
|--|--|--|
|- Identity|Gibt die Daten Verschlüsselungsrichtlinie an, die Sie ändern möchten.|N|
|-Refresh|Verwenden Sie die Aktualisierungsoption, um die Daten Verschlüsselungsrichtlinie zu aktualisieren, nachdem Sie einen der zugeordneten Schlüssel im Azure Key Vault gedreht haben. Sie müssen keinen Wert für diese Option angeben.|v|
|-Enabled|Der Parameter Enabled aktiviert oder deaktiviert die Daten Verschlüsselungsrichtlinie. Vor dem Deaktivieren einer Richtlinie müssen Sie die Zuweisung von Ihrem Mandanten aufheben. Gültige Werte sind:</br > $true: die Richtlinie ist aktiviert</br > $true: Die Richtlinie ist aktiviert. Dies ist der Standardwert.
|v|
|-Name|Der Parameter Name gibt den eindeutigen Namen der Datenverschlüsselungsrichtlinie an.|v
|-Description|Der Parameter Description gibt eine optionale Beschreibung für die Datenverschlüsselungsrichtlinie an.|v|

### <a name="get-policy-details"></a>Abrufen von Richtliniendetails

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

Beschreibung: Dieses Cmdlet listet alle M365DataAtRest-Verschlüsselungsrichtlinien auf, die für den Mandanten erstellt werden, oder Details zu einer bestimmten Richtlinie.

Beispiele:

In diesem Beispiel wird eine Zusammenfassungsliste mit M365DatAtRest-Verschlüsselungsrichtlinien in der Organisation zurückgegeben.

```powershell
Get-M365DataAtRestEncryptionPolicy
```

In diesem Beispiel werden detaillierte Informationen für die Daten Verschlüsselungsrichtlinie mit dem Namen "Nam Policy" zurückgegeben.

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

Parameter:

| Name | Beschreibung | Optional (j/N) |
|--|--|--|
|- Identity|Gibt die Daten Verschlüsselungsrichtlinie an, für die Sie die Details auflisten möchten.|v|

### <a name="get-policy-assignment-info"></a>Abrufen von Informationen zur Richtlinienzuweisung

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

Beschreibung: Dieses Cmdlet listet die Richtlinie auf, die dem Mandanten derzeit zugewiesen ist.

## <a name="offboarding-from-customer-key"></a>Offboarding aus dem Kundenschlüssel

Wenn Sie wieder auf von Microsoft verwaltete Schlüssel zurückgreifen müssen, können Sie. Wenn Sie extern, werden Ihre Daten mit der von jeder einzelnen Arbeitsauslastung unterstützten Standardverschlüsselung erneut verschlüsselt. Exchange Online unterstützt beispielsweise die Standardverschlüsselung mit von Microsoft verwalteten Schlüsseln.

Wenn Sie sich entschieden haben, ihren Mandanten über den Kundenschlüssel auf Mandantenebene extern, wenden Sie sich an Microsoft mit einer Anforderung per e-Mail, um den Dienst für den Mandanten unter [m365ck@Microsoft.com](mailto:m365ck@microsoft.com)"zu deaktivieren".

> [!IMPORTANT]
> Offboarding ist nicht identisch mit einem Datenlöschvorgang. Eine Datenbereinigung dauerhaft Crypto-löscht die Daten Ihrer Organisation aus Microsoft 365, offboarding nicht. Sie können keine Datenbereinigung für eine Richtlinie auf Mandantenebene durchführen. Informationen zum Pfad zum Löschen von Daten finden Sie unter [REVOKE your Keys und Start the Data Purge Path Process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).

## <a name="about-the-availability-key"></a>Informationen zum Verfügbarkeits Schlüssel

Informationen zum Verfügbarkeits Schlüssel finden Sie unter [erfahren Sie mehr über den Verfügbarkeits Schlüssel](customer-key-availability-key-understand.md).

## <a name="key-rotation"></a>Tasten Rotation

Informationen zu rotierenden oder Roll Schlüsseln, die mit dem Kundenschlüssel verwendet werden, finden Sie unter [Rollen oder Drehen eines Kunden Schlüssels oder eines Verfügbarkeits Schlüssels](customer-key-availability-key-roll.md). Wenn Sie die Datenausführungsverhinderung so aktualisieren, dass die neue Version der Schlüssel verwendet wird, führen Sie das Set-M365DataAtRestEncryptionPolicy-Cmdlet aus, wie weiter oben in diesem Artikel beschrieben.

## <a name="related-articles"></a>Verwandte Artikel:

- [Dienstverschlüsselung mit Kundenschlüssel](customer-key-overview.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)

- [Informationen zum Verfügbarkeits Schlüssel](customer-key-availability-key-understand.md)

- [Dienst Verschlüsselung](office-365-service-encryption.md)
