---
title: Verhinderung von Datenverlust (DLP) und Microsoft Teams.
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Microsoft Teams Chats und Kanäle unterstützen DLP-Richtlinien (Data Loss Prevention).
ms.openlocfilehash: 6467ae7fdfc9c8636bd306efde5cb89c100e5e6c
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782561"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Verhinderung von Datenverlust (DLP) und Microsoft Teams.

Wenn Ihre Organisation über Verhinderung von Datenverlust (Data Loss Prevention, DLP) verfügt, können Sie Richtlinien definieren, die verhindern, dass Personen vertrauliche Informationen in einer Microsoft Teams Kanal- oder Chatsitzung freigeben. Hier sind einige Beispiele für die Funktionsweise dieses Schutzes:

- **Beispiel 1: Schützen vertraulicher Informationen in Nachrichten.** Angenommen, jemand versucht, vertrauliche Informationen in einem Teams Chat oder Kanal für Gäste (externe Benutzer) freizugeben. Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, werden Nachrichten mit vertraulichen Informationen, die an externe Benutzer gesendet werden, gelöscht. Dies geschieht automatisch und innerhalb von Sekunden entsprechend der Konfiguration Ihrer DLP-Richtlinie.

    > [!NOTE]
    > DLP für Microsoft Teams blockiert vertrauliche Inhalte, wenn sie für Microsoft Teams Benutzer freigegeben werden, die Folgendes haben:<br/>- [Gastzugriff](/MicrosoftTeams/guest-access) in Teams und Kanälen; Oder<br/>- [Externer Zugriff](/MicrosoftTeams/manage-external-access) in Besprechungen und Chatsitzungen. <p>DLP für externe Chatsitzungen funktioniert nur, wenn sich sowohl der Absender als auch der Empfänger im modus "Nur" Teams befinden und [Microsoft Teams systemeigenen Partnerverbund](/microsoftteams/manage-external-access)verwenden. DLP für Teams blockiert keine Nachrichten in [der Interoperabilität](/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) mit Skype for Business oder nicht systemeigenen Verbundchatsitzungen.

- **Beispiel 2: Schützen vertraulicher Informationen in Dokumenten.** Angenommen, jemand versucht, ein Dokument für Gäste in einem Microsoft Teams Kanal oder Chat freizugeben, und das Dokument enthält vertrauliche Informationen. Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, wird das Dokument für diese Benutzer nicht geöffnet. Ihre DLP-Richtlinie muss SharePoint und OneDrive einschließen, damit ein Schutz besteht. Dies ist ein Beispiel für DLP für SharePoint, das in Microsoft Teams angezeigt wird und daher erfordert, dass Benutzer für Office 365 DLP lizenziert sind (in Office 365 E3 enthalten), aber keine Benutzer für Office 365 Advanced Compliance lizenziert werden müssen.)

## <a name="dlp-licensing-for-microsoft-teams"></a>DLP-Lizenzierung für Microsoft Teams

Die Funktionen [zur Verhinderung von Datenverlust](dlp-learn-about-dlp.md) wurden erweitert, um Microsoft Teams Chat- und Kanalnachrichten **einzuschließen, einschließlich Nachrichten aus privaten Kanälen** für:

- Office 365 E5/A5
- Microsoft 365 E5/A5
- Microsoft 365 A5 Information Protection und Governance
- Office 365 Advanced Compliance

Office 365 und Microsoft 365 E3 DLP-Schutz für SharePoint Online, OneDrive und Exchange Online enthalten. Dies umfasst auch Dateien, die über Teams freigegeben werden, da Teams SharePoint Online und OneDrive zum Freigeben von Dateien verwendet.

Für die Unterstützung des DLP-Schutzes in Teams Chat ist E5 erforderlich.

Weitere Informationen zu den Lizenzierungsanforderungen finden Sie unter [Microsoft 365-Dienste auf Mandantenebene – Leitfaden zur Lizenzierung](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).

> [!IMPORTANT]
> DLP gilt nur für die tatsächlichen Nachrichten im Chat- oder Kanalthread. Aktivitätsbenachrichtigungen – die eine kurze Nachrichtenvorschau enthalten und basierend auf den Benachrichtigungseinstellungen eines Benutzers angezeigt werden – sind **nicht** in Teams DLP enthalten. Alle vertraulichen Informationen, die in dem Teil der Nachricht vorhanden sind, der in der Vorschau angezeigt wird, bleiben in der Benachrichtigung sichtbar, auch nachdem die DLP-Richtlinie angewendet und vertrauliche Informationen entfernt wurde.

