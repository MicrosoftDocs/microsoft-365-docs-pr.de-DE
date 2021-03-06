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
description: Erfahren Sie Microsoft Defender Antivirus Ihre Windows vor Softwarebedrohungen wie Viren, Schadsoftware und Spyware schützt.
ms.openlocfilehash: 7c5d000e2a8c30e17d1f890cef69fe88beed75bb
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198363"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Von Microsoft Defender Antivirus entdeckte Bedrohungen

Microsoft Defender Antivirus schützt Ihre Windows vor Softwarebedrohungen wie Viren, Schadsoftware und Spyware.

- Viren werden in der Regel durch Anfügen ihres Codes an andere Dateien auf Ihrem Gerät oder Netzwerk verbreitet und können dazu führen, dass infizierte Programme falsch funktionieren.
- Schadsoftware umfasst schädliche Dateien, Anwendungen und Code, die schäden verursachen und die normale Nutzung von Geräten unterbrechen können. Außerdem kann Schadsoftware nicht autorisierten Zugriff zulassen, Systemressourcen verwenden, Kennwörter und Kontoinformationen stehlen, Sie von Ihrem Computer sperren und Lösegeld fordern und vieles mehr.
- Spyware sammelt Daten, z. B. Web-Browsing-Aktivitäten, und sendet die Daten an Remoteserver.
 
Zum Bereitstellen von Bedrohungsschutz Microsoft Defender Antivirus verschiedene Methoden verwendet. Zu diesen Methoden gehören cloudbasierter Schutz, Echtzeitschutz und dedizierte Schutzupdates.

- Der in der Cloud zugestellte Schutz hilft bei der nahezu sofortigen Erkennung und Blockierung neuer und neuer Bedrohungen.
- Bei der Immer-on-Überprüfung werden die Überwachung des Datei- und Prozessverhaltens und andere Techniken (auch als *Echtzeitschutz bekannt) verwendet.*
- Dedizierte Schutzupdates basieren auf maschinellem Lernen, einer menschlichen und automatisierten Big Data-Analyse und einer eingehenden Forschung zur Bedrohungsabwehr. 

Weitere Informationen zu Schadsoftware und Microsoft Defender Antivirus finden Sie in den folgenden Artikeln: 

