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
description: Erfahren Sie, wie Sie die automatische Weiterleitung von E-Mails beenden.
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903682"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="b75ab-103">Automatische Weiterleitung von E-Mails beenden</span><span class="sxs-lookup"><span data-stu-id="b75ab-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="b75ab-104">Wenn ein Hacker Zugriff auf das Postfach eines Benutzers erhält, kann er die E-Mails des Benutzers automatisch an eine externe Adresse weiterleiten und proprietäre Informationen stehlen.</span><span class="sxs-lookup"><span data-stu-id="b75ab-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="b75ab-105">Sie können dies beenden, indem Sie eine Nachrichtenflussregel erstellen.</span><span class="sxs-lookup"><span data-stu-id="b75ab-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="b75ab-106">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="b75ab-106">Try it!</span></span>

1. <span data-ttu-id="b75ab-107">Wählen Sie Microsoft 365 Admin Center **die** Option Exchange , **Nachrichtenfluss** und auf der Registerkarte Regeln das Pluszeichen aus, und wählen Sie neue Regel **erstellen aus.** </span><span class="sxs-lookup"><span data-stu-id="b75ab-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="b75ab-108">Wählen **Sie Weitere Optionen aus.**</span><span class="sxs-lookup"><span data-stu-id="b75ab-108">Select **More options**.</span></span> <span data-ttu-id="b75ab-109">Nennen Sie Ihre neue Regel.</span><span class="sxs-lookup"><span data-stu-id="b75ab-109">Name your new rule.</span></span>
1. <span data-ttu-id="b75ab-110">Öffnen Sie dann die Dropdownliste, um **diese Regel anzuwenden, wenn**, wählen Sie den **Absender** aus, und ist dann **extern intern**.</span><span class="sxs-lookup"><span data-stu-id="b75ab-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="b75ab-111">Wählen **Sie Innerhalb der Organisation** aus, und klicken Sie dann auf **OK**.</span><span class="sxs-lookup"><span data-stu-id="b75ab-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="b75ab-112">Wählen **Sie Bedingung hinzufügen** aus, öffnen Sie die Dropdownliste, wählen Sie **Nachrichteneigenschaften** aus, und schließen Sie **dann den Nachrichtentyp ein.**</span><span class="sxs-lookup"><span data-stu-id="b75ab-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="b75ab-113">Öffnen Sie **die Dropdownliste Nachrichtentyp** auswählen, wählen **Sie Automatisch weiterleiten** und dann OK **aus.**</span><span class="sxs-lookup"><span data-stu-id="b75ab-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="b75ab-114">Öffnen Sie **die Dropdownliste** Do the following, select **Block the message,** then **reject the message and include an explanation**.</span><span class="sxs-lookup"><span data-stu-id="b75ab-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="b75ab-115">Geben Sie den Nachrichtentext für Ihre Erläuterung ein, und wählen Sie dann **OK aus.**</span><span class="sxs-lookup"><span data-stu-id="b75ab-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="b75ab-116">Scrollen Sie nach unten, und wählen Sie **Speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="b75ab-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="b75ab-117">Ihre Regel wurde erstellt, und Hacker können Nachrichten nicht mehr automatisch weiterleiten.</span><span class="sxs-lookup"><span data-stu-id="b75ab-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="b75ab-118">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="b75ab-118">Related content</span></span>

<span data-ttu-id="b75ab-119">[Hinzufügen eines weiteren E-Mail-Alias](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) für einen Benutzer (Artikel) Konfigurieren der E-Mail-Weiterleitung [in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (Artikel) Suchen und Beheben von Problemen bei der E-Mail-Zustellung als [Office 365 business admin](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="b75ab-119">[Add another email alias for a user](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) (article) [Configure email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (article) [Find and fix email delivery issues as an Office 365 for business admin](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>