---
title: Hinzufügen von benutzerdefinierten und erforderlichen Fragen zur Buchungsseite
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: fd6b7587-5055-4bcd-83a4-13bd4929bfff
description: Wenn Sie Kunden Fragen stellen müssen, wenn Sie einen Termin bei Ihnen online buchen, können Sie der Buchungsseite benutzerdefinierte Fragen und erforderliche Fragen hinzufügen.
ms.openlocfilehash: ebbb07857fd8bb196f769dfb7e71ad25a85dfd54
ms.sourcegitcommit: 41fd71ec7175ea3b94f5d3ea1ae2c8fb8dc84227
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/09/2020
ms.locfileid: "47419714"
---
# <a name="add-custom-and-required-questions-to-the-booking-page"></a>Hinzufügen von benutzerdefinierten und erforderlichen Fragen zur Buchungsseite

Mit Buchungen können Sie Fragen erstellen, um Ihre Kunden bei der Buchung von Terminen zu Fragen. Außerdem können Sie auswählen, welche Fragen erforderlich sind.

Sie ordnen die Fragen einem Dienst zu, sodass jeder Dienst eine andere Gruppe von Fragen haben kann. Ein Friseur kann beispielsweise Kunden bitten, die einen haarfärbungs Termin buchen, wenn es sich um bekannte Allergien für Bleiche oder Farbtöne handelt. Auf diese Weise können Sie und ihre Kunden Zeit sparen, wenn Sie Ihren Termin erreichen.

Den Kunden werden die benutzerdefinierten Fragen angezeigt, wenn Sie Ihren Termin auf der Buchungsseite erstellen. Die Mitarbeiter sehen die benutzerdefinierten Fragen beim Erstellen einer neuen Buchung aus dem Buchungskalender oder beim Anzeigen eines vorhandenen Termins. Bei Buchungen werden alle Ihre Fragen in einer Masterliste gespeichert, sodass Sie nicht für jeden Dienst dieselben Fragen erneut erstellen müssen. Sie können auch auswählen, ob Fragen erforderlich oder optional sind.

> [!NOTE]
> Die Antworten des Kunden auf die Fragen können Sie sehen, wenn Sie sich Ihren Termin im Buchungskalender ansehen.

Weitere Informationen zum personalisieren und Anpassen Ihrer Buchungsseite finden Sie unter [Anpassen Ihrer Buchungsseite](customize-booking-page.md).

## <a name="add-custom-questions-to-your-services"></a>Hinzufügen von benutzerdefinierten Fragen zu Ihren Diensten

1. Melden Sie sich bei Microsoft 365 an, und wechseln Sie zu **Buchungen**.

1. Wechseln Sie zu **Dienste** , und bearbeiten Sie entweder einen vorhandenen Dienst, oder **fügen Sie einen Dienst hinzu**.

1. Scrollen Sie nach unten zum Abschnitt **benutzerdefinierte Felder** , und wählen Sie dann **ändern**aus.

   Wir haben bereits einige grundlegende Fragen zur Kundeninformation hinzugefügt: Kunden-e-Mail, Telefonnummer, Kundenadresse und Kunden Notizen. Wenn Sie dies zum ersten Mal durchführen, werden die Fragen zur Kundeninformation in grau markiert. Das bedeutet, dass dem Benutzer diese Frage angezeigt wird. Wenn Sie die Frage auswählen, wird das Hervorhebungsfeld um Sie herum ausgeblendet, und Ihr Kunde wird diese Frage nicht gestellt.

   In diesem Beispiel wurden die Telefonnummer und Kunden Notizen deaktiviert, und wir haben zwei neue benutzerdefinierte Fragen erstellt, die Sie stellen sollten.

   ![Bild des Bildschirms "benutzerdefinierte Fragen"](../media/bookings-questions-custom-fields.png)

1. Um die Frage erforderlich zu machen, aktivieren Sie das Kontrollkästchen **erforderlich** . Ihr Kunde kann die Buchung erst abschließen, nachdem er die erforderlichen Fragen beantwortet hat.

1. Um eine benutzerdefinierte Frage zu erstellen, wählen Sie am oberen Rand des Bereichs **eine Frage hinzufügen** aus. Schreiben Sie Ihre Frage, und wählen Sie dann **Speichern**aus.

1. Klicken Sie auf die Frage, um Sie zu aktivieren. Um ihn herum wird ein hervorgehobenes Feld angezeigt, und die Frage ist aktiviert.

1. Klicken Sie oben auf der Seite auf **OK** , und speichern Sie dann **den Dienst**.

Durch Buchungen werden alle Ihre benutzerdefinierten Fragen in einer Masterliste gespeichert, sodass Sie jedem Dienst problemlos Fragen hinzufügen können, ohne dieselben Fragen wiederholt eingeben zu müssen. Wenn Sie beispielsweise einen anderen Dienst öffnen, wird die Frage, die Sie für den ersten Dienst erstellt haben, im Abschnitt benutzerdefinierte Felder angezeigt, aber er wird deaktiviert. Klicken Sie auf die Frage, sodass ein hervorgehobenes Rechteck angezeigt wird und die Frage aktiviert ist.

In diesem Beispiel können Sie sehen, dass die Fragen, die für den ersten Dienst hinzugefügt wurden, für diesen Dienst zur Verfügung stehen. Alle Fragen, die Sie für diesen Dienst erstellen, stehen für alle Dienste zur Verfügung.

   ![Bild der Fragen, die für mehrere Dienste angezeigt werden](../media/bookings-questions-services.png)

Wenn Ihre Buchungsseite bereits veröffentlicht ist, müssen Sie nichts anderes tun. Kunden sehen die Fragen, wenn Sie das nächste Mal mit Ihnen buchen. Wenn Ihre Buchungsseite noch nicht veröffentlicht wurde, navigieren Sie in Outlook im Internet zur **Buchungsseite** , und wählen Sie dann **Speichern und veröffentlichen**aus.

> [!WARNING]
> Sie können auch Fragen aus der Masterliste löschen. Wenn Sie jedoch eine Frage löschen, wird Sie aus jedem Dienst gelöscht. Es wird empfohlen, dass Sie die Frage deaktivieren, indem Sie Sie auswählen, um sicherzustellen, dass Sie keine Auswirkungen auf andere Dienste haben. Sie können sehen, dass eine Frage deaktiviert ist, wenn Sie nicht von einem markierten Rechteck umgeben ist.

## <a name="customer-experience"></a>Kundenerfahrung

Wenn Ihre Kunden einen Termin mit Ihnen buchen, werden die grundlegenden Fragen zur Kundeninformation im Abschnitt **Ihre Details hinzufügen** angezeigt. Alle benutzerdefinierten Fragen, die Sie hinzufügen, finden Sie im Abschnitt **zusätzliche Informationen bereitstellen** .

![Abbildung dessen, was Kunden sehen, wenn Fragen aktiviert sind](../media/bookings-questions-customer.png)

## <a name="staff-experience"></a>Mitarbeiter Erfahrung

Wenn Ihre Kunden einen Termin bei Ihnen buchen, werden Ihre Mitarbeiter die Fragen und Antworten des Kunden auf dem Buchungskalender angezeigt. Um es anzuzeigen, gehen Sie zu **Buchungen** \> **Kalender** und öffnen Sie einen Termin.

![Abbildung dessen, was Mitarbeiter sehen, wenn Fragen aktiviert sind](../media/bookings-questions-staff.png)
