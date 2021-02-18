---
title: Verhinderung von Datenverlust und Microsoft Teams.
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
description: Sie können jetzt die DLP-Richtlinien auf Microsoft Teams-Chats und -Kanäle anwenden. In diesem Artikel erfahren Sie mehr über die Funktionsweise.
ms.openlocfilehash: 13d5d73423cc6ad7db76076f6a53dde668b8fa5c
ms.sourcegitcommit: 88820cd2536a7da868e472d10b4d265c52e5692b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/17/2021
ms.locfileid: "50279363"
---
# <a name="data-loss-prevention-and-microsoft-teams"></a>Verhinderung von Datenverlust und Microsoft Teams.

> [!NOTE]
> Funktionen zur Verhinderung von Datenverlust wurden kürzlich zu Microsoft Teams Chat- und Kanalnachrichten für Benutzer hinzugefügt, die für Office 365 E5/A5, Microsoft 365 E5/A5, Microsoft 365 Information Protection and Governance oder Office 365 Advanced Compliance lizenziert sind. Office 365 und Microsoft 365 E3 umfassen #A0 für SharePoint Online, OneDrive und Exchange Online. Dies umfasst auch Dateien, die über Teams freigegeben werden, da Teams SharePoint Online und OneDrive zum Freigeben von Dateien verwendet.
Für die Unterstützung des DLP-Schutzes in Teams Chat ist E5 erforderlich.
Weitere Informationen zu den Lizenzierungsanforderungen finden Sie unter [Microsoft 365-Dienste auf Mandantenebene – Leitfaden zur Lizenzierung](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance).

> [!IMPORTANT]
> DLP für Teams wird nur unterstützt, wenn der Benutzer über ein Postfach in Exchange Online verfügt.

## <a name="overview-of-dlp-for-microsoft-teams"></a>Übersicht über DLP für Microsoft Teams

In letzter Zeit wurden die Funktionen zur Verhinderung von Datenverlust (Data [Loss Prevention,](data-loss-prevention-policies.md) DLP) um Chat- und Kanalnachrichten von Microsoft Teams erweitert, einschließlich Nachrichten **im privaten Kanal.**

Wenn Ihre Organisation über DLP verfügt, können Sie jetzt Richtlinien definieren, die verhindern, dass Personen vertrauliche Informationen in einem Microsoft Teams-Kanal oder einer Chatsitzung freigeben. Hier sind einige Beispiele für die Funktionsweise dieses Schutzes:

