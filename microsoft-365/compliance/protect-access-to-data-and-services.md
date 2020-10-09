---
title: Schutz von Benutzer- und Gerätezugriff
f1.keywords:
- NOCSH
ms.author: bcarter
author: brendacarter
manager: laurawi
ms.date: 4/17/2018
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a6ef28a4-2447-4b43-aae2-f5af6d53c68e
description: Hier erfahren Sie, wie Sie Benutzer-und Geräte Zugriff auf Microsoft 365-Daten und-Dienste schützen und Datenverlust abwehren.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 64baa2c9e49a9b24841ec50db3e5592ba3d7d55d
ms.sourcegitcommit: cd17328baa58448214487e3e68c37590ab9fd08d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48399024"
---
# <a name="protect-user-and-device-access"></a>Schutz von Benutzer- und Gerätezugriff

Der Schutz des Zugriffs auf Ihre Microsoft 365-Daten und-Dienste ist für die Verteidigung gegen Cyberangriffe und den Schutz vor Datenverlusten entscheidend. Derselbe Schutz kann auf andere SaaS-Anwendungen in Ihrer Umgebung und sogar auf lokale Anwendungen angewendet werden, die mit Azure Active Directory Application Proxy veröffentlicht werden.
  
## <a name="step-1-review-recommendations"></a>Schritt 1: Überprüfen der Empfehlungen

Empfohlene Funktionen zum Schutz von Identitäten und Geräten, die auf Office 365, andere SaaS-Dienste und lokale Anwendungen zugreifen, die mit dem Azure AD-Anwendungsproxy veröffentlicht werden.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Schritt 2: Schützen von Administratorkonten und Zugriff
Die Administratorkonten, die Sie zum Verwalten Ihrer Microsoft 365-Umgebung verwenden, umfassen erweiterte Berechtigungen. Dies sind wertvolle Ziele für Hacker und cyberattackers. 

Verwenden Sie zunächst Administratorkonten nur für die Verwaltung. Administratoren sollten über ein separates Benutzerkonto für reguläre, nicht administrative Zwecke verfügen und bei Bedarf nur Ihr Administratorkonto verwenden, um eine Aufgabe abzuschließen, die ihrer Auftragsfunktion zugeordnet ist.

Schützen Sie Ihre Administratorkonten mit mehrstufiger Authentifizierung und bedingtem Zugriff. Weitere Informationen finden Sie unter [Protecting Administrator Accounts](https://docs.microsoft.com/microsoft-365/enterprise/identity-access-prerequisites#protecting-administrator-accounts). 

Konfigurieren Sie als nächstes die privilegierte Zugriffsverwaltung in Office 365. Die Verwaltung des privilegierten Zugriffs ermöglicht eine präzise steuerbare Zugriffskontrolle über privilegierte Administratoraufgaben in Office 365. Damit können Sie Ihre Organisation vor Verstößen schützen, die vorhandene privilegierte Administratorkonten mit dem ständigen Zugriff auf vertrauliche Daten oder den Zugriff auf wichtige Konfigurationseinstellungen verwenden können.

- [Übersicht über die Verwaltung privilegierter Zugriffsrechte](privileged-access-management-overview.md)
- [Konfigurieren von Privileged Access Management](privileged-access-management-configuration.md)

Eine weitere wichtige Empfehlung ist die Verwendung von Workstations, die speziell für administrative Arbeiten konfiguriert sind. Hierbei handelt es sich um dedizierte Geräte, die nur für administrative Aufgaben verwendet werden. Siehe [Sichern von privilegiertem Zugriff](https://docs.microsoft.com/windows-server/identity/securing-privileged-access/securing-privileged-access).

Schließlich können Sie die Auswirkungen von versehentlichem Mangel an administrativem Zugriff verringern, indem Sie zwei oder mehr Notfall Zugriffskonten in Ihrem Mandanten erstellen. Weitere Informationen finden Sie unter [Verwalten von Notfall Zugriffskonten in Azure AD](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-emergency-access). 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Schritt 3: Konfigurieren der empfohlenen Richtlinien für Identitäts-und Geräte Zugriff
Mehrstufige Authentifizierung (MFA) und Richtlinien für bedingten Zugriff sind leistungsstarke Tools zur Minderung von kompromittierten Konten und nicht autorisiertem Zugriff. Es wird empfohlen, eine Reihe von Richtlinien zu implementieren, die gemeinsam getestet wurden. Weitere Informationen, einschließlich Bereitstellungsschritten, finden Sie unter [Identity and Device Access Configurations](../security/office-365-security/microsoft-365-policies-configurations.md).

 Diese Richtlinien implementieren die folgenden Funktionen:
- Mult-Factor-Authentifizierung
- Bedingter Zugriff
- InTune-App-Schutz (app und Datenschutz für Geräte)
- Intune-Gerätekompatibilität
- Azure AD Identity Protection

Die Implementierung der InTune-Gerätekompatibilität erfordert die Geräteregistrierung. Durch die Verwaltung von Geräten können Sie sicherstellen, dass Sie ordnungsgemäß und kompatibel sind, bevor Sie Ihnen den Zugriff auf Ressourcen in Ihrer Umgebung ermöglichen. Siehe [Registrieren von Geräten für die Verwaltung in InTune](https://docs.microsoft.com/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Schritt 4: Konfigurieren von SharePoint-Gerätezugriffs Richtlinien

Microsoft empfiehlt, Inhalte auf SharePoint-Websites mit vertraulichen und streng reglementierten Inhalten mit Gerätezugriffs Steuerelementen zu schützen. Weitere Informationen finden Sie unter [Richtlinien Empfehlungen für das Sichern von SharePoint-Websites und-Dateien](../security/office-365-security/sharepoint-file-access-policies.md).



    

