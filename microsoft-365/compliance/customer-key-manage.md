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
# <a name="manage-customer-key"></a><span data-ttu-id="41bf3-103">Verwalten des Kundenschlüssels</span><span class="sxs-lookup"><span data-stu-id="41bf3-103">Manage Customer Key</span></span>

<span data-ttu-id="41bf3-104">Nachdem Sie den Kundenschlüssel für Office 365 eingerichtet haben, müssen Sie eine oder mehrere Datenverschlüsselungsrichtlinien (Data Encryption Policies, DEP) erstellen und zuweisen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-104">After you've set up Customer Key for Office 365, you'll need to create and assign one or more data encryption policies (DEP).</span></span> <span data-ttu-id="41bf3-105">Nachdem Sie Ihre DEPs zugewiesen haben, können Sie Ihre Schlüssel wie in diesem Artikel beschrieben verwalten.</span><span class="sxs-lookup"><span data-stu-id="41bf3-105">Once you've assigned your DEPs, you can manage your keys as described in this article.</span></span> <span data-ttu-id="41bf3-106">Weitere Informationen zum Kundenschlüssel finden Sie in den zugehörigen Themen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-106">Learn more about Customer Key in the related topics.</span></span>

## <a name="create-a-dep-for-use-with-multiple-workloads-for-all-tenant-users"></a><span data-ttu-id="41bf3-107">Erstellen einer DEP für die Verwendung mit mehreren Workloads für alle Mandantenbenutzer</span><span class="sxs-lookup"><span data-stu-id="41bf3-107">Create a DEP for use with multiple workloads for all tenant users</span></span>

<span data-ttu-id="41bf3-108">Bevor Sie beginnen, stellen Sie sicher, dass Sie die aufgaben, die zum Einrichten des Kunden erforderlich sind, abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="41bf3-108">Before you begin, ensure that you've completed the tasks required to set up Customer.</span></span> <span data-ttu-id="41bf3-109">Weitere Informationen finden Sie unter [Einrichten des Kundenschlüssels](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="41bf3-109">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="41bf3-110">Zum Erstellen der DEP benötigen Sie die Key Vault-URIs, die Sie während des Setups erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="41bf3-110">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="41bf3-111">Weitere Informationen finden Sie unter [Abrufen des URI für jeden Azure Key Vault-Schlüssel](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span><span class="sxs-lookup"><span data-stu-id="41bf3-111">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="41bf3-112">Führen Sie die folgenden Schritte aus, um eine DEP mit mehreren Arbeitsauslastungen zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="41bf3-112">To create a multi-workload DEP, follow these steps:</span></span>
  
1. <span data-ttu-id="41bf3-113">Stellen Sie auf Ihrem lokalen Computer mithilfe eines Unternehmens- oder Schulkontos, das über globale Administrator- oder Complianceadministratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in einem Windows PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-113">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="41bf3-114">Verwenden Sie zum Erstellen einer DEP das cmdlet New-M365DataAtRestEncryptionPolicy Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="41bf3-114">To create a DEP, use the New-M365DataAtRestEncryptionPolicy cmdlet.</span></span>

   ```powershell
   New-M365DataAtRestEncryptionPolicy -Name <PolicyName> -AzureKeyIDs <KeyVaultURI1, KeyVaultURI2> [-Description <String>]
   ```

   <span data-ttu-id="41bf3-115">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="41bf3-115">Where:</span></span>

   - <span data-ttu-id="41bf3-116">*PolicyName* ist der Name, den Sie für die Richtlinie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="41bf3-116">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="41bf3-117">Namen dürfen keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="41bf3-117">Names can't contain spaces.</span></span> <span data-ttu-id="41bf3-118">Beispiel: Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="41bf3-118">For example, Contoso_Global.</span></span>

   - <span data-ttu-id="41bf3-119">*KeyVaultURI1* ist der URI für den ersten Schlüssel in der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="41bf3-119">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="41bf3-120">Beispiel: <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span><span class="sxs-lookup"><span data-stu-id="41bf3-120">For example, <https://contosoWestUSvault1.vault.azure.net/keys/Key_01>.</span></span>

   - <span data-ttu-id="41bf3-121">*KeyVaultURI2* ist der URI für den zweiten Schlüssel in der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="41bf3-121">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="41bf3-122">Beispiel: <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span><span class="sxs-lookup"><span data-stu-id="41bf3-122">For example, <https://contosoCentralUSvault1.vault.azure.net/keys/Key_02>.</span></span> <span data-ttu-id="41bf3-123">Trennen Sie die beiden URI mittels Komma und Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-123">Separate the two URIs by a comma and a space.</span></span>

   - <span data-ttu-id="41bf3-124">*Die Richtlinienbeschreibung* ist eine benutzerfreundliche Beschreibung der Richtlinie, die Ihnen dabei hilft, sich daran zu erinnern, wofür die Richtlinie gilt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-124">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="41bf3-125">In der Beschreibung sind Leerzeichen erlaubt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-125">You can include spaces in the description.</span></span> <span data-ttu-id="41bf3-126">Beispiel: "Stammrichtlinie für mehrere Arbeitsauslastungen für alle Benutzer im Mandanten."</span><span class="sxs-lookup"><span data-stu-id="41bf3-126">For example, "Root policy for multiple workloads for all users in the tenant.".</span></span>

<span data-ttu-id="41bf3-127">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="41bf3-127">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Contoso_Global" -AzureKeyIDs "https://contosoWestUSvault1.vault.azure.net/keys/Key_01","https://contosoCentralUSvault1.vault.azure.net/keys/Key_02" -Description "Policy for multiple workloads for all users in the tenant."
```

### <a name="assign-multi-workload-policy"></a><span data-ttu-id="41bf3-128">Zuweisen einer Richtlinie mit mehreren Arbeitsauslastungen</span><span class="sxs-lookup"><span data-stu-id="41bf3-128">Assign multi-workload policy</span></span>

<span data-ttu-id="41bf3-129">Weisen Sie die DEP mithilfe des cmdlets Set-M365DataAtRestEncryptionPolicyAssignment zu.</span><span class="sxs-lookup"><span data-stu-id="41bf3-129">Assign the DEP by using the Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="41bf3-130">Nachdem Sie die Richtlinie zugewiesen haben, Microsoft 365 die Daten mit dem schlüssel verschlüsselt, der in der DEP identifiziert ist.</span><span class="sxs-lookup"><span data-stu-id="41bf3-130">Once you assign the policy, Microsoft 365 encrypts the data with the key identified in the DEP.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy <PolicyName or ID>
```

 <span data-ttu-id="41bf3-131">Dabei *ist PolicyName* der Name der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="41bf3-131">Where *PolicyName* is the name of the policy.</span></span> <span data-ttu-id="41bf3-132">Beispiel: Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="41bf3-132">For example, Contoso_Global.</span></span>

