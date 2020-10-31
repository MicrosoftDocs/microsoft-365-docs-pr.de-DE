---
title: Einrichten eines Connectors zum Archivieren von Cisco Jabber auf MS SQL-Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Cisco Jabber-Daten aus Globanet in Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren. Nach dem Archivieren dieser Daten können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten von drittanbieterdaten verwenden.
ms.openlocfilehash: f20d7827b2ec00fe5c7acc491d7a595d99fe8589
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816608"
---
# <a name="set-up-a-connector-to-archive-cisco-jabber-data"></a>Einrichten eines Connectors zum Archivieren von Cisco Jabber-Daten

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center, um Daten aus der Cisco Jabber-Plattform in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Globanet bietet Ihnen einen [Cisco Jabber](https://globanet.com/jabber/) -Konnektor, der so konfiguriert ist, dass er Elemente aus der MS SQL-Datenbank von Jabber wie 1:1 Chatnachrichten und Gruppenchats erfasst und diese Elemente dann nach Microsoft 365 importiert. Der Connector Ruft Daten aus der MS SQL-Datenbank von Cisco Jabber ab, verarbeitet sie und wandelt die Inhalte aus dem Cisco Jabber-Konto eines Benutzers in ein e-Mail-Nachrichtenformat um und importiert diese Elemente in das Postfach des Benutzers in Microsoft 365.

Nachdem Cisco Jabber-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen sowie die Kompatibilität der Kommunikation anwenden. Die Verwendung eines Cisco Jabber-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="overview-of-archiving-cisco-jabber-data"></a>Übersicht über das Archivieren von Cisco Jabber-Daten

In der folgenden Übersicht wird erläutert, wie Sie einen Connector zum Archivieren von Cisco Jabber-Daten in Microsoft 365 verwenden.

![Archivierungs Workflow für Cisco Jabber-Daten](../media/CiscoJabberonMSSQLConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Cisco zusammen, um einen Cisco jabber in der MS SQL-Datenbank einzurichten und zu konfigurieren.

2. Alle 24 Stunden werden Cisco Jabber-Elemente aus der MS SQL-Datenbank auf die Globanet Merge1-Website kopiert. Der Connector wandelt auch den Inhalt von Chatnachrichten in ein e-Mail-Nachrichtenformat um.

3. Der Cisco Jabber Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Globanet Merge1-Website her und überträgt die Elemente an einen sicheren Azure-Speicherort in der Microsoft-Cloud.

4. Der automatische Benutzerzuordnung als Connector importiert Elemente in die Postfächer bestimmter Benutzer mithilfe des Werts der *e-Mail* -Eigenschaft des in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschriebenen. Ein Unterordner im Posteingangsordner namens " **Cisco Jabber" in MS SQL** wird in den Benutzerpostfächern erstellt, und die Nachrichtenelemente werden in diesen Ordner importiert. Der Connector bestimmt anhand des Werts der *Email* -Eigenschaft, in welches Postfach Elemente importiert werden sollen. Jedes Cisco Jabber-Element enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Teilnehmers aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Erstellen Sie ein Globanet-Merge1-Konto für Microsoft-Connectors. Um dieses Konto zu erstellen, wenden Sie sich an den [Globanet-Kunden Support](https://globanet.com/ms-connectors-contact/). Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Richten Sie eine MS SQL-Datenbank ein, um Jabber-Elemente aus vor dem Erstellen des Connectors in Schritt 1 abzurufen. Sie geben die Verbindungseinstellungen für die MS SQL-Datenbank beim Konfigurieren des Cisco Jabber-Konnektors in Schritt 2 an. Weitere Informationen finden Sie im [Merge1-Benutzerhandbuch für Drittanbieter-Konnektoren](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

- Der Benutzer, der den Cisco Jabber Connector in Schritt 1 erstellt (und in Schritt 3 vervollständigt) muss der Rolle "Post Fach Import Export" in Exchange Online zugewiesen sein. Diese Rolle ist für das Hinzufügen von Connectors auf der Seite **Daten Konnektoren** im Microsoft 365 Compliance Center erforderlich. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-cisco-jabber-connector"></a>Schritt 1: Einrichten des Cisco Jabber-Connectors

Der erste Schritt besteht darin, auf die **Daten Konnektoren** im Microsoft 365 Compliance Center zuzugreifen und einen Connector für Cisco Jabber auf MS SQL-Daten zu erstellen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **Data Connectors**  >  **Cisco jabber in MS SQL** .

2. Klicken Sie auf der Seite **Cisco Jabber auf MS SQL** -Produktbeschreibung auf **Connector hinzufügen** .

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen** .

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **weiter** .

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-cisco-jabber-connector-on-the-globanet-merge1-site"></a>Schritt 2: Konfigurieren des Cisco Jabber-Konnektors auf der Globanet Merge1-Website

Der zweite Schritt besteht darin, den Cisco Jabber auf dem MS SQL-Connector auf der Globanet Merge1-Website zu konfigurieren. Informationen zum Konfigurieren von Cisco Jabber auf MS SQL Connector finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Cisco%20Jabber%20on%20MS%20SQL%20User%20Guide%20.pdf).

Nachdem Sie auf **& Ende speichern** klicken, wird die Seite **Benutzerzuordnung** im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und den Connector zu vervollständigen, der im Microsoft 365 Compliance Center eingerichtet wurde:

1. Aktivieren Sie auf der Seite **Cisco Jabber on MS SQL users to Microsoft 365 users** die automatische Benutzerzuordnung. Der Cisco Jabber auf MS SQL-Elementen enthält eine Eigenschaft mit dem Namen " *e-Mail* ", die e-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf der Seite **Administrator Zustimmung** auf **Zustimmung erteilen** . Sie werden zur Microsoft-Website umgeleitet. Klicken Sie auf **akzeptieren** , um die Zustimmung zu erteilen.

   Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um die Zustimmung des Administrators bereitzustellen, müssen Sie mit den Anmeldeinformationen eines globalen Administrators von Microsoft 365 angemeldet sein und dann die Zustimmungs Anforderung annehmen. Wenn Sie nicht als globaler Administrator angemeldet sind, können Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) wechseln und sich mit globalen Administratoranmeldeinformationen anmelden, um die Anforderung zu akzeptieren.

3. Klicken Sie auf **weiter** , überprüfen Sie Ihre Einstellungen, und wechseln Sie zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-cisco-jabber-connector"></a>Schritt 4: Überwachen des Cisco Jabber-Connectors

Nachdem Sie den Cisco jabber in MS SQL Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie dann **Cisco jabber in MS SQL** Connector aus, um die Flyout-Seite anzuzeigen. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken Sie unter **Connectorstatus with Source** auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Zurzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt zur Verfügung stehen.
