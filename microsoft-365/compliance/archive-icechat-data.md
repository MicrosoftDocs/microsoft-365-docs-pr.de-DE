---
title: Einrichten eines Connectors zum Archivieren von ICE Chat-Daten
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
description: Administratoren können einen Connector zum Importieren und Archivieren von Daten aus dem ICE Chat-Tool in Microsoft 365 einrichten. Auf diese Weise können Sie Daten aus Datenquellen von Drittanbietern in Microsoft 365 archivieren, damit Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: 663b122ec81a3d2d448e8d0abe5da0bdd9dc7313
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904183"
---
# <a name="set-up-a-connector-to-archive-ice-chat-data"></a>Einrichten eines Connectors zum Archivieren von ICE Chat-Daten

Verwenden Sie einen systemeigenen Connector im Microsoft 365 Compliance Center, um Finanzdienstchatdaten aus dem TOOL für die Zusammenarbeit im ICE Chat zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er einmal täglich eine Verbindung mit der SECURE FTP (SECURE FTP)-Website (SECURE FTP) Ihrer Organisation sicher, konvertiert den Inhalt von Chatnachrichten in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in Postfächer in Microsoft 365.

Nachdem ICE-Chatdaten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. die Aufbewahrung von Rechtsstreitigkeiten, eDiscovery, Archivierung, Überwachung, Kommunikationskonformität und Microsoft 365-Aufbewahrungsrichtlinien auf ICE Chat-Daten anwenden. Sie können z. B. ICE Chat-Nachrichten mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die ICE -Chat-Daten enthält, einem Custodian in einem Advanced eDiscovery-Fall zuordnen. Die Verwendung eines ICE-Chatconnector zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Richtlinien von Behörden und Behörden einhalten kann.

## <a name="overview-of-archiving-ice-chat-data"></a>Übersicht über die Archivierung von ICE Chat-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von ICE-Chatdaten in Microsoft 365 erläutert.

![ICE Chat-Archivierungsworkflow](../media/ICEChatConnectorWorkflow.png)

1. Ihre Organisation arbeitet mit ICE Chat zusammen, um eine ICE Chat -SFTP-Website zu einrichten. Sie arbeiten auch mit ICE Chat zusammen, um ICE Chat so zu konfigurieren, dass Chatnachrichten auf Ihre ICE Chat SFTP-Website kopiert werden.

2. Einmal alle 24 Stunden werden Chatnachrichten aus dem ICE Chat auf Ihre ICE Chat SFTP-Website kopiert.

3. Der ice chat connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit dem ICE Chat SFTP-Standort bereit und überträgt die Chatnachrichten aus den vorherigen 24 Stunden an einen sicheren Azure Storage-Speicherort in der Microsoft Cloud. Der Connector konvertiert auch den Inhalt einer Chat-Chat-Chats in ein E-Mail-Nachrichtenformat.

4. Der Connector importiert Chatnachrichtenelemente in die Postfächer bestimmter Benutzer. In den **Benutzerpostfächern** wird ein neuer Ordner namens ICE Chat erstellt, und die Chatnachrichtenelemente werden in diesen Ordner importiert. Der Connector verwendet den Wert der *Eigenschaften SenderEmail* und *RecipientEmail.* Jede Chatnachricht enthält diese Eigenschaften, die mit der E-Mail-Adresse des Absenders und jedem Empfänger/Teilnehmer der Chatnachricht gefüllt werden.

   Neben der automatischen Benutzerzuordnung, die die Werte der *Eigenschaft SenderEmail* und *RecipientEmail* verwendet (d. h. der Connector importiert eine Chatnachricht in das Postfach des Absenders und die Postfächer jedes Empfängers), können Sie auch eine benutzerdefinierte Benutzerzuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei enthält die ICE Chat *ImId* und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer in Ihrer Organisation. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnungsdatei bereitstellen, wird für jedes Chatelement zunächst die datei für die benutzerdefinierte Zuordnung vom Connector angezeigt. Wenn kein gültiges Microsoft 365-Benutzerkonto gefunden wird, das der ICE Chat-ImId eines Benutzers entspricht, verwendet der Connector die *Eigenschaften SenderEmail* und *RecipientEmail* des Chatelements, um das Element in die Postfächer der Chatteilnehmer zu importieren. Wenn der Connector keinen gültigen Microsoft 365-Benutzer in der benutzerdefinierten Zuordnungsdatei oder den *Eigenschaften SenderEmail* und *RecipientEmail* findet, wird das Element nicht importiert.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Einige der implementierungsschritte, die zum Archivieren von ICE Chat-Daten erforderlich sind, sind außerhalb von Microsoft 365 und müssen abgeschlossen sein, bevor Sie den Connector im Compliance Center erstellen können.

