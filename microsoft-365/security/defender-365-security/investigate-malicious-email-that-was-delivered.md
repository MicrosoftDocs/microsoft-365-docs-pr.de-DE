---
title: Untersuchen schädlicher E-Mails, die in Office 365 zugestellt wurden, Suchen und Untersuchen von schädlichen E-Mails
keywords: TIMailData-Inline, Sicherheitsvorfall, Vorfall, ATP PowerShell, E-Mail-Schadsoftware, gefährdete Benutzer, E-Mail-Phish, E-Mail-Schadsoftware, E-Mail-Kopfzeilen lesen, Kopfzeilen lesen, E-Mail-Kopfzeilen öffnen,spezielle Aktionen
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
description: Erfahren Sie, wie Sie Bedrohungsuntersuchungs- und Reaktionsfunktionen verwenden, um schädliche E-Mails zu finden und zu untersuchen.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2781850eacf8b0fcf4909406aca335f1bbeb0753
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065232"
---
# <a name="investigate-malicious-email-that-was-delivered-in-office-365"></a>Untersuchen schädlicher E-Mails, die in Office 365 zugestellt wurden

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**

- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Mit Microsoft Defender für Office 365](defender-for-office-365.md) können Sie Aktivitäten untersuchen, die Personen in Ihrer Organisation gefährden, und Maßnahmen zum Schutz Ihrer Organisation ergreifen. Wenn Sie beispielsweise Teil des Sicherheitsteams Ihrer Organisation sind, können Sie verdächtige E-Mail-Nachrichten finden und untersuchen, die zugestellt wurden. Sie können dies mithilfe von [Threat Explorer (oder Echtzeiterkennungen) tun.](threat-explorer.md)

> [!NOTE]
> Wechseln Sie hier zum [Korrekturartikel.](remediate-malicious-email-delivered-office-365.md)

## <a name="before-you-begin"></a>Vorbereitung

Stellen Sie sicher, dass folgende Anforderungen erfüllt sind:

- Ihre Organisation verfügt [über Microsoft Defender für Office 365,](defender-for-office-365.md) und Benutzern werden Lizenzen [zugewiesen.](../../admin/manage/assign-licenses-to-users.md)

- [Die Überwachungsprotokollierung](../../compliance/turn-audit-log-search-on-or-off.md) ist für Ihre Organisation aktiviert.

- In Ihrer Organisation sind Richtlinien für Antispam, An malware, Antiphishing und so weiter definiert. Weitere [Informationen finden Sie unter Protect against threats in Office 365](protect-against-threats.md).

- Sie sind ein globaler Administrator oder haben entweder den Sicherheitsadministrator oder die Rolle Suchen und Löschen im Security & Compliance Center zugewiesen. Siehe [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md). Für einige Aktionen muss auch eine neue Vorschaurolle zugewiesen sein.

### <a name="preview-role-permissions"></a>Vorschau von Rollenberechtigungen

Um bestimmte Aktionen wie das Anzeigen von Nachrichtenkopfzeilen oder das Herunterladen von E-Mail-Nachrichteninhalten ausführen zu können, muss eine neue Rolle namens *Vorschau* einer anderen geeigneten Rollengruppe hinzugefügt werden. In der folgenden Tabelle werden die erforderlichen Rollen und Berechtigungen erläutert.

****

|Aktivität|Rollengruppe|Vorschaurolle erforderlich?|
|---|---|---|
|Verwenden von Bedrohungs-Explorer (und Echtzeiterkennungen) zum Analysieren von Bedrohungen |Globaler Administrator <p> Sicherheitsadministrator <p> Sicherheitsleseberechtigter|Nein|
|Verwenden des Bedrohungs-Explorers (und Echtzeiterkennungen) zum Anzeigen von Kopfzeilen für E-Mail-Nachrichten sowie zum Anzeigen einer Vorschau und zum Herunterladen von isolierten E-Mail-Nachrichten|Globaler Administrator <p> Sicherheitsadministrator <p> Sicherheitsleseberechtigter|Nein|
|Verwenden des Bedrohungs-Explorers zum Anzeigen von Kopfzeilen, Anzeigen einer Vorschau von E-Mails (nur auf der E-Mail-Entitätsseite) und Herunterladen von E-Mail-Nachrichten, die an Postfächer übermittelt werden|Globaler Administrator <p> Sicherheitsadministrator <p> Sicherheitsleseberechtigter <p> Vorschau|Ja|
|

