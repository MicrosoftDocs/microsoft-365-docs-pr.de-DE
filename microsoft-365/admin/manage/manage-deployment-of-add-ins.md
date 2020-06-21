---
title: Verwalten der Bereitstellung von Add-Ins im Admin Center
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
ms.openlocfilehash: 25a4cd4147f6388cdbd8982eb10624e7b7e8f6cb
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780121"
---
# <a name="manage-deployment-of-add-ins-in-the-microsoft-365-admin-center"></a>Verwalten der Bereitstellung von Add-Ins im Microsoft 365 Admin Center

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end

[] Office-Add-Ins helfen Ihnen beim Personalisieren Ihrer Dokumente und beim Optimieren der Art und Weise, wie Sie im Web auf Informationen zugreifen (lesen Sie [Erste Schritte mit Ihrem Office-Add-In](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). Als Administrator können Sie Office-Add-Ins für die Benutzer in Ihrer Organisation bereitstellen. Verwenden Sie dazu das Feature für die zentralisierte Bereitstellung im Microsoft 365 Admin Center.
  
Die zentrale Bereitstellung ist die empfohlene und funktionsreichste Möglichkeit für die meisten Administratoren, um Add-Ins für Benutzer und Gruppen innerhalb einer Organisation bereitzustellen. Weitere Informationen zum ermitteln, ob Ihre Organisation eine zentralisierte Bereitstellung unterstützenkann, finden Sie unter [bestimmen, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert](centralized-deployment-of-add-ins.md).
  
Die zentrale Bereitstellung bietet die folgenden Vorteile:
  
- Ein globaler Administrator kann ein Add-in einem Benutzer, mehreren Benutzern über eine Gruppe oder allen im Mandanten direkt zuweisen.
    
- When the relevant Office application starts, the add-in automatically downloads for the user. If the add-in supports add-in commands, the add-in automatically appears in the Ribbon within the Office application.
    
- Add-Ins werden nicht mehr für Benutzer angezeigt, wenn der Administrator das Add-in deaktiviert oder löscht oder wenn der Benutzer aus Azure Active Directory oder aus einer Gruppe entfernt wird, der das Add-in zugewiesen ist.
    
> [!NOTE]
>  Für Word verwenden Excel und PowerPoint einen [SharePoint-App-Katalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) zum Bereitstellen von Add-Ins für Benutzer in einer lokalen Umgebung ohne Verbindung mit Microsoft 365 und/oder Unterstützung für SharePoint-Add-Ins erforderlich. > für Outlook verwenden Sie die Exchange-Systemsteuerung für die Bereitstellung in einer lokalen Umgebung ohne Verbindung mit Microsoft 365. > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Empfohlene Vorgehensweise für die Bereitstellung von Office-Add-Ins

Consider rolling out add-ins in a phased approach to help ensure your add-in deployment goes smoothly. We recommend the following plan:
  
1. Roll-out the add-in to a small set of business stakeholders and members of the IT department. Evaluate if the deployment was successful, and if so, move on to step 2.
    
2. Roll-out to a larger set of individuals within the business who will be using the add-in. Again, evaluate results and, if all went well, go to the next step of a full deployment.
    
3. Stellen Sie das Add-In der gesamten Benutzerzielgruppe bereit.
    
Je nach Größe der Zielgruppe möchten Sie ggf. Bereitstellungsschritte hinzufügen oder entfernen.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Bereitstellen eines Office-Add-Ins mithilfe des Admin Centers

Bevor Sie beginnen, lesen Sie [ermitteln, ob die zentrale Bereitstellung von Add-Ins für Ihre Organisation funktioniert](centralized-deployment-of-add-ins.md).

  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> **-Add-ins** .
    
2. Wählen Sie **Add-In bereitstellen** oben auf der Seite aus. Wählen Sie auf der Übersichtseite ** und als nächstes** aus.
    
3. Wählen Sie eine Option aus und folgen Sie den Anweisungen. 
  
4. Wenn Sie die Option zum Hinzufügen eines Add-Ins aus dem Office Store ausgewählt haben, können Sie nun die Add-in-Auswahl vornehmen. Beachten Sie, dass Sie die verfügbaren Add-Ins nach den Kategorien **Für Sie vorgeschlagen**, **Bewertung** oder **Name** anzeigen können. Aus dem Office Store können nur kostenlose Add-Ins hinzugefügt werden. Kostenpflichtige Add-Ins werden derzeit nicht unterstützt. Nachdem Sie Ihr Add-in ausgewählt haben, müssen Sie einigen zusätzlichen Bedingungen zustimmen, damit Sie fortfahren können. <br/><br/> Hinweis: mit der Office Store Option werden Updates und Verbesserungen des Add-Ins automatisch für Benutzer ohne ihre Eingriffe zur Verfügung gestellt.

5. Wählen Sie auf der nächsten Seite die Option **jeder**, **bestimmte Benutzer/Gruppen** oder **nur mich** aus, um anzugeben, für wen das Add-in bereitgestellt wird. Verwenden Sie das Suchfeld, um die Benutzer oder Gruppen zu finden, für die Sie das Add-In bereitstellen möchten. <br/>Hinweis: Informationen zu den anderen Status, die für ein Add-in gelten. Weitere Informationen finden Sie unter [Add-in-Zustände](#add-in-states) weiter unten in diesem Thema.
  
6. Wählen Sie **Bereitstellen**.
  
7. Wenn das Add-in bereitgestellt wurde, wird ein grünes Häkchen angezeigt. Folgen Sie den Anweisungen auf der Seite, um zu testen, ob das Add-In erfolgreich bereitgestellt wurde.

> [!NOTE]
> Benutzer müssen möglicherweise Office neu starten, damit das Add-in-Symbol im Menüband der App angezeigt wird. Outlook-Add-Ins können bis zu 24 Stunden in Anspruch nehmen, um auf den Benutzer-menübändern angezeigt zu werden.
    
8. Wenn Sie fertig sind, wählen Sie **weiter**aus. Wenn Sie nur für sich selbst bereitgestellt haben, können Sie ändern auswählen, **der Zugriff auf das Add-in hat** , um mehr Benutzer bereitzustellen.



Wenn Sie das Add-in für andere Mitglieder Ihrer Organisation bereitgestellt haben, befolgen Sie die angezeigten Anweisungen, um die Bereitstellung des Add-ins effektiv anzukündigen. <br/>Sie sehen nun Ihr Add-In zusammen mit andere Apps in Microsoft 365.
  
Es empfiehlt sich, die Benutzer und Gruppen zu informieren, für die Sie das Add-In bereitstellen, damit diese wissen, dass es verfügbar ist. Erwägen Sie, im Rahmen eine E-Mail zu senden, das beschreibt, wann und wie das Add-In verwendet werden sollten und die erläutert, wie das Add-In ihnen helfen kann, ihre Arbeit besser zu erledigen. Einschließen oder verknüpfen Sie relevante Hilfeinhalte oder FAQs, die hilfreich sein können, wenn Benutzer Probleme mit dem Add-in haben.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Überlegungen beim Zuweisen eines Add-Ins zu Benutzern und Gruppen

Admins can assign an add-in to everyone or to specific users and groups. Each option has implications:
  
- **Everyone**: As the name implies, this option assigns the add-in to every user in the tenant. Use this option sparingly and only for add-ins that are truly universal to your organization. 
    
- **Users**: If you assign an add-in to an individual user, then to deploy the add-in to a new user, you will need to first add that user. The same goes for removing users. 
    
- **Groups**: If you assign an add-in to a group, users who are added to the group will automatically be assigned the add-in. And, when a user is removed from a group, the user loses access to the add-in. In either case, no additional action is required from you as the admin. 

- **Nur ich**: Wenn Sie ein Add-in nur für sich selbst zuweisen, wird das Add-in nur Ihrem Konto zugewiesen. Dies ist ideal, wenn Sie das Add-in zuerst testen möchten.
    
Die Option, die für Ihre Organisation richtig ist, hängt von Ihrer Konfiguration ab. Wir empfehlen jedoch Zuweisungen mithilfe von Gruppen vorzunehmen. Als Administrator finden Sie es möglicherweise einfacher, Add-Ins mithilfe von Gruppen zu verwalten und die Mitgliedschaft in diesen Gruppen zu steuern, anstatt jedes Mal die zugewiesenen Benutzer ändern zu müssen. Andererseits kann es Fälle geben, in denen Sie den Zugriff auf eine sehr kleine Gruppe von Benutzern beschränken möchten und das Add-In entsprechend nur bestimmten Benutzern zuweisen. In diesem Fall müssen Sie die zugewiesenen Benutzer manuell verwalten.
  
### <a name="add-in-states"></a>Add-In-Status

Ein Add-in kann **entweder im Status ein oder** **aus** sein.
  
|**Status**|**Wie der Status eintritt**|**Auswirkung**|
|:-----|:-----|:-----|
|**Active**  <br/> |Der Administrator hat das Add-in hochgeladen und Benutzern oder Gruppen zugewiesen.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen sehen es im jeweiligen Client.  <br/> |
|**Deaktiviert**  <br/> |Der Administrator hat das Add-In deaktiviert.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr auf das Add-In zugreifen.  <br/> Wenn der Zustand des Add-Ins in "Aktiv" geändert wird, können die Benutzer und Gruppen wieder darauf zugreifen.  <br/> |
|**Gelöscht**  <br/> |Der Administrator hat das Add-In gelöscht.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr darauf zugreifen.  <br/> |
   
Sie sollten ein Add-in in einem Fall löschen, wenn es von keinem mehr verwendet wird. Das Deaktivieren eines Add-Ins ist möglicherweise sinnvoll, wenn ein Add-in nur zu bestimmten Jahreszeiten verwendet wird.
  
### <a name="security-of-office-add-ins"></a>Sicherheit von Office-Add-Ins

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

### <a name="edit-add-in-access"></a>Bearbeiten des Add-in-Zugriffs

Nach der Bereitstellung können Administratoren auch den Benutzer Zugriff auf Add-Ins ändern.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen**für  >  **Dienste &-Add-ins** .

2. Wählen Sie das bereitgestellte Add-in aus.

3. Klicken Sie unter **Wer hat Zugriff**auf **Bearbeiten** .
4. Speichern Sie die Änderungen.
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Verhindern von Add-in-Downloads durch Deaktivieren der Office Store für alle Clients (außer Outlook)

> [!NOTE]
> Die Outlook-Add-in-Installation wird von einem [anderen Prozess](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)verwaltet.

Als Organisation möchten Sie möglicherweise verhindern, dass neue Office-Add-Ins aus dem Office Store heruntergeladen werden. Dies kann in Verbindung mit einer zentralisierten Bereitstellung verwendet werden, um sicherzustellen, dass nur von der Organisation genehmigte Add-Ins für Benutzer in Ihrer Organisation bereitgestellt werden.
  
So deaktivieren Sie die Add-In-Übernahme:
  
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
  
Wenn Sie verhindern möchten, dass sich ein Benutzer mit einem Microsoft-Konto anmeldet, können Sie die Anmeldung einschränken, sodass nur das organisationskonto verwendet wird. Weitere Informationen finden Sie [hier](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx).
 
  
## <a name="minors-and-acquiring-add-ins-from-the-store"></a>Minderjährige und Erwerb von Add-Ins aus dem Store

Die allgemeine Datenschutzverordnung (dsgvo) ist eine Verordnung der Europäischen Union, die am 25. Mai 2018 wirksam wird. Es gibt Benutzern Rechte und Schutz Ihrer Daten. Einer der Aspekte des dsgvo ist, dass Minderjährige Ihre persönlichen Daten nicht an Parteien senden dürfen, die ihre Eltern oder Erziehungsberechtigten nicht genehmigt haben. Das spezifische Alter, das als Minderjährige definiert ist, hängt von der Region ab, in der sich die Person befindet.
  
Regionen mit gesetzlichen Bestimmungen zur elterlichen Zustimmung sind die Vereinigten Staaten, Südkorea, das Vereinigte Königreich und die Europäische Union. Für diese Regionen wird ein Minderjähriger (über Azure Active Directory) daran gehindert, neue Office-Add-Ins aus dem Store abzurufen und Add-Ins auszuführen, die zuvor erworben wurden. Für Länder ohne gesetzliche Bestimmungen gibt es keine Downloadbeschränkungen.
  
Ein Benutzer wird basierend auf den in Azure Active Directory angegebenen Daten als Minderjähriger festgelegt. Der mandantenadministrator ist für die Deklaration der legalen Altersgruppe und der elterlichen Zustimmung für diesen Benutzer verantwortlich.
  
Wenn der übergeordnete/Erziehungsberechtigte einem Minderjährigen unter Verwendung eines bestimmten Add-ins zustimmt, kann der mandantenadministrator die zentralisierte Bereitstellung verwenden, um das Add-in für alle Minderjährigen bereitzustellen, die Zustimmung haben.
  
Um dsgvo-konform für Minderjährige zu sein, müssen Sie sicherstellen, dass eine der folgenden Builds von Office in ihrer Schule/Organisation bereitgestellt wird.
  
 **Für Word, Excel, PowerPoint und Project**: 
  
|||
|:-----|:-----|
|**Plattform** <br/> |**Buildnummer** <br/> |
|Microsoft 365 apps for Enterprise (aktueller Kanal)  <br/> |9001,2138   <br/> |
|Microsoft 365-Apps für Unternehmen (halbjährlicher Enterprise-Kanal)  <br/> |8431,2159  <br/> |
|Office 2016 für Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 für Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 für Mac  <br/> |16.11.18020200  <br/> |
|Office für das Web  <br/> |Nicht zutreffend  <br/> |
   
 **Für Outlook**: 
  
|||
|:-----|:-----|
|**Plattform** <br/> |**Buildnummer** <br/> |
|Outlook 2016 für Windows (MSI)  <br/> |Build kein feststellen  <br/> |
|Outlook 2016 für Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 für Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile für IOS  <br/> |2.75.0  <br/> |
|Outlook Mobile für Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |Nicht zutreffend  <br/> |
   
 **Office 2013 Anforderungen**
  
Word-, Excel-und PowerPoint 2013 für Windows unterstützen dieselben geringfügigen Prüfungen, wenn Active Directory Authentifizierungsbibliothek (Adal) aktiviert ist. Es gibt zwei Optionen für die Compliance, wie weiter erläutert.
  
- **Aktivieren Sie Adal**. In diesem Artikel wird erläutert, wie Sie Adal für Office 2013 aktivieren: [Verwenden der modernen Authentifizierung von Microsoft 365 mit Office-Clients](https://docs.microsoft.com/office365/enterprise/modern-auth-for-office-2013-and-2016).<br/>Sie müssen auch die Registrierungsschlüssel festlegen, um Adal zu aktivieren, wie unter [Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten](../security-and-compliance/enable-modern-authentication.md)erläutert.<br/>Darüber hinaus müssen Sie die folgenden April-Updates für Office 2013 installieren:
    
  - [Beschreibung des Sicherheitsupdates für Office 2013:10. April 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3. April 2018, Update für Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Aktivieren Sie Adal nicht**. Wenn Sie Adal nicht in Office 2013 aktivieren können, empfehlen wir die Verwendung von Gruppenrichtlinien zum Deaktivieren des Speichers für die Office-Clients. Informationen zum Deaktivieren der Einstellungen für die APP für Office finden Sie [hier](https://technet.microsoft.com/library/cc178992.aspx).
    
## <a name="end-user-experience-with-add-ins"></a>Benutzerfreundlichkeit bei Add-Ins

Now that you've deployed the add-in, your end users can start using it in their Office applications (see [Start using your Office Add-in](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)). The add-in will appear on all platforms that the add-in supports.
  
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

## <a name="delete-the-add-in"></a>Löschen des Add-ins

Sie können auch ein Add-in löschen, das bereitgestellt wurde.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen**für  >  **Dienste &-Add-ins** .

2. Wählen Sie das bereitgestellte Add-in aus.

3. Klicken Sie auf **Add-in löschen**. Entfernen Sie die Add-In-Schaltfläche in der unteren rechten Ecke.
4. Überprüfen Sie Ihre Auswahl und wählen Sie **Add-In entfernen**aus.
  
## <a name="learn-more"></a>Weitere Informationen

Weitere Informationen zum Erstellen von [Office-Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=846362)
  
[Verwenden Sie PowerShell-Cmdlets für zentralisierte Bereitstellung zum Verwalten von Add-ins](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins).
  
[Problembehandlung: Benutzer können keine Add-Ins sehen](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
