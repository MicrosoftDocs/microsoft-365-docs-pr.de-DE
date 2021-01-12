---
title: Migrieren von Geschäftlichen E-Mails und Kalendern aus Google Workspace
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie E-Mails, Kontakte und Kalender von Google Workspace zu Microsoft 365 Business migrieren.
ms.openlocfilehash: ab70a43fb7c26c23ebc9024b1cd2803c164a0aa4
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794647"
---
# <a name="migrate-business-email-and-calendar-from-google-workspace"></a>Migrieren von Geschäftlichen E-Mails und Kalendern aus Google Workspace

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LPt6?autoplay=false]

Sie können eine vom Administrator verwaltete Migration zu Exchange Online aus Google Workspace verwenden. Sie können die E-Mails entweder alle gleichzeitig oder phasenweise migrieren. Die folgenden Schritte zeigen, wie Sie die E-Mail-Daten gleichzeitig migrieren. Weitere Informationen finden Sie unter [Ausführen einer G Suite-Migration.](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration)

Der Migrationsprozess dauert mehrere Schritte und kann abhängig von der Datenmenge, die Sie migrieren, mehrere Stunden bis zu ein paar Tage dauern.

## <a name="try-it"></a>Probieren Sie es aus!

### <a name="create-a-google-service-account"></a>Erstellen eines Google -Dienstkontos