> [!NOTE]
> *Vorschau* ist eine Rolle und keine Rollengruppe; die Vorschaurolle muss einer vorhandenen Rollengruppe für Office 365 (unter) hinzugefügt <https://protection.office.com> werden. Wechseln Sie **zu Berechtigungen,** und bearbeiten Sie dann entweder eine vorhandene Rollengruppe, oder fügen Sie eine neue Rollengruppe hinzu, der die **Vorschaurolle** zugewiesen ist.
> Der Rolle globaler Administrator wird das Microsoft 365 Admin Center ( ) zugewiesen, und die Rollen Security Administrator und Security Reader werden im <https://admin.microsoft.com> Security & Compliance Center ( ) <https://protection.office.com> zugewiesen. Weitere Informationen zu Rollen und Berechtigungen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

Wir wissen, dass das Anzeigen und Herunterladen von E-Mails vertrauliche Aktivitäten sind, und daher ist die Überwachung für diese aktiviert. Sobald ein Administrator diese Aktivitäten in E-Mails ausführt, werden Überwachungsprotokolle für dasselbe generiert und können im Office 365 Security & Compliance Center ( ) angezeigt <https://protection.office.com> werden. Wechseln Sie **zur Suche**  >  **nach Überwachungsprotokollen,** und filtern Sie im Abschnitt Suchen nach dem Administratornamen. Die gefilterten Ergebnisse zeigen die Aktivität **AdminMailAccess an.** Wählen Sie eine Zeile aus, um Details im Abschnitt **Weitere Informationen** zu E-Mails in der Vorschau anzuzeigen.

## <a name="find-suspicious-email-that-was-delivered"></a>Suchen verdächtiger E-Mails, die zugestellt wurden

Der Bedrohungs-Explorer ist ein leistungsstarker Bericht, der mehreren Zwecken dienen kann, z. B. dem Suchen und Löschen von Nachrichten, dem Identifizieren der IP-Adresse eines böswilligen E-Mail-Absenders oder dem Starten eines Vorfalls zur weiteren Untersuchung. Das folgende Verfahren konzentriert sich auf die Verwendung von Explorer zum Suchen und Löschen schädlicher E-Mails aus den Postfächern des Empfängers.

> [!NOTE]
> Standardsuchen im Explorer enthalten derzeit keine zapped-Elemente.  Dies gilt für alle Ansichten, z. B. Schadsoftware- oder Phishingansichten. Zum Hinzufügen von zapped-Elementen müssen Sie einen **Delivery-Aktionssatz** hinzufügen, der **entfernt von ZAP enthält.** Wenn Sie alle Optionen enthalten, werden alle Ergebnisse der Zustellungsaktion angezeigt, einschließlich zapped-Elementen.

1. **Navigieren Sie zu Bedrohungs-Explorer:** Wechseln Sie zu und melden Sie sich mit Ihrem Geschäfts- oder <https://protection.office.com> Schulkonto für Office 365 an. Dies führt Sie zum Security & Compliance Center.

2. Wählen Sie in der linken Navigationsschnellstart die Option **Bedrohungsverwaltungs-Explorer** \> **aus.**

    ![Explorer mit den Feldern Zustellungsaktion und Zustellungsspeicherort.](../../media/ThreatExFields.PNG)

    Möglicherweise sehen Sie die neue **Spalte Sonderaktionen.** Dieses Feature soll Administratoren das Ergebnis der Verarbeitung einer E-Mail mitzuteilen. Auf **die Spalte** Sonderaktionen kann an derselben Stelle wie die Zustellungsaktion und der  **Zustellungsspeicherort zugegriffen werden.** Spezielle Aktionen können am Ende der E-Mail-Zeitachse des Bedrohungs-Explorers aktualisiert werden. Dabei handelt es sich um ein neues Feature, mit dem die Suche für Administratoren verbessert werden soll.

