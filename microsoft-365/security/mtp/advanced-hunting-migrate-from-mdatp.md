---
title: Migrieren von erweiterten Jagd Abfragen von Microsoft Defender ATP
description: Hier erfahren Sie, wie Sie Ihre Microsoft Defender ATP-Abfragen anpassen können, damit Sie Sie in Microsoft Threat Protection verwenden können.
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Microsoft Defender ATP, mdatp, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Zuordnung
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
- m365-initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b1738180e192baafa60f76fada1e433319922b91
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412682"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a><span data-ttu-id="c63fe-104">Migrieren von erweiterten Jagd Abfragen von Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="c63fe-104">Migrate advanced hunting queries from Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="c63fe-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c63fe-105">**Applies to:**</span></span>
- <span data-ttu-id="c63fe-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c63fe-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="c63fe-107">Stellen Sie Ihre erweiterten Jagd Workflows von Microsoft Defender ATP so ein, dass Sie mit einer breiteren Datenmenge proaktiv nach Bedrohungen suchen.</span><span class="sxs-lookup"><span data-stu-id="c63fe-107">Move your advanced hunting workflows from Microsoft Defender ATP to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="c63fe-108">In Microsoft Threat Protection erhalten Sie Zugriff auf Daten aus anderen Microsoft 365-Sicherheitslösungen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="c63fe-108">In Microsoft Threat Protection, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="c63fe-109">Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c63fe-109">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="c63fe-110">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c63fe-110">Office 365 Advanced Threat Protection</span></span>
- <span data-ttu-id="c63fe-111">Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="c63fe-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="c63fe-112">Azure Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c63fe-112">Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="c63fe-113">Die meisten Microsoft Defender ATP-Kunden können [Microsoft Threat Protection ohne zusätzliche Lizenzen verwenden](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="c63fe-113">Most Microsoft Defender ATP customers can [use Microsoft Threat Protection without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="c63fe-114">Um mit dem Übergang ihrer erweiterten Jagd Workflows von Microsoft Defender ATP zu beginnen, [Aktivieren Sie Microsoft Threat Protection](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="c63fe-114">To start transitioning your advanced hunting workflows from Microsoft Defender ATP, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

<span data-ttu-id="c63fe-115">Sie können den Übergang ohne Auswirkungen auf die vorhandenen Microsoft Defender ATP-Workflows durchführen.</span><span class="sxs-lookup"><span data-stu-id="c63fe-115">You can transition without affecting your existing Microsoft Defender ATP workflows.</span></span> <span data-ttu-id="c63fe-116">Gespeicherte Abfragen bleiben intakt, und benutzerdefinierte Erkennungsregeln werden weiterhin ausgeführt und Warnungen generiert.</span><span class="sxs-lookup"><span data-stu-id="c63fe-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="c63fe-117">Sie werden jedoch in Microsoft Threat Protection angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c63fe-117">They will, however, be visible in Microsoft Threat Protection.</span></span> 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a><span data-ttu-id="c63fe-118">Schema Tabellen in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c63fe-118">Schema tables in Microsoft Threat Protection only</span></span>
<span data-ttu-id="c63fe-119">Das [Advanced Hunting-Schema von Microsoft Threat Protection](advanced-hunting-schema-tables.md) bietet zusätzliche Tabellen, die Daten aus verschiedenen Microsoft 365-Sicherheitslösungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="c63fe-119">The [Microsoft Threat Protection advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="c63fe-120">Die folgenden Tabellen stehen nur in Microsoft Threat Protection zur Verfügung:</span><span class="sxs-lookup"><span data-stu-id="c63fe-120">The following tables are available only in Microsoft Threat Protection:</span></span>

| <span data-ttu-id="c63fe-121">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="c63fe-121">Table name</span></span> | <span data-ttu-id="c63fe-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c63fe-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="c63fe-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="c63fe-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="c63fe-124">Dateien, IP-Adressen, URLs, Benutzer oder Geräte, die Warnungen zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="c63fe-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="c63fe-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="c63fe-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="c63fe-126">Warnungen von Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security und Azure ATP, einschließlich schwere Informationen und Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="c63fe-126">Alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="c63fe-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="c63fe-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="c63fe-128">Dateibezogene Aktivitäten in Cloud-apps und-Diensten</span><span class="sxs-lookup"><span data-stu-id="c63fe-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="c63fe-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="c63fe-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="c63fe-130">Informationen zu an e-Mails angeschlossenen Dateien</span><span class="sxs-lookup"><span data-stu-id="c63fe-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="c63fe-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="c63fe-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="c63fe-132">E-Mail-Ereignisse von Microsoft 365, einschließlich e-Mail-Zustellung und Blockierungs Ereignisse</span><span class="sxs-lookup"><span data-stu-id="c63fe-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="c63fe-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="c63fe-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="c63fe-134">Sicherheitsereignisse, die nach der Zustellung auftreten, nachdem Microsoft 365 die e-Mails an das Empfängerpostfach übermittelt hat</span><span class="sxs-lookup"><span data-stu-id="c63fe-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="c63fe-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="c63fe-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="c63fe-136">Informationen zu URLs in e-Mails</span><span class="sxs-lookup"><span data-stu-id="c63fe-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="c63fe-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="c63fe-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="c63fe-138">Ereignisse, die einen lokalen Domänencontroller mit Active Directory (AD) umfassen.</span><span class="sxs-lookup"><span data-stu-id="c63fe-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="c63fe-139">Diese Tabelle enthält eine Reihe von identitätsbezogenen Ereignissen und Systemereignissen auf dem Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="c63fe-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="c63fe-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="c63fe-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="c63fe-141">Kontoinformationen aus verschiedenen Quellen, einschließlich Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="c63fe-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="c63fe-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="c63fe-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="c63fe-143">Authentifizierungsereignisse für Active Directory und Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="c63fe-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="c63fe-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="c63fe-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="c63fe-145">Abfragen für Active Directory-Objekte wie Benutzer, Gruppen, Geräte und Domänen</span><span class="sxs-lookup"><span data-stu-id="c63fe-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="c63fe-146">Map-DeviceAlertEvents-Tabelle</span><span class="sxs-lookup"><span data-stu-id="c63fe-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="c63fe-147">Die `AlertInfo` `AlertEvidence` Tabellen und ersetzen die `DeviceAlertEvents` Tabelle im ATP-Schema von Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="c63fe-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender ATP schema.</span></span> <span data-ttu-id="c63fe-148">Neben Daten zu Geräte Warnungen enthalten diese beiden Tabellendaten zu Warnungen für Identitäten, Apps und e-Mails.</span><span class="sxs-lookup"><span data-stu-id="c63fe-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="c63fe-149">Verwenden Sie die folgende Tabelle, um zu prüfen, wie `DeviceAlertEvents` Spalten Spalten in den `AlertInfo` -und-Tabellen zugeordnet werden `AlertEvidence` .</span><span class="sxs-lookup"><span data-stu-id="c63fe-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="c63fe-150">Zusätzlich zu den Spalten in der folgenden Tabelle enthält die `AlertEvidence` Tabelle viele andere Spalten, die ein ganzheitlicheres Bild der Benachrichtigungen aus verschiedenen Quellen bieten.</span><span class="sxs-lookup"><span data-stu-id="c63fe-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="c63fe-151">Alle AlertEvidence-Spalten anzeigen</span><span class="sxs-lookup"><span data-stu-id="c63fe-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="c63fe-152">DeviceAlertEvents-Spalte</span><span class="sxs-lookup"><span data-stu-id="c63fe-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="c63fe-153">Wo die gleichen Daten in Microsoft Threat Protection gefunden werden</span><span class="sxs-lookup"><span data-stu-id="c63fe-153">Where to find the same data in Microsoft Threat Protection</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="c63fe-154">`AlertInfo` und  `AlertEvidence` Tabellen</span><span class="sxs-lookup"><span data-stu-id="c63fe-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="c63fe-155">`AlertInfo` und  `AlertEvidence` Tabellen</span><span class="sxs-lookup"><span data-stu-id="c63fe-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="c63fe-156">`AlertEvidence` Tabelle</span><span class="sxs-lookup"><span data-stu-id="c63fe-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="c63fe-157">`AlertEvidence` Tabelle</span><span class="sxs-lookup"><span data-stu-id="c63fe-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="c63fe-158">`AlertInfo` Tabelle</span><span class="sxs-lookup"><span data-stu-id="c63fe-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="c63fe-159">`AlertInfo` Tabelle</span><span class="sxs-lookup"><span data-stu-id="c63fe-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="c63fe-160">`AlertInfo` Tabelle</span><span class="sxs-lookup"><span data-stu-id="c63fe-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="c63fe-161">`AlertEvidence` Tabelle</span><span class="sxs-lookup"><span data-stu-id="c63fe-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="c63fe-162">`AlertEvidence` Tabelle</span><span class="sxs-lookup"><span data-stu-id="c63fe-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="c63fe-163">`AlertEvidence` Tabelle</span><span class="sxs-lookup"><span data-stu-id="c63fe-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="c63fe-164">`AlertEvidence` Tabelle</span><span class="sxs-lookup"><span data-stu-id="c63fe-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="c63fe-165">`AlertInfo` Tabelle</span><span class="sxs-lookup"><span data-stu-id="c63fe-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="c63fe-166">Diese Spalte wird in der Regel in Microsoft Defender ATP verwendet, um verwandte Datensätze in anderen Tabellen zu finden.</span><span class="sxs-lookup"><span data-stu-id="c63fe-166">This column is typically used in Microsoft Defender ATP to locate related records in other tables.</span></span> <span data-ttu-id="c63fe-167">In Microsoft Threat Protection können Sie verwandte Daten direkt aus der Tabelle abrufen `AlertEvidence` .</span><span class="sxs-lookup"><span data-stu-id="c63fe-167">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="c63fe-168">Diese Spalte wird in der Regel in Microsoft Defender ATP für zusätzliche Ereignisinformationen in anderen Tabellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="c63fe-168">This column is typically used in Microsoft Defender ATP for additional event information in other tables.</span></span> <span data-ttu-id="c63fe-169">In Microsoft Threat Protection können Sie verwandte Daten direkt aus der Tabelle abrufen `AlertEvidence` .</span><span class="sxs-lookup"><span data-stu-id="c63fe-169">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a><span data-ttu-id="c63fe-170">Anpassen vorhandener ATP-Abfragen für Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="c63fe-170">Adjust existing Microsoft Defender ATP queries</span></span>
<span data-ttu-id="c63fe-171">Microsoft Defender ATP-Abfragen funktionieren nur dann, wenn Sie auf die `DeviceAlertEvents` Tabelle verweisen.</span><span class="sxs-lookup"><span data-stu-id="c63fe-171">Microsoft Defender ATP queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="c63fe-172">Wenn Sie diese Abfragen in Microsoft Threat Protection verwenden möchten, wenden Sie diese Änderungen an:</span><span class="sxs-lookup"><span data-stu-id="c63fe-172">To use these queries in Microsoft Threat Protection, apply these changes:</span></span>

- <span data-ttu-id="c63fe-173">Ersetzen Sie `DeviceAlertEvents` durch `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="c63fe-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="c63fe-174">Verknüpfen Sie die `AlertInfo` und die `AlertEvidence` Tabellen `AlertId` , um äquivalente Daten abzurufen.</span><span class="sxs-lookup"><span data-stu-id="c63fe-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="c63fe-175">Ursprüngliche Abfrage</span><span class="sxs-lookup"><span data-stu-id="c63fe-175">Original query</span></span>
<span data-ttu-id="c63fe-176">Die folgende Abfrage verwendet `DeviceAlertEvents` in Microsoft Defender ATP, um die Warnungen zu erhalten, die _powershell.exe_beinhalten:</span><span class="sxs-lookup"><span data-stu-id="c63fe-176">The following query uses `DeviceAlertEvents` in Microsoft Defender ATP to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="c63fe-177">Geänderte Abfrage</span><span class="sxs-lookup"><span data-stu-id="c63fe-177">Modified query</span></span>
<span data-ttu-id="c63fe-178">Die folgende Abfrage wurde für die Verwendung in Microsoft Threat Protection angepasst.</span><span class="sxs-lookup"><span data-stu-id="c63fe-178">The following query has been adjusted for use in Microsoft Threat Protection.</span></span> <span data-ttu-id="c63fe-179">Anstatt den Dateinamen direkt von zu überprüfen, wird der Dateiname `DeviceAlertEvents` `AlertEvidence` in dieser Tabelle verknüpft und überprüft.</span><span class="sxs-lookup"><span data-stu-id="c63fe-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="c63fe-180">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c63fe-180">Related topics</span></span>
- [<span data-ttu-id="c63fe-181">Aktivieren von Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="c63fe-181">Turn on Microsoft Threat Protection</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c63fe-182">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="c63fe-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c63fe-183">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="c63fe-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c63fe-184">Erweiterte Suche in Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="c63fe-184">Advanced hunting in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)