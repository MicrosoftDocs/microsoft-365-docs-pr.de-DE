---
title: Verwalten von Lizenzen für Geräte
f1.keywords:
- CSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
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
ms.custom: okr_SMB
search.appverid:
- MET150
ms.openlocfilehash: c7c747d5f4d2408b717bf16068d23c7882c2d667
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 02/24/2020
ms.locfileid: "42242325"
---
# <a name="manage-licenses-for-devices"></a><span data-ttu-id="1baad-103">Verwalten von Lizenzen für Geräte</span><span class="sxs-lookup"><span data-stu-id="1baad-103">Manage licenses for devices</span></span>

<span data-ttu-id="1baad-104">Wenn Sie Office 365 ProPlus für Bildung (Gerät) haben, können Sie Geräte mithilfe von Azure AD Gruppenlizenzen zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1baad-104">If you have Office 365 ProPlus for Education (device), you can assign licenses to devices by using Azure AD groups.</span></span> <span data-ttu-id="1baad-105">Wenn ein Gerät über eine Lizenz verfügt, kann jeder, der dieses Gerät verwendet, Office 365 verwenden.</span><span class="sxs-lookup"><span data-stu-id="1baad-105">When a device has a license, anyone who uses that device can use Office 365.</span></span> <span data-ttu-id="1baad-106">Angenommen, Sie verfügen über 20 Laptops und Tablets, die von Personen in Ihrer Organisation verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="1baad-106">For example, let’s say you have 20 laptops and tablets that are used by people in your organization.</span></span> <span data-ttu-id="1baad-107">Wenn Sie jedem Gerät eine Lizenz zuweisen, verwendet jede Person, die sich bei einem der Geräte anmeldet, Office 365, ohne dass eine eigene Lizenz erforderlich ist.</span><span class="sxs-lookup"><span data-stu-id="1baad-107">When you assign a license to each device, each person who logs in to one of the devices uses Office 365 without the need for their own license.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1baad-108">Office 365 ProPlus für Education (Gerät) steht nur für Education a3-und A5-Volumenlizenzkunden zur Verfügung.</span><span class="sxs-lookup"><span data-stu-id="1baad-108">Office 365 ProPlus for Education (device) is only available to Education A3 and A5 volume licensing customers.</span></span>

