---
title: Einrichten eines Connectors zum Archivieren von "Speak"-Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Daten aus Globanet in Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren. Nach dem Archivieren dieser Daten können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten von drittanbieterdaten verwenden.
ms.openlocfilehash: ee1e5c63d8990d5847241dc0ab4a88ed19e3215f
ms.sourcegitcommit: 36d12e02f6fda199ae7f2fb72fe52d7e2b5b4efd
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/31/2020
ms.locfileid: "49740292"
---
# <a name="set-up-a-connector-to-archive-redtail-speak-data"></a>Einrichten eines Connectors zum Archivieren von druckwort-Daten

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center zum Importieren und Archivieren von Daten aus den in Ihrer Microsoft 365-Organisation geäußerten Benutzerpostfächern. Globanet bietet Ihnen einen [codespeak](https://globanet.com/redtail/) -Konnektor, der so konfiguriert ist, dass er Elemente aus dem SFTP-Server Ihrer Organisation erfasst, auf denen die Elemente von "totail" empfangen werden. Der Connector wandelt die Inhalte aus dem Text in ein e-Mail-Nachrichtenformat um und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem Sie die Daten in Benutzerpostfächern gespeichert haben, können Sie Microsoft 365-Kompatibilitätsfeatures wie Beweissicherungsverfahren, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen anwenden. Die Verwendung eines codekonnektors zum Importieren und Archivieren von Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="overview-of-archiving-the-redtail-speak-data"></a>Übersicht über die Archivierung der codespeak-Daten

In der folgenden Übersicht wird erläutert, wie Sie einen Konnektor verwenden, um die Daten in Microsoft 365 zu archivieren.

![Archivierungs Workflow für codespeak-Daten](../media/RedtailSpeakConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit dem Wort "sprechen", um ein SMTP-Gateway einzurichten und zu konfigurieren, in dem Nachrichten täglich von "pretail" an den SFTP-Server Ihrer Organisation weitergeleitet werden.

2. Einmal alle 24 Stunden werden die Globanet Speak-Elemente auf die Merge1-Website von kopiert. Der Connector wandelt auch die sprechenden Elemente in ein e-Mail-Nachrichtenformat um.

3. Der im Microsoft 365 Compliance Center erstellte Globanet Speak Connector stellt jeden Tag eine Verbindung mit der Merge1-Website von her und überträgt die Nachrichten an einen sicheren Azure-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten "gettail"-Elemente in die Postfächer bestimmter Benutzer, wobei der Wert der *Email* -Eigenschaft der automatischen Benutzerzuordnung wie in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschrieben wird. Ein Unterordner im Posteingangsordner mit dem Namen " **pretail Speak** " wird in den Benutzerpostfächern erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector bestimmt anhand des Werts der *Email* -Eigenschaft, in welches Postfach Elemente importiert werden sollen. Jedes druckbare Speak-Element enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Globanet-Merge1-Konto für Microsoft-Connectors. Um ein Konto zu erstellen, wenden Sie sich an den [Globanet-Kunden Support](https://globanet.com/contact-us/). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- In Schritt 2 müssen Sie den SFTP-Server Ihrer Organisation angeben. Dies ist erforderlich, damit Globanet Merge1 Sie kontaktieren kann, um zum Sammeln von Daten über SFTP zu sprechen.

- Der Benutzer, der in Schritt 1 den codetail Speak Importer-Konnektor erstellt (und in Schritt 3 vervollständigt wird), muss der Rolle "Post Fach Import/-Export" in Exchange Online zugewiesen sein. Diese Rolle ist für das Hinzufügen von Connectors auf der Seite Daten Konnektoren im Microsoft 365 Compliance Center erforderlich. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-redtail-speak-connector"></a>Schritt 1: Einrichten des "More Speak"-Konnektors

Der erste Schritt besteht im Zugriff auf die Seite " **Daten Konnektoren** " im Microsoft 365 Compliance Center und zum Erstellen eines Connectors für die Sprech Daten.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie auf **Data Connectors** &gt; **Speak**.

2. Klicken Sie auf der Seite Produktbeschreibung **sprechen** auf **neuen Connector hinzufügen**.

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-redtail-speak-connector-on-the-globanet-merge1-site"></a>Schritt 2: Konfigurieren des "Globanet Speak"-Konnektors auf der Merge1-Website

Der zweite Schritt besteht darin, den codetail Speak-Connector auf der Merge1-Website zu konfigurieren. Weitere Informationen zum Konfigurieren des Merge1 Speak-Connectors finden Sie unter [Benutzerhandbuch für Drittanbieter-Konnektoren](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Redtail%20Speak%20User%20Guide%20.pdf).

Nachdem Sie auf **& Ende speichern** klicken, wird die Seite **Benutzerzuordnung** im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und das Connector-Setup abzuschließen:

1. Aktivieren Sie auf der Seite **Karte "Benutzer zu Microsoft 365** -Benutzer sprechen" die automatische Benutzerzuordnung. Das Wort "Sendungen sprechen" enthält eine Eigenschaft mit dem Namen " *e-Mail*", die e-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf **weiter**, überprüfen Sie Ihre Einstellungen, und wechseln Sie zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-redtail-speak-connector"></a>Schritt 4: Überwachen des Audioconnectors Speak

Nachdem Sie den Connector Speak erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Konnektoren** , und wählen Sie dann den Stecker **Speak** Connector aus, um die Flyout-Seite anzuzeigen. Auf dieser Seite werden Eigenschaften und Informationen zum Connector angezeigt.

3. Klicken Sie unter **Connectorstatus with Source** auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Zurzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt zur Verfügung stehen.
