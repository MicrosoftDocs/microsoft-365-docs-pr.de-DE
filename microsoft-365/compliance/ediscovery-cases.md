---
title: Verwalten von eDiscovery-Fällen im Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
ms.assetid: 8dd335ab-29d0-41c3-8dd8-9f7c7481e60c
description: 'Verwenden Sie das Security #a0 Compliance Center, um eDiscovery-Fälle in Ihrer Organisation zu erstellen und zu verwalten. Sie können dem Fall Mitglieder zuweisen, inhaltsspeicherorte in der Warteschleife platzieren, mit der Anfrage verknüpfte Inhalts Suchvorgänge ausführen und die Suchergebnisse exportieren. Sie können auch die Falldaten für eine weitere Analyse in Office 365 Advanced eDiscovery vorbereiten.'
ms.openlocfilehash: 6cc0cb0a709463be0e624162555dd221564b4dd3
ms.sourcegitcommit: 570ad1c7c334476ecec00dc355dfe52e8c2bb87b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/08/2020
ms.locfileid: "41862105"
---
# <a name="manage-ediscovery-cases-in-the-security--compliance-center"></a>Verwalten von eDiscovery-Fällen im Security & Compliance Center

Sie können eDiscovery-Fälle im Compliance Center in Office 365 und Microsoft 365 verwenden, um zu steuern, wer eDiscovery-Fälle in Ihrer Organisation erstellen, auf Sie zugreifen und diese verwalten kann. Wenn Ihre Organisation über ein Office 365 E5-Abonnement verfügt, können Sie auch mithilfe von eDiscovery-Fällen Suchergebnisse mithilfe Office 365 Advanced eDiscovery analysieren.
  
Mit einem eDiscovery-Fall können Sie einem Fall Mitglieder hinzufügen, Steuern, welche Arten von Aktionen von bestimmten Fall Mitgliedern ausgeführt werden können, Aufbewahrungsmöglichkeiten für für einen Rechtsfall relevanter Inhaltsspeicher platzieren und mehrere Inhalts suchen mit einem einzigen Fall verknüpfen. Sie können auch die Ergebnisse einer beliebigen Inhaltssuche exportieren, die einem Fall zugeordnet ist, oder Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten. eDiscovery-Fälle sind eine gute Möglichkeit, um zu beschränken, wer Zugriff auf Inhaltssuchen und Suchergebnisse für einen bestimmten Rechtsfall in Ihrer Organisation hat.
  
Verwenden Sie den folgenden Workflow, um eDiscovery-Fälle im Security #a0 Compliance Center und in Advanced eDiscovery einzurichten und zu verwenden.

