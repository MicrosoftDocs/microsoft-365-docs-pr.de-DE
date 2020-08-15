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
ms.openlocfilehash: ea631d12a95ca813ebf9da3286e36d724d51a2f7
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/14/2020
ms.locfileid: "46696033"
---
# <a name="view-microsoft-365-user-accounts-with-powershell"></a>Anzeigen von Microsoft 365-Benutzerkonten mit PowerShell

*Dieser Artikel gilt sowohl für Microsoft 365 Enterprise als auch für Office 365 Enterprise.*

Sie können zwar das Microsoft 365 Admin Center verwenden, um die Konten für Ihren Microsoft 365-Mandanten anzuzeigen, aber Sie können auch PowerShell für Microsoft 365 verwenden und einige Dinge tun, die das Admin Center nicht kann.
  
## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a>Verwenden der Azure Active Directory PowerShell für Graph-Module

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).
  
### <a name="view-all-accounts"></a>Alle Konten anzeigen

Um die vollständige Liste der Benutzerkonten anzuzeigen, führen Sie den folgenden Befehl aus:
  
```powershell
Get-AzureADUser
```

Es sollten Informationen ähnlich den folgenden angezeigt werden:
  
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

Um ein bestimmtes Benutzerkonto anzuzeigen, geben Sie den Anmeldekontonamen des Benutzerkontos ein, das auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet wird, entfernen Sie die Zeichen "<" und ">", und führen Sie den folgenden Befehl aus:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account>
```

Hier ein Beispiel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com
```

### <a name="view-additional-property-values-for-a-specific-account"></a>Anzeigen zusätzlicher Eigenschaftswerte für ein bestimmtes Konto

Standardmäßig zeigt das Cmdlet **Get-AzureADUser** nur die Eigenschaften ObjectID, DisplayName und userPrincipalName von Konten an.

Um die Liste der anzuzeigenden Eigenschaften selektiver zu machen, können Sie das Cmdlet **Select** in Kombination mit dem Cmdlet **Get-AzureADUser** verwenden. Um die beiden Cmdlets zu kombinieren, verwenden wir das "Pipe"-Zeichen "|", das Azure Active Directory PowerShell für Graph anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden. Es folgt ein Beispielbefehl, mit dem DisplayName, Department und UsageLocation für jedes Benutzerkonto angezeigt werden:
  
