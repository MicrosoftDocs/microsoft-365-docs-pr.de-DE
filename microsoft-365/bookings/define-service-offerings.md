---
title: Definieren Ihrer Serviceangebote in Bookings
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Anweisungen zum Eingeben von Dienstangebotsinformationen, einschließlich Dienstname, Beschreibung, Ort, Dauer und Preise. Sie können auch die Mitarbeiter kategorisieren, die qualifiziert sind, den betreffenden Dienst zu leisten.
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962537"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definieren Ihrer Serviceangebote in Bookings

Wenn Sie Ihre Serviceangebote in Microsoft Bookings definieren, legen Sie einen Dienstnamen, eine Beschreibung, einen Standort fest (wählen Sie aus, ob Sie sich persönlich treffen oder eine Onlinebesprechung haben), Dauer, Standarderinnerungen für Kunden und Mitarbeiter, interne Hinweise zum Dienst und Preise. Sie können auch die Mitarbeiter kategorisieren, die qualifiziert sind, den betreffenden Dienst zu leisten. Wenn Kunden dann zu Ihrer Geschäftswebsite kommen, um einen Termin zu reservieren, können sie genau sehen, welche Arten von Terminen verfügbar sind, welche Person sie den Dienst bereitstellen möchten und wie viel ihr Dienst kosten wird.

Sie können auch angepasste Informationen und URLs zur E-Mail-Bestätigung und Erinnerungen hinzufügen, die Sie senden, wenn jemand einen Dienst über Ihre Buchungsseite gebucht hat.

## <a name="create-the-service-details"></a>Erstellen der Dienstdetails

