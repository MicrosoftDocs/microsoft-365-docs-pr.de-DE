---
title: Voraussetzungen für Microsoft Managed Desktop
description: Lizenzen, Azure-Konten, Authentifizierungseinstellungen und Microsoft 365 Einstellungen, die vor der Registrierung in Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: c2b0cc6db8ade434e94db92ae225140f7b1aec69
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289583"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Voraussetzungen für Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In diesem Thema werden die Infrastrukturanforderungen beschrieben, die Sie erfüllen müssen, um den Erfolg mit Microsoft Managed Desktop sicherzustellen.


Bereich | Erforderliche Details
--- | ---
Lizenzierung |Microsoft Managed Desktop erfordert die Microsoft 365 E3-Lizenz mit Microsoft Defender für Endpunkt (oder Äquivalenten), die Ihren Benutzern zugewiesen ist.<br>Ausführliche Informationen zu den spezifischen Serviceplänen finden Sie unter ["Weitere Informationen zu Lizenzen"](#more-about-licenses) in diesem Thema.<br>Weitere Informationen zu verfügbaren Lizenzen finden Sie unter [Microsoft 365 Lizenzierung.](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans)
Konnektivität | Alle Microsoft Managed Desktop Geräte erfordern eine Verbindung mit zahlreichen Microsoft-Dienstendpunkten aus dem Unternehmensnetzwerk.<br><br>Eine vollständige Liste der erforderlichen IPs und URLs finden Sie unter ["Netzwerkkonfiguration".](../get-ready/network.md) 
Azure Active Directory | Azure Active Directory (Azure AD) muss entweder die Autoritätsquelle für alle Benutzerkonten sein, oder Benutzerkonten müssen aus dem lokalen Active Directory mithilfe der neuesten unterstützten Version von Azure AD Verbinden synchronisiert werden.<br><br>Weitere Informationen finden Sie unter [Azure AD Verbinden.](/azure/active-directory/hybrid/whatis-azure-ad-connect)<br><br>Weitere Informationen zu unterstützten Versionen von Azure AD Verbinden finden Sie unter [Azure AD Verbinden:Versionsveröffentlichungsverlauf.](/azure/active-directory/hybrid/reference-connect-version-history)
Authentifizierung | Wenn Azure AD nicht die Quelle der primären Authentifizierung für Benutzerkonten ist, müssen Sie eine dieser Konten in Azure AD Verbinden konfigurieren:<br>- Kennworthashsynchronisierung<br>– Pass-Through-Authentifizierung<br>– Ein externer Identitätsanbieter (einschließlich Windows Server-ADFS und Nicht-Microsoft-IDPs), der zur Erfüllung der Azure AD-Integrationsanforderungen konfiguriert ist. Weitere Informationen finden Sie in den [Richtlinien.](https://www.microsoft.com/download/details.aspx?id=56843) <br><br>Beim Festlegen von Authentifizierungsoptionen mit Azure AD Verbinden wird auch das Kennwortrückschreiben empfohlen. Weitere Informationen finden Sie unter [Kennwortrückschreiben.](/azure/active-directory/authentication/howto-sspr-writeback) <br><br>Wenn ein externer Identitätsanbieter implementiert ist, müssen Sie die Lösung überprüfen:<br>– Erfüllt die Azure AD-Integrationsanforderungen<br>– Unterstützt bedingten Azure AD-Zugriff, mit dem die richtlinie zur Gerätekompatibilität Microsoft Managed Desktop konfiguriert werden kann<br>– Ermöglicht die Geräteregistrierung und Die Verwendung von Microsoft 365 Diensten oder Features, die als Teil der Microsoft Managed Desktop <br><br>Weitere Informationen zu Authentifizierungsoptionen mit Azure AD finden Sie unter [Azure AD Verbinden Benutzeranmeldeoptionen.](/azure/active-directory/connect/active-directory-aadconnect-user-signin)
Microsoft 365 | OneDrive for Business muss für Microsoft Managed Desktop Benutzer aktiviert sein.<br><br>Obwohl es nicht erforderlich ist, sich bei Microsoft Managed Desktop zu registrieren, wird dringend empfohlen, die folgenden Dienste in die Cloud zu migrieren:<br>– E-Mail: Migrieren Sie zu cloudbasierten Postfächern, Exchange online, oder konfigurieren Sie sie mit Exchange Online Hybridbereitstellung mit Exchange 2013 oder höher lokal.<br>– Dateien und Ordner: Migrieren sie zu OneDrive for Business oder SharePoint Online.<br>– Tools für die Onlinezusammenarbeit: Migrieren zu Teams.
Geräteverwaltung | Microsoft Managed Desktop Geräte müssen mithilfe von Microsoft Intune verwaltet werden. Intune muss als Autorität für die Verwaltung mobiler Geräte festgelegt werden.<br><br>Weitere Informationen finden Sie unter [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune).
Datensicherung und -wiederherstellung | Microsoft Managed Desktop müssen Dateien zum Schutz mit OneDrive for Business synchronisiert werden. Alle Dateien, die nicht mit OneDrive for Business synchronisiert wurden, werden von Microsoft Managed Desktop nicht garantiert und gehen möglicherweise beim Austausch von Geräten oder bei Supportanrufen verloren, die eine Gerätezurücksetzung erfordern.<br><br>Obwohl dies nicht erforderlich ist, empfiehlt Microsoft Managed Desktop dringend die Migration von zugeordneten Netzwerklaufwerken zur entsprechenden Cloudlösung. Weitere Informationen finden Sie unter [Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop](mapped-drives.md)

Wenn Sie bereit sind, mit Microsoft Managed Desktop zu beginnen, wenden Sie sich an Ihren Microsoft-Konto-Manager. 

## <a name="more-about-licenses"></a>Weitere Informationen zu Lizenzen

Microsoft Managed Desktop erfordert bestimmte Lizenzoptionen, um funktionieren zu können. Informationen zur Verwendung dieser Lizenzen finden Sie [unter Microsoft Managed Desktop Technologien.](../intro/technologies.md)

> [!TIP]
> Um diese Lizenzoptionen bestimmten Benutzern zuzuweisen, empfehlen wir, die [gruppenbasierte Lizenzierungsfunktion](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) von Azure Active Directory zu nutzen.

- Azure Active Directory Premium P1
- Microsoft Intune
- Windows 10 Enterprise  
- Microsoft Defender für Endpunkt
- Microsoft 365 Apps for Enterprise
- Microsoft Teams
- [SharePoint Online Plan 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online Plan 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans)

> [!TIP]
> Ihr Microsoft Account Manager hilft Ihnen, Ihre aktuellen Lizenzen und Servicepläne zu überprüfen und den effizientesten Pfad zu finden, um zusätzliche Lizenzen oder Servicepläne zu erhalten, die Sie möglicherweise benötigen, während Duplizierung vermieden wird.

## <a name="steps-to-get-ready"></a>Schritte zum Vorbereiten

1. Überprüfen Sie [die Voraussetzungen für Microsoft Managed Desktop.](prerequisites.md) (Dieser Artikel)
2. Verwenden Sie [Bereitschaftsbewertungstools.](readiness-assessment-tool.md)
3. [Voraussetzungen für Gastkonten](guest-accounts.md)
4. [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md)
5. [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop](authentication.md)
7. [Apps im Microsoft Managed Desktop](apps.md)
8. [Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop](mapped-drives.md)
9. [Vorbereiten der Druckressourcen für Microsoft Managed Desktop](printing.md)
