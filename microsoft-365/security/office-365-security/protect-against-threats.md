---
title: Schutz vor Bedrohungen
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Administratoren können Informationen zum Bedrohungsschutz in Microsoft 365 und konfigurieren, wie Sie für Ihre Organisation verwendet werden.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ad74e9bdcd7b937873108d2ba049c16db8c235b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202579"
---
# <a name="protect-against-threats"></a>Schutz vor Bedrohungen

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


Hier ist eine Schnellstartanleitung, die die Konfiguration von Advanced Threat Protection in Chunks unterteilt. Wenn Sie mit den Features zum Schutz vor Bedrohungen in Office 365 vertraut sind, nicht sicher sind, wo Sie beginnen sollten, oder wenn Sie am besten *lernen, verwenden*Sie diese Anleitung als Prüfliste und als Ausgangspunkt.

> [!IMPORTANT]
> Die **anfänglichen empfohlenen Einstellungen sind für jede Art von Richtlinie enthalten; viele Optionen sind jedoch verfügbar, und Sie können Ihre Einstellungen an die Anforderungen Ihrer Organisation anpassen**. Lassen Sie etwa 30 Minuten zu, bis Ihre Richtlinien oder Änderungen sich über Ihr Rechenzentrum durchsetzen.

## <a name="requirements"></a>Anforderungen

### <a name="subscriptions"></a>Abonnements

Die Features für den Bedrohungsschutz sind in *allen* Microsoft-oder Office 365-Abonnements enthalten. Einige Abonnements weisen jedoch erweiterte Funktionen auf. In der folgenden Tabelle sind die in diesem Artikel enthaltenen Schutzfeatures zusammen mit den Mindestanforderungen für Abonnements aufgeführt.

> [!TIP]
> Beachten Sie, dass über die Anweisungen zum Aktivieren der Überwachung hinaus mit den *Schritten* Antischadsoftware, Antiphishing und Antispamfunktionen gestartet werden, die als Teil von Office 365 Exchange Online Protection (**EoP**) gekennzeichnet sind. Dies kann in einem Artikel zum Thema Advanced Threat Protection unmerklich erscheinen, bis Sie sich an Advanced Threat Protection (**ATP**) erinnern, der EoP enthält und auf diesen aufbaut.

****

