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
ms.openlocfilehash: 8f55667254ce7f5cbd9d4de274623ca4a3c4aa9d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909947"
---
# <a name="manage-customer-key"></a><span data-ttu-id="8d6a9-103">Verwalten des Kundenschlüssels</span><span class="sxs-lookup"><span data-stu-id="8d6a9-103">Manage Customer Key</span></span>

<span data-ttu-id="8d6a9-104">Nachdem Sie den Kundenschlüssel für Office 365 eingerichtet haben, können Sie Ihre Schlüssel wie in diesem Artikel beschrieben verwalten.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="8d6a9-105">Weitere Informationen zum Kundenschlüssel finden Sie in den zugehörigen Themen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="8d6a9-106">Wiederherstellen von Azure Key Vault-Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="8d6a9-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="8d6a9-107">Verwenden Sie vor dem Ausführen einer Wiederherstellung die von Soft Delete bereitgestellten Wiederherstellungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="8d6a9-108">Für alle mit Customer Key verwendeten Schlüssel muss Soft Delete aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="8d6a9-109">Soft Delete wirkt wie ein Recycling-Mülleimer und ermöglicht die Wiederherstellung von bis zu 90 Tagen, ohne dass eine Wiederherstellung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="8d6a9-110">Eine Wiederherstellung sollte nur unter extremen und außergewöhnlichen Umständen erforderlich sein, beispielsweise, wenn ein Schlüssel oder ein Schlüsseltresor verloren geht.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="8d6a9-111">Wenn Sie einen Schlüssel zur Verwendung mit Customer Key wiederherstellen müssen, führen Sie in Azure PowerShell das Cmdlet „Restore-AzureKeyVaultKey“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="8d6a9-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="8d6a9-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8d6a9-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="8d6a9-113">Wenn der Schlüsseltresor bereits einen Schlüssel mit demselben Namen enthält, schlägt der Wiederherstellungsvorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="8d6a9-114">Restore-AzKeyVaultKey werden alle Schlüsselversionen und alle Metadaten für den Schlüssel einschließlich des Schlüsselnamens wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="8d6a9-115">Verwalten von Schlüsseltresor-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="8d6a9-115">Manage key vault permissions</span></span>

