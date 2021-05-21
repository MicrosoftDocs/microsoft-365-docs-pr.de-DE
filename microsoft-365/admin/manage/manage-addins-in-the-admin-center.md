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
description: Erfahren Sie mehr über die Verwendung von zentralisierten Add-Ins zum Bereitstellen von Add-Ins für Benutzer und Gruppen in Ihrer Organisation.
ms.openlocfilehash: c103cfc4e3e7b404ea4d31d81bc30d7990a922dc
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593969"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Verwalten von Add-Ins im Admin Center

Office-Add-Ins helfen Ihnen, Ihre Dokumente zu personalisieren und den Zugriff auf Informationen im Web zu optimieren (siehe [Start using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). 

Nachdem ein Administrator Add-Ins für Benutzer in einer Organisation bereitgestellt hat, kann der Administrator Add-Ins deaktivieren oder aktivieren, bearbeiten, löschen und den Zugriff auf die Add-Ins verwalten.

Weitere Informationen zum Installieren von Add-Ins aus dem Admin Center finden Sie unter [Deploy add-ins in the Admin Center](./manage-deployment-of-add-ins.md).
  
## <a name="add-in-states"></a>Add-In-Status

Ein Add-In kann den Status **Ein** oder **Aus** haben.
  
| Status | Auftreten des Status | Auswirkung |
|:-----|:-----|:-----|
|**Aktiv**  <br/> |Der Administrator hat das Add-In hochgeladen und Benutzern oder Gruppen zugewiesen.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen sehen es im jeweiligen Client.  <br/> |
|**Deaktiviert**  <br/> |Der Administrator hat das Add-In deaktiviert.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr auf das Add-In zugreifen.  <br/> Wenn der Zustand des Add-Ins in "Aktiv" geändert wird, können die Benutzer und Gruppen wieder darauf zugreifen.  <br/> |
|**Gelöscht**  <br/> |Der Administrator hat das Add-In gelöscht.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr darauf zugreifen.  <br/> |
   
Erwägen Sie das Löschen eines Add-Ins, wenn es nicht mehr verwendet wird. Beispielsweise kann das Deaktivieren eines Add-Ins sinnvoll sein, wenn ein Add-In nur zu bestimmten Zeiten des Jahres verwendet wird.

## <a name="delete-an-add-in"></a>Löschen eines Add-Ins

Sie können auch ein bereitgestelltes Add-In löschen.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen**  >  **Dienste & Add-Ins.**

    > [!NOTE]
    > Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert. Wenn die oben genannten Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt Zentrale Bereitstellung, indem Sie **zu Einstellungen** integrierte  >  **Apps wechseln.** Wählen Sie oben auf der Seite Integrierte **Apps** die Option **Add-Ins aus.**

2. Wählen Sie das bereitgestellte Add-In aus.

3. Klicken Sie auf **Add-In löschen.** Entfernen Sie die Schaltfläche Add-In in der unteren rechten Ecke.

4. Überprüfen Sie Ihre Auswahl und wählen Sie **Add-In entfernen** aus.

## <a name="edit-add-in-access"></a>Bearbeiten des Add-In-Zugangs

Nach der Bereitstellung können Administratoren auch den Benutzerzugriff auf Add-Ins verwalten.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen**  >  **Dienste & Add-Ins.**

    > [!NOTE]
    > Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert. Wenn die oben genannten Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt Zentrale Bereitstellung, indem Sie **zu Einstellungen** integrierte  >  **Apps wechseln.** Wählen Sie oben auf der Seite Integrierte **Apps** die Option **Add-Ins aus.**

2. Wählen Sie das bereitgestellte Add-In aus.

3. Klicken Sie **auf Bearbeiten** unter Wer **Zugriff hat**.

4. Speichern Sie die Änderungen.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Verhindern von Add-In-Downloads durch Deaktivieren der Office Store für alle Clients (außer Outlook)

> [!NOTE]
> Outlook Add-In-Installation wird von einem anderen [Prozess verwaltet.](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)

Als Organisation möchten Sie möglicherweise verhindern, dass neue Office-Add-Ins aus dem Office Store. Dies kann in Verbindung mit der zentralen Bereitstellung verwendet werden, um sicherzustellen, dass nur von der Organisation genehmigte Add-Ins für Benutzer in Ihrer Organisation bereitgestellt werden.
  
**So deaktivieren Sie den Add-In-Erwerb**
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> [Dienste &amp; Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=2053743).

    > [!NOTE]
    > Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert. Wenn die oben genannten Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt Zentrale Bereitstellung, indem Sie **zu Einstellungen** integrierte  >  **Apps wechseln.** Wählen Sie oben auf der Seite Integrierte **Apps** die Option **Add-Ins aus.**
    
3. Wählen Sie **Benutzereigene Apps und Dienste aus**.
    
4. Deaktivieren Sie die Option, um Benutzern den Zugriff auf den Office Store zu erlauben.

    Dadurch wird verhindert, dass alle Benutzer die folgenden Add-Ins aus dem Store abrufen.
      
    - Add-Ins für Word, Excel und PowerPoint 2016 aus:
        
      - Windows
      - Mac
      - Office
        
        
    - Käufe, die in **AppSource beginnen**
        
    - Add-Ins innerhalb Microsoft 365
        
    Einem Benutzer, der versucht, auf den Store zu zugreifen, wird die folgende Meldung angezeigt: Leider wurde Microsoft 365 so konfiguriert, dass der einzelne Erwerb von Office Store **verhindert wird.**
  
Unterstützung für das Deaktivieren der Office Store ist in den folgenden Versionen verfügbar:
  
- Windows: 16.0.9001 – Derzeit verfügbar.
    
- Mac: 16.10.18011401 – Derzeit verfügbar.
    
- iOS: 2.9.18010804 – Derzeit verfügbar.
    
- Das Web – Derzeit verfügbar.
    
Dies verhindert nicht, dass ein Administrator die zentrale Bereitstellung zum Zuweisen eines Add-Ins aus der Office Store.
  
Um zu verhindern, dass sich ein Benutzer mit einem Microsoft-Konto anmeldet, können Sie die Anmeldung auf die Verwendung des Organisationskontos beschränken. Weitere Informationen finden Sie unter [Identity, authentication, and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office).  

> [!NOTE] 
> Wenn Sie verhindern, dass Benutzer auf den Office Store zugreifen, wird auch verhindert, dass sie [Office-Add-Ins](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)für Tests von einer Netzwerkfreigabe querladen.

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Weitere Informationen zur Endbenutzererfahrung mit Add-Ins

Nachdem Sie ein Add-In bereitgestellt haben, können Ihre Endbenutzer damit beginnen, es in ihren Office zu verwenden (siehe [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Das Add-In wird auf allen Plattformen angezeigt, die vom Add-In unterstützt werden.
  
Wenn das Add-In Add-In-Befehle unterstützt, werden diese im Office-Menüband angezeigt. Im folgenden Beispiel wird der Befehl **Zitat suchen** für das Add-In **Zitate** angezeigt. 

![Office menüband mit Suchzitate](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Wenn das bereitgestellte Add-In keine Add-In-Befehle unterstützt oder Sie alle bereitgestellten Add-Ins anzeigen möchten, können Sie sie über **Meine Add-Ins anzeigen.** 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>In Word 2016, Excel 2016 oder PowerPoint 2016

1. Wählen **Sie Meine \> Add-Ins einfügen aus.** 
    
2. Wählen Sie im Office-Add-In-Fenster die Schaltfläche **Vom Administrator verwaltet** aus. 
    
3. Doppelklicken Sie auf das zuvor bereitgestellte Add-In (in diesem Beispiel **Zitate**).

    ![Registerkarte "Verwalteter Administrator" Office Add-Ins-Seite](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>In Outlook

1. Wählen Sie **auf dem Menüband** Start die Option **Add-Ins erhalten aus.**

    ![Schaltfläche "Speichern" in Outlook](../../media/getaddinsicon.png)
  
2. Wählen Sie im linken Navigationsbereich **vom Administrator verwaltete** aus. 

## <a name="related-content"></a>Verwandte Inhalte

[Bereitstellen von Add-Ins im Admin Center](./manage-deployment-of-add-ins.md) (Artikel)

Weitere Informationen zum Erstellen und Erstellen [Office Add-Ins](/office/dev/add-ins/overview/office-add-ins) (Artikel)
  
[Verwenden von PowerShell-Cmdlets](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) für die zentrale Bereitstellung zum Verwalten von Add-Ins (Artikel)
  
[Problembehandlung: Benutzer sieht keine Add-Ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (Artikel)

[Minderjährige und Erwerben von Add-Ins Microsoft Store](./minors-and-acquiring-addins-from-the-store.md) (Artikel)