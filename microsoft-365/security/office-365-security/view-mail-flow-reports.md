---
title: Anzeigen von Nachrichtenflussberichten im Dashboard "Berichte"
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: Administratoren können sich über die Nachrichtenflussberichte informieren, die im Dashboard "Berichte" im Security & Compliance Center verfügbar sind.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: fd8f6c3da1c195fbd540638ae73674deccf2762a
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/17/2021
ms.locfileid: "52985504"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>Anzeigen von Nachrichtenflussberichten im Dashboard "Berichte" im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Zusätzlich zu den Nachrichtenflussberichten, die im [Nachrichtenflussdashboard](mail-flow-insights-v2.md) im Security & Compliance Center verfügbar sind, stehen im Berichtsdashboard eine Vielzahl zusätzlicher Nachrichtenflussberichte zur Verfügung, die Ihnen bei der Überwachung Ihrer Microsoft 365-Organisation helfen.

Wenn Sie über die [erforderlichen Berechtigungen](#what-permissions-are-needed-to-view-these-reports)verfügen, können Sie diese Berichte im Security & [Compliance Center](https://protection.office.com) anzeigen, indem Sie zum **Berichtsdashboard** \> wechseln. Um direkt zum Berichtsdashboard zu wechseln, öffnen Sie <https://protection.office.com/insightdashboard> .

![Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>Connectorbericht

Der **Connectorbericht** zeigt Nachrichtenflussaktivitäten auf den [eingehenden und ausgehenden Connectors](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) an, die für Ihre Organisation konfiguriert sind.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **"Connectorbericht"** aus. Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ConnectorReport> .

![Connectorberichts-Widget im Berichtsdashboard](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>Berichtsansicht für den Connectorbericht

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Anzeigen von Daten nach: Nachrichtenfluss:** Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten an, nach:

  - **Total**
  - **Aus dem Internet ohne Connector**
  - **Ins Internet ohne Connector**
  - Ein bestimmter Connector, den Sie konfiguriert haben.

  Um die Daten im Diagramm zu isolieren, verwenden Sie die **Show-Daten für** das Steuerelement, um eine dieser Optionen oder **den gesamten Nachrichtenfluss** auszuwählen.

  ![Anzeigen von Daten nach E-Mail-Fluss im Connector-Bericht](../../media/connector-report-view-data-by-mail-flow.png)

- **Anzeigen von Daten nach: TLS-Verwendung:** Dieses Diagramm zeigt den Prozentsatz der TLS-Versionsnutzung (Transport Layer Security) für den Nachrichtenfluss.

  Um die Daten im Diagramm zu isolieren, verwenden Sie die **Show-Daten für** das Steuerelement, um eine der folgenden Optionen auszuwählen:

  - **Alle Nachrichtenübermittlungen**
  - **Aus dem Internet ohne Connector**
  - **Ins Internet ohne Connector**
  - Ein bestimmter Connector, den Sie konfiguriert haben.

  ![Anzeigen von Daten nach TLS-Verwendung im Connector-Bericht](../../media/connector-report-view-data-by-tls-usage.png)

Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.

### <a name="details-table-view-for-the-connector-report"></a>Detailtabellenansicht für den Connectorbericht

Wenn Sie in einer Berichtsansicht auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Verbindungsrichtung und -name**
- **Connectortyp**
- **Tls erzwungen?**: Der Wert **True** oder **False**.
- **Kein TLS** (Prozentsatz)
- **TLS 1.0** (Prozentsatz)
- **TLS 1.1** (Prozentsatz)
- **TLS 1.2** (Prozentsatz)
- **Volume:** Die Anzahl der Nachrichten.

Wenn Sie in einer **Detailtabellenansicht** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.

Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.

## <a name="exchange-transport-rule-report"></a>Exchange-Transportregelbericht

Der **Exchange-Transportregelbericht** zeigt die Auswirkungen von Nachrichtenflussregeln (auch als Transportregeln bezeichnet) auf ein- und ausgehende Nachrichten in Ihrer Organisation.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **Exchange-Transportregel** aus. Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ETRRuleReport> .

![Exchange-Transportregel-Widget im Berichtsdashboard](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Berichtsansicht für den Exchange-Transportregelbericht

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Anzeigen von Daten nach: Exchange-Transportregeln** \> **Unterschlüsselung nach: Richtung:** Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von Transportregeln betroffen waren.

- **Anzeigen von Daten nach: Exchange-Transportregeln** \> **Unterschlüsselung nach: Schweregrad:** Dieses Diagramm zeigt die Anzahl der Meldungen mit **hohem und** **mittlerem Schweregrad** sowie Meldungen mit **dem niedrigen Schweregrad.** Sie legen den Schweregrad als Aktion in der Regel fest (**Überwachen Sie diese Regel mit Schweregrad** oder _SetAuditSeverity_). Weitere Informationen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online.](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions)

- **Anzeigen von Daten nach: DLP-Exchange-Transportregeln** \> **Unterschlüsselung nach: Richtung:** Dieses Diagramm zeigt die Anzahl der **eingehenden** und **ausgehenden** Nachrichten, die von DLP-Transportregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren. Sie können das Diagramm weiter verfeinern, indem Sie die folgenden Optionen auswählen:

  - **Anzeigen von Daten für: Alle DLP-Transportregeln**
  - **Anzeigen von Daten für: Kompromittierte Benutzer**
  - **Show data for: Low volume of content detected U.S. Mof Act**

- **Anzeigen von Daten nach: DLP-Exchange-Transportregeln** \> **Unterschlüsselung nach: Richtung:** Diese Ansicht zeigt die Anzahl der Nachrichten mit **hohem und** **mittlerem Schweregrad** sowie Nachrichten mit **dem niedrigen Schweregrad,** die von DLP-Transportregeln betroffen waren. Sie können das Diagramm weiter verfeinern, indem Sie die folgenden Optionen auswählen:

  - **Anzeigen von Daten für: Alle DLP-Transportregeln**
  - **Anzeigen von Daten für: Kompromittierte Benutzer**
  - **Show data for: Low volume of content detected U.S. Mof Act**

Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Schweregradwerte

![Berichtsansicht im Exchange-Transportregelbericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Detailtabellenansicht für den Exchange-Transportregelbericht

Wenn Sie auf **"Detailtabelle anzeigen"** klicken, hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich ansehen:

- **Anzeigen von Daten nach: Exchange-Transportregeln:**

  - **Date**
  - **Transportregel**
  - **Betreff**
  - **Absenderadresse**
  - **Empfängeradresse**
  - **Schweregrad**
  - **Richtung**

- **Anzeigen von Daten nach: DLP Exchange-Transportregeln:**

  - **Date**
  - **DLP-Richtlinie**
  - **Transportregel**
  - **Betreff**
  - **Absenderadresse**
  - **Empfängeradresse**
  - **Schweregrad**
  - **Richtung**

Wenn Sie in einer Detailtabellenansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Schweregradwerte

Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.

## <a name="forwarding-report"></a>Weiterleitungsbericht

Der **Weiterleitungsbericht** zeigt die automatisch weitergeleiteten Nachrichten Ihrer Organisation aus Exchange Online-Postfächern an externe Domänen an. Weitergeleitete Nachrichten können ein Sicherheits- oder Compliancerisiko darstellen und auf ein kompromittiertes Konto hinweisen.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **"Weiterleitungsbericht"** aus. Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![Weiterleitung des Berichts-Widgets im Berichtsdashboard](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>Berichtsansicht für den Weiterleitungsbericht

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Anzeigen von Daten für: Weiterleitungsmethoden:** Die folgenden Methoden werden angezeigt:

  - **Transportregel**: Wird auch als [Nachrichtenflussregeln bezeichnet.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - **Postfachregel**: Wird auch als [Posteingangsregeln bezeichnet.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)

  ![Ansicht "Weiterleitungsmethoden" im Weiterleitungsbericht](../../media/forwarding-report-forwarding-methods.png)

- **Anzeigen von Daten für: Weiterleitungsdomänen:** In dieser Ansicht werden die Empfängerdomänen angezeigt, die die Ziele für die Weiterleitung sind.

  ![Ansicht "Weiterleitungsdomänen" im Bericht "Weiterleitung"](../../media/forwarding-report-forwarding-domains.png)

- **Show data for: forwarders**: The following forwarders are shown:

  - **Transportregel**
  - Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.

  ![Ansicht "Weiterleitungen" im Weiterleitungsbericht](../../media/forwarding-report-forwarders.png)

Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.

### <a name="details-table-view-for-the-forwarding-report"></a>Detailtabellenansicht für den Weiterleitungsbericht

Wenn Sie in einer Berichtsansicht auf **"Detailtabelle anzeigen"** klicken, werden die folgenden Informationen angezeigt:

- **Weiterleitungen:** Der Wert **"Transportregel"** oder das Postfach, das die Posteingangsregel für die Weiterleitung enthält.
- **Weiterleitungstyp:** Der Wert **Postfachregel** oder **Transportregel**.
- **Empfängername**
- **Empfängerdomäne**
- **Details:** Dies ist der GUID-Wert der Nachrichtenflussregel oder der RuleIdentity-Wert der Posteingangsregel.
- **Count**
- **Erstes Weiterleitungsdatum**

Wenn Sie in einer **Detailtabellenansicht** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.

Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.

## <a name="mailflow-status-report"></a>E-Mailflow-Statusbericht

Der **E-Mailflow-Statusbericht** ähnelt dem [Bericht "Gesendete und empfangene E-Mails"](#sent-and-received-email-report)mit zusätzlichen Informationen zu E-Mails, die am Edge zugelassen oder blockiert werden. Dies ist der einzige Bericht, der Edgeschutzinformationen enthält, und zeigt an, wie viele E-Mails blockiert werden, bevor sie zur Auswertung durch Exchange Online Protection (EOP) in den Dienst zugelassen werden. Es ist wichtig zu verstehen, dass eine Nachricht, die an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.
Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **Den E-Mail-Flussstatusbericht** aus. To go directly to the **Mail flow status report**, open <https://protection.office.com/mailflowStatusReport> .

![Nachrichtenflussstatusberichts-Widget im Dashboard "Berichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Typansicht für den Mailflow-Statusbericht

Wenn Sie den Bericht  öffnen, ist standardmäßig die Registerkarte Typ ausgewählt. Standardmäßig enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:

- **Datum:** Die letzten 7 Tage.
- **Richtung:**

  - **Eingehende**
  - **Ausgehende**
  - **Organisationsinternes:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h. absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von **ein-** und **ausgehend** gezählt)

- **Typ:**

  - **Gute E-Mails**
  - **Schadsoftware**
  - **Spam**
  - **Edgeschutz**
  - **Regelnachrichten**
  - **Phishing-E-Mail**

Das Diagramm ist nach den **Type-Werten** organisiert.

Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.

Die Datentabelle enthält die folgenden Informationen:

- **Richtung**
- **Typ**
- **24 Stunden**
- **3 Tage**
- **7 Tage**
- **15 Tage**
- **30 Tage**

Wenn Sie auf **"Kategorie auswählen"** klicken, um weitere Details zu erhalten, können Sie aus den folgenden Werten auswählen:

- **Phishing-E-Mail:** Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)
- **Schadsoftware in E-Mails:** Diese Auswahl führt Sie zum [Bedrohungsschutzstatusbericht.](view-email-security-reports.md#threat-protection-status-report)
- **Spamerkennungen:** Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)
- **Edge blockierter Spam:** Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)

**Exportieren**:

Für die Detailansicht können Sie nur Daten für einen Tag exportieren. Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.

Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt. Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.

![Typansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Richtungsansicht für den Mailflow-Statusbericht

Wenn Sie auf die Registerkarte **"Richtung"** klicken, werden die gleichen Standardfilter aus der **Typansicht** verwendet.

Das Diagramm ist nach **Richtungswerten** organisiert.

Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken. Es werden dieselben Filter aus der **Typansicht** verwendet.

Die Datentabelle enthält dieselben Informationen aus der **Typansicht.**

The **Choose a category for more details** available selections and behavior are the same as the **Type** view.

**Exportieren**:

Für die Detailansicht können Sie nur Daten für einen Tag exportieren. Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.

Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt. Wenn die Daten für diesen Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.

![Richtungsansicht im E-Mailflow-Statusbericht](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a>Trichteransicht für den Mailflow-Statusbericht

Die **Trichteransicht** zeigt Ihnen, wie die E-Mail-Bedrohungsschutzfeatures von Microsoft eingehende und ausgehende E-Mails in Ihrer Organisation filtern. Es enthält Details zur Gesamtzahl der E-Mails und dazu, wie sich die konfigurierten Bedrohungsschutzfeatures, einschließlich Edgeschutz, Antischadsoftware, Antiphishing, Antispam und Antispoofing, auf diese Anzahl auswirken.

Wenn Sie auf die Registerkarte **"Trichter"** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert sind:

- **Datum:** Die letzten 7 Tage.

- **Richtung:**

  - **Eingehende**
  - **Ausgehende**
  - **Organisationsintern:** Diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden; d. h. absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von Ein- und Ausgehend gezählt).

Die Aggregatansicht und die Datentabellenansicht ermöglichen eine Filterung von 90 Tagen.

Wenn Sie auf **"Filtern"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.

Dieses Diagramm zeigt die E-Mail-Anzahl nach:

- **E-Mail-Gesamtanzahl**
- **E-Mail nach Edgeschutz**
- **E-Mail nach Antischadsoftware, Dateireputation, Dateitypblockierung**
- **E-Mail nach Antiphishing, URL-Reputation, Markenidentitätswechsel, Antispoofing**
- **E-Mails nach Antispam, Massenfilterung von E-Mails**
- **E-Mail nach Benutzer- und Domänenidentitätswechsel**<sup>1</sup>
- **E-Mail nach Datei- und URL-Detonation**<sup>1</sup>
- **E-Mails, die nach der Zustellung als gutartig erkannt wurden (URL-Click-Time-Schutz)**

<sup>1</sup> Nur Defender für Office 365

Um die von EOP oder Defender gefilterte E-Mail für Office 365 separat anzuzeigen, klicken Sie auf den Wert in der Diagrammlegende.

Die Datentabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:

- **Date**
- **E-Mail-Gesamtanzahl**
- **Edgeschutz**
- **Antischadsoftware, Dateireputation, Dateitypblock:**
  - **Dateizuruf:** Nachrichten, die aufgrund der Identifizierung einer angefügten Datei von anderen Microsoft-Kunden gefiltert wurden.
  - **Dateitypblock:** Nachrichten, die aufgrund des typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.
- **Antiphishing, URL-Zuverlässigkeit, Markenidentitätswechsel, Antispoofing:**
  - **URL-Zuverlässigkeit:** Nachrichten, die aufgrund der Identifizierung der URL von anderen Microsoft-Kunden gefiltert wurden.
  - **Markenidentitätswechsel:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die von bekannten Absendern als Absender imitiert wurde.
  - **Antispoofing:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die versucht, eine Domäne zu spoofen, zu der der Empfänger gehört, oder einer Domäne, die der Absender der Nachricht nicht besitzt.
- **Antispam, Massen-E-Mail-Filterung:**
  - **Massen-E-Mail-Filterung:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, Massen-E-Mails an die Empfänger zu übermitteln.
- **Benutzer- und Domänenidentitätswechsel (Defender für Office 365):**
  - **Benutzeridentitätswechsel:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, einen Benutzer (Nachrichtensender) zu imitieren, der in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.
  - **Domänenidentitätswechsel:** Nachrichten, die aufgrund eines Versuchs gefiltert wurden, eine Domäne zu imitieren, die in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.
- **Datei- und URL-Detonation (Defender für Office 365):**
  - **Dateidetonation:** Nachrichten, die nach einer Safe Anlagenrichtlinie gefiltert sind.
  - **URL-Detonation:** Nachricht, gefiltert nach einer Safe Links-Richtlinie.
- **Schutz nach der Zustellung und ZAP (ATP) oder ZAP (EOP):** ZAP gibt die automatische Bereinigung zur Nullstunde an.

Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.

**Exportieren**:

Nachdem Sie unter **"Optionen"** auf **"Exportieren"** geklickt haben, können Sie einen der folgenden Werte auswählen:

- **Zusammenfassung (mit Daten für die letzten 90 Tage)**
- **Details (mit Daten für die letzten 30 Tage)**

Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen .** Daten für die aktuellen Filter werden in eine .csv Datei exportiert.

Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt. Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.

 ![Trichteransicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a>Tech-Ansicht für den Mailflow-Statusbericht

Die **Tech-Ansicht** ähnelt der **Trichteransicht** und bietet detailliertere Details für die konfigurierten Funktionen zum Schutz vor Bedrohungen. Im Diagramm können Sie sehen, wie Nachrichten in den verschiedenen Phasen des Bedrohungsschutzes kategorisiert werden.

Wenn Sie standardmäßig auf die Registerkarte **"Tech-Ansicht"** klicken, enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert sind:

- **Datum:** Die letzten 7 Tage.

- **Richtung:**

  - **Eingehende**
  - **Ausgehende**
  - **Organisationsinternes:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h. absender abc@domain.com sendet an empfänger xyz@domain.com (getrennt von eingehenden und ausgehenden Zählungen)

Die Aggregatansicht und die Datentabellenansicht ermöglichen eine Filterung von 90 Tagen.

Wenn Sie auf **"Filtern"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.

Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:

- **E-Mail-Gesamtanzahl**
- **Edge zulassen** und **Edge gefiltert**
- **Keine Schadsoftware**, **Safe Erkennung von Anlagen,** <sup>\*</sup> Erkennung von **Antischadsoftwaremodulen** und **Regelmeldungen**
- **Keine Phishing-,** **DMARC-Fehler,** **Identitätswechselerkennung,** **Spooferkennung** und **Phishing-Erkennung**
- **Keine Erkennung mit URL-Detonation** und **URL-Detonationserkennung**<sup>\*</sup>
- **Keine Spam-** und  **Spamnachrichten**
- **Nicht böswillige E-Mails,** **Safe-Links-Erkennung** <sup>\*</sup> und **ZAP**

<sup>\*</sup>Defender für Office 365

Wenn Sie mit dem Mauszeiger auf eine Kategorie im Diagramm zeigen, können Sie die Anzahl der Nachrichten in dieser Kategorie anzeigen.

Die Datentabelle enthält die folgenden Informationen, die in absteigender Datumsreihenfolge angezeigt werden:

- **Date**
- **E-Mail-Gesamtanzahl**
- **Edge gefiltert**
- **Antischadsoftwaremodul, Safe Anlagen, Regel gefiltert:**
  - **Regel gefiltert:** Nachrichten, die aufgrund von Nachrichtenflussregeln gefiltert werden (auch als Transportregeln bezeichnet).
- **DMARC, Identitätswechsel, Spoofing, Phishing gefiltert:**
  - **DMARC:** Nachrichten, die aufgrund eines Fehlers bei der DMARC-Authentifizierungsprüfung gefiltert wurden.
- **ERKENNUNG DER URL-Detonation**
- **Antispam gefiltert**
- **ZAP entfernt**
- **Erkennung durch Safe Links**

Wenn Sie eine Zeile in der Datentabelle auswählen, wird im Flyout eine weitere Aufschlüsselung der E-Mail-Anzahl angezeigt.

**Exportieren**:

Wenn Sie auf **"Exportieren"** klicken, können Sie unter **"Optionen"** einen der folgenden Werte auswählen:

- **Zusammenfassung (mit Daten für die letzten 90 Tage)**
- **Details (mit Daten für die letzten 30 Tage)**

Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen .** Daten für die aktuellen Filter werden in eine .csv Datei exportiert.

Jede exportierte .csv Datei ist auf 150.000 Zeilen beschränkt. Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv Dateien erstellt.

 ![Tech-Ansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a>Gesendeter und empfangener E-Mail-Bericht

Der Bericht **"Gesendete und empfangene E-Mails"** ist ein intelligenter Bericht, der Informationen zu eingehenden und ausgehenden E-Mails anzeigt, einschließlich Spamerkennungen, Schadsoftware und E-Mails, die als "gut" gekennzeichnet sind. Der Unterschied zwischen diesem Bericht und dem [E-Mailflow-Statusbericht](#mailflow-status-report) besteht darin, dass dieser Bericht keine Daten zu Nachrichten enthält, die durch den Edgeschutz blockiert wurden. Es ist wichtig zu verstehen, dass eine Nachricht als eine Nachricht zählt, wenn sie an fünf Empfänger gesendet wird.

Die Aggregatansicht und die Detailansicht des Berichts ermöglichen eine Filterung von 90 Tagen.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie **"Gesendete und empfangene E-Mails"** aus. Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![Gesendetes und empfangenes E-Mail-Widget im Dashboard "Berichte"](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>Berichtsansicht für den Bericht "Gesendete und empfangene E-Mails"

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Unterteilen nach: Typ:** Das Diagramm zeigt alle verfügbaren Kategorien an:

  - **Total**
  - **Gute E-Mails**
  - **Schadsoftware (Antischadsoftware)** (EOP)
  - **Spamerkennungen**
  - **Regelnachrichten**
  - **Erweiterte Schadsoftware** (Microsoft Defender für Office 365)

  Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, sehen Sie Details für diesen Tag.

  ![Typansicht im Bericht "Gesendete und empfangene E-Mails"](../../media/sent-and-received-email-report-type-view.png)

- **Aufschlüsselung nach: Richtung:** Das Diagramm zeigt Daten vom Typ **"Total",** **"Inbound"** und **"Outbound"** an. Wenn Sie den Mauszeiger über einen Tag (Datenpunkt) im Diagramm bewegen, sehen Sie Details für diesen Tag.

  ![Richtungsansicht im Bericht "Gesendete und empfangene E-Mails"](../../media/sent-and-received-email-report-direction-view.png)

- **Drilldown nach** \> **Schadsoftware (Antischadsoftware):** Diese Auswahl führt Sie zum Bericht über [Schadsoftwareerkennungen.](view-email-security-reports.md#malware-detections-report)

- **Drilldown nach** \> **Spamerkennungen)**: Diese Auswahl führt Sie zum [Spamerkennungsbericht.](view-email-security-reports.md#spam-detections-report)

Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Typwerte

Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>Detailtabellenansicht für den Bericht "Gesendete und empfangene E-Mails"

Wenn Sie in der Ansicht **Nach-Unten:Richtung** **auf** Detailtabelle anzeigen klicken, werden die folgenden Informationen angezeigt: 

- **Datum (UTC)**
- **Typ**
- **Richtung**
- **Nachrichtenanzahl**

Wenn Sie in einer Detailtabellenansicht auf **Filter** klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Typwerte

Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.

## <a name="top-senders-and-recipients-report"></a>Bericht zu den wichtigsten Absendern und Empfängern

Der Bericht **"Häufigste Absender und Empfänger"** ist ein Kreisdiagramm, in dem Ihre wichtigsten E-Mail-Absender und -Empfänger angezeigt werden.

Um den Bericht anzuzeigen, öffnen Sie das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** \>  und wählen Sie die wichtigsten Absender **und Empfänger** aus. Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![Widget "Häufigste Absender und Empfänger" im Dashboard "Berichte"](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>Berichtsansicht für den Bericht "Häufigste Absender" und "Empfänger"

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Anzeigen von Daten für \> die wichtigsten E-Mail-Absender**
- **Anzeigen von Daten für \> die wichtigsten E-Mail-Empfänger**
- **Anzeigen von Daten für \> die häufigsten Spamempfänger**
- **Anzeigen von Daten für \> Empfänger von Schadsoftware** (Top Malware Recipients, EOP)
- **Anzeigen von Daten für \> die häufigsten Empfänger von Schadsoftware (Defender für Office 365)**

Die Zusammensetzung des Kreisdiagramms wird basierend auf diesen Auswahlen geändert.

Wenn Sie mit dem Mauszeiger auf einen Wedge im Kreisdiagramm zeigen, können Sie die Anzahl der gesendeten oder empfangenen Nachrichten anzeigen.

Wenn Sie in einer Berichtsansicht auf **Filter** klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.

![Kreisdiagramm in berichtsansicht im Bericht "Top senders and recipients"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>Detailtabellenansicht für den Bericht "Top senders" und "recipient"

Wenn Sie auf **"Detailtabelle anzeigen"** klicken, hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich ansehen:

- **Anzeigen von Daten für \> die wichtigsten E-Mail-Absender**

  - **Die häufigsten E-Mail-Absender**
  - **Count**

- **Anzeigen von Daten für \> die wichtigsten E-Mail-Empfänger**

  - **Top-E-Mail-Empfänger**
  - **Count**

- **Anzeigen von Daten für \> die häufigsten Spamempfänger**

  - **Häufigste Spamempfänger**
  - **Count**

- **Anzeigen von Daten für \> Empfänger von Schadsoftware** (Top Malware Recipients, EOP)

  - **Die häufigsten Empfänger von Schadsoftware**
  - **Count**

- **Anzeigen von Daten für \> die häufigsten Empfänger von Schadsoftware (Defender für Office 365)**

  - **Die häufigsten Empfänger von Schadsoftware (Defender für Office 365)**
  - **Count**

Wenn Sie in einer **Detailtabellenansicht** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum** angeben.

Klicken Sie auf Bericht **anzeigen,** um zur Berichtsansicht zurückzukehren.

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?

Um die in diesem Artikel beschriebenen Berichte anzuzeigen und zu verwenden, müssen Sie Mitglied einer der folgenden Rollengruppen im Security & Compliance Center sein:

- **Organisationsverwaltung**
- **Sicherheitsadministrator**
- **Sicherheitsleseberechtigter**
- **Globaler Leser**

Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="related-topics"></a>Verwandte Themen

[Intelligente Berichte und Einblicke im Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)

[Nachrichtenübermittlung und Einblicke im Security & Compliance Center](mail-flow-insights-v2.md)

[Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center](view-email-security-reports.md)

[Anzeigen von Berichten für Microsoft Defender für Office 365](view-reports-for-mdo.md)
