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
ms.collection:
- M365-security-compliance
- m365-initiative-m365-defender
ms.topic: article
ms.openlocfilehash: 65cd02f4277cf3694d85eac92392899b140c9f74
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/09/2020
ms.locfileid: "48412142"
---
# <a name="emailpostdeliveryevents"></a><span data-ttu-id="161cd-104">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="161cd-104">EmailPostDeliveryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="161cd-105">**Gilt für:**</span><span class="sxs-lookup"><span data-stu-id="161cd-105">**Applies to:**</span></span>
- <span data-ttu-id="161cd-106">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="161cd-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="161cd-107">Die `EmailPostDeliveryEvents` Tabelle im [Advanced Hunting](advanced-hunting-overview.md) -Schema enthält Informationen zu Post Zustellungs Aktionen für e-Mail-Nachrichten, die von Microsoft 365 verarbeitet wurden.</span><span class="sxs-lookup"><span data-stu-id="161cd-107">The `EmailPostDeliveryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains information about post-delivery actions taken on email messages processed by Microsoft 365.</span></span> <span data-ttu-id="161cd-108">Verwenden Sie dieser Referenz, um Abfragen zu erstellen, die Informationen aus dieser Tabelle zurückgeben.</span><span class="sxs-lookup"><span data-stu-id="161cd-108">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="161cd-109">Ausführliche Informationen zu den `ActionType` von einer Tabelle unterstützten Ereignistypen (Values) finden Sie in der [integrierten Schemareferenz](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) , die im Sicherheitscenter verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="161cd-109">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="161cd-110">Wenn Sie weitere Informationen zu einzelnen e-Mail-Nachrichten erhalten möchten, können Sie auch die [`EmailEvents`](advanced-hunting-emailevents-table.md) [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md) Tabellen verwenden [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) .</span><span class="sxs-lookup"><span data-stu-id="161cd-110">To get more information about individual email messages, you can also use the [`EmailEvents`](advanced-hunting-emailevents-table.md), [`EmailAttachmentInfo`](advanced-hunting-emailattachmentinfo-table.md), and the [`EmailUrlInfo`](advanced-hunting-emailurlinfo-table.md) tables.</span></span> <span data-ttu-id="161cd-111">Informationen zu anderen Tabellen im Schema "Erweiterte Suche" finden Sie unter [Referenz zur erweiterten Suche](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="161cd-111">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="161cd-112">Spaltenname</span><span class="sxs-lookup"><span data-stu-id="161cd-112">Column name</span></span> | <span data-ttu-id="161cd-113">Datentyp</span><span class="sxs-lookup"><span data-stu-id="161cd-113">Data type</span></span> | <span data-ttu-id="161cd-114">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="161cd-114">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="161cd-115">datetime</span><span class="sxs-lookup"><span data-stu-id="161cd-115">datetime</span></span> | <span data-ttu-id="161cd-116">Datum und Uhrzeit der Aufzeichnung des Ereignisses</span><span class="sxs-lookup"><span data-stu-id="161cd-116">Date and time when the event was recorded</span></span> |
| `EventId` | <span data-ttu-id="161cd-117">string</span><span class="sxs-lookup"><span data-stu-id="161cd-117">string</span></span> | <span data-ttu-id="161cd-118">Eindeutiger Bezeichner für das Ereignis</span><span class="sxs-lookup"><span data-stu-id="161cd-118">Unique identifier for the event</span></span> |
| `NetworkMessageId` | <span data-ttu-id="161cd-119">string</span><span class="sxs-lookup"><span data-stu-id="161cd-119">string</span></span> | <span data-ttu-id="161cd-120">Eindeutiger Bezeichner für die von Microsoft 365 generierte e-Mail</span><span class="sxs-lookup"><span data-stu-id="161cd-120">Unique identifier for the email, generated by Microsoft 365</span></span> |
| `InternetMessageId` | <span data-ttu-id="161cd-121">string</span><span class="sxs-lookup"><span data-stu-id="161cd-121">string</span></span> | <span data-ttu-id="161cd-122">Öffentlich sichtbarer Bezeichner für die E-Mail-Nachricht, die vom sendenden E-Mail-System festgelegt wird</span><span class="sxs-lookup"><span data-stu-id="161cd-122">Public-facing identifier for the email that is set by the sending email system</span></span> |
| `Action` | <span data-ttu-id="161cd-123">string</span><span class="sxs-lookup"><span data-stu-id="161cd-123">string</span></span> | <span data-ttu-id="161cd-124">Für die Entität ausgeführte Aktion</span><span class="sxs-lookup"><span data-stu-id="161cd-124">Action taken on the entity</span></span> |
| `ActionType` | <span data-ttu-id="161cd-125">string</span><span class="sxs-lookup"><span data-stu-id="161cd-125">string</span></span> | <span data-ttu-id="161cd-126">Typ der Aktivität, die das Ereignis ausgelöst hat: manuelle Korrektur, Phishing-zap, Malware-zap</span><span class="sxs-lookup"><span data-stu-id="161cd-126">Type of activity that triggered the event: Manual remediation, Phish ZAP, Malware ZAP</span></span> |
| `ActionTrigger` | <span data-ttu-id="161cd-127">string</span><span class="sxs-lookup"><span data-stu-id="161cd-127">string</span></span> | <span data-ttu-id="161cd-128">Gibt an, ob eine Aktion von einem Administrator (manuell oder durch Genehmigung einer ausstehenden automatisierten Aktion) oder durch einen speziellen Mechanismus wie zap oder dynamische Zustellung ausgelöst wurde.</span><span class="sxs-lookup"><span data-stu-id="161cd-128">Indicates whether an action was triggered by an administrator (manually or through approval of a pending automated action), or by some special mechanism, such as a ZAP or Dynamic Delivery</span></span> |
| `ActionResult` | <span data-ttu-id="161cd-129">string</span><span class="sxs-lookup"><span data-stu-id="161cd-129">string</span></span> | <span data-ttu-id="161cd-130">Ergebnis der Aktion</span><span class="sxs-lookup"><span data-stu-id="161cd-130">Result of the action</span></span> |
| `RecipientEmailAddress` | <span data-ttu-id="161cd-131">string</span><span class="sxs-lookup"><span data-stu-id="161cd-131">string</span></span> | <span data-ttu-id="161cd-132">E-Mail-Adresse des Empfängers oder E-Mail-Adresse des Empfängers nach Erweiterung der Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="161cd-132">Email address of the recipient, or email address of the recipient after distribution list expansion</span></span> |
| `DeliveryLocation` | <span data-ttu-id="161cd-133">string</span><span class="sxs-lookup"><span data-stu-id="161cd-133">string</span></span> | <span data-ttu-id="161cd-134">Der Ort, an den die E-Mail zugestellt wurde: "Posteingang/Ordner", "lokal"/"extern", "Junk", "Quarantäne", "Fehler", „Verloren“ oder "Gelöschte Elemente"</span><span class="sxs-lookup"><span data-stu-id="161cd-134">Location where the email was delivered: Inbox/Folder, On-premises/External, Junk, Quarantine, Failed, Dropped, Deleted items</span></span> |

