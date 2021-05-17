---
title: Microsoft Managed Desktop-Technologien
description: In diesem Artikel werden die in Microsoft Managed Desktop verwendeten Technologien und Apps aufgeführt.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 22371d22562960efdc50235657a08e15dba893d3
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920576"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop-Technologien

In diesem Artikel werden die in Microsoft Managed Desktop verwendeten Technologien und Apps aufgeführt.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-Lizenzierung ist für alle Microsoft Managed Desktop-Benutzer erforderlich. Weitere Informationen zu den Lizenzierungsanforderungen für den Dienst finden Sie unter [Voraussetzungen für Microsoft Managed Desktop](../get-ready/prerequisites.md).

In diesem Artikel werden die Komponenten zusammengefasst, die in den erforderlichen Enterprise-Lizenzen enthalten sind, mit einer Beschreibung, wie der Dienst jede Komponente mit Microsoft Managed Desktop-Geräten verwendet. Spezifische Rollen und Zuständigkeiten für jeden Bereich werden in der Dokumentation zu Microsoft Managed Desktop beschrieben. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 oder E5
 |
 --- | ---
Microsoft 365 Apps for Enterprise (64-Bit) | Diese Office-Anwendungen werden mit dem Gerät ausgeliefert: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>Die 64-Bit-Vollversionen von Microsoft Project und Microsoft Visio sind nicht enthalten. Da die Installation dieser Anwendungen jedoch von der Installation von Microsoft 365 Apps for Enterprise abhängt, hat Microsoft Managed Desktop Standardmäßige Microsoft Intune-Bereitstellungen und Sicherheitsgruppen erstellt, die Sie dann verwenden können, um diese Anwendungen für lizenzierte Benutzer bereitzustellen. Weitere Informationen finden Sie unter [Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten.](../get-started/project-visio.md)
OneDrive |Einmaliges Anmelden in Azure Active Directory ist für Benutzer aktiviert, wenn sie sich zum ersten Mal bei OneDrive anmelden.<br><br>Bekannte Ordnerumleitung für Ordner "Desktop", "Dokument" und "Bilder" ist enthalten; aktiviert und von Microsoft Managed Desktop konfiguriert.
Store-Apps |    Microsoft Sway und Power BI werden nicht mit dem Gerät ausgeliefert. Diese Apps stehen im Microsoft Store zum Download bereit.
Win32-Anwendungen |    Teams wird nicht mit dem Gerät ausgeliefert, sondern von Microsoft für Microsoft Managed Desktop-Geräte verpackt und bereitgestellt. Der Azure Information Protection-Client wird nicht mit dem Gerät ausgeliefert, aber Sie können ihn für die Bereitstellung packen lassen.
Webanwendungen |  Yammer werden Office in einem Browser, Delve, Flow, StaffHub, PowerApps und Planner nicht mit dem Gerät ausgeliefert. Benutzer können über einen Browser auf die Webversion dieser Anwendungen zugreifen.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 oder E3 mit Microsoft Defender for Endpoint
Es wird empfohlen, dass Ihre IT-Administratoren die folgenden Einstellungen konfigurieren. Diese Einstellungen werden nicht als Teil von Microsoft Managed Desktop einbezogen oder verwaltet.

 |
 --- | ---
Windows Hello for Business | Sie sollten Windows Hello for Business implementieren, um Kennwörter durch eine starke zweistufige Authentifizierung für Microsoft Managed Desktop-Geräte zu ersetzen. Weitere Informationen finden Sie unter [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification).
Anwendungsvirtualisierung | Sie können Anwendungsvirtualisierungspakete (App-V) mithilfe des Intune Win32-App-Verwaltungsclients bereitstellen. Weitere Informationen finden Sie unter [Application Virtualization](/windows/application-management/app-v/appv-technical-reference).
Verhinderung von Datenverlust in Microsoft 365 | Sie sollten die Verhinderung von Datenverlust in Microsoft 365 implementieren, um die Aktionen zu überwachen, die für Elemente ergriffen werden, die Sie als vertraulich festgelegt haben, und um die unbeabsichtigte Freigabe dieser Elemente zu verhindern. Weitere Informationen finden Sie unter Verhinderung von [Datenverlust in Microsoft 365](../../compliance/endpoint-dlp-learn-about.md).


Im Rahmen von Microsoft Managed Desktop enthaltene und verwaltete Features:

 |
 --- | ---
