---
title: Verwalten des Kundenschlüssels
ms.author: krowley
author: kccross
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Nachdem Sie den Kundenschlüssel eingerichtet haben, erfahren Sie, wie Sie ihn verwalten, indem Sie AKV-Schlüssel wiederherstellen, Berechtigungen verwalten und Datenverschlüsselungsrichtlinien erstellen und zuweisen.
ms.openlocfilehash: da806ec9dcf1327ec5fdd6b0a0c9e7f22c89584e
ms.sourcegitcommit: 94e64afaf12f3d8813099d8ffa46baba65772763
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52345058"
---
# <a name="manage-customer-key"></a>Verwalten des Kundenschlüssels

Nachdem Sie den Kundenschlüssel für Office 365 eingerichtet haben, müssen Sie eine oder mehrere Datenverschlüsselungsrichtlinien (Data Encryption Policies, DEP) erstellen und zuweisen. Nachdem Sie Ihre DEPs zugewiesen haben, können Sie Ihre Schlüssel wie in diesem Artikel beschrieben verwalten. Weitere Informationen zum Kundenschlüssel finden Sie in den zugehörigen Themen.

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a>Erstellen einer DEP für die Verwendung mit mehreren Workloads für alle Mandantenbenutzer

Bevor Sie beginnen, stellen Sie sicher, dass Sie die aufgaben, die zum Einrichten des Kunden erforderlich sind, abgeschlossen haben. Weitere Informationen finden Sie unter [Einrichten des Kundenschlüssels](customer-key-set-up.md). Zum Erstellen der DEP benötigen Sie die Key Vault-URIs, die Sie während des Setups erhalten haben. Weitere Informationen finden Sie unter [Abrufen des URI für jeden Azure Key Vault-Schlüssel](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).

Führen Sie die folgenden Schritte aus, um eine DEP mit mehreren Arbeitsauslastungen zu erstellen:
  
1. Stellen Sie auf Ihrem lokalen Computer mithilfe eines Unternehmens- oder Schulkontos, das über globale Administrator- oder Complianceadministratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in einem Windows PowerShell herstellen.

2. Verwenden Sie zum Erstellen einer DEP das cmdlet New-M365DataAtRestEncryptionPolicy Cmdlet.

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   Dabei gilt:

   - *PolicyName* ist der Name, den Sie für die Richtlinie verwenden möchten. Namen dürfen keine Leerzeichen enthalten. Beispiel: Contoso_Global.

   - *KeyVaultURI1* ist der URI für den ersten Schlüssel in der Richtlinie. Beispiel: <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.

   - *KeyVaultURI2* ist der URI für den zweiten Schlüssel in der Richtlinie. Beispiel: <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>. Trennen Sie die beiden URI mittels Komma und Leerzeichen.

   - *Die Richtlinienbeschreibung* ist eine benutzerfreundliche Beschreibung der Richtlinie, die Ihnen dabei hilft, sich daran zu erinnern, wofür die Richtlinie gilt. In der Beschreibung sind Leerzeichen erlaubt. Beispiel: "Stammrichtlinie für mehrere Arbeitsauslastungen für alle Benutzer im Mandanten."

Beispiel:

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a>Zuweisen einer Richtlinie mit mehreren Arbeitsauslastungen

Weisen Sie die DEP mithilfe des cmdlets Set-M365DataAtRestEncryptionPolicyAssignment zu. Nachdem Sie die Richtlinie zugewiesen haben, Microsoft 365 die Daten mit dem schlüssel verschlüsselt, der in der DEP identifiziert ist.

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 Dabei *ist PolicyName* der Name der Richtlinie. Beispiel: Contoso_Global.

Beispiel:

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a>Erstellen einer DEP für die Verwendung mit Exchange Online Postfächern

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aufgaben zum Einrichten von Azure Key Vault abgeschlossen haben. Weitere Informationen finden Sie unter [Einrichten des Kundenschlüssels](customer-key-set-up.md). Führen Sie diese Schritte aus, indem Sie eine Remoteverbindung mit Exchange Online Windows PowerShell.

