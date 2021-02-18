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
description: Administratoren können mehr über den Bedrohungsschutz in Microsoft 365 erfahren und konfigurieren, wie er für Ihre Organisation verwendet wird.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c9ca420609628476faba6262fe7ed412b8fa5746
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288801"
---
# <a name="protect-against-threats"></a>Schutz vor Bedrohungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Hier ist eine Schnellstartanleitung, die die Konfiguration von Defender für Office 365 in Blöcke unterbricht. Wenn Sie noch nicht mit den Bedrohungsschutzfeatures in Office 365, nicht sicher sind, wo Sie beginnen sollten, oder wenn Sie dies am besten *erlernen,* verwenden Sie diese Anleitung als Prüfliste und Ausgangspunkt.

> [!IMPORTANT]
> **Die anfänglichen empfohlenen** Einstellungen sind für jede Art von Richtlinie enthalten. Es stehen jedoch zahlreiche Optionen zur Verfügung, und Sie können Ihre Einstellungen an die Anforderungen Ihrer Organisation anpassen. Es dauert ungefähr 30 Minuten, bis Ihre Richtlinien oder Änderungen ihren Weg durch Ihr Rechenzentrum finden.

## <a name="requirements"></a>Anforderungen

### <a name="subscriptions"></a>Abonnements

Bedrohungsschutzfunktionen sind in *allen Microsoft-* oder Office 365-Abonnements enthalten. Einige Abonnements verfügen jedoch über erweiterte Features. In der folgenden Tabelle sind die in diesem Artikel enthaltenen Schutzfeatures zusammen mit den Mindestanforderungen für Abonnements aufgeführt.

> [!TIP]
> Beachten Sie, dass über die Anweisungen  zum Aktivieren der Überwachung hinaus Schritte zum Starten von Ansoftware, Antiphishing und Antispam, die als Teil von Office 365 Exchange Online Protection (**EOP)** gekennzeichnet sind, beginnen. Dies mag in einem Defender für Office 365-Artikel ungerade erscheinen, bis Sie sich erinnern , dass (**Defender für Office 365**) EOP enthält und darauf aufbaut.

****