BitLocker-Laufwerkverschlüsselung | Die BitLocker-Laufwerkverschlüsselung wird zum Verschlüsseln aller Systemlaufwerke verwendet. Weitere Informationen finden Sie unter [BitLocker Drive Encryption](/windows/security/information-protection/bitlocker/bitlocker-overview).
Windows Defender System Guard | Schützt die Integrität des Systems beim Start und überprüft, ob die Systemintegrität wirklich beibehalten wurde. Weitere Informationen finden Sie unter [Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows).
Windows Defender Credential Guard | Windows Defender Credential Guard verwendet virtualisierungsbasierte Sicherheit, um geheime Schlüssel zu isolieren, sodass nur privilegierte Systemsoftware darauf zugreifen kann. Weitere Informationen finden Sie unter [Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows).
Microsoft Defender for Endpoint – Endpunkterkennung und -reaktion | Microsoft Managed Desktop Security Operations reagiert auf Warnungen und ergreift Maßnahmen zur Behebung von Bedrohungen mithilfe von Endpoint Detection and Response. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint - Endpoint Detection and Response](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response).
Microsoft Defender for Endpoint – Bedrohungsexperten | Microsoft Managed Desktop integriert Einblicke und Daten von Bedrohungsexperten durch gezielte Angriffsbenachrichtigungen. Bevor dieser Dienst aktiviert ist, müssen Sie zusätzliche Zustimmung erteilen. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint - Threat Experts](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).
Microsoft Defender for Endpoint – Bedrohungs- und Sicherheitsrisikoverwaltung | Erforderlich für die zukünftige Verwendung im Microsoft Managed Desktop-Dienstplan. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint – Threat and Vulnerability Management](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt).
Microsoft Defender for Endpoint – Attack Surface Reduction | Die Reduzierung der Angriffsfläche zielt auf riskante Softwareverhalten ab, die häufig von Angreifern missbraucht werden. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint - Attack Surface Reduction](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction).
Microsoft Defender for Endpoint – Exploit Protection | Schützt vor Schadsoftware, die Exploits verwendet, um Geräte zu infizieren und zu verteilen, indem sie automatisch Techniken zur Risikominderung auf Betriebssystemprozesse und Apps anwenden. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint - Exploit Protection](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection).
Microsoft Defender for Endpoint – Netzwerkschutz | Der Netzwerkschutz erweitert den Umfang von Microsoft Defender SmartScreen, um den gesamten ausgehenden HTTP- und HTTPS-Datenverkehr zu blockieren, der versucht, eine Verbindung mit Quellen mit niedriger Reputation herzustellen. Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint - Network Protection](/windows/security/threat-protection/microsoft-defender-atp/network-protection).
Microsoft Defender Tamper Protection | Windows Tamper Protection wird verwendet, um zu verhindern, dass Sicherheitseinstellungen wie virenschutz geändert werden. Weitere Informationen finden Sie unter [Microsoft Defender Tamper Protection](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection).
Microsoft Defender Antivirus Behavior-based, heuristic, and real-time antivirus protection | Immer bei der Überprüfung auf Datei- und Prozessbedrohungen, die möglicherweise nicht als Schadsoftware erkannt werden. Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Behavior-based, heuristic, and real-time antivirus protection]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10).
Microsoft Defender Antivirus Cloud-delivered Protection | Bietet dynamischen, nahezu sofortigen, automatisierten Schutz vor neuen und neuen Bedrohungen. Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Cloud-delivered Protection](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus).
Microsoft Defender "Beim ersten Blick blockieren" | Ermöglicht die Erkennung und Blockierung neuer Schadsoftware, wenn Windows eine verdächtige oder unbekannte Datei erkennt. Weitere Informationen finden Sie unter [Microsoft Defender Block at first sight](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus).
Microsoft Defender AV Potenziell unerwünschte Anwendungen | Potenziell unerwünschte Anwendungen werden verwendet, um Apps zu blockieren, die dazu führen können, dass Ihr Computer langsam ausgeführt wird, unerwartete Anzeigen anzeigen oder im schlechtesten Fall andere Software installieren, die unerwartet oder unerwünscht sein kann. Weitere Informationen finden Sie unter [Microsoft Defender AV Potentially Unwanted Applications](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus).
Windows Defender Firewall mit erweiterter Sicherheit | Hostbasierte, zwei-Wege-Netzwerkdatenverkehrfilterung für ein Gerät, Windows Defender Firewall nicht autorisierten Netzwerkdatenverkehr blockiert, der in das lokale Gerät oder aus das lokale Gerät fließt. Weitere Informationen finden Sie unter [Windows Defender Firewall with Advanced Security](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security).
Benutzerkontensteuerung | Die Benutzerkontensteuerung wechselt zum Secure Desktop, wenn für eine Aufgabe oder Aktion der Administratorkontotypzugriff erforderlich ist. Microsoft Managed Desktop-Benutzern wird standardmäßiger Benutzerzugriff bei der Registrierung zugewiesen. Weitere Informationen finden Sie unter [Benutzerkontensteuerung](/windows/security/identity-protection/user-account-control/how-user-account-control-works).


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Sie können alle Features von Enterprise Mobility + Security E3 und Azure Active Directory Premium P2 verwenden, um MDM-Geräte zu verwalten.
Microsoft Cloud App Security |  Sie können dieses optionale Feature mit Microsoft Managed Desktop verwenden.
Azure Information Protection P2  | Sie können dieses optionale Feature mit Microsoft Managed Desktop verwenden.