<span data-ttu-id="8d6a9-116">Mehrere Cmdlets stehen zur Verfügung, mit denen Sie die Schlüsseltresor-Berechtigungen ansehen und, falls erforderlich, entfernen können.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="8d6a9-117">Möglicherweise müssen Sie Berechtigungen entfernen, beispielsweise, wenn ein Mitarbeiter das Team verlässt.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="8d6a9-118">Für jede dieser Aufgaben verwenden Sie Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="8d6a9-119">Weitere Informationen zu Azure Powershell finden Sie [unter Overview of Azure PowerShell](/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="8d6a9-119">For information about Azure Powershell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="8d6a9-120">Führen Sie zum Anzeigen von Schlüsseltresorberechtigungen das cmdlet Get-AzKeyVault aus.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="8d6a9-121">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8d6a9-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="8d6a9-122">Führen Sie zum Entfernen der Berechtigungen eines Administrators das cmdlet Remove-AzKeyVaultAccessPolicy aus:</span><span class="sxs-lookup"><span data-stu-id="8d6a9-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="8d6a9-123">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8d6a9-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="8d6a9-124">Verwalten von Datenverschlüsselungsrichtlinien (DATA Encryption Policies, DEPs) mit dem Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="8d6a9-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="8d6a9-125">Customer Key behandelt DEPs zwischen den verschiedenen Diensten unterschiedlich.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="8d6a9-126">Sie können z. B. eine andere Anzahl von DEPs für die verschiedenen Dienste erstellen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="8d6a9-127">**Exchange Online und Skype for Business:** Sie können bis zu 50 DEPs erstellen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="8d6a9-128">Anweisungen finden Sie unter [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="8d6a9-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="8d6a9-129">**SharePoint Online-, OneDrive for Business- und #A0** Eine DEP gilt für Daten an einem geografischen Standort, auch geo _genannt._</span><span class="sxs-lookup"><span data-stu-id="8d6a9-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="8d6a9-130">Wenn Sie das Multi-Geo-Feature von Office 365 verwenden, können Sie eine Datenverschlüsselungsrichtlinie (DEP) pro Geo erstellen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="8d6a9-131">Wenn Sie multi-geo nicht verwenden, können Sie eine DEP erstellen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="8d6a9-132">Normalerweise erstellen Sie die DEP beim Einrichten des Kundenschlüssels.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="8d6a9-133">Anweisungen finden Sie unter [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span><span class="sxs-lookup"><span data-stu-id="8d6a9-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="8d6a9-134">Anzeigen der dePs, die Sie für Exchange Online und Skype for Business erstellt haben</span><span class="sxs-lookup"><span data-stu-id="8d6a9-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="8d6a9-135">Führen Sie die folgenden Schritte aus, um eine Liste aller DEPs zu sehen, die Sie für Exchange Online und Skype for Business mithilfe des Get-DataEncryptionPolicy PowerShell-Cmdlets erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="8d6a9-136">Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [eine Verbindung mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8d6a9-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="8d6a9-137">Führen Sie zum Zurückgeben aller DEPs in Ihrer Organisation das cmdlet Get-DataEncryptionPolicy parameterfrei aus.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="8d6a9-138">Weitere Informationen zum cmdlet Get-DataEncryptionPolicy finden Sie unter [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="8d6a9-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="8d6a9-139">Zuweisen einer DEP vor der Migration eines Postfachs in die Cloud</span><span class="sxs-lookup"><span data-stu-id="8d6a9-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="8d6a9-140">Wenn Sie die DEP zuweisen, verschlüsselt Microsoft 365 den Inhalt des Postfachs mithilfe der zugewiesenen DEP während der Migration.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="8d6a9-141">Dieser Vorgang ist effizienter als das Migrieren des Postfachs, das Zuweisen der DEP und dann das Warten auf die Verschlüsselung, was Stunden oder möglicherweise Tage dauern kann.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="8d6a9-142">Führen Sie zum Zuweisen einer DEP zu einem Postfach vor der Migration zu Office 365 das cmdlet Set-MailUser in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="8d6a9-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="8d6a9-143">Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [eine Verbindung mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8d6a9-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="8d6a9-144">Führen Sie Set-MailUser cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-144">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="8d6a9-145">Dabei *gibt GeneralMailboxOrMailUserIdParameter* ein Postfach an, und *DataEncryptionPolicyIdParameter* ist die ID der DEP.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="8d6a9-146">Weitere Informationen zum cmdlet Set-MailUser finden Sie unter [Set-MailUser](/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="8d6a9-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="8d6a9-147">Ermitteln der Datenverschlüsselungsrichtlinie (DEP), die einem Postfach zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="8d6a9-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="8d6a9-148">Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um zu ermitteln, welche Datenverschlüsselungsrichtlinie (DEP) einem Postfach zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="8d6a9-149">Das Cmdlet meldet einen eindeutigen Bezeichner (GUID) zurück.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="8d6a9-150">Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [eine Verbindung mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8d6a9-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="8d6a9-151">Wobei *GeneralMailboxOrMailUserIdParameter* ein Postfach angibt und DataEncryptionPolicyID die GUID der DEP zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="8d6a9-152">Weitere Informationen zum Cmdlet „Get-MailboxStatistics“ finden Sie unter [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span><span class="sxs-lookup"><span data-stu-id="8d6a9-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="8d6a9-153">Führen Sie Get-DataEncryptionPolicy cmdlet aus, um den Anzeigenamen der DEP zu finden, der das Postfach zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="8d6a9-154">Dabei ist der *GUID* derjenige GUID, der vom Cmdlet „Get-MailboxStatistics“ im vorherigen Schritt zurückgemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="8d6a9-155">Überprüfen, ob der Kundenschlüssel die Verschlüsselung beendet hat</span><span class="sxs-lookup"><span data-stu-id="8d6a9-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="8d6a9-156">Ob Sie gerade einen Kundenschlüssel gerollt, eine neue DEP zugewiesen oder ein Postfach migriert haben, führen Sie die Schritte in diesem Abschnitt aus, um sicherzustellen, dass die Verschlüsselung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="8d6a9-157">Überprüfen, ob die Verschlüsselung für Exchange Online und Skype for Business abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="8d6a9-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="8d6a9-158">Das Verschlüsseln eines Postfachs kann einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="8d6a9-159">Wir empfehlen, dass Sie 72 Stunden warten, bevor Sie versuchen, die Verschlüsselung nach dem Ändern einer Datenverschlüsselungsrichtlinie (DEP) oder nach dem erstmaligen Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="8d6a9-160">Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um festzustellen, ob ein Postfach verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="8d6a9-161">Die IsEncrypted-Eigenschaft meldet den Wert **True** (Richtig), wenn das Postfach verschlüsselt ist, und den Wert **False** (Falsch), wenn das Postfach nicht verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="8d6a9-162">Die Zeit zum Abschließen von Postfachbewegungen hängt von der Größe des Postfachs ab.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="8d6a9-163">Wenn der Kundenschlüssel das Postfach nach 72 Stunden nach dem Zuweisen einer neuen DEP nicht vollständig verschlüsselt hat, wenden Sie sich an den Microsoft-Support, um Hilfe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="8d6a9-164">Das New-MoveRequest cmdlet ist nicht mehr für lokale Postfachbewegungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="8d6a9-165">Weitere Informationen [finden Sie in](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) dieser Ankündigung.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="8d6a9-166">Überprüfen, ob die Verschlüsselung für SharePoint Online-, OneDrive for Business- und #A0 abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="8d6a9-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="8d6a9-167">Überprüfen Sie den Status der Verschlüsselung, indem Sie Get-SPODataEncryptionPolicy cmdlet wie folgt ausführen:</span><span class="sxs-lookup"><span data-stu-id="8d6a9-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="8d6a9-168">Die Ausgabe dieses Cmdlets umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="8d6a9-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="8d6a9-169">URI des Primärschlüssels.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-169">The URI of the primary key.</span></span>

- <span data-ttu-id="8d6a9-170">URI des Sekundärschlüssels.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="8d6a9-171">Verschlüsselungsstatus für den Geo.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-171">The encryption status for the geo.</span></span> <span data-ttu-id="8d6a9-172">Mögliche weitere Angaben:</span><span class="sxs-lookup"><span data-stu-id="8d6a9-172">Possible states include:</span></span>

  - <span data-ttu-id="8d6a9-173">**Unregistered:** (Nicht registriert) Die Customer Key-Verschlüsselung wurde noch nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="8d6a9-174">**Registering:** (Registrierung läuft) Die Customer Key-Verschlüsselung wurde angewendet wurde und Ihre Dateien werden gegenwärtig gerade verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="8d6a9-175">Wenn der Schlüssel für den Geografischen registriert wird, werden Ihnen auch Informationen angezeigt, welcher Prozentsatz der Websites im Geografischen abgeschlossen ist, damit Sie den Verschlüsselungsfortschritt überwachen können.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="8d6a9-176">**Registered:** (Registriert) Die Customer Key- Verschlüsselung wurde angewendet, und alle Dateien auf allen Websites wurden verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="8d6a9-177">**Rolling:** Das Erstellen eines sich fortlaufend ändernden, sogenannten Rolling-Codes für den Schlüssel ist in Gang.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="8d6a9-178">Wenn der Schlüssel für den geografischen Standort rollt, erhalten Sie außerdem Informationen dazu, welcher Prozentsatz der Websites den Schlüsselrollvorgang abgeschlossen hat, damit Sie den Fortschritt überwachen können.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="unassign-a-dep-from-a-mailbox"></a><span data-ttu-id="8d6a9-179">Unassign a DEP from a mailbox</span><span class="sxs-lookup"><span data-stu-id="8d6a9-179">Unassign a DEP from a mailbox</span></span>

<span data-ttu-id="8d6a9-180">Mit dem Set-mailbox PowerShell-Cmdlet können Sie eine DEP aus einem Postfach zuweisen und den auf `DataEncryptionPolicy` `$NULL` festlegen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-180">You unassign a DEP from a mailbox using the Set-mailbox PowerShell cmdlet and setting the `DataEncryptionPolicy` to `$NULL`.</span></span> <span data-ttu-id="8d6a9-181">Wenn Sie dieses Cmdlet ausführen, wird die derzeit zugewiesene DEP entfernt und das Postfach mithilfe der DEP erneut verschlüsselt, die den verwalteten Standardschlüsseln von Microsoft zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-181">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft managed keys.</span></span> <span data-ttu-id="8d6a9-182">Die von verwalteten Schlüsseln von Microsoft verwendete DEP kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-182">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="8d6a9-183">Wenn Sie keine verwalteten Schlüssel von Microsoft verwenden möchten, können Sie dem Postfach eine weitere DEP zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-183">If you don't want to use Microsoft managed keys, you can assign another DEP to the mailbox.</span></span>

<span data-ttu-id="8d6a9-184">Führen Sie die folgenden Schritte aus, um die DEP mithilfe des Set-Mailbox PowerShell-Cmdlets aus einem Postfach zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-184">To unassign the DEP from a mailbox using the Set-Mailbox PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="8d6a9-185">Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, [eine Verbindung mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8d6a9-185">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="8d6a9-186">Führen Sie Set-Mailbox cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-186">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="8d6a9-187">Widerrufen Der Schlüssel und Starten des Datenbereinigungspfadprozesses</span><span class="sxs-lookup"><span data-stu-id="8d6a9-187">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="8d6a9-188">Sie steuern den Widerruf aller Stammschlüssel, einschließlich des Verfügbarkeitsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-188">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="8d6a9-189">Customer Key bietet die Kontrolle über den Aspekt der Beendigungsplanung der gesetzlichen Anforderungen für Sie.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-189">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="8d6a9-190">Wenn Sie ihre Schlüssel widerrufen möchten, um Ihre Daten zu löschen und den Dienst zu beenden, löscht der Dienst den Verfügbarkeitsschlüssel, sobald der Datenlöschvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-190">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="8d6a9-191">Microsoft 365 überwacht und überprüft den Datenbereinigungspfad.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-191">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="8d6a9-192">Weitere Informationen finden Sie im SSAE 18 SOC 2-Bericht, der im [Service Trust Portal verfügbar ist.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="8d6a9-192">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="8d6a9-193">Darüber hinaus empfiehlt Microsoft die folgenden Dokumente:</span><span class="sxs-lookup"><span data-stu-id="8d6a9-193">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="8d6a9-194">Leitfaden zur Risikobewertung und Compliance für Finanzinstitute in der Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="8d6a9-194">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="8d6a9-195">Überlegungen zur O365-Beendigungsplanung</span><span class="sxs-lookup"><span data-stu-id="8d6a9-195">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="8d6a9-196">Der Datenbereinigungspfad unterscheidet sich geringfügig zwischen den verschiedenen Diensten.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-196">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="8d6a9-197">Widerrufen Ihrer Kundenschlüssel und des Verfügbarkeitsschlüssels für Exchange Online und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="8d6a9-197">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="8d6a9-198">Wenn Sie den Pfad zur Datenbereinigung für Exchange Online und Skype for Business initiieren, legen Sie eine permanente Datenbereinigungsanforderung für eine DEP fest.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-198">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="8d6a9-199">Dadurch werden verschlüsselte Daten in den Postfächern, denen diese DEP zugewiesen ist, dauerhaft gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-199">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="8d6a9-200">Da Sie das PowerShell-Cmdlet nur für eine DEP gleichzeitig ausführen können, sollten Sie eine einzelne DEP allen Postfächern erneut zuweisen, bevor Sie den Datenbereinigungspfad initiieren.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-200">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="8d6a9-201">Verwenden Sie nicht den Pfad zum Löschen von Daten, um eine Teilmenge Ihrer Postfächer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-201">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="8d6a9-202">Dieser Vorgang ist nur für Kunden gedacht, die den Dienst verlassen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-202">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="8d6a9-203">Führen Sie die folgenden Schritte aus, um den Datenbereinigungspfad zu initiieren:</span><span class="sxs-lookup"><span data-stu-id="8d6a9-203">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="8d6a9-204">Entfernen von Umbruch- und Auspackberechtigungen für "O365 Exchange Online" aus Azure Key Vaults.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-204">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="8d6a9-205">Stellen Sie mithilfe eines Arbeits- oder Schulkontos mit globalen Administratorrechten in Ihrer Organisation eine Verbindung [mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="8d6a9-205">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="8d6a9-206">Führen Sie für jede DEP, die zu löschende Postfächer enthält, das [Cmdlet Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-206">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="8d6a9-207">Wenn der Befehl fehlschlägt, stellen Sie sicher, dass Sie die Exchange Online-Berechtigungen aus beiden Schlüsseln in Azure Key Vault entfernt haben, wie weiter oben in dieser Aufgabe angegeben.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-207">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="8d6a9-208">Nachdem Sie den Switch PermanentDataPurgeRequested mit dem cmdlet Set-DataEncryptionPolicy festgelegt haben, können Sie diese DEP nicht mehr Postfächern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-208"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="8d6a9-209">Wenden Sie sich an den Microsoft-Support, und fordern Sie das Data Purge eDocument an.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-209">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="8d6a9-210">Auf Ihre Anfrage sendet Microsoft Ihnen ein rechtliches Dokument, um die Löschung von Daten zu bestätigen und zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-210">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="8d6a9-211">Die Person in Ihrer Organisation, die sich während des Onboardings als genehmigende Person im FastTrack-Angebot angemeldet hat, muss dieses Dokument signieren.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-211">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="8d6a9-212">Normalerweise handelt es sich dabei um eine Führungskraft oder eine andere benannte Person in Ihrem Unternehmen, die berechtigt ist, den Papierkram im Namen Ihrer Organisation zu signieren.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-212">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="8d6a9-213">Nachdem Ihr Vertreter das rechtliche Dokument signiert hat, geben Sie es an Microsoft zurück (in der Regel über eine eDoc-Signatur).</span><span class="sxs-lookup"><span data-stu-id="8d6a9-213">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="8d6a9-214">Sobald Microsoft das rechtliche Dokument erhält, führt Microsoft Cmdlets aus, um die Datenbereinigung auszulösen, die zuerst die Richtlinie löscht, die Postfächer für das dauerhafte Löschen markiert und dann den Verfügbarkeitsschlüssel löscht.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-214">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="8d6a9-215">Sobald der Datenbereinigungsprozess abgeschlossen ist, wurden die Daten gelöscht, auf Exchange Online kann nicht zugegriffen werden und kann nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-215">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="8d6a9-216">Widerrufen Ihrer Kundenschlüssel und des Verfügbarkeitsschlüssels für SharePoint Online-, OneDrive for Business- und #A0</span><span class="sxs-lookup"><span data-stu-id="8d6a9-216">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="8d6a9-217">Führen Sie die folgenden Schritte aus, um den Datenbereinigungspfad für SharePoint Online-, OneDrive for Business- und #A0 zu initiieren:</span><span class="sxs-lookup"><span data-stu-id="8d6a9-217">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="8d6a9-218">Widerrufen des Azure Key Vault-Zugriffs.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-218">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="8d6a9-219">Alle Schlüsseltresoradministratoren müssen zustimmen, den Zugriff zu widerrufen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-219">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="8d6a9-220">Sie löschen den Azure Key Vault für SharePoint Online nicht.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-220">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="8d6a9-221">Schlüsseltresor können für mehrere SharePoint Online-Mandanten und DEPs freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-221">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="8d6a9-222">Wenden Sie sich an Microsoft, um den Verfügbarkeitsschlüssel zu löschen.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-222">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="8d6a9-223">Wenn Sie microsoft kontaktieren, um den Verfügbarkeitsschlüssel zu löschen, senden wir Ihnen ein rechtliches Dokument.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-223">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="8d6a9-224">Die Person in Ihrer Organisation, die sich während des Onboardings als genehmigende Person im FastTrack-Angebot angemeldet hat, muss dieses Dokument signieren.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-224">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="8d6a9-225">Normalerweise handelt es sich dabei um eine Führungskraft oder eine andere benannte Person in Ihrem Unternehmen, die gesetzlich autorisiert ist, den Papierkram im Namen Ihrer Organisation zu signieren.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-225">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="8d6a9-226">Sobald Ihr Vertreter das rechtliche Dokument signiert hat, geben Sie es an Microsoft zurück (in der Regel über eine eDoc-Signatur).</span><span class="sxs-lookup"><span data-stu-id="8d6a9-226">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="8d6a9-227">Sobald Microsoft das rechtliche Dokument erhält, führen wir Cmdlets aus, um die Datenbereinigung auszulösen, die die Kryptografielöschung des Mandantenschlüssels, des Websiteschlüssels und aller einzelnen Schlüssel pro Dokument durchführt, wodurch die Schlüsselhierarchie unwiderruflich gebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-227">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="8d6a9-228">Nachdem die Datenbereinigungs-Cmdlets abgeschlossen sind, wurden Ihre Daten gelöscht.</span><span class="sxs-lookup"><span data-stu-id="8d6a9-228">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="8d6a9-229">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="8d6a9-229">Related articles</span></span>

- [<span data-ttu-id="8d6a9-230">Dienstverschlüsselung mit Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="8d6a9-230">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="8d6a9-231">Informationen zum Verfügbarkeitsschlüssel</span><span class="sxs-lookup"><span data-stu-id="8d6a9-231">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="8d6a9-232">Einrichten des Kundenschlüssels</span><span class="sxs-lookup"><span data-stu-id="8d6a9-232">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="8d6a9-233">Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels</span><span class="sxs-lookup"><span data-stu-id="8d6a9-233">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="8d6a9-234">Customer Lockbox</span><span class="sxs-lookup"><span data-stu-id="8d6a9-234">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="8d6a9-235">Dienstverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="8d6a9-235">Service Encryption</span></span>](office-365-service-encryption.md)