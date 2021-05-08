---
title: Übersicht über die Geräteermittlung
description: Erfahren Sie, wie Sie die Endpunkterkennung in Microsoft 365 Defender nutzen, um nicht verwaltete Geräte in Ihrem Netzwerk zu finden.
keywords: Geräteerkennung, Ermittlung, passiv, proaktiv, Netzwerk, Sichtbarkeit, Server, Arbeitsstation, onboard, nicht verwaltete Geräte
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
ms.openlocfilehash: 2dee1193e9f852e66df324927bf38d37d736d251
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245948"
---
# <a name="device-discovery-overview"></a>Übersicht über die Geräteermittlung

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

[!include[Prerelease information](../../includes/prerelease.md)]

Zum Schutz Ihrer Umgebung müssen Sie eine Bestandsaufnahme der Geräte in Ihrem Netzwerk verwenden. Die Zuordnung von Geräten in einem Netzwerk kann jedoch häufig kostspielig, schwierig und zeitaufwändig sein. 

Microsoft Defender for Endpoint bietet eine Geräteerkennungsfunktion, mit der Sie nicht verwaltete Geräte finden können, die mit Ihrem Unternehmensnetzwerk verbunden sind, ohne dass zusätzliche Appliances oder aufwändige Prozessänderungen nötig sind.


Mit der Geräteerkennungsfunktion können Sie:

- **Ermitteln von Unternehmensendpunkten, die mit Ihrem Unternehmensnetzwerk verbunden sind** <br>
Mithilfe von einfachen oder standardmäßigen Ermittlungsoptionen können Sie Arbeitsstationen, Server und mobile Endpunkte ermitteln, die noch nicht in Microsoft Defender for Endpoint integrierte sind.  

- **Onboarding von ermittelten Endpunkten**<br>
Nicht verwaltete Endpunkte in Ihrem Netzwerk führen zu Sicherheitsrisiken und Risiken für Ihr Netzwerk. Das Onboarding in den Dienst kann die Sichtbarkeit der Dienste erhöhen. 

In Verbindung mit dieser Funktion wird eine neue Sicherheitsempfehlung zum Onboarding von Geräten in Microsoft Defender for Endpoint im Rahmen der vorhandenen Bedrohungs- und Sicherheitsrisikoverwaltung verfügbar sein.



## <a name="discovery-methods"></a>Ermittlungsmethoden
Es gibt zwei Erkennungsmodi: 

-   Grundlegende Ermittlung 
-   Standardermittlung (empfohlen) 


> [!IMPORTANT]
> Die Ermittlung ist auf den Basismodus festgelegt. Sie können diese Konfiguration über die Einstellungsseite beibehalten. Die Standardermittlung ist der Standardmodus für alle Vorschaukunden ab dem 10. Mai 2021 , sofern sie nicht vor diesem Datum über die Einstellungsseite geändert wird.

### <a name="basic-discovery"></a>Grundlegende Ermittlung 

In diesem Modus erfassen Endpunkte passiv Ereignisse in Ihrem Netzwerk und extrahieren Geräteinformationen aus ihnen. Die grundlegende Ermittlung verwendet die SenseNDR.exe für die passive Netzwerkdatenerfassung, und es wird kein Netzwerkdatenverkehr initiiert. Endpunkte extrahieren einfach Daten aus jedem Netzwerkdatenverkehr, der von einem integrierten Gerät angezeigt wird. 

### <a name="standard-discovery"></a>Standardermittlung 

Mit diesem Modus können Endpunkte beobachtete Geräte im Netzwerk aktiv austesten, um die gesammelten Daten zu bereichern und so eine zuverlässige und zusammenhängende Geräteinventarisierung zu erstellen. Der Standardmodus verwendet intelligentes, aktives Sondieren, um noch mehr Informationen zu beobachteten Geräten zu ermitteln, um vorhandene Geräteinformationen zu bereichern.  

Wenn der Standardmodus aktiviert ist, werden minimale und vernachlässigbare Netzwerkaktivitäten, die vom Ermittlungssensor generiert werden, möglicherweise von Den Netzwerküberwachungstools in Ihrer Organisation beobachtet.  

 Wenn Sie diesen Modus nicht aktivieren möchten, erhalten Sie nur eingeschränkte Sichtbarkeit nicht verwalteter Endpunkte in Ihrem Netzwerk.

