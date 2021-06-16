---
title: Verwalten, welche Office Features in "Neuigkeiten" angezeigt werden
f1.keywords:
- NOCSH
ms.author: danbrown
author: DHB-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Entscheiden Sie, welche Office Features angezeigt oder ausgeblendet werden sollen, wenn ein Benutzer die Hilfe > Neuigkeiten in seiner Office-App auf Windows mithilfe des Features "Neuigkeiten in Office" im Microsoft 365 Admin Center auswählt.
ms.openlocfilehash: 395038bebda407771802a61ba5aefc350c7c5cd1
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929479"
---
# <a name="manage-which-office-features-appear-in-whats-new"></a>Verwalten, welche Office Features in "Neuigkeiten" angezeigt werden

Wenn eine wichtige Office-Funktion veröffentlicht wird, erhalten Benutzer eine Meldung darüber, wenn sie  >  in ihrer Office-App auf Windows "Help **What's New"** auswählen.

Sie können steuern, welche dieser Featurenachrichten Ihren Benutzern angezeigt werden, indem Sie das Feature **"Neuigkeiten in Office"** im Microsoft 365 Admin Center verwenden. Wenn Sie eine Featurenachricht für Ihre Benutzer ausblenden möchten, können Sie später jederzeit zurückkehren und sie ihnen anzeigen.

> [!NOTE]
> - Wenn Sie eine Featurenachricht von Ihren Benutzern ausblenden, wird das Feature im Office-App nicht deaktiviert.
> - Ihnen muss entweder die Globale Administratorrolle oder die Administratorrolle Office Apps zugewiesen werden, um das Feature **"Neuigkeiten in Office"** zu verwenden.

## <a name="show-or-hide-new-features"></a>Ein- oder ausblenden neuer Funktionen 

1. Wählen Sie im Microsoft 365 Admin Center unter **Einstellungen** **Organisationseinstellungen** aus.
2. Wählen Sie auf der Registerkarte **"Dienste"** die Option **"Neuigkeiten in Office"** aus.
3. Wenn Sie auf den Featurenamen klicken, wird ein Flyout-Bereich mit den folgenden Informationen angezeigt:
     - Eine kurze Beschreibung des Features.
     - Ein Link zu einem Artikel, um mehr über das Feature zu erfahren.
     - Die Office Anwendungen, in denen das Feature angezeigt wird.
     - Die erste Version (Version), in der das Feature für diesen Kanal verfügbar ist.
4. Choose **Hide from users**. Wenn Sie das Feature zuvor ausgeblendet haben, wählen Sie **"Benutzern anzeigen" aus.**

Sie können auch mehrere Features auf der Seite **"Verwalten" auswählen, welche Office Features auf** der Seite "Neuigkeiten" angezeigt werden, und dann entweder **"Ausblenden"** oder **"Anzeigen"** auswählen.

> [!NOTE]
> - Wenn ein Feature in mehreren Office Apps verfügbar ist, blendet das Festlegen des Features auf **"Ausgeblendet"** die Featuremeldung in allen Office Apps aus.
> - Alle Featuremeldungen werden Benutzern standardmäßig angezeigt. Dies ist der Standardstatus für alle Features, und der Status ändert sich nur, wenn Sie sich entschieden haben, eine Featurenachricht auszublenden oder anzuzeigen.
> - Sie können auch das Feature **"Neuigkeiten in Office"** im Microsoft 365 Apps Admin Center ( [https://config.office.com](https://config.office.com) ) aufrufen. Das Feature befindet sich unter **Anpassung**  >  **der neuen Verwaltung.**

## <a name="list-of-features"></a>Liste der Features

Sie können filtern, welche Features auf der Seite **"Verwalten" angezeigt werden, welche Office Features auf der Seite "Neuigkeiten" angezeigt werden.** Sie können nach Kanal, Anwendung oder Status oder nach einer Kombination aus diesen filtern.

Neue Features werden auf der Seite basierend auf dem folgenden Zeitplan angezeigt:

|Kanal|Datum|Maßnahmen ergreifen|
|:-----|:-----|:-----|
|**Current** <br/> |15. des Monats  <br/> |1 bis 3 Wochen vor der monatlichen Veröffentlichung <br/> |
|**Monatlicher Enterprise-Kanal** <br/> |Erster Des Monats  <br/> |Zwei Wochen vor der Hauptversion mit neuen Features |
|**Halbjährlicher Enterprise (Vorschau)** <br/> |1. September und 1. März <br/> | 2 Wochen vor der Hauptversion mit neuen Features|
|**Semi-Annual Enterprise** <br/> |1. Januar und 1. Juli <br/> | 2 Wochen vor der Hauptversion mit neuen Features<br/> |

Weitere Informationen dazu, wann neue Versionen für jeden Updatekanal veröffentlicht werden, finden Sie unter [Updateverlauf für Microsoft 365 Apps (nach Datum aufgelistet).](/officeupdates/update-history-microsoft365-apps-by-date)

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a>Hinzufügen der Karte "Neuigkeiten in Office" zur Admin Center-Startseite

1. On the Microsoft 365 admin page, choose **Add card** on top of the page
2. Suchen **Sie verwalten, welche Office Features in "Neuigkeiten"** in der Liste angezeigt werden, und wählen Sie sie aus.
3. Sobald sich die Karte auf Ihrer Startseite befindet, können Sie **"Neuigkeiten" in Office** auswählen, um die Features für Ihre Organisation [ein- oder auszublenden.](#show-or-hide-new-features)


## <a name="related-articles"></a>Verwandte Artikel

[Office What's New management is now generally available](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)
