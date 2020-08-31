---
title: Verwalten einer isolierten SharePoint Online-Teamwebsite
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: Verwalten einer isolierten SharePoint Online Teamwebsite, Hinzufügen neuer Benutzer und Gruppen, Entfernen von Benutzern und Gruppen und Erstellen eines Dokuments Unterordners mit benutzerdefinierten Berechtigungen.
ms.openlocfilehash: d66f9a349bd5834d07fbc13146127bde522923e4
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/29/2020
ms.locfileid: "47308267"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a>Verwalten einer isolierten SharePoint Online-Teamwebsite

 **Zusammenfassung:** Mit diesen Verfahren können Sie Ihre isolierte SharePoint Online-Teamwebsite verwalten.
  
In diesem Artikel werden allgemeine Verwaltungsaufgaben für eine isolierte SharePoint Online-Teamwebsite erläutert.
  
## <a name="add-a-new-user"></a>Hinzufügen eines neuen Benutzers

Wenn ein neuer Benutzer der Website beitritt, müssen Sie entscheiden, in welchem Umfang, d. h. mit welcher Berechtigungsstufe, er an der Website teilnehmen soll:
  
- Verwaltung: Fügen Sie das neue Benutzerkonto zur Zugriffsgruppe der Websiteadministratoren hinzu.
    
- Aktive Zusammenarbeit: Fügen Sie das Benutzerkonto zur Zugriffsgruppe der Websitemitglieder hinzu.
    
- Anzeige: Fügen Sie das Benutzerkonto zur Zugriffsgruppe der Websitebetrachter hinzu.
    
Wenn Sie Benutzerkonten und Gruppen über Active Directory-Domänendienste (AD DS) verwalten, fügen Sie die entsprechenden Benutzer den entsprechenden Zugriffsgruppen mithilfe der normalen AD DS Benutzer-und Gruppen Verwaltungsverfahren hinzu, und warten Sie, bis die Synchronisierung mit Ihrem Abonnement erfolgt ist.
  
Wenn Sie Benutzerkonten und Gruppen über Microsoft 365 verwalten, können Sie das Microsoft 365 Admin Center oder Microsoft PowerShell verwenden:
  
- Melden Sie sich für das Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkonto Administrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen, um die entsprechenden Benutzer den entsprechenden Zugriffsgruppen hinzuzufügen.
    
- Stellen Sie für PowerShell zunächst [eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul her](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module). Verwenden Sie den folgenden PowerShell-Befehlsblock, um ein Benutzerkonto unter Verwendung des Benutzerprinzipalnamens (User Principal Name, UPN) zu einer Zugriffsgruppe hinzuzufügen:
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Verwenden Sie den folgenden PowerShell-Befehlsblock, um ein Benutzerkonto unter Verwendung des Anzeigenamens zu einer Zugriffsgruppe hinzuzufügen:

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a>Hinzufügen einer neuen Gruppe

Wenn Sie Zugriff für eine ganze Gruppe hinzufügen möchten, müssen Sie entscheiden, in welchem Umfang, d. h. mit welcher Berechtigungsstufe, sämtliche Mitglieder der Gruppe an der Website teilnehmen sollen:
  
- Verwaltung: Fügen Sie die Gruppe zur Zugriffsgruppe der Websiteadministratoren hinzu.
    
- Aktive Zusammenarbeit: Fügen Sie die Gruppe zur Zugriffsgruppe der Websitemitglieder hinzu.
    
- Anzeige: Fügen Sie die Gruppe zur Zugriffsgruppe der Websitbetrachter hinzu.
    
Wenn Sie Benutzerkonten und Gruppen über AD DS verwalten, fügen Sie die entsprechenden Gruppen mithilfe der normalen AD DS Benutzer-und Gruppen Verwaltungsverfahren zu den entsprechenden Gruppen hinzu, und warten Sie, bis die Synchronisierung mit Ihrem Abonnement erfolgt ist.
  
