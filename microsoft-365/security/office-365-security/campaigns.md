---
title: Kampagnenansichten in Microsoft Defender für Office 365 Plan
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: mcostea
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: Erfahren Sie mehr über Kampagnenansichten in Microsoft Defender für Office 365.
ms.openlocfilehash: 8e5c49c9a45d1578da1eea33a560da611fb74155
ms.sourcegitcommit: a76de3d1604d755b29053e7bf557c0008be6ad23
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/08/2021
ms.locfileid: "49788015"
---
# <a name="campaign-views-in-microsoft-defender-for-office-365"></a>Kampagnenansichten in Microsoft Defender für Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Kampagnenansichten sind ein Feature in Microsoft Defender für Office 365 Plan 2 (z. B. Microsoft 365 E5 oder Organisationen mit einem Defender für Office 365 Plan 2-Add-On). Kampagnenansichten im Security & Compliance Center identifizieren und kategorisieren Phishingangriffe im Dienst. Kampagnenansichten können Ihnen bei Folgendem helfen:

- Phishing-Angriffe effektiv untersuchen und darauf reagieren.
- Besseres Verständnis des Umfangs des Angriffs.
- Entscheidungsträgern den Nutzen anzeigen.

Mit Kampagnenansichten können Sie das Gesamtbild eines Angriffs schneller und vollständiger erfassen als jeder Mensch.

## <a name="what-is-a-campaign"></a>Was ist eine Kampagne?

Eine Kampagne ist ein koordinierter E-Mail-Angriff gegen eine oder mehrere Organisationen. E-Mail-Angriffe, die Anmeldeinformationen und Unternehmensdaten stehlen, sind eine große und lu lugige Branche. Wenn Technologien zunehmen, um Angriffe zu stoppen, ändern Angreifer ihre Methoden, um einen weiterhin erfolgreichen Erfolg zu gewährleisten.

Microsoft nutzt die großen Mengen an Antiphishing-, Antispam- und An malware-Daten über den gesamten Dienst, um Kampagnen zu identifizieren. Wir analysieren und klassifizieren die Angriffsinformationen nach verschiedenen Faktoren. Zum Beispiel:

- **Angriffsquelle:** Die Quell-IP-Adressen und E-Mail-Domänen des Absenders.
- **Nachrichteneigenschaften:** Inhalt, Formatvorlage und Tonfall der Nachrichten.
- **Nachrichtenempfänger:** Beziehung zwischen Empfängern. Beispielsweise Empfängerdomänen, Empfängerauftragsfunktionen (Administratoren, Führungskräfte usw.), Unternehmenstypen (groß, klein, öffentlich, privat usw.) und Branchen.
- **Angriffsnutzlast:** Schädliche Links, Anlagen oder andere Nutzlasten in den Nachrichten.

Eine Kampagne kann kurzlebig sein oder mehrere Tage, Wochen oder Monate mit aktiven und inaktiven Zeiträumen umfassen. Möglicherweise wird eine Kampagne für Ihre bestimmte Organisation gestartet, oder Ihre Organisation ist Teil einer größeren Kampagne in mehreren Unternehmen.

## <a name="campaign-views-in-the-security--compliance-center"></a>Kampagnenansichten im Security & Compliance Center

