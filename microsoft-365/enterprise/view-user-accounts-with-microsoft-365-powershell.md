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
ms.openlocfilehash: 4dba05ce440ec0d395fda58a12df3e9f751bb469
ms.sourcegitcommit: 8589323c1b4ab43aab30597ee66303b0a0eb71ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/05/2020
ms.locfileid: "48357898"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a><span data-ttu-id="1e6fd-103">Anzeigen von Microsoft 365-Benutzerkonten mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e6fd-103">View Microsoft 365 user accounts with PowerShell</span></span>

<span data-ttu-id="1e6fd-104">*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*</span><span class="sxs-lookup"><span data-stu-id="1e6fd-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="1e6fd-105">Sie können zwar das Microsoft 365 Admin Center verwenden, um die Konten für Ihren Microsoft 365-Mandanten anzuzeigen, aber Sie können auch PowerShell für Microsoft 365 verwenden und einige Dinge tun, die das Admin Center nicht kann.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-105">Although you can use the Microsoft 365 admin center to view the accounts for your Microsoft 365 tenant, you can also use PowerShell for Microsoft 365 and do some things that the admin center cannot.</span></span>
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="1e6fd-106">Verwenden der Azure Active Directory PowerShell für Graph-Module</span><span class="sxs-lookup"><span data-stu-id="1e6fd-106">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="1e6fd-107">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-107">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
### <a name="view-all-accounts"></a><span data-ttu-id="1e6fd-108">Alle Konten anzeigen</span><span class="sxs-lookup"><span data-stu-id="1e6fd-108">View all accounts</span></span>

<span data-ttu-id="1e6fd-109">Um die vollständige Liste der Benutzerkonten anzuzeigen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-109">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-AzureADUser
```

<span data-ttu-id="1e6fd-110">Es sollten Informationen ähnlich den folgenden angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-110">You should see information similar to this:</span></span>
  
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

### <a name="view-a-specific-account"></a><span data-ttu-id="1e6fd-111">Anzeigen eines bestimmten Kontos</span><span class="sxs-lookup"><span data-stu-id="1e6fd-111">View a specific account</span></span>

<span data-ttu-id="1e6fd-112">Um ein bestimmtes Benutzerkonto anzuzeigen, geben Sie den Anmeldekontonamen des Benutzerkontos ein, das auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet wird, entfernen Sie die Zeichen "<" und ">", und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-112">To display a specific user account, fill in the sign-in account name of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

<span data-ttu-id="1e6fd-113">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-113">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a><span data-ttu-id="1e6fd-114">Anzeigen zusätzlicher Eigenschaftswerte für ein bestimmtes Konto</span><span class="sxs-lookup"><span data-stu-id="1e6fd-114">View additional property values for a specific account</span></span>

<span data-ttu-id="1e6fd-115">Standardmäßig zeigt das Cmdlet **Get-AzureADUser** nur die Eigenschaften ObjectID, DisplayName und userPrincipalName von Konten an.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-115">By default, the **Get-AzureADUser** cmdlet only displays the ObjectID, DisplayName, and UserPrincipalName properties of accounts.</span></span>

<span data-ttu-id="1e6fd-116">Um die Liste der anzuzeigenden Eigenschaften selektiver zu machen, können Sie das Cmdlet **Select** in Kombination mit dem Cmdlet **Get-AzureADUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-116">To be more selective about the list of properties to display, you can use the **Select** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="1e6fd-117">Um die beiden Cmdlets zu kombinieren, verwenden wir das "Pipe"-Zeichen "|", das Azure Active Directory PowerShell für Graph anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-117">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="1e6fd-118">Es folgt ein Beispielbefehl, mit dem DisplayName, Department und UsageLocation für jedes Benutzerkonto angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-118">Here is an example command that displays the DisplayName, Department, and UsageLocation for every user account:</span></span>
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

<span data-ttu-id="1e6fd-119">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-119">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="1e6fd-120">Alle Informationen der Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden (**|**).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-120">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="1e6fd-121">Zeigt nur den Namen des Benutzerkontos, die Abteilung und den Verwendungs Speicherort an ( **Wählen Sie DisplayName, Abteilung, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-121">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
  
<span data-ttu-id="1e6fd-122">Um alle Eigenschaften für Benutzerkonten anzuzeigen, verwenden Sie das **Select** -Cmdlet und das Platzhalterzeichen (\*), um Sie alle für ein bestimmtes Benutzerkonto anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-122">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="1e6fd-123">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-123">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="1e6fd-124">Als weiteres Beispiel können Sie den aktivierten Status eines bestimmten Benutzerkontos überprüfen, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-124">As another example, you can check the enabled status of a specific user account with the following command:</span></span>
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a><span data-ttu-id="1e6fd-125">Anzeigen des Status der Konto Synchronisierung</span><span class="sxs-lookup"><span data-stu-id="1e6fd-125">View account synchronization status</span></span>

<span data-ttu-id="1e6fd-126">Benutzerkonten weisen zwei Quellen auf; Windows Server Active Directory (AD), bei denen es sich um Konten handelt, die vom lokalen AD zur Cloud synchronisiert werden und Azure Ad die in der Cloud direkt erstellte Konten sind.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-126">User accounts have two sources; Windows Server Active Directory (AD) which are accounts that sync from on-premises AD to the cloud and Azure AD which are accounts directly created in the cloud.</span></span>

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```
<span data-ttu-id="1e6fd-127">Mit diesem Befehl wird PowerShell angewiesen, alle Benutzer abzurufen, bei denen das Attribut **DirSyncEnabled** auf true festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-127">This command instructs PowerShell to get all users who have the attribute **DirSyncEnabled** set to True.</span></span> <span data-ttu-id="1e6fd-128">Es kann zum Abrufen von Konten verwendet werden, die von lokalen AD synchronisiert werden.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-128">It can be used to pull up accounts synchronizing from on-premise AD.</span></span>


