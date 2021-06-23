---
title: Schutz vor Bedrohungen in Microsoft Defender für Office 365, Antischadsoftware, Antiphishing, Antispam, Tresor Links, Tresor Anlagen, Zap (Zero-Hour Auto Purge), MDO-Sicherheitskonfiguration
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 06/22/2021
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können mehr über den Bedrohungsschutz in Microsoft 365 erfahren und konfigurieren, wie sie für Ihre Organisation verwendet werden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 31ca7c27e3be20e20c16004490bd2ecd5ca4ae05
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083680"
---
# <a name="protect-against-threats"></a>Schutz vor Bedrohungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Hier ist eine Schnellstartanleitung, in der die Konfiguration von Defender für Office 365 in Abschnitte unterteilt wird. Wenn Sie in Office 365 noch keine Informationen zum Schutz vor Bedrohungen haben, nicht sicher sind, wo Sie beginnen sollen, oder wenn Sie am besten lernen, verwenden Sie diese Anleitung als Prüfliste und Ausgangspunkt.

> [!IMPORTANT]
> **Anfänglich empfohlene Einstellungen sind für jede Art von Richtlinie enthalten. Es stehen jedoch viele Optionen zur Verfügung, und Sie können Ihre Einstellungen an die Anforderungen Ihrer spezifischen Organisation anpassen.** Lassen Sie ungefähr 30 Minuten zu, bis Ihre Richtlinien oder Änderungen in Ihrem Rechenzentrum funktionieren.
>
> Um die manuelle Konfiguration der meisten Richtlinien in Defender für Office 365 zu überspringen, können Sie voreingestellte Sicherheitsrichtlinien auf Standard- oder Strict-Ebene verwenden. Weitere Informationen finden Sie unter ["Voreingestellte Sicherheitsrichtlinien" in EOP und Microsoft Defender für Office 365.](preset-security-policies.md)

## <a name="requirements"></a>Anforderungen

### <a name="subscriptions"></a>Abonnements

Bedrohungsschutzfeatures sind in *allen* Microsoft- oder Office 365-Abonnements enthalten. Einige Abonnements verfügen jedoch über erweiterte Features. In der folgenden Tabelle sind die in diesem Artikel enthaltenen Schutzfeatures zusammen mit den Mindestabonnementanforderungen aufgeführt.

> [!TIP]
> Beachten Sie, dass über die Anweisungen zum Aktivieren der Überwachung hinaus *die Schritte* mit Antischadsoftware, Antiphishing und Antispam beginnen, die als Teil von Office 365 Exchange Online Protection (**EOP**) gekennzeichnet sind. Dies kann in einem Defender für Office 365 Artikel ungerade erscheinen, bis Sie sich daran erinnern (**Defender für Office 365**) EOP enthält und darauf aufbaut.

<br>

****

