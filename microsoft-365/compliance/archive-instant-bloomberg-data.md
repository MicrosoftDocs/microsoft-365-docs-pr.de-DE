---
title: Einrichten eines Connectors zum Archivieren von Instant Bloomberg-Daten in Office 365
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
description: Administratoren können einen systemeigenen Connector einrichten, um Daten aus dem Chat-Tool von Instant Bloomberg in Office 365 zu importieren. Auf diese Weise können Sie Daten aus Drittanbieter-Datenquellen in Office 365 archivieren, sodass Sie Compliance-Features wie Legal Hold, Inhaltssuche und Aufbewahrungsrichtlinien zum Verwalten der drittanbieterdaten Ihrer Organisation verwenden können.
ms.openlocfilehash: 8a9a388c62ca59dfcdb2f123fd0776e619f8d38e
ms.sourcegitcommit: 7f26840a4330b0fd29807ec091c6915d283b3dd2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2019
ms.locfileid: "39615605"
---
# <a name="set-up-a-connector-to-archive-instant-bloomberg-data-in-office-365"></a>Einrichten eines Connectors zum Archivieren von Instant Bloomberg-Daten in Office 365

Verwenden Sie einen nativen Connector im Security #a0 Compliance Center in Office 365 zum Importieren und Archivieren von Finanz Dienstleistungs-Chat Daten aus dem Tool " [Instant Bloomberg](https://www.bloomberg.com/professional/product/collaboration/) Collaboration". Nachdem Sie einen Connector eingerichtet und konfiguriert haben, stellt er einmal täglich eine Verbindung mit der Bloomberg Secure FTP Site (SFTP) Ihrer Organisation her, wandelt den Inhalt von Chatnachrichten in ein e-Mail-Nachrichtenformat um und importiert diese Elemente dann in Postfächer in Office 365.

Nachdem Instant Bloomberg-Daten in Benutzerpostfächern gespeichert wurden, können Sie Office 365 Compliance-Features wie Beweissicherungsverfahren, Inhaltssuche, in-situ-Archivierung, Überwachung, [Kommunikations Konformität](communication-compliance.md)und Office 365-Aufbewahrungsrichtlinien auf Bloomberg-Daten anwenden. Beispielsweise können Sie Instant Bloomberg Chatnachrichten mithilfe der Inhaltssuche durchsuchen oder das Postfach, das die Instant Bloomberg-Daten enthält, einer Depotbank in einem erweiterten eDiscovery-Fall zuordnen. Die Verwendung eines Instant Bloomberg-Konnektors zum Importieren und Archivieren von Daten in Office 365 kann dazu beitragen, dass Ihre Organisation mit behördlichen und behördlichen Richtlinien konform bleibt.

## <a name="overview-of-archiving-instant-bloomberg-data"></a>Übersicht über die Archivierung von Instant Bloomberg-Daten

In der folgenden Übersicht wird erläutert, wie Sie einen Konnektor verwenden, um Chat Daten in Office 365 zu archivieren. 

![Sofortiger Bloomberg-Import-und-Archivierungsprozess](media/InstantBloombergDataArchiving.png)

1. Ihre Organisation arbeitet mit Bloomberg zusammen, um eine Bloomberg SFTP-Website einzurichten. Sie können auch mit Bloomberg zusammenarbeiten, um Instant Bloomberg so zu konfigurieren, dass Chatnachrichten auf Ihre Bloomberg SFTP-Website kopiert werden.

2. Alle 24 Stunden werden Chatnachrichten von Instant Bloomberg auf die Bloomberg SFTP-Website kopiert.
    
3. Der Instant Bloomberg Connector, den Sie im Security #a0 Compliance Center erstellen, stellt jeden Tag eine Verbindung mit der Bloomberg SFTP-Website her und überträgt die Chatnachrichten aus den vorherigen 24 Stunden an einen sicheren Azure-Speicherbereich in der Microsoft-Cloud. Der Connector wandelt auch den Inhalt einer Chat Massage in ein e-Mail-Nachrichtenformat um.
    
