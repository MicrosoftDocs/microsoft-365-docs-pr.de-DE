---
title: Einrichten eines Connectors zum Archivieren von Signalkommunikationsdaten in Microsoft 365
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
description: Administratoren können einen TeleMessage-Connector einrichten, um Signalkommunikationsdaten in Microsoft 365 zu importieren und zu archivieren. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliance-Features wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Daten von Drittanbietern Ihrer Organisation zu verwalten.
ms.openlocfilehash: a779cb312e20fdf5fac0987a33734e7e81ba9c74
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054853"
---
# <a name="set-up-a-connector-to-archive-signal-communications-data-preview"></a>Einrichten eines Connectors zum Archivieren von Signalkommunikationsdaten (Vorschau)

Verwenden Sie den TeleMessage-Connector in der Microsoft 365 Compliance Center, um Signalchats, Anlagen, Dateien und gelöschte Nachrichten und Anrufe zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er eine Verbindung mit dem TeleMessage-Konto Ihrer Organisation her und importiert die mobile Kommunikation von Mitarbeitern, die den TeleMessage-Signalarchivierer verwenden, in Postfächer in Microsoft 365.

Nachdem Die Daten des Signalarchivierungsconnectors in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung, Inhaltssuche und Microsoft 365 Aufbewahrungsrichtlinien auf Signalkommunikationsdaten anwenden. Sie können beispielsweise die Signalkommunikation mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die Daten des Signalarchivierungsconnectors enthält, einem Verwahrer in einem Advanced eDiscovery Fall zuordnen. Die Verwendung eines Signalarchivierer-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Corporate Governance-Bestimmungen und behördlichen Richtlinien zu gewährleisten.

## <a name="overview-of-archiving-signal-communications-data"></a>Übersicht über die Archivierung von Signalkommunikationsdaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Signalkommunikationsdaten in Microsoft 365 erläutert.

![Archivierungsworkflow für die Signalkommunikation](../media/SignalConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit TeleMessage zusammen, um einen Signalarchivierer-Connector einzurichten. Weitere Informationen finden Sie unter [Aktivieren des TeleMessage-Signalarchivierers für Microsoft 365](https://www.telemessage.com/microsoft-365-activation-for-signal-archiver/).

2. In Echtzeit werden die Signaldaten Ihrer Organisation auf die TeleMessage-Website kopiert.

3. Der Signalarchivierungsconnector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der TeleMessage-Website her und überträgt die E-Mail-Nachrichten aus den letzten 24 Stunden in einen sicheren Azure Storage Bereich in der Microsoft Cloud.

4. Der Connector importiert die Mobilen Kommunikationselemente in das Postfach eines bestimmten Benutzers. Ein neuer Ordner mit dem Namen "Signalarchivierer" wird im Postfach des bestimmten Benutzers erstellt, und die Elemente werden in das Postfach importiert. Der Connector führt die Zuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft des Benutzers* durch. Jede E-Mail-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der E-Mail-Nachricht aufgefüllt wird.

> Zusätzlich zur automatischen Benutzerzuordnung mithilfe des Werts der *E-Mail-Adresseigenschaft* des Benutzers können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei sollte die Mobiltelefonnummer des Benutzers und die entsprechende Microsoft 365 Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird der Connector für jedes E-Mail-Element zuerst die benutzerdefinierte Zuordnungsdatei betrachten. Wenn kein gültiger Microsoft 365 Benutzer gefunden wird, der der Mobiltelefonnummer eines Benutzers entspricht, verwendet der Connector die E-Mail-Adresseigenschaft des Benutzers des E-Mail-Elements. Wenn der Connector keinen gültigen Microsoft 365 Benutzer in der benutzerdefinierten Zuordnungsdatei oder in der *E-Mail-Adresseigenschaft des E-Mail-Elements* des Benutzers findet, wird das Element nicht importiert.

## <a name="before-you-set-up-a-connector"></a>Vor dem Einrichten eines Connectors

- Order the [Signal Archiver service from TeleMessage](https://www.telemessage.com/mobile-archiver/order-mobile-archiver-for-o365/) and get a valid administration account for your organization. Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector im Compliance Center erstellen.

- Registrieren Sie alle Benutzer, für die die Signalarchivierung erforderlich ist, im TeleMessage-Konto. Achten Sie beim Registrieren von Benutzern darauf, die gleiche E-Mail-Adresse zu verwenden, die für ihr Microsoft 365 Konto verwendet wird.

- Installieren Sie die Signalarchivierungs-App auf den Mobiltelefonen Ihrer Mitarbeiter, und aktivieren Sie sie. Die Signalarchivierer-App ermöglicht es ihnen, mit anderen Signalbenutzern zu kommunizieren und zu chatten.

- Dem Benutzer, der in Schritt 3 einen Signalarchiviererconnector erstellt, muss die Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Dies ist erforderlich, um Connectors auf der **Seite "Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="create-a-signal-archiver-connector"></a>Erstellen eines Signalarchiviererconnectors

Nachdem Sie die im vorherigen Abschnitt beschriebenen Voraussetzungen erfüllt haben, können Sie den Signalarchivierer-Connector im Microsoft 365 Compliance Center erstellen. Der Connector verwendet die informationen, die Sie angeben, um eine Verbindung mit der TeleMessage-Website herzustellen, und überträgt Signalkommunikationsdaten an die entsprechenden Benutzerpostfachfelder in Microsoft 365.

1. Wechseln Sie zu <https://compliance.microsoft.com> "Datenconnectors Signalarchivierung", und klicken Sie dann auf **"Datenkonnektoren".**  >  

2. Klicken Sie auf der Produktbeschreibungsseite **"Signalarchivierer"** auf **"Connector hinzufügen".**

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
