---
title: Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
description: Administratoren können alle Arten von isolierten Nachrichten für alle Benutzer anzeigen, freigeben und löschen. Nur Administratoren können Nachrichten verwalten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (Transportregeln) isoliert wurden.
ms.openlocfilehash: fdab820d2ccedaf8e4f51ba71b15d2c807d06dd1
ms.sourcegitcommit: fe4beef350ef9f39b1098755cff46fa2b8e7dc4d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2020
ms.locfileid: "42857073"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-office-365"></a>Verwalten von isolierten Nachrichten und Dateien als Administrator in Office 365

In Quarantäne werden potenziell gefährliche oder unerwünschte Nachrichten in Office 365 Organisationen mit Postfächern in Exchange Online-oder eigenständigen Exchange Online Schutzorganisationen (EoP) ohne Exchange Online Postfächern gespeichert. Weitere Informationen finden Sie unter [Quarantine in Office 365](quarantine-email-messages.md).

Administratoren können alle Arten von isolierten Nachrichten für alle Benutzer anzeigen, freigeben und löschen. Nur Administratoren können Nachrichten verwalten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) isoliert wurden. Administratoren können auch falsch positive Ergebnisse an Microsoft melden.

Administratoren in Organisationen mit Office 365 Advance Threat Protection (ATP) können auch in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams isolierte Dateien anzeigen, herunterladen und löschen.

Sie können isolierte Nachrichten im Security & Compliance Center oder in PowerShell anzeigen und verwalten (Exchange Online PowerShell für Office 365 Kunden; Exchange Online Protection PowerShell für eigenständige EoP-Kunden).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Um das Office 365 Security & Compliance Center zu öffnen, gehen <https://protection.office.com>Sie zu. Um die Quarantäne Seite direkt zu öffnen, wechseln Sie <https://protection.office.com/quarantine>zu.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit Exchange Online Protection PowerShell finden Sie unter [Connect to Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell).

- Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Quarantäne als Administrator verwalten können. Die Berechtigungen werden durch die **Quarantäne** Rolle im Security & Compliance Center gesteuert. Diese Rolle wird standardmäßig der Rollengruppe **Organisationsverwaltung** (Global Admins), **Quarantine Administrator**und **Sicherheitsadministrator** im Security & Compliance Center zugewiesen. Weitere Informationen finden Sie unter [Berechtigungen im Office 365 Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Isolierte Nachrichten werden für einen Standardzeitraum aufbewahrt, bevor Sie automatisch gelöscht werden:

  - Nachrichten, die von antispamregeln (Spam, Phishing und Massen-e-Mails) unter Quarantäne gestellt werden: 30 Tage. Dies ist der Standard-und Höchstwert. Informationen zum Konfigurieren dieses Werts finden Sie unter [configure Anti-Spam Policies in Office 365](configure-your-spam-filter-policies.md).

  - Nachrichten, die nach Nachrichtenfluss Regeln unter Quarantäne gestellt werden (die Regelaktion ist **die Nachricht an die gehostete Quarantäne zuzustellen**): 30 Tage. Dieser Wert kann nicht geändert werden.

  - Nachrichten, die Schadsoftware enthalten: 15 Tage.

  Wenn eine Nachricht aus der Quarantäne abläuft, können Sie Sie nicht wiederherstellen.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Verwenden des Security & Compliance Center zum Verwalten von e-Mail-Nachrichten in Quarantäne

### <a name="view-quarantined-email"></a>Anzeigen von e-Mails in Quarantäne

1. Wechseln Sie im Security and Compliance Center zu **Threat Management** \> **Review** \> **Quarantine**.

2. Stellen Sie sicher, dass die **Ansicht isoliert** auf den Standardwert **e-Mail**festgelegt ist.

3. Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken. Klicken Sie auf **Spalten ändern** , um maximal sieben Spalten anzuzeigen. Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:

   - **Empfangen**<sup>\*</sup>

   - **Absender**<sup>\*</sup>

   - **Betreff**<sup>\*</sup>

   - **Quarantäne Grund**<sup>\*</sup>

   - **Veröffentlicht?**<sup>\*</sup>

   - **Richtlinientyp**<sup>\*</sup>

   - **Abläuft**<sup>\*</sup>

   - **Empfänger**

   - **Nachrichten-ID**

   - **Richtlinienname**

   - **Size**

   - **Direction**

   Wenn Sie fertig sind, klicken Sie auf **Speichern**, oder klicken Sie auf **auf Standard festlegen**.

4. Klicken Sie auf **Filter**, um die Ergebnisse zu filtern. Die verfügbaren Filter sind:

   - **Expires Time**: Filtern von Nachrichten nach Ablauf der Quarantäne:

     - **Heute**

     - **Nächste 2 Tage**

     - **Nächste 7 Tage**

     - **Benutzerdefiniert**: Geben Sie ein **Start** -und **Enddatum**ein.

   - **Empfangszeit**: Geben Sie ein **Start** -und **Enddatum**ein.

   - **Quarantäne Grund**:

     - **Richtlinie**: die Nachricht stimmte mit den Bedingungen einer Nachrichtenfluss Regel überein (auch als Transportregel bezeichnet).

     - **Bulk**

     - **Phishingfilterrichtlinie**

     - **Schadsoftware**

     - **Spam**

     - **Phishing mit hoher Zuverlässigkeit**

   - **E-Mail-Empfänger**: alle Benutzer oder nur an Sie gesendete Nachrichten. Endbenutzer können nur isolierte Nachrichten verwalten, die an Sie gesendet werden.

   Klicken Sie auf **Löschen**, um den Filter zu löschen. Zum Ausblenden des Filter Flyouts klicken Sie erneut auf **Filtern** .

5. Verwenden Sie **Sortierergebnisse nach** (die Schaltfläche **Nachrichten-ID** standardmäßig) und einen entsprechenden Wert, um nach bestimmten Nachrichten zu suchen. Platzhalter werden nicht unterstützt. Sie können anhand der folgenden Werte suchen:

   - Nach **richten-ID**: die global eindeutige ID der Nachricht.

        Beispielsweise haben Sie die [Nachrichtenablaufverfolgung](message-trace-scc.md) verwendet, um nach einer Nachricht zu suchen, die an einen Benutzer in Ihrer Organisation gesendet wurde, und Sie bestimmen, dass die Nachricht in Quarantäne statt übermittelt wurde. Achten Sie darauf, den vollständigen Meldungs-ID-Wert einzuschließen, der\<\>möglicherweise spitzen Klammern () enthält. Zum Beispiel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **Absender-e-Mail-Adresse**: e-Mail-Adresse eines einzelnen Absenders.

   - **Empfänger-e-Mail-Adresse**: die e-Mail-Adresse eines einzelnen Empfängers.

   - **Betreff**: Verwenden Sie den gesamten Betreff der Nachricht. Bei der Suche wird die Groß-/Kleinschreibung nicht beachtet.

   Nachdem Sie die Suchkriterien eingegeben haben, klicken ![Sie auf](../media/scc-quarantine-refresh.png) Aktualisieren Schaltfläche **Aktualisieren** , um die Ergebnisse zu filtern.

Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Aktionen dafür durchführen zu lassen (beispielsweise anzeigen, freigeben, herunterladen oder Löschen der Nachricht).

#### <a name="export-message-results"></a>Exportieren von Nachrichten Ergebnissen

1. Wählen Sie die Nachrichten aus, für die Sie sich interessieren, und klicken Sie auf **Ergebnisse exportieren**.

2. Klicken Sie in der Bestätigungsmeldung auf **Ja** , um zu warnen, dass das Browserfenster geöffnet bleibt.

3. Wenn der Export abgeschlossen ist, können Sie den Downloadspeicherort für die CSV-Datei benennen und auswählen.

#### <a name="view-quarantined-message-details"></a>Anzeigen von Details für isolierte Nachrichten

Wenn Sie eine e-Mail-Nachricht in der Liste auswählen, werden im **Detail** -Flyout-Bereich die folgenden Nachrichtendetails angezeigt:

- Nach **richten-ID**: der Global eindeutige Bezeichner für die Nachricht.

- **Absenderadresse**

- **Received**: das Datum/die Uhrzeit, zu der die Nachricht empfangen wurde.

- **Betreff**

- **Quarantäne Grund**: zeigt an, ob eine Nachricht als **Spam**, **Massen**, **Phishing**, Übereinstimmung mit einer Nachrichtenfluss Regel (**Transport Regel**) identifiziert wurde oder als enthaltender **Schadsoftware**erkannt wurde.

- **Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Nachricht** anzeigen oder **Nachrichtenkopfzeile anzeigen** klicken, um die vollständige Liste der Empfänger anzuzeigen.

- **Expires**: das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.

- **Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.

- **Noch nicht freigegeben an**: alle e-Mail-Adressen (falls vorhanden), für die die Nachricht noch nicht freigegeben wurde.

### <a name="take-action-on-quarantined-email"></a>Aktion für in Quarantäne versehene e-Mails ausführen

Nachdem Sie eine Nachricht ausgewählt haben, haben Sie mehrere Möglichkeiten, mit den Nachrichten im **Detail** -Flyout-Bereich zu tun:

- **Nachricht freigeben**: Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:

  - **Melden von Nachrichten an Microsoft zur Analyse**: diese Option ist standardmäßig aktiviert und meldet die irrtümlich unter Quarantäne gestellte Nachricht an Microsoft als falsch positiv. Wenn die Nachricht als Spam, Massen, Phishing oder mit Schadsoftware isoliert wurde, wird die Nachricht auch an das Microsoft-Spam Analyse Team gemeldet. Je nach Analyse können die Dienst weiten spamfilterregeln so angepasst werden, dass die Nachricht durchlassen wird.

  - Wählen Sie eine der folgenden Optionen aus:

    - **Freigeben von Nachrichten für alle Empfänger**

    - **Freigeben von Nachrichten an bestimmte Empfänger**

    - **Freigeben von Nachrichten für andere Personen**

  Wenn Sie fertig sind, klicken Sie auf **Nachrichten freigeben**.

  Hinweise zum Freigeben von Nachrichten:

  - Sie können eine Nachricht nur einmal an denselben Empfänger freigeben.

  - Nur Empfänger, die die Nachricht nicht erhalten haben, werden in der Liste der potenziellen Empfänger angezeigt.

- **Nachrichtenkopfzeile anzeigen**: Wählen Sie diesen Link aus, um den Text der Nachrichtenkopfzeile anzuzeigen. Um die Kopfzeilenfelder und-Werte eingehend zu analysieren, kopieren Sie den Text der Nachrichtenkopfzeile in die Zwischenablage, und wählen Sie dann **Microsoft Message Header Analyzer** aus, um zur Remote Verbindungs Untersuchung zu wechseln (Klicken Sie mit der rechten Maustaste, und wählen Sie **in einer neuen Registerkarte öffnen** aus, wenn Sie Office 365 nicht verlassen möchten). Fügen Sie die Kopfzeile der Nachricht auf der Seite im Abschnitt Nachrichtenkopf Analyse ein, und wählen Sie **Kopfzeilen analysieren**aus:

- **Vorschau Nachricht**: Wählen Sie im eingeblendeten Flyout-Bereich eine der folgenden Optionen aus:

  - **Quellansicht**: zeigt die HTML-Version des Nachrichtentexts an, für den alle Links deaktiviert sind.
  
  - **Text Ansicht**: zeigt den Nachrichtentext im nur-Text-Format an.

- **Aus Quarantäne entfernen**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.

- **Nachricht herunterladen**: Wählen Sie im Flyout-Bereich, der angezeigt wird, **die Risiken vom Herunterladen dieser Nachricht aus** , um eine lokale Kopie der Nachricht im eml-Format zu speichern.

- **Nachricht übermitteln**: Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:

  - **Objekttyp**: **e-Mail** (Standard), **URL**oder **Anlage**.

  - **Übermittlungs Format**: **Netzwerknachrichten-ID** (Standard, mit dem entsprechenden Wert im Feld **Netzwerknachrichten-ID** ) oder **Datei** (wechseln Sie zu einer lokalen eml-oder msg-Datei). Beachten Sie Folgendes: Wenn Sie **Datei** auswählen und dann **Netzwerknachrichten-ID**auswählen, ist der anfängliche Wert nicht mehr vorhanden.

  - **Recipients**: Geben Sie bei Lease einen ursprünglichen Empfänger der Nachricht ein, oder klicken Sie auf **Alles auswählen** , um alle Empfänger zu identifizieren. Sie können auch auf **Alle auswählen** klicken und dann einzelne Empfänger selektiv entfernen.

  - **Grund für die Übermittlung**: **sollte nicht blockiert worden sein** (Standard) oder hätte **blockiert werden**müssen.

  Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.

Wenn Sie die Nachricht nicht freigeben oder entfernen, wird Sie nach Ablauf der standardmäßigen Aufbewahrungszeit für Quarantäne gelöscht.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Ausführen von Aktionen in mehreren isolierten e-Mail-Nachrichten

Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), wird der Flyout-Bereich **Massenaktionen** angezeigt, in dem Sie die folgenden Aktionen ausführen können:

