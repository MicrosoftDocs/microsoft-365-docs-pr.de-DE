---
title: Finden und Freigeben von Nachrichten in Quarantäne als Administrator
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ab95bf17-bb09-4dd1-9990-ddd02ddecf05
ms.collection:
- M365-security-compliance
description: In diesem Thema wird beschrieben, wie Administratoren von Exchange Online und Exchange Online Protection (EOP) isolierte Nachrichten finden, freigeben und Berichte dazu erstellen, die sich im Exchange Admin Center (EAC).
ms.openlocfilehash: e60c0ae87f050b6e72e53b6069a61cd52df0641a
ms.sourcegitcommit: 2468bcb01625f97a322459814d81b9faad717859
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/05/2019
ms.locfileid: "39871841"
---
# <a name="find-and-release-quarantined-messages-as-an-administrator"></a>Finden und Freigeben von Nachrichten in Quarantäne als Administrator

In diesem Thema wird beschrieben, wie Administratoren von Exchange Online und Exchange Online Protection (EOP) isolierte Nachrichten finden, freigeben und Berichte dazu erstellen, die sich im Exchange Admin Center (EAC). Office 365 leitet Nachrichten in Quarantäne, da Sie entweder als Spam identifiziert wurden oder mit einer Nachrichtenfluss Regel (auch als Transportregel bezeichnet) übereinstimmten.

Sie können die Sicherheits #a0 Compliance Center anstelle der Exchange-Verwaltungskonsole verwenden, um diese Aufgaben auch auszuführen. das Quarantäne Portal in der Exchange-Verwaltungskonsole (EAC) ist auf decommisioned festgelegt.  Weitere Informationen finden Sie unter [Quarantäne für e-Mail-Nachrichten in Office 365](https://support.office.com/article/Quarantine-email-messages-in-Office-365-4c234874-015e-4768-8495-98fcccfc639b).

Isolierte Nachrichten werden im EAC auf der Seite **Quarantäne** aufgeführt. Standardmäßig sind die Nachrichten aufsteigend nach Alter im Feld **EMPFANGEN** sortiert. Auch die Werte **ABSENDER**, **BETREFF** und **LÄUFT AB** werden für jede Nachricht aufgelistet. Sie können nach jedem dieser Felder sortieren, indem Sie auf ihre Kopfzeile klicken. Durch ein zweites Klicken auf eine Spaltenüberschrift wird die Sortierreihenfolge umgekehrt. Auf der Seite **Quarantäne** können maximal 500 Nachrichten angezeigt werden.

Sie können eine Liste aller isolierten Nachrichten anzeigen oder durch Angabe von Filterkriterien nach bestimmten Nachrichten suchen (durch Filtern können Sie auch die Anzahl der Ergebnisse verringern, wenn Sie mehr als 500 Nachrichten haben). Nachdem Sie eine bestimmte isolierte Nachricht gesucht und gefunden haben, können Sie nähere Informationen zur Nachricht anzeigen. Des Weiteren können Sie Folgendes:

- Sie können die Nachricht auch für einen oder mehrere Empfänger freigeben und optional als falsch positives Ergebnis (kein Junk) dem Microsoft-Spamanalyseteam melden, das die Nachricht bewertet und analysiert. Abhängig vom Ergebnis der Analyse werden die Filterregeln für Spaminhalte des Diensts angepasst, damit die Nachricht zugestellt werden kann.

- Sie können die Nachricht freigeben und alle zukünftigen Nachrichten von diesem Absender zulassen.

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Bevor Sie dieses Verfahren bzw. diese Verfahren ausführen können, müssen Ihnen die entsprechenden Berechtigungen zugewiesen werden. Informationen zu den von Ihnen benötigten Berechtigungen finden Sie unter "Quarantäne" in den [Features Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions) Thema.

- Sie können auf der Seite **Quarantäne** mehrere Nachrichten auf einmal freizugeben oder melden. Alternativ können Sie dazu ein Windows PowerShellRemoteskript erstellen. Verwenden Sie das [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)-Cmdlet, um nach Nachrichten zu suchen, und das [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)-Cmdlet, um sie freizugeben.

