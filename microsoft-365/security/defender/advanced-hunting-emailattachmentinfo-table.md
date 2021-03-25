---
title: Tabelle "EmailAttachmentInfo" im Schema "Erweiterte Suche"
description: Hier erfahren Sie mehr über die in der Tabelle "EmailAttachmentInfo" des Schemas "Erweiterte Suche" enthaltenen Informationen zu Anlagen.
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailAttachmentInfo, network message id, sender, recipient, attachment id, attachment name, malware verdict
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
mms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 43e861d43e6e98f1e17d737f431bb72c42f3f4f6
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/23/2021
ms.locfileid: "51065920"
---
# <a name="emailattachmentinfo"></a><span data-ttu-id="c1ba6-104">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="c1ba6-104">EmailAttachmentInfo</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="c1ba6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="c1ba6-105">**Applies to:**</span></span>
- <span data-ttu-id="c1ba6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c1ba6-106">Microsoft 365 Defender</span></span>



<span data-ttu-id="c1ba6-107">Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Anlagen in E-Mails, die von `EmailAttachmentInfo` Microsoft Defender für Office 365 verarbeitet wurden. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="c1ba6-107">The `EmailAttachmentInfo` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about attachments on emails processed by Microsoft Defender for Office 365.</span></span> <span data-ttu-id="c1ba6-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="c1ba6-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="c1ba6-109">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="c1ba6-109">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="c1ba6-110">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="c1ba6-110">Column name</span></span> | <span data-ttu-id="c1ba6-111">Datentyp</span><span class="sxs-lookup"><span data-stu-id="c1ba6-111">Data type</span></span> | <span data-ttu-id="c1ba6-112">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="c1ba6-112">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="c1ba6-113">datetime</span><span class="sxs-lookup"><span data-stu-id="c1ba6-113">datetime</span></span> | <span data-ttu-id="c1ba6-114">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="c1ba6-114">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="c1ba6-115">string</span><span class="sxs-lookup"><span data-stu-id="c1ba6-115">string</span></span> | <span data-ttu-id="c1ba6-116">Eindeutige ID für die von Microsoft 365 generierte E-Mail</span><span class="sxs-lookup"><span data-stu-id="c1ba6-116">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `SenderFromAddress` | <span data-ttu-id="c1ba6-117">string</span><span class="sxs-lookup"><span data-stu-id="c1ba6-117">string</span></span> | <span data-ttu-id="c1ba6-118">Für E-Mail-Empfänger im E-Mail-Client in der FROM-Kopfzeile angezeigte Absender-E-Mail-Adresse</span><span class="sxs-lookup"><span data-stu-id="c1ba6-118">Sender email address in the FROM header, which is visible to email recipients on their email clients</span></span> |
| `SenderDisplayName` | <span data-ttu-id="c1ba6-119">string</span><span class="sxs-lookup"><span data-stu-id="c1ba6-119">string</span></span> | <span data-ttu-id="c1ba6-120">Name des absenders, der im Adressbuch angezeigt wird, in der Regel eine Kombination aus einem vor- oder vornamen, einer mittleren Initiale und einem Nachnamen oder Nachnamen</span><span class="sxs-lookup"><span data-stu-id="c1ba6-120">Name of the sender displayed in the address book, typically a combination of a given or first name, a middle initial, and a last name or surname</span></span> |
| `SenderObjectId` | <span data-ttu-id="c1ba6-121">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c1ba6-121">string</span></span> | <span data-ttu-id="c1ba6-122">Eindeutige ID für das Konto des Absenders in Azure AD</span><span class="sxs-lookup"><span data-stu-id="c1ba6-122">Unique identifier for the sender’s account in Azure AD</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="c1ba6-123">string</span><span class="sxs-lookup"><span data-stu-id="c1ba6-123">string</span></span> | <span data-ttu-id="c1ba6-124">E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="c1ba6-124">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `RecipientObjectId` | <span data-ttu-id="c1ba6-125">string</span><span class="sxs-lookup"><span data-stu-id="c1ba6-125">string</span></span> | <span data-ttu-id="c1ba6-126">Eindeutige ID für den E-Mail-Empfänger in Azure AD</span><span class="sxs-lookup"><span data-stu-id="c1ba6-126">Unique identifier for the email recipient in Azure AD</span></span> |
| `FileName` | <span data-ttu-id="c1ba6-127">string</span><span class="sxs-lookup"><span data-stu-id="c1ba6-127">string</span></span> | <span data-ttu-id="c1ba6-128">Name der Datei, auf die die aufgezeichnete Aktion angewendet wurde</span><span class="sxs-lookup"><span data-stu-id="c1ba6-128">Name of the file that the recorded action was applied to</span></span> |
| `FileType` | <span data-ttu-id="c1ba6-129">string</span><span class="sxs-lookup"><span data-stu-id="c1ba6-129">string</span></span> | <span data-ttu-id="c1ba6-130">Dateierweiterungstyp</span><span class="sxs-lookup"><span data-stu-id="c1ba6-130">File extension type</span></span> |
| `SHA256` | <span data-ttu-id="c1ba6-131">string</span><span class="sxs-lookup"><span data-stu-id="c1ba6-131">string</span></span> | <span data-ttu-id="c1ba6-132">SHA-256 der Datei, auf die die aufgezeichnete Aktion angewendet wurde.</span><span class="sxs-lookup"><span data-stu-id="c1ba6-132">SHA-256 of the file that the recorded action was applied to.</span></span> <span data-ttu-id="c1ba6-133">Dieses Feld wird in der Regel nicht ausgefüllt – Verwenden Sie die SHA1-Spalte, wenn verfügbar.</span><span class="sxs-lookup"><span data-stu-id="c1ba6-133">This field is usually not populated — use the SHA1 column when available.</span></span> |
| `ThreatTypes` | <span data-ttu-id="c1ba6-134">string</span><span class="sxs-lookup"><span data-stu-id="c1ba6-134">string</span></span> | <span data-ttu-id="c1ba6-135">Bestimmen Sie aus dem E-Mail-Filterstapel, ob die E-Mail Schadsoftware, Phishing oder andere Bedrohungen enthält.</span><span class="sxs-lookup"><span data-stu-id="c1ba6-135">Verdict from the email filtering stack on whether the email contains malware, phishing, or other threats</span></span> |
| `ThreatNames` | <span data-ttu-id="c1ba6-136">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c1ba6-136">string</span></span> | <span data-ttu-id="c1ba6-137">Erkennungsname für Schadsoftware oder andere gefundene Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="c1ba6-137">Detection name for malware or other threats found</span></span> |
| `DetectionMethods` | <span data-ttu-id="c1ba6-138">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="c1ba6-138">string</span></span> | <span data-ttu-id="c1ba6-139">Methoden zum Erkennen von Schadsoftware, Phishing oder anderen In der E-Mail gefundenen Bedrohungen</span><span class="sxs-lookup"><span data-stu-id="c1ba6-139">Methods used to detect malware, phishing, or other threats found in the email</span></span> |
| `ReportId` | <span data-ttu-id="c1ba6-140">long</span><span class="sxs-lookup"><span data-stu-id="c1ba6-140">long</span></span> | <span data-ttu-id="c1ba6-141">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="c1ba6-141">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="c1ba6-142">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="c1ba6-142">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="related-topics"></a><span data-ttu-id="c1ba6-143">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="c1ba6-143">Related topics</span></span>
- [<span data-ttu-id="c1ba6-144">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="c1ba6-144">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="c1ba6-145">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="c1ba6-145">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="c1ba6-146">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="c1ba6-146">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="c1ba6-147">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="c1ba6-147">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="c1ba6-148">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="c1ba6-148">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="c1ba6-149">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="c1ba6-149">Apply query best practices</span></span>](advanced-hunting-best-practices.md)