Kampagnenansichten sind im [Security & Compliance Center](https://protection.office.com) bei Threat **Management** \> **Campaigns** oder direkt unter <https://protection.office.com/campaigns> verfügbar.

![Kampagnenübersicht im Security & Compliance Center](../../media/campaigns-overview.png)

Sie können auch kampagnenansichten von:

- **Bedrohungsverwaltung** \> **Explorer** \> **Ansicht** \> **Kampagnen**
- **Bedrohungsverwaltung** \> **Explorer** \> **Ansicht** \> **Alle E-Mails** \> **Registerkarte "Kampagne"**
- **Bedrohungsverwaltung** \> **Explorer** \> **Ansicht** \> **Phishing** \> **Registerkarte "Kampagne"**
- **Bedrohungsverwaltung** \> **Explorer** \> **Ansicht** \> **Schadsoftware** \> **Registerkarte "Kampagne"**

Für den Zugriff auf Kampagnenansichten müssen Sie Mitglied der  Rollengruppe **"Organisationsverwaltung",** **"Sicherheitsadministrator"** oder "Sicherheitsleseprogramm" im Security & Compliance Center sein. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="campaigns-overview"></a>Kampagnenübersicht

Auf der Übersichtsseite werden Informationen zu allen Kampagnen angezeigt.

Auf der Registerkarte **"Kampagnen"** wird im Bereich "Kampagnentyp" ein Balkendiagramm angezeigt, in dem die Anzahl der Empfänger pro Tag angezeigt wird.  Standardmäßig zeigt das Diagramm **Phishing-** und **Schadsoftwaredaten.**

> [!TIP]
> Wenn keine Kampagnendaten angezeigt werden, versuchen Sie, den Datumsbereich oder die Filter zu [ändern.](#filters-and-settings)

Auf der restlichen Übersichtsseite werden die folgenden Informationen auf der Registerkarte **"Kampagne"** angezeigt:

- **Name**

- **Beispiel-Betreff**: Betreffzeile einer der Nachrichten in der Kampagne. Beachten Sie, dass alle Nachrichten in der Kampagne nicht unbedingt denselben Betreff haben.

- **Gezielt:** Der Prozentsatz, wie er berechnet wird durch: (die Anzahl der Kampagnenempfänger in Ihrer Organisation) / (die Gesamtzahl der Empfänger in der Kampagne in allen Organisationen im Dienst). Dieser Wert gibt den Grad an, zu dem die Kampagne nur an Ihre Organisation gerichtet ist (ein höherer Wert) im Vergleich zu anderen Organisationen im Dienst (ein niedrigerer Wert).

- **Typ:** Dieser Wert ist entweder **Phishing oder** **Schadsoftware.**

- **Untertyp:** Dieser Wert enthält weitere Details zur Kampagne. Zum Beispiel:
  - **Phishing:** Sofern verfügbar, die Marke, die von dieser Kampagne ge phishinged wird. Beispiel: `Microsoft` , `365` , , oder `Unknown` `Outlook` `DocuSign` .
  - **Schadsoftware:** z. `HTML/PHISH` B. oder `HTML/<MalwareFamilyName>` .

  Soweit verfügbar, die Marke, die von dieser Kampagne mit Phishing betitelt wird. Wenn die Erkennung durch die Defender für Office 365-Technologie gesteuert wird, wird das Präfix **ATP-** dem Untertypwert hinzugefügt.

- **Empfänger**: Die Anzahl der Benutzer, auf die diese Kampagne abzielt.

- **Posteingang:** Die Anzahl der Benutzer, die Nachrichten von dieser Kampagne in ihrem Posteingang empfangen haben (nicht an den Junk-E-Mail-Ordner zugestellt).

- **Angeklickt:** Die Anzahl der Benutzer, die auf die URL geklickt oder die Anlage in der Phishingnachricht geöffnet haben.

- **Klickrate:** Der Prozentsatz, wie er durch "**Geklickter**  /  **Posteingang" berechnet** wird. Dieser Wert ist ein Indikator für die Effektivität der Kampagne. Anders ausgedrückt, wenn die Empfänger die Nachricht als Phishing identifizieren konnten und nicht auf die Nutzlast-URL geklickt haben.

  Beachten **Sie, dass die** Klickrate nicht in Schadsoftwarekampagnen verwendet wird.

- **Besucht:** Wie viele Benutzer es tatsächlich bis zur Nutzlastwebsite durch gemacht haben. Wenn **"Clicked"-Werte,** aber sichere Links den Zugriff auf die Website blockiert haben, ist dieser Wert null.

Auf **der Registerkarte "Kampagnenherkunft"** werden die Nachrichtenquellen auf einer Karte der Welt angezeigt.

### <a name="filters-and-settings"></a>Filter und Einstellungen

Oben auf der Seite "Kampagnenansichten" gibt es mehrere Filter- und Abfrageeinstellungen, mit deren Hilfe Sie bestimmte Kampagnen finden und isolieren können.

![Kampagnenfilter](../../media/campaign-filters-and-settings.png)

Die grundlegendste Filterung, die Sie verwenden können, sind das Startdatum/die Startzeit und das Enddatum/die Endzeit.

Um die Ansicht weiter zu filtern, können Sie eine  einzelne Eigenschaft mit mehreren Werten filtern, indem Sie auf die Schaltfläche "Kampagnentyp" klicken, Ihre Auswahl treffen und dann auf **Aktualisieren klicken.**

Die filterbaren Kampagneneigenschaften, die  auf der Schaltfläche "Kampagnentyp" verfügbar sind, werden in der folgenden Liste beschrieben:

- **Standard:**
  - **Kampagnentyp:** Wählen **Sie Schadsoftware** oder **Phishing aus.** Das Löschen der Auswahl hat dasselbe Ergebnis wie das Auswählen beider Optionen.
  - **Kampagnenname**
  - **Kampagnenuntertyp**
  - **Sender**
  - **Recipients**
  - **Absenderdomäne**
  - **Betreff**
  - **Dateiname der Anlage**
  - **Schadsoftwarefamilie**
  - **Tags:** Benutzer oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten). Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)
  - **Systemüberschreibungen**
  - **Zustellungsaktion**
  - **Zusätzliche Aktion**
  - **Directionality**
  - **Erkennungstechnologie**
  - **Ursprünglicher Übermittlungsort**
  - **Aktueller Übermittlungsort**
  - **Systemüberschreibungen**