1. Wechseln Sie zur [Seite Dienste verwalten,](https://outlook.office.com/bookings/services) und wählen **Sie Dienst hinzufügen aus.**

2. **Dienstname**: Geben Sie den Namen Ihres Diensts ein. Dies ist der Name, der im Dropdownmenü auf der Seite Kalender angezeigt wird. Dieser Name wird auch angezeigt, wenn jemand manuell einen Termin auf der Kalenderseite hinzufügt und als Kachel auf der Self-Service-Seite angezeigt wird.

3. **Beschreibung**: Die von Ihnen eingebene Beschreibung wird angezeigt, wenn ein Benutzer auf der Seite Self-Service auf das Informationssymbol klickt.

4. **Standardspeicherort:** Dieser Ort wird in Bestätigungs- und Erinnerungs-E-Mails für Mitarbeiter und Kunden angezeigt und im Kalenderereignis angezeigt, das für die Buchung erstellt wurde.

5. **Onlinebesprechung** hinzufügen: Diese Einstellung aktiviert oder deaktiviert Onlinebesprechungen für jeden Termin, entweder über Teams oder Skype, je nachdem, welches Sie als Standardclient für den Mitarbeiter konfigurieren.

    - Aktiviert:

        - Ein Link zu einer Teams- oder Skype-Besprechung, die für die Buchung eindeutig ist, wird dem Kalenderereignis sowohl in den Kalendern der Mitarbeiter als auch in den Kalendern der Kunden sowie mit Einwahlinformationen hinzugefügt.
        - Der Link zum Teilnehmen an der Besprechung wird allen Bestätigungs- und Erinnerungs-E-Mails hinzugefügt, wie im folgenden Beispiel gezeigt:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Beispiel für link to join Teams meeting in Bookings":::

        > [!NOTE]
        > Teams Besprechungen können über die Teams mobile App, die Teams-Desktop-App, in einem Webbrowser oder über die Telefonanwahl teilnehmen. Es wird dringend empfohlen, Teams als Standard-Onlinebesprechungsdienst für Ihren Mandanten zu aktivieren, um virtuelle Termine optimal zu buchen.

    - Deaktiviert:
        - Termine enthalten keine Besprechungsoption, und alle besprechungsbezogenen  Felder, die angezeigt werden, wenn Onlinebesprechung hinzufügen aktiviert ist, werden nicht angezeigt.

6. **Standarddauer:** So lange werden alle Besprechungen gebucht. Die Uhrzeit wird ab der Startzeit blockiert, die während der Buchung ausgewählt wird. Die vollständige Terminzeit wird in den Kalendern der Mitarbeiter blockiert.

7. **Pufferzeit, die** Ihr Kunde nicht buchen kann: Wenn Sie diese Einstellung aktivieren, können Sie dem Kalender der Mitarbeiter jedes Mal zusätzliche Zeit hinzufügen, wenn ein Termin gebucht wird.

    Die Uhrzeit wird im Kalender des Mitarbeiters blockiert und wirkt sich auf Frei/Gebucht-Informationen aus. Wenn ein Termin um 15:00 Uhr endet und dem Ende der Besprechung 10 Minuten Pufferzeit hinzugefügt wurden, wird der Kalender des Personals bis 15:10 Uhr als ausgelastet und nicht buchbar angezeigt. Dies kann nützlich sein, wenn Ihre Mitarbeiter zeit brauchen, bevor sie eine Besprechung vorbereiten, z. B. ein Arzt, der das Diagramm eines Patienten überprüft, oder ein Finanzberater, der relevante Kontoinformationen vorbereitet. Es kann auch nach einer Besprechung hilfreich sein, z. B. wenn jemand Zeit benötigt, um an einen anderen Ort zu reisen.

8. **Lassen Sie den** Kunden seine Buchung verwalten: Diese Einstellung bestimmt, ob der Kunde seine Buchung ändern oder stornieren kann, vorausgesetzt, er wurde über die Registerkarte Kalender in der Bookings Web App gebucht.

    - Aktiviert:

        Die **Schaltfläche Buchung verwalten** wird in der Kundenbestätigungs-E-Mail angezeigt. Wenn diese Schaltfläche vom Kunden ausgewählt wird, werden drei Optionen angezeigt:
        - **Reschedule** Wenn Sie diese Option auswählen, wird der Benutzer auf eine dienstspezifische Self-Service-Seite weitergeleitet, auf der er eine neue Uhrzeit und/oder ein neues Datum für denselben Dienst und denselben Mitarbeiter aus der ursprünglichen Buchung auswählen kann. Beachten Sie, dass der ursprüngliche Mitarbeiter zwar standardmäßig an die neu terminierte Buchung angefügt ist, der Benutzer jedoch auch die Möglichkeit hat, den Mitarbeiter zu ändern.
        - **Buchung stornieren** Dadurch wird die Buchung abgebrochen und aus dem Kalender der Mitarbeiter entfernt.
        - **Neue Buchung** Diese Option führt den Benutzer zur Self-Service, auf der alle Dienste und Mitarbeiter aufgeführt sind, um eine neue Buchung zu planen.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="Die Schaltfläche &quot;Bookings verwalten&quot; in Bookings":::

        Es wird nur empfohlen, diese Einstellung aktiviert zu lassen, wenn Sie mit Kunden, die auf die Seite zugreifen, Self-Service sind.

    - Deaktiviert:

        Der Benutzer kann seine Buchung nicht neu terminieren oder stornieren, wenn er über die Registerkarte Kalender in der Bookings-Web-App buchet. Bei der Buchung über Self-Service haben Kunden jedoch weiterhin  die Schaltfläche Buchung verwalten und alle Optionen, auch wenn diese Einstellung deaktiviert ist.

        Es wird empfohlen, diese Einstellung zu deaktivieren, wenn Sie den Zugriff auf die Self-Service beschränken möchten. Darüber hinaus empfehlen wir, Ihren Bestätigungs- und Erinnerungs-E-Mails Text zu hinzufügen, in dem Ihre Kunden darüber informiert werden, wie Sie Änderungen an ihrer Buchung auf andere Weise vornehmen können, z. B. indem Sie das Büro anrufen oder eine E-Mail an den Helpdesk senden.

9. **Maximale Teilnehmerzahl pro Ereignis** Mit dieser Einstellung können Sie Dienste erstellen, für die mehrere Personen dieselbe Terminzeit und dieselben Mitarbeiter (z. B. einen Fitnesskurs) reservieren können. Der Terminzeitplatz für den ausgewählten Dienst, die Mitarbeiter und die Uhrzeit stehen zur Verfügung, bis die von Ihnen angegebene maximale Anzahl von Teilnehmern erreicht ist. Aktuelle Terminkapazität und Teilnehmer können auf der Registerkarte Kalender in der Bookings Web App angezeigt werden.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Beispiel für das Festlegen der maximalen Teilnehmerzahl in Bookings":::

10. **Standardpreis**  Dies ist der Preis, der auf der Seite Self-Service wird. Wenn **"Preis nicht festgelegt"** ausgewählt ist, wird kein Preis oder Verweis auf Kosten oder Preise angezeigt.

11. **Hinweise** Dieses Feld wird im Buchungsereignis für gebuchte Mitarbeiter sowie im Ereignis angezeigt, das auf der Registerkarte Kalender in der Bookings-Web-App angezeigt wird.

12. **Benutzerdefinierte Felder** In diesem Abschnitt können Fragen hinzugefügt oder entfernt werden, wenn der Kunde Fragen beantworten muss, um die Buchung erfolgreich zu ermöglichen.

    - Kunden-E-Mails, Telefonnummern, Adressen und Notizen sind nicht austauschbare Felder, aber Sie können sie optional machen, indem Sie neben jedem Feld die Option **Erforderlich** deaktivieren.

    - Sie können eine Frage mit mehreren Auswahl- oder Textantworten hinzufügen, indem **Sie Eine Frage hinzufügen auswählen.**

        Benutzerdefinierte Felder können nützlich sein, wenn Sie Informationen sammeln, die bei jeder Buchung des bestimmten Termins benötigt werden. Beispiele sind Versicherungsanbieter vor einem Krankenhausbesuch, Kredittyp für Kreditberatungen, Hauptstudium für akademische Beratung oder Bewerber-ID für Kandidateninterviews.

13. **Erinnerungen und Bestätigungen** Beide Arten von E-Mails werden an Kunden, Mitarbeiter oder beide zu einem bestimmten Zeitraum vor dem Termin gesendet. Für jeden Termin können je nach Ihren Wünschen mehrere Nachrichten erstellt werden.

    - Die Standardbestätigungs- und Erinnerungs-E-Mails enthalten grundlegende Informationen zum Termin, z. B. den Kunden-/Clientnamen, den Namen des Mitarbeiters, den gebuchten Dienst oder Termin und den Zeitpunkt des Termins. Für Onlinebesprechungen wird auch ein Link zum Beitreten einbezogen. Die Möglichkeit, die Buchung zu verwalten, kann auch einbezogen werden, wenn diese Einstellung aktiviert ist (wie oben in Schritt 8 beschrieben).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Eine Bestätigungs-E-Mail von Bookings":::

    - Optional können Sie einen beliebigen zusätzlichen Text hier eingeben, z. B. Informationen zur Neuplanung oder informationen darüber, was Kunden für den Termin mitbringen sollten. Im Folgenden sehen Sie ein Beispiel für angepassten Text, der der ursprünglichen Bestätigungs-E-Mail hinzugefügt wurde, im Feld **Zusätzliche Informationen für E-Mail-Bestätigung:**

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Zusätzliche Informationen in einer Bookings-E-Mail":::

14. **Aktivieren von Textnachrichtenbenachrichtigungen für Ihren Kunden** Wenn diese Option SMS, werden nachrichten an den Kunden gesendet, jedoch nur, wenn sie sich dafür entscheiden.

    - Opt-In-Feld auf der manuellen Buchungs- und Self-Service Seite:

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Das Opt-In-Feld in Bookings":::

    - Textnachrichtenbenachrichtigungen sehen wie folgt aus (beachten Sie, dass SMS Benachrichtigungen derzeit nur in Nordamerika verfügbar sind):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Eine Textbenachrichtigung von Bookings":::

15. **Veröffentlichungsoptionen** Wählen Sie aus, ob dieser Dienst auf der Seite "Self-Service" als buchbar angezeigt werden soll oder ob der Dienst nur auf der Registerkarte Kalender in der Bookings Web App buchbar sein soll.

16. **Planungsrichtlinie** Diese Einstellung bestimmt, wie Terminzeiten angezeigt werden, und der Zeitraum, in dem Buchungen vorgenommen oder storniert werden können.

17. **E-Mail-Benachrichtigungen** Legt fest, wann E-Mails an Mitarbeiter der Organisation und an Kunden oder Kunden gesendet werden.

18. **Mitarbeiter** Durch Aktivieren dieses Kontrollkästchens können Kunden oder Kunden einen bestimmten Mitarbeiter für ihren Termin auswählen.

    - Aktiviert:

        Kunden können aus allen Mitarbeitern auswählen, die dem Termin bei der Buchung auf der Seite Self-Service werden. Wenn Sie die Option **Jeder auswählen,** wählt Bookings nach dem Zufallsprinzip einen verfügbaren Mitarbeiter aus, der dem Termin zugewiesen werden soll.

    - Deaktiviert:

        Kunden, die über die Self-Service buchen, können einen Dienst und eine Uhrzeit und ein Datum auswählen. Die verfügbaren Mitarbeiter werden nach dem Zufallsprinzip gebucht. Beachten Sie, dass bestimmte Mitarbeiter weiterhin ausgewählt werden können, wenn sie über die Registerkarte Kalender in der Bookings Web App gebucht werden.

19. **Verfügbarkeit** Die folgenden Optionen bestimmen, wann der Dienst gebucht werden kann:

    - **Buchbar, wenn Mitarbeiter kostenlos sind** Der Dienst behält die Verfügbarkeit basierend darauf bei, wann Mitarbeiter innerhalb der Geschäftszeiten kostenlos sind, ohne zusätzliche Zeitbeschränkungen.

    - **Benutzerdefinierte Stunden (wöchentlich wiederkehrende Zeiten)** Der Dienst verfügt über eine zusätzliche Verfügbarkeitsebene, die weiter eingeschränkt werden kann (zusätzlich zur Einschränkung durch Geschäftszeiten oder mit Mitarbeiterzeiten). Verwenden Sie diese Option, wenn Ihr Dienst nur zu einem bestimmten Zeitpunkt bereitgestellt oder ausgeführt werden kann.

    - **Festlegen einer anderen Verfügbarkeit für einen Datumsbereich** Diese Einstellung wirkt sich auf die Verfügbarkeit zu einem bestimmten Zeitpunkt und nicht auf eine wiederkehrende Basis aus. Dies kann z. B. verwendet werden, wenn ein computer, der für den Dienst benötigt wird, vorübergehend in Betrieb ist und nicht verfügbar ist oder wenn eine Organisation für einen Feiertag geschlossen wird.

20. **Zuweisen von Mitarbeitern** Wählen Sie die Mitarbeiter aus (vorausgesetzt, Sie haben mitarbeiter zur Registerkarte Mitarbeiter hinzugefügt), die für den jeweiligen Dienst buchbar sind. Wenn Sie keine einzelnen Mitarbeiter auswählen, werden alle Mitarbeiter dem Dienst zugewiesen.