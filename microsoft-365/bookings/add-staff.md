---
title: Mitarbeiter zu Bookings hinzufügen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
description: Verwenden Sie diese Seite, um Ihre Mitarbeiterliste zu erstellen und Mitarbeiterdetails wie Name, Telefonnummer und E-Mail-Adresse zu verwalten.
ms.openlocfilehash: 23757c492986936125eff1203e6a99231164da22
ms.sourcegitcommit: 5d8de3e9ee5f52a3eb4206f690365bb108a3247b
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/04/2021
ms.locfileid: "52768945"
---
# <a name="add-staff-to-bookings"></a>Mitarbeiter zu Bookings hinzufügen

Auf der Seite "Mitarbeiter" in Bookings erstellen Sie Ihre Personalliste und verwalten Mitarbeiterdetails wie Name, Telefonnummer und E-Mail-Adresse. Von hier aus können Sie auch die Arbeitszeiten für jeden Mitarbeiter festlegen.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Obwohl Bookings ein Feature von Microsoft 365 ist, müssen nicht alle Mitarbeiter über ein Microsoft 365 Konto verfügen. Alle Mitarbeiter müssen über eine gültige E-Mail-Adresse verfügen, damit sie Buchungen erhalten und Änderungen planen können.

## <a name="watch-add-your-staff-to-bookings"></a>Watch: Add your staff to Bookings

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

## <a name="steps"></a>Schritte

