---
title: Empfohlene erste Schritte mit DLP-Richtlinienvorlagen
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 8/7/2017
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection:
- M365-security-compliance
localization_priority: Normal
ms.custom:
- seo-marvel-apr2020
description: In diesem Artikel erfahren Sie, wie Sie die empfohlene DLP-Richtlinie (Data Loss Prevention) für Ihre Organisation erstellen und bearbeiten.
ms.openlocfilehash: 9588eabe5dbe2b1e60eaeb6a45eb95cc327383aa
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 06/19/2020
ms.locfileid: "44817634"
---
# <a name="get-started-with-dlp-policy-recommendations"></a><span data-ttu-id="c4e68-103">Empfohlene erste Schritte mit DLP-Richtlinienvorlagen</span><span class="sxs-lookup"><span data-stu-id="c4e68-103">Get started with DLP policy recommendations</span></span>

<span data-ttu-id="c4e68-104">Diese Erkenntnis gesteuerte Empfehlung hilft Ihrer Organisation, vertrauliche Inhalte zu schützen, wenn Sie in Microsoft 365 gespeichert und freigegeben wird, indem Sie darüber informiert werden, wenn eine mögliche Lücke in ihrer DLP-Richtlinien Abdeckung besteht.</span><span class="sxs-lookup"><span data-stu-id="c4e68-104">This insight-driven recommendation helps your organization keep sensitive content secure when it's stored and shared in Microsoft 365 by informing you when there's a possible gap in your DLP policy coverage.</span></span> <span data-ttu-id="c4e68-105">Diese Empfehlung wird auf der **Start** Seite des Security &amp; Compliance Centers angezeigt, wenn Ihre Dokumente eine der fünf häufigsten Arten von vertraulichen Informationen enthalten, die jedoch nicht durch eine Richtlinie zur Verhinderung von Datenverlust (Data Loss Prevention, DLP) geschützt sind.</span><span class="sxs-lookup"><span data-stu-id="c4e68-105">You'll see this recommendation on the **Home** page of the Security &amp; Compliance Center, if your documents contain any of the top-five most common types of sensitive information but aren't protected by a data loss prevention (DLP) policy.</span></span> 
  
<span data-ttu-id="c4e68-106">Sie können dieses Widget verwenden, um schnell eine angepasste DLP-Richtlinie mit nur einem Mausklick oder zwei zu erstellen, und nachdem Sie diese DLP-Richtlinie erstellt haben, ist sie vollständig anpassbar.</span><span class="sxs-lookup"><span data-stu-id="c4e68-106">You can use this widget to quickly create a customized DLP policy in just a click or two, and after you create this DLP policy, it's fully customizable.</span></span> <span data-ttu-id="c4e68-107">Wenn die Empfehlung zunächst nicht angezeigt wird, klicken Sie im unteren Bereich des Abschnitts **empfohlen für Sie** auf **+ mehr** .</span><span class="sxs-lookup"><span data-stu-id="c4e68-107">Note that if you don't see the recommendation at first, try clicking **+More** at the bottom of the **Recommended for you** section.</span></span> 
  
![Widget mit dem Namen "ungeschützte vertrauliche Informationen"](../media/91bc04d2-6eff-4294-8b73-b2d56d26ffc4.png)
  
## <a name="create-the-recommended-dlp-policy"></a><span data-ttu-id="c4e68-109">Erstellen der empfohlenen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="c4e68-109">Create the recommended DLP policy</span></span>

<span data-ttu-id="c4e68-110">Wenn das Widget Ihnen ungeschützte vertrauliche Informationen zeigt, wählen Sie am unteren Rand **Erste Schritte** aus, um schnell eine DLP-Richtlinie zu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4e68-110">When the widget shows you unprotected sensitive information, choose **Get started** at the bottom to quickly create a DLP policy.</span></span> 
  
<span data-ttu-id="c4e68-111">Zum Schutz der vertraulichen Informationen wird diese DLP-Richtlinie wie folgt unterstützt:</span><span class="sxs-lookup"><span data-stu-id="c4e68-111">To help protect the sensitive information, this DLP policy:</span></span>
  
