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
ms.openlocfilehash: dbdbd61b4d06e183d8cc5461122e316b2b6b1797
ms.sourcegitcommit: 40ec697e27b6c9a78f2b679c6f5a8875dacde943
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/23/2020
ms.locfileid: "44352202"
---
# <a name="manage-customer-key"></a><span data-ttu-id="1f568-103">Verwalten des Kunden Schlüssels</span><span class="sxs-lookup"><span data-stu-id="1f568-103">Manage Customer Key</span></span>

<span data-ttu-id="1f568-104">Nachdem Sie den Kundenschlüssel für Office 365 eingerichtet haben, können Sie die Schlüssel wie in diesem Artikel beschrieben verwalten.</span><span class="sxs-lookup"><span data-stu-id="1f568-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="1f568-105">Erfahren Sie mehr über den Kundenschlüssel in den verwandten Themen.</span><span class="sxs-lookup"><span data-stu-id="1f568-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="1f568-106">Wiederherstellen von Azure Key Vault-Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="1f568-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="1f568-107">Verwenden Sie vor dem Ausführen einer Wiederherstellung die von Soft Delete bereitgestellten Wiederherstellungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="1f568-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="1f568-108">Für alle mit Customer Key verwendeten Schlüssel muss Soft Delete aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="1f568-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="1f568-109">Soft Delete wirkt wie ein Recycling-Mülleimer und ermöglicht die Wiederherstellung von bis zu 90 Tagen, ohne dass eine Wiederherstellung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1f568-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="1f568-110">Eine Wiederherstellung sollte nur unter extremen und außergewöhnlichen Umständen erforderlich sein, beispielsweise, wenn ein Schlüssel oder ein Schlüsseltresor verloren geht.</span><span class="sxs-lookup"><span data-stu-id="1f568-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="1f568-111">Wenn Sie einen Schlüssel zur Verwendung mit Customer Key wiederherstellen müssen, führen Sie in Azure PowerShell das Cmdlet „Restore-AzureKeyVaultKey“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="1f568-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="1f568-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f568-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="1f568-113">Wenn der schlüsseltresor bereits einen Schlüssel mit dem gleichen Namen enthält, schlägt der Wiederherstellungsvorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="1f568-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="1f568-114">Restore-AzKeyVaultKey stellt alle Schlüssel Versionen und alle Metadaten für den Schlüssel einschließlich des Schlüssel namens wieder her.</span><span class="sxs-lookup"><span data-stu-id="1f568-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="1f568-115">Verwalten von Schlüsseltresor-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="1f568-115">Manage key vault permissions</span></span>