- **Erweitert:**
  - **Internetnachrichten-ID:** Im **Nachrichten-ID-Kopfzeilenfeld** im Nachrichtenkopf verfügbar. Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (beachten Sie die spitzen Klammern).
  - **Netzwerknachrichten-ID:** Ein GUID-Wert, der im Kopfzeilenfeld **"X-MS-Exchange-Organization-Network-Message-Id"** im Nachrichtenkopf verfügbar ist.
  - **Sender-IP**
  - **Anlage SHA256**: Um den #A0 einer Datei in Windows zu finden, führen Sie den folgenden Befehl an einer Eingabeaufforderung aus: `certutil.exe -hashfile "<Path>\<Filename>" SHA256` .
  - **Cluster-ID**
  - **Warnungsrichtlinien-ID**
  - **ZAP-URL-Signal**

- **URLs:**
  - **URL-Domäne**
  - **URL-Domäne und -Pfad**
  - **URL**
  - **Pfad der URL**
  - **Click verdict**

Für eine erweiterte Filterung, einschließlich der Filterung nach mehreren Eigenschaften, können Sie auf die Schaltfläche **"Erweiterter Filter"** klicken, um eine Abfrage zu erstellen. Es stehen dieselben Kampagneneigenschaften zur Verfügung, jedoch mit den folgenden Verbesserungen:

- Sie können auf "Bedingung **hinzufügen" klicken,** um mehrere Bedingungen auszuwählen.
- Sie können den **Operator "And"** oder **"Or"** zwischen Bedingungen auswählen.
- Sie können das **Bedingungsgruppenelement** am unteren Rand der Bedingungsliste auswählen, um komplexe Verbundbedingungen zu bilden.

Wenn Sie fertig sind, klicken Sie auf die Schaltfläche **"Abfrage".**

Nachdem Sie einen einfachen oder erweiterten Filter erstellt haben, können Sie ihn mithilfe der Abfrage **"Speichern"** oder **"Speichern unter" speichern.** Wenn Sie später zu Kampagnenansichten zurückkehren, können Sie einen gespeicherten Filter laden, indem Sie auf **"Gespeicherte Abfrageeinstellungen" klicken.**

Klicken Sie auf "Diagrammdaten exportieren"  oder "Kampagnenliste exportieren", und wählen Sie **"Diagrammdaten** exportieren" oder **"Kampagnenliste exportieren"** aus, um das Diagramm oder die Liste der Kampagnen zu exportieren.

Wenn Sie über ein Microsoft Defender for Endpoint-Abonnement verfügen, können Sie auf die **MDE-Einstellungen** klicken, um die Kampagneninformationen mit Microsoft Defender for Endpoint zu verbinden oder zu trennen. Weitere Informationen finden Sie unter [Integrieren von Microsoft Defender für Office 365 in Microsoft Defender for Endpoint](integrate-office-365-ti-with-wdatp.md).

## <a name="campaign-details"></a>Kampagnendetails

Wenn Sie auf den Namen einer Kampagne klicken, werden die Kampagnendetails in einem Flyout angezeigt.

### <a name="campaign-information"></a>Kampagneninformationen

Oben in der Ansicht "Kampagnendetails" sind die folgenden Kampagneninformationen verfügbar:

- **ID:** Die eindeutige Kampagnen-ID.

- **Gestartet** und **beendet:** Das Start- und Enddatum der Kampagne. Beachten Sie, dass diese Datumsangaben möglicherweise über die Filterdaten hinaus gehen, die Sie auf der Übersichtsseite ausgewählt haben.

