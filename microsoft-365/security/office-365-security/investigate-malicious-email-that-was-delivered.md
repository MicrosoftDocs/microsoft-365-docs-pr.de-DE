---
title: Untersuchen schädlicher e-Mails, die in Office 365 bereitgestellt wurden, suchen und untersuchen schädlicher e-Mails
keywords: TIMailData-Inline, Sicherheitsvorfall, Vorfall, ATP PowerShell, e-Mail-Schadsoftware, kompromittierte Benutzer, e-Mail-Phishing, e-Mail-Schadsoftware, e-Mail-Header lesen, Kopfzeilen lesen, offene e-Mail-Header
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 07/09/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie mithilfe von Bedrohungs Ermittlungs-und-Antwortfunktionen böswillige e-Mails suchen und untersuchen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7677c1741a173c0528504f0fad67439608845f64
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48842940"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a>Untersuchen schädlicher e-Mails, die in Office 365 bereitgestellt wurden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


[Microsoft Defender für Office 365](office-365-atp.md) ermöglicht es Ihnen, Aktivitäten zu untersuchen, mit denen Personen in Ihrer Organisation gefährdet werden, und Maßnahmen zum Schutz Ihrer Organisation zu ergreifen. Wenn Sie beispielsweise Teil des Sicherheitsteams Ihrer Organisation sind, können Sie nach verdächtigen e-Mail-Nachrichten suchen und diese untersuchen, die übermittelt wurden. Sie können dies mithilfe von [Threat Explorer (oder Echtzeiterkennung)](threat-explorer.md)durchführen.

> [!NOTE]
> Wechseln Sie [hier](remediate-malicious-email-delivered-office-365.md)zum Korrektur Artikel.

## <a name="before-you-begin"></a>Vorbereitung

Stellen Sie sicher, dass folgende Anforderungen erfüllt sind:

- Ihre Organisation verfügt über [Microsoft Defender für Office 365](office-365-atp.md) und [Lizenzen werden Benutzern zugewiesen](../../admin/manage/assign-licenses-to-users.md).

- die [Überwachungsprotokollierung](../../compliance/turn-audit-log-search-on-or-off.md) ist für Ihre Organisation aktiviert.

- Ihre Organisation verfügt über Richtlinien, die für Antispam-, Antischadsoftware-und Anti-Phishing-Maßnahmen und so weiter definiert sind. Weitere Informationen finden Sie unter [Protect Against Threats in Office 365](protect-against-threats.md).

- Sie sind globaler Administrator oder haben im Security Compliance Center entweder den Sicherheitsadministrator oder die Such-und Säuberungs Rolle zugewiesen &amp; . Weitere Informationen finden Sie unter [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md). Für einige Aktionen muss auch eine neue Vorschau Rolle zugewiesen sein.

### <a name="preview-role-permissions"></a>Vorschau der Rollen Berechtigungen

Um bestimmte Aktionen auszuführen, beispielsweise das Anzeigen von Nachrichtenkopfzeilen oder das Herunterladen von e-Mail-Nachrichteninhalten, müssen Sie eine neue Rolle namens " *Preview* " zu einer anderen entsprechenden Rollengruppe hinzufügen. In der folgenden Tabelle werden die erforderlichen Rollen und Berechtigungen erläutert.

****

|Aktivität|Rollengruppe|Vorschau-Rolle erforderlich?|
|---|---|---|
|Verwenden von Threat Explorer (und Echtzeiterkennung) zum Analysieren von Bedrohungen |Globaler Administrator <br> Sicherheitsadministrator <br> Sicherheitsleseberechtigter|Nein|
|Verwenden Sie Threat Explorer (und Echtzeiterkennung), um Kopfzeilen für e-Mail-Nachrichten anzuzeigen sowie e-Mail-Nachrichten, die in Quarantäne verschoben wurden, anzuzeigen und herunterzuladen.|Globaler Administrator <br> Sicherheitsadministrator <br>Sicherheitsleseberechtigter|Nein|
|Verwenden von Threat Explorer zum Anzeigen von Kopfzeilen und Herunterladen von an Postfächern zugestellten e-Mails|Globaler Administrator <br>Sicherheitsadministrator <br> Sicherheitsleseberechtigter <br> Vorschau|Ja|
|

