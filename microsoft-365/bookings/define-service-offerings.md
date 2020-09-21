---
title: Definieren Ihrer Dienstangebote in Buchungen
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.topic: article
ms.service: bookings
localization_priority: Normal
ms.assetid: 4a1c391e-524f-48e0-bef8-185df3a9634b
description: Anweisungen zum Eingeben von Dienstangebots Informationen, einschließlich Dienstname, Beschreibung, Standort, Dauer und Preis. Sie können auch die Mitarbeiter kategorisieren, die qualifiziert sind, den betreffenden Dienst zu leisten.
ms.openlocfilehash: 095188546c01149a793a478a3cbd5ac9fbeb5524
ms.sourcegitcommit: 7c0873d2a804f17697844fb13f1a100fabce86c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/18/2020
ms.locfileid: "47962537"
---
# <a name="define-your-service-offerings-in-bookings"></a>Definieren Ihrer Dienstangebote in Buchungen

Wenn Sie Ihre Dienstangebote in Microsoft-Buchungen definieren, legen Sie einen Dienstnamen, eine Beschreibung, einen Standort fest (Wählen Sie aus, ob Sie persönlich zusammentreffen oder eine Onlinebesprechung haben möchten), die Dauer, die Standarderinnerungen an Kunden und Mitarbeiter, interne Hinweise zum Dienst und Preise. Sie können auch die Mitarbeiter kategorisieren, die qualifiziert sind, den betreffenden Dienst zu leisten. Wenn Kunden dann zu ihrer Geschäftswebsite kommen, um einen Termin zu buchen, können Sie genau sehen, welche Arten von Terminen zur Verfügung stehen, die Person auswählen, für die Sie den Dienst bereitstellen möchten, und wie viel Ihr Dienst Kosten wird.

Sie können auch benutzerdefinierte Informationen und URLs zur e-Mail-Bestätigung und Erinnerungen hinzufügen, die Sie senden, wenn jemand über Ihre Buchungsseite einen Dienst Bucht.

## <a name="create-the-service-details"></a>Erstellen der Dienstdetails

