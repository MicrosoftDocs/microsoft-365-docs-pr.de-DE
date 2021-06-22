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
description: Erfahren Sie, wie Sie einen Connector in der Microsoft 365 Compliance Center einrichten und verwenden, um Daten von Cisco Jabber auf PostgreSQL zu importieren und zu archivieren, um Microsoft 365.
ms.openlocfilehash: 7fca60df9d2c0378579d7700fb3dae9bbcdf619d
ms.sourcegitcommit: fa9efab24a84f71fec7d001f2ad8949125fa8eee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2021
ms.locfileid: "53054797"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-postgresql-data"></a>Einrichten eines Connectors zum Archivieren von Cisco Jabber auf PostgreSQL-Daten

Verwenden Sie einen Connectors in der Microsoft 365 Compliance Center, um Daten aus der Cisco Jabber-Plattform in Benutzerpostfächer in Ihrer Microsoft 365 Organisation zu importieren und zu archivieren. Stellt einen [Cisco Jabber on PostgreSQL-Connector](https://www.veritas.com/insights/merge1/jabber) bereit, der so konfiguriert ist, dass Elemente aus der Datenquelle eines Drittanbieters (in regelmäßigen Abständen) erfasst und in Microsoft 365 importiert werden. Der Connector konvertiert die Inhalte wie Nachrichten, Chats und freigegebene Inhalte von Cisco Jabber auf PostgreSQL in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in Microsoft 365 in das Postfach des Benutzers.

Nachdem Cisco Jabber auf PostgreSQL-Daten in Benutzerpostfächern gespeichert wurde, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung für juristische Zwecke, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anwenden. Die Verwendung eines Cisco Jabber on PostgreSQL-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Behörden- und gesetzlichen Richtlinien zu halten.

## <a name="overview-of-archiving-cisco-jabber-on-postgresql-data"></a>Übersicht über die Archivierung von Cisco Jabber auf PostgreSQL-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Cisco Jabber auf PostgreSQL-Daten in Microsoft 365 erläutert.

![Archivierungsworkflow für Cisco Jabber auf PostgreSQL-Daten](../media/CiscoJabberonPostgreSQLConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Cisco Jabber auf PostgreSQL zusammen, um einen Cisco Jabber auf der PostgreSQL-Website einzurichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden Cisco Jabber on PostgreSQL-Elemente auf die Website "Merge1" kopiert. Der Connector konvertiert auch Cisco Jabber auf PostgreSQL-Elementen in ein E-Mail-Nachrichtenformat.

3. Der Cisco Jabber on PostgreSQL-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der Website "Merge1" her und überträgt den Jabber-Inhalt an einen sicheren Azure Storage Standort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *E-Mail-Eigenschaft* der automatischen Benutzerzuordnung, wie in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschrieben. Ein Unterordner im Posteingangsordner mit dem Namen **Cisco Jabber auf PostgreSQL** wird in den Benutzerpostfächern erstellt, und Elemente werden in diesen Ordner importiert. Der Connector verwendet dazu den Wert der *Email-Eigenschaft.* Jedes Jabber-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Merge1-Konto für Microsoft-Connectors. Wenden Sie sich hierzu an [den Kundensupport.](https://www.veritas.com/content/support/en_US) Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der in Schritt 1 den Cisco Jabber on PostgreSQL-Connector erstellt (und in Schritt 3 abgeschlossen hat), muss der Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Diese Rolle ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-on-postgresql-connector"></a>Schritt 1: Einrichten des Cisco Jabber on PostgreSQL-Connectors

Der erste Schritt besteht darin, auf die **Seite "Datenkonnektoren"** im Microsoft 365 Compliance Center zuzugreifen und einen Connector für Jabber-Daten zu erstellen.

1. Wechseln Sie zu <https://compliance.microsoft.com> und klicken Sie dann auf **"Datenconnectors** &gt; **Cisco Jabber" auf PostgreSQL**.

2. Klicken Sie auf der **Seite "Cisco Jabber on PostgreSQL** product description" auf **"Connector hinzufügen".**

3. Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **"Weiter".**

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-cisco-jabber-on-postgresql-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des Cisco Jabber auf PostgreSQL auf der Website "Merge1"

Der zweite Schritt besteht darin, den Cisco Jabber on PostgreSQL-Connector auf der Website "Merge1" zu konfigurieren. Informationen zum Konfigurieren des Cisco Jabber on PostgreSQL-Connectors finden Sie im [Benutzerhandbuch für Merge1-Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20PostgreSQL%20User%20Guide.pdf)von Drittanbietern.

Nachdem Sie auf **"Speichern & Fertig stellen"** geklickt haben, wird die **Seite "Benutzerzuordnung"** im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und die Connectoreinrichtung im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der **Seite "Map Cisco Jabber on PostgreSQL users to Microsoft 365 users"** die automatische Benutzerzuordnung. Die Cisco Jabber on PostgreSQL-Elemente enthalten eine Eigenschaft namens *"Email",* die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365 Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf **"Weiter",** überprüfen Sie Ihre Einstellungen, und wechseln Sie dann zur Seite **"Datenconnectors",** um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-cisco-jabber-on-postgresql-connector"></a>Schritt 4: Überwachen des Cisco Jabber on PostgreSQL-Connectors

Nachdem Sie den Cisco Jabber on PostgreSQL-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Navigieren Sie im linken Navigationsbereich zu <https://compliance.microsoft.com/> "Datenconnectors", und klicken Sie auf **"Datenconnectors".**

2. Klicken Sie auf die Registerkarte **"Connectors",** und wählen Sie dann den **Cisco Jabber im PostgreSQL-Connector** aus, um die Flyoutseite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

3. Klicken Sie unter **Connectorstatus mit Quelle** auf den Link **"Protokoll herunterladen",** um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
