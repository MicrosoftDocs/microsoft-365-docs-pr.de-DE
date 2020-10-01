---
title: Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
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
ms.openlocfilehash: 7e594f758e0fb08b0b8718248466ecbc46903b82
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327009"
---
# <a name="view-email-security-reports-in-the-security--compliance-center"></a>Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Im [Security & Compliance Center](https://protection.office.com) stehen eine Vielzahl von Berichten zur Verfügung, um zu sehen, wie e-Mail-Sicherheitsfunktionen wie Antispam-, Antischadsoftware-und Verschlüsselungsfeatures in Microsoft 365 Ihre Organisation schützen. Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im Security & Compliance Center anzeigen, indem Sie **Reports** zum \> **Dashboard**Berichte wechseln. Wenn Sie direkt zum Dashboard Berichte wechseln möchten, öffnen Sie <https://protection.office.com/insightdashboard> .

![Berichts Dashboard im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="compromised-users-report"></a>Bericht über kompromittierte Benutzer

> [!NOTE]
> Dieser Bericht ist in Microsoft 365-Organisationen mit Exchange Online-Postfächern verfügbar. Es ist nicht in eigenständigen Exchange Online Schutzorganisationen (EoP) verfügbar.

Der Bericht " **kompromittierte Benutzer** " zeigt die Anzahl der Benutzerkonten an, die in den letzten 7 Tagen als **verdächtig** oder **eingeschränkt** gekennzeichnet wurden. Konten in einem dieser Zustände sind problematisch oder sogar gefährdet. Bei häufiger Verwendung können Sie mit dem Bericht Spitzen und sogar Trends in verdächtigen oder eingeschränkten Konten erkennen. Weitere Informationen zu kompromittierten Benutzern finden Sie unter [reagieren auf ein kompromittiertes e-Mail-Konto](responding-to-a-compromised-email-account.md).

![Kompromittierte Benutzer-Widget im Dashboard Berichte](../../media/compromised-users-report-widget.png)

In der Ansicht "aggregiert" werden Daten für die letzten 90 Tage angezeigt, und in der Detailansicht werden Daten für die letzten 30 Tage angezeigt.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **kompromittierte Benutzer**aus. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=CompromisedUsers> .

Sie können die Tabelle Diagramm und Details filtern, indem Sie auf **Filter** klicken und mindestens einen der folgenden Werte auswählen:

- **Start Datum** und **Enddatum**

- **Verdächtig**: das Benutzerkonto hat verdächtige e-Mails gesendet, und es besteht das Risiko, dass das Senden von e-Mails eingeschränkt wird.

- **Eingeschränkt**: das Benutzerkonto wurde aufgrund strenger verdächtiger Muster vom Senden von e-Mails eingeschränkt.

![Berichtsansicht im Bericht "kompromittierte Benutzer"](../../media/compromised-users-report-activity-view.png)

Wenn Sie auf **Detailtabelle anzeigen**klicken, werden die folgenden Details angezeigt:

- **Erstellungszeit**
- **Benutzer-ID**
- **Aktion**

Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.

## <a name="encryption-report"></a>Verschlüsselungs Bericht

Der **Verschlüsselungs Bericht** steht in EoP (Abonnements mit Postfächern in Exchange Online oder eigenständigen EoP ohne Exchange Online Postfächer) zur Verfügung. Das Sicherheitsteam Ihrer Organisation kann Informationen in diesem Bericht verwenden, um Muster zu identifizieren und Richtlinien für vertrauliche e-Mail-Nachrichten proaktiv anzuwenden oder anzupassen. Beispiel:

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

## <a name="malware-detections-in-email-report"></a>Malware Erkennungen im e-Mail-Bericht

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
- **Nachrichten-ID**: verfügbar im Kopfzeilenfeld nach **richten-ID** im Nachrichtenkopf und sollte eindeutig sein. Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (Beachten Sie die spitzen Klammern).
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

![Spam Erkennungs Widget im Dashboard "Berichte"](../../media/spam-detections-report-widget.png)

Weitere Informationen zum Antispamschutz finden Sie unter [Anti-Spam Protection in EoP](anti-spam-protection.md).

### <a name="report-view-for-the-spam-detections-report"></a>Berichtsansicht für den Spam Erkennungs Bericht

Die folgenden Diagramme stehen in der Berichtsansicht zur Verfügung:

- **Aufschlüsseln nach: Action**: die folgenden Ereignistypen werden angezeigt:

  - **Gefilterter Spam Inhalt**
  - **Spam-IP-Block**
  - **Spam Umschlag Block**
  - **Spam-Blockierung-Filter**: verzeichnisbasierte Edge-Blockierung (Blockierung)

  Wenn Sie auf einen Tag (Datenpunkt) im Diagramm zeigen, können Sie sehen, wie viele Elemente an diesem Tag blockiert wurden, und wie diese Elemente kategorisiert werden.

  ![Aktionsansicht im Spam Erkennungs Bericht](../../media/spam-detections-report-action-view.png)

- **Aufschlüsseln nach: Direction**: die folgenden Anweisungen werden angezeigt:

  - **Eingehende**
  - **Ausgehende**

  ![Richtungs Ansicht in im Spam Erkennungs Bericht](../../media/spam-detections-report-direction-view.png)

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
- **Aktion**
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
- **Aktion**
- **Nachrichtenanzahl**

Klicken Sie auf **Bericht anzeigen**, um zur Berichtsansicht zurückzukehren.

## <a name="threat-protection-status-report"></a>Threat Protection-Statusbericht

Der **Statusbericht zum Bedrohungsschutz** ist sowohl in EoP als auch in Office 365 ATP verfügbar; die Berichte enthalten jedoch unterschiedliche Daten. EoP-Kunden können beispielsweise Informationen über in e-Mails erkannte Schadsoftware anzeigen, aber keine Informationen zu [bösartigen Dateien, die von ATP für SharePoint, OneDrive oder Microsoft Teams erkannt](atp-for-spo-odb-and-teams.md)wurden.

Der Bericht enthält die Anzahl von e-Mail-Nachrichten mit bösartigen Inhalten wie Dateien oder Websiteadressen (URLs), die von der Antischadsoftware-Engine, der [automatischen Säuberungs-Funktion (Zero-Hour)](zero-hour-auto-purge.md)und den ATP-Features wie [sichere Links](atp-safe-links.md), [sichere Anlagen](atp-safe-attachments.md)und [ATP-Anti-Phishing](set-up-anti-phishing-policies.md)blockiert wurden. Sie können diese Informationen verwenden, um Trends zu identifizieren oder zu bestimmen, ob Organisationsrichtlinien angepasst werden müssen. Es ist wichtig zu verstehen, dass wenn eine Nachricht an fünf Empfänger gesendet wird, wir Sie als fünf verschiedene Nachrichten und nicht eine Nachricht zählen.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center](https://protection.office.com), wechseln Sie **Reports** zum \> **Dashboard** Berichte, und wählen Sie **Threat Protection Status**aus. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie eine der folgenden URLs:

- Office 365 ATP: <https://protection.office.com/reportv2?id=ATPV2AggregateReport> .
- EoP <https://protection.office.com/reportv2?id=ATPAggregateLightReport>

![Widget "Threat Protection Status" im Dashboard "Berichte"](../../media/threat-protection-status-report-widget.png)

Standardmäßig zeigt das Diagrammdaten für die letzten 7 Tage an. Wenn Sie auf **Filter**klicken, können Sie einen Datumsbereich von 90 Tag auswählen (Testabonnements sind möglicherweise auf 30 Tage eingeschränkt). Die Tabellenansicht Details ermöglicht das Filtern für 30 Tage.

### <a name="report-view-for-the-threat-protection-status-report"></a>Berichtsansicht für den Statusbericht über den Bedrohungsschutz

Die folgenden Ansichten sind verfügbar:

- **Anzeigen von Daten nach: Übersicht**: die folgenden Erkennungsinformationen werden angezeigt:

  - **E-Mail-Schadsoftware**
  - **Phishing per e-Mail**
  - **Inhalts-Schadsoftware**

  ![Übersichtsansicht im Statusbericht über den Bedrohungsschutz](../../media/threat-protection-status-report-overview-view.png)

- **Anzeigen von Daten nach: Inhalt \> Schadsoftware**<sup>1</sup>: die folgenden Informationen werden für Office 365 ATP-Organisationen angezeigt:

  - **Anti-Malware-Modul**
  - **Datei Explosion**

  ![Ansicht "Inhalts-Malware" im Statusbericht "Threat Protection"](../../media/threat-protection-status-report-content-malware-view.png)

- **Aufschlüsseln nach: Erkennungstechnologie** und **Anzeigen von Daten nach: e-Mail \> Phishing**: die folgenden Informationen werden angezeigt:

  - **ATP-generierte URL-Reputation**<sup>1</sup>
  - **Erweiterter Phish-Filter**
  - **Fälschungsschutz: DMARC-Fehler**
  - **Anti-Spoofing: Intra-org**
  - **Anti-Spoofing: externe Domäne**
  - **Marken Identitätswechsel**
  - **Domänen Identitätswechsel**<sup>1</sup>
  - **EoP-URL-Reputation**
  - **Allgemeiner Phish-Filter**
  - **Sonstige**
  - **Phishing-zap**<sup>2</sup>
  - **URL Detonation**<sup>1</sup>
  - **Benutzeridentitätswechsel**<sup>1</sup>

  ![Erkennungstechnologie-Ansicht für Phishing-e-Mails im Statusbericht "Threat Protection"](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Aufschlüsseln nach: Erkennungstechnologie** und **Anzeigen von Daten nach: e-Mail- \> Schadsoftware**: die folgenden Informationen werden angezeigt:

  - **ATP-generierte dateireputation**<sup>1</sup>
  - **Anti-Malware-Modul**<sup>1</sup>
  - **Anti-Malware-Richtlinien Dateityp-Block**
  - **Datei Detonation**<sup>1</sup>
  - **Böswillige dateireputation**
  - **Malware zap**<sup>2</sup>
  - **Sonstige**

  ![Erkennungstechnologie-Ansicht für Malware im Statusbericht "Threat Protection"](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Aufschlüsseln nach: Richtlinientyp** und **Anzeigen von Daten nach: e-Mail- \> Phishing** oder **Anzeigen von Daten nach: e-Mail- \> Schadsoftware**: die folgenden Informationen werden angezeigt:

  - **Anti-Malware**
  - **Sichere Anlage**<sup>1</sup>
  - **Anti-Phishing**
  - **Anti-Spam**
  - **Nachrichtenfluss Regel** (auch als Transportregel bezeichnet)
  - **Sonstige**

  ![Richtlinientyp Ansicht für Phishing-e-Mails im Statusbericht "Threat Protection"](../../media/threat-protection-status-report-phishing-policy-type-view.png)

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

  ![Zustellungsstatus Ansicht für Phishing-e-Mails im Statusbericht "Threat Protection"](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> Office 365 nur ATP

<sup>2</sup> Zero-Hour Auto Purge (zap) ist nicht in eigenständigen EoP verfügbar (funktioniert nur in Exchange Online Postfächern).

Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

- **Start Datum** und **Enddatum**
- **Erkennung**
- **Geschützt von**: **ATP** oder **EoP**
- **Tag**: Filtern nach Tag, um Benutzer oder Gruppen zurückzugeben, für die ein bestimmtes Tag angewendet wurde. Weitere Informationen zu Benutzer Tags finden Sie unter [User Tags](user-tags.md).
- **Domäne**

> [!NOTE]
> **Geschützt von**, **Tag** und **Domäne** sind nur Office 365 ATP. Diese filterbaren Eigenschaften stehen in **View Data by: Content \> Schadsoftware**nicht zur Verfügung.

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Detailtabellen Ansicht für den Threat Protection-Statusbericht

Wenn Sie auf **Detailtabelle anzeigen**klicken, hängt die Anzeige der angezeigten Informationen von dem Diagramm ab, das Sie gesucht haben:

- **Anzeigen von Daten nach: Inhalt \> Schadsoftware**:

  - **Date**
  - **Standort**
  - **Regie**
  - **Name der Schadsoftware**

Wenn Sie in dieser Ansicht auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:

- **Start Datum** und **Enddatum**
- **Erkennung**

**Daten anzeigen nach: Übersicht**: keine **Detailtabellen** -Schaltfläche anzeigen verfügbar.

- Alle anderen Diagramme:

  - **Date**
  - **Betreff**
  - **Sender**
  - **Recipients**
  - **Erkannt von**
  - **Zustellungsstatus**
  - **Kompromiss Quelle**
  - **Tags**

Wenn Sie auf **Filter**klicken, können Sie den Bericht mit den folgenden Filtern ändern:

- **Start Datum** und **Enddatum**
- **Erkennung**
- **Geschützt durch** (nur Office 365 ATP): **ATP** oder **EoP**
- **Tag**: Filtern nach Tag, um Benutzer oder Gruppen zurückzugeben, für die ein bestimmtes Tag angewendet wurde. Weitere Informationen zu Benutzer Tags finden Sie unter [User Tags](user-tags.md).
- **Domäne**
- **Empfänger** (Beachten Sie, dass diese filterbare Eigenschaft nur in der Detailtabellen Ansicht verfügbar ist)

## <a name="top-malware-report"></a>Höchst schädlicher Bericht

Der **oberste Schadsoftware** -Bericht zeigt die verschiedenen Arten von Schadsoftware, die durch den [Schutz vor Schadsoftware in EoP](anti-malware-protection.md)erkannt wurden.

Um den Bericht anzuzeigen, öffnen Sie das [Security & Compliance Center](https://protection.office.com), wechseln Sie zu **Berichte** \> - **Dashboard** , und wählen Sie **oben Malware**aus. Wenn Sie direkt zum Bericht wechseln möchten, öffnen Sie <https://protection.office.com/reportv2?id=TopMalware> .

![Oberes Malware-Widget im Dashboard "Berichte"](../../media/top-malware-report-widget.png)

Wenn Sie mit dem Mauszeiger auf einen Keil im Kreisdiagramm zeigen, sehen Sie den Namen einer Art von Schadsoftware und wie viele Nachrichten mit dieser Schadsoftware erkannt wurden.

![Obere Malware Berichtsansicht](../../media/top-malware-report-view.png)

Wenn Sie auf **Detailtabelle anzeigen**klicken, werden die folgenden Details angezeigt:

- **Top-Schadsoftware**
- **Count**

Wenn Sie in der Ansicht Berichtsansicht oder Detailtabelle auf **Filter** klicken, können Sie einen Datumsbereich mit **anfangs** -und **Enddatum**angeben.

## <a name="url-threat-protection-report"></a>URL-Bedrohungsschutz Bericht

Der **URL Threat Protection-Bericht** steht in Office 365 Advanced Threat Protection (ATP) zur Verfügung. Weitere Informationen finden Sie unter [URL Threat Protection-Bericht](view-reports-for-atp.md#url-threat-protection-report).

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

[Anzeigen von Nachrichtenfluss Berichten im Security & Compliance Center](view-mail-flow-reports.md)

[Anzeigen von Berichten für Office 365 Advanced Threat Protection](view-reports-for-atp.md)
