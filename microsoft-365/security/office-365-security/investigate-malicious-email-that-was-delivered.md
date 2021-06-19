---
title: Untersuchen schädlicher E-Mails, die in Office 365 zugestellt wurden, Suchen und Untersuchen bösartiger E-Mails
keywords: TIMailData-Inline, Sicherheitsvorfall, Vorfall, Microsoft Defender für Endpunkt PowerShell, E-Mail-Schadsoftware, kompromittierte Benutzer, E-Mail-Phishing, E-Mail-Schadsoftware, E-Mail-Kopfzeilen lesen, Kopfzeilen lesen, E-Mail-Header öffnen, spezielle Aktionen
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: 12/16/2020
audience: ITPro
ms.topic: article
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 8f54cd33-4af7-4d1b-b800-68f8818e5b2a
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie die Funktionen für die Untersuchung und Reaktion auf Bedrohungen verwenden, um schädliche E-Mails zu finden und zu untersuchen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ef29493bd68166b88bba3ef5905f0427823b4015
ms.sourcegitcommit: d904f04958a13a514ce10219ed822b9e4f74ca2d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2021
ms.locfileid: "53028851"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a>Untersuchen bösartiger E-Mails, die in Office 365 zugestellt wurden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**

- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Mit Microsoft Defender für Office 365](defender-for-office-365.md) können Sie Aktivitäten untersuchen, die Personen in Ihrer Organisation gefährden, und Maßnahmen zum Schutz Ihrer Organisation ergreifen. Wenn Sie beispielsweise Teil des Sicherheitsteams Ihrer Organisation sind, können Sie verdächtige E-Mail-Nachrichten finden und untersuchen, die zugestellt wurden. Dazu können Sie [den Bedrohungs-Explorer (oder Echtzeiterkennungen)](threat-explorer.md)verwenden.

> [!NOTE]
> Springen Sie [hier](remediate-malicious-email-delivered-office-365.md)zum Korrekturartikel.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Stellen Sie sicher, dass folgende Anforderungen erfüllt sind:

- Ihre Organisation verfügt [über Microsoft Defender für Office 365](defender-for-office-365.md) und Benutzern werden Lizenzen [zugewiesen.](../../admin/manage/assign-licenses-to-users.md)

- [Die Überwachungsprotokollierung](../../compliance/turn-audit-log-search-on-or-off.md) ist für Ihre Organisation aktiviert.

