---
title: Einrichten eines Connectors für WebEx-Teams-Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Daten aus dem WebEx Teams-Konnektor von Globanet in Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren, damit Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten der drittanbieterdaten Ihrer Organisation verwenden können.
ms.openlocfilehash: e116b02a53538f7eff4188b670fa6b42b873a9e9
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620221"
---
# <a name="set-up-a-connector-to-archive-webex-teams-data"></a>Einrichten eines Connectors zum Archivieren von WebEx-Teams-Daten

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center, um Daten aus WebEx-Teams in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Globanet bietet einen [WebEx Teams](https://globanet.com/webex-teams/) -Connector, der zum Erfassen von WebEx-Teams-Kommunikations Elementen und zum Importieren dieser Daten in Microsoft 365 konfiguriert ist. Der Connector wandelt Inhalte aus WebEx-Teams, wie 1:1-Chats, Gruppenunterhaltungen, Kanal Unterhaltungen und Anlagen aus dem WebEx Teams Ihres Unternehmens, in ein e-Mail-Nachrichtenformat um und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem die Daten von WebEx Teams in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen sowie die Kompatibilität der Kommunikation anwenden. Die Verwendung eines WebEx Teams-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="overview-of-archiving-webex-teams-data"></a>Übersicht über das Archivieren von WebEx-Teams-Daten

In der folgenden Übersicht wird der Vorgang der Verwendung eines Connectors zum Archivieren von WebEx-Teams-Daten in Microsoft 365 erläutert.

![Archivierungs Workflow für WebEx-Teams-Daten](../media/WebexTeamsConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit WebEx-Teams zusammen, um eine WebEx Teams-Website einzurichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden WebEx Teams-Elemente auf die Globanet Merge1-Website kopiert. Der Connector wandelt auch die WebEx Teams-Elemente in ein e-Mail-Nachrichtenformat um.

3. Der WebEx Teams-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit dem Globanet Merge1 her und überträgt die Produkte von WebEx Teams an einen sicheren Azure-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert Elemente in die Postfächer bestimmter Benutzer, indem er den Wert der *Email* -Eigenschaft der automatischen Benutzerzuordnung wie in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschrieben verwendet. Ein Unterordner im Ordner "Posteingang" mit dem Namen " **WebEx Teams** " wird in den Benutzerpostfächern erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector verwendet den Wert der *Email* -Eigenschaft. Jedes WebEx Teams-Element enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Erstellen Sie ein Globanet-Merge1-Konto für Microsoft-Connectors. Um dieses Konto zu erstellen, wenden Sie sich an den [Globanet-Kunden Support](https://globanet.com/ms-connectors-contact). Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Erstellen Sie eine Anwendung [https://developer.webex.com/](https://developer.webex.com) zum Abrufen von Daten aus Ihrem WebEx Teams-Konto. Eine Schritt-für-Schritt-Anleitung zum Erstellen der Anwendung finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf) .

   Wenn Sie diese Anwendung erstellen, generiert die WebEx-Plattform eine Reihe eindeutiger Anmeldeinformationen. Diese Anmeldeinformationen werden in Schritt 2 verwendet, wenn Sie den WebEx Teams-Connector auf der globalen Merge1-Website konfigurieren.

- Der Benutzer, der den WebEx Teams-Connector in Schritt 1 erstellt (und diesen in Schritt 3 ausführt) muss der Rolle "Post Fach Import Export" in Exchange Online zugewiesen sein. Diese Rolle ist für das Hinzufügen von Connectors auf der Seite **Daten Konnektoren** im Microsoft 365 Compliance Center erforderlich. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-webex-teams-connector"></a>Schritt 1: Einrichten des WebEx Teams-Connectors

Der erste Schritt besteht darin, Zugriff auf die **Daten Konnektoren** zu erhalten und den [WebEx Teams](https://globanet.com/webex-teams/) -Connector einzurichten.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **Daten Konnektoren** für  >  **WebEx Teams**.

2. Klicken Sie auf der Seite Produktbeschreibung für **WebEx-Teams** auf **Connector hinzufügen**.

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-webex-teams-connector-on-the-globanet-merge1-site"></a>Schritt 2: Konfigurieren des WebEx Teams-Connectors auf der Globanet Merge1-Website

Der zweite Schritt besteht darin, den WebEx Teams-Connector auf der Merge1-Website zu konfigurieren. Informationen zum Konfigurieren des WebEx Teams-Connectors finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Webex%20Teams%20User%20Guide%20.pdf).

Nachdem Sie auf **& Ende speichern** klicken, wird die Seite **Benutzerzuordnung** im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und das Connector-Setup im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der Seite **WebEx Teams-Benutzer auf Microsoft 365-Benutzer zuordnen** die Option Automatische Benutzerzuordnung. Die WebEx Teams-Elemente enthalten eine Eigenschaft mit dem Namen " *e-Mail*", die e-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf **weiter**, überprüfen Sie Ihre Einstellungen, und wechseln Sie dann zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-webex-teams-connector"></a>Schritt 4: Überwachen des WebEx Teams-Connectors

Nachdem Sie den WebEx Teams-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie den **WebEx Teams** -Konnektor aus, um die Flyout-Seite anzuzeigen. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken Sie unter **Connectorstatus with Source** auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen zu den Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Zurzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt zur Verfügung stehen.
