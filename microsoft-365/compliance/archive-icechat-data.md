---
title: Einrichten eines Connectors zum Archivieren von Ice-Chat Daten
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Daten aus dem ICE-Chat-Tool in Microsoft 365 einrichten. Auf diese Weise können Sie Daten aus Drittanbieter-Datenquellen in Microsoft 365 archivieren, damit Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten der drittanbieterdaten Ihrer Organisation verwenden können.
ms.openlocfilehash: cd56e98aadc2b7328b733939ecc8951413309ba5
ms.sourcegitcommit: ae3aa7f29be16d08950cf23cad489bc069aa8617
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48408765"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>Einrichten eines Connectors zum Archivieren von Ice-Chat Daten

Verwenden Sie einen systemeigenen Connector im Microsoft 365 Compliance Center zum Importieren und Archivieren von Finanz Dienstleistungs-Chat Daten aus dem ICE Chat-Zusammenarbeits Tool. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er eine Verbindung mit der ICE Chat Secure FTP (SFTP)-Website Ihrer Organisation einmal täglich her, wandelt den Inhalt von Chat Nachrichten in ein e-Mail-Nachrichtenformat um und importiert diese Elemente anschließend in Postfächer in Microsoft 365.

Nachdem Ice-Chat Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, eDiscovery, Archivierung, Überwachung, Kommunikations Konformität und Microsoft 365-Aufbewahrungsrichtlinien auf Ice-Chatdaten anwenden. Sie können beispielsweise Ice-Chatnachrichten mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die Ice-Chat Daten enthält, einer Depotbank in einem erweiterten eDiscovery-Fall zuordnen. Die Verwendung eines ICE-Chat-Konnektors zum Importieren und Archivieren von Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="overview-of-archiving-ice-chat-data"></a>Übersicht über die Archivierung von Ice-Chat Daten

In der folgenden Übersicht wird erläutert, wie Sie einen Connector zum Archivieren von Ice-Chat Daten in Microsoft 365 verwenden.

![Ice Chat-Archivierungs Workflow](../media/ICEChatConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit ICE Chat zusammen, um eine Ice Chat SFTP-Website einzurichten. Sie können auch mit ICE Chat zusammenarbeiten, um den ICE Chat so zu konfigurieren, dass Chatnachrichten in Ihre Ice Chat SFTP-Website kopiert werden.

2. Einmal alle 24 Stunden werden Chatnachrichten von Ice Chat auf Ihre Ice Chat SFTP-Website kopiert.

3. Der ICE Chat Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der ICE Chat SFTP-Website her und überträgt die Chat Nachrichten aus den vorherigen 24 Stunden an einen sicheren Azure-Speicherort in der Microsoft-Cloud. Der Connector wandelt auch den Inhalt einer Chat Massage in ein e-Mail-Nachrichtenformat um.

4. Der Connector importiert Chatnachrichten Elemente in die Postfächer bestimmter Benutzer. In den Benutzerpostfächern wird ein neuer Ordner mit dem Namen **Ice Chat** erstellt, und die Chatnachrichten Elemente werden in diesen Ordner importiert. Der Connector verwendet den Wert der Eigenschaften *SenderEmail* und *RecipientEmail* . Jede Chatnachricht enthält diese Eigenschaften, die mit der e-Mail-Adresse des Absenders und allen Empfängern/Teilnehmern der Chatnachricht aufgefüllt werden.

   Zusätzlich zur automatischen Benutzerzuordnung, die die Werte der *SenderEmail* -und der *RecipientEmail* -Eigenschaft verwendet (was bedeutet, dass der Connector eine Chatnachricht in das Postfach des Absenders und die Postfächer jedes Empfängers importiert), können Sie auch benutzerdefinierte Benutzerzuordnungen definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei enthält den ICE Chat *ImId* und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer in Ihrer Organisation. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnungsdatei bereitstellen, wird der Connector für jedes Chat Element zuerst die benutzerdefinierte Zuordnungsdatei betrachten. Wenn ein gültiges Microsoft 365-Benutzerkonto, das dem ICE Chat-ImId eines Benutzers entspricht, nicht gefunden wird, verwendet der Connector die *SenderEmail* -und *RecipientEmail* -Eigenschaften des Chat Elements, um das Element in die Postfächer der Chat Teilnehmer zu importieren. Wenn der Connector weder in der benutzerdefinierten Zuordnungsdatei noch in den Eigenschaften *SenderEmail* und *RecipientEmail* einen gültigen Microsoft 365-Benutzer findet, wird das Element nicht importiert.

## <a name="before-you-begin"></a>Bevor Sie beginnen:

Einige der erforderlichen Schritte zum Archivieren von Ice-Chat Daten liegen außerhalb von Microsoft 365 und müssen abgeschlossen sein, bevor Sie den Connector im Compliance Center erstellen können.

- Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um dieser Anforderung zuzustimmen, gehen Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), melden Sie sich mit den Anmeldeinformationen eines Office 365 globalen Administrators an, und nehmen Sie dann die Anforderung an. Sie müssen diesen Schritt ausführen, bevor Sie den ICE Chat Connector in Schritt 3 erfolgreich erstellen können.

