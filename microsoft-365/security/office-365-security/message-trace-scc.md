---
title: Nachrichtenablaufverfolgung im Security & Compliance Center
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 3e64f99d-ac33-4aba-91c5-9cb4ca476803
description: 'Administratoren können die Nachrichtenablaufverfolgung im Security #a0 Compliance Center verwenden, um herauszufinden, was mit Nachrichten passiert ist.'
ms.openlocfilehash: fa10c4168720565770ec0a3bc4bb06486155c3cc
ms.sourcegitcommit: 5710ce729c55d95b8b452d99ffb7ea92b5cb254a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2019
ms.locfileid: "39970331"
---
# <a name="message-trace-in-the-security--compliance-center"></a>Nachrichtenablaufverfolgung im Security & Compliance Center

## <a name="overview"></a>Übersicht

Die Nachrichtenablaufverfolgung im Security #a0 Compliance Center folgt e-Mail-Nachrichten, wenn Sie über Ihre Exchange Online Organisation Reisen. Sie können ermitteln, ob eine Nachricht empfangen, abgelehnt, zurückgestellt oder vom Dienst gesendet wurde. Außerdem werden die Aktionen der Nachricht gezeigt, bevor diese ihren finalen Status erreicht hat.

> [!NOTE]
> Um die Nachrichtenablaufverfolgung durchführen zu können, muss der Administrator Mitglied der Rollengruppen "Organisationsverwaltung", "Compliance Management" oder "Helpdesk" sein.

Die Nachrichtenablaufverfolgung im Security #a0 Compliance Center verbessert die Nachrichtenablaufverfolgung, die im Exchange Admin Center (EAC) zur Verfügung stand. Sie können die Informationen aus der Nachrichtenablaufverfolgung verwenden, um Benutzer Fragen über das geschehen mit ihren Nachrichten effizient zu beantworten, Probleme mit dem Nachrichtenfluss zu beheben und Richtlinienänderungen zu überprüfen.

