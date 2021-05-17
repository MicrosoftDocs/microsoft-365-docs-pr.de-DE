---
title: Einrichten eines Connectors zum Archivieren von "Red tail Speak"-Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von "Red tail Speak"-Daten aus "Microsoft 365" einrichten. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365. Nachdem Sie diese Daten archiviert haben, können Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um Daten von Drittanbietern zu verwalten.
ms.openlocfilehash: ee9540b4000387454eb177f864407e03abd25bc6
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164148"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Einrichten eines Connectors zum Archivieren von Redtail Speak-Daten

Verwenden Sie einen Connectors vom Microsoft 365, um Daten aus dem Redtail Speak to user mailboxes in Ihrer Organisation Microsoft 365 archivieren. Mit Einem ["Redtail](https://globanet.com/redtail/) Speak"-Connector, der für die Erfassung von Elementen vom SFTP-Server Ihrer Organisation konfiguriert ist, auf dem die Elemente von Redtail empfangen werden, bietet Ihnen Einschwenkung. Der Connector konvertiert den Inhalt aus Redtail Speak in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem Redtail Speak-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anwenden. Die Verwendung eines Redtail Speak-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 Kann Dazu beitragen, dass Ihre Organisation die Richtlinien von Behörden und Behörden einhalten kann.

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Übersicht über die Archivierung der Redtail Speak-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der Redtail Speak-Daten in Microsoft 365.

![Archivierungsworkflow für Redtail Speak-Daten](../media/RedtailSpeakConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Redtail Speak zusammen, um ein SMTP-Gateway zu einrichten und zu konfigurieren, in dem Nachrichten täglich von Redtail Speak an den SFTP-Server Ihrer Organisation weitergeleitet werden.

2. Einmal alle 24 Stunden werden die Redtail Speak-Elemente auf die Website "Merge1" von "Veritas Merge1" kopiert. Der Connector konvertiert auch die Redtail Speak-Elemente in ein E-Mail-Nachrichtenformat.

3. Der Redtail Speak-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit dem Standort von Veritas Merge1 her und überträgt die Nachrichten an einen sicheren Azure Storage in der Microsoft Cloud.

4. Der Connector importiert die konvertierten Redtail Speak-Elemente mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung, wie in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschrieben, in die Postfächer bestimmter Benutzer. In den Benutzerpostfächern wird ein Unterordner im Posteingangsordner **"Redtail Speak"** erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der Email-Eigenschaft, in welches Postfach Elemente *importiert werden.* Jedes Redtail Speak-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für Denkdruck1 für Microsoft Connectors. Wenden Sie sich zum Erstellen eines Kontos an [den Kundensupport von Veritas](https://www.veritas.com/content/support/). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- In Schritt 2 müssen Sie den SFTP-Server Ihrer Organisation angeben. Dieser Schritt ist erforderlich, damit Sich Einsingen1 mit ihr in Verbindung setzen kann, um Redtail Speak-Daten über SFTP zu sammeln.

- Der Benutzer, der den Redtail Speak-Importerconnector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen) muss der Rolle Postfachimportexport in Exchange Online. Diese Rolle ist erforderlich, um Connectors auf der Seite Datenconnectors im compliance center Microsoft 365 hinzufügen. Diese Rolle ist standardmäßig keinem Rollengruppen in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-redtail-speak-connector"></a>Schritt 1: Einrichten des Redtail Speak-Connectors

Der erste Schritt besteht  im Zugriff auf die Seite Datenconnectors im Microsoft 365 Compliance Center und erstellen Sie einen Connector für die Redtail Speak-Daten.

1. Wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com/) Und wählen **Sie Datenconnectors** &gt; **Redtail Speak aus.**

2. Wählen Sie **auf der Seite Produktbeschreibung** von Redtail Speak die Option Neuen Connector hinzufügen **aus.**

3. Wählen Sie **auf der Seite Nutzungsbedingungen** die Option **Akzeptieren aus.**

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und wählen Sie dann **Weiter aus.**

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-redtail-speak-connector-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des Redtail Speak-Connectors auf der Website "Merge1"

Der zweite Schritt besteht in der Konfiguration des Redtail Speak-Connectors auf dem Merge1-Standort. Weitere Informationen zum Konfigurieren des Redtail Speak-Connectors finden Sie unter [Merge1-Benutzerhandbuch für Drittanbieterconnectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf).

Nachdem Sie speichern **& abgeschlossen**  ausgewählt haben, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung abzuschließen:

1. Aktivieren Sie auf der Seite Benutzer **Microsoft 365** Benutzer zuordnen die automatische Benutzerzuordnung. Die Redtail Speak-Elemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365 zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Wählen **Sie Weiter** aus, überprüfen  Sie Ihre Einstellungen, und wechseln Sie zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-redtail-speak-connector"></a>Schritt 4: Überwachen des Redtail Speak-Connectors

Nachdem Sie den Redtail Speak-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und wählen Sie **Datenconnectors** im linken Navigationsgerät aus.

2. Wählen Sie die **Registerkarte Connectors** aus, und wählen Sie dann den **Redtail Speak-Connector** aus, um die Flyoutseite anzeigen zu können. Auf dieser Seite werden Eigenschaften und Informationen zum Connector angezeigt.

3. Wählen **Sie unter Connectorstatus mit Quelle** den Link **Protokoll** herunterladen aus, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.