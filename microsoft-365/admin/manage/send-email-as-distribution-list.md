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
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a7c98273-067e-4162-b3a1-4ba081796012
description: Senden Sie E-Mails als Verteilerliste in Microsoft 365, sodass ein Mitglied auf eine Nachricht antwortet, die aus der Verteilerliste stammt.
ms.openlocfilehash: c77455b5b990a9c35fc7e47ee81cc9ddef4d0a23
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53392515"
---
# <a name="send-email-as-a-distribution-list"></a><span data-ttu-id="1f8a8-103">Senden von E-Mails als Verteilerliste</span><span class="sxs-lookup"><span data-stu-id="1f8a8-103">Send email as a distribution list</span></span>

<span data-ttu-id="1f8a8-104">In Microsoft 365 können Sie E-Mails als Verteilerliste senden.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-104">In Microsoft 365, you can send email as a distribution list.</span></span> <span data-ttu-id="1f8a8-105">Wenn eine Person, die Mitglied der Verteilerliste ist, auf eine an die Verteilerliste gesendete Nachricht antwortet, sieht es so aus, als ob die E-Mail von der Verteilerliste und nicht vom einzelnen Benutzer stammt.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-105">When a person who is a member of the distribution list replies to a message sent to the distribution list, the email appears to be from the distribution list, not from the individual user.</span></span> <span data-ttu-id="1f8a8-106">In diesem Thema wird gezeigt, wie das geht.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-106">This topic shows you how to do this.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="1f8a8-107">Bevor Sie beginnen:</span><span class="sxs-lookup"><span data-stu-id="1f8a8-107">Before you begin</span></span>

<span data-ttu-id="1f8a8-108">Bevor Sie diese Schritte ausführen, stellen Sie sicher, dass Sie einer Microsoft 365 Verteilerliste hinzugefügt wurden und Ihnen die Berechtigung "Senden als" gewährt wurde.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-108">Before you perform these steps, make sure you've been added to a Microsoft 365 distribution list and you've have been granted Send as permission on it.</span></span>
  
 <span data-ttu-id="1f8a8-109">**Administratoren:** Stellen Sie sicher, dass Sie die Schritte unter ["Hinzufügen eines Microsoft 365 Benutzers oder Kontakts zu einer Liste"](../email/add-user-or-contact-to-distribution-list.md) befolgt haben und Mitgliedern das Senden von [E-Mails als Microsoft 365 Gruppenthemen erlauben,](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) und die richtigen Personen zur Verteilerliste hinzugefügt haben.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-109">**Admins**: Make sure you've followed the steps in the [Add a Microsoft 365 user or contact to a list](../email/add-user-or-contact-to-distribution-list.md) and [Allow members to send email as a Microsoft 365 Group](../../solutions/allow-members-to-send-as-or-send-on-behalf-of-group.md#allow-members-to-send-email-as-a-group) topics, and added the correct people to the distribution list.</span></span>
  
## <a name="outlook-on-the-web"></a><span data-ttu-id="1f8a8-110">Outlook im Web</span><span class="sxs-lookup"><span data-stu-id="1f8a8-110">Outlook on the web</span></span>

1. <span data-ttu-id="1f8a8-111">Öffnen Sie Outlook im Web, und wechseln Sie zu Ihrem Posteingang.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-111">Open Outlook on the web and go to your inbox.</span></span> 
    
2. <span data-ttu-id="1f8a8-112">Öffnen Sie eine an die Verteilerliste gesendete Nachricht.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-112">Open a message that was sent to the distribution list.</span></span> 
    
3. <span data-ttu-id="1f8a8-113">Wählen Sie **"Antworten" aus.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-113">Select **Reply**.</span></span> 
    
4. <span data-ttu-id="1f8a8-114">Wählen Sie unten in der Nachricht **weitere** \> **Anzeigen aus.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-114">At the bottom of the message, select **More** \> **Show from**.</span></span><br/> <span data-ttu-id="1f8a8-115">![Wählen Sie "Mehr" und dann "Aus anzeigen" aus.](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span><span class="sxs-lookup"><span data-stu-id="1f8a8-115">![Select More and then choose Show From](../../media/534f13b7-9f15-48ea-8835-ea2ed1863ece.png)</span></span>
  
