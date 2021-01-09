---
title: Einrichten eines Connectors zum Archivieren von LinkedIn-Daten
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Erfahren Sie, wie Administratoren & einen systemeigenen Connector zum Importieren von Daten von einer LinkedIn -Unternehmensseite in Microsoft 365 verwenden können.
ms.openlocfilehash: 9f6cb2c6d5c47559f1fda13b6d03bfed3afe6fa2
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790179"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>Einrichten eines Connectors zum Archivieren von LinkedIn-Daten

Verwenden Sie einen Connector im Microsoft 365 Compliance Center, um Daten von LinkedIn -Unternehmensseiten zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, wird alle 24 Stunden eine Verbindung mit dem Konto für die spezifische LinkedIn -Unternehmensseite hergestellt. Der Connector konvertiert die auf der Seite "Unternehmen" veröffentlichten Nachrichten in eine E-Mail-Nachricht und importiert diese Elemente dann in ein Postfach in Microsoft 365.

Nachdem die Daten der LinkedIn -Company-Seite in einem Postfach gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. das Aufbewahrungsverfahren für Rechtsstreitigkeiten, die Inhaltssuche, In-Place-Archivierung, Überwachung und Microsoft 365-Aufbewahrungsrichtlinien auf LinkedIn-Daten anwenden. Sie können beispielsweise mithilfe der Inhaltssuche nach diesen Elementen suchen oder das Speicherpostfach einem Verwahrer in einem Advanced eDiscovery-Fall zuordnen. Das Erstellen eines Connectors zum Importieren und Archivieren von LinkedIn-Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den behördlichen und behördlichen Richtlinien entspricht.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

- Dem Benutzer, der einen LinkedIn Company Page Connector erstellt, muss die Rolle "Postfachimport/-export" in Exchange Online zugewiesen sein. Dies ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimport/-export" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimport/-export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) den [Abschnitten](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) "Rollengruppen erstellen" oder "Rollengruppen ändern" im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Sie müssen über die Anmeldeinformationen (E-Mail-Adresse oder Telefonnummer und Kennwort) eines LinkedIn-Benutzerkontos verfügen, das ein Administrator für die zu archivierende LinkedIn-Unternehmensseite ist. Sie verwenden diese Anmeldeinformationen, um sich beim Einrichten des Connectors bei LinkedIn zu anmelden.

- Der LinkedIn Connector kann insgesamt 200.000 Elemente an einem einzigen Tag importieren. Wenn mehr als 200.000 LinkedIn-Elemente an einem Tag verfügbar sind, wird keines dieser Elemente nach Microsoft 365 importiert.

## <a name="create-a-linkedin-connector"></a>Erstellen eines LinkedIn-Connectors

1. Wechseln Sie <https://compliance.microsoft.com> zu den Seiten **"LinkedIn Company", und** klicken Sie dann auf  >  **"Datenconnectors".**

2. Klicken Sie **auf der Produktseite der LinkedIn-Unternehmensseiten** auf **"Connector hinzufügen".**

3. Wählen Sie **auf der Seite "Nutzungsbedingungen"** die Option **"Annehmen" aus.**

4. Klicken Sie **auf der Seite "Mit LinkedIn** anmelden" **auf "Mit LinkedIn anmelden".**

   Die Anmeldeseite von LinkedIn wird angezeigt.

   ![LinkedIn-Anmeldeseite](../media/LinkedInSigninPage.png)

5. Geben Sie auf der Anmeldeseite von LinkedIn die E-Mail-Adresse (oder Telefonnummer) und das Kennwort für das LinkedIn-Konto ein, das der Unternehmensseite zugeordnet ist, die Sie archivieren möchten, und klicken Sie dann auf **"Anmelden".**

   Eine Assistentenseite wird mit einer Liste aller LinkedIn-Unternehmensseiten angezeigt, die dem Konto zugeordnet sind, bei dem Sie sich angemeldet haben. Ein Connector kann nur für eine Unternehmensseite konfiguriert werden. Wenn Ihre Organisation über mehrere LinkedIn-Unternehmensseiten verfügt, müssen Sie für jede Seite einen Connector erstellen.

   ![Eine Seite mit einer Liste von LinkedIn-Unternehmensseiten wird angezeigt.](../media/LinkedInSelectCompanyPage.png)

6. Wählen Sie die Unternehmensseite aus, auf der Sie Elemente archivieren möchten, und klicken Sie dann auf **"Weiter".**

7. Klicken Sie **auf** der Seite "Speicherort auswählen" auf das Feld, wählen Sie die E-Mail-Adresse eines Microsoft 365-Postfachs aus, in das die LinkedIn-Elemente importiert werden sollen, und klicken Sie dann auf **"Weiter".** Elemente werden in den Posteingangsordner in diesem Postfach importiert.

8. Klicken **Sie auf "Weiter",** um die Connectoreinstellungen zu überprüfen, und klicken Sie dann auf **"Fertig** stellen", um die Connectoreinrichtung abzuschließen.

Nachdem Sie den Connector erstellt haben,  können Sie zur Seite "Datenconnectors" zurückwechseln, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen (wählen Sie bei Bedarf "Aktualisieren" aus, um die Liste der Connectors zu aktualisieren).  Der Wert in der **Spalte "Status"** wartet **auf den Start.** Es dauert bis zu 24 Stunden, bis der erste Importvorgang gestartet wird. Nach dem ersten Ausführen und Importieren der LinkedIn-Elemente wird der Connector einmal alle 24 Stunden ausgeführt und importiert alle neuen Elemente, die in den letzten 24 Stunden auf der Seite "LinkedIn Company" erstellt wurden.

Um weitere Details anzuzeigen, wählen Sie den Connector in der Liste auf der Seite **"Datenconnectors"** aus, um die Flyoutseite anzuzeigen. Unter **"Status"** gibt der angezeigte Datumsbereich den Altersfilter an, der bei der Connectorerstellung ausgewählt wurde.

## <a name="more-information"></a>Weitere Informationen

LinkedIn-Elemente werden in den Unterordner "LinkedIn" im Posteingang des Speicherpostfachs in Microsoft 365 importiert. Sie werden als E-Mail-Nachrichten angezeigt.
