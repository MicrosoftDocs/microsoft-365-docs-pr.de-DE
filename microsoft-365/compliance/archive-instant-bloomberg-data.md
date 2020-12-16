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
description: Erfahren Sie, wie Administratoren einen Data Connector zum Importieren und Archivieren von Daten aus dem Chat-Tool von Instant Bloomberg in Microsoft 365 einrichten und verwenden können.
ms.openlocfilehash: c2a56feb80f6772462fae47eb2a020e951f246e6
ms.sourcegitcommit: 849b365bd3eaa9f3c3a9ef9f5973ef81af9156fa
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/16/2020
ms.locfileid: "49688490"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data"></a>Einrichten eines Connectors zum Archivieren von Instant Bloomberg-Daten

Verwenden Sie einen systemeigenen Connector im Microsoft 365 Compliance Center zum Importieren und Archivieren von Finanz Dienstleistungs-Chat Daten aus dem Tool für die [sofortige Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) -Zusammenarbeit. Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er einmal täglich eine Verbindung mit der Bloomberg Secure FTP Site (SFTP) Ihrer Organisation her, wandelt den Inhalt von Chatnachrichten in ein e-Mail-Nachrichtenformat um und importiert diese Elemente dann in Postfächer in Microsoft 365.

Nachdem Instant Bloomberg-Daten in Benutzerpostfächern gespeichert wurden, können Sie Microsoft 365-Compliance-Features wie Beweissicherungsverfahren, Inhaltssuche, In-Place Archivierung, Überwachung, Kommunikations Konformität und Microsoft 365-Aufbewahrungsrichtlinien auf Bloomberg-Daten anwenden. Beispielsweise können Sie Instant Bloomberg Chatnachrichten mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die Instant Bloomberg-Daten enthält, einer Depotbank in einem erweiterten eDiscovery-Fall zuordnen. Die Verwendung eines Instant Bloomberg-Konnektors zum Importieren und Archivieren von Daten in Microsoft 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Übersicht über die Archivierung von Instant Bloomberg-Daten

In der folgenden Übersicht wird erläutert, wie Sie einen Connector zum Archivieren von Instant Bloomberg Chat-Daten in Microsoft 365 verwenden. 

![Sofortiger Bloomberg-Import-und-Archivierungsprozess](../media/InstantBloombergDataArchiving.png)

1. Ihre Organisation arbeitet mit Bloomberg zusammen, um eine Bloomberg SFTP-Website einzurichten. Sie können auch mit Bloomberg zusammenarbeiten, um Instant Bloomberg so zu konfigurieren, dass Chatnachrichten auf Ihre Bloomberg SFTP-Website kopiert werden.

2. Alle 24 Stunden werden Chatnachrichten von Instant Bloomberg auf die Bloomberg SFTP-Website kopiert.

3. Der Instant Bloomberg Connector, den Sie im Microsoft 365 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Bloomberg SFTP-Website her und überträgt die Chatnachrichten aus den vorherigen 24 Stunden an einen sicheren Azure-Speicherbereich in der Microsoft-Cloud. Der Connector wandelt auch den Inhalt einer Chat Massage in ein e-Mail-Nachrichtenformat um.

4. Der Connector importiert die Chatnachrichten Elemente in das Postfach eines bestimmten Benutzers. Ein neuer Ordner mit dem Namen InstantBloomberg wird im Postfach des jeweiligen Benutzers erstellt, und die Elemente werden darin importiert. Der Connector führt dies mithilfe des Werts der *CorporateEmailAddress* -Eigenschaft aus. Jede Chatnachricht enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Teilnehmers der Chatnachricht aufgefüllt wird. Zusätzlich zur automatischen Benutzerzuordnung mit dem Wert der *CorporateEmailAddress* -Eigenschaft können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Diese Zuordnungsdatei sollte eine Bloomberg-UUID und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird der Connector für jedes Chat Element zuerst die benutzerdefinierte Zuordnungsdatei betrachten. Wenn kein gültiger Microsoft 365-Benutzer gefunden wird, der der Bloomberg-UUID eines Benutzers entspricht, verwendet der Connector die *CorporateEmailAddress* -Eigenschaft des Chat Elements. Wenn der Connector weder in der benutzerdefinierten Zuordnungsdatei noch in der *CorporateEmailAddress* -Eigenschaft des Chat Elements einen gültigen Microsoft 365-Benutzer findet, wird das Element nicht importiert.

## <a name="before-you-begin"></a>Vorbereitung

Einige der Implementierungsschritte, die zum Archivieren von Bloomberg-Daten erforderlich sind, sind extern bei Microsoft 365 und müssen abgeschlossen sein, bevor Sie den Connector im Compliance Center erstellen können.

