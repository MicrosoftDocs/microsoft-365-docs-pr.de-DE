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
description: Administratoren können einen Connector zum Importieren und Archivieren von CellTrust-Daten aus Globanet in Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren. Nach dem Archivieren dieser Daten können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten von drittanbieterdaten verwenden.
ms.openlocfilehash: 990f52eb48fcf031bda3c9f17884ff3d384afc55
ms.sourcegitcommit: 6fc6aaa2b7610e148f41018abd229e3c55b2f3d0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "49620486"
---
# <a name="set-up-a-connector-to-archive-celltrust-data"></a>Einrichten eines Connectors zum Archivieren von CellTrust-Daten

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center, um Daten aus der CellTrust-Plattform in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Globanet stellt einen [CellTrust](https://globanet.com/celltrust/) -Connector bereit, der zum Erfassen von Elementen aus der Drittanbieter-Datenquelle (regelmäßig) konfiguriert ist und diese Elemente in Microsoft 365 importiert. Der Connector wandelt den Inhalt von SMS-Nachrichten aus CellTrust-Konten in ein e-Mail-Nachrichtenformat um und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem CellTrust-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen sowie die Kompatibilität der Kommunikation anwenden. Die Verwendung eines CellTrust-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="overview-of-archiving-celltrust-data"></a>Übersicht über das Archivieren von CellTrust-Daten

In der folgenden Übersicht wird der Vorgang der Verwendung eines Connectors zum Archivieren von CellTrust-Daten in Microsoft 365 erläutert.

![Archivierungs Workflow für CellTrust-Daten](../media/CellTrustConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit CellTrust zusammen, um eine CellTrust-Website einzurichten und zu konfigurieren.

2. Alle 24 Stunden werden CellTrust-Elemente in die Globanet-Merge1-Website kopiert. Der Connector wandelt auch den Inhalt einer Nachricht in ein e-Mail-Nachrichtenformat um.

3. Der CellTrust-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Globanet-Merge1-Website her und überträgt die Nachrichten an einen sicheren Azure-Speicherort in der Microsoft-Cloud.

4. Der automatische Benutzerzuordnung als Connector importiert Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *e-Mail* -Eigenschaft des in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschriebenen. Ein Unterordner im Posteingangsordner mit dem Namen **CellTrust** wird in den Benutzerpostfächern erstellt, und die Nachrichtenelemente werden in diesen Ordner importiert. Der Connector bestimmt anhand des Werts der *Email* -Eigenschaft, in welches Postfach Elemente importiert werden sollen. Jedes CellTrust-Element enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Teilnehmers aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Erstellen Sie ein Merge1-Konto für Microsoft-Connectors. Um ein Konto zu erstellen, wenden Sie sich an den [Globanet-Kunden Support](https://globanet.com/contact-us/). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den CellTrust-Connector in Schritt 1 erstellt (und in Schritt 3 vervollständigt) muss der Rolle "Post Fach Import Export" in Exchange Online zugewiesen sein. Diese Rolle ist für das Hinzufügen von Connectors auf der Seite **Daten Konnektoren** im Microsoft 365 Compliance Center erforderlich. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-celltrust-connector"></a>Schritt 1: Einrichten des CellTrust-Konnektors

Der erste Schritt besteht darin, auf die **Daten Konnektoren** im Microsoft 365 Compliance Center zuzugreifen und einen Connector für CellTrust-Daten zu erstellen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **Daten Konnektoren** \> **CellTrust**.

2. Klicken Sie auf der Seite **CellTrust** -Produktbeschreibung auf **Connector hinzufügen**.

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-celltrust-connector-on-the-globanet-merge1-site"></a>Schritt 2: Konfigurieren des CellTrust-Konnektors auf der Globanet-Merge1-Website

Der zweite Schritt besteht darin, den CellTrust-Connector auf der Globanet-Merge1-Website zu konfigurieren. Informationen zum Konfigurieren des CellTrust-Konnektors finden Sie unter [Merge1 Connector-Benutzerhandbuch für Drittanbieter](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20CellTrust%20User%20Guide%20.pdf).

Nachdem Sie auf **& Ende speichern** klicken, wird die Seite **Benutzerzuordnung** im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und den Connector zu vervollständigen, der im Microsoft 365 Compliance Center eingerichtet wurde:

1. Aktivieren Sie auf der Seite CellTrust-Benutzer auf **Microsoft 365** -Benutzer zuordnen die Option Automatische Benutzerzuordnung. Die CellTrust-Elemente enthalten eine Eigenschaft mit dem Namen " *e-Mail*", die e-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf **weiter**, überprüfen Sie Ihre Einstellungen, und wechseln Sie zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-celltrust-connector"></a>Schritt 4: Überwachen des CellTrust-Connectors

Nachdem Sie den CellTrust-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie dann den **CellTrust** -Konnektor aus, um die Flyout-Seite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

3. Klicken Sie unter **Connectorstatus with Source** auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Zurzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt zur Verfügung stehen.
