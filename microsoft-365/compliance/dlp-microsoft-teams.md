---
title: Verhinderung von Datenverlust und Microsoft Teams
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
description: Sie können jetzt DLP-Richtlinien auf Chats und Kanäle von Microsoft Teams anwenden. Lesen Sie diesen Artikel, um mehr über die Funktionsweise zu erfahren.
ms.openlocfilehash: 290e1e7a7c3fd395c1f7e1739b08eba64c8d2d8d
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2020
ms.locfileid: "43633054"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Verhinderung von Datenverlust und Microsoft Teams

> [!NOTE]
> Kürzlich wurden Funktionen zur Verhinderung von Datenverlust zu den Microsoft Teams-Chat- und Kanalnachrichten für Benutzer hinzugefügt, die für Office 365 Advanced Compliance lizensiert sind. Sie sind als eigenständige Option verfügbar und in Office 365 E5 und Microsoft 365 E5 Compliance enthalten. Office 365 und Microsoft 365 E3 umfassen DLP-Schutz für SharePoint Online, OneDrive und Exchange Online. Dies umfasst auch Dateien, die über Teams freigegeben werden, da Microsoft Teams SharePoint Online und OneDrive zum Freigeben von Dateien verwendet.
Für die Unterstützung des DLP-Schutzes im Teamchat ist E5 erforderlich.
Weitere Informationen zu den Lizenzierungsanforderungen finden Sie unter [Microsoft 365-Dienste auf Mandantenebene – Leitfaden zur Lizenzierung](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

## <a name="overview-of-dlp-for-microsoft-teams"></a>Übersicht über DLP für Microsoft Teams

Vor kurzem wurden die Funktionen zur [Verhinderung von Datenverlust (Data Loss Prevention](data-loss-prevention-policies.md) , DLP) auf Microsoft Teams-Chat und Kanal Nachrichten erweitert.

> [!NOTE]
> DLP wird derzeit für private Kanal Nachrichten nicht unterstützt.

Wenn Ihre Organisation über DLP verfügt, können Sie jetzt Richtlinien definieren, die verhindern, dass Personen vertrauliche Informationen in einem Microsoft Teams-Kanal oder in einer Chatsitzung freigeben. Im folgenden finden Sie einige Beispiele für die Funktionsweise dieses Schutzes:

- **Beispiel 1: Schützen vertraulicher Informationen in Nachrichten**. Angenommen, jemand versucht, vertrauliche Informationen in einem Microsoft Teams-Chat oder-Kanal mit Gästen (externe Benutzer) freizugeben. Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, werden Nachrichten mit vertraulichen Informationen, die an externe Benutzer gesendet werden, gelöscht. Dies geschieht automatisch und innerhalb von Sekunden, je nachdem, wie ihre DLP-Richtlinie konfiguriert ist.

    > [!NOTE]
    > DLP für Microsoft Teams blockiert vertrauliche Inhalte, wenn Sie für Microsoft Teams-Benutzer freigegeben werden, die über Folgendes verfügen:<br/>- [Gastzugriff](https://docs.microsoft.com/MicrosoftTeams/guest-access) in Teams und Kanälen; oder<br/>- [externer Zugriff](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) in Besprechungen und Chatsitzungen. <p>DLP für externe Chatsitzungen funktioniert nur, wenn sich sowohl der Absender als auch der Empfänger im Modus "nur Teams" und unter Verwendung von [Microsoft Teams Native Federation](https://docs.microsoft.com/microsoftteams/manage-external-access)befinden. DLP für Teams blockiert keine Nachrichten in [Interop](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) mit Skype for Business-oder nicht-systemeigenen Sitzungen für den Verbund Chat.

- **Beispiel 2: Schützen vertraulicher Informationen in Dokumenten**. Angenommen, jemand versucht, ein Dokument für Gäste in einem Microsoft Teams-Kanal oder Chat freizugeben, und das Dokument enthält vertrauliche Informationen. Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, wird das Dokument nicht für diese Benutzer geöffnet. Beachten Sie, dass in diesem Fall SharePoint und OneDrive in ihrer DLP-Richtlinie enthalten sein müssen, damit der Schutz vorhanden ist. (Dies ist ein Beispiel für DLP für SharePoint, das in Microsoft Teams angezeigt wird, und erfordert daher, dass Benutzer für Office 365 DLP lizenziert sind (in Office 365 E3 enthalten), erfordert aber keine Lizenzierung von Benutzern für Office 365 Advanced Compliance.)

## <a name="policy-tips-help-educate-users"></a>Richtlinien Tipps helfen Benutzern bei der Schulung

Ähnlich wie DLP in [Exchange, Outlook, Outlook im Internet](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web), [SharePoint Online, OneDrive für Unternehmen Websites](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)und [Office-Desktop Clients](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)funktioniert, werden Richtlinien Tipps angezeigt, wenn eine Aktion mit einer DLP-Richtlinie in Konflikt steht. Im folgenden finden Sie ein Beispiel für einen richtlinientipp:

![Benachrichtigung über blockierte Nachrichten in Microsoft Teams](../media/dlp-teams-blockedmessage-notification.png)

In diesem Fall hat der Absender versucht, eine Sozialversicherungsnummer in einem Microsoft Teams-Kanal freizugeben. Der Link **Was kann ich tun?** öffnet ein Dialogfeld, in dem Optionen für den Absender zum Beheben des Problems bereitgestellt werden. Beachten Sie, dass der Absender in diesem Fall entscheiden kann, die Richtlinie außer Kraft zu setzen oder einen Administrator zu benachrichtigen, um ihn zu überprüfen und zu beheben.

![Optionen zum Auflösen blockierter Nachrichten](../media/dlp-teams-blockedmessage-possibleactions.png)

In Ihrer Organisation können Sie festlegen, dass Benutzer eine DLP-Richtlinie außer Kraft setzen. Wenn Sie Ihre DLP-Richtlinien konfigurieren, können Sie die Standardrichtlinien Tipps verwenden oder [Richtlinien Tipps](#to-customize-policy-tips) für Ihre Organisation anpassen.

Zurück zu unserem Beispiel, in dem ein Absender eine Sozialversicherungsnummer in einem Teams-Kanal freigegeben hat, sehen Sie hier, was der Empfänger gesehen hat:

![Nachricht blockiert](../media/dlp-teams-blockedmessage-notification-to-user.png)

Der Link " **Was ist das?** " öffnet einen [Artikel](data-loss-prevention-policies.md) über DLP-Richtlinien, der erklärt, warum die Nachricht blockiert wurde.

### <a name="to-customize-policy-tips"></a>So passen Sie Richtlinien Tipps an

Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt. Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).

1. Wechseln Sie zum Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), und melden Sie sich an.

2. Wählen Sie > **Richtlinie**zur **Verhinderung von Datenverlust**aus.

3. Wählen Sie eine Richtlinie aus, und wählen Sie neben **Richtlinieneinstellungen**die Option **Bearbeiten**aus.

4. Erstellen Sie entweder eine neue Regel, oder bearbeiten Sie eine vorhandene Regel für die Richtlinie.<br/>![Bearbeiten einer Regel für eine Richtlinie](../media/dlp-teams-editrule.png)<br/>

5. Wählen Sie auf der Registerkarte **Benutzer Benachrichtigungen** die Option **e-Mail-Text anpassen** und/oder **die Textoptionen richtlinientipp anpassen** aus.<br/>![Anpassen von Benutzer Benachrichtigungen und Richtlinien Tipps](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Geben Sie den Text an, der für e-Mail-Benachrichtigungen und/oder Richtlinien Tipps verwendet werden soll, und klicken Sie dann auf **Speichern**.

7. Wählen Sie auf der Registerkarte **Richtlinieneinstellungen** die Option **Speichern**aus.

Lassen Sie ungefähr eine Stunde zu, bis sich Ihre Änderungen durch Ihr Rechenzentrum durchlaufen und mit Benutzerkonten synchronisiert werden.
 <!-- why are these syncing to user accounts? -->
## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Hinzufügen von Microsoft Teams als Standort zu vorhandenen DLP-Richtlinien

Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt. Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).

1. Wechseln Sie zum Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), und melden Sie sich an.

