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
description: Dieses Thema führt Sie durch die empfohlene Konfiguration für mandantenweite Einstellungen, die sich auf die Sicherheit Ihrer Microsoft 365 umgebung auswirken.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b1bb3f9bf6507e41d8b927137a9ab9ea8803637c
ms.sourcegitcommit: ccbdf2638fc6646bfb89450169953f4c3ce4b9b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/24/2021
ms.locfileid: "53105524"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Konfigurieren Ihres Microsoft 365-Mandanten für höhere Sicherheit 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Dieses Thema führt Sie durch die empfohlene Konfiguration für mandantenweite Einstellungen, die sich auf die Sicherheit Ihrer Microsoft 365 umgebung auswirken. Ihre Sicherheitsanforderungen erfordern möglicherweise mehr oder weniger Sicherheit. Verwenden Sie diese Empfehlungen als Ausgangspunkt.

## <a name="check-office-365-secure-score"></a>Überprüfen Office 365 Sicherheitsbewertung

Office 365 Die Sicherheitsbewertung analysiert die Sicherheit Ihrer Organisation basierend auf Ihren regulären Aktivitäten und Sicherheitseinstellungen und weist eine Bewertung zu. Notieren Sie sich zunächst Ihre aktuelle Bewertung. Das Anpassen einiger mandantenweiter Einstellungen erhöht Ihre Bewertung. Das Ziel besteht nicht darin, die maximale Punktzahl zu erreichen, sondern sich der Möglichkeiten bewusst zu sein, Ihre Umgebung zu schützen, die sich nicht negativ auf die Produktivität Ihrer Benutzer auswirken. Siehe [Microsoft-Sicherheitsbewertung.](../defender/microsoft-secure-score.md)

## <a name="tune-threat-management-policies-in-the-microsoft-365-defender-portal"></a>Optimieren von Richtlinien für die Bedrohungsverwaltung im Microsoft 365 Defender Portal

Das Microsoft 365 Defender-Portal enthält Funktionen, die Ihre Umgebung schützen. Es enthält auch Berichte und Dashboards, die Sie zum Überwachen und Ergreifen von Maßnahmen verwenden können. Einige Bereiche verfügen über Standardrichtlinienkonfigurationen. Einige Bereiche enthalten keine Standardrichtlinien oder -regeln. Besuchen Sie diese Richtlinien unter **E-Mail & Richtlinien** für die Zusammenarbeit \> **&** \> **Bedrohungsrichtlinien,** um die Einstellungen für das Bedrohungsmanagement für eine sicherere Umgebung zu optimieren.

<br>

****

