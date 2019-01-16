---
title: Sicherheit in Microsoft Managed Desktop
description: ''
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 928d01e7386bedc500e984b9c2a3240c6229bb43
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/16/2019
ms.locfileid: "26868184"
---
# <a name="security-in-microsoft-managed-desktop"></a>Sicherheit in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Microsoft verwalteter Desktop wendet eine Reihe von Richtlinien und nutzt viele Microsoft-Technologien, mit denen sichere Microsoft verwalteter Desktop-Geräte und gespeicherten Unternehmensdaten. Die unten aufgeführten Bereiche sind weitere aufgeführt:  

- [Datensicherheit](#data-security) - Typen von von Microsoft verwalteten Desktops und dem sicheren Speicherort gesammelten Daten
- [Gerätesicherheit](#device-security) – Sicherheit und Schutz auf Microsoft verwalteter Desktop-Geräten
- [Identitäts- und](#identity-and-access-management) – Verwalten von sicheren Verwendung von Geräten über Webdienste für Azure Active Directory-Identität
- [Netzwerksicherheit](#network-security) – VPN-Informationen und Microsoft verwalteter Desktop empfohlen Lösung und Einstellungen
- [IT-Sicherheit](#information-security) – optional verfügbaren Dienste auf vertraulichen Informationen zu schützen 

## <a name="data-security"></a>Datensicherheit

In Azure SQL-Datenbanken in der Microsoft-Mandanten in den USA gehostet werden von Kunden Mandanten gesammelten Daten (wodurch Microsoft Managed Desktop-IT-Dienste und Vorgänge) gespeichert.

Weitere Informationen finden Sie unter [Microsoft Azure-Sicherheit](https://docs.microsoft.com/azure/security/azure-database-security-overview).

Unten finden Sie die Arten von Daten, die von Ihrem Mandanten übertragen:

- Device Update, Verwendung und Zuverlässigkeit-Daten
- App-Bereitstellung und Zuverlässigkeit Daten
- Update- und Sicherheit Bereitstellung Richtliniendaten
- Benutzer, die Geräte zugewiesen



## <a name="device-security"></a>Sicherheit von Geräten

Microsoft verwalteten Desktops wird sichergestellt, alle verwaltete Geräten sind gesichert und geschützt und erkennt Bedrohungen so früh wie möglich über die folgenden Dienste:

Dienst | Beschreibung
--- | ---
Antivirus | Windows Defender AV ist installiert und konfiguriert<br>Windows Defender a/v-Definitionen sind auf dem aktuellen Stand
Vollständige Volume-Verschlüsselung |    Windows BitLocker ist die Lautstärke Verschlüsselung-Lösung für Microsoft verwalteter Desktop-Geräte.<br><br>Nachdem eine Organisation Onboarded an den Webdienst handelt, werden Geräte mit Windows BitLocker mit integrierten vertrauen Platform Modul (TPM) um nicht autorisierten Zugriff auf lokale Daten zu verhindern, wenn das Gerät im Ruhezustand oder deaktiviert ist verschlüsselt. 
Überwachung |    Windows Defender erweiterte Threat Protection (Windows Defender ATP) wird für die Sicherheit Bedrohung Überwachung auf allen Geräten von Microsoft verwaltet Desktop verwendet. Windows Defender ATP ermöglicht Unternehmenskunden erkennen, untersuchen und reagieren auf Erweiterte Bedrohungen in ihrem Unternehmensnetzwerk. Weitere Informationen finden Sie unter [Windows Defender erweiterte Threat Protection.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Softwareupdates (engl.) |  Microsoft verwalteter Desktop-Geräte werden immer mit den neuesten Sicherheitsupdates geschützt.
Sichere Gerätekonfiguration |   Microsoft verwalteter Desktop implementiert die Microsoft Security Baseline. Weitere Informationen finden Sie unter [Windows Sicherheitsbaselines.](https://docs.microsoft.com/windows/security/threat-protection/windows-security-baselines)



## <a name="identity-and-access-management"></a>Identitäts- und Zugriffsverwaltung

Identitäts-und schützt Unternehmensressourcen und Unternehmensdaten. Microsoft verwalteter Desktop konfiguriert Geräte, um sicherzustellen, dass sichere Verwendung mit Azure Active Directory (AD Azure) Identitäten verwaltet. Es ist der Kunde dafür verantwortlich, die genaue Informationen in ihrer Azure AD-Mandanten zu verwalten. 

Dienst | Beschreibung
--- | ---
Biometrische Authentifizierung |  Windows Hello ermöglicht Benutzern, sich mit der Vorderseite oder eine PIN, Kennwörter vergessen oder stehlen schwieriger zu tätigen. Weitere Informationen finden Sie unter [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
Mehrstufige Authentifizierung | Azure Multi-Factor Authentication steuert den Zugriff auf sensible Funktionen des Diensts Microsoft verwalteter Desktop enger durch ein höheres Maß an Authentifizierung mit einem Mobiltelefon als auch als Self-service das Zurücksetzen von Kennwörtern bereitstellen. 
Berechtigung für Standardbenutzer |  Zum Schutz des Systems und sicherer machen, wird der Benutzer Standard Benutzerberechtigungen zugewiesen. Dies wird als Teil der Windows-Autopilot Out-of-Box-Experience zugewiesen.



## <a name="network-security"></a>Netzwerksicherheit

Kunden sind verantwortlich für die Netzwerksicherheit. 

Dienst | Beschreibung
--- | ---
VPN | Kunden besitzen ihre VPN-Infrastruktur, um sicherzustellen, dass beschränkte Unternehmensressourcen außerhalb des Intranets verfügbar gemacht werden können.<br><br>Mindestanforderung: Microsoft Managed Desktop benötigt eine Windows 10 kompatibel und unterstützte VPN-Lösung. Wenn Ihre Organisation eine VPN-Lösung benötigt wird, muss sie unterstützten Windows 10 und gepackt und über Intune bereitgestellt werden. Weitere Informationen erhalten Sie von Ihrem Softwarepublisher.<br><br>Empfehlung:<br>-Microsoft empfiehlt eine moderne VPN-Lösung, die auf einfache Weise zu Push VPN-Profilen über Intune bereitgestellt werden konnte. Dadurch wird immer auf, nahtlose, zuverlässige und sichere Weise Zugriff auf Unternehmensnetzwerk. Weitere Informationen finden Sie unter [[VPN-Einstellungen in Intune]](https://docs.microsoft.com/intune/vpn-settings-configure).<br>-Dicken VPN-Clients oder VPN-Clients von Vorversionen, werden nicht von Microsoft während der Verwendung von Microsoft verwalteter Desktop wie es die Endbenutzer-Umgebung beeinflussen kann empfohlen.<br>-Microsoft empfiehlt, die ausgehende Webdatenverkehr direkt zu Internet wechselt, ohne Umweg über das VPN, um mögliche Leistungsprobleme zu vermeiden.<br>-Microsoft empfiehlt idealerweise die Verwendung von Azure Active Directory-App-Proxy anstelle eines VPN.


## <a name="information-security"></a>IT-Sicherheit

Kunden können optionale Dienste zum Schutz von Unternehmensressourcen hochwertige konfigurieren. 

Dienst | Beschreibung
--- | ---
Wiederherstellung von Daten  | Informationen, die in Ordnern auf dem Gerät gespeichert wird zu OneDrive for Business gesichert. Microsoft verwalteter Desktop ist nicht für Daten, die mit OneDrive for Business synchronisiert ist nicht verantwortlich. 
Windows Information Protection |    Für Unternehmen, die hohe Sicherheitsstufen Informationen benötigen, sollten [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) und [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection). 

