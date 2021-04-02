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
# <a name="hunt-for-ransomware"></a><span data-ttu-id="c0229-104">Suche nach Ransomware</span><span class="sxs-lookup"><span data-stu-id="c0229-104">Hunt for ransomware</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c0229-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c0229-105">**Applies to:**</span></span>
- <span data-ttu-id="c0229-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c0229-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="c0229-107">Ransomware hat sich schnell von einer einfachen Warensoftware entwickelt, die einzelne Computerbenutzer betrifft, zu einer Unternehmensbedrohung, die branchen- und regierungsweite Einrichtungen stark beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="c0229-107">Ransomware has rapidly evolved from being simple commodity malware affecting individual computer users to an enterprise threat that is severely impacting industries and government institutions.</span></span> <span data-ttu-id="c0229-108">Microsoft [365 Defender](microsoft-365-defender.md) bietet zwar viele Funktionen, mit deren Hilfe Ransomware und damit verbundene Angriffsaktivitäten erkannt und blockiert werden, aber proaktive Überprüfungen auf Anzeichen von Kompromissen können dazu beitragen, dass Ihr Netzwerk geschützt bleibt.</span><span class="sxs-lookup"><span data-stu-id="c0229-108">While [Microsoft 365 Defender](microsoft-365-defender.md) provides many capabilities that detect and block ransomware and associated intrusion activities, performing proactive checks for signs of compromise can help keep your network protected.</span></span>

