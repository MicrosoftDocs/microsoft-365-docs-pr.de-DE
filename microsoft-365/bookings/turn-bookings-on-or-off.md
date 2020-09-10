---
title: Aktivieren oder Deaktivieren von Microsoft-Buchungen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 5382dc07-aaa5-45c9-8767-502333b214ce
description: Erfahren Sie, wie Sie Zugriff auf Microsoft-Buchungen in Microsoft 365 erhalten.
ms.openlocfilehash: 815aa3a859db15364aa18d3550001a28d085b711
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419640"
---
# <a name="turn-microsoft-bookings-on-or-off"></a>Aktivieren oder Deaktivieren von Microsoft-Buchungen

Buchungen können für die gesamte Organisation oder für bestimmte Benutzer aktiviert oder deaktiviert werden. Wenn Sie Buchungen für Benutzer aktivieren, können Sie eine Buchungsseite erstellen, einen Kalender erstellen und anderen Personen die Möglichkeit geben, Zeit mit Ihnen zu buchen.

> [!NOTE]
> Die in diesen Abschnitten beschriebenen Administrator Steuerelemente sind für Office 365, die von 21Vianet-Kunden (China) betrieben werden, nicht verfügbar.

## <a name="turn-bookings-on-or-off-for-your-organization-using-the-microsoft-365-admin-center"></a>Aktivieren oder Deaktivieren von Buchungen für Ihre Organisation mithilfe des Microsoft 365 Admin Center

1. Melden Sie sich beim Microsoft 365 Admin Center als globaler Administrator an.

2. Wechseln Sie im Admin Center zu **Einstellungen** ,   \> **Settings** und wählen Sie **Buchungen**aus.

3. Aktivieren oder deaktivieren Sie das Kontrollkästchen **Ihre Organisation kann Buchungen verwenden** , um Buchungen für Ihre Organisation zu aktivieren oder zu deaktivieren.

   > [!NOTE]
   > Durch das Deaktivieren von Buchungen wird der gesamte Zugriff auf den Dienst deaktiviert, einschließlich der Erstellung und Verwaltung von Buchungsseiten.

4. Wählen Sie **Save Changes**aus.

## <a name="turn-bookings-on-or-off-for-your-organization-using-powershell"></a>Aktivieren oder Deaktivieren von Reservierungen für Ihre Organisation mithilfe von PowerShell

