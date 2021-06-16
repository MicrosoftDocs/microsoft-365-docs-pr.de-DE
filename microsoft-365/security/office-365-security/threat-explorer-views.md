---
title: Ansichten im Bedrohungs-Explorer und Echtzeiterkennungen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 05/15/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid: ''
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Erfahren Sie, wie Sie den Bedrohungs-Explorer und den Bericht über Echtzeiterkennungen verwenden, um Bedrohungen im Microsoft 365 Defender-Portal zu untersuchen und darauf zu reagieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1c79cc717a2dbe345627f99830590c674fa02f09
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52929635"
---
# <a name="views-in-threat-explorer-and-real-time-detections"></a>Ansichten im Bedrohungs-Explorer und Echtzeiterkennungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


![Sicherheitsrisiken-Explorer](../../media/explorer.png)

[Der Bedrohungs-Explorer](threat-explorer.md) (und der Bericht über Echtzeiterkennungen) ist ein leistungsstarkes, nahezu in Echtzeit verfügbares Tool, mit dem Sicherheitsteams Bedrohungen im Microsoft 365 Defender-Portal untersuchen und darauf reagieren können. Explorer (und der Bericht über Echtzeiterkennungen) zeigt Informationen zu verdächtiger Schadsoftware und Phishing in E-Mails und Dateien in Office 365 sowie andere Sicherheitsbedrohungen und Risiken für Ihre Organisation an.

- Wenn Sie [über Microsoft Defender für Office 365](defender-for-office-365.md) Plan 2 verfügen, verfügen Sie über Explorer.
- Wenn Sie Über Microsoft Defender für Office 365 Plan 1 verfügen, haben Sie Echtzeiterkennungen.

Wenn Sie den Explorer (oder den Bericht über Echtzeiterkennungen) zum ersten Mal öffnen, zeigt die Standardansicht E-Mail-Schadsoftwareerkennungen für die letzten 7 Tage an. Dieser Bericht kann auch Microsoft Defender für Office 365 Erkennungen anzeigen, z. B. bösartige URLs, die von [sicheren Links](safe-links.md)erkannt werden, und schädliche Dateien, die von [sicheren Anlagen](safe-attachments.md)erkannt werden. Dieser Bericht kann so geändert werden, dass Daten für die letzten 30 Tage angezeigt werden (mit einem kostenpflichtigen Microsoft Defender für Office 365 P2-Abonnement). Testabonnements enthalten nur Daten für die letzten sieben Tage.

****

|Abonnement|Dienstprogramm|Datentage|
|---|---|---|
|Testversion von Microsoft Defender für Office 365 P1|Echtzeiterkennungen|7 |
|Microsoft Defender für Office 365 P1 bezahlt|Echtzeiterkennungen|30|
|Microsoft Defender for Office 365 P1 paid testing Defender for Office 365 P2 trial|Sicherheitsrisiken-Explorer|7 |
|Testversion von Microsoft Defender für Office 365 P2|Sicherheitsrisiken-Explorer|7 |
|Microsoft Defender für Office 365 P2, bezahlt|Sicherheitsrisiken-Explorer|30|
|

> [!NOTE]
> Wir werden in Kürze die Datenaufbewahrungs- und Suchgrenze von Explorer (und Echtzeiterkennungen) für Testmandanten von 7 auf 30 Tage erweitern. Diese Änderung wird als Teil des Roadmap-Elements Nr. 70544 nachverfolgt und befindet sich derzeit in einer Rolloutphase.

Verwenden Sie das Menü **"Ansicht",** um zu ändern, welche Informationen angezeigt werden. Mithilfe von QuickInfos können Sie bestimmen, welche Ansicht verwendet werden soll.

![Menü "Ansicht des Bedrohungs-Explorers"](../../media/all-email.png)

Nachdem Sie eine Ansicht ausgewählt haben, können Sie Filter anwenden und Abfragen einrichten, um weitere Analysen durchzuführen. Die folgenden Abschnitte bieten eine kurze Übersicht über die verschiedenen Ansichten, die im Explorer verfügbar sind (oder Echtzeiterkennungen).

## <a name="email--malware"></a>E-Mail-> Schadsoftware

Um diesen Bericht anzuzeigen, wählen Sie im Explorer  (oder Echtzeiterkennungen) die Option \> **"E-Mail-Schadsoftware** \> anzeigen" aus. In dieser Ansicht werden Informationen zu E-Mail-Nachrichten angezeigt, die als schadsoftware enthalten identifiziert wurden.

![Anzeigen von Daten zu E-Mails, die als Schadsoftware identifiziert wurden](../../media/detection-technology.png)

Klicken Sie auf **"Absender",** um die Liste der Anzeigeoptionen zu öffnen. Verwenden Sie diese Liste, um Daten nach Absender, Empfänger, Absenderdomäne, Betreff, Erkennungstechnologie, Schutzstatus und mehr anzuzeigen.

