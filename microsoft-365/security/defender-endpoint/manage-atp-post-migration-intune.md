---
title: Verwalten von Microsoft Defender for Endpoint mithilfe von Intune
description: Informationen zum Verwalten von Microsoft Defender for Endpoint mit Intune
keywords: nach der Migration, Verwalten, Betrieb, Wartung, Auslastung, Intune, Microsoft Defender for Endpoint, edr
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
ms.date: 09/22/2020
ms.reviewer: chventou
ms.openlocfilehash: d8396c352e593f9922b11e23119f7d9718eaf752
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934225"
---
# <a name="manage-microsoft-defender-for-endpoint-with-intune"></a>Verwalten von Microsoft Defender for Endpoint mit Intune

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

Es wird empfohlen, [Microsoft Endpoint Manager](https://docs.microsoft.com/mem)zu verwenden, das Microsoft Intune (Intune) umfasst, um die Bedrohungsschutzfunktionen Ihrer Organisation für Geräte (auch als Endpunkte bezeichnet) zu verwalten. [Erfahren Sie mehr über Endpoint Manager](https://docs.microsoft.com/mem/endpoint-manager-overview).

In diesem Artikel wird beschrieben, wie Sie Ihre Microsoft Defender for Endpoint-Einstellungen in Intune finden, und es werden verschiedene Aufgaben aufgeführt, die Sie ausführen können.

## <a name="find-your-microsoft-defender-for-endpoint-settings-in-intune"></a>Suchen Ihrer Microsoft Defender for Endpoint-Einstellungen in Intune

> [!IMPORTANT]
> Sie müssen ein globaler Administrator oder Dienstadministrator in Intune sein, um die in diesem Artikel beschriebenen Einstellungen zu konfigurieren. Weitere Informationen finden Sie unter **[Typen von Administratoren (Intune).](https://docs.microsoft.com/mem/intune/fundamentals/users-add#types-of-administrators)**

1. Wechseln Sie zum Azure-Portal ( [https://portal.azure.com](https://portal.azure.com) ) und melden Sie sich an.

2. Wählen **Sie unter Azure Services** intune **aus.**

3. Wählen Sie im Navigationsbereich auf der linken Seite Gerätekonfiguration **aus,** und wählen Sie dann unter **Verwalten** die Option **Profile aus.**

4. Wählen Sie ein vorhandenes Profil aus, oder erstellen Sie ein neues Profil.

> [!TIP]
> Benötigen Sie Hilfe? Weitere **[Informationen finden Sie unter Using Microsoft Defender for Endpoint with Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection#example-of-using-microsoft-defender-atp-with-intune)**.  

## <a name="configure-microsoft-defender-for-endpoint-with-intune"></a>Konfigurieren von Microsoft Defender for Endpoint mit Intune

In der folgenden Tabelle sind verschiedene Aufgaben aufgeführt, die Sie zum Konfigurieren von Microsoft Defender for Endpoint mit Intune ausführen können. Sie müssen nicht alles gleichzeitig konfigurieren. Wählen Sie einen Vorgang aus, lesen Sie die entsprechenden Ressourcen, und fahren Sie dann fort.

|Aufgabe  |Ressourcen mit mehr Informationen  |
|---------|---------|
|**Verwalten der Geräte Ihrer Organisation mithilfe von Intune** zum Schutz der auf ihnen gespeicherten Geräte und Daten     |[Schützen von Geräten mit Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/device-protect)         |
|**Integrieren von Microsoft Defender for Endpoint in Intune** als Mobile Threat Defense-Lösung <br/>*(für Android-Geräte und Geräte, auf Windows 10 oder höher ausgeführt werden)*   |[Erzwingen der Compliance für Microsoft Defender for Endpoint mit bedingten Zugriff in Intune](https://docs.microsoft.com/mem/intune/protect/advanced-threat-protection)         |
|**Verwenden des bedingten Zugriffs** zum Steuern der Geräte und Apps, die eine Verbindung mit Ihren E-Mail- und Unternehmensressourcen herstellen können |[Konfigurieren des bedingten Zugriffs in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-conditional-access) |
|**Konfigurieren Microsoft Defender Antivirus Einstellungen mithilfe** des Richtlinienkonfigurationsdienstanbieters ([Policy CSP](https://docs.microsoft.com/windows/client-management/mdm/policy-configuration-service-provider)) |[Geräteeinschränkungen: Microsoft Defender Antivirus](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus)<br/><br/>[Richtlinien-CSP – Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender)  | 
|**Geben Sie bei Bedarf Ausschlüsse für Microsoft Defender Antivirus** <br/><br/>*Im Allgemeinen sollten Sie keine Ausschlüsse anwenden müssen. Microsoft Defender Antivirus umfasst eine Reihe von automatischen Ausschlüssen, die auf bekannten Betriebssystemverhalten und typischen Verwaltungsdateien basieren, z. B. solche, die in der Unternehmensverwaltung, datenbankverwaltung und anderen Unternehmensszenarien verwendet werden.* |[Virenscanempfehlungen für Enterprise Computer, auf denen derzeit unterstützte Versionen von Windows](https://support.microsoft.com/help/822158/virus-scanning-recommendations-for-enterprise-computers)<br/><br/>[Geräteeinschränkungen: Microsoft Defender Antivirus Ausschlüsse für Windows 10 Geräte](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-antivirus-exclusions) <br/><br/>[Konfigurieren Microsoft Defender Antivirus Ausschlüsse für Windows Server 2016 oder 2019](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-server-exclusions-microsoft-defender-antivirus)|
|**Konfigurieren Von Regeln zur Reduzierung** der Angriffsfläche für Softwareverhalten, die häufig von Angreifern missbraucht werden<br/><br/>*Konfigurieren Sie zunächst ihre [](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/audit-windows-defender) Regeln zur Reduzierung der Angriffsfläche im Überwachungsmodus (für mindestens eine Woche und bis zu zwei Monate). Sie können den Status mithilfe Power BI überwachen ([unsere](https://github.com/microsoft/MDATP-PowerBI-Templates/tree/master/Attack%20Surface%20Reduction%20rules)Vorlage erhalten ) und diese Regeln dann auf den aktiven Modus festlegen, wenn Sie bereit sind.* |[Überwachungsmodus in Microsoft Defender for Endpoint ](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/audit-windows-defender)<br/><br/>[Endpunktschutz: Attack Surface Reduction](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10?toc=/intune/configuration/toc.json&bc=/intune/configuration/breadcrumb/toc.json#attack-surface-reduction)<br/><br/>[Weitere Informationen zu Regeln zur Reduzierung der Angriffsfläche](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)<br/><br/>[Tech Community Blogbeitrag: Demystifying attack surface reduction rules - Part 1](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/demystifying-attack-surface-reduction-rules-part-1/ba-p/1306420) |
|**Konfigurieren Der Netzwerkfilterung,** um ausgehende Verbindungen von jeder App zu IP-Adressen oder Domänen mit niedriger Reputation zu blockieren  <br/><br/>*Netzwerkfilterung wird auch als [Netzwerkschutz bezeichnet.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/network-protection)*<br/><br/>*Stellen Sie sicher, Windows 10 auf den Geräten die neuesten Updates für die [Antischalwareplattform installiert](https://support.microsoft.com/help/4052623/update-for-microsoft-defender-antimalware-platform) sind.*|[Endpunktschutz: Netzwerkfilterung](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#network-filtering)<br/><br/>[Überprüfen von Netzwerkschutzereignissen in Windows Ereignisanzeige](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/evaluate-network-protection#review-network-protection-events-in-windows-event-viewer) |
|**Konfigurieren des kontrollierten Ordnerzugriffs** zum Schutz vor Ransomware <br/><br/>*[Der kontrollierte Ordnerzugriff](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/controlled-folders) wird auch als Antiransomwareschutz bezeichnet.*  |[Endpunktschutz: Kontrollierter Ordnerzugriff](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#controlled-folder-access) <br/><br/>[Aktivieren des kontrollierten Ordnerzugriffs in Intune](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-controlled-folders#intune)  |
|**Konfigurieren des Exploitschutzes** zum Schutz der Geräte Ihrer Organisation vor Schadsoftware, die Exploits verwendet, um andere Geräte zu verbreiten und zu infizieren <br/><br/> *[Exploit-Schutz](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/exploit-protection) wird auch als Exploit Guard bezeichnet.* |[Endpunktschutz: Microsoft Defender Exploit Guard](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-exploit-guard) <br/><br/>[Aktivieren des Exploitschutzes in Intune](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/enable-exploit-protection#intune) |
|**Konfigurieren Microsoft Defender SmartScreen,** um sich vor schädlichen Websites und Dateien im Internet zu schützen. <br/><br/> *Microsoft Edge sollten auf den Geräten Ihrer Organisation installiert werden. Konfigurieren Sie exploit protection, um den Schutz in Google Chrome- und FireFox-Browsern zu gewährleisten.*  |[Microsoft Defender SmartScreen](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-overview) <br/><br/>[Geräteeinschränkungen: Microsoft Defender SmartScreen](https://docs.microsoft.com/mem/intune/configuration/device-restrictions-windows-10#microsoft-defender-smartscreen)<br/><br/>[Richtlinieneinstellungen für die Verwaltung von SmartScreen in Intune](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-smartscreen/microsoft-defender-smartscreen-available-settings#mdm-settings)  |
|**Konfigurieren Microsoft Defender Firewall,** um nicht autorisierten Netzwerkdatenverkehr zu blockieren, der auf oder aus den Geräten Ihrer Organisation fließt  |[Endpunktschutz: Microsoft Defender Firewall](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-firewall) <br/><br/> [Microsoft Defender Firewall mit erweiterter Sicherheit](https://docs.microsoft.com/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security) |
|**Konfigurieren von Verschlüsselung und BitLocker,** um Informationen auf den Geräten Ihrer Organisation zu schützen, auf Windows |[Endpunktschutz: Windows Verschlüsselung](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#windows-encryption)<br/><br/>[BitLocker für Windows 10 Geräte](https://docs.microsoft.com/windows/security/information-protection/bitlocker/bitlocker-overview) |
|**Konfigurieren von Microsoft Defender Credential Guard** zum Schutz vor Angriffen auf den Diebstahl von Anmeldeinformationen |Informationen Windows 10, Windows Server 2016 und Windows Server 2019 finden Sie unter [Endpunktschutz: Microsoft Defender Credential Guard](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-credential-guard) <br/><br/>Informationen zu Windows 7 SP1, Windows Server 2008 R2 SP1, Windows 8.1 und Windows Server 2012 R2 finden Sie unter Minderung von [Pass-the-Hash(PtH)-Angriffen](https://www.microsoft.com/download/details.aspx?id=36036) und anderen Diebstahl von Anmeldeinformationen, Versionen 1 und 2  |
|**Konfigurieren der Microsoft Defender-Anwendungssteuerung,** um zu wählen, ob Apps auf den Geräten Ihrer Organisation überwacht oder vertrauenswürdig sind <br/><br/>*Microsoft Defender Application Control wird auch als [AppLocker bezeichnet.](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/applocker/applocker-overview)*|[Bereitstellen von Microsoft Defender Application Control-Richtlinien mithilfe von Microsoft Intune](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-application-control/deploy-windows-defender-application-control-policies-using-intune)<br/><br/>[Endpunktschutz: Microsoft Defender Application Control](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-application-control)<br/><br/>[AppLocker CSP](https://docs.microsoft.com/windows/client-management/mdm/applocker-csp)|
|**Konfigurieren der Gerätesteuerung und des Zugriffs auf** USB-Peripheriegeräte, um zu verhindern, dass Bedrohungen in nicht autorisierten Peripheriegeräten Ihre Geräte kompromittieren |[Steuern von USB-Geräten und anderen Wechselmedien mithilfe von Microsoft Defender für Endpoint und Intune](https://docs.microsoft.com/windows/security/threat-protection/device-control/control-usb-devices-using-intune)  |

## <a name="configure-your-microsoft-defender-security-center"></a>Konfigurieren der Microsoft Defender Security Center

Wenn Sie dies noch nicht getan haben, konfigurieren Sie Ihre **Microsoft Defender Security Center** ( ), um Warnungen anzuzeigen, Funktionen zum Schutz vor Bedrohungen zu konfigurieren und detaillierte Informationen über die allgemeine Sicherheitslage Ihrer [https://securitycenter.windows.com](https://securitycenter.windows.com) Organisation anzuzeigen. 

Sie können auch konfigurieren, ob und welche Features Endbenutzer in der Microsoft Defender Security Center.

- [Übersicht über die Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/use)

- [Endpunktschutz: Microsoft Defender Security Center](https://docs.microsoft.com/mem/intune/protect/endpoint-protection-windows-10#microsoft-defender-security-center)

## <a name="next-steps"></a>Nächste Schritte

- [Hier erhalten Sie eine Übersicht Bedrohungs- und Sicherheitsrisikomanagement](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/next-gen-threat-and-vuln-mgt)

- [Besuchen Sie das Microsoft Defender Security Center security operations dashboard](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard)
