---
title: Microsoft Defender für Endpunkt durch simulierte Angriffe erleben
description: Führen Sie die bereitgestellten Angriffsszenariosimulationen aus, um zu erfahren, wie Microsoft Defender für Endpunkt Verstöße erkennen, untersuchen und darauf reagieren kann.
keywords: Test, Szenario, Angriff, Simulation, simuliert, Auslauf, Microsoft Defender für Endpunkt
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
ms.openlocfilehash: 9a56167f0025ec42f4fd441886f83026c1bf23d6
ms.sourcegitcommit: 0d1b065c94125b495e9886200f7918de3bda40b3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/08/2021
ms.locfileid: "53339538"
---
# <a name="experience-microsoft-defender-for-endpoint-through-simulated-attacks"></a>Microsoft Defender für Endpunkt durch simulierte Angriffe erleben 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-abovefoldlink)

>[!TIP]
>- Erfahren Sie mehr über die neuesten Verbesserungen in Microsoft Defender für Endpunkt: [Was ist neu in Defender für Endpunkt?](https://cloudblogs.microsoft.com/microsoftsecure/2018/11/15/whats-new-in-windows-defender-atp/).
>- Defender für Endpunkt hat in der letzten MITRE-Evaluierung branchenführende Optik- und Erkennungsfunktionen demonstriert. Lesen Sie: [Insights aus der MITRE ATT&CK-basierten Auswertung.](https://cloudblogs.microsoft.com/microsoftsecure/2018/12/03/insights-from-the-mitre-attack-based-evaluation-of-windows-defender-atp/)

Möglicherweise möchten Sie Defender für Endpunkt testen, bevor Sie mehr als ein paar Geräte in den Dienst integrieren. Dazu können Sie kontrollierte Angriffssimulationen auf einigen Testgeräten ausführen. Nachdem Sie die simulierten Angriffe ausgeführt haben, können Sie überprüfen, wie Defender für Endpunkt bösartige Aktivitäten aufdecken und untersuchen, wie es eine effiziente Reaktion ermöglicht.

## <a name="before-you-begin"></a>Bevor Sie beginnen

Zum Ausführen einer der bereitgestellten Simulationen benötigen Sie mindestens [ein integriertes Gerät.](onboard-configure.md) 

Lesen Sie das exemplarische Vorgehensweisendokument, das für jedes Angriffsszenario bereitgestellt wird. Jedes Dokument enthält Betriebssystem- und Anwendungsanforderungen sowie detaillierte Anweisungen, die für ein Angriffsszenario spezifisch sind.

## <a name="run-a-simulation"></a>Ausführen einer Simulation

1. Wählen Sie in Lernprogrammen zur  >  **Endpunktauswertung &**  >  **Lernprogrammen & Simulationen** aus, welche der verfügbaren Angriffsszenarien Sie simulieren möchten:

   - **Szenario 1: Dokument fällt Hintertür ab** – simuliert die Bereitstellung eines Social Engineering-Lockdokuments. Das Dokument startet eine speziell gestaltete Hintertür, die Angreifern die Kontrolle gibt.

   - **Szenario 2: PowerShell-Skript bei dateilosen Angriffen** – simuliert einen dateilosen Angriff, der auf PowerShell basiert, die Reduzierung der Angriffsfläche und die Erkennung bösartiger Speicheraktivitäten durch Geräte.
    
   - **Szenario 3: Automatisierte Reaktion auf Sicherheitsvorfälle** – löst eine automatisierte Untersuchung aus, die automatisch Nach- und Korrektur von Verletzungsartefakten auslöst, um Ihre Reaktionsfähigkeit auf Vorfälle zu skalieren.

2. Laden Sie das entsprechende Exemplarische Vorgehensweise-Dokument herunter, und lesen Sie es, das sie in Ihrem ausgewählten Szenario bereitgestellt haben.

3. Laden Sie die Simulationsdatei herunter, oder kopieren Sie das Simulationsskript, indem **Sie** zu  >  **Hilfesimulationen & Lernprogrammen** navigieren. Sie können die Datei oder das Skript auf dem Testgerät herunterladen, dies ist jedoch nicht obligatorisch.

4. Führen Sie die Simulationsdatei oder das Skript auf dem Testgerät aus, wie im Dokument mit exemplarischer Vorgehensweise beschrieben.

> [!NOTE]
> Simulationsdateien oder Skripts imitieren Angriffsaktivitäten, sind aber eigentlich gutartig und schaden dem Testgerät nicht.
> 
> 
> Möchten Sie Defender für Endpunkt erfahren? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-attacksimulations-belowfoldlink)


## <a name="related-topics"></a>Verwandte Themen

- [Onboarding von Geräten](onboard-configure.md)
- [Onboarding von Windows 10-Geräten](configure-endpoints.md)
