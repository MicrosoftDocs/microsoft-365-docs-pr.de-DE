---
title: Erste Schritte mit den wichtigsten eDiscovery-Fällen in Microsoft 365
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
description: In diesem Artikel wird beschrieben, wie Sie mit der Verwendung von Core eDiscovery in Microsoft 365 beginnen. Nachdem Sie eDiscovery-Berechtigungen zugewiesen und eine Anfrage erstellt haben, können Sie Mitglieder hinzufügen, eDiscovery-Haltestatus erstellen und dann nach Daten suchen und exportieren, die für Ihre Untersuchung relevant sind.
ms.openlocfilehash: 5faae81eb81ce8c69e3ae801d153c664ac152bda
ms.sourcegitcommit: 6ea9a910a8106a5f1aa589c55d166bfa67fd12a8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/18/2020
ms.locfileid: "44280545"
---
# <a name="get-started-with-core-ediscovery"></a>Erste Schritte mit Core eDiscovery

Core eDiscovery in Microsoft 365 bietet ein einfaches eDiscovery-Tool, mit dem Organisationen Inhalte in Microsoft 365 und Office 365 durchsuchen und exportieren können. Sie können auch die zentrale eDiscovery verwenden, um eine eDiscovery-Aufbewahrung an Inhaltsspeicherorten wie Exchange-Postfächern, SharePoint-Websites, OneDrive-Konten und Microsoft Teams zu platzieren. Für die Bereitstellung von Haupt-eDiscovery ist nichts erforderlich, aber es gibt einige erforderliche Aufgaben, die ein IT-Administrator und eDiscovery-Manager ausführen müssen, bevor Ihre Organisation mit der Verwendung von Core eDiscovery für die Suche, den Export und die Aufbewahrung von Inhalten beginnen kann.

In diesem Artikel werden die erforderlichen Schritte zum Einrichten von Core eDiscovery erläutert. Dies umfasst die Sicherstellung der erforderlichen Lizenzierung für den Zugriff auf die Haupt-eDiscovery und das Platzieren eines eDiscovery-Speichers an Inhalts Standorten sowie das Zuweisen von Berechtigungen für Ihr IT-, rechts-und Ermittlungsteam, damit Sie auf Fälle zugreifen und diese verwalten können. Dieser Artikel bietet außerdem eine allgemeine Übersicht über die Verwendung von Fällen zum Suchen und Exportieren von Inhalten.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Schritt 1: überprüfen und zuweisen geeigneter Lizenzen

Für die Lizenzierung für die zentrale eDiscovery ist das entsprechende Organisations Abonnement und die Lizenzierung pro Benutzer erforderlich.

- **Organisations Abonnement:** Um auf die Haupt-eDiscovery im Microsoft 365 Compliance Center oder im Office 365 Security & Compliance Center zuzugreifen und die Funktionen Hold und Export zu verwenden, muss Ihre Organisation über ein Microsoft 365 E3-oder Office 365 E3-Abonnement oder höher verfügen.

- **Lizenzierung pro Benutzer:** Um einen eDiscovery-Speicher für Postfächer und Websites zu halten, muss einem Benutzer je nach Ihrem Organisations Abonnement eine der folgenden Lizenzen zugewiesen sein:

  - Eine Microsoft 365 E3-oder Office 365 E3-Lizenz oder höher

   ODER

  - Office 365 E1-Lizenz mit einer Exchange Online Plan 2-oder Exchange Online-Add-on-Lizenz für die Archivierung

  UND

  - Office 365 E1-Lizenz mit einer Add-on-Lizenz für SharePoint Online Plan 2 oder OneDrive für Unternehmen Plan 2
  
  Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users).

Informationen zur Lizenzierung:

- Laden Sie die Lösung "Discover & respond" im Vergleich zur [Microsoft 365-Kompatibilitäts Lizenzierung](https://docs.microsoft.com/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)herunter.

- Weitere Informationen finden Sie unter [Security & Compliance Center Service Description](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="step-2-assign-ediscovery-permissions"></a>Schritt 2: Zuweisen von eDiscovery-Berechtigungen

Um auf die zentrale eDiscovery zuzugreifen oder als Mitglied eines zentralen eDiscovery-Falls hinzugefügt zu werden, muss einem Benutzer die entsprechenden Berechtigungen zugewiesen werden. Ein Benutzer muss insbesondere als Mitglied der Rollengruppe "eDiscovery-Manager" im Office 365 Security & Compliance Center hinzugefügt werden. Mitglieder dieser Rollengruppe können zentrale eDiscovery-Fälle erstellen und verwalten. Sie können Mitglieder hinzufügen und entfernen, Benutzer mit eDiscovery besetzen, Suchvorgänge erstellen und bearbeiten und Inhalte aus einem zentralen eDiscovery-Fall exportieren.

Führen Sie die folgenden Schritte aus, um Benutzer zur eDiscovery-Manager-Rollengruppe hinzuzufügen:

1. Wechseln Sie zu, [https://protection.office.com/permissions](https://protection.office.com/permissions) und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365-oder Office 365-Organisation an.

2. Wählen Sie auf der Seite **Berechtigungen** die Rollengruppe **eDiscovery-Manager** aus.

3. Klicken Sie auf der Seite eDiscovery-Manager-Flyout neben dem Abschnitt **eDiscovery-Manager** auf **Bearbeiten** .

4. Klicken Sie auf der Seite **eDiscovery-Manager auswählen** im Assistenten zum Bearbeiten der Rollengruppe auf **Ermittlungs-Manager auswählen**.

5. Klicken Sie auf **Hinzufügen** , und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Klicken Sie auf **Hinzufügen** , um die ausgewählten Benutzer hinzuzufügen, und klicken Sie dann auf **Fertig**.

7. Klicken Sie auf **Speichern** , um die Benutzer der Rollengruppe hinzuzufügen, und klicken Sie dann auf **Schließen** , um den Schritt abzuschließen.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Weitere Informationen zur eDiscovery-Manager-Rollengruppe

Es gibt zwei Untergruppen in der Rollengruppe "eDiscovery-Manager". Der Unterschied zwischen diesen Untergruppen basiert auf dem Bereich.

- **eDiscovery-Manager:** Kann die zentralen eDiscovery-Fälle anzeigen und verwalten, in denen Sie erstellt werden oder deren Mitglied Sie sind. Wenn ein anderer eDiscovery-Manager einen Fall erstellt, aber keinen zweiten eDiscovery-Manager als Mitglied dieses Falles hinzufügt, kann der zweite eDiscovery-Manager den Fall nicht auf der zentralen eDiscovery-Seite im Compliance Center anzeigen oder öffnen. Im Allgemeinen können die meisten Personen in Ihrer Organisation der Untergruppe eDiscovery-Manager hinzugefügt werden.

- **eDiscovery-Administrator:** Kann alle Fall Verwaltungsaufgaben ausführen, die ein eDiscovery-Manager ausführen kann. Darüber hinaus können eDiscovery-Administratoren folgende Aktionen durchführen:

  - Anzeigen aller Fälle, die auf der zentralen eDiscovery-Seite aufgeführt sind.
  
  - Verwalten Sie alle Fälle in der Organisation, nachdem Sie sich selbst als Mitglied der Anfrage hinzugefügt haben.

  - Zugriffs-und Export Fall Daten für alle Fälle in der Organisation.

  Aufgrund des breiten Zugriffs Umfangs sollte eine Organisation nur wenige Administratoren haben, die Mitglieder der Untergruppe "eDiscovery Administrators" sind.

Weitere Informationen zu eDiscovery-Berechtigungen und eine Beschreibung der einzelnen Rollen, die der Rollengruppe "eDiscovery-Manager" zugewiesen sind, finden Sie unter [Zuweisen von eDiscovery-Berechtigungen](assign-ediscovery-permissions.md).

## <a name="step-3-create-a-core-ediscovery-case"></a>Schritt 3: Erstellen eines zentralen eDiscovery-Falls

Der nächste Schritt besteht darin, einen Fall zu erstellen und mit der Verwendung von Core eDiscovery zu beginnen. Führen Sie die folgenden Schritte aus, um einen Fall zu erstellen und Mitglieder hinzuzufügen. Der Benutzer, der den Fall erstellt, wird automatisch als Mitglied hinzugefügt.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und melden Sie sich mit den Anmeldeinformationen für ein Benutzerkonto an, dem die entsprechenden eDiscovery-Berechtigungen zugewiesen wurden. Mitglieder der Rollengruppe "Organisationsverwaltung" können auch Haupt-eDiscovery-Fälle erstellen.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Center auf **Alle anzeigen**, und klicken Sie dann auf **eDiscovery > Kern**.

3. Klicken Sie auf der **zentralen eDiscovery** -Seite auf **Fall erstellen**.

4. Geben Sie auf der **neuen Fall** Flyout-Seite der Groß-/Kleinschreibung einen Namen (erforderlich), und geben Sie dann eine optionale Fallnummer und eine Beschreibung ein. Der Case-Name muss in Ihrer Organisation eindeutig sein.

5. Klicken Sie auf **Speichern** , um die Anfrage zu erstellen.

   Der neue Fall wird erstellt und auf der zentralen eDiscovery-Seite angezeigt. Möglicherweise müssen Sie auf **Aktualisieren** klicken, um den neuen Fall anzuzeigen. 

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>Schritt 4 (optional): Hinzufügen von Mitgliedern zu einem zentralen eDiscovery-Fall

Wenn Sie in Schritt 3 einen Fall erstellen und Sie der einzige Benutzer sind, der den Fall verwendet, müssen Sie diesen Schritt nicht ausführen. Sie können mit dem Fall beginnen, eDiscovery-Haltestatus zu erstellen, nach Inhalten zu suchen oder Suchergebnisse zu exportieren. Führen Sie diesen Schritt aus, wenn Sie anderen Benutzern (oder Rollengruppen) Zugriff auf die Anfrage gewähren möchten.

1. Klicken Sie auf der **zentralen eDiscovery** -Seite im Microsoft 365 Compliance Center auf den Namen des Falls, dem Sie Mitglieder hinzufügen möchten.

2. Klicken Sie auf der Seite **diesen Fall Flyout verwalten** unter **Mitglieder verwalten**auf **Hinzufügen** , um der Anfrage Mitglieder hinzuzufügen. 

    Sie können auch die Rolle "Rollengruppe" als Mitglieder einer Anfrage hinzufügen. Klicken Sie unter **Rollengruppen verwalten**auf **Hinzufügen**. Sie können die Rollengruppen, denen Sie angehören, nur einem Fall zuweisen. Das liegt daran, dass Rollengruppen steuern, wer einem eDiscovery-Fall Mitglieder zuweisen kann.

3. Klicken Sie in der Liste der Personen oder Rollengruppen, die als Mitglieder der Anfrage hinzugefügt werden können, auf das Kontrollkästchen neben den Namen der Personen (oder Rollengruppen), die Sie hinzufügen möchten. Wenn Sie eine große Liste von Personen haben, die als Mitglieder hinzugefügt werden können, verwenden Sie das **Suchfeld** , um nach einer bestimmten Person in der Liste zu suchen.
  
4. Nachdem Sie die Personen oder Rollengruppen ausgewählt haben, die als Mitglieder der Anfrage hinzugefügt werden sollen, klicken Sie auf **Hinzufügen**.

5. Klicken Sie auf **Speichern** , um die neue Liste der Fall Mitglieder zu speichern.

## <a name="explore-the-core-ediscovery-workflow"></a>Untersuchen des zentralen eDiscovery-Workflows

Um Ihnen den Einstieg in die Verwendung von Core eDiscovery zu erleichtern, finden Sie hier einen einfachen Workflow zum Erstellen von eDiscovery-Archiven für interessante Personen, zum Suchen nach Inhalten, die für Ihre Untersuchung relevant sind, und zum Exportieren dieser Daten zur weiteren Überprüfung. In jedem dieser Schritte werden auch einige erweiterte Haupt-eDiscovery-Funktionen hervorgehoben, die Sie untersuchen können.

![Zentraler eDiscovery-Workflow](../media/CoreEdiscoveryWorkflow.png)

1. **[Erstellen eines eDiscovery-Haltestatus](create-ediscovery-holds.md)**. Der erste Schritt nach dem Erstellen eines Falls ist das Platzieren eines Haltestatus (auch als *eDiscovery*-Archiv bezeichnet) an den Inhaltsspeicherorten der Personen, die für Ihre Untersuchung relevant sind. Zu den Inhaltsspeicherorten gehören Exchange-Postfächer, SharePoint-Websites, OneDrive-Konten sowie die Postfächer und Websites, die Microsoft Teams und Office 365 Gruppen zugeordnet sind. Während dieser Schritt optional ist, behält das Erstellen eines eDiscovery-Speichers Inhalte bei, die für den Fall während der Untersuchung relevant sein können. Wenn Sie einen eDiscovery-Haltebereich erstellen, können Sie den gesamten Inhalt an bestimmten Inhaltsspeicherorten beibehalten oder einen abfragebasierten Haltebereich erstellen, um nur die Inhalte beizubehalten, die mit einer halte Abfrage übereinstimmen. Neben dem Beibehalten von Inhalten besteht ein weiterer Grund zum Erstellen von eDiscovery-Archiven darin, die inhaltsspeicherorte schnell durchsuchen zu lassen (anstatt jeden zu durchsuchenden Standort auszuwählen), wenn Sie im nächsten Schritt suchen erstellen und ausführen. Nachdem Sie Ihre Untersuchung abgeschlossen haben, können Sie alle von Ihnen erstellten Haltestatus freigeben.

2. **[Suchen nach Inhalten](search-for-content-in-core-ediscovery.md)**. Nachdem Sie eDiscovery-Haltestatus erstellt haben, verwenden Sie das integrierte Such Tool, um die inhaltsspeicherorte zu durchsuchen. Sie können auch andere inhaltsspeicherorte nach Daten durchsuchen, die möglicherweise für den Fall relevant sind. Sie können verschiedene Suchvorgänge erstellen und ausführen, die mit der Anfrage verknüpft sind. Sie verwenden Schlüsselwörter, Eigenschaften und Bedingungen zum [Erstellen von Suchabfragen](keyword-queries-and-search-conditions.md) , die Suchergebnisse mit den Daten zurückgeben, die für den Fall wahrscheinlich relevant sind. Des Weiteren können Sie Folgendes:

   - Anzeigen von Suchstatistiken, die Ihnen beim Verfeinern einer Suchabfrage helfen können, um die Ergebnisse einzugrenzen.

   - Zeigen Sie eine Vorschau der Suchergebnisse an, um schnell zu überprüfen, ob die relevanten Daten gefunden werden.

   - Überarbeiten Sie eine Abfrage, und führen Sie die Suche erneut aus.

3. **[Exportieren und Herunterladen von Suchergebnissen](export-content-in-core-ediscovery.md)**. Nachdem Sie die für Ihre Untersuchung relevanten Daten gesucht und gefunden haben, können Sie Sie aus Office 365 zur Überprüfung durch Personen außerhalb des Ermittlungsteams exportieren. Das Exportieren von Daten erfolgt in einem zweistufigen Prozess. Der erste Schritt besteht darin, die Ergebnisse einer Suche im Fall von Office 365 zu exportieren. Dies wird erreicht, indem die Ergebnisse einer Suche in einen von Microsoft bereitgestellten Azure-Speicherort kopiert werden. Der nächste Schritt besteht darin, das eDiscovery-Export Tool zum Herunterladen des Inhalts auf einen lokalen Computer zu verwenden. Zusätzlich zu den exportierten Datendateien enthält der Inhalt des Exportpakets auch einen Exportbericht, einen Zusammenfassungsbericht und einen Fehlerbericht.
