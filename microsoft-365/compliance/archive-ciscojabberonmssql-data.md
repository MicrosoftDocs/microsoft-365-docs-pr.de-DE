---
title: Einrichten eines Connectors zum Archivieren von Cisco Jabber auf MS SQL in Microsoft 365
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
description: Administratoren können einen Connector einrichten, um Cisco Jabber auf MS zu importieren und zu archivieren, SQL daten aus Demente in Microsoft 365 zu importieren und zu archivieren. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren. Nachdem Sie diese Daten archiviert haben, können Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um Daten von Drittanbietern zu verwalten.
ms.openlocfilehash: 01899e4142d6e60fb10a101f7af8e9b4143a38c8
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764301"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-ms-sql-data"></a>Einrichten eines Connectors zum Archivieren von Cisco Jabber auf MS SQL Daten

Verwenden Sie einen Connectors für Denkdaten im Microsoft 365 Compliance Center, um Daten von der Cisco Jabber-Plattform in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Mit Einem [Cisco Jabber-Connector,](https://globanet.com/jabber/) der für die Erfassung von Elementen aus der MS SQL Database von Jabber konfiguriert ist, z. B. 1:1-Chatnachrichten und Gruppenchats, bietet Ihnen Das Unternehmen einen Cisco Jabber-Connector, der für das Erfassen von Elementen aus der MS SQL Database von Jabber konfiguriert ist, z. B. 1:1-Chatnachrichten und Gruppenchats, und diese Elemente dann in Microsoft 365 importieren. Der Connector ruft Daten aus der MS SQL Database von Cisco Jabber ab, verarbeitet sie und konvertiert den Inhalt aus dem Cisco Jabber-Konto eines Benutzers in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem Cisco Jabber-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures anwenden, z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Kommunikationskonformität. Die Verwendung eines Cisco Jabber-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Behördlichen und behördlichen Richtlinien einhalten kann.

## <a name="overview-of-archiving-cisco-jabber-data"></a>Übersicht über die Archivierung von Cisco Jabber-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Cisco Jabber auf MS SQL In Microsoft 365 erläutert.

![Archivierungsworkflow für Cisco Jabber-Daten](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Cisco zusammen, um ein Cisco Jabber auf MS SQL zu konfigurieren.

2. Alle 24 Stunden werden Cisco Jabber-Elemente aus der MS-SQL-Datenbank auf die Website "Veritas Merge1" kopiert. Der Connector konvertiert auch den Inhalt von Chatnachrichten in ein E-Mail-Nachrichtenformat.

3. Der Cisco Jabber-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Website von "Veritas Merge1" her und überträgt die Elemente an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Die automatische Benutzerzuordnung als Connector importiert Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *Email-Eigenschaft* des in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschriebenen . Ein Unterordner im Posteingangsordner mit dem Namen **Cisco Jabber** auf MS SQL wird in den Benutzerpostfächern erstellt, und die Nachrichtenelemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der Email-Eigenschaft, in welches Postfach Elemente *importiert werden.* Jedes Cisco Jabber-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für Denkdruck1 für Microsoft Connectors. Wenden Sie sich zum Erstellen dieses Kontos an [den Kundensupport von Veritas](https://www.veritas.com/content/support/). Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Richten Sie eine MS-SQL-Datenbank ein, aus der Jabber-Elemente abgerufen werden, bevor Sie den Connector in Schritt 1 erstellen. Sie geben die Verbindungseinstellungen für die MS-SQL-Datenbank an, wenn Sie den Cisco Jabber-Connector in Schritt 2 konfigurieren. Weitere Informationen finden Sie im [Benutzerhandbuch für Merge1-Connectors von Drittanbietern.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf)

- Der Benutzer, der den Cisco Jabber-Connector in Schritt 1 erstellt (und ihn in Schritt 3 abgeschlossen hat), muss der Rolle Postfachimportexport in Exchange Online zugewiesen sein. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Diese Rolle ist standardmäßig nicht einer Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-on-ms-sql-connector"></a>Schritt 1: Einrichten des Cisco Jabber on MS SQL Connector

Der erste Schritt besteht im Zugriff auf die **Datenconnectors** im Microsoft 365 Compliance Center und dem Erstellen eines Connectors für Cisco Jabber auf MS SQL Daten.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf   >  **Datenconnectors Cisco Jabber auf MS SQL**.

2. Klicken Sie **auf der Seite Cisco Jabber on MS SQL** Produktbeschreibung auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-cisco-jabber-on-ms-sql-connector-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des Cisco Jabber on MS SQL Connector auf dem Standort "Veritas Merge1"

Der zweite Schritt besteht in der Konfiguration des Cisco Jabber on MS SQL Connector auf dem Standort "Veritas Merge1". Informationen zum Konfigurieren von Cisco Jabber auf MS SQL finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

Nachdem Sie auf **& Beenden** klicken, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und den im Microsoft 365 Compliance Center eingerichteten Connector zu vervollständigen:

1. Aktivieren Sie auf der **Seite Cisco Jabber auf MS SQL Benutzer zu Microsoft 365-Benutzern** zuordnen die automatische Benutzerzuordnung. Die Cisco Jabber on MS SQL enthält eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen  Sie Ihre Einstellungen, und wechseln Sie zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>Schritt 4: Überwachen des Cisco Jabber-Connectors

Nachdem Sie den Cisco Jabber auf MS SQL erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie **auf die** Registerkarte Connectors, und wählen Sie dann **Cisco Jabber auf MS SQL,** um die Flyoutseite zu zeigen. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
