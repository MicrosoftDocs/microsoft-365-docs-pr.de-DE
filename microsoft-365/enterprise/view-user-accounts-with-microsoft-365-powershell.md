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
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Anzeigen von Microsoft 365-Benutzerkonten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können das Microsoft 365 Admin Center verwenden, um die Konten für Ihren Microsoft 365-Mandanten anzuzeigen. PowerShell für Microsoft 365 ermöglicht dies, bietet aber auch zusätzliche Funktionen.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
### <a name="view-all-accounts"></a>Alle Konten anzeigen

Um die vollständige Liste der Benutzerkonten anzuzeigen, führen Sie den folgenden Befehl aus:
  
```powershell
Get-AzureADUser
```

Sie sollten ähnliche Informationen wie die folgenden erhalten:
  
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

### <a name="view-a-specific-account"></a>Anzeigen eines bestimmten Kontos

Führen Sie den folgenden Befehl aus, um ein bestimmtes Benutzerkonto anzuzeigen. Geben Sie den Anmeldekontonamen des Benutzerkontos ein, das auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet wird. Entfernen Sie die Zeichen "<" und ">".
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Hier ein Beispiel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Anzeigen zusätzlicher Eigenschaftswerte für ein bestimmtes Konto

Standardmäßig zeigt das Cmdlet **Get-AzureADUser** nur die Eigenschaften *objectID*, *DisplayName*und *userPrincipalName* von Konten an.

Um die anzuzeigenden Eigenschaften selektiver zu machen, verwenden **Sie das SELECT** -Cmdlet in Kombination mit dem Cmdlet **Get-AzureADUser** . Um die beiden Cmdlets zu kombinieren, verwenden Sie das "Pipe"-Zeichen ("|"), das Azure Active Directory PowerShell für Graph anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden. Im folgenden Beispiel wird der Befehl *DisplayName*, *Department*und *UsageLocation* für jedes Benutzerkonto angezeigt:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
1. Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).
    
1.  Zeigt nur den Namen des Benutzerkontos, die Abteilung und den Verwendungs Speicherort an (**Wählen Sie DisplayName, Abteilung, UsageLocation**).
  
Wenn Sie alle Eigenschaften für ein bestimmtes Benutzerkonto anzeigen möchten, verwenden **Sie das SELECT** -Cmdlet und das Platzhalterzeichen (*). Hier ein Beispiel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Führen Sie als weiteres Beispiel den folgenden Befehl aus, um den aktivierten Status eines bestimmten Benutzerkontos zu überprüfen:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Anzeigen des Status der Konto Synchronisierung

Benutzerkonten weisen zwei Quellen auf: 

- Windows Server Active Directory (AD), bei denen es sich um Konten handelt, die vom lokalen AD zur Cloud synchronisiert werden.

- Azure Active Directory (Azure AD) Ad-Konten, die direkt in der Cloud erstellt werden.


Mit dem folgenden Befehl wird PowerShell angewiesen, alle Benutzer abzurufen, bei denen das Attribut *DirSyncEnabled* auf *true*festgelegt ist. Sie können es verwenden, um Konten zu finden, die von lokalen AD synchronisiert werden.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

Mit dem folgenden Befehl wird PowerShell angewiesen, alle Benutzer abzurufen, bei denen das Attribut *DirSyncEnabled* auf *false*festgelegt ist. Sie können damit nur Cloud-Konten suchen.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Anzeigen von Konten basierend auf einer gemeinsamen Eigenschaft

Um die Liste der anzuzeigenden Konten selektiver zu machen, können Sie das Cmdlet **Where** in Kombination mit dem Cmdlet **Get-AzureADUser** verwenden. Um die beiden Cmdlets zu kombinieren, verwenden Sie das "Pipe"-Zeichen ("|"), das Azure Active Directory PowerShell für Graph anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden. Es folgt ein Beispielbefehl, in dem nur die Benutzerkonten angezeigt werden, die einen nicht angegebenen Verwendungs Speicherort aufweisen:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Dieser Befehl weist Azure Active Directory PowerShell für Graph Folgendes zu:
  
