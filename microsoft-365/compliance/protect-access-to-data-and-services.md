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
description: Erfahren Sie, wie Sie den Benutzer- und Gerätezugriff auf Microsoft 365-Daten und -Dienste schützen und vor Datenverlust schützen.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9ff7bd2ff8b4b333eb30a6cc82797a8968941e0b
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051697"
---
# <a name="protect-user-and-device-access"></a>Schutz von Benutzer- und Gerätezugriff

Der Schutz des Zugriffs auf Ihre Microsoft 365-Daten und -Dienste ist entscheidend für die Verteidigung vor Cyberangriffen und den Schutz vor Datenverlust. Dieselben Schutzmaßnahmen können auch auf andere SaaS-Anwendungen in Ihrer Umgebung und sogar auf lokale Anwendungen angewendet werden, die mit dem Azure Active Directory-Anwendungsproxy veröffentlicht wurden.
  
## <a name="step-1-review-recommendations"></a>Schritt 1: Überprüfen von Empfehlungen

Empfohlene Funktionen zum Schutz von Identitäten und Geräten, die auf Office 365, andere SaaS-Dienste und lokale Anwendungen zugreifen, die mit dem Azure AD-Anwendungsproxy veröffentlicht werden.
  
[PDF](https://go.microsoft.com/fwlink/p/?linkid=841656) | [Visio](https://go.microsoft.com/fwlink/p/?linkid=841657) | [Weitere Sprachen](https://www.microsoft.com/download/details.aspx?id=55032)
  
## <a name="step-2-protect-administrator-accounts-and-access"></a>Schritt 2: Schützen von Administratorkonten und Zugriff
Die administrativen Konten, die Sie zum Verwalten Ihrer Microsoft 365-Umgebung verwenden, enthalten erhöhte Rechte. Dies sind wertvolle Ziele für Hacker und Cyberangriffe. 

Verwenden Sie zunächst nur Administratorkonten für die Verwaltung. Administratoren sollten über ein separates Benutzerkonto für die reguläre, nicht administrative Verwendung verfügen und ihr Administratorkonto nur verwenden, wenn dies erforderlich ist, um eine Aufgabe auszuführen, die mit ihrer Auftragsfunktion verknüpft ist.

Schützen Sie Ihre Administratorkonten mit mehrstufiger Authentifizierung und bedingten Zugriff. Weitere Informationen finden Sie unter [Schützen von Administratorkonten](../security/defender-365-security/identity-access-prerequisites.md#protecting-administrator-accounts). 

Konfigurieren Sie als Nächstes die Verwaltung des privilegierten Zugriffs in Office 365. Die Verwaltung des privilegierten Zugriffs ermöglicht eine präzise steuerbare Zugriffskontrolle über privilegierte Administratoraufgaben in Office 365. Sie kann Ihre Organisation vor Verstößen schützen, die vorhandene privilegierte Administratorkonten mit ständigem Zugriff auf vertrauliche Daten oder Zugriff auf kritische Konfigurationseinstellungen verwenden können.

- [Übersicht über die Verwaltung privilegierter Zugriffe](privileged-access-management-overview.md)
- [Konfigurieren von Privileged Access Management](privileged-access-management-configuration.md)

Eine weitere empfehlung ist die Verwendung von Arbeitsstationen, die speziell für administrative Arbeit konfiguriert sind. Dies sind dedizierte Geräte, die nur für Administrative Aufgaben verwendet werden. Weitere [Informationen finden Sie unter Schützen des privilegierten Zugriffs](/windows-server/identity/securing-privileged-access/securing-privileged-access).

Schließlich können Sie die Auswirkungen eines unbeabsichtigten Mangels an Administrativem Zugriff verringern, indem Sie zwei oder mehr Notfallzugriffskonten in Ihrem Mandanten erstellen. Weitere [Informationen finden Sie unter Verwalten von Notfallzugriffskonten in Azure AD](/azure/active-directory/users-groups-roles/directory-emergency-access). 

## <a name="step-3-configure-recommended-identity-and-device-access-policies"></a>Schritt 3: Konfigurieren empfohlener Identitäts- und Gerätezugriffsrichtlinien
Mehrstufige Authentifizierung (Multi-Factor Authentication, MFA) und Richtlinien für bedingten Zugriff sind leistungsstarke Tools zur Minderung von kompromittierten Konten und nicht autorisiertem Zugriff. Es wird empfohlen, eine Reihe von Richtlinien zu implementieren, die gemeinsam getestet wurden. Weitere Informationen, einschließlich bereitstellungsschritten, finden Sie unter [Identity and device access configurations](../security/defender-365-security/microsoft-365-policies-configurations.md).

 Diese Richtlinien implementieren die folgenden Funktionen:
- Mehrstufige Authentifizierung
- Bedingter Zugriff
- Intune-App-Schutz (App- und Datenschutz für Geräte)
- Intune-Gerätekompatibilität
- Azure AD Identity Protection

Für die Implementierung der Intune-Gerätekonformität ist die Geräteregistrierung erforderlich. Mit der Verwaltung von Geräten können Sie sicherstellen, dass sie fehlerfrei und kompatibel sind, bevor sie Zugriff auf Ressourcen in Ihrer Umgebung erhalten. Siehe [Registrieren von Geräten für die Verwaltung in Intune](/intune-classic/deploy-use/enroll-devices-in-microsoft-intune)

## <a name="step-4-configure-sharepoint-device-access-policies"></a>Schritt 4: Konfigurieren von SharePoint-Gerätezugriffsrichtlinien

Microsoft empfiehlt, Inhalte auf SharePoint-Websites mit vertraulichen und streng regulierten Inhalten mit Gerätezugriffssteuerelementen zu schützen. Weitere Informationen finden Sie unter [Richtlinienempfehlungen zum Sichern von SharePoint-Websites und -Dateien](../security/defender-365-security/sharepoint-file-access-policies.md).



