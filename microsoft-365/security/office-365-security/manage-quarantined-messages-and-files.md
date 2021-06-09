---
title: Verwalten von Nachrichten und Dateien in Quarantäne als Administrator
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
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
description: Administratoren können erfahren, wie sie isolierte Nachrichten für alle Benutzer in Exchange Online Protection (EOP) anzeigen und verwalten. Administratoren in Organisationen mit Microsoft Defender für Office 365 können auch isolierte Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams verwalten.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 7b484cc3a8462115b5151b34ba93ba0c041e16b4
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52822298"
---
# <a name="manage-quarantined-messages-and-files-as-an-admin-in-eop"></a>Verwalten von isolierten Nachrichten und Dateien als Administrator in EOP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In Microsoft 365-Organisationen mit Postfächern in Exchange Online oder in eigenständigen Exchange Online Protection (EOP)-Organisationen ohne Exchange Online-Postfächer, enthält die Quarantäne potenziell gefährliche oder unerwünschte Nachrichten. Weitere Informationen finden Sie unter [Quarantäne gestellte E-Mail-Nachrichten in EOP.](quarantine-email-messages.md)

Administratoren können alle Arten von isolierten Nachrichten für alle Benutzer anzeigen, freigeben und löschen. Nur Administratoren können Nachrichten verwalten, die als Schadsoftware, Phishing mit hohem Vertrauen oder als Folge von Nachrichtenflussregeln (auch als Transportregeln bezeichnet) isoliert wurden. Administratoren können auch falsch positive Ergebnisse an Microsoft melden.

Administratoren in Organisationen mit Microsoft Defender für Office 365 können auch isolierte Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams anzeigen, herunterladen und löschen.

Sie können isolierte Nachrichten im Microsoft 365 Security Center oder in PowerShell anzeigen und verwalten (Exchange Online PowerShell für Microsoft 365 Organisationen mit Postfächern in Exchange Online; eigenständige EOP PowerShell für Organisationen ohne Exchange Online Postfächer).

## <a name="what-do-you-need-to-know-before-you-begin"></a>Was sollten Sie wissen, bevor Sie beginnen?

- Um das Sicherheitscenter zu öffnen, wechseln Sie zu <https://security.microsoft.com> . Um die Quarantäne-Seite direkt zu öffnen, wechseln Sie zu <https://security.microsoft.com/quarantine>.

- Wie Sie eine Verbindung mit Exchange Online PowerShell herstellen, finden Sie unter [Herstellen einer Verbindung mit Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell). Informationen zum Herstellen einer Verbindung mit dem eigenständigen Exchange Online Protection PowerShell finden Sie unter [Verbinden mit PowerShell in Exchange Online Protection](/powershell/exchange/connect-to-exchange-online-protection-powershell).

- Sie müssen in **Exchange Online** Berechtigungen erhalten, bevor Sie die in diesem Artikel beschriebenen Schritte ausführen können:
  - Um Maßnahmen gegen isolierte Nachrichten für alle Benutzer zu ergreifen, müssen Sie Mitglied der Rollengruppen **"Organisationsverwaltung",** **"Sicherheitsadministrator"** oder **"Quarantäneadministrator"** <sup>\*</sup> sein.
  - Für den schreibgeschützten Zugriff auf isolierte Nachrichten für alle Benutzer müssen Sie Mitglied der Rollengruppe **"Globaler Leser"** oder **"Sicherheitsleseberechtigter"** sein.

  Weitere Informationen finden Sie unter [Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo).

  **Hinweise**:

  - Durch Hinzufügen von Benutzern zur entsprechenden Azure Active Directory-Rolle im Microsoft 365 Admin Center erhalten Benutzer die erforderlichen Berechtigungen _und_ Berechtigungen für andere Features in Microsoft 365. Weitere Informationen finden Sie unter [Informationen zu Administratorrollen](../../admin/add-users/about-admin-roles.md).
  - Die Rollengruppe **Organisationsverwaltung mit Leserechten** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) ermöglicht auch einen schreibgeschützten Zugriff auf das Feature.
  - <sup>\*</sup>Mitglieder der **Rollengruppe "Quarantäneadministrator"** müssen auch Mitglieder der Rollengruppe **"Hygieneverwaltung"** in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) sein, um Quarantäneverfahren in Exchange Online PowerShell durchzuführen.

