---
title: Verwenden automatisierter Untersuchungen zum Untersuchen und Beheben von Bedrohungen
description: Verstehen des automatisierten Untersuchungsflusses in Microsoft Defender für Endpunkt.
keywords: automatisiert, Untersuchung, Erkennung, Microsoft Defender für Endpunkt
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
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
ms.openlocfilehash: e52471e1b3e9ee3a410de493b536f9d360d60624
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844442"
---
# <a name="overview-of-automated-investigations"></a>Übersicht über automatisierte Untersuchungen

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


Möchten Sie sehen, wie es funktioniert? Sehen Sie sich das folgende Video an: <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4bOeh]

Die Technologie bei der automatisierten Untersuchung verwendet verschiedene Prüfalgorithmen und basiert auf Prozessen, die von Sicherheitsanalysten verwendet werden. AIR-Funktionen sind so konzipiert, dass Warnungen untersucht und sofort Maßnahmen ergriffen werden, um Verstöße zu beheben. AIR-Funktionen reduzieren das Warnungsvolumen erheblich, sodass sich Sicherheitsvorgänge auf komplexere Bedrohungen und andere hochwertige Initiativen konzentrieren können. Alle Korrekturaktionen, ob ausstehend oder abgeschlossen, werden im [Info-Center](auto-investigation-action-center.md)nachverfolgt. Im Info-Center werden ausstehende Aktionen genehmigt (oder abgelehnt), und abgeschlossene Aktionen können bei Bedarf rückgängig sein.

Dieser Artikel bietet eine Übersicht über AIR und enthält Links zu den nächsten Schritten und zusätzlichen Ressourcen.

> [!TIP]
> Möchten Sie Microsoft Defender für Endpunkt erleben? [Registrieren Sie sich für eine kostenlose Testversion.](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-automated-investigations-abovefoldlink)

## <a name="how-the-automated-investigation-starts"></a>Beginn der automatisierten Untersuchung

Eine automatisierte Untersuchung kann beginnen, wenn eine Warnung ausgelöst wird oder wenn ein Sicherheitsoperator die Untersuchung initiiert.

|Situation  |Aktionen  |
|---------|---------|
|Eine Warnung wird ausgelöst.     | Im Allgemeinen wird eine automatisierte Untersuchung gestartet, wenn eine [Warnung](review-alerts.md) ausgelöst wird und ein [Vorfall](view-incidents-queue.md) erstellt wird. Angenommen, eine schädliche Datei befindet sich auf einem Gerät. Wenn diese Datei erkannt wird, wird eine Warnung ausgelöst, und ein Vorfall wird erstellt. Ein automatisierter Untersuchungsprozess beginnt auf dem Gerät. Da andere Warnungen aufgrund derselben Datei auf anderen Geräten generiert werden, werden sie dem zugeordneten Vorfall und der automatisierten Untersuchung hinzugefügt.         |
|Eine Untersuchung wird manuell gestartet.     | Eine automatisierte Untersuchung kann von Ihrem Sicherheitsteam manuell gestartet werden. Angenommen, ein Sicherheitsoperator überprüft eine Liste von Geräten und stellt fest, dass ein Gerät ein hohes Risikoniveau aufweist. Der Sicherheitsoperator kann das Gerät in der Liste auswählen, um das Flyout zu öffnen, und dann **"Automatische Untersuchung initiieren"** auswählen. |

## <a name="how-an-automated-investigation-expands-its-scope"></a>Erweitern des Umfangs einer automatisierten Untersuchung

Während eine Untersuchung ausgeführt wird, werden alle anderen vom Gerät generierten Warnungen zu einer laufenden automatisierten Untersuchung hinzugefügt, bis diese Untersuchung abgeschlossen ist. Wenn die gleiche Bedrohung auf anderen Geräten angezeigt wird, werden diese Geräte der Untersuchung hinzugefügt.

Wenn eine inkriminierte Entität auf einem anderen Gerät angezeigt wird, erweitert der automatisierte Untersuchungsprozess seinen Bereich, um dieses Gerät einzuschließen, und ein allgemeines Sicherheits-Playbook wird auf diesem Gerät gestartet. Wenn während dieses Erweiterungsprozesses aus derselben Entität 10 oder mehr Geräte gefunden werden, erfordert diese Erweiterungsaktion eine Genehmigung und wird auf der Registerkarte **"Ausstehende Aktionen"** angezeigt.

