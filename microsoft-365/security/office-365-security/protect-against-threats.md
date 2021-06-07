---
title: Schutz vor Bedrohungen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Administratoren können sich über den Bedrohungsschutz in Microsoft 365 informieren und konfigurieren, wie sie für Ihre Organisation verwendet werden.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ac90aa853769b239386d422e0b196a1f6140bf95
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793196"
---
# <a name="protect-against-threats"></a>Schutz vor Bedrohungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Im Folgenden finden Sie eine Schnellstartanleitung, in der die Konfiguration von Defender für Office 365 in Blöcke unterteilt wird. Wenn Sie noch nicht mit den Bedrohungsschutzfeatures in Office 365, nicht sicher sind, wo Sie beginnen sollen, oder wenn Sie am besten damit *lernen,* verwenden Sie diese Anleitung als Prüfliste und Ausgangspunkt.

> [!IMPORTANT]
> **Anfänglich empfohlene Einstellungen sind für jede Art von Richtlinie enthalten. Es stehen jedoch viele Optionen zur Verfügung, und Sie können Ihre Einstellungen an die Anforderungen Ihrer spezifischen Organisation anpassen.** Lassen Sie ungefähr 30 Minuten zu, bis Ihre Richtlinien oder Änderungen in Ihrem Rechenzentrum funktionieren.

## <a name="requirements"></a>Anforderungen

### <a name="subscriptions"></a>Abonnements

Bedrohungsschutzfeatures sind in *allen* Microsoft- oder Office 365-Abonnements enthalten. Einige Abonnements verfügen jedoch über erweiterte Features. In der folgenden Tabelle sind die in diesem Artikel enthaltenen Schutzfeatures zusammen mit den Mindestabonnementanforderungen aufgeführt.

> [!TIP]
> Beachten Sie, dass die *Schritte* über die Anweisungen zum Aktivieren der Überwachung hinaus Antischadsoftware, Antiphishing und Antispam starten, die als Teil von Office 365 Exchange Online Protection (**EOP**) gekennzeichnet sind. Dies kann in einem Defender for Office 365-Artikel ungerade erscheinen, bis Sie sich daran erinnern (**Defender für Office 365**) EOP enthält und darauf aufbaut.

<br>

****

