---
title: Vorbereiten einer nicht routingfähigen Domäne für die Verzeichnissynchronisierung
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365E_SetupDirSyncLocalDir
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: e7968303-c234-46c4-b8b0-b5c93c6d57a7
description: Erfahren Sie, wie Sie vor der Synchronisierung mit Ihrem Microsoft 365-Mandanten eine nicht routingfähige Domäne ihren lokalen Benutzerkonten zugeordnet haben.
ms.openlocfilehash: e4d0e020c5792c610d501c33e8f3d5131b7a1ff0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927396"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="0166c-103">Vorbereiten einer nicht routingfähigen Domäne für die Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="0166c-103">Prepare a non-routable domain for directory synchronization</span></span>

<span data-ttu-id="0166c-104">Wenn Sie Ihr lokales Verzeichnis mit Microsoft 365 synchronisieren, müssen Sie über eine überprüfte Domäne in Azure Active Directory (Azure AD) verfügen.</span><span class="sxs-lookup"><span data-stu-id="0166c-104">When you synchronize your on-premises directory with Microsoft 365, you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="0166c-105">Es werden nur die Benutzerprinzipalnamen (User Principal Names, UPNs) synchronisiert, die der lokalen Active Directory Domain Services (AD DS)-Domäne zugeordnet sind.</span><span class="sxs-lookup"><span data-stu-id="0166c-105">Only the User Principal Names (UPNs) that are associated with the on-premises Active Directory Domain Services (AD DS) domain are synchronized.</span></span> <span data-ttu-id="0166c-106">Jeder UPN, der eine nicht routingfähige Domäne enthält, z. B. ".local" (Beispiel: billa@contoso.local), wird jedoch mit einer .onmicrosoft.com-Domäne synchronisiert (Beispiel: billa@contoso.onmicrosoft.com).</span><span class="sxs-lookup"><span data-stu-id="0166c-106">However, any UPN that contains a non-routable domain, such as ".local" (example: billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (example: billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="0166c-107">Wenn Sie derzeit eine ".local"-Domäne für Ihre Benutzerkonten in AD DS verwenden, wird empfohlen, sie so zu ändern, dass sie eine überprüfte Domäne wie billa@contoso.com verwenden, um eine ordnungsgemäß mit Ihrer Microsoft 365-Domäne zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="0166c-107">If you currently use a ".local" domain for your user accounts in AD DS, it's recommended that you change them to use a verified domain, such as billa@contoso.com, in order to properly synchronize with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="0166c-108">Was passiert, wenn ich nur eine lokale Domäne habe?</span><span class="sxs-lookup"><span data-stu-id="0166c-108">What if I only have a ".local" on-premises domain?</span></span>

<span data-ttu-id="0166c-109">Sie verwenden Azure AD Connect zum Synchronisieren Ihres AD DS mit dem Azure AD-Mandanten Ihres Microsoft 365-Mandanten.</span><span class="sxs-lookup"><span data-stu-id="0166c-109">You use Azure AD Connect for synchronizing your AD DS to the Azure AD tenant of your Microsoft 365 tenant.</span></span> <span data-ttu-id="0166c-110">Weitere Informationen finden Sie unter [Integrieren Ihrer lokalen Identitäten in Azure AD](/azure/architecture/reference-architectures/identity/azure-ad).</span><span class="sxs-lookup"><span data-stu-id="0166c-110">For more information, see [Integrating your on-premises identities with Azure AD](/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="0166c-111">Azure AD Connect synchronisiert den UPN und das Kennwort Ihrer Benutzer, sodass sich Benutzer mit denselben Anmeldeinformationen anmelden können, die sie lokal verwenden.</span><span class="sxs-lookup"><span data-stu-id="0166c-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="0166c-112">Azure AD Connect synchronisiert jedoch nur Benutzer mit Domänen, die von Microsoft 365 überprüft werden.</span><span class="sxs-lookup"><span data-stu-id="0166c-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="0166c-113">Dies bedeutet, dass die Domäne auch von Azure AD überprüft wird, da Microsoft 365-Identitäten von Azure AD verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="0166c-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="0166c-114">Anders ausgedrückt: Die Domäne muss eine gültige Internetdomäne sein (z. B. .com, .org, .net, .us).</span><span class="sxs-lookup"><span data-stu-id="0166c-114">In other words, the domain has to be a valid Internet domain (such as, .com, .org, .net, .us).</span></span> <span data-ttu-id="0166c-115">Wenn Ihr interner AD DS nur eine nicht routingfähige Domäne verwendet (z. B. ".local"), kann dies nicht mit der überprüften Domäne übereinstimmen, die Sie für Ihren Microsoft 365-Mandanten haben.</span><span class="sxs-lookup"><span data-stu-id="0166c-115">If your internal AD DS only uses a non-routable domain (for example, ".local"), this can't possibly match the verified domain you have for your Microsoft 365 tenant.</span></span> <span data-ttu-id="0166c-116">Sie können dieses Problem beheben, indem Sie entweder Ihre primäre Domäne in Ihrem lokalen AD DS ändern oder ein oder mehrere UPN-Suffixe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0166c-116">You can fix this issue by either changing your primary domain in your on-premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="0166c-117">Ändern Der primären Domäne</span><span class="sxs-lookup"><span data-stu-id="0166c-117">Change your primary domain</span></span>

<span data-ttu-id="0166c-118">Ändern Sie Ihre primäre Domäne in eine Domäne, die Sie in Microsoft 365 überprüft haben, z. B. contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0166c-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="0166c-119">Jeder Benutzer mit der Domäne "contoso.local" wird dann auf contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0166c-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="0166c-120">Dies ist jedoch ein sehr beteiligter Prozess, und eine einfachere Lösung wird im folgenden Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0166c-120">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="0166c-121">Hinzufügen von UPN-Suffixen und Aktualisieren ihrer Benutzer</span><span class="sxs-lookup"><span data-stu-id="0166c-121">Add UPN suffixes and update your users to them</span></span>

<span data-ttu-id="0166c-122">Sie können das Problem ".local" lösen, indem Sie neue UPN-Suffixe oder -Suffixe in AD DS registrieren, um der Domäne (oder Domänen), die Sie in Microsoft 365 überprüft haben, zu entsprechen.</span><span class="sxs-lookup"><span data-stu-id="0166c-122">You can solve the ".local" problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="0166c-123">Nachdem Sie das neue Suffix registriert haben, aktualisieren Sie die Benutzer-UPNs, um beispielsweise die ".local" durch den neuen Domänennamen zu ersetzen, sodass ein Benutzerkonto wie ein billa@contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0166c-123">After you register the new suffix, you update the user UPNs to replace the ".local" with the new domain name, for example, so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="0166c-124">Nachdem Sie die UPNs so aktualisiert haben, dass sie die überprüfte Domäne verwenden, können Sie Ihren lokalen AD DS mit Microsoft 365 synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="0166c-124">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
#### <a name="step-1-add-the-new-upn-suffix"></a><span data-ttu-id="0166c-125">Schritt 1: Hinzufügen des neuen UPN-Suffixes\*\*</span><span class="sxs-lookup"><span data-stu-id="0166c-125">Step 1: Add the new UPN suffix\*\*</span></span>
  
1. <span data-ttu-id="0166c-126">Wählen Sie auf dem AD DS-Domänencontroller im Server-Manager  \> **Extras Active Directory-Domänen und Vertrauensstellungen aus.**</span><span class="sxs-lookup"><span data-stu-id="0166c-126">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="0166c-127">**Oder, wenn Sie nicht über Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="0166c-127">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="0166c-128">Drücken **Sie die Windows-TASTE + R,** um das **Dialogfeld Ausführen** zu öffnen, und geben Sie dann Domain.msc ein, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="0166c-128">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![Wählen Sie Active Directory-Domänen und Vertrauensstellungen aus.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="0166c-130">Klicken Sie **im Fenster Active Directory-Domänen** und Vertrauensstellungen mit der rechten Maustaste auf **Active Directory-Domänen** und Vertrauensstellungen, und wählen Sie dann **Eigenschaften aus.**</span><span class="sxs-lookup"><span data-stu-id="0166c-130">In the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![Klicken Sie mit der rechten Maustaste auf Active Directory-Domänen und -Vertrauensstellungen, und wählen Sie Eigenschaften aus.](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="0166c-132">Geben Sie auf der Registerkarte **UPN-Suffixe** im Feld **Alternative UPN-Suffixe** Ihr neues UPN-Suffix oder -Suffix ein, und wählen Sie **dann Anwenden** hinzufügen \> **aus.**</span><span class="sxs-lookup"><span data-stu-id="0166c-132">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![Hinzufügen eines neuen UPN-Suffixes](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="0166c-134">Wählen **Sie OK** aus, wenn Sie mit dem Hinzufügen von Suffixen fertig sind.</span><span class="sxs-lookup"><span data-stu-id="0166c-134">Choose **OK** when you're done adding suffixes.</span></span> 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a><span data-ttu-id="0166c-135">Schritt 2: Ändern des UPN-Suffixes für vorhandene Benutzer</span><span class="sxs-lookup"><span data-stu-id="0166c-135">Step 2: Change the UPN suffix for existing users</span></span>
  
1. <span data-ttu-id="0166c-136">Wählen Sie auf dem AD DS-Domänencontroller im Server-Manager **Extras** \> **Active Directory-Benutzer und -Computer aus.**</span><span class="sxs-lookup"><span data-stu-id="0166c-136">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="0166c-137">**Oder, wenn Sie nicht über Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="0166c-137">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="0166c-138">Drücken **Sie die Windows-TASTE + R,** um das Dialogfeld **Ausführen** zu öffnen, und geben Sie dann Dsa.msc ein, und klicken Sie dann auf **OK.**</span><span class="sxs-lookup"><span data-stu-id="0166c-138">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="0166c-139">Wählen Sie einen Benutzer aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **Eigenschaften aus.**</span><span class="sxs-lookup"><span data-stu-id="0166c-139">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="0166c-140">Wählen Sie **auf** der Registerkarte Konto in der Dropdownliste UPN-Suffix das neue UPN-Suffix aus, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="0166c-140">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![Hinzufügen eines neuen UPN-Suffixs für einen Benutzer](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="0166c-142">Führen Sie diese Schritte für jeden Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="0166c-142">Complete these steps for every user.</span></span>
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a><span data-ttu-id="0166c-143">Verwenden von PowerShell zum Ändern des UPN-Suffixes für alle Benutzer</span><span class="sxs-lookup"><span data-stu-id="0166c-143">Use PowerShell to change the UPN suffix for all of your users</span></span>

<span data-ttu-id="0166c-144">Wenn Sie viele Benutzerkonten aktualisieren müssen, ist die Verwendung von PowerShell einfacher.</span><span class="sxs-lookup"><span data-stu-id="0166c-144">If you have a lot of user accounts to update, it's easier to use PowerShell.</span></span> <span data-ttu-id="0166c-145">Im folgenden Beispiel werden die Cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) und [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) verwendet, um alle contoso.local-Suffixe in contoso.com AD DS zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0166c-145">The following example uses the cmdlets [Get-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617241(v=technet.10)) and [Set-ADUser](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617215(v=technet.10)) to change all contoso.local suffixes to contoso.com in AD DS.</span></span> 

<span data-ttu-id="0166c-146">Sie können beispielsweise die folgenden PowerShell-Befehle ausführen, um alle contoso.local-Suffixe auf contoso.com:</span><span class="sxs-lookup"><span data-stu-id="0166c-146">For example, you could run the following PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="0166c-147">Weitere Informationen zur Windows PowerShell in AD DS finden Sie unter Active [Directory Windows PowerShell](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) Module.</span><span class="sxs-lookup"><span data-stu-id="0166c-147">See [Active Directory Windows PowerShell module](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/ee617195(v=technet.10)) to learn more about using Windows PowerShell in AD DS.</span></span>