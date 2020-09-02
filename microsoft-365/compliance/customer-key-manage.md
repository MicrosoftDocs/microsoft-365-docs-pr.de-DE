---
title: Verwalten des Kunden Schlüssels
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
description: Nachdem Sie den Kundenschlüssel eingerichtet haben, erfahren Sie, wie Sie ihn verwalten, indem Sie AKV-Schlüssel wiederherstellen und Berechtigungen und Daten Verschlüsselungsrichtlinien verwalten.
ms.openlocfilehash: 8f5f23fa1b8ce8baa8fafd3f29ca5fb8905887a1
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324257"
---
# <a name="manage-customer-key"></a>Verwalten des Kunden Schlüssels

Nachdem Sie den Kundenschlüssel für Office 365 eingerichtet haben, können Sie die Schlüssel wie in diesem Artikel beschrieben verwalten. Erfahren Sie mehr über den Kundenschlüssel in den verwandten Themen.

## <a name="restore-azure-key-vault-keys"></a>Wiederherstellen von Azure Key Vault-Schlüsseln

Verwenden Sie vor dem Ausführen einer Wiederherstellung die von Soft Delete bereitgestellten Wiederherstellungsfunktionen. Für alle mit Customer Key verwendeten Schlüssel muss Soft Delete aktiviert sein. Soft Delete wirkt wie ein Recycling-Mülleimer und ermöglicht die Wiederherstellung von bis zu 90 Tagen, ohne dass eine Wiederherstellung erforderlich ist. Eine Wiederherstellung sollte nur unter extremen und außergewöhnlichen Umständen erforderlich sein, beispielsweise, wenn ein Schlüssel oder ein Schlüsseltresor verloren geht. Wenn Sie einen Schlüssel zur Verwendung mit Customer Key wiederherstellen müssen, führen Sie in Azure PowerShell das Cmdlet „Restore-AzureKeyVaultKey“ wie folgt aus:
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

Beispiel:
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

Wenn der schlüsseltresor bereits einen Schlüssel mit dem gleichen Namen enthält, schlägt der Wiederherstellungsvorgang fehl. Restore-AzKeyVaultKey stellt alle Schlüssel Versionen und alle Metadaten für den Schlüssel einschließlich des Schlüssel namens wieder her.
  
## <a name="manage-key-vault-permissions"></a>Verwalten von Schlüsseltresor-Berechtigungen

Mehrere Cmdlets stehen zur Verfügung, mit denen Sie die Schlüsseltresor-Berechtigungen ansehen und, falls erforderlich, entfernen können. Möglicherweise müssen Sie Berechtigungen entfernen, beispielsweise, wenn ein Mitarbeiter das Team verlässt. Für jede dieser Aufgaben wird Azure PowerShell verwendet. Informationen zu Azure PowerShell finden Sie unter [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).

Führen Sie das Cmdlet Get-AzKeyVault aus, um die schlüsseltresor-Berechtigungen anzuzeigen.

```powershell
Get-AzKeyVault -VaultName <vault name>
```

Zum Beispiel:

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

Um die Berechtigungen eines Administrators zu entfernen, führen Sie das Cmdlet Remove-AzKeyVaultAccessPolicy aus:
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

Zum Beispiel:

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a>Verwalten von Daten Verschlüsselungsrichtlinien (DEPs) mit dem Kundenschlüssel

Kundenschlüssel behandelt DEPs unterschiedlich zwischen den verschiedenen Diensten. Sie können beispielsweise eine andere Anzahl von DEPs für die verschiedenen Dienste erstellen.

**Exchange Online und Skype for Business:** Sie können bis zu 50 DEPs erstellen. Anweisungen finden Sie unter [Erstellen einer Daten Verschlüsselungsrichtlinie (DEP) für die Verwendung mit Exchange Online und Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).

**SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien:** Eine DEP gilt für Daten an einem geografischen Standort, der auch als _Geo_bezeichnet wird. Wenn Sie das Multi-Geo-Feature von Office 365 verwenden, können Sie eine Datenverschlüsselungsrichtlinie (DEP) pro Geo erstellen. Wenn Sie keine Multi-Geo-Daten verwenden, können Sie eine DEP erstellen. Normalerweise erstellen Sie die Datenausführungsverhinderung, wenn Sie den Kundenschlüssel einrichten. Anweisungen finden Sie unter [Erstellen einer Daten Verschlüsselungsrichtlinie (DEP) für jede SharePoint Online und OneDrive für Unternehmen Geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a>Anzeigen der DEPs, die Sie für Exchange Online und Skype for Business erstellt haben

Führen Sie die folgenden Schritte aus, um eine Liste aller DEPs anzuzeigen, die Sie für Exchange Online und Skype for Business mithilfe des PowerShell-Cmdlets "Get-DataEncryptionPolicy" erstellt haben.

1. Wenn Sie ein Arbeits-oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Organisation verwenden möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

2. Wenn Sie alle DEPs in Ihrer Organisation zurückgeben möchten, führen Sie das Cmdlet Get-DataEncryptionPolicy ohne Parameter aus.

   ```powershell
   Get-DataEncryptionPolicy
   ```

   Weitere Informationen zum Get-DataEncryptionPolicy-Cmdlet finden Sie unter [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps).

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a>Zuweisen einer Datenausführungsverhinderung vor der Migration eines Postfachs in die Cloud

Wenn Sie die Datenausführungsverhinderung zuweisen, verschlüsselt Microsoft 365 die Inhalte des Postfachs mithilfe der zugewiesenen DEP während der Migration. Dieser Prozess ist effizienter als die Migration des Postfachs, das Zuweisen der Datenausführungsverhinderung und das anschließende warten auf die Verschlüsselung, was Stunden oder möglicherweise Tage dauern kann.

Führen Sie das Cmdlet "MailUser" in Exchange Online PowerShell aus, um einem Postfach eine Datenausführungsverhinderung zuzuweisen, bevor Sie es zu Office 365 migrieren:

1. Wenn Sie ein Arbeits-oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Organisation verwenden möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

2. Führen Sie das Cmdlet "Sets-MailUser" aus.

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   Dabei gibt *GeneralMailboxOrMailUserIdParameter* ein Postfach an, und *DataEncryptionPolicyIdParameter* ist die ID der DEP. Weitere Informationen zum Cmdlet "MailUser" finden Sie unter [festlegen-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps).

### <a name="determine-the-dep-assigned-to-a-mailbox"></a>Ermitteln der Datenverschlüsselungsrichtlinie (DEP), die einem Postfach zugewiesen ist

Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um zu ermitteln, welche Datenverschlüsselungsrichtlinie (DEP) einem Postfach zugewiesen ist. Das Cmdlet meldet einen eindeutigen Bezeichner (GUID) zurück.
  
1. Wenn Sie ein Arbeits-oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Organisation verwenden möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   Dabei gibt *GeneralMailboxOrMailUserIdParameter* ein Postfach an, und DataEncryptionPolicyID gibt die GUID der Datenausführungsverhinderung zurück. Weitere Informationen zum Cmdlet „Get-MailboxStatistics“ finden Sie unter [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps).
  
2. Führen Sie das Cmdlet Get-DataEncryptionPolicy aus, um den Anzeigenamen der DEP zu ermitteln, der das Postfach zugewiesen ist.
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   Dabei ist der *GUID* derjenige GUID, der vom Cmdlet „Get-MailboxStatistics“ im vorherigen Schritt zurückgemeldet wurde.

## <a name="verify-that-customer-key-has-finished-encryption"></a>Sicherstellen, dass der Kundenschlüssel die Verschlüsselung abgeschlossen hat

Unabhängig davon, ob Sie einen Kundenschlüssel gerollt, eine neue DEP zugewiesen oder ein Postfach migriert haben, verwenden Sie die Schritte in diesem Abschnitt, um sicherzustellen, dass die Verschlüsselung abgeschlossen ist.

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a>Überprüfen, ob die Verschlüsselung für Exchange Online und Skype for Business abgeschlossen ist

Das Verschlüsseln eines Postfachs kann einige Zeit in Anspruch nehmen. Wir empfehlen, dass Sie 72 Stunden warten, bevor Sie versuchen, die Verschlüsselung nach dem Ändern einer Datenverschlüsselungsrichtlinie (DEP) oder nach dem erstmaligen Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach zu überprüfen.
  
Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um festzustellen, ob ein Postfach verschlüsselt ist.
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

Die IsEncrypted-Eigenschaft meldet den Wert **True** (Richtig), wenn das Postfach verschlüsselt ist, und den Wert **False** (Falsch), wenn das Postfach nicht verschlüsselt ist.

Die Zeit bis zum Abschließen der Postfachverschiebungen hängt von der Größe des Postfachs ab. Wenn der Kundenschlüssel das Postfach nach 72 Stunden nach dem Zuweisen einer neuen DEP nicht vollständig verschlüsselt hat, wenden Sie sich an den Microsoft-Support, um Hilfe zu erhalten. Das Cmdlet New-MoveRequest ist für Verschiebungen von lokalen Postfächern nicht mehr verfügbar. Weitere Informationen erhalten Sie in [dieser Ankündigung](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) .

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Überprüfen, ob die Verschlüsselung für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien abgeschlossen ist

Überprüfen Sie den Verschlüsselungsstatus, indem Sie das Cmdlet Get-SPODataEncryptionPolicy wie folgt ausführen:

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

Die Ausgabe dieses Cmdlets umfasst Folgendes:
  
- URI des Primärschlüssels.

- URI des Sekundärschlüssels.

- Verschlüsselungsstatus für den Geo. Mögliche weitere Angaben:

  - **Unregistered:** (Nicht registriert) Die Customer Key-Verschlüsselung wurde noch nicht angewendet.

  - **Registering:** (Registrierung läuft) Die Customer Key-Verschlüsselung wurde angewendet wurde und Ihre Dateien werden gegenwärtig gerade verschlüsselt. Wenn der Schlüssel für den Geo registriert ist, werden Ihnen auch Informationen darüber angezeigt, wie viel Prozent der Websites in der Geo abgeschlossen sind, damit Sie den Verschlüsselungs Fortschritt überwachen können.

  - **Registered:** (Registriert) Die Customer Key- Verschlüsselung wurde angewendet, und alle Dateien auf allen Websites wurden verschlüsselt.

  - **Rolling:** Das Erstellen eines sich fortlaufend ändernden, sogenannten Rolling-Codes für den Schlüssel ist in Gang. Wenn der Schlüssel für den Geo rollt, werden Ihnen auch Informationen darüber angezeigt, wie viel Prozent der Websites den Schlüsselrollen Vorgang abgeschlossen haben, damit Sie den Fortschritt überwachen können.

## <a name="unassign-a-dep-from-a-mailbox"></a>Aufheben der Zuweisung einer Datenausführungsverhinderung von einem Postfach

Sie heben die Zuweisung einer Datenausführungsverhinderung von einem Postfach mithilfe des PowerShell-Cmdlets "Cmdlet" und Festlegen von `DataEncryptionPolicy` auf auf zurück `$NULL` . Durch das Ausführen dieses Cmdlets wird die Zuweisung der derzeit zugewiesenen DEP aufgehoben und das Postfach mithilfe der DEP, die den standardmäßigen Microsoft-verwalteten Schlüsseln zugeordnet ist, erneut verschlüsselt. Sie können die Zuweisung der Datenausführungsverhinderung für von Microsoft verwaltete Schlüssel nicht aufheben. Wenn Sie keine verwalteten Microsoft-Schlüssel verwenden möchten, können Sie dem Postfach eine weitere DEP zuweisen.

Führen Sie die folgenden Schritte aus, um die Zuweisung der Datenausführungsverhinderung von einem Postfach mithilfe des PowerShell-Cmdlets für die Gruppe zu beenden.

1. Wenn Sie ein Arbeits-oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Organisation verwenden möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).

