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
description: Beschreibt die ersten Schritte mit Core eDiscovery in Microsoft 365. Nachdem Sie eDiscovery-Berechtigungen zugewiesen und einen Fall erstellt haben, können Sie Mitglieder hinzufügen, eDiscovery-Haltebereiche erstellen und dann nach Inhalten suchen und exportieren, die für Ihre Untersuchung relevant sind.
ms.openlocfilehash: 9466b2e3268a447a4008363e88290d4d02558c76
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341472"
---
# <a name="get-started-with-core-ediscovery-in-microsoft-365"></a>Erste Schritte mit Core eDiscovery in Microsoft 365

Core eDiscovery in Microsoft 365 bietet ein einfaches eDiscovery-Tool, mit dem Organisationen Inhalte in Microsoft 365 und Office 365 suchen und exportieren können. Sie können Core eDiscovery auch verwenden, um einen eDiscovery-Speicher für Inhaltsspeicherorte zu platzieren, z. B. Exchange Postfächer, SharePoint Websites, OneDrive Konten und Microsoft Teams. Es ist nichts erforderlich, um Core eDiscovery bereitzustellen, aber es gibt einige erforderliche Aufgaben, die ein IT-Administrator und eDiscovery-Manager ausführen müssen, bevor Ihre Organisation mit der Verwendung von Core eDiscovery zum Suchen, Exportieren und Aufbewahren von Inhalten beginnen kann.

In diesem Artikel werden die erforderlichen Schritte zum Einrichten von Core eDiscovery erläutert. Dazu gehört die Sicherstellung der ordnungsgemäßen Lizenzierung, die für den Zugriff auf Core eDiscovery erforderlich ist, und das Erteilen eines eDiscovery-Haltebereichs für Inhaltsspeicherorte sowie das Zuweisen von Berechtigungen zu Ihrem IT-, Rechts- und Untersuchungsteam, damit sie auf Fälle zugreifen und diese verwalten können. Dieser Artikel bietet auch eine allgemeine Übersicht über die Verwendung von Fällen zum Suchen und Exportieren von Inhalten.

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>Schritt 1: Überprüfen und Zuweisen der entsprechenden Lizenzen

Die Lizenzierung für Core eDiscovery erfordert das entsprechende Organisationsabonnement und die Lizenzierung pro Benutzer.

- **Organisationsabonnement:** Um auf Core eDiscovery im Microsoft 365 Compliance Center oder im Office 365 Security & Compliance Center zuzugreifen und die Halte- und Exportfunktionen zu verwenden, muss Ihre Organisation über ein Microsoft 365 E3- oder Office 365 E3-Abonnement oder höher verfügen.

- **Lizenzierung pro Benutzer:** Um eine eDiscovery-Aufbewahrung für Postfächer und Websites zu aktivieren, muss einem Benutzer je nach Abonnement Ihrer Organisation eine der folgenden Lizenzen zugewiesen werden:

  - Eine Microsoft 365 E3 oder Office 365 E3 Lizenz oder höher

   ODER

  - Office 365 E1-Lizenz mit einer Exchange Online Plan 2- oder Exchange Online-Archivierung-Add-On-Lizenz

  UND

  - Office 365 E1-Lizenz mit einer Add-On-Lizenz für SharePoint Onlineplan 2 oder OneDrive for Business Plan 2
  
  Informationen zum Zuweisen von Lizenzen finden Sie unter [Zuweisen von Lizenzen zu Benutzern.](../admin/manage/assign-licenses-to-users.md)

Informationen zur Lizenzierung:

- Laden Sie die Lösung "Entdecken & Antworten" im [Microsoft 365 Compliance-Lizenzierungsvergleich herunter,](/office365/servicedescriptions/downloads/microsoft-365-compliance-licensing-comparison.xlsx)und sehen Sie sich diese an.

- Weitere Informationen finden Sie in der [Security & Compliance Center-Dienstbeschreibung.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)

## <a name="step-2-assign-ediscovery-permissions"></a>Schritt 2: Zuweisen von eDiscovery-Berechtigungen