<span data-ttu-id="41bf3-133">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="41bf3-133">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Contoso_Global"
```

## <a name="create-a-dep-for-use-with-exchange-online-mailboxes"></a><span data-ttu-id="41bf3-134">Erstellen einer DEP für die Verwendung mit Exchange Online Postfächern</span><span class="sxs-lookup"><span data-stu-id="41bf3-134">Create a DEP for use with Exchange Online mailboxes</span></span>

<span data-ttu-id="41bf3-135">Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aufgaben zum Einrichten von Azure Key Vault abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="41bf3-135">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="41bf3-136">Weitere Informationen finden Sie unter [Einrichten des Kundenschlüssels](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="41bf3-136">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span> <span data-ttu-id="41bf3-137">Führen Sie diese Schritte aus, indem Sie eine Remoteverbindung mit Exchange Online Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41bf3-137">You'll complete these steps by remotely connecting to Exchange Online with Windows PowerShell.</span></span>

<span data-ttu-id="41bf3-138">Eine Datenverschlüsselungsrichtlinie (DEP) ist mit einer Reihe von im Azure Key Vault gespeicherten Schlüsseln verknüpft.</span><span class="sxs-lookup"><span data-stu-id="41bf3-138">A DEP is associated with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="41bf3-139">Sie weisen einem Postfach in der Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="41bf3-139">You assign a DEP to a mailbox in Microsoft 365.</span></span> <span data-ttu-id="41bf3-140">Microsoft 365 verwendet dann die in der Richtlinie identifizierten Schlüssel, um das Postfach zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="41bf3-140">Microsoft 365 will then use the keys identified in the policy to encrypt the mailbox.</span></span> <span data-ttu-id="41bf3-141">Zum Erstellen der DEP benötigen Sie die Key Vault-URIs, die Sie während des Setups erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="41bf3-141">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="41bf3-142">Weitere Informationen finden Sie unter [Abrufen des URI für jeden Azure Key Vault-Schlüssel](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span><span class="sxs-lookup"><span data-stu-id="41bf3-142">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>

<span data-ttu-id="41bf3-143">Nicht vergessen!</span><span class="sxs-lookup"><span data-stu-id="41bf3-143">Remember!</span></span> <span data-ttu-id="41bf3-144">Wenn Sie eine DEP erstellen, geben Sie zwei Schlüssel in zwei verschiedenen Azure Key Vaults an.</span><span class="sxs-lookup"><span data-stu-id="41bf3-144">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="41bf3-145">Erstellen Sie diese Schlüssel in zwei separaten Azure-Regionen, um georedundanz zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="41bf3-145">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>

<span data-ttu-id="41bf3-146">Führen Sie die folgenden Schritte aus, um eine DEP für die Verwendung mit einem Postfach zu erstellen:</span><span class="sxs-lookup"><span data-stu-id="41bf3-146">To create a DEP to use with a mailbox, follow these steps:</span></span>
  
1. <span data-ttu-id="41bf3-147">Stellen Sie auf Ihrem lokalen Computer mithilfe eines Arbeits- oder Schulkontos, das über globale Administrator- oder Exchange Online Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in einem Windows PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-147">On your local computer, using a work or school account that has global administrator or Exchange Online admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="41bf3-148">Um eine Datenverschlüsselungsrichtlinie zu erstellen, verwenden Sie das Cmdlet „New-DataEncryptionPolicy“, indem Sie den folgenden Befehl eingeben.</span><span class="sxs-lookup"><span data-stu-id="41bf3-148">To create a DEP, use the New-DataEncryptionPolicy cmdlet by typing the following command.</span></span>

   ```powershell
   New-DataEncryptionPolicy -Name <PolicyName> -Description "Policy Description" -AzureKeyIDs <KeyVaultURI1>, <KeyVaultURI2>
   ```

   <span data-ttu-id="41bf3-149">Dabei gilt:</span><span class="sxs-lookup"><span data-stu-id="41bf3-149">Where:</span></span>

   - <span data-ttu-id="41bf3-150">*PolicyName* ist der Name, den Sie für die Richtlinie verwenden möchten.</span><span class="sxs-lookup"><span data-stu-id="41bf3-150">*PolicyName* is the name you want to use for the policy.</span></span> <span data-ttu-id="41bf3-151">Namen dürfen keine Leerzeichen enthalten.</span><span class="sxs-lookup"><span data-stu-id="41bf3-151">Names can't contain spaces.</span></span> <span data-ttu-id="41bf3-152">Beispiel: USA_Postfächer.</span><span class="sxs-lookup"><span data-stu-id="41bf3-152">For example, USA_mailboxes.</span></span>

   - <span data-ttu-id="41bf3-153">*Die Richtlinienbeschreibung* ist eine benutzerfreundliche Beschreibung der Richtlinie, die Ihnen dabei hilft, sich daran zu erinnern, wofür die Richtlinie gilt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-153">*Policy Description* is a user-friendly description of the policy that will help you remember what the policy is for.</span></span> <span data-ttu-id="41bf3-154">In der Beschreibung sind Leerzeichen erlaubt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-154">You can include spaces in the description.</span></span> <span data-ttu-id="41bf3-155">Beispiel: "Stammschlüssel für Postfächer in den USA und ihren Gebieten".</span><span class="sxs-lookup"><span data-stu-id="41bf3-155">For example, "Root key for mailboxes in USA and its territories".</span></span>

   - <span data-ttu-id="41bf3-156">*KeyVaultURI1* ist der URI für den ersten Schlüssel in der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="41bf3-156">*KeyVaultURI1* is the URI for the first key in the policy.</span></span> <span data-ttu-id="41bf3-157">Beispiel: <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span><span class="sxs-lookup"><span data-stu-id="41bf3-157">For example, <https://contoso_EastUSvault01.vault.azure.net/keys/USA_key_01>.</span></span>

   - <span data-ttu-id="41bf3-158">*KeyVaultURI2* ist der URI für den zweiten Schlüssel in der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="41bf3-158">*KeyVaultURI2* is the URI for the second key in the policy.</span></span> <span data-ttu-id="41bf3-159">Beispiel: <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span><span class="sxs-lookup"><span data-stu-id="41bf3-159">For example, <https://contoso_EastUS2vault01.vault.azure.net/keys/USA_Key_02>.</span></span> <span data-ttu-id="41bf3-160">Trennen Sie die beiden URI mittels Komma und Leerzeichen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-160">Separate the two URIs by a comma and a space.</span></span>

   <span data-ttu-id="41bf3-161">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="41bf3-161">Example:</span></span>
  
   ```powershell
   New-DataEncryptionPolicy -Name USA_mailboxes -Description "Root key for mailboxes in USA and its territories" -AzureKeyIDs https://contoso_EastUSvault02.vault.azure.net/keys/USA_key_01, https://contoso_CentralUSvault02.vault.azure.net/keys/USA_Key_02
   ```

<span data-ttu-id="41bf3-162">Ausführliche Informationen zu Syntax und Parametern finden Sie unter [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="41bf3-162">For detailed syntax and parameter information, see [New-DataEncryptionPolicy](/powershell/module/exchange/new-data-encryptionpolicy).</span></span>

### <a name="assign-a-dep-to-a-mailbox"></a><span data-ttu-id="41bf3-163">Zuweisen einer Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach</span><span class="sxs-lookup"><span data-stu-id="41bf3-163">Assign a DEP to a mailbox</span></span>

<span data-ttu-id="41bf3-164">Zuweisen der Datenverschlüsselungsrichtlinie (DEP) zu einem Postfach mithilfe des Cmdlets „Set-Mailbox“.</span><span class="sxs-lookup"><span data-stu-id="41bf3-164">Assign the DEP to a mailbox by using the Set-Mailbox cmdlet.</span></span> <span data-ttu-id="41bf3-165">Nachdem Sie die Richtlinie zugewiesen haben, Microsoft 365 das Postfach mit dem in der DEP identifizierten Schlüssel verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="41bf3-165">Once you assign the policy, Microsoft 365 can encrypt the mailbox with the key identified in the DEP.</span></span>
  
```powershell
Set-Mailbox -Identity <MailboxIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="41bf3-166">Wobei *MailboxIdParameter* ein Benutzerpostfach angibt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-166">Where *MailboxIdParameter* specifies a user mailbox.</span></span> <span data-ttu-id="41bf3-167">Weitere Informationen zum Cmdlet „Set-Mailbox“ finden Sie unter [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span><span class="sxs-lookup"><span data-stu-id="41bf3-167">For more information about the Set-Mailbox cmdlet, see [Set-Mailbox](/powershell/module/exchange/set-mailbox).</span></span>

<span data-ttu-id="41bf3-168">In Hybridumgebungen können Sie den lokalen Postfachdaten, die mit Ihrem Mandanten synchronisiert werden, Exchange Online zuweisen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-168">In hybrid environments, you can assign a DEP to the on-premises mailbox data that is synchronized into your Exchange Online tenant.</span></span> <span data-ttu-id="41bf3-169">Um diesen synchronisierten Postfachdaten eine DEP zuzuordnen, verwenden Sie das cmdlet Set-MailUser Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="41bf3-169">To assign a DEP to this synchronized mailbox data, you'll use the Set-MailUser cmdlet.</span></span> <span data-ttu-id="41bf3-170">Weitere Informationen zu Postfachdaten in der Hybridumgebung finden Sie unter lokale Postfächer, die [Outlook für iOS](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)und Android mit moderner Hybridauthentifizierung verwenden.</span><span class="sxs-lookup"><span data-stu-id="41bf3-170">For more information about mailbox data in the hybrid environment, see [on-premises mailboxes using Outlook for iOS and Android with hybrid Modern Authentication](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth).</span></span>

```powershell
Set-MailUser -Identity <MailUserIdParameter> -DataEncryptionPolicy <PolicyName>
```

