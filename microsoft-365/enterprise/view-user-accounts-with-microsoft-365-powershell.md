---
title: Anzeigen Microsoft 365 Benutzerkonten mit PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- PowerShell
- Ent_Office_Other
- seo-marvel-apr2020
ms.assetid: bb12f49d-a85d-4f3b-ada2-5c4e33977b10
description: Erfahren Sie, wie Sie Ihre Microsoft 365 Benutzerkonten mit PowerShell auf unterschiedliche Weise anzeigen, auflisten oder anzeigen.
ms.openlocfilehash: 77219fb89430ed257ef2a68a7b24bf9ebac715b2
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53290171"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="598ed-103">Anzeigen Microsoft 365 Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="598ed-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="598ed-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="598ed-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="598ed-105">Sie können die Microsoft 365 Admin Center verwenden, um die Konten für Ihren Microsoft 365 Mandanten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="598ed-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="598ed-106">PowerShell für Microsoft 365 ermöglicht dies, bietet aber auch zusätzliche Funktionen.</span><span class="sxs-lookup"><span data-stu-id="598ed-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="598ed-107">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="598ed-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="598ed-108">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365 Mandanten](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)her.</span><span class="sxs-lookup"><span data-stu-id="598ed-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="598ed-109">Alle Konten anzeigen</span><span class="sxs-lookup"><span data-stu-id="598ed-109">View all accounts</span></span>

<span data-ttu-id="598ed-110">Führen Sie den folgenden Befehl aus, um die vollständige Liste der Benutzerkonten anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="598ed-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="598ed-111">Sie sollten Informationen wie die folgende erhalten:</span><span class="sxs-lookup"><span data-stu-id="598ed-111">You should get information similar to this:</span></span>
  
```powershell
ObjectId                             DisplayName                                           UserPrincipalName
--------                             -----------                                           -----------------
032fc1fc-b5a2-46f1-8635-3d7dcb52c48d Adele Vance                                           AdeleV@litwareinc.OnMicr...
bd1e6af1-41e7-4f77-a2ac-5b209950135c Global Administrator                                  admin@litwareinc.onmicro...
ec37a4d6-232e-4eb7-82a5-1613490642a5 Alex Wilber                                           AlexW@litwareinc.OnMicro...
be4bdddd-c790-424c-9f96-a0cf609b7815 Allan Deyoung                                         AllanD@litwareinc.OnMicr...
598ab87b-76f0-4bf9-9538-bd46b10f4438 Christie Cline                                        ChristieC@litwareinc.OnM...
40722671-e520-4a5f-97d4-0bc9e9b2dc0f Debra Berger                                          DebraB@litwareinc.OnMicr...
```

### <a name="view-a-specific-account"></a><span data-ttu-id="598ed-112">Anzeigen eines bestimmten Kontos</span><span class="sxs-lookup"><span data-stu-id="598ed-112">View a specific account</span></span>

<span data-ttu-id="598ed-113">Führen Sie den folgenden Befehl aus, um ein bestimmtes Benutzerkonto anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="598ed-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="598ed-114">Geben Sie den Anmeldekontonamen des Benutzerkontos ein, das auch als Benutzerprinzipalname (USER Principal Name, UPN) bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="598ed-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="598ed-115">Entfernen Sie die Zeichen "<" und ">".</span><span class="sxs-lookup"><span data-stu-id="598ed-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="598ed-116">Hier ist ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="598ed-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="598ed-117">Anzeigen zusätzlicher Eigenschaftswerte für ein bestimmtes Konto</span><span class="sxs-lookup"><span data-stu-id="598ed-117">View additional property values for a specific account</span></span>

