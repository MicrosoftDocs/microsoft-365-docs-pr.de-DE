---
title: Automatische Weiterleitung von E-Mails beenden
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie die automatische Weiterleitung von E-Mails beenden.
ms.openlocfilehash: ebbe37ab5c4a60c6ac4b6ebf8877247199460fa1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925886"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="ffbbc-103">Beenden der automatischen E-Mail-Weiterleitung</span><span class="sxs-lookup"><span data-stu-id="ffbbc-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="ffbbc-104">Wenn ein Hacker Zugriff auf das Postfach eines Benutzers erhält, kann er die E-Mails des Benutzers automatisch an eine externe Adresse weiterleiten und proprietäre Informationen stehlen.</span><span class="sxs-lookup"><span data-stu-id="ffbbc-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="ffbbc-105">Sie können dies beenden, indem Sie eine Nachrichtenflussregel erstellen.</span><span class="sxs-lookup"><span data-stu-id="ffbbc-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="ffbbc-106">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="ffbbc-106">Try it!</span></span>

1. <span data-ttu-id="ffbbc-107">Wählen Sie im Microsoft 365 Admin Center **Exchange,** Nachrichtenfluss **und** auf der Registerkarte "Regeln" das Pluszeichen aus, und wählen Sie eine **neue Regel aus.** </span><span class="sxs-lookup"><span data-stu-id="ffbbc-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="ffbbc-108">Wählen Sie **weitere Optionen aus.**</span><span class="sxs-lookup"><span data-stu-id="ffbbc-108">Select **More options**.</span></span> <span data-ttu-id="ffbbc-109">Benennen Sie die neue Regel.</span><span class="sxs-lookup"><span data-stu-id="ffbbc-109">Name your new rule.</span></span>
1. <span data-ttu-id="ffbbc-110">Öffnen Sie dann die Dropdownliste, um **diese Regel anzuwenden, wenn**, wählen Sie **den** Absender aus, und ist dann **extern intern**.</span><span class="sxs-lookup"><span data-stu-id="ffbbc-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="ffbbc-111">Wählen **Sie innerhalb der Organisation** und dann **OK** aus.</span><span class="sxs-lookup"><span data-stu-id="ffbbc-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="ffbbc-112">Choose **add condition**, open the drop-down, select The message **properties**, then include the **message type**.</span><span class="sxs-lookup"><span data-stu-id="ffbbc-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="ffbbc-113">Öffnen Sie **die Dropdownliste "Nachrichtentyp** auswählen", wählen **Sie "Automatische Weiterleitung"** und dann **"OK" aus.**</span><span class="sxs-lookup"><span data-stu-id="ffbbc-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="ffbbc-114">Öffnen Sie **die Dropdownliste** "Do the following", wählen **Sie "Nachricht** blockieren" aus, weisen Sie dann die Nachricht **zurück, und fügen Sie eine Erklärung ein.**</span><span class="sxs-lookup"><span data-stu-id="ffbbc-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="ffbbc-115">Geben Sie den Meldungstext für Ihre Erklärung ein, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="ffbbc-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="ffbbc-116">Scrollen Sie nach unten, und wählen Sie **"Speichern" aus.**</span><span class="sxs-lookup"><span data-stu-id="ffbbc-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="ffbbc-117">Ihre Regel wurde erstellt, und Hacker können Nachrichten nicht mehr automatisch weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="ffbbc-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>