- Ihre Organisation hat Richtlinien für Antispam, Antischadsoftware, Antiphishing usw. definiert. Siehe ["Schutz vor Bedrohungen in Office 365.](protect-against-threats.md)

- Sie sind ein globaler Administrator, oder Sie haben entweder den Sicherheitsadministrator oder die Rolle "Suchen und Löschen" in Microsoft 365 Defender zugewiesen. Siehe ["Berechtigungen" im Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md). Für einige Aktionen muss auch eine neue Vorschaurolle zugewiesen sein.

### <a name="preview-role-permissions"></a>Rollenberechtigungen in der Vorschau anzeigen

Um bestimmte Aktionen auszuführen, z. B. das Anzeigen von Nachrichtenkopfzeilen oder das Herunterladen von E-Mail-Nachrichteninhalten, muss eine neue Rolle namens *"Vorschau"* zu einer anderen geeigneten Rollengruppe hinzugefügt werden. In der folgenden Tabelle werden die erforderlichen Rollen und Berechtigungen erläutert.

****

|Aktivität|Rollengruppe|Vorschaurolle erforderlich?|
|---|---|---|
|Verwenden des Bedrohungs-Explorers (und Echtzeiterkennungen) zum Analysieren von Bedrohungen |Globaler Administrator <p> Sicherheitsadministrator <p> Sicherheitsleseberechtigter|Nein|
|Verwenden des Bedrohungs-Explorers (und Echtzeiterkennungen) zum Anzeigen von Kopfzeilen für E-Mail-Nachrichten sowie zum Anzeigen einer Vorschau und zum Herunterladen von isolierten E-Mail-Nachrichten|Globaler Administrator <p> Sicherheitsadministrator <p> Sicherheitsleseberechtigter|Nein|
|Verwenden des Bedrohungs-Explorers zum Anzeigen von Headern, Anzeigen einer Vorschau von E-Mails (nur auf der Seite der E-Mail-Entität) und Herunterladen von E-Mail-Nachrichten, die an Postfächer übermittelt werden|Globaler Administrator <p> Sicherheitsadministrator <p> Sicherheitsleseberechtigter <p> Vorschau|Ja|
|

> [!NOTE]
> *Die Vorschau* ist eine Rolle und keine Rollengruppe. Die Vorschaurolle muss einer vorhandenen Rollengruppe für Office 365 (unter ) hinzugefügt <https://security.microsoft.com> werden. Wechseln Sie zu **"Berechtigungen",** und bearbeiten Sie dann entweder eine vorhandene Rollengruppe, oder fügen Sie eine neue Rollengruppe hinzu, der die **Vorschaurolle** zugewiesen ist.
> Die Rolle "Globaler Administrator" wird der Microsoft 365 Admin Center ( <https://admin.microsoft.com> ) zugewiesen, und die Rollen "Sicherheitsadministrator" und "Sicherheitsleseberechtigter" werden in Microsoft 365 Defender ( <https://security.microsoft.com> ) zugewiesen. Weitere Informationen zu Rollen und Berechtigungen finden Sie unter ["Berechtigungen" im Microsoft 365 Defender](permissions-in-the-security-and-compliance-center.md).

Wir wissen, dass das Anzeigen der Vorschau und das Herunterladen von E-Mails vertrauliche Aktivitäten sind, und daher ist die Überwachung für diese aktiviert. Sobald ein Administrator diese Aktivitäten für E-Mails durchführt, werden Überwachungsprotokolle für dasselbe generiert und können im Office 365 Microsoft 365 Defender ( ) angezeigt <https://security.microsoft.com> werden. Wechseln Sie zur **Suche** nach  >  **Überwachungsprotokollen,** und filtern Sie den Administratornamen im Abschnitt "Suche". Die gefilterten Ergebnisse zeigen Aktivität **AdminMailAccess** an. Wählen Sie eine Zeile aus, um Details im Abschnitt **"Weitere Informationen"** zu vorschaueten oder heruntergeladenen E-Mails anzuzeigen.

## <a name="find-suspicious-email-that-was-delivered"></a>Suchen nach verdächtigen E-Mails, die zugestellt wurden

Der Bedrohungs-Explorer ist ein leistungsstarker Bericht, der mehreren Zwecken dienen kann, z. B. dem Suchen und Löschen von Nachrichten, der Identifizierung der IP-Adresse eines böswilligen E-Mail-Absenders oder dem Starten eines Vorfalls zur weiteren Untersuchung. Der Schwerpunkt des folgenden Verfahrens liegt auf der Verwendung von Explorer, um schädliche E-Mails aus den Postfächern des Empfängers zu suchen und zu löschen.

> [!NOTE]
> Standardmäßige Suchvorgänge im Explorer enthalten derzeit keine "Zapped"-Elemente.  Dies gilt für alle Ansichten, z. B. Schadsoftware- oder Phishingansichten. Um "Zapped"-Elemente einzuschließen, müssen Sie einen **Übermittlungsaktionssatz** hinzufügen, um **"Von ZAP entfernt" einzuschließen.** Wenn Sie alle Optionen einschließen, werden alle Ergebnisse der Übermittlungsaktion angezeigt, einschließlich "Zapped"-Elemente.

1. **Navigieren Sie zum Bedrohungs-Explorer:** Rufen Sie <https://security.microsoft.com> Ihr Geschäfts-, Schul- oder Unikonto für Office 365 auf, und melden Sie sich an. Dadurch gelangen Sie zu Microsoft 365 Defender.

2. Wählen Sie im Linken Navigations-Schnellstart **E-Mail &** Zusammenarbeits-Explorer \> aus.

      Möglicherweise sehen Sie die neue Spalte **"Sonderaktionen".** Dieses Feature soll Administratoren das Ergebnis der Verarbeitung einer E-Mail mitteilen. Auf die Spalte **"Sonderaktionen"** kann an derselben Stelle wie die **Übermittlungsaktion** und der **Übermittlungsspeicherort** zugegriffen werden. Sonderaktionen können am Ende der E-Mail-Zeitachse des Bedrohungs-Explorers aktualisiert werden. Dies ist ein neues Feature, das darauf abzielt, die Suche für Administratoren zu verbessern.

3. **Ansichten im Bedrohungs-Explorer:** Wählen Sie im Menü **"Ansicht"** die Option **"Alle E-Mails"** aus.

    ![Ansichtsmenü des Bedrohungs-Explorers und E-Mail – Schadsoftware, Phishing, Übermittlungen und alle E-Mail-Optionen, auch Inhalt – Schadsoftware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    Die  Schadsoftwareansicht ist derzeit die Standardansicht und erfasst E-Mails, in denen eine Schadsoftware-Bedrohung erkannt wird. Die *Phish-Ansicht* funktioniert für Phishing auf die gleiche Weise.

    Die *gesamte E-Mail-Ansicht* listet jedoch jede von der Organisation empfangene E-Mail auf, unabhängig davon, ob Bedrohungen erkannt wurden oder nicht. Wie Sie sich vorstellen können, sind dies viele Daten, weshalb diese Ansicht einen Platzhalter anzeigt, der angibt, dass ein Filter angewendet werden soll. (Diese Ansicht ist nur für Defender für Office 365 P2-Kunden verfügbar.)

    *Die Ansicht "Übermittlungen"* zeigt alle von einem Administrator oder Benutzer übermittelten E-Mails an, die an Microsoft gemeldet wurden.

4. **Suchen und Filtern im Bedrohungs-Explorer:** Filter werden oben auf der Seite in der Suchleiste angezeigt, um Administratoren bei ihren Untersuchungen zu unterstützen. Beachten Sie, dass mehrere Filter gleichzeitig angewendet werden können und einem Filter mehrere durch Kommas getrennte Werte hinzugefügt werden, um die Suche einzugrenzen. Denken Sie daran:

    - Filter führen bei den meisten Filterbedingungen eine genaue Übereinstimmung aus.
    - Der Betrefffilter verwendet eine CONTAINS-Abfrage.
    - URL-Filter funktionieren mit oder ohne Protokolle (z. B. https).
    - URL-Domäne, URL-Pfad, URL-Domäne und Pfadfilter erfordern kein Protokoll zum Filtern.
    - Sie müssen jedes Mal auf das Symbol "Aktualisieren" klicken, wenn Sie die Filterwerte ändern, um relevante Ergebnisse zu erhalten.

5. **Erweiterte Filter:** Mit diesen Filtern können Sie komplexe Abfragen erstellen und Ihren Datensatz filtern. Durch Klicken auf *"Erweiterte Filter"* wird ein Flyout mit Optionen geöffnet.

   Die erweiterte Filterung ist eine hervorragende Ergänzung zu den Suchfunktionen. Ein boolescher **NOT-Filter** wurde für die Domäne *"Empfänger",* *"Absender"* und *"Absender"* eingeführt, um Administratoren die Untersuchung durch Ausschließen von Werten zu ermöglichen. Diese Option wird unter dem Auswahlparameter *"Contains none of"* angezeigt. **Nicht** zulassen, dass Administratoren Benachrichtigungspostfächer, Standardantwortpostfächer von ihren Untersuchungen ausschließen, und ist nützlich für Fälle, in denen Administratoren nach einem bestimmten Betreff suchen (subject="Attention"), in denen der Empfänger auf *keines der defaultMail-contoso.com \@* festgelegt werden kann. Dies ist eine genaue Wertesuche.

   ![Der Erweiterte Filter "Recipients - Enthält keinen von".](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   *Die Filterung nach Stunden* hilft dem Sicherheitsteam Ihrer Organisation, schnell einen Drilldown durchzuführen. Die kürzeste zulässige Zeitdauer beträgt 30 Minuten. Wenn Sie die verdächtige Aktion nach Zeitrahmen eingrenzen können (z. B. vor 3 Stunden), schränkt dies den Kontext ein und hilft, das Problem zu erkennen.

   ![Die Option zum Filtern nach Stunden, um die Anzahl der zu verarbeitenden Datensicherheitsteams einzuschränken, deren kürzeste Dauer 30 Minuten beträgt.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Felder im Bedrohungs-Explorer:** Der Bedrohungs-Explorer macht wesentlich mehr sicherheitsrelevante E-Mail-Informationen verfügbar, z. B. *Übermittlungsaktion,* *Übermittlungsort,* *Sonderaktion,* *Direktionalität,* *Außerkraftsetzungen* und *URL-Bedrohung.* Außerdem kann das Sicherheitsteam Ihrer Organisation mit höherer Sicherheit untersuchen.

    *Übermittlungsaktion* ist die Aktion, die aufgrund vorhandener Richtlinien oder Erkennungen für eine E-Mail ausgeführt wird. Hier sind die möglichen Aktionen, die eine E-Mail ausführen kann:

    - **Zugestellt** – E-Mail wurde an den Posteingang oder Ordner eines Benutzers übermittelt, und der Benutzer kann direkt darauf zugreifen.
    - **Junk** -E-Mails (an Junk übermittelt) – E-Mails wurden entweder an den Junk-Ordner des Benutzers oder an den gelöschten Ordner gesendet, und der Benutzer hat Zugriff auf E-Mail-Nachrichten im Junk- oder gelöschten Ordner.
    - **Blockiert** – alle E-Mail-Nachrichten, die isoliert sind, fehlgeschlagen sind oder verworfen wurden. (Der Benutzer kann nicht darauf zugreifen.)
    - **Ersetzt** – alle E-Mails, bei denen schädliche Anlagen durch .txt Dateien ersetzt werden, die angeben, dass die Anlage bösartig war

    **Übermittlungsort:** Der Filter "Übermittlungsort" ist verfügbar, um Administratoren zu helfen, zu verstehen, wo verdächtige bösartige E-Mails geendet haben und welche Maßnahmen dagegen ergriffen wurden. Die resultierenden Daten können in eine Tabellenkalkulation exportiert werden. Mögliche Übermittlungsorte sind:

    - **Posteingang oder Ordner** – Die E-Mail befindet sich gemäß Ihren E-Mail-Regeln im Posteingang oder in einem bestimmten Ordner.
    - **Lokal oder extern** – Das Postfach ist nicht in der Cloud vorhanden, sondern lokal.
    - **Junk-Ordner** – Die E-Mail befindet sich im Junk-E-Mail-Ordner eines Benutzers.
    - **Ordner "Gelöschte Elemente":** Die E-Mail befindet sich im Ordner "Gelöschte Elemente" eines Benutzers.
    - **Quarantäne** – Die E-Mail in Quarantäne und nicht im Postfach eines Benutzers.
    - **Fehlgeschlagen–** Die E-Mail konnte das Postfach nicht erreichen.
    - **Verworfen** – Die E-Mail wurde an einer anderen Stelle im Nachrichtenfluss verloren.

    **Richtungsabhängigkeit:** Mit dieser Option kann Ihr Sicherheitsteam nach der "Richtung" filtern, aus der eine E-Mail stammt oder die gerade ausgeführt wird. Direktionalitätswerte sind *eingehende,* *ausgehende* und organisationsinterne Nachrichten (entspricht *E-Mails,* die von außen in Ihre Organisation gelangen, von Ihrer Organisation gesendet oder intern an Ihre Organisation gesendet werden). Diese Informationen können Sicherheitsteams dabei helfen, Spoofing und Identitätswechsel zu erkennen, da ein Konflikt zwischen dem Directionality-Wert (z. B. *Eingehend)* und die Domäne des Absenders (die *scheinbar* eine interne Domäne ist) sind offensichtlich! Der Directionality-Wert ist getrennt und kann sich von der Nachrichtenablaufverfolgung unterscheiden. Ergebnisse können in eine Tabellenkalkulation exportiert werden.

    **Außerkraftsetzungen:** Dieser Filter akzeptiert Informationen, die auf der Registerkarte "Details" der E-Mail angezeigt werden, und macht damit offen, wo Organisations- oder Benutzerrichtlinien zum Zulassen und Blockieren von E-Mails *überschrieben* wurden. Das Wichtigste an diesem Filter ist, dass er dem Sicherheitsteam Ihrer Organisation hilft, zu sehen, wie viele verdächtige E-Mails aufgrund der Konfiguration zugestellt wurden. Dadurch haben sie die Möglichkeit, die Berechtigungen und Blöcke nach Bedarf zu ändern. Dieses Resultset dieses Filters kann in eine Tabellenkalkulation exportiert werden.

    ****

    |Außerkraftsetzungen des Bedrohungs-Explorers|Bedeutung|
    |---|---|
    |Zulässig nach Organisationsrichtlinie|E-Mails wurden gemäß der Organisationsrichtlinie in das Postfach zugelassen.|
    |Blockiert durch Die Organisationsrichtlinie|Die Zustellung von E-Mails an das Postfach wurde gemäß der Organisationsrichtlinie blockiert.|
    |Dateierweiterung durch Organisationsrichtlinie blockiert|Die Übermittlung der Datei an das Postfach wurde gemäß der Organisationsrichtlinie blockiert.|
    |Zulässig durch Benutzerrichtlinie|E-Mails wurden gemäß der Benutzerrichtlinie in das Postfach zugelassen.|
    |Blockiert durch Benutzerrichtlinie|Die Zustellung von E-Mails an das Postfach wurde gemäß der Benutzerrichtlinie blockiert.|
    |

    **URL-Bedrohung:** Das URL-Bedrohungsfeld wurde auf der *Registerkarte "Details"* einer E-Mail hinzugefügt, um die von einer URL dargestellte Bedrohung anzugeben. Bedrohungen, die von einer URL angezeigt werden, können *Schadsoftware,* *Phishing* oder *Spam* enthalten, und eine URL *ohne Bedrohung* *wird* im Abschnitt "Keine Bedrohungen" lauten.

7. **Ansicht der E-Mail-Zeitachse:** Ihr Sicherheitsteam muss sich möglicherweise eingehender mit E-Mail-Details befassen, um weitere Untersuchungen durchführen zu können. Auf der E-Mail-Zeitachse können Administratoren Aktionen anzeigen, die für eine E-Mail von der Zustellung bis zur Nach zustellung ausgeführt wurden. Klicken Sie zum Anzeigen einer E-Mail-Zeitachse auf den Betreff einer E-Mail-Nachricht, und klicken Sie dann auf die E-Mail-Zeitachse. (Es wird unter anderen Überschriften im Bereich angezeigt, z. B. Zusammenfassung oder Details.) Diese Ergebnisse können in eine Tabellenkalkulation exportiert werden.

    Die E-Mail-Zeitachse wird in einer Tabelle geöffnet, in der alle Zustellungs- und Nachzustellereignisse für die E-Mail angezeigt werden. Wenn keine weiteren Aktionen für die E-Mail vorhanden sind, sollten Sie ein einzelnes Ereignis für die ursprüngliche Zustellung sehen, das ein Ergebnis angibt, z. B. *blockiert*, mit einem Diktat wie *Phishing*. Administratoren können die gesamte E-Mail-Zeitachse exportieren, einschließlich aller Details auf der Registerkarte und der E-Mail (z. B. Betreff, Absender, Empfänger, Netzwerk und Nachrichten-ID). Die E-Mail-Zeitachse reduziert die Zufälligkeit, da weniger Zeit für die Überprüfung verschiedener Orte aufgewendet wird, um zu versuchen, Ereignisse zu verstehen, die seit dem Eintreffen der E-Mail aufgetreten sind. Wenn mehrere Ereignisse gleichzeitig in einer E-Mail oder in der Nähe auftreten, werden diese Ereignisse in einer Zeitachsenansicht angezeigt.

8. **Vorschau/Download:** Der Bedrohungs-Explorer gibt Ihrem Sicherheitsteam die Details, die sie zum Untersuchen verdächtiger E-Mails benötigen. Ihr Sicherheitsteam kann folgende Aktionen ausführen:

    - [Überprüfen Sie die Übermittlungsaktion und den Speicherort.](#check-the-delivery-action-and-location)

    - [Zeigen Sie die Zeitachse Ihrer E-Mail an.](#view-the-timeline-of-your-email)

### <a name="check-the-delivery-action-and-location"></a>Überprüfen der Übermittlungsaktion und des Speicherorts

Im [Bedrohungs-Explorer (und Echtzeiterkennungen)](threat-explorer.md)verfügen Sie jetzt über die Spalten **"Übermittlungsaktion"** und **"Übermittlungsort"** anstelle der früheren Spalte **"Zustellungsstatus".** Dadurch erhalten Sie ein vollständigeres Bild davon, wo Ihre E-Mail-Nachrichten landen. Ein Teil des Ziels dieser Änderung ist es, Untersuchungen für Sicherheitsteams zu vereinfachen, aber das Ergebnis ist, den Speicherort der problematischen E-Mail-Nachrichten auf einen Blick zu kennen.

Der Übermittlungsstatus ist jetzt in zwei Spalten unterteilt:

- **Zustellungsaktion** – Wie lautet der Status dieser E-Mail?

- **Übermittlungsort** – Wo wurde diese E-Mail als Ergebnis weitergeleitet?

Übermittlungsaktion ist die Aktion, die aufgrund vorhandener Richtlinien oder Erkennungen für eine E-Mail ausgeführt wird. Hier sind die möglichen Aktionen, die eine E-Mail ausführen kann:

- **Zugestellt** – E-Mail wurde an den Posteingang oder Ordner eines Benutzers übermittelt, und der Benutzer kann direkt darauf zugreifen.

- **Junk -** E-Mails wurden entweder an den Junk-Ordner des Benutzers oder an den gelöschten Ordner gesendet, und der Benutzer hat Zugriff auf E-Mail-Nachrichten im Junk- oder gelöschten Ordner.

- **Blockiert** – alle E-Mail-Nachrichten, die isoliert sind, fehlgeschlagen sind oder verworfen wurden. (Der Benutzer kann nicht darauf zugreifen.)

- **Ersetzt** – alle E-Mails, bei denen schädliche Anlagen durch .txt Dateien ersetzt werden, die angeben, dass die Anlage bösartig war.

Der Übermittlungsort zeigt die Ergebnisse von Richtlinien und Erkennungen an, die nach der Zustellung ausgeführt werden. Es ist mit einer Übermittlungsaktion verknüpft. Dieses Feld wurde hinzugefügt, um Einblicke in die Aktion zu geben, die ausgeführt wird, wenn eine Problem-E-Mail gefunden wird. Hier sind die möglichen Werte des Übermittlungsorts:

- **Posteingang oder Ordner** – Die E-Mail befindet sich im Posteingang oder in einem Ordner (gemäß Ihren E-Mail-Regeln).

- **Lokal oder extern** – Das Postfach ist nicht in der Cloud vorhanden, sondern lokal.

- **Junk-Ordner** – Die E-Mail befindet sich im Junk-Ordner eines Benutzers.

- **Ordner "Gelöschte Elemente":** Die E-Mail befindet sich im Ordner "Gelöschte Elemente" eines Benutzers.

- **Quarantäne** – Die E-Mail in Quarantäne und nicht im Postfach eines Benutzers.

- **Fehlgeschlagen–** Die E-Mail konnte das Postfach nicht erreichen.

- **Verworfen** – Die E-Mail geht an einer anderen Stelle im Nachrichtenfluss verloren.

### <a name="view-the-timeline-of-your-email"></a>Anzeigen der Zeitachse Ihrer E-Mail

**Die E-Mail-Zeitachse** ist ein Feld im Bedrohungs-Explorer, das die Suche für Ihr Sicherheitsteam vereinfacht. Wenn mehrere Ereignisse gleichzeitig oder in der Nähe einer E-Mail auftreten, werden diese Ereignisse in einer Zeitachsenansicht angezeigt. Einige Ereignisse, die nach der Zustellung an E-Mails auftreten, werden in der Spalte **"Sonderaktionen"** erfasst. Das Kombinieren von Informationen aus der Zeitachse einer E-Mail-Nachricht mit speziellen Aktionen, die nach der Zustellung ausgeführt wurden, bietet Administratoren Einblicke in Richtlinien und die Bedrohungsbehandlung (z. B. wo die E-Mail weitergeleitet wurde und in einigen Fällen, was die endgültige Bewertung war).

> [!IMPORTANT]
> Wechseln Sie [hier](remediate-malicious-email-delivered-office-365.md)zu einem Problembehebungsthema.

## <a name="related-topics"></a>Verwandte Themen

[Beheben bösartiger E-Mails, die in Office 365 zugestellt wurden](remediate-malicious-email-delivered-office-365.md)

[Microsoft Defender für Office 365](office-365-ti.md)

[Schutz vor Bedrohungen in Office 365](protect-against-threats.md)

[Anzeigen von Berichten für Defender für Office 365](view-reports-for-mdo.md)
