---
title: Verwalten von Lizenzen für Geräte
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
- commerce
description: Hier erfahren Sie, wie Sie Gruppen für die Verwendung mit Geräten Lizenzen zuweisen.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: 29bd56ccff01d8c21cc67d1188fa21e338fb4b7e
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 10/21/2020
ms.locfileid: "48638183"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="88d1b-103">Verwalten von Lizenzen für Geräte</span><span class="sxs-lookup"><span data-stu-id="88d1b-103">Manage licenses for devices</span></span>

<span data-ttu-id="88d1b-104">Wenn Sie Microsoft 365 Apps für Unternehmen (Gerät) oder Microsoft 365 Apps für Bildungseinrichtungen (Gerät) haben, können Sie Geräte mithilfe Azure AD Gruppenlizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="88d1b-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="88d1b-105">Wenn ein Gerät über eine Lizenz verfügt, kann jeder, der dieses Gerät verwendet, Microsoft 365-Apps für Enterprise (zuvor mit dem Namen Office 365 ProPlus) verwenden.</span><span class="sxs-lookup"><span data-stu-id="88d1b-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="88d1b-106">Angenommen, Sie verfügen über 20 Laptops und Tablets, die von Personen in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="88d1b-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="88d1b-107">Wenn Sie jedem Gerät eine Lizenz zuweisen, verwendet jede Person, die sich bei einem der Geräte anmeldet, Microsoft 365-Apps für Enterprise, ohne dass eine eigene Lizenz erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="88d1b-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88d1b-108">Die gerätebasierte Lizenzierung für Microsoft 365-Apps für Unternehmen ist nur als Add-on-Lizenz für einige kommerzielle Kunden und einige Schulungs Kunden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="88d1b-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="88d1b-109">Für kommerzielle Kunden ist die Lizenz *Microsoft 365 apps for Enterprise (Gerät)* und steht nur über Enterprise Agreement/Enterprise Agreement Subscription zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="88d1b-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="88d1b-110">Für Education-Kunden ist die Lizenz *Microsoft 365 apps for Education (Gerät)* und ist nur über die Registrierung für Bildungslösungen (EBS) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="88d1b-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="88d1b-111">Weitere Informationen finden Sie im Blogbeitrag zur [Verfügbarkeit von Bildungseinrichtungen](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="88d1b-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="88d1b-112">Wenden Sie sich für kommerzielle Verfügbarkeit an Ihren Microsoft-Konto Vertreter.</span><span class="sxs-lookup"><span data-stu-id="88d1b-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="88d1b-113">Zunächst erstellen Sie eine Gruppe im Azure Active Directory Admin Center und weisen dann der Gruppe Geräte zu.</span><span class="sxs-lookup"><span data-stu-id="88d1b-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="88d1b-114">Weitere Informationen zur Geräte Lizenzierung, einschließlich Geräteanforderungen, zu den Arten von Gruppen, die Sie verwenden können, und zum Konfigurieren von Microsoft 365-Apps für Enterprise zur Verwendung der Geräte Lizenzierung finden Sie unter [Device-based licensing for Microsoft 365 apps for Enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="88d1b-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="88d1b-115">Sie müssen ein globaler Administrator sein, um die Aufgaben in diesem Artikel durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="88d1b-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="88d1b-116">Zuweisen von Lizenzen zu Geräten</span><span class="sxs-lookup"><span data-stu-id="88d1b-116">Assign licenses to devices</span></span>

<span data-ttu-id="88d1b-117">Wenn Sie einer Gruppe Lizenzen zuweisen, weisen Sie allen Geräten innerhalb der Gruppe Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="88d1b-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="88d1b-118">Sie können einer einzelnen Gruppe nur ein Abonnement zuweisen.</span><span class="sxs-lookup"><span data-stu-id="88d1b-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="88d1b-119">Wechseln Sie im Microsoft 365 Admin Center zur Seite **Abrechnungs**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="88d1b-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="88d1b-120">Wählen Sie auf der Seite **Lizenzen** die Option **Microsoft 365 apps for Education (Gerät)** oder **Microsoft 365 apps for Enterprise (Gerät)** aus.</span><span class="sxs-lookup"><span data-stu-id="88d1b-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="88d1b-121">Wählen Sie auf der nächsten Seite ein Abonnement aus, und wählen Sie dann **Lizenzen zuweisen**aus.</span><span class="sxs-lookup"><span data-stu-id="88d1b-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="88d1b-122">Geben Sie im Bereich **Lizenzen einer Gruppe zuweisen** die Eingabe eines Gruppennamens ein, und wählen Sie ihn aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="88d1b-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="88d1b-123">Wählen Sie **assign**und dann **Close**aus.</span><span class="sxs-lookup"><span data-stu-id="88d1b-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="88d1b-124">Aufheben der Zuweisung von Lizenzen von Geräten</span><span class="sxs-lookup"><span data-stu-id="88d1b-124">Unassign licenses from devices</span></span>

<span data-ttu-id="88d1b-125">Wenn Sie die Zuweisung von Lizenzen von einer Gruppe aufheben, entfernen Sie die Lizenzen von allen Geräten innerhalb der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="88d1b-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="88d1b-126">Alle apps und die zugehörigen Daten sind dann schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="88d1b-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="88d1b-127">Wechseln Sie im Admin Center zur Seite **Abrechnungs**  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="88d1b-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="88d1b-128">Wählen Sie auf der Seite **Lizenzen** die Option **Microsoft 365 apps for Education (Gerät)** oder **Microsoft 365 apps for Enterprise (Gerät)** aus.</span><span class="sxs-lookup"><span data-stu-id="88d1b-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="88d1b-129">Wählen Sie auf der nächsten Seite ein Abonnement aus, wählen Sie **Weitere Aktionen**aus, und wählen Sie dann Lizenzen für die **Zuweisung**aufheben aus.</span><span class="sxs-lookup"><span data-stu-id="88d1b-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="88d1b-130">Wählen Sie im Dialogfeld **Lizenzen** aufheben die Option **Zuweisung**aufheben aus.</span><span class="sxs-lookup"><span data-stu-id="88d1b-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>