1. Alle Informationen zu den Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden ( **|** ).
    
1. Suchen Sie nach allen Benutzerkonten mit einem nicht angegebenen Verwendungs Speicherort (**wobei {$ \_ . UsageLocation-EQ $NULL}**). In den geschweiften Klammern weist der Befehl PowerShell an, nur die Konten zu finden, für die die UsageLocation-Benutzerkonto Eigenschaft (** $ \_ . UsageLocation**) ist nicht angegeben (**-EQ $NULL**).
    
Die **UsageLocation**-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist. Um alle Eigenschaften für ein bestimmtes Benutzerkonto anzuzeigen, verwenden Sie das **Select** -Cmdlet und das Platzhalterzeichen (*). Hier ein Beispiel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Das **City**-Objekt steht z. B. für den Namen einer Benutzerkontoeigenschaft. Mit dem folgenden Befehl können Sie alle Konten von Benutzern auflisten, die in London Leben:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Die Syntax für das Cmdlet **Where** in diesen Beispielen ist **{$ \_ .** [Name der Benutzerkonten Eigenschaft] [Vergleichsoperator] Wert **}**. > [Vergleichsoperator] ist **-EQ** für gleich, **-ne** für ungleich, **-lt** für kleiner als, **-gt** für größer als und andere.  [value] ist normalerweise eine Zeichenfolge (eine Sequenz von Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder **$null** für Unspecified. Weitere Informationen finden Sie unter [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="view-all-accounts"></a>Alle Konten anzeigen

Um die vollständige Liste der Benutzerkonten anzuzeigen, führen Sie den folgenden Befehl aus:
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core unterstützt das Microsoft Azure Active Directory Modul für Windows PowerShell Modul und Cmdlets mit *MSOL* nicht in Ihrem Namen. Führen Sie diese Cmdlets aus Windows PowerShell aus.
>

Sie sollten ähnliche Informationen wie die folgenden erhalten:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Das **Get-MsolUser**-Cmdlet verfügt darüber hinaus über eine Reihe von Parametern zum Filtern der angezeigten Benutzerkonten. Führen Sie zum Beispiel für die Liste der nicht lizenzierten Benutzer (Benutzer, die Microsoft 365 hinzugefügt wurden, aber noch nicht für die Verwendung eines der Dienste lizenziert wurden) den folgenden Befehl aus:
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Sie sollten ähnliche Informationen wie die folgenden erhalten:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Informationen zu zusätzlichen Parametern zum Filtern der Gruppe von Benutzerkonten, die angezeigt werden, finden Sie unter [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Anzeigen eines bestimmten Kontos

Führen Sie den folgenden Befehl aus, um ein bestimmtes Benutzerkonto anzuzeigen. Geben Sie den Anmeldenamen des Benutzerkontos ein, das auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet wird. Entfernen Sie die Zeichen "<" und ">".
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Anzeigen von Konten basierend auf einer gemeinsamen Eigenschaft

Um die Liste der anzuzeigenden Konten selektiver zu machen, können Sie das Cmdlet **Where** in Kombination mit dem Cmdlet **Get-MsolUser** verwenden. Um die beiden Cmdlets zu kombinieren, verwenden Sie das "Pipe"-Zeichen ("|"), das PowerShell anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden. Im folgenden Beispiel werden nur die Benutzerkonten angezeigt, die einen nicht angegebenen Verwendungs Speicherort aufweisen:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
1. Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).
    
1. Suchen Sie nach allen Benutzerkonten mit einem nicht angegebenen Verwendungs Speicherort (**wobei {$ \_ . UsageLocation-EQ $NULL}**). In den geschweiften Klammern weist der Befehl PowerShell an, nur die Gruppe von Konten zu finden, für die die UsageLocation-Benutzerkonto Eigenschaft (** $ \_ . UsageLocation**) ist nicht angegeben (**-EQ $NULL**).
    
Sie sollten ähnliche Informationen wie die folgenden erhalten:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

Die *UsageLocation*-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist. Um alle Eigenschaften für Benutzerkonten anzuzeigen, verwenden Sie das **Select** -Cmdlet und das Platzhalterzeichen (*), um Sie alle für ein bestimmtes Benutzerkonto anzuzeigen. Hier ein Beispiel:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Das *City*-Objekt steht z. B. für den Namen einer Benutzerkontoeigenschaft. Mit dem folgenden Befehl können Sie alle Benutzerkonten für Benutzer auflisten, die in London Leben:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Die Syntax für das Cmdlet **Where** in diesen Beispielen ist **{$ \_ .** [Name der Benutzerkonten Eigenschaft] [Vergleichsoperator] Wert **}**.  [Vergleichsoperator] is **-EQ** für gleich, **-ne** für ungleich, **-lt** für kleiner als, **-gt** für größer als und andere.  [value] ist normalerweise eine Zeichenfolge (eine Sequenz von Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder **$null** für Unspecified. Weitere Informationen finden Sie unter [Where](https://docs.microsoft.com/powershell/module/microsoft.powershell.core/where-object?view=powershell-7).
  
Verwenden Sie den folgenden Befehl, um den blockierten Status eines Benutzerkontos zu überprüfen:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Anzeigen zusätzlicher Eigenschaftswerte für Konten

Standardmäßig werden mit dem Cmdlet **Get-MsolUser** diese drei Eigenschaften von Benutzerkonten angezeigt:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Wenn Sie zusätzliche Eigenschaften benötigen, beispielsweise die Abteilung, in der der Benutzer arbeitet, und das Land/die Region, in der Sie Microsoft 365-Dienste verwenden, können Sie **Get-MsolUser** in Kombination mit dem **Select** -Cmdlet ausführen, um die Liste der Benutzerkontoeigenschaften anzugeben. Hier ein Beispiel:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
1. Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).
    
1. Zeigt nur den Namen des Benutzerkontos, die Abteilung und den Verwendungs Speicherort an (**Wählen Sie DisplayName, Abteilung, UsageLocation**).
    
Sie sollten ähnliche Informationen wie die folgenden erhalten:
  
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

Mit dem Cmdlet **"Select** " können Sie auswählen, welche Eigenschaften angezeigt werden sollen. Wenn Sie alle Eigenschaften für ein bestimmtes Benutzerkonto anzeigen möchten, verwenden Sie das Platzhalterzeichen (*). Hier ein Beispiel:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Um die Liste der anzuzeigenden Konten selektiver anzuzeigen, können Sie auch das Cmdlet " **Where** " verwenden. Es folgt ein Beispielbefehl, in dem nur die Benutzerkonten angezeigt werden, die einen nicht angegebenen Verwendungs Speicherort aufweisen:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
1. Alle Informationen zu den Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden ( **|** ).
    
1. Suchen Sie nach allen Benutzerkonten mit einem nicht angegebenen Verwendungs Speicherort (**wobei {$ \_ . UsageLocation-EQ $NULL}**) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ). In den geschweiften Klammern weist der Befehl PowerShell an, nur die Konten zu finden, für die die UsageLocation-Benutzerkonto Eigenschaft (** $ \_ . UsageLocation**) ist nicht angegeben (**-EQ $NULL**).
    
1. Zeigt nur den Namen des Benutzerkontos, die Abteilung und den Verwendungs Speicherort an (**Wählen Sie DisplayName, Abteilung, UsageLocation**).
    
Sie sollten ähnliche Informationen wie die folgenden erhalten:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Wenn Sie die Verzeichnissynchronisierung zum Erstellen und Verwalten Ihrer Microsoft 365-Benutzer verwenden, können Sie das lokale Konto anzeigen, von dem ein Microsoft 365-Benutzer projiziert wurde. Im folgenden Beispiel wird davon ausgegangen, dass:

- Azure AD Connect ist für die Verwendung des standardmäßigen Quell Ankers von objectGUID konfiguriert. (Weitere Informationen zum Konfigurieren eines Quell Ankers finden Sie unter [Azure AD Connect: Design Concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)).
- Das Active Directory-Domänendienste Modul für PowerShell wurde installiert (siehe [Remotetools](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)).

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)
