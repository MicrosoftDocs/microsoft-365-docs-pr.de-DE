---
title: Einrichten eines Connectors zum Archivieren von Salesforce Chatter-Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Salesforce -Chatter-Daten aus DerEntraum in Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren. Nachdem Sie diese Daten archiviert haben, können Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um Daten von Drittanbietern zu verwalten.
ms.openlocfilehash: c04dc3026eaa5abb23b332dbae826c052344da31
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164058"
---
# <a name="set-up-a-connector-to-archive-salesforce-chatter-data"></a>Einrichten eines Connectors zum Archivieren von Salesforce Chatter-Daten

Verwenden Sie im Microsoft 365 Compliance Center einen Connectors für Denkvorgang, um Daten aus der Salesforce Chatter-Plattform in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Ein [Salesforce-Chatterconnector,](http://globanet.com/chatter/) der Elemente aus der Datenquelle eines Drittanbieters erfasst und diese Elemente nach Microsoft 365 importiert, wird von Dereinst mit einem Salesforce Chatter-Connector verbunden. Der Connector konvertiert die Inhalte wie Chats, Anlagen und Beiträge aus Salesforce Chatter in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem Salesforce-Chatter-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. Das Aufbewahrungsverfahren für Rechtsstreitigkeiten, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anwenden. Die Verwendung eines Salesforce Chatter-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den richtlinienkonformen Richtlinien von Behörden und Behörden entspricht.

## <a name="overview-of-archiving-salesforce-chatter-data"></a>Übersicht über die Archivierung von Salesforce Chatter-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der Salesforce Chatter-Daten in Microsoft 365 erläutert.

![Archivierungsworkflow für Salesforce Chatter-Daten](../media/SalesforceChatterConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Salesforce Chatter zusammen, um eine Salesforce Chatter-Website zu einrichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden Salesforce Chatter-Elemente auf die Website "Merge1" von "Veritas Merge1" kopiert. Der Connector verwendet auch Salesforce Chatter-Elemente in einem E-Mail-Nachrichtenformat.

3. Der Salesforce Chatter-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Website von Veritas Merge1 her und überträgt die Chatterinhalte an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung, wie in [Schritt 3 beschrieben.](#step-3-map-users-and-complete-the-connector-setup) In den Benutzerpostfächern wird ein Unterordner im Posteingangsordner namens **Salesforce Chatter** erstellt, und Elemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der Email-Eigenschaft, in welches Postfach Elemente *importiert werden.* Jedes Chatter-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements gefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Merge1-Konto für Microsoft Connectors. Wenden Sie sich zum Erstellen eines Kontos an [den Kundensupport von Veritas](https://www.veritas.com/content/support/). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Erstellen Sie eine Salesforce-Anwendung, und erwerben Sie ein Token unter [https://salesforce.com](https://salesforce.com) . Sie müssen sich als Administrator beim Salesforce-Konto anmelden und ein persönliches Benutzertoken zum Importieren von Daten erhalten. Außerdem müssen Trigger auf der Chatter-Website veröffentlicht werden, um Updates, Lösch- und Bearbeitungen zu erfassen. Diese Trigger erstellen einen Beitrag auf einem Kanal, und Merge1 erfasst die Informationen aus dem Kanal. Schrittweise Anweisungen zum Erstellen der Anwendung und zum Erwerben des Tokens finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).

- Der Benutzer, der den Salesforce Chatter-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen) muss der Rolle Postfachimportexport in Exchange Online zugewiesen werden. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keinem Rollengruppen in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-salesforce-chatter-connector"></a>Schritt 1: Einrichten des Salesforce-Chatterconnector

Der erste Schritt besteht im Zugriff auf die Seite **Datenconnectors** im Microsoft 365 Compliance Center und dem Erstellen eines Connectors für Chatterdaten.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors**  >  **Salesforce Chatter**.

2. Klicken Sie **auf der Seite Salesforce Chatter-Produktbeschreibung** auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-salesforce-chatter-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des Salesforce-Chatters auf der Website "Veritas Merge1"

Der zweite Schritt besteht im Konfigurieren des Salesforce-Chatterconnector auf dem Standort "Merge1" von "Merge1". Informationen zum Konfigurieren des Salesforce-Chatterconnectors finden Sie unter [Merge1-Benutzerhandbuch für Drittanbieterconnectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).

Nachdem Sie auf & Beenden  **klicken,** wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der **Seite Salesforce Chatter-Benutzer zu Microsoft 365-Benutzern** zuordnen die automatische Benutzerzuordnung. Die Salesforce Chatter-Elemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen Sie  Ihre Einstellungen, und wechseln Sie dann zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-salesforce-chatter-connector"></a>Schritt 4: Überwachen des Salesforce-Chatterconnector

Nachdem Sie den Salesforce Chatter-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie auf **die Registerkarte** Connectors, und klicken Sie dann auf den **Salesforce Chatter-Connector,** um die Flyoutseite mit den Eigenschaften und Informationen zum Connector zu zeigen.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.