5. <span data-ttu-id="1f8a8-116">Klicken Sie mit der rechten Maustaste auf die Absenderadresse , z. B. `Ina@weewalter.me` und wählen Sie **"Entfernen"** aus.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-116">Right-click on the From address - such as `Ina@weewalter.me` - and choose **Remove**.</span></span><br/> <span data-ttu-id="1f8a8-117">![Entfernen des FROM-Alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span><span class="sxs-lookup"><span data-stu-id="1f8a8-117">![Remove the FROM alias](../../media/9b8d8e8f-dc46-499c-89bd-0a480603bf1f.png)</span></span>
  
6. <span data-ttu-id="1f8a8-118">Geben Sie dann die Verteilerlistenadresse ein, z. B. support@contoso.com, und senden Sie die Nachricht.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-118">Then type the distribution list address such as support@contoso.com, and send the message.</span></span> <span data-ttu-id="1f8a8-119">Wenn Sie das nächste Mal aus der Verteilerliste antworten, wird die Adresse als Option in der **Von-Liste** angezeigt.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-119">The next time you reply from the distribution list, its address will appear as an option in the **From** list.</span></span><br/><span data-ttu-id="1f8a8-120">![Alias des freigegebenen Postfachs wird angezeigt](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span><span class="sxs-lookup"><span data-stu-id="1f8a8-120">![Alias of the shared mailbox appears](../../media/f7632a9a-9cab-446c-9e37-23ef50c5b975.png)</span></span>

## <a name="outlook"></a><span data-ttu-id="1f8a8-121">Outlook</span><span class="sxs-lookup"><span data-stu-id="1f8a8-121">Outlook</span></span>

1. <span data-ttu-id="1f8a8-122">Öffnen Sie Outlook Desktopclient.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-122">Open Outlook desktop client.</span></span>

2. <span data-ttu-id="1f8a8-123">Verfassen sie eine neue E-Mail.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-123">Compose a New Email.</span></span> <span data-ttu-id="1f8a8-124">Klicken Sie auf das **Feld "Von",** und wählen Sie **"Andere E-Mail-Adresse"** aus.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-124">Click the **From** field and select **Other email address**.</span></span> <span data-ttu-id="1f8a8-125">Wenn das Feld "Von" nicht angezeigt wird, navigieren Sie zu **"Optionen",** und wählen Sie im Abschnitt "Felder anzeigen" die Option **"Von" aus.**</span><span class="sxs-lookup"><span data-stu-id="1f8a8-125">If you do not see the From field, navigate to **Options** and select **From** in the Show fields section.</span></span>

3. <span data-ttu-id="1f8a8-126">Wählen Sie die Adresse der **Verteilerliste** aus der globalen Adressliste aus.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-126">Select the **Distribution List** address from the Global Address List.</span></span>

4. <span data-ttu-id="1f8a8-127">Senden Sie die E-Mail.</span><span class="sxs-lookup"><span data-stu-id="1f8a8-127">Send the email.</span></span>

## <a name="related-content"></a><span data-ttu-id="1f8a8-128">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="1f8a8-128">Related content</span></span>

<span data-ttu-id="1f8a8-129">[Erstellen, Bearbeiten oder Löschen einer Sicherheitsgruppe im Microsoft 365 Admin Center](../email/create-edit-or-delete-a-security-group.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="1f8a8-129">[Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md) (article)</span></span>\
<span data-ttu-id="1f8a8-130">[E-Mail-Zusammenarbeit](../email/email-collaboration.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="1f8a8-130">[Email collaboration](../email/email-collaboration.md) (article)</span></span>\
<span data-ttu-id="1f8a8-131">[Hinzufügen eines Benutzers oder Kontakts zu einer Verteilergruppe](../email/add-user-or-contact-to-distribution-list.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="1f8a8-131">[Add a user or contact to a distribution group](../email/add-user-or-contact-to-distribution-list.md) (article)</span></span>