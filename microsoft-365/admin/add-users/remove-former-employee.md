---
title: Entfernen eines ehemaligen Mitarbeiters
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 44d96212-4d90-4027-9aa9-a95eddb367d1
description: 'Führen Sie diese Prüfliste aus, um einen Mitarbeiter aus Microsoft 365 zu entfernen und Daten zu sichern. '
ms.openlocfilehash: adf5c683828b30a978199145fa2c54f17d1b6b37
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44780577"
---
# <a name="remove-a-former-employee"></a>Entfernen eines ehemaligen Mitarbeiters

::: moniker range="o365-21vianet"

> [!NOTE]
> Das Admin Center wird geändert. Wenn Ihre Erfahrung nicht den hier aufgeführten Details entspricht, lesen Sie [über das neue Microsoft 365 Admin Center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).

::: moniker-end
  
## <a name="sign-out-now"></a>Sofortiges Abmelden

::: moniker range="o365-worldwide"

Sehen Sie sich ein kurzes Video zum Entfernen eines Mitarbeiters an. <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

Wenn Sie dieses Video hilfreich fanden, sehen Sie sich bitte die [komplette Schulungsserie für kleine Unternehmen und jene, die neu bei Microsoft 365 sind](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816), an.

So entfernen Sie einen Mitarbeiter:

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Aktivieren Sie das Kontrollkästchen neben dem Namen des Benutzers, und wählen Sie dann **Kennwort zurücksetzen**aus.

3. Geben Sie ein neues Kennwort ein, und wählen Sie dann **Zurücksetzen**aus. (Senden Sie es nicht an Sie.)
    
4. Wählen Sie den Namen des Benutzers aus, um den Eigenschaftenbereich zu öffnen, und wählen Sie auf der Registerkarte **OneDrive** die Option **Abmelden initiieren**aus.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Benutzer aus, und wählen Sie dann **Kennwort zurücksetzen**aus.

3. Geben Sie ein neues Kennwort ein, und wählen Sie dann **Zurücksetzen**aus. (Senden Sie es nicht an Sie.)

4. Wählen Sie den Benutzer erneut aus, erweitern Sie **OneDrive Einstellungen**, und wählen Sie dann **initiieren** neben **Abmelden aus**.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Benutzer aus, und wählen Sie dann **Kennwort zurücksetzen**aus.

3. Geben Sie ein neues Kennwort ein, und wählen Sie dann **Zurücksetzen**aus. (Senden Sie es nicht an Sie.)

4. Wählen Sie den Benutzer erneut aus, erweitern Sie **OneDrive Einstellungen**, und wählen Sie dann **initiieren** neben **Abmelden aus**.

::: moniker-end

    
Innerhalb einer Stunde-oder nachdem Sie die aktuelle Seite von Microsoft 365 verlassen haben-werden Sie aufgefordert, sich erneut anzumelden. (Ein Zugriffstoken ist gut für eine Stunde, sodass die Zeitachse davon abhängt, wie viel Zeit auf dem Token bleibt und ob Sie aus Ihrer aktuellen Webseite navigieren.)
  
 **Einschränkung**: Wenn sich der Benutzer in Outlook im Internet befindet und nur in seinem Postfach klickt, wird er möglicherweise nicht sofort gestartet. Sobald Sie eine andere Kachel wie OneDrive auswählen oder Ihren Browser aktualisieren, wird die Abmeldung initiiert. 
  