- **Release-Nachrichten**: die Optionen sind identisch mit denen, wenn Sie eine einzelne Nachricht freigeben, es sei denn, Sie können keine **Nachrichten für bestimmte Empfänger**auswählen. Sie können nur **Release-Nachricht für alle Empfänger** auswählen oder **Nachrichten an andere Personen freigeben**.

- **Löschen von Nachrichten**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.

Wenn Sie fertig sind, klicken Sie auf **Schließen**.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Nur ATP: Verwenden Sie das Security & Compliance Center, um isolierte Dateien zu verwalten.

> [!NOTE]
> Die Verfahren für in Quarantäne befindliche Dateien in diesem Abschnitt stehen nur für ATP-Plan 1-und Plan 2-Abonnenten zur Verfügung.

In Organisationen mit ATP können Administratoren isolierte Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams verwalten.

### <a name="view-quarantined-files"></a>Anzeigen von isolierten Dateien

1. Wechseln Sie im Security and Compliance Center zu **Threat Management** \> **Review** \> **Quarantine**.

2. Ändern Sie die Ansicht in den Standardwert **Dateien**unter **Quarantäne** . Sie können nach einem Feld sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.

3. Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken. Klicken Sie auf **Spalten ändern** , um maximal sieben Spalten anzuzeigen. Die Standardspalten sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:

   - **Benutzer**<sup>\*</sup>

   - **Speicherort**<sup>\*</sup>

   - **Dateiname**<sup>\*</sup>

   - **Datei-URL**<sup>\*</sup>

   - **Dateigröße**<sup>\*</sup>

   - **Abläuft**<sup>\*</sup>

   - **Veröffentlicht?**<sup>\*</sup>

   - **Erkannt von**

   - **Geändert von Zeit**

