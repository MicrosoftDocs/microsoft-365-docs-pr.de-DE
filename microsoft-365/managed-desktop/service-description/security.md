---
title: Sicherheitstechnologien in Microsoft Managed Desktop
description: Technologien für Gerätesicherheit, Identitäts- und Zugriffsverwaltung, Netzwerksicherheit und Informationssicherheit
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5076ddca6053adc7cebb9599c8d82a42c7ab5a63
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840913"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Sicherheitstechnologien in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop verwendet mehrere Microsoft-Technologien, um verwaltete Geräte und Daten zu schützen. Darüber hinaus werden im Microsoft Managed Desktop Security Operations Center [verschiedene](security-operations.md) Prozesse in Verbindung mit diesen Technologien verwendet.

Insbesondere gilt: 

- [Gerätesicherheit –](#device-security) Sicherheit und Schutz auf Microsoft Managed Desktop-Geräten
- [Identitäts- und Zugriffsverwaltung](#identity-and-access-management) – Verwalten der sicheren Verwendung von Geräten über Azure Active Directory Identity Services
- [Netzwerksicherheit –](#network-security) EMPFOHLENE Lösung und Einstellungen für VPN-Informationen und Microsoft Managed Desktop
- [Informationssicherheit –](#information-security) optionale verfügbare Dienste zum weiteren Schutz vertraulicher Informationen 

Informationen zu Datenspeicherung, Nutzung und Sicherheitspraktiken, die von Microsoft Managed Desktop verwendet werden, finden Sie in unserem Whitepaper unter [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Gerätesicherheit

Microsoft Managed Desktop stellt sicher, dass alle verwalteten Geräte gesichert und geschützt sind, und erkennt Bedrohungen so früh wie möglich mithilfe der folgenden Dienste:

Dienst | Beschreibung
--- | ---
Antivirus | Microsoft Defender AV ist installiert und konfiguriert<br>Microsoft Defender -AV-Definitionen sind auf dem neuesten Stand
Vollständige Volumeverschlüsselung |    Windows BitLocker ist die Volumeverschlüsselungslösung für Microsoft Managed Desktop-Geräte.<br><br>Sobald eine Organisation in den Dienst integriert ist, werden Geräte mit Windows BitLocker mit integriertem Trust Platform Module (TPM) verschlüsselt, um nicht autorisierten Zugriff auf lokale Daten zu verhindern, wenn sich das Gerät im Ruhezustand befindet oder deaktiviert ist. 
Überwachung |    Microsoft Defender for Endpoint wird für die Überwachung von Sicherheitsbedrohungen auf allen Microsoft Managed Desktop-Geräten verwendet. Mit Defender for Endpoint können Unternehmenskunden erweiterte Bedrohungen in ihrem Unternehmensnetzwerk erkennen, untersuchen und darauf reagieren. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Betriebssystemupdates |  Microsoft Managed Desktop-Geräte werden immer mit den neuesten Sicherheitsupdates gesichert.
Konfiguration sicherer Geräte |   Microsoft Managed Desktop implementiert die Microsoft Security Baseline. Weitere Informationen finden Sie unter [Windows-Sicherheitsgrundwerte.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Identitäts- und Zugriffsverwaltung

Identitäts- und Zugriffsverwaltung schützt Unternehmensressourcen und unternehmenskritische Daten. Microsoft Managed Desktop konfiguriert Geräte, um die sichere Verwendung mit verwalteten Azure Active Directory (Azure AD)-Identitäten sicherzustellen. Es liegt in der Verantwortung des Kunden, genaue Informationen in ihrem Azure AD-Mandanten zu verwalten. 

Dienst | Beschreibung
--- | ---
Biometrische Authentifizierung |  Windows Hello ermöglicht Benutzern die Anmeldung mit ihrem Gesicht oder einer PIN, wodurch Kennwörter schwieriger zu vergessen oder zu stehlen sind. Kunden sind für die Implementierung der erforderlichen Voraussetzungen für ihr lokales Active Directory für die Verwendung dieses Diensts in einer Hybridkonfiguration verantwortlich. Weitere Informationen finden Sie unter [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Standardbenutzerberechtigung |  Um das System zu schützen und sicherer zu machen, werden dem Benutzer Standardbenutzerberechtigungen zugewiesen. Diese Berechtigung wird als Teil der Windows Autopilot Out-of-Box-Erfahrung zugewiesen.



## <a name="network-security"></a>Netzwerksicherheit

Kunden sind für die Netzwerksicherheit verantwortlich. 

Dienst | Beschreibung
--- | ---
VPN | Kunden besitzen ihre VPN-Infrastruktur, um sicherzustellen, dass begrenzte Unternehmensressourcen außerhalb des Intranets verfügbar gemacht werden können.<br><br>Mindestanforderung: Microsoft Managed Desktop erfordert eine Windows 10-kompatible und unterstützte VPN-Lösung. Wenn Ihre Organisation eine VPN-Lösung benötigt, muss sie Windows 10 unterstützen und über Intune verpackt und bereitgestellt werden können. Weitere Informationen erhalten Sie von Ihrem Softwareherausgeber.<br><br>Empfehlung:<br>- Microsoft empfiehlt eine moderne VPN-Lösung, die einfach über Intune bereitgestellt werden kann, um VPN-Profile zu pushen. Dieser Ansatz bietet eine nahtlose, nahtlose, zuverlässige und sichere Möglichkeit für den Zugriff auf das Unternehmensnetzwerk. Weitere Informationen finden Sie [unter [VPN-Einstellungen in Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>– Thick-VPN-Clients oder ältere VPN-Clients werden von Microsoft bei der Verwendung von Microsoft Managed Desktop nicht empfohlen, da dies Auswirkungen auf die Benutzerumgebung haben kann.<br>- Microsoft empfiehlt, dass der ausgehende Webdatenverkehr direkt ins Internet geht, ohne das VPN zu verwenden, um Leistungsprobleme zu vermeiden.<br>- Im Idealfall empfiehlt Microsoft die Verwendung von Azure Active Directory-App-Proxy anstelle eines VPN.


## <a name="information-security"></a>Informationssicherheit

Sie können diese optionalen Dienste konfigurieren, um hochwertige Unternehmensressourcen zu schützen. 

Dienst | Beschreibung
--- | ---
Datenwiederherstellung  | Informationen, die in Schlüsselordnern auf dem Gerät gespeichert sind, werden in OneDrive for Business gesichert. Microsoft Managed Desktop ist nicht für Daten verantwortlich, die nicht mit OneDrive for Business synchronisiert werden. 
Windows Information Protection |    Für Unternehmen, die ein hohes Maß an Informationssicherheit benötigen, empfehlen wir [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) und Azure Information [Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection) 

