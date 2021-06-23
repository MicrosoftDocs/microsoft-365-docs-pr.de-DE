---
title: Grundlagen von Bedrohungs-Explorer und Echtzeiterkennungen in Microsoft Defender für Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: Verwenden Sie Explorer- oder Echtzeiterkennungen, um Bedrohungen effizient zu untersuchen und darauf zu reagieren.
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083188"
---
# <a name="explorer-and-real-time-detections-basics"></a><span data-ttu-id="6da69-103">Grundlagen der Explorer- und Echtzeiterkennung</span><span class="sxs-lookup"><span data-stu-id="6da69-103">Explorer and Real-time detections basics</span></span>

<span data-ttu-id="6da69-104">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="6da69-104">**Applies to**</span></span>
- [<span data-ttu-id="6da69-105">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="6da69-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="6da69-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="6da69-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="6da69-107">Inhalt dieses Artikels:</span><span class="sxs-lookup"><span data-stu-id="6da69-107">In this article:</span></span>

- [<span data-ttu-id="6da69-108">Unterschiede zwischen Explorer- und Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="6da69-108">Differences between Explorer and Real-time detections</span></span>](#differences-between-explorer-and-real-time-detections)
- [<span data-ttu-id="6da69-109">Erforderliche Lizenzen und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6da69-109">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="6da69-110">Dies ist Teil einer **Drei-Artikel-Reihe** zu **Explorer (auch bekannt als Bedrohungs-Explorer),** **E-Mail-Sicherheit** und **Explorer- und Echtzeiterkennungsgrundlagen** (z. B. Unterschiede zwischen den Tools und berechtigungen, die zum Betrieb erforderlich sind).</span><span class="sxs-lookup"><span data-stu-id="6da69-110">This is part of a **3-article series** on **Explorer (also known as Threat Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="6da69-111">Die beiden anderen Artikel dieser Reihe sind [die Bedrohungssuche im Explorer](threat-hunting-in-threat-explorer.md) und die [E-Mail-Sicherheit mit Explorer.](email-security-in-microsoft-defender.md)</span><span class="sxs-lookup"><span data-stu-id="6da69-111">The other two articles in this series are [Threat hunting in Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="6da69-112">In diesem Artikel wird der Unterschied zwischen Explorer- und Echtzeiterkennungsberichten sowie den erforderlichen Lizenzen und Berechtigungen erläutert.</span><span class="sxs-lookup"><span data-stu-id="6da69-112">This article explains the difference between Explorer and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="6da69-113">Wenn Ihre Organisation [über Microsoft Defender für Office 365](defender-for-office-365.md)verfügt und Sie über die [Berechtigungen](#required-licenses-and-permissions)verfügen, können Sie **Explorer** (auch als **Bedrohungs-Explorer** bezeichnet) oder **Echtzeiterkennungen** verwenden, um Bedrohungen zu erkennen und zu beheben.</span><span class="sxs-lookup"><span data-stu-id="6da69-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** (also known as **Threat Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="6da69-114">Wechseln Sie im Microsoft 365 Defender-Portal ( <https://security.microsoft.com> ) zu **E-Mail & Zusammenarbeit,** und wählen Sie dann **Explorer-** _oder_ **Echtzeiterkennungen aus.**</span><span class="sxs-lookup"><span data-stu-id="6da69-114">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<span data-ttu-id="6da69-115">Mit diesen Tools können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="6da69-115">With these tools, you can:</span></span>

- <span data-ttu-id="6da69-116">Sehen Sie sich Schadsoftware an, die von Microsoft 365 Sicherheitsfeatures erkannt wurde.</span><span class="sxs-lookup"><span data-stu-id="6da69-116">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="6da69-117">Zeigen Sie die Phishing-URL an, und klicken Sie auf Bewertungsdaten.</span><span class="sxs-lookup"><span data-stu-id="6da69-117">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="6da69-118">Starten Sie einen automatisierten Untersuchungs- und Reaktionsprozess aus einer Ansicht im Explorer.</span><span class="sxs-lookup"><span data-stu-id="6da69-118">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="6da69-119">Untersuchen Sie schädliche E-Mails und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="6da69-119">Investigate malicious email, and more.</span></span>

<span data-ttu-id="6da69-120">Weitere Informationen finden Sie unter [E-Mail-Sicherheit mit Explorer](email-security-in-microsoft-defender.md).</span><span class="sxs-lookup"><span data-stu-id="6da69-120">For more information, see [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-explorer-and-real-time-detections"></a><span data-ttu-id="6da69-121">Unterschiede zwischen Explorer- und Echtzeiterkennungen</span><span class="sxs-lookup"><span data-stu-id="6da69-121">Differences between Explorer and Real-time detections</span></span>

- <span data-ttu-id="6da69-122">*Echtzeiterkennungen* sind ein Berichterstellungstool, das in Defender für Office 365 Plan 1 verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6da69-122">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="6da69-123">*Der Bedrohungs-Explorer* ist ein Tool zur Bedrohungssuche und -behebung, das in Defender für Office 365 Plan 2 verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="6da69-123">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="6da69-124">Mit dem Bericht über Echtzeiterkennungen können Sie Erkennungen in Echtzeit anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6da69-124">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="6da69-125">Der Bedrohungs-Explorer tut dies auch, bietet jedoch zusätzliche Details für einen bestimmten Angriff, z. B. das Hervorheben von Angriffskampagnen, und bietet Sicherheitsteams die Möglichkeit, Bedrohungen zu beheben (einschließlich des Auslösens einer [automatisierten Untersuchung und Reaktionsuntersuchung).](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="6da69-125">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="6da69-126">Eine *Ansicht "Alle E-Mails"* ist im Bedrohungs-Explorer verfügbar, aber nicht im Bericht über Echtzeiterkennungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="6da69-126">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="6da69-127">Umfangreiche Filterfunktionen und Korrekturaktionen sind im Bedrohungs-Explorer enthalten.</span><span class="sxs-lookup"><span data-stu-id="6da69-127">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="6da69-128">Weitere Informationen finden Sie unter [Microsoft Defender für Office 365 Dienstbeschreibung: Funktionsverfügbarkeit in Defender für Office 365-Plänen.](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)</span><span class="sxs-lookup"><span data-stu-id="6da69-128">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="6da69-129">Erforderliche Lizenzen und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="6da69-129">Required licenses and permissions</span></span>

<span data-ttu-id="6da69-130">Sie benötigen [Microsoft Defender,](defender-for-office-365.md) damit Office 365 explorer- oder Echtzeiterkennungen verwenden können:</span><span class="sxs-lookup"><span data-stu-id="6da69-130">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="6da69-131">Explorer ist nur in Defender für Office 365 Plan 2 enthalten.</span><span class="sxs-lookup"><span data-stu-id="6da69-131">Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="6da69-132">Der Bericht über Echtzeiterkennungen ist in Defender für Office 365 Plan 1 enthalten.</span><span class="sxs-lookup"><span data-stu-id="6da69-132">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="6da69-133">Sicherheitsteams müssen Lizenzen für alle Benutzer zuweisen, die von Defender für Office 365 geschützt werden sollen, und beachten, dass Explorer- und Echtzeiterkennungen Erkennungsdaten für lizenzierte Benutzer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="6da69-133">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="6da69-134">Zum Anzeigen und Verwenden von Explorer- *oder* Echtzeiterkennungen benötigen Sie die folgenden Berechtigungen:</span><span class="sxs-lookup"><span data-stu-id="6da69-134">To view and use Explorer *or* Real-time detections, you need the following permissions:</span></span>

- <span data-ttu-id="6da69-135">In Defender für Office 365:</span><span class="sxs-lookup"><span data-stu-id="6da69-135">In Defender for Office 365:</span></span>
  - <span data-ttu-id="6da69-136">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="6da69-136">Organization Management</span></span>
  - <span data-ttu-id="6da69-137">Sicherheitsadministrator (kann im Azure Active Directory Admin Center ( ) zugewiesen werden. <https://aad.portal.azure.com></span><span class="sxs-lookup"><span data-stu-id="6da69-137">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="6da69-138">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="6da69-138">Security Reader</span></span>
- <span data-ttu-id="6da69-139">In Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="6da69-139">In Exchange Online:</span></span>
  - <span data-ttu-id="6da69-140">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="6da69-140">Organization Management</span></span>
  - <span data-ttu-id="6da69-141">Organisationsverwaltung – nur Leserechte</span><span class="sxs-lookup"><span data-stu-id="6da69-141">View-Only Organization Management</span></span>
  - <span data-ttu-id="6da69-142">Schreibgeschützte Empfänger</span><span class="sxs-lookup"><span data-stu-id="6da69-142">View-Only Recipients</span></span>
  - <span data-ttu-id="6da69-143">Complianceverwaltung</span><span class="sxs-lookup"><span data-stu-id="6da69-143">Compliance Management</span></span>

<span data-ttu-id="6da69-144">Weitere Informationen zu Rollen und Berechtigungen finden Sie in den folgenden Artikeln:</span><span class="sxs-lookup"><span data-stu-id="6da69-144">To learn more about roles and permissions, see the following articles:</span></span>

- [<span data-ttu-id="6da69-145">Berechtigungen im Microsoft 365 Defender-Portal</span><span class="sxs-lookup"><span data-stu-id="6da69-145">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="6da69-146">Berechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="6da69-146">Permissions in Exchange Online</span></span>](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a><span data-ttu-id="6da69-147">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="6da69-147">More information</span></span>

- [<span data-ttu-id="6da69-148">Bedrohungs-Explorer sammelt E-Mail-Details auf der E-Mail-Entitätsseite</span><span class="sxs-lookup"><span data-stu-id="6da69-148">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="6da69-149">Suchen und Untersuchen von bösartigen E-Mails, die zugestellt wurden</span><span class="sxs-lookup"><span data-stu-id="6da69-149">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="6da69-150">Anzeigen schädlicher Dateien, die in SharePoint Online, OneDrive und Microsoft Teams erkannt wurden</span><span class="sxs-lookup"><span data-stu-id="6da69-150">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="6da69-151">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="6da69-151">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="6da69-152">Automatische Untersuchung und Reaktion in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="6da69-152">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
