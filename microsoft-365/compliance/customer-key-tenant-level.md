---
title: Kundenschlüssel für Microsoft 365 auf der Mandantenebene (öffentliche Vorschau)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/17/2021
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
description: Erfahren Sie, wie Sie den Kundenschlüssel für alle Daten in Ihrem Microsoft 365-Mandanten einrichten.
ms.openlocfilehash: 7ffa9a8148a8ae699711b62da48cd2c856d48cac
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727478"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a>Übersicht über den Kundenschlüssel für Microsoft 365 auf Mandantenebene (öffentliche Vorschau)

Mithilfe von schlüsseln, die Sie bereitstellen, können Sie eine Datenverschlüsselungsrichtlinie (Data Encryption Policy, DEP) erstellen und sie dem Mandanten zuweisen. Die DEP verschlüsselt Daten über den Mandanten für diese Workloads:

- Teams-Chatnachrichten (1:1-Chats, Gruppenchats, Besprechungschats und Kanalunterhaltungen)
- Teams-Mediennachrichten (Bilder, Codeausschnitte, Videonachrichten, Audionachrichten, Wiki-Bilder)
- Im Speicher von Teams gespeicherte Anruf- und Besprechungsaufzeichnungen von Teams
- Teams-Chatbenachrichtigungen
- Vorschläge für Teams-Chats von Cortana
- Teams-Statusmeldungen
- Benutzer- und Signalinformationen für Exchange Online
- Exchange Online-Postfächer, die nicht bereits verschlüsselte Kundenschlüsseldeps auf Anwendungsebene sind

Für Microsoft Teams verschlüsselt der Kundenschlüssel auf Mandantenebene neue Daten ab dem Zeitpunkt, zu dem die DEP dem Mandanten zugewiesen wurde. Die öffentliche Vorschau unterstützt das Verschlüsseln vergangener Daten nicht. Für Exchange Online verschlüsselt der Customer Key alle vorhandenen und neuen Daten.

Sie können mehrere DEPs pro Mandant erstellen, aber nur eine DEP zu einem beliebigen Zeitpunkt zuweisen. Wenn Sie die DEP zuweisen, beginnt die Verschlüsselung automatisch, kann jedoch abhängig von der Größe Ihres Mandanten einige Zeit dauern.

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a>Richtlinien auf Mandantenebene fügen dem Kundenschlüssel für Microsoft 365 eine umfassendere Kontrolle hinzu

Wenn Sie bereits den Kundenschlüssel für Exchange Online und Sharepoint Online eingerichtet haben, passt die neue öffentliche Vorschau auf Mandantenebene dazu.

Die von Ihnen erstellten Verschlüsselungsrichtlinien auf Mandantenebene verschlüsselt alle Daten für die Microsoft Teams- und Exchange Online-Workloads in Microsoft 365. Wenn Sie für Exchange Online jedoch bereits Kundenschlüssel-DEPs einzelnen Postfächern zugewiesen haben, setzt die Richtlinie auf Mandantenebene diese DEPs nicht außer Kraft. Die Richtlinie auf Mandantenebene verschlüsselt nur Postfächer, denen noch keine Kundenschlüssel-DEP auf Postfachebene zugewiesen ist.

Beispielsweise werden Microsoft #A0 und einige #A1 und Besprechungsaufzeichnungen, die in OneDrive for Business und SharePoint gespeichert werden, durch eine SharePoint Online-DEP verschlüsselt. Eine einzelne SharePoint Online-DEP verschlüsselt Inhalte innerhalb eines einzelnen Geografischen.

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a>Einrichten des Kundenschlüssels auf Mandantenebene (öffentliche Vorschau)

Diese Schritte sind ähnlich, aber nicht identisch mit den Schritten zum Einrichten des Kundenschlüssels auf Anwendungsebene. Sie sollten diese öffentliche Vorschau nur mit Testdaten in Test mandanten verwenden. Verwenden Sie diese Version nicht mit Produktionsdaten oder in Ihrer Produktionsumgebung. Wenn Sie bereits über eine Produktionsbereitstellung des Kundenschlüssels verfügen, verwenden Sie diese Schritte, um den Kundenschlüssel auf Mandantenebene in einer Testumgebung zu einrichten.

Sie führen die meisten dieser Aufgaben durch eine Remoteverbindung mit Azure PowerShell aus. Um optimale Ergebnisse zu erzielen, sollten Sie Version 4.4.0 oder höher von Azure PowerShell verwenden.

Bevor Sie beginnen, sollten Sie Folgendes sicherstellen:

- Sie müssen ein Arbeits- oder Schulkonto verwenden, das über die Administratorrolle "Compliance" verfügt, um den Kundenschlüssel auf Mandantenebene einrichten zu können.
- Stellen Sie sicher, dass Sie über die entsprechende Lizenzierung für Ihre Organisation verfügen. Verwenden Sie ein kostenpflichtiges, in Rechnung gestelltes Azure-Abonnement mithilfe Konzernvertrag oder eines Clouddienstanbieters. Azure-Abonnements, die mit Pay As You Go-Plänen oder mit einer Kreditkarte erworben wurden, werden für den Kundenschlüssel nicht unterstützt. Ab dem 1. April 2020 wird der Kundenschlüssel in Office 365 in Office 365 E5, M365 E5, M365 E5 Compliance und M365 E5 Information Protection & Governance SKUs angeboten. Office 365 Advanced Compliance SKU ist nicht mehr für die Beschaffung neuer Lizenzen verfügbar. Vorhandene Office 365 Advanced Compliance-Lizenzen werden weiterhin unterstützt. Während der Dienst mit mindestens einer Lizenz unter dem Mandanten mit der entsprechenden Lizenz aktiviert werden kann, sollten Sie dennoch sicherstellen, dass alle Benutzer, die von dem Dienst profitieren, über entsprechende Lizenzen verfügen.

### <a name="create-two-new-azure-subscriptions"></a>Zwei neue Azure-Abonnements erstellen

Für Customer Key sind zwei Schlüssel für jede Daten- Verschlüsselungsrichtlinie (DEP) erforderlich. Um dies zu erreichen, müssen Sie zwei Azure-Abonnements erstellen. Als bewährte Methode empfiehlt Microsoft, dass separate Mitglieder Ihrer Organisation jeweils einen Schlüssel für jedes Abonnement konfigurieren. Verwenden Sie diese Azure-Abonnements nur zum Verwalten von Verschlüsselungsschlüsseln für Microsoft 365. Auf diese Weise ist Ihre Organisation geschützt, falls einer ihrer Betreiber versehentlich, absichtlich oder in böswilliger Absicht die Schlüssel, für die Sie verantwortlich sind, löscht oder auf andere Weise unsachgemäß handhabt.

Es gibt praktisch keine Beschränkung hinsichtlich der Anzahl von Azure-Abonnements, die Sie für Ihre Organisation erstellen können. Die Verwendung dieser bewährten Methode trägt dazu bei, die Auswirkungen von menschlichen Fehlern zu minimieren und gleichzeitig die vom Kundenschlüssel verwendeten Ressourcen zu verwalten.

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a>Azure- Abonnements registrieren, um einen obligatorischen Aufbewahrungszeitraum zu nutzen.

Der temporäre oder dauerhafte Verlust von Stammverschlüsselungsschlüsseln kann für den Dienstbetrieb störend oder sogar katastrophal sein und zu Datenverlusten führen. Aus diesem Grund ist für die mit Customer Key verwendeten Ressourcen ein starker Schutz erforderlich. Alle Azure-Ressourcen, die mit Customer Key verwendet werden, bieten Schutzmechanismen, die weit über die Standardkonfiguration hinaus gehen. Azure-Abonnements können derart gekennzeichnet oder registriert werden, dass eine sofortige und unwiderrufliche Kündigung vermieden wird. Dies wird als Registrierung eines obligatorischen Aufbewahrungszeitraums bezeichnet. Die schritte, die zum Registrieren von Azure-Abonnements für einen obligatorischen Aufbewahrungszeitraum erforderlich sind, erfordern die Zusammenarbeit mit Microsoft. Dieser Vorgang kann bis zu fünf Arbeitstage dauern. Bisher wurde diese Funktion zeitweise als „Nicht kündigen" bezeichnet.
  
Bevor Sie sich an das Microsoft 365-Team wenden, müssen Sie die folgenden Schritte für jedes Azure-Abonnement ausführen, das Sie mit Dem Kundenschlüssel verwenden. Stellen Sie sicher, dass Das [Azure PowerShell Az-Modul](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) installiert ist, bevor Sie beginnen.

