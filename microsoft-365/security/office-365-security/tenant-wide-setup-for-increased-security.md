---
title: 'Konfigurieren Ihres Microsoft 365-Mandanten für höhere Sicherheit '
f1.keywords:
- NOCSH
ms.author: bcarter
author: BrendaCarter
manager: laurawi
ms.date: 10/11/2018
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_IP
- M365-security-compliance
search.appverid: MET150
ms.assetid: 8d274fe3-db51-4107-ba64-865e7155b355
ms.custom:
- seo-marvel-apr2020
description: In diesem Thema werden Sie durch die empfohlene Konfiguration für mandantenweite Einstellungen, die sich auf die Sicherheit Ihrer Microsoft 365 auswirken, beschrieben.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 686768d05e37a4e103640c2973fd30abaa25630b
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538939"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Konfigurieren Ihres Microsoft 365-Mandanten für höhere Sicherheit 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

In diesem Thema werden Sie durch die empfohlene Konfiguration für mandantenweite Einstellungen, die sich auf die Sicherheit Ihrer Microsoft 365 auswirken, beschrieben. Ihre Sicherheitsanforderungen erfordern möglicherweise mehr oder weniger Sicherheit. Verwenden Sie diese Empfehlungen als Ausgangspunkt.

## <a name="check-office-365-secure-score"></a>Überprüfen Office 365 Secure Score