Die Standardermittlung verwendet verschiedene PowerShell-Skripts, um Geräte im Netzwerk aktiv zu testen. Diese PowerShell-Skripts sind von Microsoft signiert und werden an folgendem Speicherort ausgeführt: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\*.ps` . Beispiel: `C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\UnicastScannerV1.1.0.ps1`.

Sie können Ihre Discoveryeinstellungen ändern und anpassen, weitere Informationen finden Sie unter [Configure device discovery](configure-device-discovery.md).

> [!NOTE]
> Das Ermittlungsmodul unterscheidet zwischen Netzwerkereignissen, die im Unternehmensnetzwerk empfangen werden, und außerhalb des Unternehmensnetzwerks. Geräte, die nicht mit Unternehmensnetzwerken verbunden sind, werden nicht ermittelt oder im Gerätebestand aufgeführt. 



## <a name="device-inventory"></a>Gerätebestand 
Geräte, die entdeckt wurden, aber noch nicht von Microsoft Defender for Endpoint onboarded und gesichert wurden, werden auf der Registerkarte Endpunkte unter Geräteinventar aufgeführt. Sie können jetzt einen neuen Filter in der Geräteinventarliste namens Onboarding-Status verwenden, der einen der folgenden Werte haben kann:

- Onboarded – Der Endpunkt wird in Microsoft Defender for Endpoint onboarded.
- Kann onboarded werden– Der Endpunkt wurde im Netzwerk erkannt, und das Betriebssystem wurde als ein Endpunkt identifiziert, der von Microsoft Defender for Endpoint unterstützt wird, aber derzeit nicht onboarded ist. Es wird dringend empfohlen, diese Geräte zu integrieren.
- Nicht unterstützt – Der Endpunkt wurde im Netzwerk ermittelt, wird jedoch nicht von Microsoft Defender for Endpoint unterstützt.
- Unzureichende Informationen – Das System konnte die Unterstützungsfähigkeit des Geräts nicht ermitteln. Das Aktivieren der Standarderkennung auf mehr Geräten im Netzwerk kann die ermittelten Attribute bereichern. 
 

![Abbildung des Geräteinventardashboards](images/2b62255cd3a9dd42f3219e437b956fb9.png)

> [!TIP]
> Sie können filter immer anwenden, um nicht verwaltete Geräte aus der Gerätebestandsliste auszuschließen. Sie können auch die Spalte Onboardingstatus in API-Abfragen verwenden, um nicht verwaltete Geräte herausfiltern. 

## <a name="vulnerability-assessment-on-discovered-devices"></a>Sicherheitsrisikobewertung auf erkannten Geräten
Sicherheitsrisiken und Risiken auf Ihren Geräten sowie andere ermittelte nicht verwaltete Geräte im Netzwerk sind Teil der aktuellen TVM-Flüsse unter "Security Empfehlungen" und werden auf Entitätsseiten im gesamten Portal dargestellt. Suchen Sie nach "SSH"-bezogenen Sicherheitsempfehlungen, um SSH-Sicherheitsrisiken zu finden, die für nicht verwaltete und verwaltete Geräte im Zusammenhang stehen. 

![Abbildung des Dashboards für Sicherheitsempfehlungen](images/1156c82ffadd356ce329d1cf551e806c.png)  

## <a name="use-advanced-hunting-on-discovered-devices"></a>Verwenden der erweiterten Suche auf erkannten Geräten
Sie können erweiterte Suchabfragen verwenden, um die Sichtbarkeit auf ermittelten Geräten zu verbessern.
In der Tabelle DeviceInfo finden Sie Details zu ermittelten Endpunkten oder netzwerkbezogene Informationen zu diesen Geräten in der DeviceNetworkInfo-Tabelle.
  

![Abbildung der erweiterten Verwendung der Suche](images/f48ba1779eddee9872f167453c24e5c9.png)


Die Geräteerkennung nutzt integrierte Microsoft Defender for Endpoint-Geräte als Netzwerkdatenquelle, um Aktivitäten nicht integrierten Geräten zu entsprechen. Dies bedeutet, dass aktivitäten auf dem nicht integrierten Gerät auf der Zeitachse und in der Tabelle Advanced hunting DeviceNetworkEvents angezeigt werden, wenn ein integriertes Microsoft Defender for Endpoint-Gerät mit einem nicht integrierten Gerät kommuniziert. 



Neue Ereignisse sind TCP(Transmission Control Protocol)-Verbindungen und passen zum aktuellen DeviceNetworkEvents-Schema. TCP-Ingress auf das Microsoft Defender for Endpoint-fähige Gerät von einem nicht von Microsoft Defender für Endpoint aktivierten Gerät.  

Außerdem wurden die folgenden Aktionstypen hinzugefügt:  

- ConnectionAttempt – Versuch, eine TCP-Verbindung herzustellen (syn)  
- ConnectionAcknowledged – Eine Bestätigung, dass eine TCP-Verbindung akzeptiert wurde (syn\ack)  

Sie können diese Beispielabfrage ausprobieren:  

```
DeviceNetworkEvents  
| where ActionType == "ConnectionAcknowledged" or ActionType == "ConnectionAttempt"  
| take 10  
```


## <a name="changed-behavior"></a>Geändertes Verhalten
Im folgenden Abschnitt werden die Änderungen aufgeführt, die Sie in Microsoft Defender for Endpoint und/oder Microsoft 365 Security Center beobachten, wenn diese Funktion aktiviert ist. 
 
1.  Geräte, die nicht in Microsoft Defender to Endpoint onboarded sind, werden voraussichtlich im Geräteinventar, in der erweiterten Suche und in API-Abfragen angezeigt. Dadurch kann die Größe der Abfrageergebnisse erheblich erhöht werden. 
    1. Die Tabellen "DeviceInfo" und "DeviceNetworkInfo" in Advanced Hunting enthalten nun ermitteltes Gerät. Sie können diese Geräte mithilfe des Attributs "OnboardingStatus" herausfiltern.

    2. Ermittelte Geräte werden voraussichtlich in den Ergebnissen der Streaming-API-Abfrage angezeigt. Sie können diese Geräte mithilfe des Filters `OnboardingStatus` in Ihrer Abfrage herausfiltern. 

2.  Nicht verwaltete Geräte werden vorhandenen Gerätegruppen basierend auf den definierten Kriterien zugewiesen. 
3.  In seltenen Fällen kann die Standarderkennung Warnungen auf Netzwerkmonitoren oder Sicherheitstools auslösen. Bitte geben Sie Feedback, wenn solche Ereignisse auftreten, um zu verhindern, dass sich diese Probleme wiederholen. Sie können explizit ausschließen, dass bestimmte Ziele oder ganze Subnetze von der Standardermittlung aktiv untersucht werden. 



## <a name="next-steps"></a>Nächste Schritte
- [Konfigurieren der Geräteermittlung](configure-device-discovery.md)
- [Häufig gestellte Fragen zur Geräteerkennung](device-discovery-faq.md)
