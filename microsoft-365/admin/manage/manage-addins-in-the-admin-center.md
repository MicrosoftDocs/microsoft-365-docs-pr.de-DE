---
title: Verwalten von Add-Ins im Admin Center
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
ms.openlocfilehash: 5366bd5be80559f23490aeb54f9417a189169e12
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114201"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Verwalten von Add-Ins im Admin Center

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).

::: moniker-end

Office-Add-Ins helfen Ihnen, Ihre Dokumente zu personalisieren und die Art und Weise zu optimieren, wie Sie auf Informationen im Web zugreifen (siehe Start [using your Office add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). 

Nachdem ein Administrator Add-Ins für Benutzer in einer Organisation bereitgestellt hat, kann er die Add-Ins deaktivieren oder aktivieren, bearbeiten, löschen und den Zugriff auf die Add-Ins verwalten.

Weitere Informationen zum Installieren von Add-Ins aus dem Admin Center finden Sie unter Bereitstellen von [Add-Ins im Admin Center.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)
  
## <a name="add-in-states"></a>Add-In-Status

Ein Add-in kann den Status "Ein" **oder** **"Aus"** haben.
  
|**Status**|**Wie der Status eintritt**|**Auswirkung**|
|:-----|:-----|:-----|
|**Active**  <br/> |Der Administrator hat das Add-in hochgeladen und Benutzern oder Gruppen zugewiesen.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen sehen es im jeweiligen Client.  <br/> |
|**Deaktiviert**  <br/> |Der Administrator hat das Add-In deaktiviert.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr auf das Add-In zugreifen.  <br/> Wenn der Zustand des Add-Ins in "Aktiv" geändert wird, können die Benutzer und Gruppen wieder darauf zugreifen.  <br/> |
|**Gelöscht**  <br/> |Der Administrator hat das Add-In gelöscht.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr darauf zugreifen.  <br/> |
   
Erwägen Sie das Löschen eines Add-Ins, wenn es nicht mehr verwendet wird. Beispielsweise kann das Deaktivieren eines Add-Ins sinnvoll sein, wenn ein Add-in nur zu bestimmten Zeiten des Jahres verwendet wird.

## <a name="delete-an-add-in"></a>Löschen eines Add-Ins

Sie können auch ein bereitgestelltes Add-In löschen.

1. Wechseln Sie im Admin Center zur Seite   >  **"&-Add-Ins".**

     > [!NOTE]
    > Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert. Wenn die oben genannten Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt "Zentrale Bereitstellung", indem Sie **zu**"Integrierte  >  **Einstellungen"-Apps wechseln.** On the top of the **Integrated apps** page, choose **Add-ins**.

2. Wählen Sie das bereitgestellte Add-In aus.

3. Klicken Sie auf **"Add-In löschen".** Entfernen Sie die Add-In-Schaltfläche in der unteren rechten Ecke.

4. Überprüfen Sie Ihre Auswahl und wählen Sie **Add-In entfernen** aus.

## <a name="edit-add-in-access"></a>Bearbeiten des Add-In-Zugangs

Nach der Bereitstellung können Administratoren auch den Benutzerzugriff auf Add-Ins verwalten.

1. Wechseln Sie im Admin Center zur Seite   >  **"&-Add-Ins".**

     > [!NOTE]
    > Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert. Wenn die oben genannten Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt "Zentrale Bereitstellung", indem Sie **zu**"Integrierte  >  **Einstellungen"-Apps wechseln.** On the top of the **Integrated apps** page, choose **Add-ins**.

2. Wählen Sie das bereitgestellte Add-In aus.

3. Klicken Sie unter **"Wer** hat **Zugriff" auf "Bearbeiten".**

4. Speichern Sie die Änderungen.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Verhindern von Add-In-Downloads durch Deaktivieren des Office Store auf allen Clients (außer Outlook)

> [!NOTE]
> Die Installation von Outlook-Add-Ins wird von einem anderen [Prozess verwaltet.](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)

Als Organisation möchten Sie möglicherweise verhindern, dass neue Office-Add-Ins aus dem Office Store heruntergeladen werden. Dies kann in Verbindung mit der zentralen Bereitstellung verwendet werden, um sicherzustellen, dass nur von der Organisation genehmigte Add-Ins für Benutzer in Ihrer Organisation bereitgestellt werden.
  
**So deaktivieren Sie den Add-In-Kauf**
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> [Dienste &amp; Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=2053743).

     > [!NOTE]
    > Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert. Wenn die oben genannten Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt "Zentrale Bereitstellung", indem Sie **zu**"Integrierte  >  **Einstellungen"-Apps wechseln.** On the top of the **Integrated apps** page, choose **Add-ins**.
    
3. Wählen Sie **Benutzereigene Apps und Dienste aus**.
    
4. Deaktivieren Sie die Option, um Benutzern den Zugriff auf den Office Store zu erlauben.

Dadurch wird verhindert, dass alle Benutzer die folgenden Add-Ins aus dem Store erwerben.
  
- Add-Ins für Word, Excel und PowerPoint 2016 aus:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Käufe, die in **AppSource beginnen**
    
- Add-Ins in Microsoft 365
    
Einem Benutzer, der versucht, auf den Store zu zugreifen, wird die folgende Meldung angezeigt: Microsoft 365 wurde leider so konfiguriert, dass der einzelne Erwerb von **Office Store-Add-Ins verhindert wird.**
  
Unterstützung für das Deaktivieren des Office Store ist in den folgenden Versionen verfügbar:
  
- Windows: 16.0.9001 – Derzeit verfügbar.
    
- Mac: 16.10.18011401 – Derzeit verfügbar.
    
- iOS: 2.9.18010804 – Derzeit verfügbar.
    
- Das Web – derzeit verfügbar.
    
Dies verhindert nicht, dass ein Administrator die zentrale Bereitstellung verwendet, um ein Add-In aus dem Office Store zuzuordnen.
  
Um zu verhindern, dass sich ein Benutzer mit einem Microsoft-Konto anmeldet, können Sie die Anmeldung auf die Verwendung des Organisationskontos beschränken. Weitere Informationen finden Sie unter [Identität, Authentifizierung und Autorisierung in Office 2016.](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)  

> [!NOTE]
> Wenn Benutzer nicht auf den Office Store zugreifen können, wird auch verhindert, dass sie [Office-Add-Ins zu Testzwecken querladen.](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Weitere Informationen zur Endbenutzererfahrung mit Add-Ins

Nachdem Sie ein Add-In bereitgestellt haben, können Ihre Endbenutzer damit beginnen, es in ihren Office-Anwendungen zu verwenden (siehe Start [using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Das Add-in wird auf allen Plattformen angezeigt, die das Add-in unterstützt.
  
Wenn das Add-In Add-In-Befehle unterstützt, werden diese im Office-Menüband angezeigt. Im folgenden Beispiel wird der Befehl **Zitat suchen** für das Add-In **Zitate** angezeigt. 

![Menüband von Office mit Suchersuchen](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Wenn das bereitgestellte Add-In keine Add-In-Befehle unterstützt oder Wenn Sie alle bereitgestellten Add-Ins anzeigen möchten, können Sie sie über Meine **Add-Ins anzeigen.** 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>In Word 2016, Excel 2016 oder PowerPoint 2016

1. Wählen **Sie "Meine \> Add-Ins einfügen" aus.** 
    
2. Wählen Sie im Office-Add-In-Fenster die Schaltfläche **Vom Administrator verwaltet** aus. 
    
3. Doppelklicken Sie auf das Add-In, das Sie zuvor bereitgestellt haben (in diesem Beispiel **Zitate** ). <br/>![Registerkarte "Vom Administrator verwaltet" auf der Seite "Office-Add-Ins"](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>In Outlook

1. Wählen Sie **im Menüband "Start"** die Option **"Add-Ins erhalten" aus.**<br/>![Schaltfläche "Speichern" in Outlook](../../media/getaddinsicon.png)
  
2. Wählen Sie im linken Navigationsbereich **vom Administrator verwaltete** aus. 

## <a name="learn-more"></a>Weitere Informationen

[Bereitstellen von Add-Ins im Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

Weitere Informationen zum Erstellen von [Office-Add-Ins](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)
  
[Verwenden Sie powerShell-Cmdlets](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)für die zentrale Bereitstellung zum Verwalten von Add-Ins.
  
[Problembehandlung: Benutzer sieht keine Add-Ins](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Minderjährige und Erwerb von Add-Ins aus dem Microsoft Store](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
