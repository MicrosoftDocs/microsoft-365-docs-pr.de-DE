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
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie Ihrem Abonnement eine weitere Domäne hinzufügen können.
ms.openlocfilehash: a641005913f7dfd866366f0f8065019dd5c17fe8
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903742"
---
# <a name="add-another-domain"></a><span data-ttu-id="2808d-103">Hinzufügen einer weiteren Domäne</span><span class="sxs-lookup"><span data-stu-id="2808d-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="2808d-104">In Ihrem Unternehmen könnten mehrere Domänennamen für unterschiedliche Zwecke benötigt werden.</span><span class="sxs-lookup"><span data-stu-id="2808d-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="2808d-105">Beispielsweise könnte es sein, dass Sie eine andere Schreibweise für Ihren Firmennamen hinzufügen möchten, weil Kunden diese bereits verwenden und ihre Mitteilungen bei Ihnen nicht angekommen sind.</span><span class="sxs-lookup"><span data-stu-id="2808d-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="2808d-106">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="2808d-106">Try it!</span></span>

1. <span data-ttu-id="2808d-107">Wählen Sie im Microsoft 365 Admin Center **Einrichten** aus.</span><span class="sxs-lookup"><span data-stu-id="2808d-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="2808d-108">Wählen Sie unter **Benutzerdefinierte Domäne einrichten** die Option **Anzeigen** aus.</span><span class="sxs-lookup"><span data-stu-id="2808d-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="2808d-109">Wählen Sie **Verwalten** und dann **Domäne hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="2808d-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="2808d-110">Geben Sie den Namen der Domäne ein, die Sie hinzufügen möchten, und klicken Sie auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2808d-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="2808d-111">Melden Sie sich bei Ihrer Domänenregistrierungsstelle an, in diesem Fall GoDaddy, und klicken Sie dann auf **Weiter**.</span><span class="sxs-lookup"><span data-stu-id="2808d-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="2808d-112">Melden Sie sich bei der Registrierungsstelle an, sofern Sie dazu aufgefordert werden, und wählen Sie dann **Autorisieren** aus.</span><span class="sxs-lookup"><span data-stu-id="2808d-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="2808d-113">Wählen Sie **DNS-Einträge für mich hinzufügen** und dann **Weiter** aus.</span><span class="sxs-lookup"><span data-stu-id="2808d-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="2808d-114">Wählen Sie die Dienste für Ihre neue Domäne aus, und deaktivieren Sie die Kontrollkästchen für alle Dienste, die von einer anderen Domäne verarbeitet werden.</span><span class="sxs-lookup"><span data-stu-id="2808d-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="2808d-115">Wenn Sie beispielsweise die neue Domäne nur für E-Mails verwenden möchten, wählen Sie **Exchange** aus, und deaktivieren Sie die Kontrollkästchen für **Skype for Business** und **Verwaltung mobiler Geräte für Office 365**.</span><span class="sxs-lookup"><span data-stu-id="2808d-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="2808d-116">Wählen Sie **Weiter**, **Autorisieren**, **Weiter** und dann **Fertigstellen** aus.</span><span class="sxs-lookup"><span data-stu-id="2808d-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="2808d-117">Ihre neue Domäne wurde hinzugefügt.</span><span class="sxs-lookup"><span data-stu-id="2808d-117">Your new domain has been added.</span></span>

<span data-ttu-id="2808d-118">Um E-Mails in Ihrer neuen Domäne zu empfangen, müssen Sie für jeden Benutzer einen neuen E-Mail-Alias hinzufügen:</span><span class="sxs-lookup"><span data-stu-id="2808d-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="2808d-119">Wählen Sie **Benutzer**, **Aktive Benutzer** und dann den Benutzer aus, dem der neue Alias zugewiesen werden soll.</span><span class="sxs-lookup"><span data-stu-id="2808d-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="2808d-120">Wählen Sie **Verwalten von E-Mail-Aliasen** und dann **Alias hinzufügen** aus.</span><span class="sxs-lookup"><span data-stu-id="2808d-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="2808d-121">Geben Sie den Benutzernamen ein, und wählen Sie dann in der Dropdownliste die neue Domäne aus.</span><span class="sxs-lookup"><span data-stu-id="2808d-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="2808d-122">Klicken Si auf **Änderungen speichern**, und schließen Sie dann das Fenster.</span><span class="sxs-lookup"><span data-stu-id="2808d-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="2808d-123">Wiederholen Sie diese Schritte für jeden Benutzer, der E-Mails in der neuen Domäne empfangen soll.</span><span class="sxs-lookup"><span data-stu-id="2808d-123">Repeat these steps for each user who should receive email at the new domain.</span></span>

## <a name="related-content"></a><span data-ttu-id="2808d-124">Verwandte Inhalte</span><span class="sxs-lookup"><span data-stu-id="2808d-124">Related content</span></span>

<span data-ttu-id="2808d-125">[Hinzufügen einer](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) Domäne zu Microsoft 365 (Artikel) Hinzufügen von [DNS-Einträgen](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) zum Verbinden Ihrer Domäne (Artikel) Ändern von [Namenservern](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) zum Einrichten von Microsoft 365 mit beliebigen Domänenregistrierungsstellen (Artikel) [Häufig](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) gestellte Fragen zu Domänen (Artikel)</span><span class="sxs-lookup"><span data-stu-id="2808d-125">[Add a domain to Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/setup/add-domain) (article) [Add DNS records to connect your domain](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider) (article) [Change nameservers to set up Microsoft 365 with any domain registrar](https://docs.microsoft.com/microsoft-365/admin/get-help-with-domains/change-nameservers-at-any-domain-registrar) (article) [Domains FAQ](https://docs.microsoft.com/microsoft-365/admin/setup/domains-faq) (article)</span></span>