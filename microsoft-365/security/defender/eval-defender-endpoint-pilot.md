---
title: Pilotieren von Microsoft Defender für Endpunkt, Einrichten eines Pilotprojekts, Testen von Funktionen in der Evaluierung
description: Erfahren Sie, wie Sie ein Pilotprojekt für Microsoft Defender für Endpunkt (MDE) ausführen, einschließlich der Überprüfung der Pilotgruppe und des Testens von Funktionen.
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: v-jweston
author: jweston-1
ms.date: 07/09/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-overview
- m365solution-evalutatemtp
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: d1efc37bd6412e441593dc9cf81296162f7fa754
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/15/2021
ms.locfileid: "53458008"
---
# <a name="pilot-microsoft-defender-for-endpoint"></a>Pilotprojekt für Microsoft Defender für Endpunkt

Dieser Artikel führt Sie beim Ausführen eines Pilotprojekts für Microsoft Defender für Endpunkt. 

Führen Sie die folgenden Schritte aus, um das Pilotprojekt für Microsoft Defender für Endpunkt einzurichten und zu konfigurieren. 

![Schritte zum Hinzufügen von Microsoft Defender for Identity zur Defender-Evaluierungsumgebung](../../media/defender/m365-defender-endpoint-pilot-steps.png)

- Schritt 1. Überprüfen der Pilotgruppe
- Schritt 2. Testen von Funktionen

Wenn Sie Microsoft Defender für Endpunkt testen, können Sie vor dem Onboarding Ihrer gesamten Organisation einige Geräte in den Dienst integrieren.  

Sie können dann funktionen testen, die verfügbar sind, z. B. das Ausführen von Angriffssimulationen und das Sehen, wie Defender für Endpunkt bösartige Aktivitäten aufdecken und ihnen eine effiziente Reaktion ermöglicht. 

## <a name="step-1-verify-pilot-group"></a>Schritt 1. Überprüfen der Pilotgruppe
Nachdem Sie die im Abschnitt ["Evaluierung aktivieren"](eval-defender-endpoint-enable-eval.md) beschriebenen Integrationsschritte abgeschlossen haben, sollten die Geräte ungefähr nach einer Stunde in der Geräteinventurliste angezeigt werden. 

Wenn Ihre integrierten Geräte angezeigt werden, können Sie mit dem Testen von Funktionen fortfahren. 

## <a name="step-2-try-out-capabilities"></a>Schritt 2. Testen von Funktionen
Nachdem Sie das Onboarding einiger Geräte abgeschlossen und sichergestellt haben, dass diese Berichte an den Dienst senden, machen Sie sich mit dem Produkt vertraut, indem Sie die leistungsstarken Funktionen ausprobieren, die sofort verfügbar sind.

Während des Pilotprojekts können Sie problemlos mit dem Testen einiger Features beginnen, um das Produkt in Aktion zu sehen, ohne komplexe Konfigurationsschritte durchlaufen zu müssen.

Beginnen wir mit dem Auschecken der Dashboards.

### <a name="view-the-device-inventory"></a>Anzeigen des Gerätebestands
In der Geräteinventur sehen Sie die Liste der Endpunkte, Netzwerkgeräte und IoT-Geräte in Ihrem Netzwerk. Es bietet Ihnen nicht nur eine Übersicht über die Geräte in Ihrem Netzwerk, sondern bietet auch ausführliche Informationen dazu, z. B. Domäne, Risikostufe, Betriebssystemplattform und andere Details zur einfachen Identifizierung der am meisten gefährdeten Geräte.

### <a name="view-the-threat-and-vulnerability-management-dashboard"></a>Anzeigen des Dashboards für Bedrohungen und Sicherheitsrisikomanagement 
Bedrohungen und Sicherheitsrisikomanagement helfen Ihnen, sich auf die Schwachstellen zu konzentrieren, die das dringendste und höchste Risiko für die Organisation darstellen. Erhalten Sie im Dashboard eine allgemeine Übersicht über die Belichtungsbewertung der Organisation, die Microsoft-Sicherheitsbewertung für Geräte, die Verteilung der Gerätebelichtung, die wichtigsten Sicherheitsempfehlungen, die am häufigsten gefährdete Software, die wichtigsten Wartungsaktivitäten und die am häufigsten verfügbar gemachten Gerätedaten. 

### <a name="run-a-simulation"></a>Ausführen einer Simulation
Microsoft Defender für Endpunkt enthält ["Do It Yourself"-Angriffsszenarien,](https://securitycenter.windows.com/tutorials) die Sie auf Ihren Pilotgeräten ausführen können.  Jedes Dokument enthält Betriebssystem- und Anwendungsanforderungen sowie detaillierte Anweisungen, die für ein Angriffsszenario spezifisch sind. Diese Skripts sind sicher, dokumentiert und einfach zu verwenden. Diese Szenarien spiegeln die Defender für Endpunkt-Funktionen wider und führen Sie durch die Untersuchungserfahrung.

Zum Ausführen einer der bereitgestellten Simulationen benötigen Sie mindestens [ein integriertes Gerät.](../defender-endpoint/onboard-configure.md)

1. Wählen Sie **in**  >  **Hilfesimulationen & Lernprogrammen** aus, welche der verfügbaren Angriffsszenarien Sie simulieren möchten:

   - **Szenario 1: Dokument fällt Hintertür ab** – simuliert die Bereitstellung eines Social Engineering-Lockdokuments. Das Dokument startet eine speziell gestaltete Hintertür, die Angreifern die Kontrolle gibt.

   - **Szenario 2: PowerShell-Skript bei dateilosen Angriffen** – simuliert einen dateilosen Angriff, der auf PowerShell basiert, die Reduzierung der Angriffsfläche und die Erkennung bösartiger Speicheraktivitäten durch Geräte.

   - **Szenario 3: Automatisierte Reaktion auf Sicherheitsvorfälle** – löst eine automatisierte Untersuchung aus, die automatisch Nach- und Korrektur von Verletzungsartefakten auslöst, um Ihre Reaktionsfähigkeit auf Vorfälle zu skalieren.

2. Laden Sie das entsprechende Exemplarische Vorgehensweise-Dokument herunter, und lesen Sie es, das sie in Ihrem ausgewählten Szenario bereitgestellt haben.

3. Laden Sie die Simulationsdatei herunter, oder kopieren Sie das Simulationsskript, indem **Sie** zu  >  **Hilfesimulationen & Lernprogrammen** navigieren. Sie können die Datei oder das Skript auf das Testgerät herunterladen, dies ist jedoch nicht obligatorisch.

4. Führen Sie die Simulationsdatei oder das Skript auf dem Testgerät aus, wie im Dokument mit exemplarischer Vorgehensweise beschrieben.

> [!NOTE]
> Simulationsdateien oder Skripts imitieren Angriffsaktivitäten, sind aber eigentlich gutartig und schaden dem Testgerät nicht.

## <a name="next-steps"></a>Nächste Schritte
[Auswerten Microsoft Cloud App Security](eval-defender-mcas-overview.md)

Kehren Sie zur Übersicht für ["Auswerten von Microsoft Defender für Endpunkt"](eval-defender-endpoint-overview.md) zurück.

Kehren Sie zur Übersicht für [Evaluierungs- und Pilot-Microsoft 365 Defender](eval-overview.md)