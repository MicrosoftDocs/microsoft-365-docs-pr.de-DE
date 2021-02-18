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
description: Dieses Thema führt Sie durch die empfohlene Konfiguration für mandantenweite Einstellungen, die sich auf die Sicherheit Ihrer Microsoft 365-Umgebung auswirken.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6eff529a4ab2271df30579af227fe0c28691ae58
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/18/2021
ms.locfileid: "50286345"
---
# <a name="configure-your-microsoft-365-tenant-for-increased-security"></a>Konfigurieren Ihres Microsoft 365-Mandanten für höhere Sicherheit 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**Gilt für**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender für Office 365 Plan 1 und Plan 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

Dieses Thema führt Sie durch die empfohlene Konfiguration für mandantenweite Einstellungen, die sich auf die Sicherheit Ihrer Microsoft 365-Umgebung auswirken. Ihre Sicherheitsanforderungen erfordern möglicherweise mehr oder weniger Sicherheit. Verwenden Sie diese Empfehlungen als Ausgangspunkt.

## <a name="check-office-365-secure-score"></a>Überprüfen der Office 365-Sicherheitsüberprüfung

Die Office 365-Sicherheitsanalyse analysiert die Sicherheit Ihrer Organisation basierend auf Ihren regulären Aktivitäten und Sicherheitseinstellungen und weist eine Bewertung zu. Notieren Sie sich zunächst Ihre aktuelle Bewertung. Wenn Sie einige mandantenweite Einstellungen anpassen, wird Ihre Bewertung erhöht. Ziel ist es nicht, die maximale Punktzahl zu erreichen, sondern sich der Möglichkeiten zum Schutz Ihrer Umgebung bewusst zu sein, die sich nicht negativ auf die Produktivität ihrer Benutzer auswirken. Siehe [Microsoft Secure Score](../mtp/microsoft-secure-score.md).

## <a name="tune-threat-management-policies-in-the-microsoft-365-security-center"></a>Optimieren der Richtlinien für die Bedrohungsverwaltung im Microsoft 365 Security Center

Das Microsoft 365 Security Center umfasst Funktionen zum Schutz Ihrer Umgebung. Es enthält auch Berichte und Dashboards, die Sie zum Überwachen und Ergreifen von Maßnahmen verwenden können. Einige Bereiche verfügen über Standardrichtlinienkonfigurationen. Einige Bereiche enthalten keine Standardrichtlinien oder -regeln. Besuchen Sie diese Richtlinien im Rahmen der Bedrohungsverwaltung, um die Einstellungen für die Bedrohungsverwaltung für eine sicherere Umgebung zu optimieren.

****

