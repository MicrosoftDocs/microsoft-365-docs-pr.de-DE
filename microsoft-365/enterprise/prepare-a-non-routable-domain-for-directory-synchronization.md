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
description: Erfahren Sie, was Sie tun müssen, wenn Ihren lokalen Benutzerkonten eine nicht routingfähige Domäne zugeordnet ist, bevor Sie sie mit Ihrem Microsoft 365-Mandanten synchronisieren.
ms.openlocfilehash: dcd941bbae159afeb0cf6ef4f5acbaf409966295
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780332"
---
# <a name="prepare-a-non-routable-domain-for-directory-synchronization"></a>Vorbereiten einer nicht routingfähigen Domäne für die Verzeichnissynchronisierung

Wenn Sie Ihr lokales Verzeichnis mit Microsoft 365 synchronisieren, müssen Sie über eine überprüfte Domäne in Azure Active Directory (Azure AD) verfügen. Es werden nur die Benutzerprinzipalnamen (User Principal Names, UPNs) synchronisiert, die der lokalen AD DS (Active Directory Domain Services)-Domäne zugeordnet sind. Jeder UPN, der eine nicht routingfähige Domäne enthält, z. B. ".local" (Beispiel: billa@contoso.local), wird jedoch mit einer .onmicrosoft.com-Domäne synchronisiert (Beispiel: billa@contoso.onmicrosoft.com). 

Wenn Sie derzeit eine ".local"-Domäne für Ihre Benutzerkonten in AD DS verwenden, wird empfohlen, sie so zu ändern, dass sie eine überprüfte Domäne wie billa@contoso.com verwenden, um eine ordnungsgemäßen Synchronisierung mit Ihrer Microsoft 365-Domäne zu gewährleisten.
  
## <a name="what-if-i-only-have-a-local-on-premises-domain"></a>Was passiert, wenn ich nur eine lokale Domäne ".local" habe?

