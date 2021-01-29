---
title: Schützen Ihrer Administratorkonten
f1.keywords:
- NOCSH
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
- m365solution-smb
ms.custom:
- Adm_O365
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
description: Erfahren Sie, wie Sie Ihre Administratorkonten einrichten und schützen.
ms.openlocfilehash: 73e4b69571b1e1d0a4d1585224fe256ff135c40a
ms.sourcegitcommit: 1b30ac6e05906c8a014b1fed33fc71e1821f6ad2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/29/2021
ms.locfileid: "50044488"
---
# <a name="protect-your-administrator-accounts"></a>Schützen Ihrer Administratorkonten

Da Administratorkonten mit erhöhten Rechten verfügen, sind sie wertvolle Ziele für Hacker und Cyberkriminellen. Inhalt dieses Artikels

- Einrichten eines zusätzlichen Administratorkontos für Notfälle.
- Informationen zum Schützen dieser Konten.

Wenn Sie sich für Microsoft 365 registrieren und Ihre Informationen eingeben, werden Sie automatisch globaler Administrator. Ein globaler Administrator hat die ultimative Kontrolle über Benutzerkonten und alle anderen Einstellungen im Microsoft Admin Center, aber es gibt viele verschiedene Arten von Administratorkonten mit unterschiedlichem Zugriffsgrad. Informationen [zu den verschiedenen Zugriffsebenen](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles) für jede Art von Administratorrolle finden Sie unter Administratorrollen.

## <a name="create-additional-admin-accounts"></a>Erstellen zusätzlicher Administratorkonten

Verwenden Sie Administratorkonten nur für die Verwaltung. Administratoren sollten über ein separates Benutzerkonto für die regelmäßige Verwendung von Office-Apps verfügen und ihr Administratorkonto nur bei Bedarf verwenden, um Konten und Geräte zu verwalten und gleichzeitig an anderen Administratorfunktionen zu arbeiten. Es ist auch eine gute Idee, die Microsoft 365-Lizenz aus den Administratorkonten zu entfernen, damit Sie nicht dafür bezahlen müssen.

Sie sollten mindestens ein zusätzliches globales Administratorkonto einrichten, um einem anderen vertrauenswürdigen Mitarbeiter Administratorzugriff zu geben. Sie können auch separate Administratorkonten für die Benutzerverwaltung erstellen (diese Rolle wird als **Benutzerverwaltungsadministrator bezeichnet).** Weitere Informationen finden Sie unter ["Administratorrollen".](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)

So erstellen Sie zusätzliche Administratorkonten:

 1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Admin Center,</a> und wählen Sie **im** linken Navigationsbereich "Aktive \>  Benutzer" aus.

    ![Choose Users and then Active users in the left nav](../media/Activeusers.png)

 2. Wählen Sie **oben auf der** Seite "Aktive Benutzer" die  Option "Benutzer hinzufügen" aus, und geben Sie im Bereich "Neuer Benutzer" den Namen und weitere Informationen ein. 
 3. Erweitern Sie den **Abschnitt** "Rollen", und wählen Sie **"Globaler Administrator" aus,** um diesem Benutzer globalen Administratorzugriff zu geben. Sie können auch einen **angepassten Administrator auswählen** und eine der angezeigten Rollen auswählen.

    Geben Sie eine alternative E-Mail in das **Textfeld "Alternative E-Mail-Adresse"** ein. Sie können diese Adresse verwenden, um Ihre Kennwortinformationen wiederhergestellt, wenn Sie gesperrt werden. Für globale Administratoren wird auch eine Rechnung an diese Adresse gesendet.

    ![Auswählen der Administratorrolle](../media/adminroles.png)

 4. Verschieben Sie im Abschnitt "Produktlizenzen" den Selektor für **Microsoft 365 Business** in **"Aus"** und "Benutzer ohne **Produktlizenz erstellen"** auf **"Ein".** 

    ![Auswählen der Produktlizenz](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Erstellen eines Administratorkontos für Den Notfall

Sie sollten auch ein Sicherungskonto erstellen, das nicht mit mehrstufiger Authentifizierung (Multi-Factor Authentication, MFA) eingerichtet ist, damit Sie sich nicht versehentlich sperren (z. B. wenn Sie Ihr Telefon verlieren, das Sie als zweite Überprüfungsmethode verwenden). Stellen Sie sicher, dass das Kennwort für dieses Konto ein Ausdruck oder mindestens 16 Zeichen lang ist. Dies wird häufig als "Break-Glass-Konto" bezeichnet.

## <a name="create-a-user-account-for-yourself"></a>Erstellen eines Benutzerkontos für sich selbst

Verwenden Sie Ihr Benutzerkonto, um an der Zusammenarbeit mit Ihrer Organisation teilzunehmen, einschließlich der E-Mail-Überprüfung. Dies bedeutet, dass Ihre Administratoranmeldeinformationen *alice.Chavez <span></span> @Contoso.org* und Ihr reguläres Benutzerkonto *alice <span></span> @Contoso.com ähnelt.*

So erstellen Sie ein neues Benutzerkonto:

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Admin Center,</a> und wählen Sie **im** linken Navigationsbereich "Aktive \>  Benutzer" aus.
2. Wählen Sie **oben auf der** Seite "Aktive Benutzer" die  Option "Benutzer hinzufügen" aus, und geben Sie im Bereich "Neuer Benutzer" den Namen und weitere Informationen ein. 
3. Erweitern Sie den **Abschnitt** "Rollen", und wählen **Sie "Benutzer" (kein Administratorzugriff) aus.**
4. Verschieben Sie im Abschnitt "Produktlizenzen" den Selektor für **Microsoft 365 Business** in **"Ein".** 

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Registrieren Sie jedes dieser Konten für die mehrstufige Authentifizierung.

Stellen Sie sicher, dass diese Konten die [mehrstufige Authentifizierung verwenden.](m365-campaigns-multifactor-authenication.md)

## <a name="additional-recommendations"></a>Zusätzliche Empfehlungen

- Stellen Sie sicher, dass Administratorkonten auch für die mehrstufige Authentifizierung eingerichtet sind. Dies wird in "Konfigurieren von Richtlinien für bedingten [Zugriff" gezeigt.](m365-campaigns-conditional-access.md)
- Schließen Sie vor der Verwendung von Administratorkonten alle nicht verbundenen Browsersitzungen und Apps, einschließlich persönlicher E-Mail-Konten. Sie können sie auch in privaten oder inkognito-Browserfenstern verwenden.
- Achten Sie darauf, dass Sie sich nach Abschluss der Administratoraufgaben von der Browsersitzung abmelden.
