---
title: Grundlagen des Bedrohungs-Explorers und der Echtzeiterkennung in Microsoft Defender für Office 365
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
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300155"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a><span data-ttu-id="e39fd-103">Grundlagen für den Bedrohungs-Explorer und die Echtzeiterkennung</span><span class="sxs-lookup"><span data-stu-id="e39fd-103">Threat Explorer and Real-time detections basics</span></span>

<span data-ttu-id="e39fd-104">Inhalt dieses Artikels:</span><span class="sxs-lookup"><span data-stu-id="e39fd-104">In this article:</span></span>

- [<span data-ttu-id="e39fd-105">Unterschiede zwischen Bedrohungs-Explorer und Echtzeiterkennung</span><span class="sxs-lookup"><span data-stu-id="e39fd-105">Differences between Threat Explorer and Real-time detections</span></span>](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [<span data-ttu-id="e39fd-106">Erforderliche Lizenzen und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e39fd-106">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="e39fd-107">Dies ist Teil einer **3-Artikel-Reihe** über Threat **Explorer (Explorer),** **E-Mail-Sicherheit** **und** Explorer- und Echtzeiterkennungsgrund grundlagen (z. B. Unterschiede zwischen den Tools und Berechtigungen, die für deren Betrieb erforderlich sind).</span><span class="sxs-lookup"><span data-stu-id="e39fd-107">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="e39fd-108">Die anderen beiden Artikel in dieser Reihe sind Die [Bedrohungssuche im Bedrohungs-Explorer](threat-hunting-in-threat-explorer.md) und [E-Mail-Sicherheit mit Dem Bedrohungs-Explorer](email-security-in-microsoft-defender.md).</span><span class="sxs-lookup"><span data-stu-id="e39fd-108">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="e39fd-109">In diesem Artikel wird der Unterschied zwischen bedrohungserkundungs- und Echtzeiterkennungsberichten sowie den erforderlichen Lizenzen und Berechtigungen erläutert.</span><span class="sxs-lookup"><span data-stu-id="e39fd-109">This article explains the difference between threat exploration and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="e39fd-110">**Gilt für**</span><span class="sxs-lookup"><span data-stu-id="e39fd-110">**Applies to**</span></span>
- [<span data-ttu-id="e39fd-111">Microsoft Defender für Office 365 Plan 1 und Plan 2</span><span class="sxs-lookup"><span data-stu-id="e39fd-111">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="e39fd-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e39fd-112">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="e39fd-113">Wenn Ihre Organisation [Microsoft Defender für Office 365](defender-for-office-365.md)hat und Sie über die Berechtigungen verfügen, können Sie den Bedrohungs-Explorer (explorer genannt) oder **Echtzeiterkennungen** verwenden, um Bedrohungen zu erkennen und zu abwehren. [](#required-licenses-and-permissions)  </span><span class="sxs-lookup"><span data-stu-id="e39fd-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Threat Explorer** (called **Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="e39fd-114">Wechseln Sie im **Security & Compliance Center** zu Bedrohungsverwaltung, und wählen Sie dann **Explorer-**  oder **Echtzeiterkennungen aus.** </span><span class="sxs-lookup"><span data-stu-id="e39fd-114">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="e39fd-115">Mit Microsoft Defender für Office 365 Plan 2 sehen Sie:</span><span class="sxs-lookup"><span data-stu-id="e39fd-115">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="e39fd-116">Mit Microsoft Defender für Office 365 Plan 1 sehen Sie:</span><span class="sxs-lookup"><span data-stu-id="e39fd-116">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![Bedrohungs-Explorer](../../media/threatmgmt-explorer.png)|![Echtzeiterkennungen](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="e39fd-119">Mit diesen Tools können Sie folgende Aktionen ausführen:</span><span class="sxs-lookup"><span data-stu-id="e39fd-119">With these tools, you can:</span></span>

- <span data-ttu-id="e39fd-120">Siehe Schadsoftware, die von Microsoft 365 erkannt wird.</span><span class="sxs-lookup"><span data-stu-id="e39fd-120">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="e39fd-121">Zeigen Sie die Phishing-URL an, und klicken Sie auf Diktierdaten.</span><span class="sxs-lookup"><span data-stu-id="e39fd-121">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="e39fd-122">Starten Sie einen automatisierten Untersuchungs- und Reaktionsprozess aus einer Ansicht im Explorer.</span><span class="sxs-lookup"><span data-stu-id="e39fd-122">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="e39fd-123">Untersuchen Sie bösartige E-Mails und vieles mehr.</span><span class="sxs-lookup"><span data-stu-id="e39fd-123">Investigate malicious email, and more.</span></span>

<span data-ttu-id="e39fd-124">Weitere Informationen finden Sie unter [E-Mail-Sicherheit mit Dem Bedrohungs-Explorer](email-security-in-microsoft-defender.md).</span><span class="sxs-lookup"><span data-stu-id="e39fd-124">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="e39fd-125">Unterschiede zwischen Bedrohungs-Explorer und Echtzeiterkennung</span><span class="sxs-lookup"><span data-stu-id="e39fd-125">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="e39fd-126">*Echtzeiterkennungen ist ein Berichterstellungstool,* das in Defender für Office 365 Plan 1 verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e39fd-126">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="e39fd-127">*Threat Explorer* ist ein Tool zur Bedrohungssuche und -behebung, das in Defender for Office 365 Plan 2 verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="e39fd-127">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="e39fd-128">Mit dem Bericht über Echtzeiterkennungen können Sie Erkennungen in Echtzeit anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e39fd-128">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="e39fd-129">Der Bedrohungs-Explorer führt dies ebenfalls aus, bietet jedoch zusätzliche Details für einen bestimmten Angriff, z. B. das [](automated-investigation-response-office.md)Hervorheben von Angriffskampagnen, und bietet Sicherheitsteams die Möglichkeit, Bedrohungen zu be behebung (einschließlich auslösen einer automatisierten Untersuchung und Reaktionsuntersuchung).</span><span class="sxs-lookup"><span data-stu-id="e39fd-129">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="e39fd-130">Eine *Alle-E-Mail-Ansicht* ist im Bedrohungs-Explorer verfügbar, aber nicht im Bericht über Echtzeiterkennungen enthalten.</span><span class="sxs-lookup"><span data-stu-id="e39fd-130">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="e39fd-131">Umfangreiche Filterfunktionen und Korrekturaktionen sind im Bedrohungs-Explorer enthalten.</span><span class="sxs-lookup"><span data-stu-id="e39fd-131">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="e39fd-132">Weitere Informationen finden Sie unter [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span><span class="sxs-lookup"><span data-stu-id="e39fd-132">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="e39fd-133">Erforderliche Lizenzen und Berechtigungen</span><span class="sxs-lookup"><span data-stu-id="e39fd-133">Required licenses and permissions</span></span>

<span data-ttu-id="e39fd-134">Sie müssen [über Microsoft Defender verfügen, Office 365](defender-for-office-365.md) Explorer- oder Echtzeiterkennungen verwenden können:</span><span class="sxs-lookup"><span data-stu-id="e39fd-134">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="e39fd-135">Explorer ist jedoch nur in Defender für Office 365 Plan 2 enthalten.</span><span class="sxs-lookup"><span data-stu-id="e39fd-135">But Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="e39fd-136">Der Bericht "Echtzeiterkennungen" ist in Defender for Office 365 Plan 1 enthalten.</span><span class="sxs-lookup"><span data-stu-id="e39fd-136">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="e39fd-137">Security Operations Teams müssen Lizenzen für alle Benutzer zuweisen, die von Defender for Office 365 geschützt werden sollten, und beachten Sie, dass Explorer- und Echtzeiterkennungen Erkennungsdaten für lizenzierte Benutzer anzeigen.</span><span class="sxs-lookup"><span data-stu-id="e39fd-137">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="e39fd-138">Zum Anzeigen und Verwenden von *Explorer- oder* Echtzeiterkennungen müssen Sie über Folgendes verfügen:</span><span class="sxs-lookup"><span data-stu-id="e39fd-138">To view and use Explorer *or* Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="e39fd-139">Für das Security & Compliance Center:</span><span class="sxs-lookup"><span data-stu-id="e39fd-139">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="e39fd-140">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="e39fd-140">Organization Management</span></span>
  - <span data-ttu-id="e39fd-141">Sicherheitsadministrator (dies kann im Azure Active Directory Admin Center zugewiesen werden ( <https://aad.portal.azure.com> )</span><span class="sxs-lookup"><span data-stu-id="e39fd-141">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="e39fd-142">Sicherheitsleseberechtigter</span><span class="sxs-lookup"><span data-stu-id="e39fd-142">Security Reader</span></span>

- <span data-ttu-id="e39fd-143">Für Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="e39fd-143">For Exchange Online:</span></span>

  - <span data-ttu-id="e39fd-144">Organisationsverwaltung</span><span class="sxs-lookup"><span data-stu-id="e39fd-144">Organization Management</span></span>
  - <span data-ttu-id="e39fd-145">Organisationsverwaltung – nur Leserechte</span><span class="sxs-lookup"><span data-stu-id="e39fd-145">View-Only Organization Management</span></span>
  - <span data-ttu-id="e39fd-146">Schreibgeschützte Empfänger</span><span class="sxs-lookup"><span data-stu-id="e39fd-146">View-Only Recipients</span></span>
  - <span data-ttu-id="e39fd-147">Verwaltung der Richtlinientreue</span><span class="sxs-lookup"><span data-stu-id="e39fd-147">Compliance Management</span></span>

<span data-ttu-id="e39fd-148">Weitere Informationen zu Rollen und Berechtigungen finden Sie in den folgenden Ressourcen:</span><span class="sxs-lookup"><span data-stu-id="e39fd-148">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="e39fd-149">Berechtigungen im Security & Compliance Center</span><span class="sxs-lookup"><span data-stu-id="e39fd-149">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="e39fd-150">Featureberechtigungen in Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e39fd-150">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="e39fd-151">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e39fd-151">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="e39fd-152">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="e39fd-152">More information</span></span>
- [<span data-ttu-id="e39fd-153">Threat Explorer sammelt E-Mail-Details auf der E-Mail-Entitätsseite</span><span class="sxs-lookup"><span data-stu-id="e39fd-153">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="e39fd-154">Suchen und Untersuchen von bösartigen E-Mails, die zugestellt wurden</span><span class="sxs-lookup"><span data-stu-id="e39fd-154">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="e39fd-155">Anzeigen von schädlichen Dateien, die in SharePoint Online, OneDrive und Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e39fd-155">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="e39fd-156">Threat Protection-Statusbericht</span><span class="sxs-lookup"><span data-stu-id="e39fd-156">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="e39fd-157">Automatische Untersuchung und Reaktion in Microsoft Threat Protection</span><span class="sxs-lookup"><span data-stu-id="e39fd-157">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)