4. Klicken Sie auf **Filter**, um die Ergebnisse zu filtern. Die verfügbaren Filter sind:

   - **Expires Time**: Filtern von Nachrichten nach Ablauf der Quarantäne:

     - **Heute**

     - **Nächste 2 Tage**

     - **Nächste 7 Tage**

     - Ein benutzerdefiniertes Datum/Zeitintervall.

   - **Empfangszeit**

   - **Quarantäne Grund**: der einzige verfügbare Wert ist **Schadsoftware**.

Nachdem Sie eine bestimmte isolierte Datei gefunden haben, wählen Sie die Datei aus, um Details dazu anzuzeigen, und nehmen Sie Aktionen vor (beispielsweise anzeigen, freigeben, herunterladen oder Löschen der Nachricht).

#### <a name="export-file-results"></a>Exportieren von Datei Ergebnissen

1. Wählen Sie die Dateien aus, für die Sie sich interessieren, und klicken Sie auf **Ergebnisse exportieren**.

2. Klicken Sie in der Bestätigungsmeldung auf **Ja** , um zu warnen, dass das Browserfenster geöffnet bleibt.

3. Wenn der Export abgeschlossen ist, können Sie den Downloadspeicherort für die CSV-Datei benennen und auswählen.

#### <a name="view-quarantined-file-details"></a>Anzeigen von Details in isolierten Dateien