1. Wechseln Sie zur [Seite Dienste verwalten](https://outlook.office.com/bookings/services) , und wählen Sie **Dienst hinzufügen**aus.

2. **Dienstname**: Geben Sie den Namen Ihres Diensts ein. Dies ist der Name, der im Dropdownmenü auf der Kalender Seite angezeigt wird. Dieser Name wird auch angezeigt, wenn jeder Benutzer manuell einen Termin auf der Kalender Seite hinzufügt und auf der Self-Service-Seite als Kachel angezeigt wird.

3. **Beschreibung**: die eingegebene Beschreibung wird angezeigt, wenn ein Benutzer auf das Informationssymbol auf der Self-Service-Seite klickt.

4. **Standardspeicherort**: dieser Speicherort wird auf Bestätigungs-und Erinnerungs-e-Mails sowohl für Mitarbeiter als auch für Kunden angezeigt und wird im Kalenderereignis angezeigt, das für die Buchung erstellt wurde.

5. **Onlinebesprechung hinzufügen**: Diese Einstellung aktiviert oder deaktiviert Onlinebesprechungen für jeden Termin, entweder über Teams oder Skype, je nachdem, welche Person Sie als Standard Client für den Mitarbeiter konfiguriert haben.

    - Aktiviert

        - Ein Link zu einem Team oder einer Skype-Besprechung, der für die Buchung eindeutig ist, wird dem Kalenderereignis sowohl auf dem Kalender des Mitarbeiters als auch auf dem Kunden sowie auf Einwahlinformationen hinzugefügt.
        - Der Link zum teilnehmen an der Besprechung wird allen Bestätigungs-und Erinnerungs-e-Mails hinzugefügt, wie im folgenden Beispiel dargestellt:

        :::image type="content" source="media/bookings-teams-meeting-link.jpg" alt-text="Beispiel für einen Link zum beitreten in Microsoft Teams-Besprechungen in Buchungen":::

        > [!NOTE]
        > Microsoft Teams-Besprechungen können über die Teams-Mobile App, die Desktop-App für Teams, in einem Webbrowser oder über das Telefoneinwahl Mitglied hinzugefügt werden. Es wird dringend empfohlen, Microsoft Teams als standardmäßigen Online-Besprechungs Dienst für Ihren Mandanten zu aktivieren, um virtuelle Termine mit der besten Buchungs Erfahrung zu buchen.

    - Deaktiviert
        - Termine enthalten keine Besprechungsoption, und alle Besprechungs bezogenen Felder, die angezeigt werden, wenn " **Onlinebesprechung hinzufügen** " aktiviert ist, werden nicht angezeigt.

6. **Standarddauer**: Dies ist, wie lange alle Besprechungen für gebucht werden. Die Zeit wird ab der Startzeit blockiert, die während der Buchung ausgewählt wird. Die gesamte Termin Zeit wird in den Kalendern des Mitarbeiters blockiert.

7. **Pufferzeit, die Ihr Kunde nicht buchen kann**: Wenn Sie diese Einstellung aktivieren, können Sie den Kalender jedes Mal, wenn ein Termin gebucht wird, um zusätzliche Zeit ergänzen.

    Die Zeit wird im Kalender des Mitarbeiters blockiert und wirkt sich auf Frei/Gebucht-Informationen aus. Das heißt, wenn ein Termin um 3:00 Uhr endet und 10 Minuten Pufferzeit am Ende der Besprechung hinzugefügt wurde, wird der Kalender des Mitarbeiters bis 3:10PM als belegt und nicht buchbar angezeigt. Dies kann hilfreich sein, wenn Ihre Mitarbeiter Zeit vor der Vorbereitung einer Besprechung benötigen, beispielsweise einen Arzt, der das Diagramm eines Patienten überprüft, oder ein Finanzberater, der relevante Kontoinformationen vorbereitet. Es kann auch nach einer Besprechung hilfreich sein, beispielsweise wenn jemand Zeit braucht, um an einen anderen Ort zu reisen.

8. **Lassen Sie den Kunden Ihre Buchung verwalten**: Diese Einstellung legt fest, ob der Kunde seine Buchung ändern oder stornieren kann, vorausgesetzt, er wurde über die Registerkarte Kalender in der nichtdie-App gebucht.

    - Aktiviert

        Die Schaltfläche " **Buchung verwalten** " wird in der Kunden Bestätigungs-e-Mail angezeigt. Wenn diese Schaltfläche vom Kunden ausgewählt wird, werden drei Optionen angezeigt:
        - Erneutes **Planen** Wenn Sie diese Option auswählen, wird der Benutzer zu einer dienstspezifischen Self-Service-Seite, auf der Sie eine neue Uhrzeit und/oder ein Datum für denselben Dienst und denselben Mitarbeiter aus der ursprünglichen Buchung auswählen können. Beachten Sie, dass der Benutzer auch dann die Möglichkeit hat, den Mitarbeiter zu ändern, obwohl der ursprüngliche Mitarbeiter standardmäßig mit der neu geplanten Buchung verbunden ist.
        - **Buchung stornieren** Dadurch wird die Buchung storniert und aus dem Kalender des Mitarbeiters entfernt.
        - **Neue Buchung** Diese Option bringt den Benutzer zur Self-Service-Seite, wobei alle Dienste und Mitarbeiter aufgelistet sind, um eine neue Buchung zu planen.

        :::image type="content" source="media/bookings-manage-booking-button.jpg" alt-text="Die Schaltfläche "Buchungen verwalten" in Buchungen":::

        Es wird nur empfohlen, diese Einstellung aktiviert zu lassen, wenn Sie mit Kunden vertraut sind, die auf die Self-Service-Seite zugreifen.

    - Deaktiviert

        Der Benutzer kann seine Buchung nicht neu planen oder stornieren, wenn er über die Registerkarte Kalender der Buchungen-Webanwendung gebucht wird. Bei der Buchung über die Self-Service-Seite verfügen Kunden jedoch weiterhin über die Schaltfläche " **Buchung verwalten** " und alle Optionen, auch wenn diese Einstellung deaktiviert ist.

        Es wird empfohlen, diese Einstellung zu deaktivieren, wenn Sie den Zugriff auf die Self-Service-Seite einschränken möchten. Darüber hinaus empfehlen wir Hinzufügen von Text zu ihren Bestätigungs-und Erinnerungs-e-Mails, die ihren Kunden mitteilen, wie Sie Änderungen an Ihrer Buchung auf andere Weise vornehmen können, beispielsweisedurch den Anruf im Büro oder per e-Mail an das Helpdesk.

9. **Maximale Anzahl von Teilnehmern pro Ereignis** Mit dieser Einstellung können Sie Dienste erstellen, für die mehrere Personen denselben Termin und dieselben Mitarbeiter (beispielsweise eine Fitness Klasse) buchen müssen. Der Termin Zeitschlitz für den ausgewählten Dienst, das Personal und die Uhrzeit ist verfügbar, bis die von Ihnen angegebene maximale Anzahl von Teilnehmern erreicht wurde. Die aktuelle Kapazität des Termins und die Teilnehmer können auf der Registerkarte Kalender in der Buchungs-Webanwendung angezeigt werden.

    :::image type="content" source="media/bookings-maximum-attendees.jpg" alt-text="Beispiel für das Festlegen der maximalen Anzahl von Teilnehmern bei Buchungen":::

10. **Standardpreis**  Dies ist der Preis, der auf der Self-Service-Seite angezeigt wird. Wenn " **Preis nicht festgelegt** " ausgewählt ist, wird kein Preis oder Bezug auf Kosten oder Preise angezeigt.

11. **Anmerkungen** Dieses Feld wird im Buchungs Ereignis für gebuchte Mitarbeiter sowie auf dem Ereignis angezeigt, das auf der Registerkarte Kalender in der Buchungs-Webanwendung angezeigt wird.

12. **Benutzerdefinierte Felder** In diesem Abschnitt können Sie Fragen hinzufügen oder entfernen, wenn der Kunde eine Antwort erhalten muss, um eine erfolgreiche Buchung zu ermöglichen.

    - Kunden-e-Mail, Telefonnummer, Adresse und Notizen sind nicht abnehmbare Felder, können aber optional sein, indem Sie neben jedem Feld die Option **erforderlich** deaktivieren.

    - Sie können eine Multiple-Choice-oder Text-Antwort-Frage hinzufügen, indem Sie **eine Frage hinzufügen**auswählen.

        Benutzerdefinierte Felder können hilfreich sein, wenn Sie Informationen sammeln, die jedes Mal erforderlich sind, wenn der jeweilige Termin gebucht wird. Beispiele hierfür sind Versicherungsanbieter vor einem klinikbesuch, Darlehenstyp für Darlehens Beratungen, Major of Study für akademische Beratung oder Bewerber-ID für Kandidaten Interviews.

13. **Erinnerungen und Bestätigungen** Beide Arten von e-Mails werden an Kunden, Mitarbeiter oder beides an einem bestimmten Zeitraum vor dem Termin gesendet. Für jeden Termin können nach Wunsch mehrere Nachrichten erstellt werden.

    - Die standardmäßigen Bestätigungs-und Erinnerungs-e-Mails enthalten grundlegende Informationen zum Termin, beispielsweise den Namen des Kunden/Kunden, den Namen des Mitarbeiters, den gebuchten Dienst oder Termin sowie die Uhrzeit des Termins. Für Onlinebesprechungen wird auch ein Link zum beitreten hinzugefügt. Die Möglichkeit, die Buchung zu verwalten, kann auch einbezogen werden, wenn diese Einstellung aktiviert ist (wie oben in Schritt 8 beschrieben).

        :::image type="content" source="media/bookings-remind-confirm.jpg" alt-text="Bestätigungs-e-Mail von Buchungen":::

    - Optional können Sie zusätzlichen Text hinzufügen, den Sie hier möchten, beispielsweise Informationen zur Neuterminierung oder was Kunden für den Termin mitbringen sollen. Im folgenden sehen Sie ein Beispiel für benutzerdefinierten Text, der der ursprünglichen Bestätigungs-e-Mail hinzugefügt wurde, im Feld **zusätzliche Informationen für e-Mail-Bestätigung** :

        :::image type="content" source="media/bookings-additional-info.jpg" alt-text="Zusätzliche Informationen in einer Reservierungs-e-Mail":::

14. **Aktivieren von Textnachrichten Benachrichtigungen für Ihren Kunden** Wenn diese Option aktiviert ist, werden SMS-Nachrichten an den Kunden gesendet, jedoch nur, wenn Sie sich anmelden.

    - Opt-in-Feld auf der Seite "Manuelle Buchung" und "Self-Service":

        :::image type="content" source="media/bookings-opt-In-boc.jpg" alt-text="Das Opt-in-Feld bei Buchungen":::

    - Benachrichtigungen für Text Nachrichten werden wie folgt aussehen (Beachten Sie, dass SMS-Benachrichtigungen derzeit nur in Nordamerika verfügbar sind):

        :::image type="content" source="media/bookings-text-notifications.jpg" alt-text="Eine Textbenachrichtigung von Buchungen":::

15. **Veröffentlichungsoptionen** Wählen Sie aus, ob dieser Dienst auf der Self-Service-Seite als buchbar angezeigt werden soll, oder um den Dienst nur auf der Registerkarte Kalender in der Buchungs-Webanwendung zu buchen.

16. **Planungsrichtlinie** Mit dieser Einstellung wird festgelegt, wie Termin Zeiten angezeigt werden, sowie den Zeitraum, in dem Buchungen getätigt oder storniert werden können.

17. **E-Mail-Benachrichtigungen** Legt fest, wann e-Mails an die Mitarbeiter der Organisation und an Kunden oder Kunden gesendet werden.

18. **Mitarbeiter** Durch Aktivieren dieses Kontrollkästchens können Kunden oder Kunden einen bestimmten Mitarbeiter für Ihren Termin auswählen.

    - Aktiviert

        Kunden können aus allen Mitarbeitern auswählen, die dem Termin bei der Buchung auf der Self-Service-Seite zugeordnet sind. Wenn Sie die Option **jeder** auswählen, wählen Sie einen verfügbaren Mitarbeiter nach dem Zufallsprinzip aus, der dem Termin zugewiesen werden soll.

    - Deaktiviert

        Kunden, die über die Self-Service-Seite buchen, können einen Dienst und eine Uhrzeit und ein Datum auswählen. Die verfügbaren Mitarbeiter werden nach dem Zufallsprinzip gebucht. Beachten Sie, dass bestimmte Mitarbeiter weiterhin ausgewählt werden können, wenn Sie über die Registerkarte Kalender in der Buchungen-Webanwendung gebucht werden.

19. **Verfügbarkeit** Die folgenden Optionen bestimmen, wann der Dienst gebucht werden kann:

    - **Buchbar, wenn das Personal frei ist** Der Dienst behält die Verfügbarkeit basierend darauf, wann Mitarbeiter innerhalb der Geschäftszeiten kostenlos sind, ohne zusätzliche Zeitbeschränkungen.

    - **Benutzerdefinierte Stunden (wiederkehrende Wochen)** Der Dienst verfügt über eine zusätzliche Verfügbarkeitsstufe, die weiter eingeschränkt werden kann (zusätzlich zur Einschränkung von Geschäftszeiten oder Stunden mit Mitarbeitern). Verwenden Sie diese Option, wenn Ihr Dienst nur zu einem bestimmten Zeitpunkt bereitgestellt oder ausgeführt werden kann.

    - **Festlegen einer unterschiedlichen Verfügbarkeit für einen Datumsbereich** Diese Einstellung wirkt sich auf die Verfügbarkeit zu einem bestimmten Zeitpunkt anstatt auf eine wiederkehrende Basis aus. Dies kann beispielsweise verwendet werden, wenn ein Computer, der für den Dienst benötigt wird, vorübergehend gewartet und nicht verfügbar ist oder wenn eine Organisation für einen Feiertag geschlossen ist.

20. **Zuweisen von Mitarbeitern** Wählen Sie das Personal aus (sofern Sie der Registerkarte Mitarbeiter Mitarbeiter hinzugefügt haben), die für diesen bestimmten Dienst gebucht werden. Wenn Sie keine einzelnen Mitarbeiter auswählen, werden alle Mitarbeiter dem Dienst zugewiesen.