---
title: Testen von Microsoft 365 aus Ihrer benutzerdefinierten Domäne
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
ms.custom: ''
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie die E-Mail-Funktionalität aus Ihrer benutzerdefinierten Domäne an ein Microsoft 365-Postfach mit nur zwei Testkonten testen können.
ms.openlocfilehash: 019f1786756a036132f95fd5e8ef8a1d42cd515b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50914714"
---
# <a name="pilot-microsoft-365-from-my-custom-domain"></a>Testen von Microsoft 365 aus Ihrer benutzerdefinierten Domäne

Sie können Microsoft 365 mit den folgenden Anforderungen und Einschränkungen testen:

- Ihr aktueller E-Mail-Anbieter muss E-Mail-Weiterleitung unterstützen.

- Sie müssen Ihre Microsoft 365-DNS-Einträge bei Ihrem DNS-Hostinganbieter verwalten, statt diese Einträge von Microsoft 365 verwalten zu lassen.

    Weitere Informationen finden Sie unter [Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

- Frei/Gebucht-Informationen für Benutzer auf dem anderen E-Mail-Server stehen nicht zur Verfügung.

- Administratoren können nicht alle Benutzerkonten von einem einzigen Standort aus verwalten.

- Möglicherweise sind die Benutzer nicht in der Lage, Microsoft 365-Spamfilter zu verwenden.

- Dies wird für eine sehr kleine Anzahl von Benutzern empfohlen und gilt nur für die Verwendung von E-Mails für ein Pilotprojekt.

## <a name="set-up-a-microsoft-365-pilot"></a>Einrichten eines Microsoft 365-Pilotprojekts

Führen Sie die folgenden Schritte aus, um ein Microsoft 365-Pilotprojekt einzurichten:

### <a name="step-1-sign-in-to-the-microsoft-365-admin-center"></a>Schritt 1: Anmelden beim Microsoft 365 Admin Center

1. Melden Sie sich mit Ihrem Geschäfts-, Schul- oder Unikonto beim [Microsoft 365 Admin Center](https://admin.microsoft.com) an.

2. Wählen Sie im linken Navigationsbereich **Einstellungen** > **Domänen** aus.

### <a name="step-2-verify-that-you-own-the-domain-you-want-to-use"></a>Schritt 2: Überprüfung, ob Sie die gewünschte Domäne besitzen

1. Klicken Sie auf der Seite **Domänen** auf **Domäne hinzufügen**.

2. Geben Sie den Domänennamen in das Feld ein, wählen Sie **Diese Domäne verwenden** aus, und wählen Sie dann **Weiter**.

3. Wählen Sie die Dienste aus, die Sie mit Ihrer Domäne testen möchten, z. B. E-Mail und Chat.

5. Befolgen Sie auf der Seite **Domäne überprüfen** die schrittweisen Anleitungen, und wählen Sie dann **Überprüfen**.

    Es kann zwischen einigen Minuten und 72 Stunden dauern, bis DNS-Änderungen wirksam werden.

    Wenn die Überprüfung erfolgreich ist, werden Sie aufgefordert, Ihre DNS-Einträge zu ändern.

### <a name="step-3-mark-the-domain-as-shared-in-exchange-online"></a>Schritt 3: Kennzeichnen der Domäne als freigegeben in Exchange Online

1. Wählen Sie im Exchange Admin Center im Abschnitt **Nachrichtenfluss** die Option **Akzeptierte Domänen** aus, und wählen Sie dann die Domäne aus, die Sie ändern möchten.

2. Doppelklicken Sie, um das Fenster zu öffnen, und wählen Sie dann **Internes Relay** aus. 

3. Wählen Sie **Speichern** aus.

    Diese Einstellung wird möglicherweise erst nach einigen Minuten wirksam.

### <a name="step-4-unblock-the-existing-email-server-optional"></a>Schritt 4: Entsperren des vorhandenen Mailservers (optional)

Microsoft 365 verwendet Exchange Online Protection (EOP) zum Schutz vor Spam. EOP blockiert möglicherweise Ihren vorhandenen E-Mail-Server, wenn ein hohes Spamaufkommen erkannt wird, das von Ihrem aktuellen E-Mail-Server weitergeleitet wird. Wenn Sie den Spamschutz für Ihren anderen E-Mail-Anbieter als vertrauenswürdig einstufen, können Sie die Blockierung des Servers in Microsoft 365 aufheben.

> [!NOTE]
> Wenn Sie die Blockierung des vorhandenen E-Mail-Servers aufheben, können alle Spamnachrichten, die über den ursprünglichen Server eintreffen, an die Microsoft 365-Postfächer übermittelt werden, und Sie können den Spamschutz durch Microsoft 365 nicht auswerten.

1. Wählen Sie im Navigationsbereich des Exchange Admin Centers **Schutz** aus, und wählen Sie dann **Verbindungsfilter** aus.

2. Wählen Sie in der **IP-Zulassungsliste** den Eintrag **+** aus, und fügen Sie die IP-Adresse des Mailservers für Ihren aktuellen E-Mail-Anbieter hinzu. 

### <a name="step-5-create-user-accounts-and-set-the-primary-reply-to-address"></a>Schritt 5: Erstellen von Benutzerkonten und Festlegen der primären Antwortadresse

1. Wählen Sie linken Navigationsbereich des Microsoft 365 Admin Centers **Benutzer** > **Aktive Benutzer** aus.

2. Erstellen Sie zwei Testkonten, indem Sie zwei vorhandene Benutzer hinzufügen.

    Wählen Sie für jedes Konto **+ Benutzer hinzufügen** aus, und geben Sie die erforderlichen Informationen ein, einschließlich der Kennwortmethode, die Sie testen möchten.

    Um sicherzustellen, dass die E-Mail eines Benutzers unverändert bleibt, muss das Feld **Benutzername** der aktuellen E-Mail-Adresse des Benutzers entsprechen.

3. Wählen Sie die entsprechende Lizenz aus, klicken Sie auf **Weiter**, und klicken Sie dann auf **Hinzufügen fertig stellen**. 

4. Wählen Sie neben **Benutzername** Ihren benutzerdefinierten Domänennamen aus der Dropdownliste aus. 

5. Wählen Sie **Erstellen** > **Schließen**.

### <a name="step-6-configure-mail-to-flow-from-microsoft-365-or-office-365-to-email-server"></a>Teil 6: **Konfigurieren von E-Mails für den Fluss von Microsoft 365 oder Office 365 zum E-Mail-Server

Dafür sind zwei Schritte nötig:

1. Konfigurieren Ihrer Microsoft 365- oder Office 365-Umgebung.

2. Einrichten eines Connectors von Microsoft 365 oder Office 365 zu Ihrem E-Mail-Server.

### <a name="1-configure-your-microsoft-365-or-office-365-environment"></a>1. Konfigurieren Ihrer Microsoft 365- oder Office 365-Umgebung

Stellen Sie sicher, dass Sie Folgendes in Microsoft 365 oder Office 365 erledigt haben:

1. Zum Einrichten von Connectors benötigen Sie Ihnen zugewiesene Berechtigungen, bevor Sie beginnen können. Welche Berechtigungen Sie benötigen, können Sie dem Eintrag "Microsoft 365- und Office 365-Connectors" im Thema [Featureberechtigungen in EOP](../../security/office-365-security/feature-permissions-in-eop.md) entnehmen.

2. Wenn Sie möchten, dass EOP oder Exchange Online E-Mails von Ihren E-Mail-Servern an das Internet weiterleitet, gehen Sie wie folgt vor:

   - Verwenden Sie ein Zertifikat, das mit einem Antragstellernamen konfiguriert ist, der einer akzeptierte Domäne in Microsoft 365 oder Office 365 entspricht. Es wird empfohlen, dass der allgemeine Name des Zertifikats oder der alternative Antragstellername mit der primären SMTP-Domäne für Ihre Organisation übereinstimmt. Ausführliche Informationen finden Sie unter [Voraussetzungen für Ihre lokale E-Mail-Umgebung](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/set-up-connectors-to-route-mail#prerequisites-for-your-on-premises-email-environment).

   – ODER –

   - Stellen Sie sicher, dass alle Absenderdomänen und -unterdomänen in Ihrer Organisation in Microsoft 365 oder Office 365 als akzeptierte Domänen konfiguriert sind.

   Weitere Informationen zum Definieren von akzeptierten Domänen finden Sie unter [Verwalten von akzeptierten Domänen in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) und [Aktivieren des Nachrichtenflusses für Unterdomänen in Exchange Online](/exchange/mail-flow-best-practices/manage-accepted-domains/enable-mail-flow-for-subdomains).

3. Entscheiden Sie, ob Sie Nachrichtenflussregeln (auch als Transportregeln bezeichnet) oder Domänennamen verwenden möchten, um E-Mails von Microsoft 365 oder Office 365 an Ihre E-Mail-Server zu übermitteln. Die meisten Unternehmen entscheiden sich dafür, E-Mails für alle akzeptierten Domänen zu übermitteln. Weitere Informationen finden Sie unter [Szenario: Bedingtes E-Mail-Routing in Exchange Online](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/conditional-mail-routing).

> [!NOTE]
> Sie können Nachrichtenflussregel einrichten, wie in [Aktionen für die Nachrichtenflussregel in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions) beschrieben. Beispielsweise möchten Sie Nachrichtenflussregeln möglicherweise mit Connectors verwenden, wenn Ihre E-Mails zurzeit über Verteilerlisten an mehrere Standorte weitergeleitet werden.

### <a name="2-set-up-a-connector-from-microsoft-365-or-office-365-to-your-email-server"></a>2. Einrichten eines Connectors von Microsoft 365 oder Office 365 zu Ihrem E-Mail-Server

Um in Microsoft 365 oder Office 365 einen Connector zu erstellen, wählen Sie **Administrator** aus, und klicken Sie dann auf **Exchange**, um zum Exchange-Verwaltungskonsole zu gelangen. Klicken Sie dann auf **Nachrichtenfluss** und auf **Connectors**.

Einrichten von Connectors mithilfe des Assistenten.

Klicken Sie zum Starten des Assistenten auf das Pluszeichen **+**. Wählen Sie auf dem ersten Bildschirm **Von** Office 365 und **An** den E-Mail-Server Ihrer Organisation aus.

Klicken Sie auf **Weiter**, und befolgen Sie die Anweisungen des Assistenten. Klicken Sie auf die Links **Hilfe** oder **Weitere Informationen**, wenn Sie weitere Informationen benötigen. Der Assistent führt Sie durch das Setup. Stellen Sie am Ende sicher, dass Ihr Connector eine Bestätigung vornimmt. Wenn der Connector keine Bestätigung vornimmt, doppelklicken Sie auf angezeigte Meldung, um mehr Informationen zu erhalten, und lesen Sie [Validieren von Connectors](/exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/validate-connectors), um Hilfe zur Problembehebung zu erhalten.



### <a name="step-7-update-dns-records-at-your-dns-hosting-provider"></a>Schritt 7: Aktualisieren der DNS-Einträge bei Ihrem DNS-Hostinganbieter

Melden Sie sich bei der Website Ihres DNS-Hostinganbieters an, und folgen Sie den Anweisungen unter [Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne](../get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md).

**Machen Sie die folgenden beiden Ausnahmen:**

- Erstellen Sie keinen neuen MX-Eintrag bzw. ändern Sie Ihren bestehenden MX-Eintrag nicht.

- Wenn Sie bereits über einen SPF-Eintrag (Sender Policy Framework) für Ihren bisherigen E-Mail-Anbieter verfügen, erstellen Sie keinen neuen SPF (TXT)-Eintrag für Exchange Online, sondern fügen Sie dem vorhandenen TXT-Eintrag "include:spf.protection.outlook.com" hinzu.

    Beispiel: "v=spf1 mx include:adatum.com include:spf.protection.outlook.com ~all"

    Wenn Sie nicht über einen SPF-Eintrag verfügen, ändern Sie den von Microsoft 365 empfohlenen so, dass er die Domäne für Ihren aktuellen E-Mail-Anbieter einschließt, und fügen Sie "spf.protection.outlook.com" hinzu. Dadurch werden ausgehende Nachrichten von beiden E-Mail-Systemen autorisiert.

### <a name="step-8-set-up-email-forwarding-at-your-current-provider"></a>Schritt 8: Einrichten von E-Mail-Weiterleitung bei Ihrem aktuellen Anbieter

Richten Sie bei Ihrem aktuellen E-Mail-Anbieter Weiterleitung für die E-Mail-Konten Ihrer Benutzer an Ihre onmicrosoft.com-Domäne ein:

- Leiten Sie das Postfach des Benutzers A an usera@yourcompany.onmicrosoft.com weiter.

- Leiten Sie das Postfach des Benutzers B an userb@yourcompany.onmicrosoft.com weiter.

Nachdem Sie diesen Schritt ausgeführt haben, sind alle an usera@yourcompany.com und userb@yourcompany.com gesendeten E-Mails in Microsoft 365 verfügbar.

> [!NOTE]
> Wenden Sie sich an Ihren derzeitigen E-Mail-Anbieter, um die genauen Schritte für das Einrichten der E-Mail-Weiterleitung zu erfragen.<br/>
> Sie brauchen keine Kopie von Nachrichten beim aktuellen E-Mail-Anbieter zu behalten.<br/>
> Die meisten Anbieter leiten E-Mail so weiter, dass die Antwortadresse des Absenders erhalten bleibt, sodass Antworten an den ursprünglichen Absender gehen.

### <a name="step-9-test-mail-flow"></a>Schritt 9: Testen des Nachrichtenflusses

1. Melden Sie sich mit den Anmeldeinformationen für Benutzer A bei Outlook Web App an.

2. Führen Sie die folgenden Tests aus:

    - Testen Sie lokale Microsoft-E-Mail, indem Sie eine E-Mail z. B. an Benutzer B senden. Die E-Mail wird sofort zugestellt. In diesem Szenario wird die Nachricht nicht an das Postfach für Benutzer B auf dem ursprünglichen Server weitergeleitet, da das Microsoft 365-Postfach lokal ist.

    - Testen Sie E-Mail an einen Benutzer auf dem vorhandenen E-Mail-System, indem Sie eine E-Mail z. B. an Benutzer C senden. Die E-Mail wird an das Postfach für Benutzer C auf Ihrem ursprünglichen E-Mail-Server übermittelt.

    - Überprüfen Sie, ob die Weiterleitung von einem externen Konto oder von einem E-Mail-Konto eines Mitarbeiters auf dem vorhandenen E-Mail-System ordnungsgemäß eingerichtet wurde. Senden Sie beispielsweise vom ursprünglichen Serverkonto für Benutzer C oder einem Hotmail-Konto eine E-Mail an Benutzer A, und überprüfen Sie, ob sie im Microsoft 365-Postfach für Benutzer A eingetroffen ist.

### <a name="step-10-move-mailbox-contents"></a>Schritt 10: Verschieben von Postfachinhalten

Da Sie nur zwei Testbenutzer verschieben und Benutzer A und Benutzer B beide Outlook verwenden, können Sie die E-Mail verschieben, indem Sie die alte .PST-Datei im neuen Outlook-Profil öffnen und die Nachrichten, Kalenderelemente, Kontakte usw. kopieren. Weitere Informationen hierzu finden Sie unter [Importieren von E-Mails, Kontakten und Kalendern aus einer Outlook-PST-Datei](https://support.microsoft.com/office/import-email-contacts-and-calendar-from-an-outlook-pst-file-431a8e9a-f99f-4d5f-ae48-ded54b3440ac).

Nachdem sie in die entsprechenden Speicherorte im Microsoft 365-Postfach importiert wurden, kann auf die Elemente von jedem beliebigen Gerät aus zugegriffen werden.