<span data-ttu-id="598ed-118">Standardmäßig zeigt das Cmdlet **"Get-AzureADUser"** nur die Eigenschaften *ObjectID,* *DisplayName* und *UserPrincipalName* von Konten an.</span><span class="sxs-lookup"><span data-stu-id="598ed-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="598ed-119">Um die anzuzeigenden Eigenschaften selektiver zu gestalten, verwenden Sie das Cmdlet **"Select"** in Kombination mit dem Cmdlet **"Get-AzureADUser".**</span><span class="sxs-lookup"><span data-stu-id="598ed-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="598ed-120">Um die beiden Cmdlets zu kombinieren, verwenden Sie das "pipe"-Zeichen ("|"), das Azure Active Directory PowerShell anweist, Graph die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="598ed-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="598ed-121">Hier ist ein Beispielbefehl, der *displayName*, *Department* und *UsageLocation* für jedes Benutzerkonto anzeigt:</span><span class="sxs-lookup"><span data-stu-id="598ed-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="598ed-122">Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="598ed-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="598ed-123">Rufen Sie alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="598ed-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="598ed-124">Zeigt nur den Benutzernamen, die Abteilung und den Verwendungsort an (**Wählen Sie DisplayName, Abteilung, UsageLocation** aus).</span><span class="sxs-lookup"><span data-stu-id="598ed-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="598ed-125">Um alle Eigenschaften für ein bestimmtes Benutzerkonto anzuzeigen, verwenden Sie das Cmdlet **"Select"** und das Platzhalterzeichen (\*).</span><span class="sxs-lookup"><span data-stu-id="598ed-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="598ed-126">Hier ist ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="598ed-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="598ed-127">Führen Sie als weiteres Beispiel den folgenden Befehl aus, um den Aktiviertstatus eines bestimmten Benutzerkontos zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="598ed-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="598ed-128">Anzeigen des Kontosynchronisierungsstatus</span><span class="sxs-lookup"><span data-stu-id="598ed-128">View account synchronization status</span></span>

<span data-ttu-id="598ed-129">Benutzerkonten haben zwei Quellen:</span><span class="sxs-lookup"><span data-stu-id="598ed-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="598ed-130">Windows Server Active Directory (AD), bei denen es sich um Konten handelt, die von lokalem AD mit der Cloud synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="598ed-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="598ed-131">Azure Active Directory (Azure AD)-AD-Konten, die direkt in der Cloud erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="598ed-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="598ed-132">Der folgende Befehl weist PowerShell an, alle Benutzer abzurufen, deren Attribut *DirSyncEnabled* auf *"True"* festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="598ed-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="598ed-133">Sie können es verwenden, um Konten zu suchen, die von lokalem AD synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="598ed-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="598ed-134">Der folgende Befehl weist PowerShell an, alle Benutzer abzurufen, deren Attribut *DirSyncEnabled* auf False festgelegt *ist.*</span><span class="sxs-lookup"><span data-stu-id="598ed-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="598ed-135">Sie können es verwenden, um nur cloudbasierte Konten zu finden.</span><span class="sxs-lookup"><span data-stu-id="598ed-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="598ed-136">Anzeigen von Konten basierend auf einer allgemeinen Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="598ed-136">View accounts based on a common property</span></span>