<span data-ttu-id="1baad-109">Zunächst erstellen Sie eine Gruppe im Azure Active Directory Admin Center und weisen dann der Gruppe Geräte zu.</span><span class="sxs-lookup"><span data-stu-id="1baad-109">To begin, you create a group in the Azure Active Directory admin center, and then assign devices to the group.</span></span> <span data-ttu-id="1baad-110">Weitere Informationen zur Geräte Lizenzierung, einschließlich Geräteanforderungen, zu den Arten von Gruppen, die Sie verwenden können, und zum Konfigurieren Office 365 ProPlus für die Verwendung der Geräte Lizenzierung finden Sie unter [Geräte Lizenzierung für Office 365 ProPlus für Education-Kunden](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span><span class="sxs-lookup"><span data-stu-id="1baad-110">To learn more about device licensing, including device requirements, what types of groups you can use, and how to configure Office 365 ProPlus to use device licensing, see [Device licensing for Office 365 ProPlus for Education customers](https://go.microsoft.com/fwlink/p/?linkid=2094216).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1baad-111">Sie müssen ein globaler Administrator sein, um die Aufgaben in diesem Artikel durchführen zu können.</span><span class="sxs-lookup"><span data-stu-id="1baad-111">You must be a Global admin to complete the tasks in this article.</span></span>

## <a name="assign-licenses-to-devices"></a><span data-ttu-id="1baad-112">Zuweisen von Lizenzen zu Geräten</span><span class="sxs-lookup"><span data-stu-id="1baad-112">Assign licenses to devices</span></span>

<span data-ttu-id="1baad-113">Wenn Sie einer Gruppe Lizenzen zuweisen, weisen Sie allen Geräten innerhalb der Gruppe Lizenzen zu.</span><span class="sxs-lookup"><span data-stu-id="1baad-113">When you assign licenses to a group, you assign licenses to all devices within the group.</span></span> <span data-ttu-id="1baad-114">Sie können einer einzelnen Gruppe nur ein Abonnement zuweisen.</span><span class="sxs-lookup"><span data-stu-id="1baad-114">You can only assign one subscription to any single group.</span></span>

1. <span data-ttu-id="1baad-115">Wechseln Sie im Microsoft 365 Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="1baad-115">In the Microsoft 365 admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="1baad-116">Wählen Sie \*\*\*\* auf der Seite Lizenzen **Office 365 ProPlus für Bildung (Gerät)** aus.</span><span class="sxs-lookup"><span data-stu-id="1baad-116">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="1baad-117">Wählen Sie auf der Seite **Office 365 ProPlus-Education (Gerät)** ein Abonnement aus, und wählen Sie dann **Lizenzen zuweisen**aus.</span><span class="sxs-lookup"><span data-stu-id="1baad-117">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, then choose **Assign licenses**.</span></span>
4. <span data-ttu-id="1baad-118">Geben Sie im Bereich **Lizenzen einer Gruppe zuweisen** die Eingabe eines Gruppennamens ein, und wählen Sie ihn aus den Ergebnissen aus, um ihn der Liste hinzuzufügen.</span><span class="sxs-lookup"><span data-stu-id="1baad-118">In the **Assign licenses to a group** pane, begin typing a group name, and then choose it from the results to add it to the list.</span></span>
6. <span data-ttu-id="1baad-119">Wählen Sie **assign**und dann **Close**aus.</span><span class="sxs-lookup"><span data-stu-id="1baad-119">Choose **Assign**, then choose **Close**.</span></span>

## <a name="unassign-licenses-from-devices"></a><span data-ttu-id="1baad-120">Aufheben der Zuweisung von Lizenzen von Geräten</span><span class="sxs-lookup"><span data-stu-id="1baad-120">Unassign licenses from devices</span></span>

<span data-ttu-id="1baad-121">Wenn Sie die Zuweisung von Lizenzen von einer Gruppe aufheben, entfernen Sie die Lizenzen von allen Geräten innerhalb der Gruppe.</span><span class="sxs-lookup"><span data-stu-id="1baad-121">When you unassign licenses from a group, you remove the licenses from all devices within the group.</span></span> <span data-ttu-id="1baad-122">Alle apps und die zugehörigen Daten sind dann schreibgeschützt.</span><span class="sxs-lookup"><span data-stu-id="1baad-122">All apps and their associated data are then read-only.</span></span>

1. <span data-ttu-id="1baad-123">Wechseln Sie im Admin Center zur Seite **Abrechnungs** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Lizenzen</a> .</span><span class="sxs-lookup"><span data-stu-id="1baad-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>
2. <span data-ttu-id="1baad-124">Wählen Sie \*\*\*\* auf der Seite Lizenzen **Office 365 ProPlus für Bildung (Gerät)** aus.</span><span class="sxs-lookup"><span data-stu-id="1baad-124">On the **Licenses** page, choose **Office 365 ProPlus for Education (device)**.</span></span>
3. <span data-ttu-id="1baad-125">Wählen Sie auf der Seite **Office 365 ProPlus-Education (Gerät)** ein Abonnement aus, wählen Sie **Weitere Aktionen**aus, und wählen Sie dann Lizenzen für die **Zuweisung**aufheben aus.</span><span class="sxs-lookup"><span data-stu-id="1baad-125">On the **Office 365 ProPlus for Education (device)** page, choose a subscription, choose **More actions**, then choose **Unassign licenses**.</span></span>
5. <span data-ttu-id="1baad-126">Wählen Sie im Dialogfeld **Lizenzen** aufheben die Option **Zuweisung**aufheben aus.</span><span class="sxs-lookup"><span data-stu-id="1baad-126">In the **Unassign licenses** dialog box, choose **Unassign**.</span></span>