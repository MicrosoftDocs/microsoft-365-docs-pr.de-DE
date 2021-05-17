---
title: Einrichten eines Connectors zum Archivieren von Webseitendaten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Webseitenerfassungsdaten aus DerEntwebseite in Microsoft 365. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: d37ed5fdb6995fa9333181d254b1fccd2b08b43b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163849"
---
# <a name="set-up-a-connector-to-archive-webpage-data"></a>Einrichten eines Connectors zum Archivieren von Webseitendaten

Verwenden Sie einen Connectors vom Microsoft 365, um Daten von Webseiten in Benutzerpostfächer in Ihrer Organisation zu importieren und Microsoft 365 archivieren. Mit Einem [Verbinder für die](https://globanet.com/webpage-capture) Webseitenerfassung wird ein Link zu bestimmten Webseiten (und Links auf diesen Seiten) auf einer bestimmten Website oder einer gesamten Domäne erfasst. Der Connector konvertiert den Webseiteninhalt in ein PDF-, PNG- oder benutzerdefiniertes Dateiformat, fügt die konvertierten Dateien dann an eine E-Mail-Nachricht an und importiert diese E-Mail-Elemente dann in Benutzerpostfächer in Microsoft 365.

Nachdem Webseiteninhalte in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie z. B. Litigation Hold, eDiscovery und Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen anwenden. Die Verwendung eines Verbinders für die Webseitenerfassung zum Importieren und Archivieren von Daten in Microsoft 365 Kann Dazu beitragen, dass Ihre Organisation den richtlinienkonformen Richtlinien von Behörden und Behörden entspricht.

## <a name="overview-of-archiving-webpage-data"></a>Übersicht über archivierungswebdaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Webseiteninhalten in Microsoft 365.

![Archivierungsworkflow für Webseitendaten](../media/WebPageCaptureConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit der Webseitenquelle zusammen, um eine Website für die Webseitenerfassung zu einrichten und zu konfigurieren.

2. Einmal alle 24 Stunden werden die Elemente der Webseitenquellen auf die Website "Merge1" kopiert. Der Connector konvertiert außerdem den Inhalt einer Webseite und fügt ihn an eine E-Mail-Nachricht an.

3. Der im Microsoft 365 Compliance Center erstellte Webseitenerfassungsconnector stellt täglich eine Verbindung mit der Website von Veritas Merge1 her und überträgt die Webseitenelemente an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Webseitenelemente mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung in die Postfächer bestimmter Benutzer, wie in [Schritt 3 beschrieben.](#step-3-map-users-and-complete-the-connector-setup) In den Benutzerpostfächern wird  ein Unterordner im Posteingangsordner "Webseitenerfassung" erstellt, und die Webseitenelemente werden in diesen Ordner importiert. Der Connector verwendet dazu den Wert der *Email-Eigenschaft.* Jedes Webseitenelement enthält diese Eigenschaft, die mit den E-Mail-Adressen aufgefüllt wird, die beim Konfigurieren des Webseitenaufnahmeconnector in [Schritt 2 bereitgestellt werden.](#step-2-configure-the-webpage-capture-connector-on-the-veritas-merge1-site)

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für Denkdruck1 für Microsoft Connectors. Wenden Sie sich zum Erstellen dieses Kontos an [den Kundensupport von Veritas](https://www.veritas.com/content/support/). Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Sie müssen mit der Unterstützung von Veritas zusammenarbeiten, um ein benutzerdefiniertes Dateiformat zum Konvertieren der Webseitenelemente in ein benutzerdefiniertes Dateiformat zu erstellen. Weitere Informationen finden Sie im [Benutzerhandbuch für Merge1-Connectors von Drittanbietern.](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf)

- Der Benutzer, der den Webseitenaufnahmeconnector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen) muss der Rolle "Postfachimportexport" in Exchange Online. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im compliance center Microsoft 365 hinzufügen. Diese Rolle ist standardmäßig nicht einer Rollengruppe in der Exchange Online. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-webpage-capture-connector"></a>Schritt 1: Einrichten des Webseitenaufnahmeconnector

Der erste Schritt besteht im Zugriff auf die **Datenconnectors** und dem Erstellen eines Connectors für Webseiten-Quelldaten.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors**  >  **Webseitenerfassung**.

2. Klicken Sie **auf der Seite** Webseitenerfassungsproduktbeschreibung auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-webpage-capture-connector-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des Verbinders für die Webseitenerfassung auf der Website "Merge1"

Der zweite Schritt besteht in der Konfiguration des Verbinders für die Webseitenerfassung auf der Website "Merge1" von "Veritas Merge1". Informationen zum Konfigurieren des Verbinders für die Webseitenerfassung finden Sie unter [Merge1-Benutzerhandbuch für Drittanbieterconnectors](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf).

Nachdem Sie auf **Speichern &** Fertig  stellen geklickt haben, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der Seite Benutzer für **Benutzer Microsoft 365** Webseite zuordnen die automatische Benutzerzuordnung. Die Webseitenerfassungselemente enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365 zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen  Sie Ihre Einstellungen, und wechseln Sie zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-webpage-capture-connector"></a>Schritt 4: Überwachen des Webseitenaufnahmeconnector

Nachdem Sie den Verbinder für die Webseitenerfassung erstellt haben, können Sie den Connectorstatus im Microsoft 365 anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie auf **die Registerkarte** Connectors, und wählen Sie dann den **Webseitenaufnahmeconnector** aus, um die Flyoutseite anzuzeigen. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.