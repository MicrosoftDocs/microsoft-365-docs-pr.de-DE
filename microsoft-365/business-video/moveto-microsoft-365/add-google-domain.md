---
title: Hinzufügen Ihrer Google Workspace-Domäne
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
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
description: Erfahren Sie, wie Sie Ihre Domäne von Google Workspace zu Microsoft 365 Business verschieben.
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578771"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="3ab44-103">Hinzufügen Ihrer Google Workspace-Domäne zu Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3ab44-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="3ab44-104">Fügen Sie Ihre Google Workspace-Domäne zu Microsoft 365 Business hinzu, damit Sie Ihre geschäftliche E-Mail-Adresse weiterhin verwenden können.</span><span class="sxs-lookup"><span data-stu-id="3ab44-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="3ab44-105">Probieren Sie es aus!</span><span class="sxs-lookup"><span data-stu-id="3ab44-105">Try it!</span></span>

1. <span data-ttu-id="3ab44-106">Wechseln Sie zum [Microsoft 365 Admin Center](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="3ab44-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="3ab44-107">Wählen Sie im Microsoft 365 Admin Center im linken Navigations navi die Option **Alle** anzeigen , **Einstellungen** und dann **Domänen aus.**</span><span class="sxs-lookup"><span data-stu-id="3ab44-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="3ab44-108">Wählen **Sie Domäne hinzufügen** aus, geben Sie Ihren Domänennamen ein, und wählen Sie dann Diese Domäne verwenden **aus.**</span><span class="sxs-lookup"><span data-stu-id="3ab44-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="3ab44-109">Wählen Sie, **Fügen Sie den Domänen DNS-Einträge einen TXT-Eintrag hinzu,** wählen Sie **Weiter** aus, und kopieren Sie den TXT-Wert.</span><span class="sxs-lookup"><span data-stu-id="3ab44-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="3ab44-110">Wechseln Sie zurück zur [Google Admin Console,](https://admin.google.com)wählen Sie **Domänen** **,** Domänen verwalten , **Details anzeigen**, **Domäne** verwalten, **DNS**, und scrollen Sie dann nach unten zu **Benutzerdefinierte Ressourceneinträge**.</span><span class="sxs-lookup"><span data-stu-id="3ab44-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="3ab44-111">Öffnen Sie die Dropdownliste Datensatztyp, wählen Sie **TXT** aus, fügen Sie den kopierten TXT-Wert ein, und wählen Sie **dann Hinzufügen aus.**</span><span class="sxs-lookup"><span data-stu-id="3ab44-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="3ab44-112">Das Update dauert in der Regel innerhalb weniger Minuten, kann jedoch bis zu 48 Stunden dauern.</span><span class="sxs-lookup"><span data-stu-id="3ab44-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="3ab44-113">Kehren Sie zum Microsoft 365 Admin Center zurück, wählen **Sie Überprüfen** und dann **Schließen aus.**</span><span class="sxs-lookup"><span data-stu-id="3ab44-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="3ab44-114">Wenn Sie Ihre Domäne als primäre E-Mail für Ihre Benutzer festlegen möchten, wählen Sie im linken Navigations navi die Option **Benutzer**  >  **Aktive Benutzer aus.**</span><span class="sxs-lookup"><span data-stu-id="3ab44-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="3ab44-115">Wählen Sie einen Benutzer aus, wählen Sie **Benutzername und** E-Mail verwalten, **Bearbeiten** aus, wählen Sie Ihre Domäne aus der Dropdownliste aus, und wählen Sie dann **Fertig** und Änderungen **speichern aus.**</span><span class="sxs-lookup"><span data-stu-id="3ab44-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="3ab44-116">Wiederholen Sie diesen Vorgang für jeden Benutzer.</span><span class="sxs-lookup"><span data-stu-id="3ab44-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="3ab44-117">Wenn Sie fertig sind, können Sie Office-Apps installieren und Ihre E-Mail- und Kalenderelemente zu Microsoft 365 migrieren.</span><span class="sxs-lookup"><span data-stu-id="3ab44-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 