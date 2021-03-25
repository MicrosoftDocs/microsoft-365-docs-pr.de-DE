---
title: Verwenden automatisierter Untersuchungen zur Untersuchung und Behebung von Bedrohungen
description: Verstehen Sie den automatisierten Untersuchungsfluss in Microsoft Defender for Endpoint.
keywords: automatisiert, Untersuchung, Erkennung, Defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.date: 02/02/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: how-to
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: 7143a360fb7093f94c6f66373587e1c895dd3213
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51200305"
---
# <a name="overview-of-automated-investigations"></a>Übersicht über automatisierte Untersuchungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Möchten Sie sehen, wie es funktioniert? Sehen Sie sich das folgende Video an: <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

Die Technologie bei der automatisierten Untersuchung verwendet verschiedene Prüfalgorithmen und basiert auf Prozessen, die von Sicherheitsanalysten verwendet werden. Die AIR-Funktionen sollen Warnungen untersuchen und sofortige Maßnahmen zur Behebung von Verstößen ergreifen. Die AIR-Funktionen reduzieren das Warnungsvolumen erheblich, sodass sich Sicherheitsvorgänge auf komplexere Bedrohungen und andere hochwertige Initiativen konzentrieren können. Alle Korrekturaktionen, ob ausstehend oder abgeschlossen, werden im [Aktionscenter nachverfolgt.](auto-investigation-action-center.md) Im Aktionscenter werden ausstehende Aktionen genehmigt (oder abgelehnt), und abgeschlossene Aktionen können bei Bedarf rückgängig gemacht werden.

Dieser Artikel bietet eine Übersicht über AIR und enthält Links zu den nächsten Schritten und zusätzlichen Ressourcen.

> [!TIP]
> Möchten Sie Microsoft Defender for Endpoint erleben? [Registrieren Sie sich für eine kostenlose Testversion](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink).

## <a name="how-the-automated-investigation-starts"></a>Start der automatisierten Untersuchung

Eine automatisierte Untersuchung kann beginnen, wenn eine Warnung ausgelöst wird oder wenn ein Sicherheitsoperator die Untersuchung initiiert.

|Situation  |Aktionen  |
|---------|---------|
|Eine Warnung wird ausgelöst     | Im Allgemeinen wird eine automatisierte Untersuchung gestartet, wenn [eine](review-alerts.md) Warnung ausgelöst wird und ein [Vorfall](view-incidents-queue.md) erstellt wird. Angenommen, eine schädliche Datei befindet sich auf einem Gerät. Wenn diese Datei erkannt wird, wird eine Warnung ausgelöst, und ein Vorfall wird erstellt. Auf dem Gerät beginnt ein automatisierter Untersuchungsprozess. Da andere Warnungen aufgrund derselben Datei auf anderen Geräten generiert werden, werden sie dem zugeordneten Vorfall und der automatisierten Untersuchung hinzugefügt.         |
|Eine Untersuchung wird manuell gestartet     | Eine automatisierte Untersuchung kann von Ihrem Sicherheitsteam manuell gestartet werden. Angenommen, ein Sicherheitsoperator überprüft eine Liste der Geräte und bemerkt, dass ein Gerät ein hohes Risikoniveau hat. Der Sicherheitsoperator kann das Gerät in der Liste auswählen, um das Flyout zu öffnen, und dann automatische Untersuchung **initiieren auswählen.** |

## <a name="how-an-automated-investigation-expands-its-scope"></a>Erweitern des Umfangs einer automatisierten Untersuchung

Während eine Untersuchung ausgeführt wird, werden alle anderen vom Gerät generierten Warnungen einer fortlaufenden automatisierten Untersuchung hinzugefügt, bis diese Untersuchung abgeschlossen ist. Wenn die gleiche Bedrohung auch auf anderen Geräten angezeigt wird, werden diese Geräte der Untersuchung hinzugefügt.

Wenn eine inkriminierte Entität auf einem anderen Gerät angezeigt wird, erweitert der automatisierte Untersuchungsprozess seinen Bereich um dieses Gerät, und ein allgemeines Sicherheitsspielbuch wird auf diesem Gerät gestartet. Wenn während dieses Erweiterungsprozesses 10 oder mehr Geräte aus derselben Entität gefunden werden, erfordert diese Erweiterungsaktion eine Genehmigung und ist auf der Registerkarte **Ausstehende Aktionen** sichtbar.

## <a name="how-threats-are-remediated"></a>Wie Bedrohungen behoben werden

Wenn Warnungen ausgelöst werden und eine automatisierte Untersuchung ausgeführt wird, wird für jeden untersuchten Nachweis ein Urteil generiert. Die Urteile können 
- *Bösartig*;
- *Verdächtig*; oder 
- *Keine Bedrohungen gefunden.* 

Wenn die Ergebnisse erreicht sind, können automatisierte Untersuchungen zu einer oder mehreren Abhilfemaßnahmen führen. Beispiele für Korrekturaktionen sind das Senden einer Datei in quarantäne, das Beenden eines Diensts, das Entfernen einer geplanten Aufgabe und vieles mehr. Weitere Informationen finden Sie unter [Remediation actions](manage-auto-investigation.md#remediation-actions).  

Je nach [Automatisierungsstufe](automation-levels.md) für Ihre Organisation und anderen Sicherheitseinstellungen können Korrekturaktionen automatisch oder nur nach Genehmigung durch Ihr Sicherheitsteam ausgeführt werden. Zusätzliche Sicherheitseinstellungen, die sich auf die automatische Behebung auswirken können, umfassen den Schutz [vor potenziell unerwünschten](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) Anwendungen (PUA). 

Alle Korrekturaktionen, ob ausstehend oder abgeschlossen, werden im [Aktionscenter nachverfolgt.](auto-investigation-action-center.md) Bei Bedarf kann ihr Sicherheitsbetriebsteam eine Korrekturaktion rückgängig machen. Weitere Informationen finden Sie unter [Review and approve remediation actions following an automated investigation](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/manage-auto-investigation).

> [!TIP]
> Sehen Sie sich die neue, einheitliche Untersuchungsseite im Microsoft 365 Security Center an. Weitere Informationen finden Sie unter [(NEU!) Vereinheitlichte Untersuchungsseite](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).


## <a name="requirements-for-air"></a>Anforderungen für AIR

Ihre Organisation muss über Defender for Endpoint verfügen (siehe [Mindestanforderungen für Microsoft Defender for Endpoint](minimum-requirements.md)).

Derzeit unterstützt AIR nur die folgenden Betriebssystemversionen:
- Windows Server 2019
- Windows 10, Version 1709 (Betriebssystem build 16299.1085 with [KB4493441](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)) oder höher
- Windows 10, Version 1803 (Betriebssystem build 17134.704 mit [KB4493464](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)) oder höher
- Windows 10, Version [1803](https://docs.microsoft.com/windows/release-information/status-windows-10-1809-and-windows-server-2019) oder höher

## <a name="next-steps"></a>Nächste Schritte

- [Weitere Informationen zu Automatisierungsebenen](automation-levels.md)
- [Weitere Informationen finden Sie im interaktiven Leitfaden: Untersuchen und Behebung von Bedrohungen mit Microsoft Defender for Endpoint](https://aka.ms/MDATP-IR-Interactive-Guide)
- [Konfigurieren automatisierter Untersuchungs- und Korrekturfunktionen in Microsoft Defender for Endpoint](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>Siehe auch

- [PUA-Schutz](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Automatisierte Untersuchung und Reaktion in Microsoft Defender für Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)
- [Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/defender/mtp-autoir)
