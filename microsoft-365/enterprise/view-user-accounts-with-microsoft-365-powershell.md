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
description: In diesem Artikel erfahren Sie, wie Sie Ihre Microsoft 365-Benutzerkonten mit PowerShell auf unterschiedliche Weise anzeigen, auflisten oder anzeigen können.
ms.openlocfilehash: 312e9fb983c4d1f4de8bc74586c88f1e669eb90a
ms.sourcegitcommit: 66b8fc1d8ba4f17487cd2004ac19cf2fff472f3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/24/2020
ms.locfileid: "48754072"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="8e086-103">Anzeigen von Microsoft 365-Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e086-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="8e086-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="8e086-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="8e086-105">Sie können das Microsoft 365 Admin Center verwenden, um die Konten für Ihren Microsoft 365-Mandanten anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e086-105">You can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant.</span></span> <span data-ttu-id="8e086-106">PowerShell für Microsoft 365 ermöglicht dies, bietet aber auch zusätzliche Funktionen.</span><span class="sxs-lookup"><span data-stu-id="8e086-106">PowerShell for Microsoft 365 enables this but also provides additional functionality.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="8e086-107">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="8e086-107">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="8e086-108">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="8e086-108">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="8e086-109">Alle Konten anzeigen</span><span class="sxs-lookup"><span data-stu-id="8e086-109">View all accounts</span></span>

<span data-ttu-id="8e086-110">Um die vollständige Liste der Benutzerkonten anzuzeigen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8e086-110">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="8e086-111">Sie sollten ähnliche Informationen wie die folgenden erhalten:</span><span class="sxs-lookup"><span data-stu-id="8e086-111">You should get information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="8e086-112">Anzeigen eines bestimmten Kontos</span><span class="sxs-lookup"><span data-stu-id="8e086-112">View a specific account</span></span>

<span data-ttu-id="8e086-113">Führen Sie den folgenden Befehl aus, um ein bestimmtes Benutzerkonto anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e086-113">To display a specific user account, run the following command.</span></span> <span data-ttu-id="8e086-114">Geben Sie den Anmeldekontonamen des Benutzerkontos ein, das auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="8e086-114">Fill in the sign-in account name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="8e086-115">Entfernen Sie die Zeichen "<" und ">".</span><span class="sxs-lookup"><span data-stu-id="8e086-115">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="8e086-116">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e086-116">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="8e086-117">Anzeigen zusätzlicher Eigenschaftswerte für ein bestimmtes Konto</span><span class="sxs-lookup"><span data-stu-id="8e086-117">View additional property values for a specific account</span></span>

<span data-ttu-id="8e086-118">Standardmäßig zeigt das Cmdlet **Get-AzureADUser** nur die Eigenschaften *objectID*, *DisplayName*und *userPrincipalName* von Konten an.</span><span class="sxs-lookup"><span data-stu-id="8e086-118">By default, the **Get-AzureADUser** cmdlet only displays the *ObjectID*, *DisplayName*, and *UserPrincipalName* properties of accounts.</span></span>

<span data-ttu-id="8e086-119">Um die anzuzeigenden Eigenschaften selektiver zu machen, verwenden **Sie das SELECT** -Cmdlet in Kombination mit dem Cmdlet **Get-AzureADUser** .</span><span class="sxs-lookup"><span data-stu-id="8e086-119">To be more selective about the properties to display, use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="8e086-120">Um die beiden Cmdlets zu kombinieren, verwenden Sie das "Pipe"-Zeichen ("|"), das Azure Active Directory PowerShell für Graph anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="8e086-120">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="8e086-121">Im folgenden Beispiel wird der Befehl *DisplayName*, *Department*und *UsageLocation* für jedes Benutzerkonto angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8e086-121">Here's an example command that displays the *DisplayName*, *Department*, and *UsageLocation* for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="8e086-122">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="8e086-122">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="8e086-123">Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="8e086-123">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1.  <span data-ttu-id="8e086-124">Zeigt nur den Namen des Benutzerkontos, die Abteilung und den Verwendungs Speicherort an (**Wählen Sie DisplayName, Abteilung, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="8e086-124">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
  