- Isolierte Nachrichten werden für einen Standardzeitraum aufbewahrt, bevor sie automatisch gelöscht werden:
  - 30 Tage für Nachrichten, die durch Antispamrichtlinien (Spam, Phishing und Massen-E-Mails) isoliert wurden. Dies ist der Standard- und Maximalwert. Informationen zum Konfigurieren (niedriger) dieses Werts finden Sie unter [Konfigurieren von Antispamrichtlinien.](configure-your-spam-filter-policies.md)
  - 15 Tage für Nachrichten, die Schadsoftware enthalten.
  - 15 Tage für Dateien, die von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams in Defender für Office 365 isoliert wurden.

  Wenn eine Nachricht aus der Quarantäne abläuft, können Sie sie nicht wiederherstellen.

## <a name="use-the-security-center-to-manage-quarantined-email-messages"></a>Verwenden des Sicherheitscenters zum Verwalten von isolierten E-Mail-Nachrichten

### <a name="view-quarantined-email"></a>Anzeigen von isolierten E-Mails

1. Wechseln Sie im Security Center zu **E-Mail &** \> **Zusammenarbeitsüberprüfungsquarantäne.** \> 

2. Überprüfen Sie auf der **Seite "Quarantäne",** ob **"In Quarantäne befindliche Ansicht"** auf den Standardwert **"E-Mail"** festgelegt ist.

3. Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken. Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen. Die Standardwerte sind mit einem Sternchen (<sup>\*</sup>) gekennzeichnet:

   - **Empfangen**<sup>\*</sup>
   - **Absender**<sup>\*</sup>
   - **Betreff**<sup>\*</sup>
   - **Quarantänegrund**<sup>\*</sup>
   - **Veröffentlicht?**<sup>\*</sup>
   - **Richtlinientyp**<sup>\*</sup>
   - **Läuft ab**<sup>\*</sup>
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
     - **Richtlinie:** Die Nachricht stimmte mit den Bedingungen einer Nachrichtenflussregel überein (auch als Transportregel bezeichnet).
     - **Masse**
     - **Phishing:** Die Spamfilterbewertung **lautete Phishing-E-Mail** oder Antiphishingschutz isoliert die Nachricht ([Spoofingeinstellungen](set-up-anti-phishing-policies.md#spoof-settings) oder [Identitätswechselschutz](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)).
     - **Schadsoftware**
     - **Spam**
     - **Phishing mit hoher Konfidenz**
   - **Richtlinientyp**: Filtern von Nachrichten nach Richtlinientyp:
     - **Antischadsoftwarerichtlinie**
     - **Richtlinie für sichere Anlagen**
     - **Antiphishing-Richtlinie**
     - **Richtlinie für gehostete Inhaltsfilter** (Antispamrichtlinie)
     - **Transportregel**
   - **E-Mail-Empfänger:** Alle Benutzer oder nur Nachrichten, die an Sie gesendet werden. Endbenutzer können nur isolierte Nachrichten verwalten, die an sie gesendet werden.

   Klicken Sie auf **Löschen**, um den Filter zu löschen. Um das Filter-Flyout auszublenden, klicken Sie erneut auf **Filter**.

5. Verwenden Sie **Ergebnisse sortieren nach** (standardmäßig die Schaltfläche **Nachrichten-ID**) und einen entsprechenden Wert, um bestimmte Nachrichten zu finden. Platzhalter werden nicht unterstützt. Sie können nach den folgenden Werten suchen:
   - **Nachrichten-ID**: Die globale eindeutige ID der Nachricht.

     Beispielsweise haben Sie die [Nachrichtenablaufverfolgung](message-trace-scc.md) verwendet, um nach einer Nachricht zu suchen, die an einen Benutzer in Ihrer Organisation gesendet wurde, und Sie bestimmen, dass die Nachricht in Quarantäne anstatt zugestellt wurde. Achten Sie darauf, den vollständigen Nachrichten-ID-Wert einzuschließen, der spitze Klammern ( ) enthalten \<\> kann. Zum Beispiel: `<79239079-d95a-483a-aacf-e954f592a0f6@XYZPR00BM0200.contoso.com>`.

   - **E-Mail-Adresse des Absenders**: Die E-Mail-Adresse eines einzelnen Absenders.
   - **Richtlinienname**: Verwenden Sie den vollständigen Namen der Nachricht. Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.
   - **E-Mail-Adresse des Empfängers**: Die E-Mail-Adresse eines einzelnen Empfängers.
   - **Betreff**: Verwenden Sie den gesamten Betreff der Nachricht. Bei der Suche wird nicht zwischen Groß- und Kleinschreibung unterschieden.
   - **Richtlinienname:** Der Name der Richtlinie, die für die Quarantäne der Nachricht verantwortlich war.

   Nachdem Sie die Suchkriterien eingegeben haben, klicken Sie auf die ![Schaltfläche Aktualisieren](../../media/scc-quarantine-refresh.png) **Aktualisieren**, um die Ergebnisse zu filtern.

Nachdem Sie eine bestimmte isolierte Nachricht gefunden haben, wählen Sie die Nachricht aus, um Details dazu anzuzeigen und Maßnahmen zu ergreifen (z. B. die Nachricht anzeigen, freigeben, herunterladen oder löschen).

#### <a name="view-quarantined-message-details"></a>Anzeigen von Details der isolierten Nachricht

Wenn Sie eine E-Mail-Nachricht in der Liste auswählen, sind die folgenden Nachrichtendetails im angezeigten Detail-Flyout verfügbar:

- **Nachrichten-ID**: Die globale eindeutige ID für die Nachricht.
- **Absenderadresse**
- **Empfangen**: Das Datum/die Uhrzeit des Nachrichtenempfangs.
- **Betreff**
- **Quarantänegrund:** Zeigt an, ob eine Nachricht als **Spam,** **Massen-**, **Phishing-** oder Nachrichtenflussregel **(Transportregel)** identifiziert wurde oder als **schadsoftware** enthaltend identifiziert wurde.
- **Empfängeranzahl**
- **Empfänger**: Wenn die Nachricht mehrere Empfänger enthält, müssen Sie auf **Vorschau der Nachricht anzeigen** oder **Nachrichten** Kopfzeile anzeigen klicken, um die gesamte Liste der Empfänger anzuzeigen.
- **Läuft ab**. Das Datum/die Uhrzeit, zu der die Nachricht automatisch und dauerhaft aus der Quarantäne gelöscht wird.
- **Freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht freigegeben wurde.
- **Noch nicht freigegeben für**: Alle E-Mail-Adressen (sofern vorhanden), für die die Nachricht noch nicht freigegeben wurde.

### <a name="take-action-on-quarantined-email"></a>Maßnahmen für isolierte E-Mails ergreifen

Nachdem Sie eine Nachricht ausgewählt haben, haben Sie mehrere Optionen für die Aktionen mit den Nachrichten im Detail-Flyout:

- **Veröffentlichungsnachricht:** Wählen Sie im angezeigten Flyout die folgenden Optionen aus:
  - **Melden Sie Nachrichten an Microsoft zur Analyse:** Dies ist standardmäßig ausgewählt und meldet die fälschlicherweise isolierte Nachricht als falsch positives Ergebnis an Microsoft. Wenn die Nachricht als Spam, Massen-, Phishing- oder Schadsoftware isoliert wurde, wird die Nachricht auch an das Microsoft Spam Analysis Team gemeldet. Abhängig von ihrer Analyse können die dienstweiten Spamfilterregeln angepasst werden, um die Nachricht durchzulassen.
  - Wählen Sie eine der folgenden Optionen aus:
    - **Freigeben von Nachrichten an alle Empfänger**
    - **Freigeben von Nachrichten an bestimmte Empfänger**
    - **Nachrichten an andere Personen** freigeben: Beachten Sie, dass das Freigeben von Schadsoftwarenachrichten für andere Personen als die ursprünglichen Empfänger nicht unterstützt wird.

  Klicken Sie nach Abschluss des Vorgangs auf **Nachrichten freigeben**.

  Hinweise zum Freigeben von Nachrichten:

  - Sie können eine Nachricht nicht mehrmals an denselben Empfänger freigeben.
  - Nur Empfänger, die die Nachricht nicht erhalten haben, werden in der Liste der potenziellen Empfänger angezeigt.

- **Nachrichtenkopf anzeigen**: Wählen Sie diesen Link aus, um den Nachrichtenkopftext anzuzeigen. Um den Nachrichtenkopf im Detail zu analysieren, kopieren Sie den Nachrichtenkopftext in die Zwischenablage, und wählen Sie dann **Microsoft-Nachrichtenkopfanalyse** aus, um zur Remoteverbindungsuntersuchung zu wechseln (klicken Sie mit der rechten Maustaste, und wählen Sie **In neuer Registerkarte öffnen** aus, wenn Sie Microsoft 365 nicht verlassen möchten, um die Aufgabe auszuführen). Fügen Sie den Nachrichtenkopf auf der Seite in den Abschnitt "Nachrichtenkopfanalyse" ein, und wählen Sie dann **Kopfzeilen analysieren** aus:
- **Vorschaunachricht:** Wählen Sie im angezeigten Flyout eine der folgenden Optionen aus:
  - **Quellansicht**: Zeigt die HTML-Version des Nachrichtentextes an, wobei alle Links deaktiviert sind.
  - **Textansicht**: Zeigt den Nachrichtentext im Klartext an.
- **Aus Quarantäne entfernen:** Nachdem Sie in der angezeigten Warnung auf **"Ja"** geklickt haben, wird die Nachricht sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.
- **Nachricht herunterladen:** Wählen Sie im angezeigten Flyout **die Option "Ich kann die Risiken beim Herunterladen dieser Nachricht verstehen" aus,** um eine lokale Kopie der Nachricht im EML-Format zu speichern.
- **Absender blockieren**: Fügen Sie den Absender zur Liste blockierter Absender für Ihr Postfach hinzu. Weitere Informationen finden Sie unter [E-Mail-Absender blockieren](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4).
- **Nachricht senden:** Wählen Sie im angezeigten Flyout die folgenden Optionen aus:
  - **Objekttyp:** **E-Mail** (Standard), **URL** oder **Anlage**.
  - **Übermittlungsformat:** **Netzwerknachrichten-ID** (Standard, mit dem entsprechenden Wert im **Feld "Netzwerknachrichten-ID")** oder **Datei** (navigieren Sie zu einer lokalen EML- oder MSG-Datei). Beachten Sie: Wenn Sie **"Datei"** und dann **"Netzwerknachrichten-ID"** auswählen, ist der Ursprüngliche Wert weg.
  - **Empfänger:** Geben Sie bei Lease einen ursprünglichen Empfänger der Nachricht ein, oder klicken Sie auf **"Alle auswählen",** um alle Empfänger zu identifizieren. Sie können auch auf **"Alle auswählen"** klicken und dann einzelne Empfänger selektiv entfernen.
  - **Grund für die Übermittlung:** **Sollte nicht blockiert worden sein** (Standard) oder hätte blockiert werden **sollen.**

  Wenn Sie fertig sind, klicken Sie auf **"Absenden".**

Wenn Sie die Nachricht nicht freigeben oder entfernen, wird sie nach Ablauf der Standard-Quarantäneaufbewahrungszeit gelöscht.

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>Maßnahmen für mehrere isolierte E-Mail-Nachrichten ergreifen

Wenn Sie mehrere isolierte Nachrichten in der Liste auswählen (bis zu 100), wird das Flyout für **Massenaktionen** angezeigt, in dem Sie die folgenden Aktionen ausführen können:

- **Nachrichten freigeben**: Die Optionen sind die gleichen wie bei der Freigabe einer einzelnen Nachricht, außer dass Sie nicht **Nachrichten an bestimmte Empfänger freigeben** auswählen können; Sie können nur **Nachricht an alle Empfänger freigeben** oder **Nachrichten an andere Personen freigeben** auswählen.

  > [!NOTE]
  > Betrachten Sie das folgende Szenario: john@gmail.com sendet eine Nachricht an faith@contoso.com und john@subsidiary.contoso.com. Gmail verzweigt diese Nachricht in zwei Kopien, die beide als Phishing in Microsoft in quarantäne gestellt werden. Ein Administrator gibt beide Nachrichten an admin@contoso.com frei. Die erste veröffentlichte Nachricht, die das Administratorpostfach erreicht, wird zugestellt. Die zweite freigegebene Nachricht wird als doppelte Zustellung identifiziert und übersprungen. Nachrichten werden als Duplikate identifiziert, wenn sie die gleiche Nachrichten-ID und Empfangszeit haben.

- **Nachrichten löschen:** Nachdem Sie in der angezeigten Warnung auf **"Ja"** geklickt haben, werden die Nachrichten sofort gelöscht, ohne an die ursprünglichen Empfänger gesendet zu werden.

Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

## <a name="use-the-security-center-to-manage-quarantined-files-in-defender-for-office-365"></a>Verwenden des Sicherheitscenters zum Verwalten von isolierten Dateien in Defender für Office 365

> [!NOTE]
> Die Verfahren für isolierte Dateien in diesem Abschnitt sind nur für Abonnenten von Microsoft Defender für Office 365 Plan 1 und Plan 2 verfügbar.

In Organisationen mit Defender für Office 365 können Administratoren isolierte Dateien in SharePoint Online, OneDrive for Business und Microsoft Teams verwalten. Informationen zum Aktivieren des Schutzes für diese Dateien finden Sie unter [Aktivieren von sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams.](turn-on-mdo-for-spo-odb-and-teams.md)

### <a name="view-quarantined-files"></a>Anzeigen von isolierten Dateien

1. Wechseln Sie im Security Center zu **E-Mail &** \> **Zusammenarbeitsüberprüfungsquarantäne.** \> 

2. Ändern Sie auf der **Quarantäneseite** die Ansicht in **Quarantäne** in den **Wertdateien.** Sie können nach einem Feld sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken.

3. Sie können die Ergebnisse sortieren, indem Sie auf eine verfügbare Spaltenüberschrift klicken. Klicken Sie auf **Spalten ändern**, um höchstens sieben Spalten anzuzeigen. Die Standardspalten sind mit einem Sternchen ( ) gekennzeichnet: <sup>\*</sup>
   - **Benutzer**<sup>\*</sup>
   - **Lage**<sup>\*</sup>
   - **Dateiname**<sup>\*</sup>
   - **Datei-URL**<sup>\*</sup>
   - **Dateigröße**<sup>\*</sup>
   - **Läuft ab**<sup>\*</sup>
   - **Veröffentlicht?**<sup>\*</sup>
   - **Erkannt von**
   - **Nach Uhrzeit geändert**

4. Klicken Sie auf **Filter**, um die Ergebnisse zu filtern. Die verfügbaren Filter sind:
   - **Ablaufzeit**: Filtern von Nachrichten nach ihrem Ablauf aus der Quarantäne:
     - **Heute**
     - **Nächste 2 Tage**
     - **Nächste 7 Tage**
     - Ein benutzerdefinierter Datums-/Uhrzeitbereich.
   - **Empfangszeit**
   - **Quarantänegrund:** Der einzige verfügbare Wert ist **Schadsoftware**.
   - **Richtlinientyp**

Nachdem Sie eine bestimmte isolierte Datei gefunden haben, wählen Sie die Datei aus, um Details darüber anzuzeigen und Maßnahmen zu ergreifen (z. B. Anzeigen, Freigeben, Herunterladen oder Löschen der Nachricht).

#### <a name="view-quarantined-file-details"></a>Anzeigen von Details zu isolierten Dateien

Wenn Sie eine Datei in der Liste auswählen, sind die folgenden Dateidetails im daraufhin geöffneten Detail-Flyout verfügbar:

- **Dateiname**
- **Datei-URL:** URL, die den Speicherort der Datei definiert (z. B. in SharePoint Online).
- **Bösartiger Inhalt erkannt auf** Das Datum/die Uhrzeit, zu dem/der die Datei unter Quarantäne gestellt wurde.
- **Läuft ab:** Das Datum, an dem die Datei aus der Quarantäne gelöscht wird.
- **Erkannt von**: Defender für Office 365 oder das Antischadsoftware-Modul von Microsoft.
- **Veröffentlicht?**
- **Name der Schadsoftware**
- **Dokument-ID:** Ein eindeutiger Bezeichner für das Dokument.
- **Dateigröße:** in Kilobyte (KB).
- **Organisation** Die eindeutige ID Ihrer Organisation.
- **Zuletzt geändert**
- **Geändert von:** Der Benutzer, der die Datei zuletzt geändert hat.
- **Secure Hash Algorithm 256-Bit (SHA-256) value:** You can use this hash value to identify the file in other reputation stores or in other locations in your environment.

### <a name="take-action-on-quarantined-files"></a>Ergreifen von Maßnahmen für isolierte Dateien

Wenn Sie eine Datei in der Liste auswählen, können Sie die folgenden Aktionen für die Datei im Detail-Flyout ausführen:

- **Release files**: Select (default) or unselect **Report files to Microsoft for analysis,** and then click **Release files**.
- **Datei herunterladen**
- **Entfernen von Dateien aus der Quarantäne**

Wenn Sie die Dateien nicht freigeben oder entfernen, werden sie nach Ablauf des Standardmäßigen Quarantäneaufbewahrungszeitraums gelöscht.

#### <a name="actions-on-multiple-quarantined-files"></a>Aktionen für mehrere isolierte Dateien

Wenn Sie mehrere isolierte Dateien in der Liste auswählen (bis zu 100), wird das Flyout für **Massenaktionen** angezeigt, in dem Sie die folgenden Aktionen ausführen können:

- **Freigeben von Dateien**
- **Dateien löschen:** Nachdem Sie in der angezeigten Warnung auf **"Ja"** geklickt haben, werden die Dateien sofort gelöscht.

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-view-and-manage-quarantined-messages-and-files"></a>Verwenden Exchange Online PowerShell oder der eigenständigen EOP PowerShell zum Anzeigen und Verwalten von isolierten Nachrichten und Dateien

Die Cmdlets, die Sie zum Anzeigen und Verwalten von Nachrichten und Dateien in Quarantäne verwenden, sind:

- [Delete-QuarantineMessage](/powershell/module/exchange/delete-quarantinemessage)

- [Export-QuarantineMessage](/powershell/module/exchange/export-quarantinemessage)

- [Get-QuarantineMessage](/powershell/module/exchange/get-quarantinemessage)

- [Preview-QuarantineMessage:](/powershell/module/exchange/preview-quarantinemessage)Beachten Sie, dass dieses Cmdlet nur für Nachrichten und nicht für isolierte Dateien aus sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams gilt.

- [Release-QuarantineMessage](/powershell/module/exchange/release-quarantinemessage)
