---
title: Verwalten des Kundenschlüssels
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 02/05/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: Nachdem Sie den Kundenschlüssel eingerichtet haben, erfahren Sie, wie Sie ihn verwalten, indem Sie AKV-Schlüssel wiederherstellen und Berechtigungen und Ihre Datenverschlüsselungsrichtlinien verwalten.
ms.openlocfilehash: 284a8ff24fef2f7e8b807477c99e20aaf593552e
ms.sourcegitcommit: 94fa3e57fa6505551d84ae7b458150dceff30db7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/26/2021
ms.locfileid: "51394667"
---
# <a name="manage-customer-key"></a>Verwalten des Kundenschlüssels

Nachdem Sie den Kundenschlüssel für Office 365 eingerichtet haben, können Sie Ihre Schlüssel wie in diesem Artikel beschrieben verwalten. Weitere Informationen zum Kundenschlüssel finden Sie in den zugehörigen Themen.

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

Mehrere Cmdlets stehen zur Verfügung, mit denen Sie die Schlüsseltresor-Berechtigungen ansehen und, falls erforderlich, entfernen können. Möglicherweise müssen Sie Berechtigungen entfernen, beispielsweise, wenn ein Mitarbeiter das Team verlässt. Für jede dieser Aufgaben verwenden Sie Azure PowerShell. Weitere Informationen zu Azure Powershell finden Sie [unter Overview of Azure PowerShell](/powershell/azure/).

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

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>Verwalten von Datenverschlüsselungsrichtlinien (DATA Encryption Policies, DEPs) mit dem Kundenschlüssel

Customer Key behandelt DEPs zwischen den verschiedenen Diensten unterschiedlich. Sie können z. B. eine andere Anzahl von DEPs für die verschiedenen Dienste erstellen.

**Exchange Online und Skype for Business:** Sie können bis zu 50 DEPs erstellen. Anweisungen finden Sie unter [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).

**SharePoint Online-, OneDrive for Business- und #A0** Eine DEP gilt für Daten an einem geografischen Standort, auch geo _genannt._ Wenn Sie das Multi-Geo-Feature von Office 365 verwenden, können Sie eine Datenverschlüsselungsrichtlinie (DEP) pro Geo erstellen. Wenn Sie multi-geo nicht verwenden, können Sie eine DEP erstellen. Normalerweise erstellen Sie die DEP beim Einrichten des Kundenschlüssels. Anweisungen finden Sie unter [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Anzeigen der dePs, die Sie für Exchange Online und Skype for Business erstellt haben

Führen Sie die folgenden Schritte aus, um eine Liste aller DEPs zu sehen, die Sie für Exchange Online und Skype for Business mithilfe des Get-DataEncryptionPolicy PowerShell-Cmdlets erstellt haben.

1. Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [eine Verbindung mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Führen Sie zum Zurückgeben aller DEPs in Ihrer Organisation das cmdlet Get-DataEncryptionPolicy parameterfrei aus.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Weitere Informationen zum cmdlet Get-DataEncryptionPolicy finden Sie unter [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Zuweisen einer DEP vor der Migration eines Postfachs in die Cloud

Wenn Sie die DEP zuweisen, verschlüsselt Microsoft 365 den Inhalt des Postfachs mithilfe der zugewiesenen DEP während der Migration. Dieser Vorgang ist effizienter als das Migrieren des Postfachs, das Zuweisen der DEP und dann das Warten auf die Verschlüsselung, was Stunden oder möglicherweise Tage dauern kann.

Führen Sie zum Zuweisen einer DEP zu einem Postfach vor der Migration zu Office 365 das cmdlet Set-MailUser in Exchange Online PowerShell aus:

1. Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [eine Verbindung mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Führen Sie Set-MailUser cmdlet aus.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Dabei *gibt GeneralMailboxOrMailUserIdParameter* ein Postfach an, und *DataEncryptionPolicyIdParameter* ist die ID der DEP. Weitere Informationen zum cmdlet Set-MailUser finden Sie unter [Set-MailUser](/powershell/module/exchange/set-mailuser).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Ermitteln der Datenverschlüsselungsrichtlinie (DEP), die einem Postfach zugewiesen ist

Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um zu ermitteln, welche Datenverschlüsselungsrichtlinie (DEP) einem Postfach zugewiesen ist. Das Cmdlet meldet einen eindeutigen Bezeichner (GUID) zurück.
  
1. Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [eine Verbindung mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)

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

Ob Sie gerade einen Kundenschlüssel gerollt, eine neue DEP zugewiesen oder ein Postfach migriert haben, führen Sie die Schritte in diesem Abschnitt aus, um sicherzustellen, dass die Verschlüsselung abgeschlossen ist.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Überprüfen, ob die Verschlüsselung für Exchange Online und Skype for Business abgeschlossen ist

Das Verschlüsseln eines Postfachs kann einige Zeit in Anspruch nehmen. Wir empfehlen, dass Sie 72 Stunden warten, bevor Sie versuchen, die Verschlüsselung nach dem Ändern einer Datenverschlüsselungsrichtlinie (DEP) oder nach dem erstmaligen Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach zu überprüfen.
  
Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um festzustellen, ob ein Postfach verschlüsselt ist.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Die IsEncrypted-Eigenschaft meldet den Wert **True** (Richtig), wenn das Postfach verschlüsselt ist, und den Wert **False** (Falsch), wenn das Postfach nicht verschlüsselt ist.

Die Zeit zum Abschließen von Postfachbewegungen hängt von der Größe des Postfachs ab. Wenn der Kundenschlüssel das Postfach nach 72 Stunden nach dem Zuweisen einer neuen DEP nicht vollständig verschlüsselt hat, wenden Sie sich an den Microsoft-Support, um Hilfe zu erhalten. Das New-MoveRequest cmdlet ist nicht mehr für lokale Postfachbewegungen verfügbar. Weitere Informationen [finden Sie in](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) dieser Ankündigung.

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Überprüfen, ob die Verschlüsselung für SharePoint Online-, OneDrive for Business- und #A0 abgeschlossen ist

Überprüfen Sie den Status der Verschlüsselung, indem Sie Get-SPODataEncryptionPolicy cmdlet wie folgt ausführen:

```powershell
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

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a>Rollback vom Kundenschlüssel zu verwalteten Schlüsseln von Microsoft

Für Kundenschlüssel auf Mandantenebene müssen Sie microsoft mit einer Anforderung für "offboarding" über den Kundenschlüssel erreichen. Die Anforderung wird vom On Call Engineering-Team verarbeitet.

Für Kundenschlüssel auf Anwendungsebene müssen Sie dazu eine DEP mithilfe des PowerShell-Cmdlets Set-mailbox aus Postfächern zuweisen und auf `DataEncryptionPolicy` `$NULL` festlegen. Wenn Sie dieses Cmdlet ausführen, wird die derzeit zugewiesene DEP entfernt und das Postfach mithilfe der DEP erneut verschlüsselt, die den verwalteten Standardschlüsseln von Microsoft zugeordnet ist. Die von verwalteten Schlüsseln von Microsoft verwendete DEP kann nicht entfernt werden. Wenn Sie keine verwalteten Schlüssel von Microsoft verwenden möchten, können Sie dem Postfach eine weitere Customer Key DEP zuweisen.

Führen Sie die folgenden Schritte aus, um die DEP mithilfe des Set-Mailbox PowerShell-Cmdlets aus einem Postfach zuzuweisen.

1. Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [eine Verbindung mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)

2. Führen Sie Set-Mailbox cmdlet aus.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Widerrufen Der Schlüssel und Starten des Datenbereinigungspfadprozesses

Sie steuern den Widerruf aller Stammschlüssel, einschließlich des Verfügbarkeitsschlüssels. Customer Key bietet die Kontrolle über den Aspekt der Beendigungsplanung der gesetzlichen Anforderungen für Sie. Wenn Sie ihre Schlüssel widerrufen möchten, um Ihre Daten zu löschen und den Dienst zu beenden, löscht der Dienst den Verfügbarkeitsschlüssel, sobald der Datenlöschvorgang abgeschlossen ist. Sie können keine Datenbereinigung für eine Richtlinie auf Mandantenebene ausführen.

Microsoft 365 überwacht und überprüft den Datenbereinigungspfad. Weitere Informationen finden Sie im SSAE 18 SOC 2-Bericht, der im [Service Trust Portal verfügbar ist.](https://servicetrust.microsoft.com/) Darüber hinaus empfiehlt Microsoft die folgenden Dokumente:

- [Leitfaden zur Risikobewertung und Compliance für Finanzinstitute in der Microsoft Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [Überlegungen zur O365-Beendigungsplanung](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Der Datenbereinigungspfad unterscheidet sich geringfügig zwischen den verschiedenen Diensten.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Widerrufen Ihrer Kundenschlüssel und des Verfügbarkeitsschlüssels für Exchange Online und Skype for Business

Wenn Sie den Pfad zur Datenbereinigung für Exchange Online und Skype for Business initiieren, legen Sie eine permanente Datenbereinigungsanforderung für eine DEP fest. Dadurch werden verschlüsselte Daten in den Postfächern, denen diese DEP zugewiesen ist, dauerhaft gelöscht.

Da Sie das PowerShell-Cmdlet nur für eine DEP gleichzeitig ausführen können, sollten Sie eine einzelne DEP allen Postfächern erneut zuweisen, bevor Sie den Datenbereinigungspfad initiieren.

> [!WARNING]
> Verwenden Sie nicht den Pfad zum Löschen von Daten, um eine Teilmenge Ihrer Postfächer zu löschen. Dieser Vorgang ist nur für Kunden gedacht, die den Dienst verlassen.

Führen Sie die folgenden Schritte aus, um den Datenbereinigungspfad zu initiieren:

1. Entfernen von Umbruch- und Auspackberechtigungen für "O365 Exchange Online" aus Azure Key Vaults.

2. Stellen Sie mithilfe eines Arbeits- oder Schulkontos mit globalen Administratorrechten in Ihrer Organisation eine Verbindung [mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)

3. Führen Sie für jede DEP, die zu löschende Postfächer enthält, das [Cmdlet Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) wie folgt aus.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Wenn der Befehl fehlschlägt, stellen Sie sicher, dass Sie die Exchange Online-Berechtigungen aus beiden Schlüsseln in Azure Key Vault entfernt haben, wie weiter oben in dieser Aufgabe angegeben.Nachdem Sie den Switch PermanentDataPurgeRequested mit dem cmdlet Set-DataEncryptionPolicy festgelegt haben, können Sie diese DEP nicht mehr Postfächern zuweisen.

4. Wenden Sie sich an den Microsoft-Support, und fordern Sie das Data Purge eDocument an.

    Auf Ihre Anfrage sendet Microsoft Ihnen ein rechtliches Dokument, um die Löschung von Daten zu bestätigen und zu autorisieren. Die Person in Ihrer Organisation, die sich während des Onboardings als genehmigende Person im FastTrack-Angebot angemeldet hat, muss dieses Dokument signieren. Normalerweise handelt es sich dabei um eine Führungskraft oder eine andere benannte Person in Ihrem Unternehmen, die berechtigt ist, den Papierkram im Namen Ihrer Organisation zu signieren.

5. Nachdem Ihr Vertreter das rechtliche Dokument signiert hat, geben Sie es an Microsoft zurück (in der Regel über eine eDoc-Signatur).

    Sobald Microsoft das rechtliche Dokument erhält, führt Microsoft Cmdlets aus, um die Datenbereinigung auszulösen, die zuerst die Richtlinie löscht, die Postfächer für das dauerhafte Löschen markiert und dann den Verfügbarkeitsschlüssel löscht. Sobald der Datenbereinigungsprozess abgeschlossen ist, wurden die Daten gelöscht, auf Exchange Online kann nicht zugegriffen werden und kann nicht wiederhergestellt werden.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a>Widerrufen Ihrer Kundenschlüssel und des Verfügbarkeitsschlüssels für SharePoint Online-, OneDrive for Business- und #A0

Führen Sie die folgenden Schritte aus, um den Datenbereinigungspfad für SharePoint Online-, OneDrive for Business- und #A0 zu initiieren:

1. Widerrufen des Azure Key Vault-Zugriffs. Alle Schlüsseltresoradministratoren müssen zustimmen, den Zugriff zu widerrufen.

   Sie löschen den Azure Key Vault für SharePoint Online nicht. Schlüsseltresor können für mehrere SharePoint Online-Mandanten und DEPs freigegeben werden.

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