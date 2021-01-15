---
title: Von Microsoft Defender Antivirus entdeckte Bedrohungen
f1.keywords: CSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid: MET150
description: Erfahren Sie, wie Microsoft Defender Antivirus Ihre Windows-Geräte vor Softwarebedrohungen wie Viren, Schadsoftware und Spyware schützt.
ms.openlocfilehash: 1653aef6967cdf76e6e19acda158fb29758280a8
ms.sourcegitcommit: df58fd8ebe14ca98fc1be84dbfb9c29ef7ab1d62
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/15/2021
ms.locfileid: "49870899"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Von Microsoft Defender Antivirus entdeckte Bedrohungen

Microsoft Defender Antivirus schützt Ihre Windows-Geräte vor Softwarebedrohungen wie Viren, Schadsoftware und Spyware.

- Viren werden in der Regel durch Anfügen ihres Codes an andere Dateien auf Ihrem Gerät oder Netzwerk verteilt und können dazu führen, dass infizierte Programme nicht ordnungsgemäß funktionieren.
- Schadsoftware umfasst schädliche Dateien, Anwendungen und Code, die Schäden verursachen und die normale Verwendung von Geräten unterbrechen können. Darüber hinaus kann Schadsoftware nicht autorisierten Zugriff zulassen, Systemressourcen verwenden, Kennwörter und Kontoinformationen stehlen, Sie von Ihrem Computer sperren und Lösegeld verlangen und vieles mehr.
- Spyware sammelt Daten, z. B. Webbrowsen-Aktivitäten, und sendet die Daten an Remoteserver.
 
Um Bedrohungsschutz zu bieten, verwendet Microsoft Defender Antivirus mehrere Methoden. Diese Methoden umfassen über die Cloud übermittelten Schutz, Echtzeitschutz und dedizierte Schutzupdates.

- Der über die Cloud übermittelte Schutz hilft dabei, neue und neue Bedrohungen nahezu sofort zu erkennen und zu blockieren.
- Bei der always-on-Überprüfung werden die Überwachung des Datei- und Prozessverhaltens und andere Techniken (auch als *Echtzeitschutz bekannt) verwendet.*
- Dedizierte Schutzupdates basieren auf maschinellem Lernen, menschlichen und automatisierten Big-Data-Analysen und detaillierten Forschungen zum Schutz vor Bedrohungen. 

Weitere Informationen zu Schadsoftware und Microsoft Defender Antivirus finden Sie in den folgenden Artikeln: 

