---
title: Verwalten von eDiscovery-Fällen im Security & Compliance Center
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: 10/12/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 9a00b9ea-33fd-4772-8ea6-9d3c65e829e6
description: 'Verwenden Sie das Security #a0 Compliance Center, um eDiscovery-Aufbewahrungen zu erstellen und auf eDiscovery-Fälle in Ihrer Organisation zuzugreifen und Sie zu verwalten.'
ms.openlocfilehash: 026bd31145dc73261012a9cde1b6befd19ddba4d
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37081620"
---
# <a name="manage-ediscovery-cases-in-the-security--compliance-center"></a>Verwalten von eDiscovery-Fällen im Security & Compliance Center

Sie können eDiscovery-Fälle im Security #a0 Compliance Center verwenden, um zu steuern, wer eDiscovery-Fälle in Ihrer Organisation erstellen, auf Sie zugreifen und diese verwalten kann. Wenn Ihre Organisation über ein Office 365 E5-Abonnement verfügt, können Sie auch mithilfe von eDiscovery-Fällen Suchergebnisse mithilfe Office 365 Advanced eDiscovery analysieren.
  
Mit einem eDiscovery-Fall können Sie einem Fall Mitglieder hinzufügen, Steuern, welche Arten von Aktionen von bestimmten Fall Mitgliedern ausgeführt werden können, Aufbewahrungsmöglichkeiten für für einen Rechtsfall relevanter Inhaltsspeicher platzieren und mehrere Inhalts suchen mit einem einzigen Fall verknüpfen. Sie können auch die Ergebnisse einer beliebigen Inhaltssuche exportieren, die einem Fall zugeordnet ist, oder Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten. eDiscovery-Fälle sind eine gute Möglichkeit, um zu beschränken, wer Zugriff auf Inhaltssuchen und Suchergebnisse für einen bestimmten Rechtsfall in Ihrer Organisation hat.
  
Verwenden Sie den folgenden Workflow zum Einrichten und Verwenden von eDiscovery-Fällen im Security #a0 Compliance Center und in Advanced eDiscovery.
  
