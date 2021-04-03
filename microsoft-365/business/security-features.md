---
title: Microsoft 365 Business Premium-Sicherheits- und Compliancefeatures
f1.keywords:
- NOCSH
ms.author: sharik
author: skjerland
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
description: Erfahren Sie mehr über die Sicherheitsfeatures von Microsoft 365 Business Premium, um Ihre Daten auf PCs, Smartphones und Tablets zu schützen.
ms.openlocfilehash: bca20a7a03a93f7ac2bf8752476046f0db43cc70
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578145"
---
# <a name="microsoft-365-business-premium-security-and-compliance-features"></a>Microsoft 365 Business Premium-Sicherheits- und Compliancefeatures

Microsoft 365 Business Premium bietet vereinfachte Sicherheitsfeatures zum Schutz Ihrer Daten auf PCs, Smartphones und Tablets.
    
## <a name="microsoft-365-admin-center-security-features"></a>Sicherheitsfeatures für Microsoft 365 Admin Center

Sie können viele der Microsoft 365 Business Premium-Sicherheitsfeatures im Admin Center verwalten, wodurch Sie diese Features einfacher aktivieren oder deaktivieren können. Im Admin Center können Sie folgendes tun:
  
- [Festlegen von Anwendungsverwaltungseinstellungen für Android- oder iOS-Geräte](app-protection-settings-for-android-and-ios.md) . 
    
    Zu diesen Einstellungen gehören das Löschen von Dateien von einem inaktiven Gerät nach einem festgelegten Zeitraum, das Verschlüsseln von Arbeitsdateien, das Festlegen einer PIN durch Benutzer und so weiter.
    
- [Festlegen von Anwendungsschutzeinstellungen für Windows 10-Geräte](protection-settings-for-windows-10-devices.md) . 
    
    Diese Einstellungen können auf Unternehmensdaten auf unternehmenseigenen oder persönlichen Geräten angewendet werden.
    
- [Festlegen von Geräteschutzeinstellungen für Windows 10-Geräte](protection-settings-for-windows-10-pcs.md) . 
    
    Sie können die [BitLocker-Verschlüsselung](/windows/security/information-protection/bitlocker/bitlocker-frequently-asked-questions) aktivieren, um Daten zu schützen, falls ein Gerät verloren geht oder gestohlen wird, und [Windows Exploit Guard](/windows/security/threat-protection/microsoft-defender-atp/enable-exploit-protection) einen erweiterten Schutz vor Ransomware ermöglichen. 
    
- [Entfernen von Unternehmensdaten von Geräten](remove-company-data.md)
    
    Sie können Unternehmensdaten remote wischen, wenn ein Gerät verloren geht, gestohlen wird oder ein Mitarbeiter Ihr Unternehmen verlässt.
    
- [Setzen Sie Windows 10-Geräte auf ihre Werkseinstellungen zurück.](reset-devices-to-factory-settings.md) 
    
    Sie können alle Windows 10-Geräte zurücksetzen, auf die Geräteschutzeinstellungen angewendet wurden.
    
## <a name="additional-security-features"></a>Zusätzliche Sicherheitsfeatures 

Die erweiterten Features in Microsoft 365 Business Premium helfen Ihnen, Ihr Unternehmen vor Cyberbedrohungen zu bewahren und vertrauliche Informationen zu schützen.
  
- **[Microsoft Defender für Office 365](../security/office-365-security/defender-for-office-365.md)**
    
    Microsoft Defender für Office 365 schützt Ihr Unternehmen vor ausgefeilten Phishing- und Ransomwareangriffen, die Mitarbeiter- oder Kundeninformationen gefährdet. Zu den Features gehören:
    
  - Ausgefeilte Anlagenscans und AI-betriebene Analysen zum Erkennen und Verwerfen von gefährlichen Nachrichten.
    
  - Automatische Überprüfungen von Links in E-Mails, um zu bewerten, ob sie Teil eines Phishingschemas sind. Dadurch können Sie nicht auf unsichere Websites zugreifen.

- **[Die vollständigen Funktionen von Intune im Azure-Portal](/mem/intune/fundamentals/what-is-intune)**
    
    Durch den Zugriff auf das Intune Admin Center im Azure-Portal können Sie zusätzliche Sicherheitsfeatures einrichten, z. B. die Verwaltung von MacOS-, iPhone- und Android-Geräten sowie erweiterte Geräteverwaltung für Windows, die nicht über das Microsoft 365 Admin Center verfügbar sind.
