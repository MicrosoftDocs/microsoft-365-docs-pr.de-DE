---
title: Microsoft Managed Desktop-Technologien
description: In diesem Artikel werden die Technologien und Apps aufgeführt, die in Microsoft Managed Desktop verwendet werden.
keywords: Microsoft Managed Desktop, Microsoft 365, Dienst, Dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 4932a40455c8ed4d8fdfc0dfae99c8001e582ff4
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094867"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop-Technologien

In diesem Artikel werden die Technologien und Apps aufgeführt, die in Microsoft Managed Desktop verwendet werden.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-Lizenzierung ist für alle Benutzer von Microsoft Managed Desktop erforderlich. Weitere Informationen zu den Lizenzierungsanforderungen für den Dienst finden Sie unter ["Voraussetzungen für Microsoft Managed Desktop".](../get-ready/prerequisites.md)

In diesem Artikel werden die Komponenten zusammengefasst, die in den erforderlichen Lizenzen für Unternehmen enthalten sind, sowie eine Beschreibung, wie der Dienst die einzelnen Komponenten mit Microsoft Managed Desktop-Geräten verwendet. Spezifische Rollen und Zuständigkeiten für jeden Bereich werden in der gesamten Microsoft Managed Desktop-Dokumentation ausführlich beschrieben. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 oder E5
 |
 --- | ---
Microsoft 365 Apps for Enterprise (64-Bit) | Diese Office-Anwendungen werden mit dem Gerät ausgeliefert: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>Die 64-Bit-Vollversionen von Microsoft Project und Microsoft Visio sind nicht enthalten. Da die Installation dieser Anwendungen jedoch von der Installation von Microsoft 365 Apps for Enterprise abhängt, hat Microsoft Managed Desktop standardmäßige Microsoft Intune-Bereitstellungen und Sicherheitsgruppen erstellt, die Sie dann verwenden können, um diese Anwendungen für lizenzierte Benutzer bereitzustellen. Weitere Informationen finden Sie unter [Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop-Geräten.](../get-started/project-visio.md)
OneDrive |Azure Active #A0 ist für Benutzer aktiviert, wenn sie sich zum ersten Mal bei OneDrive anmelden.<br><br>Umleitung bekannter Ordner für die Ordner "Desktop", "Dokument" und "Bilder" ist enthalten; aktiviert und von Microsoft Managed Desktop konfiguriert.
Store-Apps |    Microsoft Sway und Power BI werden nicht im Lieferumfang des Geräts ausgeliefert. Diese Apps stehen im Microsoft Store zum Download zur Verfügung.
Win32-Anwendungen |    Teams ist nicht im Lieferumfang des Geräts enthalten, sondern wird von Microsoft für Microsoft Managed Desktop-Geräte gepackt und bereitgestellt. Azure Information Protection Client ist nicht im Lieferumfang des Geräts enthalten, Sie können ihn jedoch für die Bereitstellung packen.
Webanwendungen |  Yammer, Office in einem Browser, Delve, Flow, StaffHub, PowerApps und Planner werden nicht mit dem Gerät ausgeliefert. Benutzer können über einen Browser auf die Webversion dieser Anwendungen zugreifen.



## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 oder E3 mit Microsoft Defender for Endpoint
Empfohlen
 |
 --- | ---
[Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) | Kunden wird empfohlen, Windows Hello for Business zu implementieren, um Kennwörter durch eine sichere zweistufige Authentifizierung zu ersetzen, die auf Microsoft Managed Desktop-Geräten verwendet wird.
[Anwendungsvirtualisierung](https://docs.microsoft.com/windows/application-management/app-v/appv-technical-reference) | Kunden können Application Virtualization (App-V)-Pakete mithilfe des Intune Win32-App-Verwaltungsclients bereitstellen.
[Verhinderung von Datenverlust in Microsoft 365](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about) | Kunden wird empfohlen, Microsoft 365 Data Loss Prevention (DLP) zu implementieren, um die Aktionen zu überwachen, die für Elemente ergriffen werden, die Sie als vertraulich festgelegt haben, und um die unbeabsichtigte Freigabe dieser Elemente zu verhindern.   

Im Dienst enthalten und verwaltet
 |
 --- | ---
[BitLocker-Laufwerkverschlüsselung](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) | Die BitLocker-Laufwerkverschlüsselung wird zum Verschlüsseln aller Systemlaufwerke verwendet. 
[Windows Defender System Guard]( https://docs.microsoft.com/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows) | Schützt die Integrität des Systems beim Start und überprüft, ob die Systemintegrität wirklich beibehalten wurde.
[Windows Defender Credential Guard]( https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) | Windows Defender Credential Guard verwendet virtualisierungsbasierte Sicherheit, um geheime Schlüssel zu isolieren, sodass nur privilegierte Systemsoftware darauf zugreifen kann.
[Microsoft Defender for Endpoint | Endpunkterkennung und -reaktion](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response) |     Microsoft Managed Desktop Security Operations reagiert auf Warnungen und ergreift Maßnahmen zur Behebung von Bedrohungen mithilfe von Endpunkterkennung und -reaktion.
[Microsoft Defender for Endpoint | Bedrohungsexperten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts) | Microsoft Managed Desktop integriert Einblicke und Daten von Bedrohungsexperten durch gezielte Angriffsbenachrichtigungen. Kunden müssen zusätzliche Zustimmung geben, bevor dieser Dienst aktiviert wird.  
[Microsoft Defender for Endpoint | Bedrohungs- und Sicherheitsrisikoverwaltung](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt) | Erforderlich für die zukünftige Verwendung im Microsoft Managed Desktop-Dienstplan.
[Microsoft Defender for Endpoint | Attack Surface Reduction](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction) | Attack Surface Reduction zielt auf riskante Softwareverhalten ab, die häufig von Angreifern missbraucht werden.
[Microsoft Defender for Endpoint | Exploit-Schutz](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/exploit-protection) | Schützt vor Schadsoftware, die Exploits verwendet, um Geräte zu infizieren und zu verteilen, indem Exploit-Gegentechniken automatisch sowohl auf Betriebssystemprozesse als auch auf Apps angewendet werden.
[Microsoft Defender for Endpoint | Netzwerkschutz](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/network-protection) | Der Netzwerkschutz erweitert den Umfang von Microsoft Defender SmartScreen, um den gesamten ausgehenden HTTP/s-Datenverkehr zu blockieren, der versucht, eine Verbindung mit Quellen mit niedriger Reputation herzustellen.
[Microsoft Defender Manipulationsschutz](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection) | Windows Tamper Protection wird verwendet, um zu verhindern, dass Sicherheitseinstellungen wie Virenschutz geändert werden.
[Microsoft Defender Antivirus Behavior-basierter, heuristischer und Echtzeit-Antivirusschutz]( https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10) | Immer auf Datei- und Prozessbedrohungen prüfen, die möglicherweise nicht als Schadsoftware erkannt werden.
[Von Microsoft Defender Antivirus über die Cloud gelieferter Schutz](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus) | Bietet dynamischen, nahezu sofortigen, automatisierten Schutz vor neuen und neuen Bedrohungen.
[Microsoft Defender block at first sight](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus) | Ermöglicht die Erkennung und Blockierung neuer Schadsoftware, wenn Windows eine verdächtige oder unbekannte Datei erkennt.
[Microsoft Defender AV– Potenziell unerwünschte Anwendungen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) | Potenziell unerwünschte Anwendungen (PUA) werden verwendet, um Apps zu blockieren, die dazu führen können, dass Ihr Computer langsam ausgeführt wird, unerwartete Anzeigen anzeigen oder im schlechtesten Fall andere Software installieren, die unerwartet oder unerwünscht sein kann.
[Windows Defender Firewall mit erweiterter Sicherheit](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) | Hostbasierte, zwei-Wege-Netzwerkdatenverkehrfilterung für ein Gerät, Windows Defender Firewall blockiert nicht autorisierten Netzwerkdatenverkehr, der in das oder aus dem lokalen Gerät fließt.
[Benutzerkontensteuerung](https://docs.microsoft.com/windows/security/identity-protection/user-account-control/how-user-account-control-works) | Die Benutzerkontensteuerung wechselt zum Secure Desktop, wenn für eine Aufgabe oder Aktion der Administratorkontotypzugriff erforderlich ist. Microsoft Managed Desktop-Benutzern wird standardmäßiger Benutzerzugriff bei der Registrierung zugewiesen. 


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Sie können alle Features von Enterprise Mobility + Security E3 und Azure Active Directory Premium P2 zum Verwalten von MDM-Geräten verwenden.
Microsoft Cloud App-Sicherheit |  Sie können dieses optionale Feature mit Microsoft Managed Desktop verwenden.
Azure Information Protection P2  | Sie können dieses optionale Feature mit Microsoft Managed Desktop verwenden.
