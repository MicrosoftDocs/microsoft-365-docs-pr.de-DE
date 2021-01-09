---
title: Einrichten eines Connectors zum Archivieren von ICE -Chatdaten
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
description: Administratoren können einen Connector einrichten, um Daten aus dem ICE Chat Tool in Microsoft 365 zu importieren und zu archivieren. Auf diese Weise können Sie Daten aus Drittanbieterdatenquellen in Microsoft 365 archivieren, damit Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 79a18017ce7aa3c646fa6c7230bde4b001ddc4c8
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790169"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>Einrichten eines Connectors zum Archivieren von ICE -Chatdaten

Verwenden Sie einen nativen Connector im Microsoft 365 Compliance Center, um Chatdaten für Finanzdienstleistungen aus dem ICE Chat Collaboration Tool zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, verbindet er sich einmal täglich mit der ICE Chat Secure FTP (SFTP)-Website Ihrer Organisation, konvertiert den Inhalt von Chatnachrichten in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in Postfächer in Microsoft 365.

Nachdem ice chat data is stored in user mailboxes, you can apply Microsoft 365 compliance features such as litigation hold, eDiscovery, archiving, auditing, communication compliance, and Microsoft 365 retention policies to ICE Chat data. Sie können z. B. ICE -Chatnachrichten mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die ICE -Chatdaten enthält, einem Verwahrer in einem Advanced eDiscovery-Fall zuordnen. Die Verwendung eines ICE -Chat-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den behördlichen und behördlichen Richtlinien entspricht.

## <a name="overview-of-archiving-ice-chat-data"></a>Übersicht über die Archivierung von ICE -Chatdaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von ICE-Chatdaten in Microsoft 365 erläutert.

