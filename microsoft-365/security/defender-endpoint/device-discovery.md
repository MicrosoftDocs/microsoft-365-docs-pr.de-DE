---
title: Übersicht über die Geräteermittlung
description: Erfahren Sie, wie Sie die Endpunktermittlung in Microsoft 365 Defender nutzen, um nicht verwaltete Geräte in Ihrem Netzwerk zu finden.
keywords: Geräteermittlung, entdecken, passiv, proaktiv, Netzwerk, Sichtbarkeit, Server, Arbeitsstation, onboard, nicht verwaltete Geräte
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 9a21c5d067a0ec27b00ff4b4c9aae90bbb65a062
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289871"
---
# <a name="device-discovery-overview"></a>Übersicht über die Geräteermittlung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Der Schutz Ihrer Umgebung erfordert eine Bestandsaufnahme der Geräte, die sich in Ihrem Netzwerk befinden. Die Zuordnung von Geräten in einem Netzwerk kann jedoch häufig teuer, schwierig und zeitaufwändig sein.

Microsoft Defender für Endpunkt bietet eine Geräteermittlungsfunktion, mit der Sie nicht verwaltete Geräte finden können, die mit Ihrem Unternehmensnetzwerk verbunden sind, ohne dass zusätzliche Appliances oder umständliche Prozessänderungen erforderlich sind.

Die Geräteermittlungsfunktion ermöglicht Folgendes:

- **Ermitteln von Unternehmensendpunkten, die mit Ihrem Unternehmensnetzwerk verbunden sind**

  Mit einfachen oder standardmäßigen Ermittlungsoptionen können Sie Arbeitsstationen, Server und mobile Endpunkte ermitteln, die noch nicht in Microsoft Defender für Endpunkt integriert sind.

- **Onboarding von ermittelten Endpunkten**

  Nicht verwaltete Endpunkte in Ihrem Netzwerk führen zu Sicherheitsrisiken und Risiken für Ihr Netzwerk. Durch das Onboarding in den Dienst kann die Sichtbarkeit der Sicherheit für sie erhöht werden.

In Verbindung mit dieser Funktion wird eine neue Sicherheitsempfehlung zum Onboarding von Geräten in Microsoft Defender für Endpunkt als Teil der vorhandenen Bedrohungs- und Sicherheitsrisikoverwaltung verfügbar sein.

## <a name="discovery-methods"></a>Ermittlungsmethoden

Es gibt zwei Erkennungsmodi:

- Grundlegende Ermittlung
- Standardermittlung (empfohlen)

> [!IMPORTANT]
> Die Ermittlung ist auf den Basismodus festgelegt. Sie können diese Konfiguration über die Einstellungsseite beibehalten. Die Standardermittlung ist der Standardmodus für alle Kunden ab dem 19. Juli 2021, es sei denn, sie wird über die Einstellungsseite vor diesem Datum geändert.

### <a name="basic-discovery"></a>Grundlegende Ermittlung

In diesem Modus erfassen Endpunkte passiv Ereignisse in Ihrem Netzwerk und extrahieren Geräteinformationen daraus. Die grundlegende Ermittlung verwendet die SenseNDR.exe Binärdatei für die passive Netzwerkdatensammlung, und es wird kein Netzwerkdatenverkehr initiiert. Endpunkte extrahieren einfach Daten aus jedem Netzwerkdatenverkehr, der von einem integrierten Gerät erkannt wird.

### <a name="standard-discovery"></a>Standardermittlung

Dieser Modus ermöglicht Es Endpunkten, beobachtete Geräte im Netzwerk aktiv zu untersuchen, um gesammelte Daten zu erweitern, sodass Sie einen zuverlässigen und konsistenten Gerätebestand erstellen können. Der Standardmodus verwendet intelligente, aktive Untersuchung, um noch mehr Informationen zu beobachteten Geräten zu ermitteln, um vorhandene Geräteinformationen zu erweitern.

Wenn der Standardmodus aktiviert ist, werden minimale und geringfügige Netzwerkaktivitäten, die vom Ermittlungssensor generiert werden, möglicherweise von Netzwerküberwachungstools in Ihrer Organisation beobachtet.

 Wenn Sie diesen Modus nicht aktivieren, erhalten Sie nur eingeschränkte Sichtbarkeit von nicht verwalteten Endpunkten in Ihrem Netzwerk.

