---
title: Verwalten von Nachrichten und Dateien in Quarantäne als Administrator
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: 065cc2cf-2f3a-47fd-a434-2a20b8f51d0c
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: Administratoren erfahren, wie Sie isolierte Nachrichten für alle Benutzer in Exchange Online Protection (EoP) anzeigen und verwalten können. Administratoren in Organisationen mit Office 365 Advanced Threat Protection (Office 365 ATP) können auch unter Quarantäne gestellte Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams verwalten.
ms.openlocfilehash: 7e9b49e7e7a90f5271a65bb26cecdd1a7ce2ab84
ms.sourcegitcommit: 260c69fa31a898428d51cfdbd762c5f0213c403c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/10/2020
ms.locfileid: "48417223"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten. Weitere Informationen finden Sie unter [Quarantäne-e-Mail-Nachrichten in EoP](quarantine-email-messages.md).

Administratoren können alle Arten von isolierten Nachrichten für alle Benutzer anzeigen, freigeben und löschen. Nur Administratoren können Nachrichten verwalten, die als Schadsoftware, als hochgradig vertrauenswürdiges Phishing oder als Ergebnis von Nachrichtenfluss Regeln (auch bekannt als Transportregeln) isoliert wurden. Administratoren können auch falsch positive Ergebnisse an Microsoft melden.

Administratoren in Organisationen mit Office 365 Advance Threat Protection (Office 365 ATP) können unter Quarantäne gestellte Dateien auch in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams anzeigen, herunterladen und löschen.

Sie können isolierte Nachrichten im Security & Compliance Center oder in PowerShell anzeigen und verwalten (Exchange Online PowerShell für Microsoft 365-Organisationen mit Postfächern in Exchange Online; eigenständige EoP PowerShell für Organisationen ohne Exchange Online Postfächer).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Zum Öffnen des Security & Compliance Centers wechseln Sie zu <https://protection.office.com>. Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://protection.office.com/quarantine>.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen Berechtigungen zugewiesen haben, bevor Sie die Quarantäne als Administrator verwalten können. Die Berechtigungen werden durch die **Quarantäne** Rolle im Security & Compliance Center gesteuert. Diese Rolle wird standardmäßig der Rollengruppe **Organisationsverwaltung** (Global Admins), **Quarantine Administrator**und **Sicherheitsadministrator** im Security & Compliance Center zugewiesen. Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

- Isolierte Nachrichten werden für einen Standardzeitraum aufbewahrt, bevor Sie automatisch gelöscht werden:

  - Nachrichten, die von antispamregeln (Spam, Phishing und Massen-e-Mails) unter Quarantäne gestellt werden: 30 Tage. Dies ist der Standard-und Höchstwert. Informationen zum Konfigurieren dieses Werts finden Sie unter [configure Anti-Spam Policies](configure-your-spam-filter-policies.md).

  - Nachrichten, die Schadsoftware enthalten: 15 Tage.

  Wenn eine Nachricht aus der Quarantäne abläuft, können Sie Sie nicht wiederherstellen.

## <a name="use-the-security--compliance-center-to-manage-quarantined-email-messages"></a>Verwenden des Security & Compliance Center zum Verwalten von e-Mail-Nachrichten in Quarantäne

### <a name="view-quarantined-email"></a>Anzeigen von e-Mails in Quarantäne

1. Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.

2. Stellen Sie sicher, dass **Quarantäne anzeigen** auf den Standardwert **E-Mail** festgelegt ist.

3. Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken. Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen. Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:

   - **Empfangen**<sup>\*</sup>
   - **Absender**<sup>\*</sup>
   - **Betreff**<sup>\*</sup>
   - **Quarantänegrund**<sup>\*</sup>
   - **Veröffentlicht?**<sup>\*</sup>
   - **Richtlinientyp**<sup>\*</sup>
   - **Empfänger**
   - **Nachrichten-ID**
   - **Name der Richtlinie**
   - **Größe**
   - **Richtung**

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**, oder klicken Sie auf **Als Standard festlegen**.

