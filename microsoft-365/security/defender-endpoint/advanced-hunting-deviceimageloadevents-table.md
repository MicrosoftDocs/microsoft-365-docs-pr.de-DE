---
title: DeviceImageLoadEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu DLL-Ladeereignissen in der DeviceImageLoadEvents-Tabelle des schemas für die erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, search, query, telemetry, schema reference, kusto, table, column, data type, description, deviceimageloadevents, DLL loading, library, file image, ImageLoadEvents
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: aad270a101e7052e04e4530e661e0e86c2db70d2
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51067071"
---
# <a name="deviceimageloadevents"></a><span data-ttu-id="9575a-104">DeviceImageLoadEvents</span><span class="sxs-lookup"><span data-stu-id="9575a-104">DeviceImageLoadEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="9575a-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9575a-105">**Applies to:**</span></span>
- [<span data-ttu-id="9575a-106">Microsoft Defender für Endpunkt</span><span class="sxs-lookup"><span data-stu-id="9575a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


><span data-ttu-id="9575a-107">Möchten Sie Defender for Endpoint erleben?</span><span class="sxs-lookup"><span data-stu-id="9575a-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="9575a-108">Registrieren Sie sich für eine kostenlose Testversion.</span><span class="sxs-lookup"><span data-stu-id="9575a-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-advancedhuntingref-abovefoldlink)

