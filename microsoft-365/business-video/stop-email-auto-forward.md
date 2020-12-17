---
title: Automatische Weiterleitung von e-Mails beenden
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Hier erfahren Sie, wie Sie e-Mails mit automatischer Weiterleitung beenden.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702020"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="20276-103">Beenden der automatischen e-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="20276-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="20276-104">Wenn ein Hacker Zugriff auf das Postfach eines Benutzers erhält, kann er die e-Mail des Benutzers automatisch an eine externe Adresse weiterleiten und proprietäre Informationen stehlen.</span><span class="sxs-lookup"><span data-stu-id="20276-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="20276-105">Sie können dies beenden, indem Sie eine e-Mail-Fluss Regel erstellen.</span><span class="sxs-lookup"><span data-stu-id="20276-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="20276-106">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="20276-106">Try it!</span></span>

1. <span data-ttu-id="20276-107">Wählen Sie im Microsoft 365 Admin Center **Exchange**, **Nachrichtenfluss** aus, und wählen Sie auf der Registerkarte **Regeln** das Pluszeichen aus, und wählen Sie **neue Regel erstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="20276-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="20276-108">Wählen Sie **Weitere Optionen** aus.</span><span class="sxs-lookup"><span data-stu-id="20276-108">Select **More options**.</span></span> <span data-ttu-id="20276-109">Nennen Sie die neue Regel.</span><span class="sxs-lookup"><span data-stu-id="20276-109">Name your new rule.</span></span>
1. <span data-ttu-id="20276-110">Öffnen Sie dann die Dropdownliste für **diese Regel anwenden, wenn** Sie **den Absender** auswählen und dann **Externe interne**.</span><span class="sxs-lookup"><span data-stu-id="20276-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="20276-111">Wählen Sie **innerhalb der Organisation** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="20276-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="20276-112">Wählen Sie **Bedingung hinzufügen** aus, öffnen Sie die Dropdownliste, wählen Sie **die Nachrichteneigenschaften** aus, und schließen Sie dann **den Nachrichtentyp ein**.</span><span class="sxs-lookup"><span data-stu-id="20276-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="20276-113">Öffnen Sie die Dropdownliste **Nachrichtentyp auswählen** , wählen Sie **automatisch weiterleiten** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="20276-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="20276-114">Öffnen Sie die Dropdownliste **gehen Sie wie folgt** vor, wählen Sie **Nachricht blockieren** aus, **und lehnen Sie die Nachricht ab, und fügen Sie eine Erläuterung hinzu**.</span><span class="sxs-lookup"><span data-stu-id="20276-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="20276-115">Geben Sie den Nachrichtentext für Ihre Erklärung ein, und wählen Sie dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="20276-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="20276-116">Scrollen Sie nach unten, und wählen Sie **Speichern** aus.</span><span class="sxs-lookup"><span data-stu-id="20276-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="20276-117">Ihre Regel wurde erstellt, und Hacker können keine Nachrichten mehr automatisch weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="20276-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>