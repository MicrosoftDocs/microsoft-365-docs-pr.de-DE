---
title: EmailPostDeliveryEvents-Tabelle im schema der erweiterten Suche
description: Informationen zu Aktionen nach der Zustellung für Microsoft 365-E-Mails finden Sie in der EmailPostDeliveryEvents-Tabelle des schemas für erweiterte Suche
keywords: Advanced Hunting, Threat Hunting, Cyber Threat Hunting, Microsoft Threat Protection, microsoft 365, mtp, m365, search, query, telemetry, schema reference, kusto, table, column, data type, description, EmailPostDeliveryEvents, network message id, sender, recipient, attachment id, attachment id, attachment name, malware verdict, phishing verdict, attachment count, link count, url count
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
ms.openlocfilehash: 8940d1dd370f804f8539bf4e753b1112d3c8d3bf
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2021
ms.locfileid: "51198197"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="ef110-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="ef110-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="ef110-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="ef110-105">**Applies to:**</span></span>
- <span data-ttu-id="ef110-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ef110-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="ef110-107">Die Tabelle im Schema der erweiterten Suche enthält Informationen zu Aktionen nach der Zustellung, die für von `EmailPostDeliveryEvents` Microsoft 365 verarbeitete E-Mail-Nachrichten ergriffen werden. [](advanced-hunting-overview.md)</span><span class="sxs-lookup"><span data-stu-id="ef110-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="ef110-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="ef110-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="ef110-109">Ausführliche Informationen zu den von einer Tabelle unterstützten Ereignistypen ( Werte) finden Sie unter Verwendung der integrierten Schemareferenz, die `ActionType` im Security Center verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="ef110-109">For detailed information about the events types (`ActionType` values) supported by a table, use the built-in schema reference available in the security center.</span></span>

