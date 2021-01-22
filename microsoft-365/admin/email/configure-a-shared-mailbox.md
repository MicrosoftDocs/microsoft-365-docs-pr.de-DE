---
title: Konfigurieren der Einstellungen für das freigegebene Postfach
f1.keywords:
- NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
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
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
description: Nachdem Sie ein freigegebenes Postfach erstellt haben, sollten Sie einige Einstellungen für die Benutzer konfigurieren, z. B. E-Mail-Weiterleitung und automatische Antworten. Später möchten Sie möglicherweise andere Einstellungen ändern, z. B. den Postfachnamen oder die Mitglieder.
ms.openlocfilehash: fe5d35be556b8edf5456bc2c0b820dc0ce77e323
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49926606"
---
# <a name="configure-shared-mailbox-settings"></a>Konfigurieren der Einstellungen für das freigegebene Postfach

Nachdem Sie ein [freigegebenes](create-a-shared-mailbox.md)Postfach erstellt haben, sollten Sie einige Einstellungen für die Postfachbenutzer konfigurieren, z. B. die E-Mail-Weiterleitung und automatische Antworten. Später möchten Sie möglicherweise andere Einstellungen ändern, z. B. den Postfachnamen, Mitglieder oder Mitgliedsberechtigungen. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Ändern des Namens oder des E-Mail-Alias eines freigegebenen Postfachs oder der primären E-Mail-Adresse

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"Bearbeiten"** neben **"Name", "E-Mail", "E-Mail-Aliase" aus.**

3. Geben Sie einen neuen Namen ein, oder fügen Sie einen anderen Alias hinzu. Wenn Sie die primäre E-Mail-Adresse ändern möchten, muss Ihr Postfach mehrere E-Mail-Aliase haben.

4. Klicken Sie auf **Speichern**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Weiterleiten von E-Mails, die an ein freigegebenes Postfach gesendet wurden

Sie müssen dem freigegebenen Postfach keine Lizenz zuweisen, um an dieses gesendete E-Mails weiterleiten zu können. Sie können die Nachrichten an eine beliebige gültige E-Mail-Adresse oder Verteilerliste weiterleiten.

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"E-Mail-Weiterleitung** \> **bearbeiten" aus.**
    
