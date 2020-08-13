---
title: EmailPostDeliveryEvents-Tabelle im Advanced Hunting-Schema
description: Informationen zu Post Zustellungs Aktionen, die in Microsoft 365-e-Mails in der EmailPostDeliveryEvents-Tabelle des Advanced Hunting-Schemas ausgeführt wurden
keywords: Erweiterte Suche, Bedrohungs Suche, Cyber-Bedrohungs Suche, Microsoft Threat Protection, Microsoft 365, MTP, m365, Suche, Abfrage, Telemetrie, Schemareferenz, Kusto, Tabelle, Spalte, Datentyp, Beschreibung, EmailPostDeliveryEvents, Netzwerknachrichten-ID, Absender, Empfänger, Anlagen-ID, Anlagenname, Schadsoftware, Phishing-Urteil, ANLAGENANZAHL, Link Anzahl, URL-Anzahl
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
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 0384f3ba07b42c8e783994dfa1db75cf2d6ca80b
ms.sourcegitcommit: 51097b18d94da20aa727ebfbeb6ec84c263b25c3
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 08/12/2020
ms.locfileid: "46648863"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="f09f6-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="f09f6-104">EmailPostDeliveryEvents</span></span>

<span data-ttu-id="f09f6-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="f09f6-105">**Applies to:**</span></span>
- <span data-ttu-id="f09f6-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f09f6-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="f09f6-107">Die `EmailPostDeliveryEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Post Zustellungs Aktionen für e-Mail-Nachrichten, die von Microsoft 365 verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="f09f6-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="f09f6-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="f09f6-108">Use this reference to construct queries that return information from this table.</span></span>

<span data-ttu-id="f09f6-109">Wenn Sie weitere Informationen zu einzelnen e-Mail-Nachrichten erhalten möchten, können Sie auch die [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) Tabellen verwenden [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) .</span><span class="sxs-lookup"><span data-stu-id="f09f6-109">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="f09f6-110">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="f09f6-110">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="f09f6-111">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="f09f6-111">Column name</span></span> | <span data-ttu-id="f09f6-112">Datentyp</span><span class="sxs-lookup"><span data-stu-id="f09f6-112">Data type</span></span> | <span data-ttu-id="f09f6-113">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="f09f6-113">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="f09f6-114">datetime</span><span class="sxs-lookup"><span data-stu-id="f09f6-114">datetime</span></span> | <span data-ttu-id="f09f6-115">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="f09f6-115">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="f09f6-116">string</span><span class="sxs-lookup"><span data-stu-id="f09f6-116">string</span></span> | <span data-ttu-id="f09f6-117">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="f09f6-117">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="f09f6-118">string</span><span class="sxs-lookup"><span data-stu-id="f09f6-118">string</span></span> | <span data-ttu-id="f09f6-119">Eindeutiger Bezeichner für die von Microsoft 365 generierte e-Mail</span><span class="sxs-lookup"><span data-stu-id="f09f6-119">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="f09f6-120">string</span><span class="sxs-lookup"><span data-stu-id="f09f6-120">string</span></span> | <span data-ttu-id="f09f6-121">Öffentlich sichtbarer Bezeichner für die E-Mail-Nachricht, die vom sendenden E-Mail-System festgelegt wird</span><span class="sxs-lookup"><span data-stu-id="f09f6-121">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="f09f6-122">string</span><span class="sxs-lookup"><span data-stu-id="f09f6-122">string</span></span> | <span data-ttu-id="f09f6-123">Für die Entität ausgeführte Aktion</span><span class="sxs-lookup"><span data-stu-id="f09f6-123">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="f09f6-124">string</span><span class="sxs-lookup"><span data-stu-id="f09f6-124">string</span></span> | <span data-ttu-id="f09f6-125">Typ der Aktivität, die das Ereignis ausgelöst hat: manuelle Korrektur, Phishing-zap, Malware-zap</span><span class="sxs-lookup"><span data-stu-id="f09f6-125">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="f09f6-126">string</span><span class="sxs-lookup"><span data-stu-id="f09f6-126">string</span></span> | <span data-ttu-id="f09f6-127">Gibt an, ob eine Aktion von einem Administrator (manuell oder durch Genehmigung einer ausstehenden automatisierten Aktion) oder durch einen speziellen Mechanismus wie zap oder dynamische Zustellung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="f09f6-127">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="f09f6-128">string</span><span class="sxs-lookup"><span data-stu-id="f09f6-128">string</span></span> | <span data-ttu-id="f09f6-129">Ergebnis der Aktion</span><span class="sxs-lookup"><span data-stu-id="f09f6-129">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="f09f6-130">string</span><span class="sxs-lookup"><span data-stu-id="f09f6-130">string</span></span> | <span data-ttu-id="f09f6-131">E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="f09f6-131">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="f09f6-132">string</span><span class="sxs-lookup"><span data-stu-id="f09f6-132">string</span></span> | <span data-ttu-id="f09f6-133">Der Ort, an den die E-Mail zugestellt wurde: "Posteingang/Ordner", "lokal"/"extern", "Junk", "Quarantäne", "Fehler", „Verloren“ oder "Gelöschte Elemente"</span><span class="sxs-lookup"><span data-stu-id="f09f6-133">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="f09f6-134">Unterstützte Ereignistypen</span><span class="sxs-lookup"><span data-stu-id="f09f6-134">Supported event types</span></span>
<span data-ttu-id="f09f6-135">In dieser Tabelle werden Ereignisse mit den folgenden `ActionType` Werten erfasst:</span><span class="sxs-lookup"><span data-stu-id="f09f6-135">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="f09f6-136">**Manuelle Korrektur** : ein Administrator hat manuell eine Aktion für eine e-Mail-Nachricht durchgeführt, nachdem er an das Benutzerpostfach übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="f09f6-136">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="f09f6-137">Dies umfasst Aktionen, die manuell über den [Threat Explorer](../office-365-security/threat-explorer.md) oder Genehmigungen für [automatisierte Ermittlungs-und Antwort Aktionen (Air)](mtp-autoir-actions.md)ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="f09f6-137">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="f09f6-138">**Phishing zap** – [Zero-Hour Auto Purge (zap)](../office-365-security/zero-hour-auto-purge.md) hat nach der Zustellung Aktionen für eine Phishing-e-Mail durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="f09f6-138">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="f09f6-139">**Malware zap** – Zero-Hour Auto Purge (zap) hat eine Aktion für eine e-Mail-Nachricht gefunden, die Schadsoftware nach der Zustellung enthält.</span><span class="sxs-lookup"><span data-stu-id="f09f6-139">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="f09f6-140">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="f09f6-140">Related topics</span></span>
- [<span data-ttu-id="f09f6-141">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="f09f6-141">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="f09f6-142">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="f09f6-142">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="f09f6-143">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="f09f6-143">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="f09f6-144">Jagd auf Geräte, e-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="f09f6-144">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="f09f6-145">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="f09f6-145">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="f09f6-146">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="f09f6-146">Apply query best practices</span></span>](advanced-hunting-best-practices.md)