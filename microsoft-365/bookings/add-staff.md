---
title: Hinzufügen von Mitarbeitern zu Buchungen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 298c529b-407b-4a2b-b2c5-6e77a9d1f07f
description: Auf dieser Seite können Sie Ihre Mitarbeiterliste erstellen und Mitarbeiterdetails wie Name, Telefonnummer und e-Mail-Adresse verwalten.
ms.openlocfilehash: cfd42eedb6e0bea08cdee1503fc373167996c75b
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419717"
---
# <a name="add-staff-to-bookings"></a>Hinzufügen von Mitarbeitern zu Buchungen

Auf der Seite "Mitarbeiter" in Buchungen können Sie Ihre Personalliste erstellen und Mitarbeiterdetails wie Name, Telefonnummer und e-Mail-Adresse verwalten. Sie können auch Arbeitsstunden für jeden Mitarbeiter von hier festlegen.

> [!NOTE]
> Reservierungen sind standardmäßig für Kunden mit den Abonnements Microsoft 365 Business Standard, Microsoft 365 a3 oder Microsoft 365 a5 aktiviert. Reservierungen stehen auch Kunden mit Office 365 Enterprise E3 und Office 365 Enterprise E5 zur Verfügung, Sie sind jedoch standardmäßig deaktiviert. Die ersten Schritte finden Sie unter [Get Access to Microsoft Booking](get-access.md). Informationen zum Aktivieren oder Deaktivieren von Buchungen finden Sie unter [Aktivieren oder Deaktivieren von Buchungen für Ihre Organisation](turn-bookings-on-or-off.md).

## <a name="add-staff"></a>Mitarbeiter hinzufügen

Obwohl Buchungen ein Feature von Microsoft 365 sind, müssen nicht alle Mitarbeiter ein Microsoft 365-Konto besitzen. Alle Mitarbeiter müssen über eine gültige e-Mail-Adresse verfügen, damit Sie Buchungen erhalten und Änderungen planen können.

Sehen Sie sich dieses Video an, oder führen Sie die folgenden Schritte aus, um Ihre Mitarbeiter hinzuzufügen.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWuVka]

1. Wechseln Sie zur [Seite Mitarbeiter verwalten](https://outlook.office.com/bookings/staff) , und wählen Sie **Mitarbeiter hinzufügen** aus.

2. Klicken Sie auf die Schaltfläche **Mitarbeiter hinzufügen** .

3. Wenn Sie Mitarbeiter aus Ihrem Mandanten hinzufügen möchten, geben Sie den Namen in das Feld **Personen hinzufügen** ein, und wählen Sie diese aus, wenn Sie im Dropdownmenü angezeigt werden. Die anderen Felder werden automatisch aufgefüllt.

    Nachdem ein Mitarbeiter hinzugefügt wurde, können Sie den Namen bearbeiten, der in allen Buchungen angezeigt wird, indem Sie das **x** neben dem Namen auswählen und das Feld **Personen hinzufügen** bearbeiten. Dies kann hilfreich sein, wenn Sie möchten, dass Mitarbeiter einen bestimmten Titel oder Namen für Kunden anzeigen können, beispielsweise das Listing von Adele Vance als "Dr. Vance, MD".

4. Um Mitarbeiter von außerhalb Ihres Mandanten hinzuzufügen, geben Sie Ihre e-Mails und andere Informationen manuell ein.

    > [!NOTE]
    > Mitarbeiter von außerhalb Ihres Mandanten können Frei/Gebucht-Informationen nicht mit Buchungen teilen.

5. Wählen Sie für jeden Mitarbeiter eine Rolle aus: Administrator, Viewer oder Gast.
    - **Administratoren** können alle Einstellungen bearbeiten, Mitarbeiter hinzufügen und entfernen sowie Buchungen erstellen, bearbeiten oder löschen.
    - **Betrachter** können alle Buchungen im Kalender anzeigen, aber nicht ändern oder löschen. Sie verfügen über Lesezugriff auf Einstellungen.
    - **Gäste** können Buchungen zugeordnet werden, aber Sie können das Buchungs Postfach nicht öffnen.

6. Wählen Sie **alle Mitarbeiter per e-Mail benachrichtigen, wenn eine Ihnen zugewiesene Buchung erstellt oder geändert wird** , um Mitarbeiter-e-Mails zu aktivieren. Es folgt eine Beispiel-e-Mail:

    :::image type="content" source="media/bookings-notify-all-email.jpg" alt-text="Eine Benachrichtigungs-e-Mail von Buchungen":::

7. Auswählen von **Ereignissen in Office 365 Kalender beeinflussen die Verfügbarkeit** , wenn Sie möchten, dass die Frei/Gebucht-Informationen aus den Kalendern von Mitarbeitern die Verfügbarkeit von Buchungsdiensten durch Buchungen beeinflussen.

    Wenn beispielsweise ein Mitarbeiter eine Teambesprechung oder einen persönlichen Termin für 15 Uhr an einem Mittwoch geplant hat, wird dieser Mitarbeiter in den Buchungen als nicht verfügbar in diesem Zeitschlitz angezeigt. Diese Zeit wird in der Kalenderansicht "Buchungen" als "gebucht" oder "vorläufig" angezeigt, wie im folgenden Beispiel dargestellt.

    :::image type="content" source="media/bookings-busy-tentative-view.jpg" alt-text="Ansicht eines Buchungs Kalenders":::

> [!IMPORTANT]
> Wir empfehlen dringend, diese Einstellung zu verlassen (Sie ist standardmäßig aktiviert), um Doppelbuchungen zu vermeiden und die Verfügbarkeit Ihrer Mitarbeiter zu optimieren.

8. Wählen Sie **Geschäftszeiten verwenden** aus, um alle Buchhaltungs Zeiten für Ihre Mitarbeiter nur innerhalb der Geschäftszeiten festzulegen, die Sie im Abschnitt Geschäfts **Zeiten** auf der Seite Unternehmensinformationen festgelegt haben.

    Wenn Sie dieses Kontrollkästchen deaktivieren, können Mitarbeiter benutzerdefinierte Stunden angegeben werden, die bei der Reservierung weiter eingeschränkt werden können. Dies ist hilfreich für Szenarien, in denen ein Mitarbeiter nur dienstags und mittwochs vor Ort sein kann, oder er widmet seine Vormittage für eine Art von Terminen und nachmittags für andere Typen.
