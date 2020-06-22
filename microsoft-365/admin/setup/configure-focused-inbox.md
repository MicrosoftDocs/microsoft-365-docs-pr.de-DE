---
title: Konfigurieren des Posteingangs mit Relevanz für jeden Benutzer in Ihrer Organisation
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
description: 'Erfahren Sie, wie Sie den Posteingang mit Relevanz mit dem Posteingang für alle oder bestimmte Benutzer Ihrer Organisation konfigurieren. '
ms.openlocfilehash: f56e85e79fcf17cde89ec3d6094ca757ccf0cc68
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44779929"
---
# <a name="configure-focused-inbox-for-everyone-in-your-organization"></a>Konfigurieren des Posteingangs mit Relevanz für jeden Benutzer in Ihrer Organisation

  Wenn Sie dafür zuständig sind, die Funktion der E-Mail für JEDEN in einem Unternehmen zu konfigurieren, dann ist das genau der Artikel für Sie! Es wird erläutert, wie Sie die E-Mail-Funktion für Ihr Unternehmen anpassen oder deaktivieren und beantwortet [Häufig gestellte Fragen](#faq-for-focused-inbox).  <br/> Wenn Sie den Posteingang mit Relevanz für sich selbst deaktivieren möchten, lesen Sie [Deaktivieren des Posteingangs mit Relevanz](https://support.microsoft.com/office/f714d94d-9e63-4217-9ccb-6cb2986aa1b2).  
   
If you want to be sure that your users receive business-specific email messages, for example, from HR or payroll, you can configure Focused Inbox so these messages reach the Focused view. You can also control whether users in your organization see the Focused Inbox in their mailbox.
  
## <a name="turn-focused-inbox-on-or-off-in-your-organization"></a>Aktivieren oder Deaktivieren von "Posteingang mit Relevanz" in Ihrer Organisation

Sie verwenden PowerShell, um den Posteingang mit Relevanz für alle Benutzer in Ihrer Organisation zu aktivieren oder deaktivieren. Möchten Sie diesen Vorgang im Microsoft 365 Admin Center ausführen? Teilen Sie dies unserem Entwicklungsteam mit. **[Stimmen Sie hier ab!](https://go.microsoft.com/fwlink/?linkid=862489)**
  
 **So deaktivieren Sie den Posteingang mit Relevanz:**
  
The following PowerShell example turns Focused Inbox **Off** in your organization. However, it doesn't block the availability of the feature for your users. If they want, they can still re-enable Focused Inbox again on each of their clients. 
  
1. [Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).
    
3. Führen Sie das Cmdlet **Get-OrganizationConfig** aus. 
    
 ``` PowerShell
Get-OrganizationConfig
 ```

4. Suchen Sie nach **FocusedInboxOn**, um die aktuelle Einstellung anzuzeigen: 
    
    ![Antwort von PowerShell zum Status des Posteingangs mit Relevanz.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Führen Sie das folgende Cmdlet aus, um "Posteingang mit Relevanz" zu deaktivieren.
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $false
 ```

6. Führen Sie das Cmdlet **Get-OrganizationConfig** erneut aus, und Sie sehen, dass "FocusedInboxOn" auf "$false" festgelegt ist, d. h. dass der Posteingang mit Relevanz deaktiviert ist. 
    
 **So aktivieren Sie den Posteingang mit Relevanz:**
  
- Führen Sie in Schritt 5 oben das folgende Cmdlet aus, um "Posteingang mit Relevanz" zu aktivieren.
    
 ``` PowerShell
 Set-OrganizationConfig -FocusedInboxOn $true
 ```

## <a name="what-do-users-see-after-i-turn-on-focused-inbox"></a>Was wird Benutzern angezeigt, nachdem der Posteingang mit Relevanz aktiviert wurde? 

Your users will see the Focused view only after they close and restart Outlook. When they restart Outlook, they'll see a Tip in the Outlook user interface giving them to the option to use the new Focused Inbox.
  
![Die Abbildung zeigt, wie der Posteingang mit Relevanz aussieht, wenn ein Benutzer Outlook im Web zum ersten Mal öffnet.](../../media/f6ef79e7-0f4c-4a23-b6f0-7c15d927b5f0.png)
  
If you're switching from Clutter to Focused Inbox, they can decide to enable it ("Try it") or dismiss the feature. If the user has multiple (supported) clients, they can enable/disable Focused Inbox individually on each one. The tip looks like this:
  
![So sieht der Posteingang mit Relevanz aus, wenn er für Ihre Benutzer bereitgestellt wurde und Outlook erneut geöffnet wird.](../../media/c034f969-d650-4333-88f1-dd10ade0a94c.png)
  
When a user decides to start using Focused Inbox, Clutter gets disabled automatically. The Clutter folder gets converted into a standard folder, that allows the user to rename or delete it.
  
## <a name="turn-focused-inbox-on-or-off-for-specific-users"></a>Aktivieren oder Deaktivieren des Posteingangs mit Relevanz für bestimmte Benutzer

This example turns Focused Inbox **Off** for Tim Matthews in the Contoso organization. However, it doesn't block the availability of the feature to him. If his wants, he can still re-enable Focused Inbox again on each of his clients. 
  
1. [Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in the Messaging policy and compliance permissions topic.
    
3. Führen Sie das cmdlet **Get-FocusedInbox** aus, z. B.: 
    
 ``` PowerShell
 Get-FocusedInbox -Identity <tim@contoso.com>
 ```

4. Suchen Sie nach "FocusedInboxOn", um die aktuelle Einstellung anzuzeigen:
    
    ![Antwort von PowerShell zum Status des Posteingangs mit Relevanz.](../../media/419d8caa-89b9-45c5-91d9-8c023297456e.png)
  
5. Führen Sie das folgende Cmdlet aus, um "Posteingang mit Relevanz" zu deaktivieren:
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $false
 ```

6. Oder führen Sie das folgende Cmdlet aus, um "Posteingang mit Relevanz" zu aktivieren:
    
 ``` PowerShell
 Set-FocusedInbox -Identity <tim@contoso.com> -FocusedInboxOn $true
 ```

## <a name="use-the-ui-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Verwenden der Benutzeroberfläche, um für alle Benutzer eine Transportregel zum Weiterleiten von E-Mail-Nachrichten an die Ansicht "Relevant" zu erstellen

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.
    
2. Navigieren Sie zu **Nachrichtenfluss** \> **Regeln**. Wählen Sie ![EAC Symbol hinzufügen](../../media/795e5bdd-48bb-433f-8e07-3c7a19f8eca2.gif) und wählen Sie dann **Neue Regel erstellen...** aus. 
    
3. Nachdem Sie die neue Regel erstellt haben, wählen Sie **Speichern**, um die Regel zu starten. 
    
    Die folgende Abbildung zeigt ein Beispiel, bei dem alle Nachrichten vom „Lohnbuchhaltung“ an den Posteingang mit Relevanz zugestellt werden.
    
    ![focusedinbox payroll](../../media/focusedinbox-transport-rule.PNG)
  
## <a name="use-powershell-to-create-a-transport-rule-to-direct-email-messages-to-the-focused-view-for-all-your-users"></a>Verwenden von PowerShell, um für alle Benutzer eine Transportregel zum Weiterleiten von E-Mail-Nachrichten an die Ansicht "Relevant" zu erstellen

1. [Stellen Sie eine Verbindung mit Exchange Online mithilfe der Remote-PowerShell her](https://go.microsoft.com/fwlink/p/?LinkId=396554).
    
2. You need to be assigned permissions before you can perform this procedure or procedures. To see what permissions you need, see the "Transport rules" entry in [Messaging policy and compliance permissions](https://go.microsoft.com/fwlink/p/?LinkId=829796).

3. Führen Sie den folgenden Befehl aus, um zuzulassen, dass alle Nachrichten beispielsweise von der Lohnbuchhaltung an den Posteingang mit Relevanz zugestellt werden.
    
 ``` PowerShell
 New-TransportRule -Name <name_of_the_rule> -From "Payroll Department" -SetHeaderName "X-MS-Exchange-Organization-BypassFocusedInbox" -SetHeaderValue "true"
 ```

> [!IMPORTANT]
> In diesem Beispiel wird sowohl bei "X-MS-Exchange-Organization-BypassFocusedInbox" als auch bei "true" die Groß- und Kleinschreibung berücksichtigt.
> Der Posteingang mit Relevanz berücksichtigt den X-Header zur Umgehung von Clutter - wenn Sie diese Einstellung in "Clutter" verwenden, wird sie im Posteingang mit Relevanz verwendet. Detaillierte Informationen zur Syntax und den Parametern finden Sie unter [New-TransportRule](https://go.microsoft.com/fwlink/p/?LinkId=830194).

### <a name="how-do-you-know-this-worked"></a>Woher wissen Sie, dass dieses Verfahren erfolgreich war?

Sie können die Kopfzeilen der E-Mail-Nachrichten überprüfen, um zu sehen, ob die E-Mail-Nachrichten basierend auf der Transportregelumleitung für den Posteingang mit Relevanz im Postfach ankommen. Wählen Sie in einem Postfach in Ihrer Organisation eine E-Mail-Nachricht aus, auf die die Transportregel "Posteingang mit Relevanz" angewendet wird. Schauen Sie sich die Kopfzeilen der Nachricht an. Hier sollte **X-MS-Exchange-Organization-BypassFocusedInbox: true** angezeigt werden. Dies bedeutet, dass die Umgehung funktioniert. Informationen zum Anzeigen der Kopfzeileninformationen finden Sie unter [Anzeigen der Internetkopfzeileninformationen einer E-Mail-Nachricht](https://go.microsoft.com/fwlink/p/?LinkId=822530). 
 
## <a name="turn-onoff-clutter"></a>Aktivieren/Deaktivieren von "Clutter"
 
We've received reports that Clutter suddenly stopped working for some users. If this happens, you can enable it again for specific users. See [Configure Clutter for your organization](../email/configure-clutter.md).
 
## <a name="faq-for-focused-inbox"></a>Häufig gestellte Fragen (FAQ) zum Posteingang mit Relevanz

Dies sind Antworten auf häufig gestellte Fragen zum Posteingang mit Relevanz. 

### <a name="can-i-control-how-i-roll-out-focused-inbox-in-my-organization"></a>Kann ich steuern, wie "Posteingang mit Relevanz" in meiner Organisation implementiert wird?

Yes. You can turn Focused Inbox on or off for your entire organization, or you can turn it on or off for specified users. See above.
  
### <a name="is-the-focused-inbox-feature-only-available-for-office-2016-clients"></a>Steht die Funktion "Posteingang mit Relevanz" NUR auf Office 2016-Clients zur Verfügung?

Ja, sie betrifft nur Benutzer mit Office 2016. Die Funktion wird nicht rückwirkend in Outlook 2013 und früheren Versionen implementiert.
  
### <a name="how-long-does-it-take-for-focused-inbox-changes-to-take-place-in-outlook"></a>Wie lange dauert es, bis Änderungen am Posteingang mit Relevanz in Outlook wirksam werden?

Nachdem Sie den Posteingang mit Relevanz aktiviert oder deaktiviert haben, werden die Einstellungen wirksam, sobald Ihre Benutzer Outlook schließen und erneut starten.
  
### <a name="what-happens-to-clutter-once-i-turn-on-focused-inbox"></a>Was geschieht mit "Clutter", nachdem ich den Posteingang mit Relevanz aktiviert habe?

After switching, you'll no longer receive less actionable email in the Clutter folder. Instead, email will be split between the Focused and Other tabs in your inbox. The same algorithm that moved items to the Clutter folder now powers Focused Inbox, meaning that any emails that were set to move to Clutter will now be moved to Other. Any messages already in your Clutter folder will remain there until you decide to delete or move them.
  
Lesen Sie dazu diesen Beitrag von [Tony Redmond](https://www.petri.com/author/tony-redmond), Microsoft MVP: [How the Focused Inbox Replaces Clutter Inside Office 365](https://www.petri.com/focused-inbox-office-365) (So ersetzt der Posteingang mit Relevanz den Ordner "Clutter" in Office 365).
  
### <a name="can-i-keep-users-on-clutter-what-is-microsofts-recommendation-when-it-comes-to-using-clutter-vs-focused-inbox"></a>Kann "Clutter" für Benutzer aktiviert bleiben? Was empfiehlt Microsoft hinsichtlich der Verwendung von Clutter gegenüber dem Posteingang mit Relevanz?

Yes, you can keep users on Clutter and disable Focused Inbox, however, eventually Clutter will be fully replaced with Focused Inbox so Microsoft's recommends moving to Focused Inbox now. To learn more about when you use Clutter with Exchange Online, see this blog post: [Update on Focused Inbox and our plans for Clutter](https://techcommunity.microsoft.com/t5/Outlook-Blog/Update-on-Focused-Inbox-and-our-plans-for-Clutter/ba-p/136448).
  
### <a name="should-i-disable-clutter-for-my-end-users-if-we-are-going-to-move-everyone-to-focused-inbox"></a>Sollte "Clutter" für Endbenutzer deaktiviert werden, wenn wir die Umstellung aller Benutzer auf den Posteingang mit Relevanz planen?

No. It's possible to disable Clutter for a mailbox explicitly by running the Set-Clutter cmdlet. However, if you do this, the mailbox owner will see messages that were previously redirected to the Clutter folder remain in the Inbox and they'll have to process those messages until their client is upgraded to a version that supports the Focused Inbox. It's therefore best not to disable Clutter until the upgraded clients are available.
  
### <a name="why-are-there-two-different-cmdlets-for-managing-focused-inbox"></a>Warum gibt es zwei unterschiedliche Cmdlets für die Verwaltung von "Posteingang mit Relevanz"?

In Verbindung mit "Posteingang mit Relevanz" gibt es zwei Zustände.
  
- **Organisationsebene**: Status "Posteingang mit Relevanz" und einen zugehörigen Zeitstempel mit der letzten Aktualisierung. 
    
- **Postfachebene**: Status "Posteingang mit Relevanz" und einen zugehörigen Zeitstempel mit der letzten Aktualisierung. 
    
### <a name="how-does-outlook-decide-to-show-the-focused-inbox-experience-with-these-two-states"></a>Wie kann Outlook entscheiden, ob die Benutzeroberfläche "Posteingang mit Relevanz" mit diesen beiden Zuständen angezeigt werden soll?

Outlook decides to show the experience by choosing which cmdlet has the latest time stamp. By default, both time stamps are "null" and in this case, the feature is enabled.
  
### <a name="why-does-the-get-focusedinbox-cmdlet-return-true-when-ive-turned-focused-inbox-off-in-my-organization"></a>Warum gibt das Cmdlet Get-FocusedInbox "true" zurück, wenn ich "Posteingang mit Relevanz" in meiner Organisation deaktiviert habe?

There are two cmdlets for controlling Focused Inbox. When you run Get-FocusedInbox for a mailbox, it returns the mailbox level state of the feature. The experience in Outlook is chosen based on which cmdlet state was last modified.
  
### <a name="can-i-run-a-script-to-see-who-has-turned-on-focused-inbox"></a>Kann ich ein Skript ausführen, um zu sehen, wer den Posteingang mit Relevanz aktiviert hat?

No, and this is by design. Focused Inbox enablement is a client side setting, so all the cmdlet can do is tell you if the user's mailbox is eligible for the client experience. It is possible for it to be simultaneously enabled in some clients and disabled in others, for example, enabled in Outlook app and Outlook Mobile but disabled in Outlook on the web.
