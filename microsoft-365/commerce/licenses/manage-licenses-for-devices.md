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
description: Erfahren Sie, wie Sie Gruppen Lizenzen für die Verwendung mit Geräten zuweisen.
ms.custom:
- okr_SMB
- AdminSurgePortfolio
search.appverid:
- MET150
ms.openlocfilehash: a316810e3e6ddb1373697dc56b2fccb5a32cf0b1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911482"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="6be74-103">Verwalten von Lizenzen für Geräte</span><span class="sxs-lookup"><span data-stu-id="6be74-103">Manage licenses for devices</span></span>

<span data-ttu-id="6be74-104">Wenn Sie über Microsoft 365 Apps for Enterprise (Gerät) oder Microsoft 365 Apps for Education (Gerät) verfügen, können Sie Mithilfe von Azure AD-Gruppen Lizenzen zu Geräten zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6be74-104">If you have Microsoft 365 Apps for enterprise (device) or Microsoft 365 Apps for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="6be74-105">Wenn ein Gerät über eine Lizenz verfügt, kann jeder, der dieses Gerät verwendet, Microsoft 365 Apps for Enterprise (zuvor Office 365 ProPlus genannt) verwenden.</span><span class="sxs-lookup"><span data-stu-id="6be74-105">When a device has a license, anyone who uses that device can use Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="6be74-106">Angenommen, Sie verfügen über 20 Laptops und Tablets, die von Personen in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="6be74-106">For example, let's say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="6be74-107">Wenn Sie jedem Gerät eine Lizenz zuweisen, verwendet jede Person, die sich bei einem der Geräte anmeldet, Microsoft 365 Apps for Enterprise, ohne dass eine eigene Lizenz erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="6be74-107">When you assign a license to each device, each person who logs in to one of the devices uses Microsoft 365 Apps for enterprise without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6be74-108">Die gerätebasierte Lizenzierung für Microsoft 365 Apps for Enterprise ist nur als Add-On-Lizenz für einige kommerzielle Kunden und einige Bildungskunden verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6be74-108">Device-based licensing for Microsoft 365 Apps for enterprise is available only as an add-on license for some commercial customers and some education customers.</span></span> <span data-ttu-id="6be74-109">Für kommerzielle Kunden ist die Lizenz *Microsoft 365 Apps for Enterprise (Gerät)* und nur über Konzernvertrag/Konzernvertrag verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6be74-109">For commercial customers, the license is *Microsoft 365 Apps for enterprise (device)* and is available only through Enterprise Agreement/Enterprise Agreement Subscription.</span></span> <span data-ttu-id="6be74-110">Für Bildungskunden ist die Lizenz *Microsoft 365 Apps for Education (Gerät)* und nur über Enrollment for Education Solutions (EES) verfügbar.</span><span class="sxs-lookup"><span data-stu-id="6be74-110">For education customers, the license is *Microsoft 365 Apps for Education (device)* and is available only through Enrollment for Education Solutions (EES).</span></span> <span data-ttu-id="6be74-111">Weitere Informationen finden Sie im Blogbeitrag zur Verfügbarkeit [von Bildungseinrichtungen](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span><span class="sxs-lookup"><span data-stu-id="6be74-111">For more information, read the blog post on [education availability](https://educationblog.microsoft.com/2019/08/attention-it-administrators-announcing-device-based-subscription-for-education/).</span></span> <span data-ttu-id="6be74-112">Wenden Sie sich zur kommerziellen Verfügbarkeit an Ihren Microsoft-Kontomitarbeiter.</span><span class="sxs-lookup"><span data-stu-id="6be74-112">For commercial availability, contact your Microsoft account representative.</span></span>

<span data-ttu-id="6be74-113">Zunächst erstellen Sie eine Gruppe im Azure Active Directory Admin Center und weisen der Gruppe dann Geräte zu.</span><span class="sxs-lookup"><span data-stu-id="6be74-113">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="6be74-114">Weitere Informationen zur Gerätelizenzierung, einschließlich gerätebasierter Anforderungen, der arten von Gruppen, die Sie verwenden können, und zum Konfigurieren von Microsoft 365 Apps for Enterprise für die Verwendung der Gerätelizenzierung finden Sie unter Gerätebasierte Lizenzierung für [Microsoft 365 Apps for Enterprise](/deployoffice/device-based-licensing).</span><span class="sxs-lookup"><span data-stu-id="6be74-114">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Microsoft 365 Apps for enterprise to use device licensing, see [Device-based licensing for Microsoft 365 Apps for enterprise](/deployoffice/device-based-licensing).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="6be74-115">Sie müssen ein globaler Administrator sein, um die Aufgaben in diesem Artikel ausführen zu können.</span><span class="sxs-lookup"><span data-stu-id="6be74-115">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="6be74-116">Zuweisen von Lizenzen zu Geräten</span><span class="sxs-lookup"><span data-stu-id="6be74-116">Assign licenses to devices</span></span>

<span data-ttu-id="6be74-117">Wenn Sie einer Gruppe Lizenzen zuweisen, weisen Sie allen Geräten innerhalb der Gruppe Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="6be74-117">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="6be74-118">Sie können einer einzelnen Gruppe nur ein Abonnement zuweisen.</span><span class="sxs-lookup"><span data-stu-id="6be74-118">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="6be74-119">Wechseln Sie im Microsoft 365 Admin Center zur Seite  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Abrechnungslizenzen.</a></span><span class="sxs-lookup"><span data-stu-id="6be74-119">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="6be74-120">Wählen Sie **auf** der Seite Lizenzen **die Option Microsoft 365 Apps for Education (Gerät)** oder **Microsoft 365 Apps for Enterprise (Gerät) aus.**</span><span class="sxs-lookup"><span data-stu-id="6be74-120">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="6be74-121">Wählen Sie auf der nächsten Seite ein Abonnement aus, und wählen Sie dann **Lizenzen zuweisen aus.**</span><span class="sxs-lookup"><span data-stu-id="6be74-121">On the next page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="6be74-122">Beginnen Sie **im** Bereich Zuweisen von Lizenzen zu einem Gruppenbereich mit der Eingabe eines Gruppennamens, und wählen Sie ihn dann aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="6be74-122">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
5. <span data-ttu-id="6be74-123">Wählen **Sie Zuweisen** aus, und wählen Sie dann Schließen **aus.**</span><span class="sxs-lookup"><span data-stu-id="6be74-123">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="6be74-124">Zuweisen von Lizenzen von Geräten</span><span class="sxs-lookup"><span data-stu-id="6be74-124">Unassign licenses from devices</span></span>

<span data-ttu-id="6be74-125">Wenn Sie lizenzen aus einer Gruppe entfernen, entfernen Sie die Lizenzen von allen Geräten innerhalb der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="6be74-125">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="6be74-126">Alle Apps und ihre zugehörigen Daten sind dann schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="6be74-126">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="6be74-127">Wechseln Sie im Admin Center zur Seite  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Abrechnungslizenzen.</a></span><span class="sxs-lookup"><span data-stu-id="6be74-127">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="6be74-128">Wählen Sie **auf** der Seite Lizenzen **die Option Microsoft 365 Apps for Education (Gerät)** oder **Microsoft 365 Apps for Enterprise (Gerät) aus.**</span><span class="sxs-lookup"><span data-stu-id="6be74-128">On the **Licenses** page, choose **Microsoft 365 Apps for Education (device)** or **Microsoft 365 Apps for enterprise (device)**.</span></span>
3. <span data-ttu-id="6be74-129">Wählen Sie auf der nächsten Seite ein Abonnement aus, wählen Sie **Weitere Aktionen** aus, und wählen Sie dann Lizenzen zuweisen **aus.**</span><span class="sxs-lookup"><span data-stu-id="6be74-129">On the next page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
4. <span data-ttu-id="6be74-130">Wählen Sie **im Dialogfeld Lizenzen** nicht zuweisen die Option **Unassign aus.**</span><span class="sxs-lookup"><span data-stu-id="6be74-130">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>