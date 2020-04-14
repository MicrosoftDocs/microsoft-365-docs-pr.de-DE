---
title: Threat Explorer und Echt Zeit Erkennungen, neu in Threat Explorer, Änderungen am Threat Explorer, neu in Office 365, Sicherheit, Cloud Security, New to Security in ATP, neue ATP-Features
f1.keywords:
- NOCSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 82ac9922-939c-41be-9c8a-7c75b0a4e27d
ms.collection:
- M365-security-compliance
description: Erfahren Sie mehr über Explorer und Echt Zeit Erkennungen im Security &amp; Compliance Center.
ms.openlocfilehash: c854021eaf6c5d252f36961fde427c5532ba1ef6
ms.sourcegitcommit: 4c6af6530b4997055b8e60bf532e75cbc72fb6c5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/14/2020
ms.locfileid: "43284253"
---
# <a name="threat-explorer-and-real-time-detections"></a>Threat Explorer und Echtzeiterkennung

Wenn Ihre Organisation [Office 365 Advanced Threat Protection](office-365-atp.md) (Office 365 ATP) verfügt und Sie über die [erforderlichen Berechtigungen](#required-licenses-and-permissions)verfügen, haben Sie entweder **Explorer** -oder **Echt Zeit Erkennungen** (früher *Echtzeitberichte* – [Siehe What es New](#new-features-in-threat-explorer-and-real-time-detections)!). Wechseln Sie im Security & Compliance Center zu **Threat Management**, und wählen Sie dann **Explorer** _oder_ **Real-Time Detections**aus.

|||
|---|---|
|**Mit ATP-Plan 2 sehen Sie Folgendes:**|**Mit ATP-Plan 1 sehen Sie Folgendes:**|
|![Bedrohungs-Explorer](../../media/threatmgmt-explorer.png)|![Echtzeiterkennungen](../../media/threatmgmt-realtimedetections.png)|
|

Mit Explorer (oder Echtzeiterkennung) haben Sie einen leistungsfähigen Bericht, der es Ihrem Sicherheitsteam ermöglicht, Bedrohungen effektiv und effizient zu untersuchen und auf diese zu reagieren. Der Bericht ähnelt dem folgenden Bild:

![Wechseln Sie zu Threat \> Management Explorer](../../media/cab32fa2-66f1-4ad5-bc1d-2bac4dbeb48c.png)

Mit diesem Bericht haben Sie folgende Möglichkeiten:

- [Siehe von Office 365 Sicherheitsfeatures erkannte Schadsoftware](#see-malware-detected-in-email-by-technology)
- [Anzeigen von Daten zu Phishing-URLs und klicken auf Urteil](#view-data-about-phishing-urls-and-click-verdict)
- [Starten eines automatisierten unter Such-und Antwort Prozesses aus einer Ansicht im Explorer](#start-automated-investigation-and-response) (nur ATP-Plan 2)
- ... [Untersuchung schädlicher e-Mails und vieles mehr](#more-ways-to-use-explorer-or-real-time-detections)!

## <a name="new-features-in-threat-explorer-and-real-time-detections"></a>Neue Features in Threat Explorer und Echt Zeit Erkennungen

Drei neue Features in Threat Explorer und Echt Zeit Erkennungen hinzugefügt:

- [E-Mail-Kopfzeile anzeigen und e-Mail-Textkörper downloaden](#preview-email-header-and-download-email-body)
- [E-Mail-Zeitachse](#email-timeline)
- [Export-URL klicken Sie auf Daten](#export-url-click-data)

Diese neuen Features werden unten erläutert.

### <a name="preview-email-header-and-download-email-body"></a>E-Mail-Kopfzeile anzeigen und e-Mail-Textkörper downloaden

Die Möglichkeit zum Anzeigen einer e-Mail-Kopfzeile und zum Herunterladen des e-Mail-Texts sind neue Features, die in Threat Explorer verfügbar sind. Administratoren können heruntergeladene Kopfzeilen/e-Mail-Nachrichten auf Bedrohungen analysieren. Da das Herunterladen von e-Mail-Nachrichten die Exposition von Informationen gefährden kann, wird dieser Prozess durch rollenbasierte Zugriffssteuerung (RBAC) gesteuert. Eine neue Rolle, *Vorschau*, muss einer anderen Office 365 Rollengruppe (beispielsweise Sicherheitsvorgänge oder Sicherheits Administrator) hinzugefügt werden, um die Möglichkeit zum Herunterladen von e-Mails und der Vorschau von Kopfzeilen in der Ansicht "All-e-Mail-Nachrichten" zu gewähren.

Durch Explorer (und Echtzeiterkennung) werden jedoch auch neue Felder hinzugefügt, mit denen Sie ein vollständigeres Bild davon erhalten, wo Ihre e-Mail-Nachrichten landen. Ein Teil des Ziels dieser Änderung besteht darin, die Suche für Sicherheitsmitarbeiter einfacher zu machen, aber das Ergebnis ist, dass der Speicherort der Problem-e-Mail-Nachrichten auf einen Blick zu erkennen ist.

Wie wird das gemacht? Der Zustellungs Status wird nun in zwei Spalten aufgeteilt:

- **Zustellungs Aktion** – wie lautet der Status dieser e-Mail?
- **Zustellungs Speicherort** – wohin wurde diese e-Mail weitergeleitet?

Zustellungs Aktion ist die Aktion, die aufgrund vorhandener Richtlinien oder Erkennungen auf eine e-Mail angewendet wird. Hier sind die möglichen Aktionen, die eine e-Mail ausführen kann:

|||||
|---|---|---|---|
|**Geliefert**|**Ausrangierten**|**Gesperrt**|**Ersetzt**|
|E-Mail wurde an den Posteingang des Benutzers oder einen anderen Ordner zugestellt, und der Benutzer kann direkt darauf zugreifen.| E-Mails wurden entweder an den Junk-Ordner des Benutzers oder den Ordner "gelöscht" gesendet, und der Benutzer hat Zugriff auf e-Mail-Nachrichten in diesen Ordnern.| Alle e-Mail-Nachrichten, die isoliert, fehlerhaft oder gelöscht wurden und auf die der Benutzer nicht zugreifen kann.| Alle e-Mail-Nachrichten, bei denen böswillige Anlagen durch txt-Dateien ersetzt wurden, in denen die Anlagen als schädlich eintraten.|
|

Und hier ist, was der Benutzer sehen kann und was er nicht kann:

|||
|---|---|
|**Für Endbenutzer zugänglich**|**Für Endbenutzer unzugänglich**|
|Geliefert|Gesperrt|
|Ausrangierten|Ersetzt|
|

Der Übermittlungsort zeigt die Ergebnisse von Richtlinien und Erkennungen an, die nach der Zustellung ausgeführt werden. Sie ist mit einer Zustellungs Aktion verknüpft. Dieses Feld wurde hinzugefügt, um Einblicke in die Aktion zu geben, die ausgeführt wird, wenn ein Problem mit e-Mails gefunden wird. Im folgenden sind die möglichen Werte für den Zustellungs Speicherort zu finden:

- **Posteingang oder Ordner**: die e-Mail befindet sich im Posteingang oder in einem Ordner (entsprechend Ihren e-Mail-Regeln).
- **On-Prem oder extern**: das Postfach ist nicht in der Cloud vorhanden, sondern lokal.
- **Junk-Ordner**: die e-Mail befindet sich im Ordner Junk eines Benutzers.
- **Ordner "Gelöschte Elemente"**: die e-Mail im Ordner "Gelöschte Elemente" eines Benutzers.
- **Quarantine**: die e-Mail-Nachricht in Quarantäne und befindet sich nicht im Postfach eines Benutzers.
- **Fehler**: die e-Mail konnte das Postfach nicht erreichen.
- **Abgelegt**: die e-Mail wird irgendwo im Nachrichtenfluss verloren.

### <a name="email-timeline"></a>E-Mail-Zeitachse

Die **e-Mail-Zeitachse** ist eine weitere neue Explorer-Funktion, mit der die Jagd Erfahrung für Administratoren verbessert werden soll. Es reduziert die Zufallsgenerierung, da die Überprüfung verschiedener Standorte kürzer ist, um zu versuchen, das Ereignis zu verstehen. Wenn mehrere Ereignisse bei oder nahe gleichzeitig in einer e-Mail auftreten, werden diese Ereignisse in einer Zeitachsenansicht angezeigt. In der Tat werden einige Ereignisse, die nach der Zustellung an Ihre e-Mails geschehen, in der Spalte "spezielle Aktion" erfasst. Durch die Kombination der Informationen aus der Zeitachse dieser e-Mail mit der speziellen Aktion, die Sie für die e-Mail-Zustellung durchführen, erhalten Administratoren einen Einblick in die Funktionsweise Ihrer Richtlinien, wo die e-Mails schließlich weitergeleitet wurden, und in einigen Fällen was die abschließende Bewertung war.

Weitere Informationen zur Untersuchung schädlicher e-Mail-Nachrichten finden Sie unter [untersuchen und Beheben von böswilligen e-Mails, die in Office 365 bereitgestellt wurden](investigate-malicious-email-that-was-delivered.md).

### <a name="export-url-click-data"></a>Export-URL klicken Sie auf Daten

Außerdem können Sie nun Berichte für URL-Klicks in Microsoft Excel exportieren, um sowohl die Netzwerknachrichten-ID als auch das Klick Urteil anzuzeigen, um zu verstehen, wo Ihre URL auf den Datenverkehr fällt. So funktioniert es. Klicken Sie auf der Office 365-Schnellstartleiste in Threat Management auf diese Kette:

**Explorer** \> - **Ansicht Phish** \> **Klicks** \> **Top URLs oder URL Top Klicks** \> **Klicken Sie auf einen beliebigen Datensatz, um das URL-Flyout zu öffnen** .

Wenn Sie auf eine URL in der Liste klicken, wird im Ausklappbereich eine neue Schaltfläche Exportieren angezeigt. Verwenden Sie diese Schaltfläche, um Daten zur einfacheren Berichterstellung in eine Excel-Tabelle zu migrieren.

Sie können den gleichen Speicherort im Bericht über Echt Zeit Erkennungen wie folgt abrufen:

**Explorer** \> - **Echt Zeit Erkennungen** \> **Anzeigen von Phishing** \> - **URLs** \> **Top-URLs oder oberen Klicks** \> **Klicken Sie auf einen beliebigen Datensatz, um das URL-Flyout** \> **zu öffnen, navigieren Sie zur Registerkarte Klicks.**

> [!TIP]
> Network Message ID ordnet den Klick zurück zu bestimmten Mails zu, wenn Sie über den Explorer oder zugeordnete Tools von Drittanbietern über die Netzwerknachrichten-ID suchen. Durch die Suche über die Netzwerknachrichten-ID erhalten Administratoren die spezifische e-Mail-Adresse, die mit einem Klick Ergebnis verknüpft ist. Für eine schnellere und leistungsstärkere Analyse durch den Export mit wird die korrelierte Identifikation der Netzwerknachrichten-ID ermöglicht.

![tp_ExportClickResultAndNetworkID. png](../../media/tp_ExportClickResultAndNetworkID.png)

## <a name="see-malware-detected-in-email-by-technology"></a>Siehe in e-Mail erkannte Malware nach Technologie

Angenommen, Sie möchten die in e-Mail-nach Office 365-Technologie erkannte Malware sehen. Verwenden Sie dazu die [e-Mail->](threat-explorer-views.md#email--malware) Ansicht "Malware" des Explorers (oder Echtzeiterkennung).

1. Wählen Sie im Security & Compliance Center[https://protection.office.com](https://protection.office.com)() **Threat Management** > **Explorer** (oder **Echtzeiterkennung**) aus. (In diesem Beispiel wird der Explorer verwendet.)

2. Wählen Sie im Menü **Ansicht** die Option **e-Mail-** > **Schadsoftware**aus.

   ![Menü "Ansicht" für Explorer](../../media/ExplorerViewEmailMalwareMenu.png)

3. Klicken Sie auf **Absender**, und wählen Sie dann **Basis** > **Erkennungstechnologie**aus.

   Ihre Erkennungstechnologien stehen nun als Filter für den Bericht zur Verfügung.

   ![Technologien zur Erkennung von Malware](../../media/ExplorerEmailMalwareDetectionTech.png)

4. Wählen Sie eine Option aus, und klicken Sie dann auf die Schaltfläche **Aktualisieren** , um diesen Filter anzuwenden.

   ![Ausgewählte Erkennungstechnologie](../../media/ExplorerEmailMalwareDetectionTechATP.png)

Der Bericht wird aktualisiert, um die in e-Mail-Nachweise erkannten Ergebnisse mithilfe der ausgewählten Technologie-Option anzuzeigen. Von hier aus können Sie weitere Analysen durchführen.

## <a name="view-data-about-phishing-urls-and-click-verdict"></a>Anzeigen von Daten zu Phishing-URLs und klicken auf Urteil

Angenommen, Sie möchten Phishing-Versuche über URLs in e-Mails sehen, einschließlich einer Liste von URLs, die zugelassen, blockiert und außer Kraft gesetzt wurden. Zum Identifizieren von URLs, auf die geklickt wurde, müssen [ATP-sichere Links](atp-safe-links.md) konfiguriert werden. Stellen Sie sicher, dass Sie [Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md) zum Zeitpunkt des Klick Schutzes und zur Protokollierung von Klick urteilen durch ATP-sichere Links eingerichtet haben.

Um Phishing-URLs in Nachrichten und Klicks auf URLs in Phishing-Nachrichten zu überprüfen, verwenden Sie die [e-Mail-> Phishing-](threat-explorer-views.md#email--phish) Ansicht des Explorers (oder Echtzeiterkennung).

1. Wählen Sie im Security & Compliance Center[https://protection.office.com](https://protection.office.com)() **Threat Management** > **Explorer** (oder **Echtzeiterkennung**) aus. (In diesem Beispiel wird der Explorer verwendet.)

2. Wählen Sie im Menü **Ansicht** die Option**Phishing** **per e-Mail** > aus.

   ![Menü "Ansicht" für Explorer](../../media/ExplorerViewEmailPhishMenu.png)

3. Klicken Sie auf **Absender**, und wählen Sie dann **URLs** > **Klicken Sie auf Urteil**.

4. Wählen Sie eine oder mehrere Optionen aus, beispielsweise " **blockiert** " und "über **schrieben**", und klicken Sie dann auf die Schaltfläche **Aktualisieren** , die sich in derselben Reihe befindet wie die Optionen zum Anwenden des Filters. (Aktualisieren Sie Ihr Browserfenster nicht.)

   ![URLs und Klick Urteile](../../media/ThreatExplorerEmailPhishClickVerdictOptions.png)

    Der Bericht wird aktualisiert, um zwei unterschiedliche URL-Tabellen auf der Registerkarte URL unter dem Bericht anzuzeigen:

   - **Top-URLs** sind die URLs, die in den Nachrichten enthalten sind, nach denen Sie nach unten gefiltert haben, und die e-Mail-Zustellungs Aktion zählt für jede URL. In der Phishing-e-Mail-Ansicht enthält diese Liste normalerweise legitime URLs. Angreifer enthalten eine Mischung aus guten und ungültigen URLs in ihren Nachrichten, um Sie zu übermitteln, aber Sie machen die bösartigen Links für den Benutzer interessanter, auf Sie zuwerden. Die Tabelle der URLs wird nach der Gesamtzahl der e-Mails sortiert (Beachten Sie jedoch, dass diese Spalte ausgeblendet ist, um die Ansicht zu vereinfachen).

   - Zu den **wichtigsten Klicks** gehören die eingebundenen URLs, auf die geklickt wurde, sortiert nach der Gesamtanzahl der Klick Zähler (diese Spalte wird auch nicht angezeigt, um die Ansicht zu vereinfachen). Gesamtanzahl Zählungen nach Spalte geben Sie die sichere Links klicken Sie auf Urteils Zählung für jede URL, auf die geklickt wurde. In der Phishing-e-Mail-Ansicht sind dies häufiger verdächtige oder böswillige URLs, aber Sie können URLs enthalten, die keine Bedrohungen, sondern Phishing-Nachrichten darstellen. URL Klicks auf unverpackte Links werden hier nicht angezeigt.

   Die zwei URL-Tabellen zeigen die wichtigsten URLs in Phishing-e-Mails nach Zustellungs Aktion und Speicherort an, und Sie zeigen URL-Klicks an, die blockiert wurden (oder trotz einer Warnung besucht wurden), sodass Sie verstehen, welche möglichen fehlerhaften Links von Benutzern empfangen und mit den Benutzern in Interaktion stehen. Von hier aus können Sie weitere Analysen durchführen. Beispielsweise können Sie unter dem Diagramm die häufigsten URLs in e-Mail-Nachrichten sehen, die in der Umgebung Ihrer Organisation blockiert wurden.

   ![Blockierte Explorer-URLs](../../media/ExplorerPhishClickVerdictURLs.png)

   Wählen Sie eine URL aus, um ausführlichere Informationen anzuzeigen.
   
   > [!NOTE]
   > Im Dialogfeld URL-Flyout wird die Filterung für e-Mail-Nachrichten entfernt, um Ihnen die vollständige Ansicht der URL-Exposition in Ihrer Umgebung anzuzeigen. Auf diese Weise können Sie nach e-Mail-Nachrichten im Explorer nach bestimmten URLs suchen, die potenzielle Bedrohungen darstellen, und dann Ihr Verständnis der URL-Exposition in Ihrer Umgebung (über das Dialogfeld URL-Details) erweitern, ohne der Explorer-Ansicht selbst URL-Filter hinzufügen zu müssen.

## <a name="review-email-messages-reported-by-users"></a>Überprüfen von von Benutzern gemeldeten e-Mail-Nachrichten

Angenommen, Sie möchten e-Mail-Nachrichten anzeigen, die Benutzer in Ihrer Organisation als Junk-, kein Junk-oder als Phishing gemeldet haben, indem Sie das [Berichtsnachrichten-Add-in für Outlook und Outlook im Internet](enable-the-report-message-add-in.md)verwenden. Verwenden Sie dazu die Ansicht [e-Mail > Übermittlungen](threat-explorer-views.md#email--submissions) des Explorers (oder Echtzeiterkennung).

1. Wählen Sie im Security & Compliance Center[https://protection.office.com](https://protection.office.com)() **Threat Management** > **Explorer** (oder **Echtzeiterkennung**) aus. (In diesem Beispiel wird der Explorer verwendet.)

2. Wählen Sie im Menü **Ansicht** die Option **e-Mail-** > über**mittlungen**aus. (Dies wurde früher als **Benutzer gemeldet**bezeichnet.)

   ![Menü "Ansicht" für Explorer](../../media/explorer-view-menu-email-user-reported.png)

3. Klicken Sie auf **Absender**, und wählen Sie **Standard** > **Berichtstyp**aus.

4. Wählen Sie eine Option wie **Phishing**aus, und klicken Sie dann auf die Schaltfläche **Aktualisieren** .

   ![Vom Benutzer gemeldetes Phishing](../../media/EmailUserReportedReportType.png)

Der Bericht wird aktualisiert, um Daten über e-Mail-Nachrichten anzuzeigen, die Personen in Ihrer Organisation als Phishing-Versuch gemeldet haben. Sie können diese Informationen verwenden, um weitere Analysen durchzuführen und bei Bedarf Ihre [ATP-Anti-Phishing-Richtlinien](set-up-anti-phishing-policies.md)anzupassen.

## <a name="start-automated-investigation-and-response"></a>Starten der automatischen Untersuchung und Antwort

> [!NOTE]
> In **Office 365 ATP-Plan 2** und **Office 365 E5**stehen automatisierte Ermittlungs-und Antwortfunktionen zur Verfügung.

(Neu!) Durch [Automatische Untersuchung und Antwort](automated-investigation-response-office.md) können Sie Ihr Sicherheits Betriebsteam viel Zeit und Mühe beim untersuchen und verringern von Cyberangriffe speichern. Zusätzlich zum Konfigurieren von Warnungen, die ein Sicherheits Textbuch auslösen können, können Sie einen automatisierten Ermittlungs-und Antwortprozess aus einer Ansicht im Explorer starten.

Ausführliche Informationen hierzu finden Sie unter [Beispiel: ein Sicherheitsadministrator löst eine Untersuchung im Explorer aus](automated-investigation-response-office.md#example-a-security-administrator-triggers-an-investigation-from-threat-explorer).

## <a name="more-ways-to-use-explorer-or-real-time-detections"></a>Weitere Möglichkeiten zum Verwenden von Explorer (oder Echtzeiterkennung)

Zusätzlich zu den in diesem Artikel beschriebenen Szenarien stehen Ihnen viele weitere Berichtsoptionen mit Explorer (oder Echtzeiterkennung) zur Verfügung.

- [Suchen und Untersuchen von bösartigen E-Mails, die zugestellt wurden](investigate-malicious-email-that-was-delivered.md)
- [Anzeigen schädlicher Dateien, die in SharePoint Online, OneDrive und Microsoft Teams erkannt wurden](malicious-files-detected-in-spo-odb-or-teams.md)
- [Erhalten einer Übersicht über die Ansichten in Threat Explorer (und Echtzeiterkennung)](threat-explorer-views.md)

## <a name="required-licenses-and-permissions"></a>Erforderliche Lizenzen und Berechtigungen

Sie benötigen [Office 365 ATP](office-365-atp.md) , um den Explorer oder Echt Zeit Erkennungen zu erhalten.

- Der Explorer ist in Office 365 ATP-Plan 2 enthalten.
- Der Bericht über Echt Zeit Erkennungen ist in Office 365 ATP-Plan 1 enthalten.
- Planen Sie die Zuweisung von Lizenzen für alle Benutzer, die durch Office 365 ATP geschützt werden sollen. (Explorer-oder Echt Zeit Erkennungen zeigen Erkennungsdaten für lizenzierte Benutzer.)

Zum Anzeigen und Verwenden von Explorer-oder Echt Zeit Erkennungen müssen Sie über die entsprechenden Berechtigungen verfügen, beispielsweise solche, die einem Sicherheitsadministrator oder Sicherheits Leser erteilt werden.

- Für das Security &amp; Compliance Center müssen Sie eine der folgenden Rollen zugewiesen haben:

  - Organisationsverwaltung
  - Sicherheits Administrator (Dies kann im Azure Active Directory Admin Center zugewiesen werden ([https://aad.portal.azure.com](https://aad.portal.azure.com)))
  - Sicherheitsleseberechtigter

- Für Exchange Online müssen Sie eine der folgenden Rollen entweder in der Exchange-Verwaltungskonsole ([https://outlook.office365.com/ecp](https://outlook.office365.com/ecp)) oder mit PowerShell-Cmdlets zugewiesen haben (siehe [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell)):

  - Organisationsverwaltung
  - Organisationsverwaltung mit Leserechten
  - Rolle „Empfänger mit Leserechten“
  - Verwaltung der Richtlinientreue

Weitere Informationen zu Rollen und Berechtigungen finden Sie in den folgenden Ressourcen:

- [Berechtigungen im Office 365 Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md)
- [Featureberechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

## <a name="some-differences-between-threat-explorer-and-real-time-detections"></a>Einige Unterschiede zwischen dem Bedrohungs-Explorer und Echt Zeit Erkennungen

- Der Bericht über **Echt Zeit Erkennungen** steht in Office 365 ATP-Plan 1 zur Verfügung, während **Threat Explorer** in Office 365 ATP-Plan 2 zur Verfügung steht.
- Der Bericht über **Echt Zeit Erkennungen** ermöglicht das Anzeigen von Erkennungen in Echtzeit. Dieser Vorgang wird auch von **Threat Explorer** durchgesetzt, aber Sie können auch zusätzliche Details für einen bestimmten Angriff anzeigen.
- Eine **alle e-Mail-** Ansicht ist in **Threat Explorer** verfügbar (und befindet sich nicht im Bericht über **Echt Zeit Erkennungen** ).
- In **Threat Explorer**sind weitere Filterfunktionen und verfügbare Aktionen enthalten.

Weitere Informationen finden Sie unter [Office 365 ATP-Dienstbeschreibung: Verfügbarkeit von Features in Advanced Threat Protection (ATP)-Plänen](https://docs.microsoft.com/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).
