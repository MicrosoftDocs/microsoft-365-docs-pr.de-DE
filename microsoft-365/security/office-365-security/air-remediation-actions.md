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
ms.openlocfilehash: 1dff52fe1bdab364e03bc42afc84c9b54696ccf5
ms.sourcegitcommit: 58c1b4208a5e231463091573e40696d08fc39b8e
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/25/2020
ms.locfileid: "42955533"
---
# <a name="remediation-actions-following-an-automated-investigation-in-office-365"></a><span data-ttu-id="6b3d9-104">Behebungsaktionen nach einer automatisierten Untersuchung in Office 365</span><span class="sxs-lookup"><span data-stu-id="6b3d9-104">Remediation actions following an automated investigation in Office 365</span></span>

## <a name="remediation-actions"></a><span data-ttu-id="6b3d9-105">Wartungsaktionen</span><span class="sxs-lookup"><span data-stu-id="6b3d9-105">Remediation actions</span></span>

<span data-ttu-id="6b3d9-106">Zu den [automatischen Ermittlungs-und Antwortfunktionen](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (Air) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 gehören bestimmte Korrekturaktionen.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-106">[Automated investigation and response capabilities](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) in [Office 365 Advanced Threat Protection](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) (Office 365 ATP) Plan 2 include certain remediation actions.</span></span> <span data-ttu-id="6b3d9-107">Wenn eine automatische Untersuchung ausgeführt wird oder abgeschlossen ist, wird in der Regel eine oder mehrere Korrekturaktionen angezeigt, die von Ihrem Sicherheits Betriebsteam genehmigt werden müssen, um den Vorgang fortzusetzen.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-107">Whenever an automated investigation is running or has completed, you'll typically see one or more remediation actions that require approval by your security operations team to proceed.</span></span> 

<span data-ttu-id="6b3d9-108">In der folgenden Tabelle sind die derzeit in Office 365 ATP verfügbaren Korrekturaktionen zusammengefasst.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-108">The following table summarizes the remediation actions that are currently available in Office 365 ATP.</span></span> 

|<span data-ttu-id="6b3d9-109">Aktion</span><span class="sxs-lookup"><span data-stu-id="6b3d9-109">Action</span></span> | <span data-ttu-id="6b3d9-110">Beschreibung</span><span class="sxs-lookup"><span data-stu-id="6b3d9-110">Description</span></span> |
|-----|-----|
|<span data-ttu-id="6b3d9-111">URL blockieren (Zeitpunkt des Klickens)</span><span class="sxs-lookup"><span data-stu-id="6b3d9-111">Block URL (time-of-click)</span></span> |<span data-ttu-id="6b3d9-112">Schützt vor e-Mail-Nachrichten und Dokumenten, die bösartige URLs enthalten.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-112">Protects against email messages and documents that contain malicious URLs.</span></span> <span data-ttu-id="6b3d9-113">Auf diese Weise können böswillige Links und Verwandte Webseiten über [sichere Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) blockiert werden, wenn der Benutzer auf einen Link in einer vorhandenen Office-Datei oder in einer älteren e-Mail-Nachricht klickt.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-113">This enables the blocking of malicious links and any related webpages via [Safe Links](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-safe-links) when the user clicks a link in an existing Office file or in an older email message.</span></span> |
|<span data-ttu-id="6b3d9-114">Weiche e-Mail löschen</span><span class="sxs-lookup"><span data-stu-id="6b3d9-114">Soft delete email</span></span>  |<span data-ttu-id="6b3d9-115">Weiche Löschen bestimmter e-Mail-Nachrichten aus dem Postfach eines Benutzers.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-115">Soft delete specific email messages from a user's mailbox.</span></span> <br/><span data-ttu-id="6b3d9-116">Eine vorläufig gelöschte Nachricht wird in den Ordner "Wiederherstellbare Elemente" des Benutzers verschoben und so lange aufbewahrt, bis der Aufbewahrungszeitraum für gelöschte Elemente abläuft.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-116">A soft-deleted message is moved to a user's Recoverable Items folder and is retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="6b3d9-117">E-Mail-Cluster mit Soft Delete</span><span class="sxs-lookup"><span data-stu-id="6b3d9-117">Soft delete email clusters</span></span>  |<span data-ttu-id="6b3d9-118">Soft Delete böswillige e-Mail-Nachrichten, die einer Abfrage aus den Postfächern aller Benutzer entsprechen.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-118">Soft delete malicious email messages matching a query from all users' mailboxes.</span></span> <br/><span data-ttu-id="6b3d9-119">Vorläufig gelöschte Nachrichten werden in den Ordner "Wiederherstellbare Elemente" der Benutzer verschoben und bis zum Ablauf des Aufbewahrungszeitraums für gelöschte Elemente beibehalten.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-119">Soft-deleted messages are moved to users' Recoverable Items folder and are retained until the deleted item retention period expires.</span></span> |
|<span data-ttu-id="6b3d9-120">Externe E-Mail-Weiterleitung deaktivieren</span><span class="sxs-lookup"><span data-stu-id="6b3d9-120">Turn off external mail forwarding</span></span> |<span data-ttu-id="6b3d9-121">Entfernt eine Weiterleitungsregel aus dem Postfach eines bestimmten Endbenutzers.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-121">Removes a forwarding rule from a specific end user's mailbox.</span></span>|

> [!NOTE]
> <span data-ttu-id="6b3d9-122">In Office 365 ATP werden keine Korrekturaktionen automatisch durchgeführt.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-122">In Office 365 ATP, no remediation actions are taken automatically.</span></span> <span data-ttu-id="6b3d9-123">Korrekturaktionen werden nur nach Genehmigung durch das Sicherheitsteam Ihrer Organisation ausgeführt.</span><span class="sxs-lookup"><span data-stu-id="6b3d9-123">Remediation actions are taken only upon approval by your organization's security team.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="6b3d9-124">Nächste Schritte</span><span class="sxs-lookup"><span data-stu-id="6b3d9-124">Next steps</span></span>

- [<span data-ttu-id="6b3d9-125">Anzeigen ausstehender oder abgeschlossener Korrekturaktionen nach einer automatisierten Untersuchung in Office 365</span><span class="sxs-lookup"><span data-stu-id="6b3d9-125">View pending or completed remediation actions following an automated investigation in Office 365</span></span>](air-review-approve-pending-completed-actions.md)

- [<span data-ttu-id="6b3d9-126">Details und Ergebnisse einer automatisierten Untersuchung in Office 365</span><span class="sxs-lookup"><span data-stu-id="6b3d9-126">Details and results of an automated investigation in Office 365</span></span>](air-view-investigation-results.md)

## <a name="related-articles"></a><span data-ttu-id="6b3d9-127">Verwandte Artikel</span><span class="sxs-lookup"><span data-stu-id="6b3d9-127">Related articles</span></span>

- [<span data-ttu-id="6b3d9-128">Automatisierte Untersuchung in Microsoft Defender Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6b3d9-128">Automated investigation in Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/automated-investigations)

- [<span data-ttu-id="6b3d9-129">Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6b3d9-129">Microsoft Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-threat-protection)