![ICE -Chat-Archivierungsworkflow](../media/ICEChatConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit ICE Chat zusammen, um einen ICE Chat -SFTP-Standort zu einrichten. Sie arbeiten auch mit ICE Chat zusammen, um ICE Chat so zu konfigurieren, dass Chatnachrichten auf Ihre ICE Chat -SFTP-Website kopiert werden.

2. Einmal alle 24 Stunden werden Chatnachrichten von ICE Chat an Ihre ICE Chat -SFTP-Website kopiert.

3. Der ICE Chat-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit dem ICE Chat -SFTP-Standort sicher und überträgt die Chatnachrichten aus den vorherigen 24 Stunden an einen sicheren Azure Storage-Speicherort in der Microsoft Cloud. Der Connector konvertiert auch den Inhalt eines Chatnachrichtenformats in ein E-Mail-Nachrichtenformat.

4. Der Connector importiert Chatnachrichtenelemente in die Postfächer bestimmter Benutzer. In den Benutzerpostfächern wird ein neuer Ordner mit dem Namen **ICE Chat** erstellt, und die Chatnachrichtenelemente werden in diesen Ordner importiert. Der Connector verwendet den Wert der *SenderEmail-* und *RecipientEmail-Eigenschaften.* Jede Chatnachricht enthält diese Eigenschaften, die mit der E-Mail-Adresse des Absenders und aller Empfänger/Teilnehmer der Chatnachricht aufgefüllt werden.

   Zusätzlich zur automatischen Benutzerzuordnung, bei der die Werte der Eigenschaft *"SenderEmail"* und *"RecipientEmail"* verwendet werden (d. h., der Connector importiert eine Chatnachricht in das Postfach des Absenders und die Postfächer jedes Empfängers), können Sie auch eine benutzerdefinierte Benutzerzuordnung definieren, indem Sie eine Datei für die CSV-Zuordnung hochladen. Diese Zuordnungsdatei enthält die ICE *Chat-ImId* und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer in Ihrer Organisation. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine Datei für die benutzerdefinierte Zuordnung bereitstellen, wird der Connector zunächst für jedes Chatelement die Datei für die benutzerdefinierte Zuordnung betrachten. Wenn kein gültiges Microsoft 365-Benutzerkonto gefunden wird, das der ICE Chat-ImId eines Benutzers entspricht, verwendet der Connector die *SenderEmail-* und *RecipientEmail-Eigenschaften* des Chatelements, um das Element in die Postfächer der Chatteilnehmer zu importieren. Wenn der Connector keinen gültigen Microsoft 365-Benutzer in der Benutzerdefinierten Zuordnungsdatei oder den *SenderEmail-* und *RecipientEmail-Eigenschaften* findet, wird das Element nicht importiert.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Einige der Implementierungsschritte, die zum Archivieren von ICE -Chatdaten erforderlich sind, sind außerhalb von Microsoft 365 und müssen abgeschlossen sein, bevor Sie den Connector im Compliance Center erstellen können.

- ICE Chat berechnet seinen Kunden eine Gebühr für die externe Compliance. Ihre Organisation sollte sich an die Ice Chat-Vertriebsgruppe wenden, um dies zu besprechen und den ICE Chat-Datendienstvertrag zu unterzeichnen, den Sie unter erhalten [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) können. Dieser Vertrag gilt zwischen ICE Chat und Ihrer Organisation und schließt Microsoft nicht ein. Nachdem Sie in Schritt 2 eine ICE Chat -SFTP-Website eingerichtet haben, stellt ICE Chat die FTP-Anmeldeinformationen direkt für Ihre Organisation zur Verfügung. Anschließend geben Sie microsoft diese Anmeldeinformationen beim Einrichten des Connectors in Schritt 3 an.

- Sie müssen einen ICE Chat -SFTP-Standort einrichten, bevor Sie den Connector in Schritt 3 erstellen. Nachdem Sie mit ICE Chat die Website SFTP eingerichtet haben, werden die Daten aus ICE Chat täglich auf die WEBSITE SFTP hochgeladen. Der connector, den Sie in Schritt 3 erstellen, stellt eine Verbindung mit dieser SFTP-Website und überträgt die Chatdaten an Microsoft 365-Postfächer. SFTP verschlüsselt auch die ICE Chat-Daten, die während des Übertragungsprozesses an Postfächer gesendet werden.

- Der ICE -Chat-Connector kann insgesamt 200.000 Elemente an einem einzigen Tag importieren. Wenn die Website SFTP mehr als 200.000 Elemente enthält, wird keines dieser Elemente in Microsoft 365 importiert.

- Dem Administrator, der den ICE -Chat-Connector in Schritt 3 erstellt (und der die öffentlichen Schlüssel und die IP-Adresse in Schritt 1 herunterlädt), muss die Rolle "Postfachimport/-export" in Exchange Online zugewiesen sein. Diese Rolle ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimport/-export" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimport/-export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) den [Abschnitten](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) "Rollengruppen erstellen" oder "Rollengruppen ändern" im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Schritt 1: Abrufen von öffentlichen SSH- und PGP-Schlüsseln

Der erste Schritt besteht im Abrufen einer Kopie der öffentlichen Schlüssel für SSH (Secure Shell) und Pretty Good Privacy (PGP). Verwenden Sie diese Schlüssel in Schritt 2, um den ICE Chat -SFTP-Standort so zu konfigurieren, dass der Connector (den Sie in Schritt 3 erstellen) eine Verbindung mit dem STANDORT SFTP herstellen und die ICE -Chatdaten an Microsoft 365-Postfächer übertragen kann. In diesem Schritt erhalten Sie auch eine IP-Adresse, die Sie beim Konfigurieren des ICE Chat -SFTP-Standorts verwenden.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) in der linken **Navigationsleiste zu Datenconnectors,** und klicken Sie auf diese.

2. Klicken Sie **auf der Seite "Datenconnectors"** unter **"ICE Chat"** auf **"Anzeigen".**

3. Klicken Sie **auf der Seite ICE Chat** auf **"Connector hinzufügen".**

4. Klicken Sie **auf der Seite "Nutzungsbedingungen"** auf **"Annehmen".**

5. Klicken Sie auf der Seite Zum Hinzufügen von Anmeldeinformationen für **die ICE Chat -SFTP-Website** unter Schritt 1 auf den Download-SSH-Schlüssel, den Download-PGP-Schlüssel und **die Download-IP-Adresslinks,** um eine Kopie jeder Datei auf Ihrem lokalen Computer zu speichern.   Diese Dateien enthalten die folgenden Elemente, die zum Konfigurieren der ICE Chat -SFTP-Website in Schritt 2 verwendet werden:

   - Öffentlicher SSH-Schlüssel: Dieser Schlüssel wird zum Konfigurieren von Secure SSH verwendet, um eine sichere Remoteanmeldung zu aktivieren, wenn der Connector eine Verbindung mit dem ICE Chat -SFTP-Standort herstellt.

   - Öffentlicher PGP-Schlüssel: Dieser Schlüssel wird verwendet, um die Verschlüsselung von Daten zu konfigurieren, die vom ICE Chat -SFTP-Standort an Microsoft 365 übertragen werden.

   - IP-Adresse: Der ICE Chat -SFTP-Standort ist so konfiguriert, dass nur eine Verbindungsanforderung von dieser IP-Adresse akzeptiert wird, die vom ICE Chat Connector verwendet wird, den Sie in Schritt 3 erstellt haben.