- <span data-ttu-id="c4e68-112">Erkennt, wenn Inhalte in Exchange, SharePoint und OneDrive, die einen der ungeschützten Typen vertraulicher Informationen enthalten, für Personen außerhalb Ihrer Organisation freigegeben werden.</span><span class="sxs-lookup"><span data-stu-id="c4e68-112">Detects when content in Exchange, SharePoint, and OneDrive that contains one of the unprotected types of sensitive information is shared with people outside your organization.</span></span>
    
- <span data-ttu-id="c4e68-113">Generiert detaillierte Aktivitätsberichte, sodass Sie nachverfolgen können, wie wer die Inhalte für Personen außerhalb Ihrer Organisation freigegeben hat.</span><span class="sxs-lookup"><span data-stu-id="c4e68-113">Generates detailed activity reports so that you can track things like who shared the content with people outside your organization and when they did it.</span></span> <span data-ttu-id="c4e68-114">Sie können die [DLP-Berichte](view-the-dlp-reports.md) und [Überwachungsprotokolldaten](search-the-audit-log-in-security-and-compliance.md) (Where **Activity**  =  **DLP**) verwenden, um diese Informationen anzuzeigen.</span><span class="sxs-lookup"><span data-stu-id="c4e68-114">You can use the [DLP reports](view-the-dlp-reports.md) and [audit log data](search-the-audit-log-in-security-and-compliance.md) (where **Activity** = **DLP**) to see this information.</span></span>
    
<span data-ttu-id="c4e68-115">Sie können auch die DLP-Richtlinie festlegen:</span><span class="sxs-lookup"><span data-stu-id="c4e68-115">You can also choose to have the DLP policy:</span></span>
  
- <span data-ttu-id="c4e68-116">Senden Sie eine Vorfall Berichts-e-Mail, wenn Benutzer viele dieser vertraulichen Informationen für Personen außerhalb Ihrer Organisation freigeben.</span><span class="sxs-lookup"><span data-stu-id="c4e68-116">Send you an incident report email when users share a lot of this sensitive information with people outside your organization.</span></span>
    
- <span data-ttu-id="c4e68-117">Fügen Sie dem e-Mail-Vorfall Bericht weitere Benutzer hinzu.</span><span class="sxs-lookup"><span data-stu-id="c4e68-117">Add other users to the email incident report.</span></span>
    
- <span data-ttu-id="c4e68-118">Zeigen Sie einen richtlinientipp an, und senden Sie eine e-Mail-Benachrichtigung an Benutzer, wenn Sie versuchen, diese vertraulichen Informationen für Personen außerhalb Ihrer Organisation freizugeben.</span><span class="sxs-lookup"><span data-stu-id="c4e68-118">Show a policy tip and send an email notification to users when they attempt to share this sensitive information with people outside your organization.</span></span> <span data-ttu-id="c4e68-119">Weitere Informationen zu diesen Optionen finden Sie unter [Senden von e-Mail-Benachrichtigungen und Anzeigen von Richtlinien Tipps für DLP-Richtlinien](use-notifications-and-policy-tips.md).</span><span class="sxs-lookup"><span data-stu-id="c4e68-119">For more information on these options, see [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md).</span></span>
    
<span data-ttu-id="c4e68-120">Wenn Sie diese Optionen später ändern möchten, können Sie die DLP-Richtlinie nach ihrer Erstellung bearbeiten.</span><span class="sxs-lookup"><span data-stu-id="c4e68-120">If you want to change these options later, you can edit the DLP policy after it's created.</span></span> <span data-ttu-id="c4e68-121">Beispielsweise können Sie die Richtlinie restriktiver machen, indem Sie auch Personen daran hindern, Inhalte freizugeben, die vertrauliche Informationen an erster Stelle enthalten-siehe den nächsten Abschnitt.</span><span class="sxs-lookup"><span data-stu-id="c4e68-121">For example, you can make the policy more restrictive by even blocking people from sharing content that contains sensitive information in the first place - see the next section.</span></span>
  
![Einstellungen für das Widget mit dem Namen ungeschützte vertrauliche Informationen](../media/b6106cbd-1bed-4582-aaef-b678de470c9b.png)
  
## <a name="edit-the-recommended-dlp-policy"></a><span data-ttu-id="c4e68-123">Bearbeiten der empfohlenen DLP-Richtlinie</span><span class="sxs-lookup"><span data-stu-id="c4e68-123">Edit the recommended DLP policy</span></span>

