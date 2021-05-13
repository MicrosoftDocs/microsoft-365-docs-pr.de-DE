---
title: Migrieren erweiterter Suchabfragen von Microsoft Defender for Endpoint
description: Erfahren Sie, wie Sie Ihre Microsoft Defender for Endpoint-Abfragen so anpassen, dass Sie sie in Microsoft 365 können
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft 365 Defender, microsoft 365, m365, Microsoft Defender for Endpoint, Suche, Abfrage, Telemetrie, benutzerdefinierte Erkennungen, Schema, Kusto, Zuordnung
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
ms.custom: seo-marvel-apr2020
ms.technology: m365d
ms.openlocfilehash: ba6f84f9f08d0635dab6ac65eaa697b8e0e73df7
ms.sourcegitcommit: fb6c5e04ade1e82b26b2f911577b5ac721f1c544
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/13/2021
ms.locfileid: "52470688"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="61ffe-104">Migrieren erweiterter Suchabfragen von Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61ffe-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="61ffe-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="61ffe-105">**Applies to:**</span></span>
- <span data-ttu-id="61ffe-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61ffe-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="61ffe-107">Verschieben Sie Ihre erweiterten Workflows für die Suche von Microsoft Defender for Endpoint, um mit einem umfassenderen Datensatz proaktiv nach Bedrohungen zu fahnen.</span><span class="sxs-lookup"><span data-stu-id="61ffe-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="61ffe-108">In Microsoft 365 Defender erhalten Sie Zugriff auf Daten von anderen Microsoft 365 Sicherheitslösungen, einschließlich:</span><span class="sxs-lookup"><span data-stu-id="61ffe-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="61ffe-109">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="61ffe-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="61ffe-110">Microsoft Defender für Office 365</span><span class="sxs-lookup"><span data-stu-id="61ffe-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="61ffe-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="61ffe-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="61ffe-112">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="61ffe-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="61ffe-113">Die meisten Microsoft Defender for Endpoint-Kunden können [Microsoft 365 Defender ohne zusätzliche Lizenzen verwenden.](prerequisites.md#licensing-requirements)</span><span class="sxs-lookup"><span data-stu-id="61ffe-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="61ffe-114">Um mit dem Übergang Ihrer erweiterten Suche von Defender for Endpoint zu beginnen, aktivieren Sie [Microsoft 365 Defender](m365d-enable.md).</span><span class="sxs-lookup"><span data-stu-id="61ffe-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

<span data-ttu-id="61ffe-115">Sie können ohne Auswirkungen auf ihre vorhandenen Defender for Endpoint-Workflows umwechseln.</span><span class="sxs-lookup"><span data-stu-id="61ffe-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="61ffe-116">Gespeicherte Abfragen bleiben erhalten, und benutzerdefinierte Erkennungsregeln werden weiterhin ausgeführt und Warnungen generiert.</span><span class="sxs-lookup"><span data-stu-id="61ffe-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="61ffe-117">Sie sind jedoch in defender Microsoft 365 sichtbar.</span><span class="sxs-lookup"><span data-stu-id="61ffe-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="61ffe-118">Schematabellen nur in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61ffe-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="61ffe-119">Das [Microsoft 365 defender advanced hunting-Schema](advanced-hunting-schema-tables.md) enthält zusätzliche Tabellen mit Daten aus verschiedenen Microsoft 365 Sicherheitslösungen.</span><span class="sxs-lookup"><span data-stu-id="61ffe-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="61ffe-120">Die folgenden Tabellen sind nur in defender Microsoft 365 verfügbar:</span><span class="sxs-lookup"><span data-stu-id="61ffe-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="61ffe-121">Tabellenname</span><span class="sxs-lookup"><span data-stu-id="61ffe-121">Table name</span></span> | <span data-ttu-id="61ffe-122">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="61ffe-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="61ffe-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="61ffe-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="61ffe-124">Dateien, IP-Adressen, URLs, Benutzer oder Geräte, die Warnungen zugeordnet sind</span><span class="sxs-lookup"><span data-stu-id="61ffe-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="61ffe-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="61ffe-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="61ffe-126">Warnungen von Microsoft Defender for Endpoint, Microsoft Defender für Office 365, Microsoft Cloud App Security und Microsoft Defender for Identity, einschließlich Schweregradinformationen und Bedrohungskategorien</span><span class="sxs-lookup"><span data-stu-id="61ffe-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="61ffe-127">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="61ffe-127">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="61ffe-128">Informationen zu Dateien, die an E-Mails angefügt sind</span><span class="sxs-lookup"><span data-stu-id="61ffe-128">Information about files attached to emails</span></span> |
| [<span data-ttu-id="61ffe-129">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="61ffe-129">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="61ffe-130">Microsoft 365 E-Mail-Ereignisse, einschließlich E-Mail-Zustellung und Blockieren von Ereignissen</span><span class="sxs-lookup"><span data-stu-id="61ffe-130">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="61ffe-131">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="61ffe-131">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="61ffe-132">Sicherheitsereignisse, die nach der Zustellung auftreten, nachdem Microsoft 365 E-Mails an das Empfängerpostfach zugestellt haben</span><span class="sxs-lookup"><span data-stu-id="61ffe-132">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="61ffe-133">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="61ffe-133">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="61ffe-134">Informationen zu URLs in E-Mails</span><span class="sxs-lookup"><span data-stu-id="61ffe-134">Information about URLs on emails</span></span> |
| [<span data-ttu-id="61ffe-135">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="61ffe-135">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="61ffe-136">Ereignisse mit einem lokalen Domänencontroller, auf dem Active Directory (AD) ausgeführt wird.</span><span class="sxs-lookup"><span data-stu-id="61ffe-136">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="61ffe-137">Diese Tabelle enthält eine Reihe von identitätsbezogenen Ereignissen und Systemereignissen auf dem Domänencontroller.</span><span class="sxs-lookup"><span data-stu-id="61ffe-137">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="61ffe-138">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="61ffe-138">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="61ffe-139">Kontoinformationen aus verschiedenen Quellen, einschließlich Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="61ffe-139">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="61ffe-140">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="61ffe-140">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="61ffe-141">Authentifizierungsereignisse in Active Directory und Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="61ffe-141">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="61ffe-142">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="61ffe-142">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="61ffe-143">Abfragen für Active Directory-Objekte, z. B. Benutzer, Gruppen, Geräte und Domänen</span><span class="sxs-lookup"><span data-stu-id="61ffe-143">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

>[!IMPORTANT]
> <span data-ttu-id="61ffe-144">Abfragen und benutzerdefinierte Erkennungen, die Schematabellen verwenden, die nur in Microsoft 365 Defender verfügbar sind, können nur in defender Microsoft 365 werden.</span><span class="sxs-lookup"><span data-stu-id="61ffe-144">Queries and custom detections which use schema tables that are only available in Microsoft 365 Defender can only be viewed in Microsoft 365 Defender.</span></span>

## <a name="map-devicealertevents-table"></a><span data-ttu-id="61ffe-145">DeviceAlertEvents-Tabelle zuordnung</span><span class="sxs-lookup"><span data-stu-id="61ffe-145">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="61ffe-146">Die `AlertInfo` Tabellen und ersetzen die Tabelle im Microsoft Defender for `AlertEvidence` `DeviceAlertEvents` Endpoint-Schema.</span><span class="sxs-lookup"><span data-stu-id="61ffe-146">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="61ffe-147">Neben Daten zu Gerätewarnungen enthalten diese beiden Tabellen Daten zu Warnungen für Identitäten, Apps und E-Mails.</span><span class="sxs-lookup"><span data-stu-id="61ffe-147">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="61ffe-148">Verwenden Sie die folgende Tabelle, um zu überprüfen, `DeviceAlertEvents` wie Spalten Spalten in und Tabellen `AlertInfo` `AlertEvidence` zuordnungen.</span><span class="sxs-lookup"><span data-stu-id="61ffe-148">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="61ffe-149">Zusätzlich zu den Spalten in der folgenden Tabelle enthält die Tabelle viele weitere Spalten, die ein ganzheitliches Bild von Warnungen aus `AlertEvidence` verschiedenen Quellen bieten.</span><span class="sxs-lookup"><span data-stu-id="61ffe-149">In addition to the columns in the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="61ffe-150">Alle AlertEvidence-Spalten anzeigen</span><span class="sxs-lookup"><span data-stu-id="61ffe-150">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="61ffe-151">Spalte DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="61ffe-151">DeviceAlertEvents column</span></span> | <span data-ttu-id="61ffe-152">Wo finden Sie dieselben Daten in Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="61ffe-152">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="61ffe-153">`AlertInfo` und  `AlertEvidence` Tabellen</span><span class="sxs-lookup"><span data-stu-id="61ffe-153">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="61ffe-154">`AlertInfo` und  `AlertEvidence` Tabellen</span><span class="sxs-lookup"><span data-stu-id="61ffe-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="61ffe-155">`AlertEvidence` Tabelle</span><span class="sxs-lookup"><span data-stu-id="61ffe-155">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="61ffe-156">`AlertEvidence` Tabelle</span><span class="sxs-lookup"><span data-stu-id="61ffe-156">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="61ffe-157">`AlertInfo` Tabelle</span><span class="sxs-lookup"><span data-stu-id="61ffe-157">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="61ffe-158">`AlertInfo` Tabelle</span><span class="sxs-lookup"><span data-stu-id="61ffe-158">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="61ffe-159">`AlertInfo` Tabelle</span><span class="sxs-lookup"><span data-stu-id="61ffe-159">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="61ffe-160">`AlertEvidence` Tabelle</span><span class="sxs-lookup"><span data-stu-id="61ffe-160">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="61ffe-161">`AlertEvidence` Tabelle</span><span class="sxs-lookup"><span data-stu-id="61ffe-161">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="61ffe-162">`AlertEvidence` Tabelle</span><span class="sxs-lookup"><span data-stu-id="61ffe-162">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="61ffe-163">`AlertEvidence` Tabelle</span><span class="sxs-lookup"><span data-stu-id="61ffe-163">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="61ffe-164">`AlertInfo` Tabelle</span><span class="sxs-lookup"><span data-stu-id="61ffe-164">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="61ffe-165">Diese Spalte wird in der Regel in Microsoft Defender for Endpoint verwendet, um verwandte Datensätze in anderen Tabellen zu finden.</span><span class="sxs-lookup"><span data-stu-id="61ffe-165">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="61ffe-166">In Microsoft 365 Defender können Sie verwandte Daten direkt aus der Tabelle `AlertEvidence` erhalten.</span><span class="sxs-lookup"><span data-stu-id="61ffe-166">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="61ffe-167">Diese Spalte wird in der Regel in Microsoft Defender for Endpoint für zusätzliche Ereignisinformationen in anderen Tabellen verwendet.</span><span class="sxs-lookup"><span data-stu-id="61ffe-167">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="61ffe-168">In Microsoft 365 Defender können Sie verwandte Daten direkt aus der Tabelle `AlertEvidence` erhalten.</span><span class="sxs-lookup"><span data-stu-id="61ffe-168">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="61ffe-169">Anpassen vorhandener Microsoft Defender for Endpoint-Abfragen</span><span class="sxs-lookup"><span data-stu-id="61ffe-169">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="61ffe-170">Microsoft Defender for Endpoint-Abfragen funktionieren wie folgt, es sei denn, sie verweisen auf die `DeviceAlertEvents` Tabelle.</span><span class="sxs-lookup"><span data-stu-id="61ffe-170">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="61ffe-171">Um diese Abfragen in Microsoft 365 verwenden zu können, wenden Sie die folgenden Änderungen an:</span><span class="sxs-lookup"><span data-stu-id="61ffe-171">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="61ffe-172">Ersetzen `DeviceAlertEvents` Sie durch `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="61ffe-172">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="61ffe-173">Schließen Sie sich `AlertInfo` der Tabelle und den Tabellen an `AlertEvidence` `AlertId` an, um gleichwertige Daten zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="61ffe-173">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="61ffe-174">Ursprüngliche Abfrage</span><span class="sxs-lookup"><span data-stu-id="61ffe-174">Original query</span></span>
<span data-ttu-id="61ffe-175">Die folgende Abfrage wird `DeviceAlertEvents` in Microsoft Defender for __ Endpoint verwendet, um die Warnungen zu erhalten, diepowershell.exe:</span><span class="sxs-lookup"><span data-stu-id="61ffe-175">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="61ffe-176">Geänderte Abfrage</span><span class="sxs-lookup"><span data-stu-id="61ffe-176">Modified query</span></span>
<span data-ttu-id="61ffe-177">Die folgende Abfrage wurde für die Verwendung in defender Microsoft 365 angepasst.</span><span class="sxs-lookup"><span data-stu-id="61ffe-177">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="61ffe-178">Anstatt den Dateinamen direkt aus zu überprüfen, wird der Dateiname in dieser Tabelle bei- und `DeviceAlertEvents` `AlertEvidence` überprüft.</span><span class="sxs-lookup"><span data-stu-id="61ffe-178">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="migrate-custom-detection-rules"></a><span data-ttu-id="61ffe-179">Migrieren von benutzerdefinierten Erkennungsregeln</span><span class="sxs-lookup"><span data-stu-id="61ffe-179">Migrate custom detection rules</span></span>

<span data-ttu-id="61ffe-180">Wenn Microsoft Defender for Endpoint-Regeln auf Microsoft 365 Defender bearbeitet werden, funktionieren sie weiterhin wie zuvor, wenn die resultierende Abfrage nur Gerätetabellen betrachtet.</span><span class="sxs-lookup"><span data-stu-id="61ffe-180">When Microsoft Defender for Endpoint rules are edited on Microsoft 365 Defender, they continue to function as before if the resulting query looks at device tables only.</span></span> 

<span data-ttu-id="61ffe-181">Beispielsweise werden Warnungen, die von benutzerdefinierten Erkennungsregeln generiert werden, die nur Gerätetabellen abfragen, weiterhin an Ihr SIEM übermittelt und E-Mail-Benachrichtigungen generiert, je nachdem, wie Sie diese in Microsoft Defender for Endpoint konfiguriert haben.</span><span class="sxs-lookup"><span data-stu-id="61ffe-181">For example, alerts generated by custom detection rules that query only device tables will continue to be delivered to your SIEM and generate email notifications, depending on how you’ve configured these in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="61ffe-182">Alle vorhandenen Unterdrückungsregeln in Defender for Endpoint gelten weiterhin.</span><span class="sxs-lookup"><span data-stu-id="61ffe-182">Any existing suppression rules in Defender for Endpoint will also continue to apply.</span></span>

<span data-ttu-id="61ffe-183">Nachdem Sie eine Defender for Endpoint-Regel so bearbeitet haben, dass sie Identitäts- und E-Mail-Tabellen abfragt, die nur in Microsoft 365 Defender verfügbar sind, wird die Regel automatisch zu Microsoft 365 Defender verschoben.</span><span class="sxs-lookup"><span data-stu-id="61ffe-183">Once you edit a Defender for Endpoint rule so that it queries identity and email tables, which are only available in Microsoft 365 Defender, the rule is automatically moved to Microsoft 365 Defender.</span></span> 

<span data-ttu-id="61ffe-184">Von der migrierten Regel generierte Warnungen:</span><span class="sxs-lookup"><span data-stu-id="61ffe-184">Alerts generated by the migrated rule:</span></span>

- <span data-ttu-id="61ffe-185">Sind nicht mehr im Defender for Endpoint-Portal (Microsoft Defender Security Center)</span><span class="sxs-lookup"><span data-stu-id="61ffe-185">Are no longer visible in the Defender for Endpoint portal (Microsoft Defender Security Center)</span></span>
- <span data-ttu-id="61ffe-186">Beenden Sie die Zugestelltung an Ihr SIEM oder generieren Sie E-Mail-Benachrichtigungen.</span><span class="sxs-lookup"><span data-stu-id="61ffe-186">Stop being delivered to your SIEM or generate email notifications.</span></span> <span data-ttu-id="61ffe-187">Um diese Änderung zu ändern, konfigurieren Sie Benachrichtigungen über Microsoft 365 Defender, um die Warnungen zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="61ffe-187">To work around this change, configure notifications through Microsoft 365 Defender to get the alerts.</span></span> <span data-ttu-id="61ffe-188">Sie können die Microsoft 365 [Defender-API](api-incident.md) verwenden, um Benachrichtigungen für Kundenerkennungswarnungen oder damit zusammenhängende Vorfälle zu erhalten.</span><span class="sxs-lookup"><span data-stu-id="61ffe-188">You can use the [Microsoft 365 Defender API](api-incident.md) to receive notifications for customer detection alerts or related incidents.</span></span>
- <span data-ttu-id="61ffe-189">Wird nicht von Microsoft Defender for Endpoint-Unterdrückungsregeln unterdrückt.</span><span class="sxs-lookup"><span data-stu-id="61ffe-189">Won't be suppressed by Microsoft Defender for Endpoint suppression rules.</span></span> <span data-ttu-id="61ffe-190">Um zu verhindern, dass Warnungen für bestimmte Benutzer, Geräte oder Postfächer generiert werden, ändern Sie die entsprechenden Abfragen so, dass diese Entitäten explizit ausgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="61ffe-190">To prevent alerts from being generated for certain users, devices, or mailboxes, modify the corresponding queries to exclude those entities explicitly.</span></span>

<span data-ttu-id="61ffe-191">Wenn Sie eine Regel auf diese Weise bearbeiten, werden Sie zur Bestätigung aufgefordert, bevor diese Änderungen angewendet werden.</span><span class="sxs-lookup"><span data-stu-id="61ffe-191">If you edit a rule this way, you will be prompted for confirmation before such changes are applied.</span></span>

<span data-ttu-id="61ffe-192">Neue Warnungen, die von benutzerdefinierten Erkennungsregeln im Microsoft 365 werden auf einer Warnungsseite angezeigt, die die folgenden Informationen enthält:</span><span class="sxs-lookup"><span data-stu-id="61ffe-192">New alerts generated by custom detection rules in Microsoft 365 Defender portal are displayed in an alert page that provides the following information:</span></span>

- <span data-ttu-id="61ffe-193">Titel und Beschreibung der Warnung</span><span class="sxs-lookup"><span data-stu-id="61ffe-193">Alert title and description</span></span> 
- <span data-ttu-id="61ffe-194">Auswirkungen auf Ressourcen</span><span class="sxs-lookup"><span data-stu-id="61ffe-194">Impacted assets</span></span>
- <span data-ttu-id="61ffe-195">Aktionen, die als Reaktion auf die Warnung ergriffen wurden</span><span class="sxs-lookup"><span data-stu-id="61ffe-195">Actions taken in response to the alert</span></span>
- <span data-ttu-id="61ffe-196">Abfrageergebnisse, die die Warnung ausgelöst haben</span><span class="sxs-lookup"><span data-stu-id="61ffe-196">Query results that triggered the alert</span></span> 
- <span data-ttu-id="61ffe-197">Informationen zur benutzerdefinierten Erkennungsregel</span><span class="sxs-lookup"><span data-stu-id="61ffe-197">Information on the custom detection rule</span></span> 
 
> [!div class="mx-imgBorder"]
> <span data-ttu-id="61ffe-198">![Abbildung der neuen Warnungsseite](../../media/new-alert-page.png)</span><span class="sxs-lookup"><span data-stu-id="61ffe-198">![Image of new alert page](../../media/new-alert-page.png)</span></span>

## <a name="write-queries-without-devicealertevents"></a><span data-ttu-id="61ffe-199">Schreiben von Abfragen ohne DeviceAlertEvents</span><span class="sxs-lookup"><span data-stu-id="61ffe-199">Write queries without DeviceAlertEvents</span></span>

<span data-ttu-id="61ffe-200">Im Microsoft 365 Defender-Schema werden die Tabellen und bereitgestellt, um die verschiedenen Informationen zu verwenden, die Warnungen aus verschiedenen `AlertInfo` `AlertEvidence` Quellen begleiten.</span><span class="sxs-lookup"><span data-stu-id="61ffe-200">In the Microsoft 365 Defender schema, the `AlertInfo` and `AlertEvidence` tables are provided to accommodate the diverse set of information that accompany alerts from various sources.</span></span> 

<span data-ttu-id="61ffe-201">Um die gleichen Warnungsinformationen zu erhalten, die Sie aus der Tabelle im Microsoft Defender for Endpoint-Schema erhalten haben, filtern Sie die Tabelle nach, und schließen Sie dann jede eindeutige ID mit der Tabelle an, die detaillierte Ereignis- und Entitätsinformationen `DeviceAlertEvents` `AlertInfo` `ServiceSource` `AlertEvidence` enthält.</span><span class="sxs-lookup"><span data-stu-id="61ffe-201">To get the same alert information that you used to get from the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema, filter the `AlertInfo` table by `ServiceSource` and then join each unique ID with the `AlertEvidence` table, which provides detailed event and entity information.</span></span> 

<span data-ttu-id="61ffe-202">Sehen Sie sich die folgende Beispielabfrage an:</span><span class="sxs-lookup"><span data-stu-id="61ffe-202">See the sample query below:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
| join AlertEvidence on AlertId
```

<span data-ttu-id="61ffe-203">Diese Abfrage liefert viel mehr Spalten als `DeviceAlertEvents` im Microsoft Defender for Endpoint-Schema.</span><span class="sxs-lookup"><span data-stu-id="61ffe-203">This query yields many more columns than `DeviceAlertEvents` in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="61ffe-204">Um die Ergebnisse verwaltbar zu halten, verwenden Sie, um nur die Spalten zu `project` erhalten, die Sie interessieren.</span><span class="sxs-lookup"><span data-stu-id="61ffe-204">To keep results manageable, use `project` to get only the columns you are interested in.</span></span> <span data-ttu-id="61ffe-205">Das folgende Beispiel projektiert Spalten, an denen Sie möglicherweise interessiert sind, wenn die Untersuchung die PowerShell-Aktivität erkannt hat:</span><span class="sxs-lookup"><span data-stu-id="61ffe-205">The example below projects columns you might be interested in when the investigation detected PowerShell activity:</span></span>

```kusto
AlertInfo
| where Timestamp > ago(7d)
| where ServiceSource == "Microsoft Defender for Endpoint"
    and AttackTechniques has "powershell"
| join AlertEvidence on AlertId
| project Timestamp, Title, AlertId, DeviceName, FileName, ProcessCommandLine 
```

<span data-ttu-id="61ffe-206">Wenn Sie nach bestimmten Entitäten filtern möchten, die an den Warnungen beteiligt sind, können Sie dazu den Entitätstyp und den Wert angeben, nach dem Sie `EntityType` filtern möchten.</span><span class="sxs-lookup"><span data-stu-id="61ffe-206">If you'd like to filter for specific entities involved in the alerts, you can do so by specifying the entity type in `EntityType` and the value you would like to filter for.</span></span> <span data-ttu-id="61ffe-207">Im folgenden Beispiel wird nach einer bestimmten IP-Adresse sucht:</span><span class="sxs-lookup"><span data-stu-id="61ffe-207">The following example looks for a specific IP address:</span></span>

```kusto
AlertInfo
| where Title == "Insert_your_alert_title"
| join AlertEvidence on AlertId 
| where EntityType == "Ip" and RemoteIP == "192.88.99.01" 
```

## <a name="see-also"></a><span data-ttu-id="61ffe-208">Weitere Artikel</span><span class="sxs-lookup"><span data-stu-id="61ffe-208">See also</span></span>
- [<span data-ttu-id="61ffe-209">Microsoft 365 Defender aktivieren</span><span class="sxs-lookup"><span data-stu-id="61ffe-209">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="61ffe-210">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="61ffe-210">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="61ffe-211">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="61ffe-211">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="61ffe-212">Erweiterte Suche in Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="61ffe-212">Advanced hunting in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)