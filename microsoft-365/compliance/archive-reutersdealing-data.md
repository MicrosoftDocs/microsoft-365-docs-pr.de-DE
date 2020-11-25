---
title: Einrichten eines Connectors zum Archivieren von Reuters-Handelsdaten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Reuters-Handelsdaten von Globanet nach Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren. Nach dem Archivieren dieser Daten können Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten von drittanbieterdaten verwenden.
ms.openlocfilehash: 6b1b1421944e139b0e5051e99dafb4fba9e126ba
ms.sourcegitcommit: 95b85a1fdf43e3f0839483fa22e279262703f15f
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/24/2020
ms.locfileid: "49407309"
---
# <a name="set-up-a-connector-to-archive-reuters-dealing-data"></a>Einrichten eines Connectors zum Archivieren von Reuters-Handelsdaten

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center, um Daten aus der Reuters-Dealing-Plattform in Benutzerpostfächer in Ihrer Microsoft 365-Organisation zu importieren und zu archivieren. Globanet bietet Ihnen einen [Reuters-Dealing](https://globanet.com/reuters-dealing/) -Connector, der so konfiguriert ist, dass er Elemente aus der Drittanbieter-Datenquelle (regelmäßig) erfasst und diese Elemente dann nach Microsoft 365 importiert. Der Connector wandelt die Abwicklungs Kommunikation aus dem Reuters-Dealing-Konto in ein e-Mail-Nachrichtenformat um und importiert diese Elemente dann in das Postfach des Benutzers in Microsoft 365.

Nachdem die Reuters-dealdaten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen sowie die Kompatibilität der Kommunikation anwenden. Die Verwendung eines Reuters-Dealing-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="overview-of-archiving-reuters-dealing-data"></a>Übersicht über die Archivierung von Reuters-Handelsdaten

In der folgenden Übersicht wird erläutert, wie Sie einen Connector zum Archivieren der Reuters-Geschäftsdaten in Microsoft 365 verwenden.

![Archivierungs Workflow für Reuters-Handelsdaten](../media/ReuetersDealingConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit Reuters im Zusammenhang mit der Einrichtung und Konfiguration einer Reuters-Dealing-Website.

2. Alle 24 Stunden werden die Reuters-Dealing Items auf die Globanet Merge1-Website kopiert. Der Connector wandelt die Elemente auch in ein e-Mail-Nachrichtenformat um.

3. Der Reuters Dealing Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Globanet Merge1-Website her und überträgt die Inhalte an einen sicheren Azure-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert Elemente in die Postfächer bestimmter Benutzer, indem er den Wert der *Email* -Eigenschaft der automatischen Benutzerzuordnung wie in [Schritt 3](#step-3-map-users-and-complete-the-connector-setup)beschrieben verwendet. Ein Unterordner im Posteingangsordner namens **Reuters Dealing** wird in den Benutzerpostfächern erstellt, und die Elemente werden in diesen Ordner importiert. Der Connector bestimmt anhand des Werts der *Email* -Eigenschaft, in welches Postfach Elemente importiert werden sollen. Jedes Reuters-Dealing-Element enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Teilnehmers des Elements aufgefüllt wird.

## <a name="before-you-begin"></a>Vorbereitung

- Erstellen Sie ein Globanet-Merge1-Konto für Microsoft-Connectors. Um ein Konto zu erstellen, wenden Sie sich an den [Globanet-Kunden Support](https://globanet.com/contact-us). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den Reuters Dealing Connector in Schritt 1 erstellt (und in Schritt 3 vervollständigt) muss der Rolle "Post Fach Import Export" in Exchange Online zugewiesen sein. Diese Rolle ist für das Hinzufügen von Connectors auf der Seite **Daten Konnektoren** im Microsoft 365 Compliance Center erforderlich. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-reuters-dealing-connector"></a>Schritt 1: Einrichten des Reuters-Dealing-Connectors

Der erste Schritt besteht darin, auf die Seite " **Daten Konnektoren** " in Microsoft 365 zuzugreifen und einen Connector für Reuters-Datenverarbeitungs Daten zu erstellen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **Data Connectors**  >  **Reuters Dealing**.

2. Klicken Sie auf der Seite **Reuters Dealing** Product Description auf **Connector hinzufügen**.

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **weiter**.

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-reuters-dealing-connector-on-the-globanet-merge1-site"></a>Schritt 2: Konfigurieren des Reuters-Dealing-Connectors auf der Globanet Merge1-Website

Der zweite Schritt besteht darin, den Reuters-Dealing-Connector auf Globanet der Merge1-Website zu konfigurieren. Informationen zum Konfigurieren des Reuters-Dealing-Connectors finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Reuters%20Dealing%20User%20Guide%20.pdf).

Nachdem Sie auf **& Ende speichern** klicken, wird die Seite **Benutzerzuordnung** im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und das Connector-Setup im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der Seite **Reuters Dealing users to Microsoft 365 users** die automatische Benutzerzuordnung.

   Reuters-Dealing Items enthalten eine Eigenschaft namens " *e-Mail*", die e-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf der Seite **Administrator Zustimmung** auf die Schaltfläche **Zustimmung erteilen** . Sie werden zur Microsoft-Website umgeleitet. Klicken Sie auf **akzeptieren** , um die Zustimmung zu erteilen.

    Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um die Zustimmung des Administrators bereitzustellen, müssen Sie mit den Anmeldeinformationen eines globalen Administrators von Microsoft 365 angemeldet sein und dann die Zustimmungs Anforderung annehmen. Wenn Sie nicht als globaler Administrator angemeldet sind, können Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) wechseln und sich mit globalen Administratoranmeldeinformationen anmelden, um die Anforderung zu akzeptieren.

3. Klicken Sie auf **weiter**, überprüfen Sie Ihre Einstellungen, und wechseln Sie zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-reuters-dealing-connector"></a>Schritt 4: Überwachen des Reuters-Dealing-Connectors

Nachdem Sie den Reuters-Dealing Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie dann den **Reuters-Dealing** Connector aus, um die Flyout-Seite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

3. Klicken Sie unter **Connectorstatus with Source** auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Zurzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt zur Verfügung stehen.
