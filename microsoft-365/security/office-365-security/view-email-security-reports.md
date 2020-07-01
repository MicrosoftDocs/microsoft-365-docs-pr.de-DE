---
title: Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center
f1.keywords:
- NOCSH
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
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Hier erfahren Sie, wie Sie e-Mail-Sicherheitsberichte für Ihre Organisation suchen und verwenden. E-Mail-Sicherheitsberichte sind im Security & Compliance Center verfügbar.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 226f147dec7795ce6f8314a04218eab84e609218
ms.sourcegitcommit: c43ebb915fa0eb7eb720b21b62c0d1e58e7cde3d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/30/2020
ms.locfileid: "44937049"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center

Im [Security & Compliance Center](https://protection.office.com) stehen eine Vielzahl von Berichten zur Verfügung, um zu sehen, wie e-Mail-Sicherheitsfunktionen wie Antispam-, Antischadsoftware-und Verschlüsselungsfeatures in Microsoft 365 Ihre Organisation schützen. Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im Security & Compliance Center anzeigen, indem Sie **Reports** zum \> **Dashboard**Berichte wechseln. Wenn Sie direkt zum Dashboard Berichte wechseln möchten, öffnen Sie <https://protection.office.com/insightdashboard> .

![Berichts Dashboard im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Bericht über kompromittierte Benutzer

Der Bericht " **kompromittierte Benutzer** " zeigt die Anzahl der Benutzerkonten an, die in den letzten 7 Tagen als **verdächtig** oder **eingeschränkt** gekennzeichnet wurden. Konten in einem dieser Zustände sind problematisch oder sogar gefährdet. Bei häufiger Verwendung können Sie mit dem Bericht Spitzen und sogar Trends in verdächtigen oder eingeschränkten Konten erkennen. Weitere Informationen zu kompromittierten Benutzern finden Sie unter [reagieren auf ein kompromittiertes e-Mail-Konto](responding-to-a-compromised-email-account.md).

In der Ansicht "aggregiert" werden Daten für die letzten 90 Tage angezeigt, und in der Detailansicht werden Daten für die letzten 30 Tage angezeigt.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **kompromittierte Benutzer**aus. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=CompromisedUsers> .

Sie können die Tabelle Diagramm und Details filtern, indem Sie auf **Filter** klicken und mindestens einen der folgenden Werte auswählen:

- **Start Datum** und **Enddatum**

- **Verdächtig**: das Benutzerkonto hat verdächtige e-Mails gesendet, und es besteht das Risiko, dass das Senden von e-Mails eingeschränkt wird.

- **Eingeschränkt**: das Benutzerkonto wurde aufgrund strenger verdächtiger Muster vom Senden von e-Mails eingeschränkt.

![Der Bericht "kompromittierte Benutzer" wird in Microsoft 365](../../media/tp-threatProtectStatRpt-CompromisedUserRpt.png)

Wenn Sie auf **Detailtabelle anzeigen**klicken, werden die folgenden Details angezeigt:

- **Erstellungszeit**
- **Benutzer-ID**
- **Action**

Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.

## <a name="encryption-report"></a>Verschlüsselungs Bericht

Der **Verschlüsselungs Bericht** steht in EoP (Abonnements mit Postfächern in Exchange Online oder eigenständigen EoP ohne Exchange Online Postfächer) zur Verfügung. Das Sicherheitsteam Ihrer Organisation kann Informationen in diesem Bericht verwenden, um Muster zu identifizieren und Richtlinien für vertrauliche e-Mail-Nachrichten proaktiv anzuwenden oder anzupassen. Zum Beispiel:

- Wenn eine große Anzahl von von Benutzern verschlüsselten e-Mail-Nachrichten angezeigt wird, möchten Sie möglicherweise eine Verschlüsselungsrichtlinie zum Automatisieren der Verschlüsselung für bestimmte Anwendungsfälle hinzufügen. Weitere Informationen finden Sie unter [Definieren von Nachrichtenfluss Regeln zum Verschlüsseln von e-Mail-Nachrichten in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).

- Wenn Sie über eine Reihe von Verschlüsselungs Vorlagen verfügen, die von niemandem verwendet werden, können Sie untersuchen, ob Benutzer eine Funktions Schulung benötigen.

Die Aggregatansicht ermöglicht das Filtern für die letzten 90 Tage, während die Detailansicht 10 Tage lang gefiltert werden kann.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Verschlüsselungs Bericht**aus. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=EncryptionReport> .

Weitere Informationen zur Verschlüsselung finden Sie unter [e-Mail-Verschlüsselung in Microsoft 365](../../compliance/email-encryption.md).

### <a name="report-view-for-the-encryption-report"></a>Berichtsansicht für den Verschlüsselungs Bericht

Sie können die folgenden Filter für das Diagramm verwenden:

- **Anzeigen von Daten nach: Nachrichten Verschlüsselungs Bericht** und **Aufschlüsselung nach: Verschlüsselungsmethode**: die folgenden Verschlüsselungsmethoden sind verfügbar:

  - **Verschlüsselung nach Benutzer**
  - **Verschlüsselung nach Richtlinie**

  Wenn Sie auf **Filter**klicken, können Sie das Diagramm mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Verschlüsselungsmethode.
  - Verschlüsselungs Vorlage.

- **Anzeigen von Daten nach: Nachrichten Verschlüsselungs Bericht** und **Aufschlüsselung nach: Verschlüsselungs Vorlage**: die folgenden Verschlüsselungsmethoden sind verfügbar:

  - **Nicht weiterleiten**
  - **Nur verschlüsseln**
  - **Vorheriges OM**
  - **Custom**

  Wenn Sie auf **Filter**klicken, können Sie das Diagramm mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Verschlüsselungsmethode
  - Verschlüsselungs Vorlage

- **Daten nach: Top 5 Recipient Domains**: in dieser Ansicht wird ein Kreisdiagramm mit gesendeten Nachrichten Zählern für die Top 5-Empfängerdomänen angezeigt.

  Wenn Sie auf **Filter**klicken, können Sie ein **Start** -und **Enddatum**auswählen.

### <a name="details-table-view-for-the-encryption-report"></a>Detailtabellen Ansicht für den Verschlüsselungs Bericht

Wenn Sie auf **Detailtabelle anzeigen**klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:

- **Aufschlüsseln nach: Verschlüsselungsmethode** oder **Aufschlüsselung durch: Verschlüsselungs Vorlage**: die folgenden Informationen werden angezeigt:

  - **Date**
  - **Absenderadresse**
  - **Verschlüsselungs Vorlage**
  - **Verschlüsselungsmethode**
  - **Empfängeradresse**
  - **Betreff**

- **Anzeigen von Daten nach: Top 5 Recipient Domains**:

  - **Date**
  - **Empfängerdomäne**
  - **Nachrichtenanzahl**
  
Wenn Sie in einer Detailtabellen Ansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Start Datum** und **Enddatum**
- Verschlüsselungsmethode
- Verschlüsselungs Vorlage

Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.

## <a name="mailflow-status-report"></a>Nachrichtenfluss-Statusbericht

Der e-Mail- **Fluss Statusbericht** enthält Informationen zu Schadsoftware, Spam, Phishing und blockierten Edge-Nachrichten. Weitere Informationen finden Sie unter [Nachrichtenfluss-Statusbericht](view-mail-flow-reports.md#mailflow-status-report).

## <a name="malware-detection-in-email-report"></a>Erkennung von Schadsoftware im e-Mail-Bericht

Der Bericht " **Malwareerkennungen in e-Mail** " zeigt Informationen zu Malwareerkennungen in eingehenden und ausgehenden e-Mail-Nachrichten (Schadsoftware, die durch Exchange Online Schutz oder EoP erkannt wurde). Weitere Informationen zum Schutz vor Schadsoftware in EoP finden Sie unter [Anti-Malware Protection in EoP](anti-malware-protection.md).

 Der Filter "Aggregierte Ansicht" ermöglicht 90 Tage, während der Filter "Details" nur 10 Tage zulässt.

Wenn Sie den Bericht anzeigen möchten, öffnen Sie das [Security & Compliance Center](https://protection.office.com), wechseln Sie zu **Berichte** \> - **Dashboard** , und wählen Sie in e-Mail die Option " **Malware Erkennungen" aus**. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=MalwareDetections> .

![Malware Erkennungen im e-Mail-widget im Dashboard Berichte](../../media/malware-detections-widget.png)

Sie können sowohl das Diagramm als auch die Tabelle Details filtern, indem Sie auf **Filter** klicken und folgende Optionen auswählen:

- **Start Datum** und **Enddatum**
- **Eingehende**
- **Ausgehende**

![Berichtsansicht im Bericht "Malware Erkennung in e-Mail"](../../media/malware-detections-report-view.png)

Wenn Sie auf **Detailtabelle anzeigen**klicken, werden die folgenden Details angezeigt:

- **Date**
- **Absenderadresse**
- **Empfängeradresse**
- **Nachrichten-ID**
- **Betreff**
- **Filename**
- **Name der Schadsoftware**

Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.

## <a name="sent-and-received-email-report"></a>Gesendete und empfangene e-Mail-Berichte

Der Bericht **gesendete und empfangene e-Mails** enthält Informationen zu Schadsoftware, Spam, Nachrichtenfluss Regeln (auch bekannt als Transportregeln) und erweiterte Schadsoftware-Erkennungen, nachdem e-Mail-Dienste in den Dienst eingegangen sind. Weitere Informationen finden Sie unter [gesendete und empfangene e-Mail-Berichte](view-mail-flow-reports.md#sent-and-received-email-report).

## <a name="spam-detections-report"></a>Spamerkennungsbericht

Der **Spam Erkennungs** Bericht zeigt Spam-e-Mails an, die von EoP blockiert wurden. Nachrichten werden einzeln und nicht pro Empfänger gezählt. Wenn beispielsweise die gleiche Spamnachricht an 100 Empfänger in Ihrer Organisation gesendet wurde, zählt sie als eine Nachricht.

Die aggregierte Ansicht ermöglicht eine Filterung von 90 Tagen, während die Detailtabelle 10 Tage Filterung zulässt.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Spam Erkennung**aus. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=SpamDetections> .

![Spam Erkennungs Widget im Dashboard "Berichte"](../../media/spam-detections-widget.png)

Weitere Informationen zum Antispamschutz finden Sie unter [Anti-Spam Protection in EoP](anti-spam-protection.md).

### <a name="report-view-for-the-spam-detections-report"></a>Berichtsansicht für den Spam Erkennungs Bericht

Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:

- **Aufschlüsseln nach: Action**: die folgenden Ereignistypen werden angezeigt:

  - **Gefilterter Spam Inhalt**
  - **Spam-IP-Block**
  - **Spam Umschlag Block**
  - **Spam-Blockierung-Filter**: verzeichnisbasierte Edge-Blockierung (Blockierung)

  Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, können Sie sehen, wie viele Elemente an diesem Tag blockiert wurden, und wie diese Elemente kategorisiert werden.

  ![Aktionsansicht in der Berichtsansicht im Spam Erkennungs Bericht](../../media/spam-detections-report-action-view.png)

- **Aufschlüsseln nach: Direction**: die folgenden Anweisungen werden angezeigt:

  - **Eingehende**
  - **Ausgehende**

Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Start Datum** und **Enddatum**
- Richtungswerte
- Werte des Ereignistyps

### <a name="details-table-view-for-the-spam-detections-report"></a>Detailtabellen Ansicht für den Spam Erkennungs Bericht

Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Absenderadresse**
- **Empfängeradresse**
- **Ereignistyp**
- **Action**
- **Betreff**

Wenn Sie in einer Detailtabelle auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Start Datum** und **Enddatum**
- Richtungswerte
- Werte des Ereignistyps

Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.

## <a name="spoof-detections-report"></a>Spoofing-Erkennungs Bericht

Der Bericht **Spoof-Erkennungen** zeigt, wie viele gefälschte e-Mail-Nachrichten erkannt wurden und von denen, die als "gut" eingestuft wurden (Spoof-e-Mails wurden aus legitimen geschäftlichen Gründen ausgeführt). Weitere Informationen zur Spoofing finden Sie unter [Anti-Spoofing Protection in EoP](anti-spoofing-protection.md).

Die aggregierte Ansicht des Berichts ermöglicht eine Filterung von 90 Tagen, während die Detailansicht nur zehn Tage nach der Filterung zulässt.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Spoof-Erkennungen**aus. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=SpoofMailReport> .

![Widget "Spoof Detections" im Dashboard "Berichte"](../../media/spoof-detections-widget.png)

Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, können Sie sehen, wie viele Spoofing-e-Mail-Nachrichten durchlaufen haben.

Sie können die Tabelle Diagramm und Details filtern, indem Sie auf **Filter** klicken und mindestens einen der folgenden Werte auswählen:

- **Start Datum** und **Enddatum**

- **Gute e-Mail**

- **Als Spam erfasst**

![Berichtsansicht im Bericht "Spoof-Erkennungen"](../../media/spoof-detections-report-view.png)

Wenn Sie auf **Detailtabelle anzeigen**klicken, werden die folgenden Details angezeigt:

- **Date**
- **Gefälschter Absender**
- **Echter Absender**
- **Sender-IP**
- **Action**
- **Nachrichtenanzahl**

Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.

## <a name="threat-protection-status-report"></a>Statusbericht über den Bedrohungsschutz

Der **Statusbericht zum Bedrohungsschutz** ist sowohl in EoP als auch in Office 365 ATP verfügbar; die Berichte enthalten jedoch unterschiedliche Daten. EoP-Kunden können beispielsweise Informationen über in e-Mails erkannte Schadsoftware anzeigen, aber keine Informationen zu [schädlichen Dateien, die in SharePoint Online, OneDrive oder Microsoft Teams erkannt](atp-for-spo-odb-and-teams.md)wurden. Weitere Informationen zu Office 365 ATP-Berichten finden Sie unter [Anzeigen von Berichten für Office 365 Advanced Threat Protection](view-reports-for-atp.md).

Hierbei handelt es sich um einen intelligenten Bericht mit bösartigen e-Mails, die erkannt und blockiert wurden, und ermöglicht es Sicherheitsadministratoren, Trends zu identifizieren oder zu bestimmen, ob Organisationsrichtlinien angepasst werden müssen.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Threat Protection Status**aus. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=ATPV2AggregateReport> .

![Threat Protection-Statusbericht](../../media/0ff86e12-c2b2-4d89-92a5-cefb054dc070.png)

Standardmäßig zeigt das Diagrammdaten für die letzten 7 Tage an. Wenn Sie auf **Filter**klicken, können Sie einen Datumsbereich von 90 Tag auswählen (Testabonnements sind möglicherweise auf 30 Tage eingeschränkt). Die Tabellenansicht Details ermöglicht das Filtern für 30 Tage.

### <a name="report-view-for-the-threat-protection-status-report"></a>Berichtsansicht für den Statusbericht über den Bedrohungsschutz

Die folgenden Ansichten sind verfügbar:

- **Anzeigen von Daten nach: Übersicht**: die folgenden Erkennungsinformationen werden angezeigt:

  - **E-Mail-Schadsoftware**
  - **Phishing per e-Mail**
  - **Inhalts-Schadsoftware**

- **Anzeigen von Daten nach: Inhalt \> Schadsoftware**: die folgenden Informationen werden angezeigt:

  - **Anti-Malware-Modul**
  - **Datei Explosion**

- **Aufschlüsseln nach: Erkennungstechnologie** und **Anzeigen von Daten nach: e-Mail \> Phishing**: die folgenden Informationen werden angezeigt:

  - **Von ATP generierte URL-Reputation**<sup>\*</sup>
  - **Erweiterter Phish-Filter**<sup>\*</sup>
  - **Fälschungsschutz: DMARC-Fehler**
  - **Anti-Spoofing: Intra-org**
  - **Anti-Spoofing: externe Domäne**
  - **Marken Identitätswechsel**<sup>\*</sup>
  - **Domänen Identitätswechsel**<sup>\*</sup>
  - **EoP-URL-Reputation**
  - **Allgemeiner Phish-Filter**
  - **Sonstige**
  - **Phishing-zap**<sup>\*\*</sup>
  - **URL-Detonation**<sup>\*\*</sup>
  - **Benutzeridentitätswechsel**<sup>\*</sup>

- **Aufschlüsseln nach: Erkennungstechnologie** und **Anzeigen von Daten nach: e-Mail- \> Schadsoftware**: die folgenden Informationen werden angezeigt:

  - **Von der ATP generierte dateireputation**<sup>\*\*</sup>
  - **Anti-Malware-Modul**
  - **Anti-Malware-Richtlinien Dateityp-Block**
  - **Datei Explosion**<sup>\*\*</sup>
  - **Böswillige dateireputation**
  - * * Malware zap * * * *<sup>\*\*</sup>
  - **Sonstige**

- **Aufschlüsseln nach: Richtlinientyp** und **Anzeigen von Daten nach: e-Mail- \> Phishing** oder **Anzeigen von Daten nach: e-Mail- \> Schadsoftware**: die folgenden Informationen werden angezeigt:

  - **Anti-Malware**<sup>\*\*</sup>
  - **Sichere Anlage**<sup>\*\*</sup>
  - **Anti-Phishing**
  - **Antispam**
  - **Nachrichtenfluss Regel** (auch als Transportregel bezeichnet)
  - **Sonstige**

- **Aufschlüsseln nach: Zustellungsstatus** und **Anzeigen von Daten nach: e-Mail \> Phishing** oder **Daten anzeigen nach: e-Mail- \> Schadsoftware**: die folgenden Informationen werden angezeigt:

  - **Zustellung fehlgeschlagen**
  - **Gelöscht**
  - **Weitergeleitet**
  - **Gehostetes Postfach: benutzerdefinierter Ordner**
  - **Gehostetes Postfach: Gelöschte Elemente**
  - **Gehostetes Postfach: Posteingang**
  - **Gehostetes Postfach: Junk**
  - **Lokaler Server: zugestellt**
  - **Quarantäne**

<sup>\*</sup>Nur Office 365 ATP

<sup>\*\*</sup>Die automatische Bereinigung ohne Stunden (zap) ist in eigenständigen EoP nicht verfügbar (Sie funktioniert nur in Exchange Online Postfächern).

Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

- **Start Datum** und **Enddatum**
- Erkennungswert
- **Geschützt durch** (nur Office 365 ATP): **ATP** oder **EoP**. Beachten Sie, dass diese filterbare Eigenschaft in **View Data by: Content \> Schadsoftware**nicht verfügbar ist.

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Detailtabellen Ansicht für den Threat Protection-Statusbericht

Wenn Sie auf **Detailtabelle anzeigen**klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:

- **Anzeigen von Daten nach: Inhalt \> Schadsoftware**:

- **Date**
- **Ort**
- **Regie**
- **Name der Schadsoftware**

- **Daten anzeigen nach: Übersicht**: keine **Detailtabellen** -Schaltfläche anzeigen verfügbar.

- Alle anderen Diagramme:

  - **Date**
  - **Betreff**
  - **Sender**
  - **Recipients**
  - **Regie**
  - **Zustellungsstatus**
  - **Kompromiss Quelle**

Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

- **Start Datum** und **Enddatum**
- Erkennungswert
- **Geschützt durch** (nur Office 365 ATP): **ATP** oder **EoP**. Beachten Sie, dass diese filterbare Eigenschaft in **View Data by: Content \> Schadsoftware**nicht verfügbar ist.

## <a name="top-malware-report"></a>Höchst schädlicher Bericht

Der **oberste Schadsoftware** -Bericht zeigt die verschiedenen Arten von Schadsoftware, die von [EoP](eop-features.md)erkannt wurde.

Um den Bericht anzuzeigen, öffnen Sie das [Security & Compliance Center](https://protection.office.com), wechseln Sie zu **Berichte** \> - **Dashboard** , und wählen Sie **oben Malware**aus. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=TopMalwaret> .

![SCC-EoP Top-Schadsoftware](../../media/763330b3-f56e-4ba4-b0bb-051500ae950a.png)

Wenn Sie mit dem Mauszeiger auf einen Keil im Kreisdiagramm zeigen, sehen Sie den Namen einer Art von Schadsoftware und wie viele Nachrichten mit dieser Schadsoftware erkannt wurden.

Klicken (oder tippen) Sie auf den Bericht, um ihn in einem neuen Browserfenster zu öffnen, in dem Sie eine detailliertere Ansicht des Berichts erhalten können.

![Dieser Bericht zeigt die wichtigste für Ihre Organisation erkannte Malware](../../media/3fded224-fb31-4713-86f2-8afce5ce2991.png)

Unter dem Diagramm sehen Sie eine Liste der erkannten Schadsoftware und wie viele Nachrichten mit dieser Schadsoftware erkannt wurden. Beachten Sie, dass die Aggregatansicht nur eine Filterung von 90 Tagen zulässt.

## <a name="url-threat-protection-report"></a>URL-Bedrohungsschutz Bericht

Das Widget für diesen Bericht wird im Dashboard "Berichte" als **URL-Schutzbericht** bezeichnet und ist nur in Office 365 Advanced Threat Protection (ATP) verfügbar. Insbesondere gilt:

- Ein Microsoft 365 E5-Abonnement.
- Ein Advanced Threat Protection-Add-on (Plan 1 *oder* Plan 2) für jedes andere Abonnement, das Exchange Online Protection (EoP) enthält.

Wenn Sie direkt zum **URL Threat Protection** -Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=URLProtectionActionReport> .

> [!NOTE]
> In diesem Bericht werden keine klickdaten von Benutzern angezeigt, bei denen die Richtlinie für sichere Links angewendet die Option **Benutzerklicks nicht nachverfolgen** aktiviert hat.

![Grafik des URL Threat Protection-Berichts in Aktion.](../../media/tp-URLThreatProRpt1.PNG)

### <a name="report-view-for-the-url-threat-protection-report"></a>Berichtsansicht für den URL-Bedrohungsschutz Bericht

Der **URL Threat Protection** -Bericht enthält zwei aggregierte Ansichten, die einmal alle vier Stunden aktualisiert werden, sodass Daten für die letzten 90 Tage angezeigt werden:

- **Aktion zum Schutz vor URLs**: zeigt die Anzahl der URL-Klicks von Benutzern in der Organisation und die Ergebnisse des Klick Vorgangs an:

  - **Gesperrt**
  - **Blockiert und durchgeklickt**
  - **Durch Klicken während der Überprüfung**

  Ein Klick gibt an, dass der Benutzer auf die Seite blockieren zur böswilligen Website geklickt hat (Administratoren können durch Klicken auf Richtlinien für sichere Links deaktivieren).

  Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Die verfügbaren Klick Schutzaktionen sowie den Wert, der zum Anzeigen von Informationen für alle URL-Klicks (nicht nur für blockierte Klicks) **zulässig** ist.

- **URL-Klick nach Anwendung**: zeigt die Anzahl der URL-Klicks von Anwendungen an, die Office 365 ATP-sichere Links unterstützen:

  - **E-Mail-Client**
  - **PowerPoint**
  - **Word**
  - **Excel**
  - **OneNote**
  - **Visio**
  - **Microsoft Teams**
  - **Other**

  Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Start Datum** und **Enddatum**
  - Die verfügbaren Anwendungen.

### <a name="details-table-view-for-the-threat-protection-report"></a>Detailtabellen Ansicht für den Threat Protection-Bericht

Wenn Sie auf **Details-Tabelle anzeigen**klicken, bietet der Bericht eine nahezu Echtzeitansicht aller Klicks, die innerhalb der Organisation für die letzten 7 Tage mit den folgenden Details geschehen:

- **Klicken Sie auf Zeit**
- **Benutzer**
- **URL**
- **Action**
- **App**

Wenn Sie in der Detailtabellen Ansicht auf **Filter** klicken, können Sie nach denselben Kriterien wie in der Berichtsansicht filtern, auch nach **Domänen** oder **Empfängern** , die durch Kommas getrennt sind.

Klicken Sie auf **Bericht anzeigen**, um wieder zur Berichtsansicht zu gelangen.

## <a name="user-reported-messages-report"></a>Bericht über vom Benutzer gemeldete Nachrichten

Der Bericht "vom **Benutzer gemeldete Nachrichten** " zeigt Informationen über e-Mail-Nachrichten an, die von Benutzern mithilfe des [Berichtsnachrichten-Add-ins](https://docs.microsoft.com/microsoft-365/security/office-365-security/enable-the-report-message-add-in)als Junk-oder Phishing-Versuche oder als gute e-Mail gemeldet wurden.

Für jede Nachricht stehen Details zur Verfügung, einschließlich des Zustellungs Grundes, einer solchen Spam Richtlinienausnahme oder Nachrichtenfluss Regel, die für Ihre Organisation konfiguriert ist. Um Details anzuzeigen, wählen Sie ein Element in der Liste Benutzer Berichte aus, und zeigen Sie dann die Informationen auf den Registerkarten **Zusammenfassung** und **Details** an.

![Der Bericht über Benutzer Berichte zeigt Nachrichten an, die als Junk-, nicht als Junk-oder Phishing-Versuche bezeichnet werden.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

Führen Sie einen der folgenden Schritte aus, um diesen Bericht im [Security & Compliance Center](https://protection.office.com)anzuzeigen:

- Wechseln Sie zu **Threat Management** \> **Dashboard** von \> **Benutzern gemeldete Nachrichten**.

- Wechseln Sie zu **Threat Management** \> **überprüfen** von \> **Benutzern gemeldeten Nachrichten**.

![Wählen Sie im Security & Compliance Center die Option Threat Management \> Review \> User gemeldete Nachrichten aus.](../../media/e372c57c-1414-4616-957b-bc933b8c8711.png)

> [!IMPORTANT]
> Damit der Bericht über vom Benutzer gemeldete Nachrichten ordnungsgemäß funktioniert, **muss die Überwachungsprotokollierung** für Ihre Office 365 Umgebung aktiviert sein. Dies erfolgt in der Regel durch eine Person, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Microsoft 365-Überwachungsprotokoll Suche](https://docs.microsoft.com/microsoft-365/compliance/turn-audit-log-search-on-or-off).

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?

Zum Anzeigen und Verwenden der Berichte müssen Sie Mitglied der angegebenen Rollengruppe im Security & Compliance Center **und** in Exchange Online sein.

- Im Security & Compliance Center müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  -Organisationsverwaltung-Sicherheits Administrator (Dies können Sie auch im [Azure Active Directory Admin Center](https://aad.portal.azure.com) – Sicherheits Leser

  Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](https://docs.microsoft.com/microsoft-365/security/office-365-security/permissions-in-the-security-and-compliance-center).

- In Exchange Online müssen Sie Mitglied einer der folgenden Rollengruppen sein:

  -Organisationsverwaltung-nur Ansichts Organisationsverwaltung-nur Empfänger – Compliance-Management

Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo) und [Verwalten von Rollengruppen in Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/role-groups).

## <a name="what-if-the-reports-arent-showing-data"></a>Was geschieht, wenn die Berichte keine Daten anzeigen?

Wenn Sie keine Daten in ihren Berichten sehen, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind. Weitere Informationen finden Sie unter [Protect Against Threats](protect-against-threats.md).

## <a name="related-topics"></a>Verwandte Themen

[Anti-Spam-und Antischadsoftware-Schutz in EoP](anti-spam-and-anti-malware-protection.md)

[Intelligente Berichte und Einblicke im Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)
