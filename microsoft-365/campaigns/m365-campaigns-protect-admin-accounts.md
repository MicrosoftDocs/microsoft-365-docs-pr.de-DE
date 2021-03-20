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
ms.openlocfilehash: ec5b971ba4f1fdc8834e10ddf90ff219f763f805
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912174"
---
# <a name="protect-your-administrator-accounts"></a>Schützen Ihrer Administratorkonten

Da Administratorkonten mit erhöhten Rechten verfügen, sind sie wertvolle Ziele für Hacker und Cyberkriminellen. Inhalt dieses Artikels

- Einrichten eines zusätzlichen Administratorkontos für Notfälle.
- So schützen Sie diese Konten.

Wenn Sie sich für Microsoft 365 registrieren und Ihre Informationen eingeben, werden Sie automatisch zum globalen Administrator. Ein globaler Administrator hat die ultimative Kontrolle über Benutzerkonten und alle anderen Einstellungen im Microsoft Admin Center, es gibt jedoch viele verschiedene Arten von Administratorkonten mit unterschiedlichem Zugriffsgrad. Informationen [zu den](/office365/admin/add-users/about-admin-roles) verschiedenen Zugriffsebenen für jede Art von Administratorrolle finden Sie unter Informationen zu Administratorrollen.

## <a name="create-additional-admin-accounts"></a>Erstellen zusätzlicher Administratorkonten

Verwenden Sie Administratorkonten nur für die Verwaltung. Administratoren sollten über ein separates Benutzerkonto für die regelmäßige Verwendung von Office-Apps verfügen und ihr Administratorkonto nur verwenden, wenn dies erforderlich ist, um Konten und Geräte zu verwalten und andere Administratorfunktionen zu verwenden. Es empfiehlt sich auch, die Microsoft 365-Lizenz aus den Administratorkonten zu entfernen, damit Sie nicht dafür bezahlen müssen.

Sie möchten mindestens ein zusätzliches globales Administratorkonto einrichten, um Administratoren Zugriff auf einen anderen vertrauenswürdigen Mitarbeiter zu geben. Sie können auch separate Administratorkonten für die Benutzerverwaltung erstellen (diese Rolle wird **als Benutzerverwaltungsadministrator bezeichnet).** Weitere Informationen finden Sie unter [Über Administratorrollen](/office365/admin/add-users/about-admin-roles).

So erstellen Sie zusätzliche Administratorkonten:

 1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Admin Center,</a> und wählen Sie dann **Benutzer** \> **Aktive Benutzer** im linken Navigationsgerät aus.

    ![Wählen Sie Benutzer und dann Aktive Benutzer im linken Navigationsgerät aus.](../media/Activeusers.png)

 2. Wählen Sie **auf der** Seite Aktive Benutzer oben auf der  Seite Benutzer hinzufügen aus, und geben Sie im Bereich Neuer Benutzer den Namen und weitere Informationen ein. 
 3. Erweitern Sie den **Abschnitt Rollen,** und wählen Sie **Globaler Administrator aus,** um diesem Benutzer globalen Administratorzugriff zu geben. Sie können auch **angepassten Administrator auswählen** und eine der angezeigten Rollen auswählen.

    Geben Sie eine alternative E-Mail in das **Textfeld Alternative E-Mail-Adresse** ein. Sie können diese Adresse verwenden, um Ihre Kennwortinformationen wiederhergestellt zu werden, wenn Sie gesperrt werden. Für globale Administratoren wird auch eine Abrechnung an diese Adresse gesendet.

    ![Auswählen der Administratorrolle](../media/adminroles.png)

 4. Verschieben Sie **im** Abschnitt Produktlizenzen den Selektor für **Microsoft 365 Business** auf **Aus** und den Benutzer ohne **Produktlizenz** erstellen auf **Ein**.

    ![Auswählen der Produktlizenz](../media/productlicense.png)

## <a name="create-an-emergency-admin-account"></a>Erstellen eines Notfalladministratorkontos

Sie sollten auch ein Sicherungskonto erstellen, das nicht mit mehrstufiger Authentifizierung (MFA) eingerichtet ist, damit Sie sich nicht versehentlich sperren (z. B. wenn Sie Ihr Telefon verlieren, das Sie als zweite Form der Überprüfung verwenden). Stellen Sie sicher, dass das Kennwort für dieses Konto ein Ausdruck oder mindestens 16 Zeichen lang ist. Dies wird häufig als "Break-Glass-Konto" bezeichnet.

## <a name="create-a-user-account-for-yourself"></a>Erstellen eines Benutzerkontos für sich selbst

Verwenden Sie Ihr Benutzerkonto, um an der Zusammenarbeit mit Ihrer Organisation teilzunehmen, einschließlich der Überprüfung von E-Mails. Dies bedeutet, dass Ihre Administratoranmeldeinformationen möglicherweise *Alice.Chavez <span></span> @Contoso.org* ähneln und Ihr reguläres Benutzerkonto *alice <span></span> @Contoso.com .*

So erstellen Sie ein neues Benutzerkonto:

1. Wechseln Sie zum <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">Admin Center,</a> und wählen Sie dann **Benutzer** \> **Aktive Benutzer** im linken Navigationsgerät aus.
2. Wählen Sie **auf der** Seite Aktive Benutzer oben auf der  Seite Benutzer hinzufügen aus, und geben Sie im Bereich Neuer Benutzer den Namen und weitere Informationen ein. 
3. Erweitern Sie den **Abschnitt Rollen,** und wählen **Sie Benutzer (kein Administratorzugriff) aus.**
4. Verschieben Sie **im Abschnitt** Produktlizenzen die Auswahl für **Microsoft 365 Business** auf **Ein**.

## <a name="register-each-of-these-accounts-for-multi-factor-authentication"></a>Registrieren jedes dieser Konten für die mehrstufige Authentifizierung

Stellen Sie sicher, dass diese Konten die [mehrstufige Authentifizierung verwenden.](m365-campaigns-multifactor-authenication.md)

## <a name="additional-recommendations"></a>Zusätzliche Empfehlungen

- Stellen Sie sicher, dass Administratorkonten auch für die mehrstufige Authentifizierung eingerichtet sind. Wir zeigen Ihnen, wie Sie dies tun können, unter [Configure conditional access policies](m365-campaigns-conditional-access.md).
- Schließen Sie vor der Verwendung von Administratorkonten alle nicht zusammenhängenden Browsersitzungen und Apps, einschließlich persönlicher E-Mail-Konten. Sie können sie auch in privaten oder inkognito-Browserfenstern verwenden.
- Achten Sie nach Abschluss der Administratoraufgaben darauf, sich von der Browsersitzung abmelden.