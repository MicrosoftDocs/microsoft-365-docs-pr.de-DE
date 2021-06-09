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
ms.openlocfilehash: 7c1f768e69fa65c76529e641f095e13fc7ad67c8
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841340"
---
# <a name="microsoft-managed-desktop-technologies"></a>Microsoft Managed Desktop-Technologien

In diesem Artikel werden die Technologien und Apps aufgeführt, die in Microsoft Managed Desktop verwendet werden.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise Lizenzierung ist für alle Microsoft Managed Desktop Benutzer erforderlich. Weitere Informationen zu den Lizenzierungsanforderungen für den Dienst finden Sie unter [Voraussetzungen für Microsoft Managed Desktop](../get-ready/prerequisites.md).

In diesem Artikel werden die Komponenten zusammengefasst, die in den erforderlichen Enterprise Lizenzen enthalten sind, mit einer Beschreibung, wie der Dienst jede Komponente mit Microsoft Managed Desktop Geräten verwendet. Spezifische Rollen und Zuständigkeiten für jeden Bereich werden in Microsoft Managed Desktop Dokumentation ausführlich beschrieben. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 oder E5
 |
 --- | ---
Microsoft 365 Apps for Enterprise (64-Bit) | Diese Office Anwendungen werden mit dem Gerät ausgeliefert: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, OneNote.<br><br>Die 64-Bit-Vollversionen von Microsoft Project und Microsoft Visio sind nicht enthalten. Da die Installation dieser Anwendungen jedoch von der Microsoft 365 Apps for Enterprise Installation abhängt, hat Microsoft Managed Desktop standard Microsoft Intune Bereitstellungen und Sicherheitsgruppen erstellt, die Sie dann verwenden können, um diese Anwendungen für lizenzierte Benutzer bereitzustellen. Weitere Informationen finden Sie unter [Installieren von Microsoft Project oder Microsoft Visio auf Microsoft Managed Desktop Geräten.](../get-started/project-visio.md)
OneDrive |Azure Active Directory Einmaliges Anmelden ist für Benutzer aktiviert, wenn sie sich zum ersten Mal bei OneDrive anmelden.<br><br>Die Umleitung bekannter Ordner für Ordner "Desktop", "Dokument" und "Bilder" ist enthalten. aktiviert und von Microsoft Managed Desktop konfiguriert.
Store-Apps |    Microsoft Sway und Power BI werden nicht mit dem Gerät ausgeliefert. Diese Apps können von Microsoft Store heruntergeladen werden.
Win32-Anwendungen |    Teams wird nicht mit dem Gerät ausgeliefert, sondern verpackt und von Microsoft für Microsoft Managed Desktop Geräte bereitgestellt. Der Azure Information Protection-Client ist nicht mit dem Gerät ausgeliefert, sie können ihn jedoch für die Bereitstellung packen lassen.
Webanwendungen |  Yammer, Office in einem Browser, Delve, Flow, StaffHub, PowerApps und Planner werden nicht mit dem Gerät ausgeliefert. Benutzer können mit einem Browser auf die Webversion dieser Anwendungen zugreifen.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise E5 oder E3 mit Microsoft Defender für Endpunkt
Es wird empfohlen, dass Ihre IT-Administratoren die folgenden Einstellungen konfigurieren. Diese Einstellungen werden nicht in Microsoft Managed Desktop einbezogen oder verwaltet.

 |
 --- | ---
Windows Hello for Business | Sie sollten Windows Hello for Business implementieren, um Kennwörter durch eine sichere zweistufige Authentifizierung für Microsoft Managed Desktop Geräte zu ersetzen. Weitere Informationen finden Sie unter [Windows Hello for Business](/windows/security/identity-protection/hello-for-business/hello-identity-verification).
Anwendungsvirtualisierung | Sie können Application Virtualization (App-V)-Pakete mit dem Intune Win32-App-Verwaltungsclient bereitstellen. Weitere Informationen finden Sie unter [Application Virtualization](/windows/application-management/app-v/appv-technical-reference).
Microsoft 365 Verhinderung von Datenverlust | Sie sollten Microsoft 365 Verhinderung von Datenverlust implementieren, um die Aktionen zu überwachen, die für Elemente ausgeführt werden, die Sie als vertraulich eingestuft haben, und um die unbeabsichtigte Freigabe dieser Elemente zu verhindern. Weitere Informationen finden Sie unter [Microsoft 365 Verhinderung von Datenverlust.](../../compliance/endpoint-dlp-learn-about.md)