- **Auswirkung:** Dieser Abschnitt enthält die folgenden Daten für den ausgewählten Datumsbereichsfilter (oder den Sie auf der Zeitachse auswählen):
  - Die Gesamtzahl der Empfänger.
  - Die Anzahl der Nachrichten, die "Posteingang" waren (d. h. an den Posteingang übermittelt, nicht an den Junk-E-Mail-Ordner).
  - Wie viele Benutzer in der Phishingnachricht auf die URL-Nutzlast geklickt haben.
  - Howe many users visited the URL.

- **Gezielt:** Der Prozentsatz, wie er berechnet wird durch: (die Anzahl der Kampagnenempfänger in Ihrer Organisation) / (die Gesamtzahl der Empfänger in der Kampagne in allen Organisationen im Dienst). Beachten Sie, dass dieser Wert über die gesamte Lebensdauer der Kampagne berechnet wird und sich nicht basierend auf Datumsfiltern ändert.

- Eine interaktive Zeitachse der Kampagnenaktivität: Auf der Zeitachse werden Aktivitäten über die gesamte Lebensdauer der Kampagne angezeigt. Standardmäßig enthält der schattierte Bereich den Datumsbereichsfilter, den Sie in der Übersicht ausgewählt haben. Sie können klicken und ziehen, um einen bestimmten Start- und Endpunkt auszuwählen, wodurch sich die daten ändern, die im Auswirkungsbereich und auf der restlichen Seite angezeigt <u>werden,  </u>wie in den nächsten Abschnitten beschrieben.

In der Titelleiste können  Sie auf das Aufschreiben der Schaltfläche "Kampagne herunterladen" klicken, um die Kampagnendetails in ein Dokument in Word herunterzuladen (standardmäßig mit dem Namen ![ ](../../media/download-campaign-write-up-button.png) CampaignReport.docx). Beachten Sie, dass der Download Details über die gesamte Lebensdauer der Kampagne enthält (nicht nur die ausgewählten Filterdaten).

![Kampagneninformationen](../../media/campaign-details-campaign-info.png)

### <a name="campaign-flow"></a>Kampagnenfluss

In der Mitte der Ansicht "Kampagnendetails" werden wichtige Details zur Kampagne im Abschnitt **"Flow"** in einem horizontalen Flussdiagramm (auch als _Sankey-Diagramm_ bekannt) angezeigt. Diese Details helfen Ihnen, die Elemente der Kampagne und die potenziellen Auswirkungen in Ihrer Organisation zu verstehen.

> [!TIP]
> Die im Flussdiagramm angezeigten  Informationen werden durch den schattierten Datumsbereich auf der Zeitachse gesteuert, wie im vorherigen Abschnitt beschrieben.

![Kampagnendetails, die keine Benutzer-URL-Klicks enthalten](../../media/campaign-details-no-recipient-actions.png)

Wenn Sie im Diagramm auf ein horizontales Band zeigen, sehen Sie die Anzahl der verwandten Nachrichten (z. B. Nachrichten aus einer bestimmten Quell-IP, Nachrichten aus der Quell-IP-Adresse, die die angegebene Absenderdomäne verwenden, usw.).

Das Diagramm enthält die folgenden Informationen:

- **Sender-IPs**
- **Absenderdomänen**
- **Filterverkündungen:** Die Werte der Bewertung stehen im Zusammenhang mit den verfügbaren Phishing- und Spamfilterungsverkündungen, wie in den Kopfzeilen von [Antispamnachrichten beschrieben.](anti-spam-message-headers.md) Die verfügbaren Werte werden in der folgenden Tabelle beschrieben:

  ****

  |Wert|Spamfilter-|Beschreibung|
  |---|---|---|
  |**Zulässig**|`SFV:SKN` <p> `SFV:SKI`|Die Nachricht wurde als keine Spam- und/oder übersprungene Filterung markiert, bevor sie von der Spamfilterung ausgewertet wurde. Beispielsweise wurde die Nachricht von einer Nachrichtenflussregel (auch als Transportregel bezeichnet) als kein Spam gekennzeichnet. <p> Die Nachricht hat die Spamfilterung aus anderen Gründen übersprungen. Beispielsweise werden Absender und Empfänger in derselben Organisation angezeigt.|
  |**Gesperrt**|`SFV:SKS`|Die Nachricht wurde als Spam markiert, bevor sie von der Spamfilterung ausgewertet wurde. Beispielsweise durch eine Nachrichtenflussregel.|
  |**Erkannt**|`SFV:SPM`|Die Nachricht wurde vom Spamfilter als Spam markiert.|
  |**Nicht erkannt**|`SFV:NSPM`|Die Nachricht wurde von der Spamfilterung als kein Spam gekennzeichnet.|
  |**Veröffentlicht**|`SFV:SKQ`|Die Nachricht hat die Spamfilterung übersprungen, da sie aus der Quarantäne entfernt wurde.|
  |**Mandanten zulassen**<sup>\*</sup>|`SFV:SKA`|Die Nachricht hat die Spamfilterung aufgrund der Einstellungen in einer Antispamrichtlinie übersprungen. Der Absender war beispielsweise in der Liste der zulässigen Absender oder der zulässigen Domänen aufgeführt.|
  |**Mandantenblock**<sup>\*\*</sup>|`SFV:SKA`|Die Nachricht wurde aufgrund der Einstellungen in einer Antispamrichtlinie durch die Spamfilterung blockiert. Der Absender war beispielsweise in der Liste der zulässigen Absender oder der zulässigen Domänen aufgeführt.|
  |**Benutzer zulassen**<sup>\*</sup>|`SFV:SFE`|Die Nachricht hat die Spamfilterung übersprungen, da der Absender in der Liste sicherer Absender eines Benutzers enthalten war.|
  |**Benutzerblockierung**<sup>\*\*</sup>|`SFV:BLK`|Die Nachricht wurde durch die Spamfilterung blockiert, da der Absender in der Liste blockierter Absender eines Benutzers enthalten war.|
  |**ZAP**|n/v|[Zap (Zero-Hour Auto Purge)](zero-hour-auto-purge.md) hat die zugestellte Nachricht in den Junk-E-Mail-Ordner oder die Quarantäne verschoben. Sie konfigurieren die Aktion in Ihrer Antispamrichtlinie.|
  |

  <sup>\*</sup> Überprüfen Sie Ihre Antispamrichtlinien, da die zulässige Nachricht wahrscheinlich vom Dienst blockiert worden wäre.

  <sup>\*\*</sup> Überprüfen Sie Ihre Antispamrichtlinien, da diese Nachrichten isoliert und nicht zugestellt werden sollten.

- **Zustellungsorte:** Wahrscheinlich möchten Sie Nachrichten untersuchen, die an Empfänger übermittelt wurden (entweder an den Posteingang oder den Junk-E-Mail-Ordner), auch wenn Benutzer nicht auf die Nutzlast-URL in der Nachricht geklickt haben. Sie können die isolierten Nachrichten auch aus der Quarantäne entfernen. Weitere Informationen finden Sie unter ["Isolierte E-Mail-Nachrichten" in EOP.](quarantine-email-messages.md)
  - **Ordner gelöscht**
  - **Dropped**
  - **Extern:** Der Empfänger befindet sich in Ihrer lokalen E-Mail-Organisation in Hybridumgebungen.
  - **Fehlgeschlagen**
  - **Weitergeleitet**
  - **Posteingang**
  - **Junk-E-Mail-Ordner**
  - **Quarantäne**
  - **Unknown**

- **URL-Klicks:** Diese Werte werden im nächsten Abschnitt beschrieben.

> [!NOTE]
> In allen Ebenen, die mehr als 10 Elemente enthalten, werden die 10 obersten Elemente angezeigt, während der Rest in **"Andere"** gebündelt ist.

#### <a name="url-clicks"></a>URL-Klicks

Wenn eine Phishingnachricht an den Posteingang oder junk-E-Mail-Ordner eines Empfängers zugestellt wird, besteht immer die Möglichkeit, dass der Benutzer auf die Nutzlast-URL klickt. Das Nichtklicken auf die URL ist ein kleiner Erfolg, aber Sie müssen ermitteln, warum die Phishingnachricht überhaupt an das Postfach zugestellt wurde.

Wenn ein Benutzer in der Phishingnachricht auf die Nutzlast-URL geklickt hat, werden die Aktionen im **Bereich "URL klickt"** des Diagramms in der Ansicht "Kampagnendetails" angezeigt.