<span data-ttu-id="8e086-125">Wenn Sie alle Eigenschaften für ein bestimmtes Benutzerkonto anzeigen möchten, verwenden **Sie das SELECT** -Cmdlet und das Platzhalterzeichen (\*).</span><span class="sxs-lookup"><span data-stu-id="8e086-125">To see all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="8e086-126">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e086-126">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="8e086-127">Führen Sie als weiteres Beispiel den folgenden Befehl aus, um den aktivierten Status eines bestimmten Benutzerkontos zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="8e086-127">As another example, run the following command to check the enabled status of a specific user account:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="8e086-128">Anzeigen des Status der Konto Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="8e086-128">View account synchronization status</span></span>

<span data-ttu-id="8e086-129">Benutzerkonten weisen zwei Quellen auf:</span><span class="sxs-lookup"><span data-stu-id="8e086-129">User accounts have two sources:</span></span> 

- <span data-ttu-id="8e086-130">Windows Server Active Directory (AD), bei denen es sich um Konten handelt, die vom lokalen AD zur Cloud synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="8e086-130">Windows Server Active Directory (AD), which are accounts that sync from on-premises AD to the cloud.</span></span>

- <span data-ttu-id="8e086-131">Azure Active Directory (Azure AD) Ad-Konten, die direkt in der Cloud erstellt werden.</span><span class="sxs-lookup"><span data-stu-id="8e086-131">Azure Active Directory (Azure AD) AD accounts, which are created directly in the cloud.</span></span>


<span data-ttu-id="8e086-132">Mit dem folgenden Befehl wird PowerShell angewiesen, alle Benutzer abzurufen, bei denen das Attribut *DirSyncEnabled* auf *true*festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8e086-132">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *True*.</span></span> <span data-ttu-id="8e086-133">Sie können es verwenden, um Konten zu finden, die von lokalen AD synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="8e086-133">You can use it to find accounts that are synchronizing from on-premise AD.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

<span data-ttu-id="8e086-134">Mit dem folgenden Befehl wird PowerShell angewiesen, alle Benutzer abzurufen, bei denen das Attribut *DirSyncEnabled* auf *false*festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="8e086-134">The following command instructs PowerShell to get all users who have the attribute *DirSyncEnabled* set to *False*.</span></span> <span data-ttu-id="8e086-135">Sie können damit nur Cloud-Konten suchen.</span><span class="sxs-lookup"><span data-stu-id="8e086-135">You can use it to find cloud-only accounts.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="8e086-136">Anzeigen von Konten basierend auf einer gemeinsamen Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8e086-136">View accounts based on a common property</span></span>

