---
title: Anzeigen von Microsoft 365-Benutzerkonten mit PowerShell
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
description: Erfahren Sie, wie Sie Ihre Microsoft 365-Benutzerkonten mit PowerShell auf unterschiedliche Weise anzeigen, auflisten oder anzeigen.
ms.openlocfilehash: de91195afeb8480bf231d9536e4b3a94502a6da1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50924648"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="7075d-103">Anzeigen von Microsoft 365-Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="7075d-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="7075d-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="7075d-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="7075d-105">Sie können das Microsoft 365 Admin Center zum Anzeigen der Konten für Ihren Microsoft 365-Mandanten verwenden.</span><span class="sxs-lookup"><span data-stu-id="7075d-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="7075d-106">PowerShell für Microsoft 365 ermöglicht dies, bietet aber auch zusätzliche Funktionen.</span><span class="sxs-lookup"><span data-stu-id="7075d-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="7075d-107">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="7075d-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="7075d-108">Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="7075d-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="7075d-109">Anzeigen aller Konten</span><span class="sxs-lookup"><span data-stu-id="7075d-109">View all accounts</span></span>

<span data-ttu-id="7075d-110">Führen Sie den folgenden Befehl aus, um die vollständige Liste der Benutzerkonten anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="7075d-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="7075d-111">Informationen wie diese sollten sie erhalten:</span><span class="sxs-lookup"><span data-stu-id="7075d-111">You should get information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="7075d-112">Anzeigen eines bestimmten Kontos</span><span class="sxs-lookup"><span data-stu-id="7075d-112">View a specific account</span></span>

<span data-ttu-id="7075d-113">Führen Sie zum Anzeigen eines bestimmten Benutzerkontos den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="7075d-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="7075d-114">Geben Sie den Anmeldekontonamen des Benutzerkontos ein, das auch als Benutzerprinzipalname (User Principal Name, UPN) bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="7075d-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="7075d-115">Entfernen Sie die Zeichen "<" und ">".</span><span class="sxs-lookup"><span data-stu-id="7075d-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="7075d-116">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7075d-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="7075d-117">Anzeigen zusätzlicher Eigenschaftswerte für ein bestimmtes Konto</span><span class="sxs-lookup"><span data-stu-id="7075d-117">View additional property values for a specific account</span></span>