Wenn Sie Benutzerkonten und Gruppen über Office 365 verwalten, können Sie das Microsoft 365 Admin Center oder PowerShell verwenden:
  
- Melden Sie sich für das Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkonto Administrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen zum Hinzufügen der entsprechenden Gruppen zu den entsprechenden Zugriffsgruppen.
    
- Stellen Sie für PowerShell zunächst [eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul her](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
 Führen Sie dann die folgenden PowerShell-Befehle aus:
 
```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a>Entfernen eines Benutzers

Wenn der Zugriff auf eine Website für einen Benutzer entfernt werden muss, entfernen Sie den betreffenden Benutzer aus der Zugriffsgruppe, in der er derzeit basierend auf dem Umfang seiner Teilnahme an der Website Mitglied ist:
  
- Verwaltung: Entfernen Sie das Benutzerkonto aus der Zugriffsgruppe der Websiteadministratoren.
    
- Aktive Zusammenarbeit: Entfernen Sie das Benutzerkonto aus der Zugriffsgruppe der Websitemitglieder.
    
- Anzeige: Entfernen Sie das Benutzerkonto aus der Zugriffsgruppe der Websitebetrachter.
    
Wenn Sie Benutzerkonten und Gruppen über AD DS verwalten, entfernen Sie die entsprechenden Benutzer aus den entsprechenden Zugriffsgruppen mithilfe ihrer normalen AD DS Benutzer-und Gruppen Verwaltungsverfahren, und warten Sie, bis die Synchronisierung mit Ihrem Abonnement erfolgt ist.
  
Wenn Sie Benutzerkonten und Gruppen über Office 365 verwalten, können Sie das Microsoft 365 Admin Center oder PowerShell verwenden:
  
- Melden Sie sich für das Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkonto Administrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen, um die entsprechenden Benutzer aus den entsprechenden Zugriffsgruppen zu entfernen.
    
- Stellen Sie für PowerShell zunächst [eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul her](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).
Verwenden Sie den folgenden PowerShell-Befehlsblock, um ein Benutzerkonto unter Verwendung des UPN aus einer Zugriffsgruppe zu entfernen:
    
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

Verwenden Sie den folgenden PowerShell-Befehlsblock, um ein Benutzerkonto unter Verwendung des Anzeigenamens aus einer Zugriffsgruppe zu entfernen:
    
```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a>Entfernen einer Gruppe

Wenn der Zugriff für eine ganze Gruppe entfernt werden soll, entfernen Sie die betreffende Gruppe aus der Zugriffsgruppe, in der sie derzeit basierend auf dem Umfang ihrer Teilnahme an der Website Mitglied ist:
  
- Verwaltung: Entfernen Sie die Gruppe aus der Zugriffsgruppe der Websiteadministratoren.
    
- Aktive Zusammenarbeit: Entfernen Sie die Gruppe aus der Zugriffsgruppe der Websitemitglieder.
    
- Anzeige: Entfernen Sie die Gruppe aus der Zugriffsgruppe der Websitebetrachter.
    
Wenn Sie Benutzerkonten und Gruppen über Windows Server Active Directory verwalten, entfernen Sie die entsprechenden Gruppen aus den entsprechenden Zugriffsgruppen mithilfe ihrer normalen AD DS Benutzer-und Gruppen Verwaltungsverfahren, und warten Sie auf die Synchronisierung mit Ihrem Abonnement.
  
Wenn Sie Benutzerkonten und Gruppen über Office 365 verwalten, können Sie das Microsoft 365 Admin Center oder PowerShell verwenden:
  
- Melden Sie sich für das Microsoft 365 Admin Center mit einem Benutzerkonto an, dem die Rolle "Benutzerkonto Administrator" oder "Unternehmensadministrator" zugewiesen wurde, und verwenden Sie Gruppen, um die entsprechenden Gruppen aus den entsprechenden Zugriffsgruppen zu entfernen.
    
- Stellen Sie für PowerShell zunächst [eine Verbindung mit dem Azure Active Directory PowerShell for Graph-Modul her](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).    
Verwenden Sie den folgenden PowerShell-Befehlsblock, um eine Gruppe unter Verwendung des Anzeigenamens aus einer Zugriffsgruppe zu entfernen:
    
```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a>Erstellen eines Dokumentunterordners mit benutzerdefinierten Berechtigungen

In manchen Fällen benötigt eine Teilmenge der Personen, die innerhalb der isolierten Website arbeiten, einen privateren Ort für die Zusammenarbeit. Für SharePoint Online-Websites können Sie einen Unterordner im Dokumentordner der Website erstellen und benutzerdefinierte Berechtigungen zuweisen. Benutzer ohne Berechtigungen können den Unterordner nicht sehen.
  
Gehen Sie zum Erstellen eines Dokumentunterordners mit benutzerdefinierten Berechtigungen folgendermaßen vor:
  
1. Melden Sie sich bei einem Konto an, das Mitglied der Zugriffsgruppe "Administratoren" für die Website ist. Hilfe finden Sie unter [Where to sign in to Microsoft 365 (Wo kann ich mich bei Microsoft 365 anmelden?)](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).
    
2. Wechseln Sie zu der isolierten Teamwebsite, und klicken Sie auf **Dokumente**.
    
3. Navigieren Sie zu dem Ordner im Dokumentordner, der den Unterordner mit benutzerdefinierten Berechtigungen enthalten soll, erstellen Sie den Ordner, und öffnen Sie ihn.
    
4. Klicken Sie auf **Freigeben**.
    
5. Klicken Sie auf **Freigegeben für > Erweitert**.
    
6. Klicken Sie auf **Berechtigungsvererbung beenden**, und klicken Sie dann auf **OK**.
    
7. Klicken Sie auf **Freigeben**.
    
8. Klicken Sie auf **Freigegeben für > Erweitert**.
    
9. Klicken Sie auf **Berechtigungen erteilen > Freigegeben für > Erweitert**.
    
10. Klicken Sie auf der Berechtigungsseite auf **Mitglieder von \<site name>** in der Liste.
    
11. Aktivieren Sie auf der Seite **Mitglieder von \<site name>** das Kontrollkästchen neben der Zugriffsgruppe der Websitemitglieder, klicken Sie auf **Aktionen**, klicken Sie auf **Benutzer aus Gruppe entfernen**, und klicken Sie dann auf **OK**.
    
12. Um diesem Unterordner bestimmte Mitglieder hinzuzufügen, klicken Sie auf **Neu > Benutzer hinzufügen**.
    
13. Geben Sie im Dialogfeld **Freigeben** die Namen der Benutzerkonten ein, die an Dateien im Unterordner zusammenarbeiten können, und klicken Sie dann auf **Freigeben**.
    
14. Aktualisieren Sie die Webseite, um die neuen Ergebnisse anzuzeigen.
    
15. Klicken Sie im linken Navigationsbereich unter **Gruppen** auf die Gruppe **Besucher von \<site name>**, und führen Sie die Schritte 11 bis 14 aus, um den Satz der Benutzerkonten anzugeben, die die Dateien im Unterordner anzeigen können (nach Bedarf).
    
16. Klicken Sie im linken Navigationsbereich unter **Gruppen** auf die Gruppe **Besitzer von \<site name>**, und führen Sie die Schritte 11 bis 14 aus, um den Satz der Benutzerkonten anzugeben, die die Berechtigungen im Unterordner verwalten können (nach Bedarf).
    
17. Schließen Sie die Registerkarte **Benutzer und Gruppen** im Browser.
    
## <a name="see-also"></a>Siehe auch

[Isolierte SharePoint Online-Teamwebsites](isolated-sharepoint-online-team-sites.md)
  
[Entwerfen einer isolierten SharePoint Online-Teamwebsite](design-an-isolated-sharepoint-online-team-site.md)

[Bereitstellen einer isolierten SharePoint Online-Teamwebsite](deploy-an-isolated-sharepoint-online-team-site.md)



