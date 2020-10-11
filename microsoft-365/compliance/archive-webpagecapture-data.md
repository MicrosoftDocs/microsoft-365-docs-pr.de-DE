---
title: Einrichten eines Connectors zum Archivieren von Webseiten Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Webseiten-Aufnahmedaten aus Globanet in Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren, damit Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten der drittanbieterdaten Ihrer Organisation verwenden können.
ms.openlocfilehash: b3f622a63e4f4dfe550f481bee6b3a56dfd3bdb1
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48409110"
---
# <a name="set-up-a-connector-to-archive-webpage-data-preview"></a>Einrichten eines Connectors zum Archivieren von Webseiten Daten (Vorschau)

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center, um Daten aus Webseiten in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Globanet bietet einen [Web-Capture](https://globanet.com/webpage-capture) -Konnektor, der bestimmte Webseiten (und Links auf diesen Seiten) in einer bestimmten Website oder einer ganzen Domäne erfasst. Der Connector wandelt die Webseiteninhalte in ein PDF-, PNG-oder benutzerdefiniertes Dateiformat um und fügt dann die konvertierten Dateien an eine e-Mail-Nachricht an und importiert dann diese e-Mail-Elemente in Benutzerpostfächer in Microsoft 365.

Nachdem Webseiteninhalte in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Kompatibilitätsfeatures wie Beweissicherungsverfahren, eDiscovery-und Aufbewahrungsrichtlinien sowie Aufbewahrungs Bezeichnungen anwenden. Durch die Verwendung eines Webpage Capture-Konnektors zum Importieren und Archivieren von Daten in Microsoft 365 können Sie Ihrer Organisation bei der Einhaltung von behördlichen und behördlichen Richtlinien helfen.

## <a name="overview-of-archiving-webpage-data"></a>Übersicht über die Archivierung von Webseiten Daten

In der folgenden Übersicht wird erläutert, wie Sie einen Connector zum Archivieren von Webseiteninhalten in Microsoft 365 verwenden.

![Archivierungs Workflow für Webseiten Daten](../media/WebPageCaptureConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit der Webseite-Quelle zusammen, um eine Website-Erfassungs Website einzurichten und zu konfigurieren.

2. Alle 24 Stunden werden die Elemente der Webseite Sources auf die Globanet Merge1-Website kopiert. Der Connector konvertiert auch den Inhalt einer Webseite in eine e-Mail-Nachricht.

3. Der Web Capture-Konnektor, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Globanet Merge1-Website her und überträgt die Webseitenelemente an einen sicheren Azure-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Webseitenelemente in die Postfächer bestimmter Benutzer, indem er den Wert der *Email* -Eigenschaft der automatischen Benutzerzuordnung wie in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschrieben verwendet. Ein Unterordner im Posteingangsordner mit dem Namen **Webpage Capture** wird in den Benutzerpostfächern erstellt, und die Webseitenelemente werden in diesen Ordner importiert. Der Connector verwendet den Wert der *Email* -Eigenschaft. Jedes Webpage-Element enthält diese Eigenschaft, die mit den e-Mail-Adressen aufgefüllt wird, die beim Konfigurieren des Webpage Capture-Konnektors in [Schritt 2](#step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site)angegeben werden.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Erstellen Sie ein Globanet-Merge1-Konto für Microsoft-Connectors. Wenden Sie sich dazu an den [Globanet-Kunden Support](https://globanet.com/ms-connectors-contact/). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Sie müssen mit der Globanet-Unterstützung zusammenarbeiten, um ein benutzerdefiniertes Dateiformat einzurichten, in das die Webseitenelemente konvertiert werden sollen. Weitere Informationen finden Sie im Merge1-Benutzerhandbuch für Drittanbieter-Konnektoren in 

- Der Benutzer, der den Capture-Konnektor der Webseite in Schritt 1 erstellt (und in Schritt 3 vervollständigt wird), muss der Rolle "Post Fach Import Export" in Exchange Online zugewiesen sein. Diese Rolle ist für das Hinzufügen von Connectors auf der Seite **Daten Konnektoren** im Microsoft 365 Compliance Center erforderlich. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-webpage-capture-connector"></a>Schritt 1: Einrichten des Connectors für die Webpage Capture

Der erste Schritt besteht darin, auf die **Daten-Konnektoren** zuzugreifen und einen Connector für Webseiten Quelldaten zu erstellen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **Daten Verbinder**-  >  **Webseite erfassen**.

2. Klicken Sie auf der Seite Produktbeschreibung der **Webseite erfassen** auf **Connector hinzufügen**.

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-webpage-capture-connector-on-the-globanet-merge1-site"></a>Schritt 2: Konfigurieren des Webpage Capture-Konnektors auf der Globanet Merge1-Website

Der zweite Schritt besteht darin, den Webpage Capture-Konnektor auf der Globanet Merge1-Website zu konfigurieren. Informationen zum Konfigurieren des Webseiten Sammlungs-Konnektors finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Web%20Page%20Capture%20User%20Guide%20.pdf).

Nachdem Sie auf **& fertig stellen**klicken, werden Sie zurück zum Microsoft 365 Compliance Center auf die Seite **Benutzerzuordnung** im Connector-Assistenten umgeleitet.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und das Connector-Setup im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der Seite **Karte "Webseite erfassen" für Benutzer auf Microsoft 365** -Benutzer die automatische Benutzerzuordnung. Die Webseite Capture-Elemente enthalten eine Eigenschaft mit dem Namen " *e-Mail*", die e-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf der Seite **Administrator Zustimmung** auf **Zustimmung erteilen**. Sie werden zur Microsoft-Website umgeleitet. Klicken Sie auf **akzeptieren** , um die Zustimmung zu erteilen.

   Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um die Zustimmung des Administrators bereitzustellen, müssen Sie mit den Anmeldeinformationen eines globalen Administrators von Microsoft 365 angemeldet sein und dann die Zustimmungs Anforderung annehmen. Wenn Sie nicht als globaler Administrator angemeldet sind, können Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) wechseln und sich mit globalen Administratoranmeldeinformationen anmelden, um die Anforderung zu akzeptieren.

3. Klicken Sie auf **weiter**, überprüfen Sie Ihre Einstellungen, und wechseln Sie zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-webpage-capture-connector"></a>Schritt 4: Überwachen des Webpage Capture-Konnektors

Nachdem Sie den Website Sammlungs-Konnektor erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie dann den **Datenerfassungs** -Konnektor aus, um die Flyout-Seite mit den Eigenschaften und Informationen zum Connector anzuzeigen.

3. Klicken Sie unter **Connectorstatus with Source**auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Zurzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt zur Verfügung stehen.