1. Wechseln Sie zur [Seite "Mitarbeiter verwalten",](https://outlook.office.com/bookings/staff) und wählen Sie **"Mitarbeiter hinzufügen"** aus.

2. Wählen Sie die Schaltfläche **"Mitarbeiter hinzufügen"** aus.

3. Wenn Sie Mitarbeiter aus Ihrer Organisation hinzufügen, geben Sie ihren Namen in das Feld **"Personen hinzufügen"** ein, und wählen Sie sie aus, wenn sie im Dropdownmenü angezeigt werden. Die anderen Felder werden automatisch ausgefüllt.

    Nachdem ein Mitarbeiter hinzugefügt wurde, können Sie den Namen bearbeiten, der in allen Bookings-Kommunikationen angezeigt wird, indem Sie das **x** neben ihrem Namen auswählen und das Feld **"Personen hinzufügen"** bearbeiten. Dies kann hilfreich sein, wenn Mitarbeitern ein bestimmter Titel oder Name für Kunden angezeigt werden soll, z. B. adele Vance als "Dr. Vance, MD".

4. Um Mitarbeiter von außerhalb Ihrer Organisation hinzuzufügen, geben Sie ihre E-Mails und andere Informationen manuell ein.

    > [!NOTE]
    > Mitarbeiter von außerhalb Ihres Mandanten können keine Frei/Gebucht-Informationen mit Bookings teilen.

5. Wählen Sie für jeden Mitarbeiter eine Rolle aus: Administrator, Viewer oder Gast.
    - **Administratoren** können alle Einstellungen bearbeiten, Mitarbeiter hinzufügen und entfernen sowie Buchungen erstellen, bearbeiten oder löschen.
    - **Benutzer** können alle Buchungen im Kalender sehen, aber sie können sie nicht ändern oder löschen. Sie haben schreibgeschützten Zugriff auf Einstellungen.
    - **Gäste** können Buchungen zugewiesen werden, aber sie können das Buchungspostfach nicht öffnen.

6. Wählen Sie **"Alle Mitarbeiter per E-Mail benachrichtigen" aus, wenn eine ihnen zugewiesene Buchung erstellt oder geändert wird,** um Mitarbeiter-E-Mails zu aktivieren. Es folgt eine Beispiel-E-Mail:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Eine Benachrichtigungs-E-Mail von Bookings":::

7. Wählen Sie **Ereignisse in Office 365 Kalender aus, die sich auf** die Verfügbarkeit auswirken, wenn Sie möchten, dass sich die Frei/Gebucht-Informationen aus den Kalendern der Mitarbeiter auf die Verfügbarkeit für Bookings-Dienste über Bookings auswirken.

    Wenn ein Mitarbeiter beispielsweise eine Teambesprechung oder einen persönlichen Termin für einen Mittwoch um 15:00 Uhr geplant hat, zeigt Bookings an, dass der Mitarbeiter in diesem Zeitraum nicht gebucht werden kann. Diese Zeit wird in der Bookings-Kalenderansicht als beschäftigt oder mit Vorbehalt angezeigt, wie im folgenden Beispiel gezeigt.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Eine Ansicht eines Bookings-Kalenders":::

> [!IMPORTANT]
> Es wird dringend empfohlen, diese Einstellung zu aktivieren (sie ist standardmäßig aktiviert), um Doppelbuchungen zu vermeiden und die Verfügbarkeit Ihrer Mitarbeiter zu optimieren.

8. Wählen Sie **"Geschäftszeiten verwenden"** aus, um alle buchbaren Zeiten für Ihre Mitarbeiter so festzulegen, dass sie sich nur innerhalb der Geschäftszeiten befinden, die Sie im Abschnitt **"Geschäftszeiten"** auf der Seite "Geschäftsinformationen" festgelegt haben.

    Durch Deaktivieren dieses Kontrollkästchens können Mitarbeiter benutzerdefinierte Stunden erhalten, die die Anzahl der gebuchten Mitarbeiter weiter einschränken. Dies ist hilfreich für Szenarien, in denen ein Mitarbeiter möglicherweise nur dienstags und mittwochs vor Ort ist oder seine Morgenstunden für eine Art von Terminen und die Morgenstunden für andere Typen widmen.

    > [!NOTE]
    > Nur die ersten 31 Mitarbeiter, die Sie zu Ihrer Mitarbeiterseite hinzufügen, werden angezeigt, wenn Sie Mitarbeiter zu einem Dienst zuweisen.

## <a name="make-a-bookings-user-a-super-user-without-adding-them-as-staff-in-bookings"></a>Machen Sie einen Bookings-Benutzer zu einem Superbenutzer, ohne sie als Mitarbeiter in Bookings hinzuzufügen

Möglicherweise möchten Sie Ihrer Mitarbeiterliste in Bookings eine Person hinzufügen, ohne sie für Kunden oder Kunden verfügbar zu machen. Sobald Sie sie zu einem Superbenutzer machen, wird er Administrator des Buchungspostfachs. Als Administrator eines Buchungspostfachs ist definiert, dass sie Vollzugriff und Send-as-Berechtigungen für das Buchungspostfach haben.

> [!NOTE]
> Diese Schritte funktionieren nur, wenn dem hinzugefügten Benutzer in Bookings noch keine **Viewerrolle** zugewiesen wurde.

1. [Verbinden mit PowerShell Microsoft 365.](/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)

2. Weisen Sie mithilfe von PowerShell vollzugriff mit den folgenden Befehlen zu:

    ```powershell
    Add-MailboxPermission -Identity <bookingmailbox@emailaddress> -User <adminusers@emailaddress> -AccessRights FullAccess -Deny:$false
    ```

3. Führen Sie dann diesen Befehl aus, um "Senden als"-Berechtigungen zuzuweisen.

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

Hier ist ein Beispiel für einen PowerShell-Befehl zum Hinzufügen von Allie Bellew zum Postfach der Contoso-Kita-Buchung.

1. Führen Sie zuerst diesen Befehl aus:

    ```powershell
    Add-MailboxPermission -Identity "daycare@contoso.com" -User "Allie Bellew" -AccessRights FullAccess -InheritanceType All
    ```

2. Führen Sie dann den folgenden Befehl aus:

    ```powershell
    Add-RecipientPermission -Identity <bookingmailbox@emailaddress> -Trustee <adminusers@emailaddress> -AccessRights SendAs -Confirm:$false
    ```

**Allie Bellew** hat jetzt Administratorzugriff, wird aber nicht als buchbare Mitarbeiter in Bookings angezeigt.