```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $true}
```
<span data-ttu-id="1e6fd-129">Mit diesem Befehl wird PowerShell angewiesen, alle Benutzer abzurufen, bei denen das Attribut **DirSyncEnabled** auf false festgelegt ist.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-129">This command instructs PowerShell to get all users who have the attribute **DirSyncEnabled** set to False.</span></span> <span data-ttu-id="1e6fd-130">Es kann verwendet werden, um Cloud-only-Konten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-130">It can be used to pull up cloud-only accounts.</span></span>

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="1e6fd-131">Anzeigen einiger Konten basierend auf einer gemeinsamen Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1e6fd-131">View some accounts based on a common property</span></span>

<span data-ttu-id="1e6fd-132">Um die Liste der anzuzeigenden Konten selektiver zu machen, können Sie das Cmdlet **Where** in Kombination mit dem Cmdlet **Get-AzureADUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-132">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-AzureADUser** cmdlet.</span></span> <span data-ttu-id="1e6fd-133">Um die beiden Cmdlets zu kombinieren, verwenden wir das "Pipe"-Zeichen "|", das Azure Active Directory PowerShell für Graph anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-133">To combine the two cmdlets, we use the "pipe" character "|", which tells Azure Active Directory PowerShell for Graph to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="1e6fd-134">Nachfolgend ist ein Beispielbefehl aufgeführt, mit dem nur die Benutzerkonten angezeigt werden, die über einen nicht angegebenen Verwendungsstandort verfügen:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-134">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="1e6fd-135">Dieser Befehl weist Azure Active Directory PowerShell für Graph Folgendes zu:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-135">This command instructs Azure Active Directory PowerShell for Graph to:</span></span>
  
