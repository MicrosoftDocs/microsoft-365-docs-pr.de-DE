---
title: Sicherheit in Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: b91b646b00869827dfb2131e9df9db38a770d9df
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278634"
---
# <a name="security-in-microsoft-managed-desktop"></a>Sicherheit in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop wendet eine Reihe von Standardrichtlinien an und verwendet zahlreiche Microsoft-Technologien, um sicherzustellen, dass von Microsoft verwaltete Desktop Geräte, gespeicherte Unternehmensdaten und vieles mehr geschützt werden. Die folgenden Bereiche sind weiter unten aufgeführt:  

- [Datensicherheit](#data-security) – Arten von Daten, die von Microsoft Managed Desktop gesammelt und sicher gespeichert werden
- [Gerätesicherheit](#device-security) – Sicherheit und Schutz auf von Microsoft verwalteten Desktop Geräten
- [Identitäts-und Zugriffsverwaltung](#identity-and-access-management) – Verwalten der sicheren Verwendung von Geräten über Azure Active Directory Identity Services
- [Netzwerksicherheit](#network-security) – VPN-Informationen und Empfohlene Microsoft Managed Desktop-Lösung und Einstellungen
- [Informationssicherheit](#information-security) – optionale verfügbare Dienste zum Schutz vertraulicher Informationen 

## <a name="data-security"></a>Datensicherheit

Daten, die von Kundenmandanten erfasst werden (Dies ermöglicht Microsoft Managed Desktop-IT-Dienste und-Vorgänge), werden in Azure SQL-Datenbanken im Microsoft-Mandanten gespeichert, der in den USA gehostet wird.

Weitere Informationen finden Sie unter [Microsoft Azure Security](https://docs.microsoft.com/azure/security/azure-database-security-overview).

Nachfolgend sind die Datentypen aufgeführt, die von Ihrem Mandanten übermittelt werden:

- Geräteaktualisierung, Verwendungs-und Zuverlässigkeitsdaten
- App-Bereitstellung und Zuverlässigkeitsdaten
- Update-und Sicherheitsrichtlinien-Bereitstellungsdaten
- Geräte zugewiesene Benutzer



## <a name="device-security"></a>Gerätesicherheit

Microsoft Managed Desktop stellt sicher, dass alle verwalteten Geräte gesichert und geschützt sind, und erkennt Bedrohungen so früh wie möglich mithilfe der folgenden Dienste:

Dienst | Beschreibung
--- | ---
Antivirus | Windows Defender AV ist installiert und konfiguriert<br>Windows Defender AV-Definitionen sind auf dem neuesten Stand
Vollständige Volumen Verschlüsselung |    Windows BitLocker ist die Volumen Verschlüsselungslösung für Microsoft Managed Desktop-Geräte.<br><br>Sobald eine Organisation in den Dienst integriert wurde, werden die Geräte mithilfe von Windows BitLocker mit integriertem Trust Platform Module (TPM) verschlüsselt, um den unbefugten Zugriff auf lokale Daten zu verhindern, wenn sich das Gerät im Standbymodus befindet, oder aus. 
Überwachung |    Windows Defender Advanced Threat Protection (Windows Defender ATP) wird für die Überwachung von Sicherheitsbedrohungen auf allen Microsoft-Desktop Geräten verwendet. Mit Windows Defender ATP können Unternehmenskunden erweiterte Bedrohungen in Ihrem Unternehmensnetzwerk aufspüren, untersuchen und darauf reagieren. Weitere Informationen finden Sie unter [Advanced Threat Protection von Windows Defender.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Betriebssystemupdates |  Microsoft Managed Desktop-Geräte sind immer mit den neuesten Sicherheitsupdates gesichert.
Sichere Gerätekonfiguration |   Microsoft Managed Desktop implementiert die Microsoft-Sicherheitsbasislinie. Weitere Informationen finden Sie unter [Windows-Sicherheits-Baselines.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Identitäts- und Zugriffsverwaltung

Identitäts-und Zugriffsverwaltung schützt Unternehmensressourcen und geschäftskritische Daten. Microsoft Managed Desktop konfiguriert Geräte, um die sichere Verwendung mit Azure Active Directory (Azure AD) verwalteten Identitäten sicherzustellen. Der Kunde ist dafür verantwortlich, im Azure AD-Mandanten genaue Informationen zu erhalten. 

Dienst | Beschreibung
--- | ---
Biometrische Authentifizierung |  Windows Hello ermöglicht es Benutzern, sich über Ihr Gesicht oder eine PIN anzumelden, um Kennwörter zu vergessen oder zu stehlen. Weitere Informationen finden Sie unter [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
Mehrstufige Authentifizierung | Die mehrstufige Azure-Authentifizierung steuert den Zugriff auf vertrauliche Funktionen des verwalteten Desktop Diensts von Microsoft, indem eine zusätzliche Authentifizierungsebene über ein Mobiltelefon und eine Self-Service-Kennwortzurücksetzung bereitgestellt wird. 
Standard Benutzerberechtigung |  Um das System zu schützen und es sicherer zu machen, wird dem Benutzer Standard Benutzerberechtigungen zugewiesen. Dieser wird als Teil der Out-of-Box-Benutzeroberfläche von Windows Autopilot zugewiesen.



## <a name="network-security"></a>Netzwerksicherheit

Die Kunden sind für die Netzwerksicherheit verantwortlich. 

Dienst | Beschreibung
--- | ---
VPN | Kunden besitzen Ihre VPN-Infrastruktur, um sicherzustellen, dass begrenzte Unternehmensressourcen außerhalb des Intranets verfügbar gemacht werden können.<br><br>Mindestanforderung: Microsoft Managed Desktop erfordert eine Windows 10-kompatible und unterstützte VPN-Lösung. Wenn Ihre Organisation eine VPN-Lösung benötigt, muss Sie Windows 10 unterstützen und über InTune verpackt und bereitgestellt werden. Weitere Informationen erhalten Sie von Ihrem Softwareherausgeber.<br><br>Empfehlung<br>-Microsoft empfiehlt eine moderne VPN-Lösung, die problemlos über InTune bereitgestellt werden kann, um VPN-Profile zu pushen. Dies stellt eine ständige, nahtlose, zuverlässige und sichere Möglichkeit für den Zugriff auf das Unternehmensnetzwerk bereit. Weitere Informationen finden Sie unter [[VPN Settings in InTune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>-Dicke VPN-Clients oder Legacy-VPN-Clients werden von Microsoft bei der Verwendung von Microsoft Managed Desktop nicht empfohlen, da sich dies auf die Endbenutzerumgebung auswirken kann.<br>-Microsoft empfiehlt, dass der ausgehende Web-Datenverkehr direkt ins Internet gelangt, ohne das VPN zu überlaufen, um Leistungsprobleme zu vermeiden.<br>-Im Idealfall empfiehlt Microsoft die Verwendung von Azure Active Directory-App-Proxy anstelle eines VPN.


## <a name="information-security"></a>Informationssicherheit

Kunden können diese optionalen Dienste so konfigurieren, dass Sie die hochwertigen Ressourcen von Unternehmen schützen. 

Dienst | Beschreibung
--- | ---
Datenwiederherstellung  | In Schlüsselordnern auf dem Gerät gespeicherte Informationen werden in OneDrive for Business gesichert. Microsoft Managed Desktop ist nicht für Daten verantwortlich, die nicht mit OneDrive for Business synchronisiert werden. 
Windows Information Protection |    Für Unternehmen, die ein hohes Maß an Informationssicherheit erfordern, empfehlen wir [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) und [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection). 

