---
title: Festlegen von Pufferzeit in Microsoft Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 271f43e4-b8f7-4d63-8059-b5747679bb7e
description: Legen Sie die Pufferzeit vor oder nach einem Termin in Microsoft-Buchungen fest, um Zeit zum Bereinigen oder Zurücksetzen von Geräten zu gewähren.
ms.openlocfilehash: dceb777f9ddba9f1ddabfee00608813afae57a86
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419647"
---
# <a name="set-buffer-time-in-microsoft-bookings"></a>Festlegen von Pufferzeit in Microsoft Bookings

Für einige Ihrer Termine ist möglicherweise Zeit erforderlich, bevor oder nachdem Sie sich mit Ihrem Kunden getroffen haben, um Ihren Raum und Ihr Equipment einzurichten, zu bereinigen oder zurückzusetzen. Oder wenn Sie zwischen Kundenterminen unterwegs sind, benötigen Sie möglicherweise Zeit, um sicherzustellen, dass Sie und Ihr Team zwischen den Terminen Reisen können, ohne dass der Kunde gewartet wird.

Sie können die Pufferzeit vor dem Start von Terminen, nach dem Termin Ende oder beides festlegen, um den Mitarbeitern die zusätzliche Zeit zu geben, die Sie für die Vorbereitung Ihres nächsten Termins benötigen.

> [!NOTE]
> Reservierungen sind standardmäßig für Kunden mit den Abonnements Microsoft 365 Business Standard, Microsoft 365 a3 oder Microsoft 365 a5 aktiviert. Reservierungen stehen auch Kunden mit Office 365 Enterprise E3 und Office 365 Enterprise E5 zur Verfügung, Sie sind jedoch standardmäßig deaktiviert. Die ersten Schritte finden Sie unter [Get Access to Microsoft Booking](get-access.md). Informationen zum Aktivieren oder Deaktivieren von Buchungen finden Sie unter [Aktivieren oder Deaktivieren von Buchungen für Ihre Organisation](turn-bookings-on-or-off.md).

## <a name="set-buffer-time-defaults"></a>Festlegen von Standardeinstellungen für die Pufferzeit

Die Standardwerte für Pufferzeit werden auf der Seite **Dienstdetails** in Buchungen festgelegt. Wie alle auf dieser Seite festgelegten Dienst Standardwerte können diese Standardeinstellungen von Ihnen für eine bestimmte Buchung bearbeitet werden, um bestimmte Kundenanforderungen zu erfüllen.

Die Einstellung Pufferzeit befindet sich direkt unterhalb der **standardmäßigen Dauer** Auswahl auf der Seite **Dienstdetails** . Bevor Sie für einen bestimmten Dienst festgelegt werden kann, müssen Sie die Einstellung Pufferzeit aktivieren, indem Sie die Umschaltfläche Pufferzeit auswählen. Dadurch werden die Dropdown-Listen **before** und **after** angezeigt, die verwendet werden, um die standardmäßige Zeitspanne, die vor und nach jeder Buchung aufbewahrt werden soll, wie im folgenden dargestellt zu wählen:

   ![Bild der Buchungen mit aktivierter Pufferzeit](../media/bookings-buffertime.png)

## <a name="buffer-time-and-appointment-timing"></a>Zeitplanung für Pufferzeit und Termin

Um Verwirrung bei Kundenterminen zu vermeiden, werden in Bookings in Ihrem Kalender sowie in E-Mail-Bestätigungen und Erinnerungen an die entsprechenden Mitarbeiter die Pufferzeit und der tatsächliche Zeitpunkt für den Termin (an dem Ihr Kunde Sie erwartet) angezeigt. Unten sehen Sie beispielsweise, was Sie bei Buchungen für einen Termin mit einem Kunden sehen, der 15 Minuten vor der Wartezeit für den Termin vorliegt.

Beachten Sie, dass bei dem eigentlichen Ereignis (links im Bild) die Pufferzeit heller und der eigentliche Kundentermin dunkler schattiert ist. Der Termin Aufruf (der beim Auswählen des Ereignisses geöffnet wird) besagt ausdrücklich, dass der Termin von 9 Uhr bis 10 Uhr morgens mit Katie Jordan vorliegt und 15 Minuten Pufferzeit vor dem Termin und 0 Minuten nach dem Termin umfasst. Bestätigungen und Erinnerungen an das Personal beziehen sich ähnlich auf bestimmte Puffer-und Termin Zeiten, während der Kunde nur Bestätigungen und Erinnerungen erhält, die auf ein 9.00 Uhr bis 10:00 Uhr-Termin verweisen.

   ![Bild der Buchung Termin Aufruf mit Pufferzeit angezeigt](../media/bookings-buffertime-callout.png)

## <a name="buffer-time-and-availability"></a>Pufferzeit und Verfügbarkeit

Ihre Kunden sehen nicht direkt und können die von Ihnen festgelegten Pufferzeiten nicht ändern. Da jedoch Pufferzeit verwendet wird, um die Gesamtdauer des Diensts zu berechnen, sehen Kunden Sie und ihre relevanten Mitarbeiter sowohl während der Puffer-als auch der regulären Termin Zeiten als gebucht. Kunden sehen auch nur die Verfügbarkeit für Sie und Ihre Mitarbeiter, wenn genügend Zeit für den Termin und die zugehörige Pufferzeit vorhanden ist.

Beispielsweise erfordert ein einstündiger Termin mit einer Pufferzeit von 15 Minuten vor dem Termin einen verfügbaren Zeit Block von mindestens 1 Stunde und 15 Minuten. Ein Termin für diesen Dienst würde daher einen 75-minütigen Zeit Block in Ihrem Kalender ausfüllen und benötigt 75 Minuten Verfügbarkeit für die Buchung ohne Konflikt.