Im Rahmen Microsoft Managed Desktop enthaltene und verwaltete Features:

 |
 --- | ---
BitLocker Laufwerkverschlüsselung | BitLocker Die Laufwerkverschlüsselung wird verwendet, um alle Systemlaufwerke zu verschlüsseln. Weitere Informationen finden Sie unter [BitLocker Laufwerkverschlüsselung.](/windows/security/information-protection/bitlocker/bitlocker-overview)
Windows Defender System Guard | Schützt die Integrität des Systems beim Start und überprüft, ob die Systemintegrität wirklich aufrechterhalten wurde. Weitere Informationen finden Sie unter [Windows Defender System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows).
Windows Defender Credential Guard | Windows Defender Credential Guard verwendet virtualisierungsbasierte Sicherheit, um geheime Schlüssel zu isolieren, sodass nur privilegierte Systemsoftware darauf zugreifen kann. Weitere Informationen finden Sie unter [Windows Defender System Guard](/windows/security/threat-protection/windows-defender-system-guard/system-guard-how-hardware-based-root-of-trust-helps-protect-windows).
Microsoft Defender für Endpunkt – Endpunkterkennung und -reaktion | Microsoft Managed Desktop Sicherheitsvorgänge reagieren auf Warnungen und ergreifen Maßnahmen, um Bedrohungen mithilfe von Endpunkterkennung und -reaktion zu beheben. Weitere Informationen finden Sie unter [Microsoft Defender für Endpunkt – Endpunkterkennung und -reaktion.](/windows/security/threat-protection/microsoft-defender-atp/overview-endpoint-detection-response)
Microsoft Defender für Endpunkt – Bedrohungsexperten | Microsoft Managed Desktop lässt sich mit Erkenntnissen und Daten von Bedrohungsexperten durch gezielte Angriffsbenachrichtigungen integrieren. Sie müssen zusätzliche Zustimmung geben, bevor dieser Dienst aktiviert ist. Weitere Informationen finden Sie unter [Microsoft Defender für Endpunkt – Bedrohungsexperten.](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)
Microsoft Defender für Endpunkt – Bedrohungs- und Sicherheitsrisikoverwaltung | Erforderlich für die zukünftige Verwendung im Microsoft Managed Desktop Serviceplan. Weitere Informationen finden Sie unter [Microsoft Defender für Endpunkt – Bedrohungs- und Sicherheitsrisikoverwaltung.](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)
Microsoft Defender für Endpunkt – Verringerung der Angriffsfläche | Attack Surface Reduction zielt auf riskante Softwareverhalten ab, die häufig von Angreifern missbraucht werden. Weitere Informationen finden Sie unter [Microsoft Defender für Endpunkt – Attack Surface Reduction.](/windows/security/threat-protection/microsoft-defender-atp/attack-surface-reduction)
Microsoft Defender für Endpunkt – Exploit-Schutz | Schützt vor Schadsoftware, die Exploits verwendet, um Geräte zu infizieren und zu verbreiten, indem automatisch Exploit-Minderungstechniken auf Betriebssystemprozesse und Apps angewendet werden. Weitere Informationen finden Sie unter [Microsoft Defender für Endpunkt – Exploit-Schutz.](/windows/security/threat-protection/microsoft-defender-atp/exploit-protection)
Microsoft Defender für Endpunkt – Netzwerkschutz | Der Netzwerkschutz erweitert den Bereich der Microsoft Defender SmartScreen, um den gesamten ausgehenden HTTP- und HTTPS-Datenverkehr zu blockieren, der versucht, eine Verbindung mit Quellen mit niedriger Zuverlässigkeit herzustellen. Weitere Informationen finden Sie unter [Microsoft Defender für Endpunkt – Netzwerkschutz.](/windows/security/threat-protection/microsoft-defender-atp/network-protection)
Microsoft Defender-Manipulationsschutz | Windows Der Manipulationsschutz wird verwendet, um zu verhindern, dass Sicherheitseinstellungen wie der Virenschutz geändert werden. Weitere Informationen finden Sie unter [Microsoft Defender Tamper Protection](/windows/security/threat-protection/microsoft-defender-antivirus/prevent-changes-to-security-settings-with-tamper-protection).
Microsoft Defender Antivirus Verhaltensbasierter, heuristischer und Echtzeit-Antivirenschutz | Immer auf Datei- und Prozessbedrohungen prüfen, die möglicherweise nicht als Schadsoftware erkannt werden. Weitere Informationen finden Sie unter [Microsoft Defender Antivirus Verhaltensbasierten, heuristischen und Echtzeit-Antivirenschutz.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)
Microsoft Defender Antivirus Über die Cloud bereitgestellter Schutz | Bietet dynamischen, nahezu sofortigen automatisierten Schutz vor neuen und neuen Bedrohungen. Weitere Informationen finden Sie unter Microsoft Defender Antivirus über [die Cloud bereitgestellten Schutz.](/windows/security/threat-protection/microsoft-defender-antivirus/utilize-microsoft-cloud-protection-microsoft-defender-antivirus)
Microsoft Defender "Bei erster Anzeige blockieren" | Stellt die Erkennung und Blockierung neuer Schadsoftware bereit, wenn Windows eine verdächtige oder unbekannte Datei erkennt. Weitere Informationen finden Sie unter ["Microsoft Defender Beim ersten Sichten blockieren".](/windows/security/threat-protection/microsoft-defender-antivirus/configure-block-at-first-sight-microsoft-defender-antivirus)
Möglicherweise unerwünschte Microsoft Defender AV-Anwendungen | Potenziell unerwünschte Anwendungen werden verwendet, um Apps zu blockieren, die dazu führen können, dass Ihr Computer langsam ausgeführt wird, unerwartete Anzeigen anzeigt oder im schlechtesten Fall andere Software installiert, die unerwartet oder unerwünschte sein kann. Weitere Informationen finden Sie unter [Microsoft Defender AV, potenziell unerwünschte Anwendungen.](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
Windows Defender Firewall mit erweiterter Sicherheit | Hostbasierte, bidirektionale Netzwerkdatenverkehrfilterung für ein Gerät, Windows Defender Firewall nicht autorisierten Netzwerkdatenverkehr blockiert, der in das oder aus dem lokalen Gerät fließt. Weitere Informationen finden Sie unter [Windows Defender Firewall mit erweiterter Sicherheit.](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security)
Benutzerkontensteuerung | Die Benutzerkontensteuerung wechselt zum sicheren Desktop, wenn für eine Aufgabe oder Aktion der Administratorkontotypzugriff erforderlich ist. Microsoft Managed Desktop Benutzern bei der Registrierung standardmäßiger Benutzerzugriff zugewiesen wird. Weitere Informationen finden Sie unter [Benutzerkontensteuerung.](/windows/security/identity-protection/user-account-control/how-user-account-control-works)


## <a name="enterprise-mobility--security-e5"></a>Enterprise Mobility + Security E5

 |
 --- | ---
Enterprise Mobility + Security E3<br>Azure Active Directory Premium P2 |    Sie können alle Features von Enterprise Mobility + Security E3 verwenden, um MDM-Geräte zu verwalten. Sie können Azure Active Directory Premium P2 als optionales Feature mit Microsoft Managed Desktop verwenden.
Microsoft Cloud App Security |  Sie können dieses optionale Feature mit Microsoft Managed Desktop verwenden.
Azure Information Protection P2  | Sie können dieses optionale Feature mit Microsoft Managed Desktop verwenden.
