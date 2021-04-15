---
title: Einrichten eines Connectors zum Archivieren von Cisco Jabber auf PostgreSQL-Daten in Microsoft 365
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
description: Erfahren Sie, wie Sie einen Connector im Microsoft 365 Compliance Center einrichten und verwenden, um Daten aus Cisco Jabber auf PostgreSQL in Microsoft 365 zu importieren und zu archivieren.
ms.openlocfilehash: 47cd3c7e9d3717426fbcf43bf1b0df16bbe2cf80
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51767097"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-postgresql-data-preview"></a>Einrichten eines Connectors zum Archivieren von Cisco Jabber auf PostgreSQL-Daten (Vorschau)

Verwenden Sie einen Connectors für Denkdaten im Microsoft 365 Compliance Center, um Daten von der Cisco Jabber-Plattform in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Ein Cisco [Jabber on PostgreSQL-Connector,](https://www.veritas.com/insights/merge1/jabber) der so konfiguriert ist, dass Elemente aus der Datenquelle eines Drittanbieters (regelmäßig) erfasst und in Microsoft 365 importiert werden. Der Connector konvertiert inhalte wie Nachrichten, Chats und freigegebene Inhalte von Cisco Jabber auf PostgreSQL in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem Cisco Jabber on PostgreSQL-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anwenden. Die Verwendung eines Cisco Jabber on PostgreSQL-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den richtlinienkonformen Richtlinien von Behörden und Behörden entspricht.

## <a name="overview-of-archiving-cisco-jabber-on-postgresql-data"></a>Übersicht über die Archivierung von Cisco Jabber auf PostgreSQL-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der Cisco Jabber on PostgreSQL-Daten in Microsoft 365 erläutert.

![Archivierungsworkflow für Cisco Jabber für PostgreSQL-Daten](../media/CiscoJabberonPostgreSQLConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Cisco Jabber auf PostgreSQL zusammen, um ein Cisco Jabber auf der PostgreSQL-Website zu einrichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden Cisco Jabber auf PostgreSQL-Elemente auf die Website "Veritas Merge1" kopiert. Der Connector konvertiert außerdem Cisco Jabber für PostgreSQL-Elemente in ein E-Mail-Nachrichtenformat.

3. Der Cisco Jabber on PostgreSQL-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Website "Veritas Merge1" her und überträgt die Jabber-Inhalte an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung, wie in [Schritt 3 beschrieben.](#step-3-map-users-and-complete-the-connector-setup) In den Benutzerpostfächern wird ein Unterordner im Posteingangsordner mit dem Namen **Cisco Jabber auf PostgreSQL** erstellt, und Elemente werden in diesen Ordner importiert. Der Connector verwendet dazu den Wert der *Email-Eigenschaft.* Jedes Jabber-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Merge1-Konto für Microsoft Connectors. Wenden Sie sich dazu an [den Kundensupport von Veritas.](https://www.veritas.com/content/support/en_US) Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den Cisco Jabber on PostgreSQL-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen hat), muss der Rolle Postfachimportexport in Exchange Online zugewiesen sein. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Diese Rolle ist standardmäßig keinem Rollengruppen in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-on-postgresql-connector"></a>Schritt 1: Einrichten des Cisco Jabber auf dem PostgreSQL-Connector

Der erste Schritt besteht im Zugriff auf die Seite **Datenconnectors** im Microsoft 365 Compliance Center und dem Erstellen eines Connectors für Jabber-Daten.

1. Wechseln Sie <https://compliance.microsoft.com> zu, und klicken Sie dann auf  &gt; **Datenconnectors Cisco Jabber auf PostgreSQL**.

2. Klicken Sie **auf der Seite Cisco Jabber on PostgreSQL** product description auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-cisco-jabber-on-postgresql-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren von Cisco Jabber auf PostgreSQL auf der Website "Veritas Merge1"

Der zweite Schritt besteht in der Konfiguration des Cisco Jabber on PostgreSQL-Connectors auf dem Standort "Veritas Merge1". Informationen zum Konfigurieren des Cisco Jabber on PostgreSQL-Connectors finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf).

Nachdem Sie auf **& Beenden** klicken, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der **Seite Cisco Jabber on PostgreSQL users to Microsoft 365 users** die automatische Benutzerzuordnung. Die Cisco Jabber on PostgreSQL-Elemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen Sie  Ihre Einstellungen, und wechseln Sie dann zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-cisco-jabber-on-postgresql-connector"></a>Schritt 4: Überwachen des Cisco Jabber on PostgreSQL-Connectors

Nachdem Sie den Cisco Jabber on PostgreSQL-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie <https://compliance.microsoft.com/> zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie **auf die** Registerkarte Connectors, und wählen Sie dann den Cisco Jabber on **PostgreSQL-Connector** aus, um die Flyoutseite mit den Eigenschaften und Informationen zum Connector anzeigen zu können.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt, aber die Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
