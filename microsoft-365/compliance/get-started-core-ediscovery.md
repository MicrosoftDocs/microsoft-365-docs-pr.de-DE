---
title: Erste Schritte mit Core eDiscovery-Fällen in Microsoft 365
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
description: Beschreibt die ersten Schritte mit Core eDiscovery in Microsoft 365. Nachdem Sie eDiscovery-Berechtigungen zugewiesen und einen Fall erstellt haben, können Sie Mitglieder hinzufügen, eDiscovery-Halterechte erstellen und dann inhalte suchen und exportieren, die für Ihre Untersuchung relevant sind.
ms.openlocfilehash: 00506c2f072fff6aa30c7d96bffdc18eb5eda20b
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311016"
---
# <a name="get-started-with-core-ediscovery-in-microsoft-365"></a>Erste Schritte mit Core eDiscovery in Microsoft 365

Core eDiscovery in Microsoft 365 bietet ein einfaches eDiscovery-Tool, mit dem Organisationen Inhalte in Microsoft 365 und Office 365. Sie können core eDiscovery auch verwenden, um eDiscovery für Inhaltsspeicherorte wie Exchange-Postfächer, SharePoint-Websites, OneDrive-Konten und Microsoft Teams. Für die Bereitstellung von Core eDiscovery ist nichts erforderlich, aber es gibt einige erforderliche Aufgaben, die ein IT-Administrator und eDiscovery-Manager ausführen müssen, bevor Ihre Organisation core eDiscovery zum Suchen, Exportieren und Beibehalten von Inhalten verwenden kann.

In diesem Artikel werden die schritte erläutert, die zum Einrichten von Core eDiscovery erforderlich sind. Dies umfasst die Sicherstellung der ordnungsgemäßen Lizenzierung, die für den Zugriff auf Core eDiscovery und das Festlegen eines eDiscovery-Haltebereichs für Inhaltsstandorte erforderlich ist, sowie das Zuweisen von Berechtigungen an Ihr IT-, Rechts- und Untersuchungsteam, damit es auf Fälle zugreifen und diese verwalten kann. Dieser Artikel bietet außerdem eine übersicht über die Verwendung von Fällen zum Suchen und Exportieren von Inhalten.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Schritt 1: Überprüfen und Zuweisen entsprechender Lizenzen

Die Lizenzierung für Core eDiscovery erfordert das entsprechende Organisationsabonnement und die Benutzerlizenzierung.

- **Organisationsabonnement:** Um auf Core eDiscovery im Microsoft 365 Compliance Center oder im Office 365 Security & Compliance Center zu zugreifen und die Halte- und Exportfeatures zu verwenden, muss Ihre Organisation über ein Microsoft 365 E3- oder Office 365 E3-Abonnement oder höher verfügen.

- **Benutzerlizenzierung:** Zum Platzieren eines eDiscovery-Archivs für Postfächer und Websites muss einem Benutzer eine der folgenden Lizenzen zugewiesen werden, abhängig von Ihrem Organisationsabonnement:

  - Eine Microsoft 365 E3 oder Office 365 E3-Lizenz oder höher

   ODER

  - Office 365 E1-Lizenz mit Exchange Online Plan 2 oder Exchange Online-Archivierung Add-On-Lizenz

  UND

  - Office 365 E1-Lizenz mit SharePoint Online Plan 2 oder OneDrive for Business Plan 2-Add-On-Lizenz
  
  Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern](../admin/manage/assign-licenses-to-users.md).

Informationen zur Lizenzierung finden Sie unter:

- Laden Sie die Lösung "Ermitteln & Antworten" im Microsoft 365 [Compliance Licensing Comparison herunter.](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)

- Weitere Informationen [finden Sie in & Security & Compliance Center Service Description](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center).

## <a name="step-2-assign-ediscovery-permissions"></a>Schritt 2: Zuweisen von eDiscovery-Berechtigungen