|Bereich|Enthält eine Standardrichtlinie|Empfehlung|
|---|---|---|
|**Antiphishing**|Ja|Wenn Sie über eine benutzerdefinierte Domäne verfügen, konfigurieren Sie die standardmäßige Antiphishingrichtlinie, um die E-Mail-Konten Ihrer wertvollsten Benutzer, z. B. Ihres CEO, und Ihre Domäne zu schützen. <p> Lesen [Sie die Antiphishingrichtlinien in Office 365, und](set-up-anti-phishing-policies.md) lesen Sie "Konfigurieren von [Antiphishingrichtlinien in EOP"](configure-anti-phishing-policies-eop.md) oder "Konfigurieren von [Antiphishingrichtlinien in Microsoft Defender für Office 365".](configure-atp-anti-phishing-policies.md)|
|**Ansoftwaremodul**|Ja| Bearbeiten Sie die Standardrichtlinie: <ul><li>Filter für allgemeine Anlagentypen: Aktivieren</li></ul> <p> Sie können auch benutzerdefinierte Filterrichtlinien für Schadsoftware erstellen und diese auf bestimmte Benutzer, Gruppen oder Domänen in Ihrer Organisation anwenden. <p> Weitere Informationen: <ul><li>[Schutz vor Schadsoftware](anti-malware-protection.md)</li><li>[Konfigurieren von Antischadsoftwarerichtlinien](configure-anti-malware-policies.md)</li></ul>|
|**Sichere Anlagen in Microsoft Defender für Office 365**|Nein|Klicken Sie auf der Hauptseite für sichere Anlagen auf **die globalen Einstellungen,** und aktivieren Sie diese Einstellung: <ul><li>**Defender für Office 365 für SharePoint, OneDrive und Microsoft Teams aktivieren**</li></ul> <p> Erstellen Sie eine Richtlinie für sichere Anlagen mit den folgenden Einstellungen: <ul><li> **Block**: Select **Block** as the unknown malware response.</li><li>**Umleitung aktivieren:** Aktivieren Sie dieses Kontrollkästchen, und geben Sie eine E-Mail-Adresse ein, z. B. ein Administrator- oder Quarantänekonto.</li><li>**Wenden Sie die oben aufgeführte Auswahl an,** wenn bei der Schadsoftwareprüfung auf Anlagen ein Zeitfehler auftritt oder ein Fehler auftritt: Aktivieren Sie dieses Kontrollkästchen.</li><li>**_Angewendet auf:_* **Die Empfängerdomäne wählt** \> Ihre Domäne aus.</li></ul> <p> Weitere Informationen: [Sichere Anlagen für SharePoint, OneDrive und Microsoft Teams](atp-for-spo-odb-and-teams.md) und Einrichten von Richtlinien für sichere [Anlagen](set-up-atp-safe-attachments-policies.md)|
|**Sichere Links in Microsoft Defender für Office 365**|Ja|Klicken Sie auf der Hauptseite für sichere Links auf **globale Einstellungen:** <ul><li>**Verwenden Sie sichere Links in: Office 365-Anwendungen:** Stellen Sie sicher, dass diese Einstellung aktiviert ist.</li><li>**Nicht nachverfolgen, wenn Benutzer auf "Sichere Links"** klicken: Deaktivieren Sie diese Einstellung, um Benutzerklicks nachverfolgt zu werden.</li></ul> <p> Erstellen Sie eine Richtlinie für sichere Links mit den folgenden Einstellungen: <ul><li>**Wählen Sie die Aktion für unbekannte potenziell schädliche URLs in Nachrichten** aus: Stellen Sie sicher, dass diese Einstellung ein **ist.**</li><li>**Wählen Sie die Aktion für unbekannte oder potenziell schädliche URLs in Microsoft Teams** aus: Stellen Sie sicher, dass diese Einstellung ein **ist.**</li><li>**Anwenden der Echtzeit-URL-Überprüfung auf verdächtige Links** und Links, die auf Dateien verweisen: Aktivieren Sie dieses Kontrollkästchen.</li><li>**Warten Sie, bis die URL-Überprüfung abgeschlossen ist, bevor** Sie die Nachricht zu senden: Aktivieren Sie dieses Kontrollkästchen.</li><li>**Sichere Links auf E-Mail-Nachrichten anwenden, die innerhalb der Organisation gesendet werden:** Aktivieren Sie dieses Kontrollkästchen.</li><li>**Benutzer dürfen nicht zur ursprünglichen URL klicken:** Aktivieren Sie dieses Kontrollkästchen.</li><li>**Angewendet auf:** **Die Empfängerdomäne ist** \> Ihre Domäne.</li></ul> <p> Weitere Informationen: [Einrichten von Richtlinien für sichere Links](set-up-atp-safe-links-policies.md).|
|**Antispam (E-Mail-Filterung)**|Ja| Was Sie sich ansehen müssen: <ul><li>Zu viel Spam – Wählen Sie die benutzerdefinierten Einstellungen aus, und bearbeiten Sie die Standard-Spamfilterrichtlinie.</li><li>Spoofintelligenz – Überprüfen Sie Absender, die Ihre Domäne gefälscht haben. Blockieren oder zulassen Sie diese Absender.</li></ul> <p> Weitere Informationen: [Microsoft 365 Email Anti-Spam Protection](anti-spam-protection.md).|
|***E-Mail-Authentifizierung***|Ja|Bei der E-Mail-Authentifizierung wird ein Dns (Domain Name System) verwendet, um E-Mail-Nachrichten über den Absender einer E-Mail überprüfbare Informationen hinzuzufügen. Microsoft 365 richtet die E-Mail-Authentifizierung für die Standarddomäne (onmicrosoft.com) ein, Aber Microsoft 365-Administratoren können auch die E-Mail-Authentifizierung für benutzerdefinierte Domänen verwenden. Es werden drei Authentifizierungsmethoden verwendet: <ul><li>Sender Policy Framework (oder SPF).</li><ul><li>Informationen zum Einrichten finden Sie [unter Einrichten von SPF in Microsoft 365, um Spoofing zu verhindern.](set-up-spf-in-office-365-to-help-prevent-spoofing.md)</li></ul> <li>DomainKeys Identified Mail (DKIM).</li><ul><li>Informationen [zum Überprüfen ausgehender E-Mails, die von Ihrer benutzerdefinierten Domäne](use-dkim-to-validate-outbound-email.md)gesendet werden, finden Sie unter "Verwenden von DKIM".</li><li>Nachdem Sie DKIM konfiguriert haben, aktivieren Sie es im Security Center.</li></ul><li>Domänenbasierte Nachrichtenauthentifizierung, Berichterstellung und Konformität (DMARC).</li><ul><li>Verwenden Sie für das Setup von [DMARC DMARC, um E-Mails in Microsoft 365 zu überprüfen.](use-dmarc-to-validate-email.md)</li></ul></ul>|
|

