---
title: Verwalten von Microsoft Defender für Endpunkt mit Intune
description: Erfahren Sie, wie Sie Microsoft Defender für Endpunkt mit Intune verwalten
keywords: nach der Migration, verwalten, Vorgänge, Wartung, Auslastung, Intune, Microsoft Defender für Endpunkt, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
ms.topic: article
ms.date: 06/11/2021
ms.reviewer: chventou
ms.openlocfilehash: ccbcbcb71d60dadf24b6f94bab126a1f1ca1c322
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908281"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Verwalten von Microsoft Defender für Endpunkt mit Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Es wird empfohlen, [Microsoft Endpoint Manager](/mem)zu verwenden, das Microsoft Intune (Intune) zum Verwalten der Bedrohungsschutzfeatures Ihrer Organisation für Geräte (auch als Endpunkte bezeichnet) umfasst. [Weitere Informationen zu Endpoint Manager](/mem/endpoint-manager-overview).

In diesem Artikel wird beschrieben, wie Sie Ihre Microsoft Defender für Endpunkt-Einstellungen in Intune finden und verschiedene Aufgaben auflisten, die Sie ausführen können.

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Suchen Ihrer Microsoft Defender für Endpunkt-Einstellungen in Intune

> [!IMPORTANT]
> Sie müssen ein globaler Administrator oder Dienstadministrator in Intune sein, um die in diesem Artikel beschriebenen Einstellungen zu konfigurieren. Weitere Informationen finden Sie unter **[Typen von Administratoren (Intune).](/mem/intune/fundamentals/users-add#types-of-administrators)**

1. Wechseln Sie zum Azure-Portal ( [https://portal.azure.com](https://portal.azure.com) ) und melden Sie sich an.

2. Wählen Sie unter **Azure Services** **Intune** aus.

3. Wählen Sie im Navigationsbereich auf der linken Seite die **Gerätekonfiguration** und dann unter **"Verwalten"** die Option **"Profile" aus.**

4. Wählen Sie ein vorhandenes Profil aus, oder erstellen Sie ein neues Profil.

> [!TIP]
> Benötigen Sie Hilfe? Weitere Informationen finden Sie **[unter Verwenden von Microsoft Defender für Endpunkt mit Intune.](/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**  

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Konfigurieren von Microsoft Defender für Endpunkt mit Intune

In der folgenden Tabelle sind verschiedene Aufgaben aufgeführt, die Sie ausführen können, um Microsoft Defender für Endpunkt mit Intune zu konfigurieren. Sie müssen nicht alles auf einmal konfigurieren. Wählen Sie eine Aufgabe aus, lesen Sie die entsprechenden Ressourcen, und fahren Sie dann fort.

|Aufgabe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|**Verwalten der Geräte Ihrer Organisation mit Intune** zum Schutz dieser Geräte und daten, die auf ihnen gespeichert sind     |[Schützen von Geräten mit Microsoft Intune](/mem/intune/protect/device-protect)         |
|**Integrieren von Microsoft Defender für Endpunkt in Intune** als Mobile Threat Defense-Lösung <br/>*(für Android-Geräte und -Geräte, die Windows 10 oder höher ausgeführt werden)*   |[Erzwingen der Compliance für Microsoft Defender für Endpunkt mit bedingtem Zugriff in Intune](/mem/intune/protect/advanced-threat-protection)         |
|**Verwenden des bedingten Zugriffs** zum Steuern der Geräte und Apps, die eine Verbindung zu Ihren E-Mails und Unternehmensressourcen herstellen können |[Konfigurieren des bedingten Zugriffs in Microsoft Defender für Endpunkt](/microsoft-365/security/defender-endpoint/configure-conditional-access) |
|**Konfigurieren Microsoft Defender Antivirus Einstellungen** mithilfe des Richtlinienkonfigurationsdienstanbieters ([Policy CSP](/windows/client-management/mdm/policy-configuration-service-provider)) |[Geräteeinschränkungen: Microsoft Defender Antivirus](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)<br/><br/>[Richtlinien-CSP – Microsoft Defender für Endpunkt](/windows/client-management/mdm/policy-csp-defender)  | 
|**Geben Sie ggf. Ausschlüsse für Microsoft Defender Antivirus** <br/><br/>*Im Allgemeinen sollten Sie keine Ausschlüsse anwenden müssen. Microsoft Defender Antivirus umfasst eine Reihe automatischer Ausschlüsse, die auf bekannten Betriebssystemverhaltensweisen und typischen Verwaltungsdateien basieren, z. B. solche, die in der Unternehmensverwaltung, datenbankverwaltung und anderen Unternehmensszenarien verwendet werden.* |[Empfehlungen zur Virenüberprüfung für Enterprise Computer, auf denen derzeit unterstützte Versionen von Windows ausgeführt werden](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers)<br/><br/>[Geräteeinschränkungen: Microsoft Defender Antivirus Ausschlüsse für Windows 10 Geräte](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/>[Konfigurieren Microsoft Defender Antivirus Ausschlüsse für Windows Server 2016 oder 2019](/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|Konfigurieren Sie Die Regeln zur Verringerung der **Angriffsfläche** so, dass sie auf Softwareverhalten abzielen, die häufig von Angreifern missbraucht werden<br/><br/>*Konfigurieren Sie die Regeln zur Verringerung der Angriffsfläche zunächst im [Überwachungsmodus](/microsoft-365/security/defender-endpoint/audit-windows-defender) (für mindestens eine Woche und bis zu zwei Monate). Sie können den Status mithilfe Power BI überwachen ([unsere Vorlage abrufen)](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)und diese Regeln dann auf den aktiven Modus festlegen, wenn Sie bereit sind.* |[Überwachungsmodus in Microsoft Defender für Endpunkt ](/microsoft-365/security/defender-endpoint/audit-windows-defender)<br/><br/>[Endpunktschutz: Attack Surface Reduction](/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction)<br/><br/>[Weitere Informationen zu Regeln zur Verringerung der Angriffsfläche](/microsoft-365/security/defender-endpoint/attack-surface-reduction)<br/><br/>[Tech Community Blogbeitrag: Demystifying attack surface reduction rules - Part 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) |
|**Konfigurieren Sie Ihre Netzwerkfilterung** so, dass ausgehende Verbindungen von jeder App zu IP-Adressen oder Domänen mit niedriger Zuverlässigkeit blockiert werden.  <br/><br/>*Die Netzwerkfilterung wird auch als [Netzwerkschutz](/microsoft-365/security/defender-endpoint/network-protection)bezeichnet.*<br/><br/>*Stellen Sie sicher, dass auf Windows 10 Geräten die neuesten [Antischadsoftware-Plattformupdates](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform) installiert sind.*|[Endpunktschutz: Netzwerkfilterung](/mem/intune/protect/endpoint-protection-windows-10#network-filtering)<br/><br/>[Überprüfen von Netzwerkschutzereignissen in Windows Ereignisanzeige](/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer) |
|**Konfigurieren des kontrollierten Ordnerzugriffs** zum Schutz vor Ransomware <br/><br/>*[Der kontrollierte Ordnerzugriff](/microsoft-365/security/defender-endpoint/controlled-folders) wird auch als Antiransomware-Schutz bezeichnet.*  |[Endpunktschutz: Kontrollierter Ordnerzugriff](/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Aktivieren des kontrollierten Ordnerzugriffs in Intune](/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)  |
|**Konfigurieren des Exploit-Schutzes,** um die Geräte Ihrer Organisation vor Schadsoftware zu schützen, die Exploits verwendet, um andere Geräte zu verbreiten und zu infizieren <br/><br/> *[Exploit-Schutz](/microsoft-365/security/defender-endpoint/exploit-protection) wird auch als Exploit Guard bezeichnet.* |[Endpunktschutz: Microsoft Defender Exploit Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/>[Aktivieren des Exploit-Schutzes in Intune](/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune) |
|**Konfigurieren Sie Microsoft Defender SmartScreen** zum Schutz vor schädlichen Websites und Dateien im Internet. <br/><br/> *Microsoft Edge sollten auf den Geräten Ihrer Organisation installiert werden. Konfigurieren Sie den Exploit-Schutz für Google Chrome- und FireFirefox-Browser, um Schutz zu gewährleisten.*  |[Microsoft Defender SmartScreen](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/>[Geräteeinschränkungen: Microsoft Defender SmartScreen](/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen)<br/><br/>[Richtlinieneinstellungen für die Verwaltung von SmartScreen in Intune](/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)  |
|**Konfigurieren sie Microsoft Defender Firewall,** um nicht autorisierten Netzwerkdatenverkehr zu blockieren, der in die Geräte Ihrer Organisation oder aus ihr heraus fließt.  |[Endpunktschutz: Microsoft Defender Firewall](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [Microsoft Defender Firewall mit erweiterter Sicherheit](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) |
|**Konfigurieren von Verschlüsselung und BitLocker** zum Schutz von Informationen auf den Geräten Ihrer Organisation, auf denen Windows |[Endpunktschutz: Windows Verschlüsselung](/mem/intune/protect/endpoint-protection-windows-10#windows-encryption)<br/><br/>[BitLocker für Windows 10 Geräte](/windows/security/information-protection/bitlocker/bitlocker-overview) |
|**Konfigurieren von Microsoft Defender Credential Guard** zum Schutz vor Angriffen durch Diebstahl von Anmeldeinformationen |Informationen zu Windows 10, Windows Server 2016 und Windows Server 2019 finden Sie unter [Endpunktschutz: Microsoft Defender Credential Guard](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/>Informationen zu Windows 7 SP1, Windows Server 2008 R2 SP1, Windows 8.1 und Windows Server 2012 R2 finden Sie unter ["Minimieren von Pass-the-Hash(PtH)-Angriffen und anderen Diebstahl von Anmeldeinformationen", Version 1 und 2.](https://www.microsoft.com/download/details.aspx?id=36036)  |
|**Konfigurieren der Microsoft Defender-Anwendungssteuerung,** um auszuwählen, ob Apps auf den Geräten Ihrer Organisation überwacht oder als vertrauenswürdig eingestuft werden sollen <br/><br/>*Microsoft Defender Application Control wird auch als [AppLocker](/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)bezeichnet.*|[Bereitstellen von Richtlinien für die Microsoft Defender-Anwendungssteuerung mithilfe von Microsoft Intune](/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune)<br/><br/>[Endpunktschutz: Microsoft Defender-Anwendungssteuerung](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control)<br/><br/>[AppLocker-Konfigurationsdienstanbieter](/windows/client-management/mdm/applocker-csp)|
|**Konfigurieren der Gerätesteuerung und des Zugriffs auf USB-Peripheriegeräte,** um zu verhindern, dass Bedrohungen in nicht autorisierten Peripheriegeräten Ihre Geräte beeinträchtigen |[Steuern von USB-Geräten und anderen Wechselmedien mit Microsoft Defender für Endpunkt und Intune](/windows/security/threat-protection/device-control/control-usb-devices-using-intune)  |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurieren Ihrer Microsoft Defender Security Center

Wenn sie dies noch nicht getan haben, konfigurieren Sie Ihr Microsoft 365 Defender-Portal so, dass Warnungen angezeigt werden, Bedrohungsschutzfeatures konfiguriert und detaillierte Informationen zum allgemeinen Sicherheitsstatus Ihrer Organisation angezeigt werden. Siehe [Microsoft Defender Security Center](microsoft-defender-security-center.md). Sie können auch konfigurieren, ob und welche Features Endbenutzern im Microsoft 365 Defender-Portal angezeigt werden.

- [Übersicht über die Microsoft Defender Security Center](/microsoft-365/security/defender-endpoint/use)

- [Endpunktschutz: Microsoft Defender Security Center](/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Nächste Schritte

- [Übersicht über Bedrohungs- und Sicherheitsrisikomanagement](/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besuchen Sie das Dashboard für Microsoft Defender Security Center Sicherheitsvorgänge.](/microsoft-365/security/defender-endpoint/security-operations-dashboard)