Um auf Core eDiscovery zuzugreifen oder als Mitglied eines Core eDiscovery-Falls hinzugefügt zu werden, müssen einem Benutzer die entsprechenden Berechtigungen zugewiesen werden. Insbesondere muss ein Benutzer als Mitglied der Rollengruppe "eDiscovery-Manager" im Office 365 Security & Compliance Center hinzugefügt werden. Mitglieder dieser Rollengruppe können Core eDiscovery-Fälle erstellen und verwalten. Sie können Mitglieder hinzufügen und entfernen, Benutzern eine eDiscovery-Aufbewahrung unterstellen, Suchen erstellen und bearbeiten und Inhalte aus einem Core eDiscovery-Fall exportieren.

Führen Sie die folgenden Schritte aus, um der Rollengruppe "eDiscovery-Manager" Benutzer hinzuzufügen:

1. Rufen Sie <https://compliance.microsoft.com/permissions> die Anmeldeinformationen für ein Administratorkonto in Ihrer Microsoft 365 oder Office 365 Organisation auf, und melden Sie sich an.

2. Wählen Sie auf der Seite **"Berechtigungen"** die **Rollengruppe "eDiscovery-Manager"** aus.

3. Klicken Sie auf der Flyoutseite des eDiscovery-Managers neben dem **Abschnitt "eDiscovery-Manager"** auf **"Bearbeiten".**

4. Klicken Sie auf der Seite **"eDiscovery-Manager auswählen"** im Assistenten zum Bearbeiten von Rollengruppen auf **"Discovery-Manager auswählen".**

5. Klicken Sie auf **"Hinzufügen",** und aktivieren Sie dann das Kontrollkästchen für alle Benutzer, die Sie der Rollengruppe hinzufügen möchten.

6. Klicken Sie auf **"Hinzufügen",** um die ausgewählten Benutzer hinzuzufügen, und klicken Sie dann auf **"Fertig".**

7. Klicken Sie auf **"Speichern",** um die Benutzer zur Rollengruppe hinzuzufügen, und klicken Sie dann auf **"Schließen",** um den Schritt abzuschließen.

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>Weitere Informationen zur Rollengruppe "eDiscovery-Manager"

Es gibt zwei Untergruppen in der Rollengruppe "eDiscovery-Manager". Der Unterschied zwischen diesen Untergruppen basiert auf dem Bereich.

- **eDiscovery-Manager:** Kann die von ihnen erstellten core eDiscovery-Fälle anzeigen und verwalten oder Mitglied sein. Wenn ein anderer eDiscovery-Manager einen Fall erstellt, aber keinen zweiten eDiscovery-Manager als Mitglied dieses Falls hinzufüge, kann der zweite eDiscovery-Manager den Fall nicht auf der Core eDiscovery-Seite im Compliance Center anzeigen oder öffnen. Im Allgemeinen können die meisten Personen in Ihrer Organisation der Untergruppe "eDiscovery-Manager" hinzugefügt werden.

- **eDiscovery-Administrator:** Kann alle Fallverwaltungsaufgaben ausführen, die ein eDiscovery-Manager ausführen kann. Außerdem kann ein eDiscovery-Administrator Folgendes:

  - Zeigen Sie alle Fälle an, die auf der Core eDiscovery-Seite aufgeführt sind.
  
  - Verwalten aller Fälle in der Organisation, nachdem er sich selbst als Fallmitglied hinzugefügt hat.

  - Zugreifen auf und Exportieren von Falldaten für jeden Fall in der Organisation.

  Aufgrund des breit gefächerten Zugriffs sollte eine Organisation nur über wenige Administratoren verfügen, die Mitglieder der Untergruppe der eDiscovery-Administratoren sind.

Weitere Informationen zu eDiscovery-Berechtigungen und eine Beschreibung der einzelnen Rollen, die der Rollengruppe "eDiscovery-Manager" zugewiesen sind, finden Sie unter ["Zuweisen von eDiscovery-Berechtigungen".](assign-ediscovery-permissions.md)

## <a name="step-3-create-a-core-ediscovery-case"></a>Schritt 3: Erstellen eines Core eDiscovery-Falls

