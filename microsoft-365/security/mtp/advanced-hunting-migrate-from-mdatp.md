---
title: Migrieren erweiterter Suchabfragen von Microsoft Defender for Endpoint
description: Erfahren Sie, wie Sie Ihre Microsoft Defender for Endpoint-Abfragen so anpassen, dass Sie sie in Microsoft 365 Defender verwenden können.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, M365, Microsoft Defender ATP, Mdatp, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Zuordnung
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: 521b5fc2a8efee83b6a2931e7dbc1c713bd63cd2
ms.sourcegitcommit: c0cfb9b354db56fdd329aec2a89a9b2cf160c4b0
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/03/2021
ms.locfileid: "50094807"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="850e2-104">Migrieren erweiterter Suchabfragen von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="850e2-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="850e2-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="850e2-105">**Applies to:**</span></span>
- <span data-ttu-id="850e2-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="850e2-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="850e2-107">Verschieben Sie Ihre Workflows für die erweiterte Suche von Microsoft Defender for Endpoint, um proaktiv nach Bedrohungen zu abwehren, indem Sie einen größeren Satz von Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="850e2-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="850e2-108">In Microsoft 365 Defender erhalten Sie Zugriff auf Daten aus anderen Microsoft 365-Sicherheitslösungen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="850e2-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="850e2-109">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="850e2-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="850e2-110">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="850e2-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="850e2-111">Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="850e2-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="850e2-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="850e2-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="850e2-113">Die meisten Microsoft Defender for Endpoint-Kunden können [Microsoft 365 Defender ohne zusätzliche Lizenzen verwenden.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="850e2-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="850e2-114">Um mit dem Übergang Ihrer Workflows für die erweiterte Suche von Defender for Endpoint zu beginnen, aktivieren Sie [Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="850e2-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="850e2-115">Sie können einen Übergang ohne Auswirkungen auf Ihre vorhandenen Defender for Endpoint-Workflows.</span><span class="sxs-lookup"><span data-stu-id="850e2-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="850e2-116">Gespeicherte Abfragen bleiben erhalten, und benutzerdefinierte Erkennungsregeln werden weiterhin ausgeführt und generieren Warnungen.</span><span class="sxs-lookup"><span data-stu-id="850e2-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="850e2-117">Sie sind jedoch in Microsoft 365 Defender sichtbar.</span><span class="sxs-lookup"><span data-stu-id="850e2-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="850e2-118">Schematabellen nur in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="850e2-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="850e2-119">Das [Microsoft 365 Defender Advanced Hunting-Schema](advanced-hunting-schema-tables.md) bietet zusätzliche Tabellen mit Daten aus verschiedenen Microsoft 365-Sicherheitslösungen.</span><span class="sxs-lookup"><span data-stu-id="850e2-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="850e2-120">Die folgenden Tabellen sind nur in Microsoft 365 Defender verfügbar:</span><span class="sxs-lookup"><span data-stu-id="850e2-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="850e2-121">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="850e2-121">Table name</span></span> | <span data-ttu-id="850e2-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="850e2-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="850e2-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="850e2-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="850e2-124">Dateien, IP-Adressen, URLs, Benutzer oder Geräte, die Warnungen zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="850e2-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="850e2-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="850e2-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="850e2-126">Warnungen von Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity, einschließlich Schweregradinformationen und Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="850e2-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="850e2-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="850e2-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="850e2-128">Dateibezogene Aktivitäten in Cloud-Apps und -Diensten</span><span class="sxs-lookup"><span data-stu-id="850e2-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="850e2-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="850e2-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="850e2-130">Informationen zu Dateien, die an E-Mails angefügt sind</span><span class="sxs-lookup"><span data-stu-id="850e2-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="850e2-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="850e2-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="850e2-132">Microsoft 365-E-Mail-Ereignisse, einschließlich E-Mail-Übermittlung und Blockieren von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="850e2-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="850e2-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="850e2-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="850e2-134">Sicherheitsereignisse, die nach der Zustellung auftreten, nachdem Microsoft 365 die E-Mails an das Empfängerpostfach zugestellt hat</span><span class="sxs-lookup"><span data-stu-id="850e2-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="850e2-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="850e2-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="850e2-136">Informationen zu URLs in E-Mails</span><span class="sxs-lookup"><span data-stu-id="850e2-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="850e2-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="850e2-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="850e2-138">Ereignisse, an denen ein lokales Domänencontroller beteiligt ist, auf dem Active Directory (AD) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="850e2-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="850e2-139">In dieser Tabelle wird eine Reihe von identitätsbezogenen Ereignissen und Systemereignissen auf dem Domänencontroller behandelt.</span><span class="sxs-lookup"><span data-stu-id="850e2-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="850e2-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="850e2-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="850e2-141">Kontoinformationen aus verschiedenen Quellen, einschließlich Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="850e2-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="850e2-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="850e2-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="850e2-143">Authentifizierungsereignisse für Active Directory und Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="850e2-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="850e2-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="850e2-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="850e2-145">Abfragen für Active Directory-Objekte, z. B. Benutzer, Gruppen, Geräte und Domänen</span><span class="sxs-lookup"><span data-stu-id="850e2-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="850e2-146">Tabelle "DeviceAlertEvents zuordnung"</span><span class="sxs-lookup"><span data-stu-id="850e2-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="850e2-147">Die `AlertInfo` Tabelle und die Tabellen ersetzen die Tabelle im Microsoft Defender for `AlertEvidence` `DeviceAlertEvents` Endpoint-Schema.</span><span class="sxs-lookup"><span data-stu-id="850e2-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="850e2-148">Zusätzlich zu Daten zu Gerätewarnungen enthalten diese beiden Tabellen Daten zu Warnungen für Identitäten, Apps und E-Mails.</span><span class="sxs-lookup"><span data-stu-id="850e2-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="850e2-149">Verwenden Sie die folgende Tabelle, um zu überprüfen, wie Spalten Spalten in den Und `DeviceAlertEvents` `AlertInfo` Tabellen `AlertEvidence` zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="850e2-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="850e2-150">Zusätzlich zu den Spalten in der folgenden Tabelle enthält die Tabelle viele weitere Spalten, die ein ganzheitliches Bild von Warnungen aus `AlertEvidence` verschiedenen Quellen liefern.</span><span class="sxs-lookup"><span data-stu-id="850e2-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="850e2-151">Anzeigen aller AlertEvidence-Spalten</span><span class="sxs-lookup"><span data-stu-id="850e2-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="850e2-152">Spalte "DeviceAlertEvents"</span><span class="sxs-lookup"><span data-stu-id="850e2-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="850e2-153">Wo die gleichen Daten in Microsoft 365 Defender zu finden sind</span><span class="sxs-lookup"><span data-stu-id="850e2-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="850e2-154">`AlertInfo` und  `AlertEvidence` Tabellen</span><span class="sxs-lookup"><span data-stu-id="850e2-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="850e2-155">`AlertInfo` und  `AlertEvidence` Tabellen</span><span class="sxs-lookup"><span data-stu-id="850e2-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="850e2-156">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="850e2-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="850e2-157">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="850e2-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="850e2-158">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="850e2-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="850e2-159">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="850e2-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="850e2-160">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="850e2-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="850e2-161">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="850e2-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="850e2-162">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="850e2-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="850e2-163">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="850e2-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="850e2-164">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="850e2-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="850e2-165">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="850e2-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="850e2-166">Diese Spalte wird in der Regel in Microsoft Defender for Endpoint verwendet, um verwandte Datensätze in anderen Tabellen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="850e2-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="850e2-167">In Microsoft 365 Defender können Sie verwandte Daten direkt aus der Tabelle `AlertEvidence` erhalten.</span><span class="sxs-lookup"><span data-stu-id="850e2-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="850e2-168">Diese Spalte wird in der Regel in Microsoft Defender for Endpoint für zusätzliche Ereignisinformationen in anderen Tabellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="850e2-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="850e2-169">In Microsoft 365 Defender können Sie verwandte Daten direkt aus der Tabelle `AlertEvidence` erhalten.</span><span class="sxs-lookup"><span data-stu-id="850e2-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="850e2-170">Anpassen vorhandener Microsoft Defender für Endpunktabfragen</span><span class="sxs-lookup"><span data-stu-id="850e2-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="850e2-171">Microsoft Defender for Endpoint-Abfragen funktionieren wie beh nk, es sei denn, sie verweisen auf die `DeviceAlertEvents` Tabelle.</span><span class="sxs-lookup"><span data-stu-id="850e2-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="850e2-172">Um diese Abfragen in Microsoft 365 Defender zu verwenden, wenden Sie die folgenden Änderungen an:</span><span class="sxs-lookup"><span data-stu-id="850e2-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="850e2-173">Ersetzen `DeviceAlertEvents` Durch `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="850e2-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="850e2-174">Verbinden Sie `AlertInfo` die Tabellen und die `AlertEvidence` Tabellen, um entsprechende Daten zu `AlertId` erhalten.</span><span class="sxs-lookup"><span data-stu-id="850e2-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="850e2-175">Ursprüngliche Abfrage</span><span class="sxs-lookup"><span data-stu-id="850e2-175">Original query</span></span>
<span data-ttu-id="850e2-176">Die folgende Abfrage wird `DeviceAlertEvents` in Microsoft Defender for __ Endpoint verwendet, um die Warnungen zu erhalten, diepowershell.exe:</span><span class="sxs-lookup"><span data-stu-id="850e2-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="850e2-177">Geänderte Abfrage</span><span class="sxs-lookup"><span data-stu-id="850e2-177">Modified query</span></span>
<span data-ttu-id="850e2-178">Die folgende Abfrage wurde für die Verwendung in Microsoft 365 Defender angepasst.</span><span class="sxs-lookup"><span data-stu-id="850e2-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="850e2-179">Anstatt den Dateinamen direkt aus zu überprüfen, wird der Dateiname in dieser Tabelle bei der Verknüpfung und überprüfung auf `DeviceAlertEvents` `AlertEvidence` den Dateinamen überprüft.</span><span class="sxs-lookup"><span data-stu-id="850e2-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```



## <a name="see-also"></a><span data-ttu-id="850e2-180">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="850e2-180">See also</span></span>
- [<span data-ttu-id="850e2-181">Aktivieren von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="850e2-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="850e2-182">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="850e2-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="850e2-183">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="850e2-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="850e2-184">Erweiterte Suche in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="850e2-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)