## <a name="supported-event-types"></a><span data-ttu-id="161cd-135">Unterstützte Ereignistypen</span><span class="sxs-lookup"><span data-stu-id="161cd-135">Supported event types</span></span>
<span data-ttu-id="161cd-136">In dieser Tabelle werden Ereignisse mit den folgenden `ActionType` Werten erfasst:</span><span class="sxs-lookup"><span data-stu-id="161cd-136">This table captures events with the following `ActionType` values:</span></span>

- <span data-ttu-id="161cd-137">**Manuelle Korrektur** : ein Administrator hat manuell eine Aktion für eine e-Mail-Nachricht durchgeführt, nachdem er an das Benutzerpostfach übermittelt wurde.</span><span class="sxs-lookup"><span data-stu-id="161cd-137">**Manual remediation** – An administrator manually took action on an email message after it was delivered to the user mailbox.</span></span> <span data-ttu-id="161cd-138">Dies umfasst Aktionen, die manuell über den [Threat Explorer](../office-365-security/threat-explorer.md) oder Genehmigungen für [automatisierte Ermittlungs-und Antwort Aktionen (Air)](mtp-autoir-actions.md)ausgeführt werden.</span><span class="sxs-lookup"><span data-stu-id="161cd-138">This includes actions taken manually through [Threat Explorer](../office-365-security/threat-explorer.md) or approvals of [automated investigation and response (AIR) actions](mtp-autoir-actions.md).</span></span>
- <span data-ttu-id="161cd-139">**Phishing zap** – [Zero-Hour Auto Purge (zap)](../office-365-security/zero-hour-auto-purge.md) hat nach der Zustellung Aktionen für eine Phishing-e-Mail durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="161cd-139">**Phish ZAP** – [Zero-hour auto purge (ZAP)](../office-365-security/zero-hour-auto-purge.md) took action on a phishing email after delivery.</span></span>
- <span data-ttu-id="161cd-140">**Malware zap** – Zero-Hour Auto Purge (zap) hat eine Aktion für eine e-Mail-Nachricht gefunden, die Schadsoftware nach der Zustellung enthält.</span><span class="sxs-lookup"><span data-stu-id="161cd-140">**Malware ZAP** – Zero-hour auto purge (ZAP) took action on an email message found containing malware after delivery.</span></span>

## <a name="related-topics"></a><span data-ttu-id="161cd-141">Verwandte Themen</span><span class="sxs-lookup"><span data-stu-id="161cd-141">Related topics</span></span>
- [<span data-ttu-id="161cd-142">Übersicht über die erweiterte Suche</span><span class="sxs-lookup"><span data-stu-id="161cd-142">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="161cd-143">Lernen der Abfragesprache</span><span class="sxs-lookup"><span data-stu-id="161cd-143">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="161cd-144">Verwenden freigegebener Abfragen</span><span class="sxs-lookup"><span data-stu-id="161cd-144">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="161cd-145">Suchen auf Geräten, in E-Mails, Apps und Identitäten</span><span class="sxs-lookup"><span data-stu-id="161cd-145">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="161cd-146">Grundlegendes zum Schema</span><span class="sxs-lookup"><span data-stu-id="161cd-146">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="161cd-147">Anwenden bewährter Methoden für Abfragen</span><span class="sxs-lookup"><span data-stu-id="161cd-147">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
