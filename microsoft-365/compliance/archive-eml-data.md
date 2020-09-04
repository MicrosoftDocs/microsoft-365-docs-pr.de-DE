---
title: Einrichten eines Connectors zum Archivieren von eml-Daten in Microsoft 365
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
ROBOTS: NOINDEX, NOFOLLOW
description: Administratoren können einen Connector zum Importieren und Archivieren von eml-Daten aus Globanet in Microsoft 365 einrichten. Auf diese Weise können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren, damit Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten der drittanbieterdaten Ihrer Organisation verwenden können.
ms.openlocfilehash: 9a2b473f258973dcbe9cb0e6a155671c80b1f552
ms.sourcegitcommit: a6625f76e8f19eebd9353ed70c00d32496ec06eb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/03/2020
ms.locfileid: "47362066"
---
# <a name="set-up-a-connector-to-archive-eml-data-preview"></a>Einrichten eines Connectors zum Archivieren von eml-Daten (Vorschau)

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center, um eml-Daten in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. EML ist die Dateierweiterung für eine e-Mail-Nachricht, die in einer Datei gespeichert ist. Der Connector wandelt den Inhalt eines Elements aus dem Quellformat in ein e-Mail-Nachrichtenformat um und importiert dann das Element in ein Benutzerpostfach.

Nachdem EML-Nachrichten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen sowie die Kompatibilität der Kommunikation anwenden. Die Verwendung eines eml-Konnektors zum Importieren und Archivieren von Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="overview-of-archiving-eml-data"></a>Übersicht über das Archivieren von eml-Daten

In der folgenden Übersicht wird der Vorgang der Verwendung eines Connectors zum Archivieren von eml-Daten in Microsoft 365 erläutert.

![Archivierungs Workflow für eml-Daten](../media/EMLConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit der EML-Quelle zusammen, um eine EML-Website einzurichten und zu konfigurieren.

2. Alle 24 Stunden werden Inhaltselemente aus der EML-Quelle auf die Globanet Merge1-Website kopiert. Während dieses Prozesses wird der Inhalt einer EML-Datei in ein e-Mail-Nachrichtenformat konvertiert.

3. Der EML-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Globanet Merge1-Website her und überträgt die Nachrichten an einen sicheren Azure-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Nachrichtenelemente in die Postfächer bestimmter Benutzer, wobei der Wert der *Email* -Eigenschaft des in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschriebenen automatischen Benutzer Zuordnungsprozesses verwendet wird. Während dieses Prozesses wird ein Unterordner im Posteingang-Ordner mit dem Namen **eml**in den Benutzerpostfächern erstellt, und die EML-Elemente werden in diesen Ordner importiert. Der Connector verwendet den Wert der *Email* -Eigenschaft. Jede Nachricht enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Teilnehmers des Inhaltselements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Globanet-Merge1-Konto, indem Sie die allgemeinen Geschäftsbedingungen für einen eml-Konnektor akzeptieren. Wenden Sie sich dazu an den [Globanet-Kunden Support](https://globanet.com/contact-us). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den eml-Konnektor in Schritt 1 erstellt (und in Schritt 3 vervollständigt wird), muss der Rolle "Post Fach Import Export" in Exchange Online zugewiesen sein. Diese Rolle ist für das Hinzufügen von Connectors auf der Seite **Daten Konnektoren** im Microsoft 365 Compliance Center erforderlich. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-an-eml-connector"></a>Schritt 1: Einrichten eines eml-Connectors

Der erste Schritt besteht darin, auf die Seite " **Daten Konnektoren** " im Microsoft 365 Compliance Center zuzugreifen und einen Connector für eml-Daten zu erstellen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **Daten Konnektoren**  >  **eml**.

2. Klicken Sie auf der Seite **eml** -Produktbeschreibung auf **Connector hinzufügen**.

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-eml-connector-on-the-globanet-merge1-site"></a>Schritt 2: Konfigurieren des eml-Konnektors auf der Globanet Merge1-Website

Der zweite Schritt besteht darin, den eml-Konnektor auf der Globanet Merge1-Website zu konfigurieren. Informationen zum Konfigurieren des eml-Konnektors finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20EML%20User%20Guide%20.pdf).

Nachdem Sie auf **& fertig stellen**klicken, werden Sie zum Microsoft 365 Compliance Center auf die Seite **Benutzerzuordnung** des Connector-Assistenten zurückgegeben.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und den Connector zu vervollständigen, der im Microsoft 365 Compliance Center eingerichtet wurde:

1. Aktivieren Sie auf der Seite **externe Benutzer auf Microsoft 365-Benutzer zuordnen** die Option Automatische Benutzerzuordnung. Die EML-Quellelemente enthalten eine Eigenschaft mit dem Namen " *e-Mail*", die e-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die EML-Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf der Seite **Administrator Zustimmung** auf die Schaltfläche **Zustimmung erteilen** . Sie werden zur Microsoft-Website umgeleitet. Klicken Sie auf **akzeptieren** , um die Zustimmung zu erteilen.

   Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um die Zustimmung des Administrators bereitzustellen, müssen Sie mit den Anmeldeinformationen eines globalen Administrators von Microsoft 365 angemeldet sein und dann die Zustimmungs Anforderung annehmen. Wenn Sie nicht als globaler Administrator angemeldet sind, können Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) wechseln und sich mit globalen Administratoranmeldeinformationen anmelden, um die Anforderung zu akzeptieren.

3. Klicken Sie auf **weiter**, überprüfen Sie Ihre Einstellungen, und wechseln Sie dann zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-eml-connector"></a>Schritt 4: Überwachen des eml-Connectors

Nachdem Sie den eml-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie dann den **eml** -Konnektor aus, um die Flyout-Seite mit den Eigenschaften und Informationen zum Connector anzuzeigen.

3. Klicken Sie unter **Connectorstatus with Source**auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen zu den Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Zurzeit wird kein Import von Anlagen unterstützt, die größer als 10 MB sind, aber die Unterstützung größerer Elemente wird zu einem späteren Zeitpunkt zur Verfügung stehen.