|Schutztyp|Abonnementanforderung|
|---|---|
|Überwachungsprotokollierung (für Berichtszwecke)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Schutz vor Schadsoftware|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Antiphishingschutz|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Antispamschutz|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Schutz vor bösartigen URLs und Dateien in E-Mails und Office Dokumenten (Tresor Links und Tresor Anlagen)|[Microsoft Defender für Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Rollen und Berechtigungen

Um Defender für Office 365 Richtlinien zu konfigurieren, muss Ihnen eine entsprechende Rolle zugewiesen werden. Sehen Sie sich die tabelle unten für Rollen an, die diese Aktionen ausführen können.

<br>

****

|Rolle oder Rollengruppe|Weitere Informationen|
|---|---|
|Globaler Administrator|[Informationen zu Microsoft 365-Administratorrollen](../../admin/add-users/about-admin-roles.md)|
|Sicherheitsadministrator|[Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online-Organisationsverwaltung|[Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo)|
|

Weitere Informationen finden Sie unter ["Berechtigungen" im Microsoft 365 Defender-Portal.](permissions-microsoft-365-security-center.md)

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>Aktivieren der Überwachungsprotokollierung für Berichte und Untersuchungen

- Starten Sie die Überwachungsprotokollierung frühzeitig. Für einige der folgenden  Schritte müssen Sie die Überwachung aktivieren. Die Überwachungsprotokollierung ist in Abonnements verfügbar, die [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)enthalten. Um Daten in Bedrohungsschutzberichten, [E-Mail-Sicherheitsberichten](view-email-security-reports.md)und [Explorer](threat-explorer.md)anzuzeigen, muss die Überwachungsprotokollierung *aktiviert* sein. Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>Teil 1: Schutz vor Schadsoftware in EOP

Weitere Informationen zu den empfohlenen Einstellungen für Antischadsoftware finden Sie unter [EOP-Richtlinieneinstellungen für Antischadsoftware.](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)

1. Öffnen Sie die **Seite "Antischadsoftware"** im Microsoft 365 Defender Portal unter <https://security.microsoft.com/antimalwarev2> .

2. Wählen Sie auf der Seite **"Antischadsoftware"** die Richtlinie mit dem Namen **"Standard" aus,** indem Sie auf den Namen klicken.

3. Klicken Sie im daraufhin geöffneten Flyout mit den Richtliniendetails auf **"Schutzeinstellungen bearbeiten",** und konfigurieren Sie dann die folgenden Einstellungen:
   - Abschnitt **"Schutzeinstellungen":**
     - Wählen Sie **"Allgemeinen Anlagenfilter aktivieren"** aus, um den allgemeinen Anlagenfilter zu aktivieren. Klicken Sie auf **Dateitypen anpassen,** um weitere Dateitypen hinzuzufügen.
     - **Automatische Bereinigung der Nullstunde für Schadsoftware aktivieren:** Überprüfen Sie, ob diese Einstellung ausgewählt ist. Weitere Informationen zu ZAP für Schadsoftware finden Sie unter [Zero-Hour Auto Purge (ZAP) für Schadsoftware.](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-malware)
   - **Benachrichtigungsbereich:** Stellen Sie sicher, dass keine der Benachrichtigungseinstellungen ausgewählt ist.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

4. Zurück auf dem Flyout der Richtliniendetails klicken Sie auf **Schließen**.

Ausführliche Anweisungen zum Konfigurieren von Antischadsoftwarerichtlinien finden Sie unter [Konfigurieren von Antischadsoftwarerichtlinien in EOP.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>Teil 2: Antiphishingschutz in EOP und Defender für Office 365

[Antiphishingschutz](anti-phishing-protection.md) ist in Abonnements verfügbar, die [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)enthalten. Erweiterter Antiphishingschutz ist in [Defender für Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)verfügbar.

Weitere Informationen zu den empfohlenen Einstellungen für Antiphishingrichtlinien finden Sie unter [EOP Antiphishing-Richtlinieneinstellungen](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) und [Antiphishingrichtlinieneinstellungen in Microsoft Defender für Office 365.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)

Im folgenden Verfahren wird beschrieben, wie Sie die Standardmäßige Antiphishingrichtlinie konfigurieren. Einstellungen, die nur in Defender für Office 365 verfügbar sind, sind deutlich gekennzeichnet.

1. Öffnen Sie die **Seite "Antiphishing"** im Microsoft 365 Defender-Portal unter <https://security.microsoft.com/antiphishing> .

2. Wählen Sie auf der **Seite "Antiphishing"** die Richtlinie mit dem Namen **Office365 AntiPhish Default (Standard)** aus, indem Sie auf den Namen klicken.

3. Konfigurieren Sie im angezeigten Richtliniendetails-Flyout die folgenden Einstellungen:
   - **Phishingschwellenwert & Schutzabschnitt:** Klicken Sie auf **"Schutzeinstellungen bearbeiten",** und konfigurieren Sie die folgenden Einstellungen im daraufhin geöffneten Flyout:
     - **Schwellenwert für Phishing-E-Mails:** <sup>\*</sup> Wählen Sie **2 – Aggressiv** (Standard) oder **3 – Aggressiver** (streng) aus.
     - Abschnitt **"Identitätswechsel":** <sup>\*</sup> Konfigurieren Sie die folgenden Werte:
       - Wählen Sie **"Schützen von Benutzern aktivieren"** aus, klicken Sie auf den angezeigten Link **"Absender verwalten",** und fügen Sie interne und externe Absender hinzu, um sich vor Identitätswechsel zu schützen, z. B. die Vorstände Ihrer Organisation, Ihren CEO, GIF und andere leitende Führungskräfte.
       - Wählen Sie **"Zu schützende Domänen aktivieren"** aus, und konfigurieren Sie dann die folgenden angezeigten Einstellungen:
         - Wählen Sie **"Domänen einschließen" aus, die ich besitze,** um interne Absender in Ihren akzeptierten Domänen (sichtbar durch Klicken auf **"Meine Domänen anzeigen")** vor Identitätswechsel zu schützen.
         - Um Absender in anderen Domänen zu schützen, wählen Sie **benutzerdefinierte Domänen einschließen** aus, klicken Sie auf den angezeigten Link **Benutzerdefinierte Domänen verwalten ,** und fügen Sie dann weitere Domänen hinzu, um den Identitätswechsel zu schützen.
     - **Abschnitt "Vertrauenswürdige Absender und Domänen** <sup>\*</sup> hinzufügen": Klicken Sie auf **"Verwalten (nn) vertrauenswürdiger Absender und Domänen",** um Absender- und Absenderdomänenausnahmen für den Identitätswechselschutz bei Bedarf zu konfigurieren.
     - Einstellungen für die <sup>\*</sup> Postfachintelligenz: Überprüfen Sie, ob die Option **"Postfachintelligenz aktivieren"** und **"Intelligenz für Identitätswechselschutz aktivieren"** ausgewählt ist.
     - Abschnitt **"Spoofing":** Überprüfen Sie, ob **die Spoofintelligenz** aktiviert ist.

     Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - Abschnitt **"Aktionen":** Klicken Sie auf **"Aktionen bearbeiten",** und konfigurieren Sie die folgenden Einstellungen im daraufhin geöffneten Flyout:
     - Abschnitt **"Nachrichtenaktionen":** Konfigurieren Sie die folgenden Einstellungen:
       - **Wenn die Nachricht als angenommener Benutzer erkannt wird:** <sup>\*</sup> Wählen Sie **"Nachricht unter Quarantäne stellen"** aus.
       - **Wenn die Nachricht als imitierte Domäne erkannt wird:** <sup>\*</sup> Wählen Sie **"Nachricht unter Quarantäne stellen"** aus.
       - **Wenn die Postfachintelligenz einen imitierten Benutzer erkennt:** <sup>\*</sup> Wählen Sie **"Nachricht in Junk-E-Mail-Ordner des Empfängers verschieben "** (Standard) oder **"Nachricht unter Quarantäne** stellen" (Streng) aus.
       - **Wenn die Nachricht als Spoofing erkannt wird:** Wählen Sie **"Nachricht in Junk-E-Mail-Ordner des Empfängers verschieben "** (Standard) oder **"Nachricht unter Quarantäne** stellen" (streng) aus.
     - **Sicherheitstipps & Indikatorenabschnitt:** Konfigurieren Sie die folgenden Einstellungen:
       - **Ersten Kontakt anzeigen Sicherheitstipp:** Auswählen (aktivieren).
       - **Benutzeridentitätswechsel Sicherheitstipp** <sup>\*</sup> anzeigen: Auswählen (aktivieren).
       - **Anzeigen des Domänenidentitätswechsels Sicherheitstipp:** <sup>\*</sup> Auswählen (Aktivieren).
       - **Ungewöhnliche Zeichen für den Benutzeridentitätswechsel anzeigen Sicherheitstipp:** <sup>\*</sup> Auswählen (Aktivieren).
       - **Show (?) for unauthenticated senders for spoof:** Select (turn on).
       - **Show "via" tag:** Select (turn on).

     Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   <sup>\*</sup>Diese Einstellung ist nur in Defender für Office 365 verfügbar.

4. Klicken Sie auf **"Speichern"** und dann auf **"Schließen".**

Ausführliche Anweisungen zum Konfigurieren von Antiphishingrichtlinien finden Sie unter [Konfigurieren von Antiphishingrichtlinien in EOP](configure-anti-phishing-policies-eop.md) und [Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365.](configure-mdo-anti-phishing-policies.md)

## <a name="part-3---anti-spam-protection-in-eop"></a>Teil 3 : Antispamschutz in EOP

Weitere Informationen zu den empfohlenen Einstellungen für Antispam finden Sie unter [EOP Antispamrichtlinieneinstellungen.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

1. Öffnen Sie die Seite **"Antispamrichtlinien"** im portal Microsoft 365 Defender unter <https://security.microsoft.com/antispam> .

2. Wählen Sie auf der Seite **"Antispamrichtlinien"** die Richtlinie mit dem Namen **"Eingehende Antispamrichtlinie" (Standard)** aus der Liste aus, indem Sie auf den Namen klicken.

3. Konfigurieren Sie im angezeigten Richtliniendetails-Flyout die folgenden Einstellungen:
   - **Schwellenwert für Massen-E-Mails & Abschnitt "Spameigenschaften":** Klicken Sie auf **Spamschwellenwert und Eigenschaften bearbeiten.** Konfigurieren Sie im angezeigten Flyout die folgenden Einstellungen:
     - **Schwellenwert für Massen-E-Mails:** Legen Sie diesen Wert auf 5 (streng) oder 6 (Standard) fest.
     - Behalten Sie für andere Einstellungen die Standardwerte bei (**Aus** oder **Keine**).

     Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - **Abschnitt "Aktionen":** Klicken Sie auf **"Aktionen bearbeiten".** Konfigurieren Sie im angezeigten Flyout die folgenden Einstellungen:
     - Abschnitt **"Nachrichtenaktionen":**
       - **Spam:** Überprüfen, ob **Nachricht in Junk-E-Mail-Ordner** verschoben wird (Standard) oder **Quarantänenachricht** auswählen (streng).
       - **Spam mit hoher Spamwahrscheinlichkeit:** Wählen Sie **"Quarantänenachricht"** aus.
       - **Phishing:** Wählen Sie **"Quarantänenachricht"** aus.
       - **Phishing mit hoher Vertrauenswürdigkeit:** Überprüfen Sie, ob **Quarantänenachrichten** ausgewählt sind.
       - **Massen:** Vergewissern Sie sich, dass **die Nachricht in den Junk-E-Mail-Ordner** verschoben wird (Standard) oder **"Quarantänenachricht"** (streng) auswählen.
     - **Aufbewahrung von Spam in Quarantäne für diese viele Tage:** Überprüfen Sie den Wert **30** Tage.
     - **Aktivieren Sie Spamsicherheitstipps:** Überprüfen Sie, ob diese Einstellung ausgewählt (aktiviert) ist.
     - **Automatische Bereinigung zur Nullstunde aktivieren (ZAP):** Überprüfen Sie, ob diese Einstellung ausgewählt (aktiviert) ist.
       - **Aktivieren für Phishingnachrichten:** Überprüfen Sie, ob diese Einstellung ausgewählt (aktiviert) ist. Weitere Informationen finden Sie unter [Zero-Hour Auto Purge (ZAP) für Phishing.](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-phishing)
       - **Aktivieren für Spamnachrichten:** Überprüfen Sie, ob diese Einstellung ausgewählt (aktiviert) ist. Weitere Informationen finden Sie unter [Zap (Zero-Hour Auto Purge) für Spam.](zero-hour-auto-purge.md#zero-hour-auto-purge-zap-for-spam)
     -  Benachrichtigungsabschnitt:
       - Wählen Sie **Spambenachrichtigungen für Endbenutzer aktivieren aus.**
         - **Senden Von Spambenachrichtigungen für Endbenutzer alle (Tage):** Überprüfen Sie den Wert **3** Tage.
         - **Sprache:** Überprüfen Sie den Wert **"Standard",** oder wählen Sie eine Sprache aus.

     Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - Abschnitt **"Zulässige und blockierte Absender und Domänen":** Überprüfen oder bearbeiten Sie Ihre zulässigen Absender und zulässigen Domänen, wie unter [Erstellen blockierter Absenderlisten in EOP](create-block-sender-lists-in-office-365.md) oder [Erstellen von Listen sicherer Absender in EOP](create-safe-sender-lists-in-office-365.md)beschrieben.

     Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

4. Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

Ausführliche Anweisungen zum Konfigurieren von Antispamrichtlinien finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Teil 4 – Schutz vor bösartigen URLs und Dateien (Tresor Links und Tresor Anlagen in Defender für Office 365)

Der Time-of-Click-Schutz vor bösartigen URLs und Dateien ist in Abonnements verfügbar, die [Microsoft Defender für Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)enthalten. Sie wird über [Tresor Richtlinien](safe-attachments.md) für Anlagen und [Tresor Links](safe-links.md) eingerichtet.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Tresor Anlagenrichtlinien in Microsoft Defender für Office 365

Weitere Informationen zu den empfohlenen Einstellungen für Tresor Anlagen finden Sie unter . [Tresor Anlageneinstellungen.](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

1. Öffnen Sie die Seite **Tresor Anlagen** im portal Microsoft 365 Defender unter <https://security.microsoft.com/safeattachmentv2> .

2. Klicken Sie auf der Seite **Tresor Anlagen** auf **globale Einstellungen,** und konfigurieren Sie dann die folgenden Einstellungen für das angezeigte Flyout:
   - **Aktivieren Sie Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams:** Aktivieren Sie diese Einstellung ( ![ Umschalten ](../../media/scc-toggle-on.png) ).

     > [!IMPORTANT]
     > **Bevor Sie Tresor Anlagen für SharePoint, OneDrive und Microsoft Teams aktivieren, überprüfen Sie, ob die Überwachungsprotokollierung in Ihrer Organisation aktiviert ist.** Diese Aktion wird in der Regel von einer Person ausgeführt, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist. Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche!](../../compliance/turn-audit-log-search-on-or-off.md)

   - **Aktivieren Sie Tresor Dokumente für Office Clients:** Aktivieren Sie diese Einstellung ( ![ Umschalten ](../../media/scc-toggle-on.png) ). Beachten Sie, dass dieses Feature nur mit Microsoft 365 E5- oder Microsoft 365 E5 Security-Lizenzen verfügbar und von Bedeutung ist.
   - **Zulassen, dass Benutzer durch geschützte Ansicht klicken, auch wenn Tresor Dokumente die Datei als schädlich identifiziert** haben: Überprüfen Sie, ob diese Einstellung deaktiviert ist ( ![ Deaktivieren ](../../media/scc-toggle-off.png) ).

   Wenn Sie fertig sind, klicken Sie auf **"Speichern".**

3. Klicken Sie wieder auf der Seite **Tresor Anlagen** auf das ![ Symbol Erstellen . ](../../media/m365-cc-sc-create-icon.png)

4. Konfigurieren Sie im daraufhin geöffneten Assistenten zum **Erstellen Tresor Anlagenrichtlinien** die folgenden Einstellungen:
   - **Benennen Sie die Seite "Richtlinie":**
     - **Name:** Geben Sie etwas Eindeutiges und Beschreibendes ein.
     - **Beschreibung:** Geben Sie eine optionale Beschreibung ein.
   - Seite **"Benutzer und Domänen":** Da dies Ihre erste Richtlinie ist und Sie wahrscheinlich die Abdeckung maximieren möchten, sollten Sie ihre [akzeptierten Domänen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in das Feld **"Domänen"** eingeben. Andernfalls können Sie die Felder **"Benutzer"** und **"Gruppen"** für eine präzisere Steuerung verwenden. Sie können Ausnahmen angeben, indem Sie **diese Benutzer, Gruppen und Domänen ausschließen und** Werte eingeben.
   - **Einstellungen** Seite:
     - **Tresor Attachments unknown malware response:** Select **Block**.
     - **Anlage mit erkannten Anlagen umleiten:** **Umleitung aktivieren:** Diese Einstellung aktivieren (auswählen) und eine E-Mail-Adresse eingeben, um erkannte Nachrichten zu empfangen.
     - **Wenden Sie die Erkennungsantwort Tresor Anlagen an, wenn die Überprüfung nicht abgeschlossen werden kann (Timeout oder Fehler):** Überprüfen Sie, ob diese Einstellung ausgewählt ist.

5. Wenn Sie fertig sind, klicken Sie auf **"Absenden"** und dann auf **"Fertig".**

6. (Empfohlen) Führen Sie als globaler Administrator oder SharePoint Onlineadministrator das Cmdlet **["Set-SPOTenant"](/powershell/module/sharepoint-online/Set-SPOTenant)** aus, wobei der Parameter _"DisallowInfectedFileDownload"_ in SharePoint Online PowerShell festgelegt `$true` ist.
   - `$true` blockiert alle Aktionen (mit Ausnahme von Delete) für erkannte Dateien. Personen können erkannte Dateien nicht öffnen, verschieben, kopieren oder freigeben.
   - `$false` blockiert alle Aktionen außer "Löschen" und "Herunterladen". Personen können das Risiko akzeptieren und eine erkannte Datei herunterladen.

7. Es kann bis zu 30 Minuten dauern, bis ihre Änderungen auf alle Microsoft 365 Rechenzentren verteilt sind.

Ausführliche Anweisungen zum Konfigurieren Tresor Anlagenrichtlinien und globalen Einstellungen für Tresor Anlagen finden Sie in den folgenden Themen:

- [Einrichten Tresor Anlagenrichtlinien in Microsoft Defender für Office 365](set-up-safe-attachments-policies.md)
- [Aktivieren von Sicheren Anlagen für SharePoint, OneDrive und Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)
- [Sichere Dokumente in Microsoft 365 E5](safe-docs.md)

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Tresor Verknüpfungsrichtlinien in Microsoft Defender für Office 365

Weitere Informationen zu den empfohlenen Einstellungen für Tresor Links finden Sie unter [Tresor Links-Einstellungen.](recommended-settings-for-eop-and-office365.md#safe-links-settings)

1. Öffnen Sie die Seite **Tresor Links** im Microsoft 365 Defender Portal unter <https://security.microsoft.com/safelinksv2> .

2. Klicken Sie auf der Seite **Tresor Links** auf **globale Einstellungen,** und konfigurieren Sie dann die folgenden Einstellungen für das angezeigte Flyout:
   - **Einstellungen, die für Inhalte im Abschnitt "Unterstützte Office 365 Apps" gelten:**
     - **Verwenden Sie Tresor Links in Office 365 Apps:** Überprüfen Sie, ob diese Einstellung aktiviert ist ( ![ Umschalten ](../../media/scc-toggle-on.png) ).
     - **Nicht nachverfolgen, wenn Benutzer in Office 365 Apps auf geschützte Links klicken:** Deaktivieren ( ![ Deaktivieren ](../../media/scc-toggle-off.png) )
     - **Benutzer dürfen in Office 365 Apps nicht auf die ursprüngliche URL klicken:** Überprüfen Sie, ob diese Einstellung aktiviert ist ( ![ Umschalten ](../../media/scc-toggle-on.png) ).

   Wenn Sie fertig sind, klicken Sie auf **"Speichern".**

3. Klicken Sie zurück auf der **Seite Tresor Links** auf das Symbol ![ Erstellen . ](../../media/m365-cc-sc-create-icon.png)

4. Konfigurieren Sie im daraufhin geöffneten Assistenten zum **Erstellen Tresor Verknüpfungsrichtlinien** die folgenden Einstellungen:
   - **Benennen Sie die Seite "Richtlinie":**
     - **Name:** Geben Sie etwas Eindeutiges und Beschreibendes ein.
     - **Beschreibung:** Geben Sie eine optionale Beschreibung ein.
   - Seite **"Benutzer und Domänen":** Da dies Ihre erste Richtlinie ist und Sie wahrscheinlich die Abdeckung maximieren möchten, sollten Sie ihre [akzeptierten Domänen](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains) in das Feld **"Domänen"** eingeben. Andernfalls können Sie die Felder **"Benutzer"** und **"Gruppen"** für eine präzisere Steuerung verwenden. Sie können Ausnahmen angeben, indem Sie **diese Benutzer, Gruppen und Domänen ausschließen und** Werte eingeben.
   - Seite **"Schutzeinstellungen":**
     - **Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in Nachrichten** aus: Aktivieren Sie diese **Einstellung.**
     - **Wählen Sie die Aktion für unbekannte oder potenziell schädliche URLs in Microsoft Teams** aus: Aktivieren Sie diese **Einstellung.** Seit März 2020 befindet sich diese Einstellung in der Vorschau und ist nur für Mitglieder des Microsoft Teams Technology Adoption Program (TAP) verfügbar oder funktionsfähig.
     - **Wenden Sie die Echtzeit-URL-Überprüfung auf verdächtige Links und Links an, die auf Dateien verweisen:** Wählen Sie diese Einstellung aus (aktivieren).
       - **Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht übermitteln:** Wählen Sie diese Einstellung aus (aktivieren).
     - **Wenden Sie Tresor Links auf E-Mail-Nachrichten** an, die innerhalb der Organisation gesendet werden: Wählen Sie diese Einstellung aus (aktivieren).
     - **Benutzerklicks nicht nachverfolgen:** Überprüfen Sie, ob diese Einstellung nicht ausgewählt (deaktiviert) ist.
     - **Benutzer dürfen nicht auf die ursprüngliche URL klicken:** Überprüfen Sie, ob diese Einstellung aktiviert (ausgewählt) ist.
     - **Anzeigen des Organisationsbrandings auf Benachrichtigungs- und Warnseiten:** Das Auswählen dieser Einstellung (Aktivieren) ist erst sinnvoll, nachdem Sie die Anweisungen unter ["Anpassen des Microsoft 365 Designs für Ihre Organisation](../../admin/setup/customize-your-organization-theme.md) zum Hochladen Ihres Unternehmenslogos" befolgt haben.
     - **Schreiben Sie die folgenden URLs nicht neu:** Es gibt keine spezifische Empfehlung für diese Einstellung. Weitere Informationen finden Sie unter ["Die folgenden URLs nicht umschreiben" in Tresor Verknüpfungsrichtlinien.](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)
   - **Benachrichtigungsseite:**
     - **Wie möchten Sie Benutzer benachrichtigen?** section: Optional, you can select **Use custom notification text** to enter customized notification text to use. Sie können auch **Microsoft Translator für die automatische Lokalisierung** verwenden auswählen, um den benutzerdefinierten Benachrichtigungstext in die Sprache des Benutzers zu übersetzen. Andernfalls lassen **Sie den Standardmäßigen Benachrichtigungstext** ausgewählt.

5. Wenn Sie fertig sind, klicken Sie auf **"Absenden"** und dann auf **"Fertig".**

Ausführliche Anweisungen zum Konfigurieren von Richtlinien für Tresor Links und globale Einstellungen für Tresor Links finden Sie in den folgenden Themen:

- [Einrichten Tresor Links-Richtlinien in Microsoft Defender für Office 365](set-up-safe-links-policies.md)
- [Konfigurieren globaler Einstellungen für Tresor Links in Microsoft Defender für Office 365](configure-global-settings-for-safe-links.md)

### <a name="now-set-up-alerts-for-detected-files-in-sharepoint-online-or-onedrive-for-business"></a>Richten Sie jetzt Warnungen für erkannte Dateien in SharePoint Online oder OneDrive for Business

Um eine Benachrichtigung zu erhalten, wenn eine Datei in SharePoint Online oder OneDrive for Business als bösartig erkannt wurde, können Sie eine Warnung wie in diesem Abschnitt beschrieben einrichten.

1. Wechseln Sie im Portal Microsoft 365 Defender unter <https://security.microsoft.com> **"E-Mail &** \> **Zusammenarbeitsrichtlinien &** \> **Regelwarnungsrichtlinie"** zu "E-Mail & Zusammenarbeitsrichtlinien".

2. Klicken Sie auf der Seite **"Warnungsrichtlinie"** auf **"Neue Warnungsrichtlinie".**

3. Der Assistent **für neue Warnungsrichtlinien** wird geöffnet. Konfigurieren Sie auf der Seite **"Name"** die folgenden Einstellungen:
   - **Name:** Geben Sie einen eindeutigen und beschreibenden Namen ein. Sie können z. B. schädliche Dateien in Bibliotheken eingeben.
   - **Beschreibung:** Geben Sie eine optionale Beschreibung ein.
   - **Schweregrad:** Wählen Sie **"Niedrig",** **"Mittel"** oder **"Hoch"** aus.
   - **Kategorie:** Auswählen **der Bedrohungsverwaltung**.

   Wenn Sie fertig sind, klicken Sie auf **"Weiter".**

4. Konfigurieren Sie auf der Seite **"Warnungseinstellungen erstellen"** die folgenden Einstellungen:
   - **Wozu möchten Sie eine Warnung erstellen?** Section: **Activity is** \> **Detected malware in file**.
   - **Wie soll die Warnung ausgelöst werden?** Überprüfen Sie jedes Mal, wenn **eine Aktivität mit der Regel übereinstimmt.**

   Wenn Sie fertig sind, klicken Sie auf **"Weiter".**

5. Konfigurieren Sie auf der Seite **"Empfänger festlegen"** die folgenden Einstellungen:
   - **E-Mail-Benachrichtigungen senden:** Überprüfen Sie, ob diese Einstellung aktiviert ist.
   - **E-Mail-Empfänger:** Wählen Sie einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheitsleser aus, die eine Benachrichtigung erhalten sollen, wenn eine schädliche Datei erkannt wird.
   - **Tägliches Benachrichtigungslimit:** Überprüfen **Sie,** ob kein Grenzwert ausgewählt ist.

   Wenn Sie fertig sind, klicken Sie auf **"Weiter".**

6. Überprüfen Sie auf der Seite **"Einstellungen überprüfen"** Ihre Einstellungen, überprüfen Sie, ob **"Ja"** ausgewählt ist, aktivieren Sie sie sofort, und klicken Sie dann auf **"Fertig stellen".**

Weitere Informationen zu Warnungsrichtlinien finden Sie [unter Warnungsrichtlinien im Microsoft 365 Compliance Center](../../compliance/alert-policies.md).

> [!NOTE]
> Wenn Sie die Konfiguration abgeschlossen haben, verwenden Sie diese Links, um Workloaduntersuchungen zu starten:
>
>- [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report)
>- [Verwenden des Microsoft 365 Defender-Portals zum Verwalten von isolierten Dateien in Defender für Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [Vorgehensweise, wenn eine schädliche Datei in SharePoint Online, OneDrive oder Microsoft Teams gefunden wird](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Verwalten von isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="post-setup-tasks-and-next-steps"></a>Aufgaben nach dem Setup und nächste Schritte

Stellen Sie nach dem Konfigurieren der Bedrohungsschutzfeatures sicher, dass Sie überwachen, wie diese Features funktionieren! Überprüfen und überarbeiten Sie Ihre Richtlinien so, dass sie das tun, wozu Sie sie benötigen. Achten Sie außerdem auf neue Features und Dienstupdates, die einen Mehrwert bieten können.

<br>

****

|Vorgehensweise|Ressourcen mit mehr Informationen|
|---|---|
|Erfahren Sie, wie Die Funktionen zum Schutz vor Bedrohungen für Ihre Organisation funktionieren, indem Sie Berichte anzeigen.|[E-Mail-Sicherheitsberichte](view-email-security-reports.md) <p> [Berichte für Microsoft Defender für Office 365](view-reports-for-mdo.md) <p> [Sicherheitsrisiken-Explorer](threat-explorer.md)|
|Überprüfen und Überarbeiten Ihrer Bedrohungsschutzrichtlinien in regelmäßigen Abständen nach Bedarf|[Sicherheitsbewertung](../defender/microsoft-secure-score.md) <p> [Microsoft 365 Untersuchung und Reaktion auf Bedrohungen](./office-365-ti.md)|
|Auf neue Features und Dienstupdates achten|[Standard- und Targeted Release-Optionen](../../admin/manage/release-options-in-office-365.md) <p> [Nachrichtencenter](../../admin/manage/message-center.md) <p> [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Dienstbeschreibungen](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