3. **Ansichten im Bedrohungs-Explorer:** Wählen Sie im Menü **Ansicht** alle **E-Mails aus.**

    ![Menü "Ansicht des Bedrohungs-Explorers" und "E-Mail- Schadsoftware,Phish", "Übermittlungen" und "Alle E-Mail-Optionen", auch Inhalt - Schadsoftware.](../../media/tp-InvestigateMalEmail-viewmenu.png)

    Die *Schadsoftwareansicht* ist derzeit die Standardeinstellung und erfasst E-Mails, in denen eine Schadsoftwarebedrohung erkannt wird. Die *Phish-Ansicht* funktioniert für Phish auf die gleiche Weise.

    In der *E-Mail-Ansicht* werden jedoch alle von der Organisation empfangenen E-Mails aufgeführt, unabhängig davon, ob Bedrohungen erkannt wurden oder nicht. Wie Sie sich vorstellen können, handelt es sich um eine Große Menge von Daten, weshalb in dieser Ansicht ein Platzhalter angezeigt wird, der die Anwendung eines Filters fordert. (Diese Ansicht ist nur für Defender für Office 365 P2-Kunden verfügbar.)

    *Die Übermittlungsansicht* zeigt alle E-Mails an, die vom Administrator oder Benutzer übermittelt wurden, die an Microsoft gemeldet wurden.

4. **Suchen und Filtern im Bedrohungs-Explorer:** Filter werden oben auf der Seite in der Suchleiste angezeigt, um Administratoren bei ihren Ermittlungen zu unterstützen. Beachten Sie, dass mehrere Filter gleichzeitig angewendet werden können und einem Filter mehrere durch Kommas getrennte Werte hinzugefügt werden, um die Suche einengt. Denken Sie daran:

    - Filter können für die meisten Filterbedingungen exakt übereinstimmen.
    - Der Betrefffilter verwendet eine CONTAINS-Abfrage.
    - URL-Filter funktionieren mit oder ohne Protokolle (z. B. https).
    - FÜR URL-Domänen-, URL-Pfad- und URL-Domänen- und -Pfadfilter ist kein Filterprotokoll erforderlich.
    - Sie müssen jedes Mal auf das Symbol Aktualisieren klicken, wenn Sie die Filterwerte ändern, um relevante Ergebnisse zu erhalten.

5. **Erweiterte Filter:** Mit diesen Filtern können Sie komplexe Abfragen erstellen und Ihren Datensatz filtern. Wenn Sie auf *Erweiterte Filter klicken,* wird ein Flyout mit Optionen geöffnet.

   Die erweiterte Filterung ist eine großartige Ergänzung der Suchfunktionen. In der Domäne *Empfänger,* Absender  und  Absender wurde ein boolescher **NOT-Filter** eingeführt, um Administratoren die Untersuchung durch Ausschließen von Werten zu ermöglichen. Diese Option wird unter selection parameter *Contains none of angezeigt.* **NOT** lässt Administratoren Benachrichtigungspostfächer, Standardantwortpostfächer von ihren Untersuchungen ausschließen und ist nützlich für Fälle, in denen Administratoren nach einem bestimmten Betreff suchen (subject="Attention"), in dem der Empfänger auf keines der defaultMail-contoso.com festgelegt werden *\@ kann.* Dies ist eine genaue Wertsuche.

   ![Der Filter Recipients - "Contains none of" Advanced.](../../media/tp-InvestigateMalEmail-AdvancedFilter.png)

   *Das Filtern nach Stunden* hilft dem Sicherheitsteam Ihrer Organisation, schnell einen Drilldown zu erstellen. Die kürzeste zulässige Zeitdauer beträgt 30 Minuten. Wenn Sie die verdächtige Aktion nach Zeitrahmen eingrenzn können (z. B. vor 3 Stunden), wird der Kontext dadurch begrenzt, und das Problem kann dadurch behoben werden.

   ![Die Option filtert nach Stunden, um die Menge der datensicherheitsteams zu kürzen, deren kürzeste Dauer 30 Minuten beträgt.](../../media/tp-InvestigateMalEmail-FilterbyHours.png)

