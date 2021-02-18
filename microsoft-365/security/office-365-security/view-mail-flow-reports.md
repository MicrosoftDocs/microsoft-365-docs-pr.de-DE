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
ms.openlocfilehash: dbbec056203ad816d37f5451115d2c7d172eee92
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286717"
---
# <a name="view-mail-flow-reports-in-the-reports-dashboard-in-security--compliance-center"></a>Anzeigen von Nachrichtenflussberichten im Dashboard "Berichte" im Security & Compliance Center

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Zusätzlich zu den Nachrichtenflussberichten, [](mail-flow-insights-v2.md) die im E-Mail-Flussdashboard im Security & Compliance Center verfügbar sind, stehen im Dashboard "Berichte" verschiedene zusätzliche Nachrichtenflussberichte zur Verfügung, die Ihnen bei der Überwachung Ihrer Microsoft 365-Organisation helfen.

Wenn Sie über die erforderlichen [Berechtigungen verfügen,](#what-permissions-are-needed-to-view-these-reports)können Sie diese Berichte im [Security & Compliance Center](https://protection.office.com) anzeigen, indem Sie zum Dashboard **"Berichte"** \> **gehen.** Um direkt zum Dashboard "Berichte" zu wechseln, öffnen Sie <https://protection.office.com/insightdashboard> .

![Dashboard "Berichte" im Security & Compliance Center](../../media/6b213d34-adbb-44af-8549-be9a7e2db087.png)

## <a name="connector-report"></a>Connectorbericht

Der **Connectorbericht zeigt** nachrichtenflussaktivitäten auf den eingehenden und ausgehenden [Connectors,](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/use-connectors-to-configure-mail-flow) die für Ihre Organisation konfiguriert sind.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** und wählen Sie \>  den **Connectorbericht aus.** Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ConnectorReport> .

![Connectorberichts-Widget im Dashboard "Berichte"](../../media/connector-report-widget.png)

### <a name="report-view-for-the-connector-report"></a>Berichtsansicht für den Connectorbericht

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Daten anzeigen nach: Nachrichtenfluss:** Dieses Diagramm zeigt die Anzahl der eingehenden und ausgehenden Nachrichten, organisiert nach:

  - **Total**
  - **Aus dem Internet ohne Connector**
  - **Ins Internet ohne Connector**
  - Ein bestimmter Connector, den Sie konfiguriert haben.

  Um die Daten im Diagramm  zu isolieren, verwenden Sie das Steuerelement "Daten für Steuerelement anzeigen", um eine dieser Optionen oder den **ganzen Nachrichtenfluss auszuwählen.**

  ![Anzeigen von Daten nach Nachrichtenfluss im Connectorbericht](../../media/connector-report-view-data-by-mail-flow.png)

- **Daten nach: TLS-Verwendung anzeigen:** Dieses Diagramm zeigt den Prozentsatz der Verwendung der Transport Layer Security (TLS)-Version für den Nachrichtenfluss.

  Um die Daten im Diagramm  zu isolieren, verwenden Sie das Steuerelement "Daten für Steuerelement anzeigen", um eine der folgenden Optionen auszuwählen:

  - **Sämtlicher Nachrichtenfluss**
  - **Aus dem Internet ohne Connector**
  - **Ins Internet ohne Connector**
  - Ein bestimmter Connector, den Sie konfiguriert haben.

  ![Anzeigen von Daten nach der Verwendung von TLS im Connectorbericht](../../media/connector-report-view-data-by-tls-usage.png)

Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

### <a name="details-table-view-for-the-connector-report"></a>Detailtabelle für den Connectorbericht

Wenn Sie in einer **Berichtsansicht auf "Details anzeigen"** klicken, werden die folgenden Informationen angezeigt:

- **Date**
- **Connectorrichtung und -name**
- **Connectortyp**
- **Erzwungenes TLS?**: Der Wert **True** oder **False**.
- **Kein TLS** (Prozentsatz)
- **TLS 1.0** (Prozentsatz)
- **TLS 1.1** (Prozentsatz)
- **TLS 1.2** (Prozentsatz)
- **Volume**: Die Anzahl der Nachrichten.

Wenn Sie in einer **Detailtabelle auf** Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**

## <a name="exchange-transport-rule-report"></a>Bericht über Exchange-Transportregel

Der **Exchange-Transportregelbericht** zeigt die Auswirkungen von Nachrichtenflussregeln (auch als Transportregeln bezeichnet) auf eingehende und ausgehende Nachrichten in Ihrer Organisation.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** und wählen Sie \>  die **Exchange-Transportregel aus.** Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=ETRRuleReport> .

![Exchange-Transportregel-Widget im Dashboard "Berichte"](../../media/transport-rule-report-widget.png)

### <a name="report-view-for-the-exchange-transport-rule-report"></a>Berichtsansicht für den Exchange-Transportregelbericht

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Anzeigen von Daten nach: Exchange-Transportregeln** \> **Nach Folgendem: Richtung:** Dieses Diagramm  zeigt  die Anzahl eingehender und ausgehender Nachrichten, die von Transportregeln betroffen waren.

- **Anzeigen von Daten nach: Exchange-Transportregeln** \> **Nach Schweregrad aufbrechen:** Dieses Diagramm  zeigt die Anzahl der Nachrichten mit hohem schweregrad und mittlerem Schweregrad und niedrigem **Schweregrad.** Sie legen den Schweregrad als Aktion in der Regel **(Diese** Regel mit Schweregrad oder _SetAuditSeverity überwachen) festgelegt._ Weitere Informationen finden Sie unter [Nachrichtenflussregelaktionen in Exchange Online](https://docs.microsoft.com//Exchange/security-and-compliance/mail-flow-rules/mail-flow-rule-actions).

- **Anzeigen von Daten nach: DLP -Exchange-Transportregeln** \> **Nach Folgendem:** Richtung: Dieses Diagramm  zeigt  die Anzahl eingehender und ausgehender Nachrichten, die von Transportregeln zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) betroffen waren. Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:

  - **Anzeigen von Daten für: Alle DLP-Transportregeln**
  - **Anzeigen von Daten für: Gefährdete Benutzer**
  - **Show data for: Low volume of content detected U.S. Patriot Act**

- **Anzeigen von Daten nach: DLP -Exchange-Transportregeln** \> **Aufbrechen nach: Richtung:** Diese Ansicht zeigt die Anzahl der  Nachrichten mit hohem schweregrad und mittlerem Schweregrad sowie Nachrichten mit niedrigem Schweregrad, die von den DLP-Transportregeln betroffen waren.  Sie können das Diagramm weiter verfeinern, indem Sie eine der folgenden Optionen auswählen:

  - **Anzeigen von Daten für: Alle DLP-Transportregeln**
  - **Anzeigen von Daten für: Gefährdete Benutzer**
  - **Show data for: Low volume of content detected U.S. Patriot Act**

Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Schweregradwerte

![Berichtsansicht im Exchange-Transportregelbericht](../../media/transport-rule-report-report-view.png)

### <a name="details-table-view-for-the-exchange-transport-rule-report"></a>Detailtabelle für den Exchange-Transportregelbericht

Wenn Sie auf **"Details anzeigen" klicken,** hängen die angezeigten Informationen vom Diagramm ab, das Sie betrachtet haben:

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

Wenn Sie in einer **Detailtabelle auf** "Filter" klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Schweregradwerte

Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**

## <a name="forwarding-report"></a>Weiterleitungsbericht

Der **Weiterleitungsbericht zeigt** die automatisch von Exchange Online-Postfächern an externe Domänen weitergeleiteten Nachrichten Ihrer Organisation an. Weitergeleitete Nachrichten können ein Sicherheits- oder Compliancerisiko darstellen und auf ein gefährdetes Konto hinweisen.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum **Berichtsdashboard,** und wählen Sie \>  **"Weiterleitungsbericht" aus.** Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=MailFlowForwarding> .

![Widget für Weiterleitungsbericht im Dashboard "Berichte"](../../media/forwarding-report-widget.png)

### <a name="report-view-for-the-forwarding-report"></a>Berichtsansicht für den Weiterleitungsbericht

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Daten für: Weiterleitungsmethoden anzeigen:** Die folgenden Methoden werden gezeigt:

  - **Transportregel:** Auch als [Nachrichtenflussregeln bezeichnet.](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)
  - **Postfachregel:** Auch als [Posteingangsregeln bezeichnet.](https://support.microsoft.com/office/c24f5dea-9465-4df4-ad17-a50704d66c59)

  ![Ansicht "Weiterleitungsmethoden" im Weiterleitungsbericht](../../media/forwarding-report-forwarding-methods.png)

- **Daten anzeigen für: Weiterleitungsdomänen:** In dieser Ansicht werden die Empfängerdomänen angezeigt, die die Ziele für die Weiterleitung sind.

  ![Ansicht "Domänen weiterleiten" im Weiterleitungsbericht](../../media/forwarding-report-forwarding-domains.png)

- **Anzeigen von Daten für: Weiterleitungen:** Die folgenden Weiterleitungen werden angezeigt:

  - **Transportregel**
  - Das Postfach, das die Posteingangsregel für die Weiterleitung enthält.

  ![Weiterleitungsansicht im Weiterleitungsbericht](../../media/forwarding-report-forwarders.png)

Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

### <a name="details-table-view-for-the-forwarding-report"></a>Detailtabelle für den Weiterleitungsbericht

Wenn Sie in einer **Berichtsansicht auf "Details anzeigen"** klicken, werden die folgenden Informationen angezeigt:

- **Weiterleitungen:** Der Wert **der Transportregel** oder das Postfach, das die Posteingangsregel für die Weiterleitung enthält.
- **Weiterleitungstyp:** Der Wert **Postfachregel oder** **Transportregel**.
- **Empfängername**
- **Empfängerdomäne**
- **Details:** Dies ist der GUID-Wert der Nachrichtenflussregel oder der RuleIdentity-Wert der Posteingangsregel.
- **Count**
- **Erstes Weiterleitungsdatum**

Wenn Sie in einer **Detailtabelle auf** Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**

## <a name="mailflow-status-report"></a>Statusbericht über den Nachrichtenfluss

Der **Statusbericht "E-Mail-Nachrichtenfluss"** ähnelt dem Bericht "Gesendete und empfangene E-Mail", [](#sent-and-received-email-report)mit zusätzlichen Informationen zu E-Mails, die auf dem Edge zulässig oder blockiert sind. Dies ist der einzige Bericht, der Informationen zum Edgeschutz enthält und zeigt, wie viele E-Mails blockiert werden, bevor sie zur Auswertung durch Exchange Online Protection (EOP) in den Dienst zugelassen werden. Es ist wichtig zu wissen, dass eine Nachricht, wenn sie an fünf Empfänger gesendet wird, als fünf verschiedene Nachrichten und nicht als eine Nachricht gezählt wird.
Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum Berichtsdashboard, und wählen Sie den Statusbericht für den  \>  **Nachrichtenfluss aus.** Um direkt zum Statusbericht für den **Nachrichtenfluss zu wechseln,** öffnen Sie <https://protection.office.com/mailflowStatusReport> .

![Bericht "E-Mail-Statusbericht" im Dashboard "Berichte"](../../media/mail-flow-status-report-widget.png)

### <a name="type-view-for-the-mailflow-status-report"></a>Typansicht für den Statusbericht "E-Mail-Nachrichtenfluss"

Wenn Sie den Bericht öffnen, ist die Registerkarte **"Typ"** standardmäßig ausgewählt. Standardmäßig enthält diese Ansicht ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:

- **Datum**: Die letzten 7 Tage.
- **Richtung:**

  - **Eingehende Nachrichten**
  - **Ausgehend**
  - **Organisationsinterne :** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h. Absender abc@domain.com an Empfänger gesendet xyz@domain.com (separat von **ein-** und ausgehend **gezählt)**

- **Typ:**

  - **Gute E-Mail**
  - **Schadsoftware**
  - **Spam**
  - **Edgeschutz**
  - **Regelmeldungen**
  - **Phishing-E-Mail**

Das Diagramm ist nach den **Typwerten** organisiert.

Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken.

Die Datentabelle enthält die folgenden Informationen:

- **Richtung**
- **Type**
- **24 Stunden**
- **3 Tage**
- **7 Tage**
- **15 Tage**
- **30 Tage**

Wenn Sie **auf "Kategorie auswählen" klicken,** um weitere Informationen zu erhalten, können Sie aus den folgenden Werten auswählen:

- **Phishing-E-Mail:** Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)
- **Schadsoftware in** E-Mail: Diese Auswahl führt Sie zum Statusbericht zum [Bedrohungsschutz.](view-email-security-reports.md#threat-protection-status-report)
- **Spamerkennungen:** Diese Auswahl führt Sie zum [Bericht "Spamerkennungen".](view-email-security-reports.md#spam-detections-report)
- **Edge blockierter Spam:** Diese Auswahl führt Sie zum Bericht ["Spamerkennungen".](view-email-security-reports.md#spam-detections-report)

**Exportieren:**

Für die Detailansicht können Sie Daten nur für einen Tag exportieren. Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.

Jede exportierte .csv-Datei ist auf 150.000 Zeilen beschränkt. Wenn die Daten für den Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv-Dateien erstellt.

![Typansicht im Statusbericht "Nachrichtenfluss" ](../../media/mail-flow-status-report-type-view.png)

### <a name="direction-view-for-the-mailflow-status-report"></a>Richtungsansicht für den Statusbericht "E-Mail-Nachrichtenfluss"

Wenn Sie auf die Registerkarte **"Richtung"** klicken, werden dieselben Standardfilter aus der **Typansicht** verwendet.

Das Diagramm ist nach **Richtungswerten** organisiert.

Sie können diese Filter ändern, indem Sie auf **"Filter"** oder auf einen Wert in der Diagrammlegende klicken. Es werden dieselben Filter aus der **Typansicht** verwendet.

Die Datentabelle enthält dieselben Informationen aus der **Typansicht.**

The **Choose a category for more details** available selections and behavior are the same as the **Type** view.

**Exportieren:**

Für die Detailansicht können Sie Daten nur für einen Tag exportieren. Wenn Sie Also Daten für 7 Tage exportieren möchten, müssen Sie 7 verschiedene Exportaktionen ausführen.

Jede exportierte .csv-Datei ist auf 150.000 Zeilen beschränkt. Wenn die Daten für den Tag mehr als 150.000 Zeilen enthalten, werden mehrere .csv-Dateien erstellt.

![Richtungsansicht im Statusbericht "E-Mail-Nachrichtenfluss" ](../../media/mail-flow-status-report-direction-view.png)

### <a name="funnel-view-for-the-mailflow-status-report"></a>Trichteransicht für den Statusbericht "E-Mail-Nachrichtenfluss"

Die **Trichteransicht** zeigt, wie die Features zum Schutz vor E-Mail-Bedrohungen von Microsoft eingehende und ausgehende E-Mails in Ihrer Organisation filtern. Sie enthält Details zur Gesamtzahl der E-Mails und dazu, wie sich die konfigurierten Bedrohungsschutzfunktionen, einschließlich Edgeschutz, Ansoftware, Antiphishing, Antispam und Antis spoofing, auf diese Anzahl auswirken.

Wenn Sie auf die Registerkarte **Trichter** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:

- **Datum**: Die letzten 7 Tage.

- **Richtung:**

  - **Eingehende Nachrichten**
  - **Ausgehend**
  - **Organisationsinterne :** Diese Anzahl gilt für Nachrichten, die innerhalb eines Mandanten gesendet werden; d. h. absender abc@domain.com an empfänger-xyz@domain.com (separat von ein- und ausgehend gezählt).

Die Aggregatansicht und die Datentabelle ermöglichen eine Filterung von 90 Tagen.

Wenn Sie auf **"Filter"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.

Dieses Diagramm zeigt die Anzahl der E-Mails, organisiert nach:

- **Gesamt-E-Mail**
- **E-Mail nach Edgeschutz**
- **E-Mail nach Ansoftware, Datei-Reputation, Dateitypblock**
- **E-Mail nach Anti phish, URL-Reputation, Markenwechsel, Antis spoofing**
- **E-Mail nach Antispam, Massen-E-Mail-Filterung**
- **E-Mail nach Benutzer- und Domänenwechsel**<sup>1</sup>
- **E-Mail nach Datei- und URL-Detonation**<sup>1</sup>
- **E-Mail, die nach dem Schutz nach der Zustellung als gutartig erkannt wurde (URL-Klickzeitschutz)**

<sup>Nur 1</sup> Defender für Office 365

Um die von EOP oder Defender für Office 365 gefilterte E-Mail separat anzeigen zu können, klicken Sie auf den Wert in der Diagrammlegende.

Die Datentabelle enthält die folgenden Informationen in absteigender Datumsreihenfolge:

- **Date**
- **Gesamt-E-Mail**
- **Edgeschutz**
- **An malware, file reputation, file type block**:
  - **Datei-Reputation:** Nachrichten, die aufgrund der Identifizierung einer angefügten Datei durch andere Kunden von Microsoft gefiltert wurden.
  - **Dateitypblock:** Nachrichten, die aufgrund des Typs der in der Nachricht identifizierten schädlichen Datei gefiltert wurden.
- **Anti phish, URL reputation, Brand impersonation, anti-spoof**:
  - **URL-Reputation:** Nachrichten, die aufgrund der Identifizierung der URL durch andere Kunden von Microsoft gefiltert wurden.
  - **Markenwechsel:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die von bekannten Marken imitierenden Absendern stammt.
  - **Antis spoof:** Nachrichten, die aufgrund der Nachricht gefiltert wurden, die versucht, eine Domäne, der der Empfänger angehört, oder eine Domäne zu spoofieren, die dem Nachrichtensender nicht gehört.
- **Antispam, Massen-E-Mail-Filterung:**
  - **Massen-E-Mail-Filterung:** Nachrichten, die aufgrund eines Versuchs, Massen-E-Mails an die Empfänger zu senden, gefiltert wurden.
- **Identitätswechsel von Benutzern und Domänen (Defender für Office 365):**
  - **Benutzer-Identitätswechsel:** Nachrichten, die aufgrund eines Versuches gefiltert wurden, die Identität eines Benutzers (Nachrichtensenders) zu imitieren, der in den Identitätsschutzeinstellungen einer Antiphishingrichtlinie definiert ist.
  - **Domänen-Identitätswechsel:** Nachrichten, die aufgrund eines Versuches gefiltert wurden, eine Domäne zu imitieren, die in den Identitätswechselschutzeinstellungen einer Antiphishingrichtlinie definiert ist.
- **Datei- und URL-Detonation (Defender für Office 365)**:
  - **Dateidetonation:** Nachrichten, die durch eine Richtlinie für sichere Anlagen gefiltert wurden.
  - **URL-Detonation:** Nachricht, gefiltert durch eine Richtlinie für sichere Links.
- **Post delivery protection and ZAP (ATP) or ZAP (EOP)**: ZAP indicates zero hour auto-purge.

Wenn Sie eine Zeile in der Datentabelle auswählen, wird eine weitere Aufschlüsselung der E-Mail-Zähler im Flyout angezeigt.

**Exportieren:**

Nachdem Sie unter **"Optionen"** **auf**"Exportieren" geklickt haben, können Sie einen der folgenden Werte auswählen:

- **Zusammenfassung (mit Daten für die letzten 90 Tage)**
- **Details (mit Daten für die letzten 30 Tage)**

Wählen **Sie unter "Datum"** einen Bereich aus, und klicken Sie dann auf **"Übernehmen".** Daten für die aktuellen Filter werden in eine CSV-Datei exportiert.

Jede exportierte .csv-Datei ist auf 150.000 Zeilen beschränkt. Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv-Dateien erstellt.

 ![Trichteransicht im Statusbericht "E-Mail-Nachrichtenfluss" ](../../media/mail-flow-status-report-funnel-view.png)

### <a name="tech-view-for-the-mailflow-status-report"></a>Tech view for the Mailflow status report

Die **tech-Ansicht** ähnelt der **Trichteransicht** und bietet genauere Details für die konfigurierten Funktionen zum Schutz vor Bedrohungen. Anhand des Diagramms können Sie sehen, wie Nachrichten in den verschiedenen Phasen des Bedrohungsschutzes kategorisiert werden.

Wenn Sie auf die Registerkarte **"Tech-Ansicht"** klicken, enthält diese Ansicht standardmäßig ein Diagramm und eine Datentabelle, die mit den folgenden Filtern konfiguriert ist:

- **Datum**: Die letzten 7 Tage.

- **Richtung:**

  - **Eingehende Nachrichten**
  - **Ausgehend**
  - **Organisationsinterne :** Diese Anzahl gilt für Nachrichten innerhalb eines Mandanten, d. h. Absender abc@domain.com an Empfänger gesendet xyz@domain.com (separat von ein- und ausgehend gezählt)

Die Aggregatansicht und die Datentabelle ermöglichen eine Filterung von 90 Tagen.

Wenn Sie auf **"Filter"** klicken, können Sie sowohl das Diagramm als auch die Datentabelle filtern.

Dieses Diagramm zeigt Nachrichten, die in die folgenden Kategorien unterteilt sind:

- **Gesamt-E-Mail**
- **Edge zulassen** und **Edge gefiltert**
- **Keine Schadsoftware,** **Erkennung sicherer Anlagen,** Erkennung von An <sup>\*</sup> **malwaremodulen** und **Regelmeldungen**
- **Kein Phishing,** **DMARC-Fehler,** **Identitätswechselerkennung,** **Spooferkennung** und **Phishingerkennung**
- **Keine Erkennung mit URL-Detonation** und **ERKENNUNG der URL-Detonation**<sup>\*</sup>
- **Keine Spam-** und  **Spamnachrichten**
- **Nicht schädliche E-Mails,** **Erkennung sicherer Links** und <sup>\*</sup> **ZAP**

<sup>\*</sup> Defender für Office 365

Wenn Sie mit der Maus auf eine Kategorie im Diagramm zeigen, wird die Anzahl der Nachrichten in dieser Kategorie angezeigt.

Die Datentabelle enthält die folgenden Informationen in absteigender Datumsreihenfolge:

- **Date**
- **Gesamt-E-Mail**
- **Edge gefiltert**
- **An malware engine, Safe Attachments, rule filtered**:
  - **Regel gefiltert:** Nachrichten, die aufgrund von Nachrichtenflussregeln gefiltert wurden (auch bekannt als Transportregeln).
- **DMARC, Identitätswechsel, Spoofing, Phishing gefiltert:**
  - **DMARC:** Nachrichten, die gefiltert wurden, weil die Nachricht die DMARC-Authentifizierungsprüfung nicht hat.
- **Erkennung der URL-Detonation**
- **Antispamfilter**
- **ZAP entfernt**
- **Erkennung durch sichere Links**

Wenn Sie eine Zeile in der Datentabelle auswählen, wird eine weitere Aufschlüsselung der E-Mail-Zähler im Flyout angezeigt.

**Exportieren:**

Wenn Sie auf **"Exportieren"** **klicken,** können Sie unter "Optionen" einen der folgenden Werte auswählen:

- **Zusammenfassung (mit Daten für die letzten 90 Tage)**
- **Details (mit Daten für die letzten 30 Tage)**

Wählen **Sie unter "Datum"** einen Bereich aus, und klicken Sie dann auf **"Übernehmen".** Daten für die aktuellen Filter werden in eine CSV-Datei exportiert.

Jede exportierte .csv-Datei ist auf 150.000 Zeilen beschränkt. Wenn die Daten mehr als 150.000 Zeilen enthalten, werden mehrere .csv-Dateien erstellt.

 ![Tech view in the Mailflow status report ](../../media/mail-flow-status-report-Tech-view.png)

## <a name="sent-and-received-email-report"></a>Gesendeter und empfangener E-Mail-Bericht

Der **Bericht "Gesendete** und empfangene E-Mail" ist ein intelligenter Bericht mit Informationen zu eingehenden und ausgehenden E-Mails, einschließlich Spamerkennungen, Schadsoftware und als "gut" gekennzeichneter E-Mails. Der Unterschied zwischen diesem Bericht und [dem](#mailflow-status-report) Statusbericht für den Nachrichtenfluss besteht in folgendem: Dieser Bericht enthält keine Daten zu Nachrichten, die durch den Edgeschutz blockiert wurden. Es ist wichtig zu wissen, dass eine Nachricht, wenn sie an fünf Empfänger gesendet wird, als eine Nachricht gezählt wird.

Die Aggregatansicht und die Detailansicht des Berichts lassen eine Filterung von 90 Tagen zu.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum Dashboard "Berichte", und wählen Sie "Gesendete und empfangene E-Mail"  \>  **aus.** Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=SentAndReceivedMailATP> .

![Gesendetes und empfangenes E-Mail-Widget im Dashboard "Berichte"](../../media/sent-and-received-email-report-widget.png)

### <a name="report-view-for-the-sent-and-received-email-report"></a>Berichtsansicht für den Bericht über gesendete und empfangene E-Mails

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Aufteilen nach: Typ**: Das Diagramm zeigt alle verfügbaren Kategorien:

  - **Total**
  - **Gute E-Mail**
  - **Schadsoftware (Ansoftware)** (EOP)
  - **Spamerkennungen**
  - **Regelmeldungen**
  - **Erweiterte Schadsoftware** (Microsoft Defender für Office 365)

  Wenn Sie mit der Maus auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details zu diesem Tag angezeigt.

  ![Typansicht im Bericht "Gesendete und empfangene E-Mail"](../../media/sent-and-received-email-report-type-view.png)

- **Aufbrechen nach: Richtung:** Das Diagramm zeigt **Die Gesamt-,** **Eingehenden** und **ausgehenden** Daten. Wenn Sie mit der Maus auf einen Tag (Datenpunkt) im Diagramm zeigen, werden Details zu diesem Tag angezeigt.

  ![Richtungsansicht im Bericht "Gesendete und empfangene E-Mail"](../../media/sent-and-received-email-report-direction-view.png)

- **Drilldown nach** \> **Schadsoftware (Ansoftware):** Diese Auswahl führt Sie zu den [Schadsoftwareerkennungen im E-Mail-Bericht.](view-email-security-reports.md#malware-detections-in-email-report)

- **Drilldown nach** \> **Spamerkennungen):** Diese Auswahl führt Sie zum Bericht ["Spamerkennungen".](view-email-security-reports.md#spam-detections-report)

Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Typwerte

Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**

### <a name="details-table-view-for-the-sent-and-received-email-report"></a>Detailtabelle für den Bericht "Gesendete und empfangene E-Mail"

Wenn Sie in der **Tabelle "Details anzeigen"** in der Tabelle "Nach: Richtung oder Nach unten  **nach:** Richtungsansicht" klicken, werden die folgenden Informationen angezeigt:

- **Datum (UTC)**
- **Type**
- **Richtung**
- **Anzahl der Nachrichten**

Wenn Sie in einer **Detailtabelle auf** "Filter" klicken, können Sie die Ergebnisse mit den folgenden Filtern ändern:

- **Startdatum** und **Enddatum**
- Richtungswerte
- Typwerte

Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**

## <a name="top-senders-and-recipients-report"></a>Bericht zu den am besten verwendeten Absendern und Empfängern

Der **Bericht "Die besten Absender und Empfänger"** ist ein Kreisdiagramm, in dem Die besten E-Mail-Absender und Empfänger angezeigt werden.

Öffnen Sie zum Anzeigen des Berichts das [Security & Compliance Center,](https://protection.office.com)wechseln Sie zum Dashboard "Berichte", und wählen Sie  \>  **"Top senders and recipients" aus.** Um direkt zum Bericht zu wechseln, öffnen Sie <https://protection.office.com/reportv2?id=TopSenderRecipientsATP> .

![Das Widget mit den besten Absendern und Empfängern im Dashboard "Berichte"](../../media/top-senders-and-recipients-widget.png)

### <a name="report-view-for-the-top-senders-and-recipient-report"></a>Berichtsansicht für den Bericht der obersten Absender und Empfänger

Die folgenden Diagramme sind in der Berichtsansicht verfügbar:

- **Anzeigen von Daten für \> die obersten E-Mail-Absender**
- **Anzeigen von Daten für \> die obersten E-Mail-Empfänger**
- **Anzeigen von Daten für \> die obersten Spamempfänger**
- **Anzeigen von Daten für \> EOP (Top Malware Recipients)**
- **Anzeigen von Daten für \> die am besten geschützten Empfänger von Schadsoftware (Defender für Office 365)**

Die Zusammensetzung des Kreisdiagramms ändert sich basierend auf diesen Auswahlen.

Wenn Sie im Kreisdiagramm auf einen Spalt zeigen, wird die Anzahl der gesendeten oder empfangenen Nachrichten angezeigt.

Wenn Sie **in** einer Berichtsansicht auf "Filter" klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

![Kreisdiagramm in der Berichtsansicht im Bericht "Die obersten Absender und Empfänger"](../../media/top-senders-and-recipients-report-view.png)

### <a name="details-table-view-for-the-top-senders-and-recipient-report"></a>Detailtabelle für den Bericht der obersten Absender und Empfänger

Wenn Sie auf **"Details anzeigen" klicken,** hängen die angezeigten Informationen vom Diagramm ab, das Sie betrachtet haben:

- **Anzeigen von Daten für \> die obersten E-Mail-Absender**

  - **Die am besten verwendeten E-Mail-Absender**
  - **Count**

- **Anzeigen von Daten für \> die obersten E-Mail-Empfänger**

  - **Die am besten verwendeten E-Mail-Empfänger**
  - **Count**

- **Anzeigen von Daten für \> die obersten Spamempfänger**

  - **Die am besten erhaltenen Spamempfänger**
  - **Count**

- **Anzeigen von Daten für \> EOP (Top Malware Recipients)**

  - **Am besten für Schadsoftwareempfänger**
  - **Count**

- **Anzeigen von Daten für \> die am besten geschützten Empfänger von Schadsoftware (Defender für Office 365)**

  - **Am besten für Schadsoftwareempfänger (Defender für Office 365)**
  - **Count**

Wenn Sie in einer **Detailtabelle auf** Filter klicken, können Sie einen Datumsbereich mit **Startdatum** und **Enddatum angeben.**

Klicken Sie auf "Bericht anzeigen", um zur **Berichtsansicht zurück zu wechseln.**

## <a name="what-permissions-are-needed-to-view-these-reports"></a>Welche Berechtigungen sind erforderlich, um diese Berichte anzeigen zu können?

Um die in diesem Artikel beschriebenen Berichte anzeigen und verwenden zu können, müssen Sie Mitglied einer der folgenden Rollengruppen im Security & Compliance Center sein:

- **Organisationsverwaltung**
- **Sicherheitsadministrator**
- **Sicherheitsleseprogramm**
- **Globaler Leser**

Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

> [!NOTE]
> Durch das Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen im Security & Compliance Center _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).

## <a name="related-topics"></a>Verwandte Themen

[Intelligente Berichte und Einblicke im Security & Compliance Center](reports-and-insights-in-security-and-compliance.md)

[Nachrichtenübermittlung und Einblicke im Security & Compliance Center](mail-flow-insights-v2.md)

[Anzeigen von E-Mail-Sicherheitsberichten im Security & Compliance Center](view-email-security-reports.md)

[Anzeigen von Berichten für Microsoft Defender für Office 365](view-reports-for-atp.md)