- ICE Chat berechnet seinen Kunden eine Gebühr für externe Compliance. Ihre Organisation sollte sich an die ICE Chat-Vertriebsgruppe wenden, um zu diskutieren und den ICE Chat-Datendienstevertrag zu unterzeichnen, den Sie unter erhalten [https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf](https://www.theice.com/publicdocs/agreements/ICE\_Data\_Services\_Agreement.pdf) können. Diese Vereinbarung besteht zwischen ICE Chat und Ihrer Organisation und schließt Microsoft nicht ein. Nachdem Sie eine ICE Chat -SFTP-Website in Schritt 2 eingerichtet haben, stellt ICE Chat die FTP-Anmeldeinformationen direkt für Ihre Organisation zur Verfügung. Anschließend stellen Sie microsoft diese Anmeldeinformationen beim Einrichten des Connectors in Schritt 3 zur Verfügung.

- Sie müssen einen ICE Chat -SFTP-Standort einrichten, bevor Sie den Connector in Schritt 3 erstellen. Nach der Arbeit mit ICE Chat zum Einrichten der SFTP-Website werden täglich Daten aus ICE Chat auf den SFTP-Standort hochgeladen. Der connector, den Sie in Schritt 3 erstellen, stellt eine Verbindung mit dieser SFTP-Website ein und überträgt die Chatdaten an Microsoft 365-Postfächer. SFTP verschlüsselt auch die ICE Chat-Daten, die während des Übertragungsprozesses an Postfächer gesendet werden.

- Der ICE Chat Connector kann insgesamt 200.000 Elemente an einem einzigen Tag importieren. Wenn mehr als 200.000 Elemente auf der SFTP-Website vorhanden sind, wird keines dieser Elemente nach Microsoft 365 importiert.

- Dem Administrator, der den ICE-Chatconnector in Schritt 3 erstellt (und der die öffentlichen Schlüssel und die IP-Adresse in Schritt 1 herunterlädt), muss die Rolle Postfachimportexport in Exchange Online zugewiesen werden. Diese Rolle ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Schritt 1: Abrufen öffentlicher SSH- und PGP-Schlüssel

Der erste Schritt besteht im Abrufen einer Kopie der öffentlichen Schlüssel für Secure Shell (SSH) und Pretty Good Privacy (PGP). Sie verwenden diese Schlüssel in Schritt 2, um den ICE Chat SFTP-Standort so zu konfigurieren, dass der Connector (den Sie in Schritt 3 erstellen) eine Verbindung mit dem SFTP-Standort herstellen und die ICE Chat-Daten an Microsoft 365-Postfächer übertragen kann. In diesem Schritt erhalten Sie auch eine IP-Adresse, die Sie beim Konfigurieren des ICE Chat SFTP-Standorts verwenden.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie **auf der Seite Datenconnectors** unter **ICE Chat** auf **Anzeigen**.

3. Klicken Sie **auf der Seite ICE-Chat** auf **Connector hinzufügen.**

4. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

5. Klicken Sie auf der Seite Anmeldeinformationen für **ICE Chat SFTP** unter Schritt 1 hinzufügen auf die Links **SSH-Schlüssel** herunterladen, **PGP-Schlüssel** herunterladen und IP-Adresslinks herunterladen, um eine Kopie jeder Datei auf Ihrem lokalen Computer zu speichern.  Diese Dateien enthalten die folgenden Elemente, die zum Konfigurieren der ICE Chat -SFTP-Website in Schritt 2 verwendet werden:

   - Öffentlicher SSH-Schlüssel: Dieser Schlüssel wird verwendet, um Secure SSH zu konfigurieren, um eine sichere Remoteanmeldung zu ermöglichen, wenn der Connector eine Verbindung mit dem ICE Chat SFTP-Standort herstellt.

   - Öffentlicher PGP-Schlüssel: Dieser Schlüssel wird verwendet, um die Verschlüsselung von Daten zu konfigurieren, die vom ICE Chat SFTP-Standort an Microsoft 365 übertragen werden.

   - IP-Adresse: Der ICE Chat SFTP-Standort ist so konfiguriert, dass er eine Verbindungsanforderung nur von dieser IP-Adresse akzeptiert, die vom ice chat connector verwendet wird, den Sie in Schritt 3 erstellen.

6. Klicken **Sie auf Abbrechen,** um den Assistenten zu schließen. Sie kommen in Schritt 3 zu diesem Assistenten zurück, um den Connector zu erstellen.

## <a name="step-2-configure-the-ice-chat-sftp-site"></a>Schritt 2: Konfigurieren der ICE Chat -SFTP-Website

Der nächste Schritt besteht in der Verwendung der öffentlichen SSH- und PGP-Schlüssel und der in Schritt 1 erhaltenen IP-Adresse, um die SSH-Authentifizierung und die PGP-Verschlüsselung für den ICE Chat SFTP-Standort zu konfigurieren. Auf diese Weise kann der in Schritt 3 erstellte ICE Chat-Connector eine Verbindung mit dem ICE Chat -SFTP-Standort herstellen und ICE Chat-Daten an Microsoft 365 übertragen. Sie müssen mit dem ICE Chat-Kundensupport zusammenarbeiten, um Ihre ICE Chat SFTP-Website einrichten zu können.

## <a name="step-3-create-an-ice-chat-connector"></a>Schritt 3: Erstellen eines ICE-Chatconnector

Der letzte Schritt besteht im Erstellen eines ICE-Chatconnector im Microsoft 365 Compliance Center. Der Connector verwendet die informationen, die Sie bereitstellen, um eine Verbindung mit der ICE Chat -SFTP-Website herzustellen und Chatnachrichten an die entsprechenden Benutzerpostfächer in Microsoft 365 zu übertragen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) zu, und klicken Sie **im** linken Navigations navi auf Datenconnectors.

