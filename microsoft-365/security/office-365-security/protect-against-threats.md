---
title: Schutz vor Bedrohungen in Office 365
ms.author: tracyp
author: msfttracyp
manager: dansimp
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
ms.date: 05/09/2019
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: Verwenden Sie diesen Artikel als Leitfaden zum Konfigurieren der Features für den Bedrohungsschutz jetzt.
ms.openlocfilehash: 7d18c8901b1edcc9e5238ed092bdb27bec684b1b
ms.sourcegitcommit: 1162d676b036449ea4220de8a6642165190e3398
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/20/2019
ms.locfileid: "37082401"
---
# <a name="protect-against-threats-in-office-365"></a>Schutz vor Bedrohungen in Office 365

Office 365 enthält eine Vielzahl von Features zum Schutz vor Bedrohungen. Hier ist eine Schnellstartanleitung, die Sie als Prüfliste verwenden können, um sicherzustellen, dass Ihre Threat Protection-Funktionen für Ihre Organisation eingerichtet sind. Wenn Sie neue Features für den Schutz vor Bedrohungen in Office 365 haben oder einfach nicht wissen, wo Sie beginnen sollten, verwenden Sie die folgende Anleitung als Ausgangspunkt. 

> [!IMPORTANT]
> Die **anfänglichen empfohlenen Einstellungen sind für jede Art von Richtlinie enthalten; viele Optionen sind jedoch verfügbar, und Sie können Ihre Einstellungen an die Anforderungen Ihrer Organisation anpassen**. Lassen Sie etwa 30 Minuten zu, bis Ihre Richtlinien oder Änderungen sich über Ihr Rechenzentrum durchsetzen.

## <a name="requirements"></a>Voraussetzungen

### <a name="subscriptions"></a>Abonnements

Die Features für den Bedrohungsschutz sind in allen Office 365 Abonnements enthalten; Einige Abonnements enthalten jedoch erweiterte Funktionen. In der folgenden Tabelle sind die in diesem Artikel enthaltenen Schutzfeatures zusammen mit den Mindestanforderungen für Abonnements aufgeführt.<br/>

|Protection-Typ  |Abonnementanforderung  |
|---------|---------|
|Schutz vor Schadsoftware    | [Exchange Online Schutz](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description) EoP        |
|Schutz vor bösartigen URLs und Dateien in e-Mail-und Office-Dokumenten    | [Office 365 Advanced Threat Protection](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) ATP       |
|Antiphishingschutz    | [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)      |
|Erweiterter Schutz gegen Phishing    | [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)   |
|Antispamschutz     | [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)       |
|Automatische Bereinigung ohne Stunden (für e-Mail)    | [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)        |
|Überwachungsprotokollierung (wird für Berichtszwecke verwendet)    | [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)        |

### <a name="roles-and-permissions"></a>Rollen und Berechtigungen

