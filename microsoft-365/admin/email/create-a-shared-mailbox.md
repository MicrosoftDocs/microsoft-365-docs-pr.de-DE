---
title: Erstellen eines freigegebenen Postfachs
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
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 871a246d-3acd-4bba-948e-5de8be0544c9
description: Erstellen Sie ein freigegebenes Postfach, damit mehrere Benutzer in Ihrem Unternehmen die Verantwortung für das Lesen und Beantworten von E-Mails teilen, die an eine Adresse gesendet wurden.
ms.openlocfilehash: 47690e1295b67c01f86429d97e0fc8d82ad58d6f
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529635"
---
# <a name="create-a-shared-mailbox"></a>Erstellen eines freigegebenen Postfachs 

> [!NOTE]
> Wenn Ihre Organisation eine Exchange-Hybridumgebung verwendet, sollten Sie das lokale Exchange Admin Center (EAC) zum Erstellen und Verwalten von freigegebenen Postfächern verwenden. Siehe [Erstellen freigegebener Postfächer im Exchange Admin Center](https://docs.microsoft.com/Exchange/collaboration/shared-mailboxes/create-shared-mailboxes?view=exchserver-2019.)<br><br>
> Wenn Sie nicht sicher sind, ob Sie ein freigegebenes Postfach oder eine Microsoft 365-Gruppe für Outlook erstellen sollten, finden Sie Informationen dazu unter [Vergleichen von Gruppen](../create-groups/compare-groups.md). Beachten Sie, dass es aktuell nicht möglich ist, ein freigegebenes Postfach zu einer Microsoft 365-Gruppe zu migrieren. Wenn Sie diese Funktion wünschen, teilen Sie uns dies mittels [Hier abstimmen](https://go.microsoft.com/fwlink/?linkid=871518) mit.

Freigegebene Postfächer lassen sich auf einfache Weise erstellen, damit eine Gruppe von Personen E-Mails einer gemeinsamen E-Mail-Adresse wie "info@contoso.com" überwachen und senden kann. Wenn eine Person in der Gruppe auf eine Nachricht antwortet, die an das freigegebene Postfach gesendet wurde, wird als Absender der E-Mail das freigegebene Postfach angegeben, nicht der einzelne Benutzer. 

Freigegebene Postfächer enthalten einen freigegebenen Kalender. Viele kleine Unternehmen nutzen den freigegebenen Kalender gerne als zentralen Ort, an dem jeder Mitarbeiter seine Termine eintragen kann. So können beispielsweise alle drei Personen, die Kundenbesuche durchführen, den freigegebenen Kalender anzeigen und darin ihre Termine eintragen.  Dies ist eine einfache Möglichkeit, um jeden über den jeweiligen Aufenthaltsort auf dem Laufenden zu halten.

Lesen Sie vor dem Erstellen eines freigegebenen Postfachs unbedingt [Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md).

## <a name="create-a-shared-mailbox-and-add-members"></a>Erstellen eines freigegebenen Postfachs und Hinzufügen von Mitgliedern
  
1. Melden Sie sich mit einem globalen Administrator oder mit einem Exchange-Administratorkonto an. Wenn die Meldung „**Sie haben keine Berechtigung für den Zugriff auf diese Seite oder die Ausführung dieser Aktion**“ angezeigt wird, sind Sie kein Administrator. 

::: moniker range="o365-worldwide"

2. Wechseln Sie im Admin Center zur Seite **Gruppen** \><a href="https://go.microsoft.com/fwlink/p/?linkid=2066847" target="_blank">Freigegebene Postfächer</a>.

::: moniker-end

::: moniker range="o365-germany"

2. Wechseln Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=848041) zur Seite **Gruppen** \> **Freigegebene Postfächer**.

::: moniker-end

::: moniker range="o365-21vianet"

2. Wechseln Sie im [Admin Center](https://go.microsoft.com/fwlink/p/?linkid=850627) zur Seite **Gruppen** \> **Freigegebene Postfächer**.

::: moniker-end
    
3. Wählen Sie auf der Seite **Freigegebene Postfächer****+ Postfach hinzufügen** aus. Geben Sie einen Namen für das freigegebene Postfach ein. Der Assistent wählt dann die E-Mail-Adresse aus, die Sie aber bearbeiten können.
    
    ![Geben Sie Ihrem freigegebenen Postfach einen Namen.](../../media/e3035132-8986-4ec7-b7c0-f2752080d2c0.png)
  
4. Klicken Sie auf **Hinzufügen**. Es kann ein paar Minuten dauern, bevor Sie Mitglieder hinzufügen können.

5. Wählen Sie unter **Nächste Schritte** die Option **Mitglieder zu diesem Postfach hinzufügen** aus. Mitglieder sind die Personen, denen ermöglich wird, die eingehenden E-Mails für dieses freigegebene Postfach und die ausgehenden Antworten anzuzeigen.

   ![Wählen Sie „Mitglieder hinzufügen“ aus](../../media/a2a72e3d-6170-40fe-a94f-0af8fbef8ab2.png)

6. Wählen Sie die Schaltfläche **+ Mitglieder hinzufügen** aus. Setzen Sie ein Häkchen neben diejenigen Personen, die dieses freigegebene Postfach nutzen sollen, und klicken Sie auf **Speichern**.

   ![Weisen Sie dem freigegebenen Postfach Mitglieder zu](../../media/e6c58953-f6d7-4f0b-97ba-308516bf2a94.png)

7. Wählen Sie **Schließen** aus.

Sie haben ein freigegebenes Postfach, das einen freigegebenen Kalender enthält. Fahren Sie jetzt mit dem nächsten Schritt fort: Blockieren der Anmeldung für das freigegebene Postfachkonto.

## <a name="block-sign-in-for-the-shared-mailbox-account"></a>Blockieren der Anmeldung für das freigegebene Postfachkonto

Zu jedem freigegebenen Postfach gehört ein entsprechendes Benutzerkonto. Haben Sie festgestellt, dass Sie beim Erstellen des freigegebenen Postfachs nicht zur Eingabe eines Kennworts aufgefordert wurden? Das Konto verfügt über ein Kennwort, das jedoch vom System generiert wurde (unbekannt). Sie sollten sich nicht mit dem Konto beim freigegebenen Postfach anmelden.

Doch was passiert, wenn ein Administrator einfach das Kennwort für das freigegebene Postfachbenutzerkonto zurücksetzt? Oder was passiert, wenn ein Angreifer Zugriff auf die Anmeldeinformationen des freigegebenen Postfachkontos erhält? Dies würde dem Benutzerkonto ermöglichen, sich beim freigegebenen Postfach anzumelden und eine E-Mail zu senden. Um dies zu verhindern, müssen Sie die Anmeldung für das Konto blockieren, das dem freigegebenen Postfach zugeordnet ist.

::: moniker range="o365-worldwide"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Aktive Benutzer</a>.

2. Suchen Sie in der Liste der Benutzerkonten nach dem Konto für das freigegebene Postfach (ändern Sie beispielsweise den Filter in **Nicht lizenzierte Benutzer**).

3. Wählen Sie den Benutzer aus, dessen Eigenschaftenbereich Sie öffnen möchten, und wählen Sie dann das Symbol **Diesen Benutzer blockieren** ![Screenshot des Symbols „Diesen Benutzer blockieren](../../media/block-user-icon.png).

   **Hinweis**: Wenn das Konto bereits blockiert ist, wird am oberen Rand **Anmeldung blockiert** angezeigt und das Symbol zeigt **Entsperren des Benutzers**.

4. Wählen Sie im Bereich **Diesen Benutzer blockieren?** **Benutzer für die Anmeldung blockieren** aus und wählen Sie dann **Änderungen speichern**.

::: moniker-end

::: moniker range="o365-germany"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847686" target="_blank">Aktive Benutzer</a>.

2. Suchen Sie in der Liste der Benutzerkonten nach dem Konto für das freigegebene Postfach (ändern Sie beispielsweise die Ansicht zu **Nicht lizenzierte Benutzer**) und wählen Sie dann das Konto aus.

3. Wählen Sie im Eigenschaften-Flyout **Anmeldung blockieren** aus.

    **Hinweis:** Wenn das Konto bereits blockiert wurde, zeigt die Schaltfläche **Anmeldung freigeben** an.

4. Vergewissern Sie sich, dass im Flyout-Menü **Anmeldestatus bearbeiten** die Option „Benutzer für die Anmeldung sperren“ aktiviert ist, wählen Sie **Speichern** und dann **Schließen** aus.

::: moniker-end

::: moniker range="o365-21vianet"

1. Wechseln Sie im Admin Center zu der Seite **Benutzer** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850628" target="_blank">Aktive Benutzer</a>.

2. Suchen Sie in der Liste der Benutzerkonten nach dem Konto für das freigegebene Postfach (ändern Sie beispielsweise die Ansicht zu **Nicht lizenzierte Benutzer**) und wählen Sie dann das Konto aus.

3. Wählen Sie im Eigenschaften-Flyout **Anmeldung blockieren** aus.

    **Hinweis:** Wenn das Konto bereits blockiert wurde, zeigt die Schaltfläche **Anmeldung freigeben** an.

4. Vergewissern Sie sich, dass im Flyout-Menü **Anmeldestatus bearbeiten** die Option „Benutzer für die Anmeldung sperren“ aktiviert ist, wählen Sie **Speichern** und dann **Schließen** aus.
::: moniker-end

Anweisungen dazu, wie Sie die-Anmeldung für-Konten mit Azure AD PowerShell (einschließlich vieler Konten gleichzeitig) blockieren können, finden Sie unter [Blockieren von Benutzerkonten mit Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/block-user-accounts-with-office-365-powershell).

## <a name="add-the-shared-mailbox-to-outlook"></a>Hinzufügen des freigegebenen Postfachs in Outlook

Wenn Sie in Ihrem Unternehmen die automatische Zuordnung aktiviert haben (wie es die meisten Benutzer standardmäßig tun), wird das freigegebene Postfach in der Outlook-App ihrer Benutzer automatisch angezeigt, nachdem sie Outlook geschlossen und erneut gestartet haben. 

Die automatische Zuordnung wird für das Postfach des Benutzers und nicht für das freigegebene Postfach festgelegt.   Dies bedeutet: Wenn Sie über eine Sicherheitsgruppe zu verwalten versuchen, wer auf das freigegebene Postfach zugreifen darf, funktioniert die automatische Zuordnung nicht. Deshalb müssen Sie zur Nutzung der automatischen Zuordnung Berechtigungen explizit zuweisen. Die automatische Zuordnung ist standardmäßig aktiviert. Informationen zum Deaktivieren dieser Option finden Sie unter [Entfernen der automatischen Zuordnung für ein freigegebenes Postfach](https://docs.microsoft.com/office365/troubleshoot/administration/remove-automapping-for-shared-mailbox).

Weitere Informationen zu in Outlook freigegebenen Postfächern finden Sie unter:

- <a href="https://support.microsoft.com/office/d94a8e9e-21f1-4240-808b-de9c9c088afd" target="_blank">Öffnen und Verwenden eines geteilten Postfachs in Outlook</a>

- <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Hinzufügen eines freigegebenen Postfachs zu Outlook im Web</a>

- <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Hinzufügen eines geteilten Postfachs zu Outlook Mobile</a>

- <a href="https://support.microsoft.com/office/6ecc39c5-5577-4a1d-b18c-bbdc92972cb2" target="_blank">Öffnen eines freigegebenen Ordners oder Postfachs in Outlook für Mac</a>

- <a href="https://support.microsoft.com/office/b0963400-2a51-4c64-afc7-b816d737d164" target="_blank">Hinzufügen von Regeln zu einem freigegebenen Postfach</a>


## <a name="use-a-shared-mailbox-on-a-mobile-device-phone-or-tablet"></a>Verwenden eines geteilten Postfachs auf einem mobilen Gerät (Smartphone oder Tablet)

Sie können auf ein geteiltes Postfach auf einem mobilen Gerät auf zweierlei Arten zuzugreifen:
- Fügen Sie das freigegebene Postfach in der <a href="https://apps.apple.com/us/app/microsoft-outlook/id951937596" target="_blank">Outlook für iOS-App</a> oder der <a href="https://play.google.com/store/apps/details?id=com.microsoft.office.outlook&hl=en_US" target="_blank">Outlook for Android Mobile-App</a> hinzu. 
    
    Die entsprechenden Anleitungen finden Sie unter <a href="https://support.microsoft.com/office/f866242c-81b2-472e-8776-6c49c5473c9f" target="_blank">Hinzufügen eines freigegebenen Postfachs zu Outlook Mobile</a>.

- Öffnen Sie Ihren Browser, melden Sie sich an und wechseln Sie dann zu Outlook im Web. Von Outlook im Web aus können Sie auf das freigegebene Postfach zugreifen.

    Die entsprechenden Anleitungen finden Sie unter <a href="https://support.microsoft.com/office/98b5a90d-4e38-415d-a030-f09a4cd28207" target="_blank">Hinzufügen eines freigegebenen Postfachs zu Outlook im Web</a>.
    
> [!NOTE]
> Das freigegebene Postfach kann nur zur Outlook für iOS-App oder zur mobilen Outlook für Android-App hinzugefügt werden.

## <a name="use-the-shared-calendar"></a>Verwenden des geteilten Kalenders

Beim Erstellen des freigegebenen Postfachs haben Sie automatisch einen freigegebenen Kalender erstellt. Wir verwenden bevorzugt den freigegebenen Kalender des Postfachs statt eines SharePoint-Kalenders zum Nachverfolgen von Terminen und des Aufenthaltsorts von Personen. Ein freigegebener Kalender ist in Outlook integriert und ist viel einfacher zu verwenden als ein SharePoint-Kalender.

1. Wechseln Sie in der Outlook-App zur Kalenderansicht und wählen Sie das freigegebene Postfach aus.

2. Wenn Sie Termine eingeben, kann diese jeder ansehen, der Mitglied des geteilten Postfachs ist.

3. Jedes Mitglied des geteilten Postfachs kann Termine im Kalender erstellen, sehen und verwalten, genau wie in seinem persönlichen Kalender. Jedes Mitglied des geteilten Postfachs kann Änderungen im freigegebenen Kalender sehen.

## <a name="related-articles"></a>Verwandte Artikel

[Informationen zu freigegebenen Postfächern](about-shared-mailboxes.md)

[Konfigurieren eines freigegebenen Postfachs](configure-a-shared-mailbox.md)

[Konvertieren eines Benutzerpostfachs in ein freigegebenes Postfach](convert-user-mailbox-to-shared-mailbox.md)

[Entfernen einer Lizenz aus einem freigegebenen Postfach](remove-license-from-shared-mailbox.md)

[Beheben von Problemen mit freigegebenen Postfächern](resolve-issues-with-shared-mailboxes.md)