Zum Aktivieren oder Deaktivieren von Buchungen für Ihre Organisation mit dem PowerShell-Cmdlet " [OrganizationConfig" stellen](https://docs.microsoft.com/powershell/module/exchange/set-organizationconfig)Sie [eine Verbindung mit Exchange Online PowerShell her]() , und führen Sie den folgenden Befehl aus:

```PowerShell
   Set-OrganizationConfig -BookingsEnabled $false
```

### <a name="turn-bookings-on-or-off-for-individual-users"></a>Aktivieren oder Deaktivieren von Buchungen für einzelne Benutzer

Sie können Buchungen für einzelne Benutzer deaktivieren.

1. Wechseln Sie zum Microsoft 365 Admin Center, und wählen Sie dann **Benutzer** \> **aktive Benutzer**aus.

1. Wählen Sie den gewünschten Benutzer aus, und wählen Sie dann **Lizenzen und apps**aus.

1. Erweitern Sie **apps** , und deaktivieren Sie das Kontrollkästchen für Microsoft-Buchungen.

## <a name="require-staff-approvals-before-sharing-freebusy-information"></a>Personal Genehmigungen erfordern, bevor Sie Frei/Gebucht-Informationen freigeben

Administratoren können von Mitarbeitern in Ihrer Organisation verlangen, dass Sie sich anmelden, bevor Ihre Verfügbarkeitsinformationen Überbuchungen freigegeben werden und bevor Sie über eine Buchungsseite gebucht werden können. Diese Einstellung steht im Microsoft 365 Admin Center unter Einstellungen für **Settings** \> **Settings** \> **Reservierungen**zur Verfügung.

Wenn diese Einstellung aktiviert ist, werden Mitarbeiter, die in Buchungs Kalendern als Mitarbeiter hinzugefügt wurden, in der von Ihnen empfangenen e-Mail-Benachrichtigung einen Link genehmigen/ablehnen finden.

Dieses Feature wird schrittweise weltweit auf Microsoft 365-Kunden verteilt. Wenn diese Option im Microsoft 365 Admin Center nicht angezeigt wird, schauen Sie bald zurück.

## <a name="block-social-sharing-options"></a>Blockieren von Optionen für die soziale Freigabe

Administratoren können steuern, wie Buchungsseiten in sozialen Netzwerken freigegeben werden. Diese Einstellung steht im Microsoft 365 Admin Center unter Einstellungen für **Settings** \> **Settings** \> **Reservierungen**zur Verfügung.

Dieses Feature wird schrittweise weltweit auf Microsoft 365-Kunden verteilt. Wenn diese Option im Microsoft 365 Admin Center nicht angezeigt wird, schauen Sie bald zurück.

## <a name="allow-only-selected-users-to-create-bookings-calendars"></a>Nur ausgewählten Benutzern das Erstellen von Buchungs Kalendern erlauben

Durch die Verwendung von Richtlinieneinschränkungen können Sie die Lizenzierung von lizenzierten Benutzern daran hindern, Buchungen von Kalendern erstellen zu können. Sie müssen zunächst Buchungen für Ihre gesamte Organisation aktivieren. Alle Benutzer in Ihrer Organisation verfügen über Buchungs Lizenzen, aber nur die in der Richtlinie enthaltenen Buchungen können Buchungskalender erstellen und Vollzugriff auf die von Ihnen erstellten Kalender erhalten.

Benutzer, die in dieser Richtlinie enthalten sind, können neue Buchungskalender erstellen und können als Mitarbeiter in beliebiger Kapazität (einschließlich der Administratorrolle) vorhandenen Buchungs Kalendern hinzugefügt werden. Benutzer, die nicht in dieser Richtlinie enthalten sind, können keine neuen Buchungen Kalender erstellen und erhalten eine Fehlermeldung, wenn Sie versuchen, dies zu tun.

Sie müssen die folgenden Befehle mit Exchange Online PowerShell ausführen. Weitere Informationen zum Ausführen von Exchange Online-Cmdlets finden Sie unter [Connect to Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell).

> [!IMPORTANT]
> In den folgenden Schritten wird davon ausgegangen, dass in Ihrer Organisation keine anderen Outlook Web App (OWA)-Postfachrichtlinien erstellt wurden.

1. Erstellen Sie eine neue Postfachrichtlinie für Benutzer, die Kalender mit Buchungen erstellen dürfen. (Buchungen Kalendererstellung ist standardmäßig durch neue Postfachrichtlinien zulässig.)

   ```PowerShell
   New-OwaMailboxPolicy -Name "BookingsCreators"
   ```

   Weitere Informationen finden Sie unter [New-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/new-owamailboxpolicy).

2. Weisen Sie diese Richtlinie den relevanten Benutzern zu, indem Sie diesen Befehl für jeden Benutzer ausführen, dem Sie die Berechtigung zum Erstellen von Buchungs Kalendern erteilen möchten.

   ```PowerShell
   Set-CASMailbox -Identity <someCreator@emailaddress> -OwaMailboxPolicy "BookingsCreators"
   ```

   Weitere Informationen finden Sie unter [Set-CASMailbox](https://docs.microsoft.com/powershell/module/exchange/set-casmailbox).

3. Optional: führen Sie diesen Befehl aus, wenn Sie Buchungen für alle anderen Benutzer in Ihrer Organisation deaktivieren möchten.

   ```PowerShell
   Set-OwaMailboxPolicy "OwaMailboxPolicy-Default" -BookingsMailboxCreationEnabled:$false
   ```

   Weitere Informationen finden Sie unter [Set-OwaMailboxPolicy](https://docs.microsoft.com/powershell/module/exchange/set-owamailboxpolicy).

Weitere Informationen zu OWA-Postfachrichtlinien finden Sie in den folgenden Themen:

- [Erstellen einer Outlook im Internet-Postfachrichtlinie in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)

- [Anwenden oder Entfernen einer Outlook im webpostfach-Richtlinie für ein Postfach in Exchange Online](https://docs.microsoft.com/exchange/clients-and-mobile-in-exchange-online/outlook-on-the-web/create-outlook-web-app-mailbox-policy)