- **Beispiel 1: Schützen vertraulicher Informationen in Nachrichten**. Angenommen, jemand versucht, vertrauliche Informationen in einem Chat oder Kanal von Teams für Gäste (externe Benutzer) zu teilen. Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, werden Nachrichten mit vertraulichen Informationen gelöscht, die an externe Benutzer gesendet werden. Dies geschieht automatisch und innerhalb von Sekunden, je nach Konfiguration Ihrer DLP-Richtlinie.

    > [!NOTE]
    > DLP für Microsoft Teams blockiert vertrauliche Inhalte, wenn sie für Microsoft Teams-Benutzer freigegeben werden, die über:<br/>- [Gastzugriff](https://docs.microsoft.com/MicrosoftTeams/guest-access) in Teams und Kanälen; oder<br/>- [Externer Zugriff](https://docs.microsoft.com/MicrosoftTeams/manage-external-access) in Besprechungen und Chatsitzungen. <p>DLP für externe Chatsitzungen funktioniert nur, wenn sich der Absender und der Empfänger im Modus "Nur Teams" befinden und den nativen [Microsoft Teams-Verbund verwenden.](https://docs.microsoft.com/microsoftteams/manage-external-access) DLP für Teams blockiert keine Nachrichten in [Interop](https://docs.microsoft.com/microsoftteams/teams-and-skypeforbusiness-coexistence-and-interoperability#interoperability-of-teams-and-skype-for-business) mit Skype for Business oder nicht systemeigenen Verbundchatsitzungen.

- **Beispiel 2: Schützen vertraulicher Informationen in Dokumenten**. Angenommen, jemand versucht, ein Dokument für Gäste in einem Microsoft Teams-Kanal oder -Chat zu teilen, und das Dokument enthält vertrauliche Informationen. Wenn Sie eine DLP-Richtlinie definiert haben, um dies zu verhindern, wird das Dokument für diese Benutzer nicht geöffnet. Beachten Sie, dass Ihre #A0 in diesem Fall SharePoint und OneDrive enthalten muss, damit der Schutz möglich ist. (Dies ist ein Beispiel für DLP für SharePoint, das in Microsoft Teams verfügbar ist und daher erfordert, dass Benutzer für Office 365 DLP (in Office 365 E3 enthalten) lizenziert sind, aber keine Lizenz für Office 365 Advanced Compliance benötigen.)

## <a name="policy-tips-help-educate-users"></a>Richtlinientipps helfen Bei der Schulung von Benutzern

Ähnlich wie DLP in [Exchange-, Outlook-, Outlook](data-loss-prevention-policies.md#policy-evaluation-in-exchange-online-outlook-and-outlook-on-the-web)im Web-, [SharePoint Online-, OneDrive for #A0](data-loss-prevention-policies.md#policy-evaluation-in-onedrive-for-business-and-sharepoint-online-sites)und [#A1](data-loss-prevention-policies.md#policy-evaluation-in-the-office-desktop-programs)funktioniert, werden Richtlinientipps angezeigt, wenn eine Aktion mit einer #A2 in Konflikt steht. Hier ist ein Beispiel für einen Richtlinientipp:

![Benachrichtigung über blockierte Nachrichten in Teams](../media/dlp-teams-blockedmessage-notification.png)

In diesem Fall hat der Absender versucht, eine Sozialversicherungsnummer in einem Microsoft Teams-Kanal zu teilen. Über **den Link "Was kann ich tun?** " wird ein Dialogfeld geöffnet, in dem Optionen für den Absender zum Beheben des Problems angezeigt werden. Beachten Sie, dass der Absender in diesem Fall die Richtlinie außer Kraft setzen oder einen Administrator benachrichtigen kann, die Richtlinie zu überprüfen und zu beheben.

![Optionen zum Auflösen blockierter Nachrichten](../media/dlp-teams-blockedmessage-possibleactions.png)

In Ihrer Organisation können Sie festlegen, dass Benutzer eine DLP-Richtlinie außer Kraft setzen können. Und wenn Sie Ihre DLP-Richtlinien konfigurieren, können Sie die Standardrichtlinientipps verwenden oder Richtlinientipps für [Ihre](#to-customize-policy-tips) Organisation anpassen.

Kehren wir zu unserem Beispiel zurück, in dem ein Absender eine Sozialversicherungsnummer in einem Kanal von Teams freigegeben hat, und das hat der Empfänger gesehen:

![Nachricht blockiert](../media/dlp-teams-blockedmessage-notification-to-user.png)

Der **Link "Was ist das?** " öffnet einen [Artikel](data-loss-prevention-policies.md) zu DLP-Richtlinien, in dem erläutert wird, warum die Nachricht blockiert wurde.

### <a name="to-customize-policy-tips"></a>So passen Sie Richtlinientipps an

Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle mit Berechtigungen zum Bearbeiten von DLP-Richtlinien zugewiesen sein. Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).

1. Wechseln Sie zum Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ), und melden Sie sich an.

2. Wählen **Sie "Richtlinie zur Verhinderung von**  >  **Datenverlust" aus.**

3. Wählen Sie eine Richtlinie aus, und wählen Sie neben **den Richtlinieneinstellungen** **"Bearbeiten" aus.**

4. Erstellen Sie entweder eine neue Regel, oder bearbeiten Sie eine vorhandene Regel für die Richtlinie.<br/>![Bearbeiten einer Regel für eine Richtlinie](../media/dlp-teams-editrule.png)<br/>

5. Wählen Sie **auf der Registerkarte "Benutzerbenachrichtigungen"** die Option "E-Mail-Text **anpassen"** und/oder "Richtlinientipptextoptionen **anpassen"** aus.<br/>![Anpassen von Benutzerbenachrichtigungen und Richtlinientipps](../media/dlp-teams-editrule-usernotifications.png)<br/>  

6. Geben Sie den Text an, den Sie für E-Mail-Benachrichtigungen und/oder Richtlinientipps verwenden möchten, und wählen Sie dann **"Speichern" aus.**

7. Wählen Sie **auf der Registerkarte** "Richtlinieneinstellungen" **"Speichern" aus.**

Lassen Sie ungefähr eine Stunde zeit, bis Ihre Änderungen ihren Weg durch Ihr Rechenzentrum finden und mit Benutzerkonten synchronisiert werden.
 <!-- why are these syncing to user accounts? -->

## <a name="add-microsoft-teams-as-a-location-to-existing-dlp-policies"></a>Hinzufügen von Microsoft Teams als Speicherort zu vorhandenen DLP-Richtlinien

Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle mit Berechtigungen zum Bearbeiten von DLP-Richtlinien zugewiesen sein. Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).

