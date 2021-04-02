---
title: Erleben von Microsoft Defender ATP durch simulierte Angriffe
description: Führen Sie die bereitgestellten Simulationen des Angriffsszenarios aus, um zu erfahren, wie Microsoft Defender ATP Verstöße erkennen, untersuchen und darauf reagieren kann.
keywords: wdatp, test, scenario, attack, simulation, simulated, diy, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 11/20/2018
ms.technology: mde
ms.openlocfilehash: b3fb862ac6e845ed4a3f5b72bae902f00c125b53
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498302"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>Erleben von Microsoft Defender for Endpoint durch simulierte Angriffe 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- Erfahren Sie mehr über die neuesten Verbesserungen in Microsoft Defender ATP: [Was ist neu in Defender for Endpoint?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
>- Defender for Endpoint hat in der kürzlichen MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen gezeigt. Read: [Insights from the MITRE ATT&CK-based evaluation](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/).

Möglicherweise möchten Sie Defender for Endpoint nutzen, bevor Sie mehr als ein paar Geräte in den Dienst integrieren. Dazu können Sie kontrollierte Angriffssimulationen auf einigen Testgeräten ausführen. Nachdem Sie die simulierten Angriffe ausgeführt haben, können Sie überprüfen, wie Defender for Endpoint schädliche Aktivitäten aufgreift, und untersuchen, wie eine effiziente Reaktion ermöglicht wird.

## <a name="before-you-begin"></a>Vorbereitung

Zum Ausführen einer der bereitgestellten Simulationen benötigen Sie mindestens [ein integriertes Gerät.](onboard-configure.md) 

Lesen Sie das exemplarische Vorgehensweisendokument, das für jedes Angriffsszenario bereitgestellt wird. Jedes Dokument enthält Betriebssystem- und Anwendungsanforderungen sowie detaillierte Anweisungen, die für ein Angriffsszenario spezifisch sind.

## <a name="run-a-simulation"></a>Ausführen einer Simulation

1. Wählen **Sie** in & Hilfesimulationen die verfügbaren  >  **Angriffsszenarien** aus, die Sie simulieren möchten:

   - **Szenario 1: Dokument fällt hinter die Hintertür** – simuliert die Zustellung eines sozial entwickelten Lockure-Dokuments. Das Dokument startet eine speziell entworfene Backdoor, die Angreifern die Kontrolle gibt.

   - **Szenario 2: PowerShell-Skript** bei dateilosem Angriff – simuliert einen dateilosen Angriff, der auf PowerShell basiert, und zeigt die Reduzierung der Angriffsfläche und die Erkennung bösartiger Speicheraktivitäten durch Gerätelernen an.
    
   - **Szenario 3: Automatisierte** Reaktion auf Sicherheitsvorfälle – löst eine automatisierte Untersuchung aus, die automatisch nach Verletzungsartefakten fahnen und diese behoben, um Ihre Kapazität für die Reaktion auf Vorfälle zu skalieren.

2. Laden Sie das entsprechende exemplarische Vorgehensweisendokument herunter, das im ausgewählten Szenario bereitgestellt wird, und lesen Sie es.

3. Laden Sie die Simulationsdatei herunter, oder kopieren Sie das Simulationsskript, indem Sie zu  >  **Hilfesimulationen & navigieren.** Sie können die Datei oder das Skript auf dem Testgerät herunterladen, es ist jedoch nicht zwingend erforderlich.

4. Führen Sie die Simulationsdatei oder das Skript auf dem Testgerät wie im exemplarischen Vorgehensweisendokument angewiesen aus.

> [!NOTE]
> Simulationsdateien oder Skripts imitieren Angriffsaktivitäten, sind aber tatsächlich gutartig und schaden dem Testgerät nicht.
> 
> 
> Möchten Sie Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a>Verwandte Themen

- [Onboarding von Geräten](onboard-configure.md)
- [Onboarding von Windows 10-Geräten](configure-endpoints.md)
