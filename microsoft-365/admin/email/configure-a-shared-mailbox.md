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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
description: Erstellen Sie ein freigegebenes Postfach, und konfigurieren Sie einige Einstellungen für die Benutzer, z. B. E-Mail-Weiterleitung und automatische Antworten.
ms.openlocfilehash: e69d1bbde5784339f3973bf456eca1ded72840af
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53393991"
---
# <a name="configure-shared-mailbox-settings"></a>Konfigurieren der Einstellungen für das freigegebene Postfach

Nachdem Sie [ein freigegebenes Postfach erstellt](create-a-shared-mailbox.md)haben, sollten Sie einige Einstellungen für die Postfachbenutzer konfigurieren, z. B. die E-Mail-Weiterleitung und automatische Antworten. Später möchten Sie möglicherweise andere Einstellungen ändern, z. B. den Postfachnamen, Mitglieder oder Mitgliedsberechtigungen. 

## <a name="change-the-name-or-email-alias-of-a-shared-mailbox-or-change-the-primary-email-address"></a>Ändern des Namens oder des E-Mail-Alias eines freigegebenen Postfachs oder Ändern der primären E-Mail-Adresse

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann neben **Name, E-Mail, E-Mail-Aliase** **bearbeiten** aus.

3. Geben Sie einen neuen Namen ein, oder fügen Sie einen weiteren Alias hinzu. Wenn Sie die primäre E-Mail-Adresse ändern möchten, muss Ihr Postfach über mehrere E-Mail-Aliase verfügen.

4. Klicken Sie auf **Speichern**.

## <a name="forward-emails-that-are-sent-to-a-shared-mailbox"></a>Weiterleiten von E-Mails, die an ein freigegebenes Postfach gesendet wurden

Sie müssen dem freigegebenen Postfach keine Lizenz zuweisen, um E-Mails weiterzuleiten, die an das freigegebene Postfach gesendet werden. Sie können die Nachrichten an eine beliebige gültige E-Mail-Adresse oder Verteilerliste weiterleiten.

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"E-Mail-Weiterleitung** \> **bearbeiten"** aus.
    
3. Legen Sie die Umschaltfläche auf **"Ein"** fest, und geben Sie eine E-Mail-Adresse ein, an die die Nachrichten weitergeleitet werden sollen. Dabei kann es sich um eine beliebige gültige E-Mail-Adresse handeln. Um an mehrere Adressen weiterzuleiten, müssen Sie [eine Verteilergruppe](/office365/admin/setup/create-distribution-lists) für die Adressen erstellen und dann den Namen der Gruppe in dieses Feld eingeben.
    
4. Klicken Sie auf **Speichern**.

## <a name="send-automatic-replies-from-a-shared-mailbox"></a>Senden von automatischen Antworten aus einem freigegebenen Postfach

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"Automatische Antworten** \> **bearbeiten"** aus.
    
3. Setzen Sie den Schalter auf **Ein**, und wählen Sie aus, ob die Antwort an Personen innerhalb oder außerhalb Ihrer Organisation gesendet werden soll.

4. Geben Sie die Antwort ein, die Sie an Personen innerhalb Ihrer Organisation senden möchten. Sie können nur Text (keine Bilder) hinzufügen.

5. Wenn Sie *auch* eine Antwort an Personen außerhalb Ihrer Organisation senden möchten, aktivieren Sie das Kontrollkästchen, wen Sie die Antwort erhalten möchten, und geben Sie den Text ein. Es ist nicht möglich, eine Antwort nur an Personen außerhalb Ihrer Organisation (ohne Einbeziehung von Personen innerhalb Ihrer Organisation) zu senden.

6. Klicken Sie auf **Speichern**.

## <a name="allow-everyone-to-see-the-sent-email-the-replies"></a>Jedem erlauben, die gesendeten E-Mails (die Antworten) anzuzeigen

Nachrichten, die aus dem freigegebenen Postfach gesendet wurden, werden standardmäßig nicht im Ordner "Gesendete Elemente" dieses Postfachs gespeichert. Stattdessen werden sie im Ordner "Gesendete Elemente" der Person gespeichert, die die Nachricht gesendet hat.

Wenn Sie zulassen möchten, dass jeder die gesendete E-Mail sehen kann, bearbeiten Sie im Admin Center die Einstellungen für das freigegebene Postfach, und wählen Sie **"Gesendete Elemente** \> **bearbeiten"** aus.