Eine Datenverschlüsselungsrichtlinie (DEP) ist mit einer Reihe von im Azure Key Vault gespeicherten Schlüsseln verknüpft. Sie weisen einem Postfach in der Microsoft 365. Microsoft 365 verwendet dann die in der Richtlinie identifizierten Schlüssel, um das Postfach zu verschlüsseln. Zum Erstellen der DEP benötigen Sie die Key Vault-URIs, die Sie während des Setups erhalten haben. Weitere Informationen finden Sie unter [Abrufen des URI für jeden Azure Key Vault-Schlüssel](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).

Nicht vergessen! Wenn Sie eine DEP erstellen, geben Sie zwei Schlüssel in zwei verschiedenen Azure Key Vaults an. Erstellen Sie diese Schlüssel in zwei separaten Azure-Regionen, um georedundanz zu gewährleisten.

Führen Sie die folgenden Schritte aus, um eine DEP für die Verwendung mit einem Postfach zu erstellen:
  
1. Stellen Sie auf Ihrem lokalen Computer mithilfe eines Arbeits- oder Schulkontos, das über globale Administrator- oder Exchange Online Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in einem Windows PowerShell herstellen.

2. Um eine Datenverschlüsselungsrichtlinie zu erstellen, verwenden Sie das Cmdlet „New-DataEncryptionPolicy“, indem Sie den folgenden Befehl eingeben.

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   Dabei gilt:

   - *PolicyName* ist der Name, den Sie für die Richtlinie verwenden möchten. Namen dürfen keine Leerzeichen enthalten. Beispiel: USA_Postfächer.

   - *Die Richtlinienbeschreibung* ist eine benutzerfreundliche Beschreibung der Richtlinie, die Ihnen dabei hilft, sich daran zu erinnern, wofür die Richtlinie gilt. In der Beschreibung sind Leerzeichen erlaubt. Beispiel: "Stammschlüssel für Postfächer in den USA und ihren Gebieten".

   - *KeyVaultURI1* ist der URI für den ersten Schlüssel in der Richtlinie. Beispiel: <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.

   - *KeyVaultURI2* ist der URI für den zweiten Schlüssel in der Richtlinie. Beispiel: <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>. Trennen Sie die beiden URI mittels Komma und Leerzeichen.

   Beispiel:
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).

### <a name="assign-a-dep-to-a-mailbox"></a>Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach

Zuweisen der Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach mithilfe des Cmdlets „Set-Mailbox“. Nachdem Sie die Richtlinie zugewiesen haben, Microsoft 365 das Postfach mit dem in der DEP identifizierten Schlüssel verschlüsseln.
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

Wobei *MailboxIdParameter* ein Benutzerpostfach angibt. Weitere Informationen zum Cmdlet „Set-Mailbox“ finden Sie unter [Set-Mailbox](/powershell/module/exchange/set-mailbox).

In Hybridumgebungen können Sie den lokalen Postfachdaten, die mit Ihrem Mandanten synchronisiert werden, Exchange Online zuweisen. Um diesen synchronisierten Postfachdaten eine DEP zuzuordnen, verwenden Sie das cmdlet Set-MailUser Cmdlet. Weitere Informationen zu Postfachdaten in der Hybridumgebung finden Sie unter lokale Postfächer, die [Outlook für iOS](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)und Android mit moderner Hybridauthentifizierung verwenden.

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

Dabei *gibt MailUserIdParameter* einen E-Mail-Benutzer an (auch als E-Mail-aktivierter Benutzer bezeichnet). Weitere Informationen zum cmdlet Set-MailUser finden Sie unter [Set-MailUser](/powershell/module/exchange/set-mailuser).

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a>Erstellen einer DEP für die Verwendung mit SharePoint Online-, OneDrive for Business- und Teams Dateien

Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aufgaben zum Einrichten von Azure Key Vault abgeschlossen haben. Weitere Informationen finden Sie unter [Einrichten des Kundenschlüssels](customer-key-set-up.md).
  
Zum Einrichten des Kundenschlüssels für SharePoint Online-, OneDrive for Business- und Teams-Dateien führen Sie diese Schritte aus, indem Sie eine Remoteverbindung mit SharePoint Online mit Windows PowerShell.
  
