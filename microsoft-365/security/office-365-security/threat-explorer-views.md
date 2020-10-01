---
title: Ansichten im Threat Explorer und Echt Zeit Erkennungen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
description: In diesem Artikel erfahren Sie, wie Sie Threat Explorer und den Bericht über Echt Zeit Erkennungen verwenden, um Bedrohungen im Security Compliance Center zu untersuchen und auf diese zu reagieren &amp; .
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1310baec402d9053e93b7166ca38cfcab11d73b2
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326985"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Ansichten im Threat Explorer und Echt Zeit Erkennungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


![Sicherheitsrisiken-Explorer](../../media/ThreatExplorerFirstOpened.png)

[Threat Explorer](threat-explorer.md) (und der Bericht über Echt Zeit Erkennungen) ist ein leistungsfähiges, near-Echt Zeit Tool, um Sicherheitsteams beim untersuchen und reagieren auf Bedrohungen im Security Compliance Center zu unterstützen &amp; . Explorer (und der Bericht über Echt Zeit Erkennungen) zeigt Informationen zu mutmaßlicher Schadsoftware und Phishing in e-Mails und Dateien in Office 365 sowie andere Sicherheitsrisiken und Risiken für Ihre Organisation an.

- Wenn Sie [Office 365 Advanced Threat Protection](office-365-atp.md) (ATP) Plan 2 haben, haben Sie den Explorer.
- Wenn Sie Office 365 ATP-Plan 1 haben, haben Sie Echt Zeit Erkennungen.

Wenn Sie Explorer zum ersten Mal öffnen (oder den Bericht über Echt Zeit Erkennungen), werden in der Standardansicht e-Mail-Malwareerkennungen für die letzten 7 Tage angezeigt. In diesem Bericht können auch ATP-Erkennungen angezeigt werden, beispielsweise bösartige URLs, die von [sicheren Links](atp-safe-links.md)erkannt wurden, sowie bösartige Dateien, die durch [sichere Anlagen](atp-safe-attachments.md)erkannt wurden. Dieser Bericht kann geändert werden, um Daten für die letzten 30 Tage anzuzeigen (mit einem kostenpflichtigen ATP P2-Abonnement). Testabonnements enthalten nur Daten für die letzten sieben Tage.

****

|Abonnement|Dienstprogramm|Tage mit Daten|
|---|---|---|
|ATP P1-Testversion|Echtzeiterkennungen|7 |
|ATP P1 bezahlt|Echtzeiterkennungen|30|
|ATP P1 Paid testing ATP P2 Testversion|Sicherheitsrisiken-Explorer|7 |
|ATP P2-Testversion|Sicherheitsrisiken-Explorer|7 |
|ATP P2 Paid|Sicherheitsrisiken-Explorer|30|
|

Verwenden Sie das Menü **Ansicht** , um zu ändern, welche Informationen angezeigt werden. Mithilfe von QuickInfos können Sie bestimmen, welche Ansicht verwendet werden soll.

![Ansicht im Menü "Bedrohungs-Explorer"](../../media/ThreatExplorerViewMenu.png)

Nachdem Sie eine Ansicht ausgewählt haben, können Sie Filter anwenden und Abfragen einrichten, um eine weitere Analyse durchzuführen. Die folgenden Abschnitte bieten eine kurze Übersicht über die verschiedenen Ansichten, die in Explorer verfügbar sind (oder Echt Zeit Erkennungen).

## <a name="email--malware"></a>E-Mail-> Schadsoftware

Wenn Sie diesen Bericht anzeigen möchten, wählen Sie im Explorer (oder Echtzeiterkennung) **View**die Option  >  **e-Mail-**  >  **Schadsoftware**anzeigen aus. In dieser Ansicht werden Informationen zu e-Mail-Nachrichten angezeigt, die als mit Schadsoftware gekennzeichnet wurden.

![Anzeigen von Daten zu e-Mails, die als Schadsoftware identifiziert wurden](../../media/ExplorerEmailMalwareMenu.png)

Klicken Sie auf **Absender** , um die Liste der Anzeigeoptionen zu öffnen. Verwenden Sie diese Liste, um Daten nach Absender, Empfänger, Absenderdomäne, Betreff, Erkennungstechnologie, Schutzstatus und vielem mehr anzuzeigen.

Um beispielsweise zu sehen, welche Aktionen bei erkannten e-Mail-Nachrichten durchgeführt wurden, wählen Sie in der Liste **Schutzstatus** aus. Wählen Sie eine Option aus, und klicken Sie dann auf die Schaltfläche Aktualisieren, um diesen Filter auf Ihren Bericht anzuwenden.

