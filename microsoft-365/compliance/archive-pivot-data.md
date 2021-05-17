---
title: Einrichten eines Connectors zum Archivieren von Pivotdaten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Pivot-Daten aus DemEntys in Microsoft 365. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 8e88f5166ebcc4d1285a81e041b6d97be46786e3
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164189"
---
# <a name="set-up-a-connector-to-archive-pivot-data"></a>Einrichten eines Connectors zum Archivieren von Pivotdaten

Verwenden Sie einen Connectors vom Microsoft 365, um Daten von der Pivotplattform in Benutzerpostfächer in Ihrer Organisation Microsoft 365 archivieren. Mit einem Pivotconnector, der so konfiguriert ist, dass Elemente aus der Datenquelle eines Drittanbieters (regelmäßig) erfasst und anschließend importiert werden, wird ein Microsoft 365. [](https://globanet.com/pivot/) Pivot ist eine Instant Messaging-Plattform, die die Zusammenarbeit mit Finanzmarktteilnehmern ermöglicht. Der Connector konvertiert Elemente wie Chatnachrichten aus den Pivotkonten eines Benutzers in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in die Benutzerpostfächer in Microsoft 365.

Nachdem Pivotdaten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen und Kommunikationskonformität anwenden. Die Verwendung eines Pivotconnector zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Richtlinien von Behörden und Behörden einhalten kann.

## <a name="overview-of-archiving-pivot-data"></a>Übersicht über die Archivierung von Pivot-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der Pivotdaten in Microsoft 365.

![Archivierungsworkflow für Pivotdaten](../media/PivotConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Pivot zusammen, um eine Pivot-Quellwebsite zu einrichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden Pivotelemente auf die Website "Merge1" kopiert. Der Connector konvertiert die Pivotelemente auch in ein E-Mail-Nachrichtenformat.

3. Der Pivotconnector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit dem Standort Von Derb zusammen und überträgt die Pivotelemente an einen sicheren Azure Storage in der Microsoft Cloud.

4. Der Connector importiert die Pivot-Elemente mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung in die Postfächer bestimmter Benutzer, wie in [Schritt 3 beschrieben.](#step-3-map-users-and-complete-the-connector-setup) In den Benutzerpostfächern wird ein Unterordner im Posteingangsordner **namens Pivot** erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector verwendet dazu den Wert der *Email-Eigenschaft.* Jedes Pivot-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements gefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für Denkdruck1 für Microsoft Connectors. Wenden Sie sich zum Erstellen dieses Kontos an [den Kundensupport von Veritas](https://www.veritas.com/content/support/). Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den Pivotconnector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen) muss der Rolle Postfachimportexport in der Exchange Online. Diese Rolle ist erforderlich, um Connectors auf der Seite Datenconnectors im compliance center Microsoft 365 hinzufügen. Diese Rolle ist standardmäßig nicht einer Rollengruppe in der Exchange Online. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-pivot-connector"></a>Schritt 1: Einrichten des Pivotconnector

Der erste Schritt besteht im Zugriff auf die Seite **Datenconnectors** im Microsoft Compliance Center und erstellen Sie einen Connector für Pivot-Daten.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors**  >  **Pivot**.

2. Klicken Sie **auf der Seite Pivot-Produktbeschreibung** auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-pivot-connector-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des Pivotconnector auf dem Standort "Merge1"

Der zweite Schritt besteht im Konfigurieren des Pivotconnector auf dem Merge1-Standort. Informationen zum Konfigurieren des Pivotconnectors auf dem Standort "Merge1" finden Sie unter [Merge1-Benutzerhandbuch für Drittanbieterconnectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Pivot%20User%20Guide%20.pdf).

Nachdem Sie auf **Speichern &** Fertig  stellen geklickt haben, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung im Microsoft 356 Compliance Center abzuschließen:

1. Aktivieren Sie auf der Seite Pivotbenutzer **Microsoft 365 Benutzer** zuordnen die automatische Benutzerzuordnung. Die Pivotelemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365 zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen  Sie Ihre Einstellungen, und wechseln Sie zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-pivot-connector"></a>Schritt 4: Überwachen des Pivotconnector

Nachdem Sie den Pivotconnector erstellt haben, können Sie den Connectorstatus im Microsoft 365 anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie auf **die** Registerkarte Connectors, und wählen Sie dann den **Pivotconnector** aus, um die Flyoutseite anzeigen zu können. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.