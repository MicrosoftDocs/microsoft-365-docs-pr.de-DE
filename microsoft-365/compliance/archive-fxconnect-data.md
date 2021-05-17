---
title: Einrichten eines Connectors zum Archivieren von FX-Verbinden in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Daten aus einem Verbinden in Microsoft 365. Mit diesem Connector können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, sodass Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 1efbe8d6d8cecdd8394b565abad4d33c8610398f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164260"
---
# <a name="set-up-a-connector-to-archive-fx-connect-data"></a>Einrichten eines Connectors zum Archivieren von FX-Verbinden Daten

Verwenden Sie einen Connectors vom Microsoft 365-Compliance-Center, um Daten aus der FX Verbinden-Plattform für die Zusammenarbeit in Benutzerpostfächer in Ihrer Organisation Microsoft 365 archivieren. Ein [Fx-Verbinden,](https://globanet.com/fx-connect/) der so konfiguriert ist, dass fx-Verbinden-Elemente erfasst und in Microsoft 365. Der Connector konvertiert den Inhalt aus FX Verbinden, z. B. Handel, Nachrichten und andere Details aus dem FX Verbinden-Konto Ihrer Organisation, in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem fx Verbinden in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365 Compliancefeatures wie z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen und Kommunikationskonformität anwenden. Die Verwendung eines fx Verbinden zum Importieren und Archivieren von Daten in Microsoft 365 Kann Dazu beitragen, dass Ihre Organisation mit den richtlinienkonformen Richtlinien von Behörden und Behörden konform ist.

## <a name="overview-of-archiving-fx-connect-data"></a>Übersicht über die Archivierung von FX-Verbinden Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren der FX-Verbinden in Microsoft 365.

![Archivierungsworkflow für FX-Verbinden Daten](../media/FXConnectConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit FX Verbinden zum Einrichten und Konfigurieren einer FX-Verbinden website.

2. Einmal alle 24 Stunden werden Elemente aus FX-Verbinden-Konten auf die Website "Merge1" von "Veritas Merge1" kopiert. Der Connector konvertiert auch die FX-Verbinden in ein E-Mail-Nachrichtenformat.

3. Der FX Verbinden-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit dem Standort Von Derb zusammen und überträgt die FX Verbinden-Elemente an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *Email-Eigenschaft* der automatischen Benutzerzuordnung, wie in [Schritt 3 beschrieben.](#step-3-map-users-and-complete-the-connector-setup) In den Benutzerpostfächern wird ein **Unterordner** im Posteingangsordner mit dem Namen FX Verbinden erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector verwendet dazu den Wert der *Email-Eigenschaft.* Jedes FX Verbinden-Element enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für Denkdruck1 für Microsoft Connectors.  Wenden Sie sich zum Erstellen eines Kontos an [den Kundensupport von Veritas](https://globanet.com/ms-connectors-contact). Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den FX-Verbinden in Schritt 1 erstellt (und ihn in Schritt 3 abgeschlossen hat), muss der Rolle Postfachimportexport in Exchange Online. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im compliance center Microsoft 365 hinzufügen. Diese Rolle ist standardmäßig nicht einer Rollengruppe in der Exchange Online. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in der Exchange Online. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten [Erstellen](/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-fx-connect-connector"></a>Schritt 1: Einrichten des FX-Verbinden Connectors

Der erste Schritt besteht  im Zugriff auf die Seite Datenconnectors im Microsoft 365 Compliance Center und erstellen Sie einen Connector für FX-Verbinden Daten.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors**  >  **FX Verbinden**.

2. Klicken Sie auf der Verbinden-Produktbeschreibungsseite auf **Connector hinzufügen.** 

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-fx-connect-connector-on-the-veritas-merge1-site"></a>Schritt 2: Konfigurieren des FX-Verbinden auf der Website "Merge1"

Im zweiten Schritt wird der FX-Verbinden auf dem Merge1-Standort konfiguriert. Informationen zum Konfigurieren des FX-Verbinden finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20FX%20Connect%20User%20Guide%20.pdf).

Nachdem Sie auf **Speichern &** Fertig  stellen geklickt haben, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

Führen Sie die folgenden Schritte aus, um Benutzer zu zuordnungen und die Connectoreinrichtung im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der Seite Verbinden **Benutzer Microsoft 365** Die automatische Benutzerzuordnung. Die FX-Verbinden enthalten eine Eigenschaft namens *Email*, die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365 zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen Sie  Ihre Einstellungen, und wechseln Sie dann zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-fx-connect-connector"></a>Schritt 4: Überwachen des FX Verbinden Connector

Nachdem Sie den FX-Verbinden erstellt haben, können Sie den Connectorstatus im Microsoft 365 anzeigen.

1. Wechseln Sie <https://compliance.microsoft.com/> zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie auf **die** Registerkarte Connectors, und wählen Sie dann den **FX-Verbinden** aus, um die Flyoutseite angezeigt zu werden. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.