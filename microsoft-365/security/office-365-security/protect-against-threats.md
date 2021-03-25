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
ms.openlocfilehash: 189325dab37a548c717cd554ecd1d37c19ae57ea
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51205795"
---
# <a name="protect-against-threats"></a>Schutz vor Bedrohungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Hier finden Sie eine Schnellstartanleitung, die die Konfiguration von Defender für Office 365 in Blöcke aufbricht. Wenn Sie mit Denkschutzfeatures in Office 365 neu sind, nicht sicher sind, wo sie beginnen sollen, oder wenn Sie dies am besten *lernen,* verwenden Sie diese Anleitung als Prüfliste und Ausgangspunkt.

> [!IMPORTANT]
> **Erste empfohlene Einstellungen sind für** jede Art von Richtlinie enthalten. Es stehen jedoch viele Optionen zur Verfügung, und Sie können Ihre Einstellungen an die Anforderungen Ihrer organisation anpassen. Lassen Sie ungefähr 30 Minuten, bis Ihre Richtlinien oder Änderungen ihren Weg durch Ihr Datencenter finden.

## <a name="requirements"></a>Anforderungen

### <a name="subscriptions"></a>Abonnements

Bedrohungsschutzfunktionen sind in *allen Microsoft-* oder Office 365-Abonnements enthalten. Einige Abonnements verfügen jedoch über erweiterte Features. In der folgenden Tabelle sind die in diesem Artikel enthaltenen Schutzfunktionen zusammen mit den Mindestabonnementanforderungen aufgeführt.

> [!TIP]
> Beachten Sie, dass über die Anweisungen  zum Aktivieren der Überwachung hinaus Schritte zum Starten von Schadsoftware, Antiphishing und Antispam beginnen, die als Teil von Office 365 Exchange Online Protection (**EOP**) gekennzeichnet sind. Dies kann in einem Defender for Office 365-Artikel seltsam erscheinen, bis Sie sich erinnern (**Defender for Office 365**) enthält EOP und baut darauf auf.

****

