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
description: Erfahren Sie, wie Sie Ihrem Abonnement eine weitere Domäne hinzufügen.
ms.openlocfilehash: fef3dc06f270b79cc7f9e729b39727c9116b923d
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/04/2021
ms.locfileid: "50423083"
---
# <a name="add-another-domain"></a><span data-ttu-id="5e492-103">Hinzufügen einer weiteren Domäne</span><span class="sxs-lookup"><span data-stu-id="5e492-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="5e492-104">Ihr Unternehmen benötigt möglicherweise mehrere Domänennamen für verschiedene Zwecke.</span><span class="sxs-lookup"><span data-stu-id="5e492-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="5e492-105">Sie können z. B. eine andere Schreibweise Ihres Firmennamens hinzufügen, da Kunden sie bereits verwenden und ihre Kommunikation Sie nicht erreicht hat.</span><span class="sxs-lookup"><span data-stu-id="5e492-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="5e492-106">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="5e492-106">Try it!</span></span>

1. <span data-ttu-id="5e492-107">Wählen Sie im Microsoft 365 Admin Center **Setup aus.**</span><span class="sxs-lookup"><span data-stu-id="5e492-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="5e492-108">Wählen **Sie unter Einrichten Ihrer benutzerdefinierten Domäne die** Option Ansicht **aus.**</span><span class="sxs-lookup"><span data-stu-id="5e492-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="5e492-109">Wählen **Sie Verwalten** und dann Domäne hinzufügen **aus.**</span><span class="sxs-lookup"><span data-stu-id="5e492-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="5e492-110">Geben Sie den neuen Domänennamen ein, den Sie hinzufügen möchten, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="5e492-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="5e492-111">Melden Sie sich bei Ihrer Domänenregistrierungsstelle an, in diesem Fall GoDaddy, und wählen Sie dann **Weiter aus.**</span><span class="sxs-lookup"><span data-stu-id="5e492-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="5e492-112">Wenn Sie dazu aufgefordert werden, melden Sie sich bei Ihrer Registrierungsstelle an, und wählen Sie dann **Autorisieren aus.**</span><span class="sxs-lookup"><span data-stu-id="5e492-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="5e492-113">Wählen **Sie Hinzufügen der DNS-Einträge für mich** aus, und wählen Sie dann Weiter **aus.**</span><span class="sxs-lookup"><span data-stu-id="5e492-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="5e492-114">Wählen Sie die Dienste für Ihre neue Domäne aus, und aktivieren Sie die Kontrollkästchen für alle Dienste, die von einer anderen Domäne verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="5e492-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="5e492-115">Wenn Sie beispielsweise nur die neue Domäne für E-Mails verwenden möchten, wählen Sie **Exchange** aus, und aktivieren Sie die Kontrollkästchen für **Skype for Business** und Mobile Device Management für Office **365**.</span><span class="sxs-lookup"><span data-stu-id="5e492-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="5e492-116">Wählen **Sie Weiter**, **Autorisieren**, **Weiter** und dann Fertig **stellen aus.**</span><span class="sxs-lookup"><span data-stu-id="5e492-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="5e492-117">Ihre neue Domäne wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="5e492-117">Your new domain has been added.</span></span>

<span data-ttu-id="5e492-118">Zum Empfangen von E-Mails in Ihrer neuen Domäne müssen Sie für jeden Benutzer einen neuen E-Mail-Alias hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="5e492-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="5e492-119">Wählen **Sie Benutzer**, **Aktive** Benutzer und dann den Benutzer aus, dem der neue Alias zugewiesen wird.</span><span class="sxs-lookup"><span data-stu-id="5e492-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="5e492-120">Wählen **Sie Verwalten von E-Mail-Aliasen** aus, und fügen Sie dann einen Alias **hinzu.**</span><span class="sxs-lookup"><span data-stu-id="5e492-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="5e492-121">Geben Sie den Benutzernamen ein, und wählen Sie dann in der Dropdownliste die neue Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="5e492-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="5e492-122">Wählen **Sie Änderungen speichern** aus, und schließen Sie das Fenster.</span><span class="sxs-lookup"><span data-stu-id="5e492-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="5e492-123">Wiederholen Sie diese Schritte für jeden Benutzer, der E-Mails in der neuen Domäne empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="5e492-123">Repeat these steps for each user who should receive email at the new domain.</span></span>