- [Grundlegendes zu Schadsoftware & anderen Bedrohungen](/windows/security/threat-protection/intelligence/understanding-malware)
- [Identifizieren von Schadsoftware und potenziell unerwünschten Anwendungen durch Microsoft](/windows/security/threat-protection/intelligence/criteria)
- [Schutz der nächsten Generation in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Was geschieht, wenn eine Nicht-Microsoft-Antivirenlösung verwendet wird? 

Microsoft Defender Antivirus ist Teil des Betriebssystems und auf Geräten aktiviert, auf deren Windows 10. Wenn Sie jedoch eine Nicht-Microsoft-Antivirenlösung verwenden und [Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)nicht verwenden, wechselt Microsoft Defender Antivirus automatisch in den deaktivierten Modus.  

Wenn sich Benutzer und Kunden im deaktivierten Modus befinden, können sie Microsoft Defender Antivirus für geplante oder on-Demand-Scans verwenden, um Bedrohungen zu identifizieren. Die Microsoft Defender Antivirus wird jedoch nicht mehr:

- als Standard-Antivirus-App verwendet werden.
- Dateien aktiv auf Bedrohungen überprüfen.
- Beheben oder Beheben von Bedrohungen.

Wenn Sie die Nicht-Microsoft-Antivirenlösung deinstallieren, wechselt Microsoft Defender Antivirus automatisch in den aktiven Modus, um Ihre Windows vor Bedrohungen zu schützen.

> [!TIP]
> - Wenn Sie Microsoft 365 verwenden, sollten Sie Microsoft Defender Antivirus als primäre Antivirenlösung verwenden. Integration kann einen besseren Schutz bieten. Weitere Informationen finden Sie unter [Better together: Microsoft Defender Antivirus and Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Achten Sie darauf, Microsoft Defender Antivirus immer auf dem neuesten Stand zu halten, auch wenn Sie eine Nicht-Microsoft-Antivirenlösung verwenden.

## <a name="what-to-expect-when-threats-are-detected"></a>Was zu erwarten ist, wenn Bedrohungen erkannt werden

Wenn Bedrohungen von Microsoft Defender Antivirus erkannt werden, geschieht Folgendes:

- Benutzer erhalten [Benachrichtigungen in Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- Erkennungen werden in der [Windows-Sicherheit auf](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) der Seite **Schutzverlauf** aufgelistet.  
- Wenn Sie Ihre  [Windows 10-Geräte](secure-win-10-pcs.md) gesichert und in  [Intune](/mem/intune/enrollment/windows-enrollment-methods)registriert haben und In Ihrer Organisation 800 oder weniger Geräte registriert sind, werden Bedrohungserkennungen und Einblicke im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a> auf der Seite Bedrohungen und Antivirus angezeigt, auf die Sie über die **Microsoft Defender Antivirus-Karte** auf der Startseite zugreifen können (oder im Navigationsbereich, indem Sie Integritätsbedrohungen &   >  **Antivirus** auswählen).

    Wenn in Ihrer Organisation mehr als 800 Geräte in Intune registriert sind, werden Sie aufgefordert, Bedrohungserkennungen und -einblicke von [Microsoft Endpoint Manager](/mem/endpoint-manager-overview) statt auf der Seite Bedrohungen und Antivirus zu **sehen.**
 
    > [!NOTE]
    > Die **Microsoft Defender Antivirus** Karte und **die** Seite Bedrohungen und Antivirus werden in Phasen ausgeführt, sodass Sie möglicherweise keinen unmittelbaren Zugriff darauf haben.

In den meisten Fällen müssen Benutzer keine weiteren Aktionen ergreifen. Sobald eine schädliche Datei oder ein schädliches Programm auf einem Gerät erkannt wird, wird Microsoft Defender Antivirus blockiert und verhindert, dass es ausgeführt wird. Darüber hinaus werden dem Antivirus- und Antischantischantischungsmodul neu erkannte Bedrohungen hinzugefügt, sodass auch andere Geräte und Benutzer geschützt sind.  

Wenn ein Benutzer eine Aktion ergreifen muss, z. B. das Genehmigen des Entfernens einer schädlichen Datei, wird dies in der Benachrichtigung angezeigt, die er erhält. Weitere Informationen zu Aktionen, die Microsoft Defender Antivirus im Namen eines Benutzers ausführen, oder zu Aktionen, die Benutzer möglicherweise ausführen müssen, finden Sie unter [Protection History](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708). Informationen zum Verwalten von Bedrohungserkennungen als IT-Profi/Administrator finden Sie unter Überprüfen erkannter [Bedrohungen und Ergreifen von Maßnahmen.](review-threats-take-action.md)

Weitere Informationen zu verschiedenen Bedrohungen finden Sie auf der <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Microsoft Security Intelligence-Bedrohungswebsite,</a>auf der Sie die folgenden Aktionen ausführen können: 

- Aktuelle Informationen zu den obersten Bedrohungen anzeigen.
- Zeigen Sie die neuesten Bedrohungen für eine bestimmte Region an.
- Suchen Sie in der Bedrohungsenzyklopädie nach Details zu einer bestimmten Bedrohung.

## <a name="related-content"></a>Verwandte Inhalte

[Secure Windows 10 devices](secure-windows-10-devices.md) (article)\
[Bewerten Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (Artikel)\
[Aktivieren des In-Time- und Cloud-zugestellten Antivirenschutzes](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (Artikel)\
[Aktivieren und Verwenden von Microsoft Defender Antivirus der](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) Windows-Sicherheit App (Artikel)\
[Aktivieren der Microsoft Defender Antivirus mithilfe von Gruppenrichtlinien](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (Artikel)\
[Aktualisieren Der Antivirendefinitionen](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (Artikel)\
[So übermitteln Sie Schadsoftware und Nicht-Schadsoftware zur Analyse](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) an Microsoft (Artikel)