6. **Felder im Bedrohungs-Explorer:** Der Bedrohungs-Explorer macht viel mehr sicherheitsrelevante E-Mail-Informationen verfügbar, z. B. *Zustellungsaktion, Zustellungsspeicherort,*  *Spezielle* *Aktion,* Direktionalität, Außerkraftsetzungen und *URL-Bedrohung.* Außerdem kann das Sicherheitsteam Ihrer Organisation mit höherer Sicherheit untersuchen.

    *Übermittlungsaktion* ist die Aktion, die aufgrund vorhandener Richtlinien oder Erkennungen für eine E-Mail ergriffen wird. Hier sind die möglichen Aktionen, die eine E-Mail ausführen kann:

    - **Zugestellt** – E-Mails wurden an den Posteingang oder Ordner eines Benutzers übermittelt, und der Benutzer kann direkt darauf zugreifen.
    - **Junked** (An Junk übermittelt) – E-Mails wurden entweder an den Junkordner oder gelöschten Ordner des Benutzers gesendet, und der Benutzer hat Zugriff auf E-Mail-Nachrichten in ihrem Junk- oder Deleted-Ordner.
    - **Blockiert** – alle E-Mail-Nachrichten, die isoliert, fehlgeschlagen oder gelöscht wurden. (Auf die kann der Benutzer nicht mehr zugegriffen werden.)
    - **Ersetzt** – E-Mails, bei denen schädliche Anlagen durch TXT-Dateien ersetzt werden, in denen die Anlage als schädlich bezeichnet wird

    **Zustellungsort:** Der Filter "Zustellungsort" ist verfügbar, um Administratoren zu helfen, zu verstehen, wo mutmaßliche schädliche E-Mails geentert wurden und welche Aktionen ergriffen wurden. Die resultierenden Daten können in eine Tabellenkalkulation exportiert werden. Mögliche Zustellungsorte sind:

    - **Posteingang oder Ordner** – Die E-Mail befindet sich gemäß Ihren E-Mail-Regeln im Posteingang oder in einem bestimmten Ordner.
    - **Lokal oder extern** – Das Postfach ist nicht in der Cloud vorhanden, sondern lokal.
    - **Junkordner** – Die E-Mail befindet sich im Junk-E-Mail-Ordner eines Benutzers.
    - **Ordner "Gelöschte** Elemente": Die E-Mail befindet sich im Ordner Gelöschte Elemente eines Benutzers.
    - **Quarantäne** – Die E-Mail in Quarantäne und nicht im Postfach eines Benutzers.
    - **Fehler** – Die E-Mail konnte das Postfach nicht erreichen.
    - **Dropped** – Die E-Mail ging an einer anderen Stelle im Nachrichtenfluss verloren.

    **Direktionalität:** Mit dieser Option kann Ihr Sicherheitsteam nach der "Richtung" filtern, von der eine E-Mail stammt oder gerade läuft. Direktionalitätswerte sind Eingehende *,* Ausgehende und Intra-Organisation (entspricht *E-Mails,* die von außerhalb in Ihre Organisation kommen, aus Ihrer Organisation gesendet werden oder intern an Ihre Organisation gesendet werden). Diese Informationen können Sicherheitsteams dabei helfen, Spoofing und Identitätswechsel zu erkennen, da ein Konflikt zwischen dem Directionality-Wert (z. B. *Eingehende ),* und die Domäne des Absenders (die *eine* interne Domäne zu sein scheint) wird offensichtlich sein! Der Directionality-Wert ist getrennt und kann sich von der Nachrichtenverfolgung unterscheiden. Ergebnisse können in eine Tabellenkalkulation exportiert werden.

    **Außerkraftsetzungen**: Dieser Filter verwendet Informationen, die auf der Registerkarte Details der E-Mail angezeigt werden, und verwendet ihn, um verfügbar zu machen, wo Organisations- oder Benutzerrichtlinien zum Zulassen und Blockieren von E-Mails außer Kraft gesetzt *wurden.* Das Wichtigste an diesem Filter ist, dass es dem Sicherheitsteam Ihrer Organisation hilft, zu sehen, wie viele verdächtige E-Mails aufgrund der Konfiguration zugestellt wurden. Dies gibt ihnen die Möglichkeit, die Zu- und Absperren nach Bedarf zu ändern. Dieser Ergebnissatz dieses Filters kann in eine Tabellenkalkulation exportiert werden.

    ****

    |Außerkraftsetzungen des Bedrohungs-Explorers|Was sie bedeuten|
    |---|---|
    |Von der Organisationsrichtlinie zugelassen|E-Mails wurden wie von der Organisationsrichtlinie geleitet in das Postfach zugelassen.|
    |Von der Organisationsrichtlinie blockiert|Die Zustellung von E-Mails an das Postfach wurde wie von der Organisationsrichtlinie geleitet blockiert.|
    |Von der Organisationsrichtlinie blockierte Dateierweiterung|Die Zustellung der Datei an das Postfach wurde wie von der Organisationsrichtlinie geleitet blockiert.|
    |Zulässig nach Benutzerrichtlinie|E-Mails wurden wie von der Benutzerrichtlinie geleitet in das Postfach zugelassen.|
    |Durch Benutzerrichtlinie blockiert|Die Zustellung von E-Mails an das Postfach wurde wie von der Benutzerrichtlinie geleitet blockiert.|
    |

    **URL-Bedrohung:** Das Feld URL-Bedrohung  wurde auf der Registerkarte Details einer E-Mail enthalten, um die Bedrohung anzugeben, die durch eine URL dargestellt wird. Bedrohungen, die von einer URL dargestellt werden, können  *Schadsoftware,* *Phishing* oder *Spam* umfassen, und eine URL ohne Bedrohungen wird im Abschnitt Bedrohungen *keines* sagen.

