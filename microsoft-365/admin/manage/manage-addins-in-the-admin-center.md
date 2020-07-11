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
description: Hier erfahren Sie, wie Sie Add-Ins für Benutzer und Gruppen in Ihrer Organisation mithilfe einer zentralisierten Bereitstellung im Admin Center bereitstellen können.
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103099"
---
# <a name="manage-add-ins-in-the-admin-center"></a>Verwalten von Add-Ins im Admin Center

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

Office-Add-Ins unterstützen Sie bei der Personalisierung Ihrer Dokumente und bei der Optimierung der Art und Weise, wie Sie auf Informationen im Internet zugreifen (siehe [Start mit Ihrem Office-Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). 

Nachdem ein Administrator Add-Ins für Benutzer in einer Organisation bereitgestellt hat, kann der Administrator Add-Ins aus-oder einschalten, bearbeiten, löschen und den Zugriff auf die Add-Ins verwalten.

Weitere Informationen zum Installieren von Add-Ins aus dem Admin Center finden Sie unter [Deploy Add-Ins in the Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins).
  
## <a name="add-in-states"></a>Add-In-Status

Ein Add-in kann entweder im Status **on** oder **Off** liegen.
  
|**Status**|**Wie der Status eintritt**|**Auswirkung**|
|:-----|:-----|:-----|
|**Active**  <br/> |Der Administrator hat das Add-in hochgeladen und Benutzern oder Gruppen zugewiesen.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen sehen es im jeweiligen Client.  <br/> |
|**Deaktiviert**  <br/> |Der Administrator hat das Add-In deaktiviert.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr auf das Add-In zugreifen.  <br/> Wenn der Zustand des Add-Ins in "Aktiv" geändert wird, können die Benutzer und Gruppen wieder darauf zugreifen.  <br/> |
|**Gelöscht**  <br/> |Der Administrator hat das Add-In gelöscht.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr darauf zugreifen.  <br/> |
   
Sie sollten ein Add-in in einem Fall löschen, wenn es von keinem mehr verwendet wird. Beispielsweise kann das Deaktivieren eines Add-ins sinnvoll sein, wenn ein Add-in nur zu bestimmten Jahreszeiten verwendet wird.

## <a name="delete-an-add-in"></a>Löschen eines Add-Ins

Sie können auch ein Add-in löschen, das bereitgestellt wurde.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen**für  >  **Dienste &-Add-ins** .

2. Wählen Sie das bereitgestellte Add-in aus.

3. Klicken Sie auf **Add-in löschen**. Entfernen Sie die Add-In-Schaltfläche in der unteren rechten Ecke.

4. Überprüfen Sie Ihre Auswahl und wählen Sie **Add-In entfernen**aus.

## <a name="edit-add-in-access"></a>Bearbeiten des Add-In-Zugangs

Nach der Bereitstellung können Administratoren auch den Benutzer Zugriff auf Add-Ins verwalten.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen**für  >  **Dienste &-Add-ins** .

2. Wählen Sie das bereitgestellte Add-in aus.

3. Klicken Sie unter **Wer hat Zugriff**auf **Bearbeiten** .

4. Speichern Sie die Änderungen.

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Verhindern von Add-in-Downloads durch Deaktivieren der Office Store für alle Clients (außer Outlook)

> [!NOTE]
> Die Outlook-Add-in-Installation wird von einem [anderen Prozess](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)verwaltet.

Als Organisation möchten Sie möglicherweise verhindern, dass neue Office-Add-Ins aus dem Office Store heruntergeladen werden. Dies kann in Verbindung mit einer zentralisierten Bereitstellung verwendet werden, um sicherzustellen, dass nur von der Organisation genehmigte Add-Ins für Benutzer in Ihrer Organisation bereitgestellt werden.
  
**So deaktivieren Sie die Add-in-Akquisition**
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> [Dienste &amp; Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=2053743).
    
3. Wählen Sie **Benutzereigene Apps und Dienste aus**.
    
4. Deaktivieren Sie die Option, um Benutzern den Zugriff auf den Office Store zu erlauben.

Dadurch wird verhindert, dass alle Benutzer die folgenden Add-Ins aus dem Speicher erwerben.
  
- Add-Ins für Word, Excel und PowerPoint 2016 von:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Übernahmen, die in **AppSource** beginnen
    
- Add-Ins in Microsoft 365
    
Ein Benutzer, der versucht, auf den Store zuzugreifen, wird die folgende Meldung angezeigt: **Sorry, Microsoft 365 wurde so konfiguriert, dass die einzelne Akquisition von Office Store-Add-Ins verhindert wird.**
  
Unterstützung für das Deaktivieren des Office Store ist in den folgenden Versionen verfügbar:
  
- Windows: 16.0.9001 – derzeit verfügbar.
    
- Mac: 16.10.18011401 – derzeit verfügbar.
    
- iOS: 2.9.18010804-derzeit verfügbar.
    
- Das derzeit verfügbare Internet.
    
Dies hindert einen Administrator nicht daran, ein Add-in aus dem Office Store mithilfe einer zentralisierten Bereitstellung zuzuweisen.
  
Wenn Sie verhindern möchten, dass sich ein Benutzer mit einem Microsoft-Konto anmeldet, können Sie die Anmeldung einschränken, sodass nur das organisationskonto verwendet wird. Weitere Informationen finden Sie unter [Identity, Authentication und Authorization in Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).  

## <a name="more-about-the-end-user-experience-with-add-ins"></a>Weitere Informationen zur Benutzeroberfläche mit Add-ins

Nachdem Sie ein Add-in bereitgestellt haben, können Ihre Endbenutzer damit beginnen, es in Ihren Office-Anwendungen zu verwenden (siehe [Start mit der Office-Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Das Add-in wird auf allen Plattformen angezeigt, die das Add-in unterstützt.
  
If the add-in supports add-in commands, the commands appear on the Office ribbon. In the following example, the command **Search Citation** appears for the **Citations** add-in. 

![Office-Menüband mit Such Zitaten](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Wenn das bereitgestellte Add-in keine Add-in-Befehle unterstützt oder wenn Sie alle bereitgestellten Add-Ins anzeigen möchten, können Sie diese über **Meine Add-ins**anzeigen. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>In Word 2016, Excel 2016 oder PowerPoint 2016

1. Wählen **Sie \> Meine Add-Ins einfügen**aus. 
    
2. Wählen Sie im Office-Add-In-Fenster die Schaltfläche **Vom Administrator verwaltet** aus. 
    
3. Doppelklicken Sie auf das Add-In, das Sie zuvor bereitgestellt haben (in diesem Beispiel **Zitate** ). <br/>![Registerkarte "verwalteter Administrator" der Seite "Office-Add-Ins"](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>In Outlook

1. Wählen Sie im Menüband **Start** die Option **Add-Ins abrufen**aus.<br/>![Schaltfläche "Speichern" in Outlook](../../media/getaddinsicon.png)
  
2. Wählen Sie im linken Navigationsbereich **vom Administrator verwaltete** aus. 

## <a name="learn-more"></a>Weitere Informationen

[Bereitstellen von Add-Ins im Admin Center](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

Weitere Informationen zum Erstellen von [Office-Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=846362)
  
[Verwenden Sie PowerShell-Cmdlets für zentralisierte Bereitstellung zum Verwalten von Add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).
  
[Problembehandlung: Benutzer können keine Add-Ins sehen](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[Minderjährige und Erwerb von Add-Ins aus dem Microsoft Store](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)