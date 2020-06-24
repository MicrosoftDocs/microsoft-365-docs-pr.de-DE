---
title: Verwenden Sie Exchange Online und das Security & Compliance Center, um die SEC-Richtlinie 17a-4 einzuhalten
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Konfigurieren Sie Exchange Online & Compliance Center, um den behördlichen Bestimmungen von CFTC Regel 1.31(c)-(d), FINRA Regel 4511 und SEC Regel 17a-4 gerecht zu werden.
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.openlocfilehash: 6dc53ec9dd016a2423ca96886bba400e2f17e17a
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819075"
---
# <a name="use-exchange-online-and-the-security--compliance-center-to-comply-with-sec-rule-17a-4"></a><span data-ttu-id="75a7b-103">Verwenden Sie Exchange Online und das Security & Compliance Center, um die SEC-Richtlinie 17a-4 einzuhalten</span><span class="sxs-lookup"><span data-stu-id="75a7b-103">Use Exchange Online and the Security & Compliance Center to comply with SEC Rule 17a-4</span></span>

><span data-ttu-id="75a7b-104">*[Microsoft 365-Lizenzierungsleitfaden für Sicherheit und Compliance](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="75a7b-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="75a7b-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="75a7b-105">If your organization needs to comply with regulatory standards for retaining your data, the Security & Compliance Center provides features to manage the lifecycle of your data in Exchange Online.</span></span> <span data-ttu-id="75a7b-106">This includes the ability to retain, audit, search, and export your data.</span><span class="sxs-lookup"><span data-stu-id="75a7b-106">This includes the ability to retain, audit, search, and export your data.</span></span> <span data-ttu-id="75a7b-107">These capabilities are sufficient to meet the needs of most organizations.</span><span class="sxs-lookup"><span data-stu-id="75a7b-107">These capabilities are sufficient to meet the needs of most organizations.</span></span>

<span data-ttu-id="75a7b-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span><span class="sxs-lookup"><span data-stu-id="75a7b-108">However, some organizations in highly regulated industries are subject to more stringent regulatory requirements.</span></span> <span data-ttu-id="75a7b-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span><span class="sxs-lookup"><span data-stu-id="75a7b-109">For example, financial institutions such as banks or broker dealers are subject to Rule 17a-4 issued by the Securities and Exchange Commission (SEC).</span></span> <span data-ttu-id="75a7b-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span><span class="sxs-lookup"><span data-stu-id="75a7b-110">Rule 17a-4 has specific requirements for electronic data storage, including many aspects of record management, such as the duration, format, quality, availability, and accountability of records retention.</span></span>

<span data-ttu-id="75a7b-111">Damit diese Organisationen besser verstehen, wie das Security & Compliance Center genutzt werden kann, um ihre gesetzlichen Auflagen für Exchange Online einzuhalten, insbesondere in Bezug auf die Anforderungen der Richtlinie 17a-4, haben wir in Zusammenarbeit mit Cohasset Associates eine Bewertung veröffentlicht.</span><span class="sxs-lookup"><span data-stu-id="75a7b-111">To help these organizations better understand how the Security & Compliance Center can be leveraged to meet their regulatory obligations for Exchange Online, specifically in relation to Rule 17a-4 requirements, we have released an assessment in partnership with Cohasset Associates.</span></span>

<span data-ttu-id="75a7b-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span><span class="sxs-lookup"><span data-stu-id="75a7b-112">Cohasset validated that when Exchange Online and the Security & Compliance Center are configured as recommended, they meet the relevant storage requirements of CFTC Rule 1.31(c)-(d), FINRA Rule 4511, and SEC Rule 17a-4.</span></span> <span data-ttu-id="75a7b-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span><span class="sxs-lookup"><span data-stu-id="75a7b-113">We targeted this set of rules because they represent the most prescriptive guidance globally for records retention for financial institutions.</span></span>

## <a name="download-the-cohasset-assessment"></a><span data-ttu-id="75a7b-114">Die Bewertung von Cohasset herunterladen</span><span class="sxs-lookup"><span data-stu-id="75a7b-114">Download the Cohasset assessment</span></span>

<span data-ttu-id="75a7b-115">Sie können [hier die Bewertung von Cohasset herunterladen](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span><span class="sxs-lookup"><span data-stu-id="75a7b-115">You can [download the Cohasset assessment here](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9fa8349d-a0c9-47d9-93ad-472aa0fa44ec&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers).</span></span>

![Titelseite für die Bewertung von Cohasset Associates zum Herunterladen](../media/cohasset-associates-assessment.png)

## <a name="this-assessment-is-specific-to-exchange-online"></a><span data-ttu-id="75a7b-117">Diese Bewertung ist beschränkt auf Exchange Online</span><span class="sxs-lookup"><span data-stu-id="75a7b-117">This assessment is specific to Exchange Online</span></span>

<span data-ttu-id="75a7b-118">Note that this assessment is specific to Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="75a7b-118">Note that this assessment is specific to Exchange Online.</span></span> <span data-ttu-id="75a7b-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span><span class="sxs-lookup"><span data-stu-id="75a7b-119">The assessment does not include other Microsoft 365 services such as SharePoint Online or OneDrive for Business, although we are planning support for those services with respect to SEC 17a-4 in the future.</span></span>

<span data-ttu-id="75a7b-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="75a7b-120">It's important to understand that Skype for Business and Teams also store data in Exchange Online.</span></span> <span data-ttu-id="75a7b-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span><span class="sxs-lookup"><span data-stu-id="75a7b-121">Therefore, the assessment does cover messages from Skype for Business and channel and chat messages from Teams.</span></span>

## <a name="using-preservation-lock-is-key-to-the-recommended-configuration"></a><span data-ttu-id="75a7b-122">Die Verwendung der Erhaltungssperre ist für die empfohlene Konfiguration essentiell</span><span class="sxs-lookup"><span data-stu-id="75a7b-122">Using Preservation Lock is key to the recommended configuration</span></span>

<span data-ttu-id="75a7b-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span><span class="sxs-lookup"><span data-stu-id="75a7b-123">Highly regulated industries are often required to store electronic communications to meet the WORM (write once, read many) requirement.</span></span> <span data-ttu-id="75a7b-124">The WORM requirement dictates a storage solution in which a record must be:</span><span class="sxs-lookup"><span data-stu-id="75a7b-124">The WORM requirement dictates a storage solution in which a record must be:</span></span>

- <span data-ttu-id="75a7b-125">Sie müssen über einen erforderlichen Aufbewahrungszeitraum gespeichert werden, der nicht verkürzt sondern nur verlängert werden kann.</span><span class="sxs-lookup"><span data-stu-id="75a7b-125">Retained for a required retention period that cannot be shortened, only increased.</span></span>
- <span data-ttu-id="75a7b-126">Sie müssen unveränderlich sein, d. h. Datensätze können während des erforderlichen Aufbewahrungszeitraums nicht überschrieben, gelöscht oder geändert werden.</span><span class="sxs-lookup"><span data-stu-id="75a7b-126">Immutable, meaning that the record cannot be overwritten, erased, or altered during the required retention period.</span></span>

<span data-ttu-id="75a7b-127">In Exchange Online, when a [retention policy](retention-policies.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span><span class="sxs-lookup"><span data-stu-id="75a7b-127">In Exchange Online, when a [retention policy](retention-policies.md) is applied to a user's mailbox, all the user's content will be retained based on the criteria of the policy.</span></span> <span data-ttu-id="75a7b-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span><span class="sxs-lookup"><span data-stu-id="75a7b-128">In fact, if a user attempts to delete or modify an email, a copy of the email before the change is made will be preserved in a secure, hidden location in the user's mailbox.</span></span> <span data-ttu-id="75a7b-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span><span class="sxs-lookup"><span data-stu-id="75a7b-129">Retention policies can help ensure that an organization retains electronic communications, but those policies can be modified.</span></span>

<span data-ttu-id="75a7b-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span><span class="sxs-lookup"><span data-stu-id="75a7b-130">By placing a Preservation Lock on a retention policy, an organization ensures that the policy cannot be modified.</span></span> <span data-ttu-id="75a7b-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span><span class="sxs-lookup"><span data-stu-id="75a7b-131">In fact, after a Preservation Lock is applied to a retention policy, the following actions are restricted:</span></span>

- <span data-ttu-id="75a7b-132">Die in der Richtlinie enthaltene Aufbewahrungsdauer kann nur verlängert, nicht gekürzt werden.</span><span class="sxs-lookup"><span data-stu-id="75a7b-132">The retention period of the policy can only be increased, not shortened.</span></span>
- <span data-ttu-id="75a7b-133">Benutzer können der Richtlinie hinzugefügt werden, jedoch können keine Benutzer entfernt werden.</span><span class="sxs-lookup"><span data-stu-id="75a7b-133">Users can be added to the policy, but no user can be removed.</span></span>
- <span data-ttu-id="75a7b-134">Die Aufbewahrungsrichtlinie kann nicht von einem Administrator gelöscht werden.</span><span class="sxs-lookup"><span data-stu-id="75a7b-134">The retention policy cannot be deleted by an administrator.</span></span>

<span data-ttu-id="75a7b-135">Eine Erhaltungssperre kann Sie bei der Einhaltung der gesetzlichen Bestimmungen der SEC 17a-4 unterstützen.</span><span class="sxs-lookup"><span data-stu-id="75a7b-135">Preservation Lock can help you meet the SEC 17a-4 regulatory requirements.</span></span>

## <a name="how-to-set-up-preservation-lock"></a><span data-ttu-id="75a7b-136">So richten Sie eine Erhaltungssperre ein</span><span class="sxs-lookup"><span data-stu-id="75a7b-136">How to set up Preservation Lock</span></span>

<span data-ttu-id="75a7b-137">Sie können eine Aufbewahrungsrichtlinie nur mithilfe von PowerShell sperren.</span><span class="sxs-lookup"><span data-stu-id="75a7b-137">You can lock a retention policy by using PowerShell.</span></span> <span data-ttu-id="75a7b-138">Weitere Informationen hierzu finden Sie unter [Verwenden der Erhaltungssperre zur Einhaltung gesetzlicher Vorschriften](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span><span class="sxs-lookup"><span data-stu-id="75a7b-138">For more information, see [Use Preservation Lock to comply with regulatory requirements](retention-policies.md#use-preservation-lock-to-comply-with-regulatory-requirements).</span></span>

## <a name="known-limitations"></a><span data-ttu-id="75a7b-139">Bekannte Einschränkungen</span><span class="sxs-lookup"><span data-stu-id="75a7b-139">Known limitations</span></span>

<span data-ttu-id="75a7b-140">Derzeit gibt es einige Einschränkungen für Exchange Online:</span><span class="sxs-lookup"><span data-stu-id="75a7b-140">Currently, there are a few limitations for Exchange Online:</span></span>

- <span data-ttu-id="75a7b-141">Unterhaltungsfäden stehen nicht für Chats und Kanal Nachrichten in Teams zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="75a7b-141">Threaded communications are not available for Teams chat and channel messages.</span></span>
- <span data-ttu-id="75a7b-142">Für Teams Chat- und Kanalnachrichten werden „gefällt mir“-Angaben nicht gespeichert.</span><span class="sxs-lookup"><span data-stu-id="75a7b-142">Likes are not retained for Teams chat and channel messages.</span></span>

> [!NOTE]
> <span data-ttu-id="75a7b-143">Überwachung auf Elementebene für Microsoft 365-Gruppenpostfächer steht jetzt zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="75a7b-143">Item-level auditing is now available for Microsoft 365 group mailboxes.</span></span> <span data-ttu-id="75a7b-144">Weitere Informationen finden Sie unter [Postfachüberwachungen verwalten](enable-mailbox-auditing.md).</span><span class="sxs-lookup"><span data-stu-id="75a7b-144">For more information, see [Manage mailbox auditing](enable-mailbox-auditing.md).</span></span>