> [!NOTE]
> Nur die ersten 50000-Nachrichten werden in den Ergebnissen angezeigt. Das Cmdlet [Get-HistoricalSearch](https://docs.microsoft.com/powershell/module/exchange/reporting/get-historicalsearch) in Exchange Online PowerShell oder Exchange Online Protection PowerShell gibt alle Nachrichten in den Ergebnissen zurück.

## <a name="open-message-trace"></a>Nachrichtenablaufverfolgung öffnen

1. [Melden Sie sich bei Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4) mit Ihrem Geschäfts-, Schul- oder Unikonto an.

2. Wählen Sie das Symbol für das App-Startfeld ![Symbol für Office 365-App-Startfeld](../media/0aaa6945-f9a4-4b13-bf5f-d5c5dbe978fb.png) in der oberen linken Ecke und dann **Administrator** aus.

3. Erweitern Sie in der linken oberen Navigationsleiste **Admin Center** , und wählen Sie **Sicherheits #a0 Kompatibilität**aus.

4. Erweitern Sie auf der Seite **Sicherheit #a0 Kompatibilität** , die geöffnet wird, den Eintrag Nachrichten **Fluss**, und wählen Sie **Nachrichtenablaufverfolgung**aus.

## <a name="message-trace-page"></a>Seite "Nachrichtenablaufverfolgung"

Von hier aus können Sie eine neue Standardablaufverfolgung starten, indem Sie auf die Schaltfläche **Trace starten** klicken. Dadurch werden alle Nachrichten für alle Absender und Empfänger der letzten zwei Tage gesucht. Sie können auch eine der gespeicherten Abfragen aus den verfügbaren Abfrage Kategorien verwenden und diese wie folgt ausführen oder als Ausgangspunkt für Ihre eigenen Abfragen verwenden:

- **Standardabfragen**: integrierte Abfragen, die von Office 365 bereitgestellt werden.

- **Benutzerdefinierte Abfragen**: Abfragen, die von Administratoren in Ihrer Organisation für die zukünftige Verwendung gespeichert wurden.

- Selbst **gespeicherte Abfragen**: die letzten zehn zuletzt ausgeführten Abfragen. Mit dieser Liste können Sie ganz einfach abholen, wo Sie aufgehört haben.

Auf dieser Seite finden Sie auch einen Abschnitt zu **herunterladbaren Berichten** für die von Ihnen übermittelten Anforderungen sowie die Berichte selbst, wenn Sie zum Download zur Verfügung stehen.

## <a name="options-for-a-new-message-trace"></a>Optionen für eine neue Nachrichtenablaufverfolgung

### <a name="filter-by-senders-and-recipients"></a>Filtern nach Absendern und Empfängern

Die Standardwerte sind **alle Absender** und **alle Empfänger**, aber Sie können die folgenden Felder verwenden, um die Ergebnisse zu filtern:

- **Von diesen Personen**: Klicken Sie in dieses Feld, um einen oder mehrere Absender aus Ihrer Organisation auszuwählen. Sie können auch mit dem Eingeben eines Namens beginnen, und die Elemente in der Liste werden nach Ihren Eingaben gefiltert, ähnlich wie die Suchseiten.

- **Für diese Personen**: Klicken Sie in dieses Feld, um einen oder mehrere Empfänger in Ihrer Organisation auszuwählen.

> [!NOTE]
> Sie können auch die e-Mail-Adressen externer Absender und Empfänger eingeben. Platzhalter werden unterstützt (beispielsweise `*@contoso.com`), aber Sie können nicht gleichzeitig mehrere Platzhaltereinträge im gleichen Feld verwenden.<br/>Sie können mehrere Absender oder Empfängerlisten durch Semikolons getrennt einfügen (`;`). Leerzeichen`\s`(), Carriage Returns (`\r`) oder Next Lines`\n`().

### <a name="time-range"></a>Zeitbereich

Der Standardwert ist **2 Tage**, aber Sie können Datum/Uhrzeit Bereiche von bis zu 90 Tagen angeben. Berücksichtigen Sie beim Verwenden von Datums-und Zeitbereichen folgende Probleme:

- Standardmäßig wählen Sie den Zeitbereich in der **Slider** -Ansicht mithilfe eines Zeitlineals aus. Sie können nur die angezeigten Tages-oder Zeiteinstellungen auswählen. Wenn Sie versuchen, einen dazwischen liegenden Wert auszuwählen, wird die Start-und endblase an die nächstgelegene angezeigte Einstellung andocken.

   ![Einen Slider-Zeitbereich in einer neuen Nachrichtenablaufverfolgung im Security #a0 Compliance Center](../media/55a9e9c1-f7d5-4047-b217-824e8b976bcb.png)

   Sie können aber auch zur **benutzerdefinierten** Ansicht wechseln, in der Sie die Werte **Start Datum** und **Enddatum** (einschließlich Uhrzeiten) angeben können, und Sie können auch die **Zeitzone für den** Bereich Datum/Uhrzeit auswählen. Beachten Sie, dass die **Zeit Zonen** Einstellung sowohl für Ihre Abfrage Eingaben als auch für Ihre Abfrageergebnisse gilt.

   ![Ein benutzerdefinierter Zeitbereich in einer neuen Nachrichtenablaufverfolgung im Security #a0 Compliance Center](../media/ed4c8d50-9ea5-4694-93f9-ee3ab6660b4f.png)

   Für mindestens 10 Tage sind die Ergebnisse sofort als **Zusammenfassungs** Bericht verfügbar. Wenn Sie einen Zeitbereich angeben, der sogar etwas größer als 10 Tage ist, werden die Ergebnisse verzögert, da Sie nur als herunterladbare CSV-Datei ( **Erweiterte Zusammenfassung** oder **Erweiterte** Berichte) verfügbar sind.

   Weitere Informationen zu den verschiedenen Berichtstypen finden Sie im Abschnitt [auswählen des Berichtstyps](#choose-report-type) in diesem Thema.

   **Hinweis**: verbesserte Zusammenfassung und erweiterte Berichte werden mithilfe von archivierten Nachrichtenablauf Verfolgungsdaten vorbereitet, und es kann bis zu mehreren Stunden dauern, bis Ihr Bericht zum Download verfügbar ist. Je nachdem, wie viele andere Administratoren auch Berichtsanforderungen zur gleichen Zeit übermittelt haben, wird möglicherweise auch eine Verzögerung festgestellt, bevor die Verarbeitung für Ihre in die Warteschlange stehende Anforderung beginnt.

- Beim Speichern einer Abfrage in der **Slider** -Ansicht wird der relative Zeitbereich gespeichert (beispielsweise 3 Tage ab heute). Beim Speichern einer Abfrage in der **benutzerdefinierten** Ansicht wird der absolute Datum/Zeitbereich gespeichert (beispielsweise 2018-05-06 13:00 bis 2018-05-08 18:00).

### <a name="more-search-options"></a>Weitere Suchoptionen

#### <a name="delivery-status"></a>Zustellungsstatus

Sie können den Standardwert **alle** ausgewählt lassen, oder Sie können einen der folgenden Werte auswählen, um die Ergebnisse zu filtern:

- **Zugestellt**: die Nachricht wurde erfolgreich an das vorgesehene Ziel übermittelt.

- **Pending**: die Zustellung der Nachricht wird versucht oder erneut versucht.

- **Expanded**: ein Verteilergruppenempfänger wurde vor der Zustellung an die einzelnen Mitglieder der Gruppe erweitert.

- **Fehler**: die Nachricht wurde nicht zugestellt.

- **Quarantäne**: die Nachricht wurde in Quarantäne verschoben (als Spam, Massen-e-Mail oder Phishing). Weitere Informationen finden Sie unter [Quarantäne für e-Mail-Nachrichten in Office 365](quarantine-email-messages.md).

- **Gefiltert als Spam**: die Nachricht wurde als Spam identifiziert und wurde abgelehnt oder blockiert (nicht in Quarantäne).

- **Status wird abgerufen:** Die Nachricht wurde kürzlich von Office 365 empfangen, es sind jedoch noch keine weiteren Statusdaten verfügbar. Schauen Sie in ein paar Minuten zurück.

**Hinweis**: die Werte **Ausstehend,** **isoliert**und **Filter als Spam** sind nur für Suchvorgänge in weniger als 10 Tagen verfügbar. Außerdem kann es eine Verzögerung von 5 bis 10 Minuten zwischen dem aktuellen und dem gemeldeten Zustellungsstatus geben.

#### <a name="message-id"></a>Nachrichten-ID

Dies ist die Internet Nachrichten-ID (auch als Client-ID bezeichnet), die im Kopfzeilenfeld nach **richten-ID:** im Nachrichtenkopf gefunden wird. Benutzer können Ihnen diesen Wert geben, um bestimmte Nachrichten zu untersuchen.

Dieser Wert ist für die Lebensdauer der Nachricht konstant. Bei Nachrichten, die in Office 365 oder Exchange erstellt wurden, liegt der `<GUID@ServerFQDN>`Wert im Format vor, einschließlich\< \>der spitzen Klammern (). Beispiel: `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`. Andere Messagingsysteme verwenden möglicherweise unterschiedliche Syntax oder Werte. Dieser Wert sollte eindeutig sein, aber nicht alle e-Mail-Systeme folgen strikt dieser Anforderung. Wenn das Kopfzeilenfeld **Message-ID:** für eingehende Nachrichten von externen Quellen nicht vorhanden oder leer ist, wird ein beliebiger Wert zugewiesen.

Wenn Sie die nach **richten-ID** verwenden, um die Ergebnisse zu filtern, müssen Sie unbedingt die vollständige Zeichenfolge einschließlich aller spitzen Klammern einschließen.

#### <a name="direction"></a>Direction

Sie können den Standardwert " **alle** ausgewählt **" oder "** **eingehend** " auswählen (Nachrichten, die an Empfänger in Ihrer Organisation gesendet werden) oder ausgehend (von Benutzern in Ihrer Organisation gesendete Nachrichten), um die Ergebnisse zu filtern.

#### <a name="original-client-ip-address"></a>Ursprüngliche Client-IP-Adresse

Sie können die Ergebnisse nach Client-IP-Adresse einfeilen, um Hacker Computer zu untersuchen, die große Mengen an Spam oder Schadsoftware senden. Obwohl die Nachrichten möglicherweise von mehreren Absendern stammen, ist es wahrscheinlich, dass der gleiche Computer alle Nachrichten generiert.

**Hinweis**: die Client-IP-Adressinformationen sind nur für 10 Tage verfügbar und stehen nur in den **erweiterten Zusammenfassungen** oder **erweiterten** Berichten (herunterladbare CSV-Dateien) zur Verfügung.

### <a name="choose-report-type"></a>Auswählen des Berichtstyps

Die verfügbaren Berichtstypen sind:

- **Zusammenfassung**: verfügbar, wenn der Zeitbereich weniger als 10 Tage beträgt und keine zusätzlichen Filteroptionen erforderlich sind. Die Ergebnisse stehen fast unmittelbar nach dem Klicken auf **Suchen**zur Verfügung.

- **Erweiterte Zusammenfassung** oder **Erweiterung**: Diese Berichte sind nur als herunterladbare CSV-Dateien verfügbar und erfordern eine oder mehrere der folgenden Filteroptionen unabhängig vom Zeitbereich: **durch diese Personen**, **für diese Personen**oder nach **richten-ID**. Sie können Platzhalter für die Absender oder die Empfänger verwenden (beispielsweise \*@contoso. com).

**Hinweise**:

- Erweiterte Zusammenfassung und erweiterte Berichte werden mithilfe von archivierten Nachrichtenablauf Verfolgungsdaten vorbereitet, und es kann bis zu mehreren Stunden dauern, bis Ihr Bericht zum Download verfügbar ist. Je nachdem, wie viele andere Administratoren gleichzeitig Berichtsanforderungen übermittelt haben, wird möglicherweise auch eine Verzögerung festgestellt, bevor die Verarbeitung der Warteschlangen Anforderung beginnt.

- Sie können zwar eine erweiterte Zusammenfassung oder einen erweiterten Bericht für einen beliebigen Datums-und Zeitbereich auswählen, die letzten vier Stunden archivierter Daten sind jedoch für diese beiden Berichtstypen noch nicht verfügbar.

Wenn Sie auf **weiter**klicken, wird eine Zusammenfassungsseite mit den ausgewählten Filteroptionen, einem eindeutigen (bearbeitbaren) Titel für den Bericht und der e-Mail-Adresse angezeigt, die die Benachrichtigung erhält, wenn die Nachrichtenablaufverfolgung abgeschlossen wird (auch bearbeitbar und muss sich in einer der akzeptierten Domänen der Organisation befinden). Klicken Sie auf **Bericht vorbereiten** , um die Nachrichtenablaufverfolgung zu senden. Auf der Hauptseite der **Nachrichtenablaufverfolgung** können Sie den Status des Berichts im Abschnitt **Berichte zum Herunterladen** anzeigen.

Weitere Informationen zu den Informationen, die in den verschiedenen Berichtstypen zurückgegeben werden, finden Sie im nächsten Abschnitt.

## <a name="message-trace-results"></a>Ergebnisse der Nachrichtenablaufverfolgung

Die verschiedenen Berichtstypen geben unterschiedliche Informationsebenen zurück. Die Informationen, die in den verschiedenen Berichten zur Verfügung stehen, werden in den folgenden Abschnitten beschrieben.

### <a name="summary-report-output"></a>Ausgabe des Zusammenfassungsberichts

Nach dem Ausführen der Nachrichtenablaufverfolgung werden die Ergebnisse aufgelistet, sortiert nach absteigender Datums-und Zeitangabe (zuletzt zuerst).

![Ergebnisse des Zusammenfassungsberichts für Nachrichtenablaufverfolgung im Security #a0 Compliance Center](../media/0664bafe-0b03-477b-b571-0b046ac8c977.png)

Der Zusammenfassungsbericht enthält die folgenden Informationen:

- **Date**: das Datum und die Uhrzeit, zu der die Nachricht vom Dienst empfangen wurde, unter Verwendung der konfigurierten UTC-Zeitzone.

- **Absender**: die e-Mail-Adresse des Absenders (*Alias*@*Domäne*).

- **Empfänger**: die e-Mail-Adresse des Empfängers oder Empfängers. Für eine Nachricht, die an mehrere Empfänger gesendet wird, gibt es eine pro Empfänger. Wenn es sich bei dem Empfänger um eine Verteilergruppe, eine dynamische Verteilergruppe oder eine e-Mail-aktivierte Sicherheitsgruppe handelt, ist die Gruppe der erste Empfänger, und dann befindet sich jedes Mitglied der Gruppe in einer separaten Leitung.

- **Betreff**: die ersten 256 Zeichen des **betreffs** der Nachricht: Field.

- **Status**: diese Werte werden im Abschnitt [Zustellungsstatus](#delivery-status) beschrieben.

Standardmäßig werden die ersten 250-Ergebnisse geladen und leicht verfügbar. Wenn Sie nach unten scrollen, gibt es eine kleine Pause, wenn der nächste Batch mit Ergebnissen geladen wird. Anstatt einen Bildlauf durchzuführen, können Sie auf **alle laden** klicken, um alle Ergebnisse auf maximal 10.000 zu laden.

Sie können auf die Spaltenüberschriften klicken, um die Ergebnisse nach den Werten in dieser Spalte in aufsteigender oder absteigender Reihenfolge zu sortieren.

Sie können auf **Filterergebnisse** klicken, um die Ergebnisse nach einer oder mehreren Spalten zu filtern.

Sie können die Ergebnisse exportieren, nachdem Sie eine oder mehrere Zeilen ausgewählt haben, indem Sie auf **Ergebnisse exportieren** und dann auf **alle Ergebnisse exportieren**, **geladene Ergebnisse exportieren**oder **ausgewählt**exportieren klicken.

#### <a name="find-related-records-for-this-message"></a>Suchen nach verwandten Datensätzen für diese Nachricht

Zugehörige Nachrichtendatensätze sind Datensätze, die dieselbe Nachrichten-ID gemeinsam verwendet haben. Denken Sie daran, dass auch eine einzelne Nachricht, die zwischen zwei Personen gesendet wird, mehrere Datensätze generieren kann. Die Anzahl der Datensätze steigt, wenn die Nachricht von Verteilergruppenerweiterung, Weiterleitung, Nachrichtenfluss Regeln (auch bekannt als Transportregeln) usw. betroffen ist.

Nachdem Sie das Kontrollkästchen einer Zeile markiert haben, können Sie nach verwandten Datensätzen für die Nachricht suchen, indem Sie auf die Schaltfläche **Verwandte Suchen** klicken, oder indem Sie **Weitere Optionen** ![weitere](../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Verwandte Einträge für diese Nachricht suchen**auswählen.

Weitere Informationen zur Nachrichten-ID finden Sie weiter oben in diesem Thema im Abschnitt Nachrichten-ID.

#### <a name="message-trace-details"></a>Details zur Nachrichtenablaufverfolgung

In der Ausgabe des Zusammenfassungsberichts können Sie mit einer der folgenden Methodendetails zu einer Nachricht anzeigen:

- Wählen Sie die Zeile aus (Klicken Sie auf eine beliebige Stelle in der Zeile außer dem Kontrollkästchen).

- Aktivieren Sie das Kontrollkästchen Zeile, und klicken Sie auf **Weitere Optionen** ![mehr](../media/1ea52bbf-9d00-48ce-9362-307f7f6fb7fe.png) \> **Details zur Nachrichtenanzeige anzeigen**.

   ![Details nach dem Doppelklicken auf eine Zeile in der Zusammenfassungsbericht-Nachrichtenablauf Verfolgungsergebnisse im Security #a0 Compliance Center](../media/e50ee7cd-810a-4c06-8b58-e56ffd7028d1.png)

Die Nachrichtenablauf Verfolgungs Details enthalten die folgenden zusätzlichen Informationen, die im Zusammenfassungsbericht nicht vorhanden sind:

- **Nachrichten Ereignisse**: Dieser Abschnitt enthält Klassifikationen, mit denen die Aktionen kategorisiert werden, die der Dienst für Nachrichten ausführt. **Einige der interessantesten Ereignisse** , die auftreten können, sind:

  - **Receive**: die Nachricht wurde vom Dienst empfangen.

  - **Send**: die Nachricht wurde vom Dienst gesendet.

  - **Fehler**: die Nachricht konnte nicht zugestellt werden.

  - **Deliver**: die Nachricht wurde an ein Postfach übermittelt.

  - **Expand**: die Nachricht wurde an eine Verteilergruppe gesendet, die erweitert wurde.

  - **Übertragung**: Empfänger wurden aufgrund von Inhaltskonvertierung, Nachrichtenempfänger Grenzwerten oder Agents zu einer gegabelten Nachricht verschoben.

  - **Aufschieben**: die Nachrichtenzustellung wurde verschoben und kann später erneut versucht werden.

  - **Behoben**: die Nachricht wurde an eine neue Empfängeradresse basierend auf einem Active Directory Nachschlagen umgeleitet. Wenn dies geschieht, wird die ursprüngliche Empfängeradresse zusammen mit dem abschließenden Zustellungsstatus in der Nachrichtenablaufverfolgung einer separaten Zeile aufgeführt.

  Hinweise:

  - Bei einer ereignisreichen Nachricht, die erfolgreich zugestellt wurde, werden mehrere **Ereignis** Einträge in der Nachrichtenablaufverfolgung generiert.

  - Diese Liste ist nicht als erschöpfend zu verstehen. Beschreibungen von weiteren Ereignissen finden Sie unter [Ereignistypen im Nachrichtenverfolgungsprotokoll](https://docs.microsoft.com/Exchange/mail-flow/transport-logs/message-tracking#event-types-in-the-message-tracking-log). Beachten Sie, dass es sich bei diesem Link um ein Exchange Server (Lokales Exchange)-Thema handelt.

- **Weitere Informationen**: Dieser Abschnitt enthält die folgenden Details:

  - Nach **richten-ID**: dieser Wert wird im Abschnitt nach [richten-ID](#message-id) weiter oben in diesem Thema beschrieben. Beispiel: `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

  - **Nachrichtengröße**

  - **Von IP**: die IP-Adresse des Computers, von dem die Nachricht gesendet wurde. Für ausgehende Nachrichten, die von Exchange Online gesendet wurden, wird kein Wert angegeben.

  - **In IP**: die IP-Adresse oder Adressen, bei denen der Dienst versucht hat, die Nachricht zuzustellen. Wenn die Nachricht mehrere Empfänger aufweist, werden diese angezeigt. Für eingehende Nachrichten, die an Exchange Online gesendet wurden, wird kein Wert angegeben.

### <a name="enhanced-summary-reports"></a>Erweiterte Zusammenfassungsberichte

Verfügbare (abgeschlossene) erweiterte Zusammenfassungsberichte stehen im Abschnitt **Berichte zum Herunterladen** an der Start Nachrichtenablaufverfolgung zur Verfügung. Die folgenden Informationen sind im Bericht verfügbar:

- **origin_timestamp**<sup>*</sup>: das Datum und die Uhrzeit, zu der die Nachricht anfänglich vom Dienst empfangen wurde, unter Verwendung der konfigurierten UTC-Zeitzone.

- **sender_address**: die e-Mail-Adresse des Absenders (*Alias*@*Domäne*).

- **Recipient_status**: der Status der Zustellung der Nachricht an den Empfänger. Wenn die Nachricht an mehrere Empfänger gesendet wurde, werden alle Empfänger und der entsprechende Status für jeden im Format: \< *e-Mail-Adress*\>##\<*Status*\>angezeigt. Beispiel:

  - **# #Receive, Send bedeutet,** dass die Nachricht vom Dienst empfangen und an das vorgesehene Ziel gesendet wurde.

  - **# #Receive, Fail bedeutet,** dass die Nachricht vom Dienst empfangen wurde, die Zustellung an das vorgesehene Ziel jedoch fehlgeschlagen ist.

  - **# #Receive, Deliver bedeutet,** dass die Nachricht vom Dienst empfangen und an das Postfach des Empfängers übermittelt wurde.

- **message_subject**: die ersten 256 Zeichen des **Betreff** -Felds der Nachricht.

- **total_bytes**: die Größe der Nachricht in Bytes, einschließlich Anlagen.

- **message_id**: dieser Wert wird im Abschnitt nach [richten-ID](#message-id) weiter oben in diesem Thema beschrieben. Beispiel: `<d9683b4c-127b-413a-ae2e-fa7dfb32c69d@DM3NAM06BG401.Eop-nam06.prod.protection.outlook.com>`.

- **network_message_id**: ein eindeutiger Nachrichten-ID-Wert, der über alle Kopien der Nachricht, die aufgrund von Verzweigung oder Verteilergruppenerweiterung erstellt werden können, gespeichert wird. Ein Beispielwert ist `1341ac7b13fb42ab4d4408cf7f55890f`.

- **original_client_ip**: die IP-Adresse des Clients des Absenders.

- **Directional**: gibt an, ob die Nachricht eingehend (1) an Ihre Organisation gesendet wurde oder ob Sie ausgehende (2) von Ihrer Organisation gesendet wurde.

- **connector_id**: der Name des Quell-oder Ziel-Konnektors. Weitere Informationen zu Connectors in Exchange Online finden Sie unter [Configure Mail Flow using Connectors in Office 365](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow).

- **delivery_priority**<sup>*</sup>: gibt an, ob die Nachricht mit **hoher**, **niedriger**oder **normaler** Priorität gesendet wurde.

<sup>*</sup>Diese Eigenschaften sind nur in erweiterten Zusammenfassungsberichten verfügbar.

### <a name="extended-reports"></a>Erweiterte Berichte

Verfügbare (abgeschlossene) Erweiterte Berichte stehen im Abschnitt zum **Herunterladen von Berichten** am Anfang der Nachrichtenablaufverfolgung zur Verfügung. In einem erweiterten Bericht stehen praktisch alle Informationen aus einem erweiterten Zusammenfassungsbericht zur Verfügung (mit Ausnahme von **origin_timestamp** und **delivery_priority**). Die folgenden zusätzlichen Informationen sind nur in einem erweiterten Bericht verfügbar:

- **client_ip**: die IP-Adresse des e-Mail-Servers oder Messagingclients, der die Nachricht übermittelt hat.

- **client_hostname**: der Hostname oder der vollqualifizierte Domänenname des e-Mail-Servers oder Messagingclients, der die Nachricht übermittelt hat.

- **server_ip**: die IP-Adresse des Quell-oder Zielservers.

- **server_hostname**: der Hostname oder der vollqualifizierte Domänenname des Zielservers.

- **source_context**: zusätzliche Informationen, die dem Feld **Quelle** zugeordnet sind. Beispiel:

  - `Protocol Filter Agent`

  - `3489061114359050000`

- **Quelle**: die Exchange Online Komponente, die für das Ereignis verantwortlich ist. Beispiel:

  - `AGENT`

  - `MAILBOXRULE`

  - `SMTP`

- **event_id**: Diese entsprechen den **Nachrichtenereignis** Werten, die im Abschnitt [verwandte Datensätze für diese Nachricht suchen](#find-related-records-for-this-message) erläutert werden.

- **internal_message_id**: eine Nachrichten-ID, die vom Exchange Online Server zugewiesen wird, der die Nachricht derzeit verarbeitet.

- **recipient_address**: die e-Mail-Adressen der Empfänger der Nachricht. Mehrere E-Mail-Adressen sind durch ein Semikolon (;) getrennt.

- **recipient_count**: die Gesamtzahl der Empfänger in der Nachricht.

- **related_recipient_address**: wird mit `EXPAND` `REDIRECT`-,- `RESOLVE` und-Ereignissen verwendet, um andere Empfänger-e-Mail-Adressen anzuzeigen, die der Nachricht zugeordnet sind.

- **Referenz**: Dieses Feld enthält zusätzliche Informationen für bestimmte Ereignistypen. Beispiel:

  - **DSN**: enthält den Berichtslink, bei dem es sich um den **message_id** Wert der zugehörigen Benachrichtigung über den Zustellungsstatus (auch als DSN, Unzustellbarkeitsbericht, NDR oder Bounce-Nachricht bezeichnet) handelt, wenn nach diesem Ereignis ein DSN generiert wird. Wenn es sich um eine DSN-Nachricht handelt, enthält dieses Feld den **message_id** Wert der ursprünglichen Nachricht, für die der DSN generiert wurde.

  - **Expand**: enthält den **related_recipient_address** Wert der zugehörigen Nachrichten.

  - **Receive**: enthält möglicherweise den **message_id** Wert der zugehörigen Nachricht, wenn die Nachricht von anderen Prozessen generiert wurde (beispielsweise Posteingangsregeln).

  - **Send**: enthält den **internal_message_id** Wert aller DSN-Nachrichten.

  - **Übertragung**: enthält den **internal_message_id** Wert der Nachricht, die verzweigt wird (beispielsweisedurch Inhaltskonvertierung, Empfänger Grenzwerte für Nachrichten oder Agents).

  - **MAILBOXRULE**: enthält den **internal_message_id** Wert der eingehenden Nachricht, die bewirkt hat, dass die Posteingangsregel die ausgehende Nachricht generiert hat.

    Für andere Ereignistypen ist dieses Feld zumeist leer.

- **return_path**: die Absender-e-Mail-Adresse, die durch den Befehl **Mail from** angegeben wurde, der die Nachricht gesendet hat. Obwohl dieses Feld nie leer ist, kann es den Wert der NULL-Absenderadresse darstellen `<>`, dargestellt als.

- **message_info**: zusätzliche Informationen zur Nachricht. Beispiel:

  - Der Nachrichtenursprung Datum-Uhrzeit in UTC für `DELIVER` und `SEND` Ereignisse. Das Datum-Uhrzeit der Erstellung ist die Uhrzeit, zu der die Nachricht zuerst in die Exchange Online Organisation eingegeben wurde. Die UTC-Datum-Uhrzeit wird im ISO 8601-Datum-Uhrzeit-Format `yyyy-mm-ddThh:mm:ss.fffZ`dargestellt: `yyyy` , wobei = `mm` Year, = `dd` month, = `T` Day, den Anfang der Zeitkomponente angibt `hh` , = Hour `mm` , = Minute `ss` , = Second `fff` , = Brüche einer Sekunde, und `Z` `Zulu`eine andere Möglichkeit zum bezeichnen von UTC darstellt.

  - Authentifizierungsfehler. Beispielsweise können Sie den Wert `11a` und den Typ der Authentifizierung sehen, der beim Auftreten des Authentifizierungsfehlers verwendet wurde.

- **tenant_id**: ein GUID-Wert, der die Exchange Online Organisation darstellt (Beispiels `39238e87-b5ab-4ef6-a559-af54c6b07b42`Weise).

- **original_server_ip**: die IP-Adresse des ursprünglichen Servers.

- **custom_data**: enthält Daten im Zusammenhang mit bestimmten Ereignistypen. Weitere Informationen finden Sie in den folgenden Abschnitten.

#### <a name="custom_data-values"></a>custom_data Werte

Das **custom_data** Feld für ein `AGENTINFO` Ereignis wird von einer Vielzahl von Exchange Online-Agents verwendet, um Details zur Nachrichtenverarbeitung zu protokollieren. Einige der interessantesten Agents werden in den folgenden Abschnitten beschrieben.

#### <a name="spam-filter-agent"></a>Spam Filter-Agent

Ein **custom_data** Wert, der mit `S:SFA` beginnt, ist vom Spamfilter-Agent. Die wichtigsten Details werden in der folgenden Tabelle beschrieben:

|**Wert**|**Beschreibung**|
|:-----|:-----|
|`SFV=NSPM`|Die Nachricht wurde als "Nicht-Spam" markiert und an die vorgesehenen Empfänger gesendet.|
|`SFV=SPM`|Die Nachricht wurde vom Inhaltsfilter als Spam markiert.|
|`SFV=BLK`|Die Filterung wurde übergangen, und die Nachricht wurde gesperrt, da sie von einem gesperrten Absender stammt.|
|`SFV=SKS`|Die Nachricht wurde bereits als Spam markiert, noch bevor sie vom Inhaltsfilter verarbeitet wurde Dies beinhaltet Nachrichten, bei denen die Nachricht einer Transportregel entsprach, die diese automatisch als Spam markiert und alle zusätzlichen Filterungen umgeht.|
|`SCL=<number>`|Weitere Informationen zu den verschiedenen SCL-Werten und deren Bedeutung finden Sie unter [SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md).|
|`PCL=<number>`|Der PCL-Wert (Phishing Confidence Level) der Nachricht. Diese Werte können auf die gleiche Weise interpretiert werden wie die in [SCL-Bewertungen (Spam Confidence Level)](spam-confidence-levels.md) dokumentierten SCL-Werte.  |
|`DI=SB`|Der Absender der Nachricht wurde blockiert.|
|`DI=SQ`|Die Nachricht wurde unter Quarantäne gestellt.|
|`DI=SD`|Die Nachricht wurde gelöscht.|
|`DI=SJ`|Die Nachricht wurde an den Ordner "Junk-E-Mail" des Empfängers gesendet.|
|`DI=SN`|Die Nachricht wurde durch den Pool für besonders riskante Zustellungen geleitet. Weitere Informationen finden Sie unter [hochriskanter Zustellungs Pool für ausgehende Nachrichten](high-risk-delivery-pool-for-outbound-messages.md).|
|`DI=SO`|Die Nachricht wurde durch den normalen Pool für ausgehende Zustellungen geleitet.|
|`SFS=[a]|SFS=[b]`|Dies bedeutet, dass Übereinstimmungen mit den Spam-Regeln gefunden wurden.|
|`IPV=CAL`|Die Nachricht wurde durch die Spam-Filter gelassen, weil die IP-Adrese in einer IP-Zulassungsliste im Verbindungsfilter angegeben wurde.|
|`H=<EHLOstring>`|Die HELO-oder EHLO-Zeichenfolge des Verbindungs-e-Mail-Servers.|
|`PTR=<ReverseDNS>`|Der PTR-Eintrag der IP-Adresse des Absenders, auch bekannt als Reverse-DNS-Adresse.|

Ein Beispiel **custom_data** Wert für eine Nachricht, die nach Spam wie folgt gefiltert wird:

`S:SFA=SUM|SFV=SPM|IPV=CAL|SRV=BULK|SFS=470454002|SFS=349001|SCL=9|SCORE=-1|LIST=0|DI=SN|RD=ftmail.inc.com|H=ftmail.inc.com|CIP=98.129.140.74|SFP=1501|ASF=1|CTRY=US|CLTCTRY=|LANG=en|LAT=287|LAT=260|LAT=18;`

#### <a name="malware-filter-agent"></a>Filter-Agent für Schadsoftware

Ein **custom_data** Wert, der mit `S:AMA` beginnt, ist vom Filter-Agent für Schadsoftware. Die wichtigsten Details werden in der folgenden Tabelle beschrieben:

|**Wert**|**Beschreibung**|
|:-----|:-----|
|`AMA=SUM|v=1|` oder `AMA=EV|v=1`|Die Nachricht enthält Schadsoftware. `SUM`Gibt an, dass die Schadsoftware von einer beliebigen Anzahl von Modulen erkannt wurde. `EV`Gibt an, dass die Schadsoftware von einem bestimmten Modul erkannt wurde. Wenn von einem Modul Schadsoftware erkannt wird, werden dadurch die nachfolgenden Aktionen ausgelöst.|
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

Ein Beispiel **custom_data** Wert für eine Nachricht, die Malware enthält, sieht wie folgt aus:

`S:AMA=SUM|v=1|action=b|error=|atch=1;S:AMA=EV|engine=M|v=1|sig=1.155.974.0|name=DOS/Test_File|file=filename;S:AMA=EV|engine=A|v=1|sig=201707282038|name=Test_File|file=filename`

#### <a name="transport-rule-agent"></a>Transport Regel-Agent

Ein **custom_data** Wert, der mit`S:TRA` beginnt, ist vom Transportregel-Agent für Nachrichtenfluss Regeln (auch bekannt als Transportregeln). Die wichtigsten Details werden in der folgenden Tabelle beschrieben:

|**Wert**|**Beschreibung**|
|:-----|:-----|
|`ETR|ruleId=<guid>`|Die ID der Regel, die abgeglichen wurde.|
|`St=<datetime>`|Das Datum und die Uhrzeit in UTC, als die Regelübereinstimmung aufgetreten ist.|
|`Action=<ActionDefinition>`|Die Aktion, die angewendet wurde. Eine Liste der verfügbaren Aktionen finden Sie unter [Aktionen für Nachrichtenfluss Regeln in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).|
|`Mode=<Mode>`|Der Modus der Regel. Gültige Werte sind: <br/>• **Erzwingen**: alle Aktionen für die Regel werden erzwungen. <br/>• **Test mit Richtlinien Tipps:**: alle richtlinientipp Aktionen werden gesendet, aber andere Durchsetzungs Aktionen werden nicht ausgeführt. <br/>• **Test ohne Richtlinien Tipps**: Aktionen werden in einer Protokolldatei aufgeführt, aber die Absender werden nicht benachrichtigt, und es werden keine Durchsetzungs Aktionen ausgeführt.|

Ein Beispiel **custom_data** Wert für eine Nachricht, die mit den Bedingungen einer e-Mail-Fluss Regel übereinstimmt, sieht wie folgt aus:

`S:TRA=ETR|ruleId=19a25eb2-3e43-4896-ad9e-47b6c359779d|st=7/17/2017 12:31:25 AM|action=ApplyHtmlDisclaimer|sev=1|mode=Enforce`
