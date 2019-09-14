---
title: Voraussetzungen für Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 6595b6496c8fb2e71542b6aae9f35e4f40c08aa4
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981716"
---
# <a name="prerequisites-for-microsoft-managed-desktop"></a>Voraussetzungen für Microsoft Managed Desktop

<!--This topic is the target for a "Learn more" link in the Admin Portal (aka.ms/prereq-azure); do not delete.-->
<!--from Prerequisites -->

In diesem Thema werden die Infrastrukturanforderungen beschrieben, die Sie erfüllen müssen, um den Erfolg mit Microsoft Managed Desktop sicherzustellen. 

Microsoft Kurzhilfe steht Ihnen zur Verfügung, um Sie bei der Erfüllung dieser Anforderungen zu unterstützen und Sie bei der Vorbereitung der Teilnahme an Microsoft Managed Desktop zu unterstützen Weitere Informationen finden Sie unter [Microsoft](https://fasttrack.microsoft.com/about)Kurzdaten. 

Bereich | Erforderliche Details
--- | ---
Lizenzierung |Microsoft Managed Desktop erfordert eine der folgenden Microsoft 365-Lizenzen (oder Entsprechungen):<br>-Microsoft 365 E5<br>-Microsoft 365 E3 mit dem Microsoft 365 E5-Sicherheits-Add-on<br><br>Ausführliche Informationen zu den spezifischen Dienstplänen und deren Rolle in Microsoft Managed Desktop finden Sie unter [Weitere Informationen zu Lizenzen](#more-about-licenses) in diesem Thema.<br>Weitere Informationen zu verfügbaren Lizenzen finden Sie unter [Microsoft 365 Licensing](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans).
Konnektivität |  Für alle Microsoft Managed Desktop-Geräte ist eine Verbindung mit zahlreichen Microsoft-Dienstendpunkten aus dem Unternehmensnetzwerk erforderlich.<br><br>Eine vollständige Liste der erforderlichen IPS und URLs finden Sie unter [Netzwerkkonfiguration](../get-ready/network.md). 
Azure Active Directory |    Azure Active Directory (Azure AD) muss entweder die Autoritäts Quelle für alle Benutzerkonten sein, oder Benutzerkonten müssen mit der neuesten unterstützten Version von Azure AD Connect von lokalen Active Directory synchronisiert werden.<br><br>Das [Enterprise-Status-Roaming](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-overview) muss für Microsoft Managed Desktop-Benutzer aktiviert sein.<br><br>Weitere Informationen finden Sie unter [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/hybrid/whatis-azure-ad-connect).<br><br>Weitere Informationen zu unterstützten Azure AD Connect-Versionen finden Sie unter [Azure AD Connect: Version Release History](https://docs.microsoft.com/azure/active-directory/hybrid/reference-connect-version-history).
Authentication |    Wenn Azure AD nicht die Autoritäts Quelle für Benutzerkonten ist, müssen Sie eine davon in Azure AD Connect konfigurieren:<br>-Kennworthash Synchronisierung<br>-Pass-Through-Authentifizierung<br>-Verbund mit ADFS<br><br>Beim Festlegen von Authentifizierungsoptionen mit Azure AD Connect wird auch das Kenn Wort Rückschreiben empfohlen. Weitere Informationen finden Sie unter [Kenn Wort Rück schreibe](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback). <br><br>Weitere Informationen zu Authentifizierungsoptionen mit Azure AD finden Sie unter [Azure AD Connect User Sign-in Options](https://docs.microsoft.com/azure/active-directory/connect/active-directory-aadconnect-user-signin).
Office 365 |    OneDrive für Unternehmen müssen für Microsoft Managed Desktop-Benutzer aktiviert sein.<br><br>Obwohl es nicht erforderlich ist, sich bei Microsoft Managed Desktop anzumelden, wird dringend empfohlen, die folgenden Dienste in die Cloud zu migrieren:<br>-E-Mail: Migrieren Sie zu cloudbasierten Postfächern, Exchange Online oder konfigurieren Sie mit Exchange Online Hybriden mit Exchange 2013 oder höher, lokal.<br>-Dateien und Ordner: Migrieren Sie zu OneDrive für Unternehmen oder SharePoint Online.<br>-Tools für die Online Zusammenarbeit: Migration zu Microsoft Teams.
Geräteverwaltung | Microsoft Managed Desktop-Geräte erfordern eine Verwaltung mit Microsoft InTune. InTune muss als Verwaltungsautorität für mobile Geräte festgelegt sein.<br><br>Weitere Informationen finden Sie unter [Microsoft InTune](https://www.microsoft.com/cloud-platform/microsoft-intune). 
Datensicherung und-Wiederherstellung | Microsoft Managed Desktop erfordert das Synchronisieren von Dateien mit OneDrive für Unternehmen Schutz. Alle Dateien, die nicht mit OneDrive für Unternehmen synchronisiert wurden, werden von Microsoft Managed Desktop nicht garantiert und gehen möglicherweise während des Geräteaustauschs verloren oder unterstützen Anrufe, die ein Zurücksetzen des Geräts erfordern.<br><br>Obwohl dies nicht erforderlich ist, empfiehlt Microsoft Managed Desktop dringend die Migration von zugeordneten Netzlaufwerken zur entsprechenden Cloud-Lösung. Weitere Informationen finden Sie unter [Prepare Mapped Drives for Microsoft Managed Desktop](mapped-drives.md)

Wenn Sie die ersten Schritte mit Microsoft Managed Desktop abgeschlossen haben, wenden Sie sich an Ihren Microsoft-Konto-Manager. 

## <a name="more-about-licenses"></a>Weitere Informationen zu Lizenzen

Microsoft Managed Desktop erfordert bestimmte Lizenzoptionen, um zu funktionieren. Diese Optionen stehen in einer Reihe verschiedener Lizenzpakete zur Verfügung, von denen einige möglicherweise bereits besitzen. Diese Tabelle zeigt, welche erforderlichen Optionen in welchen Lizenzen zur Verfügung stehen und wie Sie Ihre Rolle in Microsoft Managed Desktop zusammenfassen.

> [!TIP]
> Um diese Lizenzoptionen bestimmten Benutzern zuzuweisen, empfiehlt es sich, das [Gruppenbasierte Lizenzierungs Feature](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal) von Azure Active Directory zu nutzen.



|Lizenzoption |In *jedem* dieser Lizenzprodukte verfügbar |Verwendung von Microsoft Managed Desktop|
|-------------|-------------|-------------|
|Azure Active Directory Premium P1     |-Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5* -Sicherheits-Add-on<br>-Enterprise Mobility + Sicherheit E5<br>-Enterprise Mobility + Security E3<br>-Azure Active Directory Premium P1|  Ermöglicht den Zugriff auf Microsoft-Cloud-Dienste; ermöglicht Autopilot das Registrieren von Geräten      |
|Microsoft Intune | -Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5* -Sicherheits-Add-on<br>-Enterprise Mobility + Sicherheit E5<br>-Enterprise Mobility + Security E3<br>-Microsoft InTune  |  Erforderlich zum Registrieren von Geräten, Bereitstellen von Updates und Verwalten von Geräten       |
|Windows 10 Enterprise  |-Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5* -Sicherheits-Add-on<br>-Windows 10 Enterprise E3<br>-Windows 10 Enterprise E5 | Bereitstellen von Enterprise-Features von Windows 10       |
|Erweiterter Bedrohungsschutz von Microsoft Defender | -Microsoft 365 E5<br>-Microsoft 365 E3 + Microsoft 365 *E5* -Sicherheits-Add-on<br>-Windows 10 Enterprise E5<br>-Microsoft Defender Advanced Threat Protection   |  Bereitstellen von Erkennung, Überwachung, Warnungen und Reaktion auf Bedrohungen  |
|Office 365 ProPlus  |-Microsoft 365 E5<br>-Microsoft 365 E3<br>-Office 365 E5<br>-Office 365 E3| Aktiviert Office-und Produktivitäts-und Zusammenarbeitstools    |

> [!TIP]
> Ihr Microsoft-Konto Manager hilft Ihnen beim Überprüfen Ihrer aktuellen Lizenzen und Dienstpläne und sucht nach dem effizientesten Pfad, um zusätzliche Lizenzen oder Servicepläne zu erhalten, die Sie möglicherweise benötigen, und gleichzeitig die Duplizierung vermeiden.