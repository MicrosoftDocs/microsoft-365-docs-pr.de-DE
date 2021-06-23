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
description: Administratoren können einen Connector einrichten, um XIP-Quelldaten von Microsoft 365 zu importieren und zu archivieren. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren. Nachdem Sie diese Daten archiviert haben, können Sie Compliance-Features wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um Daten von Drittanbietern zu verwalten.
ms.openlocfilehash: a3906d9a79c214ca7cfc25f868c5f24661f40004
ms.sourcegitcommit: 778103d20a2b4c43e524aa436775764d8d8d4c33
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53096636"
---
# <a name="set-up-a-connector-to-archive-xip-source-data"></a>Einrichten eines Connectors zum Archivieren von XIP-Quelldaten

Verwenden Sie einen Connectors in der Microsoft 365 Compliance Center, um Daten von der XIP-Quellplattform in Benutzerpostfächer in Ihrer Microsoft 365 Organisation zu importieren und zu archivieren. Stellt einen [XIP-Connector](https://globanet.com/xip/) bereit, der die Verwendung einer XIP-Datei zum Importieren von Elementen in Microsoft 365 ermöglicht. Eine XIP-Datei ähnelt einer ZIP-Datei, ermöglicht jedoch die Verwendung einer digitalen Signatur. Die digitale Signatur wird von "Merge 1" überprüft, bevor die XIP-Quelldatei extrahiert wird. Der Connector konvertiert den Inhalt aus der XIP-Quelldatei in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in die Benutzerpostfächer in Microsoft 365.

Nachdem XIP-Quelldaten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie Beweissicherung für juristische Zwecke, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Kommunikationscompliance anwenden. Die Verwendung eines XIP-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Ihrer Organisation helfen, die Einhaltung von Behörden- und behördlichen Richtlinien zu halten.

## <a name="overview-of-archiving-the-xip-source-data"></a>Übersicht über die Archivierung der XIP-Quelldaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der XIP-Quelldaten in Microsoft 365 erläutert.

![Archivierungsworkflow für XIP-Quelldaten](../media/XIPConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit der XIP-Quelle zusammen, um eine XIP-Website einzurichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden XIP-Quellelemente auf die Website "Seriendruck1" kopiert. Der Connector konvertiert außerdem den Inhalt in ein E-Mail-Nachrichtenformat.

3. Der XIP-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der Website "Merge1" her und überträgt die Nachrichten an einen sicheren Azure Storage Ort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Nachrichtenelemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *E-Mail-Eigenschaft* der automatischen Benutzerzuordnung, wie in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschrieben. Ein Unterordner im Posteingangsordner mit dem Namen **XIP** wird in den Benutzerpostfächern erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der *E-Mail-Eigenschaft,* in welches Postfach Elemente importiert werden sollen. Jedes Quellelement enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Merge1-Konto für Microsoft-Connectors. Um ein Konto zu erstellen, wenden Sie sich an [den Kundensupport.](https://www.veritas.com/content/support/) Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den XIP-Connector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen hat), muss der Rolle "Postfachimportexport" in Exchange Online zugewiesen werden. Diese Rolle ist erforderlich, um Connectors auf der Seite "Datenconnectors" im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimportexport" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimportexport" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten ["Erstellen von Rollengruppen"](/Exchange/permissions-exo/role-groups#create-role-groups) oder "Ändern von [Rollengruppen"](/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-xip-connector"></a>Schritt 1: Einrichten des XIP-Connectors

Der erste Schritt besteht darin, auf die Seite **"Datenconnectors"** im Microsoft365 Compliance Center zuzugreifen und einen Connector für die XIP-Quelldaten zu erstellen.

1. Wechseln Sie zu [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **"Datenconnectors** \> **XIP".**

2. Klicken  Sie auf der XIP-Produktbeschreibungsseite auf **"Neuen Connector hinzufügen".**

3. Klicken Sie auf der Seite **"Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **"Weiter".**

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-xip-connector-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des XIP-Connectors auf der Merge1-Website

Der zweite Schritt besteht darin, den XIP-Connector auf dem Merge1-Standort zu konfigurieren. Informationen zum Konfigurieren des XIP-Connectors finden Sie im Benutzerhandbuch für [Merge1-Connectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XIP%20User%20Guide%20.pdf)von Drittanbietern.

Nachdem Sie auf **"Speichern & Fertig stellen"** geklickt haben, wird die **Seite "Benutzerzuordnung"** im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und das Connector-Setup abzuschließen:

1. Aktivieren Sie auf der Seite "Zuordnung von **XIP-Benutzern zu Microsoft 365 Benutzern"** die automatische Benutzerzuordnung. Die XIP-Quellelemente enthalten eine Eigenschaft namens *"Email",* die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365 Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf **"Weiter",** überprüfen Sie Ihre Einstellungen, und wechseln Sie zur Seite **"Datenconnectors",** um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-xip-connector"></a>Schritt 4: Überwachen des XIP-Connectors

Nachdem Sie den XIP-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie in [https://compliance.microsoft.com](https://compliance.microsoft.com/) der linken Navigationsleiste zu "Datenconnectors", und klicken Sie auf **"Datenconnectors".**

2. Klicken Sie auf die Registerkarte **Connectors,** und wählen Sie dann den **XIP-Connector** aus, um die Flyoutseite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

3. Klicken Sie unter **Connectorstatus mit Quelle** auf den Link **"Protokoll herunterladen",** um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.