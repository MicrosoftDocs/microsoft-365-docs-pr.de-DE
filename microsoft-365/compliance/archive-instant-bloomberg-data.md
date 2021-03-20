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
ms.openlocfilehash: 6a7f05f592da1b0413d2d40f364f67e7120168b9
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904173"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>Einrichten eines Connectors zum Archivieren von Instant Bloomberg-Daten

Verwenden Sie einen systemeigenen Connector im Microsoft 365 Compliance Center zum Importieren und Archivieren von Finanzdienstchatdaten aus dem [Instant Bloomberg-Tool](https://www.bloomberg.com/professional/product/collaboration/) für die Zusammenarbeit. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, verbindet er sich einmal täglich mit der Bloomberg Secure FTP Site (SFTP) Ihrer Organisation, konvertiert den Inhalt von Chatnachrichten in ein E-Mail-Nachrichtenformat und importiert diese Elemente dann in Postfächer in Microsoft 365.

Nachdem Instant Bloomberg-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliancefeatures wie z. B. Das Aufbewahrungsverfahren für Rechtsstreitigkeiten, die Inhaltssuche, In-Place-Archivierung, Überwachung, Kommunikationskonformität und Microsoft 365-Aufbewahrungsrichtlinien auf Instant Bloomberg-Daten anwenden. Sie können beispielsweise Chatnachrichten von Instant Bloomberg mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die Instant Bloomberg-Daten enthält, einem Custodian in einem Advanced eDiscovery-Fall zuordnen. Die Verwendung eines Instant Bloomberg-Connectors zum Importieren und Archivieren von Daten in Microsoft 365 kann Dazu beitragen, dass Ihre Organisation die Behördlichen und behördlichen Richtlinien einhalten kann.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Übersicht über die Archivierung von Instant Bloomberg-Daten

In der folgenden Übersicht wird der Prozess der Verwendung eines Connectors zum Archivieren von Instant Bloomberg-Chatdaten in Microsoft 365 erläutert. 

![Sofortiger Bloomberg-Import- und Archivierungsprozess](../media/InstantBloombergDataArchiving.png)

1. Ihre Organisation arbeitet mit Bloomberg zusammen, um eine Bloomberg-SFTP-Website zu einrichten. Sie arbeiten auch mit Bloomberg zusammen, um Instant Bloomberg so zu konfigurieren, dass Chatnachrichten auf Ihre Bloomberg SFTP-Website kopiert werden.

2. Einmal alle 24 Stunden werden Chatnachrichten von Instant Bloomberg auf die Bloomberg SFTP-Website kopiert.

3. Der Instant Bloomberg-Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt täglich eine Verbindung mit der Bloomberg -SFTP-Website bereit und überträgt die Chatnachrichten aus den vorherigen 24 Stunden an einen sicheren Azure Storage-Bereich in der Microsoft Cloud. Der Connector konvertiert auch den Inhalt einer Chat-Chat-Chats in ein E-Mail-Nachrichtenformat.

4. Der Connector importiert die Chatnachrichtenelemente in das Postfach eines bestimmten Benutzers. Im Postfach des jeweiligen Benutzers wird ein neuer Ordner namens InstantBloomberg erstellt, in den die Elemente importiert werden. Der Connector verwendet dazu den Wert der *CorporateEmailAddress-Eigenschaft.* Jede Chatnachricht enthält diese Eigenschaft, die mit der E-Mail-Adresse jedes Teilnehmers der Chatnachricht gefüllt wird. Neben der automatischen Benutzerzuordnung mithilfe des Werts der *CorporateEmailAddress-Eigenschaft* können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei sollte eine Bloomberg-UUID und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird der Connector für jedes Chatelement zunächst die Datei mit der benutzerdefinierten Zuordnung betrachten. Wenn er keinen gültigen Microsoft 365-Benutzer findet, der der Bloomberg-UUID eines Benutzers entspricht, verwendet der Connector die *CorporateEmailAddress-Eigenschaft* des Chatelements. Wenn der Connector keinen gültigen Microsoft 365-Benutzer in der benutzerdefinierten Zuordnungsdatei oder der *CorporateEmailAddress-Eigenschaft* des Chatelements findet, wird das Element nicht importiert.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Einige der Implementierungsschritte, die zum Archivieren von Instant Bloomberg-Daten erforderlich sind, sind außerhalb von Microsoft 365 und müssen abgeschlossen sein, bevor Sie den Connector im Compliance Center erstellen können.

- Abonnieren Sie [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Dies ist erforderlich, damit Sie sich bei Bloomberg Anywhere anmelden können, um auf die Bloomberg SFTP-Website zu zugreifen, die Sie einrichten und konfigurieren müssen.

- Richten Sie eine Bloomberg SFTP (Secure File Transfer Protocol)-Website ein. Nach der Zusammenarbeit mit Bloomberg zum Einrichten der SFTP-Website werden die Daten von Instant Bloomberg täglich auf die SFTP-Website hochgeladen. Der connector, den Sie in Schritt 2 erstellen, stellt eine Verbindung mit dieser SFTP-Website ein und überträgt die Chatdaten an Microsoft 365-Postfächer. SFTP verschlüsselt auch die Chatdaten von Instant Bloomberg, die während des Übertragungsprozesses an Postfächer gesendet werden.

  Weitere Informationen zu Bloomberg SFTP (auch *BB-SFTP genannt):*

  - Weitere Informationen finden Sie im Dokument "SFTP Connectivity Standards" unter [Bloomberg Support](https://www.bloomberg.com/professional/support/documentation/).

  - Wenden [Sie sich an den Bloomberg-Kundensupport](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

  Nachdem Sie mit Bloomberg eine SFTP-Website eingerichtet haben, stellt Bloomberg Ihnen einige Informationen zur Verfügung, nachdem Sie auf die Bloomberg-Implementierungs-E-Mail-Nachricht antworten. Speichern Sie eine Kopie der folgenden Informationen. Verwenden Sie ihn zum Einrichten eines Connectors in Schritt 3.

  - Firmencode, der eine ID für Ihre Organisation ist und zur Anmeldung bei der Bloomberg SFTP-Website verwendet wird.

  - Kennwort für Ihre Bloomberg SFTP-Website

  - URL für Bloomberg SFTP-Website (z. B. sftp.bloomberg.com)

  - Portnummer für Bloomberg SFTP-Website

- Der Instant Bloomberg-Connector kann insgesamt 200.000 Elemente an einem einzigen Tag importieren. Wenn mehr als 200.000 Elemente auf der SFTP-Website vorhanden sind, wird keines dieser Elemente nach Microsoft 365 importiert.

- Dem Benutzer, der in Schritt 3 einen Instant Bloomberg-Connector erstellt (und der die öffentlichen Schlüssel und die IP-Adresse in Schritt 1 herunterlädt), muss die Rolle Postfachimportexport in Exchange Online zugewiesen werden. Dies ist erforderlich, um Connectors auf der Seite **Datenconnectors** im Microsoft 365 Compliance Center hinzuzufügen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle Postfachimportexport zur Rollengruppe Organisationsverwaltung in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle Postfachimportexport zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie in den Abschnitten Erstellen von [Rollengruppen](/Exchange/permissions-exo/role-groups#create-role-groups) oder [Ändern](/Exchange/permissions-exo/role-groups#modify-role-groups) von Rollengruppen im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Schritt 1: Abrufen öffentlicher SSH- und PGP-Schlüssel

Der erste Schritt besteht im Abrufen einer Kopie der öffentlichen Schlüssel für Secure Shell (SSH) und Pretty Good Privacy (PGP). Sie verwenden diese Schlüssel in Schritt 2, um die Bloomberg SFTP-Website so zu konfigurieren, dass der Connector (den Sie in Schritt 3 erstellen) eine Verbindung mit der SFTP-Website herstellen und die Chatdaten von Instant Bloomberg an Microsoft 365-Postfächer übertragen kann. In diesem Schritt erhalten Sie auch eine IP-Adresse, die Sie beim Konfigurieren der Bloomberg SFTP-Website verwenden.

1. Wechseln Sie <https://compliance.microsoft.com> zu, und klicken Sie dann auf **Datenconnectors**  >  **Instant Bloomberg**.

2. Klicken Sie **auf der Seite Instant Bloomberg-Produktbeschreibung** auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Klicken Sie auf der Website Anmeldeinformationen für **Bloomberg SFTP** hinzufügen unter Schritt 1 auf die Links **SSH-Schlüssel** herunterladen, **PGP-Schlüssel** herunterladen und IP-Adresslinks herunterladen, um eine Kopie jeder Datei auf Ihrem lokalen Computer zu speichern.  Diese Dateien enthalten die folgenden Elemente, die zum Konfigurieren der Bloomberg -SFTP-Website in Schritt 2 verwendet werden:

   - Öffentlicher SSH-Schlüssel: Dieser Schlüssel wird verwendet, um Secure Shell (SSH) zu konfigurieren, um eine sichere Remoteanmeldung zu aktivieren, wenn der Connector eine Verbindung mit dem Bloomberg SFTP-Standort herstellt.

   - Öffentlicher PGP-Schlüssel: Dieser Schlüssel wird verwendet, um die Verschlüsselung von Daten zu konfigurieren, die von der Bloomberg SFTP-Website an Microsoft 365 übertragen werden.

   - IP-Adresse: Die Bloomberg-SFTP-Website ist so konfiguriert, dass sie nur eine Verbindungsanforderung von dieser IP-Adresse akzeptiert, die vom Instant Bloomberg-Connector verwendet wird, den Sie in Schritt 3 erstellen. 

5. Klicken **Sie auf Abbrechen,** um den Assistenten zu schließen. Sie kommen in Schritt 3 zu diesem Assistenten zurück, um den Connector zu erstellen.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Schritt 2: Konfigurieren der Bloomberg SFTP-Website

Der nächste Schritt besteht in der Verwendung der öffentlichen SSH- und PGP-Schlüssel und der in Schritt 1 erhaltenen IP-Adresse, um die SSH-Authentifizierung und die PGP-Verschlüsselung für die Bloomberg-SFTP-Website zu konfigurieren. Dadurch kann der in Schritt 3 erstellte Instant Bloomberg-Connector eine Verbindung mit der Bloomberg -SFTP-Website herstellen und Instant Bloomberg-Daten an Microsoft 365 übertragen. Sie müssen mit dem Bloomberg-Kundensupport zusammenarbeiten, um Ihre Bloomberg SFTP-Website einrichten zu können. Wenden [Sie sich an den Bloomberg-Kundensupport,](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) um Unterstützung zu erhalten. 

> [!IMPORTANT]
> Bloomberg empfiehlt, die drei Dateien, die Sie in Schritt 1 heruntergeladen haben, an eine E-Mail-Nachricht anfügen und diese an das Kundensupportteam zu senden, wenn Sie mit ihnen zusammenarbeiten, um Ihre Bloomberg -SFTP-Website einrichten.

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Schritt 3: Erstellen eines Instant Bloomberg-Connectors

Der letzte Schritt besteht im Erstellen eines Instant Bloomberg-Connectors im Microsoft 365 Compliance Center. Der Connector verwendet die informationen, die Sie bereitstellen, um eine Verbindung mit der Bloomberg -SFTP-Website herzustellen und Chatnachrichten an die entsprechenden Benutzerpostfächer in Microsoft 365 zu übertragen.

1. Wechseln Sie <https://compliance.microsoft.com> zu, und klicken Sie dann auf **Datenconnectors**  >  **Instant Bloomberg**.

2. Klicken Sie **auf der Seite Instant Bloomberg-Produktbeschreibung** auf Connector **hinzufügen.**

3. Klicken Sie **auf der Seite Nutzungsbedingungen** auf **Akzeptieren**.

4. Geben Sie auf der Seite Anmeldeinformationen für **Bloomberg SFTP-Website** hinzufügen unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **Weiter**.

    - **Firmencode:** Die ID für Ihre Organisation, die als Benutzername für die Bloomberg SFTP-Website verwendet wird.

    - **Kennwort:** Kennwort für bloomberg SFTP-Website.

    - **SFTP-URL:** Die URL für die Bloomberg-SFTP-Website (z. B. sftp.bloomberg.com).

    - **SFTP-Port:** Die Portnummer für den Bloomberg SFTP-Standort. Der Connector verwendet diesen Port, um eine Verbindung mit dem SFTP-Standort herzustellen.

5. Wählen Sie auf der Seite Zu **importierende** Datentypen auswählen die erforderlichen Datentypen aus, die neben Nachrichten importiert werden **sollen.**

6. Aktivieren Sie **auf der Seite** Benutzerzuordnung die automatische Benutzerzuordnung, und stellen Sie bei Bedarf eine benutzerdefinierte Benutzerzuordnung zur Verfügung.

   > [!NOTE]
   > Der Connector importiert die Chatnachrichtenelemente in das Postfach eines bestimmten Benutzers. Im Postfach des jeweiligen Benutzers wird ein neuer Ordner namens **InstantBloomberg** erstellt, in den die Elemente importiert werden. Der Connector verwendet den Wert der *CorporateEmailAddress-Eigenschaft.* Jede Chatnachricht enthält diese Eigenschaft, und die Eigenschaft wird mit der E-Mail-Adresse jedes Teilnehmers der Chatnachricht gefüllt. Neben der automatischen Benutzerzuordnung mithilfe des Werts der *CorporateEmailAddress-Eigenschaft* können Sie auch benutzerdefinierte Zuordnungen definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Die Zuordnungsdatei sollte die Bloomberg-UUID und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird für jedes Chatelement zunächst die benutzerdefinierte Zuordnungsdatei vom Connector angezeigt. Wenn er keinen gültigen Microsoft 365-Benutzer findet, der der Bloomberg-UUID eines Benutzers entspricht, verwendet der Connector die *CorporateEmailAddress-Eigenschaft* des Chatelements. Wenn der Connector keinen gültigen Microsoft 365-Benutzer in der benutzerdefinierten Zuordnungsdatei oder der *CorporateEmailAddress-Eigenschaft* des Chatelements findet, wird das Element nicht importiert.

7. Klicken **Sie auf Weiter,** überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Vorbereiten,** um den Connector zu erstellen.

8. Wechseln Sie zur **Seite Datenconnectors,** um den Fortschritt des Importvorgangs für den neuen Connector zu sehen.