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
description: Hier erfahren Sie, was Sie tun müssen, wenn Sie vor der Synchronisierung mit Microsoft 365 eine nicht-routale-Domäne mit Ihren lokalen Benutzern verbunden haben.
ms.openlocfilehash: 835beffb77c495179991fbb4388ecd9ee804ec91
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695916"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a><span data-ttu-id="0a797-103">Vorbereiten einer nicht routingfähigen Domäne für die Verzeichnissynchronisierung</span><span class="sxs-lookup"><span data-stu-id="0a797-103">Prepare a non-routable domain for directory synchronization</span></span>
<span data-ttu-id="0a797-104">Wenn Sie Ihr lokales Verzeichnis mit Microsoft 365 synchronisieren, müssen Sie über eine verifizierte Domäne in Azure Active Directory (Azure AD) verfügen.</span><span class="sxs-lookup"><span data-stu-id="0a797-104">When you synchronize your on-premises directory with Microsoft 365 you have to have a verified domain in Azure Active Directory (Azure AD).</span></span> <span data-ttu-id="0a797-105">Nur die Benutzerprinzipalnamen (User Principal Names, UPN), die der lokalen Domäne zugeordnet sind, werden synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="0a797-105">Only the User Principal Names (UPN) that are associated with the on-premises domain are synchronized.</span></span> <span data-ttu-id="0a797-106">Allerdings wird jeder UPN, der eine nicht Routingfähige Domäne enthält, beispielsweise. local (wie Billa@contoso. local), mit einer. onmicrosoft.com-Domäne (wie Billa@contoso.onmicrosoft.com) synchronisiert.</span><span class="sxs-lookup"><span data-stu-id="0a797-106">However, any UPN that contains an non-routable domain, for example .local (like billa@contoso.local), will be synchronized to an .onmicrosoft.com domain (like billa@contoso.onmicrosoft.com).</span></span> 

<span data-ttu-id="0a797-107">Wenn Sie derzeit eine. local-Domäne für ihre Benutzerkonten in Active Directory-Domänendienste (AD DS) verwenden, sollten Sie diese so ändern, dass Sie eine verifizierte Domäne (wie Billa@contoso.com) verwenden, um ordnungsgemäß mit Ihrer Microsoft 365-Domäne zu synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="0a797-107">If you currently use a .local domain for your user accounts in Active Directory Domain Services (AD DS) it's recommended that you change them to use a verified domain (like billa@contoso.com) in order to properly sync with your Microsoft 365 domain.</span></span>
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a><span data-ttu-id="0a797-108">Was geschieht, wenn ich nur eine lokale lokale Domäne habe?</span><span class="sxs-lookup"><span data-stu-id="0a797-108">What if I only have a .local on-premises domain?</span></span>

<span data-ttu-id="0a797-109">Das neueste Tool, mit dem Sie Ihre AD DS mit Azure AD synchronisieren können, heißt Azure AD Connect.</span><span class="sxs-lookup"><span data-stu-id="0a797-109">The most recent tool you can use for synchronizing your AD DS to Azure AD is named Azure AD Connect.</span></span> <span data-ttu-id="0a797-110">Weitere Informationen finden Sie unter [integrieren Ihrer lokalen Identitäten in Azure AD](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).</span><span class="sxs-lookup"><span data-stu-id="0a797-110">For more information, see [Integrating your on-premises identities with Azure AD](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad).</span></span>
  