- **Gleicher [bedingter Zugriff](/azure/active-directory/conditional-access/overview) wie Azure AD Premium P1-Plan**


    Bedingter Zugriff kann Ihre Organisation vor Anmelderisiken, Zugriffsversuchen aus einem unerwarteten Netzwerk oder Locale, Zugriffsversuchen von riskanten Gerätetypen und so weiter schützen. Richtlinien für bedingten Zugriff werden nach Abschluss der ersten Authentifizierung erzwungen und verwenden Signale des ersten Authentifizierungsereigniss, um festzustellen, ob der versuchte Zugriff genehmigt, verweigert oder ob weitere Nachweise (z. B. eine zweite Form der Identifizierung) erforderlich sind.

    Die enthaltenen Features für bedingten Zugriff sind:

    - Zugriff basierend auf Benutzername, Gruppe und Rolle
    - Zugriff [basierend auf einer App](/azure/active-directory/conditional-access/app-based-conditional-access) 
    - [Zugriff basierend auf Standort](/azure/active-directory/authentication/howto-registration-mfa-sspr-combined#conditional-access-policies-for-combined-registration);  Nur Zugriff von vertrauenswürdigen IP-Bereichen oder bestimmten Ländern zulassen 
    - MFA für zugriff erforderlich
    - Blockieren des Zugriffs auf Apps, die die ältere [Authentifizierung verwenden](/azure/active-directory/conditional-access/block-legacy-authentication)
    - Erfordern, dass Apps den [Intune-App-Schutz verwenden](/azure/active-directory/conditional-access/app-protection-based-conditional-access)
    - Benutzerdefinierte Authentifizierung wie MFA bei Drittanbietern, z. B. DUO.
   
    Sonstige Features:
    - [Self-Service-Kennwortzurücksetzung](/azure/active-directory/authentication/concept-sspr-customization) für Azure AD-Hybrid
    
## <a name="compliance-features"></a>Compliance-Features

Ihr Microsoft 365 Business Premium-Abonnement enthält Features, mit deren Hilfe Sie Compliance- und behördliche Standards einhalten können.

- **[Übersicht über Richtlinien zur Verhinderung von Datenverlust](../compliance/data-loss-prevention-policies.md)** (Data Loss Prevention Policies, DLP). 
    
    Sie können DLP so einrichten, dass vertrauliche Informationen wie Kreditkartennummern, Sozialversicherungsnummern und so weiter automatisch erkannt werden, um die unbeabsichtigte Freigabe außerhalb Ihres Unternehmens zu verhindern.
    
- **[Exchange Online-Archivierung](https://products.office.com/exchange/microsoft-exchange-online-archiving-email)**
    
    Exchange Online-Archivierung-Lizenz ermöglicht die einfache Archivierung von Nachrichten mit kontinuierlicher Datensicherung. Es speichert alle E-Mails eines Benutzers, einschließlich gelöschter Elemente, falls sie später für die Ermittlung oder Wiederherstellung benötigt werden. Darüber hinaus können Sie unterschiedliche Aufbewahrungsrichtlinien verwenden, um E-Mail-Daten für Rechtsstreitigkeiten, eDiscovery oder zur Erfüllung von Complianceanforderungen zu speichern.
    
- **[Vertraulichkeitsbezeichnungen](../compliance/sensitivity-labels.md)**

   Microsoft 365 Business Premium enthält alle Features von [Azure Information Protection Plan 1](https://go.microsoft.com/fwlink/p/?linkid=871407). Mit diesem Plan können  Sie Vertraulichkeitsbezeichnungen erstellen, mit denen Sie den Zugriff auf vertrauliche Informationen in E-Mails und Dokumenten steuern können, mit Steuerelementen wie "Nicht weiterleiten" und "Nicht kopieren". Sie können vertrauliche Informationen auch als "Vertraulich" klassifizieren und angeben, wie klassifizierte Informationen außerhalb und innerhalb des Unternehmens freigegeben werden können. Die Verschlüsselung auf Unternehmensebene ist einfach auf E-Mails und Dokumente anzuwenden, um Ihre Informationen privat zu halten. Sie können auch das Azure Information Protection-Client-Add-In für Office-Apps installieren. Weitere Informationen finden Sie unter [Einheitlicher Bezeichnungsclient für Azure Information Protection](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history). Installieren Sie für Vertraulichkeitsbezeichnungen **dieAzInfoProtection_UL.exe**.

Sie können diese Features im Security Compliance Center und &amp; im Intune Admin Center verwalten. Im Laufe der Zeit werden die vereinfachten Steuerelemente dem Microsoft 365 Admin Center hinzugefügt.
  
    
## <a name="faq"></a>Häufig gestellte Fragen

 ### <a name="are-these-security-features-available-in-all-markets"></a>Sind diese Sicherheitsfeatures in allen Märkten verfügbar?
  
Ja, diese Features sind in allen Märkten verfügbar, in denen Microsoft 365 Business Premium verkauft wird.
  
### <a name="how-do-i-find-the-security-amp-compliance-center"></a>Wie finde ich das Security &amp; Compliance Center?
  
1. Melden Sie sich mit Ihren Administratoranmeldeinformationen bei [Microsoft 365 Business Premium](https://portal.microsoft.com/) an. 
    
2. Suchen Sie im linken Navigations navig **nach Admin Center,** und erweitern Sie es. 
    
    ![Wählen Sie im linken Navigations navi im Microsoft 365 Admin Center Admin Center aus.](../media/fa4484f8-c637-45fd-a7bd-bdb3abfd6c03.png)
  
3. Wählen **Sie &amp; Sicherheitskonformität** aus, um zum Security &amp; Compliance Center zu wechseln.
