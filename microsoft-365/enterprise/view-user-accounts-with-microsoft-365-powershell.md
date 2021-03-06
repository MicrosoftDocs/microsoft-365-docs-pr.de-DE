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
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Anzeigen Microsoft 365 Benutzerkonten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können die Microsoft 365 Admin Center verwenden, um die Konten für Ihren Microsoft 365 Mandanten anzuzeigen. PowerShell für Microsoft 365 ermöglicht dies, bietet aber auch zusätzliche Funktionen.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365 Mandanten](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)her.
  
### <a name="view-all-accounts"></a>Alle Konten anzeigen

Führen Sie den folgenden Befehl aus, um die vollständige Liste der Benutzerkonten anzuzeigen:
  
```powershell
Get-AzureADUser
```

Sie sollten Informationen wie die folgende erhalten:
  
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

Führen Sie den folgenden Befehl aus, um ein bestimmtes Benutzerkonto anzuzeigen. Geben Sie den Anmeldekontonamen des Benutzerkontos ein, das auch als Benutzerprinzipalname (USER Principal Name, UPN) bezeichnet wird. Entfernen Sie die Zeichen "<" und ">".
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Hier ist ein Beispiel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Anzeigen zusätzlicher Eigenschaftswerte für ein bestimmtes Konto

Standardmäßig zeigt das Cmdlet **"Get-AzureADUser"** nur die Eigenschaften *ObjectID,* *DisplayName* und *UserPrincipalName* von Konten an.

Um die anzuzeigenden Eigenschaften selektiver zu gestalten, verwenden Sie das Cmdlet **"Select"** in Kombination mit dem Cmdlet **"Get-AzureADUser".** Um die beiden Cmdlets zu kombinieren, verwenden Sie das "pipe"-Zeichen ("|"), das Azure Active Directory PowerShell anweist, Graph die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden. Hier ist ein Beispielbefehl, der *displayName*, *Department* und *UsageLocation* für jedes Benutzerkonto anzeigt:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:
  
1. Rufen Sie alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).
    
1.  Zeigt nur den Benutzernamen, die Abteilung und den Verwendungsort an (**Wählen Sie DisplayName, Abteilung, UsageLocation** aus).
  
Um alle Eigenschaften für ein bestimmtes Benutzerkonto anzuzeigen, verwenden Sie das Cmdlet **"Select"** und das Platzhalterzeichen (*). Hier ist ein Beispiel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Führen Sie als weiteres Beispiel den folgenden Befehl aus, um den Aktiviertstatus eines bestimmten Benutzerkontos zu überprüfen:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-account-synchronization-status"></a>Anzeigen des Kontosynchronisierungsstatus

Benutzerkonten haben zwei Quellen: 

- Windows Server Active Directory (AD), bei denen es sich um Konten handelt, die von lokalem AD mit der Cloud synchronisiert werden.

- Azure Active Directory (Azure AD)-AD-Konten, die direkt in der Cloud erstellt werden.