<span data-ttu-id="598ed-137">Um die Liste der anzuzeigenden Konten selektiver zu gestalten, können Sie das Cmdlet **"Where"** in Kombination mit dem Cmdlet **"Get-AzureADUser"** verwenden.</span><span class="sxs-lookup"><span data-stu-id="598ed-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="598ed-138">Um die beiden Cmdlets zu kombinieren, verwenden Sie das "pipe"-Zeichen ("|"), das Azure Active Directory PowerShell anweist, Graph die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="598ed-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="598ed-139">Hier ist ein Beispielbefehl, der nur die Benutzerkonten anzeigt, die über einen nicht angegebenen Verwendungsort verfügen:</span><span class="sxs-lookup"><span data-stu-id="598ed-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="598ed-140">Mit diesem Befehl wird Azure Active Directory PowerShell angewiesen, folgende Graph auszuführen:</span><span class="sxs-lookup"><span data-stu-id="598ed-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="598ed-141">Rufen Sie alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="598ed-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="598ed-142">Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungsort (**Wobei {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="598ed-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="598ed-143">Innerhalb der geschweiften Klammern weist der Befehl PowerShell an, nur den Satz von Konten zu suchen, für die die UsageLocation-Benutzerkontoeigenschaft (**$ \_ . UsageLocation**) ist nicht angegeben (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="598ed-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="598ed-144">Die **UsageLocation**-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="598ed-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="598ed-145">Um alle Eigenschaften für ein bestimmtes Benutzerkonto anzuzeigen, verwenden Sie das Cmdlet **"Select"** und das Platzhalterzeichen (\*).</span><span class="sxs-lookup"><span data-stu-id="598ed-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="598ed-146">Hier ist ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="598ed-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="598ed-147">Das **City**-Objekt steht z. B. für den Namen einer Benutzerkontoeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="598ed-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="598ed-148">Mit dem folgenden Befehl können Sie alle Konten von Benutzern auflisten, die in London leben:</span><span class="sxs-lookup"><span data-stu-id="598ed-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
> <span data-ttu-id="598ed-149">Die Syntax für das Cmdlet **"Where"** in diesen Beispielen lautet **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="598ed-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="598ed-150">[Name der Benutzerkontoeigenschaft] [Vergleichsoperator] [Wert] **}**.> [Vergleichsoperator] ist **-eq** für gleich, **-ne** für ungleich, **-lt** für kleiner als, **-gt** für größer als und andere.</span><span class="sxs-lookup"><span data-stu-id="598ed-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="598ed-151">[Wert] ist in der Regel eine Zeichenfolge (eine Abfolge von Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder **$Null** für nicht angegebene Zeichen.</span><span class="sxs-lookup"><span data-stu-id="598ed-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="598ed-152">Weitere Informationen finden Sie unter [Where](/powershell/module/microsoft.powershell.core/where-object).</span><span class="sxs-lookup"><span data-stu-id="598ed-152">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="598ed-153">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="598ed-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="598ed-154">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365 Mandanten](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)her.</span><span class="sxs-lookup"><span data-stu-id="598ed-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="598ed-155">Alle Konten anzeigen</span><span class="sxs-lookup"><span data-stu-id="598ed-155">View all accounts</span></span>

<span data-ttu-id="598ed-156">Führen Sie den folgenden Befehl aus, um die vollständige Liste der Benutzerkonten anzuzeigen:</span><span class="sxs-lookup"><span data-stu-id="598ed-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="598ed-157">Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="598ed-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="598ed-158">Führen Sie diese Cmdlets über Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="598ed-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="598ed-159">Sie sollten Informationen wie die folgende erhalten:</span><span class="sxs-lookup"><span data-stu-id="598ed-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="598ed-160">Das **Get-MsolUser**-Cmdlet verfügt darüber hinaus über eine Reihe von Parametern zum Filtern der angezeigten Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="598ed-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="598ed-161">Führen Sie z. B. für die Liste der nicht lizenzierten Benutzer (Benutzer, die Microsoft 365 hinzugefügt wurden, aber noch nicht lizenziert wurden, um einen der Dienste zu verwenden) den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="598ed-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="598ed-162">Sie sollten Informationen wie die folgende erhalten:</span><span class="sxs-lookup"><span data-stu-id="598ed-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="598ed-163">Weitere Informationen zu zusätzlichen Parametern zum Filtern der angezeigten Benutzerkonten finden Sie unter [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="598ed-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="598ed-164">Anzeigen eines bestimmten Kontos</span><span class="sxs-lookup"><span data-stu-id="598ed-164">View a specific account</span></span>

<span data-ttu-id="598ed-165">Führen Sie den folgenden Befehl aus, um ein bestimmtes Benutzerkonto anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="598ed-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="598ed-166">Geben Sie den Anmeldenamen des Benutzerkontos ein, das auch als Benutzerprinzipalname (USER Principal Name, UPN) bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="598ed-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="598ed-167">Entfernen Sie die Zeichen "<" und ">".</span><span class="sxs-lookup"><span data-stu-id="598ed-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="598ed-168">Anzeigen von Konten basierend auf einer allgemeinen Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="598ed-168">View accounts based on a common property</span></span>

<span data-ttu-id="598ed-169">Um die Liste der anzuzeigenden Konten selektiver zu gestalten, können Sie das Cmdlet **"Where"** in Kombination mit dem Cmdlet **"Get-MsolUser"** verwenden.</span><span class="sxs-lookup"><span data-stu-id="598ed-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="598ed-170">Um die beiden Cmdlets zu kombinieren, verwenden Sie das "pipe"-Zeichen ("|"), das PowerShell anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="598ed-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="598ed-171">Hier ist ein Beispiel, in dem nur die Benutzerkonten mit einem nicht angegebenen Verwendungsort angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="598ed-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="598ed-172">Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="598ed-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="598ed-173">Rufen Sie alle Informationen zu den Benutzerkonten (**Get-MsolUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="598ed-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="598ed-174">Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungsort (**Wobei {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="598ed-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="598ed-175">Innerhalb der geschweiften Klammern weist der Befehl PowerShell an, nur den Satz von Konten zu suchen, für die die UsageLocation-Benutzerkontoeigenschaft (**$ \_ . UsageLocation**) ist nicht angegeben (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="598ed-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="598ed-176">Sie sollten Informationen wie die folgende erhalten:</span><span class="sxs-lookup"><span data-stu-id="598ed-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="598ed-177">Die *UsageLocation*-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="598ed-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="598ed-178">Um alle Eigenschaften für Benutzerkonten anzuzeigen, verwenden Sie das Cmdlet **"Select"** und das Platzhalterzeichen (\*), um sie für ein bestimmtes Benutzerkonto anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="598ed-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="598ed-179">Hier ist ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="598ed-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="598ed-180">Das *City*-Objekt steht z. B. für den Namen einer Benutzerkontoeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="598ed-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="598ed-181">Mit dem folgenden Befehl können Sie alle Benutzerkonten für Benutzer auflisten, die in London leben:</span><span class="sxs-lookup"><span data-stu-id="598ed-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
> <span data-ttu-id="598ed-182">Die Syntax für das Cmdlet **"Where"** in diesen Beispielen lautet **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="598ed-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="598ed-183">[Name der Benutzerkontoeigenschaft] [Vergleichsoperator] [Wert] **}**.</span><span class="sxs-lookup"><span data-stu-id="598ed-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="598ed-184">[Vergleichsoperator] ist **-eq** für gleich, **-ne** für ungleich, **-lt** für kleiner als, **-gt** für größer als und andere.</span><span class="sxs-lookup"><span data-stu-id="598ed-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="598ed-185">[Wert] ist in der Regel eine Zeichenfolge (eine Abfolge von Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder **$Null** für nicht angegebene Zeichen.</span><span class="sxs-lookup"><span data-stu-id="598ed-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="598ed-186">Weitere Informationen finden Sie unter [Where](/powershell/module/microsoft.powershell.core/where-object).</span><span class="sxs-lookup"><span data-stu-id="598ed-186">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object).</span></span>
  
<span data-ttu-id="598ed-187">Verwenden Sie den folgenden Befehl, um den Sperrstatus eines Benutzerkontos zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="598ed-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="598ed-188">Anzeigen zusätzlicher Eigenschaftswerte für Konten</span><span class="sxs-lookup"><span data-stu-id="598ed-188">View additional property values for accounts</span></span>

<span data-ttu-id="598ed-189">Standardmäßig zeigt das Cmdlet **"Get-MsolUser"** die folgenden drei Eigenschaften von Benutzerkonten an:</span><span class="sxs-lookup"><span data-stu-id="598ed-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="598ed-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="598ed-190">UserPrincipalName</span></span>

- <span data-ttu-id="598ed-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="598ed-191">DisplayName</span></span>

- <span data-ttu-id="598ed-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="598ed-192">isLicensed</span></span>

<span data-ttu-id="598ed-193">Wenn Sie zusätzliche Eigenschaften benötigen, z. B. die Abteilung, in der der Benutzer arbeitet, und das Land/die Region, in dem/der er Microsoft 365 Dienste verwendet, können Sie **Get-MsolUser** in Kombination mit **dem** Select-Cmdlet ausführen, um die Liste der Benutzerkontoeigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="598ed-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="598ed-194">Hier ist ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="598ed-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="598ed-195">Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="598ed-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="598ed-196">Rufen Sie alle Informationen zu den Benutzerkonten (**Get-MsolUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="598ed-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="598ed-197">Zeigt nur den Benutzernamen, die Abteilung und den Verwendungsort an (**Wählen Sie DisplayName, Abteilung, UsageLocation** aus).</span><span class="sxs-lookup"><span data-stu-id="598ed-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="598ed-198">Sie sollten Informationen wie die folgende erhalten:</span><span class="sxs-lookup"><span data-stu-id="598ed-198">You should get information similar to this:</span></span>
  
```powershell
DisplayName             Department                       UsageLocation
-----------             ----------                       -------------
Bonnie Kearney          Sales & Marketing                    US
Fabrice Canel           Legal                                US
Brian Johnson
Anne Wallace            Executive Management                 US
Alex Darrow             Sales & Marketing                    US
Scott Wallace           Operations
```

<span data-ttu-id="598ed-199">Mit dem Cmdlet **"Auswählen"** können Sie auswählen, welche Eigenschaften angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="598ed-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="598ed-200">Um alle Eigenschaften für ein bestimmtes Benutzerkonto anzuzeigen, verwenden Sie das Platzhalterzeichen (\*).</span><span class="sxs-lookup"><span data-stu-id="598ed-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="598ed-201">Hier ist ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="598ed-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="598ed-202">Um die Liste der anzuzeigenden Konten selektiver zu gestalten, können Sie auch das Cmdlet **"Where"** verwenden.</span><span class="sxs-lookup"><span data-stu-id="598ed-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="598ed-203">Hier ist ein Beispielbefehl, der nur die Benutzerkonten anzeigt, die über einen nicht angegebenen Verwendungsort verfügen:</span><span class="sxs-lookup"><span data-stu-id="598ed-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="598ed-204">Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:</span><span class="sxs-lookup"><span data-stu-id="598ed-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="598ed-205">Rufen Sie alle Informationen zu den Benutzerkonten (**Get-MsolUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="598ed-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="598ed-206">Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungsort (**Wobei {$ \_ . UsageLocation -eq $Null}**), und senden Sie die resultierenden Informationen an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="598ed-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="598ed-207">Innerhalb der geschweiften Klammern weist der Befehl PowerShell an, nur den Satz von Konten zu suchen, für die die UsageLocation-Benutzerkontoeigenschaft (**$ \_ . UsageLocation**) ist nicht angegeben (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="598ed-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="598ed-208">Zeigt nur den Benutzernamen, die Abteilung und den Verwendungsort an (**Wählen Sie DisplayName, Abteilung, UsageLocation** aus).</span><span class="sxs-lookup"><span data-stu-id="598ed-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="598ed-209">Sie sollten Informationen wie die folgende erhalten:</span><span class="sxs-lookup"><span data-stu-id="598ed-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="598ed-210">Wenn Sie die Verzeichnissynchronisierung verwenden, um Ihre Microsoft 365 Benutzer zu erstellen und zu verwalten, können Sie das lokale Konto anzeigen, aus dem ein Microsoft 365 Benutzer projiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="598ed-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="598ed-211">Im folgenden Beispiel wird davon ausgegangen, dass:</span><span class="sxs-lookup"><span data-stu-id="598ed-211">The following example assumes that:</span></span>

- <span data-ttu-id="598ed-212">Azure AD Verbinden ist so konfiguriert, dass der Standardquellanker von ObjectGUID verwendet wird.</span><span class="sxs-lookup"><span data-stu-id="598ed-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="598ed-213">(Weitere Informationen zum Konfigurieren eines Quellankers finden Sie unter [Azure AD Verbinden: Designkonzepte).](/azure/active-directory/hybrid/plan-connect-design-concepts)</span><span class="sxs-lookup"><span data-stu-id="598ed-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="598ed-214">Das Active Directory Domain Services-Modul für PowerShell wurde installiert (siehe [RSAT-Tools).](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)</span><span class="sxs-lookup"><span data-stu-id="598ed-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="598ed-215">Weitere Informationen:</span><span class="sxs-lookup"><span data-stu-id="598ed-215">See also</span></span>

[<span data-ttu-id="598ed-216">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="598ed-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="598ed-217">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="598ed-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="598ed-218">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="598ed-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)