## <a name="scope-of-dlp-protection"></a>Umfang des DLP-Schutzes

DLP-Schutz wird auf Teams Entitäten unterschiedlich angewendet.

|Benutzerkonten/Gruppen/Liste  |Teams Entität |DLP-Schutz verfügbar|
|---------|---------|---------|
|Einzelne Benutzerkonten     |1:1/n-Chats         |ja         |
|     |Allgemeine Chats         |nein         |
|     |Private Kanäle         |ja         |
|Sicherheitsgruppen/Verteilerlisten  | 1:1/n-Chats         |ja         |
|     |Allgemeine Chats         |nein         |
|     |Private Kanäle         |ja        |
|Microsoft 365 Gruppe    |1:1/n-Chats          |nein         |
|     |Allgemeine Chats          |ja        |
|     |Private Kanäle|nein| 


## <a name="policy-tips-help-educate-users"></a>Richtlinientipps helfen bei der Schulung von Benutzern

Ähnlich wie DLP in [Exchange, Outlook, Outlook im Web,](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web) [SharePoint Online, OneDrive for Business Websites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)und Office [Desktopclients,](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)werden Richtlinientipps angezeigt, wenn eine Aktion mit einer DLP-Richtlinie ausgelöst wird. Hier ist ein Beispiel für einen Richtlinientipp:

![Benachrichtigung über blockierte Nachrichten in Teams](../media/dlp-teams-blockedmessage-notification.png)

Hier hat der Absender versucht, eine Sozialversicherungsnummer in einem Microsoft Teams Kanal freizugeben. Über den Link **"Was kann ich tun?"** wird ein Dialogfeld geöffnet, das Optionen für den Absender zur Behebung des Problems bereitstellt. Beachten Sie, dass der Absender die Richtlinie außer Kraft setzen oder einen Administrator benachrichtigen kann, die Richtlinie zu überprüfen und zu beheben.

![Optionen zum Auflösen blockierter Nachrichten](../media/dlp-teams-blockedmessage-possibleactions.png)

In Ihrer Organisation können Sie festlegen, dass Benutzer eine DLP-Richtlinie außer Kraft setzen können. Wenn Sie Ihre DLP-Richtlinien konfigurieren, können Sie die Standardrichtlinientipps verwenden oder [Richtlinientipps](#to-customize-policy-tips) für Ihre Organisation anpassen.

Wenn Sie zu unserem Beispiel zurückkehren, in dem ein Absender eine Sozialversicherungsnummer in einem Teams Kanal freigegeben hat, sieht der Empfänger Folgendes:

> [!div class="mx-imgBorder"]
> ![Nachricht blockiert](../media/dlp-teams-blockedmessage-notification-to-user.png)

### <a name="to-customize-policy-tips"></a>Anpassen von Richtlinientipps

Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt. Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).

1. Wechseln Sie zum Compliance Center ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie "Richtlinie **zur Verhinderung von Datenverlust"**  >  aus.

3. Wählen Sie eine Richtlinie aus, und wählen Sie neben **den Richtlinieneinstellungen** **"Bearbeiten"** aus.

4. Erstellen Sie entweder eine neue Regel, oder bearbeiten Sie eine vorhandene Regel für die Richtlinie.

    > [!div class="mx-imgBorder"]
    > ![Bearbeiten einer Regel für eine Richtlinie](../media/dlp-teams-editrule.png)

5. Wählen Sie auf der Registerkarte **"Benutzerbenachrichtigungen"** die Option **"E-Mail-Text anpassen"** und/oder **"Richtlinientipp-Textoptionen anpassen"** aus.

    > [!div class="mx-imgBorder"]
    > ![Anpassen von Benutzerbenachrichtigungen und Richtlinientipps](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Geben Sie den Text an, den Sie für E-Mail-Benachrichtigungen und/oder Richtlinientipps verwenden möchten, und wählen Sie dann **Speichern** aus.

7. Wählen Sie auf der Registerkarte **"Richtlinieneinstellungen"** die Option **"Speichern"** aus.

Lassen Sie ungefähr eine Stunde zu, bis Ihre Änderungen sich in Ihrem Rechenzentrum befinden und mit Benutzerkonten synchronisiert werden.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Hinzufügen von Microsoft Teams als Speicherort zu bestehenden DLP-Richtlinien

Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt. Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).