Sie verwenden Azure AD Connect für die Synchronisierung Ihres AD DS mit dem Azure AD-Mandanten Ihres Microsoft 365-Mandanten. Weitere Informationen finden Sie unter [Integrieren Ihrer lokalen Identitäten in Azure AD.](https://docs.microsoft.com/azure/architecture/reference-architectures/identity/azure-ad)
  
Azure AD Connect synchronisiert den UPN und das Kennwort Ihrer Benutzer, sodass benutzer sich mit denselben Anmeldeinformationen anmelden können, die sie lokal verwenden. Azure AD Connect synchronisiert jedoch nur Benutzer mit Domänen, die von Microsoft 365 überprüft werden. Dies bedeutet, dass die Domäne auch von Azure AD überprüft wird, da Microsoft 365-Identitäten von Azure AD verwaltet werden. Anders ausgedrückt, muss die Domäne eine gültige Internetdomäne sein (z. B. .com, .org, .net, .us). Wenn Ihr interner AD DS nur eine nicht routingfähige Domäne verwendet (z. B. ".local"), kann dies möglicherweise nicht mit der überprüften Domäne übereinstimmen, die Sie für Ihren Microsoft 365-Mandanten haben. Sie können dieses Problem beheben, indem Sie entweder Ihre primäre Domäne in Ihrem lokalen AD DS ändern oder ein oder mehrere UPN-Suffixe hinzufügen.
  
### <a name="change-your-primary-domain"></a>Ändern Ihrer primären Domäne

Ändern Sie Ihre primäre Domäne in eine Domäne, die Sie in Microsoft 365 überprüft haben, z. B. contoso.com. Jeder Benutzer mit der Domäne "contoso.local" wird dann auf contoso.com. Dies ist jedoch ein sehr beteiligter Prozess, und im folgenden Abschnitt wird eine einfachere Lösung beschrieben.
  
### <a name="add-upn-suffixes-and-update-your-users-to-them"></a>Hinzufügen von UPN-Suffixen und Aktualisieren der Benutzer

Sie können das Problem ".local" lösen, indem Sie neue UPN-Suffixe oder Suffixe in AD DS registrieren, um mit der Domäne (oder den Domänen) zu übereinstimmen, die Sie in Microsoft 365 überprüft haben. Nachdem Sie das neue Suffix registriert haben, aktualisieren Sie die Benutzer-UPNs, um beispielsweise die Datei ".local" durch den neuen Domänennamen zu ersetzen, sodass ein Benutzerkonto wie ein billa@contoso.com.
  
Nachdem Sie die UPNs für die Verwendung der überprüften Domäne aktualisiert haben, können Sie Ihre lokalen AD DS mit Microsoft 365 synchronisieren.
  
#### <a name="step-1-add-the-new-upn-suffix"></a>Schritt 1: Hinzufügen des neuen UPN-Suffixes**
  
1. On the AD DS domain controller, in the Server Manager choose **Tools** \> **Active Directory Domains and Trusts**.
    
    **Oder wenn Sie keine Windows Server 2012**
    
    Drücken **Sie die Windows-TASTE + R,** um das Dialogfeld "Ausführen" zu öffnen, geben Sie "Domain.msc" ein, und wählen Sie dann OK **aus.** 
    
    ![Wählen Sie Active Directory Domains and Trusts aus.](../media/46b6e007-9741-44af-8517-6f682e0ac974.png)
  
2. Klicken Sie **im Fenster "Active Directory-Domänen** und -Vertrauensstellungen" mit der rechten Maustaste auf **Active Directory-Domänen** und -Vertrauensstellungen, und wählen Sie dann **"Eigenschaften" aus.**
    
    ![Klicken Sie mit der rechten Maustaste auf Active Directory-Domänen und -Vertrauensstellungen, und wählen Sie "Eigenschaften" aus.](../media/39d20812-ffb5-4ba9-8d7b-477377ac360d.png)
  
3. Geben Sie auf der Registerkarte **"UPN-Suffixe"** im Feld **"Alternative UPN-Suffixe"** Ihr neues UpN-Suffix oder die neuen Suffixe ein, und wählen Sie dann "Übernehmen"  \> **aus.**
    
    ![Hinzufügen eines neuen UPN-Suffixes](../media/a4aaf919-7adf-469a-b93f-83ef284c0915.PNG)
  
    Wählen **Sie "OK"** aus, wenn Sie mit dem Hinzufügen von Suffixen fertig sind. 
    
 #### <a name="step-2-change-the-upn-suffix-for-existing-users"></a>Schritt 2: Ändern des Suffixes "UPN" für vorhandene Benutzer
  
1. Wählen Sie auf dem AD DS-Domänencontroller im Server-Manager **"Extras** \> **Active Directory-Benutzer und -Computer" aus.**
    
    **Oder wenn Sie keine Windows Server 2012**
    
    Drücken **Sie die Windows-TASTE + R,** um das Dialogfeld "Ausführen" zu öffnen, geben Sie "Dsa.msc" ein, und klicken Sie dann auf **"OK".** 
    
2. Wählen Sie einen Benutzer aus, klicken Sie mit der rechten Maustaste, und wählen Sie dann **"Eigenschaften" aus.**
    
3. Wählen Sie **auf der** Registerkarte "Konto" in der Dropdownliste "UPN-Suffix" das neue Benutzernamensuffix aus, und klicken Sie dann auf **"OK".**
    
    ![Hinzufügen eines neuen Benutzer-UPN-Suffixes](../media/54876751-49f0-48cc-b864-2623c4835563.png)
  
4. Führen Sie diese Schritte für jeden Benutzer aus.
    
   
### <a name="use-powershell-to-change-the-upn-suffix-for-all-of-your-users"></a>Verwenden von PowerShell zum Ändern des Benutzernamensuffixes für alle Benutzer

Wenn Viele Benutzerkonten aktualisiert werden müssen, ist die Verwendung von PowerShell einfacher. Im folgenden Beispiel werden die Cmdlets ["Get-ADUser"](https://go.microsoft.com/fwlink/p/?LinkId=624312) und ["Set-ADUser"](https://go.microsoft.com/fwlink/p/?LinkId=624313) verwendet, um alle Contoso.local-Suffixe in contoso.com AD DS zu ändern. 

Sie können beispielsweise die folgenden PowerShell-Befehle ausführen, um alle Contoso.local-Suffixe auf contoso.com:
    
  ```powershell
  $LocalUsers = Get-ADUser -Filter "UserPrincipalName -like '*contoso.local'" -Properties userPrincipalName -ResultSetSize $null
  $LocalUsers | foreach {$newUpn = $_.UserPrincipalName.Replace("@contoso.local","@contoso.com"); $_ | Set-ADUser -UserPrincipalName $newUpn}
  ```

Weitere [Informationen zur Verwendung von Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=624314) in AD DS finden Sie Windows PowerShell Active Directory-Modul. 