- Informationen zu Tastenkombinationen, die möglicherweise für die Verfahren in diesem Thema gelten, finden Sie unter [Tastenkombinationen für das Exchange Admin Center in Exchange Online](https://docs.microsoft.com/Exchange/accessibility/keyboard-shortcuts-in-admin-center).

> [!TIP]
> Liegt ein Problem vor? Bitten Sie in den Exchange-Foren um Hilfe. Besuchen Sie die Foren unter [Exchange Server](https://go.microsoft.com/fwlink/p/?linkId=60612),[Exchange Online](https://go.microsoft.com/fwlink/p/?linkId=267542) oder [Exchange Online Protection](https://go.microsoft.com/fwlink/p/?linkId=285351).

## <a name="use-advanced-search-to-filter-and-locate-quarantined-messages"></a>Filtern und Auffinden von Nachrichten in Quarantäne anhand der erweiterten Suche

Im Exchange Admin Center (EAC) können Sie mithilfe der erweiterten Suche anhand mehrerer verschiedener Bedingungen nach Elementen in Quarantäne suchen. Sie können diese Bedingungen separat oder in Kombination miteinander verwenden. Die Suche gibt eine Liste von Nachrichten zurück, die mit all Ihren Filterkriterien übereinstimmen.

1. Navigieren Sie im Exchange Admin Center zu **Schutz** \> **Quarantäne**, und klicken Sie dann auf **Erweiterte Suche**.

2. Wählen Sie im Fenster **Erweiterte Suche** eine beliebige Kombination der folgenden Felder aus. Aktivieren Sie das zugehörige Kontrollkästchen, um eine Bedingung auszuwählen. Platzhalter werden nicht unterstützt.

   1. **Nachrichten-ID**: Sie können diesen Parameter verwenden, um eine gezielte Suche nach einer bestimmten Nachricht durchzuführen. Wenn eine bestimmte Nachricht beispielsweise von einem Benutzer in Ihrer Organisation gesendet wird oder für diesen bestimmt ist, aber ihr Ziel nicht erreicht, können Sie mit der Nachrichtenablaufverfolgung nach der Nachricht suchen. Weitere Informationen finden Sie unter [Ausführen einer Nachrichtenablaufverfolgung und Anzeigen der Ergebnisse](https://docs.microsoft.com/exchange/monitoring/trace-an-email-message/run-a-message-trace-and-view-results). Wenn Sie feststellen, dass die Nachricht in Quarantäne gesendet wurde, möglicherweise aufgrund der Übereinstimmung mit einer Regel oder ihrer Identifizierung als Spam, können Sie diese Nachricht einfach in der Quarantäne finden, indem Sie ihre Nachrichten-ID angeben. Dabei müssen Sie die vollständige Zeichenfolge der Nachrichten-ID angeben. Hierzu können auch spitze Klammern (\<\>) gehören.

   2. **Absender-e-Mail-Adresse**: Geben Sie die e-Mail-Adresse der Person an, die die Nachricht gesendet hat.

   3. **E-Mail-Adresse des Empfängers**: Geben Sie die e-Mail-Adresse des beabsichtigten Empfängers der Nachricht an.

   4. **Betreff**: Geben Sie den Text der Betreffzeile der Nachricht an.

   5. **Empfangen**: Sie können auswählen, dass die Nachricht innerhalb der letzten 24 Stunden ( **heute**), innerhalb der letzten 48 Stunden ( **Letzte 2 Tage**), innerhalb der letzten Woche ( **Letzte 7 Tage**) in Quarantäne eingegangen ist, oder Sie können ein benutzerdefiniertes Zeitintervall auswählen, in dem die Nachricht von der Quarantäne empfangen wurde.

   6. **Expires**: Sie können auswählen, dass die Nachricht innerhalb der nächsten 24 Stunden ( **heute**) aus der Quarantäne gelöscht wird, innerhalb der nächsten 48 Stunden ( **Nächste 2 Tage**), innerhalb der nächsten Woche ( **Nächste 7 Tage**), oder Sie können ein benutzerdefiniertes Zeitintervall auswählen, in dem die Nachricht aus der Quarantäne gelöscht wird.

      > [!IMPORTANT]
      > Spam isolierte Nachrichten werden standardmäßig 30 Tage lang in Quarantäne aufbewahrt, während isolierte Nachrichten, die einer e-Mail-Fluss Regel entsprechen, bis zu 30 Tage lang in der Quarantäne aufbewahrt werden, basierend auf dem in der standardmäßigen Inhaltsfilter Richtlinie festgelegten Aufbewahrungszeitraum. Nach dieser Zeitspanne Office 365 die Nachrichten gelöscht und können nicht abgerufen werden. Der Aufbewahrungszeitraum für isolierte Nachrichten, die mit einer e-Mail-Fluss Regel übereinstimmen, kann nicht konfiguriert werden. Der Aufbewahrungszeitraum für Nachrichten mit Spamquarantäne kann jedoch über die Einstellung **Spam für (Tage)** in den Inhaltsfilter Richtlinien beibehalten werden. Weitere Informationen finden Sie unter [Konfigurieren von Spamfilterrichtlinien](configure-your-spam-filter-policies.md).

   7. **Geben** Sie Sie können angeben, ob nach isolierten Nachrichten gesucht werden soll, die als **Spam**identifiziert wurden, oder ob nach Nachrichten gesucht werden soll, die mit einer Nachrichtenfluss Regel übereinstimmen (**Transport Regel**).

3. Klicken Sie auf **OK**, um die erweiterte Suche zu starten.

   > [!NOTE]
   > Um Ihre Suchkriterien zu löschen und alle Nachrichten in der Quarantäne anzuzeigen, deaktivieren Sie im Fenster **Erweiterte Suche** alle Kontrollkästchen, und klicken Sie dann auf **OK**.

Dann wird nach Nachrichten gesucht, und die Ergebnisse, die den angegebenen Kriterien entsprechen, werden an der Benutzeroberfläche angezeigt. Maximal 500 Nachrichten können in der Exchange-Verwaltungskonsole angezeigt werden.

## <a name="view-details-about-a-specific-quarantined-message"></a>Anzeigen von Details zu einer bestimmten Quarantänenachricht

Nachdem Sie auf der Seite **Quarantäne** eine bestimmte isolierte Nachricht gefunden haben, können Sie Details zu dieser anzeigen.

1. Wenn Sie auf der Seite **Quarantäne** eine bestimmte Nachricht auswählen, wird im Detailbereich auf der rechten Seite des Bildschirms eine Zusammenfassung der Eigenschaften dieser Nachricht angezeigt.

   Für **Nachrichtenstatus** sind folgende Werte möglich:

   - **Typ**: gibt an, ob die Nachricht als **Spam** identifiziert wurde oder mit einer Nachrichtenfluss Regel übereinstimmt (**Transport Regel**).

   - **Expires**: das Datum, an dem die Nachricht aus der Quarantäne gelöscht wird.

   Für **Nachrichtendetails** sind folgende Werte möglich:

   - **Absender**: die e-Mail-Adresse der Person, die die Nachricht gesendet hat.

   - **Betreff**: der Text der Betreffzeile der Nachricht.

   - **Received**: das Datum, an dem die Nachricht von der Quarantäne empfangen wurde.

   - **Größe**: die Größe der Nachricht in Kilobyte (KB) oder, wenn die Nachrichtengröße größer als 999 KBS ist, in Megabyte (MB).

   - **Nachrichtenkopfzeile anzeigen**: Klicken Sie auf diesen Link, um das Dialogfeld **Nachrichtenkopfzeile** zu öffnen, in dem Sie den Text der Nachrichtenkopfzeile anzeigen können. Sie können den Text der Nachrichtenkopfzeile auch in die Zwischenablage kopieren und in die [Nachrichtenkopfanalyse](https://testconnectivity.microsoft.com/?tabid=mha) einfügen. Klicken Sie im Tool für de Nachrichtenkopfanalyse auf **Kopfzeilen analysieren**, um Informationen zur Kopfzeile abzurufen.

    > [!TIP]
    > Informationen zu spezifischen, vom Dienst eingefügten Antispam-Nachrichtenkopfzeilenfeldern finden Sie unter [Antispam-Nachrichtenkopfzeilen](anti-spam-message-headers.md).

   - **Vorschau für E-Mail** Klicken Sie auf diesen Link, um den Text der Nachricht zu prüfen.

2. Wenn Sie auf eine Quarantänenachricht doppelklicken, wird das Fenster **Quarantined message** (Quarantänenachricht) geöffnet, und die folgenden Informationen werden angezeigt:

   - **Veröffentlicht für**: eine Liste aller e-Mail-Adressen, für die die Nachricht freigegeben wurde (sofern vorhanden).

   - **Noch nicht freigegeben an**: eine Liste aller e-Mail-Adressen, für die die Nachricht nicht freigegeben wurde (sofern vorhanden). Sie können auf den Link **Freigeben für** klicken, um die Nachricht freizugeben; weitere Informationen zum Freigeben einer Nachricht finden Sie im nächsten Abschnitt.

   - Nach **richten-ID**: die Internet Nachrichten-ID (auch als Client-ID bezeichnet), die in der Kopfzeile der Nachricht gefunden wurde.

   Klicken Sie auf **Schließen**, um zum Hauptfenster für die Quarantäne zurückzukehren.

## <a name="release-messages-from-quarantine"></a>Freigeben von Nachrichten aus der Quarantäne

Wenn Sie Nachrichten für Empfänger freigeben möchten, stehen dazu folgende Möglichkeiten zur Verfügung:

- [Freigeben einer isolierten Nachricht und Zulassen aller zukünftigen Nachrichten vom Absender](#release-a-quarantined-message-and-allow-future-messages-from-the-sender)

- [Freigeben einer isolierten Nachricht für bestimmte Empfänger, ohne sie als falsch positives Ergebnis zu melden](#release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive)

- [Freigeben einer oder mehrerer isolierten Nachrichten für alle Empfänger](#release-one-or-more-quarantined-messages-to-all-recipients)

- [Freigeben einer oder mehrerer isolierten Nachrichten für alle Empfänger und Melden der Nachrichten als falsch positive Ergebnisse](#release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives)

### <a name="release-a-quarantined-message-and-allow-future-messages-from-the-sender"></a>Freigeben einer isolierten Nachricht und Zulassen aller zukünftigen Nachrichten vom Absender

1. Navigieren Sie im Exchange Admin Center zu **Schutz** \> **Quarantäne**.

2. Klicken Sie auf eine Nachricht, um Sie auszuwählen, und klicken Sie dann auf das Symbol **Nachricht freigeben** wie im folgenden Screenshot dargestellt.

   ![Zeigt die Quarantäneseite an, auf der das Symbol zum Freigeben von Nachrichten hervorgehoben und die Freigabeoptionen angezeigt werden](../media/36ee081f-3e30-40c9-8ce3-240cee1970cc.png)

   Wählen Sie **Ausgewählte Nachricht freigeben und Absender zulassen** aus der Dropdownliste aus.

3. Das Dialogfeld **Nachricht freizugeben und Absender zulassen** wird geöffnet. Optional können Sie die Nachricht an Microsoft melden und dann auf **Freigeben und zulassen** klicken. Die Nachricht wird für alle Empfänger freigegeben, an die sie gerichtet ist, und alle zukünftigen Nachrichten von diesem Absender werden zugelassen. Wenn diese Nachricht jedoch aufgrund einer Nachrichtenfluss Regel oder eines blockierten Absenders unter Quarantäne gestellt wurde, wird der Absender weiterhin für zukünftige Nachrichten blockiert.

### <a name="release-a-quarantined-message-to-specific-recipients-without-reporting-it-as-a-false-positive"></a>Freigeben einer isolierten Nachricht für bestimmte Empfänger, ohne sie als falsch positives Ergebnis zu melden

1. Navigieren Sie im Exchange Admin Center zu **Schutz** \> **Quarantäne**.

2. Wählen Sie eine Nachricht aus, klicken Sie auf das Symbol **Nachricht freigeben**, und wählen Sie dann in der Dropdownliste **Nachricht an bestimmte Empfänger freigeben** aus.

3. Wählen Sie im Dialogfeld **Nachricht freigeben** eine der folgenden Optionen aus:

   - **Nachricht für alle Empfänger freigeben** Beachten Sie beim Auswählen dieser Option, dass die Nachricht nur einmal für denselben Empfänger freigegeben werden kann. Hat ein Empfänger die Nachricht bereits zuvor empfangen, wird sie ihm nicht noch einmal zugestellt.

   - **Nachricht für angegebene Empfänger freigeben** Wählen Sie die Empfänger aus, für die die Nachricht freigegeben werden soll. Da eine Nachricht nur einmal für denselben Empfänger freigegeben werden kann, werden in dieser Liste nur die Empfänger aufgeführt, für die die Nachricht noch freigegeben werden kann. Mehrfachauswahl möglich. Klicken Sie anschließend auf **Hinzufügen**.

4. Klicken Sie auf **Freigeben**.

Wenn **Sie auf Aktualisierungs** ![Symbol](../media/ITPro-EAC-RefreshIcon.gif) aktualisieren klicken, um Ihre Daten zu aktualisieren, und dann auf die Nachricht doppelklicken, sollten Sie sehen, dass Sie für die vorgesehenen Empfänger freigegeben wurde.

### <a name="release-one-or-more-quarantined-messages-to-all-recipients"></a>Freigeben einer oder mehrerer isolierten Nachrichten für alle Empfänger

1. Navigieren Sie im Exchange Admin Center zu **Schutz** \> **Quarantäne**.

2. Klicken Sie auf eine Nachricht, um sie auszuwählen, oder verwenden Sie die UMSCHALTTASTE, um mehrere Nachrichten auszuwählen. Klicken Sie dann auf das Symbol **Nachricht freigeben**.

3. Wählen Sie in der Dropdownliste **Ausgewählte Nachrichten für alle Empfänger freigeben**.

4. Es wird ein Dialogfeld mit einer Warnung geöffnet. Lesen Sie die Warnung, und wählen Sie **Ja**, wenn Sie fortfahren möchten. Beachten Sie beim Auswählen dieser Option, dass die Nachricht nur einmal für denselben Empfänger freigegeben werden kann. Hat ein Empfänger die Nachricht bereits zuvor empfangen, wird sie ihm nicht noch einmal zugestellt.

### <a name="release-one-or-more-quarantined-messages-to-all-recipients-and-report-false-positives"></a>Freigeben einer oder mehrerer isolierten Nachrichten für alle Empfänger und Melden der Nachrichten als falsch positive Ergebnisse

1. Navigieren Sie im Exchange Admin Center zu **Schutz** \> **Quarantäne**.

2. Klicken Sie auf eine Nachricht, um sie auszuwählen, oder verwenden Sie die UMSCHALTTASTE, um mehrere Nachrichten auszuwählen. Klicken Sie dann auf das Symbol **Nachricht freigeben**.

3. Wählen Sie in der Dropdownliste **Ausgewählte Nachrichten freigeben und als falsch positive Ergebnisse melden**.

4. Es wird ein Dialogfeld mit einer Warnung geöffnet. Lesen Sie die Warnung, und wählen Sie **Ja**, wenn Sie fortfahren möchten. Beachten Sie beim Auswählen dieser Option, dass die Nachricht nur einmal für denselben Empfänger freigegeben werden kann. Hat ein Empfänger die Nachricht bereits zuvor empfangen, wird sie ihm nicht noch einmal zugestellt.

   Wenn Sie diese Option auswählen, wird die Nachricht für alle Empfänger freigegeben, die sie noch nicht erhalten haben. Falls es sich um eine Nachricht in der Spamquarantäne handelt, wird sie außerdem dem Microsoft-Spamanalyseteam gemeldet, das die Nachricht bewertet und analysiert. Abhängig vom Ergebnis der Analyse werden die Filterregeln für Spaminhalte des Diensts angepasst, damit die Nachricht zugestellt werden kann.

> [!TIP]
> Stellen Sie durch folgende Schritte in [Sicherstellen, dass eine Nachricht nicht als Spam gekennzeichnet wird](how-to-help-ensure-that-a-message-isn-t-marked-as-spam.md) sicher, dass eine Nachricht nicht als Spam markiert wird.

Wenn Sie auf das Symbol **Aktualisieren**![Aktualisieren (Symbol)](../media/ITPro-EAC-RefreshIcon.gif) klicken, um Ihre Daten zu aktualisieren, und dann auf die Nachricht doppelklicken, sollte die Nachricht an die beabsichtigten Empfänger freigegeben werden.

## <a name="for-more-information"></a>Weitere Informationen

[Häufig gestellte Fragen (FAQ) zur Quarantäne](quarantine-faq.md)
