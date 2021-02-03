---
title: Migrieren erweiterter Suchabfragen von Microsoft Defender for Endpoint
description: Erfahren Sie, wie Sie Ihre Microsoft Defender for Endpoint-Abfragen so anpassen, dass Sie sie in Microsoft 365 Defender verwenden können.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, Mtp, m365, Microsoft Defender ATP, Mdatp, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Microsoft 365, Zuordnung
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
ms.openlocfilehash: 4e008488bdd733c9a7ce5b418fb838e0fe880d9d
ms.sourcegitcommit: d354727303d9574991b5a0fd298d2c9414e19f6c
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/02/2021
ms.locfileid: "50080740"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="beaf0-104">Migrieren erweiterter Suchabfragen von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="beaf0-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="beaf0-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="beaf0-105">**Applies to:**</span></span>
- <span data-ttu-id="beaf0-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="beaf0-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="beaf0-107">Verschieben Sie Ihre Workflows für die erweiterte Suche von Microsoft Defender for Endpoint, um proaktiv nach Bedrohungen zu abwehren, indem Sie eine breitere Gruppe von Daten verwenden.</span><span class="sxs-lookup"><span data-stu-id="beaf0-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="beaf0-108">In Microsoft 365 Defender erhalten Sie Zugriff auf Daten aus anderen Microsoft 365-Sicherheitslösungen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="beaf0-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="beaf0-109">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="beaf0-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="beaf0-110">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="beaf0-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="beaf0-111">Microsoft Cloud App-Sicherheit</span><span class="sxs-lookup"><span data-stu-id="beaf0-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="beaf0-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="beaf0-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="beaf0-113">Die meisten Microsoft Defender for Endpoint-Kunden können [Microsoft 365 Defender ohne zusätzliche Lizenzen verwenden.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="beaf0-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="beaf0-114">Um mit dem Übergang Ihrer Workflows für die erweiterte Suche von Defender for Endpoint zu beginnen, aktivieren Sie [Microsoft 365 Defender](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="beaf0-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="beaf0-115">Sie können einen Übergang ohne Auswirkungen auf Ihre vorhandenen Defender for Endpoint-Workflows.</span><span class="sxs-lookup"><span data-stu-id="beaf0-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="beaf0-116">Gespeicherte Abfragen bleiben erhalten, und benutzerdefinierte Erkennungsregeln werden weiterhin ausgeführt und generieren Warnungen.</span><span class="sxs-lookup"><span data-stu-id="beaf0-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="beaf0-117">Sie sind jedoch in Microsoft 365 Defender sichtbar.</span><span class="sxs-lookup"><span data-stu-id="beaf0-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="beaf0-118">Schematabellen nur in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="beaf0-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="beaf0-119">Das [Microsoft 365 Defender Advanced Hunting-Schema](advanced-hunting-schema-tables.md) bietet zusätzliche Tabellen mit Daten aus verschiedenen Microsoft 365-Sicherheitslösungen.</span><span class="sxs-lookup"><span data-stu-id="beaf0-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="beaf0-120">Die folgenden Tabellen sind nur in Microsoft 365 Defender verfügbar:</span><span class="sxs-lookup"><span data-stu-id="beaf0-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="beaf0-121">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="beaf0-121">Table name</span></span> | <span data-ttu-id="beaf0-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="beaf0-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="beaf0-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="beaf0-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="beaf0-124">Dateien, IP-Adressen, URLs, Benutzer oder Geräte, die Warnungen zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="beaf0-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="beaf0-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="beaf0-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="beaf0-126">Warnungen von Microsoft Defender für Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity, einschließlich Schweregradinformationen und Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="beaf0-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="beaf0-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="beaf0-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="beaf0-128">Dateibezogene Aktivitäten in Cloud-Apps und -Diensten</span><span class="sxs-lookup"><span data-stu-id="beaf0-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="beaf0-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="beaf0-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="beaf0-130">Informationen zu Dateien, die an E-Mails angefügt sind</span><span class="sxs-lookup"><span data-stu-id="beaf0-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="beaf0-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="beaf0-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="beaf0-132">Microsoft 365-E-Mail-Ereignisse, einschließlich E-Mail-Übermittlung und Blockieren von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="beaf0-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="beaf0-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="beaf0-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="beaf0-134">Sicherheitsereignisse, die nach der Zustellung auftreten, nachdem Microsoft 365 die E-Mails an das Empfängerpostfach übermittelt hat</span><span class="sxs-lookup"><span data-stu-id="beaf0-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="beaf0-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="beaf0-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="beaf0-136">Informationen zu URLs in E-Mails</span><span class="sxs-lookup"><span data-stu-id="beaf0-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="beaf0-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="beaf0-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="beaf0-138">Ereignisse, an denen ein lokales Domänencontroller beteiligt ist, auf dem Active Directory (AD) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="beaf0-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="beaf0-139">In dieser Tabelle wird eine Reihe von identitätsbezogenen Ereignissen und Systemereignissen auf dem Domänencontroller behandelt.</span><span class="sxs-lookup"><span data-stu-id="beaf0-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="beaf0-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="beaf0-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="beaf0-141">Kontoinformationen aus verschiedenen Quellen, einschließlich Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="beaf0-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="beaf0-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="beaf0-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="beaf0-143">Authentifizierungsereignisse für Active Directory und Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="beaf0-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="beaf0-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="beaf0-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="beaf0-145">Abfragen für Active Directory-Objekte, z. B. Benutzer, Gruppen, Geräte und Domänen</span><span class="sxs-lookup"><span data-stu-id="beaf0-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="beaf0-146">Tabelle "DeviceAlertEvents zuordnung"</span><span class="sxs-lookup"><span data-stu-id="beaf0-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="beaf0-147">Die `AlertInfo` Tabelle und die Tabellen ersetzen die Tabelle im Microsoft Defender for `AlertEvidence` `DeviceAlertEvents` Endpoint-Schema.</span><span class="sxs-lookup"><span data-stu-id="beaf0-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="beaf0-148">Zusätzlich zu Daten zu Gerätewarnungen enthalten diese beiden Tabellen Daten zu Warnungen für Identitäten, Apps und E-Mails.</span><span class="sxs-lookup"><span data-stu-id="beaf0-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="beaf0-149">Verwenden Sie die folgende Tabelle, um zu überprüfen, wie Spalten Spalten in den Und `DeviceAlertEvents` `AlertInfo` Tabellen `AlertEvidence` zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="beaf0-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="beaf0-150">Zusätzlich zu den Spalten in der folgenden Tabelle enthält die Tabelle viele weitere Spalten, die ein ganzheitliches Bild von Warnungen aus `AlertEvidence` verschiedenen Quellen liefern.</span><span class="sxs-lookup"><span data-stu-id="beaf0-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="beaf0-151">Anzeigen aller AlertEvidence-Spalten</span><span class="sxs-lookup"><span data-stu-id="beaf0-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="beaf0-152">Spalte "DeviceAlertEvents"</span><span class="sxs-lookup"><span data-stu-id="beaf0-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="beaf0-153">Wo die gleichen Daten in Microsoft 365 Defender zu finden sind</span><span class="sxs-lookup"><span data-stu-id="beaf0-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="beaf0-154">`AlertInfo` und  `AlertEvidence` Tabellen</span><span class="sxs-lookup"><span data-stu-id="beaf0-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="beaf0-155">`AlertInfo` und  `AlertEvidence` Tabellen</span><span class="sxs-lookup"><span data-stu-id="beaf0-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="beaf0-156">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="beaf0-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="beaf0-157">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="beaf0-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="beaf0-158">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="beaf0-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="beaf0-159">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="beaf0-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="beaf0-160">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="beaf0-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="beaf0-161">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="beaf0-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="beaf0-162">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="beaf0-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="beaf0-163">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="beaf0-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="beaf0-164">`AlertEvidence` Table</span><span class="sxs-lookup"><span data-stu-id="beaf0-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="beaf0-165">`AlertInfo` Table</span><span class="sxs-lookup"><span data-stu-id="beaf0-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="beaf0-166">Diese Spalte wird in der Regel in Microsoft Defender for Endpoint verwendet, um verwandte Datensätze in anderen Tabellen zu suchen.</span><span class="sxs-lookup"><span data-stu-id="beaf0-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="beaf0-167">In Microsoft 365 Defender können Sie verwandte Daten direkt aus der Tabelle `AlertEvidence` erhalten.</span><span class="sxs-lookup"><span data-stu-id="beaf0-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="beaf0-168">Diese Spalte wird in der Regel in Microsoft Defender for Endpoint für zusätzliche Ereignisinformationen in anderen Tabellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="beaf0-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="beaf0-169">In Microsoft 365 Defender können Sie verwandte Daten direkt aus der Tabelle `AlertEvidence` erhalten.</span><span class="sxs-lookup"><span data-stu-id="beaf0-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="beaf0-170">Anpassen vorhandener Microsoft Defender für Endpunktabfragen</span><span class="sxs-lookup"><span data-stu-id="beaf0-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="beaf0-171">Microsoft Defender for Endpoint-Abfragen funktionieren wie beh nk, es sei denn, sie verweisen auf die `DeviceAlertEvents` Tabelle.</span><span class="sxs-lookup"><span data-stu-id="beaf0-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="beaf0-172">Um diese Abfragen in Microsoft 365 Defender zu verwenden, wenden Sie die folgenden Änderungen an:</span><span class="sxs-lookup"><span data-stu-id="beaf0-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="beaf0-173">Ersetzen `DeviceAlertEvents` Durch `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="beaf0-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="beaf0-174">Verbinden Sie `AlertInfo` die Tabellen und die `AlertEvidence` Tabellen, um entsprechende Daten zu `AlertId` erhalten.</span><span class="sxs-lookup"><span data-stu-id="beaf0-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="beaf0-175">Ursprüngliche Abfrage</span><span class="sxs-lookup"><span data-stu-id="beaf0-175">Original query</span></span>
<span data-ttu-id="beaf0-176">Die folgende Abfrage wird `DeviceAlertEvents` in Microsoft Defender for __ Endpoint verwendet, um die Warnungen zu erhalten, diepowershell.exe:</span><span class="sxs-lookup"><span data-stu-id="beaf0-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="beaf0-177">Geänderte Abfrage</span><span class="sxs-lookup"><span data-stu-id="beaf0-177">Modified query</span></span>
<span data-ttu-id="beaf0-178">Die folgende Abfrage wurde für die Verwendung in Microsoft 365 Defender angepasst.</span><span class="sxs-lookup"><span data-stu-id="beaf0-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="beaf0-179">Anstatt den Dateinamen direkt aus zu überprüfen, wird der Dateiname in dieser Tabelle bei der Verknüpfung und überprüfung auf `DeviceAlertEvents` `AlertEvidence` den Dateinamen überprüft.</span><span class="sxs-lookup"><span data-stu-id="beaf0-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="beaf0-180">Migrieren von benutzerdefinierten Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="beaf0-180">Migrate custom detection rules</span></span>

<span data-ttu-id="beaf0-181">Wenn Microsoft Defender für Endpunktregeln in Microsoft 365 Defender bearbeitet werden, funktionieren sie weiterhin wie zuvor, wenn die resultierende Abfrage nur gerätetabellen betrachtet.</span><span class="sxs-lookup"><span data-stu-id="beaf0-181">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> <span data-ttu-id="beaf0-182">Beispielsweise werden von benutzerdefinierten Erkennungsregeln generierte Warnungen, die nur Gerätetabellen abfragen, weiterhin an Ihr SIEM übermittelt und E-Mail-Benachrichtigungen generiert, je nachdem, wie Sie diese in Microsoft Defender for Endpoint konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="beaf0-182">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="beaf0-183">Alle vorhandenen Unterdrückungsregeln in Defender for Endpoint gelten weiterhin.</span><span class="sxs-lookup"><span data-stu-id="beaf0-183">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="beaf0-184">Nachdem Sie eine Defender für Endpunktregel so bearbeitet haben, dass sie Identitäts- und E-Mail-Tabellen abfragt, die nur in Microsoft 365 Defender verfügbar sind, wird die Regel automatisch nach Microsoft 365 Defender verschoben.</span><span class="sxs-lookup"><span data-stu-id="beaf0-184">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="beaf0-185">Von der migrierten Regel generierte Warnungen:</span><span class="sxs-lookup"><span data-stu-id="beaf0-185">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="beaf0-186">Sind nicht mehr im Defender for Endpoint-Portal sichtbar (Microsoft Defender Security Center)</span><span class="sxs-lookup"><span data-stu-id="beaf0-186">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="beaf0-187">Beenden Sie die zugestellte SIEM-Nachricht, oder generieren Sie E-Mail-Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="beaf0-187">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="beaf0-188">Um diese Änderung zu umarbeiten, konfigurieren Sie Benachrichtigungen über Microsoft 365 Defender, um die Warnungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="beaf0-188">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="beaf0-189">Sie können die [Microsoft 365 Defender-API](api-incident.md) verwenden, um Benachrichtigungen für Kundenerkennungswarnungen oder verwandte Vorfälle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="beaf0-189">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="beaf0-190">Wird von Microsoft Defender für Endpunktunterdrückungsregeln nicht unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="beaf0-190">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="beaf0-191">Um zu verhindern, dass Warnungen für bestimmte Benutzer, Geräte oder Postfächer generiert werden, ändern Sie die entsprechenden Abfragen, um diese Entitäten explizit auszuschließen.</span><span class="sxs-lookup"><span data-stu-id="beaf0-191">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="beaf0-192">Wenn Sie eine Regel auf diese Weise bearbeiten, werden Sie zur Bestätigung aufgefordert, bevor solche Änderungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="beaf0-192">If you do edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="beaf0-193">Neue Warnungen, die von benutzerdefinierten Erkennungsregeln im Microsoft 365 -Defender-Portal generiert werden, werden auf einer Warnungsseite mit den folgenden Informationen angezeigt:</span><span class="sxs-lookup"><span data-stu-id="beaf0-193">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="beaf0-194">Warnungstitel und -beschreibung</span><span class="sxs-lookup"><span data-stu-id="beaf0-194">Alert title and description</span></span> 
- <span data-ttu-id="beaf0-195">Betroffener Ressourcen</span><span class="sxs-lookup"><span data-stu-id="beaf0-195">Impacted assets</span></span>
- <span data-ttu-id="beaf0-196">Als Reaktion auf die Warnung ergriffene Aktionen</span><span class="sxs-lookup"><span data-stu-id="beaf0-196">Actions taken in response to the alert</span></span>
- <span data-ttu-id="beaf0-197">Abfrageergebnisse, die die Warnung ausgelöst haben</span><span class="sxs-lookup"><span data-stu-id="beaf0-197">Query results that triggered the alert</span></span> 
- <span data-ttu-id="beaf0-198">Informationen zur benutzerdefinierten Erkennungsregel</span><span class="sxs-lookup"><span data-stu-id="beaf0-198">Information on the custom detection rule</span></span> 
 
![Abbildung der neuen Warnungsseite](../../media/newalertpage.png)

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="beaf0-200">Schreiben von Abfragen ohne DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="beaf0-200">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="beaf0-201">Im Microsoft 365 Defender-Schema werden die Warnungen und Tabellen bereitgestellt, um die verschiedenen Informationen zu Warnungen aus verschiedenen `AlertInfo` `AlertEvidence` Quellen zu nutzen.</span><span class="sxs-lookup"><span data-stu-id="beaf0-201">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="beaf0-202">Um die gleichen Warnungsinformationen zu erhalten, die Sie verwendet haben, um aus der Tabelle im Microsoft Defender for Endpoint-Schema zu erhalten, filtern Sie die Tabelle nach, und verbinden Sie dann jede eindeutige ID mit der Tabelle, die detaillierte Ereignis- und Entitätsinformationen `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` enthält.</span><span class="sxs-lookup"><span data-stu-id="beaf0-202">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="beaf0-203">Sehen Sie sich die beispielabfrage unten an:</span><span class="sxs-lookup"><span data-stu-id="beaf0-203">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="beaf0-204">Diese Abfrage liefert viel mehr Spalten als `DeviceAlertEvents` im Microsoft Defender for Endpoint-Schema.</span><span class="sxs-lookup"><span data-stu-id="beaf0-204">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="beaf0-205">Um die Ergebnisse verwaltbar zu halten, verwenden Sie diese, `project` um nur die Spalten zu erhalten, für die Sie sich interessieren.</span><span class="sxs-lookup"><span data-stu-id="beaf0-205">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="beaf0-206">Das folgende Beispiel projektiert Spalten, an denen Sie möglicherweise interessiert sind, wenn die Untersuchung eine PowerShell-Aktivität festgestellt hat:</span><span class="sxs-lookup"><span data-stu-id="beaf0-206">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="beaf0-207">Wenn Sie nach bestimmten Entitäten filtern möchten, die an den Warnungen beteiligt sind, können Sie dazu den Entitätstyp und den Wert angeben, nach dem gefiltert `EntityType` werden soll.</span><span class="sxs-lookup"><span data-stu-id="beaf0-207">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="beaf0-208">Das folgende Beispiel sucht nach einer bestimmten IP-Adresse:</span><span class="sxs-lookup"><span data-stu-id="beaf0-208">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="beaf0-209">Siehe auch</span><span class="sxs-lookup"><span data-stu-id="beaf0-209">See also</span></span>
- [<span data-ttu-id="beaf0-210">Aktivieren von Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="beaf0-210">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="beaf0-211">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="beaf0-211">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="beaf0-212">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="beaf0-212">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="beaf0-213">Erweiterte Suche in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="beaf0-213">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)