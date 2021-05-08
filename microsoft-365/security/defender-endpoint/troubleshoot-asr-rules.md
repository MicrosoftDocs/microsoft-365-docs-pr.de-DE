---
title: Melden und Behandeln von Microsoft Defender for Endpoint-ASR-Regeln
description: In diesem Thema wird beschrieben, wie Sie Microsoft Defender for Endpoint -ASR-Regeln melden und Behandeln von Problemen behandeln.
keywords: Attack Surface Reduction Rules, Asr, Hips, Host Intrusion Prevention System, Protection Rules, Anti-Exploit, Antiexploit, Exploit, Infection Prevention, microsoft defender for endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: lovina-saldanha
ms.author: v-lsaldanha
ms.reviewer: ''
manager: dansimp
ms.custom: asr
ms.topic: article
ms.technology: mde
ms.openlocfilehash: c043e97d6c02e4f41d000e9ce8cfea4a0950252a
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246143"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a>Melden und Behandeln von Microsoft Defender für ATP-ASR-Regeln

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Das Microsoft 365 Security Center ist die neue Schnittstelle für die Überwachung und Verwaltung der Sicherheit in Ihren Microsoft-Identitäten, Daten, Geräten, Apps und Infrastruktur. Hier können Sie den Sicherheitsstatus Ihrer Organisation ganz einfach anzeigen, Geräte, Benutzer und Apps konfigurieren sowie Benachrichtigungen zu verdächtigen Aktivitäten erhalten. Das Microsoft 365 Security Center ist dazu bestimmt, Sicherheitsadministratoren und Sicherheitsteams zu ermöglichen, Verwaltung und Schutz Ihrer Organisation zu verbessern. Besuchen Sie Microsoft 365 Security Center unter https://security.microsoft.com .
In Microsoft 365 Security Center bieten wir Ihnen einen vollständigen Blick auf die aktuelle Konfiguration und Ereignisse von ASR-Regeln in Ihrem Nachlass. Beachten Sie, dass Ihre Geräte in den Microsoft Defender for Endpoint-Dienst integrierte werden müssen, damit diese Berichte aufgefüllt werden können.
Hier ist ein Screenshot der Microsoft 365 Security Center (unter **Berichte**  >  **Geräte**  >  **Attack surface reduction**). Wählen Sie auf Geräteebene **im** Bereich Attack **surface reduction** rules die Option Konfiguration aus. Der folgende Bildschirm wird angezeigt, auf dem Sie ein bestimmtes Gerät auswählen und die konfiguration der einzelnen ASR-Regel überprüfen können.

:::image type="content" source="images/asrrulesnew.png" alt-text="Bildschirm &quot;ASR-Regeln&quot;":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a>Microsoft Defender for Endpoint – Erweiterte Suche

Eines der leistungsstärksten Features von Microsoft Defender for Endpoint ist die erweiterte Suche. Wenn Sie mit der erweiterten Suche nicht vertraut sind, verweisen Sie proaktiv auf Bedrohungen mit [erweiterter Suche.](advanced-hunting-overview.md)

Bei der erweiterten Suche handelt es sich um ein abfragebasiertes (Kusto Query Language)-Tool zur Bedrohungssuche, mit dem Sie bis zu 30 Tage der erfassten (unformatierten) Daten erkunden können, die MDE Endpoint Detection and Response (EDR) von allen Computern sammelt. Durch die erweiterte Suche können Sie Ereignisse proaktiv überprüfen, um nach interessanten Indikatoren und Entitäten zu suchen. Der flexible Zugriff auf Daten hilft bei der ungesübten Suche nach bekannten und potenziellen Bedrohungen.

Durch die erweiterte Suche ist es möglich, Informationen zu ASR-Regeln zu extrahieren, Berichte zu erstellen und detaillierte Informationen zum Kontext eines bestimmten ASR-Regel-Audit- oder -Blockereignis zu erhalten.

ASR-Regelereignisse können in der DeviceEvents-Tabelle im Abschnitt erweiterte Suche des Microsoft Defender Security Center. Eine einfache Abfrage wie die folgende kann beispielsweise alle Ereignisse melden, die über ASR-Regeln als Datenquelle verfügen, für die letzten 30 Tage und fasst sie durch die ActionType-Anzahl zusammen, dass es sich in diesem Fall um den tatsächlichen Codenamen der ASR-Regel handeln wird.

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Erweiterte Suchabfrage":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="Erweiterter Jagdbildschirm":::

Mit der erweiterten Suche können Sie die Abfragen nach Ihren Wünschen gestalten, sodass Sie sehen können, was geschieht, unabhängig davon, ob Sie auf einem einzelnen Computer etwas bestimmen oder Einblicke aus Ihrer gesamten Umgebung extrahieren möchten.

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Microsoft Defender for Endpoint-Computerzeitachse