> [!NOTE]
> Für nicht standardmäßige Bereitstellungen von SPF, Hybridbereitstellungen und Problembehandlung: Wie [Microsoft 365 Sender Policy Framework (SPF)](how-office-365-uses-spf-to-prevent-spoofing.md)verwendet, um Spoofing zu verhindern.

## <a name="view-dashboards-and-reports-in-the-security-and-compliance-centers"></a>Anzeigen von Dashboards und Berichten im Security and Compliance Center

Besuchen Sie diese Berichte und Dashboards, um mehr über den Zustand Ihrer Umgebung zu erfahren. Die Daten in diesen Berichten werden reicher, wenn Ihre Organisation Office 365-Dienste verwendet. Machen Sie sich vorerst mit dem vertraut, wofür Sie überwachen und Maßnahmen ergreifen können. Weitere Informationen finden Sie unter : [Berichte im Microsoft 365 Security and Compliance Center](../../compliance/reports-in-security-and-compliance.md).

****

|Dashboard|Beschreibung|
|---|---|
|[Dashboard für die Bedrohungsverwaltung](security-dashboard.md)|Verwenden  Sie im Abschnitt "Bedrohungsverwaltung" des Security Centers dieses Dashboard, um Bedrohungen anzuzeigen, die bereits behandelt wurden, und als praktisches Tool, um Geschäftlichen Entscheidungsträgern zu melden, welche Bedrohungsuntersuchungs- und Reaktionsfunktionen bereits zum Sichern Ihres Unternehmens durchgeführt wurden.|
|[Sicherheitsrisiken-Explorer (oder Echtzeit-Erkennung)](threat-explorer.md)|Dies befindet sich auch im Abschnitt **"Bedrohungsverwaltung"** des Security Centers. Wenn Sie einen Angriff auf Ihren Mandanten untersuchen oder auftreten, verwenden Sie Explorer (oder Echtzeiterkennungen), um Bedrohungen zu analysieren. Explorer (und der Bericht über Echtzeiterkennungen) zeigt Ihnen das Volumen der Angriffe im Laufe der Zeit, und Sie können diese Daten nach Bedrohungsfamilien, Angreiferinfrastruktur und vielem mehr analysieren. Sie können auch jede verdächtige E-Mail für die Vorfallliste markieren.|
|Berichte – Dashboard|Zeigen Sie **im Abschnitt** "Berichte" des Sicherheitscenters Überwachungsberichte für Ihre SharePoint Online- und Exchange Online-Organisationen an. Sie können auch über die Seite "Berichte anzeigen" auf Azure Active Directory (Azure AD)-Benutzer-Anmeldeberichte, Benutzeraktivitätsberichte und das Azure AD-Überwachungsprotokoll **zugreifen.**|
|

![Security center Dashboard](../../media/870ab776-36d2-49c7-b615-93b2bc42fce5.png)

## <a name="configure-additional-exchange-online-tenant-wide-settings"></a>Konfigurieren zusätzlicher mandantenweiter Exchange Online-Einstellungen

Viele der Steuerelemente für Sicherheit und Schutz im Exchange Admin Center sind auch im Security Center enthalten. Sie müssen diese nicht an beiden Stellen konfigurieren. Hier sind einige zusätzliche Einstellungen, die empfohlen werden.

****

