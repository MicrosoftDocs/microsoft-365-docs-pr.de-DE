---
title: Einrichten eines Connectors zum Archivieren von Yieldbroker-Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Yieldbroker-Daten aus Dement in Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren. Nachdem Sie diese Daten archiviert haben, können Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um Daten von Drittanbietern zu verwalten.
ms.openlocfilehash: 1f2ca6850057112cc0a97b08811532961a213e89
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163779"
---
# <a name="set-up-a-connector-to-archive-yieldbroker-data"></a>Einrichten eines Connectors zum Archivieren von Yieldbroker-Daten

Verwenden Sie einen Connectors für Denkdaten im Microsoft 365 Compliance Center, um Daten aus dem Yieldbroker in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Mit Einem [Yieldbroker-Connector,](https://globanet.com/yieldbroker/) der für die Erfassung von Elementen aus der Datenquelle eines Drittanbieters und den Import dieser Elemente in Microsoft 365 konfiguriert ist, bietet Ihnen DasEinverleibungsconnector. Der Connector konvertiert den Inhalt aus Yieldbroker in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem Yieldbroker in Benutzerpostfächern gespeichert wurde, können Sie Microsoft 365-Compliancefeatures wie z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anwenden. Die Verwendung eines Yieldbroker-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Richtlinien von Behörden und Behörden einhalten kann.

## <a name="overview-of-archiving-yieldbroker-data"></a>Übersicht über die Archivierung von Yieldbroker-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der Yieldbroker-Daten in Microsoft 365 erläutert.

![Archivierungsworkflow für Yieldbroker-Daten](../media/YieldbrokerConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit dem Yieldbroker zusammen, um eine Yieldbroker-Website zu einrichten und zu konfigurieren.

2. Alle 24 Stunden werden Yieldbroker-Elemente auf die Website "Merge1" kopiert. Der Connector konvertiert den Inhalt auch in ein E-Mail-Nachrichtenformat.

3. Der yieldbroker-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Website "Veritas Merge1" her und überträgt die Nachrichten an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Yieldbroker-Elemente mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung in die Postfächer bestimmter Benutzer, wie in [Schritt 3 beschrieben.](#step-3-map-users-and-complete-the-connector-setup) In den Benutzerpostfächern wird ein Unterordner im Posteingangsordner mit dem Namen **Yieldbroker** erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der Email-Eigenschaft, in welches Postfach Elemente *importiert werden.* Jede Yieldbroker-Eigenschaft enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für Denkdruck1 für Microsoft Connectors. Wenden Sie sich zum Erstellen eines Kontos an [den Kundensupport von Veritas](https://www.veritas.com/content/support/). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den Yieldbroker-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen) muss der Rolle Postfachimportexport in Exchange Online zugewiesen werden. Diese Rolle ist erforderlich, um Connectors auf der Seite Datenconnectors im Microsoft 365 Compliance Center hinzuzufügen. Diese Rolle ist standardmäßig keinem Rollengruppen in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-yieldbroker-connector"></a>Schritt 1: Einrichten des Yieldbroker-Connectors

Der erste Schritt besteht im Zugriff auf die Seite **Datenconnectors** im Microsoft 365 Compliance Center und dem Erstellen eines Connectors für den Yieldbroker.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors** &gt; **Yieldbroker**.

2. Klicken Sie auf der Seite Produktbeschreibung von **Yieldbroker** auf **Neuen Connector hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-yieldbroker-connector-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des Yieldbroker-Connectors auf dem Standort "Merge1"

Der zweite Schritt besteht in der Konfiguration des Yieldbroker-Connectors auf dem Merge1-Standort. Informationen zum Konfigurieren des Yieldbroker finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Yieldbroker%20User%20Guide%20.pdf).

Nachdem Sie auf **& Beenden** klicken, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung abzuschließen:

1. Aktivieren Sie auf der Seite **Yieldbroker-Benutzer zu Microsoft 365-Benutzern** zuordnen die automatische Benutzerzuordnung. Die Yieldbroker-Elemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen  Sie Ihre Einstellungen, und wechseln Sie zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-yieldbroker-connector"></a>Schritt 4: Überwachen des Yieldbroker-Connectors

Nachdem Sie den Yieldbroker-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie **auf die Registerkarte** Connectors, und wählen Sie dann den **Yieldbroker-Connector** aus, um die Flyoutseite mit den Eigenschaften und Informationen zum Connector anzeigen zu können.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.