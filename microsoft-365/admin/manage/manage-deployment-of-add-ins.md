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
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Erfahren Sie, wie Sie Mithilfe der zentralen Bereitstellung im Admin Center Add-Ins für Benutzer und Gruppen in Ihrer Organisation bereitstellen.
ms.openlocfilehash: ef7237f20780cb67bc84561ad8617dd8da6f8b82
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926354"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Bereitstellen von Add-Ins im Admin Center

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

[] Office-Add-Ins helfen Ihnen beim Personalisieren Ihrer Dokumente und beim Optimieren der Art und Weise, wie Sie im Web auf Informationen zugreifen (lesen Sie [Erste Schritte mit Ihrem Office-Add-In](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Als Administrator können Sie Office-Add-Ins für die Benutzer in Ihrer Organisation mithilfe des Features "Zentrale Bereitstellung" im Microsoft 365 Admin Center bereitstellen. Die zentrale Bereitstellung ist die empfohlene und funktionsreichste Methode für die meisten Administratoren zum Bereitstellen von Add-Ins für Benutzer und Gruppen innerhalb einer Organisation. 

Weitere Informationen dazu, wie Sie ermitteln können, ob Ihre Organisation die zentrale Bereitstellung unterstützen kann, finden Sie unter Ermitteln, ob die zentrale Bereitstellung von [Add-Ins für Ihre Organisation funktioniert.](centralized-deployment-of-add-ins.md)

Weitere Informationen zum Verwalten von Add-Ins nach der Bereitstellung finden Sie unter Verwalten von [Add-Ins im Admin Center.](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Für Word verwenden Excel und PowerPoint einen [SharePoint-App-Katalog,](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) um Add-Ins für Benutzer in einer lokalen Umgebung ohne Verbindung zu Microsoft 365 und/oder unterstützung für SharePoint-Add-Ins zu bereitstellen. Verwenden Sie für Outlook die Exchange-Systemsteuerung, um sie in einer lokalen Umgebung ohne Verbindung mit Microsoft 365 zu bereitstellen.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Empfohlene Vorgehensweise für die Bereitstellung von Office-Add-Ins

Zum Rollout von Add-Ins mithilfe eines phasenweiser Ansatzes wird Folgendes empfohlen:
  
1. Stellen Sie das Add-In für eine kleine Gruppe von Projektbeteiligten und Mitgliedern der IT-Abteilung bereit. Wenn die Bereitstellung erfolgreich ist, wechseln Sie zu Schritt 2.
    
2. Sie können das Add-in für weitere Personen im Unternehmen rollouten. Werten Sie erneut die Ergebnisse aus, und fahren Sie bei erfolgreicher Bereitstellung mit der vollständigen Bereitstellung fort.
    
3. Führen Sie ein vollständiges Rollout für alle Benutzer durch.
    
Je nach Größe der Zielgruppe können Sie Rolloutschritte hinzufügen oder entfernen.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Bereitstellen eines Office-Add-Ins mithilfe des Admin Centers

Bevor Sie beginnen, lesen Sie "Ermitteln", ob die zentrale Bereitstellung von [Add-Ins für Ihre Organisation funktioniert.](centralized-deployment-of-add-ins.md)
  
1. Wechseln Sie im Admin Center zur **Seite** \> **"Einstellungen-Add-Ins".** Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zur Seite "Integrierte Einstellungen für  \>  \> **Apps-Add-Ins".**
    
2. Wählen Sie oben auf der Seite **"Add-In** bereitstellen" und dann **"Weiter" aus.**
 
    > [!NOTE]
    > Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert. Wenn die oben genannten Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt "Zentrale Bereitstellung", indem Sie **zu**"Integrierte  >  **Einstellungen"-Apps wechseln.** On the top of the **Integrated apps** page, choose **Add-ins**.
    
3. Wählen Sie eine Option aus und folgen Sie den Anweisungen. 
  
4. Wenn Sie die Option zum Hinzufügen eines Add-Ins aus dem Office Store ausgewählt haben, treffen Sie ihre Add-In-Auswahl. </br>

    Sie können verfügbare Add-Ins nach Kategorien anzeigen: **Für** Sie vorgeschlagen, **Bewertung** oder **Name**. Im Office Store sind nur kostenlose Add-Ins verfügbar. Kostenpflichtige Add-Ins werden derzeit nicht unterstützt. Nachdem Sie ein Add-In ausgewählt haben, akzeptieren Sie die Allgemeinen Geschäftsbedingungen, um fortzufahren. <br/> 

    > [!NOTE] 
    > Mit der Office Store-Option werden Updates und Verbesserungen automatisch für Benutzer bereitgestellt.

5. Wählen Sie auf der nächsten Seite **Alle**, **Bestimmte Benutzer/Gruppen** oder **Nur ich** aus, um anzugeben, für wen das Add-in bereitgestellt wird. Verwenden Sie das Suchfeld, um nach bestimmten Benutzern oder Gruppen zu suchen. <br/>

    > [!NOTE] 
    > Weitere Informationen zu anderen Zustände, die für ein Add-In gelten, finden Sie unter [Add-In-Zustände.](https://docs.microsoft.com/microsoft-365/admin/manage/manage-addins-in-the-admin-center.md)
  
6. Wählen Sie **Bereitstellen**.
  
7. Wenn das Add-in bereitgestellt wird, wird ein grünes Teilchen angezeigt. Befolgen Sie die Anweisungen auf der Seite, um das Add-in zu testen.

    > [!NOTE]
    > Benutzer müssen Office möglicherweise neu starten, um das Add-In-Symbol im Menüband der App anzeigen zu können. Es kann bis zu 24 Stunden dauern, bis Outlook-Add-Ins auf den Menübändern der App angezeigt werden.
    
8. Wenn Sie fertig sind, wählen Sie **"Weiter" aus.** Wenn Sie nur für sich selbst bereitgestellt haben, können Sie "Ändern, wer Zugriff auf das **Add-In** hat" auswählen, um die Bereitstellung für mehr Benutzer zu ermöglichen.

    Wenn Sie das Add-in für andere Mitglieder Ihrer Organisation bereitgestellt haben, folgen Sie den Anweisungen, um die Bereitstellung des Add-Ins ankündigen. <br/>
  
    Es ist eine bewährte Methode, Benutzer und Gruppen darüber zu informieren, dass das bereitgestellte Add-In verfügbar ist. Erwägen Sie das Senden einer E-Mail, in der beschrieben wird, wann und wie das Add-in verwendet wird. Fügen Sie Hilfeinhalte oder häufig gestellte Fragen hinzu, die Benutzern bei Problemen mit dem Add-in helfen können, oder verknüpfen Sie diese.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Überlegungen beim Zuweisen eines Add-Ins zu Benutzern und Gruppen

Administratoren können jedem oder bestimmten Benutzern und Gruppen ein Add-In zuweisen. Jede Option hat Auswirkungen:
  
- **Jeder** Mit dieser Option wird das Add-in jedem Benutzer in der Organisation zugewiesen. Verwenden Sie diese Option nur in Ausnahmefällen, da sie wirklich die gesamte Organisation betrifft. 
    
- **Benutzer** Wenn Sie einem einzelnen Benutzer ein Add-In zuweisen und das Add-in dann einem neuen Benutzer bereitstellen, müssen Sie zuerst den neuen Benutzer hinzufügen.
    
- **Gruppen** Wenn Sie ein Add-In einer Gruppe zuweisen, wird Benutzern, die der Gruppe hinzugefügt werden, automatisch das Add-In zugewiesen. Wenn ein Benutzer aus einer Gruppe entfernt wird, verliert der Benutzer den Zugriff auf das Add-In. In beiden Fällen ist vom Administrator keine zusätzliche Aktion erforderlich. 

- **Just me** Wenn Sie ein Add-In nur sich selbst zuweisen, wird das Add-in nur Ihrem Konto zugewiesen, das sich ideal zum Testen des Add-Ins eignet.
    
Die richtige Option für Ihre Organisation hängt von Ihrer Konfiguration ab. Es wird jedoch empfohlen, Zuweisungen mithilfe von Gruppen zu erstellen. Als Administrator ist es möglicherweise einfacher, Add-Ins mithilfe von Gruppen zu verwalten und die Mitgliedschaft dieser Gruppen zu steuern, anstatt jedes Mal einzelne Benutzer zuzuordnen. In einigen Situationen können Sie den Zugriff auf eine kleine Gruppe von Benutzern einschränken, indem Sie Zuweisungen für bestimmte Benutzer vornehmen, indem Sie Benutzer manuell zuweisen.
  
## <a name="more-about-office-add-ins-security"></a>Weitere Informationen zur Sicherheit von Office-Add-Ins

Office-Add-Ins sind eine Kombination aus einer XML-Manifestdatei, die einige Metadaten zum Add-In enthält, aber vor allem auf eine Webanwendung verweist, die den gesamten Code und die Logik enthält. Add-Ins können verschiedene Bereiche von Funktionen umfassen. So können Add-Ins beispielsweise Folgendes:
  
- Daten anzeigen.
    
- Das Dokument eines Benutzers lesen, um kontextbezogene Dienste zur Verfügung zu stellen.
    
- Daten im Dokument eines Benutzers lesen und in das Dokument schreiben, um diesem Benutzer einen Wert zu bieten.
    
Weitere Informationen zu den Typen und Funktionen von Office-Add-Ins finden Sie unter [Office-Add-Ins-Plattformübersicht](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins), insbesondere im Abschnitt "Aufbau eines Office-Add-In".
  
Zur Interaktion mit dem Dokument des Benutzers muss das Add-In die erforderlichen Berechtigungen im Manifest deklarieren. Ein 5-stufiges JavaScript-API-Zugriffsberechtigungsmodell bildet die Grundlage für Datenschutz und Sicherheit für Benutzer der Aufgabenbereich-Add-Ins. Der Großteil der Add-Ins im Office Store weist die Berechtigungsstufe "ReadWriteDocument" auf, und fast alle Add-Ins unterstützen mindestens die Stufe "ReadDocument". Weitere Informationen zu den Berechtigungsstufen finden Sie unter [Anfordern von Berechtigungen zur API-Verwendung in Inhalts- und Aufgabenbereich-Add-Ins](https://docs.microsoft.com/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
Beim Aktualisieren eines Manifests werden in der Regel Änderungen am Symbol und Text eines Add-Ins vorgenommen. Gelegentlich ändern sich auch Add-In-Befehle. Die Berechtigungen des Add-Ins ändern sich jedoch nicht. Die Webanwendung, in der der gesamte Code und die Logik für das Add-In ausgeführt werden, kann sich jederzeit ändern. Dies liegt in der Natur von Webanwendungen.
  
Aktualisierungen für Add-Ins werden auf folgende Weise ausgeführt:
  
- **Line-of-Business-Add-In:** In diesem Fall, in dem ein Administrator ein Manifest explizit hochgeladen hat, erfordert das Add-In, dass der Administrator eine neue Manifestdatei zur Unterstützung von Metadatenänderungen hochlädt. Beim nächsten Starten der jeweiligen Office-Anwendungen wird das Add-In aktualisiert. Die Webanwendung kann sich jederzeit ändern. 

    > [!NOTE]
    > Der Administrator muss kein BRANCHEN-Add-In entfernen, um ein Update zu machen.   Im Abschnitt "Add-Ins" kann der Administrator einfach auf  das BRANCHEN-Add-In klicken und in der unteren rechten Ecke die Schaltfläche "Aktualisieren" auswählen. Das Update funktioniert nur, wenn die Version des neuen Add-Ins größer als die des vorhandenen Add-Ins ist.   
    
- **Office Store-Add-In:** Wenn ein Administrator ein Add-In aus dem Office Store ausgewählt hat und dieses Add-In im Office Store aktualisiert wird, wird das Add-In später in der zentralen Bereitstellung aktualisiert. Beim nächsten Starten der jeweiligen Office-Anwendungen wird das Add-In aktualisiert. Die Webanwendung kann sich jederzeit ändern. 
  
## <a name="learn-more"></a>Weitere Informationen

[Verwalten von Add-Ins im Admin Center](manage-addins-in-the-admin-center.md)

[Erstellen Sie Ihr erstes Word-Aufgabenbereich-Add-In.](https://docs.microsoft.com/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)

[Minderjährige und Erwerb von Add-Ins aus dem Store](minors-and-acquiring-addins-from-the-store.md)
  
[Verwenden von Zentralen Bereitstellungs-PowerShell-Cmdlets zum Verwalten von Add-Ins](https://docs.microsoft.com/microsoft-365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)
  
[Problembehandlung: Dem Benutzer werden keine Add-Ins angezeigt](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
