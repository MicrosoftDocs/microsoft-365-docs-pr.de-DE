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
search.appverid:
- BCS160
- MET150
- MOE150
description: Nachdem Sie ein freigegebenes Postfach erstellt haben, sollten Sie einige Einstellungen für die Benutzer konfigurieren, z. B. E-Mail-Weiterleitung und automatische Antworten. Später möchten Sie möglicherweise andere Einstellungen ändern, z. B. den Postfachnamen oder Mitglieder.
ms.openlocfilehash: 2d0998ba2bdc95a9f78f59527bd9bd6fa98b4c45
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915914"
---
# <a name="configure-shared-mailbox-settings"></a>Konfigurieren der Einstellungen für das freigegebene Postfach

Nachdem Sie ein [freigegebenes](create-a-shared-mailbox.md)Postfach erstellt haben, sollten Sie einige Einstellungen für die Postfachbenutzer konfigurieren, z. B. E-Mail-Weiterleitung und automatische Antworten. Später möchten Sie möglicherweise andere Einstellungen ändern, z. B. den Postfachnamen, Mitglieder oder Mitgliedsberechtigungen. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Ändern des Namens oder des E-Mail-Alias eines freigegebenen Postfachs oder Ändern der primären E-Mail-Adresse

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **Bearbeiten** neben **Name, E-Mail, E-Mail-Aliase aus.**

3. Geben Sie einen neuen Namen ein, oder fügen Sie einen anderen Alias hinzu. Wenn Sie die primäre E-Mail-Adresse ändern möchten, muss Ihr Postfach über mehrere E-Mail-Aliase verfügen.

4. Wählen Sie **Speichern** aus.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Weiterleiten von E-Mails, die an ein freigegebenes Postfach gesendet wurden

Sie müssen dem freigegebenen Postfach keine Lizenz zuweisen, um E-Mails weiter zu senden, die an das freigegebene Postfach gesendet werden. Sie können die Nachrichten an eine beliebige gültige E-Mail-Adresse oder Verteilerliste weiterleiten.

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **E-Mail-Weiterleitung** \> **Bearbeiten aus.**
    
3. Legen Sie den Umschalter auf **Ein** und geben Sie eine E-Mail-Adresse ein, an die die Nachrichten weitergeleitet werden sollen. Dies kann eine beliebige gültige E-Mail-Adresse sein. Zum Weiterleiten an mehrere Adressen [](/office365/admin/setup/create-distribution-lists) müssen Sie eine Verteilergruppe für die Adressen erstellen und dann den Namen der Gruppe in dieses Feld eingeben.
    
4. Wählen Sie **Speichern** aus.

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

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie **dann Automatische Antworten** Bearbeiten \> **aus.**
    
3. Setzen Sie den Schalter auf **Ein**, und wählen Sie aus, ob die Antwort an Personen innerhalb oder außerhalb Ihrer Organisation gesendet werden soll.

4. Geben Sie die Antwort ein, die Sie an Personen innerhalb Ihrer Organisation senden möchten. Sie können nur Text (keine Bilder) hinzufügen.

5. Wenn Sie auch *eine* Antwort an Personen außerhalb Ihrer Organisation senden möchten, aktivieren Sie das Kontrollkästchen, wen Sie die Antwort erhalten möchten, und geben Sie den Text ein. Es ist nicht möglich, eine Antwort nur an Personen außerhalb Ihrer Organisation (ohne Einbeziehung von Personen innerhalb Ihrer Organisation) zu senden.

6. Wählen Sie **Speichern** aus.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Jedem erlauben, die gesendeten E-Mails (die Antworten) anzuzeigen

Nachrichten, die aus dem freigegebenen Postfach gesendet wurden, werden standardmäßig nicht im Ordner "Gesendete Elemente" dieses Postfachs gespeichert. Stattdessen werden sie im Ordner "Gesendete Elemente" der Person gespeichert, die die Nachricht gesendet hat.

Wenn Sie allen Benutzern das Anzeigen der gesendeten E-Mail ermöglichen möchten, bearbeiten Sie im Admin Center die Einstellungen für freigegebene Postfächer, und wählen Sie Gesendete **Elemente** \> **Bearbeiten aus.**


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

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **E-Mail-Apps** \> **Bearbeiten aus.**

3. Legen Sie die Umschalte **auf Ein** für alle Apps, die Mitglieder für den Zugriff auf das freigegebene Postfach verwenden sollen. Legen Sie den Umschalter **für** apps, die sie nicht verwenden sollen, auf Aus. 

4. Wählen Sie **Speichern** aus.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Verschieben eines freigegebenen Postfachs in das Verfahrensverfahren

Weitere Informationen zum Prozesssicherungsverfahren finden Sie unter [Create a Litigation Hold](../../compliance/create-a-litigation-hold.md).

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end 

::: moniker range="o365-germany"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">Admin Center</a> zur Seite **Gruppen** > **Freigegebene Postfächer**. 

::: moniker-end

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann Rechtsstreitigkeiten  \> **archivieren Bearbeiten aus.**

3. Legen Sie den Umschalter auf **Ein .** 

4. Geben Sie optional eine Dauer, eine Notiz zum Halteraum und eine URL mit weiteren Informationen ein.  

5. Wählen Sie **Speichern** aus.


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

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie **dann Mitglieder** \> **bearbeiten aus.**

3. Führen Sie einen der folgenden Schritte aus:
   - Wenn Sie Mitglieder hinzufügen möchten, wählen Sie **Mitglieder hinzufügen** aus, suchen oder wählen Sie ein hinzuzufügendes Mitglied aus, und wählen Sie dann **Speichern aus.**
   - Um Mitglieder zu entfernen, verwenden Sie das Feld Suchen, um bei Bedarf nach dem Mitglied zu suchen, wählen Sie **das X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern aus.** 

4. Wählen Sie noch mal **Speichern** aus.

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

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie **dann Mitglieder Berechtigungen** anpassen \> **aus.**

3. Wählen **Sie Bearbeiten** neben der Berechtigung aus, die Sie für ein Mitglied ändern möchten. 

4. Führen Sie einen der folgenden Schritte aus:
   - Wenn Sie diesem zusätzlichen Mitglied diese Berechtigung erteilen möchten, wählen Sie Berechtigungen hinzufügen **aus,** suchen oder wählen Sie ein hinzuzufügendes Mitglied aus, und wählen Sie dann **Speichern aus.**
   - Um die Berechtigung aus einem Mitglied zu entfernen, verwenden Sie das Feld Suchen, um bei Bedarf nach dem Mitglied zu suchen, wählen Sie **das X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern aus.** 

4. Wählen Sie noch mal **Speichern** aus.

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

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie **dann Anzeigen in der globalen Adressliste** Bearbeiten \> **aus.**

3. Legen Sie den Umschalter auf **Ein oder** **Aus .** 

4. Wählen Sie **Speichern** aus.

> [!NOTE]
> Das Ausblenden eines freigegebenen Postfachs aus der Adressliste macht es neuen freigegebenen Postfachmitgliedern unmöglich, das ausgeblendete Postfach ihrem Outlook-Profil hinzuzufügen, bis das freigegebene Postfach erneut in der Adressliste angezeigt wird. 

## <a name="related-articles"></a>Verwandte Artikel

[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md)

[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md)

[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md)

[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md)

[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md)