---
title: Melden und Beheben von Problemen mit Microsoft Defender für Endpunkt-ASR-Regeln
description: In diesem Thema wird beschrieben, wie Microsoft Defender für Endpunkt-ASR-Regeln gemeldet und Problembehandlung ausgeführt wird.
keywords: Attack Surface Reduction-Regeln, Asr, Hips, Host Intrusion Prevention System, Schutzregeln, Anti-Exploit, Antiexploit, Exploit, Infektionsverhinderung, Microsoft Defender für Endpunkt
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
ms.openlocfilehash: 65e3e8d1baef7ca4440824c9a262f0b5f696b657
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194745"
---
# <a name="report-and-troubleshoot-microsoft-defender-for-atp-asr-rules"></a>Melden und Beheben von Problemen mit Microsoft Defender für ATP ASR-Regeln

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**Gilt für:**

- [Microsoft Defender für Endpunkt](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

Das Microsoft 365 Security Center ist die neue Schnittstelle für die Überwachung und Verwaltung der Sicherheit über Ihre Microsoft-Identitäten, Daten, Geräte, Apps und Infrastruktur hinweg. Hier können Sie den Sicherheitsstatus Ihrer Organisation ganz einfach anzeigen, Geräte, Benutzer und Apps konfigurieren sowie Benachrichtigungen zu verdächtigen Aktivitäten erhalten. Das Microsoft 365 Security Center ist dazu bestimmt, Sicherheitsadministratoren und Sicherheitsteams zu ermöglichen, Verwaltung und Schutz Ihrer Organisation zu verbessern. Besuchen Sie das Microsoft 365 Security Center unter https://security.microsoft.com .
In Microsoft 365 Security Center bieten wir Ihnen einen vollständigen Überblick über die aktuelle KONFIGURATION und Ereignisse von ASR-Regeln in Ihrem Bestand. Beachten Sie, dass Ihre Geräte in den Microsoft Defender für Endpunktdienst integriert werden müssen, damit diese Berichte ausgefüllt werden können.
Hier ist ein Screenshot aus dem Microsoft 365 Security Center (unter **Attack** Surface Reduction für Berichte  >  **für Geräte).**  >   Wählen Sie auf Geräteebene im Regelbereich zur Verringerung der **Angriffsfläche** die Option **"Konfiguration"** aus. Der folgende Bildschirm wird angezeigt, auf dem Sie ein bestimmtes Gerät auswählen und dessen individuelle ASR-Regelkonfiguration überprüfen können.

:::image type="content" source="images/asrrulesnew.png" alt-text="ASR-Regelbildschirm":::

## <a name="microsoft-defender-for-endpoint--advanced-hunting"></a>Microsoft Defender für Endpunkt – Erweiterte Suche

Eines der leistungsstärksten Features von Microsoft Defender für Endpunkt ist die erweiterte Suche. Wenn Sie mit der erweiterten Suche nicht vertraut sind, suchen Sie [proaktiv nach Bedrohungen mit der erweiterten Suche.](advanced-hunting-overview.md)

Die erweiterte Suche ist ein abfragebasiertes (Kusto Query Language) Bedrohungssuche-Tool, mit dem Sie bis zu 30 Tage der erfassten (unformatierten) Daten, die Defender für Endpunkt von Ihren Geräten erfasst. Durch die erweiterte Suche können Sie Ereignisse proaktiv untersuchen, um interessante Indikatoren und Entitäten zu finden. Der flexible Zugriff auf Daten hilft bei der uneingeschränkte Suche nach bekannten und potenziellen Bedrohungen.

Durch die erweiterte Suche ist es möglich, ASR-Regelinformationen zu extrahieren, Berichte zu erstellen und ausführliche Informationen zum Kontext einer bestimmten ASR-Regelüberwachung oder eines Bestimmten Blockereignisses abzurufen.

ASR-Regelereignisse können in der DeviceEvents-Tabelle im Abschnitt "Erweiterte Suche" des Microsoft Defender Security Center abgefragt werden. Beispielsweise kann eine einfache Abfrage wie die folgende alle Ereignisse melden, die ASR-Regeln als Datenquelle für die letzten 30 Tage aufweisen, und diese anhand der ActionType-Anzahl zusammenfassen, in diesem Fall ist dies der tatsächliche Codename der ASR-Regel.

:::image type="content" source="images/adv-hunt-querynew.png" alt-text="Erweiterte Suchabfrage":::

:::image type="content" source="images/adv-hunt-sc-2new.png" alt-text="Bildschirm &quot;Erweiterte Suche&quot;":::

Mit der erweiterten Suche können Sie die Abfragen nach Ihren Wünschen gestalten, damit Sie sehen können, was geschieht, unabhängig davon, ob Sie etwas auf einem einzelnen Computer anheften oder Einblicke aus Ihrer gesamten Umgebung extrahieren möchten.

## <a name="microsoft-defender-for-endpoint-machine-timeline"></a>Computerzeitachse von Microsoft Defender für Endpunkt

Eine Alternative zur erweiterten Suche, jedoch mit einem schmaleren Bereich, ist die Microsoft Defender für Endpunkt-Computerzeitachse. Sie können alle erfassten Ereignisse eines Geräts für die letzten sechs Monate im Microsoft Defender Security Center anzeigen, indem Sie zur Computerliste wechseln, einen bestimmten Computer auswählen und dann auf die Registerkarte Zeitachse klicken.

Unten ist ein Screenshot der Zeitachsenansicht dieser Ereignisse auf einem bestimmten Endpunkt dargestellt.  Aus dieser Ansicht können Sie die Ereignisliste basierend auf einer der Ereignisgruppen im rechten Bereich filtern. Sie können auch gekennzeichnete und ausführliche Ereignisse aktivieren oder deaktivieren, während Sie Warnungen anzeigen und einen Bildlauf durch die verlaufsbezogene Zeitachse ausführen.

:::image type="content" source="images/mic-sec-def-timelinenew.png" alt-text="Microsoft Defender Security Center-Zeitachse":::

## <a name="how-to-troubleshoot-asr-rules"></a>Problembehandlung bei ASR-Regeln

Die erste und direkteste Möglichkeit besteht darin, lokal auf einem Windows Gerät zu überprüfen, welche ASR-Regeln aktiviert sind (und deren Konfiguration) mithilfe der PowerShell-Cmdlets erfolgt.

Hier sind einige weitere Informationsquellen, die Windows bietet, um die Auswirkungen und den Betrieb von ASR-Regeln zu behandeln.

### <a name="querying-which-rules-are-active"></a>Abfragen, welche Regeln aktiv sind
Eine der einfachsten Möglichkeiten, um festzustellen, ob ASR-Regeln bereits aktiviert sind, ist das PowerShell-Cmdlet "Get-MpPreference".
Hier ist ein Beispiel:

:::image type="content" source="images/getmpreferencescriptnew.png" alt-text="mppreference-Skript abrufen":::

Es sind mehrere ASR-Regeln mit unterschiedlichen konfigurierten Aktionen aktiv.

Um die oben genannten Informationen zu ASR-Regeln zu erweitern, können Sie die Eigenschaften **AttackSurfaceReductionRules_Ids** und/oder **AttackSurfaceReductionRules_Actions** verwenden.

Beispiel:

*Get-MPPreference | Select-Object -ExpandProperty**-AttackSurfaceReductionRules_Ids*

:::image type="content" source="images/getmpref-examplenew.png" alt-text="beispiel für &quot;get mpreference&quot;":::

Im obigen Beispiel werden alle IDs für ASR-Regeln angezeigt, deren Einstellung sich von 0 unterscheidet (nicht konfiguriert).

Im nächsten Schritt werden dann die tatsächlichen Aktionen (Blockieren oder Überwachen) aufgeführt, mit denen jede Regel konfiguriert ist. 

*Get-MPPreference | Select-Object -ExpandProperty**-AttackSurfaceReductionRules_Actions*

:::image type="content" source="images/getmpref-example2new.png" alt-text="get mppreference example2":::

### <a name="querying-blocking-and-auditing-events"></a>Abfragen von Blockierungs- und Überwachungsereignissen
ASR-Regelereignisse können im Windows Defender-Protokoll angezeigt werden.

Um darauf zuzugreifen, öffnen Sie Windows Ereignisanzeige, und navigieren Sie zu **"Anwendungs- und Dienstprotokolle"**  >  **von Microsoft**  >  **Windows**  >  **Windows Defender**  >  **Operational**.

:::image type="content" source="images/eventviewerscrnew.png" alt-text="Ereignisanzeige scr":::

## <a name="microsoft-defender-malware-protection-logs"></a>Microsoft Defender-Protokolle zum Schutz vor Schadsoftware
Sie können Regelereignisse auch über das Microsoft Defender Antivirus dedizierte Befehlszeilentool anzeigen, das aufgerufen `*mpcmdrun.exe*` wird und zum Verwalten und Konfigurieren von Aufgaben verwendet werden kann, und Aufgaben bei Bedarf automatisieren.

Dieses Hilfsprogramm finden Sie unter *%ProgramFiles%\Windows Defender\MpCmdRun.exe*. Sie müssen es über eine Eingabeaufforderung mit erhöhten Rechten ausführen (d. a. als Administrator ausführen).

Um die Supportinformationen zu generieren, geben *SieMpCmdRun.exe -getfiles* ein. Nach einer Weile werden mehrere Protokolle in ein Archiv (MpSupportFiles.cab) gepackt und in *C:\ProgramData\Microsoft\Windows Defender\Support* zur Verfügung gestellt.

:::image type="content" source="images/malware-prot-logsnew.png" alt-text="Protokolle zum Schutz vor Schadsoftware":::

Extrahieren Sie dieses Archiv, und Sie haben viele Dateien zur Problembehandlung zur Verfügung.

Die relevantesten Dateien sind:

- **MPOperationalEvents.txt:** Diese Datei enthält dieselbe Ebene von Informationen, die in der Ereignisanzeige für das Betriebsprotokoll Windows Defender zu finden sind.
- **MPRegistry.txt** – In dieser Datei können Sie alle aktuellen Windows Defender Konfigurationen analysieren, beginnend mit der Erfassung der Supportprotokolle.
- **MPLog.txt** – Dieses Protokoll enthält ausführlichere Informationen zu allen Aktionen/Vorgängen des Windows Defender.
