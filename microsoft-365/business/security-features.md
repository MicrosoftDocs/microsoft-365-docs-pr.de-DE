---
title: Microsoft 365 Business Premium-Sicherheits-und Compliance-Features
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: reference
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-security-compliance
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: c123694a-1efb-459e-a8d5-2187975373dc
description: Erfahren Sie mehr über die Sicherheitsfunktionen, die mit Microsoft 365 Business Premium geliefert werden, um Ihre Daten auf PCs, Telefonen und Tablets zu schützen.
ms.openlocfilehash: 839b5481e27591e1762a0d8eb5623f279d6d22dd
ms.sourcegitcommit: 2d59b24b877487f3b84aefdc7b1e200a21009999
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/27/2020
ms.locfileid: "44402712"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Microsoft 365 Business Premium-Sicherheits-und Compliance-Features

Microsoft 365 Business Premium bietet vereinfachte Sicherheitsfunktionen zum Schutz Ihrer Daten auf PCs, Telefonen und Tablets.
    
## <a name="microsoft-365-admin-center-security-features"></a>Microsoft 365 Admin Center-Sicherheitsfeatures

[![Hinweis, der Sie darüber informiert, dass sich das Admin Center ändert und Sie unter "aka.ms/aboutM365preview" weitere Details finden.](../media/m365admincenterchanging.png)](https://docs.microsoft.com/office365/admin/microsoft-365-admin-center-preview)

Sie können viele der Microsoft 365 Business Premium-Sicherheitsfunktionen im Admin Center verwalten, wodurch Sie eine vereinfachte Möglichkeit zum Aktivieren oder Deaktivieren dieser Features erhalten. Im Admin Center können Sie folgendermaßen vorgehen:
  
- [Legen Sie Anwendungs Verwaltungseinstellungen für Android-oder IOS-Geräte fest](app-protection-settings-for-android-and-ios.md) . 
    
    Zu diesen Einstellungen gehören das Löschen von Dateien aus einem inaktiven Gerät nach einem festgelegten Zeitraum, das Verschlüsseln von Arbeitsdateien, die Anforderung, dass Benutzer eine PIN festlegen usw.
    
- [Legen Sie Anwendungsschutz Einstellungen für Windows 10-Geräte fest](protection-settings-for-windows-10-devices.md) . 
    
    Diese Einstellungen können auf Unternehmensdaten sowohl auf unternehmenseigenen als auch auf persönlichen eigenen Geräten angewendet werden.
    
- [Festlegen von Geräteschutz Einstellungen für Windows 10-Geräte](protection-settings-for-windows-10-pcs.md) . 
    
    Sie können die [BitLocker](https://go.microsoft.com/fwlink/p/?linkid=871405) -Verschlüsselung aktivieren, um Daten für den Fall zu schützen, dass ein Gerät verloren geht oder gestohlen wird, und [Windows Exploit Guard](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) für erweiterten Schutz gegen Ransomware bereitzustellen. 
    
- [Entfernen von Unternehmensdaten von Geräten](remove-company-data.md)
    
    Sie können Unternehmensdaten Remote löschen, wenn ein Gerät verloren geht, gestohlen wird oder ein Mitarbeiter Ihr Unternehmen verlässt.
    
- [Zurücksetzen von Windows 10-Geräten auf die Werkseinstellungen](reset-devices-to-factory-settings.md) . 
    
    Sie können alle Windows 10-Geräte zurücksetzen, auf die Geräteschutz Einstellungen angewendet wurden.
    
## <a name="additional-security-features"></a>Zusätzliche Sicherheitsfeatures 

Erweiterte Features in Microsoft 365 Business Premium stehen Ihnen zum Schutz Ihres Unternehmens vor Cyber-Bedrohungen und zum Schutz vertraulicher Informationen zur Verfügung.
  
- **[Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)**
    
    Advanced Threat Protection (ATP) schützt Ihr Unternehmen vor ausgeklügelten Phishing-und Ransomware-Angriffen, die dazu dienen, Mitarbeiter-oder Kundeninformationen zu kompromittieren. Zu den Features gehören:
    
  - Ausgeklügelte Anlagen Scans und AI-basierte Analyse zum erkennen und verwerfen gefährlicher Nachrichten.
    
  - Automatische Überprüfung von Links in e-Mails, um festzustellen, ob Sie Teil eines Phishing-Schemas sind. Dadurch können Sie sicher vor dem Zugriff auf unsichere Websites schützen.

- **[Die vollständigen Funktionen von InTune im Azure-Portal](https://go.microsoft.com/fwlink/p/?linkid=871403)**
    
    Wenn Sie auf das InTune-Verwaltungscenter im Azure-Portal zugreifen, können Sie zusätzliche Sicherheitsfeatures wie die Verwaltung von MacOS-Geräten, iPhone und Android-Geräten sowie erweiterte Geräteverwaltung für Windows einrichten, die über das Microsoft 365 Admin Center nicht verfügbar sind.
- **Gleicher [bedingter Zugriff](https://docs.microsoft.com/azure/active-directory/conditional-access/overview) wie Azure AD Premium P1-Plan**


    Bedingter Zugriff kann zum Schutz Ihrer Organisation vor Anmelde Risiken, zum Zugriff auf Versuche von einem unerwarteten Netzwerk oder Gebietsschema, zum Zugreifen auf Versuche von riskanten Gerätetypen usw. beitragen. Richtlinien für bedingten Zugriff werden nach Abschluss der ersten Authentifizierung erzwungen, und es werden Signale aus dem ersten Authentifizierungsereignis verwendet, um zu ermitteln, ob der versuchte Zugriff genehmigt, verweigert oder wenn mehr Beweise (beispielsweise eine zweite Form der Identifikation) erforderlich sind.

    Zu den bedingten Zugriffsfunktionen gehören:

    - Zugriff basierend auf Benutzername, Gruppe und Rolle
    - Zugriff [basierend auf einer APP](https://docs.microsoft.com/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Zugriff basierend auf dem Standort](https://docs.microsoft.com/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  Zugriff nur aus vertrauenswürdigen IP-Bereichen oder bestimmten Ländern zulassen 
    - MFA für den Zugriff erforderlich
    - Blockieren des Zugriffs auf apps, die die [Legacy Authentifizierung](https://docs.microsoft.com/azure/active-directory/conditional-access/block-legacy-authentication) verwenden
    - Apps erfordern TP use [InTune-App-Schutz](https://docs.microsoft.com/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Benutzerdefinierte Authentifizierung wie MFA mit Drittanbietern, beispielsweise Duo.
   
    Sonstige Features:
    - [Self-Service-Kennwortzurücksetzung](https://docs.microsoft.com/azure/active-directory/authentication/concept-sspr-customization) für Hybrid Azure AD
    
## <a name="compliance-features"></a>Compliance-Features

Ihr Microsoft 365 Business Premium-Abonnement umfasst Features, mit denen Sie Compliance-und regulatorische Standards aufrecht erhalten können.

- **[Übersicht über die Richtlinien zur Verhinderung von Datenverlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies)** (DLP). 
    
    Sie können DLP so einrichten, dass vertrauliche Informationen wie Kreditkartennummern, Sozialversicherungsnummern usw. automatisch erkannt werden, um eine unbeabsichtigte Freigabe außerhalb Ihres Unternehmens zu verhindern.
    
- **[Exchange Online-Archivierung](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online Archivierungslizenz ermöglicht das einfache Archivieren von Nachrichten mit fortlaufender Datensicherung. Sie speichert alle e-Mail-Nachrichten eines Benutzers, einschließlich gelöschter Elemente, für den Fall, dass Sie später zur Ermittlung oder Wiederherstellung benötigt werden. Darüber hinaus können Sie unterschiedliche Aufbewahrungsrichtlinien verwenden, um e-Mail-Daten für Beweissicherungsverfahren, eDiscovery oder zur Erfüllung von Compliance-Anforderungen beizubehalten.
    
- **[Vertraulichkeitsbezeichnungen](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)**

   Microsoft 365 Business Premium umfasst alle Funktionen von [Azure Information Protection Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407). Mit diesem Plan können Sie **Sensitivitäts Bezeichnungen** erstellen, mit denen Sie den Zugriff auf vertrauliche Informationen in e-Mails und Dokumenten steuern können, mit Steuerelementen wie "nicht weiterleiten" und "nicht kopieren". Sie können vertrauliche Informationen auch als "vertraulich" klassifizieren und angeben, wie klassifizierte Informationen außerhalb und innerhalb des Unternehmens freigegeben werden können. Die unternehmensweite Verschlüsselung lässt sich einfach auf e-Mails und Dokumente anwenden, um Ihre Informationen privat zu halten. Sie können auch das Azure Information Protection-Client-Add-in für Office-Apps installieren. Weitere Informationen finden Sie unter [Azure Information Protection Unified Labelling-Client](https://docs.microsoft.com/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). Für Sensitivitäts Bezeichnungen installieren Sie die **AzInfoProtection_UL. exe**.

Sie können diese Funktionen im Security &amp; Compliance Center und im InTune Admin Center verwalten. Im Laufe der Zeit werden die vereinfachten Steuerelemente dem Microsoft 365 Admin Center hinzugefügt.
  
    
## <a name="faq"></a>Häufig gestellte Fragen

 ### <a name="are-these-security-features-available-in-all-markets"></a>Sind diese Sicherheitsfeatures in allen Märkten verfügbar?
  
Ja, diese Features stehen in allen Märkten zur Verfügung, in denen Microsoft 365 Business Premium verkauft wird.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Wie finde ich das Security &amp; Compliance Center?
  
1. Melden Sie sich mit Ihren Administratoranmeldeinformationen bei [Microsoft 365 Business Premium](https://portal.microsoft.com/) an. 
    
2. Suchen Sie im linken Navigationsbereich **Admin Center** , und erweitern Sie es. 
    
    ![Wählen Sie im linken Navigationsbereich im Microsoft 365 Admin Center die Option Admin Center aus.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Wählen Sie **Security &amp; Compliance** , um zum Security &amp; Compliance Center zu gelangen.