1. Wechseln Sie zum Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ), und melden Sie sich an.

2. Wählen **Sie "Richtlinie zur Verhinderung von**  >  **Datenverlust" aus.**

3. Wählen Sie eine Richtlinie aus, und sehen Sie sich die Werte unter **"Speicherorte" an.** Wenn Teams **Chat- und Kanalnachrichten angezeigt werden,** sind Sie alle festgelegt. Wenn Sie dies nicht möchten, klicken Sie auf **Bearbeiten**.<br/>![Speicherorte für vorhandene Richtlinien](../media/dlp-teams-editexistingpolicy.png)<br/>

4. Aktivieren Sie **in der** Spalte "Status" die Richtlinie für **Chat- und Kanalnachrichten in Teams.**<br/>![DLP für Chats und Kanäle in Teams](../media/dlp-teams-addteamschatschannels.png)<br/>

5. Behalten Sie **auf der** Registerkarte "Speicherorte auswählen" die Standardeinstellung aller Konten bei, oder wählen Sie "Bestimmte **Speicherorte auswählen" aus.** Sie können Folgendes angeben:
    1. Bis zu 1.000 einzelne Konten zum Ein- oder Ausschließen
    1. Verteilerlisten und Sicherheitsgruppen, die ein- oder ausgeschlossen werden. **Dies ist eine öffentliche Vorschaufunktion.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**--> 
    
6. Wählen Sie dann **Weiter** aus.



6. Klicken Sie auf **Speichern**.

Lassen Sie ungefähr eine Stunde zeit, bis Ihre Änderungen ihren Weg durch Ihr Rechenzentrum finden und mit Benutzerkonten synchronisiert werden.
<!-- again, why user accounts? -->

## <a name="define-a-new-dlp-policy-for-microsoft-teams"></a>Definieren einer neuen DLP-Richtlinie für Microsoft Teams