<span data-ttu-id="8e086-137">Um die Liste der anzuzeigenden Konten selektiver zu machen, können Sie das Cmdlet **Where** in Kombination mit dem Cmdlet **Get-AzureADUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e086-137">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="8e086-138">Um die beiden Cmdlets zu kombinieren, verwenden Sie das "Pipe"-Zeichen ("|"), das Azure Active Directory PowerShell für Graph anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="8e086-138">To combine the two cmdlets, use the "pipe" character ("|"), which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="8e086-139">Es folgt ein Beispielbefehl, in dem nur die Benutzerkonten angezeigt werden, die einen nicht angegebenen Verwendungs Speicherort aufweisen:</span><span class="sxs-lookup"><span data-stu-id="8e086-139">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="8e086-140">Dieser Befehl weist Azure Active Directory PowerShell für Graph Folgendes zu:</span><span class="sxs-lookup"><span data-stu-id="8e086-140">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
1. <span data-ttu-id="8e086-141">Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="8e086-141">Get all the information on the user accounts (**Get-AzureADUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="8e086-142">Suchen Sie nach allen Benutzerkonten mit einem nicht angegebenen Verwendungs Speicherort (**wobei {$ \_ . UsageLocation-EQ $NULL}**).</span><span class="sxs-lookup"><span data-stu-id="8e086-142">Find all the user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="8e086-143">In den geschweiften Klammern weist der Befehl PowerShell an, nur die Konten zu finden, für die die UsageLocation-Benutzerkonto Eigenschaft (\*\* $ \_ . UsageLocation**) ist nicht angegeben (**-EQ $NULL\*\*).</span><span class="sxs-lookup"><span data-stu-id="8e086-143">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="8e086-144">Die **UsageLocation**-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8e086-144">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="8e086-145">Um alle Eigenschaften für ein bestimmtes Benutzerkonto anzuzeigen, verwenden Sie das **Select** -Cmdlet und das Platzhalterzeichen (\*).</span><span class="sxs-lookup"><span data-stu-id="8e086-145">To display all the properties for a specific user account, use the **Select** cmdlet and the wildcard character (\*).</span></span> <span data-ttu-id="8e086-146">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e086-146">Here's an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="8e086-147">Das **City**-Objekt steht z. B. für den Namen einer Benutzerkontoeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8e086-147">For example, **City** is the name of a user account property.</span></span> <span data-ttu-id="8e086-148">Mit dem folgenden Befehl können Sie alle Konten von Benutzern auflisten, die in London Leben:</span><span class="sxs-lookup"><span data-stu-id="8e086-148">You can use the following command to list all accounts of users who live in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="8e086-149">Die Syntax für das Cmdlet **Where** in diesen Beispielen ist **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="8e086-149">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="8e086-150">[Name der Benutzerkonten Eigenschaft] [Vergleichsoperator] Wert **}**. > [Vergleichsoperator] ist **-EQ** für gleich, **-ne** für ungleich, **-lt** für kleiner als, **-gt** für größer als und andere.</span><span class="sxs-lookup"><span data-stu-id="8e086-150">[user account property name] [comparison operator] [value] **}**.> [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="8e086-151">[value] ist normalerweise eine Zeichenfolge (eine Sequenz von Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder **$null** für Unspecified.</span><span class="sxs-lookup"><span data-stu-id="8e086-151">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="8e086-152">Weitere Informationen finden Sie unter [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="8e086-152">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="8e086-153">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e086-153">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="8e086-154">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="8e086-154">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="8e086-155">Alle Konten anzeigen</span><span class="sxs-lookup"><span data-stu-id="8e086-155">View all accounts</span></span>

<span data-ttu-id="8e086-156">Um die vollständige Liste der Benutzerkonten anzuzeigen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8e086-156">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="8e086-157">PowerShell Core unterstützt das Microsoft Azure Active Directory Modul für Windows PowerShell Modul und Cmdlets mit *MSOL* nicht in Ihrem Namen.</span><span class="sxs-lookup"><span data-stu-id="8e086-157">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="8e086-158">Führen Sie diese Cmdlets aus Windows PowerShell aus.</span><span class="sxs-lookup"><span data-stu-id="8e086-158">Run these cmdlets from Windows PowerShell.</span></span>
>

<span data-ttu-id="8e086-159">Sie sollten ähnliche Informationen wie die folgenden erhalten:</span><span class="sxs-lookup"><span data-stu-id="8e086-159">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="8e086-160">Das **Get-MsolUser**-Cmdlet verfügt darüber hinaus über eine Reihe von Parametern zum Filtern der angezeigten Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="8e086-160">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="8e086-161">Führen Sie zum Beispiel für die Liste der nicht lizenzierten Benutzer (Benutzer, die Microsoft 365 hinzugefügt wurden, aber noch nicht für die Verwendung eines der Dienste lizenziert wurden) den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="8e086-161">For example, for the list of unlicensed users (users who have been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command:</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="8e086-162">Sie sollten ähnliche Informationen wie die folgenden erhalten:</span><span class="sxs-lookup"><span data-stu-id="8e086-162">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="8e086-163">Informationen zu zusätzlichen Parametern zum Filtern der Gruppe von Benutzerkonten, die angezeigt werden, finden Sie unter [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="8e086-163">For information about additional parameters to filter the set of user accounts that are displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="8e086-164">Anzeigen eines bestimmten Kontos</span><span class="sxs-lookup"><span data-stu-id="8e086-164">View a specific account</span></span>

<span data-ttu-id="8e086-165">Führen Sie den folgenden Befehl aus, um ein bestimmtes Benutzerkonto anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e086-165">To display a specific user account, run the following command.</span></span> <span data-ttu-id="8e086-166">Geben Sie den Anmeldenamen des Benutzerkontos ein, das auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet wird.</span><span class="sxs-lookup"><span data-stu-id="8e086-166">Fill in the sign-in name of the user account, which is also known as the user principal name (UPN).</span></span> <span data-ttu-id="8e086-167">Entfernen Sie die Zeichen "<" und ">".</span><span class="sxs-lookup"><span data-stu-id="8e086-167">Remove the "<" and ">" characters.</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a><span data-ttu-id="8e086-168">Anzeigen von Konten basierend auf einer gemeinsamen Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="8e086-168">View accounts based on a common property</span></span>

<span data-ttu-id="8e086-169">Um die Liste der anzuzeigenden Konten selektiver zu machen, können Sie das Cmdlet **Where** in Kombination mit dem Cmdlet **Get-MsolUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e086-169">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="8e086-170">Um die beiden Cmdlets zu kombinieren, verwenden Sie das "Pipe"-Zeichen ("|"), das PowerShell anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="8e086-170">To combine the two cmdlets, use the "pipe" character ("|"), which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="8e086-171">Im folgenden Beispiel werden nur die Benutzerkonten angezeigt, die einen nicht angegebenen Verwendungs Speicherort aufweisen:</span><span class="sxs-lookup"><span data-stu-id="8e086-171">Here's an example that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="8e086-172">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="8e086-172">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="8e086-173">Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="8e086-173">Get all the information on the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="8e086-174">Suchen Sie nach allen Benutzerkonten mit einem nicht angegebenen Verwendungs Speicherort (**wobei {$ \_ . UsageLocation-EQ $NULL}**).</span><span class="sxs-lookup"><span data-stu-id="8e086-174">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**).</span></span> <span data-ttu-id="8e086-175">In den geschweiften Klammern weist der Befehl PowerShell an, nur die Gruppe von Konten zu finden, für die die UsageLocation-Benutzerkonto Eigenschaft (\*\* $ \_ . UsageLocation**) ist nicht angegeben (**-EQ $NULL\*\*).</span><span class="sxs-lookup"><span data-stu-id="8e086-175">Inside the braces, the command instructs PowerShell to find only the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
<span data-ttu-id="8e086-176">Sie sollten ähnliche Informationen wie die folgenden erhalten:</span><span class="sxs-lookup"><span data-stu-id="8e086-176">You should get information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="8e086-177">Die *UsageLocation*-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="8e086-177">The *UsageLocation* property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="8e086-178">Um alle Eigenschaften für Benutzerkonten anzuzeigen, verwenden Sie das **Select** -Cmdlet und das Platzhalterzeichen (\*), um Sie alle für ein bestimmtes Benutzerkonto anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="8e086-178">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="8e086-179">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e086-179">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="8e086-180">Das *City*-Objekt steht z. B. für den Namen einer Benutzerkontoeigenschaft.</span><span class="sxs-lookup"><span data-stu-id="8e086-180">For example, *City* is the name of a user account property.</span></span> <span data-ttu-id="8e086-181">Mit dem folgenden Befehl können Sie alle Benutzerkonten für Benutzer auflisten, die in London Leben:</span><span class="sxs-lookup"><span data-stu-id="8e086-181">You can use the following command to list all of the user accounts for users who live in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="8e086-182">Die Syntax für das Cmdlet **Where** in diesen Beispielen ist **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="8e086-182">The syntax for the **Where** cmdlet in these examples is **Where {$\_.**</span></span> <span data-ttu-id="8e086-183">[Name der Benutzerkonten Eigenschaft] [Vergleichsoperator] Wert **}**.</span><span class="sxs-lookup"><span data-stu-id="8e086-183">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="8e086-184">[Vergleichsoperator] is **-EQ** für gleich, **-ne** für ungleich, **-lt** für kleiner als, **-gt** für größer als und andere.</span><span class="sxs-lookup"><span data-stu-id="8e086-184">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="8e086-185">[value] ist normalerweise eine Zeichenfolge (eine Sequenz von Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder **$null** für Unspecified.</span><span class="sxs-lookup"><span data-stu-id="8e086-185">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="8e086-186">Weitere Informationen finden Sie unter [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span><span class="sxs-lookup"><span data-stu-id="8e086-186">For more information, see [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).</span></span>
  
<span data-ttu-id="8e086-187">Verwenden Sie den folgenden Befehl, um den blockierten Status eines Benutzerkontos zu überprüfen:</span><span class="sxs-lookup"><span data-stu-id="8e086-187">To check the blocked status of a user account, use the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="8e086-188">Anzeigen zusätzlicher Eigenschaftswerte für Konten</span><span class="sxs-lookup"><span data-stu-id="8e086-188">View additional property values for accounts</span></span>

<span data-ttu-id="8e086-189">Standardmäßig werden mit dem Cmdlet **Get-MsolUser** diese drei Eigenschaften von Benutzerkonten angezeigt:</span><span class="sxs-lookup"><span data-stu-id="8e086-189">By default, the **Get-MsolUser** cmdlet displays these three properties of user accounts:</span></span>
  
- <span data-ttu-id="8e086-190">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="8e086-190">UserPrincipalName</span></span>
    
- <span data-ttu-id="8e086-191">DisplayName</span><span class="sxs-lookup"><span data-stu-id="8e086-191">DisplayName</span></span>
    
- <span data-ttu-id="8e086-192">isLicensed</span><span class="sxs-lookup"><span data-stu-id="8e086-192">isLicensed</span></span>
    
<span data-ttu-id="8e086-193">Wenn Sie zusätzliche Eigenschaften benötigen, beispielsweise die Abteilung, in der der Benutzer arbeitet, und das Land/die Region, in der Sie Microsoft 365-Dienste verwenden, können Sie **Get-MsolUser** in Kombination mit dem **Select** -Cmdlet ausführen, um die Liste der Benutzerkontoeigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="8e086-193">If you need additional properties, such as the department where the user works and the country/region where they use Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="8e086-194">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e086-194">Here's an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="8e086-195">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="8e086-195">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="8e086-196">Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="8e086-196">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="8e086-197">Zeigt nur den Namen des Benutzerkontos, die Abteilung und den Verwendungs Speicherort an (**Wählen Sie DisplayName, Abteilung, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="8e086-197">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="8e086-198">Sie sollten ähnliche Informationen wie die folgenden erhalten:</span><span class="sxs-lookup"><span data-stu-id="8e086-198">You should get information similar to this:</span></span>
  
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

<span data-ttu-id="8e086-199">Mit dem Cmdlet **"Select** " können Sie auswählen, welche Eigenschaften angezeigt werden sollen.</span><span class="sxs-lookup"><span data-stu-id="8e086-199">The **Select** cmdlet lets you choose what properties to display.</span></span> <span data-ttu-id="8e086-200">Wenn Sie alle Eigenschaften für ein bestimmtes Benutzerkonto anzeigen möchten, verwenden Sie das Platzhalterzeichen (\*).</span><span class="sxs-lookup"><span data-stu-id="8e086-200">To display all the properties for a specific user account, use the wildcard character (\*).</span></span> <span data-ttu-id="8e086-201">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="8e086-201">Here's an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="8e086-202">Um die Liste der anzuzeigenden Konten selektiver anzuzeigen, können Sie auch das Cmdlet " **Where** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="8e086-202">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="8e086-203">Es folgt ein Beispielbefehl, in dem nur die Benutzerkonten angezeigt werden, die einen nicht angegebenen Verwendungs Speicherort aufweisen:</span><span class="sxs-lookup"><span data-stu-id="8e086-203">Here's an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="8e086-204">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="8e086-204">This command instructs PowerShell to:</span></span>
  
1. <span data-ttu-id="8e086-205">Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="8e086-205">Get all the information about the user accounts (**Get-MsolUser**) and send it to the next command (**|**).</span></span>
    
1. <span data-ttu-id="8e086-206">Suchen Sie nach allen Benutzerkonten mit einem nicht angegebenen Verwendungs Speicherort (**wobei {$ \_ . UsageLocation-EQ $NULL}**) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="8e086-206">Find all user accounts that have an unspecified usage location (**Where {$\_.UsageLocation -eq $Null}**), and send the resulting information to the next command (**|**).</span></span> <span data-ttu-id="8e086-207">In den geschweiften Klammern weist der Befehl PowerShell an, nur die Konten zu finden, für die die UsageLocation-Benutzerkonto Eigenschaft (\*\* $ \_ . UsageLocation**) ist nicht angegeben (**-EQ $NULL\*\*).</span><span class="sxs-lookup"><span data-stu-id="8e086-207">Inside the braces, the command instructs PowerShell to only find the set of accounts for which the UsageLocation user account property (**$\_.UsageLocation**) is not specified (**-eq $Null**).</span></span>
    
1. <span data-ttu-id="8e086-208">Zeigt nur den Namen des Benutzerkontos, die Abteilung und den Verwendungs Speicherort an (**Wählen Sie DisplayName, Abteilung, UsageLocation**).</span><span class="sxs-lookup"><span data-stu-id="8e086-208">Display only the user account name, department, and usage location (**Select DisplayName, Department, UsageLocation**).</span></span>
    
<span data-ttu-id="8e086-209">Sie sollten ähnliche Informationen wie die folgenden erhalten:</span><span class="sxs-lookup"><span data-stu-id="8e086-209">You should get information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="8e086-210">Wenn Sie die Verzeichnissynchronisierung zum Erstellen und Verwalten Ihrer Microsoft 365-Benutzer verwenden, können Sie das lokale Konto anzeigen, von dem ein Microsoft 365-Benutzer projiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="8e086-210">If you're using directory synchronization to create and manage your Microsoft 365 users, you can display the local account from which a Microsoft 365 user has been projected.</span></span> <span data-ttu-id="8e086-211">Im folgenden Beispiel wird davon ausgegangen, dass:</span><span class="sxs-lookup"><span data-stu-id="8e086-211">The following example assumes that:</span></span>

- <span data-ttu-id="8e086-212">Azure AD Connect ist für die Verwendung des standardmäßigen Quell Ankers von objectGUID konfiguriert.</span><span class="sxs-lookup"><span data-stu-id="8e086-212">Azure AD Connect is configured to use the default source anchor of ObjectGUID.</span></span> <span data-ttu-id="8e086-213">(Weitere Informationen zum Konfigurieren eines Quell Ankers finden Sie unter [Azure AD Connect: Design Concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span><span class="sxs-lookup"><span data-stu-id="8e086-213">(For more information about configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).</span></span>
- <span data-ttu-id="8e086-214">Das Active Directory-Domänendienste Modul für PowerShell wurde installiert (siehe [Remotetools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span><span class="sxs-lookup"><span data-stu-id="8e086-214">The Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="8e086-215">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="8e086-215">See also</span></span>

[<span data-ttu-id="8e086-216">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e086-216">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8e086-217">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="8e086-217">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="8e086-218">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8e086-218">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
