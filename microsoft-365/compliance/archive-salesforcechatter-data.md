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
description: Administratoren können einen Connector zum Importieren und Archivieren von Salesforce-chatterdaten von Globanet nach Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren. Nach dem Archivieren dieser Daten können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten von drittanbieterdaten verwenden.
ms.openlocfilehash: 60d86cd01ef8da3a02839d4a3f815be02dc1ee01
ms.sourcegitcommit: a3215cc22faa47e935d22300c481e47ab2680b44
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/21/2020
ms.locfileid: "49722972"
---
# <a name="set-up-a-connector-to-archive-salesforce-chatter-data-preview"></a>Einrichten eines Connectors zum Archivieren von Salesforce Chatter Data (Vorschau)

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center, um Daten aus der Salesforce-Chatter-Plattform in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Globanet bietet einen [Salesforce-Chatter](http://globanet.com/chatter/) -Konnektor, der Elemente aus der Drittanbieter-Datenquelle erfasst und diese Elemente in Microsoft 365 importiert. Der Connector wandelt die Inhalte wie Chats, Anlagen und Beiträge aus Salesforce Chatter in ein e-Mail-Nachrichtenformat um und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem die Daten von Salesforce Chatter in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Kompatibilitätsfeatures wie Beweissicherungsverfahren, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen anwenden. Durch die Verwendung eines Salesforce Chatter Connectors zum Importieren und Archivieren von Daten in Microsoft 365 können Sie Ihrer Organisation dabei helfen, mit behördlichen und behördlichen Richtlinien konform zu bleiben.

## <a name="overview-of-archiving-salesforce-chatter-data"></a>Übersicht über das Archivieren von Salesforce Chatter-Daten

In der folgenden Übersicht wird erläutert, wie Sie einen Connector zum Archivieren der Salesforce-chatterdaten in Microsoft 365 verwenden.

![Archivierungs Workflow für Salesforce Chatter-Daten](../media/SalesforceChatterConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Salesforce Chatter zusammen, um eine Chatter-Website für Salesforce einzurichten und zu konfigurieren.

2. Alle 24 Stunden werden Salesforce-Chatter-Elemente auf die Globanet Merge1-Website kopiert. Der Connector Salesforce auch Chatter-Elemente in einem e-Mail-Nachrichtenformat.

3. Der Salesforce Chatter Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Globanet Merge1-Website her und überträgt die Chatter-Inhalte an einen sicheren Azure-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Elemente in die Postfächer bestimmter Benutzer, wobei der Wert der *Email* -Eigenschaft der automatischen Benutzerzuordnung wie in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschrieben wird. Ein Unterordner im Ordner "Mailbox" namens " **Salesforce Chatter** " wird in den Benutzerpostfächern erstellt, und Elemente werden in diesen Ordner importiert. Der Connector bestimmt anhand des Werts der *Email* -Eigenschaft, in welches Postfach Elemente importiert werden sollen. Jedes Chatter-Element enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Merge1-Konto für Microsoft-Connectors. Um ein Konto zu erstellen, wenden Sie sich an den [Globanet-Kunden Support](https://globanet.com/contact-us/). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Erstellen Sie eine Salesforce-Anwendung, und erwerben Sie ein Token unter [https://salesforce.com](https://salesforce.com) . Sie müssen sich als Administrator beim Salesforce-Konto anmelden und ein persönliches Token des Benutzers zum Importieren von Daten abrufen. Außerdem müssen Auslöser auf der Chatter-Website veröffentlicht werden, um Aktualisierungen, Löschungen und Bearbeitungen zu erfassen. Mit diesen Triggern wird ein Beitrag in einem Kanal erstellt, und Merge1 erfasst die Informationen aus dem Kanal. Eine Schritt-für-Schritt-Anleitung zum Erstellen der Anwendung und zum Abrufen des Tokens finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).

- Der Benutzer, der den Salesforce Chatter Connector in Schritt 1 erstellt (und in Schritt 3 vervollständigt) muss der Rolle "Post Fach Import Export" in Exchange Online zugewiesen sein. Diese Rolle ist für das Hinzufügen von Connectors auf der Seite **Daten Konnektoren** im Microsoft 365 Compliance Center erforderlich. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-salesforce-chatter-connector"></a>Schritt 1: Einrichten des Salesforce Chatter Connectors

Der erste Schritt besteht darin, auf die Seite " **Daten Konnektoren** " im Microsoft 365 Compliance Center zuzugreifen und einen Connector für chatterdaten zu erstellen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **Daten Konnektoren** für  >  **Salesforce Chatter**.

2. Klicken Sie auf der Seite **Salesforce Chatter** -Produktbeschreibung auf **Connector hinzufügen**.

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-salesforce-chatter-on-the-globanet-merge1-site"></a>Schritt 2: Konfigurieren des Salesforce Chatter auf der Globanet Merge1-Website

Der zweite Schritt besteht darin, den Salesforce-Chatter-Konnektor auf der Globanet Merge1-Website zu konfigurieren. Informationen zum Konfigurieren des Salesforce Chatter-Konnektors finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20SalesForce%20Chatter%20User%20Guide%20.pdf).

Nachdem Sie auf **& Ende speichern klicken,** wird die Seite **Benutzerzuordnung** im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und das Connector-Setup im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der Seite " **Salesforce Chatter users to Microsoft 365 users** " die automatische Benutzerzuordnung. Die Salesforce-Chatter-Elemente enthalten eine Eigenschaft mit dem Namen " *e-Mail*", die e-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf **weiter**, überprüfen Sie Ihre Einstellungen, und wechseln Sie dann zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-salesforce-chatter-connector"></a>Schritt 4: Überwachen des Salesforce Chatter-Connectors

Nachdem Sie den Salesforce-Chatter-Konnektor erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und klicken Sie dann auf den **Salesforce Chatter** Connector, um die Flyout-Seite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

3. Klicken Sie unter **Connectorstatus with Source** auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Zurzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt zur Verfügung stehen.
