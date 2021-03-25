---
title: Einrichten eines Connectors zum Archivieren von Jive-Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Jive-Daten aus Demente in Microsoft 365 einrichten. Mit diesem Connector können Sie Daten von Drittanbietern in Microsoft 365 archivieren, damit Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 35e6d8ee75d14943ea07fc1f6bce82f826b91297
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164240"
---
# <a name="set-up-a-connector-to-archive-jive-data"></a>Einrichten eines Connectors zum Archivieren von Jive-Daten

Verwenden Sie einen Connectors für Denkdaten im Microsoft 365 Compliance Center, um Daten von der Plattform für die Zusammenarbeit in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Ein [Jive-Connector,](https://globanet.com/jive/) der so konfiguriert ist, dass Elemente aus der Datenquelle eines Drittanbieters (regelmäßig) erfasst und anschließend in Microsoft 365 importiert werden. Der Connector konvertiert Inhalte wie E-Mail-Nachrichten, Chats und Anlagen aus dem Jive-Konto eines Benutzers in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem Jive-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures anwenden, wie z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Kommunikationskonformität. Die Verwendung eines Jive-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Richtlinien von Behörden und Behörden einhalten kann.

## <a name="overview-of-archiving-jive-data"></a>Übersicht über die Archivierung von Jive-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der Jive-Daten in Microsoft 365 erläutert.

![Archivierungsworkflow für Jive-Daten](../media/JiveConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Jive zusammen, um eine Jive-Website zu einrichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden Elemente aus Jive auf die Website "Veritas Merge1" kopiert. Der Connector konvertiert auch den Inhalt von Jive-Elementen in ein E-Mail-Nachrichtenformat.

3. Der Jive-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Website von Veritas Merge1 her und überträgt den Inhalt an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Elemente mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung in die Postfächer bestimmter Benutzer, wie in [Schritt 3 beschrieben.](#step-3-map-users-and-complete-the-connector-setup) In den Benutzerpostfächern wird ein neuer Unterordner im Posteingangsordner **Jive** erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector verwendet dazu den Wert der *Email-Eigenschaft.* Jedes Jive-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für Denkdruck1 für Microsoft Connectors. Wenden Sie sich zum Erstellen dieses Kontos an [den Kundensupport von Veritas](https://www.veritas.com/content/support/). Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den Jive-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen) muss der Rolle Postfachimportexport in Exchange Online zugewiesen sein. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Diese Rolle ist standardmäßig nicht einer Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-jive-connector"></a>Schritt 1: Einrichten des Jive-Connectors

Im ersten Schritt können Sie auf die Seite **Datenconnectors** im Microsoft 365 Compliance Center zugreifen und einen Connector für Jive-Daten erstellen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors**  >  **Jive**.

2. Klicken Sie **auf der Seite Jive-Produktbeschreibung** auf **Connector hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-jive-connector"></a>Schritt 2: Konfigurieren des Jive-Connectors

Der zweite Schritt besteht im Konfigurieren des Jive-Connectors auf dem Merge1-Standort. Informationen zum Konfigurieren des Jive-Connectors finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Jive%20User%20Guide.pdf).

Nachdem Sie auf **& Beenden** klicken, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der Seite Benutzer **zu Microsoft 365-Benutzern** zuordnen die automatische Benutzerzuordnung. Die Jive-Elemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen  Sie Ihre Einstellungen, und wechseln Sie zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-jive-connector"></a>Schritt 4: Überwachen des Jive-Connectors

Nachdem Sie den Jive-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie auf **die** Registerkarte Connectors, und wählen Sie dann den **Jive-Connector** aus, um die Flyoutseite anzeigen zu können. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen zu den Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.