<span data-ttu-id="0a797-111">Azure AD Connect synchronisiert den UPN und das Kennwort Ihrer Benutzer, sodass sich Benutzer mit denselben Anmeldeinformationen anmelden können, die Sie lokal verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a797-111">Azure AD Connect synchronizes your users' UPN and password so that users can sign in with the same credentials they use on-premises.</span></span> <span data-ttu-id="0a797-112">Allerdings synchronisiert Azure AD Connect nur Benutzer mit Domänen, die von Microsoft 365 überprüft wurden.</span><span class="sxs-lookup"><span data-stu-id="0a797-112">However, Azure AD Connect only synchronizes users to domains that are verified by Microsoft 365.</span></span> <span data-ttu-id="0a797-113">Dies bedeutet, dass die Domäne auch von Azure AD überprüft wird, da Microsoft 365-Identitäten von Azure AD verwaltet werden.</span><span class="sxs-lookup"><span data-stu-id="0a797-113">This means that the domain also is verified by Azure AD because Microsoft 365 identities are managed by Azure AD.</span></span> <span data-ttu-id="0a797-114">Die Domäne muss also eine gültige Internet Domäne sein (beispielsweise. com,. org, .net,. US usw.).</span><span class="sxs-lookup"><span data-stu-id="0a797-114">In other words, the domain has to be a valid Internet domain (for example, .com, .org, .net, .us, etc.).</span></span> <span data-ttu-id="0a797-115">Wenn Ihr interner AD DS nur eine nicht Routingfähige Domäne verwendet (beispielsweise. local), kann dies nicht möglicherweise mit der überprüften Domäne übereinstimmen, die Sie auf Microsoft 365 haben.</span><span class="sxs-lookup"><span data-stu-id="0a797-115">If your internal AD DS only uses a non-routable domain (for example, .local), this can't possibly match the verified domain you have on Microsoft 365.</span></span> <span data-ttu-id="0a797-116">Sie können dieses Problem beheben, indem Sie entweder Ihre primäre Domäne in Ihrem lokalen AD DS ändern oder ein oder mehrere UPN-Suffixe hinzufügen.</span><span class="sxs-lookup"><span data-stu-id="0a797-116">You can fix this issue by either changing your primary domain in your on premises AD DS, or by adding one or more UPN suffixes.</span></span>
  
### <a name="change-your-primary-domain"></a><span data-ttu-id="0a797-117">**Ändern der primären Domäne**</span><span class="sxs-lookup"><span data-stu-id="0a797-117">**Change your primary domain**</span></span>

