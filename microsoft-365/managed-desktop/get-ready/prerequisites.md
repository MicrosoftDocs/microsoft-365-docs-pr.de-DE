---
title: Voraussetzungen für Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 11/1/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 19bd7c553840b0de51f7b26a8f1206a9c5d7b3af
ms.sourcegitcommit: b27650d1388ca136f85fcc662fe3ba069e9ee895
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/02/2019
ms.locfileid: "33560054"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Voraussetzungen für Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

Der Erfolg mit Microsoft Managed Desktop beginnt mit bekannten, dokumentierten und vereinbarten Anforderungen für die Infrastruktur des Kunden. Dieser Abschnitt enthält die folgenden Infastructure-Anforderungen. 

Microsoft-Kurzarbeits ist verfügbar, um Kunden bei der Erfüllung dieser Anforderungen zu unterstützen und Sie bei der Vorbereitung der Teilnahme an Microsoft Managed Desktop vorzubereiten. Weitere Informationen finden Sie unter [Microsoft](https://fasttrack.microsoft.com/about)-Kurzdaten. 

Bereich | Erforderliche Details
--- | ---
Lizenzierung |Microsoft Managed Desktop erfordert die folgenden Microsoft 365-Lizenzen (oder Äquivalenzen):<br>-Microsoft 365 E5<br>-Microsoft 365 E3 + Sicherheit E5<br><br>Weitere Informationen zu den verfügbaren Lizenzen finden Sie unter [Microsoft 365 Licensing](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Konnektivität |  Alle von Microsoft verwalteten Desktop Geräte erfordern eine Verbindung mit zahlreichen Microsoft-Dienstendpunkten aus dem Unternehmensnetzwerk.<br><br>Eine vollständige Liste der erforderlichen IPS und URLs finden Sie unter [Netzwerkkonfiguration](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) muss entweder die Autoritäts Quelle für alle Benutzerkonten sein, oder Benutzerkonten müssen vom lokalen Active Directory mithilfe der neuesten unterstützten Version von Azure AD Connect synchronisiert werden.<br><br>Weitere Informationen zu Azure AD Connect finden Sie unter [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Weitere Informationen zu unterstützten Azure AD Connect-Versionen finden Sie unter [Azure AD Connect: Version Release History](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Authentication |    Wenn Azure AD nicht die Autoritäts Quelle für Benutzerkonten ist, müssen Sie eine dieser in Azure AD Connect konfigurieren:<br>-Kennworthash Synchronisierung<br>-Passthrough-Authentifizierung<br>-Verbund mit ADFS<br><br>Wenn Sie Authentifizierungsoptionen mit Azure AD Connect festlegen, ist auch ein Kenn Wort Rückschreiben erforderlich. Weitere Informationen finden Sie unter [Kenn Wort Rück schreibe](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Weitere Informationen zu Authentifizierungsoptionen mit Azure AD finden Sie unter [Azure AD Connect-Benutzeranmelde Optionen](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    Obwohl es nicht erforderlich ist, sich bei Microsoft Managed Desktop anzumelden, wird dringend empfohlen, die folgenden Dienste in die Cloud zu migrieren:<br>-E-Mail-Migration zu Cloud-basierten Postfächern, Exchange Online oder mit Exchange Online-Hybrid mit Exchange 2013 oder höher, lokal.<br>-Dateien und Ordner – Migration zu OneDrive for Business/SharePoint Online.<br>-Tools für die Online Zusammenarbeit – Migration zu Teams.
Geräteverwaltung | Microsoft Managed Desktop-Geräte erfordern eine Verwaltung mit Microsoft InTune. InTune muss als Verwaltungsautorität für mobile Geräte festgelegt werden.<br><br>Weitere Informationen finden Sie unter [Microsoft InTune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Datensicherung und-Wiederherstellung | Microsoft Managed Desktop erfordert, dass Dateien mit OneDrive for Business zum Schutz synchronisiert werden. Alle Dateien, die nicht mit OneDrive for Business synchronisiert wurden, werden von Microsoft Managed Desktop nicht garantiert und können während des Geräteaustauschs verloren gehen oder Anrufe unterstützen, die ein Zurücksetzen des Geräts erfordern.<br><br>Obwohl dies nicht erforderlich ist, empfiehlt Microsoft Managed Desktop dringend die Migration von zugeordneten Netzlaufwerken zur entsprechenden Cloud-Lösung.  

Wenn Sie mit Microsoft Managed Desktop beginnen möchten, wenden Sie sich an Ihren Microsoft-Konto Manager. 
