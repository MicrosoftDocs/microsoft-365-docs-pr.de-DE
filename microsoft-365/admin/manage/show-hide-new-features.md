---
title: Manage which ‎Office‎ features appear in What's New
f1.keywords:
- NOCSH
ms.author: danbrown
author: DHB-MSFT
manager: scotv
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
description: Entscheiden Sie, welche Office-Features angezeigt oder ausgeblendet werden, wenn ein Benutzer hilfe > Was ist neu in ihrer Office-App unter Windows mithilfe der Funktion "Neues in Office" im Microsoft 365 Admin Center.
ms.openlocfilehash: b9d20e3df4a2de540316dce0e6a6905c07e65176
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915027"
---
# <a name="manage-which-office-features-appear-in-whats-new"></a>Manage which Office‎ features appear in What's New

When an important ‎Office‎ feature is released, users will get a message about it when they choose **Help**  >  **What's New** in their ‎‎Office‎‎ app on ‎Windows‎.

Sie können steuern, welche dieser Featuremeldungen Ihren Benutzern angezeigt werden, indem Sie das Feature Neues **in Office** im Microsoft 365 Admin Center verwenden. Wenn Sie entscheiden, eine Featurenachricht für Ihre Benutzer auszublenden, können Sie immer zu einem späteren Zeitpunkt wiederkommen und sie ihnen anzeigen.

> [!NOTE]
> - Wenn Sie eine Featurenachricht vor Ihren Benutzern ausblenden, wird das Feature in der Office-App nicht deaktiviert.
> - Sie müssen entweder der Globalen Administratorrolle oder der Administratorrolle office apps zugewiesen sein, um das **Feature Neues in Office verwenden zu** können.

## <a name="show-or-hide-new-features"></a>Ein- oder ausblenden neuer Funktionen 

1. Wählen Sie im Microsoft 365 Admin Center unter **Einstellungen** die Option **Organisationseinstellungen aus.**
2. Wählen Sie **auf der** Registerkarte Dienste die Option Neues in **Office aus.**
3. Wenn Sie auf den Featurenamen klicken, wird ein Fly-Out-Bereich mit den folgenden Informationen angezeigt:
     - Eine kurze Beschreibung des Features.
     - Ein Link zu einem Artikel, um mehr über das Feature zu erfahren.
     - Die Office-Anwendungen, in der das Feature angezeigt wird.
     - Die erste Version (Version), in der das Feature für den Kanal verfügbar ist.
4. Wählen **Sie Ausblenden von Benutzern aus.** Wenn Sie das Feature zuvor verborgen haben, wählen Sie **Benutzer anzeigen aus.**

You can also select multiple features on the **Manage which ‎Office‎ features appear in What's New** page, and then choose either **Hide** or **Show**.

> [!NOTE]
> - Wenn ein Feature in mehreren Office-Apps verfügbar ist, blendet das Festlegen des Features auf **Ausgeblendet** die Featurenachricht in allen diesen Office-Apps aus.
> - Alle Featurenachrichten werden Benutzern standardmäßig angezeigt. Dies ist der Standardstatus für alle Features, und der Status ändert sich nur, wenn Sie eine Featurenachricht ausblenden oder anzeigen möchten.
> - Sie können auch über das Microsoft 365 Apps Admin Center ( ) auf das Feature Neues **in Office** [https://config.office.com](https://config.office.com) zugreifen. Das Feature finden Sie unter **Customization**  >  **What's New Management**.

## <a name="list-of-features"></a>Liste der Features

You can filter which features appear on the **Manage which ‎Office‎ features appear in What's New** page. Sie können nach Kanal, Anwendung oder Status oder nach einer Kombination von filtern.

Neue Features werden basierend auf dem folgenden Zeitplan auf der Seite angezeigt:

||||
|:-----|:-----|:-----|
|**Kanal** <br/> |**Date** <br/> |**Maßnahmen ergreifen** <br/> |
|**Current** <br/> |15. des Monats  <br/> |1 bis 3 Wochen vor der monatlichen Veröffentlichung <br/> |
|**Monatlicher Enterprise-Kanal** <br/> |Erstes des Monats  <br/> |Zwei Wochen vor der Hauptversion, die neue Features bietet |
|**Semi-Annual Enterprise (Preview)** <br/> |1. September und 1. März <br/> | 2 Wochen vor der Hauptversion, die neue Features bietet|
|**Semi-Annual Enterprise** <br/> |1. Januar und 1. Juli <br/> | 2 Wochen vor der Hauptversion, die neue Features bietet<br/> |

Weitere Informationen zum Zeitpunkt der Veröffentlichung neuer Versionen für jeden Updatekanal finden Sie unter [Updateverlauf für Microsoft 365 Apps (nach Datum aufgeführt).](/officeupdates/update-history-microsoft365-apps-by-date)

## <a name="add-the-whats-new-in-office-card-to-the-admin-center-home-page"></a>Hinzufügen der Karte "Neues in Office" zur Admin Center-Homepage

1. Wählen Sie auf der Seite Microsoft 365 Admin die Option Karte **hinzufügen** oben auf der Seite aus.
2. Suchen **Sie verwalten, welche Office-Features in What's New** in der Liste angezeigt werden, und wählen Sie sie aus.
3. Sobald sich die Karte auf Ihrer Homepage befindet, können Sie in **Office** Neues auswählen, um die Features für [Ihre](#show-or-hide-new-features) Organisation ein- oder auszublenden.


## <a name="related-articles"></a>Verwandte Artikel

[Office What's New Management ist jetzt allgemein verfügbar](https://techcommunity.microsoft.com/t5/microsoft-365-blog/office-what-s-new-management-is-now-generally-available/ba-p/1179954)