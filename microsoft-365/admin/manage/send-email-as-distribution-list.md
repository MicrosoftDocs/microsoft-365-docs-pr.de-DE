---
title: Senden von E-Mails als Verteilerliste
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Erfahren Sie, wie Sie E-Mails als Verteilerliste in Microsoft 365 senden.
ms.openlocfilehash: 379f2471fd38da5098bf8f2ca82f4f76ee82bd8e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915158"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="cc00d-103">Senden von E-Mails als Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="cc00d-103">Send email as a distribution list</span></span>

<span data-ttu-id="cc00d-104">In Microsoft 365 können Sie E-Mails als Verteilerliste senden.</span><span class="sxs-lookup"><span data-stu-id="cc00d-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="cc00d-105">Wenn eine Person, die Mitglied der Verteilerliste ist, auf eine an die Verteilerliste gesendete Nachricht antwortet, sieht es so aus, als ob die E-Mail von der Verteilerliste und nicht vom einzelnen Benutzer stammt.</span><span class="sxs-lookup"><span data-stu-id="cc00d-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="cc00d-106">In diesem Thema wird gezeigt, wie das geht.</span><span class="sxs-lookup"><span data-stu-id="cc00d-106">This topic shows you how to do this.</span></span>
  
## <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="cc00d-107">Senden von E-Mails als Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="cc00d-107">Send email as a distribution list</span></span>

<span data-ttu-id="cc00d-108">Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie einer Microsoft 365-Verteilerliste hinzugefügt wurden und Ihnen die Berechtigung Senden als Berechtigung erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="cc00d-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="cc00d-109">**Admins**: Stellen Sie sicher, dass Sie die Schritte unter Hinzufügen eines [Microsoft 365-Benutzers](../email/add-user-or-contact-to-distribution-list.md) oder Kontakts zu einer Liste und Zulassen, dass Mitglieder E-Mails als [Microsoft 365-Gruppenthemen](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) senden, befolgt haben, und die richtigen Personen zur Verteilerliste hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="cc00d-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
1. <span data-ttu-id="cc00d-110">Öffnen Sie Outlook im Web, und wechseln Sie zu Ihrem Posteingang.</span><span class="sxs-lookup"><span data-stu-id="cc00d-110">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="cc00d-111">Öffnen Sie eine an die Verteilerliste gesendete Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cc00d-111">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="cc00d-112">Wählen Sie **Antworten** aus.</span><span class="sxs-lookup"><span data-stu-id="cc00d-112">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="cc00d-113">Wählen Sie unten in der Nachricht **weitere** \> **Anzeigen aus aus.**</span><span class="sxs-lookup"><span data-stu-id="cc00d-113">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="cc00d-114">![Wählen Sie Mehr aus, und wählen Sie dann Aus anzeigen aus.](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="cc00d-114">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="cc00d-115">Klicken Sie mit der rechten Maustaste auf die Von-Adresse , z. B. `Ina@weewalter.me` und wählen Sie Entfernen **aus.**</span><span class="sxs-lookup"><span data-stu-id="cc00d-115">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="cc00d-116">![Entfernen des FROM-Alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="cc00d-116">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="cc00d-117">Geben Sie dann die Verteilerlistenadresse wie support@contoso.com ein, und senden Sie die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="cc00d-117">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="cc00d-118">Wenn Sie das nächste Mal aus der Verteilerliste antworten, wird ihre Adresse als Option in der **Liste Von** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="cc00d-118">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="cc00d-119">![Alias des freigegebenen Postfachs wird angezeigt](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="cc00d-119">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>
