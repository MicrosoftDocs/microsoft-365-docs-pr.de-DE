---
title: Einrichten eines Connectors zum Archivieren von Slack eDiscovery-Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Daten aus Der Kugellack eDiscovery in Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren. Nachdem Sie diese Daten archiviert haben, können Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um Daten von Drittanbietern zu verwalten.
ms.openlocfilehash: a5273082ba2f88cda8c323f47aec40fed31455d2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925097"
---
# <a name="set-up-a-connector-to-archive-slack-ediscovery-data"></a>Einrichten eines Connectors zum Archivieren von Slack eDiscovery-Daten

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center, um Drittanbieterdaten aus sozialen Medien, Chatnachrichten und Plattformen für die Dokumentzusammenarbeit in Postfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Das Programm Bietet einen [Slack-Connector,](https://globanet.com/slack/) der so konfiguriert ist, dass Elemente aus der Datenquelle eines Drittanbieters (regelmäßig) erfasst und anschließend in Microsoft 365 importiert werden. Slack zieht Nachrichten und Dateien aus der Slack-API, konvertiert sie in ein E-Mail-Nachrichtenformat und importiert das Element dann in Benutzerpostfächer.

Nachdem Slack eDiscovery-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. Das Rechtsstreitigkeitensverfahren, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen und die Kommunikationskonformität anwenden. Die Verwendung eines Slack-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den richtlinienkonformen Richtlinien von Behörden und Behörden entspricht.

## <a name="overview-of-archiving-slack-ediscovery-data"></a>Übersicht über die Archivierung von Slack eDiscovery-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der Slack-Informationen in Microsoft 365 erläutert.

![Workflow für die Pufferarchivierung](../media/SlackConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Slack zusammen, um einen Slack-Standort zu einrichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden Chatnachrichten von Slack eDiscovery auf die Website "GlobeNet Merge1" kopiert. Der Connector konvertiert auch den Inhalt einer Chatnachricht in ein E-Mail-Nachrichtenformat.

3. Der Slack eDiscovery-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Website "Globenet Merge1" bereit und überträgt die Chatnachrichten an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Chatnachrichtenelemente mithilfe des Werts der *Email-Eigenschaft* und der automatischen Benutzerzuordnung in die Postfächer bestimmter Benutzer, wie in Schritt 3 beschrieben. In den Benutzerpostfächern wird ein neuer Unterordner im Posteingangsordner mit dem Namen **Slack eDiscovery** erstellt, und die Chatnachrichtenelemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der Email-Eigenschaft, in welches Postfach Elemente *importiert werden.* Jede Chatnachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der Chatnachricht gefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für das Merge1-Konto von "GlobeNet Merge1" für Microsoft-Connectors. Um ein Konto zu erstellen, wenden Sie sich an [den Kundensupport von "Globenet".](https://globanet.com/ms-connectors-contact) Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Rufen Sie den Benutzernamen und das Kennwort für das Slack-Unternehmenskonto Ihrer Organisation ab. Sie müssen sich bei diesem Konto in Schritt 2 anmelden, wenn Sie Slack konfigurieren.

- Der Benutzer, der den Slack eDiscovery-Connector in Schritt 1 erstellt (und ihn in Schritt 3 abgeschlossen hat), muss der Rolle Postfachimportexport in Exchange Online zugewiesen werden. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Diese Rolle ist standardmäßig nicht einer Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-slack-ediscovery-connector"></a>Schritt 1: Einrichten des Slack eDiscovery-Connectors

Der erste Schritt besteht im Zugriff auf die Seite **Datenconnectors** im Microsoft 365 Compliance Center und dem Erstellen eines Connectors für Pufferdaten.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf   >  **Datenconnectors Slack eDiscovery**.

2. Klicken Sie **auf der Seite Produktbeschreibung für Slack eDiscovery** auf **Connector hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-slack-ediscovery"></a>Schritt 2: Konfigurieren von Slack eDiscovery

Der zweite Schritt besteht im Konfigurieren des Slack eDiscovery-Connectors auf dem Merge1-Standort. Weitere Informationen zum Konfigurieren des Slack eDiscovery-Connectors auf der Website von "Globenet Merge1" finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Slack%20eDiscovery%20User%20Guide.pdf).

Nachdem Sie auf **& Beenden** klicken, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

1. Aktivieren Sie auf der Seite Externe **Benutzer zu Microsoft 365-Benutzern** zuordnen die automatische Benutzerzuordnung.

   Slack eDiscovery-Elemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen  Sie Ihre Einstellungen, und wechseln Sie zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-slack-ediscovery-connector"></a>Schritt 4: Überwachen des Slack eDiscovery-Connectors

Nachdem Sie den Slack eDiscovery-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie auf **die** Registerkarte Connectors, und wählen Sie dann **den Slack eDiscovery-Connector** aus, um die Flyoutseite anzeigen zu können. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen zu den Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.