Wenn Sie beispielsweise sehen möchten, welche Aktionen für erkannte E-Mail-Nachrichten ausgeführt wurden, wählen Sie den **Schutzstatus** in der Liste aus. Wählen Sie eine Option aus, und klicken Sie dann auf die Schaltfläche "Aktualisieren", um diesen Filter auf Ihren Bericht anzuwenden.

![Optionen für den Bedrohungsschutzstatus für den Bedrohungs-Explorer](../../media/ThreatExplorerProtectionStatusOptions.png)

Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten Nachrichten an. Wenn Sie ein Element in der Liste auswählen, wird ein Flyoutbereich geöffnet, in dem Sie mehr über das ausgewählte Element erfahren können.

![Bedrohungs-Explorer mit geöffneter Flyout](../../media/ThreatExplorerMalwareItemSelectedFlyout.png)

## <a name="email--phish"></a>E-Mail-> Phishing

Um diesen Bericht anzuzeigen, wählen Sie im Explorer  (oder Echtzeiterkennungen) \> **E-Mail-Phishing** anzeigen \> aus. In dieser Ansicht werden E-Mail-Nachrichten angezeigt, die als Phishingversuche identifiziert wurden.

![Anzeigen von Daten zu E-Mails, die als Phishingversuche identifiziert wurden](../../media/phish.png)

Klicken Sie auf **"Absender",** um die Liste der Anzeigeoptionen zu öffnen. Verwenden Sie diese Liste, um Daten nach Absender, Empfänger, Absenderdomäne, Absender-IP, URL-Domäne, Klickbewertung und mehr anzuzeigen.

Um beispielsweise zu sehen, welche Aktionen ausgeführt wurden, wenn Benutzer auf URLs geklickt haben, die als Phishingversuche identifiziert wurden, wählen Sie in der Liste **auf "Bewertung klicken",** wählen Sie eine oder mehrere Optionen aus, und klicken Sie dann auf die Schaltfläche "Aktualisieren".

![Klicken Sie auf die Bewertungsoptionen für den Phishingbericht.](../../media/click-verdict.png)

Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten Nachrichten, URL-Klicks, URLs und E-Mail-Ursprung an.

![URLs, die in E-Mail-Nachrichten als Phishing erkannt wurden](../../media/ThreatExplorerEmailPhishURLs.png)

Wenn Sie ein Element in der Liste auswählen, z. B. eine url, die erkannt wurde, wird ein Flyoutbereich geöffnet, in dem Sie mehr über das ausgewählte Element erfahren können.

![Details zu einer erkannten URL](../../media/ThreatExplorerEmailPhishURLDetails.png)

## <a name="email--submissions"></a>E-Mail->-Übermittlungen

Um diesen Bericht anzuzeigen, wählen Sie im Explorer  (oder Echtzeiterkennungen) die Option \> **"E-Mail-Übermittlungen** \> anzeigen" **aus.** Diese Ansicht zeigt E-Mails, die Benutzer als Junk-, nicht Junk- oder Phishing-E-Mails gemeldet haben.

![Von Benutzern gemeldete E-Mail-Nachrichten](../../media/ThreatExplorerEmailUserReportedViewOptions.png)

Klicken Sie auf **"Absender",** um die Liste der Anzeigeoptionen zu öffnen. Verwenden Sie diese Liste, um Informationen nach Absender, Empfängern, Berichtstyp (die Entscheidung des Benutzers, dass die E-Mail Junk war, nicht Junk oder Phishing) und mehr anzuzeigen.

Wenn Sie z. B. Informationen zu E-Mail-Nachrichten anzeigen möchten, die als Phishingversuche gemeldet wurden, klicken Sie auf  \> **"Absenderbericht",** wählen Sie **"Phishing"** aus, und klicken Sie dann auf die Schaltfläche "Aktualisieren".

![Für den Berichtstypfilter ausgewählter Phishing-Wert](../../media/ThreatExplorerEmailUserReportedPhishSelected.png)

Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten E-Mail-Nachrichten an, z. B. Betreffzeile, DIE IP-Adresse des Absenders, der Benutzer, der die Nachricht als Junk, nicht Junk oder Phishing gemeldet hat, und vieles mehr.

![Nachrichten, die als Phishingversuche gemeldet wurden](../../media/ThreatExplorerEmailPhishUserReportedPhishDetails.png)

Wählen Sie ein Element in der Liste aus, um weitere Details anzuzeigen.

## <a name="email--all-email"></a>E-Mail > Alle E-Mails

Um diesen Bericht anzuzeigen,  wählen Sie im Explorer \> **"Alle E-Mail anzeigen"** \> aus. Diese Ansichten zeigen eine Gesamtansicht der E-Mail-Aktivitäten, einschließlich E-Mails, die aufgrund von Phishing oder Schadsoftware als bösartig erkannt wurden, sowie alle nicht schädlichen E-Mails (normale E-Mails, Spam und Massen-E-Mails).

