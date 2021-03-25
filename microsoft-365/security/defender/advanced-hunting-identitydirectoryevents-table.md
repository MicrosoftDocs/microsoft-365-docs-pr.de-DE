---
title: IdentityDirectoryEvents-Tabelle im schema der erweiterten Suche
description: Weitere Informationen zu Domänencontroller- und Active Directory-Ereignissen finden Sie in der IdentityDirectoryEvents-Tabelle des schemas für die erweiterte Suche.
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungensuche, Microsoft Threat Protection, microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, IdentityDirectoryEvents, Domänencontroller, Active Directory, Azure ATP, Identitäten
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
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ba63bdeb215c24e68d0e507d99e026c5b2695cb0
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51068327"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="adf6c-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="adf6c-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="adf6c-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="adf6c-105">**Applies to:**</span></span>
- <span data-ttu-id="adf6c-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="adf6c-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="adf6c-107">Die Tabelle im Schema der erweiterten Suche enthält Ereignisse, die einen lokalen Domänencontroller mit `IdentityDirectoryEvents` Active Directory [](advanced-hunting-overview.md) (AD) enthalten.</span><span class="sxs-lookup"><span data-stu-id="adf6c-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="adf6c-108">Diese Tabelle erfasst verschiedene identitätsbezogene Ereignisse, z. B. Kennwortänderungen, Kennwortablauf und Benutzerprinzipalnamen(UPN) Änderungen.</span><span class="sxs-lookup"><span data-stu-id="adf6c-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="adf6c-109">Außerdem werden Systemereignisse auf dem Domänencontroller erfasst, z. B. das Planen von Aufgaben und die PowerShell-Aktivität.</span><span class="sxs-lookup"><span data-stu-id="adf6c-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="adf6c-110">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="adf6c-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="adf6c-111">Ausführliche Informationen zu den von einer Tabelle unterstützten Ereignistypen ( Werte) finden Sie unter Verwendung der integrierten Schemareferenz, die `ActionType` im Security Center verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="adf6c-111">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="adf6c-112">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="adf6c-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="adf6c-113">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="adf6c-113">Column name</span></span> | <span data-ttu-id="adf6c-114">Datentyp</span><span class="sxs-lookup"><span data-stu-id="adf6c-114">Data type</span></span> | <span data-ttu-id="adf6c-115">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="adf6c-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="adf6c-116">datetime</span><span class="sxs-lookup"><span data-stu-id="adf6c-116">datetime</span></span> | <span data-ttu-id="adf6c-117">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="adf6c-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="adf6c-118">string</span><span class="sxs-lookup"><span data-stu-id="adf6c-118">string</span></span> | <span data-ttu-id="adf6c-119">Typ der Aktivität, die das Ereignis ausgelöst hat.</span><span class="sxs-lookup"><span data-stu-id="adf6c-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="adf6c-120">Weitere Informationen [finden Sie in der In-Portal-Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="adf6c-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="adf6c-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-121">string</span></span> | <span data-ttu-id="adf6c-122">Anwendung, die die aufgezeichnete Aktion ausgeführt hat</span><span class="sxs-lookup"><span data-stu-id="adf6c-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="adf6c-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-123">string</span></span> | <span data-ttu-id="adf6c-124">Benutzerprinzipalname (UPN) des Kontos, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="adf6c-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="adf6c-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-125">string</span></span> | <span data-ttu-id="adf6c-126">Anzeigename des Kontos, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="adf6c-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="adf6c-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-127">string</span></span> | <span data-ttu-id="adf6c-128">Vollqualifizierter Domänenname (FQDN) des Geräts, auf das die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="adf6c-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="adf6c-129">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-129">string</span></span> | <span data-ttu-id="adf6c-130">Name des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="adf6c-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="adf6c-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-131">string</span></span> | <span data-ttu-id="adf6c-132">IP-Adresse des Geräts, auf dem die Serveranwendung ausgeführt wird, die die aufgezeichnete Aktion verarbeitet hat</span><span class="sxs-lookup"><span data-stu-id="adf6c-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="adf6c-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-133">string</span></span> | <span data-ttu-id="adf6c-134">Zielport der Aktivität</span><span class="sxs-lookup"><span data-stu-id="adf6c-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="adf6c-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-135">string</span></span> | <span data-ttu-id="adf6c-136">Während der Kommunikation verwendetes Protokoll</span><span class="sxs-lookup"><span data-stu-id="adf6c-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="adf6c-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-137">string</span></span> | <span data-ttu-id="adf6c-138">Benutzername des Kontos</span><span class="sxs-lookup"><span data-stu-id="adf6c-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="adf6c-139">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-139">string</span></span> | <span data-ttu-id="adf6c-140">Domäne des Kontos</span><span class="sxs-lookup"><span data-stu-id="adf6c-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="adf6c-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-141">string</span></span> | <span data-ttu-id="adf6c-142">Benutzerprinzipalname (UPN) des Kontos</span><span class="sxs-lookup"><span data-stu-id="adf6c-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="adf6c-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-143">string</span></span> | <span data-ttu-id="adf6c-144">Security Identifier (SID) des Kontos</span><span class="sxs-lookup"><span data-stu-id="adf6c-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="adf6c-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-145">string</span></span> | <span data-ttu-id="adf6c-146">Eindeutige ID für das Konto in Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="adf6c-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="adf6c-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-147">string</span></span> | <span data-ttu-id="adf6c-148">Name des Kontobenutzers, der im Adressbuch angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="adf6c-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="adf6c-149">In der Regel eine Kombination aus einem angegebenen oder Vornamen, einer mittleren Initiierung und einem Nachnamen oder Nachnamen.</span><span class="sxs-lookup"><span data-stu-id="adf6c-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="adf6c-150">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-150">string</span></span> | <span data-ttu-id="adf6c-151">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="adf6c-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="adf6c-152">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-152">string</span></span> | <span data-ttu-id="adf6c-153">Dem Gerät während der Kommunikation zugewiesene IP-Adresse</span><span class="sxs-lookup"><span data-stu-id="adf6c-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="adf6c-154">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-154">string</span></span> | <span data-ttu-id="adf6c-155">WÄHREND der Kommunikation verwendeter TCP-Port</span><span class="sxs-lookup"><span data-stu-id="adf6c-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="adf6c-156">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-156">string</span></span> | <span data-ttu-id="adf6c-157">Stadt, Land oder anderer geografischer Standort, der dem Ereignis zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="adf6c-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="adf6c-158">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-158">string</span></span> | <span data-ttu-id="adf6c-159">Internetdienstanbieter, der der IP-Adresse zugeordnet ist</span><span class="sxs-lookup"><span data-stu-id="adf6c-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="adf6c-160">long</span><span class="sxs-lookup"><span data-stu-id="adf6c-160">long</span></span> | <span data-ttu-id="adf6c-161">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="adf6c-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="adf6c-162">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="adf6c-162">string</span></span> | <span data-ttu-id="adf6c-163">Zusätzliche Informationen zur Entität oder zum Ereignis</span><span class="sxs-lookup"><span data-stu-id="adf6c-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="adf6c-164">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="adf6c-164">Related topics</span></span>
- [<span data-ttu-id="adf6c-165">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="adf6c-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="adf6c-166">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="adf6c-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="adf6c-167">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="adf6c-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="adf6c-168">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="adf6c-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="adf6c-169">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="adf6c-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="adf6c-170">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="adf6c-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
