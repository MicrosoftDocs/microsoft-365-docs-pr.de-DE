---
title: Anzeigen von E-Mail-Sicherheitsberichten im Microsoft 365 Defender-Portal
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 3a137e28-1174-42d5-99af-f18868b43e86
ms.collection:
- M365-security-compliance
description: Erfahren Sie, wie Sie E-Mail-Sicherheitsberichte für Ihre Organisation finden und verwenden. E-Mail-Sicherheitsberichte sind im Microsoft 365 Defender-Portal verfügbar.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: bb7570722fcc957ca86d68f6b42ef254578d7bd7
ms.sourcegitcommit: 3d30ec03628870a22c54b6ec5d865cbe94f34245
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/14/2021
ms.locfileid: "52930321"
---
# <a name="view-email-security-reports-in-the-microsoft-365-defender-portal"></a>Anzeigen von E-Mail-Sicherheitsberichten im Microsoft 365 Defender-Portal

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Im [Microsoft 365 Defender-Portal](https://security.microsoft.com) stehen eine Vielzahl von Berichten zur Verfügung, mit denen Sie sehen können, wie E-Mail-Sicherheitsfeatures wie Antispam, Antischadsoftware und Verschlüsselungsfunktionen in Microsoft 365 Ihre Organisation schützen. Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im Microsoft 365 Defender-Portal anzeigen, indem Sie zu  \> **E-Mail-Berichte &** \> **Zusammenarbeit E-Mail & Zusammenarbeitsberichte wechseln.** Um direkt zum Berichtsdashboard zu wechseln, öffnen Sie <https://security.microsoft.com/emailandcollabreport> .

![Berichtsdashboard im Microsoft 365 Defender-Portal](../../media/email-collaboration-reports.png)

## <a name="compromised-users-report"></a>Bericht "Kompromittierte Benutzer"

> [!NOTE]
> Dieser Bericht ist in Microsoft 365 Organisationen mit Exchange Online Postfächern verfügbar. Es ist in eigenständigen Exchange Online Protection (EOP)-Organisationen nicht verfügbar.

Der Bericht **"Kompromittierte Benutzer"** zeigt die Anzahl der Benutzerkonten an, die innerhalb der letzten 7 Tage als **verdächtig** oder **eingeschränkt** markiert wurden. Konten in einem dieser Zustände sind problematisch oder sogar kompromittiert. Bei häufiger Verwendung können Sie den Bericht verwenden, um Spitzen und sogar Trends in verdächtigen oder eingeschränkten Konten zu erkennen. Weitere Informationen zu kompromittierten Benutzern finden Sie unter [Antworten auf ein kompromittiertes E-Mail-Konto.](responding-to-a-compromised-email-account.md)

![Widget "Kompromittierte Benutzer" im Dashboard "Berichte"](../../media/compromised-users-report-widget.png)

In der Aggregatansicht werden Daten für die letzten 90 Tage und in der Detailansicht Daten für die letzten 30 Tage angezeigt.

Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **"E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte",** und klicken Sie unter **"Kompromittierte Benutzer"** auf **"Details anzeigen".** Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/CompromisedUsers> .

Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **Filter** klicken und einen oder mehrere der folgenden Werte auswählen:

- **Startdatum** und **Enddatum**

- **Verdächtig:** Das Benutzerkonto hat verdächtige E-Mails gesendet und besteht das Risiko, dass das Senden von E-Mails eingeschränkt wird.

- **Eingeschränkt:** Das Benutzerkonto wurde aufgrund von hochgradig verdächtigen Mustern am Senden von E-Mails gehindert.

![Berichtsansicht im Bericht "Kompromittierte Benutzer"](../../media/compromised-users-report-activity-view.png)

Wenn Sie auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Details angezeigt:

- **Erstellungszeitpunkt**
- **Benutzer-ID**
- **Action**

Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.

## <a name="encryption-report"></a>Verschlüsselungsbericht

Der **Verschlüsselungsbericht** ist in EOP verfügbar (Abonnements mit Postfächern in Exchange Online oder eigenständiger EOP ohne Exchange Online Postfächer). Das Sicherheitsteam Ihrer Organisation kann die Informationen in diesem Bericht verwenden, um Muster zu identifizieren und Richtlinien für vertrauliche E-Mail-Nachrichten proaktiv anzuwenden oder anzupassen. Beispiel:

- Wenn eine hohe Anzahl von E-Mail-Nachrichten von Benutzern verschlüsselt wird, möchten Sie möglicherweise eine Verschlüsselungsrichtlinie hinzufügen, um die Verschlüsselung für bestimmte Anwendungsfälle zu automatisieren. Weitere Informationen finden Sie unter [Definieren von Nachrichtenflussregeln zum Verschlüsseln von E-Mail-Nachrichten in Microsoft 365](../../compliance/define-mail-flow-rules-to-encrypt-email.md).

- Wenn Sie über eine Reihe von Verschlüsselungsvorlagen verfügen, die jedoch nicht verwendet werden, können Sie untersuchen, ob Benutzer eine Featureschulung benötigen.

Die Aggregatansicht ermöglicht das Filtern für die letzten 90 Tage, während die Detailansicht das Filtern für 10 Tage zulässt.

Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **"E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte",** und klicken Sie auf **"Details anzeigen"** unter **"Verschlüsselungsbericht".** Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=EncryptionReport> .

Weitere Informationen zur Verschlüsselung finden Sie unter [E-Mail-Verschlüsselung in Microsoft 365](../../compliance/email-encryption.md).

### <a name="report-view-for-the-encryption-report"></a>Berichtsansicht für den Verschlüsselungsbericht

Sie können die folgenden Filter für das Diagramm verwenden:

- **Anzeigen von Daten nach: Nachrichtenverschlüsselungsbericht** und **Aufschlüsselung nach: Verschlüsselungsmethode:** Die folgenden Verschlüsselungsmethoden sind verfügbar:

  - **Verschlüsselung nach Benutzer**
  - **Verschlüsselung nach Richtlinie**

  Wenn Sie auf **"Filter"** klicken, können Sie das Diagramm mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - Verschlüsselungsmethode.
  - Verschlüsselungsvorlage.

- **Anzeigen von Daten nach: Nachrichtenverschlüsselungsbericht** und **Aufschlüsselung nach: Verschlüsselungsvorlage:** Die folgenden Verschlüsselungsmethoden sind verfügbar:

  - **Nicht weiterleiten**
  - **Nur verschlüsseln**
  - **Vorheriges OME**
  - **Custom**

  Wenn Sie auf **"Filter"** klicken, können Sie das Diagramm mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - Verschlüsselungsmethode
  - Verschlüsselungsvorlage

- **Anzeigen von Daten nach: Top 5 recipient domains:** This view shows a pie chart with sent message counts for the top 5 recipient domains.

  Wenn Sie auf **Filter** klicken, können Sie ein **Start-** und **Enddatum** auswählen.

### <a name="details-table-view-for-the-encryption-report"></a>Detailtabellenansicht für den Verschlüsselungsbericht

Wenn Sie auf **"Detailtabelle anzeigen"** klicken, hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich ansehen:

- **Unterschlüsselung nach: Verschlüsselungsmethode** oder **Aufschlüsselung nach: Verschlüsselungsvorlage:** Die folgenden Informationen werden angezeigt:

  - **Date**
  - **Absenderadresse**
  - **Verschlüsselungsvorlage**
  - **Verschlüsselungsmethode**
  - **Empfängeradresse**
  - **Betreff**

- **Anzeigen von Daten nach: Top 5 Empfängerdomänen:**

  - **Date**
  - **Empfängerdomäne**
  - **Nachrichtenanzahl**

Wenn Sie in einer Detailtabellenansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Verschlüsselungsmethode
- Verschlüsselungsvorlage

Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.

## <a name="mailflow-status-report"></a>E-Mailflow-Statusbericht

Der **E-Mailflow-Statusbericht** enthält Informationen zu Schadsoftware, Spam, Phishing und blockierten Edgenachrichten. Weitere Informationen finden Sie im [Mailflow-Statusbericht.](view-mail-flow-reports.md#mailflow-status-report)

## <a name="malware-detections-in-email-report"></a>Schadsoftwareerkennungen im E-Mail-Bericht

Der Bericht über **Schadsoftwareerkennungen in E-Mails** enthält Informationen zu Schadsoftwareerkennungen in eingehenden und ausgehenden E-Mail-Nachrichten (von Exchange Online Protection oder EOP erkannte Schadsoftware). Weitere Informationen zum Schutz vor Schadsoftware in EOP finden Sie unter [Antischadsoftwareschutz in EOP.](anti-malware-protection.md)

 Der Aggregatansichtsfilter lässt 90 Tage zu, während der Detailtabellenfilter nur 10 Tage zulässt.

To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** Email \> **& collaboration** Email & collaboration \> **reports** and click **View details** under **Malware detected in email**. Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/MalwareDetections> .

![Schadsoftwareerkennungen im E-Mail-Widget im Berichtsdashboard](../../media/malware-detections-widget.png)

Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **"Filter"** klicken und Folgendes auswählen:

- **Startdatum** und **Enddatum**
- **Eingehende**
- **Ausgehende**

![Berichtsansicht im Bericht "Schadsoftwareerkennung in E-Mail"](../../media/malware-detections-report-view.png)

Wenn Sie auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Details angezeigt:

- **Date**
- **Absenderadresse**
- **Empfängeradresse**
- **Nachrichten-ID:** Verfügbar im **Nachrichten-ID-Kopfzeilenfeld** im Nachrichtenkopf und sollte eindeutig sein. Ein Beispielwert ist `<08f1e0f6806a47b4ac103961109ae6ef@server.domain>` (beachten Sie die spitzen Klammern).
- **Betreff**
- **Filename**
- **Name der Schadsoftware**

Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.

## <a name="mail-latency-report"></a>E-Mail-Latenzbericht

Der **E-Mail-Latenzbericht** enthält Informationen zur E-Mail-Zustellungs- und Detonationslatenz in Ihrer Organisation. Weitere Informationen finden Sie im [E-Mail-Latenzbericht.](view-reports-for-mdo.md#mail-latency-report)

## <a name="sent-and-received-email-report"></a>Gesendeter und empfangener E-Mail-Bericht

Der Bericht **"Gesendete und empfangene E-Mails"** enthält Informationen zu Schadsoftware, Spam, Nachrichtenflussregeln (auch als Transportregeln bezeichnet) und erweiterte Schadsoftwareerkennungen, nachdem E-Mails in den Dienst gelangt sind. Weitere Informationen finden Sie unter ["Gesendete und empfangene E-Mail-Berichte".](view-mail-flow-reports.md#sent-and-received-email-report)

## <a name="spam-detections-report"></a>Spamerkennungsbericht

Der **Spamerkennungsbericht** zeigt Spam-E-Mail-Nachrichten an, die von EOP blockiert wurden. Nachrichten werden einzeln gezählt, nicht pro Empfänger. Wenn die gleiche Spamnachricht beispielsweise an 100 Empfänger in Ihrer Organisation gesendet wurde, zählt sie als eine Nachricht.

Die Aggregatansicht ermöglicht das Filtern von 90 Tagen, während die Detailtabelle das Filtern von 10 Tagen zulässt.

To view the report, open the [Microsoft 365 Defender portal](https://security.microsoft.com), go to **Reports** Email \> **& collaboration** Email & collaboration \> **reports** and click **View details** under Spam **detections**. Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/SpamDetections> .

![Spamerkennungs-Widget im Dashboard "Berichte"](../../media/spam-detections-report-widget.png)

Weitere Informationen zum Antispamschutz finden Sie unter [Antispamschutz in EOP.](anti-spam-protection.md)

### <a name="report-view-for-the-spam-detections-report"></a>Berichtsansicht für den Spamerkennungsbericht

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Unterschlüsselung nach: Aktion:** Die folgenden Ereignistypen werden angezeigt:

  - **Gefilterter Spaminhalt**
  - **Spam-IP-Blockierung**
  - **Spam-Umschlagblock**
  - **Spam-DBEB-Filter:** Verzeichnisbasierte Edgeblockierung (DBEB)

  Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, können Sie sehen, wie viele Elemente an diesem Tag blockiert wurden und wie diese Elemente kategorisiert werden.

  ![Aktionsansicht im Spamerkennungsbericht](../../media/spam-detections-report-action-view.png)

- **Aufschlüsseln nach: Richtung:** Die folgenden Richtungen werden angezeigt:

  - **Eingehende**
  - **Ausgehende**

  ![Richtungsansicht im Spamerkennungsbericht](../../media/spam-detections-report-direction-view.png)

Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Ereignistypwerte

### <a name="details-table-view-for-the-spam-detections-report"></a>Detailtabellenansicht für den Spamerkennungsbericht

Wenn Sie in einer Berichtsansicht auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Absenderadresse**
- **Empfängeradresse**
- **Ereignistyp**
- **Action**
- **Betreff**

Wenn Sie in einer Detailtabelle auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Ereignistypwerte

Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.

## <a name="spoof-detections-report"></a>Bericht über Spooferkennungen

> [!NOTE]
> Der verbesserte Bericht über Spooferkennungen, wie in diesem Artikel beschrieben, befindet sich in der Vorschau, kann geändert werden und ist nicht in allen Organisationen verfügbar. In der älteren Version des Berichts wurden nur **"Gute E-Mails"** und **"Als Spam abgefangen"** angezeigt.

Der Bericht **"Spooferkennungen"** enthält Informationen zu Nachrichten, die aufgrund von Spoofing blockiert oder zugelassen wurden. Weitere Informationen zum Spoofing finden Sie unter [Antispoofingschutz in EOP.](anti-spoofing-protection.md)

Die Aggregatansicht des Berichts lässt 45 Tage Filterung <sup>\*</sup> zu, während die Detailansicht nur zehn Tage Filterung zulässt.

<sup>\*</sup> Schließlich können Sie die Filterung bis zu 90 Tage verwenden.

Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte,** und klicken Sie unter **Spoofing-Erkennungen** auf **Details anzeigen.** Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/SpoofMailReport> .

![Widget "Spooferkennungen" im Dashboard "Berichte"](../../media/spoof-detections-widget.png)

Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, können Sie sehen, wie viele gefälschte Nachrichten erkannt wurden und warum.

Sie können sowohl das Diagramm als auch die Detailtabelle filtern, indem Sie auf **Filter** klicken und einen oder mehrere der folgenden Werte auswählen:

- **Startdatum** und **Enddatum**

- **Ergebnis**
  - **bestehen**
  - **Fehler**
  - **SoftPass**
  - **Keine**
  - **Other**

- **Spooftyp:** **Intern** und **extern**

![Berichtsansicht im Bericht über Spooferkennungen](../../media/spoof-detections-report-view.png)

Wenn Sie auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Details angezeigt:

- **Date**
- **Gefälschter Benutzer**
- **Senden der Infrastruktur**
- **Spooftyp**
- **Ergebnis**
- **Ergebniscode**
- **SPF**
- **DKIM**
- **DMARC**
- **Nachrichtenanzahl**

Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.

Weitere Informationen zu Ergebniscodes für die zusammengesetzte Authentifizierung finden Sie unter [Antispam-Nachrichtenkopfzeilen in Microsoft 365](anti-spam-message-headers.md).

## <a name="threat-protection-status-report"></a>Threat Protection-Statusbericht

Der **Statusbericht zum Bedrohungsschutz** ist sowohl in EOP als auch in Microsoft Defender für Office 365 verfügbar. Die Berichte enthalten jedoch unterschiedliche Daten. EOP-Kunden können z. B. Informationen zu Schadsoftware anzeigen, die in E-Mails erkannt wurde, aber keine Informationen zu schädlichen Dateien, die von [sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)erkannt wurden.

Der Bericht enthält die Anzahl der E-Mail-Nachrichten mit schädlichen Inhalten, z. B. Dateien oder Websiteadressen (URLs), die vom Antischadsoftwaremodul blockiert wurden, Zap [(Zero-Hour Auto Purge)](zero-hour-auto-purge.md)und Defender für Office 365 Features wie [sichere Links,](safe-links.md) [sichere Anlagen](safe-attachments.md)und [Antiphishing.](set-up-anti-phishing-policies.md) Anhand dieser Informationen können Sie Trends erkennen oder ermitteln, ob Die Unternehmensrichtlinien angepasst werden müssen.

**Hinweis:** Es ist wichtig zu wissen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.

Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte,** und klicken Sie auf Details unter **Bedrohungsschutzstatus** **anzeigen.** Um direkt zum Bericht zu wechseln, öffnen Sie eine der folgenden URLs:

- Microsoft Defender für Office 365:<https://protection.office.com/reportv2?id=TPSAggregateReportATP>
- Eop: <https://protection.office.com/reportv2?id=TPSAggregateReport>

![Bedrohungsschutzstatus-Widget im Dashboard "Berichte"](../../media/threat-protection-status-report-widget.png)

Standardmäßig werden im Diagramm Daten für die letzten 7 Tage angezeigt. Wenn Sie auf **"Filter"** klicken, können Sie einen Zeitraum von 90 Tagen auswählen (Testabonnements sind möglicherweise auf 30 Tage begrenzt). Die Detailtabellenansicht ermöglicht das Filtern für 30 Tage.

### <a name="report-view-for-the-threat-protection-status-report"></a>Berichtsansicht für den Bedrohungsschutzstatusbericht

Die folgenden Ansichten sind verfügbar:

- **Anzeigen von Daten nach: Übersicht:** Die folgenden Erkennungsinformationen werden angezeigt:

  - **E-Mail-Schadsoftware**
  - **E-Mail-Phishing**
  - **Inhalts-Schadsoftware**

  ![Übersichtsansicht im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-overview-view.png)

- **Anzeigen von Daten nach: Inhalt \> Schadsoftware**<sup>1:</sup>Die folgenden Informationen werden für Microsoft Defender für Office 365 Organisationen angezeigt:

  - **Antischadsoftwaremodul:** Schädliche Dateien, die in SharePoint, OneDrive und Microsoft Teams von der [integrierten Virenerkennung in Microsoft 365](virus-detection-in-spo.md)erkannt werden.
  - **Dateidetonation:** Schädliche Dateien, die von [sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)erkannt werden.

  ![Ansicht "Inhalts-Schadsoftware" im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-content-malware-view.png)

- **Anzeigen von Daten nach: Nachrichtenüberschreibung:** Die folgenden Informationen zum Außerkraftsetzungsgrund werden angezeigt:

  - **Lokales Überspringen**
  - **IP zulassen**
  - **Nachrichtenflussregel**
  - **Absender zulassen**
  - **Domänen zulassen**
  - **ZAP nicht aktiviert**
  - **Junk-E-Mail-Ordner nicht aktiviert**
  - **Benutzersicherer Absender**
  - **Benutzersichere Domäne**

  ![Ansicht "Nachrichtenüberschreibung" im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-message-override-view.png)

- **Unterschlüsselung nach: Erkennungstechnologie** und **Anzeigen von Daten nach: E-Mail-Phishing: \>** Die folgenden Informationen werden angezeigt:

  - **ATP-generierte URL-Zuverlässigkeit**<sup>1:</sup>Bösartige URL-Reputation, die von Defender für Office 365 Detonationen in anderen Microsoft 365 Kunden generiert wurde.
  - **Erweiterter Phishingfilter:** Phishingsignale basierend auf maschinellem Lernen.
  - **Antispoofing : DMARC-Fehler:** DMARC-Authentifizierungsfehler bei Nachrichten.
  - **Antispoofing – organisationsintern:** Der Absender versucht, die Empfängerdomäne zu spoofen.
  - **Antispoofing – externe Domäne:** Der Absender versucht, eine andere Domäne zu spoofen.
  - **Markenidentitätswechsel:** Identitätswechsel bekannter Marken basierend auf Absendern.
  - **Domänenidentitätswechsel**<sup>1:</sup>Identitätswechsel von Domänen, die der Kunde besitzt oder definiert.
  - **EOP-URL-Zuverlässigkeit:** Böswillige URL-Reputation.
  - **Allgemeiner Phishingfilter:** Phishingsignale basierend auf Analystenregeln.
  - **Sonstige**
  - **Phishing ZAP**<sup>2:</sup>Automatische Bereinigung von Phishingnachrichten zur Nullstunde.
  - **URL-Detonation**<sup>1</sup>
  - **Benutzeridentitätswechsel**<sup>1:</sup>Identitätswechsel von Benutzern, die vom Administrator definiert wurden oder über die Postfachintelligenz gelernt haben.

  ![Ansicht der Erkennungstechnologie für Phishing-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-detection-tech-view.png)

- **Unterschlüsselung nach: Erkennungstechnologie** und **Anzeigen von Daten nach: E-Mail-Schadsoftware: \>** Die folgenden Informationen werden angezeigt:

  - **ATP-generierte Dateireputation**<sup>1:</sup>Alle bösartigen Dateireputationen, die von Defender für Office 365 Detonationen generiert wurden.
  - **Antischadsoftwaremodul**<sup>1:</sup>Erkennung von Antischadsoftwaremodulen.
  - Dateitypblock für **Antischadsoftwarerichtlinie:** Hierbei handelt es sich um E-Mail-Nachrichten, die aufgrund des in der Nachricht identifizierten Typs bösartiger Dateien herausgefiltert werden.
  - **Dateidetonation**<sup>1:</sup>Erkennung durch sichere Anlagen.
  - **Böswillige Dateireputation**
  - **Schadsoftware ZAP**<sup>2</sup>
  - **Sonstige**

  ![Ansicht der Erkennungstechnologie für Schadsoftware im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-malware-detection-tech-view.png)

- **Unterschlüsselung nach: Richtlinientyp** und **Daten anzeigen nach: E-Mail-Phishing \>** oder **Daten anzeigen nach: E-Mail-Schadsoftware: \>** Die folgenden Informationen werden angezeigt:

  - **Antischadsoftware**
  - **Sichere Anlagen**<sup>1</sup>
  - **Antiphishing**
  - **Antispam**
  - **Nachrichtenflussregel** (auch als Transportregel bezeichnet)
  - **Sonstige**

  ![Richtlinientypansicht für Phishing-E-Mails im Bedrohungsschutzstatusbericht](../../media/threat-protection-status-report-phishing-policy-type-view.png)

- **Aufschlüsseln nach: Zustellungsstatus** und **Daten anzeigen nach: E-Mail-Phishing \>** oder **Daten anzeigen nach: E-Mail-Schadsoftware: \>** Die folgenden Informationen werden angezeigt:

  - **Übermittlung fehlgeschlagen**
  - **Gelöscht**
  - **Weitergeleitet**
  - **Gehostetes Postfach: Benutzerdefinierter Ordner**
  - **Gehostetes Postfach: Gelöschte Elemente**
  - **Gehostetes Postfach: Posteingang**
  - **Gehostetes Postfach: Junk**
  - **Lokaler Server: Bereitgestellt**
  - **Quarantäne**

  ![Übermittlungsstatusansicht für Phishing-E-Mails im Statusbericht zum Bedrohungsschutz](../../media/threat-protection-status-report-phishing-delivery-status-view.png)

<sup>1</sup> Defender nur für Office 365

<sup>2</sup> Zero-Hour Auto Purge (ZAP) ist in eigenständigem EOP nicht verfügbar (es funktioniert nur in Exchange Online Postfächern).

Wenn Sie auf **Filter** klicken, hängen die verfügbaren Filter von dem Diagramm ab, das Sie sich ansehen:

- For **View data by: Content \> Malware**, you can modify the report by **Start date** and end **date,** and the **Detection** value.

- For **View data by: Message Override**, you can modify the report with the following filters:

  - **Startdatum** und **Enddatum**
  - **Außerkraftsetzungsgrund**
  - **Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten). Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)
  - **Domäne**

- Für alle anderen Ansichten können Sie den Bericht mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - **Erkennung**
  - **Geschützt durch:** **ATP** oder **EOP**
  - **Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten). Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)
  - **Domäne**

### <a name="details-table-view-for-the-threat-protection-status-report"></a>Detailtabellenansicht für den Bedrohungsschutzstatusbericht

Wenn Sie auf **"Detailtabelle anzeigen"** klicken, hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich ansehen:

- **Anzeigen von Daten nach: Übersicht:** Es ist keine Schaltfläche für **die Ansichtsdetails-Tabelle** verfügbar.

- **Anzeigen von Daten nach: Inhalt \> Schadsoftware**:

  - **Date**
  - **Standort**
  - **Weitergeleitet von**
  - **Name der Schadsoftware**

  Wenn Sie in dieser Ansicht auf **Filter** klicken, können Sie den Bericht nach **Startdatum** und **Enddatum** sowie dem **Erkennungswert** ändern.

- **Anzeigen von Daten nach: Nachrichtenüberschreibung:**

  - **Date**
  - **Betreff**
  - **Sender**
  - **Recipients**
  - **Erkannt von**
  - **Außerkraftsetzungsgrund**
  - **Quelle der Kompromitt**
  - **Tags**

  Wenn Sie in dieser Ansicht auf **Filter** klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - **Außerkraftsetzungsgrund**
  - **Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten). Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)
  - **Domäne**
  - **Empfänger** (Beachten Sie, dass diese filterbare Eigenschaft nur in der Detailtabellenansicht verfügbar ist)