<span data-ttu-id="ef110-110">Um weitere Informationen zu einzelnen E-Mail-Nachrichten zu erhalten, können Sie auch die [`EmailEvents`](advanced-hunting-emailevents-table.md) , und die Tabellen [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) verwenden.</span><span class="sxs-lookup"><span data-stu-id="ef110-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="ef110-111">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="ef110-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="ef110-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="ef110-112">Column name</span></span> | <span data-ttu-id="ef110-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="ef110-113">Data type</span></span> | <span data-ttu-id="ef110-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="ef110-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="ef110-115">datetime</span><span class="sxs-lookup"><span data-stu-id="ef110-115">datetime</span></span> | <span data-ttu-id="ef110-116">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="ef110-116">Date and time when the event was recorded</span></span> |
| `NetworkMessageId` | <span data-ttu-id="ef110-117">string</span><span class="sxs-lookup"><span data-stu-id="ef110-117">string</span></span> | <span data-ttu-id="ef110-118">Eindeutige ID für die von Microsoft 365 generierte E-Mail</span><span class="sxs-lookup"><span data-stu-id="ef110-118">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="ef110-119">string</span><span class="sxs-lookup"><span data-stu-id="ef110-119">string</span></span> | <span data-ttu-id="ef110-120">Öffentlich sichtbarer Bezeichner für die E-Mail-Nachricht, die vom sendenden E-Mail-System festgelegt wird</span><span class="sxs-lookup"><span data-stu-id="ef110-120">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="ef110-121">string</span><span class="sxs-lookup"><span data-stu-id="ef110-121">string</span></span> | <span data-ttu-id="ef110-122">Für die Entität ergriffene Aktion</span><span class="sxs-lookup"><span data-stu-id="ef110-122">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="ef110-123">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef110-123">string</span></span> | <span data-ttu-id="ef110-124">Aktivitätstyp, der das Ereignis ausgelöst hat: Manuelle Korrektur, Phish ZAP, Schadsoftware-ZAP</span><span class="sxs-lookup"><span data-stu-id="ef110-124">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="ef110-125">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef110-125">string</span></span> | <span data-ttu-id="ef110-126">Gibt an, ob eine Aktion von einem Administrator ausgelöst wurde (manuell oder durch Genehmigung einer ausstehenden automatisierten Aktion) oder durch einen speziellen Mechanismus, z. B. eine ZAP oder dynamische Zustellung</span><span class="sxs-lookup"><span data-stu-id="ef110-126">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="ef110-127">Zeichenfolge</span><span class="sxs-lookup"><span data-stu-id="ef110-127">string</span></span> | <span data-ttu-id="ef110-128">Ergebnis der Aktion</span><span class="sxs-lookup"><span data-stu-id="ef110-128">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="ef110-129">string</span><span class="sxs-lookup"><span data-stu-id="ef110-129">string</span></span> | <span data-ttu-id="ef110-130">E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="ef110-130">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="ef110-131">string</span><span class="sxs-lookup"><span data-stu-id="ef110-131">string</span></span> | <span data-ttu-id="ef110-132">Der Ort, an den die E-Mail zugestellt wurde: "Posteingang/Ordner", "lokal"/"extern", "Junk", "Quarantäne", "Fehler", „Verloren“ oder "Gelöschte Elemente"</span><span class="sxs-lookup"><span data-stu-id="ef110-132">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |
| `ReportId` | <span data-ttu-id="ef110-133">long</span><span class="sxs-lookup"><span data-stu-id="ef110-133">long</span></span> | <span data-ttu-id="ef110-134">Ereignisbezeichner basierend auf einem Repeating-Indikator.</span><span class="sxs-lookup"><span data-stu-id="ef110-134">Event identifier based on a repeating counter.</span></span> <span data-ttu-id="ef110-135">Um eindeutige Ereignisse zu identifizieren, muss diese Spalte in Verbindung mit den Spalten DeviceName und Timestamp verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="ef110-135">To identify unique events, this column must be used in conjunction with the DeviceName and Timestamp columns.</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="ef110-136">Unterstützte Ereignistypen</span><span class="sxs-lookup"><span data-stu-id="ef110-136">Supported event types</span></span>
<span data-ttu-id="ef110-137">Diese Tabelle erfasst Ereignisse mit den folgenden `ActionType` Werten:</span><span class="sxs-lookup"><span data-stu-id="ef110-137">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="ef110-138">**Manuelle Korrektur:** Ein Administrator hat manuell Eine E-Mail-Nachricht nach der Zugestellten an das Benutzerpostfach aktiviert.</span><span class="sxs-lookup"><span data-stu-id="ef110-138">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="ef110-139">Dazu gehören Aktionen, die manuell über [den Bedrohungs-Explorer](../office-365-security/threat-explorer.md) oder Genehmigungen von automatisierten Untersuchungs- und Reaktionsaktionen [(AIR) ergriffen werden.](m365d-autoir-actions.md)</span><span class="sxs-lookup"><span data-stu-id="ef110-139">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](m365d-autoir-actions.md).</span></span>
- <span data-ttu-id="ef110-140">**Phish ZAP** – Die automatische Reinigung [(Zero-Hour Auto Purge, ZAP)](../office-365-security/zero-hour-auto-purge.md) hat nach der Zustellung Eine Phishing-E-Mail verwendet.</span><span class="sxs-lookup"><span data-stu-id="ef110-140">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="ef110-141">**Schadsoftware ZAP** – Die automatische Reinigung (Zero-Hour Auto Purge, ZAP) hat eine E-Mail-Nachricht nach der Zustellung mit Schadsoftware gefunden.</span><span class="sxs-lookup"><span data-stu-id="ef110-141">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="ef110-142">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="ef110-142">Related topics</span></span>
- [<span data-ttu-id="ef110-143">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="ef110-143">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ef110-144">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="ef110-144">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ef110-145">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="ef110-145">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="ef110-146">Suche über Geräte, E-Mails, Apps und Identitäten hinweg</span><span class="sxs-lookup"><span data-stu-id="ef110-146">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="ef110-147">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="ef110-147">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="ef110-148">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="ef110-148">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
