---
title: Löschen eines Buchungskalenders
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 8c3a913c-2247-4519-894d-b6263eeb9920
description: Verwenden Sie die Microsoft 365 Admin Center oder Windows PowerShell, um Bookings-Kalender zu löschen.
ms.openlocfilehash: 1ef67ce4dbf67da6f081106815f76ff85f11ef92
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288443"
---
# <a name="delete-a-booking-calendar-in-bookings"></a>Löschen eines Buchungskalenders in Bookings

In diesem Artikel wird erläutert, wie Sie einen kalender für unerwünschte Buchungen löschen können. Sie können den Buchungskalender im Microsoft 365 Admin Center löschen oder PowerShell verwenden. Der Bookings-Kalender ist ein Postfach in Exchange Online sodass Sie das entsprechende Benutzerkonto löschen, um den Buchungskalender zu löschen.

> [!IMPORTANT]
> Alle Buchungskalender, die Sie 2017 oder zuvor erstellt haben, müssen mithilfe der PowerShell-Anweisungen zu diesem Thema gelöscht werden. Alle Buchungskalender, die 2018 oder danach erstellt wurden, können im Microsoft 365 Admin Center gelöscht werden.

Im Buchungskalender werden alle relevanten Informationen zu diesem Buchungskalender und die daten gespeichert, einschließlich:

- Geschäftsinformationen, Logo und Arbeitszeiten, die hinzugefügt wurden, als der Buchungskalender erstellt wurde
- Relevante Mitarbeiter und Dienste, die hinzugefügt wurden, als der Buchungskalender erstellt wurde
- Alle Buchungen und Abwesenheitstermine, die dem Buchungskalender hinzugefügt wurden, nachdem er erstellt wurde.

> [!WARNING]
> Nachdem ein Buchungskalender gelöscht wurde, werden diese zusätzlichen Informationen auch dauerhaft gelöscht und können nicht wiederhergestellt werden.

## <a name="delete-a-booking-calendar-in-the-microsoft-365-admin-center"></a>Löschen eines Buchungskalenders im Microsoft 365 Admin Center

1. Gehen Sie zum Microsoft 365 Admin Center.

1. Wählen Sie im Admin Center **Benutzer** aus.

   ![Abbildung der Benutzeroberfläche von Benutzern in Microsoft 365 Admin Center](../media/bookings-admin-center-users.png)

1. Wählen Sie auf der Seite **Aktive Benutzer** die Namen der Benutzer aus, die Sie löschen möchten, und wählen Sie dann **Benutzer löschen** aus.

   ![Abbildung der Benutzeroberfläche zum Löschen von Benutzern in Microsoft 365 Admin Center](../media/bookings-delete-user.png)

## <a name="delete-a-booking-calendar-using-exchange-online-powershell"></a>Löschen eines Buchungskalenders mit Exchange Online PowerShell

Unter [Verbinden Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell-v2) finden Sie Voraussetzungen und Anleitungen zum Herstellen einer Verbindung mit Exchange Online PowerShell.

Zum Ausführen dieser Schritte müssen Sie ein aktives Microsoft PowerShell-Befehlsfenster verwenden, das Sie ausgeführt haben, indem Sie die Option "Als Administrator ausführen" auswählen.

1. Laden Sie in einem PowerShell-Fenster das EXO V2-Modul, indem Sie den folgenden Befehl ausführen:

   ```powershell
   Import-Module ExchangeOnlineManagement
   ```

   > [!NOTE]
   > Wenn Sie [das EXO V2-Modul bereits installiert](/powershell/exchange/exchange-online-powershell-v2#install-and-maintain-the-exo-v2-module) haben, funktioniert der vorherige Befehl wie beschrieben.
   
2. Die Syntax des Befehls, den Sie ausführen müssen, sieht so aus:

   ```powershell
   Connect-ExchangeOnline -UserPrincipalName <UPN> 
   ```

   - _\<UPN\>_ ist Ihr Konto im Benutzerprinzipalnamen-Format (z. B. `john@contoso.com`).

3. Wenn Sie dazu aufgefordert werden, melden Sie sich mit Mandantenadministratoranmeldeinformationen beim Microsoft 365 Mandanten an, der den Buchungskalender hostet, den Sie dauerhaft löschen möchten.

4. Sobald dieser Befehl verarbeitet wurde, geben Sie den folgenden Befehl ein, um eine Liste der Buchungspostfächer in Ihrem Mandanten abzurufen:

   ```powershell
   Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

5. Geben Sie den folgenden Befehl ein:

   ```powershell
   remove-mailbox [BookingCalendarToDelete]
   ```

   > [!IMPORTANT]
   > Achten Sie darauf, den genauen Namen des Buchungspostfachalias einzugeben, den Sie dauerhaft löschen möchten.

6. Um zu überprüfen, ob der Kalender gelöscht wurde, geben Sie den folgenden Befehl ein:

   ```powershell
    Get-EXOMailbox -RecipientTypeDetails SchedulingMailbox
   ```

   Der gelöschte Kalender wird nicht in der Ausgabe angezeigt.
