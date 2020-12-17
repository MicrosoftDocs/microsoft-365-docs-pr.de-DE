---
title: Domäne hinzufügen
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
description: Hier erfahren Sie, wie Sie Ihrem Abonnement eine weitere Domäne hinzufügen.
ms.openlocfilehash: 16f6c4e416ede560d69014e320eb32c4453fd3f5
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702168"
---
# <a name="add-another-domain"></a><span data-ttu-id="dbcc5-103">Hinzufügen einer weiteren Domäne</span><span class="sxs-lookup"><span data-stu-id="dbcc5-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="dbcc5-104">Ihr Unternehmen benötigt möglicherweise mehrere Domänennamen für verschiedene Zwecke.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="dbcc5-105">Sie können beispielsweise eine andere Schreibweise Ihres Firmennamens hinzufügen, da Kunden diese bereits verwenden und ihre Kommunikation Sie nicht erreichen konnte.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="dbcc5-106">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="dbcc5-106">Try it!</span></span>

1. <span data-ttu-id="dbcc5-107">Wählen Sie im Microsoft 365 Admin Center die Option **Setup** aus.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="dbcc5-108">Wählen Sie unter **Get Your Custom Domain Setup aus die** Option **View** aus.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="dbcc5-109">Wählen Sie **Verwalten** und dann **Domäne hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="dbcc5-110">Geben Sie den neuen Domänennamen ein, den Sie hinzufügen möchten, und wählen Sie dann **weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="dbcc5-111">Melden Sie sich bei Ihrer Domänenregistrierungsstelle an, in diesem Fall GoDaddy, und wählen Sie dann **weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="dbcc5-112">Wenn Sie dazu aufgefordert werden, melden Sie sich bei Ihrer Registrierungsstelle an, und wählen Sie dann **autorisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="dbcc5-113">Wählen Sie **DNS-Einträge für mich hinzufügen** aus, und wählen Sie dann **weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="dbcc5-114">Wählen Sie die Dienste für die neue Domäne aus, und deaktivieren Sie die Kontrollkästchen für alle Dienste, die von einer anderen Domäne verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="dbcc5-115">Wenn Sie beispielsweise nur die neue Domäne für e-Mail verwenden möchten, wählen Sie **Exchange** aus, und deaktivieren Sie die Kontrollkästchen für **Skype for Business** und **Verwaltung mobiler Geräte für Office 365**.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="dbcc5-116">Wählen Sie **weiter**, **autorisieren**, **weiter** und dann **Fertig stellen** aus.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="dbcc5-117">Ihre neue Domäne wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-117">Your new domain has been added.</span></span>

<span data-ttu-id="dbcc5-118">Wenn Sie e-Mails in ihrer neuen Domäne empfangen möchten, müssen Sie für jeden Benutzer einen neuen e-Mail-Alias hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="dbcc5-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="dbcc5-119">Wählen Sie **Benutzer**, **aktive Benutzer** aus, und wählen Sie dann den Benutzer aus, dem der neue Alias zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="dbcc5-120">Wählen Sie **e-Mail-Aliase verwalten** aus, und fügen Sie dann **einen Alias hinzu**.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="dbcc5-121">Geben Sie den Benutzernamen ein, und wählen Sie dann in der Dropdownliste die neue Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="dbcc5-122">Wählen Sie **Änderungen speichern** aus, und schließen Sie dann das Fenster.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="dbcc5-123">Wiederholen Sie diese Schritte für jeden Benutzer, der e-Mails in der neuen Domäne empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="dbcc5-123">Repeat these steps for each user who should receive email at the new domain.</span></span>