4. Klicken Sie auf **Filter**, um die Ergebnisse zu filtern. Die verfügbaren Filter sind:

   - **Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:
     - **Heute**
     - **Nächste 2 Tage**
     - **Nächste 7 Tage**
     - **Benutzerdefiniert**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.

   - **Empfangszeit**: Geben Sie ein **Anfangsdatum** und **Enddatum** ein.

   - **Quarantänegrund**:
     - **Richtlinie**: die Nachricht stimmte mit den Bedingungen einer Nachrichtenfluss Regel überein (auch als Transportregel bezeichnet).
     - **Massensendung**
     - **Phishing**: das Spamfilter Urteil lautete, dass die Nachricht durch **Phishing-e-Mails** oder Anti-Phishing-schutzisoliert wurde ([Spoof-Einstellungen](set-up-anti-phishing-policies.md#spoof-settings) oder [Identitätswechsel Schutz](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)).
     - **Schadsoftware**
     - **Spam**
     - **Phishing mit hoher Zuverlässigkeit**

   - **E-Mail-Empfänger**: alle Benutzer oder nur an Sie gesendete Nachrichten. Endbenutzer können nur isolierte Nachrichten verwalten, die an Sie gesendet werden.

   Klicken Sie auf **Löschen**, um den Filter zu löschen. Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.

5. Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID**) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden. Platzhalter werden nicht unterstützt. Sie können nach den folgenden Werten suchen:

   - **Nachrichten-ID**: Die globale eindeutige ID der Nachricht.

     Beispielsweise haben Sie die [Nachrichtenablaufverfolgung](message-trace-scc.md) verwendet, um nach einer Nachricht zu suchen, die an einen Benutzer in Ihrer Organisation gesendet wurde, und Sie bestimmen, dass die Nachricht in Quarantäne statt übermittelt wurde. Achten Sie darauf, den vollständigen Meldungs-ID-Wert einzuschließen, der möglicherweise spitzen Klammern ( \<\> ) enthält. Zum Beispiel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **E-Mail-Adresse des Absenders**: Die E-Mail-Adresse eines einzelnen Absenders.

   - **E-Mail-Adresse des Empfängers**: Die E-Mail-Adresse eines einzelnen Empfängers.

   - **Betreff**: Verwenden Sie den gesamten Betreff der Nachricht. Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.

   Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../../media/scc-quarantine-refresh.png) **Aktualisieren**, um die Ergebnisse zu filtern.

Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).

#### <a name="export-message-results"></a>Nachrichtenergebnisse exportieren

1. Wählen Sie die gewünschten Nachrichten aus, und klicken Sie auf **Ergebnisse exportieren**.

2. Klicken Sie auf **Ja** in der Bestätigungsnachricht, die Sie warnt, das Browserfenster geöffnet zu lassen.

3. Wenn Ihr Export fertig ist, können Sie den Speicherort für die .csv-Datei benennen und auswählen.

#### <a name="view-quarantined-message-details"></a>Anzeigen von Details der isolierten Nachricht

Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, werden die folgenden Nachrichtendetails im Flyout-Fenster **Details** angezeigt:

- **Nachrichten-ID**: Die globale eindeutige ID für die Nachricht.

- **Absenderadresse**

- **Empfangen**: Das Datum/die Uhrzeit des Nachrichtenempfangs.

- **Betreff**

- **Quarantäne Grund**: zeigt an, ob eine Nachricht als **Spam**, **Massen**, **Phishing**, Übereinstimmung mit einer Nachrichtenfluss Regel (**Transport Regel**) identifiziert wurde oder als enthaltender **Schadsoftware**erkannt wurde.

- **Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.

- **Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.

- **Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.

- **Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.

### <a name="take-action-on-quarantined-email"></a>Maßnahmen für isolierte E-Mails ergreifen

