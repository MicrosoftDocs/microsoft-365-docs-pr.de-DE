---
title: Einrichten eines Connectors zum Archivieren von XIP-Quelldaten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von XIP-Quelldaten aus Demeni in Microsoft 365. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365. Nachdem Sie diese Daten archiviert haben, können Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um Daten von Drittanbietern zu verwalten.
ms.openlocfilehash: dd0881260b278819d9a2a86d2d43cb22c3b2420a
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163799"
---
# <a name="set-up-a-connector-to-archive-xip-source-data"></a>Einrichten eines Connectors zum Archivieren von XIP-Quelldaten

Verwenden Sie einen Connectors vom Microsoft 365 Zum Importieren und Archivieren von Daten von der XIP-Quellplattform in Benutzerpostfächer in Microsoft 365 Organisation. Mit einem [XIP-Connector,](https://globanet.com/xip/) der die Verwendung einer XIP-Datei zum Importieren von Elementen in die Microsoft 365. Eine XIP-Datei ähnelt einer ZIP-Datei, ermöglicht jedoch die Verwendung einer digitalen Signatur. Die digitale Signatur wird durch den 1.1-Merge von Veritas überprüft, bevor die XIP-Quelldatei extrahiert wird. Der Connector konvertiert den Inhalt aus der XIP-Quelldatei in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem XIP-Quelldaten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen und Kommunikationskonformität anwenden. Die Verwendung eines XIP-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 Kann Dazu beitragen, dass Ihre Organisation die Richtlinien von Behörden und Behörden einhalten kann.

## <a name="overview-of-archiving-the-xip-source-data"></a>Übersicht über die Archivierung der XIP-Quelldaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der XIP-Quelldaten in Microsoft 365.

![Archivierungsworkflow für XIP-Quelldaten](../media/XIPConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit der XIP-Quelle zusammen, um eine XIP-Website zu einrichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden XIP-Quellelemente auf die Website "Merge1" kopiert. Der Connector konvertiert den Inhalt auch in ein E-Mail-Nachrichtenformat.

3. Der XIP-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit dem Standort Von -Merge1 her und überträgt die Nachrichten an einen sicheren Azure Storage in der Microsoft Cloud.

4. Der Connector importiert die konvertierten Nachrichtenelemente mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung in die Postfächer bestimmter Benutzer, wie in [Schritt 3 beschrieben.](#step-3-map-users-and-complete-the-connector-setup) In den Benutzerpostfächern wird ein Unterordner im Posteingangsordner **namens XIP** erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der Email-Eigenschaft, in welches Postfach Elemente *importiert werden.* Jedes Quellelement enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers gefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für Denkdruck1 für Microsoft Connectors. Wenden Sie sich zum Erstellen eines Kontos an [den Kundensupport von Veritas](https://www.veritas.com/content/support/). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den XIP-Connector in Schritt 1 erstellt (und ihn in Schritt 3 abgeschlossen hat), muss der Rolle Postfachimportexport in Exchange Online. Diese Rolle ist erforderlich, um Connectors auf der Seite Datenconnectors im compliance center Microsoft 365 hinzufügen. Diese Rolle ist standardmäßig keinem Rollengruppen in der Exchange Online. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-xip-connector"></a>Schritt 1: Einrichten des XIP-Connectors

Der erste Schritt besteht im Zugriff auf die Seite **Datenconnectors** im Microsoft365 Compliance Center und dem Erstellen eines Connectors für die XIP-Quelldaten.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors** \> **XIP**.

2. Klicken Sie **auf der Seite XIP-Produktbeschreibung** auf Neuen **Connector hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-xip-connector-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des XIP-Connectors auf der Website "Merge1" von "Veritas Merge1"

Der zweite Schritt besteht in der Konfiguration des XIP-Connectors auf dem Merge1-Standort. Informationen zum Konfigurieren des XIP-Connectors finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf).

Nachdem Sie auf **Speichern &** Fertig  stellen geklickt haben, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung abzuschließen:

1. Aktivieren Sie auf der Seite **XIP-Benutzer Microsoft 365 Benutzer** zuordnen die automatische Benutzerzuordnung. Die XIP-Quellelemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365 zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen  Sie Ihre Einstellungen, und wechseln Sie zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-xip-connector"></a>Schritt 4: Überwachen des XIP-Connectors

Nachdem Sie den XIP-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie **auf die** Registerkarte Connectors, und wählen Sie dann den **XIP-Connector** aus, um die Flyoutseite mit den Eigenschaften und Informationen zum Connector anzeigen zu können.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.