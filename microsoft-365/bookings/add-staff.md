---
title: Mitarbeiter zu Bookings hinzufügen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 298c529b-407b-4a2b-b2c5-6e77a9d1f07f
description: Verwenden Sie diese Seite, um Ihre Mitarbeiterliste zu erstellen und Mitarbeiterdetails wie Name, Telefonnummer und E-Mail-Adresse zu verwalten.
ms.openlocfilehash: 11d62cc34522de21e63b8bdf6e7e15729ac73dc1
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399193"
---
# <a name="add-staff-to-bookings"></a>Mitarbeiter zu Bookings hinzufügen

Auf der Seite Mitarbeiter in Bookings erstellen Sie Ihre Personalliste und verwalten Mitarbeiterdetails wie Name, Telefonnummer und E-Mail-Adresse. Sie können von hier aus auch die Arbeitszeiten für jeden Mitarbeiter festlegen.

## <a name="add-staff"></a>Hinzufügen von Mitarbeitern

Obwohl Bookings ein Feature der Microsoft 365 ist, müssen nicht alle Mitarbeiter über ein Microsoft 365 verfügen. Alle Mitarbeiter müssen über eine gültige E-Mail-Adresse verfügen, damit sie Buchungen empfangen und Änderungen planen können.

Sehen Sie sich dieses Video an, oder führen Sie die folgenden Schritte aus, um Ihre Mitarbeiter hinzuzufügen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

1. Wechseln Sie zur Seite [Mitarbeiter verwalten,](https://outlook.office.com/bookings/staff) und wählen Sie **Mitarbeiter hinzufügen aus.**

2. Wählen Sie die **Schaltfläche Mitarbeiter hinzufügen** aus.

3. Geben Sie beim Hinzufügen von Mitarbeitern innerhalb  Ihrer Organisation ihren Namen in das Feld Personen hinzufügen ein, und wählen Sie sie aus, wenn sie im Dropdownmenü angezeigt werden. Die anderen Felder werden automatisch auffüllt.

    Nachdem ein Mitarbeiter hinzugefügt wurde, können Sie den Namen bearbeiten, der in allen Bookings-Kommunikationen angezeigt wird, indem Sie das **x** neben ihrem Namen auswählen und das Feld Personen **hinzufügen** bearbeiten. Dies kann hilfreich sein, wenn Mitarbeiter einen bestimmten Titel oder Namen für Kunden anzeigen möchten, z. B. Adele Vance als "Dr. Vance, MD" auflisten.

4. Wenn Sie Mitarbeiter außerhalb Ihrer Organisation hinzufügen möchten, geben Sie ihre E-Mails und andere Informationen manuell ein.

    > [!NOTE]
    > Mitarbeiter von außerhalb Ihres Mandanten können Frei/Gebucht-Informationen nicht für Bookings freigeben.

5. Wählen Sie für jeden Mitarbeiter eine Rolle aus: Administrator, Viewer oder Gast.
    - **Administratoren** können alle Einstellungen bearbeiten, Mitarbeiter hinzufügen und entfernen sowie Buchungen erstellen, bearbeiten oder löschen.
    - **Die Betrachter** können alle Buchungen im Kalender anzeigen, aber sie können sie nicht ändern oder löschen. Sie haben schreibgeschützten Zugriff auf Einstellungen.
    - **Gästen** können Buchungen zugewiesen werden, aber sie können das Buchungspostfach nicht öffnen.

6. Wählen **Sie Alle Mitarbeiter per E-Mail benachrichtigen aus, wenn** eine ihnen zugewiesene Buchung erstellt oder geändert wird, um Mitarbeiter-E-Mails zu aktivieren. Nachfolgend finden Sie eine Beispiel-E-Mail:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Eine Benachrichtigungs-E-Mail von Bookings":::

7. Select **Events on Office 365 calendar affect availability** if you want the free/busy information from staff members' calendars to impact availability for bookings services through Bookings.

    Wenn ein Mitarbeiter beispielsweise über eine Teambetreffs oder einen persönlichen Termin verfügt, der für 15:00 Uhr an einem Mittwoch geplant ist, zeigt Bookings an, dass der Mitarbeiter nicht verfügbar ist, um in diesem Zeitfenster gebucht zu werden. Diese Zeit wird in der Bookings-Kalenderansicht als ausgelastet oder zagig angezeigt, wie im folgenden Beispiel gezeigt.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Ansicht eines Bookings-Kalenders":::

> [!IMPORTANT]
> Es wird dringend empfohlen, diese Einstellung aktiviert zu lassen (sie ist standardmäßig aktiviert), um Doppelbuchungen zu vermeiden und die Verfügbarkeit Ihrer Mitarbeiter zu optimieren.

8. Wählen **Sie Geschäftszeiten verwenden** aus, um alle buchbaren Zeiten für Ihre Mitarbeiter  auf die Geschäftszeiten zu legen, die Sie im Abschnitt Geschäftszeiten auf der Seite Geschäftsinformationen festgelegt haben.

    Durch Deaktivieren dieses Felds können Mitarbeiter benutzerdefinierte Stunden erhalten, die bei der Buchung weiter begrenzt werden. Dies ist hilfreich für Szenarien, in denen ein Mitarbeiter nur dienstags und mittwochs vor Ort ist oder seine Morgenstunden für eine Art von Terminen und deren Nachmittage für andere Typen verwendet.

    > [!NOTE]
    > Nur die ersten 31 Mitarbeiter, die Sie Ihrer Mitarbeiterseite hinzufügen, werden angezeigt, wenn Sie einem Dienst Mitarbeiter zuweisen.
