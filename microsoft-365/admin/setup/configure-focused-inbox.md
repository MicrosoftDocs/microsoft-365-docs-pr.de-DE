---
title: Konfigurieren des Posteingangs mit Relevanz für jeden Benutzer in Ihrer Organisation
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 613a845c-4b71-41de-b331-acdcf5b6625d
description: Wenn Sie für die Konfiguration der E-Mail-Einstellungen für alle Mitarbeiter eines Unternehmens verantwortlich sind, wird in diesem Artikel erklärt, wie Sie den Posteingang mit Relevanz für Benutzer konfigurieren.
ms.openlocfilehash: ddd0886988072139a199bfc3f6e8adbbf25ad58b
ms.sourcegitcommit: 686f192e1a650ec805fe8e908b46ca51771ed41f
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52623701"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>Konfigurieren des Posteingangs mit Relevanz für jeden Benutzer in Ihrer Organisation

Wenn Sie dafür zuständig sind, die Funktion der E-Mail für JEDEN in einem Unternehmen zu konfigurieren, dann ist das genau der Artikel für Sie! Es wird erläutert, wie Sie die E-Mail-Funktion für Ihr Unternehmen anpassen oder deaktivieren und beantwortet [Häufig gestellte Fragen](#faq-for-focused-inbox).

Wenn Sie den Posteingang mit Relevanz für sich selbst deaktivieren möchten, lesen Sie [Deaktivieren des Posteingangs mit Relevanz](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).  

Wenn Sie sicher sein möchten, dass Ihre Benutzer geschäftsspezifische E-Mail-Nachrichten wie E-Mails von der Personalabteilung oder der Buchhaltung erhalten, können Sie den Posteingang mit Relevanz so konfigurieren, dass diese Nachrichten in der Ansicht "Relevant" angezeigt werden. Sie können außerdem steuern, ob den Benutzern in Ihrer Organisation der Posteingang mit Relevanz angezeigt wird.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>Aktivieren oder Deaktivieren von "Posteingang mit Relevanz" in Ihrer Organisation

Sie verwenden PowerShell, um den Posteingang mit Relevanz für alle Benutzer in Ihrer Organisation zu aktivieren oder deaktivieren. Möchten Sie diesen Vorgang im Microsoft 365 Admin Center ausführen? Teilen Sie dies unserem Entwicklungsteam mit. **[Stimmen Sie hier ab!](https://go.microsoft.com/fwlink/?linkid=862489)**
  
**So deaktivieren Sie den Posteingang mit Relevanz:**
  
In dem folgenden PowerShell-Beispiel wird der Posteingang mit Relevanz in Ihrer Organisation auf **Aus** festgelegt. Dadurch wird die Verfügbarkeit der Funktion für Ihre Benutzer jedoch nicht blockiert. Auf Wunsch können sie den Posteingang mit Relevanz trotzdem wieder auf jedem ihrer Clients aktivieren.  
  
1. [Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ihnen müssen Berechtigungen zugewiesen werden, bevor Sie diese Verfahren ausführen können. Informationen zu den benötigten Berechtigungen finden Sie unter dem Eintrag "Transportregeln" in [Berechtigungen für Empfängerrichtlinien und Compliance](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).

3. Führen Sie das Cmdlet **Get-OrganizationConfig** aus. 

    ```powershell
    Get-OrganizationConfig
    ```

4. Suchen Sie nach **FocusedInboxOn**, um die aktuelle Einstellung anzuzeigen: 

    ![Antwort von PowerShell zum Status des Posteingangs mit Relevanz.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Führen Sie das folgende Cmdlet aus, um "Posteingang mit Relevanz" zu deaktivieren.

    ```powershell
    Set-OrganizationConfig -FocusedInboxOn $false
    ```

6. Führen Sie das Cmdlet **Get-OrganizationConfig** erneut aus, und Sie sehen, dass "FocusedInboxOn" auf "$false" festgelegt ist, d. h. dass der Posteingang mit Relevanz deaktiviert ist. 

**So aktivieren Sie den Posteingang mit Relevanz:**
  
- Führen Sie in Schritt 5 oben das folgende Cmdlet aus, um "Posteingang mit Relevanz" zu aktivieren.

  ```powershell
  Set-OrganizationConfig -FocusedInboxOn $true
  ```
    
## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>Was wird Benutzern angezeigt, nachdem der Posteingang mit Relevanz aktiviert wurde? 

Der Posteingang mit Relevanz wird Benutzern erst nach dem Schließen und erneuten Starten von Outlook angezeigt. Beim Neustart von Outlook wird ein Tipp in der Outlook-Benutzeroberfläche angezeigt, der auf die Möglichkeit verweist, den neuen Posteingang mit Relevanz zu nutzen.
  
![Die Abbildung zeigt, wie der Posteingang mit Relevanz aussieht, wenn ein Benutzer Outlook im Web zum ersten Mal öffnet.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
Wenn Sie von "Clutter&quot; zum Posteingang mit Relevanz wechseln, können sie entscheiden, ob sie ihn aktivieren (&quot;Testen") oder das Feature schließen möchten. Wenn ein Benutzer über mehrere (unterstützte) Clients verfügt, kann er den Posteingang mit Relevanz für jeden Client einzeln aktivieren bzw. deaktivieren. Der Tipp sieht so aus:
  
![So sieht der Posteingang mit Relevanz aus, wenn er für Ihre Benutzer bereitgestellt wurde und Outlook erneut geöffnet wird.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
Wenn sich ein Benutzer zur Nutzung des Posteingangs mit Relevanz entscheidet, wird die Funktion "Clutter" automatisch deaktiviert. Der Ordner "Clutter" wird in einen Standardordner umgewandelt, sodass der Benutzer ihn umbenennen oder löschen kann.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>Aktivieren oder Deaktivieren des Posteingangs mit Relevanz für bestimmte Benutzer

In diesem Beispiel wird "Posteingang mit Relevanz" für Tim Matthews in der Organisation Contoso auf **Aus** festgelegt. Dadurch wird die Verfügbarkeit der Funktion für ihn jedoch nicht blockiert. Auf Wunsch kann er den Posteingang mit Relevanz trotzdem wieder auf jedem seiner Clients aktivieren. 
  
1. [Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ihnen müssen Berechtigungen zugewiesen werden, bevor Sie diese Verfahren ausführen können. Informationen zu den benötigten Berechtigungen finden Sie unter dem Thema "Transportregeln" in "Berechtigungen für Empfängerrichtlinien und Compliance".

3. Führen Sie das cmdlet **Get-FocusedInbox** aus, z. B.: 

    ```powershell
    Get-FocusedInbox -Identity <tim@contoso.com>
    ```

4. Suchen Sie nach "FocusedInboxOn", um die aktuelle Einstellung anzuzeigen:

    ![Antwort von PowerShell zum Status des Posteingangs mit Relevanz.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Führen Sie das folgende Cmdlet aus, um "Posteingang mit Relevanz" zu deaktivieren:

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
    ```

    Oder führen Sie das folgende Cmdlet aus, um "Posteingang mit Relevanz" zu aktivieren:

    ```powershell
    Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
    ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Verwenden der Benutzeroberfläche, um für alle Benutzer eine Transportregel zum Weiterleiten von E-Mail-Nachrichten an die Ansicht "Relevant" zu erstellen

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.

2. Navigieren Sie zu **Nachrichtenfluss** \> **Regeln**. Wählen Sie ![EAC Symbol hinzufügen](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) und wählen Sie dann **Neue Regel erstellen...** aus. 

3. Nachdem Sie die neue Regel erstellt haben, wählen Sie **Speichern**, um die Regel zu starten.

    Die folgende Abbildung zeigt ein Beispiel, bei dem alle Nachrichten vom „Lohnbuchhaltung“ an den Posteingang mit Relevanz zugestellt werden.

    ![focusedinbox payroll](../../media/focusedinbox-transport-rule.PNG)

    > [!NOTE]
    > Der Textwert der Kopfzeile in diesem Beispiel lautet **X-MS-Exchange-Organization-BypassFocusedInbox**.
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Verwenden von PowerShell, um für alle Benutzer eine Transportregel zum Weiterleiten von E-Mail-Nachrichten an die Ansicht "Relevant" zu erstellen

1. [Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](/powershell/exchange/connect-to-exchange-online-powershell).

2. Ihnen müssen Berechtigungen zugewiesen werden, bevor Sie diese Verfahren ausführen können. Informationen zu den benötigten Berechtigungen finden Sie unter dem Eintrag "Transportregeln" in [Berechtigungen für Empfängerrichtlinien und Compliance](/exchange/messaging-policy-and-compliance-permissions-exchange-2013-help).

3. Führen Sie den folgenden Befehl aus, um zuzulassen, dass alle Nachrichten beispielsweise von der Lohnbuchhaltung an den Posteingang mit Relevanz zugestellt werden.

    ```powershell
    New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
    ```

> [!IMPORTANT]
> In diesem Beispiel wird sowohl bei "X-MS-Exchange-Organization-BypassFocusedInbox" als auch bei "true" die Groß- und Kleinschreibung berücksichtigt.
> Der Posteingang mit Relevanz berücksichtigt den X-Header zur Umgehung von Clutter - wenn Sie diese Einstellung in "Clutter" verwenden, wird sie im Posteingang mit Relevanz verwendet. Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](/powershell/module/exchange/new-transportrule).

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Sie können die Kopfzeilen der E-Mail-Nachrichten überprüfen, um zu sehen, ob die E-Mail-Nachrichten basierend auf der Transportregelumleitung für den Posteingang mit Relevanz im Postfach ankommen. Wählen Sie in einem Postfach in Ihrer Organisation eine E-Mail-Nachricht aus, auf die die Transportregel "Posteingang mit Relevanz" angewendet wird. Schauen Sie sich die Kopfzeilen der Nachricht an. Hier sollte **X-MS-Exchange-Organization-BypassFocusedInbox: true** angezeigt werden. Dies bedeutet, dass die Umgehung funktioniert. Informationen zum Anzeigen der Kopfzeileninformationen finden Sie unter [Anzeigen der Internetkopfzeileninformationen einer E-Mail-Nachricht](https://go.microsoft.com/fwlink/p/?LinkId=822530).

### <a name="what-will-the-user-see"></a>Was wird der Benutzer sehen?

Wenn eine Transportregel vorhanden ist, wird eine Benachrichtigung für die Überschreibung angezeigt. Bei Outlook im Web wird die Option "Immer in Sonstige verschieben" deaktiviert und eine QuickInfo angezeigt. Outlook-Clients auf dem Desktop erlauben die Auswahl von "Immer in Sonstige verschieben" und zeigen einen Dialog an.

## <a name="turn-onoff-clutter"></a>Aktivieren/Deaktivieren von "Clutter"

Wir haben Berichte erhalten, dass "Clutter" bei einigen Benutzern plötzlich nicht mehr funktionierte. Wenn das geschieht, können Sie "Clutter" für bestimmte Benutzer erneut aktivieren. Weitere Informationen finden Sie unter [Konfigurieren von "Clutter" für Ihre Organisation](../email/configure-clutter.md).

## <a name="faq-for-focused-inbox"></a>Häufig gestellte Fragen (FAQ) zum Posteingang mit Relevanz

Dies sind Antworten auf häufig gestellte Fragen zum Posteingang mit Relevanz.

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>Kann ich steuern, wie "Posteingang mit Relevanz" in meiner Organisation implementiert wird?

Ja. Sie können den Posteingang mit Relevanz für die gesamte Organisation aktivieren oder deaktivieren, oder Sie können das Feature für bestimmte Benutzer aktivieren oder deaktivieren. Siehe weiter oben.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>Steht die Funktion "Posteingang mit Relevanz" NUR auf Office 2016-Clients zur Verfügung?

Ja, sie betrifft nur Benutzer mit Office 2016. Die Funktion wird nicht rückwirkend in Outlook 2013 und früheren Versionen implementiert.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>Wie lange dauert es, bis Änderungen am Posteingang mit Relevanz in Outlook wirksam werden?

Nachdem Sie den Posteingang mit Relevanz aktiviert oder deaktiviert haben, werden die Einstellungen wirksam, sobald Ihre Benutzer Outlook schließen und erneut starten.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>Was geschieht mit "Clutter", nachdem ich den Posteingang mit Relevanz aktiviert habe?

Nach dem Wechsel werden keine weniger handlungsrelevante E-Mails mehr im Ordner "Clutter" abgelegt. Stattdessen werden die E-Mails auf die Registerkarten "Relevant" und "Sonstige" im Posteingang aufgeteilt. Der gleiche Algorithmus, mit dem Elemente in den Ordner "Clutter" verschoben wurden, bildet nun die Grundlage für den Posteingang mit Relevanz. Das bedeutet, dass alle E-Mails, für die das Verschieben in "Clutter" festgelegt wurde, jetzt in "Sonstige" verschoben werden. Alle Nachrichten, die sich bereits im Ordner "Clutter" befinden, bleiben dort, bis sie gelöscht oder verschoben werden.
  
Lesen Sie dazu diesen Beitrag von [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365) (So ersetzt der Posteingang mit Relevanz den Ordner "Clutter" in Office 365).
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>Kann „Clutter“ für Benutzer aktiviert bleiben? Was empfiehlt Microsoft hinsichtlich der Verwendung von Clutter gegenüber dem Posteingang mit Relevanz?

Ja, Sie können "Clutter" für Benutzer aktiviert lassen und den Posteingang mit Relevanz deaktivieren. Allerdings soll "Clutter" im Lauf der Zeit vollständig durch den Posteingang mit Relevanz ersetzt werden. Daher empfiehlt Microsoft, jetzt auf den Posteingang mit Relevanz umzustellen. Weitere Informationen zur Verwendung von "Clutter" mit Exchange Online finden Sie in diesem Blogbeitrag: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448) (Aktualisieren des Posteingangs mit Relevanz und unsere Pläne für "Clutter").
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>Sollte "Clutter" für Endbenutzer deaktiviert werden, wenn wir die Umstellung aller Benutzer auf den Posteingang mit Relevanz planen?

Nein. "Clutter" kann für ein Postfach explizit durch Ausführen des Cmdlets "Set-Clutter" deaktiviert werden. Wenn dies erfolgt, werden dem Postfachbesitzer Nachrichten, die zuvor in den Ordner "Clutter" umgeleitet wurden, wieder im Posteingang angezeigt, sodass er diese Nachrichten verarbeiten muss, bis für seinen Client das Upgrade auf eine Version erfolgt, die den Posteingang mit Relevanz unterstützt. Es empfiehlt sich daher, den Ordner "Clutter" erst zu deaktivieren, wenn Clients mit Upgrade zur Verfügung stehen.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>Warum gibt es zwei unterschiedliche Cmdlets für die Verwaltung von "Posteingang mit Relevanz"?

In Verbindung mit "Posteingang mit Relevanz" gibt es zwei Zustände.
  
- **Organisationsebene**: Status "Posteingang mit Relevanz" und einen zugehörigen Zeitstempel mit der letzten Aktualisierung.

- **Postfachebene**: Status "Posteingang mit Relevanz" und einen zugehörigen Zeitstempel mit der letzten Aktualisierung. 

### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>Wie kann Outlook entscheiden, ob die Benutzeroberfläche "Posteingang mit Relevanz" mit diesen beiden Zuständen angezeigt werden soll?

Outlook entscheidet basierend auf dem Cmdlet mit dem neuesten Zeitstempel, welche Benutzeroberfläche angezeigt wird. Standardmäßig sind beide Zeitstempel "null", und in diesem Fall ist die Funktion aktiviert.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>Warum gibt das Cmdlet Get-FocusedInbox "true" zurück, wenn ich "Posteingang mit Relevanz" in meiner Organisation deaktiviert habe?

Es gibt zwei Cmdlets für die Steuerung von "Posteingang mit Relevanz". Wenn Sie Get-FocusedInbox für ein Postfach ausführen, wird der Zustand der Funktion auf Postfachebene zurückgegeben. Die Benutzeroberfläche in Outlook wird basierend darauf ausgewählt, welcher Zustand des jeweiligen Cmdlets zuletzt geändert wurde.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>Kann ich ein Skript ausführen, um zu sehen, wer den Posteingang mit Relevanz aktiviert hat?

Nein, und dies ist beabsichtigt. Die Aktivierung des Posteingangs mit Relevanz ist eine clientseitige Einstellung. Deshalb kann Sie das Cmdlet lediglich informieren, wenn das Postfach des Benutzers für die Client-Oberfläche berechtigt ist. Es ist möglich, dass es in einigen Clients gleichzeitig aktiviert und in anderen deaktiviert ist, z. B. in der Outlook-App und Outlook Mobile aktiviert, doch in Outlook im Web deaktiviert.

## <a name="related-content"></a>Verwandte Inhalte

[Konfigurieren von „Clutter“ für Ihre Organisation](../email/configure-clutter.md) (Artikel)\
[Konfigurieren der Einstellungen für das freigegebene Postfach](../email/configure-a-shared-mailbox.md) (Artikel)\
[Erstellen von Signaturen und Verzichtserklärungen](create-signatures-and-disclaimers.md) (Video)