|Schutztyp|Abonnementanforderung|
|---|---|
|Überwachungsprotokollierung (zu Berichtszwecken)|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|Schutz vor Schadsoftware|[Exchange Online Schutz](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EoP**)|
|Antiphishingschutz|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Antispamschutz|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Automatische Bereinigung ohne Stunden (für e-Mail)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|Schutz vor bösartigen URLs und Dateien in e-Mail-und Office-Dokumenten (sichere Links und sichere Anlagen)|[Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**)|
|Aktivieren von ATP für SharePoint-, OneDrive-und Microsoft Teams-Arbeitsauslastungen| [ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide)|
|Erweiterter Antiphishingschutz|[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>Rollen und Berechtigungen

Um ATP-Richtlinien zu konfigurieren, müssen Sie im [Security & Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)eine entsprechende Rolle zugewiesen haben. Sehen Sie sich die folgende Tabelle für Rollen an, die diese Aktionen ausführen können.

****

|Rolle oder Rollengruppe|Weitere Informationen|
|---|---|
|globaler Administrator|[Informationen zu Microsoft 365-Administratorrollen](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|Sicherheitsadministrator|[Administratorrollenberechtigungen in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online-Organisationsverwaltung|[Berechtigungen in Exchange Online](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>und<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

Weitere Informationen finden Sie unter [Permissions in the Security &amp; Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>Aktivieren Sie die Überwachungsprotokollierung für die Berichterstellung und Untersuchung, bevor Sie beginnen.

Starten Sie die Überwachungsprotokollierung frühzeitig. Für einige der folgenden Schritte müssen Sie die Überwachung **durchführen.** Die Überwachungsprotokollierung steht in Abonnements zur Verfügung, die [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)umfassen. Um Daten in Threat Protection-Berichten anzuzeigen, beispielsweise im [Sicherheits Dashboard](security-dashboard.md), in [e-Mail-Sicherheitsberichten](view-email-security-reports.md)und im [Explorer](threat-explorer.md), muss die Überwachungsprotokollierung *aktiviert*sein. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="part-1---anti-malware-protection"></a>Part 1 – Schutz vor Schadsoftware

Der [Schutz vor Schadsoftware](anti-malware-protection.md) ist in Abonnements, die [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)enthalten, verfügbar.

1. Wählen Sie im [Security & Compliance Center](https://protection.office.com)die Option " **Threat Management**  >  **Policy**  >  **Anti-Malware**" aus.

2. Doppelklicken Sie auf die **Standard** Richtlinie, und wählen Sie dann **Einstellungen**aus.

3. Geben Sie die folgenden Einstellungen an:

    - Behalten Sie im Abschnitt " **Malware Erkennungs Antwort** " die Standardeinstellung " **Nein**" bei.

    - Wählen Sie im Abschnitt **Filter für allgemeine Anlagentypen** die Option **ein**aus.

4. Klicken Sie auf **Speichern**.

Weitere Informationen zu Anti-Malware-Richtlinienoptionen finden Sie unter [configure Anti-Malware Policies](configure-anti-malware-policies.md).

## <a name="part-2---anti-phishing-protection"></a>Part 2-Schutz gegen Phishing

[Anti-Phishing]

[Anti-Phishing-Schutz](anti-phishing-protection.md) ist in Abonnements verfügbar, die [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)enthalten. Advanced Anti-Phishing Protection ist in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)verfügbar.

Im folgenden Verfahren wird beschrieben, wie Sie eine ATP-Richtlinie zum Schutz vor Phishing konfigurieren. Die Schritte ähneln dem Konfigurieren einer Anti-Phishing-Richtlinie (ohne ATP).

1. Wählen Sie im [Security & Compliance Center](https://protection.office.com)die Option " **Threat Management**  >  **Policy**  >  **ATP Anti-Phishing**" aus.

2. Klicken Sie auf **Standardrichtlinie**.

3. Klicken Sie im Abschnitt **Identitätswechsel** auf **Bearbeiten**, und geben Sie dann die folgenden Einstellungen an:

   - *Aktivieren Sie auf der* Registerkarte **zu schützende Benutzer hinzufügen** den Schutz. Fügen Sie dann Benutzer wie die Verwaltungsratsmitglieder Ihrer Organisation, ihren CEO, CFO und andere Führungskräfte hinzu. (Sie können eine einzelne e-Mail-Adresse eingeben oder zum Anzeigen einer Liste klicken.)

   - Aktivieren Sie auf der Registerkarte **zu schützende Domänen hinzufügen** **die Domäne automatisch einschließen, die ich besitze**. Wenn Sie benutzerdefinierte Domänen haben, fügen Sie Sie jetzt hinzu.

   - Wählen Sie auf der Registerkarte **Aktionen** die Option Nachricht für den **imitierten Benutzer** und die **Identität der imitierten Domäne** **isolieren** aus. Aktivieren Sie außerdem die Sicherheitstipps für Identitätswechsel.

   - Stellen Sie auf der Registerkarte **Post Fach Intelligenz** sicher, dass die Post Fach Intelligenz aktiviert ist, und aktivieren Sie den Post Fachnachrichten basierten Identitätswechsel Schutz. Wählen Sie in der Liste **Wenn e-Mail von einer imitierten Benutzer gesendet wird** **die Option Nachricht isolieren**aus.

   - Geben Sie auf der Registerkarte **vertrauenswürdige Absender und Domänen hinzufügen** alle vertrauenswürdigen Absender oder Domänen an, die Sie hinzufügen möchten.

   - **Speichern** Sie auf der Registerkarte **Überprüfen Ihrer Einstellungen** , nachdem Sie Ihre Einstellungen überprüft haben.

4. Klicken Sie im Abschnitt **Spoof** auf **Bearbeiten**, und geben Sie dann die folgenden Einstellungen an:

   - Stellen Sie auf der Registerkarte **Spoofing-Filtereinstellungen** sicher, dass der Schutz vor Spoofing aktiviert ist.

   - Wählen Sie auf der Registerkarte **Aktionen** **die Option Nachricht isolieren**aus.

   - **Speichern** Sie auf der Registerkarte **Überprüfen Ihrer Einstellungen** , nachdem Sie Ihre Änderungen überprüft haben. (Wenn Sie keine Änderungen vorgenommen haben, **kündigen**Sie.)

5. Schließen Sie die Seite Standardrichtlinieneinstellungen.

Weitere Informationen zu den Optionen für Anti-Phishing-Richtlinien finden Sie unter [configure ATP Anti-Phishing Policies](configure-atp-anti-phishing-policies.md).

## <a name="part-3---anti-spam-protection"></a>Part 3 – Schutz vor Spam

[Anti-Spam Protection](anti-spam-protection.md) ist in Abonnements mit [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)verfügbar.

1. Wählen Sie im [Security & Compliance Center](https://protection.office.com)die Option " **Threat Management**  >  **Policy**  >  **Anti-Spam**" aus.

2. Aktivieren Sie auf der Registerkarte **Benutzer** definiert benutzerdefinierte Einstellungen.

3. Erweitern Sie **standardmäßige Spamfilter Richtlinie**, klicken Sie auf **Richtlinie bearbeiten**, und geben Sie dann die folgenden Einstellungen an:

   - Legen Sie im Abschnitt **Spam-und Massenaktionen** den Schwellenwert auf den Wert 5 oder 6 fest.

   - Überprüfen Sie (und/oder bearbeiten Sie) ihre zulässigen Absender und Domänen im Abschnitt **Zulassungslisten** .

4. Klicken Sie auf **Speichern**.

Weitere Informationen zu den Antispam-Richtlinienoptionen finden Sie unter [configure Anti-Spam Policies in EoP](configure-your-spam-filter-policies.md).

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments"></a>Part 4 – Schutz vor bösartigen URLs und Dateien (sichere Links und sichere Anlagen)

Time-of-Click-Schutz vor bösartigen URLs und Dateien ist in Abonnements verfügbar, die [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) enthalten. Es ist durch ATP- [sichere Anlagen](atp-safe-attachments.md) und Richtlinien für [ATP-sichere Links](atp-safe-links.md) eingerichtet.

### <a name="atp-safe-attachments-policies"></a>Richtlinien für ATP-sichere Anlagen

Um ATP- [sichere Anlagen](atp-safe-attachments.md)einzurichten, müssen Sie mindestens eine Richtlinie für ATP-sichere Anlagen definieren.

1. Wählen Sie im [Security & Compliance Center](https://protection.office.com)die Option " **Threat Management**  >  **Policy**  >  **ATP Safe Attachments**" aus.

2. Aktivieren Sie die Option **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren**.

3. Klicken Sie im Abschnitt **e-Mail-Anlagen schützen** auf das Pluszeichen ( **+** ).

4. Geben Sie die folgenden Einstellungen an:

   - Geben Sie im Feld **Name den Namen** ein `Block malware` .

   - Wählen Sie im Abschnitt Antwort die Option **blockieren**aus.

   - Wählen Sie im Abschnitt **Redirect Attachment** die Option **Redirect aktivieren**aus. Geben Sie die e-Mail-Adresse des Sicherheitsadministrators oder-Betreibers Ihrer Organisation an, der die erkannten Dateien prüft.

   - Wählen Sie im Abschnitt **angewendet für** **die Option Empfängerdomäne lautet**aus. Wählen Sie dann Ihre Domäne aus, klicken Sie auf **Hinzufügen**und dann auf **OK**.

5. **Save**.

6. (**Empfohlener zusätzlicher Schritt**) Führen Sie als globaler Administrator oder SharePoint Online Administrator das Cmdlet " **[SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** " aus, wobei der Parameter " **DisallowInfectedFileDownload** " für Ihre Microsoft 365-Umgebung auf  *true* festgelegt ist. (Dadurch wird verhindert, dass Benutzer Dateien öffnen, verschieben, kopieren oder freigeben, die als bösartig erkannt werden.)

Weitere Informationen finden Sie unter [Einrichten Office 365 ATP-Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md) und [Aktivieren von Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>Richtlinien für ATP-sichere Links

Um ATP- [sichere Links](atp-safe-links.md)einzurichten, überprüfen und bearbeiten Sie die Standardrichtlinie, und fügen Sie eine Richtlinie für bestimmte Benutzer hinzu.

1. Wählen Sie im [Security & Compliance Center](https://protection.office.com)die Option " **Threat Management**  >  **Policy**  >  **ATP Safe Links**" aus.

2. Doppelklicken Sie auf die **Standard** Richtlinie.

3. Wählen Sie im Abschnitt **sichere Links in verwenden** die Option **Microsoft 365 Apps für Unternehmen, Office für IOS und Android**aus, und klicken Sie dann auf **Speichern**.

4. Klicken Sie im Abschnitt **Richtlinien für bestimmte Empfänger** auf das Pluszeichen ( **+** ).

5. Geben Sie die folgenden Einstellungen an:

   - Geben Sie im Feld **Name** einen Namen ein, beispielsweise `Safe Links` .

   - Wählen Sie im Abschnitt **Aktion auswählen die** Option **ein**aus.

   - Wählen Sie diese Optionen aus:

     - **Verwenden sicherer Anlagen zum Überprüfen herunterladbarer Inhalte**

     - **Anwenden von sicheren Links auf e-Mail-Nachrichten, die innerhalb der Organisation gesendet werden**

     - **Nicht zulassen, dass Benutzer über sichere Links auf die ursprüngliche URL klicken**

   - Wählen Sie im Abschnitt **angewendet für** **die Option Empfängerdomäne lautet**aus. Wählen Sie dann Ihre Domäne aus, klicken Sie auf **Hinzufügen**und dann auf **OK**.

6. **Save**.

Weitere Informationen hierzu finden Sie unter [Einrichten einer Richtlinie für Office 365 ATP-sichere Links](set-up-atp-safe-links-policies.md).

## <a name="part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads"></a>Abschnitt 5: Aktivieren von ATP für SharePoint-, OneDrive-und Microsoft Teams-Arbeitsauslastungen

Arbeitslasten wie SharePoint, OneDrive und Teams werden für die Zusammenarbeit entwickelt. Die Verwendung von ATP hilft beim blockieren und erkennen von Dateien, die als bösartige Daten in Teamwebsites und Dokumentbibliotheken identifiziert werden. Mehr darüber, wie das funktioniert, erfahren Sie [hier](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide).

> [!IMPORTANT]
> **Bevor Sie mit diesem Verfahren beginnen, müssen Sie sicherstellen, dass die Überwachungsprotokollierung für Ihre Microsoft 365-Umgebung bereits aktiviert ist**. Dies erfolgt in der Regel durch eine Person, der die Rolle "Überwachungsprotokolle" in Exchange Online zugewiesen ist. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren der Überwachungsprotokoll Suche](../../compliance/turn-audit-log-search-on-or-off.md)!

1. Wechseln Sie zu <https://protection.office.com> , und melden Sie sich mit ihrem geschäftlichen oder Schulkonto an.

2. Wählen Sie im Sicherheits & Compliance Center im linken Navigationsbereich unter **Bedrohungs Verwaltung**die Option **Richtlinien** für \> **sichere Anlagen**aus.

   ![Wählen Sie im Security & Compliance Center die Option Threat Management Policy aus. \>](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. Wählen Sie **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren**aus.

   ![Aktivieren von Advanced Threat Protection für SharePoint Online, OneDrive für Unternehmen und Microsoft Teams](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. **Save**.

5. Überprüfen Sie (und bearbeiten Sie gegebenenfalls die Richtlinien für [sichere Anlagen](set-up-atp-safe-attachments-policies.md) Ihrer Organisation und [Richtlinien für sichere Links](set-up-atp-safe-links-policies.md)).

6. Empfohlen Führen Sie als globaler Administrator oder SharePoint Online Administrator das Cmdlet " **[SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** " aus, wobei der Parameter _DisallowInfectedFileDownload_ auf festgelegt ist `$true` .

   - `$true` alle Aktionen (außer DELETE) für erkannte Dateien werden blockiert. Personen können erkannte Dateien nicht öffnen, kopieren oder freigeben.
   - `$false` blockiert alle Aktionen außer DELETE und Download. Personen können wählen, das Risiko zu akzeptieren und eine erkannte Datei herunterzuladen.

   > [!TIP]
   > Weitere Informationen zur Verwendung von PowerShell mit Microsoft 365 finden Sie unter [Verwalten von Microsoft 365 mit PowerShell](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell).

7. Lassen Sie bis zu 30 Minuten zu, bis Ihre Änderungen auf alle Microsoft 365-Rechenzentren verteilt wurden.

### <a name="now-set-up-alerts-for-detected-files"></a>Jetzt Benachrichtigungen für erkannte Dateien einrichten

Um eine Benachrichtigung zu erhalten, wenn eine Datei in SharePoint Online, OneDrive für Unternehmen oder Microsoft Teams als bösartig identifiziert wurde, können Sie eine Warnung einrichten.

1. Wählen Sie im [Security & Compliance Center](https://protection.office.com) **Alerts** \> **Manage Alerts**aus.

2. Wählen Sie **neue Warnungs Richtlinie**aus.

3. Geben Sie einen Namen für die Warnung an. Sie können beispielsweise böswillige Dateien in Bibliotheken eingeben.

4. Geben Sie eine Beschreibung für die Warnung ein. Sie können beispielsweise benachrichtigte Administratoren eingeben, wenn schädliche Dateien in SharePoint Online, OneDrive oder Microsoft Teams erkannt werden.

5. Legen Sie im Abschnitt **Diese Warnung senden, wenn...** fest:

   a. Wählen Sie in der Liste **Aktivitäten** die Option **erkannte Schadsoftware in Datei aus**.

   b. Lassen Sie das Feld **Benutzer** leer.

6. Wählen Sie im Abschnitt **diese Benachrichtigung an... senden** einen oder mehrere globale Administratoren, Sicherheitsadministratoren oder Sicherheits Leser aus, die eine Benachrichtigung erhalten sollen, wenn eine Schadsoftware erkannt wird.

7. **Save**.

Weitere Informationen zu Warnungen finden Sie unter [Erstellen von Aktivitäts Warnungen im Security & Compliance Center](../../compliance/create-activity-alerts.md).

> [!NOTE]
> Wenn Sie die Konfiguration abgeschlossen haben, verwenden Sie die folgenden Links, um Arbeits Auslastungs Untersuchungen zu starten:
>
> - [Anzeigen von Informationen zu bösartigen Dateien, die in SharePoint, OneDrive oder Microsoft Teams erkannt wurden](malicious-files-detected-in-spo-odb-or-teams.md)
> - [Vorgehensweise beim finden einer schädlichen Datei in SharePoint Online, OneDrive oder Microsoft Teams](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
> - [Verwalten von isolierten Nachrichten und Dateien als Administrator in Microsoft 365](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>Part 6-zusätzliche Einstellungen für die Konfiguration

Neben der Konfiguration des Schutzes vor Schadsoftware, bösartigen URLs und Dateien, Phishing und Spam wird empfohlen, die automatische Bereinigung ohne Stunden zu konfigurieren.

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>Automatische Bereinigung ohne Stunden für e-Mail in EoP

In Abonnements mit [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)ist die [Automatische Bereinigung von Null Stunden](zero-hour-auto-purge.md) (zap) verfügbar. Dieser Schutz ist standardmäßig aktiviert. die folgenden Bedingungen müssen jedoch erfüllt sein, damit der Schutz wirksam ist:

- Spam Aktionen sind so konfiguriert, dass die **Nachricht in den Junk-e-Mail-Ordner** in [Anti-Spam-Richtlinien](anti-spam-protection.md)verschiebt wird.

- Benutzer haben Ihre Standard [Einstellungen für Junk-e-Mails](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)beibehalten und den Junk-e-Mail-Schutz nicht deaktiviert.

Weitere Informationen finden Sie unter [Zero-Hour Auto Purge – Schutz vor Spam und Schadsoftware](zero-hour-auto-purge.md).

## <a name="post-setup-tasks-and-next-steps"></a>Aufgaben nach dem Setup und nächste Schritte

Stellen Sie nach dem Konfigurieren der Features für den Schutz vor Bedrohungen sicher, dass die Funktionsweise dieser Features überwacht wird. Überprüfen und überarbeiten Sie Ihre Richtlinien so, dass Sie das tun, was Sie benötigen. Achten Sie außerdem auf neue Features und dienstupdates, die einen Mehrwert bieten können.

****

|Vorgehensweise|Ressourcen mit mehr Informationen|
|---|---|
|Erfahren Sie, wie die Features für den Schutz von Bedrohungen für Ihre Organisation durch Anzeigen von Berichten funktionieren.|[Sicherheits Dashboard](security-dashboard.md)<br/>[E-Mail-Sicherheitsberichte](view-email-security-reports.md)<br/>[Reportagen für Office 365 ATP](view-reports-for-atp.md)<br/>[Sicherheitsrisiken-Explorer](threat-explorer.md)|
|Regelmäßige Überprüfung und Überarbeitung ihrer Threat Protection-Richtlinien nach Bedarf|[Sicherheitsbewertung](../mtp/microsoft-secure-score.md)<br/>[Intelligente Berichte und Einblicke](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 Threat Investigation and Response Features](keep-users-safe-with-office-365-ti.md)|
|Überwachen neuer Features und dienstupdates|[Standard mäßige und gezielte Veröffentlichungsoptionen](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[Nachrichtencenter](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Dienstbeschreibungen](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|Erfahren Sie mehr über die empfohlenen Standard mäßigen und strengen Sicherheitskonfigurationen für EoP und ATP. | [Empfohlene Einstellungen für EoP und Office 365 ATP-Sicherheit](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) |
