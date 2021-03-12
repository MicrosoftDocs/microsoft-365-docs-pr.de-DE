---
title: Nachrichtenablaufverfolgung im Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
ms.custom:
- seo-marvel-apr2020
description: Administratoren können die Nachrichtenverfolgung im Security & Compliance Center verwenden, um herauszufinden, was mit Nachrichten passiert ist.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 9c3f7e4bc9624b9fae48074203da525d7a504a12
ms.sourcegitcommit: 06d9e056eabfbac8fafe66cc32907b33d4ae8253
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/12/2021
ms.locfileid: "50741575"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Nachrichtenablaufverfolgung im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

## <a name="message-trace-features"></a>Nachrichtenverfolgungsfeatures

Nachrichtenverfolgung im Security & Compliance Center folgt E-Mail-Nachrichten, während sie durch Ihre Exchange Online-Organisation reisen. Sie können bestimmen, ob eine Nachricht vom Dienst empfangen, abgelehnt, zurückgestellt oder zugestellt wurde. Außerdem werden die Aktionen der Nachricht gezeigt, bevor diese ihren finalen Status erreicht hat.

Die Nachrichtenverfolgung im Security & Compliance Center verbessert die ursprüngliche Nachrichtenverfolgung, die im Exchange Admin Center (EAC) verfügbar war. Sie können die Informationen aus der Nachrichtenablaufverfolgung verwenden, um Benutzerfragen effizient zu beantworten, was mit Nachrichten passiert ist, Probleme mit dem Nachrichtenfluss zu beheben und Richtlinienänderungen zu überprüfen.