## <a name="choose-the-apps-that-a-shared-mailbox-can-use-to-access-microsoft-email"></a>Auswählen der Apps, die ein freigegebenes Postfach für den Zugriff auf Microsoft-E-Mails verwenden kann

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"E-Mail-Apps** \> **bearbeiten"** aus.

3. Legen Sie die Umschaltfläche für alle Apps **auf "Ein"** fest, mit denen Mitglieder auf das freigegebene Postfach zugreifen können sollen. Legen Sie die Umschaltfläche für apps, die sie nicht verwenden sollen, auf **"Aus"** fest. 

4. Klicken Sie auf **Speichern**.


## <a name="put-a-shared-mailbox-on-litigation-hold"></a>Aktivieren der Beweissicherung für ein freigegebenes Postfach

Weitere Informationen zum Beweissicherungsverfahren finden Sie unter [Erstellen eines Beweissicherungsverfahrens.](../../compliance/create-a-litigation-hold.md)

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann  \> **"Beweissicherungsverfahren" aus.**

3. Legen Sie die Umschaltfläche auf **"Ein"** fest. 

4. Geben Sie optional eine Dauer, einen Hinweis zum Haltebereich und eine URL mit weiteren Informationen ein.  

5. Klicken Sie auf **Speichern**.


## <a name="add-or-remove-members"></a>Hinzufügen oder Entfernen von Mitgliedern

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **"Mitglieder** \> **bearbeiten"** aus.

3. Führen Sie einen der folgenden Schritte aus:
   - Wählen Sie zum Hinzufügen von Mitgliedern **"Mitglieder hinzufügen"** aus, suchen Sie nach einem hinzuzufügenden Mitglied oder wählen Sie es aus, und wählen Sie dann **"Speichern"** aus.
   - Um Mitglieder zu entfernen, verwenden Sie das Suchfeld, um bei Bedarf nach dem Mitglied zu suchen, wählen Sie das **X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern** aus. 

4. Wählen Sie noch mal **Speichern** aus.

## <a name="add-or-remove-permissions-of-members"></a>Hinzufügen oder Entfernen von Berechtigungen von Mitgliedern

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann Die  \> **Berechtigungen "Elemente anpassen"** aus.

3. Wählen Sie **"Bearbeiten"** neben der Berechtigung aus, die Sie für ein Mitglied ändern möchten. 

4. Führen Sie einen der folgenden Schritte aus:
   - Um diese Berechtigung einem zusätzlichen Mitglied zu erteilen, wählen Sie **"Berechtigungen hinzufügen"** aus, suchen Oder wählen Sie ein hinzuzufügende Mitglied aus, und wählen Sie dann **"Speichern"** aus.
   - Um die Berechtigung aus einem Mitglied zu entfernen, verwenden Sie das Suchfeld, um bei Bedarf nach dem Mitglied zu suchen, wählen Sie das **X** neben dem Namen des Mitglieds aus, und wählen Sie dann **Speichern** aus. 

4. Wählen Sie noch mal **Speichern** aus.

## <a name="show-or-hide-a-shared-mailbox-in-the-global-address-list"></a>Ein- oder Ausblenden eines freigegebenen Postfachs in der globalen Adressliste

Wenn Sie das freigegebene Postfach nicht in der globalen Adressliste anzeigen möchten, wird das Postfach nicht in der Adressliste Ihrer Organisation angezeigt, aber es erhält weiterhin E-Mails, die an das Postfach gesendet werden. 

1. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

2. Wählen Sie das freigegebene Postfach aus, das Sie bearbeiten möchten, und wählen Sie dann **in der globalen Adressliste** "Bearbeiten" die Option \> **"Anzeigen"** aus.

3. Legen Sie die Umschaltfläche auf **"Ein"**  oder **"Aus"** fest. 

4. Klicken Sie auf **Speichern**.

> [!NOTE]
> Das Ausblenden eines freigegebenen Postfachs aus der Adressliste macht es für neue freigegebene Postfachmitglieder unmöglich, das ausgeblendete Postfach zu ihrem Outlook Profil hinzuzufügen, bis das freigegebene Postfach wieder in der Adressliste angezeigt wird. 

## <a name="related-content"></a>Verwandte Inhalte

[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md) (Artikel)\
[Erstellen eines freigegebenen Postfachs](create-a-shared-mailbox.md) (Artikel)\
[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md) (Artikel)\
[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md) (Artikel)\
[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md) (Artikel)