[Step 1: Assign eDiscovery permissions to potential case members](manage-ediscovery-cases.md#step1_1)
  
[Schritt 2: Erstellen einer neuen Anfrage](manage-ediscovery-cases.md#step2_1)
  
[Schritt 3: Hinzufügen von Mitgliedern zu einer Anfrage](manage-ediscovery-cases.md#step2a_1)
  
[Schritt 4: Platzieren von Inhaltsspeicherorten in der Warteschleife](manage-ediscovery-cases.md#step3_1)
  
[Schritt 5: Erstellen und Ausführen einer einem Fall zugeordneten Inhaltssuche](manage-ediscovery-cases.md#step4_1)
  
[Schritt 6: Exportieren der Ergebnisse einer Inhaltssuche, die einer Anfrage zugeordnet ist](manage-ediscovery-cases.md#step5_1)
  
[Schritt 7: Vorbereiten der Suchergebnisse für Advanced eDiscovery](manage-ediscovery-cases.md#step7_1)
  
[Schritt 8: Wechseln zu der Groß-/Kleinschreibung in Advanced eDiscovery](manage-ediscovery-cases.md#gotoAeD_1)
  
[Optional Schritt 9: Schließen eines Falls](manage-ediscovery-cases.md#closecase_1)
  
[Optional Schritt 10: Erneutes Öffnen eines geschlossenen Falls](manage-ediscovery-cases.md#reopencase_1)
  
[Weitere Informationen](manage-ediscovery-cases.md#moreinfo_1)
  
## <a name="step-1-assign-ediscovery-permissions-to-potential-case-members"></a>Schritt 1: Zuweisen von eDiscovery-Berechtigungen zu potenziellen Fallmitgliedern
<a name="step1_1"> </a>

Der erste Schritt besteht darin, Personen die entsprechenden eDiscovery-bezogenen Berechtigungen zuzuweisen, damit Sie Sie in Schritt 2 zu einem eDiscovery-Fall hinzufügen können. Sie müssen Mitglied der Rollengruppe "Organisationsverwaltung" (oder der Rolle "Rollenverwaltung" zugewiesen) im Sicherheits #a0 Compliance Center sein, um eDiscovery-Berechtigungen zuzuweisen. In der folgenden Liste werden die eDiscovery-bezogenen Rollengruppen im Security #a0 Compliance Center beschrieben.
  
- **Prüfer** Diese Rollengruppe verfügt über die restriktivsten eDiscovery-bezogenen Berechtigungen. Mitglieder dieser Gruppe können die Liste der Fälle auf der Seite " **eDiscovery** " im Security #a0 Compliance Center nur anzeigen und öffnen, von der Sie Mitglieder sind. Sie können keine Fälle erstellen, einem Fall Mitglieder hinzufügen, Aufbewahrungen erstellen, Suchergebnisse exportieren oder Ergebnisse für Advanced eDiscovery vorbereiten. Mitglieder können jedoch auf Fälle in Advanced eDiscovery zugreifen, um Analyseaufgaben auszuführen. 
    
- **eDiscovery-Manager** Mitglieder dieser Rollengruppe können eDiscovery-Fälle erstellen und verwalten. Sie können Mitglieder hinzufügen und entfernen, inhaltsspeicherorte in der Warteschleife platzieren, Inhalts suchen, die einem Fall zugeordnet sind, erstellen und bearbeiten, die Ergebnisse einer Inhaltssuche exportieren und Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten. In dieser Rollengruppe gibt es zwei Untergruppen. Der Unterschied zwischen diesen Untergruppen basiert auf dem Bereich.
    
  - **eDiscovery-Manager** Kann die eDiscovery-Fälle anzeigen und verwalten, in denen Sie erstellt werden oder deren Mitglied Sie sind. Wenn ein anderer eDiscovery-Manager einen Fall erstellt, aber keinen zweiten eDiscovery-Manager als Mitglied dieses Falles hinzufügt, kann der zweite eDiscovery-Manager den Fall nicht auf der **eDiscovery** -Seite im Security #a0 Compliance Center anzeigen oder öffnen. eDiscovery-Manager können auch auf ihre Fälle in Advanced eDiscovery zugreifen, um Analyseaufgaben durchzuführen. 
    
  - **eDiscovery-Administrator** Kann alle Fall Verwaltungsaufgaben ausführen, die ein eDiscovery-Manager ausführen kann. Darüber hinaus können eDiscovery-Administratoren folgende Aktionen durchführen:
    
  - Anzeigen aller Fälle, die auf der Seite **eDiscovery-Fälle** aufgeführt sind. 
    
  - Verwalten Sie alle eDiscovery-Fälle in der Organisation, nachdem Sie sich selbst als Mitglied der Anfrage hinzugefügt haben.
    
  - Ausführen von administrativen Aufgaben in Advanced eDiscovery, beispielsweise verarbeiten von Falldaten für die Analyse, Konfigurieren von Fall Einstellungen und Exportieren von Daten aus Advanced eDiscovery. Dies liegt daran, dass eine Person, die ein eDiscovery-Administrator im Security #a0 Compliance Center ist, automatisch als Administrator in Advanced eDiscovery hinzugefügt wird.
    
    Überlegungen dazu, warum Sie ggf. einen eDiscovery-Administrator in Ihrer Organisation benötigen, finden Sie im Abschnitt [More information](manage-ediscovery-cases.md#moreinfo_1). 
    
> [!IMPORTANT]
> Wenn eine Person nicht Mitglied einer dieser eDiscovery-bezogenen Rollengruppen ist oder kein Mitglied einer Rollengruppe ist, der die Rolle "Prüfer" zugewiesen ist, können Sie Sie nicht als Mitglied eines eDiscovery-Falls hinzufügen. 
  
 **So weisen Sie eDiscovery-Berechtigungen zu**
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich bei Office 365 mit Ihrem Geschäfts-, Schul- oder Unikonto an.
    
3. Klicken Sie im Security #a0 Compliance Center auf **Berechtigungen**, und führen Sie eine der folgenden Aktionen basierend auf den eDiscovery-Berechtigungen aus, die Sie zuweisen möchten.
    
  - Um Berechtigungen für Prüfer zuzuweisen, wählen Sie die Rollengruppe **Prüfer** aus, und klicken Sie dann neben **Mitglieder** auf **Bearbeiten**. Klicken Sie auf **Mitglieder auswählen**, ![klicken](media/ITPro-EAC-AddIcon.gif) Sie **auf Symbol hinzufügen wählen** Sie den Benutzer aus, den Sie der Rollengruppe Prüfer hinzufügen möchten, und klicken Sie dann auf **hinzu**fügen.
    
  - Um eDiscovery Manager-Berechtigungen zuzuweisen, wählen Sie die Rollengruppe **eDiscovery-** Manager aus, und klicken Sie dann neben **eDiscovery-Manager**auf **Bearbeiten**. Klicken Sie auf **eDiscovery-Manager auswählen**, klicken Sie auf ![Symbol](media/ITPro-EAC-AddIcon.gif) hinzufügen * * hinzufügen * *, wählen Sie den Benutzer aus, den Sie als eDiscovery-Manager hinzufügen möchten, und klicken Sie dann auf **Hinzufügen**.
    
  - Um eDiscovery-Administratorberechtigungen zuzuweisen, wählen Sie die Rollengruppe **eDiscovery-Manager** aus, und klicken Sie dann neben **eDiscovery-Administrator**auf **Bearbeiten**. Klicken Sie auf **eDiscovery-Administrator auswählen**, klicken Sie auf ![Symbol](media/ITPro-EAC-AddIcon.gif) **hinzu**fügen, wählen Sie den Benutzer aus, den Sie als eDiscovery-Administrator hinzufügen möchten, und klicken Sie dann auf **hinzu**fügen.
    
4. Nachdem Sie alle Benutzer hinzugefügt haben, klicken Sie auf **Fertig**, klicken Sie auf **Speichern** , um die Änderungen an der Rollengruppe zu speichern, und klicken Sie dann auf **Schließen**.
    

  
## <a name="step-2-create-a-new-case"></a>Schritt 2: Erstellen einer neuen Anfrage
<a name="step2_1"> </a>

Der nächste Schritt besteht darin, einen neuen eDiscovery-Fall zu erstellen. Sie müssen Mitglied der Rollengruppe „eDiscovery-Manager“ sein, um eDiscovery-Fälle zu erstellen. Wie bereits erläutert, können Sie (und andere Fall Mitglieder) nach dem Erstellen eines neuen Falls im Security #a0 Compliance Center auf denselben Fall in Advanced eDiscovery zugreifen, wenn Sie eine Organisation mit einem Office 365 E5-Abonnement haben.
  
1. Wechseln Sie zu [https://protection.office.com](https://protection.office.com).
    
2. Melden Sie sich bei Office 365 mit Ihrem Geschäfts-, Schul- oder Unikonto an.
    
3. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery**, und klicken Sie ![dann auf](media/ITPro-EAC-AddIcon.gif) Symbol hinzufügen, **um eine Anfrage zu erstellen**.
    
4. Geben Sie auf der Seite **neuer Fall** einen Namen ein, geben Sie eine optionale Beschreibung ein, und klicken Sie dann auf **Speichern**. Beachten Sie, dass der Case-Name in Ihrer Organisation eindeutig sein muss.
    
    ![Neue Case-Seite](media/538f66b8-eb6e-4c4c-83d8-7154fd85883a.png)
  
    Der neue Fall wird in der Liste der Fälle auf der **eDiscovery** -Seite angezeigt. Beachten Sie, dass Sie den Mauszeiger über einen Fallnamen bewegen können, um Informationen über den Fall anzuzeigen, einschließlich des Status der Anfrage ( **aktiv** oder **geschlossen**), der Beschreibung des Falls (die im vorherigen Schritt erstellt wurde), und wenn der Fall zuletzt geändert wurde und Wer es geändert hat.
    
    > [!TIP]
    > Nachdem Sie einen neuen Fall erstellt haben, können Sie ihn jederzeit umbenennen. Klicken Sie auf der **eDiscovery** -Seite einfach auf den Namen des Falls. Ändern Sie auf der Seite **diesen Fall Flyout verwalten** den Namen, der in dem Feld unter **Name**angezeigt wird, und speichern Sie die Änderung. 
  
## <a name="step-3-add-members-to-a-case"></a>Schritt 3: Hinzufügen von Mitgliedern zu einer Anfrage
<a name="step2a_1"> </a>

Nachdem Sie einen neuen Fall erstellt haben, besteht der nächste Schritt darin, der Anfrage Mitglieder hinzuzufügen. Wie zuvor erläutert, können nur Benutzer, die Mitglieder der Rollengruppen Prüfer oder eDiscovery-Manager sind, als Mitglied der Anfrage hinzugefügt werden. Beachten Sie, dass der eDiscovery-Manager, der den Fall erstellt hat, automatisch als Mitglied hinzugefügt wird.
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie auf den Namen des Falls, dem Sie Mitglieder hinzufügen möchten.
    
    Die Dropdown Seite **diesen Fall verwalten** wird angezeigt. 
    
    ![Klicken Sie auf den Namen der Groß-/Kleinschreibung, um die Seite diesen Fall zu verwalten anzuzeigen.](media/2364dc08-a3dc-4724-acf4-7a68c8588e6f.png)
  
3. Klicken Sie ![unter **Mitglieder verwalten**auf Symbol](media/ITPro-EAC-AddIcon.gif) **hinzu** fügen, um der Anfrage Mitglieder hinzuzufügen. 
    
4. Klicken Sie in der Liste der Personen, die als Mitglied der Anfrage hinzugefügt werden können, auf das Kontrollkästchen neben dem Namen der Personen, die Sie der Anfrage hinzufügen möchten.
    
    > [!TIP]
    > Wenn Sie eine große Liste von Personen haben, die als Mitglieder hinzugefügt werden können, verwenden Sie das **Suchfeld** , um nach einer bestimmten Person in der Liste zu suchen. 
  
5. Nachdem Sie die Personen ausgewählt haben, die als Mitglieder der Gruppe hinzugefügt werden sollen, klicken Sie auf **Hinzufügen**.
    
    Klicken Sie in **diesem Fall verwalten**auf **Speichern** , um die neue Liste der Fall Mitglieder zu speichern. 
    
6. Klicken Sie auf **Speichern** , um die neue Liste der Fall Mitglieder zu speichern. 
  
## <a name="step-4-place-content-locations-on-hold"></a>Schritt 4: Platzieren von Inhaltsspeicherorten in der Warteschleife
<a name="step3_1"> </a>

Sie können einen eDiscovery-Fall zum Erstellen von Haltebereichen verwenden, um Inhalte beizubehalten, die möglicherweise für den Fall relevant sind. Sie können die Postfächer und OneDrive für Unternehmen Websites von Personen, die für den Fall Verwalter sind, aufbewahren. Sie können auch das Gruppenpostfach, die SharePoint-Website und die OneDrive für Unternehmen Website für eine Office 365 Gruppe aufbewahren. Ebenso können Sie das Postfach und die Website, die Microsoft Teams zugeordnet sind, aufbewahren. Wenn Sie inhaltsspeicherorte in der Warteschleife platzieren, wird der Inhalt so lange aufbewahrt, bis Sie den Haltebereich vom Inhaltsspeicherort entfernen oder bis Sie den Haltebereich löschen.
  
Wenn Sie einen Haltebereich erstellen, haben Sie die folgenden Optionen, um den Inhalt zu belegen, der an den angegebenen Inhaltsspeicherorten gehalten wird:
  
- Sie erstellen einen unbegrenzten Haltebereich, in dem der gesamte Inhalt aufbewahrt wird. Alternativ können Sie einen abfragebasierten Speicher erstellen, in dem nur Inhalte, die einer Suchabfrage entsprechen, in die Warteschleife gestellt werden.
    
- Sie können einen Datumsbereich angeben, in dem nur der Inhalt gespeichert werden soll, der innerhalb dieses Datumsbereichs gesendet, empfangen oder erstellt wurde. Alternativ können Sie alle Inhalte speichern, unabhängig davon, wann Sie gesendet, empfangen oder erstellt wurden.
    
> [!NOTE]
> Sie können maximal 10.000-Speicherrichtlinien für alle eDiscovery-Fälle in Ihrer Organisation festlegen. 
  
So erstellen Sie einen Aufbewahrungsplatz für einen eDiscovery-Fall:
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, in dem Sie die Aufbewahrungspflicht erstellen möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf **halten**.
    
    ![Klicken Sie auf speichern, um die Seite Fall Haltestatus anzuzeigen.](media/25c0300a-bd33-4443-a121-d595b1a3e00f.png)
  
4. Klicken Sie auf der Seite **Haltestatus** auf **Neues**![Symbol](media/ITPro-EAC-AddIcon.gif)hinzufügen.
    
5. Geben Sie auf der Seite **neuen Haltestatus erstellen** dem Haltestatus einen Namen. Der Name des haltebereichs muss in Ihrer Organisation eindeutig sein. 
    
6. Wählen Sie die inhaltsspeicherorte aus, die Sie in die Warteschleife stellen möchten. Sie können Postfächer, Websites und öffentliche Ordner in der Warteschleife platzieren.
    
    ![Wählen Sie Inhaltsspeicherorte aus, die im Haltebereich platziert werden sollen.](media/a00c952c-f91f-4708-b5a4-6213e4c413c7.png)
  
1. **Postfächer** Klicken Sie auf Add](media/ITPro-EAC-AddIcon.gif) -Symbol **Hinzufügen**![, um Postfächer für die Aufbewahrung festzulegen. Verwenden Sie das Suchfeld, um nach Benutzerpostfächern und Verteilergruppen zu suchen (um die Postfächer der Gruppenmitglieder festhalten zu können), damit Sie in der Warteschleife platziert werden. Sie können das zugeordnete Postfach auch für eine Office 365 Gruppe oder ein Microsoft-Team aufbewahren. 
    
    > [!NOTE]
    > Wenn Sie auf Add-Symbol](media/ITPro-EAC-AddIcon.gif) **Hinzufügen**![klicken, um die Aufbewahrungspflicht für Postfächer festzulegen, ist die angezeigte Post Fachauswahl leer. Dies ist beabsichtigt, um die Leistung zu verbessern. Um Personen zu dieser Liste hinzuzufügen, geben Sie einen Namen (mindestens 3 Zeichen) in das Suchfeld ein, und ****![klicken Sie auf](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)Suchsymbol suchen. 
  
2. **Websites** Klicken Sie auf Add](media/ITPro-EAC-AddIcon.gif) -Symbol **Hinzufügen**![, um SharePoint und OneDrive für Unternehmen Websites anzugeben, die in der Warteschleife platziert werden. Geben Sie die URL für jede Website ein, die Sie in die Warteschleife stellen möchten. Sie können auch die URL für die SharePoint-Website für eine Office 365 Gruppe oder ein Microsoft-Team hinzufügen. 
    
    Im Abschnitt [Weitere Informationen](https://support.office.com/article/edea80d6-20a7-40fb-b8c4-5e8c8395f6da.aspx#moreinfo_1) finden Sie Tipps zum Platzieren von Office 365 Gruppen und Microsoft Teams in der Warteschleife. 
    
    > [!NOTE]
    > Im seltenen Fall, dass der Benutzerprinzipalname (UPN) einer Person geändert wird, wird die URL für Ihr OneDrive-Konto ebenfalls geändert, um den neuen UPN zu integrieren. In diesem Fall müssen Sie den Haltebereich ändern, indem Sie die neue OneDrive-URL des Benutzers hinzufügen und die alte entfernen. 
  
3. **Öffentliche Ordner** Klicken Sie auf **Alle öffentlichen Ordner speichern** , um alle öffentlichen Ordner in Ihrer Exchange Online Organisation in der Warteschleife zu platzieren. Beachten Sie, dass Sie keine bestimmten öffentlichen Ordner für die Aufbewahrung auswählen können. Lassen Sie die Option keine **öffentlichen Ordner speichern** aktiviert, wenn Sie öffentliche Ordner nicht aufbewahren möchten. 
    
7. Wenn Sie das Hinzufügen von Inhaltsspeicherorten in der Warteschleife abgeschlossen haben, klicken Sie auf **weiter**.
    
8. Um eine abfragebasierte Aufbewahrung mit Bedingungen zu erstellen, führen Sie die folgenden Schritte aus. Klicken Sie andernfalls einfach auf **Fertig stellen** , um den gesamten Inhalt zu speichern. 
    
    ![Erstellen eines abfragebasierten Haltestatus durch Angeben von Schlüsselwörtern und Bedingungen](media/a5bb802e-2e96-4f12-8b33-1ddd671638e4.png)
  
    Weitere Informationen zum Erstellen einer Suchabfrage und zum Verwenden von Bedingungen finden Sie unter [Keyword-Abfragen und Suchbedingungen für die Inhaltssuche](keyword-queries-and-search-conditions.md).
    
1. Geben Sie im Feld unter **Was sollen wir suchen?** eine Suchabfrage in das Feld ein, sodass nur der Inhalt, der die Suchkriterien erfüllt, in der Warteschleife gespeichert wird. Sie können Schlüsselwörter, Nachrichteneigenschaften oder Dokumenteigenschaften wie Dateinamen angeben. Sie können auch komplexere Abfragen verwenden, die einen booleschen Operator wie **and**, **or**oder **Not**verwenden. Wenn Sie das Feld Schlüsselwort leer lassen, werden alle Inhalte, die sich an den angegebenen Inhaltsspeicherorten befinden, aufbewahrt. 
    
2. Klicken Sie unter **Bedingungen**auf **Bedingung hinzufügen** , um eine oder mehrere Bedingungen hinzuzufügen, um die Suchabfrage für den Haltebereich einzuschränken. Jede Bedingung fügt der KQL-Suchabfrage, die erstellt und ausgeführt wird, eine Klausel hinzu, wenn Sie den Haltebereich erstellen. Sie können beispielsweise einen Datumsbereich angeben, damit e-Mail-oder Website Dokumente, die innerhalb des Datumsbereichs erstellt wurden, in der Warteschleife gespeichert werden. Eine Bedingung ist durch **AND**-Operator logisch mit der (im Schlüsselwortfeld angegebenen) Schlüsselwortabfrage verbunden. Das bedeutet, dass Elemente sowohl die Stichwortabfrage als auch die Bedingung erfüllen müssen, die in der Warteschleife gespeichert werden soll. 
    
9. Nachdem Sie einen abfragebasierten Speicher konfiguriert haben, klicken Sie auf **Fertig stellen** , um den Haltestatus zu erstellen. 
  
### <a name="hold-statistics"></a>Aufbewahrungs Statistik

Nach einer Weile werden Informationen zum neuen Haltestatus im Detailbereich auf der Seite halte **Status** des ausgewählten haltebereichs angezeigt. Diese Informationen umfassen die Anzahl der zu speichernden Postfächer und Websites sowie Statistiken zu den Inhalten, die in der Warteschleife gespeichert wurden, beispielsweise die Gesamtanzahl und Größe der zu speichernden Elemente sowie die Uhrzeit, zu der die Aufbewahrungs Statistik zuletzt berechnet wurde. Diese Aufbewahrungs Statistiken helfen Ihnen zu ermitteln, wie viele Inhalte im Zusammenhang mit dem eDiscovery-Fall gehalten werden. 
  
![Aufbewahrungs Statistiken werden im Detailbereich für den ausgewählten Haltestatus angezeigt.](media/e46359a3-cba1-4771-bbf5-bc53b4a2cb14.png)
  
Beachten Sie die folgenden Aspekte bei Aufbewahrungs Statistiken:
  
- Die Gesamtanzahl der Elemente in der Warteschleife gibt die Anzahl der Elemente aus allen Inhaltsquellen an, die in der Warteschleife gespeichert werden. Wenn Sie einen abfragebasierten Haltebereich erstellt haben, gibt diese Statistik die Anzahl der Elemente an, die mit der Abfrage übereinstimmen.
    
- Die Anzahl der zu speichernden Elemente umfasst auch nicht indizierte Elemente, die an den Inhaltsspeicherorten gefunden wurden. Beachten Sie, dass beim Erstellen eines abfragebasierten haltebereichs alle nicht indizierten Elemente in den Inhaltsspeicherorten in der Warteschleife gespeichert werden. Dies umfasst nicht indizierte Elemente, die nicht mit den Suchkriterien eines abfragebasierten haltebereichs und nicht indizierten Elementen übereinstimmen, die möglicherweise außerhalb einer Datumsbereichs Bedingung liegen. Dies unterscheidet sich von dem, was passiert, wenn Sie eine Inhaltssuche ausführen, in der nicht indizierte Elemente, die nicht mit der Suchabfrage übereinstimmen oder von einer Datumsbereichs Bedingung ausgeschlossen werden, nicht in den Suchergebnissen enthalten sind. Weitere Informationen zu nicht indizierten Elementen finden Sie unter nicht [indizierte Elemente in der Inhaltssuche in Office 365](partially-indexed-items-in-content-search.md).
    
- Sie können die neuesten Aufbewahrungs Statistiken abrufen, indem Sie auf **Statistik aktualisieren** klicken, um eine Such Schätzung erneut auszuführen, mit der die aktuelle Anzahl der zu speichernden Elemente berechnet wird. Klicken Sie gegebenenfalls in ****![der Symbolleiste](media/O365-MDM-Policy-RefreshIcon.gif) auf Aktualisierungssymbol aktualisieren, um die Aufbewahrungs Statistiken im Detailbereich zu aktualisieren. 
    
- Es ist normal, dass die Anzahl der zu speichernden Elemente im Laufe der Zeit steigt, da Benutzer, deren Postfach oder Standort in der Warteschleife ist, normalerweise neue e-Mail-Nachrichten senden oder empfangen und neue SharePoint-und OneDrive für Unternehmen-Dokumente erstellen.
  
## <a name="step-5-create-and-run-a-content-search-associated-with-a-case"></a>Schritt 5: Erstellen und Ausführen einer einem Fall zugeordneten Inhaltssuche
<a name="step4_1"> </a>

Nachdem ein eDiscovery-Fall erstellt wurde und alle depotverwalter im Zusammenhang mit dem Fall gespeichert wurden, können Sie eine oder mehrere Inhalts Suchvorgänge erstellen und ausführen, die mit der Anfrage verknüpft sind. Inhalts Suchvorgänge, die einem Fall zugeordnet sind, werden nicht auf der Seite **Suchen** im Security #a0 Compliance Center aufgeführt. Dies bedeutet, dass der Zugriff auf Inhalts suchen, die einem Fall zugeordnet sind, nur von Fall Mitgliedern erreicht werden kann, die auch Mitglieder der eDiscovery-Manager-Rollengruppe sind. 
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, in dem Sie eine Inhaltssuche erstellen möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf **Suchen**.
    
    ![Klicken Sie auf der Startseite der Anfrage auf Suche](media/bd358eb3-12d4-4f0c-8317-d192286813d0.png)
  
4. Klicken Sie auf der Seite **Suchen** auf **Neues**![Symbol](media/ITPro-EAC-AddIcon.gif)hinzufügen.
    
5. Geben Sie auf der Seite **neue Suche** einen Namen für die Suche ein. Inhalts suchen, die einem Fall zugeordnet sind, müssen Namen enthalten, die innerhalb Ihrer Office 365 Organisation eindeutig sind. 
    
6. Wählen Sie die inhaltsspeicherorte aus, die Sie durchsuchen möchten. Sie können Postfächer, Websites und öffentliche Ordner in derselben Suche durchsuchen.
    
    ![Inhaltsspeicherorte für Suchanfragen, alle inhaltsspeicherorte oder bestimmte inhaltsspeicherorte auswählen](media/08c523dc-cba8-4fce-aee6-f86251204393.png)
  
1. **Alle Case-Inhalte** Wählen Sie diese Option aus, um alle inhaltsspeicherorte zu durchsuchen, die in der Anfrage gespeichert wurden. Wenn die Groß-/Kleinschreibung mehrere Haltestatus enthält, werden die inhaltsspeicherorte aus allen Haltebereichen durchsucht, wenn Sie diese Option auswählen. Wenn ein Inhaltsspeicherort in einem abfragebasierten Speicherplatz gefunden wurde, werden beim Ausführen der Inhaltssuche, die Sie in diesem Schritt erstellen, nur die Elemente durchsucht, die in der Warteschleife gespeichert sind. Wenn beispielsweise ein Benutzer auf Abfrage basiertem Case Hold gesetzt wurde, der Elemente aufrecht erhält, die vor einem bestimmten Datum gesendet oder erstellt wurden, werden nur diese Elemente mithilfe der Suchkriterien der Inhaltssuche durchsucht. Dies wird erreicht, indem die Case Hold-Abfrage und die Inhalts Suchabfrage durch einen **and-** Operator verbunden werden. Weitere Informationen zum Suchen von Fall Inhalten finden Sie im Abschnitt [Weitere Informationen](manage-ediscovery-cases.md#moreinfo_1) am Ende dieses Artikels. 
    
2. **Überall suchen** Wählen Sie diese Option aus, um alle inhaltsspeicherorte in Ihrer Organisation zu durchsuchen. Wenn Sie diese Option auswählen, können Sie auswählen, dass alle Exchange-Postfächer durchsucht werden sollen (einschließlich der Postfächer für alle Office 365 Gruppen und Microsoft Teams), alle SharePoint-und OneDrive für Unternehmen-Websites (einschließlich der Websites für alle Office 365 Gruppen und Microsoft Teams) und alle öffentlichen Ordner.
    
3. **Benutzerdefinierte Standortauswahl** Wählen Sie diese Option aus, um die Postfächer und Websites auszuwählen, die Sie durchsuchen möchten. Wenn Sie diese Option auswählen, wird die Liste der Postfächer und Websites vorab mit den Inhaltsspeicherorten aufgefüllt, die in der Anfrage gespeichert werden. Sie haben auch die Möglichkeit, alle öffentlichen Ordner in Ihrer Organisation zu durchsuchen.
    
    ![Durchsuchen aller Fall Inhalte, Durchsuchen aller Speicherorte oder Durchsuchen eines benutzerdefinierten Speicherorts](media/7ca97ab4-52d5-46a5-9e24-e3a4d1001595.png)
  
    Wenn Sie diese Option auswählen und einen beliebigen Inhaltsspeicherort in der Warteschleife durchsuchen, wird keine Abfrage von einem abfragebasierten Aufbewahrungs Fall auf die Suchabfrage angewendet. In anderen Worten wird der gesamte Inhalt eines Standorts durchsucht, und nicht nur der Inhalt, der von einem abfragebasierten Aufbewahrungsplatz beibehalten wird.
    
    Sie können die zuvor aufgefüllten Speicherorte für Inhalte entfernen oder neue hinzufügen. Wenn Sie diese Option auswählen, haben Sie auch die Flexibilität, alle inhaltsspeicherorte für einen bestimmten Dienst zu durchsuchen (beispielsweisedurch Suchen aller Exchange-Postfächer), oder Sie können bestimmte inhaltsspeicherorte für einen Dienst durchsuchen. Sie können auch auswählen, ob die öffentlichen Ordner in Ihrer Organisation durchsucht werden sollen.
    
    Beachten Sie beim Hinzufügen von Inhaltsspeicherorten zur Suche Folgendes:
    
  - Wenn Sie auf Add-Symbol](media/ITPro-EAC-AddIcon.gif) **Hinzufügen**![klicken, um die zu durchsuchenden Postfächer anzugeben, ist die angezeigte Post Fachauswahl leer. Dies ist beabsichtigt, um die Leistung zu verbessern. Wenn Sie dieser Liste Empfänger hinzufügen möchten, geben Sie einen Namen (mindestens 3 Zeichen) in das Suchfeld ein, ****![und klicken Sie](media/5f6f9463-50e9-460b-8738-b67e759c2efc.gif)auf Suchsymbol suchen.
    
  - Sie können inaktive Postfächer, Office 365 Gruppen, Microsoft Teams und Verteilergruppen zur Liste der zu durchsuchenden Postfächer hinzufügen. Dynamische Verteilergruppen werden nicht unterstützt. Wenn Sie Office 365 Gruppen oder Microsoft Teams hinzufügen, wird das Gruppen-oder Team Postfach durchsucht. die Postfächer der Gruppenmitglieder werden nicht durchsucht.
    
  - Wenn Sie keine Postfächer oder Websites in eine Suche einschließen möchten, wählen Sie **bestimmte zu durchsuchende Postfächer** auswählen aus, oder **Wählen Sie bestimmte Websites für**die Suche aus, aber fügen Sie der Liste keine Postfächer oder Websites hinzu.
    
  - Klicken Sie zum Hinzufügen von Websites](media/ITPro-EAC-AddIcon.gif) auf![Add- **Symbol hinzufügen**, und geben Sie dann die URL für jede Website ein, die Sie durchsuchen möchten. Sie können auch die URL für die SharePoint-Website für Office 365 Gruppen und Microsoft Teams hinzufügen. 
    
7. Nachdem Sie die zu durchsuchenden inhaltsspeicherorte ausgewählt haben, klicken Sie auf **weiter**.
    
8. Auf der Seite **Neue Suche** können Sie Schlüsselwörter und Bedingungen zum Erstellen der Suchabfrage hinzufügen. <br/>![Suchkriterien und-Bedingungen](media/9064147e-feac-4090-bbf6-2298ad7622c6.png)
  
9. Geben Sie im Feld unter **Wonach sollen wir für Sie suchen?** eine Suchabfrage ein. Sie können Schlüsselwörter, Nachrichteneigenschaften , z. B. Sende- und Empfangsdatum, oder Dokumenteigenschaften angeben, z. B. Dateinamen oder das Datum der letzten Dokumentänderung. Sie können komplexere Abfragen verwenden, die einen booleschen Operator verwenden, beispielsweise **and**, **or**, **Not**, **near**oder **ONEAR**. Sie können auch nach vertraulichen Informationen (wie etwa Sozialversicherungsnummern) in Dokumenten suchen oder nach Dokumenten suchen, die extern freigegeben wurden. Wenn Sie das Feld Schlüsselwort leer lassen, werden alle Inhalte, die sich an den angegebenen Inhaltsspeicherorten befinden, in die Suchergebnisse eingeschlossen. 
    
10. Sie können auf das Kontrollkästchen **Keyword-Liste anzeigen** und in jeder Zeile ein Stichwort eingeben. Wenn Sie dies tun, werden die Schlüsselwörter für jede Zeile durch den **or** -Operator in der erstellten Suchabfrage miteinander verbunden. 
    
    ![Schlüsselwörter für die Suche](media/c3ef511a-e0a3-4b5d-9779-36803270a193.png)
  
    Gründe für die Verwendung der Stichwortliste Sie können Statistiken abrufen, die zeigen, wie viele Elemente mit den einzelnen Schlüsselwörtern übereinstimmen. Auf diese Weise können Sie schnell erkennen, welche Stichwörter am häufigsten (und am wenigsten) effektiv sind. Sie können auch eine Stichwort Phrase (umgeben von Klammern) in einer Zeile verwenden. Weitere Informationen zu Suchstatistiken finden Sie unter [Anzeigen von Keyword-Statistiken für Inhalts Suchergebnisse](view-keyword-statistics-for-content-search.md).
    
    Weitere Informationen zur Verwendung der Liste Stichwörter finden Sie unter [Weitere Informationen](run-a-content-search-in-the-security-and-compliance-center.md#moreinfo).
    
11. Klicken Sie auf **Abfrage für Tippfehler überprüfen** , um Ihre Abfrage auf nicht unterstützte Zeichen und boolesche Operatoren zu überprüfen, die möglicherweise nicht groß geschrieben werden. Nicht unterstützte Zeichen werden häufig ausgeblendet und verursachen in der Regel einen Suchfehler oder geben unbeabsichtigte Ergebnisse zurück. Weitere Informationen zu den nicht unterstützten Zeichen, die überprüft werden, finden Sie unter [Überprüfen der Inhalts Suchabfrage auf Fehler](check-your-content-search-query-for-errors.md).
    
12. Fügen Sie unter **Bedingungen**einer Suchabfrage Bedingungen hinzu, um eine Suche einzuschränken und eine verfeinerte Ergebnismenge zurückzugeben. Jede Bedingung fügt eine Klausel zu der KQL-Suchabfrage hinzu, die beim Starten der Suche erstellt und ausgeführt wird. Eine Bedingung ist durch **AND**-Operator logisch mit der (im Schlüsselwortfeld angegebenen) Schlüsselwortabfrage verbunden. Dies bedeutet, dass Elemente sowohl die Schlüsselwortabfrage als auch die Bedingung erfüllen muss, damit sie in die Suchergebnisse aufgenommen werden. Auf diese Weise können Sie Ihre Ergebnisse mit Bedingungen eingrenzen. 
    
    Weitere Informationen zum Erstellen einer Suchabfrage sowie zur Verwendung von Bedingungen finden Sie unter [Keyword queries for Content Search](keyword-queries-and-search-conditions.md).
    
13. Klicken Sie auf **Suche**, um die Sucheinstellungen zu speichern und die Suche zu starten. 
    
    Die Suche wird gestartet. Nach einer Weile wird im Detailbereich eine Schätzung der Suchergebnisse angezeigt. Die Schätzung enthält die Gesamtgröße und die Anzahl der Elemente, die den Suchkriterien entsprechen. Die Such Schätzung enthält auch die Anzahl der nicht indizierten Elemente in den durchsuchten Inhaltsspeicherorten. Die Anzahl nicht indizierter Elemente, die den Suchkriterien nicht entsprechen, werden in die Suchstatistiken einbezogen, die im Detailbereich angezeigt werden. Wenn ein nicht indiziertes Element mit der Suchabfrage übereinstimmt (da andere Nachrichten-oder Dokumenteigenschaften die Suchkriterien erfüllen), wird es nicht in die geschätzte Anzahl nicht indexierter Elemente aufgenommen. Wenn ein nicht indiziertes Element durch die Suchkriterien ausgeschlossen wird, wird es auch nicht in die Schätzung nicht indexierter Elemente einbezogen.
    
    Wenn die Suche abgeschlossen ist, können Sie eine Vorschau der Suchergebnisse anzeigen. Klicken Sie bei Bedarf ****![auf Aktualisierungssymbol](media/O365-MDM-Policy-RefreshIcon.gif) aktualisieren, um die Informationen im Detailbereich zu aktualisieren. 
  
## <a name="step-6-export-the-results-of-a-content-search-associated-with-a-case"></a>Schritt 6: Exportieren der Ergebnisse einer Inhaltssuche, die einer Anfrage zugeordnet ist
<a name="step5_1"> </a>

Nachdem eine Suche erfolgreich ausgeführt wurde, können Sie die Suchergebnisse exportieren. Wenn Sie Suchergebnisse exportieren, werden Postfachelemente in PST-Dateien oder als einzelne Nachrichten heruntergeladen. Wenn Sie Inhalte aus SharePoint und OneDrive für Unternehmen Websites exportieren, werden Kopien von systemeigenen Office-Dokumenten und anderen Dokumenten exportiert. Eine Manifestdatei (im XML-Format), die Informationen zu jedem Suchergebnis enthält, wird ebenfalls exportiert.
  
Sie können die Ergebnisse eines Exports exportieren [die Ergebnisse einer einzelnen Suche, die einem Fall zugeordnet](manage-ediscovery-cases.md#singlesearch_1) ist, oder Sie können die Ergebnisse des [Exports mit den Ergebnissen mehrerer Suchvorgänge exportieren, die einem Fall zugeordnet sind](manage-ediscovery-cases.md#multiplesearches_1).
  
### <a name="export-the-results-of-a-single-search-associated-with-a-case"></a>Exportieren der Ergebnisse einer einzelnen Suche, die einem Fall zugeordnet ist
<a name="singlesearch_1"> </a>

1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, aus dem Sie die Suche exportieren möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf **Suchen**.
    
4. Klicken Sie in der Liste der Suchvorgänge für den Fall auf die Suche, aus der Sie Suchergebnisse exportieren möchten ****![, klicken Sie auf Export](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)Suchergebnisse exportieren, und klicken Sie dann auf **Ergebnisse exportieren**.
    
    Die Seite **Suchergebnisse exportieren** wird angezeigt. Der Workflow zum Exportieren der Ergebnisse aus einer Inhaltssuche, die einem Fall zugeordnet ist, entspricht dem Exportieren der Suchergebnisse für eine Suche auf der Seite **Inhaltssuche** . Eine Schritt-für-Schritt-Anleitung finden Sie unter [Exportieren von Suchergebnissen aus dem Security #a0 Compliance Center](export-search-results.md).
    
    > [!NOTE]
    > Wenn Sie Suchergebnisse exportieren, haben Sie die Möglichkeit, die Deduplizierung zu aktivieren, sodass nur eine Kopie einer e-Mail-Nachricht exportiert wird, obwohl in den durchsuchten Postfächern möglicherweise mehrere Instanzen derselben Nachricht gefunden wurden. Weitere Informationen zur Deduplizierung und zur Identifizierung von doppelten Elementen finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen](de-duplication-in-ediscovery-search-results.md). 
  
5. Nachdem Sie den Export gestartet haben, klicken Sie auf **exportieren** , um die Liste der Exportaufträge anzuzeigen, die für diesen Fall vorhanden sind. 
    
    ![Klicken Sie auf exportieren, um eine Liste der Exportaufträge anzuzeigen.](media/b7b95bf7-134e-471e-961e-f86c1bb633eb.png)
  
    Möglicherweise müssen Sie **auf Aktualisierungs**![Symbol](media/O365-MDM-Policy-RefreshIcon.gif) aktualisieren klicken, um die Liste der Exportaufträge zu aktualisieren, um den soeben erstellten Exportauftrag anzuzeigen. Beachten Sie, dass Exportaufträge den gleichen Namen wie die entsprechende Inhaltssuche haben, wobei **_Export** an das Ende des Such namens angehängt wird. 
    
6. Klicken Sie auf den soeben erstellten Exportauftrag, um Statusinformationen im Detailbereich anzuzeigen. Diese Informationen umfassen den Prozentsatz der Elemente, die in einen Azure-Speicherbereich in der Microsoft-Cloud übertragen wurden.
    
    Nachdem alle Elemente übertragen wurden, klicken Sie auf **exportierte Ergebnisse herunterladen** , um die Suchergebnisse auf den lokalen Computer herunterzuladen. Weitere Informationen finden Sie unter Schritt 2 in [Exportieren von Suchergebnissen aus dem Security #a0 Compliance Center](export-search-results.md) .
    
### <a name="export-the-results-of-multiple-searches-associated-with-a-case"></a>Exportieren der Ergebnisse mehrerer Suchvorgänge, die einem Fall zugeordnet sind
<a name="multiplesearches_1"> </a>

Als Alternative zum Exportieren der Ergebnisse einer einzelnen Inhaltssuche, die einem Fall zugeordnet ist, können Sie die Ergebnisse mehrerer Suchvorgänge aus demselben Fall in einem einzelnen Export exportieren. Das Exportieren der Ergebnisse von mehreren Suchvorgängen ist schneller und einfacher als das Exportieren der Ergebnisse um die Suche nach dem anderen.
  
> [!NOTE]
> Sie können die Ergebnisse mehrerer suchen nicht exportieren, wenn eine dieser Suchvorgänge so konfiguriert wurde, dass alle Fall Inhalte durchsucht werden. Exportieren Sie nur die Ergebnisse mehrerer Suchvorgänge nach Suchvorgängen, die einem eDiscovery-Fall zugeordnet sind. Sie können die Ergebnisse mehrerer Suchvorgänge, die auf der Seite **Inhaltssuche** im Security #a0 Compliance Center aufgeführt sind, nicht exportieren. 
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, aus dem Sie die Suche exportieren möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf **Suchen**.
    
4. Wählen Sie in der Liste der Suchvorgänge mindestens zwei Suchvorgänge aus, aus denen Sie Suchergebnisse exportieren möchten.
    
    > [!NOTE]
    > Wenn Sie mehrere Suchvorgänge auswählen möchten, drücken Sie **STRG** , während Sie auf jede Suche klicken. Sie können auch mehrere benachbarte Suchvorgänge auswählen, indem Sie auf die erste Suche klicken, die **UMSCHALT** Taste gedrückt halten und dann auf die letzte Suche klicken. 
  
5. Nachdem Sie die Suchvorgänge ausgewählt haben ****![, klicken Sie auf Export](media/47205c65-babd-4b3a-bd7b-98dfd92883ba.png)Suchergebnisse exportieren, und klicken Sie dann auf **Ergebnisse exportieren**.
    
6. Die Seite * * Exportieren der Suchergebnisse für *n* suchen * * wird angezeigt, wobei *n* die Anzahl der Suchvorgänge ist, für die Sie Ergebnisse exportieren. Beachten Sie, dass Sie dem Exportauftrag einen Namen geben müssen. 
    
    Der Workflow zum Exportieren der Ergebnisse aus mehreren Inhalts suchen, die einem Fall zugeordnet sind, ist identisch mit dem Exportieren der Suchergebnisse für eine einzelne Suche. Eine Schritt-für-Schritt-Anleitung finden Sie unter [Exportieren von Suchergebnissen aus dem Security #a0 Compliance Center](export-search-results.md).
    
    > [!NOTE]
    > Wenn Sie Suchergebnisse aus mehreren Suchvorgängen exportieren, die einem Fall zugeordnet sind, können Sie auch die Deduplizierung aktivieren, sodass nur eine Kopie einer e-Mail-Nachricht exportiert wird, obwohl möglicherweise mehrere Instanzen derselben Nachricht im Postfächer, die in einer oder mehreren Suchvorgängen durchsucht wurden. Weitere Informationen zur Deduplizierung und zur Identifizierung von doppelten Elementen finden Sie unter [Deduplizierung in eDiscovery-Suchergebnissen](de-duplication-in-ediscovery-search-results.md). 
  
7. Nachdem Sie den Export gestartet haben, klicken Sie auf **exportieren** , um die Liste der Exportaufträge anzuzeigen, die für diesen Fall angezeigt werden. 
    
    ![Klicken Sie auf exportieren, um eine Liste der Exportaufträge anzuzeigen.](media/b7b95bf7-134e-471e-961e-f86c1bb633eb.png)
  
    Möglicherweise müssen Sie **auf Aktualisierungs**![Symbol](media/O365-MDM-Policy-RefreshIcon.gif) aktualisieren klicken, um die Liste der Exportaufträge zu aktualisieren, um den soeben erstellten Exportauftrag anzuzeigen. Beachten Sie, dass die Suchvorgänge, die in den Exportauftrag aufgenommen wurden, in der Spalte **Suchen** aufgeführt werden. 
    
8. Klicken Sie auf den soeben erstellten Exportauftrag, um Statusinformationen im Detailbereich anzuzeigen. Diese Informationen umfassen den Prozentsatz der Elemente, die in einen Azure-Speicherbereich in der Microsoft-Cloud übertragen wurden.
    
9. Nachdem alle Elemente übertragen wurden, klicken Sie auf **exportierte Ergebnisse herunterladen** , um die Suchergebnisse auf den lokalen Computer herunterzuladen. Weitere Informationen finden Sie unter Schritt 2 in [Exportieren von Suchergebnissen aus dem Security #a0 Compliance Center](export-search-results.md) .
    
#### <a name="more-information-about-exporting-the-results-of-multiple-searches"></a>Weitere Informationen zum Exportieren der Ergebnisse mehrerer Suchvorgänge

- Wenn Sie die Ergebnisse mehrerer Suchvorgänge exportieren, werden die Suchabfragen von allen suchen mit **oder** -Operatoren kombiniert, und dann wird die kombinierte Suche gestartet. Die geschätzten Ergebnisse der kombinierten Suche werden im Detailbereich des ausgewählten Exportauftrags angezeigt. Die Suchergebnisse werden dann in den Azure-Speicherbereich in der Microsoft-Cloud übertragen. Der Status der Übertragung wird auch im Detailbereich angezeigt. Wie bereits erwähnt, können Sie Sie nach dem Übertragen aller Suchergebnisse auf Ihren lokalen Computer herunterladen. 
    
- Die maximale Anzahl von Stichwörtern aus den Suchabfragen für alle Suchvorgänge, die Sie exportieren möchten, lautet 500. (Dies ist der gleiche Grenzwert für eine einzelne Inhaltssuche). Das liegt daran, dass der Exportauftrag alle Suchabfragen mit dem **or** -Operator kombiniert. Wenn Sie diesen Grenzwert überschreiten, wird ein Fehler zurückgegeben. In diesem Fall müssen Sie die Ergebnisse aus weniger Suchvorgängen exportieren oder die Suchabfragen der zu exportierenden suchen vereinfachen. 
    
- Die exportierten Suchergebnisse werden nach der Inhaltsquelle organisiert, in der das Element gefunden wurde. Das bedeutet, dass für eine Inhaltsquelle in den Export Ergebnissen möglicherweise Elemente von unterschiedlichen Suchvorgängen zurückgegeben werden. Wenn Sie beispielsweise e-Mail-Nachrichten in einer PST-Datei für jedes Postfach exportieren möchten, hat die PST-Datei möglicherweise Ergebnisse aus mehreren Suchvorgängen.
    
- Wenn dasselbe e-Mail-Element oder Dokument vom gleichen Inhaltsspeicherort von mehr als einer der Suchvorgänge zurückgegeben wird, die Sie exportieren, wird nur eine Kopie des Elements exportiert.
    
- Sie können einen Export für mehrere Suchvorgänge nach dem Erstellen nicht bearbeiten. Beispielsweise können Sie dem Export keine Suchvorgänge hinzufügen oder daraus entfernen. Sie müssen einen neuen Exportauftrag erstellen, um die exportierten Suchergebnisse zu ändern. Nachdem ein Exportauftrag erstellt wurde, können Sie die Ergebnisse nur auf einen Computer herunterladen, den Export neu starten oder den Exportauftrag löschen.
    
- Wenn Sie den Export neu starten, wirken sich Änderungen an den Abfragen der Suchvorgänge, aus denen der Exportauftrag besteht, nicht auf die Suchergebnisse aus, die abgerufen werden. Wenn Sie einen Export neu starten, wird derselbe kombinierte Suchabfrage Auftrag, der beim Erstellen des Exportauftrags ausgeführt wurde, erneut ausgeführt.
    
- Wenn Sie einen Export von der Seite **Exports** in einem eDiscovery-Fall neu starten, überschreiben die Suchergebnisse, die an den Azure-Speicherbereich übertragen werden, die vorherigen Ergebnisse; die vorherigen Ergebnisse, die dort übertragen wurden, stehen nicht zum Herunterladen zur Verfügung. 
    
- Das Vorbereiten der Ergebnisse mehrerer Suchvorgänge für die Analyse in Advanced eDiscovery ist nicht verfügbar. Sie können nur die Ergebnisse einer einzelnen Suche für die Analyse in Advanced eDiscovery vorbereiten.
  
## <a name="step-7-prepare-search-results-for-advanced-ediscovery"></a>Schritt 7: Vorbereiten der Suchergebnisse für Advanced eDiscovery
<a name="step7_1"> </a>

Wenn Ihre Organisation über ein Office 365 E5-Abonnement verfügt, können Sie die Ergebnisse von Inhalts suchen vorbereiten, die einem Fall für die Analyse in Advanced eDiscovery zugeordnet sind. Nachdem Sie Suchergebnisse vorbereitet haben, können Sie zu Advanced eDiscovery wechseln (siehe [Schritt 8: Wechseln Sie zu der Anfrage in Advanced eDiscovery](manage-ediscovery-cases.md#gotoAeD_1)) und verarbeiten die Suchergebnis Daten zur weiteren Analyse in Advanced eDiscovery.
  
Wenn Sie Suchergebnisse für Advanced eDiscovery vorbereiten, extrahiert die OCR-Funktion (Optical Character Recognition) automatisch Text aus Bildern. OCR wird für lose Dateien, e-Mail-Anlagen und eingebettete Bilder unterstützt. Auf diese Weise können Sie die Textanalyse Funktionen von Advanced eDiscovery (Near-Duplicates, e-Mail-Threading, Themes und Predictive Coding) auf Text in Bilddateien anwenden.
  
> [!NOTE]
> Um die Daten eines Benutzers mithilfe von Advanced eDiscovery zu analysieren, muss dem Benutzer (dem Verwalter der Daten) eine Office 365 E5-Lizenz zugewiesen werden. Alternativ können Benutzern mit einer Office 365 E1-oder E3-Lizenz eine erweiterte eDiscovery-eigenständige Lizenz zugewiesen werden. Administratoren und Compliance Officer, die Fällen zugeordnet sind, und Verwenden von Advanced eDiscovery zum Analysieren von Daten benötigen keine E5-Lizenz. 
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, für den Sie Suchergebnisse für die Analyse in Advanced eDiscovery vorbereiten möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf **Suche**, und wählen Sie dann die Suche aus.
    
4. Klicken Sie im Detailbereich unter **Ergebnisse mit erweiterter eDiscovery analysieren**auf **Ergebnisse zur Analyse vorbereiten**.
    
5. Gehen Sie auf der Seite **Ergebnisse für Analyse vorbereiten** folgendermaßen vor:  
    
  - Wählen Sie aus, ob indizierte Elemente, indexierte und nicht indizierte Elemente oder nur nicht indizierte Elemente zur Analyse in Advanced eDiscovery vorbereitet werden sollen.
    
  - Legen Sie fest, ob alle Versionen von Dokumenten in SharePoint einbezogen werden sollen, die die Suchkriterien erfüllen. Diese Option wird nur dann angezeigt, wenn die Inhaltsquellen für die Suche Websites umfassen.
    
  - Geben Sie an, ob eine Benachrichtigung an eine Person gesendet (oder kopiert) werden soll, wenn der Vorbereitungsprozess abgeschlossen ist und die Daten für die Verarbeitung in Advanced eDiscovery bereit sind.
    
6. Klicken Sie auf **Vorbereiten**.
    
    Die Suchergebnisse werden mit Advanced eDiscovery für die Analyse vorbereitet.
    
7. Klicken Sie im Detailbereich auf **Vorbereitungsstatus überprüfen** , um Informationen zum Vorbereitungsprozess anzuzeigen. Wenn der Vorbereitungsprozess abgeschlossen ist, können Sie den Fall in Advanced eDiscovery aufrufen, um die Daten für die Analyse zu verarbeiten. 
  
## <a name="step-8-go-to-the-case-in-advanced-ediscovery"></a>Schritt 8: Wechseln zu der Groß-/Kleinschreibung in Advanced eDiscovery
<a name="gotoAeD_1"> </a>

Nachdem Sie einen Fall im Security #a0 Compliance Center erstellt haben, können Sie in der erweiterten eDiscovery auf denselben Fall wechseln.
  
So navigieren Sie zu einem Fall in Advanced eDiscovery:
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie neben dem Fall, zu dem Sie in Advanced eDiscovery wechseln möchten, auf **Öffnen** . 
    
3. Klicken Sie auf der **Start** Seite für den Fall auf **zu Advanced eDiscovery wechseln**.
    
    ![Klicken Sie auf zu Erweiterte eDiscovery wechseln, um die Anfrage in Advanced eDiscovery zu öffnen.](media/8e34ba23-62e3-4e68-a530-b6ece39b54be.png)
  
    Die **Verbindung mit der erweiterten eDiscovery** -Statusleiste wird angezeigt. Wenn Sie mit Advanced eDiscovery verbunden sind, wird auf der Seite eine Liste mit Containern angezeigt. 
    
    ![Der Fall wird in Advanced eDiscovery angezeigt.](media/8036e152-70dc-4bb7-9379-61c1ed8326b4.png)
  
    Diese Container stellen die Suchergebnisse dar, die Sie in Schritt 7 zur Analyse in Advanced eDiscovery vorbereitet haben. Beachten Sie, dass der Name des Containers den gleichen Namen wie die Inhaltssuche in dem Fall im Security #a0 Compliance Center hat. Die Container in der Liste sind diejenigen, die Sie vorbereitet haben. Wenn ein anderer Benutzer Suchergebnisse für Advanced eDiscovery vorbereitet hat, werden die entsprechenden Container nicht in die Liste aufgenommen.
    
4. Wenn Sie die Suchergebnis Daten aus einem Container in den Fall in Advanced eDiscovery laden möchten, wählen Sie einen Container aus, und klicken Sie auf **verarbeiten**.
    
    Informationen zum Verarbeiten von Containern finden Sie unter [Ausführen des Prozess Moduls und Laden von Daten in Office 365 Advanced eDiscovery](run-the-process-module-and-load-data-in-advanced-ediscovery.md).
    
> [!TIP]
> Klicken Sie auf **zu eDiscovery wechseln** , um zum gleichen Fall im Security #a0 Compliance Center zurückzukehren. 
  
## <a name="optional-step-9-close-a-case"></a>Optional Schritt 9: Schließen eines Falls
<a name="closecase_1"> </a>

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
    
4. Klicken Sie auf der Seite **Details** auf **Fall schließen**.
    
    Es wird eine Warnung angezeigt, die besagt, dass die dem Fall zugeordneten Haltestatus deaktiviert werden.
    
5. Klicken Sie auf **Ja** , um den Fall zu schließen. 
    
    Der Status auf der Flyout-Seite " **diesen Fall verwalten** " wird von " **aktiv** " in " **Schließen**" geändert.
    
6. Schließen Sie **diesen Fall verwalten**.
    
7. Klicken Sie **** ![auf der Seite eDiscovery auf Symbol](media/O365-MDM-Policy-RefreshIcon.gif) **Aktualisierung** aktualisieren, um den Status des geschlossenen Falls zu aktualisieren. Es kann bis zu 60 Minuten dauern, bis der Abschlussprozess abgeschlossen ist. 
    
    Wenn der Prozess abgeschlossen ist, wird der Status der Anfrage in **Close** auf der **eDiscovery** -Seite geändert. Klicken Sie erneut auf den Namen der Anfrage, um die Flyout-Seite " **diesen Fall verwalten** " anzuzeigen, die Informationen dazu enthält, wann der Fall geschlossen wurde und wer ihn geschlossen hat. 
  
## <a name="optional-step-10-re-open-a-closed-case"></a>Optional Schritt 10: Erneutes Öffnen eines geschlossenen Falls
<a name="reopencase_1"> </a>

Wenn Sie einen Fall erneut öffnen, werden alle Haltestatus, die beim Schließen des Cases vorhanden waren, nicht automatisch wiederhergestellt. Nachdem der Fall erneut geöffnet wurde, müssen Sie zur halte Seite wechseln und die vorherigen **halte** Status aktivieren. Wenn Sie einen Haltestatus aktivieren möchten, wählen Sie ihn aus, und klicken Sie im Detailbereich auf **Einschalten** . 
  
1. Klicken Sie im Security #a0 Compliance Center auf **eDiscovery** \> **eDiscovery** , um die Liste der Fälle in Ihrer Organisation anzuzeigen. 
    
2. Klicken Sie auf den Namen der Anfrage, die Sie erneut öffnen möchten.
    
    Die Dropdown Seite **diesen Fall verwalten** wird angezeigt. 
    
3. Klicken Sie unter **Fall Status verwalten**auf **erneuter Fall öffnen**.
    
    Es wird eine Warnung angezeigt, die besagt, dass die Haltestatus, die dem Fall zugeordnet waren, wenn Sie geschlossen wurde, nicht automatisch aktiviert werden.
    
4. Klicken Sie auf **Ja** , um die Anfrage erneut zu öffnen. 
    
    Der Status auf der Flyout-Seite " **diesen Fall verwalten** " wird von " **geschlossen** " in " **aktiv**" geändert.
    
5. Schließen Sie **diesen Fall verwalten**.
    
6. Klicken Sie **** ![auf der Seite eDiscovery auf Symbol](media/O365-MDM-Policy-RefreshIcon.gif) **Aktualisierung** aktualisieren, um den Status des erneut geöffneten Falls zu aktualisieren. Es kann bis zu 60 Minuten dauern, bis der Vorgang zum erneuten Öffnen abgeschlossen ist. 
    
    Wenn der Prozess abgeschlossen ist, wird der Status des Falles in **Active** auf der **eDiscovery** -Seite geändert. 
  
## <a name="more-information"></a>Weitere Informationen
<a name="moreinfo_1"> </a>

- **Gibt es Einschränkungen für eDiscovery-Fälle oder haltebereiche, die einem eDiscovery-Fall zugeordnet sind?** In der folgenden Tabelle sind die Grenzwerte für eDiscovery-Fälle und Case-Holds aufgeführt.
    
|**Beschreibung der Beschränkung**|**Grenzwert**|
|:-----|:-----|
|Maximale Anzahl von Fällen für eine Organisation  <br/> |Keine Begrenzung  <br/> |
|Maximale Anzahl von Fall Behältern für eine Organisation  <br/> |10,000  <br/> |
|Maximale Anzahl von Postfächern in einem einzigen Aufbewahrungs Fall  <br/> |1,000  <br/> |
|Maximale Anzahl von SharePoint-und OneDrive für Unternehmen-Websites in einem einzigen Aufbewahrungs Fall  <br/> |100  <br/> |
   
- **Was geschieht mit Fällen, die auf der Seite Fallverwaltung in Advanced eDiscovery erstellt wurden?** Sie können auf eine Liste älterer erweiterter eDiscovery-Fälle zugreifen, indem Sie auf der Seite **eDiscovery** im Security #a0 Compliance Center auf den Link unten klicken. Um jedoch in einem älteren Fall arbeiten zu können, müssen Sie sich an Office 365 Support wenden und die Anfrage dazu stellen, dass der Fall in einen neuen eDiscovery-Fall im Security #a0 Compliance Center verschoben wird. 
    
- **Gründe für die Erstellung eines eDiscovery-Administrators** Wie bereits erläutert, ist ein eDiscovery-Administrator Mitglied der Rollengruppe "eDiscovery-Manager", die alle eDiscovery-Fälle in Ihrer Organisation anzeigen und auf diese zugreifen kann. Dieser Zugriff auf alle eDiscovery-Fälle dient zwei wichtigen Zwecken:
    
  - Wenn eine Person, die das einzige Mitglied eines eDiscovery-Falls ist, die Organisation verlässt, kann niemand (einschließlich Mitglieder der Rollengruppe „Organisationsverwaltung“ oder andere Mitglieder der Rollengruppe „eDiscovery-Manager“) auf diesen eDiscovery-Fall zugreifen, da diese Personen keine Fallmitglieder sind. In diesem Fall gäbe es keine Möglichkeit, auf die Daten in dem Fall zuzugreifen. Da ein eDiscovery-Administrator jedoch auf alle eDiscovery-Fälle in der Organisation zugreifen kann, kann er den Fall im Security #a0 Compliance Center anzeigen und sich selbst oder einen anderen eDiscovery-Manager als Mitglied des Falles hinzufügen.
    
  - Da ein eDiscovery-Administrator alle eDiscovery-Fälle anzeigen und darauf zugreifen kann, kann er alle Fälle und zugehörige Inhalts suchen überwachen und überwachen. So kann der Missbrauch von Inhaltssuchen oder anderen eDiscovery-Fällen verhindert werden. Und da eDiscovery-Administratoren in den Ergebnissen einer Inhaltssuche potenziell vertrauliche Informationen abrufen können, sollten Sie die Anzahl von Benutzern, die eDiscovery-Administratoren sind, einschränken.
    
    Schließlich werden eDiscovery-Administratoren im Security #a0 Compliance Center automatisch als Administratoren in Advanced eDiscovery hinzugefügt, wie zuvor erläutert. Das bedeutet, dass eine Person, die ein eDiscovery-Administrator ist, administrative Aufgaben in Advanced eDiscovery ausführen kann, beispielsweise das Einrichten von Benutzern, das Erstellen von Fällen und das Hinzufügen von Daten zu Fällen.
    
- **Was sind die Lizenzierungsanforderungen zum Speichern von Inhaltsspeicherorten?** Im Allgemeinen benötigen Organisationen ein Office 365 E3-Abonnement oder höher, um inhaltsspeicherorte in der Warteschleife zu platzieren. Für die Aufbewahrung von Postfächern ist eine Exchange Online Plan 2-Lizenz erforderlich. Weitere Informationen finden Sie in dieser [FAQ](https://support.office.com/article/9d1a29ae-b7b4-4a27-9c8c-84289023dcae.aspx#Q5).

- **Was sollten Sie sonst wissen, wenn Sie alle Fall Inhalte in Schritt 5 durchsuchen?** Wie bereits erläutert, können Sie die inhaltsspeicherorte durchsuchen, die in der Anfrage gespeichert wurden. Wenn Sie dies tun, wird nur der Inhalt gesucht, der mit den Aufbewahrungs Kriterien übereinstimmt. Wenn keine Aufbewahrungs Kriterien vorhanden sind, werden alle Inhalte durchsucht. Wenn sich der Inhalt auf einem abfragebasierten Haltebereich befindet, werden nur die Inhalte, die sowohl die Aufbewahrungs Kriterien (aus dem in Schritt 4 festgelegten Speicherplatz) als auch die Suchkriterien (aus der Suche in Schritt 5) entsprechen, mit den Suchergebnissen zurückgegeben.
    
    Im folgenden finden Sie einige andere Punkte, die Sie beim Durchsuchen aller Case-Inhalte beachten sollten:
    
  - Wenn ein Inhaltsspeicherort Teil mehrerer haltebereiche im gleichen Fall ist, werden die Aufbewahrungs Abfragen durch einen **oder** -Operator kombiniert, wenn Sie diesen Inhaltsspeicherort mithilfe der Option "alle Groß-/Kleinschreibung" Durchsuchen. Wenn ein Inhaltsspeicherort Teil von zwei unterschiedlichen Haltebereichen ist, wobei einer auf Abfrage basiert ist und der andere ein unbegrenzter Speicher ist (wobei der gesamte Inhalt in den Haltebereich gesetzt wird), wird der gesamte Inhalt aufgrund des unbegrenzten Haltestatus durchsucht. 
    
  - Wenn eine Inhaltssuche für einen Fall gilt und Sie Sie so konfiguriert haben, dass alle Fall Inhalte durchsucht werden und Sie dann einen Haltestatus ändern (durch Hinzufügen oder Entfernen eines Inhaltsspeicherorts oder Ändern der halte Abfrage), wird die Suchkonfiguration mit diesen Änderungen aktualisiert. Sie müssen die Suche jedoch erneut ausführen, nachdem der Haltebereich geändert wurde, um die Suchergebnisse zu aktualisieren.
    
  - Wenn mehrere Case-Aufbewahrungsorte an einer Inhaltsposition in einem eDiscovery-Fall gespeichert werden und Sie alle Fall Inhalte durchsuchen möchten, beträgt die maximale Anzahl von Stichwörtern für diese Suchabfrage 500. Das liegt daran, dass die Inhaltssuche alle abfragebasierten Haltestatus mit dem Operator **or** kombiniert. Wenn in den kombinierten Aufbewahrungs Abfragen und der Inhalts Suchabfrage mehr als 500 Schlüsselwörter vorhanden sind, wird der gesamte Inhalt im Postfach durchsucht, und nicht nur der Inhalt, der mit dem abfragebasierten Case-Wert übereinstimmt. 
    
  - Wenn ein Case Hold den Status " **Einschalten**" aufweist, können Sie die Speicherorte der Fall Inhalte weiterhin durchsuchen, während der Haltebereich aktiviert ist.
    
  - Wenn eine Suche so konfiguriert ist, dass alle Fall Inhalte durchsucht werden, können Sie, wie bereits erwähnt, diese Suche nicht einschließen, wenn Sie die Ergebnisse mehrerer Suchvorgänge exportieren möchten. Wenn eine Suche so konfiguriert ist, dass alle Fall Inhalte durchsucht werden, müssen Sie die Ergebnisse dieser einzelnen Suche exportieren.
    
- **Was ist mit dem Platzieren eines Haltestatus für Office 365 Gruppen und Microsoft Teams?** Microsoft Teams sind auf Office 365 Gruppen aufgebaut. Daher ist es sehr ähnlich, dass Sie in einem eDiscovery-Fall aufbewahrt werden. Beachten Sie beim Platzieren von Office 365 Gruppen und Microsoft Teams die folgenden Aspekte. 
    
  - Zum Platzieren von Inhalten in Office 365 Gruppen und in Microsoft Teams müssen Sie das Postfach und die SharePoint-Website angeben, die einer Gruppe oder einem Team zugeordnet sind.
    
  - Führen Sie das Cmdlet **Get-Unifiedgroup** in Exchange Online aus, um Eigenschaften für eine Office 365 Gruppe oder ein Microsoft-Team anzuzeigen. Dies ist eine gute Möglichkeit, die URL für die Website abzurufen, die einer Office 365 Gruppe oder einem Microsoft-Team zugeordnet ist. Mit dem folgenden Befehl werden beispielsweise ausgewählte Eigenschaften für eine Office 365 Gruppe mit dem Namen "Senior Leadership Team" angezeigt: 
    
  ```
  Get-UnifiedGroup "Senior Leadership Team" | FL DisplayName,Alias,PrimarySmtpAddress,SharePointSiteUrl
  DisplayName            : Senior Leadership Team
  Alias                  : seniorleadershipteam
  PrimarySmtpAddress     : seniorleadershipteam@contoso.onmicrosoft.com
  SharePointSiteUrl      : https://contoso.sharepoint.com/sites/seniorleadershipteam
  
  ```

    > [!NOTE]
    > Damit Sie das Cmdlet **Get-Unifiedgroup** ausführen können, müssen Sie in Exchange Online die Rolle "nur-Ansicht-Empfänger" besitzen oder Mitglied einer Rollengruppe sein, der die Rolle "nur-Empfänger" zugewiesen ist. 
  
  - Wenn das Postfach eines Benutzers durchsucht wird, werden alle Office 365 Gruppen oder Microsoft Teams, bei denen der Benutzer Mitglied ist, nicht durchsucht. Wenn Sie eine Office 365 Gruppe oder ein Microsoft-Team halten, wird auf ähnliche Weise nur das Gruppenpostfach und die Gruppen Website in den Wartebereich verschoben. die Postfächer und OneDrive für Unternehmen Websites von Gruppenmitgliedern werden nicht in den Haltestatus versetzt, es sei denn, Sie fügen Sie explizit in den Haltebereich ein. Wenn Sie daher eine Office 365 Gruppe oder ein Microsoft-Team aus rechtlichen Gründen in die Warteschleife stellen müssen, sollten Sie die Postfächer und OneDrive für Unternehmen Websites für Gruppen-und Teammitglieder in demselben Archiv hinzufügen.
    
  - Wenn Sie eine Liste der Mitglieder einer Office 365 Gruppe oder eines Microsoft-Teams erhalten möchten, können Sie die Eigenschaften auf der Seite " **Start \> Gruppen** " im Microsoft 365 Admin Center anzeigen. Alternativ können Sie den folgenden Befehl in Exchange Online PowerShell ausführen: 
    
  ```
  Get-UnifiedGroupLinks <group or team name> -LinkType Members | FL DisplayName,PrimarySmtpAddress 
  ```

    > [!NOTE]
    > Damit Sie das Cmdlet **Get-UnifiedGroupLinks** ausführen können, müssen Sie in Exchange Online die Rolle "nur-Ansicht-Empfänger" besitzen oder Mitglied einer Rollengruppe sein, der die Rolle "nur-Ansicht-Empfänger" zugewiesen ist. 
  
  - Unterhaltungen, die Teil eines Microsoft Teams-Kanals sind, werden in dem Postfach gespeichert, das dem Microsoft-Team zugeordnet ist. Auf ähnliche Weise werden Dateien, die Teammitglieder in einem Kanal freigeben, auf der SharePoint-Website des Teams gespeichert. Daher müssen Sie das Microsoft Team-Postfach und die SharePoint-Website speichern, um Unterhaltungen und Dateien in einem Kanal beizubehalten.
    
    Alternativ werden Unterhaltungen, die Teil der Chatliste in Microsoft Teams sind, im Postfach des Benutzers gespeichert, der am Chat teilnimmt. Und Dateien, die ein Benutzer in Chat Unterhaltungen freigibt, werden auf der OneDrive für Unternehmen Website des Benutzers gespeichert, der die Datei freigibt. Daher müssen Sie die einzelnen Benutzerpostfächer und OneDrive für Unternehmen Websites in der Warteschleife platzieren, um Unterhaltungen und Dateien in der Chat Liste beizubehalten. Daher empfiehlt es sich, die Postfächer von Mitgliedern eines Microsoft-Teams zusätzlich zur Aufbewahrung des Team Postfachs (und der Website) in einem Archiv zu platzieren.
    
    > [!IMPORTANT]
    > Benutzer, die an Unterhaltungen teilnehmen, die Teil der Chat Liste in Microsoft Teams sind, müssen über ein Exchange Online (Cloud-basiertes) Postfach verfügen, um Chat Unterhaltungen beizubehalten, wenn das Postfach in einen eDiscovery-Speicher gesetzt wird. Das liegt daran, dass Unterhaltungen, die Teil der Chat Liste sind, in den cloudbasierten Postfächern der Chat Teilnehmer gespeichert werden. Wenn ein Chat Teilnehmer kein Exchange Online Postfach hat, können Sie keine Chat Unterhaltungen beibehalten. Beispielsweise können Benutzer mit einem lokalen Postfach in einer Exchange-hybridbereitstellung an Unterhaltungen teilnehmen, die Teil der Chat Liste in Microsoft Teams sind. In diesem Fall können Inhalte aus diesen Unterhaltungen jedoch nicht beibehalten werden, da die Benutzer keine cloudbasierten Postfächer haben. 
  
  - Jeder Microsoft-Team-oder Team Kanal enthält ein wiki für die Notizen und die Zusammenarbeit. Der Inhalt des Wikis wird automatisch in einer Datei mit dem MHT-Format gespeichert. Diese Datei wird in der Microsoft Teams-wiki-Datendokument Bibliothek auf der SharePoint-Website des Teams gespeichert. Sie können die Inhalte im wiki in der Warteschleife platzieren, indem Sie die SharePoint-Website des Teams in der Warteschleife platzieren.
    
    > [!NOTE]
    > Die Funktion zum Beibehalten von wiki-Inhalten für einen Microsoft-Team-oder Team Kanal (wenn Sie die SharePoint-Website des Teams in der Warteschleife platzieren) wurde am 22. Juni 2017 veröffentlicht. Wenn eine Teamwebsite gespeichert ist, wird der Inhalt des Wikis ab diesem Datum beibehalten. Wenn jedoch eine Teamwebsite gespeichert ist und der Inhalt des Wikis vor dem 22. Juni 2017 gelöscht wurde, wurde der Inhalt des Wikis nicht beibehalten. 
  
- **Wie finde ich die URL für OneDrive für Unternehmen Websites?** Informationen zum Sammeln einer Liste der URLs für die OneDrive für Unternehmen Websites in Ihrer Organisation, damit Sie Sie zu einem Haltestatus oder einer Suche hinzufügen können, die einem eDiscovery-Fall zugeordnet ist, finden Sie unter [Erstellen einer Liste aller OneDrive-Standorte in Ihrer Organisation](https://support.office.com/article/8e200cb2-c768-49cb-88ec-53493e8ad80a). Dieses Skript in diesem Artikel erstellt eine Textdatei, die eine Liste aller OneDrive-Websites enthält. Um dieses Skript auszuführen, müssen Sie die SharePoint Online-Verwaltungsshell installieren und verwenden. Stellen Sie sicher, dass Sie die URL für die mysite-Domäne Ihrer Organisation an jede OneDrive-Website anfügen, die Sie durchsuchen möchten. Dies ist die Domäne, die alle OneDrive enthält. Beispiel: `https://contoso-my.sharepoint.com`. Hier ist ein Beispiel für eine URL für die OneDrive-Website eines Benutzers `https://contoso-my.sharepoint.com/personal/sarad_contoso_onmicrosoft.com`:.