Der nächste Schritt besteht darin, einen Fall zu erstellen und mit der Verwendung von Core eDiscovery zu beginnen. Führen Sie die folgenden Schritte aus, um einen Fall zu erstellen und Mitglieder hinzuzufügen. Der Benutzer, der den Fall erstellt, wird automatisch als Mitglied hinzugefügt.

1. Rufen Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) die Anmeldeinformationen für ein Benutzerkonto ab, dem die entsprechenden eDiscovery-Berechtigungen zugewiesen wurden, und melden Sie sich an. Mitglieder der Rollengruppe "Organisationsverwaltung" können auch Core eDiscovery-Fälle erstellen.

2. Klicken Sie im linken Navigationsbereich des Microsoft 365 Compliance Center auf **Alle anzeigen,** und klicken Sie dann auf **eDiscovery > Core**.

3. Klicken Sie auf der Core **eDiscovery-Seite** auf **"Fall erstellen".**

4. Geben Sie auf der Flyoutseite **"Neuer Fall"** dem Fall einen Namen (erforderlich) und geben Sie dann eine optionale Beschreibung ein. Der Fallname muss in Ihrer Organisation eindeutig sein.

5. Klicken Sie auf **"Speichern",** um den Fall zu erstellen.

   Der neue Fall wird erstellt und auf der Core eDiscovery-Seite angezeigt. Möglicherweise müssen Sie auf **"Aktualisieren"** klicken, um den neuen Fall anzuzeigen.

## <a name="step-4-optional-add-members-to-a-core-ediscovery-case"></a>Schritt 4 (optional): Hinzufügen von Mitgliedern zu einem Core eDiscovery-Fall

Wenn Sie in Schritt 3 einen Fall erstellen und die einzige Person sind, die den Fall verwendet, müssen Sie diesen Schritt nicht ausführen. Sie können den Fall verwenden, um eDiscovery-Haltebereiche zu erstellen, nach Inhalten zu suchen und Suchergebnisse zu exportieren. Führen Sie diesen Schritt aus, wenn Sie anderen Benutzern (oder Rollengruppen) Zugriff auf den Fall gewähren möchten.

1. Klicken Sie auf der **Core eDiscovery-Seite** im Microsoft 365 Compliance Center auf den Namen des Falls, dem Sie Mitglieder hinzufügen möchten.

2. Wählen Sie auf der Startseite des Falls die **Registerkarte Einstellungen** und dann Access **& Berechtigungen** aus.

3. Klicken Sie auf der **Flyoutseite "Access & Berechtigungen"** unter **"Mitglieder"** auf **"Hinzufügen",** um dem Fall Mitglieder hinzuzufügen.

    Sie können auch Rollengruppen als Mitglieder eines Falls hinzufügen. Klicken Sie unter **"Rollengruppen"** auf **"Hinzufügen".** Sie können nur die Rollengruppen, in denen Sie Mitglied sind, einem Fall zuweisen. Der Grund dafür ist, dass Rollengruppen steuern, wer Einem eDiscovery-Fall Mitglieder zuweisen kann.

4. Klicken Sie in der Liste der Personen oder Rollengruppen, die als Mitglieder des Falls hinzugefügt werden können, links neben dem Namen der Personen (oder Rollengruppen), die Sie hinzufügen möchten. Wenn Sie über eine große Liste von Personen oder Rollengruppen verfügen, die als Mitglieder hinzugefügt werden können, verwenden Sie das **Suchfeld,** um nach einer bestimmten Person oder Rollengruppe in der Liste zu suchen.
  
5. Nachdem Sie die Personen oder Rollengruppen ausgewählt haben, die als Mitglieder des Falls hinzugefügt werden sollen, klicken Sie auf **"Speichern",** um die neuen Mitglieder oder Rollengruppen zu speichern.

## <a name="explore-the-core-ediscovery-workflow"></a>Erkunden des eDiscovery-Kernworkflows