7. E-Mail-Zeitachsenansicht: Ihr Sicherheitsteam muss möglicherweise tief in die E-Mail-Details eintauchen, um weitere Untersuchungen durchzuführen. Auf der E-Mail-Zeitachse können Administratoren Aktionen anzeigen, die für eine E-Mail von der Zustellung bis zur Postzustellung ergriffen wurden. Klicken Sie zum Anzeigen einer E-Mail-Zeitachse auf den Betreff einer E-Mail-Nachricht, und klicken Sie dann auf E-Mail-Zeitachse. (Es wird unter anderen Überschriften im Bereich angezeigt, z. B. Zusammenfassung oder Details.) Diese Ergebnisse können in eine Tabellenkalkulation exportiert werden.

    Die E-Mail-Zeitachse wird für eine Tabelle geöffnet, in der alle Zustellungs- und Postzustellungsereignisse für die E-Mail angezeigt werden. Wenn keine weiteren Aktionen in der E-Mail enthalten sind, sollte ein einzelnes Ereignis für die ursprüngliche Zustellung mit einem Ergebnis wie *Blockiert* mit einem Urteil wie *Phish zu sehen sein.* Administratoren können die gesamte E-Mail-Zeitachse exportieren, einschließlich aller Details auf der Registerkarte und E-Mail (z. B. Betreff, Absender, Empfänger, Netzwerk und Nachrichten-ID). Die E-Mail-Zeitachse reduziert die Randomisierung, da weniger Zeit damit verbracht wird, verschiedene Speicherorte zu überprüfen, um ereignisse zu verstehen, die seit dem Eintreffen der E-Mail passiert sind. Wenn mehrere Ereignisse gleichzeitig oder in der Nähe einer E-Mail auftreten, werden diese Ereignisse in einer Zeitachsenansicht angezeigt.