2. Führen Sie das Cmdlet "festgelegt-Postfach" aus.

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a>Widerrufen von Schlüsseln und Starten des Prozesses zur Bereinigung des Datenpfads

Sie steuern die Sperrung aller Stammschlüssel, einschließlich des Verfügbarkeits Schlüssels. Kundenschlüssel bietet Ihnen die Kontrolle über den Aspekt der Beendigungs Planung der behördlichen Anforderungen. Wenn Sie Ihre Schlüssel widerrufen, um Ihre Daten zu löschen und den Dienst zu beenden, löscht der Dienst den Verfügbarkeits Schlüssel nach Abschluss des Daten Löschvorgangs.

Microsoft 365 überwacht und validiert den Pfad zur Datenbereinigung. Weitere Informationen finden Sie im SSAE 18 SOC 2-Bericht, der im [Dienst Vertrauensstellungs Portal](https://servicetrust.microsoft.com/)zur Verfügung steht. Darüber hinaus empfiehlt Microsoft die folgenden Dokumente:

- [Leitfaden für Risikobewertung und Compliance für Finanzinstitute in der Microsoft-Cloud](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [O365-Exit-Planungsüberlegungen](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

Der Pfad der Datenbereinigung unterscheidet sich geringfügig zwischen den verschiedenen Diensten.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a>Widerrufen Sie Ihre Kundenschlüssel und den Verfügbarkeits Schlüssel für Exchange Online und Skype for Business

Wenn Sie den Pfad zum Löschen von Daten für Exchange Online und Skype for Business initiieren, legen Sie eine permanente Daten Löschanforderung für eine DEP fest. Dadurch werden verschlüsselte Daten in den Postfächern, denen diese Ausführungsverhinderung zugewiesen ist, dauerhaft gelöscht.

Da Sie das PowerShell-Cmdlet nur für jeweils eine DEP ausführen können, sollten Sie vor dem Initiieren des Daten Bereinigungs Pfads eine einzelne Ausführungsverhinderung allen ihren Postfächern erneut zuweisen.

> [!WARNING]
> Verwenden Sie nicht den Daten Lösch Pfad, um eine Teilmenge ihrer Postfächer zu löschen. Dieser Prozess ist nur für Kunden vorgesehen, die den Dienst beenden.

Führen Sie die folgenden Schritte aus, um den Pfad der Datenbereinigung zu initiieren:

1. Entfernen Sie Wrap-und Unwrap-Berechtigungen für "O365 Exchange Online" aus Azure Key Vaults.

2. Stellen Sie eine [Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps), indem Sie ein Arbeits-oder Schulkonto mit globalen Administratorrechten in Ihrer Organisation verwenden.

3. Führen Sie für jede DEP, die Postfächer enthält, die Sie löschen möchten, das Cmdlet " [DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) " wie folgt aus.

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   Wenn der Befehl fehlschlägt, stellen Sie sicher, dass Sie die Exchange Online Berechtigungen aus beiden Schlüsseln in Azure Key Vault entfernt haben, wie weiter oben in dieser Aufgabe angegeben.Nachdem Sie den Parametern permanentdatapurgerequested-Switch mit dem Cmdlet "DataEncryptionPolicy" festgelegt haben, können Sie diese DEP nicht mehr Postfächern zuweisen.

4. Wenden Sie sich an den Microsoft-Support, und fordern Sie die Datenbereinigung eDocument.

    Auf Ihre Anfrage hin sendet Microsoft Ihnen ein rechtliches Dokument zur Bestätigung und Autorisierung der Löschung von Daten. Die Person in Ihrer Organisation, die sich als genehmigende Person im Angebot beim Onboarding angemeldet hat, muss dieses Dokument signieren. Normalerweise handelt es sich dabei um eine Führungskraft oder eine andere designierte Person in Ihrem Unternehmen, die rechtlich befugt ist, die Unterlagen im Namen Ihrer Organisation zu signieren.

5. Wenn Ihr Vertreter das rechtliche Dokument unterzeichnet hat, senden Sie es an Microsoft (in der Regel über eine edoc-Signatur).

    Sobald Microsoft das Dokument "Legal" erhält, führt Microsoft Cmdlets aus, um die Datenbereinigung auszulösen, die die Richtlinie zuerst löscht, die Postfächer für einen permanenten Löschvorgang markiert und dann den Verfügbarkeits Schlüssel löscht. Nachdem der Daten Löschvorgang abgeschlossen wurde, wurden die Daten bereinigt, können nicht auf Exchange Online zugegriffen werden und sind nicht wiederherstellbar.

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a>Widerrufen von Kunden Schlüsseln und dem Verfügbarkeits Schlüssel für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien

Führen Sie die folgenden Schritte aus, um den Daten Lösch Pfad für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien zu initiieren:

1. Sperren Sie den Azure Key Vault-Zugriff. Alle Key Vault-Administratoren müssen zustimmen, den Zugriff aufzuheben.

   Sie löschen nicht den Azure-schlüsseltresor für SharePoint Online. Schlüssel Tresore können von mehreren SharePoint Online Mandanten und DEPs gemeinsam verwendet werden.

2. Wenden Sie sich an Microsoft, um den Verfügbarkeits Schlüssel zu löschen.

    Wenn Sie sich an Microsoft wenden, um den Verfügbarkeits Schlüssel zu löschen, erhalten Sie ein rechtliches Dokument. Die Person in Ihrer Organisation, die sich als genehmigende Person im Angebot beim Onboarding angemeldet hat, muss dieses Dokument signieren. Normalerweise handelt es sich um eine Führungskraft oder eine andere designierte Person in Ihrem Unternehmen, die rechtlich befugt ist, die Unterlagen im Namen Ihrer Organisation zu signieren.

3. Wenn Ihr Vertreter das rechtliche Dokument signiert, senden Sie es an Microsoft (in der Regel über eine edoc-Signatur).

   Sobald Microsoft das Dokument "Legal" erhält, führen wir Cmdlets aus, um die Datenbereinigung auszulösen, die das kryptografische Löschen des Mandanten Schlüssels, des Standort Schlüssels und aller einzelnen Einzeldokument Schlüssel ausführt, wodurch die Schlüsselhierarchie unwiderruflich unterbrochen wird. Nachdem die Cmdlets für die Datenbereinigung abgeschlossen wurden, wurden die Daten gelöscht.

## <a name="related-articles"></a>Verwandte Artikel

- [Dienstverschlüsselung mit dem Kundenschlüssel](customer-key-overview.md)

- [Informationen zum Verfügbarkeits Schlüssel](customer-key-availability-key-understand.md)

- [Einrichten des Kunden Schlüssels](customer-key-set-up.md)

- [Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels](customer-key-availability-key-roll.md)

- [Customer Lockbox](customer-lockbox-requests.md)

- [Dienst Verschlüsselung](office-365-service-encryption.md)