- Ice Chat berechnet ihren Kunden Gebühren für externe Compliance. Ihre Organisation sollte sich an die Ice Chat Sales Group wenden, um zu diskutieren und die Ice Chat Data Services-Vereinbarung zu unterzeichnen, die Sie unter erhalten können [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) . Diese Vereinbarung besteht zwischen Ice Chat und Ihrer Organisation und umfasst keine Microsoft. Nachdem Sie in Schritt 2 eine Ice Chat SFTP-Website eingerichtet haben, stellt Ice Chat die FTP-Anmeldeinformationen direkt in Ihrer Organisation bereit. Anschließend sollten Sie diese Anmeldeinformationen bei der Einrichtung des Connectors in Schritt 3 an Microsoft weitergeben.

- Sie müssen eine Ice Chat SFTP-Website einrichten, bevor Sie den Connector in Schritt 3 erstellen. Nach der Arbeit mit ICE Chat, um die SFTP-Website einzurichten, werden Daten aus dem ICE-Chat jeden Tag auf die SFTP-Website hochgeladen. Der in Schritt 3 erstellte Connector stellt eine Verbindung mit dieser SFTP-Website her und überträgt die Chat Daten an Microsoft 365-Postfächer. SFTP verschlüsselt auch die Ice-Chat-Daten, die während des Übertragungsprozesses an Postfächer gesendet werden.

- Der Administrator, der in Schritt 3 den ICE-Chat-Konnektor erstellt (und der die öffentlichen Schlüssel und die IP-Adresse in Schritt 1 herunterlädt) muss in Exchange Online die Rolle "Post Fach Import Export" zugewiesen haben. Diese Rolle ist für das Hinzufügen von Connectors auf der Seite **Daten Konnektoren** im Microsoft 365 Compliance Center erforderlich. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Schritt 1: Abrufen von öffentlichen SSH-und PGP-Schlüsseln

Der erste Schritt besteht darin, eine Kopie der öffentlichen Schlüssel für Secure Shell (SSH) und Pretty Good Privacy (PGP) zu erhalten. Sie verwenden diese Schlüssel in Schritt 2, um die Website Ice Chat SFTP so zu konfigurieren, dass der in Schritt 3 erstellte Connector die Verbindung zur SFTP-Website herstellen und die Ice-Chatdaten an Microsoft 365-Postfächerüber tragen kann. Außerdem erhalten Sie in diesem Schritt eine IP-Adresse, die Sie beim Konfigurieren der ICE Chat SFTP-Website verwenden.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf der Seite **Daten Konnektoren** unter **Ice Chat**auf **Ansicht**.

3. Klicken Sie auf der Seite **Ice Chat** auf **Connector hinzufügen**.

4. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

5. Klicken Sie auf der Seite **Anmeldeinformationen für ICE Chat SFTP-Website hinzufügen** unter Schritt 1 auf den Link **SSH herunterladen**, **PGP-Schlüssel**herunterladen und **IP-Adress Links herunterladen** , um eine Kopie der einzelnen Dateien auf dem lokalen Computer zu speichern. Diese Dateien enthalten die folgenden Elemente, die zum Konfigurieren der ICE Chat SFTP-Website in Schritt 2 verwendet werden:

   - Öffentlicher SSH-Schlüssel: dieser Schlüssel wird zum Konfigurieren von Secure SSH verwendet, um eine sichere Remoteanmeldung zu ermöglichen, wenn der Connector eine Verbindung mit der ICE Chat SFTP-Website herstellt.

   - Öffentlicher PGP-Schlüssel: dieser Schlüssel wird verwendet, um die Verschlüsselung von Daten zu konfigurieren, die von der ICE Chat SFTP-Website an Microsoft 365 übertragen werden.

   - IP-Adresse: die Ice Chat SFTP-Website ist so konfiguriert, dass Sie eine Verbindungsanforderung nur von dieser IP-Adresse akzeptiert, die von dem ICE-Chat-Konnektor verwendet wird, den Sie in Schritt 3 erstellen.