## <a name="how-threats-are-remediated"></a>Wie Bedrohungen behoben werden

Wenn Warnungen ausgelöst werden und eine automatisierte Untersuchung ausgeführt wird, wird für jeden untersuchten Nachweis ein Bewertungsbeitrag generiert. Die Bewertung kann folgendermaßen lauten: 
- *Bösartig*;
- *Verdächtig*; Oder 
- *Es wurden keine Bedrohungen gefunden.* 

Wenn Bewertungen erreicht werden, können automatisierte Untersuchungen zu einer oder mehreren Korrekturaktionen führen. Beispiele für Korrekturaktionen sind das Senden einer Datei in die Quarantäne, das Beenden eines Diensts, das Entfernen einer geplanten Aufgabe und vieles mehr. Weitere Informationen finden Sie unter ["Wartungsaktionen".](manage-auto-investigation.md#remediation-actions)  

Je nach dem [Grad der Automatisierung](automation-levels.md) für Ihre Organisation sowie anderen Sicherheitseinstellungen können Korrekturaktionen automatisch oder nur nach Genehmigung durch Ihr Sicherheitsteam ausgeführt werden. Zusätzliche Sicherheitseinstellungen, die sich auf die automatische Korrektur auswirken können, umfassen [den Schutz vor potenziell unerwünschten Anwendungen](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus) (PUA). 

Alle Korrekturaktionen, ob ausstehend oder abgeschlossen, werden im [Info-Center](auto-investigation-action-center.md)nachverfolgt. Bei Bedarf kann Ihr Sicherheitsteam eine Korrekturaktion rückgängigmachen. Weitere Informationen finden Sie unter ["Überprüfen und Genehmigen von Abhilfemaßnahmen nach einer automatisierten Untersuchung".](/microsoft-365/security/defender-endpoint/manage-auto-investigation)

> [!TIP]
> Sehen Sie sich die neue, einheitliche Untersuchungsseite im Microsoft 365 Security Center an. Weitere Informationen finden Sie unter [(NEU!) Einheitliche Untersuchungsseite](/microsoft-365/security/defender/m365d-autoir-results#new-unified-investigation-page).


## <a name="requirements-for-air"></a>Anforderungen für AIR

Ihre Organisation muss über Defender für Endpunkt verfügen (siehe [Mindestanforderungen für Microsoft Defender für Endpunkt).](minimum-requirements.md)

Derzeit unterstützt AIR nur die folgenden Betriebssystemversionen:
- Windows Server 2019
- Windows 10, Version 1709 (Betriebssystembuild 16299.1085 mit [KB4493441)](https://support.microsoft.com/help/4493441/windows-10-update-kb4493441)oder höher
- Windows 10, Version 1803 (Betriebssystembuild 17134.704 mit [KB4493464)](https://support.microsoft.com/help/4493464/windows-10-update-kb4493464)oder höher
- Windows 10, Version [1803](/windows/release-information/status-windows-10-1809-and-windows-server-2019) oder höher

## <a name="next-steps"></a>Nächste Schritte

- [Weitere Informationen zu Automatisierungsebenen](automation-levels.md)
- [Weitere Informationen finden Sie im interaktiven Leitfaden: Untersuchen und Beheben von Bedrohungen mit Microsoft Defender für Endpunkt](https://aka.ms/MDATP-IR-Interactive-Guide)
- [Konfigurieren automatisierter Untersuchungs- und Korrekturfunktionen in Microsoft Defender für Endpunkt](configure-automated-investigations-remediation.md)

## <a name="see-also"></a>Siehe auch

- [PUA-Schutz](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)
- [Automatisierte Untersuchung und Reaktion in Microsoft Defender für Office 365](/microsoft-365/security/office-365-security/office-365-air)
- [Automatisierte Untersuchung und Reaktion in Microsoft 365 Defender](/microsoft-365/security/defender/mtp-autoir)
