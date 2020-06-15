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
ms.openlocfilehash: 21c1fedce1ebc09e6c33b74a1b2c035c90988e12
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717306"
---
# <a name="manage-customer-key"></a><span data-ttu-id="58ad0-103">Verwalten des Kunden Schlüssels</span><span class="sxs-lookup"><span data-stu-id="58ad0-103">Manage Customer Key</span></span>

<span data-ttu-id="58ad0-104">Nachdem Sie den Kundenschlüssel für Office 365 eingerichtet haben, können Sie die Schlüssel wie in diesem Artikel beschrieben verwalten.</span><span class="sxs-lookup"><span data-stu-id="58ad0-104">After you've set up Customer Key for Office 365, you can manage your keys as described in this article.</span></span> <span data-ttu-id="58ad0-105">Erfahren Sie mehr über den Kundenschlüssel in den verwandten Themen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-105">Learn more about Customer Key in the related topics.</span></span>

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="58ad0-106">Wiederherstellen von Azure Key Vault-Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="58ad0-106">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="58ad0-107">Verwenden Sie vor dem Ausführen einer Wiederherstellung die von Soft Delete bereitgestellten Wiederherstellungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-107">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="58ad0-108">Für alle mit Customer Key verwendeten Schlüssel muss Soft Delete aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="58ad0-108">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="58ad0-109">Soft Delete wirkt wie ein Recycling-Mülleimer und ermöglicht die Wiederherstellung von bis zu 90 Tagen, ohne dass eine Wiederherstellung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="58ad0-109">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="58ad0-110">Eine Wiederherstellung sollte nur unter extremen und außergewöhnlichen Umständen erforderlich sein, beispielsweise, wenn ein Schlüssel oder ein Schlüsseltresor verloren geht.</span><span class="sxs-lookup"><span data-stu-id="58ad0-110">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="58ad0-111">Wenn Sie einen Schlüssel zur Verwendung mit Customer Key wiederherstellen müssen, führen Sie in Azure PowerShell das Cmdlet „Restore-AzureKeyVaultKey“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="58ad0-111">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="58ad0-112">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="58ad0-112">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="58ad0-113">Wenn der schlüsseltresor bereits einen Schlüssel mit dem gleichen Namen enthält, schlägt der Wiederherstellungsvorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="58ad0-113">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="58ad0-114">Restore-AzKeyVaultKey stellt alle Schlüssel Versionen und alle Metadaten für den Schlüssel einschließlich des Schlüssel namens wieder her.</span><span class="sxs-lookup"><span data-stu-id="58ad0-114">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="58ad0-115">Verwalten von Schlüsseltresor-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="58ad0-115">Manage key vault permissions</span></span>