- [Grundlegendes zu Schadsoftware & anderen Bedrohungen](/windows/security/threat-protection/intelligence/understanding-malware)
- [So identifiziert Microsoft Schadsoftware und potenziell unerwünschte Anwendungen](/windows/security/threat-protection/intelligence/criteria)
- [Schutz der nächsten Generation in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Was geschieht, wenn eine nicht von Microsoft verwendete Antivirenlösung verwendet wird? 

Microsoft Defender Antivirus ist Teil des Betriebssystems und auf Geräten unter Windows 10 aktiviert. Wenn Sie jedoch eine Nicht-Microsoft-Antivirenlösung verwenden und [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)nicht verwenden, wechselt Microsoft Defender Antivirus automatisch in den deaktivierten Modus.  

Im deaktivierten Modus können Benutzer und Kunden Weiterhin Microsoft Defender Antivirus für geplante oder bedarfsgerechte Scans verwenden, um Bedrohungen zu identifizieren. Microsoft Defender Antivirus wird jedoch nicht mehr:

- als standardmäßige Antiviren-App verwendet werden.
- Dateien aktiv auf Bedrohungen überprüfen.
- Bedrohungen zu beheben oder zu beheben.

Wenn Sie die Nicht-Microsoft-Antivirenlösung deinstallieren, wechselt Microsoft Defender Antivirus automatisch in den aktiven Modus, um Ihre Windows-Geräte vor Bedrohungen zu schützen.

> [!TIP]
> - Wenn Sie Microsoft 365 verwenden, sollten Sie Microsoft Defender Antivirus als primäre Antivirenlösung verwenden. Die Integration kann einen besseren Schutz bieten. Weitere [Informationen finden Sie zusammen: Microsoft Defender Antivirus und Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Stellen Sie sicher, dass Sie Microsoft Defender Antivirus auf dem neuesten Stand halten, auch wenn Sie eine nicht von Microsoft stammende Antivirenlösung verwenden.

## <a name="what-to-expect-when-threats-are-detected"></a>Was sie erwarten können, wenn Bedrohungen erkannt werden

Wenn Bedrohungen von Microsoft Defender Antivirus erkannt werden, geschieht Folgendes:

- Benutzer erhalten [Benachrichtigungen in Windows.](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e) 
- Erkennungen werden in der [Windows-Sicherheits-App](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) auf der Seite **"Schutzverlauf"** aufgeführt.  
- If you've [secured your Windows 10 devices](secure-win-10-pcs.md) and [enrolled them in Intune,](/mem/intune/enrollment/windows-enrollment-methods)and your organization has 800 or fewer devices enrolled, you'll see threat detections and insights in the <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 admin center</a> on the Threats and **antivirus** page, which you can access from the Microsoft **Defender Antivirus** card on the **Home** page (or from the navigation pane by selecting **Health** Threats  >  **& antivirus**).

    Wenn Ihre Organisation über mehr als 800 Geräte verfügt, die in Intune registriert sind, werden Sie aufgefordert, Bedrohungserkennungen und -einblicke von [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) anstelle der Bedrohungs- und Antivirenseite einsuchen zu lassen. 
 
    > [!NOTE]
    > Die **Microsoft Defender Antivirus-Karte** und die Seite "Bedrohungen und **Antivirensoftware"** werden phasenweise veröffentlicht, sodass Sie möglicherweise keinen sofortigen Zugriff darauf haben.

In den meisten Fällen müssen Benutzer keine weiteren Maßnahmen ergreifen. Sobald eine schädliche Datei oder ein schädliches Programm auf einem Gerät erkannt wird, blockiert Microsoft Defender Antivirus die Datei und verhindert, dass sie ausgeführt wird. Darüber hinaus werden neu erkannte Bedrohungen dem Antivirus- und Antischalwaremodul hinzugefügt, sodass auch andere Geräte und Benutzer geschützt werden.  

Wenn ein Benutzer eine Aktion ergreifen muss, z. B. das Genehmigen des Entfernens einer schädlichen Datei, wird dies in der Benachrichtigung angezeigt, die er erhält. Weitere Informationen zu Aktionen, die Microsoft Defender Antivirus im Namen eines Benutzers vornimmt, oder aktionen, die Benutzer möglicherweise ausführen müssen, finden Sie im [Schutzverlauf.](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708) Informationen zum Verwalten von Bedrohungserkennungen als IT-Professional/Administrator finden Sie unter "Überprüfen erkannter [Bedrohungen und Ergreifen von Maßnahmen".](review-threats-take-action.md)

Weitere Informationen zu verschiedenen Bedrohungen finden Sie auf der <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft Security Intelligence Threats-Website,</a>auf der Sie die folgenden Aktionen ausführen können: 

- Aktuelle Informationen zu den bedrohungsbedrohungen.
- Zeigen Sie die neuesten Bedrohungen für eine bestimmte Region an.
- Durchsuchen Sie die Bedrohungsbedrohung nach Details zu einer bestimmten Bedrohung.

## <a name="related-content"></a>Verwandte Inhalte

[Sichern von Windows 10-Geräten](secure-windows-10-devices.md) (Artikel)\
[Bewerten von Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (Artikel)\
[So aktivieren Sie den Antivirenschutz in Echtzeit](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) und über die Cloud (Artikel)\
[Aktivieren und Verwenden von Microsoft Defender Antivirus in der Windows-Sicherheits-App](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (Artikel)\
[So aktivieren Sie Microsoft Defender Antivirus mithilfe von Gruppenrichtlinien](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (Artikel)\
[So aktualisieren Sie Ihre Antivirendefinitionen](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (Artikel)\
[So übermitteln Sie Schadsoftware und Nicht-Schadsoftware zur Analyse](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) an Microsoft (Artikel)