8. **Vorschau/Download:** Der Bedrohungs-Explorer gibt Ihrem Sicherheitsteam die Details, die sie zum Untersuchen verdächtiger E-Mails benötigen. Ihr Sicherheitsbetriebsteam kann:

    - [Überprüfen Sie die Zustellungsaktion und den Speicherort](#check-the-delivery-action-and-location).

    - [Zeigen Sie die Zeitachse Ihrer E-Mail an.](#view-the-timeline-of-your-email)

### <a name="check-the-delivery-action-and-location"></a>Überprüfen der Zustellungsaktion und des Speicherorts

Im [Bedrohungs-Explorer (und In-Time-Erkennungen)](threat-explorer.md)  haben Sie jetzt die Spalten **Zustellungsaktion** und Zustellungsspeicherort anstelle der früheren **Spalte Zustellungsstatus.** Dies führt zu einem vollständigeren Bild, wo Ihre E-Mail-Nachrichten landen. Teil des Ziels dieser Änderung ist es, Untersuchungen für Sicherheitsteams zu vereinfachen, aber das Ergebnis ist, den Speicherort von problematischen E-Mail-Nachrichten auf einen Blick zu kennen.

Der Zustellungsstatus ist nun in zwei Spalten aufgeschlüsselt:

- **Zustellungsaktion** – Wie ist der Status dieser E-Mail?

- **Zustellungsspeicherort** – Wo wurde diese E-Mail als Ergebnis geroutet?

Übermittlungsaktion ist die Aktion, die aufgrund vorhandener Richtlinien oder Erkennungen für eine E-Mail ergriffen wird. Hier sind die möglichen Aktionen, die eine E-Mail ausführen kann:

- **Zugestellt** – E-Mails wurden an den Posteingang oder Ordner eines Benutzers übermittelt, und der Benutzer kann direkt darauf zugreifen.

- **Junked** – E-Mails wurden entweder an den Junk- oder den gelöschten Ordner des Benutzers gesendet, und der Benutzer hat Zugriff auf E-Mail-Nachrichten im Junk- oder Gelöschten Ordner.

- **Blockiert** – alle E-Mail-Nachrichten, die isoliert, fehlgeschlagen oder gelöscht wurden. (Auf die kann der Benutzer nicht mehr zugegriffen werden.)

- **Ersetzt** – alle E-Mails, bei denen schädliche Anlagen durch TXT-Dateien ersetzt werden, in denen die Anlage als schädlich bezeichnet wird.

Der Zustellungsspeicherort zeigt die Ergebnisse von Richtlinien und Erkennungen an, die nach der Zustellung ausgeführt werden. Es ist mit einer Zustellungsaktion verknüpft. Dieses Feld wurde hinzugefügt, um Einen Einblick in die Aktion zu erhalten, die beim Finden einer Problem-E-Mail ergriffen wurde. Hier sind die möglichen Werte des Zustellungsspeicherorts:

- **Posteingang oder Ordner** – Die E-Mail befindet sich im Posteingang oder in einem Ordner (gemäß Ihren E-Mail-Regeln).

- **Lokal oder extern** – Das Postfach ist nicht in der Cloud vorhanden, sondern lokal.

- **Junkordner** – Die E-Mail befindet sich im Junkordner eines Benutzers.

- **Ordner "Gelöschte** Elemente": Die E-Mail befindet sich im Ordner Gelöschte Elemente eines Benutzers.

- **Quarantäne** – Die E-Mail in Quarantäne und nicht im Postfach eines Benutzers.

- **Fehler** – Die E-Mail konnte das Postfach nicht erreichen.

- **Dropped** – Die E-Mail geht an einem anderen Ort im Nachrichtenfluss verloren.

### <a name="view-the-timeline-of-your-email"></a>Anzeigen der Zeitachse Ihrer E-Mail

**Die** E-Mail-Zeitachse ist ein Feld im Bedrohungs-Explorer, das die Suche für Ihr Sicherheitsteam vereinfacht. Wenn mehrere Ereignisse gleichzeitig oder in der Nähe einer E-Mail auftreten, werden diese Ereignisse in einer Zeitachsenansicht angezeigt. Einige Ereignisse, die nach der Zustellung an E-Mails auftreten, werden in der Spalte **Spezielle Aktionen** erfasst. Wenn Sie Informationen aus der Zeitachse einer E-Mail-Nachricht mit speziellen Aktionen kombinieren, die nach der Zustellung ergriffen wurden, erhalten Administratoren Einblicke in Richtlinien und die Behandlung von Bedrohungen (z. B. wo die E-Mail geroutet wurde, und in einigen Fällen, was die endgültige Bewertung war).

> [!IMPORTANT]
> Wechseln Sie hier zu einem [Problembehebungsthema.](remediate-malicious-email-delivered-office-365.md)

## <a name="related-topics"></a>Verwandte Themen

[Behebung bösartiger E-Mails, die in Office 365 zugestellt wurden](remediate-malicious-email-delivered-office-365.md)

[Microsoft Defender für Office 365](office-365-ti.md)

[Schutz vor Bedrohungen in Office 365](protect-against-threats.md)

[Anzeigen von Berichten für Defender für Office 365](view-reports-for-mdo.md)
