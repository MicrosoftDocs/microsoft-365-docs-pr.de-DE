---
title: Wechseln zu Microsoft Defender for Endpoint – Onboard
description: Dies ist Phase 3, Onboard, für die Migration von einer Nicht-Microsoft-Lösung zu Microsoft Defender for Endpoint.
keywords: Migration, windows defender advanced threat protection, atp, edr
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
- m365solution-migratetomdatp
ms.custom: migrationguides
ms.topic: article
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: 2916f113f3c26a9c33c6da1f235a9b143667b9cf
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068472"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a>Wechseln zu Microsoft Defender for Endpoint – Phase 3: Onboard

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

| [![Phase 1: Prepare3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)<br/>[Phase 1: Vorbereiten](switch-to-microsoft-defender-prepare.md) | [![Phase 2: Einrichten](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)<br/>[Phase 2: Einrichten](switch-to-microsoft-defender-setup.md) | ![Phase 3: Onboarding](images/phase-diagrams/onboard.png)<br/>Phase 3: Onboarding |
|--|--|--|
|| |*Sie sind hier!* |


**Willkommen bei Phase 3 des [Wechsels zu Microsoft Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)**. Diese Migrationsphase umfasst die folgenden Schritte:

1. [Onboarding von Geräten in Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).
2. [Führen Sie einen Erkennungstest aus.](#run-a-detection-test)
3. [Deinstallieren Sie Ihre Nicht-Microsoft-Lösung.](#uninstall-your-non-microsoft-solution)
4. [Stellen Sie sicher, dass sich Microsoft Defender for Endpoint im aktiven Modus befindet.](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a>Onboarding von Geräten in Microsoft Defender for Endpoint

1. Wechseln Sie zum Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ) und melden Sie sich an.
2. Wählen **Sie Einstellungen**  >  **Geräteverwaltung**  >  **Onboarding aus.** 
3. Wählen Sie **in der Liste Betriebssystem zum Starten des Onboardingprozesses** auswählen ein Betriebssystem aus. 
4. Wählen **Sie unter Bereitstellungsmethode** eine Option aus. Folgen Sie den Links und Aufforderungen zum Onboarding der Geräte Ihrer Organisation. Benötigen Sie Hilfe? Weitere [Informationen finden Sie unter Onboarding-Methoden](#onboarding-methods) (in diesem Artikel).

### <a name="onboarding-methods"></a>Onboardingmethoden
 
Die Bereitstellungsmethoden variieren, je nachdem, welches Betriebssystem ausgewählt ist. Weitere Informationen zum Onboarding finden Sie in den ressourcen, die in der folgenden Tabelle aufgeführt sind.

|Betriebssystem  |Methode  |
|---------|---------|
|Windows 10     |- [Gruppenrichtlinie](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)<br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)<br/>- [Verwaltung mobiler Geräte (Intune)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)<br/>- [Lokales Skript](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/><br/>**HINWEIS:** Ein lokales Skript eignet sich für einen Nachweis des Konzepts, sollte jedoch nicht für die Produktionsbereitstellung verwendet werden. Für eine Produktionsbereitstellung wird die Verwendung von Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Intune empfohlen.         |
|- Windows 8.1 Enterprise <br/>- Windows 8.1 Pro <br/>- Windows 7 SP1 Enterprise <br/>- Windows 7 SP1 Pro     | [Microsoft Monitoring Agent](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-atp)<br/><br/>**HINWEIS:** Microsoft Monitoring Agent ist jetzt Azure Log Analytics Agent. Weitere Informationen finden Sie unter [Log Analytics Agent Overview](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).        |
|– Windows Server 2019 und höher <br/>- Windows Server 2019 Core Edition <br/>– Windows Server, Version 1803 und höher |- [Lokales Skript](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script) <br/>- [Gruppenrichtlinie](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp) <br/>- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm) <br/>- [System Center Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager) <br/>- [VDI-Onboardingskripts für nicht persistente Geräte](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi) <br/><br/>**HINWEIS:** Ein lokales Skript eignet sich für einen Nachweis des Konzepts, sollte jedoch nicht für die Produktionsbereitstellung verwendet werden. Für eine Produktionsbereitstellung wird die Verwendung von Gruppenrichtlinien, Microsoft Endpoint Configuration Manager oder Intune empfohlen.    |
|- Windows Server 2016 <br/>- Windows Server 2012 R2 <br/>- Windows Server 2008 R2 SP1  |- [Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)<br/>- [Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp) |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)<br/><br/>iOS<br/><br/>Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS oder höher LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |[Onboarding von Nicht-Windows-Geräten](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-non-windows)  |

## <a name="run-a-detection-test"></a>Ausführen eines Erkennungstests

Um sicherzustellen, dass Ihre integrierten Geräte ordnungsgemäß mit Microsoft Defender for Endpoint verbunden sind, können Sie einen Erkennungstest ausführen.

|Betriebssystem  |Richtlinien  |
|---------|---------|
|- Windows 10 <br/>- Windows Server 2019 <br/>- Windows Server, Version 1803 <br/>- Windows Server 2016 <br/>- Windows Server 2012 R2     |Weitere [Informationen finden Sie unter Ausführen eines Erkennungstests.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test) <br/><br/>Besuchen Sie die Microsoft Defender for Endpoint-Demoszenarien-Website ( ) und testen Sie eines [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) oder mehrere der Szenarien. Testen Sie beispielsweise das **Demoszenario für den Cloud-zugestellten** Schutz.         |
|macOS<br/>- 10.15 (Catalina)<br/>- 10.14 (Mojave)<br/>- 10.13 (High Sierra)     |Laden Sie die HEIMWERKER-App unter herunter und verwenden Sie [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) sie. <br/><br/>Weitere Informationen finden Sie unter [Microsoft Defender for Endpoint für Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).        |
|Linux:<br/>- RHEL 7.2+<br/>- CentOS Linux 7.2+<br/>- Ubuntu 16 LTS oder höher LTS<br/>- SLES 12+<br/>- Debian 9+<br/>- Oracle Linux 7.2 |1. Führen Sie den folgenden Befehl aus, und suchen Sie nach einem Ergebnis von **1:** <br/>`mdatp health --field real_time_protection_enabled`. <br/><br/>2. Öffnen Sie ein Terminalfenster, und führen Sie den folgenden Befehl aus: <br/>`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`. <br/><br/>3. Führen Sie den folgenden Befehl aus, um erkannte Bedrohungen auflisten: <br/>`mdatp threat list`. <br/><br/>Weitere Informationen finden Sie unter [Microsoft Defender ATP für Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux). |

## <a name="uninstall-your-non-microsoft-solution"></a>Deinstallieren Ihrer Nicht-Microsoft-Lösung

Nachdem Sie die Geräte Ihrer Organisation in Microsoft Defender for Endpoint integrierte haben, besteht der nächste Schritt in der Deinstallation Ihrer Nicht-Microsoft-Endpunktschutzlösung.

Um Hilfe bei diesem Schritt zu erhalten, erreichen Sie das technische Supportteam Ihres Lösungsanbieters.

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a>Stellen Sie sicher, dass sich Microsoft Defender for Endpoint im aktiven Modus befindet

Nachdem Sie Ihre Nicht-Microsoft-Lösung zum Schutz von Endpunkten deinstalliert haben, müssen Sie im nächsten Schritt sicherstellen, dass Microsoft Defender Antivirus und Microsoft Defender for Endpoint aktiviert und im aktiven Modus sind.

Besuchen Sie dazu die Microsoft Defender for Endpoint-Demoszenarien-Website ( [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ). Testen Sie mindestens eines der Demoszenarien auf dieser Seite, einschließlich mindestens der folgenden:
- In der Cloud zugestellter Schutz
- Potenziell unerwünschte Anwendungen (PUA)
- Network Protection (NP)

> [!IMPORTANT]
> Wenn Sie Windows Server 2016 verwenden, müssen Sie Microsoft Defender Antivirus möglicherweise manuell starten. Dazu verwenden Sie das PowerShell-Cmdlet `mpcmdrun.exe -wdenable` auf dem Gerät.

## <a name="next-steps"></a>Nächste Schritte

**Herzlichen Glückwunsch!** Sie haben die Migration [zu Microsoft Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)abgeschlossen! 

- [Besuchen Sie Ihr Sicherheitsbetriebsdashboard](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard) im Microsoft Defender Security Center ( [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ). 
- [Verwalten von Microsoft Defender for Endpoint, post migration](manage-atp-post-migration.md).
