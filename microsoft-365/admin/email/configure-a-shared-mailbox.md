---
title: Konfigurieren eines freigegebenen Postfachs
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
search.appverid:
- BCS160
- MET150
- MOE150
description: Nachdem Sie ein freigegebenes Postfach erstellt haben, sollten Sie einige Einstellungen für die Benutzer konfigurieren, beispielsweise e-Mail-Weiterleitung und automatische Antworten. Möglicherweise möchten Sie später andere Einstellungen ändern, beispielsweise den Postfachnamen oder die Mitglieder.
ms.openlocfilehash: fc2995dc448c7cb28c13c10d78b57e7141963539
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212021"
---
# <a name="configure-a-shared-mailbox"></a>Konfigurieren eines freigegebenen Postfachs

Nachdem Sie [ein freigegebenes Postfach erstellt](create-a-shared-mailbox.md)haben, sollten Sie einige Einstellungen für die Postfachbenutzer konfigurieren, beispielsweise e-Mail-Weiterleitung und automatische Antworten. Möglicherweise möchten Sie später andere Einstellungen ändern, beispielsweise den Postfachnamen, Mitglieder oder Mitgliedsberechtigungen. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Ändern des Namens oder des e-Mail-Alias eines freigegebenen Postfachs oder Ändern der primären e-Mail-Adresse

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten** neben **Name, e-Mail, e-Mail-Aliase**aus.

3. Geben Sie einen neuen Namen ein, oder fügen Sie einen weiteren Alias hinzu. Wenn Sie die primäre e-Mail-Adresse ändern möchten, muss Ihr Postfach über mehr als einen e-Mail-Alias verfügen.

4. Klicken Sie auf **Speichern**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Weiterleiten von E-Mails, die an ein freigegebenes Postfach gesendet wurden

Sie müssen dem freigegebenen Postfach keine Lizenz zuweisen, um an Sie gesendete e-Mails weiterzuleiten. Sie können die Nachrichten an eine beliebige gültige e-Mail-Adresse oder Verteilerliste weiterleiten.

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **e-Mail Weiterleitung** \> **Bearbeiten**aus.
    
3. Legen Sie die Umschaltfläche **auf**ein und geben Sie eine e-Mail-Adresse ein, an die die Nachrichten weitergeleitet werden sollen. Es kann sich um eine beliebige gültige e-Mail-Adresse handeln. Um an mehrere Adressen weiterzuleiten, müssen Sie [eine Verteilergruppe](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists?view=o365-worldwide) für die Adressen erstellen und dann den Namen der Gruppe in dieses Feld eingeben.
    
4. Klicken Sie auf **Speichern**.

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>Senden von automatischen Antworten aus einem freigegebenen Postfach

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **automatische Antworten** \> **Bearbeiten**aus.
    
3. Setzen Sie den Schalter auf **Ein**, und wählen Sie aus, ob die Antwort an Personen innerhalb oder außerhalb Ihrer Organisation gesendet werden soll.

4. Geben Sie die Antwort ein, die Sie an Personen innerhalb Ihrer Organisation senden möchten. Sie können nur Text (keine Bilder) hinzufügen.

5. Wenn Sie *auch* eine Antwort an Personen außerhalb Ihrer Organisation senden möchten, aktivieren Sie das Kontrollkästchen, die Antwort erhalten soll, und geben Sie den Text ein. Es ist nicht möglich, eine Antwort nur an Personen außerhalb Ihrer Organisation (ohne Einbeziehung von Personen innerhalb Ihrer Organisation) zu senden.

6. Klicken Sie auf **Speichern**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Jedem erlauben, die gesendeten E-Mails (die Antworten) anzuzeigen

Nachrichten, die aus dem freigegebenen Postfach gesendet wurden, werden standardmäßig nicht im Ordner "Gesendete Elemente" dieses Postfachs gespeichert. Stattdessen werden sie im Ordner "Gesendete Elemente" der Person gespeichert, die die Nachricht gesendet hat.