- <span data-ttu-id="1e6fd-136">Alle Informationen der Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden (**|**).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-136">Get all of the information on the user accounts ( **Get-AzureADUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="1e6fd-137">Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungs Speicherort ( **wobei {$ \_ . UsageLocation-EQ $NULL}** ).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-137">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="1e6fd-138">In den geschweiften Klammern weist der Befehl PowerShell an, nur den kontensatz zu finden, in dem die UsageLocation-Benutzerkonto Eigenschaft ( \*\* $ \_ . UsageLocation\*\* ) ist nicht angegeben ( **-EQ $NULL** ).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-138">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="1e6fd-139">Die **UsageLocation**-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-139">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="1e6fd-140">Um alle Eigenschaften für Benutzerkonten anzuzeigen, verwenden Sie das **Select** -Cmdlet und das Platzhalterzeichen (\*), um Sie alle für ein bestimmtes Benutzerkonto anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-140">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="1e6fd-141">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-141">Here is an example:</span></span>
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="1e6fd-p108">In dieser Liste steht das **City**-Objekt für den Namen einer Benutzerkontoeigenschaft. Dies bedeutet, dass Sie mit dem folgenden Befehl eine Liste aller Benutzerkonten für Benutzer, die in London leben, anzeigen können:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-p108">For example, from this list, **City** is the name of a user account property. This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="1e6fd-144">Die Syntax für das in diesen Beispielen dargestellte Cmdlet **Where** ist **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="1e6fd-144">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="1e6fd-145">[Name der Benutzerkonten Eigenschaft] [Vergleichsoperator] Wert **}**. > [Vergleichsoperator] ist **-EQ** für gleich, **-ne** für ungleich, **-lt** für kleiner als, **-gt** für größer als und andere.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-145">[user account property name] [comparison operator] [value] **}**.>  [comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="1e6fd-146">[value] ist normalerweise eine Zeichenfolge (eine Sequenz von Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder **$null** für Unspecified> siehe [Where](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) für weitere Informationen.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-146">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified>  See [Where](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) for more information.</span></span>
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="1e6fd-147">Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e6fd-147">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="1e6fd-148">Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-148">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

### <a name="view-all-accounts"></a><span data-ttu-id="1e6fd-149">Alle Konten anzeigen</span><span class="sxs-lookup"><span data-stu-id="1e6fd-149">View all accounts</span></span>

<span data-ttu-id="1e6fd-150">Um die vollständige Liste der Benutzerkonten anzuzeigen, führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-150">To display the full list of user accounts, run this command:</span></span>
  
```powershell
Get-MsolUser
```

>[!Note]
><span data-ttu-id="1e6fd-151">PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-151">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="1e6fd-152">Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-152">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="1e6fd-153">Es sollten Informationen ähnlich den folgenden angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-153">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="1e6fd-154">Das **Get-MsolUser**-Cmdlet verfügt darüber hinaus über eine Reihe von Parametern zum Filtern der angezeigten Benutzerkonten.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-154">The **Get-MsolUser** cmdlet also has a set of parameters to filter the set of user accounts displayed.</span></span> <span data-ttu-id="1e6fd-155">Führen Sie diesen Befehl beispielsweise für die Liste der nicht lizenzierten Benutzer (Benutzer, die Microsoft 365 hinzugefügt wurden, aber noch nicht für die Verwendung eines der Dienste lizenziert wurden) aus.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-155">For example, for the list of unlicensed users (users who've been added to Microsoft 365 but haven't yet been licensed to use any of the services), run this command.</span></span>
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

<span data-ttu-id="1e6fd-156">Es sollten Informationen ähnlich den folgenden angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-156">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

<span data-ttu-id="1e6fd-157">Weitere Informationen zu zusätzlichen Parametern zum Filtern des angezeigten Satzes von Benutzerkonten finden Sie unter [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-157">For more information about additional parameters to filter the display the set of user accounts displayed, see [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).</span></span>
  
### <a name="view-a-specific-account"></a><span data-ttu-id="1e6fd-158">Anzeigen eines bestimmten Kontos</span><span class="sxs-lookup"><span data-stu-id="1e6fd-158">View a specific account</span></span>

<span data-ttu-id="1e6fd-159">Um ein bestimmtes Benutzerkonto anzuzeigen, geben Sie den Anmeldenamen des Benutzerkontos des Benutzerkontos ein, das auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet wird, entfernen Sie die Zeichen "<" und ">", und führen Sie den folgenden Befehl aus:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-159">To display a specific user account, fill in the sign-in name of the user account of the user account, also known as the user principal name (UPN), remove the "<" and ">" characters, and run this command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a><span data-ttu-id="1e6fd-160">Anzeigen einiger Konten basierend auf einer gemeinsamen Eigenschaft</span><span class="sxs-lookup"><span data-stu-id="1e6fd-160">View some accounts based on a common property</span></span>

<span data-ttu-id="1e6fd-161">Um die Liste der anzuzeigenden Konten selektiver zu machen, können Sie das Cmdlet **Where** in Kombination mit dem Cmdlet **Get-MsolUser** verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-161">To be more selective about the list of accounts to display, you can use the **Where** cmdlet in combination with the **Get-MsolUser** cmdlet.</span></span> <span data-ttu-id="1e6fd-162">Um die beiden Cmdlets zu kombinieren, verwenden wir das "Pipe"-Zeichen "|", das PowerShell anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-162">To combine the two cmdlets, we use the "pipe" character "|", which tells PowerShell to take the results of one command and send it to the next command.</span></span> <span data-ttu-id="1e6fd-163">Nachfolgend ist ein Beispielbefehl aufgeführt, mit dem nur die Benutzerkonten angezeigt werden, die über einen nicht angegebenen Verwendungsstandort verfügen:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-163">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

<span data-ttu-id="1e6fd-164">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-164">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="1e6fd-165">Alle Informationen der Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden (**|**).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-165">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="1e6fd-166">Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungs Speicherort ( **wobei {$ \_ . UsageLocation-EQ $NULL}** ).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-166">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ).</span></span> <span data-ttu-id="1e6fd-167">In den geschweiften Klammern weist der Befehl PowerShell an, nur den kontensatz zu finden, in dem die UsageLocation-Benutzerkonto Eigenschaft ( \*\* $ \_ . UsageLocation\*\* ) ist nicht angegeben ( **-EQ $NULL** ).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-167">Inside the braces, the command instructs PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
<span data-ttu-id="1e6fd-168">Es sollten Informationen ähnlich den folgenden angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-168">You should see information similar to this:</span></span>
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

<span data-ttu-id="1e6fd-169">Die **UsageLocation**-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-169">The **UsageLocation** property is only one of many properties associated with a user account.</span></span> <span data-ttu-id="1e6fd-170">Um alle Eigenschaften für Benutzerkonten anzuzeigen, verwenden Sie das **Select** -Cmdlet und das Platzhalterzeichen (\*), um Sie alle für ein bestimmtes Benutzerkonto anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-170">To see all of the properties for user accounts, use the **Select** cmdlet and the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="1e6fd-171">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-171">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="1e6fd-p115">In dieser Liste steht das **City**-Objekt für den Namen einer Benutzerkontoeigenschaft. Dies bedeutet, dass Sie mit dem folgenden Befehl eine Liste aller Benutzerkonten für Benutzer, die in London leben, anzeigen können:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-p115">For example, from this list, **City** is the name of a user account property. This means you can use the following command to list all of the user accounts for users living in London:</span></span>
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  <span data-ttu-id="1e6fd-174">Die Syntax für das in diesen Beispielen dargestellte Cmdlet **Where** ist **{$ \_ .**</span><span class="sxs-lookup"><span data-stu-id="1e6fd-174">The syntax for the **Where** cmdlet shown in these examples is **Where {$\_.**</span></span> <span data-ttu-id="1e6fd-175">[Name der Benutzerkonten Eigenschaft] [Vergleichsoperator] Wert **}**.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-175">[user account property name] [comparison operator] [value] **}**.</span></span>  <span data-ttu-id="1e6fd-176">[Vergleichsoperator] is **-EQ** für gleich, **-ne** für ungleich, **-lt** für kleiner als, **-gt** für größer als und andere.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-176">[comparison operator] is **-eq** for equals, **-ne** for not equals, **-lt** for less than, **-gt** for greater than, and others.</span></span>  <span data-ttu-id="1e6fd-177">[value] ist normalerweise eine Zeichenfolge (eine Sequenz von Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder **$null** für Unspecified.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-177">[value] is typically a string (a sequence of letters, numbers, and other characters), a numerical value, or **$Null** for unspecified.</span></span> <span data-ttu-id="1e6fd-178">Weitere Informationen finden Sie unter [Where](https://technet.microsoft.com/library/hh849715.aspx) for more.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-178">See [Where](https://technet.microsoft.com/library/hh849715.aspx) for more information.</span></span>
  
<span data-ttu-id="1e6fd-179">Sie können den blockierten Status eines Benutzerkontos überprüfen, indem Sie den folgenden Befehl ausführen:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-179">You can check the blocked status of a user account with the following command:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a><span data-ttu-id="1e6fd-180">Anzeigen zusätzlicher Eigenschaftswerte für Konten</span><span class="sxs-lookup"><span data-stu-id="1e6fd-180">View additional property values for accounts</span></span>

<span data-ttu-id="1e6fd-181">Das Cmdlet **Get-MsolUser** zeigt standardmäßig drei Eigenschaften von Benutzerkonten an:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-181">The **Get-MsolUser** cmdlet by default displays three properties of user accounts:</span></span>
  
- <span data-ttu-id="1e6fd-182">UserPrincipalName</span><span class="sxs-lookup"><span data-stu-id="1e6fd-182">UserPrincipalName</span></span>
    
- <span data-ttu-id="1e6fd-183">DisplayName</span><span class="sxs-lookup"><span data-stu-id="1e6fd-183">DisplayName</span></span>
    
- <span data-ttu-id="1e6fd-184">isLicensed</span><span class="sxs-lookup"><span data-stu-id="1e6fd-184">isLicensed</span></span>
    
<span data-ttu-id="1e6fd-185">Wenn Sie zusätzliche Eigenschaften benötigen, beispielsweise die Abteilung, für die der Benutzer arbeitet, und das Land/die Region, in der der Benutzer Microsoft 365-Dienste verwendet, können Sie **Get-MsolUser** in Kombination mit dem **Select** -Cmdlet ausführen, um die Liste der Benutzerkontoeigenschaften anzugeben.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-185">If you need additional properties, such as the department the user works for and the country/region where the user uses Microsoft 365 services, you can run **Get-MsolUser** in combination with the **Select** cmdlet to specify the list of user account properties.</span></span> <span data-ttu-id="1e6fd-186">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-186">Here is an example:</span></span>
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="1e6fd-187">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-187">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="1e6fd-188">Alle Informationen der Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden (**|**).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-188">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="1e6fd-189">Zeigt nur den Namen des Benutzerkontos, die Abteilung und den Verwendungs Speicherort an ( **Wählen Sie DisplayName, Abteilung, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-189">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="1e6fd-190">Es sollten Informationen ähnlich den folgenden angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-190">You should see information similar to this:</span></span>
  
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

<span data-ttu-id="1e6fd-191">Mit dem Cmdlet **"Select** " können Sie die Eigenschaften auswählen, die ein Befehl angezeigt werden soll.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-191">The **Select** cmdlet lets you pick and choose the properties you want a command to display.</span></span> <span data-ttu-id="1e6fd-192">Wenn Sie alle Eigenschaften für Benutzerkonten anzeigen möchten, verwenden Sie das Platzhalterzeichen (\*), um Sie alle für ein bestimmtes Benutzerkonto anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-192">To see all of the properties for user accounts, use the wildcard character (\*) to display them all for a specific user account.</span></span> <span data-ttu-id="1e6fd-193">Hier ein Beispiel:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-193">Here is an example:</span></span>
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

<span data-ttu-id="1e6fd-194">Um die Liste der anzuzeigenden Konten selektiver anzuzeigen, können Sie auch das Cmdlet " **Where** " verwenden.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-194">To be more selective about the list of accounts to display, you can also use the **Where** cmdlet.</span></span> <span data-ttu-id="1e6fd-195">Nachfolgend ist ein Beispielbefehl aufgeführt, mit dem nur die Benutzerkonten angezeigt werden, die über einen nicht angegebenen Verwendungsstandort verfügen:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-195">Here is an example command that displays only those user accounts that have an unspecified usage location:</span></span>
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

<span data-ttu-id="1e6fd-196">Mit diesem Befehl wird PowerShell an Folgendes angewiesen:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-196">This command instructs PowerShell to:</span></span>
  
- <span data-ttu-id="1e6fd-197">Alle Informationen der Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden (**|**).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-197">Get all of the information on the user accounts ( **Get-MsolUser** ) and send it to the next command ( **|** ).</span></span>
    
- <span data-ttu-id="1e6fd-198">Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungs Speicherort ( **wobei {$ \_ . UsageLocation-EQ $NULL}** ) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-198">Find all of the user accounts that have an unspecified usage location ( **Where {$\_.UsageLocation -eq $Null}** ) and send the resulting information to the next command ( **|** ).</span></span> <span data-ttu-id="1e6fd-199">Innerhalb der geschweiften Klammern weist der Befehl PowerShell an, nur den kontensatz zu finden, in dem die UsageLocation-Benutzerkonto Eigenschaft ( \*\* $ \_ . UsageLocation\*\* ) ist nicht angegeben ( **-EQ $NULL** ).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-199">Inside the braces, the command is instructing PowerShell to only find the set of accounts in which the UsageLocation user account property ( **$\_.UsageLocation** ) is not specified ( **-eq $Null** ).</span></span>
    
- <span data-ttu-id="1e6fd-200">Zeigt nur den Namen des Benutzerkontos, die Abteilung und den Verwendungs Speicherort an ( **Wählen Sie DisplayName, Abteilung, UsageLocation** ).</span><span class="sxs-lookup"><span data-stu-id="1e6fd-200">Display only the user account name, department, and usage location ( **Select DisplayName, Department, UsageLocation** ).</span></span>
    
<span data-ttu-id="1e6fd-201">Es sollten Informationen ähnlich den folgenden angezeigt werden:</span><span class="sxs-lookup"><span data-stu-id="1e6fd-201">You should see information similar to this:</span></span>
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

<span data-ttu-id="1e6fd-202">Wenn Sie die Verzeichnissynchronisierung zum Erstellen und Verwalten Ihrer Microsoft 365-Benutzer verwenden, können Sie das lokale Konto anzeigen, aus dem ein Microsoft 365-Benutzer projiziert wurde.</span><span class="sxs-lookup"><span data-stu-id="1e6fd-202">If you are using directory synchronization to create and manage your Microsoft 365 users, you can display which local account a Microsoft 365 user has been projected from.</span></span> <span data-ttu-id="1e6fd-203">Im folgenden wird davon ausgegangen, dass Azure AD Connect für die Verwendung des Standard Quell Ankers von objectGUID konfiguriert ist (Weitere Informationen zum Konfigurieren eines Quell Ankers finden Sie unter [Azure AD Connect: Design Concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)), und es wird davon ausgegangen, dass das Active Directory-Domänendienste Modul für PowerShell installiert wurde (siehe Tools für die [Remoteverwaltung](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span><span class="sxs-lookup"><span data-stu-id="1e6fd-203">The following assumes that Azure AD Connect has been configured to use the default source anchor of ObjectGUID (for more on configuring a source anchor, see [Azure AD Connect: Design concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)) and assumes that the Active Directory Domain Services module for PowerShell has been installed (see [RSAT tools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):</span></span>

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a><span data-ttu-id="1e6fd-204">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="1e6fd-204">See also</span></span>

[<span data-ttu-id="1e6fd-205">Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e6fd-205">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1e6fd-206">Verwalten von Microsoft 365 mit PowerShell</span><span class="sxs-lookup"><span data-stu-id="1e6fd-206">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="1e6fd-207">Erste Schritte mit PowerShell für Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="1e6fd-207">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
