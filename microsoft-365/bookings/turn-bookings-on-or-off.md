---
title: Microsoft Bookings an- oder ausschalten
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Erfahren Sie, wie Sie zugriff auf Microsoft Bookings in Microsoft 365 erhalten.
ms.openlocfilehash: 7b1582a480ac4fdcd5a131febcc59450aa13e299
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913766"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Microsoft Bookings an- oder ausschalten

Buchungen können für Ihre gesamte Organisation oder für bestimmte Benutzer aktiviert oder deaktiviert werden. Wenn Sie Bookings für Benutzer aktivieren, können sie eine Bookings-Seite erstellen, einen Kalender erstellen und anderen Personen erlauben, Zeit mit ihnen zu reservieren.

> [!NOTE]
> Die in diesen Abschnitten beschriebenen Administratorsteuerelemente sind für Office 365 Operated by 21Vianet (China)-Kunden nicht verfügbar.

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Aktivieren oder Deaktivieren von Bookings für Ihre Organisation mithilfe des Microsoft 365 Admin Centers

1. Melden Sie sich beim Microsoft 365 Admin Center als globaler Administrator an.

2. Wechseln Sie im Admin Center zu  **Einstellungen**   \> **Organisationseinstellungen,** und wählen Sie **Bookings aus.**

3. Aktivieren Sie das Kontrollkästchen **Zulassen, dass Ihre Organisation Bookings zum** Aktivieren oder Deaktivieren von Bookings für Ihre Organisation verwendet.

   > [!NOTE]
   > Wenn Sie Bookings deaktivieren, wird der Zugriff auf den Dienst deaktiviert, einschließlich der Erstellung und Verwaltung von Bookings-Seiten.

4. Wählen **Sie Änderungen speichern aus.**

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Aktivieren oder Deaktivieren von Bookings für Ihre Organisation mithilfe von PowerShell

Um Bookings für Ihre Organisation mit dem PowerShell-Cmdlet [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig)zu aktivieren oder zu deaktivieren, stellen Sie eine Verbindung mit [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell) auf, und führen Sie den folgenden Befehl aus:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Aktivieren oder Deaktivieren von Bookings für einzelne Benutzer

Sie können Bookings für einzelne Benutzer deaktivieren.

1. Wechseln Sie zum Microsoft 365 Admin Center, und wählen Sie **dann Benutzer** Aktive \> **Benutzer aus.**

1. Wählen Sie den gewünschten Benutzer aus, und wählen Sie **dann Lizenzen und Apps aus.**

1. Erweitern **Sie Apps,** und aktivieren Sie das Kontrollkästchen für Microsoft Bookings.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Vor der Freigabe von Frei/Gebucht-Informationen Mitarbeitergenehmigungen benötigen

Administratoren können mitarbeiter in ihrer Organisation die Anmeldung verlangen, bevor ihre Verfügbarkeitsinformationen über Bookings freigegeben werden und bevor sie über eine Buchungsseite gebucht werden können. Diese Einstellung ist im Microsoft 365 Admin Center unter **Einstellungen** \> **Einstellungen** \> **Bookings verfügbar.**

Wenn diese Einstellung aktiviert ist, finden Mitarbeiter, die als Mitarbeiter in Buchungskalendern hinzugefügt werden, einen Link genehmigen/ablehnen in der E-Mail-Benachrichtigung, die sie erhalten.

Dieses Feature wird schrittweise weltweit für Microsoft 365-Kunden eingeführt. Wenn diese Option im Microsoft 365 Admin Center nicht angezeigt wird, schauen Sie bald zurück.

## <a name="block-social-sharing-options"></a>Blockieren von Optionen für die freigabe für soziale Netzwerke

Administratoren können steuern, wie Buchungsseiten in sozialen Netzwerken freigegeben werden. Diese Einstellung ist im Microsoft 365 Admin Center unter **Einstellungen** \> **Einstellungen** \> **Bookings verfügbar.**

Dieses Feature wird schrittweise weltweit für Microsoft 365-Kunden eingeführt. Wenn diese Option im Microsoft 365 Admin Center nicht angezeigt wird, schauen Sie bald zurück.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Nur ausgewählte Benutzer zum Erstellen von Bookings-Kalendern zulassen

Mithilfe von Richtlinieneinschränkungen können Sie verhindern, dass lizenzierte Benutzer Bookings-Kalender erstellen können. Sie müssen zuerst Bookings für Ihre gesamte Organisation aktivieren. Alle Benutzer in Ihrer Organisation verfügen über Bookings-Lizenzen, aber nur diejenigen, die in der Richtlinie enthalten sind, können Bookings-Kalender erstellen und voll darauf zugreifen, wer auf die von ihnen erstellten Kalender zugreifen kann.

Benutzer, die in dieser Richtlinie enthalten sind, können neue Bookings-Kalender erstellen und als Mitarbeiter in beliebiger Kapazität (einschließlich der Administratorrolle) vorhandenen Bookings-Kalendern hinzugefügt werden. Benutzer, die nicht in dieser Richtlinie enthalten sind, können keine neuen Bookings-Kalender erstellen und erhalten eine Fehlermeldung, wenn sie dies versuchen.

Sie müssen die folgenden Befehle mit Exchange Online PowerShell ausführen. Weitere Informationen zum Ausführen von Exchange Online-Cmdlets finden Sie unter [Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).

> [!IMPORTANT]
> In den folgenden Schritten wird davon ausgegangen, dass keine anderen Outlook Web App (OWA)-Postfachrichtlinien in Ihrer Organisation erstellt wurden.

1. Erstellen Sie eine neue Postfachrichtlinie für Benutzer, die Bookings-Kalender erstellen dürfen sollten. (Die Erstellung von Bookings-Kalendern ist standardmäßig durch neue Postfachrichtlinien zulässig.)

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Weitere Informationen finden Sie unter [New-OwaMailboxPolicy](/powershell/module/exchange/new-owamailboxpolicy).

2. Weisen Sie diese Richtlinie den relevanten Benutzern zu, indem Sie diesen Befehl für jeden Benutzer ausführen, den Sie zum Erstellen von Bookings-Kalendern berechtigt sein möchten.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Weitere Informationen finden Sie unter [Set-CASMailbox](/powershell/module/exchange/set-casmailbox).

3. Optional: Führen Sie diesen Befehl aus, wenn Sie Bookings für alle anderen Benutzer in Ihrer Organisation deaktivieren möchten.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Weitere Informationen finden Sie unter [Set-OwaMailboxPolicy](/powershell/module/exchange/set-owamailboxpolicy).

Weitere Informationen zu OWA-Postfachrichtlinien finden Sie in den folgenden Themen:

- [Erstellen einer Outlook im Webpostfachrichtlinie in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Anwenden oder Entfernen einer Outlook im Webpostfachrichtlinie für ein Postfach in Exchange Online](/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)