---
title: Schützen Ihrer Administratorkonten
ms.author: sirkkuw
author: sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-Campaigns
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Erfahren Sie, wie Sie Ihre Administratorkonten einrichten und schützen.
ms.openlocfilehash: 857c24ac0ec134e119b3de083afe8dc3269bdbe2
ms.sourcegitcommit: c452413dff5d5388c9725f38871246237c313e65
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/22/2019
ms.locfileid: "35183306"
---
# <a name="protect-your-administrator-accounts"></a>Schützen Ihrer Administratorkonten

Da die Administratorkonten mit erhöhten Rechten ausgestattet sind, sind Sie wertvolle Ziele für Hacker und Cyber-Kriminelle. Inhalt dieses Artikels

- Einrichten eines zusätzlichen Administratorkontos für Notfälle.
- Wie diese Konten geschützt werden.
 
Wenn Sie sich für Microsoft 365 Business registrieren und Ihre Informationen eingeben, werden Sie automatisch zum globalen Administrator. Ein globaler Administrator hat die ultimative Kontrolle über Benutzerkonten und alle anderen Einstellungen im Microsoft Admin Center, aber es gibt viele verschiedene Arten von Administratorkonten mit unterschiedlichem Zugriffs Grad. Unter Informationen zu [Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) finden Sie Informationen zu den verschiedenen Zugriffsebenen für jede Art von Administratorrolle.


## <a name="create-additional-admin-accounts"></a>Erstellen zusätzlicher Administratorkonten

Verwenden Sie Administratorkonten nur für die Verwaltung. Administratoren sollten über ein separates Benutzerkonto für die regelmäßige Verwendung von Office-Apps verfügen und nur dann Ihr Administratorkonto verwenden, wenn es erforderlich ist, um Konten, Geräte und während der Arbeit an anderen Verwaltungsfunktionen zu verwalten.  Es empfiehlt sich auch, die Microsoft 365 Business License aus den Administratorkonten zu entfernen, damit Sie nicht dafür bezahlen müssen.

Sie möchten mindestens ein zusätzliches globales Administratorkonto einrichten, um Administratorzugriff auf einen anderen vertrauenswürdigen Mitarbeiter zu erhalten. Sie können auch separate Administratorkonten für die Benutzerverwaltung erstellen (diese Rolle wird als **Benutzer Verwaltungs Administrator**bezeichnet). Weitere Informationen finden Sie unter Informationen [zu Administratorrollen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) .

So erstellen Sie zusätzliche Administratorkonten:

 1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Admin Center</a> , und wählen Sie dann **Benutzer** \> **aktive Benutzer** im linken Navigationsbereich aus.

    ![Wählen Sie Benutzer und dann aktive Benutzer im linken Navigationsbereich aus.](media/Activeusers.png)

2. Wählen Sie auf der Seite **aktive Benutzer** die Option **Benutzer hinzufügen** oben auf der Seite aus, und geben Sie im Bereich **neuer Benutzer** den Namen und andere Informationen ein.
3. Erweitern Sie den Abschnitt **Rollen** , und wählen Sie **globaler Administrator** aus, um diesem Benutzer den globalen Administratorzugriff zu gewähren. Sie können auch **benutzerdefinierten Administrator** auswählen und eine der Rollen auswählen, die angezeigt werden.

    Geben Sie eine Alternative e-Mail in das Textfeld Alternative e-Mail-Adresse ein. Sie können diese Adresse verwenden, um Ihre Kennwortinformationen wiederherzustellen, wenn Sie gesperrt werden. Für globale Administratoren wird auch eine Abrechnungs Anweisung an diese Adresse gesendet.

    ![Auswählen der Administratorrolle](media/adminroles.png)
    
4. Stellen Sie im Abschnitt **Produktlizenzen** den Selektor für **Microsoft 365 Business** auf **aus** , und legen Sie den **Benutzer ohne Produktlizenz** auf **ein**.

    ![Produktlizenz auswählen](media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Erstellen eines Notfall Administratorkontos

Sie sollten auch ein sicherungskonto erstellen, das nicht mit mehrstufiger Authentifizierung (Multi-Factor Authentication, MFA) eingerichtet ist, damit Sie sich nicht versehentlich selbst verschließen (beispielsweise wenn Sie Ihr Telefon verlieren, das Sie als Sekunde von der Überprüfung verwenden). Stellen Sie sicher, dass das Kennwort für dieses Konto ein Ausdruck oder mindestens 16 Zeichen lang ist. Dies wird häufig als "Break-Glass-Konto" bezeichnet.

## <a name="create-a-user-account-for-yourself"></a>Erstellen eines Benutzerkontos für sich selbst

Verwenden Sie Ihr Benutzerkonto, um an der Zusammenarbeit mit Ihrer Organisation teilzunehmen, einschließlich der Überprüfung von e-Mails. Das heißt, Ihre Administratoranmeldeinformationen ähneln möglicherweise *Alice. Chavez<span></span>@contoso. org* , und Ihr reguläres Benutzerkonto ähnelt *Alice<span></span>@contoso. com*.

So erstellen Sie ein neues Benutzerkonto:
1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Admin Center</a> , und wählen Sie dann **Benutzer** \> **aktive Benutzer** im linken Navigationsbereich aus.
2. Wählen Sie auf der Seite **aktive Benutzer** die Option **Benutzer hinzufügen** oben auf der Seite aus, und geben Sie im Bereich **neuer Benutzer** den Namen und andere Informationen ein.
3. Erweitern Sie den Abschnitt **Rollen** , und wählen Sie **Benutzer (kein Administratorzugriff)** aus.
1. Stellen Sie im Abschnitt **Produktlizenzen** den Selektor für **Microsoft 365 Business** auf **ein**. 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Registrieren jedes dieser Konten für mehrstufige Authentifizierung


## <a name="additional-recommendations"></a>Weitere Empfehlungen

- Stellen Sie sicher, dass auch Administratorkonten für die mehrstufige Authentifizierung eingerichtet sind. In diesem Artikel erfahren Sie, wie Sie die [Richtlinien für bedingten Zugriff konfigurieren](m365-campaigns-conditional-access.md).
- Schließen Sie vor der Verwendung von Administratorkonten alle nicht verwandten Browsersitzungen und apps, einschließlich persönlicher e-Mail-Konten. Sie können auch in privaten oder inkognito-Browserfenstern verwenden.
- Nachdem Sie die Administratoraufgaben abgeschlossen haben, müssen Sie sich bei der Browsersitzung abmelden.