1. Melden Sie sich mit Azure PowerShell an. Anweisungen finden Sie unter [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Führen Sie Register-AzProviderFeature cmdlet aus, um Ihre Abonnements für die Verwendung eines obligatorischen Aufbewahrungszeitraums zu registrieren. Führen Sie diese Aktion für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. Wenden Sie sich an Microsoft, um den Prozess unter [m365ck@microsoft.com.](mailto:m365ck@microsoft.com) Teilen Sie uns in Ihrem E-Mail bitte Folgendes mit:

   **Betreff**: Kundenschlüssel für \<*Your tenant's fully-qualified domain name*\>

   **Textkörper**: Abonnements-IDs, für die Sie einen obligatorischen Aufbewahrungszeitraum verbindlich festlegen möchten.
   Die Ausgabe der Get-AzProviderFeature für jedes Abonnement.

   Die Service-Level-Vereinbarung (Service Level Agreement, SLA) für den Abschluss dieses Vorgangs beläuft sich auf fünf Werktage, nachdem Microsoft benachrichtigt wurde (und überprüft hat, dass Sie Ihre Abonnements für die Nutzung eines obligatorischen Aufbewahrungszeitraums registriert haben).

4. Nachdem Sie von Microsoft eine Benachrichtigung erhalten haben, dass die Registrierung abgeschlossen ist, überprüfen Sie den Status Ihrer Registrierung, indem Sie den befehl Get-AzProviderFeature wie folgt ausführen. Bei Überprüfung gibt der Get-AzProviderFeature den Wert **Registered für** die Registration **State-Eigenschaft** zurück. Führen Sie diese Aktion für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. Führen Sie zum Abschließen des Vorgangs den Befehl Register-AzResourceProvider aus. Führen Sie diese Aktion für jedes Abonnement aus.

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a>Erstellen eines Premium Azure Key Vault für jedes Abonnement

Die Schritte zum Erstellen eines Schlüssel Tresors sind in ["erste Schritte mit Azure Key Vault"](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)dokumentiert, das Sie durch das Installieren und Ingangsetzen von Azure PowerShell, das Herstellen einer Verbindung mit Ihrem Azure-Abonnement, das Erstellen einer Ressourcengruppe und das Erstellen eines Schlüsseltresors in dieser Ressourcengruppe führt.
  
Wenn Sie einen Schlüsseltresor erstellen, müssen Sie eine SKU auswählen: entweder Standard oder Premium. Die Standard-SKU ermöglicht das Schützen von Azure Key Vault-Schlüsseln mittels Software – es gibt keinen Schlüsselschutz mittels eines Hardware-Sicherheitsmoduls (HSM) – und die Premium-SKU ermöglicht die Verwendung von Hardware-Sicherheitsmodulen zum Schutz von Key-Vault-Schlüsseln. Customer Key akzeptiert Schlüsseltresore mit jeder SKU, wobei Microsoft dringend empfiehlt, nur die Premium-SKU zu verwenden. Die Betriebskosten mit Schlüsseln eines der beiden Typen sind identisch. Der einzige Unterschied bei den Kosten sind die monatlichen Kosten für jeden HSM-geschützten Schlüsseln. Detailinformationen finden Si unter [Key Vault-Preise](https://azure.microsoft.com/pricing/details/key-vault/).
  
> [!IMPORTANT]
> Verwenden Sie die Premium-SKU-Schlüsseltresore und HSM-geschützten Schlüssel für Produktionsdaten, und verwenden Sie nur standardmäßige SKU-Schlüsseltresore und Schlüssel für Tests und Überprüfungen.

Verwenden Sie ein allgemeines Präfix für Schlüsseltresor und eine Abkürzung für die Verwendung und den Bereich des Schlüsseltresor und der Schlüssel. Für den Contoso-Dienst, in dem sich die Tresore in Nordamerika befinden, ist beispielsweise ein mögliches Namenspaar Contoso-O365-NA-VaultA1 und Contoso-O365-NA-VaultA2. In Azure sind Tresornamen global eindeutige Zeichenfolgen, daher müssen Sie möglicherweise Variationen Ihrer gewünschten Namen ausprobieren, falls die gewünschten Namen bereits von anderen Azure-Kunden beansprucht werden. Nachdem sie konfiguriert wurden, können Die Namen von Tresoren nicht geändert werden. Daher sollten Sie einen schriftlichen Plan für die Einrichtung verwenden und eine zweite Person verwenden, um zu überprüfen, ob der Plan ordnungsgemäß ausgeführt wurde.

Erstellen Sie Ihre Depots nach Möglichkeit in nicht-gekoppelten Regionen. Gekoppelte Azure-Regionen bieten eine hohe Verfügbarkeit über Dienstausfall-Domänen hinweg. Dementsprechend können regionale Paare gegenseitig als Backup-Region der jeweils anderen betrachtet werden. Dies bedeutet, dass eine Azure-Ressource, die in einer bestimmten Region platziert ist, durch die gekoppelte Region automatisch an Fehlertoleranz gewinnt. Aus diesem Grund bedeutet die Auswahl von Regionen für zwei Vaults, die in einer Datenverschlüsselungsrichtlinie verwendet werden, in der die Regionen gekoppelt sind, dass nur insgesamt zwei Verfügbarkeitsregionen verwendet werden. In den meisten geografischen Regionen gibt es nur zwei Regionen, weshalb es noch nicht möglich ist, nicht-gekoppelte Regionen auszuwählen. Wählen Sie nach Möglichkeit zwei nicht gekoppelte Bereiche für die beiden mit einer Datenverschlüsselungsrichtlinie verwendeten Tresore aus. Dies hat den positiven Effekt, dass insgesamt vier verfügbare Regionen genutzt werden. Weitere Informationen hierzu sowie ein aktuelles Verzeichnis der Regionenpaare finden Sie unter [Geschäftskontinuität und Notfallwiederherstellung (Business continuity and disaster recovery, BCDR): Gekoppelte Regionen in Azure](https://docs.microsoft.com/azure/best-practices-availability-paired-regions).

### <a name="assign-permissions-to-each-key-vault"></a>Zuweisen von Berechtigungen für jeden Schlüsseltresor (Key Vault)

Sie müssen für jeden Schlüsseltresor entsprechend der von Ihnen gewählten Implementierung drei gesonderte Berechtigungsgruppen für Customer Key definieren. Sie müssen beispielsweise eine Berechtigungsgruppe für jede der folgenden Optionen definieren:
  
- **Schlüsseltresor-Administratoren**, deren Aufgabe das tägliche Verwalten Ihrer Schlüsseltresore für Ihre Organisation ist. Zu diesen Aufgaben gehören Datensicherung sowie Erstellen, Abrufen, Importieren, Auflisten und Wiederherstellen.

  > [!IMPORTANT]
  > Die Berechtigungsgruppe, die Schlüsseltresor-Administratoren zugewiesen ist, beinhaltet keine Berechtigung zum Löschen von Schlüsseln. Dies ist beabsichtigt und eine wichtige Vorgehensweise. Kryptografische Schlüssel werden normalerweise nicht gelöscht, da dadurch Daten dauerhaft vernichtet werden. Eine bewährte Methode besteht darin, den Schlüsseltresor-Administratoren diese Berechtigung nicht standardmäßig zuzuweisen. Behalten Sie stattdessen diese Berechtigung den Schlüsseltresor-Mitwirkenden vor und weisen Sie diese einem Administrator nur kurzfristig und lediglich, sofern die damit verbundenen Folgen klar verstanden wurden, zu.
  
  Melden Sie sich bei Ihrem Azure-Abonnement mit Azure PowerShell an, um diesen Berechtigungen einem Benutzer in Ihrer Organisation zuzuordnen. Anweisungen finden Sie unter [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

   Führen Sie Set-AzKeyVaultAccessPolicy cmdlet aus, um die erforderlichen Berechtigungen zu erteilen.

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   Beispiel:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- **Schlüsseltresor-Mitwirkenden**, die Berechtigungen für den Azure Key Vault selbst ändern können. Sie müssen diese Berechtigungen ändern, wenn Mitarbeiter Ihr Team verlassen oder ihrem Team beitreten, oder in der seltenen Situation, dass die Schlüsseltresoradministratoren berechtigterweise die Berechtigung zum Löschen oder Wiederherstellen eines Schlüssels benötigen. Dieser Gruppe von Schlüsseltresor-Mitwirkenden muss die Rolle Mitwirkender für Ihren Schlüsseltresor zugewiesen werden. Sie können diese Rolle mithilfe des Azure-Ressourcenmanagers zuweisen. Ausführliche Schritte finden Sie unter [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources. Der Administrator, der ein Abonnement erstellt, verfügt standardmäßig über diesen Zugriff und kann der Mitwirkendenrolle andere Administratoren zuweisen.

- **Microsoft 365-Daten im** Ruhedienst, der die Arbeit des Kundenschlüssels auf Mandantenebene vor sich hat. Führen Sie zum Erteilen von Berechtigungen für Microsoft 365 das **Cmdlet Set-AzKeyVaultAccessPolicy** mit der folgenden Syntax aus:

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  Dabei gilt Folgendes:

  - *Vaultname* ist der Name des schlüsseltresor, den Sie erstellt haben.

  Beispiel: Ersetzen Sie für den Microsoft 365 Data at Rest Encryption-Dienst  *Microsoft 365 appID* durch `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a>Aktivieren und Bestätigen des vorläufigen Löschens in Ihren Schlüsseltresoren

Wenn Sie Ihre Schlüssel schnell wiederherstellen können, ist ein umfassender Dienstausfalls aufgrund von versehentlich oder in böswilliger Absicht gelöschten Schlüsseln weniger wahrscheinlich. Aktivieren Sie diese Konfiguration, die als Soft Delete bezeichnet wird, bevor Sie Ihre Schlüssel mit dem Kundenschlüssel verwenden können. Das Aktivieren von Soft Delete ermöglicht Ihnen des Wiederherstellen von Schlüsseln oder Tresoren innerhalb von 90 Tagen nach dem Löschen, ohne diese aus der Datensicherung wiederherstellen zu müssen.
  
Führen Sie die folgenden Schritte aus, um Soft Delete für Ihre Schlüsseltresore zu aktivieren:
  
1. Melden Sie sich bei Ihrem Azure-Abonnement mit Windows PowerShell. Anweisungen finden Sie unter [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).

2. Führen Sie [das Cmdlet Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) aus. In diesem Beispiel ist *der Name des* Tresors der Schlüssel, für den Sie das soft delete aktivieren:

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. Bestätigen Sie, dass das soft delete für den Schlüsseltresor konfiguriert ist, indem Sie das **Cmdlet Get-AzKeyVault** ausführen. Wenn das soft delete für den Schlüsseltresor ordnungsgemäß konfiguriert ist, gibt die _Eigenschaft Soft Delete Enabled_ den Wert True **zurück:**

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a>Hinzufügen eines Schlüssels zu jedem Schlüsseltresor durch das Erstellen oder Importieren eines Schlüssels

Es gibt zwei Methoden zum Hinzufügen von Schlüsseln zu einem Azure Key Vault. Sie können entweder direkt im Schlüsseltresor einen Schlüssel erstellen oder aber einen Schlüssel importieren. Das Erstellen eines Schlüssels direkt im Schlüsseltresor ist die einfachere Methode, während der Import eines Schlüssels die vollständige Kontrolle über die Generierung des Schlüssels bietet. Verwenden Sie die RSA-Schlüssel. Azure Key Vault unterstützt das Um- und Auspacken mit elliptischen Kurventasten nicht.
  
Führen Sie das [Cmdlet Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) wie folgt aus, um einen Schlüssel direkt in Ihrem Schlüsseltresor zu erstellen:
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

Dabei gilt Folgendes:

- *Vaultname* ist der Name des Schlüsseltresor, in dem Sie den Schlüssel erstellen möchten.

- *Schlüsselname* ist der Name, den Sie dem neuen Schlüssel geben möchten.

  > [!TIP]
  > Benennen Sie Schlüssel, die eine ähnliche Benennungskonvention verwenden, nach dem oben für Schlüsseltresore beschriebenen Verfahren. Auf diese Weise ist die Zeichenfolge in Tools, die lediglich den Schlüsselnamen anzeigen, selbsterklärend.
  
Wenn Sie den Schlüssel mit einem HSM schützen möchten, stellen Sie sicher, dass Sie **HSM** als Wert des _Parameters Destination_ angeben, andernfalls Geben Sie **Software an.**

Beispiel:
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a>Überprüfen der Wiederherstellungsebene Ihrer Schlüssel

Microsoft 365 setzt voraus, dass das Azure Key Vault-Abonnement auf Do Not Cancel festgelegt ist und dass die von Customer Key verwendeten Schlüssel für die soft delete aktiviert sind. Sie können dies sicherstellen, indem Sie die Wiederherstellungsstufe für Ihre Schlüssel überprüfen.
  
Führen Sie zum Überprüfen der Wiederherstellungsstufe eines Schlüssels in Azure PowerShell das cmdlet Get-AzKeyVaultKey wie folgt aus:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

Wenn die _Recovery Level-Eigenschaft_ einen anderen Wert als den Wert **Recoverable+ProtectedSubscription** zurückgibt, müssen Sie diesen Artikel überprüfen und sicherstellen, dass Sie alle Schritte befolgt haben, um das Abonnement in die Liste Nicht abbrechen zu setzen, und dass Sie das "soft delete" für jeden Ihrer Schlüsseltresor aktiviert haben. Als Nächstes senden Sie einen Screenshot der Ausgabe `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` von in E-Mail an m365ck@microsoft.com.

### <a name="back-up-azure-key-vault"></a>Sichern von Azure Key Vault

Unmittelbar nach dem Erstellen oder Ändern eines Schlüssels, dem Durchführen einer Sicherung und dem Speichern von Kopien der Sicherung, sowohl online als auch offline. Verbinden Sie keine Offlinekopien mit einem Netzwerk. Speichern Sie sie stattdessen in einem physischen sicheren oder kommerziellen Speicher. Mindestens eine Kopie der Sicherung sollte an einem Speicherort gespeichert werden, auf den bei einem Notfall zugegriffen werden kann. Die einzelnen Sicherungen sind die einzige Möglichkeit zum Wiederherstellen des Schlüsselmaterials, sollte ein Key-Vault-Schlüssel dauerhaft vernichtet oder auf andere Weise funktionsuntüchtig gemacht worden sein. Schlüssel, die sich außerhalb des Azure Key Vault befinden und in Azure Key Vault importiert wurden, sind als Sicherung nicht geeignet, da die Metadaten, die für die Verwendung des Schlüssels mit Customer Key erforderlich sind, mit dem externen Schlüssel nicht vorhanden sind. Nur eine vom Azure Key Vault erstellte Sicherung kann für Wiederherstellungsvorgänge mit Customer Key verwendet werden. Daher ist es wichtig, dass Sie eine Sicherung von Azure Key Vault erstellen, sobald ein Schlüssel hochgeladen oder erstellt wurde.
  
Führen Sie zum Erstellen einer Sicherung eines Azure Key Vault-Schlüssels das [Cmdlet Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) wie folgt aus:

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

Stellen Sie sicher, dass die Ausgabedatei das Suffix `.backup` verwendet.
  
Die aus diesem Cmdlet resultierende Ausgabedatei ist verschlüsselt und kann außerhalb von Azure Key Vault nicht verwendet werden. Die Sicherung kann nur für das Azure-Abonnement wiederhergestellt werden, aus dem die Sicherung erstellt wurde.
  
Beispiel:
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a>Konfigurationseinstellungen von Azure Key Vault verifizieren

Das Durchführen der Überprüfung vor der Verwendung von Schlüsseln in einer Datenverschlüsselungsrichtlinie (DEP) ist optional, wird jedoch dringend empfohlen. Insbesondere, wenn Sie andere als die in diesem Artikel beschriebenen Schritte zum Einrichten Ihrer Schlüssel und Tresore verwenden, sollten Sie den Sicherheitsstatus Ihrer Azure Key Vault-Ressourcen überprüfen, bevor Sie Customer Key konfigurieren.
  
Überprüfen, ob für Ihre Schlüssel die Funktionen „Abrufen“, „WrapKey“ und „unWrapKey“ aktiviert sind:
  
Führen Sie [das Cmdlet Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) wie folgt aus:
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

Suchen Sie in der Ausgabe nach der Zugriffsrichtlinie und nach der Microsoft 365-App-ID (GUID). Alle drei Vorgänge get, wrapKey und unwrapKey müssen unter Berechtigungen für Schlüssel angezeigt werden.
  
Wenn die Zugriffsrichtlinienkonfiguration falsch ist, führen Sie das cmdlet Set-AzKeyVaultAccessPolicy wie folgt aus:
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

Beispiel: Ersetzen Sie für den Microsoft 365 Data at Rest Encryption-Dienst  *Microsoft 365 appID* durch `c066d759-24ae-40e7-a56f-027002b5d3e4`

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

Führen Sie das [Cmdlet Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) wie folgt aus, um zu überprüfen, ob für Ihre Schlüssel kein Ablaufdatum festgelegt ist:
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

Ein abgelaufener Schlüssel kann nicht vom Kundenschlüssel verwendet werden, und Vorgänge, die mit einem abgelaufenen Schlüssel versucht werden, führen möglicherweise zu einem Dienstausfall. Es wird dringend empfohlen, dass mit Customer Key verwendete Schlüssel kein Ablaufdatum aufweisen. Ein einmal festgelegtes Ablaufdatum kann nicht gelöscht werden, es kann jedoch eine Datumänderung vorgenommen werden. Wenn ein Schlüssel verwendet werden muss, für den ein Ablaufdatum festgelegt ist, ändern Sie bitte das Ablaufdatum auf 31.12.9999. Schlüssel mit einem Ablaufdatum, das auf ein anderes Datum als den 31.12.9999 festgelegt ist, bestehen die Microsoft 365-Überprüfung nicht.
  
Führen Sie das [Cmdlet Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) wie folgt aus, um ein Ablaufdatum zu ändern, das auf einen anderen Wert als den 31.12.9999 festgelegt wurde:
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a>Abrufen eines URI für jeden Azure Key Vault-Schlüssel

Nachdem Sie alle Schritte in Azure abgeschlossen haben, um Ihre Schlüsseltresor einrichten und Ihre Schlüssel hinzugefügt haben, führen Sie den folgenden Befehl aus, um den URI für den Schlüssel in jedem Schlüsseltresor zu erhalten. Sie müssen diese URI verwenden, wenn Sie in weiterer Folge die einzelnen Datenverschlüsselungsrichtlinien (DEP) erstellen und zuweisen, also speichern Sie diese Informationen an einem sicheren Ort. Denken Sie daran, diesen Befehl jeweils für jeden Schlüsseltresor einmal auszuführen.
  
In Azure PowerShell:
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a>Einrichten der Kundenschlüsselverschlüsselungsrichtlinie für Ihren Mandanten

Bevor Sie diese Cmdlets ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Obwohl in diesem Artikel alle Parameter für die Cmdlets aufgeführt sind, haben Sie möglicherweise keinen Zugriff auf einige Parameter, wenn sie nicht in den Ihnen zugewiesenen Berechtigungen enthalten sind. Wie Sie herausfinden, welche Berechtigungen zur Ausführung eines bestimmten Cmdlets oder Parameters in Ihrer Organisation erforderlich sind, können Sie unter [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions) nachlesen.

### <a name="create-policy"></a>Richtlinie erstellen

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

Beschreibung: Aktivieren Sie den Complianceadministrator, um eine neue Datenverschlüsselungsrichtlinie (Data Encryption Policy, DEP) mit zwei AKV-Stammschlüsseln zu erstellen. Nach dem Erstellen kann eine Richtlinie mithilfe eines cmdlets Set-M365DataAtRestEncryptionPolicyAssignment zugewiesen werden. Bei der ersten Zuweisung von Schlüsseln oder nach dem Drehen von Schlüsseln kann es bis zu 24 Stunden dauern, bis die neuen Schlüssel wirksam werden. Wenn die neue DEP mehr als 24 Stunden in Kraft tritt, wenden Sie sich an Microsoft.

Beispiel:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

Parameter:

| Name | Beschreibung | Optional (Y/N) |
|----------|----------|---------|
|Name|Anzeigename der Datenverschlüsselungsrichtlinie|N|
|AzureKeyIDs|Gibt zwei URI-Werte der Azure Key Vault-Schlüssel an, die durch ein Komma getrennt sind und der Datenverschlüsselungsrichtlinie zugeordnet werden.|N|
|Beschreibung|Beschreibung der Datenverschlüsselungsrichtlinie|N|

### <a name="assign-policy"></a>Richtlinie zuweisen

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy “<Default_PolicyName or Default_PolicyID>”
```

Beschreibung: Dieses Cmdlet wird zum Konfigurieren der Standardmäßigen Datenverschlüsselungsrichtlinie verwendet. Diese Richtlinie wird dann verwendet, um Daten über alle Supportarbeitslasten hinweg zu verschlüsseln. 

Beispiel:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy “Default_PolicyName”
```

Parameter:

| Name | Beschreibung | Optional (Y/N) |
|----------|----------|---------|
-DataEncryptionPolicy|Gibt die Datenverschlüsselungsrichtlinie an, die zugewiesen werden muss. geben Sie entweder den Richtliniennamen oder die Richtlinien-ID an.|N|

### <a name="modify-or-refresh-policy"></a>Ändern oder Aktualisieren der Richtlinie

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

Beschreibung: Das Cmdlet kann zum Ändern oder Aktualisieren einer vorhandenen Richtlinie verwendet werden. Es kann auch verwendet werden, um eine Richtlinie zu aktivieren oder zu deaktivieren. Bei der ersten Zuweisung von Schlüsseln oder nach dem Drehen von Schlüsseln kann es bis zu 24 Stunden dauern, bis die neuen Schlüssel wirksam werden. Wenn die neue DEP mehr als 24 Stunden in Kraft tritt, wenden Sie sich an Microsoft.

Beispiele:

Deaktivieren sie eine Datenverschlüsselungsrichtlinie.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

Aktualisieren einer Datenverschlüsselungsrichtlinie.

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

Parameter:

| Name | Beschreibung | Optional (Y/N) |
|----------|----------|---------|
|-Identity|Gibt die Datenverschlüsselungsrichtlinie an, die Sie ändern möchten.|N|
|-Refresh|Verwenden Sie die Option Aktualisieren, um die Datenverschlüsselungsrichtlinie zu aktualisieren, nachdem Sie einen der zugeordneten Schlüssel im Azure Key Vault gedreht haben. Sie müssen keinen Wert für diese Option angeben.|v|
|-Enabled|Der Parameter Enabled aktiviert oder deaktiviert die Datenverschlüsselungsrichtlinie. Bevor Sie eine Richtlinie deaktivieren, müssen Sie sie ihrem Mandanten zuweisen. Gültige Werte sind:</br > $true: Die Richtlinie ist aktiviert</br > $true: Die Richtlinie ist aktiviert. Dies ist der Standardwert.
|v|
|-Name|Der Parameter Name gibt den eindeutigen Namen der Datenverschlüsselungsrichtlinie an.|v|
|-Description|Der Parameter Description gibt eine optionale Beschreibung für die Datenverschlüsselungsrichtlinie an.|v|

### <a name="get-policy-details"></a>Erhalten von Richtliniendetails

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

Beschreibung: Dieses Cmdlet listet alle M365DataAtRest-Verschlüsselungsrichtlinien auf, die für den Mandanten erstellt werden, oder Details zu einer bestimmten Richtlinie.

Beispiele:

In diesem Beispiel wird eine Zusammenfassungsliste der M365DatAtRest-Verschlüsselungsrichtlinien in der Organisation zurückgegeben.

```powershell
Get-M365DataAtRestEncryptionPolicy
```

In diesem Beispiel werden detaillierte Informationen für die Datenverschlüsselungsrichtlinie namens "NAM-Richtlinie" zurückgegeben.

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

Parameter:

| Name | Beschreibung | Optional (Y/N) |
|----------|----------|---------|
|-Identity|Gibt die Datenverschlüsselungsrichtlinie an, für die Sie die Details auflisten möchten.|v|

### <a name="get-policy-assignment-info"></a>Informationen zur Richtlinienzuweisung erhalten

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

Beschreibung: Dieses Cmdlet listet die Richtlinie auf, die dem Mandanten derzeit zugewiesen ist.

## <a name="offboarding-from-customer-key"></a>Offboarding über den Kundenschlüssel

Wenn Sie zu von Microsoft verwalteten Schlüsseln zurückkehren müssen, können Sie dies. Beim Offboard werden Ihre Daten mithilfe der standardverschlüsselten Verschlüsselung, die von jeder einzelnen Arbeitsauslastung unterstützt wird, erneut verschlüsselt. Exchange Online unterstützt beispielsweise die Standardverschlüsselung mithilfe von von Microsoft verwalteten Schlüsseln.

Wenn Sie sich entschieden haben, Ihren Mandanten vom Kundenschlüssel auf Mandantenebene zu entfernen, erreichen Sie Microsoft mit einer E-Mail-Anforderung, um den Dienst für den Mandanten unter [m365ck@microsoft.com zu deaktivieren.](mailto:m365ck@microsoft.com)

> [!IMPORTANT]
> Offboarding ist nicht identisch mit einer Datenbereinigung. Eine Datenbereinigung löscht die Daten Ihrer Organisation dauerhaft aus Microsoft 365, offboarding nicht. Sie können keine Datenbereinigung für eine Richtlinie auf Mandantenebene ausführen. Informationen zum Datenbereinigungspfad finden Sie unter [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).

## <a name="about-the-availability-key"></a>Informationen zum Verfügbarkeitsschlüssel

Weitere Informationen zum Verfügbarkeitsschlüssel finden Sie [unter Informationen zum Verfügbarkeitsschlüssel](customer-key-availability-key-understand.md).

## <a name="key-rotation"></a>Schlüsseldrehung

Informationen zum Drehen oder Rollen von Schlüsseln, die mit dem Kundenschlüssel verwendet werden, finden Sie unter [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md). Wenn Sie die DEP so aktualisieren, dass die neue Version der Schlüssel verwendet wird, führen Sie das cmdlet Set-M365DataAtRestEncryptionPolicy aus, wie weiter oben in diesem Artikel beschrieben.

## <a name="related-articles"></a>Verwandte Artikel:

- [Dienstverschlüsselung mit Kundenschlüssel](customer-key-overview.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)

- [Informationen zum Verfügbarkeitsschlüssel](customer-key-availability-key-understand.md)

- [Dienstverschlüsselung](office-365-service-encryption.md)