[Step 1: Assign eDiscovery permissions to potential case members](#step-1-assign-ediscovery-permissions-to-potential-case-members)

[Schritt 2: Erstellen einer neuen Anfrage](#step-2-create-a-new-case)

[Schritt 3: Hinzufügen von Mitgliedern zu einer Anfrage](#step-3-add-members-to-a-case)

[Schritt 4: Platzieren von Inhaltsspeicherorten in der Warteschleife](#step-4-place-content-locations-on-hold)

[Schritt 5: Erstellen und Ausführen einer einem Fall zugeordneten Inhaltssuche](#step-5-create-and-run-a-content-search-associated-with-a-case)

[Schritt 6: Exportieren der Ergebnisse einer Inhaltssuche, die einer Anfrage zugeordnet ist](#step-6-export-the-results-of-a-content-search-associated-with-a-case)

[Schritt 7: Vorbereiten der Suchergebnisse für Advanced eDiscovery](#step-7-prepare-search-results-for-advanced-ediscovery)

[Schritt 8: Wechseln zu der Groß-/Kleinschreibung in Advanced eDiscovery](#step-8-go-to-the-case-in-advanced-ediscovery)

[Optional Schritt 9: Schließen eines Falls](#optional-step-9-close-a-case)

[Optional Schritt 10: Erneutes Öffnen eines geschlossenen Falls](#optional-step-10-re-open-a-closed-case)

[Weitere Informationen](#more-information)
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a>Schritt 1: Zuweisen von eDiscovery-Berechtigungen zu potenziellen Fallmitgliedern

Der erste Schritt besteht darin, Personen die entsprechenden eDiscovery-bezogenen Berechtigungen zuzuweisen, damit Sie Sie in Schritt 2 zu einem eDiscovery-Fall hinzufügen können. Sie müssen Mitglied der Rollengruppe "Organisationsverwaltung" (oder der Rolle "Rollenverwaltung" zugewiesen) im Sicherheits #a0 Compliance Center sein, um eDiscovery-Berechtigungen zuzuweisen. In der folgenden Liste werden die eDiscovery-bezogenen Rollengruppen im Security #a0 Compliance Center beschrieben. 
  
- **Prüfer.** Diese Rollengruppe verfügt über die restriktivsten Berechtigungen in Bezug auf eDiscovery. Der primäre Zweck dieser Rollengruppe besteht darin, Mitgliedern das Anzeigen und Zugreifen auf Falldaten in [Office 365 Advanced](office-365-advanced-ediscovery.md) eDiscovery (auch bekannt als *Advanced eDiscovery v1*) zu ermöglichen. Mitglieder dieser Gruppe können die Liste der Fälle auf der Seite " **eDiscovery** " im Security #a0 Compliance Center nur anzeigen und öffnen, von der Sie Mitglieder sind. Nachdem der Benutzer im Security and Compliance Center auf einen Fall zugegriffen hat, kann er auf " **Advanced eDiscovery" wechseln** , um auf die Falldaten in Advanced eDiscovery zuzugreifen und diese zu analysieren. Sie können keine Fälle erstellen, einem Fall Mitglieder hinzufügen, Aufbewahrungen erstellen, Suchergebnisse in der Vorschau anzeigen, Suchergebnisse exportieren oder Ergebnisse für Advanced eDiscovery vorbereiten. 

   > [!NOTE]
   > Zu diesem Zeitpunkt können Benutzer, die Mitglied der Rollengruppe Prüfer sind, nicht auf Daten in [Advanced eDiscovery in Microsoft 365](overview-ediscovery-20.md) (auch bekannt als *Advanced eDiscovery v2*) zugreifen. Wenn Sie einem Fall in Advanced eDiscovery v2 Mitglieder hinzufügen möchten, damit Sie die Falldaten überprüfen können, muss ein Benutzer Mitglied der Rollengruppe "eDiscovery-Manager" sein.
    
- **eDiscovery-Manager.** Mitglieder dieser Rollengruppe können eDiscovery-Fälle erstellen und verwalten. Sie können Mitglieder hinzufügen und entfernen, inhaltsspeicherorte in der Warteschleife platzieren, Inhalts suchen, die einem Fall zugeordnet sind, erstellen und bearbeiten, die Ergebnisse einer Inhaltssuche exportieren und Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten. In dieser Rollengruppe gibt es zwei Untergruppen. Der Unterschied zwischen diesen Untergruppen basiert auf dem Bereich.
    
  - **eDiscovery-Manager.** Kann die eDiscovery-Fälle anzeigen und verwalten, in denen Sie erstellt werden oder deren Mitglied Sie sind. Wenn ein anderer eDiscovery-Manager einen Fall erstellt, aber keinen zweiten eDiscovery-Manager als Mitglied dieses Falles hinzufügt, kann der zweite eDiscovery-Manager den Fall nicht auf der **eDiscovery** -Seite im Security #a0 Compliance Center anzeigen oder öffnen. eDiscovery-Manager können auch auf ihre Fälle in Advanced eDiscovery zugreifen, um Analyseaufgaben durchzuführen. 
    
  - **eDiscovery-Administrator *.** Kann alle Fall Verwaltungsaufgaben ausführen, die ein eDiscovery-Manager ausführen kann. Darüber hinaus können eDiscovery-Administratoren folgende Aktionen durchführen:
    
    - Anzeigen aller Fälle, die auf der Seite **eDiscovery-Fälle** aufgeführt sind. 
    
    - Verwalten Sie alle Fälle in der Organisation, nachdem Sie sich selbst als Mitglied der Anfrage hinzugefügt haben.
    
    - Zugriffs Fall Daten in Advanced eDiscovery für jeden Fall in der Organisation.
    
    Überlegungen dazu, warum Sie ggf. einen eDiscovery-Administrator in Ihrer Organisation benötigen, finden Sie im Abschnitt [More information](#more-information). 
    
> [!IMPORTANT]
> Wenn eine Person nicht Mitglied einer dieser eDiscovery-bezogenen Rollengruppen ist oder kein Mitglied einer Rollengruppe ist, der die Rolle "Prüfer" zugewiesen ist, können Sie Sie nicht als Mitglied eines eDiscovery-Falls hinzufügen. 

Weitere Informationen zu eDiscovery-Berechtigungen finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).
  
 **So weisen Sie eDiscovery-Berechtigungen zu**
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto bei Office 365 an.
    
3. Klicken Sie im Security #a0 Compliance Center auf **Berechtigungen**, und führen Sie eine der folgenden Aktionen basierend auf den eDiscovery-Berechtigungen aus, die Sie zuweisen möchten.
    
    - Um Prüferberechtigungen zuzuweisen, wählen Sie die Rollengruppe **Prüfer** aus, und klicken Sie dann neben **Mitglieder**auf **Bearbeiten**. Klicken Sie auf **Mitglieder auswählen**, klicken Sie auf **Bearbeiten**, klicken Sie auf ![Symbol](media/ITPro-EAC-AddIcon.gif) **hinzu**fügen, wählen Sie den Benutzer aus, den Sie der Rollengruppe Prüfer hinzufügen möchten, und klicken Sie dann auf **hinzu**fügen.
    
    - Um eDiscovery Manager-Berechtigungen zuzuweisen, wählen Sie die Rollengruppe **eDiscovery-** Manager aus, und klicken Sie dann neben **eDiscovery-Manager**auf **Bearbeiten**. Klicken Sie auf **eDiscovery-Manager auswählen**, klicken ![Sie auf](media/ITPro-EAC-AddIcon.gif) **Bearbeiten**, klicken Sie auf Symbol hinzufügen * * Add * *, wählen Sie den Benutzer aus, den Sie als eDiscovery-Manager hinzufügen möchten, und klicken Sie dann auf **Hinzufügen**.
    
    - Um eDiscovery-Administratorberechtigungen zuzuweisen, wählen Sie die Rollengruppe **eDiscovery-Manager** aus, und klicken Sie dann neben **eDiscovery-Administrator**auf **Bearbeiten**. Klicken Sie auf **eDiscovery-Administrator auswählen**, klicken ![Sie auf](media/ITPro-EAC-AddIcon.gif) **Bearbeiten**, klicken Sie **auf Symbol hinzufügen,** wählen Sie den Benutzer aus, den Sie als eDiscovery-Administrator hinzufügen möchten, und klicken Sie dann auf **hinzu**fügen.
    
4. Nachdem Sie alle Benutzer hinzugefügt haben, klicken Sie auf **Fertig**, klicken Sie auf **Speichern** , um die Änderungen an der Rollengruppe zu speichern, und klicken Sie dann auf **Schließen**.

## <a name="step-2-create-a-new-case"></a>Schritt 2: Erstellen einer neuen Anfrage

Der nächste Schritt besteht darin, einen eDiscovery-Fall zu erstellen. Sie müssen Mitglied der Rollengruppe „eDiscovery-Manager“ sein, um eDiscovery-Fälle zu erstellen. Wie bereits erläutert, können Sie (und andere Fall Mitglieder) nach dem Erstellen eines Falls im Security #a0 Compliance Center auf denselben Fall in Advanced eDiscovery zugreifen, wenn Ihre Organisation über ein Office 365 E5-Abonnement verfügt.
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto bei Office 365 an.
    
3. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery**, und klicken Sie ![dann auf](media/ITPro-EAC-AddIcon.gif) Symbol hinzufügen, **um eine Anfrage zu erstellen**.
    
4. Geben Sie auf der Seite **neuer Fall** einen Namen ein, geben Sie eine optionale Beschreibung ein, und klicken Sie dann auf **Speichern**. Der Case-Name muss in Ihrer Organisation eindeutig sein.
    
    ![Erstellen einer Anfrage](media/7f78f83b-1525-4c77-9888-4b6bda1e148d.png)
  
    Der neue Fall wird in der Liste der Fälle auf der **eDiscovery** -Seite angezeigt. Sie können den Mauszeiger über einen Fallnamen bewegen, um Informationen über den Fall anzuzeigen, einschließlich des Status der Anfrage (**aktiv** oder **geschlossen**), der Beschreibung des Falls (die im vorherigen Schritt erstellt wurde), und wenn der Fall zuletzt geändert wurde und wer ihn geändert hat.
    
    > [!TIP]
    > Nachdem Sie einen neuen Fall erstellt haben, können Sie ihn jederzeit umbenennen. Klicken Sie auf der **eDiscovery** -Seite einfach auf den Namen des Falls. Ändern Sie auf der Seite **diesen Fall Flyout verwalten** den Namen, der in dem Feld unter **Name**angezeigt wird, und speichern Sie die Änderung. 
  
## <a name="step-3-add-members-to-a-case"></a>Schritt 3: Hinzufügen von Mitgliedern zu einer Anfrage

Nachdem Sie einen Fall erstellt haben, besteht der nächste Schritt darin, der Anfrage Mitglieder hinzuzufügen. Wie zuvor erläutert, können nur Benutzer, die Mitglieder der Rollengruppen Prüfer oder eDiscovery-Manager sind, als Mitglieder der Anfrage hinzugefügt werden. Der eDiscovery-Manager, der den Fall erstellt hat, wird automatisch als Mitglied hinzugefügt.
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie auf den Namen des Falls, dem Sie Mitglieder hinzufügen möchten.
    
    Die Dropdown Seite **diesen Fall verwalten** wird angezeigt. 
    
    ![Verwalten einer Fall Flyout-Seite](media/11f35ceb-6c98-4580-a3bc-ad688e9c7af9.png)
  
3. Klicken Sie ![unter **Mitglieder verwalten**auf Symbol](media/ITPro-EAC-AddIcon.gif) **hinzu** fügen, um der Anfrage Mitglieder hinzuzufügen. 
    
    Sie können auch eine Rollengruppe zur Anfrage hinzufügen. Klicken Sie unter **Rollengruppen verwalten**auf ![Symbol](media/ITPro-EAC-AddIcon.gif) **hinzu**fügen.
    
    > [!NOTE]
    > Rollengruppen steuern, wer einem eDiscovery-Fall Mitglieder zuweisen kann. Das bedeutet, dass Sie den Rollengruppen, denen Sie angehören, nur eine Anfrage zuweisen können.
    
4. Klicken Sie in der Liste der Personen oder Rollengruppen, die als Mitglieder der Anfrage hinzugefügt werden können, auf das Kontrollkästchen neben den Namen der Personen oder Rollengruppen, die Sie hinzufügen möchten.
    
    > [!TIP]
    > Wenn Sie eine große Liste von Personen haben, die als Mitglieder hinzugefügt werden können, verwenden Sie das **Suchfeld** , um nach einer bestimmten Person in der Liste zu suchen. 
  
5. Nachdem Sie die Personen oder Rollengruppen ausgewählt haben, die als Mitglieder der Gruppe hinzugefügt werden sollen, klicken Sie auf **Hinzufügen**.
    
    Klicken Sie in **diesem Fall verwalten**auf **Speichern** , um die neue Liste der Fall Mitglieder zu speichern. 
    
6. Klicken Sie auf **Speichern** , um die neue Liste der Fall Mitglieder zu speichern. 
  
## <a name="step-4-place-content-locations-on-hold"></a>Schritt 4: Platzieren von Inhaltsspeicherorten in der Warteschleife

Sie können einen eDiscovery-Fall zum Erstellen von Haltebereichen verwenden, um Inhalte beizubehalten, die möglicherweise für den Fall relevant sind. Sie können die Postfächer und OneDrive für Unternehmen Websites von Personen, die für den Fall Verwalter sind, aufbewahren. Sie können auch das Gruppenpostfach, die SharePoint-Website und die OneDrive für Unternehmen Website für eine Office 365 Gruppe aufbewahren. Ebenso können Sie die Postfächer und Websites, die Microsoft Teams oder Jammer Gruppen zugeordnet sind, aufbewahren. Wenn Sie inhaltsspeicherorte in der Warteschleife platzieren, wird der Inhalt so lange aufbewahrt, bis Sie den Haltebereich vom Inhaltsspeicherort entfernen oder bis Sie den Haltebereich löschen.

> [!NOTE]
> Nachdem Sie die Aufbewahrungsdauer eines Inhalts gespeichert haben, dauert es bis zu 24 Stunden, bis der Haltestatus wirksam wird. 
>   
Wenn Sie einen Haltebereich erstellen, haben Sie die folgenden Optionen, um den Inhalt zu belegen, der an den angegebenen Inhaltsspeicherorten gehalten wird:
  
- Sie erstellen einen unbegrenzten Haltebereich, in dem der gesamte Inhalt aufbewahrt wird. Alternativ können Sie einen abfragebasierten Speicher erstellen, in dem nur Inhalte, die einer Suchabfrage entsprechen, in die Warteschleife gestellt werden.
    
- Sie können einen Datumsbereich angeben, in dem nur der Inhalt gespeichert werden soll, der innerhalb dieses Datumsbereichs gesendet, empfangen oder erstellt wurde. Alternativ können Sie alle Inhalte speichern, unabhängig davon, wann Sie gesendet, empfangen oder erstellt wurden.
    
> [!NOTE]
> Sie können maximal 10.000-Speicherrichtlinien für alle eDiscovery-Fälle in Ihrer Organisation festlegen. 
  
So erstellen Sie einen Aufbewahrungsplatz für einen eDiscovery-Fall:
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, in dem Sie die Aufbewahrungspflicht erstellen möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf die Registerkarte **halten** . 
    
    ![Klicken Sie auf die Registerkarte halten](media/3fef2db4-36de-4517-a34d-82f47b82d9bf.png)
  
4. Klicken Sie ![auf der Seite **Haltestatus** auf](media/ITPro-EAC-AddIcon.gif) Symbol **Erstellen**hinzufügen.
    
5. Geben Sie auf der Seite **Name Ihres Haltestatus** dem Haltestatus einen Namen. Der Name des haltebereichs muss in Ihrer Organisation eindeutig sein. 
    
    ![Geben Sie Ihrem Haltestatus einen eindeutigen Namen.](media/7e15ea63-abd1-4f14-a29c-7ecfb9571d2c.png)
  
6. Optional Fügen Sie im Feld **Beschreibung** eine Beschreibung des Haltestatus hinzu. 
    
7. Klicken Sie auf **Weiter**.
    
8. Wählen Sie die inhaltsspeicherorte aus, die Sie in die Warteschleife stellen möchten. Sie können Postfächer, Websites und öffentliche Ordner in der Warteschleife platzieren.
    
    ![Wählen Sie Inhaltsspeicherorte aus, die im Haltebereich platziert werden sollen.](media/a59e4265-9151-4dbf-913f-6a4ab8db06b4.png)
  
   a. **Exchange-e-Mail** -klicken Sie auf **Benutzer, Gruppen oder Teams auswählen** , und klicken Sie dann erneut auf **Benutzer, Gruppen oder Teams auswählen** . zur Angabe von Postfächern, die in den Haltebereich verschoben werden. Verwenden Sie das Suchfeld, um nach Benutzerpostfächern und Verteilergruppen zu suchen (um die Postfächer der Gruppenmitglieder festhalten zu können), damit Sie in der Warteschleife platziert werden. Sie können das zugeordnete Postfach auch für ein Microsoft-Team, eine Jammer Gruppe oder eine Office 365 Gruppe aufbewahren. Aktivieren Sie das Kontrollkästchen Benutzer, Gruppe, Team, klicken Sie auf **auswählen**, und klicken Sie dann auf **Fertig**.
    
    > [!NOTE]
    > Wenn Sie auf **Benutzer, Gruppen oder Teams auswählen** klicken, um festzulegende Postfächer anzugeben, ist die angezeigte Post Fachauswahl leer. Dies ist beabsichtigt, um die Leistung zu verbessern. Geben Sie einen Namen (mindestens 3 Zeichen) in das Suchfeld ein, um Personen zu dieser Liste hinzuzufügen. 

   b. **SharePoint-Websites** – klicken Sie auf **Websites auswählen** , und klicken Sie dann erneut auf **Websites auswählen** , um SharePoint und OneDrive für Unternehmen Websites für die Aufbewahrung festzulegen. Geben Sie die URL für jede Website ein, die Sie in die Warteschleife stellen möchten. Sie können auch die URL für die SharePoint-Website für ein Microsoft-Team, eine Jammer Gruppe oder eine Office 365 Gruppe hinzufügen. Klicken Sie auf **auswählen**, und klicken Sie dann auf **Fertig**.
    
    Im Abschnitt [Weitere Informationen](#more-information) finden Sie Tipps zum Platzieren von Microsoft Teams, Jammer Gruppen und Office 365 Gruppen in der Warteschleife. 
    
    > [!NOTE]
    > Im seltenen Fall, dass der Benutzerprinzipalname (UPN) einer Person geändert wird, wird die URL für Ihr OneDrive-Konto ebenfalls geändert, um den neuen UPN zu integrieren. In diesem Fall müssen Sie den Haltebereich ändern, indem Sie die neue OneDrive-URL des Benutzers hinzufügen und die alte entfernen. 
  
   c. **Öffentliche Exchange-Ordner.** Verschieben Sie das Toggle ![-Steuer](media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) Element der Umschaltfläche in die **all** -Position, um alle öffentlichen Ordner in Ihrer Exchange Online Organisation zu speichern. Sie können keine bestimmten öffentlichen Ordner auswählen, die in die Warteschleife gestellt werden sollen. Lassen Sie den Toggle-Schalter auf " **None** " festgelegt, wenn Sie öffentliche Ordner nicht in den Speicher setzen möchten.
    
9. Wenn Sie das Hinzufügen von Inhaltsspeicherorten in der Warteschleife abgeschlossen haben, klicken Sie auf **weiter**.
    
10. Um eine abfragebasierte Aufbewahrung mit Bedingungen zu erstellen, führen Sie die folgenden Schritte aus. Klicken Sie andernfalls auf **weiter** .
    
    ![Erstellen eines abfragebasierten haltebereichs mit Bedingungen](media/d587b58e-d05c-4ac0-b0fe-09019e4f1063.png)
  
    
       a. Geben Sie im Feld unter **Schlüsselwörter**eine Suchabfrage in das Feld ein, sodass nur der Inhalt, der die Suchkriterien erfüllt, in der Warteschleife gespeichert wird. Sie können Schlüsselwörter, Nachrichteneigenschaften oder Dokumenteigenschaften wie Dateinamen angeben. Sie können auch komplexere Abfragen verwenden, die einen booleschen Operator wie **and**, **or**oder **Not**verwenden. Wenn Sie das Feld Schlüsselwort leer lassen, werden alle Inhalte, die sich an den angegebenen Inhaltsspeicherorten befinden, aufbewahrt.
    
    b. Klicken ![Sie auf](media/ITPro-EAC-AddIcon.gif) Symbol hinzufügen **Bedingungen** hinzufügen, um eine oder mehrere Bedingungen hinzuzufügen, um die Suchabfrage für den Haltebereich einzuschränken. Jede Bedingung fügt der KQL-Suchabfrage, die erstellt und ausgeführt wird, eine Klausel hinzu, wenn Sie den Haltebereich erstellen. Sie können beispielsweise einen Datumsbereich angeben, damit e-Mail-oder Website Dokumente, die innerhalb des Datumsbereichs erstellt wurden, in der Warteschleife gespeichert werden. Eine Bedingung ist durch **AND**-Operator logisch mit der (im Schlüsselwortfeld angegebenen) Schlüsselwortabfrage verbunden. Das bedeutet, dass Elemente sowohl die Stichwortabfrage als auch die Bedingung erfüllen müssen, die in der Warteschleife gespeichert werden soll.

    Weitere Informationen zum Erstellen einer Suchabfrage und zum Verwenden von Bedingungen finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
    
11. Klicken Sie nach dem Konfigurieren eines abfragebasierten Haltestatus auf **weiter**.
    
12. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **diesen Haltebereich erstellen**.
    
### <a name="hold-statistics"></a>Aufbewahrungs Statistik

Nach einer Weile werden Informationen zum neuen Haltestatus im Detailbereich auf der Seite halte **Status** des ausgewählten haltebereichs angezeigt. Diese Informationen umfassen die Anzahl der zu speichernden Postfächer und Websites sowie Statistiken zu den Inhalten, die in der Warteschleife gespeichert wurden, beispielsweise die Gesamtanzahl und Größe der zu speichernden Elemente sowie die Uhrzeit, zu der die Aufbewahrungs Statistik zuletzt berechnet wurde. Diese Aufbewahrungs Statistiken helfen Ihnen zu ermitteln, wie viele Inhalte im Zusammenhang mit dem eDiscovery-Fall gehalten werden. 
  
![Aufbewahrungs Statistik](media/575cfe0a-9210-4ae4-8df8-65665d66712e.png)
  
Beachten Sie die folgenden Aspekte bei Aufbewahrungs Statistiken:
  
- Die Gesamtanzahl der Elemente in der Warteschleife gibt die Anzahl der Elemente aus allen Inhaltsquellen an, die in der Warteschleife gespeichert werden. Wenn Sie einen abfragebasierten Haltebereich erstellt haben, gibt diese Statistik die Anzahl der Elemente an, die mit der Abfrage übereinstimmen.
    
- Die Anzahl der zu speichernden Elemente umfasst auch nicht indizierte Elemente, die an den Inhaltsspeicherorten gefunden wurden. Wenn Sie einen abfragebasierten Haltebereich erstellen, werden alle nicht indizierten Elemente in den Inhaltsspeicherorten in die Warteschleife gesetzt. Dies umfasst nicht indizierte Elemente, die nicht mit den Suchkriterien eines abfragebasierten haltebereichs und nicht indizierten Elementen übereinstimmen, die möglicherweise außerhalb einer Datumsbereichs Bedingung liegen. Dies unterscheidet sich von dem, was passiert, wenn Sie eine Inhaltssuche ausführen, in der nicht indizierte Elemente, die nicht mit der Suchabfrage übereinstimmen oder von einer Datumsbereichs Bedingung ausgeschlossen werden, nicht in den Suchergebnissen enthalten sind. Weitere Informationen zu nicht indizierten Elementen finden Sie unter [teilweise indizierte Elemente in der Inhaltssuche in Office 365](partially-indexed-items-in-content-search.md).
    
- Sie können die neuesten Aufbewahrungs Statistiken abrufen, indem Sie auf **Statistik aktualisieren** klicken, um eine Such Schätzung erneut auszuführen, mit der die aktuelle Anzahl der zu speichernden Elemente berechnet wird. Klicken Sie gegebenenfalls in ****![der Symbolleiste](media/O365-MDM-Policy-RefreshIcon.gif) auf Aktualisierungssymbol aktualisieren, um die Aufbewahrungs Statistiken im Detailbereich zu aktualisieren. 
    
- Es ist normal, dass die Anzahl der zu speichernden Elemente im Laufe der Zeit steigt, da Benutzer, deren Postfach oder Standort in der Warteschleife ist, normalerweise neue e-Mail-Nachrichten senden oder empfangen und neue SharePoint-und OneDrive für Unternehmen-Dokumente erstellen.
    
> [!NOTE]
> Wenn ein SharePoint-Website-oder OneDrive-Konto in eine andere Region in einer Multi-Geo-Umgebung verschoben wird, werden die Statistiken für diese Website nicht in die halte Statistik aufgenommen. Der Inhalt der Website bleibt jedoch weiterhin gespeichert. Wenn eine Website in einen anderen Bereich verschoben wird, wird auch die im Haltestatus angezeigte URL nicht aktualisiert. Sie müssen den Haltebereich bearbeiten und die URL aktualisieren. 
  
## <a name="step-5-create-and-run-a-content-search-associated-with-a-case"></a>Schritt 5: Erstellen und Ausführen einer einem Fall zugeordneten Inhaltssuche

Nachdem ein eDiscovery-Fall erstellt wurde und alle depotverwalter im Zusammenhang mit dem Fall gespeichert wurden, können Sie eine oder mehrere Inhalts Suchvorgänge erstellen und ausführen, die mit der Anfrage verknüpft sind. Inhalts Suchvorgänge, die einem Fall zugeordnet sind, werden nicht auf der Seite **Suchen** im Security #a0 Compliance Center aufgeführt. Dies bedeutet, dass der Zugriff auf Inhalts suchen, die einem Fall zugeordnet sind, nur von Fall Mitgliedern erreicht werden kann, die auch Mitglieder der eDiscovery-Manager-Rollengruppe sind. 
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, in dem Sie eine Inhaltssuche erstellen möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf die Registerkarte **Suche** . 
    
    ![Registerkarte "Suche"](media/2e15fe32-1a2e-4588-ad0b-5d96f77cece9.png)
  
4. Klicken Sie **** ![auf der Seite Suche auf Symbol](media/ITPro-EAC-AddIcon.gif) **neue Suche**hinzufügen. 
    
5. Auf der Seite **Neue Suche** können Sie Schlüsselwörter und Bedingungen zum Erstellen der Suchabfrage hinzufügen. 
    
    ![Neue Suche](media/0e9954e7-c0ea-4e05-820b-e4b81dc5f81d.png)
  
6. Sie können Schlüsselwörter, Nachrichteneigenschaften wie gesendete und empfangene Datumsangaben oder Dokumenteigenschaften angeben, beispielsweise Dateinamen oder das Datum, an dem ein Dokument zuletzt geändert wurde. Sie können komplexere Abfragen verwenden, die einen booleschen Operator verwenden, beispielsweise **and**, **or**, **Not**, **near**oder **ONEAR**. Sie können auch nach vertraulichen Informationen (z. B. Sozialversicherungsnummern) in Dokumenten oder nach Dokumenten suchen, die extern freigegeben wurden. Wenn Sie das Feld Schlüsselwort leer lassen, werden alle Inhalte, die sich an den angegebenen Inhaltsspeicherorten befinden, in die Suchergebnisse eingeschlossen. 
    
7. Sie können auf das Kontrollkästchen **Schlüsselwortliste anzeigen** und in jede Zeile ein Stichwort eingeben. Wenn Sie dies tun, werden die Schlüsselwörter für jede Zeile durch den **or** -Operator in der erstellten Suchabfrage miteinander verbunden. 
    
    ![Stichwortliste](media/29cceb5d-2817-4fc4-b91a-ced1c5824a17.png)
  
    Gründe für die Verwendung der Schlüsselwortliste Sie können Statistiken abrufen, die zeigen, wie viele Elemente den einzelnen Schlüsselwörtern entsprechen. Dadurch können Sie schnell erkennen, welche Schlüsselwörter am effektivsten (und am wenigsten effektiv) sind. Sie können auch einen (in Klammern eingeschlossenen) Schlüsselwortausdruck in einer Zeile verwenden. Weitere Informationen zu Suchstatistiken finden Sie unter [Anzeigen der Schlüsselwortstatistik für Inhaltssuchergebnisse](view-keyword-statistics-for-content-search.md).
    
    Weitere Informationen zur Verwendung der Liste Stichwörter finden Sie unter [Erstellen einer Suchabfrage](content-search.md#building-a-search-query).
    
8. Fügen Sie unter **Bedingungen**einer Suchabfrage Bedingungen hinzu, um eine Suche einzuschränken und eine verfeinerte Ergebnismenge zurückzugeben. Jede Bedingung fügt eine Klausel zu der KQL-Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird. Eine Bedingung ist durch **AND**-Operator logisch mit der (im Schlüsselwortfeld angegebenen) Schlüsselwortabfrage verbunden. Dies bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch die Bedingung erfüllen muss, damit sie in die Suchergebnisse aufgenommen werden. Auf diese Weise können Sie Ihre Ergebnisse mit Bedingungen eingrenzen. 
    
    Weitere Informationen zum Erstellen einer Suchabfrage sowie zur Verwendung von Bedingungen finden Sie unter [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).
    
9. Wählen Sie unter **Standorte: Aufbewahrungsorte**die inhaltsspeicherorte aus, die Sie durchsuchen möchten. Sie können Postfächer, Websites und öffentliche Ordner in derselben Suche durchsuchen.
    
    ![Speicherorte, Aufbewahrungsorte](media/d56398aa-0b20-4500-8e26-494eab92a99f.png)
  
    - **Alle Standorte** – wählen Sie diese Option aus, um alle inhaltsspeicherorte in Ihrer Organisation zu durchsuchen. Wenn Sie diese Option auswählen, können Sie auswählen, dass alle Exchange-Postfächer durchsucht werden sollen (einschließlich der Postfächer für alle Microsoft Teams, Jammer Gruppen und Office 365 Gruppen), alle SharePoint-und OneDrive für Unternehmen-Websites (einschließlich der Websites für alle Microsoft Teams, Jammer Gruppen und Office 365 Gruppen) und alle öffentlichen Ordner.
    
    - **Alle Aufbewahrungsorte.** Wählen Sie diese Option aus, um alle inhaltsspeicherorte zu durchsuchen, die in der Anfrage gespeichert wurden. Wenn die Groß-/Kleinschreibung mehrere Haltestatus enthält, werden die inhaltsspeicherorte aus allen Haltebereichen durchsucht, wenn Sie diese Option auswählen. Wenn ein Inhaltsspeicherort in einem abfragebasierten Speicherplatz gefunden wurde, werden beim Ausführen der Inhaltssuche, die Sie in diesem Schritt erstellen, nur die Elemente durchsucht, die in der Warteschleife gespeichert sind. Wenn beispielsweise ein Benutzer auf Abfrage basiertem Case Hold gesetzt wurde, der Elemente aufrecht erhält, die vor einem bestimmten Datum gesendet oder erstellt wurden, werden nur diese Elemente mithilfe der Suchkriterien der Inhaltssuche durchsucht. Dies wird erreicht, indem die Case Hold-Abfrage und die Inhalts Suchabfrage durch einen **and-** Operator verbunden werden. Weitere Informationen zum Suchen von Fall Inhalten finden Sie im Abschnitt [Weitere Informationen](#more-information) am Ende dieses Artikels. 
    
    - **Bestimmte Standorte.** Wählen Sie diese Option aus, um die Postfächer und Websites auszuwählen, die Sie durchsuchen möchten. Wenn Sie diese Option auswählen und auf **ändern**klicken, wird eine Liste der Speicherorte angezeigt. Sie können auswählen, ob Sie einen oder alle Benutzer, Gruppen, Teams oder Website Standorte durchsuchen möchten.
    
      ![Auswählen bestimmter Standorte](media/97469b15-7be1-4aee-be27-f8343636152c.png)
  
      Sie können auch alle öffentlichen Ordner in Ihrer Organisation durchsuchen, aber wenn Sie diese Option auswählen und einen beliebigen Inhaltsspeicherort in der Warteschleife durchsuchen, werden alle Abfragen von einem abfragebasierten Aufbewahrungs Fall nicht auf die Suchabfrage angewendet. In anderen Worten wird der gesamte Inhalt eines Standorts durchsucht, und nicht nur der Inhalt, der von einem abfragebasierten Aufbewahrungsplatz beibehalten wird.
    
      Sie können die zuvor aufgefüllten Speicherorte für Inhalte entfernen oder neue hinzufügen. Wenn Sie diese Option auswählen, haben Sie auch die Flexibilität, alle inhaltsspeicherorte für einen bestimmten Dienst zu durchsuchen (beispielsweisedurch Suchen aller Exchange-Postfächer), oder Sie können bestimmte inhaltsspeicherorte für einen Dienst durchsuchen. Sie können auch auswählen, ob die öffentlichen Ordner in Ihrer Organisation durchsucht werden sollen.
    
      Beachten Sie beim Hinzufügen von Inhaltsspeicherorten zur Suche Folgendes:
    
      - Wenn Sie auf **Benutzer, Gruppen oder Teams auswählen** klicken, um die zu durchsuchenden Postfächer anzugeben, ist die angezeigte Post Fachauswahl leer. Dies ist beabsichtigt, um die Leistung zu verbessern. Klicken Sie zum Hinzufügen von Empfängern zu dieser Liste auf **Benutzer, Gruppen oder Teams auswählen**, geben Sie einen Namen (mindestens 3 Zeichen) in das Suchfeld ein, aktivieren Sie das Kontrollkästchen neben dem Namen, und klicken Sie dann auf **auswählen**. 
    
      - Sie können inaktive Postfächer, Microsoft Teams, Jammer Gruppen, Office 365 Gruppen und Verteilergruppen zur Liste der zu durchsuchenden Postfächer hinzufügen. Dynamische Verteilergruppen werden nicht unterstützt. Wenn Sie Microsoft Teams, Jammer Gruppen oder Office 365 Gruppen hinzufügen, wird das Gruppen-oder Team Postfach durchsucht. die Postfächer der Gruppenmitglieder werden nicht durchsucht.
    
      - Klicken Sie zum Hinzufügen von Websites auf **Websites auswählen**, dann auf **Websites erneut auswählen** , und geben Sie dann die URL für jede Website ein, die Sie durchsuchen möchten. Sie können auch die URL für die SharePoint-Website für ein Microsoft-Team, eine Jammer Gruppe oder eine Office 365 Gruppe hinzufügen. 
    
10. Nachdem Sie die zu durchsuchenden inhaltsspeicherorte ausgewählt haben, klicken Sie auf **Fertig** und dann auf **Speichern**.
    
11. Klicken Sie auf der Seite **neue Suche** auf **Speichern** , und geben Sie dann einen Namen für die Suche ein. Inhalts suchen, die einem Fall zugeordnet sind, müssen Namen enthalten, die innerhalb Ihrer Office 365 Organisation eindeutig sind. 
    
12. Klicken Sie auf **Run speichern &amp; ** , um die Sucheinstellungen zu speichern. 
    
13. Geben Sie einen eindeutigen Namen für die Suche ein, und klicken Sie auf **Speichern** , um die Suche zu starten. 
    
    Die Suche beginnt. Nach einer Weile wird im Detailbereich eine Schätzung der Suchergebnisse angezeigt. Die Schätzung enthält die Gesamtgröße und die Anzahl der Elemente, die den Suchkriterien entsprechen. Die Such Schätzung enthält auch die Anzahl der nicht indizierten Elemente an den durchsuchten Inhaltsspeicherorten. Die Anzahl nicht indizierter Elemente, die den Suchkriterien nicht entsprechen, werden in die Suchstatistiken einbezogen, die im Detailbereich angezeigt werden. Wenn ein nicht indiziertes Element mit der Suchabfrage übereinstimmt (da andere Nachrichten-oder Dokumenteigenschaften die Suchkriterien erfüllen), wird es nicht in die geschätzte Anzahl nicht indexierter Elemente aufgenommen. Wenn ein nicht indiziertes Element durch die Suchkriterien ausgeschlossen wird, wird es auch nicht in die Schätzung nicht indexierter Elemente einbezogen.
    
  Wenn die Suche abgeschlossen ist, können Sie eine Vorschau der Suchergebnisse anzeigen. Klicken Sie bei Bedarf ****![auf Aktualisierungssymbol](media/O365-MDM-Policy-RefreshIcon.gif) aktualisieren, um die Informationen im Detailbereich zu aktualisieren. 
    
## <a name="step-6-export-the-results-of-a-content-search-associated-with-a-case"></a>Schritt 6: Exportieren der Ergebnisse einer Inhaltssuche, die einer Anfrage zugeordnet ist

Nachdem eine Suche erfolgreich ausgeführt wurde, können Sie die Suchergebnisse exportieren. Wenn Sie Suchergebnisse exportieren, werden Postfachelemente in PST-Dateien oder als einzelne Nachrichten heruntergeladen. Wenn Sie Inhalte aus SharePoint und OneDrive für Unternehmen Websites exportieren, werden Kopien von systemeigenen Office-Dokumenten und anderen Dokumenten exportiert. Eine Manifestdatei (im XML-Format), die Informationen zu jedem Suchergebnis enthält, wird ebenfalls exportiert.
  
Sie können die Ergebnisse einer einzelnen Suche exportieren, die [einem Fall zugeordnet](#export-the-results-of-a-single-search-associated-with-a-case) ist, oder Sie können die Ergebnisse [mehrerer Suchvorgänge exportieren, die einem Fall zugeordnet sind](#export-the-results-of-multiple-searches-associated-with-a-case).
  
### <a name="export-the-results-of-a-single-search-associated-with-a-case"></a>Exportieren der Ergebnisse einer einzelnen Suche, die einem Fall zugeordnet ist

1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, aus dem Sie die Suche exportieren möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf **Suchen**.
    
4. Klicken Sie in der Liste der Suchvorgänge auf die Suche, aus der Sie Suchergebnisse exportieren möchten, klicken Sie ![auf Suchergebnisse](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **exportieren, und**wählen Sie dann **Ergebnisse exportieren** aus der Dropdownliste aus. 
    
    Die Seite **Ergebnisse exportieren** wird angezeigt. 
    
    ![Seite "Ergebnisse exportieren"](media/ab0bb46d-310b-4374-8644-717146df6676.png)
  
    Der Workflow zum Exportieren der Ergebnisse aus einer Inhaltssuche, die einem Fall zugeordnet ist, entspricht dem Exportieren der Suchergebnisse für eine Suche auf der Seite **Inhaltssuche** . Eine Schritt-für-Schritt-Anleitung finden Sie unter [Exportieren von Inhalts Suchergebnissen](export-search-results.md).
    
    > [!NOTE]
    > Wenn Sie Suchergebnisse exportieren, haben Sie die Möglichkeit, die Deduplizierung zu aktivieren, sodass nur eine Kopie einer e-Mail-Nachricht exportiert wird, obwohl in den durchsuchten Postfächern möglicherweise mehrere Instanzen derselben Nachricht gefunden wurden. Weitere Informationen zur Deduplizierung und zur Identifizierung von doppelten Elementen finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen](de-duplication-in-ediscovery-search-results.md). 
  
5. Klicken Sie auf die Registerkarte **exportieren** , um die Liste der Exportaufträge anzuzeigen, die für diesen Fall vorhanden sind. 
    
    ![Registerkarte "Exportieren"](media/1b84c45e-4ec9-4ecd-9e07-eaf8fc4cc307.png)
  
    Möglicherweise müssen Sie **auf Aktualisierungs**![Symbol](media/O365-MDM-Policy-RefreshIcon.gif) aktualisieren klicken, um die Liste der Exportaufträge so zu aktualisieren, dass der von Ihnen erstellte Exportauftrag angezeigt wird. Export Aufträge haben den gleichen Namen wie die entsprechende Inhaltssuche, wobei **_Export** an das Ende des Such namens angehängt wird. 
    
6. Klicken Sie auf den soeben erstellten Exportauftrag, um Statusinformationen im Detailbereich anzuzeigen. Diese Informationen umfassen den Prozentsatz der Elemente, die in einen Azure-Speicherbereich in der Microsoft-Cloud übertragen wurden.
    
    Nachdem alle Elemente übertragen wurden, klicken Sie auf **Ergebnisse herunterladen** , um die Suchergebnisse auf den lokalen Computer herunterzuladen. Weitere Informationen finden Sie unter Schritt 2 in [Exportieren von Inhalts Suchergebnissen](export-search-results.md)
    
### <a name="export-the-results-of-multiple-searches-associated-with-a-case"></a>Exportieren der Ergebnisse mehrerer Suchvorgänge, die einem Fall zugeordnet sind

Als Alternative zum Exportieren der Ergebnisse einer einzelnen Inhaltssuche, die einem Fall zugeordnet ist, können Sie die Ergebnisse mehrerer Suchvorgänge aus demselben Fall in einem einzelnen Export exportieren. Das Exportieren der Ergebnisse von mehreren Suchvorgängen ist schneller und einfacher als das Exportieren der Ergebnisse um die Suche nach dem anderen.
  
> [!NOTE]
> Sie können die Ergebnisse mehrerer suchen nicht exportieren, wenn eine dieser Suchvorgänge so konfiguriert wurde, dass alle Fall Inhalte durchsucht werden. Exportieren Sie nur die Ergebnisse mehrerer Suchvorgänge nach Suchvorgängen, die einem eDiscovery-Fall zugeordnet sind. Sie können die Ergebnisse mehrerer Suchvorgänge, die auf der Seite **Inhaltssuche** im Security #a0 Compliance Center aufgeführt sind, nicht exportieren. 
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, aus dem Sie Suchergebnisse exportieren möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf **Suchen**.
    
4. Wählen Sie in der Liste der Suchvorgänge mindestens zwei Suchvorgänge aus, aus denen Sie Suchergebnisse exportieren möchten.
    
    > [!NOTE]
    > Wenn Sie mehrere Suchvorgänge auswählen möchten, drücken Sie STRG, während Sie auf jede Suche klicken. Sie können auch mehrere benachbarte Suchvorgänge auswählen, indem Sie auf die erste Suche klicken, die UMSCHALTTASTE gedrückt halten und dann auf die letzte Suche klicken. 
  
5. Nachdem Sie die Suchvorgänge ausgewählt haben, wird die Seite **Massenaktionen** angezeigt. 
    
    ![Klicken Sie auf der Seite Massenaktionen auf Ergebnisse exportieren.](media/f34e3707-a9c1-494f-91a4-da1165aa730a.png)
  
    
6. Klicken ![Sie auf Suchergebnis](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) Symbol Export **Ergebnisse**exportieren.

7. Geben Sie auf der Seite **Ergebnisse exportieren** den eindeutigen Namen exportieren ein, wählen Sie Ausgabeoptionen aus, und wählen Sie aus, wie Ihre Inhalte exportiert werden sollen. Klicken Sie auf **Exportieren**.
    
    Der Workflow zum Exportieren der Ergebnisse aus mehreren Inhalts suchen, die einem Fall zugeordnet sind, ist identisch mit dem Exportieren der Suchergebnisse für eine einzelne Suche. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Exportieren von Inhalts Suchergebnissen](export-search-results.md).
    
    > [!NOTE]
    > Wenn Sie Suchergebnisse aus mehreren Suchvorgängen exportieren, die einem Fall zugeordnet sind, können Sie auch die Deduplizierung aktivieren, sodass nur eine Kopie einer e-Mail-Nachricht exportiert wird, obwohl möglicherweise mehrere Instanzen derselben Nachricht im Postfächer, die in einer oder mehreren Suchvorgängen durchsucht wurden. Weitere Informationen zur Deduplizierung und zur Identifizierung von doppelten Elementen finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen](de-duplication-in-ediscovery-search-results.md). 
  
8. Nachdem Sie den Export gestartet haben, klicken Sie auf die Registerkarte **exportieren** , um die Liste der Exportaufträge für diesen Fall anzuzeigen. 
    
    ![Registerkarte "Exportieren", mehrere Suchvorgänge](media/b9505e1b-559f-4a8c-96b3-a3f734753926.png)
  
    Möglicherweise müssen Sie **auf Aktualisierungs** ![Symbol](media/O365-MDM-Policy-RefreshIcon.gif) aktualisieren klicken, um die Liste der Exportaufträge zu aktualisieren, um den von Ihnen erstellten Exportauftrag anzuzeigen. Die Suchvorgänge, die in den Exportauftrag aufgenommen wurden, werden in der Spalte **Suchen** aufgeführt. 
    
8. Klicken Sie auf den soeben erstellten Exportauftrag, um Statusinformationen im Detailbereich anzuzeigen. Diese Informationen umfassen den Prozentsatz der Elemente, die in einen Azure-Speicherbereich in der Microsoft-Cloud übertragen wurden.
    
9. Nachdem alle Elemente übertragen wurden, klicken Sie auf **Ergebnisse herunterladen** , um die Suchergebnisse auf den lokalen Computer herunterzuladen. Weitere Informationen finden Sie unter Schritt 2 unter [Exportieren von Inhalts Suchergebnissen](export-search-results.md).
    
#### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>Weitere Informationen zum Exportieren der Ergebnisse mehrerer Suchvorgänge

- Wenn Sie die Ergebnisse mehrerer Suchvorgänge exportieren, werden die Suchabfragen von allen suchen mit **oder** -Operatoren kombiniert, und dann wird die kombinierte Suche gestartet. Die geschätzten Ergebnisse der kombinierten Suche werden im Detailbereich des ausgewählten Exportauftrags angezeigt. Die Suchergebnisse werden dann in den Azure-Speicherbereich in der Microsoft-Cloud übertragen. Der Status der Übertragung wird auch im Detailbereich angezeigt. Wie bereits erwähnt, können Sie Sie nach dem Übertragen aller Suchergebnisse auf Ihren lokalen Computer herunterladen. 
    
- Die maximale Anzahl von Stichwörtern aus den Suchabfragen für alle Suchvorgänge, die Sie exportieren möchten, lautet 500. (Dies ist der gleiche Grenzwert für eine einzelne Inhaltssuche). Das liegt daran, dass der Exportauftrag alle Suchabfragen mit dem **or** -Operator kombiniert. Wenn Sie diesen Grenzwert überschreiten, wird ein Fehler zurückgegeben. In diesem Fall müssen Sie die Ergebnisse aus weniger Suchvorgängen exportieren oder die Suchabfragen der zu exportierenden suchen vereinfachen. 
    
- Die exportierten Suchergebnisse werden nach der Inhaltsquelle organisiert, in der das Element gefunden wurde. Das bedeutet, dass für eine Inhaltsquelle in den Export Ergebnissen möglicherweise Elemente von unterschiedlichen Suchvorgängen zurückgegeben werden. Wenn Sie beispielsweise e-Mail-Nachrichten in einer PST-Datei für jedes Postfach exportieren möchten, hat die PST-Datei möglicherweise Ergebnisse aus mehreren Suchvorgängen.
    
- Wenn dasselbe e-Mail-Element oder Dokument vom gleichen Inhaltsspeicherort von mehr als einer der Suchvorgänge zurückgegeben wird, die Sie exportieren, wird nur eine Kopie des Elements exportiert.
    
- Sie können einen Export für mehrere Suchvorgänge nach dem Erstellen nicht bearbeiten. Beispielsweise können Sie dem Export keine Suchvorgänge hinzufügen oder daraus entfernen. Sie müssen einen Exportauftrag erstellen, um die exportierten Suchergebnisse zu ändern. Nachdem ein Exportauftrag erstellt wurde, können Sie die Ergebnisse nur auf einen Computer herunterladen, den Export neu starten oder den Exportauftrag löschen.
    
- Wenn Sie den Export neu starten, wirken sich Änderungen an den Abfragen der Suchvorgänge, aus denen der Exportauftrag besteht, nicht auf die Suchergebnisse aus, die abgerufen werden. Wenn Sie einen Export neu starten, wird derselbe kombinierte Suchabfrage Auftrag, der beim Erstellen des Exportauftrags ausgeführt wurde, erneut ausgeführt.
    
- Wenn Sie einen Export von der Seite **Exports** in einem eDiscovery-Fall neu starten, überschreiben die Suchergebnisse, die an den Azure-Speicherbereich übertragen werden, die vorherigen Ergebnisse. Die vorherigen Ergebnisse, die dort übertragen wurden, stehen nicht zum Herunterladen zur Verfügung. 
    
- Das Vorbereiten der Ergebnisse mehrerer Suchvorgänge für die Analyse in Advanced eDiscovery ist nicht verfügbar. Sie können nur die Ergebnisse einer einzelnen Suche für die Analyse in Advanced eDiscovery vorbereiten.

## <a name="step-7-prepare-search-results-for-advanced-ediscovery"></a>Schritt 7: Vorbereiten der Suchergebnisse für Advanced eDiscovery

Wenn Ihre Organisation über ein Office 365 E5-Abonnement verfügt, können Sie die Ergebnisse von Inhalts suchen vorbereiten, die einem Fall für die Analyse in Advanced eDiscovery zugeordnet sind. Nachdem Sie Suchergebnisse vorbereitet haben, können Sie zu Advanced eDiscovery wechseln (siehe [Schritt 8: Wechseln Sie zu der Anfrage in Advanced eDiscovery](#step-8-go-to-the-case-in-advanced-ediscovery)) und verarbeiten die Suchergebnis Daten zur weiteren Analyse in Advanced eDiscovery.
  
Wenn Sie Suchergebnisse für Advanced eDiscovery vorbereiten, extrahiert die OCR-Funktion (Optical Character Recognition) automatisch Text aus Bildern. OCR wird für lose Dateien, e-Mail-Anlagen und eingebettete Bilder unterstützt. Auf diese Weise können Sie die Textanalyse Funktionen von Advanced eDiscovery (Near-Duplicates, e-Mail-Threading, Themes und Predictive Coding) auf Text in Bilddateien anwenden.
  
> [!NOTE]
> Um die Daten eines Benutzers mithilfe von Advanced eDiscovery zu analysieren, muss dem Benutzer (dem Verwalter der Daten) eine Office 365 E5-Lizenz zugewiesen werden. Alternativ können Benutzern mit einer Office 365 E1-oder E3-Lizenz eine erweiterte eDiscovery-eigenständige Lizenz zugewiesen werden. Administratoren und Compliance Officer, die Fällen zugeordnet sind, und Verwenden von Advanced eDiscovery zum Analysieren von Daten benötigen keine E5-Lizenz. 
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, für den Sie Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf **Suche**, und wählen Sie dann die Suche aus.
    
4. Klicken Sie im Detailbereich auf ![Such](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png) **Ergebnis Symbol exportieren**, und klicken Sie dann auf **für erweiterte eDiscovery vorbereiten**.
    
    ![Vorbereiten der Ergebnisse für Advanced eDiscovery](media/b6548ff0-a6e9-42b1-9ae4-5c15146f5690.png)
  
5. Wählen Sie auf der Seite **Advanced eDiscovery vorbereiten** eine der folgenden Optionen aus: 
    
    - Alle Elemente, ausgenommen solche mit nicht erkanntem Format, sind verschlüsselt oder wurden aus anderen Gründen nicht indiziert.
    
    - Alle Elemente, einschließlich derer, die nicht erkanntes Format aufweisen, werden verschlüsselt oder aus anderen Gründen nicht indiziert.
    
    - Nur Elemente, die ein nicht wieder erkennbares Format aufweisen, werden aus anderen Gründen verschlüsselt oder nicht indiziert.
    
6. Optional Aktivieren Sie das Kontrollkästchen **Versionen für SharePoint-Dateien einschließen** . 
    
7. Klicken Sie auf **Vorbereiten**.
    
    Die Suchergebnisse werden mit Advanced eDiscovery für die Analyse vorbereitet.
    
8. Klicken Sie auf **Schließen** , um den Detailbereich zu schließen. 
    
## <a name="step-8-go-to-the-case-in-advanced-ediscovery"></a>Schritt 8: Wechseln zu der Groß-/Kleinschreibung in Advanced eDiscovery

Nachdem Sie einen Fall im Security #a0 Compliance Center erstellt haben, können Sie in der erweiterten eDiscovery auf denselben Fall wechseln.
  
So navigieren Sie zu einem Fall in Advanced eDiscovery:
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, zu dem Sie in Advanced eDiscovery wechseln möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf **zu Advanced eDiscovery wechseln**.
    
    ![Wählen Sie zu Advanced eDiscovery wechseln aus.](media/d7e31558-e79c-4782-b841-2b735568a576.png)
  
    Die **Verbindung mit der erweiterten eDiscovery** -Statusleiste wird angezeigt. Wenn Sie mit Advanced eDiscovery verbunden sind, wird auf der Seite eine Liste mit Containern angezeigt. 
    
    ![Erweiterte eDiscorvery-Statusanzeige](media/4a84273d-765b-44b8-9006-c20e810ea393.png)
  
    Diese Container stellen die Suchergebnisse dar, die Sie in Schritt 7 zur Analyse in Advanced eDiscovery vorbereitet haben. Der Name des Containers hat den gleichen Namen wie die Inhaltssuche in dem Fall im Security #a0 Compliance Center. Die Container in der Liste sind diejenigen, die Sie vorbereitet haben. Wenn ein anderer Benutzer Suchergebnisse für Advanced eDiscovery vorbereitet hat, werden die entsprechenden Container nicht in die Liste aufgenommen.
    
4. Wenn Sie die Suchergebnis Daten aus einem Container in den Fall in Advanced eDiscovery laden möchten, wählen Sie einen Container aus, und klicken Sie auf **verarbeiten**.
    
    Informationen zum Verarbeiten von Containern finden Sie unter [Ausführen des Prozess Moduls und Laden von Daten in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md).
    
> [!TIP]
> Klicken Sie auf **zu eDiscovery wechseln** , um zum gleichen Fall im Security #a0 Compliance Center zurückzukehren. 
  
## <a name="optional-step-9-close-a-case"></a>Optional Schritt 9: Schließen eines Falls

Wenn der von einem eDiscovery-Fall unterstützte rechtliche Fall oder die Untersuchung abgeschlossen ist, können Sie den Fall schließen. Hier erfahren Sie, was passiert, wenn Sie einen Fall schließen:
  
- Wenn der Fall alle inhaltsspeicherorte enthält, sind diese Haltestatus deaktiviert. Dies kann dazu führen, dass Inhalte dauerhaft gelöscht oder gelöscht werden, entweder durch den Benutzer oder durch einen automatisierten Prozess, beispielsweise eine Löschrichtlinie.
    
- Durch das Schließen eines Case werden nur die haltebereiche deaktiviert, die diesem Fall zugeordnet sind. Wenn andere haltebereiche an einem Inhaltsspeicherort platziert werden (beispielsweise ein Beweissicherungsverfahren. eine Erhaltungs Richtlinie oder ein Haltestatus aus einem anderen eDiscovery-Fall) diese Aufbewahrungen werden weiterhin beibehalten.
    
- Der Fall wird weiterhin auf der Seite "eDiscovery" im Security #a0 Compliance Center aufgeführt. Die Details, Aufbewahrungen, Suchvorgänge und Elemente eines geschlossenen Falls werden beibehalten.
    
- Sie können einen Fall bearbeiten, nachdem er geschlossen wurde. Beispielsweise können Sie Mitglieder hinzufügen oder entfernen, suchen erstellen, Suchergebnisse exportieren und das Suchergebnis für die Analyse in Advanced eDiscovery vorbereiten. Der Hauptunterschied zwischen aktiven und geschlossenen Fällen besteht darin, dass die haltebereiche deaktiviert sind, wenn ein Fall geschlossen wird.
    
So schließen Sie einen Fall:
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie auf den Namen der Groß-/Kleinschreibung, die Sie schließen möchten.
    
    Die Dropdown Seite **diesen Fall verwalten** wird angezeigt. 
    
3. Klicken Sie unter **Status der Groß-/Kleinschreibung verwalten**auf ![die Schaltfläche Peek-Taste](media/b6512677-5e7b-42b0-a8a3-3be1d7fa23ee.gif) **Schließen**.
    
    Es wird eine Warnung angezeigt, die besagt, dass die dem Fall zugeordneten Haltestatus deaktiviert werden.
    
4. Klicken Sie auf **Ja** , um den Fall zu schließen. 
    
    Der Status auf der Flyout-Seite " **diesen Fall verwalten** " wird von " **aktiv** " in " **Schließen**" geändert.
    
5. Schließen Sie die Seite **diesen Fall verwalten** . 
    
6. Klicken Sie **** ![auf der Seite eDiscovery auf Symbol](media/O365-MDM-Policy-RefreshIcon.gif) **Aktualisierung** aktualisieren, um den Status des geschlossenen Falls zu aktualisieren. Es kann bis zu 60 Minuten dauern, bis der Abschlussprozess abgeschlossen ist. 
    
    Wenn der Prozess abgeschlossen ist, wird der Status der Groß-/Kleinschreibung auf der **eDiscovery** -Seite in **geschlossen** geändert. Klicken Sie erneut auf den Namen der Anfrage, um die Flyout-Seite " **diesen Fall verwalten** " anzuzeigen, die Informationen dazu enthält, wann der Fall geschlossen wurde und wer ihn geschlossen hat. 
     
## <a name="optional-step-10-re-open-a-closed-case"></a>Optional Schritt 10: Erneutes Öffnen eines geschlossenen Falls

Wenn Sie einen Fall erneut öffnen, werden alle Haltestatus, die beim Schließen des Cases vorhanden waren, nicht automatisch wiederhergestellt. Nachdem der Fall erneut geöffnet wurde, müssen Sie zur **halte** Seite wechseln und die vorherigen Holds-Objekte aktivieren. Zum Aktivieren eines haltebereichs wählen Sie ihn aus, und klicken Sie im Detailbereich auf **Einschalten** . 
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie auf den Namen der Groß-/Kleinschreibung, die Sie erneut öffnen möchten.
    
    Die Dropdown Seite **diesen Fall verwalten** wird angezeigt. 
    
3. Klicken Sie unter **Fall Status verwalten**auf **erneuter Fall öffnen**.
    
    Es wird eine Warnung angezeigt, die besagt, dass die haltebereiche, die dem Fall beim Schließen zugeordnet waren, nicht automatisch aktiviert werden.
    
4. Klicken Sie auf **Ja** , um die Anfrage erneut zu öffnen. 
    
    Der Status auf der Flyout-Seite " **diesen Fall verwalten** " wird von " **geschlossen** " in " **aktiv**" geändert.
    
5. Schließen Sie die Seite **diesen Fall verwalten** . 
    
6. Klicken Sie **** ![auf der Seite eDiscovery auf Symbol](media/O365-MDM-Policy-RefreshIcon.gif) **Aktualisierung** aktualisieren, um den Status des erneut geöffneten Falls zu aktualisieren. Es kann bis zu 60 Minuten dauern, bis der Vorgang zum erneuten Öffnen abgeschlossen ist. 
    
    Wenn der Prozess abgeschlossen ist, wird der Status des Falles in **Active** auf der **eDiscovery** -Seite geändert. 
  
## <a name="optional-step-11-delete-a-case"></a>Optional Schritt 11: Löschen einer Anfrage

Sie können auch aktive und abgeschlossene Fälle löschen. Wenn Sie einen Fall löschen, werden alle Suchvorgänge und Exporte gelöscht und aus der Liste der Fälle auf der Seite " **eDiscovery** " im Security #a0 Compliance Center entfernt. Sie können einen gelöschten Fall nicht erneut öffnen. 

Bevor Sie einen Fall löschen können (ob er aktiv oder geschlossen ist), müssen Sie zunächst *alle* Haltestatus löschen, die mit der Groß-/Kleinschreibung verknüpft sind. Dies umfasst das Löschen von Haltebereichen mit dem Status **Off**. 

So löschen Sie einen Haltestatus:

1. Wechseln Sie zur Registerkarte halte **Status** , falls Sie löschen möchten.

2. Klicken Sie auf den Haltestatus, den Sie löschen möchten.

3. Klicken Sie auf der Flyout-Seite auf **Haltestatus löschen**.

So löschen Sie einen Fall:

1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie auf den Namen der Groß-/Kleinschreibung, die Sie löschen möchten.

3. Klicken Sie unter **Fall Status verwalten** auf der Flyout-Seite auf **Fall löschen**.

Wenn der Fall, den Sie löschen möchten, noch enthält, wird eine Fehlermeldung angezeigt. Sie müssen alle dem Fall zugeordneten haltebereiche löschen und dann erneut versuchen, die Groß-/Kleinschreibung zu löschen.

## <a name="more-information"></a>Weitere Informationen

- **Gibt es Einschränkungen für eDiscovery-Fälle oder haltebereiche, die einem eDiscovery-Fall zugeordnet sind?** In der folgenden Tabelle sind die Grenzwerte für eDiscovery-Fälle und Case-Holds aufgeführt.
    
  |**Beschreibung der Beschränkung**|**Grenzwert**|
  |:-----|:-----|
  |Maximale Anzahl von Fällen für eine Organisation  <br/> |Keine Begrenzung  <br/> |
  |Maximale Anzahl von Fall Behältern für eine Organisation  <br/> |10.000  <br/> |
  |Maximale Anzahl von Postfächern in einem einzigen Aufbewahrungs Fall  <br/> |1.000  <br/> |
  |Maximale Anzahl von SharePoint-und OneDrive für Unternehmen-Websites in einem einzigen Aufbewahrungs Fall  <br/> |100  <br/> |
   
- **Was geschieht mit Fällen, die auf der Seite Fallverwaltung in Advanced eDiscovery erstellt wurden?** Sie können auf eine Liste älterer erweiterter eDiscovery-Fälle zugreifen, indem Sie auf der Seite **eDiscovery** im Security #a0 Compliance Center auf den Link unten klicken. Um jedoch in einem älteren Fall arbeiten zu können, müssen Sie sich an Office 365 Support wenden und die Anfrage dazu stellen, dass der Fall in einen neuen eDiscovery-Fall im Security #a0 Compliance Center verschoben wird. 
    
- **Gründe für das Festlegen eines eDiscovery-Administrators** Wie bereits erwähnt, ist ein eDiscovery-Administrator Mitglied der Rollengruppe „eDiscovery-Manager“, die alle eDiscovery-Fälle in Ihrer Organisation anzeigen und auf diese zugreifen kann. Dieser Zugriff auf alle eDiscovery-Fälle dient zwei wichtigen Zwecken:
    
  - Wenn eine Person, die das einzige Mitglied eines eDiscovery-Falls ist, die Organisation verlässt, kann niemand (einschließlich Mitglieder der Rollengruppe „Organisationsverwaltung“ oder andere Mitglieder der Rollengruppe „eDiscovery-Manager“) auf diesen eDiscovery-Fall zugreifen, da diese Personen keine Fallmitglieder sind. In diesem Fall gäbe es keine Möglichkeit, auf die Daten in dem Fall zuzugreifen. Da ein eDiscovery-Administrator jedoch auf alle eDiscovery-Fälle in der Organisation zugreifen kann, kann er den Fall im Security #a0 Compliance Center anzeigen und sich selbst oder einen anderen eDiscovery-Manager als Mitglied des Falles hinzufügen.
    
  - Da ein eDiscovery-Administrator alle eDiscovery-Fälle anzeigen und darauf zugreifen kann, kann er alle Fälle und zugehörige Inhalts suchen überwachen und überwachen. So kann der Missbrauch von Inhaltssuchen oder anderen eDiscovery-Fällen verhindert werden. Und da eDiscovery-Administratoren in den Ergebnissen einer Inhaltssuche potenziell vertrauliche Informationen abrufen können, sollten Sie die Anzahl von Benutzern, die eDiscovery-Administratoren sind, einschränken.
    
    Schließlich werden eDiscovery-Administratoren im Security #a0 Compliance Center automatisch als Administratoren in Advanced eDiscovery hinzugefügt, wie zuvor erläutert. Das bedeutet, dass eine Person, die ein eDiscovery-Administrator ist, administrative Aufgaben in Advanced eDiscovery ausführen kann, beispielsweise das Einrichten von Benutzern, das Erstellen von Fällen und das Hinzufügen von Daten zu Fällen.
    
- **Was sind die Lizenzierungsanforderungen zum Speichern von Inhaltsspeicherorten?** Im Allgemeinen benötigen Organisationen ein Office 365 E3-Abonnement oder höher, um inhaltsspeicherorte in der Warteschleife zu platzieren. Damit Postfächer aufbewahrt werden können, ist eine Exchange Online Plan 2-Lizenz für das Postfach erforderlich, das Sie in die Warteschleife setzen möchten.
    
- **Was sollten Sie sonst wissen, wenn Sie alle Fall Inhalte in Schritt 5 durchsuchen?** Wie bereits erläutert, können Sie die inhaltsspeicherorte durchsuchen, die in der Anfrage gespeichert wurden. Wenn Sie dies tun, wird nur der Inhalt gesucht, der mit den Aufbewahrungs Kriterien übereinstimmt. Wenn keine Aufbewahrungs Kriterien vorhanden sind, werden alle Inhalte durchsucht. Wenn sich der Inhalt auf einem abfragebasierten Haltebereich befindet, werden nur die Inhalte, die sowohl die Aufbewahrungs Kriterien (aus dem in Schritt 4 festgelegten Speicherplatz) als auch die Suchkriterien (aus der Suche in Schritt 5) entsprechen, mit den Suchergebnissen zurückgegeben.
    
    Im folgenden finden Sie einige andere Punkte, die Sie beim Durchsuchen aller Case-Inhalte beachten sollten:
    
  - Wenn ein Inhaltsspeicherort Teil mehrerer haltebereiche im gleichen Fall ist, werden die Aufbewahrungs Abfragen durch einen **oder** -Operator kombiniert, wenn Sie diesen Inhaltsspeicherort mithilfe der Option "alle Groß-/Kleinschreibung" Durchsuchen. Wenn ein Inhaltsspeicherort Teil von zwei unterschiedlichen Haltebereichen ist, wobei einer auf Abfrage basiert und der andere ein unbegrenzter Speicher ist (wobei der gesamte Inhalt in den Haltebereich gesetzt wird), wird der gesamte Inhalt aufgrund des unbegrenzten Haltestatus durchsucht. 
    
  - Wenn eine Inhaltssuche für einen Fall gilt und Sie Sie so konfiguriert haben, dass alle Fall Inhalte durchsucht werden und Sie dann einen Haltestatus ändern (durch Hinzufügen oder Entfernen eines Inhaltsspeicherorts oder Ändern der halte Abfrage), wird die Suchkonfiguration mit diesen Änderungen aktualisiert. Sie müssen die Suche jedoch erneut ausführen, nachdem der Haltebereich geändert wurde, um die Suchergebnisse zu aktualisieren.
    
  - Wenn mehrere Case-Aufbewahrungsorte an einer Inhaltsposition in einem eDiscovery-Fall gespeichert werden und Sie alle Fall Inhalte durchsuchen möchten, beträgt die maximale Anzahl von Stichwörtern für diese Suchabfrage 500. Das liegt daran, dass die Inhaltssuche alle abfragebasierten Haltestatus mit dem Operator **or** kombiniert. Wenn in den kombinierten Aufbewahrungs Abfragen und der Inhalts Suchabfrage mehr als 500 Schlüsselwörter vorhanden sind, wird der gesamte Inhalt im Postfach durchsucht, und nicht nur der Inhalt, der mit abfragebasierten Fällen übereinstimmt. 
    
  - Wenn ein Case Hold den Status " **Einschalten**" aufweist, können Sie die Speicherorte der Fall Inhalte weiterhin durchsuchen, während der Haltebereich aktiviert ist.
    
  - Wenn eine Suche so konfiguriert ist, dass alle Fall Inhalte durchsucht werden, können Sie, wie bereits erwähnt, diese Suche nicht einschließen, wenn Sie die Ergebnisse mehrerer Suchvorgänge exportieren möchten. Wenn eine Suche so konfiguriert ist, dass alle Fall Inhalte durchsucht werden, müssen Sie die Ergebnisse dieser einzelnen Suche exportieren.
    
- **Wenn ein Postfach, eine SharePoint-Website oder ein OneDrive-Konto, das in der Warteschleife ist, in eine andere Region in einer Multi-Geo-Umgebung verschoben wird, wird der Haltebereich dennoch angewendet?** In allen Fällen werden die Inhalte in einem Postfach-, Standort-oder OneDrive-Konto weiterhin beibehalten. Die Aufbewahrungs Statistik enthält jedoch keine Elemente mehr von einem Inhaltsspeicherort, der in eine andere Region verschoben wurde. Wenn Sie Aufbewahrungs Statistiken für einen verschobenen Inhaltsspeicherort einschließen möchten, müssen Sie den Aufbewahrungsplatz bearbeiten und die URL (oder SMTP-Adresse eines Postfachs) aktualisieren, damit der Inhaltsspeicherort wieder in die halte Statistik aufgenommen wird. 
    
- **Was ist mit dem Platzieren eines Haltestatus für Office 365 Gruppen und Microsoft Teams?** Microsoft Teams ist auf Office 365 Gruppen aufgebaut. Daher ist es ähnlich, dass Sie in einem eDiscovery-Fall in den Haltebereich versetzt werden. Beachten Sie beim Platzieren von Office 365 Gruppen und Microsoft Teams die folgenden Aspekte. 
    
  - Zum Platzieren von Inhalten in Office 365 Gruppen und in Microsoft Teams müssen Sie das Postfach und die SharePoint-Website angeben, die einer Gruppe oder einem Team zugeordnet sind.
    
  - Führen Sie das Cmdlet **Get-Unifiedgroup** in Exchange Online aus, um Eigenschaften für eine Office 365 Gruppe oder ein Microsoft-Team anzuzeigen. Dies ist eine gute Möglichkeit, die URL für die Website abzurufen, die einer Office 365 Gruppe oder einem Microsoft-Team zugeordnet ist. Mit dem folgenden Befehl werden z. B. ausgewählte Eigenschaften für die Office 365-Gruppe „Geschäftsleitung“ angezeigt: 
    
       ```text
       Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl

       DisplayName            : Senior Leadership Team
       Alias                  : seniorleadershipteam
       PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
       SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
       ```

    > [!NOTE]
    > Zum Ausführen des **Get-UnifiedGroup**-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde. 
  
  - Wenn das Postfach eines Benutzers durchsucht wird, werden alle Office 365 Gruppen oder Microsoft Teams, bei denen der Benutzer Mitglied ist, nicht durchsucht. Wenn Sie eine Office 365 Gruppe oder ein Microsoft-Team halten, wird auf ähnliche Weise nur das Gruppenpostfach und die Gruppen Website in den Haltebereich verschoben. Die Postfächer und OneDrive für Unternehmen Websites von Gruppenmitgliedern werden nicht in den Haltestatus versetzt, es sei denn, Sie fügen Sie explizit in den Haltebereich ein. Wenn Sie daher eine Office 365 Gruppe oder ein Microsoft-Team aus einem rechtlichen Grund in die Warteschleife stellen müssen, sollten Sie die Postfächer und OneDrive für Unternehmen Websites für Gruppen-und Teammitglieder in demselben Archiv hinzufügen.
    
  - Wenn Sie eine Liste der Mitglieder einer Office 365 Gruppe oder eines Microsoft-Teams erhalten möchten, können Sie die Eigenschaften auf der Seite " **Start \> Gruppen** " im Microsoft 365 Admin Center anzeigen. Alternativ können Sie den folgenden Befehl in Exchange Online-PowerShell ausführen: 
    
    ```powershell
    Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
    ```

    > [!NOTE]
    > Zum Ausführen des **Get-UnifiedGroupLinks**-Cmdlets müssen Sie über die Rolle "Empfänger (nur Anzeige)" in Exchange Online verfügen oder ein Mitglied einer Rollengruppe sein, der die Rolle "Empfänger (nur Anzeige)" zugewiesen wurde. 
  
  - Unterhaltungen, die Teil eines Microsoft Teams-Kanals sind, werden in dem Postfach gespeichert, das dem Microsoft-Team zugeordnet ist. Gleichermaßen werden Dateien, die Teammitglieder in einem Kanal freigeben, auf der SharePoint-Website des Teams gespeichert. Daher müssen Sie das Microsoft Team-Postfach und die SharePoint-Website speichern, um Unterhaltungen und Dateien in einem Kanal beizubehalten.
    
    Alternativ werden Unterhaltungen, die Teil der Chatliste in Microsoft Teams sind, im Postfach des Benutzers gespeichert, der am Chat teilnimmt. Und Dateien, die ein Benutzer in Chat Unterhaltungen freigibt, werden auf der OneDrive für Unternehmen Website des Benutzers gespeichert, der die Datei freigibt. Daher müssen Sie die einzelnen Benutzerpostfächer und OneDrive für Unternehmen Websites in der Warteschleife platzieren, um Unterhaltungen und Dateien in der Chat Liste beizubehalten. Daher empfiehlt es sich, die Postfächer von Mitgliedern eines Microsoft-Teams zusätzlich zur Aufbewahrung des Team Postfachs (und der Website) in einem Archiv zu platzieren.
    
    > [!IMPORTANT]
    > Benutzer, die an Unterhaltungen teilnehmen, die Teil der Chat Liste in Microsoft Teams sind, müssen über ein Exchange Online (Cloud-basiertes) Postfach verfügen, um Chat Unterhaltungen beizubehalten, wenn das Postfach in einen eDiscovery-Speicher gesetzt wird. Das liegt daran, dass Unterhaltungen, die Teil der Chat Liste sind, in den cloudbasierten Postfächern der Chat Teilnehmer gespeichert werden. Wenn ein Chat Teilnehmer kein Exchange Online Postfach hat, können Sie keine Chat Unterhaltungen beibehalten. Beispielsweise können Benutzer mit einem lokalen Postfach in einer Exchange-hybridbereitstellung an Unterhaltungen teilnehmen, die Teil der Chat Liste in Microsoft Teams sind. In diesem Fall können Inhalte aus diesen Unterhaltungen jedoch nicht beibehalten werden, da die Benutzer keine cloudbasierten Postfächer haben. 
  
  - Jeder Microsoft-Team-oder Team Kanal enthält ein wiki für die Notizen und die Zusammenarbeit. Die Wiki-Inhalte werden automatisch in einer Datei im MHT-Format gespeichert. Diese Datei wird in der Dokumentbibliothek für Wiki-Daten auf der SharePoint-Website des Teams gespeichert. Sie können die Inhalte im wiki in der Warteschleife platzieren, indem Sie die SharePoint-Website des Teams in der Warteschleife platzieren.
    
    > [!NOTE]
    > Die Funktion zum Beibehalten von wiki-Inhalten für einen Microsoft-Team-oder Team Kanal (wenn Sie die SharePoint-Website des Teams in der Warteschleife platzieren) wurde am 22. Juni 2017 veröffentlicht. Wenn eine Teamwebsite gespeichert ist, wird der Inhalt des Wikis ab diesem Datum beibehalten. Wenn jedoch eine Teamwebsite gespeichert ist und der Inhalt des Wikis vor dem 22. Juni 2017 gelöscht wurde, wurde der Inhalt des Wikis nicht beibehalten. 

- **Wie finde ich die URL für OneDrive für Unternehmen Websites?** Informationen zum Sammeln einer Liste der URLs für die OneDrive für Unternehmen Websites in Ihrer Organisation, damit Sie Sie zu einem Haltestatus oder einer Suche hinzufügen können, die einem eDiscovery-Fall zugeordnet ist, finden Sie unter [Erstellen einer Liste aller OneDrive-Standorte in Ihrer Organisation](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Mit dem Skript in diesem Artikel wird eine Textdatei erstellt, die eine Liste aller OneDrive-Websites enthält. Um dieses Skript ausführen zu können, müssen Sie die SharePoint Online-Verwaltungsshell installieren und verwenden. Achten Sie darauf, die URL für die "MeineWebsite"-Domäne Ihrer Organisation an jede OneDrive-Website anzuhängen, die Sie durchsuchen möchten. Dies ist die Domäne, die Ihr gesamtes OneDrive enthält, z. B. `https://contoso-my.sharepoint.com`. Hier ein Beispiel für die URL der OneDrive-Website eines Benutzers: `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`.