Wenn Sie PowerShell verwenden möchten, um einen Benutzer sofort abzumelden, lesen Sie den Artikel über das Cmdlet [Revoke-AzureADUserAllRefreshToken](https://go.microsoft.com/fwlink/?linkid=841345). 
  
Weitere Informationen dazu, wie lange es dauert, für jemand die E-Mail-Nutzung zu beenden, finden Sie unter [Wichtige Informationen zum Beenden der E-Mail-Sitzung eines Mitarbeiters](#what-you-need-to-know-about-terminating-an-employees-email-session).
  
## <a name="overview-of-all-the-steps-to-remove-an-employee-and-secure-data"></a>Übersicht über alle Schritte zum Entfernen eines Mitarbeiters und Sichern der Daten
<a name="bkmk_now"> </a>

Eine Frage, die wir häufig erhalten, lautet: "Was muss ich tun, um Daten zu schützen, wenn ein Mitarbeiter die Organisation verlässt?" In diesem Artikel wird erläutert, wie Sie den Zugriff auf Microsoft 365 und die erforderlichen Schritte zum Sichern Ihrer Daten blockieren können.
  
> [!NOTE]
> Wenn Sie ein globaler Administrator sind, können Sie den Mitarbeiter löschen, seine e-Mail weiterleiten und auswählen, was mit dem OneDrive-Inhalt zu tun ist, indem Sie die neue geführte Benutzeroberfläche verwenden. Weitere Informationen finden Sie unter [globaler Administrator: Löschen eines Benutzers](remove-former-employee.md). Es wird jedoch empfohlen, alle hier aufgelisteten zusätzlichen Schritte abzuschließen, um sicherzustellen, dass der Mitarbeiter keinen Zugriff auf die Daten Ihres Unternehmens hat. 
  
Here's a quick overview. Each step is explained in detail in this article.
  
|||
|:-----|:-----|
|**Schritt** <br/> |**Zweck** <br/> |
|1. [Speichern der Inhalte des Postfachs eines ehemaligen Mitarbeiters](#save-the-contents-of-a-former-employees-mailbox) <br/> |Dies ist für die Person, die die Arbeit des Mitarbeiters übernimmt, oder im Falle von Rechtsstreitigkeiten nützlich.  <br/> |
|2. [Weiterleiten der E-Mails eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter oder Konvertieren des Benutzerpostfachs in ein freigegebenes Postfach](#forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox) <br/> |This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.  <br/> |
|3. [Zurücksetzen und Blockieren des mobilen Geräts eines ehemaligen Mitarbeiters](#wipe-and-block-a-former-employees-mobile-device) <br/> |Entfernt die Geschäftsdaten vom Smartphone oder Tablet.  <br/> |
|4. [Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf Microsoft 365-Daten](#block-a-former-employees-access-to-microsoft-365-data)<br/> |Dadurch wird verhindert, dass die Person auf Ihr altes Microsoft 365-Postfach und Ihre Daten zugreift.  <br/><br/> **Tipp**: Wenn Sie den Zugriff eines Benutzers blockieren, bezahlen Sie weiterhin für Ihre Lizenz. Sie müssen die Lizenz in Ihrem Abonnement löschen, um die Bezahlung dafür zu beenden (Schritt 5).           |
|5. [Verschieben des OneDrive-Inhalts eines Mitarbeiters](get-access-to-and-back-up-a-former-user-s-data.md) <br/> |Wenn Sie nur die Lizenz eines Benutzers entfernen, aber das Konto nicht löschen, können Sie auch nach mehr als 30 Tagen auf den OneDrive-Inhalt des Benutzers zugreifen.  <br/><br/> Before you delete the account, you should move the content of their OneDrive to another location that's easy for you to access. After you delete an employee's account, the content in their OneDrive is retained for **30** days. During that 30 days, however, you can restore the user's account, and gain access to their OneDrive content. If you restore the user's account, the OneDrive content will remain accessible to you even after 30 days.  <br/> |
|5a. What if the person used their personal computer to access OneDrive and SharePoint?  <br/> |Wenn er anstelle eines vom Unternehmen bereitgestellten Computers seinen privaten PC zum Herunterladen von Dateien aus OneDrive und SharePoint verwendet hat, haben Sie keine Möglichkeit, die dort gespeicherten Dateien zu bereinigen.  <br/><br/> Er hat weiterhin Zugriff auf alle Dateien, die mit seinem Computer synchronisiert wurden.  <br/> |
|6. [Entfernen und löschen Sie die Microsoft 365-Lizenz von einem ehemaligen Mitarbeiter](#remove-and-delete-the-microsoft-365-license-from-a-former-employee)<br/> |When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person.  <br/><br/> When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  <br/> |
|7. [Löschen des Benutzerkontos eines ehemaligen Mitarbeiters](#delete-a-former-employees-user-account)<br/> |Dadurch wird das Konto aus Ihrem Admin Center entfernt. So behalten Sie die Übersicht.  <br/> |
   
## <a name="save-the-contents-of-a-former-employees-mailbox"></a>Speichern der Inhalte des Postfachs eines ehemaligen Mitarbeiters
<a name="bkmk_preserve"> </a>

Es gibt zwei Möglichkeiten, wie Sie die Inhalte des Postfachs eines ehemaligen Mitarbeiters speichern können:
  
1. Add the former employee's email address to your version of Outlook 2013 or 2016, and then export the data to a .pst file. You can import the data to another email account as needed. To learn how to do this, see [Get access to and back up a former user's data](get-access-to-and-back-up-a-former-user-s-data.md).
    
    ODER
    
2. Place a Litigation Hold or In-Place Hold on the mailbox before the deleting the user account. This is much more complicated than the first option but worth doing if: your Enterprise plan includes archiving and legal hold, litigation is a possibility, and you have a technically strong IT department.
    
    Nachdem Sie das Postfach in ein "inaktives Postfach" umgewandelt haben, können Administratoren, Compliance Officer oder Datensatzmanager In-Situ-eDiscovery-Tools in Exchange Online verwenden, um auf die Inhalte zuzugreifen und sie zu durchsuchen.
    
    Inaktive Postfächer können keine E-Mails empfangen und werden im freigegebenen Adressbuch Ihrer Organisation oder in anderen Listen nicht angezeigt.
    
    Informationen zum Aufbewahren eines Postfachs finden Sie unter [Manage inactive Mailboxes in Exchange Online](https://docs.microsoft.com/microsoft-365/compliance/create-and-manage-inactive-mailboxes).
    
## <a name="forward-a-former-employees-email-to-another-employee-or-convert-to-a-shared-mailbox"></a>Weiterleiten der E-Mails eines ehemaligen Mitarbeiters an einen anderen Mitarbeiter oder Konvertieren des Benutzerpostfachs in ein freigegebenes Postfach
<a name="bkmk_forward"> </a>

In diesem Schritt weisen Sie die E-Mail-Adresse des ehemaligen Mitarbeiters einem anderen Mitarbeiter zu, oder Sie [konvertieren das Postfach des Benutzers in ein freigegebenes Postfach](../email/convert-user-mailbox-to-shared-mailbox.md), das Sie erstellt haben. 
  
- Creating a shared mailbox is the less expensive way to go because you won't have to pay for a license **as long as the mailbox is smaller than 50GB**. Over 50GB and you'll need to assign a license to it. 
    
- If you convert the mailbox to a shared mailbox, all the old email will be available, too. This can take up a lot of space.
    
- Wenn Sie die E-Mail-Weiterleitung eingerichtet haben, werden nur  *neue*  an den ehemaligen Mitarbeiter gesendeten E-Mails jetzt an den aktuellen Mitarbeiter gesendet. 
    
- Bei der E-Mail-Weiterleitung muss das Konto des ehemaligen Mitarbeiters über eine Lizenz verfügen.
    
 > [!IMPORTANT] 
 > Wenn Sie e-Mail-Weiterleitung oder ein freigegebenes Postfach einrichten, löschen Sie am Ende nicht das Konto des ehemaligen Mitarbeiters. Es muss nämlich vorhanden sein, damit die E-Mail-Weiterleitung oder das freigegebene Postfach funktionieren. 

::: moniker range="o365-worldwide"  

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Namen des Mitarbeiters aus, den Sie blockieren möchten, und wählen Sie dann die Registerkarte **e-Mail** aus.

3. Wählen Sie unter **e-Mail-weiter**Leitung die Option **e-Mail Weiterleitung verwalten**aus.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Wählen Sie **Speichern**. 
    
6. Denken Sie daran, dass das Konto des ehemaligen Mitarbeiters nicht gelöscht werden sollte.
 
::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Mitarbeiter aus, den Sie blockieren möchten, und erweitern Sie **e-Mail-Einstellungen**.

3. Wählen Sie neben **e-Mail-Weiterleitung**die Option **Bearbeiten**aus.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Wählen Sie **Speichern**. 
    
6. Denken Sie daran, dass das Konto des ehemaligen Mitarbeiters nicht gelöscht werden sollte.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Mitarbeiter aus, den Sie blockieren möchten, und erweitern Sie **e-Mail-Einstellungen**.

3. Wählen Sie neben **e-Mail-Weiterleitung**die Option **Bearbeiten**aus.

4. Turn on **Forward all email sent to this mailbox**. In the **Forwarding address** box, type the email address of the current employee (or shared mailbox) who's going to get the email. 
  
5. Wählen Sie **Speichern**. 
    
6. Denken Sie daran, dass das Konto des ehemaligen Mitarbeiters nicht gelöscht werden sollte.

::: moniker-end


    
## <a name="wipe-and-block-a-former-employees-mobile-device"></a>Zurücksetzen und Blockieren des mobilen Geräts eines ehemaligen Mitarbeiters
<a name="bkmk_mobile"> </a>

Wenn der ehemalige Mitarbeiter ein Firmenhandy genutzt hat, können Sie dieses Gerät über das Exchange Admin Center zurücksetzen und blockieren, damit alle Unternehmensdaten auf dem Gerät entfernt werden und dieses Gerät keine Verbindung mehr mit Office 365 herstellen kann.
  

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.

3. Navigieren Sie im Exchange Admin Center zu **Empfänger** \> **Postfächer**. 
    
4. Wählen Sie den Benutzer aus, und wählen Sie unter **Mobile Geräte**die Option **Details anzeigen**aus. 
    
5. Wählen Sie auf der Seite **Details für mobile Geräte** unter **Mobile Geräte**das Mobile Gerät aus, wählen Sie Daten Zurücksetzungs Gerät **wischen**aus ![ ](../../media/1c113a36-53cb-4974-884f-3ecd9535506e.png) , und wählen Sie dann **blockieren**aus. 
    
6. Wählen Sie **Speichern**. 
    
    **Tip**: Be sure you remove or disable the user from your on-premises Blackberry Enterprise Service. You should also disable any Blackberry devices for the user. Refer to the Blackberry Business Cloud Services Administration Guide if you need specific steps on how to disable the user. 
    
## <a name="block-a-former-employees-access-to-microsoft-365-data"></a>Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf Microsoft 365-Daten
<a name="bkmk_block"> </a>

 > [!IMPORTANT] 
 > Das Blockieren eines Kontos kann bis zu 24 Stunden dauern, bis es wirksam wird. Wenn Sie den Anmeldezugriff eines Benutzers sofort verhindern müssen, sollten Sie [Ihr Kennwort zurücksetzen](reset-passwords.md) und dann ein einmaliges Ereignis initiieren, das Sie von Microsoft 365-Sitzungen auf allen Geräten signieren wird. Weitere Informationen finden Sie unter [Sofortiges Abmelden](#sign-out-now).
 

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Namen des Mitarbeiters aus, den Sie blockieren möchten, und wählen Sie unter dem Namen des Benutzers das Symbol für **diesen Benutzer blockieren**aus.

3. Wählen Sie **blockieren Sie den Benutzer für die Anmeldung aus**, und wählen Sie dann **Speichern**aus. 

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Mitarbeiter aus, den Sie blockieren möchten, und wählen Sie dann **Anmeldung blockieren**aus.

3. Wählen Sie **blockieren Sie den Benutzer für die Anmeldung aus**, und wählen Sie dann **Speichern**aus. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Mitarbeiter aus, den Sie blockieren möchten, und wählen Sie dann **Anmeldung blockieren**aus.

3. Wählen Sie **blockieren Sie den Benutzer für die Anmeldung aus**, und wählen Sie dann **Speichern**aus. 

::: moniker-end

## <a name="block-a-former-employees-access-to-email-exchange-online"></a>Blockieren des Zugriffs eines ehemaligen Mitarbeiters auf E-Mail (Exchange Online)
<a name="bkmk_block_email"> </a>

Wenn Sie über e-Mail als Teil Ihres Microsoft 365-Abonnements verfügen, müssen Sie sich beim Exchange Admin Center anmelden, um die folgenden Schritte durchführen, um zu verhindern, dass Ihr ehemaliger Mitarbeiter auf seine e-Mail zugreift.
  

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=2059104" target="_blank">Exchange Admin Center</a>.
     
2. Navigieren Sie im Exchange Admin Center zu **Empfänger** \> **Postfächer**. 
    
3. Doppelklicken Sie auf den Benutzer, und wechseln Sie zur Seite **Postfachfeatures** . Wählen Sie unter **Mobile Geräte**die Option **Exchange ActiveSync deaktivieren** aus **, und deaktivieren Sie OWA für mobile Geräte,** und beantworten Sie beide bei der entsprechenden Aufforderung mit **Ja** . 
    
4. Wählen Sie unter **e-Mail-Konnektivität**die Option **Deaktivieren** und **Ja** beantworten, wenn Sie dazu aufgefordert werden. 
    
## <a name="remove-and-delete-the-microsoft-365-license-from-a-former-employee"></a>Entfernen und Löschen der Microsoft 365-Lizenz von einem ehemaligen Mitarbeiter
<a name="bkmk_remove"> </a>

Damit Sie nicht weiterhin für eine Lizenz bezahlen, nachdem jemand Ihre Organisation verlassen hat, müssen Sie Ihre Microsoft 365-Lizenz entfernen und dann aus Ihrem Abonnement löschen. Wenn Sie die Lizenz nicht aus Ihrem Abonnement löschen möchten, können Sie sie einem anderen Benutzer zuweisen.
  
Wenn Sie die Lizenz entfernen, werden alle Daten des Benutzers noch 30 Tage gespeichert. Sie können auf die Daten [zugreifen](get-access-to-and-back-up-a-former-user-s-data.md) oder das Konto [wiederherstellen](restore-user.md), wenn der Benutzer zurückkehrt. Nach 30 Tagen werden alle Daten des Benutzers (mit Ausnahme der auf SharePoint Online gespeicherten Dokumente) dauerhaft aus Microsoft 365 gelöscht und können nicht wiederhergestellt werden. 

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Namen des Mitarbeiters aus, den Sie blockieren möchten, und wählen Sie dann die Registerkarte **Lizenzen und apps** aus.

4. Deaktivieren Sie die Kontrollkästchen für die zu entfernenden Lizenzen, und wählen Sie dann **Änderungen speichern**aus.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Mitarbeiter aus, den Sie blockieren möchten, und wählen Sie dann neben **Produktlizenzen**die Option **Bearbeiten**aus.

3. Deaktivieren Sie auf der Seite **Produktlizenzen** die zu entfernenden Lizenzen, und wählen Sie dann **Speichern**aus.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Mitarbeiter aus, den Sie blockieren möchten, und wählen Sie dann neben **Produktlizenzen**die Option **Bearbeiten**aus.

3. Deaktivieren Sie auf der Seite **Produktlizenzen** die zu entfernenden Lizenzen, und wählen Sie dann **Speichern**aus.

::: moniker-end


**Zum Verringern der Anzahl der von Ihnen bezahlten Lizenzen**, bis Sie eine andere Person einstellen, führen Sie die folgenden Schritte aus: 

::: moniker range="o365-worldwide"



1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Ihre Produkte</a>.


::: moniker-end

::: moniker range="o365-germany"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Abonnements</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. Navigieren Sie im Admin Center zur Seite **Abrechnung** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Abonnements</a>.

::: moniker-end
    
2. Wählen Sie **Lizenzen hinzufügen/entfernen** aus, um die Lizenz zu löschen, damit Sie Sie erst dann bezahlen, wenn Sie eine andere Person einstellen.

Wenn Sie eine weitere Person zu Ihrem Unternehmen [Hinzufügen](add-users.md) , werden Sie aufgefordert, gleichzeitig eine Lizenz mit nur einem Schritt zu kaufen.
    
Weitere Informationen zum Verwalten von Benutzerlizenzen für Microsoft 365 for Business finden Sie unter [Zuweisen von Lizenzen zu Benutzern in Microsoft 365 for](../manage/assign-licenses-to-users.md)Business und [Entfernen von Lizenzen von Benutzern in Microsoft 365 for Business](../manage/remove-licenses-from-users.md).
  
## <a name="how-the-deleted-employee-account-affects-skype-for-business"></a>Auswirkungen des gelöschten Mitarbeiterkontos auf Skype for Business
<a name="bkmk_remove"> </a>

When you remove a user's license from Office 365, the PSTN calling number associated with the user will be released. You can assign it to another user.
  
If the user belongs to a queue group, they will no longer be a viable target of the call queue agents. So, we recommend also removing the user from the groups associated with the call queue. 
  
## <a name="delete-a-former-employees-user-account"></a>Löschen des Benutzerkontos eines ehemaligen Mitarbeiters
<a name="bkmk_delete"> </a>

Nachdem Sie auf alle Benutzerdaten des ehemaligen Mitarbeiters zugegriffen und diese gespeichert haben, können Sie das Konto des ehemaligen Mitarbeiters löschen.
  
Don't delete the account if you've set up email forwarding or converted it to a shared mailbox. Both need the account to anchor the forwarding or shared mailbox.

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Namen des Mitarbeiters aus, den Sie löschen möchten.

3. Wählen Sie unter dem Namen des Benutzers das Symbol für **Delete User**aus. Wählen Sie die gewünschten Optionen für diesen Benutzer aus, und wählen Sie dann **Benutzer löschen**aus.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Namen des Mitarbeiters aus, den Sie löschen möchten.

3. Wählen Sie oben auf der Seite **Benutzer löschen**aus. Wählen Sie die gewünschten Optionen für diesen Benutzer aus, und wählen Sie dann **Benutzer löschen**aus.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

2. Wählen Sie den Namen des Mitarbeiters aus, den Sie löschen möchten.

3. Wählen Sie oben auf der Seite **Benutzer löschen**aus. Wählen Sie die gewünschten Optionen für diesen Benutzer aus, und wählen Sie dann **Benutzer löschen**aus.

::: moniker-end

When you delete a user, the account becomes inactive for approximately 30 days. You have until then to restore the account before it is permanently deleted.
  
### <a name="does-your-organization-use-active-directory"></a>Verwendet Ihre Organisation Active Directory?

Wenn Ihre Organisation Benutzerkonten mit Microsoft 365 aus einer lokalen Active Directory Umgebung synchronisiert, müssen Sie diese Benutzerkonten in Ihrem lokalen Active Directory Dienst löschen und wiederherstellen. Sie können sie nicht in Office 365 löschen und wiederherstellen.
  
Anweisungen hierzu finden Sie in diesem Artikel: [Löschen eines Benutzerkontos](https://go.microsoft.com/fwlink/?linkid=841808).
  
Wenn Sie Azure Active Directory verwenden, lesen Sie den Artikel zum PowerShell-Cmdlet [Remove-MsolUser](https://go.microsoft.com/fwlink/?linkid=842230). 
  
## <a name="what-you-need-to-know-about-terminating-an-employees-email-session"></a>Wichtige Informationen zum Beenden der E-Mail-Sitzung eines Mitarbeiters
<a name="bkmk_session"> </a>

Hier finden Sie Informationen dazu, wie Sie die E-Mail-Nutzung für einen Mitarbeiter beenden können (Exchange).
  
|||
|:-----|:-----|
|**Mögliche Aktionen** <br/> |**Wie geht das?** <br/> |
|Sitzung beenden (z. B. Outlook im Web, Outlook, Exchange Active Sync usw.) und Öffnen einer neuen Sitzung erzwingen  <br/> |Kennwort zurücksetzen  <br/> |
|Sitzung beenden und Zugriff auf zukünftige Sitzungen (für alle Protokolle) sperren  <br/> |Disable the account. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-Mailbox user@contoso.com -AccountDisabled:$true` <br/> |
|Sitzung für ein bestimmtes Protokoll (z. B. ActiveSync) beenden  <br/> |Disable the protocol. For example (in the Exchange admin center or using PowerShell):  <br/>  `Set-CASMailbox user@contoso.com -ActiveSyncEnabled:$false` <br/> |
   
Die oben aufgeführten Vorgänge können an drei Stellen erfolgen:
  
|||
|:-----|:-----|
|**Ort zum Beenden der Sitzung** <br/> |**Dauer der Maßnahme** <br/> |
|Im Exchange Admin Center oder mithilfe von PowerShell  <br/> |Voraussichtliche Verzögerung = innerhalb von 30 Minuten  <br/> |
|Azure Active Directory Admin Center  <br/> |Voraussichtliche Verzögerung = 60 Minuten  <br/> |
|Lokale Umgebung  <br/> |Voraussichtliche Verzögerung = 3 Stunden oder mehr  <br/> |
   
### <a name="how-to-get-fastest-response-for-account-termination"></a>So erhalten Sie eine schnelle Reaktion auf die Kündigung eines Kontos

 **Fastest**: Use the Exchange admin center (use PowerShell) or Azure Active Directory admin center. In an on-premises environment, it can take several hours to sync the change through DirSync. 
  
 **Fastest for a user with presence on-premises and in the Exchange Datacenter**: Terminate the session using Azure Active Directory admin center/Exchange admin center AND make the change in the on-premises environment as well. Otherwise, the change in Azure Active Directory admin center/Exchange admin center will be overwritten by DirSync. 
  
## <a name="related-articles"></a>Verwandte Artikel

[Wiederherstellen eines Benutzers](restore-user.md)
  