> [!NOTE]
> Wenn ein Fehler angezeigt wird, der **zu viele Daten anzeigt,** fügen Sie einen Filter hinzu, und schränken Sie ggf. den angezeigten Datumsbereich ein.

Um einen Filter anzuwenden, wählen Sie **"Absender"** aus, wählen Sie ein Element in der Liste aus, und klicken Sie dann auf die Schaltfläche "Aktualisieren". In unserem Beispiel haben wir **die Erkennungstechnologie** als Filter verwendet (es stehen mehrere Optionen zur Verfügung). Anzeigen von Informationen nach Absender, Domäne des Absenders, Empfänger, Betreff, Dateiname der Anlage, Schadsoftwarefamilie, Schutzstatus (Aktionen, die von Ihren Bedrohungsschutzfeatures und -richtlinien in Office 365 ausgeführt werden), Erkennungstechnologie (wie die Schadsoftware erkannt wurde) und vieles mehr.

![Anzeigen von Daten zu erkannten E-Mails durch Erkennungstechnologie](../../media/0c032eb3-6021-4174-9f06-ff8f30c245ca.png)

Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten E-Mail-Nachrichten an, z. B. Betreffzeile, Empfänger, Absender, Status usw.

## <a name="content--malware"></a>Inhalt > Schadsoftware

Um diesen Bericht anzuzeigen, wählen Sie im Explorer  (oder Echtzeiterkennungen) \> **inhaltsbezogene** \> **Schadsoftware** anzeigen aus. In dieser Ansicht werden Dateien angezeigt, die von [Microsoft Defender für Office 365 in SharePoint Online, OneDrive for Business und Microsoft Teams](mdo-for-spo-odb-and-teams.md)als bösartig erkannt wurden.

Anzeigen von Informationen nach Schadsoftwarefamilie, Erkennungstechnologie (wie die Schadsoftware erkannt wurde) und Workload (OneDrive, SharePoint oder Teams).

![Anzeigen von Daten zu erkannter Schadsoftware](../../media/malware-family.png)

Zeigen Sie unterhalb des Diagramms weitere Details zu bestimmten Dateien an, z. B. Anlagendateiname, Arbeitsauslastung, Dateigröße, wer die Datei zuletzt geändert hat und vieles mehr.

## <a name="click-to-filter-capabilities"></a>Klick-und-Filter-Funktionen

Mit Explorer (und Echtzeiterkennungen) können Sie einen Filter in einem Klick anwenden. Klicken Sie in der Legende auf ein Element, und dieses Element wird zu einem Filter für den Bericht. Nehmen wir beispielsweise an, dass wir die Schadsoftwareansicht im Explorer betrachten:

![Wechseln sie zum Explorer für die \> Bedrohungsverwaltung](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Durch Klicken auf **die ATP-Detonation** in diesem Diagramm wird eine Ansicht wie die folgende angezeigt:

![Explorer gefiltert, um nur Defender für Office 365 Detonation-Ergebnisse anzuzeigen](../../media/7241d7dd-27bc-467d-9db8-6e806c49df14.png)

In dieser Ansicht betrachten wir jetzt Daten für Dateien, die durch [sichere Anlagen](safe-attachments.md)detoniert wurden. Unterhalb des Diagramms sehen wir Details zu bestimmten E-Mail-Nachrichten mit Anlagen, die von sicheren Anlagen erkannt wurden.

![Spezifische Details zu E-Mail-Nachrichten mit erkannten Anlagen](../../media/c91fb05c-d1d4-4085-acc6-f7008a415c2a.png)

Wenn Sie ein oder mehrere Elemente auswählen, wird das Menü **"Aktionen"** aktiviert, das mehrere Auswahlmöglichkeiten für die ausgewählten Elemente bietet.

![Wenn Sie ein Element auswählen, wird das Menü "Aktionen" aktiviert.](../../media/95f127a4-1b2a-4a76-88b9-096e3ba27d1b.png)

Die Möglichkeit, in einem Klick zu filtern und zu bestimmten Details zu navigieren, kann Ihnen viel Zeit bei der Untersuchung von Bedrohungen sparen.

## <a name="queries-and-filters"></a>Abfragen und Filter

Der Explorer (sowie der Bericht über Echtzeiterkennungen) verfügt über mehrere leistungsstarke Filter und Abfragefunktionen, mit denen Sie details anzeigen können, z. B. benutzerorientierte Top-Benutzer, top Schadsoftwarefamilien, Erkennungstechnologie und vieles mehr. Jede Art von Bericht bietet eine Vielzahl von Möglichkeiten zum Anzeigen und Erkunden von Daten.

> [!IMPORTANT]
> Verwenden Sie keine Platzhalterzeichen, z. B. ein Sternchen oder ein Fragezeichen, in der Abfrageleiste für Explorer (oder Echtzeiterkennungen). Wenn Sie im **Feld Betreff** nach E-Mail-Nachrichten suchen, führt Explorer (oder Echtzeiterkennungen) einen teilweisen Abgleich durch und liefert Ergebnisse, die einer Platzhaltersuche ähneln.