<span data-ttu-id="7075d-118">Standardmäßig zeigt das **Cmdlet Get-AzureADUser** nur die *Eigenschaften ObjectID,* *DisplayName* und *UserPrincipalName* von Konten an.</span><span class="sxs-lookup"><span data-stu-id="7075d-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="7075d-119">Verwenden Sie das **Cmdlet Select** in Kombination mit dem **Cmdlet Get-AzureADUser,** um selektiver über die zu zeigenden Eigenschaften zu sein.</span><span class="sxs-lookup"><span data-stu-id="7075d-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="7075d-120">Verwenden Sie zum Kombinieren der beiden Cmdlets das "Pipe"-Zeichen ("|"), das Azure Active Directory PowerShell für Graph anfordert, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="7075d-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="7075d-121">Hier ist ein Beispielbefehl, der *displayName*, *Department* und *UsageLocation* für jedes Benutzerkonto anzeigt:</span><span class="sxs-lookup"><span data-stu-id="7075d-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="7075d-122">Dieser Befehl wies PowerShell an:</span><span class="sxs-lookup"><span data-stu-id="7075d-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="7075d-123">Alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) erhalten und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="7075d-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="7075d-124">Zeigt nur den Benutzernamen, die Abteilung und den Verwendungsspeicherort an (**Select DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="7075d-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="7075d-125">Um alle Eigenschaften für ein bestimmtes Benutzerkonto zu sehen, verwenden Sie das **Cmdlet Select** und das Platzhalterzeichen (\*).</span><span class="sxs-lookup"><span data-stu-id="7075d-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="7075d-126">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7075d-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="7075d-127">Führen Sie als weiteres Beispiel den folgenden Befehl aus, um den aktivierten Status eines bestimmten Benutzerkontos zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="7075d-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="7075d-128">Anzeigen des Kontosynchronisierungsstatus</span><span class="sxs-lookup"><span data-stu-id="7075d-128">View account synchronization status</span></span>

<span data-ttu-id="7075d-129">Benutzerkonten verfügen über zwei Quellen:</span><span class="sxs-lookup"><span data-stu-id="7075d-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="7075d-130">Windows Server Active Directory (AD), bei denen es sich um Konten handelt, die von lokalem AD mit der Cloud synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7075d-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="7075d-131">Azure Active Directory (Azure AD) AD-Konten, die direkt in der Cloud erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="7075d-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="7075d-132">Mit dem folgenden Befehl wird PowerShell angewiesen, alle Benutzer zu erhalten, für die das Attribut *DirSyncEnabled* auf *True festgelegt ist.*</span><span class="sxs-lookup"><span data-stu-id="7075d-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="7075d-133">Sie können es verwenden, um Konten zu finden, die von lokalen AD synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="7075d-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="7075d-134">Mit dem folgenden Befehl wird PowerShell angewiesen, alle Benutzer zu erhalten, für die das Attribut *DirSyncEnabled* auf *False festgelegt ist.*</span><span class="sxs-lookup"><span data-stu-id="7075d-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="7075d-135">Sie können es verwenden, um nur cloudbasierte Konten zu finden.</span><span class="sxs-lookup"><span data-stu-id="7075d-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="7075d-136">Anzeigen von Konten basierend auf einer allgemeinen Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7075d-136">View accounts based on a common property</span></span>

<span data-ttu-id="7075d-137">Um die Liste der angezeigten Konten selektiver zu machen, können Sie das **Cmdlet Where** in Kombination mit dem Cmdlet **Get-AzureADUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="7075d-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="7075d-138">Verwenden Sie zum Kombinieren der beiden Cmdlets das "Pipe"-Zeichen ("|"), das Azure Active Directory PowerShell für Graph anfordert, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="7075d-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="7075d-139">Hier ist ein Beispielbefehl, der nur die Benutzerkonten mit einem nicht angegebenen Verwendungsspeicherort anzeigt:</span><span class="sxs-lookup"><span data-stu-id="7075d-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="7075d-140">Dieser Befehl wies Azure Active Directory PowerShell für Graph an:</span><span class="sxs-lookup"><span data-stu-id="7075d-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="7075d-141">Alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) erhalten und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="7075d-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="7075d-142">Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungsspeicherort (**Where {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="7075d-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="7075d-143">Innerhalb der geschweiften Klammern wird PowerShell vom Befehl angewiesen, nur den Satz von Konten zu finden, für die die UsageLocation-Benutzerkontoeigenschaft **( . $ \_ UsageLocation**) ist nicht angegeben (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="7075d-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="7075d-144">Die **UsageLocation**-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7075d-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="7075d-145">Verwenden Sie zum Anzeigen aller Eigenschaften für ein bestimmtes Benutzerkonto das **Cmdlet Select** und das Platzhalterzeichen (\*).</span><span class="sxs-lookup"><span data-stu-id="7075d-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="7075d-146">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7075d-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="7075d-147">Das **City**-Objekt steht z. B. für den Namen einer Benutzerkontoeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7075d-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="7075d-148">Mit dem folgenden Befehl können Sie alle Konten von Benutzern auflisten, die in London leben:</span><span class="sxs-lookup"><span data-stu-id="7075d-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="7075d-149">Die Syntax  für das Where-Cmdlet in diesen Beispielen lautet **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="7075d-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="7075d-150">[Name der Benutzerkontoeigenschaft] [Vergleichsoperator] [value] **}**.> [Vergleichsoperator] ist **-eq** für equals, **-ne** für nicht gleich, **-lt** für kleiner als, **-gt** für größer als und andere.</span><span class="sxs-lookup"><span data-stu-id="7075d-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="7075d-151">[value] ist in der Regel eine Zeichenfolge (eine Abfolge von  Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder $Null nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="7075d-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="7075d-152">Weitere Informationen finden Sie unter [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="7075d-152">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="7075d-153">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="7075d-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="7075d-154">Stellen Sie [zunächst eine Verbindung mit Ihrem Microsoft 365-Mandanten herzustellen.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="7075d-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="7075d-155">Anzeigen aller Konten</span><span class="sxs-lookup"><span data-stu-id="7075d-155">View all accounts</span></span>

<span data-ttu-id="7075d-156">Führen Sie den folgenden Befehl aus, um die vollständige Liste der Benutzerkonten anzeigen zu können:</span><span class="sxs-lookup"><span data-stu-id="7075d-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="7075d-157">Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell Core nicht unterstützt.</span><span class="sxs-lookup"><span data-stu-id="7075d-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="7075d-158">Führen Sie diese Cmdlets über Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="7075d-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="7075d-159">Informationen wie diese sollten sie erhalten:</span><span class="sxs-lookup"><span data-stu-id="7075d-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="7075d-160">Das **Get-MsolUser**-Cmdlet verfügt darüber hinaus über eine Reihe von Parametern zum Filtern der angezeigten Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="7075d-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="7075d-161">Führen Sie beispielsweise für die Liste der nicht lizenzierten Benutzer (Benutzer, die Microsoft 365 hinzugefügt wurden, aber noch keine Lizenz für die Verwendung der Dienste haben) den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="7075d-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="7075d-162">Informationen wie diese sollten sie erhalten:</span><span class="sxs-lookup"><span data-stu-id="7075d-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="7075d-163">Weitere Informationen zu zusätzlichen Parametern zum Filtern der angezeigten Benutzerkonten finden Sie unter [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="7075d-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="7075d-164">Anzeigen eines bestimmten Kontos</span><span class="sxs-lookup"><span data-stu-id="7075d-164">View a specific account</span></span>

<span data-ttu-id="7075d-165">Führen Sie zum Anzeigen eines bestimmten Benutzerkontos den folgenden Befehl aus.</span><span class="sxs-lookup"><span data-stu-id="7075d-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="7075d-166">Geben Sie den Anmeldenamen des Benutzerkontos ein, das auch als Benutzerprinzipalname (User Principal Name, UPN) bekannt ist.</span><span class="sxs-lookup"><span data-stu-id="7075d-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="7075d-167">Entfernen Sie die Zeichen "<" und ">".</span><span class="sxs-lookup"><span data-stu-id="7075d-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="7075d-168">Anzeigen von Konten basierend auf einer allgemeinen Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="7075d-168">View accounts based on a common property</span></span>

<span data-ttu-id="7075d-169">Um die Liste der angezeigten Konten selektiver zu machen, können Sie das **Cmdlet Where** in Kombination mit dem Cmdlet **Get-MsolUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="7075d-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="7075d-170">Verwenden Sie zum Kombinieren der beiden Cmdlets das Zeichen "pipe" ("|"), das PowerShell anfordert, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="7075d-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="7075d-171">Im Folgenden finden Sie ein Beispiel, in dem nur die Benutzerkonten mit einem nicht angegebenen Verwendungsspeicherort angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="7075d-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="7075d-172">Dieser Befehl wies PowerShell an:</span><span class="sxs-lookup"><span data-stu-id="7075d-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="7075d-173">Alle Informationen zu den Benutzerkonten (**Get-MsolUser**) erhalten und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="7075d-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="7075d-174">Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungsspeicherort (**Where {$ \_ . UsageLocation -eq $Null}**).</span><span class="sxs-lookup"><span data-stu-id="7075d-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="7075d-175">Innerhalb der geschweiften Klammern wird PowerShell vom Befehl angewiesen, nur den Satz von Konten zu finden, für die die UsageLocation-Benutzerkontoeigenschaft (**$ \_ . UsageLocation**) ist nicht angegeben (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="7075d-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="7075d-176">Informationen wie diese sollten sie erhalten:</span><span class="sxs-lookup"><span data-stu-id="7075d-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="7075d-177">Die *UsageLocation*-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="7075d-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="7075d-178">Um alle Eigenschaften für Benutzerkonten zu sehen, verwenden Sie das **Cmdlet Select** und das Platzhalterzeichen (\*) zum Anzeigen aller Eigenschaften für ein bestimmtes Benutzerkonto.</span><span class="sxs-lookup"><span data-stu-id="7075d-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="7075d-179">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7075d-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="7075d-180">Das *City*-Objekt steht z. B. für den Namen einer Benutzerkontoeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="7075d-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="7075d-181">Mit dem folgenden Befehl können Sie alle Benutzerkonten für Benutzer in London auflisten:</span><span class="sxs-lookup"><span data-stu-id="7075d-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="7075d-182">Die Syntax  für das Where-Cmdlet in diesen Beispielen lautet **Where {$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="7075d-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="7075d-183">[Name der Benutzerkontoeigenschaft] [Vergleichsoperator] [value] **}**.</span><span class="sxs-lookup"><span data-stu-id="7075d-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="7075d-184">[Vergleichsoperator] ist **-eq** für gleich, **-ne** für nicht gleich, **-lt** für kleiner als, **-gt** für größer als und andere.</span><span class="sxs-lookup"><span data-stu-id="7075d-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="7075d-185">[value] ist in der Regel eine Zeichenfolge (eine Abfolge von  Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder $Null nicht angegeben.</span><span class="sxs-lookup"><span data-stu-id="7075d-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="7075d-186">Weitere Informationen finden Sie unter [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="7075d-186">For more information, see [Where](/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="7075d-187">Verwenden Sie den folgenden Befehl, um den blockierten Status eines Benutzerkontos zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="7075d-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="7075d-188">Anzeigen zusätzlicher Eigenschaftswerte für Konten</span><span class="sxs-lookup"><span data-stu-id="7075d-188">View additional property values for accounts</span></span>

<span data-ttu-id="7075d-189">Standardmäßig zeigt das **Cmdlet Get-MsolUser** die folgenden drei Eigenschaften von Benutzerkonten an:</span><span class="sxs-lookup"><span data-stu-id="7075d-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="7075d-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="7075d-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="7075d-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="7075d-191">DisplayName</span></span>
    
- <span data-ttu-id="7075d-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="7075d-192">isLicensed</span></span>
    
<span data-ttu-id="7075d-193">Wenn Sie zusätzliche Eigenschaften benötigen, z. B. die Abteilung, in der der Benutzer arbeitet, und das Land/die Region, in dem er Microsoft 365-Dienste verwendet, können Sie **Get-MsolUser** in Kombination mit dem **Cmdlet Select** ausführen, um die Liste der Benutzerkontoeigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="7075d-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="7075d-194">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7075d-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="7075d-195">Dieser Befehl wies PowerShell an:</span><span class="sxs-lookup"><span data-stu-id="7075d-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="7075d-196">Alle Informationen zu den Benutzerkonten (**Get-MsolUser**) erhalten und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="7075d-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="7075d-197">Zeigt nur den Benutzernamen, die Abteilung und den Verwendungsspeicherort an (**Select DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="7075d-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="7075d-198">Informationen wie diese sollten sie erhalten:</span><span class="sxs-lookup"><span data-stu-id="7075d-198">You should get information similar to this:</span></span>
  
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

<span data-ttu-id="7075d-199">Mit **dem Cmdlet** Select können Sie auswählen, welche Eigenschaften angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="7075d-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="7075d-200">Verwenden Sie zum Anzeigen aller Eigenschaften für ein bestimmtes Benutzerkonto das Platzhalterzeichen (\*).</span><span class="sxs-lookup"><span data-stu-id="7075d-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="7075d-201">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="7075d-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="7075d-202">Um die Liste der angezeigten Konten selektiver zu machen, können Sie auch das **Cmdlet Where** verwenden.</span><span class="sxs-lookup"><span data-stu-id="7075d-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="7075d-203">Hier ist ein Beispielbefehl, der nur die Benutzerkonten mit einem nicht angegebenen Verwendungsspeicherort anzeigt:</span><span class="sxs-lookup"><span data-stu-id="7075d-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="7075d-204">Dieser Befehl wies PowerShell an:</span><span class="sxs-lookup"><span data-stu-id="7075d-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="7075d-205">Alle Informationen zu den Benutzerkonten (**Get-MsolUser**) erhalten und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="7075d-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="7075d-206">Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungsspeicherort (**Where {$ \_ . UsageLocation -eq $Null}**), und senden Sie die resultierenden Informationen an den nächsten Befehl ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="7075d-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="7075d-207">Innerhalb der geschweiften Klammern wird PowerShell vom Befehl angewiesen, nur den Satz von Konten zu finden, für die die UsageLocation-Benutzerkontoeigenschaft **( . $ \_ UsageLocation**) ist nicht angegeben (**-eq $Null**).</span><span class="sxs-lookup"><span data-stu-id="7075d-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="7075d-208">Zeigt nur den Benutzernamen, die Abteilung und den Verwendungsspeicherort an (**Select DisplayName, Department, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="7075d-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="7075d-209">Informationen wie diese sollten sie erhalten:</span><span class="sxs-lookup"><span data-stu-id="7075d-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="7075d-210">Wenn Sie die Verzeichnissynchronisierung zum Erstellen und Verwalten Ihrer Microsoft 365-Benutzer verwenden, können Sie das lokale Konto anzeigen, von dem ein Microsoft 365-Benutzer projiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="7075d-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="7075d-211">Im folgenden Beispiel wird davon ausgegangen:</span><span class="sxs-lookup"><span data-stu-id="7075d-211">The following example assumes that:</span></span>

- <span data-ttu-id="7075d-212">Azure AD Connect ist für die Verwendung des Standardmäßigen Quellankers von ObjectGUID konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="7075d-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="7075d-213">(Weitere Informationen zum Konfigurieren eines Quellankers finden Sie unter [Azure AD Connect: Design concepts](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span><span class="sxs-lookup"><span data-stu-id="7075d-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="7075d-214">Das Active Directory Domain Services-Modul für PowerShell wurde installiert (siehe [RSAT-Tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span><span class="sxs-lookup"><span data-stu-id="7075d-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="7075d-215">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="7075d-215">See also</span></span>

[<span data-ttu-id="7075d-216">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="7075d-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7075d-217">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="7075d-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="7075d-218">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="7075d-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)