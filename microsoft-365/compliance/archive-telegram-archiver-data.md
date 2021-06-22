---
title: Einrichten eines Connectors zum Archivieren von Kommunikationsdaten in Microsoft 365
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
ms.collection: M365-security-compliance
description: Administratoren können einen TeleMessage-Connector zum Importieren und Archivieren von Nachrichtendaten in Microsoft 365 einrichten. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliance-Features wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten der Drittanbieterdaten Ihrer Organisation verwenden können.
ms.openlocfilehash: d3fbe02dce56bec01d66351aa69500a3d5d93a37
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054845"
---
# <a name="set-up-a-connector-to-archive-telegram-communications-data-preview"></a>Einrichten eines Connectors zum Archivieren von Kommunikationsdaten (Vorschau)

Verwenden Sie den TeleMessage-Connector im Microsoft 365 Compliance Center, um Chats, Anlagen, Dateien und gelöschte Nachrichten und Anrufe zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er eine Verbindung mit dem TeleMessage-Konto Ihrer Organisation her und importiert die mobile Kommunikation von Mitarbeitern mithilfe des Archivarchivs "Archiv" in Postfächer in Microsoft 365.

Nachdem Archivarchivierungsconnectordaten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung, Inhaltssuche und Microsoft 365 Aufbewahrungsrichtlinien auf Kommunikationsdaten anwenden. Sie können z. B. über die Inhaltssuche die Kommunikation mit der Postfächer durchsuchen oder das Postfach, das die Connectordaten des Archivarchivs enthält, einem Verwahrer in einem Advanced eDiscovery Fall zuordnen. Die Verwendung eines Archiver-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Corporate Governance-Bestimmungen und behördlichen Richtlinien zu gewährleisten.

## <a name="overview-of-archiving-telegram-communications-data"></a>Übersicht über die Archivierung von Kommunikationsdaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Kommunikationsdaten in Microsoft 365 erläutert.

![Archivierungsworkflow für Die Kommunikation](../media/TelegramConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage zusammen, um einen Archiver-Connector einzurichten. Weitere Informationen finden Sie unter [Aktivieren des TeleMessage-Archivarchivs für Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-telegram-archiver/).

2. In Echtzeit werden die Datensätze Ihrer Organisation auf die TeleMessage-Website kopiert.

3. Der Archivarchivierungsconnector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der TeleMessage-Website her und überträgt die E-Mail-Nachrichten aus den vorherigen 24 Stunden in einen sicheren Azure Storage Bereich in der Microsoft Cloud.

4. Der Connector importiert die Mobilen Kommunikationselemente in das Postfach eines bestimmten Benutzers. Ein neuer Ordner namens "Archivarchivierer" wird im Postfach des bestimmten Benutzers erstellt, und die Elemente werden in das Postfach importiert. Der Connector führt diese Zuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft des Benutzers* durch. Jede E-Mail-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der E-Mail-Nachricht aufgefüllt wird.

> Zusätzlich zur automatischen Benutzerzuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft* des Benutzers können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei sollte die Mobiltelefonnummer des Benutzers und die entsprechende Microsoft 365 Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird der Connector für jedes E-Mail-Element zuerst die benutzerdefinierte Zuordnungsdatei betrachten. Wenn kein gültiger Microsoft 365 Benutzer gefunden wird, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die E-Mail-Adresseigenschaft des Benutzers des E-Mail-Elements. Wenn der Connector keinen gültigen Microsoft 365 Benutzer in der benutzerdefinierten Zuordnungsdatei oder in der *E-Mail-Adresseigenschaft* des E-Mail-Elements des Benutzers findet, wird das Element nicht importiert.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

- Bestellen Sie den [Archivierungsdienst von TeleMessage ,](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) und rufen Sie ein gültiges Verwaltungskonto für Ihre Organisation ab. Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector im Compliance Center erstellen.

- Registrieren Sie alle Benutzer, die die Archivierung erfordern, im TeleMessage-Konto. Achten Sie beim Registrieren von Benutzern darauf, die gleiche E-Mail-Adresse zu verwenden, die für ihr Microsoft 365 Konto verwendet wird.

- Installieren Sie die App "Archivarchivierung" auf den Mobiltelefonen Ihrer Mitarbeiter, und aktivieren Sie sie. Mit der Archiv-App "Archivierer" können sie mit anderen Benutzern kommunizieren und mit anderen Benutzern chatten.

- Dem Benutzer, der in Schritt 3 einen Archivarchiviererconnector erstellt, muss die Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Dies ist erforderlich, um Connectors auf der **Seite "Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="create-a-telegram-archiver-connector"></a>Erstellen eines Archivr-Connectors

Nachdem Sie die im vorherigen Abschnitt beschriebenen Voraussetzungen erfüllt haben, können Sie den Connector "Archivarchivieren" im Microsoft 365 Compliance Center erstellen. Der Connector verwendet die Von Ihnen bereitgestellten Informationen, um eine Verbindung mit der TeleMessage-Website herzustellen, und überträgt Kommunikationsdaten an die entsprechenden Benutzerpostfachfelder in Microsoft 365.

1. Wechseln Sie zu <https://compliance.microsoft.com> und klicken Sie dann auf **Datenconnectors** > T **elegram Archiver**.

2. Klicken Sie auf der Produktbeschreibungsseite des **Archivarchivs** auf **"Connector hinzufügen".**

3. Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie auf der Seite **"Bei TeleMessage anmelden"** unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **"Weiter".**

    - **Benutzername:** Ihr TeleMessage-Benutzername.

    - **Kennwort:** Ihr TeleMessage-Kennwort.

5. Nachdem der Connector erstellt wurde, können Sie das Popupfenster schließen und zur nächsten Seite wechseln.

6. Aktivieren Sie auf der Seite **"Benutzerzuordnung"** die automatische Benutzerzuordnung. Laden Sie zum Aktivieren der benutzerdefinierten Zuordnung eine CSV-Datei hoch, die die Benutzerzuordnungsinformationen enthält, und klicken Sie dann auf **"Weiter".**

7. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen,** um den Connector zu erstellen.

8. Wechseln Sie zur Registerkarte Connectors auf der Seite **"Datenconnectors",** um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
