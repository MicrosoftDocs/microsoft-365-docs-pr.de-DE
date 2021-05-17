---
title: Voraussetzungen für Microsoft Managed Desktop
description: Lizenzen, Azure-Konten, Authentifizierungseinstellungen und Microsoft 365, die vor der Registrierung bei der Registrierung eingerichtet Microsoft Managed Desktop
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e4469d8abcfa8308c64e2efa7f7dc4f0156e5718
ms.sourcegitcommit: b6763a8ab240fbdd56078a7c9452445d0c4b9545
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/22/2021
ms.locfileid: "51957527"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Voraussetzungen für Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In diesem Thema werden die Infrastrukturanforderungen beschrieben, die Sie erfüllen müssen, um den Erfolg mit Microsoft Managed Desktop. 


Bereich | Erforderliche Details
--- | ---
Lizenzierung |Microsoft Managed Desktop erfordert die Microsoft 365 E3 Microsoft Defender for Endpoint (oder gleichwertigen Lizenzen), die Ihren Benutzern zugewiesen sind.<br>Weitere Informationen zu den spezifischen Dienstplänen finden Sie [unter Weitere Informationen zu Lizenzen](#more-about-licenses) in diesem Thema.<br>Weitere Informationen zu verfügbaren Lizenzen finden Sie unter [Microsoft 365 Lizenzierung](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans).
Konnektivität |  Alle Microsoft Managed Desktop benötigen Konnektivität mit zahlreichen Microsoft-Dienstendpunkten aus dem Unternehmensnetzwerk.<br><br>Die vollständige Liste der erforderlichen IPs und URLs finden Sie unter [Netzwerkkonfiguration](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) muss entweder die Autoritätsquelle für alle Benutzerkonten sein, oder Benutzerkonten müssen aus lokalem Active Directory mithilfe der neuesten unterstützten Version von Azure AD Verbinden.<br><br>[Enterprise Statusroaming](/azure/active-directory/devices/enterprise-state-roaming-overview) muss für benutzer Microsoft Managed Desktop aktiviert sein.<br><br>Weitere Informationen finden Sie unter [Azure AD Verbinden](/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Weitere Informationen zu unterstützten Versionen von Azure AD Verbinden finden Sie unter [Azure AD Verbinden:Version Release History](/azure/active-directory/hybrid/reference-connect-version-history).
Authentifizierung |    Wenn Azure AD nicht die Quelle der primären Authentifizierung für Benutzerkonten ist, müssen Sie eine der folgenden Einstellungen in Azure AD Verbinden:<br>- Kennworthashsynchronisierung<br>- Pass-Through-Authentifizierung<br>– Ein externer Identitätsanbieter (einschließlich Windows Server ADFS und Nicht-Microsoft-IDPs), der für die Erfüllung der Azure AD-Integrationsanforderungen konfiguriert ist. Weitere Informationen [finden Sie in](https://www.microsoft.com/download/details.aspx?id=56843) den Richtlinien. <br><br>Wenn Sie Authentifizierungsoptionen mit Azure AD Verbinden, wird auch ein Kennwortrückschreiben empfohlen. Weitere Informationen finden Sie unter [Kennwortrückschreiben](/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Wenn ein externer Identitätsanbieter implementiert ist, müssen Sie die Lösung überprüfen:<br>– Erfüllt die Azure AD-Integrationsanforderungen<br>– Unterstützt bedingten Azure AD-Zugriff, wodurch Microsoft Managed Desktop Gerätekonformitätsrichtlinie konfiguriert werden kann<br>– Ermöglicht die Geräteregistrierung und -Microsoft 365 von Diensten oder Features, die als Teil der Microsoft Managed Desktop <br><br>Weitere Informationen zu Authentifizierungsoptionen mit Azure AD finden Sie unter [Azure AD Verbinden Benutzer-Anmeldeoptionen](/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Microsoft 365 | OneDrive for Business muss für benutzer Microsoft Managed Desktop aktiviert sein.<br><br>Obwohl es nicht erforderlich ist, sich bei Microsoft Managed Desktop zu registrieren, wird dringend empfohlen, die folgenden Dienste in die Cloud zu migrieren:<br>- E-Mail: Migrieren Sie zu cloudbasierten Postfächern, Exchange Online oder konfigurieren Sie mit Exchange Online Hybrid mit Exchange 2013 oder höher lokal.<br>- Dateien und Ordner: Migrieren Sie zu OneDrive for Business oder SharePoint Online.<br>– Tools für die Onlinezusammenarbeit: Migrieren zu Teams.
Geräteverwaltung | Microsoft Managed Desktop geräte erfordern die Verwaltung mithilfe Microsoft Intune. Intune muss als Autorität für die Verwaltung mobiler Geräte festgelegt werden.<br><br>Weitere Informationen finden Sie unter [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Datensicherung und -wiederherstellung |  Microsoft Managed Desktop erfordert, dass Dateien zum Schutz mit OneDrive for Business synchronisiert werden. Alle Dateien, die nicht mit OneDrive for Business synchronisiert werden, werden von Microsoft Managed Desktop nicht garantiert und gehen möglicherweise beim Geräteaustausch verloren oder unterstützen Anrufe, die eine Gerätezurücksetzung erfordern.<br><br>Obwohl nicht erforderlich, empfiehlt Microsoft Managed Desktop dringend die Migration von zugeordneten Netzwerklaufwerken zur geeigneten Cloudlösung. Weitere Informationen finden Sie unter [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md)

Wenn Sie bereit sind, mit dem Microsoft Managed Desktop zu beginnen, wenden Sie sich an Ihren Microsoft Account Manager. 

## <a name="more-about-licenses"></a>Weitere Informationen zu Lizenzen

Microsoft Managed Desktop erfordert bestimmte Lizenzoptionen, um zu funktionieren. Informationen [zur Verwendung dieser](../intro/technologies.md) Lizenzen finden Sie unter Microsoft Managed Desktop-Technologien.

> [!TIP]
> Um diese Lizenzoptionen bestimmten Benutzern zuzuordnen, wird empfohlen, das [gruppenbasierte](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Lizenzierungsfeature von Azure Active Directory.

- Azure Active Directory Premium P1
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender für Endpunkt
- Microsoft 365 Apps for Enterprise
- Microsoft Teams
- [SharePoint Online Plan 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online Plan 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Ihr Microsoft Account Manager hilft Ihnen, Ihre aktuellen Lizenzen und Dienstpläne zu überprüfen und den effizientesten Weg zu finden, um zusätzliche Lizenzen oder Dienstpläne zu erhalten, die Sie möglicherweise benötigen, und gleichzeitig Duplizierungen zu vermeiden.

## <a name="steps-to-get-ready"></a>Schritte für die ersten Schritte

1. Überprüfen [Sie Voraussetzungen für Microsoft Managed Desktop](prerequisites.md). (Dieser Artikel)
2. Verwenden [Sie Die Bereitschaftsbewertungstools](readiness-assessment-tool.md).
3. [Voraussetzungen für Gastkonten](guest-accounts.md)
4. [Netzwerkkonfiguration für Microsoft Managed Desktop](network.md)
5. [Vorbereiten von Zertifikaten und Netzwerkprofilen für Microsoft Managed Desktop](certs-wifi-lan.md)
6. [Vorbereiten des lokalen Ressourcenzugriffs für Microsoft Managed Desktop](authentication.md)
7. [Apps im Microsoft Managed Desktop](apps.md)
8. [Vorbereiten zugeordneter Laufwerke für Microsoft Managed Desktop](mapped-drives.md)
9. [Vorbereiten der Druckressourcen für Microsoft Managed Desktop](printing.md)