2. Wählen Sie > **Richtlinie**zur **Verhinderung von Datenverlust**aus.

3. Wählen Sie eine Richtlinie aus, und sehen Sie sich die Werte unter **Standorte**an. Wenn Sie Microsoft **Teams-Chat und Kanal Nachrichten**sehen, sind Sie alle festgelegt. Klicken Sie andernfalls auf **Bearbeiten**.<br/>![Speicherorte für vorhandene Richtlinien](../media/dlp-teams-editexistingpolicy.png)<br/>

4. Aktivieren Sie in der Spalte **Status** die Richtlinie für Microsoft **Teams-Chat und Kanal Nachrichten**.<br/>![DLP für Chats und Kanäle in Microsoft Teams](../media/dlp-teams-addteamschatschannels.png)<br/>

5. Behalten Sie die Standardeinstellungen aller Konten bei, oder geben Sie an, welche Konten einbezogen oder ausgeschlossen werden sollen.

6. Klicken Sie auf **Speichern**.

Lassen Sie ungefähr eine Stunde zu, bis sich Ihre Änderungen durch Ihr Rechenzentrum durchlaufen und mit Benutzerkonten synchronisiert werden.
<!-- again, why user accounts? -->
## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definieren einer neuen DLP-Richtlinie für Microsoft Teams

Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle zugewiesen sein, die über Berechtigungen zum Bearbeiten von DLP-Richtlinien verfügt. Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).