Sie ordnen eine DEP einem Satz von Schlüsseln zu, die in Azure Key Vault gespeichert sind. Sie wenden eine Datenverschlüsselungsrichtlinie (DEP) auf alle Ihre Daten an einem geografischen Standort an, der auch als Geo bezeichnet wird. Wenn Sie das Multi-Geo-Feature von Office 365 verwenden, können Sie eine DEP pro Geografischem erstellen, mit der Möglichkeit, unterschiedliche Schlüssel pro Geografischem zu verwenden. Wenn Sie multi-geo nicht verwenden, können Sie eine DEP in Ihrer Organisation für die Verwendung mit SharePoint Online-, OneDrive for Business- und Teams erstellen. Microsoft 365 verwendet die in der DEP identifizierten Schlüssel, um Ihre Daten in diesem Geografischen zu verschlüsseln. Zum Erstellen der DEP benötigen Sie die Key Vault-URIs, die Sie während des Setups erhalten haben. Weitere Informationen finden Sie unter [Abrufen des URI für jeden Azure Key Vault-Schlüssel](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).
  
Nicht vergessen! Wenn Sie eine DEP erstellen, geben Sie zwei Schlüssel in zwei verschiedenen Azure Key Vaults an. Erstellen Sie diese Schlüssel in zwei separaten Azure-Regionen, um georedundanz zu gewährleisten.
  
Um eine Datenverschlüsselungsrichtlinie (DEP) zu erstellen, müssen Sie mithilfe von Windows PowerShell eine Remote-Verbindung zu SharePoint Online herstellen.
  
1. Verwenden Sie auf Ihrem lokalen Computer mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, Verbinden [Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)SharePoint verwenden.

