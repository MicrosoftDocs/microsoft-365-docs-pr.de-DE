---
title: Einrichten eines Connectors zum Archivieren eines Arbeitsplatzes aus Facebook-Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Daten aus dem Arbeitsplatz von Facebook einrichten, das auf der Merge1-Website von Globanet in Microsoft 365 archiviert wird. Das Einrichten eines Connectors erfordert die Verwendung von Globanet mit diesem Connector können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren, damit Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten der drittanbieterdaten Ihrer Organisation verwenden können.
ms.openlocfilehash: ce92302da73151945e42a8120363221fe7b393b3
ms.sourcegitcommit: 3c39866865c8c61bce2169818d8551da65033cfe
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/30/2020
ms.locfileid: "48816728"
---
# <a name="set-up-a-connector-to-archive-workplace-from-facebook-data"></a>Einrichten eines Connectors zum Archivieren eines Arbeitsplatzes aus Facebook-Daten

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center zum Importieren und Archivieren von Daten aus dem Arbeitsplatz von Facebook in Benutzerpostfächer in Ihrer Microsoft 365-Organisation. Globanet bietet einen [Arbeitsplatz von Facebook](https://globanet.com/workplace/) Connector, der zum Erfassen von Elementen aus der Drittanbieter-Datenquelle (regelmäßig) und zum Importieren dieser Elemente in Microsoft 365 konfiguriert ist. Der Connector wandelt die Inhalte wie Chats, Anlagen, Beiträge und Videos vom Arbeitsplatz in ein e-Mail-Nachrichtenformat um und importiert diese Elemente dann in Benutzerpostfächer in Microsoft 365.

Nachdem Arbeitsplatzdaten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, Aufbewahrungsrichtlinien und Aufbewahrungs Bezeichnungen sowie die Kompatibilität der Kommunikation anwenden. Mithilfe von Workplace from Facebook Connector zum Importieren und Archivieren von Daten in Microsoft 365 können Sie Ihrer Organisation dabei helfen, mit behördlichen und behördlichen Richtlinien konform zu bleiben.

## <a name="overview-of-archiving-workplace-from-facebook-data"></a>Übersicht über die Archivierung von Arbeitsplätzen aus Facebook-Daten

In der folgenden Übersicht wird der Vorgang der Verwendung eines Connectors zum Archivieren von Arbeitsplatzdaten in Microsoft 365 erläutert.

![Archivierungs Workflow für Workplace aus Facebook-Daten](../media/WorkplaceConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit dem Arbeitsplatz von Facebook zusammen, um eine Arbeitsplatz Website einzurichten und zu konfigurieren.

2. Alle 24 Stunden werden Elemente von Workplace auf die Globanet Merge1-Website kopiert. Der Connector wandelt auch den Inhalt dieser Elemente in ein e-Mail-Nachrichtenformat um.

3. Der Arbeitsplatz von Facebook Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit dem Globanet Merge1 her und überträgt die Arbeitsplatz Elemente an einen sicheren Azure-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Elemente in die Postfächer bestimmter Benutzer, wobei der Wert der *Email* -Eigenschaft der automatischen Benutzerzuordnung wie in Schritt 3 beschrieben wird. Ein Unterordner im Posteingangsordner namens " **Workplace from Facebook** " wird erstellt, und die Arbeitsplatz Elemente werden in diesen Ordner importiert. Der Connector verwendet den Wert der *Email* -Eigenschaft. Jedes Arbeitsplatz Element enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Chat-oder Post-Teilnehmers aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

- Erstellen Sie ein Globanet-Merge1-Konto für Microsoft-Connectors. Um dieses Konto zu erstellen, wenden Sie sich an den [Globanet-Kunden Support](https://globanet.com/ms-connectors-contact). Sie melden sich bei diesem Konto an, wenn Sie den Connector in Schritt 1 erstellen.

- Erstellen Sie eine benutzerdefinierte Integration https://my.workplace.com/work/admin/apps/ , um Daten vom Arbeitsplatz über APIs für Compliance-und eDiscovery-Zwecke abzurufen.

   Beim Erstellen der Integration generiert die Arbeitsplatz Plattform eine Reihe eindeutiger Anmeldeinformationen, die zum Generieren von Token verwendet werden, die für die Authentifizierung verwendet werden. Diese Token werden am Arbeitsplatz vom Konfigurations-Assistenten für Facebook Connector in Schritt 2 verwendet. Eine Schritt-für-Schritt-Anleitung zum Erstellen der Anwendungen finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).

- Der Benutzer, der den Arbeitsplatz von Facebook Connector in Schritt 1 erstellt (und den Sie in Schritt 3 ausführt) muss der Rolle "Post Fach Import Export" in Exchange Online zugewiesen sein. Diese Rolle ist für das Hinzufügen von Connectors auf der Seite **Daten Konnektoren** im Microsoft 365 Compliance Center erforderlich. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-the-workplace-from-facebook-connector"></a>Schritt 1: Einrichten des Arbeitsplatzes von Facebook Connector

Der erste Schritt besteht darin, auf die Seite " **Daten Konnektoren** " im Microsoft 365 Compliance Center zuzugreifen und einen Connector für Arbeitsplatzdaten zu erstellen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **Daten Verbindungs** -  >  **Arbeitsplatz von Facebook** .

2. Klicken Sie auf der Seite für die Produktbeschreibung auf dem **Arbeitsplatz** auf **Connector hinzufügen** .

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen** .

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **weiter** .

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-the-workplace-from-facebook-connector-on-the-globanet-merge1-site"></a>Schritt 2: Konfigurieren des Arbeitsplatzes von Facebook Connector auf der Globanet Merge1-Website

Der zweite Schritt besteht darin, den Arbeitsplatz von Facebook Connector auf der Merge1-Website zu konfigurieren. Informationen zum Konfigurieren des Arbeitsplatzes von Facebook Connector finden Sie unter [Merge1 Third-Party Connectors User Guide](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20Workplace%20from%20Facebook%20User%20Guide%20.pdf).

Nachdem Sie auf **& Ende speichern** klicken, wird die Seite **Benutzerzuordnung** im Connector-Assistenten im Microsoft 365 Compliance Center angezeigt.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und das Connector-Setup im Microsoft 365 Compliance Center abzuschließen:

1. Aktivieren Sie auf der Seite **externe Benutzer auf Microsoft 365-Benutzer zuordnen** die Option Automatische Benutzerzuordnung. Die Arbeitsplatz Elemente enthalten eine Eigenschaft mit dem Namen " *e-Mail* ", die e-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

2. Klicken Sie auf der Seite **Administrator Zustimmung** auf **Zustimmung erteilen** . Sie werden zur Microsoft-Website umgeleitet. Klicken Sie auf **akzeptieren** , um die Zustimmung zu erteilen.
  
   Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um die Zustimmung des Administrators bereitzustellen, müssen Sie mit den Anmeldeinformationen eines globalen Administrators von Microsoft 365 angemeldet sein und dann die Zustimmungs Anforderung annehmen. Wenn Sie nicht als globaler Administrator angemeldet sind, können Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) wechseln und sich mit globalen Administratoranmeldeinformationen anmelden, um die Anforderung zu akzeptieren.

3. Klicken Sie auf **weiter** , überprüfen Sie Ihre Einstellungen, und wechseln Sie dann zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-workplace-from-facebook-connector"></a>Schritt 4: Überwachen des Arbeitsplatzes von Facebook Connector

Nachdem Sie den Arbeitsplatz über Facebook Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie dann den **Arbeitsbereich von Facebook Connector aus** , um die Flyout-Seite anzuzeigen. Diese Seite enthält die Eigenschaften und Informationen zum Connector.

3. Klicken Sie unter **Connectorstatus with Source** auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Informationen zu den Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Zurzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt zur Verfügung stehen.