Sie müssen eine geeignete Rolle zum Konfigurieren von Richtlinien im [Security #a0 Compliance Center](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)zugewiesen sein. Die folgende Tabelle enthält einige Beispiele: 

|Rolle oder Rollengruppe  |Weitere Informationen  |
|---------|---------|
|Office 365 globaler Administrator |[Informationen zu Administratorrollen von Office 365](https://docs.microsoft.com/office365/admin/add-users/about-admin-roles)|
|Sicherheitsadministrator |[Berechtigungen für Administrator Rollen in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online Organisationsverwaltung |[Berechtigungen in Exchange Online](https://docs.microsoft.com/en-us/exchange/permissions-exo/permissions-exo) <br>und<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/exchange-online-powershell?view=exchange-ps)|

Weitere Informationen finden Sie unter [Permissions in the Office 365 &amp; Security Compliance Center](permissions-in-the-security-and-compliance-center.md).

## <a name="part-1---anti-malware-protection"></a>Part 1 – Schutz vor Schadsoftware

Der [Schutz vor Schadsoftware](anti-malware-protection.md) ist in Abonnements, die [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)enthalten, verfügbar. 

1. Wählen Sie im [Security #a0 Compliance Center](https://protection.office.com)die Option " **Threat Management** > **Policy** > **Anti-Malware**" aus.

2. Doppelklicken Sie auf die **Standard** Richtlinie, und wählen Sie dann **Einstellungen**aus.

3. Geben Sie die folgenden Einstellungen an:

    - Behalten Sie im Abschnitt " **Malware Erkennungs Antwort** " die Standardeinstellung " **Nein**" bei.

    - Wählen Sie im Abschnitt **Filter für allgemeine Anlagentypen** die Option **ein**aus.

4. Klicken Sie auf **Speichern**.

Weitere Informationen zu Anti-Malware-Richtlinienoptionen finden Sie unter [configure Anti-Malware Policies](configure-anti-malware-policies.md).

## <a name="part-2---protection-from-malicious-urls-and-files"></a>Part 2 – Schutz vor bösartigen URLs und Dateien

Time-of-Click-Schutz vor bösartigen URLs und Dateien ist in Abonnements verfügbar, die [Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) enthalten, und wird über [ATP-sichere Anlagen](atp-safe-attachments.md) und Richtlinien für [ATP-sichere Links](atp-safe-links.md) eingerichtet.

### <a name="atp-safe-attachments-policies"></a>Richtlinien für ATP-sichere Anlagen

Um ATP- [sichere Anlagen](atp-safe-attachments.md)einzurichten, müssen Sie mindestens eine Richtlinie für ATP-sichere Anlagen definieren. 

1. Wählen Sie im [Security #a0 Compliance Center](https://protection.office.com)die Option " **Threat Management** > **Policy** > **ATP Safe Attachments**" aus.

2. Aktivieren Sie die Option **ATP für SharePoint, OneDrive und Microsoft Teams aktivieren**.

3. Klicken Sie im Abschnitt **e-Mail-Anlagen schützen** auf das**+** Pluszeichen ().

4. Geben Sie die folgenden Einstellungen an:

    - Geben `Block malware`Sie im Feld **Name den Namen** ein.

    - Wählen Sie im Abschnitt Antwort die Option **blockieren**aus.

    - Wählen Sie im Abschnitt **Umleitungs Anlage** die Option **Umleitung aktivieren**aus, und geben Sie dann die e-Mail-Adresse für den Sicherheitsadministrator oder-Operator Ihres Unternehmens an, der erkannte Dateien prüft.

    - Wählen Sie im Abschnitt **angewendet für** **die Option Empfängerdomäne lautet**aus. Wählen Sie dann Ihre Domäne aus, wählen Sie **Hinzufügen**aus, und klicken Sie dann auf **OK**.

5. Klicken Sie auf **Speichern**.

6. (**Empfohlener zusätzlicher Schritt**) Führen Sie als globaler Administrator oder SharePoint Online Administrator das Cmdlet " **[SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant?view=sharepoint-ps)** " mit dem Parameter " **DisallowInfectedFileDownload** " für Ihre Office 365 Umgebung auf " *true* " fest. (Dadurch wird verhindert, dass Benutzer Dateien öffnen, verschieben, kopieren oder freigeben, die als bösartig erkannt werden.)  

Weitere Informationen finden Sie unter [Einrichten Office 365 ATP-Richtlinien für sichere Anlagen](set-up-atp-safe-attachments-policies.md) und [Aktivieren von Office 365 ATP für SharePoint, OneDrive und Microsoft Teams](turn-on-atp-for-spo-odb-and-teams.md).

### <a name="atp-safe-links-policies"></a>Richtlinien für ATP-sichere Links

Um ATP- [sichere Links](atp-safe-links.md)einzurichten, überprüfen und bearbeiten Sie die Standardrichtlinie, und fügen Sie eine Richtlinie für bestimmte Benutzer hinzu.

1. Wählen Sie im [Security #a0 Compliance Center](https://protection.office.com)die Option " **Threat Management** > **Policy** > **ATP Safe Links**" aus.

2. Doppelklicken Sie auf die **Standard** Richtlinie.

3. Wählen Sie im Abschnitt **sichere Links in verwenden** die Option **Office 365 ProPlus, Office für IOS und Android**aus, und klicken Sie dann auf **Speichern**.

4. Klicken Sie im Abschnitt **Richtlinien für bestimmte Empfänger** auf das Pluszeichen (**+**).

5. Geben Sie die folgenden Einstellungen an:

    - Geben Sie im Feld **Name** einen Namen ein, beispielsweise `Safe Links`.

    - Wählen Sie im Abschnitt **Aktion auswählen die** Option **ein**aus.

    - Wählen Sie diese Optionen aus:

        - **Verwenden sicherer Anlagen zum Überprüfen herunterladbarer Inhalte** 

        - **Anwenden von sicheren Links auf e-Mail-Nachrichten, die innerhalb der Organisation gesendet werden**

        - **Nicht zulassen, dass Benutzer über sichere Links auf die ursprüngliche URL klicken**

    - Wählen Sie im Abschnitt **angewendet für** **die Option Empfängerdomäne lautet**aus. Wählen Sie dann Ihre Domäne aus, wählen Sie **Hinzufügen**aus, und klicken Sie dann auf **OK**.

6. Klicken Sie auf **Speichern**.

Weitere Informationen finden Sie unter [Einrichten Office 365 Richtlinien für ATP-sichere Links](set-up-atp-safe-links-policies.md). 

## <a name="part-3---anti-phishing-protection"></a>Part 3 – Schutz gegen Phishing

[Anti-Phishing-Schutz](anti-phishing-protection.md) ist in Abonnements verfügbar, die [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)enthalten. Advanced Anti-Phishing Protection ist in [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)verfügbar. Im folgenden Verfahren wird beschrieben, wie Sie eine ATP-Richtlinie zum Schutz vor Phishing konfigurieren. Die Schritte ähneln dem Konfigurieren einer Anti-Phishing-Richtlinie (ohne ATP).

1. Wählen Sie im [Security #a0 Compliance Center](https://protection.office.com)die Option " **Threat Management** > **Policy** > **ATP Anti-Phishing**" aus.

2. Klicken Sie auf **Standardrichtlinie**.

3. Klicken Sie im Abschnitt **Identitätswechsel** auf **Bearbeiten**, und geben Sie dann die folgenden Einstellungen an:

    - Aktivieren Sie auf der Registerkarte **zu schützende Benutzer hinzufügen** den Schutz aktiviert. Fügen Sie dann Benutzer wie die Verwaltungsratsmitglieder Ihrer Organisation, ihren CEO, CFO und andere Führungskräfte hinzu. (Sie können eine einzelne e-Mail-Adresse eingeben oder zum Anzeigen einer Liste klicken.)

    - Aktivieren Sie auf der Registerkarte **zu schützende Domänen hinzufügen** **die Domäne automatisch einschließen, die ich besitze**. Wenn Sie benutzerdefinierte Domänen haben, fügen Sie diese ebenfalls hinzu.

    - Wählen Sie auf der Registerkarte **Aktionen** die Option **Nachricht in die Junk-e-Mail-Ordner der Empfänger für den** imitierten Benutzer und die Identitäts Identität der Domäne senden aus, und aktivieren Sie Sicherheitstipps.

    - Stellen Sie sicher, dass auf der Registerkarte **Post Fach Intelligenz** die Option Post Fach Intelligenz aktiviert ist.

    - Klicken Sie auf der Registerkarte **Überprüfen der Einstellungen** auf **Speichern**, nachdem Sie die Einstellungen überprüft haben.

4. Klicken Sie im Abschnitt **Spoof** auf **Bearbeiten**, und geben Sie dann die folgenden Einstellungen an:

    - Stellen Sie auf der Registerkarte **Spoofing-Filtereinstellungen** sicher, dass der Schutz vor Spoofing aktiviert ist.

    - Wählen Sie auf der Registerkarte **Aktionen** die Option Nachricht in die Junk-e-Mail-Ordner der Empfänger Migrieren aus.

    - Klicken Sie auf der Registerkarte **Überprüfen der Einstellungen** auf **Speichern**, nachdem Sie die Einstellungen überprüft haben. (Wenn Sie keine Änderungen vorgenommen haben, klicken Sie auf **Abbrechen**.)

5. Schließen Sie die Seite Standardrichtlinieneinstellungen.

Weitere Informationen zu den Optionen für Anti-Phishing-Richtlinien finden Sie unter [Einrichten von Anti-Phishing-Richtlinien](set-up-anti-phishing-policies.md).

## <a name="part-4---anti-spam-protection"></a>Part 4 – Schutz vor Spam

[Anti-Spam Protection](anti-spam-protection.md) ist in Abonnements mit [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)verfügbar.

1. Wählen Sie im [Security #a0 Compliance Center](https://protection.office.com)die Option " **Threat Management** > **Policy** > **Anti-Spam**" aus.

2. Aktivieren Sie auf der Registerkarte **Benutzerdefiniert** **benutzerdefinierte Einstellungen** .

3. Erweitern Sie **standardmäßige Spamfilter Richtlinie**, klicken Sie auf **Richtlinie bearbeiten**, und geben Sie dann die folgenden Einstellungen an:

    - Legen Sie im Abschnitt **Spam-und Massenaktionen** den Schwellenwert auf den Wert 5 oder 6 fest.

    - Im Abschnitt **Zulassungslisten können** Sie die zulässigen Absender und Domänen überprüfen (und gegebenenfalls Bearbeiten).

4. Klicken Sie auf **Speichern**.

Weitere Informationen zu den Antispam-Richtlinienoptionen finden Sie unter [configure the Anti-Spam Policies](configure-the-anti-spam-policies.md).

## <a name="part-5---additional-settings-to-configure"></a>Part 5-zusätzliche Einstellungen für configure

Zusätzlich zum Konfigurieren von Schutz vor Schadsoftware, böswilligen URLs und Dateien, Phishing und Spam empfehlen wir Ihnen, die Einstellungen für die automatische Bereinigung und die Überwachungsprotokollierung für Null Stunden zu konfigurieren.

### <a name="zero-hour-auto-purge-for-email"></a>Automatische Bereinigung ohne Stunden für e-Mail

[Automatische Bereinigung ohne Stunden](zero-hour-auto-purge.md) (Zap) ist in Abonnements verfügbar, die [EoP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description)enthalten. Dieser Schutz ist standardmäßig aktiviert. die folgenden Bedingungen müssen jedoch erfüllt sein, damit der Schutz wirksam ist:

- Spam Aktionen sind so konfiguriert, dass die **Nachricht in den Junk-e-Mail-Ordner** in [Anti-Spam-Richtlinien](anti-spam-protection.md)verschiebt wird.

- Benutzer haben Ihre Standard [Einstellungen für Junk-e-Mails](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)beibehalten und den Junk-e-Mail-Schutz nicht deaktiviert.

Weitere Informationen finden Sie unter [Zero-Hour Auto Purge – Schutz vor Spam und Schadsoftware](zero-hour-auto-purge.md).

### <a name="audit-logging-for-reporting-and-investigation"></a>Überwachungsprotokollierung für die Berichterstellung und Untersuchung

Die Überwachungsprotokollierung steht in Abonnements zur Verfügung, die [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description)umfassen. Um Daten in Threat Protection-Berichten wie dem [Sicherheits Dashboard](security-dashboard.md), [e-Mail-Sicherheitsberichten](../../compliance/view-email-security-reports.md)und dem [Explorer](threat-explorer.md)anzuzeigen, muss die Überwachungsprotokollierung für Ihre Organisation aktiviert sein. Weitere Informationen finden Sie unter [Aktivieren oder Deaktivieren von Office 365 Überwachungsprotokoll Suche](../../compliance/turn-audit-log-search-on-or-off.md).

## <a name="post-setup-tasks"></a>Aufgaben nach dem Setup

Nachdem Sie die Features für den Schutz vor Bedrohungen konfiguriert haben, müssen Sie die Funktionsweise dieser Features überwachen, Ihre Richtlinien nach Bedarf überprüfen und überarbeiten sowie auf neue Features und dienstupdates achten.

|Nächste Schritte  |Ressourcen für weitere Informationen  |
|---------|---------|
|Erfahren Sie, wie die Features für den Schutz von Bedrohungen für Ihre Organisation durch Anzeigen von Berichten funktionieren.    |[Sicherheits Dashboard](security-dashboard.md)<br/>[E-Mail-Sicherheitsberichte](../../compliance/view-email-security-reports.md)<br/>[Reportagen für Office 365 ATP](view-reports-for-atp.md)<br/>[Sicherheitsrisiken-Explorer](threat-explorer.md)    |
|Regelmäßige Überprüfung und Überarbeitung ihrer Threat Protection-Richtlinien nach Bedarf    |[Sicherheitsbewertung](../mtp/microsoft-secure-score.md)<br/>[Intelligente Berichte und Einblicke](reports-and-insights-in-security-and-compliance.md)<br/>[Untersuchung und Antwortfunktionen für Office 365 Bedrohungen](keep-users-safe-with-office-365-ti.md)          |
|Überwachen neuer Features und dienstupdates     |[Standard mäßige und gezielte Veröffentlichungsoptionen](https://docs.microsoft.com/office365/admin/manage/release-options-in-office-365?view=o365-worldwide)<br/>[Nachrichtencenter](https://docs.microsoft.com/office365/admin/manage/message-center?view=o365-worldwide)<br/>[Microsoft 365-Roadmap](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[Dienstbeschreibungen](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)         |
