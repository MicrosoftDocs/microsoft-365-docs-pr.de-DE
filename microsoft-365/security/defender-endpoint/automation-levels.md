---
title: Automatisierungsstufen bei der automatischen Untersuchung und Behebung
description: Erhalten Sie einen Überblick über Automatisierungsstufen und deren Funktionsweise in Microsoft Defender für Endpunkt
keywords: automatisiert, Untersuchung, Ebene, Microsoft Defender für Endpunkt
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
ms.openlocfilehash: 6d453a8b6e5c4947c0fb03131c539b083227c28a
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844646"
---
# <a name="automation-levels-in-automated-investigation-and-remediation-capabilities"></a>Automatisierungsebenen bei automatisierten Untersuchungs- und Korrekturfunktionen

**Gilt für:**
- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Air-Funktionen (Automated Investigation and Remediation) in Microsoft Defender für Endpunkt können auf eine von mehreren Automatisierungsebenen konfiguriert werden. Ihre Automatisierungsstufe wirkt sich darauf aus, ob Korrekturmaßnahmen nach AIR-Untersuchungen automatisch oder nur nach Genehmigung durchgeführt werden.  
- *Vollständige Automatisierung* (empfohlen) bedeutet, dass Korrekturmaßnahmen automatisch für Artefakte ausgeführt werden, die als bösartig eingestuft wurden.
- *Semiautomatisierung* bedeutet, dass einige Korrekturmaßnahmen automatisch ausgeführt werden, aber andere Korrekturaktionen warten auf die Genehmigung, bevor sie ausgeführt werden. (Siehe Die Tabelle in [den Automatisierungsebenen.)](#levels-of-automation)
- Alle Korrekturaktionen , ob ausstehend oder abgeschlossen, werden im Info-Center ( ) nachverfolgt. [https://securitycenter.windows.com](https://securitycenter.windows.com) 

> [!TIP]
> Um optimale Ergebnisse zu erzielen, empfehlen wir die Verwendung der vollständigen Automatisierung, wenn Sie [AIR konfigurieren.](configure-automated-investigations-remediation.md) Daten, die im letzten Jahr gesammelt und analysiert wurden, zeigen, dass Kunden, die die vollständige Automatisierung verwenden, 40 % mehr besonders vertrauenswürdige Schadsoftwarebeispiele entfernt wurden als Kunden, die eine niedrigere Automatisierungsstufe verwenden. Die vollständige Automatisierung kann Ihnen helfen, Ihre Ressourcen für den Sicherheitsbetrieb freizugeben, um sich mehr auf Ihre strategischen Initiativen zu konzentrieren.

## <a name="levels-of-automation"></a>Automatisierungsebenen

In der folgenden Tabelle werden die einzelnen Automatisierungsebenen und ihre Funktionsweise beschrieben.

|Automatisierungsebene | Beschreibung|
|:---|:---|
|**Vollständig – Bedrohungen automatisch beheben** <br/>(auch als *vollständige Automatisierung* bezeichnet)| Bei vollständiger Automatisierung werden Korrekturaktionen automatisch ausgeführt. Alle durchgeführten Korrekturaktionen können im [Info-Center](auto-investigation-action-center.md) auf der Registerkarte **"Verlauf"** angezeigt werden. Bei Bedarf kann eine Korrekturaktion rückgängig sein.<br/><br/>**_Die vollständige Automatisierung wird empfohlen_* und ist standardmäßig für Mandanten ausgewählt, die am oder nach dem 16. August 2020 mit Microsoft Defender für Endpunkt erstellt wurden, ohne dass gerätegruppen noch definiert wurden.*  |
|**Semi – Genehmigung für jede Korrektur erforderlich** <br/>(wird auch als *Semiautomatisierung* bezeichnet)| Bei dieser Stufe der Halbautomatisierung ist eine Genehmigung für *alle* Korrekturmaßnahmen erforderlich. Solche ausstehenden Aktionen können im [Info-Center](auto-investigation-action-center.md)auf der Registerkarte **"Ausstehend"** angezeigt und genehmigt werden.<br/><br/>*Diese Stufe der Semiautomatisierung ist standardmäßig für Mandanten ausgewählt, die vor dem 16. August 2020 mit Microsoft Defender für Endpunkt erstellt wurden, ohne dass Gerätegruppen definiert wurden.*|
|**Semi – Genehmigung für Kernordner-Korrektur erforderlich** <br/>(auch eine Art *semi-automation*)  | Bei dieser Stufe der Semiautomatisierung ist die Genehmigung für alle Korrekturaktionen erforderlich, die für Dateien oder ausführbare Dateien in Kernordnern erforderlich sind. Zu den Kernordnern gehören Betriebssystemverzeichnisse, z. **B.** die Windows ( `\windows\*` ).<br/><br/>Korrekturmaßnahmen können automatisch für Dateien oder ausführbare Dateien ausgeführt werden, die sich in anderen (nicht im Kern enthaltenen) Ordnern befinden. <br/><br/>Ausstehende Aktionen für Dateien oder ausführbare Dateien in Kernordnern können im [Info-Center](auto-investigation-action-center.md)auf der Registerkarte **"Ausstehend"** angezeigt und genehmigt werden. <br/><br/>Aktionen, die für Dateien oder ausführbare Dateien in anderen Ordnern ausgeführt wurden, können im [Info-Center](auto-investigation-action-center.md)auf der Registerkarte **"Verlauf"** angezeigt werden. |
|**Semi – Genehmigung für Nicht-Temp-Ordner-Korrektur erforderlich** <br/>(auch eine Art *semi-automation*)| Bei dieser Stufe der Semiautomatisierung ist die Genehmigung für alle Korrekturaktionen erforderlich, die für Dateien oder ausführbare Dateien erforderlich sind, die *sich nicht* in temporären Ordnern befinden. <br/><br/>Temporäre Ordner können die folgenden Beispiele enthalten: <br/>- `\users\*\appdata\local\temp\*`<br/>- `\documents and settings\*\local settings\temp\*` <br/>- `\documents and settings\*\local settings\temporary\*`<br/>- `\windows\temp\*`<br/>- `\users\*\downloads\*`<br/>- `\program files\` <br/>- `\program files (x86)\*`<br/>- `\documents and settings\*\users\*`<br/><br/>Korrekturmaßnahmen können automatisch für Dateien oder ausführbare Dateien ausgeführt werden, die sich in temporären Ordnern befinden. <br/><br/>Ausstehende Aktionen für Dateien oder ausführbare Dateien, die sich nicht in temporären Ordnern befinden, können im [Info-Center](auto-investigation-action-center.md)auf der Registerkarte **"Ausstehend"** angezeigt und genehmigt werden.<br/><br/>Aktionen, die für Dateien oder ausführbare Dateien in temporären Ordnern ausgeführt wurden, können im [Info-Center](auto-investigation-action-center.md)auf der Registerkarte **"Verlauf"** angezeigt und genehmigt werden.   |
|**Keine automatisierte Antwort** <br/>(wird auch als *"keine Automatisierung"* bezeichnet) | Ohne Automatisierung wird die automatisierte Untersuchung nicht auf den Geräten Ihrer Organisation ausgeführt. Infolgedessen werden aufgrund einer automatisierten Untersuchung keine Korrekturmaßnahmen ergriffen oder ausstehend. Je nachdem, wie Ihre Antivirus- und Die Nächste Generation der Schutzfunktionen konfiguriert sind, können jedoch andere Bedrohungsschutzfeatures, z. B. [schutz vor potenziell unerwünschten Anwendungen,](/windows/security/threat-protection/microsoft-defender-antivirus/detect-block-potentially-unwanted-apps-microsoft-defender-antivirus)wirksam sein.<br/><br/>***Die Verwendung der Option *"Keine Automatisierung"* wird nicht empfohlen,** da dadurch der Sicherheitsstatus der Geräte Ihrer Organisation reduziert wird. Erwägen Sie die [Einrichtung Ihrer Automatisierungsstufe für die vollständige Automatisierung (oder zumindest die Semiautomatisierung).](/microsoft-365/security/defender-endpoint/machine-groups) |

## <a name="important-points-about-automation-levels"></a>Wichtige Punkte zu Automatisierungsebenen

- Die vollständige Automatisierung hat sich als zuverlässig, effizient und sicher erwiesen und wird für alle Kunden empfohlen. Die vollständige Automatisierung gibt Ihre kritischen Sicherheitsressourcen frei, damit sie sich mehr auf Ihre strategischen Initiativen konzentrieren können.

- Neue Mandanten (einschließlich Mandanten, die am oder nach dem 16. August 2020 erstellt wurden) mit Microsoft Defender für Endpunkt sind standardmäßig auf die vollständige Automatisierung festgelegt.

- Wenn Ihr Sicherheitsteam Gerätegruppen mit einem Automatisierungsgrad definiert hat, werden diese Einstellungen nicht durch die neuen Standardeinstellungen geändert, die bereitgestellt werden. 

- Sie können Ihre Standardautomatisierungseinstellungen beibehalten oder entsprechend den Anforderungen Ihrer Organisation ändern. Um Ihre Einstellungen zu ändern, [legen Sie den Automatisierungsgrad fest.](/microsoft-365/security/defender-endpoint/configure-automated-investigations-remediation#set-up-device-groups)

## <a name="next-steps"></a>Nächste Schritte

- [Konfigurieren automatisierter Untersuchungs- und Korrekturfunktionen in Microsoft Defender für Endpunkt](configure-automated-investigations-remediation.md)

- [Besuchen Sie das Info-Center](/microsoft-365/security/defender-endpoint/auto-investigation-action-center#the-action-center)
