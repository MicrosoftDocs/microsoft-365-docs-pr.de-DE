---
title: Von Microsoft Defender Antivirus erkannte Bedrohungen
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
description: Erfahren Sie, wie Microsoft Defender Antivirus Ihre Windows-Geräte vor Software Bedrohungen wie Viren, Schadsoftware und Spyware schützt.
ms.openlocfilehash: e3c8a1071625bba41af5f3cccd50f8484acac18d
ms.sourcegitcommit: 20d1158c54a5058093eb8aac23d7e4dc68054688
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/21/2020
ms.locfileid: "49376713"
---
# <a name="threats-detected-by-microsoft-defender-antivirus"></a>Von Microsoft Defender Antivirus erkannte Bedrohungen

Microsoft Defender Antivirus schützt Ihre Windows-Geräte vor Software Bedrohungen wie Viren, Schadsoftware und Spyware.

- Viren werden normalerweise durch Anfügen Ihres Codes an andere Dateien auf Ihrem Gerät oder Netzwerk verbreitet und können dazu führen, dass infizierte Programme nicht ordnungsgemäß funktionieren.
- Schadsoftware umfasst schädliche Dateien, Anwendungen und Code, die zu Beschädigungen und zur Unterbrechung der normalen Verwendung von Geräten führen können. Schadsoftware kann auch nicht autorisierten Zugriff erlauben, Systemressourcen verwenden, Kennwörter und Kontoinformationen stehlen, Sie von Ihrem Computer sperren und um Lösegeld bitten und vieles mehr.
- Spyware sammelt Daten, beispielsweise Webbrowsing-Aktivitäten, und sendet die Daten an Remoteserver.
 
Um den Schutz vor Bedrohungen zu gewährleisten, verwendet Microsoft Defender Antivirus mehrere Methoden. Diese Methoden umfassen Cloud-gelieferten Schutz, Echtzeitschutz und dedizierte Schutzupdates.

- Der in der Cloud bereitgestellte Schutz hilft bei der sofortigen Erkennung und Blockierung neuer und neu auftretender Bedrohungen.
- Bei der permanenten Überprüfung werden Datei-und Prozess Verhaltensüberwachung und andere Techniken (auch als *Echtzeitschutz* bezeichnet) verwendet.
- Dedizierte Schutzupdates basieren auf dem maschinellen lernen, der Human-und der automatisierten Big-Data-Analyse und der detaillierten Bedrohungs Resistenz-Forschung. 

Weitere Informationen zu Schadsoftware und Microsoft Defender Antivirus finden Sie in den folgenden Artikeln: 

- [Grundlegendes zu Malware & anderen Bedrohungen](/windows/security/threat-protection/intelligence/understanding-malware)
- [Identifizieren von Schadsoftware und potenziell unerwünschten Anwendungen durch Microsoft](/windows/security/threat-protection/intelligence/criteria)
- [Schutz der nächsten Generation in Windows 10](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)

## <a name="what-happens-when-a-non-microsoft-antivirus-solution-is-used"></a>Was geschieht, wenn eine Antivirenlösung von Drittanbietern verwendet wird? 

Microsoft Defender Antivirus ist Bestandteil des Betriebssystems und ist auf Geräten mit Windows 10 aktiviert. Wenn Sie jedoch eine nicht-Microsoft-Antivirenlösung verwenden und [Microsoft Defender für Endpoint](/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)nicht verwenden, wechselt Microsoft Defender Antivirus automatisch in den Modus "deaktiviert".  

Im Modus "deaktiviert" können Benutzer und Kunden weiterhin Microsoft Defender Antivirus für geplante oder bedarfsgesteuerte Scans verwenden, um Bedrohungen zu identifizieren. Allerdings wird Microsoft Defender Antivirus nicht mehr:

- als standardmäßige Antivirus-App verwendet werden.
- aktives überprüfen von Dateien auf Bedrohungen.
- Beheben von Bedrohungen.

Wenn Sie die Antivirensoftware von Drittanbietern deinstallieren, wechselt Microsoft Defender Antivirus automatisch in den aktiven Modus, um Ihre Windows-Geräte vor Bedrohungen zu schützen.

> [!TIP]
> - Wenn Sie Microsoft 365 verwenden, sollten Sie Microsoft Defender Antivirus als primäre Antivirus-Lösung verwenden. Integration kann einen besseren Schutz bieten. Siehe [besser zusammen: Microsoft Defender Antivirus und Office 365](/windows/security/threat-protection/microsoft-defender-antivirus/office-365-microsoft-defender-antivirus).
> - Stellen Sie sicher, dass Sie Microsoft Defender Antivirus auf dem neuesten Stand halten, auch wenn Sie eine nicht von Microsoft bereitgestellten Antivirus-Lösung verwenden.

