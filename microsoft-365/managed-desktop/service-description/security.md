---
title: Sicherheit in Microsoft Managed Desktop
description: ''
keywords: Dokumentation Microsoft verwalteter Desktop, Microsoft-365-Dienst
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: 0ea0bbc6a8055ee8459fadd85a6fa4ddac14bdb7
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/28/2018
ms.locfileid: "26868184"
---
# <a name="security-in-microsoft-managed-desktop"></a>Sicherheit in Microsoft Managed Desktop

<!--Security, also Onboarding doc: data handling/store, privileged account access -->

Mithilfe von vielen Microsoft-Technologien, stellen wir sicher, dass Microsoft verwalteter Desktop Geräte sicher sind und das Microsoft verwalteter Desktop Security Vorgängen in Team verhindern, erkennen und auf Bedrohungen erweiterte reagieren kann. Drittanbieter-Security-Produkte, apps und Dienste sind nicht zulässig. Microsoft wendet einen Basisplan Standardrichtlinie, um sicherzustellen, Geräte, Identität, Netzwerk und Unternehmensdaten gesichert und geschützt werden.

In den folgenden Abschnitten werden diese Kategorien der Erzwingung der Sicherheit beschrieben:

- [Datensicherheit](#data-security) - wie wir Ihre Daten sicher gespeichert und Anforderungen für die Sicherheit von Azure Positionierung erfüllt
- [Gerätesicherheit](#device-security) – sichere sind wie wir Microsoft verwalteter Desktop Geräte sicherstellen
- [Identität Sicherheit](#identity-security) – wie kann sichergestellt werden Benutzer am Arbeitsplatz modernen sind nicht gefährdet.
- [Netzwerksicherheit](#network-security) – wie wir einen sicheren Zugriff auf Unternehmensressourcen sicherstellen
- [IT-Sicherheit](#information-security) – sichere ist wie wir Unternehmensdaten gewährleisten
- [Privilegierten Kontos Access](#privileged-account-access) – wie wir Einschränken des Zugriffs

## <a name="data-security"></a>Datensicherheit

Daten, die von Ihrem Mandanten übertragen werden in Azure SQL-Datenbanken in der Microsoft-Mandanten in den USA gehostet gespeichert. Ihre Daten gespeichert und für die Sicherheit von Azure Positionierung Anforderungen erfüllt. 

Weitere Informationen finden Sie unter [Microsoft Azure-Sicherheit](https://www.microsoft.com/TrustCenter/Security/azure-security).

In dieser Liste werden die Arten von Daten zwischen Microsoft und Ihrem Mandanten übertragen zusammengefasst. 

- Von Microsoft an Ihrem Mandanten
    - Gruppennamen
    - Konfigurieren der Sicherheitsrichtlinien
    - Gerät Aufträge
    - Benutzerkonten (Msadmin, Mstest, Microsoft verwaltete Desktop_soc_ro, Microsoft verwaltete Desktop_wdgsoc)
    - Die oben genannten 4 Benutzern E5 Lizenz zugewiesen
    - Richtlinien für klingelt Update für Windows update
    - In der Zukunft werden Funktionen ausgebaut, um das Veröffentlichen von anderen Inhaltstypen Konfiguration einschließlich apps, Richtlinien und Einstellungen zu ermöglichen.
- Von Ihrem Mandanten an Microsoft
    - Device Update, Verwendung und Zuverlässigkeit-Daten
    - App-Bereitstellung und Zuverlässigkeit Daten
    - Update- und Sicherheit Bereitstellung Richtliniendaten
    - Benutzer, die Geräte zugewiesen



## <a name="device-security"></a>Sicherheit von Geräten

Um Sicherheitsrisiken auszuschließen, ist es wichtig, um sicherzustellen, dass alle Microsoft verwalteter Desktop-Geräte fehlerfrei und gesichert werden. Es ist gleichermaßen wichtig, um sicherzustellen, dass wir können fehlerhaft Geräte erkennen und das Risiko so früh wie möglich.

Die folgende Tabelle enthält die Dienste zur Verfügung gestellt, um sicherzustellen, dass Microsoft verwalteter Desktop Geräte vertrauenswürdigen, fehlerfrei und gesichert wurden.

Dienst | Beschreibung
--- | ---
Antivirus | Es wird Folgendes sicherstellen:<br>-A/v Windows-Defender ist installiert und konfiguriert<br>-A/v Windows-Defender Definitionen sind auf dem aktuellen Stand
Vollständige Volume-Verschlüsselung |    Windows BitLocker ist die datenlösung Verschlüsselung für Microsoft verwalteter Desktop-Geräte.<br><br>Nachdem eine Organisation Onboarded an den Webdienst handelt, werden Geräte mit Windows BitLocker mit integrierten vertrauen Platform Modul (TPM) um nicht autorisierten Zugriff auf lokale Daten zu verhindern, wenn das Gerät im Ruhezustand oder deaktiviert ist verschlüsselt. 
Überwachung |    Windows Defender erweiterte Threat Protection (Windows Defender ATP) ist das Sicherheitsrisiko überwachen-Lösung für alle Microsoft verwalteter Desktop-Geräte. Windows Defender ATP ermöglicht Unternehmenskunden erkennen, untersuchen und reagieren auf Erweiterte Bedrohungen in ihrem Unternehmensnetzwerk. Weitere Informationen finden Sie unter [Windows Defender erweiterte Threat Protection.](https://docs.microsoft.com/windows/threat-protection/windows-defender-atp/windows-defender-advanced-threat-protection) 
Softwareupdates (engl.) |  Microsoft wird sichergestellt, dass Microsoft verwalteter Desktop Geräte immer mit dem neuesten Sicherheitsupdate für Windows und Office, mithilfe von Windows Update für Unternehmen geschützt sind.
Wiederherstellung“, |  Unternehmensdaten auf OneDrive für Unternehmen gespeichert und können problemlos für Microsoft verwalteter Desktop Geräte wiederhergestellt werden. Weitere Informationen finden Sie unter [OneDrive for Business.](https://support.office.com/article/Restore-a-previous-version-of-a-file-in-OneDrive-159cad6d-d76e-4981-88ef-de6e96c93893?ui=en-US&rs=en-US&ad=US) 



## <a name="identity-security"></a>Identity-Sicherheit

Identitäts-und schützt Unternehmensressourcen und Unternehmensdaten. Azure Active Directory (AD Azure) bietet Identitätsdienste in der Cloud und Cloud-basierten Authentifizierung aktivieren, die nur vertrauenswürdige Personen sicherstellt Unternehmensressourcen von Microsoft verwalteten Desktops Geräten zugreifen kann.

Dienst | Beschreibung
--- | ---
Authentifizierungsanbieter für Enterprise-Klasse |  Azure AD-Premium-Editionen von Microsoft verwendet geben Ihnen einen Hochverfügbarkeits-Dienst gehostet in Rechenzentren Global verteilt. Der Dienst verarbeitet Milliarden Authentifizierungen von mehr als 200 Millionen aktive Benutzer pro Tag und bietet Ihnen eine SLA 99,9 %.
Biometrische Authentifizierung |  Windows Hello ermöglicht Benutzern, sich mit der Vorderseite oder eine PIN, Kennwörter vergessen oder stehlen schwieriger zu tätigen. Dies erfordern möglicherweise zusätzliche Aufgaben konfigurieren. Weitere Informationen finden Sie unter [Windows Hello.](https://docs.microsoft.com/windows-hardware/design/device-experiences/windows-hello)
Multi-Factor authentication | Azure Multi-Factor Authentication verhindert nicht autorisierten Zugriff auf lokalen und cloud-Anwendungen durch ein höheres Maß an Authentifizierung mit einem Mobiltelefon Zurücksetzen von Kennwörtern sowie wie Self-service bereitstellen. 
Berechtigung für Standardbenutzer |  Zum Schutz des Systems und sicherer machen, wird der Benutzer Standard Benutzerberechtigungen zugewiesen. Dies wird als Teil der Windows-Autopilot Out-of-Box-Experience zugewiesen.



## <a name="network-security"></a>Netzwerksicherheit

Kunden sind verantwortlich für die Netzwerksicherheit. 

Dienst | Beschreibung
--- | ---
VPN | Kunden besitzen ihre VPN-Infrastruktur, um sicherzustellen, dass beschränkte Unternehmensressourcen außerhalb des Intranets verfügbar gemacht werden können.<br><br>Mindestanforderung: Microsoft Managed Desktop benötigt eine Windows 10 kompatibel und unterstützte VPN-Lösung. Wenn Ihre Organisation eine VPN-Lösung benötigt wird, muss sie unterstützten Windows 10 und gepackt und über Intune bereitgestellt werden. Weitere Informationen erhalten Sie von Ihrem Softwarepublisher.<br><br>Empfehlung:<br>-Microsoft empfiehlt eine moderne VPN-Lösung, die auf einfache Weise über Intune Push VPN-Profile bereitgestellt werden konnte. Dadurch wird immer auf, nahtlose, zuverlässige und sichere Weise Zugriff auf Unternehmensnetzwerk. Weitere Informationen finden Sie unter VPN-Einstellungen in Intune.<br>-Dicken VPN-Clients oder VPN-Clients von Vorversionen, werden nicht von Microsoft während der Verwendung von Microsoft verwalteter Desktop wie es die Endbenutzer-Umgebung beeinflussen kann empfohlen.<br>-Microsoft empfiehlt, die ausgehende Webdatenverkehr direkt zu Internet wechselt, ohne Umweg über das VPN, um mögliche Leistungsprobleme zu vermeiden.<br>-Microsoft empfiehlt idealerweise die Verwendung von Azure Active Directory-App-Proxy anstelle eines VPN.


## <a name="information-security"></a>IT-Sicherheit

Kunden können optionale Dienste zum Schutz von Unternehmensressourcen hochwertige konfigurieren. 

Dienst | Beschreibung
--- | ---
Bedingter Zugriff |    Zugriff auf Unternehmensressourcen und Dienste nur, wenn das Gerät kompatibel ist.
Wiederherstellung von Daten  | Informationen, die in Ordnern auf dem Gerät gespeichert wird zu OneDrive für Bbusiness gesichert. Microsoft verwalteter Desktop ist nicht für Daten, die mit OneDrive for Business synchronisiert ist nicht verantwortlich. 
Windows Information Protection |    Für Unternehmen, die hohe Sicherheitsstufen Informationen benötigen, sollten [Windows Information Protection](https://docs.microsoft.com/windows/threat-protection/windows-information-protection/protect-enterprise-data-using-wip) und [Azure Information Protection.](https://www.microsoft.com/cloud-platform/azure-information-protection). 


## <a name="privileged-account-access"></a>Privilegierten Kontozugriff

Heute, den wir Zugriff auf die Anmeldeinformationen des Kunden MSAdmin und die Anwendung über diese Mechanismen einschränken:

- **Operatoren** – Microsoft full-einmalig-Mitarbeiter befindet sich in den USA, die eine periodische Hintergrund und Sicherheit Prüfung erfolgreich abgeschlossen haben.
- **Operator Identität** – geschützte gemäß den Standards von Microsoft. Weitere Informationen finden Sie unter [Verwalten von Benutzeridentitäten und sicheren Zugriff bei Microsoft](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft). 
- **Protokollierung** der Operator-Umgebung und innerhalb der Mandant des Kunden erfolgt. Protokolldaten und persönliche Informationen werden beibehalten, in der jeweiligen Umgebung und durchlaufen nicht Umgebungen. 