![Bedrohungsschutz-Status Optionen für Threat Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

Zeigen Sie unter dem Diagramm weitere Details zu bestimmten Nachrichten an. Wenn Sie ein Element in der Liste auswählen, wird ein Ausklappbereich geöffnet, in dem Sie weitere Informationen zum ausgewählten Element erhalten.

![Threat Explorer mit geöffnetem Flyout](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>E-Mail > Phishing

Wenn Sie diesen Bericht anzeigen möchten, wählen Sie im Explorer (oder Echtzeiterkennung) **View**die Option  >  **e-Mail-**  >  **Phishing**anzeigen aus. Diese Ansicht zeigt e-Mail-Nachrichten, die als Phishing-Versuche identifiziert wurden.

![Anzeigen von Daten zu e-Mails, die als Phishing-Versuche identifiziert wurden](../../media/ThreatExplorerEmailPhish.png)

Klicken Sie auf **Absender** , um die Liste der Anzeigeoptionen zu öffnen. Verwenden Sie diese Liste, um Daten nach Absender, Empfänger, Absenderdomäne, Absender-IP, URL-Domäne, Klick Urteil und vieles mehr anzuzeigen.

Um beispielsweise zu sehen, welche Aktionen durchgeführt wurden, als Personen auf URLs geklickt haben, die als Phishing-Versuche identifiziert wurden, wählen Sie in der Liste **auf Urteil klicken** , wählen Sie eine oder mehrere Optionen aus, und klicken Sie dann auf die Schaltfläche Aktualisieren.

![Klicken Sie auf Urteils Optionen für den Phish-Bericht](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

Zeigen Sie unter dem Diagramm weitere Details zu bestimmten Nachrichten, URL-Klicks, URLs und e-Mail-Ursprung an.

![Als Phishing erkannte URLs in e-Mail-Nachrichten](../../media/ThreatExplorerEmailPhishURLs.png)

Wenn Sie ein Element in der Liste auswählen, beispielsweise eine erkannte URL, wird ein Ausklappbereich geöffnet, in dem Sie weitere Informationen zum ausgewählten Element erhalten.

![Details zu einer erkannten URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a>E-Mail > Übermittlungen

Um diesen Bericht anzuzeigen, wählen Sie im Explorer (oder Echtzeiterkennung) die Option **View**  >  **e-Mail-**  >  **Übermittlungen**anzeigen aus. In dieser Ansicht werden e-Mails angezeigt, die Benutzer als Junk-e-Mail, nicht als Junk oder als Phishing-e-Mails gemeldet haben.

![Von Benutzern gemeldete e-Mail-Nachrichten](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

Klicken Sie auf **Absender** , um die Liste der Anzeigeoptionen zu öffnen. Verwenden Sie diese Liste, um Informationen nach Absender, Empfänger, Berichtstyp anzuzeigen (die Bestimmung des Benutzers, dass es sich bei der e-Mail um Junk-e-Mails handelte, nicht um Junk-oder Phishing-Zwecke) und vieles mehr.

Wenn Sie beispielsweise Informationen zu e-Mail-Nachrichten anzeigen möchten, die als Phishing-Versuche gemeldet wurden, klicken Sie auf **Absender**  >  **Berichtstyp**, wählen Sie **Phishing**aus, und klicken Sie dann auf die Schaltfläche Aktualisieren.

![Für den Berichtstyp Filter ausgewählter Phishing-Typ](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Zeigen Sie unter dem Diagramm weitere Details zu bestimmten e-Mail-Nachrichten an, beispielsweise Betreffzeile, die IP-Adresse des Absenders, den Benutzer, der die Nachricht als Junk-e-Mail, nicht Junk oder Phishing gemeldet hat, und vieles mehr.

![Nachrichten, die als Phishing-Versuche gemeldet wurden](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

Wählen Sie ein Element in der Liste aus, um weitere Details anzuzeigen.

## <a name="email--all-email"></a>E-Mail > alle e-Mails

Um diesen Bericht anzuzeigen, wählen Sie im Explorer **View**die Option  >  **e-Mail**  >  **alle e-Mails**anzeigen aus. Diese Ansichten zeigen eine Gesamtansicht der e-Mail-Aktivität an, einschließlich e-Mails, die aufgrund von Phishing oder Schadsoftware als bösartig eingestuft wurden, sowie alle nicht-böswilligen e-Mails (normale e-Mail, Spam und Massen-e-Mails).

> [!NOTE]
> Wenn Sie eine Fehlermeldung erhalten, die zu **viele anzuzeigende Daten**liest, fügen Sie einen Filter hinzu, und verringern Sie ggf. den von Ihnen angezeigten Datumsbereich.

Wenn Sie einen Filter anwenden möchten, wählen Sie **Absender**aus, wählen Sie ein Element in der Liste aus, und klicken Sie dann auf die Schaltfläche Aktualisieren. In unserem Beispiel haben wir die **Erkennungstechnologie** als Filter verwendet (es stehen verschiedene Optionen zur Verfügung). Anzeigen von Informationen nach Absender, Domäne des Absenders, Empfänger, Betreff, Anlagendateiname, Malwarefamilie, Schutzstatus (Aktionen, die von den Bedrohungen geschützt sind, und Richtlinien in Office 365), Erkennungstechnologie (wie die Schadsoftware erkannt wurde) und vieles mehr.

![Anzeigen von Daten zu erkannten e-Mails anhand von Erkennungstechnologien](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

Zeigen Sie unter dem Diagramm weitere Details zu bestimmten e-Mail-Nachrichten an, beispielsweise Betreff, Empfänger, Absender, Status usw.

## <a name="content--malware"></a>Inhalte > Schadsoftware

Wenn Sie diesen Bericht anzeigen möchten, wählen Sie im Explorer (oder Echtzeiterkennung) **View**die Option  >  **Inhalts**  >  **Malware**anzeigen aus. In dieser Ansicht werden Dateien angezeigt, die von [Office 365 Advanced Threat Protection in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams](atp-for-spo-odb-and-teams.md)als bösartig identifiziert wurden.

Anzeigen von Informationen nach Malwarefamilie, Erkennungstechnologie (wie die Schadsoftware erkannt wurde) und Arbeitsauslastung (OneDrive, SharePoint oder Teams).

![Anzeigen von Daten zu erkannter Schadsoftware](../../media/d11dc568-b091-4159-b261-df13d76b520b.png)

Zeigen Sie unter dem Diagramm weitere Details zu bestimmten Dateien an, beispielsweise Anlagendateiname, Arbeitsauslastung, Dateigröße, wer die Datei zuletzt geändert hat und vieles mehr.

## <a name="click-to-filter-capabilities"></a>Click-to-Filter-Funktionen

Mit Explorer (und Echtzeiterkennung) können Sie einen Filter in einem Klick anwenden. Klicken Sie auf ein Element in der Legende, und dieses Element wird zum Filter für den Bericht. Nehmen wir beispielsweise an, dass wir uns die Malware-Ansicht im Explorer ansehen:

![Wechseln Sie zu Threat Management \> Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Wenn Sie in diesem Diagramm auf **ATP-Detonation** klicken, wird eine Ansicht wie die folgende angezeigt:

![Explorer gefiltert, um nur ATP-detonations Ergebnisse anzuzeigen](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

In dieser Ansicht betrachten wir nun Daten für Dateien, die mit [sicheren Anlagen](atp-safe-attachments.md)gezündet wurden. Unter dem Diagramm können Details zu bestimmten e-Mail-Nachrichten mit Anlagen angezeigt werden, die von sicheren Anlagen erkannt wurden.

![Spezifische Details zu e-Mail-Nachrichten mit erkannten Anlagen](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

Wenn Sie ein oder mehrere Elemente auswählen, wird das Menü **Aktionen** aktiviert, das mehrere Auswahlmöglichkeiten für die ausgewählten Elemente bietet.

![Durch die Auswahl eines Elements wird das Menü Aktionen aktiviert.](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

Die Möglichkeit, mit einem Klick zu filtern und zu bestimmten Details zu navigieren, kann Ihnen viel Zeit bei der Untersuchung von Bedrohungen sparen.

## <a name="queries-and-filters"></a>Abfragen und Filter

Explorer (sowie der Bericht über Echt Zeit Erkennungen) verfügt über mehrere leistungsstarke Filter und Abfragefunktionen, mit denen Sie Details eingehen können, beispielsweise Top-Zielbenutzer, Top-Malware Familien, Erkennungstechnologien und vieles mehr. Jede Art von Bericht bietet eine Vielzahl von Möglichkeiten zum Anzeigen und Durchsuchen von Daten.

> [!IMPORTANT]
> Verwenden Sie in der Abfrage Leiste für Explorer (oder Echtzeiterkennung) keine Platzhalterzeichen, beispielsweise ein Sternchen oder ein Fragezeichen. Wenn Sie im **Feld Betreff** nach e-Mail-Nachrichten suchen, führt der Explorer (oder Echt Zeit Erkennungsvorgang) partielle Übereinstimmungen und Ergebnis Ergebnisse aus, die einer Platzhaltersuche ähneln.