> [!NOTE]
>
> - Um eine Nachrichtenverfolgung zu erstellen, müssen Sie Mitglied der Rollengruppen Organisationsverwaltung, Complianceverwaltung oder HelpDesk sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).
>
> - Die maximale Anzahl von Nachrichten, die in den Ergebnissen angezeigt werden, hängt vom ausgewählten Berichtstyp ab (Weitere Informationen finden Sie im Abschnitt [Berichtstyp](#choose-report-type) auswählen). Das [Cmdlet Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/get-historicalsearch) in Exchange Online PowerShell oder eigenständiger EOP PowerShell gibt alle Nachrichten in den Ergebnissen zurück.

## <a name="open-message-trace"></a>Öffnen der Nachrichtenverfolgung

1. Öffnen Sie das Security & Compliance Center unter <https://protection.office.com> .

2. Erweitern **Sie den Nachrichtenfluss,** und wählen Sie **dann Nachrichtenablaufverfolgung aus.**

## <a name="message-trace-page"></a>Seite "Nachrichtenverfolgung"

Von hier aus können Sie eine neue Standardverfolgung starten, indem Sie auf die Schaltfläche **Ablaufverfolgung starten** klicken. Dadurch werden alle Nachrichten für alle Absender und Empfänger für die letzten zwei Tage gesucht. Sie können auch eine der gespeicherten Abfragen aus den verfügbaren Abfragekategorien verwenden und sie entweder wie vorhanden ausführen oder als Ausgangspunkt für Ihre eigenen Abfragen verwenden:

- **Standardabfragen:** Von Microsoft 365 bereitgestellte integrierte Abfragen.

- **Benutzerdefinierte Abfragen:** Abfragen, die von Administratoren in Ihrer Organisation zur zukünftigen Verwendung gespeichert werden.

- **Automatisch gespeicherte Abfragen:** Die letzten zehn zuletzt ausgeführten Abfragen. Diese Liste macht es einfach, die Stelle zu finden, an der Sie auf der Stelle aufbließen.

Außerdem finden Sie auf dieser Seite einen Abschnitt **zum** Herunterladen von Berichten für die von Ihnen übermittelten Anforderungen sowie die Berichte selbst, wenn sie zum Download verfügbar sind.

## <a name="options-for-a-new-message-trace"></a>Optionen für eine neue Nachrichtenverfolgung

### <a name="filter-by-senders-and-recipients"></a>Filtern nach Absendern und Empfängern

Die Standardwerte sind **Alle Absender** und **Alle** Empfänger. Sie können jedoch die folgenden Felder verwenden, um die Ergebnisse zu filtern:

- **By these people**: Click in this field to select one or more senders from your organization. Sie können auch mit der Eingabe eines Namens beginnen, und die Elemente in der Liste werden nach dem Typ gefiltert, ähnlich wie sich eine Suchseite verhält.

- **Für diese Personen**: Klicken Sie in dieses Feld, um einen oder mehrere Empfänger in Ihrer Organisation auszuwählen.

> [!NOTE]
>
> - Sie können auch die E-Mail-Adressen externer Absender und Empfänger eingeben. Platzhalter werden unterstützt (z. B. ), sie können jedoch nicht mehrere Platzhaltereinträge gleichzeitig im gleichen `*@contoso.com` Feld verwenden.
>
> - Sie können mehrere Absender oder Empfängerlisten einfügen, die durch Semikolons ( ) getrennt `;` sind. Leerzeichen ( `\s` ), Wagenrücklauf ( `\r` ) oder nächste Zeilen ( `\n` ).

### <a name="time-range"></a>Zeitbereich

Der Standardwert ist **2 Tage,** Sie können jedoch Datums-/Uhrzeitbereiche von bis zu 90 Tagen angeben. Berücksichtigen Sie beim Verwenden von Datums-/Uhrzeitbereichen die folgenden Probleme:

- Standardmäßig wählen Sie den Zeitraum in der **Schieberegleransicht** mithilfe einer Zeitlinie aus. Sie können nur die angezeigten Tages- oder Uhrzeiteinstellungen auswählen. Wenn Sie versuchen, einen Zwischenwert auszuwählen, wird die Start-/End-Blase an die nächste angezeigte Einstellung einrasten.

  ![Ein Schieberegler-Zeitbereich in einer neuen Nachrichtenverfolgung im Security & Compliance Center](../../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

  Sie können jedoch auch  zur benutzerdefinierten Ansicht wechseln, in der Sie die Werte **Startdatum** und Enddatum (einschließlich Uhrzeiten) angeben können, und Sie können auch die Zeitzone für den Datums-/Uhrzeitbereich auswählen.   Beachten Sie, **dass die Zeitzoneneinstellung** sowohl für Die Abfrageeingaben als auch für die Abfrageergebnisse gilt.

  ![Ein benutzerdefinierter Zeitraum in einer neuen Nachrichtenverfolgung im Security & Compliance Center](../../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

  Für 10 Tage oder weniger sind die Ergebnisse sofort als **Zusammenfassungsbericht** verfügbar. Wenn Sie einen Zeitraum angeben, der noch etwas größer als 10 Tage ist, werden die Ergebnisse verzögert, da sie nur als herunterladbare CSV-Datei **verfügbar** sind ( Erweiterte Zusammenfassung oder erweiterte **Berichte).**

  Weitere Informationen zu den verschiedenen Berichtstypen finden Sie im Abschnitt [Berichtstyp](#choose-report-type) auswählen in diesem Artikel.

  > [!NOTE]
  > Erweiterte Zusammenfassungsberichte und erweiterte Berichte werden mithilfe archivierter Nachrichtenverfolgungsdaten vorbereitet, und es kann bis zu mehrere Stunden dauern, bis Ihr Bericht zum Download verfügbar ist. Je nachdem, wie viele andere Administratoren auch Berichtsanforderungen zur gleichen Zeit übermittelt haben, können Sie auch eine Verzögerung bemerken, bevor die Verarbeitung für Ihre Anforderung in der Warteschlange beginnt.

- Beim Speichern einer Abfrage in **der Schieberegleransicht** wird der relative Zeitraum (z. B. 3 Tage ab heute) gespart. Beim Speichern einer Abfrage **in** der benutzerdefinierten Ansicht wird der absolute Datums-/Uhrzeitbereich (z. B. 2018-05-06 13:00 bis 2018-05-08 18:00) speichert.

### <a name="more-search-options"></a>Weitere Suchoptionen

#### <a name="delivery-status"></a>Zustellungsstatus

Sie können den Standardwert **Alle** ausgewählt lassen, oder Sie können einen der folgenden Werte auswählen, um die Ergebnisse zu filtern:

- **Zugestellt**: Die Nachricht wurde erfolgreich an das beabsichtigte Ziel übermittelt.

- **Ausstehend**: Die Zustellung der Nachricht wird versucht oder erneut versucht.

- **Erweitert:** Ein Verteilergruppenempfänger wurde vor der Zustellung an die einzelnen Mitglieder der Gruppe erweitert.

- **Fehler:** Die Nachricht wurde nicht zugestellt.

- **Quarantäne:** Die Nachricht wurde isoliert (als Spam, Massen-E-Mail oder Phishing). Weitere Informationen finden Sie unter [Quarantined email messages in EOP](quarantine-email-messages.md).

- **Als Spam gefiltert:** Die Nachricht wurde als Spam identifiziert und abgelehnt oder blockiert (nicht isoliert).

- **Status abrufen:** Die Nachricht wurde kürzlich von Microsoft 365 empfangen, es sind jedoch noch keine weiteren Statusdaten verfügbar. Check back in a few minutes.

> [!NOTE]
> Die Werte **Pending,** **Quarantined** und **Filter as spam** sind nur für Suchaufträge verfügbar, die weniger als 10 Tage dauern. Außerdem kann zwischen dem tatsächlichen und dem gemeldeten Zustellungsstatus eine Verzögerung von 5 bis 10 Minuten liegen.

#### <a name="message-id"></a>Nachrichten-ID

Dies ist die Internetnachrichten-ID (auch als Client-ID bezeichnet), die im **Nachrichtenkopffeld Message-ID:** im Nachrichtenkopf gefunden wird. Benutzer können Ihnen diesen Wert geben, um bestimmte Nachrichten zu untersuchen.

Dieser Wert ist für die Lebensdauer der Nachricht konstant. Für Nachrichten, die in Microsoft 365 oder Exchange erstellt wurden, hat der Wert das Format , einschließlich der `<GUID@ServerFQDN>` eckigen Klammern ( \< \> ). Zum Beispiel, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Andere Messagingsysteme verwenden möglicherweise unterschiedliche Syntax oder Werte. Dieser Wert sollte eindeutig sein, aber nicht alle E-Mail-Systeme halten sich strikt an diese Anforderung. Wenn das **Kopfzeilenfeld Message-ID:** nicht vorhanden ist oder für eingehende Nachrichten aus externen Quellen leer ist, wird ein beliebiger Wert zugewiesen.

Wenn Sie die Ergebnisse mithilfe der **Nachrichten-ID** filtern, müssen Sie unbedingt die vollständige Zeichenfolge einschließlich aller eckigen Klammern angeben.

#### <a name="direction"></a>Direction

Sie können den Standardwert **Alle** ausgewählt lassen, oder Sie können **eingehende** Nachrichten (nachrichten, die an Empfänger in Ihrer Organisation gesendet werden) oder **Ausgehend** (Nachrichten, die von Benutzern in Ihrer Organisation gesendet werden) auswählen, um die Ergebnisse zu filtern.

#### <a name="original-client-ip-address"></a>Ursprüngliche Client-IP-Adresse

Sie können die Ergebnisse nach Client-IP-Adresse filern, um gehackte Computer zu untersuchen, die große Mengen an Spam oder Schadsoftware senden. Obwohl die Nachrichten möglicherweise von mehreren Absendern stammen, generiert wahrscheinlich derselbe Computer alle Nachrichten.

> [!NOTE]
> Die Client-IP-Adressinformationen sind nur für 10 Tage  verfügbar  und nur in der erweiterten Zusammenfassung oder erweiterten Berichten (herunterladbare CSV-Dateien) verfügbar.

### <a name="choose-report-type"></a>Berichtstyp auswählen

Die verfügbaren Berichtstypen sind:

- **Zusammenfassung**: Verfügbar, wenn der Zeitraum weniger als 10 Tage beträgt und keine zusätzlichen Filteroptionen erforderlich sind. Die Ergebnisse sind unmittelbar nach dem Klicken auf **Suchen verfügbar.** Der Bericht gibt bis zu 20.000 Ergebnisse zurück.

- **Erweiterte Zusammenfassung** oder **Erweitert:** Diese Berichte sind nur als herunterladbare CSV-Dateien verfügbar und erfordern eine oder mehrere der folgenden Filteroptionen unabhängig vom Zeitraum: Von **diesen** Personen , **An** diese Personen oder **Nachrichten-ID**. Sie können Platzhalter für die Absender oder Empfänger verwenden (z. B. \* @contoso.com). Der Erweiterte Zusammenfassende Bericht gibt bis zu 50.000 Ergebnisse zurück. Der erweiterte Bericht gibt bis zu 1000 Ergebnisse zurück.

> [!NOTE]
>
> - Erweiterte Zusammenfassungsberichte und erweiterte Berichte werden mithilfe archivierter Nachrichtenverfolgungsdaten vorbereitet, und es kann bis zu mehrere Stunden dauern, bis Ihr Bericht heruntergeladen werden kann. Je nachdem, wie viele andere Administratoren auch Berichtsanforderungen zur gleichen Zeit übermittelt haben, können Sie auch eine Verzögerung bemerken, bevor Die Anforderung in der Warteschlange verarbeitet wird.
>
> - Sie können zwar eine erweiterte Zusammenfassung oder einen erweiterten Bericht für einen beliebigen Datums-/Uhrzeitbereich auswählen, aber in der Regel stehen die letzten vier Stunden archivierter Daten für diese beiden Berichtstypen noch nicht zur Verfügung.
>
> - Die maximale Größe für einen herunterladbaren Bericht beträgt 500 MB. Wenn ein herunterladbarer Bericht mehr als 500 MB überschreitet, können Sie den Bericht nicht in Excel oder Editor öffnen.

Wenn Sie auf **Weiter** klicken, wird eine Zusammenfassungsseite mit den ausgewählten Filteroptionen, einem eindeutigen (bearbeitbaren) Titel für den Bericht und der E-Mail-Adresse angezeigt, die die Benachrichtigung empfängt, wenn die Nachrichtenverfolgung abgeschlossen ist (auch bearbeitbar und muss sich in einer der akzeptierten Domänen Ihrer Organisation befinden). Klicken **Sie auf Bericht vorbereiten,** um die Nachrichtenverfolgung zu übermitteln. Auf der **Hauptseite Nachrichtenverfolgung** sehen Sie den Status des Berichts im Abschnitt **Herunterladbare Berichte.**

Weitere Informationen zu den Informationen, die in den verschiedenen Berichtstypen zurückgegeben werden, finden Sie im nächsten Abschnitt.

## <a name="message-trace-results"></a>Ergebnisse der Nachrichtenverfolgung

Die verschiedenen Berichtstypen geben unterschiedliche Informationsstufen zurück. Die Informationen, die in den verschiedenen Berichten verfügbar sind, werden in den folgenden Abschnitten beschrieben.

### <a name="summary-report-output"></a>Zusammenfassungsberichtausgabe

Nach dem Ausführen der Nachrichtenverfolgung werden die Ergebnisse aufgelistet, sortiert nach absteigenden Datum/Uhrzeit (zuletzt zuerst).

![Zusammenfassungsberichtsergebnisse für die Nachrichtenverfolgung im Security & Compliance Center](../../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

Der Zusammenfassende Bericht enthält die folgenden Informationen:

- **Date**: Das Datum und die Uhrzeit, zu der die Nachricht vom Dienst empfangen wurde, unter Verwendung der konfigurierten UTC-Zeitzone.

- **Absender**: Die E-Mail-Adresse des Absenders ( @ *Aliasdomäne*).

- **Recipient**: Die E-Mail-Adresse des Empfängers oder empfängers. Für eine Nachricht, die an mehrere Empfänger gesendet wird, gibt es eine Zeile pro Empfänger. Wenn es sich bei dem Empfänger um eine Verteilergruppe, eine dynamische Verteilergruppe oder eine E-Mail-aktivierte Sicherheitsgruppe handelt, ist die Gruppe der erste Empfänger, und dann befindet sich jedes Mitglied der Gruppe in einer separaten Zeile.

- **Betreff**: Die ersten 256 Zeichen des Felds **Betreff:** der Nachricht.

- **Status**: Diese Werte werden im Abschnitt [Zustellungsstatus](#delivery-status) beschrieben.

Standardmäßig sind die ersten 250 Ergebnisse geladen und sofort verfügbar. Wenn Sie einen Bildlauf nach unten durchführen, gibt es eine leichte Pause, wenn der nächste Ergebnisbatch geladen wird. Anstelle eines Bildlaufs können Sie auf **Alle** Laden klicken, um alle Ergebnisse bis zu maximal 10.000 zu laden.

Sie können auf die Spaltenkopfzeilen klicken, um die Ergebnisse nach den Werten in dieser Spalte in aufsteigender oder absteigender Reihenfolge zu sortieren.

Sie können auf **Ergebnisse filtern klicken,** um die Ergebnisse nach einer oder mehreren Spalten zu filtern.

Sie können die Ergebnisse exportieren, nachdem Sie eine  oder mehrere Zeilen ausgewählt haben, indem Sie auf Ergebnisse exportieren klicken und dann **Alle** Ergebnisse exportieren, **geladene** Ergebnisse exportieren oder ausgewählte exportieren **auswählen.**

#### <a name="find-related-records-for-this-message"></a>Suchen verwandter Datensätze für diese Nachricht

Verwandte Nachrichtendatensätze sind Datensätze, die dieselbe Nachrichten-ID gemeinsam verwendet haben. Denken Sie daran, dass auch eine einzelne Nachricht, die zwischen zwei Personen gesendet wird, mehrere Datensätze generieren kann. Die Anzahl der Datensätze nimmt zu, wenn die Nachricht von der Verteilergruppenerweiterung, Weiterleitung, Nachrichtenflussregeln (auch als Transportregeln bezeichnet) usw. betroffen ist.

Nachdem Sie das Kontrollkästchen einer Zeile ausgewählt haben, können Sie  verwandte Datensätze für die Nachricht  finden, indem Sie auf die schaltfläche Suchen klicken, die angezeigt wird, oder indem Sie Weitere Optionen Weitere Informationen zu verwandten Datensätzen für diese Nachricht ![ ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **auswählen.**

Weitere Informationen zur Nachrichten-ID finden Sie weiter oben in diesem Artikel im Abschnitt Nachrichten-ID.

#### <a name="message-trace-details"></a>Details zur Nachrichtenverfolgung

In der Zusammenfassungsberichtausgabe können Sie Details zu einer Nachricht mithilfe einer der folgenden Methoden anzeigen:

- Wählen Sie die Zeile aus (klicken Sie auf eine beliebige Stelle in der Zeile mit Ausnahme des Kontrollkästchens).

- Aktivieren Sie das Kontrollkästchen der Zeile, und klicken Sie auf **Weitere Optionen** ![ Weitere ](../../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Nachrichtendetails anzeigen**.

   ![Details nach dem Doppelklicken auf eine Zeile in der Nachrichtenverfolgung des Sammelberichts im Security & Compliance Center](../../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

Die Details zur Nachrichtenverfolgung enthalten die folgenden zusätzlichen Informationen, die im Zusammenfassenden Bericht nicht vorhanden sind:

- **Nachrichtenereignisse:** Dieser Abschnitt enthält Klassifizierungen, die helfen, die Aktionen zu kategorisieren, die der Dienst für Nachrichten übernimmt. **Einige der interessanteren Ereignisse,** auf die Sie stoßen können, sind:

  - **Receive**: Die Nachricht wurde vom Dienst empfangen.

  - **Senden**: Die Nachricht wurde vom Dienst gesendet.

  - **Fail**: Die Nachricht konnte nicht zugestellt werden.

  - **Zugestellt:** Die Nachricht wurde an ein Postfach zugestellt.

  - **Expand**: Die Nachricht wurde an eine Verteilergruppe gesendet, die erweitert wurde.

  - **Übertragung:** Empfänger wurden aufgrund von Inhaltskonvertierung, Beschränkungen von Nachrichtenempfängern oder Agents in eine bifurcierte Nachricht verschoben.

  - **Zurückgestellt:** Die Nachrichtenzustellung wurde verschoben und kann später erneut versucht werden.

  - **Resolved**: Die Nachricht wurde basierend auf einer Active Directory-Suche an eine neue Empfängeradresse umgeleitet. Wenn dies geschieht, wird die ursprüngliche Empfängeradresse zusammen mit dem abschließenden Zustellungsstatus in der Nachrichtenablaufverfolgung einer separaten Zeile aufgeführt.

  > [!NOTE]
  > 
  > - Eine ungleichmäßige Nachricht, die erfolgreich zugestellt wird, generiert mehrere **Ereigniseinträge** in der Nachrichtenverfolgung.
  > 
  > - Diese Liste soll nicht vollständig sein. Beschreibungen von weiteren Ereignissen finden Sie unter [Ereignistypen im Nachrichtenverfolgungsprotokoll](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log). Beachten Sie, dass dieser Link ein Exchange Server (lokales Exchange)-Thema ist.

- **Weitere Informationen**: Dieser Abschnitt enthält die folgenden Details:

  - **Nachrichten-ID**: Dieser Wert wird weiter oben in diesem Artikel im Abschnitt [Nachrichten-ID](#message-id) beschrieben. Zum Beispiel, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

  - **Nachrichtengröße**

  - **Von IP**: Die IP-Adresse des Computers, der die Nachricht gesendet hat. Für ausgehende Nachrichten, die von Exchange Online gesendet wurden, wird kein Wert angegeben.

  - **To IP**: The IP address or addresses where the service attempted to deliver the message. Wenn die Nachricht mehrere Empfänger hat, werden diese angezeigt. Für eingehende Nachrichten, die an Exchange Online gesendet wurden, wird kein Wert angegeben.

### <a name="enhanced-summary-reports"></a>Erweiterte Zusammenfassungsberichte

Verfügbare (abgeschlossene) Erweiterte Zusammenfassungsberichte sind im Abschnitt **Herunterladbare Berichte** am Anfang der Nachrichtenverfolgung verfügbar. Die folgenden Informationen sind im Bericht verfügbar:

- **origin_timestamp**: Datum und Uhrzeit, zu dem die Nachricht vom Dienst unter Verwendung der konfigurierten <sup>*</sup> UTC-Zeitzone empfangen wurde.

- **sender_address**: Die E-Mail-Adresse des Absenders ( @ *Aliasdomäne*).

- **Recipient_status**: Der Status der Zustellung der Nachricht an den Empfänger. Wenn die Nachricht an mehrere Empfänger gesendet wurde, werden alle Empfänger und der entsprechende Status im Format angezeigt: \<*email address*\> ## \<*status*\> . Beispiel:

  - **##Receive, Send** bedeutet, dass die Nachricht vom Dienst empfangen und an das beabsichtigte Ziel gesendet wurde.

  - **##Receive, Fail** bedeutet, dass die Nachricht vom Dienst empfangen wurde, aber die Zustellung an das beabsichtigte Ziel fehlgeschlagen ist.

  - **##Receive, Deliver** bedeutet, dass die Nachricht vom Dienst empfangen und an das Postfach des Empfängers zugestellt wurde.

- **message_subject**: Die ersten 256 Zeichen des **Betrefffelds** der Nachricht.

- **total_bytes**: Die Größe der Nachricht in Bytes, einschließlich Anlagen.

- **message_id**: Dieser Wert wird weiter oben in diesem Artikel im Abschnitt [Nachrichten-ID](#message-id) beschrieben. Zum Beispiel, `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id**: Ein eindeutiger Nachrichten-ID-Wert, der in allen Kopien der Nachricht beibehalten wird, die aufgrund von Verfuellung oder Erweiterung von Verteilergruppen erstellt werden können. Ein Beispielwert ist `1341ac7b13fb42ab4d4408cf7f55890f` .

- **original_client_ip**: Die IP-Adresse des Clients des Absenders.

- **directionality**: Gibt an, ob die Nachricht eingehenden (1) an Ihre Organisation gesendet wurde oder ob sie ausgehend (2) von Ihrer Organisation gesendet wurde.

- **connector_id**: Der Name des Quell- oder Zielconnector. Weitere Informationen zu Connectors in Exchange Online finden Sie unter [Configure mail flow using connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

- **delivery_priority**: Gibt an, ob die Nachricht mit der Priorität <sup>*</sup> **"Hoch",** **"Niedrig"** oder **"Normal" gesendet** wurde.

<sup>*</sup> Diese Eigenschaften sind nur in erweiterten Zusammenfassungsberichten verfügbar.

### <a name="extended-reports"></a>Erweiterte Berichte

Verfügbare (abgeschlossene) Erweiterte Berichte sind im Abschnitt **Herunterladbare Berichte** am Anfang der Nachrichtenverfolgung verfügbar. Praktisch alle Informationen aus einem erweiterten Zusammenfassenden Bericht sind in einem erweiterten Bericht verfügbar (mit Ausnahme von origin_timestamp **und** **delivery_priority**). Die folgenden zusätzlichen Informationen sind nur in einem erweiterten Bericht verfügbar:

- **client_ip**: Die IP-Adresse des E-Mail-Servers oder Messagingclients, der die Nachricht übermittelt hat.

- **client_hostname**: Der Hostname oder FQDN des E-Mail-Servers oder Messagingclients, der die Nachricht übermittelt hat.

- **server_ip**: Die IP-Adresse des Quell- oder Zielservers.

- **server_hostname**: Der Hostname oder FQDN des Zielservers.

- **source_context**: Zusätzliche Informationen, die dem **Quellfeld zugeordnet** sind. Beispiel:

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **source**: Die Exchange Online-Komponente, die für das Ereignis verantwortlich ist. Beispiel:

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id**: Diese entsprechen den **Message-Ereigniswerten,** die im Abschnitt Suchen verwandter Datensätze [für diese Nachricht erläutert](#find-related-records-for-this-message) werden.

- **internal_message_id**: Eine Nachrichten-ID, die vom Exchange Online-Server zugewiesen wird, der die Nachricht derzeit verarbeitet.

- **recipient_address**: Die E-Mail-Adressen der Empfänger der Nachricht. Mehrere E-Mail-Adressen sind durch ein Semikolon (;) getrennt.

- **recipient_count**: Die Gesamtanzahl der Empfänger in der Nachricht.

- **related_recipient_address**: Wird mit , und -Ereignissen zum Anzeigen anderer E-Mail-Empfängeradressen verwendet, `EXPAND` die der Nachricht zugeordnet `REDIRECT` `RESOLVE` sind.

- **reference**: Dieses Feld enthält zusätzliche Informationen für bestimmte Ereignistypen. Beispiel:

  - **DSN**: Enthält den Berichtslink, bei dem es sich um den **message_id-Wert** der zugeordneten Zustellungsstatusbenachrichtigung (auch als DSN, Unzustellbarkeitsbericht, Unzustellbarkeitsbericht oder Unzustellbarkeitsnachricht bezeichnet) handelt, wenn ein DSN nach diesem Ereignis generiert wird. Wenn es sich um eine DSN-Nachricht handelt, enthält dieses Feld den message_id der ursprünglichen Nachricht, für die der DSN generiert wurde. 

  - **EXPAND**: Enthält den **related_recipient_address** der zugehörigen Nachrichten.

  - **RECEIVE**: Kann den **message_id** der zugehörigen Nachricht enthalten, wenn die Nachricht von anderen Prozessen generiert wurde (z. B. Posteingangsregeln).

  - **SEND**: Enthält **internal_message_id** wert aller DSN-Nachrichten.

  - **TRANSFER**: Enthält den **internal_message_id** der Nachricht, die gegabelt wird (z. B. durch Inhaltskonvertierung, Nachrichtenempfängerbeschränkungen oder Agents).

  - **MAILBOXRULE**: Enthält **den internal_message_id** der eingehenden Nachricht, die dazu führte, dass die Posteingangsregel die ausgehende Nachricht generierte.

    Für andere Ereignistypen ist dieses Feld zumeist leer.

- **return_path**: Die durch den Befehl **MAIL FROM** angegebene E-Mail-Adresse, die die Nachricht gesendet hat. Obwohl dieses Feld nie leer ist, kann der Wert der Null-Absenderadresse als dargestellt `<>` werden.

- **message_info**: Zusätzliche Informationen zur Nachricht. Beispiel:

  - Die Datums-/Uhrzeit der Nachrichtenherkunft in UTC für `DELIVER` und `SEND` Ereignisse. Die Ursprungsdatumszeit ist der Zeitpunkt, zu dem die Nachricht zum ersten Mal in die Exchange Online-Organisation eingegeben wurde. Die UTC-Datums-Uhrzeit wird im Datums-Uhrzeit-Format iso 8601 dargestellt: , wobei = Jahr, = Monat, = Tag den Anfang der Zeitkomponente `yyyy-mm-ddThh:mm:ss.fffZ` `yyyy` `mm` `dd` `T` angibt, `hh` = Stunde, `mm` = Minute, = Sekunde, `ss` = `fff` `Z` `Zulu` Bruchteile einer Sekunde, und bedeutet , was eine weitere Möglichkeit zum Bezeichnen von UTC ist.

  - Authentifizierungsfehler. Beispielsweise können der Wert und der Authentifizierungstyp angezeigt werden, der beim `11a` Aufgetretenen des Authentifizierungsfehlers verwendet wurde.

- **tenant_id**: Ein GUID-Wert, der die Exchange Online-Organisation darstellt (z. B. `39238e87-b5ab-4ef6-a559-af54c6b07b42` ).

- **original_server_ip**: Die IP-Adresse des ursprünglichen Servers.

- **custom_data**: Enthält Daten zu bestimmten Ereignistypen. Weitere Informationen finden Sie in den folgenden Abschnitten.

#### <a name="custom_data-values"></a>custom_data-Werte

Das **custom_data** für ein Ereignis wird von einer Vielzahl von `AGENTINFO` Exchange Online-Agents zum Protokollieren von Nachrichtenverarbeitungsdetails verwendet. Einige der interessanteren Agents werden in den folgenden Abschnitten beschrieben.

#### <a name="spam-filter-agent"></a>Spamfilter-Agent

Ein **custom_data,** der mit `S:SFA` beginnt, ist vom Spamfilter-Agent. Die wichtigsten Details werden in der folgenden Tabelle beschrieben:

****

|Wert|Beschreibung|
|---|---|
|`SFV=NSPM`|Die Nachricht wurde als "Nicht-Spam" markiert und an die vorgesehenen Empfänger gesendet.|
|`SFV=SPM`|Die Nachricht wurde von der Antispamfilterung (auch als Inhaltsfilterung bezeichnet) als Spam markiert.|
|`SFV=BLK`|Die Filterung wurde übergangen, und die Nachricht wurde gesperrt, da sie von einem gesperrten Absender stammt.|
|`SFV=SKS`|Die Nachricht wurde vor der Verarbeitung durch die Antispamfilterung als Spam markiert. Dies beinhaltet Nachrichten, bei denen die Nachricht einer Nachrichtenflussregel (auch als Transportregel bezeichnet) entsprach, die diese automatisch als Spam markiert und alle zusätzlichen Filterungen umgeht.|
|`SCL=<number>`|Weitere Informationen zu den verschiedenen SCL-Werten und deren Bedeutung finden Sie unter [SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md).|
|`PCL=<number>`|Der PCL-Wert (Phishing Confidence Level) der Nachricht. Diese Werte können auf die gleiche Weise interpretiert werden wie die in [SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md) dokumentierten SCL-Werte.  |
|`DI=SB`|Der Absender der Nachricht wurde blockiert.|
|`DI=SQ`|Die Nachricht wurde unter Quarantäne gestellt.|
|`DI=SD`|Die Nachricht wurde gelöscht.|
|`DI=SJ`|Die Nachricht wurde an den Ordner "Junk-E-Mail" des Empfängers gesendet.|
|`DI=SN`|Die Nachricht wurde durch den normalen Pool für ausgehende Zustellungen geleitet.|
|`DI=SO`|Die Nachricht wurde durch den Pool für besonders riskante Zustellungen geleitet. Weitere Informationen finden Sie unter [Zustellungspool mit höherem Risiko für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md).|
|`SFS=[a]|SFS=[b]`|Dies bedeutet, dass Übereinstimmungen mit den Spam-Regeln gefunden wurden.|
|`IPV=CAL`|Die Nachricht wurde durch die Spam-Filter gelassen, weil die IP-Adrese in einer IP-Zulassungsliste im Verbindungsfilter angegeben wurde.|
|`H=<EHLOstring>`|Die HELO- oder EHLO-Zeichenfolge des verbindenden E-Mail-Servers.|
|`PTR=<ReverseDNS>`|Der PTR-Eintrag der IP-Adresse des Absenders, auch bekannt als Reverse-DNS-Adresse.|
|

Ein Beispiel **custom_data** wert für eine Nachricht, die nach Spam wie dem folgenden gefiltert wird:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Schadsoftwarefilter-Agent

Ein **custom_data,** der mit `S:AMA` beginnt, ist vom Schadsoftwarefilter-Agent. Die wichtigsten Details werden in der folgenden Tabelle beschrieben:

****

|Wert|Beschreibung|
|---|---|
|`AMA=SUM|v=1|` oder `AMA=EV|v=1`|Die Nachricht enthält Schadsoftware. `SUM` gibt an, dass die Schadsoftware von einer beliebigen Anzahl von Modulen erkannt werden konnte. `EV` gibt an, dass die Schadsoftware von einem bestimmten Modul erkannt wurde. Wenn von einem Modul Schadsoftware erkannt wird, werden dadurch die nachfolgenden Aktionen ausgelöst.|
|`Action=r`|Die Nachricht wurde ersetzt.|
|`Action=p`|Die Nachricht wurde umgangen.|
|`Action=d`|Die Nachricht wurde zurückgestellt.|
|`Action=s`|Die Nachricht wurde gelöscht.|
|`Action=st`|Die Nachricht wurde umgangen.|
|`Action=sy`|Die Nachricht wurde umgangen.|
|`Action=ni`|Die Nachricht wurde abgelehnt.|
|`Action=ne`|Die Nachricht wurde abgelehnt.|
|`Action=b`|Die Nachricht wurde blockiert.|
|`Name=<malware>`|Der Name der Schadsoftware, die gefunden wurde.|
|`File=<filename>`|Der Name der Datei, welche die Schadsoftware enthielt.|
|

Ein Beispiel **custom_data** für eine Nachricht, die Schadsoftware enthält, sieht wie die folgende aus:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Transportregel-Agent

Ein **custom_data,** der mit beginnt, ist vom Transport Rule Agent für `S:TRA` Nachrichtenflussregeln (auch transport rules). Die wichtigsten Details werden in der folgenden Tabelle beschrieben:

****

|Wert|Beschreibung|
|---|---|
|`ETR|ruleId=<guid>`|Die ID der Regel, die abgeglichen wurde.|
|`St=<datetime>`|Datum und Uhrzeit in UTC, wenn die Regel übereinstimmung aufgetreten ist.|
|`Action=<ActionDefinition>`|Die Aktion, die angewendet wurde. Eine Liste der verfügbaren Aktionen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|`Mode=<Mode>`|Der Modus der Regel. Gültige Werte sind:<ul><li>**Enforce**: Alle Aktionen für die Regel werden erzwungen.</li><li>**Test mit Richtlinientipps:**: Alle Richtlinientippaktionen werden gesendet, andere Erzwingungsaktionen werden jedoch nicht durchgeführt.</li><li>**Test ohne Richtlinientipps:** Aktionen werden in einer Protokolldatei aufgeführt, Absender werden jedoch in keinem Fall benachrichtigt, und Erzwingungsaktionen werden nicht durchgeführt.</li></ul>|
|

Ein Beispiel **custom_data** für nachrichten, die den Bedingungen einer Nachrichtenflussregel entspricht, sieht wie die folgende aus:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