2. Führen Sie in der Microsoft SharePoint Online Management-Shell das Cmdlet Register-SPODataEncryptionPolicy wie folgt durch:

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   Beispiel:
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   Sobald Sie die Datenverschlüsselungsrichtlinie (DEP) registrieren, beginnt die Verschlüsselung der Daten im Geo. Die Verschlüsselung kann einige Zeit dauern. Weitere Informationen zur Verwendung dieses Parameters finden Sie unter [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a>Anzeigen der dePs, die Sie für die Exchange Online erstellt haben

Verwenden Sie zum Anzeigen einer Liste aller dePs, die Sie für Postfächer erstellt haben, das Get-DataEncryptionPolicy PowerShell-Cmdlet.

1. Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung [mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Führen Sie zum Zurückgeben aller DEPs in Ihrer Organisation das cmdlet Get-DataEncryptionPolicy parameterfrei aus.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Weitere Informationen zum cmdlet Get-DataEncryptionPolicy finden Sie unter [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Zuweisen einer DEP vor der Migration eines Postfachs in die Cloud

Wenn Sie die DEP zuweisen, Microsoft 365 den Inhalt des Postfachs mithilfe der zugewiesenen DEP während der Migration verschlüsselt. Dieser Vorgang ist effizienter als das Migrieren des Postfachs, das Zuweisen der DEP und dann das Warten auf die Verschlüsselung, was Stunden oder möglicherweise Tage dauern kann.

Um einem Postfach eine DEP zuzuordnen, bevor Sie es zu Office 365, führen Sie das cmdlet Set-MailUser in Exchange Online PowerShell aus:

1. Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung [mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Führen Sie Set-MailUser cmdlet aus.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Dabei *gibt GeneralMailboxOrMailUserIdParameter* ein Postfach an, und *DataEncryptionPolicyIdParameter* ist die ID der DEP. Weitere Informationen zum cmdlet Set-MailUser finden Sie unter [Set-MailUser](/powershell/module/exchange/set-mailuser).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Ermitteln der Datenverschlüsselungsrichtlinie (DEP), die einem Postfach zugewiesen ist

Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um zu ermitteln, welche Datenverschlüsselungsrichtlinie (DEP) einem Postfach zugewiesen ist. Das Cmdlet meldet einen eindeutigen Bezeichner (GUID) zurück.
  
1. Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung [mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Wobei *GeneralMailboxOrMailUserIdParameter* ein Postfach angibt und DataEncryptionPolicyID die GUID der DEP zurückgibt. Weitere Informationen zum Cmdlet „Get-MailboxStatistics“ finden Sie unter [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).
  
2. Führen Sie Get-DataEncryptionPolicy cmdlet aus, um den Anzeigenamen der DEP zu finden, der das Postfach zugewiesen ist.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Dabei ist der *GUID* derjenige GUID, der vom Cmdlet „Get-MailboxStatistics“ im vorherigen Schritt zurückgemeldet wurde.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Überprüfen, ob der Kundenschlüssel die Verschlüsselung beendet hat

Verwenden Sie die Schritte in diesem Abschnitt, um sicherzustellen, dass die Verschlüsselung abgeschlossen ist, unabhängig davon, ob Sie einen Kundenschlüssel gerollt, eine neue DEP zugewiesen oder ein Postfach migriert haben.

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a>Überprüfen, ob die Verschlüsselung für Exchange Online abgeschlossen ist

Das Verschlüsseln eines Postfachs kann einige Zeit in Anspruch nehmen. Bei der ersten Verschlüsselung muss das Postfach auch vollständig von einer Datenbank in eine andere verschoben werden, bevor der Dienst das Postfach verschlüsseln kann.
  
Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um festzustellen, ob ein Postfach verschlüsselt ist.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Die IsEncrypted-Eigenschaft gibt den Wert **true** zurück, wenn das Postfach verschlüsselt ist, und den Wert **false,** wenn das Postfach nicht verschlüsselt ist. Die Zeit zum Abschließen von Postfachbewegungen hängt von der Anzahl der Postfächer ab, denen Sie zum ersten Mal eine DEP zuweisen, und der Größe der Postfächer. Wenn die Postfächer nach einer Woche nach dem Zugewiesenen der DEP nicht verschlüsselt wurden, wenden Sie sich an Microsoft.

Das New-MoveRequest cmdlet ist nicht mehr für lokale Postfachbewegungen verfügbar. Weitere Informationen [finden Sie in](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) dieser Ankündigung.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Überprüfen, ob die Verschlüsselung für SharePoint Online-, OneDrive for Business- und Teams ist

Überprüfen Sie den Status der Verschlüsselung, indem Sie Get-SPODataEncryptionPolicy cmdlet wie folgt ausführen:

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

Die Ausgabe dieses Cmdlets umfasst Folgendes:
  
- URI des Primärschlüssels.

- URI des Sekundärschlüssels.

- Verschlüsselungsstatus für den Geo. Mögliche weitere Angaben:

  - **Unregistered:** (Nicht registriert) Die Customer Key-Verschlüsselung wurde noch nicht angewendet.

  - **Registering:** (Registrierung läuft) Die Customer Key-Verschlüsselung wurde angewendet wurde und Ihre Dateien werden gegenwärtig gerade verschlüsselt. Wenn der Schlüssel für den Geografischen registriert wird, werden Ihnen auch Informationen angezeigt, welcher Prozentsatz der Websites im Geografischen abgeschlossen ist, damit Sie den Verschlüsselungsfortschritt überwachen können.

  - **Registered:** (Registriert) Die Customer Key- Verschlüsselung wurde angewendet, und alle Dateien auf allen Websites wurden verschlüsselt.

  - **Rolling:** Das Erstellen eines sich fortlaufend ändernden, sogenannten Rolling-Codes für den Schlüssel ist in Gang. Wenn der Schlüssel für den geografischen Standort rollt, erhalten Sie außerdem Informationen dazu, welcher Prozentsatz der Websites den Schlüsselrollvorgang abgeschlossen hat, damit Sie den Fortschritt überwachen können.

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a>Erhalten Von Details zu DEPs, die Sie mit mehreren Arbeitsauslastungen verwenden

Führen Sie die folgenden Schritte aus, um Details zu allen DEPs zu erhalten, die Sie für die Verwendung mit mehreren Workloads erstellt haben:

1. Stellen Sie auf Ihrem lokalen Computer mithilfe eines Unternehmens- oder Schulkontos, das über globale Administrator- oder Complianceadministratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in einem Windows PowerShell herstellen.

   - Führen Sie diesen Befehl aus, um die Liste aller DEPs mit mehreren Arbeitsauslastungen in der Organisation zurückzukehren.

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - Führen Sie diesen Befehl aus, um Details zu einer bestimmten DEP zurückzukehren. In diesem Beispiel werden detaillierte Informationen für die DEP mit dem Namen "Contoso_Global" zurückgegeben.

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a>Get multi-workload DEP assignment information

Führen Sie die folgenden Schritte aus, um herauszufinden, welche DEP Ihrem Mandanten derzeit zugewiesen ist. 

1. Stellen Sie auf Ihrem lokalen Computer mithilfe eines Unternehmens- oder Schulkontos, das über globale Administrator- oder Complianceadministratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in einem Windows PowerShell herstellen.

2. Geben Sie diesen Befehl ein.

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a>Deaktivieren einer DEP mit mehreren Arbeitsauslastungen

Bevor Sie eine DEP mit mehreren Arbeitsauslastungen deaktivieren, müssen Sie die DEP von Arbeitsauslastungen in Ihrem Mandanten entfernen. Führen Sie die folgenden Schritte aus, um eine mit mehreren Workloads verwendete DEP zu deaktivieren:

1. Stellen Sie auf Ihrem lokalen Computer mithilfe eines Unternehmens- oder Schulkontos, das über globale Administrator- oder Complianceadministratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in einem Windows PowerShell herstellen.

2. Führen Sie Set-M365DataAtRestEncryptionPolicy cmdlet aus.
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

Dabei *ist PolicyName* der Name oder die eindeutige ID der Richtlinie. Beispiel: Contoso_Global.

Beispiel:

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a>Wiederherstellen von Azure Key Vault-Schlüsseln

Verwenden Sie vor dem Ausführen einer Wiederherstellung die von Soft Delete bereitgestellten Wiederherstellungsfunktionen. Für alle mit Customer Key verwendeten Schlüssel muss Soft Delete aktiviert sein. Soft Delete wirkt wie ein Recycling-Mülleimer und ermöglicht die Wiederherstellung von bis zu 90 Tagen, ohne dass eine Wiederherstellung erforderlich ist. Eine Wiederherstellung sollte nur unter extremen und außergewöhnlichen Umständen erforderlich sein, beispielsweise, wenn ein Schlüssel oder ein Schlüsseltresor verloren geht. Wenn Sie einen Schlüssel zur Verwendung mit Customer Key wiederherstellen müssen, führen Sie in Azure PowerShell das Cmdlet „Restore-AzureKeyVaultKey“ wie folgt aus:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Beispiel:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Wenn der Schlüsseltresor bereits einen Schlüssel mit demselben Namen enthält, schlägt der Wiederherstellungsvorgang fehl. Restore-AzKeyVaultKey werden alle Schlüsselversionen und alle Metadaten für den Schlüssel einschließlich des Schlüsselnamens wiederhergestellt.
  
## <a name="manage-key-vault-permissions"></a>Verwalten von Schlüsseltresor-Berechtigungen

Mehrere Cmdlets stehen zur Verfügung, mit denen Sie die Schlüsseltresor-Berechtigungen ansehen und, falls erforderlich, entfernen können. Möglicherweise müssen Sie Berechtigungen entfernen, beispielsweise, wenn ein Mitarbeiter das Team verlässt. Für jede dieser Aufgaben verwenden Sie Azure PowerShell. Weitere Informationen zu Azure PowerShell finden Sie [unter Overview of Azure PowerShell](/powershell/azure/).

Führen Sie zum Anzeigen von Schlüsseltresorberechtigungen das cmdlet Get-AzKeyVault aus.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

Beispiel:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Führen Sie zum Entfernen der Berechtigungen eines Administrators das cmdlet Remove-AzKeyVaultAccessPolicy aus:
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

Beispiel:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>Rollback vom Kundenschlüssel zu verwalteten Schlüsseln von Microsoft

Wenn Sie zu von Microsoft verwalteten Schlüsseln zurückkehren müssen, können Sie dies. Beim Offboard werden Ihre Daten mithilfe der standardverschlüsselten Verschlüsselung, die von jeder einzelnen Arbeitsauslastung unterstützt wird, erneut verschlüsselt. Beispielsweise unterstützt Exchange Online Standardverschlüsselung mithilfe von von Microsoft verwalteten Schlüsseln.

> [!IMPORTANT]
> Offboarding ist nicht identisch mit einer Datenbereinigung. Eine Datenbereinigung löscht die Daten Ihrer Organisation dauerhaft aus Microsoft 365 offboarding nicht. Sie können keine Datenbereinigung für eine Richtlinie mit mehreren Arbeitsauslastungen ausführen.

Wenn Sie den Kundenschlüssel nicht mehr zum Zuweisen von DEPs mit mehreren Arbeitsauslastungen verwenden möchten, müssen Sie den Microsoft-Support mit einer Anforderung an "offboard" über den Kundenschlüssel erreichen. Bitten Sie das Supportteam, eine Dienstanfrage an Microsoft 365 Kundenschlüsselteam zu senden. Wenden Sie sich an m365-ck@service.microsoft.com, wenn Sie Fragen haben.

Wenn Sie einzelne Postfächer nicht mehr mithilfe von DEPs auf Postfachebene verschlüsseln möchten, können Sie dePs auf Postfachebene von allen Postfächern zuweisen.

Verwenden Sie das PowerShell-Cmdlet, um die Set-Mailbox zuzuweisen.

1. Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung [mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Führen Sie Set-Mailbox cmdlet aus.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

Wenn Sie dieses Cmdlet ausführen, wird die derzeit zugewiesene DEP entfernt und das Postfach mithilfe der DEP, die standardmäßig von Microsoft verwalteten Schlüsseln zugeordnet ist, erneut verschlüsselt. Die von verwalteten Schlüsseln von Microsoft verwendete DEP kann nicht entfernt werden. Wenn Sie keine von Microsoft verwalteten Schlüssel verwenden möchten, können Sie dem Postfach eine weitere Kundenschlüssel-DEP zuweisen.

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Widerrufen Der Schlüssel und Starten des Datenbereinigungspfadprozesses

Sie steuern den Widerruf aller Stammschlüssel, einschließlich des Verfügbarkeitsschlüssels. Customer Key bietet die Kontrolle über den Aspekt der Beendigungsplanung der gesetzlichen Anforderungen für Sie. Wenn Sie ihre Schlüssel widerrufen möchten, um Ihre Daten zu löschen und den Dienst zu beenden, löscht der Dienst den Verfügbarkeitsschlüssel, sobald der Datenlöschvorgang abgeschlossen ist. Dies wird für Kundenschlüssel-DEPs unterstützt, die einzelnen Postfächern zugewiesen sind.

Microsoft 365 überwacht und überprüft den Datenbereinigungspfad. Weitere Informationen finden Sie im SSAE 18 SOC 2-Bericht, der im [Service Trust Portal verfügbar ist.](https://servicetrust.microsoft.com/) Darüber hinaus empfiehlt Microsoft die folgenden Dokumente:

- [Leitfaden zur Risikobewertung und Compliance für Finanzinstitute in der Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Überlegungen zur O365-Beendigungsplanung](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Das Löschen von DEP mit mehreren Arbeitslasten wird für den Microsoft 365 nicht unterstützt. Die DEP mit mehreren Arbeitsauslastungen wird verwendet, um Daten über mehrere Arbeitsauslastungen hinweg für alle Mandantenbenutzer zu verschlüsseln. Das Löschen einer solchen DEP würde dazu führen, dass auf Daten aus mehreren Arbeitsauslastungen nicht mehr zugegriffen werden kann. Wenn Sie entscheiden, Microsoft 365 dienste vollständig zu beenden, können Sie den Pfad der Mandantenlöschung pro dokumentiertem Prozess verfolgen. Erfahren [Sie, wie Sie einen Mandanten in Azure Active Directoy löschen.](/azure/active-directory/enterprise-users/directory-delete-howto)

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Widerrufen Sie Ihre Kundenschlüssel und den Verfügbarkeitsschlüssel für Exchange Online und Skype for Business

Wenn Sie den Datenbereinigungspfad für Exchange Online und Skype for Business initiieren, legen Sie eine permanente Datenbereinigungsanforderung für eine DEP fest. Dadurch werden verschlüsselte Daten in den Postfächern, denen diese DEP zugewiesen ist, dauerhaft gelöscht.

Da Sie das PowerShell-Cmdlet nur für eine DEP gleichzeitig ausführen können, sollten Sie eine einzelne DEP allen Postfächern erneut zuweisen, bevor Sie den Datenbereinigungspfad initiieren.

> [!WARNING]
> Verwenden Sie nicht den Pfad zum Löschen von Daten, um eine Teilmenge Ihrer Postfächer zu löschen. Dieser Vorgang ist nur für Kunden gedacht, die den Dienst verlassen.

Führen Sie die folgenden Schritte aus, um den Datenbereinigungspfad zu initiieren:

1. Entfernen von Umbruch- und Auspackberechtigungen für "O365 Exchange Online" aus Azure Key Vaults.

2. Stellen Sie mithilfe eines Arbeits- oder Schulkontos mit globalen Administratorrechten in Ihrer Organisation eine Verbindung mit [Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)

3. Führen Sie für jede DEP, die zu löschende Postfächer enthält, das [Cmdlet Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) wie folgt aus.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Wenn der Befehl fehlschlägt, stellen Sie sicher, dass Sie die Exchange Online aus beiden Schlüsseln in Azure Key Vault entfernt haben, wie weiter oben in dieser Aufgabe angegeben.Nachdem Sie den Switch PermanentDataPurgeRequested mit dem cmdlet Set-DataEncryptionPolicy festgelegt haben, können Sie diese DEP nicht mehr Postfächern zuweisen.

4. Wenden Sie sich an den Microsoft-Support, und fordern Sie das Data Purge eDocument an.

    Auf Ihre Anfrage sendet Microsoft Ihnen ein rechtliches Dokument, um die Löschung von Daten zu bestätigen und zu autorisieren. Die Person in Ihrer Organisation, die sich während des Onboardings als genehmigende Person im FastTrack-Angebot angemeldet hat, muss dieses Dokument signieren. Normalerweise handelt es sich dabei um eine Führungskraft oder eine andere benannte Person in Ihrem Unternehmen, die berechtigt ist, den Papierkram im Namen Ihrer Organisation zu signieren.

5. Nachdem Ihr Vertreter das rechtliche Dokument signiert hat, geben Sie es an Microsoft zurück (in der Regel über eine eDoc-Signatur).

    Sobald Microsoft das rechtliche Dokument erhält, führt Microsoft Cmdlets aus, um die Datenbereinigung auszulösen, die zuerst die Richtlinie löscht, die Postfächer für das dauerhafte Löschen markiert und dann den Verfügbarkeitsschlüssel löscht. Sobald der Datenbereinigungsprozess abgeschlossen ist, wurden die Daten gelöscht, der Exchange Online nicht mehr möglich und kann nicht wiederhergestellt werden.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Widerrufen Ihrer Kundenschlüssel und des Verfügbarkeitsschlüssels für SharePoint Online-, OneDrive for Business- und Teams Dateien

Führen Sie die folgenden Schritte aus, um den Datenbereinigungspfad für SharePoint Online-, OneDrive for Business- und Teams zu initiieren:

1. Widerrufen des Azure Key Vault-Zugriffs. Alle Schlüsseltresoradministratoren müssen zustimmen, den Zugriff zu widerrufen.

   Sie löschen den Azure Key Vault für SharePoint Online. Schlüsseltresor können von mehreren SharePoint Und DEPs gemeinsam genutzt werden.

2. Wenden Sie sich an Microsoft, um den Verfügbarkeitsschlüssel zu löschen.

    Wenn Sie microsoft kontaktieren, um den Verfügbarkeitsschlüssel zu löschen, senden wir Ihnen ein rechtliches Dokument. Die Person in Ihrer Organisation, die sich während des Onboardings als genehmigende Person im FastTrack-Angebot angemeldet hat, muss dieses Dokument signieren. Normalerweise handelt es sich dabei um eine Führungskraft oder eine andere benannte Person in Ihrem Unternehmen, die gesetzlich autorisiert ist, den Papierkram im Namen Ihrer Organisation zu signieren.

3. Sobald Ihr Vertreter das rechtliche Dokument signiert hat, geben Sie es an Microsoft zurück (in der Regel über eine eDoc-Signatur).

   Sobald Microsoft das rechtliche Dokument erhält, führen wir Cmdlets aus, um die Datenbereinigung auszulösen, die die Kryptografielöschung des Mandantenschlüssels, des Websiteschlüssels und aller einzelnen Schlüssel pro Dokument durchführt, wodurch die Schlüsselhierarchie unwiderruflich gebrochen wird. Nachdem die Datenbereinigungs-Cmdlets abgeschlossen sind, wurden Ihre Daten gelöscht.

## <a name="related-articles"></a>Verwandte Artikel

- [Dienstverschlüsselung mit Kundenschlüssel](customer-key-overview.md)

- [Informationen zum Verfügbarkeitsschlüssel](customer-key-availability-key-understand.md)

- [Einrichten des Kundenschlüssels](customer-key-set-up.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Dienstverschlüsselung](office-365-service-encryption.md)