---
title: Tabelle "EmailPostDeliveryEvents" im Schema "Erweiterte Suche"
description: Informationen zu Post-Delivery-Aktionen für Microsoft 365-E-Mails in der Tabelle "EmailPostDeliveryEvents" des Schemas für die erweiterte Suche
keywords: Erweiterte Suche, Bedrohungssuche, Cyberbedrohungssuche, Microsoft Threat Protection, Microsoft 365, mtp, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, EmailPostDeliveryEvents, Netzwerknachrichten-ID, Absender, Empfänger, Anlagen-ID, Anlagenname, Malware-Bewert, Phishing-Bewert, Anlagenanzahl, Linkanzahl, URL-Anzahl
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
ms.technology: m365d
ms.openlocfilehash: d7920be05156320411f3907cbcdae88d315b5136
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49929706"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="9d60e-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="9d60e-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="9d60e-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="9d60e-105">**Applies to:**</span></span>
- <span data-ttu-id="9d60e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="9d60e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="9d60e-107">Die Tabelle im Schema für die erweiterte Suche enthält Informationen zu Aktionen nach der Zustellung, die für von `EmailPostDeliveryEvents` Microsoft 365 verarbeitete E-Mail-Nachrichten ergriffen werden. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="9d60e-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="9d60e-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="9d60e-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="9d60e-109">Ausführliche Informationen zu den Ereignistypen (Werten), die von einer Tabelle unterstützt werden, finden Sie in der integrierten Schemareferenz, die im `ActionType` Security Center verfügbar ist. [](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="9d60e-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="9d60e-110">Um weitere Informationen zu einzelnen E-Mail-Nachrichten zu erhalten, können Sie auch die [`EmailEvents`](advanced-hunting-emailevents-table.md) , und die Tabellen [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="9d60e-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="9d60e-111">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="9d60e-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="9d60e-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="9d60e-112">Column name</span></span> | <span data-ttu-id="9d60e-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="9d60e-113">Data type</span></span> | <span data-ttu-id="9d60e-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="9d60e-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="9d60e-115">datetime</span><span class="sxs-lookup"><span data-stu-id="9d60e-115">datetime</span></span> | <span data-ttu-id="9d60e-116">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="9d60e-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="9d60e-117">string</span><span class="sxs-lookup"><span data-stu-id="9d60e-117">string</span></span> | <span data-ttu-id="9d60e-118">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="9d60e-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="9d60e-119">string</span><span class="sxs-lookup"><span data-stu-id="9d60e-119">string</span></span> | <span data-ttu-id="9d60e-120">Eindeutiger Bezeichner für die von Microsoft 365 generierte E-Mail</span><span class="sxs-lookup"><span data-stu-id="9d60e-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="9d60e-121">string</span><span class="sxs-lookup"><span data-stu-id="9d60e-121">string</span></span> | <span data-ttu-id="9d60e-122">Öffentlich sichtbarer Bezeichner für die E-Mail-Nachricht, die vom sendenden E-Mail-System festgelegt wird</span><span class="sxs-lookup"><span data-stu-id="9d60e-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="9d60e-123">string</span><span class="sxs-lookup"><span data-stu-id="9d60e-123">string</span></span> | <span data-ttu-id="9d60e-124">Für die Entität ergriffene Aktion</span><span class="sxs-lookup"><span data-stu-id="9d60e-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="9d60e-125">string</span><span class="sxs-lookup"><span data-stu-id="9d60e-125">string</span></span> | <span data-ttu-id="9d60e-126">Aktivitätstyp, der das Ereignis ausgelöst hat: Manuelle Wartung, Phish ZAP, Schadsoftware ZAP</span><span class="sxs-lookup"><span data-stu-id="9d60e-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="9d60e-127">string</span><span class="sxs-lookup"><span data-stu-id="9d60e-127">string</span></span> | <span data-ttu-id="9d60e-128">Gibt an, ob eine Aktion von einem Administrator (manuell oder durch Genehmigung einer ausstehenden automatisierten Aktion) oder durch einen speziellen Mechanismus ausgelöst wurde, z. B. eine ZAP- oder dynamische Übermittlung.</span><span class="sxs-lookup"><span data-stu-id="9d60e-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="9d60e-129">string</span><span class="sxs-lookup"><span data-stu-id="9d60e-129">string</span></span> | <span data-ttu-id="9d60e-130">Ergebnis der Aktion</span><span class="sxs-lookup"><span data-stu-id="9d60e-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="9d60e-131">string</span><span class="sxs-lookup"><span data-stu-id="9d60e-131">string</span></span> | <span data-ttu-id="9d60e-132">E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="9d60e-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="9d60e-133">string</span><span class="sxs-lookup"><span data-stu-id="9d60e-133">string</span></span> | <span data-ttu-id="9d60e-134">Der Ort, an den die E-Mail zugestellt wurde: "Posteingang/Ordner", "lokal"/"extern", "Junk", "Quarantäne", "Fehler", „Verloren“ oder "Gelöschte Elemente"</span><span class="sxs-lookup"><span data-stu-id="9d60e-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="9d60e-135">Unterstützte Ereignistypen</span><span class="sxs-lookup"><span data-stu-id="9d60e-135">Supported event types</span></span>
<span data-ttu-id="9d60e-136">In dieser Tabelle werden Ereignisse mit den folgenden Werten `ActionType` erfasst:</span><span class="sxs-lookup"><span data-stu-id="9d60e-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="9d60e-137">**Manuelle Korrektur:** Ein Administrator hat manuell Aktionen für eine E-Mail-Nachricht nach derEn Zugestellt an das Benutzerpostfach ergreifen.</span><span class="sxs-lookup"><span data-stu-id="9d60e-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="9d60e-138">Dazu gehören Aktionen, die manuell über [den Bedrohungs-Explorer](../office-365-security/threat-explorer.md) oder Genehmigungen von automatisierten Untersuchungs- und [Reaktionsaktionen (AIR) ergriffen werden.](mtp-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="9d60e-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="9d60e-139">**Phish ZAP** – [Zap (Zero-hour Auto Purge)](../office-365-security/zero-hour-auto-purge.md) hat nach der Zustellung eine Aktion für eine Phishing-E-Mail-Nachricht ergreifen.</span><span class="sxs-lookup"><span data-stu-id="9d60e-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="9d60e-140">**Schadsoftware ZAP** – Zap hat eine E-Mail-Nachricht, die nach der Zustellung Schadsoftware enthält, automatisch gelöscht (Zero-Hour Auto Purge, ZAP) gelöscht.</span><span class="sxs-lookup"><span data-stu-id="9d60e-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="9d60e-141">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="9d60e-141">Related topics</span></span>
- [<span data-ttu-id="9d60e-142">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="9d60e-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="9d60e-143">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="9d60e-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="9d60e-144">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="9d60e-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="9d60e-145">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="9d60e-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="9d60e-146">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="9d60e-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="9d60e-147">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="9d60e-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
