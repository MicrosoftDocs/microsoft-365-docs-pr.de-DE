---
title: Voraussetzungen für Microsoft Managed Desktop
description: Lizenzen, Azure-Konten, Authentifizierungseinstellungen und Microsoft 365-Einstellungen, die vor der Registrierung bei Microsoft Managed Desktop eingerichtet werden
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c298c0d07b73966fe3946f0e3f2706da5d2d30fc
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453897"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Voraussetzungen für Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In diesem Thema werden die Infrastrukturanforderungen beschrieben, die Sie erfüllen müssen, um den Erfolg mit Microsoft Managed Desktop sicherzustellen. 


Bereich | Erforderliche Details
--- | ---
Lizenzierung |Microsoft Managed Desktop erfordert die Microsoft 365 E3-Lizenz mit Microsoft Defender for Endpoint (oder entsprechenden), die Ihren Benutzern zugewiesen ist. Zwei Lizenzen für Azure Active Directory Premium 2 müssen im Mandanten verfügbar sein, benutzer benötigen diese Lizenz jedoch nicht. <br>Weitere Informationen zu den spezifischen Dienstplänen finden Sie [unter Weitere Informationen zu Lizenzen](#more-about-licenses) in diesem Thema.<br>Weitere Informationen zu verfügbaren Lizenzen finden Sie unter [Microsoft 365-Lizenzierung](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Konnektivität |  Alle Microsoft Managed Desktop-Geräte erfordern Konnektivität mit zahlreichen Microsoft-Dienstendpunkten aus dem Unternehmensnetzwerk.<br><br>Die vollständige Liste der erforderlichen IPs und URLs finden Sie unter [Netzwerkkonfiguration](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) muss entweder die Autoritätsquelle für alle Benutzerkonten sein, oder Benutzerkonten müssen mit der neuesten unterstützten Version von Azure AD Connect aus lokalem Active Directory synchronisiert werden.<br><br>[Enterprise State Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) muss für Microsoft Managed Desktop-Benutzer aktiviert sein.<br><br>Weitere Informationen finden Sie unter [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Weitere Informationen zu unterstützten Azure AD Connect-Versionen finden Sie unter [Azure AD Connect:Version Release History](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Authentifizierung |    Wenn Azure AD nicht die Quelle der primären Authentifizierung für Benutzerkonten ist, müssen Sie eine der folgenden Einstellungen in Azure AD Connect konfigurieren:<br>- Kennworthashsynchronisierung<br>- Pass-Through-Authentifizierung<br>– Ein externer Identitätsanbieter (einschließlich Windows Server ADFS und Nicht-Microsoft-IDPs), der für die Erfüllung der Azure AD-Integrationsanforderungen konfiguriert ist. Weitere Informationen [finden Sie in](https://www.microsoft.com/download/details.aspx?id=56843) den Richtlinien. <br><br>Beim Festlegen von Authentifizierungsoptionen mit Azure AD Connect wird auch ein Kennwortrückschreiben empfohlen. Weitere Informationen finden Sie unter [Kennwortrückschreiben](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Wenn ein externer Identitätsanbieter implementiert ist, müssen Sie die Lösung überprüfen:<br>– Erfüllt die Azure AD-Integrationsanforderungen<br>– Unterstützt bedingten Azure AD-Zugriff, wodurch die Microsoft Managed Desktop-Gerätekonformitätsrichtlinie konfiguriert werden kann<br>– Ermöglicht die Geräteregistrierung und -verwendung von Microsoft 365-Diensten oder -Features, die als Teil von Microsoft Managed Desktop erforderlich sind <br><br>Weitere Informationen zu Authentifizierungsoptionen mit Azure AD finden Sie unter [Azure AD Connect-Benutzer-Anmeldeoptionen](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Microsoft 365 | OneDrive for Business muss für Microsoft Managed Desktop-Benutzer aktiviert sein.<br><br>Obwohl die Registrierung bei Microsoft Managed Desktop nicht erforderlich ist, wird dringend empfohlen, die folgenden Dienste in die Cloud zu migrieren:<br>- E-Mail: Migrieren Sie zu cloudbasierten Postfächern, Exchange online oder konfigurieren Sie mit Exchange Online Hybrid mit Exchange 2013 oder höher, lokal.<br>- Dateien und Ordner: Migrieren sie zu OneDrive for Business oder SharePoint Online.<br>– Tools für die Onlinezusammenarbeit: Migrieren zu Teams.
Geräteverwaltung | Microsoft Managed Desktop-Geräte erfordern die Verwaltung mithilfe von Microsoft Intune. Intune muss als Autorität für die Verwaltung mobiler Geräte festgelegt werden.<br><br>Weitere Informationen finden Sie unter [Microsoft Intune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Datensicherung und -wiederherstellung |  Microsoft Managed Desktop erfordert, dass Dateien aus Schutz mit OneDrive for Business synchronisiert werden. Dateien, die nicht mit OneDrive for Business synchronisiert werden, werden von Microsoft Managed Desktop nicht garantiert und gehen möglicherweise während des Geräteaustauschs verloren oder unterstützen Anrufe, die eine Gerätezurücksetzung erfordern.<br><br>Obwohl nicht erforderlich, empfiehlt Microsoft Managed Desktop dringend die Migration von zugeordneten Netzwerklaufwerken zur geeigneten Cloudlösung. Weitere Informationen finden Sie unter [Prepare mapped drives for Microsoft Managed Desktop](mapped-drives.md)

Wenn Sie bereit sind, mit Microsoft Managed Desktop zu beginnen, wenden Sie sich an Ihren Microsoft Account Manager. 

## <a name="more-about-licenses"></a>Weitere Informationen zu Lizenzen

Microsoft Managed Desktop erfordert bestimmte Lizenzoptionen, um funktionieren zu können. Informationen zur Verwendung dieser Lizenzen finden Sie unter [Microsoft Managed Desktop-Technologien.](../intro/technologies.md)

> [!TIP]
> Um diese Lizenzoptionen bestimmten Benutzern zuzuordnen, wird empfohlen, das [gruppenbasierte](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) Lizenzierungsfeature von Azure Active Directory zu nutzen.

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
