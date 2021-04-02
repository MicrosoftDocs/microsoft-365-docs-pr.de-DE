---
title: Suchen nach Ransomware mit erweiterter Suche
description: Verwenden Sie die erweiterte Suche, um Geräte zu finden, die potenziell von Ransomware betroffen sind.
keywords: Erweiterte Suche, Ransomware, Bedrohungssuche, Cyberbedrohungensuche, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft Threat Protection, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 97f2174f74e7866f75b901cd1609341548a1a7c5
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498217"
---
# <a name="hunt-for-ransomware"></a>Suche nach Ransomware

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**Gilt für:**
- Microsoft 365 Defender

Ransomware hat sich schnell von einer einfachen Warensoftware entwickelt, die einzelne Computerbenutzer betrifft, zu einer Unternehmensbedrohung, die branchen- und regierungsweite Einrichtungen stark beeinträchtigt. Microsoft [365 Defender](microsoft-365-defender.md) bietet zwar viele Funktionen, mit deren Hilfe Ransomware und damit verbundene Angriffsaktivitäten erkannt und blockiert werden, aber proaktive Überprüfungen auf Anzeichen von Kompromissen können dazu beitragen, dass Ihr Netzwerk geschützt bleibt.

> [Informationen zu vom Menschen betriebener Ransomware](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

Mit [der erweiterten Suche](advanced-hunting-overview.md) in Microsoft 365 Defender können Sie Abfragen erstellen, die nach einzelnen Artefakten im Zusammenhang mit Ransomware-Aktivitäten suchen. Sie können auch komplexere Abfragen ausführen, die nach Aktivitätszeichen suchen und diese Zeichen abwägen können, um Geräte zu finden, die sofortige Aufmerksamkeit erfordern.

## <a name="signs-of-ransomware-activity"></a>Anzeichen von Ransomware-Aktivität
Microsoft-Sicherheitsforscher haben verschiedene häufige, aber feine Artefakte in vielen Ransomware-Kampagnen beobachtet, die von anspruchsvollen Eindringlingen gestartet wurden. Diese Zeichen umfassen hauptsächlich die Verwendung von Systemtools, um die Verschlüsselung vorzubereiten, die Erkennung zu verhindern und eindeutige forensische Nachweise zu erstellen.

| Ransomware-Aktivität | Allgemeine Tools | Intent |
|--|--|--|
| Beenden von Prozessen | _taskkill.exe_, _net stop_ | Stellen Sie sicher, dass Für die Verschlüsselung bestimmte Dateien nicht von verschiedenen Anwendungen gesperrt werden. |
| Deaktivieren von Diensten | _sc.exe_ | – Stellen Sie sicher, dass Für die Verschlüsselung bestimmte Dateien nicht von verschiedenen Anwendungen gesperrt werden.<br>– Verhindern, dass Sicherheitssoftware die Verschlüsselung und andere Ransomware-Aktivitäten stört.<br>– Beenden Sie, dass Sicherungssoftware wiederherstellbare Kopien erstellt.  |
| Löschen von Protokollen und Dateien | _cipher.exe_, _wevtutil_, _fsutil.exe_ | Entfernen sie forensische Nachweise. |
| Löschen von Schattenkopien  | _vsadmin.exe_, _wmic.exe_ | Entfernen Sie Laufwerkschattenkopien, die zum Wiederherstellen verschlüsselter Dateien verwendet werden können. |
| Löschen und Beenden von Sicherungen | _wbadmin.exe_ | Löschen Sie vorhandene Sicherungen, und beenden Sie geplante Sicherungsaufgaben, um die Wiederherstellung nach der Verschlüsselung zu verhindern. |
| Ändern der Starteinstellungen | _bcdedit.exe_ | Deaktivieren Sie Warnungen und automatische Reparaturen nach Startfehlern, die durch den Verschlüsselungsprozess verursacht werden können. |
| Deaktivieren von Wiederherstellungstools | _schtasks.exe_, _regedit.exe_, | Deaktivieren Sie Systemwiederherstellung und andere Systemwiederherstellungsoptionen. |

## <a name="check-for-individual-signs-of-ransomware-activity"></a>Überprüfen auf einzelne Anzeichen von Ransomware-Aktivität
Viele Aktivitäten, die ein Ransomware-Verhalten darstellen, einschließlich der im vorherigen Abschnitt beschriebenen Aktivitäten, können gutartig sein. Wenn Sie die folgenden Abfragen verwenden, um Ransomware zu finden, führen Sie mehrere Abfragen aus, um zu überprüfen, ob auf denselben Geräten verschiedene Anzeichen für eine mögliche Ransomware-Aktivität angezeigt werden.

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a>Beenden mehrerer Prozesse _mithilfetaskkill.exe_
Diese Abfrage überprüft, ob versucht wird, mindestens 10 separate Prozesse mithilfe des Dienstprogramms _taskkill.exe_ beenden. [Ausführen einer Abfrage](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a>Beenden von Prozessen mithilfe _von Net Stop_
Diese Abfrage überprüft, ob versucht wird, mindestens 10 separate Prozesse mithilfe des _Befehls net stop zu_ beenden. [Ausführen einer Abfrage](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a>Löschen von Daten auf mehreren Laufwerken _mithilfecipher.exe_
Diese Abfrage überprüft, ob versucht wird, Daten auf mehreren Laufwerken mithilfe von _cipher.exe._ Diese Aktivität wird in der Regel von Ransomware durchgeführt, um die Wiederherstellung von Daten nach der Verschlüsselung zu verhindern. [Ausführen einer Abfrage](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for cipher.exe deleting data from multiple drives
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine),
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1
```

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a>Löschen von forensischen Nachweisen aus Ereignisprotokollen mithilfe _von wevtutil_
Diese Abfrage überprüft, ob versucht wird, mindestens 10 Protokolleinträge aus Ereignisprotokollen mithilfe von _wevtutil zu löschen._ [Ausführen einer Abfrage](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a>Deaktivieren von Diensten _mithilfesc.exe_
Diese Abfrage überprüft, ob versucht wird, mindestens 10 vorhandene Dienste mithilfe von _sc.exe._ [Ausführen einer Abfrage](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a>Deaktivieren der Systemwiederherstellung
Diese Abfrage identifiziert Versuche, die Systemwiederherstellung zu beenden und zu verhindern, dass das System Wiederherstellungspunkte erstellt, die zum Wiederherstellen von durch Ransomware verschlüsselten Daten verwendet werden können. [Ausführen einer Abfrage](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
//Pivoting for rundll32  
| where InitiatingProcessFileName =~ 'rundll32.exe'   
//Looking for empty command line   
and InitiatingProcessCommandLine !contains " " and InitiatingProcessCommandLine != ""  
//Looking for schtasks.exe as the created process  
and FileName in~ ('schtasks.exe')  
//Disabling system restore   
and ProcessCommandLine has 'Change' and ProcessCommandLine has 'SystemRestore' 
and ProcessCommandLine has 'disable'
```

### <a name="backup-deletion"></a>Löschen der Sicherung
Diese Abfrage identifiziert die Verwendung von _wmic.exe,_ um Momentaufnahmen von Schattenkopien vor der Verschlüsselung zu löschen. [Ausführen einer Abfrage](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a>Überprüfen auf mehrere Anzeichen von Ransomware-Aktivität
Anstatt mehrere Abfragen separat durchzuführen, können Sie auch eine umfassende Abfrage verwenden, die auf mehrere Anzeichen von Ransomware-Aktivität überprüft, um betroffene Geräte zu identifizieren. Die folgende konsolidierte Abfrage:
- Sucht nach relativ konkreten und subtilen Anzeichen für Ransomware-Aktivität
- Wiegt das Vorhandensein dieser Zeichen
- Identifiziert Geräte mit einer höheren Wahrscheinlichkeit, Ziel von Ransomware zu sein 

Bei der Ausführung gibt diese konsolidierte Abfrage eine Liste der Geräte zurück, auf denen mehrere Angriffszeichen vorhanden sind. Die Anzahl der einzelnen Arten von Ransomware-Aktivitäten wird ebenfalls angezeigt. Um diese konsolidierte Abfrage ausführen zu können, kopieren Sie sie direkt in den editor für erweiterte [Suchabfragen.](https://security.microsoft.com/advanced-hunting) 

```kusto
// Find attempts to stop processes using taskkill.exe
let taskKill = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10;
// Find attempts to stop processes using net stop
let netStop = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10;
// Look for cipher.exe deleting data from multiple drives
let cipher = DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "cipher.exe" 
// cipher.exe /w flag used for deleting data 
| where ProcessCommandLine has "/w" 
| summarize CipherCount = dcount(ProcessCommandLine), 
CipherList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 1m) 
// cipher.exe accessing multiple drives in a short timeframe 
| where CipherCount > 1;
// Look for use of wevtutil to clear multiple logs
let wevtutilClear = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10;
// Look for sc.exe disabling services
let scDisable = DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10;
// Main query for counting and aggregating evidence
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "vssadmin.exe" and ProcessCommandLine has_any("list shadows", "delete shadows")
or FileName =~ "fsutil.exe" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal"
or ProcessCommandLine has("bcdedit") and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures")
or ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup")
or (ProcessCommandLine has "wevtutil" and ProcessCommandLine has "cl") 
or (ProcessCommandLine has "wmic" and ProcessCommandLine has "shadowcopy delete")
or (ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled")
| extend Bcdedit = iff(ProcessCommandLine has "bcdedit" and ProcessCommandLine has_any("recoveryenabled no", "bootstatuspolicy ignoreallfailures"), 1, 0)
| extend ShadowCopyDelete = iff (ProcessCommandLine has "shadowcopy delete", 1, 0)
| extend VssAdminShadows = iff(ProcessCommandLine has "vssadmin" and ProcessCommandLine has_any("list shadows", "delete shadows"), 1, 0)
| extend Wbadmin = iff(ProcessCommandLine has "wbadmin" and ProcessCommandLine has "delete" and ProcessCommandLine has_any("backup", "catalog", "systemstatebackup"), 1,0)
| extend Fsutil = iff(ProcessCommandLine has "fsutil" and ProcessCommandLine has "usn" and ProcessCommandLine has "deletejournal", 1, 0)
| summarize FirstActivity = min(Timestamp), ReportId = any(ReportId), Commands = make_set(ProcessCommandLine) by DeviceId, Fsutil, Wbadmin, ShadowCopyDelete, Bcdedit, VssAdminShadows, bin(Timestamp, 6h)
// Joining extra evidence
| join kind=leftouter (wevtutilClear) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (cipher) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (netStop) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (taskKill) on $left.DeviceId == $right.DeviceId
| join kind=leftouter (scDisable) on $left.DeviceId == $right.DeviceId
| extend WevtutilUse = iff(LogClearCount > 10, 1, 0)
| extend CipherUse = iff(CipherCount > 1, 1, 0)
| extend NetStopUse = iff(netStopCount > 10, 1, 0)
| extend TaskkillUse = iff(taskKillCount > 10, 1, 0)
| extend ScDisableUse = iff(ScDisableCount > 10, 1, 0)
// Adding up all evidence
| mv-expand CommandList = NetStopList, TaskKillList, ClearedLogList, CipherList, Commands, ScDisableList
// Format results
| summarize BcdEdit = iff(make_set(Bcdedit) contains "1" , 1, 0), NetStop10PlusCommands = iff(make_set(NetStopUse) contains "1", 1, 0), Wevtutil10PlusLogsCleared = iff(make_set(WevtutilUse) contains "1", 1, 0),
CipherMultipleDrives = iff(make_set(CipherUse) contains "1", 1, 0), Fsutil = iff(make_set(Fsutil) contains "1", 1, 0), ShadowCopyDelete = iff(make_set(ShadowCopyDelete) contains "1", 1, 0),
Wbadmin = iff(make_set(Wbadmin) contains "1", 1, 0), TaskKill10PlusCommand = iff(make_set(TaskkillUse) contains "1", 1, 0), VssAdminShadow = iff(make_set(VssAdminShadows) contains "1", 1, 0), 
ScDisable = iff(make_set(ScDisableUse) contains "1", 1, 0), TotalEvidenceCount = count(CommandList), EvidenceList = make_set(Commands), StartofBehavior = min(FirstActivity) by DeviceId, bin(Timestamp, 1d)
| extend UniqueEvidenceCount = BcdEdit + NetStop10PlusCommands + Wevtutil10PlusLogsCleared + CipherMultipleDrives + Wbadmin + Fsutil + TaskKill10PlusCommand + VssAdminShadow + ScDisable + ShadowCopyDelete
| where UniqueEvidenceCount > 2
```
### <a name="understand-and-tweak-the-query-results"></a>Verstehen und Optimieren der Abfrageergebnisse
Die konsolidierte Abfrage gibt die folgenden Ergebnisse zurück:

- **DeviceId –** identifiziert das betroffene Gerät 
- **TimeStamp**– das erste Mal, wenn ein Anzeichen von Ransomware-Aktivität auf dem Gerät beobachtet wurde
- **Spezifische Aktivitätszeichen**– die Anzahl für jedes In mehreren Spalten angezeigte Zeichen, z. B. _BcdEdit_ oder _FsUtil_
- **TotalEvidenceCount**– Anzahl der beobachteten Zeichen
- **UniqueEvidenceCount**– Anzahl der Beobachteten Zeichentypen

![Abbildung der Abfrageergebnisse für Ransomware-Aktivität](../../media/advanced-hunting-ransomware-query.png)

*Abfrageergebnisse mit betroffenen Geräten und Anzahl verschiedener Zeichen von Ransomware-Aktivität*

Standardmäßig werden im Abfrageergebnis nur Geräte mit mehr als zwei Arten von Ransomware-Aktivität aufgeführt. Um alle Geräte mit anzeichen einer Ransomware-Aktivität zu sehen, ändern Sie den folgenden Operator, und legen Sie die Zahl `where` auf Null (0) festgelegt. Um weniger Geräte zu sehen, legen Sie eine höhere Anzahl ein. 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a>Verwandte Themen
- [Übersicht über die erweiterte Suche](advanced-hunting-overview.md)
- [Lernen der Abfragesprache](advanced-hunting-query-language.md)
- [Arbeiten mit Abfrageergebnissen](advanced-hunting-query-results.md)
- [Verwenden freigegebener Abfragen](advanced-hunting-shared-queries.md)
- [Grundlegendes zum Schema](advanced-hunting-schema-tables.md)
- [Anwenden bewährter Methoden für Abfragen](advanced-hunting-best-practices.md)