2. Klicken Sie **auf der Seite Datenconnectors** unter **ICE Chat** auf **Anzeigen**.

3. Klicken Sie **auf der Seite ICE-Chat** auf **Connector hinzufügen.**

4. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

5. Geben Sie auf der Seite Anmeldeinformationen für **ICE Chat SFTP** hinzufügen unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf Verbindung **überprüfen.**

   - **Firmencode:** Die ID für Ihre Organisation, die als Benutzername für die ICE Chat SFTP-Website verwendet wird.

   - **Kennwort:** Das Kennwort für Ihre ICE Chat SFTP-Website.

   - **SFTP-URL:** Die URL für die ICE Chat -SFTP-Website (z. B. sftp.theice.com).

   - **SFTP-Port:** Die Portnummer für den ICE Chat SFTP-Standort. Der Connector verwendet diesen Port, um eine Verbindung mit dem SFTP-Standort herzustellen.

6. Klicken Sie nach der Überprüfung der Verbindung auf **Weiter**.

7. Aktivieren Sie auf der Seite Externe Benutzer **zu Microsoft 365-Benutzern** zuordnen die automatische Benutzerzuordnung, und stellen Sie bei Bedarf eine benutzerdefinierte Benutzerzuordnung zur Verfügung. Sie können eine Kopie der BENUTZERzuordnungs-CSV-Datei auf dieser Seite herunterladen. Sie können die Benutzerzuordnungen der Datei hinzufügen und dann hochladen.

   > [!NOTE]
   > Wie bereits erläutert, enthält die benutzerdefinierte Zuordnungsdatei -CSV-Datei die ICE Chat-Imid und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird für jedes Chatelement zunächst die benutzerdefinierte Zuordnungsdatei vom Connector angezeigt. Wenn kein gültiger Microsoft 365-Benutzer gefunden wird, der der ICE Chat-Imid eines Benutzers entspricht, importiert der Connector das Element in die Postfächer für die Benutzer, die in den *Eigenschaften SenderEmail* und *RecipientEmail* des Chatelements angegeben sind. Wenn der Connector keinen gültigen Microsoft 365-Benutzer durch automatische oder benutzerdefinierte Benutzerzuordnung findet, wird das Element nicht importiert.

8. Klicken **Sie auf Weiter,** überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen,** um den Connector zu erstellen.

9. Wechseln Sie zur **Seite Datenconnectors,** um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.