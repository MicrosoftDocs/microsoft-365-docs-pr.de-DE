---
title: Senden einer E-Mail als Verteilerliste in Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Erfahren Sie, wie Sie E-Mails als Verteilerliste in Office 365 senden können.
ms.openlocfilehash: f165279cf6cfbedda4f122f453c2321c16f412d3
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42252741"
---
# <a name="send-email-as-a-distribution-list-in-office-365"></a><span data-ttu-id="c09b2-103">Senden einer E-Mail als Verteilerliste in Office 365</span><span class="sxs-lookup"><span data-stu-id="c09b2-103">Send email as a distribution list in Office 365</span></span>

<span data-ttu-id="c09b2-p101">[] In Office 365 können Sie eine E-Mail als Verteilerliste senden. Wenn eine Person, die Mitglied der Verteilerliste ist, auf eine an die Verteilerliste gesendete Nachricht antwortet, sieht es so aus, als ob die E-Mail von der Verteilerliste und nicht vom einzelnen Benutzer stammt. In diesem Thema wird gezeigt, wie das geht.</span><span class="sxs-lookup"><span data-stu-id="c09b2-p101">In Office 365, you can send email as a distribution list. When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user. This topic shows you how to do this.</span></span>
  
## <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="c09b2-107">E-Mail als Verteilerliste senden</span><span class="sxs-lookup"><span data-stu-id="c09b2-107">Send email as a distribution list</span></span>

<span data-ttu-id="c09b2-108">Stellen Sie vor dem Ausführen dieser Schritte sicher, dass Sie einer Office 365 Verteilerliste hinzugefügt wurden und Ihnen die Berechtigung "Senden als" erteilt wurde.</span><span class="sxs-lookup"><span data-stu-id="c09b2-108">Before you perform these steps, make sure you've been added to an Office 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="c09b2-109">**Administratoren**: Stellen Sie sicher, dass Sie die Schritte im Thema [Hinzufügen eines Office 365 Benutzers oder Kontakts zu einer Liste](../email/add-user-or-contact-to-distribution-list.md) und zulassen, dass [Mitglieder e-Mails als Office 365 Gruppen senden können](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) , befolgt haben, und fügen Sie die richtigen Personen zur Verteilerliste hinzu.</span><span class="sxs-lookup"><span data-stu-id="c09b2-109">**Admins**: Make sure you've followed the steps in the [Add an Office 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as an Office 365 Group](../create-groups/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
1. <span data-ttu-id="c09b2-110">Öffnen Sie Outlook im Web, und wechseln Sie zu Ihrem Posteingang.</span><span class="sxs-lookup"><span data-stu-id="c09b2-110">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="c09b2-111">Öffnen Sie eine an die Verteilerliste gesendete Nachricht.</span><span class="sxs-lookup"><span data-stu-id="c09b2-111">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="c09b2-112">Wählen Sie **Antworten**aus.</span><span class="sxs-lookup"><span data-stu-id="c09b2-112">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="c09b2-113">Wählen Sie unten in der Nachricht **mehr** \> **anzeigen aus aus**.</span><span class="sxs-lookup"><span data-stu-id="c09b2-113">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="c09b2-114">![Wählen Sie mehr aus, und wählen Sie dann anzeigen aus](../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="c09b2-114">![Select More and then choose Show From](../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="c09b2-115">Klicken Sie mit der rechten Maustaste auf die von- `Ina@weewalter.me` Adresse-wie-und wählen Sie **Entfernen**aus.</span><span class="sxs-lookup"><span data-stu-id="c09b2-115">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="c09b2-116">![Entfernen des from-Alias](../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="c09b2-116">![Remove the FROM alias](../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="c09b2-117">Geben Sie dann die Verteilerlisten Adresse wie support@contoso.com ein, und senden Sie die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="c09b2-117">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="c09b2-118">Wenn Sie das nächste Mal von der Verteilerliste Antworten, wird Ihre Adresse als Option in der Liste **von** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="c09b2-118">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="c09b2-119">![Alias des freigegebenen Postfachs wird angezeigt](../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="c09b2-119">![Alias of the shared mailbox appears](../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>
  