<span data-ttu-id="9575a-109">Die `DeviceImageLoadEvents` Tabelle im Schema der erweiterten [Suche](advanced-hunting-overview.md) enthält Informationen zu DLL-Ladeereignissen.</span><span class="sxs-lookup"><span data-stu-id="9575a-109">The `DeviceImageLoadEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about DLL loading events.</span></span> <span data-ttu-id="9575a-110">Verwenden Sie diese Referenz, um Abfragen zu erstellen, die Informationen aus der Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="9575a-110">Use this reference to construct queries that return information from the table.</span></span>

<span data-ttu-id="9575a-111">Weitere Informationen zu anderen Tabellen im Schema für die erweiterte Suche finden Sie in der [Schemareferenz](advanced-hunting-schema-reference.md)für erweiterte Suche .</span><span class="sxs-lookup"><span data-stu-id="9575a-111">For information on other tables in the advanced hunting schema, see [the advanced hunting schema reference](advanced-hunting-schema-reference.md).</span></span>

| <span data-ttu-id="9575a-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="9575a-112">Column name</span></span> | <span data-ttu-id="9575a-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9575a-113">Data type</span></span> | <span data-ttu-id="9575a-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9575a-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9575a-115">datetime</span><span class="sxs-lookup"><span data-stu-id="9575a-115">datetime</span></span> | <span data-ttu-id="9575a-116">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9575a-116">Date and time when the event was recorded</span></span> |
| `DeviceId` | <span data-ttu-id="9575a-117">string</span><span class="sxs-lookup"><span data-stu-id="9575a-117">string</span></span> | <span data-ttu-id="9575a-118">Eindeutige ID für das Gerät im Dienst</span><span class="sxs-lookup"><span data-stu-id="9575a-118">Unique identifier for the device in the service</span></span> |
| `DeviceName` | <span data-ttu-id="9575a-119">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-119">string</span></span> | <span data-ttu-id="9575a-120">Vollqualifizierter Domänenname (FQDN) des Geräts</span><span class="sxs-lookup"><span data-stu-id="9575a-120">Fully qualified domain name (FQDN) of the device</span></span> |
| `ActionType` | <span data-ttu-id="9575a-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-121">string</span></span> | <span data-ttu-id="9575a-122">Typ der Aktivität, die das Ereignis ausgelöst hat</span><span class="sxs-lookup"><span data-stu-id="9575a-122">Type of activity that triggered the event</span></span> |
| `FileName` | <span data-ttu-id="9575a-123">string</span><span class="sxs-lookup"><span data-stu-id="9575a-123">string</span></span> | <span data-ttu-id="9575a-124">Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="9575a-124">Name of the file that the recorded action was applied to</span></span> |
| `FolderPath` | <span data-ttu-id="9575a-125">string</span><span class="sxs-lookup"><span data-stu-id="9575a-125">string</span></span> | <span data-ttu-id="9575a-126">Ordner, der die Datei enthält, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="9575a-126">Folder containing the file that the recorded action was applied to</span></span> |
| `SHA1` | <span data-ttu-id="9575a-127">string</span><span class="sxs-lookup"><span data-stu-id="9575a-127">string</span></span> | <span data-ttu-id="9575a-128">SHA-1 der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="9575a-128">SHA-1 of the file that the recorded action was applied to</span></span> |
| `MD5` | <span data-ttu-id="9575a-129">string</span><span class="sxs-lookup"><span data-stu-id="9575a-129">string</span></span> | <span data-ttu-id="9575a-130">MD5-Hash der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="9575a-130">MD5 hash of the file that the recorded action was applied to</span></span> |
| `InitiatingProcessAccountDomain` | <span data-ttu-id="9575a-131">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-131">string</span></span> | <span data-ttu-id="9575a-132">Domäne des Kontos, mit dem der Prozess für das Ereignis verantwortlich war</span><span class="sxs-lookup"><span data-stu-id="9575a-132">Domain of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountName` | <span data-ttu-id="9575a-133">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-133">string</span></span> | <span data-ttu-id="9575a-134">Benutzername des Kontos, das den prozess für das Ereignis verantwortlich führte</span><span class="sxs-lookup"><span data-stu-id="9575a-134">User name of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessAccountSid` | <span data-ttu-id="9575a-135">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-135">string</span></span> | <span data-ttu-id="9575a-136">Security Identifier (SID) des Kontos, das den für das Ereignis verantwortlichen Prozess führte</span><span class="sxs-lookup"><span data-stu-id="9575a-136">Security Identifier (SID) of the account that ran the process responsible for the event</span></span> |
| `InitiatingProcessIntegrityLevel` | <span data-ttu-id="9575a-137">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-137">string</span></span> | <span data-ttu-id="9575a-138">Integritätsebene des Prozesses, der das Ereignis initiiert hat.</span><span class="sxs-lookup"><span data-stu-id="9575a-138">Integrity level of the process that initiated the event.</span></span> <span data-ttu-id="9575a-139">Windows weist Prozesse Integritätsstufen basierend auf bestimmten Merkmalen zu, z. B. wenn sie über einen Internetdownload gestartet wurden.</span><span class="sxs-lookup"><span data-stu-id="9575a-139">Windows assigns integrity levels to processes based on certain characteristics, such as if they were launched from an internet download.</span></span> <span data-ttu-id="9575a-140">Diese Integritätsstufen beeinflussen Berechtigungen für Ressourcen</span><span class="sxs-lookup"><span data-stu-id="9575a-140">These integrity levels influence permissions to resources</span></span> |
| `InitiatingProcessTokenElevation` | <span data-ttu-id="9575a-141">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-141">string</span></span> | <span data-ttu-id="9575a-142">Tokentyp, der angibt, ob die Berechtigungserweiterung für die Benutzerzugriffssteuerung (User Access Control, UAC) auf den Prozess angewendet wurde, der das Ereignis initiiert hat</span><span class="sxs-lookup"><span data-stu-id="9575a-142">Token type indicating the presence or absence of User Access Control (UAC) privilege elevation applied to the process that initiated the event</span></span> |
| `InitiatingProcessSHA1` | <span data-ttu-id="9575a-143">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-143">string</span></span> | <span data-ttu-id="9575a-144">SHA-1 des Prozesses (Bilddatei), der das Ereignis initiiert hat</span><span class="sxs-lookup"><span data-stu-id="9575a-144">SHA-1 of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessMD5` | <span data-ttu-id="9575a-145">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-145">string</span></span> | <span data-ttu-id="9575a-146">MD5-Hash des Prozesses (Bilddatei), der das Ereignis initiiert hat</span><span class="sxs-lookup"><span data-stu-id="9575a-146">MD5 hash of the process (image file) that initiated the event</span></span> |
| `InitiatingProcessFileName` | <span data-ttu-id="9575a-147">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-147">string</span></span> | <span data-ttu-id="9575a-148">Name des Prozesses, der das Ereignis initiiert hat</span><span class="sxs-lookup"><span data-stu-id="9575a-148">Name of the process that initiated the event</span></span> |
| `InitiatingProcessId` | <span data-ttu-id="9575a-149">int</span><span class="sxs-lookup"><span data-stu-id="9575a-149">int</span></span> | <span data-ttu-id="9575a-150">Prozess-ID (PID) des Prozesses, der das Ereignis initiiert hat</span><span class="sxs-lookup"><span data-stu-id="9575a-150">Process ID (PID) of the process that initiated the event</span></span> |
| `InitiatingProcessCommandLine` | <span data-ttu-id="9575a-151">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-151">string</span></span> | <span data-ttu-id="9575a-152">Befehlszeile zum Ausführen des Prozesses, der das Ereignis initiiert hat</span><span class="sxs-lookup"><span data-stu-id="9575a-152">Command line used to run the process that initiated the event</span></span> |
| `InitiatingProcessCreationTime` | <span data-ttu-id="9575a-153">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="9575a-153">datetime</span></span> | <span data-ttu-id="9575a-154">Datum und Uhrzeit, zu dem der Prozess gestartet wurde, der das Ereignis initiiert hat</span><span class="sxs-lookup"><span data-stu-id="9575a-154">Date and time when the process that initiated the event was started</span></span> |
| `InitiatingProcessFolderPath` | <span data-ttu-id="9575a-155">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-155">string</span></span> | <span data-ttu-id="9575a-156">Ordner mit dem Prozess (Bilddatei), der das Ereignis initiiert hat</span><span class="sxs-lookup"><span data-stu-id="9575a-156">Folder containing the process (image file) that initiated the event</span></span> |
| `InitiatingProcessParentId` | <span data-ttu-id="9575a-157">int</span><span class="sxs-lookup"><span data-stu-id="9575a-157">int</span></span> | <span data-ttu-id="9575a-158">Prozess-ID (PID) des übergeordneten Prozesses, der den prozess, der für das Ereignis verantwortlich war,</span><span class="sxs-lookup"><span data-stu-id="9575a-158">Process ID (PID) of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentFileName` | <span data-ttu-id="9575a-159">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-159">string</span></span> | <span data-ttu-id="9575a-160">Name des übergeordneten Prozesses, der den prozessverantwortlichen Prozess für das Ereignis gezeitet hat</span><span class="sxs-lookup"><span data-stu-id="9575a-160">Name of the parent process that spawned the process responsible for the event</span></span> |
| `InitiatingProcessParentCreationTime` | <span data-ttu-id="9575a-161">Datum/Uhrzeit</span><span class="sxs-lookup"><span data-stu-id="9575a-161">datetime</span></span> | <span data-ttu-id="9575a-162">Datum und Uhrzeit, zu der das übergeordnete Element des für das Ereignis verantwortlichen Prozesses gestartet wurde</span><span class="sxs-lookup"><span data-stu-id="9575a-162">Date and time when the parent of the process responsible for the event was started</span></span> |
| `ReportId` | <span data-ttu-id="9575a-163">long</span><span class="sxs-lookup"><span data-stu-id="9575a-163">long</span></span> | <span data-ttu-id="9575a-164">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="9575a-164">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="9575a-165">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten `DeviceName` und verwendet `Timestamp` werden.</span><span class="sxs-lookup"><span data-stu-id="9575a-165">To identify unique events, this column must be used in conjunction with the `DeviceName` and `Timestamp` columns</span></span> |
| `AppGuardContainerId` | <span data-ttu-id="9575a-166">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="9575a-166">string</span></span> | <span data-ttu-id="9575a-167">Id für den virtualisierten Container, der von Application Guard zum Isolieren von Browseraktivitäten verwendet wird</span><span class="sxs-lookup"><span data-stu-id="9575a-167">Identifier for the virtualized container used by Application Guard to isolate browser activity</span></span> |

## <a name="related-topics"></a><span data-ttu-id="9575a-168">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9575a-168">Related topics</span></span>
- [<span data-ttu-id="9575a-169">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="9575a-169">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9575a-170">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="9575a-170">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9575a-171">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="9575a-171">Understand the schema</span></span>](advanced-hunting-schema-reference.md)