<span data-ttu-id="0a797-118">Ändern Sie Ihre primäre Domäne in eine Domäne, die Sie in Microsoft 365 überprüft haben, beispielsweise contoso.com.</span><span class="sxs-lookup"><span data-stu-id="0a797-118">Change your primary domain to a domain you have verified in Microsoft 365, for example, contoso.com.</span></span> <span data-ttu-id="0a797-119">Jeder Benutzer mit der Domäne "contoso. local" wird dann auf contoso.com aktualisiert.</span><span class="sxs-lookup"><span data-stu-id="0a797-119">Every user that has the domain contoso.local is then updated to contoso.com.</span></span> <span data-ttu-id="0a797-120">Anweisungen hierzu finden Sie unter [Funktionsweise der Domänenumbenennung](https://go.microsoft.com/fwlink/p/?LinkId=624174).</span><span class="sxs-lookup"><span data-stu-id="0a797-120">For instructions, see [How Domain Rename Works](https://go.microsoft.com/fwlink/p/?LinkId=624174).</span></span> <span data-ttu-id="0a797-121">Dies ist jedoch ein sehr beteiligter Prozess, und eine einfachere Lösung wird im folgenden Abschnitt beschrieben.</span><span class="sxs-lookup"><span data-stu-id="0a797-121">This is a very involved process, however, and an easier solution is described in the following section.</span></span>
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a><span data-ttu-id="0a797-122">**Hinzufügen von UPN-Suffixen und Aktualisieren der Benutzer**</span><span class="sxs-lookup"><span data-stu-id="0a797-122">**Add UPN suffixes and update your users to them**</span></span>

<span data-ttu-id="0a797-123">Sie können das. local-Problem lösen, indem Sie neue UPN-Suffixe oder-Suffixe in AD DS zur Übereinstimmung mit der Domäne (oder den Domänen) registrieren, die Sie in Microsoft 365 überprüft haben.</span><span class="sxs-lookup"><span data-stu-id="0a797-123">You can solve the .local problem by registering new UPN suffix or suffixes in AD DS to match the domain (or domains) you verified in Microsoft 365.</span></span> <span data-ttu-id="0a797-124">Nachdem Sie das neue Suffix registriert haben, aktualisieren Sie den Benutzer UPNs so, dass die. local durch den neuen Domänennamen ersetzt wird, sodass ein Benutzerkonto wie Billa@contoso.com aussieht.</span><span class="sxs-lookup"><span data-stu-id="0a797-124">After you register the new suffix, you update the user UPNs to replace the .local with the new domain name for example so that a user account looks like billa@contoso.com.</span></span>
  
<span data-ttu-id="0a797-125">Nachdem Sie die UPNs für die Verwendung der überprüften Domäne aktualisiert haben, können Sie Ihre lokale AD DS mit Microsoft 365 synchronisieren.</span><span class="sxs-lookup"><span data-stu-id="0a797-125">After you have updated the UPNs to use the verified domain, you are ready to synchronize your on-premises AD DS with Microsoft 365.</span></span>
  
 <span data-ttu-id="0a797-126">**Schritt 1: Hinzufügen des neuen UPN-Suffix**</span><span class="sxs-lookup"><span data-stu-id="0a797-126">**Step 1: Add the new UPN suffix**</span></span>
  
1. <span data-ttu-id="0a797-127">Wählen Sie auf dem AD DS Domänencontroller im Server-Manager **Tools** \> **Active Directory Domänen und Vertrauensstellungen**aus.</span><span class="sxs-lookup"><span data-stu-id="0a797-127">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.</span></span>
    
    <span data-ttu-id="0a797-128">**Oder, wenn Sie nicht über Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="0a797-128">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="0a797-129">Drücken Sie die **Windows-Taste + R** , um das Dialogfeld **Ausführen** zu öffnen, und geben Sie dann in Domain. msc ein, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="0a797-129">Press **Windows key + R** to open the **Run** dialog, and then type in Domain.msc, and then choose **OK**.</span></span>
    
    ![Wählen Sie Active Directory Domänen und Vertrauensstellungen aus.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. <span data-ttu-id="0a797-131">Klicken Sie im Fenster **Active Directory Domänen und Vertrauensstellungen** mit der rechten Maustaste auf **Active Directory Domänen und Vertrauensstellungen**, und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="0a797-131">On the **Active Directory Domains and Trusts** window, right-click **Active Directory Domains and Trusts**, and then choose **Properties**.</span></span>
    
    ![Klicken Sie mit der rechten Maustaste auf Active Directory Domänen und Vertrauensstellungen, und wählen Sie Eigenschaften](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. <span data-ttu-id="0a797-133">Geben Sie auf der Registerkarte **UPN-Suffixe** im Feld **alternative UPN-Suffixe** ihre neuen UPN-Suffixe oder Suffixe ein, und wählen Sie dann **Add** \> **Apply**aus.</span><span class="sxs-lookup"><span data-stu-id="0a797-133">On the **UPN Suffixes** tab, in the **Alternative UPN Suffixes** box, type your new UPN suffix or suffixes, and then choose **Add** \> **Apply**.</span></span>
    
    ![Hinzufügen eines neuen UPN-Suffix](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    <span data-ttu-id="0a797-135">Klicken Sie auf **OK** , wenn Sie das Hinzufügen von Suffixen abgeschlossen haben.</span><span class="sxs-lookup"><span data-stu-id="0a797-135">Choose **OK** when you're done adding suffixes.</span></span> 
    
 <span data-ttu-id="0a797-136">**Schritt 2: Ändern des UPN-Suffixes für vorhandene Benutzer**</span><span class="sxs-lookup"><span data-stu-id="0a797-136">**Step 2: Change the UPN suffix for existing users**</span></span>
  
1. <span data-ttu-id="0a797-137">Wählen Sie auf dem AD DS Domänencontroller im Server-Manager die Option **Extras** \> **Active Directory Benutzer und Computer**aus.</span><span class="sxs-lookup"><span data-stu-id="0a797-137">On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Users and Computers**.</span></span>
    
    <span data-ttu-id="0a797-138">**Oder, wenn Sie nicht über Windows Server 2012**</span><span class="sxs-lookup"><span data-stu-id="0a797-138">**Or, if you don't have Windows Server 2012**</span></span>
    
    <span data-ttu-id="0a797-139">Drücken Sie die **Windows-Taste + R** , um das Dialogfeld **Ausführen** zu öffnen, und geben Sie dann DSA. msc ein, und klicken Sie dann auf **OK** .</span><span class="sxs-lookup"><span data-stu-id="0a797-139">Press **Windows key + R** to open the **Run** dialog, and then type in Dsa.msc, and then click **OK**</span></span>
    
2. <span data-ttu-id="0a797-140">Wählen Sie einen Benutzer aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **Eigenschaften**aus.</span><span class="sxs-lookup"><span data-stu-id="0a797-140">Select a user, right-click, and then choose **Properties**.</span></span>
    
3. <span data-ttu-id="0a797-141">Wählen Sie auf der Registerkarte **Konto** in der Dropdownliste UPN-Suffix das neue UPN-Suffix aus, und wählen Sie dann **OK**aus.</span><span class="sxs-lookup"><span data-stu-id="0a797-141">On the **Account** tab, in the UPN suffix drop-down list, choose the new UPN suffix, and then choose **OK**.</span></span>
    
    ![Hinzufügen eines neuen UPN-Suffixes für einen Benutzer](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. <span data-ttu-id="0a797-143">Führen Sie diese Schritte für jeden Benutzer aus.</span><span class="sxs-lookup"><span data-stu-id="0a797-143">Complete these steps for every user.</span></span>
    
   
### <a name="you-can-also-use-windows-powershell-to-change-the-upn-suffix-for-all-users"></a><span data-ttu-id="0a797-144">**Sie können auch Windows PowerShell verwenden, um das UPN-Suffix für alle Benutzer zu ändern.**</span><span class="sxs-lookup"><span data-stu-id="0a797-144">**You can also use Windows PowerShell to change the UPN suffix for all users**</span></span>

<span data-ttu-id="0a797-145">Wenn Sie viele Benutzer aktualisieren müssen, ist es einfacher, Windows PowerShell zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="0a797-145">If you have a lot of users to update, it is easier to use Windows PowerShell.</span></span> <span data-ttu-id="0a797-146">Im folgenden Beispiel werden die Cmdlets [Get-User](https://go.microsoft.com/fwlink/p/?LinkId=624312) und [festgelegt-User](https://go.microsoft.com/fwlink/p/?LinkId=624313) verwendet, um alle contoso. local-Suffixe in contoso.com zu ändern.</span><span class="sxs-lookup"><span data-stu-id="0a797-146">The following example uses the cmdlets [Get-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624312) and [Set-ADUser](https://go.microsoft.com/fwlink/p/?LinkId=624313) to change all contoso.local suffixes to contoso.com.</span></span> 

<span data-ttu-id="0a797-147">Beispiel für Feinde können Sie die folgenden Windows PowerShell Befehle ausführen, um alle contoso. local-Suffixe auf contoso.com zu aktualisieren:</span><span class="sxs-lookup"><span data-stu-id="0a797-147">Foe example, you could run the following Windows PowerShell commands to update all contoso.local suffixes to contoso.com:</span></span>
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

<span data-ttu-id="0a797-148">Weitere Informationen zum Verwenden von Windows PowerShell in AD DS finden Sie unter [Active Directory Windows PowerShell Moduls](https://go.microsoft.com/fwlink/p/?LinkId=624314) .</span><span class="sxs-lookup"><span data-stu-id="0a797-148">See [Active Directory Windows PowerShell module](https://go.microsoft.com/fwlink/p/?LinkId=624314) to learn more about using Windows PowerShell in AD DS.</span></span> 

