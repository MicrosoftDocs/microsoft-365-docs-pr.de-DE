---
title: "Manage which Office features appear in What's New" f1.keywords:
- NOCSH ms.author: danbrown author: DHB-MSFT manager: scotv audience: Admin ms.topic: article ms.service: o365-administration localization_priority: Normal ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC ms.custom: AdminSurgePortfolio search.appverid:
- BCS160
- MET150
- MOE150 description: "Decide which Office features to show or hide when a user chooses Help > What's New in their Office app on Windows by using the "What's new in Office" feature in the Microsoft 365 admin center."
---

# <a name="manage-which-office-features-appear-in-whats-new"></a>Verwalten, welche Office-Features in "Was ist neu" angezeigt werden

Wenn ein wichtiges Office-Feature veröffentlicht wird, erhalten Benutzer eine Meldung darüber, wenn sie in ihrer Office-App unter Windows "Hilfe  >  **what's New"** auswählen.

Sie können steuern, welche dieser Featuremeldungen Ihren Benutzern angezeigt werden, indem Sie das Feature "Neues **in Office"** im Microsoft 365 Admin Center verwenden. Wenn Sie eine Featurenachricht für Ihre Benutzer ausblenden möchten, können Sie jederzeit später wiederkommen und sie für sie anzeigen.

> [!NOTE]
> - Wenn Sie eine Featurenachricht für Ihre Benutzer ausblenden, wird das Feature in der Office-App nicht deaktiviert.
> - Ihnen muss entweder die rolle "Globaler Administrator" oder die Administratorrolle "Office-Apps" zugewiesen sein, um das Feature "Neues **in Office" verwenden zu** können.

## <a name="show-or-hide-new-features"></a>Ein- oder ausblenden neuer Funktionen 

1. Wählen Sie im Microsoft 365 Admin Center unter **"Einstellungen"** die **Organisationseinstellungen aus.**
2. Wählen Sie **auf der** Registerkarte "Dienste" die **Option "Neues in Office" aus.**
3. Wenn Sie auf den Featurenamen klicken, wird ein Flyoutbereich mit den folgenden Informationen angezeigt:
     - Eine kurze Beschreibung des Features.
     - Ein Link zu einem Artikel, um mehr über das Feature zu erfahren.
     - Die Office-Anwendungen, in der das Feature angezeigt wird.
     - Die erste Version (Version), in der das Feature für den Kanal verfügbar ist.
4. Choose **Hide from users**. Wenn Sie das Feature zuvor verborgen haben, wählen Sie **"Für Benutzer anzeigen" aus.**

Sie können auf der  Seite "Neu" auch mehrere Features auf der Seite "Office-Features verwalten" auswählen und dann "Ausblenden" **oder** **"Einblenden" auswählen.**

> [!NOTE]
> - Wenn ein Feature in mehreren Office-Apps verfügbar ist, blendet das Festlegen des Features auf **"Ausgeblendet"** die Featuremeldung in allen diesen Office-Apps aus.
> - Alle Featuremeldungen werden Benutzern standardmäßig angezeigt. Dies ist der Standardstatus für alle Features, und der Status ändert sich nur, wenn Sie eine Featuremeldung ausblenden oder anzeigen möchten.
> - Sie können das Feature "Neues **in Office"** auch über das Microsoft 365 Apps Admin Center ( ) [https://config.office.com](https://config.office.com) nutzen. Das Feature befindet sich unter **"Customization**  >  **What's New Management".**

## <a name="list-of-features"></a>Liste der Features

Sie können filtern, welche Features auf der Seite "Neu verwalten" angezeigt **werden.** Sie können nach Kanal, Anwendung oder Status oder nach einer kombination filtern.

Neue Features werden auf der Seite basierend auf dem folgenden Zeitplan angezeigt:

||||
|:-----|:-----|:-----|
|**Kanal** <br/> |**Date** <br/> |**Ergreifen von Maßnahmen** <br/> |
|**Current** <br/> |15. des Monats  <br/> |1 - 3 Wochen vor der monatlichen Version <br/> |
|**Monatlicher Enterprise-Kanal** <br/> |Monatserstes  <br/> |Zwei Wochen vor der Hauptversion mit neuen Features |
|**Semi-Annual Enterprise (Vorschau)** <br/> |1. September und 1. März <br/> | 2 Wochen vor der Hauptversion, die neue Features bietet|
|**Semi-Annual Enterprise** <br/> |1. Januar und 1. Juli <br/> | 2 Wochen vor der Hauptversion, die neue Features bietet<br/> |

Weitere Informationen dazu, wann neue Versionen für jeden Updatekanal veröffentlicht werden, finden Sie im Updateverlauf für [Microsoft 365-Apps (nach Datum aufgeführt).](https://docs.microsoft.com/officeupdates/update-history-microsoft365-apps-by-date)

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a>Hinzufügen der Karte "Neues in Office" zur Admin Center-Startseite

1. On the Microsoft 365 admin page, choose **Add card** on top of the page
2. Suchen **Sie, welche Office-Features in der** Liste "Neu" angezeigt werden, und wählen Sie sie aus.
3. Sobald sich die Karte auf Ihrer Startseite befindet, können [](#show-or-hide-new-features) Sie "Neues **in Office"** auswählen, um die Features für Ihre Organisation ein- oder auszublenden.


## <a name="related-articles"></a>Verwandte Artikel

[Office What's New management is now generally available](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)