Wenn Sie zulassen möchten, dass alle Benutzer die gesendeten e-Mails anzeigen können, bearbeiten Sie im Admin Center die Einstellungen für freigegebene Postfächer, und wählen Sie **Gesendete Elemente** \> **Bearbeiten**aus.


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-office-365-email"></a>Auswählen der apps, die ein freigegebenes Postfach für den Zugriff auf Office 365 e-Mail verwenden kann

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **e-Mail apps** \> **Bearbeiten**aus.

3. Legen Sie die Umschaltfläche für alle apps, die Mitglieder für den Zugriff auf das freigegebene Postfach verwenden können, auf **ein** fest. Legen Sie die Umschaltfläche für alle apps, die Sie nicht verwenden möchten, auf **Off** fest. 

4. Klicken Sie auf **Speichern**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Speichern eines freigegebenen Postfachs für das Beweissicherungsverfahren

Weitere Informationen zum Beweissicherungsverfahren finden Sie unter [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **Bearbeitungs** **Prozess halten** \> aus.

3. Legen Sie die Umschaltfläche **auf ein**fest. 

4. Geben Sie optional eine Dauer, eine Notiz zum Haltestatus und eine URL mit weiteren Informationen ein.  

5. Klicken Sie auf **Speichern**.


## <a name="add-or-remove-members"></a>Hinzufügen oder Entfernen von Mitgliedern

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und klicken Sie dann auf **Mitglieder** \> **Bearbeiten**.

3. Führen Sie einen der folgenden Schritte aus:
   - Klicken Sie zum Hinzufügen von Mitgliedern auf **Mitglieder hinzufügen**, suchen Sie nach einem Mitglied, das hinzugefügt werden soll, und wählen Sie dann **Speichern**aus.
   - Um Mitglieder zu entfernen, verwenden Sie das Suchfeld, um bei Bedarf nach dem Element zu suchen, wählen Sie das **X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern**aus. 

4. Wählen Sie erneut **Speichern** aus.

## <a name="add-or-remove-permissions-of-members"></a>Hinzufügen oder Entfernen von Berechtigungen für Mitglieder

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, **und wählen Sie dann Benutzer** \> **Berechtigungen anpassen**aus.

3. Wählen Sie neben der Berechtigung, die Sie für ein Mitglied ändern möchten, die Option **Bearbeiten** aus. 

4. Führen Sie einen der folgenden Schritte aus:
   - Um diese Berechtigung einem zusätzlichen Mitglied zu erteilen, wählen Sie **Berechtigungen hinzufügen**, suchen oder Auswählen eines hinzuzufügenden Elements aus, und wählen Sie dann **Speichern**aus.
   - Wenn Sie die Berechtigung eines Mitglieds entfernen möchten, verwenden Sie das Suchfeld, um nach dem Mitglied zu suchen, falls erforderlich, wählen Sie das **X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern**aus. 

4. Wählen Sie erneut **Speichern** aus.

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Ein-oder Ausblenden eines freigegebenen Postfachs in der globalen Adressliste

Wenn Sie das freigegebene Postfach nicht in der globalen Adressliste anzeigen möchten, wird das Postfach nicht in der Adressliste Ihrer Organisation angezeigt, es erhält jedoch weiterhin e-Mail-Nachrichten, die an es gesendet werden. 

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **in globale Adresslisten** \> **Bearbeitung**anzeigen aus.

3. Legen Sie die Umschaltfläche **auf ein** oder **aus**fest. 

4. Klicken Sie auf **Speichern**.

> [!NOTE]
> Wenn Sie ein freigegebenes Postfach aus der Adressliste ausblenden, ist es für neue freigegebene Post Fach Mitglieder unmöglich, das ausgeblendete Postfach Ihrem Outlook-Profil hinzuzufügen, bis das freigegebene Postfach erneut in der Adressliste angezeigt wird. 

## <a name="related-articles"></a>Verwandte Artikel

[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md)

[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md)

[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md)

[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md)

[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md)