1. Wechseln Sie zum Security & Compliance Center ([https://protection.office.com](https://protection.office.com)), und melden Sie sich an.

2. Wählen Sie **Datenverlust-Verhinderung** > -**Richtlinie** > **+ Richtlinie erstellen**.

3. Wählen Sie eine [Vorlage](data-loss-prevention-policies.md#dlp-policy-templates)aus, und klicken Sie dann auf **weiter**.<br/>In unserem Beispiel haben wir die Datenvorlage "U.S. persönlich identifizierbare Informationen" ausgewählt.<br/>![Datenschutz Vorlage für DLP-Richtlinie](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. Geben Sie auf der Registerkarte **Name Ihrer Richtlinie** einen Namen und eine Beschreibung für die Richtlinie ein, und klicken Sie dann auf **weiter**.

5. Behalten Sie auf der Registerkarte **Speicherorte** die Standardeinstellung alle Speicherorte bei, oder wählen Sie die Option **bestimmte Speicherorte**auswählen aus, und klicken Sie dann auf **weiter**.<br/>Wenn Sie bestimmte Standorte ausgewählt haben, wählen Sie diese für ihre DLP-Richtlinie aus, und klicken Sie dann auf **weiter**.<br/>![DLP-Richtlinienspeicher Orte](../media/dlp-teams-selectlocationsnewpolicy.png)<br/>
    > [!NOTE]
    > Wenn Sie sicherstellen möchten, dass Dokumente, die vertrauliche Informationen enthalten, nicht ungeeignet freigegeben werden, stellen Sie sicher, dass **SharePoint-Websites** und **OneDrive-Konten** zusammen mit Microsoft **Teams-Chat und Kanal Nachrichten**aktiviert sind.
    > Kanäle in Microsoft Teams hängen stark von Exchange Online Funktionalität ab. Stellen Sie sicher, dass der **Exchange-e-Mail-** Speicherort auch für die Richtlinien aktiviert ist, die auf den Inhalt der Kanäle angewendet werden sollen.  
<br/>

6. Behalten Sie auf der Registerkarte **Richtlinieneinstellungen** unter **Anpassen des Inhaltstyps, den Sie schützen möchten**, die standardmäßigen einfachen Einstellungen bei, oder wählen Sie **Erweiterte Einstellungen verwenden**aus, und klicken Sie dann auf **weiter**. Wenn Sie erweiterte Einstellungen auswählen, können Sie Regeln für Ihre Richtlinie erstellen oder bearbeiten. (Informationen dazu finden Sie unter [einfache Einstellungen im Vergleich zu erweiterten Einstellungen](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings).)

7.  Überprüfen Sie auf der Registerkarte **Richtlinieneinstellungen** unter **Was möchten Sie tun, wenn vertrauliche Informationen erkannt werden?** die Einstellungen. (Hier können Sie auswählen, ob Standard [Richtlinien Tipps und e-Mail-Benachrichtigungen](use-notifications-and-policy-tips.md)beibehalten oder angepasst werden sollen.)<br/>![DLP-Richtlinieneinstellungen mit Tipps und Benachrichtigungen](../media/dlp-teams-policysettings-tipsemails.png)<br/>Wenn Sie die Überprüfung oder Bearbeitung von Einstellungen abgeschlossen haben, wählen Sie **weiter**aus.

8. Wählen Sie auf der Registerkarte **Richtlinieneinstellungen** unter soll **die Richtlinie aktiviert oder zuerst getestet werden?** aus, ob die Richtlinie aktiviert, [zuerst getestet](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode)oder für jetzt deaktiviert werden soll, und wählen Sie dann **weiter**aus.<br/>![Angeben, ob die Richtlinie aktiviert werden soll](../media/dlp-teams-policysettings-turnonnow.png)<br/>

9. Überprüfen Sie auf der Registerkarte **Einstellungen überprüfen** die Einstellungen für die neue Richtlinie. Wählen Sie **Bearbeiten** aus, um Änderungen vorzunehmen. Wenn Sie fertig sind, wählen Sie **Erstellen**aus.

Lassen Sie die neue Richtlinie ungefähr eine Stunde lang durch Ihr Rechenzentrum arbeiten und mit Benutzerkonten synchronisieren.

## <a name="related-articles"></a>Verwandte Artikel

[Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)

[Senden von E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien](use-notifications-and-policy-tips.md)