- Abonnieren Sie [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Dies ist erforderlich, damit Sie sich bei Bloomberg Anywhere anmelden können, um auf die Bloomberg SFTP-Website zuzugreifen, die Sie einrichten und konfigurieren müssen.

- Richten Sie eine Bloomberg SFTP (Secure File Transfer Protocol)-Website ein. Nach der Arbeit mit Bloomberg, um die SFTP-Website einzurichten, werden Daten aus Instant Bloomberg jeden Tag auf die SFTP-Website hochgeladen. Der in Schritt 2 erstellte Connector stellt eine Verbindung mit dieser SFTP-Website her und überträgt die Chat Daten an Microsoft 365-Postfächer. SFTP verschlüsselt auch die Instant Bloomberg Chat-Daten, die während des Übertragungsprozesses an Postfächer gesendet werden.

  Informationen zu Bloomberg SFTP (auch *BB-SFTP* genannt):

  - Siehe das Dokument "SFTP Connectivity Standards" unter [Bloomberg Support](https://www.bloomberg.com/professional/support/documentation/).

  - Wenden Sie sich an den [Bloomberg-Kundensupport](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

  Nachdem Sie mit Bloomberg zusammengearbeitet haben, um eine SFTP-Website einzurichten, stellt Bloomberg Ihnen einige Informationen zur Verfügung, nachdem Sie auf die e-Mail-Nachricht der Bloomberg-Implementierung reagiert haben. Speichern Sie eine Kopie der folgenden Informationen. Sie verwenden Sie, um einen Connector in Schritt 3 einzurichten.

  - Firm Code, der eine ID für Ihre Organisation ist und zur Anmeldung bei der Bloomberg SFTP-Website verwendet wird.

  - Kennwort für Ihre Bloomberg SFTP-Website

  - URL für Bloomberg SFTP-Website (beispielsweise SFTP.Bloomberg.com)

  - Port Nummer für Bloomberg SFTP-Website

- Der Instant Bloomberg Connector kann insgesamt 200.000 Elemente an einem einzigen Tag importieren. Wenn an einem Tag in der SFTP-Website mehr als 200.000 Elemente vorhanden sind, wird keines dieser itmes in Microsoft 365 importiert.

- Der Benutzer, der in Schritt 3 einen Instant Bloomberg-Konnektor erstellt (und der die öffentlichen Schlüssel und die IP-Adresse in Schritt 1 herunterlädt) muss die Rolle "Post Fach Import Export" in Exchange Online zugewiesen haben. Dies ist für das Hinzufügen von Connectors auf der Seite " **Daten Konnektoren** " im Microsoft 365 Compliance Center erforderlich. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Schritt 1: Abrufen von öffentlichen SSH-und PGP-Schlüsseln

Der erste Schritt besteht darin, eine Kopie der öffentlichen Schlüssel für Secure Shell (SSH) und Pretty Good Privacy (PGP) zu erhalten. Sie verwenden diese Schlüssel in Schritt 2, um die Bloomberg-SFTP-Website so zu konfigurieren, dass der in Schritt 3 erstellte Connector eine Verbindung mit der SFTP-Website herstellen und die Instant Bloomberg-Chat Daten an Microsoft 365-Postfächerüber tragen kann. Außerdem erhalten Sie in diesem Schritt eine IP-Adresse, die Sie beim Konfigurieren der Bloomberg SFTP-Website verwenden.

1. Wechseln Sie zu, <https://compliance.microsoft.com> und klicken Sie dann auf **Data Connectors**  >  **Instant Bloomberg**.

2. Klicken Sie auf der Seite **Instant Bloomberg** -Produktbeschreibung auf **Connector hinzufügen** .

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

4. Klicken Sie auf der **Website Anmeldeinformationen für Bloomberg SFTP** unter Schritt 1 auf den Link **SSH herunterladen**, **PGP-Schlüssel** herunterladen und **IP-Adress Links herunterladen** , um eine Kopie der einzelnen Dateien auf dem lokalen Computer zu speichern. Diese Dateien enthalten die folgenden Elemente, die zum Konfigurieren der Bloomberg SFTP-Website in Schritt 2 verwendet werden:

   - Öffentlicher SSH-Schlüssel: dieser Schlüssel wird zum Konfigurieren von Secure Shell (SSH) verwendet, um eine sichere Remoteanmeldung zu ermöglichen, wenn der Connector eine Verbindung mit der Bloomberg SFTP-Website herstellt.

   - Öffentlicher PGP-Schlüssel: dieser Schlüssel wird verwendet, um die Verschlüsselung von Daten zu konfigurieren, die von der Bloomberg SFTP-Website an Microsoft 365 übertragen werden.

   - IP-Adresse: die Bloomberg SFTP-Website ist für die Annahme einer Verbindungsanforderung nur von dieser IP-Adresse konfiguriert, die von dem in Schritt 3 erstellten Instant Bloomberg-Konnektor verwendet wird. 

5. Klicken Sie auf **Abbrechen** , um den Assistenten zu schließen. Sie kehren zu diesem Assistenten in Schritt 3 zurück, um den Connector zu erstellen.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Schritt 2: Konfigurieren der Bloomberg SFTP-Website

Der nächste Schritt besteht darin, die öffentlichen SSH-und PGP-Schlüssel sowie die IP-Adresse zu verwenden, die Sie in Schritt 1 zum Konfigurieren der SSH-Authentifizierung und der PGP-Verschlüsselung für die Bloomberg SFTP-Website erhalten haben. Auf diese Weise können Sie den in Schritt 3 erstellten Instant Bloomberg-Konnektor mit der Bloomberg SFTP-Website verbinden und Instant Bloomberg-Daten an Microsoft 365 übertragen. Sie müssen mit dem Bloomberg-Kundensupport zusammenarbeiten, um Ihre Bloomberg SFTP-Website einzurichten. Wenden Sie sich zur Unterstützung an den [Bloomberg-Kundensupport](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) . 

> [!IMPORTANT]
> Bloomberg empfiehlt, dass Sie die drei Dateien, die Sie in Schritt 1 heruntergeladen haben, an eine e-Mail-Nachricht anfügen und diese an Ihren Kundensupport senden, wenn Sie mit Ihnen zusammenarbeiten, um Ihre Bloomberg SFTP-Website einzurichten.

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Schritt 3: Erstellen eines Instant Bloomberg-Connectors

Der letzte Schritt besteht darin, einen Instant Bloomberg-Connector im Microsoft 365 Compliance Center zu erstellen. Der Connector verwendet die von Ihnen bereitgestellten Informationen, um eine Verbindung mit der Bloomberg SFTP-Website herzustellen und Chatnachrichten an die entsprechenden Benutzerpostfach-Postfächer in Microsoft 365 zu übertragen.

1. Wechseln Sie zu, <https://compliance.microsoft.com> und klicken Sie dann auf **Data Connectors**  >  **Instant Bloomberg**.

2. Klicken Sie auf der Seite **Instant Bloomberg** -Produktbeschreibung auf **Connector hinzufügen** .

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

4. Geben Sie auf der Seite **Anmeldeinformationen für Bloomberg SFTP-Website hinzufügen** unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **weiter**.

    - **Firm Code:** Die ID für Ihre Organisation, die als Benutzername für die Bloomberg SFTP-Website verwendet wird.

    - **Kennwort:** Kennwort für Bloomberg SFTP-Website.

    - **SFTP-URL:** Die URL für die Website von Bloomberg SFTP (beispielsweise SFTP.Bloomberg.com).

    - **SFTP-Port:** Die Portnummer für Bloomberg SFTP-Website. Der Connector verwendet diesen Port, um eine Verbindung mit der SFTP-Website herzustellen.

5. Wählen Sie auf der Seite **zu importierende Datentypen auswählen** die erforderlichen Datentypen aus, die außer den **Nachrichten** importiert werden sollen.

6. Aktivieren Sie auf der Seite **Benutzerzuordnung** die automatische Benutzerzuordnung, und geben Sie nach Bedarf Benutzerzuordnung an.

   > [!NOTE]
   > Der Connector importiert die Chatnachrichten Elemente in das Postfach eines bestimmten Benutzers. Ein neuer Ordner mit dem Namen **InstantBloomberg** wird im Postfach des jeweiligen Benutzers erstellt, und die Elemente werden darin importiert. Der Connector verwendet den Wert der *CorporateEmailAddress* -Eigenschaft. Jede Chatnachricht enthält diese Eigenschaft, und die Eigenschaft wird mit der e-Mail-Adresse jedes Teilnehmers der Chatnachricht aufgefüllt. Zusätzlich zur automatischen Benutzerzuordnung mit dem Wert der *CorporateEmailAddress* -Eigenschaft können Sie auch eine benutzerdefinierte Zuordnung definieren, indem Sie eine CSV-Zuordnungsdatei hochladen. Die Zuordnungsdatei sollte die Bloomberg-UUID und die entsprechende Microsoft 365-Postfachadresse für jeden Benutzer enthalten. Wenn Sie die automatische Benutzerzuordnung aktivieren und eine benutzerdefinierte Zuordnung bereitstellen, wird der Connector für jedes Chat Element zuerst die benutzerdefinierte Zuordnungsdatei betrachten. Wenn kein gültiger Microsoft 365-Benutzer gefunden wird, der der Bloomberg-UUID eines Benutzers entspricht, verwendet der Connector die *CorporateEmailAddress* -Eigenschaft des Chat Elements. Wenn der Connector weder in der benutzerdefinierten Zuordnungsdatei noch in der *CorporateEmailAddress* -Eigenschaft des Chat Elements einen gültigen Microsoft 365-Benutzer findet, wird das Element nicht importiert.

7. Klicken Sie auf **weiter**, überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **vorbereiten** , um den Connector zu erstellen.

8. Wechseln Sie zur Seite **Daten Konnektoren** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.