- Alle anderen Diagramme:

  - **Date**
  - **Betreff**
  - **Sender**
  - **Recipients**
  - **Erkannt von**
  - **Übermittlungsstatus**
  - **Quelle der Kompromitt**
  - **Tags**

  Wenn Sie auf **"Filter"** klicken, können Sie den Bericht mit den folgenden Filtern ändern:

  - **Startdatum** und **Enddatum**
  - **Erkennung**
  - **Geschützt durch:** **Defender für Office 365** oder **EOP**
  - **Tag:** Filtert die Ergebnisse nach Benutzern oder Gruppen, auf die das angegebene Benutzertag angewendet wurde (einschließlich Prioritätskonten). Weitere Informationen zu Benutzertags finden Sie unter [Benutzertags.](user-tags.md)
  - **Domäne**
  - **Empfänger** (Beachten Sie, dass diese filterbare Eigenschaft nur in der Detailtabellenansicht verfügbar ist)

## <a name="top-malware-report"></a>Bericht über häufigste Schadsoftware

Der **Bericht "Häufigste Schadsoftware"** zeigt die verschiedenen Arten von Schadsoftware, die vom [Schutz vor Schadsoftware in EOP](anti-malware-protection.md)erkannt wurden.

Um den Bericht anzuzeigen, öffnen Sie das [Microsoft 365 Defender-Portal,](https://security.microsoft.com)wechseln Sie zu **"E-Mail-Berichte** \> **& Zusammenarbeit** \> **E-Mail & Zusammenarbeitsberichte",** und klicken Sie auf **"Details anzeigen"** unter **"Häufigste Schadsoftware".** Um direkt zum Bericht zu wechseln, öffnen Sie <https://security.microsoft.com/reports/TopMalware> .

![Das am häufigsten verwendete Malware-Widget im Dashboard "Berichte"](../../media/top-malware-report-widget.png)

Wenn Sie den Mauszeiger über einen Wedge im Kreisdiagramm bewegen, sehen Sie den Namen einer Art von Schadsoftware und wie viele Nachrichten als Schadsoftware erkannt wurden.

![Ansicht des Berichts über häufigste Schadsoftware](../../media/top-malware-report-view.png)

Wenn Sie auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Details angezeigt:

- **Häufigste Schadsoftware**
- **Count**

Wenn Sie in der Berichtsansicht oder in der Detailtabellenansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.

## <a name="url-threat-protection-report"></a>URL-Bedrohungsschutzbericht

Der **URL-Bedrohungsschutzbericht** ist in Microsoft Defender für Office 365 verfügbar. Weitere Informationen finden Sie unter [URL Threat Protection Report](view-reports-for-mdo.md#url-threat-protection-report).

## <a name="user-reported-messages-report"></a>Bericht über vom Benutzer gemeldete Nachrichten

Der Bericht **"Vom Benutzer gemeldete Nachrichten"** enthält Informationen zu E-Mail-Nachrichten, die Benutzer mithilfe des [Add-Ins "Nachricht melden"](enable-the-report-message-add-in.md) oder des [Add-Ins "Berichtsphishing"](enable-the-report-phish-add-in.md)als Junk- oder Phishingversuche oder als gute E-Mails gemeldet haben.

Details sind für jede Nachricht verfügbar, einschließlich des Grunds für die Zustellung, z. B. eine Für Ihre Organisation konfigurierte Spamrichtlinienausnahme oder E-Mail-Flussregel. Wählen Sie zum Anzeigen von Details ein Element in der Benutzerberichtsliste aus, und zeigen Sie dann die Informationen auf den Registerkarten **Zusammenfassung** und Details an. 

![Der Bericht "Vom Benutzer gemeldete Nachrichten" zeigt Nachrichten an, die als Junk-, nicht Junk- oder Phishingversuche gekennzeichnet sind.](../../media/ad5e9a3d-b833-419c-bcc9-3425d9604ead.png)

To view this report, in the [Microsoft 365 Defender portal,](https://security.microsoft.com)go to **Reports** Email \> **& collaboration** \> **Email & collaboration reports** \> **User reported messages**.

- Go to **Reports** \> **Email & collaboration** Email & collaboration \> **reports** User \> **reported messages**.

![Wählen Sie im Microsoft 365 Defender-Portal \> "Berichts-E-Mail & Zusammenarbeit \> E-Mail & Berichte zur Zusammenarbeit \> Gemeldete Benutzernachrichten" aus.](../../media/user-reported-messages.png)

> [!IMPORTANT]
> Damit der Bericht über vom Benutzer gemeldete Nachrichten ordnungsgemäß funktioniert, muss die **Überwachungsprotokollierung** für Ihre Office 365 Umgebung aktiviert sein. Dies geschieht in der Regel von einer Person, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren Microsoft 365 Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?

Um die in diesem Artikel beschriebenen Berichte anzuzeigen und zu verwenden, müssen Sie Mitglied einer der folgenden Rollengruppen im Microsoft 365 Defender-Portal sein:

- **Organisationsverwaltung**
- **Sicherheitsadministrator**
- **Sicherheitsleseberechtigter**
- **Globaler Leser**

Weitere Informationen finden Sie unter [Berechtigungen im Microsoft 365 Defender-Portal.](permissions-in-the-security-and-compliance-center.md)

**Hinweis:** Wenn Sie Benutzer zur entsprechenden Azure Active Directory Rolle im Microsoft 365 Admin Center hinzufügen, erhalten Benutzer die erforderlichen Berechtigungen im Microsoft 365 Defender-Portal _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="what-if-the-reports-arent-showing-data"></a>Was geschieht, wenn in den Berichten keine Daten angezeigt werden?

Wenn in Ihren Berichten keine Daten angezeigt werden, überprüfen Sie, ob Ihre Richtlinien ordnungsgemäß eingerichtet sind. Weitere Informationen finden Sie unter ["Schutz vor Bedrohungen".](protect-against-threats.md)

## <a name="related-topics"></a>Verwandte Themen

[Antispam- und Antischadsoftwareschutz in EOP](anti-spam-and-anti-malware-protection.md)

[Intelligente Berichte und Einblicke im Microsoft 365 Defender-Portal](reports-and-insights-in-security-and-compliance.md)

[Anzeigen von Nachrichtenflussberichten im Microsoft 365 Defender-Portal](view-mail-flow-reports.md)

[Anzeigen von Berichten für Defender für Office 365](view-reports-for-mdo.md)