1. Wechseln Sie zum Compliance Center ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie "Richtlinie **zur Verhinderung von Datenverlust"**  >  aus.

3. Wählen Sie eine Richtlinie aus, und sehen Sie sich die Werte unter **Speicherorte an.** Wenn **Teams Chat- und Kanalnachrichten** angezeigt wird, sind Sie alle festgelegt. Wenn Dies nicht der Fall ist, klicken Sie auf **"Bearbeiten".**

    > [!div class="mx-imgBorder"]
    > ![Speicherorte für vorhandene Richtlinien](../media/dlp-teams-editexistingpolicy.png)

4. Aktivieren Sie in der Spalte **"Status"** die Richtlinie für **Teams Chat- und Kanalnachrichten.**

    > [!div class="mx-imgBorder"]
    > ![DLP für Teams Chats und Kanäle](../media/dlp-teams-addteamschatschannels.png)

5. Behalten Sie auf der Registerkarte **"Speicherorte auswählen"** die Standardeinstellung aller Konten bei, oder wählen Sie **"Bestimmte Speicherorte auswählen"** aus. Sie können Folgendes angeben:

    1. bis zu 1.000 einzelne Konten, die ein- oder ausgeschlossen werden sollen
    1. Verteilerlisten und Sicherheitsgruppen, die eingeschlossen oder ausgeschlossen werden sollen. 
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. Wählen Sie dann **Weiter** aus.

7. Klicken Sie auf **Speichern**.

Lassen Sie ungefähr eine Stunde zu, bis Ihre Änderungen sich in Ihrem Rechenzentrum befinden und mit Benutzerkonten synchronisiert werden.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definieren einer neuen DLP-Richtlinie für Microsoft Teams

Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt. Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).