Um auf Core eDiscovery zu zugreifen oder als Mitglied eines Core eDiscovery-Falls hinzugefügt zu werden, müssen einem Benutzer die entsprechenden Berechtigungen zugewiesen werden. Insbesondere muss ein Benutzer als Mitglied der Rollengruppe eDiscovery Manager im Office 365 Security & Compliance Center hinzugefügt werden. Mitglieder dieser Rollengruppe können Core eDiscovery-Fälle erstellen und verwalten. Sie können Mitglieder hinzufügen und entfernen, benutzer eine eDiscovery-Schleife setzen, Suchen erstellen und bearbeiten und Inhalte aus einem Core eDiscovery-Fall exportieren.

Führen Sie die folgenden Schritte aus, um der Rollengruppe eDiscovery Manager Benutzer hinzuzufügen:

1. Wechseln Sie zu und melden Sie sich mit den Anmeldeinformationen für ein Administratorkonto in Microsoft 365 [https://protection.office.com/permissions](https://protection.office.com/permissions) oder Office 365 an.

2. Wählen Sie **auf der** Seite Berechtigungen die **Rollengruppe eDiscovery-Manager** aus.

3. Klicken Sie auf der Flyoutseite  des eDiscovery-Managers neben dem **eDiscovery-Manager** auf Bearbeiten.

4. Klicken Sie **auf der Seite eDiscovery-Manager** auswählen im Assistenten zum Bearbeiten von Rollengruppen auf **Discovery-Manager auswählen.**

5. Klicken **Sie auf** Hinzufügen, und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Klicken **Sie auf** Hinzufügen, um die ausgewählten Benutzer hinzuzufügen, und klicken Sie dann auf **Fertig**.

7. Klicken **Sie auf Speichern,** um die Benutzer zur Rollengruppe hinzuzufügen, und klicken Sie dann auf **Schließen,** um den Schritt zu vervollständigen.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Weitere Informationen zur Rollengruppe eDiscovery-Manager

Die Rollengruppe eDiscovery Manager besteht aus zwei Untergruppen. Der Unterschied zwischen diesen Untergruppen basiert auf dem Bereich.

- **eDiscovery Manager**: Kann die von ihnen erstellten Core eDiscovery-Fälle anzeigen und verwalten. Wenn ein anderer eDiscovery-Manager einen Fall erstellt, aber keinen zweiten eDiscovery-Manager als Mitglied dieses Falls hinzu fügt, kann der zweite eDiscovery-Manager den Fall nicht auf der Seite Core eDiscovery im Compliance Center anzeigen oder öffnen. Im Allgemeinen können die meisten Personen in Ihrer Organisation der Untergruppe eDiscovery Manager hinzugefügt werden.

- **eDiscovery-Administrator:** Kann alle Fallverwaltungsaufgaben ausführen, die ein eDiscovery-Manager ausführen kann. Außerdem kann ein eDiscovery-Administrator Folgendes:

  - Zeigen Sie alle Fälle an, die auf der Seite Core eDiscovery aufgeführt sind.
  
  - Verwalten aller Fälle in der Organisation, nachdem er sich selbst als Fallmitglied hinzugefügt hat.

  - Zugreifen auf und Exportieren von Falldaten für jeden Fall in der Organisation.

  Aufgrund des breit gefächerten Zugriffs sollte eine Organisation nur über wenige Administratoren verfügen, die Mitglieder der Untergruppe der eDiscovery-Administratoren sind.

Weitere Informationen zu eDiscovery-Berechtigungen und eine Beschreibung jeder Rolle, die der Rollengruppe eDiscovery-Manager zugewiesen ist, finden Sie unter [Assign eDiscovery permissions](assign-ediscovery-permissions.md).

## <a name="step-3-create-a-core-ediscovery-case"></a>Schritt 3: Erstellen eines Core eDiscovery-Falls

Im nächsten Schritt erstellen Sie einen Fall und beginnen mit core eDiscovery. Führen Sie die folgenden Schritte aus, um einen Fall zu erstellen und Mitglieder hinzuzufügen. Der Benutzer, der den Fall erstellt, wird automatisch als Mitglied hinzugefügt.

1. Wechseln Sie zu, und melden Sie sich mit den Anmeldeinformationen für ein Benutzerkonto an, dem die entsprechenden [https://compliance.microsoft.com](https://compliance.microsoft.com) eDiscovery-Berechtigungen zugewiesen wurden. Mitglieder der Rollengruppe Organisationsverwaltung können auch Core eDiscovery-Fälle erstellen.

2. Klicken Sie im linken Navigationsbereich Microsoft 365 Compliance Center auf Alle **anzeigen,** und klicken Sie dann auf **eDiscovery > Core**.

3. Klicken Sie **auf der Seite Core eDiscovery** auf Fall **erstellen**.

4. Geben Sie **auf der** Seite Flyout für neue Fälle dem Fall einen Namen (erforderlich) zu, und geben Sie dann eine optionale Beschreibung ein. Der Fallname muss in Ihrer Organisation eindeutig sein.

5. Klicken **Sie auf Speichern,** um den Fall zu erstellen.

   Der neue Fall wird erstellt und auf der Seite Core eDiscovery angezeigt. Möglicherweise müssen Sie auf **Aktualisieren klicken,** um den neuen Fall anzeigen zu können.

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>Schritt 4 (optional): Hinzufügen von Mitgliedern zu einem Core eDiscovery-Fall

Wenn Sie einen Fall in Schritt 3 erstellen und die einzige Person sind, die den Fall verwendet, müssen Sie diesen Schritt nicht ausführen. Sie können den Fall verwenden, um eDiscovery-Halteverbote zu erstellen, nach Inhalten zu suchen und Suchergebnisse zu exportieren. Führen Sie diesen Schritt aus, wenn Sie anderen Benutzern (oder Rollengruppen) Zugriff auf den Fall ermöglichen möchten.

1. Klicken Sie auf der Seite Core **eDiscovery** im Microsoft 365 Compliance Center auf den Namen des Falls, dem Sie Mitglieder hinzufügen möchten.

2. Wählen Sie auf der Homepage der Fall die **Registerkarte Einstellungen** aus, und wählen Sie dann Access **& aus.**

3. Klicken Sie **auf & Zugriffsberechtigungen-Flyout** unter **Mitglieder** auf **Hinzufügen,** um dem Fall Mitglieder hinzuzufügen.

    Sie können auch Rollengruppen als Mitglieder eines Falls hinzufügen. Klicken **Sie unter Rollengruppen** auf **Hinzufügen**. Sie können nur die Rollengruppen, in der Sie Mitglied sind, einem Fall zuweisen. Das liegt daran, dass Rollengruppen steuern, wer Einem eDiscovery-Fall Mitglieder zuweisen kann.

4. Klicken Sie in der Liste der Personen oder Rollengruppen, die als Mitglieder des Falls hinzugefügt werden können, links neben dem Namen der Personen (oder Rollengruppen), die Sie hinzufügen möchten. Wenn Sie über eine große Liste von Personen oder Rollengruppen verfügen, die als Mitglieder hinzugefügt werden können, verwenden Sie das Suchfeld, um nach einer bestimmten Person oder Rollengruppe in der Liste zu suchen. 
  
5. Nachdem Sie die Personen oder Rollengruppen ausgewählt haben, die als Mitglieder des Falls hinzugefügt werden, klicken Sie auf **Speichern,** um die neuen Mitglieder oder Rollengruppen zu speichern.

## <a name="explore-the-core-ediscovery-workflow"></a>Erkunden des Core eDiscovery-Workflows

Um Sie mit der Verwendung von eDiscovery zu beginnen, finden Sie hier einen einfachen Workflow zum Erstellen von eDiscovery-Speichern für Personen von Interesse, zum Suchen nach Inhalten, die für Ihre Untersuchung relevant sind, und zum Exportieren dieser Daten zur weiteren Überprüfung. In jedem dieser Schritte werden auch einige erweiterte Core eDiscovery-Funktionen hervorgehoben, die Sie erkunden können.

![Zentraler eDiscovery-Workflow](../media/CoreEdiscoveryWorkflow.png)

1. **[Erstellen eines eDiscovery-Halteraums](create-ediscovery-holds.md)**. Der erste Schritt nach dem Erstellen eines Falls besteht im Platzieren eines Halteraums (auch *als eDiscovery-Halteraum* bezeichnet) für die Inhaltsorte der Personen, die an Ihrer Untersuchung interessiert sind. Inhaltsspeicherorte umfassen Exchange Postfächer, SharePoint Websites, OneDrive Konten und die Postfächer und Websites, die Microsoft Teams und Office 365 zugeordnet sind. Obwohl dieser Schritt optional ist, werden beim Erstellen eines eDiscovery-Halteraums Inhalte beibehalten, die für den Fall während der Untersuchung relevant sein können. Beim Erstellen eines eDiscovery-Halteraums können Sie alle Inhalte an bestimmten Inhaltsstandorten beibehalten oder einen abfragebasierten Halteraum erstellen, um nur den Inhalt zu erhalten, der einer Halteabfrage entspricht. Neben dem Beibehalten von Inhalten besteht ein weiterer guter Grund zum Erstellen von eDiscovery-Speichern in der schnellen Suche nach den Speicherorten im Haltespeicherort (anstatt jeden zu durchsuchende Speicherort auszuwählen), wenn Sie im nächsten Schritt Suchen erstellen und ausführen. Nachdem Sie ihre Untersuchung abgeschlossen haben, können Sie alle von Ihnen erstellten Halteschleifen los.

2. **[Suchen nach Inhalten](search-for-content-in-core-ediscovery.md)**. Nachdem Sie eDiscovery-Halteplätze erstellt haben, verwenden Sie das integrierte Suchtool, um die Speicherorte im Halteraum zu durchsuchen. Sie können auch andere Inhaltsspeicherorte nach Daten durchsuchen, die für den Fall relevant sein können. Sie können verschiedene Suchbegriffe erstellen und ausführen, die dem Fall zugeordnet sind. Sie verwenden Schlüsselwörter, Eigenschaften [](keyword-queries-and-search-conditions.md) und Bedingungen, um Suchabfragen zu erstellen, die Suchergebnisse mit den Daten zurückgeben, die für den Fall am ehesten relevant sind. Sie können auch Folgendes tun:

   - Anzeigen von Suchstatistiken, mit deren Hilfe Sie eine Suchabfrage zum Einen der Ergebnisse einfeinern können.

   - Zeigen Sie eine Vorschau der Suchergebnisse an, um schnell zu überprüfen, ob die relevanten Daten gefunden werden.

   - Überarbeiten Sie eine Abfrage, und führen Sie die Suche erneut aus.

3. **[Exportieren und Herunterladen von Suchergebnissen](export-content-in-core-ediscovery.md)**. Nachdem Sie Daten gesucht und gefunden haben, die für Ihre Untersuchung relevant sind, können Sie sie aus Office 365 zur Überprüfung durch Personen außerhalb des Untersuchungsteams exportieren. Das Exportieren von Daten ist ein Zwei-Schritt-Prozess. Der erste Schritt besteht im Exportieren der Ergebnisse einer Suche im Fall aus Office 365. Dazu werden die Ergebnisse einer Suche an einen von Microsoft bereitgestellten Speicherort Azure Storage kopiert. Im nächsten Schritt verwenden Sie das eDiscovery-Export-Tool, um die Inhalte auf einen lokalen Computer herunterzuladen. Zusätzlich zu den exportierten Datendateien enthält der Inhalt des Exportpakets auch einen Exportbericht, einen Zusammenfassenden Bericht und einen Fehlerbericht.
