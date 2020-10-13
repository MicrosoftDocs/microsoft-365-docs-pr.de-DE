---
title: IdentityDirectoryEvents-Tabelle im Advanced Hunting-Schema
description: Informationen zu Domänencontroller-und Active Directory Ereignissen in der IdentityDirectoryEvents-Tabelle des Advanced Hunting-Schemas
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, IdentityDirectoryEvents, Domänencontroller, Active Directory, Azure ATP, Identitäten
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
ms.openlocfilehash: d93ef3eb3bbf6def0f633aa0f69032e37d10c4c9
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430376"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="d30dd-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="d30dd-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d30dd-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="d30dd-105">**Applies to:**</span></span>
- <span data-ttu-id="d30dd-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="d30dd-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="d30dd-107">Die `IdentityDirectoryEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Ereignisse, die einen lokalen Domänencontroller mit Active Directory (AD) umfassen.</span><span class="sxs-lookup"><span data-stu-id="d30dd-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="d30dd-108">In dieser Tabelle werden verschiedene identitätsbezogene Ereignisse erfasst, wie Kennwortänderungen, Kennwortablauf und Benutzerprinzipalnamen (User Principal Name, UPN) geändert.</span><span class="sxs-lookup"><span data-stu-id="d30dd-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="d30dd-109">Außerdem werden Systemereignisse auf dem Domänencontroller erfasst, wie die Planung von Aufgaben und die PowerShell-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="d30dd-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="d30dd-110">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="d30dd-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="d30dd-111">Ausführliche Informationen zu den `ActionType` von einer Tabelle unterstützten Ereignistypen (Values) finden Sie in der [integrierten Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) , die im Sicherheitscenter verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="d30dd-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="d30dd-112">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="d30dd-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="d30dd-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="d30dd-113">Column name</span></span> | <span data-ttu-id="d30dd-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="d30dd-114">Data type</span></span> | <span data-ttu-id="d30dd-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="d30dd-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="d30dd-116">datetime</span><span class="sxs-lookup"><span data-stu-id="d30dd-116">datetime</span></span> | <span data-ttu-id="d30dd-117">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="d30dd-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="d30dd-118">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-118">string</span></span> | <span data-ttu-id="d30dd-119">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="d30dd-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="d30dd-120">Details finden Sie [in der in-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) .</span><span class="sxs-lookup"><span data-stu-id="d30dd-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="d30dd-121">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-121">string</span></span> | <span data-ttu-id="d30dd-122">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="d30dd-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="d30dd-123">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-123">string</span></span> | <span data-ttu-id="d30dd-124">Benutzerprinzipalname (User Principal Name, UPN) des Kontos, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="d30dd-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="d30dd-125">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-125">string</span></span> | <span data-ttu-id="d30dd-126">Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="d30dd-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="d30dd-127">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-127">string</span></span> | <span data-ttu-id="d30dd-128">Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="d30dd-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="d30dd-129">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-129">string</span></span> | <span data-ttu-id="d30dd-130">Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="d30dd-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="d30dd-131">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-131">string</span></span> | <span data-ttu-id="d30dd-132">IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="d30dd-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="d30dd-133">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-133">string</span></span> | <span data-ttu-id="d30dd-134">Ziel Port der Aktivität</span><span class="sxs-lookup"><span data-stu-id="d30dd-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="d30dd-135">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-135">string</span></span> | <span data-ttu-id="d30dd-136">Während der Kommunikation verwendete Protokolle</span><span class="sxs-lookup"><span data-stu-id="d30dd-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="d30dd-137">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-137">string</span></span> | <span data-ttu-id="d30dd-138">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="d30dd-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="d30dd-139">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-139">string</span></span> | <span data-ttu-id="d30dd-140">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="d30dd-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="d30dd-141">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-141">string</span></span> | <span data-ttu-id="d30dd-142">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="d30dd-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="d30dd-143">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-143">string</span></span> | <span data-ttu-id="d30dd-144">Sicherheits-ID (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="d30dd-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="d30dd-145">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-145">string</span></span> | <span data-ttu-id="d30dd-146">Eindeutiger Bezeichner für das Konto in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d30dd-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="d30dd-147">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-147">string</span></span> | <span data-ttu-id="d30dd-148">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="d30dd-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="d30dd-149">Normalerweise eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiation und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="d30dd-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="d30dd-150">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-150">string</span></span> | <span data-ttu-id="d30dd-151">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="d30dd-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="d30dd-152">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-152">string</span></span> | <span data-ttu-id="d30dd-153">Dem Gerät während der Kommunikation zugewiesene IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="d30dd-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="d30dd-154">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-154">string</span></span> | <span data-ttu-id="d30dd-155">Während der Kommunikation verwendeter TCP-Port</span><span class="sxs-lookup"><span data-stu-id="d30dd-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="d30dd-156">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-156">string</span></span> | <span data-ttu-id="d30dd-157">Ort, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="d30dd-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="d30dd-158">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-158">string</span></span> | <span data-ttu-id="d30dd-159">Internet Dienstanbieter, der der IP-Adresse zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="d30dd-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="d30dd-160">long</span><span class="sxs-lookup"><span data-stu-id="d30dd-160">long</span></span> | <span data-ttu-id="d30dd-161">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="d30dd-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="d30dd-162">string</span><span class="sxs-lookup"><span data-stu-id="d30dd-162">string</span></span> | <span data-ttu-id="d30dd-163">Zusätzliche Informationen zur Entität oder zum Ereignis</span><span class="sxs-lookup"><span data-stu-id="d30dd-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="d30dd-164">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="d30dd-164">Related topics</span></span>
- [<span data-ttu-id="d30dd-165">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="d30dd-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="d30dd-166">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="d30dd-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="d30dd-167">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="d30dd-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="d30dd-168">Suchen auf Geräten, in E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="d30dd-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="d30dd-169">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="d30dd-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="d30dd-170">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="d30dd-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
