---
title: Verwalten von Add-Ins im Admin Center
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Erfahren Sie mehr über die Verwendung zentralisierter Add-Ins zum Bereitstellen von Add-Ins für Benutzer und Gruppen in Ihrer Organisation.
ms.openlocfilehash: ed9086c77cdf10435bae09f76493af6058d2d758
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314387"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Verwalten von Add-Ins im Admin Center

Office-Add-Ins helfen Ihnen, Ihre Dokumente zu personalisieren und den Zugriff auf Informationen im Web zu optimieren (siehe [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). 

Nachdem ein Administrator Add-Ins für Benutzer in einer Organisation bereitgestellt hat, kann der Administrator Add-Ins deaktivieren oder aktivieren, bearbeiten, löschen und den Zugriff auf die Add-Ins verwalten.

Weitere Informationen zum Installieren von Add-Ins aus dem Admin Center finden Sie unter [Bereitstellen von Add-Ins im Admin Center.](./manage-deployment-of-add-ins.md)
  
## <a name="add-in-states"></a>Add-In-Status

Ein Add-In kann den Status **"Ein"** oder **"Aus"** aufweisen.
  
| Status | Auftreten des Status | Auswirkung |
|:-----|:-----|:-----|
|**Aktiv**  <br/> |Der Administrator hat das Add-In hochgeladen und benutzern oder Gruppen zugewiesen.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen sehen es im jeweiligen Client.  <br/> |
|**Deaktiviert**  <br/> |Der Administrator hat das Add-In deaktiviert.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr auf das Add-In zugreifen.  <br/> Wenn der Zustand des Add-Ins in "Aktiv" geändert wird, können die Benutzer und Gruppen wieder darauf zugreifen.  <br/> |
|**Gelöscht**  <br/> |Der Administrator hat das Add-In gelöscht.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr darauf zugreifen.  <br/> |
   
Erwägen Sie das Löschen eines Add-Ins, wenn es nicht mehr verwendet wird. Beispielsweise kann das Deaktivieren eines Add-Ins sinnvoll sein, wenn ein Add-In nur zu bestimmten Zeiten des Jahres verwendet wird.

## <a name="delete-an-add-in"></a>Löschen eines Add-Ins

Sie können auch ein Add-In löschen, das bereitgestellt wurde.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen**  >  **Dienste & Add-Ins.**

    > [!NOTE]
    > Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert. Wenn die oben beschriebenen Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt "Zentrale Bereitstellung", indem Sie zu **Einstellungen**  >  **integrierten Apps** wechseln. Wählen Sie oben auf der Seite **"Integrierte Apps"** die Option **"Add-Ins" aus.**

2. Wählen Sie das bereitgestellte Add-In aus.

3. Klicken Sie auf **"Add-In löschen".** Entfernen Sie die Add-In-Schaltfläche in der unteren rechten Ecke.

4. Überprüfen Sie Ihre Auswahl und wählen Sie **Add-In entfernen** aus.

## <a name="edit-add-in-access"></a>Bearbeiten des Add-In-Zugangs

Nach der Bereitstellung können Administratoren auch den Benutzerzugriff auf Add-Ins verwalten.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen**  >  **Dienste & Add-Ins.**

    > [!NOTE]
    > Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert. Wenn die oben beschriebenen Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt "Zentrale Bereitstellung", indem Sie zu **Einstellungen**  >  **integrierten Apps** wechseln. Wählen Sie oben auf der Seite **"Integrierte Apps"** die Option **"Add-Ins" aus.**

2. Wählen Sie das bereitgestellte Add-In aus.

3. Klicken Sie auf **Bearbeiten** unter **Wer Zugriff hat.**

4. Speichern Sie die Änderungen.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Verhindern von Add-In-Downloads durch Deaktivieren der Office Store auf allen Clients (außer Outlook)

> [!NOTE]
> Outlook Add-In-Installation wird durch einen [anderen Prozess](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)verwaltet.

Als Organisation möchten Sie möglicherweise verhindern, dass neue Office-Add-Ins aus dem Office Store heruntergeladen werden. Dies kann in Verbindung mit der zentralen Bereitstellung verwendet werden, um sicherzustellen, dass nur von der Organisation genehmigte Add-Ins für Benutzer innerhalb Ihrer Organisation bereitgestellt werden.
  
**So deaktivieren Sie den Add-In-Erwerb**
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> [Dienste &amp; Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=2053743).

    > [!NOTE]
    > Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert. Wenn die oben beschriebenen Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt "Zentrale Bereitstellung", indem Sie zu **Einstellungen**  >  **integrierten Apps** wechseln. Wählen Sie oben auf der Seite **"Integrierte Apps"** die Option **"Add-Ins" aus.**
    
3. Wählen Sie **Benutzereigene Apps und Dienste aus**.
    
4. Deaktivieren Sie die Option, um Benutzern den Zugriff auf den Office Store zu erlauben.

    Dadurch wird verhindert, dass alle Benutzer die folgenden Add-Ins aus dem Store erwerben.
      
    - Add-Ins für Word, Excel und PowerPoint 2016 aus:
        
      - Windows
      - Mac
      - Office
        
        
    - Käufe beginnend mit **AppSource**
        
    - Add-Ins in Microsoft 365
        
    Einem Benutzer, der versucht, auf den Store zuzugreifen, wird die folgende Meldung angezeigt: Leider wurde Microsoft 365 so konfiguriert, dass der **einzelne Erwerb von Office Store-Add-Ins verhindert wird.**
  
Unterstützung für das Deaktivieren der Office Store ist in den folgenden Versionen verfügbar:
  
- Windows: 16.0.9001 – Derzeit verfügbar.
    
- Mac: 16.10.18011401 – Derzeit verfügbar.
    
- iOS: 2.9.18010804 – Derzeit verfügbar.
    
- Das Web – derzeit verfügbar.
    
Dies hindert einen Administrator nicht daran, die zentrale Bereitstellung zum Zuweisen eines Add-Ins aus dem Office Store zu verwenden.

> [!NOTE] 
> Add-Ins wie Visio Data Visualizer, Bing Karten und People Graph werden weiterhin im Menüband angezeigt, auch wenn ein Administrator die Store deaktiviert hat. Um diese Links zu entfernen, müssen Administratoren die Store über das Gruppenrichtlinienobjekt (Group Policy Object, GPO) deaktivieren.
  
Um zu verhindern, dass sich ein Benutzer mit einem Microsoft-Konto anmeldet, können Sie die Anmeldung so einschränken, dass nur das Organisationskonto verwendet wird. Weitere Informationen finden Sie unter [Identität, Authentifizierung und Autorisierung in Office 2016.](/DeployOffice/security/identity-authentication-and-authorization-in-office)  

> [!NOTE] 
> Wenn Benutzer am Zugriff auf den Office Store gehindert werden, wird auch verhindert, dass sie [Office-Add-Ins zu Testzwecken aus einer Netzwerkfreigabe querladen.](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Weitere Informationen zur Endbenutzererfahrung mit Add-Ins

Nachdem Sie ein Add-In bereitgestellt haben, können Ihre Endbenutzer es in ihren Office Anwendungen verwenden (siehe ["Start using your Office Add-in").](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) Das Add-In wird auf allen Plattformen angezeigt, die das Add-In unterstützt.
  
Wenn das Add-In Add-In-Befehle unterstützt, werden diese im Office-Menüband angezeigt. Im folgenden Beispiel wird der Befehl **Zitat suchen** für das Add-In **Zitate** angezeigt. 

![Office Menüband mit Suchz zitaten](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Wenn das bereitgestellte Add-In keine Add-In-Befehle unterstützt oder wenn Sie alle bereitgestellten Add-Ins anzeigen möchten, können Sie diese über **Meine Add-Ins** anzeigen. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>In Word 2016, Excel 2016 oder PowerPoint 2016

1. Wählen Sie **\> "Meine Add-Ins einfügen" aus.** 
    
2. Wählen Sie im Office-Add-In-Fenster die Schaltfläche **Vom Administrator verwaltet** aus. 
    
3. Doppelklicken Sie auf das Add-In, das Sie zuvor bereitgestellt haben (in diesem Beispiel **Zitate).**

    ![Registerkarte "Vom Administrator verwaltet" der Seite "Office-Add-Ins"](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>In Outlook

1. Wählen Sie im Menüband **"Start"** die Option **"Add-Ins abrufen" aus.**

    ![Schaltfläche "Speichern" in Outlook](../../media/getaddinsicon.png)
  
2. Wählen Sie im linken Navigationsbereich **vom Administrator verwaltete** aus. 

## <a name="related-content"></a>Verwandte Inhalte

[Bereitstellen von Add-Ins im Admin Center](./manage-deployment-of-add-ins.md) (Artikel)\
Weitere Informationen zum Erstellen und Erstellen [von Office-Add-Ins](/office/dev/add-ins/overview/office-add-ins) (Artikel)\
[Verwenden von PowerShell-Cmdlets für die zentrale Bereitstellung zum Verwalten von Add-Ins](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (Artikel)\
[Problembehandlung: Benutzer sehen keine Add-Ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (Artikel)\
[Minderjährige und Erwerb von Add-Ins aus dem Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (Artikel)
