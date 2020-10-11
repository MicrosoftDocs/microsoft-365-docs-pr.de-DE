---
title: Einrichten eines Connectors zum Archivieren von Zoom Besprechungsdaten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Daten aus Globanet-Zoom Besprechungen in Microsoft 365 einrichten. Auf diese Weise können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren, damit Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten der drittanbieterdaten Ihrer Organisation verwenden können.
ms.openlocfilehash: ef153ec0a14a257f1f46b011e4c15d2b3b704ed3
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408943"
---
# <a name="set-up-a-connector-to-archive-zoom-meetings-data"></a>Einrichten eines Connectors zum Archivieren von Zoom Besprechungsdaten

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center, um Daten aus Zoom Besprechungen in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Globanet bietet einen [Zoom-Besprechungs](https://globanet.com/zoom/) -Konnektor, der so konfiguriert ist, dass er Elemente aus der Drittanbieter-Datenquelle (regelmäßig) erfasst und diese Elemente nach Microsoft 365 importiert. Der Connector wandelt den Inhalt der Besprechungen (einschließlich Chats, aufgezeichneten Dateien und Metadaten) aus dem Konto "Zoom Besprechungen" in ein e-Mail-Nachrichtenformat um und importiert diese Elemente dann in Benutzerpostfächer in Microsoft 365.

Nachdem Zoom-Besprechungsdaten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen sowie die Kompatibilität der Kommunikation anwenden. Die Verwendung eines Zoom-Besprechungs-Konnektors zum Importieren und Archivieren von Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="overview-of-archiving-zoom-meetings-data"></a>Übersicht über das Archivieren von Zoom Besprechungsdaten

In der folgenden Übersicht wird erläutert, wie Sie einen Connector zum Archivieren von Zoom Besprechungsdaten in Microsoft 365 verwenden.

![Workflow "Zoom Meetings-Archivierung"](../media/ZoomMeetingsConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Zoom Besprechungen zusammen, um eine Zoom-Besprechungswebsite einzurichten und zu konfigurieren.

2. Alle 24 Stunden werden Besprechungselemente aus Zoom Besprechungen auf die Globanet Merge1-Website kopiert. Der Connector wandelt auch den Inhalt der Besprechungen in ein e-Mail-Nachrichtenformat um.

3. Der Zoom-Besprechungs-Konnektor, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit dem Globanet Merge1 her und überträgt die Besprechungsnachrichten an einen sicheren Azure-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Besprechungselemente in die Postfächer bestimmter Benutzer, wobei der Wert der *e-Mail* -Eigenschaft und die automatische Benutzerzuordnung, wie in Schritt 3 beschrieben, verwendet werden. Ein neuer Unterordner im Ordner "Posteingang" mit dem Namen " **Zoom Meetings** " wird in Benutzerpostfächern erstellt, und die Besprechungselemente werden in diesen Ordner importiert. Der Connector verwendet den Wert der *Email* -Eigenschaft. Jedes Besprechungselement enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Teilnehmers der Besprechung aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Erstellen Sie ein Globanet-Merge1-Konto für Microsoft-Connectors. Wenden Sie sich dazu an den [Globanet-Kunden Support](https://globanet.com/ms-connectors-contact). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Rufen Sie den Benutzernamen und das Kennwort für das Zoom Business-oder Zoom Enterprise-Konto Ihrer Organisation ab. Wenn Sie den Zoom Besprechungen-Konnektor konfigurieren, müssen Sie sich in Schritt 2 bei diesem Konto anmelden.

- Erstellen Sie die folgenden Anwendungen auf dem [Zoom-Marktplatz](https://marketplace.zoom.us):

  - OAuth-Anwendung

  - JWT-Anwendung

  Nachdem Sie diese Anwendungen erstellt haben, generiert die Zoom Plattform eine Reihe eindeutiger Anmeldeinformationen, die zum Generieren der Token verwendet werden. Diese Token werden verwendet, um den Connector zu authentifizieren, wenn er eine Verbindung mit Ihrem zoomkonto herstellt und Elemente an die Merge1-Website kopiert. Sie werden diese Token verwenden, wenn Sie den Zoom-Konnektor in Schritt 2 konfigurieren.

  Eine Schritt-für-Schritt-Anleitung zum Erstellen der OAuth-und JWT-Anwendungen finden Sie unter [Merge1-Benutzerhandbuch für Drittanbieter-Konnektoren](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

- Der Benutzer, der den Zoom Besprechungen-Konnektor in Schritt 1 erstellt (und in Schritt 3 vervollständigt wird), muss der Rolle "Post Fach Import/-Export" in Exchange Online zugewiesen sein. Diese Rolle ist für das Hinzufügen von Connectors auf der Seite **Daten Konnektoren** im Microsoft 365 Compliance Center erforderlich. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-zoom-meetings-connector"></a>Schritt 1: Einrichten des Zoom Besprechungen-Konnektors

Der erste Schritt besteht darin, auf die **Daten-Konnektoren** im Microsoft 365 Compliance Center zuzugreifen und einen Zoom-Besprechungs-Konnektor zu erstellen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **Daten Verbinder**-  >  **Zoom Besprechungen**.

2. Klicken Sie auf der Seite **Zoom Besprechungen** Produktbeschreibung auf **Connector hinzufügen**.

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-zoom-meetings-connector"></a>Schritt 2: Konfigurieren des Zoom Besprechung-Konnektors

Der zweite Schritt besteht darin, den Zoom Besprechungen-Konnektor auf der Merge1-Website zu konfigurieren. Weitere Informationen zum Konfigurieren des Zoom Besprechung-Konnektors auf der Globanet Merge1-Website finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Zoom%20Meetings%20User%20Guide%20.pdf).

Nachdem Sie auf **& fertig stellen**klicken, werden Sie zurück zum Microsoft 365 Compliance Center auf die Seite **Benutzerzuordnung** im Connector-Assistenten umgeleitet.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

1. Aktivieren Sie auf der Seite **externe Benutzer auf Microsoft 365-Benutzer zuordnen** die Option Automatische Benutzerzuordnung.

   Zu Zoom-Besprechungselementen gehört eine Eigenschaft mit dem Namen " *e-Mail* ", die e-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf der Seite **Administrator Zustimmung** auf **Zustimmung erteilen**. Sie werden zur Microsoft-Website umgeleitet. Klicken Sie auf **akzeptieren** , um die Zustimmung zu erteilen.
  
   Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um die Zustimmung des Administrators bereitzustellen, müssen Sie mit den Anmeldeinformationen eines globalen Administrators von Microsoft 365 angemeldet sein und dann die Zustimmungs Anforderung annehmen. Wenn Sie nicht als globaler Administrator angemeldet sind, können Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) wechseln und sich mit globalen Administratoranmeldeinformationen anmelden, um die Anforderung zu akzeptieren.

3. Klicken Sie auf **weiter**, überprüfen Sie Ihre Einstellungen, und wechseln Sie zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-zoom-meetings-connector"></a>Schritt 4: Überwachen des Zoom Besprechungen-Konnektors

Nachdem Sie den Zoom Besprechungen-Konnektor erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie dann den **Zoom Besprechungen** -Konnektor aus, um die Flyout-Seite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

3. Klicken Sie unter **Connectorstatus with Source**auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen zu den Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Zurzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt zur Verfügung stehen.

- Damit der Zoom-Besprechungs-Konnektor funktioniert, müssen Sie Aufzeichnungen beim Einrichten von Zoom Besprechungen aktivieren.