Eine Alternative zur erweiterten Suche, jedoch mit einem schmaleren Bereich, ist die Microsoft Defender for Endpoint-Computerzeitachse. Sie können alle erfassten Ereignisse eines Geräts in den letzten sechs Monaten im Microsoft Defender Security Center anzeigen, indem Sie zur Liste Computer einen bestimmten Computer auswählen und dann auf die Registerkarte Zeitachse klicken.

Nachfolgend sehen Sie einen Screenshot der Zeitachsenansicht dieser Ereignisse auf einem bestimmten Endpunkt.  In dieser Ansicht können Sie die Ereignisliste basierend auf allen Ereignisgruppen im rechten Bereich filtern. Sie können auch gekennzeichnete und ausführliche Ereignisse aktivieren oder deaktivieren, während Sie Warnungen anzeigen und einen Bildlauf durch die verlaufshistorische Zeitachse durchführen.

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Microsoft Defender Security Center-Zeitachse":::

## <a name="how-to-troubleshoot-asr-rules"></a>How to troubleshoot ASR rules?

Die erste und unmittelbarste Möglichkeit besteht in der lokalen Überprüfung auf einem Windows-Gerät, welche ASR-Regeln mit den PowerShell-Cmdlets aktiviert sind (und deren Konfiguration).

Hier sind einige weitere Informationsquellen, die Windows, um die Auswirkungen und den Betrieb von ASR-Regeln zu beheben.

### <a name="querying-which-rules-are-active"></a>Abfragen der aktiven Regeln
Eine der einfachsten Methoden, um zu ermitteln, ob DIE-Regeln bereits aktiviert sind – und, über ein PowerShell-Cmdlet, Get-MpPreference.
Hier ein Beispiel:

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="mppreference-Skript erhalten":::

Es sind mehrere ASR-Regeln mit unterschiedlichen konfigurierten Aktionen aktiv.

Zum Erweitern der obigen Informationen zu ASR-Regeln können Sie die Eigenschaften AttackSurfaceReductionRules_Ids **und/oder** **AttackSurfaceReductionRules_Actions.**

Beispiel:

*Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Ids*

:::image type="content" source="images/getmpref-examplenew.png" alt-text="mpreference-Beispiel erhalten":::

Im obigen Beispiel werden alle IDs für ASR-Regeln mit einer anderen Einstellung als 0 (Nicht konfiguriert) angezeigt.

Im nächsten Schritt werden dann die tatsächlichen Aktionen (Blockieren oder Überwachen) aufgeführt, mit der jede Regel konfiguriert ist. 

*Get-MPPreference | Select-Object -ExpandProperty**AttackSurfaceReductionRules_Actions*

:::image type="content" source="images/getmpref-example2new.png" alt-text="mppreference-Beispiel2 erhalten":::

### <a name="querying-blocking-and-auditing-events"></a>Abfragen von Blockieren und Überwachen von Ereignissen
ASR-Regelereignisse können im Windows Defender angezeigt werden.

Öffnen Sie zum Zugriff Windows Ereignisanzeige, und navigieren Sie zu Anwendungen und **Dienstprotokolle**  >  **Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.

:::image type="content" source="images/eventviewerscrnew.png" alt-text="event viewer scr":::

## <a name="microsoft-defender-malware-protection-logs"></a>Microsoft Defender Malware Protection Logs
Sie können Regelereignisse auch über das dedizierte Befehlszeilentool Microsoft Defender Antivirus, das zum Verwalten und Konfigurieren und Automatisieren von Aufgaben bei Bedarf verwendet werden `*mpcmdrun.exe*` kann, anzeigen.

Dieses Hilfsprogramm finden Sie unter *%ProgramFiles%\Windows Defender\MpCmdRun.exe*. Sie müssen ihn über eine Eingabeaufforderung mit erhöhten Rechten ausführen (d. h. als Administrator ausführen).

Geben Sie zum Generieren der Supportinformationen *MpCmdRun.exe -getfiles ein.* Nach einer Weile werden mehrere Protokolle in einem Archiv (MpSupportFiles.cab) verpackt und in *C:\ProgramData\Microsoft\Windows Defender\Support verfügbar gemacht.*

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="Malwareschutzprotokolle":::

Extrahieren Sie dieses Archiv, und Sie haben viele Dateien zur Problembehandlung zur Verfügung.

Die relevantesten Dateien sind wie folgt:

- **MPOperationalEvents.txt** – Diese Datei enthält die gleiche Informationsebene, die in der Ereignisanzeige für Windows Defender Betriebsprotokoll gefunden wurde.
- **MPRegistry.txt** – In dieser Datei können Sie alle aktuellen konfigurationen Windows Defender analysieren, ab dem Zeitpunkt, zu dem die Supportprotokolle erfasst wurden.
- **MPLog.txt** – Dieses Protokoll enthält ausführlichere Informationen zu allen Aktionen/Vorgängen der Windows Defender.
