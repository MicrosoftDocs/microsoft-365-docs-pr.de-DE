---
title: Domäne hinzufügen
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
- AdminTemplateSet
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Ihre Organisation benötigt möglicherweise mehrere Domänen, damit Kunden Sie finden können. Erfahren Sie, wie Sie Ihrem Abonnement eine weitere Domäne hinzufügen können.
ms.openlocfilehash: 766d0f6c1e3c68a262bc01ba432e042f0d274ce8
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394845"
---
# <a name="add-another-domain"></a><span data-ttu-id="ecb09-104">Hinzufügen einer weiteren Domäne</span><span class="sxs-lookup"><span data-stu-id="ecb09-104">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="ecb09-105">In Ihrem Unternehmen könnten mehrere Domänennamen für unterschiedliche Zwecke benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="ecb09-105">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="ecb09-106">Beispielsweise könnte es sein, dass Sie eine andere Schreibweise für Ihren Firmennamen hinzufügen möchten, weil Kunden diese bereits verwenden und ihre Mitteilungen bei Ihnen nicht angekommen sind.</span><span class="sxs-lookup"><span data-stu-id="ecb09-106">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="ecb09-107">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="ecb09-107">Try it!</span></span>

1. <span data-ttu-id="ecb09-108">Wählen Sie im Microsoft 365 Admin Center **Einrichten** aus.</span><span class="sxs-lookup"><span data-stu-id="ecb09-108">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="ecb09-109">Wählen Sie unter **Benutzerdefinierte Domäne einrichten** die Option **Anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="ecb09-109">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="ecb09-110">Wählen Sie **Verwalten** und dann **Domäne hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="ecb09-110">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="ecb09-111">Geben Sie den Namen der Domäne ein, die Sie hinzufügen möchten, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ecb09-111">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="ecb09-112">Melden Sie sich bei Ihrer Domänenregistrierungsstelle an, in diesem Fall GoDaddy, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="ecb09-112">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="ecb09-113">Melden Sie sich bei der Registrierungsstelle an, sofern Sie dazu aufgefordert werden, und wählen Sie dann **Autorisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="ecb09-113">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="ecb09-114">Wählen Sie **DNS-Einträge für mich hinzufügen** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="ecb09-114">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="ecb09-115">Wählen Sie die Dienste für Ihre neue Domäne aus, und deaktivieren Sie die Kontrollkästchen für alle Dienste, die von einer anderen Domäne verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="ecb09-115">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="ecb09-116">Wenn Sie beispielsweise die neue Domäne nur für E-Mails verwenden möchten, wählen Sie **Exchange** aus, und deaktivieren Sie die Kontrollkästchen für **Skype for Business** und **Verwaltung mobiler Geräte für Office 365**.</span><span class="sxs-lookup"><span data-stu-id="ecb09-116">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="ecb09-117">Wählen Sie **Weiter**, **Autorisieren**, **Weiter** und dann **Fertigstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="ecb09-117">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="ecb09-118">Ihre neue Domäne wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="ecb09-118">Your new domain has been added.</span></span>

<span data-ttu-id="ecb09-119">Um E-Mails in Ihrer neuen Domäne zu empfangen, müssen Sie für jeden Benutzer einen neuen E-Mail-Alias hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="ecb09-119">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="ecb09-120">Wählen Sie **Benutzer**, **Aktive Benutzer** und dann den Benutzer aus, dem der neue Alias zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="ecb09-120">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="ecb09-121">Wählen Sie **Verwalten von E-Mail-Aliasen** und dann **Alias hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="ecb09-121">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="ecb09-122">Geben Sie den Benutzernamen ein, und wählen Sie dann in der Dropdownliste die neue Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="ecb09-122">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="ecb09-123">Klicken Si auf **Änderungen speichern**, und schließen Sie dann das Fenster.</span><span class="sxs-lookup"><span data-stu-id="ecb09-123">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="ecb09-124">Wiederholen Sie diese Schritte für jeden Benutzer, der E-Mails in der neuen Domäne empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="ecb09-124">Repeat these steps for each user who should receive email at the new domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="ecb09-125">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="ecb09-125">Related content</span></span>

<span data-ttu-id="ecb09-126">[Hinzufügen einer Domäne zu Microsoft 365](../admin/setup/add-domain.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="ecb09-126">[Add a domain to Microsoft 365](../admin/setup/add-domain.md) (article)</span></span>\
<span data-ttu-id="ecb09-127">[Hinzufügen von DNS-Einträgen zum Verbinden Ihrer Domäne](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="ecb09-127">[Add DNS records to connect your domain](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) (article)</span></span>\
<span data-ttu-id="ecb09-128">[Ändern des Namenservers zum Einrichten von Microsoft 365 mit einer beliebigen Domänenregistrierungsstelle](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="ecb09-128">[Change nameservers to set up Microsoft 365 with any domain registrar](../admin/get-help-with-domains/change-nameservers-at-any-domain-registrar.md) (article)</span></span>\
<span data-ttu-id="ecb09-129">[Häufig gestellte Fragen zu Domänen](../admin/setup/domains-faq.yml) (Artikel)</span><span class="sxs-lookup"><span data-stu-id="ecb09-129">[Domains FAQ](../admin/setup/domains-faq.yml) (article)</span></span>