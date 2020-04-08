---
title: Verwalten der Bereitstellung von Office 365-Add-Ins im Admin Center
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: get-started-article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: Hier erfahren Sie, wie Sie Add-Ins für Benutzer und Gruppen in Ihrer Organisation mithilfe einer zentralisierten Bereitstellung im Admin Center bereitstellen können.
ms.openlocfilehash: 74c1ceb8e9d2193e7ad7afd2b339d29d54780517
ms.sourcegitcommit: 732bb72a0b5ae09cb39536185aa29d6097ec72fd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/08/2020
ms.locfileid: "43189009"
---
# <a name="manage-deployment-of-office-365-add-ins-in-the-microsoft-365-admin-center"></a>Verwalten der Bereitstellung von Office 365-Add-Ins im Microsoft 365 Admin Center

[] Office-Add-Ins helfen Ihnen beim Personalisieren Ihrer Dokumente und beim Optimieren der Art und Weise, wie Sie im Web auf Informationen zugreifen (lesen Sie [Erste Schritte mit Ihrem Office-Add-In](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). Als Administrator können Sie Office-Add-Ins für die Benutzer in Ihrer Organisation bereitstellen. Verwenden Sie dazu das Feature für die zentralisierte Bereitstellung im Microsoft 365 Admin Center.
  
Die zentrale Bereitstellung ist die empfohlene und funktionsreichste Möglichkeit für die meisten Administratoren, um Add-Ins für Benutzer und Gruppen innerhalb einer Organisation bereitzustellen. Weitere Informationen zum Ermitteln, ob die zentrale Bereitstellung in Ihrer Organisation genutzt werden kann, finden Sie unter [Ermitteln, ob die zentrale Bereitstellung von Add-Ins in Ihrer Office 365-Organisation funktioniert](centralized-deployment-of-add-ins.md).
  
Die zentrale Bereitstellung bietet die folgenden Vorteile:
  
- Ein globaler Administrator kann ein Add-in einem Benutzer, mehreren Benutzern über eine Gruppe oder allen im Mandanten direkt zuweisen.
    
- Wenn die entsprechende Office-Anwendung gestartet wird, wird das Add-In automatisch für den Benutzer heruntergeladen. Wenn das Add-In Add-In-Befehle unterstützt, wird das Add-In automatisch im Menüband der Office-Anwendung angezeigt.
    
- Add-Ins werden nicht mehr für Benutzer angezeigt, wenn der Administrator das Add-in deaktiviert oder löscht oder wenn der Benutzer aus Azure Active Directory oder aus einer Gruppe entfernt wird, der das Add-in zugewiesen ist.
    
> [!NOTE]
>  Für Word verwenden Excel und PowerPoint einen [SharePoint-App-Katalog](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) zum Bereitstellen von Add-Ins für Benutzer in einer lokalen Umgebung ohne Verbindung mit Office 365 und/oder Unterstützung für SharePoint-Add-Ins erforderlich. >  Verwenden Sie für Outlook die Exchange-Systemsteuerung in einer lokalen Umgebung ohne Verbindung zu Office 365. > 
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>Empfohlene Vorgehensweise für die Bereitstellung von Office-Add-ins

Erwägen Sie, Add-Ins schrittweise bereitzustellen, um zu gewährleisten, dass die Bereitstellung der Add-Ins reibungslos verläuft. Hierbei wird folgender Plan empfohlen:
  
1. Stellen Sie das Add-In für eine kleine Gruppe von Projektbeteiligten und Mitgliedern der IT-Abteilung bereit. Überprüfen Sie, ob die Bereitstellung erfolgreich verlaufen ist, und fahren Sie in dem Fall mit Schritt 2 fort.
    
2. Stellen Sie das Add-In für eine größere Personengruppe im Unternehmen bereit, die das Add-In nutzen sollen. Überprüfen Sie die Ergebnisse erneut, und wenn alles erfolgreich verlaufen ist, fahren Sie mit dem nächsten Schritt der vollständigen Bereitstellung fest.
    
3. Stellen Sie das Add-In der gesamten Benutzerzielgruppe bereit.
    
Je nach Größe der Zielgruppe möchten Sie ggf. Bereitstellungsschritte hinzufügen oder entfernen.
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>Bereitstellen eines Office-Add-Ins mithilfe des Admin Centers

Lesen Sie zunächst [Ermitteln, ob die zentrale Bereitstellung von Add-Ins in Ihrer Office 365-Organisation funktioniert](centralized-deployment-of-add-ins.md).

  
1. Wechseln Sie im Microsoft 365 Admin Center zur Seite mit den **Einstellungen** > **-Add-ins** .
    
2. Wählen Sie oben auf der Seite **Add-in bereitstellen** aus. Wählen Sie auf der Seite Übersicht die Option **weiter**aus.
    
3. Wählen Sie eine Option aus, und folgen Sie den Anweisungen.
  
4. Wenn Sie die Option zum Hinzufügen eines Add-Ins aus dem Office Store ausgewählt haben, können Sie nun die Add-in-Auswahl vornehmen. Beachten Sie, dass Sie die verfügbaren Add-Ins nach den Kategorien **Für Sie vorgeschlagen**, **Bewertung** oder **Name** anzeigen können. Aus dem Office Store können nur kostenlose Add-Ins hinzugefügt werden. Kostenpflichtige Add-Ins werden derzeit nicht unterstützt. Nachdem Sie Ihr Add-in ausgewählt haben, müssen Sie einigen zusätzlichen Bedingungen zustimmen, damit Sie fortfahren können. <br/><br/> Hinweis: mit der Office Store Option werden Updates und Verbesserungen des Add-Ins automatisch für Benutzer ohne ihre Eingriffe zur Verfügung gestellt.

5. Wählen Sie auf der nächsten Seite die Option **jeder**, **bestimmte Benutzer/Gruppen** oder **nur mich** aus, um anzugeben, für wen das Add-in bereitgestellt wird. Verwenden Sie das Suchfeld, um die Benutzer oder Gruppen zu finden, für die Sie das Add-In bereitstellen möchten. <br/>Hinweis: Informationen zu den anderen Status, die für ein Add-in gelten. Weitere Informationen finden Sie unter [Add-in-Zustände](#add-in-states) weiter unten in diesem Thema.
  
6. Wählen Sie **Bereitstellen**.
  
7. Wenn das Add-in bereitgestellt wurde, wird ein grünes Häkchen angezeigt. Sie können den Anweisungen auf der Seite folgen, um zu testen, ob das Add-in erfolgreich bereitgestellt wurde.

> [!NOTE]
> Benutzer müssen möglicherweise Office neu starten, damit das Add-in-Symbol im Menüband der App angezeigt wird. Outlook-Add-Ins können bis zu 24 Stunden in Anspruch nehmen, um auf den Benutzer-menübändern angezeigt zu werden.
    
8. Wenn Sie fertig sind, wählen Sie **weiter**aus. Wenn Sie nur für sich selbst bereitgestellt haben, können Sie ändern auswählen, **der Zugriff auf das Add-in hat** , um mehr Benutzer bereitzustellen.



Wenn Sie das Add-in für andere Mitglieder Ihrer Organisation bereitgestellt haben, befolgen Sie die angezeigten Anweisungen, um die Bereitstellung des Add-ins effektiv anzukündigen. <br/>Sie sehen nun Ihr Add-In sowie andere Apps in Office 365.
  
Es empfiehlt sich, die Benutzer und Gruppen zu informieren, für die Sie das Add-In bereitstellen, damit diese wissen, dass es verfügbar ist. Erwägen Sie, im Rahmen eine E-Mail zu senden, das beschreibt, wann und wie das Add-In verwendet werden sollten und die erläutert, wie das Add-In ihnen helfen kann, ihre Arbeit besser zu erledigen. Einschließen oder verknüpfen Sie relevante Hilfeinhalte oder FAQs, die hilfreich sein können, wenn Benutzer Probleme mit dem Add-in haben.
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>Überlegungen beim Zuweisen eines Add-Ins zu Benutzern und Gruppen

Administratoren können jedem oder bestimmten Benutzern und Gruppen ein Add-In zuweisen. Jede Option hat Auswirkungen:
  
- **Jeder**: Wie der Name schon sagt, wird mit dieser Option das Add-In jedem Benutzer des Mandanten zugewiesen. Verwenden Sie diese Option nur in Ausnahmefällen, da sie wirklich die gesamte Organisation betrifft. 
    
- **Benutzer**: Wenn Sie ein Add-In nur einem einzelnen (neuen) Benutzer zuweisen möchten, muss dieser Benutzer zunächst hinzugefügt werden. Das Gleiche gilt für das Entfernen von Benutzern. 
    
- **Gruppen**: Wenn Sie ein Add-In einer Gruppe zuweisen, wird dieses den Benutzern, die der Gruppe hinzugefügt werden, automatisch zugewiesen. Wenn dann ein Benutzer aus der Gruppe entfernt wird, verliert dieser den Zugriff auf das Add-In. In beiden Fällen ist von Ihrer Seite als Administrator keine weitere Aktion erforderlich. 

- **Nur ich**: Wenn Sie ein Add-in nur für sich selbst zuweisen, wird das Add-in nur Ihrem Konto zugewiesen. Dies ist ideal, wenn Sie das Add-in zuerst testen möchten.
    
Die Option, die für Ihre Organisation richtig ist, hängt von Ihrer Konfiguration ab. Wir empfehlen jedoch Zuweisungen mithilfe von Gruppen vorzunehmen. Als Administrator finden Sie es möglicherweise einfacher, Add-Ins mithilfe von Gruppen zu verwalten und die Mitgliedschaft in diesen Gruppen zu steuern, anstatt jedes Mal die zugewiesenen Benutzer ändern zu müssen. Andererseits kann es Fälle geben, in denen Sie den Zugriff auf eine sehr kleine Gruppe von Benutzern beschränken möchten und das Add-In entsprechend nur bestimmten Benutzern zuweisen. In diesem Fall müssen Sie die zugewiesenen Benutzer manuell verwalten.
  
### <a name="add-in-states"></a>Add-In-Statusangaben

Administratoren können die Add-Ins, die Sie für alle Benutzer aus dem Microsoft 365 Admin Center bereitstellen, aktivieren oder deaktivieren.

1.    Wechseln Sie im Admin Center zur Seite **Einstellungen** > **-Add-ins** . 
2.    Wählen Sie das bereitgestellte Add-in aus. 
3.    Klicken Sie auf die **Status** -Umschaltfläche, um das Add-in **ein** -oder **auszuschalten.** 
4.    Speichern Sie die Änderungen.  

Einer von drei Add-in-Status steht ebenfalls zur Verfügung.
 
|**Status**|**Wie der Status eintritt**|**Auswirkung**|
|:-----|:-----|:-----|
|**Active**  <br/> |Der Administrator hat das Add-in hochgeladen und Benutzern oder Gruppen zugewiesen.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen sehen es im jeweiligen Client.  <br/> |
|**Deaktiviert**  <br/> |Der Administrator hat das Add-In deaktiviert.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr auf das Add-In zugreifen.  <br/> Wenn der Add-in-Zustand in " **aktiv**" geändert wird, können die Benutzer und Gruppen erneut darauf zugreifen.  <br/> |
|**Gelöscht**  <br/> |Der Administrator hat das Add-In gelöscht.  <br/> |Die dem Add-In zugewiesenen Benutzer und Gruppen können nicht mehr darauf zugreifen.  <br/> |
   
Sie sollten ein Add-in in einem Fall löschen, wenn es von keinem mehr verwendet wird. Das Deaktivieren eines Add-Ins ist möglicherweise sinnvoll, wenn ein Add-in nur zu bestimmten Jahreszeiten verwendet wird.
  
### <a name="security-of-office-add-ins"></a>Sicherheit von Office-Add-Ins

Office-Add-Ins sind eine Kombination aus einer XML-Manifestdatei, die einige Metadaten zum Add-In enthält, aber vor allem auf eine Webanwendung verweist, die den gesamten Code und die Logik enthält. Add-Ins können verschiedene Bereiche von Funktionen umfassen. So können Add-Ins beispielsweise Folgendes:
  
- Daten anzeigen.
    
- Das Dokument eines Benutzers lesen, um kontextbezogene Dienste zur Verfügung zu stellen.
    
- Daten im Dokument eines Benutzers lesen und in das Dokument schreiben, um diesem Benutzer einen Wert zu bieten.
    
Weitere Informationen zu den Typen und Funktionen von Office-Add-Ins finden Sie unter [Office-Add-Ins-Plattformübersicht](https://go.microsoft.com/fwlink/p/?linkid=846362), insbesondere im Abschnitt "Aufbau eines Office-Add-In".
  
Zur Interaktion mit dem Dokument des Benutzers muss das Add-In die erforderlichen Berechtigungen im Manifest deklarieren. Ein 5-stufiges JavaScript-API-Zugriffsberechtigungsmodell bildet die Grundlage für Datenschutz und Sicherheit für Benutzer der Aufgabenbereich-Add-Ins. Der Großteil der Add-Ins im Office Store weist die Berechtigungsstufe "ReadWriteDocument" auf, und fast alle Add-Ins unterstützen mindestens die Stufe "ReadDocument". Weitere Informationen zu den Berechtigungsstufen finden Sie unter [Anfordern von Berechtigungen zur API-Verwendung in Inhalts- und Aufgabenbereich-Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=848863).
  
Beim Aktualisieren eines Manifests werden in der Regel Änderungen am Symbol und Text eines Add-Ins vorgenommen. Gelegentlich ändern sich auch Add-In-Befehle. Die Berechtigungen des Add-Ins ändern sich jedoch nicht. Die Webanwendung, in der der gesamte Code und die Logik für das Add-In ausgeführt werden, kann sich jederzeit ändern. Dies liegt in der Natur von Webanwendungen.
  
Aktualisierungen für Add-Ins werden auf folgende Weise ausgeführt:
  
- **Line-of-Business-Add-In:** In diesem Fall, in dem ein Administrator ein Manifest explizit hochgeladen hat, erfordert das Add-In, dass der Administrator eine neue Manifestdatei zur Unterstützung von Metadatenänderungen hochlädt. Beim nächsten Starten der jeweiligen Office-Anwendungen wird das Add-In aktualisiert. Die Webanwendung kann sich jederzeit ändern. 

    > [!NOTE]
    > Administratoren müssen ein Lob-Add-in nicht für eine Aktualisierung entfernen.   Im Abschnitt Add-Ins kann der Administrator einfach auf das Lob-Add-in klicken und die **Schaltfläche Aktualisieren** in der unteren rechten Ecke auswählen. Das Update funktioniert nur, wenn die Version des neuen Add-ins größer ist als das des vorhandenen Add-Ins.   
    
- **Office Store-Add-In:** Wenn ein Administrator ein Add-In aus dem Office Store ausgewählt hat und dieses Add-In im Office Store aktualisiert wird, wird das Add-In später in der zentralen Bereitstellung aktualisiert. Beim nächsten Starten der jeweiligen Office-Anwendungen wird das Add-In aktualisiert. Die Webanwendung kann sich jederzeit ändern. 

### <a name="edit-add-in-access"></a>Bearbeiten des Add-in-Zugriffs

Nach der Bereitstellung können Administratoren auch den Benutzer Zugriff auf Add-Ins ändern.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** > für**Dienste &-Add-ins** .

2. Wählen Sie das bereitgestellte Add-in aus.

3. Klicken Sie unter **Wer hat Zugriff**auf **Bearbeiten** .
4. Speichern Sie die Änderungen.
    
### <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>Verhindern von Add-in-Downloads durch Deaktivieren der Office Store für alle Clients (außer Outlook)

> [!NOTE]
> Die Outlook-Add-in-Installation wird von einem [anderen Prozess](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)verwaltet.

Als Organisation möchten Sie möglicherweise verhindern, dass neue Office-Add-Ins aus dem Office Store heruntergeladen werden. Dies kann in Verbindung mit einer zentralisierten Bereitstellung verwendet werden, um sicherzustellen, dass nur von der Organisation genehmigte Add-Ins für Benutzer in Ihrer Organisation bereitgestellt werden.
  
So deaktivieren Sie die Add-in-Akquisition:
  
1. Wechseln Sie im Admin Center zur Seite **Einstellungen** \> [Dienste &amp; Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=2053743).
    
3. Wählen Sie **Benutzer eigene Apps und Dienste**aus.
    
4. Deaktivieren Sie die Option, Benutzern den Zugriff auf den Office Store zu ermöglichen.

Dadurch wird verhindert, dass alle Benutzer die folgenden Add-Ins aus dem Speicher erwerben.
  
- Add-Ins für Word, Excel und PowerPoint 2016 von:
    
  - Windows
    
  - Mac
    
  - Office
    
    
- Übernahmen, die in **AppSource** beginnen
    
- Add-Ins in Office 365
    
Ein Benutzer, der versucht, auf den Store zuzugreifen, wird die folgende Meldung angezeigt: **Sorry, Office 365 wurde so konfiguriert, dass die einzelne Akquisition von Office Store-Add-Ins verhindert wird.**
  
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
|Office 2016 ProPlus monatlich für Windows  <br/> |9001,2138   <br/> |
|Office 2016 ProPlus halbjährlich  <br/> |8431,2159  <br/> |
|Office 2016 für Windows  <br/> |16.0.4672.1000  <br/> |
|Office 2013 für Windows  <br/> |15.0.5023.1000  <br/> |
|Office 2016 für Mac  <br/> |16.11.18020200  <br/> |
|Office für das Web  <br/> |–  <br/> |
   
 **Für Outlook**: 
  
|||
|:-----|:-----|
|**Plattform** <br/> |**Buildnummer** <br/> |
|Outlook 2016 für Windows (MSI)  <br/> |Build kein feststellen  <br/> |
|Outlook 2016 für Windows (C2R)  <br/> |16.0.9323.1000  <br/> |
|Office 2016 für Mac  <br/> |16.0.9318.1000  <br/> |
|Outlook Mobile für IOS  <br/> |2.75.0  <br/> |
|Outlook Mobile für Android  <br/> |2.2.145  <br/> |
|Outlook.com  <br/> |–  <br/> |
   
 **Office 2013 Anforderungen**
  
Word-, Excel-und PowerPoint 2013 für Windows unterstützen dieselben geringfügigen Prüfungen, wenn Active Directory Authentifizierungsbibliothek (Adal) aktiviert ist. Es gibt zwei Optionen für die Compliance, wie weiter erläutert.
  
- **Aktivieren Sie Adal**. In diesem Artikel wird erläutert, wie Sie Adal für Office 2013 aktivieren: [verwenden Office 365 modernen Authentifizierung mit Office-Clients](https://support.office.com/article/776c0036-66fd-41cb-8928-5495c0f9168a).<br/>Sie müssen auch die Registrierungsschlüssel festlegen, um Adal zu aktivieren, wie unter [Aktivieren der modernen Authentifizierung für Office 2013 auf Windows-Geräten](../security-and-compliance/enable-modern-authentication.md)erläutert.<br/>Darüber hinaus müssen Sie die folgenden April-Updates für Office 2013 installieren:
    
  - [Beschreibung des Sicherheitsupdates für Office 2013:10. April 2018](https://support.microsoft.com/help/4018330/description-of-the-security-update-for-office-2013-april-10-2018)
    
  - [3. April 2018, Update für Office 2013 (KB4018333)](https://support.microsoft.com/help/4018333/april-3-2018-update-for-office-2013-kb4018333)
    
- **Aktivieren Sie Adal nicht**. Wenn Sie Adal nicht in Office 2013 aktivieren können, empfehlen wir die Verwendung von Gruppenrichtlinien zum Deaktivieren des Speichers für die Office-Clients. Informationen zum Deaktivieren der Einstellungen für die APP für Office finden Sie [hier](https://technet.microsoft.com/library/cc178992.aspx).
    
## <a name="end-user-experience-with-add-ins"></a>Benutzerfreundlichkeit bei Add-Ins

Nachdem Sie das Add-In bereitgestellt haben, können die Endbenutzer es in ihren Office-Anwendungen verwenden (siehe [Erste Schritte mit dem Office-Add-In](https://support.office.com/article/82e665c4-6700-4b56-a3f3-ef5441996862.aspx)). Das Add-In wird auf allen Plattformen angezeigt, die das Add-In unterstützt.
  
Wenn das Add-In Add-In-Befehle unterstützt, werden diese im Office-Menüband angezeigt. Im folgenden Beispiel wird der Befehl **Zitat suchen** für das Add-In **Zitate** angezeigt. 

![Office-Menüband mit Such Zitaten](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
Wenn das bereitgestellte Add-in keine Add-in-Befehle unterstützt oder wenn Sie alle bereitgestellten Add-Ins anzeigen möchten, können Sie diese über **Meine Add-ins**anzeigen. 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>In Word 2016, Excel 2016 oder PowerPoint 2016

1. Wählen **Sie \> meine Add-Ins einfügen**aus. 
    
2. Wählen Sie im Office-Add-In-Fenster die Schaltfläche **Vom Administrator verwaltet** aus. 
    
3. Doppelklicken Sie auf das Add-In, das Sie zuvor bereitgestellt haben (in diesem Beispiel **Zitate** ). <br/>![Registerkarte "verwalteter Administrator" der Seite "Office-Add-Ins"](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>In Outlook

1. Wählen Sie im Menüband **Start** die Option **Add-Ins abrufen**aus.<br/>![Schaltfläche "Speichern" in Outlook](../../media/getaddinsicon.png)
  
2. Wählen Sie im linken Navigationsbereich die Option **Admin-Managed** aus.

## <a name="delete-the-add-in"></a>Löschen des Add-ins

Sie können auch ein Add-in löschen, das bereitgestellt wurde.

1. Wechseln Sie im Admin Center zur Seite **Einstellungen** > für**Dienste &-Add-ins** .

2. Wählen Sie das bereitgestellte Add-in aus.

3. Klicken Sie auf **Add-in löschen**. Entfernen Sie die Add-in-Schaltfläche in der unteren rechten Ecke.
4. Überprüfen Sie Ihre Auswahl, und wählen Sie **Add-in entfernen**aus.
  
## <a name="learn-more"></a>Weitere Informationen

Weitere Informationen zum Erstellen von [Office-Add-Ins](https://go.microsoft.com/fwlink/p/?linkid=846362)
  
[Verwenden Sie PowerShell-Cmdlets für zentralisierte Bereitstellung zum Verwalten von Add-ins](https://support.office.com/article/94f4e86d-b8e5-42dd-b558-e6092f830ec9).
  
[Problembehandlung: Benutzer können keine Add-Ins sehen](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)