```powershell
Get-AzureADUser | Select DisplayName,Department,UsageLocation
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
- Alle Informationen der Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden (**|**).
    
- Zeigt nur den Namen des Benutzerkontos, die Abteilung und den Verwendungs Speicherort an ( **Wählen Sie DisplayName, Abteilung, UsageLocation** ).
  
Um alle Eigenschaften für Benutzerkonten anzuzeigen, verwenden Sie das **Select** -Cmdlet und das Platzhalterzeichen (*), um Sie alle für ein bestimmtes Benutzerkonto anzuzeigen. Hier ein Beispiel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

Als weiteres Beispiel können Sie den aktivierten Status eines bestimmten Benutzerkontos überprüfen, indem Sie den folgenden Befehl ausführen:
  
```powershell
Get-AzureADUser -ObjectID <sign-in name of the user account> | Select DisplayName,UserPrincipalName,AccountEnabled
```

### <a name="view-some-accounts-based-on-a-common-property"></a>Anzeigen einiger Konten basierend auf einer gemeinsamen Eigenschaft

Um die Liste der anzuzeigenden Konten selektiver zu machen, können Sie das Cmdlet **Where** in Kombination mit dem Cmdlet **Get-AzureADUser** verwenden. Um die beiden Cmdlets zu kombinieren, verwenden wir das "Pipe"-Zeichen "|", das Azure Active Directory PowerShell für Graph anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden. Nachfolgend ist ein Beispielbefehl aufgeführt, mit dem nur die Benutzerkonten angezeigt werden, die über einen nicht angegebenen Verwendungsstandort verfügen:
  
```powershell
Get-AzureADUser | Where {$_.UsageLocation -eq $Null}
```

Dieser Befehl weist Azure Active Directory PowerShell für Graph Folgendes zu:
  
- Alle Informationen der Benutzerkonten abrufen (**Get-AzureADUser**) und an den nächsten Befehl senden (**|**).
    
- Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungs Speicherort ( **wobei {$ \_ . UsageLocation-EQ $NULL}** ). In den geschweiften Klammern weist der Befehl PowerShell an, nur den kontensatz zu finden, in dem die UsageLocation-Benutzerkonto Eigenschaft ( ** $ \_ . UsageLocation** ) ist nicht angegeben ( **-EQ $NULL** ).
    
Die **UsageLocation**-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist. Um alle Eigenschaften für Benutzerkonten anzuzeigen, verwenden Sie das **Select** -Cmdlet und das Platzhalterzeichen (*), um Sie alle für ein bestimmtes Benutzerkonto anzuzeigen. Hier ein Beispiel:
  
```powershell
Get-AzureADUser -ObjectID BelindaN@litwareinc.onmicosoft.com | Select *
```

In dieser Liste steht das **City**-Objekt für den Namen einer Benutzerkontoeigenschaft. Dies bedeutet, dass Sie mit dem folgenden Befehl eine Liste aller Benutzerkonten für Benutzer, die in London leben, anzeigen können:
  
```powershell
Get-AzureADUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Die Syntax für das in diesen Beispielen dargestellte Cmdlet **Where** ist **{$ \_ .** [Name der Benutzerkonten Eigenschaft] [Vergleichsoperator] Wert **}**. > [Vergleichsoperator] ist **-EQ** für gleich, **-ne** für ungleich, **-lt** für kleiner als, **-gt** für größer als und andere.  [value] ist normalerweise eine Zeichenfolge (eine Sequenz von Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder **$null** für Unspecified> siehe [Where](https://docs.microsoft.com/powershell/module/Microsoft.PowerShell.Core/Where?view=powershell-5.1) für weitere Informationen.
  

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a>Verwenden des Microsoft Azure Active Directory-Moduls für Windows PowerShell

Stellen Sie zunächst [eine Verbindung mit Ihrem Microsoft 365-Mandanten her](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).

### <a name="view-all-accounts"></a>Alle Konten anzeigen

Um die vollständige Liste der Benutzerkonten anzuzeigen, führen Sie den folgenden Befehl aus:
  
```powershell
Get-MsolUser
```

>[!Note]
>PowerShell Core unterstützt nicht das Microsoft Azure Active Directory-Modul für Windows PowerShell und Cmdlets mit **Msol** im Namen. Um diese Cmdlets weiterhin verwenden zu können, müssen Sie sie über Windows PowerShell ausführen.
>

Es sollten Informationen ähnlich den folgenden angezeigt werden:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BonnieK@litwareinc.onmicrosoft.com    Bonnie Kearney        True
FabriceC@litwareinc.onmicrosoft.com   Fabrice Canel         True
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
AnneWlitwareinc.onmicrosoft.com       Anne Wallace          True
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Das **Get-MsolUser**-Cmdlet verfügt darüber hinaus über eine Reihe von Parametern zum Filtern der angezeigten Benutzerkonten. Führen Sie diesen Befehl beispielsweise für die Liste der nicht lizenzierten Benutzer (Benutzer, die Microsoft 365 hinzugefügt wurden, aber noch nicht für die Verwendung eines der Dienste lizenziert wurden) aus.
  
```powershell
Get-MsolUser -UnlicensedUsersOnly
```

Es sollten Informationen ähnlich den folgenden angezeigt werden:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False
```

Weitere Informationen zu zusätzlichen Parametern zum Filtern des angezeigten Satzes von Benutzerkonten finden Sie unter [Get-MsolUser](https://docs.microsoft.com/previous-versions/azure/dn194133(v=azure.100)).
  
### <a name="view-a-specific-account"></a>Anzeigen eines bestimmten Kontos

Um ein bestimmtes Benutzerkonto anzuzeigen, geben Sie den Anmeldenamen des Benutzerkontos des Benutzerkontos ein, das auch als Benutzerprinzipalname (User Principal Name, UPN) bezeichnet wird, entfernen Sie die Zeichen "<" und ">", und führen Sie den folgenden Befehl aus:
  
```powershell
Get-MsolUser -UserPrincipalName <sign-in name of the user account>
```

### <a name="view-some-accounts-based-on-a-common-property"></a>Anzeigen einiger Konten basierend auf einer gemeinsamen Eigenschaft

Um die Liste der anzuzeigenden Konten selektiver zu machen, können Sie das Cmdlet **Where** in Kombination mit dem Cmdlet **Get-MsolUser** verwenden. Um die beiden Cmdlets zu kombinieren, verwenden wir das "Pipe"-Zeichen "|", das PowerShell anweist, die Ergebnisse eines Befehls zu übernehmen und an den nächsten Befehl zu senden. Nachfolgend ist ein Beispielbefehl aufgeführt, mit dem nur die Benutzerkonten angezeigt werden, die über einen nicht angegebenen Verwendungsstandort verfügen:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null}
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
- Alle Informationen der Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden (**|**).
    
- Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungs Speicherort ( **wobei {$ \_ . UsageLocation-EQ $NULL}** ). In den geschweiften Klammern weist der Befehl PowerShell an, nur den kontensatz zu finden, in dem die UsageLocation-Benutzerkonto Eigenschaft ( ** $ \_ . UsageLocation** ) ist nicht angegeben ( **-EQ $NULL** ).
    
Es sollten Informationen ähnlich den folgenden angezeigt werden:
  
```powershell
UserPrincipalName                     DisplayName           isLicensed
-----------------                     -----------           ----------
BrianJ@litwareinc.onmicrosoft.com     Brian Johnson         False 
ScottW@litwareinc.onmicrosoft.com     Scott Wallace         False

```

Die **UsageLocation**-Eigenschaft ist nur eine von vielen Eigenschaften, die einem Benutzerkonto zugeordnet ist. Um alle Eigenschaften für Benutzerkonten anzuzeigen, verwenden Sie das **Select** -Cmdlet und das Platzhalterzeichen (*), um Sie alle für ein bestimmtes Benutzerkonto anzuzeigen. Hier ein Beispiel:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

In dieser Liste steht das **City**-Objekt für den Namen einer Benutzerkontoeigenschaft. Dies bedeutet, dass Sie mit dem folgenden Befehl eine Liste aller Benutzerkonten für Benutzer, die in London leben, anzeigen können:
  
```powershell
Get-MsolUser | Where {$_.City -eq "London"}
```

> [!TIP]
>  Die Syntax für das in diesen Beispielen dargestellte Cmdlet **Where** ist **{$ \_ .** [Name der Benutzerkonten Eigenschaft] [Vergleichsoperator] Wert **}**.  [Vergleichsoperator] is **-EQ** für gleich, **-ne** für ungleich, **-lt** für kleiner als, **-gt** für größer als und andere.  [value] ist normalerweise eine Zeichenfolge (eine Sequenz von Buchstaben, Zahlen und anderen Zeichen), ein numerischer Wert oder **$null** für Unspecified. Weitere Informationen finden Sie unter [Where](https://technet.microsoft.com/library/hh849715.aspx) for more.
  
Sie können den blockierten Status eines Benutzerkontos überprüfen, indem Sie den folgenden Befehl ausführen:
  
```powershell
Get-MsolUser -UserPrincipalName <UPN of user account> | Select DisplayName,BlockCredential
```

### <a name="view-additional-property-values-for-accounts"></a>Anzeigen zusätzlicher Eigenschaftswerte für Konten

Das Cmdlet **Get-MsolUser** zeigt standardmäßig drei Eigenschaften von Benutzerkonten an:
  
- UserPrincipalName
    
- DisplayName
    
- isLicensed
    
Wenn Sie zusätzliche Eigenschaften benötigen, beispielsweise die Abteilung, für die der Benutzer arbeitet, und das Land/die Region, in der der Benutzer Microsoft 365-Dienste verwendet, können Sie **Get-MsolUser** in Kombination mit dem **Select** -Cmdlet ausführen, um die Liste der Benutzerkontoeigenschaften anzugeben. Hier ein Beispiel:
  
```powershell
Get-MsolUser | Select DisplayName, Department, UsageLocation
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
- Alle Informationen der Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden (**|**).
    
- Zeigt nur den Namen des Benutzerkontos, die Abteilung und den Verwendungs Speicherort an ( **Wählen Sie DisplayName, Abteilung, UsageLocation** ).
    
Es sollten Informationen ähnlich den folgenden angezeigt werden:
  
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

Mit dem Cmdlet **"Select** " können Sie die Eigenschaften auswählen, die ein Befehl angezeigt werden soll. Wenn Sie alle Eigenschaften für Benutzerkonten anzeigen möchten, verwenden Sie das Platzhalterzeichen (*), um Sie alle für ein bestimmtes Benutzerkonto anzuzeigen. Hier ein Beispiel:
  
```powershell
Get-MsolUser -UserPrincipalName BelindaN@litwareinc.onmicosoft.com | Select *
```

Um die Liste der anzuzeigenden Konten selektiver anzuzeigen, können Sie auch das Cmdlet " **Where** " verwenden. Nachfolgend ist ein Beispielbefehl aufgeführt, mit dem nur die Benutzerkonten angezeigt werden, die über einen nicht angegebenen Verwendungsstandort verfügen:
  
```powershell
Get-MsolUser | Where {$_.UsageLocation -eq $Null} | Select DisplayName, Department, UsageLocation
```

Mit diesem Befehl wird PowerShell an Folgendes angewiesen:
  
- Alle Informationen der Benutzerkonten abrufen (**Get-MsolUser**) und an den nächsten Befehl senden (**|**).
    
- Suchen Sie alle Benutzerkonten mit einem nicht angegebenen Verwendungs Speicherort ( **wobei {$ \_ . UsageLocation-EQ $NULL}** ) und die resultierenden Informationen an den nächsten Befehl senden ( **|** ). Innerhalb der geschweiften Klammern weist der Befehl PowerShell an, nur den kontensatz zu finden, in dem die UsageLocation-Benutzerkonto Eigenschaft ( ** $ \_ . UsageLocation** ) ist nicht angegeben ( **-EQ $NULL** ).
    
- Zeigt nur den Namen des Benutzerkontos, die Abteilung und den Verwendungs Speicherort an ( **Wählen Sie DisplayName, Abteilung, UsageLocation** ).
    
Es sollten Informationen ähnlich den folgenden angezeigt werden:
  
```powershell
DisplayName              Department                      UsageLocation
-----------              ----------                      -------------
Brian Johnson 
Scott Wallace            Operations
```

Wenn Sie die Verzeichnissynchronisierung zum Erstellen und Verwalten Ihrer Microsoft 365-Benutzer verwenden, können Sie das lokale Konto anzeigen, aus dem ein Microsoft 365-Benutzer projiziert wurde. Im folgenden wird davon ausgegangen, dass Azure AD Connect für die Verwendung des Standard Quell Ankers von objectGUID konfiguriert ist (Weitere Informationen zum Konfigurieren eines Quell Ankers finden Sie unter [Azure AD Connect: Design Concepts](https://docs.microsoft.com/azure/active-directory/hybrid/plan-connect-design-concepts)), und es wird davon ausgegangen, dass das Active Directory-Domänendienste Modul für PowerShell installiert wurde (siehe Tools für die [Remoteverwaltung](https://www.microsoft.com/en-gb/download/details.aspx?id=45520)):

```powershell
Get-ADUser ([guid][System.Convert]::FromBase64String((Get-MsolUser -UserPrincipalName <UPN of user account>).ImmutableID)).guid
```

## <a name="see-also"></a>Siehe auch

[Verwalten von Microsoft 365-Benutzerkonten, -Lizenzen und -Gruppen mit PowerShell](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[Verwalten von Microsoft 365 mit PowerShell](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[Erste Schritte mit PowerShell für Microsoft 365](getting-started-with-microsoft-365-powershell.md)