- **Zulässig**
- **BlockPage:** Der Empfänger hat auf die Nutzlast-URL geklickt, [](atp-safe-links.md) aber der Zugriff auf die schädliche Website wurde durch eine Richtlinie für sichere Links in Ihrer Organisation blockiert.
- **BlockPageOverride:** Der Empfänger hat auf die Nutzlast-URL in der Nachricht geklickt, sichere Links haben versucht, sie zu beenden, aber sie konnten den Block außer Kraft setzen. Überprüfen Sie Ihre [Richtlinien für sichere](set-up-atp-safe-links-policies.md) Links, um zu sehen, warum Benutzer die Prüfung auf sichere Links außer Kraft setzen und mit der schädlichen Website fortfahren dürfen.
- **PendingDetonationPage**: Safe Attachments in Microsoft Defender for Office 365 is in the process of opening and investigating the payload URL in a virtual computer environment.
- **PendingDetonationPageOverride:** Der Empfänger konnte den Nutzlastdetonationsprozess außer Kraft setzen und die URL öffnen, ohne auf die Ergebnisse zu warten.

### <a name="tabs"></a>Registerkarten

Mit den Registerkarten in der Ansicht "Kampagnendetails" können Sie die Kampagne weiter untersuchen.

> [!TIP]
> Die informationen, die auf den Registerkarten angezeigt werden, werden durch den schattierten Datumsbereich auf der Zeitachse gesteuert, wie im Abschnitt ["Kampagneninformationen"](#campaign-information) beschrieben.

- **URL-Klicks:** Wenn Benutzer nicht auf die Nutzlast-URL in der Nachricht geklickt haben, ist dieser Abschnitt leer. Wenn ein Benutzer auf die URL klicken konnte, werden die folgenden Werte aufgefüllt:
  - **Benutzer**<sup>\*</sup>
  - **URL**<sup>\*</sup>
  - **Klickzeit**
  - **Click verdict**

- **Sender-IPs**
  - **Sender-IP**<sup>\*</sup>
  - **Gesamtanzahl**
  - **Posteingang**
  - **Nicht im Posteingang**
  - **SPF übergeben:** Der Absender wurde vom [Sender Policy Framework (SPF) authentifiziert.](how-office-365-uses-spf-to-prevent-spoofing.md) Ein Absender, der die SPF-Überprüfung nicht besteht, weist auf einen nicht authentifizierten Absender hin, oder die Nachricht fälscht einen legitimen Absender.

- **Absender**
  - **Absender:** Dies ist die tatsächliche Absenderadresse im SMTP MAIL FROM-Befehl, bei der es sich nicht unbedingt um die Absender-E-Mail-Adresse handelt, die Benutzern in ihren E-Mail-Clients angezeigt wird.
  - **Gesamtanzahl**
  - **Posteingang**
  - **Nicht im Posteingang**
  - **DKIM übergeben:** Der Absender wurde von [DkIM (Domain Keys Identified Mail) authentifiziert.](support-for-validation-of-dkim-signed-messages.md) Ein Absender, der die ÜBERPRÜFUNG von DKIM nicht besteht, weist auf einen nicht authentifizierten Absender hin, oder die Nachricht fälscht einen legitimen Absender.
  - **DMARC übergeben:** Der Absender wurde von domänenbasierter Nachrichtenauthentifizierung, Berichterstellung und Konformität [(DMARC) authentifiziert.](use-dmarc-to-validate-email.md) Ein Absender, der die DMARC-Überprüfung nicht besteht, weist auf einen nicht authentifizierten Absender hin, oder die Nachricht fälscht einen legitimen Absender an.

- **Anlagen**
  - **Filename**
  - **SHA256**
  - **Schadsoftwarefamilie**
  - **Gesamtanzahl**

- **URL**
  - **URL**<sup>\*</sup>
  - **Gesamtanzahl**

<sup>\*</sup> Wenn Sie auf diesen Wert klicken, wird ein neues Flyout geöffnet, das weitere Details zu dem angegebenen Element (Benutzer, URL usw.) oben in der Ansicht "Kampagnendetails" enthält. Wenn Sie zur Ansicht "Kampagnendetails" zurückkehren möchten, klicken Sie im neuen Flyout auf **Fertig**.

### <a name="buttons"></a>Schaltflächen

Mit den Schaltflächen in der Ansicht "Kampagnendetails" können Sie die Funktionen von Threat Explorer verwenden, um die Kampagne weiter zu untersuchen.

- **Kampagne durchsuchen**: Öffnet eine neue Threat Explorer-Suchregisterkarte mit dem Wert **Kampagnen-ID** als Suchfilter.
- **Nachrichten im Posteingang erkunden:** Öffnet eine neue Suchregisterkarte des Bedrohungs-Explorers unter Verwendung der Kampagnen-ID und des Zustellungsspeicherorts: Posteingang als Suchfilter.  