<span data-ttu-id="58ad0-116">Mehrere Cmdlets stehen zur Verfügung, mit denen Sie die Schlüsseltresor-Berechtigungen ansehen und, falls erforderlich, entfernen können.</span><span class="sxs-lookup"><span data-stu-id="58ad0-116">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="58ad0-117">Möglicherweise müssen Sie Berechtigungen entfernen, beispielsweise, wenn ein Mitarbeiter das Team verlässt.</span><span class="sxs-lookup"><span data-stu-id="58ad0-117">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="58ad0-118">Für jede dieser Aufgaben wird Azure PowerShell verwendet.</span><span class="sxs-lookup"><span data-stu-id="58ad0-118">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="58ad0-119">Informationen zu Azure PowerShell finden Sie unter [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="58ad0-119">For information about Azure Powershell, see [Overview of Azure PowerShell](https://docs.microsoft.com/powershell/azure/).</span></span>

<span data-ttu-id="58ad0-120">Führen Sie das Cmdlet Get-AzKeyVault aus, um die schlüsseltresor-Berechtigungen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-120">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="58ad0-121">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="58ad0-121">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="58ad0-122">Um die Berechtigungen eines Administrators zu entfernen, führen Sie das Cmdlet Remove-AzKeyVaultAccessPolicy aus:</span><span class="sxs-lookup"><span data-stu-id="58ad0-122">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="58ad0-123">Zum Beispiel:</span><span class="sxs-lookup"><span data-stu-id="58ad0-123">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="manage-data-encryption-policies-deps-with-customer-key"></a><span data-ttu-id="58ad0-124">Verwalten von Daten Verschlüsselungsrichtlinien (DEPs) mit dem Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="58ad0-124">Manage data encryption policies (DEPs) with Customer Key</span></span>

<span data-ttu-id="58ad0-125">Kundenschlüssel behandelt DEPs unterschiedlich zwischen den verschiedenen Diensten.</span><span class="sxs-lookup"><span data-stu-id="58ad0-125">Customer Key handles DEPs differently between the different services.</span></span> <span data-ttu-id="58ad0-126">Sie können beispielsweise eine andere Anzahl von DEPs für die verschiedenen Dienste erstellen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-126">For example, you can create a different number of DEPs for the different services.</span></span>

<span data-ttu-id="58ad0-127">**Exchange Online und Skype for Business:** Sie können bis zu 50 DEPs erstellen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-127">**Exchange Online and Skype for Business:** You can create up to 50 DEPs.</span></span> <span data-ttu-id="58ad0-128">Anweisungen finden Sie unter [Erstellen einer Daten Verschlüsselungsrichtlinie (DEP) für die Verwendung mit Exchange Online und Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span><span class="sxs-lookup"><span data-stu-id="58ad0-128">For instructions, see [Create a data encryption policy (DEP) for use with Exchange Online and Skype for Business](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-use-with-exchange-online-and-skype-for-business).</span></span>

<span data-ttu-id="58ad0-129">**SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien:** Eine DEP gilt für Daten an einem geografischen Standort, der auch als _Geo_bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="58ad0-129">**SharePoint Online, OneDrive for Business, and Teams files:** A DEP applies to data in one geographic location, also called a _geo_.</span></span> <span data-ttu-id="58ad0-130">Wenn Sie das Multi-Geo-Feature von Office 365 verwenden, können Sie eine Datenverschlüsselungsrichtlinie (DEP) pro Geo erstellen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-130">If you use the multi-geo feature of Office 365, you can create one DEP per geo.</span></span> <span data-ttu-id="58ad0-131">Wenn Sie keine Multi-Geo-Daten verwenden, können Sie eine DEP erstellen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-131">If you are not using multi-geo, you can create one DEP.</span></span> <span data-ttu-id="58ad0-132">Normalerweise erstellen Sie die Datenausführungsverhinderung, wenn Sie den Kundenschlüssel einrichten.</span><span class="sxs-lookup"><span data-stu-id="58ad0-132">Normally, you create the DEP when you set up Customer Key.</span></span> <span data-ttu-id="58ad0-133">Anweisungen finden Sie unter [Erstellen einer Daten Verschlüsselungsrichtlinie (DEP) für jede SharePoint Online und OneDrive für Unternehmen Geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span><span class="sxs-lookup"><span data-stu-id="58ad0-133">For instructions, see [Create a data encryption policy (DEP) for each SharePoint Online and OneDrive for Business geo](customer-key-set-up.md#create-a-data-encryption-policy-dep-for-each-sharepoint-online-and-onedrive-for-business-geo).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="58ad0-134">Anzeigen der DEPs, die Sie für Exchange Online und Skype for Business erstellt haben</span><span class="sxs-lookup"><span data-stu-id="58ad0-134">View the DEPs you've created for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="58ad0-135">Führen Sie die folgenden Schritte aus, um eine Liste aller DEPs anzuzeigen, die Sie für Exchange Online und Skype for Business mithilfe des PowerShell-Cmdlets "Get-DataEncryptionPolicy" erstellt haben.</span><span class="sxs-lookup"><span data-stu-id="58ad0-135">To view a list of all the DEPs you've created for Exchange Online and Skype for Business using the Get-DataEncryptionPolicy PowerShell cmdlet, complete these steps.</span></span>

1. <span data-ttu-id="58ad0-136">Wenn Sie ein Arbeits-oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Organisation verwenden möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="58ad0-136">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="58ad0-137">Wenn Sie alle DEPs in Ihrer Organisation zurückgeben möchten, führen Sie das Cmdlet Get-DataEncryptionPolicy ohne Parameter aus.</span><span class="sxs-lookup"><span data-stu-id="58ad0-137">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

  ```powershell
  Get-DataEncryptionPolicy
  ```

  <span data-ttu-id="58ad0-138">Weitere Informationen zum Get-DataEncryptionPolicy-Cmdlet finden Sie unter [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="58ad0-138">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/get-dataencryptionpolicy?view=exchange-ps).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="58ad0-139">Zuweisen einer Datenausführungsverhinderung vor der Migration eines Postfachs in die Cloud</span><span class="sxs-lookup"><span data-stu-id="58ad0-139">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="58ad0-140">Wenn Sie die Datenausführungsverhinderung zuweisen, verschlüsselt Microsoft 365 die Inhalte des Postfachs mithilfe der zugewiesenen DEP während der Migration.</span><span class="sxs-lookup"><span data-stu-id="58ad0-140">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="58ad0-141">Dieser Prozess ist effizienter als die Migration des Postfachs, das Zuweisen der Datenausführungsverhinderung und das anschließende warten auf die Verschlüsselung, was Stunden oder möglicherweise Tage dauern kann.</span><span class="sxs-lookup"><span data-stu-id="58ad0-141">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="58ad0-142">Führen Sie das Cmdlet "MailUser" in Exchange Online PowerShell aus, um einem Postfach eine Datenausführungsverhinderung zuzuweisen, bevor Sie es zu Office 365 migrieren:</span><span class="sxs-lookup"><span data-stu-id="58ad0-142">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="58ad0-143">Wenn Sie ein Arbeits-oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Organisation verwenden möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="58ad0-143">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

2. <span data-ttu-id="58ad0-144">Führen Sie das Cmdlet "Sets-MailUser" aus.</span><span class="sxs-lookup"><span data-stu-id="58ad0-144">Run the Set-MailUser cmdlet.</span></span>

  ```powershell
  Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
  ```

  <span data-ttu-id="58ad0-145">Dabei gibt *GeneralMailboxOrMailUserIdParameter* ein Postfach an, und *DataEncryptionPolicyIdParameter* ist die ID der DEP.</span><span class="sxs-lookup"><span data-stu-id="58ad0-145">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="58ad0-146">Weitere Informationen zum Cmdlet "MailUser" finden Sie unter [festlegen-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="58ad0-146">For more information about the Set-MailUser cmdlet, see [Set-MailUser](https://docs.microsoft.com/powershell/module/exchange/set-mailuser?view=exchange-ps).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="58ad0-147">Ermitteln der Datenverschlüsselungsrichtlinie (DEP), die einem Postfach zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="58ad0-147">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="58ad0-148">Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um zu ermitteln, welche Datenverschlüsselungsrichtlinie (DEP) einem Postfach zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="58ad0-148">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="58ad0-149">Das Cmdlet meldet einen eindeutigen Bezeichner (GUID) zurück.</span><span class="sxs-lookup"><span data-stu-id="58ad0-149">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="58ad0-150">Wenn Sie ein Arbeits-oder Schulkonto mit globalen Administratorberechtigungen in Ihrer Organisation verwenden möchten, stellen Sie [eine Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="58ad0-150">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="58ad0-151">Dabei gibt *GeneralMailboxOrMailUserIdParameter* ein Postfach an, und DataEncryptionPolicyID gibt die GUID der Datenausführungsverhinderung zurück.</span><span class="sxs-lookup"><span data-stu-id="58ad0-151">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="58ad0-152">Weitere Informationen zum Cmdlet „Get-MailboxStatistics“ finden Sie unter [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps).</span><span class="sxs-lookup"><span data-stu-id="58ad0-152">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](https://docs.microsoft.com/powershell/module/exchange/get-mailboxstatistics?view=exchange-ps).</span></span>
  
2. <span data-ttu-id="58ad0-153">Führen Sie das Cmdlet Get-DataEncryptionPolicy aus, um den Anzeigenamen der DEP zu ermitteln, der das Postfach zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="58ad0-153">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="58ad0-154">Dabei ist der *GUID* derjenige GUID, der vom Cmdlet „Get-MailboxStatistics“ im vorherigen Schritt zurückgemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="58ad0-154">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="58ad0-155">Sicherstellen, dass der Kundenschlüssel die Verschlüsselung abgeschlossen hat</span><span class="sxs-lookup"><span data-stu-id="58ad0-155">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="58ad0-156">Unabhängig davon, ob Sie einen Kundenschlüssel gerollt, eine neue DEP zugewiesen oder ein Postfach migriert haben, verwenden Sie die Schritte in diesem Abschnitt, um sicherzustellen, dass die Verschlüsselung abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="58ad0-156">Whether you've just rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="58ad0-157">Überprüfen, ob die Verschlüsselung für Exchange Online und Skype for Business abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="58ad0-157">Verify encryption completes for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="58ad0-158">Das Verschlüsseln eines Postfachs kann einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-158">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="58ad0-159">Wir empfehlen, dass Sie 72 Stunden warten, bevor Sie versuchen, die Verschlüsselung nach dem Ändern einer Datenverschlüsselungsrichtlinie (DEP) oder nach dem erstmaligen Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach zu überprüfen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-159">We recommend that you wait 72 hours before you attempt to validate encryption after you change a DEP or the first time you assign a DEP to a mailbox.</span></span>
  
<span data-ttu-id="58ad0-160">Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um festzustellen, ob ein Postfach verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="58ad0-160">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="58ad0-161">Die IsEncrypted-Eigenschaft meldet den Wert **True** (Richtig), wenn das Postfach verschlüsselt ist, und den Wert **False** (Falsch), wenn das Postfach nicht verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="58ad0-161">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox is not encrypted.</span></span>

<span data-ttu-id="58ad0-162">Die Zeit bis zum Abschließen der Postfachverschiebungen hängt von der Größe des Postfachs ab.</span><span class="sxs-lookup"><span data-stu-id="58ad0-162">The time to complete mailbox moves depends on the size of the mailbox.</span></span> <span data-ttu-id="58ad0-163">Wenn der Kundenschlüssel das Postfach nach 72 Stunden nach dem Zuweisen einer neuen DEP nicht vollständig verschlüsselt hat, wenden Sie sich an den Microsoft-Support, um Hilfe zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="58ad0-163">If Customer Key hasn't completely encrypted the mailbox after 72 hours from the time you assign a new DEP, contact Microsoft support for help.</span></span> <span data-ttu-id="58ad0-164">Das Cmdlet New-MoveRequest ist für Verschiebungen von lokalen Postfächern nicht mehr verfügbar.</span><span class="sxs-lookup"><span data-stu-id="58ad0-164">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="58ad0-165">Weitere Informationen erhalten Sie in [dieser Ankündigung](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) .</span><span class="sxs-lookup"><span data-stu-id="58ad0-165">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="58ad0-166">Überprüfen, ob die Verschlüsselung für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="58ad0-166">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="58ad0-167">Überprüfen Sie den Verschlüsselungsstatus, indem Sie das Cmdlet Get-SPODataEncryptionPolicy wie folgt ausführen:</span><span class="sxs-lookup"><span data-stu-id="58ad0-167">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```powershell
Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="58ad0-168">Die Ausgabe dieses Cmdlets umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="58ad0-168">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="58ad0-169">URI des Primärschlüssels.</span><span class="sxs-lookup"><span data-stu-id="58ad0-169">The URI of the primary key.</span></span>

- <span data-ttu-id="58ad0-170">URI des Sekundärschlüssels.</span><span class="sxs-lookup"><span data-stu-id="58ad0-170">The URI of the secondary key.</span></span>

- <span data-ttu-id="58ad0-171">Verschlüsselungsstatus für den Geo.</span><span class="sxs-lookup"><span data-stu-id="58ad0-171">The encryption status for the geo.</span></span> <span data-ttu-id="58ad0-172">Mögliche weitere Angaben:</span><span class="sxs-lookup"><span data-stu-id="58ad0-172">Possible states include:</span></span>

  - <span data-ttu-id="58ad0-173">**Unregistered:** (Nicht registriert) Die Customer Key-Verschlüsselung wurde noch nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="58ad0-173">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="58ad0-174">**Registering:** (Registrierung läuft) Die Customer Key-Verschlüsselung wurde angewendet wurde und Ihre Dateien werden gegenwärtig gerade verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="58ad0-174">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="58ad0-175">Wenn der Schlüssel für den Geo registriert ist, werden Ihnen auch Informationen darüber angezeigt, wie viel Prozent der Websites in der Geo abgeschlossen sind, damit Sie den Verschlüsselungs Fortschritt überwachen können.</span><span class="sxs-lookup"><span data-stu-id="58ad0-175">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="58ad0-176">**Registered:** (Registriert) Die Customer Key- Verschlüsselung wurde angewendet, und alle Dateien auf allen Websites wurden verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="58ad0-176">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="58ad0-177">**Rolling:** Das Erstellen eines sich fortlaufend ändernden, sogenannten Rolling-Codes für den Schlüssel ist in Gang.</span><span class="sxs-lookup"><span data-stu-id="58ad0-177">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="58ad0-178">Wenn der Schlüssel für den Geo rollt, werden Ihnen auch Informationen darüber angezeigt, wie viel Prozent der Websites den Schlüsselrollen Vorgang abgeschlossen haben, damit Sie den Fortschritt überwachen können.</span><span class="sxs-lookup"><span data-stu-id="58ad0-178">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="58ad0-179">Widerrufen von Schlüsseln und Starten des Prozesses zur Bereinigung des Datenpfads</span><span class="sxs-lookup"><span data-stu-id="58ad0-179">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="58ad0-180">Sie steuern die Sperrung aller Stammschlüssel, einschließlich des Verfügbarkeits Schlüssels.</span><span class="sxs-lookup"><span data-stu-id="58ad0-180">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="58ad0-181">Kundenschlüssel bietet Ihnen die Kontrolle über den Aspekt der Beendigungs Planung der behördlichen Anforderungen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-181">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="58ad0-182">Wenn Sie Ihre Schlüssel widerrufen, um Ihre Daten zu löschen und den Dienst zu beenden, löscht der Dienst den Verfügbarkeits Schlüssel nach Abschluss des Daten Löschvorgangs.</span><span class="sxs-lookup"><span data-stu-id="58ad0-182">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span>

<span data-ttu-id="58ad0-183">Microsoft 365 überwacht und validiert den Pfad zur Datenbereinigung.</span><span class="sxs-lookup"><span data-stu-id="58ad0-183">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="58ad0-184">Weitere Informationen finden Sie im SSAE 18 SOC 2-Bericht, der im [Dienst Vertrauensstellungs Portal](https://servicetrust.microsoft.com/)zur Verfügung steht.</span><span class="sxs-lookup"><span data-stu-id="58ad0-184">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="58ad0-185">Darüber hinaus empfiehlt Microsoft die folgenden Dokumente:</span><span class="sxs-lookup"><span data-stu-id="58ad0-185">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="58ad0-186">Leitfaden für Risikobewertung und Compliance für Finanzinstitute in der Microsoft-Cloud</span><span class="sxs-lookup"><span data-stu-id="58ad0-186">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="58ad0-187">O365-Exit-Planungsüberlegungen</span><span class="sxs-lookup"><span data-stu-id="58ad0-187">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="58ad0-188">Der Pfad der Datenbereinigung unterscheidet sich geringfügig zwischen den verschiedenen Diensten.</span><span class="sxs-lookup"><span data-stu-id="58ad0-188">The data purge path differs slightly between the different services.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="58ad0-189">Widerrufen Sie Ihre Kundenschlüssel und den Verfügbarkeits Schlüssel für Exchange Online und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="58ad0-189">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="58ad0-190">Wenn Sie den Pfad zum Löschen von Daten für Exchange Online und Skype for Business initiieren, legen Sie eine permanente Daten Löschanforderung für eine DEP fest.</span><span class="sxs-lookup"><span data-stu-id="58ad0-190">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="58ad0-191">Dadurch werden verschlüsselte Daten in den Postfächern, denen diese Ausführungsverhinderung zugewiesen ist, dauerhaft gelöscht.</span><span class="sxs-lookup"><span data-stu-id="58ad0-191">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="58ad0-192">Da Sie das PowerShell-Cmdlet nur für jeweils eine DEP ausführen können, sollten Sie vor dem Initiieren des Daten Bereinigungs Pfads eine einzelne Ausführungsverhinderung allen ihren Postfächern erneut zuweisen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-192">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="58ad0-193">Verwenden Sie nicht den Daten Lösch Pfad, um eine Teilmenge ihrer Postfächer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-193">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="58ad0-194">Dieser Prozess ist nur für Kunden vorgesehen, die den Dienst beenden.</span><span class="sxs-lookup"><span data-stu-id="58ad0-194">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="58ad0-195">Führen Sie die folgenden Schritte aus, um den Pfad der Datenbereinigung zu initiieren:</span><span class="sxs-lookup"><span data-stu-id="58ad0-195">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="58ad0-196">Entfernen Sie Wrap-und Unwrap-Berechtigungen für "O365 Exchange Online" aus Azure Key Vaults.</span><span class="sxs-lookup"><span data-stu-id="58ad0-196">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="58ad0-197">Stellen Sie eine [Verbindung mit Exchange Online PowerShell her](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps), indem Sie ein Arbeits-oder Schulkonto mit globalen Administratorrechten in Ihrer Organisation verwenden.</span><span class="sxs-lookup"><span data-stu-id="58ad0-197">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell?view=exchange-ps).</span></span>

3. <span data-ttu-id="58ad0-198">Führen Sie für jede DEP, die Postfächer enthält, die Sie löschen möchten, das Cmdlet " [DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) " wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="58ad0-198">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](https://docs.microsoft.com/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="58ad0-199">Wenn der Befehl fehlschlägt, stellen Sie sicher, dass Sie die Exchange Online Berechtigungen aus beiden Schlüsseln in Azure Key Vault entfernt haben, wie weiter oben in dieser Aufgabe angegeben.</span><span class="sxs-lookup"><span data-stu-id="58ad0-199">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="58ad0-200">Nachdem Sie den Parametern permanentdatapurgerequested-Switch mit dem Cmdlet "DataEncryptionPolicy" festgelegt haben, können Sie diese DEP nicht mehr Postfächern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-200"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="58ad0-201">Wenden Sie sich an den Microsoft-Support, und fordern Sie die Datenbereinigung eDocument.</span><span class="sxs-lookup"><span data-stu-id="58ad0-201">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="58ad0-202">Auf Ihre Anfrage hin sendet Microsoft Ihnen ein rechtliches Dokument zur Bestätigung und Autorisierung der Löschung von Daten.</span><span class="sxs-lookup"><span data-stu-id="58ad0-202">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="58ad0-203">Die Person in Ihrer Organisation, die sich als genehmigende Person im Angebot beim Onboarding angemeldet hat, muss dieses Dokument signieren.</span><span class="sxs-lookup"><span data-stu-id="58ad0-203">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="58ad0-204">Normalerweise handelt es sich dabei um eine Führungskraft oder eine andere designierte Person in Ihrem Unternehmen, die rechtlich befugt ist, die Unterlagen im Namen Ihrer Organisation zu signieren.</span><span class="sxs-lookup"><span data-stu-id="58ad0-204">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="58ad0-205">Wenn Ihr Vertreter das rechtliche Dokument unterzeichnet hat, senden Sie es an Microsoft (in der Regel über eine edoc-Signatur).</span><span class="sxs-lookup"><span data-stu-id="58ad0-205">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="58ad0-206">Sobald Microsoft das Dokument "Legal" erhält, führt Microsoft Cmdlets aus, um die Datenbereinigung auszulösen, die die Richtlinie zuerst löscht, die Postfächer für einen permanenten Löschvorgang markiert und dann den Verfügbarkeits Schlüssel löscht.</span><span class="sxs-lookup"><span data-stu-id="58ad0-206">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="58ad0-207">Nachdem der Daten Löschvorgang abgeschlossen wurde, wurden die Daten bereinigt, können nicht auf Exchange Online zugegriffen werden und sind nicht wiederherstellbar.</span><span class="sxs-lookup"><span data-stu-id="58ad0-207">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepointonlineonedriveforbusinessandteamsfiles"></a><span data-ttu-id="58ad0-208">Widerrufen von Kunden Schlüsseln und dem Verfügbarkeits Schlüssel für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien</span><span class="sxs-lookup"><span data-stu-id="58ad0-208">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="58ad0-209">Führen Sie die folgenden Schritte aus, um den Daten Lösch Pfad für SharePoint Online-, OneDrive für Unternehmen-und Microsoft Teams-Dateien zu initiieren:</span><span class="sxs-lookup"><span data-stu-id="58ad0-209">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="58ad0-210">Sperren Sie den Azure Key Vault-Zugriff.</span><span class="sxs-lookup"><span data-stu-id="58ad0-210">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="58ad0-211">Alle Key Vault-Administratoren müssen zustimmen, den Zugriff aufzuheben.</span><span class="sxs-lookup"><span data-stu-id="58ad0-211">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="58ad0-212">Sie löschen nicht den Azure-schlüsseltresor für SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="58ad0-212">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="58ad0-213">Schlüssel Tresore können von mehreren SharePoint Online Mandanten und DEPs gemeinsam verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="58ad0-213">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="58ad0-214">Wenden Sie sich an Microsoft, um den Verfügbarkeits Schlüssel zu löschen.</span><span class="sxs-lookup"><span data-stu-id="58ad0-214">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="58ad0-215">Wenn Sie sich an Microsoft wenden, um den Verfügbarkeits Schlüssel zu löschen, erhalten Sie ein rechtliches Dokument.</span><span class="sxs-lookup"><span data-stu-id="58ad0-215">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="58ad0-216">Die Person in Ihrer Organisation, die sich als genehmigende Person im Angebot beim Onboarding angemeldet hat, muss dieses Dokument signieren.</span><span class="sxs-lookup"><span data-stu-id="58ad0-216">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="58ad0-217">Normalerweise handelt es sich um eine Führungskraft oder eine andere designierte Person in Ihrem Unternehmen, die rechtlich befugt ist, die Unterlagen im Namen Ihrer Organisation zu signieren.</span><span class="sxs-lookup"><span data-stu-id="58ad0-217">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="58ad0-218">Wenn Ihr Vertreter das rechtliche Dokument signiert, senden Sie es an Microsoft (in der Regel über eine edoc-Signatur).</span><span class="sxs-lookup"><span data-stu-id="58ad0-218">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="58ad0-219">Sobald Microsoft das Dokument "Legal" erhält, führen wir Cmdlets aus, um die Datenbereinigung auszulösen, die das kryptografische Löschen des Mandanten Schlüssels, des Standort Schlüssels und aller einzelnen Einzeldokument Schlüssel ausführt, wodurch die Schlüsselhierarchie unwiderruflich unterbrochen wird.</span><span class="sxs-lookup"><span data-stu-id="58ad0-219">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="58ad0-220">Nachdem die Cmdlets für die Datenbereinigung abgeschlossen wurden, wurden die Daten gelöscht.</span><span class="sxs-lookup"><span data-stu-id="58ad0-220">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="58ad0-221">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="58ad0-221">Related articles</span></span>

- [<span data-ttu-id="58ad0-222">Dienst Verschlüsselung mit Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="58ad0-222">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="58ad0-223">Informationen zum Verfügbarkeits Schlüssel</span><span class="sxs-lookup"><span data-stu-id="58ad0-223">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="58ad0-224">Einrichten des Kunden Schlüssels</span><span class="sxs-lookup"><span data-stu-id="58ad0-224">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="58ad0-225">Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels</span><span class="sxs-lookup"><span data-stu-id="58ad0-225">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="58ad0-226">Customer Lockbox</span><span class="sxs-lookup"><span data-stu-id="58ad0-226">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="58ad0-227">Dienst Verschlüsselung</span><span class="sxs-lookup"><span data-stu-id="58ad0-227">Service Encryption</span></span>](office-365-service-encryption.md)