Nachdem Sie eine Nachricht ausgewählt haben, haben Sie mehrere Möglichkeiten, mit den Nachrichten im **Detail** -Flyout-Bereich zu tun:

- **Nachricht freigeben**: Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:

  - **Melden von Nachrichten an Microsoft zur Analyse**: diese Option ist standardmäßig aktiviert und meldet die irrtümlich unter Quarantäne gestellte Nachricht an Microsoft als falsch positiv. Wenn die Nachricht als Spam, Massen, Phishing oder mit Schadsoftware isoliert wurde, wird die Nachricht auch an das Microsoft-Spam Analyse Team gemeldet. Je nach Analyse können die Dienst weiten spamfilterregeln so angepasst werden, dass die Nachricht durchlassen wird.

  - Wählen Sie eine der folgenden Optionen aus:
    - **Freigeben von Nachrichten für alle Empfänger**
    - **Freigeben von Nachrichten an bestimmte Empfänger**
    - **Freigeben von Nachrichten für andere Personen**

  Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.

  Hinweise zum Freigeben von Nachrichten:

  - Sie können eine Nachricht nur einmal an denselben Empfänger freigeben.

  - Nur Empfänger, die die Nachricht nicht erhalten haben, werden in der Liste der potenziellen Empfänger angezeigt.

- **Nachrichtenkopf anzeigen**: Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen. Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Microsoft 365 nicht verlassen möchten, um die Aufgabe auszuführen). Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:

- **Vorschau der Nachricht anzeigen**: Wählen Sie im angezeigten Flyout-Fenster eine der folgenden Optionen:

  - **Quellansicht**: Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.
  - **Textansicht**: Zeigt den Nachrichtentext im Klartext an.

- **Aus Quarantäne entfernen**: Nachdem Sie in der angezeigten Warnmeldung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.

- **Nachricht herunterladen**: Wählen Sie im daraufhin angezeigten Flyout-Fenster **Ich verstehe die Risiken beim Herunterladen dieser Nachricht** aus, um eine lokale Kopie der Nachricht im eml-Format zu speichern.

- **Nachricht übermitteln**: Wählen Sie im eingeblendeten Flyout-Bereich die folgenden Optionen aus:

  - **Objekttyp**: **e-Mail** (Standard), **URL**oder **Anlage**.

  - **Übermittlungs Format**: **Netzwerknachrichten-ID** (Standard, mit dem entsprechenden Wert im Feld **Netzwerknachrichten-ID** ) oder **Datei** (wechseln Sie zu einer lokalen eml-oder msg-Datei). Beachten Sie Folgendes: Wenn Sie **Datei** auswählen und dann **Netzwerknachrichten-ID**auswählen, ist der anfängliche Wert nicht mehr vorhanden.

  - **Recipients**: Geben Sie bei Lease einen ursprünglichen Empfänger der Nachricht ein, oder klicken Sie auf **Alles auswählen** , um alle Empfänger zu identifizieren. Sie können auch auf **Alle auswählen** klicken und dann einzelne Empfänger selektiv entfernen.

  - **Grund für die Übermittlung**: **sollte nicht blockiert worden sein** (Standard) oder hätte **blockiert werden**müssen.

  Wenn Sie fertig sind, klicken Sie auf über **Mitteln**.

Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen

Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), erscheint das Flyout-Fenster **Massenaktionen**, in dem Sie die folgenden Aktionen durchführen können:

- **Nachrichten freigeben**: Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.

  > [!NOTE]
  > Nehmen Sie das folgende Szenario in Frage: John@gmail.com sendet eine Nachricht an Faith@contoso.com und John@Subsidiary.contoso.com. Gmail verzweigt diese Nachricht in zwei Kopien, die an die Quarantäne als Phishing in Microsoft weitergeleitet werden. Ein Administrator gibt beide Nachrichten an admin@contoso.com frei. Die erste freigegebene Nachricht, die das Administratorpostfach erreicht, wird übermittelt. Die zweite freigegebene Nachricht wird als doppelte Zustellung identifiziert und übersprungen. Nachricht werden als Duplikate identifiziert, wenn Sie dieselbe Nachrichten-ID und dieselbe Empfangszeit haben.

