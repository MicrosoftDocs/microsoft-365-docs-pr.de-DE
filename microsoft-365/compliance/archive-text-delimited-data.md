---
title: Einrichten eines Connectors zum Archivieren von texttrennten Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von texttrennten Daten aus DemEnttrennten in Microsoft 365. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365. Nachdem Sie diese Daten archiviert haben, können Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden, um Daten von Drittanbietern zu verwalten.
ms.openlocfilehash: 9a8265766dd08a78c3f218710a3bc4b623f7f670
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163938"
---
# <a name="set-up-a-connector-to-archive-text-delimited-data"></a>Einrichten eines Connectors zum Archivieren von texttrennten Daten

Verwenden Sie einen Connectors vom Microsoft 365, um texttrennte Daten in Benutzerpostfächer in Ihrer Organisation zu importieren Microsoft 365 archivieren. Ein durch [Text](https://globanet.com/text-delimited) getrennter Connector, der so konfiguriert ist, dass Elemente aus einer Datenquelle eines Drittanbieters (regelmäßig) erfasst und in eine Microsoft 365. Der Connector konvertiert Inhalte aus der texttrennten Datenquelle in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem texttrennte Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures anwenden, wie z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen. Die Verwendung eines texttrennten Datenconnector zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation mit den richtlinienkonformen Richtlinien von Behörden und Behörden konform ist.

## <a name="overview-of-archiving-the-text-delimited-data"></a>Übersicht über die Archivierung der texttrennten Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von texttrennten Quellinformationen in Microsoft 365.

![Archivierungsworkflow für texttrennte Daten](../media/TextDelimitedConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit der texttrennten Quelle zusammen, um eine durch Text getrennte Website einrichten und konfigurieren zu können.

2. Einmal alle 24 Stunden werden Chatnachrichten aus der texttrennten Quelle auf die Website "Veritas Merge1" kopiert. Der Connector konvertiert den Inhalt auch in ein E-Mail-Nachrichtenformat.

3. Der texttrennte Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Website von "Veritas Merge1" her und überträgt die Nachrichten an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Nachrichtenelemente mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung in die Postfächer bestimmter Benutzer, wie in Schritt 3 beschrieben. In den Benutzerpostfächern wird ein neuer Unterordner im Posteingangsordner mit dem Namen **Text- Delimited** erstellt, und die Nachrichtenelemente werden in diesen Ordner importiert. Der Connector bestimmt mithilfe des Werts der Email-Eigenschaft, in welches Postfach Elemente *importiert werden.* Jede Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers gefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für Denkdruck1 für Microsoft Connectors. Wenden Sie sich zum Erstellen dieses Kontos an [den Kundensupport von Veritas](https://globanet.com/ms-connectors-contact). Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den texttrennten Connector in Schritt 1 erstellt (und ihn in Schritt 3 abgeschlossen hat), muss der Rolle Postfachimportexport in Exchange Online. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im compliance center Microsoft 365 hinzufügen. Diese Rolle ist standardmäßig nicht einer Rollengruppe in der Exchange Online. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-text-delimited-connector"></a>Schritt 1: Einrichten des durch Text getrennten Connectors

Der erste Schritt besteht  im Zugriff auf die Seite Datenconnectors im Microsoft 365 Compliance Center und dem Erstellen eines Connectors für texttrennte Daten.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors**  >  **Text-Delimited**.

2. Klicken Sie **auf der Seite mit texttrennten** Produktbeschreibungen auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-text-delimited-connector-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des durch Text getrennten Connectors auf der Website "Merge1"

Der zweite Schritt besteht im Konfigurieren des durch Text getrennten Connectors auf der Merge1-Website. Informationen zum Konfigurieren des durch Text getrennten Connectors auf der Website "Merge1" finden Sie unter [Merge1-Benutzerhandbuch](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20text-delimited%20User%20Guide%20.pdf)für Drittanbieterconnectors .

Nachdem Sie auf **Speichern &** Fertig  stellen geklickt haben, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der Seite Externe **Benutzer Microsoft 365 Benutzer zuordnen** die automatische Benutzerzuordnung. Die Text- Getrennte Quellelemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365 zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen Sie  Ihre Einstellungen, und wechseln Sie dann zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-text-delimited-connector"></a>Schritt 4: Überwachen des durch Text getrennten Connectors

Nachdem Sie den Text- Delimited Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie **auf die** Registerkarte Connectors, und wählen Sie dann den **Text-Delimited Connector** aus, um die Flyoutseite anzeigen zu können. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen zu den Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.