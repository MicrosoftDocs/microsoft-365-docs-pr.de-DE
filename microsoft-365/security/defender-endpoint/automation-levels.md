---
title: Automatisierungsebenen bei automatisierter Untersuchung und Behebung
description: Erhalten Sie eine Übersicht über Automatisierungsstufen und deren Funktionsweise in Microsoft Defender for Endpoint
keywords: automatisiert, Untersuchung, Ebene, Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: JoeDavies-MSFT
ms.author: josephd
ms.date: 10/22/2020
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.reviewer: ramarom, evaldm, isco, mabraitm, chriggs
ms.custom: AIR
ms.openlocfilehash: ba206002415fcd4ae968cc88563136399b78f435
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274774"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>Automatisierungsebenen in automatisierten Untersuchungs- und Behebungsfunktionen

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Funktionen für die automatisierte Untersuchung und Korrektur (AIR) in Microsoft Defender for Endpoint können auf eine von mehreren Automatisierungsebenen konfiguriert werden. Ihre Automatisierungsebene wirkt sich darauf aus, ob Korrekturmaßnahmen nach AIR-Untersuchungen automatisch oder nur nach Genehmigung ausgeführt werden.  
- *Vollständige Automatisierung* (empfohlen) bedeutet, dass Korrekturaktionen automatisch für Artefakte ausgeführt werden, die als bösartig ermittelt wurden.
- *Semiautomatisierung* bedeutet, dass einige Korrekturaktionen automatisch ausgeführt werden, aber andere Korrekturaktionen warten auf die Genehmigung, bevor sie ausgeführt werden. (Siehe Tabelle unter [Automatisierungsebenen](#levels-of-automation).)
- Alle Korrekturaktionen, ob ausstehend oder abgeschlossen, werden im Action Center ( ) nachverfolgt. [https://securitycenter.windows.com](https://securitycenter.windows.com) 

> [!TIP]
> Für optimale Ergebnisse wird empfohlen, bei der Konfiguration von AIR die vollständige [Automatisierung zu verwenden.](configure-automated-investigations-remediation.md) Daten, die im vergangenen Jahr gesammelt und analysiert wurden, zeigen, dass Kunden, die vollautomatisierung verwenden, 40 % mehr besonders vertrauensbedenkte Schadsoftwarebeispiele entfernt wurden als Kunden, die niedrigere Automatisierungsebenen verwenden. Die vollständige Automatisierung kann Ihnen helfen, Ressourcen für den Sicherheitsbetrieb frei zu lassen, um sich stärker auf Ihre strategischen Initiativen zu konzentrieren.

## <a name="levels-of-automation"></a>Automatisierungsebenen

In der folgenden Tabelle werden die einzelnen Automatisierungsebenen und deren Funktionsweise beschrieben.

|Automatisierungsebene | Beschreibung|
|:---|:---|
|**Vollständig – Automatische Behebung von Bedrohungen** <br/>(wird auch als *vollautomatisierung bezeichnet*)| Bei vollständiger Automatisierung werden Korrekturaktionen automatisch ausgeführt. Alle ergriffenen Korrekturaktionen können im [Aktionscenter](auto-investigation-action-center.md) auf der Registerkarte **Verlauf angezeigt** werden. Bei Bedarf kann eine Korrekturaktion rückgängig gemacht werden.<br/><br/>**_Die vollständige_* Automatisierung wird empfohlen und ist standardmäßig für Mandanten ausgewählt, die am oder nach dem 16. August 2020 mit Microsoft Defender for Endpoint erstellt wurden, ohne dass noch keine Gerätegruppen definiert sind.*  |
|**Semi – Genehmigung für alle Korrekturen erforderlich** <br/>(wird auch als *Semiautomatisierung bezeichnet*)| Bei dieser Stufe der Semiautomatisierung ist eine Genehmigung für *alle Korrekturmaßnahmen* erforderlich. Solche ausstehenden Aktionen können im [Aktionscenter](auto-investigation-action-center.md)auf der Registerkarte Ausstehend angezeigt **und genehmigt** werden.<br/><br/>*Diese Stufe der Semiautomatisierung wird standardmäßig für Mandanten ausgewählt, die vor dem 16. August 2020 mit Microsoft Defender for Endpoint erstellt wurden, ohne dass Gerätegruppen definiert wurden.*|
|**Semi – Erfordert die Genehmigung für die Korrektur von Kernordnern** <br/>(auch eine Art *von Semiautomatisierung*)  | Bei dieser Stufe der Semiautomatisierung ist die Genehmigung für alle Korrekturaktionen erforderlich, die für Dateien oder ausführbare Dateien in Kernordnern erforderlich sind. Zu den Hauptordnern gehören Betriebssystemverzeichnissen, z. **B. Windows** ( `\windows\*` ).<br/><br/>Korrekturaktionen können automatisch für Dateien oder ausführbare Dateien ausgeführt werden, die sich in anderen Ordnern (nicht im Kern) befinden. <br/><br/>Ausstehende Aktionen für Dateien oder ausführbare Dateien in Kernordnern können im [Aktionscenter](auto-investigation-action-center.md)auf der Registerkarte **Ausstehend angezeigt und** genehmigt werden. <br/><br/>Aktionen, die für Dateien oder ausführbare Dateien in anderen Ordnern ausgeführt wurden, können im [Aktionscenter](auto-investigation-action-center.md)auf der Registerkarte **Verlauf angezeigt** werden. |
|**Semi – Genehmigung für nicht temporäre Ordnerbehebung erforderlich** <br/>(auch eine Art *von Semiautomatisierung*)| Bei dieser Stufe der Semiautomatisierung ist eine Genehmigung für alle Korrekturaktionen erforderlich, die für Dateien oder ausführbare Dateien erforderlich sind, die sich *nicht* in temporären Ordnern befinden. <br/><br/>Temporäre Ordner können die folgenden Beispiele enthalten: <br/>- `\users\*\appdata\local\temp\*`<br/>- `\documents and settings\*\local settings\temp\*` <br/>- `\documents and settings\*\local settings\temporary\*`<br/>- `\windows\temp\*`<br/>- `\users\*\downloads\*`<br/>- `\program files\` <br/>- `\program files (x86)\*`<br/>- `\documents and settings\*\users\*`<br/><br/>Korrekturaktionen können automatisch für Dateien oder ausführbare Dateien ausgeführt werden, die sich in temporären Ordnern befinden. <br/><br/>Ausstehende Aktionen für Dateien oder ausführbare Dateien, die sich nicht in temporären Ordnern befinden, können im [Aktionscenter](auto-investigation-action-center.md)auf der Registerkarte **Ausstehend** angezeigt und genehmigt werden.<br/><br/>Aktionen, die für Dateien oder ausführbare Dateien in temporären Ordnern ausgeführt wurden, können im [Aktionscenter](auto-investigation-action-center.md)auf der Registerkarte Verlauf angezeigt und **genehmigt** werden.   |
|**Keine automatisierte Antwort** <br/>(auch als keine *Automatisierung bezeichnet*) | Ohne Automatisierung wird die automatisierte Untersuchung nicht auf den Geräten Ihrer Organisation ausgeführt. Aus diesem Grund werden keine Korrekturaktionen als Ergebnis einer automatisierten Untersuchung ergriffen oder ausstehend. Je nachdem, wie Ihre Antiviren- und Schutzfunktionen der nächsten Generation konfiguriert [sind,](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)können jedoch andere Bedrohungsschutzfeatures wirksam werden, z. B. schutz vor potenziell unerwünschten Anwendungen.<br/><br/>***Es wird *nicht empfohlen,* die Option "Keine** Automatisierung" zu verwenden, da dadurch die Sicherheitslage der Geräte Ihrer Organisation reduziert wird. [Erwägen Sie, Ihre Automatisierungsebene auf vollständige Automatisierung (oder zumindest semiautomatisierung) *](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/machine-groups)zu setzen. |

## <a name="important-points-about-automation-levels"></a>Wichtige Punkte zu Automatisierungsstufen

- Die vollständige Automatisierung hat sich als zuverlässig, effizient und sicher erwiesen und wird für alle Kunden empfohlen. Durch die vollständige Automatisierung werden Ihre kritischen Sicherheitsressourcen frei, sodass sie sich stärker auf Ihre strategischen Initiativen konzentrieren können.

- Neue Mandanten (zu denen Mandanten gehören, die am oder nach dem 16. August 2020 erstellt wurden) mit Microsoft Defender for Endpoint sind standardmäßig auf vollautomatisierung festgelegt.

- Wenn Ihr Sicherheitsteam Gerätegruppen mit automatisierungsorientiertem Maß definiert hat, werden diese Einstellungen nicht durch die neuen Standardeinstellungen geändert, die jetzt ins Rollen gebracht werden. 

- Sie können Ihre Standardautomatisierungseinstellungen behalten oder entsprechend Ihren organisatorischen Anforderungen ändern. Wenn Sie Ihre Einstellungen ändern möchten, [legen Sie den Automatisierungsgrad ein.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups)

## <a name="next-steps"></a>Nächste Schritte

- [Konfigurieren automatisierter Untersuchungs- und Korrekturfunktionen in Microsoft Defender for Endpoint](configure-automated-investigations-remediation.md)

- [Besuchen Sie das Action Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
