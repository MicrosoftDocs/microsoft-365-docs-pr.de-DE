---
title: Ransomware mit erweiterter Suche suchen
description: Verwenden Sie die erweiterte Suche, um von Ransomware potenziell betroffene Geräte zu finden.
keywords: Erweiterte Jagd, Ransomware, Bedrohungs Suche, Cyber Threat Hunting, Suche, Abfrage, Telemetrie, Microsoft 365, Microsoft Threat Protection, Microsoft 365 Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.openlocfilehash: aaee2af4b3df849b57b8e1c18ab330603042fe96
ms.sourcegitcommit: 8ad481ed61cb6dabf8afb0fb04296666fa166450
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 11/26/2020
ms.locfileid: "49422904"
---
# <a name="hunt-for-ransomware"></a><span data-ttu-id="da0aa-104">Hunt für Ransomware</span><span class="sxs-lookup"><span data-stu-id="da0aa-104">Hunt for ransomware</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="da0aa-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="da0aa-105">**Applies to:**</span></span>
- <span data-ttu-id="da0aa-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="da0aa-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="da0aa-107">Ransomware hat sich schnell von der einfachen Rohstoff-Schadsoftware für einzelne Computer Benutzer zu einer Unternehmens Bedrohung entwickelt, die Branchen und Regierungsinstitutionen stark beeinträchtigt.</span><span class="sxs-lookup"><span data-stu-id="da0aa-107">Ransomware has rapidly evolved from being simple commodity malware affecting individual computer users to an enterprise threat that is severely impacting industries and government institutions.</span></span> <span data-ttu-id="da0aa-108">Während [Microsoft 365 Defender](microsoft-threat-protection.md) viele Funktionen bereitstellt, die Ransomware und zugehörige Intrusions Aktivitäten erkennen und blockieren, kann das durchführen proaktiver Überprüfungen auf Zeichen von Kompromissen dazu beitragen, dass Ihr Netzwerk geschützt bleibt.</span><span class="sxs-lookup"><span data-stu-id="da0aa-108">While [Microsoft 365 Defender](microsoft-threat-protection.md) provides many capabilities that detect and block ransomware and associated intrusion activities, performing proactive checks for signs of compromise can help keep your network protected.</span></span>