1. Melden Sie sich mit einem Browser Chrome bei Ihrer Google Workspace-Verwaltungskonsole [unter admin.google.com](https://admin.google.com). 
1. Navigieren Sie in einer neuen Registerkarte oder einem neuen Fenster zur Seite ["Dienstkonten".](https://console.developers.google.com/iam-admin/serviceaccounts) 
1. Select **Create project,** name the project and choose **Create**. 
1. Wählen **Sie "Dienstkonto erstellen"** aus, geben Sie einen Namen ein, wählen **Sie "Erstellen"** und dann "Fertig" **aus.** 
1. Öffnen Sie das **Menü "Aktionen",** wählen Sie **"Bearbeiten"** aus, und notieren Sie sich die eindeutige ID. Sie benötigen diese ID später im Prozess. 
1. Öffnen Sie den **Abschnitt "Domänenweite Delegierung anzeigen".** 
1. Wählen **Sie "Domänenweite Delegierung für G Suite aktivieren",** geben Sie einen Produktnamen für den Zustimmungsbildschirm ein, und wählen Sie **"Speichern" aus.** 

    > [!NOTE]
> Der Produktname wird nicht vom Migrationsprozess verwendet, sondern zum Speichern im Dialogfeld benötigt.     

1. Öffnen Sie das **Menü "Aktionen"** erneut, und wählen Sie **"Schlüssel erstellen" aus.** 
1. Choose **JSON**, then **Create**. 

     Der private Schlüssel wird im Downloadordner auf Ihrem Gerät gespeichert.
 
1. Wählen Sie **Schließen** aus. 

### <a name="enable-api-usage-for-the-project"></a>Aktivieren der API-Verwendung für das Projekt

1. Navigieren Sie zur [APIs-Seite.](https://console.developers.google.com/apis/library) 
1. Geben Sie in der Suchleiste die **Gmail-API ein.**
1. Wählen Sie es aus, und wählen Sie dann **"Aktivieren" aus.**
1. Wiederholen Sie diesen Vorgang für die Google Kalender-API und die Kontakte-API. 

### <a name="grant-access-to-the-service-account"></a>Gewähren des Zugriffs auf das Dienstkonto

1. Kehren Sie zur Google Workspace-Verwaltungskonsole zurück. 
1. Wählen Sie **Sicherheit** aus, scrollen Sie nach unten, und öffnen Sie **API-Steuerelemente.** 
1. Scrollen Sie nach unten, und wählen **Sie "Domänenweite Delegierung verwalten" aus.**
1. Wählen **Sie "Neu hinzufügen"** aus, und geben Sie die Client-ID ein, die Sie sich zuvor notieren.
1. Geben Sie dann die OAuth-Bereiche für die Google-APIs ein. Diese sind unter [aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#grant-access-to-the-service-account-for-your-google-tenant) Schritt 5 verfügbar und sind:

    `https://mail.google.com/,https://www.googleapis.com/auth/calendar,https://www.google.com/m8/feeds/,https://www.googleapis.com/auth/gmail.settings.sharing`
 
1. Choose **Authorize**. 

### <a name="create-a-sub-domain-for-mail-going-to-microsoft-365"></a>Erstellen einer Unterdomäne für E-Mails an Microsoft 365

1. Kehren Sie zur **Google Workspace-Verwaltungskonsole** zurück.
1. Select **Domains**, **Manage domains**, then, Add a domain **alias**. 
1. Geben Sie einen Domänenalias wie `m365.contoso.com` .
1. Wählen Sie dann **"Weiter" aus, und überprüfen Sie den Domänenbesitz.** 

    Die Domänenüberprüfung dauert in der Regel nur einige Minuten, kann aber bis zu 48 Stunden dauern.

1. Wechseln Sie zum [Microsoft 365 Admin Center.](https://admin.microsoft.com)
1. Wählen Sie **im Microsoft 365 Admin Center** im linken Navigationsbereich **"Alle** anzeigen", **"Einstellungen",** **"Domänen"** und dann **"Domäne hinzufügen" aus.** 
1. Geben Sie die zuvor erstellte Unterdomäne ein, und wählen Sie **dann "Diese Domäne verwenden" aus.** 
1. Um die Domäne zu verbinden, wählen Sie **"Weiter" aus.** 
1. Scrollen Sie nach unten, und notieren Sie sich die MX-, CNAME- und TXT-Einträge. 
1. Kehren Sie zur **Google Admin Konsole zurück.**
1. Select **Domains**, select **Manage domains**, Verify **Details** and then, Manage **domain**. 
1. Wählen Sie in der linken Navigationsleiste **DNS** aus, und scrollen Sie nach unten zu **benutzerdefinierten Ressourceneinträgen.** 
1. Öffnen Sie das Eintragstypdropdown, und wählen Sie **MX** aus, geben Sie die zuvor notierte MX-Eintragsinformationen ein, oder kopieren Sie sie, und fügen Sie sie ein, und wählen Sie dann **"Hinzufügen" aus.** 
1. Wiederholen Sie den Vorgang für den #A0 und den TXT-Eintrag. 

    Es kann einige Zeit dauern, bis diese Änderungen wirksam werden.  

1. Kehren Sie zu dem Ort zurück, an dem Sie im **Microsoft 365 Admin Center** auf dem Weg waren, und wählen Sie **"Weiter" aus.** 

Ihre Domäne ist jetzt eingerichtet.  

### <a name="create-email-aliases-in-microsoft-365"></a>Erstellen von E-Mail-Aliasen in Microsoft 365

Bevor die Migration beginnen kann, müssen Sie E-Mail-Aliase für Ihre Benutzer mit der neuen Unterdomäne erstellen. 

1. Um den nächsten Schritt  zu starten, wählen Sie im Assistenten zum Hinzufügen von Domänen im Microsoft 365 Admin Center **"Zu aktive Benutzer wechseln" aus.** 
1. Wählen Sie einen Benutzer aus, und verwalten **Sie dann Benutzernamen und E-Mails.** 
1. Wählen Sie **in der Dropdownliste** "Domänen" die Zuvor erstellte Unterdomäne aus. 
1. Geben Sie einen Benutzernamen ein, wählen **Sie "Hinzufügen",** **"Änderungen speichern"** aus, und schließen Sie das Fenster. 

    Wiederholen Sie diesen Vorgang für jeden Benutzer. 

### <a name="start-the-migration-process"></a>Starten des Migrationsprozesses

Sobald Sie fertig sind, können Sie migrieren. 

1. Scrollen Sie in der linken Navigationsleiste des **Microsoft 365 Admin Centers** nach unten zu Admin **Center,** und wählen Sie **Exchange aus.** 
1. Wählen **Sie unter "Empfänger"** **die Option "Migration",** **"Neu",** **"Zu Exchange Online** migrieren", **"G Suite-Migration"** und dann **"Weiter" aus.** 
1. Erstellen Sie eine CSV-Datei mit einer Liste der Postfächer, die Sie migrieren möchten. Stellen Sie sicher, dass die Datei dieses Format verwendet: 

    ```CSV
    EmailAddress
    will@fabrikaminc.net
    user123@fabrikaminc.net
    ```

      Weitere Informationen finden Sie [unter aka.ms/GoogleWorkspaceMigration](https://docs.microsoft.com/exchange/mailbox-migration/perform-g-suite-migration#start-a-g-suite-migration-batch-with-the-exchange-admin-center-eac). 

1. Select **Choose File**, navigate to the CSV file, choose it, select **Open**, then **Next**. 
1. Überprüfen Sie die Administrator-E-Mail-Adresse, die Sie zu Testzwecken verwenden möchten. 
1. Select **Choose File**, navigate to the JSON file you created earlier (usually in the Downloads folder on your computer), choose it, select **Open**, then **Next**. 
1. Geben Sie einen Namen in das Feld **"Neuer Migrationsbatchname" ein.**
1. Geben Sie die Von Ihnen erstellte Unterdomäne im Feld **Zielzustellungsdomäne** ein, wählen Sie **"Weiter"** und dann **"Neu" aus.** 
1. Nachdem die Informationen gespeichert wurden, wählen Sie **OK aus.** 

    Sie können jetzt den Status Ihrer Migration anzeigen. 

1. Wählen Sie nach einiger Zeit abhängig von der Anzahl der Benutzer, die Sie migrieren, die Option **"Aktualisieren" aus.** 
1. Nachdem der Status in **"Synchronisiert" geändert** wurde, wählen **Sie "Diesen Migrationsbatch abschließen"** und dann **"Ja" aus.** 
1. Sobald der Prozess abgeschlossen ist, wird Ihr Status in Abgeschlossen **geändert.** 
1. Wenn Sie möchten, können Sie Details **anzeigen auswählen,** um weitere Informationen zur Migration zu erhalten. 
1. Wählen Sie **Schließen** aus. 
1. Öffnen Sie Outlook, um zu überprüfen, ob alle E-Mails von Google Workspace erfolgreich migriert wurden.
Sie können dies auch für Kalenderelemente und Kontakte wiederholen.