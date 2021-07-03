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
ms.openlocfilehash: 07d4632c6ce775d98d9606f9edc4566aa48d9d8e
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287803"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Sicherheitstechnologien in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop verwendet verschiedene Microsoft-Technologien, um verwaltete Geräte und Daten zu schützen. Darüber hinaus verwendet das Microsoft Managed Desktop Security Operations Center verschiedene [Prozesse](security-operations.md) in Verbindung mit diesen Technologien.

Insbesondere gilt:

- [Gerätesicherheit](#device-security) – Sicherheit und Schutz auf Microsoft Managed Desktop Geräten
- [Identitäts- und Zugriffsverwaltung](#identity-and-access-management) – Verwalten der sicheren Verwendung von Geräten über Azure Active Directory Identitätsdienste
- [Netzwerksicherheit](#network-security) – VPN-Informationen und Microsoft Managed Desktop empfohlene Lösung und Einstellungen
- [Informationssicherheit](#information-security) – optionale verfügbare Dienste zum weiteren Schutz vertraulicher Informationen

Informationen zur Datenspeicherung, -verwendung und -sicherheit, die von Microsoft Managed Desktop verwendet werden, finden Sie in unserem Whitepaper unter [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Gerätesicherheit

Microsoft Managed Desktop stellt sicher, dass alle verwalteten Geräte gesichert und geschützt sind, und erkennt Bedrohungen so früh wie möglich mithilfe der folgenden Dienste:

Dienst | Beschreibung
--- | ---
Antivirus | Microsoft Defender AV ist installiert und konfiguriert<br>Microsoft Defender AV-Definitionen sind auf dem neuesten Stand
Vollständige Volumeverschlüsselung | Windows BitLocker ist die Volumeverschlüsselungslösung für Microsoft Managed Desktop Geräte.<br><br>Sobald eine Organisation in den Dienst integriert ist, werden Geräte mit Windows BitLocker mit integriertem Trust Platform Module (TPM) verschlüsselt, um nicht autorisierten Zugriff auf lokale Daten zu verhindern, wenn sich das Gerät im Standbymodus befindet oder ausgeschaltet ist.
Überwachung | Microsoft Defender für Endpunkt wird für die Überwachung von Sicherheitsrisiken auf allen Microsoft Managed Desktop Geräten verwendet. Defender für Endpunkt ermöglicht Es Unternehmenskunden, fortgeschrittene Bedrohungen in ihrem Unternehmensnetzwerk zu erkennen, zu untersuchen und darauf zu reagieren. Weitere Informationen finden Sie unter [Microsoft Defender für Endpunkt.](/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection)
Betriebssystemupdates | Microsoft Managed Desktop Geräte werden immer mit den neuesten Sicherheitsupdates gesichert.
Konfiguration sicherer Geräte | Microsoft Managed Desktop implementiert die Microsoft-Sicherheitsgrundwerte. Weitere Informationen finden Sie unter [Windows Sicherheitsgrundwerte.](/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Identitäts- und Zugriffsverwaltung

Identitäts- und Zugriffsverwaltung schützt Unternehmensressourcen und unternehmenskritische Daten. Microsoft Managed Desktop konfiguriert Geräte, um eine sichere Verwendung mit verwalteten Azure Active Directory (Azure AD)-Identitäten sicherzustellen. Es liegt in der Verantwortung des Kunden, genaue Informationen in ihrem Azure AD-Mandanten zu verwalten.

Dienst | Beschreibung
--- | ---
Biometrische Authentifizierung | Windows Hello ermöglicht Es Benutzern, sich mit ihrem Gesicht oder einer PIN anzumelden, wodurch Kennwörter schwieriger zu vergessen oder zu stehlen sind. Kunden sind für die Implementierung der erforderlichen Voraussetzungen für ihr lokales Active Directory für die Verwendung dieses Diensts in einer Hybridkonfiguration verantwortlich. Weitere Informationen finden Sie unter [Windows Hello.](/windows-hardware/design/device-experiences/windows-hello) 
Standardbenutzerberechtigung | Um das System zu schützen und sicherer zu machen, werden dem Benutzer Standardbenutzerberechtigungen zugewiesen. Diese Berechtigung wird als Teil der Windows Autopilot-Out-of-Box-Erfahrung zugewiesen.



## <a name="network-security"></a>Netzwerksicherheit

Kunden sind für die Netzwerksicherheit verantwortlich. 

Dienst | Beschreibung
--- | ---
VPN | Kunden besitzen ihre VPN-Infrastruktur, um sicherzustellen, dass begrenzte Unternehmensressourcen außerhalb des Intranets verfügbar gemacht werden können.<br><br>Mindestanforderung: Microsoft Managed Desktop erfordert eine Windows 10 kompatible und unterstützte VPN-Lösung. Wenn Ihre Organisation eine VPN-Lösung benötigt, muss sie Windows 10 unterstützen und über Intune gepackt und bereitgestellt werden können. Wenden Sie sich an Ihren Softwareherausgeber, um weitere Informationen zu erhalten.<br><br>Empfehlung:<br>– Microsoft empfiehlt eine moderne VPN-Lösung, die problemlos über Intune bereitgestellt werden kann, um VPN-Profile zu pushen. Dieser Ansatz bietet eine always-on, nahtlose, zuverlässige und sichere Möglichkeit, auf das Unternehmensnetzwerk zuzugreifen. Weitere Informationen finden Sie unter [[VPN-Einstellungen in Intune].](/intune/vpn-settings-configure)<br>– Thick VPN-Clients oder ältere VPN-Clients werden von Microsoft nicht empfohlen, während Microsoft Managed Desktop verwendet wird, da dies auswirkungen auf die Benutzerumgebung haben kann.<br>– Microsoft empfiehlt, den ausgehenden Webdatenverkehr direkt ins Internet zu übertragen, ohne das VPN zu durchlaufen, um Leistungsprobleme zu vermeiden.<br>– Im Idealfall empfiehlt Microsoft die Verwendung von Azure Active Directory App-Proxy anstelle eines VPN.


## <a name="information-security"></a>Informationssicherheit

Sie können diese optionalen Dienste konfigurieren, um hochwertige Unternehmensressourcen zu schützen. 

Dienst | Beschreibung
--- | ---
Datenwiederherstellung  | Informationen, die in Schlüsselordnern auf dem Gerät gespeichert sind, werden auf OneDrive for Business gesichert. Microsoft Managed Desktop ist nicht für Daten verantwortlich, die nicht mit OneDrive for Business synchronisiert werden.
Windows Information Protection | Für Unternehmen, die ein hohes Maß an Informationssicherheit benötigen, empfehlen wir [Windows Information Protection](/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) und Azure Information [Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection)