## <a name="what-to-expect-when-threats-are-detected"></a>Was erwartet werden soll, wenn Bedrohungen erkannt werden

Wenn Bedrohungen von Microsoft Defender Antivirus erkannt werden, passieren die folgenden Dinge:

- Benutzer erhalten [Benachrichtigungen in Windows](https://support.microsoft.com/windows/8942c744-6198-fe56-4639-34320cf9444e). 
- Erkennungen werden in der [Windows-Sicherheits-App](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) auf der Seite **Schutz Verlauf** aufgeführt.  
- Wenn Sie [Ihre Windows 10-Geräte gesichert](secure-win-10-pcs.md) haben [und diese in InTune registriert](/mem/intune/enrollment/windows-enrollment-methods)haben, werden Sie auf der Seite "aktive Bedrohungen" im <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 Admin Center</a> auf der Seite " **aktive Bedrohungen** ", **auf die Sie** über die **Microsoft Defender-antiviruskarte** zugreifen können (oder über den Navigationsbereich, indem Sie **Integritäts**  >  **Bedrohungen & Antivirus** auswählen), zu Bedrohungen erkannt und Einblicke erhalten.
    > [!NOTE]
    > Auf der Seite **Microsoft Defender Antivirus** -Karte und **aktive Bedrohungen** wird in Phasen ein Rollback ausgeführt, sodass Sie möglicherweise keinen unmittelbaren Zugriff darauf haben.

In den meisten Fällen müssen Benutzer keine weiteren Aktionen durchführen. Sobald eine bösartige Datei oder ein infiziertes Programm auf einem Gerät erkannt wird, blockiert Microsoft Defender Antivirus diese und verhindert die Ausführung. Außerdem werden dem Antivirus-und Antischadsoftware-Modul neu erkannte Bedrohungen hinzugefügt, damit auch andere Geräte und Benutzer geschützt sind.  

Wenn ein Benutzer eine Aktion ausführen muss, beispielsweise das Entfernen einer schädlichen Datei genehmigen, wird dies in der Benachrichtigung angezeigt, die Sie erhalten. Weitere Informationen zu Aktionen, die Microsoft Defender Antivirus im Auftrag eines Benutzers ausführt, oder Aktionen, die Benutzer möglicherweise ausführen müssen, finden Sie unter [Protection History](https://support.microsoft.com/office/f1e5fd95-09b4-46d1-b8c7-1059a1e09708). Informationen zum Verwalten von Bedrohungserkennungen als IT-Experte/Administrator finden Sie unter [überprüfen erkannter Bedrohungen und ergreifen von Aktionen](review-threats-take-action.md).

Weitere Informationen zu verschiedenen Bedrohungen finden Sie auf der <a href="https://www.microsoft.com/wdsi/threats" target="_blank">Website Microsoft Security Intelligence Threats</a>, auf der Sie die folgenden Aktionen ausführen können: 

- Hier werden aktuelle Informationen zu wichtigsten Bedrohungen angezeigt.
- Anzeigen der neuesten Bedrohungen für eine bestimmte Region.
- Durchsuchen Sie die Bedrohungs Enzyklopädie nach Details zu einer bestimmten Bedrohung.

## <a name="related-content"></a>Verwandte Inhalte

[Sichere Windows 10-Geräte](secure-windows-10-devices.md) (Artikel) \
[Auswerten von Microsoft Defender Antivirus](/windows/security/threat-protection/microsoft-defender-antivirus/evaluate-microsoft-defender-antivirus) (Artikel) \
[Aktivieren von Echtzeitfunktionen und von der Cloud bereitgestellten Antivirenschutz](/mem/intune/user-help/turn-on-defender-windows#turn-on-real-time-and-cloud-delivered-protection) (Artikel) \
[Vorgehensweise aktivieren und Verwenden von Microsoft Defender Antivirus aus der Windows-Sicherheits-App](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-security-center-antivirus) (Artikel) \
[Vorgehensweise Aktivieren von Microsoft Defender Antivirus mithilfe von Gruppenrichtlinien](/mem/intune/user-help/turn-on-defender-windows#turn-on-windows-defender) (Artikel) \
[Aktualisieren der Antivirus-Definitionen](/mem/intune/user-help/turn-on-defender-windows#update-your-antivirus-definitions) (Artikel) \
[Vorgehensweise übermitteln von Schadsoftware und nicht-Schadsoftware an Microsoft zur Analyse](/microsoft-365/security/office-365-security/submitting-malware-and-non-malware-to-microsoft-for-analysis) (Artikel)