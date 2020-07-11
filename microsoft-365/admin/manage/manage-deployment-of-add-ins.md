---
title: Bereitstellen von Add-Ins im Admin Center
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
ms.openlocfilehash: 51db2bf7b618bddf2c6de417b7f5e53c91a64a1b
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/11/2020
ms.locfileid: "45102860"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Bereitstellen von Add-Ins im Admin Center

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

[] Office-Add-Ins helfen Ihnen beim Personalisieren Ihrer Dokumente und beim Optimieren der Art und Weise, wie Sie im Web auf Informationen zugreifen (lesen Sie [Erste Schritte mit Ihrem Office-Add-In](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Als Administrator können Sie Office-Add-Ins für die Benutzer in Ihrer Organisation mithilfe des Features für die zentralisierte Bereitstellung im Microsoft 365 Admin Center bereitstellen. Die zentrale Bereitstellung ist die empfohlene und funktionsreichste Möglichkeit für die meisten Administratoren, um Add-Ins für Benutzer und Gruppen innerhalb einer Organisation bereitzustellen. 

Weitere Informationen zum ermitteln, ob Ihre Organisation eine zentralisierte Bereitstellung unterstützenkann, finden Sie unter [bestimmen, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert](centralized-deployment-of-add-ins.md).

Weitere Informationen zum Verwalten von Add-Ins nach der Bereitstellung finden Sie unter [Verwalten von Add-Ins im Admin Center](manage-addins-in-the-admin-center.md) .
  
> [!NOTE]
>  Für Word verwenden Excel und PowerPoint einen [SharePoint-App-Katalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) zum Bereitstellen von Add-Ins für Benutzer in einer lokalen Umgebung ohne Verbindung mit Microsoft 365 und/oder Unterstützung für SharePoint-Add-Ins erforderlich. Für Outlook verwenden Sie die Exchange-Systemsteuerung für die Bereitstellung in einer lokalen Umgebung ohne Verbindung mit Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Empfohlene Vorgehensweise für die Bereitstellung von Office-Add-Ins

Für das Rollout von Add-Ins mithilfe eines phasenweisen Ansatzes wird Folgendes empfohlen:
  
1. Stellen Sie das Add-In für eine kleine Gruppe von Projektbeteiligten und Mitgliedern der IT-Abteilung bereit. Wenn die Bereitstellung erfolgreich ist, fahren Sie mit Schritt 2 fort.
    
2. Stellen Sie das Add-in für mehr Personen innerhalb des Unternehmens bereit. Werten Sie die Ergebnisse erneut aus, und fahren Sie bei erfolgreicher Ausführung mit der vollständigen Bereitstellung fort.
    
3. Führen Sie eine vollständige Einführung für alle Benutzer aus.
    
Je nach Größe der Zielgruppe können Sie die Roll-out-Schritte hinzufügen oder entfernen.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Bereitstellen eines Office-Add-Ins mithilfe des Admin Centers

Bevor Sie beginnen, lesen Sie [ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert](centralized-deployment-of-add-ins.md).
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> **-Add-ins** .
    
2. Wählen Sie oben auf der Seite **Add-in bereitstellen** aus, und wählen Sie dann **weiter**aus.
    
3. Wählen Sie eine Option aus und folgen Sie den Anweisungen. 
  
4. Wenn Sie die Option zum Hinzufügen eines Add-Ins aus dem Office Store ausgewählt haben, müssen Sie die Add-in-Auswahl vornehmen. </br>

    Sie können die verfügbaren Add-Ins nach Kategorien anzeigen: **vorgeschlagen für Sie**, **Bewertung**oder **Name**. In der Office Store sind nur ﻿kostenlose Add-Ins verfügbar. Kostenpflichtige Add-Ins werden derzeit nicht unterstützt. Nachdem Sie ein Add-in ausgewählt haben, akzeptieren Sie die Bedingungen, um den Vorgang fortzusetzen. <br/> 

    > [!NOTE] 
    > Mit der Office Store Option werden Updates und Verbesserungen automatisch für Benutzer durchgestellten.

5. Wählen Sie auf der nächsten Seite ** Alle **, **Bestimmte Benutzer/Gruppen** oder **Nur ich** aus, um anzugeben, für wen das Add-in bereitgestellt wird. Suchen Sie im Suchfeld nach bestimmten Benutzern oder Gruppen. <br/>

    > [!NOTE] 
    > Weitere Informationen zu anderen Status, die für ein Add-in gelten, finden Sie unter [Add-in States](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md).
  
6. Wählen Sie **Bereitstellen**.
  
7. Wenn das Add-in bereitgestellt wird, wird ein grünes Häkchen angezeigt. Befolgen Sie die Anweisungen auf der Seite, um das Add-in zu testen.

    > [!NOTE]
    > Benutzer müssen Office möglicherweise neu starten, um das Add-in-Symbol auf dem App-Menüband anzuzeigen. Outlook-Add-Ins können bis zu 24 Stunden dauern, bis Sie auf App-menübändern angezeigt werden.
    
8. Wenn Sie fertig sind, wählen Sie **weiter**aus. Wenn Sie nur für sich selbst bereitgestellt haben, können Sie ändern auswählen, **der Zugriff auf das Add-in hat** , um mehr Benutzern bereitzustellen.

    Wenn Sie das Add-in für andere Mitglieder Ihrer Organisation bereitgestellt haben, befolgen Sie die Anweisungen, um die Bereitstellung des Add-ins anzukündigen. <br/>
  
    Es wird empfohlen, Benutzer und Gruppen darüber zu informieren, dass das bereitgestellte Add-in verfügbar ist. Sie sollten eine e-Mail senden, in der beschrieben wird, wann und wie das Add-in verwendet wird. Einschließen oder Verknüpfen von Hilfeinhalten oder FAQs, die Benutzern helfen können, wenn Probleme mit dem Add-in auftreten.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Überlegungen beim Zuweisen eines Add-Ins zu Benutzern und Gruppen

Administratoren können jedem oder bestimmten Benutzern und Gruppen ein Add-In zuweisen. Jede Option hat Auswirkungen:
  
- **Jeder Benutzer** Mit dieser Option wird das Add-in allen Benutzern in der Organisation zugewiesen. Verwenden Sie diese Option nur in Ausnahmefällen, da sie wirklich die gesamte Organisation betrifft. 
    
- **Benutzer** Wenn Sie ein Add-in einem einzelnen Benutzer zuweisen und dann das Add-in für einen neuen Benutzer bereitstellen, müssen Sie zuerst den neuen Benutzer hinzufügen.
    
- **Gruppen** Wenn Sie ein Add-in einer Gruppe zuweisen, werden Benutzern, die der Gruppe hinzugefügt werden, automatisch das Add-in zugewiesen. Wenn ein Benutzer aus einer Gruppe entfernt wird, verliert der Benutzer den Zugriff auf das Add-in. In beiden Fällen ist vom Administrator keine weitere Aktion erforderlich. 

- **Nur ich** Wenn Sie ein Add-in nur für sich selbst zuweisen, wird das Add-in nur Ihrem Konto zugewiesen, was ideal zum Testen des Add-Ins ist.
    
Die richtige Option für Ihre Organisation hängt von Ihrer Konfiguration ab. Es wird jedoch empfohlen, Zuordnungen mithilfe von Gruppen zu erstellen. Als Administrator ist es möglicherweise einfacher, Add-Ins mithilfe von Gruppen zu verwalten und die Mitgliedschaft dieser Gruppen zu steuern, anstatt einzelne Benutzer jedes Mal zuzuweisen. In einigen Situationen möchten Sie möglicherweise den Zugriff auf eine kleine Gruppe von Benutzern einschränken, indem Sie Benutzer manuell zuweisen, indem Sie Zuweisungen an bestimmte Benutzer vornehmen.
  
## <a name="more-about-office-add-ins-security"></a>Weitere Informationen zur Sicherheit von Office-Add-ins

Office add-ins combine an XML manifest file that contains some metadata about the add-in, but most importantly points to a web application which contains all the code and logic. Add-ins can range in their capabilities. For example, add-ins can:
  
- Daten anzeigen.
    
- Das Dokument eines Benutzers lesen, um kontextbezogene Dienste zur Verfügung zu stellen.
    
- Daten im Dokument eines Benutzers lesen und in das Dokument schreiben, um diesem Benutzer einen Wert zu bieten.
    
Weitere Informationen zu den Typen und Funktionen von Office-Add-Ins finden Sie unter [Office-Add-Ins-Plattformübersicht](https://go.microsoft.com/fwlink/p/?linkid=846362), insbesondere im Abschnitt "Aufbau eines Office-Add-In".
  
To interact with the user's document, the add-in needs to declare what permission it needs in the manifest. A five-level JavaScript API access-permissions model provides the basis for privacy and security for users of task pane add-ins. The majority of the add-ins in the Office Store are level ReadWriteDocument with almost all add-ins supporting at least the ReadDocument level. For more information about the permission levels, see [Requesting permissions for API use in content and task pane add-ins](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
When updating a manifest, the typical changes are to an add-in's icon and text. Occasionally, add-in commands change. However, the permissions of the add-in do not change. The web application where all the code and logic for the add-in runs can change at any time, which is the nature of web applications.
  
Aktualisierungen für Add-Ins werden auf folgende Weise ausgeführt:
  
- **Line-of-business add-in:** In this case, where an admin explicitly uploaded a manifest, the add-in requires that the admin upload a new manifest file to support metadata changes. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 

    > [!NOTE]
    > Administratoren müssen ein Lob-Add-in nicht für eine Aktualisierung entfernen.   Im Abschnitt Add-Ins kann der Administrator einfach auf das Lob-Add-in klicken und die **Schaltfläche Aktualisieren** in der unteren rechten Ecke auswählen. Das Update funktioniert nur, wenn die Version des neuen Add-ins größer ist als das des vorhandenen Add-Ins.   
    
- **Office Store add-in:** When an admin selected an add-in from the Office Store, if an add-in updates in the Office Store, the add-in will update later in Centralized Deployment. The next time the relevant Office applications start, the add-in will update. The web application can change at any time. 
  
## <a name="learn-more"></a>Weitere Informationen

Erstellen und Erstellen von [Office-Add-ins](https://go.microsoft.com/fwlink/p/?linkid=846362)

[Verwalten von Add-Ins im Admin Center](manage-addins-in-the-admin-center.md)

[Minderjährige und Erwerb von Add-Ins aus dem Store](minors-and-acquiring-addins-from-the-store.md)
  
[Verwenden von PowerShell-Cmdlets für zentralisierte Bereitstellung zum Verwalten von Add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Problembehandlung: Benutzer können keine Add-Ins sehen](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