> [!NOTE]
> *Vorschau* ist eine Rolle und keine Rollengruppe; die Vorschau Rolle muss einer vorhandenen Rollengruppe für Office 365 hinzugefügt werden. Der globalen Administrator Rolle wird das Microsoft 365 Admin Center ( [https://admin.microsoft.com](https://admin.microsoft.com) ) zugewiesen, und die Rollen Sicherheitsadministrator und Sicherheits Leser werden im Security & Compliance Center zugewiesen ( [https://protection.office.com](https://protection.office.com) ). Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Permissions in the Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="find-suspicious-email-that-was-delivered"></a>Verdächtige e-Mails finden, die zugestellt wurden

Threat Explorer ist ein leistungsfähiger Bericht, der mehrere Zwecke wie das Suchen und Löschen von Nachrichten, das Identifizieren der IP-Adresse eines böswilligen e-Mail-Absenders oder das Starten eines Vorfalls zur weiteren Untersuchung dienen kann. Das folgende Verfahren konzentriert sich auf die Verwendung von Explorer zum Suchen und Löschen von böswilligen e-Mails aus Postfächern des Empfängers.

> [!NOTE]
> Standardsuch Vorgänge im Explorer enthalten derzeit keine gezappten Elemente.  Dies gilt für alle Ansichten, beispielsweise Schadsoftware oder Phishing-Ansichten. Um gezappte Elemente einzuschließen, müssen Sie eine "Zustellungs Aktion" hinzufügen, die "removed by Zap" enthalten soll. Wenn Sie alle Optionen einschließen, werden alle Ergebnisse der Übermittlungsaktion angezeigt, einschließlich zapped-Elementen.

1. **Navigieren Sie zu Threat Explorer** : Wechseln Sie zu, [https://protection.office.com](https://protection.office.com) und melden Sie sich mit Ihrem Arbeits-oder Schulkonto für Office 365 an. Dadurch gelangen Sie zum Security &amp; Compliance Center.

2. Klicken Sie in der linken Navigations Schnellstartleiste auf **Threat Management** \> **Explorer**.

    ![Explorer mit Felder Zustellungs Aktion und Zustellungs Speicherort.](../../media/ThreatExFields.PNG)

    Möglicherweise wird die Spalte neue **spezielle Aktionen** feststellen. Dieses Feature zielt darauf ab, den Administratoren das Ergebnis der Verarbeitung einer e-Mail mitzuteilen. Auf die Spalte **spezielle Aktionen** kann an derselben Stelle wie **Zustellungs Aktion** und **Zustellungs Speicherort** zugegriffen werden. Spezielle Aktionen können am Ende der e-Mail-Zeitachse von Threat Explorer aktualisiert werden, ein neues Feature, mit dem die Jagd Erfahrung für Administratoren besser gemacht werden soll.

3. **Ansichten im Bedrohungs-Explorer** : Wählen Sie im Menü **Ansicht** die Option **alle e-Mails** aus.

    ![Threat Explorer-Menü "Ansicht" und e-Mail-Schadsoftware, Phishing, Übermittlungen und alle e-Mail-Optionen, auch Inhalts-Schadsoftware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    Die *Malware* -Ansicht ist derzeit die Standardeinstellung und erfasst e-Mails, bei denen eine Malwarebedrohung erkannt wird. Die *Phishing* -Ansicht funktioniert auf die gleiche Weise, für Phishing.

    In der *e-Mail-* Ansicht werden allerdings alle von der Organisation empfangenen e-Mails aufgelistet, unabhängig davon, ob Bedrohungen erkannt wurden oder nicht. Wie Sie sich vorstellen können, handelt es sich dabei um viele Daten, weshalb in dieser Ansicht ein Platzhalter angezeigt wird, der die Anwendung eines Filters anfordert. (Diese Ansicht ist nur für Defender für Office 365 P2-Kunden verfügbar.)

    Ansicht " *Einsendungen* " zeigt alle e-Mails an, die von Administrator oder Benutzer übermittelt wurden, die an Microsoft gemeldet wurden.

4. **Suchen und Filtern in Threat Explorer** : Filter werden oben auf der Seite in der Suchleiste angezeigt, um Administratoren bei ihren Untersuchungen zu unterstützen. Beachten Sie, dass mehrere Filter gleichzeitig angewendet werden können, und mehrere durch trennzeichengetrennte Werte zu einem Filter hinzugefügt werden, um die Suche einzuschränken. Denken Sie daran:

    - Filter führen bei den meisten Filterbedingungen eine exakte Übereinstimmung aus.
    - Der Antragsteller Filter verwendet eine Contains-Abfrage.
    - URL-Filter funktionieren mit oder ohne Protokolle (z. b. HTTPS).
    - Für URL-Domäne, URL-Pfad und URL-Domänen-und Pfadfilter ist kein Protokoll zum Filtern erforderlich.
    - Sie müssen jedes Mal, wenn Sie die Filterwerte ändern, auf das Symbol Aktualisieren klicken, um relevante Ergebnisse zu erhalten.

5. **Erweiterte Filter** : mit diesen Filtern können Sie komplexe Abfragen erstellen und das Dataset filtern. Durch Klicken auf *Erweiterte Filter* wird ein Flyout mit Optionen geöffnet.

   Die erweiterte Filterung ist eine hervorragende Ergänzung der Suchfunktionen. Ein boolescher **Not** -Filter wurde für die *Empfänger* -, *Absender* -und *Absenderdomäne* eingeführt, um Administratoren die Untersuchung durch Ausschließen von Werten zu ermöglichen. Diese Option wird unter Selection Parameter *Contains None of* angezeigt. **Not** lässt zu, dass Administratoren Warnungs Postfächer, standardmäßige Antwort Postfächer aus ihren Untersuchungen ausschließen, und ist nützlich für Fälle, in denen Administratoren nach einem bestimmten Betreff suchen (Subject = "ATTENTION"), wobei der Empfänger auf *keines von defaultMail \@ contoso.com* festgelegt werden kann. Dies ist eine exakte Wert Suche.

   ![Die Empfänger-"enthält keinen der erweiterten Filter".](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   Das *Filtern nach Stunden* hilft dem Sicherheitsteam Ihres Unternehmens schnell. Die kürzeste zulässige Dauer beträgt 30 Minuten. Wenn Sie die verdächtige Aktion mit einem Zeitrahmen eingrenzen können (beispielsweise vor 3 Std.), wird dadurch der Kontext eingeschränkt und das Problem gezielt identifiziert.

   ![Die Option nach Stunden filtern, um die Anzahl der zu verarbeitenden Daten Sicherheitsteams einzuschränken und deren kürzeste Dauer 30 Minuten beträgt.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Fields in Threat Explorer** : Threat Explorer macht viel mehr sicherheitsbezogene e-Mail-Informationen wie *Zustellungs Aktionen* , *Zustellungsorte* , *spezielle Aktionen* , *Richtungs* -, *Außerkraftsetzungen* und *URL-Bedrohungen* verfügbar. Außerdem kann das Sicherheitsteam Ihrer Organisation mit höherer Sicherheit untersucht werden.

    *Zustellungs Aktion* ist die Aktion, die aufgrund vorhandener Richtlinien oder Erkennungen auf eine e-Mail angewendet wird. Hier sind die möglichen Aktionen, die eine e-Mail ausführen kann:

    - **Zugestellt** – e-Mails wurden im Posteingang oder Ordner eines Benutzers zugestellt, und der Benutzer kann direkt darauf zugreifen.
    - **Junked** (zugestellt an Junk) – e-Mails wurden entweder an den Junk-Ordner des Benutzers oder den Ordner "gelöscht" gesendet, und der Benutzer hat Zugriff auf e-Mail-Nachrichten in seinem Junk-oder Deleted-Ordner.
    - **Blockiert** – alle e-Mail-Nachrichten, die unter Quarantäne gestellt, fehlerhaft oder gelöscht wurden. (Für den Benutzer ist vollständig kein Zugriff möglich.)
    - **Ersetzt** – jede e-Mail-Nachricht, bei der böswillige Anlagen durch txt-Dateien ersetzt werden, die den Status der Anlage böswillig aufweisen

    **Zustellungsort** : der Filter "Übermittlungsort" steht zur Verfügung, damit Administratoren verstehen, wo verdächtige böswillige e-Mails beendet wurden und welche Aktionen dazu unternommen wurden. Die daraus resultierenden Daten können in das Arbeitsblatt exportiert werden. Mögliche Zustellungsorte sind:

    - **Posteingang oder Ordner** – die e-Mail befindet sich im Posteingang oder in einem bestimmten Ordner, entsprechend Ihren e-Mail-Regeln.
    - **On-Prem oder External** – das Postfach ist nicht in der Cloud vorhanden, sondern lokal.
    - **Junk-Ordner** – die e-Mail befindet sich im Junk-e-Mail-Ordner eines Benutzers.
    - **Ordner "Gelöschte Elemente"** – die e-Mail befindet sich im Ordner "Gelöschte Elemente" eines Benutzers.
    - **Quarantine** – die e-Mail-Nachricht in Quarantäne und nicht im Postfach eines Benutzers.
    - **Fehler** – die e-Mail konnte das Postfach nicht erreichen.
    - **Fallen gelassen** – die e-Mail ging an einer beliebigen Stelle im Nachrichtenfluss verloren.

    **Directional** : mit dieser Option können Ihre Sicherheits Betriebsteams nach der "Richtung" filtern, aus der eine e-Mail stammt, oder Sie wird ausgeführt. Die Richtwerte sind *eingehend* , ausgehend und *Intra-org* (entsprechend zu e-Mails, die von außerhalb an Ihre Organisation gesendet *werden, die* aus Ihrer Organisation gesendet werden oder intern an Ihre org gesendet werden). Diese Informationen können Sicherheitsteams beim spotten von Spoofing und Identitätswechsel helfen, da ein Missverhältnis zwischen dem Richtungswert (ex. *Eingehend* ) und die Domäne des Absenders (die *scheinbar* eine interne Domäne ist) ist offensichtlich! Der Richtungswert ist getrennt und kann von der Nachrichtenablaufverfolgung abweichen. Ergebnisse können in das Arbeitsblatt exportiert werden.

    **Außerkraftsetzungen** : dieser Filter enthält Informationen, die auf der Registerkarte Details der e-Mail angezeigt werden, und verwendet diese, um anzuzeigen, wo Organisations-oder Benutzerrichtlinien zum zulassen und Blockieren von e-Mails *außer Kraft gesetzt* wurden. Das wichtigste an diesem Filter ist, dass es dem Sicherheitsteam Ihres Unternehmens hilft zu sehen, wie viele verdächtige e-Mails aufgrund der Konfiguration übermittelt wurden. Dadurch erhalten Sie die Möglichkeit, nach Bedarf die zulässigen und blockierten zu ändern. Dieses Resultset dieses Filters kann in das Arbeitsblatt exportiert werden.

    ****

    |Überschreibungen von Threat Explorer|Bedeutung|
    |---|---|
    |Zulässig durch org-Richtlinie|E-Mail-Nachrichten wurden im Postfach gemäß der Organisationsrichtlinie zugelassen.|
    |Durch org-Richtlinie blockiert|E-Mail-Nachrichten wurden gemäß der Organisationsrichtlinie von der Zustellung an das Postfach blockiert.|
    |Durch die org-Richtlinie blockierte Dateierweiterung|Die Datei wurde gemäß der Organisationsrichtlinie von der Zustellung an das Postfach blockiert.|
    |Nach Benutzerrichtlinie zulässig|E-Mail-Nachrichten wurden gemäß der Benutzerrichtlinie in das Postfach zugelassen.|
    |Durch Benutzerrichtlinie blockiert|E-Mail-Nachrichten wurden gemäß der Benutzerrichtlinie von der Zustellung an das Postfach blockiert.|
    |

    **URL Threat** : das Feld URL-Bedrohung wurde auf der Registerkarte *Details* einer e-Mail angezeigt, um die von einer URL dargestellte Bedrohung anzugeben. Bedrohungen, die von einer URL dargestellt werden, können *Schadsoftware* , *Phishing* oder *Spam* sein, und eine URL *ohne Bedrohung* wird im Abschnitt "Bedrohungen" *keine Aussage geben* .

7. **E-Mail-Zeitachsenansicht** : Ihr Sicherheits Betriebsteam muss möglicherweise tief in die e-Mail-Details eintauchen, um weiter zu untersuchen. Die e-Mail-Zeitachse ermöglicht Administratoren das Anzeigen von Aktionen, die in einer e-Mail von der Zustellung bis zur nach Zustellung vorgenommen wurden. Klicken Sie zum Anzeigen einer e-Mail-Zeitachse auf den Betreff einer e-Mail-Nachricht, und klicken Sie dann auf e-Mail-Zeitplan. (Es wird unter anderen Überschriften wie Zusammenfassung oder Details auf dem Panel angezeigt.) Diese Ergebnisse können in das Arbeitsblatt exportiert werden.

    Die e-Mail-Zeitachse wird in einer Tabelle geöffnet, in der alle Zustellungs-und Post Zustell Ereignisse für die e-Mail angezeigt werden. Wenn die e-Mail keine weiteren Aktionen enthält, sollten Sie ein einzelnes Ereignis für die ursprüngliche Zustellung sehen, das ein Ergebnis wie " *blockiert* " mit einem Urteil wie " *Phishing* " angibt. Administratoren können die gesamte e-Mail-Zeitachse exportieren, einschließlich aller Details auf der Registerkarte und der e-Mail-Adresse (wie Betreff, Absender, Empfänger, Netzwerk und Nachrichten-ID). Die e-Mail-Zeitachse schneidet nach dem Zufallsprinzip ab, da es bei der Überprüfung verschiedener Standorte kürzer ist, um zu versuchen, Ereignisse zu verstehen, die seit dem Eintreffen der e-Mail geschehen sind. Wenn mehrere Ereignisse bei oder nahe gleichzeitig in einer e-Mail auftreten, werden diese Ereignisse in einer Zeitachsenansicht angezeigt.

8. **Vorschau/Download** : Threat Explorer gibt Ihrem Security Operations-Team die Details, die Sie benötigen, um verdächtige e-Mails zu untersuchen. Ihr Sicherheits Betriebsteam kann entweder:

    - [Überprüfen Sie die Zustellungs Aktion und den Speicherort](#check-the-delivery-action-and-location).

    - [Zeigen Sie die Zeitachse Ihrer e-Mail an](#view-the-timeline-of-your-email).

### <a name="check-the-delivery-action-and-location"></a>Überprüfen der Übermittlungsaktion und des Speicherorts

In [Threat Explorer (und Echtzeiterkennung)](threat-explorer.md)haben Sie nun die Spalten **Zustellungs Aktion** und **Zustellungs Speicherort** anstelle der früheren Spalte **Zustellungs Status** . Dadurch wird ein vollständigeres Bild davon erzielt, wo Ihre e-Mail-Nachrichten landen. Ein Teil des Ziels dieser Änderung besteht darin, Untersuchungen für Sicherheits Betriebsteams zu vereinfachen, aber das Ergebnis ist, dass der Speicherort der Problem-e-Mail-Nachrichten auf einen Blick zu erkennen ist.

Der Zustellungs Status wird nun in zwei Spalten aufgeteilt:

- **Zustellungs Aktion** – wie lautet der Status dieser e-Mail?

- **Zustellungs Speicherort** – wohin wurde diese e-Mail weitergeleitet?

Zustellungs Aktion ist die Aktion, die aufgrund vorhandener Richtlinien oder Erkennungen auf eine e-Mail angewendet wird. Hier sind die möglichen Aktionen, die eine e-Mail ausführen kann:

- **Zugestellt** – e-Mails wurden im Posteingang oder Ordner eines Benutzers zugestellt, und der Benutzer kann direkt darauf zugreifen.

- **Junked** – e-Mails wurden entweder an den Junk-Ordner des Benutzers oder den Ordner "gelöscht" gesendet, und der Benutzer hat Zugriff auf e-Mail-Nachrichten in seinem Junk-oder Deleted-Ordner.

- **Blockiert** – alle e-Mail-Nachrichten, die unter Quarantäne gestellt, fehlerhaft oder gelöscht wurden. (Für den Benutzer ist vollständig kein Zugriff möglich.)

- **Ersetzt** – jede e-Mail-Nachricht, bei der böswillige Anlagen durch txt-Dateien ersetzt werden, in denen der Anhang als böswillig bezeichnet wird.

Der Übermittlungsort zeigt die Ergebnisse von Richtlinien und Erkennungen an, die nach der Zustellung ausgeführt werden. Sie ist mit einer Zustellungs Aktion verknüpft. Dieses Feld wurde hinzugefügt, um Einblicke in die Aktion zu geben, die ausgeführt wird, wenn ein Problem mit e-Mails gefunden wird. Im folgenden sind die möglichen Werte für den Zustellungs Speicherort zu finden:

- **Posteingang oder Ordner** – die e-Mail befindet sich im Posteingang oder in einem Ordner (entsprechend Ihren e-Mail-Regeln).

- **On-Prem oder External** – das Postfach ist nicht in der Cloud vorhanden, sondern lokal.

- **Junk-Ordner** – die e-Mail befindet sich im Junk-Ordner eines Benutzers.

- **Ordner "Gelöschte Elemente"** – die e-Mail befindet sich im Ordner "Gelöschte Elemente" eines Benutzers.

- **Quarantine** – die e-Mail-Nachricht in Quarantäne und nicht im Postfach eines Benutzers.

- **Fehler** – die e-Mail konnte das Postfach nicht erreichen.

- **Fallen gelassen** – die e-Mail wird irgendwo im Nachrichtenfluss verloren.

### <a name="view-the-timeline-of-your-email"></a>Anzeigen der Zeitachse Ihrer e-Mail

**E-Mail-Zeitachse** ist ein Feld in Threat Explorer, das die Suche für Ihr Sicherheitsteam erleichtert. Wenn mehrere Ereignisse bei oder nahe gleichzeitig in einer e-Mail auftreten, werden diese Ereignisse in einer Zeitachsenansicht angezeigt. Einige Ereignisse, die nach der Zustellung an e-Mails geschehen, werden in der Spalte **spezielle Aktionen** erfasst. Durch das Kombinieren von Informationen aus der Zeitachse einer e-Mail-Nachricht mit speziellen Aktionen, die nach der Zustellung vorgenommen wurden, erhalten Administratoren Einblicke in Richtlinien und die Bedrohungsbehandlung (beispielsweise, wohin die e-Mail weitergeleitet wurde, und in einigen Fällen was die abschließende Bewertung war).

> [!IMPORTANT]
> Wechseln Sie [hier](remediate-malicious-email-delivered-office-365.md)zu einem Korrektur Thema.

## <a name="related-topics"></a>Verwandte Themen

[Beheben von in Office 365 zugestellten böswilligen e-Mails](remediate-malicious-email-delivered-office-365.md)

[Microsoft Defender für Office 365](office-365-ti.md)

[Schutz vor Bedrohungen in Office 365](protect-against-threats.md)

[Anzeigen von Berichten für Defender für Office 365](view-reports-for-atp.md)
