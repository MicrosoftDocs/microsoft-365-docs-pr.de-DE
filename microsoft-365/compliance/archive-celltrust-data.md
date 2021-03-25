---
title: Einrichten eines Connectors zum Archivieren von CellTrust-Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von CellTrust-Daten aus Dement in Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren. Nachdem Sie diese Daten archiviert haben, können Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um Daten von Drittanbietern zu verwalten.
ms.openlocfilehash: 855d48303c7c35c32951105799aa117675820420
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164388"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a>Einrichten eines Connectors zum Archivieren von CellTrust-Daten

Verwenden Sie einen Connectors für Denkdaten im Microsoft 365 Compliance Center, um Daten von der CellTrust-Plattform in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Ein CellTrust-Connector, der Elemente aus der Datenquelle eines Drittanbieters erfasst und diese Elemente nach Microsoft 365 importiert, wird von DerEinstreuer mit einem [CellTrust-Connector](https://globanet.com/celltrust/) unterstützt. Der Connector konvertiert den Inhalt von SMS-Nachrichten aus CellTrust-Konten in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem CellTrust-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Kommunikationskonformität anwenden. Die Verwendung eines CellTrust-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den richtlinienkonformen Richtlinien von Behörden und Behörden entspricht.

## <a name="overview-of-archiving-celltrust-data"></a>Übersicht über die Archivierung von CellTrust-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von CellTrust-Daten in Microsoft 365 erläutert.

![Archivierungsworkflow für CellTrust-Daten](../media/CellTrustConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit CellTrust zusammen, um eine CellTrust-Website zu einrichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden CellTrust-Elemente auf die Website "Merge1" kopiert. Der Connector konvertiert auch den Inhalt einer Nachricht in ein E-Mail-Nachrichtenformat.

3. Der cellTrust-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit dem Standort Von Derb zusammen und überträgt die Nachrichten an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Die automatische Benutzerzuordnung als Connector importiert Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *Email-Eigenschaft* des in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschriebenen . In den Benutzerpostfächern wird ein Unterordner im Posteingangsordner **cellTrust** erstellt, und die Nachrichtenelemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der Email-Eigenschaft, in welches Postfach Elemente *importiert werden.* Jedes CellTrust-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Merge1-Konto für Microsoft Connectors. Wenden Sie sich zum Erstellen eines Kontos an [den Kundensupport von Veritas](https://www.veritas.com/content/support/). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den CellTrust-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen) muss der Rolle Postfachimportexport in Exchange Online zugewiesen sein. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-celltrust-connector"></a>Schritt 1: Einrichten des CellTrust-Connectors

Der erste Schritt besteht im Zugriff auf die **Datenconnectors** im Microsoft 365 Compliance Center und dem Erstellen eines Connectors für CellTrust-Daten.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors** \> **CellTrust**.

2. Klicken Sie auf der **Seite CellTrust-Produktbeschreibung** auf **Connector hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-celltrust-connector-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des CellTrust-Connectors auf dem Standort "Merge1"

Der zweite Schritt besteht in der Konfiguration des CellTrust-Connectors auf dem Standort "Merge1". Informationen zum Konfigurieren des CellTrust-Connectors finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf).

Nachdem Sie auf **& Beenden** klicken, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und den im Microsoft 365 Compliance Center eingerichteten Connector zu vervollständigen:

1. Aktivieren Sie auf der Seite **CellTrust-Benutzer zu Microsoft 365-Benutzern** zuordnen die automatische Benutzerzuordnung. Die CellTrust-Elemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen  Sie Ihre Einstellungen, und wechseln Sie zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-celltrust-connector"></a>Schritt 4: Überwachen des CellTrust-Connectors

Nachdem Sie den CellTrust-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie **auf die** Registerkarte Connectors, und wählen Sie dann den **CellTrust-Connector** aus, um die Flyoutseite mit den Eigenschaften und Informationen zum Connector angezeigt zu werden.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.