<span data-ttu-id="1f568-116">Mehrere Cmdlets stehen zur Verfügung, mit denen Sie die Schlüsseltresor-Berechtigungen ansehen und, falls erforderlich, entfernen können.</span><span class="sxs-lookup"><span data-stu-id="1f568-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="1f568-117">Möglicherweise müssen Sie Berechtigungen entfernen, beispielsweise, wenn ein Mitarbeiter das Team verlässt.</span><span class="sxs-lookup"><span data-stu-id="1f568-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="1f568-118">Für jede dieser Aufgaben wird Azure PowerShell verwendet.</span><span class="sxs-lookup"><span data-stu-id="1f568-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="1f568-119">Informationen zu Azure PowerShell finden Sie unter [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="1f568-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="1f568-120">Führen Sie das Cmdlet Get-AzKeyVault aus, um die schlüsseltresor-Berechtigungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1f568-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="1f568-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f568-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="1f568-122">Um die Berechtigungen eines Administrators zu entfernen, führen Sie das Cmdlet Remove-AzKeyVaultAccessPolicy aus:</span><span class="sxs-lookup"><span data-stu-id="1f568-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="1f568-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f568-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="1f568-124">Verwalten von Daten Verschlüsselungsrichtlinien (DEPs) mit dem Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="1f568-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="1f568-125">Kundenschlüssel behandelt DEPs unterschiedlich zwischen den verschiedenen Diensten.</span><span class="sxs-lookup"><span data-stu-id="1f568-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="1f568-126">Sie können beispielsweise eine andere Anzahl von DEPs für die verschiedenen Dienste erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f568-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="1f568-127">**Exchange Online und Skype for Business:** Sie können bis zu 50 DEPs erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f568-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="1f568-128">Anweisungen finden Sie unter [Erstellen einer Daten Verschlüsselungsrichtlinie (DEP) für die Verwendung mit Exchange Online und Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="1f568-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="1f568-129">**SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien:** Eine DEP gilt für Daten an einem geografischen Standort, der auch als _Geo_bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="1f568-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="1f568-130">Wenn Sie das Multi-Geo-Feature von Office 365 verwenden, können Sie eine Datenverschlüsselungsrichtlinie (DEP) pro Geo erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f568-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="1f568-131">Wenn Sie keine Multi-Geo-Daten verwenden, können Sie eine DEP erstellen.</span><span class="sxs-lookup"><span data-stu-id="1f568-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="1f568-132">Normalerweise erstellen Sie die Datenausführungsverhinderung, wenn Sie den Kundenschlüssel einrichten.</span><span class="sxs-lookup"><span data-stu-id="1f568-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="1f568-133">Anweisungen finden Sie unter [Erstellen einer Daten Verschlüsselungsrichtlinie (DEP) für jede SharePoint Online und OneDrive für Unternehmen Geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span><span class="sxs-lookup"><span data-stu-id="1f568-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="1f568-134">Anzeigen der DEPs, die Sie für Exchange Online und Skype for Business erstellt haben</span><span class="sxs-lookup"><span data-stu-id="1f568-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="1f568-135">Führen Sie die folgenden Schritte aus, um eine Liste aller DEPs anzuzeigen, die Sie für Exchange Online und Skype for Business mithilfe des PowerShell-Cmdlets "Get-DataEncryptionPolicy" erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="1f568-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="1f568-136">Wenn Sie ein Arbeits-oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Organisation verwenden möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="1f568-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="1f568-137">Wenn Sie alle DEPs in Ihrer Organisation zurückgeben möchten, führen Sie das Cmdlet Get-DataEncryptionPolicy ohne Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="1f568-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

  ```powershell
  Get-DataEncryptionPolicy
  ```

  <span data-ttu-id="1f568-138">Weitere Informationen zum Get-DataEncryptionPolicy-Cmdlet finden Sie unter [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="1f568-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="1f568-139">Zuweisen einer Datenausführungsverhinderung vor der Migration eines Postfachs in die Cloud</span><span class="sxs-lookup"><span data-stu-id="1f568-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="1f568-140">Wenn Sie die Datenausführungsverhinderung zuweisen, verschlüsselt Microsoft 365 die Inhalte des Postfachs mithilfe der zugewiesenen DEP während der Migration.</span><span class="sxs-lookup"><span data-stu-id="1f568-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="1f568-141">Dieser Prozess ist effizienter als die Migration des Postfachs, das Zuweisen der Datenausführungsverhinderung und das anschließende warten auf die Verschlüsselung, was Stunden oder möglicherweise Tage dauern kann.</span><span class="sxs-lookup"><span data-stu-id="1f568-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="1f568-142">Führen Sie das Cmdlet "MailUser" in Exchange Online PowerShell aus, um einem Postfach eine Datenausführungsverhinderung zuzuweisen, bevor Sie es zu Office 365 migrieren:</span><span class="sxs-lookup"><span data-stu-id="1f568-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="1f568-143">Wenn Sie ein Arbeits-oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Organisation verwenden möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="1f568-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="1f568-144">Führen Sie das Cmdlet "Sets-MailUser" aus.</span><span class="sxs-lookup"><span data-stu-id="1f568-144">Run the Set-MailUser cmdlet.</span></span>

  ```powershell
  Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
  ```

  <span data-ttu-id="1f568-145">Dabei gibt *GeneralMailboxOrMailUserIdParameter* ein Postfach an, und *DataEncryptionPolicyIdParameter* ist die ID der DEP.</span><span class="sxs-lookup"><span data-stu-id="1f568-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="1f568-146">Weitere Informationen zum Cmdlet "MailUser" finden Sie unter [festlegen-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="1f568-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="1f568-147">Ermitteln der Datenverschlüsselungsrichtlinie (DEP), die einem Postfach zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="1f568-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="1f568-148">Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um zu ermitteln, welche Datenverschlüsselungsrichtlinie (DEP) einem Postfach zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1f568-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="1f568-149">Das Cmdlet meldet einen eindeutigen Bezeichner (GUID) zurück.</span><span class="sxs-lookup"><span data-stu-id="1f568-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="1f568-150">Wenn Sie ein Arbeits-oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Organisation verwenden möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="1f568-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="1f568-151">Dabei gibt *GeneralMailboxOrMailUserIdParameter* ein Postfach an, und DataEncryptionPolicyID gibt die GUID der Datenausführungsverhinderung zurück.</span><span class="sxs-lookup"><span data-stu-id="1f568-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="1f568-152">Weitere Informationen zum Cmdlet „Get-MailboxStatistics“ finden Sie unter [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="1f568-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps).</span></span>
  
2. <span data-ttu-id="1f568-153">Führen Sie das Cmdlet Get-DataEncryptionPolicy aus, um den Anzeigenamen der DEP zu ermitteln, der das Postfach zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="1f568-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="1f568-154">Dabei ist der *GUID* derjenige GUID, der vom Cmdlet „Get-MailboxStatistics“ im vorherigen Schritt zurückgemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="1f568-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="1f568-155">Sicherstellen, dass der Kundenschlüssel die Verschlüsselung abgeschlossen hat</span><span class="sxs-lookup"><span data-stu-id="1f568-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="1f568-156">Unabhängig davon, ob Sie einen Kundenschlüssel gerollt, eine neue DEP zugewiesen oder ein Postfach migriert haben, verwenden Sie die Schritte in diesem Abschnitt, um sicherzustellen, dass die Verschlüsselung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="1f568-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="1f568-157">Überprüfen, ob die Verschlüsselung für Exchange Online und Skype for Business abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="1f568-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="1f568-158">Das Verschlüsseln eines Postfachs kann einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="1f568-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="1f568-159">Wir empfehlen, dass Sie 72 Stunden warten, bevor Sie versuchen, die Verschlüsselung nach dem Ändern einer Datenverschlüsselungsrichtlinie (DEP) oder nach dem erstmaligen Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="1f568-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="1f568-160">Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um festzustellen, ob ein Postfach verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="1f568-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="1f568-161">Die IsEncrypted-Eigenschaft meldet den Wert **True** (Richtig), wenn das Postfach verschlüsselt ist, und den Wert **False** (Falsch), wenn das Postfach nicht verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="1f568-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="1f568-162">Die Zeit bis zum Abschließen der Postfachverschiebungen hängt von der Größe des Postfachs ab.</span><span class="sxs-lookup"><span data-stu-id="1f568-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="1f568-163">Wenn der Kundenschlüssel das Postfach nach 72 Stunden nach dem Zuweisen einer neuen DEP nicht vollständig verschlüsselt hat, initiieren Sie eine Post Fach Verlagerung.</span><span class="sxs-lookup"><span data-stu-id="1f568-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, initiate a mailbox move.</span></span> <span data-ttu-id="1f568-164">Verwenden Sie dazu das Cmdlet New-MoveRequest, und geben Sie den Alias des Postfachs an.</span><span class="sxs-lookup"><span data-stu-id="1f568-164">To do this, use the New-MoveRequest cmdlet and provide the alias of the mailbox.</span></span> <span data-ttu-id="1f568-165">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1f568-165">For example:</span></span>
  
```powershell
New-MoveRequest <alias>
```

<span data-ttu-id="1f568-166">Weitere Informationen zu diesem Cmdlet finden Sie unter [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/new-moverequest?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="1f568-166">For more information about this cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/new-moverequest?view=exchange-ps).</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="1f568-167">Überprüfen, ob die Verschlüsselung für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="1f568-167">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="1f568-168">Überprüfen Sie den Verschlüsselungsstatus, indem Sie das Cmdlet Get-SPODataEncryptionPolicy wie folgt ausführen:</span><span class="sxs-lookup"><span data-stu-id="1f568-168">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="1f568-169">Die Ausgabe dieses Cmdlets umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="1f568-169">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="1f568-170">URI des Primärschlüssels.</span><span class="sxs-lookup"><span data-stu-id="1f568-170">The URI of the primary key.</span></span>

- <span data-ttu-id="1f568-171">URI des Sekundärschlüssels.</span><span class="sxs-lookup"><span data-stu-id="1f568-171">The URI of the secondary key.</span></span>

- <span data-ttu-id="1f568-172">Verschlüsselungsstatus für den Geo.</span><span class="sxs-lookup"><span data-stu-id="1f568-172">The encryption status for the geo.</span></span> <span data-ttu-id="1f568-173">Mögliche weitere Angaben:</span><span class="sxs-lookup"><span data-stu-id="1f568-173">Possible states include:</span></span>

  - <span data-ttu-id="1f568-174">**Unregistered:** (Nicht registriert) Die Customer Key-Verschlüsselung wurde noch nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="1f568-174">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="1f568-175">**Registering:** (Registrierung läuft) Die Customer Key-Verschlüsselung wurde angewendet wurde und Ihre Dateien werden gegenwärtig gerade verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="1f568-175">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="1f568-176">Wenn der Schlüssel für den Geo registriert ist, werden Ihnen auch Informationen darüber angezeigt, wie viel Prozent der Websites in der Geo abgeschlossen sind, damit Sie den Verschlüsselungs Fortschritt überwachen können.</span><span class="sxs-lookup"><span data-stu-id="1f568-176">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="1f568-177">**Registered:** (Registriert) Die Customer Key- Verschlüsselung wurde angewendet, und alle Dateien auf allen Websites wurden verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="1f568-177">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="1f568-178">**Rolling:** Das Erstellen eines sich fortlaufend ändernden, sogenannten Rolling-Codes für den Schlüssel ist in Gang.</span><span class="sxs-lookup"><span data-stu-id="1f568-178">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="1f568-179">Wenn der Schlüssel für den Geo rollt, werden Ihnen auch Informationen darüber angezeigt, wie viel Prozent der Websites den Schlüsselrollen Vorgang abgeschlossen haben, damit Sie den Fortschritt überwachen können.</span><span class="sxs-lookup"><span data-stu-id="1f568-179">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="1f568-180">Widerrufen von Schlüsseln und Starten des Prozesses zur Bereinigung des Datenpfads</span><span class="sxs-lookup"><span data-stu-id="1f568-180">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="1f568-181">Sie steuern die Sperrung aller Stammschlüssel, einschließlich des Verfügbarkeits Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="1f568-181">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="1f568-182">Kundenschlüssel bietet Ihnen die Kontrolle über den Aspekt der Beendigungs Planung der behördlichen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="1f568-182">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="1f568-183">Wenn Sie Ihre Schlüssel widerrufen, um Ihre Daten zu löschen und den Dienst zu beenden, löscht der Dienst den Verfügbarkeits Schlüssel nach Abschluss des Daten Löschvorgangs.</span><span class="sxs-lookup"><span data-stu-id="1f568-183">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="1f568-184">Microsoft 365 überwacht und validiert den Pfad zur Datenbereinigung.</span><span class="sxs-lookup"><span data-stu-id="1f568-184">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="1f568-185">Weitere Informationen finden Sie im SSAE 18 SOC 2-Bericht, der im [Dienst Vertrauensstellungs Portal](https://servicetrust.microsoft.com/)zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="1f568-185">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="1f568-186">Darüber hinaus empfiehlt Microsoft die folgenden Dokumente:</span><span class="sxs-lookup"><span data-stu-id="1f568-186">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="1f568-187">Leitfaden für Risikobewertung und Compliance für Finanzinstitute in der Microsoft-Cloud</span><span class="sxs-lookup"><span data-stu-id="1f568-187">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="1f568-188">O365-Exit-Planungsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="1f568-188">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="1f568-189">Der Pfad der Datenbereinigung unterscheidet sich geringfügig zwischen den verschiedenen Diensten.</span><span class="sxs-lookup"><span data-stu-id="1f568-189">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="1f568-190">Widerrufen Sie Ihre Kundenschlüssel und den Verfügbarkeits Schlüssel für Exchange Online und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="1f568-190">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="1f568-191">Wenn Sie den Pfad zum Löschen von Daten für Exchange Online und Skype for Business initiieren, legen Sie eine permanente Daten Löschanforderung für eine DEP fest.</span><span class="sxs-lookup"><span data-stu-id="1f568-191">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="1f568-192">Dadurch werden verschlüsselte Daten in den Postfächern, denen diese Ausführungsverhinderung zugewiesen ist, dauerhaft gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1f568-192">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="1f568-193">Da Sie das PowerShell-Cmdlet nur für jeweils eine DEP ausführen können, sollten Sie vor dem Initiieren des Daten Bereinigungs Pfads eine einzelne Ausführungsverhinderung allen ihren Postfächern erneut zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1f568-193">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="1f568-194">Verwenden Sie nicht den Daten Lösch Pfad, um eine Teilmenge ihrer Postfächer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="1f568-194">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="1f568-195">Dieser Prozess ist nur für Kunden vorgesehen, die den Dienst beenden.</span><span class="sxs-lookup"><span data-stu-id="1f568-195">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="1f568-196">Führen Sie die folgenden Schritte aus, um den Pfad der Datenbereinigung zu initiieren:</span><span class="sxs-lookup"><span data-stu-id="1f568-196">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="1f568-197">Entfernen Sie Wrap-und Unwrap-Berechtigungen für "O365 Exchange Online" aus Azure Key Vaults.</span><span class="sxs-lookup"><span data-stu-id="1f568-197">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="1f568-198">Stellen Sie eine [Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps), indem Sie ein Arbeits-oder Schulkonto mit globalen Administratorrechten in Ihrer Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="1f568-198">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="1f568-199">Führen Sie für jede DEP, die Postfächer enthält, die Sie löschen möchten, das Cmdlet " [DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) " wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="1f568-199">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="1f568-200">Wenn der Befehl fehlschlägt, stellen Sie sicher, dass Sie die Exchange Online Berechtigungen aus beiden Schlüsseln in Azure Key Vault entfernt haben, wie weiter oben in dieser Aufgabe angegeben.</span><span class="sxs-lookup"><span data-stu-id="1f568-200">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="1f568-201">Nachdem Sie den Parametern permanentdatapurgerequested-Switch mit dem Cmdlet "DataEncryptionPolicy" festgelegt haben, können Sie diese DEP nicht mehr Postfächern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1f568-201"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="1f568-202">Wenden Sie sich an den Microsoft-Support, und fordern Sie die Datenbereinigung eDocument.</span><span class="sxs-lookup"><span data-stu-id="1f568-202">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="1f568-203">Auf Ihre Anfrage hin sendet Microsoft Ihnen ein rechtliches Dokument zur Bestätigung und Autorisierung der Löschung von Daten.</span><span class="sxs-lookup"><span data-stu-id="1f568-203">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="1f568-204">Die Person in Ihrer Organisation, die sich als genehmigende Person im Angebot beim Onboarding angemeldet hat, muss dieses Dokument signieren.</span><span class="sxs-lookup"><span data-stu-id="1f568-204">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="1f568-205">Normalerweise handelt es sich dabei um eine Führungskraft oder eine andere designierte Person in Ihrem Unternehmen, die rechtlich befugt ist, die Unterlagen im Namen Ihrer Organisation zu signieren.</span><span class="sxs-lookup"><span data-stu-id="1f568-205">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="1f568-206">Wenn Ihr Vertreter das rechtliche Dokument unterzeichnet hat, senden Sie es an Microsoft (in der Regel über eine edoc-Signatur).</span><span class="sxs-lookup"><span data-stu-id="1f568-206">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="1f568-207">Sobald Microsoft das Dokument "Legal" erhält, führt Microsoft Cmdlets aus, um die Datenbereinigung auszulösen, die die Richtlinie zuerst löscht, die Postfächer für einen permanenten Löschvorgang markiert und dann den Verfügbarkeits Schlüssel löscht.</span><span class="sxs-lookup"><span data-stu-id="1f568-207">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="1f568-208">Nachdem der Daten Löschvorgang abgeschlossen wurde, wurden die Daten bereinigt, können nicht auf Exchange Online zugegriffen werden und sind nicht wiederherstellbar.</span><span class="sxs-lookup"><span data-stu-id="1f568-208">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="1f568-209">Widerrufen von Kunden Schlüsseln und dem Verfügbarkeits Schlüssel für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien</span><span class="sxs-lookup"><span data-stu-id="1f568-209">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="1f568-210">Führen Sie die folgenden Schritte aus, um den Daten Lösch Pfad für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien zu initiieren:</span><span class="sxs-lookup"><span data-stu-id="1f568-210">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="1f568-211">Sperren Sie den Azure Key Vault-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="1f568-211">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="1f568-212">Alle Key Vault-Administratoren müssen zustimmen, den Zugriff aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="1f568-212">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="1f568-213">Sie löschen nicht den Azure-schlüsseltresor für SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="1f568-213">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="1f568-214">Schlüssel Tresore können von mehreren SharePoint Online Mandanten und DEPs gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1f568-214">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="1f568-215">Wenden Sie sich an Microsoft, um den Verfügbarkeits Schlüssel zu löschen.</span><span class="sxs-lookup"><span data-stu-id="1f568-215">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="1f568-216">Wenn Sie sich an Microsoft wenden, um den Verfügbarkeits Schlüssel zu löschen, erhalten Sie ein rechtliches Dokument.</span><span class="sxs-lookup"><span data-stu-id="1f568-216">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="1f568-217">Die Person in Ihrer Organisation, die sich als genehmigende Person im Angebot beim Onboarding angemeldet hat, muss dieses Dokument signieren.</span><span class="sxs-lookup"><span data-stu-id="1f568-217">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="1f568-218">Normalerweise handelt es sich um eine Führungskraft oder eine andere designierte Person in Ihrem Unternehmen, die rechtlich befugt ist, die Unterlagen im Namen Ihrer Organisation zu signieren.</span><span class="sxs-lookup"><span data-stu-id="1f568-218">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="1f568-219">Wenn Ihr Vertreter das rechtliche Dokument signiert, senden Sie es an Microsoft (in der Regel über eine edoc-Signatur).</span><span class="sxs-lookup"><span data-stu-id="1f568-219">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="1f568-220">Sobald Microsoft das Dokument "Legal" erhält, führen wir Cmdlets aus, um die Datenbereinigung auszulösen, die das kryptografische Löschen des Mandanten Schlüssels, des Standort Schlüssels und aller einzelnen Einzeldokument Schlüssel ausführt, wodurch die Schlüsselhierarchie unwiderruflich unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="1f568-220">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="1f568-221">Nachdem die Cmdlets für die Datenbereinigung abgeschlossen wurden, wurden die Daten gelöscht.</span><span class="sxs-lookup"><span data-stu-id="1f568-221">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1f568-222">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="1f568-222">Related articles</span></span>

- [<span data-ttu-id="1f568-223">Dienst Verschlüsselung mit Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="1f568-223">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="1f568-224">Informationen zum Verfügbarkeits Schlüssel</span><span class="sxs-lookup"><span data-stu-id="1f568-224">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="1f568-225">Einrichten des Kunden Schlüssels</span><span class="sxs-lookup"><span data-stu-id="1f568-225">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="1f568-226">Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels</span><span class="sxs-lookup"><span data-stu-id="1f568-226">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="1f568-227">Customer Lockbox</span><span class="sxs-lookup"><span data-stu-id="1f568-227">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="1f568-228">Dienst Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="1f568-228">Service Encryption</span></span>](office-365-service-encryption.md)