Wenn Sie eine Datei in der Liste auswählen, werden im **Detail** -Flyout-Bereich die folgenden Dateidetails angezeigt:

- **Dateiname**

- **Datei-URL**: URL, die den Speicherort der Datei definiert (beispielsweise in SharePoint Online).

- **Böswilliger Inhalt erkannt in** Das Datum/die Uhrzeit, zu dem die Datei isoliert wurde.

- **Expires**: das Datum, an dem die Datei aus der Quarantäne gelöscht wird.

- **Erkannt von**: ATP (Advanced Threat Protection) oder Microsofts Anti-Malware Engine.

- **Veröffentlicht?**

- **Name der Schadsoftware**

- **Dokument-ID**: ein eindeutiger Bezeichner für das Dokument.

- **Dateigröße**: in Kilobyte (KB).

- **Organisation** Die eindeutige ID Ihrer Organisation.

- **Zuletzt geändert**

- **Geändert von**: der Benutzer, der die Datei zuletzt geändert hat.

- **Secure Hash Algorithm 256-Bit (SHA-256)-Wert**: Sie können diesen Hashwert verwenden, um die Datei in anderen Reputation Stores oder an anderen Speicherorten in Ihrer Umgebung zu identifizieren.

### <a name="take-action-on-quarantined-files"></a>Ausführen von Aktionen für isolierte Dateien

Wenn Sie eine Datei in der Liste auswählen, können Sie die folgenden Aktionen für die Datei im **Detail** -Flyout-Bereich ausführen:

- **Dateien freigeben**: Wählen Sie (Standard) aus, oder heben Sie **die Auswahl von Berichtsdateien für Microsoft für die Analyse auf**, und klicken Sie dann auf **Dateien freigeben**.

- **Datei herunterladen**

- **Datei aus Quarantäne entfernen**

Wenn Sie die Dateien nicht freigeben oder entfernen, werden Sie nach Ablauf der standardmäßigen Aufbewahrungszeit für Quarantäne gelöscht.

#### <a name="actions-on-multiple-quarantined-files"></a>Aktionen für mehrere isolierte Dateien

Wenn Sie mehrere isolierte Dateien in der Liste auswählen (bis zu 100), wird der Flyout-Bereich **Massenaktionen** angezeigt, in dem Sie die folgenden Aktionen ausführen können:

- **Veröffentlichungsdateien**

- **Dateien löschen**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, werden die Dateien sofort gelöscht.

Wenn Sie fertig sind, klicken Sie auf **Schließen**.

## <a name="use-exchange-online-powershell-or-standalone-exchange-online-protection-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Verwenden Exchange Online PowerShell oder eigenständiger Exchange Online Protection PowerShell zum Anzeigen und Verwalten von isolierten Nachrichten und Dateien

Folgende Cmdlets werden zum Anzeigen und Verwalten von Nachrichten und Dateien in der Quarantäne verwendet:

- [DELETE-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-quarantinemessage)

- [Vorschau-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/preview-quarantinemessage): Beachten Sie, dass dieses Cmdlet nur für Nachrichten gilt, nicht für Malware Dateien von ATP für SharePoint Online, OneDrive für Unternehmen oder Teams.

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/release-quarantinemessage)
