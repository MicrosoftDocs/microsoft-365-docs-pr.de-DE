---
title: Anzeigen von Nachrichtenflussberichten im Berichtedashboard
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
description: Administratoren können sich über die Nachrichtenflussberichte informieren, die im Dashboard Berichte im Security & Compliance Center verfügbar sind.
ms.custom: ''
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 38beac44af191a027db722ade25ca7fd0e505d9b
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245672"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>Anzeigen von Nachrichtenflussberichten im Berichtedashboard im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Zusätzlich zu den Nachrichtenflussberichten, [](mail-flow-insights-v2.md) die im Nachrichtenflussdashboard im Security & Compliance Center verfügbar sind, stehen im Dashboard Berichte eine Vielzahl zusätzlicher Nachrichtenflussberichte zur Verfügung, mit deren Hilfe Sie Ihre Organisation Microsoft 365 können.

Wenn Sie über die [erforderlichen Berechtigungen verfügen,](#what-permissions-are-needed-to-view-these-reports)können Sie diese Berichte im [Security & Compliance Center](https://protection.office.com) anzeigen, indem Sie zu **Reports** \> **Dashboard gehen.** Öffnen Sie , um direkt zum Dashboard Berichte zu <https://protection.office.com/insightdashboard> wechseln.

![Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>Connectorbericht

Der **Connectorbericht zeigt** nachrichtenflussaktivität auf den ein- und ausgehenden [Connectors,](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die für Ihre Organisation konfiguriert sind.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln **Sie** zu Berichtsdashboard, und wählen \>  Sie **Connectorbericht aus.** Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=ConnectorReport> wechseln.

![Connectorberichts-Widget im Berichtsdashboard](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>Berichtsansicht für den Connectorbericht

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Daten anzeigen nach: Nachrichtenfluss**: Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten an, die nach folgendem Geordneten organisiert sind:

  - **Total**
  - **Aus dem Internet ohne Connector**
  - **Ins Internet ohne Connector**
  - Ein bestimmter Connector, den Sie konfiguriert haben.

  Um die Daten im Diagramm  zu isolieren, verwenden Sie das Steuerelement Daten für Steuerelement anzeigen, um eine dieser Optionen oder **Den ganzen Nachrichtenfluss auszuwählen.**

  ![Anzeigen von Daten nach E-Mail-Fluss im Connectorbericht](../../media/connector-report-view-data-by-mail-flow.png)

- **Daten nach: TLS-Nutzung** anzeigen: Dieses Diagramm zeigt den Prozentsatz der Verwendung der Transport Layer Security (TLS)-Version für den Nachrichtenfluss.

  Verwenden Sie zum Isolieren  der Daten im Diagramm die Option Daten für Steuerelement anzeigen, um eine der folgenden Optionen auszuwählen:

  - **Der ganze E-Mail-Fluss**
  - **Aus dem Internet ohne Connector**
  - **Ins Internet ohne Connector**
  - Ein bestimmter Connector, den Sie konfiguriert haben.

  ![Anzeigen von Daten nach TLS-Nutzung im Connectorbericht](../../media/connector-report-view-data-by-tls-usage.png)

Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

### <a name="details-table-view-for-the-connector-report"></a>Detailtabelle für den Connectorbericht

Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Richtung und Name des Connectors**
- **Connectortyp**
- **Erzwungener TLS-Wert?**: Der **Wert True** oder **False**.
- **Kein TLS** (Prozentsatz)
- **TLS 1.0** (Prozentsatz)
- **TLS 1.1** (Prozentsatz)
- **TLS 1.2** (Prozentsatz)
- **Volume**: Die Anzahl der Nachrichten.

Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**

## <a name="exchange-transport-rule-report"></a>Exchange Transportregelbericht

Der **Exchange-Transportregelbericht** zeigt die Auswirkungen von Nachrichtenflussregeln (auch als Transportregeln bezeichnet) auf ein- und ausgehende Nachrichten in Ihrer Organisation.

Öffnen Sie zum Anzeigen des Berichts das Security  [& Compliance Center,](https://protection.office.com)wechseln Sie zu Berichtsdashboard, und wählen Sie \>  **Exchange Transportregel aus.** Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=ETRRuleReport> wechseln.

![Exchange-Transportregel-Widget im Dashboard "Berichte"](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Berichtsansicht für den Exchange Transportregelbericht

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Anzeigen von Daten nach: Exchange Transportregeln** \> **Nach: Richtung aufbrechen:** Dieses  Diagramm zeigt  die Anzahl der eingehenden und ausgehenden Nachrichten, die von Transportregeln betroffen waren.

- **Anzeigen von Daten nach: Exchange Transportregeln** \> **Aufbrechen nach: Schweregrad**: Dieses  Diagramm zeigt die Anzahl der Nachrichten mit hohem Schweregrad und mittlerem Schweregrad und niedriger **Schweregrad.** Sie legen den Schweregrad als Aktion in der Regel (**Diese** Regel mit schweregrad oder _SetAuditSeverity überwachen) festgelegt._ Weitere Informationen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online](//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Anzeigen von Daten nach: DLP Exchange Transportregeln** \> **Nach: Richtung** aufbrechen: Dieses  Diagramm zeigt  die Anzahl der eingehenden und ausgehenden Nachrichten, die von DLP-Transportregeln (Data Loss Prevention, Verhinderung von Datenverlust) betroffen waren. Sie können das Diagramm weiter verfeinern, indem Sie die folgenden Optionen auswählen:

  - **Anzeigen von Daten für: Alle DLP-Transportregeln**
  - **Anzeigen von Daten für: gefährdete Benutzer**
  - **Anzeigen von Daten für: Geringes Inhaltsvolumen, das vom U.S. Patriot Act erkannt wurde**

- **Anzeigen von Daten nach: DLP Exchange Transportregeln** \> **Nach: Richtung** aufbrechen: Diese  Ansicht zeigt die Anzahl der  Nachrichten mit hohem schweregrad und mittlerem Schweregrad und niedriger Schweregrad, die von DLP-Transportregeln betroffen waren.  Sie können das Diagramm weiter verfeinern, indem Sie die folgenden Optionen auswählen:

  - **Anzeigen von Daten für: Alle DLP-Transportregeln**
  - **Anzeigen von Daten für: gefährdete Benutzer**
  - **Anzeigen von Daten für: Geringes Inhaltsvolumen, das vom U.S. Patriot Act erkannt wurde**

Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Schweregradwerte

![Berichtsansicht im Exchange Transportregelbericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Detailtabelle für den bericht Exchange Transportregel

Wenn Sie auf **Detailtabelle anzeigen klicken,** hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich angeschaut haben:

- **Daten anzeigen nach: Exchange Transportregeln**:

  - **Date**
  - **Transportregel**
  - **Betreff**
  - **Absenderadresse**
  - **Empfängeradresse**
  - **Schweregrad**
  - **Richtung**

- **Anzeigen von Daten nach: DLP Exchange Transportregeln**:

  - **Date**
  - **DLP-Richtlinie**
  - **Transportregel**
  - **Betreff**
  - **Absenderadresse**
  - **Empfängeradresse**
  - **Schweregrad**
  - **Richtung**

Wenn Sie in **einer** Detailtabelle auf Filter klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Schweregradwerte

Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**

## <a name="forwarding-report"></a>Weiterleitungsbericht

Der **Weiterleitungsbericht zeigt** die automatisch weitergeleiteten Nachrichten Ihrer Organisation an externe Domänen aus Exchange Online Postfächern an. Weitergeleitete Nachrichten können ein Sicherheits- oder Compliancerisiko darstellen und möglicherweise auf ein gefährdetes Konto hinweisen.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen \>  Sie **Weiterleitungsbericht aus.** Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=MailFlowForwarding> wechseln.

![Weiterleitungsberichts-Widget im Berichtsdashboard](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>Berichtsansicht für den Weiterleitungsbericht

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Daten anzeigen für: Weiterleitungsmethoden**: Die folgenden Methoden werden angezeigt:

  - **Transportregel**: Wird auch als [Nachrichtenflussregeln bezeichnet.](/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - **Postfachregel**: Wird auch als [Posteingangsregeln bezeichnet.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)

  ![Forwarding methods view in the Forwarding report](../../media/forwarding-report-forwarding-methods.png)

- **Daten anzeigen für: Weiterleitungsdomänen**: Diese Ansicht zeigt die Empfängerdomänen an, die die Ziele für die Weiterleitung sind.

  ![Weiterleitungsdomänenansicht im Weiterleitungsbericht](../../media/forwarding-report-forwarding-domains.png)

- **Daten anzeigen für: Forwarders**: Die folgenden Weiterleitungen werden angezeigt:

  - **Transportregel**
  - Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.

  ![Weiterleitungsansicht im Weiterleitungsbericht](../../media/forwarding-report-forwarders.png)

Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

### <a name="details-table-view-for-the-forwarding-report"></a>Detailtabelle für den Weiterleitungsbericht

Wenn Sie in einer Berichtsansicht auf **Detailtabelle anzeigen** klicken, werden die folgenden Informationen angezeigt:

- **Forwarders**: Der Wert **Transportregel** oder das Postfach, das die Posteingangsregel für die Weiterleitung enthält.
- **Weiterleitungstyp**: Der Wert **Postfachregel oder** **Transportregel**.
- **Empfängername**
- **Empfängerdomäne**
- **Details**: Dies ist der GUID-Wert der Nachrichtenflussregel oder der RuleIdentity-Wert der Posteingangsregel.
- **Count**
- **Erstes Weiterleitungsdatum**

Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**

## <a name="mailflow-status-report"></a>E-Mailflow-Statusbericht

Der **E-Mailflow-Statusbericht** ähnelt dem Bericht "Gesendete und empfangene E-Mail", [](#sent-and-received-email-report)mit zusätzlichen Informationen zu E-Mails, die am Edge zulässig oder blockiert sind. Dies ist der einzige Bericht, der Edgeschutzinformationen enthält und zeigt, wie viele E-Mails blockiert werden, bevor sie zur Auswertung durch EOP (EOP) in den Dienst zugelassen Exchange Online Protection werden. Es ist wichtig zu wissen, dass eine Nachricht, wenn sie an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.
Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen Sie \>  **E-Mailflow-Statusbericht aus.** Öffnen Sie , um direkt zum **Nachrichtenflussstatusbericht zu** <https://protection.office.com/mailflowStatusReport> wechseln.

![E-Mailflow-Statusbericht-Widget im Berichtsdashboard](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Typansicht für den Mailflow-Statusbericht

Wenn Sie den Bericht öffnen, **wird** standardmäßig die Registerkarte Typ ausgewählt. Standardmäßig enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:

- **Datum**: Die letzten 7 Tage.
- **Richtung**:

  - **Eingehendes**
  - **Ausgehend**
  - **Innerhalb der Organisation:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h. Absender abc@domain.com an Empfänger gesendet xyz@domain.com (getrennt von **ein-** und ausgehend **gezählt)**

- **Typ**:

  - **Gute E-Mail**
  - **Schadsoftware**
  - **Spam**
  - **Edgeschutz**
  - **Regelmeldungen**
  - **Phishing-E-Mail**

Das Diagramm wird nach den **Type-Werten** organisiert.

Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken.

Die Datentabelle enthält die folgenden Informationen:

- **Richtung**
- **Typ**
- **24 Stunden**
- **3 Tage**
- **7 Tage**
- **15 Tage**
- **30 Tage**

Wenn Sie auf **Kategorie auswählen klicken,** können Sie aus den folgenden Werten auswählen:

- **Phishing-E-Mail:** Diese Auswahl führt Sie zum [Statusbericht zum Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)
- **Schadsoftware in** E-Mail: Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)
- **Spamerkennungen:** Diese Auswahl führt Sie zum [Bericht "Spamerkennungen".](view-email-security-reports.md#spam-detections-report)
- **Edge-blockierter Spam:** Diese Auswahl führt Sie zum [Bericht "Spamerkennungen".](view-email-security-reports.md#spam-detections-report)

**Export**:

Für die Detailansicht können Sie Daten nur für einen Tag exportieren. Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.

Jede exportierte .csv ist auf 150.000 Zeilen beschränkt. Wenn die Daten für den Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv erstellt.

![Typansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Richtungsansicht für den Mailflow-Statusbericht

Wenn Sie auf die **Registerkarte Richtung** klicken, werden dieselben Standardfilter aus der **Typansicht** verwendet.

Das Diagramm wird nach **Richtungswerten** organisiert.

Sie können diese Filter ändern, indem Sie auf **Filter** klicken oder auf einen Wert in der Diagrammlegende klicken. Es werden dieselben Filter aus der **Typansicht** verwendet.

Die Datentabelle enthält dieselben Informationen aus der **Type-Ansicht.**

Die **Option Kategorie auswählen für weitere Details,** die auswahl- und verhalten verfügbar sind, sind mit der **Typansicht** identisch.

**Export**:

Für die Detailansicht können Sie Daten nur für einen Tag exportieren. Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.

Jede exportierte .csv ist auf 150.000 Zeilen beschränkt. Wenn die Daten für den Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv erstellt.

![Richtungsansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a>Trichteransicht für den Mailflow-Statusbericht

Die **Trichteransicht** zeigt, wie die E-Mail-Bedrohungsschutzfeatures von Microsoft eingehende und ausgehende E-Mails in Ihrer Organisation filtern. Sie enthält Details zur Gesamtzahl der E-Mails und dazu, wie sich die konfigurierten Funktionen zum Schutz vor Bedrohungen, einschließlich Edgeschutz, Anschmierung von Schadsoftware, Antiphishing, Antispam und Antis spoofing auf diese Anzahl auswirken.

Wenn Sie auf die Registerkarte **Trichter** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:

- **Datum**: Die letzten 7 Tage.

- **Richtung**:

  - **Eingehendes**
  - **Ausgehend**
  - **Innerhalb der Organisation:** Diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden. d. h. Absender abc@domain.com an Empfänger gesendet xyz@domain.com (getrennt von ein- und ausgehend gezählt).

Die Aggregatansicht und die Datentabelle ermöglichen eine Filterung von 90 Tagen.

Wenn Sie auf **Filtern** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.

Dieses Diagramm zeigt die E-Mail-Anzahl, die nach folgendem Geordneten organisiert ist:

- **E-Mail insgesamt**
- **E-Mail nach Edgeschutz**
- **E-Mail nach Anschmierung von Schadsoftware, Datei reputation, Dateitypblock**
- **E-Mail nach Antiphish, URL-Reputation, Markenwechsel, Antis spoof**
- **E-Mail nach Antispam, Massen-E-Mail-Filterung**
- **E-Mail nach Benutzer- und Domänenwechsel**<sup>1</sup>
- **E-Mail nach Datei- und URL-Detonation**<sup>1</sup>
- **E-Mails, die nach der Zustellung als gutartig erkannt wurden (URL-Klickzeitschutz)**

<sup>1</sup> Defender für Office 365

Klicken Sie auf den Wert in der Diagrammlegende, um die von EOP oder Defender für Office 365 gefilterte E-Mail-Nachricht separat anzeigen zu können.

Die Datentabelle enthält die folgenden Informationen in absteigender Datumsreihenfolge:

- **Date**
- **E-Mail insgesamt**
- **Edgeschutz**
- **An malware, file reputation, file type block**:
  - **Datei-Reputation:** Nachrichten, die aufgrund der Identifizierung einer angefügten Datei durch andere Microsoft-Kunden gefiltert wurden.
  - **Dateitypblock:** Nachrichten, die aufgrund des Typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.
- **Antiphish, URL-Reputation, Markenwechsel, Antis spoof**:
  - **URL-Reputation:** Nachrichten, die aufgrund der Identifizierung der URL durch andere Microsoft-Kunden gefiltert wurden.
  - **Markenwechsel:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die von bekannten Markensendern als Identitätswechsel gesendet wurde.
  - **Antis spoof**: Nachrichten, die aufgrund der Nachricht gefiltert wurden, die versucht, eine Domäne zu spoofen, zu der der Empfänger gehört, oder eine Domäne, die der Nachrichtensender nicht besitzt.
- **Antispam, Massen-E-Mail-Filterung**:
  - Massen-E-Mail-Filterung: Nachrichten, die aufgrund eines Versuches gefiltert wurden, Massen-E-Mails an die Empfänger zu senden.
- Identitätswechsel von Benutzern und Domänen **(Defender for Office 365)**:
  - **Benutzerwechsel:** Nachrichten, die aufgrund eines Versuches gefiltert wurden, einen Benutzer (Nachrichtensender) zu imitieren, der in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.
  - **Domänenwechsel:** Nachrichten, die aufgrund eines Versuches gefiltert wurden, eine Domäne zu imitieren, die in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.
- **Datei- und URL-Detonation (Defender for Office 365)**:
  - **Dateidetonation:** Nachrichten, die nach einer Richtlinie für sichere Anlagen gefiltert werden.
  - **URL-Detonation:** Nachricht, die nach einer Richtlinie für sichere Links gefiltert wurde.
- **Post-Delivery Protection und ZAP (ATP) oder ZAP (EOP):** ZAP gibt null Stunden automatisches Löschen an.

Wenn Sie eine Zeile in der Datentabelle auswählen, wird eine weitere Aufschlüsselung der E-Mail-Anzahl im Flyout angezeigt.

**Export**:

Nachdem Sie unter **Optionen** auf **Exportieren** geklickt haben, können Sie einen der folgenden Werte auswählen:

- **Zusammenfassung (mit Daten für die letzten 90 Tage)**
- **Details (mit Daten für die letzten 30 Tage)**

Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen**. Daten für die aktuellen Filter werden in eine datei .csv exportiert.

Jede exportierte .csv ist auf 150.000 Zeilen beschränkt. Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv erstellt.

 ![Trichteransicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a>Tech-Ansicht für den Mailflow-Statusbericht

Die **Tech-Ansicht** ähnelt der **Trichteransicht** und bietet detailliertere Details für die konfigurierten Features zum Schutz vor Bedrohungen. Anhand des Diagramms können Sie sehen, wie Nachrichten in den verschiedenen Phasen des Bedrohungsschutzes kategorisiert werden.

Wenn Sie auf die Registerkarte **Tech-Ansicht** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:

- **Datum**: Die letzten 7 Tage.

- **Richtung**:

  - **Eingehendes**
  - **Ausgehend**
  - **Innerhalb der Organisation:** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h. Absender abc@domain.com an Empfänger gesendet xyz@domain.com (getrennt von ein- und ausgehend gezählt)

Die Aggregatansicht und die Datentabelle ermöglichen eine Filterung von 90 Tagen.

Wenn Sie auf **Filtern** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.

Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:

- **E-Mail insgesamt**
- **Edge zulassen** und **Edge gefiltert**
- **Keine Schadsoftware,** **Erkennung sicherer Anlagen,** <sup>\*</sup> Erkennung von An **malwaremodulen** und **Regelmeldungen**
- **Kein Phish,** **DMARC-Fehler,** **Identitätswechselerkennung,** **Spooferkennung** und **Phishingerkennung**
- **Keine Erkennung mit URL-Detonation** und **URL-Detonation**<sup>\*</sup>
- **Keine Spam-** und  **Spamnachrichten**
- **Nicht schädliche E-Mails,** **Erkennung sicherer** <sup>\*</sup> Links und **ZAP**

<sup>\*</sup>Defender für Office 365

Wenn Sie den Mauszeiger auf eine Kategorie im Diagramm zeigen, wird die Anzahl der Nachrichten in dieser Kategorie angezeigt.

Die Datentabelle enthält die folgenden Informationen in absteigender Datumsreihenfolge:

- **Date**
- **E-Mail insgesamt**
- **Edge gefiltert**
- **An malware engine, Safe Attachments, rule filtered**:
  - **Regel gefiltert:** Nachrichten, die aufgrund von Nachrichtenflussregeln gefiltert wurden (auch als Transportregeln bekannt).
- **DMARC, Identitätswechsel, Spoof, Phish gefiltert**:
  - **DMARC**: Nachrichten, die gefiltert wurden, weil die DMARC-Authentifizierungsüberprüfung der Nachricht fehlt.
- **Erkennung der URL-Detonation**
- **Antispam gefiltert**
- **ZAP entfernt**
- **Erkennung durch sichere Links**

Wenn Sie eine Zeile in der Datentabelle auswählen, wird eine weitere Aufschlüsselung der E-Mail-Anzahl im Flyout angezeigt.

**Export**:

Wenn Sie auf **Exportieren** klicken, können Sie unter **Optionen** einen der folgenden Werte auswählen:

- **Zusammenfassung (mit Daten für die letzten 90 Tage)**
- **Details (mit Daten für die letzten 30 Tage)**

Wählen Sie unter **Datum** einen Bereich aus, und klicken Sie dann auf **Übernehmen**. Daten für die aktuellen Filter werden in eine datei .csv exportiert.

Jede exportierte .csv ist auf 150.000 Zeilen beschränkt. Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv erstellt.

 ![Tech-Ansicht im Mailflow-Statusbericht](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a>Gesendeter und empfangener E-Mail-Bericht

Der **Bericht "Gesendete** und empfangene E-Mail" ist ein smarter Bericht, der Informationen zu eingehenden und ausgehenden E-Mails enthält, einschließlich Spamerkennungen, Schadsoftware und E-Mails, die als "gut" identifiziert werden. Der Unterschied zwischen diesem Bericht und dem [E-Mailflow-Statusbericht](#mailflow-status-report) ist: Dieser Bericht enthält keine Daten zu Nachrichten, die durch den Edgeschutz blockiert wurden. Es ist wichtig zu wissen, dass eine Nachricht, wenn sie an fünf Empfänger gesendet wird, als eine Nachricht gezählt wird.

Die Aggregatansicht und die Detailansicht des Berichts ermöglichen eine Filterung von 90 Tagen.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen Sie \>  **Gesendete und empfangene E-Mails aus.** Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> wechseln.

![Gesendetes und empfangenes E-Mail-Widget im Dashboard "Berichte"](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>Berichtsansicht für den Gesendeten und empfangenen E-Mail-Bericht

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Aufteilen nach: Typ**: Das Diagramm zeigt alle verfügbaren Kategorien an:

  - **Total**
  - **Gute E-Mail**
  - **Schadsoftware (Anti-Malware)** (EOP)
  - **Spamerkennungen**
  - **Regelmeldungen**
  - **Erweiterte Schadsoftware** (Microsoft Defender for Office 365)

  Wenn Sie den Mauszeiger auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für den Tag angezeigt.

  ![Typansicht im Bericht Gesendete und empfangene E-Mail](../../media/sent-and-received-email-report-type-view.png)

- **Aufbrechen nach: Richtung**: Das Diagramm zeigt **Gesamt-,** **Eingehende** und **ausgehende** Daten an. Wenn Sie den Mauszeiger auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details für den Tag angezeigt.

  ![Richtungsansicht im Bericht Gesendete und empfangene E-Mails](../../media/sent-and-received-email-report-direction-view.png)

- **Drilldown von** \> **Schadsoftware (Ansoftware):** Diese Auswahl führt Sie zu den [Schadsoftwareerkennungen im E-Mail-Bericht.](view-email-security-reports.md#malware-detections-in-email-report)

- **Drilldown von** \> **Spamerkennungen)**: Diese Auswahl führt Sie zum [Bericht "Spamerkennungen".](view-email-security-reports.md#spam-detections-report)

Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Typwerte

Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>Detailtabelle für den Gesendeten und empfangenen E-Mail-Bericht

Wenn Sie **in der Ansicht Nach:** Richtung oder Nach unten **nach:** Richtungsansicht auf Detailtabelle anzeigen klicken, werden die folgenden Informationen angezeigt: 

- **Datum (UTC)**
- **Typ**
- **Richtung**
- **Anzahl der Nachrichten**

Wenn Sie in **einer** Detailtabelle auf Filter klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Typwerte

Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**

## <a name="top-senders-and-recipients-report"></a>Bericht über die besten Absender und Empfänger

Der **Bericht "Absender und Empfänger am** oberen Rand" ist ein Kreisdiagramm, in dem Ihre absender und empfänger am besten angezeigt werden.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie **zu** Berichtsdashboard, und wählen Sie \>  **Top senders and recipients aus.** Öffnen Sie , um direkt zum Bericht zu <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> wechseln.

![Widget mit den besten Absendern und Empfängern im Dashboard "Berichte"](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>Berichtsansicht für den Bericht mit den besten Absendern und Empfängern

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Anzeigen von Daten für \> Die obersten E-Mail-Absender**
- **Anzeigen von Daten für \> Die obersten E-Mail-Empfänger**
- **Anzeigen von Daten für \> Die besten Spamempfänger**
- **Anzeigen von Daten für \> EOP (Top Malware Recipients)**
- **Anzeigen von Daten für \> Top Malware Recipients (Defender for Office 365)**

Die Zusammensetzung des Kreisdiagramms ändert sich basierend auf diesen Auswahlen.

Wenn Sie auf einen Keil im Kreisdiagramm zeigen, wird eine Anzahl der gesendeten oder empfangenen Nachrichten angezeigt.

Wenn Sie **in** einer Berichtsansicht auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

![Kreisdiagramm in der Berichtsansicht im Bericht "Absender und Empfänger am oberen Rand"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>Detailtabelle für den Bericht "Absender und Empfänger am oberen Rand"

Wenn Sie auf **Detailtabelle anzeigen klicken,** hängen die angezeigten Informationen von dem Diagramm ab, das Sie sich angeschaut haben:

- **Anzeigen von Daten für \> Die obersten E-Mail-Absender**

  - **Die besten E-Mail-Absender**
  - **Count**

- **Anzeigen von Daten für \> Die obersten E-Mail-Empfänger**

  - **Die besten E-Mail-Empfänger**
  - **Count**

- **Anzeigen von Daten für \> Die besten Spamempfänger**

  - **Die besten Spamempfänger**
  - **Count**

- **Anzeigen von Daten für \> EOP (Top Malware Recipients)**

  - **Empfänger der besten Schadsoftware**
  - **Count**

- **Anzeigen von Daten für \> Top Malware Recipients (Defender for Office 365)**

  - **Top malware recipients (Defender for Office 365)**
  - **Count**

Wenn Sie in einer **Detailtabelle** auf Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken Sie auf Bericht anzeigen, um zur Berichtsansicht **zurück zu wechseln.**

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Welche Berechtigungen sind zum Anzeigen dieser Berichte erforderlich?

Um die in diesem Artikel beschriebenen Berichte anzeigen und verwenden zu können, müssen Sie Mitglied einer der folgenden Rollengruppen im Security & Compliance Center sein:

- **Organisationsverwaltung**
- **Sicherheitsadministrator**
- **Security Reader**
- **Globaler Leser**

Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="related-topics"></a>Verwandte Themen

[Intelligente Berichte und Einblicke im Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)

[Nachrichtenübermittlung und Einblicke im Security & Compliance Center](mail-flow-insights-v2.md)

[Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center](view-email-security-reports.md)

[Anzeigen von Berichten für Microsoft Defender für Office 365](view-reports-for-mdo.md)
