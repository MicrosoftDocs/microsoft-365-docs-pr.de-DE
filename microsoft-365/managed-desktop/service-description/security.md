---
title: Sicherheitstechnologien in Microsoft Managed Desktop
description: ''
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: e69656e13cd9a300cd56bdd5db7703f2387d23d4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846204"
---
# <a name="security-technologies-in-microsoft-managed-desktop"></a>Sicherheitstechnologien in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft Managed Desktop verwendet mehrere Microsoft-Technologien, um die Sicherung verwalteter Geräte und Daten zu unterstützen. Darüber hinaus verwendet das Microsoft Managed Desktop Security Operations Center eine Vielzahl von [Prozessen](security-operations.md) in Verbindung mit diesen Technologien.

Insbesondere gilt: 

- [Gerätesicherheit](#device-security) – Sicherheit und Schutz auf Microsoft Managed Desktop-Geräten
- [Identitäts-und Zugriffsverwaltung](#identity-and-access-management) – Verwalten der sicheren Verwendung von Geräten über Azure Active Directory Identitätsdienste
- [Netzwerksicherheit](#network-security) – empfohlene Lösung und Einstellungen für VPN-Informationen und Microsoft Managed Desktop
- [Informationssicherheit](#information-security) – optional verfügbare Dienste für den weiteren Schutz vertraulicher Informationen 

Informationen zu den von Microsoft Managed Desktop verwendeten Datenspeicher-, Nutzungs-und Sicherheitsmethoden finden Sie in unserem Whitepaper unter [https://aka.ms/mmd-data](https://aka.ms/mmd-data) .


## <a name="device-security"></a>Gerätesicherheit

Microsoft Managed Desktop stellt sicher, dass alle verwalteten Geräte gesichert und geschützt sind, und erkennt Bedrohungen so früh wie möglich mithilfe der folgenden Dienste:

Dienst | Beschreibung
--- | ---
Antivirus | Microsoft Defender AV ist installiert und konfiguriert<br>Microsoft Defender AV-Definitionen sind auf dem neuesten Stand
Vollständige Volumen Verschlüsselung |    Windows BitLocker ist die Volumen Verschlüsselungslösung für Microsoft Managed Desktop-Geräte.<br><br>Sobald eine Organisation in den Dienst integriert wurde, werden die Geräte mithilfe von Windows BitLocker mit integriertem TPM (Trust Platform Module) verschlüsselt, um den nicht autorisierten Zugriff auf lokale Daten zu verhindern, wenn sich das Gerät im Ruhezustand befindet, oder aus. 
Überwachung |    Microsoft Defender für Endpoint wird für die Überwachung von Sicherheitsbedrohungen auf allen von Microsoft verwalteten Desktop Geräten verwendet. Mit Defender for Endpoint können Unternehmenskunden fortgeschrittene Bedrohungen in Ihrem Unternehmensnetzwerk erkennen, untersuchen und darauf reagieren. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Betriebssystemupdates |  Microsoft Managed Desktop-Geräte sind immer mit den neuesten Sicherheitsupdates gesichert.
Konfiguration für sichere Geräte |   Microsoft Managed Desktop implementiert die Microsoft-Sicherheitsbasis. Weitere Informationen finden Sie unter [Windows-Sicherheitsbasislinien.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Identitäts- und Zugriffsverwaltung

Identity and Access Management schützt Unternehmensressourcen und unternehmenswichtige Daten. Microsoft Managed Desktop konfiguriert Geräte zur Sicherstellung der sicheren Verwendung mit verwalteten Azure-Active Directory (Azure AD)-Identitäten. Es liegt in der Verantwortung des Kunden, in seinem Azure AD Mandanten genaue Informationen zu erhalten. 

Dienst | Beschreibung
--- | ---
Biometrische Authentifizierung |  Mit Windows Hello können sich Benutzer mit Ihrem Gesicht oder einer PIN anmelden, wodurch Kennwörter schwerer zu vergessen oder zu stehlen sind. Kunden sind für die Implementierung der erforderlichen Voraussetzungen für Ihre lokalen Active Directory für die Verwendung dieses Diensts in einer Hybrid Konfiguration verantwortlich. Weitere Informationen finden Sie unter [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello) 
Standard Benutzerberechtigung |  Um das System zu schützen und es sicherer zu machen, wird dem Benutzer Standard Benutzerberechtigungen zugewiesen. Dies wird als Teil der Out-of-Box-Erfahrung von Windows Autopilot zugewiesen.



## <a name="network-security"></a>Netzwerksicherheit

Kunden sind für die Netzwerksicherheit verantwortlich. 

Dienst | Beschreibung
--- | ---
VPN | Kunden besitzen Ihre VPN-Infrastruktur, um sicherzustellen, dass beschränkte Unternehmensressourcen außerhalb des Intranets verfügbar gemacht werden können.<br><br>Mindestanforderung: Microsoft Managed Desktop erfordert eine Windows 10-kompatible und unterstützte VPN-Lösung. Wenn Ihre Organisation eine VPN-Lösung benötigt, muss Windows 10 unterstützt und über InTune gepackt und bereitgestellt werden. Weitere Informationen erhalten Sie von Ihrem Softwareherausgeber.<br><br>Empfehlung<br>-Microsoft empfiehlt eine moderne VPN-Lösung, die problemlos über InTune bereitgestellt werden kann, um VPN-Profile zu pushen. Dadurch erhalten Sie eine ständige, nahtlose, zuverlässige und sichere Methode für den Zugriff auf das Unternehmensnetzwerk. Weitere Informationen finden Sie unter [[VPN Settings in InTune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>-Thick VPN-Clients oder Legacy-VPN-Clients werden von Microsoft nicht empfohlen, wenn Sie Microsoft Managed Desktop verwenden, da sich dies auf die Benutzerumgebung auswirken kann.<br>-Microsoft empfiehlt, dass der ausgehende Webdatenverkehr direkt ins Internet wechselt, ohne das VPN zu durchlaufen, um Leistungsprobleme zu vermeiden.<br>-Im Idealfall empfiehlt Microsoft die Verwendung von Azure Active Directory-App-Proxy anstelle eines VPN.


## <a name="information-security"></a>Informationssicherheit

Sie können diese optionalen Dienste zum Schutz von unternehmensübergreifenden hochwertigen Ressourcen konfigurieren. 

Dienst | Beschreibung
--- | ---
Datenwiederherstellung  | In Schlüsselordnern auf dem Gerät gespeicherte Informationen werden in OneDrive für Unternehmen gesichert. Microsoft Managed Desktop ist nicht für Daten verantwortlich, die nicht mit OneDrive für Unternehmen synchronisiert werden. 
Windows Information Protection |    Für Unternehmen, die ein hohes Maß an Informationssicherheit benötigen, wird [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) und [Azure Information Protection](https://www.microsoft.com/cloud-platform/azure-information-protection)empfohlen.. 