Hier finden Sie einen einfachen Workflow zum Erstellen von eDiscovery-Haltebereichen für Personen von Interesse, zum Suchen nach Inhalten, die für Ihre Untersuchung relevant sind, und zum Exportieren dieser Daten zur weiteren Überprüfung. In jedem dieser Schritte werden auch einige erweiterte Core eDiscovery-Funktionen hervorgehoben, die Sie erkunden können.

![Core eDiscovery-Workflow](../media/CoreEdiscoveryWorkflow.png)

1. **[Erstellen sie einen eDiscovery-Haltebereich.](create-ediscovery-holds.md)** Der erste Schritt nach dem Erstellen eines Falls besteht darin, für die Inhaltsspeicherorte der Personen, die an Ihrer Untersuchung interessiert sind, ein Haltebereich (auch *als eDiscovery-Haltebereich* bezeichnet) zu platzieren. Zu den Inhaltsspeicherorten gehören Exchange Postfächer, SharePoint Websites, OneDrive Konten sowie die Postfächer und Websites, die Microsoft Teams und Office 365 Gruppen zugeordnet sind. Obwohl dieser Schritt optional ist, behält das Erstellen eines eDiscovery-Haltebereichs Inhalte bei, die während der Untersuchung für den Fall relevant sein können. Wenn Sie einen eDiscovery-Haltebereich erstellen, können Sie alle Inhalte an bestimmten Inhaltsspeicherorten beibehalten, oder Sie können einen abfragebasierten Haltebereich erstellen, um nur die Inhalte beizubehalten, die einer Haltebereichsabfrage entsprechen. Neben der Aufbewahrung von Inhalten ist ein weiterer guter Grund für die Erstellung von eDiscovery-Haltebereichen, die Inhaltsspeicherorte schnell zu durchsuchen (anstatt jeden zu durchsuchenden Speicherort auswählen zu müssen), wenn Sie im nächsten Schritt Suchvorgänge erstellen und ausführen. Nachdem Sie Ihre Untersuchung abgeschlossen haben, können Sie alle von Ihnen erstellten Haltebereich freigeben.

2. **[Suchen sie nach Inhalten.](search-for-content-in-core-ediscovery.md)** Nachdem Sie eDiscovery-Haltebereiche erstellt haben, verwenden Sie das integrierte Suchtool, um die Haltebereiche von Inhalten zu durchsuchen. Sie können auch andere Inhaltsspeicherorte nach Daten durchsuchen, die für den Fall relevant sein können. Sie können verschiedene Suchvorgänge erstellen und ausführen, die dem Fall zugeordnet sind. Sie verwenden Schlüsselwörter, Eigenschaften und Bedingungen, um [Suchabfragen](keyword-queries-and-search-conditions.md) zu erstellen, die Suchergebnisse mit den daten zurückgeben, die für den Fall am wahrscheinlichsten relevant sind. Sie können auch Folgendes tun:

   - Anzeigen von Suchstatistiken, mit denen Sie eine Suchabfrage verfeinern können, um die Ergebnisse einzugrenzen.

   - Anzeigen einer Vorschau der Suchergebnisse, um schnell zu überprüfen, ob die relevanten Daten gefunden werden.

   - Überarbeiten Sie eine Abfrage, und führen Sie die Suche erneut aus.

3. **[Exportieren und Herunterladen von Suchergebnissen.](export-content-in-core-ediscovery.md)** Nachdem Sie nach Daten gesucht und diese gefunden haben, die für Ihre Untersuchung relevant sind, können Sie sie aus Office 365 exportieren, um sie von Personen außerhalb des Untersuchungsteams zu überprüfen. Das Exportieren von Daten besteht aus zwei Schritten. Der erste Schritt besteht darin, die Ergebnisse einer Suche im Fall aus Office 365 zu exportieren. Dazu werden die Ergebnisse einer Suche an einen von Microsoft bereitgestellten Azure Storage Speicherort kopiert. Der nächste Schritt besteht darin, das eDiscovery-Exporttool zum Herunterladen des Inhalts auf einen lokalen Computer zu verwenden. Zusätzlich zu den exportierten Datendateien enthält das Exportpaket auch einen Exportbericht, einen Zusammenfassungsbericht und einen Fehlerbericht.