Standard Discovery verwendet verschiedene PowerShell-Skripts, um Geräte im Netzwerk aktiv zu untersuchen. Diese PowerShell-Skripts sind von Microsoft signiert und werden an folgendem Speicherort ausgeführt: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` . Beispiel: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.

Sie können Ihre Ermittlungseinstellungen ändern und anpassen. Weitere Informationen finden Sie unter [Konfigurieren der Geräteermittlung.](configure-device-discovery.md)

> [!NOTE]
> Das Ermittlungsmodul unterscheidet zwischen Netzwerkereignissen, die im Unternehmensnetzwerk empfangen werden, und außerhalb des Unternehmensnetzwerks. Geräte, die nicht mit Unternehmensnetzwerken verbunden sind, werden nicht ermittelt oder im Gerätebestand aufgeführt.

## <a name="device-inventory"></a>Gerätebestand

Geräte, die ermittelt wurden, aber noch nicht integriert und von Microsoft Defender für Endpunkt gesichert wurden, werden im Geräteinventar auf der Registerkarte "Endpunkte" aufgeführt. Sie können nun einen neuen Filter in der Gerätebestandsliste namens Onboardingstatus verwenden, der einen der folgenden Werte aufweisen kann:

- Onboarded – Der Endpunkt ist in Microsoft Defender für Endpunkt integriert.
- Kann integriert werden – Der Endpunkt wurde im Netzwerk ermittelt, und das Betriebssystem wurde als ein Endpunkt identifiziert, der von Microsoft Defender für Endpunkt unterstützt wird, aber derzeit nicht integriert ist. Es wird dringend empfohlen, diese Geräte zu integrieren.
- Nicht unterstützt – Der Endpunkt wurde im Netzwerk ermittelt, wird jedoch von Microsoft Defender für Endpunkt nicht unterstützt.
- Unzureichende Informationen – Das System konnte die Unterstützung des Geräts nicht ermitteln. Das Aktivieren der Standardermittlung auf mehr Geräten im Netzwerk kann die ermittelten Attribute erweitern.

![Abbildung des Geräteinventar-Dashboards](images/2b62255cd3a9dd42f3219e437b956fb9.png)

> [!TIP]
> Sie können immer Filter anwenden, um nicht verwaltete Geräte aus der Gerätebestandsliste auszuschließen. Sie können auch die Spalte "Onboardingstatus" in API-Abfragen verwenden, um nicht verwaltete Geräte herauszufiltern.

## <a name="vulnerability-assessment-on-discovered-devices"></a>Bewertung von Sicherheitsrisiken auf ermittelten Geräten

Sicherheitsrisiken und Risiken auf Ihren Geräten sowie andere ermittelte nicht verwaltete Geräte im Netzwerk sind Teil des aktuellen TVM-Flusses unter "Sicherheit Empfehlungen" und werden auf Entitätsseiten im portalweiten Format dargestellt.
Suchen Sie nach "SSH"-Sicherheitsempfehlungen, um SSH-Sicherheitsrisiken zu finden, die mit nicht verwalteten und verwalteten Geräten zusammenhängen.

![Abbildung des Dashboards für Sicherheitsempfehlungen](images/1156c82ffadd356ce329d1cf551e806c.png)

## <a name="use-advanced-hunting-on-discovered-devices"></a>Verwenden der erweiterten Suche auf ermittelten Geräten

Sie können Abfragen der erweiterten Suche verwenden, um Aufschlüsse auf ermittelten Geräten zu erhalten.
Hier finden Sie Details zu ermittelten Endpunkten in der DeviceInfo-Tabelle oder netzwerkbezogene Informationen zu diesen Geräten in der DeviceNetworkInfo-Tabelle.

![Abbildung der verwendung der erweiterten Suche](images/f48ba1779eddee9872f167453c24e5c9.png)

Die Gerätesuche nutzt integrierte Geräte von Microsoft Defender für Endpunkt als Netzwerkdatenquelle, um Aktivitäten nicht integrierten Geräten zuzuordnen. Dies bedeutet, dass, wenn ein integriertes Microsoft Defender für Endpunkt-Gerät mit einem nicht integrierten Gerät kommuniziert, Aktivitäten auf dem nicht integrierten Gerät auf der Zeitachse und über die DeviceNetworkEvents-Tabelle für die erweiterte Suche angezeigt werden können.

Neue Ereignisse sind TCP-Verbindungen (Transmission Control Protocol) und passen in das aktuelle DeviceNetworkEvents-Schema. TCP-Ausgang an das Microsoft Defender für Endpunkt-aktivierte Gerät von einem nicht von Microsoft Defender für Endpunkt aktivierten Gerät. 

Die folgenden Aktionstypen wurden ebenfalls hinzugefügt:

- ConnectionAttempt – Ein Versuch, eine TCP-Verbindung herzustellen (syn) 
- ConnectionAcknowledged – Eine Bestätigung, dass eine TCP-Verbindung akzeptiert wurde (syn\ack) 

Sie können diese Beispielabfrage testen:

```
DeviceNetworkEvents
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"
| take 10
```

## <a name="changed-behavior"></a>Geändertes Verhalten

Im folgenden Abschnitt werden die Änderungen aufgeführt, die Sie in Microsoft Defender für Endpunkt und/oder Microsoft 365 Security Center beobachten werden, wenn diese Funktion aktiviert ist.

1. Geräte, die nicht in Microsoft Defender zu Endpunkt integriert sind, werden voraussichtlich im Gerätebestand, in der erweiterten Suche und in API-Abfragen angezeigt. Dies kann die Größe der Abfrageergebnisse erheblich erhöhen.
    1. Die Tabellen "DeviceInfo" und "DeviceNetworkInfo" in der erweiterten Suche enthalten nun das ermittelte Gerät. Sie können diese Geräte mithilfe des "OnboardingStatus"-Attributs herausfiltern.
    2. Es wird erwartet, dass ermittelte Geräte in den Abfrageergebnissen der Streaming-API angezeigt werden. Sie können diese Geräte herausfiltern, indem Sie den `OnboardingStatus` Filter in Ihrer Abfrage verwenden.
2. Nicht verwaltete Geräte werden vorhandenen Gerätegruppen basierend auf den definierten Kriterien zugewiesen.
3. In seltenen Fällen kann die Standardermittlung Warnungen auf Netzwerkmonitoren oder Sicherheitstools auslösen. Bitte geben Sie Feedback, wenn Sie solche Ereignisse erleben, um zu verhindern, dass sich diese Probleme wiederholen. Sie können explizit ausschließen, dass bestimmte Ziele oder ganze Subnetze von der Standardermittlung aktiv untersucht werden.

## <a name="next-steps"></a>Nächste Schritte

- [Konfigurieren der Geräteermittlung](configure-device-discovery.md)
- [Häufig gestellte Fragen zur Geräteermittlung](device-discovery-faq.md)
