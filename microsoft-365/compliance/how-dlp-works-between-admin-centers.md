---
title: Funktionsweise von DLP mit Security & Compliance Center & Exchange Admin Center
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/19/2019
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: a7e4342a-a0a1-4b43-b166-3d7eecf5d2fd
description: Erfahren Sie, wie DLP im Security & Compliance Center mit DLP und Nachrichtenflussregeln (Transportregeln) im Exchange Admin Center funktioniert.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: cd8a3eb0e7bb859ab9e10551fadd22cc7dcb2a39
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905937"
---
# <a name="how-dlp-works-between-the-security--compliance-center-and-exchange-admin-center"></a><span data-ttu-id="e2296-103">Funktionsweise von DLP zwischen dem Security & Compliance Center und Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="e2296-103">How DLP works between the Security & Compliance Center and Exchange admin center</span></span>

<span data-ttu-id="e2296-104">In Office 365 können Sie eine Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) in zwei verschiedenen Admin Centern erstellen:</span><span class="sxs-lookup"><span data-stu-id="e2296-104">In Office 365, you can create a data loss prevention (DLP) policy in two different admin centers:</span></span>
  
- <span data-ttu-id="e2296-105">Im **Security & Compliance Center** können Sie eine einzelne & erstellen, um Inhalte in SharePoint, OneDrive, Exchange und jetzt Microsoft Teams zu schützen.</span><span class="sxs-lookup"><span data-stu-id="e2296-105">In the **Security & Compliance Center**, you can create a single DLP policy to help protect content in SharePoint, OneDrive, Exchange, and now Microsoft Teams.</span></span> <span data-ttu-id="e2296-106">Wenn möglich, wird empfohlen, hier eine DLP-Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2296-106">When possible, we recommend that you create a DLP policy here.</span></span> <span data-ttu-id="e2296-107">Weitere Informationen finden Sie unter [DLP im Security & Compliance Center](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="e2296-107">For more information, see [DLP in the Security & Compliance Center](data-loss-prevention-policies.md).</span></span>
    
