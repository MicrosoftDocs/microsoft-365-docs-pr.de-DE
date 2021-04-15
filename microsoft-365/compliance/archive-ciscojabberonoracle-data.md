---
title: Einrichten eines Connectors zum Archivieren von Cisco Jabber auf Oracle-Daten in Microsoft 365
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
description: Erfahren Sie, wie Sie einen Connector im Microsoft 365 Compliance Center einrichten und verwenden, um Daten von Cisco Jabber auf Oracle zu Microsoft 365 zu importieren und zu archivieren.
ms.openlocfilehash: c3a2d64605eb3cda235c73964507a82c940187fe
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2021
ms.locfileid: "51767109"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-on-oracle-data-preview"></a>Einrichten eines Connectors zum Archivieren von Cisco Jabber auf Oracle-Daten (Vorschau)

Verwenden Sie einen Connectors für Denkdaten im Microsoft 365 Compliance Center, um Daten aus der Cisco Jabber on Oracle-Plattform in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Mit Einem Cisco Jabber on Oracle-Connector, der so konfiguriert ist, dass Elemente aus der Datenquelle eines Drittanbieters erfasst werden (regelmäßig) und diese Elemente in Microsoft 365 importiert werden, wird von Denkartikeln ein Cisco [Jabber](https://www.veritas.com/insights/merge1/jabber) on Oracle-Connector zur Verfeinern von Elementen aus der Datenquelle eines Drittanbieters konfiguriert. Der Connector konvertiert die Inhalte wie Dateien und Dateivorgänge, Kommentare und freigegebene Inhalte von Cisco Jabber auf Oracle in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem Cisco Jabber on Oracle-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. Das Rechtsstreitigkeitensverfahren, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anwenden. Die Verwendung eines Cisco Jabber on Oracle-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Behördlichen und behördlichen Richtlinien einhalten kann.

## <a name="overview-of-archiving-cisco-jabber-on-oracle-data"></a>Übersicht über die Archivierung von Cisco Jabber auf Oracle-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der Cisco Jabber on Oracle-Daten in Microsoft 365 erläutert.

![Archivierungsworkflow für Cisco Jabber für Oracle-Daten](../media/CiscoJabberOnOracleConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Cisco Jabber auf Oracle zusammen, um einen Cisco Jabber auf der Oracle-Website zu einrichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden Cisco Jabber auf Oracle-Elemente auf die Website "Veritas Merge1" kopiert. Der Connector konvertiert außerdem Cisco Jabber für Oracle-Elemente in ein E-Mail-Nachrichtenformat.

3. Der Cisco Jabber on Oracle-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Website "Veritas Merge1" her und überträgt die Jabber-Inhalte an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung, wie in [Schritt 3 beschrieben.](#step-3-map-users-and-complete-the-connector-setup) In den Benutzerpostfächern wird ein Unterordner im Posteingangsordner mit dem Namen **Cisco Jabber auf Oracle** erstellt, und Elemente werden in diesen Ordner importiert. Der Connector verwendet dazu den Wert der *Email-Eigenschaft.* Jedes Jabber-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Merge1-Konto für Microsoft Connectors. Wenden Sie sich dazu an [den Kundensupport von Veritas.](https://www.veritas.com/content/support/en_US) Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den Cisco Jabber on Oracle-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen) muss der Rolle Postfachimportexport in Exchange Online zugewiesen sein. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Diese Rolle ist standardmäßig keinem Rollengruppen in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-on-oracle-connector"></a>Schritt 1: Einrichten des Cisco Jabber on Oracle-Connectors

Der erste Schritt besteht im Zugriff auf die Seite **Datenconnectors** im Microsoft 365 Compliance Center und dem Erstellen eines Connectors für Jabber-Daten.

1. Wechseln Sie <https://compliance.microsoft.com> zu, und klicken Sie dann auf   >  **Datenconnectors Cisco Jabber auf Oracle**.

2. Klicken Sie **auf der Seite Cisco Jabber on Oracle** Produktbeschreibung auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-cisco-jabber-on-oracle-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren von Cisco Jabber auf Oracle auf der Website "Veritas Merge1"

Der zweite Schritt besteht in der Konfiguration des Cisco Jabber on Oracle-Connectors auf dem Standort "Veritas Merge1". Informationen zum Konfigurieren des Cisco Jabber on Oracle-Connectors finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20Oracle%20User%20Guide.pdf).

Nachdem Sie auf **& Beenden** klicken, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der **Seite Cisco Jabber on Oracle-Benutzer zu Microsoft 365-Benutzern** zuordnen die automatische Benutzerzuordnung. Die Cisco Jabber on Oracle-Elemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen Sie  Ihre Einstellungen, und wechseln Sie dann zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-cisco-jabber-on-oracle-connector"></a>Schritt 4: Überwachen des Cisco Jabber on Oracle-Connectors

Nachdem Sie den Cisco Jabber on Oracle-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie <https://compliance.microsoft.com/> zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie **auf die** Registerkarte Connectors, und wählen Sie dann den **Cisco Jabber on Oracle-Connector** aus, um die Flyoutseite mit den Eigenschaften und Informationen zum Connector anzeigen zu können.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt, aber die Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.