|Schutztyp|Abonnementanforderung|
|---|---|
|Überwachungsprotokollierung (zu Berichtszwecken)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Schutz vor Schadsoftware|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Antiphishingschutz|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Antispamschutz|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Automatische Bereinigung zur Nullstunde (für E-Mail)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Schutz vor schädlichen URLs und Dateien in E-Mails und Office-Dokumenten (sichere Links und sichere Anlagen)|[Microsoft Defender für Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Aktivieren von sicheren Anlagen für SharePoint-, OneDrive- und Microsoft #A0|[Defender für Office 365 ](atp-for-spo-odb-and-teams.md)|
|Erweiterter Antiphishingschutz|[Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Rollen und Berechtigungen

Zum Konfigurieren von Defender für Office 365-Richtlinien muss Ihnen im [Security & Compliance Center eine entsprechende Rolle zugewiesen werden.](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) In der folgenden Tabelle finden Sie Rollen, die diese Aktionen ausführen können.

****

|Rolle oder Rollengruppe|Weitere Informationen|
|---|---|
|Globaler Administrator|[Informationen zu Microsoft 365-Administratorrollen](../../admin/add-users/about-admin-roles.md)|
|Sicherheitsadministrator|[Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online-Organisationsverwaltung|[Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> und <p> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Weitere Informationen finden Sie unter ["Berechtigungen" im Security & Compliance Center.](permissions-in-the-security-and-compliance-center.md)

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Bevor Sie beginnen, aktivieren Sie die Überwachungsprotokollierung für Berichte und Untersuchungen.

Starten Sie die Überwachungsprotokollierung frühzeitig. Für bestimmte der folgenden  Schritte muss die Überwachung aktiviert sein. Die Überwachungsprotokollierung ist in Abonnements verfügbar, die [Exchange Online enthalten.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) Zum Anzeigen von Daten in Bedrohungsschutzberichten, [](view-email-security-reports.md)z. B. dem [Sicherheitsdashboard,](security-dashboard.md)E-Mail-Sicherheitsberichten und [Explorer,](threat-explorer.md)muss die Überwachungsprotokollierung ein *sein.* Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren [der Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>Teil 1: Schutz vor Schadsoftware

[Der Schutz vor Schadsoftware](anti-malware-protection.md) ist in Abonnements verfügbar, die [EOP enthalten.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die Option "Richtlinie für die **Bedrohungsverwaltung** \>  \> **– Schadsoftware" aus.**

2. Doppelklicken Sie auf die **Standardrichtlinie,** und wählen Sie dann Einstellungen **aus.**

3. Geben Sie die folgenden Einstellungen an:

    - Behalten Sie **im Abschnitt "Reaktion** auf Schadsoftwareerkennung" die Standardeinstellung **"Nein" bei.**

    - Wählen Sie **im Abschnitt "Filter für allgemeine Anlagentypen"** die Option **"Ein" aus.**

4. Klicken Sie auf **Speichern**.

Weitere Informationen zu Den Optionen für Ansoftwarerichtlinien finden Sie unter ["Konfigurieren von An malware-Richtlinien".](configure-anti-malware-policies.md)

## <a name="part-2---anti-phishing-protection"></a>Teil 2: Antiphishingschutz

[Antiphishingschutz](anti-phishing-protection.md) ist in Abonnements verfügbar, die [EOP enthalten.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Erweiterter Antiphishingschutz ist in [Defender für Office 365 verfügbar.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

Im folgenden Verfahren wird beschrieben, wie Sie eine Antiphishingrichtlinie in Microsoft Defender für Office 365 konfigurieren. Die Schritte ähneln dem Konfigurieren einer Antiphishingrichtlinie in EOP.

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die **Atp-Antiphishing-Richtlinie** zur \>  \> **Bedrohungsverwaltung aus.**

2. Klicken Sie **auf "Standardrichtlinie".**

3. Klicken Sie **im Abschnitt "Identitätswechsel"** auf **"Bearbeiten",** und geben Sie dann die folgenden Einstellungen an:

   - Aktivieren Sie **auf der Registerkarte "Benutzer zum Schützen** hinzufügen" *den* Schutz. Fügen Sie dann Benutzer hinzu, z. B. die Boardmitglieder Ihrer Organisation, Ihren CEO, CFO und andere führungskräfte. (Sie können eine einzelne E-Mail-Adresse eingeben oder auf eine Liste klicken.)

   - Aktivieren Sie **auf der Registerkarte "Domänen zum Schützen** hinzufügen" die Domänen, die ich **habe, automatisch mit ein.** Wenn Sie über benutzerdefinierte Domänen verfügen, fügen Sie sie jetzt hinzu.

   - Wählen Sie **auf der** Registerkarte "Aktionen" die Option zum Isolieren der Nachricht für den imitierten Benutzer und die Optionen für die  **imitierte Domäne** aus.  Aktivieren Sie außerdem Tipps zur Identitätswechselsicherheit.

   - Stellen Sie auf der Registerkarte "Postfachintelligenz" sicher, dass die Postfachintelligenz aktiviert ist, und aktivieren Sie den Schutz vor postfachintelligenzbasiertem Identitätswechsel.  Wählen Sie **in der Liste "Wenn E-Mails von einer imitierten Benutzerliste** gesendet werden" die Option **"Nachricht isolieren" aus.**

   - Geben Sie **auf der Registerkarte Vertrauenswürdige Absender** und Domänen hinzufügen alle vertrauenswürdigen Absender oder Domänen an, die Sie hinzufügen möchten.

   - **Speichern** Sie auf der **Registerkarte "Einstellungen überprüfen",** nachdem Sie Ihre Einstellungen überprüft haben.

4. Klicken Sie **im Abschnitt "Spoofing"** auf **"Bearbeiten",** und geben Sie dann die folgenden Einstellungen an:

   - Stellen Sie **auf der Registerkarte "Spoofingfiltereinstellungen"** sicher, dass der Antis spoofingschutz aktiviert ist.

   - Wählen Sie **auf der** Registerkarte "Aktionen" die Option **"Nachricht isolieren" aus.**

   - **Speichern** Sie auf der Registerkarte **"Einstellungen überprüfen",** nachdem Sie Ihre Änderungen überprüft haben. (Wenn Sie keine Änderungen vorgenommen haben, brechen **Sie ab.)**

5. Schließen Sie die Seite mit den Standardrichtlinieneinstellungen.

Weitere Informationen zu Ihren Antiphishingrichtlinienoptionen finden Sie unter "Konfigurieren von [Antiphishingrichtlinien in Microsoft Defender für Office 365".](configure-atp-anti-phishing-policies.md)

## <a name="part-3---anti-spam-protection"></a>Teil 3: Antispamschutz

[Antispamschutz](anti-spam-protection.md) ist in Abonnements verfügbar, die [EOP enthalten.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die Option "Antispamrichtlinie für die  \>  \> **Bedrohungsverwaltung" aus.**

2. Aktivieren Sie **auf** der Registerkarte "Benutzerdefiniert" die benutzerdefinierten Einstellungen.

3. Erweitern **Sie die Standardfilterrichtlinie für Spam,** klicken Sie auf "Richtlinie **bearbeiten",** und geben Sie dann die folgenden Einstellungen an:

   - Legen Sie **im Abschnitt "Spam-** und Massenaktionen" den Schwellenwert auf den Wert 5 oder 6.

   - Überprüfen **(und/oder** bearbeiten) Sie im Abschnitt "Zugelassene Listen" Ihre zulässigen Absender und Domänen.

4. Klicken Sie auf **Speichern**.

Weitere Informationen zu Ihren Antispamrichtlinienoptionen finden Sie unter ["Konfigurieren von Antispamrichtlinien in EOP".](configure-your-spam-filter-policies.md)

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Teil 4: Schutz vor bösartigen URLs und Dateien (sichere Links und sichere Anlagen in Defender für Office 365)

Der Time-of-Click-Schutz vor bösartigen URLs und Dateien ist in Abonnements verfügbar, die [Microsoft Defender für Office 365 enthalten.](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) Sie wird über Richtlinien für sichere [Anlagen](atp-safe-attachments.md) und sichere [Links](atp-safe-links.md) eingerichtet.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Richtlinien für sichere Anlagen in Microsoft Defender für Office 365

Erstellen Sie zum Einrichten [von](atp-safe-attachments.md)sicheren Anlagen mindestens eine Richtlinie für sichere Links.

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die Bedrohungsverwaltungsrichtlinie  \>  \> **"ATP Sichere Anlagen"** aus, und klicken Sie dann auf **"Erstellen".**

2. Konfigurieren Sie **im angezeigten** Assistenten für neue Richtlinien für sichere Anlagen die folgenden Einstellungen:

   - Geben Sie **im Feld "Name"** `Block malware` den Namen ein, und klicken Sie dann auf **"Weiter".**

   - Konfigurieren Sie **auf der** Seite "Einstellungen" die folgenden Einstellungen:
     - Wählen Sie **im Abschnitt "Sichere Anlagen unbekannte Schadsoftwareantwort"** die Option **"Blockieren" aus.**
     - Wählen Sie **im Abschnitt "Umleitungsanlage"** die Option **"Umleitung aktivieren" aus.** Geben Sie die E-Mail-Adresse für den Sicherheitsadministrator oder -operator Ihrer Organisation an, der erkannte Dateien überprüft.

     Klicken Sie auf **Weiter**.

3. On the **Applied to** page, click Add **a condition**, choose Applied **if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.

4. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **"Fertig stellen".**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Richtlinien für sichere Links in Microsoft Defender für Office 365

Überprüfen und bearbeiten Sie [zum](atp-safe-links.md)Einrichten von sicheren Links Ihre globalen Einstellungen für sichere Links, und erstellen Sie mindestens eine Richtlinie für sichere Links.

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die Bedrohungsverwaltungsrichtlinie  \>  \> **"ATP-sichere** Links" aus, klicken Sie auf **"Globale** Einstellungen", und konfigurieren Sie dann die folgenden Einstellungen:

   - Überprüfen **Sie die Verwendung sicherer Links in: Office 365-Anwendungen** sind aktiviert: ![ Umschalten. ](../../media/scc-toggle-on.png)
   - **Nicht nachverfolgen, wenn Benutzer auf "Sichere Links"** klicken: Deaktivieren Sie diese Einstellung, um Benutzerklicks nachverfolgt zu werden: ![ Umschalten ](../../media/scc-toggle-off.png) aus.
   - **Benutzer dürfen keine sicheren Links** zur ursprünglichen URL durchklicken: Überprüfen Sie, ob diese Einstellung aktiviert ist: ![ Umschalten. ](../../media/scc-toggle-on.png)

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

2. Klicken Sie wieder auf der Hauptseite für sichere Links auf **"Erstellen".**

3. Konfigurieren Sie **im angezeigten Assistenten** zum Erstellen von Richtlinien für sichere Links die folgenden Einstellungen:

   - Geben Sie **im Feld "Name"** einen Namen wie z. B. `Safe Links` ein, und klicken Sie dann auf **"Weiter".**

   - Konfigurieren Sie **auf der** Seite "Einstellungen" die folgenden Einstellungen:
     - **Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in Nachrichten aus:** Wählen Sie **"Ein" aus.**
     - **Wählen Sie die Aktion für unbekannte oder potenziell schädliche URLs in Microsoft Teams** aus: Wählen Sie **"Ein" aus.**
     - **Anwenden sicherer Links auf innerhalb der Organisation gesendete E-Mail-Nachrichten**
     - **Warten, bis die URL-Überprüfung abgeschlossen ist, bevor die Nachricht zu senden ist**
     - **Anwenden sicherer Links auf innerhalb der Organisation gesendete E-Mail-Nachrichten**
     - **Benutzer dürfen nicht zur ursprünglichen URL klicken**

     Klicken Sie auf **Weiter**.

4. On the **Applied to** page, click Add **a condition**, choose Applied **if: The recipient domain is**, click **Add**, select your domain or domains, click **Add**, click **Done**, and then click **Next**.

5. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **"Fertig stellen".**

Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für sichere Links](set-up-atp-safe-links-policies.md).

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Teil 5 : Überprüfen, ob sichere Anlagen für SharePoint, OneDrive und Microsoft Teams aktiviert sind

Workloads wie SharePoint, OneDrive und Teams sind für die Zusammenarbeit erstellt. Die Verwendung von Defender für Office 365 hilft beim Blockieren und Erkennen von Dateien, die in Teamwebsites und Dokumentbibliotheken als bösartig identifiziert werden. Weitere Informationen dazu finden Sie [hier.](atp-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> Bevor Sie mit diesem Verfahren beginnen, stellen Sie sicher, dass die **Überwachungsprotokollierung für Ihre Microsoft 365-Umgebung bereits aktiviert ist.** Dies wird in der Regel von einer Person durchgeführt, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist. Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren [der Überwachungsprotokollsuche!](../../compliance/turn-audit-log-search-on-or-off.md)

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die  \>  \> Bedrohungsverwaltungsrichtlinie **"ATP Sichere** Anlagen" aus, und klicken Sie dann auf **"Globale Einstellungen".**

2. Stellen Sie sicher, dass der Umschalter **"Turn on Defender for Office 365 for SharePoint", "OneDrive" und "Microsoft Teams"** auf der rechten Seite ist: Umschalten auf , und klicken Sie dann auf ![ ](../../media/scc-toggle-on.png) **"Speichern".**

3. Überprüfen (und bearbeiten Sie gegebenenfalls) die Richtlinien für sichere Anlagen und [sichere](set-up-atp-safe-attachments-policies.md) Links in [Ihrer Organisation.](set-up-atp-safe-links-policies.md)

4. (Empfohlen) Führen Sie als globaler Administrator oder SharePoint Online-Administrator das **[Cmdlet "Set-SPOTenant"](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** aus, bei dem der Parameter _"DisallowInfectedFileDownload"_ auf " festgelegt `$true` ist.

   - `$true` blockiert alle Aktionen (mit Ausnahme von "Löschen") für erkannte Dateien. Erkannte Dateien können nicht geöffnet, kopiert oder gemeinsam verwendet werden.
   - `$false` blockiert alle Aktionen mit Ausnahme von "Löschen" und "Herunterladen". Benutzer können das Risiko akzeptieren und eine erkannte Datei herunterladen.

   > [!TIP]
   > Weitere Informationen zur Verwendung von PowerShell mit Microsoft 365 finden Sie unter Verwalten von [Microsoft 365 mit PowerShell.](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)

5. Es kann bis zu 30 Minuten dauern, bis Ihre Änderungen auf alle Microsoft 365-Rechenzentren verteilt sind.

### <a name="now-set-up-alerts-for-detected-files"></a>Einrichten von Warnungen für erkannte Dateien

Um eine Benachrichtigung zu erhalten, wenn eine Datei in SharePoint Online, OneDrive for Business oder Microsoft Teams als bösartig identifiziert wurde, können Sie eine Warnung einrichten.

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die Option "Warnungen  \> **verwalten" aus.**

2. Wählen **Sie "Neue Warnungsrichtlinie" aus.**

3. Geben Sie einen Namen für die Warnung an. Sie können z. B. bösartige Dateien in Bibliotheken eingeben.

4. Geben Sie eine Beschreibung für die Warnung ein. Sie können beispielsweise "Administratoren benachrichtigen" eingeben, wenn bösartige Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.

5. Legen Sie **im Abschnitt "Senden Sie diese Warnung, wenn...** " dies vor:

   a. Wählen Sie **in der Liste** "Aktivitäten" die Option **"Erkannte Schadsoftware" in der Datei aus.**

   b. Lassen Sie das **Feld "Benutzer"** leer.

6. Wählen Sie im Abschnitt "Diese Warnung senden **an...** " einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheitsleser aus, die eine Benachrichtigung erhalten sollen, wenn eine schädliche Datei erkannt wird.

7. **Speichern**.

Weitere Informationen zu Warnungen finden Sie unter ["Erstellen von Aktivitätswarnungen" im Security & Compliance Center.](../../compliance/create-activity-alerts.md)

> [!NOTE]
> Wenn Sie die Konfiguration abgeschlossen haben, verwenden Sie die folgenden Links, um Arbeitsauslastungsuntersuchungen zu starten:
>
>- [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report)
>- [Verwenden des Security & Compliance Center zum Verwalten von Isolierten Dateien](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Was zu tun ist, wenn eine schädliche Datei in SharePoint Online, OneDrive oder Microsoft Teams gefunden wird](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Verwalten von Isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Teil 6: Zusätzliche zu konfigurierende Einstellungen

Neben der Konfiguration des Schutzes vor Schadsoftware, schädlichen URLs und Dateien, Phishing und Spam wird empfohlen, die automatische Bereinigung zur Nullstunde zu konfigurieren.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Automatisches Löschen zur Nullstunde für E-Mails in EOP

[Zap (Zero-Hour Auto Purge)](zero-hour-auto-purge.md) ist in Abonnements verfügbar, die [EOP enthalten.](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Dieser Schutz ist standardmäßig aktiviert. Die folgenden Bedingungen müssen jedoch erfüllt sein, damit der Schutz wirksam wird:

- Spamaktionen werden in Antispamrichtlinien auf "Nachricht in [Junk-E-Mail-Ordner verschieben" festgelegt.](anti-spam-protection.md) 

- Benutzer haben ihre Standardeinstellungen für [Junk-E-Mail beibehalten](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)und den Junk-E-Mail-Schutz nicht deaktiviert.

Weitere Informationen finden Sie unter "Automatische Bereinigung zur Nullstunde [- Schutz vor Spam und Schadsoftware".](zero-hour-auto-purge.md)

## <a name="post-setup-tasks-and-next-steps"></a>Aufgaben nach dem Setup und nächste Schritte

Nachdem Sie die Bedrohungsschutzfeatures konfiguriert haben, müssen Sie die Funktionsweise dieser Features überwachen! Überprüfen und überarbeiten Sie Ihre Richtlinien, damit sie die von Ihnen benötigten Maßnahmen erhalten. Achten Sie außerdem auf neue Features und Dienstupdates, die einen Mehrwert bieten können.

****

|Vorgehensweise|Ressourcen mit mehr Informationen|
|---|---|
|Sehen Sie sich die Funktionsweise von Bedrohungsschutzfeatures für Ihre Organisation an, indem Sie Berichte anzeigen.|[Sicherheitsdashboard](security-dashboard.md) <p> [E-Mail-Sicherheitsberichte](view-email-security-reports.md) <p> [Berichte für Microsoft Defender für Office 365](view-reports-for-atp.md) <p> [Sicherheitsrisiken-Explorer](threat-explorer.md)|
|Überprüfen und überarbeiten Sie Ihre Richtlinien zum Schutz vor Bedrohungen regelmäßig nach Bedarf.|[Sicherheitsbewertung](../mtp/microsoft-secure-score.md) <p> [Intelligente Berichte und Einblicke](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 Threat Investigation and Response Features](keep-users-safe-with-office-365-ti.md)|
|Auf neue Features und Dienstupdates achten|[Standard- und Zielversionsoptionen](../../admin/manage/release-options-in-office-365.md) <p> [Nachrichtencenter](../../admin/manage/message-center.md) <p> [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Dienstbeschreibungen](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Erfahren Sie mehr über die empfohlenen Standard- und Strict-Sicherheitskonfigurationen für EOP und Defender für Office 365.|[Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365-Sicherheit](recommended-settings-for-eop-and-office365-atp.md)|