> [<span data-ttu-id="c0229-109">Informationen zu vom Menschen betriebener Ransomware</span><span class="sxs-lookup"><span data-stu-id="c0229-109">Read about human-operated ransomware</span></span>](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

<span data-ttu-id="c0229-110">Mit [der erweiterten Suche](advanced-hunting-overview.md) in Microsoft 365 Defender können Sie Abfragen erstellen, die nach einzelnen Artefakten im Zusammenhang mit Ransomware-Aktivitäten suchen.</span><span class="sxs-lookup"><span data-stu-id="c0229-110">With [advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender, you can create queries that locate individual artifacts associated with ransomware activity.</span></span> <span data-ttu-id="c0229-111">Sie können auch komplexere Abfragen ausführen, die nach Aktivitätszeichen suchen und diese Zeichen abwägen können, um Geräte zu finden, die sofortige Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="c0229-111">You can also run more sophisticated queries that can look for signs of activity and weigh those signs to find devices that require immediate attention.</span></span>

## <a name="signs-of-ransomware-activity"></a><span data-ttu-id="c0229-112">Anzeichen von Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="c0229-112">Signs of ransomware activity</span></span>
<span data-ttu-id="c0229-113">Microsoft-Sicherheitsforscher haben verschiedene häufige, aber feine Artefakte in vielen Ransomware-Kampagnen beobachtet, die von anspruchsvollen Eindringlingen gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="c0229-113">Microsoft security researchers have observed various common yet subtle artifacts in many ransomware campaigns launched by sophisticated intruders.</span></span> <span data-ttu-id="c0229-114">Diese Zeichen umfassen hauptsächlich die Verwendung von Systemtools, um die Verschlüsselung vorzubereiten, die Erkennung zu verhindern und eindeutige forensische Nachweise zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c0229-114">These signs mostly involve use of system tools to prepare for encryption, prevent detection, and clear forensic evidence.</span></span>

| <span data-ttu-id="c0229-115">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="c0229-115">Ransomware activity</span></span> | <span data-ttu-id="c0229-116">Allgemeine Tools</span><span class="sxs-lookup"><span data-stu-id="c0229-116">Common tools</span></span> | <span data-ttu-id="c0229-117">Intent</span><span class="sxs-lookup"><span data-stu-id="c0229-117">Intent</span></span> |
|--|--|--|
| <span data-ttu-id="c0229-118">Beenden von Prozessen</span><span class="sxs-lookup"><span data-stu-id="c0229-118">Stop processes</span></span> | <span data-ttu-id="c0229-119">_taskkill.exe_, _net stop_</span><span class="sxs-lookup"><span data-stu-id="c0229-119">_taskkill.exe_, _net stop_</span></span> | <span data-ttu-id="c0229-120">Stellen Sie sicher, dass Für die Verschlüsselung bestimmte Dateien nicht von verschiedenen Anwendungen gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="c0229-120">Ensure files targeted for encryption are not locked by various applications.</span></span> |
| <span data-ttu-id="c0229-121">Deaktivieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="c0229-121">Turn off services</span></span> | <span data-ttu-id="c0229-122">_sc.exe_</span><span class="sxs-lookup"><span data-stu-id="c0229-122">_sc.exe_</span></span> | <span data-ttu-id="c0229-123">– Stellen Sie sicher, dass Für die Verschlüsselung bestimmte Dateien nicht von verschiedenen Anwendungen gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="c0229-123">- Ensure files targeted for encryption are not locked by various applications.</span></span><br><span data-ttu-id="c0229-124">– Verhindern, dass Sicherheitssoftware die Verschlüsselung und andere Ransomware-Aktivitäten stört.</span><span class="sxs-lookup"><span data-stu-id="c0229-124">- Prevent security software from disrupting encryption and other ransomware activity.</span></span><br><span data-ttu-id="c0229-125">– Beenden Sie, dass Sicherungssoftware wiederherstellbare Kopien erstellt.</span><span class="sxs-lookup"><span data-stu-id="c0229-125">- Stop backup software from creating recoverable copies.</span></span>  |
| <span data-ttu-id="c0229-126">Löschen von Protokollen und Dateien</span><span class="sxs-lookup"><span data-stu-id="c0229-126">Delete logs and files</span></span> | <span data-ttu-id="c0229-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span><span class="sxs-lookup"><span data-stu-id="c0229-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span></span> | <span data-ttu-id="c0229-128">Entfernen sie forensische Nachweise.</span><span class="sxs-lookup"><span data-stu-id="c0229-128">Remove forensic evidence.</span></span> |
| <span data-ttu-id="c0229-129">Löschen von Schattenkopien</span><span class="sxs-lookup"><span data-stu-id="c0229-129">Delete shadow copies</span></span>  | <span data-ttu-id="c0229-130">_vsadmin.exe_, _wmic.exe_</span><span class="sxs-lookup"><span data-stu-id="c0229-130">_vsadmin.exe_, _wmic.exe_</span></span> | <span data-ttu-id="c0229-131">Entfernen Sie Laufwerkschattenkopien, die zum Wiederherstellen verschlüsselter Dateien verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c0229-131">Remove drive shadow copies that can be used to recover encrypted files.</span></span> |
| <span data-ttu-id="c0229-132">Löschen und Beenden von Sicherungen</span><span class="sxs-lookup"><span data-stu-id="c0229-132">Delete and stop backups</span></span> | <span data-ttu-id="c0229-133">_wbadmin.exe_</span><span class="sxs-lookup"><span data-stu-id="c0229-133">_wbadmin.exe_</span></span> | <span data-ttu-id="c0229-134">Löschen Sie vorhandene Sicherungen, und beenden Sie geplante Sicherungsaufgaben, um die Wiederherstellung nach der Verschlüsselung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="c0229-134">Delete existing backups and stop scheduled backup tasks, preventing recovery after encryption.</span></span> |
| <span data-ttu-id="c0229-135">Ändern der Starteinstellungen</span><span class="sxs-lookup"><span data-stu-id="c0229-135">Modify boot settings</span></span> | <span data-ttu-id="c0229-136">_bcdedit.exe_</span><span class="sxs-lookup"><span data-stu-id="c0229-136">_bcdedit.exe_</span></span> | <span data-ttu-id="c0229-137">Deaktivieren Sie Warnungen und automatische Reparaturen nach Startfehlern, die durch den Verschlüsselungsprozess verursacht werden können.</span><span class="sxs-lookup"><span data-stu-id="c0229-137">Turn off warnings and automatic repairs after boot failures that can be caused by the encryption process.</span></span> |
| <span data-ttu-id="c0229-138">Deaktivieren von Wiederherstellungstools</span><span class="sxs-lookup"><span data-stu-id="c0229-138">Turn off recovery tools</span></span> | <span data-ttu-id="c0229-139">_schtasks.exe_, _regedit.exe_,</span><span class="sxs-lookup"><span data-stu-id="c0229-139">_schtasks.exe_, _regedit.exe_,</span></span> | <span data-ttu-id="c0229-140">Deaktivieren Sie Systemwiederherstellung und andere Systemwiederherstellungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="c0229-140">Turn off System Restore and other system recovery options.</span></span> |

## <a name="check-for-individual-signs-of-ransomware-activity"></a><span data-ttu-id="c0229-141">Überprüfen auf einzelne Anzeichen von Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="c0229-141">Check for individual signs of ransomware activity</span></span>
<span data-ttu-id="c0229-142">Viele Aktivitäten, die ein Ransomware-Verhalten darstellen, einschließlich der im vorherigen Abschnitt beschriebenen Aktivitäten, können gutartig sein.</span><span class="sxs-lookup"><span data-stu-id="c0229-142">Many activities that constitute ransomware behavior, including the activities described in the preceding section, can be benign.</span></span> <span data-ttu-id="c0229-143">Wenn Sie die folgenden Abfragen verwenden, um Ransomware zu finden, führen Sie mehrere Abfragen aus, um zu überprüfen, ob auf denselben Geräten verschiedene Anzeichen für eine mögliche Ransomware-Aktivität angezeigt werden.</span><span class="sxs-lookup"><span data-stu-id="c0229-143">When using the following queries to locate ransomware, run more than one query to check whether the same devices are exhibiting various signs of possible ransomware activity.</span></span>

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a><span data-ttu-id="c0229-144">Beenden mehrerer Prozesse _mithilfetaskkill.exe_</span><span class="sxs-lookup"><span data-stu-id="c0229-144">Stopping multiple processes using _taskkill.exe_</span></span>
<span data-ttu-id="c0229-145">Diese Abfrage überprüft, ob versucht wird, mindestens 10 separate Prozesse mithilfe des Dienstprogramms _taskkill.exe_ beenden.</span><span class="sxs-lookup"><span data-stu-id="c0229-145">This query checks for attempts to stop at least 10 separate processes using the _taskkill.exe_ utility.</span></span> [<span data-ttu-id="c0229-146">Ausführen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0229-146">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a><span data-ttu-id="c0229-147">Beenden von Prozessen mithilfe _von Net Stop_</span><span class="sxs-lookup"><span data-stu-id="c0229-147">Stopping processes using _net stop_</span></span>
<span data-ttu-id="c0229-148">Diese Abfrage überprüft, ob versucht wird, mindestens 10 separate Prozesse mithilfe des _Befehls net stop zu_ beenden.</span><span class="sxs-lookup"><span data-stu-id="c0229-148">This query checks for attempts to stop at least 10 separate processes using the _net stop_ command.</span></span> [<span data-ttu-id="c0229-149">Ausführen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0229-149">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a><span data-ttu-id="c0229-150">Löschen von Daten auf mehreren Laufwerken _mithilfecipher.exe_</span><span class="sxs-lookup"><span data-stu-id="c0229-150">Deletion of data on multiple drives using _cipher.exe_</span></span>
<span data-ttu-id="c0229-151">Diese Abfrage überprüft, ob versucht wird, Daten auf mehreren Laufwerken mithilfe von _cipher.exe._</span><span class="sxs-lookup"><span data-stu-id="c0229-151">This query checks for attempts to delete data on multiple drives using _cipher.exe_.</span></span> <span data-ttu-id="c0229-152">Diese Aktivität wird in der Regel von Ransomware durchgeführt, um die Wiederherstellung von Daten nach der Verschlüsselung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="c0229-152">This activity is typically done by ransomware to prevent recovery of data after encryption.</span></span> [<span data-ttu-id="c0229-153">Ausführen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0229-153">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

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

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a><span data-ttu-id="c0229-154">Löschen von forensischen Nachweisen aus Ereignisprotokollen mithilfe _von wevtutil_</span><span class="sxs-lookup"><span data-stu-id="c0229-154">Clearing of forensic evidence from event logs using _wevtutil_</span></span>
<span data-ttu-id="c0229-155">Diese Abfrage überprüft, ob versucht wird, mindestens 10 Protokolleinträge aus Ereignisprotokollen mithilfe von _wevtutil zu löschen._</span><span class="sxs-lookup"><span data-stu-id="c0229-155">This query checks for attempts to clear at least 10 log entries from event logs using _wevtutil_.</span></span> [<span data-ttu-id="c0229-156">Ausführen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0229-156">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a><span data-ttu-id="c0229-157">Deaktivieren von Diensten _mithilfesc.exe_</span><span class="sxs-lookup"><span data-stu-id="c0229-157">Turning off services using _sc.exe_</span></span>
<span data-ttu-id="c0229-158">Diese Abfrage überprüft, ob versucht wird, mindestens 10 vorhandene Dienste mithilfe von _sc.exe._</span><span class="sxs-lookup"><span data-stu-id="c0229-158">This query checks for attempts to turn off at least 10 existing services using _sc.exe_.</span></span> [<span data-ttu-id="c0229-159">Ausführen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0229-159">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a><span data-ttu-id="c0229-160">Deaktivieren der Systemwiederherstellung</span><span class="sxs-lookup"><span data-stu-id="c0229-160">Turning off System Restore</span></span>
<span data-ttu-id="c0229-161">Diese Abfrage identifiziert Versuche, die Systemwiederherstellung zu beenden und zu verhindern, dass das System Wiederherstellungspunkte erstellt, die zum Wiederherstellen von durch Ransomware verschlüsselten Daten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="c0229-161">This query identifies attempts to stop System Restore and prevent the system from creating restore points, which can be used to recover data encrypted by ransomware.</span></span> [<span data-ttu-id="c0229-162">Ausführen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0229-162">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

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

### <a name="backup-deletion"></a><span data-ttu-id="c0229-163">Löschen der Sicherung</span><span class="sxs-lookup"><span data-stu-id="c0229-163">Backup deletion</span></span>
<span data-ttu-id="c0229-164">Diese Abfrage identifiziert die Verwendung von _wmic.exe,_ um Momentaufnahmen von Schattenkopien vor der Verschlüsselung zu löschen.</span><span class="sxs-lookup"><span data-stu-id="c0229-164">This query identifies use of _wmic.exe_ to delete shadow copy snapshots prior to encryption.</span></span> [<span data-ttu-id="c0229-165">Ausführen einer Abfrage</span><span class="sxs-lookup"><span data-stu-id="c0229-165">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a><span data-ttu-id="c0229-166">Überprüfen auf mehrere Anzeichen von Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="c0229-166">Check for multiple signs of ransomware activity</span></span>
<span data-ttu-id="c0229-167">Anstatt mehrere Abfragen separat durchzuführen, können Sie auch eine umfassende Abfrage verwenden, die auf mehrere Anzeichen von Ransomware-Aktivität überprüft, um betroffene Geräte zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="c0229-167">Instead of running several queries separately, you can also use a comprehensive query that checks for multiple signs of ransomware activity to identify affected devices.</span></span> <span data-ttu-id="c0229-168">Die folgende konsolidierte Abfrage:</span><span class="sxs-lookup"><span data-stu-id="c0229-168">The following consolidated  query:</span></span>
- <span data-ttu-id="c0229-169">Sucht nach relativ konkreten und subtilen Anzeichen für Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="c0229-169">Looks for both relatively concrete and subtle signs of ransomware activity</span></span>
- <span data-ttu-id="c0229-170">Wiegt das Vorhandensein dieser Zeichen</span><span class="sxs-lookup"><span data-stu-id="c0229-170">Weighs the presence of these signs</span></span>
- <span data-ttu-id="c0229-171">Identifiziert Geräte mit einer höheren Wahrscheinlichkeit, Ziel von Ransomware zu sein</span><span class="sxs-lookup"><span data-stu-id="c0229-171">Identifies devices with a higher chance of being targets of ransomware</span></span> 

<span data-ttu-id="c0229-172">Bei der Ausführung gibt diese konsolidierte Abfrage eine Liste der Geräte zurück, auf denen mehrere Angriffszeichen vorhanden sind.</span><span class="sxs-lookup"><span data-stu-id="c0229-172">When run, this consolidated query returns a list of devices that have exhibited multiple signs of attack.</span></span> <span data-ttu-id="c0229-173">Die Anzahl der einzelnen Arten von Ransomware-Aktivitäten wird ebenfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c0229-173">The count of each type of ransomware activity is also shown.</span></span> <span data-ttu-id="c0229-174">Um diese konsolidierte Abfrage ausführen zu können, kopieren Sie sie direkt in den editor für erweiterte [Suchabfragen.](https://security.microsoft.com/advanced-hunting)</span><span class="sxs-lookup"><span data-stu-id="c0229-174">To run this consolidated query, copy it directly to the [advanced hunting query editor](https://security.microsoft.com/advanced-hunting).</span></span> 

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
### <a name="understand-and-tweak-the-query-results"></a><span data-ttu-id="c0229-175">Verstehen und Optimieren der Abfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="c0229-175">Understand and tweak the query results</span></span>
<span data-ttu-id="c0229-176">Die konsolidierte Abfrage gibt die folgenden Ergebnisse zurück:</span><span class="sxs-lookup"><span data-stu-id="c0229-176">The consolidated query returns the following results:</span></span>

- <span data-ttu-id="c0229-177">**DeviceId –** identifiziert das betroffene Gerät</span><span class="sxs-lookup"><span data-stu-id="c0229-177">**DeviceId**—identifies the affected device</span></span> 
- <span data-ttu-id="c0229-178">**TimeStamp**– das erste Mal, wenn ein Anzeichen von Ransomware-Aktivität auf dem Gerät beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="c0229-178">**TimeStamp**—first time any sign of ransomware activity was observed on the device</span></span>
- <span data-ttu-id="c0229-179">**Spezifische Aktivitätszeichen**– die Anzahl für jedes In mehreren Spalten angezeigte Zeichen, z. B. _BcdEdit_ oder _FsUtil_</span><span class="sxs-lookup"><span data-stu-id="c0229-179">**Specific signs of activity**—the count for each sign shown in multiple columns, such as _BcdEdit_ or _FsUtil_</span></span>
- <span data-ttu-id="c0229-180">**TotalEvidenceCount**– Anzahl der beobachteten Zeichen</span><span class="sxs-lookup"><span data-stu-id="c0229-180">**TotalEvidenceCount**—number of observed signs</span></span>
- <span data-ttu-id="c0229-181">**UniqueEvidenceCount**– Anzahl der Beobachteten Zeichentypen</span><span class="sxs-lookup"><span data-stu-id="c0229-181">**UniqueEvidenceCount**—number of types of observed signs</span></span>

![Abbildung der Abfrageergebnisse für Ransomware-Aktivität](../../media/advanced-hunting-ransomware-query.png)

<span data-ttu-id="c0229-183">*Abfrageergebnisse mit betroffenen Geräten und Anzahl verschiedener Zeichen von Ransomware-Aktivität*</span><span class="sxs-lookup"><span data-stu-id="c0229-183">*Query results showing affected devices and counts of various signs of ransomware activity*</span></span>

<span data-ttu-id="c0229-184">Standardmäßig werden im Abfrageergebnis nur Geräte mit mehr als zwei Arten von Ransomware-Aktivität aufgeführt.</span><span class="sxs-lookup"><span data-stu-id="c0229-184">By default, the query result lists only devices that have more than two types of ransomware activity.</span></span> <span data-ttu-id="c0229-185">Um alle Geräte mit anzeichen einer Ransomware-Aktivität zu sehen, ändern Sie den folgenden Operator, und legen Sie die Zahl `where` auf Null (0) festgelegt.</span><span class="sxs-lookup"><span data-stu-id="c0229-185">To see all devices with any sign of ransomware activity, modify the following `where` operator and set the number to zero (0).</span></span> <span data-ttu-id="c0229-186">Um weniger Geräte zu sehen, legen Sie eine höhere Anzahl ein.</span><span class="sxs-lookup"><span data-stu-id="c0229-186">To see fewer devices, set a higher number.</span></span> 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a><span data-ttu-id="c0229-187">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c0229-187">Related topics</span></span>
- [<span data-ttu-id="c0229-188">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="c0229-188">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c0229-189">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="c0229-189">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c0229-190">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="c0229-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="c0229-191">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="c0229-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c0229-192">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="c0229-192">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c0229-193">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="c0229-193">Apply query best practices</span></span>](advanced-hunting-best-practices.md)