|Schutztyp|Abonnementanforderung|
|---|---|
|Überwachungsprotokollierung (zu Berichtszwecken)|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Schutz vor Schadsoftware|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|Antiphishingschutz|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Antispamschutz|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Automatisches Löschen in null Stunden (für E-Mails)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Schutz vor schädlichen URLs und Dateien in E-Mail- und Office-Dokumenten (sichere Links und sichere Anlagen)|[Microsoft Defender für Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|Aktivieren sicherer Anlagen für SharePoint-, OneDrive- und Microsoft #A0|[Defender für Office 365 ](turn-on-mdo-for-spo-odb-and-teams.md)|
|Erweiterter Antiphishingschutz|[Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Rollen und Berechtigungen

Zum Konfigurieren von Defender für Office 365-Richtlinien muss Ihnen eine entsprechende Rolle im [Security & Compliance Center zugewiesen werden.](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center) In der folgenden Tabelle finden Sie Rollen, die diese Aktionen ausführen können.

****

|Rolle oder Rollengruppe|Weitere Informationen|
|---|---|
|globaler Administrator|[Informationen zu Microsoft 365-Administratorrollen](../../admin/add-users/about-admin-roles.md)|
|Sicherheitsadministrator|[Administratorrollenberechtigungen in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online-Organisationsverwaltung|[Berechtigungen in Exchange Online](/exchange/permissions-exo/permissions-exo) <p> und <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|

Weitere Informationen finden Sie unter [Berechtigungen im Security & Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Bevor Sie beginnen, aktivieren Sie die Überwachungsprotokollierung für Berichte und Untersuchungen.

Starten Sie die Überwachungsprotokollierung frühzeitig. Die Überwachung muss für **bestimmte** der folgenden Schritte eins sein. Die Überwachungsprotokollierung ist in Abonnements verfügbar, die [Exchange Online enthalten.](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description) Zum Anzeigen von Daten in Bedrohungsschutzberichten, [](view-email-security-reports.md)wie z. B. dem Sicherheitsdashboard, E-Mail-Sicherheitsberichten und [Explorer,](threat-explorer.md)muss die Überwachungsprotokollierung *auf lauten.* [](security-dashboard.md) Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren [der Überwachungsprotokollsuche.](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="part-1---anti-malware-protection"></a>Teil 1 – Schutz vor Schadsoftware

[Der Schutz vor Schadsoftware](anti-malware-protection.md) ist in Abonnements verfügbar, die [EOP enthalten.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die Option **Bedrohungsverwaltungsrichtlinie** \>  \> **An malware aus.**

2. Doppelklicken Sie auf **die Standardrichtlinie,** und wählen Sie dann **Einstellungen aus.**

3. Geben Sie die folgenden Einstellungen an:

    - Behalten Sie **im Abschnitt** Reaktion auf die Schadsoftwareerkennung die Standardeinstellung **Nein bei.**

    - Wählen Sie **im Abschnitt Filter für allgemeine Anlagentypen** die Option Ein **aus.**

4. Klicken Sie auf **Speichern**.

Weitere Informationen zu Optionen für An malware-Richtlinien finden Sie unter [Configure anti-malware policies](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection"></a>Teil 2 – Schutz vor Phishing

[Antiphishingschutz](anti-phishing-protection.md) ist in Abonnements verfügbar, die [EOP enthalten.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Erweiterter Antiphishingschutz ist in [Defender for Office 365 verfügbar.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)

Im folgenden Verfahren wird beschrieben, wie Sie eine Antiphishingrichtlinie in Microsoft Defender für Office 365 konfigurieren. Die Schritte ähneln dem Konfigurieren einer Antiphishingrichtlinie in EOP.

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die Option **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP-Antiphishing aus.**

2. Klicken Sie **auf Standardrichtlinie**.

3. Klicken Sie **im Abschnitt Identitätswechsel** auf **Bearbeiten**, und geben Sie dann die folgenden Einstellungen an:

   - Aktivieren Sie **auf der Registerkarte Benutzer zum Schützen** hinzufügen den *Schutz.* Fügen Sie dann Benutzer hinzu, z. B. die Vorratsmitglieder Ihrer Organisation, Ihren CEO, CFO und andere leitende Führungskräfte. (Sie können eine einzelne E-Mail-Adresse eingeben oder auf klicken, um eine Liste angezeigt zu werden.)

   - Aktivieren Sie auf der Registerkarte Zu **schützende** Domänen hinzufügen **automatisch die Domänen,** die ich habe. Wenn Sie über benutzerdefinierte Domänen verfügen, fügen Sie sie jetzt hinzu.

   - Wählen Sie auf **der** Registerkarte Aktionen  die Option Nachricht **sowohl** für den identitätswechselten Benutzer als auch für die **Identitätswechseldomäne isolieren** aus. Aktivieren Sie außerdem Tipps zur Identitätswechselsicherheit.

   - Stellen Sie **auf der** Registerkarte Postfachintelligenz sicher, dass die Postfachintelligenz aktiviert ist, und aktivieren Sie den Schutz vor Identitätswechseln auf Postfachintelligenz. Wählen Sie **in der Liste Wenn E-Mails von einem imitierten** Benutzer gesendet werden, die Option Nachricht **isolieren aus.**

   - Geben Sie **auf der Registerkarte vertrauenswürdige** Absender und Domänen hinzufügen alle vertrauenswürdigen Absender oder Domänen an, die Sie hinzufügen möchten.

   - **Speichern** Sie auf der Registerkarte Einstellungen **überprüfen,** nachdem Sie Ihre Einstellungen überprüft haben.

4. Klicken Sie **im Abschnitt Spoof** auf **Bearbeiten**, und geben Sie dann die folgenden Einstellungen an:

   - Stellen Sie auf der Registerkarte **Spoofingfiltereinstellungen** sicher, dass der Schutz vor Spoofing aktiviert ist.

   - Wählen Sie **auf der** Registerkarte Aktionen die Option **Nachricht isolieren aus.**

   - **Speichern** Sie auf der **Registerkarte Einstellungen überprüfen,** nachdem Sie Ihre Änderungen überprüft haben. (Wenn Sie keine Änderungen vorgenommen **haben,** abbrechen .)

5. Schließen Sie die Seite mit den Standardrichtlinieneinstellungen.

Weitere Informationen zu Ihren Antiphishingrichtlinienoptionen finden Sie unter [Configure anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection"></a>Teil 3 – Antispamschutz

[Antispamschutz ist](anti-spam-protection.md) in Abonnements verfügbar, die [EOP enthalten.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die Option **Bedrohungsverwaltungsrichtlinie** \>  \> **Antispam aus.**

2. Aktivieren Sie **auf** der Registerkarte Benutzerdefinierte Einstellungen benutzerdefinierte Einstellungen.

3. Erweitern **Sie Die Standardmäßige Spamfilterrichtlinie,** klicken **Sie auf Richtlinie bearbeiten,** und geben Sie dann die folgenden Einstellungen an:

   - Legen Sie **im Abschnitt Spam-** und Massenaktionen den Schwellenwert auf den Wert 5 oder 6.

   - Überprüfen **(und/oder** bearbeiten) Sie im Abschnitt Listen zulassen Ihre zulässigen Absender und Domänen.

4. Klicken Sie auf **Speichern**.

Weitere Informationen zu Ihren Antispamrichtlinienoptionen finden Sie unter [Configure anti-spam policies in EOP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>Teil 4 – Schutz vor schädlichen URLs und Dateien (Sichere Links und sichere Anlagen in Defender für Office 365)

Der Schutz vor schädlichen URLs und Dateien ist in Abonnements verfügbar, die [Microsoft Defender für Office 365 enthalten.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) Es wird über Richtlinien für sichere [Anlagen und](safe-attachments.md) [sichere Links](safe-links.md) eingerichtet.

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>Richtlinien für sichere Anlagen in Microsoft Defender für Office 365

Erstellen Sie zum Einrichten [sicherer Anlagen](safe-attachments.md)mindestens eine Richtlinie für sichere Links.

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die Option **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP Sichere** Anlagen aus, und klicken Sie dann auf **Erstellen**.

2. Konfigurieren Sie **im angezeigten** Richtlinien-Assistenten für neue sichere Anlagen die folgenden Einstellungen:

   - Geben Sie **im Feld Name** `Block malware` ein, und klicken Sie dann auf **Weiter**.

   - Konfigurieren Sie **auf** der Seite Einstellungen die folgenden Einstellungen:
     - Wählen Sie **im Abschnitt Sichere Anlagen unbekannte Schadsoftwareantwort** die Option Blockieren **aus.**
     - Wählen Sie **im Abschnitt Umleitungsanlage** die Option Umleitung aktivieren **aus.** Geben Sie die E-Mail-Adresse für den Sicherheitsadministrator oder -operator Ihrer Organisation an, der erkannte Dateien überprüft.

     Klicken Sie auf **Weiter**.

3. Klicken Sie **auf** der Seite Angewendet auf auf Bedingung **hinzufügen,** wählen Sie Angewendet aus, **wenn:** Die Empfängerdomäne ist , klicken Sie auf **Hinzufügen,** wählen Sie Ihre Domäne oder Domänen aus, klicken Sie auf Hinzufügen **,** klicken Sie auf **Fertig**, und klicken Sie dann auf **Weiter**.

4. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen.**

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>Richtlinien für sichere Links in Microsoft Defender für Office 365

Zum Einrichten sicherer [Links](safe-links.md)überprüfen und bearbeiten Sie Ihre globalen Einstellungen für sichere Links, und erstellen Sie mindestens eine Richtlinie für sichere Links.

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die Option Bedrohungsverwaltungsrichtlinie  \>  \> **ATP Sichere Links** aus, und klicken Sie auf **Globale** Einstellungen, und konfigurieren Sie dann die folgenden Einstellungen:

   - Überprüfen Sie, ob Sichere **Links verwenden in: Office 365-Anwendungen** aktiviert ist: ![ Umschalten auf ](../../media/scc-toggle-on.png) .
   - **Nicht nachverfolgen, wenn Benutzer auf Sichere Links klicken:** Deaktivieren Sie diese Einstellung, um Benutzerklicks nachverfolgt zu ![ werden: Umschalten ](../../media/scc-toggle-off.png) .
   - **Benutzer dürfen nicht auf sichere Links** zur ursprünglichen URL klicken: Überprüfen Sie, ob diese Einstellung aktiviert ist: ![ Umschalten auf ](../../media/scc-toggle-on.png) .

   Klicken Sie nach Abschluss des Vorgangs auf **Speichern**.

2. Klicken Sie wieder auf der Hauptseite für sichere Links auf **Erstellen**.

3. Konfigurieren Sie **im angezeigten** Assistenten zum Erstellen sicherer Links die folgenden Einstellungen:

   - Geben Sie **im Feld Name** einen Namen ein, z. B. , und klicken Sie dann auf `Safe Links` **Weiter**.

   - Konfigurieren Sie **auf** der Seite Einstellungen die folgenden Einstellungen:
     - Wählen Sie die Aktion für unbekannte potenziell schädliche **URLs in Nachrichten aus:** Wählen Sie **Ein aus.**
     - **Wählen Sie die Aktion für unbekannte oder potenziell** schädliche URLs in Microsoft Teams aus: Wählen Sie ein **aus.**
     - **Anwenden sicherer Links auf E-Mail-Nachrichten, die innerhalb der Organisation gesendet werden**
     - **Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor sie die Nachricht zu senden.**
     - **Anwenden sicherer Links auf E-Mail-Nachrichten, die innerhalb der Organisation gesendet werden**
     - **Benutzer dürfen nicht zur ursprünglichen URL klicken**

     Klicken Sie auf **Weiter**.

4. Klicken Sie **auf** der Seite Angewendet auf auf Bedingung **hinzufügen,** wählen Sie Angewendet aus, **wenn:** Die Empfängerdomäne ist , klicken Sie auf **Hinzufügen,** wählen Sie Ihre Domäne oder Domänen aus, klicken Sie auf Hinzufügen **,** klicken Sie auf **Fertig**, und klicken Sie dann auf **Weiter**.

5. Überprüfen Sie Ihre Einstellungen, und klicken Sie dann auf **Fertig stellen.**

Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für sichere Links](set-up-safe-links-policies.md).

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>Teil 5 – Überprüfen, ob sichere Anlagen für SharePoint, OneDrive und Microsoft Teams aktiviert sind

Arbeitsauslastungen wie SharePoint, OneDrive und Teams sind für die Zusammenarbeit erstellt. Die Verwendung von Defender für Office 365 hilft beim Blockieren und Erkennen von Dateien, die in Teamwebsites und Dokumentbibliotheken als schadhaft identifiziert werden. Weitere Informationen dazu finden Sie [hier.](mdo-for-spo-odb-and-teams.md)

> [!IMPORTANT]
> Bevor Sie mit diesem Verfahren beginnen, stellen Sie sicher, dass die Überwachungsprotokollierung für Ihre **Microsoft 365-Umgebung** bereits aktiviert ist. Dies wird in der Regel von einer Person durchgeführt, der die Rolle Überwachungsprotokolle in Exchange Online zugewiesen ist. Weitere Informationen finden Sie unter Aktivieren oder Deaktivieren [der Überwachungsprotokollsuche](../../compliance/turn-audit-log-search-on-or-off.md)!

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die Option **Bedrohungsverwaltungsrichtlinie** \>  \> **ATP Sichere** Anlagen aus, und klicken Sie dann auf Globale **Einstellungen**.

2. Überprüfen Sie, ob der Umschalter Aktivieren von **Defender für Office 365 für SharePoint, OneDrive** und Microsoft Teams nach rechts ist: Umschalten auf , und klicken Sie dann ![ auf ](../../media/scc-toggle-on.png) **Speichern**.

3. Überprüfen (und bearbeiten Sie gegebenenfalls) die Richtlinien für sichere Anlagen in Ihrer Organisation [und](set-up-safe-attachments-policies.md) Richtlinien für [sichere Links](set-up-safe-links-policies.md).

4. (Empfohlen) Führen Sie als globaler Administrator oder SharePoint Online-Administrator das **[Cmdlet Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** aus, und der _Parameter DisallowInfectedFileDownload_ ist auf `$true` festgelegt.

   - `$true` blockiert alle Aktionen (mit Ausnahme von Delete) für erkannte Dateien. Erkannte Dateien können nicht geöffnet, kopiert oder gemeinsam verwendet werden.
   - `$false` blockiert alle Aktionen mit Ausnahme von Löschen und Herunterladen. Die Benutzer können das Risiko akzeptieren und eine erkannte Datei herunterladen.

   > [!TIP]
   > Weitere Informationen zur Verwendung von PowerShell mit Microsoft 365 finden Sie unter [Manage Microsoft 365 with PowerShell](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md).

5. Erlauben Sie bis zu 30 Minuten, bis Ihre Änderungen auf alle Microsoft 365-Rechenzentren verteilt werden.

### <a name="now-set-up-alerts-for-detected-files"></a>Einrichten von Warnungen für erkannte Dateien

Um eine Benachrichtigung zu erhalten, wenn eine Datei in SharePoint Online, OneDrive for Business oder Microsoft Teams als schädlich identifiziert wurde, können Sie eine Warnung einrichten.

1. Wählen Sie [im Security & Compliance Center](https://protection.office.com)die Option **Warnungen** \> **verwalten aus.**

2. Wählen **Sie Neue Warnungsrichtlinie aus.**

3. Geben Sie einen Namen für die Warnung an. Sie können beispielsweise bösartige Dateien in Bibliotheken eingeben.

4. Geben Sie eine Beschreibung für die Warnung ein. Sie können beispielsweise Administrator benachrichtigen eingeben, wenn schädliche Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.

5. Legen Sie im Abschnitt Diese **Warnung senden, wenn...** festgelegt:

   a. Wählen Sie **in der Liste** Aktivitäten die Option **Schadsoftware in Datei erkannt aus.**

   b. Lassen Sie das **Feld Benutzer** leer.

6. Wählen Sie im Abschnitt Diese **Warnung an...** senden einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheitsleser aus, die Benachrichtigungen erhalten sollen, wenn eine schädliche Datei erkannt wird.

7. **Speichern** Sie .

Weitere Informationen zu Warnungen finden Sie unter [Create activity alerts in the Security & Compliance Center](../../compliance/create-activity-alerts.md).

> [!NOTE]
> Verwenden Sie nach Abschluss der Konfiguration die folgenden Links, um Arbeitsauslastungsuntersuchungen zu starten:
>
>- [Threat Protection-Statusbericht](view-email-security-reports.md#threat-protection-status-report)
>- [Verwenden des Security & Compliance Center zum Verwalten isolierter Dateien](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [Was tun, wenn eine schädliche Datei in SharePoint Online, OneDrive oder Microsoft Teams gefunden wird](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [Verwalten von isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Teil 6 – Zusätzliche Zu konfigurierende Einstellungen

Neben dem Konfigurieren des Schutzes vor Schadsoftware, bösartigen URLs und Dateien, Phishing und Spam wird empfohlen, die automatische Bereinigung zu null Stunden zu konfigurieren.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Automatisches Löschen von E-Mails in EOP in null Stunden

[Zap (Zero-Hour Auto Purge)](zero-hour-auto-purge.md) ist in Abonnements verfügbar, die [EOP enthalten.](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) Dieser Schutz ist standardmäßig aktiviert. Die folgenden Bedingungen müssen jedoch erfüllt sein, damit der Schutz wirksam wird:

- Spamaktionen werden in Antispamrichtlinien auf "Nachricht in [Junk-E-Mail-Ordner verschieben" festgelegt.](anti-spam-protection.md) 

- Benutzer haben ihre Standardmäßigen [Junk-E-Mail-Einstellungen beibehalten](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)und den Junk-E-Mail-Schutz nicht deaktiviert.

Weitere Informationen finden Sie unter Automatisches Löschen der Nullstunde [– Schutz vor Spam und Schadsoftware.](zero-hour-auto-purge.md)

## <a name="post-setup-tasks-and-next-steps"></a>Aufgaben nach dem Setup und die nächsten Schritte

Achten Sie nach dem Konfigurieren der Features für den Bedrohungsschutz darauf, die Funktionsweise dieser Features zu überwachen. Überprüfen und überarbeiten Sie Ihre Richtlinien so, dass sie das tun, wozu Sie sie benötigen. Achten Sie außerdem auf neue Features und Dienstupdates, die einen Mehrwert bieten können.

****

|Vorgehensweise|Ressourcen mit mehr Informationen|
|---|---|
|Sehen Sie sich an, wie Bedrohungsschutzfeatures für Ihre Organisation funktionieren, indem Sie Berichte anzeigen.|[Sicherheitsdashboard](security-dashboard.md) <p> [E-Mail-Sicherheitsberichte](view-email-security-reports.md) <p> [Berichte für Microsoft Defender für Office 365](view-reports-for-mdo.md) <p> [Sicherheitsrisiken-Explorer](threat-explorer.md)|
|Überprüfen und überarbeiten Sie ihre Richtlinien für den Bedrohungsschutz regelmäßig nach Bedarf.|[Sicherheitsbewertung](../defender/microsoft-secure-score.md) <p> [Intelligente Berichte und Einblicke](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 Threat Investigation and Response Features](./office-365-ti.md)|
|Auf neue Features und Dienstupdates achten|[Standard- und Zielversionsoptionen](../../admin/manage/release-options-in-office-365.md) <p> [Nachrichtencenter](../../admin/manage/message-center.md) <p> [Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [Dienstbeschreibungen](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Erfahren Sie mehr über empfohlene Standard- und Strikte Sicherheitskonfigurationen für EOP und Defender für Office 365|[Empfohlene Einstellungen für EOP und Microsoft Defender für Office 365-Sicherheit](recommended-settings-for-eop-and-office365.md)|