|Bereich|Standardrichtlinie?|Empfehlung|
|---|---|---|
|**Antiphishing**|Ja|Konfigurieren Sie die standardmäßige Antiphishingrichtlinie wie hier beschrieben: [Konfigurieren von Antiphishingschutzeinstellungen in EOP und Defender für Office 365.](protect-against-threats.md#part-2---anti-phishing-protection-in-eop-and-defender-for-office-365) <p> Weitere Informationen: <ul><li>[Antiphishingrichtlinien in Microsoft 365](set-up-anti-phishing-policies.md)</li><li>[Empfohlene Antiphishingrichtlinieneinstellungen in Microsoft Defender für Office 365](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)</li><li> [Einblick in den Identitätswechsel](impersonation-insight.md)</li><li>[Einblick in die Spoofintelligenz in EOP](learn-about-spoof-intelligence.md)</li><li>[Verwalten der Mandanten-Zulassungs-/Sperrliste.](tenant-allow-block-list.md)</li></ul>|
|**Antischadsoftwaremodul**|Ja|Konfigurieren Sie die Standardmäßige Antischadsoftwarerichtlinie wie hier beschrieben: [Konfigurieren von Einstellungen zum Schutz vor Schadsoftware in EOP.](protect-against-threats.md#part-1---anti-malware-protection-in-eop) <p> Weitere Informationen: <ul><li>[Schutz vor Schadsoftware](anti-malware-protection.md)</li><li>[Empfohlene Richtlinieneinstellungen für Antischadsoftware](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)</li><li>[Konfigurieren von Antischadsoftwarerichtlinien](configure-anti-malware-policies.md)</li></ul>|
|**Sichere Anlagen in Defender für Office 365**|Nein|Konfigurieren Sie die globalen Einstellungen für Tresor Anlagen, und erstellen Sie eine Tresor Anlagenrichtlinie wie hier beschrieben: [Konfigurieren Tresor Anlageneinstellungen in Microsoft Defender für Office 365](protect-against-threats.md#safe-attachments-policies-in-microsoft-defender-for-office-365). <p> Weitere Informationen: <ul><li>[Empfohlene Einstellungen für Tresor Anlagen](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)</li><li>[Tresor Anlagen in Microsoft Defender für Office 365](safe-attachments.md)</li><li>[Einrichten von Richtlinien für sichere Anlagen](set-up-safe-attachments-policies.md)</li><li>[Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](mdo-for-spo-odb-and-teams.md)</li><li>[Sichere Dokumente in Microsoft 365 E5](safe-docs.md)</li></ul>|
|**Tresor Links in Microsoft Defender für Office 365**|Nein|Konfigurieren Sie die globalen Einstellungen für Tresor Links, und erstellen Sie eine richtlinie für Tresor Links, wie hier beschrieben: [Konfigurieren Tresor Links-Einstellungen in Microsoft Defender für Office 365](protect-against-threats.md#safe-links-policies-in-microsoft-defender-for-office-365). <p> Weitere Informationen: <ul><li>[Empfohlene Einstellungen für Tresor Links](recommended-settings-for-eop-and-office365.md#safe-links-settings)</li><li>[Einrichten von Richtlinien für sichere Links](set-up-safe-links-policies.md)</li><li>[Tresor Links in Microsoft Defender für Office 365](safe-links.md)</li><li>[Konfigurieren globaler Einstellungen für Tresor Links in Microsoft Defender für Office 365](configure-global-settings-for-safe-links.md)</li></ul>|
|**Antispam (E-Mail-Filterung)**|Ja|Konfigurieren Sie die standardmäßige Antispamrichtlinie wie hier beschrieben: [Konfigurieren von Antispamschutzeinstellungen in EOP](protect-against-threats.md#part-3---anti-spam-protection-in-eop) <p> Weitere Informationen: <ul><li>[Empfohlene Antispamrichtlinieneinstellungen](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)</li><li>[Antispamschutz in EOP](anti-spam-protection.md)</li><li>[Konfigurieren von Antispamrichtlinien in EOP](configure-your-spam-filter-policies.md)</li></ul>|
|***E-Mail-Authentifizierung***|Ja|Die E-Mail-Authentifizierung verwendet DNS-Einträge, um E-Mail-Nachrichten über die Nachrichtenquelle und den Absender überprüfbare Informationen hinzuzufügen. Microsoft 365 konfiguriert automatisch die E-Mail-Authentifizierung für die Standarddomäne (onmicrosoft.com), aber Microsoft 365 Administratoren können auch die E-Mail-Authentifizierung für benutzerdefinierte Domänen konfigurieren. Es werden drei Authentifizierungsmethoden verwendet: <ul><li>Sender Policy Framework (oder SPF).</li><ul><li>Informationen zum Einrichten finden Sie unter [Einrichten von SPF in Microsoft 365, um Spoofing zu verhindern.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</li></ul> <li>DomainKeys Identified Mail (DKIM).</li><ul><li>Siehe [Verwenden von DKIM zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne gesendet werden.](use-dkim-to-validate-outbound-email.md)</li><li>Nachdem Sie DKIM konfiguriert haben, aktivieren Sie es im Microsoft 365 Defender Portal.</li></ul><li>Domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität (DOMAIN-based Message Authentication, Reporting, and Conformance, DMARC).</li><ul><li>Verwenden Sie für das DMARC-Setup [DMARC, um E-Mails in Microsoft 365 zu überprüfen.](use-dmarc-to-validate-email.md)</li></ul></ul>|
|

> [!NOTE]
> Für nicht standardmäßige Bereitstellungen von SPF, Hybridbereitstellungen und Problembehandlung: [Wie Microsoft 365 Sender Policy Framework (SPF) verwendet, um Spoofing zu verhindern.](how-office-365-uses-spf-to-prevent-spoofing.md)

## <a name="view-dashboards-and-reports-in-the-microsoft-365-defender-portal"></a>Anzeigen von Dashboards und Berichten im Microsoft 365 Defender Portal

Besuchen Sie diese Berichte und Dashboards, um mehr über den Zustand Ihrer Umgebung zu erfahren. Die Daten in diesen Berichten werden reicher, wenn Ihre Organisation Office 365 Dienste verwendet. Machen Sie sich vorerst damit vertraut, was Sie überwachen und entsprechende Maßnahmen ergreifen können.

<br>

****

|Dashboard|Beschreibung|
|---|---|
|E-Mail-Sicherheitsberichte|Diese Berichte sind in Exchange Online Protection verfügbar. Weitere Informationen finden Sie unter [Anzeigen von E-Mail-Sicherheitsberichten im Microsoft 365 Defender Portal.](view-email-security-reports.md)|
|Defender für Office 365-Berichte|Die Berichte sind nur in Defender für Office 365 verfügbar. Weitere Informationen finden Sie unter [Anzeigen von Defender für Office 365 Berichte im Microsoft 365 Defender Portal.](view-reports-for-mdo.md)|
|Nachrichtenflussberichte und Einblicke|Diese Berichte und Einblicke sind im Exchange Admin Center (EAC) verfügbar. Weitere Informationen finden Sie unter [Nachrichtenflussberichte](/exchange/monitoring/mail-flow-reports/mail-flow-reports) und [Einblicke in den Nachrichtenfluss.](/exchange/monitoring/mail-flow-insights/mail-flow-insights)|
|[Sicherheitsrisiken-Explorer (oder Echtzeit-Erkennung)](threat-explorer.md)|Wenn Sie einen Angriff auf Ihren Mandanten untersuchen oder erleben, verwenden Sie Explorer (oder Echtzeiterkennungen), um Bedrohungen zu analysieren. Der Explorer (und der Bericht über Echtzeiterkennungen) zeigt Ihnen das Volumen von Angriffen im Laufe der Zeit an, und Sie können diese Daten nach Bedrohungsfamilien, Angreiferinfrastruktur und mehr analysieren. Sie können auch verdächtige E-Mails für die Vorfallliste markieren.|
|

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Konfigurieren zusätzlicher Exchange Online mandantenweiter Einstellungen

Hier sind einige zusätzliche Einstellungen, die empfohlen werden.

<br>

****

|Bereich|Empfehlung|
|---|---|
|**Nachrichtenflussregeln** (auch als Transportregeln bezeichnet)|Fügen Sie eine Nachrichtenflussregel zum Schutz vor Ransomware hinzu, indem Sie ausführbare Dateitypen und Office Dateitypen blockieren, die Makros enthalten. Weitere Informationen finden Sie unter [Verwenden von Nachrichtenflussregeln zum Überprüfen](/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments)von Nachrichtenanlagen in Exchange Online . <p> Sehen Sie sich diese zusätzlichen Themen an: <ul><li>[Schutz vor Ransomware](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Schutz vor Schadsoftware und Ransomware in Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Wiederherstellen von einem Ransomware-Angriff in Office 365](recover-from-ransomware.md)</li></ul> <p> Erstellen Sie eine Nachrichtenflussregel, um die automatische Weiterleitung von E-Mails an externe Domänen zu verhindern. Weitere Informationen finden Sie unter ["Minimieren externer Clientweiterleitungsregeln mit Sicherheitsbewertung".](/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) <p> Weitere Informationen: [Nachrichtenflussregeln (Transportregeln) in Exchange Online](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Moderne Authentifizierung**|Moderne Authentifizierung ist eine Voraussetzung für die Verwendung der mehrstufigen Authentifizierung (MFA). MFA wird empfohlen, um den Zugriff auf Cloudressourcen, einschließlich E-Mails, zu sichern. <p> Weitere Informationen finden Sie in den folgenden Themen: <ul><li>[Deaktivieren oder Aktivieren der modernen Authentifizierung in Exchange Online](/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business Online: Aktivieren Ihres Mandanten für die moderne Authentifizierung](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> Die moderne Authentifizierung ist standardmäßig für Office 2016-Clients, SharePoint Online und OneDrive for Business aktiviert. <p> Weitere Informationen: [Funktionsweise der modernen Authentifizierung für Office 2013- und Office 2016-Client-Apps](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Konfigurieren von mandantenweiten Freigaberichtlinien im SharePoint Admin Center

Microsoft-Empfehlungen zum Konfigurieren SharePoint Teamwebsites auf zunehmenden Schutzebenen, beginnend mit grundlegendem Schutz. Weitere Informationen finden Sie unter [Richtlinienempfehlungen zum Sichern SharePoint Websites und Dateien.](sharepoint-file-access-policies.md)

SharePoint Teamwebsites, die auf der Basisebene konfiguriert sind, ermöglichen das Freigeben von Dateien für externe Benutzer mithilfe anonymer Zugriffslinks. Dieser Ansatz wird empfohlen, anstatt Dateien per E-Mail zu senden.

Um die Ziele für grundlegenden Schutz zu unterstützen, konfigurieren Sie mandantenweite Freigaberichtlinien wie hier empfohlen. Freigabeeinstellungen für einzelne Websites können restriktiver sein als diese mandantenweite Richtlinie, aber nicht weniger restriktiv.

<br>

****

|Bereich|Enthält eine Standardrichtlinie|Empfehlung|
|---|---|---|
|**Freigabe** (SharePoint Online und OneDrive for Business)|Ja|Die externe Freigabe ist standardmäßig aktiviert. Diese Einstellungen werden empfohlen: <ul><li>Freigabe für authentifizierte externe Benutzer und Verwendung von Links für anonymen Zugriff zulassen (Standardeinstellung).</li><li>Links für anonymen Zugriff laufen in diesen vielen Tagen ab. Geben Sie bei Bedarf eine Zahl ein, z. B. 30 Tage.</li><li>Standardlinktyp – wählen Sie "Intern" aus (nur Personen in der Organisation). Benutzer, die mit anonymen Links teilen möchten, müssen diese Option im Freigabemenü auswählen.</li></ul> <p> Weitere Informationen: [Übersicht über die externe Freigabe](/sharepoint/external-sharing-overview)|
|

SharePoint Admin Center und OneDrive for Business Admin Center enthalten dieselben Einstellungen. Die Einstellungen in beiden Admin Center gelten für beide.

## <a name="configure-settings-in-azure-active-directory"></a>Konfigurieren von Einstellungen in Azure Active Directory

Besuchen Sie diese beiden Bereiche in Azure Active Directory, um die mandantenweite Einrichtung für sicherere Umgebungen abzuschließen.

### <a name="configure-named-locations-under-conditional-access"></a>Konfigurieren benannter Speicherorte (unter bedingtem Zugriff)

Wenn Ihre Organisation Büros mit sicherem Netzwerkzugriff umfasst, fügen Sie Azure Active Directory die vertrauenswürdigen IP-Adressbereiche als benannte Speicherorte hinzu. Dieses Feature trägt dazu bei, die Anzahl der gemeldeten falsch positiven Ergebnisse für Anmelderisikoereignisse zu verringern.

Siehe: [Benannte Speicherorte in Azure Active Directory](/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Blockieren von Apps, die die moderne Authentifizierung nicht unterstützen

Die mehrstufige Authentifizierung erfordert Apps, die die moderne Authentifizierung unterstützen. Apps, die die moderne Authentifizierung nicht unterstützen, können nicht mithilfe von Regeln für bedingten Zugriff blockiert werden.

Achten Sie bei sicheren Umgebungen darauf, die Authentifizierung für Apps zu deaktivieren, die die moderne Authentifizierung nicht unterstützen. Sie können dies in Azure Active Directory mit einem Steuerelement tun, das in Kürze verfügbar ist.

Verwenden Sie in der Zwischenzeit eine der folgenden Methoden, um dies für SharePoint Online und OneDrive for Business zu erreichen:

- Verwenden Sie PowerShell, siehe Blockieren von [Apps, die keine moderne Authentifizierung (ADAL) verwenden.](/mem/intune/protect/app-modern-authentication-block)
- Konfigurieren Sie dies im SharePoint Admin Center auf der Seite "Gerätezugriff" – "Steuern des Zugriffs von Apps, die keine moderne Authentifizierung verwenden". Wählen Sie "Blockieren" aus.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Erste Schritte mit Cloud App Security oder Office 365 Cloud App Security

Verwenden Sie Office 365 Cloud App Security, um Risiken zu bewerten, bei verdächtigen Aktivitäten zu warnen und automatisch Maßnahmen zu ergreifen. Erfordert Office 365 E5 Plan.

Oder verwenden Sie Microsoft Cloud App Security, um eine tiefere Sichtbarkeit zu erhalten, auch nachdem der Zugriff gewährt wurde, umfassende Kontrollen und verbesserter Schutz für alle Ihre Cloudanwendungen, einschließlich Office 365.

Da diese Lösung den EMS E5-Plan empfiehlt, empfehlen wir, mit Cloud App Security zu beginnen, damit Sie dies mit anderen SaaS-Anwendungen in Ihrer Umgebung verwenden können. Beginnen Sie mit Standardrichtlinien und -einstellungen.

Weitere Informationen:

- [Bereitstellen von Cloud App Security](/cloud-app-security/getting-started-with-cloud-app-security)
- [Weitere Informationen zu Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)
- [Was ist Microsoft Cloud App Security?](/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security-Dashboard](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Weitere Ressourcen

Diese Artikel und Handbücher enthalten zusätzliche Informationen zum Sichern Ihrer Microsoft 365 Umgebung:

- [Microsoft-Sicherheitsleitfaden für politische Kampagnen, gemeinnützige Organisationen und andere agile Organisationen](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) (Sie können diese Empfehlung in jeder Umgebung verwenden, insbesondere in reinen Cloudumgebungen).

- [Empfohlene Sicherheitsrichtlinien und Konfigurationen für Identitäten und Geräte](microsoft-365-policies-configurations.md) (diese Empfehlungen umfassen Hilfe für AD FS-Umgebungen)