Der folgende Befehl weist PowerShell an, alle Benutzer abzurufen, deren Attribut *DirSyncEnabled* auf *"True"* festgelegt ist. Sie können es verwenden, um Konten zu suchen, die von lokalem AD synchronisiert werden.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -eq $true}
```

Der folgende Befehl weist PowerShell an, alle Benutzer abzurufen, deren Attribut *DirSyncEnabled* auf False festgelegt *ist.* Sie können es verwenden, um nur cloudbasierte Konten zu finden.

```powershell
Get-AzureADUser | Where {$_.DirSyncEnabled -ne $false}
```

### <a name="view-accounts-based-on-a-common-property"></a>Anzeigen von Konten basierend auf einer allgemeinen Eigenschaft

Um die Liste der anzuzeigenden Konten selektiver zu gestalten, können Sie das Cmdlet **"Where"** in Kombination mit dem Cmdlet **"Get-AzureADUser"** verwenden. Um die beiden Cmdlets zu kombinieren, verwenden Sie das "pipe"-Zeichen ("|"), das Azure Active Directory PowerShell anweist, Graph die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden. Hier ist ein Beispielbefehl, der nur die Benutzerkonten anzeigt, die über einen nicht angegebenen Verwendungsort verfügen:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Mit diesem Befehl wird Azure Active Directory PowerShell angewiesen, folgende Graph auszuführen:
  
1. Rufen Sie alle Informationen zu den Benutzerkonten (**Get-AzureADUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).
    
1. Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungsort (**Wobei {$ \_ . UsageLocation -eq $Null}**). Innerhalb der geschweiften Klammern weist der Befehl PowerShell an, nur den Satz von Konten zu suchen, für die die UsageLocation-Benutzerkontoeigenschaft (**$ \_ . UsageLocation**) ist nicht angegeben (**-eq $Null**).
    
Die **UsageLocation**-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist. Um alle Eigenschaften für ein bestimmtes Benutzerkonto anzuzeigen, verwenden Sie das Cmdlet **"Select"** und das Platzhalterzeichen (*). Hier ist ein Beispiel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Das **City**-Objekt steht z. B. für den Namen einer Benutzerkontoeigenschaft. Mit dem folgenden Befehl können Sie alle Konten von Benutzern auflisten, die in London leben:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
> Die Syntax für das Cmdlet **"Where"** in diesen Beispielen lautet **Where {$ \_ .** [Name der Benutzerkontoeigenschaft] [Vergleichsoperator] [Wert] **}**.> [Vergleichsoperator] ist **-eq** für gleich, **-ne** für ungleich, **-lt** für kleiner als, **-gt** für größer als und andere.  [Wert] ist in der Regel eine Zeichenfolge (eine Abfolge von Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder **$Null** für nicht angegebene Zeichen. Weitere Informationen finden Sie unter [Where](/powershell/module/microsoft.powershell.core/where-object).

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365 Mandanten](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)her.

### <a name="view-all-accounts"></a>Alle Konten anzeigen

Führen Sie den folgenden Befehl aus, um die vollständige Liste der Benutzerkonten anzuzeigen:
  
```powershell
Get-MsolUser
```

>[!Note]
>Das Microsoft Azure Active Directory-Modul für Windows PowerShell-Modul und Cmdlets mit *Msol* im Namen werden von PowerShell Core nicht unterstützt. Führen Sie diese Cmdlets über Windows PowerShell aus.
>

Sie sollten Informationen wie die folgende erhalten:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Das **Get-MsolUser**-Cmdlet verfügt darüber hinaus über eine Reihe von Parametern zum Filtern der angezeigten Benutzerkonten. Führen Sie z. B. für die Liste der nicht lizenzierten Benutzer (Benutzer, die Microsoft 365 hinzugefügt wurden, aber noch nicht lizenziert wurden, um einen der Dienste zu verwenden) den folgenden Befehl aus:
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Sie sollten Informationen wie die folgende erhalten:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Weitere Informationen zu zusätzlichen Parametern zum Filtern der angezeigten Benutzerkonten finden Sie unter [Get-MsolUser](/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Anzeigen eines bestimmten Kontos

Führen Sie den folgenden Befehl aus, um ein bestimmtes Benutzerkonto anzuzeigen. Geben Sie den Anmeldenamen des Benutzerkontos ein, das auch als Benutzerprinzipalname (USER Principal Name, UPN) bezeichnet wird. Entfernen Sie die Zeichen "<" und ">".
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-accounts-based-on-a-common-property"></a>Anzeigen von Konten basierend auf einer allgemeinen Eigenschaft

Um die Liste der anzuzeigenden Konten selektiver zu gestalten, können Sie das Cmdlet **"Where"** in Kombination mit dem Cmdlet **"Get-MsolUser"** verwenden. Um die beiden Cmdlets zu kombinieren, verwenden Sie das "pipe"-Zeichen ("|"), das PowerShell anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden. Hier ist ein Beispiel, in dem nur die Benutzerkonten mit einem nicht angegebenen Verwendungsort angezeigt werden:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:
  
1. Rufen Sie alle Informationen zu den Benutzerkonten (**Get-MsolUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).
    
1. Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungsort (**Wobei {$ \_ . UsageLocation -eq $Null}**). Innerhalb der geschweiften Klammern weist der Befehl PowerShell an, nur den Satz von Konten zu suchen, für die die UsageLocation-Benutzerkontoeigenschaft (**$ \_ . UsageLocation**) ist nicht angegeben (**-eq $Null**).
    
Sie sollten Informationen wie die folgende erhalten:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

Die *UsageLocation*-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist. Um alle Eigenschaften für Benutzerkonten anzuzeigen, verwenden Sie das Cmdlet **"Select"** und das Platzhalterzeichen (*), um sie für ein bestimmtes Benutzerkonto anzuzeigen. Hier ist ein Beispiel:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Das *City*-Objekt steht z. B. für den Namen einer Benutzerkontoeigenschaft. Mit dem folgenden Befehl können Sie alle Benutzerkonten für Benutzer auflisten, die in London leben:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
> Die Syntax für das Cmdlet **"Where"** in diesen Beispielen lautet **Where {$ \_ .** [Name der Benutzerkontoeigenschaft] [Vergleichsoperator] [Wert] **}**.  [Vergleichsoperator] ist **-eq** für gleich, **-ne** für ungleich, **-lt** für kleiner als, **-gt** für größer als und andere.  [Wert] ist in der Regel eine Zeichenfolge (eine Abfolge von Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder **$Null** für nicht angegebene Zeichen. Weitere Informationen finden Sie unter [Where](/powershell/module/microsoft.powershell.core/where-object).
  
Verwenden Sie den folgenden Befehl, um den Sperrstatus eines Benutzerkontos zu überprüfen:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Anzeigen zusätzlicher Eigenschaftswerte für Konten

Standardmäßig zeigt das Cmdlet **"Get-MsolUser"** die folgenden drei Eigenschaften von Benutzerkonten an:
  
- UserPrincipalName

- DisplayName

- isLicensed

Wenn Sie zusätzliche Eigenschaften benötigen, z. B. die Abteilung, in der der Benutzer arbeitet, und das Land/die Region, in dem/der er Microsoft 365 Dienste verwendet, können Sie **Get-MsolUser** in Kombination mit **dem** Select-Cmdlet ausführen, um die Liste der Benutzerkontoeigenschaften anzugeben. Hier ist ein Beispiel:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:
  
1. Rufen Sie alle Informationen zu den Benutzerkonten (**Get-MsolUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).
    
1. Zeigt nur den Benutzernamen, die Abteilung und den Verwendungsort an (**Wählen Sie DisplayName, Abteilung, UsageLocation** aus).
    
Sie sollten Informationen wie die folgende erhalten:
  
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

Mit dem Cmdlet **"Auswählen"** können Sie auswählen, welche Eigenschaften angezeigt werden sollen. Um alle Eigenschaften für ein bestimmtes Benutzerkonto anzuzeigen, verwenden Sie das Platzhalterzeichen (*). Hier ist ein Beispiel:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Um die Liste der anzuzeigenden Konten selektiver zu gestalten, können Sie auch das Cmdlet **"Where"** verwenden. Hier ist ein Beispielbefehl, der nur die Benutzerkonten anzeigt, die über einen nicht angegebenen Verwendungsort verfügen:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Mit diesem Befehl wird PowerShell angewiesen, Folgendes zu tun:
  
1. Rufen Sie alle Informationen zu den Benutzerkonten (**Get-MsolUser**) ab, und senden Sie sie an den nächsten Befehl ( **|** ).
    
1. Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungsort (**Wobei {$ \_ . UsageLocation -eq $Null}**), und senden Sie die resultierenden Informationen an den nächsten Befehl ( **|** ). Innerhalb der geschweiften Klammern weist der Befehl PowerShell an, nur den Satz von Konten zu suchen, für die die UsageLocation-Benutzerkontoeigenschaft (**$ \_ . UsageLocation**) ist nicht angegeben (**-eq $Null**).
    
1. Zeigt nur den Benutzernamen, die Abteilung und den Verwendungsort an (**Wählen Sie DisplayName, Abteilung, UsageLocation** aus).
    
Sie sollten Informationen wie die folgende erhalten:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Wenn Sie die Verzeichnissynchronisierung verwenden, um Ihre Microsoft 365 Benutzer zu erstellen und zu verwalten, können Sie das lokale Konto anzeigen, aus dem ein Microsoft 365 Benutzer projiziert wurde. Im folgenden Beispiel wird davon ausgegangen, dass:

- Azure AD Verbinden ist so konfiguriert, dass der Standardquellanker von ObjectGUID verwendet wird. (Weitere Informationen zum Konfigurieren eines Quellankers finden Sie unter [Azure AD Verbinden: Designkonzepte).](/azure/active-directory/hybrid/plan-connect-design-concepts)
- Das Active Directory Domain Services-Modul für PowerShell wurde installiert (siehe [RSAT-Tools).](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Weitere Informationen:

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)