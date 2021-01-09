---
title: Einrichten eines Connectors zum Archivieren von Instant Bloomberg-Daten
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
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom: seo-marvel-apr2020
description: Erfahren Sie, wie Administratoren einen Datenconnector einrichten und verwenden können, um Daten aus dem Instant Bloomberg-Chattool in Microsoft 365 zu importieren und zu archivieren.
ms.openlocfilehash: b7cd35e0613d9c278e8f36efc194de9dc9b5a5f2
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790093"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>Einrichten eines Connectors zum Archivieren von Instant Bloomberg-Daten

Verwenden Sie einen nativen Connector im Microsoft 365 Compliance Center zum Importieren und Archivieren von Chatdaten für Finanzdienstleistungen aus dem Instant Bloomberg-Zusammenarbeitstool. [](https://www.bloomberg.com/professional/product/collaboration/) Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er einmal täglich eine Verbindung mit der Secure FTP Site (SFTP) von Bloomberg in Ihrer Organisation sicher, konvertiert den Inhalt von Chatnachrichten in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in Postfächer in Microsoft 365.

Nachdem Instant Bloomberg-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. das Aufbewahrungsverfahren für Rechtsstreitigkeiten, die Inhaltssuche, In-Place-Archivierung, Überwachung, Kommunikationskonformität und Microsoft 365-Aufbewahrungsrichtlinien auf Instant Bloomberg-Daten anwenden. Beispielsweise können Sie Chatnachrichten in Instant Bloomberg mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die Instant Bloomberg-Daten enthält, einem Verwahrer in einem Advanced eDiscovery-Fall zuordnen. Die Verwendung eines Instant Bloomberg-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den behördlichen und behördlichen Richtlinien entspricht.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Übersicht über die Archivierung von Instant Bloomberg-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Chatdaten von Instant Bloomberg in Microsoft 365 erläutert. 

![Import- und Archivprozess für Instant Bloomberg](../media/InstantBloombergDataArchiving.png)

1. Ihre Organisation arbeitet mit Bloomberg zusammen, um eine Bloomberg -SFTP-Website zu einrichten. Sie arbeiten auch mit Bloomberg zusammen, um Instant Bloomberg so zu konfigurieren, dass Chatnachrichten auf Ihre Bloomberg -SFTP-Website kopiert werden.

2. Einmal alle 24 Stunden werden Chatnachrichten aus Instant Bloomberg auf die Bloomberg -SFTP-Website kopiert.

3. Der Instant Bloomberg-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der Bloomberg -SFTP-Website sicher und überträgt die Chatnachrichten aus den letzten 24 Stunden an einen sicheren Azure Storage-Bereich in der Microsoft Cloud. Der Connector konvertiert auch den Inhalt eines Chatnachrichtenformats in ein E-Mail-Nachrichtenformat.

4. Der Connector importiert die Chatnachrichtenelemente in das Postfach eines bestimmten Benutzers. Im Postfach des jeweiligen Benutzers wird ein neuer Ordner mit dem Namen "InstantBloomberg" erstellt, in den die Elemente importiert werden. Der Connector verwendet dazu den Wert der *Eigenschaft CorporateEmailAddress.* Jede Chatnachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der Chatnachricht aufgefüllt wird. Zusätzlich zur automatischen Benutzerzuordnung mithilfe des Werts der Eigenschaft *CorporateEmailAddress* können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei sollte eine Bloomberg UUID und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird der Connector zunächst für jedes Chatelement die Datei für die benutzerdefinierte Zuordnung betrachten. Wenn es keinen gültigen Microsoft 365-Benutzer findet, der der Bloomberg UUID eines Benutzers entspricht, verwendet der Connector die Eigenschaft *CorporateEmailAddress* des Chatelements. Wenn der Connector keinen gültigen Microsoft 365-Benutzer in der Datei für die benutzerdefinierte Zuordnung oder in der Eigenschaft *"CorporateEmailAddress"* des Chatelements findet, wird das Element nicht importiert.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Einige der erforderlichen Implementierungsschritte zum Archivieren von Instant Bloomberg-Daten sind außerhalb von Microsoft 365 und müssen abgeschlossen sein, bevor Sie den Connector im Compliance Center erstellen können.

- Abonnieren Sie [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Dies ist erforderlich, damit Sie sich bei Bloomberg Anywhere anmelden können, um auf die Bloomberg -SFTP-Website zu zugreifen, die Sie einrichten und konfigurieren müssen.

- Richten Sie eine Bloomberg SFTP (Secure File Transfer Protocol)-Website ein. Nachdem Sie mit Bloomberg die Website SFTP eingerichtet haben, werden die Daten aus Instant Bloomberg täglich auf die SFTP-Website hochgeladen. Der connector, den Sie in Schritt 2 erstellen, stellt eine Verbindung mit dieser SFTP-Website und überträgt die Chatdaten an Microsoft 365-Postfächer. SFTP verschlüsselt auch die Chatdaten von Instant Bloomberg, die während des Übertragungsprozesses an Postfächer gesendet werden.

  Weitere Informationen zu Bloomberg SFTP (auch *BB-SFTP genannt)* finden Sie hier:

  - Weitere Informationen finden Sie im Dokument "SFTP Connectivity Standards" bei [Bloomberg Support.](https://www.bloomberg.com/professional/support/documentation/)

  - Wenden [Sie sich an den Bloomberg-Kundensupport.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

  Nachdem Sie mit Bloomberg an der Einrichtung einer -SFTP-Website arbeiten, stellt Bloomberg Ihnen einige Informationen zur Verfügung, nachdem Sie auf die E-Mail-Nachricht zur Implementierung von Bloomberg reagiert haben. Speichern Sie eine Kopie der folgenden Informationen. Sie verwenden ihn zum Einrichten eines Connectors in Schritt 3.

  - Firmencode, der eine ID für Ihre Organisation ist und zur Anmeldung bei der Bloomberg -SFTP-Website verwendet wird.

  - Kennwort für Ihre Bloomberg -SFTP-Website

  - URL für Bloomberg -SFTP-Website (z. B. sftp.bloomberg.com)

  - Portnummer für bloomberg-SFTP-Website

- Der Instant Bloomberg Connector kann insgesamt 200.000 Elemente an einem einzigen Tag importieren. Wenn die Website SFTP mehr als 200.000 Elemente enthält, wird keines dieser Elemente in Microsoft 365 importiert.

- Dem Benutzer, der in Schritt 3 einen Instant Bloomberg Connector erstellt (und der die öffentlichen Schlüssel und die IP-Adresse in Schritt 1 herunterlädt), muss die Rolle "Postfachimport/-export" in Exchange Online zugewiesen sein. Dies ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimport/-export" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimport/-export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) den [Abschnitten](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) "Rollengruppen erstellen" oder "Rollengruppen ändern" im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Schritt 1: Abrufen von öffentlichen SSH- und PGP-Schlüsseln

Der erste Schritt besteht im Abrufen einer Kopie der öffentlichen Schlüssel für SSH (Secure Shell) und Pretty Good Privacy (PGP). Sie verwenden diese Schlüssel in Schritt 2, um die Bloomberg -SFTP-Website so zu konfigurieren, dass der Connector (den Sie in Schritt 3 erstellen) eine Verbindung mit der SFTP-Website herstellen und die Chatdaten von Instant Bloomberg an Microsoft 365-Postfächer übertragen kann. Sie erhalten in diesem Schritt auch eine IP-Adresse, die Sie beim Konfigurieren der Bloomberg -SFTP-Website verwenden.

1. Wechseln Sie <https://compliance.microsoft.com> zu Und klicken Sie dann auf **"Datenconnectors**  >  **Instant Bloomberg".**

2. Klicken Sie **auf der Produktbeschreibungsseite** von Instant Bloomberg auf **"Connector hinzufügen".**

3. Klicken Sie **auf der Seite "Nutzungsbedingungen"** auf **"Annehmen".**

4. Klicken Sie auf der **Bloomberg -SFTP-Website** unter Schritt 1 auf den **Download-SSH-Schlüssel,** den **Download-PGP-Schlüssel** und die **Download-IP-Adresslinks,** um eine Kopie jeder Datei auf Ihrem lokalen Computer zu speichern. Diese Dateien enthalten die folgenden Elemente, die zum Konfigurieren der Bloomberg -SFTP-Website in Schritt 2 verwendet werden:

   - Öffentlicher SSH-Schlüssel: Dieser Schlüssel wird verwendet, um Secure Shell (SSH) so zu konfigurieren, dass eine sichere Remoteanmeldung aktiviert wird, wenn der Connector eine Verbindung mit der Bloomberg -SFTP-Website herstellt.

   - Öffentlicher PGP-Schlüssel: Dieser Schlüssel wird verwendet, um die Verschlüsselung von Daten zu konfigurieren, die vom Bloomberg -SFTP-Standort an Microsoft 365 übertragen werden.

   - IP-Adresse: Die Bloomberg -SFTP-Website ist so konfiguriert, dass nur eine Verbindungsanforderung von dieser IP-Adresse akzeptiert wird, die vom Instant Bloomberg-Connector verwendet wird, den Sie in Schritt 3 erstellt haben. 

5. Klicken Sie **auf "Abbrechen",** um den Assistenten zu schließen. Sie kommen in Schritt 3 zu diesem Assistenten zurück, um den Connector zu erstellen.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Schritt 2: Konfigurieren der Bloomberg -SFTP-Website

Der nächste Schritt besteht in der Verwendung der öffentlichen SSH- und PGP-Schlüssel und der IP-Adresse, die Sie in Schritt 1 erhalten haben, um die SSH-Authentifizierung und die PGP-Verschlüsselung für den Bloomberg -SFTP-Standort zu konfigurieren. Dadurch kann der In-Bloomberg-Connector, den Sie in Schritt 3 erstellen, eine Verbindung mit der Bloomberg -SFTP-Website herstellen und Instant Bloomberg-Daten an Microsoft 365 übertragen. Sie müssen mit dem Bloomberg-Kundensupport zusammenarbeiten, um Ihre Bloomberg -SFTP-Website zu einrichten. Wenden [Sie sich an den Bloomberg-Kundensupport,](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) um Unterstützung zu erhalten. 

> [!IMPORTANT]
> Bloomberg empfiehlt, die drei Dateien, die Sie in Schritt 1 heruntergeladen haben, an eine E-Mail-Nachricht anfügen und diese an das Kundensupportteam zu senden, wenn Sie mit ihnen zusammenarbeiten, um Ihre Bloomberg -SFTP-Website zu einrichten.

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Schritt 3: Erstellen eines Instant Bloomberg-Connectors

Der letzte Schritt besteht im Erstellen eines Instant Bloomberg-Connectors im Microsoft 365 Compliance Center. Der Connector verwendet die informationen, die Sie bereitstellen, um eine Verbindung mit der Bloomberg -SFTP-Website herzustellen und Chatnachrichten an die entsprechenden Benutzerpostfachfelder in Microsoft 365 zu übertragen.

1. Wechseln Sie <https://compliance.microsoft.com> zu Und klicken Sie dann auf **"Datenconnectors**  >  **Instant Bloomberg".**

2. Klicken Sie **auf der Produktbeschreibungsseite** von Instant Bloomberg auf **"Connector hinzufügen".**

3. Klicken Sie **auf der Seite "Nutzungsbedingungen"** auf **"Annehmen".**

4. Geben Sie auf der Seite **"Anmeldeinformationen für Bloomberg SFTP** hinzufügen" unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **"Weiter".**

    - **Firmencode:** Die ID für Ihre Organisation, die als Benutzername für die Bloomberg -SFTP-Website verwendet wird.

    - **Kennwort:** Kennwort für die Bloomberg SFTP-Website.

    - **SFTP-URL:** Die URL für die Bloomberg-SFTP-Website (z. B. sftp.bloomberg.com).

    - **SFTP-Port:** Die Portnummer für den Bloomberg SFTP-Standort. Der Connector verwendet diesen Port zum Herstellen einer Verbindung mit dem SFTP-Standort.

5. Wählen Sie **auf der Seite "Zu importierende** Datentypen auswählen" die erforderlichen Datentypen aus, die getrennt von Nachrichten importiert werden **sollen.**

6. Aktivieren Sie **auf der Seite** "Benutzerzuordnung" die automatische Benutzerzuordnung, und stellen Sie bei Bedarf eine benutzerdefinierte Benutzerzuordnung zur Verfügung.

   > [!NOTE]
   > Der Connector importiert die Chatnachrichtenelemente in das Postfach eines bestimmten Benutzers. Im Postfach des jeweiligen Benutzers wird ein neuer Ordner mit dem Namen **"InstantBloomberg"** erstellt, in den die Elemente importiert werden. Der Connector verwendet den Wert der *Eigenschaft CorporateEmailAddress.* Jede Chatnachricht enthält diese Eigenschaft, und die Eigenschaft wird mit der E-Mail-Adresse jedes Teilnehmers der Chatnachricht aufgefüllt. Zusätzlich zur automatischen Benutzerzuordnung mithilfe des Werts der Eigenschaft *CorporateEmailAddress* können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine DATEI für die CSV-Zuordnung hochladen. Die Zuordnungsdatei sollte die Bloomberg UUID und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird der Connector zunächst für jedes Chatelement die benutzerdefinierte Zuordnungsdatei betrachten. Wenn es keinen gültigen Microsoft 365-Benutzer findet, der der Bloomberg UUID eines Benutzers entspricht, verwendet der Connector die Eigenschaft *CorporateEmailAddress* des Chatelements. Wenn der Connector keinen gültigen Microsoft 365-Benutzer in der benutzerdefinierten Zuordnungsdatei oder der *Eigenschaft CorporateEmailAddress* des Chatelements findet, wird das Element nicht importiert.

7. Klicken **Sie auf "Weiter",** überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **"Connector** erstellen".

8. Wechseln Sie zur **Seite "Datenconnectors",** um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.
