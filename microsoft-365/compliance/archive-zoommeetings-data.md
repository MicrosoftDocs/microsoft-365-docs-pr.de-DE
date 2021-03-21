---
title: Einrichten eines Connectors zum Archivieren von Zoombesprechungsdaten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Daten aus Denanet-Zoombesprechungen in Microsoft 365 einrichten. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, damit Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: a8f6ab0a629054457a3a0dc7cbbe74c051820058
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50923361"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>Einrichten eines Connectors zum Archivieren von Zoombesprechungsdaten

Verwenden Sie im Microsoft 365 Compliance Center einen Globanet-Connector, um Daten aus Zoombesprechungen in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Das Programm Bietet [](https://globanet.com/zoom/) einen Zoombesprechungsconnector, der so konfiguriert ist, dass Elemente aus der Datenquelle eines Drittanbieters (regelmäßig) erfasst und in Microsoft 365 importiert werden. Der Connector konvertiert den Inhalt der Besprechungen (einschließlich Chats, aufgezeichnete Dateien und Metadaten) aus dem Konto "Besprechungen zoomen" in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in Benutzerpostfächer in Microsoft 365.

Nachdem Zoombesprechungsdaten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures anwenden, z. B. Litigation Hold, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungsbezeichnungen sowie Kommunikationskonformität. Die Verwendung eines Zoombesprechungsconnector zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Richtlinien von Behörden und Behörden einhalten kann.

## <a name="overview-of-archiving-zoom-meetings-data"></a>Übersicht über die Archivierung von Zoom-Besprechungsdaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Zoombesprechungsdaten in Microsoft 365 erläutert.

![Zoomen des Archivierungsworkflows für Besprechungen](../media/ZoomMeetingsConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Zoombesprechungen zusammen, um eine Zoombesprechungswebsite einrichten und konfigurieren zu können.

2. Einmal alle 24 Stunden werden Besprechungselemente aus Zoombesprechungen auf die Website "Globenet Merge1" kopiert. Der Connector konvertiert auch den Inhalt der Besprechungen in ein E-Mail-Nachrichtenformat.

3. Der Connector für Zoombesprechungen, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit dem Merge1 von Globanet bereit und überträgt die Besprechungsnachrichten an einen sicheren Azure Storage-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Besprechungselemente mithilfe des Werts der *Email-Eigenschaft* und der automatischen Benutzerzuordnung in die Postfächer bestimmter Benutzer, wie in Schritt 3 beschrieben. In Benutzerpostfächern wird ein neuer Unterordner im Posteingangsordner mit dem Namen **Zoom Besprechungen** erstellt, und die Besprechungselemente werden in diesen Ordner importiert. Der Connector verwendet dazu den Wert der *Email-Eigenschaft.* Jedes Besprechungselement enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der Besprechung gefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Konto für das Merge1-Konto von "GlobeNet Merge1" für Microsoft-Connectors. Wenden Sie sich zum Erstellen dieses Kontos an [den Kundensupport von "Globenet".](https://globanet.com/ms-connectors-contact) Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Rufen Sie den Benutzernamen und das Kennwort für das Zoom Business- oder Zoom Enterprise-Konto Ihrer Organisation ab. Sie müssen sich in Schritt 2 bei diesem Konto anmelden, wenn Sie den Connector für Zoombesprechungen konfigurieren.

- Erstellen Sie die folgenden Anwendungen im [Zoom Marketplace:](https://marketplace.zoom.us)

  - OAuth-Anwendung

  - JWT-Anwendung

  Nachdem Sie diese Anwendungen erstellt haben, generiert die Zoom-Plattform eine Reihe eindeutiger Anmeldeinformationen, die zum Generieren der Token verwendet werden. Diese Token werden verwendet, um den Connector zu authentifizieren, wenn er eine Verbindung mit Ihrem Zoomkonto herstellt und Elemente auf die Merge1-Website kopiert. Sie verwenden diese Token, wenn Sie den Zoomconnector in Schritt 2 konfigurieren.

  Schrittweise Anweisungen zum Erstellen der OAuth- und JWT-Anwendungen finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

- Der Benutzer, der den Zoombesprechungsconnector in Schritt 1 erstellt (und in Schritt 3 abgeschlossen) muss der Rolle Postfachimportexport in Exchange Online zugewiesen sein. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Diese Rolle ist standardmäßig nicht einer Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>Schritt 1: Einrichten des Connectors für Zoombesprechungen

Der erste Schritt besteht im Zugriff auf **die Datenconnectors** im Microsoft 365 Compliance Center und dem Erstellen eines Zoombesprechungsconnectors.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com/) zu, und klicken Sie dann auf **Datenconnectors**  >  **Zoom Besprechungen**.

2. Klicken Sie **auf der** Seite Produktbeschreibung für Zoombesprechungen auf **Connector hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **Weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-zoom-meetings-connector"></a>Schritt 2: Konfigurieren des Connectors für Zoombesprechungen

Der zweite Schritt besteht im Konfigurieren des Zoombesprechungsconnector auf dem Merge1-Standort. Weitere Informationen zum Konfigurieren des Zoombesprechungsconnectors auf der Website "Merge1" finden Sie unter [Merge1-Benutzerhandbuch](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf)für Drittanbieterconnectors .

Nachdem Sie auf **& Beenden** klicken, wird die Seite Benutzerzuordnung im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt. 

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnung von Benutzern und Abschließen der Connectoreinrichtung

1. Aktivieren Sie auf der Seite Externe **Benutzer zu Microsoft 365-Benutzern** zuordnen die automatische Benutzerzuordnung.

   Zoom Besprechungselemente enthalten eine Eigenschaft namens *E-Mail,* die E-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken **Sie auf Weiter,** überprüfen  Sie Ihre Einstellungen, und wechseln Sie zur Seite Datenconnectors, um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>Schritt 4: Überwachen des Connectors für Zoombesprechungen

Nachdem Sie den Connector für Zoombesprechungen erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie auf **die Registerkarte** Connectors, und wählen Sie dann den Connector **für Zoombesprechungen** aus, um die Flyoutseite anzeigen zu können. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken **Sie unter Connectorstatus mit Quelle** auf den Link **Protokoll** herunterladen, um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen zu den Daten, die in die Microsoft Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Derzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt verfügbar sein.

- Damit der Connector für Zoombesprechungen funktioniert, müssen Sie beim Einrichten von Zoombesprechungen Aufzeichnungen aktivieren.