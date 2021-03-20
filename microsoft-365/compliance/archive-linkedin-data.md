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
description: Erfahren Sie, wie Administratoren & einen systemeigenen Connector zum Importieren von Daten von einer LinkedIn-Unternehmensseite in Microsoft 365 verwenden können.
ms.openlocfilehash: 40e51424d086b0eee42d1f15ea577b7e8f1648c1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50906145"
---
# <a name="set-up-a-connector-to-archive-linkedin-data"></a>Einrichten eines Connectors zum Archivieren von LinkedIn-Daten

Verwenden Sie einen Connector im Microsoft 365 Compliance Center, um Daten von LinkedIn-Unternehmensseiten zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er alle 24 Stunden eine Verbindung mit dem Konto für die spezifische LinkedIn -Unternehmensseite ein. Der Connector konvertiert die auf der Seite "Unternehmen" bereitgestellten Nachrichten in eine E-Mail-Nachricht und importiert diese Elemente dann in ein Postfach in Microsoft 365.

Nachdem die Daten der LinkedIn Company-Seite in einem Postfach gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. Das Aufbewahrungsverfahren für Rechtsstreitigkeiten, die Inhaltssuche, In-Place Archivierung, Überwachung und Microsoft 365-Aufbewahrungsrichtlinien auf LinkedIn-Daten anwenden. Sie können beispielsweise mithilfe der Inhaltssuche nach diesen Elementen suchen oder das Speicherpostfach einem Custodian in einem Advanced eDiscovery-Fall zuordnen. Das Erstellen eines Connectors zum Importieren und Archivieren von LinkedIn-Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den richtlinienkonformen Richtlinien von Behörden und Behörden entspricht.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

- Dem Benutzer, der einen LinkedIn-Firmenseitenconnector erstellt, muss die Rolle Postfachimportexport in Exchange Online zugewiesen werden. Dies ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

- Sie müssen über die Anmeldeinformationen (E-Mail-Adresse oder Telefonnummer und Kennwort) eines LinkedIn-Benutzerkontos verfügen, das ein Administrator für die LinkedIn-Unternehmensseite ist, die Sie archivieren möchten. Sie verwenden diese Anmeldeinformationen, um sich beim Einrichten des Connectors bei LinkedIn zu registrieren.

- Der LinkedIn-Connector kann insgesamt 200.000 Elemente an einem einzigen Tag importieren. Wenn mehr als 200.000 LinkedIn-Elemente an einem Tag verfügbar sind, wird keines dieser Elemente nach Microsoft 365 importiert.

## <a name="create-a-linkedin-connector"></a>Erstellen eines LinkedIn-Connectors

1. Wechseln Sie <https://compliance.microsoft.com> zu, und klicken Sie dann auf **Datenconnectors**  >  **LinkedIn Company-Seiten**.

2. Klicken Sie **auf der Produktseite LinkedIn-Unternehmensseiten** auf **Connector hinzufügen.**

3. Wählen Sie **auf der Seite Nutzungsbedingungen** die Option **Akzeptieren aus.**

4. Klicken Sie auf der Seite Anmelden **mit LinkedIn** auf **Anmelden mit LinkedIn**.

   Die LinkedIn-Anmeldeseite wird angezeigt.

   ![LinkedIn-Anmeldeseite](../media/LinkedInSigninPage.png)

5. Geben Sie auf der Seite LinkedIn-Anmeldung die E-Mail-Adresse (oder Telefonnummer) und das Kennwort für das LinkedIn-Konto ein, das der Unternehmensseite zugeordnet ist, die Sie archivieren möchten, und klicken Sie dann auf **Anmelden**.

   Eine Assistentenseite wird mit einer Liste aller LinkedIn-Unternehmensseiten angezeigt, die dem Konto zugeordnet sind, bei dem Sie sich angemeldet haben. Ein Connector kann nur für eine Unternehmensseite konfiguriert werden. Wenn Ihre Organisation über mehrere LinkedIn-Unternehmensseiten verfügt, müssen Sie jeweils einen Connector erstellen.

   ![Eine Seite mit einer Liste der LinkedIn-Unternehmensseiten wird angezeigt](../media/LinkedInSelectCompanyPage.png)

6. Wählen Sie die Unternehmensseite aus, aus der Sie Elemente archivieren möchten, und klicken Sie dann auf **Weiter**.

7. Klicken Sie **auf** der Seite Speicherort auswählen in das Feld, wählen Sie die E-Mail-Adresse eines Microsoft 365-Postfachs aus, in das die LinkedIn-Elemente importiert werden sollen, und klicken Sie dann auf **Weiter**. Elemente werden in den Posteingangsordner in diesem Postfach importiert.

8. Klicken **Sie auf Weiter,** um die Connectoreinstellungen zu überprüfen, und klicken Sie dann auf **Fertig** stellen, um die Connectoreinrichtung abzuschließen.

Nachdem Sie den Connector erstellt haben,  können Sie zur Seite Datenconnectors wechseln, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen (wählen Sie **Bei** Bedarf Aktualisieren aus, um die Liste der Connectors zu aktualisieren). Der Wert in der **Spalte Status** ist Waiting **to start**. Es dauert bis zu 24 Stunden, bis der erste Importvorgang gestartet wird. Nach dem ersten Ausführen und Importieren der LinkedIn-Elemente durch den Connector wird der Connector einmal alle 24 Stunden ausgeführt und importiert alle neuen Elemente, die in den vorherigen 24 Stunden auf der LinkedIn-Unternehmensseite erstellt wurden.

Um weitere Details anzuzeigen, wählen Sie  den Connector in der Liste auf der Seite Datenconnectors aus, um die Flyoutseite anzuzeigen. Unter **Status** gibt der angezeigte Datumsbereich den Altersfilter an, der beim Erstellen des Connectors ausgewählt wurde.

## <a name="more-information"></a>Weitere Informationen

LinkedIn-Elemente werden in den LinkedIn-Unterordner im Posteingang des Speicherpostfachs in Microsoft 365 importiert. Sie werden als E-Mail-Nachrichten angezeigt.