1. Wechseln Sie zum Compliance Center ( [https://compliance.microsoft.com](https://compliance.microsoft.com) ), und melden Sie sich an.

2. Wählen Sie "Richtlinie **zur Verhinderung von Datenverlust"**  >    >  **und "Richtlinie erstellen"** aus.

3. Wählen Sie eine [Vorlage](data-loss-prevention-policies.md#dlp-policy-templates)aus, und klicken Sie dann auf **"Weiter".**

    In unserem Beispiel haben wir die Vorlage für personenbezogene Informationen in den USA ausgewählt.

    > [!div class="mx-imgBorder"]
    > ![Datenschutzvorlage für DLP-Richtlinie](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. Geben Sie auf der Registerkarte **"Name Ihrer Richtlinie"** einen Namen und eine Beschreibung für die Richtlinie an, und wählen Sie dann **"Weiter"** aus.

5. Behalten Sie auf der Registerkarte **"Speicherorte auswählen"** die Standardeinstellung aller Konten bei, oder wählen Sie **"Bestimmte Speicherorte auswählen"** aus. Sie können Folgendes angeben:

    1. bis zu 1.000 einzelne Konten, die ein- oder ausgeschlossen werden sollen
    1. Verteilerlisten und Sicherheitsgruppen, die eingeschlossen oder ausgeschlossen werden sollen. **Dies ist eine öffentliche Vorschaufunktion.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

    ![DLP-Richtlinienspeicherorte](../media/dlp-teams-selectlocationsnewpolicy.png)

    > [!NOTE]
    > Wenn Sie sicherstellen möchten, dass Dokumente, die vertrauliche Informationen enthalten, nicht unangemessen in Teams freigegeben werden, stellen Sie sicher, dass **SharePoint Websites** und **OneDrive Konten** sowie **Teams Chat- und Kanalnachrichten** aktiviert sind.

6. On the **Policy settings** tab, under Customize the type of content you want **to protect,** keep the default simple settings, or choose **Use advanced settings**, and then choose **Next**. Wenn Sie erweiterte Einstellungen auswählen, können Sie Regeln für Ihre Richtlinie erstellen oder bearbeiten. Hilfe hierzu finden Sie unter ["Einfache Einstellungen" im Vergleich zu erweiterten Einstellungen.](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)

7.  Überprüfen Sie auf der Registerkarte **"Richtlinieneinstellungen"** unter **"Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?"** die Einstellungen. Hier können Sie auswählen, ob Sie standardmäßige [Richtlinientipps und E-Mail-Benachrichtigungen](use-notifications-and-policy-tips.md)beibehalten oder anpassen möchten.

    > [!div class="mx-imgBorder"]
    > ![DLP-Richtlinieneinstellungen mit Tipps und Benachrichtigungen](../media/dlp-teams-policysettings-tipsemails.png)

    Wenn Sie die Überprüfung oder Bearbeitung der Einstellungen abgeschlossen haben, wählen Sie **Weiter**.

8. Wählen Sie auf der Registerkarte **"Richtlinieneinstellungen"** unter **Möchten Sie die Richtlinie aktivieren oder zuerst testen?** aus, ob Sie die Richtlinie aktivieren, [zuerst testen](dlp-overview-plan-for-dlp.md#policy-deployment)oder vorerst deaktiviert lassen möchten, und klicken Sie dann auf **"Weiter".**

    > [!div class="mx-imgBorder"]
    > ![Angeben, ob die Richtlinie aktiviert werden soll](../media/dlp-teams-policysettings-turnonnow.png)

9. Überprüfen Sie auf der Registerkarte **"Einstellungen überprüfen"** die Einstellungen für Ihre neue Richtlinie. Wählen Sie **"Bearbeiten"** aus, um Änderungen vorzunehmen. Wenn Sie fertig sind, wählen Sie **Erstellen** aus.

Lassen Sie ungefähr eine Stunde zu, bis ihre neue Richtlinie sich in Ihrem Rechenzentrum durcharbeiten und mit Benutzerkonten synchronisieren kann.

## <a name="prevent-external-access-to-sensitive-documents"></a>Verhindern des externen Zugriffs auf vertrauliche Dokumente

Wählen Sie Folgendes aus SharePoint, um sicherzustellen, dass externe Gäste nicht über SharePoint oder standardmäßig Teams auf Dokumente zugreifen können, die vertrauliche Informationen enthalten:

- Sie können sicherstellen, dass Dokumente geschützt sind, bis DLP-Scans ausgeführt werden, und sie als sicher für die Freigabe kennzeichnen, indem Sie [neue Dateien standardmäßig als vertraulich markieren.](/sharepoint/sensitive-by-default)

- Empfohlene DLP-Richtlinienstruktur

    - **Bedingungen:**
        - Der Inhalt enthält einen der folgenden vertraulichen Informationstypen: [Alle zutreffenden Auswählen]
        
        - Inhalte werden von Microsoft 365 für Personen außerhalb meiner Organisation freigegeben
        
          > [!div class="mx-imgBorder"]
          > ![DLP-Bedingungen zum Erkennen der externen Freigabe vertraulicher Inhalte](../media/dlp-teams-external-sharing/external-condition.png)

    - **Aktionen**
        - Zugriff auf den Inhalt für externe Benutzer einschränken
        
        - Benutzer per E-Mail und mit Richtlinientipps benachrichtigen
        
        - Vorfallberichte an den Administrator senden
        
        > [!div class="mx-imgBorder"]
        > ![DLP-Aktion zum Blockieren der externen Freigabe vertraulicher Inhalte](../media/dlp-teams-external-sharing/external-action.png)

DLP-Richtlinie in Aktion beim Versuch, ein Dokument in SharePoint freizugeben, das vertrauliche Informationen für einen externen Gast enthält:

> [!div class="mx-imgBorder"]
> ![Externe Freigabe blockiert](../media/dlp-teams-external-sharing/external-sharing-blocked.png)


DLP-Richtlinie in Aktion, wenn Gast versucht, ein Dokument in Teams mit externem Block zu öffnen:

> [!div class="mx-imgBorder"]
> ![Externer Zugriff blockiert](../media/dlp-teams-external-sharing/external-access-blocked.png)

## <a name="related-articles"></a>Verwandte Artikel

- [Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)
- [Senden von E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien](use-notifications-and-policy-tips.md)