- **Nachrichten löschen**: Nachdem Sie in der angezeigten Warnung auf **Ja** klicken, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.

Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="atp-only-use-the-security--compliance-center-to-manage-quarantined-files"></a>Nur ATP: Verwenden Sie das Security & Compliance Center, um isolierte Dateien zu verwalten.

> [!NOTE]
> Die Verfahren für in Quarantäne befindliche Dateien in diesem Abschnitt stehen nur für ATP-Plan 1-und Plan 2-Abonnenten zur Verfügung.

In Organisationen mit ATP können Administratoren isolierte Dateien in SharePoint Online, OneDrive für Unternehmen und Microsoft Teams verwalten.

### <a name="view-quarantined-files"></a>Anzeigen von isolierten Dateien

1. Wechseln Sie im Security and Compliance Center zu **Bedrohungsmanagement** \> **Überprüfung** \> **Quarantäne**.

2. Ändern Sie die Ansicht in den Standardwert **Dateien**unter **Quarantäne** . Sie können nach einem Feld sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.

3. Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken. Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen. Die Standardspalten sind mit einem Sternchen ( <sup>\*</sup> ) gekennzeichnet:

   - **Benutzer**<sup>\*</sup>
   - **Speicherort**<sup>\*</sup>
   - **Dateiname**<sup>\*</sup>
   - **Datei-URL**<sup>\*</sup>
   - **Dateigröße**<sup>\*</sup>
   - **Läuft ab**<sup>\*</sup>
   - **Veröffentlicht?**<sup>\*</sup>
   - **Erkannt von**
   - **Geändert von Zeit**

4. Klicken Sie auf **Filter**, um die Ergebnisse zu filtern. Die verfügbaren Filter sind:

   - **Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:
     - **Heute**
     - **Nächste 2 Tage**
     - **Nächste 7 Tage**
     - Ein benutzerdefiniertes Datum/Zeitintervall.
   - **Empfangszeit**
   - **Quarantäne Grund**: der einzige verfügbare Wert ist **Schadsoftware**.

Nachdem Sie eine bestimmte isolierte Datei gefunden haben, wählen Sie die Datei aus, um Details dazu anzuzeigen, und nehmen Sie Aktionen vor (beispielsweise anzeigen, freigeben, herunterladen oder Löschen der Nachricht).

#### <a name="export-file-results"></a>Exportieren von Datei Ergebnissen

1. Wählen Sie die Dateien aus, für die Sie sich interessieren, und klicken Sie auf **Ergebnisse exportieren**.

2. Klicken Sie auf **Ja** in der Bestätigungsnachricht, die Sie warnt, das Browserfenster geöffnet zu lassen.

3. Wenn Ihr Export fertig ist, können Sie den Speicherort für die .csv-Datei benennen und auswählen.

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

1. Melden Sie sich mit einem Arbeits-oder Schulkonto mit globalen Administratorrechten (oder geeigneten Sicherheits & Compliance Center-Rollen) in Ihrer Organisation an, und [wechseln Sie zum Security & Compliance Center](../../compliance/go-to-the-securitycompliance-center.md).

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Verwenden Exchange Online PowerShell oder eigenständiger EoP PowerShell zum Anzeigen und Verwalten von isolierten Nachrichten und Dateien

Folgende Cmdlets werden zum Anzeigen und Verwalten von Nachrichten und Dateien in der Quarantäne verwendet:

- [DELETE-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/get-quarantinemessage)

- [Vorschau-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/preview-quarantinemessage): Beachten Sie, dass dieses Cmdlet nur für Nachrichten gilt, nicht für Malware Dateien von ATP für SharePoint Online, OneDrive für Unternehmen oder Teams.

- [Release-QuarantineMessage](https://docs.microsoft.com/powershell/module/exchange/release-quarantinemessage)