- <span data-ttu-id="e2296-108">Im **Exchange Admin Center** können Sie eine DLP-Richtlinie erstellen, um Inhalte nur in Exchange zu schützen.</span><span class="sxs-lookup"><span data-stu-id="e2296-108">In the **Exchange admin center**, you can create a DLP policy to help protect content only in Exchange.</span></span> <span data-ttu-id="e2296-109">Diese Richtlinie kann Exchange-Nachrichtenflussregeln (auch als Transportregeln bezeichnet) verwenden, sodass sie mehr Optionen für die Verarbeitung von E-Mails bietet.</span><span class="sxs-lookup"><span data-stu-id="e2296-109">This policy can use Exchange mail flow rules (also known as transport rules), so it has more options specific to handling email.</span></span> <span data-ttu-id="e2296-110">Weitere Informationen finden Sie unter [DLP im Exchange Admin Center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span><span class="sxs-lookup"><span data-stu-id="e2296-110">For more information, see [DLP in the Exchange admin center](/exchange/security-and-compliance/data-loss-prevention/data-loss-prevention).</span></span>
    
<span data-ttu-id="e2296-111">In diesen Admin Centern erstellte DLP-Richtlinien funktionieren nebeneinander – in diesem Thema wird die Funktionsweise erläutert.</span><span class="sxs-lookup"><span data-stu-id="e2296-111">DLP polices created in these admin centers work side by side - this topic explains how.</span></span>
  
![DLP-Seiten im Security and Compliance Center und Exchange Admin Center](../media/d3eaa7e7-3b16-457b-bd9c-26707f7b584f.png)
  
## <a name="how-dlp-in-the-security--compliance-center-works-with-dlp-and-mail-flow-rules-in-the-exchange-admin-center"></a><span data-ttu-id="e2296-113">Funktionsweise von DLP im Security & Compliance Center mit DLP- und Nachrichtenflussregeln im Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="e2296-113">How DLP in the Security & Compliance Center works with DLP and mail flow rules in the Exchange admin center</span></span>

<span data-ttu-id="e2296-114">Nachdem Sie eine DLP-Richtlinie im Security & Compliance Center erstellt haben, wird die Richtlinie an allen In der Richtlinie enthaltenen Speicherorten bereitgestellt.</span><span class="sxs-lookup"><span data-stu-id="e2296-114">After you create a DLP policy in the Security & Compliance Center, the policy is deployed to all of the locations included in the policy.</span></span> <span data-ttu-id="e2296-115">Wenn die Richtlinie Exchange Online enthält, wird die Richtlinie dort synchronisiert und auf die gleiche Weise erzwungen wie eine im Exchange Admin Center erstellte DLP-Richtlinie.</span><span class="sxs-lookup"><span data-stu-id="e2296-115">If the policy includes Exchange Online, the policy's synced there and enforced in exactly the same way as a DLP policy created in the Exchange admin center.</span></span> 
  
<span data-ttu-id="e2296-116">Wenn Sie im Exchange Admin Center DLP-Richtlinien erstellt haben, funktionieren diese Richtlinien weiterhin nebeneinander mit allen Richtlinien für E-Mails, die Sie im Security & Compliance Center erstellen.</span><span class="sxs-lookup"><span data-stu-id="e2296-116">If you've created DLP policies in the Exchange admin center, those policies will continue to work side by side with any policies for email that you create in the Security & Compliance Center.</span></span> <span data-ttu-id="e2296-117">Beachten Sie jedoch, dass im Exchange Admin Center erstellte Regeln Vorrang haben.</span><span class="sxs-lookup"><span data-stu-id="e2296-117">But note that rules created in the Exchange admin center take precedence.</span></span> <span data-ttu-id="e2296-118">Alle Exchange-Nachrichtenflussregeln werden zuerst verarbeitet, und dann werden die DLP-Regeln aus dem Security & Compliance Center verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="e2296-118">All Exchange mail flow rules are processed first, and then the DLP rules from the Security & Compliance Center are processed.</span></span>
  
<span data-ttu-id="e2296-119">Dies bedeutet:</span><span class="sxs-lookup"><span data-stu-id="e2296-119">This means that:</span></span>
  
- <span data-ttu-id="e2296-120">Nachrichten, die von Exchange-Nachrichtenflussregeln blockiert werden, werden nicht von im Security & Compliance Center erstellten DLP-Regeln überprüft.</span><span class="sxs-lookup"><span data-stu-id="e2296-120">Messages that are blocked by Exchange mail flow rules won't get scanned by DLP rules created in the Security & Compliance Center.</span></span>
    
- <span data-ttu-id="e2296-121">Wenn eine Exchange-Nachrichtenflussregel eine Nachricht so ändert, dass sie einer DLP-Richtlinie im Security & Compliance Center - z. B. dem Hinzufügen externer Benutzer - zu entsprechen hat, erkennen die DLP-Regeln dies und erzwingen die Richtlinie bei Bedarf.</span><span class="sxs-lookup"><span data-stu-id="e2296-121">If an Exchange mail flow rule modifies a message in a way that causes it to match a DLP policy in the Security & Compliance Center - such as adding external users - then the DLP rules will detect this and enforce the policy as needed.</span></span>
    
<span data-ttu-id="e2296-122">Beachten Sie außerdem, dass sich Exchange-Nachrichtenflussregeln, die die Aktion "Verarbeitung beenden" verwenden, nicht auf die Verarbeitung von DLP-Regeln im Security & Compliance Center auswirken – sie werden weiterhin verarbeitet.</span><span class="sxs-lookup"><span data-stu-id="e2296-122">Also note that Exchange mail flow rules that use the "stop processing" action don't affect the processing of DLP rules in the Security & Compliance Center - they'll still be processed.</span></span>
  
## <a name="policy-tips-in-the-security--compliance-center-vs-the-exchange-admin-center"></a><span data-ttu-id="e2296-123">Richtlinientipps im Security & Compliance Center im Vergleich zum Exchange Admin Center</span><span class="sxs-lookup"><span data-stu-id="e2296-123">Policy tips in the Security & Compliance Center vs. the Exchange admin center</span></span>

<span data-ttu-id="e2296-124">Richtlinientipps können entweder mit im Exchange Admin Center erstellten DLP-Richtlinien und Nachrichtenflussregeln oder mit im Security & Compliance Center erstellten DLP-Richtlinien funktionieren, jedoch nicht mit beiden.</span><span class="sxs-lookup"><span data-stu-id="e2296-124">Policy tips can work either with DLP policies and mail flow rules created in the Exchange admin center, or with DLP policies created in the Security & Compliance Center, but not both.</span></span> <span data-ttu-id="e2296-125">Dies liegt daran, dass diese Richtlinien an unterschiedlichen Speicherorten gespeichert werden, Richtlinientipps können jedoch nur von einem einzigen Speicherort aus zeichnen.</span><span class="sxs-lookup"><span data-stu-id="e2296-125">This is because these policies are stored in different locations, but policy tips can draw only from a single location.</span></span>
  
<span data-ttu-id="e2296-126">Wenn Sie Richtlinientipps im Exchange Admin Center konfiguriert haben, werden alle Richtlinientipps, die Sie im Security & Compliance Center konfigurieren, benutzern in Outlook im Web und Outlook 2013 und höher erst angezeigt, wenn Sie die Tipps im Exchange Admin Center deaktivieren.</span><span class="sxs-lookup"><span data-stu-id="e2296-126">If you've configured policy tips in the Exchange admin center, any policy tips that you configure in the Security & Compliance Center won't appear to users in Outlook on the web and Outlook 2013 and later until you turn off the tips in the Exchange admin center.</span></span> <span data-ttu-id="e2296-127">Dadurch wird sichergestellt, dass Ihre aktuellen Exchange-Nachrichtenflussregeln weiterhin funktionieren, bis Sie zum Security & Compliance Center wechseln.</span><span class="sxs-lookup"><span data-stu-id="e2296-127">This ensures that your current Exchange mail flow rules will continue to work until you choose to switch over to the Security & Compliance Center.</span></span>
  
<span data-ttu-id="e2296-128">Beachten Sie, dass Richtlinientipps zwar nur von einem einzigen Speicherort aus zeichnen können, E-Mail-Benachrichtigungen jedoch immer gesendet werden, auch wenn Sie DLP-Richtlinien sowohl im Security & Compliance Center als auch im Exchange Admin Center verwenden.</span><span class="sxs-lookup"><span data-stu-id="e2296-128">Note that while policy tips can draw only from a single location, email notifications are always sent, even if you're using DLP policies in both the Security & Compliance Center and the Exchange admin center.</span></span>