Um diese Aufgabe ausführen zu können, muss Ihnen eine Rolle mit Berechtigungen zum Bearbeiten von DLP-Richtlinien zugewiesen sein. Weitere Informationen hierzu finden Sie unter [Berechtigungen](data-loss-prevention-policies.md#permissions).

1. Wechseln Sie zum Security & Compliance Center ( [https://protection.office.com](https://protection.office.com) ), und melden Sie sich an.

2. Wählen **Sie "Richtlinie zur Verhinderung von**  >    >  **Datenverlust" + "Richtlinie erstellen" aus.**

3. Wählen Sie [eine Vorlage](data-loss-prevention-policies.md#dlp-policy-templates)aus, und wählen Sie dann **"Weiter" aus.**<br/>In unserem Beispiel haben wir die Us-amerikanische Vorlage für personenbezogene Daten ausgewählt.<br/>![Datenschutzvorlage für die DLP-Richtlinie](../media/dlp-teams-createnewpolicy-template.png)<br/>

4. Geben Sie **auf der Registerkarte "Ihre Richtlinie** benennen" einen Namen und eine Beschreibung für die Richtlinie an, und wählen Sie dann **"Weiter" aus.**

5. Behalten Sie **auf der** Registerkarte "Speicherorte auswählen" die Standardeinstellung aller Konten bei, oder wählen Sie "Bestimmte **Speicherorte auswählen" aus.** Sie können Folgendes angeben:
    1. Bis zu 1.000 einzelne Konten zum Ein- oder Ausschließen
    1. Verteilerlisten und Sicherheitsgruppen, die ein- oder ausgeschlossen werden. **Dies ist eine öffentliche Vorschaufunktion.**
    <!-- 1. the shared mailbox of a shared channel. **This is a public preview feature.**-->  

![Speicherorte von DLP-Richtlinien](../media/dlp-teams-selectlocationsnewpolicy.png)

> [!NOTE]
> Wenn Sie sicherstellen möchten, dass Dokumente, die vertrauliche Informationen enthalten, nicht  unangemessen in Teams freigegeben werden, stellen Sie sicher, dass #A0 und #A1 sowie Chat- und Kanalnachrichten von Teams aktiviert **sind.** 


6. Behalten Sie **auf** der Registerkarte "Richtlinieneinstellungen" unter "Anpassen des zu schützende Inhaltstyps" die einfachen Standardeinstellungen bei, oder wählen Sie "Erweiterte Einstellungen verwenden" **aus,** und wählen Sie dann **"Weiter" aus.** Wenn Sie erweiterte Einstellungen auswählen, können Sie Regeln für Ihre Richtlinie erstellen oder bearbeiten. (Hilfe dazu finden Sie unter ["Einfache Einstellungen" im Vergleich zu erweiterten Einstellungen.)](data-loss-prevention-policies.md#simple-settings-vs-advanced-settings)

7.  Überprüfen Sie **auf der** Registerkarte "Richtlinieneinstellungen" unter "Was möchten Sie tun, wenn vertrauliche Informationen erkannt **werden?"** die Einstellungen. (Hier können Sie auswählen, ob Sie Standardmäßige [Richtlinientipps](use-notifications-and-policy-tips.md)und E-Mail-Benachrichtigungen behalten oder anpassen möchten.)<br/>![DLP-Richtlinieneinstellungen mit Tipps und Benachrichtigungen](../media/dlp-teams-policysettings-tipsemails.png)<br/>Wenn Sie die Einstellungen überprüft oder bearbeitet haben, wählen Sie **"Weiter" aus.**

8. On the **Policy settings tab,** under **Do you want to turn on the policy or test things out first?**, choose whether to turn the policy on, [test it first](data-loss-prevention-policies.md#roll-out-dlp-policies-gradually-with-test-mode), or keep it turned off for now, and then choose **Next**.<br/>![Angeben, ob die Richtlinie aktivieren soll](../media/dlp-teams-policysettings-turnonnow.png)<br/>

9. Überprüfen Sie **auf der Registerkarte "Einstellungen überprüfen"** die Einstellungen für die neue Richtlinie. Wählen Sie **"Bearbeiten"** aus, um Änderungen vorzunehmen. Wenn Sie fertig sind, wählen Sie **"Erstellen" aus.**

Es dauert ungefähr eine Stunde, bis die neue Richtlinie ihren Weg durch Ihr Rechenzentrum durcharbeiten und mit Benutzerkonten synchronisiert wird.

## <a name="prevent-external-access-to-sensitive-documents"></a>Verhindern des externen Zugriffs auf vertrauliche Dokumente

Um sicherzustellen, dass externe Gäste standardmäßig nicht von SharePoint oder Teams aus auf SharePoint-Dokumente zugreifen können, die vertrauliche Informationen enthalten, wählen Sie Folgendes aus:

- Sie können sicherstellen, dass Dokumente geschützt sind, bis DLP sie überprüft und als sicher für die Freigabe markiert, indem Sie neue Dateien standardmäßig als [vertraulich kennzeichnen.](https://docs.microsoft.com/sharepoint/sensitive-by-default)
- Empfohlene Struktur der DLP-Richtlinie
    - **Bedingungen:**
        - Inhalt enthält einen der folgenden Typen vertraulicher Informationen: [Alle angewendeten Auswählen]
        - Inhalte werden von Microsoft 365 für Personen außerhalb meiner Organisation freigegeben.
        <br/>![DLP-Bedingungen zum Erkennen der externen Freigabe vertraulicher Inhalte](../media/dlp-teams-external-sharing/external-condition.png)<br/>


    - **Aktionen**
        - Einschränken des Zugriffs auf inhalte für externe Benutzer
        - Benachrichtigen von Benutzern mit E-Mail- und Richtlinientipps
        - Senden von Vorfallberichten an den Administrator    
        <br/>![DLP-Aktion zum Blockieren der externen Freigabe vertraulicher Inhalte](../media/dlp-teams-external-sharing/external-action.png)<br/>

DLP-Richtlinie in Aktion beim Versuch, ein Dokument in SharePoint zu teilen, das vertrauliche Informationen für einen externen Gast enthält:
<br/>![Externe Freigabe blockiert](../media/dlp-teams-external-sharing/external-sharing-blocked.png)<br/>


DLP-Richtlinie in Aktion, wenn Gast versucht, ein Dokument in Teams zu öffnen, bei dem externe Daten blockiert werden:
<br/>![Externer Zugriff blockiert](../media/dlp-teams-external-sharing/external-access-blocked.png)<br/>

## <a name="related-articles"></a>Verwandte Artikel

[Erstellen, Testen und Optimieren einer DLP-Richtlinie](create-test-tune-dlp-policy.md)

[Senden von E-Mail-Benachrichtigungen und Anzeigen von Richtlinientipps für DLP-Richtlinien](use-notifications-and-policy-tips.md)
