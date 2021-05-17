---
title: Einrichten eines Connectors zum Archivieren von Daten aus MS-SQL-Datenbank
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Daten aus MS-SQL-Datenbank. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365. Nachdem Sie diese Daten archiviert haben, können Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um Daten von Drittanbietern zu verwalten.
ms.openlocfilehash: 494e91085494ba027a80480faba3cfb189cbd928
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164215"
---
# <a name="set-up-a-connector-to-archive-data-from-ms-sql-database"></a>Einrichten eines Connectors zum Archivieren von Daten aus MS-SQL-Datenbank

Verwenden Sie einen Connectors vom Microsoft 365, um Daten aus MS SQL-Datenbank in Benutzerpostfächer in Ihrer Organisation Microsoft 365 archivieren. Mit Einem Ms-SQL-Datenbank-Importerconnector, der so konfiguriert ist, dass Elemente aus einer Datenbank mithilfe einer XML-Konfigurationsdatei erfasst und in Microsoft 365. Der Connector konvertiert Inhalte aus MS-SQL-Datenbank in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in Benutzerpostfächer in Microsoft 365.

Nachdem Inhalte von MS SQL-Datenbank in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anwenden. Die Verwendung eines MS SQL-Datenbank zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation mit den richtlinienkonformen Richtlinien von Behörden und Behörden konform ist.

## <a name="overview-of-archiving-the-ms-sql-data"></a>Übersicht über die Archivierung der MS-SQL Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von MS-SQL In-Microsoft 365.

![Archivierungsworkflow für MS SQL Daten](../media/MSSQLDatabaseConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit einem MS-SQL-Datenbank zusammen, um eine MS-SQL-Datenbank einrichten und konfigurieren.

2. Einmal alle 24 Stunden werden SQL-Datenbank Elemente von MS auf die Website "Merge1" von "Veritas Merge1" kopiert. Der Connector konvertiert diesen Inhalt auch in ein E-Mail-Nachrichtenformat.

3. Der ms SQL-Datenbank-Importerconnector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit dem Standort Von -201 her und überträgt die Nachrichten an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten MS-SQL-Datenbank-Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung, wie in [Schritt 3 beschrieben.](#step-3-map-users-and-complete-the-connector-setup) In den Benutzerpostfächern wird ein Unterordner im Posteingangsordner ms **SQL-Datenbank Importer** erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der Email-Eigenschaft, in welches Postfach Elemente *importiert werden.* Jedes Element aus dem MS-SQL-Datenbank enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für Denkdruck1 für Microsoft Connectors. Wenden Sie sich zum Erstellen eines Kontos an [den Kundensupport von Veritas](https://www.veritas.com/content/support/). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den MS SQL-Datenbank-Importerconnector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen hat), muss der Rolle Postfachimportexport in Exchange Online. Diese Rolle ist erforderlich, um Connectors auf der Seite Datenconnectors im compliance center Microsoft 365 hinzufügen. Diese Rolle ist standardmäßig keinem Rollengruppen in der Exchange Online. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-ms-sql-database-importer-connector"></a>Schritt 1: Einrichten des MS SQL-Datenbank Importerconnector

Der erste Schritt besteht im Zugriff auf die Seite **Datenconnectors** im Microsoft365 Compliance Center und dem Erstellen eines Connectors für die MS-SQL-Datenbank.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie dann auf **Datenconnectors**  >  **MS SQL-Datenbank Importer**.

2. Klicken Sie **auf SQL-Datenbank Seite** Ms SQL-Datenbank Produktbeschreibung auf Neuen Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-ms-sql-database-importer-connector-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des MS SQL-Datenbank Importerconnector auf dem Standort "Merge1"

Der zweite Schritt besteht im Konfigurieren des MS-SQL-Datenbank-Importerconnector auf dem Merge1-Standort. Informationen zum Konfigurieren des MS-SQL-Datenbank-Importers finden Sie unter [Merge1-Benutzerhandbuch für Drittanbieterconnectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20MS%20SQL%20Database%20Importer%20User%20Guide%20.pdf).

Nachdem Sie auf **Speichern &** Fertig  stellen geklickt haben, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung abzuschließen:

1. Aktivieren Sie auf der Seite SQL-Datenbank **Benutzer** Microsoft 365 Benutzer zuordnen die automatische Benutzerzuordnung. Die MS SQL-Datenbank enthält eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365 zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen  Sie Ihre Einstellungen, und wechseln Sie zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-ms-sql-database-importer-connector"></a>Schritt 4: Überwachen des MS-SQL-Datenbank-Importerconnector

Nachdem Sie den MS-SQL-Datenbank-Importerconnector erstellt haben, können Sie den Connectorstatus im Microsoft 365 anzeigen.

1. Wechseln Sie <https://compliance.microsoft.com/> zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie **auf die** Registerkarte Connectors, und wählen Sie dann den Ms **SQL-Datenbank-Importer-Connector** aus, um die Flyoutseite mit den Eigenschaften und Informationen zum Connector angezeigt zu werden. 

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.