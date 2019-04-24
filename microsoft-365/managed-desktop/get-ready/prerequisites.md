---
title: VoraussetZungen für Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 8d9c008af9531bc5b829d248665dc5b58ac6034b
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32277386"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>VoraussetZungen für Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Der Erfolg mit Microsoft Managed Desktop beginnt mit bekannten, dokumentierten und vereinbarten Anforderungen für die Infrastruktur des Kunden. Dieser Abschnitt enthält die folgenden Infastructure-Anforderungen. 

Microsoft-Kurzarbeits ist verfügbar, um Kunden bei der Erfüllung dieser Anforderungen zu unterstützen und Sie bei der Vorbereitung der Teilnahme an Microsoft Managed Desktop vorzubereiten. Weitere Informationen finden Sie unter [Microsoft](https://fasttrack.microsoft.com/about)-Kurzdaten. 

Bereich | Erforderliche Details
--- | ---
Lizenzierung | Jedem MMD-Benutzer muss eine der folgenden Lizenzoptionen zugewiesen sein:<br>-Microsoft 365 E5<br>-Microsoft 365 E3, Enterprise Mobility + Security E5 und Windows 10 Enterprise E5<br>-Office 365 E3, Enterprise Mobility + Security E5 und Windows 10 Enterprise E5<br><br>Vorhandene Enterprise Agreement-Kunden benötigen möglicherweise Anweisungen, um die Aktivierung von Windows 10 Enterprise-Abonnements im Azure AD-Mandanten zu aktivieren. Weitere Informationen finden Sie unter [Deploy Windows 10 Enterprise licenses](https://docs.microsoft.com/windows/deployment/deploy-enterprise-licenses#enabling-subscription-activation-with-an-existing-ea).<br><br>Produktlizenzen können mithilfe von Sicherheitsgruppen zugewiesen werden, indem die Azure AD-basierte Lizenzierung konfiguriert wird. Weitere Informationen finden Sie unter [Was ist die Gruppenbasierte Lizenzierung in Azure Active Directory](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).<br><br>Weitere Informationen zu den verfügbaren Lizenzen finden Sie unter [Microsoft 365 Licensing](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Konnektivität |  Alle von Microsoft verwalteten Desktop Geräte erfordern eine Verbindung mit zahlreichen Microsoft-Dienstendpunkten aus dem Unternehmensnetzwerk.<br><br>Eine vollständige Liste der erforderlichen IPs und URLs finden Sie unter [Netzwerkkonfiguration](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) muss entweder die Autoritäts Quelle für alle Benutzerkonten sein, oder Benutzerkonten müssen vom lokalen Active Directory mithilfe der neuesten unterstützten Version von Azure AD Connect synchronisiert werden.<br><br>Weitere Informationen zu Azure AD Connect finden Sie unter [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Weitere Informationen zu unterstützten Azure AD Connect-Versionen finden Sie unter [Azure AD Connect: Version Release History](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Authentifizierung |    Wenn Azure AD nicht die Autoritäts Quelle für Benutzerkonten ist, müssen Sie eine dieser in Azure AD Connect konfigurieren:<br>-Kennworthash Synchronisierung<br>-Passthrough-Authentifizierung<br>-Verbund mit ADFS<br><br>Wenn Sie Authentifizierungsoptionen mit Azure AD Connect festlegen, ist auch ein Kenn Wort Rückschreiben erforderlich. Weitere Informationen finden Sie unter [Kenn Wort Rück schreibe](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Weitere Informationen zu Authentifizierungsoptionen mit Azure AD finden Sie unter [Azure AD Connect-Benutzeranmelde Optionen](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    Obwohl es nicht erforderlich ist, sich bei Microsoft Managed Desktop anzumelden, wird dringend empfohlen, die folgenden Dienste in die Cloud zu migrieren:<br>-E-Mail-Migration zu Cloud-basierten Postfächern, Exchange Online oder mit Exchange Online-Hybrid mit Exchange 2013 oder höher, lokal.<br>-Dateien und Ordner – Migration zu OneDrive for Business/SharePoint Online.<br>-Tools für die Online Zusammenarbeit – Migration zu Teams.
Geräteverwaltung | Microsoft Managed Desktop-Geräte erfordern eine Verwaltung mit Microsoft InTune. InTune muss als Verwaltungsautorität für mobile Geräte festgelegt werden.<br><br>Weitere Informationen finden Sie unter [Microsoft InTune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Datensicherung und-Wiederherstellung | Microsoft Managed Desktop erfordert, dass Dateien mit OneDrive for Business zum Schutz synchronisiert werden. Alle Dateien, die nicht mit OneDrive for Business synchronisiert wurden, werden von Microsoft Managed Desktop nicht garantiert und können während des Geräteaustauschs verloren gehen oder Anrufe unterstützen, die ein Zurücksetzen des Geräts erfordern.<br><br>Obwohl dies nicht erforderlich ist, empfiehlt Microsoft Managed Desktop dringend die Migration von zugeordneten Netzlaufwerken zur entsprechenden Cloud-Lösung.  

Wenn Sie mit Microsoft Managed Desktop beginnen möchten, wenden Sie sich an Ihren Microsoft-Konto Manager. 
