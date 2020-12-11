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
description: Erfahren Sie, wie Administratoren Setup & einen systemeigenen Connector verwenden können, um Daten von einer LinkedIn Unternehmensseite nach Microsoft 365 zu importieren.
ms.openlocfilehash: 42183be3663fbf4b55eadde2173b492feeae5373
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49619981"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>Einrichten eines Connectors zum Archivieren von LinkedIn-Daten

Verwenden Sie einen Connector im Microsoft 365 Compliance Center, um Daten aus LinkedIn Unternehmensseiten zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, wird er alle 24 Stunden mit dem Konto für die bestimmte Seite des LinkedIn Unternehmens verbunden. Der Connector konvertiert die Nachrichten, die auf die Unternehmensseite gesendet werden, in eine e-Mail-Nachricht und importiert diese Elemente dann in ein Postfach in Microsoft 365.

Nachdem die Daten der LinkedIn Unternehmensseite in einem Postfach gespeichert wurden, können Sie Microsoft 365-Kompatibilitätsfeatures wie Beweissicherungsverfahren, Inhaltssuche, In-Place Archivierung, Überwachung und Microsoft 365-Aufbewahrungsrichtlinien auf LinkedIn Daten anwenden. Sie können beispielsweise mithilfe der Inhaltssuche nach diesen Elementen suchen oder das Speicher Postfach einer Depotbank in einem erweiterten eDiscovery-Fall zuordnen. Das Erstellen eines Connectors zum Importieren und Archivieren von LinkedIn Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="assign-roles-and-verify-credentials"></a>Zuweisen von Rollen und Überprüfen der Anmeldeinformationen

- Dem Benutzer, der einen Unternehmensseiten-Konnektor für LinkedIn erstellt, muss in Exchange Online die Rolle "Post Fach Import/-Export" zugewiesen sein. Dies ist für das Hinzufügen von Connectors auf der Seite " **Daten Konnektoren** " im Microsoft 365 Compliance Center erforderlich. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Sie müssen über die Anmeldeinformationen (e-Mail-Adresse oder Telefonnummer und das Kennwort) eines LinkedIn-Benutzerkontos verfügen, das ein Administratorkonto für die Seite LinkedIn Company ist, die Sie archivieren möchten. Sie verwenden diese Anmeldeinformationen, um sich beim Einrichten des Connectors bei LinkedIn anzumelden.

## <a name="create-a-linkedin-connector"></a>Erstellen eines LinkedIn Connectors

1. Wechseln Sie zu, <https://compliance.microsoft.com> und klicken Sie dann auf **Daten Konnektoren**  >  **LinkedIn Unternehmensseiten**.

2. Klicken Sie auf der Produktseite des **LinkedIn Unternehmensseiten** auf **Connector hinzufügen**.

3. Wählen Sie auf der Seite **Nutzungsbedingungen** die Option **akzeptieren** aus.

4. Klicken Sie auf der Seite **mit LinkedIn anmelden** auf **mit LinkedIn anmelden**.

   Die LinkedIn Anmeldeseite wird angezeigt.

   ![Anmeldeseite für LinkedIn](../media/LinkedInSigninPage.png)

5. Geben Sie auf der Seite LinkedIn anmelden die e-Mail-Adresse (oder Telefonnummer) und das Kennwort für das LinkedIn-Konto ein, das der Unternehmensseite zugeordnet ist, die Sie archivieren möchten, und klicken Sie dann auf **Anmelden**.

   Eine Assistentenseite wird mit einer Liste aller LinkedIn Unternehmensseiten angezeigt, die dem Konto zugeordnet sind, mit dem Sie sich angemeldet haben. Ein Connector kann nur für eine Unternehmensseite konfiguriert werden. Wenn Ihre Organisation über mehrere LinkedIn Unternehmensseiten verfügt, müssen Sie für jeden eine Verbindung erstellen.

   ![Eine Seite mit einer Liste von LinkedIn Unternehmensseiten wird angezeigt](../media/LinkedInSelectCompanyPage.png)

6. Wählen Sie die Unternehmensseite aus, von der Sie Elemente archivieren möchten, und klicken Sie dann auf **weiter**.

7. Klicken Sie auf der Seite Speicherort **auswählen** auf in das Feld, wählen Sie die e-Mail-Adresse eines Microsoft 365-Postfachs aus, in das die LinkedIn Elemente importiert werden sollen, und klicken Sie dann auf **weiter**. Elemente werden in den Ordner Posteingang in diesem Postfach importiert.

8. Klicken Sie auf **weiter** , um die Connectoreinstellungen zu überprüfen, und klicken Sie dann auf **Fertig stellen** , um das Connector-Setup abzuschließen.

Nachdem Sie den Connector erstellt haben, können Sie zur Seite **Daten Konnektoren** zurückkehren, um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen (Wählen Sie bei Bedarf **Aktualisieren** aus, um die Liste der Connectors zu aktualisieren). Der Wert in der Spalte **Status** **wartet auf den Start**. Es dauert bis zu 24 Stunden, bis der erste Importvorgang gestartet wurde. Nachdem der Connector zum ersten Mal ausgeführt und die LinkedIn-Elemente importiert hat, wird der Connector alle 24 Stunden ausgeführt und importiert alle neuen Elemente, die in den vorherigen 24 Stunden auf der Seite "LinkedIn Company" erstellt wurden.

Um weitere Details anzuzeigen, wählen Sie den Konnektor in der Liste auf der Seite **Daten Konnektoren** aus, um die Flyout-Seite anzuzeigen. Unter **Status** gibt der angezeigte Datumsbereich den Altersfilter an, der beim Erstellen des Konnektors ausgewählt wurde.

## <a name="more-information"></a>Weitere Informationen

LinkedIn-Elemente werden in den Unterordner LinkedIn im Posteingang des Speicher Postfachs in Microsoft 365 importiert. Sie werden als e-Mail-Nachrichten angezeigt.
