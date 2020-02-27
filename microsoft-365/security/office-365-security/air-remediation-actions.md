---
title: Korrekturaktionen in Office 365 automatisierte Untersuchung und Antwort
keywords: Luft, autoIR, ATP, automatisiert, Untersuchung, Antwort, Behebung, Bedrohungen, erweitert, Bedrohung, Schutz
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection: M365-security-compliance
description: Erfahren Sie mehr Überkorrektur Aktionen in automatisierten Ermittlungs-und Antwortfunktionen in Office 365 Advanced Threat Protection-Plan 2.
ms.openlocfilehash: 0db49a28fb90bcddcdd874ac54216957e4be5fa1
ms.sourcegitcommit: 45ee610a380db113c2a50f6ea82d30137498babb
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/27/2020
ms.locfileid: "42288513"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="e56c8-104">Behebungsaktionen nach einer automatisierten Untersuchung in Office 365</span><span class="sxs-lookup"><span data-stu-id="e56c8-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="e56c8-105">Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="e56c8-105">Remediation actions</span></span>

<span data-ttu-id="e56c8-106">Zu den [automatisierten Ermittlungs-und Antwortfunktionen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection gehören bestimmte Korrekturaktionen.</span><span class="sxs-lookup"><span data-stu-id="e56c8-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) in Office 365 Advanced Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="e56c8-107">Wenn eine automatische Untersuchung ausgeführt wird oder abgeschlossen ist, wird in der Regel eine oder mehrere Korrekturaktionen angezeigt, die von Ihrem Sicherheits Betriebsteam genehmigt werden müssen, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="e56c8-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="e56c8-108">In der folgenden Tabelle sind die derzeit in [Office 365 Advanced Threat Protection](office-365-atp.md)verfügbaren Korrekturaktionen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="e56c8-108">The following table summarizes remediation actions currently available in [Office 365 Advanced Threat Protection](office-365-atp.md).</span></span> 

|<span data-ttu-id="e56c8-109">Aktion</span><span class="sxs-lookup"><span data-stu-id="e56c8-109">Action</span></span> | <span data-ttu-id="e56c8-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="e56c8-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="e56c8-111">URL blockieren (Zeitpunkt des Klickens)</span><span class="sxs-lookup"><span data-stu-id="e56c8-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="e56c8-112">Schutz vor e-Mails und Dokumenten, die bösartige URLs enthalten.</span><span class="sxs-lookup"><span data-stu-id="e56c8-112">Protect against emails and documents that contain malicious URLs.</span></span> <span data-ttu-id="e56c8-113">Auf diese Weise können böswillige Links und Verwandte Webseiten über [sichere Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) blockiert werden, wenn der Benutzer auf einen Link in einer vorhandenen Office-Datei oder in einer älteren e-Mail-Nachricht klickt.</span><span class="sxs-lookup"><span data-stu-id="e56c8-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="e56c8-114">Weiche e-Mail löschen</span><span class="sxs-lookup"><span data-stu-id="e56c8-114">Soft delete email</span></span>  |<span data-ttu-id="e56c8-115">Weiche Löschen bestimmter e-Mail-Nachrichten aus dem Postfach eines Benutzers</span><span class="sxs-lookup"><span data-stu-id="e56c8-115">Soft delete specific email messages from a user's mailbox</span></span>|
|<span data-ttu-id="e56c8-116">E-Mail-Cluster mit Soft Delete</span><span class="sxs-lookup"><span data-stu-id="e56c8-116">Soft delete email clusters</span></span>  |<span data-ttu-id="e56c8-117">Soft Delete böswillige e-Mail-Nachrichten, die einer Abfrage aus den Postfächern aller Benutzer entsprechen</span><span class="sxs-lookup"><span data-stu-id="e56c8-117">Soft delete malicious email messages matching a query from all users' mailboxes</span></span>|
|<span data-ttu-id="e56c8-118">Externe E-Mail-Weiterleitung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="e56c8-118">Turn off external mail forwarding</span></span> |<span data-ttu-id="e56c8-119">Entfernt die Weiterleitungsregel aus dem Postfach eines bestimmten Endbenutzers.</span><span class="sxs-lookup"><span data-stu-id="e56c8-119">Removes forwarding rule from a specific end user's mailbox</span></span>|

## <a name="approve-or-reject-pending-actions"></a><span data-ttu-id="e56c8-120">Genehmigen (oder ablehnen) Ausstehende Aktionen</span><span class="sxs-lookup"><span data-stu-id="e56c8-120">Approve (or reject) pending actions</span></span>

![Seite "Luft Ermittlungsaktionen"](../../media/air-investigationactionspage.png)

<span data-ttu-id="e56c8-122">Während Sie die [Details einer Untersuchung](air-view-investigation-results.md)anzeigen, können Sie alle ausstehenden Korrekturaktionen genehmigen oder ablehnen.</span><span class="sxs-lookup"><span data-stu-id="e56c8-122">While viewing the [details of an investigation](air-view-investigation-results.md), you can approve or reject any pending remediation actions.</span></span> <span data-ttu-id="e56c8-123">Wir empfehlen, dies so schnell wie möglich zu tun, damit Ihre automatisierten Untersuchungen abgeschlossen werden.</span><span class="sxs-lookup"><span data-stu-id="e56c8-123">We recommend doing this as soon as possible so that your automated investigations complete.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e56c8-124">Geeignete Berechtigungen sind erforderlich, um Korrekturaktionen zu genehmigen oder abzulehnen.</span><span class="sxs-lookup"><span data-stu-id="e56c8-124">Appropriate permissions are required to approve or reject remediation actions.</span></span> <span data-ttu-id="e56c8-125">Siehe [erforderliche Berechtigungen für die Verwendung von Air-Funktionen](office-365-air.md#required-permissions-to-use-air-capabilities).</span><span class="sxs-lookup"><span data-stu-id="e56c8-125">See [Required permissions to use AIR capabilities](office-365-air.md#required-permissions-to-use-air-capabilities).</span></span>

1. <span data-ttu-id="e56c8-126">Klicken Sie auf die Registerkarte **Aktionen** .</span><span class="sxs-lookup"><span data-stu-id="e56c8-126">Select the **Actions** tab.</span></span>

2. <span data-ttu-id="e56c8-127">W?hlen Sie ein Element in der Liste aus.</span><span class="sxs-lookup"><span data-stu-id="e56c8-127">Select an item in the list.</span></span> <span data-ttu-id="e56c8-128">(Dadurch werden die Schaltflächen genehmigen und ablehnen aktiviert.)</span><span class="sxs-lookup"><span data-stu-id="e56c8-128">(This activates the Approve and Reject buttons.)</span></span>

3. <span data-ttu-id="e56c8-129">Überprüfen Sie die verfügbaren Informationen für die ausgewählten Elemente, und genehmigen oder lehnen Sie die Aktion (en) dann entweder ab.</span><span class="sxs-lookup"><span data-stu-id="e56c8-129">Review available information for the item(s) you selected, and then either approve or reject the action(s).</span></span> 
 - <span data-ttu-id="e56c8-130">Mit **genehmigen** kann die Wiederherstellung beginnen.</span><span class="sxs-lookup"><span data-stu-id="e56c8-130">**Approve** allows remediation to begin.</span></span>
 - <span data-ttu-id="e56c8-131">**Reject** nimmt keine weiteren Aktionen vor</span><span class="sxs-lookup"><span data-stu-id="e56c8-131">**Reject** takes no further action</span></span>

## <a name="next-steps"></a><span data-ttu-id="e56c8-132">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="e56c8-132">Next steps</span></span>

- [<span data-ttu-id="e56c8-133">Informationen zum kompromittierten Textbuch für Benutzersicherheit</span><span class="sxs-lookup"><span data-stu-id="e56c8-133">Learn about the compromised user security playbook</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/address-compromised-users-quickly)

- [<span data-ttu-id="e56c8-134">Anzeigen Ihrer ATP-Berichte</span><span class="sxs-lookup"><span data-stu-id="e56c8-134">View your ATP reports</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/view-reports-for-atp)