3. Legen Sie die Umschalttaste auf **"Ein"** und geben Sie eine E-Mail-Adresse ein, an die die Nachrichten weitergeleitet werden sollen. Dies kann eine beliebige gültige E-Mail-Adresse sein. Zum Weiterleiten an mehrere Adressen [](https://docs.microsoft.com/office365/admin/setup/create-distribution-lists) müssen Sie eine Verteilergruppe für die Adressen erstellen und dann den Namen der Gruppe in dieses Feld eingeben.
    
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

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"Automatische Antworten** \> **Bearbeiten" aus.**
    
3. Setzen Sie den Schalter auf **Ein**, und wählen Sie aus, ob die Antwort an Personen innerhalb oder außerhalb Ihrer Organisation gesendet werden soll.

4. Geben Sie die Antwort ein, die Sie an Personen innerhalb Ihrer Organisation senden möchten. Sie können nur Text (keine Bilder) hinzufügen.

5. Wenn Sie auch *eine* Antwort an Personen außerhalb Ihrer Organisation senden möchten, aktivieren Sie das Kontrollkästchen, wer die Antwort erhalten soll, und geben Sie den Text ein. Es ist nicht möglich, eine Antwort nur an Personen außerhalb Ihrer Organisation (ohne Einbeziehung von Personen innerhalb Ihrer Organisation) zu senden.

6. Klicken Sie auf **Speichern**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Jedem erlauben, die gesendeten E-Mails (die Antworten) anzuzeigen

Nachrichten, die aus dem freigegebenen Postfach gesendet wurden, werden standardmäßig nicht im Ordner "Gesendete Elemente" dieses Postfachs gespeichert. Stattdessen werden sie im Ordner "Gesendete Elemente" der Person gespeichert, die die Nachricht gesendet hat.

Wenn Sie zulassen möchten, dass allen Benutzern die gesendete E-Mail angezeigt wird, bearbeiten Sie im Admin Center die Einstellungen für das freigegebene Postfach, und wählen Sie "Gesendete **Elemente** \> **bearbeiten" aus.**


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>Auswählen der Apps, die ein freigegebenes Postfach für den Zugriff auf Microsoft-E-Mails verwenden kann

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"E-Mail-Apps** \> **bearbeiten" aus.**

3. Legen Sie die Umschalt auf **"Ein"** für alle Apps, die Mitglieder für den Zugriff auf das freigegebene Postfach verwenden sollen. Legen Sie die Umschalt auf **"Aus"** für alle Apps, die sie nicht verwenden sollen. 

4. Klicken Sie auf **Speichern**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Ein freigegebenes Postfach in das Archiv für Rechtsstreitigkeiten setzen

Weitere Informationen zum Halten von Rechtsstreitigkeiten finden Sie unter [Create a Litigation Hold](https://docs.microsoft.com/microsoft-365/compliance/create-a-litigation-hold).

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann "Rechtsstreitigkeiten  \> **archivieren" aus.**

3. Setzen Sie den Umschalter auf **"Ein".** 

4. Geben Sie optional eine Dauer, eine Notiz zum Halte halte und eine URL mit weiteren Informationen ein.  

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

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"Mitglieder** \> **bearbeiten" aus.**

3. Führen Sie einen der folgenden Schritte aus:
   - Wählen Sie zum Hinzufügen von Mitgliedern die Option **"Mitglieder hinzufügen"** aus, suchen Oder wählen Sie ein hinzuzufügendes Mitglied aus, und wählen Sie dann **"Speichern" aus.**
   - Um Mitglieder zu entfernen, verwenden Sie das Suchfeld, um bei Bedarf nach dem Mitglied zu suchen, wählen Sie **das X** neben dem Namen des Mitglieds aus, und wählen Sie dann Speichern **aus.** 

4. Wählen Sie **erneut "Speichern"** aus.

## <a name="add-or-remove-permissions-of-members"></a>Hinzufügen oder Entfernen von Berechtigungen von Mitgliedern

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann Berechtigungen zum **Anpassen** \> **von Mitgliedern aus.**

3. Wählen **Sie "Bearbeiten"** neben der Berechtigung aus, die Sie für ein Mitglied ändern möchten. 

4. Führen Sie einen der folgenden Schritte aus:
   - Um diese Berechtigung einem zusätzlichen Mitglied zu erteilen, wählen Sie "Berechtigungen hinzufügen" **aus,** suchen sie nach einem hinzuzufügende Mitglied, oder wählen Sie es aus, und wählen Sie dann **"Speichern" aus.**
   - Um die Berechtigung von einem Mitglied zu entfernen, verwenden Sie das Suchfeld, um bei Bedarf nach dem Mitglied zu suchen, wählen Sie **das X** neben dem Namen des Mitglieds aus, und wählen Sie dann Speichern **aus.** 

4. Wählen Sie **erneut "Speichern"** aus.

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Ein- oder Ausblenden eines freigegebenen Postfachs in der globalen Adressliste

Wenn Sie das freigegebene Postfach nicht in der globalen Adressliste anzeigen möchten, wird das Postfach nicht in der Adressliste Ihrer Organisation angezeigt, es erhält jedoch weiterhin E-Mails, die an das Postfach gesendet werden. 

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann "In globaler **Adressliste anzeigen"** \> **aus.**

3. Setzen Sie den Umschalter auf **Ein oder** **Aus.** 

4. Klicken Sie auf **Speichern**.

> [!NOTE]
> Das Ausblenden eines freigegebenen Postfachs aus der Adressliste macht es für neue freigegebene Postfachmitglieder unmöglich, das ausgeblendete Postfach zu ihrem Outlook-Profil hinzuzufügen, bis das freigegebene Postfach wieder in der Adressliste angezeigt wird. 

## <a name="related-articles"></a>Verwandte Artikel

[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md)

[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md)

[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md)

[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md)

[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md)