> [<span data-ttu-id="da0aa-109">Lesen Sie mehr über die von Menschen betriebene Ransomware</span><span class="sxs-lookup"><span data-stu-id="da0aa-109">Read about human-operated ransomware</span></span>](https://www.microsoft.com/security/blog/2020/03/05/human-operated-ransomware-attacks-a-preventable-disaster/)

<span data-ttu-id="da0aa-110">Mit [Advanced Hunting](advanced-hunting-overview.md) in Microsoft 365 Defender können Sie Abfragen erstellen, die einzelne Artefakte im Zusammenhang mit der Ransomware-Aktivität finden.</span><span class="sxs-lookup"><span data-stu-id="da0aa-110">With [advanced hunting](advanced-hunting-overview.md) in Microsoft 365 Defender, you can create queries that locate individual artifacts associated with ransomware activity.</span></span> <span data-ttu-id="da0aa-111">Sie können auch komplexere Abfragen ausführen, die nach Aktivitäts Zeichen suchen und diese Zeichen abwägen können, um Geräte zu finden, die sofortige Aufmerksamkeit erfordern.</span><span class="sxs-lookup"><span data-stu-id="da0aa-111">You can also run more sophisticated queries that can look for signs of activity and weigh those signs to find devices that require immediate attention.</span></span>

## <a name="signs-of-ransomware-activity"></a><span data-ttu-id="da0aa-112">Zeichen der Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="da0aa-112">Signs of ransomware activity</span></span>
<span data-ttu-id="da0aa-113">Microsoft-Sicherheitsforscher haben verschiedene häufige, aber subtile Artefakte in vielen Ransomware-Kampagnen beobachtet, die von anspruchsvollen Eindringlingen gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="da0aa-113">Microsoft security researchers have observed various common yet subtle artifacts in many ransomware campaigns launched by sophisticated intruders.</span></span> <span data-ttu-id="da0aa-114">Diese Zeichen beinhalten hauptsächlich die Verwendung von System Tools, um die Verschlüsselung vorzubereiten, die Erkennung zu verhindern und forensische Beweise zu löschen.</span><span class="sxs-lookup"><span data-stu-id="da0aa-114">These signs mostly involve use of system tools to prepare for encryption, prevent detection, and clear forensic evidence.</span></span>

| <span data-ttu-id="da0aa-115">Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="da0aa-115">Ransomware activity</span></span> | <span data-ttu-id="da0aa-116">Allgemeine Tools</span><span class="sxs-lookup"><span data-stu-id="da0aa-116">Common tools</span></span> | <span data-ttu-id="da0aa-117">Intent</span><span class="sxs-lookup"><span data-stu-id="da0aa-117">Intent</span></span> |
|--|--|--|
| <span data-ttu-id="da0aa-118">Beenden von Prozessen</span><span class="sxs-lookup"><span data-stu-id="da0aa-118">Stop processes</span></span> | <span data-ttu-id="da0aa-119">_taskkill.exe_, _net stop_</span><span class="sxs-lookup"><span data-stu-id="da0aa-119">_taskkill.exe_, _net stop_</span></span> | <span data-ttu-id="da0aa-120">Stellen Sie sicher, dass Dateien, die für die Verschlüsselung vorgesehen sind, nicht von verschiedenen Anwendungen gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="da0aa-120">Ensure files targeted for encryption are not locked by various applications.</span></span> |
| <span data-ttu-id="da0aa-121">Deaktivieren von Diensten</span><span class="sxs-lookup"><span data-stu-id="da0aa-121">Turn off services</span></span> | <span data-ttu-id="da0aa-122">_sc.exe_</span><span class="sxs-lookup"><span data-stu-id="da0aa-122">_sc.exe_</span></span> | <span data-ttu-id="da0aa-123">-Sicherstellen, dass für die Verschlüsselung vorgesehene Dateien nicht von verschiedenen Anwendungen gesperrt werden.</span><span class="sxs-lookup"><span data-stu-id="da0aa-123">- Ensure files targeted for encryption are not locked by various applications.</span></span><br><span data-ttu-id="da0aa-124">-Verhindert, dass Sicherheitssoftware die Verschlüsselung und andere Ransomware-Aktivitäten stört.</span><span class="sxs-lookup"><span data-stu-id="da0aa-124">- Prevent security software from disrupting encryption and other ransomware activity.</span></span><br><span data-ttu-id="da0aa-125">-Beenden der Erstellung von wiederherstellbaren Kopien durch Sicherungssoftware.</span><span class="sxs-lookup"><span data-stu-id="da0aa-125">- Stop backup software from creating recoverable copies.</span></span>  |
| <span data-ttu-id="da0aa-126">Löschen von Protokollen und Dateien</span><span class="sxs-lookup"><span data-stu-id="da0aa-126">Delete logs and files</span></span> | <span data-ttu-id="da0aa-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span><span class="sxs-lookup"><span data-stu-id="da0aa-127">_cipher.exe_, _wevtutil_, _fsutil.exe_</span></span> | <span data-ttu-id="da0aa-128">Entfernen Sie forensische Beweise.</span><span class="sxs-lookup"><span data-stu-id="da0aa-128">Remove forensic evidence.</span></span> |
| <span data-ttu-id="da0aa-129">Löschen von Schattenkopien</span><span class="sxs-lookup"><span data-stu-id="da0aa-129">Delete shadow copies</span></span>  | <span data-ttu-id="da0aa-130">_vsadmin.exe_ _wmic.exe_</span><span class="sxs-lookup"><span data-stu-id="da0aa-130">_vsadmin.exe_, _wmic.exe_</span></span> | <span data-ttu-id="da0aa-131">Entfernen von Laufwerks Schattenkopien, die zum Wiederherstellen verschlüsselter Dateien verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="da0aa-131">Remove drive shadow copies that can be used to recover encrypted files.</span></span> |
| <span data-ttu-id="da0aa-132">Löschen und Beenden von Sicherungen</span><span class="sxs-lookup"><span data-stu-id="da0aa-132">Delete and stop backups</span></span> | <span data-ttu-id="da0aa-133">_wbadmin.exe_</span><span class="sxs-lookup"><span data-stu-id="da0aa-133">_wbadmin.exe_</span></span> | <span data-ttu-id="da0aa-134">Löschen Sie vorhandene Sicherungen, und beenden Sie geplante Sicherungsaufgaben, wodurch die Wiederherstellung nach der Verschlüsselung verhindert wird.</span><span class="sxs-lookup"><span data-stu-id="da0aa-134">Delete existing backups and stop scheduled backup tasks, preventing recovery after encryption.</span></span> |
| <span data-ttu-id="da0aa-135">Ändern von Start Einstellungen</span><span class="sxs-lookup"><span data-stu-id="da0aa-135">Modify boot settings</span></span> | <span data-ttu-id="da0aa-136">_bcdedit.exe_</span><span class="sxs-lookup"><span data-stu-id="da0aa-136">_bcdedit.exe_</span></span> | <span data-ttu-id="da0aa-137">Deaktivieren Sie Warnungen und automatische Reparaturen nach Startfehlern, die durch den Verschlüsselungsprozess verursacht werden können.</span><span class="sxs-lookup"><span data-stu-id="da0aa-137">Turn off warnings and automatic repairs after boot failures that can be caused by the encryption process.</span></span> |
| <span data-ttu-id="da0aa-138">Deaktivieren von Wiederherstellungstools</span><span class="sxs-lookup"><span data-stu-id="da0aa-138">Turn off recovery tools</span></span> | <span data-ttu-id="da0aa-139">_schtasks.exe_, _regedit.exe_</span><span class="sxs-lookup"><span data-stu-id="da0aa-139">_schtasks.exe_, _regedit.exe_,</span></span> | <span data-ttu-id="da0aa-140">Deaktivieren Sie die Systemwiederherstellung und andere Systemwiederherstellungsoptionen.</span><span class="sxs-lookup"><span data-stu-id="da0aa-140">Turn off System Restore and other system recovery options.</span></span> |

## <a name="check-for-individual-signs-of-ransomware-activity"></a><span data-ttu-id="da0aa-141">Überprüfen auf einzelne Zeichen der Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="da0aa-141">Check for individual signs of ransomware activity</span></span>
<span data-ttu-id="da0aa-142">Viele Aktivitäten, die das Ransomware-Verhalten darstellen, einschließlich der im vorherigen Abschnitt beschriebenen Aktivitäten, können gutartig sein.</span><span class="sxs-lookup"><span data-stu-id="da0aa-142">Many activities that constitute ransomware behavior, including the activities described in the preceding section, can be benign.</span></span> <span data-ttu-id="da0aa-143">Wenn Sie die folgenden Abfragen zum Auffinden von Ransomware verwenden, führen Sie mehrere Abfragen aus, um zu überprüfen, ob dieselben Geräte verschiedene Zeichen möglicher Ransomware-Aktivitäten aufweisen.</span><span class="sxs-lookup"><span data-stu-id="da0aa-143">When using the following queries to locate ransomware, run more than one query to check whether the same devices are exhibiting various signs of possible ransomware activity.</span></span>

### <a name="stopping-multiple-processes-using-_taskkillexe_"></a><span data-ttu-id="da0aa-144">Beenden mehrerer Prozesse mit _taskkill.exe_</span><span class="sxs-lookup"><span data-stu-id="da0aa-144">Stopping multiple processes using _taskkill.exe_</span></span>
<span data-ttu-id="da0aa-145">Diese Abfrage prüft, ob versucht wird, mindestens 10 getrennte Prozesse mit dem _taskkill.exe_ -Dienstprogramm zu beenden.</span><span class="sxs-lookup"><span data-stu-id="da0aa-145">This query checks for attempts to stop at least 10 separate processes using the _taskkill.exe_ utility.</span></span> [<span data-ttu-id="da0aa-146">Abfrage ausführen</span><span class="sxs-lookup"><span data-stu-id="da0aa-146">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RS2vCUBCFz7rgfwiuIkit3eumVSgtpYvuS9SLDTY2eLUvxN_eb8YHKlFkyNzJzDkn505aailRX7mmGlFlmhNBhUrOSGeuT3L0s6QqNaMagolEcMyCbApjx2e8TYhcH8Q1mB-emq50z_lF39gvBzo9-gEF-6Yhlyh9653ejCfRK6zCsaZfuJOu-x2jkqqN-0Yls-8-gp6dZ52OVuT6Sad1plulyN0KIkMt15_zt7zHDe8OBwv3btoJToa7Tnp0T8Ou9WzfT761gPOm3_FQ16Zxp2qcCdg33_rlyokG-iXv7_4BRNMnhkortmvTW6rqnZ7bgP2Vtm70D3d9wcFaAgAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using taskkill.exe
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "taskkill.exe" 
| summarize taskKillCount = dcount(ProcessCommandLine), TaskKillList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where taskKillCount > 10
```
  
### <a name="stopping-processes-using-_net-stop_"></a><span data-ttu-id="da0aa-147">Beenden von Prozessen mit _net stop_</span><span class="sxs-lookup"><span data-stu-id="da0aa-147">Stopping processes using _net stop_</span></span>
<span data-ttu-id="da0aa-148">Diese Abfrage prüft, ob versucht wird, mindestens 10 getrennte Prozesse mit dem Befehl _net stop_ zu beenden.</span><span class="sxs-lookup"><span data-stu-id="da0aa-148">This query checks for attempts to stop at least 10 separate processes using the _net stop_ command.</span></span> [<span data-ttu-id="da0aa-149">Abfrage ausführen</span><span class="sxs-lookup"><span data-stu-id="da0aa-149">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI2RQUvDUBCE5yz0P4ScUijWereXVkGQIti7aA1pqakhL7VVxN_ebzc1NBChPLJv2Z2ZN5sdaqhId1ppozeyF1WcVLkK7kCl0gcx-F2QFSrJFmACJ3XMlmgKGfmGWnXC6OlCU2qfIIz12OLfUk_h2FuG_IG505JayRdpDit3bIW33B2M3WeGSqIRrvudTJvpnWzmPKvc6JcYHx1eEvd8savV07e9TchzTt198AlNZ0kluNLfjHHjIPAvak4J_tvx9XtPR6ypbn1icxShvGgqyVkO-hrAm7VUrRcaTWOs6T_7hs7XjfSqL-Lpvu5BDLxjqKRjI9a9Juvew__T2x5HutIB3T1qt4QCAAA&runQuery=true&timeRangeId=week)

```kusto
// Find attempts to stop processes using net stop
DeviceProcessEvents
| where Timestamp > ago(1d)
| where FileName =~ "net.exe" and ProcessCommandLine has "stop"
| summarize netStopCount = dcount(ProcessCommandLine), NetStopList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 2m)
| where netStopCount > 10
```
### <a name="deletion-of-data-on-multiple-drives-using-_cipherexe_"></a><span data-ttu-id="da0aa-150">Löschen von Daten auf mehreren Laufwerken mit _cipher.exe_</span><span class="sxs-lookup"><span data-stu-id="da0aa-150">Deletion of data on multiple drives using _cipher.exe_</span></span>
<span data-ttu-id="da0aa-151">Diese Abfrage sucht nach versuchen, Daten auf mehreren Laufwerken mit _cipher.exe_ zu löschen.</span><span class="sxs-lookup"><span data-stu-id="da0aa-151">This query checks for attempts to delete data on multiple drives using _cipher.exe_.</span></span> <span data-ttu-id="da0aa-152">Diese Aktivität wird in der Regel von Ransomware ausgeführt, um die Wiederherstellung von Daten nach der Verschlüsselung zu verhindern.</span><span class="sxs-lookup"><span data-stu-id="da0aa-152">This activity is typically done by ransomware to prevent recovery of data after encryption.</span></span> [<span data-ttu-id="da0aa-153">Abfrage ausführen</span><span class="sxs-lookup"><span data-stu-id="da0aa-153">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAI1SXUvDQBCcZ8H_cOQpgWLoD7AvVUEo4oPvElO1pblUcmn9QPztzk6TEuEsIdzdZndndm73cuRwWGDLb0PrhWfDs8Qab1jhmX8X3D-4HJbcK66W0Rqv8hT8K4RsiPW0PHbMasVQdbiGf3vaAec4wxWtPT0lz3vhSsUCrpVVE33I_Cb6vdNhTA9EeeVaVc8KDjOugmq2SDFlrSyKvCHS1NwJZ55L_HBPondNGDGWXP2JdyMnv927UnXHWwf6l4MunupXTOPfXszVT8_smriFOCxrRU-QclOQDLgCNRwQ1u8vZc8H2o1xp-7a7U1NefSko6pnmKjakNVi4chpiA39j-rGeF6HJ3xyH76NW2ZMFLGsNDJ9i05pZSPmVdDfq-jncfqtOuU5zSuQz6Zq92w7Hfbm-9cUm-d_vZ9J9S81O2KIfAMAAA&runQuery=true&timeRangeId=week)

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

### <a name="clearing-of-forensic-evidence-from-event-logs-using-_wevtutil_"></a><span data-ttu-id="da0aa-154">Löschen forensischer Beweise aus Ereignisprotokollen mithilfe von _wevtutil_</span><span class="sxs-lookup"><span data-stu-id="da0aa-154">Clearing of forensic evidence from event logs using _wevtutil_</span></span>
<span data-ttu-id="da0aa-155">Diese Abfrage prüft, ob versucht wird, mindestens 10 Protokolleinträge aus Ereignisprotokollen mithilfe von _wevtutil_ zu löschen.</span><span class="sxs-lookup"><span data-stu-id="da0aa-155">This query checks for attempts to clear at least 10 log entries from event logs using _wevtutil_.</span></span> [<span data-ttu-id="da0aa-156">Abfrage ausführen</span><span class="sxs-lookup"><span data-stu-id="da0aa-156">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWRTU_CQBCG37OJ_2HDqSQkwMGjXgoHEg4cUI-m2hUaqGu6BaPxx_vsEFCTxmA225nOvB_tzFBDOc0VOBuyZ2JD3CnKEwMVpzfyPbVWlba8t9Sdnsi9CsPXdLfWf7Wq4xm0QuVSF5oYv4LhtQAfLIucKXWvF5gH5Ke5rak1prKEVRu2xalG3emGW6AdlGmsUv1O5m-fnLzmFHiV_G9FTKg1lUjs6Z5vucPvljsD0TOXhP6_Vm7841dFZnPAN2A_DDu36eSnCSbNnc3B6Zpb4nasZGf59zWA963orZdcEiKelBNvQ_fBNny-utOj3nn-3OUMxMA6CZV1bCt1r8i6d_TXFNKWxxrpC48hm8miAgAA&runQuery=true&timeRangeId=week)

```kusto
// Look for use of wevtutil to clear multiple logs
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "WEVTUTIL" and ProcessCommandLine has "CL"
| summarize LogClearCount = dcount(ProcessCommandLine), ClearedLogList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where LogClearCount > 10
```

### <a name="turning-off-services-using-_scexe_"></a><span data-ttu-id="da0aa-157">Deaktivieren von Diensten mit _sc.exe_</span><span class="sxs-lookup"><span data-stu-id="da0aa-157">Turning off services using _sc.exe_</span></span>
<span data-ttu-id="da0aa-158">Diese Abfrage prüft, ob versucht wird, mindestens 10 vorhandene Dienste mit _sc.exe_ zu deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="da0aa-158">This query checks for attempts to turn off at least 10 existing services using _sc.exe_.</span></span> [<span data-ttu-id="da0aa-159">Abfrage ausführen</span><span class="sxs-lookup"><span data-stu-id="da0aa-159">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAKWST2vCQBDF31nodwg5RZCqhx7bi3ooeCjovaQxraIxxfU_fvj-ZoiiEIqlhM3Ozrz3ZnZm22or0lAl3xzrk33FHpTpUbn2rEgTzfCk-tACa6kvR-Qgt5wzrKAHNdTHOnveiJZVLGiAP4e5rpAnFHaauoZlGMMqHLsmT6FvfC-slFylEnWpoVnLvM3Twy74UnJNuJdVa6gpnsAe-81iVzbE3_kZiCV9mlHZf3Sue5pzii-3C9pU3BWYo_NGKPdvGJZh4x2N9Owzyi6e5K5qmmrVKg_9dNY11hzvu0_8fu0ItQP_6zfxCqLlEUMlNVO36BNW_ax_74K9l646-gFts39I1AIAAA&runQuery=true&timeRangeId=week)

```kusto
// Look for sc.exe disabling services
DeviceProcessEvents
| where Timestamp > ago(1d)
| where ProcessCommandLine has "sc" and ProcessCommandLine has "config" and ProcessCommandLine has "disabled"
| summarize ScDisableCount = dcount(ProcessCommandLine), ScDisableList = make_set(ProcessCommandLine) by DeviceId, bin(Timestamp, 5m)
| where ScDisableCount > 10
```

### <a name="turning-off-system-restore"></a><span data-ttu-id="da0aa-160">Deaktivieren der System Wiederherstellung</span><span class="sxs-lookup"><span data-stu-id="da0aa-160">Turning off System Restore</span></span>
<span data-ttu-id="da0aa-161">Diese Abfrage identifiziert Versuche, die Systemwiederherstellung zu beenden und das System daran zu hindern, Wiederherstellungspunkte zu erstellen, die zum Wiederherstellen von von Ransomware verschlüsselten Daten verwendet werden können.</span><span class="sxs-lookup"><span data-stu-id="da0aa-161">This query identifies attempts to stop System Restore and prevent the system from creating restore points, which can be used to recover data encrypted by ransomware.</span></span> [<span data-ttu-id="da0aa-162">Abfrage ausführen</span><span class="sxs-lookup"><span data-stu-id="da0aa-162">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAK2S3UrDQBCFz7XgO6y9id4o6HWvrIVCkaJPENOYFNumZGO1ID673w4xJA1isbJMZnZ-zpzM7EiptlooQc9UqjDLc-7wp1qrwj7Via44MzK35FTotTI5PXMr0aVe8cy15NzoGo-zqg_0m3KQSsRpQtbC6uMGpdt3jHeJfU_GymqG-uQb9XpcEn1HIuvmGpZT0Aq99Dim4G3ousNO8K04sSE6EEN22kL6jvzO-LaDNW2QzqxLmGBsPo9vUMt_oA8Na3DQv3vwcmPiifpmds48jkhut8T2FLikxm_T4bI_m_6uQt-wrXO28lPPSBcdziOqPFlP9RYy47tDKtuZM07hVtSvaJ_HYRPL63-NyMgtmtWv5684jy2WDx2O0ZEM562ZBLQvURxur6gDAAA&runQuery=true&timeRangeId=week)

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

### <a name="backup-deletion"></a><span data-ttu-id="da0aa-163">Sicherungs Löschung</span><span class="sxs-lookup"><span data-stu-id="da0aa-163">Backup deletion</span></span>
<span data-ttu-id="da0aa-164">Diese Abfrage identifiziert die Verwendung von _wmic.exe_ zum Löschen von Shadow Copy-Momentaufnahmen vor der Verschlüsselung.</span><span class="sxs-lookup"><span data-stu-id="da0aa-164">This query identifies use of _wmic.exe_ to delete shadow copy snapshots prior to encryption.</span></span> [<span data-ttu-id="da0aa-165">Abfrage ausführen</span><span class="sxs-lookup"><span data-stu-id="da0aa-165">Run query</span></span>](https://security.microsoft.com/hunting?query=H4sIAAAAAAAEAJWS2wqCQBCG_-ugd5CupTfoqgMIEV70AqFLGp5QyYLo2fsavEjxwlhWZ7-df2Z2dndyuitVxD9UrdKshrGHOxVqsZda6CVPnRJYzfR0QJVhnXRRbmSjN98VXrlFXEMfzNWkfphti50zLmSMdURfmFcCaSxqY3aMX4eqVKUn1OsV_8eLWX_rbwcVVhblBovY8bT76U-AxoedWeeWp7WzV0YDMqSQFNZavuuopnHH_Iku-lbJnLPMyxnYDTp4bZ5P9M5uNpsZIWSn7l_CuNoPSggb4z4CAAA&runQuery=true&timeRangeId=week)

```kusto
DeviceProcessEvents
| where FileName =~ "wmic.exe"
| where ProcessCommandLine has "shadowcopy" and ProcessCommandLine has "delete"
| project DeviceId, Timestamp, InitiatingProcessFileName, FileName,
ProcessCommandLine, InitiatingProcessIntegrityLevel, InitiatingProcessParentFileName
```

## <a name="check-for-multiple-signs-of-ransomware-activity"></a><span data-ttu-id="da0aa-166">Überprüfen auf mehrere Zeichen der Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="da0aa-166">Check for multiple signs of ransomware activity</span></span>
<span data-ttu-id="da0aa-167">Anstatt mehrere Abfragen separat auszuführen, können Sie auch eine umfassende Abfrage verwenden, die auf mehrere Anzeichen von Ransomware-Aktivitäten prüft, um betroffene Geräte zu identifizieren.</span><span class="sxs-lookup"><span data-stu-id="da0aa-167">Instead of running several queries separately, you can also use a comprehensive query that checks for multiple signs of ransomware activity to identify affected devices.</span></span> <span data-ttu-id="da0aa-168">Die folgende konsolidierte Abfrage:</span><span class="sxs-lookup"><span data-stu-id="da0aa-168">The following consolidated  query:</span></span>
- <span data-ttu-id="da0aa-169">Sucht nach relativ konkreten und subtilen Zeichen der Ransomware-Aktivität</span><span class="sxs-lookup"><span data-stu-id="da0aa-169">Looks for both relatively concrete and subtle signs of ransomware activity</span></span>
- <span data-ttu-id="da0aa-170">Wiegt das vorhanden sein dieser Zeichen</span><span class="sxs-lookup"><span data-stu-id="da0aa-170">Weighs the presence of these signs</span></span>
- <span data-ttu-id="da0aa-171">Identifiziert Geräte mit einer höheren Wahrscheinlichkeit, Ziele von Ransomware zu sein.</span><span class="sxs-lookup"><span data-stu-id="da0aa-171">Identifies devices with a higher chance of being targets of ransomware</span></span> 

<span data-ttu-id="da0aa-172">Wenn diese konsolidierte Abfrage ausgeführt wird, wird eine Liste der Geräte zurückgegeben, die mehrere Angriffs Zeichen aufweisen.</span><span class="sxs-lookup"><span data-stu-id="da0aa-172">When run, this consolidated query returns a list of devices that have exhibited multiple signs of attack.</span></span> <span data-ttu-id="da0aa-173">Die Anzahl der einzelnen Ransomware-Aktivitätstypen wird ebenfalls angezeigt.</span><span class="sxs-lookup"><span data-stu-id="da0aa-173">The count of each type of ransomware activity is also shown.</span></span> <span data-ttu-id="da0aa-174">Um diese konsolidierte Abfrage auszuführen, kopieren Sie Sie direkt in den [erweiterten Jagd Abfrage-Editor](https://security.microsoft.com/advanced-hunting).</span><span class="sxs-lookup"><span data-stu-id="da0aa-174">To run this consolidated query, copy it directly to the [advanced hunting query editor](https://security.microsoft.com/advanced-hunting).</span></span> 

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
### <a name="understand-and-tweak-the-query-results"></a><span data-ttu-id="da0aa-175">Verstehen und Optimieren der Abfrageergebnisse</span><span class="sxs-lookup"><span data-stu-id="da0aa-175">Understand and tweak the query results</span></span>
<span data-ttu-id="da0aa-176">Die konsolidierte Abfrage gibt die folgenden Ergebnisse zurück:</span><span class="sxs-lookup"><span data-stu-id="da0aa-176">The consolidated query returns the following results:</span></span>

- <span data-ttu-id="da0aa-177">**Device**-Kennung – identifiziert das betroffene Gerät</span><span class="sxs-lookup"><span data-stu-id="da0aa-177">**DeviceId**—identifies the affected device</span></span> 
- <span data-ttu-id="da0aa-178">Zeit **Stempel**– das erste Mal, wenn ein Anzeichen für eine Ransomware-Aktivität auf dem Gerät beobachtet wurde</span><span class="sxs-lookup"><span data-stu-id="da0aa-178">**TimeStamp**—first time any sign of ransomware activity was observed on the device</span></span>
- <span data-ttu-id="da0aa-179">**Bestimmte Aktivitäts Zeichen**– die Anzahl für jedes in mehreren Spalten angezeigte Zeichen wie _Bcdedit_ oder _FsUtil_</span><span class="sxs-lookup"><span data-stu-id="da0aa-179">**Specific signs of activity**—the count for each sign shown in multiple columns, such as _BcdEdit_ or _FsUtil_</span></span>
- <span data-ttu-id="da0aa-180">**TotalEvidenceCount**– Anzahl beobachteter Zeichen</span><span class="sxs-lookup"><span data-stu-id="da0aa-180">**TotalEvidenceCount**—number of observed signs</span></span>
- <span data-ttu-id="da0aa-181">**UniqueEvidenceCount**– Anzahl der Typen beobachteter Zeichen</span><span class="sxs-lookup"><span data-stu-id="da0aa-181">**UniqueEvidenceCount**—number of types of observed signs</span></span>

![Bild der Abfrageergebnisse für Ransomware-Aktivität](../../media/advanced-hunting-ransomware-query.png)

<span data-ttu-id="da0aa-183">*Abfrageergebnisse mit betroffenen Geräten und Zählungen verschiedener Anzeichen von Ransomware-Aktivität*</span><span class="sxs-lookup"><span data-stu-id="da0aa-183">*Query results showing affected devices and counts of various signs of ransomware activity*</span></span>

<span data-ttu-id="da0aa-184">Standardmäßig listet das Abfrageergebnis nur Geräte mit mehr als zwei Arten von Ransomware-Aktivität auf.</span><span class="sxs-lookup"><span data-stu-id="da0aa-184">By default, the query result lists only devices that have more than two types of ransomware activity.</span></span> <span data-ttu-id="da0aa-185">Wenn Sie alle Geräte mit einer Ransomware-Aktivität anzeigen möchten, ändern Sie den folgenden `where` Operator, und legen Sie die Zahl auf NULL (0) fest.</span><span class="sxs-lookup"><span data-stu-id="da0aa-185">To see all devices with any sign of ransomware activity, modify the following `where` operator and set the number to zero (0).</span></span> <span data-ttu-id="da0aa-186">Wenn Sie weniger Geräte anzeigen möchten, legen Sie eine höhere Zahl fest.</span><span class="sxs-lookup"><span data-stu-id="da0aa-186">To see fewer devices, set a higher number.</span></span> 

```kusto
| where UniqueEvidenceCount > 2
```

## <a name="related-topics"></a><span data-ttu-id="da0aa-187">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="da0aa-187">Related topics</span></span>
- [<span data-ttu-id="da0aa-188">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="da0aa-188">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="da0aa-189">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="da0aa-189">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="da0aa-190">Arbeiten mit Abfrageergebnissen</span><span class="sxs-lookup"><span data-stu-id="da0aa-190">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="da0aa-191">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="da0aa-191">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="da0aa-192">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="da0aa-192">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="da0aa-193">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="da0aa-193">Apply query best practices</span></span>](advanced-hunting-best-practices.md)