<span data-ttu-id="c4e68-124">Nachdem Sie das Widget zum Erstellen einer DLP-Richtlinie verwendet haben, wird die Richtlinie unter **Verhinderung von Datenverlust** auf der Seite **Richtlinie** des Security &amp; Compliance Centers angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c4e68-124">After you use the widget to create a DLP policy, the policy appears under **Data loss prevention** on the **Policy** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="c4e68-125">Standardmäßig wird die Richtlinie **als System empfohlene Richtlinie für die Freigabe vertraulicher Informationen**bezeichnet.</span><span class="sxs-lookup"><span data-stu-id="c4e68-125">By default, the policy is named **System Recommended Policy for Sharing Sensitive Information**.</span></span> <span data-ttu-id="c4e68-126">Diese Richtlinie ist vollständig anpassbar, genauso wie jede DLP-Richtlinie, die Sie selbst von Grund auf neu erstellen.</span><span class="sxs-lookup"><span data-stu-id="c4e68-126">This policy is fully customizable, the same as any DLP policy that you create yourself from scratch.</span></span> <span data-ttu-id="c4e68-127">Wenn Sie beispielsweise entschieden haben, bei der Verwendung des Widgets keine vorfallberichte und Richtlinien Tipps zu aktivieren, können Sie die Richtlinie jederzeit bearbeiten und diese Optionen jederzeit aktivieren.</span><span class="sxs-lookup"><span data-stu-id="c4e68-127">For example, if you decided not to turn on incident reports and policy tips when you used the widget, you can always edit the policy and turn on those options at any time.</span></span>
  
![Vom System empfohlene Richtlinie für die Freigabe vertraulicher Informationen](../media/2fc49f25-ec25-4433-add4-d60f73888f13.png)
  
## <a name="when-the-widget-does-and-does-not-appear"></a><span data-ttu-id="c4e68-129">Wenn das Widget funktioniert und nicht angezeigt wird</span><span class="sxs-lookup"><span data-stu-id="c4e68-129">When the widget does and does not appear</span></span>

<span data-ttu-id="c4e68-130">Das Widget namens **ungeschützte vertrauliche Informationen** wird im Abschnitt **empfohlen für Sie** der **Start** Seite des Security &amp; Compliance Center angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c4e68-130">The widget named **Unprotected Sensitive Information** appears in the **Recommended for you** section of the **Home** page of the Security &amp; Compliance Center.</span></span> 
  
<span data-ttu-id="c4e68-131">Dieses Widget wird nur angezeigt, wenn:</span><span class="sxs-lookup"><span data-stu-id="c4e68-131">This widget appears only when:</span></span>
  
- <span data-ttu-id="c4e68-132">Neue Dokumente, die eine der fünf häufigsten Arten von vertraulichen Informationen enthalten, werden in SharePoint oder OneDrive in den letzten 30 Tagen erkannt.</span><span class="sxs-lookup"><span data-stu-id="c4e68-132">New documents containing any of the five most common types of sensitive information are detected in SharePoint or OneDrive over the past 30 days.</span></span>
    
- <span data-ttu-id="c4e68-133">Diese vertraulichen Informationen sind nicht bereits durch eine vorhandene DLP-Richtlinie geschützt.</span><span class="sxs-lookup"><span data-stu-id="c4e68-133">That sensitive information is not already protected by an existing DLP policy.</span></span>
    
<span data-ttu-id="c4e68-134">Im Gegensatz zu DLP-Richtlinien, die Ihre Daten ständig überprüfen, überprüft diese Empfehlung nach Lücken in ihrer DLP-Richtlinien Abdeckung etwa alle 48 Stunden, sodass nach dem Hochladen neuer Inhalte bis zu zwei Tage dauern kann, bis die Empfehlung angezeigt wird.</span><span class="sxs-lookup"><span data-stu-id="c4e68-134">Unlike DLP policies that are constantly scanning your data, this recommendation scans for gaps in your DLP policy coverage roughly every 48 hours, so after new content is uploaded, it may take up to two days for the recommendation to appear.</span></span>
  
<span data-ttu-id="c4e68-135">Nachdem Sie das Widget zum Erstellen einer empfohlenen DLP-Richtlinie verwendet haben, wird das Widget nicht mehr auf der **Start** Seite angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c4e68-135">Finally, after you use the widget to create a recommended DLP policy, the widget disappears from the **Home** page.</span></span> 
  

