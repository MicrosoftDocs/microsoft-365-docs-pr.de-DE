---
title: Einrichten eines Connectors zum Archivieren von Bloomberg-Nachrichtendaten
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
description: Administratoren können einen Datenconnector einrichten, um Daten aus dem E-Mail-Tool Bloomberg Message in Microsoft 365 zu importieren und zu archivieren. Auf diese Weise können Sie Daten aus Drittanbieterdatenquellen in Microsoft 365 archivieren, sodass Sie Compliancefeatures wie gesetzliche Aufbewahrung, Inhaltssuche und Aufbewahrungsrichtlinien verwenden können, um die Drittanbieterdaten Ihrer Organisation zu verwalten.
ms.openlocfilehash: f9b082dace9301f5a664078e9028c646ffa28483
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790115"
---
# <a name="set-up-a-connector-to-archive-bloomberg-message-data"></a>Einrichten eines Connectors zum Archivieren von Bloomberg-Nachrichtendaten

Verwenden Sie einen Datenconnector im Microsoft 365 Compliance Center, um Finanzdienstleister-E-Mail-Daten aus dem [Bloomberg Message Collaboration](https://www.bloomberg.com/professional/product/collaboration/) Tool zu importieren und zu archivieren. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, verbindet er sich einmal täglich mit dem Bloomberg Secure FTP (SFTP)-Standort Ihrer Organisation und importiert E-Mail-Elemente in Postfächer in Microsoft 365.

Nachdem Die Nachrichtendaten von Bloomberg in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. das Aufbewahrungsverfahren für Rechtsstreitigkeiten, die Inhaltssuche, die In-Place-Archivierung, Überwachung, Kommunikationskonformität und Microsoft 365-Aufbewahrungsrichtlinien auf Bloomberg-Nachrichtendaten anwenden. Sie können beispielsweise Bloomberg-Nachrichten-E-Mails mithilfe des Inhaltssuchtools durchsuchen oder das Postfach, das die Bloomberg -Nachrichtendaten enthält, einem Wahrer in einem Advanced eDiscovery-Fall zuordnen. Die Verwendung eines Bloomberg-Nachrichtenconnector zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation den behördlichen und behördlichen Richtlinien entspricht.

## <a name="overview-of-archiving-bloomberg-message-data"></a>Übersicht über die Archivierung von Bloomberg-Nachrichtendaten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Bloomberg-Nachrichtendaten in Microsoft 365 erläutert.

![Import- und Archivprozess für Bloomberg-Nachrichten](../media/BloombergMessageArchiving.png)

1. Ihre Organisation arbeitet mit Bloomberg zusammen, um eine Bloomberg -SFTP-Website zu einrichten. Sie arbeiten auch mit Bloomberg zusammen, um Bloomberg Message so zu konfigurieren, dass E-Mail-Nachrichten an die Bloomberg -SFTP-Website kopiert werden.

2. Alle 24 Stunden werden E-Mail-Nachrichten von Bloomberg Message an die Bloomberg -SFTP-Website kopiert.

3. Der Bloomberg-Nachrichtenconnector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der Bloomberg -SFTP-Website sicher und überträgt die E-Mail-Nachrichten aus den letzten 24 Stunden an einen sicheren Azure Storage-Bereich in der Microsoft Cloud.

4. Der Connector importiert die E-Mail-Nachrichtenelemente in das Postfach eines bestimmten Benutzers. Ein neuer Ordner namens BloombergMessage wird im Postfach des bestimmten Benutzers erstellt, und die Elemente werden in das Postfach importiert. 

   Der Connector verwendet dazu den Wert der Eigenschaft CorporateEmailAddress. Jede E-Mail-Nachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der E-Mail-Nachricht aufgefüllt wird. Zusätzlich zur automatischen Benutzerzuordnung mithilfe des Werts der Eigenschaft *CorporateEmailAddress* können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei enthält eine Bloomberg UUID und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer in Ihrer Organisation. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird der Connector zunächst für jedes E-Mail-Element die Datei für die benutzerdefinierte Zuordnung betrachten. Wenn sie keinen gültigen Microsoft 365-Benutzer findet, der der Bloomberg UUID eines Benutzers entspricht, verwendet der Connector die Eigenschaft *CorporateEmailAddress* des E-Mail-Elements. Wenn der Connector keinen gültigen Microsoft 365-Benutzer in der Datei für die benutzerdefinierte Zuordnung oder in der *Eigenschaft CorporateEmailAddress* des E-Mail-Elements findet, wird das Element nicht importiert.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Einige der implementierungsschritte erforderlich, um Bloomberg Nachrichtendaten zu archivieren sind außerhalb von Microsoft 365 und müssen abgeschlossen werden, bevor Sie den Connector im Compliance Center erstellen können.

- Abonnieren Sie [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Dies ist erforderlich, damit Sie sich bei Bloomberg Anywhere anmelden können, um auf die Bloomberg -SFTP-Website zu zugreifen, die Sie einrichten und konfigurieren müssen.

- Richten Sie eine Bloomberg SFTP (Secure File Transfer Protocol)-Website ein. Nachdem Sie mit Bloomberg die Website SFTP eingerichtet haben, werden die Daten von Bloomberg Message täglich auf die Website SFTP hochgeladen. Der connector, den Sie in Schritt 2 erstellen, stellt eine Verbindung mit dieser SFTP-Website und überträgt die E-Mail-Daten an Microsoft 365-Postfächer. SFTP verschlüsselt auch die Bloomberg-Nachrichtendaten, die während des Übertragungsprozesses an Postfächer gesendet werden.

  Weitere Informationen zu Bloomberg SFTP (auch *BB-SFTP genannt)* finden Sie hier:

  - Weitere Informationen finden Sie im Dokument "SFTP Connectivity Standards" bei [Bloomberg Support.](https://www.bloomberg.com/professional/support/documentation/)

  - Wenden [Sie sich an den Bloomberg-Kundensupport.](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc)

   > [!NOTE]
   > Wenn Ihre Organisation bereits einen Connector zum Archivieren von Instant Bloomberg-Daten bereitgestellt hat, müssen Sie keinen weiteren Standort für SFTP einrichten. Sie können denselben STANDORT für den Bloomberg Message Connector verwenden.

- Nachdem Sie mit Bloomberg an der Einrichtung einer -SFTP-Website arbeiten, stellt Bloomberg Ihnen einige Informationen zur Verfügung, nachdem Sie auf die E-Mail-Nachricht zur Implementierung von Bloomberg reagiert haben. Speichern Sie eine Kopie der folgenden Informationen. Sie verwenden ihn zum Einrichten eines Connectors in Schritt 3.

  - Firmencode, der eine ID für Ihre Organisation ist und zur Anmeldung bei der Bloomberg -SFTP-Website verwendet wird.

  - Kennwort für Ihre Bloomberg -SFTP-Website

  - URL für bloomberg-SFTP-Website (z. B. sftp.bloomberg.com). Darüber hinaus kann Bloomberg auch eine entsprechende IP-Adresse für den Bloomberg -SFTP-Standort bereitstellen, die auch zum Einrichten des Connectors verwendet werden kann.

  - Portnummer für bloomberg-SFTP-Website

- Der Bloomberg Message Connector kann insgesamt 200.000 Elemente an einem einzigen Tag importieren. Wenn die Website SFTP mehr als 200.000 Elemente enthält, wird keines dieser Elemente in Microsoft 365 importiert.

- Dem Benutzer, der in Schritt 3 einen Bloomberg-Nachrichtenconnector erstellt (und der die öffentlichen Schlüssel und die IP-Adresse in Schritt 1 herunterlädt), muss die Rolle "Postfachimport/-export" in Exchange Online zugewiesen sein. Dies ist erforderlich, um Connectors auf der Seite **"Datenconnectors"** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Postfachimport/-export" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Postfachimport/-export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in [](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) den [Abschnitten](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) "Rollengruppen erstellen" oder "Rollengruppen ändern" im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Schritt 1: Abrufen von öffentlichen SSH- und PGP-Schlüsseln

Der erste Schritt besteht im Abrufen einer Kopie der öffentlichen Schlüssel für SSH (Secure Shell) und Pretty Good Privacy (PGP). Sie verwenden diese Schlüssel in Schritt 2, um die Bloomberg -SFTP-Website so zu konfigurieren, dass der Connector (den Sie in Schritt 3 erstellen) eine Verbindung mit der SFTP-Website herstellen und die Bloomberg Message-E-Mail-Daten an Microsoft 365-Postfächer übertragen kann. Sie erhalten in diesem Schritt auch eine IP-Adresse, die Sie beim Konfigurieren der Bloomberg -SFTP-Website verwenden.

1. Wechseln Sie zu [ https://compliance.microsoft.com\ ]( https://compliance.microsoft.com) und klicken **Sie** im linken Navigationsgerät auf Datenconnectors.

2. Klicken Sie **auf der Seite "Datenconnectors"** unter **"Bloomberg-Nachricht"** auf **"Anzeigen".**

3. Klicken Sie **auf der Seite "Bloomberg Message** product description" auf **"Connector hinzufügen".**

4. Klicken Sie **auf der Seite "Nutzungsbedingungen"** auf **"Annehmen".**

5. Klicken Sie auf der **Bloomberg -SFTP-Website** unter Schritt 1 auf den **Download-SSH-Schlüssel,** den **Download-PGP-Schlüssel** und die **Download-IP-Adresslinks,** um eine Kopie jeder Datei auf Ihrem lokalen Computer zu speichern. Diese Dateien enthalten die folgenden Elemente, die zum Konfigurieren der Bloomberg -SFTP-Website in Schritt 2 verwendet werden:

   - Öffentlicher SSH-Schlüssel: Dieser Schlüssel wird verwendet, um Secure Shell (SSH) so zu konfigurieren, dass eine sichere Remoteanmeldung aktiviert wird, wenn der Connector eine Verbindung mit der Bloomberg -SFTP-Website herstellt.

   - Öffentlicher PGP-Schlüssel: Dieser Schlüssel wird verwendet, um die Verschlüsselung von Daten zu konfigurieren, die vom Bloomberg -SFTP-Standort an Microsoft 365 übertragen werden.

   - IP-Adresse: Der Bloomberg -SFTP-Standort ist so konfiguriert, dass nur eine Verbindungsanforderung von dieser IP-Adresse akzeptiert wird, die vom bloomberg-Nachrichtenconnector verwendet wird, den Sie in Schritt 3 erstellt haben.

6. Klicken Sie **auf "Abbrechen",** um den Assistenten zu schließen. Sie kommen in Schritt 3 zu diesem Assistenten zurück, um den Connector zu erstellen.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Schritt 2: Konfigurieren der Bloomberg -SFTP-Website

> [!NOTE]
> Wie bereits erwähnt, müssen Sie, wenn Ihre Organisation zuvor eine Bloomberg -SFTP-Website zum Archivieren von Instant Bloomberg-Daten eingerichtet hat, keine weitere einrichten. Beim Erstellen des Connectors in Schritt 3 können Sie denselben Standort für sfTP angeben.

Der nächste Schritt besteht in der Verwendung der öffentlichen SSH- und PGP-Schlüssel und der IP-Adresse, die Sie in Schritt 1 erhalten haben, um die SSH-Authentifizierung und die PGP-Verschlüsselung für den Bloomberg -SFTP-Standort zu konfigurieren. Dadurch kann der in Schritt 3 erstellten Bloomberg-Nachrichtenconnector eine Verbindung mit der Bloomberg -SFTP-Website herstellen und Bloomberg-Nachrichtendaten an Microsoft 365 übertragen. Sie müssen mit dem Bloomberg-Kundensupport zusammenarbeiten, um Ihre Bloomberg -SFTP-Website zu einrichten. Wenden [Sie sich an den Bloomberg-Kundensupport,](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) um Unterstützung zu erhalten.

> [!IMPORTANT]
> Bloomberg empfiehlt, die drei Dateien, die Sie in Schritt 1 heruntergeladen haben, an eine E-Mail-Nachricht anfügen und diese an das Kundensupportteam zu senden, wenn Sie mit ihnen zusammenarbeiten, um Ihre Bloomberg -SFTP-Website zu einrichten.

## <a name="step-3-create-a-bloomberg-message-connector"></a>Schritt 3: Erstellen eines Bloomberg-Nachrichtenconnector

Der letzte Schritt besteht im Erstellen eines Bloomberg-Nachrichtenconnector im Microsoft 365 Compliance Center. Der Connector verwendet die informationen, die Sie bereitstellen, um eine Verbindung mit der Bloomberg -SFTP-Website herzustellen und E-Mail-Nachrichten an die entsprechenden Benutzerpostfächer in Microsoft 365 zu übertragen.

1. Wechseln Sie [https://compliance.microsoft.com](https://compliance.microsoft.com) in der linken **Navigationsleiste zu Datenconnectors,** und klicken Sie auf diese.

2. Klicken Sie **auf der Seite "Datenconnectors"** unter **"Bloomberg-Nachricht"** auf **"Anzeigen".**

3. Klicken Sie **auf der Seite "Bloomberg Message** product description" auf **"Connector hinzufügen".**

4. Klicken Sie **auf der Seite "Nutzungsbedingungen"** auf **"Annehmen".**

5. Geben Sie auf der Seite **"Anmeldeinformationen für Bloomberg SFTP** hinzufügen" unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **"Weiter".**

      - **Firmencode:** Die ID für Ihre Organisation, die als Benutzername für die Bloomberg -SFTP-Website verwendet wird.

      - **Kennwort:** Das Kennwort für die Bloomberg-SFTP-Website Ihrer Organisation.

      - **SFTP-URL:** Die URL für die Bloomberg -SFTP-Website (z. B. sftp.bloomberg.com).

      - **SFTP-Port:** Die Portnummer für den Bloomberg SFTP-Standort. Der Connector verwendet diesen Port zum Herstellen einer Verbindung mit dem SFTP-Standort.

6. Aktivieren Sie **auf der Seite** "Benutzerzuordnung" die automatische Benutzerzuordnung, und stellen Sie bei Bedarf eine benutzerdefinierte Benutzerzuordnung zur Verfügung.

7. Klicken **Sie auf "Weiter",** überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf "Connector erstellen".

8. Wechseln Sie zur **Seite "Datenconnectors",** um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.

## <a name="known-issues"></a>Bekannte Probleme

- Threading von in Microsoft 365 importierten Bloomberg-Nachrichten-E-Mails wird nicht unterstützt. Einzelne Nachrichten, die an eine Person gesendet werden, werden importiert, werden jedoch nicht in einer Unterhaltung im Thread angezeigt. Microsoft arbeitet daran, Threading in späteren Versionen des Bloomberg Message Data Connectors zu unterstützen.