6. Klicken Sie **auf "Abbrechen",** um den Assistenten zu schließen. Sie kommen in Schritt 3 zu diesem Assistenten zurück, um den Connector zu erstellen.

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>Schritt 2: Konfigurieren der ICE Chat -SFTP-Website

Der nächste Schritt besteht in der Verwendung der öffentlichen SSH- und PGP-Schlüssel und der IP-Adresse, die Sie in Schritt 1 erhalten haben, um die SSH-Authentifizierung und die PGP-Verschlüsselung für den ICE Chat -SFTP-Standort zu konfigurieren. Dadurch kann der ice Chat-Connector, den Sie in Schritt 3 erstellen, eine Verbindung mit dem ICE Chat -SFTP-Standort herstellen und ICE -Chatdaten an Microsoft 365 übertragen. Sie müssen mit dem ICE Chat-Kundensupport zusammenarbeiten, um Ihre ICE Chat -SFTP-Website zu einrichten.

## <a name="step-3-create-an-ice-chat-connector"></a>Schritt 3: Erstellen eines ICE -Chatconnector

Der letzte Schritt besteht im Erstellen eines ICE -Chatconnector im Microsoft 365 Compliance Center. Der Connector verwendet die informationen, die Sie bereitstellen, um eine Verbindung mit dem ICE Chat -SFTP-Standort herzustellen und Chatnachrichten an die entsprechenden Benutzerpostfächer in Microsoft 365 zu übertragen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) in der linken **Navigationsleiste zu Datenconnectors,** und klicken Sie auf diese.

2. Klicken Sie **auf der Seite "Datenconnectors"** unter **"ICE Chat"** auf **"Anzeigen".**

3. Klicken Sie **auf der Seite ICE Chat** auf **"Connector hinzufügen".**

4. Klicken Sie **auf der Seite "Nutzungsbedingungen"** auf **"Annehmen".**

5. Geben Sie auf der Seite "Anmeldeinformationen für **ICE Chat -SFTP-Website** hinzufügen" unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **"Verbindung überprüfen".**

   - **Firmencode:** Die ID für Ihre Organisation, die als Benutzername für die ICE Chat -SFTP-Website verwendet wird.

   - **Kennwort:** Das Kennwort für Ihre ICE Chat SFTP-Website.

   - **SFTP-URL:** Die URL für den ICE Chat -SFTP-Standort (z. B. sftp.theice.com).

   - **SFTP-Port:** Die Portnummer für den ICE Chat SFTP-Standort. Der Connector verwendet diesen Port zum Herstellen einer Verbindung mit dem SFTP-Standort.

6. Nachdem die Verbindung überprüft wurde, klicken Sie auf **"Weiter".**

7. Aktivieren Sie auf der Seite "Externe **Benutzer microsoft 365-Benutzern** zuordnen" die automatische Benutzerzuordnung, und stellen Sie bei Bedarf eine benutzerdefinierte Benutzerzuordnung zur Verfügung. Sie können eine Kopie der Benutzerzuordnungs-CSV-Datei auf dieser Seite herunterladen. Sie können die Benutzerzuordnungen der Datei hinzufügen und dann hochladen.

   > [!NOTE]
   > Wie zuvor erläutert, enthält die benutzerdefinierte Zuordnungsdatei -CSV-Datei die ICE Chat-Imid und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer. Wenn Sie die automatische Benutzerzuordnung aktivieren und für jedes Chatelement eine benutzerdefinierte Zuordnung bereitstellen, wird zunächst die benutzerdefinierte Zuordnungsdatei vom Connector angezeigt. Wenn kein gültiger Microsoft 365-Benutzer gefunden wird, der der ICE Chat-Imid eines Benutzers entspricht, importiert der Connector das Element in die Postfächer für die Benutzer, die in den *SenderEmail-* und *RecipientEmail-Eigenschaften* des Chatelements angegeben sind. Wenn der Connector keinen gültigen Microsoft 365-Benutzer durch automatische oder benutzerdefinierte Benutzerzuordnung findet, wird das Element nicht importiert.

8. Klicken **Sie auf "Weiter",** überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **"Fertig** stellen", um den Connector zu erstellen.

9. Wechseln Sie zur **Seite "Datenconnectors",** um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.