4. Der Connector importiert die Chatnachrichten Elemente in das Postfach eines bestimmten Benutzers oder in ein alternatives Postfach. Der Connector verwendet den Wert der *CorporateEmailAddress* -Eigenschaft. Jede Chatnachricht enthält diese Eigenschaft, die mit der e-Mail-Adresse jedes Teilnehmers der Chatnachricht aufgefüllt wird. Ob ein Element in ein bestimmtes Benutzerpostfach oder in das alternative Postfach importiert wird, basiert auf den folgenden Kriterien:
    
    a. **Elemente mit einem Wert in der CorporateEmailAddress-Eigenschaft, die einem Office 365 Benutzerkonto entsprechen:** Wenn der Connector die e-Mail-Adresse in der *CorporateEmailAddress* -Eigenschaft einem bestimmten Benutzerkonto in Office 365 zuordnen kann, wird das Element in den Ordner Posteingang im Office 365 Postfach des Benutzers kopiert.
    
    b. **Elemente mit einem Wert in der CorporateEmailAddress-Eigenschaft, die keinem Office 365 Benutzerkonto entsprechen:** Wenn der Connector keine e-Mail-Adresse in der *CorporateEmailAddress* -Eigenschaft einem bestimmten Benutzerkonto in Office 365 zuordnen kann, wird das Element in den Ordner Posteingangs Verzeichnis eines alternativen Postfachs "Catch-All" in Office 365 kopiert.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Viele der erforderlichen Implementierungsschritte zum Archivieren von Instant Bloomberg-Daten sind extern für Office 365 und müssen abgeschlossen sein, bevor Sie den Connector im Security #a0 Compliance Center erstellen können.

