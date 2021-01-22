---
title: Hinzufügen Ihrer Google Workspace-Domäne
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Erfahren Sie, wie Sie Ihre Domäne von Google Workspace zu Microsoft 365 Business verschieben.
ms.openlocfilehash: 23ca451cfdcb67898a10935101efedcdf360ef91
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925002"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="71eb5-103">Hinzufügen Ihrer Google Workspace-Domäne zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="71eb5-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="71eb5-104">Fügen Sie Ihre Google Workspace-Domäne zu Microsoft 365 Business hinzu, damit Sie Ihre geschäftliche E-Mail-Adresse weiterhin verwenden können.</span><span class="sxs-lookup"><span data-stu-id="71eb5-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="71eb5-105">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="71eb5-105">Try it!</span></span>

1. <span data-ttu-id="71eb5-106">Wechseln Sie zum [Microsoft 365 Admin Center.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="71eb5-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="71eb5-107">Wählen Sie im Microsoft 365 Admin Center im linken Navigationsbereich **"Alle** anzeigen", **"Einstellungen"** und dann **"Domänen" aus.**</span><span class="sxs-lookup"><span data-stu-id="71eb5-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="71eb5-108">Wählen **Sie "Domäne hinzufügen"** aus, geben Sie Ihren Domänennamen ein, und wählen **Sie dann "Diese Domäne verwenden" aus.**</span><span class="sxs-lookup"><span data-stu-id="71eb5-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="71eb5-109">Choose, **Add a TXT record to the domains DNS records,** select **Continue**, and copy the TXT value.</span><span class="sxs-lookup"><span data-stu-id="71eb5-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="71eb5-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, View **Details**, **Manage domain**, **DNS**, and then scroll down to Custom **resource records**.</span><span class="sxs-lookup"><span data-stu-id="71eb5-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="71eb5-111">Öffnen Sie die Dropdownliste für den Eintragstyp, wählen **Sie TXT** aus, fügen Sie den kopierten TXT-Wert ein, und wählen Sie dann **"Hinzufügen" aus.**</span><span class="sxs-lookup"><span data-stu-id="71eb5-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="71eb5-112">Das Update dauert in der Regel innerhalb weniger Minuten, kann aber bis zu 48 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="71eb5-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="71eb5-113">Kehren Sie zum Microsoft 365 Admin Center zurück, wählen **Sie "Überprüfen"** und dann **"Schließen" aus.**</span><span class="sxs-lookup"><span data-stu-id="71eb5-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="71eb5-114">Wenn Sie Ihre Domäne als primäre E-Mail-Adresse für Ihre Benutzer festlegen möchten, wählen Sie im linken Navigationsbereich **"Aktive**  >  **Benutzer" aus.**</span><span class="sxs-lookup"><span data-stu-id="71eb5-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="71eb5-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span><span class="sxs-lookup"><span data-stu-id="71eb5-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="71eb5-116">Wiederholen Sie diesen Vorgang für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="71eb5-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="71eb5-117">Wenn Sie fertig sind, können Sie die Office-Apps installieren und Ihre E-Mail- und Kalenderelemente zu Microsoft 365 migrieren.</span><span class="sxs-lookup"><span data-stu-id="71eb5-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 