|Bereich|Enthält eine Standardrichtlinie|Empfehlung|
|---|---|---|
|**Nachrichtenfluss** (Nachrichtenflussregeln, auch als Transportregeln bekannt)|Nein|Fügen Sie eine Nachrichtenflussregel zum Schutz vor Ransomware hinzu, indem Sie ausführbare Dateitypen und Office-Dateitypen, die Makros enthalten, blockieren. Weitere Informationen finden Sie unter [Verwenden von Nachrichtenflussregeln zum Überprüfen von Nachrichtenanlagen in Exchange Online.](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/inspect-message-attachments) <p> Weitere Informationen finden Sie in den folgenden Themen: <ul><li>[Schutz vor Ransomware](../../admin/security-and-compliance/secure-your-business-data.md#5-protect-against-ransomware)</li><li>[Schutz vor Schadsoftware und Ransomware in Microsoft 365](https://docs.microsoft.com/compliance/assurance/assurance-malware-and-ransomware-protection)</li><li>[Wiederherstellen nach einem Ransomware-Angriff in Office 365](recover-from-ransomware.md)</li></ul> <p> Erstellen Sie eine Nachrichtenflussregel, um die automatische Weiterleitung von E-Mails an externe Domänen zu verhindern. Weitere Informationen finden Sie unter ["Minderung externer Client-Weiterleitungsregeln mit Sicherheitsergebnis".](https://docs.microsoft.com/archive/blogs/office365security/mitigating-client-external-forwarding-rules-with-secure-score) <p> Weitere Informationen: [Nachrichtenflussregeln (Transportregeln) in Exchange Online](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules)|
|**Aktivieren der modernen Authentifizierung**|Nein|Die moderne Authentifizierung ist eine Voraussetzung für die Verwendung der mehrstufigen Authentifizierung (MFA). MFA wird zum Sichern des Zugriffs auf Cloudressourcen, einschließlich E-Mails, empfohlen. <p> Weitere Informationen finden Sie in den folgenden Themen: <ul><li>[Deaktivieren oder Aktivieren der modernen Authentifizierung in Exchange Online](https://docs.microsoft.com/Exchange/clients-and-mobile-in-exchange-online/enable-or-disable-modern-authentication-in-exchange-online)</li><li>[Skype for Business Online: Aktivieren Ihres Mandanten für die moderne Authentifizierung](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)</li></ul> <p> Die moderne Authentifizierung ist standardmäßig für Office 2016-Clients, SharePoint Online und OneDrive for Business aktiviert. <p> Weitere Informationen: Funktionsweise der modernen Authentifizierung für [Office 2013- und Office 2016-Client-Apps](../../enterprise/modern-auth-for-office-2013-and-2016.md)|
|

## <a name="configure-tenant-wide-sharing-policies-in-sharepoint-admin-center"></a>Konfigurieren mandantenweite Freigaberichtlinien im SharePoint Admin Center

Empfehlungen von Microsoft für die Konfiguration von SharePoint-Teamwebsites auf einem zunehmenden Schutzniveau, beginnend mit dem grundlegenden Schutz. Weitere Informationen finden Sie unter [Richtlinienempfehlungen zum Sichern von SharePoint-Websites und -Dateien.](sharepoint-file-access-policies.md)

Auf der Basisebene konfigurierte SharePoint-Teamwebsites ermöglichen die Freigabe von Dateien für externe Benutzer mithilfe von Links für anonymen Zugriff. Dieser Ansatz wird empfohlen, anstatt Dateien per E-Mail zu senden.

Um die Ziele für den grundlegenden Schutz zu unterstützen, konfigurieren Sie mandantenweite Freigaberichtlinien, wie hier empfohlen. Freigabeeinstellungen für einzelne Websites können restriktiver sein als diese mandantenweite Richtlinie, aber nicht weniger restriktiv.

****

|Bereich|Enthält eine Standardrichtlinie|Empfehlung|
|---|---|---|
|**Freigabe** (SharePoint Online und OneDrive for Business)|Ja|Die externe Freigabe ist standardmäßig aktiviert. Diese Einstellungen werden empfohlen: <ul><li>Freigabe für authentifizierte externe Benutzer zulassen und Links für anonymen Zugriff verwenden (Standardeinstellung).</li><li>Links für anonymen Zugriff laufen in diesen vielen Tagen ab. Geben Sie bei Bedarf eine Zahl ein, z. B. 30 Tage.</li><li>Standardlinktyp – Wählen Sie "Intern" aus (nur Personen in der Organisation). Benutzer, die anonyme Links verwenden möchten, müssen diese Option im Menü "Freigabe" auswählen.</li></ul> <p> Weitere Informationen: [Übersicht über die externe Freigabe](https://docs.microsoft.com/sharepoint/external-sharing-overview)|
|

SharePoint Admin Center und OneDrive for Business Admin Center enthalten die gleichen Einstellungen. Die Einstellungen in beiden Admin Center gelten für beide.

## <a name="configure-settings-in-azure-active-directory"></a>Konfigurieren von Einstellungen in Azure Active Directory

Besuchen Sie diese beiden Bereiche in Azure Active Directory, um die mandantenweite Einrichtung für sicherere Umgebungen abzuschließen.

### <a name="configure-named-locations-under-conditional-access"></a>Konfigurieren benannter Speicherorte (unter bedingten Zugriff)

Wenn Ihre Organisation Büros mit sicherem Netzwerkzugriff umfasst, fügen Sie Azure Active Directory die vertrauenswürdigen IP-Adressbereiche als benannte Speicherorte hinzu. Mit diesem Feature kann die Anzahl der gemeldeten falsch positiven Ergebnisse für Anmelderisikoereignisse reduziert werden.

Siehe: [Benannte Speicherorte in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-named-locations)

### <a name="block-apps-that-dont-support-modern-authentication"></a>Blockieren von Apps, die die moderne Authentifizierung nicht unterstützen

Die mehrstufige Authentifizierung erfordert Apps, die die moderne Authentifizierung unterstützen. Apps, die die moderne Authentifizierung nicht unterstützen, können nicht mithilfe von Regeln für bedingten Zugriff blockiert werden.

Deaktivieren Sie für sichere Umgebungen die Authentifizierung für Apps, die die moderne Authentifizierung nicht unterstützen. Sie können dies in Azure Active Directory mit einem Steuerelement tun, das in Kürze verfügbar ist.

In the meantime, use one of the following methods to accomplish this for SharePoint Online and OneDrive for Business:

- Verwenden Sie PowerShell, siehe [Blockieren von Apps, die keine moderne Authentifizierung (ADAL) verwenden.](https://docs.microsoft.com/mem/intune/protect/app-modern-authentication-block)

- Konfigurieren Sie dies im SharePoint Admin Center auf der Seite "Gerätezugriff" – "Steuern des Zugriffs von Apps, die keine moderne Authentifizierung verwenden". Wählen Sie "Blockieren" aus.

## <a name="get-started-with-cloud-app-security-or-office-365-cloud-app-security"></a>Erste Schritte mit Cloud App Security oder Office 365 Cloud App Security

Verwenden Sie Office 365 Cloud App Security, um Risiken auszuwerten, verdächtige Aktivitäten zu warnen und automatisch Maßnahmen zu ergreifen. Erfordert einen Office 365 E5-Plan.

Oder verwenden Sie Microsoft Cloud App Security, um tiefere Einblicke zu erhalten, auch nachdem der Zugriff gewährt wurde, umfassende Kontrollen und verbesserten Schutz für alle Ihre Cloudanwendungen, einschließlich Office 365.

Da diese Lösung den EMS -E5-Plan empfiehlt, empfehlen wir, mit Cloud App Security zu beginnen, damit Sie dies mit anderen SaaS-Anwendungen in Ihrer Umgebung verwenden können. Beginnen Sie mit Standardrichtlinien und -einstellungen.

Weitere Informationen:

- [Bereitstellen von Cloud App Security](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security)

- [Weitere Informationen zu Microsoft Cloud App Security](https://www.microsoft.com/cloud-platform/cloud-app-security)

- [Was ist Cloud App Security?](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)

![Cloud App Security-Dashboard](../../media/1fb2aa65-54b8-4746-9f5e-c187d339e9f5.png)

## <a name="additional-resources"></a>Weitere Ressourcen

Diese Artikel und Leitfäden enthalten zusätzliche Informationen zum Sichern Ihrer Microsoft 365-Umgebung:

- [Sicherheitsleitfaden von Microsoft](microsoft-security-guidance-for-political-campaigns-nonprofits-and-other-agile-o.md) für politische Kampagnen, gemeinnützige Organisationen und andere agile Organisationen (Sie können diese Empfehlung in jeder Umgebung verwenden, insbesondere in Umgebungen, in denen nur die Cloud verwendet wird)

- [Empfohlene Sicherheitsrichtlinien und -konfigurationen für Identitäten und Geräte](microsoft-365-policies-configurations.md) (diese Empfehlungen umfassen Hilfe für AD FS-Umgebungen)