- Ihre Organisation muss einwilligen, dass der Office 365 Import Dienst auf Postfachdaten in Ihrer Organisation zugreifen kann. Um dieser Anforderung zuzustimmen, gehen Sie zu [dieser Seite](https://login.microsoftonline.com/common/oauth2/authorize?client_id=570d0bec-d001-4c4e-985e-3ab17fdc3073&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent), melden Sie sich mit den Anmeldeinformationen eines Office 365 globalen Administrators an, und nehmen Sie dann die Anforderung an. Sie müssen diesen Schritt ausführen, bevor Sie den Instant Bloomberg Connector in Schritt 3 erfolgreich erstellen können.

- Abonnieren Sie [Bloomberg Anywhere](https://www.bloomberg.com/professional/product/remote-access/?bbgsum-page=DG-WS-PROF-PROD-BBA). Dies ist erforderlich, damit Sie sich bei Bloomberg Anywhere anmelden können, um auf die Bloomberg SFTP-Website zuzugreifen, die Sie einrichten und konfigurieren müssen.

- Richten Sie eine Bloomberg SFTP (Secure File Transfer Protocol)-Website ein. Nach der Arbeit mit Bloomberg, um die SFTP-Website einzurichten, werden Daten aus Instant Bloomberg jeden Tag auf die SFTP-Website hochgeladen. Der in Schritt 2 erstellte Connector stellt eine Verbindung mit dieser SFTP-Website her und überträgt die Chat Daten an Office 365 Postfächer. SFTP verschlüsselt auch die Instant Bloomberg Chat Daten, die während des Übertragungsprozesses an Office 365 Postfächer gesendet werden.

    Informationen zu Bloomberg SFTP (auch *BB-SFTP*genannt):

    - Siehe das Dokument "SFTP Connectivity Standards" unter [Bloomberg Support](https://www.bloomberg.com/professional/support/documentation/).
    
    - Wenden Sie sich an den [Bloomberg-Kundensupport](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc).

    Nachdem Sie mit Bloomberg zusammengearbeitet haben, um eine SFTP-Website einzurichten, stellt Bloomberg Ihnen einige Informationen zur Verfügung, nachdem Sie auf die e-Mail-Nachricht der Bloomberg-Implementierung reagiert haben. Speichern Sie eine Kopie der folgenden Informationen. Sie verwenden Sie, um einen Connector in Schritt 3 einzurichten.

    - Firm Code, der eine ID für Ihre Organisation ist und zur Anmeldung bei der Bloomberg SFTP-Website verwendet wird.

    - Kennwort für Ihre Bloomberg SFTP-Website

    - URL für Bloomberg SFTP-Website (beispielsweise SFTP.Bloomberg.com)

    - Port Nummer für Bloomberg SFTP-Website

- Der Benutzer, der in Schritt 3 einen Instant Bloomberg-Konnektor erstellt (und der die öffentlichen Schlüssel und die IP-Adresse in Schritt 1 herunterlädt) muss die Rolle "Post Fach Import Export" in Exchange Online zugewiesen haben. Dies ist erforderlich, um im Security #a0 Compliance Center auf die Seite **Archivieren von drittanbieterdaten** zuzugreifen. Standardmäßig ist diese Rolle keiner Rollengruppe in Exchange Online zugewiesen. Sie können die Rolle "Post Fach Import exportieren" der Rollengruppe "Organisationsverwaltung" in Exchange Online hinzufügen. Sie können auch eine Rollengruppe erstellen, die Rolle "Post Fach Import Export" zuweisen und dann die entsprechenden Benutzer als Mitglieder hinzufügen. Weitere Informationen finden Sie im Abschnitt [Erstellen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#create-role-groups) von Rollengruppen oder [Ändern von Rollengruppen](https://docs.microsoft.com/Exchange/permissions-exo/role-groups#modify-role-groups) im Artikel "Verwalten von Rollengruppen in Exchange Online".

## <a name="step-1-obtain-ssh-and-pgp-public-keys"></a>Schritt 1: Abrufen von öffentlichen SSH-und PGP-Schlüsseln

Der erste Schritt besteht darin, eine Kopie der öffentlichen Schlüssel für Secure Shell (SSH) und Pretty Good Privacy (PGP) zu erhalten. Sie verwenden diese Schlüssel in Schritt 2, um die Bloomberg-SFTP-Website so zu konfigurieren, dass der in Schritt 3 erstellte Connector eine Verbindung mit der SFTP-Website herstellen und die Instant Bloomberg-Chat Daten an Office 365 Postfächer übertragen kann. Außerdem erhalten Sie in diesem Schritt eine IP-Adresse, die Sie beim Konfigurieren der Bloomberg SFTP-Website verwenden.

1. Wechseln Sie <https://protection.office.com> zu, und klicken Sie dann auf **Data Governance \> Import** , und klicken Sie dann auf **Archivieren von drittanbieterdaten**.

2. Klicken Sie auf der Seite **drittanbieterdaten archivieren** auf **Connector hinzufügen**, und klicken Sie dann auf **Instant Bloomberg**.

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

4. Klicken Sie auf der **Website Anmeldeinformationen für Bloomberg SFTP** unter Schritt 1 auf den Link **SSH herunterladen**, **PGP-Schlüssel**herunterladen und **IP-Adress Links herunterladen** , um eine Kopie der einzelnen Dateien auf dem lokalen Computer zu speichern. Diese Dateien enthalten die folgenden Elemente, die zum Konfigurieren der Bloomberg SFTP-Website in Schritt 2 verwendet werden:

   - Öffentlicher SSH-Schlüssel: dieser Schlüssel wird zum Konfigurieren von Secure Shell (SSH) verwendet, um eine sichere Remoteanmeldung zu ermöglichen, wenn der Connector eine Verbindung mit der Bloomberg SFTP-Website herstellt.

   - Öffentlicher PGP-Schlüssel: dieser Schlüssel wird verwendet, um die Verschlüsselung von Daten zu konfigurieren, die von der Bloomberg SFTP-Website an Office 365 übertragen werden.

   - IP-Adresse: die Bloomberg SFTP-Website ist für die Annahme einer Verbindungsanforderung nur von dieser IP-Adresse konfiguriert, die von dem in Schritt 3 erstellten Instant Bloomberg-Konnektor verwendet wird. 

5. Klicken Sie auf **Abbrechen** , um den Assistenten zu schließen. Sie kehren zu diesem Assistenten in Schritt 3 zurück, um den Connector zu erstellen.

## <a name="step-2-configure-the-bloomberg-sftp-site"></a>Schritt 2: Konfigurieren der Bloomberg SFTP-Website

Der nächste Schritt besteht darin, die öffentlichen SSH-und PGP-Schlüssel sowie die IP-Adresse zu verwenden, die Sie in Schritt 1 zum Konfigurieren der SSH-Authentifizierung und der PGP-Verschlüsselung für die Bloomberg SFTP-Website erhalten haben. Auf diese Weise können Sie den in Schritt 3 erstellten Instant Bloomberg-Konnektor mit der Bloomberg SFTP-Website verbinden und Instant Bloomberg-Daten an Office 365 übertragen. Sie müssen mit dem Bloomberg-Kundensupport zusammenarbeiten, um Ihre Bloomberg SFTP-Website einzurichten. Wenden Sie sich zur Unterstützung an den [Bloomberg-Kundensupport](https://service.bloomberg.com/portal/sessions/new?utm_source=bloomberg-menu&utm_medium=csc) . 

> [!IMPORTANT]
> Bloomberg empfiehlt, dass Sie die drei Dateien, die Sie in Schritt 1 heruntergeladen haben, an eine e-Mail-Nachricht anfügen und diese an Ihren Kundensupport senden, wenn Sie mit Ihnen zusammenarbeiten, um Ihre Bloomberg SFTP-Website einzurichten.

## <a name="step-3-create-an-instant-bloomberg-connector"></a>Schritt 3: Erstellen eines Instant Bloomberg-Connectors

Der letzte Schritt besteht darin, einen Instant Bloomberg-Konnektor im Security #a0 Compliance Center zu erstellen. Der Connector verwendet die von Ihnen bereitgestellten Informationen, um eine Verbindung mit der Bloomberg SFTP-Website herzustellen und Chatnachrichten an die entsprechenden Benutzerpostfach-Postfächer in Office 365 zu übertragen. 

1. Wechseln Sie <https://protection.office.com> zu, und klicken Sie dann auf **Data Governance \> Import** , und klicken Sie dann auf **Archivieren von drittanbieterdaten**.

2. Klicken Sie auf der Seite **drittanbieterdaten archivieren** auf **Connector hinzufügen**, und klicken Sie dann auf **Instant Bloomberg**.

3. Klicken Sie auf der Seite **Nutzungsbedingungen** auf **annehmen**.

4. Geben Sie auf der Seite **Anmeldeinformationen für Bloomberg SFTP-Website hinzufügen** unter Schritt 3 die erforderlichen Informationen in die folgenden Felder ein, und klicken Sie dann auf **weiter**.

    - **Firm Code:** Die ID für Ihre Organisation, die als Benutzername für die Bloomberg SFTP-Website verwendet wird.

    - **Kennwort:** Kennwort für Bloomberg SFTP-Website

    - **SFTP-URL:** Die URL für die Website von Bloomberg SFTP (beispielsweise SFTP.Bloomberg.com).

    - **SFTP-Port:** Die Portnummer für Bloomberg SFTP-Website. Der Connector verwendet diesen Port, um eine Verbindung mit der SFTP-Website herzustellen.

5. Geben Sie auf der Seite **alternatives Postfach** die e-Mail-Adresse eines Postfachs ein, das zum Speichern der Chatnachrichten aus Instant Bloomberg verwendet wird, die keinem Benutzerpostfach in Ihrer Organisation zugeordnet sind.

   > [!NOTE]
   > Jede Chatnachricht in jeder Unterhaltung in Instant Bloomberg enthält eine Eigenschaft namens *CorporateEmailAddress*, die die e-Mail-Adresse Ihrer Organisation für den Chat Teilnehmer enthält. Während des Importvorgangs versucht der Connector, Chatnachrichten in ein Benutzerpostfach in Office 365 mit denselben e-Mail-Adressen zu importieren, die mit dem in der *CorporateEmailAddress* -Eigenschaft übereinstimmen. Wenn kein Office 365 Postfach mit derselben Adresse wie in der *CorporateEmailAddress* -Eigenschaft vorhanden ist, importiert der Connector die Chatnachricht in das alternative Postfach, das Sie auf dieser Seite angeben.

6. Klicken Sie auf **weiter**, überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **vorbereiten** , um den Connector zu erstellen.

7. Wechseln Sie zur Seite **Archivieren von drittanbieterdaten** , um den Fortschritt des Importvorgangs für den neuen Connector anzuzeigen.
