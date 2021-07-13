---
title: Bereitstellen von Add-Ins im Admin Center
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
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Erfahren Sie, wie Sie Add-Ins für Benutzer und Gruppen in Ihrer Organisation mithilfe der zentralen Bereitstellung im Admin Center bereitstellen.
ms.openlocfilehash: 88613e593f3c8375073865ebe9b7e417c6b3f06f
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392851"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>Bereitstellen von Add-Ins im Admin Center

[] Office-Add-Ins helfen Ihnen beim Personalisieren Ihrer Dokumente und beim Optimieren der Art und Weise, wie Sie im Web auf Informationen zugreifen (lesen Sie [Erste Schritte mit Ihrem Office-Add-In](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Als Administrator können Sie Office-Add-Ins für die Benutzer in Ihrer Organisation bereitstellen, indem Sie das Feature für die zentrale Bereitstellung im Microsoft 365 Admin Center verwenden. Die zentrale Bereitstellung ist die empfohlene und funktionsreichere Möglichkeit für die meisten Administratoren, Add-Ins für Benutzer und Gruppen innerhalb einer Organisation bereitzustellen.

Weitere Informationen zum Ermitteln, ob Ihre Organisation die zentrale Bereitstellung unterstützen kann, finden Sie unter ["Ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert".](centralized-deployment-of-add-ins.md)

Weitere Informationen zum Verwalten von Add-Ins nach der Bereitstellung finden Sie unter [Verwalten von Add-Ins im Admin Center](manage-addins-in-the-admin-center.md)
  
> [!NOTE]
>  Für Word verwenden Excel und PowerPoint einen [SharePoint App-Katalog,](/office/dev/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) um Add-Ins für Benutzer in einer lokalen Umgebung ohne Verbindung zu Microsoft 365 und/oder Unterstützung für SharePoint Add-Ins bereitzustellen. Verwenden Sie für Outlook Exchange Systemsteuerung, um die Bereitstellung in einer lokalen Umgebung ohne Verbindung mit Microsoft 365 durchzuführen.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Empfohlene Vorgehensweise für die Bereitstellung von Office-Add-Ins

Zum Rollout von Add-Ins mithilfe eines stufenweisen Ansatzes empfehlen wir Folgendes:
  
1. Stellen Sie das Add-In für eine kleine Gruppe von Projektbeteiligten und Mitgliedern der IT-Abteilung bereit. Wenn die Bereitstellung erfolgreich ist, fahren Sie mit Schritt 2 fort.
    
2. Stellen Sie das Add-In für weitere Personen innerhalb des Unternehmens bereit. Bewerten Sie erneut die Ergebnisse, und fahren Sie bei erfolgreicher Ausführung mit der vollständigen Bereitstellung fort.
    
3. Durchführen eines vollständigen Rollouts für alle Benutzer.
    
Je nach Größe der Zielgruppe können Sie Rolloutschritte hinzufügen oder entfernen.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Bereitstellen eines Office-Add-Ins mithilfe des Admin Centers

Bevor Sie beginnen, lesen [Sie, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert.](centralized-deployment-of-add-ins.md)
  
1. Wechseln Sie im Admin Center zur **Seite Einstellungen** \> **Add-Ins.** Wenn die **Add-In-Seite** nicht angezeigt wird, wechseln Sie zur Seite **Einstellungen** \> **Integrierte** \> **Apps-Add-Ins.**

2. Wählen Sie **"Add-In bereitstellen"** oben auf der Seite und dann **"Weiter"** aus.

    > [!NOTE]
    > Das Admin Center wird auf die Bereitstellungserfahrung mit integrierten Apps aktualisiert. Integrierte Apps sind nur für globale Administratoren sichtbar, während für andere die alte Erfahrung noch vorhanden ist. Wenn die oben beschriebenen Schritte nicht angezeigt werden, wechseln Sie zum Abschnitt "Zentrale Bereitstellung", indem Sie zu **Einstellungen**  >  **integrierten Apps** wechseln. Wählen Sie oben auf der Seite **"Integrierte Apps"** die Option **"Add-Ins" aus.**

3. Wählen Sie eine Option aus und folgen Sie den Anweisungen. 
  
4. Wenn Sie die Option zum Hinzufügen eines Add-Ins aus dem Office Store ausgewählt haben, wählen Sie das Add-In aus. </br>

    Sie können verfügbare Add-Ins nach Kategorien anzeigen: **Vorgeschlagen für Sie,** **Bewertung** oder **Name.** Im Office Store sind nur kostenlose Add-Ins verfügbar. Kostenpflichtige Add-Ins werden derzeit nicht unterstützt. Nachdem Sie ein Add-In ausgewählt haben, akzeptieren Sie die Geschäftsbedingungen, um fortzufahren. <br/> 

    > [!NOTE]
    > Mit der Option Office Store werden Updates und Verbesserungen automatisch für Benutzer bereitgestellt.

5. Wählen Sie auf der nächsten Seite **Alle**, **Bestimmte Benutzer/Gruppen** oder **Nur ich** aus, um anzugeben, für wen das Add-in bereitgestellt wird. Verwenden Sie das Suchfeld, um nach bestimmten Benutzern oder Gruppen zu suchen. <br/>

    > [!NOTE]
    > Weitere Informationen zu anderen Zuständen, die für ein Add-In gelten, finden Sie unter [Add-In-Zustände.](./manage-addins-in-the-admin-center.md)
  
6. Wählen Sie **Bereitstellen**.
  
7. Ein grünes Teilstrich wird angezeigt, wenn das Add-In bereitgestellt wird. Befolgen Sie die Anweisungen auf der Seite, um das Add-In zu testen.

    > [!NOTE]
    > Benutzer müssen möglicherweise Office neu starten, um das Add-In-Symbol auf dem App-Menüband anzuzeigen. Outlook Add-Ins können bis zu 24 Stunden dauern, bis sie auf App-Menübändern angezeigt werden.

8. Wenn Sie fertig sind, wählen Sie **Weiter**. Wenn Sie nur für sich selbst bereitgestellt haben, können Sie **"Ändern" auswählen, wer Zugriff auf das Add-In hat,** um weitere Benutzer bereitzustellen.

    Wenn Sie das Add-In für andere Mitglieder Ihrer Organisation bereitgestellt haben, befolgen Sie die Anweisungen, um die Bereitstellung des Add-Ins anzukündigen. <br/>
  
    Es empfiehlt sich, Benutzer und Gruppen darüber zu informieren, dass das bereitgestellte Add-In verfügbar ist. Erwägen Sie das Senden einer E-Mail, die beschreibt, wann und wie das Add-In verwendet wird. Einschließen oder Verknüpfen von Hilfeinhalten oder häufig gestellten Fragen, die Benutzern bei Problemen mit dem Add-In helfen können.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Überlegungen beim Zuweisen eines Add-Ins zu Benutzern und Gruppen

Globale Administratoren und Exchange Administratoren können jedem oder bestimmten Benutzern und Gruppen ein Add-In zuweisen. Jede Option hat Auswirkungen:
  
- **Jeder** Diese Option weist das Add-In jedem Benutzer in der Organisation zu. Verwenden Sie diese Option nur in Ausnahmefällen, da sie wirklich die gesamte Organisation betrifft.

- **Benutzer** Wenn Sie einem einzelnen Benutzer ein Add-In zuweisen und das Add-In dann für einen neuen Benutzer bereitstellen, müssen Sie zuerst den neuen Benutzer hinzufügen.

- **Gruppen** Wenn Sie einer Gruppe ein Add-In zuweisen, wird Benutzern, die der Gruppe hinzugefügt werden, automatisch das Add-In zugewiesen. Wenn ein Benutzer aus einer Gruppe entfernt wird, verliert der Benutzer den Zugriff auf das Add-In. In beiden Fällen ist keine zusätzliche Aktion vom Administrator erforderlich.

- **Nur ich** Wenn Sie ein Add-In nur sich selbst zuweisen, wird das Add-In nur Ihrem Konto zugewiesen, das ideal zum Testen des Add-Ins geeignet ist.

Die richtige Option für Ihre Organisation hängt von Ihrer Konfiguration ab. Es wird jedoch empfohlen, Aufgaben mithilfe von Gruppen vorzunehmen. Als Administrator finden Sie es möglicherweise einfacher, Add-Ins mithilfe von Gruppen zu verwalten und die Mitgliedschaft dieser Gruppen zu steuern, anstatt jedes Mal einzelne Benutzer zuzuweisen. In einigen Situationen können Sie den Zugriff auf eine kleine Gruppe von Benutzern einschränken, indem Sie bestimmten Benutzern Zuweisungen vornehmen, indem Sie Benutzer manuell zuweisen.
  
## <a name="more-about-office-add-ins-security"></a>Weitere Informationen zur Sicherheit von Office-Add-Ins

Office-Add-Ins sind eine Kombination aus einer XML-Manifestdatei, die einige Metadaten zum Add-In enthält, aber vor allem auf eine Webanwendung verweist, die den gesamten Code und die Logik enthält. Add-Ins können verschiedene Bereiche von Funktionen umfassen. So können Add-Ins beispielsweise Folgendes:
  
- Daten anzeigen.

- Das Dokument eines Benutzers lesen, um kontextbezogene Dienste zur Verfügung zu stellen.

- Daten im Dokument eines Benutzers lesen und in das Dokument schreiben, um diesem Benutzer einen Wert zu bieten.

Weitere Informationen zu den Typen und Funktionen von Office-Add-Ins finden Sie unter [Office-Add-Ins-Plattformübersicht](/office/dev/add-ins/overview/office-add-ins), insbesondere im Abschnitt "Aufbau eines Office-Add-In".
  
Zur Interaktion mit dem Dokument des Benutzers muss das Add-In die erforderlichen Berechtigungen im Manifest deklarieren. Ein 5-stufiges JavaScript-API-Zugriffsberechtigungsmodell bildet die Grundlage für Datenschutz und Sicherheit für Benutzer der Aufgabenbereich-Add-Ins. Der Großteil der Add-Ins im Office Store weist die Berechtigungsstufe "ReadWriteDocument" auf, und fast alle Add-Ins unterstützen mindestens die Stufe "ReadDocument". Weitere Informationen zu den Berechtigungsstufen finden Sie unter [Anfordern von Berechtigungen zur API-Verwendung in Inhalts- und Aufgabenbereich-Add-Ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins).
  
Beim Aktualisieren eines Manifests werden in der Regel Änderungen am Symbol und Text eines Add-Ins vorgenommen. Gelegentlich ändern sich auch Add-In-Befehle. Die Berechtigungen des Add-Ins ändern sich jedoch nicht. Die Webanwendung, in der der gesamte Code und die Logik für das Add-In ausgeführt werden, kann sich jederzeit ändern. Dies liegt in der Natur von Webanwendungen.
  
Aktualisierungen für Add-Ins werden auf folgende Weise ausgeführt:
  
- **Line-of-Business-Add-In:** In diesem Fall, in dem ein Administrator ein Manifest explizit hochgeladen hat, erfordert das Add-In, dass der Administrator eine neue Manifestdatei zur Unterstützung von Metadatenänderungen hochlädt. Beim nächsten Starten der jeweiligen Office-Anwendungen wird das Add-In aktualisiert. Die Webanwendung kann sich jederzeit ändern.

    > [!NOTE]
    > Der Administrator muss kein Lob-Add-In für ein Update entfernen.   Im Abschnitt "Add-Ins" kann der Administrator einfach auf das Branchen-Add-In klicken und die **Schaltfläche "Aktualisieren"** in der unteren rechten Ecke auswählen. Das Update funktioniert nur, wenn die Version des neuen Add-Ins größer als die des vorhandenen Add-Ins ist.

- **Office Store-Add-In:** Wenn ein Administrator ein Add-In aus dem Office Store ausgewählt hat und dieses Add-In im Office Store aktualisiert wird, wird das Add-In später in der zentralen Bereitstellung aktualisiert. Beim nächsten Starten der jeweiligen Office-Anwendungen wird das Add-In aktualisiert. Die Webanwendung kann sich jederzeit ändern.
  
## <a name="related-content"></a>Verwandte Inhalte

[Verwalten von Add-Ins im Admin Center](manage-addins-in-the-admin-center.md) (Artikel)\
[Erstellen Ihres ersten Word-Aufgabenbereich-Add-Ins](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator) (Artikel\
[Minderjährige und Erwerb von Add-Ins aus dem Store](minors-and-acquiring-addins-from-the-store.md) (Artikel)\ [Verwenden Sie powerShell-Cmdlets für die zentrale Bereitstellung, um Add-Ins zu verwalten](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md) (Artikel)\  
[Problembehandlung: Benutzer sehen keine Add-Ins](/office365/troubleshoot/access-management/user-not-seeing-add-ins) (Artikel)