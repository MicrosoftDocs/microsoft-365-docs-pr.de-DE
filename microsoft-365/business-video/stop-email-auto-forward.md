---
title: Automatische Weiterleitung von E-Mails beenden
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
description: Erfahren Sie, wie Sie die automatische Weiterleitung von E-Mails beenden, indem Sie eine Nachrichtenflussregel erstellen, um den Diebstahl proprietärer Informationen zu vermeiden.
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706474"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="3cb06-103">Automatische Weiterleitung von E-Mails beenden</span><span class="sxs-lookup"><span data-stu-id="3cb06-103">Stop email auto-forward</span></span>

## <a name="watch-stop-auto-forwarding-emails"></a><span data-ttu-id="3cb06-104">Watch: Beenden der automatischen Weiterleitung von E-Mails</span><span class="sxs-lookup"><span data-stu-id="3cb06-104">Watch: Stop auto-forwarding emails</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="3cb06-105">Wenn ein Hacker Zugriff auf das Postfach eines Benutzers erhält, kann er die E-Mails des Benutzers automatisch an eine externe Adresse weiterleiten und proprietäre Informationen stehlen.</span><span class="sxs-lookup"><span data-stu-id="3cb06-105">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="3cb06-106">Sie können dies beenden, indem Sie eine Nachrichtenflussregel erstellen.</span><span class="sxs-lookup"><span data-stu-id="3cb06-106">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="3cb06-107">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="3cb06-107">Try it!</span></span>

1. <span data-ttu-id="3cb06-108">Wählen Sie Microsoft 365 Admin Center **die** Option Exchange , **Nachrichtenfluss** und auf der Registerkarte Regeln das Pluszeichen aus, und wählen Sie neue Regel **erstellen aus.** </span><span class="sxs-lookup"><span data-stu-id="3cb06-108">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="3cb06-109">Wählen **Sie Weitere Optionen aus.**</span><span class="sxs-lookup"><span data-stu-id="3cb06-109">Select **More options**.</span></span> <span data-ttu-id="3cb06-110">Nennen Sie Ihre neue Regel.</span><span class="sxs-lookup"><span data-stu-id="3cb06-110">Name your new rule.</span></span>
1. <span data-ttu-id="3cb06-111">Öffnen Sie dann die Dropdownliste, um **diese Regel anzuwenden, wenn**, wählen Sie den **Absender** aus, und ist dann **extern intern**.</span><span class="sxs-lookup"><span data-stu-id="3cb06-111">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="3cb06-112">Wählen **Sie Innerhalb der Organisation** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="3cb06-112">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="3cb06-113">Wählen **Sie Bedingung hinzufügen** aus, öffnen Sie die Dropdownliste, wählen Sie **Nachrichteneigenschaften** aus, und schließen Sie **dann den Nachrichtentyp ein.**</span><span class="sxs-lookup"><span data-stu-id="3cb06-113">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="3cb06-114">Öffnen Sie **die Dropdownliste Nachrichtentyp** auswählen, wählen **Sie Automatisch weiterleiten** und dann OK **aus.**</span><span class="sxs-lookup"><span data-stu-id="3cb06-114">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="3cb06-115">Öffnen Sie **die Dropdownliste** Do the following, select **Block the message,** then **reject the message and include an explanation**.</span><span class="sxs-lookup"><span data-stu-id="3cb06-115">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="3cb06-116">Geben Sie den Nachrichtentext für Ihre Erläuterung ein, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="3cb06-116">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="3cb06-117">Scrollen Sie nach unten, und wählen Sie **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="3cb06-117">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="3cb06-118">Ihre Regel wurde erstellt, und Hacker können Nachrichten nicht mehr automatisch weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="3cb06-118">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="3cb06-119">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="3cb06-119">Related content</span></span>

<span data-ttu-id="3cb06-120">[Hinzufügen eines weiteren E-Mail-Alias für einen Benutzer](../admin/email/add-another-email-alias-for-a-user.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="3cb06-120">[Add another email alias for a user](../admin/email/add-another-email-alias-for-a-user.md) (article)</span></span>\
<span data-ttu-id="3cb06-121">[Konfigurieren der E-Mail-Weiterleitung in Microsoft 365](../admin/email/configure-email-forwarding.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="3cb06-121">[Configure email forwarding in Microsoft 365](../admin/email/configure-email-forwarding.md) (article)</span></span>\
<span data-ttu-id="3cb06-122">Suchen und Beheben von Problemen bei der [E-Mail-Zustellung als Office 365 für Geschäftsadministrator](/exchange/troubleshoot/email-delivery/email-delivery-issues) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="3cb06-122">[Find and fix email delivery issues as an Office 365 for business admin](/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>