Office 365 Secure Score analysiert die Sicherheit Ihrer Organisation basierend auf Ihren regulären Aktivitäten und Sicherheitseinstellungen und weist eine Bewertung zu. Notieren Sie sich zunächst Ihre aktuelle Bewertung. Wenn Sie einige mandantenweite Einstellungen anpassen, wird Ihre Bewertung erhöht. Ziel ist es nicht, die maximale Punktzahl zu erreichen, sondern sich der Möglichkeiten zum Schutz Ihrer Umgebung bewusst zu sein, die sich nicht negativ auf die Produktivität ihrer Benutzer auswirken. Weitere [Informationen finden Sie unter Microsoft Secure Score](../defender/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Optimieren von Bedrohungsverwaltungsrichtlinien im Microsoft 365 Security Center

Das Microsoft 365 Security Center umfasst Funktionen zum Schutz Ihrer Umgebung. Es enthält auch Berichte und Dashboards, die Sie zum Überwachen und Ergreifen von Maßnahmen verwenden können. Einige Bereiche verfügen über Standardrichtlinienkonfigurationen. Einige Bereiche enthalten keine Standardrichtlinien oder -regeln. Besuchen Sie diese Richtlinien unter Bedrohungsverwaltung, um die Einstellungen für die Bedrohungsverwaltung für eine sicherere Umgebung zu optimieren.

****

|Bereich|Enthält eine Standardrichtlinie|Empfehlung|
|---|---|---|
|**Antiphishing**|Ja|<ul><li>Identitätswechselschutz – Wenn Sie Über Defender für Office 365 und eine benutzerdefinierte Domäne verfügen, konfigurieren Sie die Einstellungen für den Identitätswechselschutz in der Standardmäßigen Antiphishingrichtlinie, um die E-Mail-Konten Ihrer wertvollsten Benutzer, z. B. Ihres CEO, zu schützen und Ihre Domäne zu schützen. Weitere Informationen: [Identitätswechseleinstellungen in Antiphishingrichtlinien](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365) und [Einblick in den Identitätswechsel](impersonation-insight.md)</li><li>Spoof intelligence – Überprüfen Sie Absender, die Ihre Domäne spoofieren. Blockieren oder Zulassen dieser Absender. Weitere Informationen: [Einblick in spoof intelligence in EOP](learn-about-spoof-intelligence.md) und [Manage the Tenant Allow/Block List](tenant-allow-block-list.md).</li></ul>|
|**An-Malware-Modul**|Ja| Bearbeiten Sie die Standardrichtlinie: <ul><li>Filter für allgemeine Anlagentypen: Aktivieren</li></ul> <p> Sie können auch benutzerdefinierte Schadsoftwarefilterrichtlinien erstellen und diese auf bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation anwenden. <p> Weitere Informationen: <ul><li>[Schutz vor Schadsoftware](anti-malware-protection.md)</li><li>[Konfigurieren von Antischadsoftwarerichtlinien](configure-anti-malware-policies.md)</li></ul>|
|**Sichere Anlagen in Microsoft Defender für Office 365**|Nein|Klicken Sie auf der Hauptseite für sichere Anlagen auf **Globale Einstellungen,** und aktivieren Sie diese Einstellung: <ul><li>**Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams aktivieren**</li></ul> <p> Erstellen Sie eine Richtlinie für sichere Anlagen mit den folgenden Einstellungen: <ul><li> **Block**: Wählen Sie **Blockieren** als unbekannte Schadsoftwareantwort aus.</li><li>**Umleitung aktivieren:** Aktivieren Sie dieses Kontrollkästchen, und geben Sie eine E-Mail-Adresse ein, z. B. ein Administrator- oder Quarantänekonto.</li><li>**Wenden Sie die obige Auswahl an,** wenn die Schadsoftwareprüfung auf Anlagen ein Zeit- oder Fehlerfehler auftritt: Aktivieren Sie dieses Kontrollkästchen.</li><li>**_Angewendet auf_*: **Die Empfängerdomäne wird Ihre** Domäne \> auswählen.</li></ul> <p> Weitere Informationen: [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md) und Einrichten von Richtlinien für sichere [Anlagen](set-up-safe-attachments-policies.md)|
|**Sichere Links in Microsoft Defender für Office 365**|Ja|Klicken Sie auf der Hauptseite für sichere Links auf **Globale Einstellungen**: <ul><li>**Verwenden Sicherer Links in: Office 365:** Überprüfen Sie, ob diese Einstellung aktiviert ist.</li><li>**Nicht nachverfolgen, wenn Benutzer auf Sichere Links klicken:** Deaktivieren Sie diese Einstellung, um Benutzerklicks nachverfolgt zu werden.</li></ul> <p> Erstellen Sie eine Richtlinie für sichere Links mit den folgenden Einstellungen: <ul><li>**Wählen Sie die Aktion für unbekannte potenziell** schädliche URLs in Nachrichten aus: Überprüfen Sie, ob diese Einstellung auf ein **ist.**</li><li>**Wählen Sie die Aktion für unbekannte oder** potenziell schädliche URLs innerhalb Microsoft Teams : Überprüfen Sie, ob diese Einstellung auf Ein **ist.**</li><li>**Wenden Sie die Echtzeit-URL-Überprüfung auf verdächtige Links** und Links an, die auf Dateien verweisen: Aktivieren Sie dieses Kontrollkästchen.</li><li>**Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor Sie die Nachricht senden:** Aktivieren Sie dieses Kontrollkästchen.</li><li>**Wenden Sie sichere Links auf E-Mail-Nachrichten an, die innerhalb der Organisation gesendet werden:** Aktivieren Sie dieses Kontrollkästchen.</li><li>**Benutzer dürfen nicht zur ursprünglichen URL klicken:** Aktivieren Sie dieses Kontrollkästchen.</li><li>**Angewendet auf**: **Die Empfängerdomäne wird Ihre** Domäne \> auswählen.</li></ul> <p> Weitere Informationen: [Einrichten von Richtlinien für sichere Links](set-up-safe-links-policies.md).|
|**Antispam (E-Mail-Filterung)**|Ja| Worauf Sie achten müssen: Zu viel Spam – Wählen Sie die benutzerdefinierten Einstellungen aus, und bearbeiten Sie die Standardfilterrichtlinie für Spam. Weitere Informationen: [Microsoft 365 E-Mail-Antispamschutz](anti-spam-protection.md).|
|***E-Mail-Authentifizierung***|Ja|Die E-Mail-Authentifizierung verwendet ein Domain Name System (DNS), um E-Mail-Nachrichten über den Absender einer E-Mail überprüfbare Informationen hinzuzufügen. Microsoft 365 E-Mail-Authentifizierung für die Standarddomäne (onmicrosoft.com), aber Microsoft 365 Administratoren können auch die E-Mail-Authentifizierung für benutzerdefinierte Domänen verwenden. Es werden drei Authentifizierungsmethoden verwendet: <ul><li>Sender Policy Framework (oder SPF).</li><ul><li>Informationen zum Setup finden Sie unter [Einrichten von SPF in Microsoft 365, um Spoofing zu verhindern.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</li></ul> <li>DomainKeys Identified Mail (DKIM).</li><ul><li>Weitere Informationen finden Sie unter Verwenden von [DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet wurden.](use-dkim-to-validate-outbound-email.md)</li><li>Nachdem Sie DKIM konfiguriert haben, aktivieren Sie es im Security Center.</li></ul><li>Domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität (DMARC).</li><ul><li>Für DMARC-Setup [Verwenden Sie DMARC zum Überprüfen von E-Mails in Microsoft 365](use-dmarc-to-validate-email.md).</li></ul></ul>|
|

> [!NOTE]
> Für nicht standardmäßige Bereitstellungen von SPF, Hybridbereitstellungen und Problembehandlung: Wie Microsoft 365 Sender Policy Framework (SPF) verwendet, um [Spoofing zu verhindern.](how-office-365-uses-spf-to-prevent-spoofing.md)

## <a name="view-dashboards-and-reports-in-the-security--compliance-center"></a>Anzeigen von Dashboards und Berichten im Security & Compliance Center

Besuchen Sie diese Berichte und Dashboards, um mehr über den Zustand Ihrer Umgebung zu erfahren. Die Daten in diesen Berichten werden reicher, wenn Ihre Organisation Office 365 verwendet. Machen Sie sich vorerst mit den Aktionen vertraut, die Sie überwachen und ergreifen können. Weitere Informationen finden Sie [unter Berichte im Security & Compliance Center](../../compliance/reports-in-security-and-compliance.md).

****

|Dashboard|Beschreibung|
|---|---|
|[Dashboard für die Bedrohungsverwaltung](security-dashboard.md)|Verwenden  Sie dieses Dashboard im Abschnitt Bedrohungsverwaltung des Security Centers, um Bedrohungen anzuzeigen, die bereits behandelt wurden, und als praktisches Tool, um Entscheidungsträgern in Unternehmen darüber zu berichten, welche Bedrohungsuntersuchungs- und Reaktionsfunktionen bereits zum Sichern Ihres Unternehmens durchgeführt wurden.|
|[Sicherheitsrisiken-Explorer (oder Echtzeit-Erkennung)](threat-explorer.md)|Dies befindet sich auch im Abschnitt **Bedrohungsverwaltung** des Security Centers. Wenn Sie einen Angriff auf Ihren Mandanten untersuchen oder erleben, verwenden Sie Explorer (oder Echtzeiterkennungen), um Bedrohungen zu analysieren. Explorer (und der Bericht über Echtzeiterkennungen) zeigt ihnen das Volumen der Angriffe im Laufe der Zeit, und Sie können diese Daten nach Bedrohungsfamilien, Angreiferinfrastrukturen und mehr analysieren. Sie können auch verdächtige E-Mails für die Liste Vorfälle markieren.|
|Berichte – Dashboard|Zeigen Sie **im Abschnitt** Berichte des Security Centers Überwachungsberichte für SharePoint Online und Exchange Online an. Sie können auch auf Azure Active Directory (Azure AD)-Benutzer-Anmeldeberichte, Benutzeraktivitätsberichte und das Azure AD-Überwachungsprotokoll über die Seite Berichte **anzeigen** zugreifen.|
|

![Security center Dashboard](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Konfigurieren zusätzlicher Exchange Online mandantenweite Einstellungen

Viele der Steuerelemente für Sicherheit und Schutz im Exchange Admin Center sind auch im Security Center enthalten. Sie müssen diese nicht an beiden Stellen konfigurieren. Hier sind einige zusätzliche Einstellungen, die empfohlen werden.

****

|Bereich|Enthält eine Standardrichtlinie|Empfehlung|
|---|---|---|
|**Mail Flow** (Nachrichtenflussregeln, auch als Transportregeln bekannt)|Nein|Fügen Sie eine Nachrichtenflussregel hinzu, um vor Ransomware zu schützen, indem Sie ausführbare Dateitypen blockieren Office Dateitypen, die Makros enthalten. Weitere Informationen finden Sie unter [Verwenden von Nachrichtenflussregeln zum Überprüfen von Nachrichtenanlagen in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments). <p> Weitere Themen finden Sie unter: <ul><li>[Schutz vor Ransomware](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Malware und Ransomware Protection in Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Wiederherstellen nach einem Ransomware-Angriff in Office 365](recover-from-ransomware.md)</li></ul> <p> Erstellen Sie eine Nachrichtenflussregel, um die automatische Weiterleitung von E-Mails an externe Domänen zu verhindern. Weitere Informationen finden Sie unter [Minderung externer Client forwarding Rules with Secure Score](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score). <p> Weitere Informationen: [Nachrichtenflussregeln (Transportregeln) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Aktivieren der modernen Authentifizierung**|Nein|Die moderne Authentifizierung ist eine Voraussetzung für die Verwendung der mehrstufigen Authentifizierung (MFA). MFA wird empfohlen, um den Zugriff auf Cloudressourcen, einschließlich E-Mails, zu sichern. <p> Weitere Informationen finden Sie in den folgenden Themen: <ul><li>[Deaktivieren oder Aktivieren der modernen Authentifizierung in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business Online: Aktivieren Des Mandanten für die moderne Authentifizierung](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> Die moderne Authentifizierung ist standardmäßig für Office 2016-Clients, SharePoint Online und OneDrive for Business. <p> Weitere Informationen: [Funktionsweise der modernen Authentifizierung für Office 2013 und Office 2016-Client-Apps](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Konfigurieren von mandantenweiten Freigaberichtlinien in SharePoint Admin Center

Microsoft-Empfehlungen zum Konfigurieren SharePoint Teamwebsites auf einem zunehmenden Schutzniveau, beginnend mit dem Basisschutz. Weitere Informationen finden Sie unter [Richtlinienempfehlungen zum Sichern SharePoint Und Dateien](sharepoint-file-access-policies.md).

SharePoint auf Basisebene konfigurierten Teamwebsites ermöglichen die Freigabe von Dateien für externe Benutzer mithilfe anonymer Zugriffslinks. Dieser Ansatz wird empfohlen, anstatt Dateien in E-Mails zu senden.

Um die Ziele für den basisweiten Schutz zu unterstützen, konfigurieren Sie mandantenweite Freigaberichtlinien wie hier empfohlen. Freigabeeinstellungen für einzelne Websites können restriktiver sein als diese mandantenweite Richtlinie, aber nicht weniger streng.

****

|Bereich|Enthält eine Standardrichtlinie|Empfehlung|
|---|---|---|
|**Freigabe** (SharePoint Online und OneDrive for Business)|Ja|Die externe Freigabe ist standardmäßig aktiviert. Diese Einstellungen werden empfohlen: <ul><li>Zulassen der Freigabe für authentifizierte externe Benutzer und Verwenden anonymer Zugriffslinks (Standardeinstellung).</li><li>Anonyme Zugriffslinks laufen in diesen vielen Tagen ab. Geben Sie bei Bedarf eine Zahl ein, z. B. 30 Tage.</li><li>Standardlinktyp : Wählen Sie Intern aus (nur Personen in der Organisation). Benutzer, die anonyme Links freigeben möchten, müssen diese Option im Menü Freigabe auswählen.</li></ul> <p> Weitere Informationen: [Übersicht über die externe Freigabe](/sharepoint/external-sharing-overview)|
|

SharePoint Admin Center und OneDrive for Business Admin Center enthalten die gleichen Einstellungen. Die Einstellungen in beiden Admin Centern gelten für beide.

## <a name="configure-settings-in-azure-active-directory"></a>Konfigurieren von Einstellungen in Azure Active Directory

Besuchen Sie diese beiden Bereiche in Azure Active Directory, um die mandantenweite Einrichtung für sicherere Umgebungen abzuschließen.

### <a name="configure-named-locations-under-conditional-access"></a>Konfigurieren benannter Speicherorte (unter bedingten Zugriff)

Wenn Ihre Organisation Büros mit sicherem Netzwerkzugriff umfasst, fügen Sie die vertrauenswürdigen IP-Adressbereiche Azure Active Directory benannten Speicherorten hinzu. Dieses Feature hilft, die Anzahl der gemeldeten falsch positiven Ergebnisse für Anmelderisikoereignisse zu reduzieren.

Siehe: [Benannte Speicherorte in Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Blockieren von Apps, die keine moderne Authentifizierung unterstützen

Die mehrstufige Authentifizierung erfordert Apps, die die moderne Authentifizierung unterstützen. Apps, die die moderne Authentifizierung nicht unterstützen, können nicht mithilfe von Regeln für bedingten Zugriff blockiert werden.

Deaktivieren Sie für sichere Umgebungen die Authentifizierung für Apps, die keine moderne Authentifizierung unterstützen. Sie können dies in Azure Active Directory mit einem Steuerelement tun, das in Kürze kommt.

Verwenden Sie in der Zwischenzeit eine der folgenden Methoden, um dies für SharePoint Online und OneDrive for Business:

- Verwenden von PowerShell finden Sie unter Blockieren von [Apps, die keine moderne Authentifizierung (ADAL) verwenden.](/mem/intune/protect/app-modern-authentication-block)

- Konfigurieren Sie dies im SharePoint Admin Center auf der Seite "Gerätezugriff" – "Steuern des Zugriffs von Apps, die keine moderne Authentifizierung verwenden." Wählen Sie Block aus.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Erste Schritte mit Cloud App Security oder Office 365 Cloud App Security

Verwenden Office 365 Cloud App Security, um Risiken auszuwerten, verdächtige Aktivitäten zu überwachen und automatisch Maßnahmen zu ergreifen. Erfordert Office 365 E5-Plan.

Verwenden Sie auch Microsoft Cloud App Security, um eine tiefere Sichtbarkeit zu erhalten, auch nachdem der Zugriff gewährt wurde, umfassende Steuerelemente und verbesserten Schutz für alle Ihre Cloudanwendungen, einschließlich Office 365.

Da diese Lösung den EMS E5-Plan empfiehlt, sollten Sie mit Cloud App Security beginnen, damit Sie dies mit anderen SaaS-Anwendungen in Ihrer Umgebung verwenden können. Beginnen Sie mit Standardrichtlinien und -einstellungen.

Weitere Informationen:

- [Bereitstellen von Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)

- [Weitere Informationen zu Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Was ist Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security-Dashboard](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Zusätzliche Ressourcen

Diese Artikel und Leitfäden enthalten zusätzliche Präskriptive Informationen zum Schutz Microsoft 365 Umgebung:

- [Microsoft-Sicherheitsleitfaden](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) für politische Kampagnen, gemeinnützige Organisationen und andere agile Organisationen (Sie können diese Empfehlung in jeder Umgebung verwenden, insbesondere in Cloudumgebungen)

- [Empfohlene Sicherheitsrichtlinien und Konfigurationen für Identitäten und Geräte](microsoft-365-policies-configurations.md) (diese Empfehlungen enthalten Hilfe für AD FS-Umgebungen)