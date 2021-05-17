---
title: Einrichten eines Connectors für Webex Teams daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Daten aus dem Webex-Teams in Microsoft 365. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 654ca53fd4cd7c6091ff74360545ba335f753ffd
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163899"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Einrichten eines Connectors zum Archivieren von Webex-Teams Daten

Verwenden Sie einen Connectors vom Microsoft 365 Compliance Center, um Daten aus Webex-Teams in Benutzerpostfächer in Ihrer Organisation Microsoft 365 archivieren. Mit Einem [Webex-Teams](https://globanet.com/webex-teams/) wird ein Webex-Verbindungsconnector zur Erfassung von Webex- Teams Kommunikationselementen und zum Importieren in Microsoft 365. Der Connector konvertiert Inhalte aus Webex Teams, z. B. 1:1-Chats, Gruppenunterhaltungen, Kanalunterhaltungen und Anlagen aus dem Webex Teams-Konto Ihrer Organisation in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem Webex Teams in Benutzerpostfächern gespeichert wurde, können Sie Microsoft 365 Compliancefeatures wie z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen und Kommunikationskonformität anwenden. Die Verwendung eines Webex-Teams zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den richtlinienkonformen Richtlinien von Behörden und Behörden entspricht.

## <a name="overview-of-archiving-webex-teams-data"></a>Übersicht über die Archivierung von Webex-Teams Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Webex-Teams In-Microsoft 365.

![Archivierungsworkflow für Webex-Teams Daten](../media/WebexTeamsConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Webex Teams, um eine Webex-Website Teams einrichten und konfigurieren.

2. Einmal alle 24 Stunden werden Webex-Teams Elemente auf die Website "Merge1" von "Veritas Merge1" kopiert. Der Connector konvertiert auch die Webex-Teams in ein E-Mail-Nachrichtenformat.

3. Der Webex-Teams-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit dem Veritas Merge1 her und überträgt die Webex Teams-Elemente an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung, wie in [Schritt 3 beschrieben.](#step-3-map-users-and-complete-the-connector-setup) Ein Unterordner im Posteingangsordner **webex Teams** wird in den Benutzerpostfächern erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector verwendet dazu den Wert der *Email-Eigenschaft.* Jedes Webex-Teams enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für Denkdruck1 für Microsoft Connectors. Wenden Sie sich zum Erstellen dieses Kontos an [den Kundensupport von Veritas](https://globanet.com/ms-connectors-contact). Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Erstellen Sie eine Anwendung [https://developer.webex.com/](https://developer.webex.com) unter, um Daten aus Ihrem Webex-Teams abrufen. Schrittweise Anweisungen zum Erstellen der Anwendung finden Sie unter [Benutzerhandbuch für Merge1-Connectors von Drittanbietern.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf)

   Wenn Sie diese Anwendung erstellen, generiert die Webex-Plattform eine Reihe eindeutiger Anmeldeinformationen. Diese Anmeldeinformationen werden in Schritt 2 verwendet, wenn Sie den Webex-Teams auf der Global Merge1-Website konfigurieren.

- Der Benutzer, der den Webex-Teams-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen) muss der Rolle Postfachimportexport in Exchange Online. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im compliance center Microsoft 365 hinzufügen. Diese Rolle ist standardmäßig nicht einer Rollengruppe in der Exchange Online. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-webex-teams-connector"></a>Schritt 1: Einrichten des Webex Teams Connector

Im ersten Schritt erhalten Sie Zugriff auf die **Datenconnectors** und richten den [Webex-Teams](https://globanet.com/webex-teams/) ein.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf   >  **Datenconnectors Webex Teams**.

2. Klicken Sie **auf Teams Webex-Produktbeschreibung** auf **Connector hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-webex-teams-connector-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des Webex-Teams connectors auf der Website "Merge1" von "Veritas Merge1"

Im zweiten Schritt wird der Webex-Teams auf der Merge1-Website konfiguriert. Informationen zum Konfigurieren des Webex-Teams-Connectors finden Sie unter [Merge1-Benutzerhandbuch für Drittanbieterconnectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).

Nachdem Sie auf **Speichern &** Fertig  stellen geklickt haben, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der Seite Map **Webex Teams Benutzer Microsoft 365** Benutzerseite, um die automatische Benutzerzuordnung zu aktivieren. Die Webex-Teams enthält eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365 zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen Sie  Ihre Einstellungen, und wechseln Sie dann zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-webex-teams-connector"></a>Schritt 4: Überwachen des Webex-Teams Connectors

Nachdem Sie den Webex-Teams erstellt haben, können Sie den Connectorstatus im Microsoft 365 anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie **auf die** Registerkarte Connectors, und wählen Sie dann **den Webex-Teams** aus, um die Flyoutseite angezeigt zu werden. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen zu den Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.