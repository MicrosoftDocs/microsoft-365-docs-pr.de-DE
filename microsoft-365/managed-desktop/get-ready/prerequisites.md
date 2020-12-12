---
title: Voraussetzungen für Microsoft Managed Desktop
description: Lizenzen, Azure-Konten, Authentifizierungseinstellungen und Einstellungen von Microsoft 365, die vor der Registrierung in Microsoft Managed Desktop eingerichtet werden müssen
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 79ae949d9624021121492edb811a4ea5bfcc729a
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659140"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Voraussetzungen für Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In diesem Thema werden die Infrastrukturanforderungen beschrieben, die Sie erfüllen müssen, um den Erfolg mit Microsoft Managed Desktop sicherzustellen. 


Bereich | Erforderliche Details
--- | ---
Lizenzierung |Für Microsoft Managed Desktop ist die Microsoft 365 E3-Lizenz mit Microsoft Defender für Endpoint und Azure Active Directory Premium 2 (oder Entsprechungen) erforderlich.<br>Ausführliche Informationen zu den spezifischen Dienstplänen finden Sie unter [Weitere Informationen zu Lizenzen](#more-about-licenses) in diesem Thema.<br>Weitere Informationen zu verfügbaren Lizenzen finden Sie unter [Microsoft 365 Licensing](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Konnektivität |  Für alle Microsoft Managed Desktop-Geräte ist eine Verbindung mit zahlreichen Microsoft-Dienstendpunkten aus dem Unternehmensnetzwerk erforderlich.<br><br>Eine vollständige Liste der erforderlichen IPS und URLs finden Sie unter [Netzwerkkonfiguration](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) muss entweder die Autoritäts Quelle für alle Benutzerkonten sein, oder Benutzerkonten müssen mit der neuesten unterstützten Version von Azure AD Connect von lokalen Active Directory synchronisiert werden.<br><br>Das [Enterprise-Status-Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) muss für Microsoft Managed Desktop-Benutzer aktiviert sein.<br><br>Weitere Informationen finden Sie unter [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Weitere Informationen zu unterstützten Azure AD Connect-Versionen finden Sie unter [Azure AD Connect: Version Release History](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Authentifizierung |    Wenn Azure AD nicht die Quelle der primären Authentifizierung für Benutzerkonten ist, müssen Sie eine dieser in Azure AD Connect konfigurieren:<br>-Kennworthash Synchronisierung<br>-Pass-Through-Authentifizierung<br>– Ein externer Identitätsanbieter (einschließlich Windows Server ADFS und nicht-Microsoft-Vertriebenen), der für Azure AD Integrationsanforderungen konfiguriert ist. Weitere Informationen finden Sie in den [Richtlinien](https://www.microsoft.com/download/details.aspx?id=56843) . <br><br>Beim Festlegen von Authentifizierungsoptionen mit Azure AD Connect wird auch das Kenn Wort Rückschreiben empfohlen. Weitere Informationen finden Sie unter [Kenn Wort Rück schreibe](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Wenn ein externer Identitätsanbieter implementiert ist, müssen Sie die Lösung überprüfen:<br>-Erfüllt Azure AD Integrationsanforderungen<br>-Unterstützt Azure AD bedingten Zugriff, sodass die Microsoft Managed Desktop-Geräte Kompatibilitäts Richtlinie konfiguriert werden kann.<br>-Aktiviert die Geräteregistrierung und die Verwendung von Microsoft 365-Diensten oder-Features, die als Teil von Microsoft Managed Desktop erforderlich sind. <br><br>Weitere Informationen zu Authentifizierungsoptionen mit Azure AD finden Sie unter [Azure AD Connect User Sign-in Options](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Microsoft 365 | OneDrive für Unternehmen müssen für Microsoft Managed Desktop-Benutzer aktiviert sein.<br><br>Obwohl es nicht erforderlich ist, sich bei Microsoft Managed Desktop anzumelden, wird dringend empfohlen, die folgenden Dienste in die Cloud zu migrieren:<br>-E-Mail: Migrieren Sie zu cloudbasierten Postfächern, Exchange Online oder konfigurieren Sie mit Exchange Online Hybriden mit Exchange 2013 oder höher, lokal.<br>-Dateien und Ordner: Migrieren Sie zu OneDrive für Unternehmen oder SharePoint Online.<br>-Tools für die Online Zusammenarbeit: Migration zu Microsoft Teams.
Geräteverwaltung | Microsoft Managed Desktop-Geräte erfordern eine Verwaltung mit Microsoft InTune. InTune muss als Verwaltungsautorität für mobile Geräte festgelegt sein.<br><br>Weitere Informationen finden Sie unter [Microsoft InTune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Datensicherung und-Wiederherstellung |  Microsoft Managed Desktop erfordert das Synchronisieren von Dateien mit OneDrive für Unternehmen Schutz. Alle Dateien, die nicht mit OneDrive für Unternehmen synchronisiert wurden, werden von Microsoft Managed Desktop nicht garantiert und gehen möglicherweise während des Geräteaustauschs verloren oder unterstützen Anrufe, die ein Zurücksetzen des Geräts erfordern.<br><br>Obwohl dies nicht erforderlich ist, empfiehlt Microsoft Managed Desktop dringend die Migration von zugeordneten Netzlaufwerken zur entsprechenden Cloud-Lösung. Weitere Informationen finden Sie unter [Prepare Mapped Drives for Microsoft Managed Desktop](mapped-drives.md)

Wenn Sie die ersten Schritte mit Microsoft Managed Desktop abgeschlossen haben, wenden Sie sich an Ihren Microsoft-Konto-Manager. 

## <a name="more-about-licenses"></a>Weitere Informationen zu Lizenzen

Microsoft Managed Desktop erfordert bestimmte Lizenzoptionen, um zu funktionieren. Informationen dazu, wie diese Lizenzen verwendet werden, finden Sie unter [Microsoft Managed Desktop Technologies](../intro/technologies.md) .

> [!TIP]
> Um diese Lizenzoptionen bestimmten Benutzern zuzuweisen, empfiehlt es sich, das [Gruppenbasierte Lizenzierungs Feature](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) von Azure Active Directory zu nutzen.

- Azure Active Directory Premium P2
- Microsoft Intune 
- Windows 10 Enterprise  
- Microsoft Defender für Endpunkt
- Microsoft 365 Apps for Enterprise
- Microsoft Teams
- [SharePoint Online Plan 2](https://www.microsoft.com/microsoft-365/sharepoint/compare-sharepoint-plans)
- [Exchange Online Plan 2](https://www.microsoft.com/microsoft-365/exchange/compare-microsoft-exchange-online-plans) 


> [!TIP]
> Ihr Microsoft-Konto Manager hilft Ihnen beim Überprüfen Ihrer aktuellen Lizenzen und Dienstpläne und sucht nach dem effizientesten Pfad, um zusätzliche Lizenzen oder Servicepläne zu erhalten, die Sie möglicherweise benötigen, und gleichzeitig die Duplizierung vermeiden.