6. Klicken Sie auf **Abbrechen** , um den Assistenten zu schließen. Sie kehren zu diesem Assistenten in Schritt 3 zurück, um den Connector zu erstellen.

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>Schritt 2: Konfigurieren der ICE Chat SFTP-Website

Der nächste Schritt besteht darin, die öffentlichen SSH-und PGP-Schlüssel sowie die IP-Adresse, die Sie in Schritt 1 erhalten haben, zum Konfigurieren der SSH-Authentifizierung und der PGP-Verschlüsselung für die Ice Chat SFTP-Website zu verwenden. Auf diese Weise können Sie den in Schritt 3 erstellten Ice-Chat-Konnektor mit der ICE Chat SFTP-Website verbinden und Ice-Chat Daten an Microsoft 365 übertragen. Sie müssen mit dem ICE Chat-Kundensupport zusammenarbeiten, um Ihre Ice Chat SFTP-Website einzurichten.

## <a name="step-3-create-an-ice-chat-connector"></a>Schritt 3: Erstellen eines ICE Chat Connectors

Der letzte Schritt ist das Erstellen eines ICE-Chat-Konnektors im Microsoft 365 Compliance Center. Der Connector verwendet die von Ihnen bereitgestellten Informationen, um eine Verbindung zur Ice Chat SFTP-Website herzustellen und Chat Nachrichten an die entsprechenden Benutzerpostfach-Postfächer in Microsoft 365 zu übertragen.

1. Wechseln Sie zu, [https://compliance.microsoft.com](https://compliance.microsoft.com) und klicken Sie im linken Navigationsbereich auf **Daten-Konnektoren** .

2. Klicken Sie auf der Seite **Daten Konnektoren** unter **Ice Chat**auf **Ansicht**.

3. Klicken Sie auf der Seite **Ice Chat** auf **Connector hinzufügen**.

4. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

5. Geben Sie auf der Seite **Anmeldeinformationen für ICE Chat SFTP-Website hinzufügen** unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **Verbindung überprüfen**.

   - **Firm Code:** Die ID für Ihre Organisation, die als Benutzername für die Ice Chat SFTP-Website verwendet wird.

   - **Kennwort:** Das Kennwort für Ihre Ice Chat SFTP-Website.

   - **SFTP-URL:** Die URL für die Ice Chat SFTP-Website (beispielsweise SFTP.theice.com).

   - **SFTP-Port:** Die Portnummer für die Ice Chat SFTP-Website. Der Connector verwendet diesen Port, um eine Verbindung mit der SFTP-Website herzustellen.

6. Nachdem die Verbindung überprüft wurde, klicken Sie auf **weiter**.

7. Aktivieren Sie auf der Seite **externe Benutzer für Microsoft 365-Benutzer zuordnen** die Option Automatische Benutzerzuordnung, und geben Sie nach Bedarf eine Benutzerzuordnung an. Auf dieser Seite können Sie eine Kopie der CSV-Datei für die Benutzerzuordnung herunterladen. Sie können die Benutzerzuordnungen der Datei hinzufügen und diese dann hochladen.

   > [!NOTE]
   > Wie bereits erläutert, enthält die CSV-Datei für die benutzerdefinierte Zuordnungsdatei die Ice-Chat-Imid und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird der Connector für jedes Chat Element zuerst die benutzerdefinierte Zuordnungsdatei betrachten. Wenn kein gültiger Microsoft 365-Benutzer gefunden wird, der dem ICE Chat-Imid eines Benutzers entspricht, importiert der Connector das Element in die Postfächer für die Benutzer, die in den Eigenschaften *SenderEmail* und *RecipientEmail* des Chat Elements angegeben sind. Wenn der Connector keinen gültigen Microsoft 365-Benutzer durch eine automatische oder benutzerdefinierte Benutzerzuordnung findet, wird das Element nicht importiert.

8. Klicken Sie auf **weiter**, überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen** , um den Connector zu erstellen.

9. Wechseln Sie zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.
