---
title: Einrichten eines Connectors zum Archivieren von XSLT/XML-Daten in Microsoft 365
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
description: Administratoren können einen Connector zum Importieren und Archivieren von XSLT/XML-Daten aus Globanet in Microsoft 365 einrichten. Mit diesem Connector können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren, damit Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten der drittanbieterdaten Ihrer Organisation verwenden können.
ms.openlocfilehash: 20d24e919c0fe045e487c41e42745f73acb521ad
ms.sourcegitcommit: 16cbac5eacadd7b30cbca1fd2435ba9098de5e1c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/28/2020
ms.locfileid: "48785497"
---
# <a name="set-up-a-connector-to-archive-xsltxml-data"></a>Einrichten eines Connectors zum Archivieren von XSLT/XML-Daten

Verwenden Sie einen Globanet-Connector im Microsoft 365 Compliance Center zum Importieren und Archivieren von Daten aus der Webseiten Quelle in Benutzerpostfächer in Ihrer Microsoft 365-Organisation. Globanet bietet Ihnen einen [XSLT/XML-Konnektor](https://globanet.com/xslt-xml) , der die schnelle Entwicklung von Dateien ermöglicht, die mithilfe von XSLT (Extensible Stylesheet Language Transformations) erstellt wurden, um XML-Dateien in andere Dateiformate (wie HTML oder Text) zu transformieren, die in Microsoft 365 importiert werden können. Der Connector wandelt den Inhalt eines Elements aus der XSLT/XML-Quelle in ein e-Mail-Nachrichtenformat um und importiert dann das konvertierte Element in Microsoft 365-Postfächer.

Nachdem XSLT/XML-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Kompatibilitätsfeatures wie Beweissicherungsverfahren, eDiscovery-und Aufbewahrungsrichtlinien sowie Aufbewahrungs Bezeichnungen anwenden. Die Verwendung eines XSLT/XML-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="overview-of-archiving-xsltxml-data"></a>Übersicht über das Archivieren von XSLT/XML-Daten

In der folgenden Übersicht wird erläutert, wie Sie mithilfe eines Konnektors XSLT/XML-Quelldaten in Microsoft 365 archivieren.

![Archivierungs Workflow für XSLT/XML-Daten](../media/XSLT-XMLConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit der XSLT/XML-Quelle zusammen, um eine XSLT/XML-Website einzurichten und zu konfigurieren.

2. Alle 24 Stunden werden Chatnachrichten von der XSLT/XML-Quelle auf die Globanet Merge1-Website kopiert. Der Connector wandelt auch den Inhalt in ein e-Mail-Nachrichtenformat um.

3. Der XSLT/XML-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Globanet Merge1-Website her und überträgt die Nachrichten an einen sicheren Azure-Speicherort in der Microsoft-Cloud.

4. Der Connector importiert die konvertierten Nachrichtenelemente in die Postfächer bestimmter Benutzer, wobei der Wert der *Email* -Eigenschaft der automatischen Benutzerzuordnung wie in Schritt 3 beschrieben wird. Ein neuer Unterordner im Posteingangsordner mit dem Namen **XSLT/XML** wird in den Benutzerpostfächern erstellt, und die Nachrichtenelemente werden in diesen Ordner importiert. Der Connector verwendet den Wert der *Email* -Eigenschaft. Jede Nachricht enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Teilnehmers der Nachricht aufgefüllt wird.

## <a name="before-you-begin"></a>Bevor Sie beginnen

- Erstellen Sie ein Globanet-Merge1-Konto für Microsoft-Connectors. Wenden Sie sich dazu an den [Globanet-Kunden Support](https://globanet.com/contact-us/). Sie müssen sich bei diesem Konto anmelden, wenn Sie den Connector in Schritt 1 erstellen.

- Der Benutzer, der den XSLT/XML-Connector in Schritt 1 erstellt (und in Schritt 3 vervollständigt) muss der Rolle "Post Fach Import Export" in Exchange Online zugewiesen sein. Diese Rolle ist für das Hinzufügen von Connectors auf der Seite **Daten Konnektoren** im Microsoft 365 Compliance Center erforderlich. Diese Rolle ist in Exchange Online standardmäßig keiner Rollengruppe zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-set-up-an-xsltxml-connector"></a>Schritt 1: Einrichten eines XSLT/XML-Connectors

Der erste Schritt besteht darin, auf die **Daten-Konnektoren** im Microsoft 365 Compliance Center zuzugreifen und einen Connector für XSLT/XML-Daten zu erstellen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com/) und klicken Sie dann auf **Daten Konnektoren**  >  **XSLT/XML** .

2. Klicken Sie auf der Seite **XSLT/XML-** Produktbeschreibung auf **neuen Connector hinzufügen** .

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen** .

4. Geben Sie einen eindeutigen Namen ein, der den Connector identifiziert, und klicken Sie dann auf **weiter** .

5. Melden Sie sich bei Ihrem Merge1-Konto an, um den Connector zu konfigurieren.

## <a name="step-2-configure-an-xsltxml-connector"></a>Schritt 2: Konfigurieren eines XSLT/XML-Connectors

Der zweite Schritt besteht darin, den XSLT/XML-Connector auf der Merge1-Website zu konfigurieren. Informationen zum Konfigurieren des XSLT/XML-Connectors auf der Globanet-Merge1-Website finden Sie unter [Merge1 Connector-Benutzerhandbuch für Drittanbieter](https://docs.ms.merge1.globanetportal.com/Merge1%20Third-Party%20Connectors%20XSLT-XML%20User%20Guide%20.pdf).

Nachdem Sie auf **& fertig stellen** klicken, werden Sie zurück zum Microsoft 365 Compliance Center auf die Seite **Benutzerzuordnung** im Connector-Assistenten umgeleitet.

## <a name="step-3-map-users-and-complete-the-connector-setup"></a>Schritt 3: Zuordnen von Benutzern und Abschließen des Connector-Setups

1. Führen Sie die folgenden Schritte aus, um Benutzer zuzuordnen und das Connector-Setup im Microsoft 365 Compliance Center abzuschließen:

2. Aktivieren Sie auf der Seite **XSLT/XML-Benutzer auf Microsoft 365** -Benutzer zuordnen die Option Automatische Benutzerzuordnung. Die XSLT/XML-Elemente enthalten eine Eigenschaft mit dem Namen " *e-Mail* ", die e-Mail-Adressen für Benutzer in Ihrer Organisation enthält. Wenn der Connector diese Adresse einem Microsoft 365-Benutzer zuordnen kann, werden die Elemente in das Postfach dieses Benutzers importiert.

3. Klicken Sie auf der Seite **Administrator Zustimmung** auf **Zustimmung erteilen** . Sie werden zur Microsoft-Website umgeleitet. Klicken Sie auf **akzeptieren** , um die Zustimmung zu erteilen.

   Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um die Zustimmung des Administrators bereitzustellen, müssen Sie mit den Anmeldeinformationen eines globalen Administrators von Microsoft 365 angemeldet sein und dann die Zustimmungs Anforderung annehmen. Wenn Sie nicht als globaler Administrator angemeldet sind, können Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) wechseln und sich mit globalen Administratoranmeldeinformationen anmelden, um die Anforderung zu akzeptieren.

4. Klicken Sie auf **weiter** , überprüfen Sie Ihre Einstellungen, und wechseln Sie zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.

## <a name="step-4-monitor-the-xsltxml-connector"></a>Schritt 4: Überwachen des XSLT/XML-Connectors

Nachdem Sie den XSLT/XML-Connector erstellt haben, können Sie den Connectorstatus im Microsoft 365 Compliance Center anzeigen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf die Registerkarte **Connectors** , und wählen Sie dann den **XSLT/XML-** Konnektor aus, um die Flyout-Seite anzuzeigen, die die Eigenschaften und Informationen zum Connector enthält.

3. Klicken Sie unter **Connectorstatus with Source** auf den Link **Download Protokoll** , um das Statusprotokoll für den Connector zu öffnen (oder zu speichern). Dieses Protokoll enthält Daten, die in die Microsoft-Cloud importiert wurden.

## <a name="known-issues"></a>Bekannte Probleme

- Zurzeit wird das Importieren von Anlagen oder Elementen, die größer als 10 MB sind, nicht unterstützt. Unterstützung für größere Elemente wird zu einem späteren Zeitpunkt zur Verfügung stehen.