<span data-ttu-id="41bf3-171">Dabei *gibt MailUserIdParameter* einen E-Mail-Benutzer an (auch als E-Mail-aktivierter Benutzer bezeichnet).</span><span class="sxs-lookup"><span data-stu-id="41bf3-171">Where *MailUserIdParameter* specifies a mail user (also known as a mail-enabled user).</span></span> <span data-ttu-id="41bf3-172">Weitere Informationen zum cmdlet Set-MailUser finden Sie unter [Set-MailUser](/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="41bf3-172">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

## <a name="create-a-dep-for-use-with-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="41bf3-173">Erstellen einer DEP für die Verwendung mit SharePoint Online-, OneDrive for Business- und Teams Dateien</span><span class="sxs-lookup"><span data-stu-id="41bf3-173">Create a DEP for use with SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="41bf3-174">Bevor Sie beginnen, stellen Sie sicher, dass Sie die Aufgaben zum Einrichten von Azure Key Vault abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="41bf3-174">Before you begin, ensure that you've completed the tasks required to set up Azure Key Vault.</span></span> <span data-ttu-id="41bf3-175">Weitere Informationen finden Sie unter [Einrichten des Kundenschlüssels](customer-key-set-up.md).</span><span class="sxs-lookup"><span data-stu-id="41bf3-175">For information, see [Set up Customer Key](customer-key-set-up.md).</span></span>
  
<span data-ttu-id="41bf3-176">Zum Einrichten des Kundenschlüssels für SharePoint Online-, OneDrive for Business- und Teams-Dateien führen Sie diese Schritte aus, indem Sie eine Remoteverbindung mit SharePoint Online mit Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41bf3-176">To set up Customer Key for SharePoint Online, OneDrive for Business, and Teams files you complete these steps by remotely connecting to SharePoint Online with Windows PowerShell.</span></span>
  
<span data-ttu-id="41bf3-177">Sie ordnen eine DEP einem Satz von Schlüsseln zu, die in Azure Key Vault gespeichert sind.</span><span class="sxs-lookup"><span data-stu-id="41bf3-177">You associate a DEP with a set of keys stored in Azure Key Vault.</span></span> <span data-ttu-id="41bf3-178">Sie wenden eine Datenverschlüsselungsrichtlinie (DEP) auf alle Ihre Daten an einem geografischen Standort an, der auch als Geo bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="41bf3-178">You apply a DEP to all of your data in one geographic location, also called a geo.</span></span> <span data-ttu-id="41bf3-179">Wenn Sie das Multi-Geo-Feature von Office 365 verwenden, können Sie eine DEP pro Geografischem erstellen, mit der Möglichkeit, unterschiedliche Schlüssel pro Geografischem zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="41bf3-179">If you use the multi-geo feature of Office 365, you can create one DEP per geo with the capability to use different keys per geo.</span></span> <span data-ttu-id="41bf3-180">Wenn Sie multi-geo nicht verwenden, können Sie eine DEP in Ihrer Organisation für die Verwendung mit SharePoint Online-, OneDrive for Business- und Teams erstellen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-180">If you aren't using multi-geo, you can create one DEP in your organization for use with SharePoint Online, OneDrive for Business, and Teams files.</span></span> <span data-ttu-id="41bf3-181">Microsoft 365 verwendet die in der DEP identifizierten Schlüssel, um Ihre Daten in diesem Geografischen zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="41bf3-181">Microsoft 365 uses the keys identified in the DEP to encrypt your data in that geo.</span></span> <span data-ttu-id="41bf3-182">Zum Erstellen der DEP benötigen Sie die Key Vault-URIs, die Sie während des Setups erhalten haben.</span><span class="sxs-lookup"><span data-stu-id="41bf3-182">To create the DEP, you need the Key Vault URIs you obtained during setup.</span></span> <span data-ttu-id="41bf3-183">Weitere Informationen finden Sie unter [Abrufen des URI für jeden Azure Key Vault-Schlüssel](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span><span class="sxs-lookup"><span data-stu-id="41bf3-183">For information, see [Obtain the URI for each Azure Key Vault key](customer-key-set-up.md#obtain-the-uri-for-each-azure-key-vault-key).</span></span>
  
<span data-ttu-id="41bf3-184">Nicht vergessen!</span><span class="sxs-lookup"><span data-stu-id="41bf3-184">Remember!</span></span> <span data-ttu-id="41bf3-185">Wenn Sie eine DEP erstellen, geben Sie zwei Schlüssel in zwei verschiedenen Azure Key Vaults an.</span><span class="sxs-lookup"><span data-stu-id="41bf3-185">When you create a DEP, you specify two keys in two different Azure Key Vaults.</span></span> <span data-ttu-id="41bf3-186">Erstellen Sie diese Schlüssel in zwei separaten Azure-Regionen, um georedundanz zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="41bf3-186">Create these keys in two separate Azure regions to ensure geo-redundancy.</span></span>
  
<span data-ttu-id="41bf3-187">Um eine Datenverschlüsselungsrichtlinie (DEP) zu erstellen, müssen Sie mithilfe von Windows PowerShell eine Remote-Verbindung zu SharePoint Online herstellen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-187">To create a DEP, you need to remotely connect to SharePoint Online by using Windows PowerShell.</span></span>
  
1. <span data-ttu-id="41bf3-188">Verwenden Sie auf Ihrem lokalen Computer mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, Verbinden [Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps)SharePoint verwenden.</span><span class="sxs-lookup"><span data-stu-id="41bf3-188">On your local computer, using a work or school account that has global administrator permissions in your organization, [Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online?preserve-view=true&view=sharepoint-ps).</span></span>

2. <span data-ttu-id="41bf3-189">Führen Sie in der Microsoft SharePoint Online Management-Shell das Cmdlet Register-SPODataEncryptionPolicy wie folgt durch:</span><span class="sxs-lookup"><span data-stu-id="41bf3-189">In the Microsoft SharePoint Online Management Shell, run the Register-SPODataEncryptionPolicy cmdlet as follows:</span></span>

   ```powershell
   Register-SPODataEncryptionPolicy -Identity <adminSiteCollectionURL> -PrimaryKeyVaultName <PrimaryKeyVaultName> -PrimaryKeyName <PrimaryKeyName> -PrimaryKeyVersion <PrimaryKeyVersion> -SecondaryKeyVaultName <SecondaryKeyVaultName> -SecondaryKeyName <SecondaryKeyName> -SecondaryKeyVersion <SecondaryKeyVersion>
   ```

   <span data-ttu-id="41bf3-190">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="41bf3-190">Example:</span></span>
  
   ```powershell
   Register-SPODataEncryptionPolicy -Identity https://contoso.sharepoint.com -PrimaryKeyVaultName 'stageRG3vault' -PrimaryKeyName 'SPKey3' -PrimaryKeyVersion 'f635a23bd4a44b9996ff6aadd88d42ba' -SecondaryKeyVaultName 'stageRG5vault' -SecondaryKeyName 'SPKey5' -SecondaryKeyVersion '2b3e8f1d754f438dacdec1f0945f251a’
   ```

   <span data-ttu-id="41bf3-191">Sobald Sie die Datenverschlüsselungsrichtlinie (DEP) registrieren, beginnt die Verschlüsselung der Daten im Geo.</span><span class="sxs-lookup"><span data-stu-id="41bf3-191">When you register the DEP, encryption begins on the data in the geo.</span></span> <span data-ttu-id="41bf3-192">Die Verschlüsselung kann einige Zeit dauern.</span><span class="sxs-lookup"><span data-stu-id="41bf3-192">Encryption can take some time.</span></span> <span data-ttu-id="41bf3-193">Weitere Informationen zur Verwendung dieses Parameters finden Sie unter [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span><span class="sxs-lookup"><span data-stu-id="41bf3-193">For more information on using this parameter, see [Register-SPODataEncryptionPolicy](/powershell/module/sharepoint-online/register-spodataencryptionpolicy?preserve-view=true&view=sharepoint-ps).</span></span>

### <a name="view-the-deps-youve-created-for-exchange-online-mailboxes"></a><span data-ttu-id="41bf3-194">Anzeigen der dePs, die Sie für die Exchange Online erstellt haben</span><span class="sxs-lookup"><span data-stu-id="41bf3-194">View the DEPs you've created for Exchange Online mailboxes</span></span>

<span data-ttu-id="41bf3-195">Verwenden Sie zum Anzeigen einer Liste aller dePs, die Sie für Postfächer erstellt haben, das Get-DataEncryptionPolicy PowerShell-Cmdlet.</span><span class="sxs-lookup"><span data-stu-id="41bf3-195">To view a list of all the DEPs you've created for mailboxes, use the Get-DataEncryptionPolicy PowerShell cmdlet.</span></span>

1. <span data-ttu-id="41bf3-196">Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung [mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="41bf3-196">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="41bf3-197">Führen Sie zum Zurückgeben aller DEPs in Ihrer Organisation das cmdlet Get-DataEncryptionPolicy parameterfrei aus.</span><span class="sxs-lookup"><span data-stu-id="41bf3-197">To return all DEPs in your organization, run the Get-DataEncryptionPolicy cmdlet without any parameters.</span></span>

   ```powershell
   Get-DataEncryptionPolicy
   ```

   <span data-ttu-id="41bf3-198">Weitere Informationen zum cmdlet Get-DataEncryptionPolicy finden Sie unter [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span><span class="sxs-lookup"><span data-stu-id="41bf3-198">For more information about the Get-DataEncryptionPolicy cmdlet, see [Get-DataEncryptionPolicy](/powershell/module/exchange/get-dataencryptionpolicy).</span></span>

### <a name="assign-a-dep-before-you-migrate-a-mailbox-to-the-cloud"></a><span data-ttu-id="41bf3-199">Zuweisen einer DEP vor der Migration eines Postfachs in die Cloud</span><span class="sxs-lookup"><span data-stu-id="41bf3-199">Assign a DEP before you migrate a mailbox to the cloud</span></span>

<span data-ttu-id="41bf3-200">Wenn Sie die DEP zuweisen, Microsoft 365 den Inhalt des Postfachs mithilfe der zugewiesenen DEP während der Migration verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-200">When you assign the DEP, Microsoft 365 encrypts the contents of the mailbox using the assigned DEP during the migration.</span></span> <span data-ttu-id="41bf3-201">Dieser Vorgang ist effizienter als das Migrieren des Postfachs, das Zuweisen der DEP und dann das Warten auf die Verschlüsselung, was Stunden oder möglicherweise Tage dauern kann.</span><span class="sxs-lookup"><span data-stu-id="41bf3-201">This process is more efficient than migrating the mailbox, assigning the DEP, and then waiting for encryption to take place, which can take hours or possibly days.</span></span>

<span data-ttu-id="41bf3-202">Um einem Postfach eine DEP zuzuordnen, bevor Sie es zu Office 365, führen Sie das cmdlet Set-MailUser in Exchange Online PowerShell aus:</span><span class="sxs-lookup"><span data-stu-id="41bf3-202">To assign a DEP to a mailbox before you migrate it to Office 365, run the Set-MailUser cmdlet in Exchange Online PowerShell:</span></span>

1. <span data-ttu-id="41bf3-203">Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung [mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="41bf3-203">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="41bf3-204">Führen Sie Set-MailUser cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="41bf3-204">Run the Set-MailUser cmdlet.</span></span>

   ```powershell
   Set-MailUser -Identity <GeneralMailboxOrMailUserIdParameter> -DataEncryptionPolicy <DataEncryptionPolicyIdParameter>
   ```

   <span data-ttu-id="41bf3-205">Dabei *gibt GeneralMailboxOrMailUserIdParameter* ein Postfach an, und *DataEncryptionPolicyIdParameter* ist die ID der DEP.</span><span class="sxs-lookup"><span data-stu-id="41bf3-205">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox, and *DataEncryptionPolicyIdParameter* is the ID of the DEP.</span></span> <span data-ttu-id="41bf3-206">Weitere Informationen zum cmdlet Set-MailUser finden Sie unter [Set-MailUser](/powershell/module/exchange/set-mailuser).</span><span class="sxs-lookup"><span data-stu-id="41bf3-206">For more information about the Set-MailUser cmdlet, see [Set-MailUser](/powershell/module/exchange/set-mailuser).</span></span>

### <a name="determine-the-dep-assigned-to-a-mailbox"></a><span data-ttu-id="41bf3-207">Ermitteln der Datenverschlüsselungsrichtlinie (DEP), die einem Postfach zugewiesen ist</span><span class="sxs-lookup"><span data-stu-id="41bf3-207">Determine the DEP assigned to a mailbox</span></span>

<span data-ttu-id="41bf3-208">Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um zu ermitteln, welche Datenverschlüsselungsrichtlinie (DEP) einem Postfach zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="41bf3-208">To determine the DEP assigned to a mailbox, use the Get-MailboxStatistics cmdlet.</span></span> <span data-ttu-id="41bf3-209">Das Cmdlet meldet einen eindeutigen Bezeichner (GUID) zurück.</span><span class="sxs-lookup"><span data-stu-id="41bf3-209">The cmdlet returns a unique identifier (GUID).</span></span>
  
1. <span data-ttu-id="41bf3-210">Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung [mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="41bf3-210">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

   ```powershell
   Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl DataEncryptionPolicyID
   ```

   <span data-ttu-id="41bf3-211">Wobei *GeneralMailboxOrMailUserIdParameter* ein Postfach angibt und DataEncryptionPolicyID die GUID der DEP zurückgibt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-211">Where *GeneralMailboxOrMailUserIdParameter* specifies a mailbox and DataEncryptionPolicyID returns the GUID of the DEP.</span></span> <span data-ttu-id="41bf3-212">Weitere Informationen zum Cmdlet „Get-MailboxStatistics“ finden Sie unter [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span><span class="sxs-lookup"><span data-stu-id="41bf3-212">For more information about the Get-MailboxStatistics cmdlet, see [Get-MailboxStatistics](/powershell/module/exchange/get-mailboxstatistics).</span></span>
  
2. <span data-ttu-id="41bf3-213">Führen Sie Get-DataEncryptionPolicy cmdlet aus, um den Anzeigenamen der DEP zu finden, der das Postfach zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="41bf3-213">Run the Get-DataEncryptionPolicy cmdlet to find out the friendly name of the DEP to which the mailbox is assigned.</span></span>
  
   ```powershell
   Get-DataEncryptionPolicy <GUID>
   ```

   <span data-ttu-id="41bf3-214">Dabei ist der *GUID* derjenige GUID, der vom Cmdlet „Get-MailboxStatistics“ im vorherigen Schritt zurückgemeldet wurde.</span><span class="sxs-lookup"><span data-stu-id="41bf3-214">Where *GUID* is the GUID returned by the Get-MailboxStatistics cmdlet in the previous step.</span></span>

## <a name="verify-that-customer-key-has-finished-encryption"></a><span data-ttu-id="41bf3-215">Überprüfen, ob der Kundenschlüssel die Verschlüsselung beendet hat</span><span class="sxs-lookup"><span data-stu-id="41bf3-215">Verify that Customer Key has finished encryption</span></span>

<span data-ttu-id="41bf3-216">Verwenden Sie die Schritte in diesem Abschnitt, um sicherzustellen, dass die Verschlüsselung abgeschlossen ist, unabhängig davon, ob Sie einen Kundenschlüssel gerollt, eine neue DEP zugewiesen oder ein Postfach migriert haben.</span><span class="sxs-lookup"><span data-stu-id="41bf3-216">Whether you've rolled a Customer Key, assigned a new DEP, or migrated a mailbox, use the steps in this section to ensure that encryption completes.</span></span>

### <a name="verify-encryption-completes-for-exchange-online-mailboxes"></a><span data-ttu-id="41bf3-217">Überprüfen, ob die Verschlüsselung für Exchange Online abgeschlossen ist</span><span class="sxs-lookup"><span data-stu-id="41bf3-217">Verify encryption completes for Exchange Online mailboxes</span></span>

<span data-ttu-id="41bf3-218">Das Verschlüsseln eines Postfachs kann einige Zeit in Anspruch nehmen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-218">Encrypting a mailbox can take some time.</span></span> <span data-ttu-id="41bf3-219">Bei der ersten Verschlüsselung muss das Postfach auch vollständig von einer Datenbank in eine andere verschoben werden, bevor der Dienst das Postfach verschlüsseln kann.</span><span class="sxs-lookup"><span data-stu-id="41bf3-219">For first time encryption, the mailbox must also completely move from one database to another before the service can encrypt the mailbox.</span></span>
  
<span data-ttu-id="41bf3-220">Verwenden Sie das Cmdlet „Get-MailboxStatistics“, um festzustellen, ob ein Postfach verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="41bf3-220">Use the Get-MailboxStatistics cmdlet to determine if a mailbox is encrypted.</span></span>
  
```powershell
Get-MailboxStatistics -Identity <GeneralMailboxOrMailUserIdParameter> | fl IsEncrypted
```

<span data-ttu-id="41bf3-221">Die IsEncrypted-Eigenschaft gibt den Wert **true** zurück, wenn das Postfach verschlüsselt ist, und den Wert **false,** wenn das Postfach nicht verschlüsselt ist.</span><span class="sxs-lookup"><span data-stu-id="41bf3-221">The IsEncrypted property returns a value of **true** if the mailbox is encrypted and a value of **false** if the mailbox isn't encrypted.</span></span> <span data-ttu-id="41bf3-222">Die Zeit zum Abschließen von Postfachbewegungen hängt von der Anzahl der Postfächer ab, denen Sie zum ersten Mal eine DEP zuweisen, und der Größe der Postfächer.</span><span class="sxs-lookup"><span data-stu-id="41bf3-222">The time to complete mailbox moves depends on the number of mailboxes to which you assign a DEP for the first time, and the size of the mailboxes.</span></span> <span data-ttu-id="41bf3-223">Wenn die Postfächer nach einer Woche nach dem Zugewiesenen der DEP nicht verschlüsselt wurden, wenden Sie sich an Microsoft.</span><span class="sxs-lookup"><span data-stu-id="41bf3-223">If the mailboxes haven't been encrypted after a week from the time you assigned the DEP, contact Microsoft.</span></span>

<span data-ttu-id="41bf3-224">Das New-MoveRequest cmdlet ist nicht mehr für lokale Postfachbewegungen verfügbar.</span><span class="sxs-lookup"><span data-stu-id="41bf3-224">The New-MoveRequest cmdlet is no longer available for local mailbox moves.</span></span> <span data-ttu-id="41bf3-225">Weitere Informationen [finden Sie in](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) dieser Ankündigung.</span><span class="sxs-lookup"><span data-stu-id="41bf3-225">Refer to [this announcement](https://techcommunity.microsoft.com/t5/exchange-team-blog/disabling-new-moverequest-for-local-mailbox-moves/bc-p/1332141) for additional information.</span></span>

### <a name="verify-encryption-completes-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="41bf3-226">Überprüfen, ob die Verschlüsselung für SharePoint Online-, OneDrive for Business- und Teams ist</span><span class="sxs-lookup"><span data-stu-id="41bf3-226">Verify encryption completes for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="41bf3-227">Überprüfen Sie den Status der Verschlüsselung, indem Sie Get-SPODataEncryptionPolicy cmdlet wie folgt ausführen:</span><span class="sxs-lookup"><span data-stu-id="41bf3-227">Check on the status of encryption by running the Get-SPODataEncryptionPolicy cmdlet as follows:</span></span>

```PowerShell
   Get-SPODataEncryptionPolicy -Identity <SPOAdminSiteUrl>
```

<span data-ttu-id="41bf3-228">Die Ausgabe dieses Cmdlets umfasst Folgendes:</span><span class="sxs-lookup"><span data-stu-id="41bf3-228">The output from this cmdlet includes:</span></span>
  
- <span data-ttu-id="41bf3-229">URI des Primärschlüssels.</span><span class="sxs-lookup"><span data-stu-id="41bf3-229">The URI of the primary key.</span></span>

- <span data-ttu-id="41bf3-230">URI des Sekundärschlüssels.</span><span class="sxs-lookup"><span data-stu-id="41bf3-230">The URI of the secondary key.</span></span>

- <span data-ttu-id="41bf3-231">Verschlüsselungsstatus für den Geo.</span><span class="sxs-lookup"><span data-stu-id="41bf3-231">The encryption status for the geo.</span></span> <span data-ttu-id="41bf3-232">Mögliche weitere Angaben:</span><span class="sxs-lookup"><span data-stu-id="41bf3-232">Possible states include:</span></span>

  - <span data-ttu-id="41bf3-233">**Unregistered:** (Nicht registriert) Die Customer Key-Verschlüsselung wurde noch nicht angewendet.</span><span class="sxs-lookup"><span data-stu-id="41bf3-233">**Unregistered:** Customer Key encryption has not yet been applied.</span></span>

  - <span data-ttu-id="41bf3-234">**Registering:** (Registrierung läuft) Die Customer Key-Verschlüsselung wurde angewendet wurde und Ihre Dateien werden gegenwärtig gerade verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-234">**Registering:** Customer Key encryption has been applied and your files are in the process of being encrypted.</span></span> <span data-ttu-id="41bf3-235">Wenn der Schlüssel für den Geografischen registriert wird, werden Ihnen auch Informationen angezeigt, welcher Prozentsatz der Websites im Geografischen abgeschlossen ist, damit Sie den Verschlüsselungsfortschritt überwachen können.</span><span class="sxs-lookup"><span data-stu-id="41bf3-235">If the key for the geo is registering, you'll also be shown information on what percentage of sites in the geo are complete so that you can monitor encryption progress.</span></span>

  - <span data-ttu-id="41bf3-236">**Registered:** (Registriert) Die Customer Key- Verschlüsselung wurde angewendet, und alle Dateien auf allen Websites wurden verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-236">**Registered:** Customer Key encryption has been applied, and all files in all sites have been encrypted.</span></span>

  - <span data-ttu-id="41bf3-237">**Rolling:** Das Erstellen eines sich fortlaufend ändernden, sogenannten Rolling-Codes für den Schlüssel ist in Gang.</span><span class="sxs-lookup"><span data-stu-id="41bf3-237">**Rolling:** A key roll is in progress.</span></span> <span data-ttu-id="41bf3-238">Wenn der Schlüssel für den geografischen Standort rollt, erhalten Sie außerdem Informationen dazu, welcher Prozentsatz der Websites den Schlüsselrollvorgang abgeschlossen hat, damit Sie den Fortschritt überwachen können.</span><span class="sxs-lookup"><span data-stu-id="41bf3-238">If the key for the geo is rolling, you'll also be shown information on what percentage of sites have completed the key roll operation so that you can monitor progress.</span></span>

## <a name="get-details-about-deps-you-use-with-multiple-workloads"></a><span data-ttu-id="41bf3-239">Erhalten Von Details zu DEPs, die Sie mit mehreren Arbeitsauslastungen verwenden</span><span class="sxs-lookup"><span data-stu-id="41bf3-239">Get details about DEPs you use with multiple workloads</span></span>

<span data-ttu-id="41bf3-240">Führen Sie die folgenden Schritte aus, um Details zu allen DEPs zu erhalten, die Sie für die Verwendung mit mehreren Workloads erstellt haben:</span><span class="sxs-lookup"><span data-stu-id="41bf3-240">To get details about all of the DEPs you've created to use with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="41bf3-241">Stellen Sie auf Ihrem lokalen Computer mithilfe eines Unternehmens- oder Schulkontos, das über globale Administrator- oder Complianceadministratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in einem Windows PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-241">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

   - <span data-ttu-id="41bf3-242">Führen Sie diesen Befehl aus, um die Liste aller DEPs mit mehreren Arbeitsauslastungen in der Organisation zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="41bf3-242">To return the list of all multi-workload DEPs in the organization, run this command.</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy
     ```

   - <span data-ttu-id="41bf3-243">Führen Sie diesen Befehl aus, um Details zu einer bestimmten DEP zurückzukehren.</span><span class="sxs-lookup"><span data-stu-id="41bf3-243">To return details about a specific DEP, run this command.</span></span> <span data-ttu-id="41bf3-244">In diesem Beispiel werden detaillierte Informationen für die DEP mit dem Namen "Contoso_Global" zurückgegeben.</span><span class="sxs-lookup"><span data-stu-id="41bf3-244">This example returns detailed information for the DEP named "Contoso_Global".</span></span>

     ```powershell
        Get-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global"
     ```

## <a name="get-multi-workload-dep-assignment-information"></a><span data-ttu-id="41bf3-245">Get multi-workload DEP assignment information</span><span class="sxs-lookup"><span data-stu-id="41bf3-245">Get multi-workload DEP assignment information</span></span>

<span data-ttu-id="41bf3-246">Führen Sie die folgenden Schritte aus, um herauszufinden, welche DEP Ihrem Mandanten derzeit zugewiesen ist.</span><span class="sxs-lookup"><span data-stu-id="41bf3-246">To find out which DEP is currently assigned to your tenant, follow these steps.</span></span> 

1. <span data-ttu-id="41bf3-247">Stellen Sie auf Ihrem lokalen Computer mithilfe eines Unternehmens- oder Schulkontos, das über globale Administrator- oder Complianceadministratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in einem Windows PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-247">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="41bf3-248">Geben Sie diesen Befehl ein.</span><span class="sxs-lookup"><span data-stu-id="41bf3-248">Type this command.</span></span>

   ```powershell
      Get-M365DataAtRestEncryptionPolicyAssignment
   ```

## <a name="disable-a-multi-workload-dep"></a><span data-ttu-id="41bf3-249">Deaktivieren einer DEP mit mehreren Arbeitsauslastungen</span><span class="sxs-lookup"><span data-stu-id="41bf3-249">Disable a multi-workload DEP</span></span>

<span data-ttu-id="41bf3-250">Bevor Sie eine DEP mit mehreren Arbeitsauslastungen deaktivieren, müssen Sie die DEP von Arbeitsauslastungen in Ihrem Mandanten entfernen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-250">Before you disable a multi-workload DEP, unassign the DEP from workloads in your tenant.</span></span> <span data-ttu-id="41bf3-251">Führen Sie die folgenden Schritte aus, um eine mit mehreren Workloads verwendete DEP zu deaktivieren:</span><span class="sxs-lookup"><span data-stu-id="41bf3-251">To disable a DEP used with multiple workloads, complete these steps:</span></span>

1. <span data-ttu-id="41bf3-252">Stellen Sie auf Ihrem lokalen Computer mithilfe eines Unternehmens- oder Schulkontos, das über globale Administrator- oder Complianceadministratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in einem Windows PowerShell herstellen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-252">On your local computer, using a work or school account that has global administrator or compliance admin permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) in a Windows PowerShell window.</span></span>

2. <span data-ttu-id="41bf3-253">Führen Sie Set-M365DataAtRestEncryptionPolicy cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="41bf3-253">Run the Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span>
  
   ```powershell
   Set-M365DataAtRestEncryptionPolicy -[Identity] "PolicyName" -Enabled $false
   ```

<span data-ttu-id="41bf3-254">Dabei *ist PolicyName* der Name oder die eindeutige ID der Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="41bf3-254">Where *PolicyName* is the name or unique ID of the policy.</span></span> <span data-ttu-id="41bf3-255">Beispiel: Contoso_Global.</span><span class="sxs-lookup"><span data-stu-id="41bf3-255">For example, Contoso_Global.</span></span>

<span data-ttu-id="41bf3-256">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="41bf3-256">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "Contoso_Global" -Enabled $false
```

## <a name="restore-azure-key-vault-keys"></a><span data-ttu-id="41bf3-257">Wiederherstellen von Azure Key Vault-Schlüsseln</span><span class="sxs-lookup"><span data-stu-id="41bf3-257">Restore Azure Key Vault keys</span></span>

<span data-ttu-id="41bf3-258">Verwenden Sie vor dem Ausführen einer Wiederherstellung die von Soft Delete bereitgestellten Wiederherstellungsfunktionen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-258">Before performing a restore, use the recovery capabilities provided by soft delete.</span></span> <span data-ttu-id="41bf3-259">Für alle mit Customer Key verwendeten Schlüssel muss Soft Delete aktiviert sein.</span><span class="sxs-lookup"><span data-stu-id="41bf3-259">All keys that are used with Customer Key are required to have soft delete enabled.</span></span> <span data-ttu-id="41bf3-260">Soft Delete wirkt wie ein Recycling-Mülleimer und ermöglicht die Wiederherstellung von bis zu 90 Tagen, ohne dass eine Wiederherstellung erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="41bf3-260">Soft delete acts like a recycle bin and allows recovery for up to 90 days without the need to restore.</span></span> <span data-ttu-id="41bf3-261">Eine Wiederherstellung sollte nur unter extremen und außergewöhnlichen Umständen erforderlich sein, beispielsweise, wenn ein Schlüssel oder ein Schlüsseltresor verloren geht.</span><span class="sxs-lookup"><span data-stu-id="41bf3-261">Restore should only be required in extreme or unusual circumstances, for example if the key or key vault is lost.</span></span> <span data-ttu-id="41bf3-262">Wenn Sie einen Schlüssel zur Verwendung mit Customer Key wiederherstellen müssen, führen Sie in Azure PowerShell das Cmdlet „Restore-AzureKeyVaultKey“ wie folgt aus:</span><span class="sxs-lookup"><span data-stu-id="41bf3-262">If you must restore a key for use with Customer Key, in Azure PowerShell, run the Restore-AzureKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName <vault name> -InputFile <filename>
```

<span data-ttu-id="41bf3-263">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="41bf3-263">For example:</span></span>
  
```powershell
Restore-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -InputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

<span data-ttu-id="41bf3-264">Wenn der Schlüsseltresor bereits einen Schlüssel mit demselben Namen enthält, schlägt der Wiederherstellungsvorgang fehl.</span><span class="sxs-lookup"><span data-stu-id="41bf3-264">If the key vault already contains a key with the same name, the restore operation fails.</span></span> <span data-ttu-id="41bf3-265">Restore-AzKeyVaultKey werden alle Schlüsselversionen und alle Metadaten für den Schlüssel einschließlich des Schlüsselnamens wiederhergestellt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-265">Restore-AzKeyVaultKey restores all key versions and all metadata for the key including the key name.</span></span>
  
## <a name="manage-key-vault-permissions"></a><span data-ttu-id="41bf3-266">Verwalten von Schlüsseltresor-Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="41bf3-266">Manage key vault permissions</span></span>

<span data-ttu-id="41bf3-267">Mehrere Cmdlets stehen zur Verfügung, mit denen Sie die Schlüsseltresor-Berechtigungen ansehen und, falls erforderlich, entfernen können.</span><span class="sxs-lookup"><span data-stu-id="41bf3-267">Several cmdlets are available that enable you to view and, if necessary, remove key vault permissions.</span></span> <span data-ttu-id="41bf3-268">Möglicherweise müssen Sie Berechtigungen entfernen, beispielsweise, wenn ein Mitarbeiter das Team verlässt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-268">You might need to remove permissions, for example, when an employee leaves the team.</span></span> <span data-ttu-id="41bf3-269">Für jede dieser Aufgaben verwenden Sie Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="41bf3-269">For each of these tasks, you will use Azure PowerShell.</span></span> <span data-ttu-id="41bf3-270">Weitere Informationen zu Azure PowerShell finden Sie [unter Overview of Azure PowerShell](/powershell/azure/).</span><span class="sxs-lookup"><span data-stu-id="41bf3-270">For information about Azure PowerShell, see [Overview of Azure PowerShell](/powershell/azure/).</span></span>

<span data-ttu-id="41bf3-271">Führen Sie zum Anzeigen von Schlüsseltresorberechtigungen das cmdlet Get-AzKeyVault aus.</span><span class="sxs-lookup"><span data-stu-id="41bf3-271">To view key vault permissions, run the Get-AzKeyVault cmdlet.</span></span>

```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="41bf3-272">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="41bf3-272">For example:</span></span>

```powershell
Get-AzKeyVault -VaultName Contoso-O365EX-NA-VaultA1
```

<span data-ttu-id="41bf3-273">Führen Sie zum Entfernen der Berechtigungen eines Administrators das cmdlet Remove-AzKeyVaultAccessPolicy aus:</span><span class="sxs-lookup"><span data-stu-id="41bf3-273">To remove an administrator's permissions, run the Remove-AzKeyVaultAccessPolicy cmdlet:</span></span>
  
```powershell
Remove-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user>
```

<span data-ttu-id="41bf3-274">Beispiel:</span><span class="sxs-lookup"><span data-stu-id="41bf3-274">For example:</span></span>

```powershell
Remove-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com
```

## <a name="roll-back-from-customer-key-to-microsoft-managed-keys"></a><span data-ttu-id="41bf3-275">Rollback vom Kundenschlüssel zu verwalteten Schlüsseln von Microsoft</span><span class="sxs-lookup"><span data-stu-id="41bf3-275">Roll back from Customer Key to Microsoft managed Keys</span></span>

<span data-ttu-id="41bf3-276">Wenn Sie zu von Microsoft verwalteten Schlüsseln zurückkehren müssen, können Sie dies.</span><span class="sxs-lookup"><span data-stu-id="41bf3-276">If you need to revert to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="41bf3-277">Beim Offboard werden Ihre Daten mithilfe der standardverschlüsselten Verschlüsselung, die von jeder einzelnen Arbeitsauslastung unterstützt wird, erneut verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-277">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="41bf3-278">Beispielsweise unterstützt Exchange Online Standardverschlüsselung mithilfe von von Microsoft verwalteten Schlüsseln.</span><span class="sxs-lookup"><span data-stu-id="41bf3-278">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="41bf3-279">Offboarding ist nicht identisch mit einer Datenbereinigung.</span><span class="sxs-lookup"><span data-stu-id="41bf3-279">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="41bf3-280">Eine Datenbereinigung löscht die Daten Ihrer Organisation dauerhaft aus Microsoft 365 offboarding nicht.</span><span class="sxs-lookup"><span data-stu-id="41bf3-280">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="41bf3-281">Sie können keine Datenbereinigung für eine Richtlinie mit mehreren Arbeitsauslastungen ausführen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-281">You can't perform a data purge for a multiple workload policy.</span></span>

<span data-ttu-id="41bf3-282">Wenn Sie den Kundenschlüssel nicht mehr zum Zuweisen von DEPs mit mehreren Arbeitsauslastungen verwenden möchten, müssen Sie den Microsoft-Support mit einer Anforderung an "offboard" über den Kundenschlüssel erreichen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-282">If you decide not to use Customer Key for assigning multi-workload DEPs anymore then you'll need to reach out to Microsoft support with a request to “offboard” from Customer Key.</span></span> <span data-ttu-id="41bf3-283">Bitten Sie das Supportteam, eine Dienstanfrage an Microsoft 365 Kundenschlüsselteam zu senden.</span><span class="sxs-lookup"><span data-stu-id="41bf3-283">Ask the support team to file a service request against Microsoft 365 Customer Key team.</span></span> <span data-ttu-id="41bf3-284">Wenden Sie sich an m365-ck@service.microsoft.com, wenn Sie Fragen haben.</span><span class="sxs-lookup"><span data-stu-id="41bf3-284">Reach out to m365-ck@service.microsoft.com if you have any questions.</span></span>

<span data-ttu-id="41bf3-285">Wenn Sie einzelne Postfächer nicht mehr mithilfe von DEPs auf Postfachebene verschlüsseln möchten, können Sie dePs auf Postfachebene von allen Postfächern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-285">If you do not want to encrypt individual mailboxes using mailbox level DEPs anymore, then you can unassign mailbox level DEPs from all your mailboxes.</span></span>

<span data-ttu-id="41bf3-286">Verwenden Sie das PowerShell-Cmdlet, um die Set-Mailbox zuzuweisen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-286">To unassign mailbox DEPs, use the Set-Mailbox PowerShell cmdlet.</span></span>

1. <span data-ttu-id="41bf3-287">Stellen Sie mithilfe eines Arbeits- oder Schulkontos, das über globale Administratorberechtigungen in Ihrer Organisation verfügt, eine Verbindung [mit Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="41bf3-287">Using a work or school account that has global administrator permissions in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="41bf3-288">Führen Sie Set-Mailbox cmdlet aus.</span><span class="sxs-lookup"><span data-stu-id="41bf3-288">Run the Set-Mailbox cmdlet.</span></span>

   ```powershell
   Set-Mailbox -Identity <mailbox> -DataEncryptionPolicy $NULL
   ```

<span data-ttu-id="41bf3-289">Wenn Sie dieses Cmdlet ausführen, wird die derzeit zugewiesene DEP entfernt und das Postfach mithilfe der DEP, die standardmäßig von Microsoft verwalteten Schlüsseln zugeordnet ist, erneut verschlüsselt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-289">Running this cmdlet unassigns the currently assigned DEP and reencrypts the mailbox using the DEP associated with default Microsoft-managed keys.</span></span> <span data-ttu-id="41bf3-290">Die von verwalteten Schlüsseln von Microsoft verwendete DEP kann nicht entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="41bf3-290">You can't unassign the DEP used by Microsoft managed keys.</span></span> <span data-ttu-id="41bf3-291">Wenn Sie keine von Microsoft verwalteten Schlüssel verwenden möchten, können Sie dem Postfach eine weitere Kundenschlüssel-DEP zuweisen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-291">If you don't want to use Microsoft-managed keys, you can assign another Customer Key DEP to the mailbox.</span></span>

## <a name="revoke-your-keys-and-start-the-data-purge-path-process"></a><span data-ttu-id="41bf3-292">Widerrufen Der Schlüssel und Starten des Datenbereinigungspfadprozesses</span><span class="sxs-lookup"><span data-stu-id="41bf3-292">Revoke your keys and start the data purge path process</span></span>

<span data-ttu-id="41bf3-293">Sie steuern den Widerruf aller Stammschlüssel, einschließlich des Verfügbarkeitsschlüssels.</span><span class="sxs-lookup"><span data-stu-id="41bf3-293">You control the revocation of all root keys including the availability key.</span></span> <span data-ttu-id="41bf3-294">Customer Key bietet die Kontrolle über den Aspekt der Beendigungsplanung der gesetzlichen Anforderungen für Sie.</span><span class="sxs-lookup"><span data-stu-id="41bf3-294">Customer Key provides control of the exit planning aspect of the regulatory requirements for you.</span></span> <span data-ttu-id="41bf3-295">Wenn Sie ihre Schlüssel widerrufen möchten, um Ihre Daten zu löschen und den Dienst zu beenden, löscht der Dienst den Verfügbarkeitsschlüssel, sobald der Datenlöschvorgang abgeschlossen ist.</span><span class="sxs-lookup"><span data-stu-id="41bf3-295">If you decide to revoke your keys to purge your data and exit the service, the service deletes the availability key once the data purge process completes.</span></span> <span data-ttu-id="41bf3-296">Dies wird für Kundenschlüssel-DEPs unterstützt, die einzelnen Postfächern zugewiesen sind.</span><span class="sxs-lookup"><span data-stu-id="41bf3-296">This is supported for Customer Key DEPs that are assigned to individual mailboxes.</span></span>

<span data-ttu-id="41bf3-297">Microsoft 365 überwacht und überprüft den Datenbereinigungspfad.</span><span class="sxs-lookup"><span data-stu-id="41bf3-297">Microsoft 365 audits and validates the data purge path.</span></span> <span data-ttu-id="41bf3-298">Weitere Informationen finden Sie im SSAE 18 SOC 2-Bericht, der im [Service Trust Portal verfügbar ist.](https://servicetrust.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="41bf3-298">For more information, see the SSAE 18 SOC 2 Report available on the [Service Trust Portal](https://servicetrust.microsoft.com/).</span></span> <span data-ttu-id="41bf3-299">Darüber hinaus empfiehlt Microsoft die folgenden Dokumente:</span><span class="sxs-lookup"><span data-stu-id="41bf3-299">In addition, Microsoft recommends the following documents:</span></span>

- [<span data-ttu-id="41bf3-300">Leitfaden zur Risikobewertung und Compliance für Finanzinstitute in der Microsoft Cloud</span><span class="sxs-lookup"><span data-stu-id="41bf3-300">Risk Assessment and Compliance Guide for Financial Institutions in the Microsoft Cloud</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=edee9b14-3661-4a16-ba83-c35caf672bd7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

- [<span data-ttu-id="41bf3-301">Überlegungen zur O365-Beendigungsplanung</span><span class="sxs-lookup"><span data-stu-id="41bf3-301">O365 Exit Planning Considerations</span></span>](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=77ea7ebf-ce1b-4a5f-9972-d2d81a951d99&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)

<span data-ttu-id="41bf3-302">Das Löschen von DEP mit mehreren Arbeitslasten wird für den Microsoft 365 nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="41bf3-302">Purging of multi-workload DEP is not supported for Microsoft 365 Customer Key.</span></span> <span data-ttu-id="41bf3-303">Die DEP mit mehreren Arbeitsauslastungen wird verwendet, um Daten über mehrere Arbeitsauslastungen hinweg für alle Mandantenbenutzer zu verschlüsseln.</span><span class="sxs-lookup"><span data-stu-id="41bf3-303">The multi-workload DEP is used to encrypt data across multiple workloads across all tenant users.</span></span> <span data-ttu-id="41bf3-304">Das Löschen einer solchen DEP würde dazu führen, dass auf Daten aus mehreren Arbeitsauslastungen nicht mehr zugegriffen werden kann.</span><span class="sxs-lookup"><span data-stu-id="41bf3-304">Purging such DEP would result into data from across multiple workloads become inaccessible.</span></span> <span data-ttu-id="41bf3-305">Wenn Sie entscheiden, Microsoft 365 dienste vollständig zu beenden, können Sie den Pfad der Mandantenlöschung pro dokumentiertem Prozess verfolgen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-305">If you decide to exit Microsoft 365 services altogether then you could pursue the path of tenant deletion per the documented process.</span></span> <span data-ttu-id="41bf3-306">Erfahren [Sie, wie Sie einen Mandanten in Azure Active Directoy löschen.](/azure/active-directory/enterprise-users/directory-delete-howto)</span><span class="sxs-lookup"><span data-stu-id="41bf3-306">See [how to delete a tenant in Azure Active Directoy](/azure/active-directory/enterprise-users/directory-delete-howto).</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-exchange-online-and-skype-for-business"></a><span data-ttu-id="41bf3-307">Widerrufen Sie Ihre Kundenschlüssel und den Verfügbarkeitsschlüssel für Exchange Online und Skype for Business</span><span class="sxs-lookup"><span data-stu-id="41bf3-307">Revoke your Customer Keys and the availability key for Exchange Online and Skype for Business</span></span>

<span data-ttu-id="41bf3-308">Wenn Sie den Datenbereinigungspfad für Exchange Online und Skype for Business initiieren, legen Sie eine permanente Datenbereinigungsanforderung für eine DEP fest.</span><span class="sxs-lookup"><span data-stu-id="41bf3-308">When you initiate the data purge path for Exchange Online and Skype for Business, you set a permanent data purge request on a DEP.</span></span> <span data-ttu-id="41bf3-309">Dadurch werden verschlüsselte Daten in den Postfächern, denen diese DEP zugewiesen ist, dauerhaft gelöscht.</span><span class="sxs-lookup"><span data-stu-id="41bf3-309">Doing so permanently deletes encrypted data within the mailboxes to which that DEP is assigned.</span></span>

<span data-ttu-id="41bf3-310">Da Sie das PowerShell-Cmdlet nur für eine DEP gleichzeitig ausführen können, sollten Sie eine einzelne DEP allen Postfächern erneut zuweisen, bevor Sie den Datenbereinigungspfad initiieren.</span><span class="sxs-lookup"><span data-stu-id="41bf3-310">Since you can only run the PowerShell cmdlet against one DEP at a time, consider reassigning a single DEP to all of your mailboxes before you initiate the data purge path.</span></span>

> [!WARNING]
> <span data-ttu-id="41bf3-311">Verwenden Sie nicht den Pfad zum Löschen von Daten, um eine Teilmenge Ihrer Postfächer zu löschen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-311">Do not use the data purge path to delete a subset of your mailboxes.</span></span> <span data-ttu-id="41bf3-312">Dieser Vorgang ist nur für Kunden gedacht, die den Dienst verlassen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-312">This process is only intended for customers who are exiting the service.</span></span>

<span data-ttu-id="41bf3-313">Führen Sie die folgenden Schritte aus, um den Datenbereinigungspfad zu initiieren:</span><span class="sxs-lookup"><span data-stu-id="41bf3-313">To initiate the data purge path, complete these steps:</span></span>

1. <span data-ttu-id="41bf3-314">Entfernen von Umbruch- und Auspackberechtigungen für "O365 Exchange Online" aus Azure Key Vaults.</span><span class="sxs-lookup"><span data-stu-id="41bf3-314">Remove wrap and unwrap permissions for "O365 Exchange Online" from Azure Key Vaults.</span></span>

2. <span data-ttu-id="41bf3-315">Stellen Sie mithilfe eines Arbeits- oder Schulkontos mit globalen Administratorrechten in Ihrer Organisation eine Verbindung mit [Exchange Online PowerShell sicher.](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="41bf3-315">Using a work or school account that has global administrator privileges in your organization, [connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

3. <span data-ttu-id="41bf3-316">Führen Sie für jede DEP, die zu löschende Postfächer enthält, das [Cmdlet Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) wie folgt aus.</span><span class="sxs-lookup"><span data-stu-id="41bf3-316">For each DEP that contains mailboxes that you want to delete, run the [Set-DataEncryptionPolicy](/powershell/module/exchange/set-dataencryptionpolicy) cmdlet as follows.</span></span>

    ```powershell
    Set-DataEncryptionPolicy <Policy ID> -PermanentDataPurgeRequested -PermanentDataPurgeReason <Reason> -PermanentDataPurgeContact <ContactName>
    ```

   <span data-ttu-id="41bf3-317">Wenn der Befehl fehlschlägt, stellen Sie sicher, dass Sie die Exchange Online aus beiden Schlüsseln in Azure Key Vault entfernt haben, wie weiter oben in dieser Aufgabe angegeben.</span><span class="sxs-lookup"><span data-stu-id="41bf3-317">If the command fails, ensure that you've removed the Exchange Online permissions from both keys in Azure Key Vault as specified earlier in this task.</span></span><span data-ttu-id="41bf3-318">Nachdem Sie den Switch PermanentDataPurgeRequested mit dem cmdlet Set-DataEncryptionPolicy festgelegt haben, können Sie diese DEP nicht mehr Postfächern zuweisen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-318"> Once you've set the PermanentDataPurgeRequested switch using the Set-DataEncryptionPolicy cmdlet, you'll no longer be able to assign this DEP to mailboxes.</span></span>

4. <span data-ttu-id="41bf3-319">Wenden Sie sich an den Microsoft-Support, und fordern Sie das Data Purge eDocument an.</span><span class="sxs-lookup"><span data-stu-id="41bf3-319">Contact Microsoft support and request the Data Purge eDocument.</span></span>

    <span data-ttu-id="41bf3-320">Auf Ihre Anfrage sendet Microsoft Ihnen ein rechtliches Dokument, um die Löschung von Daten zu bestätigen und zu autorisieren.</span><span class="sxs-lookup"><span data-stu-id="41bf3-320">At your request, Microsoft sends you a legal document to acknowledge and authorize data deletion.</span></span> <span data-ttu-id="41bf3-321">Die Person in Ihrer Organisation, die sich während des Onboardings als genehmigende Person im FastTrack-Angebot angemeldet hat, muss dieses Dokument signieren.</span><span class="sxs-lookup"><span data-stu-id="41bf3-321">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="41bf3-322">Normalerweise handelt es sich dabei um eine Führungskraft oder eine andere benannte Person in Ihrem Unternehmen, die berechtigt ist, den Papierkram im Namen Ihrer Organisation zu signieren.</span><span class="sxs-lookup"><span data-stu-id="41bf3-322">Normally, this is an executive or other designated person in your company who is legally authorized to sign the paperwork on behalf of your organization.</span></span>

5. <span data-ttu-id="41bf3-323">Nachdem Ihr Vertreter das rechtliche Dokument signiert hat, geben Sie es an Microsoft zurück (in der Regel über eine eDoc-Signatur).</span><span class="sxs-lookup"><span data-stu-id="41bf3-323">Once your representative has signed the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

    <span data-ttu-id="41bf3-324">Sobald Microsoft das rechtliche Dokument erhält, führt Microsoft Cmdlets aus, um die Datenbereinigung auszulösen, die zuerst die Richtlinie löscht, die Postfächer für das dauerhafte Löschen markiert und dann den Verfügbarkeitsschlüssel löscht.</span><span class="sxs-lookup"><span data-stu-id="41bf3-324">Once Microsoft receives the legal document, Microsoft runs cmdlets to trigger the data purge which first deletes the policy, marks the mailboxes for permanent deletion, then deletes the availability key.</span></span> <span data-ttu-id="41bf3-325">Sobald der Datenbereinigungsprozess abgeschlossen ist, wurden die Daten gelöscht, der Exchange Online nicht mehr möglich und kann nicht wiederhergestellt werden.</span><span class="sxs-lookup"><span data-stu-id="41bf3-325">Once the data purge process completes, the data has been purged, is inaccessible to Exchange Online, and is not recoverable.</span></span>

### <a name="revoke-your-customer-keys-and-the-availability-key-for-sharepoint-online-onedrive-for-business-and-teams-files"></a><span data-ttu-id="41bf3-326">Widerrufen Ihrer Kundenschlüssel und des Verfügbarkeitsschlüssels für SharePoint Online-, OneDrive for Business- und Teams Dateien</span><span class="sxs-lookup"><span data-stu-id="41bf3-326">Revoke your Customer Keys and the availability key for SharePoint Online, OneDrive for Business, and Teams files</span></span>

<span data-ttu-id="41bf3-327">Führen Sie die folgenden Schritte aus, um den Datenbereinigungspfad für SharePoint Online-, OneDrive for Business- und Teams zu initiieren:</span><span class="sxs-lookup"><span data-stu-id="41bf3-327">To initiate the data purge path for SharePoint Online, OneDrive for Business, and Teams files, complete these steps:</span></span>

1. <span data-ttu-id="41bf3-328">Widerrufen des Azure Key Vault-Zugriffs.</span><span class="sxs-lookup"><span data-stu-id="41bf3-328">Revoke Azure Key Vault access.</span></span> <span data-ttu-id="41bf3-329">Alle Schlüsseltresoradministratoren müssen zustimmen, den Zugriff zu widerrufen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-329">All key vault admins must agree to revoke access.</span></span>

   <span data-ttu-id="41bf3-330">Sie löschen den Azure Key Vault für SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="41bf3-330">You do not delete the Azure Key Vault for SharePoint Online.</span></span> <span data-ttu-id="41bf3-331">Schlüsseltresor können von mehreren SharePoint Und DEPs gemeinsam genutzt werden.</span><span class="sxs-lookup"><span data-stu-id="41bf3-331">Key vaults may be shared among several SharePoint Online tenants and DEPs.</span></span>

2. <span data-ttu-id="41bf3-332">Wenden Sie sich an Microsoft, um den Verfügbarkeitsschlüssel zu löschen.</span><span class="sxs-lookup"><span data-stu-id="41bf3-332">Contact Microsoft to delete the availability key.</span></span>

    <span data-ttu-id="41bf3-333">Wenn Sie microsoft kontaktieren, um den Verfügbarkeitsschlüssel zu löschen, senden wir Ihnen ein rechtliches Dokument.</span><span class="sxs-lookup"><span data-stu-id="41bf3-333">When you contact Microsoft to delete the availability key, we'll send you a legal document.</span></span> <span data-ttu-id="41bf3-334">Die Person in Ihrer Organisation, die sich während des Onboardings als genehmigende Person im FastTrack-Angebot angemeldet hat, muss dieses Dokument signieren.</span><span class="sxs-lookup"><span data-stu-id="41bf3-334">The person in your organization who signed up as an approver in the FastTrack offer during onboarding needs to sign this document.</span></span> <span data-ttu-id="41bf3-335">Normalerweise handelt es sich dabei um eine Führungskraft oder eine andere benannte Person in Ihrem Unternehmen, die gesetzlich autorisiert ist, den Papierkram im Namen Ihrer Organisation zu signieren.</span><span class="sxs-lookup"><span data-stu-id="41bf3-335">Normally, this is an executive or other designated person in your company who's legally authorized to sign the paperwork on behalf of your organization.</span></span>

3. <span data-ttu-id="41bf3-336">Sobald Ihr Vertreter das rechtliche Dokument signiert hat, geben Sie es an Microsoft zurück (in der Regel über eine eDoc-Signatur).</span><span class="sxs-lookup"><span data-stu-id="41bf3-336">Once your representative signs the legal document, return it to Microsoft (usually through an eDoc signature).</span></span>

   <span data-ttu-id="41bf3-337">Sobald Microsoft das rechtliche Dokument erhält, führen wir Cmdlets aus, um die Datenbereinigung auszulösen, die die Kryptografielöschung des Mandantenschlüssels, des Websiteschlüssels und aller einzelnen Schlüssel pro Dokument durchführt, wodurch die Schlüsselhierarchie unwiderruflich gebrochen wird.</span><span class="sxs-lookup"><span data-stu-id="41bf3-337">Once Microsoft receives the legal document, we run cmdlets to trigger the data purge which performs crypto deletion of the tenant key, site key, and all individual per-document keys, irrevocably breaking the key hierarchy.</span></span> <span data-ttu-id="41bf3-338">Nachdem die Datenbereinigungs-Cmdlets abgeschlossen sind, wurden Ihre Daten gelöscht.</span><span class="sxs-lookup"><span data-stu-id="41bf3-338">Once the data purge cmdlets complete, your data has been purged.</span></span>

## <a name="related-articles"></a><span data-ttu-id="41bf3-339">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="41bf3-339">Related articles</span></span>

- [<span data-ttu-id="41bf3-340">Dienstverschlüsselung mit Kundenschlüssel</span><span class="sxs-lookup"><span data-stu-id="41bf3-340">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="41bf3-341">Informationen zum Verfügbarkeitsschlüssel</span><span class="sxs-lookup"><span data-stu-id="41bf3-341">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="41bf3-342">Einrichten des Kundenschlüssels</span><span class="sxs-lookup"><span data-stu-id="41bf3-342">Set up Customer Key</span></span>](customer-key-set-up.md)

- [<span data-ttu-id="41bf3-343">Rollen oder Drehen eines Kundenschlüssels oder eines Verfügbarkeitsschlüssels</span><span class="sxs-lookup"><span data-stu-id="41bf3-343">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="41bf3-344">Customer Lockbox</span><span class="sxs-lookup"><span data-stu-id="41bf3-344">Customer Lockbox</span></span>](customer-lockbox-requests.md)

- [<span data-ttu-id="41bf3-345">Dienstverschlüsselung</span><span class="sxs-lookup"><span data-stu-id="41bf3-345">Service Encryption</span></span>](office-365-service-encryption.md)