|Schutztyp|Abonnementanforderung|
|---|---|
|Überwachungsprotokollierung (für Berichtszwecke)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Schutz vor Schadsoftware|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Antiphishingschutz|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Antispamschutz|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Automatische Bereinigung zur Nullstunde (für E-Mails)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Schutz vor bösartigen URLs und Dateien in E-Mails und Office Dokumenten (sichere Links und sichere Anlagen)|[Microsoft Defender für Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Aktivieren sie sichere Anlagen für SharePoint-, OneDrive- und Microsoft Teams-Workloads|[Microsoft Defender für Office 365](turn-on-mdo-for-spo-odb-and-teams.md)|
|Erweiterter Antiphishingschutz|[Microsoft Defender für Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Rollen und Berechtigungen

Um Defender für Office 365 Richtlinien zu konfigurieren, muss Ihnen im [Security & Compliance Center](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)eine entsprechende Rolle zugewiesen werden. Sehen Sie sich die tabelle unten für Rollen an, die diese Aktionen ausführen können.

<br>

****

|Rolle oder Rollengruppe|Weitere Informationen|
|---|---|
|Globaler Administrator|[Informationen zu Microsoft 365-Administratorrollen](../../admin/add-users/about-admin-roles.md)|
|Sicherheitsadministrator|[Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online-Organisationsverwaltung|[Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo) <p> und <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|

Weitere Informationen finden Sie unter ["Berechtigungen" im Security & Compliance Center.](permissions-in-the-security-and-compliance-center.md)

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>Aktivieren der Überwachungsprotokollierung für Berichte und Untersuchungen

- Starten Sie die Überwachungsprotokollierung frühzeitig. Für einige der folgenden  Schritte müssen Sie die Überwachung aktivieren. Die Überwachungsprotokollierung ist in Abonnements verfügbar, die [Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)enthalten. Um Daten in Bedrohungsschutzberichten wie dem [Sicherheitsdashboard,](security-dashboard.md) [E-Mail-Sicherheitsberichten](view-email-security-reports.md)und [Explorer](threat-explorer.md)anzuzeigen, muss die Überwachungsprotokollierung *aktiviert* sein. Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection-in-eop"></a>Teil 1: Schutz vor Schadsoftware in EOP

Weitere Informationen zu den empfohlenen Einstellungen für Antischadsoftware finden Sie unter [EOP-Richtlinieneinstellungen für Antischadsoftware.](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)

1. Öffnen <https://security.microsoft.com/antimalwarev2> Sie .

2. Wählen Sie auf der Seite **"Antischadsoftware"** die Richtlinie mit dem Namen **"Standardrichtlinie"** aus, indem Sie auf den Namen klicken.

3. Klicken Sie im daraufhin geöffneten Flyout mit den Richtliniendetails auf **"Schutzeinstellungen bearbeiten",** und konfigurieren Sie dann die folgenden Einstellungen:
   - Wählen Sie **"Allgemeinen Anlagenfilter aktivieren" aus,** um den allgemeinen Anlagenfilter zu aktivieren. Klicken Sie auf **Dateitypen anpassen,** um weitere Dateitypen hinzuzufügen.
   - Stellen Sie sicher, dass die **automatische Bereinigung von Nullstunden für Schadsoftware** aktiviert ist.
   - Stellen Sie sicher, dass keine der Einstellungen im **Benachrichtigungsbereich** ausgewählt ist.

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

4. Zurück auf dem Flyout der Richtliniendetails klicken Sie auf **Schließen**.

Ausführliche Anweisungen zum Konfigurieren von Antischadsoftwarerichtlinien finden Sie unter [Konfigurieren von Antischadsoftwarerichtlinien in EOP.](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>Teil 2: Antiphishingschutz in EOP und Defender für Office 365

[Antiphishingschutz](anti-phishing-protection.md) ist in Abonnements verfügbar, die [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)enthalten. Erweiterter Antiphishingschutz ist in [Defender für Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)verfügbar.

Weitere Informationen zu den empfohlenen Einstellungen für Antiphishingrichtlinien finden Sie unter [EOP Antiphishing-Richtlinieneinstellungen](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings) und [Antiphishingrichtlinieneinstellungen in Microsoft Defender für Office 365.](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)

Im folgenden Verfahren wird beschrieben, wie Sie die Standardmäßige Antiphishingrichtlinie konfigurieren. Einstellungen, die nur in Defender für Office 365 verfügbar sind, sind deutlich gekennzeichnet.

1. Öffnen <https://security.microsoft.com/antiphishing> Sie .

2. Wählen Sie auf der **Seite "Antiphishing"** die Richtlinie mit dem Namen **Office365 AntiPhish Default (Standard)** aus, indem Sie auf den Namen klicken.

3. Konfigurieren Sie im angezeigten Richtliniendetails-Flyout die folgenden Einstellungen:

   - **Phishingschwellenwert & Schutzabschnitt:** Klicken Sie auf **"Schutzeinstellungen bearbeiten",** und konfigurieren Sie die folgenden Einstellungen im Flyout **"Schutzeinstellungen bearbeiten",** das geöffnet wird:
     - **Schwellenwert für Phishing-E-Mails:** <sup>\*</sup> Wählen Sie **2 – Aggressiv** (Standard) oder **3 – Aggressiver** (streng) aus.
     - Abschnitt **"Identitätswechsel":** <sup>\*</sup> Konfigurieren Sie die folgenden Werte:
       - Wählen Sie **"Schützen von Benutzern aktivieren"** aus, klicken Sie auf den angezeigten Link **"Absender verwalten",** und fügen Sie interne und externe Absender hinzu, um sich vor Identitätswechseln zu schützen, z. B. die Vorstände Ihrer Organisation, Ihren CEO, GIF und andere leitende Führungskräfte.
       - Wählen Sie **"Zu schützende Domänen aktivieren"** aus, und konfigurieren Sie dann die folgenden angezeigten Einstellungen:
         - Wählen Sie **"Domänen einschließen" aus, die ich besitze,** um interne Absender in Ihren akzeptierten Domänen (sichtbar durch Klicken auf **"Meine Domänen anzeigen")** vor Identitätswechsel zu schützen.
         - Um Absender in anderen Domänen zu schützen, wählen Sie **benutzerdefinierte Domänen einschließen** aus, klicken Sie auf den angezeigten Link **Benutzerdefinierte Domänen verwalten ,** und fügen Sie dann weitere Domänen hinzu, um den Identitätswechsel zu schützen.
     - **Abschnitt "Vertrauenswürdige Absender und Domänen** <sup>\*</sup> hinzufügen": Klicken Sie auf **"Verwalten (nn) vertrauenswürdiger Absender und Domänen",** um Absender- und Absenderdomänenausnahmen für den Identitätswechselschutz bei Bedarf zu konfigurieren.
     - Einstellungen für die <sup>\*</sup> Postfachintelligenz: Überprüfen Sie, ob die Option **"Postfachintelligenz aktivieren"** und **"Intelligenz für Identitätswechselschutz aktivieren"** ausgewählt ist.
     - Abschnitt **"Spoofing":** Überprüfen Sie, ob **die Spoofintelligenz** aktiviert ist.

     Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   - Abschnitt **"Aktionen":** Klicken Sie auf **"Aktionen bearbeiten",** und konfigurieren Sie die folgenden Einstellungen im Flyout **"Aktionen bearbeiten",** das geöffnet wird:
     - Abschnitt **"Nachrichtenaktionen":** Konfigurieren Sie die folgenden Einstellungen:
       - **Wenn die Nachricht als angenommener Benutzer erkannt wird:** <sup>\*</sup> Wählen Sie **"Nachricht unter Quarantäne stellen"** aus.
       - **Wenn die Nachricht als imitierte Domäne erkannt wird:** <sup>\*</sup> Wählen Sie **"Nachricht unter Quarantäne stellen"** aus.
       - **Wenn die Postfachintelligenz einen imitierten Benutzer erkennt:** <sup>\*</sup> Wählen Sie **"Nachricht in Junk-E-Mail-Ordner des Empfängers verschieben "** (Standard) oder **"Nachricht unter Quarantäne** stellen" (Streng) aus.
       - **Wenn die Nachricht als Spoofing erkannt wird:** Wählen Sie **"Nachricht in Junk-E-Mail-Ordner des Empfängers verschieben "** (Standard) oder **"Nachricht unter Quarantäne** stellen" (streng) aus.
     - **Sicherheitstipps & Indikatorenabschnitt:** Konfigurieren Sie die folgenden Einstellungen:
       - **Benutzeridentitätswechsel Sicherheitstipp** <sup>\*</sup> anzeigen: Auswählen (aktivieren).
       - Anzeigen des **Domänenidentitätswechsels Sicherheitstipp:** <sup>\*</sup> Auswählen (Aktivieren).
       - **Ungewöhnliche Zeichen für den Benutzeridentitätswechsel anzeigen Sicherheitstipp:** <sup>\*</sup> Auswählen (aktivieren).
       - **Show (?) for unauthenticated senders for spoof:** Select (turn on).
       - **Show "via" tag:** Select (turn on) if this setting is available.

     Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

   <sup>\*</sup>Diese Einstellung ist nur in Defender für Office 365 verfügbar.

4. Klicken Sie auf **"Speichern"** und dann auf **"Schließen".**

Ausführliche Anweisungen zum Konfigurieren von Antiphishingrichtlinien finden Sie unter [Konfigurieren von Antiphishingrichtlinien in EOP](configure-anti-phishing-policies-eop.md) und [Konfigurieren von Antiphishingrichtlinien in Microsoft Defender für Office 365.](configure-atp-anti-phishing-policies.md)

## <a name="part-3---anti-spam-protection-in-eop"></a>Teil 3 : Antispamschutz in EOP

Weitere Informationen zu den empfohlenen Einstellungen für Antispam finden Sie unter [EOP Antispamrichtlinieneinstellungen.](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)

1. Öffnen <https://security.microsoft.com/antispam> Sie .

2. Wählen Sie auf der Seite **"Antispamrichtlinien"** die Richtlinie mit dem Namen **"Eingehende Antispamrichtlinie" (Standard)** aus der Liste aus, indem Sie auf den Namen klicken.

3. Führen Sie im angezeigten Flyout mit den Richtliniendetails die folgenden Schritte aus:
   - **Schwellenwert für Massen-E-Mails & Abschnitt "Spameigenschaften":** Klicken Sie auf **"Spamschwellenwert und Eigenschaften bearbeiten".** Legen Sie im angezeigten **Spamschwellenwert und** eigenschaften-Flyout den Schwellenwert für **Massen-E-Mails** auf 5 (Streng) oder 6 (Standard) fest. Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.
   - Abschnitt **"Zulässige und blockierte Absender und Domänen":** Überprüfen oder bearbeiten Sie Ihre zulässigen Absender und zulässigen Domänen.

4. Klicken Sie nach Abschluss des Vorgangs auf **Schließen**.

Ausführliche Anweisungen zum Konfigurieren von Antispamrichtlinien finden Sie unter [Konfigurieren von Antispamrichtlinien in EOP.](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Teil 4 – Schutz vor bösartigen URLs und Dateien (sichere Links und sichere Anlagen in Defender für Office 365)

Der Time-of-Click-Schutz vor bösartigen URLs und Dateien ist in Abonnements verfügbar, die [Microsoft Defender für Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)enthalten. Sie wird über [Richtlinien](safe-attachments.md) für sichere Anlagen und [sichere Links](safe-links.md) eingerichtet.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Richtlinien für sichere Anlagen in Microsoft Defender für Office 365

Um [sichere Anlagen](safe-attachments.md)einzurichten, erstellen Sie mindestens eine Richtlinie für sichere Links.

1. Wählen Sie im [Security & Compliance Center](https://protection.office.com)die Option **"Threat Management** \> **Policy** \> **ATP Safe Attachments" aus,** und klicken Sie dann auf **"Erstellen".**

2. Konfigurieren Sie im **angezeigten** Assistenten für neue Richtlinien für sichere Anlagen die folgenden Einstellungen:

   - Geben Sie im **Feld "Name"** den Namen `Block malware` ein, und klicken Sie dann auf **"Weiter".**

   - Konfigurieren Sie auf der **Seite Einstellungen** die folgenden Einstellungen:
     - Wählen Sie im Abschnitt **"Sichere Anlagen– unbekannte Schadsoftwareantwort"** die Option **"Blockieren"** aus.
     - Wählen Sie im Abschnitt **"Umleitungsanlage"** die Option **"Umleitung aktivieren"** aus. Geben Sie die E-Mail-Adresse für den Sicherheitsadministrator oder -operator Ihrer Organisation an, der erkannte Dateien überprüft.

     Klicken Sie auf **Weiter**.

3. Klicken Sie auf der Seite **"Angewendet auf"** auf **"Bedingung hinzufügen",** wählen Sie **"Angewendet" aus, wenn: Die Empfängerdomäne ist,** klicken Sie auf **"Hinzufügen",** wählen Sie Ihre Domäne oder Domänen aus, klicken Sie auf **"Hinzufügen",** **"Fertig"** und dann auf **"Weiter".**

4. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **"Fertig stellen".**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Richtlinien für sichere Links in Microsoft Defender für Office 365

Um [sichere Links](safe-links.md)einzurichten, überprüfen und bearbeiten Sie Ihre globalen Einstellungen für sichere Links, und erstellen Sie mindestens eine Richtlinie für sichere Links.

1. Wählen Sie im [Security & Compliance Center](https://protection.office.com) **"Threat Management** \> **Policy** \> **ATP Safe Links"** aus, klicken Sie auf **"Globale Einstellungen",** und konfigurieren Sie dann die folgenden Einstellungen:

   - Überprüfen **Sie die Verwendung von sicheren Links in: Office 365 Anwendungen** aktiviert ist: ![ Umschalten ](../../media/scc-toggle-on.png) .
   - **Nicht nachverfolgen, wenn Benutzer auf "Sichere Links" klicken:** Deaktivieren Sie diese Einstellung, um Benutzerklicks nachzuverfolgen: ![ Umschalten ](../../media/scc-toggle-off.png) aus.
   - **Benutzer dürfen nicht durch sichere Links zur ursprünglichen URL klicken:** Überprüfen Sie, ob diese Einstellung aktiviert ist: ![ Umschalten ](../../media/scc-toggle-on.png) .

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

2. Klicken Sie zurück auf der Hauptseite für sichere Links auf **"Erstellen".**

3. Konfigurieren **Sie** im angezeigten Assistenten zum Erstellen von Richtlinien für sichere Links die folgenden Einstellungen:

   - Geben Sie im **Feld "Name"** einen Namen ein, z. B. `Safe Links` und klicken Sie dann auf **"Weiter".**

   - Konfigurieren Sie auf der **Seite Einstellungen** die folgenden Einstellungen:
     - **Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in Nachrichten** aus: **Aktivieren**.
     - **Wählen Sie die Aktion für unbekannte oder potenziell schädliche URLs in Microsoft Teams** aus: Wählen Sie **"Ein" aus.**
     - **Anwenden sicherer Links auf E-Mail-Nachrichten, die innerhalb der Organisation gesendet werden**
     - **Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht übermitteln.**
     - **Anwenden sicherer Links auf E-Mail-Nachrichten, die innerhalb der Organisation gesendet werden**
     - **Benutzern nicht gestatten, zur ursprünglichen URL zu klicken**

     Klicken Sie auf **Weiter**.

4. Klicken Sie auf der Seite **"Angewendet auf"** auf **"Bedingung hinzufügen",** wählen Sie **"Angewendet" aus, wenn: Die Empfängerdomäne ist,** klicken Sie auf **"Hinzufügen",** wählen Sie Ihre Domäne oder Domänen aus, klicken Sie auf **"Hinzufügen",** **"Fertig"** und dann auf **"Weiter".**

5. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **"Fertig stellen".**

Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für sichere Links](set-up-safe-links-policies.md).

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Teil 5: Überprüfen, ob sichere Anlagen für SharePoint, OneDrive und Microsoft Teams aktiviert sind

Workloads wie SharePoint, OneDrive und Teams werden für die Zusammenarbeit entwickelt. Die Verwendung von Defender für Office 365 hilft beim Blockieren und Erkennen von Dateien, die in Teamwebsites und Dokumentbibliotheken als bösartig erkannt werden. Weitere Informationen zur Funktionsweise finden Sie [hier.](mdo-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> **Bevor Sie mit diesem Verfahren beginnen, stellen Sie sicher, dass die Überwachungsprotokollierung für Ihre Microsoft 365 Umgebung bereits aktiviert ist.** Dies geschieht in der Regel von einer Person, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist. Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren der [Überwachungsprotokollsuche!](../../compliance/turn-audit-log-search-on-or-off.md)

1. Wählen Sie im [Security & Compliance Center](https://protection.office.com)die Option **"Threat Management** \> **Policy** \> **ATP Safe Attachments" aus,** und klicken Sie dann auf **"Globale Einstellungen".**

2. Vergewissern Sie sich, dass sich der Umschalter **"Defender für Office 365 für SharePoint", "OneDrive" und Microsoft Teams** auf der rechten Seite befindet: ![ "Einschalten", ](../../media/scc-toggle-on.png) und klicken Sie dann auf **"Speichern".**

3. Überprüfen (und ggf. bearbeiten) Sie die [Richtlinien für sichere Anlagen](set-up-safe-attachments-policies.md) und sichere [Links](set-up-safe-links-policies.md)In Ihrer Organisation.

4. (Empfohlen) Führen Sie als globaler Administrator oder SharePoint Onlineadministrator das Cmdlet **["Set-SPOTenant"](/powershell/module/sharepoint-online/Set-SPOTenant)** aus, wobei der Parameter _"DisallowInfectedFileDownload"_ auf ". `$true`

   - `$true` blockiert alle Aktionen (mit Ausnahme von Delete) für erkannte Dateien. Erkannte Dateien können nicht geöffnet, kopiert oder gemeinsam verwendet werden.
   - `$false` blockiert alle Aktionen außer "Löschen" und "Herunterladen". Personen können das Risiko akzeptieren und eine erkannte Datei herunterladen.

   > [!TIP]
   > Weitere Informationen zur Verwendung von PowerShell mit Microsoft 365 finden Sie unter [Verwalten von Microsoft 365 mit PowerShell.](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)

5. Es kann bis zu 30 Minuten dauern, bis ihre Änderungen auf alle Microsoft 365 Rechenzentren verteilt sind.

### <a name="now-set-up-alerts-for-detected-files"></a>Einrichten von Warnungen für erkannte Dateien

Um eine Benachrichtigung zu erhalten, wenn eine Datei in SharePoint Online-, OneDrive for Business- oder Microsoft Teams als bösartig erkannt wurde, können Sie eine Warnung einrichten.

1. Wählen Sie im [Security & Compliance Center](https://protection.office.com) **Warnungen** \> **verwalten** aus.

2. Wählen Sie **"Neue Warnungsrichtlinie"** aus.

3. Geben Sie einen Namen für die Warnung an. Sie können z. B. schädliche Dateien in Bibliotheken eingeben.

4. Geben Sie eine Beschreibung für die Warnung ein. Sie können beispielsweise Administratoren benachrichtigen, wenn schädliche Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.

5. Legen Sie im Abschnitt **"Send this alert when..."** Folgendes fest:

   a. Wählen Sie in der Liste **"Aktivitäten"** die Option **"Erkannte Schadsoftware" in der Datei** aus.

   b. Lassen Sie das Feld **Benutzer** leer.

6. Wählen Sie im Abschnitt **"Diese Warnung senden an..."** einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheitsleser aus, die eine Benachrichtigung erhalten sollen, wenn eine schädliche Datei erkannt wird.

7. **Speichern Sie**.

Weitere Informationen zu Warnungen finden Sie unter [Erstellen von Aktivitätswarnungen im Security & Compliance Center.](../../compliance/create-activity-alerts.md)

> [!NOTE]
> Wenn Sie die Konfiguration abgeschlossen haben, verwenden Sie diese Links, um Workloaduntersuchungen zu starten:
>
>- [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report)
>- [Verwenden des Security & Compliance Centers zum Verwalten von isolierten Dateien](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Vorgehensweise, wenn eine schädliche Datei in SharePoint Online, OneDrive oder Microsoft Teams gefunden wird](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Verwalten von isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Teil 6 – Zusätzliche Einstellungen zum Konfigurieren

Neben der Konfiguration des Schutzes vor Schadsoftware, bösartigen URLs und Dateien, Phishing und Spam wird empfohlen, die automatische Bereinigung zur Nullstunde zu konfigurieren.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Automatische Bereinigung zur Nullstunde für E-Mails in EOP

[Zap (Zero-Hour Auto Purge)](zero-hour-auto-purge.md) ist in Abonnements verfügbar, die [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)enthalten. Dieser Schutz ist standardmäßig aktiviert. Die folgenden Bedingungen müssen jedoch erfüllt sein, damit der Schutz wirksam ist:

- Spamaktionen sind in Antispamrichtlinien auf "Nachricht in [Junk-E-Mail-Ordner](anti-spam-protection.md) **verschieben"** festgelegt.

- Benutzer haben ihre [Standardeinstellungen für Junk-E-Mails](configure-junk-email-settings-on-exo-mailboxes.md)beibehalten und den Junk-E-Mail-Schutz nicht deaktiviert.

Weitere Informationen finden Sie unter Automatische Bereinigung zur [Nullstunde – Schutz vor Spam und Schadsoftware.](zero-hour-auto-purge.md)

## <a name="post-setup-tasks-and-next-steps"></a>Aufgaben nach dem Setup und nächste Schritte

Stellen Sie nach dem Konfigurieren der Bedrohungsschutzfeatures sicher, dass Sie überwachen, wie diese Features funktionieren! Überprüfen und überarbeiten Sie Ihre Richtlinien so, dass sie das tun, wozu Sie sie benötigen. Achten Sie außerdem auf neue Features und Dienstupdates, die einen Mehrwert bieten können.

****

|Vorgehensweise|Ressourcen mit mehr Informationen|
|---|---|
|Erfahren Sie, wie Die Funktionen zum Schutz vor Bedrohungen für Ihre Organisation funktionieren, indem Sie Berichte anzeigen.|[Sicherheitsdashboard](security-dashboard.md) <p> [E-Mail-Sicherheitsberichte](view-email-security-reports.md) <p> [Berichte für Microsoft Defender für Office 365](view-reports-for-mdo.md) <p> [Sicherheitsrisiken-Explorer](threat-explorer.md)|
|Überprüfen und Überarbeiten Ihrer Bedrohungsschutzrichtlinien in regelmäßigen Abständen nach Bedarf|[Sicherheitsbewertung](../defender/microsoft-secure-score.md) <p> [Intelligente Berichte und Einblicke](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 Funktionen für die Untersuchung und Reaktion auf Bedrohungen](./office-365-ti.md)|
|Auf neue Features und Dienstupdates achten|[Standard- und Targeted Release-Optionen](../../admin/manage/release-options-in-office-365.md) <p> [Nachrichtencenter](../../admin/manage/message-center.md) <p> [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Dienstbeschreibungen](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Erfahren Sie mehr über die empfohlenen Standard- und Strict-Sicherheitskonfigurationen für EOP und Defender für Office 365|[Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365 Sicherheit](recommended-settings-for-eop-and-office365.md)|
